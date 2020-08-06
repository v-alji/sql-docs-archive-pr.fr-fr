---
title: Présentation des types de données spatiales | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], understanding
- geography data type [SQL Server], spatial data
- planar spatial data [SQL Server], geometry data type
- spatial data types [SQL Server]
ms.assetid: 1615db50-69de-4778-8be6-4e058c00ccd4
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c0548d974e83bfe2b1e103d4458b17078fba8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703980"
---
# <a name="spatial-data-types-overview"></a><span data-ttu-id="7fe33-102">Présentation des types de données spatiales</span><span class="sxs-lookup"><span data-stu-id="7fe33-102">Spatial Data Types Overview</span></span>
  <span data-ttu-id="7fe33-103">Il existe deux types de données spatiales.</span><span class="sxs-lookup"><span data-stu-id="7fe33-103">There are two types of spatial data.</span></span> <span data-ttu-id="7fe33-104">Le type de données `geometry` prend en charge les données planaires, ou euclidiennes (monde en deux dimensions).</span><span class="sxs-lookup"><span data-stu-id="7fe33-104">The `geometry` data type supports planar, or Euclidean (flat-earth), data.</span></span> <span data-ttu-id="7fe33-105">Le type de données `geometry` se conforme à la fois à la spécification Open Geospatial Consortium (OGC) Simple Features for SQL version 1.1.0. et à la norme SQL MM (norme ISO).</span><span class="sxs-lookup"><span data-stu-id="7fe33-105">The `geometry` data type both conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0 and is compliant with SQL MM (ISO standard).</span></span>

 <span data-ttu-id="7fe33-106">De plus, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] prend en charge le type de données `geography`, qui stocke des données ellipsoïdes (monde sphérique), telles que des coordonnées GPS de latitude et de longitude.</span><span class="sxs-lookup"><span data-stu-id="7fe33-106">In addition, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supports the `geography` data type, which stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="7fe33-107">Pour obtenir une description détaillée et des exemples des nouvelles fonctionnalités spatiales dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], notamment les optimisations des types de données spatiales, téléchargez le livre blanc [New Spatial Features in SQL Server Code-Named "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407)(Nouvelles fonctions spatiales dans SQL Server nom de code « Denali »).</span><span class="sxs-lookup"><span data-stu-id="7fe33-107">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including enhancements to the spatial data types, download the white paper, [New Spatial Features in SQL Server Code-Named "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

##  <a name="spatial-data-objects"></a><a name="objects"></a> <span data-ttu-id="7fe33-108">Objets de données spatiales</span><span class="sxs-lookup"><span data-stu-id="7fe33-108">Spatial Data Objects</span></span>
 <span data-ttu-id="7fe33-109">Les types de données `geometry` et `geography` prennent en charge seize objets de données spatiales, ou types d'instances.</span><span class="sxs-lookup"><span data-stu-id="7fe33-109">The `geometry` and `geography` data types support sixteen spatial data objects, or instance types.</span></span> <span data-ttu-id="7fe33-110">Toutefois, seuls onze de ces types d’instances sont *instanciables*; vous pouvez créer et utiliser ces instances (ou les instancier) dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="7fe33-110">However, only eleven of these instance types are *instantiable*; you can create and work with these instances (or instantiate them) in a database.</span></span> <span data-ttu-id="7fe33-111">Ces instances dérivent certaines propriétés de leurs types de données parents qui les distinguent comme `Points` , **LineStrings, CircularStrings**,, `CompoundCurves` `Polygons` , `CurvePolygons` ou comme `geometry` instances multiples ou `geography` dans un `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="7fe33-111">These instances derive certain properties from their parent data types that distinguish them as `Points`, **LineStrings, CircularStrings**, `CompoundCurves`, `Polygons`, `CurvePolygons` or as multiple `geometry` or `geography` instances in a `GeometryCollection`.</span></span> <span data-ttu-id="7fe33-112">Le type `Geography` possède un type d'instance supplémentaire, `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="7fe33-112">`Geography` type has an additional instance type, `FullGlobe`.</span></span>

 <span data-ttu-id="7fe33-113">La figure ci-dessous représente la hiérarchie `geometry` sur laquelle les types de données `geometry` et `geography` sont basés.</span><span class="sxs-lookup"><span data-stu-id="7fe33-113">The figure below depicts the `geometry` hierarchy upon which the `geometry` and `geography` data types are based.</span></span> <span data-ttu-id="7fe33-114">Les types instanciables de `geometry` et `geography` sont indiqués en bleu.</span><span class="sxs-lookup"><span data-stu-id="7fe33-114">The instantiable types of `geometry` and `geography` are indicated in blue.</span></span>

 <span data-ttu-id="7fe33-115">![Hiérarchie du type geometry](../../database-engine/media/geom-hierarchy.gif "Hiérarchie du type geometry")</span><span class="sxs-lookup"><span data-stu-id="7fe33-115">![Hierarchy of the geometry type](../../database-engine/media/geom-hierarchy.gif "Hierarchy of the geometry type")</span></span>

 <span data-ttu-id="7fe33-116">Comme l’indique la figure, les dix types instanciables `geometry` des `geography` types de données et sont `Point` , `MultiPoint` , `LineString` , `CircularString` , `MultiLineString` , `CompoundCurve` , `Polygon` ,, `CurvePolygon` `MultiPolygon` et `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="7fe33-116">As the figure indicates, the ten instantiable types of the `geometry` and `geography` data types are `Point`, `MultiPoint`, `LineString`, `CircularString`, `MultiLineString`, `CompoundCurve`, `Polygon`, `CurvePolygon`, `MultiPolygon`, and `GeometryCollection`.</span></span> <span data-ttu-id="7fe33-117">Il existe un type instanciable supplémentaire pour le type de données geography : `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="7fe33-117">There is one additional instantiable type for the geography data type: `FullGlobe`.</span></span> <span data-ttu-id="7fe33-118">Les `geometry` `geography` types et peuvent reconnaître une instance spécifique tant qu’il s’agit d’une instance bien formée, même si l’instance n’est pas définie explicitement.</span><span class="sxs-lookup"><span data-stu-id="7fe33-118">The `geometry` and `geography` types can recognize a specific instance as long as it is a well-formed instance, even if the instance is not defined explicitly.</span></span> <span data-ttu-id="7fe33-119">Par exemple, si vous définissez une `Point` instance explicitement à l’aide de la méthode STPointFromText (), et que vous `geometry` `geography` Identifiez l’instance comme un `Point` , tant que l’entrée de la méthode est correctement formée.</span><span class="sxs-lookup"><span data-stu-id="7fe33-119">For example, if you define a `Point` instance explicitly using the STPointFromText() method, `geometry` and `geography` recognize the instance as a `Point`, as long as the method input is well-formed.</span></span> <span data-ttu-id="7fe33-120">Si vous définissez la même instance à l'aide de la méthode `STGeomFromText()`, les types de données `geometry` et `geography` reconnaissent l'instance comme un `Point`.</span><span class="sxs-lookup"><span data-stu-id="7fe33-120">If you define the same instance using the `STGeomFromText()` method, both the `geometry` and `geography` data types recognize the instance as a `Point`.</span></span>

 <span data-ttu-id="7fe33-121">Les sous-types des types geometry et geography sont divisés en types simples et de collection.</span><span class="sxs-lookup"><span data-stu-id="7fe33-121">The subtypes for geometry and geography types are divided into simple and collection types.</span></span>  <span data-ttu-id="7fe33-122">Certaines méthodes, telles que `STNumCurves()` , fonctionnent uniquement avec les types simples.</span><span class="sxs-lookup"><span data-stu-id="7fe33-122">Some methods like `STNumCurves()` work only with simple types.</span></span>

 <span data-ttu-id="7fe33-123">Exemples de types simples :</span><span class="sxs-lookup"><span data-stu-id="7fe33-123">Simple types include:</span></span>

-   [<span data-ttu-id="7fe33-124">Point</span><span class="sxs-lookup"><span data-stu-id="7fe33-124">Point</span></span>](../spatial/point.md)

-   [<span data-ttu-id="7fe33-125">LineString</span><span class="sxs-lookup"><span data-stu-id="7fe33-125">LineString</span></span>](../spatial/linestring.md)

-   [<span data-ttu-id="7fe33-126">CircularString</span><span class="sxs-lookup"><span data-stu-id="7fe33-126">CircularString</span></span>](../spatial/circularstring.md)

-   [<span data-ttu-id="7fe33-127">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="7fe33-127">CompoundCurve</span></span>](../spatial/compoundcurve.md)

-   [<span data-ttu-id="7fe33-128">Polygon</span><span class="sxs-lookup"><span data-stu-id="7fe33-128">Polygon</span></span>](../spatial/polygon.md)

-   [<span data-ttu-id="7fe33-129">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="7fe33-129">CurvePolygon</span></span>](../spatial/curvepolygon.md)

 <span data-ttu-id="7fe33-130">Exemples de types de collection :</span><span class="sxs-lookup"><span data-stu-id="7fe33-130">Collection types include:</span></span>

-   [<span data-ttu-id="7fe33-131">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="7fe33-131">MultiPoint</span></span>](../spatial/multipoint.md)

-   [<span data-ttu-id="7fe33-132">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="7fe33-132">MultiLineString</span></span>](../spatial/multilinestring.md)

-   [<span data-ttu-id="7fe33-133">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="7fe33-133">MultiPolygon</span></span>](../spatial/multipolygon.md)

-   [<span data-ttu-id="7fe33-134">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="7fe33-134">GeometryCollection</span></span>](../spatial/geometrycollection.md)


##  <a name="differences-between-the-geometry-and-geography-data-types"></a><a name="differences"></a> <span data-ttu-id="7fe33-135">Différences entre les types de données geometry et geography</span><span class="sxs-lookup"><span data-stu-id="7fe33-135">Differences Between the geometry and geography Data Types</span></span>
 <span data-ttu-id="7fe33-136">Les deux types de données spatiales se comportent souvent à peu près de la même façon, mais il existe des différences clés dans la façon dont les données sont stockées et manipulées.</span><span class="sxs-lookup"><span data-stu-id="7fe33-136">The two types of spatial data often behave quite similarly, but there are some key differences in how the data is stored and manipulated.</span></span>

### <a name="how-connecting-edges-are-defined"></a><span data-ttu-id="7fe33-137">Mode de définition des arêtes de connexion</span><span class="sxs-lookup"><span data-stu-id="7fe33-137">How connecting edges are defined</span></span>
 <span data-ttu-id="7fe33-138">Les données de définition concernant les types `LineString` et `Polygon` sont uniquement des sommets.</span><span class="sxs-lookup"><span data-stu-id="7fe33-138">The defining data for `LineString` and `Polygon` types are vertices only.</span></span>  <span data-ttu-id="7fe33-139">L'arête reliant deux sommets dans un type geometry forme une ligne droite.</span><span class="sxs-lookup"><span data-stu-id="7fe33-139">The connecting edge between two vertices in a geometry type is a straight line.</span></span>  <span data-ttu-id="7fe33-140">Toutefois, l'arête reliant deux sommets dans un type geography est un grand arc elliptique court entre les deux sommets.</span><span class="sxs-lookup"><span data-stu-id="7fe33-140">However, the connecting edge between two vertices in a geography type is a short great elliptic arc between the two vertices.</span></span>  <span data-ttu-id="7fe33-141">Une grande ellipse correspond à l'intersection de l'ellipsoïde avec un plan passant par son centre tandis qu'un grand arc elliptique est un segment d'arc sur la grande ellipse.</span><span class="sxs-lookup"><span data-stu-id="7fe33-141">A great ellipse is the intersection of the ellipsoid with a plane through its center and a great elliptic arc is an arc segment on the great ellipse.</span></span>

### <a name="how-circular-arc-segments-are-defined"></a><span data-ttu-id="7fe33-142">Mode de définition des segments d'arc de cercle</span><span class="sxs-lookup"><span data-stu-id="7fe33-142">How circular arc segments are defined</span></span>
 <span data-ttu-id="7fe33-143">Les segments d'arc de cercle pour les types geography sont définis sur le plan des coordonnées cartésiennes XY (les valeurs Z sont ignorées).</span><span class="sxs-lookup"><span data-stu-id="7fe33-143">Circular arc segments for geometry types are defined on the XY Cartesian coordinate plane (Z values are ignored).</span></span> <span data-ttu-id="7fe33-144">Les segments d'arc de cercle pour les types geography sont définis par des segments de courbe sur une sphère de référence.</span><span class="sxs-lookup"><span data-stu-id="7fe33-144">Circular arc segments for geography types are defined by curve segments on a reference sphere.</span></span> <span data-ttu-id="7fe33-145">Toute parallèle sur la sphère de référence peut être définie par deux arcs de cercle complémentaires où les points des deux arcs ont un angle de latitude constant.</span><span class="sxs-lookup"><span data-stu-id="7fe33-145">Any parallel on the reference sphere can be defined by two complementary circular arcs where the points for both arcs have a constant latitude angle.</span></span>

### <a name="measurements-in-spatial-data-types"></a><span data-ttu-id="7fe33-146">Mesures dans les types de données spatiales</span><span class="sxs-lookup"><span data-stu-id="7fe33-146">Measurements in spatial data types</span></span>
 <span data-ttu-id="7fe33-147">Dans le système planaire, ou monde en deux dimensions, les mesures de distances et de surfaces sont données dans la même unité de mesure que les coordonnées.</span><span class="sxs-lookup"><span data-stu-id="7fe33-147">In the planar, or flat-earth, system, measurements of distances and areas are given in the same unit of measurement as coordinates.</span></span> <span data-ttu-id="7fe33-148">Avec le type de données `geometry`, la distance entre (2, 2) et (5, 6) est 5 unités, quelles que soient les unités utilisées.</span><span class="sxs-lookup"><span data-stu-id="7fe33-148">Using the `geometry` data type, the distance between (2, 2) and (5, 6) is 5 units, regardless of the units used.</span></span>

 <span data-ttu-id="7fe33-149">Dans le système ellipsoïdal, ou monde sphérique, les coordonnées sont données en degrés de latitude et de longitude.</span><span class="sxs-lookup"><span data-stu-id="7fe33-149">In the ellipsoidal, or round-earth system, coordinates are given in degrees of latitude and longitude.</span></span> <span data-ttu-id="7fe33-150">Toutefois, les longueurs et surfaces sont généralement mesurées en mètres et en mètres carrés, bien que la mesure puisse dépendre de l'identificateur de référence spatiale (SRID) de l'instance `geography`.</span><span class="sxs-lookup"><span data-stu-id="7fe33-150">However, lengths and areas are usually measured in meters and square meters, though the measurement may depend on the spatial reference identifier (SRID) of the `geography` instance.</span></span> <span data-ttu-id="7fe33-151">L'unité de mesure la plus courante pour le type de données `geography` est le mètre.</span><span class="sxs-lookup"><span data-stu-id="7fe33-151">The most common unit of measurement for the `geography` data type is meters.</span></span>

### <a name="orientation-of-spatial-data"></a><span data-ttu-id="7fe33-152">Orientation des données spatiales</span><span class="sxs-lookup"><span data-stu-id="7fe33-152">Orientation of spatial data</span></span>
 <span data-ttu-id="7fe33-153">Dans le système planaire, l'orientation d'anneau d'un polygone n'est pas un facteur important.</span><span class="sxs-lookup"><span data-stu-id="7fe33-153">In the planar system, the ring orientation of a polygon is not an important factor.</span></span> <span data-ttu-id="7fe33-154">Par exemple, un polygone décrit par ((0, 0), (10, 0), (0, 20), (0, 0)) est le même qu'un polygone décrit par ((0, 0), (0, 20), (10, 0), (0, 0)).</span><span class="sxs-lookup"><span data-stu-id="7fe33-154">For example, a polygon described by ((0, 0), (10, 0), (0, 20), (0, 0)) is the same as a polygon described by ((0, 0), (0, 20), (10, 0), (0, 0)).</span></span> <span data-ttu-id="7fe33-155">La spécification OGC Simple Features for SQL ne stipule pas d'ordonnancement d'anneau et [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] n'applique pas d'ordonnancement d'anneau.</span><span class="sxs-lookup"><span data-stu-id="7fe33-155">The OGC Simple Features for SQL Specification does not dictate a ring ordering, and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not enforce ring ordering.</span></span>

 <span data-ttu-id="7fe33-156">Dans un système ellipsoïdal, un polygone n'a aucune signification, ou est ambigu, sans orientation.</span><span class="sxs-lookup"><span data-stu-id="7fe33-156">In an ellipsoidal system, a polygon has no meaning, or is ambiguous, without an orientation.</span></span> <span data-ttu-id="7fe33-157">Par exemple, un anneau autour de l'équateur décrit-il l'hémisphère Nord ou Sud ?</span><span class="sxs-lookup"><span data-stu-id="7fe33-157">For example, does a ring around the equator describe the northern or southern hemisphere?</span></span> <span data-ttu-id="7fe33-158">Si nous utilisons le type de données `geography` pour stocker l'instance spatiale, nous devons spécifier l'orientation de l'anneau et décrire précisément l'emplacement de l'instance.</span><span class="sxs-lookup"><span data-stu-id="7fe33-158">If we use the `geography` data type to store the spatial instance, we must specify the orientation of the ring and accurately describe the location of the instance.</span></span> <span data-ttu-id="7fe33-159">L'intérieur du polygone dans un système ellipsoïdal est défini par la règle gauche.</span><span class="sxs-lookup"><span data-stu-id="7fe33-159">The interior of the polygon in an ellipsoidal system is defined by the left-hand rule.</span></span>

 <span data-ttu-id="7fe33-160">Lorsque le niveau de compatibilité est 100 ou inférieur dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] , le `geography` type de données présente les restrictions suivantes :</span><span class="sxs-lookup"><span data-stu-id="7fe33-160">When the compatibility level is 100 or below in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] then the `geography` data type has the following restrictions:</span></span>

-   <span data-ttu-id="7fe33-161">Chaque instance `geography` doit être contenue à l'intérieur d'un seul hémisphère.</span><span class="sxs-lookup"><span data-stu-id="7fe33-161">Each `geography` instance must fit inside a single hemisphere.</span></span> <span data-ttu-id="7fe33-162">Aucun objet spatial plus grand qu'un hémisphère ne peut être stocké.</span><span class="sxs-lookup"><span data-stu-id="7fe33-162">No spatial objects larger than a hemisphere can be stored.</span></span>

-   <span data-ttu-id="7fe33-163">Toute instance `geography` d'une représentation WKB (Well-Known Binary) ou WKT (Well-Known Text) OGC (Open Geospatial Consortium) qui produit un objet plus grand qu'un hémisphère lève une `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="7fe33-163">Any `geography` instance from an Open Geospatial Consortium (OGC) Well-Known Text (WKT) or Well-Known Binary (WKB) representation that produces an object larger than a hemisphere throws an `ArgumentException`.</span></span>

-   <span data-ttu-id="7fe33-164">Les `geography` méthodes de type de données qui requièrent l’entrée de deux `geography` instances, telles que STIntersection (), STUnion (), STDifference () et STSymDifference (), retournent Null si les résultats des méthodes ne s’ajustent pas à l’intérieur d’un seul hémisphère.</span><span class="sxs-lookup"><span data-stu-id="7fe33-164">The `geography` data type methods that require the input of two `geography` instances, such as STIntersection(), STUnion(), STDifference(), and STSymDifference(), will return null if the results from the methods do not fit inside a single hemisphere.</span></span> <span data-ttu-id="7fe33-165">STBuffer() retourne également null si la sortie dépasse un seul hémisphère.</span><span class="sxs-lookup"><span data-stu-id="7fe33-165">STBuffer() will also return null if the output exceeds a single hemisphere.</span></span>

 <span data-ttu-id="7fe33-166">Dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], `FullGlobe` est un type spécial de polygone qui couvre le globe entier.</span><span class="sxs-lookup"><span data-stu-id="7fe33-166">In [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], `FullGlobe` is a special type of Polygon that covers the entire globe.</span></span> <span data-ttu-id="7fe33-167">`FullGlobe` possède une zone, mais aucune bordure ni sommet.</span><span class="sxs-lookup"><span data-stu-id="7fe33-167">`FullGlobe` has an area, but no borders or vertices.</span></span>

### <a name="outer-and-inner-rings-not-important-in-geography-data-type"></a><span data-ttu-id="7fe33-168">Les anneaux internes et externes ne sont pas importants dans le type de données geography</span><span class="sxs-lookup"><span data-stu-id="7fe33-168">Outer and inner rings not important in geography data type</span></span>
 <span data-ttu-id="7fe33-169">La spécification OGC simple Features for SQL traite des anneaux externes et internes, mais cette distinction n’a que peu de sens pour le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` type de données ; tout anneau d’un polygone peut être considéré comme l’anneau externe.</span><span class="sxs-lookup"><span data-stu-id="7fe33-169">The OGC Simple Features for SQL Specification discusses outer rings and inner rings, but this distinction makes little sense for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` data type; any ring of a polygon can be taken to be the outer ring.</span></span>

 <span data-ttu-id="7fe33-170">Pour plus d'informations sur les spécifications OGC, reportez-vous aux sites Web suivants :</span><span class="sxs-lookup"><span data-stu-id="7fe33-170">For more information on OGC specifications, see the following:</span></span>

-   [<span data-ttu-id="7fe33-171">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span><span class="sxs-lookup"><span data-stu-id="7fe33-171">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93627)

-   [<span data-ttu-id="7fe33-172">OGC Specifications, Simple Feature Access Part 2 - SQL Options</span><span class="sxs-lookup"><span data-stu-id="7fe33-172">OGC Specifications, Simple Feature Access Part 2 - SQL Options</span></span>](https://go.microsoft.com/fwlink/?LinkId=93628)


##  <a name="circular-arc-segments"></a><a name="circular"></a> <span data-ttu-id="7fe33-173">Segments d'arc de cercle</span><span class="sxs-lookup"><span data-stu-id="7fe33-173">Circular Arc Segments</span></span>
 <span data-ttu-id="7fe33-174">Trois types instanciables acceptent des segments d'arc de cercle : `CircularString`, `CompoundCurve` et `CurvePolygon`.</span><span class="sxs-lookup"><span data-stu-id="7fe33-174">Three instantiable types can take circular arc segments: `CircularString`, `CompoundCurve`, and `CurvePolygon`.</span></span>  <span data-ttu-id="7fe33-175">Un segment d'arc de cercle est défini par trois points dans un plan à deux dimensions ; le troisième point doit être différent du premier point.</span><span class="sxs-lookup"><span data-stu-id="7fe33-175">A circular arc segment is defined by three points in a two dimensional plane and the third point cannot be the same as the first point.</span></span>

 <span data-ttu-id="7fe33-176">Les figures A et B affichent des segments d'arc de cercle types.</span><span class="sxs-lookup"><span data-stu-id="7fe33-176">Figures A and B show typical circular arc segments.</span></span> <span data-ttu-id="7fe33-177">Remarquez comment chacun des trois points se situe sur le périmètre d'un cercle.</span><span class="sxs-lookup"><span data-stu-id="7fe33-177">Note how each of the three points lie on the perimeter of a circle.</span></span>

 <span data-ttu-id="7fe33-178">Les figures C et D montrent comment un segment de ligne peut être défini comme un segment d'arc de cercle.</span><span class="sxs-lookup"><span data-stu-id="7fe33-178">Figures C and D show how a line segment can be defined as a circular arc segment.</span></span>  <span data-ttu-id="7fe33-179">Notez que trois points sont toujours nécessaires pour définir le segment d'arc de cercle contrairement à un segment de ligne ordinaire qui peut être défini par deux points seulement.</span><span class="sxs-lookup"><span data-stu-id="7fe33-179">Note that three points are still needed to define the circular arc segment unlike a regular line segment which can be defined by just two points.</span></span>

 <span data-ttu-id="7fe33-180">Les méthodes qui fonctionnent sur les types de segment d'arc de cercle utilisent des segments de ligne droite pour se rapprocher de l'arc de cercle. Le nombre de segments de ligne utilisé pour se rapprocher de l'arc dépend de la longueur et de la courbure de l'arc. Les valeurs Z peuvent être stockées pour chacun des types de segment d'arc de cercle ; toutefois, les méthodes n'utilisent pas les valeurs Z dans leurs calculs.</span><span class="sxs-lookup"><span data-stu-id="7fe33-180">Methods operating on circular arc segment types use straight line segments to approximate the circular arc. The number of line segments used to approximate the arc will depend on the length and curvature of the arc. Z values can be stored for each of the circular arc segment types; however, methods will not use the Z values in their calculations.</span></span>

> [!NOTE]
>  <span data-ttu-id="7fe33-181">Si des valeurs Z sont fournies pour les segments d'arc de cercle, elles doivent être identiques pour tous les points dans le segment d'arc de cercle pour que ce dernier soit accepté comme entrée.</span><span class="sxs-lookup"><span data-stu-id="7fe33-181">If Z values are given for circular arc segments then they must be the same for all points in the circular arc segment for it to be accepted for input.</span></span> <span data-ttu-id="7fe33-182">Par exemple, `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` est autorisé, contrairement à `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` .</span><span class="sxs-lookup"><span data-stu-id="7fe33-182">For example: `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` is accepted, but `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` is not accepted.</span></span>

### <a name="linestring-and-circularstring-comparison"></a><span data-ttu-id="7fe33-183">Comparaison de LineString et de CircularString</span><span class="sxs-lookup"><span data-stu-id="7fe33-183">LineString and CircularString comparison</span></span>
 <span data-ttu-id="7fe33-184">Le diagramme suivant montre des triangles isocèles identiques (le triangle A utilise des segments de ligne pour définir le triangle, tandis que le triangle B utilise des segments d'arc de cercle) :</span><span class="sxs-lookup"><span data-stu-id="7fe33-184">The following diagram shows identical isosceles triangles (triangle A uses line segments to define the triangle and triangle B uses circular arc segments to defined the triangle):</span></span>

 ![](../../database-engine/media/7e382f76-59da-4b62-80dc-caf93e637c14.png "7e382f76-59da-4b62-80dc-caf93e637c14")

 <span data-ttu-id="7fe33-185">Cet exemple indique comment stocker les triangles isocèles ci-dessus à l'aide d'une instance `LineString` et d'une instance `CircularString` :</span><span class="sxs-lookup"><span data-stu-id="7fe33-185">This example shows how to store the above isosceles triangles using both a `LineString` instance and `CircularString` instance:</span></span>

```sql
DECLARE @g1 geometry;
DECLARE @g2 geometry;
SET @g1 = geometry::STGeomFromText('LINESTRING(1 1, 5 1, 3 5, 1 1)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(1 1, 3 1, 5 1, 4 3, 3 5, 2 3, 1 1)', 0);
IF @g1.STIsValid() = 1 AND @g2.STIsValid() = 1
  BEGIN
      SELECT @g1.ToString(), @g2.ToString()
      SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length]
  END
```

 <span data-ttu-id="7fe33-186">Remarquez qu'une instance `CircularString` requiert sept points pour définir le triangle, alors qu'une instance `LineString` n'en requiert que quatre.</span><span class="sxs-lookup"><span data-stu-id="7fe33-186">Notice that a `CircularString` instance requires seven points to define the triangle, but a `LineString` instance requires only four points to define the triangle.</span></span> <span data-ttu-id="7fe33-187">La raison est qu'une instance `CircularString` stocke des segments d'arc de cercle et non des segments de ligne.</span><span class="sxs-lookup"><span data-stu-id="7fe33-187">The reason for this is that a `CircularString` instance stores circular arc segments and not line segments.</span></span> <span data-ttu-id="7fe33-188">Par conséquent, les côtés du triangle stockés dans l'instance `CircularString` sont ABC, CDE et EFA, alors que les côtés du triangle stockés dans l'instance `LineString` sont AC, CE et EA.</span><span class="sxs-lookup"><span data-stu-id="7fe33-188">So the sides of the triangle stored in the `CircularString` instance are ABC, CDE, and EFA whereas the sides of the triangle stored in the `LineString` instance are AC, CE, and EA.</span></span>

 <span data-ttu-id="7fe33-189">Prenez l'exemple de l'extrait de code suivant :</span><span class="sxs-lookup"><span data-stu-id="7fe33-189">Consider the following code snippet:</span></span>

```sql
SET @g1 = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 4 0)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(0 0, 2 2, 4 0)', 0);
SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length];
```

 <span data-ttu-id="7fe33-190">Cet extrait de code produira les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="7fe33-190">This snippet will produce the following results:</span></span>

```
LS LengthCS Length
5.65685...6.28318...
```

 <span data-ttu-id="7fe33-191">L’illustration suivante montre le mode de stockage de chaque type (la ligne rouge affiche `LineString``@g1` , la ligne bleue affiche `CircularString``@g2` ) :</span><span class="sxs-lookup"><span data-stu-id="7fe33-191">The following illustration shows how each type is stored (red line shows `LineString``@g1`, blue line shows `CircularString``@g2`):</span></span>

 ![](../../database-engine/media/e52157b5-5160-4a4b-8560-50cdcf905b76.png "e52157b5-5160-4a4b-8560-50cdcf905b76")

 <span data-ttu-id="7fe33-192">Comme le montre l'illustration ci-dessus, les instances `CircularString` utilisent moins de points pour stocker des limites de courbe avec une précision supérieure que les instances `LineString`.</span><span class="sxs-lookup"><span data-stu-id="7fe33-192">As the illustration above shows, `CircularString` instances use fewer points to store curve boundaries with greater precision than `LineString` instances.</span></span> <span data-ttu-id="7fe33-193">`CircularString`les instances sont utiles pour stocker des limites circulaires comme un rayon de recherche de vingt milles à partir d’un point spécifique.</span><span class="sxs-lookup"><span data-stu-id="7fe33-193">`CircularString` instances are useful for storing circular boundaries like a twenty-mile search radius from a specific point.</span></span> <span data-ttu-id="7fe33-194">Les instances `LineString` conviennent particulièrement bien au stockage de limites qui sont linéaires comme un bloc d'agglomération carré.</span><span class="sxs-lookup"><span data-stu-id="7fe33-194">`LineString` instances are good for storing boundaries that are linear like a square city block.</span></span>

### <a name="linestring-and-compoundcurve-comparison"></a><span data-ttu-id="7fe33-195">Comparaison de LineString et de CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="7fe33-195">LineString and CompoundCurve comparison</span></span>
 <span data-ttu-id="7fe33-196">Les exemples de code suivants montrent comment stocker la même figure à l'aide des instances `LineString` et `CompoundCurve` :</span><span class="sxs-lookup"><span data-stu-id="7fe33-196">The following code examples show how to store the same figure using `LineString` and `CompoundCurve` instances:</span></span>

```sql
SET @g = geometry::Parse('LINESTRING(2 2, 4 2, 4 4, 2 4, 2 2)');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2), (4 2, 4 4), (4 4, 2 4), (2 4, 2 2))');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2, 4 4, 2 4, 2 2))');
```

 <span data-ttu-id="7fe33-197">or</span><span class="sxs-lookup"><span data-stu-id="7fe33-197">or</span></span>

 <span data-ttu-id="7fe33-198">Dans les exemples ci-dessus, une instance `LineString` ou une instance `CompoundCurve` pourrait stocker la figure.</span><span class="sxs-lookup"><span data-stu-id="7fe33-198">In the examples above, either a `LineString` instance or a `CompoundCurve` instance could store the figure.</span></span>  <span data-ttu-id="7fe33-199">L'exemple suivant utilise un `CompoundCurve` pour stocker un graphique en secteurs :</span><span class="sxs-lookup"><span data-stu-id="7fe33-199">This next example uses a `CompoundCurve` to store a pie slice:</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(2 2, 1 3, 0 2),(0 2, 1 0, 2 2))');
```

 <span data-ttu-id="7fe33-200">Une instance `CompoundCurve` peut stocker le segment d'arc de cercle (2 2, 1 3, 0 2) directement, alors qu'une instance `LineString` doit convertir la courbe en plusieurs segments de ligne plus petits.</span><span class="sxs-lookup"><span data-stu-id="7fe33-200">A `CompoundCurve` instance can store the circular arc segment (2 2, 1 3, 0 2) directly whereas a `LineString` instance would have to convert the curve into several smaller line segments.</span></span>

### <a name="circularstring-and-compoundcurve-comparison"></a><span data-ttu-id="7fe33-201">Comparaison de CircularString et de CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="7fe33-201">CircularString and CompoundCurve comparison</span></span>
 <span data-ttu-id="7fe33-202">L'exemple de code suivant indique comment le graphique en secteurs peut être stocké dans une instance `CircularString` :</span><span class="sxs-lookup"><span data-stu-id="7fe33-202">The following code example shows how the pie slice can be stored in a `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)');
SELECT @g.ToString(), @g.STLength();
```

 <span data-ttu-id="7fe33-203">Pour stocker le graphique en secteurs à l'aide d'une instance `CircularString`, il faut utiliser trois points pour chaque segment de ligne.</span><span class="sxs-lookup"><span data-stu-id="7fe33-203">To store the pie slice using a `CircularString` instance requires that three points be used for each line segment.</span></span>  <span data-ttu-id="7fe33-204">Si un point intermédiaire n'est pas connu, il doit être calculé ou le point de terminaison du segment de ligne doit être doublé comme le montre l'extrait de code suivant :</span><span class="sxs-lookup"><span data-stu-id="7fe33-204">If an intermediate point is not known, it either has to be calculated or the endpoint of the line segment has to be doubled as the following snippet shows:</span></span>

```sql
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 3 6.3246, 3 6.3246, 0 7, -3 6.3246, 0 0, 0 0)');
```

 <span data-ttu-id="7fe33-205">`CompoundCurve`les instances autorisent les `LineString` composants et de `CircularString` sorte que seuls deux points des segments de ligne du graphique à secteurs soient connus.</span><span class="sxs-lookup"><span data-stu-id="7fe33-205">`CompoundCurve` instances allow both `LineString` and `CircularString` components so that only two points to the line segments of the pie slice need to be known.</span></span>  <span data-ttu-id="7fe33-206">Cet exemple de code indique comment utiliser un `CompoundCurve` pour stocker la même figure :</span><span class="sxs-lookup"><span data-stu-id="7fe33-206">This code example shows how to use a `CompoundCurve` to store the same figure:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING( 3 6.3246, 0 7, -3 6.3246), (-3 6.3246, 0 0, 3 6.3246))');
SELECT @g.ToString(), @g.STLength();
```

### <a name="polygon-and-curvepolygon-comparison"></a><span data-ttu-id="7fe33-207">Comparaison de Polygon et de CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="7fe33-207">Polygon and CurvePolygon comparison</span></span>
 <span data-ttu-id="7fe33-208">Les instances `CurvePolygon` peuvent utiliser des instances `CircularString` et `CompoundCurve` lors de la définition de leurs anneaux intérieurs et extérieurs.</span><span class="sxs-lookup"><span data-stu-id="7fe33-208">`CurvePolygon` instances can use `CircularString` and `CompoundCurve` instances when defining their exterior and interior rings.</span></span>  <span data-ttu-id="7fe33-209">Les instances `Polygon` ne peuvent pas utiliser les types de segment d'arc de cercle : `CircularString` et `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="7fe33-209">`Polygon` instances cannot use the circular arc segment types: `CircularString` and `CompoundCurve`.</span></span>


## <a name="see-also"></a><span data-ttu-id="7fe33-210">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7fe33-210">See Also</span></span>
 <span data-ttu-id="7fe33-211">[Données spatiales &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [méthode type de données geometry référence](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) à la méthode de type de données [Geography référence](/sql/t-sql/spatial-geography/spatial-types-geography) [STNumCurves &#40;geometry type de données&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;type de données geography&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) [STGeomFromText &#40;type de données geometry](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type)&#41;[STGeomFromText &#40;type de données geography&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span><span class="sxs-lookup"><span data-stu-id="7fe33-211">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) [geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) [STNumCurves &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) [STGeomFromText &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) [STGeomFromText &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span></span>


