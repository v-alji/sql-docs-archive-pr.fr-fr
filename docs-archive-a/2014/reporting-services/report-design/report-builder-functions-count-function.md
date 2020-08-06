---
title: Fonction Count (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7b50b101-daf8-4fb0-ae04-57384755779f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3617e64d804b6b0f3d9522b5a089f418a942568a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613303"
---
# <a name="count-function-report-builder-and-ssrs"></a><span data-ttu-id="07bb5-102">Fonction Count (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="07bb5-102">Count Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="07bb5-103">Retourne le nombre de valeurs non Null spécifiées par l'expression, évaluée dans le contexte de l'étendue donnée.</span><span class="sxs-lookup"><span data-stu-id="07bb5-103">Returns a count of non-null values specified by the expression, evaluated in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="07bb5-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="07bb5-104">Syntax</span></span>  
  
```  
  
Count(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07bb5-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="07bb5-105">Parameters</span></span>  
 <span data-ttu-id="07bb5-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="07bb5-106">*expression*</span></span>  
 <span data-ttu-id="07bb5-107">(`Variant` ou `Binary`) Expression sur laquelle effectuer l'agrégation ; par exemple, `=Fields!FieldName.Value`.</span><span class="sxs-lookup"><span data-stu-id="07bb5-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!FieldName.Value`.</span></span>  
  
 <span data-ttu-id="07bb5-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="07bb5-108">*scope*</span></span>  
 <span data-ttu-id="07bb5-109">(`String`) Nom d'un dataset, d'un groupe ou d'une région de données qui contient les éléments de rapport auxquels appliquer la fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="07bb5-109">(`String`) The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="07bb5-110">Si le paramètre *scope* n'est pas spécifié, l'étendue actuelle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="07bb5-110">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="07bb5-111">*recursive*</span><span class="sxs-lookup"><span data-stu-id="07bb5-111">*recursive*</span></span>  
 <span data-ttu-id="07bb5-112">(**Type énuméré**) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="07bb5-112">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="07bb5-113">`Simple` (par défaut) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="07bb5-113">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="07bb5-114">Indique s'il faut effectuer l'agrégation de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="07bb5-114">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="07bb5-115">Type de retour</span><span class="sxs-lookup"><span data-stu-id="07bb5-115">Return Type</span></span>  
 <span data-ttu-id="07bb5-116">Retourne un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="07bb5-116">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07bb5-117">Notes</span><span class="sxs-lookup"><span data-stu-id="07bb5-117">Remarks</span></span>  
 <span data-ttu-id="07bb5-118">La valeur du paramètre *scope* doit être une constante de chaîne et ne peut pas être une expression.</span><span class="sxs-lookup"><span data-stu-id="07bb5-118">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="07bb5-119">Pour les agrégats externes ou les agrégats qui ne spécifient pas d'autres agrégats, le paramètre *scope* doit faire référence à l'étendue actuelle ou à une étendue contenante.</span><span class="sxs-lookup"><span data-stu-id="07bb5-119">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="07bb5-120">Pour les agrégats d'agrégats, les agrégats imbriqués peuvent spécifier une étendue enfant.</span><span class="sxs-lookup"><span data-stu-id="07bb5-120">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="07bb5-121">*Expression* peut contenir des appels aux fonctions d'agrégation imbriquées avec les exceptions et conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="07bb5-121">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="07bb5-122">Le paramètre*Scope* des agrégats imbriqués doit être identique à l'étendue de l'agrégat externe ou contenu par celle-ci.</span><span class="sxs-lookup"><span data-stu-id="07bb5-122">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="07bb5-123">Pour toutes les étendues distinctes de l'expression, une étendue doit figurer dans une relation enfant avec toutes les autres étendues.</span><span class="sxs-lookup"><span data-stu-id="07bb5-123">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="07bb5-124">Le paramètre*Scope* des agrégats imbriqués ne peut pas être le nom d'un dataset.</span><span class="sxs-lookup"><span data-stu-id="07bb5-124">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="07bb5-125">L' *expression* ne doit pas contenir `First` de fonctions, `Last` , `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="07bb5-125">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="07bb5-126">*Expression* ne doit pas contenir les agrégats imbriqués qui spécifient *recursive*.</span><span class="sxs-lookup"><span data-stu-id="07bb5-126">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="07bb5-127">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="07bb5-127">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="07bb5-128">Pour plus d’informations sur les agrégats récursifs, consultez [Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="07bb5-128">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="07bb5-129">Exemple</span><span class="sxs-lookup"><span data-stu-id="07bb5-129">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="07bb5-130">Description</span><span class="sxs-lookup"><span data-stu-id="07bb5-130">Description</span></span>  
 <span data-ttu-id="07bb5-131">L'exemple de code suivant affiche une expression qui calcule le nombre de valeurs non Null de `Size` pour l'étendue par défaut et pour une étendue de groupe parent.</span><span class="sxs-lookup"><span data-stu-id="07bb5-131">The following code example shows an expression that calculates the number of non-null values of `Size` for the default scope and for a parent group scope.</span></span> <span data-ttu-id="07bb5-132">L’expression est ajoutée à une cellule d’une ligne qui appartient au groupe enfant `GroupbySubcategory`.</span><span class="sxs-lookup"><span data-stu-id="07bb5-132">The expression is added to a cell in a row that belongs to the child group `GroupbySubcategory`.</span></span> <span data-ttu-id="07bb5-133">Le groupe parent est `GroupbyCategory`.</span><span class="sxs-lookup"><span data-stu-id="07bb5-133">The parent group is `GroupbyCategory`.</span></span> <span data-ttu-id="07bb5-134">L’expression affiche les résultats pour `GroupbySubcategory` (étendue par défaut) et pour `GroupbyCategory` (étendue de groupe parent).</span><span class="sxs-lookup"><span data-stu-id="07bb5-134">The expression displays the results for `GroupbySubcategory` (the default scope) and then for `GroupbyCategory` (the parent group scope).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07bb5-135">Les expressions ne doivent pas contenir de retours chariot ni de sauts de ligne réels ; ceux-ci sont inclus dans l'exemple pour prendre en charge des convertisseurs de documentation.</span><span class="sxs-lookup"><span data-stu-id="07bb5-135">Expressions should not contain actual carriage returns and line breaks; these are included in the example to support documentation renderers.</span></span> <span data-ttu-id="07bb5-136">Si vous copiez l'exemple suivant, supprimez les retours chariot de chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="07bb5-136">If you copy the following example, remove carriage returns from each line.</span></span>  
  
## <a name="code"></a><span data-ttu-id="07bb5-137">Code</span><span class="sxs-lookup"><span data-stu-id="07bb5-137">Code</span></span>  
  
```  
="Count (Subcategory): " & Count(Fields!Size.Value) &   
"Count (Category): " & Count(Fields!Size.Value,"GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="07bb5-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07bb5-138">See Also</span></span>  
 <span data-ttu-id="07bb5-139">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07bb5-139">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07bb5-140">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07bb5-140">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07bb5-141">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07bb5-141">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="07bb5-142">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="07bb5-142">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
