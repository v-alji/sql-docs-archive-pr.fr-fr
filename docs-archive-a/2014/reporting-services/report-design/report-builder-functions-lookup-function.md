---
title: Fonction Lookup (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e60e5bab-b286-4897-9685-9ff12703517d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 053fefff51e4b4e338e262664bd7570280c92540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605159"
---
# <a name="lookup-function-report-builder-and-ssrs"></a><span data-ttu-id="a2712-102">Fonction Lookup (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="a2712-102">Lookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a2712-103">Retourne la première valeur correspondante pour le nom spécifié d'un dataset contenant des paires nom/valeur.</span><span class="sxs-lookup"><span data-stu-id="a2712-103">Returns the first matching value for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="a2712-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a2712-104">Syntax</span></span>  
  
```  
  
Lookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2712-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a2712-105">Parameters</span></span>  
 <span data-ttu-id="a2712-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="a2712-106">*source_expression*</span></span>  
 <span data-ttu-id="a2712-107">(`Variant`) Expression évaluée dans l'étendue actuelle et qui spécifie le nom ou la clé à rechercher.</span><span class="sxs-lookup"><span data-stu-id="a2712-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="a2712-108">Par exemple : `=Fields!ProdID.Value`.</span><span class="sxs-lookup"><span data-stu-id="a2712-108">For example, `=Fields!ProdID.Value`.</span></span>  
  
 <span data-ttu-id="a2712-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="a2712-109">*destination_expression*</span></span>  
 <span data-ttu-id="a2712-110">(`Variant`) Expression évaluée pour chaque ligne d'un dataset et qui spécifie le nom ou la clé de correspondance.</span><span class="sxs-lookup"><span data-stu-id="a2712-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="a2712-111">Par exemple : `=Fields!ProductID.Value`.</span><span class="sxs-lookup"><span data-stu-id="a2712-111">For example, `=Fields!ProductID.Value`.</span></span>  
  
 <span data-ttu-id="a2712-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="a2712-112">*result_expression*</span></span>  
 <span data-ttu-id="a2712-113">( `Variant` ) Expression évaluée pour la ligne du DataSet où *source_expression*  =  *destination_expression*, et qui spécifie la valeur à récupérer.</span><span class="sxs-lookup"><span data-stu-id="a2712-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="a2712-114">Par exemple : `=Fields!ProductName.Value`.</span><span class="sxs-lookup"><span data-stu-id="a2712-114">For example, `=Fields!ProductName.Value`.</span></span>  
  
 <span data-ttu-id="a2712-115">*dataset*</span><span class="sxs-lookup"><span data-stu-id="a2712-115">*dataset*</span></span>  
 <span data-ttu-id="a2712-116">Constante qui spécifie le nom d'un dataset dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="a2712-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="a2712-117">Par exemple, « Products ».</span><span class="sxs-lookup"><span data-stu-id="a2712-117">For example, "Products".</span></span>  
  
## <a name="return"></a><span data-ttu-id="a2712-118">Renvoie</span><span class="sxs-lookup"><span data-stu-id="a2712-118">Return</span></span>  
 <span data-ttu-id="a2712-119">Retourne une valeur `Variant`, ou `Nothing` si aucune correspondance n'est trouvée.</span><span class="sxs-lookup"><span data-stu-id="a2712-119">Returns a `Variant`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2712-120">Notes</span><span class="sxs-lookup"><span data-stu-id="a2712-120">Remarks</span></span>  
 <span data-ttu-id="a2712-121">Utilisez `Lookup` pour récupérer la valeur du dataset spécifié pour une paire nom/valeur où il y a une relation un-à-un.</span><span class="sxs-lookup"><span data-stu-id="a2712-121">Use `Lookup` to retrieve the value from the specified dataset for a name/value pair where there is a 1-to-1 relationship.</span></span> <span data-ttu-id="a2712-122">Par exemple, pour un champ d'ID dans une table, vous pouvez utiliser `Lookup` pour récupérer le champ Nom correspondant d'un dataset qui n'est pas lié à la région de données.</span><span class="sxs-lookup"><span data-stu-id="a2712-122">For example, for an ID field in a table, you can use `Lookup` to retrieve the corresponding Name field from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="a2712-123">La fonction `Lookup` effectue les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a2712-123">`Lookup` does the following:</span></span>  
  
-   <span data-ttu-id="a2712-124">Évalue l'expression source dans l'étendue actuelle.</span><span class="sxs-lookup"><span data-stu-id="a2712-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="a2712-125">Évalue l'expression de destination pour chaque ligne du dataset spécifié après avoir appliqué les filtres, en fonction du classement du dataset spécifié.</span><span class="sxs-lookup"><span data-stu-id="a2712-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="a2712-126">Pour la première correspondance des expressions source et de destination, évalue l'expression de résultat pour cette ligne dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="a2712-126">On the first match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="a2712-127">Renvoie la valeur d'expression de résultat.</span><span class="sxs-lookup"><span data-stu-id="a2712-127">Returns the result expression value.</span></span>  
  
 <span data-ttu-id="a2712-128">Pour récupérer plusieurs valeurs pour un seul champ de nom ou de clé dans lequel une relation un-à-plusieurs existe, utilisez [Fonction LookupSet &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-lookupset-function.md).</span><span class="sxs-lookup"><span data-stu-id="a2712-128">To retrieve multiple values for a single name or key field where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span> <span data-ttu-id="a2712-129">Pour appeler `Lookup` pour un ensemble de valeurs, utilisez la [fonction multilookup &#40;générateur de rapports et SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="a2712-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span>  
  
 <span data-ttu-id="a2712-130">Les restrictions suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="a2712-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="a2712-131">`Lookup`est évalué après que toutes les expressions de filtre ont été appliquées.</span><span class="sxs-lookup"><span data-stu-id="a2712-131">`Lookup` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="a2712-132">Un seul niveau de recherche est pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a2712-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="a2712-133">Une expression source, destination ou de résultat ne peut pas inclure de référence à une fonction de recherche.</span><span class="sxs-lookup"><span data-stu-id="a2712-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="a2712-134">Les expressions source et de destination doivent correspondre au même type de données.</span><span class="sxs-lookup"><span data-stu-id="a2712-134">Source and destination expressions must evaluate to the same data type.</span></span> <span data-ttu-id="a2712-135">Le type retourné est identique au type de données de l'expression de résultat évaluée.</span><span class="sxs-lookup"><span data-stu-id="a2712-135">The return type is the same as the data type of the evaluated result expression.</span></span>  
  
-   <span data-ttu-id="a2712-136">Les expressions source, de destination et de résultat ne peuvent pas inclure de références à des variables de groupe ou de rapport.</span><span class="sxs-lookup"><span data-stu-id="a2712-136">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="a2712-137">`Lookup` ne peut pas être utilisé comme expression pour les éléments de rapport suivants :</span><span class="sxs-lookup"><span data-stu-id="a2712-137">`Lookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="a2712-138">des chaînes de connexion dynamiques pour une source de données ;</span><span class="sxs-lookup"><span data-stu-id="a2712-138">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="a2712-139">des champs calculés dans un dataset ;</span><span class="sxs-lookup"><span data-stu-id="a2712-139">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="a2712-140">des paramètres de requête dans un dataset ;</span><span class="sxs-lookup"><span data-stu-id="a2712-140">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="a2712-141">des filtres dans un dataset ;</span><span class="sxs-lookup"><span data-stu-id="a2712-141">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="a2712-142">des paramètres de rapport ;</span><span class="sxs-lookup"><span data-stu-id="a2712-142">Report parameters.</span></span>  
  
    -   <span data-ttu-id="a2712-143">la propriété Report.Language.</span><span class="sxs-lookup"><span data-stu-id="a2712-143">The Report.Language property.</span></span>  
  
 <span data-ttu-id="a2712-144">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="a2712-144">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2712-145">Exemple</span><span class="sxs-lookup"><span data-stu-id="a2712-145">Example</span></span>  
 <span data-ttu-id="a2712-146">Dans l'exemple suivant, supposez qu'une table est liée à un dataset qui inclut un champ pour l'identificateur de produit ProductID.</span><span class="sxs-lookup"><span data-stu-id="a2712-146">In the following example, assume that a table is bound to a dataset that includes a field for the product identifier ProductID.</span></span> <span data-ttu-id="a2712-147">Un dataset distinct nommé « Product » contient l'identificateur de produit correspondant ID et le nom de produit Name.</span><span class="sxs-lookup"><span data-stu-id="a2712-147">A separate dataset called "Product" contains the corresponding product identifier ID and the product name Name.</span></span>  
  
 <span data-ttu-id="a2712-148">Dans l'expression suivante, `Lookup` compare la valeur de ProductID à ID sur chaque ligne du dataset nommé « Product » et, lorsqu'une correspondance est trouvée, renvoie la valeur du champ Name pour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="a2712-148">In the following expression, `Lookup` compares the value of ProductID to ID in each row of the dataset called "Product" and, when a match is found, returns the value of the Name field for that row.</span></span>  
  
```  
=Lookup(Fields!ProductID.Value, Fields!ID.Value, Fields!Name.Value, "Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2712-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a2712-149">See Also</span></span>  
 <span data-ttu-id="a2712-150">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a2712-150">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a2712-151">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a2712-151">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a2712-152">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a2712-152">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a2712-153">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a2712-153">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
