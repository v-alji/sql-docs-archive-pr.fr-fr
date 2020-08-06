---
title: Fonction InScope (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8cd209a-e5d3-4dce-ab2d-f271f6c54955
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62c4ad5de7af1ac0762df29deaa17953a8a378db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605165"
---
# <a name="inscope-function-report-builder-and-ssrs"></a><span data-ttu-id="29282-102">Fonction InScope (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="29282-102">InScope Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="29282-103">Indique si l'instance actuelle d'un élément se trouve dans l'étendue spécifiée.</span><span class="sxs-lookup"><span data-stu-id="29282-103">Indicates whether the current instance of an item is in the specified scope.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="29282-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="29282-104">Syntax</span></span>  
  
```  
InScope(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29282-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="29282-105">Parameters</span></span>  
 <span data-ttu-id="29282-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="29282-106">*scope*</span></span>  
 <span data-ttu-id="29282-107">(`String`) Nom d'un dataset, d'une région de données ou d'un groupe qui spécifie une étendue.</span><span class="sxs-lookup"><span data-stu-id="29282-107">(`String`) The name of a dataset, data region, or group that specifies a scope.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="29282-108">Type de retour</span><span class="sxs-lookup"><span data-stu-id="29282-108">Return Type</span></span>  
 <span data-ttu-id="29282-109">Retourne `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="29282-109">Returns a `Boolean`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29282-110">Notes</span><span class="sxs-lookup"><span data-stu-id="29282-110">Remarks</span></span>  
 <span data-ttu-id="29282-111">La `InScope` fonction teste l’étendue de l’instance actuelle d’un élément de rapport pour l’appartenance à l’étendue spécifiée par le paramètre *scope*.</span><span class="sxs-lookup"><span data-stu-id="29282-111">The `InScope` function tests the scope of the current instance of a report item for membership in the scope specified by the *scope*parameter.</span></span>  
  
 <span data-ttu-id="29282-112">*Scope* ne peut pas être une expression.</span><span class="sxs-lookup"><span data-stu-id="29282-112">*Scope* cannot be an expression.</span></span>  
  
 <span data-ttu-id="29282-113">En règle générale, la fonction `InScope` est utilisée dans les régions de données avec définition d'étendue dynamique.</span><span class="sxs-lookup"><span data-stu-id="29282-113">A typical use for the `InScope` function is in data regions that have dynamic scoping.</span></span> <span data-ttu-id="29282-114">Ainsi, la fonction `InScope` peut être utilisée dans un lien d'extraction situé dans les cellules d'une région de données pour fournir un autre nom de rapport et des jeux de paramètres différents en fonction de la cellule sur laquelle l'utilisateur clique.</span><span class="sxs-lookup"><span data-stu-id="29282-114">For example, `InScope` can be used in a drillthrough link in a data region cells to provide a different report name and different sets of parameters depending on which cell is clicked.</span></span> <span data-ttu-id="29282-115">En voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="29282-115">An example of this is as follows:</span></span>  
  
-   <span data-ttu-id="29282-116">L’expression suivante, utilisée comme nom de rapport dans un lien d’extraction, ouvre le rapport `ProductDetail` si l’utilisateur clique sur une cellule située dans le groupe `Month` et le rapport `ProductSummary` s’il clique sur une autre cellule.</span><span class="sxs-lookup"><span data-stu-id="29282-116">The following expression, used as the report name in a drillthrough link, opens the `ProductDetail` report if the clicked cell is in the `Month` group, and the `ProductSummary` report if it is not.</span></span>  
  
    ```  
    =Iif(InScope("Month"), "ProductDetail", "ProductSummary")  
    ```  
  
-   <span data-ttu-id="29282-117">L'expression suivante, utilisée dans la propriété `Omit` d'un paramètre de rapport d'extraction, passe le paramètre au rapport cible uniquement si la cellule sur laquelle l'utilisateur clique se trouve dans le groupe `Product`.</span><span class="sxs-lookup"><span data-stu-id="29282-117">The following expression, used in the `Omit` property of a drillthrough report parameter, will pass the parameter to the target report only if the clicked cell is in the `Product` group.</span></span>  
  
    ```  
    =Not(InScope("Product"))  
    ```  
  
 <span data-ttu-id="29282-118">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="29282-118">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29282-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="29282-119">Example</span></span>  
 <span data-ttu-id="29282-120">L'exemple de code ci-dessous indique si l'instance actuelle de l'élément se trouve dans l'étendue du groupe, de la région de données ou du dataset `Product` .</span><span class="sxs-lookup"><span data-stu-id="29282-120">The following code example indicates whether the current instance of the item is in the `Product` dataset, data region, or group scope.</span></span>  
  
```  
=InScope("Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="29282-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29282-121">See Also</span></span>  
 <span data-ttu-id="29282-122">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="29282-122">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="29282-123">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="29282-123">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="29282-124">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="29282-124">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="29282-125">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="29282-125">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
