---
title: Traiter les partitions de modèles tabulaires (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6c498d2b-22d6-4661-bc21-2ee708336c8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 496874707bd4030a98b1794fe7513d1d857390ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696115"
---
# <a name="process-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="46714-102">Traiter les partitions de modèles tabulaires (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="46714-102">Process Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="46714-103">Les partitions divisent une table en sections logiques.</span><span class="sxs-lookup"><span data-stu-id="46714-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="46714-104">Chaque partition peut ensuite être traitée (actualisée) indépendamment d'autres partitions.</span><span class="sxs-lookup"><span data-stu-id="46714-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="46714-105">Les tâches de cette rubrique décrivent comment traiter les partitions dans une base de données model à l'aide de la boîte de dialogue **Traiter la ou les partitions** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46714-105">The tasks in this topic describe how to process partitions in a model database by using the **Process Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-process-a-partition"></a><a name="bkmk_create_new"></a> <span data-ttu-id="46714-106">Pour traiter une partition</span><span class="sxs-lookup"><span data-stu-id="46714-106">To process a partition</span></span>  
  
1.  <span data-ttu-id="46714-107">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquez avec le bouton droit sur la table qui contient les partitions à traiter, puis sélectionnez **Partitions**.</span><span class="sxs-lookup"><span data-stu-id="46714-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on the table that has the partitions you want to process, and then click **Partitions**.</span></span>  
  
2.  <span data-ttu-id="46714-108">Dans la boîte de dialogue **Partitions** , dans **Partitions**, cliquez sur le bouton Traiter.</span><span class="sxs-lookup"><span data-stu-id="46714-108">In the **Partitions** dialog box, in **Partitions**, click on the Process button.</span></span>  
  
3.  <span data-ttu-id="46714-109">Dans la boîte de dialogue **traiter la ou les partitions** , dans la zone de liste **mode** , sélectionnez l’un des modes de traitement suivants :</span><span class="sxs-lookup"><span data-stu-id="46714-109">In the **Process Partition(s)** dialog box, in the **Mode** listbox, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="46714-110">Mode</span><span class="sxs-lookup"><span data-stu-id="46714-110">Mode</span></span>|<span data-ttu-id="46714-111">Description</span><span class="sxs-lookup"><span data-stu-id="46714-111">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="46714-112">**Traiter par défaut**</span><span class="sxs-lookup"><span data-stu-id="46714-112">**Process Default**</span></span>|<span data-ttu-id="46714-113">Détecte l'état de traitement d'un objet de partition et effectue le traitement nécessaire pour faire passer les objets de partition non traités ou traités partiellement dans un état de traitement complet.</span><span class="sxs-lookup"><span data-stu-id="46714-113">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="46714-114">Les données des partitions et des tables vides sont chargées ; les hiérarchies, les colonnes calculées et les relations sont créées ou reconstruites.</span><span class="sxs-lookup"><span data-stu-id="46714-114">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="46714-115">**Traiter entièrement**</span><span class="sxs-lookup"><span data-stu-id="46714-115">**Process Full**</span></span>|<span data-ttu-id="46714-116">Traite un objet de partition et tous les objets qu'il contient.</span><span class="sxs-lookup"><span data-stu-id="46714-116">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="46714-117">Lorsque la commande Traiter entièrement est exécutée pour un objet qui a déjà été traité, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supprime toutes les données de l'objet, puis traite l'objet.</span><span class="sxs-lookup"><span data-stu-id="46714-117">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="46714-118">Ce type de traitement est obligatoire lorsqu'une modification structurelle a été apportée à un objet.</span><span class="sxs-lookup"><span data-stu-id="46714-118">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="46714-119">**Traiter des données**</span><span class="sxs-lookup"><span data-stu-id="46714-119">**Process Data**</span></span>|<span data-ttu-id="46714-120">Chargez les données dans une partition ou une table sans reconstruire les hiérarchies ou les relations ni recalculer les colonnes calculées et les mesures.</span><span class="sxs-lookup"><span data-stu-id="46714-120">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="46714-121">**Traiter l'effacement**</span><span class="sxs-lookup"><span data-stu-id="46714-121">**Process Clear**</span></span>|<span data-ttu-id="46714-122">Supprime toutes les données d'une partition.</span><span class="sxs-lookup"><span data-stu-id="46714-122">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="46714-123">**Traiter l'ajout**</span><span class="sxs-lookup"><span data-stu-id="46714-123">**Process Add**</span></span>|<span data-ttu-id="46714-124">Mise à jour incrémentielle de la partition avec de nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="46714-124">Incrementally update partition with new data.</span></span>|  
  
4.  <span data-ttu-id="46714-125">Dans la colonne de case à cocher **Traiter** , sélectionnez les partitions à traiter avec le mode sélectionné, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="46714-125">In the **Process** checkbox column, select the partitions you want to process with the selected mode, and then click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46714-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46714-126">See Also</span></span>  
 <span data-ttu-id="46714-127">[Partitions de modèles tabulaires &#40;&#41;SSAS tabulaire](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="46714-127">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="46714-128">Créer et gérer des partitions de modèles tabulaires &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="46714-128">Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](create-and-manage-tabular-model-partitions-ssas-tabular.md)  
  
  
