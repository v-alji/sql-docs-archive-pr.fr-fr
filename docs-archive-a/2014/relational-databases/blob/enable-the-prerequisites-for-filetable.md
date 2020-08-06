---
title: Activer les conditions préalables pour les FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], prerequisites
ms.assetid: 6286468c-9dc9-4eda-9961-071d2a36ebd6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5d5d2c5dab7909ec5403911d482823f488cdd809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600095"
---
# <a name="enable-the-prerequisites-for-filetable"></a><span data-ttu-id="ab26b-102">Activer les conditions préalables pour les FileTables</span><span class="sxs-lookup"><span data-stu-id="ab26b-102">Enable the Prerequisites for FileTable</span></span>
  <span data-ttu-id="ab26b-103">Décrit la manière de satisfaire aux conditions préalables en vue de la création et de l'utilisation de FileTables.</span><span class="sxs-lookup"><span data-stu-id="ab26b-103">Describes how to enable the prerequisites for creating and using FileTables.</span></span>  
  
##  <a name="enabling-the-prerequisites-for-filetable"></a><a name="EnablePrereq"></a> <span data-ttu-id="ab26b-104">Activation des conditions préalables pour les FileTables</span><span class="sxs-lookup"><span data-stu-id="ab26b-104">Enabling the Prerequisites for FileTable</span></span>  
 <span data-ttu-id="ab26b-105">Pour activer les conditions préalables en vue de créer et d'utiliser les FileTables, activez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ab26b-105">To enable the prerequisites for creating and using FileTables, enable the following items:</span></span>  
  
-   <span data-ttu-id="ab26b-106">**Au niveau de l'instance :**</span><span class="sxs-lookup"><span data-stu-id="ab26b-106">**At the instance level:**</span></span>  
  
    -   [<span data-ttu-id="ab26b-107">Activation de FILESTREAM au niveau de l'instance</span><span class="sxs-lookup"><span data-stu-id="ab26b-107">Enabling FILESTREAM at the Instance Level</span></span>](#BasicsFilestream)  
  
-   <span data-ttu-id="ab26b-108">**Au niveau de la base de données :**</span><span class="sxs-lookup"><span data-stu-id="ab26b-108">**At the database level:**</span></span>  
  
    -   [<span data-ttu-id="ab26b-109">Fournir un groupe de fichiers FILESTREAM au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="ab26b-109">Providing a FILESTREAM Filegroup at the Database Level</span></span>](#filegroup)  
  
    -   [<span data-ttu-id="ab26b-110">Activation de l'accès non transactionnel au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="ab26b-110">Enabling Non-Transactional Access at the Database Level</span></span>](#BasicsNTAccess)  
  
    -   [<span data-ttu-id="ab26b-111">Spécification d'un répertoire pour les FileTables au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="ab26b-111">Specifying a Directory for FileTables at the Database Level</span></span>](#BasicsDirectory)  
  
##  <a name="enabling-filestream-at-the-instance-level"></a><a name="BasicsFilestream"></a> <span data-ttu-id="ab26b-112">Activation de FILESTREAM au niveau de l'instance</span><span class="sxs-lookup"><span data-stu-id="ab26b-112">Enabling FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="ab26b-113">Les FileTables étendent les fonctionnalités FILESTREAM de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab26b-113">FileTables extend the capabilities of the FILESTREAM feature of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ab26b-114">Par conséquent, vous devez activer FILESTREAM pour l'accès d'E/S de fichier au niveau de Windows et sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avant de pouvoir créer et utiliser des FileTables.</span><span class="sxs-lookup"><span data-stu-id="ab26b-114">Therefore you have to enable FILESTREAM for file I/O access at the Windows level and on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you can create and use FileTables.</span></span>  
  
###  <a name="how-to-enable-filestream-at-the-instance-level"></a><a name="HowToFilestream"></a> <span data-ttu-id="ab26b-115">Procédure : activer FILESTREAM au niveau de l’instance</span><span class="sxs-lookup"><span data-stu-id="ab26b-115">How To: Enable FILESTREAM at the Instance Level</span></span>  
 <span data-ttu-id="ab26b-116">Pour plus d’informations sur l’activation de FILESTREAM, consultez [Activer et configurer FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="ab26b-116">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
 <span data-ttu-id="ab26b-117">Lorsque vous appelez `sp_configure` pour activer FILESTREAM au niveau de l'instance, vous devez définir l'option filestream_access_level sur 2.</span><span class="sxs-lookup"><span data-stu-id="ab26b-117">When you call `sp_configure` to enable FILESTREAM at the instance level, you have to set the filestream_access_level option to 2.</span></span> <span data-ttu-id="ab26b-118">Pour plus d’informations, consultez [Niveau d’accès du flux de fichier (option de configuration de serveur)](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ab26b-118">For more information, see [filestream access level Server Configuration Option](../../database-engine/configure-windows/filestream-access-level-server-configuration-option.md).</span></span>  
  
###  <a name="how-to-allow-filestream-through-the-firewall"></a><a name="firewall"></a> <span data-ttu-id="ab26b-119">Procédure : activer FILESTREAM via le pare-feu</span><span class="sxs-lookup"><span data-stu-id="ab26b-119">How To: Allow FILESTREAM through the Firewall</span></span>  
 <span data-ttu-id="ab26b-120">Pour plus d'informations sur l'activation de FILESTREAM via le pare-feu, consultez [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span><span class="sxs-lookup"><span data-stu-id="ab26b-120">For information about how to allow FILESTREAM through the firewall, see [Configure a Firewall for FILESTREAM Access](configure-a-firewall-for-filestream-access.md).</span></span>  
  
##  <a name="providing-a-filestream-filegroup-at-the-database-level"></a><a name="filegroup"></a> <span data-ttu-id="ab26b-121">Fournir un groupe de fichiers FILESTREAM au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="ab26b-121">Providing a FILESTREAM Filegroup at the Database Level</span></span>  
 <span data-ttu-id="ab26b-122">Avant de pouvoir créer des FileTables dans une base de données, cette dernière doit avoir un groupe de fichiers FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="ab26b-122">Before you can create FileTables in a database, the database must have a FILESTREAM filegroup.</span></span> <span data-ttu-id="ab26b-123">Pour plus d’informations sur cette condition préalable, consultez [Créer une base de données compatible FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="ab26b-123">For more information about this prerequisite, see [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
##  <a name="enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsNTAccess"></a> <span data-ttu-id="ab26b-124">Activation de l'accès non transactionnel au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="ab26b-124">Enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="ab26b-125">Les FileTables permettent aux applications Windows d'obtenir un descripteur de fichier Windows aux données FILESTREAM sans requérir de transaction.</span><span class="sxs-lookup"><span data-stu-id="ab26b-125">FileTables let Windows applications obtain a Windows file handle to FILESTREAM data without requiring a transaction.</span></span> <span data-ttu-id="ab26b-126">Pour autoriser cet accès non transactionnel aux fichiers stockés dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous devez spécifier le niveau désiré d'accès non transactionnel au niveau de la base de données pour chaque base de données qui contiendra des FileTables.</span><span class="sxs-lookup"><span data-stu-id="ab26b-126">To allow this non-transactional access to files stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you have to specify the desired level of non-transactional access at the database level for each database that will contain FileTables.</span></span>  
  
###  <a name="how-to-check-whether-non-transactional-access-is-enabled-on-databases"></a><a name="HowToCheckAccess"></a> <span data-ttu-id="ab26b-127">Procédure : vérifier si l’accès non transactionnel est activé sur les bases de données</span><span class="sxs-lookup"><span data-stu-id="ab26b-127">How To: Check Whether Non-Transactional Access Is Enabled on Databases</span></span>  
 <span data-ttu-id="ab26b-128">Interrogez l’affichage catalogue [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) et vérifiez les colonnes **non_transacted_access** et **non_transacted_access_desc**.</span><span class="sxs-lookup"><span data-stu-id="ab26b-128">Query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **non_transacted_access** and **non_transacted_access_desc** columns.</span></span>  
  
```sql  
SELECT DB_NAME(database_id), non_transacted_access, non_transacted_access_desc  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="how-to-enable-non-transactional-access-at-the-database-level"></a><a name="HowToNTAccess"></a> <span data-ttu-id="ab26b-129">Procédure : activer l’accès non transactionnel au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="ab26b-129">How To: Enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="ab26b-130">Les niveaux disponibles de l'accès non transactionnel sont FULL, READ_ONLY et OFF.</span><span class="sxs-lookup"><span data-stu-id="ab26b-130">The available levels of non-transactional access are FULL, READ_ONLY, and OFF.</span></span>  
  
 <span data-ttu-id="ab26b-131">**Spécifier le niveau d'accès non transactionnel à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ab26b-131">**Specify the level of non-transactional access by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="ab26b-132">Quand vous **créez une base de données**, appelez l’instruction [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) avec l’option FILESTREAM **NON_TRANSACTED_ACCESS**.</span><span class="sxs-lookup"><span data-stu-id="ab26b-132">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
-   <span data-ttu-id="ab26b-133">Quand vous **modifiez une base de données existante**, appelez l’instruction [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) avec l’option FILESTREAM **NON_TRANSACTED_ACCESS**.</span><span class="sxs-lookup"><span data-stu-id="ab26b-133">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **NON_TRANSACTED_ACCESS** FILESTREAM option.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' )  
    ```  
  
 <span data-ttu-id="ab26b-134">**Spécifier le niveau d'accès non transactionnel à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ab26b-134">**Specify the level of non-transactional access by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="ab26b-135">Vous pouvez spécifier le niveau d’accès non transactionnel dans le champ **Accès non transactionnel FILESTREAM** de la page **Options** de la boîte de dialogue **Propriétés de la base de données** .</span><span class="sxs-lookup"><span data-stu-id="ab26b-135">You can specify the level of non-transactional access in the **FILESTREAM Non-transacted Access** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="ab26b-136">Pour plus d’informations sur cette boîte de dialogue, consultez [Propriétés de la base de données &#40;page Options&#41;](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="ab26b-136">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
##  <a name="specifying-a-directory-for-filetables-at-the-database-level"></a><a name="BasicsDirectory"></a> <span data-ttu-id="ab26b-137">Spécification d'un répertoire pour les FileTables au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="ab26b-137">Specifying a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="ab26b-138">Lorsque vous activez l’accès non transactionnel aux fichiers au niveau de la base de données, vous pouvez éventuellement fournir en même temps un nom de répertoire à l’aide de l’option **DIRECTORY_NAME** .</span><span class="sxs-lookup"><span data-stu-id="ab26b-138">When you enable non-transactional access to files at the database level, you can optionally provide a directory name at the same time by using the **DIRECTORY_NAME** option.</span></span> <span data-ttu-id="ab26b-139">Si vous ne fournissez pas de nom de répertoire lorsque vous activez l'accès non transactionnel, vous devez le fournir ultérieurement avant de pouvoir créer des FileTables dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="ab26b-139">If you do not provide a directory name when you enable non-transactional access, then you have to provide it later before you can create FileTables in the database.</span></span>  
  
 <span data-ttu-id="ab26b-140">Dans l'arborescence du dossier FileTable, ce répertoire de base de données devient l'enfant du nom de partage spécifié pour FILESTREAM au niveau de l'instance, et le parent des FileTables créés dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="ab26b-140">In the FileTable folder hierarchy, this database-level directory becomes the child of the share name specified for FILESTREAM at the instance level, and the parent of the FileTables created in the database.</span></span> <span data-ttu-id="ab26b-141">Pour plus d'informations, consultez [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="ab26b-141">For more information, see [Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md).</span></span>  
  
###  <a name="how-to-specify-a-directory-for-filetables-at-the-database-level"></a><a name="HowToDirectory"></a> <span data-ttu-id="ab26b-142">Procédure : spécifier un répertoire pour les FileTables au niveau de la base de données</span><span class="sxs-lookup"><span data-stu-id="ab26b-142">How To: Specify a Directory for FileTables at the Database Level</span></span>  
 <span data-ttu-id="ab26b-143">Le nom que vous spécifiez doit être unique dans l'instance pour les répertoires de niveau base de données.</span><span class="sxs-lookup"><span data-stu-id="ab26b-143">The name that you specify must be unique across the instance for database-level directories.</span></span>  
  
 <span data-ttu-id="ab26b-144">**Spécifier un répertoire pour les FileTables à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ab26b-144">**Specify a directory for FileTables by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="ab26b-145">Quand vous **créez une base de données**, appelez l’instruction [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) avec l’option FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="ab26b-145">When you **create a new database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        WITH FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="ab26b-146">Quand vous **modifiez une base de données existante**, appelez l’instruction [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) avec l’option FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="ab26b-146">When you **alter an existing database**, call the [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span> <span data-ttu-id="ab26b-147">Lorsque vous utilisez ces options pour modifier le nom de répertoire, la base de données doit être verrouillée en mode exclusif, sans descripteurs de fichiers ouverts.</span><span class="sxs-lookup"><span data-stu-id="ab26b-147">When you use these options to change the directory name, the database must be exclusively locked, with no open file handles.</span></span>  
  
    ```sql  
    ALTER DATABASE database_name  
        SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL, DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="ab26b-148">Quand vous **attachez une base de données**, appelez l’instruction [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) avec l’option **FOR ATTACH** et l’option FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="ab26b-148">When you **attach a database**, call the [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the **FOR ATTACH** option and with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    CREATE DATABASE database_name  
        FOR ATTACH WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
-   <span data-ttu-id="ab26b-149">Quand vous **restaurez une base de données**, appelez l’instruction [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) avec l’option FILESTREAM **DIRECTORY_NAME**.</span><span class="sxs-lookup"><span data-stu-id="ab26b-149">When you **restore a database**, call the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement with the **DIRECTORY_NAME** FILESTREAM option.</span></span>  
  
    ```sql  
    RESTORE DATABASE database_name  
        WITH FILESTREAM ( DIRECTORY_NAME = N'directory_name' );  
    GO  
    ```  
  
 <span data-ttu-id="ab26b-150">**Spécifier un répertoire pour les FileTables à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ab26b-150">**Specify a directory for FileTables by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="ab26b-151">Vous pouvez spécifier un nom de répertoire dans le champ **Nom du répertoire FILESTREAM** de la page **Options** de la boîte de dialogue **Propriétés de la base de données** .</span><span class="sxs-lookup"><span data-stu-id="ab26b-151">You can specify a directory name in the **FILESTREAM Directory Name** field of the **Options** page of the **Database Properties** dialog box.</span></span> <span data-ttu-id="ab26b-152">Pour plus d’informations sur cette boîte de dialogue, consultez [Propriétés de la base de données &#40;page Options&#41;](../databases/database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="ab26b-152">For more information about this dialog box, see [Database Properties &#40;Options Page&#41;](../databases/database-properties-options-page.md).</span></span>  
  
###  <a name="how-to-view-existing-directory-names-for-the-instance"></a><a name="viewnames"></a> <span data-ttu-id="ab26b-153">Procédure : afficher les noms de répertoires existants pour l’instance</span><span class="sxs-lookup"><span data-stu-id="ab26b-153">How to: View Existing Directory Names for the Instance</span></span>  
 <span data-ttu-id="ab26b-154">Pour afficher la liste des noms de répertoire existant pour l’instance, interrogez l’affichage catalogue [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) et vérifiez la colonne **filestream_database_directory_name**.</span><span class="sxs-lookup"><span data-stu-id="ab26b-154">To view the list of existing directory names for the instance, query the catalog view [sys.database_filestream_options &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql) and check the **filestream_database_directory_name** column.</span></span>  
  
```sql  
SELECT DB_NAME ( database_id ), directory_name  
    FROM sys.database_filestream_options;  
GO  
```  
  
###  <a name="requirements-and-restrictions-for-the-database-level-directory"></a><a name="ReqDirectory"></a> <span data-ttu-id="ab26b-155">Exigences et restrictions pour le répertoire de niveau base de données</span><span class="sxs-lookup"><span data-stu-id="ab26b-155">Requirements and Restrictions for the Database-Level Directory</span></span>  
  
-   <span data-ttu-id="ab26b-156">La définition de **DIRECTORY_NAME** est facultative lorsque vous appelez **CREATE DATABASE** ou **ALTER DATABASE**.</span><span class="sxs-lookup"><span data-stu-id="ab26b-156">Setting the **DIRECTORY_NAME** is optional when you call **CREATE DATABASE** or **ALTER DATABASE**.</span></span> <span data-ttu-id="ab26b-157">Si vous ne spécifiez pas de valeur pour **DIRECTORY_NAME**, le nom de répertoire reste Null.</span><span class="sxs-lookup"><span data-stu-id="ab26b-157">If you do not specify a value for **DIRECTORY_NAME**, then the directory name remains null.</span></span> <span data-ttu-id="ab26b-158">Cependant, vous ne pouvez pas créer de FileTables dans la base de données tant que vous n’avez pas spécifié de valeur pour **DIRECTORY_NAME** au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ab26b-158">However you cannot create FileTables in the database until you specify a value for **DIRECTORY_NAME** at the database level.</span></span>  
  
-   <span data-ttu-id="ab26b-159">Le nom de répertoire que vous fournissez doit se conformer aux configurations requises du système de fichiers concernant les noms de répertoire valides.</span><span class="sxs-lookup"><span data-stu-id="ab26b-159">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
-   <span data-ttu-id="ab26b-160">Quand la base de données contient des FileTables, vous ne pouvez pas redéfinir **DIRECTORY_NAME** sur une valeur Null.</span><span class="sxs-lookup"><span data-stu-id="ab26b-160">When the database contains FileTables, you cannot set the **DIRECTORY_NAME** back to a null value.</span></span>  
  
-   <span data-ttu-id="ab26b-161">Lorsque vous attachez ou restaurez une base de données, l’opération échoue si la nouvelle base de données comporte une valeur pour **DIRECTORY_NAME** qui existe déjà dans l’instance cible.</span><span class="sxs-lookup"><span data-stu-id="ab26b-161">When you attach or restore a database, the operation fails if the new database has a value for **DIRECTORY_NAME** that already exists in the target instance.</span></span> <span data-ttu-id="ab26b-162">Spécifiez une valeur unique pour **DIRECTORY_NAME** lorsque vous appelez **CREATE DATABASE FOR ATTACH** ou **RESTORE DATABASE**.</span><span class="sxs-lookup"><span data-stu-id="ab26b-162">Specify a unique value for **DIRECTORY_NAME** when you call **CREATE DATABASE FOR ATTACH** or **RESTORE DATABASE**.</span></span>  
  
-   <span data-ttu-id="ab26b-163">Lorsque vous mettez à niveau une base de données existante avec [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], la valeur de **DIRECTORY_NAME** est Null.</span><span class="sxs-lookup"><span data-stu-id="ab26b-163">When you upgrade an existing database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the value of **DIRECTORY_NAME** is null.</span></span>  
  
-   <span data-ttu-id="ab26b-164">Lorsque vous activez ou désactivez l'accès non transactionnel au niveau de la base de données, l'opération ne vérifie pas si le nom de répertoire a été spécifié ou s'il est unique.</span><span class="sxs-lookup"><span data-stu-id="ab26b-164">When you enable or disable non-transactional access at the database level, the operation does not check whether the directory name has been specified or whether it is unique.</span></span>  
  
-   <span data-ttu-id="ab26b-165">Lorsque vous supprimez une base de données activée pour les FileTables, le répertoire de niveau base de données et toutes les structures de répertoires de tous les FileTables situés au niveau inférieur sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="ab26b-165">When you drop a database that was enabled for FileTables, the database-level directory and all the directory stuctures of all the FileTables under it are removed.</span></span>  
  
  
