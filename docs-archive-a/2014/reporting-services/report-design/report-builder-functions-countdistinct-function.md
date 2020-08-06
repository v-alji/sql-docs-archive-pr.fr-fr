---
title: Fonction CountDistinct (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 902c251e-e1e8-41d2-ac20-5bb6138ac410
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62fab53d4f26a874ac40e0a915c4242a41c72ce0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605176"
---
# <a name="countdistinct-function-report-builder-and-ssrs"></a><span data-ttu-id="ad994-102">Fonction CountDistinct (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ad994-102">CountDistinct Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ad994-103">Retourne le nombre de toutes les valeurs non Null distinctes spécifiées par l'expression, évaluée dans le contexte de l'étendue donnée.</span><span class="sxs-lookup"><span data-stu-id="ad994-103">Returns a count of all distinct non-null values specified by the expression, evaluated in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="ad994-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ad994-104">Syntax</span></span>  
  
```  
  
CountDistinct(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad994-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ad994-105">Parameters</span></span>  
 <span data-ttu-id="ad994-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="ad994-106">*expression*</span></span>  
 <span data-ttu-id="ad994-107">(`Variant`) Expression sur laquelle effectuer l'agrégation.</span><span class="sxs-lookup"><span data-stu-id="ad994-107">(`Variant`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="ad994-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="ad994-108">*scope*</span></span>  
 <span data-ttu-id="ad994-109">(`String`) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="ad994-109">(`String`) Optional.</span></span> <span data-ttu-id="ad994-110">Nom d'un dataset, d'un groupe ou d'une région de données qui contient les éléments de rapport auxquels appliquer la fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="ad994-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="ad994-111">Si le paramètre *scope* n'est pas spécifié, l'étendue actuelle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="ad994-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="ad994-112">*recursive*</span><span class="sxs-lookup"><span data-stu-id="ad994-112">*recursive*</span></span>  
 <span data-ttu-id="ad994-113">(**Type énuméré**) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="ad994-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="ad994-114">`Simple` (par défaut) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="ad994-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="ad994-115">Indique s'il faut effectuer l'agrégation de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="ad994-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="ad994-116">Type de retour</span><span class="sxs-lookup"><span data-stu-id="ad994-116">Return Type</span></span>  
 <span data-ttu-id="ad994-117">Retourne un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="ad994-117">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad994-118">Notes</span><span class="sxs-lookup"><span data-stu-id="ad994-118">Remarks</span></span>  
 <span data-ttu-id="ad994-119">La valeur du paramètre *scope* doit être une constante de chaîne et ne peut pas être une expression.</span><span class="sxs-lookup"><span data-stu-id="ad994-119">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="ad994-120">Pour les agrégats externes ou les agrégats qui ne spécifient pas d'autres agrégats, le paramètre *scope* doit faire référence à l'étendue actuelle ou à une étendue contenante.</span><span class="sxs-lookup"><span data-stu-id="ad994-120">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="ad994-121">Pour les agrégats d'agrégats, les agrégats imbriqués peuvent spécifier une étendue enfant.</span><span class="sxs-lookup"><span data-stu-id="ad994-121">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="ad994-122">*Expression* peut contenir des appels aux fonctions d'agrégation imbriquées avec les exceptions et conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ad994-122">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="ad994-123">Le paramètre*Scope* des agrégats imbriqués doit être identique à l'étendue de l'agrégat externe ou contenu par celle-ci.</span><span class="sxs-lookup"><span data-stu-id="ad994-123">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="ad994-124">Pour toutes les étendues distinctes de l'expression, une étendue doit figurer dans une relation enfant avec toutes les autres étendues.</span><span class="sxs-lookup"><span data-stu-id="ad994-124">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="ad994-125">Le paramètre*Scope* des agrégats imbriqués ne peut pas être le nom d'un dataset.</span><span class="sxs-lookup"><span data-stu-id="ad994-125">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="ad994-126">L' *expression* ne doit pas contenir `First` de fonctions, `Last` , `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="ad994-126">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="ad994-127">*Expression* ne doit pas contenir les agrégats imbriqués qui spécifient *recursive*.</span><span class="sxs-lookup"><span data-stu-id="ad994-127">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="ad994-128">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="ad994-128">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="ad994-129">Pour plus d’informations sur les agrégats récursifs, consultez [Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ad994-129">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad994-130">Exemple</span><span class="sxs-lookup"><span data-stu-id="ad994-130">Example</span></span>  
 <span data-ttu-id="ad994-131">L’exemple de code suivant affiche une expression qui calcule le nombre de valeurs non Null uniques de `Size` pour l’étendue par défaut et pour une étendue de groupe parent.</span><span class="sxs-lookup"><span data-stu-id="ad994-131">The following code example shows an expression that calculates the number of unique non-null values of `Size` for the default scope and for a parent group scope.</span></span> <span data-ttu-id="ad994-132">L’expression est ajoutée à une cellule d’une ligne qui appartient au groupe enfant `GroupbySubcategory`.</span><span class="sxs-lookup"><span data-stu-id="ad994-132">The expression is added to a cell in a row that belongs to the child group `GroupbySubcategory`.</span></span> <span data-ttu-id="ad994-133">Le groupe parent est `GroupbyCategory`.</span><span class="sxs-lookup"><span data-stu-id="ad994-133">The parent group is `GroupbyCategory`.</span></span> <span data-ttu-id="ad994-134">L’expression affiche les résultats pour `GroupbySubcategory` (étendue par défaut) et pour `GroupbyCategory` (étendue de groupe parent).</span><span class="sxs-lookup"><span data-stu-id="ad994-134">The expression displays the results for `GroupbySubcategory` (the default scope) and then for `GroupbyCategory` (the parent group scope).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad994-135">Les expressions ne doivent pas contenir de retours chariot ni de sauts de ligne réels ; ceux-ci sont inclus dans l'exemple de code pour prendre en charge des convertisseurs de documentation.</span><span class="sxs-lookup"><span data-stu-id="ad994-135">Expressions should not contain actual carriage returns and line breaks; these are included in the example code to support documentation renderers.</span></span> <span data-ttu-id="ad994-136">Si vous copiez l'exemple suivant, supprimez les retours chariot de chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="ad994-136">If you copy the following example, remove carriage returns from each line.</span></span>  
  
```  
="Distinct count (Subcategory): " & CountDistinct(Fields!Size.Value) &   
"Distinct count (Category): " & CountDistinct(Fields!Size.Value,"GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad994-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ad994-137">See Also</span></span>  
 <span data-ttu-id="ad994-138">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ad994-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ad994-139">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ad994-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ad994-140">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ad994-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ad994-141">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ad994-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
