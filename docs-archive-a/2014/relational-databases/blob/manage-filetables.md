---
title: Gérer des FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], security
- FileTables [SQL Server], managing access
ms.assetid: 93af982c-b4fe-4be0-8268-11f86dae27e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a15a914c243f1fafd3b913d98113e984bf533086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699779"
---
# <a name="manage-filetables"></a><span data-ttu-id="53611-102">Gérer des FileTables</span><span class="sxs-lookup"><span data-stu-id="53611-102">Manage FileTables</span></span>
  <span data-ttu-id="53611-103">Décrit les tâches d'administration courantes permettant de gérer des FileTables.</span><span class="sxs-lookup"><span data-stu-id="53611-103">Describes common administrative tasks for managing FileTables.</span></span>  
  
##  <a name="how-to-get-a-list-of-filetables-and-related-objects"></a><a name="HowToEnumerate"></a> <span data-ttu-id="53611-104">Procédure : obtenir une liste de FileTables et d’objets connexes</span><span class="sxs-lookup"><span data-stu-id="53611-104">How To: Get a List of FileTables and Related Objects</span></span>  
 <span data-ttu-id="53611-105">Pour obtenir une liste de FileTables, interrogez l'un des affichages catalogue suivants :</span><span class="sxs-lookup"><span data-stu-id="53611-105">To get a list of FileTables, query one of the following catalog views:</span></span>  
  
-   [<span data-ttu-id="53611-106">sys.filetables &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="53611-106">sys.filetables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-filetables-transact-sql)  
  
-   <span data-ttu-id="53611-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (vérifiez la valeur de la colonne **is_filetable**)</span><span class="sxs-lookup"><span data-stu-id="53611-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (Check the value of the **is_filetable** column.)</span></span>  
  
```sql  
SELECT * FROM sys.filetables;  
GO  
  
SELECT * FROM sys.tables WHERE is_filetable = 1;  
GO  
```  
  
 <span data-ttu-id="53611-108">Pour obtenir une liste des objets définis par le système créés avec les FileTables associés, interrogez l’affichage catalogue [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53611-108">To get a list of the system-defined objects that were created when the associated FileTables were created, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
SELECT object_id, OBJECT_NAME(object_id) AS 'Object Name'  
    FROM sys.filetable_system_defined_objects  
    WHERE object_id = filetable_object_id;  
GO  
```  
  
##  <a name="disabling-and-re-enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsDisabling"></a> <span data-ttu-id="53611-109">Désactivation et réactivation de l'accès non transactionnel au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="53611-109">Disabling and Re-enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="53611-110">Pour acquérir l'accès exclusif qui est obligatoire pour certaines tâches d'administration, vous devrez peut-être désactiver temporairement l'accès non transactionnel.</span><span class="sxs-lookup"><span data-stu-id="53611-110">To acquire the exclusive access that is required for certain administrative tasks, you may have to disable non-transactional access temporarily.</span></span>  
  
 <span data-ttu-id="53611-111">**Comportement de l'instruction ALTER DATABASE lors de la modification du niveau d'accès non transactionnel**</span><span class="sxs-lookup"><span data-stu-id="53611-111">**Behavior of the ALTER DATABASE statement when changing the level of non-transactional access**</span></span>  
  
-   <span data-ttu-id="53611-112">Lorsque vous affectez à l'accès non transactionnel la valeur READ_ONLY ou OFF, la commande ALTER DATABASE ne redonne pas le contrôle à l'utilisateur tant que des descripteurs de fichiers ouverts sont en conflit avec l'opération demandée.</span><span class="sxs-lookup"><span data-stu-id="53611-112">When you set non-transactional access to READ_ONLY or OFF, the ALTER DATABASE command does not return control to the user as long as there are open file handles that conflict with the requested operation.</span></span> <span data-ttu-id="53611-113">Les descripteurs de fichiers qui sont en conflit avec cette opération sont notamment les suivants :</span><span class="sxs-lookup"><span data-stu-id="53611-113">The file handles that conflict with this operation include the following:</span></span>  
  
    -   <span data-ttu-id="53611-114">Lorsque vous affectez à l'accès la valeur **NONE**, tous les descripteurs de fichiers ouverts.</span><span class="sxs-lookup"><span data-stu-id="53611-114">When you are setting access to **NONE**, all open file handles.</span></span>  
  
    -   <span data-ttu-id="53611-115">Lorsque vous affectez à l’accès la valeur **READ_ONLY**, tous les descripteurs de fichiers ouverts pour l’accès en écriture.</span><span class="sxs-lookup"><span data-stu-id="53611-115">When you are setting access to **READ_ONLY**, all file handles opened for write access.</span></span>  
  
     <span data-ttu-id="53611-116">Pour plus d'informations sur la manière de supprimer des descripteurs de fichiers ouverts, consultez [Suppression des descripteurs de fichiers ouverts associés à un FileTable](#BasicsKilling) dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="53611-116">For information about killing open file handles, see [Killing Open File Handles Associated with a FileTable](#BasicsKilling) in this topic.</span></span>  
  
     <span data-ttu-id="53611-117">Si la commande ALTER DATABASE est annulée ou se solde par une erreur de délai d'attente, le niveau d'accès transactionnel n'est pas modifié.</span><span class="sxs-lookup"><span data-stu-id="53611-117">If the ALTER DATABASE command is canceled or ends with a timeout, then the level of transactional access is not changed.</span></span>  
  
-   <span data-ttu-id="53611-118">Si vous appelez l’instruction ALTER DATABASE avec une clause WITH \<termination> (ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), tous les descripteurs de fichiers non transactionnels ouverts sont alors supprimés.</span><span class="sxs-lookup"><span data-stu-id="53611-118">If you call the ALTER DATABASE statement with a WITH \<termination> clause (ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), then all open non-transactional file handles are killed.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="53611-119">La suppression des descripteurs de fichiers ouverts peut entraîner la perte de données utilisateur non enregistrées.</span><span class="sxs-lookup"><span data-stu-id="53611-119">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="53611-120">Ce comportement est cohérent avec le comportement du système de fichiers lui-même.</span><span class="sxs-lookup"><span data-stu-id="53611-120">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
 <span data-ttu-id="53611-121">**Effets de la désactivation de l'accès non transactionnel**</span><span class="sxs-lookup"><span data-stu-id="53611-121">**Effects of disabling non-transactional access**</span></span>  
  
 <span data-ttu-id="53611-122">La modification du niveau de l'accès non transactionnel au niveau de la base de données a les effets suivants sur les répertoires FileTable sous le répertoire au niveau de la base de données :</span><span class="sxs-lookup"><span data-stu-id="53611-122">Changing the level of non-transactional access at the database level has the following effects on the FileTable directories under the database-level directory:</span></span>  
  
-   <span data-ttu-id="53611-123">Lorsque vous affectez à l'accès la valeur **NONE**, tous les répertoires FileTable et leur contenu ne sont plus accessibles ni visibles.</span><span class="sxs-lookup"><span data-stu-id="53611-123">When you set access to **NONE**, then all the FileTable directories and their contents are no longer accessible or visible.</span></span>  
  
-   <span data-ttu-id="53611-124">Lorsque vous affectez à l’accès la valeur **READ_ONLY**, tous les répertoires FileTable et leur contenu sont également en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="53611-124">When you set access to **READ_ONLY**, then all the FileTable directories and their contents are also read-only.</span></span>  
  
 <span data-ttu-id="53611-125">La désactivation de FILESTREAM au niveau de l'instance a les effets suivants sur les répertoires au niveau de la base de données sur cette instance et sur les répertoires de FileTable sous ceux-ci :</span><span class="sxs-lookup"><span data-stu-id="53611-125">Disabling FILESTREAM at the instance level has the following effects on the database-level directories on that instance, and the FileTable directories under them:</span></span>  
  
-   <span data-ttu-id="53611-126">Aucun des répertoires au niveau de la base de données sur l'instance n'est visible si FILESTREAM est désactivé au niveau de l'instance.</span><span class="sxs-lookup"><span data-stu-id="53611-126">None of the database-level directories on the instance are visible if FILESTREAM is disabled at the instance level.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-non-transactional-access-at-the-database-level"></a><a name="HowToDisable"></a> <span data-ttu-id="53611-127">Procédure : désactiver et réactiver l’accès non transactionnel au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="53611-127">How To: Disable and Re-enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="53611-128">Pour plus d’informations, consultez [Options ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="53611-128">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="53611-129">**Pour désactiver l'accès non transactionnel complet**</span><span class="sxs-lookup"><span data-stu-id="53611-129">**To disable full non-transactional access**</span></span>  
 <span data-ttu-id="53611-130">Appelez l’instruction **ALTER DATABASE** et définissez (avec SET) la valeur de **NON_TRANSACTED_ACCESS** sur **READ_ONLY** ou **OFF**.</span><span class="sxs-lookup"><span data-stu-id="53611-130">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **READ_ONLY** or **OFF**.</span></span>  
  
```sql  
-- Disable write access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = READ_ONLY );  
GO  
  
-- Disable non-transactional access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = OFF );  
GO  
```  
  
 <span data-ttu-id="53611-131">**Pour réactiver l'accès non transactionnel complet**</span><span class="sxs-lookup"><span data-stu-id="53611-131">**To re-enable full non-transactional access**</span></span>  
 <span data-ttu-id="53611-132">Appelez l’instruction **ALTER DATABASE** et définissez (avec SET) la valeur de **NON_TRANSACTED_ACCESS** sur **FULL**.</span><span class="sxs-lookup"><span data-stu-id="53611-132">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **FULL**.</span></span>  
  
```sql  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL );  
GO  
```  
  
###  <a name="how-to-ensure-the-visibility-of-the-filetables-in-a-database"></a><a name="visible"></a> <span data-ttu-id="53611-133">Procédure : assurer la visibilité des FileTables dans une base de données</span><span class="sxs-lookup"><span data-stu-id="53611-133">How to: Ensure the Visibility of the FileTables in a Database</span></span>  
 <span data-ttu-id="53611-134">Un répertoire au niveau de la base de données et les répertoires FileTable sous celui-ci sont visibles lorsque toutes les conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="53611-134">A database-level directory and the FileTable directories under it are visible when all of these conditions are true:</span></span>  
  
1.  <span data-ttu-id="53611-135">FILESTREAM est activé au niveau de l'instance.</span><span class="sxs-lookup"><span data-stu-id="53611-135">FILESTREAM is enabled at the instance level.</span></span>  
  
2.  <span data-ttu-id="53611-136">L'accès non transactionnel est activé au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="53611-136">Non-transactional access is enabled at the database level.</span></span>  
  
3.  <span data-ttu-id="53611-137">Un répertoire valide a été spécifié au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="53611-137">A valid directory has been specified at the database level.</span></span>  
  
##  <a name="disabling-and-re-enabling-the-filetable-namespace-at-the-table-level"></a><a name="BasicsEnabling"></a> <span data-ttu-id="53611-138">Désactivation et réactivation de l'espace de noms FileTable au niveau de la table</span><span class="sxs-lookup"><span data-stu-id="53611-138">Disabling and Re-enabling the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="53611-139">La désactivation de l'espace de noms FileTable désactive tous les déclencheurs et contraintes définis par le système qui ont été créés avec le FileTable.</span><span class="sxs-lookup"><span data-stu-id="53611-139">Disabling the FileTable namespace disables all the system-defined constraints and triggers that were created with the FileTable.</span></span> <span data-ttu-id="53611-140">Cela s'avère utile dans les cas où vous devez réorganiser un FileTable à grande échelle à l'aide d'opérations [!INCLUDE[tsql](../../includes/tsql-md.md)] sans avoir à appliquer la sémantique du FileTable.</span><span class="sxs-lookup"><span data-stu-id="53611-140">This is useful in cases where a FileTable has to be reorganized on a large scale by using [!INCLUDE[tsql](../../includes/tsql-md.md)] operations without incurring the expense of enforcing FileTable semantics.</span></span> <span data-ttu-id="53611-141">Toutefois, ces opérations peuvent laisser le FileTable dans un état cohérent, et de ce fait empêcher la réactivation de l'espace de noms FileTable.</span><span class="sxs-lookup"><span data-stu-id="53611-141">However these operations can leave the FileTable in an inconsistent state, and can prevent the re-enabling of the FileTable namespace.</span></span>  
  
 <span data-ttu-id="53611-142">La désactivation d'un espace de noms FileTable produit les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="53611-142">Disabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="53611-143">Les colonnes et les données FileTable ne sont pas supprimées physiquement de la table.</span><span class="sxs-lookup"><span data-stu-id="53611-143">FileTable columns and data are not physically dropped from the table.</span></span>  
  
-   <span data-ttu-id="53611-144">Le répertoire FileTable et les fichiers et répertoires qu'il contient disparaissent du système de fichiers et ne sont pas disponibles pour l'accès aux E/S de fichier.</span><span class="sxs-lookup"><span data-stu-id="53611-144">The FileTable directory and the files and directories that it contains disappear from the file system and are not available for file i/o access.</span></span>  
  
-   <span data-ttu-id="53611-145">Les colonnes FileTable définies par le système ne peuvent pas être supprimées et recréées ; toutefois, elles se comportent comme des colonnes ordinaires pour des opérations DML.</span><span class="sxs-lookup"><span data-stu-id="53611-145">System-defined FileTable columns cannot be dropped and recreated; otherwise, however, they behave like ordinary columns for DML operations.</span></span>  
  
-   <span data-ttu-id="53611-146">Les descripteurs de fichiers ouverts empêchent la désactivation des contraintes FileTable, cette opération requérant un verrou de schéma sur la table.</span><span class="sxs-lookup"><span data-stu-id="53611-146">Open file handles prevent the FileTable constraints from being disabled, since this operation requires a schema lock on the table.</span></span>  
  
-   <span data-ttu-id="53611-147">L'application de l'ensemble de la sémantique de FileTable, y compris les contraintes et les déclencheurs définies par le système, s'arrête une fois que l'espace de noms FileTable est désactivé.</span><span class="sxs-lookup"><span data-stu-id="53611-147">Enforcement of all the FileTable semantics, including system-defined constraints and triggers, stops after the FileTable namespace is disabled.</span></span>  
  
 <span data-ttu-id="53611-148">La réactivation d'un espace de noms FileTable produit les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="53611-148">Re-enabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="53611-149">La cohérence du FileTable est vérifiée.</span><span class="sxs-lookup"><span data-stu-id="53611-149">The FileTable is checked for consistency.</span></span> <span data-ttu-id="53611-150">Si des incohérences sont détectées, une erreur est générée et le FileTable reste désactivé ; sinon, le FileTable est réactivé.</span><span class="sxs-lookup"><span data-stu-id="53611-150">If inconsistencies are found, then an error is raised and the FileTable remains disabled; otherwise, the FileTable is re-enabled.</span></span>  
  
-   <span data-ttu-id="53611-151">L'application de la sémantique FileTable, y compris les contraintes et les déclencheurs définies par le système, est restaurée.</span><span class="sxs-lookup"><span data-stu-id="53611-151">The enforcement of FileTable semantics, including system-defined constraints and triggers, is restored.</span></span>  
  
-   <span data-ttu-id="53611-152">Le répertoire FileTable et les fichiers et répertoires qu'il contient sont visibles dans le système de fichiers et sont disponibles pour l'accès aux E/S de fichier.</span><span class="sxs-lookup"><span data-stu-id="53611-152">The FileTable directory and the files and directories that it contains become visible in the file system and become available for file i/o access.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-the-filetable-namespace-at-the-table-level"></a><a name="HowToEnableNS"></a> <span data-ttu-id="53611-153">Procédure : désactiver et réactiver l’espace de noms FileTable au niveau de la table</span><span class="sxs-lookup"><span data-stu-id="53611-153">How To: Disable and Re-enable the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="53611-154">Appelez l’instruction ALTER TABLE avec l’option **{ENABLE | DISABLE} FILETABLE_NAMESPACE** .</span><span class="sxs-lookup"><span data-stu-id="53611-154">Call the ALTER TABLE statement with the **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** option.</span></span>  
  
 <span data-ttu-id="53611-155">**Pour désactiver l'espace de noms FileTable**</span><span class="sxs-lookup"><span data-stu-id="53611-155">**To disable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    DISABLE FILETABLE_NAMESPACE;  
GO  
```  
  
 <span data-ttu-id="53611-156">**Pour réactiver l'espace de noms FileTable**</span><span class="sxs-lookup"><span data-stu-id="53611-156">**To re-enable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    ENABLE FILETABLE_NAMESPACE;  
GO  
```  
  
##  <a name="killing-open-file-handles-associated-with-a-filetable"></a><a name="BasicsKilling"></a> <span data-ttu-id="53611-157">Suppression des descripteurs de fichiers ouverts associés à un FileTable</span><span class="sxs-lookup"><span data-stu-id="53611-157">Killing Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="53611-158">Les descripteurs ouverts dans les fichiers stockés dans un FileTable peuvent empêcher l'accès exclusif qui est obligatoire pour certaines tâches d'administration.</span><span class="sxs-lookup"><span data-stu-id="53611-158">Open handles to the files stored in a FileTable can prevent the exclusive access that is required for certain administrative tasks.</span></span> <span data-ttu-id="53611-159">Vous devrez peut-être supprimer les descripteurs de fichiers ouverts associés à un ou à plusieurs FileTables pour activer des tâches urgentes.</span><span class="sxs-lookup"><span data-stu-id="53611-159">To enable urgent tasks, you may have to kill open file handles associated with one or more FileTables.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="53611-160">La suppression des descripteurs de fichiers ouverts peut entraîner la perte de données utilisateur non enregistrées.</span><span class="sxs-lookup"><span data-stu-id="53611-160">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="53611-161">Ce comportement est cohérent avec le comportement du système de fichiers lui-même.</span><span class="sxs-lookup"><span data-stu-id="53611-161">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
###  <a name="how-to-get-a-list-of-open-file-handles-associated-with-a-filetable"></a><a name="HowToListOpen"></a> <span data-ttu-id="53611-162">Procédure : obtenir une liste des descripteurs de fichiers ouverts associés à un FileTable</span><span class="sxs-lookup"><span data-stu-id="53611-162">How To: Get a List of Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="53611-163">Interrogez l’affichage catalogue [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53611-163">Query the catalog view [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.dm_filestream_non_transacted_handles;  
GO  
```  
  
###  <a name="how-to-kill-open-file-handles-associated-with-a-filetable"></a><a name="HowToKill"></a> <span data-ttu-id="53611-164">Procédure : supprimer les descripteurs de fichiers ouverts associés à un FileTable</span><span class="sxs-lookup"><span data-stu-id="53611-164">How To: Kill Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="53611-165">Appelez la procédure stockée [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) avec les arguments appropriés pour supprimer tous les descripteurs de fichiers ouverts dans la base de données ou dans le FileTable, ou pour supprimer un descripteur spécifique.</span><span class="sxs-lookup"><span data-stu-id="53611-165">Call the stored procedure [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) with the appropriate arguments to kill all open file handles in the database or in the FileTable, or to kill a specific handle.</span></span>  
  
```  
USE database_name;  
  
-- Kill all open handles in all the filetables in the database.  
EXEC sp_kill_filestream_non_transacted_handles;  
GO  
  
-- Kill all open handles in a single filetable.  
EXEC sp_kill_filestream_non_transacted_handles @table_name = 'filetable_name';  
GO  
  
-- Kill a single handle.  
EXEC sp_kill_filestream_non_transacted_handles @handle_id = integer_handle_id;  
GO  
```  
  
###  <a name="how-to-identify-the-locks-held-by-filetables"></a><a name="HowToIdentifyLocks"></a> <span data-ttu-id="53611-166">Procédure : identifier les verrous maintenus par les FileTables</span><span class="sxs-lookup"><span data-stu-id="53611-166">How to: Identify the Locks Held by FileTables</span></span>  
 <span data-ttu-id="53611-167">La plupart des verrous acceptés par les FileTables correspondent aux fichiers ouverts par des applications.</span><span class="sxs-lookup"><span data-stu-id="53611-167">Most locks taken by FileTables correspond to files opened by applications.</span></span>  
  
 <span data-ttu-id="53611-168">**Pour identifier les fichiers ouverts et les verrous associés**</span><span class="sxs-lookup"><span data-stu-id="53611-168">**To identify open files and the associated locks**</span></span>  
 <span data-ttu-id="53611-169">Joignez le champ **request_owner_id** dans la vue de gestion dynamique [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) au champ **fcb_id** dans [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="53611-169">Join the **request_owner_id** field in the dynamic management view [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) with the **fcb_id** field in [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span> <span data-ttu-id="53611-170">Dans certains cas, le verrou ne correspond pas à un descripteur de fichier ouvert unique.</span><span class="sxs-lookup"><span data-stu-id="53611-170">In some cases, the lock does not correspond to a single open file handle.</span></span>  
  
```sql  
SELECT opened_file_name  
    FROM sys.dm_filestream_non_transacted_handles  
    WHERE fcb_id IN  
        ( SELECT request_owner_id FROM sys.dm_tran_locks );  
GO  
```  
  
##  <a name="filetable-security"></a><a name="BasicsSecurity"></a> <span data-ttu-id="53611-171">Sécurité d'un FileTable</span><span class="sxs-lookup"><span data-stu-id="53611-171">FileTable Security</span></span>  
 <span data-ttu-id="53611-172">La sécurité des fichiers et des répertoires stockés dans des FileTables est uniquement assurée par la sécurité SQL Server.</span><span class="sxs-lookup"><span data-stu-id="53611-172">The files and directories stored in FileTables are secured by SQL Server security only.</span></span> <span data-ttu-id="53611-173">La sécurité basée sur les tables et les colonnes est appliquée pour l'accès au système de fichiers et l'accès [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53611-173">Table and column-based security is enforced for file system access as well as [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="53611-174">Les API de sécurité du système de fichiers Windows et les paramètres ACL ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="53611-174">Windows file system security APIs and ACL settings are not supported.</span></span>  
  
 <span data-ttu-id="53611-175">Les autorisations d'accès et de sécurité applicables aux conteneurs et aux groupes de fichiers FILESTREAM s'appliquent également aux FileTables, puisque les données des fichiers sont stockées en tant que colonne FILESTREAM dans le FileTable.</span><span class="sxs-lookup"><span data-stu-id="53611-175">The security and access permissions that are applicable to FILESTREAM filegroups and containers also apply to FileTables, since the file data is stored as a FILESTREAM column in the FileTable.</span></span>  
  
 <span data-ttu-id="53611-176">**Sécurité FileTable et accès Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="53611-176">**FileTable Security and Transact-SQL Access**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="53611-177">L’accès aux données dans les FileTables est sécurisé de la même façon que dans toute autre table.</span><span class="sxs-lookup"><span data-stu-id="53611-177">access to data in FileTables is secured in the same way as any other table.</span></span> <span data-ttu-id="53611-178">Des contrôles de sécurité appropriés au niveau de la table et de la colonne sont effectués pour chaque opération qui accède aux données ou les modifie.</span><span class="sxs-lookup"><span data-stu-id="53611-178">Appropriate table and column-level security checks are done for every operation that accesses or changes the data.</span></span>  
  
 <span data-ttu-id="53611-179">**Sécurité FileTable et accès au système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="53611-179">**FileTable Security and File System Access**</span></span>  
 <span data-ttu-id="53611-180">Les API du système de fichiers nécessitent des autorisations [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appropriées sur la ligne entière dans le FileTable (c'est-à-dire au niveau de la table) pour ouvrir un descripteur à un fichier ou répertoire stocké dans le FileTable.</span><span class="sxs-lookup"><span data-stu-id="53611-180">File system APIs require appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions on the entire row in the FileTable (that is, table-level permission) to open a handle to a file or directory stored in the FileTable.</span></span> <span data-ttu-id="53611-181">Si l'utilisateur ne dispose pas de l'autorisation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appropriée sur une colonne du FileTable, l'accès au système de fichiers est alors refusé.</span><span class="sxs-lookup"><span data-stu-id="53611-181">If the user does not have the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission on any column in the FileTable, then file system access is denied.</span></span>  
  
##  <a name="backup-and-filetables"></a><a name="OtherBackup"></a> <span data-ttu-id="53611-182">Sauvegarde et FileTables</span><span class="sxs-lookup"><span data-stu-id="53611-182">Backup and FileTables</span></span>  
 <span data-ttu-id="53611-183">Lorsque vous utilisez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour sauvegarder un FileTable, les données FILESTREAM sont sauvegardées avec les données structurées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="53611-183">When you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to back up a FileTable, the FILESTREAM data is backed up with the structured data in the database.</span></span> <span data-ttu-id="53611-184">Si vous ne souhaitez pas sauvegarder les données FILESTREAM avec les données relationnelles, vous pouvez utiliser une sauvegarde partielle pour exclure les groupes de fichiers FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="53611-184">If you do not want to back up FILESTREAM data with relational data, you can use a partial backup to exclude FILESTREAM filegroups.</span></span>  
  
 <span data-ttu-id="53611-185">**Cohérence transactionnelle des sauvegardes de FileTable**</span><span class="sxs-lookup"><span data-stu-id="53611-185">**Transactional Consistency of FileTable Backups**</span></span>  
  
 <span data-ttu-id="53611-186">De nombreux outils et opérations d'administration (notamment la sauvegarde, la sauvegarde de fichier journal et la réplication transactionnelle) lisent les données cohérentes au niveau transactionnel en lisant les journaux des transactions.</span><span class="sxs-lookup"><span data-stu-id="53611-186">Many administrative tools and operations, (including backup, log backup, and transactional replication) read transactionally consistent data by reading the transaction logs.</span></span> <span data-ttu-id="53611-187">À ce stade, ils lisent toutes les données FILESTREAM mises à jour dans le cadre d'une transaction.</span><span class="sxs-lookup"><span data-stu-id="53611-187">At this time, they read any FILESTREAM data updated as part of a transaction.</span></span> <span data-ttu-id="53611-188">Si l'accès non transactionnel n'est pas activé au niveau de la base de données, ces outils et opérations fonctionnent avec une cohérence transactionnelle complète.</span><span class="sxs-lookup"><span data-stu-id="53611-188">When non-transactional access is not enabled at the database level, these tools and operations work with full transactional consistency.</span></span>  
  
 <span data-ttu-id="53611-189">Toutefois, lorsque l'accès non transactionnel complet est activé, un FileTable pourrait contenir des données mises à jour plus récemment (via une mise à jour non transactionnelle) que la transaction que l'outil ou le processus lit à partir du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="53611-189">However, when full non-transactional access is enabled, then a FileTable could contain data that was updated more recently (through a non-transactional update) than the transaction that the tool or process is reading from the transaction log.</span></span> <span data-ttu-id="53611-190">Cela signifie qu’une opération de restauration à un point précis dans le temps dans une transaction spécifique peut contenir des données FILESTREAM plus récentes que cette transaction.</span><span class="sxs-lookup"><span data-stu-id="53611-190">This means that a "point in time" restore operation to a specific transaction may contain FILESTREAM data that is more recent than that transaction.</span></span> <span data-ttu-id="53611-191">Il s'agit du comportement attendu lorsque des mises à jour non transactionnelles sont autorisées sur les FileTables.</span><span class="sxs-lookup"><span data-stu-id="53611-191">This is the expected behavior when non-transactional updates are allowed on FileTables.</span></span>  
  
##  <a name="sql-server-profiler-and-filetables"></a><a name="Monitor"></a> <span data-ttu-id="53611-192">SQL Server Profiler et FileTables</span><span class="sxs-lookup"><span data-stu-id="53611-192">SQL Server Profiler and FileTables</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="53611-193">Profiler peut capturer les opérations Windows File Open et File Close dans le résultat de trace pour les fichiers stockés dans un FileTable.</span><span class="sxs-lookup"><span data-stu-id="53611-193">Profiler can capture the Windows File Open and File Close operations in trace output for files that are stored in a FileTable.</span></span>  
  
##  <a name="auditing-and-filetables"></a><a name="OtherAuditing"></a> <span data-ttu-id="53611-194">Audit et FileTables</span><span class="sxs-lookup"><span data-stu-id="53611-194">Auditing and FileTables</span></span>  
 <span data-ttu-id="53611-195">Le FileTable peut faire l'objet d'un audit  comme n'importe quelle autre table.</span><span class="sxs-lookup"><span data-stu-id="53611-195">FileTable can be audited just like any other table.</span></span> <span data-ttu-id="53611-196">Cependant, les modèles d'accès Win32 ne sont pas des opérations basées sur des ensembles.</span><span class="sxs-lookup"><span data-stu-id="53611-196">Howerver, Win32 access patterns are not set based operations.</span></span> <span data-ttu-id="53611-197">Une action unique dans le système de fichiers se traduit par plusieurs opérations DML Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="53611-197">A single action in the file system translates into multiple Transact-SQL DML operations.</span></span> <span data-ttu-id="53611-198">Par exemple, l'ouverture d'un fichier dans Microsoft Word se traduit par plusieurs opérations d'ouverture/de fermeture/de création/d'attribution d'un nouveau nom/de suppression et des activités DML Transact-SQL correspondantes.</span><span class="sxs-lookup"><span data-stu-id="53611-198">For example, opening a file in Microsoft Word translates into multiple open/close/create/rename/delete operations and corresponding Transact-SQL DML activities.</span></span> <span data-ttu-id="53611-199">Cela provoque des enregistrements d'audit détaillés dans lesquels il est difficile de mettre en corrélation des enregistrements entre les actions de système de fichiers et les enregistrements d'audit de DML Transact-SQL correspondants.</span><span class="sxs-lookup"><span data-stu-id="53611-199">This results in verbose audit records where it is hard to correlate records between file system actions and corresponding Transact-SQL DML audit records.</span></span>  
  
##  <a name="dbcc-and-filetables"></a><a name="OtherDBCC"></a> <span data-ttu-id="53611-200">DBCC et FileTables</span><span class="sxs-lookup"><span data-stu-id="53611-200">DBCC and FileTables</span></span>  
 <span data-ttu-id="53611-201">Vous pouvez utiliser DBCC CHECKCONSTRAINTS pour valider les contraintes sur un FileTable qui inclut des contraintes définies par le système.</span><span class="sxs-lookup"><span data-stu-id="53611-201">You can use DBCC CHECKCONSTRAINTS to validate the constraints on a FileTable including system-defined constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53611-202">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="53611-202">See Also</span></span>  
 <span data-ttu-id="53611-203">[Compatibilité de FileTable avec d'autres fonctionnalités SQL Server](filetable-compatibility-with-other-sql-server-features.md) </span><span class="sxs-lookup"><span data-stu-id="53611-203">[FileTable Compatibility with Other SQL Server Features](filetable-compatibility-with-other-sql-server-features.md) </span></span>  
 [<span data-ttu-id="53611-204">DDL, fonctions, procédures stockées et vues FileTable</span><span class="sxs-lookup"><span data-stu-id="53611-204">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
