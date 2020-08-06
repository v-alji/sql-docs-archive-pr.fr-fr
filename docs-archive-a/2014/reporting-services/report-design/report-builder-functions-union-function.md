---
title: Fonction Union (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c87e16fe-c12a-4c9d-a9df-7a94e229fd04
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c80926be53254ec512b2189c4b67e8cd5885733f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605140"
---
# <a name="union-function-report-builder-and-ssrs"></a><span data-ttu-id="aa6a0-102">Fonction Union (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="aa6a0-102">Union Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="aa6a0-103">Retourne l'union de toutes les valeurs numériques non Null spécifiées par l'expression, évaluée dans l'étendue donnée.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-103">Returns the union of all the non-null numeric values specified by the expression, evaluated in the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="aa6a0-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="aa6a0-104">Syntax</span></span>  
  
```  
  
Union(expression, scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa6a0-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="aa6a0-105">Parameters</span></span>  
 <span data-ttu-id="aa6a0-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="aa6a0-106">*expression*</span></span>  
 <span data-ttu-id="aa6a0-107">(`SqlGeometry` ou `SqlGeography`) Expression sur laquelle effectuer l'agrégation.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-107">(`SqlGeometry` or `SqlGeography`) The expression on which to perform the aggregation.</span></span>  
  
 <span data-ttu-id="aa6a0-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="aa6a0-108">*scope*</span></span>  
 <span data-ttu-id="aa6a0-109">(`String`) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-109">(`String`) Optional.</span></span> <span data-ttu-id="aa6a0-110">Nom d'un dataset, d'un groupe ou d'une région de données qui contient les éléments de rapport auxquels appliquer la fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="aa6a0-111">Si le paramètre *scope* n'est pas spécifié, l'étendue actuelle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-111">If *scope* is not specified, the current scope is used.</span></span>  
  
 <span data-ttu-id="aa6a0-112">*recursive*</span><span class="sxs-lookup"><span data-stu-id="aa6a0-112">*recursive*</span></span>  
 <span data-ttu-id="aa6a0-113">(**Type énuméré**) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-113">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="aa6a0-114">`Simple` (par défaut) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-114">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="aa6a0-115">Indique s'il faut effectuer l'agrégation de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-115">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return"></a><span data-ttu-id="aa6a0-116">Renvoie</span><span class="sxs-lookup"><span data-stu-id="aa6a0-116">Return</span></span>  
 <span data-ttu-id="aa6a0-117">Retourne un objet spatial, `SqlGeometry` ou `SqlGeography`, selon le type d'expression.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-117">Returns a spatial object, either `SqlGeometry` or `SqlGeography`, based on the expression type.</span></span> <span data-ttu-id="aa6a0-118">Pour plus d’informations sur `SqlGeometry` les `SqlGeography` types de données spatiales et, consultez [vue d’ensemble des types de données spatiales](../../relational-databases/spatial/spatial-data-types-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aa6a0-118">For more information about `SqlGeometry` and `SqlGeography` spatial data types, see [Spatial Data Types Overview](../../relational-databases/spatial/spatial-data-types-overview.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa6a0-119">Notes</span><span class="sxs-lookup"><span data-stu-id="aa6a0-119">Remarks</span></span>  
 <span data-ttu-id="aa6a0-120">Le jeu de données spécifié dans l'expression doit avoir le même type de données.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-120">The set of data specified in the expression must have the same data type.</span></span>  
  
 <span data-ttu-id="aa6a0-121">La valeur du paramètre *scope* doit être une constante de chaîne et ne peut pas être une expression.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-121">The value of *scope* must be a string constant and cannot be an expression.</span></span> <span data-ttu-id="aa6a0-122">Pour les agrégats externes ou les agrégats qui ne spécifient pas d'autres agrégats, le paramètre *scope* doit faire référence à l'étendue actuelle ou à une étendue contenante.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-122">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="aa6a0-123">Les étendues de dataset ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-123">Dataset scopes are not supported.</span></span> <span data-ttu-id="aa6a0-124">Pour les agrégats d'agrégats, les agrégats imbriqués peuvent spécifier une étendue enfant.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-124">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="aa6a0-125">*Expression* peut contenir des appels aux fonctions d'agrégation imbriquées avec les exceptions et conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="aa6a0-125">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="aa6a0-126">Le paramètre*Scope* des agrégats imbriqués doit être identique à l'étendue de l'agrégat externe ou contenu par celle-ci.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-126">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="aa6a0-127">Pour toutes les étendues distinctes de l'expression, une étendue doit figurer dans une relation enfant avec toutes les autres étendues.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-127">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="aa6a0-128">Le paramètre*Scope* des agrégats imbriqués ne peut pas être le nom d'un dataset.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-128">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="aa6a0-129">L' *expression* ne doit pas contenir `First` de fonctions, `Last` , `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="aa6a0-129">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="aa6a0-130">*Expression* ne doit pas contenir les agrégats imbriqués qui spécifient *recursive*.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-130">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="aa6a0-131">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="aa6a0-131">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="aa6a0-132">Pour plus d’informations sur les agrégats récursifs, consultez [Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="aa6a0-132">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa6a0-133">Exemple</span><span class="sxs-lookup"><span data-stu-id="aa6a0-133">Example</span></span>  
 <span data-ttu-id="aa6a0-134">Le tableau suivant montre des exemples d'expressions `SqlGeometry` et d'expressions de résultat de la fonction `Union`, affichés au format de données spatiales WKT (Well-Known Text).</span><span class="sxs-lookup"><span data-stu-id="aa6a0-134">The following table shows examples of `SqlGeometry` expressions and `Union` result expression, shown in WKT (Well Known Text) format for spatial data.</span></span>  
  
|<span data-ttu-id="aa6a0-135">Champ avec données spatiales</span><span class="sxs-lookup"><span data-stu-id="aa6a0-135">Field with spatial data</span></span>|<span data-ttu-id="aa6a0-136">Exemple</span><span class="sxs-lookup"><span data-stu-id="aa6a0-136">Example</span></span>|<span data-ttu-id="aa6a0-137">Résultat de la fonction Union</span><span class="sxs-lookup"><span data-stu-id="aa6a0-137">Union result</span></span>|  
|-----------------------------|-------------|------------------|  
|<span data-ttu-id="aa6a0-138">[PointLocation]</span><span class="sxs-lookup"><span data-stu-id="aa6a0-138">[PointLocation]</span></span>|<span data-ttu-id="aa6a0-139">POINT(1 2)</span><span class="sxs-lookup"><span data-stu-id="aa6a0-139">POINT(1 2)</span></span><br /><br /> <span data-ttu-id="aa6a0-140">POINT (3 4)</span><span class="sxs-lookup"><span data-stu-id="aa6a0-140">POINT(3 4)</span></span>|<span data-ttu-id="aa6a0-141">MULTIPOINT((1 2), (3 4))</span><span class="sxs-lookup"><span data-stu-id="aa6a0-141">MULTIPOINT((1 2), (3 4))</span></span>|  
|<span data-ttu-id="aa6a0-142">[PathDefinition]</span><span class="sxs-lookup"><span data-stu-id="aa6a0-142">[PathDefinition]</span></span>|<span data-ttu-id="aa6a0-143">LINESTRING(1 2, 3 4)</span><span class="sxs-lookup"><span data-stu-id="aa6a0-143">LINESTRING(1 2, 3 4)</span></span><br /><br /> <span data-ttu-id="aa6a0-144">LINESTRING(5 6, 7 8)</span><span class="sxs-lookup"><span data-stu-id="aa6a0-144">LINESTRING(5 6, 7 8)</span></span>|<span data-ttu-id="aa6a0-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span><span class="sxs-lookup"><span data-stu-id="aa6a0-145">MULTILINESTRING((7 8, 5 6), (3 4, 1 2))</span></span>|  
|<span data-ttu-id="aa6a0-146">[PolygonDefinition]</span><span class="sxs-lookup"><span data-stu-id="aa6a0-146">[PolygonDefinition]</span></span>|<span data-ttu-id="aa6a0-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span><span class="sxs-lookup"><span data-stu-id="aa6a0-147">POLYGON((1 2, 3 4, 5 2, 1 2))</span></span><br /><br /> <span data-ttu-id="aa6a0-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span><span class="sxs-lookup"><span data-stu-id="aa6a0-148">POLYGON((-1 2, -3 4, -5 2, -1 2))</span></span>|<span data-ttu-id="aa6a0-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span><span class="sxs-lookup"><span data-stu-id="aa6a0-149">MULTIPOLYGON(((1 2, 5 2, 3 4, 1 2)), ((-5 2, -1 2, -3 4, -5 2)))</span></span>|  
  
```  
=Union(Fields!PointLocation.Value)  
=Union(Fields!PathDefinition.Value)  
=Union(Fields!PolygonDefinition.Value, "Group1")  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa6a0-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aa6a0-150">See Also</span></span>  
 <span data-ttu-id="aa6a0-151">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aa6a0-151">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aa6a0-152">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aa6a0-152">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aa6a0-153">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aa6a0-153">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="aa6a0-154">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="aa6a0-154">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
