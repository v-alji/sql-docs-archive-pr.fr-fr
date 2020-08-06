---
title: Fonction Level (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 41235402-bb9e-4cb7-b91e-431e77db19cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dedbf00ce8330242c95e9592f649d95171f0987a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605163"
---
# <a name="level-function-report-builder-and-ssrs"></a><span data-ttu-id="5e13b-102">Fonction Level (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="5e13b-102">Level Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5e13b-103">Retourne le niveau de profondeur actuel d'une hiérarchie récursive.</span><span class="sxs-lookup"><span data-stu-id="5e13b-103">Returns the current level of depth in a recursive hierarchy.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="5e13b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5e13b-104">Syntax</span></span>  
  
```  
  
Level(scope)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e13b-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5e13b-105">Parameters</span></span>  
 <span data-ttu-id="5e13b-106">*scope*</span><span class="sxs-lookup"><span data-stu-id="5e13b-106">*scope*</span></span>  
 <span data-ttu-id="5e13b-107">(`String`) (Facultatif).</span><span class="sxs-lookup"><span data-stu-id="5e13b-107">(`String`) (Optional).</span></span> <span data-ttu-id="5e13b-108">Nom d'un dataset, d'un groupe ou d'une région de données qui contient les éléments de rapport auxquels appliquer la fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="5e13b-108">The name of a dataset, group, or data region that contains the report items to which to apply the aggregate function.</span></span> <span data-ttu-id="5e13b-109">Si le paramètre *scope* n'est pas spécifié, l'étendue actuelle est utilisée.</span><span class="sxs-lookup"><span data-stu-id="5e13b-109">If *scope* is not specified, the current scope is used.</span></span>  
  
## <a name="return-type"></a><span data-ttu-id="5e13b-110">Type de retour</span><span class="sxs-lookup"><span data-stu-id="5e13b-110">Return Type</span></span>  
 <span data-ttu-id="5e13b-111">Retourne un `Integer`.</span><span class="sxs-lookup"><span data-stu-id="5e13b-111">Returns an `Integer`.</span></span> <span data-ttu-id="5e13b-112">Si *scope* spécifie un DataSet ou une région de données, ou spécifie un regroupement non récursif (c’est-à-dire un regroupement sans `Parent` élément), `Level` retourne 0.</span><span class="sxs-lookup"><span data-stu-id="5e13b-112">If *scope* specifies a dataset or data region, or specifies a nonrecursive grouping (that is, a grouping with no `Parent` element), `Level` returns 0.</span></span> <span data-ttu-id="5e13b-113">Si vous omettez le paramètre *scope* , elle retourne le niveau de l'étendue actuelle.</span><span class="sxs-lookup"><span data-stu-id="5e13b-113">If *scope* is omitted, it returns the level of the current scope.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e13b-114">Notes</span><span class="sxs-lookup"><span data-stu-id="5e13b-114">Remarks</span></span>  
 <span data-ttu-id="5e13b-115">La valeur retournée par la fonction `Level` est une valeur de base zéro, c'est-à-dire que le premier niveau d'une hiérarchie est 0.</span><span class="sxs-lookup"><span data-stu-id="5e13b-115">The value returned by the `Level` function is zero based; that is, the first level in a hierarchy is 0.</span></span>  
  
 <span data-ttu-id="5e13b-116">La fonction `Level` peut être utilisée pour appliquer un retrait dans une hiérarchie récursive, comme une liste d'employés.</span><span class="sxs-lookup"><span data-stu-id="5e13b-116">The `Level` function can be used to provide indentation in a recursive hierarchy, such as an employee list.</span></span>  
  
 <span data-ttu-id="5e13b-117">Pour plus d’informations sur les hiérarchies récursives, consultez [Création de groupes de hiérarchies récursives &#40;Générateur de rapports et SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5e13b-117">For more information about recursive hierarchies, see [Creating Recursive Hierarchy Groups &#40;Report Builder and SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e13b-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="5e13b-118">Example</span></span>  
 <span data-ttu-id="5e13b-119">L'exemple de code ci-dessous indique le niveau de ligne dans le groupe Employees :</span><span class="sxs-lookup"><span data-stu-id="5e13b-119">The following code example provides the level of row in the Employees group:</span></span>  
  
```  
=Level("Employees")  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e13b-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e13b-120">See Also</span></span>  
 <span data-ttu-id="5e13b-121">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5e13b-121">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5e13b-122">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5e13b-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5e13b-123">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5e13b-123">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5e13b-124">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5e13b-124">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
