---
title: Créer, construire et interroger des instances geography | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server]
- geodetic data type [SQL Server]
- geography data type [SQL Server], about geography data type
ms.assetid: b585851e-d15b-411f-adeb-aeabeb777c0b
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: d744457cc517a6172cca96b27eae1f456deca24e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601309"
---
# <a name="create-construct-and-query-geography-instances"></a><span data-ttu-id="ea8c4-102">Créer, construire et interroger des instances geography</span><span class="sxs-lookup"><span data-stu-id="ea8c4-102">Create, Construct, and Query geography Instances</span></span>
  <span data-ttu-id="ea8c4-103">Le type de données spatiales géographiques, `geography`, représente des données dans un système de coordonnées de monde sphérique.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-103">The geography spatial data type, `geography`, represents data in a round-earth coordinate system.</span></span> <span data-ttu-id="ea8c4-104">Ce type est implémenté en tant que type de données CLR (Common Language Runtime) .NET dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea8c4-104">This type is implemented as a .NET common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ea8c4-105">Type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` qui stocke des données ellipsoïdales, telles que des coordonnées de latitude et de longitude GPS.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` data type stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>  
  
 <span data-ttu-id="ea8c4-106">Le type `geography` est prédéfini et disponible dans chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-106">The `geography` type is predefined and available in each database.</span></span> <span data-ttu-id="ea8c4-107">Vous pouvez créer des colonnes de table de type `geography` et opérer sur les données `geography` comme vous le feriez avec d'autres types fournis par le système.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-107">You can create table columns of type `geography` and operate on `geography` data in the same manner as you would use other system-supplied types.</span></span>  
  
##  <a name="creating-or-constructing-a-new-geography-instance"></a><a name="creating"></a> <span data-ttu-id="ea8c4-108">Création ou construction d'une nouvelle instance geography</span><span class="sxs-lookup"><span data-stu-id="ea8c4-108">Creating or constructing a new geography instance</span></span>  
  
###  <a name="creating-a-new-geography-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="ea8c4-109">Création d'une nouvelle instance geography à partir d'une instance existante</span><span class="sxs-lookup"><span data-stu-id="ea8c4-109">Creating a New geography Instance from an Existing Instance</span></span>  
 <span data-ttu-id="ea8c4-110">Le type de données `geography` fournit de nombreuses méthodes intégrées que vous pouvez utiliser pour créer des instances `geography` basées sur des instances existantes.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-110">The `geography` data type provides numerous built-in methods you can use to create new `geography` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="ea8c4-111">**Pour créer une mémoire tampon autour d'une géographie**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-111">**To create a buffer around a geography**</span></span>  
 [<span data-ttu-id="ea8c4-112">STBuffer &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-112">STBuffer &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stbuffer-geography-data-type)  
  
 <span data-ttu-id="ea8c4-113">**Pour créer une mémoire tampon autour d'une géographie, en tenant compte d'une tolérance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-113">**To create a buffer around a geography, allowing for a tolerance**</span></span>  
 [<span data-ttu-id="ea8c4-114">BufferWithTolerance &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-114">BufferWithTolerance &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/bufferwithtolerance-geography-data-type)  
  
 <span data-ttu-id="ea8c4-115">**Pour créer une géographie à partir de l'intersection de deux instances géographiques**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-115">**To create a geography from the intersection of two geography instances**</span></span>  
 [<span data-ttu-id="ea8c4-116">STIntersection &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-116">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="ea8c4-117">**Pour créer une géographie à partir de l'union de deux instances géographiques**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-117">**To create a geography from the union of two geography instances**</span></span>  
 [<span data-ttu-id="ea8c4-118">STUnion &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-118">STUnion &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stunion-geography-data-type)  
  
 <span data-ttu-id="ea8c4-119">**Pour créer une géographie à partir des points où une géographie n'en chevauche pas une autre**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-119">**To create a geography from the points where one geography does not overlap another**</span></span>  
 [<span data-ttu-id="ea8c4-120">STDifference &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-120">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="ea8c4-121">Construction d'une instance geography à partir d'une entrée WKT (Well-Known Text)</span><span class="sxs-lookup"><span data-stu-id="ea8c4-121">Constructing a geography Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="ea8c4-122">Le type de données `geography` fournit plusieurs méthodes intégrées qui génèrent une géographie à partir de la représentation WKT OGC (Open Geospatial Consortium).</span><span class="sxs-lookup"><span data-stu-id="ea8c4-122">The `geography` data type provides several built-in methods that generate a geography from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="ea8c4-123">La norme WKT est une chaîne de texte qui autorise l'échange de données geography sous forme textuelle.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-123">The WKT standard is a text string that allows geography data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="ea8c4-124">**Pour construire tout type d'instance geography à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-124">**To construct any type of geography instance from WKT input**</span></span>  
 [<span data-ttu-id="ea8c4-125">STGeomFromText &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-125">STGeomFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)  
  
 [<span data-ttu-id="ea8c4-126">Parse &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-126">Parse &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/parse-geography-data-type)  
  
 <span data-ttu-id="ea8c4-127">**Pour construire une instance Point geography à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-127">**To construct a geography Point instance from WKT input**</span></span>  
 [<span data-ttu-id="ea8c4-128">STPointFromText &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-128">STPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromtext-geography-data-type)  
  
 <span data-ttu-id="ea8c4-129">**Pour construire une instance MultiPoint geography à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-129">**To construct a geography MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="ea8c4-130">STMPointFromText &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-130">STMPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromtext-geography-data-type)  
  
 <span data-ttu-id="ea8c4-131">**Pour construire une instance LineString geography à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-131">**To construct a geography LineString instance from WKT input**</span></span>  
 <span data-ttu-id="ea8c4-132">STLineFromText (type de données geography)</span><span class="sxs-lookup"><span data-stu-id="ea8c4-132">STLineFromText (geography Data Type)</span></span>  
  
 <span data-ttu-id="ea8c4-133">**Pour construire une instance MultiLineString geography à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-133">**To construct a geography MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="ea8c4-134">STMLineFromText &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-134">STMLineFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromtext-geography-data-type)  
  
 <span data-ttu-id="ea8c4-135">**Pour construire une instance Polygon geography à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-135">**To construct a geography Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="ea8c4-136">STPolyFromText &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-136">STPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="ea8c4-137">**Pour construire une instance MultiPolygon geography à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-137">**To construct a geography MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="ea8c4-138">STMPolyFromText &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-138">STMPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="ea8c4-139">**Pour construire une instance GeometryCollection geography à partir d'une entrée WKT**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-139">**To construct a geography GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="ea8c4-140">STGeomCollFromText &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-140">STGeomCollFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomcollfromtext-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="ea8c4-141">Construction d'une instance geography à partir d'une entrée WKB (Well-Known Binary)</span><span class="sxs-lookup"><span data-stu-id="ea8c4-141">Constructing a geography Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="ea8c4-142">WKB est un format binaire spécifié par l'OGC qui autorise l'échange de données de `Geography` entre une application cliente et une base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-142">WKB is a binary format specified by the OGC that permits `Geography` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="ea8c4-143">Les fonctions suivantes acceptent l'entrée WKB pour construire des instances geography :</span><span class="sxs-lookup"><span data-stu-id="ea8c4-143">The following functions accept WKB input to construct geography instances:</span></span>  
  
 <span data-ttu-id="ea8c4-144">**Pour construire tout type d'instance geography à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-144">**To construct any type of geography instance from WKB input**</span></span>  
 [<span data-ttu-id="ea8c4-145">STGeomFromWKB &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-145">STGeomFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromwkb-geography-data-type)  
  
 <span data-ttu-id="ea8c4-146">**Pour construire une instance Point geography à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-146">**To construct a geography Point instance from WKB input**</span></span>  
 [<span data-ttu-id="ea8c4-147">STPointFromWKB &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-147">STPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="ea8c4-148">**Pour construire une instance MultiPoint geography à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-148">**To construct a geography MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="ea8c4-149">STMPointFromWKB &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-149">STMPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="ea8c4-150">**Pour construire une instance LineString geography à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-150">**To construct a geography LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="ea8c4-151">STLineFromWKB &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-151">STLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="ea8c4-152">**Pour construire une instance MultiLineString geography à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-152">**To construct a geography MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="ea8c4-153">STMLineFromWKB &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-153">STMLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="ea8c4-154">**Pour construire une instance Polygon geography à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-154">**To construct a geography Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="ea8c4-155">STPolyFromWKB &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-155">STPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="ea8c4-156">**Pour construire une instance MultiPolygon geography à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-156">**To construct a geography MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="ea8c4-157">STMPolyFromWKB &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-157">STMPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="ea8c4-158">**Pour construire une instance GeometryCollection geography à partir d'une entrée WKB**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-158">**To construct a geography GeometryCollection instance from WKB input**</span></span>  
 <span data-ttu-id="ea8c4-159">[STGeomCollFromWKB &#40;type de données geography&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (type de données geography)</span><span class="sxs-lookup"><span data-stu-id="ea8c4-159">[STGeomCollFromWKB &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (geography Data Type)</span></span>  
  
###  <a name="constructing-a-geography-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="ea8c4-160">Construction d'une instance geography à partir d'une entrée texte GML</span><span class="sxs-lookup"><span data-stu-id="ea8c4-160">Constructing a geography Instance from GML Text Input</span></span>  
 <span data-ttu-id="ea8c4-161">Le `geography` type de données fournit une méthode qui génère une `geography` instance à partir de GML, une représentation XML d’une `geography` instance.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-161">The `geography` data type provides a method that generates a `geography` instance from GML, an XML representation of a `geography` instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ea8c4-162">prend en charge un sous-ensemble de GML.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-162">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="ea8c4-163">Pour plus d’informations sur le langage GML (Geography Markup Language), consultez la spécification OGC : [OGC Specifications, Geography Markup Language (en anglais)](https://go.microsoft.com/fwlink/?LinkId=93629).</span><span class="sxs-lookup"><span data-stu-id="ea8c4-163">For more information on Geography Markup Language, see the OGC Specification: [OGC Specifications, Geography Markup Language.](https://go.microsoft.com/fwlink/?LinkId=93629)</span></span>  
  
 <span data-ttu-id="ea8c4-164">**Pour construire tout type d'instance geography à partir d'une entrée GML**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-164">**To construct any type of geography instance from GML input**</span></span>  
 [<span data-ttu-id="ea8c4-165">GeomFromGML &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-165">GeomFromGML &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/geomfromgml-geography-data-type)  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geography-instance"></a><a name="returning"></a> <span data-ttu-id="ea8c4-166">Renvoi de données WKT et WKB à partir d'une instance geography</span><span class="sxs-lookup"><span data-stu-id="ea8c4-166">Returning Well-Known Text and Well-Known Binary from a geography Instance</span></span>  
 <span data-ttu-id="ea8c4-167">Vous pouvez utiliser les méthodes suivantes pour retourner le format WKT ou WKB d'une instance `geography` :</span><span class="sxs-lookup"><span data-stu-id="ea8c4-167">You can use the following methods to return either the WKT or WKB format of a `geography` instance:</span></span>  
  
 <span data-ttu-id="ea8c4-168">**Pour retourner la représentation WKT d'une instance geography**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-168">**To return the WKT representation of a geography instance**</span></span>  
 [<span data-ttu-id="ea8c4-169">STAsText &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-169">STAsText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stastext-geography-data-type)  
  
 [<span data-ttu-id="ea8c4-170">ToString &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-170">ToString &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/tostring-geography-data-type)  
  
 <span data-ttu-id="ea8c4-171">**Pour retourner la représentation WKT d'une instance geography incluant des valeurs Z et M**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-171">**To return the WKT representation of a geography instance including any Z and M values**</span></span>  
 [<span data-ttu-id="ea8c4-172">AsTextZM &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-172">AsTextZM &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/astextzm-geography-data-type)  
  
 <span data-ttu-id="ea8c4-173">**Pour retourner la représentation WKB d'une instance geography**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-173">**To return the WKB representation of a geography instance**</span></span>  
 [<span data-ttu-id="ea8c4-174">STAsBinary &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-174">STAsBinary &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stasbinary-geography-data-type)  
  
 <span data-ttu-id="ea8c4-175">**Pour retourner une représentation GML d'une instance geography**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-175">**To return a GML representation of a geography instance**</span></span>  
 [<span data-ttu-id="ea8c4-176">AsGml &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-176">AsGml &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/asgml-geography-data-type)  
  
##  <a name="querying-the-properties-and-behaviors-of-geography-instances"></a><a name="query"></a> <span data-ttu-id="ea8c4-177">Interrogation des propriétés et des comportements des instances geography</span><span class="sxs-lookup"><span data-stu-id="ea8c4-177">Querying the Properties and Behaviors of geography Instances</span></span>  
 <span data-ttu-id="ea8c4-178">Toutes les `geography` instances ont un certain nombre de propriétés qui peuvent être récupérées par le biais des méthodes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournies par.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-178">All `geography` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="ea8c4-179">Les rubriques suivantes définissent les propriétés et comportements de types géographiques et les méthodes permettant de les interroger.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-179">The following topics define the properties and behaviors of geography types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="ea8c4-180">Informations sur la validité, le type d'instance et GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="ea8c4-180">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="ea8c4-181">Une fois qu’une `geography` instance est construite, vous pouvez utiliser les méthodes suivantes pour retourner le type d’instance ou, s’il s’agit d’une `GeometryCollection` instance, retourner une `geography` instance spécifique.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-181">After a `geography` instance is constructed, you can use the following methods to return the instance type, or if it is a `GeometryCollection` instance, return a specific `geography` instance.</span></span>  
  
 <span data-ttu-id="ea8c4-182">**Pour retourner le type d'instance d'une géographie**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-182">**To return the instance type of a geography**</span></span>  
 [<span data-ttu-id="ea8c4-183">STGeometryType &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-183">STGeometryType &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeometrytype-geography-data-type)  
  
 <span data-ttu-id="ea8c4-184">**Pour déterminer si une géographie est un type d'instance donné**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-184">**To determine if a geography is a given instance type**</span></span>  
 [<span data-ttu-id="ea8c4-185">InstanceOf &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-185">InstanceOf &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/instanceof-geography-data-type)  
  
 <span data-ttu-id="ea8c4-186">**Pour déterminer si une instance géographique est de forme correcte pour son type d'instance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-186">**To determine if a geography instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="ea8c4-187">STNumGeometries &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-187">STNumGeometries &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumgeometries-geography-data-type)  
  
 <span data-ttu-id="ea8c4-188">**Pour retourner une géographie spécifique dans une instance GeometryCollection**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-188">**To return a specific geography in a GeometryCollection instance**</span></span>  
 <span data-ttu-id="ea8c4-189">[STGeometryN &#40;type de données geography&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (type de données geography)</span><span class="sxs-lookup"><span data-stu-id="ea8c4-189">[STGeometryN &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (geography Data Type)</span></span>  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="ea8c4-190">Nombre de points</span><span class="sxs-lookup"><span data-stu-id="ea8c4-190">Number of Points</span></span>  
 <span data-ttu-id="ea8c4-191">Toutes les instances non vides `geography` sont constituées de *points*.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-191">All nonempty `geography` instances are comprised of *points*.</span></span> <span data-ttu-id="ea8c4-192">Ces points représentent les coordonnées de latitude et de longitude du monde sur lequel les instances `geography` sont dessinées.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-192">These points represent the latitude and longitude coordinates of the earth on which the `geography` instances are drawn.</span></span> <span data-ttu-id="ea8c4-193">Le type de données `geography` fournit de nombreuses méthodes intégrées pour interroger les points d'une instance.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-193">The data type `geography` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="ea8c4-194">**Pour retourner le nombre de points qui composent une instance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-194">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="ea8c4-195">STNumPoints &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-195">STNumPoints &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumpoints-geography-data-type)  
  
 <span data-ttu-id="ea8c4-196">**Pour retourner un point spécifique dans une instance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-196">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="ea8c4-197">STPointN &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-197">STPointN &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="ea8c4-198">**Pour retourner le point de départ d'une instance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-198">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="ea8c4-199">STStartPoint &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-199">STStartPoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ststartpoint-geography-data-type)  
  
 <span data-ttu-id="ea8c4-200">**Pour retourner le point de terminaison d'une instance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-200">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="ea8c4-201">STEndpoint &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-201">STEndpoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stendpoint-geography-data-type)  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="ea8c4-202">Dimension</span><span class="sxs-lookup"><span data-stu-id="ea8c4-202">Dimension</span></span>  
 <span data-ttu-id="ea8c4-203">Une instance `geography` non vide peut avoir 0, 1 ou 2 dimensions.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-203">A nonempty `geography` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="ea8c4-204">Les instances de dimension zéro `geography` , telles que `Point` et `MultiPoint` , n’ont pas de longueur ou de zone.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-204">Zero-dimensional `geography` instances, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="ea8c4-205">Les objets unidimensionnels, tels que `LineString, CircularString`, `CompoundCurve` et `MultiLineString`, ont une longueur.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-205">One-dimensional objects, such as `LineString, CircularString`, `CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="ea8c4-206">Les instances à deux dimensions, telles que `Polygon, CurvePolygon` , et `MultiPolygon` , ont une surface et une longueur.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-206">Two-dimensional instances, such as `Polygon, CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="ea8c4-207">Les instances vides indiquent une dimension de -1 et une `GeometryCollection` indique la dimension maximale de son contenu.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-207">Empty instances report a dimension of -1, and a `GeometryCollection` reports the maximum dimension of its contents.</span></span>  
  
 <span data-ttu-id="ea8c4-208">**Pour retourner la dimension d'une instance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-208">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="ea8c4-209">STDimension &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-209">STDimension &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdimension-geography-data-type)  
  
 <span data-ttu-id="ea8c4-210">**Pour retourner la longueur d'une instance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-210">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="ea8c4-211">STLength &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-211">STLength &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlength-geography-data-type)  
  
 <span data-ttu-id="ea8c4-212">**Pour retourner la surface d'une instance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-212">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="ea8c4-213">STArea &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-213">STArea &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/starea-geography-data-type)  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="ea8c4-214">Vide</span><span class="sxs-lookup"><span data-stu-id="ea8c4-214">Empty</span></span>  
 <span data-ttu-id="ea8c4-215">Une instance *vide* `geography` n’a aucun point.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-215">An *empty*`geography` instance does not have any points.</span></span> <span data-ttu-id="ea8c4-216">La longueur des instances `LineString, CircularString`, `CompoundCurve` et `MultiLineString` vides est 0.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-216">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is 0.</span></span> <span data-ttu-id="ea8c4-217">La surface des instances `Polygon, CurvePolygon` et `MultiPolygon` vides est 0.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-217">The area of empty `Polygon, CurvePolygon` and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="ea8c4-218">**Pour déterminer si une instance est vide**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-218">**To determine if an instance is empty**</span></span>  
 [<span data-ttu-id="ea8c4-219">STIsEmpty &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-219">STIsEmpty &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisempty-geography-data-type)  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="ea8c4-220">Fermeture</span><span class="sxs-lookup"><span data-stu-id="ea8c4-220">Closure</span></span>  
 <span data-ttu-id="ea8c4-221">Une instance *fermée* `geography` est une figure dont les points de début et de fin sont identiques.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-221">A *closed*`geography` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="ea8c4-222">Les instances `Polygon` sont considérées comme fermées.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-222">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="ea8c4-223">Les instances `Point` ne sont pas fermées.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-223">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="ea8c4-224">Un anneau est une instance `LineString` simple et fermée.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-224">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="ea8c4-225">**Pour déterminer si une instance est fermée**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-225">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="ea8c4-226">STIsClosed &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-226">STIsClosed &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisclosed-geography-data-type)  
  
 <span data-ttu-id="ea8c4-227">**Pour retourner le nombre d'anneaux dans une instance Polygon**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-227">**To return the number of rings in a Polygon instance**</span></span>  
 [<span data-ttu-id="ea8c4-228">NumRings &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-228">NumRings &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/numrings-geography-data-type)  
  
 <span data-ttu-id="ea8c4-229">**Pour retourner un anneau spécifié d'une instance géographique**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-229">**To return a specified ring of a geography instance**</span></span>  
 [<span data-ttu-id="ea8c4-230">RingN &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-230">RingN &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ringn-geography-data-type)  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="ea8c4-231">ID de référence spatial (SRID)</span><span class="sxs-lookup"><span data-stu-id="ea8c4-231">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="ea8c4-232">L'ID de référence spatial (SRID) est un identificateur spécifiant dans quel système de coordonnées ellipsoïde l'instance `geography` est représentée.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-232">The spatial reference ID (SRID) is an identifier specifying which ellipsoidal coordinate system the `geography` instance is represented in.</span></span> <span data-ttu-id="ea8c4-233">Deux instances `geography` avec différents SRID ne peuvent pas être comparées.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-233">Two `geography` instances with different SRIDs cannot be compared.</span></span>  
  
 <span data-ttu-id="ea8c4-234">**Pour définir ou retourner le SRID d'une instance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-234">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="ea8c4-235">STSrid &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-235">STSrid &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsrid-geography-data-type)  
  
 <span data-ttu-id="ea8c4-236">Cette propriété peut être modifiée.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-236">This property can be modified.</span></span>  
  
##  <a name="determining-relationships-between-geography-instances"></a><a name="rel"></a> <span data-ttu-id="ea8c4-237">Détermination de relations entre des instances geography</span><span class="sxs-lookup"><span data-stu-id="ea8c4-237">Determining Relationships between geography Instances</span></span>  
 <span data-ttu-id="ea8c4-238">Le type de données `geography` fournit de nombreuses méthodes intégrées que vous pouvez utiliser pour déterminer les relations entre deux instances `geography`.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-238">The `geography` data type provides many built-in methods you can use to determine relationships between two `geography` instances.</span></span>  
  
 <span data-ttu-id="ea8c4-239">**Pour déterminer si deux instances comprennent le même ensemble de points**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-239">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="ea8c4-240">STEquals &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-240">STEquals &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="ea8c4-241">**Pour déterminer si deux instances sont disjointes**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-241">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="ea8c4-242">STDisjoint &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-242">STDisjoint &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="ea8c4-243">**Pour déterminer si deux instances se croisent**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-243">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="ea8c4-244">STIntersects &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-244">STIntersects &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="ea8c4-245">**Pour déterminer le ou les points où deux instances se croisent**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-245">**To determine the point or points where two instances intersect**</span></span>  
 [<span data-ttu-id="ea8c4-246">STIntersection &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-246">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="ea8c4-247">**Pour déterminer la distance la plus courte entre des points dans deux instances géographiques**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-247">**To determine the shortest distance between points in two geography instances**</span></span>  
 [<span data-ttu-id="ea8c4-248">STDistance &#40;type de données geometry&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-248">STDistance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
 <span data-ttu-id="ea8c4-249">**Pour déterminer la différence en points entre deux instances géographiques**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-249">**To determine the difference in points between two geography instances**</span></span>  
 [<span data-ttu-id="ea8c4-250">STDifference &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-250">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
 <span data-ttu-id="ea8c4-251">**Pour dériver la différence symétrique, ou points uniques, d'une instance geography comparée à une autre instance**</span><span class="sxs-lookup"><span data-stu-id="ea8c4-251">**To derive the symmetric difference, or unique points, of one geography instance compared with another instance**</span></span>  
 [<span data-ttu-id="ea8c4-252">STSymDifference &#40;type de données geography&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-252">STSymDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsymdifference-geography-data-type)  
  
##  <a name="geography-instances-must-use-supported-srid"></a><a name="supportedsrid"></a> <span data-ttu-id="ea8c4-253">Les instances geography doivent utiliser un SRID pris en charge</span><span class="sxs-lookup"><span data-stu-id="ea8c4-253">geography Instances Must Use Supported SRID</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ea8c4-254">prend en charge les SRID basés sur les normes EPSG.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-254">supports SRIDs based on the EPSG standards.</span></span> <span data-ttu-id="ea8c4-255">Un SRID [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pris en charge pour les instances `geography` doit être utilisé lors de l'exécution de calculs ou de l'utilisation de méthodes avec des données spatiales géographiques.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-255">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-supported SRID for `geography` instances must be used when performing calculations or using methods with geography spatial data.</span></span> <span data-ttu-id="ea8c4-256">Le SRID doit correspondre à l’un des SRID présents dans l’affichage catalogue **sys.spatial_reference_systems** .</span><span class="sxs-lookup"><span data-stu-id="ea8c4-256">The SRID must match one of the SRIDs displayed in the **sys.spatial_reference_systems** catalog view.</span></span> <span data-ttu-id="ea8c4-257">Comme mentionné précédemment, lorsque vous effectuez des calculs sur vos données spatiales à l'aide du type de données `geography`, vos résultats dépendront de l'ellipsoïde utilisée dans la création de vos données, car un identificateur de référence spatiale (SRID) spécifique est assigné à chaque ellipsoïde.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-257">As mentioned previously, when you perform calculations on your spatial data using the `geography` data type, your results will depend on which ellipsoid was used in the creation of your data, as each ellipsoid is assigned a specific spatial reference identifier (SRID).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ea8c4-258">utilise le SRID par défaut de 4326, qui mappe au système de référence spatiale WGS 84, lors de l'utilisation de méthodes sur des instances `geography`.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-258">uses the default SRID of 4326, which maps to the WGS 84 spatial reference system, when using methods on `geography` instances.</span></span> <span data-ttu-id="ea8c4-259">Si vous utilisez des données d'un système de référence spatiale autre que WGS 84 (ou SRID 4326), vous devrez déterminer le SRID spécifique pour vos données spatiales geography.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-259">If you use data from a spatial reference system other than WGS 84 (or SRID 4326), you will need to determine the specific SRID for your geography spatial data.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="ea8c4-260">Exemples</span><span class="sxs-lookup"><span data-stu-id="ea8c4-260">Examples</span></span>  
 <span data-ttu-id="ea8c4-261">Les exemples suivants montrent comment ajouter et interroger des données géographiques.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-261">The following examples show how to add and query geography data.</span></span>  
  
-   <span data-ttu-id="ea8c4-262">Le premier exemple crée une table avec une colonne d'identité et une colonne `geography``GeogCol1`.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-262">The first example creates a table with an identity column and a `geography` column `GeogCol1`.</span></span> <span data-ttu-id="ea8c4-263">Une troisième colonne restitue la colonne `geography` dans sa représentation OGC (Open Geospatial Consortium) WKT (Well-Known Text) et utilise la méthode `STAsText()` .</span><span class="sxs-lookup"><span data-stu-id="ea8c4-263">A third column renders the `geography` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="ea8c4-264">Deux lignes sont ensuite insérées : une ligne contient une instance `LineString` de `geography`et une ligne contient une instance `Polygon` .</span><span class="sxs-lookup"><span data-stu-id="ea8c4-264">Two rows are then inserted: one row contains a `LineString` instance of `geography`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeogCol1 geography,   
        GeogCol2 AS GeogCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656)', 4326));  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))', 4326));  
    GO  
    ```  
  
-   <span data-ttu-id="ea8c4-265">Le deuxième exemple utilise la méthode `STIntersection()` pour retourner les points où les deux instances `geography` précédemment insérées se croisent.</span><span class="sxs-lookup"><span data-stu-id="ea8c4-265">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geography` instances intersect.</span></span>  
  
    ```  
    DECLARE @geog1 geography;  
    DECLARE @geog2 geography;  
    DECLARE @result geography;  
  
    SELECT @geog1 = GeogCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geog2 = GeogCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geog1.STIntersection(@geog2);  
    SELECT @result.STAsText();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ea8c4-266">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea8c4-266">See Also</span></span>  
 [<span data-ttu-id="ea8c4-267">Données spatiales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ea8c4-267">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
