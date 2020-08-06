---
title: Fonction Previous (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 403a9384-6ca4-42e8-97ca-ac3f6fe4316b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3891deec3f152cdf46da77a7f2d11d38387c5c8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605153"
---
# <a name="previous-function-report-builder-and-ssrs"></a><span data-ttu-id="f1d95-102">Fonction Previous (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="f1d95-102">Previous Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f1d95-103">Retourne la valeur ou la valeur d'agrégation spécifiée pour l'instance précédente d'un élément dans l'étendue spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f1d95-103">Returns the value or the specified aggregate value for the previous instance of an item within the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="f1d95-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f1d95-104">Syntax</span></span>  
  
```  
  
Previous(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1d95-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="f1d95-105">Parameters</span></span>  
 <span data-ttu-id="f1d95-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="f1d95-106">*expression*</span></span>  
 <span data-ttu-id="f1d95-107">(`Variant` ou `Binary`) Expression à utiliser pour identifier les données et pour laquelle récupérer la valeur précédente, par exemple, `Fields!Fieldname.Value` ou `Sum(Fields!Fieldname.Value)`.</span><span class="sxs-lookup"><span data-stu-id="f1d95-107">(`Variant` or `Binary`) The expression to use to identify the data and for which to retrieve the previous value, for example, `Fields!Fieldname.Value` or `Sum(Fields!Fieldname.Value)`.</span></span>  
  
 <span data-ttu-id="f1d95-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="f1d95-108">*scope*</span></span>  
 <span data-ttu-id="f1d95-109">(`String`) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="f1d95-109">(`String`) Optional.</span></span> <span data-ttu-id="f1d95-110">Nom d’un groupe ou d’une région de données, ou valeur null ( `Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ), qui spécifie l’étendue à partir de laquelle récupérer la valeur précédente spécifiée par *expression*.</span><span class="sxs-lookup"><span data-stu-id="f1d95-110">The name of a group or data region, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the scope from which to retrieve the previous value specified by *expression*.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="f1d95-111">Type de retour</span><span class="sxs-lookup"><span data-stu-id="f1d95-111">Return Type</span></span>  
 <span data-ttu-id="f1d95-112">Retourne un type `Variant` ou `Binary`.</span><span class="sxs-lookup"><span data-stu-id="f1d95-112">Returns a `Variant` or `Binary`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1d95-113">Notes</span><span class="sxs-lookup"><span data-stu-id="f1d95-113">Remarks</span></span>  
 <span data-ttu-id="f1d95-114">La fonction `Previous` retourne la valeur précédente de l'expression évaluée dans l'étendue spécifiée après que cette dernière a été correctement triée et filtrée.</span><span class="sxs-lookup"><span data-stu-id="f1d95-114">The `Previous` function returns the previous value for the expression evaluated in the specified scope after all sorting and filtering have been applied.</span></span>  
  
 <span data-ttu-id="f1d95-115">Si l' *expression* ne contient pas d’agrégat, la `Previous` fonction utilise par défaut l’étendue actuelle de l’élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="f1d95-115">If *expression* does not contain an aggregate, the `Previous` function defaults to the current scope for the report item.</span></span>  
  
 <span data-ttu-id="f1d95-116">Dans le groupe de détails, utilisez `Previous` pour spécifier la valeur d'une référence de champ dans l'instance précédente de la ligne de détails.</span><span class="sxs-lookup"><span data-stu-id="f1d95-116">In a details group, use `Previous` to specify the value of a field reference in the previous instance of the detail row.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1d95-117">La `Previous` fonction ne prend en charge que les références de champ dans le groupe de détails.</span><span class="sxs-lookup"><span data-stu-id="f1d95-117">The `Previous` function only supports field references in the details group.</span></span> <span data-ttu-id="f1d95-118">Par exemple, dans une zone de texte du groupe de détails, `=Previous(Fields!Quantity.Value)` retourne les données du champ `Quantity` de la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="f1d95-118">For example, in a text box in the details group, `=Previous(Fields!Quantity.Value)` returns the data for the field `Quantity` from the previous row.</span></span> <span data-ttu-id="f1d95-119">Cette expression dans la première ligne retourne une valeur Null (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="f1d95-119">In the first row, this expression returns a null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  
  
 <span data-ttu-id="f1d95-120">Si *expression* contient une fonction d’agrégation qui utilise une étendue par défaut, `Previous` agrège les données dans l’instance précédente de l’étendue spécifiée dans l’appel de la fonction d’agrégation.</span><span class="sxs-lookup"><span data-stu-id="f1d95-120">If *expression* contains an aggregate function that uses a default scope, `Previous` aggregates the data within the previous instance of the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="f1d95-121">Si *expression* contient une fonction d’agrégation qui spécifie une étendue autre que la valeur par défaut, le paramètre *scope* de la `Previous` fonction doit être une étendue contenante pour l’étendue spécifiée dans l’appel de la fonction d’agrégation.</span><span class="sxs-lookup"><span data-stu-id="f1d95-121">If *expression* contains an aggregate function that specifies a scope other than the default, the *scope* parameter for the `Previous` function must be a containing scope for the scope specified in the aggregate function call.</span></span>  
  
 <span data-ttu-id="f1d95-122">Les fonctions `Level` , `InScope` `Aggregate` et `Previous` ne peuvent pas être utilisées dans le paramètre d' *expression*.</span><span class="sxs-lookup"><span data-stu-id="f1d95-122">The functions `Level`, `InScope`, `Aggregate` and `Previous` cannot be used in the *expression*parameter.</span></span> <span data-ttu-id="f1d95-123">La spécification du paramètre *recursive* pour une fonction d’agrégation n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="f1d95-123">Specifying the *recursive* parameter for any aggregate function is not supported.</span></span>  
  
 <span data-ttu-id="f1d95-124">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="f1d95-124">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f1d95-125">Exemples</span><span class="sxs-lookup"><span data-stu-id="f1d95-125">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="f1d95-126">Description</span><span class="sxs-lookup"><span data-stu-id="f1d95-126">Description</span></span>  
 <span data-ttu-id="f1d95-127">L’exemple de code ci-dessous, quand il est placé sur la ligne de données par défaut d’une région de données, fournit la valeur du champ `LineTotal` de la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="f1d95-127">The following code example, when placed in the default data row of a data region, provides the value for the field `LineTotal` in the previous row.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f1d95-128">Code</span><span class="sxs-lookup"><span data-stu-id="f1d95-128">Code</span></span>  
  
```  
=Previous(Fields!LineTotal.Value)  
```  
  
### <a name="description"></a><span data-ttu-id="f1d95-129">Description</span><span class="sxs-lookup"><span data-stu-id="f1d95-129">Description</span></span>  
 <span data-ttu-id="f1d95-130">L'exemple suivant montre une expression qui calcule la somme des ventes réalisées au cours d'un jour spécifique du mois et la valeur précédente pour le même jour du mois d'une année précédente.</span><span class="sxs-lookup"><span data-stu-id="f1d95-130">The following example shows an expression that calculates the sum of sales on a specific day of the month and the previous value for that day of the month in a previous year.</span></span> <span data-ttu-id="f1d95-131">L’expression est ajoutée à une cellule d’une ligne qui appartient au groupe enfant `GroupbyDay`.</span><span class="sxs-lookup"><span data-stu-id="f1d95-131">The expression is added to a cell in a row that belongs to the child group `GroupbyDay`.</span></span> <span data-ttu-id="f1d95-132">Son groupe parent est `GroupbyMonth`, ayant lui-même le groupe parent `GroupbyYear`.</span><span class="sxs-lookup"><span data-stu-id="f1d95-132">Its parent group is `GroupbyMonth`, which has a parent group `GroupbyYear`.</span></span> <span data-ttu-id="f1d95-133">L'expression affiche les résultats pour GroupbyDay (étendue par défaut), puis pour `GroupbyYear` (le parent du groupe parent `GroupbyMonth`).</span><span class="sxs-lookup"><span data-stu-id="f1d95-133">The expression displays the results for GroupbyDay (the default scope) and then for `GroupbyYear` (the parent of the parent group `GroupbyMonth`).</span></span>  
  
 <span data-ttu-id="f1d95-134">Par exemple, pour une région de données avec un groupe parent nommé `Year`, son groupe enfant nommé `Month`et son groupe enfant nommé `Day` (3 niveaux imbriqués).</span><span class="sxs-lookup"><span data-stu-id="f1d95-134">For example, for a data region with a parent group named `Year`, its child group named `Month`, and its child group named `Day` (3 nested levels).</span></span> <span data-ttu-id="f1d95-135">L’expression `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` d’une ligne associée au groupe `Day` retourne la valeur des ventes réalisées le même jour du même mois de l’année précédente.</span><span class="sxs-lookup"><span data-stu-id="f1d95-135">The expression `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` in a row associated with the group `Day` returns the sales value for the same day and month for the previous year.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f1d95-136">Code</span><span class="sxs-lookup"><span data-stu-id="f1d95-136">Code</span></span>  
  
```  
=Sum(Fields!Sales.Value) & " " & Previous(Sum(Fields!Sales.Value,"GroupbyDay"),"GroupbyYear")  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1d95-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1d95-137">See Also</span></span>  
 <span data-ttu-id="f1d95-138">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f1d95-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f1d95-139">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f1d95-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="f1d95-140">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f1d95-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f1d95-141">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f1d95-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
