---
title: Créer des index non cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index creation [SQL Server], nonclustered indexes
- nonclustered indexes [SQL Server], creating
- nonclustered indexes [SQL Server], UNIQUE constraint
- indexes [SQL Server], nonclustered
- nonclustered indexes [SQL Server], PRIMARY KEY constraint
ms.assetid: 9402029a-1227-46c4-93aa-c2122eb1b943
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fae0c06b1f562dc3fc518a319df1787b3384c0cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708296"
---
# <a name="create-nonclustered-indexes"></a><span data-ttu-id="7369a-102">Créer des index non cluster</span><span class="sxs-lookup"><span data-stu-id="7369a-102">Create Nonclustered Indexes</span></span>
  <span data-ttu-id="7369a-103">Vous pouvez créer des index non-cluster dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7369a-103">You can create nonclustered indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7369a-104">Un index non-cluster est une structure d'index séparé des données stockées dans une table qui réorganise une ou plusieurs colonnes sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="7369a-104">A nonclustered index is an index structure separate from the data stored in a table that reorders one or more selected columns.</span></span> <span data-ttu-id="7369a-105">Les index non-cluster peuvent vous aider à trouver plus rapidement les données au lieu de rechercher dans la table sous-jacente. Il est parfois possible de répondre entièrement aux requêtes selon les données dans l'index non-cluster, ou l'index non-cluster peut indiquer au [!INCLUDE[ssDE](../../includes/ssde-md.md)] les lignes dans la table sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="7369a-105">Nonclustered indexes can often help you find data more quickly than searching the underlying table; queries can sometimes be answered entirely by the data in the nonclustered index, or the nonclustered index can point the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to the rows in the underlying table.</span></span> <span data-ttu-id="7369a-106">En général, les index non-cluster sont créés pour améliorer les performances des requêtes fréquemment utilisées qui ne sont pas couvertes par l'index cluster ou pour rechercher des lignes dans une table sans index cluster (ce qui s'appelle un « segment »).</span><span class="sxs-lookup"><span data-stu-id="7369a-106">Generally, nonclustered indexes are created to improve the performance of frequently used queries not covered by the clustered index or to locate rows in a table without a clustered index (called a heap).</span></span> <span data-ttu-id="7369a-107">Vous pouvez créer plusieurs index non cluster sur une table ou une vue indexée.</span><span class="sxs-lookup"><span data-stu-id="7369a-107">You can create multiple nonclustered indexes on a table or indexed view.</span></span>  
  
 <span data-ttu-id="7369a-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="7369a-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7369a-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="7369a-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7369a-110">Implémentations types</span><span class="sxs-lookup"><span data-stu-id="7369a-110">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="7369a-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7369a-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7369a-112">**Pour créer un index non-cluster à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="7369a-112">**To create a nonclustered index, using:**</span></span>  
  
     [<span data-ttu-id="7369a-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7369a-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7369a-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7369a-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7369a-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7369a-115">Before You Begin</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a><span data-ttu-id="7369a-116">Implémentations typiques</span><span class="sxs-lookup"><span data-stu-id="7369a-116">Typical Implementations</span></span>  
 <span data-ttu-id="7369a-117">Les index non-cluster sont implémentés comme ceci :</span><span class="sxs-lookup"><span data-stu-id="7369a-117">Nonclustered indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="7369a-118">**Contraintes uniques**</span><span class="sxs-lookup"><span data-stu-id="7369a-118">**UNIQUE constraints**</span></span>  
  
     <span data-ttu-id="7369a-119">Lorsque vous créez une contrainte UNIQUE, un index non-cluster unique est créé pour appliquer par défaut une contrainte UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="7369a-119">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="7369a-120">Vous pouvez spécifier un index cluster unique si aucun index cluster n'existe déjà sur la table.</span><span class="sxs-lookup"><span data-stu-id="7369a-120">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span> <span data-ttu-id="7369a-121">Pour plus d’informations, consultez [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="7369a-121">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
-   <span data-ttu-id="7369a-122">**Index indépendant d'une contrainte**</span><span class="sxs-lookup"><span data-stu-id="7369a-122">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="7369a-123">Par défaut, un index non-cluster est créé si l'option CLUSTERED n'est pas spécifiée.</span><span class="sxs-lookup"><span data-stu-id="7369a-123">By default, a nonclustered index is created if clustered is not specified.</span></span> <span data-ttu-id="7369a-124">Le nombre maximal d'index non cluster pouvant être créés par table est de 999.</span><span class="sxs-lookup"><span data-stu-id="7369a-124">The maximum number of nonclustered indexes that can be created per table is 999.</span></span> <span data-ttu-id="7369a-125">Cela inclut tous les index créés par des contraintes PRIMARY KEY ou UNIQUE, mais pas les index XML.</span><span class="sxs-lookup"><span data-stu-id="7369a-125">This includes any indexes created by PRIMARY KEY or UNIQUE constraints, but does not include XML indexes.</span></span>  
  
-   <span data-ttu-id="7369a-126">**Index non-cluster sur une vue indexée**</span><span class="sxs-lookup"><span data-stu-id="7369a-126">**Nonclustered index on an indexed view**</span></span>  
  
     <span data-ttu-id="7369a-127">Une fois qu'un index cluster unique a été créé sur une vue, vous pouvez créer des index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="7369a-127">After a unique clustered index has been created on a view, nonclustered indexes can be created.</span></span> <span data-ttu-id="7369a-128">Pour plus d’informations, consultez [Créer des vues indexées](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="7369a-128">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7369a-129">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7369a-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7369a-130">Autorisations</span><span class="sxs-lookup"><span data-stu-id="7369a-130">Permissions</span></span>  
 <span data-ttu-id="7369a-131">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="7369a-131">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="7369a-132">L’utilisateur doit être membre du rôle serveur fixe **sysadmin** ou des rôles de base de données fixes **db_ddladmin** et **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="7369a-132">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7369a-133">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7369a-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-the-table-designer"></a><span data-ttu-id="7369a-134">Pour créer un index non-cluster à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="7369a-134">To create a nonclustered index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="7369a-135">Dans l'Explorateur d'objets, développez la base de données qui contient la table sur laquelle vous souhaitez créer un index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="7369a-135">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="7369a-136">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="7369a-136">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="7369a-137">Cliquez avec le bouton droit sur la table sur laquelle vous souhaitez créer un index non-cluster, puis sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="7369a-137">Right-click the table on which you want to create a nonclustered index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="7369a-138">Dans le menu **Concepteur de tables** , cliquez sur **index/clés**.</span><span class="sxs-lookup"><span data-stu-id="7369a-138">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="7369a-139">Dans la boîte de dialogue **Index/Clés** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="7369a-139">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="7369a-140">Sélectionnez le nouvel index dans la zone de texte **Clé ou index Primary/Unique sélectionné** .</span><span class="sxs-lookup"><span data-stu-id="7369a-140">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="7369a-141">Dans la grille, sélectionnez **Créer comme Clustered**et choisissez **Non** dans la liste déroulante à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="7369a-141">In the grid, select **Create as Clustered**, and choose **No** from the drop-down list to the right of the property.</span></span>  
  
8.  <span data-ttu-id="7369a-142">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="7369a-142">Click **Close**.</span></span>  
  
9. <span data-ttu-id="7369a-143">Dans le menu **Fichier** , cliquez sur **Enregistrer**_nom_table_.</span><span class="sxs-lookup"><span data-stu-id="7369a-143">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-create-a-nonclustered-index-by-using-object-explorer"></a><span data-ttu-id="7369a-144">Pour créer un index non-cluster à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="7369a-144">To create a nonclustered index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="7369a-145">Dans l'Explorateur d'objets, développez la base de données qui contient la table sur laquelle vous souhaitez créer un index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="7369a-145">In Object Explorer, expand the database that contains the table on which you want to create a nonclustered index.</span></span>  
  
2.  <span data-ttu-id="7369a-146">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="7369a-146">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="7369a-147">Développez la table sur laquelle vous souhaitez créer un index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="7369a-147">Expand the table on which you want to create a nonclustered index.</span></span>  
  
4.  <span data-ttu-id="7369a-148">Cliquez avec le bouton droit sur le dossier **Index**, pointez sur **Nouvel index**, puis sélectionnez **Index non cluster...** .</span><span class="sxs-lookup"><span data-stu-id="7369a-148">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="7369a-149">Dans la boîte de dialogue **Nouvel index** , sur la page **Général** , entrez le nom du nouvel index dans la zone **Nom de l'index** .</span><span class="sxs-lookup"><span data-stu-id="7369a-149">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="7369a-150">Sous **Colonnes clés d’index**, cliquez sur **Ajouter…** .</span><span class="sxs-lookup"><span data-stu-id="7369a-150">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="7369a-151">Dans la boîte de dialogue **Sélectionner les colonnes à partir de**_table_name_ , activez la ou les cases à cocher de la ou des colonnes de table à ajouter à l’index non cluster.</span><span class="sxs-lookup"><span data-stu-id="7369a-151">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the nonclustered index.</span></span>  
  
8.  <span data-ttu-id="7369a-152">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7369a-152">Click **OK**.</span></span>  
  
9. <span data-ttu-id="7369a-153">Dans la boîte de dialogue **Nouvel index** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7369a-153">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7369a-154">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7369a-154">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-nonclustered-index-on-a-table"></a><span data-ttu-id="7369a-155">Pour créer un index non-cluster sur une table</span><span class="sxs-lookup"><span data-stu-id="7369a-155">To create a nonclustered index on a table</span></span>  
  
1.  <span data-ttu-id="7369a-156">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7369a-156">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7369a-157">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7369a-157">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7369a-158">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7369a-158">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named IX_ProductVendor_VendorID and delete it if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
                WHERE name = N'IX_ProductVendor_VendorID')   
        DROP INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor;   
    GO  
    -- Create a nonclustered index called IX_ProductVendor_VendorID   
    -- on the Purchasing.ProductVendor table using the BusinessEntityID column.   
    CREATE NONCLUSTERED INDEX IX_ProductVendor_VendorID   
        ON Purchasing.ProductVendor (BusinessEntityID);   
    GO  
    ```  
  
 <span data-ttu-id="7369a-159">Pour plus d’informations, consultez [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7369a-159">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
