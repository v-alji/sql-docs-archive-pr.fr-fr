---
title: Créer des index cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], clustered indexes
- clustered indexes, creating
- clustered indexes, PRIMARY KEY constraint
- clustered indexes, UNIQUE constraint
- indexes [SQL Server], clustered
ms.assetid: 47148383-c2c7-4f08-a9e4-7016bf2d1d13
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 567ff9a01bd93323149168b9e3aa0f34d78aee39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604447"
---
# <a name="create-clustered-indexes"></a><span data-ttu-id="c1281-102">Créer des index cluster</span><span class="sxs-lookup"><span data-stu-id="c1281-102">Create Clustered Indexes</span></span>
  <span data-ttu-id="c1281-103">Vous pouvez créer des index cluster sur les tables dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1281-103">You can create clustered indexes on tables in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c1281-104">À quelques exceptions près, chaque table doit posséder un index cluster.</span><span class="sxs-lookup"><span data-stu-id="c1281-104">With few exceptions, every table should have a clustered index.</span></span> <span data-ttu-id="c1281-105">Outre le fait qu'il améliore les performances des requêtes, un index cluster peut être reconstruit ou réorganisé à la demande pour contrôler la fragmentation de la table.</span><span class="sxs-lookup"><span data-stu-id="c1281-105">Besides improving query performance, a clustered index can be rebuilt or reorganized on demand to control table fragmentation.</span></span> <span data-ttu-id="c1281-106">Un index cluster peut également être créé sur une vue.</span><span class="sxs-lookup"><span data-stu-id="c1281-106">A clustered index can also be created on a view.</span></span> <span data-ttu-id="c1281-107">(Les index cluster sont définis dans la rubrique [Description des index cluster et non-cluster](clustered-and-nonclustered-indexes-described.md).)</span><span class="sxs-lookup"><span data-stu-id="c1281-107">(Clustered indexes are defined in the topic [Clustered and Nonclustered Indexes Described](clustered-and-nonclustered-indexes-described.md).)</span></span>  
  
 <span data-ttu-id="c1281-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c1281-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c1281-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c1281-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c1281-110">Implémentations types</span><span class="sxs-lookup"><span data-stu-id="c1281-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="c1281-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c1281-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c1281-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c1281-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c1281-113">**Pour créer un index cluster sur une table à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="c1281-113">**To create a clustered index on a table, using:**</span></span>  
  
     [<span data-ttu-id="c1281-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1281-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c1281-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1281-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c1281-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c1281-116">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="c1281-117">Implémentations types</span><span class="sxs-lookup"><span data-stu-id="c1281-117">Typical Implementations</span></span>  
 <span data-ttu-id="c1281-118">Les index cluster sont implémentés des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1281-118">Clustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="c1281-119">**Contraintes PRIMARY KEY et UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="c1281-119">**PRIMARY KEY and UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="c1281-120">La création d'une contrainte PRIMARY KEY entraîne la création automatique d'un index cluster unique sur la ou les colonnes pour autant qu'il n'existe pas encore d'index cluster dans la table ou qu'un index non-cluster unique n'ait pas été défini explicitement.</span><span class="sxs-lookup"><span data-stu-id="c1281-120">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="c1281-121">La colonne clé primaire ne peut pas contenir de valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="c1281-121">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="c1281-122">Lorsque vous créez une contrainte UNIQUE, un index non-cluster unique est créé pour appliquer par défaut une contrainte UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="c1281-122">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="c1281-123">Vous pouvez spécifier un index cluster unique si aucun index cluster n'existe déjà sur la table.</span><span class="sxs-lookup"><span data-stu-id="c1281-123">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="c1281-124">Un index créé dans le cadre de la contrainte reçoit automatiquement le nom de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="c1281-124">An index created as part of the constraint is automatically given the same name as the constraint name.</span></span> <span data-ttu-id="c1281-125">Pour plus d'informations, consultez [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) et [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="c1281-125">For more information, see [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md) and [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="c1281-126">**Index indépendant d'une contrainte**</span><span class="sxs-lookup"><span data-stu-id="c1281-126">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="c1281-127">Vous pouvez créer un index cluster sur une autre colonne que la colonne clé primaire si une contrainte de clé primaire non-cluster a été spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c1281-127">You can create a clustered index on a column other than primary key column if a nonclustered primary key constraint was specified.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c1281-128">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="c1281-128">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c1281-129">Lorsqu'une structure d'index cluster est créée, l'ancienne structure (source) et la nouvelle structure (cible) requièrent de l'espace disque dans leurs fichiers et groupes de fichiers respectifs.</span><span class="sxs-lookup"><span data-stu-id="c1281-129">When a clustered index structure is created, disk space for both the old (source) and new (target) structures is required in their respective files and filegroups.</span></span> <span data-ttu-id="c1281-130">L'ancienne structure n'est désallouée qu'une fois l'ensemble de la transaction validé.</span><span class="sxs-lookup"><span data-stu-id="c1281-130">The old structure is not deallocated until the complete transaction commits.</span></span> <span data-ttu-id="c1281-131">Il est également possible qu'une opération de tri nécessite de l'espace disque temporaire supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c1281-131">Additional temporary disk space for sorting may also be required.</span></span> <span data-ttu-id="c1281-132">Pour plus d’informations, consultez [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c1281-132">For more information, see [Disk Space Requirements for Index DDL Operations](disk-space-requirements-for-index-ddl-operations.md).</span></span>  
  
-   <span data-ttu-id="c1281-133">Si un index cluster est créé sur un segment comprenant plusieurs index non-cluster, ces derniers doivent tous être reconstruits afin qu'ils contiennent la valeur de clé de clustering au lieu de l'identificateur de ligne (RID).</span><span class="sxs-lookup"><span data-stu-id="c1281-133">If a clustered index is created on a heap with several existing nonclustered indexes, all the nonclustered indexes must be rebuilt so that they contain the clustering key value instead of the row identifier (RID).</span></span> <span data-ttu-id="c1281-134">De même, si un index cluster est supprimé d'une table comprenant plusieurs index non-cluster, ces derniers sont tous regénérés pendant l'opération de suppression (DROP).</span><span class="sxs-lookup"><span data-stu-id="c1281-134">Similarly, if a clustered index is dropped on a table that has several nonclustered indexes, the nonclustered indexes are all rebuilt as part of the DROP operation.</span></span> <span data-ttu-id="c1281-135">Cette opération peut prendre beaucoup de temps sur les tables volumineuses.</span><span class="sxs-lookup"><span data-stu-id="c1281-135">This may take significant time on large tables.</span></span>  
  
     <span data-ttu-id="c1281-136">Il est préférable de construire des index sur des tables volumineuses en commençant par l'index cluster, puis de poursuivre avec les index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="c1281-136">The preferred way to build indexes on large tables is to start with the clustered index and then build any nonclustered indexes.</span></span> <span data-ttu-id="c1281-137">Pensez à attribuer la valeur ON à l'option ONLINE lorsque vous créez des index sur des tables existantes.</span><span class="sxs-lookup"><span data-stu-id="c1281-137">Consider setting the ONLINE option to ON when you create indexes on existing tables.</span></span> <span data-ttu-id="c1281-138">Lorsque cette option a pour valeur ON, les verrous de table à long terme ne sont pas maintenus.</span><span class="sxs-lookup"><span data-stu-id="c1281-138">When set to ON, long-term table locks are not held.</span></span> <span data-ttu-id="c1281-139">Ce paramétrage permet de poursuivre les interrogations ou les mises à jour de la table sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="c1281-139">This enables queries or updates to the underlying table to continue.</span></span> <span data-ttu-id="c1281-140">Pour plus d'informations, consultez [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="c1281-140">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
-   <span data-ttu-id="c1281-141">La clé d'un index cluster ne peut pas contenir de colonnes `varchar` qui possèdent des données dans l'unité d'allocation ROW_OVERFLOW_DATA.</span><span class="sxs-lookup"><span data-stu-id="c1281-141">The index key of a clustered index cannot contain `varchar` columns that have existing data in the ROW_OVERFLOW_DATA allocation unit.</span></span> <span data-ttu-id="c1281-142">Si un index cluster est créé sur une colonne `varchar` et que les données existantes se trouvent dans l'unité d'allocation IN_ROW_DATA, les actions d'insertion ou de mise à jour réalisées ultérieurement sur la colonne et susceptibles d'envoyer les données hors ligne sont vouées à l'échec.</span><span class="sxs-lookup"><span data-stu-id="c1281-142">If a clustered index is created on a `varchar` column and the existing data is in the IN_ROW_DATA allocation unit, subsequent insert or update actions on the column that would push the data off-row will fail.</span></span> <span data-ttu-id="c1281-143">Pour obtenir des informations sur les tables pouvant contenir des données de dépassement de ligne, utilisez la fonction de gestion dynamique [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c1281-143">To obtain information about tables that might contain row-overflow data, use the [sys.dm_db_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-physical-stats-transact-sql) dynamic management function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c1281-144">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c1281-144">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c1281-145">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c1281-145">Permissions</span></span>  
 <span data-ttu-id="c1281-146">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="c1281-146">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="c1281-147">L’utilisateur doit être membre du rôle serveur fixe **sysadmin** ou des rôles de base de données fixes **db_ddladmin** et **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="c1281-147">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c1281-148">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1281-148">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-object-explorer"></a><span data-ttu-id="c1281-149">Pour créer un index cluster à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="c1281-149">To create a clustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="c1281-150">Dans l'Explorateur d'objets, développez la table sur laquelle vous souhaitez créer un index cluster.</span><span class="sxs-lookup"><span data-stu-id="c1281-150">In Object Explorer, expand the table on which you want to create a clustered index.</span></span>  
  
2.  <span data-ttu-id="c1281-151">Cliquez avec le bouton droit sur le dossier **Index**, pointez sur **Nouvel index**, puis sélectionnez **Index cluster...** .</span><span class="sxs-lookup"><span data-stu-id="c1281-151">Right-click the **Indexes** folder, point to **New Index**, and select **Clustered Index...**.</span></span>  
  
3.  <span data-ttu-id="c1281-152">Dans la boîte de dialogue **Nouvel index** , sur la page **Général** , entrez le nom du nouvel index dans la zone **Nom de l'index** .</span><span class="sxs-lookup"><span data-stu-id="c1281-152">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
4.  <span data-ttu-id="c1281-153">Sous **Colonnes clés d’index**, cliquez sur **Ajouter…** .</span><span class="sxs-lookup"><span data-stu-id="c1281-153">Under **Index key columns**, click **Add...**.</span></span>  
  
5.  <span data-ttu-id="c1281-154">Dans la boîte de dialogue **Sélectionner les colonnes à partir de**_table_name_ , activez la case à cocher de la colonne de table à ajouter à l’index cluster.</span><span class="sxs-lookup"><span data-stu-id="c1281-154">In the **Select Columns from**_table_name_ dialog box, select the check box of the table column to be added to the clustered index.</span></span>  
  
6.  <span data-ttu-id="c1281-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1281-155">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="c1281-156">Dans la boîte de dialogue **Nouvel index** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1281-156">In the **New Index** dialog box, click **OK**.</span></span>  
  
#### <a name="to-create-a-clustered-index-by-using-the-table-designer"></a><span data-ttu-id="c1281-157">Pour créer un index cluster à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="c1281-157">To create a clustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="c1281-158">Dans l'Explorateur d'objets, développez la base de données sur laquelle vous souhaitez créer une table avec un index cluster.</span><span class="sxs-lookup"><span data-stu-id="c1281-158">In Object Explorer, expand the database on which you want to create a table with a clustered index.</span></span>  
  
2.  <span data-ttu-id="c1281-159">Cliquez avec le bouton droit sur le dossier **Tables** et sélectionnez **Nouvelle table...** .</span><span class="sxs-lookup"><span data-stu-id="c1281-159">Right-click the **Tables** folder and click **New Table...**.</span></span>  
  
3.  <span data-ttu-id="c1281-160">Créez une table comme vous le feriez normalement.</span><span class="sxs-lookup"><span data-stu-id="c1281-160">Create a new table as you normally would.</span></span> <span data-ttu-id="c1281-161">Pour plus d’informations, consultez [Créer des tables &#40;moteur de base de données&#41;](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="c1281-161">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span>  
  
4.  <span data-ttu-id="c1281-162">Cliquez avec le bouton droit sur la nouvelle table créée ci-dessus, puis sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="c1281-162">Right-click the new table created above and click **Design**.</span></span>  
  
5.  <span data-ttu-id="c1281-163">Dans le menu **Concepteur de tables** , cliquez sur **Index/Clés**.</span><span class="sxs-lookup"><span data-stu-id="c1281-163">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
6.  <span data-ttu-id="c1281-164">Dans la boîte de dialogue **Index/Clés** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c1281-164">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
7.  <span data-ttu-id="c1281-165">Sélectionnez le nouvel index dans la zone de texte **Clé ou index Primary/Unique sélectionné** .</span><span class="sxs-lookup"><span data-stu-id="c1281-165">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
8.  <span data-ttu-id="c1281-166">Dans la grille, sélectionnez **Créer comme Clustered**et choisissez **Oui** dans la liste déroulante à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="c1281-166">In the grid, select **Create as Clustered**, and choose **Yes** from the drop-down list to the right of the property.</span></span>  
  
9. <span data-ttu-id="c1281-167">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="c1281-167">Click **Close**.</span></span>  
  
10. <span data-ttu-id="c1281-168">Dans le menu **Fichier** , cliquez sur **Enregistrer**_nom_table_.</span><span class="sxs-lookup"><span data-stu-id="c1281-168">On the **File** menu, click **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c1281-169">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1281-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-clustered-index"></a><span data-ttu-id="c1281-170">Pour créer un index cluster</span><span class="sxs-lookup"><span data-stu-id="c1281-170">To create a clustered index</span></span>  
  
1.  <span data-ttu-id="c1281-171">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1281-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c1281-172">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c1281-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c1281-173">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c1281-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Create a new table with three columns.  
    CREATE TABLE dbo.TestTable  
        (TestCol1 int NOT NULL,  
         TestCol2 nchar(10) NULL,  
         TestCol3 nvarchar(50) NULL);  
    GO  
    -- Create a clustered index called IX_TestTable_TestCol1  
    -- on the dbo.TestTable table using the TestCol1 column.  
    CREATE CLUSTERED INDEX IX_TestTable_TestCol1   
        ON dbo.TestTable (TestCol1);   
    GO  
    ```  
  
 <span data-ttu-id="c1281-174">Pour plus d’informations, consultez [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c1281-174">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1281-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1281-175">See Also</span></span>  
 <span data-ttu-id="c1281-176">[Créer des clés primaires](../tables/create-primary-keys.md) </span><span class="sxs-lookup"><span data-stu-id="c1281-176">[Create Primary Keys](../tables/create-primary-keys.md) </span></span>  
 [<span data-ttu-id="c1281-177">Créer des contraintes uniques</span><span class="sxs-lookup"><span data-stu-id="c1281-177">Create Unique Constraints</span></span>](../tables/create-unique-constraints.md)  
  
  
