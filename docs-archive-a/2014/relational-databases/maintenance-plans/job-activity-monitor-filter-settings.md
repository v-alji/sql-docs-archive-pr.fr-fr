---
title: Moniteur d’activité des travaux (Paramètres du filtre) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.jobactivitymon.filter.f1
ms.assetid: 89cb0055-5262-447f-8464-7203d4caba78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feba7b992d5d1d375b93df12135487a092792ee1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612306"
---
# <a name="job-activity-monitor-filter-settings"></a><span data-ttu-id="46299-102">Moniteur d'activité des travaux (Paramètres du filtre)</span><span class="sxs-lookup"><span data-stu-id="46299-102">Job Activity Monitor (Filter Settings)</span></span>
  <span data-ttu-id="46299-103">Cette page vous permet de réduire le nombre de lignes visibles dans le Moniteur d'activité des travaux.</span><span class="sxs-lookup"><span data-stu-id="46299-103">Use this page to reduce the number of rows visible in the Job Activity Monitor.</span></span> <span data-ttu-id="46299-104">Entrez des critères dans une ou plusieurs des zones disponibles, pour afficher uniquement les lignes qui correspondent aux valeurs spécifiées.</span><span class="sxs-lookup"><span data-stu-id="46299-104">Enter criteria in one or several of the available boxes, to show only the rows that meet the specified values.</span></span> <span data-ttu-id="46299-105">Certaines zones, telles que **État** ou **Type de blocage** , proposent un nombre défini de valeurs possibles, fournies dans une liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="46299-105">Some of the boxes, such as **Status** or **Blocking Type** offer a finite number of possible values, provided by a drop-down list.</span></span> <span data-ttu-id="46299-106">D’autres, telles que **Application** , permettent d’entrer n’importe quelle valeur et autant de valeurs que vous le souhaitez, sous la forme d’une liste dont les valeurs sont séparées par une virgule.</span><span class="sxs-lookup"><span data-stu-id="46299-106">Others, such as **Application,** allow you to enter whatever value and as many values as you wish, as a comma separated list.</span></span> <span data-ttu-id="46299-107">Les icônes de la barre d'outils vous permettent de trier les zones disponibles par catégorie ou par ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="46299-107">Toolbar icons allow you to sort the available boxes by category or alphabetically.</span></span> <span data-ttu-id="46299-108">Cliquez sur des critères pour afficher une brève description de chacun d'eux.</span><span class="sxs-lookup"><span data-stu-id="46299-108">Click the criteria to show a short description of the each one.</span></span>  
  
 <span data-ttu-id="46299-109">Pour filtrer le Moniteur d’activité des travaux, fournissez autant de critères de filtre que vous le souhaitez, cliquez sur **Appliquer le filtre**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="46299-109">To filter the Job Activity Monitor, provide as many filter criteria as you want, click **Apply filter**, and then click **OK**.</span></span>  
  
## <a name="all-jobs"></a><span data-ttu-id="46299-110">Tous les travaux</span><span class="sxs-lookup"><span data-stu-id="46299-110">All Jobs</span></span>  
 <span data-ttu-id="46299-111">Ce groupe de critères de filtre est disponible lors du filtrage du Moniteur d'activité des travaux.</span><span class="sxs-lookup"><span data-stu-id="46299-111">This group of filter criteria is available when filtering the Job Activity Monitor.</span></span>  
  
 <span data-ttu-id="46299-112">**Nom**</span><span class="sxs-lookup"><span data-stu-id="46299-112">**Name**</span></span>  
 <span data-ttu-id="46299-113">Permet de filtrer les travaux par leur nom.</span><span class="sxs-lookup"><span data-stu-id="46299-113">Filter jobs by name.</span></span>  
  
 <span data-ttu-id="46299-114">**Prochaine exécution**</span><span class="sxs-lookup"><span data-stu-id="46299-114">**Next Run**</span></span>  
 <span data-ttu-id="46299-115">Permet de filtrer par la date de prochaine exécution planifiée.</span><span class="sxs-lookup"><span data-stu-id="46299-115">Filter by the date next scheduled to run.</span></span>  
  
 <span data-ttu-id="46299-116">**Exécutable**</span><span class="sxs-lookup"><span data-stu-id="46299-116">**Runnable**</span></span>  
 <span data-ttu-id="46299-117">Permet d'afficher les travaux qui peuvent être exécutés ou les travaux qui ne le peuvent pas.</span><span class="sxs-lookup"><span data-stu-id="46299-117">View jobs that can be run, or jobs that cannot be run.</span></span> <span data-ttu-id="46299-118">Sélectionnez **Oui** pour visualiser uniquement les travaux exécutables, **Non** pour visualiser uniquement les travaux non exécutables ou **Tous** pour visualiser les deux types de travaux.</span><span class="sxs-lookup"><span data-stu-id="46299-118">Select **Yes** to view only jobs that can be run, select **No** to view only jobs that cannot be run, or select **All** to view both jobs that can be run and those that cannot.</span></span>  
  
 <span data-ttu-id="46299-119">**Dernière exécution**</span><span class="sxs-lookup"><span data-stu-id="46299-119">**Last Run**</span></span>  
 <span data-ttu-id="46299-120">Permet de filtrer par la date de dernière exécution.</span><span class="sxs-lookup"><span data-stu-id="46299-120">Filter by the date last run.</span></span>  
  
 <span data-ttu-id="46299-121">**Résultats de la dernière exécution**</span><span class="sxs-lookup"><span data-stu-id="46299-121">**Last Run Outcome**</span></span>  
 <span data-ttu-id="46299-122">Permet de filtrer les travaux par l'état de leur dernière exécution.</span><span class="sxs-lookup"><span data-stu-id="46299-122">Filter jobs by the status last time the jobs were run.</span></span>  
  
 <span data-ttu-id="46299-123">**Activé**</span><span class="sxs-lookup"><span data-stu-id="46299-123">**Enabled**</span></span>  
 <span data-ttu-id="46299-124">Permet d'afficher uniquement les travaux activés ou non activés</span><span class="sxs-lookup"><span data-stu-id="46299-124">View only enabled or not enabled jobs</span></span>  
  
 <span data-ttu-id="46299-125">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="46299-125">**Category**</span></span>  
 <span data-ttu-id="46299-126">Permet de filtrer les travaux par catégorie.</span><span class="sxs-lookup"><span data-stu-id="46299-126">Filter jobs by the job category.</span></span>  
  
 <span data-ttu-id="46299-127">**Planifié**</span><span class="sxs-lookup"><span data-stu-id="46299-127">**Scheduled**</span></span>  
 <span data-ttu-id="46299-128">Permet d'afficher tous les travaux avec planification ou sans planification.</span><span class="sxs-lookup"><span data-stu-id="46299-128">View all jobs with schedules, or without schedules.</span></span>  
  
 <span data-ttu-id="46299-129">**État**</span><span class="sxs-lookup"><span data-stu-id="46299-129">**Status**</span></span>  
 <span data-ttu-id="46299-130">Permet de filtrer les travaux par leur état.</span><span class="sxs-lookup"><span data-stu-id="46299-130">Filter jobs by the status.</span></span>  
  
## <a name="description-area"></a><span data-ttu-id="46299-131">Zone Description</span><span class="sxs-lookup"><span data-stu-id="46299-131">Description Area</span></span>  
 <span data-ttu-id="46299-132">**Zone de description**</span><span class="sxs-lookup"><span data-stu-id="46299-132">**Description Box**</span></span>  
 <span data-ttu-id="46299-133">Cette zone sans nom fournit une brève description des critères lors de leur sélection.</span><span class="sxs-lookup"><span data-stu-id="46299-133">This unnamed box provides a short description of the criteria as they are selected.</span></span>  
  
 <span data-ttu-id="46299-134">**Appliquer le filtre**</span><span class="sxs-lookup"><span data-stu-id="46299-134">**Apply filter**</span></span>  
 <span data-ttu-id="46299-135">Pour appliquer le filtre, cliquez sur **appliquer le filtre** , puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="46299-135">To apply the filter, click **Apply filter** and then click **OK**.</span></span> <span data-ttu-id="46299-136">Pour conserver les paramètres de filtre dans la boîte de dialogue **paramètres de filtre** , sans les appliquer, désactivez l’option **appliquer le filtre**, puis cliquez sur **OK**pour afficher toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="46299-136">To retain the filter settings in the **Filter Settings** dialog box, but not apply them, uncheck **Apply filter**, and then click **OK**, to display all rows.</span></span>  
  
 <span data-ttu-id="46299-137">**Clear**</span><span class="sxs-lookup"><span data-stu-id="46299-137">**Clear**</span></span>  
 <span data-ttu-id="46299-138">Rétablit les paramètres par défaut du filtre.</span><span class="sxs-lookup"><span data-stu-id="46299-138">Returns the filter settings back to the default settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46299-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46299-139">See Also</span></span>  
 [<span data-ttu-id="46299-140">Surveiller l'activité des travaux</span><span class="sxs-lookup"><span data-stu-id="46299-140">Monitor Job Activity</span></span>](../../ssms/agent/monitor-job-activity.md)  
  
  
