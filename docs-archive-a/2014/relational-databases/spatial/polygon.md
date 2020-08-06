---
title: Polygon | Microsoft Docs
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry subtypes [SQL Server]
- Polygon geometry subtype [SQL Server]
ms.assetid: b6a21c3c-fdb8-4187-8229-1c488454fdfb
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 040bb8a2558cc57b1b99a3ce984bec3c8925bc0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613912"
---
# <a name="polygon"></a><span data-ttu-id="79d18-102">Polygone</span><span class="sxs-lookup"><span data-stu-id="79d18-102">Polygon</span></span>
  <span data-ttu-id="79d18-103">Un `Polygon` est une surface à deux dimensions stockée en tant que séquence de points définissant un anneau englobant extérieur et zéro ou plusieurs anneaux intérieurs.</span><span class="sxs-lookup"><span data-stu-id="79d18-103">A `Polygon` is a two-dimensional surface stored as a sequence of points defining an exterior bounding ring and zero or more interior rings.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="79d18-104">Instances Polygon</span><span class="sxs-lookup"><span data-stu-id="79d18-104">Polygon instances</span></span>
 <span data-ttu-id="79d18-105">Une instance `Polygon` peut être formée à partir d'un anneau qui possède au moins trois points distincts.</span><span class="sxs-lookup"><span data-stu-id="79d18-105">A `Polygon` instance can be formed from a ring that has at least three distinct points.</span></span> <span data-ttu-id="79d18-106">Une instance `Polygon` peut également être vide.</span><span class="sxs-lookup"><span data-stu-id="79d18-106">A `Polygon` instance can also be empty.</span></span>

 <span data-ttu-id="79d18-107">Les anneaux extérieurs et intérieurs d'un `Polygon` définissent sa limite.</span><span class="sxs-lookup"><span data-stu-id="79d18-107">The exterior and any interior rings of a `Polygon` define its boundary.</span></span> <span data-ttu-id="79d18-108">L'espace dans les anneaux définit l'intérieur du `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="79d18-108">The space within the rings defines the interior of the `Polygon`.</span></span>

 <span data-ttu-id="79d18-109">L'illustration suivante montre des exemples d'instances `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="79d18-109">The illustration below shows examples of `Polygon` instances.</span></span>

 <span data-ttu-id="79d18-110">![Exemples d'instances Polygon géométriques](../../database-engine/media/polygon.gif "Exemples d'instances Polygon géométriques")</span><span class="sxs-lookup"><span data-stu-id="79d18-110">![Examples of geometry Polygon instances](../../database-engine/media/polygon.gif "Examples of geometry Polygon instances")</span></span>

 <span data-ttu-id="79d18-111">Comme indiqué par l'illustration :</span><span class="sxs-lookup"><span data-stu-id="79d18-111">As shown in the illustration:</span></span>

1.  <span data-ttu-id="79d18-112">La Figure 1 est une instance `Polygon` dont la limite est définie par un anneau extérieur.</span><span class="sxs-lookup"><span data-stu-id="79d18-112">Figure 1 is a `Polygon` instance whose boundary is defined by an exterior ring.</span></span>

2.  <span data-ttu-id="79d18-113">La Figure 2 est une instance `Polygon` dont la limite est définie par un anneau extérieur et deux anneaux intérieurs.</span><span class="sxs-lookup"><span data-stu-id="79d18-113">Figure 2 is a `Polygon` instance whose boundary is defined by an exterior ring and two interior rings.</span></span> <span data-ttu-id="79d18-114">La zone à l'intérieur des anneaux intérieurs fait partie de l'extérieur de l'instance `Polygon`.</span><span class="sxs-lookup"><span data-stu-id="79d18-114">The area inside the interior rings is part of the exterior of the `Polygon` instance.</span></span>

3.  <span data-ttu-id="79d18-115">La Figure 3 est une instance `Polygon` valide car ses anneaux intérieurs se croisent à un point tangent unique.</span><span class="sxs-lookup"><span data-stu-id="79d18-115">Figure 3 is a valid `Polygon` instance because its interior rings intersect at a single tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="79d18-116">Instances acceptées</span><span class="sxs-lookup"><span data-stu-id="79d18-116">Accepted instances</span></span>
 <span data-ttu-id="79d18-117">Les instances `Polygon` acceptées sont des instances qui peuvent être stockées dans une variable `geometry` ou `geography` sans lever d'exception.</span><span class="sxs-lookup"><span data-stu-id="79d18-117">Accepted `Polygon` instances are instances that can be stored in a `geometry` or `geography` variable without throwing an exception.</span></span> <span data-ttu-id="79d18-118">Les instances `Polygon` suivantes sont acceptées :</span><span class="sxs-lookup"><span data-stu-id="79d18-118">The following are accepted `Polygon` instances:</span></span>

-   <span data-ttu-id="79d18-119">Instance `Polygon` vide</span><span class="sxs-lookup"><span data-stu-id="79d18-119">An Empty `Polygon` instance</span></span>

-   <span data-ttu-id="79d18-120">Instance `Polygon` qui a un anneau extérieur acceptable et zéro ou plusieurs anneaux intérieurs acceptables</span><span class="sxs-lookup"><span data-stu-id="79d18-120">A `Polygon` instance that has an acceptable exterior ring and zero or more acceptable interior rings</span></span>

 <span data-ttu-id="79d18-121">Les critères suivants sont nécessaires pour qu'un anneau soit acceptable.</span><span class="sxs-lookup"><span data-stu-id="79d18-121">The following criteria are needed for a ring to be acceptable.</span></span>

-   <span data-ttu-id="79d18-122">L'instance `LineString` doit être acceptée.</span><span class="sxs-lookup"><span data-stu-id="79d18-122">The `LineString` instance must be accepted.</span></span>

-   <span data-ttu-id="79d18-123">L'instance `LineString` doit avoir au moins quatre points.</span><span class="sxs-lookup"><span data-stu-id="79d18-123">The `LineString` instance must have at least four points.</span></span>

-   <span data-ttu-id="79d18-124">Les points de début et de fin de l'instance `LineString` doivent être les mêmes.</span><span class="sxs-lookup"><span data-stu-id="79d18-124">The starting and ending points of the `LineString` instance must be the same.</span></span>

 <span data-ttu-id="79d18-125">L'exemple suivant illustre des instances `Polygon` acceptées.</span><span class="sxs-lookup"><span data-stu-id="79d18-125">The following example shows accepted `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON EMPTY';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 1))';
DECLARE @g3 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 3 3, 0 3, 0 0))';
DECLARE @g4 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(3 0, 6 0, 6 3, 3 3, 3 0))';
DECLARE @g5 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
```

 <span data-ttu-id="79d18-126">Comme le montrent `@g4` and `@g5`, une instance `Polygon` acceptée peut ne pas être une instance `Polygon` valide.</span><span class="sxs-lookup"><span data-stu-id="79d18-126">As `@g4` and `@g5` show an accepted `Polygon` instance may not be a valid `Polygon` instance.</span></span> <span data-ttu-id="79d18-127">`@g5` montre également qu’une instance Polygon doit contenir uniquement un anneau avec quatre points quelconques à accepter.</span><span class="sxs-lookup"><span data-stu-id="79d18-127">`@g5` also shows that a Polygon instance needs to only contain a ring with any four points to be accepted.</span></span>

 <span data-ttu-id="79d18-128">Les exemples suivants lèvent une `System.FormatException` parce que les instances `Polygon` ne sont pas acceptées.</span><span class="sxs-lookup"><span data-stu-id="79d18-128">The following examples throw a `System.FormatException` because the `Polygon` instances are not accepted.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((1 1, 3 3, 1 1))';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 5))';
```

 <span data-ttu-id="79d18-129">`@g1` n'est pas accepté parce que l'instance `LineString` pour l'anneau extérieur ne contient pas assez de points.</span><span class="sxs-lookup"><span data-stu-id="79d18-129">`@g1` is not accepted because the `LineString` instance for the exterior ring does not contain enough points.</span></span> <span data-ttu-id="79d18-130">`@g2` n'est pas accepté car le point de départ de l'instance `LineString` de l'anneau extérieur n'est pas identique au point de fin.</span><span class="sxs-lookup"><span data-stu-id="79d18-130">`@g2` is not accepted because the starting point of the exterior ring `LineString` instance is not the same as the ending point.</span></span> <span data-ttu-id="79d18-131">L'exemple suivant a un anneau extérieur acceptable, mais l'anneau intérieur n'est pas acceptable.</span><span class="sxs-lookup"><span data-stu-id="79d18-131">The following example has an acceptable exterior ring, but the interior ring is not acceptable.</span></span> <span data-ttu-id="79d18-132">Cela lève également une `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="79d18-132">This also throws a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 0 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="79d18-133">Instances valides</span><span class="sxs-lookup"><span data-stu-id="79d18-133">Valid instances</span></span>
 <span data-ttu-id="79d18-134">Les anneaux intérieurs d'un `Polygon` peuvent se toucher eux-mêmes et l'un l'autre à des points tangents uniques, mais si les anneaux intérieurs d'un `Polygon` se croisent, l'instance n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="79d18-134">The interior rings of a `Polygon` can touch both themselves and each other at single tangent points, but if the interior rings of a `Polygon` cross, the instance is not valid.</span></span>

 <span data-ttu-id="79d18-135">L'exemple suivant montre des instances `Polygon` valides.</span><span class="sxs-lookup"><span data-stu-id="79d18-135">The following example shows valid `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, -5 -10, -10 0))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="79d18-136">`@g3` est valide parce que les deux anneaux intérieurs se touchent à un point unique et ne se croisent pas l’un l’autre.</span><span class="sxs-lookup"><span data-stu-id="79d18-136">`@g3` is valid because the two interior rings touch at a single point and do not cross each other.</span></span> <span data-ttu-id="79d18-137">L'exemple suivant montre des instances `Polygon` qui ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="79d18-137">The following example shows `Polygon` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (20 0, 0 10, 0 -20, 20 0))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (5 0, 1 5, 1 -5, 5 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, 0 -10, -10 0))';
DECLARE @g4 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 1 5, 0 -10, -10 0))';
DECLARE @g5 geometry = 'POLYGON((10 0, 0 10, 0 -10, 10 0), (-20 -20, -20 20, 20 20, 20 -20, -20 -20) )';
DECLARE @g6 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid(), @g5.STIsValid(), @g6.STIsValid();
```

 <span data-ttu-id="79d18-138">`@g1` n’est pas valide, car la boucle interne touche l’anneau intérieur à deux endroits.</span><span class="sxs-lookup"><span data-stu-id="79d18-138">`@g1` is not valid because the inner ring touches the exterior ring in two places.</span></span> <span data-ttu-id="79d18-139">`@g2` n’est pas valide, car le deuxième anneau intérieur est à l’intérieur du premier anneau intérieur.</span><span class="sxs-lookup"><span data-stu-id="79d18-139">`@g2` is not valid because the second inner ring in within the interior of the first inner ring.</span></span> <span data-ttu-id="79d18-140">`@g3` n’est pas valide, car les deux anneaux intérieurs se touchent au niveau de plusieurs points consécutifs.</span><span class="sxs-lookup"><span data-stu-id="79d18-140">`@g3` is not valid because the two inner rings touch at multiple consecutive points.</span></span> <span data-ttu-id="79d18-141">`@g4` n’est pas valide, car les parties intérieures des deux anneaux intérieurs se chevauchent.</span><span class="sxs-lookup"><span data-stu-id="79d18-141">`@g4` is not valid because the interiors of the two inner rings overlap.</span></span> <span data-ttu-id="79d18-142">`@g5` n’est pas valide, car l’anneau extérieur n’est pas le premier anneau.</span><span class="sxs-lookup"><span data-stu-id="79d18-142">`@g5` is not valid because the exterior ring is not the first ring.</span></span> <span data-ttu-id="79d18-143">`@g6` n’est pas valide, car la boucle n’a pas au moins trois points distincts.</span><span class="sxs-lookup"><span data-stu-id="79d18-143">`@g6` is not valid because the ring does not have at least three distinct points.</span></span>

## <a name="examples"></a><span data-ttu-id="79d18-144">Exemples</span><span class="sxs-lookup"><span data-stu-id="79d18-144">Examples</span></span>
 <span data-ttu-id="79d18-145">L’exemple suivant crée une instance `geometry``Polygon` simple avec un trou et un SRID 10.</span><span class="sxs-lookup"><span data-stu-id="79d18-145">The following example creates a simple `geometry``Polygon` instance with a hole and SRID 10.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STPolyFromText('POLYGON((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1))', 10);
```

 <span data-ttu-id="79d18-146">Une instance non valide peut être entrée et convertie en une instance `geometry` valide.</span><span class="sxs-lookup"><span data-stu-id="79d18-146">Aninstance that is not valid may be entered and converted to a valid `geometry` instance.</span></span> <span data-ttu-id="79d18-147">Dans l'exemple suivant d'un `Polygon`, les anneaux intérieurs et extérieurs se chevauchent et l'instance n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="79d18-147">In the following example of a `Polygon`, the interior and exterior rings overlap and the instance is not valid.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('POLYGON((1 0, 0 1, 1 2, 2 1, 1 0), (2 0, 1 1, 2 2, 3 1, 2 0))');
```

 <span data-ttu-id="79d18-148">Dans l'exemple suivant, l'instance non valide est rendue valide avec `MakeValid()`.</span><span class="sxs-lookup"><span data-stu-id="79d18-148">In the following example, the invalid instance is made valid with `MakeValid()`.</span></span>

```
SET @g = @g.MakeValid();
SELECT @g.ToString();
```

 <span data-ttu-id="79d18-149">L'instance `geometry` retournée par l'exemple ci-dessus est un `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="79d18-149">The `geometry` instance returned from the above example is a `MultiPolygon`.</span></span>

```
MULTIPOLYGON (((2 0, 3 1, 2 2, 1.5 1.5, 2 1, 1.5 0.5, 2 0)), ((1 0, 1.5 0.5, 1 1, 1.5 1.5, 1 2, 0 1, 1 0)))
```

 <span data-ttu-id="79d18-150">Voici un autre exemple de conversion d'une instance non valide en instance geometry valide.</span><span class="sxs-lookup"><span data-stu-id="79d18-150">Here is another example of converting an invalid instance to a valid geometry instance.</span></span> <span data-ttu-id="79d18-151">Dans l'exemple suivant, l'instance `Polygon` a été créée à l'aide de trois points qui sont exactement les mêmes :</span><span class="sxs-lookup"><span data-stu-id="79d18-151">In the following example the `Polygon` instance has been created using three points that are exactly the same:</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('POLYGON((1 3, 1 3, 1 3, 1 3))');
SET @g = @g.MakeValid();
SELECT @g.ToString()
```

 <span data-ttu-id="79d18-152">L'instance geometry retourné ci-dessus est un `Point(1 3)`.</span><span class="sxs-lookup"><span data-stu-id="79d18-152">The geometry instance returned above is a `Point(1 3)`.</span></span>  <span data-ttu-id="79d18-153">Si le `Polygon` donné est `POLYGON((1 3, 1 5, 1 3, 1 3))` , alors `MakeValid()` retourne `LINESTRING(1 3, 1 5)`.</span><span class="sxs-lookup"><span data-stu-id="79d18-153">If the `Polygon` given is `POLYGON((1 3, 1 5, 1 3, 1 3))` then `MakeValid()` would return `LINESTRING(1 3, 1 5)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="79d18-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79d18-154">See Also</span></span>
 <span data-ttu-id="79d18-155">[STArea &#40;Geometry type de données&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;Geometry type de données&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;geometry type de données&#41;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [STInteriorRingN &#40;geometry type de données&#41;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) [STCentroid &#40;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) type [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [de données](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) Geometry&#41;[STPointOnSurface &#40;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [&#41;type de](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) données geometry [&#40;](../spatial/polygon.md)</span><span class="sxs-lookup"><span data-stu-id="79d18-155">[STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [STInteriorRingN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [MultiPolygon](../spatial/polygon.md) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)</span></span>


