---
title: Dimensions (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- OLAP objects [Analysis Services], dimensions
- dimensions [Analysis Services]
- Analysis Services objects, dimensions
ms.assetid: 2b114135-2572-4479-8c81-3ccf0cfeb9f7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e0e15d4f74c2c6cec06edaf692199e48534c7e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706876"
---
# <a name="dimensions-analysis-services---multidimensional-data"></a><span data-ttu-id="9d953-102">Dimensions (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="9d953-102">Dimensions (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="9d953-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , les dimensions sont un composant fondamental des cubes.</span><span class="sxs-lookup"><span data-stu-id="9d953-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], dimensions are a fundamental component of cubes.</span></span> <span data-ttu-id="9d953-104">Les dimensions organisent les données en relation avec un domaine d'intérêt (clients, magasins ou employés, par exemple) pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9d953-104">Dimensions organize data with relation to an area of interest, such as customers, stores, or employees, to users.</span></span> <span data-ttu-id="9d953-105">Les dimensions dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contiennent des attributs qui correspondent à des colonnes dans des tables de dimension.</span><span class="sxs-lookup"><span data-stu-id="9d953-105">Dimensions in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contain attributes that correspond to columns in dimension tables.</span></span> <span data-ttu-id="9d953-106">Ces attributs apparaissent en tant que hiérarchies d'attributs et peuvent être organisés en hiérarchies définies par l'utilisateur ou peuvent être définies en tant que hiérarchies parent-enfant basées sur des colonnes dans la table de dimensions sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="9d953-106">These attributes appear as attribute hierarchies and can be organized into user-defined hierarchies, or can be defined as parent-child hierarchies based on columns in the underlying dimension table.</span></span> <span data-ttu-id="9d953-107">Les hiérarchies sont utilisées pour organiser les mesures contenues dans un cube.</span><span class="sxs-lookup"><span data-stu-id="9d953-107">Hierarchies are used to organize measures that are contained in a cube.</span></span> <span data-ttu-id="9d953-108">Les rubriques suivantes donnent un aperçu des dimensions, des attributs et des hiérarchies.</span><span class="sxs-lookup"><span data-stu-id="9d953-108">The following topics provide an overview of dimensions, attributes, and hierarchies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d953-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9d953-109">In This Section</span></span>  
  
|<span data-ttu-id="9d953-110">Rubrique</span><span class="sxs-lookup"><span data-stu-id="9d953-110">Topic</span></span>|<span data-ttu-id="9d953-111">Description</span><span class="sxs-lookup"><span data-stu-id="9d953-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9d953-112">Présentation des dimensions &#40;Analysis Services – Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="9d953-112">Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="9d953-113">Présente les concepts des dimensions.</span><span class="sxs-lookup"><span data-stu-id="9d953-113">Provides an overview of dimension concepts.</span></span>|  
|[<span data-ttu-id="9d953-114">Attributs et hiérarchies d'attributs</span><span class="sxs-lookup"><span data-stu-id="9d953-114">Attributes and Attribute Hierarchies</span></span>](attributes-and-attribute-hierarchies.md)|<span data-ttu-id="9d953-115">Décrit les attributs et les hiérarchies d'attributs.</span><span class="sxs-lookup"><span data-stu-id="9d953-115">Describes attributes and attribute hierarchies.</span></span>|  
|[<span data-ttu-id="9d953-116">Hiérarchies utilisateur</span><span class="sxs-lookup"><span data-stu-id="9d953-116">User Hierarchies</span></span>](user-hierarchies.md)|<span data-ttu-id="9d953-117">Décrit les hiérarchies d'attributs définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d953-117">Describes user-defined hierarchies of attributes.</span></span>|  
|[<span data-ttu-id="9d953-118">Dimensions activées en écriture</span><span class="sxs-lookup"><span data-stu-id="9d953-118">Write-Enabled Dimensions</span></span>](write-enabled-dimensions.md)|<span data-ttu-id="9d953-119">Décrit les dimensions activées en écriture.</span><span class="sxs-lookup"><span data-stu-id="9d953-119">Describes write-enabled dimensions.</span></span>|  
|[<span data-ttu-id="9d953-120">Traductions de dimension</span><span class="sxs-lookup"><span data-stu-id="9d953-120">Dimension Translations</span></span>](dimension-translations.md)|<span data-ttu-id="9d953-121">Décrit les traductions des métadonnées de dimension.</span><span class="sxs-lookup"><span data-stu-id="9d953-121">Describes translations of dimension meta data.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d953-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d953-122">See Also</span></span>  
 <span data-ttu-id="9d953-123">[Dimensions dans les modèles multidimensionnels](../multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="9d953-123">[Dimensions in Multidimensional Models](../multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="9d953-124">Objets de cube &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="9d953-124">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
  
