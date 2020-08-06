---
title: Stockage de dimension | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- dimensions [Analysis Services], storage
- storing data [Analysis Services]
- storage [Analysis Services], dimensions
- relational OLAP
- multidimensional OLAP
- MOLAP
- storing data [Analysis Services], dimensions
- ROLAP
ms.assetid: 8d74b932-2174-4e1f-8414-636455880b6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa68ebcfa8f4136bcd4a131842c852665ee9851
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696272"
---
# <a name="dimension-storage"></a><span data-ttu-id="e5930-102">Stockage de dimension</span><span class="sxs-lookup"><span data-stu-id="e5930-102">Dimension Storage</span></span>
  <span data-ttu-id="e5930-103">Les dimensions dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] prennent en charge deux modes de stockage :</span><span class="sxs-lookup"><span data-stu-id="e5930-103">Dimensions in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] support two storage modes:</span></span>  
  
-   <span data-ttu-id="e5930-104">OLAP relationnel (ROLAP)</span><span class="sxs-lookup"><span data-stu-id="e5930-104">Relational OLAP (ROLAP)</span></span>  
  
-   <span data-ttu-id="e5930-105">OLAP multidimensionnel (MOLAP)</span><span class="sxs-lookup"><span data-stu-id="e5930-105">Multidimensional OLAP (MOLAP)</span></span>  
  
 <span data-ttu-id="e5930-106">Le mode de stockage détermine l'emplacement et le format des données d'une dimension.</span><span class="sxs-lookup"><span data-stu-id="e5930-106">The storage mode determines the location and form of a dimension's data.</span></span> <span data-ttu-id="e5930-107">Le mode de stockage par défaut des dimensions est MOLAP.</span><span class="sxs-lookup"><span data-stu-id="e5930-107">MOLAP is the default storage mode for dimensions.</span></span> <span data-ttu-id="e5930-108">**Rubriques connexes :**[traitement et modes de stockage des partitions](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span><span class="sxs-lookup"><span data-stu-id="e5930-108">**Related topics:**[Partition Storage Modes and Processing](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)</span></span>  
  
## <a name="molap"></a><span data-ttu-id="e5930-109">MOLAP</span><span class="sxs-lookup"><span data-stu-id="e5930-109">MOLAP</span></span>  
 <span data-ttu-id="e5930-110">Les données d'une dimension qui utilise MOLAP sont stockées dans une structure multidimensionnelle dans l'instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5930-110">Data for a dimension that uses MOLAP is stored in a multidimensional structure in the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e5930-111">Cette structure multidimensionnelle est créée et peuplée lors du traitement de la dimension.</span><span class="sxs-lookup"><span data-stu-id="e5930-111">This multidimensional structure is created and populated when the dimension is processed.</span></span> <span data-ttu-id="e5930-112">Les dimensions MOLAP offrent de meilleures performances d'interrogation que les dimensions ROLAP.</span><span class="sxs-lookup"><span data-stu-id="e5930-112">MOLAP dimensions provide better query performance than ROLAP dimensions.</span></span>  
  
## <a name="rolap"></a><span data-ttu-id="e5930-113">ROLAP</span><span class="sxs-lookup"><span data-stu-id="e5930-113">ROLAP</span></span>  
 <span data-ttu-id="e5930-114">Les données d'une dimension qui utilise ROLAP sont stockées dans les tables utilisées pour définir la dimension.</span><span class="sxs-lookup"><span data-stu-id="e5930-114">Data for a dimension that uses ROLAP is actually stored in the tables used to define the dimension.</span></span> <span data-ttu-id="e5930-115">Vous pouvez utiliser le mode de stockage ROLAP pour prendre en charge les grandes dimensions sans avoir à dupliquer de grandes quantités de données, mais au prix de performances moindres pour les requêtes.</span><span class="sxs-lookup"><span data-stu-id="e5930-115">The ROLAP storage mode can be used to support large dimensions without duplicating large amounts of data, but at the expense of query performance.</span></span> <span data-ttu-id="e5930-116">Étant donné que la dimension dépend directement des tables de la vue de source de données utilisée pour la définir, le mode de stockage ROLAP prend également en charge le mode de stockage OLAP en temps réel.</span><span class="sxs-lookup"><span data-stu-id="e5930-116">Because the dimension relies directly on the tables in the data source view used to define the dimension, the ROLAP storage mode also supports real-time OLAP.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e5930-117">Si une dimension qui utilise le mode ROLAP est incluse dans un cube qui utilise le mode MOLAP, toute modification apportée au schéma dans la table source doit être suivie par le traitement immédiat du cube.</span><span class="sxs-lookup"><span data-stu-id="e5930-117">If a dimension uses the ROLAP storage mode and the dimension is included in a cube that uses MOLAP storage, any schema changes to its source table must be followed by immediate processing of the cube.</span></span> <span data-ttu-id="e5930-118">Si vous ne procédez pas ainsi, lorsque vous interrogerez le cube, les résultats ne seront pas cohérents.</span><span class="sxs-lookup"><span data-stu-id="e5930-118">Failure to do this may result in inconsistent results when querying the cube.</span></span> <span data-ttu-id="e5930-119">**Rubrique connexe :**[automatiser Analysis Services tâches administratives avec SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="e5930-119">**Related topic:**[Automate Analysis Services Administrative Tasks with SSIS](../instances/automate-analysis-services-administrative-tasks-with-ssis.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5930-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5930-120">See Also</span></span>  
 [<span data-ttu-id="e5930-121">Traitement et modes de stockage des partitions</span><span class="sxs-lookup"><span data-stu-id="e5930-121">Partition Storage Modes and Processing</span></span>](../multidimensional-models-olap-logical-cube-objects/partitions-partition-storage-modes-and-processing.md)  
  
  
