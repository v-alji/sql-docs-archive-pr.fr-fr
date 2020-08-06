---
title: Fonction Multilookup (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1fec079e-33b3-4e4d-92b3-6b4d06a49a77
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2f2aff7a2a39e1a072cf4b05f0a04e12ced529af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605157"
---
# <a name="multilookup-function-report-builder-and-ssrs"></a><span data-ttu-id="8262e-102">Fonction Multilookup (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="8262e-102">Multilookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8262e-103">Retourne le jeu de valeurs de première correspondance pour le jeu de noms spécifié d'un dataset contenant des paires nom/valeur.</span><span class="sxs-lookup"><span data-stu-id="8262e-103">Returns the set of first-match values for the specified set of names from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="8262e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8262e-104">Syntax</span></span>  
  
```  
  
Multilookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8262e-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8262e-105">Parameters</span></span>  
 <span data-ttu-id="8262e-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="8262e-106">*source_expression*</span></span>  
 <span data-ttu-id="8262e-107">(`VariantArray`) Expression évaluée dans l'étendue actuelle et qui spécifie le jeu de noms ou de clés à rechercher.</span><span class="sxs-lookup"><span data-stu-id="8262e-107">(`VariantArray`) An expression that is evaluated in the current scope and that specifies the set of names or keys to look up.</span></span> <span data-ttu-id="8262e-108">Par exemple, pour un paramètre à valeurs multiples, `=Parameters!IDs.value`.</span><span class="sxs-lookup"><span data-stu-id="8262e-108">For example, for a multivalue parameter, `=Parameters!IDs.value`.</span></span>  
  
 <span data-ttu-id="8262e-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="8262e-109">*destination_expression*</span></span>  
 <span data-ttu-id="8262e-110">(`Variant`) Expression évaluée pour chaque ligne d'un dataset et qui spécifie le nom ou la clé de correspondance.</span><span class="sxs-lookup"><span data-stu-id="8262e-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="8262e-111">Par exemple : `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="8262e-111">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="8262e-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="8262e-112">*result_expression*</span></span>  
 <span data-ttu-id="8262e-113">( `Variant` ) Expression évaluée pour la ligne du DataSet où *source_expression*  =  *destination_expression*, et qui spécifie la valeur à récupérer.</span><span class="sxs-lookup"><span data-stu-id="8262e-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="8262e-114">Par exemple : `=Fields!Name.Value`.</span><span class="sxs-lookup"><span data-stu-id="8262e-114">For example, `=Fields!Name.Value`.</span></span>  
  
 <span data-ttu-id="8262e-115">*dataset*</span><span class="sxs-lookup"><span data-stu-id="8262e-115">*dataset*</span></span>  
 <span data-ttu-id="8262e-116">Constante qui spécifie le nom d'un dataset dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="8262e-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="8262e-117">Par exemple, « Couleurs ».</span><span class="sxs-lookup"><span data-stu-id="8262e-117">For example, "Colors".</span></span>  
  
## <a name="return"></a><span data-ttu-id="8262e-118">Renvoie</span><span class="sxs-lookup"><span data-stu-id="8262e-118">Return</span></span>  
 <span data-ttu-id="8262e-119">Retourne une valeur `VariantArray`, ou `Nothing` si aucune correspondance n'est trouvée.</span><span class="sxs-lookup"><span data-stu-id="8262e-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8262e-120">Notes</span><span class="sxs-lookup"><span data-stu-id="8262e-120">Remarks</span></span>  
 <span data-ttu-id="8262e-121">Utilisez `Multilookup` pour récupérer un ensemble de valeurs d'un dataset pour les paires nom-valeur lorsqu'il existe une relation un-à-un pour chaque paire.</span><span class="sxs-lookup"><span data-stu-id="8262e-121">Use `Multilookup` to retrieve a set of values from a dataset for name-value pairs where each pair has a 1-to-1 relationship.</span></span> <span data-ttu-id="8262e-122">`MultiLookup` équivaut à appeler `Lookup` pour un ensemble de noms ou de clés.</span><span class="sxs-lookup"><span data-stu-id="8262e-122">`MultiLookup` is the equivalent of calling `Lookup` for a set of names or keys.</span></span> <span data-ttu-id="8262e-123">Par exemple, pour un paramètre à valeurs multiples basé sur des identificateurs de clé primaire,vous pouvez utiliser `Multilookup` dans une expression d'une zone de texte d'une table pour récupérer des valeurs associées d'un dataset qui n'est pas lié au paramètre ou à la table.</span><span class="sxs-lookup"><span data-stu-id="8262e-123">For example, for a multivalue parameter that is based on primary key identifiers, you can use `Multilookup` in an expression in a text box in a table to retrieve associated values from a dataset that is not bound to the parameter or to the table.</span></span>  
  
 <span data-ttu-id="8262e-124">La fonction `Multilookup` effectue les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8262e-124">`Multilookup` does the following:</span></span>  
  
-   <span data-ttu-id="8262e-125">Elle évalue l'expression source dans l'étendue active et génère un tableau d'objets de type Variant.</span><span class="sxs-lookup"><span data-stu-id="8262e-125">Evaluates the source expression in the current scope and generates an array of variant objects.</span></span>  
  
-   <span data-ttu-id="8262e-126">Pour chaque objet du tableau, elle appelle la [Fonction Lookup &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-lookup-function.md) et ajoute le résultat au tableau de résultats.</span><span class="sxs-lookup"><span data-stu-id="8262e-126">For each object in the array, calls [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md) and adds the result to the return array.</span></span>  
  
-   <span data-ttu-id="8262e-127">Retourne le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="8262e-127">Returns the set of results.</span></span>  
  
 <span data-ttu-id="8262e-128">Pour récupérer une valeur unique dans un dataset avec les paires nom-valeur d’un nom spécifique, lorsqu’il existe une relation un-à-un, utilisez la [Fonction Lookup &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="8262e-128">To retrieve a single value from a dataset with name-value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="8262e-129">Pour récupérer plusieurs valeurs dans un dataset avec les paires nom-valeur d’un nom, lorsqu’il existe une relation un-à-plusieurs, utilisez une [Fonction LookupSet &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-lookupset-function.md).</span><span class="sxs-lookup"><span data-stu-id="8262e-129">To retrieve multiple values from a dataset with name-value pairs for a name where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span>  
  
 <span data-ttu-id="8262e-130">Les restrictions suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="8262e-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="8262e-131">`Multilookup` est évalué après que toutes les expressions de filtre ont été appliquées.</span><span class="sxs-lookup"><span data-stu-id="8262e-131">`Multilookup` is evaluated after all filter expressions are applied</span></span>  
  
-   <span data-ttu-id="8262e-132">Un seul niveau de recherche est pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8262e-132">Only one level of look-up is supported.</span></span> <span data-ttu-id="8262e-133">Une expression source, destination ou de résultat ne peut pas inclure de référence à une fonction de recherche.</span><span class="sxs-lookup"><span data-stu-id="8262e-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="8262e-134">Les expressions source et de destination doivent correspondre au même type de données.</span><span class="sxs-lookup"><span data-stu-id="8262e-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="8262e-135">Les expressions source, de destination et de résultat ne peuvent pas inclure de références à des variables de groupe ou de rapport.</span><span class="sxs-lookup"><span data-stu-id="8262e-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="8262e-136">`Multilookup` ne peut pas être utilisé comme expression pour les éléments de rapport suivants :</span><span class="sxs-lookup"><span data-stu-id="8262e-136">`Multilookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="8262e-137">des chaînes de connexion dynamiques pour une source de données ;</span><span class="sxs-lookup"><span data-stu-id="8262e-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="8262e-138">des champs calculés dans un dataset ;</span><span class="sxs-lookup"><span data-stu-id="8262e-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="8262e-139">des paramètres de requête dans un dataset ;</span><span class="sxs-lookup"><span data-stu-id="8262e-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="8262e-140">des filtres dans un dataset ;</span><span class="sxs-lookup"><span data-stu-id="8262e-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="8262e-141">des paramètres de rapport ;</span><span class="sxs-lookup"><span data-stu-id="8262e-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="8262e-142">la propriété Report.Language.</span><span class="sxs-lookup"><span data-stu-id="8262e-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="8262e-143">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="8262e-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8262e-144">Exemple</span><span class="sxs-lookup"><span data-stu-id="8262e-144">Example</span></span>  
 <span data-ttu-id="8262e-145">Supposons qu'un dataset nommé « Category » comprend le champ CategoryList, qui contient une liste séparée par des virgules d'identificateurs de catégorie, par exemple « 2, 4, 2, 1 ».</span><span class="sxs-lookup"><span data-stu-id="8262e-145">Assume a dataset called "Category" contains the field CategoryList, which is a field that contains a comma-separated list of category identifers, for example, "2, 4, 2, 1".</span></span>  
  
 <span data-ttu-id="8262e-146">Le dataset CategoryNames contient l'identificateur et le nom de catégorie, comme indiqué dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8262e-146">The dataset CategoryNames contains the category identifier and category name, as shown in the following table.</span></span>  
  
|<span data-ttu-id="8262e-147">id</span><span class="sxs-lookup"><span data-stu-id="8262e-147">ID</span></span>|<span data-ttu-id="8262e-148">Name</span><span class="sxs-lookup"><span data-stu-id="8262e-148">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="8262e-149">1</span><span class="sxs-lookup"><span data-stu-id="8262e-149">1</span></span>|<span data-ttu-id="8262e-150">Accessories</span><span class="sxs-lookup"><span data-stu-id="8262e-150">Accessories</span></span>|  
|<span data-ttu-id="8262e-151">2</span><span class="sxs-lookup"><span data-stu-id="8262e-151">2</span></span>|<span data-ttu-id="8262e-152">Bikes</span><span class="sxs-lookup"><span data-stu-id="8262e-152">Bikes</span></span>|  
|<span data-ttu-id="8262e-153">3</span><span class="sxs-lookup"><span data-stu-id="8262e-153">3</span></span>|<span data-ttu-id="8262e-154">Clothing</span><span class="sxs-lookup"><span data-stu-id="8262e-154">Clothing</span></span>|  
|<span data-ttu-id="8262e-155">4</span><span class="sxs-lookup"><span data-stu-id="8262e-155">4</span></span>|<span data-ttu-id="8262e-156">Components</span><span class="sxs-lookup"><span data-stu-id="8262e-156">Components</span></span>|  
  
 <span data-ttu-id="8262e-157">Pour rechercher les noms correspondant à la liste d'identificateurs, utilisez `Multilookup`.</span><span class="sxs-lookup"><span data-stu-id="8262e-157">To look up the names that correspond to the list of  identifiers, use `Multilookup`.</span></span> <span data-ttu-id="8262e-158">Vous devez tout d'abord fractionner la liste en un tableau de chaînes, appeler `Multilookup` pour récupérer les noms des catégories, puis concaténer les résultats en une chaîne.</span><span class="sxs-lookup"><span data-stu-id="8262e-158">You must first split the list into a string array, call `Multilookup` to retrieve the category names, and concatenate the results into a string.</span></span>  
  
 <span data-ttu-id="8262e-159">L'expression suivante, lorsqu'elle est placée dans une zone de texte dans une région de données liée au dataset Catégorie, affiche « Bicyclettes, Composants, Bicyclettes, Accessoires » :</span><span class="sxs-lookup"><span data-stu-id="8262e-159">The following expression, when placed in a text box in a data region bound to the Category dataset, displays "Bikes, Components, Bikes, Accessories":</span></span>  
  
```  
=Join(MultiLookup(Split(Fields!CategoryList.Value,","),  
   Fields!CategoryID.Value,Fields!CategoryName.Value,"Category")),  
   ", ")  
```  
  
## <a name="example"></a><span data-ttu-id="8262e-160">Exemple</span><span class="sxs-lookup"><span data-stu-id="8262e-160">Example</span></span>  
 <span data-ttu-id="8262e-161">Supposons qu' un dataset CouleursProduits contient un champ d'identificateur de couleur IDCouleur et un champ de valeur de couleur Couleur, comme indiqué dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8262e-161">Assume a dataset ProductColors contains a color identifier field ColorID and a color value field Color, as shown in the following table.</span></span>  
  
|<span data-ttu-id="8262e-162">ColorID</span><span class="sxs-lookup"><span data-stu-id="8262e-162">ColorID</span></span>|<span data-ttu-id="8262e-163">Couleur</span><span class="sxs-lookup"><span data-stu-id="8262e-163">Color</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="8262e-164">1</span><span class="sxs-lookup"><span data-stu-id="8262e-164">1</span></span>|<span data-ttu-id="8262e-165">Rouge</span><span class="sxs-lookup"><span data-stu-id="8262e-165">Red</span></span>|  
|<span data-ttu-id="8262e-166">2</span><span class="sxs-lookup"><span data-stu-id="8262e-166">2</span></span>|<span data-ttu-id="8262e-167">Bleu</span><span class="sxs-lookup"><span data-stu-id="8262e-167">Blue</span></span>|  
|<span data-ttu-id="8262e-168">3</span><span class="sxs-lookup"><span data-stu-id="8262e-168">3</span></span>|<span data-ttu-id="8262e-169">Vert</span><span class="sxs-lookup"><span data-stu-id="8262e-169">Green</span></span>|  
  
 <span data-ttu-id="8262e-170">Supposons que le paramètre à valeurs multiples *MyColors* n'est pas lié à un dataset pour ses valeurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="8262e-170">Assume the multivalue parameter *MyColors* is not bound to a dataset for its available values.</span></span> <span data-ttu-id="8262e-171">Les valeurs par défaut du paramètre sont égales à 2 et 3.</span><span class="sxs-lookup"><span data-stu-id="8262e-171">The default values for the parameter are set to 2 and 3.</span></span> <span data-ttu-id="8262e-172">L'expression suivante, lorsqu'elle est placée dans une zone de texte d'un tableau, concatène les valeurs de sélection multiple pour le paramètre dans une liste séparée par des virgules et affiche « Bleu, Vert ».</span><span class="sxs-lookup"><span data-stu-id="8262e-172">The following expression, when placed in a text box in a table, concatenates the multiple selected values for the parameter into a comma-separated list and displays "Blue, Green".</span></span>  
  
```  
=Join(MultiLookup(Parameters!MyColors.Value,Fields!ColorID.Value,Fields!Color.Value,"ProductColors"),", ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="8262e-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8262e-173">See Also</span></span>  
 <span data-ttu-id="8262e-174">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8262e-174">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8262e-175">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8262e-175">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="8262e-176">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8262e-176">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8262e-177">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8262e-177">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
