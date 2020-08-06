---
title: Fonction First (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d0914520-30c5-4d63-9b59-8d9342ed63b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cd8578a1d9a17030d603457d4eaadf107316bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605167"
---
# <a name="first-function-report-builder-and-ssrs"></a><span data-ttu-id="7ec0f-102">Fonction First (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="7ec0f-102">First Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7ec0f-103">Retourne la première valeur dans l'étendue donnée de l'expression spécifiée.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-103">Returns the first value in the given scope of the specified expression.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="7ec0f-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7ec0f-104">Syntax</span></span>  
  
```  
  
First(expression, scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ec0f-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="7ec0f-105">Parameters</span></span>  
 <span data-ttu-id="7ec0f-106">*expression*</span><span class="sxs-lookup"><span data-stu-id="7ec0f-106">*expression*</span></span>  
 <span data-ttu-id="7ec0f-107">(`Variant` ou `Binary`) Expression sur laquelle effectuer l'agrégation ; par exemple, `=Fields!FieldName.Value`.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-107">(`Variant` or `Binary`) The expression on which to perform the aggregation, for example, `=Fields!FieldName.Value`.</span></span>  
  
 <span data-ttu-id="7ec0f-108">*scope*</span><span class="sxs-lookup"><span data-stu-id="7ec0f-108">*scope*</span></span>  
 <span data-ttu-id="7ec0f-109">(`String`) Facultatif.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-109">(`String`) Optional.</span></span> <span data-ttu-id="7ec0f-110">Nom d'un dataset, d'un groupe ou d'une région de données qui contient les éléments de rapport auxquels appliquer la fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-110">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="7ec0f-111">Si le paramètre *scope* n'est pas spécifié, l'étendue actuelle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-111">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="7ec0f-112">Type de retour</span><span class="sxs-lookup"><span data-stu-id="7ec0f-112">Return Type</span></span>  
 <span data-ttu-id="7ec0f-113">Déterminé par le type d'expression.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-113">Determined by the type of expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ec0f-114">Notes</span><span class="sxs-lookup"><span data-stu-id="7ec0f-114">Remarks</span></span>  
 <span data-ttu-id="7ec0f-115">La fonction `First` retourne la première valeur d'un jeu de données après que l'étendue spécifiée a été correctement triée et filtrée.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-115">The `First` function returns the first value in a set of data after all sorting and filtering have been applied at the specified scope.</span></span>  
  
 <span data-ttu-id="7ec0f-116">La fonction `First` ne peut être utilisée dans les expressions de filtre de groupe qu'avec l'étendue actuelle (par défaut).</span><span class="sxs-lookup"><span data-stu-id="7ec0f-116">The `First` function cannot be used in group filter expressions with anything except the current (default) scope.</span></span>  
  
 <span data-ttu-id="7ec0f-117">Vous pouvez également utiliser `First` dans un en-tête de page pour retourner la première valeur de la collection `ReportItems` pour une page afin de produire des en-têtes de type dictionnaire qui affichent la première et la dernière entrées d'une page.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-117">You can also use `First` in a page header to return the first value from the `ReportItems` collection for a page in order to produce dictionary-style headings that display the first and last entries on a page.</span></span>  
  
 <span data-ttu-id="7ec0f-118">La valeur du paramètre *scope* doit être une constante de chaîne et ne peut pas être une expression.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-118">The value of *scope* must be a string constant andcannot be an expression.</span></span> <span data-ttu-id="7ec0f-119">Pour les agrégats externes ou les agrégats qui ne spécifient pas d'autres agrégats, le paramètre *scope* doit faire référence à l'étendue actuelle ou à une étendue contenante.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-119">For outer aggregates or aggregates that do not specify other aggregates, *scope* must refer to the current scope or a containing scope.</span></span> <span data-ttu-id="7ec0f-120">Pour les agrégats d'agrégats, les agrégats imbriqués peuvent spécifier une étendue enfant.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-120">For aggregates of aggregates, nested aggregates can specify a child scope.</span></span>  
  
 <span data-ttu-id="7ec0f-121">*Expression* peut contenir des appels aux fonctions d'agrégation imbriquées avec les exceptions et conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="7ec0f-121">*Expression* can contain calls to nested aggregate functions with the following exceptions and conditions:</span></span>  
  
-   <span data-ttu-id="7ec0f-122">Le paramètre*Scope* des agrégats imbriqués doit être identique à l'étendue de l'agrégat externe ou contenu par celle-ci.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-122">*Scope* for nested aggregates must be the same as, or contained by, the scope of the outer aggregate.</span></span> <span data-ttu-id="7ec0f-123">Pour toutes les étendues distinctes de l'expression, une étendue doit figurer dans une relation enfant avec toutes les autres étendues.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-123">For all distinct scopes in the expression, one scope must be in a child relationship to all other scopes.</span></span>  
  
-   <span data-ttu-id="7ec0f-124">Le paramètre*Scope* des agrégats imbriqués ne peut pas être le nom d'un dataset.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-124">*Scope* for nested aggregates cannot be the name of a dataset.</span></span>  
  
-   <span data-ttu-id="7ec0f-125">L' *expression* ne doit pas contenir `First` de fonctions, `Last` , `Previous` ou `RunningValue` .</span><span class="sxs-lookup"><span data-stu-id="7ec0f-125">*Expression* must not contain `First`, `Last`, `Previous`, or `RunningValue` functions.</span></span>  
  
-   <span data-ttu-id="7ec0f-126">*Expression* ne doit pas contenir les agrégats imbriqués qui spécifient *recursive*.</span><span class="sxs-lookup"><span data-stu-id="7ec0f-126">*Expression* must not contain nested aggregates that specify *recursive*.</span></span>  
  
 <span data-ttu-id="7ec0f-127">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="7ec0f-127">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
 <span data-ttu-id="7ec0f-128">Pour plus d’informations sur les agrégats récursifs, consultez [Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7ec0f-128">For more information about recursive aggregates, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ec0f-129">Exemple</span><span class="sxs-lookup"><span data-stu-id="7ec0f-129">Example</span></span>  
 <span data-ttu-id="7ec0f-130">L'exemple de code ci-dessous retourne le premier numéro de produit du groupe `Category` d'une région de données :</span><span class="sxs-lookup"><span data-stu-id="7ec0f-130">The following code example returns the first product number in the `Category` group of a data region:</span></span>  
  
```  
=First(Fields!ProductNumber.Value, "Category")  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ec0f-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7ec0f-131">See Also</span></span>  
 <span data-ttu-id="7ec0f-132">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7ec0f-132">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7ec0f-133">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7ec0f-133">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7ec0f-134">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7ec0f-134">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7ec0f-135">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7ec0f-135">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
