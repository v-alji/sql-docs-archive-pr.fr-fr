---
title: Totaux visuels et non visuels totaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ea9d02f2-a668-4547-ade5-e3d077a2e1bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ddff047be6a819d05276848cbeb430fb8e4c9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705564"
---
# <a name="visual-totals-and-non-visual-totals"></a><span data-ttu-id="02df5-102">Valeurs totales affichées et non affichées</span><span class="sxs-lookup"><span data-stu-id="02df5-102">Visual Totals and Non Visual Totals</span></span>
  <span data-ttu-id="02df5-103">Les valeurs totales affichées sont les totaux à la fin d'une colonne ou d'une ligne qui additionnent tous les éléments dans la colonne ou la ligne.</span><span class="sxs-lookup"><span data-stu-id="02df5-103">Visual Totals are totals at the end of a column or row that add up all of the items visible in the column or row.</span></span> <span data-ttu-id="02df5-104">C'est le comportement par défaut pour la plupart des tables en cas d'affichage.</span><span class="sxs-lookup"><span data-stu-id="02df5-104">This is the default behavior for most tables when displayed.</span></span> <span data-ttu-id="02df5-105">Toutefois, dans certains cas, l'utilisateur peut souhaiter afficher uniquement certaines colonnes dans une table mais garder les totaux pour la ligne entière, y compris ceux qui ne sont pas affichés.</span><span class="sxs-lookup"><span data-stu-id="02df5-105">However, there are times when the user wants to display only certain columns in a table but keep the totals for the entire row, including those that are not displayed.</span></span> <span data-ttu-id="02df5-106">On les appelle des `Non Visual Totals`, parce que le total est calculé à partir des valeurs visibles et non visibles.</span><span class="sxs-lookup"><span data-stu-id="02df5-106">These are called `Non Visual Totals`, because the total comes from both the visible and non-visible values.</span></span>  
  
 <span data-ttu-id="02df5-107">Le scénario suivant montre le comportement des valeurs totales non affichées.</span><span class="sxs-lookup"><span data-stu-id="02df5-107">The following scenario demonstrates the behavior of Non Visual totals.</span></span> <span data-ttu-id="02df5-108">La première étape montre le comportement par défaut des valeurs totales affichées.</span><span class="sxs-lookup"><span data-stu-id="02df5-108">The first step shows the default behavior of Visual Totals.</span></span>  
  
 <span data-ttu-id="02df5-109">L'exemple suivant illustre une requête sur [Adventure Works] pour obtenir les chiffres [Reseller Sales Amount] dans une table où les catégories de produits sont représentées par les colonnes et les types de secteur d'activité des revendeurs sont représentés par les lignes.</span><span class="sxs-lookup"><span data-stu-id="02df5-109">The following example is a query of [Adventure Works] to obtain [Reseller Sales Amount] figures in a table where the product categories are the columns and the reseller business types are the rows.</span></span> <span data-ttu-id="02df5-110">Notez que les totaux sont donnés pour les produits et les revendeurs à la fois lorsque l'instruction SELECT suivante est émise :</span><span class="sxs-lookup"><span data-stu-id="02df5-110">Note that totals are given for both products and resellers when the following SELECT statement is issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from [Adventure Works]`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="02df5-111">Génère les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="02df5-111">Produces the following results:</span></span>  
  
|||||||  
|-|-|-|-|-|-|  
||<span data-ttu-id="02df5-112">**Tous les produits**</span><span class="sxs-lookup"><span data-stu-id="02df5-112">**All Products**</span></span>|<span data-ttu-id="02df5-113">**Accessories**</span><span class="sxs-lookup"><span data-stu-id="02df5-113">**Accessories**</span></span>|<span data-ttu-id="02df5-114">**Bikes**</span><span class="sxs-lookup"><span data-stu-id="02df5-114">**Bikes**</span></span>|<span data-ttu-id="02df5-115">**Clothing**</span><span class="sxs-lookup"><span data-stu-id="02df5-115">**Clothing**</span></span>|<span data-ttu-id="02df5-116">**Composants**</span><span class="sxs-lookup"><span data-stu-id="02df5-116">**Components**</span></span>|  
|<span data-ttu-id="02df5-117">**All Resellers**</span><span class="sxs-lookup"><span data-stu-id="02df5-117">**All Resellers**</span></span>|<span data-ttu-id="02df5-118">**80 450 596,98 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-118">**$80,450,596.98**</span></span>|<span data-ttu-id="02df5-119">**571 297,93 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-119">**$571,297.93**</span></span>|<span data-ttu-id="02df5-120">**66 302 381,56 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-120">**$66,302,381.56**</span></span>|<span data-ttu-id="02df5-121">**1 777 840,84 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-121">**$1,777,840.84**</span></span>|<span data-ttu-id="02df5-122">**11 799 076,66 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-122">**$11,799,076.66**</span></span>|  
|<span data-ttu-id="02df5-123">**Specialty Bike Shop**</span><span class="sxs-lookup"><span data-stu-id="02df5-123">**Specialty Bike Shop**</span></span>|<span data-ttu-id="02df5-124">**6 756 166,18 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-124">**$6,756,166.18**</span></span>|<span data-ttu-id="02df5-125">**65 125,48 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-125">**$65,125.48**</span></span>|<span data-ttu-id="02df5-126">**6 080 117,73 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-126">**$6,080,117.73**</span></span>|<span data-ttu-id="02df5-127">**252 933,91 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-127">**$252,933.91**</span></span>|<span data-ttu-id="02df5-128">**357 989,07 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-128">**$357,989.07**</span></span>|  
|<span data-ttu-id="02df5-129">**Value Added Reseller**</span><span class="sxs-lookup"><span data-stu-id="02df5-129">**Value Added Reseller**</span></span>|<span data-ttu-id="02df5-130">**34 967 517,33 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-130">**$34,967,517.33**</span></span>|<span data-ttu-id="02df5-131">**175 002,81 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-131">**$175,002.81**</span></span>|<span data-ttu-id="02df5-132">**30 892 354,33 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-132">**$30,892,354.33**</span></span>|<span data-ttu-id="02df5-133">**592 385,71 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-133">**$592,385.71**</span></span>|<span data-ttu-id="02df5-134">**3 307 774,48 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-134">**$3,307,774.48**</span></span>|  
|<span data-ttu-id="02df5-135">**Entrepôt**</span><span class="sxs-lookup"><span data-stu-id="02df5-135">**Warehouse**</span></span>|<span data-ttu-id="02df5-136">**38 726 913,48 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-136">**$38,726,913.48**</span></span>|<span data-ttu-id="02df5-137">**331 169,64 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-137">**$331,169.64**</span></span>|<span data-ttu-id="02df5-138">**29 329 909,50 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-138">**$29,329,909.50**</span></span>|<span data-ttu-id="02df5-139">**932 521,23 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-139">**$932,521.23**</span></span>|<span data-ttu-id="02df5-140">**8 133 313,11 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-140">**$8,133,313.11**</span></span>|  
  
## <a name="non-visual-on-rows-and-columns"></a><span data-ttu-id="02df5-141">Non affichées sur les lignes et les colonnes</span><span class="sxs-lookup"><span data-stu-id="02df5-141">Non-Visual on rows and columns</span></span>  
 <span data-ttu-id="02df5-142">Pour créer une table contenant uniquement les données pour les produits Accessories et Clothing, ainsi que les revendeurs Value Added Reseller et Warehouse, tout en conservant les totaux globaux, vous pouvez utiliser NON VISUAL comme suit :</span><span class="sxs-lookup"><span data-stu-id="02df5-142">To produce a table with data only for the Accessories and Clothing products, the Value Added Reseller and Warehouse resellers, yet keeping the overall totals could be written as follows using NON VISUAL:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0,`  
  
 `{[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 1`  
  
 `from [Adventure Works])`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="02df5-143">Génère les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="02df5-143">Produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="02df5-144">**Tous les produits**</span><span class="sxs-lookup"><span data-stu-id="02df5-144">**All Products**</span></span>|<span data-ttu-id="02df5-145">**Accessories**</span><span class="sxs-lookup"><span data-stu-id="02df5-145">**Accessories**</span></span>|<span data-ttu-id="02df5-146">**Clothing**</span><span class="sxs-lookup"><span data-stu-id="02df5-146">**Clothing**</span></span>|  
|<span data-ttu-id="02df5-147">**All Resellers**</span><span class="sxs-lookup"><span data-stu-id="02df5-147">**All Resellers**</span></span>|<span data-ttu-id="02df5-148">**80 450 596,98 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-148">**$80,450,596.98**</span></span>|<span data-ttu-id="02df5-149">**571 297,93 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-149">**$571,297.93**</span></span>|<span data-ttu-id="02df5-150">**1 777 840,84 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-150">**$1,777,840.84**</span></span>|  
|<span data-ttu-id="02df5-151">**Value Added Reseller**</span><span class="sxs-lookup"><span data-stu-id="02df5-151">**Value Added Reseller**</span></span>|<span data-ttu-id="02df5-152">**34 967 517,33 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-152">**$34,967,517.33**</span></span>|<span data-ttu-id="02df5-153">**175 002,81 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-153">**$175,002.81**</span></span>|<span data-ttu-id="02df5-154">**592 385,71 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-154">**$592,385.71**</span></span>|  
|<span data-ttu-id="02df5-155">**Entrepôt**</span><span class="sxs-lookup"><span data-stu-id="02df5-155">**Warehouse**</span></span>|<span data-ttu-id="02df5-156">**38 726 913,48 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-156">**$38,726,913.48**</span></span>|<span data-ttu-id="02df5-157">**331 169,64 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-157">**$331,169.64**</span></span>|<span data-ttu-id="02df5-158">**932 521,23 $**</span><span class="sxs-lookup"><span data-stu-id="02df5-158">**$932,521.23**</span></span>|  
  
## <a name="non-visual-on-rows"></a><span data-ttu-id="02df5-159">Non affichées sur les lignes</span><span class="sxs-lookup"><span data-stu-id="02df5-159">Non-Visual on rows</span></span>  
 <span data-ttu-id="02df5-160">Pour créer une table qui additionne visuellement les colonnes mais qui, pour les totaux de ligne, affiche le total réel de tout l'élément [Category], vous pouvez utiliser la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="02df5-160">To produce a table that visually totals the columns but for row totals brings the true total of all [Category], the following query should be issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0`  
  
 `from ( Select {[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 0`  
  
 `from [Adventure Works])`  
  
 `)`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="02df5-161">Notez que NON VISUAL est uniquement appliqué à [Category].</span><span class="sxs-lookup"><span data-stu-id="02df5-161">Note how NON VISUAL is only applied to [Category].</span></span>  
  
 <span data-ttu-id="02df5-162">La requête ci-dessus génère les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="02df5-162">The above query produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="02df5-163">All Products</span><span class="sxs-lookup"><span data-stu-id="02df5-163">All Products</span></span>|<span data-ttu-id="02df5-164">Accessories</span><span class="sxs-lookup"><span data-stu-id="02df5-164">Accessories</span></span>|<span data-ttu-id="02df5-165">Clothing</span><span class="sxs-lookup"><span data-stu-id="02df5-165">Clothing</span></span>|  
|<span data-ttu-id="02df5-166">All Resellers</span><span class="sxs-lookup"><span data-stu-id="02df5-166">All Resellers</span></span>|<span data-ttu-id="02df5-167">73 694 430,80 $</span><span class="sxs-lookup"><span data-stu-id="02df5-167">$73,694,430.80</span></span>|<span data-ttu-id="02df5-168">506 172,45 $</span><span class="sxs-lookup"><span data-stu-id="02df5-168">$506,172.45</span></span>|<span data-ttu-id="02df5-169">1 524 906,93 $</span><span class="sxs-lookup"><span data-stu-id="02df5-169">$1,524,906.93</span></span>|  
|<span data-ttu-id="02df5-170">Value Added Reseller</span><span class="sxs-lookup"><span data-stu-id="02df5-170">Value Added Reseller</span></span>|<span data-ttu-id="02df5-171">34 967 517,33 $</span><span class="sxs-lookup"><span data-stu-id="02df5-171">$34,967,517.33</span></span>|<span data-ttu-id="02df5-172">175 002,81 $</span><span class="sxs-lookup"><span data-stu-id="02df5-172">$175,002.81</span></span>|<span data-ttu-id="02df5-173">592 385,71 $</span><span class="sxs-lookup"><span data-stu-id="02df5-173">$592,385.71</span></span>|  
|<span data-ttu-id="02df5-174">Warehouse</span><span class="sxs-lookup"><span data-stu-id="02df5-174">Warehouse</span></span>|<span data-ttu-id="02df5-175">38 726 913,48 $</span><span class="sxs-lookup"><span data-stu-id="02df5-175">$38,726,913.48</span></span>|<span data-ttu-id="02df5-176">331 169,64 $</span><span class="sxs-lookup"><span data-stu-id="02df5-176">$331,169.64</span></span>|<span data-ttu-id="02df5-177">932 521,23 $</span><span class="sxs-lookup"><span data-stu-id="02df5-177">$932,521.23</span></span>|  
  
 <span data-ttu-id="02df5-178">Lorsque l'on effectue une comparaison avec les résultats précédents, on observe que la ligne [All Resellers] est additionnée avec les valeurs affichées pour [Value Added Reseller] et [Warehouse] mais que la colonne [All Products] affiche la valeur totale pour tous les produits, y compris ceux qui ne sont pas affichés.</span><span class="sxs-lookup"><span data-stu-id="02df5-178">When compared with the previous results, you can observe that the [All Resellers] row now adds up to the displayed values for [Value Added Reseller] and [Warehouse] but that the [All Products] column shows the total value for all products, including those not displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02df5-179">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02df5-179">See Also</span></span>  
 <span data-ttu-id="02df5-180">[Concepts clés dans MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="02df5-180">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="02df5-181">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="02df5-181">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="02df5-182">[Utilisation de membres, de tuples et de jeux &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="02df5-182">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="02df5-183">[Notions de base des requêtes MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="02df5-183">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 <span data-ttu-id="02df5-184">[Requête MDX de base &#40;&#41;MDX](mdx-query-the-basic-query.md) </span><span class="sxs-lookup"><span data-stu-id="02df5-184">[The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md) </span></span>  
 <span data-ttu-id="02df5-185">[Restriction de la requête avec des axes de requête et de segment &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span><span class="sxs-lookup"><span data-stu-id="02df5-185">[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span></span>  
 [<span data-ttu-id="02df5-186">Définition d’un contexte de cube dans une requête &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="02df5-186">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)  
  
  
