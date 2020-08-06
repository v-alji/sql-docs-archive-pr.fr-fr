---
title: Données spatiales (SQL Server) | Microsoft Docs
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server], spatial storage design
- planar spatial data [SQL Server], designing
- spatial data types [SQL Server]
- geodetic spatial data [SQL Server]
- geometry data type [SQL Server], spatial storage design
- spatial storage [SQL Server]
- geodetic spatial data [SQL Server], designing
ms.assetid: 41a132a1-09e2-4426-b9df-225270cb8e15
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4d491420a9eca7c35b89b254a03381c6467c834c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613908"
---
# <a name="spatial-data-sql-server"></a><span data-ttu-id="fd79a-102">Données spatiales (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fd79a-102">Spatial Data (SQL Server)</span></span>
  <span data-ttu-id="fd79a-103">Données spatiales représentent des informations sur l’emplacement physique et la forme d’objets géométriques.</span><span class="sxs-lookup"><span data-stu-id="fd79a-103">Spatial data represents information about the physical location and shape of geometric objects.</span></span> <span data-ttu-id="fd79a-104">Ces objets peuvent être des emplacements précis ou des objets plus complexes, tels que des pays, des routes ou des lacs.</span><span class="sxs-lookup"><span data-stu-id="fd79a-104">These objects can be point locations or more complex objects such as countries, roads, or lakes.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fd79a-105">prend en charge deux types de données spatiales : le type de données `geometry` et le type de données `geography`.</span><span class="sxs-lookup"><span data-stu-id="fd79a-105">supports two spatial data types: the `geometry` data type and the `geography` data type.</span></span>  
  
-   <span data-ttu-id="fd79a-106">Le type `geometry` représente des données dans un système de coordonnées euclidien (plat).</span><span class="sxs-lookup"><span data-stu-id="fd79a-106">The `geometry` type represents data in a Euclidean (flat) coordinate system.</span></span>  
  
-   <span data-ttu-id="fd79a-107">Le type `geography` représente des données dans un système de coordonnées de monde sphérique.</span><span class="sxs-lookup"><span data-stu-id="fd79a-107">The `geography` type represents data in a round-earth coordinate system.</span></span>  
  
 <span data-ttu-id="fd79a-108">Ces deux types de données sont implémentés comme types de données CLR .NET dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd79a-108">Both data types are implemented as .NET common language runtime (CLR) data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fd79a-109">Pour obtenir une description détaillée et des exemples des fonctionnalités spatiales introduites dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], téléchargez le livre blanc intitulé [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407)(Nouvelles fonctionnalités spatiales dans SQL Server 2012).</span><span class="sxs-lookup"><span data-stu-id="fd79a-109">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="fd79a-110">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="fd79a-110">Related Tasks</span></span>  
 [<span data-ttu-id="fd79a-111">Créer, construire et interroger des instances geometry</span><span class="sxs-lookup"><span data-stu-id="fd79a-111">Create, Construct, and Query geometry Instances</span></span>](create-construct-and-query-geometry-instances.md)  
 <span data-ttu-id="fd79a-112">Décrit les méthodes que vous pouvez utiliser avec des instances du type de données geometry.</span><span class="sxs-lookup"><span data-stu-id="fd79a-112">Describes the methods that you can use with instances of the geometry data type.</span></span>  
  
 [<span data-ttu-id="fd79a-113">Créer, construire et interroger des instances geography</span><span class="sxs-lookup"><span data-stu-id="fd79a-113">Create, Construct, and Query geography Instances</span></span>](create-construct-and-query-geography-instances.md)  
 <span data-ttu-id="fd79a-114">Décrit les méthodes que vous pouvez utiliser avec des instances du type de données geography.</span><span class="sxs-lookup"><span data-stu-id="fd79a-114">Describes the methods that you can use with instances of the geography data type.</span></span>  
  
 [<span data-ttu-id="fd79a-115">Interroger des données spatiales au sujet du plus proche voisin</span><span class="sxs-lookup"><span data-stu-id="fd79a-115">Query Spatial Data for Nearest Neighbor</span></span>](query-spatial-data-for-nearest-neighbor.md)  
 <span data-ttu-id="fd79a-116">Décrit le modèle de requête commun qui est utilisé pour rechercher les objets spatiaux les plus proches d'un objet spatial spécifique.</span><span class="sxs-lookup"><span data-stu-id="fd79a-116">Describes the common query pattern that is used to find the closest spatial objects to a specific spatial object.</span></span>  
  
 [<span data-ttu-id="fd79a-117">Créer, modifier et supprimer les index spatiaux</span><span class="sxs-lookup"><span data-stu-id="fd79a-117">Create, Modify, and Drop Spatial Indexes</span></span>](create-modify-and-drop-spatial-indexes.md)  
 <span data-ttu-id="fd79a-118">Fournit des informations sur la création, la modification et la suppression d'un index spatial.</span><span class="sxs-lookup"><span data-stu-id="fd79a-118">Provides information about creating, altering, and dropping a spatial index.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="fd79a-119">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="fd79a-119">Related Content</span></span>  
 [<span data-ttu-id="fd79a-120">Présentation des types de données spatiales</span><span class="sxs-lookup"><span data-stu-id="fd79a-120">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
 <span data-ttu-id="fd79a-121">Présente les types de données spatiales.</span><span class="sxs-lookup"><span data-stu-id="fd79a-121">Introduces the spatial data types.</span></span>  
  
-   [<span data-ttu-id="fd79a-122">Point</span><span class="sxs-lookup"><span data-stu-id="fd79a-122">Point</span></span>](point.md)  
  
-   [<span data-ttu-id="fd79a-123">LineString</span><span class="sxs-lookup"><span data-stu-id="fd79a-123">LineString</span></span>](linestring.md)  
  
-   [<span data-ttu-id="fd79a-124">CircularString</span><span class="sxs-lookup"><span data-stu-id="fd79a-124">CircularString</span></span>](circularstring.md)  
  
-   [<span data-ttu-id="fd79a-125">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="fd79a-125">CompoundCurve</span></span>](compoundcurve.md)  
  
-   [<span data-ttu-id="fd79a-126">Polygon</span><span class="sxs-lookup"><span data-stu-id="fd79a-126">Polygon</span></span>](polygon.md)  
  
-   [<span data-ttu-id="fd79a-127">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="fd79a-127">CurvePolygon</span></span>](curvepolygon.md)  
  
-   [<span data-ttu-id="fd79a-128">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="fd79a-128">MultiPoint</span></span>](multipoint.md)  
  
-   [<span data-ttu-id="fd79a-129">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="fd79a-129">MultiLineString</span></span>](multilinestring.md)  
  
-   [<span data-ttu-id="fd79a-130">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="fd79a-130">MultiPolygon</span></span>](multipolygon.md)  
  
-   [<span data-ttu-id="fd79a-131">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="fd79a-131">GeometryCollection</span></span>](geometrycollection.md)  
  
 [<span data-ttu-id="fd79a-132">Vue d’ensemble des index spatiaux</span><span class="sxs-lookup"><span data-stu-id="fd79a-132">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
 <span data-ttu-id="fd79a-133">Présente les index spatiaux et décrit le pavage et les schémas de pavage.</span><span class="sxs-lookup"><span data-stu-id="fd79a-133">Introduces spatial indexes and describes tessellation and tessellation schemes.</span></span>  
  
  
