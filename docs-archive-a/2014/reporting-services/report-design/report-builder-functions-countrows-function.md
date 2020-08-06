---
title: Fonction CountRows (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5b1c403d-6afd-44c8-b5f6-5ecff2a29a45
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d5311dfc5dfcb89449a4039fdac4100fc5a3b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605172"
---
# <a name="countrows-function-report-builder-and-ssrs"></a><span data-ttu-id="04466-102">Fonction CountRows (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="04466-102">CountRows Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="04466-103">Retourne le nombre de lignes dans l'étendue spécifiée, y compris celles contenant des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="04466-103">Returns the number of rows in the specified scope, including rows with null values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="04466-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="04466-104">Syntax</span></span>  
  
```  
  
CountRows(scope, recursive)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04466-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="04466-105">Parameters</span></span>  
 <span data-ttu-id="04466-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="04466-106">*scope*</span></span>  
 <span data-ttu-id="04466-107">(`String`) Nom d'un dataset, d'un groupe ou d'une région de données qui contient les éléments de rapport à compter.</span><span class="sxs-lookup"><span data-stu-id="04466-107">(`String`) The name of a dataset, data region, or group that contains the report items to count.</span></span>  
  
 <span data-ttu-id="04466-108">*recursive*</span><span class="sxs-lookup"><span data-stu-id="04466-108">*recursive*</span></span>  
 <span data-ttu-id="04466-109">(**Type énuméré**) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="04466-109">(**Enumerated Type**) Optional.</span></span> <span data-ttu-id="04466-110">`Simple` (par défaut) ou `RdlRecursive`.</span><span class="sxs-lookup"><span data-stu-id="04466-110">`Simple` (default) or `RdlRecursive`.</span></span> <span data-ttu-id="04466-111">Indique s'il faut effectuer l'agrégation de manière récursive.</span><span class="sxs-lookup"><span data-stu-id="04466-111">Specifies whether to perform the aggregation recursively.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="04466-112">Type de retour</span><span class="sxs-lookup"><span data-stu-id="04466-112">Return Type</span></span>  
 <span data-ttu-id="04466-113">Retourne un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="04466-113">Returns an `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04466-114">Notes</span><span class="sxs-lookup"><span data-stu-id="04466-114">Remarks</span></span>  
 <span data-ttu-id="04466-115">`CountRows` compte toutes les lignes dans l'étendue spécifiée, y compris celles contenant des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="04466-115">`CountRows` counts all rows in the specified scope, including rows that have null values.</span></span>  
  
 <span data-ttu-id="04466-116">La valeur du paramètre *scope* ne peut pas être une expression et doit faire référence à l'étendue actuelle ou à une étendue contenante.</span><span class="sxs-lookup"><span data-stu-id="04466-116">The value of *scope* cannot be an expression and must refer to the current scope or a containing scope.</span></span>  
  
 <span data-ttu-id="04466-117">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="04466-117">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="04466-118">Pour plus d’informations sur les agrégats récursifs, consultez [Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="04466-118">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04466-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="04466-119">Example</span></span>  
 <span data-ttu-id="04466-120">L'exemple de code suivant affiche une expression qui calcule le nombre de lignes dans un groupe de lignes nommé `GroupbyCategory` (basé sur l'expression `[Category]`).</span><span class="sxs-lookup"><span data-stu-id="04466-120">The following code example shows an expression that calculates the number of rows in a row group named `GroupbyCategory` (based on the expression `[Category]`).</span></span>  
  
```  
="Number of rows: " & CountRows("GroupbyCategory")  
```  
  
## <a name="see-also"></a><span data-ttu-id="04466-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="04466-121">See Also</span></span>  
 <span data-ttu-id="04466-122">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="04466-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="04466-123">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="04466-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="04466-124">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="04466-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="04466-125">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="04466-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
