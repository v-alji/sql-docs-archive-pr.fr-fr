---
title: Désactiver les index et contraintes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.disableindexes.f1
helpviewer_keywords:
- disabled indexes [SQL Server], index operations
- nonclustered indexes [SQL Server], disabling
- disabled indexes [SQL Server], guidelines
- clustered indexes, disabling
- constraints [SQL Server], disabling
- disabled indexes [SQL Server], viewing
- FOREIGN KEY constraints, disabling
- statistical information [SQL Server], indexes
- index disabling [SQL Server]
- indexed views [SQL Server], disabled indexes
ms.assetid: 2198f1af-fa44-47e9-92df-f4fde322ba18
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 40f9de4108be4defeb2353a9e7835c289641a819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708284"
---
# <a name="disable-indexes-and-constraints"></a><span data-ttu-id="b1cd9-102">Désactiver les index et contraintes</span><span class="sxs-lookup"><span data-stu-id="b1cd9-102">Disable Indexes and Constraints</span></span>
  <span data-ttu-id="b1cd9-103">Cette rubrique explique comment désactiver un index ou des contraintes dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1cd9-103">This topic describes how to disable an index or constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b1cd9-104">La désactivation d'un index empêche l'accès des utilisateurs à celui-ci et, s'il s'agit d'un index cluster, aux données de la table sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-104">Disabling an index prevents user access to the index, and for clustered indexes to the underlying table data.</span></span> <span data-ttu-id="b1cd9-105">La définition de l'index reste présente dans les métadonnées et les statistiques sont conservées sur les index non cluster.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-105">The index definition remains in metadata, and index statistics are kept on nonclustered indexes.</span></span> <span data-ttu-id="b1cd9-106">La désactivation d'un index, qu'il soit non cluster ou cluster, sur une vue supprime physiquement les données de l'index.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-106">Disabling a nonclustered or clustered index on a view physically deletes the index data.</span></span> <span data-ttu-id="b1cd9-107">La désactivation d'un index cluster sur une table empêche l'accès aux données de celle-ci ; ces dernières existent toujours dans la table, mais les opérations de langage de manipulation de données (DML) ne peuvent pas les utiliser tant que l'index n'est pas supprimé ou reconstruit.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-107">Disabling a clustered index on a table prevents access to the data; the data still remains in the table, but is unavailable for data manipulation language (DML) operations until the index is dropped or rebuilt.</span></span>  
  
 <span data-ttu-id="b1cd9-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b1cd9-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b1cd9-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b1cd9-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b1cd9-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b1cd9-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b1cd9-112">**Pour désactiver un index, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-112">**To disable an index, using:**</span></span>  
  
     [<span data-ttu-id="b1cd9-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1cd9-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b1cd9-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1cd9-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b1cd9-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b1cd9-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b1cd9-116">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b1cd9-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b1cd9-117">L'index n'est pas géré pendant qu'il est désactivé.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-117">The index is not maintained while it is disabled.</span></span>  
  
-   <span data-ttu-id="b1cd9-118">L'optimiseur de requête ne tient pas compte de l'index désactivé lors de la création de plans d'exécution de requête.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-118">The query optimizer does not consider the disabled index when creating query execution plans.</span></span> <span data-ttu-id="b1cd9-119">En outre, les requêtes qui référencent l'index désactivé avec un indicateur de table échouent.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-119">Also, queries that reference the disabled index with a table hint fail.</span></span>  
  
-   <span data-ttu-id="b1cd9-120">Vous ne pouvez pas créer un index qui utilise le même nom qu'un index désactivé existant.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-120">You cannot create an index that uses the same name as an existing disabled index.</span></span>  
  
-   <span data-ttu-id="b1cd9-121">Un index désactivé peut être supprimé.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-121">A disabled index can be dropped.</span></span>  
  
-   <span data-ttu-id="b1cd9-122">Lorsque vous désactivez un index unique, la contrainte PRIMARY KEY ou UNIQUE et toutes les contraintes FOREIGN KEY qui référencent les colonnes indexées des autres tables sont également désactivées.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-122">When disabling a unique index, the PRIMARY KEY or UNIQUE constraint and all FOREIGN KEY constraints that reference the indexed columns from other tables are also disabled.</span></span> <span data-ttu-id="b1cd9-123">Lorsque vous désactivez un index cluster, toutes les contraintes FOREIGN KEY entrantes et sortantes sur la table sous-jacente sont également désactivées.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-123">When disabling a clustered index, all incoming and outgoing FOREIGN KEY constraints on the underlying table are also disabled.</span></span> <span data-ttu-id="b1cd9-124">Les noms des contraintes sont répertoriés dans un message d'avertissement lorsque l'index est désactivé.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-124">The constraint names are listed in a warning message when the index is disabled.</span></span> <span data-ttu-id="b1cd9-125">Une fois l'index reconstruit, toutes les contraintes doivent être activées manuellement à l'aide de l'instruction ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-125">After rebuilding the index, all constraints must be manually enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="b1cd9-126">Les index non-cluster sont automatiquement désactivés lorsque l'index cluster associé est désactivé.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-126">Nonclustered indexes are automatically disabled when the associated clustered index is disabled.</span></span> <span data-ttu-id="b1cd9-127">Ils demeurent désactivés tant que l'index cluster de la table ou de la vue n'est pas activé ou que l'index cluster de la table n'est pas supprimé.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-127">They cannot be enabled until either the clustered index on the table or view is enabled or the clustered index on the table is dropped.</span></span> <span data-ttu-id="b1cd9-128">Les index non-cluster doivent être explicitement activés, sauf si l'index cluster a été activé à l'aide de l'instruction ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-128">Nonclustered indexes must be explicitly enabled, unless the clustered index was enabled by using the ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="b1cd9-129">L'instruction ALTER INDEX ALL REBUILD recrée et active tous les index désactivés sur la table, sauf les index désactivés sur des vues.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-129">The ALTER INDEX ALL REBUILD statement rebuilds and enables all disabled indexes on the table, except for disabled indexes on views.</span></span> <span data-ttu-id="b1cd9-130">Les index sur des vues doivent être activés dans une instruction ALTER INDEX ALL REBUILD distincte.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-130">Indexes on views must be enabled in a separate ALTER INDEX ALL REBUILD statement.</span></span>  
  
-   <span data-ttu-id="b1cd9-131">La désactivation d'un index cluster sur une table désactive également tous les index cluster et non cluster sur les vues qui font référence à cette table.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-131">Disabling a clustered index on a table also disables all clustered and nonclustered indexes on views that reference that table.</span></span> <span data-ttu-id="b1cd9-132">Ces index doivent être recréés comme ceux appartenant à la table référencée.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-132">These indexes must be rebuilt just as those on the referenced table.</span></span>  
  
-   <span data-ttu-id="b1cd9-133">Les lignes de données de l'index cluster désactivé ne sont accessibles que pour supprimer ou reconstruire cet index.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-133">The data rows of the disabled clustered index cannot be accessed except to drop or rebuild the clustered index.</span></span>  
  
-   <span data-ttu-id="b1cd9-134">Vous pouvez reconstruire un index non cluster désactivé en ligne lorsque la table ne possède pas d'index cluster désactivé.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-134">You can rebuild a disabled nonclustered index online when the table does not have a disabled clustered index.</span></span> <span data-ttu-id="b1cd9-135">Toutefois, vous devez toujours reconstruire un index cluster désactivé hors ligne si vous utilisez l'instruction ALTER INDEX REBUILD ou CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-135">However, you must always rebuild a disabled clustered index offline if you use either the ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING statement.</span></span> <span data-ttu-id="b1cd9-136">Pour plus d’informations sur les opérations en ligne sur les index, consultez [Exécuter des opérations en ligne sur les index](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="b1cd9-136">For more information about online index operations, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="b1cd9-137">L'instruction CREATE STATISTICS ne peut pas être correctement exécutée sur une table qui possède un index cluster désactivé.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-137">The CREATE STATISTICS statement cannot be successfully executed on a table that has a disabled clustered index.</span></span>  
  
-   <span data-ttu-id="b1cd9-138">L'option de base de données AUTO_CREATE_STATISTICS crée de nouvelles statistiques sur une colonne lorsque l'index est désactivé et que les conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="b1cd9-138">The AUTO_CREATE_STATISTICS database option creates new statistics on a column when the index is disabled and the following conditions exist:</span></span>  
  
    -   <span data-ttu-id="b1cd9-139">AUTO_CREATE_STATISTICS a pour valeur ON.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-139">AUTO_CREATE_STATISTICS is set to ON</span></span>  
  
    -   <span data-ttu-id="b1cd9-140">Il n'existe pas de statistiques sur la colonne.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-140">There are no existing statistics for the column.</span></span>  
  
    -   <span data-ttu-id="b1cd9-141">Des statistiques sont requises pendant l'optimisation de la requête.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-141">Statistics are required during query optimization.</span></span>  
  
-   <span data-ttu-id="b1cd9-142">Si un index cluster est désactivé, [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) ne peut pas retourner d'informations sur la table sous-jacente. À la place, l'instruction signale que l'index cluster est désactivé.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-142">If a clustered index is disabled, [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) cannot return information about the underlying table; instead, the statement reports that the clustered index is disabled.</span></span> <span data-ttu-id="b1cd9-143">[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) ne peut pas être utilisé pour défragmenter un index désactivé ; l'instruction échoue avec un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-143">[DBCC INDEXDEFRAG](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql) cannot be used to defragment a disabled index; the statement fails with an error message.</span></span> <span data-ttu-id="b1cd9-144">Utilisez l'instruction [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) pour recréer un index désactivé.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-144">You can use [DBCC DBREINDEX](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) to rebuild a disabled index.</span></span>  
  
-   <span data-ttu-id="b1cd9-145">La création d'un nouvel index cluster active les index non cluster précédemment désactivés.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-145">Creating a new clustered index enables previously disabled nonclustered indexes.</span></span> <span data-ttu-id="b1cd9-146">Pour plus d’informations, consultez [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="b1cd9-146">For more information, see [Enable Indexes and Constraints](enable-indexes-and-constraints.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b1cd9-147">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b1cd9-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b1cd9-148">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b1cd9-148">Permissions</span></span>  
 <span data-ttu-id="b1cd9-149">Pour pouvoir exécuter l'instruction ALTER INDEX, vous devez obligatoirement bénéficier au minimum d'autorisations nécessaires pour exécuter les instructions ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-149">To execute ALTER INDEX, at a minimum, ALTER permission on the table or view is required.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b1cd9-150">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1cd9-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="b1cd9-151">Pour désactiver un index</span><span class="sxs-lookup"><span data-stu-id="b1cd9-151">To disable an index</span></span>  
  
1.  <span data-ttu-id="b1cd9-152">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez désactiver un index.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable an index.</span></span>  
  
2.  <span data-ttu-id="b1cd9-153">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="b1cd9-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b1cd9-154">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez désactiver un index.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-154">Click the plus sign to expand the table on which you want to disable an index.</span></span>  
  
4.  <span data-ttu-id="b1cd9-155">Cliquez sur le signe plus (+) pour développer le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="b1cd9-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="b1cd9-156">Cliquez avec le bouton droit sur l’index que vous souhaitez désactiver et sélectionnez **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-156">Right-click the index you want to disable and select **Disable**.</span></span>  
  
6.  <span data-ttu-id="b1cd9-157">Dans la boîte de dialogue **Désactiver des index** , vérifiez que l'index correct figure dans la grille **Index à désactiver** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-157">In the **Disable Indexes** dialog box, verify that the correct index is in the **Indexes to disable** grid and click **OK**.</span></span>  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="b1cd9-158">Pour désactiver tous les index d'une table</span><span class="sxs-lookup"><span data-stu-id="b1cd9-158">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="b1cd9-159">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez désactiver les index.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-159">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to disable the indexes.</span></span>  
  
2.  <span data-ttu-id="b1cd9-160">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="b1cd9-160">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b1cd9-161">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez désactiver les index.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-161">Click the plus sign to expand the table on which you want to disable the indexes.</span></span>  
  
4.  <span data-ttu-id="b1cd9-162">Cliquez avec le bouton droit sur le dossier **Index** et sélectionnez **Désactiver tout**.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-162">Right-click the **Indexes** folder and select **Disable All**.</span></span>  
  
5.  <span data-ttu-id="b1cd9-163">Dans la boîte de dialogue **Désactiver des index** , vérifiez que les index corrects figurent dans la grille **Index à désactiver** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-163">In the **Disable Indexes** dialog box, verify that the correct indexes are in the **Indexes to disable** grid and click **OK**.</span></span> <span data-ttu-id="b1cd9-164">Pour supprimer un index de la grille **Index à désactiver** , sélectionnez-le et appuyez sur la touche SUPPR.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-164">To remove an index from the **Indexes to disable** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="b1cd9-165">Les informations suivantes sont disponibles dans la boîte de dialogue **Désactiver des index** :</span><span class="sxs-lookup"><span data-stu-id="b1cd9-165">The following information is available in the **Disable Indexes** dialog box:</span></span>  
  
 <span data-ttu-id="b1cd9-166">**Nom de l'index**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-166">**Index Name**</span></span>  
 <span data-ttu-id="b1cd9-167">Affiche le nom de l'index.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-167">Displays the name of the index.</span></span> <span data-ttu-id="b1cd9-168">Durant l'exécution, cette colonne comporte également une icône pour indiquer l'état.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-168">During execution, this column also displays an icon representing the status.</span></span>  
  
 <span data-ttu-id="b1cd9-169">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-169">**Table Name**</span></span>  
 <span data-ttu-id="b1cd9-170">Affiche le nom de la table ou de la vue sur laquelle l'index a été créé.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-170">Displays the name of the table or view that the index was created on.</span></span>  
  
 <span data-ttu-id="b1cd9-171">**Type d'index**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-171">**Index Type**</span></span>  
 <span data-ttu-id="b1cd9-172">Affiche le type d’index : **Cluster**, **Non-cluster**, **Spatial**ou **XML**.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-172">Displays the type of the index: **Clustered**, **Nonclustered**, **Spatial**, or **XML**.</span></span>  
  
 <span data-ttu-id="b1cd9-173">**État**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-173">**Status**</span></span>  
 <span data-ttu-id="b1cd9-174">Affiche l'état de l'opération de désactivation.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-174">Displays the status of the disable operation.</span></span> <span data-ttu-id="b1cd9-175">Les valeurs possibles après l'exécution sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="b1cd9-175">Possible values after execution are:</span></span>  
  
-   <span data-ttu-id="b1cd9-176">Vide</span><span class="sxs-lookup"><span data-stu-id="b1cd9-176">Blank</span></span>  
  
     <span data-ttu-id="b1cd9-177">Avant l'exécution, la valeur d' **État** est vide.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-177">Prior to execution **Status** is blank.</span></span>  
  
-   <span data-ttu-id="b1cd9-178">**En cours**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-178">**In progress**</span></span>  
  
     <span data-ttu-id="b1cd9-179">La désactivation d'index a débuté mais elle n'est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-179">Disabling of the indexes has been started but is not complete.</span></span>  
  
-   <span data-ttu-id="b1cd9-180">**Success**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-180">**Success**</span></span>  
  
     <span data-ttu-id="b1cd9-181">L'opération de désactivation est achevée.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-181">The disable operation completed successfully.</span></span>  
  
-   <span data-ttu-id="b1cd9-182">**Error**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-182">**Error**</span></span>  
  
     <span data-ttu-id="b1cd9-183">Une erreur est survenue pendant la désactivation d'index et celle-ci n'a pas pu être accomplie.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-183">An error was encountered during the index disable operation, and the operation did not complete successfully.</span></span>  
  
-   <span data-ttu-id="b1cd9-184">**Arrêté**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-184">**Stopped**</span></span>  
  
     <span data-ttu-id="b1cd9-185">La désactivation d'index n'a pas été accomplie parce que l'utilisateur a interrompu l'opération.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-185">The disable of the index was not completed successfully because the user stopped the operation.</span></span>  
  
 <span data-ttu-id="b1cd9-186">**Message**</span><span class="sxs-lookup"><span data-stu-id="b1cd9-186">**Message**</span></span>  
 <span data-ttu-id="b1cd9-187">Test des messages d'erreur survenant durant la désactivation.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-187">Provides the text of error messages during the disable operation.</span></span> <span data-ttu-id="b1cd9-188">Pendant l'exécution, les erreurs sont affichées comme des liens hypertexte.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-188">During execution, errors appear as hyperlinks.</span></span> <span data-ttu-id="b1cd9-189">Le corps du message d'erreur est indiqué dans le lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-189">The text of the hyperlinks describes the body of the error.</span></span> <span data-ttu-id="b1cd9-190">La colonne **Message** est souvent trop étroite pour que la totalité du message soit visible.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-190">The **Message** column is rarely wide enough to read the full message text.</span></span> <span data-ttu-id="b1cd9-191">Deux solutions sont possibles pour afficher l'intégralité du texte :</span><span class="sxs-lookup"><span data-stu-id="b1cd9-191">There are two ways to get the full text:</span></span>  
  
-   <span data-ttu-id="b1cd9-192">Déplacez le pointeur de la souris sur la cellule du message pour afficher une info-bulle contenant le texte de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-192">Move the mouse pointer over the message cell to display a ToolTip with the error text.</span></span>  
  
-   <span data-ttu-id="b1cd9-193">Cliquez sur le lien hypertexte pour afficher une boîte de dialogue indiquant le message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-193">Click the hyperlink to display a dialog box displaying the full error.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b1cd9-194">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1cd9-194">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-an-index"></a><span data-ttu-id="b1cd9-195">Pour désactiver un index</span><span class="sxs-lookup"><span data-stu-id="b1cd9-195">To disable an index</span></span>  
  
1.  <span data-ttu-id="b1cd9-196">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1cd9-196">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b1cd9-197">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-197">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b1cd9-198">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-198">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- disables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    DISABLE;  
    ```  
  
#### <a name="to-disable-all-indexes-on-a-table"></a><span data-ttu-id="b1cd9-199">Pour désactiver tous les index d'une table</span><span class="sxs-lookup"><span data-stu-id="b1cd9-199">To disable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="b1cd9-200">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1cd9-200">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b1cd9-201">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-201">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b1cd9-202">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b1cd9-202">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Disables all indexes on the HumanResources.Employee table.  
    ALTER INDEX ALL ON HumanResources.Employee  
    DISABLE;  
    ```  
  
 <span data-ttu-id="b1cd9-203">Pour plus d’informations, consultez [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1cd9-203">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
