---
title: Fonction RunningValue (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6bee2f15-0e69-49c8-9689-b04544063b1d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 168073a0409455041f4ebe3aa4c5dcfc8fa129a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605145"
---
# <a name="runningvalue-function-report-builder-and-ssrs"></a><span data-ttu-id="85616-102">Fonction RunningValue (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="85616-102">RunningValue Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="85616-103">Retourne un agrégat cumulé de toutes les valeurs numériques non Null spécifiées par l'expression, évaluée pour l'étendue donnée.</span><span class="sxs-lookup"><span data-stu-id="85616-103">Returns a running aggregate of all non-null numeric values specified by the expression, evaluated for the given scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="85616-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="85616-104">Syntax</span></span>  
  
```  
  
RunningValue(expression, function, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85616-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="85616-105">Parameters</span></span>  
 <span data-ttu-id="85616-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="85616-106">*expression*</span></span>  
 <span data-ttu-id="85616-107">Expression sur laquelle effectuer l’agrégation, par exemple `[Quantity]`.</span><span class="sxs-lookup"><span data-stu-id="85616-107">The expression on which to perform the aggregation, for example, `[Quantity]`.</span></span>  
  
 <span data-ttu-id="85616-108">*function*</span><span class="sxs-lookup"><span data-stu-id="85616-108">*function*</span></span>  
 <span data-ttu-id="85616-109">(`Enum`) Nom de la fonction d'agrégation à appliquer à l'expression, par exemple, `Sum`.</span><span class="sxs-lookup"><span data-stu-id="85616-109">(`Enum`) The name of the aggregate function to apply to the expression, for example, `Sum`.</span></span> <span data-ttu-id="85616-110">Cette fonction ne peut pas être de type `RunningValue`, `RowNumber` ou `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="85616-110">This function cannot be `RunningValue`, `RowNumber`, or `Aggregate`.</span></span>  
  
 <span data-ttu-id="85616-111">*scope*</span><span class="sxs-lookup"><span data-stu-id="85616-111">*scope*</span></span>  
 <span data-ttu-id="85616-112">(`String`) Constante de chaîne qui correspond au nom d'un dataset, d'une région de données ou d'un groupe, ou valeur Null (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), qui spécifie le contexte dans lequel évaluer l'agrégation.</span><span class="sxs-lookup"><span data-stu-id="85616-112">(`String`) A string constant that is the name of a dataset, data region, or group, or null (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]), that specifies the context in which to evaluate the aggregation.</span></span> <span data-ttu-id="85616-113">`Nothing` spécifie le contexte le plus à l'extérieur, habituellement le dataset du rapport.</span><span class="sxs-lookup"><span data-stu-id="85616-113">`Nothing` specifies the outermost context, usually the report dataset.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="85616-114">Type de retour</span><span class="sxs-lookup"><span data-stu-id="85616-114">Return Type</span></span>  
 <span data-ttu-id="85616-115">Déterminé par la fonction d'agrégation spécifiée dans le paramètre *function* .</span><span class="sxs-lookup"><span data-stu-id="85616-115">Determined by the aggregate function that is specified in the *function* parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85616-116">Notes</span><span class="sxs-lookup"><span data-stu-id="85616-116">Remarks</span></span>  
 <span data-ttu-id="85616-117">La valeur de `RunningValue` se réinitialise à 0 pour chaque nouvelle instance de l'étendue.</span><span class="sxs-lookup"><span data-stu-id="85616-117">The value for `RunningValue` resets to 0 for each new instance of the scope.</span></span> <span data-ttu-id="85616-118">Si vous spécifiez un groupe, la valeur d'exécution est réinitialisée lorsque l'expression de groupe change.</span><span class="sxs-lookup"><span data-stu-id="85616-118">If a group is specified, the running value is reset when the group expression changes.</span></span> <span data-ttu-id="85616-119">Si vous indiquez une région de données, le cumul est réinitialisé pour chaque nouvelle instance de la région de données.</span><span class="sxs-lookup"><span data-stu-id="85616-119">If a data region is specified, the running value is reset for each new instance of the data region.</span></span> <span data-ttu-id="85616-120">Si vous spécifiez un dataset, la valeur d'exécution n'est pas réinitialisée dans l'ensemble du dataset.</span><span class="sxs-lookup"><span data-stu-id="85616-120">If a dataset is specified, the running value is not reset throughout the entire dataset.</span></span>  
  
 <span data-ttu-id="85616-121">`RunningValue` ne peut pas être utilisé dans une expression de filtre ou de tri.</span><span class="sxs-lookup"><span data-stu-id="85616-121">`RunningValue` cannot be used in a filter or sort expression.</span></span>  
  
 <span data-ttu-id="85616-122">Le jeu des données pour lequel la valeur d'exécution est calculée doit avoir le même type de données.</span><span class="sxs-lookup"><span data-stu-id="85616-122">The set of data for which the running value is calculated must have the same data type.</span></span> <span data-ttu-id="85616-123">Pour convertir des données qui ont plusieurs types de données numériques en un même type de données, utilisez des fonctions de conversion telles que `CInt`, `CDbl` ou `CDec`.</span><span class="sxs-lookup"><span data-stu-id="85616-123">To convert data that has multiple numeric data types to the same data type, use conversion functions like `CInt`, `CDbl` or `CDec`.</span></span> <span data-ttu-id="85616-124">Pour plus d'informations, consultez [Fonctions de conversion de types de données](https://go.microsoft.com/fwlink/?LinkId=96142).</span><span class="sxs-lookup"><span data-stu-id="85616-124">For more information, see [Type Conversion Functions](https://go.microsoft.com/fwlink/?LinkId=96142).</span></span>  
  
 <span data-ttu-id="85616-125">*Scope* ne peut pas être une expression.</span><span class="sxs-lookup"><span data-stu-id="85616-125">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="85616-126">*Expression* peut contenir des appels aux fonctions d'agrégation imbriquées avec les exceptions et conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="85616-126">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="85616-127">Le paramètre Scope des agrégats imbriqués doit être identique à l'étendue de l'agrégat externe ou contenu par celle-ci.</span><span class="sxs-lookup"><span data-stu-id="85616-127">Scope for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="85616-128">Pour toutes les étendues distinctes de l'expression, une étendue doit figurer dans une relation enfant avec toutes les autres étendues.</span><span class="sxs-lookup"><span data-stu-id="85616-128">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="85616-129">Le paramètre Scope des agrégats imbriqués ne peut pas être le nom d'un dataset.</span><span class="sxs-lookup"><span data-stu-id="85616-129">Scope for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="85616-130">L' *expression* ne doit pas contenir `First` de fonctions, `Last` , `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="85616-130">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="85616-131">*Expression* ne doit pas contenir les agrégats imbriqués qui spécifient *recursive*.</span><span class="sxs-lookup"><span data-stu-id="85616-131">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="85616-132">Pour calculer la valeur d'exécution du nombre de lignes, utilisez `RowNumber`.</span><span class="sxs-lookup"><span data-stu-id="85616-132">To calculate the running value of the number of rows, use `RowNumber`.</span></span> <span data-ttu-id="85616-133">Pour plus d’informations, consultez [Fonction RowNumber &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-rownumber-function.md).</span><span class="sxs-lookup"><span data-stu-id="85616-133">For more information, see [RowNumber Function &#40;Report Builder and SSRS&#41;](report-builder-functions-rownumber-function.md).</span></span>  
  
 <span data-ttu-id="85616-134">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="85616-134">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="85616-135">Pour plus d’informations sur les agrégats récursifs, consultez [Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="85616-135">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="85616-136">Exemples</span><span class="sxs-lookup"><span data-stu-id="85616-136">Examples</span></span>  
 <span data-ttu-id="85616-137">L'exemple de code suivant fournit le cumul du champ nommé `Cost` de l'étendue la plus à l'extérieur, à savoir le dataset.</span><span class="sxs-lookup"><span data-stu-id="85616-137">The following code example provides a running sum of the field named `Cost` in the outermost scope, which is the dataset.</span></span>  
  
```  
=RunningValue(Fields!Cost.Value, Sum, Nothing)  
```  
  
 <span data-ttu-id="85616-138">L'exemple de code suivant fournit le cumul du champ nommé `Score` dans le dataset nommé `DataSet1`.</span><span class="sxs-lookup"><span data-stu-id="85616-138">The following code example provides a running sum of the field named `Score` in the dataset named `DataSet1`.</span></span>  
  
```  
=RunningValue(Fields!Score.Value,sum,"DataSet1")  
```  
  
 <span data-ttu-id="85616-139">L'exemple de code suivant fournit le cumul du champ nommé `Traffic Charges` dans l'étendue la plus à l'extérieure.</span><span class="sxs-lookup"><span data-stu-id="85616-139">The following code example provides a running sum of the field named `Traffic Charges` in the outermost scope.</span></span>  
  
```  
=RunningValue(Fields!Traffic Charges.Value, Sum, Nothing)  
```  
  
## <a name="see-also"></a><span data-ttu-id="85616-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85616-140">See Also</span></span>  
 <span data-ttu-id="85616-141">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85616-141">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="85616-142">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85616-142">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="85616-143">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85616-143">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="85616-144">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="85616-144">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
