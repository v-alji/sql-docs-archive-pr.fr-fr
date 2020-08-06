---
title: MultiPolygon | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPolygon geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 2c5db358-2a16-49d9-aac5-a74e86813932
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: f18fd2485c9b2e62586d9f3e81f76f6cf680dbfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613916"
---
# <a name="multipolygon"></a><span data-ttu-id="79e9e-102">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="79e9e-102">MultiPolygon</span></span>
  <span data-ttu-id="79e9e-103">Une instance `MultiPolygon` est une collection de zéro ou plusieurs instances `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="79e9e-103">A `MultiPolygon` instance is a collection of zero or more `Polygon` instances.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="79e9e-104">Instances Polygon</span><span class="sxs-lookup"><span data-stu-id="79e9e-104">Polygon Instances</span></span>
 <span data-ttu-id="79e9e-105">L'illustration suivante montre des exemples d'instances `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="79e9e-105">The illustration below shows examples of `MultiPolygon` instances.</span></span>

 <span data-ttu-id="79e9e-106">![Exemples d'instances MultiPolygon géométriques](../../database-engine/media/multipolygon.gif "Exemples d'instances MultiPolygon géométriques")</span><span class="sxs-lookup"><span data-stu-id="79e9e-106">![Examples of geometry MultiPolygon instances](../../database-engine/media/multipolygon.gif "Examples of geometry MultiPolygon instances")</span></span>

 <span data-ttu-id="79e9e-107">Comme indiqué par l'illustration :</span><span class="sxs-lookup"><span data-stu-id="79e9e-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="79e9e-108">La Figure 1 est une instance `MultiPolygon` avec deux éléments `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="79e9e-108">Figure 1 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="79e9e-109">La limite est définie par les deux anneaux extérieurs et les trois anneaux intérieurs.</span><span class="sxs-lookup"><span data-stu-id="79e9e-109">The boundary is defined by the two exterior rings and the three interior rings.</span></span>

-   <span data-ttu-id="79e9e-110">La Figure 2 est une instance `MultiPolygon` avec deux éléments `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="79e9e-110">Figure 2 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="79e9e-111">La limite est définie par les deux anneaux extérieurs et les trois anneaux intérieurs.</span><span class="sxs-lookup"><span data-stu-id="79e9e-111">The boundary is defined by the two exterior rings and the three interior rings.</span></span> <span data-ttu-id="79e9e-112">Les deux éléments `Polygon` se croisent à un point tangent.</span><span class="sxs-lookup"><span data-stu-id="79e9e-112">The two `Polygon` elements intersect at a tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="79e9e-113">Instances acceptées</span><span class="sxs-lookup"><span data-stu-id="79e9e-113">Accepted Instances</span></span>
 <span data-ttu-id="79e9e-114">Les instances `MultiPolygon` sont acceptées si l'une des conditions suivantes est remplie.</span><span class="sxs-lookup"><span data-stu-id="79e9e-114">A `MultiPolygon` instance is accepted one of the following conditions is met.</span></span>

-   <span data-ttu-id="79e9e-115">Il s'agit d'une instance `MultiPolygon` vide.</span><span class="sxs-lookup"><span data-stu-id="79e9e-115">It is an empty `MultiPolygon` instance.</span></span>

-   <span data-ttu-id="79e9e-116">Toutes les instances comprenant l'instance `MultiPolygon` sont des instances `Polygon` acceptées.</span><span class="sxs-lookup"><span data-stu-id="79e9e-116">All instances comprising the `MultiPolygon` instance are accepted `Polygon` instances.</span></span> <span data-ttu-id="79e9e-117">Pour plus d’informations sur les `Polygon` instances acceptées, consultez [Polygon](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="79e9e-117">For more information on accepted `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

 <span data-ttu-id="79e9e-118">Les exemples suivants illustrent des `MultiPolygon` instances acceptées.</span><span class="sxs-lookup"><span data-stu-id="79e9e-118">The following examples show accepted `MultiPolygon` instances.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
```

 <span data-ttu-id="79e9e-119">L'exemple suivant illustre une instance MultiPolygon qui lève une exception `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="79e9e-119">The following example shows a MultiPolygon instance that will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3)))';
```

 <span data-ttu-id="79e9e-120">La deuxième instance du MultiPolygon est une instance LineString et non une instance Polygon acceptée.</span><span class="sxs-lookup"><span data-stu-id="79e9e-120">The second instance in the MultiPolygon is a LineString instance and not an accepted Polygon instance.</span></span>

### <a name="valid-instances"></a><span data-ttu-id="79e9e-121">Instances valides</span><span class="sxs-lookup"><span data-stu-id="79e9e-121">Valid Instances</span></span>
 <span data-ttu-id="79e9e-122">Les instances `MultiPolygon` sont valides s'il s'agit d'instances `MultiPolygon` vides ou si elles respectent les critères suivants.</span><span class="sxs-lookup"><span data-stu-id="79e9e-122">A `MultiPolygon` instance is valid if it is an empty `MultiPolygon` instance or if it meets the following criteria.</span></span>

1.  <span data-ttu-id="79e9e-123">Toutes les instances comprenant l'instance `MultiPolygon` sont des instances `Polygon` valides.</span><span class="sxs-lookup"><span data-stu-id="79e9e-123">All of the instances comprising the `MultiPolygon` instance are valid `Polygon` instances.</span></span> <span data-ttu-id="79e9e-124">Pour connaître les instances valides `Polygon` , consultez [Polygon](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="79e9e-124">For valid `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

2.  <span data-ttu-id="79e9e-125">Aucune des instances `Polygon` comprenant l'instance `MultiPolygon` n'en chevauche une autre.</span><span class="sxs-lookup"><span data-stu-id="79e9e-125">None of the `Polygon` instances comprising the `MultiPolygon` instance overlap.</span></span>

 <span data-ttu-id="79e9e-126">L'exemple suivant illustre deux instances `MultiPolygon` valides et une instance `MultiPolygon` non valide.</span><span class="sxs-lookup"><span data-stu-id="79e9e-126">The following example shows two valid `MultiPolygon` instances and one invalid `MultiPolygon` instance.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="79e9e-127">`@g2` n'est pas valide car les deux instances de `Polygon` se touchent uniquement sur un point tangent.</span><span class="sxs-lookup"><span data-stu-id="79e9e-127">`@g2` is valid because the two `Polygon` instances touch only at a tangent point.</span></span> <span data-ttu-id="79e9e-128">`@g3` n'est pas valide car les intérieurs des deux instances de `Polygon` se chevauchent.</span><span class="sxs-lookup"><span data-stu-id="79e9e-128">`@g3` is not valid because the interiors of the two `Polygon` instances overlap each other.</span></span>

## <a name="examples"></a><span data-ttu-id="79e9e-129">Exemples</span><span class="sxs-lookup"><span data-stu-id="79e9e-129">Examples</span></span>
 <span data-ttu-id="79e9e-130">L’exemple suivant illustre la création d’une instance `geometry``MultiPolygon` et retourne l’entrée WKT (well-known text) du deuxième composant.</span><span class="sxs-lookup"><span data-stu-id="79e9e-130">The following example shows the creation of a `geometry``MultiPolygon` instance and returns the Well-Known Text (WKT) of the second component.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON(((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1)), ((9 9, 9 10, 10 9, 9 9)))');
SELECT @g.STGeometryN(2).STAsText();
```

 <span data-ttu-id="79e9e-131">Cet exemple instancie une instance `MultiPolygon` vide.</span><span class="sxs-lookup"><span data-stu-id="79e9e-131">This example instantiates an empty `MultiPolygon` instance.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON EMPTY');
```

## <a name="see-also"></a><span data-ttu-id="79e9e-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79e9e-132">See Also</span></span>
 <span data-ttu-id="79e9e-133">[Polygon](../spatial/polygon.md) [STArea &#40;Geometry type de données&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;geometry type de données&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;Geometry type de données](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)&#41;[spatial Data](../spatial/spatial-data-sql-server.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="79e9e-133">[Polygon](../spatial/polygon.md) [STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


