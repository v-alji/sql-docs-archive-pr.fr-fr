---
title: Définir les propriétés d’une hiérarchie de cube | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], multilevel
- hierarchies [Analysis Services], cubes
ms.assetid: 819d0a4e-7815-4332-a605-b07ca2ade6ac
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8903a49754357aad9cf24ee63fffa45fbf120e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696248"
---
# <a name="define-cube-hierarchy-properties"></a><span data-ttu-id="7cfd9-102">Définir les propriétés des hiérarchies de cube</span><span class="sxs-lookup"><span data-stu-id="7cfd9-102">Define Cube Hierarchy Properties</span></span>
  <span data-ttu-id="7cfd9-103">Les propriétés des hiérarchies de cube vous permettent de spécifier des paramètres uniques pour les hiérarchies définies par l'utilisateur des dimensions de cube à partir de la même dimension de base de données.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-103">Cube hierarchy properties enable you to specify unique settings for user-defined hierarchies in cube dimensions based on the same database dimension.</span></span> <span data-ttu-id="7cfd9-104">Le tableau suivant décrit les propriétés d'une hiérarchie de cube.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-104">The following table describes the properties of a cube hierarchy.</span></span>  
  
|<span data-ttu-id="7cfd9-105">Propriété</span><span class="sxs-lookup"><span data-stu-id="7cfd9-105">Property</span></span>|<span data-ttu-id="7cfd9-106">Description</span><span class="sxs-lookup"><span data-stu-id="7cfd9-106">Description</span></span>|  
|--------------|-----------------|  
|`Enabled`|<span data-ttu-id="7cfd9-107">Détermine si la hiérarchie est activée pour la dimension de cube.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-107">Determines whether the hierarchy is enabled for the cube dimension.</span></span>|  
|`HierarchyID`|<span data-ttu-id="7cfd9-108">Contient l'identificateur unique (ID) de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-108">Contains the unique identifier (ID) of the hierarchy.</span></span>|  
|`OptimizedState`|<span data-ttu-id="7cfd9-109">Détermine le niveau d'optimisation appliqué à la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-109">Determines the level of optimization that is applied to the hierarchy.</span></span> <span data-ttu-id="7cfd9-110">Cette propriété peut avoir les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="7cfd9-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="7cfd9-111">`FullyOptimized` : l’instance génère des index pour la hiérarchie afin d’augmenter les performances en matière de requêtes.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-111">`FullyOptimized`: The instance builds indexes for the hierarchy to improve query performance.</span></span> <span data-ttu-id="7cfd9-112">Valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-112">This is the default value.</span></span><br /><br /> <span data-ttu-id="7cfd9-113">`NotOptimized` : l’instance ne génère pas d’index supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-113">`NotOptimized`: The instance does not build additional indexes.</span></span>|  
|`Visible`|<span data-ttu-id="7cfd9-114">Détermine la visibilité de la hiérarchie du cube.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-114">Determines the visibility of the cube hierarchy.</span></span> <span data-ttu-id="7cfd9-115">La valeur par défaut est `True`.</span><span class="sxs-lookup"><span data-stu-id="7cfd9-115">The default value is `True`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7cfd9-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7cfd9-116">See Also</span></span>  
 [<span data-ttu-id="7cfd9-117">Hiérarchies utilisateur</span><span class="sxs-lookup"><span data-stu-id="7cfd9-117">User Hierarchies</span></span>](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md)  
  
  
