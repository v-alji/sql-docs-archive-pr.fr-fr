---
title: Identificateurs de référence spatiale (SRID) | Microsoft Docs
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Spatial Reference Identifiers (SRIDs)
- geodetic spatial data [SQL Server], identifiers
- SRID
ms.assetid: 0612658a-7d1b-4178-bdc2-42b914ea31a7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 15db59b43731b9a39ff4bef78e3a6cb6929e9b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611010"
---
# <a name="spatial-reference-identifiers-srids"></a><span data-ttu-id="0cadc-102">Identificateurs de référence spatiale (SRID)</span><span class="sxs-lookup"><span data-stu-id="0cadc-102">Spatial Reference Identifiers (SRIDs)</span></span>
  <span data-ttu-id="0cadc-103">Chaque instance spatiale a un identificateur de référence spatiale (SRID).</span><span class="sxs-lookup"><span data-stu-id="0cadc-103">Each spatial instance has a spatial reference identifier (SRID).</span></span> <span data-ttu-id="0cadc-104">Le SRID correspond à un système de référence spatial basé sur l'ellipsoïde spécifique utilisée pour le mappage de monde en deux dimensions ou le mappage de monde sphérique.</span><span class="sxs-lookup"><span data-stu-id="0cadc-104">The SRID corresponds to a spatial reference system based on the specific ellipsoid used for either flat-earth mapping or round-earth mapping.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0cadc-105">Pour obtenir une description détaillée et des exemples des fonctionnalités spatiales introduites dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], notamment le nouveau SRID, téléchargez le livre blanc [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407)(Nouvelles fonctionnalités spatiales dans SQL Server 2012).</span><span class="sxs-lookup"><span data-stu-id="0cadc-105">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including a new SRID, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="0cadc-106">Une colonne spatiale peut contenir des objets avec des SRID différents.</span><span class="sxs-lookup"><span data-stu-id="0cadc-106">A spatial column can contain objects with different SRIDs.</span></span> <span data-ttu-id="0cadc-107">Toutefois, seules des instances spatiales avec le même SRID peuvent être utilisées lors de l'exécution d'opérations avec des méthodes de données spatiales [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur vos données.</span><span class="sxs-lookup"><span data-stu-id="0cadc-107">However, only spatial instances with the same SRID can be used when performing operations with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data methods on your data.</span></span> <span data-ttu-id="0cadc-108">Le résultat de toute méthode spatiale dérivée de deux instances de données spatiales est valide uniquement si ces instances ont le même SRID basé sur la même unité de mesure, donnée et projection utilisée pour déterminer les coordonnées des instances.</span><span class="sxs-lookup"><span data-stu-id="0cadc-108">The result of any spatial method derived from two spatial data instances is valid only if those instances have the same SRID that is based on the same unit of measurement, datum, and projection used to determine the coordinates of the instances.</span></span> <span data-ttu-id="0cadc-109">Les unités de mesure les plus courantes d'un SRID sont le mètre ou le mètre carré.</span><span class="sxs-lookup"><span data-stu-id="0cadc-109">The most common units of measurement of a SRID are meters or square meters.</span></span>  
  
 <span data-ttu-id="0cadc-110">Si deux instances spatiales n'ont pas le même SRID, les résultats d'une méthode de type de données `geometry` ou `geography` utilisée sur les instances retournent NULL.</span><span class="sxs-lookup"><span data-stu-id="0cadc-110">If two spatial instances do not have the same SRID, the results from a `geometry` or `geography` Data Type method used on the instances will return NULL.</span></span> <span data-ttu-id="0cadc-111">Par exemple, pour que le terme de prédicat suivant retourne un résultat non NULL, les deux instances `geometry`, `geometry1` et `geometry2`, doivent avoir le même SRID :</span><span class="sxs-lookup"><span data-stu-id="0cadc-111">For example, for the following predicate term to return a non-NULL result, the two `geometry` instances, `geometry1` and `geometry2`, must have the same SRID:</span></span>  
  
 `geometry1.STIntersects(geometry2) = 1`  
  
> [!NOTE]  
>  <span data-ttu-id="0cadc-112">Le système d’identification de référence spatiale est défini par la [norme EPSG (European Petroleum Survey Group)](https://go.microsoft.com/fwlink/?LinkId=99349) , qui regroupe un ensemble de normes développées pour la cartographie, l’arpentage et le stockage de données géodésiques.</span><span class="sxs-lookup"><span data-stu-id="0cadc-112">The spatial reference identification system is defined by the [European Petroleum Survey Group (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) standard, which is a set of standards developed for cartography, surveying, and geodetic data storage.</span></span> <span data-ttu-id="0cadc-113">Cette norme est détenue par l'OGP (Oil and Gas Producers) Surveying and Positioning Committee.</span><span class="sxs-lookup"><span data-stu-id="0cadc-113">This standard is owned by the Oil and Gas Producers (OGP) Surveying and Positioning Committee.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cadc-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0cadc-114">See Also</span></span>  
 [<span data-ttu-id="0cadc-115">Présentation des types de données spatiales</span><span class="sxs-lookup"><span data-stu-id="0cadc-115">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
