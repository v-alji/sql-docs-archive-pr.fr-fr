---
title: Fonction Sum (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2b45a024-398d-43b8-9948-b8b23fb674c9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3fce5e86ead5e2d802c7af79650e7419f45f62c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605136"
---
# <a name="sum-function-report-builder-and-ssrs"></a><span data-ttu-id="07ab2-102">Fonction Sum (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="07ab2-102">Sum Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="07ab2-103">Retourne la somme de toutes les valeurs numériques non Null spécifiées par l'expression, évaluée dans l'étendue donnée.</span><span class="sxs-lookup"><span data-stu-id="07ab2-103">Returns the sum of all the non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="07ab2-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="07ab2-104">Syntax</span></span>  
  
```  
  
Sum(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07ab2-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="07ab2-105">Parameters</span></span>  
 <span data-ttu-id="07ab2-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="07ab2-106">*expression*</span></span>  
 <span data-ttu-id="07ab2-107">(`Integer` ou `Float`) Expression sur laquelle effectuer l'agrégation.</span><span class="sxs-lookup"><span data-stu-id="07ab2-107">(`Integer` or `Float`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="07ab2-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="07ab2-108">*scope*</span></span>  
 <span data-ttu-id="07ab2-109">(`String`) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="07ab2-109">(`String`) Optional.</span></span> <span data-ttu-id="07ab2-110">Nom d'un dataset, d'un groupe ou d'une région de données qui contient les éléments de rapport auxquels appliquer la fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="07ab2-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="07ab2-111">Si le paramètre *scope* n'est pas spécifié, l'étendue actuelle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="07ab2-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="07ab2-112">*recursive*</span><span class="sxs-lookup"><span data-stu-id="07ab2-112">*recursive*</span></span>  
 <span data-ttu-id="07ab2-113">(**Type énuméré**) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="07ab2-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="07ab2-114">`Simple` (par défaut) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="07ab2-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="07ab2-115">Indique s'il faut effectuer l'agrégation de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="07ab2-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="07ab2-116">Type de retour</span><span class="sxs-lookup"><span data-stu-id="07ab2-116">Return Type</span></span>  
 <span data-ttu-id="07ab2-117">Retourne une valeur `Decimal` pour les expressions décimales et une valeur `Double` pour toutes les autres expressions.</span><span class="sxs-lookup"><span data-stu-id="07ab2-117">Returns a `Decimal` for decimal expressions and a `Double` for all other expressions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07ab2-118">Notes</span><span class="sxs-lookup"><span data-stu-id="07ab2-118">Remarks</span></span>  
 <span data-ttu-id="07ab2-119">Le jeu de données spécifié dans l'expression doit avoir le même type de données.</span><span class="sxs-lookup"><span data-stu-id="07ab2-119">The set of data specified in the expression must have the same data type.</span></span> <span data-ttu-id="07ab2-120">Pour convertir des données qui ont plusieurs types de données numériques en un même type de données, utilisez des fonctions de conversion telles que `CInt`, `CDbl` ou `CDec`.</span><span class="sxs-lookup"><span data-stu-id="07ab2-120">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="07ab2-121">Pour plus d'informations, consultez [Fonctions de conversion de types de données](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="07ab2-121">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="07ab2-122">La valeur du paramètre *scope* doit être une constante de chaîne et ne peut pas être une expression.</span><span class="sxs-lookup"><span data-stu-id="07ab2-122">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="07ab2-123">Pour les agrégats externes ou les agrégats qui ne spécifient pas d'autres agrégats, le paramètre *scope* doit faire référence à l'étendue actuelle ou à une étendue contenante.</span><span class="sxs-lookup"><span data-stu-id="07ab2-123">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="07ab2-124">Pour les agrégats d'agrégats, les agrégats imbriqués peuvent spécifier une étendue enfant.</span><span class="sxs-lookup"><span data-stu-id="07ab2-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="07ab2-125">*Expression* peut contenir des appels aux fonctions d'agrégation imbriquées avec les exceptions et conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="07ab2-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="07ab2-126">Le paramètre*Scope* des agrégats imbriqués doit être identique à l'étendue de l'agrégat externe ou contenu par celle-ci.</span><span class="sxs-lookup"><span data-stu-id="07ab2-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="07ab2-127">Pour toutes les étendues distinctes de l'expression, une étendue doit figurer dans une relation enfant avec toutes les autres étendues.</span><span class="sxs-lookup"><span data-stu-id="07ab2-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="07ab2-128">Le paramètre*Scope* des agrégats imbriqués ne peut pas être le nom d'un dataset.</span><span class="sxs-lookup"><span data-stu-id="07ab2-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="07ab2-129">L' *expression* ne doit pas contenir `First` de fonctions, `Last` , `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="07ab2-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="07ab2-130">*Expression* ne doit pas contenir les agrégats imbriqués qui spécifient *recursive*.</span><span class="sxs-lookup"><span data-stu-id="07ab2-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="07ab2-131">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="07ab2-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="07ab2-132">Pour plus d’informations sur les agrégats récursifs, consultez [Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="07ab2-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="07ab2-133">Exemple</span><span class="sxs-lookup"><span data-stu-id="07ab2-133">Example</span></span>  
 <span data-ttu-id="07ab2-134">Les deux exemples de code ci-dessous fournissent une somme des totaux d'articles dans le groupe ou la région de données `Order` .</span><span class="sxs-lookup"><span data-stu-id="07ab2-134">The following two code examples provides a sum of line item totals in the `Order` group or data region.</span></span>  
  
```  
=Sum(Fields!LineTotal.Value, "Order")  
' or   
=Sum(CDbl(Fields!LineTotal.Value), "Order")  
```  
  
## <a name="example"></a><span data-ttu-id="07ab2-135">Exemple</span><span class="sxs-lookup"><span data-stu-id="07ab2-135">Example</span></span>  
 <span data-ttu-id="07ab2-136">Dans une région de données de matrice avec les groupes de lignes imbriqués Catégorie et Sous-catégorie et les groupes de colonnes imbriqués Année et Trimestre, dans une cellule qui appartient aux groupes de lignes et de colonnes les plus profonds, l'expression suivante correspond à la valeur maximale de tous les trimestres pour toutes les sous-catégories.</span><span class="sxs-lookup"><span data-stu-id="07ab2-136">In a matrix data region with nested row groups Category and Subcategory, and nested column groups Year and Quarter, in a cell that belongs to the innermost row and column groups, the following expression evaluates to the maximum value from all quarters for all subcategories.</span></span>  
  
```  
=Max(Sum(Fields!Sales.Value))  
```  
  
## <a name="see-also"></a><span data-ttu-id="07ab2-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07ab2-137">See Also</span></span>  
 <span data-ttu-id="07ab2-138">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07ab2-138">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07ab2-139">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07ab2-139">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="07ab2-140">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="07ab2-140">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="07ab2-141">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="07ab2-141">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
