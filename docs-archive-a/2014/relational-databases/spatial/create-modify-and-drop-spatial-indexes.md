---
title: Créer, modifier et supprimer les index spatiaux | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], creating
- spatial indexes [SQL Server], dropping
- spatial indexes [SQL Server], creating
- indexes [SQL Server], dropping
- indexes [SQL Server], modifying
- spatial indexes [SQL Server], modifying
ms.assetid: 00c1b927-8ec5-44cf-87c2-c8de59745735
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 88de17e8c487d9a965f2e236edac064dc2fe4c7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601308"
---
# <a name="create-modify-and-drop-spatial-indexes"></a><span data-ttu-id="4f43d-102">Créer, modifier et supprimer les index spatiaux</span><span class="sxs-lookup"><span data-stu-id="4f43d-102">Create, Modify, and Drop Spatial Indexes</span></span>
  <span data-ttu-id="4f43d-103">Un index spatial peut effectuer plus efficacement certaines opérations sur une colonne du `geometry` type de `geography` données ou (une *colonne spatiale*).</span><span class="sxs-lookup"><span data-stu-id="4f43d-103">A spatial index can more efficiently perform certain operations on a column of the `geometry` or `geography` data type (a *spatial column*).</span></span> <span data-ttu-id="4f43d-104">Plusieurs index spatiaux peuvent être spécifiés sur une colonne spatiale.</span><span class="sxs-lookup"><span data-stu-id="4f43d-104">More than one spatial index can be specified on a spatial column.</span></span> <span data-ttu-id="4f43d-105">Cela peut s'avérer utile par exemple pour indexer différents paramètres de pavage dans une même colonne.</span><span class="sxs-lookup"><span data-stu-id="4f43d-105">This is useful, for example, for indexing different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="4f43d-106">Il existe plusieurs restrictions applicables à la création d'index spatiaux.</span><span class="sxs-lookup"><span data-stu-id="4f43d-106">There are a number of restrictions on creating spatial indexes.</span></span> <span data-ttu-id="4f43d-107">Pour plus d'informations, consultez [Restrictions sur les index spatiaux](#restrictions) dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4f43d-107">For more information, see [Restrictions on Spatial Indexes](#restrictions) in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f43d-108">Pour plus d’informations sur la relation entre les index spatiaux et les partitions et groupes de fichiers, consultez la section « Remarques » dans [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4f43d-108">For information about the relationship of spatial indexes to partition and to filegroups, see the "Remarks" section in [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
##  <a name="creating-modifying-and-dropping-spatial-indexes"></a><a name="creating"></a> <span data-ttu-id="4f43d-109">Création, modification et suppression d'index spatiaux</span><span class="sxs-lookup"><span data-stu-id="4f43d-109">Creating, Modifying, and Dropping Spatial Indexes</span></span>  
  
###  <a name="to-create-a-spatial-index"></a><a name="create"></a> <span data-ttu-id="4f43d-110">Pour créer un index spatial</span><span class="sxs-lookup"><span data-stu-id="4f43d-110">To create a spatial index</span></span>  
 <span data-ttu-id="4f43d-111">**Pour créer un index spatial à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4f43d-111">**To create a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="4f43d-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4f43d-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-spatial-index-transact-sql)  
  
 <span data-ttu-id="4f43d-113">**Pour créer un index spatial à l'aide de la boîte de dialogue Nouvel index dans Management Studio**</span><span class="sxs-lookup"><span data-stu-id="4f43d-113">**To create a spatial index by using the New Index dialog box in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-management-studio"></a><span data-ttu-id="4f43d-114">Pour créer un index spatial dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f43d-114">To create a spatial index in Management Studio</span></span>  
  
1.  <span data-ttu-id="4f43d-115">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="4f43d-115">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4f43d-116">Développez **Bases de données**, développez la base de données qui contient la table dotée de l'index spécifié, puis développez **Tables**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-116">Expand **Databases**, expand the database that contains the table with the specified index, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="4f43d-117">Développez la table pour laquelle vous souhaitez créer l'index.</span><span class="sxs-lookup"><span data-stu-id="4f43d-117">Expand the table for which you want to create the index.</span></span>  
  
4.  <span data-ttu-id="4f43d-118">Cliquez avec le bouton droit sur **Index** et sélectionnez **Nouvel index**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-118">Right-click **Indexes** and select **New Index**.</span></span>  
  
5.  <span data-ttu-id="4f43d-119">Dans le champ **Nom de l'index** , entrez un nom pour l'index.</span><span class="sxs-lookup"><span data-stu-id="4f43d-119">In the **Index name** field, enter a name for the index.</span></span>  
  
6.  <span data-ttu-id="4f43d-120">Dans la liste déroulante **Type d’index** , sélectionnez **Spatial**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-120">In the **Index type** drop-down list, select **Spatial**.</span></span>  
  
7.  <span data-ttu-id="4f43d-121">Pour spécifier la colonne spatiale à indexer, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-121">To specify the spatial column that you want to index, click **Add**.</span></span>  
  
8.  <span data-ttu-id="4f43d-122">Dans la boîte de dialogue **Sélectionner les colonnes à partir de** *\<table name>* , sélectionnez une colonne de type `geometry` ou `geography` en activant la case à cocher correspondante.</span><span class="sxs-lookup"><span data-stu-id="4f43d-122">In the **Select Columns from** *\<table name>* dialog box, select a column of type `geometry` or `geography` by selecting the corresponding check box.</span></span> <span data-ttu-id="4f43d-123">Toutes les autres colonnes spatiales deviennent alors impossibles à modifier.</span><span class="sxs-lookup"><span data-stu-id="4f43d-123">Any other spatial columns then become uneditable.</span></span> <span data-ttu-id="4f43d-124">Si vous souhaitez sélectionner une autre colonne spatiale, vous devez tout d'abord désactiver la colonne sélectionnée actuellement.</span><span class="sxs-lookup"><span data-stu-id="4f43d-124">If you want to select a different spatial column, you must first clear the currently selected column.</span></span> <span data-ttu-id="4f43d-125">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-125">When finished, click **OK**.</span></span>  
  
9. <span data-ttu-id="4f43d-126">Vérifiez votre sélection de colonne dans la grille **Colonnes clés d'index** .</span><span class="sxs-lookup"><span data-stu-id="4f43d-126">Verify your column selection in the **Index key columns** grid.</span></span>  
  
10. <span data-ttu-id="4f43d-127">Dans le volet **Sélectionner une page** de la boîte de dialogue **Propriétés de l'index** , cliquez sur **Spatial**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-127">In the **Select a page** pane of the **Index Properties** dialog box, click **Spatial**.</span></span>  
  
11. <span data-ttu-id="4f43d-128">Dans la page **Spatial** , spécifiez les valeurs que vous souhaitez utiliser pour les propriétés spatiales de l'index.</span><span class="sxs-lookup"><span data-stu-id="4f43d-128">On the **Spatial** page, specify the values that you want to use for the spatial properties of the index.</span></span>  
  
     <span data-ttu-id="4f43d-129">Lorsque vous créez un index sur une `geometry` colonne de type, vous devez spécifier les coordonnées **( *`X-min`* , *`Y-min`* )** et **( *`X-max`* , *`Y-max`* )** de la zone englobante.</span><span class="sxs-lookup"><span data-stu-id="4f43d-129">When creating an index on a `geometry` type column, you must specify the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="4f43d-130">Pour un index sur une `geography` colonne de type, les champs de cadre englobant sont en lecture seule après que vous avez spécifié le schéma de pavage de **grille géographique** , car le pavage de grille géographique n’utilise pas de cadre englobant.</span><span class="sxs-lookup"><span data-stu-id="4f43d-130">For an index on a `geography` type column, the bounding-box fields become read-only after you specify the **Geography grid** tessellation scheme, because geography grid tessellation does not use a bounding box.</span></span>  
  
     <span data-ttu-id="4f43d-131">Si vous le souhaitez, vous pouvez spécifier des valeurs autres que les valeurs par défaut pour le champ **Cellules par objet** et pour la densité de grille à tout niveau du schéma de pavage.</span><span class="sxs-lookup"><span data-stu-id="4f43d-131">Optionally, you can specify nondefault values for the **Cells Per Object** field and for the grid density at any level of the tessellation scheme.</span></span> <span data-ttu-id="4f43d-132">La quantité par défaut de cellules par objet est 16 pour [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] ou 8 pour [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] ou les versions supérieures, et la densité de grille par défaut est **Moyenne** pour [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f43d-132">The default number of cells per object is 16 for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or 8 for [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] or higher, and the default grid density is **Medium** for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span>  
  
     <span data-ttu-id="4f43d-133">Vous pouvez sélectionner GEOMETRY_AUTO_GRID ou GEOGRAPHY_AUTO_GRID pour le schéma de pavage dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f43d-133">You can select GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID for tessellation scheme in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4f43d-134">Lorsque GEOMETRY_AUTO_GRID ou GEOGRAPHY_AUTO_GRID est sélectionné, les options de densité de la grille Niveau 1, Niveau 2, Niveau 3 et Niveau 4 sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="4f43d-134">When GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID is selected, then Level 1, Level 2, Level 3, and Level 4 grid density options are disabled.</span></span>  
  
     <span data-ttu-id="4f43d-135">Pour plus d'informations sur ces propriétés, consultez [Index Properties F1 Help](../indexes/index-properties-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="4f43d-135">For more information about these properties, see [Index Properties F1 Help](../indexes/index-properties-f1-help.md).</span></span>  
  
12. <span data-ttu-id="4f43d-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-136">Click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f43d-137">Pour créer un autre index spatial sur la même colonne spatiale ou sur une colonne spatiale différente, répétez les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="4f43d-137">To create another spatial index on the same or a different spatial column, repeat the preceding steps.</span></span>  
  
  
 <span data-ttu-id="4f43d-138">**Pour créer un index spatial à l'aide du Concepteur de tables dans Management Studio**</span><span class="sxs-lookup"><span data-stu-id="4f43d-138">**To create a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-table-designer"></a><span data-ttu-id="4f43d-139">Pour créer un index spatial dans le Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="4f43d-139">To create a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="4f43d-140">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur la table pour laquelle vous souhaitez créer un index spatial, puis cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-140">In Object Explorer, right-click the table for which you want to create a spatial index, and then click **Design**.</span></span>  
  
     <span data-ttu-id="4f43d-141">La table s'ouvre dans le Concepteur de tables.</span><span class="sxs-lookup"><span data-stu-id="4f43d-141">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="4f43d-142">Sélectionnez une colonne `geometry` ou `geography` pour l'index.</span><span class="sxs-lookup"><span data-stu-id="4f43d-142">Select a `geometry` or `geography` column for the index.</span></span>  
  
3.  <span data-ttu-id="4f43d-143">Dans le menu **Concepteur de tables** , cliquez sur **Index spatial**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-143">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
4.  <span data-ttu-id="4f43d-144">Dans la boîte de dialogue **Index spatiaux** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-144">In the **Spatial Indexes** dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="4f43d-145">Sélectionnez le nouvel index dans la liste **Index spatial sélectionné** et, dans la grille située à droite, définissez les propriétés de l'index spatial.</span><span class="sxs-lookup"><span data-stu-id="4f43d-145">Select the new index in the **Selected Spatial Index** list, and in the grid to the right, set the properties for the spatial index.</span></span> <span data-ttu-id="4f43d-146">Pour plus d’informations sur les propriétés, consultez [Boîte de dialogue Index spatiaux &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4f43d-146">For information about the properties, see [Spatial Indexes Dialog Box &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
  
###  <a name="to-alter-a-spatial-index"></a><a name="alter"></a> <span data-ttu-id="4f43d-147">Pour modifier un index spatial</span><span class="sxs-lookup"><span data-stu-id="4f43d-147">To alter a spatial index</span></span>  
  
-   [<span data-ttu-id="4f43d-148">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4f43d-148">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4f43d-149">Pour modifier des options spécifiques à un index spatial, telles que BOUNDING_BOX ou GRID, vous pouvez utiliser une instruction CREATE SPATIAL INDEX qui spécifie DROP_EXISTING = ON ou supprimer l'index spatial et en créer un nouveau.</span><span class="sxs-lookup"><span data-stu-id="4f43d-149">To change options that are specific to a spatial index, such as BOUNDING_BOX or GRID, you can either use a CREATE SPATIAL INDEX statement that specifies DROP_EXISTING = ON, or drop the spatial index and create a new one.</span></span> <span data-ttu-id="4f43d-150">Pour obtenir un exemple, consultez [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4f43d-150">For an example, see [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
-   [<span data-ttu-id="4f43d-151">Modifier un index</span><span class="sxs-lookup"><span data-stu-id="4f43d-151">Modify an Index</span></span>](../indexes/modify-an-index.md)  
  
-   [<span data-ttu-id="4f43d-152">Déplacer un index existant dans un autre groupe de fichiers</span><span class="sxs-lookup"><span data-stu-id="4f43d-152">Move an Existing Index to a Different Filegroup</span></span>](../indexes/move-an-existing-index-to-a-different-filegroup.md)  
  
  
###  <a name="to-drop-a-spatial-index"></a><a name="drop"></a> <span data-ttu-id="4f43d-153">Pour supprimer un index spatial</span><span class="sxs-lookup"><span data-stu-id="4f43d-153">To drop a spatial index</span></span>  
 <span data-ttu-id="4f43d-154">**Pour supprimer un index spatial à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4f43d-154">**To drop a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="4f43d-155">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4f43d-155">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 <span data-ttu-id="4f43d-156">**Pour supprimer un index à l'aide de Management Studio**</span><span class="sxs-lookup"><span data-stu-id="4f43d-156">**To drop an index by using Management Studio**</span></span>  
 [<span data-ttu-id="4f43d-157">Suppression d'index</span><span class="sxs-lookup"><span data-stu-id="4f43d-157">Delete an Index</span></span>](../indexes/delete-an-index.md)  
  
 <span data-ttu-id="4f43d-158">**Pour supprimer un index spatial à l'aide du Concepteur de tables dans Management Studio**</span><span class="sxs-lookup"><span data-stu-id="4f43d-158">**To drop a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-drop-a-spatial-index-in-table-designer"></a><span data-ttu-id="4f43d-159">Pour supprimer un index spatial dans le Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="4f43d-159">To drop a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="4f43d-160">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur la table contenant l’index spatial que vous souhaitez supprimer et cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-160">In Object Explorer, right-click the table with the spatial index you want to delete and click **Design**.</span></span>  
  
     <span data-ttu-id="4f43d-161">La table s'ouvre dans le Concepteur de tables.</span><span class="sxs-lookup"><span data-stu-id="4f43d-161">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="4f43d-162">Dans le menu **Concepteur de tables** , cliquez sur **Index spatial**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-162">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
     <span data-ttu-id="4f43d-163">La boîte de dialogue **Index spatial** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="4f43d-163">The **Spatial Index** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="4f43d-164">Cliquez sur l'index que vous souhaitez supprimer dans la colonne **Index spatial sélectionné** .</span><span class="sxs-lookup"><span data-stu-id="4f43d-164">Click the index you want to delete in the **Selected Spatial Index** column.</span></span>  
  
4.  <span data-ttu-id="4f43d-165">Cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="4f43d-165">Click **Delete**.</span></span>  
  
  
##  <a name="restrictions-on-spatial-indexes"></a><a name="restrictions"></a> <span data-ttu-id="4f43d-166">Restrictions sur les index spatiaux</span><span class="sxs-lookup"><span data-stu-id="4f43d-166">Restrictions on Spatial Indexes</span></span>  
 <span data-ttu-id="4f43d-167">Un index spatial peut être créé uniquement sur une colonne de type `geometry` ou `geography`.</span><span class="sxs-lookup"><span data-stu-id="4f43d-167">A spatial index can be created only on a column of type `geometry` or `geography`.</span></span>  
  
### <a name="table-and-view-restrictions"></a><span data-ttu-id="4f43d-168">Restrictions sur les tables et les vues</span><span class="sxs-lookup"><span data-stu-id="4f43d-168">Table and View Restrictions</span></span>  
 <span data-ttu-id="4f43d-169">Les index spatiaux peuvent être définis uniquement sur une table dotée d'une clé primaire.</span><span class="sxs-lookup"><span data-stu-id="4f43d-169">Spatial indexes can be defined only on a table that has a primary key.</span></span> <span data-ttu-id="4f43d-170">Le nombre maximal de colonnes clés primaires sur la table est de 15.</span><span class="sxs-lookup"><span data-stu-id="4f43d-170">The maximum number of primary key columns on the table is 15.</span></span>  
  
 <span data-ttu-id="4f43d-171">La taille maximale des enregistrements de clés d'index est de 895 octets.</span><span class="sxs-lookup"><span data-stu-id="4f43d-171">The maximum size of index key records is 895 bytes.</span></span> <span data-ttu-id="4f43d-172">Les tailles supérieures génèrent une erreur.</span><span class="sxs-lookup"><span data-stu-id="4f43d-172">Larger sizes raise an error.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f43d-173">Les métadonnées de clé primaire ne peuvent pas être modifiées pendant qu'un index spatial est défini sur une table.</span><span class="sxs-lookup"><span data-stu-id="4f43d-173">Primary key metadata cannot be changed while a spatial index is defined on a table.</span></span>  
  
 <span data-ttu-id="4f43d-174">Des index spatiaux ne peuvent pas être spécifiés sur des vues indexées.</span><span class="sxs-lookup"><span data-stu-id="4f43d-174">Spatial indexes cannot be specified on indexed views.</span></span>  
  
### <a name="multiple-spatial-index-restrictions"></a><span data-ttu-id="4f43d-175">Restrictions sur plusieurs index spatiaux</span><span class="sxs-lookup"><span data-stu-id="4f43d-175">Multiple Spatial Index Restrictions</span></span>  
 <span data-ttu-id="4f43d-176">Vous pouvez créer jusqu'à 249 index spatiaux sur les colonnes spatiales dans une table prise en charge.</span><span class="sxs-lookup"><span data-stu-id="4f43d-176">You can create up to 249 spatial indexes on any of the spatial columns in a supported table.</span></span> <span data-ttu-id="4f43d-177">La création de plusieurs index spatiaux sur la même colonne spatiale peut être utile, par exemple pour indexer des paramètres de pavage différents dans une même colonne.</span><span class="sxs-lookup"><span data-stu-id="4f43d-177">Creating more than one spatial index on the same spatial column can be useful, for example, to index different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="4f43d-178">Vous pouvez créer un seul index spatial à la fois.</span><span class="sxs-lookup"><span data-stu-id="4f43d-178">You can create only one spatial index at a time.</span></span>  
  
### <a name="spatial-indexes-and-process-parallelism"></a><span data-ttu-id="4f43d-179">Index spatiaux et parallélisme de processus</span><span class="sxs-lookup"><span data-stu-id="4f43d-179">Spatial Indexes and Process Parallelism</span></span>  
 <span data-ttu-id="4f43d-180">Une construction d'index peut utiliser le parallélisme de processus disponible.</span><span class="sxs-lookup"><span data-stu-id="4f43d-180">An index build can use available process parallelism.</span></span>  
  
### <a name="version-restrictions"></a><span data-ttu-id="4f43d-181">Restrictions de version</span><span class="sxs-lookup"><span data-stu-id="4f43d-181">Version Restrictions</span></span>  
 <span data-ttu-id="4f43d-182">Les pavages spatiaux introduits dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] ne peuvent pas être répliqués dans [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] ou [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f43d-182">Spatial tessellations introduced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] cannot be replicated to [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="4f43d-183">Vous devez utiliser les pavages spatiaux [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] ou [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] pour les index spatiaux lorsqu'une compatibilité descendante avec les bases de données [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] ou [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] est une condition obligatoire.</span><span class="sxs-lookup"><span data-stu-id="4f43d-183">You must use [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] spatial tessellations for spatial indexes when backward compatibility with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] databases is a requirement.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="4f43d-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f43d-184">See Also</span></span>  
 [<span data-ttu-id="4f43d-185">Vue d’ensemble des index spatiaux</span><span class="sxs-lookup"><span data-stu-id="4f43d-185">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
  
  
