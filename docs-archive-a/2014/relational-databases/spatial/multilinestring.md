---
title: MultiLineString | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiLineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 95deeefe-d6c5-4a11-b347-379e4486e7b7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: fdd093d99d055df8e15fc22e3e570e6805e35d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613920"
---
# <a name="multilinestring"></a><span data-ttu-id="a8358-102">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="a8358-102">MultiLineString</span></span>
  <span data-ttu-id="a8358-103">Un `MultiLineString` est une collection de zéro ou plusieurs `geometry` instances ou **geographyLineString** .</span><span class="sxs-lookup"><span data-stu-id="a8358-103">A `MultiLineString` is a collection of zero or more `geometry` or **geographyLineString** instances.</span></span>  
  
## <a name="multilinestring-instances"></a><span data-ttu-id="a8358-104">Instances MultiLineString</span><span class="sxs-lookup"><span data-stu-id="a8358-104">MultiLineString instances</span></span>  
 <span data-ttu-id="a8358-105">L'illustration suivante montre des exemples d'instances `MultiLineString`.</span><span class="sxs-lookup"><span data-stu-id="a8358-105">The illustration below shows examples of `MultiLineString` instances.</span></span>  
  
 <span data-ttu-id="a8358-106">![Exemples d'instances MultiLineString géométriques](../../database-engine/media/multilinestring.gif "Exemples d'instances MultiLineString géométriques")</span><span class="sxs-lookup"><span data-stu-id="a8358-106">![Examples of geometry MultiLineString instances](../../database-engine/media/multilinestring.gif "Examples of geometry MultiLineString instances")</span></span>  
  
 <span data-ttu-id="a8358-107">Comme indiqué par l'illustration :</span><span class="sxs-lookup"><span data-stu-id="a8358-107">As shown in the illustration:</span></span>  
  
-   <span data-ttu-id="a8358-108">La figure 1 est une `MultiLineString` instance simple dont la limite est l’un des quatre points de terminaison de ses deux `LineString` éléments.</span><span class="sxs-lookup"><span data-stu-id="a8358-108">Figure 1 is a simple `MultiLineString` instance whose boundary is the four endpoints of its two `LineString` elements.</span></span>  
  
-   <span data-ttu-id="a8358-109">La Figure 2 est une instance `MultiLineString` simple car seuls les points de terminaison des éléments `LineString` se croisent.</span><span class="sxs-lookup"><span data-stu-id="a8358-109">Figure 2 is a simple `MultiLineString` instance because only the endpoints of the `LineString` elements intersect.</span></span> <span data-ttu-id="a8358-110">La limite est constituée des deux points de terminaison non chevauchants.</span><span class="sxs-lookup"><span data-stu-id="a8358-110">The boundary is the two non-overlapping endpoints.</span></span>  
  
-   <span data-ttu-id="a8358-111">La Figure 3 est une instance `MultiLineString` non simple car l'intérieur de l'un de ses éléments `LineString` est croisé.</span><span class="sxs-lookup"><span data-stu-id="a8358-111">Figure 3 is a nonsimple `MultiLineString` instance because the interior of one of its `LineString` elements is intersected.</span></span> <span data-ttu-id="a8358-112">La limite de cette instance `MultiLineString` est constituée des quatre points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="a8358-112">The boundary of this `MultiLineString` instance is the four endpoints.</span></span>  
  
-   <span data-ttu-id="a8358-113">La Figure 4 est une instance `MultiLineString` non simple et non close.</span><span class="sxs-lookup"><span data-stu-id="a8358-113">Figure 4 is a nonsimple, nonclosed `MultiLineString` instance.</span></span>  
  
-   <span data-ttu-id="a8358-114">La Figure 5 est une `MultiLineString` simple et non fermée.</span><span class="sxs-lookup"><span data-stu-id="a8358-114">Figure 5 is a simple, nonclosed `MultiLineString`.</span></span> <span data-ttu-id="a8358-115">Elle n’est pas fermée, car ses `LineStrings` éléments ne sont pas fermés.</span><span class="sxs-lookup"><span data-stu-id="a8358-115">It is not closed because its `LineStrings` elements are not closed.</span></span> <span data-ttu-id="a8358-116">Elle est simple car aucun des intérieurs des instances `LineStrings` ne se croise.</span><span class="sxs-lookup"><span data-stu-id="a8358-116">It is simple because none of the interiors of any of the `LineStrings` instances intersect.</span></span>  
  
-   <span data-ttu-id="a8358-117">La Figure 6 est une instance `MultiLineString` simple et fermée.</span><span class="sxs-lookup"><span data-stu-id="a8358-117">Figure 6 is a simple, closed `MultiLineString` instance.</span></span> <span data-ttu-id="a8358-118">Elle est fermée car tous ses éléments sont fermés.</span><span class="sxs-lookup"><span data-stu-id="a8358-118">It is closed because all its elements are closed.</span></span> <span data-ttu-id="a8358-119">Elle est simple car aucun de ses éléments ne se croise aux intérieurs.</span><span class="sxs-lookup"><span data-stu-id="a8358-119">It is simple because none of its elements intersect at the interiors.</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="a8358-120">Instances acceptées</span><span class="sxs-lookup"><span data-stu-id="a8358-120">Accepted instances</span></span>  
 <span data-ttu-id="a8358-121">Pour qu'une instance `MultiLineString` soit acceptée, elle doit être vide ou contenir uniquement les instances `LineString` acceptées.</span><span class="sxs-lookup"><span data-stu-id="a8358-121">For a `MultiLineString` instance to be accepted it must either be empty or comprised of only `LineString` intances that are accepted.</span></span> <span data-ttu-id="a8358-122">Pour plus d’informations sur les `LineString` instances acceptées, consultez [LineString](../spatial/linestring.md).</span><span class="sxs-lookup"><span data-stu-id="a8358-122">For more information on accepted `LineString` instances, see [LineString](../spatial/linestring.md).</span></span> <span data-ttu-id="a8358-123">Les exemples suivants illustrent des instances `MultiLineString` acceptées.</span><span class="sxs-lookup"><span data-stu-id="a8358-123">The following are examples of accepted `MultiLineString` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
```  
  
 <span data-ttu-id="a8358-124">L'exemple suivant lève une exception `System.FormatException` car la deuxième instance de `LineString` n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="a8358-124">The following example throws a `System.FormatException` because the second `LineString` instance is not valid.</span></span>  
  
```  
DECLARE @g geometry = 'MULTILINESTRING((1 1, 3 5),(-5 3))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="a8358-125">Instances valides</span><span class="sxs-lookup"><span data-stu-id="a8358-125">Valid instances</span></span>  
 <span data-ttu-id="a8358-126">Pour `MultiLineString` qu’une instance soit valide, elle doit répondre aux critères suivants :</span><span class="sxs-lookup"><span data-stu-id="a8358-126">For a `MultiLineString` instance to be valid it must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="a8358-127">Toutes les instances comprenant l'instance `MultiLineString` doivent être des instances `LineString` valides.</span><span class="sxs-lookup"><span data-stu-id="a8358-127">All instances comprising the `MultiLineString` instance must be valid `LineString` instances.</span></span>  
  
2.  <span data-ttu-id="a8358-128">Deux instances `LineString` comprenant l'instance `MultiLineString` peuvent se chevaucher sur un intervalle.</span><span class="sxs-lookup"><span data-stu-id="a8358-128">No two `LineString` instances comprising the `MultiLineString` instance may overlap over an interval.</span></span> <span data-ttu-id="a8358-129">Les instances `LineString` peuvent uniquement se croiser, se toucher ou toucher d'autres instances `LineString` à un nombre fini de points.</span><span class="sxs-lookup"><span data-stu-id="a8358-129">The `LineString` instances can only intersect or touch themselves or other `LineString` instances at a finite number of points.</span></span>  
  
 <span data-ttu-id="a8358-130">L'exemple suivant illustre trois instances `MultiLineString` valides et une instance `MultiLineString` non valide.</span><span class="sxs-lookup"><span data-stu-id="a8358-130">The following example shows three valid `MultiLineString` instances and one `MultiLineString` instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="a8358-131">`@g4` n'est pas valide car la deuxième instance `LineString` chevauche la première instance `LineString` à un intervalle.</span><span class="sxs-lookup"><span data-stu-id="a8358-131">`@g4` is not valid because the second `LineString` instance overlaps the first `LineString` instance at an interval.</span></span> <span data-ttu-id="a8358-132">Elles se touchent à un nombre infini de points.</span><span class="sxs-lookup"><span data-stu-id="a8358-132">They touch at an infinite number of points.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a8358-133">Exemples</span><span class="sxs-lookup"><span data-stu-id="a8358-133">Examples</span></span>  
 <span data-ttu-id="a8358-134">L’exemple suivant crée une instance `geometry``MultiLineString` simple qui contient deux éléments `LineString` avec le SRID 0.</span><span class="sxs-lookup"><span data-stu-id="a8358-134">The following example creates a simple `geometry``MultiLineString` instance containing two `LineString` elements with the SRID 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
```  
  
 <span data-ttu-id="a8358-135">Pour instancier cette instance avec un SRID différent, utilisez `STGeomFromText()` ou `STMLineStringFromText()`.</span><span class="sxs-lookup"><span data-stu-id="a8358-135">To instantiate this instance with a different SRID, use `STGeomFromText()` or `STMLineStringFromText()`.</span></span> <span data-ttu-id="a8358-136">Vous pouvez également utiliser `Parse()` puis modifier le SRID, comme indiqué dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="a8358-136">You can also use `Parse()` and then modify the SRID, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
SET @g.STSrid = 13;  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8358-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8358-137">See Also</span></span>  
 <span data-ttu-id="a8358-138">[STLength &#40;type de données geometry&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="a8358-138">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span></span>  
 <span data-ttu-id="a8358-139">[STIsClosed &#40;type de données geometry&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="a8358-139">[STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span></span>  
 <span data-ttu-id="a8358-140">[LineString](../spatial/linestring.md) </span><span class="sxs-lookup"><span data-stu-id="a8358-140">[LineString](../spatial/linestring.md) </span></span>  
 [<span data-ttu-id="a8358-141">Données spatiales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a8358-141">Spatial Data &#40;SQL Server&#41;</span></span>](../spatial/spatial-data-sql-server.md)  
  
  
