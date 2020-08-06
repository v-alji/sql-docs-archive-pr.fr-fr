---
title: Fin de l’Assistant (Assistant Partition) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.finish.f1
ms.assetid: 68a4dd5d-94d9-4a02-be31-949a6da0ef51
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60be28170e8f8ec156d1c37149ddbc04b64bf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602496"
---
# <a name="completing-the-wizard-partition-wizard"></a><span data-ttu-id="20775-102">Fin de l'Assistant (Assistant Partition)</span><span class="sxs-lookup"><span data-stu-id="20775-102">Completing the Wizard (Partition Wizard)</span></span>
  <span data-ttu-id="20775-103">Utilisez la page **Fin de l'Assistant** pour nommer la partition, définir la conception d'agrégation de la partition et éventuellement déployer et traiter la partition après avoir exécuté l'Assistant Partition.</span><span class="sxs-lookup"><span data-stu-id="20775-103">Use the **Completing the Wizard** page to name the partition, define the aggregation design for your partition, and optionally deploy and process the partition after completing the Partition Wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="20775-104">Options</span><span class="sxs-lookup"><span data-stu-id="20775-104">Options</span></span>  
 <span data-ttu-id="20775-105">**Nom**</span><span class="sxs-lookup"><span data-stu-id="20775-105">**Name**</span></span>  
 <span data-ttu-id="20775-106">Entrez le nom de la nouvelle partition.</span><span class="sxs-lookup"><span data-stu-id="20775-106">Type the name for the new partition.</span></span> <span data-ttu-id="20775-107">Si vous utilisez plusieurs tables, entrez le préfixe à combiner avec le nom de la table pour créer chaque nom de partition.</span><span class="sxs-lookup"><span data-stu-id="20775-107">If you are working with multiple tables, enter the prefix that will be combined with the table name to create each partition name.</span></span>  
  
 <span data-ttu-id="20775-108">**Options d'agrégation**</span><span class="sxs-lookup"><span data-stu-id="20775-108">**Aggregation options**</span></span>  
 <span data-ttu-id="20775-109">Définit l'option d'agrégation de la partition.</span><span class="sxs-lookup"><span data-stu-id="20775-109">Specifies the aggregation option for the partition.</span></span>  
  
 <span data-ttu-id="20775-110">Le tableau ci-après répertorie les options d'agrégation disponibles.</span><span class="sxs-lookup"><span data-stu-id="20775-110">The following table lists the aggregation options that are available.</span></span>  
  
|<span data-ttu-id="20775-111">Option</span><span class="sxs-lookup"><span data-stu-id="20775-111">Option</span></span>|<span data-ttu-id="20775-112">Description</span><span class="sxs-lookup"><span data-stu-id="20775-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="20775-113">**Créer maintenant les agrégations pour la partition**</span><span class="sxs-lookup"><span data-stu-id="20775-113">**Design aggregations for the partition now**</span></span>|<span data-ttu-id="20775-114">Conçoit les agrégations de la nouvelle partition après que l'Assistant Partition a créé la partition.</span><span class="sxs-lookup"><span data-stu-id="20775-114">Designs aggregations for the new partition after the Partition Wizard creates the new partition.</span></span> <span data-ttu-id="20775-115">Cette option démarre l'Assistant Conception d'agrégation lorsque vous cliquez sur **Terminer** dans l'Assistant Partition.</span><span class="sxs-lookup"><span data-stu-id="20775-115">Selecting this option starts the Aggregation Design Wizard after you click **Finish** in the Partition Wizard.</span></span> <span data-ttu-id="20775-116">Pour plus d’informations sur l’Assistant Conception d’agrégation, consultez [Aide (F1) de l’Assistant Conception d’agrégation](aggregation-design-wizard-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="20775-116">For more information about the Aggregation Design Wizard, see [Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md).</span></span>|  
|<span data-ttu-id="20775-117">**Créer les agrégations ultérieurement**</span><span class="sxs-lookup"><span data-stu-id="20775-117">**Design the aggregations later**</span></span>|<span data-ttu-id="20775-118">Crée la partition sans concevoir d'agrégation à ce stade.</span><span class="sxs-lookup"><span data-stu-id="20775-118">Creates the partition without designing aggregations at this time.</span></span>|  
|<span data-ttu-id="20775-119">**Copier la structure de l'agrégation à partir d'une partition existante**</span><span class="sxs-lookup"><span data-stu-id="20775-119">**Copy the aggregation design from an existing partition**</span></span>|<span data-ttu-id="20775-120">Copie la conception d'agrégation depuis une partition existante dans le groupe de mesures vers la nouvelle partition.</span><span class="sxs-lookup"><span data-stu-id="20775-120">Copies the aggregation design from an existing partition in the measure group to the new partition.</span></span> <span data-ttu-id="20775-121">Cliquez sur cette option pour rendre l'option **Copier à partir de** disponible.</span><span class="sxs-lookup"><span data-stu-id="20775-121">Clicking this option makes the **Copy from** option available.</span></span> <span data-ttu-id="20775-122">Utilisez la zone **Copier à partir de** pour sélectionner la partition de la conception d'agrégation à copier.</span><span class="sxs-lookup"><span data-stu-id="20775-122">Use the **Copy from** option to select the partition from which to copy the aggregation design.</span></span><br /><br /> <span data-ttu-id="20775-123">Notez que les partitions qui peuvent être fusionnées ultérieurement doivent avoir la même structure de table et la même conception d’agrégation.</span><span class="sxs-lookup"><span data-stu-id="20775-123">Note that partitions that may be merged in the future must have the same table structure and aggregation design.</span></span> <span data-ttu-id="20775-124">Si vous fusionnez la nouvelle partition avec une partition existante dans le groupe de mesures, vous devez copier la conception d'agrégation existante dans la nouvelle partition.</span><span class="sxs-lookup"><span data-stu-id="20775-124">If you might merge the new partition with an existing partition in the measure group, you should copy the aggregation design of the existing partition into the new partition.</span></span>|  
  
 <span data-ttu-id="20775-125">**Déployer et traiter maintenant**</span><span class="sxs-lookup"><span data-stu-id="20775-125">**Deploy and Process Now**</span></span>  
 <span data-ttu-id="20775-126">Déploie et traite la partition dans l'instance [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] définie dans la page **Emplacements pour le traitement et le stockage**.</span><span class="sxs-lookup"><span data-stu-id="20775-126">Deploys and processes the partition to the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance specified on the **Processing and Storage Locations** page.</span></span> <span data-ttu-id="20775-127">L'Assistant déploie et traite la partition après que vous ayez cliqué sur **Terminer** dans cette page.</span><span class="sxs-lookup"><span data-stu-id="20775-127">The wizard deploys and processes the partition after you click **Finish** on this page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20775-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20775-128">See Also</span></span>  
 [<span data-ttu-id="20775-129">Partitions &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="20775-129">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
