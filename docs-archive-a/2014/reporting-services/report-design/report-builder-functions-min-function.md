---
title: Fonction Min (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aa1ee96f-9fc4-4775-b9d4-c6187dc37e27
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 82bb852eeb334a0c7bde3e157f0035db766039da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605160"
---
# <a name="min-function-report-builder-and-ssrs"></a><span data-ttu-id="5ef00-102">Fonction Min (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="5ef00-102">Min Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5ef00-103">Retourne la valeur minimale de toutes les valeurs numériques non Null spécifiées par l'expression, dans le contexte de l'étendue donnée.</span><span class="sxs-lookup"><span data-stu-id="5ef00-103">Returns the minimum value of all non-null numeric values specified by the expression, in the context of the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="5ef00-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5ef00-104">Syntax</span></span>  
  
```  
  
Min(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ef00-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5ef00-105">Parameters</span></span>  
 <span data-ttu-id="5ef00-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="5ef00-106">*expression*</span></span>  
 <span data-ttu-id="5ef00-107">(`Variant`) Expression sur laquelle effectuer l'agrégation.</span><span class="sxs-lookup"><span data-stu-id="5ef00-107">(`Variant`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="5ef00-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="5ef00-108">*scope*</span></span>  
 <span data-ttu-id="5ef00-109">(`String`) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="5ef00-109">(`String`) Optional.</span></span> <span data-ttu-id="5ef00-110">Nom d'un dataset, d'un groupe ou d'une région de données qui contient les éléments de rapport auxquels appliquer la fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="5ef00-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="5ef00-111">Si le paramètre *scope* n'est pas spécifié, l'étendue actuelle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="5ef00-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="5ef00-112">*recursive*</span><span class="sxs-lookup"><span data-stu-id="5ef00-112">*recursive*</span></span>  
 <span data-ttu-id="5ef00-113">(**Type énuméré**) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="5ef00-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="5ef00-114">`Simple` (par défaut) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="5ef00-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="5ef00-115">Indique s'il faut effectuer l'agrégation de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="5ef00-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="5ef00-116">Type de retour</span><span class="sxs-lookup"><span data-stu-id="5ef00-116">Return Type</span></span>  
 <span data-ttu-id="5ef00-117">Déterminé par le type de l'expression.</span><span class="sxs-lookup"><span data-stu-id="5ef00-117">Determined by the type of the expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ef00-118">Notes</span><span class="sxs-lookup"><span data-stu-id="5ef00-118">Remarks</span></span>  
 <span data-ttu-id="5ef00-119">Le jeu de données spécifié dans l'expression doit avoir le même type de données.</span><span class="sxs-lookup"><span data-stu-id="5ef00-119">The set of data specified in the expression must have the same data type.</span></span> <span data-ttu-id="5ef00-120">Pour convertir des données qui ont plusieurs types de données numériques en un même type de données, utilisez des fonctions de conversion telles que `CInt`, `CDbl` ou `CDec`.</span><span class="sxs-lookup"><span data-stu-id="5ef00-120">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="5ef00-121">Pour plus d'informations, consultez [Fonctions de conversion de types de données](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="5ef00-121">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="5ef00-122">La valeur du paramètre *scope* doit être une constante de chaîne et ne peut pas être une expression.</span><span class="sxs-lookup"><span data-stu-id="5ef00-122">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="5ef00-123">Pour les agrégats externes ou les agrégats qui ne spécifient pas d'autres agrégats, le paramètre *scope* doit faire référence à l'étendue actuelle ou à une étendue contenante.</span><span class="sxs-lookup"><span data-stu-id="5ef00-123">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="5ef00-124">Pour les agrégats d'agrégats, les agrégats imbriqués peuvent spécifier une étendue enfant.</span><span class="sxs-lookup"><span data-stu-id="5ef00-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="5ef00-125">*Expression* peut contenir des appels aux fonctions d'agrégation imbriquées avec les exceptions et conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="5ef00-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="5ef00-126">Le paramètre*Scope* des agrégats imbriqués doit être identique à l'étendue de l'agrégat externe ou contenu par celle-ci.</span><span class="sxs-lookup"><span data-stu-id="5ef00-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="5ef00-127">Pour toutes les étendues distinctes de l'expression, une étendue doit figurer dans une relation enfant avec toutes les autres étendues.</span><span class="sxs-lookup"><span data-stu-id="5ef00-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="5ef00-128">Le paramètre*Scope* des agrégats imbriqués ne peut pas être le nom d'un dataset.</span><span class="sxs-lookup"><span data-stu-id="5ef00-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="5ef00-129">L' *expression* ne doit pas contenir `First` de fonctions, `Last` , `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="5ef00-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="5ef00-130">*Expression* ne doit pas contenir les agrégats imbriqués qui spécifient *recursive*.</span><span class="sxs-lookup"><span data-stu-id="5ef00-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="5ef00-131">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="5ef00-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="5ef00-132">Pour plus d’informations sur les agrégats récursifs, consultez [Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5ef00-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ef00-133">Exemple</span><span class="sxs-lookup"><span data-stu-id="5ef00-133">Example</span></span>  
 <span data-ttu-id="5ef00-134">L'exemple de code ci-dessous fournit le total le plus faible de l'étendue actuelle.</span><span class="sxs-lookup"><span data-stu-id="5ef00-134">The following code example provides the lowest total in the current scope.</span></span>  
  
```  
=Min(Fields!OrderTotal.Value)  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ef00-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ef00-135">See Also</span></span>  
 <span data-ttu-id="5ef00-136">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5ef00-136">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5ef00-137">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5ef00-137">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5ef00-138">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5ef00-138">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5ef00-139">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5ef00-139">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
