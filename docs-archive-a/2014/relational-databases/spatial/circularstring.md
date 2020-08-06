---
title: CircularString | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 9fe06b03-d98c-4337-9f89-54da98f49f9f
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c701cdc2e8538a5b91093e17714fd9f6508d1c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601313"
---
# <a name="circularstring"></a><span data-ttu-id="31833-102">CircularString</span><span class="sxs-lookup"><span data-stu-id="31833-102">CircularString</span></span>
  <span data-ttu-id="31833-103">Un `CircularString` est une collection de zéro ou plusieurs segments d'arc de cercle continus.</span><span class="sxs-lookup"><span data-stu-id="31833-103">A `CircularString` is a collection of zero or more continuous circular arc segments.</span></span> <span data-ttu-id="31833-104">Un segment d'arc de cercle est un segment courbé défini par trois points dans un plan à deux dimensions ; le premier point doit être différent du troisième point.</span><span class="sxs-lookup"><span data-stu-id="31833-104">A circular arc segment is a curved segment defined by three points in a two-dimensional plane; the first point cannot be the same as the third point.</span></span> <span data-ttu-id="31833-105">Si les trois points d'un segment d'arc de cercle sont colinéaires, le segment d'arc est traité comme un segment de ligne.</span><span class="sxs-lookup"><span data-stu-id="31833-105">If all three points of a circular arc segment are collinear, the arc segment is treated as a line segment.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="31833-106">Pour obtenir une description détaillée et des exemples des nouvelles fonctionnalités spatiales introduites dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , y compris le `CircularString` sous-type, téléchargez le livre blanc [nouvelles fonctionnalités spatiales dans SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="31833-106">For a detailed description and examples of the new spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CircularString` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

## <a name="circularstring-instances"></a><span data-ttu-id="31833-107">Instances CircularString</span><span class="sxs-lookup"><span data-stu-id="31833-107">CircularString instances</span></span>
 <span data-ttu-id="31833-108">Le dessin suivant montre des instances `CircularString` valides :</span><span class="sxs-lookup"><span data-stu-id="31833-108">The drawing below shows valid `CircularString` instances:</span></span>

 ![](../../database-engine/media/5ff17e34-b578-4873-9d33-79500940d0bc.png "5ff17e34-b578-4873-9d33-79500940d0bc")

### <a name="accepted-instances"></a><span data-ttu-id="31833-109">Instances acceptées</span><span class="sxs-lookup"><span data-stu-id="31833-109">Accepted instances</span></span>
 <span data-ttu-id="31833-110">Une `CircularString` instance est acceptée si elle est vide ou si elle contient un nombre impair de points, n, où n > 1.</span><span class="sxs-lookup"><span data-stu-id="31833-110">A `CircularString` instance is accepted if it is either empty or contains an odd number of points, n, where n > 1.</span></span> <span data-ttu-id="31833-111">Les instances `CircularString` suivantes sont acceptées.</span><span class="sxs-lookup"><span data-stu-id="31833-111">The following `CircularString` instances are accepted.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 2 0, 1 1)';
```

 <span data-ttu-id="31833-112">`@g3` montre que l'instance `CircularString` peut être acceptée, mais pas valide.</span><span class="sxs-lookup"><span data-stu-id="31833-112">`@g3` shows that `CircularString` instance may be accepted, but not valid.</span></span> <span data-ttu-id="31833-113">La déclaration suivante d'instance de CircularString n'est pas acceptée.</span><span class="sxs-lookup"><span data-stu-id="31833-113">The following CircularString instance declaration is not accepted.</span></span> <span data-ttu-id="31833-114">Cette déclaration lève une `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="31833-114">This declaration throws a `System.FormatException`.</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="31833-115">Instances valides</span><span class="sxs-lookup"><span data-stu-id="31833-115">Valid instances</span></span>
 <span data-ttu-id="31833-116">Une instance `CircularString` valide doit être vide ou avoir les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="31833-116">A valid `CircularString` instance must be empty or have the following attributes:</span></span>

-   <span data-ttu-id="31833-117">Elle doit contenir au moins un segment d'arc de cercle (autrement dit, voir un minimum de trois points).</span><span class="sxs-lookup"><span data-stu-id="31833-117">It must contain at least one circular arc segment (that is, have a minimum of three points).</span></span>

-   <span data-ttu-id="31833-118">Le dernier point de terminaison de chaque segment d'arc de cercle de la séquence, à l'exception du dernier segment, doit correspondre au premier point de terminaison du segment suivant dans la séquence.</span><span class="sxs-lookup"><span data-stu-id="31833-118">The last endpoint for each circular arc segment in the sequence, except for the last segment, must be the first endpoint for the next segment in the sequence.</span></span>

-   <span data-ttu-id="31833-119">Elle doit comporter un nombre impair de points.</span><span class="sxs-lookup"><span data-stu-id="31833-119">It must have an odd number of points.</span></span>

-   <span data-ttu-id="31833-120">Elle ne peut pas se chevaucher sur un intervalle.</span><span class="sxs-lookup"><span data-stu-id="31833-120">It cannot overlap itself over an interval.</span></span>

-   <span data-ttu-id="31833-121">Bien que les instances `CircularString` puissent contenir des segments de ligne, ces segments de ligne doivent être définis par trois points colinéaires.</span><span class="sxs-lookup"><span data-stu-id="31833-121">Although `CircularString` instances may contain line segments, these line segments must be defined by three collinear points.</span></span>

 <span data-ttu-id="31833-122">L'exemple suivant montre des instances `CircularString` valides.</span><span class="sxs-lookup"><span data-stu-id="31833-122">The following example shows valid `CircularString` instances.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1, 0 1)';
DECLARE @g4 geometry = 'CIRCULARSTRING(1 1, 2 2, 2 2)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(),@g4.STIsValid();
```

 <span data-ttu-id="31833-123">Une instance `CircularString` doit contenir au moins deux segments d'arc de cercle pour définir un cercle complet.</span><span class="sxs-lookup"><span data-stu-id="31833-123">A `CircularString` instance must contain at least two circular arc segments to define a complete circle.</span></span> <span data-ttu-id="31833-124">Une instance `CircularString` ne peut pas utiliser un seul segment d'arc de cercle (tel que (1 1, 3 1, 1 1)) pour définir un cercle complet.</span><span class="sxs-lookup"><span data-stu-id="31833-124">A `CircularString` instance cannot use a single circular arc segment (such as (1 1, 3 1, 1 1)) to define a complete circle.</span></span> <span data-ttu-id="31833-125">Utilisez (1 1, 2 2, 3 1, 2 0, 1 1) pour définir le cercle.</span><span class="sxs-lookup"><span data-stu-id="31833-125">Use (1 1, 2 2, 3 1, 2 0, 1 1) to define the circle.</span></span>

 <span data-ttu-id="31833-126">L'exemple suivant montre des instances CircularString qui ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="31833-126">The following example shows CircularString instances that are not valid.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING(1 1, 2 0, 1 1)';
DECLARE @g2 geometry = 'CIRCULARSTRING(0 0, 0 0, 0 0)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

### <a name="instances-with-collinear-points"></a><span data-ttu-id="31833-127">Instances avec des points colinéaires</span><span class="sxs-lookup"><span data-stu-id="31833-127">Instances with collinear points</span></span>
 <span data-ttu-id="31833-128">Dans les cas suivants un segment d'arc de cercle sera traité comme un segment de ligne :</span><span class="sxs-lookup"><span data-stu-id="31833-128">In the following cases a circular arc segment will be treated as a line segment:</span></span>

-   <span data-ttu-id="31833-129">lorsque les trois points sont colinéaires (par exemple, (1 3, 4 4, 7 5)) ;</span><span class="sxs-lookup"><span data-stu-id="31833-129">When all three points are collinear (for example, (1 3, 4 4, 7 5)).</span></span>

-   <span data-ttu-id="31833-130">lorsque le premier point et le point central sont les mêmes, mais que le troisième point est différent (par exemple, (1 3, 1 3, 7 5)) ;</span><span class="sxs-lookup"><span data-stu-id="31833-130">When the first and middle point are the same, but the third point is different (for example, (1 3, 1 3, 7 5)).</span></span>

-   <span data-ttu-id="31833-131">lorsque le point central et le dernier point sont les mêmes, mais que le premier point est différent (par exemple, (1 3, 4 4, 4 4)).</span><span class="sxs-lookup"><span data-stu-id="31833-131">When the middle and last point are the same, but the first point is different (for example, (1 3, 4 4, 4 4)).</span></span>

## <a name="examples"></a><span data-ttu-id="31833-132">Exemples</span><span class="sxs-lookup"><span data-stu-id="31833-132">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-circularstring"></a><span data-ttu-id="31833-133">R.</span><span class="sxs-lookup"><span data-stu-id="31833-133">A.</span></span> <span data-ttu-id="31833-134">Instanciation d'une instance géométrique à l'aide d'un CircularString vide</span><span class="sxs-lookup"><span data-stu-id="31833-134">Instantiating a Geometry Instance with an Empty CircularString</span></span>
 <span data-ttu-id="31833-135">Cet exemple indique comment créer une instance `CircularString` vide :</span><span class="sxs-lookup"><span data-stu-id="31833-135">This example shows how to create an empty `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING EMPTY');
```

### <a name="b-instantiating-a-geometry-instance-using-a-circularstring-with-one-circular-arc-segment"></a><span data-ttu-id="31833-136">B.</span><span class="sxs-lookup"><span data-stu-id="31833-136">B.</span></span> <span data-ttu-id="31833-137">Instanciation d'une instance géométrique à l'aide d'un CircularString avec un segment d'arc de cercle</span><span class="sxs-lookup"><span data-stu-id="31833-137">Instantiating a Geometry Instance Using a CircularString with One Circular Arc Segment</span></span>
 <span data-ttu-id="31833-138">L'exemple suivant indique comment créer une instance `CircularString` avec un segment d'arc de cercle unique (demi-cercle) :</span><span class="sxs-lookup"><span data-stu-id="31833-138">The following example shows how to create a `CircularString` instance with a single circular arc segment (half-circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry:: STGeomFromText('CIRCULARSTRING(2 0, 1 1, 0 0)', 0);
SELECT @g.ToString();
```

### <a name="c-instantiating-a-geometry-instance-using-a-circularstring-with-multiple-circular-arc-segments"></a><span data-ttu-id="31833-139">C.</span><span class="sxs-lookup"><span data-stu-id="31833-139">C.</span></span> <span data-ttu-id="31833-140">Instanciation d'une instance géométrique à l'aide d'un CircularString avec plusieurs segments d'arc de cercle</span><span class="sxs-lookup"><span data-stu-id="31833-140">Instantiating a Geometry Instance Using a CircularString with Multiple Circular Arc Segments</span></span>
 <span data-ttu-id="31833-141">L'exemple suivant indique comment créer une instance `CircularString` avec plusieurs segments d'arc de cercle (cercle complet) :</span><span class="sxs-lookup"><span data-stu-id="31833-141">The following example shows how to create a `CircularString` instance with more than one circular arc segment (full circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING(2 1, 1 2, 0 1, 1 0, 2 1)');
SELECT 'Circumference = ' + CAST(@g.STLength() AS NVARCHAR(10));  
```

 <span data-ttu-id="31833-142">Ce code produit la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="31833-142">This produces the following output:</span></span>

```
Circumference = 6.28319
```

 <span data-ttu-id="31833-143">Comparez la sortie lorsque `LineString` est utilisé à la place de `CircularString` :</span><span class="sxs-lookup"><span data-stu-id="31833-143">Compare the output when `LineString` is used instead of `CircularString`:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(2 1, 1 2, 0 1, 1 0, 2 1)', 0);
SELECT 'Perimeter = ' + CAST(@g.STLength() AS NVARCHAR(10));
```

 <span data-ttu-id="31833-144">Ce code produit la sortie suivante :</span><span class="sxs-lookup"><span data-stu-id="31833-144">This produces the following output:</span></span>

```
Perimeter = 5.65685
```

 <span data-ttu-id="31833-145">Notez que la valeur de l' `CircularString` exemple est proche de 2&#x03c0; (2 \* pi), qui est la circonférence réelle du cercle.</span><span class="sxs-lookup"><span data-stu-id="31833-145">Notice that the value for the `CircularString` example is close to 2&#x03c0; (2 \* pi), which is the actual circumference of the circle.</span></span>

### <a name="d-declaring-and-instantiating-a-geometry-instance-with-a-circularstring-in-the-same-statement"></a><span data-ttu-id="31833-146">D.</span><span class="sxs-lookup"><span data-stu-id="31833-146">D.</span></span> <span data-ttu-id="31833-147">Déclaration et instanciation d'une instance géométrique avec un CircularString dans la même instruction</span><span class="sxs-lookup"><span data-stu-id="31833-147">Declaring and Instantiating a Geometry Instance with a CircularString in the Same Statement</span></span>
 <span data-ttu-id="31833-148">Cet extrait de code indique comment déclarer et instancier une instance `geometry` avec un `CircularString` dans la même instruction :</span><span class="sxs-lookup"><span data-stu-id="31833-148">This snippet shows how to declare and instantiate a `geometry` instance with a `CircularString` in the same statement:</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)';
```

### <a name="e-instantiating-a-geography-instance-with-a-circularstring"></a><span data-ttu-id="31833-149">E.</span><span class="sxs-lookup"><span data-stu-id="31833-149">E.</span></span> <span data-ttu-id="31833-150">Instanciation d'une instance géographique avec un CircularString</span><span class="sxs-lookup"><span data-stu-id="31833-150">Instantiating a Geography Instance with a CircularString</span></span>
 <span data-ttu-id="31833-151">L'exemple suivant indique comment déclarer et instancier une instance `geography` avec un `CircularString` :</span><span class="sxs-lookup"><span data-stu-id="31833-151">The following example shows how to declare and instantiate a `geography` instance with a `CircularString`:</span></span>

```sql
DECLARE @g geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';
```

### <a name="f-instantiating-a-geometry-instance-with-a-circularstring-that-is-a-straight-line"></a><span data-ttu-id="31833-152">F.</span><span class="sxs-lookup"><span data-stu-id="31833-152">F.</span></span> <span data-ttu-id="31833-153">Instanciation d'une instance géométrique avec un CircularString qui est une ligne droite</span><span class="sxs-lookup"><span data-stu-id="31833-153">Instantiating a Geometry Instance with a CircularString that is a Straight Line</span></span>
 <span data-ttu-id="31833-154">L'exemple suivant indique comment créer une instance `CircularString` qui est une ligne droite :</span><span class="sxs-lookup"><span data-stu-id="31833-154">The following example shows how to create a `CircularString` instance that is a straight line:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('CIRCULARSTRING(0 0, 1 2, 2 4)', 0);
```

## <a name="see-also"></a><span data-ttu-id="31833-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31833-155">See Also</span></span>
 <span data-ttu-id="31833-156">[Vue d’ensemble des types de données spatiales](spatial-data-types-overview.md) [CompoundCurve](compoundcurve.md) [MakeValid &#40;type de données geography&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;geometry type de données&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [STIsValid &#40;Geometry type](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) de données&#41;STIsValid &#40;type de données [Geography&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STLength](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) &#40;type de données geometry [&#41;STStartPoint](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [&#40;STEndPoint&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [type de](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) données geometry &#40;[STPointN&#41;type](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) de données geometry [&#40;STNumPoints](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [&#41;type de](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) données geometry STIsRing [&#40;STIsClosed](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [LineString](linestring.md)</span><span class="sxs-lookup"><span data-stu-id="31833-156">[Spatial Data Types Overview](spatial-data-types-overview.md) [CompoundCurve](compoundcurve.md) [MakeValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [LineString](linestring.md)</span></span>


