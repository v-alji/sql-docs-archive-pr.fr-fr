---
title: GeometryCollection | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- GeomCollection geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 4445c0d9-a66b-4d7c-88e4-a66fa6f7d9fd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 71d2234a9b73b7647554e364fe3864f089a47a0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613930"
---
# <a name="geometrycollection"></a><span data-ttu-id="c7dda-102">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="c7dda-102">GeometryCollection</span></span>
  <span data-ttu-id="c7dda-103">Une `GeometryCollection` est une collection de zéro ou plusieurs instances `geometry` ou `geography`.</span><span class="sxs-lookup"><span data-stu-id="c7dda-103">A `GeometryCollection` is a collection of zero or more `geometry` or `geography` instances.</span></span> <span data-ttu-id="c7dda-104">Une `GeometryCollection` peut être vide.</span><span class="sxs-lookup"><span data-stu-id="c7dda-104">A `GeometryCollection` can be empty.</span></span>  
  
## <a name="geometrycollection-instances"></a><span data-ttu-id="c7dda-105">Instances GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="c7dda-105">GeometryCollection Instances</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="c7dda-106">Instances acceptées</span><span class="sxs-lookup"><span data-stu-id="c7dda-106">Accepted Instances</span></span>  
 <span data-ttu-id="c7dda-107">Pour qu'une instance `GeometryCollection` soit acceptée, il doit s'agir d'une instance `GeometryCollection` vide ou toutes les instances comprenant l'instance `GeometryCollection` doivent être des instances acceptées.</span><span class="sxs-lookup"><span data-stu-id="c7dda-107">For a `GeometryCollection` instance to be accepted, it must either be an empty `GeometryCollection` instance or all the instances comprising the `GeometryCollection` instance must be accepted instances.</span></span> <span data-ttu-id="c7dda-108">L'exemple suivant illustre des instances acceptées.</span><span class="sxs-lookup"><span data-stu-id="c7dda-108">The following example shows accepted instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
 <span data-ttu-id="c7dda-109">L'exemple suivant lève une exception `System.FormatException`, car l'instance `LinesString` dans l'instance `GeometryCollection` n'est pas acceptée.</span><span class="sxs-lookup"><span data-stu-id="c7dda-109">The following example throws a `System.FormatException` because the `LinesString` instance in the `GeometryCollection` instance is not accepted.</span></span>  
  
```  
DECLARE @g geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1), POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="c7dda-110">Instances valides</span><span class="sxs-lookup"><span data-stu-id="c7dda-110">Valid Instances</span></span>  
 <span data-ttu-id="c7dda-111">Une instance `GeometryCollection` est valide lorsque toutes les instances qui comprennent l'instance `GeometryCollection` sont valides.</span><span class="sxs-lookup"><span data-stu-id="c7dda-111">A `GeometryCollection` instance is valid when all instances that comprise the `GeometryCollection` instance are valid.</span></span> <span data-ttu-id="c7dda-112">L'exemple suivant illustre trois instances `GeometryCollection` valides et une instance non valide.</span><span class="sxs-lookup"><span data-stu-id="c7dda-112">The following shows three valid `GeometryCollection` instances and one instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g4 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, 1 -5, -5 5, -5 -1, -1 -1)))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="c7dda-113">`@g4` n'est pas valide car l'instance `Polygon` dans l'instance `GeometryCollection` n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="c7dda-113">`@g4` is not valid because the `Polygon` instance in the `GeometryCollection` instance is not valid.</span></span>  
  
 <span data-ttu-id="c7dda-114">Pour plus d’informations sur les instances acceptées et valides, consultez [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [polygone](polygon.md)et [MultiPolygon](multipolygon.md).</span><span class="sxs-lookup"><span data-stu-id="c7dda-114">For more information on accepted and valid instances, see [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md), and [MultiPolygon](multipolygon.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c7dda-115">Exemples</span><span class="sxs-lookup"><span data-stu-id="c7dda-115">Examples</span></span>  
 <span data-ttu-id="c7dda-116">L’exemple suivant instancie un objet `geometry``GeometryCollection` avec les valeurs Z dans SRID 1 contenant une instance `Point` et une instance `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="c7dda-116">The following example instantiates a `geometry``GeometryCollection` with Z values in SRID 1 containing a `Point` instance and a `Polygon` instance.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomCollFromText('GEOMETRYCOLLECTION(POINT(3 3 1), POLYGON((0 0 2, 1 10 3, 1 0 4, 0 0 2)))', 1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7dda-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7dda-117">See Also</span></span>  
 [<span data-ttu-id="c7dda-118">Données spatiales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c7dda-118">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
