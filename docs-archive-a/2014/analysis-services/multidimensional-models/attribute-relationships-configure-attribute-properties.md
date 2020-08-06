---
title: Configurer les propriétés des relations d’attributs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- flexible relationships (Analysis Services)
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
- properties [Analysis Services], attribute relationships
- rigid relationships (Analysis Services)
ms.assetid: fce511af-66d7-42fc-bb3a-6c516f16b10e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 241fa2af16377fd2cacf657ec6f99c5ca4bd0c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601162"
---
# <a name="configure-attribute-relationship-properties"></a><span data-ttu-id="8e4af-102">Configurer des propriétés de relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="8e4af-102">Configure Attribute Relationship Properties</span></span>
  <span data-ttu-id="8e4af-103">Le tableau suivant répertorie et décrit les propriétés d'une relation d'attribut.</span><span class="sxs-lookup"><span data-stu-id="8e4af-103">The following table lists and describes the properties of an attribute relationship.</span></span>  
  
|<span data-ttu-id="8e4af-104">Propriété</span><span class="sxs-lookup"><span data-stu-id="8e4af-104">Property</span></span>|<span data-ttu-id="8e4af-105">Description</span><span class="sxs-lookup"><span data-stu-id="8e4af-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8e4af-106">Attribut</span><span class="sxs-lookup"><span data-stu-id="8e4af-106">Attribute</span></span>|<span data-ttu-id="8e4af-107">Contient le nom de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="8e4af-107">Contains the name of the attribute.</span></span>|  
|<span data-ttu-id="8e4af-108">Cardinalité</span><span class="sxs-lookup"><span data-stu-id="8e4af-108">Cardinality</span></span>|<span data-ttu-id="8e4af-109">Indique la cardinalité de la relation.</span><span class="sxs-lookup"><span data-stu-id="8e4af-109">Indicates the cardinality of the relationship.</span></span> <span data-ttu-id="8e4af-110">Les valeurs sont Many, pour une relation plusieurs-à-un, ou One, pour une relation un-à-un.</span><span class="sxs-lookup"><span data-stu-id="8e4af-110">Values are Many, for a many to one relationship, or One, for a one to one relationship.</span></span> <span data-ttu-id="8e4af-111">La valeur par défaut est Many.</span><span class="sxs-lookup"><span data-stu-id="8e4af-111">Default value is Many.</span></span> <span data-ttu-id="8e4af-112">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , la propriété de cardinalité n’a aucun effet ; son utilisation est réservée à une implémentation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="8e4af-112">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the cardinality property has no effect - its use is reserved for a future implementation.</span></span>|  
|<span data-ttu-id="8e4af-113">Nom</span><span class="sxs-lookup"><span data-stu-id="8e4af-113">Name</span></span>|<span data-ttu-id="8e4af-114">Contient le nom convivial de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="8e4af-114">Contains the friendly name of the attribute.</span></span>|  
|<span data-ttu-id="8e4af-115">RelationshipType</span><span class="sxs-lookup"><span data-stu-id="8e4af-115">RelationshipType</span></span>|<span data-ttu-id="8e4af-116">Indique si les relations de membres changent avec le temps.</span><span class="sxs-lookup"><span data-stu-id="8e4af-116">Indicates whether member relationships change over time.</span></span> <span data-ttu-id="8e4af-117">Les valeurs sont Rigid, qui signifie que les relations entre membres ne changent pas avec le temps, ou Flexible, qui signifie que les relations entre membres changent avec le temps.</span><span class="sxs-lookup"><span data-stu-id="8e4af-117">Values are Rigid, which means that relationships between members do not change over time, or Flexible, which means that relationships between members change over time.</span></span> <span data-ttu-id="8e4af-118">La valeur par défaut est Flexible.</span><span class="sxs-lookup"><span data-stu-id="8e4af-118">Default is Flexible.</span></span> <span data-ttu-id="8e4af-119">Si vous définissez une relation comme flexible, les agrégations sont supprimées et recalculées dans le cadre de la mise à jour incrémentielle (elles ne sont pas supprimées si seuls de nouveaux membres sont ajoutés).</span><span class="sxs-lookup"><span data-stu-id="8e4af-119">If you define a relationship as flexible, aggregations are dropped and recomputed as part of an incremental update (they will not be dropped if only new members are added).</span></span> <span data-ttu-id="8e4af-120">Si vous définissez une relation rigide, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] conserve les agrégations une fois la dimension mise à jour de manière incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="8e4af-120">If you define a relationship as rigid, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retains aggregations when the dimension is incrementally updated.</span></span> <span data-ttu-id="8e4af-121">Si une relation rigide change, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] génère une erreur pendant le traitement incrémentiel.</span><span class="sxs-lookup"><span data-stu-id="8e4af-121">If a relationship that is defined as rigid actually changes, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generates an error during incremental processing.</span></span> <span data-ttu-id="8e4af-122">En spécifiant les relations et les propriétés de relations appropriées, vous améliorez les performances de requête et de traitement.</span><span class="sxs-lookup"><span data-stu-id="8e4af-122">Specifying the appropriate relationships and relationship properties increases query and processing performance.</span></span>|  
|<span data-ttu-id="8e4af-123">Visible</span><span class="sxs-lookup"><span data-stu-id="8e4af-123">Visible</span></span>|<span data-ttu-id="8e4af-124">Détermine la visibilité de la relation d'attribut.</span><span class="sxs-lookup"><span data-stu-id="8e4af-124">Determines the visibility of the attribute relationship.</span></span> <span data-ttu-id="8e4af-125">Les valeurs sont True ou False.</span><span class="sxs-lookup"><span data-stu-id="8e4af-125">Values are True or False.</span></span> <span data-ttu-id="8e4af-126">La valeur par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="8e4af-126">Default is True.</span></span>|  
  
  
