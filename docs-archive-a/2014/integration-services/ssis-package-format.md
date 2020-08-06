---
title: Format de package SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cfe0e5dc-5be3-4222-b721-fe83665edd94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 524c65ac5682b8efe8c4191697eb540f9acca82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700008"
---
# <a name="ssis-package-format"></a><span data-ttu-id="b0be2-102">Format de package SSIS</span><span class="sxs-lookup"><span data-stu-id="b0be2-102">SSIS Package Format</span></span>
  <span data-ttu-id="b0be2-103">Dans la version actuelle de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], des modifications significatives ont été apportées au format de package (fichier .dtsx) pour faciliter la lecture du format et la comparaison des packages.</span><span class="sxs-lookup"><span data-stu-id="b0be2-103">In the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], significant changes were made to the package format (.dtsx file) to make it easier to read the format and to compare packages.</span></span> <span data-ttu-id="b0be2-104">Vous pouvez également fusionner de manière plus fiable les packages qui ne contiennent pas de modifications en conflit ou de modifications stockées au format binaire.</span><span class="sxs-lookup"><span data-stu-id="b0be2-104">You can also more reliably merge packages that don't contain conflicting changes or changes stored in binary format.</span></span>  
  
 <span data-ttu-id="b0be2-105">Pour afficher le format de fichier de package DTSX actuel, consultez [ \[ MS-dtsx \] : spécification de format de fichier XML du package DTS (Data Transformation Services](https://go.microsoft.com/fwlink/?LinkId=233251)).</span><span class="sxs-lookup"><span data-stu-id="b0be2-105">To view the current DTSX package file format, see [\[MS-DTSX\]: Data Transformation Services Package XML File Format Specification](https://go.microsoft.com/fwlink/?LinkId=233251).</span></span>  
  
 <span data-ttu-id="b0be2-106">La liste suivante présente les modifications apportées au format de fichier.</span><span class="sxs-lookup"><span data-stu-id="b0be2-106">The following list outlines the file format changes.</span></span> <span data-ttu-id="b0be2-107">Pour afficher des exemples de code liés à ces modifications, consultez [Modifications de format de package dans SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255)</span><span class="sxs-lookup"><span data-stu-id="b0be2-107">To view code examples of these changes, see [Package Format Changes in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255).</span></span>  
  
-   <span data-ttu-id="b0be2-108">Les conventions de mise en forme ont été appliquées pour faciliter la lecture et la compréhension du fichier .dtsx.</span><span class="sxs-lookup"><span data-stu-id="b0be2-108">Formatting conventions have been applied to make it easier to read and understand the .dtsx file.</span></span>  
  
-   <span data-ttu-id="b0be2-109">Le format est plus concis.</span><span class="sxs-lookup"><span data-stu-id="b0be2-109">The format is more concise.</span></span> <span data-ttu-id="b0be2-110">Les éléments distincts de chaque propriété ont été conservés en tant qu'attributs, à l'exception de PackageFormatVersion.</span><span class="sxs-lookup"><span data-stu-id="b0be2-110">Separate elements for each property have been persisted as attributes, with the exception of the PackageFormatVersion.</span></span> <span data-ttu-id="b0be2-111">Les attributs sont répertoriés par ordre alphabétique, et les propriétés qui ont des valeurs par défaut ne sont plus conservées.</span><span class="sxs-lookup"><span data-stu-id="b0be2-111">Attributes are listed alphabetically, and properties that have default values are no longer persisted.</span></span> <span data-ttu-id="b0be2-112">Enfin, les éléments pouvant apparaître plusieurs fois, sont maintenant contenus dans un élément parent.</span><span class="sxs-lookup"><span data-stu-id="b0be2-112">Finally, elements that can appear multiple times, are now contained within a parent element.</span></span>  
  
-   <span data-ttu-id="b0be2-113">La plupart des objets d'un package qui peuvent être référencés par d'autres objets possèdent maintenant un attribut `refId` défini dans la définition XML du package.</span><span class="sxs-lookup"><span data-stu-id="b0be2-113">Most objects within a package that can be referred to by other objects now have a `refId` attribute defined in the package XML.</span></span> <span data-ttu-id="b0be2-114">Au lieu des ID de lignage, c'est l'attribut `refID` qui est maintenant conservé.</span><span class="sxs-lookup"><span data-stu-id="b0be2-114">Instead of persisting lineage IDs, the `refID` is now persisted.</span></span> <span data-ttu-id="b0be2-115">Les ID de lignage sont toujours utilisés au moment de l'exécution et régénérés lors du chargement du package.</span><span class="sxs-lookup"><span data-stu-id="b0be2-115">Lineage IDs are still used within the runtime and regenerated when the package is loaded.</span></span>  
  
     <span data-ttu-id="b0be2-116">La valeur `refId` est une chaîne unique lisible et compréhensible, par comparaison aux GUID ou aux valeurs entières.</span><span class="sxs-lookup"><span data-stu-id="b0be2-116">The `refId` value is a unique string that is readable and understandable, compared to GUIDs or integer values.</span></span> <span data-ttu-id="b0be2-117">La chaîne est similaire aux valeurs de chemin d'accès utilisées pour les configurations de packages dans les versions précédentes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0be2-117">The string is similar to path values used for package configurations in previous releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="b0be2-118">Si vous fusionnez des modifications entre deux versions d'un package, `refId` peut être utilisé dans des opérations de recherche/remplacement pour garantir que toutes les références à cet objet sont correctement mises à jour.</span><span class="sxs-lookup"><span data-stu-id="b0be2-118">If you are merging changes between two versions of a package, the `refId` can be used in find/replace operations to ensure that all references to that object have been correctly updated.</span></span>  
  
-   <span data-ttu-id="b0be2-119">Les informations de mise en page sont contenues dans une section CDATA.</span><span class="sxs-lookup"><span data-stu-id="b0be2-119">The layout information is contained in a CData section.</span></span>  
  
-   <span data-ttu-id="b0be2-120">Les annotations sont conservées en texte clair.</span><span class="sxs-lookup"><span data-stu-id="b0be2-120">Annotations are persisted in cleartext.</span></span> <span data-ttu-id="b0be2-121">Cela simplifie l'extraction des informations pour la génération automatisée de la documentation.</span><span class="sxs-lookup"><span data-stu-id="b0be2-121">This makes it easier to extract the information for automated generation of documentation.</span></span>  
  
  
