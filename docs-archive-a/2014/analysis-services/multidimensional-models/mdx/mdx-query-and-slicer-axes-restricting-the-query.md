---
title: Restriction de la requête avec des axes de requête et de secteur (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Multidimensional Expressions [Analysis Services], axes
- queries [MDX], axes
- axes [MDX]
- MDX [Analysis Services], axes
ms.assetid: a64b8172-cd73-42f9-8847-52e967b9697a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ed4d50aa40d2915c60f887e64cdc3ef8a6d52c5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703319"
---
# <a name="restricting-the-query-with-query-and-slicer-axes-mdx"></a><span data-ttu-id="c75a5-102">Restriction de la requête avec des axes de requête et de secteur (MDX)</span><span class="sxs-lookup"><span data-stu-id="c75a5-102">Restricting the Query with Query and Slicer Axes (MDX)</span></span>
  <span data-ttu-id="c75a5-103">Lors de la formulation d'une instruction SELECT MDX (Multidimensional Expressions), une application examine généralement un cube et divise le jeu de hiérarchies en deux sous-ensembles :</span><span class="sxs-lookup"><span data-stu-id="c75a5-103">When formulating a Multidimensional Expressions (MDX) SELECT statement, an application typically examines a cube and divides the set of hierarchies into two subsets:</span></span>  
  
-   <span data-ttu-id="c75a5-104">**Axes de requête**: ensemble des hiérarchies à partir desquelles les données sont extraites pour plusieurs membres.</span><span class="sxs-lookup"><span data-stu-id="c75a5-104">**Query axes**-the set of hierarchies from which data is retrieved for multiple members.</span></span> <span data-ttu-id="c75a5-105">Pour plus d’informations sur les axes de requête, consultez [Spécification du contenu d’un axe de requête &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="c75a5-105">For more information about query axes, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
-   <span data-ttu-id="c75a5-106">**Axe de secteur**: ensemble des hiérarchies à partir desquelles les données sont récupérées pour un seul membre.</span><span class="sxs-lookup"><span data-stu-id="c75a5-106">**Slicer axis**-the set of hierarchies from which data is retrieved for a single member.</span></span> <span data-ttu-id="c75a5-107">Pour plus d’informations sur l’axe de secteur, consultez [Spécification du contenu d’un axe de secteur &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span><span class="sxs-lookup"><span data-stu-id="c75a5-107">For more information about the slicer axis, see [Specifying the Contents of a Slicer Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-slicer-axis.md).</span></span>  
  
 <span data-ttu-id="c75a5-108">Dans la mesure où les axes de requête et de secteur peuvent être construits à partir de plusieurs hiérarchies du cube à interroger, ces termes permettent de différencier les hiérarchies utilisées par le cube devant faire l'objet d'une interrogation par rapport aux hiérarchies créées dans le cube retourné par une requête MDX.</span><span class="sxs-lookup"><span data-stu-id="c75a5-108">Because query and slicer axes can be constructed from multiple hierarchies of the cube to be queried, these terms are used to differentiate the hierarchies used by the cube that is to be queried from the hierarchies created in the cube returned by an MDX query.</span></span>  
  
 <span data-ttu-id="c75a5-109">Pour obtenir un exemple d’utilisation des axes de requête et de secteur, consultez [Utilisation d’axes de requête et de secteur dans un exemple simple&#40;MDX&#41;](mdx-query-and-slicer-axes-using-axes-in-a-simple-example.md).</span><span class="sxs-lookup"><span data-stu-id="c75a5-109">To see a simple example using query and slicer axes, see [Using Query and Slicer Axes in a Simple Example &#40;MDX&#41;](mdx-query-and-slicer-axes-using-axes-in-a-simple-example.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75a5-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c75a5-110">See Also</span></span>  
 <span data-ttu-id="c75a5-111">[Utilisation de membres, de tuples et de jeux &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="c75a5-111">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 [<span data-ttu-id="c75a5-112">Principes de base des requêtes MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c75a5-112">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
