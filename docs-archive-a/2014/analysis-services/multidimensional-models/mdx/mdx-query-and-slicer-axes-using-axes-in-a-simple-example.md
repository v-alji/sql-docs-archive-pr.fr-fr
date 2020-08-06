---
title: Utilisation des axes de requête et de découpage dans un exemple simple (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slicer axis
- query axis [MDX]
ms.assetid: 85bcb26f-5971-4153-b334-61f8d8b475b5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 324f082fd6659592e56af65680bd4aa623c625d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611982"
---
# <a name="using-query-and-slicer-axes-in-a-simple-example-mdx"></a><span data-ttu-id="61096-102">Utilisation d'axes de requête et de découpage dans un exemple simple (MDX)</span><span class="sxs-lookup"><span data-stu-id="61096-102">Using Query and Slicer Axes in a Simple Example (MDX)</span></span>
  <span data-ttu-id="61096-103">L'exemple simple fourni dans cette rubrique illustre les principes de base de la spécification et de l'utilisation d'axes de requête et de découpage.</span><span class="sxs-lookup"><span data-stu-id="61096-103">The simple example presented in this topic illustrates the basics of specifying and using query and slicer axes.</span></span>  
  
## <a name="the-cube"></a><span data-ttu-id="61096-104">Le cube</span><span class="sxs-lookup"><span data-stu-id="61096-104">The Cube</span></span>  
 <span data-ttu-id="61096-105">Un cube, appelé TestCube, possède deux dimensions simples appelées Route et Time.</span><span class="sxs-lookup"><span data-stu-id="61096-105">A cube, named TestCube, has two simple dimensions named Route and Time.</span></span> <span data-ttu-id="61096-106">Chaque dimension ne possède qu'une hiérarchie d'utilisateur, appelées respectivement Route et Time.</span><span class="sxs-lookup"><span data-stu-id="61096-106">Each dimension has only one user hierarchy, named Route and Time respectively.</span></span> <span data-ttu-id="61096-107">Puisque les mesures de ce cube font partie de la dimension Measures, ce cube possède trois dimensions.</span><span class="sxs-lookup"><span data-stu-id="61096-107">Because the measures of the cube are part of the Measures dimension, this cube has three dimensions in all.</span></span>  
  
## <a name="the-query"></a><span data-ttu-id="61096-108">La requête</span><span class="sxs-lookup"><span data-stu-id="61096-108">The Query</span></span>  
 <span data-ttu-id="61096-109">La requête consiste à fournir une matrice dans laquelle la mesure Packages peut être comparée d'après des routes et des heures (Time).</span><span class="sxs-lookup"><span data-stu-id="61096-109">The query is to provide a matrix in which the Packages measure can be compared across routes and times.</span></span>  
  
 <span data-ttu-id="61096-110">Dans l'exemple de requête MDX suivant, les hiérarchies Route et Time sont les axes de requête et la dimension Measures est l'axe de découpage.</span><span class="sxs-lookup"><span data-stu-id="61096-110">In the following MDX query example, the Route and Time hierarchies are the query axes, and the Measures dimension is the slicer axis.</span></span> <span data-ttu-id="61096-111">La fonction [Members](/sql/mdx/members-set-mdx) indique que la syntaxe MDX doit utiliser les membres de la hiérarchie ou du niveau pour construire un jeu.</span><span class="sxs-lookup"><span data-stu-id="61096-111">The [Members](/sql/mdx/members-set-mdx) function indicates that MDX will use the members of the hierarchy or level to construct a set.</span></span> <span data-ttu-id="61096-112">Grâce à l'utilisation de la fonction `Members`, vous ne devez pas déclarer explicitement chaque membre d'une hiérarchie ou d'un niveau spécifiques dans une requête MDX.</span><span class="sxs-lookup"><span data-stu-id="61096-112">The use of the `Members` function means that you do not have to explicitly state each member of a specific hierarchy or level in an MDX query.</span></span>  
  
```  
SELECT  
   { Route.nonground.Members } ON COLUMNS,  
   { Time.[1st half].Members } ON ROWS  
FROM TestCube  
WHERE ( [Measures].[Packages] )  
```  
  
## <a name="the-results"></a><span data-ttu-id="61096-113">Les résultats</span><span class="sxs-lookup"><span data-stu-id="61096-113">The Results</span></span>  
 <span data-ttu-id="61096-114">Le résultat est une grille identifiant la valeur de la mesure Packages à chaque intersection des dimensions d'axe COLUMNS et ROWS.</span><span class="sxs-lookup"><span data-stu-id="61096-114">The result is a grid that identifies the value of the Packages measure at each intersection of the COLUMNS and ROWS axis dimensions.</span></span> <span data-ttu-id="61096-115">Le tableau suivant représente l'aspect de cette grille.</span><span class="sxs-lookup"><span data-stu-id="61096-115">The following table shows how this grid would look.</span></span>  
  
||<span data-ttu-id="61096-116">air</span><span class="sxs-lookup"><span data-stu-id="61096-116">air</span></span>|<span data-ttu-id="61096-117">sea</span><span class="sxs-lookup"><span data-stu-id="61096-117">sea</span></span>|  
|-|---------|---------|  
|<span data-ttu-id="61096-118">1st quarter</span><span class="sxs-lookup"><span data-stu-id="61096-118">1st quarter</span></span>|<span data-ttu-id="61096-119">60</span><span class="sxs-lookup"><span data-stu-id="61096-119">60</span></span>|<span data-ttu-id="61096-120">50</span><span class="sxs-lookup"><span data-stu-id="61096-120">50</span></span>|  
|<span data-ttu-id="61096-121">2nd quarter</span><span class="sxs-lookup"><span data-stu-id="61096-121">2nd quarter</span></span>|<span data-ttu-id="61096-122">45</span><span class="sxs-lookup"><span data-stu-id="61096-122">45</span></span>|<span data-ttu-id="61096-123">45</span><span class="sxs-lookup"><span data-stu-id="61096-123">45</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61096-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61096-124">See Also</span></span>  
 <span data-ttu-id="61096-125">[Spécification du contenu d’un axe de requête &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span><span class="sxs-lookup"><span data-stu-id="61096-125">[Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md) </span></span>  
 [<span data-ttu-id="61096-126">Spécification du contenu d’un axe de secteur &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="61096-126">Specifying the Contents of a Slicer Axis &#40;MDX&#41;</span></span>](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md)  
  
  
