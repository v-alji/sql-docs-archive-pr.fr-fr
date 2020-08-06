---
title: LineString | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- LineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: e50d0b86-8b31-4285-be71-ad05c7712cbd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 5a0f77959cfe4492eca6c38951ba2868452d41ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613928"
---
# <a name="linestring"></a><span data-ttu-id="cbcd9-102">LineString</span><span class="sxs-lookup"><span data-stu-id="cbcd9-102">LineString</span></span>
  <span data-ttu-id="cbcd9-103">Un `LineString` est un objet unidimensionnel qui représente une séquence de points et les segments de ligne qui les connectent.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-103">A `LineString` is a one-dimensional object representing a sequence of points and the line segments connecting them.</span></span>

## <a name="linestring-instances"></a><span data-ttu-id="cbcd9-104">Instances LINESTRING</span><span class="sxs-lookup"><span data-stu-id="cbcd9-104">LineString Instances</span></span>
 <span data-ttu-id="cbcd9-105">L'illustration suivante montre des exemples d'instances `LineString`.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-105">The illustration below shows examples of `LineString` instances.</span></span>

 <span data-ttu-id="cbcd9-106">![Exemples d’instances LineString géométriques](../../database-engine/media/linestring.gif "Exemples d’instances LineString géométriques")</span><span class="sxs-lookup"><span data-stu-id="cbcd9-106">![Examples of geometry LineString instances](../../database-engine/media/linestring.gif "Examples of geometry LineString instances")</span></span>

 <span data-ttu-id="cbcd9-107">Comme indiqué par l'illustration :</span><span class="sxs-lookup"><span data-stu-id="cbcd9-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="cbcd9-108">La Figure 1 est une instance `LineString` simple et non fermée.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-108">Figure 1 is a simple, nonclosed `LineString` instance.</span></span>

-   <span data-ttu-id="cbcd9-109">La Figure 2 est une instance `LineString` non simple et non fermée.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-109">Figure 2 is a nonsimple, nonclosed `LineString` instance.</span></span>

-   <span data-ttu-id="cbcd9-110">La Figure 3 est une instance `LineString` fermée et simple ; il s'agit par conséquent d'un anneau.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-110">Figure 3 is a closed, simple `LineString` instance, and therefore is a ring.</span></span>

-   <span data-ttu-id="cbcd9-111">La Figure 4 est une instance `LineString` fermée et non simple ; il ne s'agit par conséquent pas d'un anneau.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-111">Figure 4 is a closed, nonsimple `LineString` instance, and therefore is not a ring.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="cbcd9-112">Instances acceptées</span><span class="sxs-lookup"><span data-stu-id="cbcd9-112">Accepted Instances</span></span>
 <span data-ttu-id="cbcd9-113">Les instances `LineString` acceptées peuvent être introduites dans une variable geometry, mais elles peuvent ne pas être des instances `LineString` valides.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-113">Accepted `LineString` instances can be input into a geometry variable, but they may not be valid `LineString` instances.</span></span> <span data-ttu-id="cbcd9-114">Pour qu'une instance `LineString` soit acceptée, elle doit répondre aux critères suivants.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-114">The following criteria must be met for a `LineString` instance to be accepted.</span></span> <span data-ttu-id="cbcd9-115">L'instance doit être formée d'au moins deux points ou être vide.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-115">The instance must be formed of at least two points or it must be empty.</span></span> <span data-ttu-id="cbcd9-116">Les instances LineString suivantes sont acceptées.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-116">The following LineString instances are accepted.</span></span>

```
DECLARE @g1 geometry = 'LINESTRING EMPTY';
DECLARE @g2 geometry = 'LINESTRING(1 1,2 3,4 8, -6 3)';
DECLARE @g3 geometry = 'LINESTRING(1 1, 1 1)';
```

 <span data-ttu-id="cbcd9-117">`@g3` montre qu'une instance `LineString` peut être acceptée, mais non valide.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-117">`@g3` shows that a `LineString` instance can be accepted, but not valid.</span></span>

 <span data-ttu-id="cbcd9-118">L'instance `LineString` suivante n'est pas acceptée.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-118">The following `LineString` instance is not accepted.</span></span> <span data-ttu-id="cbcd9-119">Elle lèvera une `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-119">It will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'LINESTRING(1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="cbcd9-120">Instances valides</span><span class="sxs-lookup"><span data-stu-id="cbcd9-120">Valid Instances</span></span>
 <span data-ttu-id="cbcd9-121">Pour qu'une instance `LineString` soit valide, elle doit répondre aux critères suivants :</span><span class="sxs-lookup"><span data-stu-id="cbcd9-121">For a `LineString` instance to be valid it must meet the following criteria.</span></span>

1.  <span data-ttu-id="cbcd9-122">L'instance `LineString` doit être acceptée.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-122">The `LineString` instance must be accepted.</span></span>

2.  <span data-ttu-id="cbcd9-123">Si une instance `LineString` n'est pas vide, elle doit contenir au moins deux points distincts.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-123">If a `LineString` instance is not empty then it must contain at least two distinct points.</span></span>

3.  <span data-ttu-id="cbcd9-124">L'instance `LineString` ne peut pas se chevaucher sur un intervalle de plusieurs points consécutifs.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-124">The `LineString` instance cannot overlap itself over an interval of two or more consecutive points.</span></span>

 <span data-ttu-id="cbcd9-125">Les instances `LineString` suivantes sont valides.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-125">The following `LineString` instances are valid.</span></span>

```
DECLARE @g1 geometry= 'LINESTRING EMPTY';
DECLARE @g2 geometry= 'LINESTRING(1 1, 3 3)';
DECLARE @g3 geometry= 'LINESTRING(1 1, 3 3, 2 4, 2 0)';
DECLARE @g4 geometry= 'LINESTRING(1 1, 3 3, 2 4, 2 0, 1 1)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();

```

 <span data-ttu-id="cbcd9-126">Les instances `LineString` suivantes ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-126">The following `LineString` instances are not valid.</span></span>

```
DECLARE @g1 geometry = 'LINESTRING(1 4, 3 4, 2 4, 2 0)';
DECLARE @g2 geometry = 'LINESTRING(1 1, 1 1)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

> [!WARNING]
>  <span data-ttu-id="cbcd9-127">La détection de chevauchements `LineString` se base sur des calculs en virgule flottante, qui ne sont pas exacts.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-127">The detection of `LineString` overlaps is based on floating-point calculations, which are not exact.</span></span>

## <a name="examples"></a><span data-ttu-id="cbcd9-128">Exemples</span><span class="sxs-lookup"><span data-stu-id="cbcd9-128">Examples</span></span>
 <span data-ttu-id="cbcd9-129">L’exemple suivant montre comment créer une instance `geometry``LineString` avec trois points et un SRID égal à 0 :</span><span class="sxs-lookup"><span data-stu-id="cbcd9-129">The following example shows how to create a `geometry``LineString` instance with three points and an SRID of 0:</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(1 1, 2 4, 3 9)', 0);
```

 <span data-ttu-id="cbcd9-130">Chaque point dans l'instance `LineString` peut contenir des valeurs Z (élévation) et M (mesure).</span><span class="sxs-lookup"><span data-stu-id="cbcd9-130">Each point in the `LineString` instance may contain Z (elevation) and M (measure) values.</span></span> <span data-ttu-id="cbcd9-131">Cet exemple ajoute des valeurs M à l'instance `LineString` créée dans l'exemple ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-131">This example adds M values to the `LineString` instance created in the example above.</span></span> <span data-ttu-id="cbcd9-132">M et Z peuvent être des valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-132">M and Z can be null values.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(1 1 NULL 0, 2 4 NULL 12.3, 3 9 NULL 24.5)', 0);
```

 <span data-ttu-id="cbcd9-133">L'exemple suivant montre comment créer une instance `geometry LineString` avec deux points identiques.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-133">The following example shows how to create a `geometry LineString` instance with two points that are the same.</span></span> <span data-ttu-id="cbcd9-134">Un appel à `IsValid` indique que l'instance `LineString` n'est pas valide et un appel à `MakeValid` convertira l'instance `LineString` en un `Point`.</span><span class="sxs-lookup"><span data-stu-id="cbcd9-134">A call to `IsValid` indicates that the `LineString` instance is not valid and a call to `MakeValid` will convert the `LineString` instance into a `Point`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::STGeomFromText('LINESTRING(1 3, 1 3)',0);
IF @g.STIsValid() = 1
  BEGIN
     SELECT @g.ToString() + ' is a valid LineString.';  
  END
ELSE
  BEGIN
     SELECT @g.ToString() + ' is not a valid LineString.';
     SET @g = @g.MakeValid();
     SELECT @g.ToString() + ' is a valid Point.';  
  END

```

 <span data-ttu-id="cbcd9-135">L'extrait de code ci-dessus retournera les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="cbcd9-135">The above code snippet will return the following:</span></span>

```
LINESTRING(1 3, 1 3) is not a valid LineString
POINT(1 3) is a valid Point.
```

## <a name="see-also"></a><span data-ttu-id="cbcd9-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbcd9-136">See Also</span></span>
 <span data-ttu-id="cbcd9-137">[STLength &#40;Geometry type de données&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndPoint &#40;geometry type de données&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) Geometry type de données&#41;[STNumPoints &#40;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) type de données geometry&#41;STIsRing &#40;type de données [Geometry](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [&#41;STIsClosed](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) &#40;type de données geometry&#41;[STPointOnSurface &#40;type de données geometry](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)&#41;[données spatiales](../spatial/spatial-data-sql-server.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cbcd9-137">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


