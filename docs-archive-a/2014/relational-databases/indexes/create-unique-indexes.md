---
title: Créer des vues uniques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- unique indexes
- designing indexes [SQL Server], unique
- clustered indexes, unique
- indexes [SQL Server], unique
- nonclustered indexes [SQL Server], unique
- unique indexes, design guidelines
ms.assetid: 56b5982e-cb94-46c0-8fbb-772fc275354a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c96c4e17a8ce0863452db171302d650f6114919
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708303"
---
# <a name="create-unique-indexes"></a><span data-ttu-id="647b2-102">Créer des index uniques</span><span class="sxs-lookup"><span data-stu-id="647b2-102">Create Unique Indexes</span></span>
  <span data-ttu-id="647b2-103">Cette rubrique explique comment créer un index unique sur une table dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="647b2-103">This topic describes how to create a unique index on a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="647b2-104">Un index unique garantit que la clé d'index ne contient aucune valeur dupliquée et que, par conséquent, chaque ligne de la table est unique d'une certaine manière.</span><span class="sxs-lookup"><span data-stu-id="647b2-104">A unique index guarantees that the index key contains no duplicate values and therefore every row in the table is in some way unique.</span></span> <span data-ttu-id="647b2-105">Il n'existe pas de différence notable entre la création d'une contrainte UNIQUE et la création d'un index unique indépendant de toute contrainte.</span><span class="sxs-lookup"><span data-stu-id="647b2-105">There are no significant differences between creating a UNIQUE constraint and creating a unique index that is independent of a constraint.</span></span> <span data-ttu-id="647b2-106">La validation des données se produit d'une manière similaire et l'optimiseur de requête ne fait aucune distinction entre un index unique créé à partir d'une contrainte et un index unique créé manuellement.</span><span class="sxs-lookup"><span data-stu-id="647b2-106">Data validation occurs in the same manner, and the query optimizer does not differentiate between a unique index created by a constraint or manually created.</span></span> <span data-ttu-id="647b2-107">Toutefois, la création d'une contrainte UNIQUE sur la colonne permet de clarifier l'objectif de l'index.</span><span class="sxs-lookup"><span data-stu-id="647b2-107">However, creating a UNIQUE constraint on the column makes the objective of the index clear.</span></span> <span data-ttu-id="647b2-108">Pour plus d'informations sur les contraintes UNIQUE, consultez [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="647b2-108">For more information on UNIQUE constraints, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md).</span></span>  
  
 <span data-ttu-id="647b2-109">Lorsque vous créez un index unique, une option vous permet d'ignorer les clés en double.</span><span class="sxs-lookup"><span data-stu-id="647b2-109">When you create a unique index, you can set an option to ignore duplicate keys.</span></span> <span data-ttu-id="647b2-110">Si vous affectez à cette option la valeur **Oui** et que vous tentez de créer une clé dupliquée en ajoutant des données concernant plusieurs lignes (avec l’instruction INSERT), la ligne qui contient le doublon n’est pas ajoutée.</span><span class="sxs-lookup"><span data-stu-id="647b2-110">If this option is set to **Yes** and you attempt to create duplicate keys by adding data that affects multiple rows (with the INSERT statement), the row containing a duplicate is not added.</span></span> <span data-ttu-id="647b2-111">Si elle a la valeur **Non**, l'intégralité de l'opération INSERT échoue et toutes les données sont restaurées.</span><span class="sxs-lookup"><span data-stu-id="647b2-111">If it is set to **No**, the entire insert operation fails and all the data is rolled back.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="647b2-112">Il n'est pas possible de créer un index unique sur une seule colonne si cette colonne contient des valeurs null dans plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="647b2-112">You cannot create a unique index on a single column if that column contains NULL in more than one row.</span></span> <span data-ttu-id="647b2-113">De même, il n'est pas possible de créer un index unique sur plusieurs colonnes si la combinaison des colonnes contient des valeurs null dans plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="647b2-113">Similarly, you cannot create a unique index on multiple columns if the combination of columns contains NULL in more than one row.</span></span> <span data-ttu-id="647b2-114">En effet, ces valeurs sont traitées comme des doublons par l'indexation.</span><span class="sxs-lookup"><span data-stu-id="647b2-114">These are treated as duplicate values for indexing purposes.</span></span>  
  
 <span data-ttu-id="647b2-115">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="647b2-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="647b2-116">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="647b2-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="647b2-117">Avantages d'un index unique</span><span class="sxs-lookup"><span data-stu-id="647b2-117">Benefits of a Unique Index</span></span>](#Benefits)  
  
     [<span data-ttu-id="647b2-118">Implémentations types</span><span class="sxs-lookup"><span data-stu-id="647b2-118">Typical Implementations</span></span>](#Implementations)  
  
     [<span data-ttu-id="647b2-119">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="647b2-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="647b2-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="647b2-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="647b2-121">**Pour créer un index unique sur une table, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="647b2-121">**To create a unique index on a table, using:**</span></span>  
  
     [<span data-ttu-id="647b2-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="647b2-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="647b2-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="647b2-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="647b2-124">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="647b2-124">Before You Begin</span></span>  
  
###  <a name="benefits-of-a-unique-index"></a><a name="Benefits"></a> <span data-ttu-id="647b2-125">Avantages d'un index unique</span><span class="sxs-lookup"><span data-stu-id="647b2-125">Benefits of a Unique Index</span></span>  
  
-   <span data-ttu-id="647b2-126">Les index uniques multicolonnes garantissent que chaque combinaison de valeurs dans la clé d'index est unique.</span><span class="sxs-lookup"><span data-stu-id="647b2-126">Multicolumn unique indexes guarantee that each combination of values in the index key is unique.</span></span> <span data-ttu-id="647b2-127">Par exemple, si un index unique est créé sur une combinaison des colonnes **LastName**, **FirstName**et **MiddleName** , deux lignes de la table ne peuvent pas posséder la même combinaison de valeurs pour ces colonnes.</span><span class="sxs-lookup"><span data-stu-id="647b2-127">For example, if a unique index is created on a combination of **LastName**, **FirstName**, and **MiddleName** columns, no two rows in the table could have the same combination of values for these columns.</span></span>  
  
-   <span data-ttu-id="647b2-128">À condition que les données contenues dans chaque colonne soient uniques, vous pouvez créer à la fois un index cluster unique et plusieurs index non cluster uniques sur la même table.</span><span class="sxs-lookup"><span data-stu-id="647b2-128">Provided that the data in each column is unique, you can create both a unique clustered index and multiple unique nonclustered indexes on the same table.</span></span>  
  
-   <span data-ttu-id="647b2-129">Les index uniques garantissent l'intégrité des données des colonnes définies.</span><span class="sxs-lookup"><span data-stu-id="647b2-129">Unique indexes ensure the data integrity of the defined columns.</span></span>  
  
-   <span data-ttu-id="647b2-130">Les index uniques fournissent des informations supplémentaires utiles à l'optimiseur de requête qui peut produire des plans d'exécution plus efficaces.</span><span class="sxs-lookup"><span data-stu-id="647b2-130">Unique indexes provide additional information helpful to the query optimizer that can produce more efficient execution plans.</span></span>  
  
###  <a name="typical-implementations"></a><a name="Implementations"></a> <span data-ttu-id="647b2-131">Implémentations types</span><span class="sxs-lookup"><span data-stu-id="647b2-131">Typical Implementations</span></span>  
 <span data-ttu-id="647b2-132">Les index uniques sont implémentés à l'aide des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="647b2-132">Unique indexes are implemented in the following ways:</span></span>  
  
-   <span data-ttu-id="647b2-133">**Contrainte PRIMARY KEY ou UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="647b2-133">**PRIMARY KEY or UNIQUE constraint**</span></span>  
  
     <span data-ttu-id="647b2-134">La création d'une contrainte PRIMARY KEY entraîne la création automatique d'un index cluster unique sur la ou les colonnes pour autant qu'il n'existe pas encore d'index cluster dans la table ou qu'un index non-cluster unique n'ait pas été défini explicitement.</span><span class="sxs-lookup"><span data-stu-id="647b2-134">When you create a PRIMARY KEY constraint, a unique clustered index on the column or columns is automatically created if a clustered index on the table does not already exist and you do not specify a unique nonclustered index.</span></span> <span data-ttu-id="647b2-135">La colonne clé primaire ne peut pas contenir de valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="647b2-135">The primary key column cannot allow NULL values.</span></span>  
  
     <span data-ttu-id="647b2-136">Lorsque vous créez une contrainte UNIQUE, un index non-cluster unique est créé pour appliquer par défaut une contrainte UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="647b2-136">When you create a UNIQUE constraint, a unique nonclustered index is created to enforce a UNIQUE constraint by default.</span></span> <span data-ttu-id="647b2-137">Vous pouvez spécifier un index cluster unique si aucun index cluster n'existe déjà sur la table.</span><span class="sxs-lookup"><span data-stu-id="647b2-137">You can specify a unique clustered index if a clustered index on the table does not already exist.</span></span>  
  
     <span data-ttu-id="647b2-138">Pour plus d'informations, consultez [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) et [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="647b2-138">For more information, see [Unique Constraints and Check Constraints](../tables/unique-constraints-and-check-constraints.md) and [Primary and Foreign Key Constraints](../tables/primary-and-foreign-key-constraints.md).</span></span>  
  
-   <span data-ttu-id="647b2-139">**Index indépendant d'une contrainte**</span><span class="sxs-lookup"><span data-stu-id="647b2-139">**Index independent of a constraint**</span></span>  
  
     <span data-ttu-id="647b2-140">Vous pouvez définir plusieurs index non-cluster uniques dans une table.</span><span class="sxs-lookup"><span data-stu-id="647b2-140">Multiple unique nonclustered indexes can be defined on a table.</span></span>  
  
     <span data-ttu-id="647b2-141">Pour plus d’informations, consultez [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="647b2-141">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="647b2-142">**Vue indexée**</span><span class="sxs-lookup"><span data-stu-id="647b2-142">**Indexed view**</span></span>  
  
     <span data-ttu-id="647b2-143">Pour créer une vue indexée, vous devez définir un index cluster unique sur une ou plusieurs colonnes de vue.</span><span class="sxs-lookup"><span data-stu-id="647b2-143">To create an indexed view, a unique clustered index is defined on one or more view columns.</span></span> <span data-ttu-id="647b2-144">La vue est exécutée et le jeu de résultats est stocké au niveau feuille de l'index de la même manière que les données de table sont stockées dans un index cluster.</span><span class="sxs-lookup"><span data-stu-id="647b2-144">The view is executed and the result set is stored in the leaf level of the index in the same way table data is stored in a clustered index.</span></span> <span data-ttu-id="647b2-145">Pour plus d’informations, consultez [Créer des vues indexées](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="647b2-145">For more information, see [Create Indexed Views](../views/views.md).</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="647b2-146">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="647b2-146">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="647b2-147">Un index unique, une contrainte UNIQUE ou une contrainte PRIMARY KEY ne peuvent pas être créés si les données comportent des valeurs de clé dupliquées.</span><span class="sxs-lookup"><span data-stu-id="647b2-147">A unique index, UNIQUE constraint, or PRIMARY KEY constraint cannot be created if duplicate key values exist in the data.</span></span>  
  
-   <span data-ttu-id="647b2-148">Un index non cluster unique peut contenir des colonnes non-clés incluses.</span><span class="sxs-lookup"><span data-stu-id="647b2-148">A unique nonclustered index can contain included nonkey columns.</span></span> <span data-ttu-id="647b2-149">Pour plus d’informations, consultez [Créer des index avec colonnes incluses](create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="647b2-149">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="647b2-150">Sécurité</span><span class="sxs-lookup"><span data-stu-id="647b2-150">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="647b2-151">Autorisations</span><span class="sxs-lookup"><span data-stu-id="647b2-151">Permissions</span></span>  
 <span data-ttu-id="647b2-152">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="647b2-152">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="647b2-153">L’utilisateur doit être membre du rôle serveur fixe **sysadmin** ou des rôles de base de données fixes **db_ddladmin** et **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="647b2-153">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="647b2-154">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="647b2-154">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-index-by-using-the-table-designer"></a><span data-ttu-id="647b2-155">Pour créer un index unique à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="647b2-155">To create a unique index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="647b2-156">Dans l'Explorateur d'objets, développez la base de données qui contient la table sur laquelle vous souhaitez créer un index unique.</span><span class="sxs-lookup"><span data-stu-id="647b2-156">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="647b2-157">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="647b2-157">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="647b2-158">Cliquez avec le bouton droit sur la table sur laquelle vous souhaitez créer un index unique, puis sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="647b2-158">Right-click the table on which you want to create a unique index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="647b2-159">Dans le menu **Concepteur de tables** , sélectionnez **Index/Clés**.</span><span class="sxs-lookup"><span data-stu-id="647b2-159">On the **Table Designer** menu, select **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="647b2-160">Dans la boîte de dialogue **Index/Clés** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="647b2-160">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="647b2-161">Sélectionnez le nouvel index dans la zone de texte **Clé ou index Primary/Unique sélectionné** .</span><span class="sxs-lookup"><span data-stu-id="647b2-161">Select the new index in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
7.  <span data-ttu-id="647b2-162">Dans la grille principale, sous **(Général)** , sélectionnez **Type** puis choisissez **Index** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="647b2-162">In the main grid, under **(General)**, select **Type** and then choose **Index** from the list.</span></span>  
  
8.  <span data-ttu-id="647b2-163">Sélectionnez **Colonnes**, puis cliquez sur les points de suspension **(…)** .</span><span class="sxs-lookup"><span data-stu-id="647b2-163">Select **Columns**, and then click the ellipsis **(...)**.</span></span>  
  
9. <span data-ttu-id="647b2-164">Dans la boîte de dialogue **Colonnes d'index** , sous **Nom de la colonne**, sélectionnez les colonnes que vous souhaitez indexer.</span><span class="sxs-lookup"><span data-stu-id="647b2-164">In the **Index Columns** dialog box, under **Column Name**, select the columns you want to index.</span></span> <span data-ttu-id="647b2-165">Vous pouvez sélectionner jusqu'à 16 colonnes.</span><span class="sxs-lookup"><span data-stu-id="647b2-165">You can select up to 16 columns.</span></span> <span data-ttu-id="647b2-166">Si vous souhaitez que les performances soient optimales, évitez d'en sélectionner plus de deux par index.</span><span class="sxs-lookup"><span data-stu-id="647b2-166">For optimal performance, select only one or two columns per index.</span></span> <span data-ttu-id="647b2-167">Pour chaque colonne sélectionnée, vous pouvez indiquer si l'index organise ses valeurs en ordre croissant ou décroissant.</span><span class="sxs-lookup"><span data-stu-id="647b2-167">For each column you select, indicate whether the index arranges values of this column in ascending or descending order.</span></span>  
  
10. <span data-ttu-id="647b2-168">Lorsque toutes les colonnes sont sélectionnées pour l'index, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="647b2-168">When all columns for the index are selected, click **OK**.</span></span>  
  
11. <span data-ttu-id="647b2-169">Dans la grille, sous **(Général)** , sélectionnez **Est unique** , puis choisissez **Oui** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="647b2-169">In the grid, under **(General)**, select **Is Unique** and then choose **Yes** from the list.</span></span>  
  
12. <span data-ttu-id="647b2-170">Facultatif : Dans la grille principale, sous **Concepteur de tables**, sélectionnez **Ignorer les clés dupliquées** , puis choisissez **Oui** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="647b2-170">Optional: In the main grid, under **Table Designer**, select **Ignore Duplicate Keys** and then choose **Yes** from the list.</span></span> <span data-ttu-id="647b2-171">Effectuez cette opération si vous souhaitez ignorer les tentatives d'ajout de données qui créeraient une clé dupliquée dans l'index unique.</span><span class="sxs-lookup"><span data-stu-id="647b2-171">Do this if you want to ignore attempts to add data that would create a duplicate key in the unique index.</span></span>  
  
13. <span data-ttu-id="647b2-172">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="647b2-172">Click **Close**.</span></span>  
  
14. <span data-ttu-id="647b2-173">Dans le menu **Fichier** , cliquez sur **Enregistrer**_nom_table_.</span><span class="sxs-lookup"><span data-stu-id="647b2-173">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="create-a-unique-index-by-using-object-explorer"></a><span data-ttu-id="647b2-174">Créer un index unique à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="647b2-174">Create a unique index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="647b2-175">Dans l'Explorateur d'objets, développez la base de données qui contient la table sur laquelle vous souhaitez créer un index unique.</span><span class="sxs-lookup"><span data-stu-id="647b2-175">In Object Explorer, expand the database that contains the table on which you want to create a unique index.</span></span>  
  
2.  <span data-ttu-id="647b2-176">Développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="647b2-176">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="647b2-177">Développez la table sur laquelle vous souhaitez créer un index unique.</span><span class="sxs-lookup"><span data-stu-id="647b2-177">Expand the table on which you want to create a unique index.</span></span>  
  
4.  <span data-ttu-id="647b2-178">Cliquez avec le bouton droit sur le dossier **Index**, pointez sur **Nouvel index**, puis sélectionnez **Index non cluster...** .</span><span class="sxs-lookup"><span data-stu-id="647b2-178">Right-click the **Indexes** folder, point to **New Index**, and select **Non-Clustered Index...**.</span></span>  
  
5.  <span data-ttu-id="647b2-179">Dans la boîte de dialogue **Nouvel index** , sur la page **Général** , entrez le nom du nouvel index dans la zone **Nom de l'index** .</span><span class="sxs-lookup"><span data-stu-id="647b2-179">In the **New Index** dialog box, on the **General** page, enter the name of the new index in the **Index name** box.</span></span>  
  
6.  <span data-ttu-id="647b2-180">Activez la case à cocher **Unique** .</span><span class="sxs-lookup"><span data-stu-id="647b2-180">Select the **Unique** check box.</span></span>  
  
7.  <span data-ttu-id="647b2-181">Sous **Colonnes clés d’index**, cliquez sur **Ajouter…** .</span><span class="sxs-lookup"><span data-stu-id="647b2-181">Under **Index key columns**, click **Add...**.</span></span>  
  
8.  <span data-ttu-id="647b2-182">Dans la boîte de dialogue **Sélectionner les colonnes à partir de**_table_name_ , activez la ou les cases à cocher de la ou des colonnes de table à ajouter à l’index unique.</span><span class="sxs-lookup"><span data-stu-id="647b2-182">In the **Select Columns from**_table_name_ dialog box, select the check box or check boxes of the table column or columns to be added to the unique index.</span></span>  
  
9. <span data-ttu-id="647b2-183">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="647b2-183">Click **OK**.</span></span>  
  
10. <span data-ttu-id="647b2-184">Dans la boîte de dialogue **Nouvel index** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="647b2-184">In the **New Index** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="647b2-185">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="647b2-185">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-index-on-a-table"></a><span data-ttu-id="647b2-186">Pour créer un index unique sur une table</span><span class="sxs-lookup"><span data-stu-id="647b2-186">To create a unique index on a table</span></span>  
  
1.  <span data-ttu-id="647b2-187">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="647b2-187">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="647b2-188">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="647b2-188">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="647b2-189">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="647b2-189">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Find an existing index named AK_UnitMeasure_Name and delete it if found  
    IF EXISTS (SELECT name from sys.indexes  
               WHERE name = N'AK_UnitMeasure_Name')   
       DROP INDEX AK_UnitMeasure_Name ON Production.UnitMeasure;   
    GO  
    -- Create a unique index called AK_UnitMeasure_Name  
    -- on the Production.UnitMeasure table using the Name column.  
    CREATE UNIQUE INDEX AK_UnitMeasure_Name   
       ON Production.UnitMeasure (Name);   
    GO  
    ```  
  
 <span data-ttu-id="647b2-190">Pour plus d’informations, consultez [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="647b2-190">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
