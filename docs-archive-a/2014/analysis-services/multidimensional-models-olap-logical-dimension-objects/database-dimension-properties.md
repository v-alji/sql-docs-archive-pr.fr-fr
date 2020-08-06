---
title: Propriétés de la dimension de base de données | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- metadata [Analysis Services]
- dimensions [Analysis Services], characteristics
- properties [Analysis Services], dimensions
ms.assetid: 075548ef-08a3-413c-8ee0-4a074c276fcc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 504e190f4c513a8c999c4d7d7ab9eaabb83298c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611985"
---
# <a name="database-dimension-properties"></a><span data-ttu-id="f94fa-102">Propriétés de dimension d'une base de données</span><span class="sxs-lookup"><span data-stu-id="f94fa-102">Database Dimension Properties</span></span>
  <span data-ttu-id="f94fa-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , les caractéristiques d’une dimension sont définies par les métadonnées de la dimension, en fonction des paramètres de diverses propriétés de dimension et des attributs ou hiérarchies contenus dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the characteristics of a dimension are defined by the metadata for the dimension, based on the settings of various dimension properties, and on the attributes or hierarchies that are contained by the dimension.</span></span> <span data-ttu-id="f94fa-104">Le tableau ci-dessous décrit les propriétés des dimensions dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f94fa-104">The following table describes the dimension properties in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="f94fa-105">Propriété</span><span class="sxs-lookup"><span data-stu-id="f94fa-105">Property</span></span>|<span data-ttu-id="f94fa-106">Description</span><span class="sxs-lookup"><span data-stu-id="f94fa-106">Description</span></span>|  
|--------------|-----------------|  
|`AttributeAllMemberName`|<span data-ttu-id="f94fa-107">Spécifie le nom du membre Tous pour les attributs d'une dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-107">Specifies the name of the All member for attributes in a dimension.</span></span>|  
|`Collation`|<span data-ttu-id="f94fa-108">Détermine le classement utilisé par la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-108">Determines the collation used by the dimension.</span></span>|  
|`CurrentStorageMode`|<span data-ttu-id="f94fa-109">Contient le mode de stockage en cours pour la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-109">Contains the current storage mode for the dimension.</span></span>|  
|`DependsOnDimension`|<span data-ttu-id="f94fa-110">Contient l'identificateur d'une autre dimension dont la dimension dépend (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="f94fa-110">Contains the ID of another dimension on which the dimension depends, if any.</span></span>|  
|`Description`|<span data-ttu-id="f94fa-111">Contient la description de la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-111">Contains the description of the dimension.</span></span>|  
|`ErrorConfiguration`|<span data-ttu-id="f94fa-112">Paramètres configurables de gestion d'erreur pour la gestion des clés dupliquées, des clés inconnues, des limites d'erreur, des actions en cas de détection d'erreur, du fichier journal des erreurs et pour la gestion des clés NULL.</span><span class="sxs-lookup"><span data-stu-id="f94fa-112">Configurable error handling settings for handling of duplicate keys, unknown keys, error limits, action upon error detection, error log file, and null key handling.</span></span>|  
|`ID`|<span data-ttu-id="f94fa-113">Contient l'identificateur unique (ID) de la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-113">Contains the unique identifier (ID) of the dimension.</span></span>|  
|`Language`|<span data-ttu-id="f94fa-114">Spécifie la langue par défaut de la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-114">Specifies the default language for the dimension.</span></span>|  
|`MdxMissingMemberMode`|<span data-ttu-id="f94fa-115">Détermine comment les membres manquants sont gérés pour les instructions MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="f94fa-115">Determines how missing members are handled for Multidimensional Expressions (MDX) statements.</span></span>|  
|`MiningModelID`|<span data-ttu-id="f94fa-116">Contient l'identificateur du modèle d'exploration de données à laquelle la dimension d'exploration de données est associée.</span><span class="sxs-lookup"><span data-stu-id="f94fa-116">Contains the ID of the mining model with which the data mining dimension is associated.</span></span> <span data-ttu-id="f94fa-117">Cette propriété est applicable seulement si la dimension est une dimension de modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="f94fa-117">This property is applicable only if the dimension is a mining model dimension.</span></span>|  
|`Name`|<span data-ttu-id="f94fa-118">Spécifie le nom de la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-118">Specifies the name of the dimension.</span></span>|  
|`ProactiveCaching`|<span data-ttu-id="f94fa-119">Définit les paramètres de cache pro-actif pour la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-119">Defines the proactive cache settings for the dimension.</span></span>|  
|`ProcessingGroup`|<span data-ttu-id="f94fa-120">Spécifie le groupe de traitement.</span><span class="sxs-lookup"><span data-stu-id="f94fa-120">Specifies the processing group.</span></span> <span data-ttu-id="f94fa-121">Les valeurs sont ByAttribute ou ByTable.</span><span class="sxs-lookup"><span data-stu-id="f94fa-121">Values are ByAttribute or ByTable.</span></span> <span data-ttu-id="f94fa-122">La valeur par défaut est `ByAttribute`.</span><span class="sxs-lookup"><span data-stu-id="f94fa-122">Default is `ByAttribute`.</span></span>|  
|`ProcessingMode`|<span data-ttu-id="f94fa-123">Indique si [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] doit créer les index et effectuer l'agrégation lors du traitement ou après celui-ci.</span><span class="sxs-lookup"><span data-stu-id="f94fa-123">Indicates whether [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] should index and aggregate during or after processing.</span></span>|  
|`ProcessingPriority`|<span data-ttu-id="f94fa-124">Détermine la priorité de traitement de la dimension lors des opérations en arrière-plan, notamment le traitement en différé des agrégations, de l'indexation ou du clustering.</span><span class="sxs-lookup"><span data-stu-id="f94fa-124">Determines the processing priority of the dimension during background operations such as lazy aggregation, indexing, or clustering.</span></span>|  
|`Source`|<span data-ttu-id="f94fa-125">Identifie la vue de source de données à laquelle la dimension est liée.</span><span class="sxs-lookup"><span data-stu-id="f94fa-125">Identifies the data source view to which the dimension is bound.</span></span>|  
|`StorageMode`|<span data-ttu-id="f94fa-126">Détermine le mode de stockage pour la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-126">Determines the storage mode for the dimension.</span></span>|  
|`Type`|<span data-ttu-id="f94fa-127">Spécifie le type de la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-127">Specifies the type of the dimension.</span></span>|  
|`UnknownMember`|<span data-ttu-id="f94fa-128">Indique si le membre inconnu est visible.</span><span class="sxs-lookup"><span data-stu-id="f94fa-128">Indicates whether the unknown member is visible.</span></span>|  
|`UnknownMemberName`|<span data-ttu-id="f94fa-129">Spécifie la légende (dans la langue par défaut de la dimension) pour le membre inconnu de la dimension.</span><span class="sxs-lookup"><span data-stu-id="f94fa-129">Specifies the caption, in the default language of the dimension, for the unknown member of the dimension.</span></span>|  
|`WriteEnabled`|<span data-ttu-id="f94fa-130">Indique si l'écriture différée de dimension est disponible (soumise à des autorisations de sécurité).</span><span class="sxs-lookup"><span data-stu-id="f94fa-130">Indicates whether dimension writebacks are available (subject to security permissions).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f94fa-131">Pour plus d’informations sur la définition des valeurs des propriétés ErrorConfiguration et UnknownMember lors de l’utilisation de valeurs NULL et d’autres problèmes d’intégrité des données, consultez [gestion des problèmes d’intégrité des données dans Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span><span class="sxs-lookup"><span data-stu-id="f94fa-131">For more information about setting values for the ErrorConfiguration and UnknownMember properties when working with null values and other data integrity issues, see [Handling Data Integrity Issues in Analysis Services 2005](https://go.microsoft.com/fwlink/?LinkId=81891).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f94fa-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f94fa-132">See Also</span></span>  
 <span data-ttu-id="f94fa-133">[Attributs et hiérarchies d’attributs](attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="f94fa-133">[Attributes and Attribute Hierarchies](attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="f94fa-134">[Hiérarchies utilisateur](user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="f94fa-134">[User Hierarchies](user-hierarchies.md) </span></span>  
 <span data-ttu-id="f94fa-135">[Relations de dimension](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="f94fa-135">[Dimension Relationships](../multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 [<span data-ttu-id="f94fa-136">Dimensions &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="f94fa-136">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)  
  
  
