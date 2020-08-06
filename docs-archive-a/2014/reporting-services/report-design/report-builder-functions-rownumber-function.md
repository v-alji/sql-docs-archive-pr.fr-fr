---
title: Fonction RowNumber (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9d718ba8-d323-49fb-aac8-e7013a117b75
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f3d16188138c2f268305fddb092d56be870a3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605147"
---
# <a name="rownumber-function-report-builder-and-ssrs"></a><span data-ttu-id="401e4-102">Fonction RowNumber (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="401e4-102">RowNumber Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="401e4-103">Retourne un nombre évolutif du nombre de lignes pour l'étendue spécifiée.</span><span class="sxs-lookup"><span data-stu-id="401e4-103">Returns a running count of the number of rows for the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="401e4-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="401e4-104">Syntax</span></span>  
  
```  
  
RowNumber(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="401e4-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="401e4-105">Parameters</span></span>  
 <span data-ttu-id="401e4-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="401e4-106">*scope*</span></span>  
 <span data-ttu-id="401e4-107">(`String`) Nom d'un dataset, d'une région de données ou d'un groupe, ou valeur Null (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), qui spécifie le contexte dans lequel évaluer le nombre de lignes.</span><span class="sxs-lookup"><span data-stu-id="401e4-107">(`String`) The name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the number of rows.</span></span> <span data-ttu-id="401e4-108">`Nothing` spécifie le contexte le plus à l'extérieur, habituellement le dataset du rapport.</span><span class="sxs-lookup"><span data-stu-id="401e4-108">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="401e4-109">Notes</span><span class="sxs-lookup"><span data-stu-id="401e4-109">Remarks</span></span>  
 <span data-ttu-id="401e4-110">`RowNumber`retourne une valeur d’exécution du nombre de lignes dans l’étendue spécifiée, tout comme [RunningValue](report-builder-functions-runningvalue-function.md) retourne la valeur d’exécution d’une fonction d’agrégation.</span><span class="sxs-lookup"><span data-stu-id="401e4-110">`RowNumber` returns a running value of the count of rows within the specified scope, just as [RunningValue](report-builder-functions-runningvalue-function.md) returns the running value of an aggregate function.</span></span> <span data-ttu-id="401e4-111">Lorsque vous spécifiez une étendue, vous spécifiez quand réinitialiser le nombre de lignes à 1.</span><span class="sxs-lookup"><span data-stu-id="401e4-111">When you specify a scope, you specify when to reset the row count to 1.</span></span>  
  
 <span data-ttu-id="401e4-112">*scope* ne peut pas être une expression.</span><span class="sxs-lookup"><span data-stu-id="401e4-112">*scope* cannot be an expression.</span></span> <span data-ttu-id="401e4-113">*scope* doit être une étendue contenante.</span><span class="sxs-lookup"><span data-stu-id="401e4-113">*scope* must be a containing scope.</span></span> <span data-ttu-id="401e4-114">Les étendues classiques, de la relation contenant-contenu le plus à l'extérieur à celle située le plus à l'intérieur, sont un dataset de rapport, une région de données, des groupes de lignes ou des groupes de colonnes.</span><span class="sxs-lookup"><span data-stu-id="401e4-114">Typical scopes, from the outermost to the innermost containment, are report dataset, data region, row groups or column groups.</span></span>  
  
 <span data-ttu-id="401e4-115">Pour incrémenter des valeurs sur plusieurs colonnes, spécifiez comme étendue le nom d'un groupe de colonnes.</span><span class="sxs-lookup"><span data-stu-id="401e4-115">To increment values across columns, specify a scope that is the name of a column group.</span></span> <span data-ttu-id="401e4-116">Pour incrémenter des nombres en bas de lignes, spécifiez comme étendue le nom d'un groupe de lignes.</span><span class="sxs-lookup"><span data-stu-id="401e4-116">To increment numbers down rows, specify a scope that is the name of a row group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="401e4-117">L'inclusion d'agrégats qui spécifient un groupe de lignes et un groupe de colonnes dans une même expression n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="401e4-117">Including aggregates that specify both a row group and a column group in a single expression is not supported.</span></span>  
  
 <span data-ttu-id="401e4-118">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="401e4-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="401e4-119">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="401e4-119">Code Example</span></span>  
 <span data-ttu-id="401e4-120">L'exemple ci-dessous est une expression que vous pouvez utiliser pour la propriété `BackgroundColor` d'une ligne de détails de région de données de tableau matriciel pour faire alterner la couleur des lignes de détails de chaque groupe, en commençant toujours par le blanc.</span><span class="sxs-lookup"><span data-stu-id="401e4-120">The following is an expression that you can use for the `BackgroundColor` property of a Tablix data region detail row to alternate the color of detail rows for each group, always beginning with White.</span></span>  
  
```  
=IIF(RowNumber("GroupbyCategory") Mod 2, "White", "PaleGreen")  
```  
  
## <a name="see-also"></a><span data-ttu-id="401e4-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="401e4-121">See Also</span></span>  
 <span data-ttu-id="401e4-122">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="401e4-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="401e4-123">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="401e4-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="401e4-124">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="401e4-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="401e4-125">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="401e4-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
