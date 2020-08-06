---
title: CurvePolygon | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e000a1d8-a049-4542-bfeb-943fd6ab3969
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b90fdbd9a0bc80dfc6a82416d0193b2951fe13ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601306"
---
# <a name="curvepolygon"></a><span data-ttu-id="3771c-102">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="3771c-102">CurvePolygon</span></span>
  <span data-ttu-id="3771c-103">Un `CurvePolygon` est une surface topologiquement fermée définie par un anneau englobant extérieur et zéro ou plusieurs anneaux intérieurs.</span><span class="sxs-lookup"><span data-stu-id="3771c-103">A `CurvePolygon` is a topologically closed surface defined by an exterior bounding ring and zero or more interior rings</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3771c-104">Pour obtenir une description détaillée et des exemples des fonctionnalités spatiales introduites dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , y compris le `CurvePolygon` sous-type, téléchargez le livre blanc [nouvelles fonctionnalités spatiales dans SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="3771c-104">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CurvePolygon` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="3771c-105">Les critères suivants définissent les attributs d’une `CurvePolygon` instance :</span><span class="sxs-lookup"><span data-stu-id="3771c-105">The following criteria define attributes of a `CurvePolygon` instance:</span></span>  
  
-   <span data-ttu-id="3771c-106">La limite de l'instance `CurvePolygon` est définie par l'anneau extérieur et tous les anneaux intérieurs.</span><span class="sxs-lookup"><span data-stu-id="3771c-106">The boundary of the `CurvePolygon` instance is defined by the exterior ring and all interior rings.</span></span>  
  
-   <span data-ttu-id="3771c-107">L'intérieur de l'instance `CurvePolygon` désigne l'espace situé entre l'anneau extérieur et tous les anneaux intérieurs.</span><span class="sxs-lookup"><span data-stu-id="3771c-107">The interior of the `CurvePolygon` instance is the space between the exterior ring and all of the interior rings.</span></span>  
  
 <span data-ttu-id="3771c-108">Une instance `CurvePolygon` diffère d'une instance `Polygon` en cela qu'une instance `CurvePolygon` peut contenir les segments d'arc de cercle suivants : `CircularString` et `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="3771c-108">A `CurvePolygon` instance differs from a `Polygon` instance in that a `CurvePolygon` instance may contain the following circular arc segments: `CircularString` and `CompoundCurve`.</span></span>  
  
## <a name="compoundcurve-instances"></a><span data-ttu-id="3771c-109">Instances CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="3771c-109">CompoundCurve instances</span></span>  
 <span data-ttu-id="3771c-110">L'illustration ci-dessous montre des figures de `CurvePolygon` valides :</span><span class="sxs-lookup"><span data-stu-id="3771c-110">Illustration below shows valid `CurvePolygon` figures:</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="3771c-111">Instances acceptées</span><span class="sxs-lookup"><span data-stu-id="3771c-111">Accepted instances</span></span>  
 <span data-ttu-id="3771c-112">Pour qu'une instance `CurvePolygon` soit acceptée, elle doit être soit vide, soit contenir uniquement des anneaux d'arc circulaires acceptés.</span><span class="sxs-lookup"><span data-stu-id="3771c-112">For a `CurvePolygon` instance to be accepted, it needs to be either empty or contain only circular arc rings that are accepted.</span></span> <span data-ttu-id="3771c-113">Un anneau d'arc circulaire accepté satisfait les exigences suivantes.</span><span class="sxs-lookup"><span data-stu-id="3771c-113">An accepted circular arc ring meets the following requirements.</span></span>  
  
1.  <span data-ttu-id="3771c-114">Être une instance acceptée `LineString`, `CircularString` ou `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="3771c-114">Is an accepted `LineString`, `CircularString`, or `CompoundCurve` instance.</span></span> <span data-ttu-id="3771c-115">Pour plus d'informations sur les instances acceptées, consultez [LineString](linestring.md), [CircularString](circularstring.md)et [CompoundCurve](compoundcurve.md).</span><span class="sxs-lookup"><span data-stu-id="3771c-115">For more information on accepted instances, see [LineString](linestring.md), [CircularString](circularstring.md), and [CompoundCurve](compoundcurve.md).</span></span>  
  
2.  <span data-ttu-id="3771c-116">Contenir au moins quatre points.</span><span class="sxs-lookup"><span data-stu-id="3771c-116">Has at least four points.</span></span>  
  
3.  <span data-ttu-id="3771c-117">Le point de début et le point de fin ont les mêmes coordonnées X et Y.</span><span class="sxs-lookup"><span data-stu-id="3771c-117">The start and end point have the same X and Y coordinates.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3771c-118">Les valeurs Z et M sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="3771c-118">Z and M values are ignored.</span></span>  
  
 <span data-ttu-id="3771c-119">L'exemple suivant illustre des instances `CurvePolygon` acceptées.</span><span class="sxs-lookup"><span data-stu-id="3771c-119">The following example shows accepted `CurvePolygon` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0, 0 0))';  
DECLARE @g3 geometry = 'CURVEPOLYGON((0 0 1, 0 0 2, 0 0 3, 0 0 3))'  
DECLARE @g4 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
DECLARE @g5 geography = 'CURVEPOLYGON((-122.3 47, 122.3 -47, 125.7 -49, 121 -38, -122.3 47))';  
```  
  
 <span data-ttu-id="3771c-120">`@g3` est accepté bien que les points de début et de fin aient des valeurs Z différentes, car les valeurs Z sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="3771c-120">`@g3` is accepted even though the start and end points have different Z values because Z values are ignored.</span></span> <span data-ttu-id="3771c-121">`@g5` est accepté même si l'instance de type `geography` n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="3771c-121">`@g5` is accepted even though the `geography` type instance is not valid.</span></span>  
  
 <span data-ttu-id="3771c-122">Les exemples suivants lèvent une `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="3771c-122">The following examples throw `System.FormatException`.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON((0 5, 0 0, 0 0, 0 0))';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0))';  
```  
  
 <span data-ttu-id="3771c-123">`@g1` n'est pas accepté parce que les points de début et de fin n'ont pas la même valeur Y.</span><span class="sxs-lookup"><span data-stu-id="3771c-123">`@g1` is not accepted because the start and end points do not have the same Y value.</span></span> <span data-ttu-id="3771c-124">`@g2` n'est pas accepté car la boucle n'a pas assez de points.</span><span class="sxs-lookup"><span data-stu-id="3771c-124">`@g2` is not accepted because the ring does not have enough points.</span></span>  
  
### <a name="valid-instances"></a><span data-ttu-id="3771c-125">Instances valides</span><span class="sxs-lookup"><span data-stu-id="3771c-125">Valid instances</span></span>  
 <span data-ttu-id="3771c-126">Pour qu'une instance `CurvePolygon` soit valide, les anneaux extérieur et intérieur doivent répondre aux critères suivants :</span><span class="sxs-lookup"><span data-stu-id="3771c-126">For a `CurvePolygon` instance to be valid both exterior and interior rings must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="3771c-127">Ils peuvent se toucher uniquement à des points de tangentes uniques.</span><span class="sxs-lookup"><span data-stu-id="3771c-127">They may only touch at single tangent points.</span></span>  
  
2.  <span data-ttu-id="3771c-128">Ils ne peuvent pas se croiser l'un l'autre.</span><span class="sxs-lookup"><span data-stu-id="3771c-128">They cannot cross each other.</span></span>  
  
3.  <span data-ttu-id="3771c-129">Chaque anneau doit contenir au moins quatre points.</span><span class="sxs-lookup"><span data-stu-id="3771c-129">Each ring must contain at least four points.</span></span>  
  
4.  <span data-ttu-id="3771c-130">Chaque anneau doit être un type de courbe acceptable.</span><span class="sxs-lookup"><span data-stu-id="3771c-130">Each ring must be an acceptable curve type.</span></span>  
  
 <span data-ttu-id="3771c-131">Les instances `CurvePolygon` doivent également répondre à des critères spécifiques, selon qu'il s'agisse de types de données `geometry` ou `geography`.</span><span class="sxs-lookup"><span data-stu-id="3771c-131">`CurvePolygon` instances also need to meet specific criteria depending on whether they are `geometry` or `geography` data types.</span></span>  
  
#### <a name="geometry-data-type"></a><span data-ttu-id="3771c-132">Type de données geometry</span><span class="sxs-lookup"><span data-stu-id="3771c-132">Geometry data type</span></span>  
 <span data-ttu-id="3771c-133">Une instance **geometryCurvePolygon** valide doit avoir les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="3771c-133">A valid **geometryCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="3771c-134">Tous les anneaux intérieurs doivent être contenus dans l'anneau extérieur.</span><span class="sxs-lookup"><span data-stu-id="3771c-134">All the interior rings must be contained within the exterior ring.</span></span>  
  
2.  <span data-ttu-id="3771c-135">Elle peut contenir plusieurs anneaux intérieurs, mais un anneau intérieur ne peut pas contenir un autre anneau intérieur.</span><span class="sxs-lookup"><span data-stu-id="3771c-135">May have multiple interior rings, but an interior ring cannot contain another interior ring.</span></span>  
  
3.  <span data-ttu-id="3771c-136">Aucun anneau ne peut se croiser lui-même ni croiser un autre anneau.</span><span class="sxs-lookup"><span data-stu-id="3771c-136">No ring can cross itself or another ring.</span></span>  
  
4.  <span data-ttu-id="3771c-137">Les anneaux ne peuvent se toucher qu'à des points de tangentes uniques (nombre de points où le contact des anneaux doit être fini).</span><span class="sxs-lookup"><span data-stu-id="3771c-137">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
5.  <span data-ttu-id="3771c-138">L'intérieur du polygone doit être connecté.</span><span class="sxs-lookup"><span data-stu-id="3771c-138">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="3771c-139">L’exemple suivant montre des instances **geometryCurvePolygon** valides.</span><span class="sxs-lookup"><span data-stu-id="3771c-139">The following example shows valid **geometryCurvePolygon** instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
SELECT @g1.STIsValid(), @g2.STIsValid();  
```  
  
 <span data-ttu-id="3771c-140">Les instances CurvePolygon ont les mêmes règles de validité que les instances Polygon, à l'exception près que les instances CurvePolygon peuvent accepter les nouveaux types de segment d'arc de cercle.</span><span class="sxs-lookup"><span data-stu-id="3771c-140">CurvePolygon instances have the same validity rules as Polygon instances with the exception that CurvePolygon instances may accept the new circular arc segment types.</span></span> <span data-ttu-id="3771c-141">Pour obtenir davantage d'exemples d'instances valides ou non valides, consultez [Polygon](polygon.md).</span><span class="sxs-lookup"><span data-stu-id="3771c-141">For more examples of instances that are valid or not valid, see [Polygon](polygon.md).</span></span>  
  
#### <a name="geography-data-type"></a><span data-ttu-id="3771c-142">Type de données geography</span><span class="sxs-lookup"><span data-stu-id="3771c-142">Geography data type</span></span>  
 <span data-ttu-id="3771c-143">Une instance **geographyCurvePolygon** valide doit avoir les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="3771c-143">A valid **geographyCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="3771c-144">L'intérieur du polygone est connecté à l'aide de la règle gauche.</span><span class="sxs-lookup"><span data-stu-id="3771c-144">The interior of the polygon is connected using the left-hand rule.</span></span>  
  
2.  <span data-ttu-id="3771c-145">Aucun anneau ne peut se croiser lui-même ni croiser un autre anneau.</span><span class="sxs-lookup"><span data-stu-id="3771c-145">No ring can cross itself or another ring.</span></span>  
  
3.  <span data-ttu-id="3771c-146">Les anneaux ne peuvent se toucher qu'à des points de tangentes uniques (nombre de points où le contact des anneaux doit être fini).</span><span class="sxs-lookup"><span data-stu-id="3771c-146">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
4.  <span data-ttu-id="3771c-147">L'intérieur du polygone doit être connecté.</span><span class="sxs-lookup"><span data-stu-id="3771c-147">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="3771c-148">L'exemple suivant montre une instance geography CurvePolygon valide.</span><span class="sxs-lookup"><span data-stu-id="3771c-148">The following example shows a valid geography CurvePolygon instance.</span></span>  
  
```  
DECLARE @g geography = 'CURVEPOLYGON((-122.3 47, 122.3 47, 125.7 49, 121 38, -122.3 47))';  
SELECT @g.STIsValid();  
```  
  
## <a name="examples"></a><span data-ttu-id="3771c-149">Exemples</span><span class="sxs-lookup"><span data-stu-id="3771c-149">Examples</span></span>  
  
### <a name="a-instantiating-a-geometry-instance-with-an-empty-curvepolygon"></a><span data-ttu-id="3771c-150">R.</span><span class="sxs-lookup"><span data-stu-id="3771c-150">A.</span></span> <span data-ttu-id="3771c-151">Instanciation d'une instance geometry avec un CurvePolygon Vide</span><span class="sxs-lookup"><span data-stu-id="3771c-151">Instantiating a Geometry Instance with an Empty CurvePolygon</span></span>  
 <span data-ttu-id="3771c-152">Cet exemple indique comment créer une instance `CurvePolygon` vide :</span><span class="sxs-lookup"><span data-stu-id="3771c-152">This example shows how to create an empty `CurvePolygon` instance:</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON EMPTY');  
```  
  
### <a name="b-declaring-and-instantiating-a-geometry-instance-with-a-curvepolygon-in-the-same-statement"></a><span data-ttu-id="3771c-153">B.</span><span class="sxs-lookup"><span data-stu-id="3771c-153">B.</span></span> <span data-ttu-id="3771c-154">Déclaration et instanciation d'une instance geometry avec un CurvePolygon dans la même instruction</span><span class="sxs-lookup"><span data-stu-id="3771c-154">Declaring and Instantiating a Geometry Instance with a CurvePolygon in the Same Statement</span></span>  
 <span data-ttu-id="3771c-155">Cet extrait de code indique comment déclarer et initialiser une instance geometry avec un `CurvePolygon` dans la même instruction :</span><span class="sxs-lookup"><span data-stu-id="3771c-155">This code snippet shows how to declare and initialize a geometry instance with a `CurvePolygon` in the same statement:</span></span>  
  
```sql  
DECLARE @g geometry = 'CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))'  
```  
  
### <a name="c-instantiating-a-geography-instance-with-a-curvepolygon"></a><span data-ttu-id="3771c-156">C.</span><span class="sxs-lookup"><span data-stu-id="3771c-156">C.</span></span> <span data-ttu-id="3771c-157">Instanciation d'une instance geography avec un CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="3771c-157">Instantiating a Geography Instance with a CurvePolygon</span></span>  
 <span data-ttu-id="3771c-158">Cet extrait de code indique comment déclarer et initialiser une instance `geography` avec un `CurvePolygon` :</span><span class="sxs-lookup"><span data-stu-id="3771c-158">This code snippet shows how to declare and initialize a `geography` instance with a `CurvePolygon`:</span></span>  
  
```sql  
DECLARE @g geography = 'CURVEPOLYGON(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';  
```  
  
### <a name="d-storing-a-curvepolygon-with-only-an-exterior-bounding-ring"></a><span data-ttu-id="3771c-159">D.</span><span class="sxs-lookup"><span data-stu-id="3771c-159">D.</span></span> <span data-ttu-id="3771c-160">Stockage d'un CurvePolygon uniquement avec un anneau englobant extérieur</span><span class="sxs-lookup"><span data-stu-id="3771c-160">Storing a CurvePolygon with Only an Exterior Bounding Ring</span></span>  
 <span data-ttu-id="3771c-161">Cet exemple indique comment stocker un cercle simple dans une instance `CurvePolygon` (seul un anneau englobant extérieur est utilisé pour définir le cercle) :</span><span class="sxs-lookup"><span data-stu-id="3771c-161">This example shows how to store a simple circle in a `CurvePolygon` instance (only an exterior bounding ring is used to define the circle):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
### <a name="e-storing-a-curvepolygon-containing-interior-rings"></a><span data-ttu-id="3771c-162">E.</span><span class="sxs-lookup"><span data-stu-id="3771c-162">E.</span></span> <span data-ttu-id="3771c-163">Stockage d'un CurvePolygon contenant des anneaux intérieurs</span><span class="sxs-lookup"><span data-stu-id="3771c-163">Storing a CurvePolygon Containing Interior Rings</span></span>  
 <span data-ttu-id="3771c-164">Cet exemple crée une bouée dans une instance `CurvePolygon` (à la fois un anneau englobant extérieur et un anneau intérieur sont utilisés pour définir la bouée) :</span><span class="sxs-lookup"><span data-stu-id="3771c-164">This example creates a donut in a `CurvePolygon` instance (both an exterior bounding ring and an interior ring is used to define the donut):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 4, 4 0, 8 4, 4 8, 0 4), CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
 <span data-ttu-id="3771c-165">Cet exemple montre à la fois une instance `CurvePolygon` valide et une instance non valide lors de l'utilisation d'anneaux intérieurs :</span><span class="sxs-lookup"><span data-stu-id="3771c-165">This example shows both a valid `CurvePolygon` instance and an invalid instance when using interior rings:</span></span>  
  
```sql  
DECLARE @g1 geometry, @g2 geometry;  
SET @g1 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (-2 2, 2 2, 2 -2, -2 -2, -2 2))');  
IF @g1.STIsValid() = 1  
  BEGIN  
     SELECT @g1.STArea();  
  END  
SET @g2 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (0 5, 5 0, 0 -5, -5 0, 0 5))');  
IF @g2.STIsValid() = 1  
  BEGIN  
     SELECT @g2.STArea();  
  END  
SELECT @g1.STIsValid() AS G1, @g2.STIsValid() AS G2;  
```  
  
 <span data-ttu-id="3771c-166">@g1 et @g2 utilisent tous les deux le même anneau englobant extérieur (un cercle avec un rayon de 5) et un carré comme anneau intérieur.</span><span class="sxs-lookup"><span data-stu-id="3771c-166">Both @g1 and @g2 use the same exterior bounding ring: a circle with a radius of 5 and they both use a square for an interior ring.</span></span>  <span data-ttu-id="3771c-167">Toutefois, l’instance @g1 est valide, mais l’instance @g2 n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="3771c-167">However, the instance @g1 is valid, but the instance @g2 is invalid.</span></span>  <span data-ttu-id="3771c-168">La raison pour laquelle @g2 n’est pas valide est que l’anneau intérieur fractionne l’espace intérieur englobé par l’anneau extérieur en quatre régions distinctes.</span><span class="sxs-lookup"><span data-stu-id="3771c-168">The reason that @g2 is invalid is that the interior ring splits the interior space bounded by the exterior ring into four separate regions.</span></span>  <span data-ttu-id="3771c-169">Le dessin suivant montre ce qui s'est produit :</span><span class="sxs-lookup"><span data-stu-id="3771c-169">The following drawing shows what occurred:</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3771c-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3771c-170">See Also</span></span>  
 <span data-ttu-id="3771c-171">[Polygon](polygon.md) </span><span class="sxs-lookup"><span data-stu-id="3771c-171">[Polygon](polygon.md) </span></span>  
 <span data-ttu-id="3771c-172">[CircularString](circularstring.md) </span><span class="sxs-lookup"><span data-stu-id="3771c-172">[CircularString](circularstring.md) </span></span>  
 <span data-ttu-id="3771c-173">[CompoundCurve](compoundcurve.md) </span><span class="sxs-lookup"><span data-stu-id="3771c-173">[CompoundCurve](compoundcurve.md) </span></span>  
 <span data-ttu-id="3771c-174">[Référence de méthodes de type de données geometry](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3771c-174">[geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span></span>  
 <span data-ttu-id="3771c-175">[Référence de méthodes de type de données geography](/sql/t-sql/spatial-geography/spatial-types-geography) </span><span class="sxs-lookup"><span data-stu-id="3771c-175">[geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) </span></span>  
 [<span data-ttu-id="3771c-176">Présentation des types de données spatiales</span><span class="sxs-lookup"><span data-stu-id="3771c-176">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
