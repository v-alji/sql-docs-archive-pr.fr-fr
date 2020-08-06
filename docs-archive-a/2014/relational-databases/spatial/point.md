---
title: Point | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Point geometry subtype [SQL Server]
- geometry data type [SQL Server], spatial data
ms.assetid: 2a596ec4-8b2f-4962-bcb4-e5c8f77edad5
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4b12069d84e00738e3ddac8c414f33903f4f0999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613913"
---
# <a name="point"></a><span data-ttu-id="4839c-102">Point</span><span class="sxs-lookup"><span data-stu-id="4839c-102">Point</span></span>
  <span data-ttu-id="4839c-103">Dans les données spatiales [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un `Point` est un objet à zéro dimension qui représente un emplacement unique et peut contenir des valeurs Z (élévation) et M (mesure).</span><span class="sxs-lookup"><span data-stu-id="4839c-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data, a `Point` is a 0-dimensional object representing a single location and may contain Z (elevation) and M (measure) values.</span></span>  
  
## <a name="geography-data-type"></a><span data-ttu-id="4839c-104">Type de données geography</span><span class="sxs-lookup"><span data-stu-id="4839c-104">Geography Data Type</span></span>  
 <span data-ttu-id="4839c-105">Le type Point pour le type de données geography représente un emplacement unique où *Lat* et *Long* désignent respectivement la latitude et la longitude.</span><span class="sxs-lookup"><span data-stu-id="4839c-105">The Point type for the geography data type represents a single location where *Lat* represents latitude and *Long* represents longitude.</span></span> <span data-ttu-id="4839c-106">Les valeurs de latitude et de longitude sont mesurées en degrés.</span><span class="sxs-lookup"><span data-stu-id="4839c-106">The values for latitude and longitude are measured in degrees.</span></span> <span data-ttu-id="4839c-107">Les valeurs de latitude sont toujours comprises dans l’intervalle [-90, 90]. Si vous entrez une valeur non comprise dans cette plage, une exception est levée.</span><span class="sxs-lookup"><span data-stu-id="4839c-107">Values for latitude always lie in the interval [-90, 90], and values that are inputted outside this range will throw an exception.</span></span> <span data-ttu-id="4839c-108">Les valeurs de longitude sont toujours comprises dans l’intervalle [-180, 180]. Si vous entrez une valeur non comprise dans cette plage, elle est renvoyée pour y être contenue.</span><span class="sxs-lookup"><span data-stu-id="4839c-108">Values for longitude always lie in the interval (-180, 180], and values inputted outside this range are wrapped around to fit in this range.</span></span> <span data-ttu-id="4839c-109">Par exemple, si vous entrez la valeur 190 pour la longitude, elle est renvoyée à la valeur -170.</span><span class="sxs-lookup"><span data-stu-id="4839c-109">For example, if 190 is inputted for longitude, then it will be wrapped to the value -170.</span></span> <span data-ttu-id="4839c-110">Le*SRID* représente l’ID de référence spatiale de l’instance **geography** à retourner.</span><span class="sxs-lookup"><span data-stu-id="4839c-110">*SRID* represents the spatial reference ID of the **geography** instance that you wish to return.</span></span>  
  
## <a name="geometry-data-type"></a><span data-ttu-id="4839c-111">Type de données geometry</span><span class="sxs-lookup"><span data-stu-id="4839c-111">Geometry Data Type</span></span>  
 <span data-ttu-id="4839c-112">Le type Point pour le type de données geometry représente un emplacement unique où *X* et *Y* désignent respectivement les coordonnées X et Y du point généré.</span><span class="sxs-lookup"><span data-stu-id="4839c-112">The Point type for the geometry data type represents a single location where *X* represents the X-coordinate of the Point being generated and *Y* represents the Y-coordinate of the Point being generated.</span></span> <span data-ttu-id="4839c-113">Le*SRID* représente l’ID de référence spatiale de l’instance **geometry** à retourner.</span><span class="sxs-lookup"><span data-stu-id="4839c-113">*SRID* represents the spatial reference ID of the **geometry** instance that you wish to return.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4839c-114">Exemples</span><span class="sxs-lookup"><span data-stu-id="4839c-114">Examples</span></span>  
 <span data-ttu-id="4839c-115">L’exemple suivant crée une instance `geometry Point`qui représente le point (3, 4) avec un SRID de 0.</span><span class="sxs-lookup"><span data-stu-id="4839c-115">The following example creates a `geometry Point`instance representing the point (3, 4) with an SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT (3 4)', 0);  
```  
  
 <span data-ttu-id="4839c-116">L’exemple suivant crée une instance `geometry``Point` qui représente le point (3, 4) avec une valeur Z (élévation) de 7, une valeur M (mesure) de 2,5 et le SRID par défaut de 0.</span><span class="sxs-lookup"><span data-stu-id="4839c-116">The next example creates a `geometry``Point` instance representing the point (3, 4) with a Z (elevation) value of 7, an M (measure) value of 2.5, and the default SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 7 2.5)');  
```  
  
 <span data-ttu-id="4839c-117">Le dernier exemple retourne les valeurs X, Y, Z et M pour l’instance `geometry``Point` .</span><span class="sxs-lookup"><span data-stu-id="4839c-117">The final example returns the X, Y, Z, and M values for the `geometry``Point` instance.</span></span>  
  
```  
SELECT @g.STX;  
SELECT @g.STY;  
SELECT @g.Z;  
SELECT @g.M;  
```  
  
 <span data-ttu-id="4839c-118">Les valeurs Z et M peuvent être spécifiées explicitement comme NULL, comme illustré dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="4839c-118">Z and M values may be explicitly specified as NULL, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 NULL NULL)');  
```  
  
## <a name="see-also"></a><span data-ttu-id="4839c-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4839c-119">See Also</span></span>  
 <span data-ttu-id="4839c-120">[MultiPoint](multipoint.md) </span><span class="sxs-lookup"><span data-stu-id="4839c-120">[MultiPoint](multipoint.md) </span></span>  
 <span data-ttu-id="4839c-121">[Type de données de la géométrie &#40;STX&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="4839c-121">[STX &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span></span>  
 <span data-ttu-id="4839c-122">[STY &#40;type de données geometry&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="4839c-122">[STY &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span></span>  
 [<span data-ttu-id="4839c-123">Données spatiales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4839c-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
