---
title: Créer des index filtrés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- filtered indexes [SQL Server], about filtered indexes
- designing indexes [SQL Server], filtered
- filtered indexes [SQL Server]
- nonclustered indexes [SQL Server], filtered
- indexes [SQL Server], filtered
ms.assetid: 25e1fcc5-45d7-4c53-8c79-5493dfaa1c74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77cf641ca84181496f26a995244029d0525ade63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708323"
---
# <a name="create-filtered-indexes"></a><span data-ttu-id="8ca71-102">Créer des index filtrés</span><span class="sxs-lookup"><span data-stu-id="8ca71-102">Create Filtered Indexes</span></span>
  <span data-ttu-id="8ca71-103">Cette rubrique explique comment créer un index filtré dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ca71-103">This topic describes how to create a filtered index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8ca71-104">Un index filtré est un index non cluster optimisé convenant tout particulièrement aux requêtes qui effectuent des sélections dans un sous-ensemble de données bien défini.</span><span class="sxs-lookup"><span data-stu-id="8ca71-104">A filtered index is an optimized nonclustered index especially suited to cover queries that select from a well-defined subset of data.</span></span> <span data-ttu-id="8ca71-105">Il utilise un prédicat de filtre pour indexer une partie des lignes de la table.</span><span class="sxs-lookup"><span data-stu-id="8ca71-105">It uses a filter predicate to index a portion of rows in the table.</span></span> <span data-ttu-id="8ca71-106">Un index filtré bien conçu peut améliorer les performances des requêtes et réduire les coûts de maintenance et de stockage des index par rapport aux index de table entière.</span><span class="sxs-lookup"><span data-stu-id="8ca71-106">A well-designed filtered index can improve query performance as well as reduce index maintenance and storage costs compared with full-table indexes.</span></span>  
  
 <span data-ttu-id="8ca71-107">Les index filtrés peuvent présenter les avantages suivants par rapport aux index de table entière :</span><span class="sxs-lookup"><span data-stu-id="8ca71-107">Filtered indexes can provide the following advantages over full-table indexes:</span></span>  
  
-   <span data-ttu-id="8ca71-108">**Meilleures performances des requêtes et qualité de plan améliorée**</span><span class="sxs-lookup"><span data-stu-id="8ca71-108">**Improved query performance and plan quality**</span></span>  
  
     <span data-ttu-id="8ca71-109">Un index filtré bien conçu améliore les performances des requêtes et la qualité du plan d'exécution car il est plus petit qu'un index non cluster de table entière et contient des statistiques filtrées.</span><span class="sxs-lookup"><span data-stu-id="8ca71-109">A well-designed filtered index improves query performance and execution plan quality because it is smaller than a full-table nonclustered index and has filtered statistics.</span></span> <span data-ttu-id="8ca71-110">Les statistiques filtrées sont plus précises que les statistiques de table entière car elles couvrent uniquement les lignes de l'index filtré.</span><span class="sxs-lookup"><span data-stu-id="8ca71-110">The filtered statistics are more accurate than full-table statistics because they cover only the rows in the filtered index.</span></span>  
  
-   <span data-ttu-id="8ca71-111">**Coûts réduits de maintenance des index**</span><span class="sxs-lookup"><span data-stu-id="8ca71-111">**Reduced index maintenance costs**</span></span>  
  
     <span data-ttu-id="8ca71-112">La maintenance d'un index intervient uniquement lorsque les instructions de langage de manipulation de données (DML) affectent les données de l'index.</span><span class="sxs-lookup"><span data-stu-id="8ca71-112">An index is maintained only when data manipulation language (DML) statements affect the data in the index.</span></span> <span data-ttu-id="8ca71-113">Un index filtré réduit les coûts de maintenance des index par rapport à un index non cluster de table entière car il est plus petit et sa maintenance n'a lieu que lorsque les données de l'index sont modifiées.</span><span class="sxs-lookup"><span data-stu-id="8ca71-113">A filtered index reduces index maintenance costs compared with a full-table nonclustered index because it is smaller and is only maintained when the data in the index is changed.</span></span> <span data-ttu-id="8ca71-114">Il est possible d'avoir un grand nombre d'index filtrés, notamment s'ils contiennent des données qui sont rarement modifiées.</span><span class="sxs-lookup"><span data-stu-id="8ca71-114">It is possible to have a large number of filtered indexes, especially when they contain data that is changed infrequently.</span></span> <span data-ttu-id="8ca71-115">De la même façon, si un index filtré contient uniquement les données fréquemment modifiées, la taille réduite de l'index limite le coût de la mise à jour des statistiques.</span><span class="sxs-lookup"><span data-stu-id="8ca71-115">Similarly, if a filtered index contains only the frequently modified data, the smaller size of the index reduces the cost of updating the statistics.</span></span>  
  
-   <span data-ttu-id="8ca71-116">**Coûts réduits de stockage des index**</span><span class="sxs-lookup"><span data-stu-id="8ca71-116">**Reduced index storage costs**</span></span>  
  
     <span data-ttu-id="8ca71-117">La création d'un index filtré peut réduire le stockage sur disque des index non cluster lorsqu'un index de table entière n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8ca71-117">Creating a filtered index can reduce disk storage for nonclustered indexes when a full-table index is not necessary.</span></span> <span data-ttu-id="8ca71-118">Vous pouvez remplacer un index non cluster de table entière par plusieurs index filtrés sans augmenter considérablement le stockage nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8ca71-118">You can replace a full-table nonclustered index with multiple filtered indexes without significantly increasing the storage requirements.</span></span>  
  
 <span data-ttu-id="8ca71-119">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="8ca71-119">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8ca71-120">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="8ca71-120">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8ca71-121">Remarques sur la conception</span><span class="sxs-lookup"><span data-stu-id="8ca71-121">Design Considerations</span></span>](#Design)  
  
     [<span data-ttu-id="8ca71-122">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8ca71-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8ca71-123">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8ca71-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8ca71-124">**Pour créer un index filtré, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="8ca71-124">**To create a filtered index, using:**</span></span>  
  
     [<span data-ttu-id="8ca71-125">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ca71-125">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8ca71-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ca71-126">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8ca71-127">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8ca71-127">Before You Begin</span></span>  
  
###  <a name="design-considerations"></a><a name="Design"></a> <span data-ttu-id="8ca71-128">Remarques sur la conception</span><span class="sxs-lookup"><span data-stu-id="8ca71-128">Design Considerations</span></span>  
  
-   <span data-ttu-id="8ca71-129">Lorsqu'une colonne contient seulement un petit nombre de valeurs pertinentes pour les requêtes, vous pouvez créer un index filtré sur ce sous-ensemble de valeurs.</span><span class="sxs-lookup"><span data-stu-id="8ca71-129">When a column only has a small number of relevant values for queries, you can create a filtered index on the subset of values.</span></span> <span data-ttu-id="8ca71-130">Ainsi, lorsque les valeurs d'une colonne sont principalement NULL et que la requête effectue uniquement des sélections dans les valeurs non NULL, vous pouvez créer un index filtré pour les lignes de données non NULL.</span><span class="sxs-lookup"><span data-stu-id="8ca71-130">For example, when the values in a column are mostly NULL and the query selects only from the non-NULL values, you can create a filtered index for the non-NULL data rows.</span></span> <span data-ttu-id="8ca71-131">L'index ainsi créé sera plus petit et coûtera moins cher en maintenance qu'un index non cluster de table entière défini sur les mêmes colonnes clés.</span><span class="sxs-lookup"><span data-stu-id="8ca71-131">The resulting index will be smaller and cost less to maintain than a full-table nonclustered index defined on the same key columns.</span></span>  
  
-   <span data-ttu-id="8ca71-132">Lorsqu'une table contient des lignes des données hétérogènes, vous pouvez créer un index filtré pour une ou plusieurs catégories de données.</span><span class="sxs-lookup"><span data-stu-id="8ca71-132">When a table has heterogeneous data rows, you can create a filtered index for one or more categories of data.</span></span> <span data-ttu-id="8ca71-133">Ceci peut améliorer les performances des requêtes sur ces lignes de données en limitant la portée d'une requête à une région spécifique de la table.</span><span class="sxs-lookup"><span data-stu-id="8ca71-133">This can improve the performance of queries on these data rows by narrowing the focus of a query to a specific area of the table.</span></span> <span data-ttu-id="8ca71-134">En outre, l'index ainsi créé sera plus petit et coûtera moins cher en maintenance qu'un index non cluster de table entière.</span><span class="sxs-lookup"><span data-stu-id="8ca71-134">Again, the resulting index will be smaller and cost less to maintain than a full-table nonclustered index.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8ca71-135">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="8ca71-135">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8ca71-136">Vous ne pouvez pas créer un index filtré sur une vue.</span><span class="sxs-lookup"><span data-stu-id="8ca71-136">You cannot create a filtered index on a view.</span></span> <span data-ttu-id="8ca71-137">Toutefois, l'optimiseur de requête peut tirer parti d'un index filtré défini sur une table référencée dans une vue.</span><span class="sxs-lookup"><span data-stu-id="8ca71-137">However, the query optimizer can benefit from a filtered index defined on a table that is referenced in a view.</span></span> <span data-ttu-id="8ca71-138">L'optimiseur de requête prend en considération un index filtré pour une requête qui effectue des sélections dans une vue si les résultats de la requête sont corrects.</span><span class="sxs-lookup"><span data-stu-id="8ca71-138">The query optimizer considers a filtered index for a query that selects from a view if the query results will be correct.</span></span>  
  
-   <span data-ttu-id="8ca71-139">Les index filtrés présentent les avantages suivants par rapport aux vues indexées :</span><span class="sxs-lookup"><span data-stu-id="8ca71-139">Filtered indexes have the following advantages over indexed views:</span></span>  
  
    -   <span data-ttu-id="8ca71-140">Coûts réduits de maintenance des index.</span><span class="sxs-lookup"><span data-stu-id="8ca71-140">Reduced index maintenance costs.</span></span> <span data-ttu-id="8ca71-141">Par exemple, le processeur de requêtes utilise moins de ressources processeur pour mettre à jour un index filtré qu'une vue indexée.</span><span class="sxs-lookup"><span data-stu-id="8ca71-141">For example, the query processor uses fewer CPU resources to update a filtered index than an indexed view.</span></span>  
  
    -   <span data-ttu-id="8ca71-142">Qualité de plan améliorée.</span><span class="sxs-lookup"><span data-stu-id="8ca71-142">Improved plan quality.</span></span> <span data-ttu-id="8ca71-143">Par exemple, lors de la compilation de la requête, l'optimiseur de requête envisage beaucoup plus souvent d'utiliser un index filtré que la vue indexée équivalente.</span><span class="sxs-lookup"><span data-stu-id="8ca71-143">For example, during query compilation, the query optimizer considers using a filtered index in more situations than the equivalent indexed view.</span></span>  
  
    -   <span data-ttu-id="8ca71-144">Reconstructions d'index en ligne.</span><span class="sxs-lookup"><span data-stu-id="8ca71-144">Online index rebuilds.</span></span> <span data-ttu-id="8ca71-145">Vous pouvez reconstruire des index filtrés alors qu'ils sont disponibles pour les requêtes.</span><span class="sxs-lookup"><span data-stu-id="8ca71-145">You can rebuild filtered indexes while they are available for queries.</span></span> <span data-ttu-id="8ca71-146">Les reconstructions d'index en ligne ne sont pas prises en charge pour les vues indexées.</span><span class="sxs-lookup"><span data-stu-id="8ca71-146">Online index rebuilds are not supported for indexed views.</span></span> <span data-ttu-id="8ca71-147">Pour plus d’informations, consultez l’option REBUILD pour [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ca71-147">For more information, see the REBUILD option for [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
    -   <span data-ttu-id="8ca71-148">Index non uniques.</span><span class="sxs-lookup"><span data-stu-id="8ca71-148">Non-unique indexes.</span></span> <span data-ttu-id="8ca71-149">Les index filtrés peuvent être non uniques, alors que les vues indexées doivent être uniques.</span><span class="sxs-lookup"><span data-stu-id="8ca71-149">Filtered indexes can be non-unique, whereas indexed views must be unique.</span></span>  
  
-   <span data-ttu-id="8ca71-150">Les index filtrés sont définis sur une seule table et ne prennent en charge que les opérateurs de comparaison simples.</span><span class="sxs-lookup"><span data-stu-id="8ca71-150">Filtered indexes are defined on one table and only support simple comparison operators.</span></span> <span data-ttu-id="8ca71-151">Si vous avez besoin d'une expression de filtre qui référence plusieurs tables ou présente une logique complexe, vous devez créer une vue.</span><span class="sxs-lookup"><span data-stu-id="8ca71-151">If you need a filter expression that references multiple tables or has complex logic, you should create a view.</span></span>  
  
-   <span data-ttu-id="8ca71-152">Il n'est pas nécessaire qu'une colonne de l'expression d'index filtré soit une colonne clé ou incluse dans la définition de l'index filtré si l'expression d'index filtré est équivalente au prédicat de requête et si la requête ne retourne pas la colonne dans l'expression d'index filtré avec les résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="8ca71-152">A column in the filtered index expression does not need to be a key or included column in the filtered index definition if the filtered index expression is equivalent to the query predicate and the query does not return the column in the filtered index expression with the query results.</span></span>  
  
-   <span data-ttu-id="8ca71-153">Une colonne de l'expression d'index filtré doit être une colonne clé ou incluse dans la définition de l'index filtré si le prédicat de la requête utilise cette colonne dans une comparaison qui n'est pas équivalente à l'expression d'index filtré.</span><span class="sxs-lookup"><span data-stu-id="8ca71-153">A column in the filtered index expression should be a key or included column in the filtered index definition if the query predicate uses the column in a comparison that is not equivalent to the filtered index expression.</span></span>  
  
-   <span data-ttu-id="8ca71-154">Une colonne de l'expression d'index filtré doit être une colonne clé ou incluse dans la définition de l'index filtré si la colonne se trouve dans le jeu de résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="8ca71-154">A column in the filtered index expression should be a key or included column in the filtered index definition if the column is in the query result set.</span></span>  
  
-   <span data-ttu-id="8ca71-155">Il n'est pas nécessaire que la clé de l'index cluster de la table soit une colonne clé ou incluse dans la définition de l'index filtré.</span><span class="sxs-lookup"><span data-stu-id="8ca71-155">The clustered index key of the table does not need to be a key or included column in the filtered index definition.</span></span> <span data-ttu-id="8ca71-156">La clé de l'index cluster est automatiquement incluse dans tous les index non cluster, y compris les index filtrés.</span><span class="sxs-lookup"><span data-stu-id="8ca71-156">The clustered index key is automatically included in all nonclustered indexes, including filtered indexes.</span></span>  
  
-   <span data-ttu-id="8ca71-157">Si l'opérateur de comparaison spécifié dans l'expression d'index filtré de l'index filtré provoque une conversion de données implicite ou explicite, une erreur se produit si cette conversion se produit du côté gauche d'un opérateur de comparaison.</span><span class="sxs-lookup"><span data-stu-id="8ca71-157">If the comparison operator specified in the filtered index expression of the filtered index results in an implicit or explicit data conversion, an error will occur if the conversion occurs on the left side of a comparison operator.</span></span> <span data-ttu-id="8ca71-158">Une solution consiste à écrire l'expression d'index filtré avec l'opérateur de conversion de données (CAST ou CONVERT) à droite de l'opérateur de comparaison.</span><span class="sxs-lookup"><span data-stu-id="8ca71-158">A solution is to write the filtered index expression with the data conversion operator (CAST or CONVERT) on the right side of the comparison operator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8ca71-159">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8ca71-159">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8ca71-160">Autorisations</span><span class="sxs-lookup"><span data-stu-id="8ca71-160">Permissions</span></span>  
 <span data-ttu-id="8ca71-161">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="8ca71-161">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="8ca71-162">L’utilisateur doit être membre du rôle serveur fixe **sysadmin** ou des rôles de base de données fixes **db_ddladmin** et **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="8ca71-162">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span> <span data-ttu-id="8ca71-163">Pour modifier l'expression d'index filtré, utilisez CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="8ca71-163">To modify the filtered index expression, use CREATE INDEX WITH DROP_EXISTING.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8ca71-164">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8ca71-164">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="8ca71-165">Pour créer un index filtré</span><span class="sxs-lookup"><span data-stu-id="8ca71-165">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="8ca71-166">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez créer un index filtré.</span><span class="sxs-lookup"><span data-stu-id="8ca71-166">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to create a filtered index.</span></span>  
  
2.  <span data-ttu-id="8ca71-167">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="8ca71-167">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="8ca71-168">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez créer un index filtré.</span><span class="sxs-lookup"><span data-stu-id="8ca71-168">Click the plus sign to expand the table on which you want to create a filtered index.</span></span>  
  
4.  <span data-ttu-id="8ca71-169">Cliquez avec le bouton droit sur le dossier **Index**, pointez sur **Nouvel index**, puis sélectionnez **Index non cluster...** .</span><span class="sxs-lookup"><span data-stu-id="8ca71-169">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="8ca71-170">Dans la boîte de dialogue **Nouvel index** , sur la page **Général** , entrez le nom du nouvel index dans la zone **Nom de l'index** .</span><span class="sxs-lookup"><span data-stu-id="8ca71-170">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="8ca71-171">Sous **Colonnes clés d’index**, cliquez sur **Ajouter…** .</span><span class="sxs-lookup"><span data-stu-id="8ca71-171">Under **Index key columns**, click **Add...**.</span></span>  
  
7.  <span data-ttu-id="8ca71-172">Dans la boîte de dialogue **Sélectionner les colonnes à partir de**_table_name_ , activez la ou les cases à cocher de la ou des colonnes de table à ajouter à l’index unique.</span><span class="sxs-lookup"><span data-stu-id="8ca71-172">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
8.  <span data-ttu-id="8ca71-173">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ca71-173">Click **OK**.</span></span>  
  
9. <span data-ttu-id="8ca71-174">Dans la page **Filtre**, sous **Expression de filtre**, entrez l’expression SQL que vous utiliserez pour créer l’index filtré.</span><span class="sxs-lookup"><span data-stu-id="8ca71-174">On the **Filter** page, under **Filter Expression**, enter SQL expression that you'll use to create the filtered index.</span></span>  
  
10. <span data-ttu-id="8ca71-175">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ca71-175">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8ca71-176">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8ca71-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-filtered-index"></a><span data-ttu-id="8ca71-177">Pour créer un index filtré</span><span class="sxs-lookup"><span data-stu-id="8ca71-177">To create a filtered index</span></span>  
  
1.  <span data-ttu-id="8ca71-178">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ca71-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8ca71-179">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="8ca71-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8ca71-180">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8ca71-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Looks for an existing filtered index named "FIBillOfMaterialsWithEndDate"  
    -- and deletes it from the table Production.BillOfMaterials if found.   
    IF EXISTS (SELECT name FROM sys.indexes  
        WHERE name = N'FIBillOfMaterialsWithEndDate'  
        AND object_id = OBJECT_ID (N'Production.BillOfMaterials'))  
    DROP INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials  
    GO  
    -- Creates a filtered index "FIBillOfMaterialsWithEndDate"  
    -- on the table Production.BillOfMaterials   
    -- using the columms ComponentID and StartDate.  
  
    CREATE NONCLUSTERED INDEX FIBillOfMaterialsWithEndDate  
        ON Production.BillOfMaterials (ComponentID, StartDate)  
        WHERE EndDate IS NOT NULL ;  
    GO  
    ```  
  
     <span data-ttu-id="8ca71-181">L'index filtré ci-dessus est valide pour la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="8ca71-181">The filtered index above is valid for the following query.</span></span> <span data-ttu-id="8ca71-182">Vous pouvez afficher le plan d'exécution de la requête pour déterminer si l'optimiseur de requête a utilisé l'index filtré.</span><span class="sxs-lookup"><span data-stu-id="8ca71-182">You can display the query execution plan to determine if the query optimizer used the filtered index.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ProductAssemblyID, ComponentID, StartDate   
    FROM Production.BillOfMaterials  
    WHERE EndDate IS NOT NULL   
        AND ComponentID = 5   
        AND StartDate > '01/01/2008' ;  
    GO  
    ```  
  
#### <a name="to-ensure-that-a-filtered-index-is-used-in-a-sql-query"></a><span data-ttu-id="8ca71-183">Pour vous assurer qu'un index filtré est utilisé dans une requête SQL</span><span class="sxs-lookup"><span data-stu-id="8ca71-183">To ensure that a filtered index is used in a SQL query</span></span>  
  
1.  <span data-ttu-id="8ca71-184">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ca71-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8ca71-185">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="8ca71-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8ca71-186">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8ca71-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT ComponentID, StartDate FROM Production.BillOfMaterials  
        WITH ( INDEX ( FIBillOfMaterialsWithEndDate ) )   
    WHERE EndDate IN ('20000825', '20000908', '20000918');   
    GO  
    ```  
  
 <span data-ttu-id="8ca71-187">Pour plus d’informations, consultez [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8ca71-187">For more information, see  [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
