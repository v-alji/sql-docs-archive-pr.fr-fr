---
title: Index spatiaux, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.spatialindexes
ms.assetid: 4d84239a-68c7-4aa2-8602-2b51dd07260f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e401b7f93a8376b1c6dc0c75ca29cbdc8a39863d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604804"
---
# <a name="spatial-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="5f610-102">Index spatiaux, boîte de dialogue (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="5f610-102">Spatial Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="5f610-103">Utilisez la boîte de dialogue **Index spatiaux** pour créer des index pour les colonnes du type de données **géométrie** or **géographie** (*colonnes spatiales*), qui ne peuvent pas être indexées à l'aide de la boîte de dialogue **Index/Clés** .</span><span class="sxs-lookup"><span data-stu-id="5f610-103">Use the **Spatial Indexes** dialog box to create indexes for columns of the **geometry** or **geography** data type (*spatial columns*), which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="5f610-104">Chaque colonne spatiale peut avoir plusieurs index spatiaux, mais ils doivent être créés un par un.</span><span class="sxs-lookup"><span data-stu-id="5f610-104">Each spatial column can have more than one spatial index, but they must be created one at a time.</span></span>  
  
 <span data-ttu-id="5f610-105">Pour plus d'informations sur les restrictions relatives à la création d'index spatiaux, consultez [Vue d'ensemble des index spatiaux](../../relational-databases/spatial/spatial-indexes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5f610-105">For information about restrictions on spatial index creation, see [Spatial Indexes Overview](../../relational-databases/spatial/spatial-indexes-overview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5f610-106">Options</span><span class="sxs-lookup"><span data-stu-id="5f610-106">Options</span></span>  
 <span data-ttu-id="5f610-107">**Index spatial sélectionné**</span><span class="sxs-lookup"><span data-stu-id="5f610-107">**Selected Spatial Index**</span></span>  
 <span data-ttu-id="5f610-108">Répertorie les index spatiaux existants.</span><span class="sxs-lookup"><span data-stu-id="5f610-108">Lists existing spatial indexes.</span></span> <span data-ttu-id="5f610-109">Sélectionnez un index pour afficher ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="5f610-109">Select an index to show its properties.</span></span> <span data-ttu-id="5f610-110">Si la liste est vide, aucun index spatial n'est défini pour la table.</span><span class="sxs-lookup"><span data-stu-id="5f610-110">If the list is empty, no spatial indexes have been defined for the table.</span></span>  
  
 <span data-ttu-id="5f610-111">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="5f610-111">**Add**</span></span>  
 <span data-ttu-id="5f610-112">Crée un index spatial.</span><span class="sxs-lookup"><span data-stu-id="5f610-112">Creates a new spatial index.</span></span>  
  
 <span data-ttu-id="5f610-113">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="5f610-113">**Delete**</span></span>  
 <span data-ttu-id="5f610-114">Supprime l'index spatial sélectionné dans la liste **Index spatial sélectionné** .</span><span class="sxs-lookup"><span data-stu-id="5f610-114">Deletes the spatial index selected in the **Selected Spatial Index** list.</span></span>  
  
 <span data-ttu-id="5f610-115">**Cellules par objet**</span><span class="sxs-lookup"><span data-stu-id="5f610-115">**Cells Per Object**</span></span>  
 <span data-ttu-id="5f610-116">Indique le nombre de cellules par objet de pavage qui peuvent être utilisées pour un objet spatial unique dans l'index.</span><span class="sxs-lookup"><span data-stu-id="5f610-116">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="5f610-117">Ce nombre peut être un entier compris entre 1 et 8192 (inclus).</span><span class="sxs-lookup"><span data-stu-id="5f610-117">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="5f610-118">La valeur par défaut est 16.</span><span class="sxs-lookup"><span data-stu-id="5f610-118">The default is 16.</span></span>  
  
 <span data-ttu-id="5f610-119">Si un objet couvre plus de cellules que le nombre spécifié par *n*, l'indexation utilise autant de cellules que nécessaire pour fournir un pavage de niveau supérieur complet.</span><span class="sxs-lookup"><span data-stu-id="5f610-119">If an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="5f610-120">Dans de tels cas, un objet peut recevoir plus de cellules que le nombre spécifié.</span><span class="sxs-lookup"><span data-stu-id="5f610-120">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="5f610-121">Dans ce cas, le nombre maximal est le nombre de cellules générées par la grille de niveau supérieur, qui dépend de la densité du **Niveau 1** .</span><span class="sxs-lookup"><span data-stu-id="5f610-121">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
 <span data-ttu-id="5f610-122">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="5f610-122">**Columns**</span></span>  
 <span data-ttu-id="5f610-123">Indique le nom de colonne et l'ordre de tri.</span><span class="sxs-lookup"><span data-stu-id="5f610-123">Indicates the column name and sort order.</span></span>  
  
 <span data-ttu-id="5f610-124">**IsSpatialIndex**</span><span class="sxs-lookup"><span data-stu-id="5f610-124">**IsSpatialIndex**</span></span>  
 <span data-ttu-id="5f610-125">Indique qu'un index spatial est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5f610-125">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="5f610-126">**Niveau 1**</span><span class="sxs-lookup"><span data-stu-id="5f610-126">**Level 1**</span></span>  
 <span data-ttu-id="5f610-127">Indique la densité de la grille de premier niveau (supérieur).</span><span class="sxs-lookup"><span data-stu-id="5f610-127">Indicates the density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="5f610-128">**Niveau 2**</span><span class="sxs-lookup"><span data-stu-id="5f610-128">**Level 2**</span></span>  
 <span data-ttu-id="5f610-129">Indique la densité de la grille de second niveau.</span><span class="sxs-lookup"><span data-stu-id="5f610-129">Indicates the density of the second-level grid.</span></span>  
  
 <span data-ttu-id="5f610-130">**Niveau 3**</span><span class="sxs-lookup"><span data-stu-id="5f610-130">**Level 3**</span></span>  
 <span data-ttu-id="5f610-131">Indique la densité de la grille de troisième niveau.</span><span class="sxs-lookup"><span data-stu-id="5f610-131">Indicates the density of the third-level grid.</span></span>  
  
 <span data-ttu-id="5f610-132">**Niveau 4**</span><span class="sxs-lookup"><span data-stu-id="5f610-132">**Level 4**</span></span>  
 <span data-ttu-id="5f610-133">Indique la densité de la grille de quatrième niveau.</span><span class="sxs-lookup"><span data-stu-id="5f610-133">Indicates the density of the fourth-level grid.</span></span>  
  
 <span data-ttu-id="5f610-134">**Schéma de pavage**</span><span class="sxs-lookup"><span data-stu-id="5f610-134">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="5f610-135">Indique le schéma de pavage :</span><span class="sxs-lookup"><span data-stu-id="5f610-135">Indicates the tessellation scheme:</span></span>  
  
 <span data-ttu-id="5f610-136">Options de colonne**geometry** :</span><span class="sxs-lookup"><span data-stu-id="5f610-136">**Geometry** column options:</span></span>  
  
-   <span data-ttu-id="5f610-137">**Grille géométrique** pour une colonne de géométrie</span><span class="sxs-lookup"><span data-stu-id="5f610-137">**Geometry grid** for a geometry column</span></span>  
  
-   <span data-ttu-id="5f610-138">**Grille géographique** pour une colonne de géographie</span><span class="sxs-lookup"><span data-stu-id="5f610-138">**Geography grid** for a geography column</span></span>  
  
 <span data-ttu-id="5f610-139">**Type**</span><span class="sxs-lookup"><span data-stu-id="5f610-139">**Type**</span></span>  
 <span data-ttu-id="5f610-140">Indique qu'un index spatial est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5f610-140">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="5f610-141">**Max. X**</span><span class="sxs-lookup"><span data-stu-id="5f610-141">**X-max**</span></span>  
 <span data-ttu-id="5f610-142">Spécifie la coordonnée x de l'angle supérieur droit du rectangle englobant.</span><span class="sxs-lookup"><span data-stu-id="5f610-142">Specifies the x-coordinate of the upper-right corner of the bounding box.</span></span> <span data-ttu-id="5f610-143">Cette propriété est estompée si le **Schéma de pavage** est une **Grille géographique**.</span><span class="sxs-lookup"><span data-stu-id="5f610-143">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="5f610-144">**Min. X**</span><span class="sxs-lookup"><span data-stu-id="5f610-144">**X-min**</span></span>  
 <span data-ttu-id="5f610-145">Spécifie la coordonnée x de l'angle inférieur gauche du rectangle englobant.</span><span class="sxs-lookup"><span data-stu-id="5f610-145">Specifies the x-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="5f610-146">Cette propriété est estompée si le **Schéma de pavage** est une **Grille géographique**.</span><span class="sxs-lookup"><span data-stu-id="5f610-146">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="5f610-147">**Max. Y**</span><span class="sxs-lookup"><span data-stu-id="5f610-147">**Y-max**</span></span>  
 <span data-ttu-id="5f610-148">Spécifie la coordonnée y de l'angle supérieur droit du rectangle englobant.</span><span class="sxs-lookup"><span data-stu-id="5f610-148">Specifies the y-coordinate of upper-right corner of the bounding box.</span></span> <span data-ttu-id="5f610-149">Cette propriété est estompée si le **Schéma de pavage** est une **Grille géographique**.</span><span class="sxs-lookup"><span data-stu-id="5f610-149">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="5f610-150">**Min. Y**</span><span class="sxs-lookup"><span data-stu-id="5f610-150">**Y-min**</span></span>  
 <span data-ttu-id="5f610-151">Spécifie la coordonnée y de l'angle inférieur gauche du rectangle englobant.</span><span class="sxs-lookup"><span data-stu-id="5f610-151">Specifies the y-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="5f610-152">Cette propriété est estompée si le **Schéma de pavage** est une **Grille géographique**.</span><span class="sxs-lookup"><span data-stu-id="5f610-152">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="5f610-153">**Identité**</span><span class="sxs-lookup"><span data-stu-id="5f610-153">**Identity**</span></span>  
 <span data-ttu-id="5f610-154">Développée, elle affiche les champs de propriétés de **Nom** et **Description** .</span><span class="sxs-lookup"><span data-stu-id="5f610-154">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="5f610-155">**(Nom)**</span><span class="sxs-lookup"><span data-stu-id="5f610-155">**(Name)**</span></span>  
 <span data-ttu-id="5f610-156">Indique le nom de l'index spatial.</span><span class="sxs-lookup"><span data-stu-id="5f610-156">Shows the name of the spatial index.</span></span> <span data-ttu-id="5f610-157">Lorsqu'un nouvel index est créé, il obtient un nom par défaut basé sur la table affichée dans la fenêtre active du Concepteur de tables.</span><span class="sxs-lookup"><span data-stu-id="5f610-157">When a new index is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="5f610-158">Vous pouvez modifier le nom à tout moment.</span><span class="sxs-lookup"><span data-stu-id="5f610-158">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="5f610-159">**Description**</span><span class="sxs-lookup"><span data-stu-id="5f610-159">**Description**</span></span>  
 <span data-ttu-id="5f610-160">Décrit l'index.</span><span class="sxs-lookup"><span data-stu-id="5f610-160">Describes the index.</span></span> <span data-ttu-id="5f610-161">Pour écrire une description plus détaillée, cliquez sur **Description**, puis sur le bouton de sélection ( **...** ) qui s’affiche à droite du champ de propriété.</span><span class="sxs-lookup"><span data-stu-id="5f610-161">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="5f610-162">Vous obtiendrez une zone d'écriture plus large.</span><span class="sxs-lookup"><span data-stu-id="5f610-162">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="5f610-163">**Catégorie Concepteur de tables**</span><span class="sxs-lookup"><span data-stu-id="5f610-163">**Table Designer Category**</span></span>  
 <span data-ttu-id="5f610-164">Développée, elle affiche des informations sur les propriétés de cet index spatial.</span><span class="sxs-lookup"><span data-stu-id="5f610-164">When expanded, shows information about the properties of this spatial index.</span></span>  
  
 <span data-ttu-id="5f610-165">**Spécification du remplissage**</span><span class="sxs-lookup"><span data-stu-id="5f610-165">**Fill Specification**</span></span>  
 <span data-ttu-id="5f610-166">Développée, elle affiche des informations sur les options **Taux de remplissage** et **Index Pad**.</span><span class="sxs-lookup"><span data-stu-id="5f610-166">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="5f610-167">**Taux de remplissage**</span><span class="sxs-lookup"><span data-stu-id="5f610-167">**Fill Factor**</span></span>  
 <span data-ttu-id="5f610-168">Spécifie le pourcentage de la page d'index que le système peut remplir.</span><span class="sxs-lookup"><span data-stu-id="5f610-168">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="5f610-169">Lorsqu'une page est pleine, le système doit la fractionner au cas où de nouvelles données seraient ajoutées, ce qui affaiblit les performances.</span><span class="sxs-lookup"><span data-stu-id="5f610-169">When a page is full, if new data is added, the system must split the page, which impairs performance.</span></span>  
  
-   <span data-ttu-id="5f610-170">La valeur 100 signifie que les pages seront remplies et occuperont un espace de stockage minimal, mais c'est la solution la moins efficace.</span><span class="sxs-lookup"><span data-stu-id="5f610-170">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="5f610-171">Ce paramètre ne doit être utilisé que lorsqu'aucune modification ne sera apportée aux données, par exemple dans un tableau en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5f610-171">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="5f610-172">Une valeur inférieure laisse davantage d'espace vide sur les ensembles de données, ce qui réduit le besoin de les fractionner à mesure que la taille des index augmente.</span><span class="sxs-lookup"><span data-stu-id="5f610-172">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="5f610-173">Néanmoins, l'espace de stockage requis est plus important.</span><span class="sxs-lookup"><span data-stu-id="5f610-173">However, it requires more storage space.</span></span> <span data-ttu-id="5f610-174">Ce paramètre est plus approprié si vous avez l'intention de modifier les données contenues dans la table.</span><span class="sxs-lookup"><span data-stu-id="5f610-174">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="5f610-175">**Index Pad**</span><span class="sxs-lookup"><span data-stu-id="5f610-175">**Pad Index**</span></span>  
 <span data-ttu-id="5f610-176">Donne aux pages de cet index le même pourcentage d'espace libre (de remplissage) que celui spécifié dans **Facteur de remplissage**.</span><span class="sxs-lookup"><span data-stu-id="5f610-176">Provides pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="5f610-177">**Verrouillage de page autorisé**</span><span class="sxs-lookup"><span data-stu-id="5f610-177">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="5f610-178">Spécifie si le verrouillage au niveau des pages est autorisé dans cet index.</span><span class="sxs-lookup"><span data-stu-id="5f610-178">Specifies whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="5f610-179">L'autorisation ou non du verrouillage au niveau de la page affecte les performances de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5f610-179">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="5f610-180">**Recalculer les statistiques**</span><span class="sxs-lookup"><span data-stu-id="5f610-180">**Re-compute  Statistics**</span></span>  
 <span data-ttu-id="5f610-181">Spécifie si de nouvelles statistiques sont calculées une fois l'index créé.</span><span class="sxs-lookup"><span data-stu-id="5f610-181">Specifies whether to compute new statistics when the index is created.</span></span> <span data-ttu-id="5f610-182">Le calcul des statistiques ralentit la génération des index, mais améliore généralement les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="5f610-182">Recomputing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="5f610-183">**Verrouillage de ligne autorisé**</span><span class="sxs-lookup"><span data-stu-id="5f610-183">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="5f610-184">Spécifie si le verrouillage au niveau des lignes est autorisé dans cet index.</span><span class="sxs-lookup"><span data-stu-id="5f610-184">Specifies whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="5f610-185">L'autorisation ou non du verrouillage au niveau de la ligne affecte les performances de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5f610-185">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f610-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f610-186">See Also</span></span>  
 [<span data-ttu-id="5f610-187">Vue d’ensemble des index spatiaux</span><span class="sxs-lookup"><span data-stu-id="5f610-187">Spatial Indexes Overview</span></span>](../../relational-databases/spatial/spatial-indexes-overview.md)  
  
  
