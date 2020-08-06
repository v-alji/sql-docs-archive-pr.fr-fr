---
title: Propriétés de l’index – Aide (F1) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.storage.f1
- sql12.swb.indexproperties.columns.f1
- sql12.swb.indexproperties.partitions.f1
- sql12.swb.indexproperties.general.f1
- sql12.swb.indexproperties.filter.f1
- sql12.swb.indexproperties.options.f1
- sql12.swb.indexproperties.spatial.f1
ms.assetid: 45efd81a-3796-4b04-b0cc-f3deec94c733
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 390a63d21dc72e052017f2d30b061d71de863bc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709403"
---
# <a name="index-properties-f1-help"></a><span data-ttu-id="e28d5-102">Propriétés de l'index – Aide (F1)</span><span class="sxs-lookup"><span data-stu-id="e28d5-102">Index Properties F1 Help</span></span>
  <span data-ttu-id="e28d5-103">Les sections de cette rubrique font référence aux différentes propriétés d'index disponibles au moyen des boîtes de dialogue [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e28d5-103">The sections in this topic refer to various index properties that are available by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialogs.</span></span>  
  
 <span data-ttu-id="e28d5-104">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="e28d5-104">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="e28d5-105">Propriétés de l'index (page Général)</span><span class="sxs-lookup"><span data-stu-id="e28d5-105">Index Properties General Page</span></span>](#General)  
  
 [<span data-ttu-id="e28d5-106">Boîte de dialogue Sélectionner les colonnes à partir de (Propriétés de l'index)</span><span class="sxs-lookup"><span data-stu-id="e28d5-106">Select (Index) Columns Dialog Box</span></span>](#Columns)  
  
 [<span data-ttu-id="e28d5-107">Propriétés de l'index (page Stockage)</span><span class="sxs-lookup"><span data-stu-id="e28d5-107">Index Properties Storage Page</span></span>](#Storage)  
  
 [<span data-ttu-id="e28d5-108">Propriétés de l'index (page Spatial)</span><span class="sxs-lookup"><span data-stu-id="e28d5-108">Index Properties Spatial Page</span></span>](#Spatial)  
  
 [<span data-ttu-id="e28d5-109">Propriétés de l'index (page Filtre)</span><span class="sxs-lookup"><span data-stu-id="e28d5-109">Index Properties Filter Page</span></span>](#Filter)  
  
##  <a name="index-properties-general-page"></a><a name="General"></a> <span data-ttu-id="e28d5-110">Propriétés de l'index (page Général)</span><span class="sxs-lookup"><span data-stu-id="e28d5-110">Index Properties General Page</span></span>  
 <span data-ttu-id="e28d5-111">La page Général vous permet d'afficher et de modifier les propriétés de l'index de la table ou de la vue sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e28d5-111">Use the General page to view or modify index properties for the selected table or view.</span></span> <span data-ttu-id="e28d5-112">Les options de chaque page peuvent changer en fonction du type d'index sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e28d5-112">The options for each page may change based on the type of index selected.</span></span>  
  
 <span data-ttu-id="e28d5-113">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="e28d5-113">**Table name**</span></span>  
 <span data-ttu-id="e28d5-114">Affiche le nom de la table ou de la vue sur laquelle l'index a été créé.</span><span class="sxs-lookup"><span data-stu-id="e28d5-114">Displays the name of the table or view that the index was created on.</span></span> <span data-ttu-id="e28d5-115">Ce champ est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e28d5-115">This field is read-only.</span></span> <span data-ttu-id="e28d5-116">Pour sélectionner une table différente, fermez la page Propriétés de l'index, sélectionnez la table appropriée, puis ouvrez de nouveau la page Propriétés de l'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-116">To select a different table, close the Index Properties page, select the correct table, and then open the Index Properties page again.</span></span>  
  
 <span data-ttu-id="e28d5-117">Des index spatiaux ne peuvent pas être spécifiés sur des vues indexées.</span><span class="sxs-lookup"><span data-stu-id="e28d5-117">Spatial indexes cannot be specified on indexed views.</span></span> <span data-ttu-id="e28d5-118">Les index spatiaux peuvent être uniquement définis pour une table dotée d'une clé primaire.</span><span class="sxs-lookup"><span data-stu-id="e28d5-118">Spatial indexes can be defined only for a table that has a primary key.</span></span> <span data-ttu-id="e28d5-119">Le nombre maximal de colonnes clés primaires sur la table est de 15.</span><span class="sxs-lookup"><span data-stu-id="e28d5-119">The maximum number of primary key columns on the table is 15.</span></span> <span data-ttu-id="e28d5-120">La taille par ligne combinée des colonnes clés primaires est limitée à 895 octets.</span><span class="sxs-lookup"><span data-stu-id="e28d5-120">The combined per-row size of the primary-key columns is limited to a maximum of 895 bytes.</span></span>  
  
 <span data-ttu-id="e28d5-121">**Nom de l'index**</span><span class="sxs-lookup"><span data-stu-id="e28d5-121">**Index name**</span></span>  
 <span data-ttu-id="e28d5-122">Affiche le nom de l'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-122">Displays the name of the index.</span></span> <span data-ttu-id="e28d5-123">Ce champ est en lecture seule pour un index existant.</span><span class="sxs-lookup"><span data-stu-id="e28d5-123">This field is read-only for an existing index.</span></span> <span data-ttu-id="e28d5-124">Permet de taper le nom de l'index, si vous en créez un nouveau.</span><span class="sxs-lookup"><span data-stu-id="e28d5-124">When creating a new index, type the name of the index.</span></span>  
  
 <span data-ttu-id="e28d5-125">**Type d'index**</span><span class="sxs-lookup"><span data-stu-id="e28d5-125">**Index type**</span></span>  
 <span data-ttu-id="e28d5-126">Indique le type d'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-126">Indicates the type of index.</span></span> <span data-ttu-id="e28d5-127">Pour les nouveaux index, indique le type d'index sélectionné lors de l'ouverture de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e28d5-127">For new indexes, indicates the type of index selected when opening the dialog box.</span></span> <span data-ttu-id="e28d5-128">Les index peuvent être : **Cluster**, **Non cluster**, **XML primaire**, **XML secondaire**, **Spatial**, **Columnstore cluster** ou **Columnstore non cluster**.</span><span class="sxs-lookup"><span data-stu-id="e28d5-128">Indexes can be: **Clustered**, **Nonclustered**, **Primary XML**, **Secondary XML**, **Spatial**, **Clustered columnstore**, or **Nonclustered Columnstore**.</span></span>  
  
 <span data-ttu-id="e28d5-129">**Remarque** Un seul index cluster est autorisé pour chaque table.</span><span class="sxs-lookup"><span data-stu-id="e28d5-129">**Note** Only one clustered index is allowed for each table.</span></span> <span data-ttu-id="e28d5-130">Un seul index columnstore optimisé en mémoire xVelocity est autorisé pour chaque table.</span><span class="sxs-lookup"><span data-stu-id="e28d5-130">Only one xVelocity memory optimized columnstore index is allowed for each table.</span></span>  
  
 <span data-ttu-id="e28d5-131">**Unique**</span><span class="sxs-lookup"><span data-stu-id="e28d5-131">**Unique**</span></span>  
 <span data-ttu-id="e28d5-132">Activez cette case à cocher pour que l'index soit unique.</span><span class="sxs-lookup"><span data-stu-id="e28d5-132">Selecting this check box makes the index unique.</span></span> <span data-ttu-id="e28d5-133">Deux lignes quelconques ne peuvent pas avoir la même valeur d'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-133">No two rows are permitted to have the same index value.</span></span> <span data-ttu-id="e28d5-134">Par défaut, cette case est décochée.</span><span class="sxs-lookup"><span data-stu-id="e28d5-134">By default, this check box is cleared.</span></span> <span data-ttu-id="e28d5-135">Lors de la modification d'un index existant, la création d'index échoue si deux lignes ont la même valeur.</span><span class="sxs-lookup"><span data-stu-id="e28d5-135">When modifying an existing index, index creation will fail if two rows have the same value.</span></span> <span data-ttu-id="e28d5-136">Pour les colonnes autorisant les valeurs NULL, un index unique autorise une seule valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="e28d5-136">For columns where NULL is permitted, a unique index permits one NULL value.</span></span>  
  
 <span data-ttu-id="e28d5-137">Si vous sélectionnez **Spatial** dans le champ **Type d'index** , la case à cocher **Unique** est estompée.</span><span class="sxs-lookup"><span data-stu-id="e28d5-137">If you select **Spatial** in the **Index type** field, the **Unique** check box is dimmed.</span></span>  
  
 <span data-ttu-id="e28d5-138">**Colonnes clés d'index**</span><span class="sxs-lookup"><span data-stu-id="e28d5-138">**Index key columns**</span></span>  
 <span data-ttu-id="e28d5-139">Ajoutez les colonnes de votre choix dans la grille **Colonnes de clés d’index** .</span><span class="sxs-lookup"><span data-stu-id="e28d5-139">Add the desired columns to the **Index key columns** grid.</span></span> <span data-ttu-id="e28d5-140">Lorsque plusieurs colonnes sont ajoutées, elles doivent être répertoriées dans l'ordre souhaité.</span><span class="sxs-lookup"><span data-stu-id="e28d5-140">When more than one column is added, the columns must be listed in the order desired.</span></span> <span data-ttu-id="e28d5-141">L'ordre des colonnes dans un index peut avoir un impact important sur les performances de l'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-141">The column order in an index can have a great impact on the index performance.</span></span>  
  
 <span data-ttu-id="e28d5-142">Un maximum de 16 colonnes peuvent être utilisées dans un index composé individuel.</span><span class="sxs-lookup"><span data-stu-id="e28d5-142">No more than 16 columns can participate in a single composite index.</span></span> <span data-ttu-id="e28d5-143">Si la valeur est supérieure à 16 colonnes, consultez la section traitant des colonnes incluses à la fin de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="e28d5-143">For greater than 16 columns, see included columns at the end of this topic.</span></span>  
  
 <span data-ttu-id="e28d5-144">Un index spatial peut être uniquement défini sur une colonne unique qui contient un type de données spatiales (une *colonne spatiale*).</span><span class="sxs-lookup"><span data-stu-id="e28d5-144">A spatial index can be defined only on a single column that contains a spatial data type (a *spatial column*).</span></span>  
  
 <span data-ttu-id="e28d5-145">**Nom**</span><span class="sxs-lookup"><span data-stu-id="e28d5-145">**Name**</span></span>  
 <span data-ttu-id="e28d5-146">Affiche le nom de la colonne utilisée dans la clé d'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-146">Displays the name of the column that participates in the index key.</span></span>  
  
 <span data-ttu-id="e28d5-147">**Ordre de tri**</span><span class="sxs-lookup"><span data-stu-id="e28d5-147">**Sort Order**</span></span>  
 <span data-ttu-id="e28d5-148">Spécifie le sens du tri de la colonne d’index sélectionnée, **Croissant** ou **Décroissant**.</span><span class="sxs-lookup"><span data-stu-id="e28d5-148">Specifies the sort direction of the selected index column, either **Ascending** or **Descending**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e28d5-149">Si le type d’index est **XML primaire** ou **Spatial**, cette colonne n’apparaît pas dans la table.</span><span class="sxs-lookup"><span data-stu-id="e28d5-149">If the index type is **Primary XML** or **Spatial**, this column does not appear in the table.</span></span>  
  
 <span data-ttu-id="e28d5-150">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e28d5-150">**Data Type**</span></span>  
 <span data-ttu-id="e28d5-151">Affiche les informations de type de données.</span><span class="sxs-lookup"><span data-stu-id="e28d5-151">Displays the data type information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e28d5-152">Si la colonne de table est une colonne calculée, le paramètre **Type de données** a la valeur « colonne calculée ».</span><span class="sxs-lookup"><span data-stu-id="e28d5-152">If the table column is a computed column, **Data type** displays "computed column."</span></span>  
  
 <span data-ttu-id="e28d5-153">**Taille**</span><span class="sxs-lookup"><span data-stu-id="e28d5-153">**Size**</span></span>  
 <span data-ttu-id="e28d5-154">Affiche le nombre maximal d'octets requis pour stocker le type de données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="e28d5-154">Displays the maximum number of bytes required to store the column data type.</span></span> <span data-ttu-id="e28d5-155">Affiche zéro (0) pour une colonne spatiale ou XML.</span><span class="sxs-lookup"><span data-stu-id="e28d5-155">Displays zero (0) for a spatial or XML column.</span></span>  
  
 <span data-ttu-id="e28d5-156">**Identité**</span><span class="sxs-lookup"><span data-stu-id="e28d5-156">**Identity**</span></span>  
 <span data-ttu-id="e28d5-157">Indique si la colonne utilisée dans la clé d'index est une colonne d'identité.</span><span class="sxs-lookup"><span data-stu-id="e28d5-157">Displays whether the column participating in the index key is an identity column.</span></span>  
  
 <span data-ttu-id="e28d5-158">**Autoriser les valeurs NULL**</span><span class="sxs-lookup"><span data-stu-id="e28d5-158">**Allow NULLs**</span></span>  
 <span data-ttu-id="e28d5-159">Indique si la colonne utilisée dans la clé d'index autorise le stockage de valeurs NULL dans la colonne de la table ou de la vue.</span><span class="sxs-lookup"><span data-stu-id="e28d5-159">Displays whether the column participating in the index key allows NULL values to be stored in the table or view column.</span></span>  
  
 <span data-ttu-id="e28d5-160">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="e28d5-160">**Add**</span></span>  
 <span data-ttu-id="e28d5-161">Ajoute une colonne à la clé d'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-161">Adds a column to the index key.</span></span> <span data-ttu-id="e28d5-162">Sélectionnez des colonnes de table dans la boîte de dialogue **Sélectionnez les colonnes à partir de** *\<table name>* qui s'affiche lorsque vous cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e28d5-162">Select table columns from the **Select Columns from** *\<table name>* dialog box that appears when you click **Add**.</span></span> <span data-ttu-id="e28d5-163">Pour un index spatial, lorsque vous sélectionnez une colonne, ce bouton est estompé.</span><span class="sxs-lookup"><span data-stu-id="e28d5-163">For a spatial index, after you select one column, this button is dimmed.</span></span>  
  
 <span data-ttu-id="e28d5-164">**Remove**</span><span class="sxs-lookup"><span data-stu-id="e28d5-164">**Remove**</span></span>  
 <span data-ttu-id="e28d5-165">Supprime la colonne sélectionnée de la clé d'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-165">Removes the selected column from participation in the index key.</span></span>  
  
 <span data-ttu-id="e28d5-166">**Monter**</span><span class="sxs-lookup"><span data-stu-id="e28d5-166">**Move Up**</span></span>  
 <span data-ttu-id="e28d5-167">Déplace la colonne sélectionnée vers le haut dans la grille de clé d'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-167">Moves the selected column up in the index key grid.</span></span>  
  
 <span data-ttu-id="e28d5-168">**Descendre**</span><span class="sxs-lookup"><span data-stu-id="e28d5-168">**Move Down**</span></span>  
 <span data-ttu-id="e28d5-169">Déplace la colonne sélectionnée vers le bas dans la grille de clé d'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-169">Moves the selected column down in the index key grid.</span></span>  
  
 <span data-ttu-id="e28d5-170">**Colonnes columnstore**</span><span class="sxs-lookup"><span data-stu-id="e28d5-170">**Columnstore columns**</span></span>  
 <span data-ttu-id="e28d5-171">Cliquez sur **Ajouter** pour sélectionner des colonnes pour l’index columnstore.</span><span class="sxs-lookup"><span data-stu-id="e28d5-171">Click **Add** to select columns for the columnstore index.</span></span> <span data-ttu-id="e28d5-172">Pour connaître les limitations sur un index columnstore, consultez [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e28d5-172">For limitations on a columnstore index, see [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span></span>  
  
 <span data-ttu-id="e28d5-173">**Colonnes incluses**</span><span class="sxs-lookup"><span data-stu-id="e28d5-173">**Included columns**</span></span>  
 <span data-ttu-id="e28d5-174">Inclut des colonnes non-clés dans l'index non cluster.</span><span class="sxs-lookup"><span data-stu-id="e28d5-174">Include nonkey columns in the nonclustered index.</span></span> <span data-ttu-id="e28d5-175">Cette option vous permet de contourner les limites actuelles de l'index relatives à la taille totale d'une clé d'index et au nombre maximal de colonnes pouvant faire partie d'une clé d'index, en ajoutant des colonnes en tant que colonnes non-clés au niveau feuille de l'index non cluster.</span><span class="sxs-lookup"><span data-stu-id="e28d5-175">This option allows you to bypass the current index limits on the total size of an index key and the maximum number of columns participating in an index key by adding columns as nonkey columns in the leaf level of the nonclustered index.</span></span> <span data-ttu-id="e28d5-176">Pour plus d’informations, consultez [Créer des index avec colonnes incluses](create-indexes-with-included-columns.md)</span><span class="sxs-lookup"><span data-stu-id="e28d5-176">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md)</span></span>  
  
##  <a name="select-index-columns-dialog-box"></a><a name="Columns"></a> <span data-ttu-id="e28d5-177">Boîte de dialogue Sélectionner les colonnes à partir de (Propriétés de l'index)</span><span class="sxs-lookup"><span data-stu-id="e28d5-177">Select (Index) Columns Dialog Box</span></span>  
 <span data-ttu-id="e28d5-178">Utilisez cette page pour ajouter des colonnes à la page **Propriétés de l'index (page Général)** lors de la création ou de la modification d'un index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-178">Use this page to add columns to the **Index Properties General** page when creating or modifying an index.</span></span>  
  
 <span data-ttu-id="e28d5-179">**Case à cocher**</span><span class="sxs-lookup"><span data-stu-id="e28d5-179">**Check box**</span></span>  
 <span data-ttu-id="e28d5-180">Activez pour ajouter des colonnes.</span><span class="sxs-lookup"><span data-stu-id="e28d5-180">Select to add columns.</span></span>  
  
 <span data-ttu-id="e28d5-181">**Nom**</span><span class="sxs-lookup"><span data-stu-id="e28d5-181">**Name**</span></span>  
 <span data-ttu-id="e28d5-182">Nom de la colonne.</span><span class="sxs-lookup"><span data-stu-id="e28d5-182">Name of the column.</span></span>  
  
 <span data-ttu-id="e28d5-183">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e28d5-183">**Data Type**</span></span>  
 <span data-ttu-id="e28d5-184">Type de données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="e28d5-184">The data type of the column.</span></span>  
  
 <span data-ttu-id="e28d5-185">**Octets**</span><span class="sxs-lookup"><span data-stu-id="e28d5-185">**Bytes**</span></span>  
 <span data-ttu-id="e28d5-186">Taille de la colonne en octets.</span><span class="sxs-lookup"><span data-stu-id="e28d5-186">The size of the column in bytes.</span></span>  
  
 <span data-ttu-id="e28d5-187">**Identité**</span><span class="sxs-lookup"><span data-stu-id="e28d5-187">**Identity**</span></span>  
 <span data-ttu-id="e28d5-188">Affiche **Oui** pour les colonnes d’identité et **Non** pour les autres.</span><span class="sxs-lookup"><span data-stu-id="e28d5-188">Displays **Yes** for identity columns, and **No** when the column is not an identity column.</span></span>  
  
 <span data-ttu-id="e28d5-189">**Null autorisé**</span><span class="sxs-lookup"><span data-stu-id="e28d5-189">**Allow Nulls**</span></span>  
 <span data-ttu-id="e28d5-190">Affiche **Oui** si la définition de table autorise la présence de valeurs Null dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="e28d5-190">Displays **Yes** when the table definition allows null values for the column.</span></span> <span data-ttu-id="e28d5-191">Affiche **Non** si la définition de la table interdit la présence de valeurs Null dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="e28d5-191">Displays **No** when the table definition does not allow nulls for the column.</span></span>  
  
##  <a name="storage-page-options"></a><a name="Storage"></a> <span data-ttu-id="e28d5-192">Options (page Stockage)</span><span class="sxs-lookup"><span data-stu-id="e28d5-192">Storage Page Options</span></span>  
 <span data-ttu-id="e28d5-193">Utilisez cette page pour consulter ou modifier les propriétés de groupe de fichiers ou de schéma de partition pour l'index sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e28d5-193">Use this page to view or modify filegroup or partition scheme properties for the selected index.</span></span> <span data-ttu-id="e28d5-194">Affiche uniquement les options relatives au type d'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-194">Only shows options related to the type of index.</span></span>  
  
 <span data-ttu-id="e28d5-195">**Groupe de fichiers**</span><span class="sxs-lookup"><span data-stu-id="e28d5-195">**Filegroup**</span></span>  
 <span data-ttu-id="e28d5-196">Stocke l'index dans le groupe de fichiers spécifié.</span><span class="sxs-lookup"><span data-stu-id="e28d5-196">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="e28d5-197">La liste répertorie uniquement les groupes de fichiers standard (row).</span><span class="sxs-lookup"><span data-stu-id="e28d5-197">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="e28d5-198">Le groupe de fichiers PRIMARY de la base de données est sélectionné par défaut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e28d5-198">The default list selection is the PRIMARY filegroup of the database.</span></span> <span data-ttu-id="e28d5-199">Pour plus d'informations, consultez [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="e28d5-199">For more information, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
 <span data-ttu-id="e28d5-200">**Groupe de fichiers Filestream**</span><span class="sxs-lookup"><span data-stu-id="e28d5-200">**Filestream filegroup**</span></span>  
 <span data-ttu-id="e28d5-201">Spécifie le groupe de fichiers pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e28d5-201">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="e28d5-202">Cette liste affiche uniquement des groupes de fichiers FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e28d5-202">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="e28d5-203">Le groupe de fichiers sélectionné par défaut dans la liste est le groupe PRIMARY FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e28d5-203">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span> <span data-ttu-id="e28d5-204">Pour plus d’informations, consultez [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e28d5-204">For more information, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="e28d5-205">**Schéma de partition**</span><span class="sxs-lookup"><span data-stu-id="e28d5-205">**Partition scheme**</span></span>  
 <span data-ttu-id="e28d5-206">Stocke l'index dans un schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="e28d5-206">Stores the index in a partition scheme.</span></span> <span data-ttu-id="e28d5-207">En cliquant sur **Schéma de partition** , vous activez la grille ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e28d5-207">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="e28d5-208">Le schéma de partition sélectionné par défaut dans la liste est celui qui est utilisé pour stocker les données de la table.</span><span class="sxs-lookup"><span data-stu-id="e28d5-208">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="e28d5-209">Si vous sélectionnez un autre schéma de partition dans la liste, les informations affichées dans la grille sont actualisées.</span><span class="sxs-lookup"><span data-stu-id="e28d5-209">When you select a different partition scheme in the list, the information in the grid is updated.</span></span> <span data-ttu-id="e28d5-210">Pour plus d’informations, consultez [Tables et index partitionnés](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e28d5-210">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="e28d5-211">L'option Schéma de partition n'est pas disponible s'il n'y a pas de schémas de partition dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e28d5-211">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="e28d5-212">**Schéma de partition Filestream**</span><span class="sxs-lookup"><span data-stu-id="e28d5-212">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="e28d5-213">Spécifie le schéma de partition utilisé pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e28d5-213">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="e28d5-214">Ce schéma de partition doit être symétrique avec celui spécifié dans l'option **Schéma de partition** .</span><span class="sxs-lookup"><span data-stu-id="e28d5-214">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="e28d5-215">Si la table n'est pas partitionnée, le champ est vide.</span><span class="sxs-lookup"><span data-stu-id="e28d5-215">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="e28d5-216">**Paramètre du schéma de partition**</span><span class="sxs-lookup"><span data-stu-id="e28d5-216">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="e28d5-217">Affiche le nom de la colonne qui participe au schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="e28d5-217">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="e28d5-218">**Colonne de table**</span><span class="sxs-lookup"><span data-stu-id="e28d5-218">**Table Column**</span></span>  
 <span data-ttu-id="e28d5-219">Sélectionnez la table ou vue à mapper avec le schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="e28d5-219">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="e28d5-220">**Type de données de la colonne**</span><span class="sxs-lookup"><span data-stu-id="e28d5-220">**Column Data Type**</span></span>  
 <span data-ttu-id="e28d5-221">Affiche des informations sur les types de données figurant dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="e28d5-221">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e28d5-222">Si la colonne de table est une colonne calculée, **Type de données de la colonne** contient la mention « colonne calculée ».</span><span class="sxs-lookup"><span data-stu-id="e28d5-222">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="e28d5-223">**Autoriser le traitement en ligne des instructions DML lors du déplacement de l'index**</span><span class="sxs-lookup"><span data-stu-id="e28d5-223">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="e28d5-224">Permet aux utilisateurs d'accéder à la table sous-jacente ou aux données des index cluster et à tous les index non-cluster associés pendant l'opération d'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-224">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span> <span data-ttu-id="e28d5-225">Pour plus d'informations, consultez [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="e28d5-225">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e28d5-226">Cette option n'est pas disponible pour les index XML ou si l'index est un index cluster désactivé.</span><span class="sxs-lookup"><span data-stu-id="e28d5-226">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="e28d5-227">**Définir le degré maximal de parallélisme**</span><span class="sxs-lookup"><span data-stu-id="e28d5-227">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="e28d5-228">Limite le nombre de processeurs à utiliser pendant l'exécution des plans parallèles.</span><span class="sxs-lookup"><span data-stu-id="e28d5-228">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="e28d5-229">La valeur par défaut est 0, indiquant que le nombre réel de processeurs disponibles est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e28d5-229">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="e28d5-230">Spécifier la valeur 1 supprime la génération d'un plan parallèle ; spécifier une valeur supérieure à 1 limite le nombre maximal de processeurs utilisés au cours de l'exécution d'une requête simple.</span><span class="sxs-lookup"><span data-stu-id="e28d5-230">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="e28d5-231">Cette option est disponible seulement si la boîte de dialogue est dans l'état **Reconstruire** ou **Recréer** .</span><span class="sxs-lookup"><span data-stu-id="e28d5-231">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span> <span data-ttu-id="e28d5-232">Pour plus d'informations, consultez [Définir l'option max degree of parallelism pour des performances optimales](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span><span class="sxs-lookup"><span data-stu-id="e28d5-232">For more information, see [Set the Max Degree of Parallelism Option for Optimal Performance](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e28d5-233">Si une valeur supérieure au nombre d'UC disponibles est spécifiée, le nombre réel d'UC est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e28d5-233">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="spatial-page-index-options"></a><a name="Spatial"></a> <span data-ttu-id="e28d5-234">Options de l'index (page Spatial)</span><span class="sxs-lookup"><span data-stu-id="e28d5-234">Spatial Page Index Options</span></span>  
 <span data-ttu-id="e28d5-235">Utilisez la page **Spatial** pour afficher ou spécifier les valeurs des propriétés spatiales.</span><span class="sxs-lookup"><span data-stu-id="e28d5-235">Use the **Spatial** page to view or specify the values of the spatial properties.</span></span> <span data-ttu-id="e28d5-236">Pour plus d’informations, consultez [Données spatiales &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e28d5-236">For more information, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
### <a name="bounding-box"></a><span data-ttu-id="e28d5-237">Cadre englobant</span><span class="sxs-lookup"><span data-stu-id="e28d5-237">Bounding Box</span></span>  
 <span data-ttu-id="e28d5-238">Le *cadre englobant* est le périmètre de la grille de niveau supérieur d’un plan géométrique.</span><span class="sxs-lookup"><span data-stu-id="e28d5-238">The *bounding box* is the perimeter of the top-level grid of a geometric plane.</span></span> <span data-ttu-id="e28d5-239">Les paramètres du cadre englobant existent uniquement dans le pavage de la grille géométrique.</span><span class="sxs-lookup"><span data-stu-id="e28d5-239">The bounding-box parameters exist only in the geometry grid tessellation.</span></span> <span data-ttu-id="e28d5-240">Ces paramètres sont indisponibles si le **Schéma de pavage** est une **Grille géographique**.</span><span class="sxs-lookup"><span data-stu-id="e28d5-240">These parameters are unavailable if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="e28d5-241">Le panneau affiche les coordonnées **( *`X-min`* , *`Y-min`* )** et **( *`X-max`* , *`Y-max`* )** de la zone englobante.</span><span class="sxs-lookup"><span data-stu-id="e28d5-241">The panel displays the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="e28d5-242">Il n'y a pas de valeurs de coordonnées par défaut.</span><span class="sxs-lookup"><span data-stu-id="e28d5-242">There are no default coordinate values.</span></span> <span data-ttu-id="e28d5-243">Par conséquent, lorsque vous créez un index spatial sur une colonne de type `geometry`, vous devez spécifier les valeurs des coordonnées.</span><span class="sxs-lookup"><span data-stu-id="e28d5-243">Therefore, when you are creating a new spatial index on a `geometry` type column, you must specify the coordinate values.</span></span>  
  
 `X-min`  
 <span data-ttu-id="e28d5-244">Coordonnée X de l'angle inférieur gauche du cadre englobant.</span><span class="sxs-lookup"><span data-stu-id="e28d5-244">The X-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `Y-min`  
 <span data-ttu-id="e28d5-245">Coordonnée Y de l'angle inférieur gauche du cadre englobant.</span><span class="sxs-lookup"><span data-stu-id="e28d5-245">The Y-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `X-max`  
 <span data-ttu-id="e28d5-246">Coordonnée X de l'angle supérieur droit du cadre englobant.</span><span class="sxs-lookup"><span data-stu-id="e28d5-246">The X-coordinate of the upper-right corner of the bounding box.</span></span>  
  
 `Y-max`  
 <span data-ttu-id="e28d5-247">Coordonnée Y de l'angle supérieur droit du cadre englobant.</span><span class="sxs-lookup"><span data-stu-id="e28d5-247">The Y-coordinate of upper-right corner of the bounding box.</span></span>  
  
### <a name="general"></a><span data-ttu-id="e28d5-248">Général</span><span class="sxs-lookup"><span data-stu-id="e28d5-248">General</span></span>  
 <span data-ttu-id="e28d5-249">**Schéma de pavage**</span><span class="sxs-lookup"><span data-stu-id="e28d5-249">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="e28d5-250">Indique le schéma de pavage de l'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-250">Indicates the tessellation scheme of the index.</span></span> <span data-ttu-id="e28d5-251">Les schémas de pavage pris en charge se présentent comme suit.</span><span class="sxs-lookup"><span data-stu-id="e28d5-251">The supported tessellation schemes are as follows.</span></span>  
  
 <span data-ttu-id="e28d5-252">**Grille géométrique**</span><span class="sxs-lookup"><span data-stu-id="e28d5-252">**Geometry grid**</span></span>  
 <span data-ttu-id="e28d5-253">Spécifie le schéma de pavage de la grille géométrique qui s'applique à une colonne du type de données `geometry`.</span><span class="sxs-lookup"><span data-stu-id="e28d5-253">Specifies the geometry grid tessellation scheme, which applies to a column of the `geometry` data type.</span></span>  
  
 <span data-ttu-id="e28d5-254">**Grille automatique géométrique**</span><span class="sxs-lookup"><span data-stu-id="e28d5-254">**Geometry Auto grid**</span></span>  
 <span data-ttu-id="e28d5-255">Cette option est activée pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quand le niveau de compatibilité de la base de données a la valeur 110 ou une valeur supérieure.</span><span class="sxs-lookup"><span data-stu-id="e28d5-255">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="e28d5-256">**Grille géographique**</span><span class="sxs-lookup"><span data-stu-id="e28d5-256">**Geography grid**</span></span>  
 <span data-ttu-id="e28d5-257">Spécifie le schéma de pavage de la grille géographique qui s’applique à une colonne du type de données **geography** .</span><span class="sxs-lookup"><span data-stu-id="e28d5-257">Specifies the geography grid tessellation scheme, which applies to a column of the **geography** data type.</span></span>  
  
 <span data-ttu-id="e28d5-258">**Grille automatique géographique**</span><span class="sxs-lookup"><span data-stu-id="e28d5-258">**Geography Auto grid**</span></span>  
 <span data-ttu-id="e28d5-259">Cette option est activée pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quand le niveau de compatibilité de la base de données a la valeur 110 ou une valeur supérieure.</span><span class="sxs-lookup"><span data-stu-id="e28d5-259">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="e28d5-260">Pour plus d’informations sur la façon dont [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implémente le pavage, consultez [Données spatiales &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e28d5-260">For information about how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implements tessellation, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="e28d5-261">**Cellules par objet**</span><span class="sxs-lookup"><span data-stu-id="e28d5-261">**Cells Per Object**</span></span>  
 <span data-ttu-id="e28d5-262">Indique le nombre de cellules par objet de pavage qui peuvent être utilisées pour un objet spatial unique dans l'index.</span><span class="sxs-lookup"><span data-stu-id="e28d5-262">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="e28d5-263">Ce nombre peut être un entier compris entre 1 et 8192 (inclus).</span><span class="sxs-lookup"><span data-stu-id="e28d5-263">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="e28d5-264">La valeur par défaut est 16, et 8 pour les versions antérieures de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] lorsque le niveau de compatibilité de la base de données est défini sur 110 ou ultérieur.</span><span class="sxs-lookup"><span data-stu-id="e28d5-264">The default is 16, and 8 for earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="e28d5-265">Au niveau supérieur, si un objet couvre plus de cellules que le nombre spécifié par *n*, l’indexation utilise autant de cellules que nécessaire pour fournir un pavage de niveau supérieur complet.</span><span class="sxs-lookup"><span data-stu-id="e28d5-265">At the top level, if an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="e28d5-266">Dans de tels cas, un objet peut recevoir plus de cellules que le nombre spécifié.</span><span class="sxs-lookup"><span data-stu-id="e28d5-266">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="e28d5-267">Dans ce cas, le nombre maximal est le nombre de cellules générées par la grille de niveau supérieur, qui dépend de la densité du **Niveau 1** .</span><span class="sxs-lookup"><span data-stu-id="e28d5-267">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
### <a name="grids"></a><span data-ttu-id="e28d5-268">Grilles</span><span class="sxs-lookup"><span data-stu-id="e28d5-268">Grids</span></span>  
 <span data-ttu-id="e28d5-269">Ce panneau affiche la densité de la grille à chaque niveau du schéma de pavage.</span><span class="sxs-lookup"><span data-stu-id="e28d5-269">This panel shows the density of the grid at each level of the tessellation scheme.</span></span> <span data-ttu-id="e28d5-270">La densité est spécifiée comme suit : **Basse**, **Moyenne**ou **Haute**.</span><span class="sxs-lookup"><span data-stu-id="e28d5-270">Density is specified as **Low**, **Medium**, or **High**.</span></span> <span data-ttu-id="e28d5-271">La valeur par défaut est **Moyenne**.</span><span class="sxs-lookup"><span data-stu-id="e28d5-271">The default is **Medium**.</span></span> <span data-ttu-id="e28d5-272">**Basse** représente une grille 4x4 (16 cellules), **Moyenne** une grille 8x8 (64 cellules) et **Haute** une grille 16x16 (256 cellules).</span><span class="sxs-lookup"><span data-stu-id="e28d5-272">**Low** represents a 4x4 grid (16 cells), **Medium** represents an 8x8 grid (64 cells), and **High** represents a 16x16 grid (256 cells).</span></span> <span data-ttu-id="e28d5-273">Ces options ne sont pas disponibles lorsque les options de pavage **Grille automatique géométrique** ou **Grille automatique géographique** sont choisies.</span><span class="sxs-lookup"><span data-stu-id="e28d5-273">These options are not available when the **Geometry Auto grid** or **Geography Auto grid** tessellation options are chosen.</span></span>  
  
 <span data-ttu-id="e28d5-274">**Niveau 1**</span><span class="sxs-lookup"><span data-stu-id="e28d5-274">**Level 1**</span></span>  
 <span data-ttu-id="e28d5-275">Densité de la grille de premier niveau (haut).</span><span class="sxs-lookup"><span data-stu-id="e28d5-275">The density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="e28d5-276">**Niveau 2**</span><span class="sxs-lookup"><span data-stu-id="e28d5-276">**Level 2**</span></span>  
 <span data-ttu-id="e28d5-277">Densité de la grille de second niveau.</span><span class="sxs-lookup"><span data-stu-id="e28d5-277">The density of the second-level grid.</span></span>  
  
 <span data-ttu-id="e28d5-278">**Niveau 3**</span><span class="sxs-lookup"><span data-stu-id="e28d5-278">**Level 3**</span></span>  
 <span data-ttu-id="e28d5-279">Densité de la grille de troisième niveau.</span><span class="sxs-lookup"><span data-stu-id="e28d5-279">The density of the third-level grid.</span></span>  
  
 <span data-ttu-id="e28d5-280">**Niveau 4**</span><span class="sxs-lookup"><span data-stu-id="e28d5-280">**Level 4**</span></span>  
 <span data-ttu-id="e28d5-281">Densité de la grille de quatrième niveau.</span><span class="sxs-lookup"><span data-stu-id="e28d5-281">The density of the fourth-level grid.</span></span>  
  
##  <a name="filter-page"></a><a name="Filter"></a> <span data-ttu-id="e28d5-282">Page Filtre</span><span class="sxs-lookup"><span data-stu-id="e28d5-282">Filter Page</span></span>  
 <span data-ttu-id="e28d5-283">Utilisez cette page pour entrer le prédicat de filtre d'un index filtré.</span><span class="sxs-lookup"><span data-stu-id="e28d5-283">Use this page to enter the filter predicate for a filtered index.</span></span> <span data-ttu-id="e28d5-284">Pour plus d'informations, consultez [Create Filtered Indexes](create-filtered-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e28d5-284">For more information, see [Create Filtered Indexes](create-filtered-indexes.md).</span></span>  
  
 <span data-ttu-id="e28d5-285">**Expression de filtre**</span><span class="sxs-lookup"><span data-stu-id="e28d5-285">**Filter Expression**</span></span>  
 <span data-ttu-id="e28d5-286">Définit quelles lignes de données inclure dans l'index filtré.</span><span class="sxs-lookup"><span data-stu-id="e28d5-286">Defines which data rows to include in the filtered index.</span></span> <span data-ttu-id="e28d5-287">Par exemple : `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span><span class="sxs-lookup"><span data-stu-id="e28d5-287">For example, `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28d5-288">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e28d5-288">See Also</span></span>  
 <span data-ttu-id="e28d5-289">[Définir les options d'index](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="e28d5-289">[Set Index Options](set-index-options.md) </span></span>  
 <span data-ttu-id="e28d5-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e28d5-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 [<span data-ttu-id="e28d5-291">sys.indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e28d5-291">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
