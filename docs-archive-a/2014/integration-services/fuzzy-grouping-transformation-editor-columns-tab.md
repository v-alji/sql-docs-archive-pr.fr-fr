---
title: Éditeur de transformation de regroupement approximatif (onglet colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.columns.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 24f4539f-2a9f-4acd-acc7-06228a07f7df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d3aef9c30a81760b7f09378a8ecd66fee0dac62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696988"
---
# <a name="fuzzy-grouping-transformation-editor-columns-tab"></a><span data-ttu-id="34a91-102">Éditeur de transformation de regroupement approximatif (onglet Colonnes)</span><span class="sxs-lookup"><span data-stu-id="34a91-102">Fuzzy Grouping Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="34a91-103">L'onglet **Colonnes** de la boîte de dialogue **Éditeur de transformation de regroupement approximatif** permet de spécifier les colonnes utilisées pour regrouper les lignes comportant des doublons.</span><span class="sxs-lookup"><span data-stu-id="34a91-103">Use the **Columns** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify the columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="34a91-104">Pour en savoir plus sur la transformation de regroupement approximatif, consultez [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="34a91-104">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="34a91-105">Options</span><span class="sxs-lookup"><span data-stu-id="34a91-105">Options</span></span>  
 <span data-ttu-id="34a91-106">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="34a91-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="34a91-107">Sélectionnez dans cette liste les colonnes d'entrée utilisées pour regrouper les lignes comportant des doublons.</span><span class="sxs-lookup"><span data-stu-id="34a91-107">Select from this list the input columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="34a91-108">**Nom**</span><span class="sxs-lookup"><span data-stu-id="34a91-108">**Name**</span></span>  
 <span data-ttu-id="34a91-109">Permet d'afficher le nom des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="34a91-109">View the names of available input columns.</span></span>  
  
 <span data-ttu-id="34a91-110">**Transfert direct**</span><span class="sxs-lookup"><span data-stu-id="34a91-110">**Pass Through**</span></span>  
 <span data-ttu-id="34a91-111">Permet d'indiquer s'il est nécessaire d'inclure la colonne d'entrée dans la sortie de la transformation.</span><span class="sxs-lookup"><span data-stu-id="34a91-111">Select whether to include the input column in the output of the transformation.</span></span> <span data-ttu-id="34a91-112">Toutes les colonnes utilisées pour le regroupement sont automatiquement copiées dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="34a91-112">All columns used for grouping are automatically copied to the output.</span></span> <span data-ttu-id="34a91-113">Vous pouvez inclure des colonnes supplémentaires en activant cette colonne.</span><span class="sxs-lookup"><span data-stu-id="34a91-113">You can include additional columns by checking this column.</span></span>  
  
 <span data-ttu-id="34a91-114">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="34a91-114">**Input Column**</span></span>  
 <span data-ttu-id="34a91-115">Choisissez l’une des colonnes d’entrée précédemment sélectionnées dans la liste **Colonnes d’entrée disponibles** .</span><span class="sxs-lookup"><span data-stu-id="34a91-115">Select one of the input columns selected earlier in the **Available Input Columns** list.</span></span>  
  
 <span data-ttu-id="34a91-116">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="34a91-116">**Output Alias**</span></span>  
 <span data-ttu-id="34a91-117">Entrez un nom descriptif pour la colonne de sortie correspondante.</span><span class="sxs-lookup"><span data-stu-id="34a91-117">Enter a descriptive name for the corresponding output column.</span></span> <span data-ttu-id="34a91-118">Par défaut, cette colonne porte le même nom que la colonne d'entrée.</span><span class="sxs-lookup"><span data-stu-id="34a91-118">By default, the output column name is the same as the input column name.</span></span>  
  
 <span data-ttu-id="34a91-119">**Grouper les alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="34a91-119">**Group Output Alias**</span></span>  
 <span data-ttu-id="34a91-120">Entrez un nom descriptif pour la colonne qui va contenir la valeur canonique des doublons groupés.</span><span class="sxs-lookup"><span data-stu-id="34a91-120">Enter a descriptive name for the column that will contain the canonical value for the grouped duplicates.</span></span> <span data-ttu-id="34a91-121">Par défaut, cette colonne de sortie porte le nom de la colonne d'entrée suivi de la mention « _clean ».</span><span class="sxs-lookup"><span data-stu-id="34a91-121">The default name of this output column is the input column name with _clean appended.</span></span>  
  
 <span data-ttu-id="34a91-122">**Type de correspondance**</span><span class="sxs-lookup"><span data-stu-id="34a91-122">**Match Type**</span></span>  
 <span data-ttu-id="34a91-123">Sélectionnez la correspondance floue ou exacte.</span><span class="sxs-lookup"><span data-stu-id="34a91-123">Select fuzzy or exact matching.</span></span> <span data-ttu-id="34a91-124">Avec une correspondance approximative, les lignes sont considérées comme des doublons si elles sont suffisamment similaires dans toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="34a91-124">Rows are considered duplicates if they are sufficiently similar across all columns with a fuzzy match type.</span></span> <span data-ttu-id="34a91-125">Si vous spécifiez une correspondance exacte pour certaines colonnes, seules les lignes contenant des valeurs identiques dans les colonnes associées à une correspondance exacte seront considérées comme des doublons probables.</span><span class="sxs-lookup"><span data-stu-id="34a91-125">If you also specify exact matching on certain columns, only rows that contain identical values in the exact matching columns are considered as possible duplicates.</span></span> <span data-ttu-id="34a91-126">Par conséquent, si vous savez qu'une colonne ne contient aucune erreur ni incohérence, vous pouvez opter pour la correspondance exacte sur cette colonne afin d'accroître la précision de la correspondance approximative sur d'autres colonnes.</span><span class="sxs-lookup"><span data-stu-id="34a91-126">Therefore, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column to increase the accuracy of the fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="34a91-127">**Similarité minimale**</span><span class="sxs-lookup"><span data-stu-id="34a91-127">**Minimum Similarity**</span></span>  
 <span data-ttu-id="34a91-128">Définissez, à l'aide du curseur, le seuil de similarité au niveau de la jointure.</span><span class="sxs-lookup"><span data-stu-id="34a91-128">Set the similarity threshold at the join level by using the slider.</span></span> <span data-ttu-id="34a91-129">Plus la valeur est proche de 1, plus la valeur de recherche doit être proche de la valeur source pour constituer une correspondance.</span><span class="sxs-lookup"><span data-stu-id="34a91-129">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="34a91-130">Si vous augmentez le seuil, vous pouvez améliorer la vitesse de correspondance étant donné qu'un plus petit nombre d'enregistrements candidats doit être pris en compte.</span><span class="sxs-lookup"><span data-stu-id="34a91-130">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="34a91-131">**Alias de sortie de similarité**</span><span class="sxs-lookup"><span data-stu-id="34a91-131">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="34a91-132">Spécifiez le nom d'une nouvelle colonne de sortie qui contient le score de similarité de la jointure sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="34a91-132">Specify the name for a new output column that contains the similarity scores for the selected join.</span></span> <span data-ttu-id="34a91-133">Si vous ne définissez pas cette valeur, la colonne de sortie n'est pas créée.</span><span class="sxs-lookup"><span data-stu-id="34a91-133">If you leave this value empty, the output column is not created.</span></span>  
  
 <span data-ttu-id="34a91-134">**Chiffres**</span><span class="sxs-lookup"><span data-stu-id="34a91-134">**Numerals**</span></span>  
 <span data-ttu-id="34a91-135">Spécifiez l'importance des premiers et derniers chiffres en comparant les données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="34a91-135">Specify the significance of leading and trailing numerals in comparing the column data.</span></span> <span data-ttu-id="34a91-136">Par exemple, si les premiers chiffres sont significatifs, « 123 Main Street » ne sera pas groupé avec « 456 Main Street ».</span><span class="sxs-lookup"><span data-stu-id="34a91-136">For example, if leading numerals are significant, "123 Main Street" will not be grouped with "456 Main Street."</span></span>  
  
|<span data-ttu-id="34a91-137">Valeur</span><span class="sxs-lookup"><span data-stu-id="34a91-137">Value</span></span>|<span data-ttu-id="34a91-138">Description</span><span class="sxs-lookup"><span data-stu-id="34a91-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="34a91-139">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="34a91-139">**Neither**</span></span>|<span data-ttu-id="34a91-140">Les premiers et derniers chiffres ne sont pas significatifs.</span><span class="sxs-lookup"><span data-stu-id="34a91-140">Leading and trailing numerals are not significant.</span></span>|  
|<span data-ttu-id="34a91-141">**Premiers**</span><span class="sxs-lookup"><span data-stu-id="34a91-141">**Leading**</span></span>|<span data-ttu-id="34a91-142">Seuls les premiers chiffres sont significatifs.</span><span class="sxs-lookup"><span data-stu-id="34a91-142">Only leading numerals are significant.</span></span>|  
|<span data-ttu-id="34a91-143">**Derniers**</span><span class="sxs-lookup"><span data-stu-id="34a91-143">**Trailing**</span></span>|<span data-ttu-id="34a91-144">Seuls les derniers chiffres sont significatifs.</span><span class="sxs-lookup"><span data-stu-id="34a91-144">Only trailing numerals are significant.</span></span>|  
|<span data-ttu-id="34a91-145">**LeadingAndTrailing**</span><span class="sxs-lookup"><span data-stu-id="34a91-145">**LeadingAndTrailing**</span></span>|<span data-ttu-id="34a91-146">Les premiers et derniers chiffres sont significatifs.</span><span class="sxs-lookup"><span data-stu-id="34a91-146">Both leading and trailing numerals are significant.</span></span>|  
  
 <span data-ttu-id="34a91-147">**Indicateurs de comparaison**</span><span class="sxs-lookup"><span data-stu-id="34a91-147">**Comparison Flags**</span></span>  
 <span data-ttu-id="34a91-148">Pour plus d’informations sur les options de comparaison de chaînes, consultez [Comparaison des données chaînes](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="34a91-148">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a91-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="34a91-149">See Also</span></span>  
 <span data-ttu-id="34a91-150">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="34a91-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="34a91-151">Identifier des lignes de données semblables à l'aide de la transformation de regroupement probable</span><span class="sxs-lookup"><span data-stu-id="34a91-151">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
