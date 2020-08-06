---
title: Traiter des données (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d88f2dc9-2933-4be5-9bf3-48ffbc2d0a1a
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2066cb6d871f43dda719cab3539253db97bfca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708719"
---
# <a name="process-data-ssas-tabular"></a><span data-ttu-id="b8e39-102">Traiter les données (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="b8e39-102">Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="b8e39-103">Lorsque vous importez des données dans un modèle tabulaire, en mode mis en cache, vous capturez un instantané de ces données au moment de l'importation.</span><span class="sxs-lookup"><span data-stu-id="b8e39-103">When you import data into a tabular model, in Cached mode, you are capturing a snapshot of that data at the time of import.</span></span> <span data-ttu-id="b8e39-104">Dans certains cas, ces données peuvent ne jamais changer et elles n'ont pas besoin d'être mises à jour dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="b8e39-104">In some cases, that data may never change and it does not need to be updated in the model.</span></span> <span data-ttu-id="b8e39-105">Toutefois, il est plus probable que les données que vous importez subissent des modifications régulièrement, et pour que votre modèle reflète les données les plus récentes des sources de données, il est nécessaire de traiter (actualiser) ces données et de recalculer les données calculées.</span><span class="sxs-lookup"><span data-stu-id="b8e39-105">However, it is more likely that the data you are importing from changes regularly, and in order for your model to reflect the most recent data from the data sources, it is necessary to process (refresh) the data and re-calculate calculated data.</span></span> <span data-ttu-id="b8e39-106">Pour mettre à jour les données dans votre modèle, effectuez une action de traitement sur toutes les tables, sur une table individuelle, par partition ou par connexion de source de données.</span><span class="sxs-lookup"><span data-stu-id="b8e39-106">To update the data in your model, you perform a process action on all tables, on an individual table, by a partition, or by a data source connection.</span></span>  
  
 <span data-ttu-id="b8e39-107">Lors de la création de votre projet de modèle, toutes les actions de traitement doivent être initiées manuellement dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8e39-107">When authoring your model project, process actions must be initiated manually in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="b8e39-108">Une fois qu'un modèle a été déployé, les opérations de traitement peuvent être effectuées en utilisant [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou planifiées à l'aide d'un script.</span><span class="sxs-lookup"><span data-stu-id="b8e39-108">After a model has been deployed, process operations can be performed by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or scheduled by using a script.</span></span> <span data-ttu-id="b8e39-109">Les tâches décrites ici concernent toutes des actions de traitement que vous pouvez effectuer pendant la création de modèles dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8e39-109">Tasks described here all pertain to process actions that you can do during model authoring in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="b8e39-110">Pour plus d'informations sur les actions de traitement pour un modèle déployé, consultez [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="b8e39-110">For more information about process actions for a deployed model, see [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b8e39-111">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="b8e39-111">Related Tasks</span></span>  
  
|<span data-ttu-id="b8e39-112">Rubrique</span><span class="sxs-lookup"><span data-stu-id="b8e39-112">Topic</span></span>|<span data-ttu-id="b8e39-113">Description</span><span class="sxs-lookup"><span data-stu-id="b8e39-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b8e39-114">Traiter manuellement les données &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="b8e39-114">Manually Process Data &#40;SSAS Tabular&#41;</span></span>](manually-process-data-ssas-tabular.md)|<span data-ttu-id="b8e39-115">Explique comment traiter manuellement des données de l'espace de travail de modèle.</span><span class="sxs-lookup"><span data-stu-id="b8e39-115">Describes how to manually process model workspace data.</span></span>|  
|[<span data-ttu-id="b8e39-116">Dépanner le traitement des données &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="b8e39-116">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)|<span data-ttu-id="b8e39-117">Explique comment résoudre les problèmes liés aux opérations de traitement.</span><span class="sxs-lookup"><span data-stu-id="b8e39-117">Describes how to troubleshoot process operations.</span></span>|  
  
  
