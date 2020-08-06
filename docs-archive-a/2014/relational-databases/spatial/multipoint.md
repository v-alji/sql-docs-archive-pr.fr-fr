---
title: MultiPoint | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPoint geometry subtype [SQL Server]
ms.assetid: 2aaab211-3aba-4dbd-90b7-095d997b1f62
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b741071b7986aceea4e49d4fde8293ef2c96fc2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613917"
---
# <a name="multipoint"></a><span data-ttu-id="0f7b7-102">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="0f7b7-102">MultiPoint</span></span>
  <span data-ttu-id="0f7b7-103">Un `MultiPoint` est une collection de zéro ou plusieurs points.</span><span class="sxs-lookup"><span data-stu-id="0f7b7-103">A `MultiPoint` is a collection of zero or more points.</span></span> <span data-ttu-id="0f7b7-104">La limite d'une instance `MultiPoint` est vide.</span><span class="sxs-lookup"><span data-stu-id="0f7b7-104">The boundary of a `MultiPoint` instance is empty.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0f7b7-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="0f7b7-105">Examples</span></span>  
 <span data-ttu-id="0f7b7-106">L'exemple suivant crée une instance `geometry MultiPoint` avec un SRID 23 et deux points : un point avec les coordonnées (2, 3), un point avec les coordonnées (7, 8) et une valeur Z de 9.5.</span><span class="sxs-lookup"><span data-stu-id="0f7b7-106">The following example creates a `geometry MultiPoint` instance with SRID 23 and two points: one point with the coordinates (2, 3), one point with the coordinates (7, 8), and a Z value of 9.5.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="0f7b7-107">Cette instance `MultiPoint` peut également être exprimée à l'aide de `STMPointFromText()` comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="0f7b7-107">This `MultiPoint` instance can also be expressed using `STMPointFromText()` as shown below.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STMPointFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="0f7b7-108">L'exemple suivant utilise la méthode `STGeometryN()` pour extraire une description du premier point dans la collection.</span><span class="sxs-lookup"><span data-stu-id="0f7b7-108">The following example uses the method `STGeometryN()` to retrieve a description of the first point in the collection.</span></span>  
  
```  
SELECT @g.STGeometryN(1).STAsText();  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f7b7-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f7b7-109">See Also</span></span>  
 <span data-ttu-id="0f7b7-110">[Point](point.md) </span><span class="sxs-lookup"><span data-stu-id="0f7b7-110">[Point](point.md) </span></span>  
 [<span data-ttu-id="0f7b7-111">Données spatiales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0f7b7-111">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
