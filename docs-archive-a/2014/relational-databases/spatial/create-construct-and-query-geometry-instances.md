---
title: Créer, construire et interroger des instances geometry | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- planar spatial data [SQL Server], getting started
- geometry data type [SQL Server], getting started
ms.assetid: c6b5c852-37d2-48d0-a8ad-e43bb80d6514
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 539f3f8bb1d9a1c277d6317cc571cf8bcb281833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601307"
---
# <a name="create-construct-and-query-geometry-instances"></a><span data-ttu-id="8d352-102">Créer, construire et interroger des instances geometry</span><span class="sxs-lookup"><span data-stu-id="8d352-102">Create, Construct, and Query geometry Instances</span></span>
  <span data-ttu-id="8d352-103">Le type de données spatiales planaire, `geometry`, représente les données dans un système de coordonnées euclidien (plat).</span><span class="sxs-lookup"><span data-stu-id="8d352-103">The planar spatial data type, `geometry`, represents data in a Euclidean (flat) coordinate system.</span></span> <span data-ttu-id="8d352-104">Ce type est implémenté en tant que type de données CLR (Common Language Runtime) dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d352-104">This type is implemented as a common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8d352-105">Le type `geometry` est prédéfini et disponible dans chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="8d352-105">The `geometry` type is predefined and available in each database.</span></span> <span data-ttu-id="8d352-106">Vous pouvez créer des colonnes de table de type `geometry` et opérer sur les données `geometry` comme vous le feriez avec d'autres types CLR.</span><span class="sxs-lookup"><span data-stu-id="8d352-106">You can create table columns of type `geometry` and operate on `geometry` data in the same manner as you would use other CLR types.</span></span>  
  
 <span data-ttu-id="8d352-107">Le type de données `geometry` (planaire) pris en charge par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est conforme à la spécification Open Geospatial Consortium (OGC) Simple Features for SQL version 1.1.0.</span><span class="sxs-lookup"><span data-stu-id="8d352-107">The `geometry` data type (planar) supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0.</span></span>  
  
 <span data-ttu-id="8d352-108">Pour plus d'informations sur les spécifications OGC, reportez-vous aux sites Web suivants :</span><span class="sxs-lookup"><span data-stu-id="8d352-108">For more information on OGC specifications, see the following:</span></span>  
  
-   [<span data-ttu-id="8d352-109">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span><span class="sxs-lookup"><span data-stu-id="8d352-109">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93628)  
  
-   [<span data-ttu-id="8d352-110">OGC Specifications, Simple Feature Access Part 2 - SQL Options</span><span class="sxs-lookup"><span data-stu-id="8d352-110">OGC Specifications, Simple Feature Access Part 2 - SQL Options</span></span>](https://go.microsoft.com/fwlink/?LinkId=93629)  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8d352-111">prend en charge un sous-ensemble de la norme GML 3.1, qui est définie dans le schéma suivant : [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span><span class="sxs-lookup"><span data-stu-id="8d352-111">supports a subset of the existing GML 3.1 standard which is defined in the following schema: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span></span>  
  
##  <a name="creating-or-constructing-a-new-geometry-instance"></a><a name="creating"></a> <span data-ttu-id="8d352-112">Création ou construction d'une nouvelle instance geometry</span><span class="sxs-lookup"><span data-stu-id="8d352-112">Creating or constructing a new geometry instance</span></span>  
  
###  <a name="creating-a-new-geometry-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="8d352-113">Création d'une instance geometry à partir d'une instance existante</span><span class="sxs-lookup"><span data-stu-id="8d352-113">Creating a New geometry Instance from an Existing Instance</span></span>  
 <span data-ttu-id="8d352-114">Le type de données `geometry` fournit de nombreuses méthodes intégrées que vous pouvez utiliser pour créer des instances `geometry` basées sur des instances existantes.</span><span class="sxs-lookup"><span data-stu-id="8d352-114">The `geometry` data type provides numerous built-in methods you can use to create new `geometry` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="8d352-115">**Pour créer une mémoire tampon autour d'une géométrie**</span><span class="sxs-lookup"><span data-stu-id="8d352-115">**To create a buffer around a geometry**</span></span>  
 [<span data-ttu-id="8d352-116">STBuffer &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-116">STBuffer &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stbuffer-geometry-data-type)  
  
 [<span data-ttu-id="8d352-117">BufferWithTolerance &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-117">BufferWithTolerance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/bufferwithtolerance-geometry-data-type)  
  
 <span data-ttu-id="8d352-118">**Pour créer une version simplifiée d'une géométrie**</span><span class="sxs-lookup"><span data-stu-id="8d352-118">**To create a simplified version of a geometry**</span></span>  
 [<span data-ttu-id="8d352-119">Reduce &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-119">Reduce &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/reduce-geometry-data-type)  
  
 <span data-ttu-id="8d352-120">**Pour créer la forme convexe d'une géométrie**</span><span class="sxs-lookup"><span data-stu-id="8d352-120">**To create the convex hull of a geometry**</span></span>  
 [<span data-ttu-id="8d352-121">STConvexHull &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-121">STConvexHull &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stconvexhull-geometry-data-type)  
  
 <span data-ttu-id="8d352-122">**Pour créer une géométrie à partir de l'intersection de deux géométries**</span><span class="sxs-lookup"><span data-stu-id="8d352-122">**To create a geometry from the intersection of two geometries**</span></span>  
 [<span data-ttu-id="8d352-123">STIntersection &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-123">STIntersection &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersection-geometry-data-type)  
  
 <span data-ttu-id="8d352-124">**Pour créer une géométrie à partir de l'union de deux géométries**</span><span class="sxs-lookup"><span data-stu-id="8d352-124">**To create a geometry from the union of two geometries**</span></span>  
 [<span data-ttu-id="8d352-125">STUnion &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-125">STUnion &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stunion-geometry-data-type)  
  
 <span data-ttu-id="8d352-126">**Pour créer une géométrie à partir des points où une géométrie n'en chevauche pas une autre**</span><span class="sxs-lookup"><span data-stu-id="8d352-126">**To create a geometry from the points where one geometry does not overlap another**</span></span>  
 [<span data-ttu-id="8d352-127">STDifference &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-127">STDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdifference-geometry-data-type)  
  
 <span data-ttu-id="8d352-128">**Pour créer une géométrie à partir des points où deux géométries ne se chevauchent pas**</span><span class="sxs-lookup"><span data-stu-id="8d352-128">**To create a geometry from the points where two geometries do not overlap**</span></span>  
 [<span data-ttu-id="8d352-129">STSymDifference &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-129">STSymDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stsymdifference-geometry-data-type)  
  
 <span data-ttu-id="8d352-130">**Pour créer une instance Point arbitraire qui repose sur une géométrie existante**</span><span class="sxs-lookup"><span data-stu-id="8d352-130">**To create an arbitrary Point instance that lies on an existing geometry**</span></span>  
 [<span data-ttu-id="8d352-131">STPointOnSurface &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-131">STPointOnSurface &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="8d352-132">Construction d'une instance geometry à partir d'une entrée WKT (Well-Known Text)</span><span class="sxs-lookup"><span data-stu-id="8d352-132">Constructing a geometry Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="8d352-133">Le type de données `geometry` fournit plusieurs méthodes intégrées qui génèrent une géométrie à partir de la représentation WKT OGC (Open Geospatial Consortium).</span><span class="sxs-lookup"><span data-stu-id="8d352-133">The `geometry` data type provides several built-in methods that generate a geometry from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="8d352-134">La norme WKT est une chaîne de texte qui autorise l'échange de données géométriques sous forme textuelle.</span><span class="sxs-lookup"><span data-stu-id="8d352-134">The WKT standard is a text string that allows geometry data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="8d352-135">**Pour construire tout type d'instance geometry à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="8d352-135">**To construct any type of geometry instance from WKT input**</span></span>  
 [<span data-ttu-id="8d352-136">STGeomFromText &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-136">STGeomFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type)  
  
 [<span data-ttu-id="8d352-137">Parse &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-137">Parse &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/parse-geometry-data-type)  
  
 <span data-ttu-id="8d352-138">**Pour construire une instance Point géométrique à partir d'entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="8d352-138">**To construct a geometry Point instance from WKT input**</span></span>  
 [<span data-ttu-id="8d352-139">STPointFromText &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-139">STPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="8d352-140">**Pour construire une instance MultiPoint geometry à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="8d352-140">**To construct a geometry MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="8d352-141">STMPointFromText &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-141">STMPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="8d352-142">**Pour construire une instance LineString geometry à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="8d352-142">**To construct a geometry LineString instance from WKT input**</span></span>  
 [<span data-ttu-id="8d352-143">STLineFromText &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-143">STLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="8d352-144">**Pour construire une instance MultiLineString geometry à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="8d352-144">**To construct a geometry MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="8d352-145">STMLineFromText &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-145">STMLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="8d352-146">**Pour construire une instance Polygon geometry à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="8d352-146">**To construct a geometry Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="8d352-147">STPolyFromText &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-147">STPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="8d352-148">**Pour construire une instance MultiPolygon geometry à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="8d352-148">**To construct a geometry MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="8d352-149">STMPolyFromText &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-149">STMPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="8d352-150">**Pour construire une instance GeometryCollection geometry à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="8d352-150">**To construct a geometry GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="8d352-151">STGeomCollFromText &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-151">STGeomCollFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromtext-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="8d352-152">Construction d'une instance geometry à partir d'une entrée WKB (Well-Known Binary)</span><span class="sxs-lookup"><span data-stu-id="8d352-152">Constructing a geometry Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="8d352-153">WKB est un format binaire spécifié par l'OGC (Open Geospatial Consortium) qui autorise l'échange de données de `geometry` entre une application cliente et une base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="8d352-153">WKB is a binary format specified by the Open Geospatial Consortium (OGC) that permits `geometry` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="8d352-154">Les fonctions suivantes acceptent l'entrée WKB pour construire des géométries :</span><span class="sxs-lookup"><span data-stu-id="8d352-154">The following functions accept WKB input to construct geometries:</span></span>  
  
 <span data-ttu-id="8d352-155">**Pour construire tout type d'instance geometry à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="8d352-155">**To construct any type of geometry instance from WKB input**</span></span>  
 [<span data-ttu-id="8d352-156">STGeomFromWKB &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-156">STGeomFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromwkb-geometry-data-type)  
  
 <span data-ttu-id="8d352-157">**Pour construire une instance Point geometry à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="8d352-157">**To construct a geometry Point instance from WKB input**</span></span>  
 [<span data-ttu-id="8d352-158">STPointFromWKB &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-158">STPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="8d352-159">**Pour construire une instance MultiPoint geometry à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="8d352-159">**To construct a geometry MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="8d352-160">STMPointFromWKB &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-160">STMPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="8d352-161">**Pour construire une instance LineString geometry à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="8d352-161">**To construct a geometry LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="8d352-162">STLineFromWKB &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-162">STLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="8d352-163">**Pour construire une instance MultiLineString geometry à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="8d352-163">**To construct a geometry MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="8d352-164">STMLineFromWKB &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-164">STMLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="8d352-165">**Pour construire une instance Polygon geometry à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="8d352-165">**To construct a geometry Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="8d352-166">STPolyFromWKB &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-166">STPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="8d352-167">**Pour construire une instance MultiPolygon geometry à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="8d352-167">**To construct a geometry MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="8d352-168">STMPolyFromWKB &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-168">STMPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="8d352-169">**Pour construire une instance GeometryCollection geometry à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="8d352-169">**To construct a geometry GeometryCollection instance from WKB input**</span></span>  
 [<span data-ttu-id="8d352-170">STGeomCollFromWKB &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-170">STGeomCollFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromwkb-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="8d352-171">Construction d'une instance geometry à partir d'une entrée texte GML</span><span class="sxs-lookup"><span data-stu-id="8d352-171">Constructing a geometry Instance from GML Text Input</span></span>  
 <span data-ttu-id="8d352-172">Le `geometry` type de données fournit une méthode qui génère une `geometry` instance à partir de GML, une représentation XML d’objets géométriques.</span><span class="sxs-lookup"><span data-stu-id="8d352-172">The `geometry` data type provides a method that generates a `geometry` instance from GML, an XML representation of geometric objects.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8d352-173">prend en charge un sous-ensemble de GML.</span><span class="sxs-lookup"><span data-stu-id="8d352-173">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="8d352-174">**Pour construire tout type d'instance geometry à partir d'une entrée GML**</span><span class="sxs-lookup"><span data-stu-id="8d352-174">**To construct any type of geometry instance from GML input**</span></span>  
 [<span data-ttu-id="8d352-175">GeomFromGml &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-175">GeomFromGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/geomfromgml-geometry-data-type)  
  
  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geometry-instance"></a><a name="returning"></a> <span data-ttu-id="8d352-176">Renvoi de données WKT et WKB à partir d'une instance geometry</span><span class="sxs-lookup"><span data-stu-id="8d352-176">Returning Well-Known Text and Well-Known Binary from a geometry Instance</span></span>  
 <span data-ttu-id="8d352-177">Vous pouvez utiliser les méthodes suivantes pour retourner le format WKT ou WKB d'une instance `geometry` :</span><span class="sxs-lookup"><span data-stu-id="8d352-177">You can use the following methods to return either the WKT or WKB format of a `geometry` instance:</span></span>  
  
 <span data-ttu-id="8d352-178">**Pour retourner la représentation WKT d'une instance geometry**</span><span class="sxs-lookup"><span data-stu-id="8d352-178">**To return the WKT representation of a geometry instance**</span></span>  
 [<span data-ttu-id="8d352-179">STAsText &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-179">STAsText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stastext-geometry-data-type)  
  
 [<span data-ttu-id="8d352-180">ToString &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-180">ToString &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/tostring-geometry-data-type)  
  
 <span data-ttu-id="8d352-181">**Pour retourner la représentation WKT d'une instance geometry incluant des valeurs Z et M**</span><span class="sxs-lookup"><span data-stu-id="8d352-181">**To return the WKT representation of a geometry instance including any Z and M values**</span></span>  
 [<span data-ttu-id="8d352-182">AsTextZM &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-182">AsTextZM &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/astextzm-geometry-data-type)  
  
 <span data-ttu-id="8d352-183">**Pour retourner la représentation WKB d'une instance geometry**</span><span class="sxs-lookup"><span data-stu-id="8d352-183">**To return the WKB representation of a geometry instance**</span></span>  
 [<span data-ttu-id="8d352-184">STAsBinary &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-184">STAsBinary &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stasbinary-geometry-data-type)  
  
 <span data-ttu-id="8d352-185">**Pour retourner une représentation GML d'une instance geometry**</span><span class="sxs-lookup"><span data-stu-id="8d352-185">**To return a GML representation of a geometry instance**</span></span>  
 [<span data-ttu-id="8d352-186">AsGml &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-186">AsGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/asgml-geometry-data-type)  
  
  
  
##  <a name="querying-the-properties-and-behaviors-of-geometry-instances"></a><a name="querying"></a> <span data-ttu-id="8d352-187">Interrogation des propriétés et comportements des instances geometry</span><span class="sxs-lookup"><span data-stu-id="8d352-187">Querying the Properties and Behaviors of geometry Instances</span></span>  
 <span data-ttu-id="8d352-188">Toutes les `geometry` instances ont un certain nombre de propriétés qui peuvent être récupérées par le biais des méthodes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournies par.</span><span class="sxs-lookup"><span data-stu-id="8d352-188">All `geometry` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="8d352-189">Les rubriques suivantes définissent les propriétés et comportements de types geometry et les méthodes permettant de les interroger.</span><span class="sxs-lookup"><span data-stu-id="8d352-189">The following topics define the properties and behaviors of geometry types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="8d352-190">Informations sur la validité, le type d'instance et GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="8d352-190">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="8d352-191">Une fois qu'une instance `geometry` est construite, vous pouvez utiliser les méthodes suivantes pour déterminer si elle est formée correctement, retourner le type d'instance ou, s'il s'agit d'une instance de collection, retourner une instance `geometry` spécifique.</span><span class="sxs-lookup"><span data-stu-id="8d352-191">Once a `geometry` instance is constructed, you can use the following methods to determine if it is well-formed, return the instance type, or, if it is a collection instance, return a specific `geometry` instance.</span></span>  
  
 <span data-ttu-id="8d352-192">**Pour retourner le type d'instance d'une géométrie**</span><span class="sxs-lookup"><span data-stu-id="8d352-192">**To return the instance type of a geometry**</span></span>  
 [<span data-ttu-id="8d352-193">STGeometryType &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-193">STGeometryType &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeometrytype-geometry-data-type)  
  
 <span data-ttu-id="8d352-194">**Pour déterminer si une géométrie est un type d'instance donné**</span><span class="sxs-lookup"><span data-stu-id="8d352-194">**To determine if a geometry is a given instance type**</span></span>  
 [<span data-ttu-id="8d352-195">InstanceOf &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-195">InstanceOf &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/instanceof-geometry-data-type)  
  
 <span data-ttu-id="8d352-196">**Pour déterminer si une instance geometry est de forme correcte pour son type d'instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-196">**To determine if a geometry instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="8d352-197">STIsValid &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-197">STIsValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)  
  
 <span data-ttu-id="8d352-198">**Pour convertir une instance geometry en une instance geometry de forme correcte avec un type d'instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-198">**To convert a geometry instance to a well-formed geometry instance with an instance type**</span></span>  
 [<span data-ttu-id="8d352-199">MakeValid &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-199">MakeValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type)  
  
 <span data-ttu-id="8d352-200">**Pour retourner le nombre de géométries dans une instance de collection geometry**</span><span class="sxs-lookup"><span data-stu-id="8d352-200">**To return the number of geometries in a geometry collection instance**</span></span>  
 [<span data-ttu-id="8d352-201">STNumGeometries &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-201">STNumGeometries &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumgeometries-geometry-data-type)  
  
 <span data-ttu-id="8d352-202">Pour retourner une géométrie spécifique dans une instance de collection géométrique</span><span class="sxs-lookup"><span data-stu-id="8d352-202">To return a specific geometry in a geometry collection instance</span></span>  
 <span data-ttu-id="8d352-203">[STGeometryN &#40;type de données geometry&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (type de données geometry)</span><span class="sxs-lookup"><span data-stu-id="8d352-203">[STGeometryN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (geometry Data type)</span></span>  
  
  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="8d352-204">Nombre de points</span><span class="sxs-lookup"><span data-stu-id="8d352-204">Number of Points</span></span>  
 <span data-ttu-id="8d352-205">Toutes les instances non vides `geometry` sont constituées de *points*.</span><span class="sxs-lookup"><span data-stu-id="8d352-205">All nonempty `geometry` instances are comprised of *points*.</span></span> <span data-ttu-id="8d352-206">Ces points représentent les coordonnées X et Y de latitude et de longitude du plan sur lequel les géométries sont dessinées.</span><span class="sxs-lookup"><span data-stu-id="8d352-206">These points represent the X- and Y-coordinates of the plane on which the geometries are drawn.</span></span> <span data-ttu-id="8d352-207">`geometry` fournit de nombreuses méthodes intégrées pour interroger les points d'une instance.</span><span class="sxs-lookup"><span data-stu-id="8d352-207">`geometry` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="8d352-208">**Pour retourner le nombre de points qui composent une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-208">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="8d352-209">STNumPoints &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-209">STNumPoints &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type)  
  
 <span data-ttu-id="8d352-210">**Pour retourner un point spécifique dans une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-210">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="8d352-211">STPointN</span><span class="sxs-lookup"><span data-stu-id="8d352-211">STPointN</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="8d352-212">**Pour retourner un point arbitraire qui repose sur une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-212">**To return an arbitrary point that lies on an instance**</span></span>  
 [<span data-ttu-id="8d352-213">STPointOnSurface</span><span class="sxs-lookup"><span data-stu-id="8d352-213">STPointOnSurface</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
 <span data-ttu-id="8d352-214">**Pour retourner le point de départ d'une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-214">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="8d352-215">STStartPoint</span><span class="sxs-lookup"><span data-stu-id="8d352-215">STStartPoint</span></span>](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type)  
  
 <span data-ttu-id="8d352-216">**Pour retourner le point de terminaison d'une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-216">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="8d352-217">STEndpoint</span><span class="sxs-lookup"><span data-stu-id="8d352-217">STEndpoint</span></span>](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type)  
  
 <span data-ttu-id="8d352-218">**Pour retourner la coordonnée X d'une instance Point**</span><span class="sxs-lookup"><span data-stu-id="8d352-218">**To return the X-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="8d352-219">STX &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-219">STX &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stx-geometry-data-type)  
  
 <span data-ttu-id="8d352-220">**Pour retourner la coordonnée Y d'une instance Point**</span><span class="sxs-lookup"><span data-stu-id="8d352-220">**To return the Y-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="8d352-221">STY</span><span class="sxs-lookup"><span data-stu-id="8d352-221">STY</span></span>](/sql/t-sql/spatial-geometry/sty-geometry-data-type)  
  
 <span data-ttu-id="8d352-222">**Pour retourner le point central géométrique d'une instance Polygone, CurvePolygon ou MultiPolygon**</span><span class="sxs-lookup"><span data-stu-id="8d352-222">**To return the geometric center point of a Polygon, CurvePolygon, or MultiPolygon instance**</span></span>  
 [<span data-ttu-id="8d352-223">STCentroid</span><span class="sxs-lookup"><span data-stu-id="8d352-223">STCentroid</span></span>](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type)  
  
  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="8d352-224">Dimension</span><span class="sxs-lookup"><span data-stu-id="8d352-224">Dimension</span></span>  
 <span data-ttu-id="8d352-225">Une instance `geometry` non vide peut avoir 0, 1 ou 2 dimensions.</span><span class="sxs-lookup"><span data-stu-id="8d352-225">A nonempty `geometry` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="8d352-226">Les `geometries` à zéro dimension, telles que `Point` et `MultiPoint`, n'ont aucune longueur ou surface.</span><span class="sxs-lookup"><span data-stu-id="8d352-226">Zero-dimensional `geometries`, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="8d352-227">Les objets unidimensionnels, tels que `LineString, CircularString, CompoundCurve` et `MultiLineString`, ont une longueur.</span><span class="sxs-lookup"><span data-stu-id="8d352-227">One-dimensional objects, such as `LineString, CircularString, CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="8d352-228">Les instances à deux dimensions, telles que `Polygon`, `CurvePolygon` et `MultiPolygon`, ont une surface et une longueur.</span><span class="sxs-lookup"><span data-stu-id="8d352-228">Two-dimensional instances, such as `Polygon`, `CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="8d352-229">Les instances vides indiquent une dimension de -1 et une `GeometryCollection` indique une surface dépendant des types de son contenu.</span><span class="sxs-lookup"><span data-stu-id="8d352-229">Empty instances will report a dimension of -1, and a `GeometryCollection` will report an area dependent on the types of its contents.</span></span>  
  
 <span data-ttu-id="8d352-230">**Pour retourner la dimension d'une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-230">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="8d352-231">STDimension</span><span class="sxs-lookup"><span data-stu-id="8d352-231">STDimension</span></span>](/sql/t-sql/spatial-geometry/stdimension-geometry-data-type)  
  
 <span data-ttu-id="8d352-232">**Pour retourner la longueur d'une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-232">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="8d352-233">STLength</span><span class="sxs-lookup"><span data-stu-id="8d352-233">STLength</span></span>](/sql/t-sql/spatial-geometry/stlength-geometry-data-type)  
  
 <span data-ttu-id="8d352-234">**Pour retourner la surface d'une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-234">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="8d352-235">STArea</span><span class="sxs-lookup"><span data-stu-id="8d352-235">STArea</span></span>](/sql/t-sql/spatial-geometry/starea-geometry-data-type)  
  
  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="8d352-236">Vide</span><span class="sxs-lookup"><span data-stu-id="8d352-236">Empty</span></span>  
 <span data-ttu-id="8d352-237">Une instance *vide* `geometry` n’a aucun point.</span><span class="sxs-lookup"><span data-stu-id="8d352-237">An *empty*`geometry` instance does not have any points.</span></span> <span data-ttu-id="8d352-238">La longueur des instances `LineString, CircularString`, `CompoundCurve` et `MultiLineString` vides est nulle.</span><span class="sxs-lookup"><span data-stu-id="8d352-238">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is zero.</span></span> <span data-ttu-id="8d352-239">La surface des instances `Polygon`, `CurvePolygon` et `MultiPolygon` vides est 0.</span><span class="sxs-lookup"><span data-stu-id="8d352-239">The area of empty `Polygon`, `CurvePolygon`, and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="8d352-240">**Pour déterminer si une instance est vide**</span><span class="sxs-lookup"><span data-stu-id="8d352-240">**To determine if an instance is empty**</span></span>  
 <span data-ttu-id="8d352-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="8d352-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span></span>  
  
  
  
###  <a name="simple"></a><a name="simple"></a> <span data-ttu-id="8d352-242">Simple</span><span class="sxs-lookup"><span data-stu-id="8d352-242">Simple</span></span>  
 <span data-ttu-id="8d352-243">Pour `geometry` qu’une de l’instance soit *simple*, elle doit remplir les deux conditions requises suivantes :</span><span class="sxs-lookup"><span data-stu-id="8d352-243">For a `geometry` of the instance to be *simple*, it must meet both of these requirements:</span></span>  
  
-   <span data-ttu-id="8d352-244">Chaque graphique de l'instance ne doit pas se croiser lui-même, sauf à ses points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="8d352-244">Each figure of the instance must not intersect itself, except at its endpoints.</span></span>  
  
-   <span data-ttu-id="8d352-245">Deux graphiques de l'instance ne peuvent se croiser l'un l'autre à un point qui n'est pas dans leurs limites.</span><span class="sxs-lookup"><span data-stu-id="8d352-245">No two figures of the instance can intersect each other at a point that is not in both of their boundaries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d352-246">Les géométries vides sont toujours simples.</span><span class="sxs-lookup"><span data-stu-id="8d352-246">Empty geometries are always simple.</span></span>  
  
 <span data-ttu-id="8d352-247">**Pour déterminer si une instance est simple**</span><span class="sxs-lookup"><span data-stu-id="8d352-247">**To determine if an instance is simple**</span></span>  
 <span data-ttu-id="8d352-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="8d352-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span></span>  
  
  
  
###  <a name="boundary-interior-and-exterior"></a><a name="boundary"></a> <span data-ttu-id="8d352-249">Limite, intérieur et extérieur</span><span class="sxs-lookup"><span data-stu-id="8d352-249">Boundary, Interior, and Exterior</span></span>  
 <span data-ttu-id="8d352-250">L' *intérieur* d’une `geometry` instance est l’espace occupé par l’instance et l' *extérieur* est l’espace qui n’est pas occupé.</span><span class="sxs-lookup"><span data-stu-id="8d352-250">The *interior* of a `geometry` instance is the space occupied by the instance, and the *exterior* is the space not occupied it.</span></span>  
  
 <span data-ttu-id="8d352-251">Une limite (*Boudary* à est définie par l’OGC comme suit :</span><span class="sxs-lookup"><span data-stu-id="8d352-251">*Boundary* is defined by the OGC as follows:</span></span>  
  
-   <span data-ttu-id="8d352-252">Les instances `Point` et `MultiPoint` n'ont pas de limite.</span><span class="sxs-lookup"><span data-stu-id="8d352-252">`Point` and `MultiPoint` instances do not have a boundary.</span></span>  
  
-   <span data-ttu-id="8d352-253">Les limites de `LineString` et `MultiLineString` sont formées par les points de départ et points de terminaison, en supprimant ceux qui ont lieu un nombre pair de fois.</span><span class="sxs-lookup"><span data-stu-id="8d352-253">`LineString` and `MultiLineString` boundaries are formed by the start points and end points, removing those that occur an even number of times.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 1, 0 0, 1 0, 0 1), (1 1, 1 0))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="8d352-254">La limite d'une instance `Polygon` ou `MultiPolygon` est l'ensemble de ses anneaux.</span><span class="sxs-lookup"><span data-stu-id="8d352-254">The boundary of a `Polygon` or `MultiPolygon` instance is the set of its rings.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0), (1 1, 1 2, 2 2, 2 1, 1 1))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="8d352-255">**Pour retourner la limite d'une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-255">**To return the boundary of an instance**</span></span>  
 [<span data-ttu-id="8d352-256">STBoundary</span><span class="sxs-lookup"><span data-stu-id="8d352-256">STBoundary</span></span>](/sql/t-sql/spatial-geometry/stboundary-geometry-data-type)  
  
  
  
###  <a name="envelope"></a><a name="envelope"></a> <span data-ttu-id="8d352-257">Enveloppe</span><span class="sxs-lookup"><span data-stu-id="8d352-257">Envelope</span></span>  
 <span data-ttu-id="8d352-258">L' *enveloppe* d’une `geometry` instance, également appelée *zone englobante*, est le rectangle aligné sur l’axe formé par les coordonnées minimales et maximales (X, Y) de l’instance.</span><span class="sxs-lookup"><span data-stu-id="8d352-258">The *envelope* of a `geometry` instance, also known as the *bounding box*, is the axis-aligned rectangle formed by the minimum and maximum (X,Y) coordinates of the instance.</span></span>  
  
 <span data-ttu-id="8d352-259">**Pour retourner l'enveloppe d'une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-259">**To return the envelope of an instance**</span></span>  
 [<span data-ttu-id="8d352-260">STEnvelope</span><span class="sxs-lookup"><span data-stu-id="8d352-260">STEnvelope</span></span>](/sql/t-sql/spatial-geometry/stenvelope-geometry-data-type)  
  
  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="8d352-261">Fermeture</span><span class="sxs-lookup"><span data-stu-id="8d352-261">Closure</span></span>  
 <span data-ttu-id="8d352-262">Une instance *fermée* `geometry` est une figure dont les points de début et de fin sont identiques.</span><span class="sxs-lookup"><span data-stu-id="8d352-262">A *closed*`geometry` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="8d352-263">Les instances `Polygon` sont considérées comme fermées.</span><span class="sxs-lookup"><span data-stu-id="8d352-263">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="8d352-264">Les instances `Point` ne sont pas fermées.</span><span class="sxs-lookup"><span data-stu-id="8d352-264">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="8d352-265">Un anneau est une instance `LineString` simple et fermée.</span><span class="sxs-lookup"><span data-stu-id="8d352-265">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="8d352-266">**Pour déterminer si une instance est fermée**</span><span class="sxs-lookup"><span data-stu-id="8d352-266">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="8d352-267">STIsClosed</span><span class="sxs-lookup"><span data-stu-id="8d352-267">STIsClosed</span></span>](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type)  
  
 <span data-ttu-id="8d352-268">**Pour déterminer si une instance est un anneau**</span><span class="sxs-lookup"><span data-stu-id="8d352-268">**To determine if an instance is a ring**</span></span>  
 [<span data-ttu-id="8d352-269">STIsRing</span><span class="sxs-lookup"><span data-stu-id="8d352-269">STIsRing</span></span>](/sql/t-sql/spatial-geometry/stisring-geometry-data-type)  
  
 <span data-ttu-id="8d352-270">**Pour retourner l'anneau extérieur d'une instance Polygon**</span><span class="sxs-lookup"><span data-stu-id="8d352-270">**To return the exterior ring of a Polygon instance**</span></span>  
 [<span data-ttu-id="8d352-271">STExteriorRing</span><span class="sxs-lookup"><span data-stu-id="8d352-271">STExteriorRing</span></span>](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type)  
  
 <span data-ttu-id="8d352-272">**Pour retourner le nombre d'anneaux intérieurs dans un Polygon**</span><span class="sxs-lookup"><span data-stu-id="8d352-272">**To return the number of interior rings in a Polygon**</span></span>  
 [<span data-ttu-id="8d352-273">STNumInteriorRing</span><span class="sxs-lookup"><span data-stu-id="8d352-273">STNumInteriorRing</span></span>](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type)  
  
 <span data-ttu-id="8d352-274">**Pour retourner un anneau intérieur spécifié d'un Polygon**</span><span class="sxs-lookup"><span data-stu-id="8d352-274">**To return a specified interior ring of a Polygon**</span></span>  
 [<span data-ttu-id="8d352-275">STInteriorRingN</span><span class="sxs-lookup"><span data-stu-id="8d352-275">STInteriorRingN</span></span>](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type)  
  
  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="8d352-276">ID de référence spatial (SRID)</span><span class="sxs-lookup"><span data-stu-id="8d352-276">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="8d352-277">L'ID de référence spatial (SRID) est un identificateur spécifiant dans quel système de coordonnées l'instance `geometry` est représentée.</span><span class="sxs-lookup"><span data-stu-id="8d352-277">The spatial reference ID (SRID) is an identifier specifying which coordinate system the `geometry` instance is represented in.</span></span> <span data-ttu-id="8d352-278">Deux instances avec différents SRID ne peuvent pas être comparées.</span><span class="sxs-lookup"><span data-stu-id="8d352-278">Two instances with different SRIDs are incomparable.</span></span>  
  
 <span data-ttu-id="8d352-279">**Pour définir ou retourner le SRID d'une instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-279">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="8d352-280">STSrid</span><span class="sxs-lookup"><span data-stu-id="8d352-280">STSrid</span></span>](/sql/t-sql/spatial-geometry/stsrid-geometry-data-type)  
  
 <span data-ttu-id="8d352-281">Cette propriété peut être modifiée.</span><span class="sxs-lookup"><span data-stu-id="8d352-281">This property can be modified.</span></span>  
  
  
  
##  <a name="determining-relationships-between-geometry-instances"></a><a name="rel"></a> <span data-ttu-id="8d352-282">Détermination de relations entre des instances geometry</span><span class="sxs-lookup"><span data-stu-id="8d352-282">Determining Relationships between geometry Instances</span></span>  
 <span data-ttu-id="8d352-283">Le type de données `geometry` fournit de nombreuses méthodes intégrées que vous pouvez utiliser pour déterminer les relations entre deux instances `geometry`.</span><span class="sxs-lookup"><span data-stu-id="8d352-283">The `geometry` data type provides many built-in methods you can use to determine relationships between two `geometry` instances.</span></span>  
  
 <span data-ttu-id="8d352-284">**Pour déterminer si deux instances comprennent le même ensemble de points**</span><span class="sxs-lookup"><span data-stu-id="8d352-284">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="8d352-285">STEquals</span><span class="sxs-lookup"><span data-stu-id="8d352-285">STEquals</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="8d352-286">**Pour déterminer si deux instances sont disjointes**</span><span class="sxs-lookup"><span data-stu-id="8d352-286">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="8d352-287">STDisjoint</span><span class="sxs-lookup"><span data-stu-id="8d352-287">STDisjoint</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="8d352-288">**Pour déterminer si deux instances se croisent**</span><span class="sxs-lookup"><span data-stu-id="8d352-288">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="8d352-289">STIntersects</span><span class="sxs-lookup"><span data-stu-id="8d352-289">STIntersects</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="8d352-290">**Pour déterminer si deux instances se touchent**</span><span class="sxs-lookup"><span data-stu-id="8d352-290">**To determine if two instances touch**</span></span>  
 [<span data-ttu-id="8d352-291">STTouches</span><span class="sxs-lookup"><span data-stu-id="8d352-291">STTouches</span></span>](/sql/t-sql/spatial-geometry/sttouches-geometry-data-type)  
  
 <span data-ttu-id="8d352-292">**Pour déterminer si deux instances se chevauchent**</span><span class="sxs-lookup"><span data-stu-id="8d352-292">**To determine if two instances overlap**</span></span>  
 [<span data-ttu-id="8d352-293">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="8d352-293">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="8d352-294">**Pour déterminer si deux instances se croisent**</span><span class="sxs-lookup"><span data-stu-id="8d352-294">**To determine if two instances cross**</span></span>  
 [<span data-ttu-id="8d352-295">STCrosses</span><span class="sxs-lookup"><span data-stu-id="8d352-295">STCrosses</span></span>](/sql/t-sql/spatial-geometry/stcrosses-geometry-data-type)  
  
 <span data-ttu-id="8d352-296">**Pour déterminer si une instance est dans une autre instance**</span><span class="sxs-lookup"><span data-stu-id="8d352-296">**To determine if one instance is within another**</span></span>  
 [<span data-ttu-id="8d352-297">STWithin</span><span class="sxs-lookup"><span data-stu-id="8d352-297">STWithin</span></span>](/sql/t-sql/spatial-geometry/stwithin-geometry-data-type)  
  
 <span data-ttu-id="8d352-298">**Pour déterminer si une instance en contient une autre**</span><span class="sxs-lookup"><span data-stu-id="8d352-298">**To determine if one instance contains another**</span></span>  
 [<span data-ttu-id="8d352-299">STContains</span><span class="sxs-lookup"><span data-stu-id="8d352-299">STContains</span></span>](/sql/t-sql/spatial-geometry/stcontains-geometry-data-type)  
  
 <span data-ttu-id="8d352-300">**Pour déterminer si une instance en chevauche une autre**</span><span class="sxs-lookup"><span data-stu-id="8d352-300">**To determine if one instance overlaps another**</span></span>  
 [<span data-ttu-id="8d352-301">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="8d352-301">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="8d352-302">**Pour déterminer si deux instances sont liées spatialement**</span><span class="sxs-lookup"><span data-stu-id="8d352-302">**To determine if two instances are spatially related**</span></span>  
 [<span data-ttu-id="8d352-303">STRelate</span><span class="sxs-lookup"><span data-stu-id="8d352-303">STRelate</span></span>](/sql/t-sql/spatial-geometry/strelate-geometry-data-type)  
  
 <span data-ttu-id="8d352-304">**Pour déterminer la distance la plus courte entre des points dans deux géométries**</span><span class="sxs-lookup"><span data-stu-id="8d352-304">**To determine the shortest distance between points in two geometries**</span></span>  
 [<span data-ttu-id="8d352-305">STDistance</span><span class="sxs-lookup"><span data-stu-id="8d352-305">STDistance</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
  
  
##  <a name="geometry-instances-default-to-zero-srid"></a><a name="defaultsrid"></a> <span data-ttu-id="8d352-306">Les instances geometry ont un SRID par défaut de zéro</span><span class="sxs-lookup"><span data-stu-id="8d352-306">geometry Instances Default to Zero SRID</span></span>  
 <span data-ttu-id="8d352-307">Le SRID par défaut pour les instances `geometry` dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est 0.</span><span class="sxs-lookup"><span data-stu-id="8d352-307">The default SRID for `geometry` instances in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 0.</span></span> <span data-ttu-id="8d352-308">Avec les données spatiales `geometry`, le SRID spécifique de l'instance spatiale n'est pas requis pour effectuer des calculs ; par conséquent, les instances peuvent résider dans un espace planaire indéfini.</span><span class="sxs-lookup"><span data-stu-id="8d352-308">With `geometry` spatial data, the specific SRID of the spatial instance is not required to perform calculations; thus, instances can reside in undefined planar space.</span></span> <span data-ttu-id="8d352-309">Pour indiquer un espace planaire indéfini dans les calculs de méthodes de type de données `geometry`, le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utilise SRID 0.</span><span class="sxs-lookup"><span data-stu-id="8d352-309">To indicate undefined planar space in the calculations of `geometry` data type methods, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses SRID 0.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="8d352-310">Exemples</span><span class="sxs-lookup"><span data-stu-id="8d352-310">Examples</span></span>  
 <span data-ttu-id="8d352-311">Les deux exemples suivants montrent comment ajouter et interroger des données géométriques.</span><span class="sxs-lookup"><span data-stu-id="8d352-311">The following two examples show how to add and query geometry data.</span></span>  
  
-   <span data-ttu-id="8d352-312">Le premier exemple crée une table avec une colonne d'identité et une colonne `geometry``GeomCol1`.</span><span class="sxs-lookup"><span data-stu-id="8d352-312">The first example creates a table with an identity column and a `geometry` column `GeomCol1`.</span></span> <span data-ttu-id="8d352-313">Une troisième colonne restitue la colonne `geometry` dans sa représentation OGC (Open Geospatial Consortium) WKT (Well-Known Text) et utilise la méthode `STAsText()` .</span><span class="sxs-lookup"><span data-stu-id="8d352-313">A third column renders the `geometry` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="8d352-314">Deux lignes sont ensuite insérées : une ligne contient une instance `LineString` de `geometry`et une ligne contient une instance `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="8d352-314">Two rows are then inserted: one row contains a `LineString` instance of `geometry`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeomCol1 geometry,   
        GeomCol2 AS GeomCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('LINESTRING (100 100, 20 180, 180 180)', 0));  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('POLYGON ((0 0, 150 0, 150 150, 0 150, 0 0))', 0));  
    GO  
    ```  
  
-   <span data-ttu-id="8d352-315">Le deuxième exemple utilise la méthode `STIntersection()` pour retourner les points où les deux instances `geometry` précédemment insérées se croisent.</span><span class="sxs-lookup"><span data-stu-id="8d352-315">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geometry` instances intersect.</span></span>  
  
    ```  
    DECLARE @geom1 geometry;  
    DECLARE @geom2 geometry;  
    DECLARE @result geometry;  
  
    SELECT @geom1 = GeomCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geom2 = GeomCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geom1.STIntersection(@geom2);  
    SELECT @result.STAsText();  
    ```  
  
  
  
## <a name="see-also"></a><span data-ttu-id="8d352-316">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d352-316">See Also</span></span>  
 [<span data-ttu-id="8d352-317">Données spatiales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8d352-317">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
