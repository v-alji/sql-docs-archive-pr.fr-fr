---
title: Génération de mesures dans MDX | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0347835-4983-4d26-acbb-6c8fae7992bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac49d37f11584bfbc5d372241056da39e7dd8c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604190"
---
# <a name="building-measures-in-mdx"></a><span data-ttu-id="df7d4-102">Génération de mesures dans une expression MDX</span><span class="sxs-lookup"><span data-stu-id="df7d4-102">Building Measures in MDX</span></span>
  <span data-ttu-id="df7d4-103">Dans les expressions multidimensionnelles (MDX, Multidimensional Expressions), une mesure est une expression DAX nommée qui est résolue en calculant l'expression permettant de retourner une valeur dans un modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="df7d4-103">In Multidimensional Expressions (MDX), a measure is a named DAX expression that is resolved by calculating the expression to return a value in a Tabular Model.</span></span> <span data-ttu-id="df7d4-104">Cette définition anodine couvre un vaste champ d'action.</span><span class="sxs-lookup"><span data-stu-id="df7d4-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="df7d4-105">La possibilité de bâtir et d'utiliser des mesures dans une requête MDX est un élément fondamental de la manipulation des données tabulaires.</span><span class="sxs-lookup"><span data-stu-id="df7d4-105">The ability to construct and use measures in an MDX query provides a great deal of manipulation capability for tabular data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="df7d4-106">Les mesures peuvent uniquement être définies dans les modèles tabulaires ; si votre base de données est définie en mode MDX, la création d'une mesure génère une erreur</span><span class="sxs-lookup"><span data-stu-id="df7d4-106">Measures can only be defined in tabular models; if your database is set in multidimensional mode, creating a measure will generate an error</span></span>  
  
 <span data-ttu-id="df7d4-107">Pour créer une mesure définie en tant que partie d'une requête MDX, et dont l'étendue est donc limitée à la requête, utilisez le mot clé WITH.</span><span class="sxs-lookup"><span data-stu-id="df7d4-107">To create a measure that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="df7d4-108">Vous pouvez ensuite utiliser la mesure au sein d'une instruction MDX SELECT.</span><span class="sxs-lookup"><span data-stu-id="df7d4-108">You can then use the measure within an MDX SELECT statement.</span></span> <span data-ttu-id="df7d4-109">Ainsi, vous pouvez modifier le membre calculé créé à l'aide du mot clé WITH sans porter atteinte à l'instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="df7d4-109">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span> <span data-ttu-id="df7d4-110">Toutefois, dans une expression MDX, vous référencez la mesure d'une manière différente de celle utilisée dans les expressions DAX ; pour référencer la mesure, vous la nommez en tant que membre de la dimension [Measures]. Consultez l'exemple d'expression MDX suivant :</span><span class="sxs-lookup"><span data-stu-id="df7d4-110">However, in MDX you reference the measure in a different way than when in DAX expressions; to reference the measure you name it as a member of the [Measures] dimension, see the following MDX example:</span></span>  
  
```  
with measure  'Sales Territory'[Total Sales Amount] = SUM('Internet Sales'[Sales Amount]) + SUM('Reseller Sales'[Sales Amount])  
select measures.[Total Sales Amount] on columns  
     ,NON EMPTY [Date].[Calendar Year].children on rows  
from [Model]  
  
```  
  
 <span data-ttu-id="df7d4-111">Retourne les données suivantes lorsqu'elle est exécutée :</span><span class="sxs-lookup"><span data-stu-id="df7d4-111">It will return the following data when executed:</span></span>  
  
||<span data-ttu-id="df7d4-112">Total Sales Amount</span><span class="sxs-lookup"><span data-stu-id="df7d4-112">Total Sales Amount</span></span>||  
|-|------------------------|-|  
|<span data-ttu-id="df7d4-113">2001</span><span class="sxs-lookup"><span data-stu-id="df7d4-113">2001</span></span>|<span data-ttu-id="df7d4-114">11331808.96</span><span class="sxs-lookup"><span data-stu-id="df7d4-114">11331808.96</span></span>||  
|<span data-ttu-id="df7d4-115">2002</span><span class="sxs-lookup"><span data-stu-id="df7d4-115">2002</span></span>|<span data-ttu-id="df7d4-116">30674773.18</span><span class="sxs-lookup"><span data-stu-id="df7d4-116">30674773.18</span></span>||  
|<span data-ttu-id="df7d4-117">2003</span><span class="sxs-lookup"><span data-stu-id="df7d4-117">2003</span></span>|<span data-ttu-id="df7d4-118">41993729.72</span><span class="sxs-lookup"><span data-stu-id="df7d4-118">41993729.72</span></span>||  
|<span data-ttu-id="df7d4-119">2004</span><span class="sxs-lookup"><span data-stu-id="df7d4-119">2004</span></span>|<span data-ttu-id="df7d4-120">25808962.34</span><span class="sxs-lookup"><span data-stu-id="df7d4-120">25808962.34</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="df7d4-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df7d4-121">See Also</span></span>  
 <span data-ttu-id="df7d4-122">[Instruction CREATe MEMBER &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="df7d4-122">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="df7d4-123">[Référence des fonctions MDX &#40;&#41;MDX](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="df7d4-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="df7d4-124">Instruction SELECT &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="df7d4-124">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
