---
title: CompoundCurve | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae357f9b-e3e2-4cdf-af02-012acda2e466
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 6a899bbe9a17a64083592e1078e8cac93365f02b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601311"
---
# <a name="compoundcurve"></a><span data-ttu-id="a6785-102">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="a6785-102">CompoundCurve</span></span>
  <span data-ttu-id="a6785-103">Un `CompoundCurve` est une collection de zéro ou plusieurs instances continues `CircularString` ou `LineString`, de type geometry ou geography.</span><span class="sxs-lookup"><span data-stu-id="a6785-103">A `CompoundCurve` is a collection of zero or more continuous `CircularString` or `LineString` instances of either geometry or geography types.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="a6785-104">Pour obtenir une description détaillée et des exemples des nouvelles fonctionnalités spatiales de cette version, y compris le `CompoundCurve` sous-type, téléchargez le livre blanc [nouvelles fonctionnalités spatiales dans SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span><span class="sxs-lookup"><span data-stu-id="a6785-104">For a detailed description and examples of the new spatial features in this release, including the `CompoundCurve` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

 <span data-ttu-id="a6785-105">Une instance `CompoundCurve` vide peut être instanciée, mais pour qu'un `CompoundCurve` soit valide, il doit respecter les critères suivants :</span><span class="sxs-lookup"><span data-stu-id="a6785-105">An empty `CompoundCurve` instance can be instantiated, but for a `CompoundCurve` to be valid it must meet the following criteria:</span></span>

1.  <span data-ttu-id="a6785-106">Il doit contenir au moins une instance `CircularString` ou `LineString`.</span><span class="sxs-lookup"><span data-stu-id="a6785-106">It must contain at least one `CircularString` or `LineString` instance.</span></span>

2.  <span data-ttu-id="a6785-107">La séquence des instances `CircularString` ou `LineString` doit être continue.</span><span class="sxs-lookup"><span data-stu-id="a6785-107">The sequence of `CircularString` or `LineString` instances must be continuous.</span></span>

 <span data-ttu-id="a6785-108">Si un `CompoundCurve` contient une séquence de plusieurs `CircularString` `LineString` instances et, le point de terminaison de fin pour chaque instance, à l’exception de la dernière instance, doit être le point de terminaison initial de l’instance suivante dans la séquence.</span><span class="sxs-lookup"><span data-stu-id="a6785-108">If a `CompoundCurve` contains a sequence of multiple `CircularString` and `LineString` instances, the ending endpoint for every instance except for the last instance must be the starting endpoint for the next instance in the sequence.</span></span> <span data-ttu-id="a6785-109">Cela signifie que si le point de fin d'une instance précédente dans la séquence est (4 3 7 2), le point de départ de l'instance suivante dans la séquence doit être (4 3 7 2).</span><span class="sxs-lookup"><span data-stu-id="a6785-109">This means that if the ending point of a prior instance in the sequence is (4 3 7 2), the starting point for the next instance in the sequence must be (4 3 7 2).</span></span> <span data-ttu-id="a6785-110">Notez que les valeurs Z (élévation) et M (mesure) du point doivent également être identiques.</span><span class="sxs-lookup"><span data-stu-id="a6785-110">Note that Z(elevation) and M(measure) values for the point must also be the same.</span></span> <span data-ttu-id="a6785-111">Si les deux points présentent une différence, une `System.FormatException` est levée.</span><span class="sxs-lookup"><span data-stu-id="a6785-111">If there is a difference in the two points, a `System.FormatException` is thrown.</span></span> <span data-ttu-id="a6785-112">Les points dans un `CircularString` n'ont pas besoin de valeur Z ou M.</span><span class="sxs-lookup"><span data-stu-id="a6785-112">Points in a `CircularString` do not have to have a Z or M value.</span></span> <span data-ttu-id="a6785-113">Si aucune valeur Z ou M n'est indiquée pour le point de fin de l'instance précédente, le point de départ de l'instance suivante ne peut pas inclure de valeur Z ou M.</span><span class="sxs-lookup"><span data-stu-id="a6785-113">If no Z or M values are given for the ending point of the prior instance, the starting point of the next instance cannot include Z or M values.</span></span> <span data-ttu-id="a6785-114">Si le point de fin de la séquence précédente est (4 3), le point de départ de la séquence suivante doit être (4 3), mais pas (4 3 7 2).</span><span class="sxs-lookup"><span data-stu-id="a6785-114">If the ending point for the prior sequence is (4 3), the starting point for the next sequence must be (4 3); it cannot be (4 3 7 2).</span></span> <span data-ttu-id="a6785-115">Tous les points d'une instance `CompoundCurve` doivent soit ne pas avoir de valeur Z, soit avoir une valeur Z identique.</span><span class="sxs-lookup"><span data-stu-id="a6785-115">All points in a `CompoundCurve` instance must have either no Z value or the same Z value.</span></span>

## <a name="compoundcurve-instances"></a><span data-ttu-id="a6785-116">Instances CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="a6785-116">CompoundCurve instances</span></span>
 <span data-ttu-id="a6785-117">L'illustration suivante montre des types de `CompoundCurve` valides.</span><span class="sxs-lookup"><span data-stu-id="a6785-117">The following illustration shows valid `CompoundCurve` types.</span></span>

 ![](../../database-engine/media/f278742e-b861-4555-8b51-3d972b7602bf.png "f278742e-b861-4555-8b51-3d972b7602bf")

### <a name="accepted-instances"></a><span data-ttu-id="a6785-118">Instances acceptées</span><span class="sxs-lookup"><span data-stu-id="a6785-118">Accepted instances</span></span>
 <span data-ttu-id="a6785-119">L'instance `CompoundCurve` est acceptée s'il s'agit d'une instance vide ou si elle répond aux critères suivants.</span><span class="sxs-lookup"><span data-stu-id="a6785-119">`CompoundCurve` instance is accepted if it is an empty instance or meets the following criteria.</span></span>

1.  <span data-ttu-id="a6785-120">Toutes les instances contenues par l'instance `CompoundCurve` sont des instances de segment d'arc de cercle acceptées.</span><span class="sxs-lookup"><span data-stu-id="a6785-120">All the instances contained by `CompoundCurve` instance are accepted circular arc segment instances.</span></span> <span data-ttu-id="a6785-121">Pour plus d’informations sur les instances de segment d’arc de cercle acceptées, consultez [LineString](linestring.md) et [CircularString](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="a6785-121">For more information on accepted circular arc segment instances, see [LineString](linestring.md) and [CircularString](circularstring.md).</span></span>

2.  <span data-ttu-id="a6785-122">Tous les segments d'arc de cercle dans l'instance `CompoundCurve` sont connectés.</span><span class="sxs-lookup"><span data-stu-id="a6785-122">All of the circular arc segments in the `CompoundCurve` instance are connected.</span></span> <span data-ttu-id="a6785-123">Le premier point de chaque segment d’arc de cercle suivant est identique au dernier point du segment d’arc de cercle précédent.</span><span class="sxs-lookup"><span data-stu-id="a6785-123">The first point for each succeeding circular arc segment is the same as the last point on the preceding circular arc segment.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="a6785-124">Cela inclut les coordonnées Z et M.</span><span class="sxs-lookup"><span data-stu-id="a6785-124">This includes the Z and M coordinates.</span></span> <span data-ttu-id="a6785-125">Ainsi, les quatre coordonnées X, Y, Z et M doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="a6785-125">So, all four coordinates X, Y, Z, and M must be the same.</span></span>

3.  <span data-ttu-id="a6785-126">Aucune des instances contenues n'est une instance vide.</span><span class="sxs-lookup"><span data-stu-id="a6785-126">None of the contained instances are empty instances.</span></span>

 <span data-ttu-id="a6785-127">L'exemple suivant illustre des instances `CompoundCurve` acceptées.</span><span class="sxs-lookup"><span data-stu-id="a6785-127">The following example shows accepted `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
```

 <span data-ttu-id="a6785-128">L'exemple suivant montre des instances `CompoundCurve` qui ne sont pas acceptées.</span><span class="sxs-lookup"><span data-stu-id="a6785-128">The following example shows `CompoundCurve` instances that are not accepted.</span></span> <span data-ttu-id="a6785-129">Ces instances lèvent une `System.FormatException`.</span><span class="sxs-lookup"><span data-stu-id="a6785-129">These instances throw `System.FormatException`.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING EMPTY)';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (1 0, 2 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="a6785-130">Instances valides</span><span class="sxs-lookup"><span data-stu-id="a6785-130">Valid instances</span></span>
 <span data-ttu-id="a6785-131">Une instance `CompoundCurve` est valide si elle répond aux critères suivants.</span><span class="sxs-lookup"><span data-stu-id="a6785-131">A `CompoundCurve` instance is valid if it meets the following criteria.</span></span>

1.  <span data-ttu-id="a6785-132">L'instance `CompoundCurve` est acceptée.</span><span class="sxs-lookup"><span data-stu-id="a6785-132">The `CompoundCurve` instance is accepted.</span></span>

2.  <span data-ttu-id="a6785-133">Toutes les instances de segment d'arc de cercle contenues par l'instance `CompoundCurve` sont des instances valides.</span><span class="sxs-lookup"><span data-stu-id="a6785-133">All circular arc segment instances contained by the `CompoundCurve` instance are valid instances.</span></span>

 <span data-ttu-id="a6785-134">L'exemple suivant montre des instances `CompoundCurve` valides.</span><span class="sxs-lookup"><span data-stu-id="a6785-134">The following example shows valid `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();

```

 <span data-ttu-id="a6785-135">`@g3` est valide parce que l'instance `CircularString` est valide.</span><span class="sxs-lookup"><span data-stu-id="a6785-135">`@g3` is valid because the `CircularString` instance is valid.</span></span> <span data-ttu-id="a6785-136">Pour plus d’informations sur la validité de l' `CircularString` instance, consultez [CircularString](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="a6785-136">For more information on the validity of the `CircularString` instance, see [CircularString](circularstring.md).</span></span>

 <span data-ttu-id="a6785-137">L'exemple suivant montre des instances `CompoundCurve` qui ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="a6785-137">The following example shows `CompoundCurve` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4, 3 5))';
DECLARE @g2 geometry = 'COMPOUNDCURVE((1 1, 1 1))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 2 3, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="a6785-138">`@g1` n’est pas valide car la deuxième instance n’est pas une instance LineString valide.</span><span class="sxs-lookup"><span data-stu-id="a6785-138">`@g1` is not valid because the second instance is not a valid LineString instance.</span></span> <span data-ttu-id="a6785-139">`@g2` n'est pas valide car l'instance `LineString` n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="a6785-139">`@g2` is not valid because the `LineString` instance is not valid.</span></span> <span data-ttu-id="a6785-140">`@g3` n'est pas valide car l'instance `CircularString` n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="a6785-140">`@g3` is not valid because the `CircularString` instance is not valid.</span></span> <span data-ttu-id="a6785-141">Pour plus d’informations sur les `CircularString` instances et valides `LineString` , consultez [CircularString](circularstring.md) et [LineString](linestring.md).</span><span class="sxs-lookup"><span data-stu-id="a6785-141">For more information on valid `CircularString` and `LineString` instances, see [CircularString](circularstring.md) and [LineString](linestring.md).</span></span>

## <a name="examples"></a><span data-ttu-id="a6785-142">Exemples</span><span class="sxs-lookup"><span data-stu-id="a6785-142">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-compooundcurve"></a><span data-ttu-id="a6785-143">R.</span><span class="sxs-lookup"><span data-stu-id="a6785-143">A.</span></span> <span data-ttu-id="a6785-144">Instanciation d'une instance geometry avec un CompooundCurve vide</span><span class="sxs-lookup"><span data-stu-id="a6785-144">Instantiating a geometry instance with an empty CompooundCurve</span></span>
 <span data-ttu-id="a6785-145">L'exemple suivant montre comment créer une instance `CompoundCurve` vide :</span><span class="sxs-lookup"><span data-stu-id="a6785-145">The following example shows how to create an empty `CompoundCurve` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE EMPTY');
```

### <a name="b-declaring-and-instantiating-a-geometry-instance-using-a-compoundcurve-in-the-same-statement"></a><span data-ttu-id="a6785-146">B.</span><span class="sxs-lookup"><span data-stu-id="a6785-146">B.</span></span> <span data-ttu-id="a6785-147">Déclaration et instanciation d'une instance geometry à l'aide d'un CompoundCurve dans la même instruction</span><span class="sxs-lookup"><span data-stu-id="a6785-147">Declaring and instantiating a geometry instance using a CompoundCurve in the same statement</span></span>
 <span data-ttu-id="a6785-148">L’exemple suivant indique comment déclarer et initialiser une instance `geometry` avec `CompoundCurve`dans la même instruction :</span><span class="sxs-lookup"><span data-stu-id="a6785-148">The following example shows how to declare and initialize a `geometry` instance with a `CompoundCurve`in the same statement:</span></span>

```sql
DECLARE @g geometry = 'COMPOUNDCURVE ((2 2, 0 0),CIRCULARSTRING (0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0))';
```

### <a name="c-instantiating-a-geography-instance-with-a-compoundcurve"></a><span data-ttu-id="a6785-149">C.</span><span class="sxs-lookup"><span data-stu-id="a6785-149">C.</span></span> <span data-ttu-id="a6785-150">Instanciation d'une instance geography avec un CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="a6785-150">Instantiating a geography instance with a CompoundCurve</span></span>
 <span data-ttu-id="a6785-151">L'exemple suivant indique comment déclarer et initialiser une instance `geography` avec un `CompoundCurve` :</span><span class="sxs-lookup"><span data-stu-id="a6785-151">The following example shows how to declare and initialize a `geography` instance with a `CompoundCurve`:</span></span>

```sql
DECLARE @g geography = 'COMPOUNDCURVE(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';
```

### <a name="d-storing-a-square-in-a-compoundcurve-instance"></a><span data-ttu-id="a6785-152">D.</span><span class="sxs-lookup"><span data-stu-id="a6785-152">D.</span></span> <span data-ttu-id="a6785-153">Stocker un carré dans une instance CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="a6785-153">Storing a square in a CompoundCurve instance</span></span>
 <span data-ttu-id="a6785-154">L'exemple suivant montre deux façons différentes d'utiliser une instance `CompoundCurve` pour stocker un carré.</span><span class="sxs-lookup"><span data-stu-id="a6785-154">The following example uses two different ways to use a `CompoundCurve` instance to store a square.</span></span>

```sql
DECLARE @g1 geometry, @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3), (1 3, 3 3),(3 3, 3 1), (3 1, 1 1))');
SET @g2 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3, 3 3, 3 1, 1 1))');
SELECT @g1.STLength(), @g2.STLength();
```

 <span data-ttu-id="a6785-155">Les longueurs de `@g1` et `@g2` sont identiques.</span><span class="sxs-lookup"><span data-stu-id="a6785-155">The lengths for both `@g1` and `@g2` are the same.</span></span> <span data-ttu-id="a6785-156">Notez dans cet exemple qu'une instance `CompoundCurve` peut stocker une ou plusieurs instances `LineString`.</span><span class="sxs-lookup"><span data-stu-id="a6785-156">Notice from the example that a `CompoundCurve` instance can store one or more instances of `LineString`.</span></span>

### <a name="e-instantiating-a-geometry-instance-using-a-compoundcurve-with-multiple-circularstrings"></a><span data-ttu-id="a6785-157">E.</span><span class="sxs-lookup"><span data-stu-id="a6785-157">E.</span></span> <span data-ttu-id="a6785-158">Instanciation d'une instance geometry à l'aide d'un CompoundCurve avec plusieurs CircularStrings</span><span class="sxs-lookup"><span data-stu-id="a6785-158">Instantiating a geometry instance using a CompoundCurve with multiple CircularStrings</span></span>
 <span data-ttu-id="a6785-159">L'exemple suivant montre comment utiliser deux instances `CircularString` différentes pour initialiser un `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="a6785-159">The following example shows how to use two different `CircularString` instances to initialize a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT @g.STLength();
```

 <span data-ttu-id="a6785-160">Cela génère la sortie suivante : 12,566370... qui est l’équivalent de 4&#x03c0; (4 \* pi).</span><span class="sxs-lookup"><span data-stu-id="a6785-160">This produces the following output: 12.566370... which is the equivalent of 4&#x03c0; (4 \* pi).</span></span> <span data-ttu-id="a6785-161">L'instance `CompoundCurve` de l'exemple stocke un cercle avec un rayon de 2.</span><span class="sxs-lookup"><span data-stu-id="a6785-161">The `CompoundCurve` instance in the example stores a circle with a radius of 2.</span></span> <span data-ttu-id="a6785-162">Les deux exemples de code précédents n'ont pas eu à utiliser un `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="a6785-162">Both of the previous code examples did not have to use a `CompoundCurve`.</span></span> <span data-ttu-id="a6785-163">Pour le premier exemple, une instance `LineString` aurait été plus simple et pour le deuxième exemple, une instance `CircularString` .</span><span class="sxs-lookup"><span data-stu-id="a6785-163">For the first example a `LineString` instance would have been simpler, and a `CircularString` instance would have been simpler for the second example.</span></span> <span data-ttu-id="a6785-164">Toutefois, l'exemple suivant montre en quoi un `CompoundCurve` constitue une meilleure solution.</span><span class="sxs-lookup"><span data-stu-id="a6785-164">However, the next example shows where a `CompoundCurve` provides a better alternative.</span></span>

### <a name="f-using-a-compoundcurve-to-store-a-semicircle"></a><span data-ttu-id="a6785-165">F.</span><span class="sxs-lookup"><span data-stu-id="a6785-165">F.</span></span> <span data-ttu-id="a6785-166">Utilisation d'un CompoundCurve pour stocker un demi-cercle</span><span class="sxs-lookup"><span data-stu-id="a6785-166">Using a CompoundCurve to store a semicircle</span></span>
 <span data-ttu-id="a6785-167">L'exemple suivant utilise une instance `CompoundCurve` pour stocker un demi-cercle.</span><span class="sxs-lookup"><span data-stu-id="a6785-167">The following example uses a `CompoundCurve` instance to store a semicircle.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 0 2))');
SELECT @g.STLength();
```

### <a name="g-storing-multiple-circularstring-and-linestring-instances-in-a-compoundcurve"></a><span data-ttu-id="a6785-168">G.</span><span class="sxs-lookup"><span data-stu-id="a6785-168">G.</span></span> <span data-ttu-id="a6785-169">Stocker plusieurs instances CircularString et LineString dans un CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="a6785-169">Storing multiple CircularString and LineString instances in a CompoundCurve</span></span>
 <span data-ttu-id="a6785-170">L'exemple suivant montre comment plusieurs instances `CircularString` et `LineString` peuvent être stockées à l'aide d'un `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="a6785-170">The following example shows how multiple `CircularString` and `LineString` instances can be stored by using a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('COMPOUNDCURVE((3 5, 3 3), CIRCULARSTRING(3 3, 5 1, 7 3), (7 3, 7 5), CIRCULARSTRING(7 5, 5 7, 3 5))');
SELECT @g.STLength();
```

### <a name="h-storing-instances-with-z-and-m-values"></a><span data-ttu-id="a6785-171">H.</span><span class="sxs-lookup"><span data-stu-id="a6785-171">H.</span></span> <span data-ttu-id="a6785-172">Stockage d'instances avec des valeurs Z et M</span><span class="sxs-lookup"><span data-stu-id="a6785-172">Storing instances with Z and M values</span></span>
 <span data-ttu-id="a6785-173">L'exemple suivant indique comment utiliser une instance `CompoundCurve` pour stocker une séquence d'instances `CircularString` et `LineString` comportant toutes deux des valeurs Z et M.</span><span class="sxs-lookup"><span data-stu-id="a6785-173">The following example shows how to use a `CompoundCurve` instance to store a sequence of `CircularString` and `LineString` instances with both Z and M values.</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(7 5 4 2, 5 7 4 2, 3 5 4 2), (3 5 4 2, 8 7 4 2))');
```

### <a name="i-illustrating-why-circularstring-instances-must-be-explicitly-declared"></a><span data-ttu-id="a6785-174">I.</span><span class="sxs-lookup"><span data-stu-id="a6785-174">I.</span></span> <span data-ttu-id="a6785-175">Illustration de la raison pour laquelle les instances CircularString doivent être déclarées de manière explicite</span><span class="sxs-lookup"><span data-stu-id="a6785-175">Illustrating why CircularString instances must be explicitly declared</span></span>
 <span data-ttu-id="a6785-176">L'exemple suivant montre pourquoi les instances `CircularString` doivent être déclarées de manière explicite.</span><span class="sxs-lookup"><span data-stu-id="a6785-176">The following example shows why `CircularString` instances must be explicitly declared.</span></span> <span data-ttu-id="a6785-177">Le programmeur essaie de stocker un cercle dans une instance `CompoundCurve` .</span><span class="sxs-lookup"><span data-stu-id="a6785-177">The programmer is trying to store a circle in a `CompoundCurve` instance.</span></span>

```sql
DECLARE @g1 geometry;  
DECLARE @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 2 4, 0 2))');
SELECT 'Circle One', @g1.STLength() AS Perimeter;  -- gives an inaccurate amount
SET @g2 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT 'Circle Two', @g2.STLength() AS Perimeter;  -- now we get an accurate amount
```

 <span data-ttu-id="a6785-178">La sortie se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="a6785-178">The output is as follows:</span></span>

```
Circle One11.940039...
Circle Two12.566370...
```

 <span data-ttu-id="a6785-179">Le périmètre du cercle deux est approximativement de 4&#x03c0; (4 \* pi), qui est la valeur réelle du périmètre.</span><span class="sxs-lookup"><span data-stu-id="a6785-179">The perimeter for Circle Two is approximately 4&#x03c0; (4 \* pi), which is the actual value for the perimeter.</span></span> <span data-ttu-id="a6785-180">Toutefois, le périmètre de Circle One est exagérément inexact.</span><span class="sxs-lookup"><span data-stu-id="a6785-180">However, the perimeter for Circle One is significantly inaccurate.</span></span> <span data-ttu-id="a6785-181">L'instance `CompoundCurve` de Circle One stocke un segment d'arc de cercle (ABC) et deux segments de ligne (CD, DA).</span><span class="sxs-lookup"><span data-stu-id="a6785-181">Circle One's `CompoundCurve` instance stores one circular arc segment (ABC) and two line segments (CD, DA).</span></span> <span data-ttu-id="a6785-182">L'instance `CompoundCurve` doit stocker deux segments d'arc de cercle (ABC, CDA) pour définir un cercle.</span><span class="sxs-lookup"><span data-stu-id="a6785-182">The `CompoundCurve` instance has to store two circular arc segments (ABC, CDA) to define a circle.</span></span> <span data-ttu-id="a6785-183">Une instance `LineString` définit le deuxième ensemble de points (4 2, 2 4, 0 2) dans l'instance `CompoundCurve` de Circle One.</span><span class="sxs-lookup"><span data-stu-id="a6785-183">A `LineString` instance defines the second set of points (4 2, 2 4, 0 2) in Circle One's `CompoundCurve` instance.</span></span> <span data-ttu-id="a6785-184">Vous devez déclarer de manière explicite une instance `CircularString` à l'intérieur d'un `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="a6785-184">You have to explicitly declare a `CircularString` instance inside a `CompoundCurve`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6785-185">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6785-185">See Also</span></span>
 <span data-ttu-id="a6785-186">[STIsValid &#40;Geometry type de données&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;Geometry type de données&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry type de données&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;Geometry type de données&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [LineString](linestring.md) [CircularString](circularstring.md) [types de données spatiales point de vue d’ensemble](spatial-data-types-overview.md) [Point](point.md)</span><span class="sxs-lookup"><span data-stu-id="a6785-186">[STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [LineString](linestring.md) [CircularString](circularstring.md) [Spatial Data Types Overview](spatial-data-types-overview.md) [Point](point.md)</span></span>


