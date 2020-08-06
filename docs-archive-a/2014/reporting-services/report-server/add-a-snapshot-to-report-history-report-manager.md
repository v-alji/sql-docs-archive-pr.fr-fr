---
title: Ajouter un instantané à un historique de rapport (Gestionnaire de rapports) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
helpviewer_keywords:
- report history [Reporting Services], adding snapshots
- historical data [Reporting Services]
- snapshots [Reporting Services], adding report snapshots
- adding snapshots to report history
- report snapshots [Reporting Services], adding
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 84d4c264ab0b82fca2a34e6356b53113d63e6994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611581"
---
# <a name="add-a-snapshot-to-report-history-report-manager"></a><span data-ttu-id="1ed90-102">ajout d'un instantané à un historique de rapport (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="1ed90-102">Add a Snapshot to Report History (Report Manager)</span></span>

<span data-ttu-id="1ed90-103">L'historique de rapport est un ensemble d'instantanés de rapport que vous créez au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="1ed90-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="1ed90-104">Un instantané de rapport est un rapport contenant des informations de mise en page et des résultats de requêtes récupérés à un moment précis.</span><span class="sxs-lookup"><span data-stu-id="1ed90-104">A report snapshot is a report that contains layout information and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="1ed90-105">Contrairement aux rapports à la demande, qui récupèrent les résultats des requêtes récentes lorsque vous les sélectionnez, les instantanés de rapport sont traités par planification, puis enregistrés sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1ed90-105">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="1ed90-106">Lorsque vous sélectionnez un instantané de rapport pour le visualiser, le serveur de rapports récupère le rapport stocké dans la base de données du serveur de rapports, puis affiche les données et la mise en page telles qu'elles étaient lors de la création de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="1ed90-106">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
<span data-ttu-id="1ed90-107">Les instantanés de rapport ne sont pas enregistrés dans un format de rendu particulier.</span><span class="sxs-lookup"><span data-stu-id="1ed90-107">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="1ed90-108">Ils sont générés dans un format d'affichage final (par exemple, au format HTML) uniquement à la demande d'un utilisateur ou d'une application.</span><span class="sxs-lookup"><span data-stu-id="1ed90-108">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="1ed90-109">Le rendu différé permet de disposer d'un instantané portable.</span><span class="sxs-lookup"><span data-stu-id="1ed90-109">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="1ed90-110">Le rendu du rapport peut être effectué dans le format approprié pour le périphérique ou le navigateur Web à l'origine de la demande.</span><span class="sxs-lookup"><span data-stu-id="1ed90-110">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
## <a name="to-manually-add-snapshots-to-report-history"></a><span data-ttu-id="1ed90-111">Pour ajouter manuellement des instantanés à un historique de rapport</span><span class="sxs-lookup"><span data-stu-id="1ed90-111">To manually add snapshots to report history</span></span>

1. <span data-ttu-id="1ed90-112">Dans le Gestionnaire de rapports, accédez à la page **Contenu** , pointez sur l’élément pour lequel vous souhaitez consulter l’historique et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="1ed90-112">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>
  
2. <span data-ttu-id="1ed90-113">Dans le menu déroulant, cliquez sur **Afficher l’historique du rapport**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-113">In the drop-down menu, click **View Report History**.</span></span>  
  
3. <span data-ttu-id="1ed90-114">Cliquez sur **Nouvel instantané**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-114">Click **New Snapshot**.</span></span> <span data-ttu-id="1ed90-115">Un instantané est créé dans la colonne **Lors de l’exécution** .</span><span class="sxs-lookup"><span data-stu-id="1ed90-115">A new snapshot is created in the **When Run** column.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1ed90-116">Pour effectuer cette opération, l’historique de rapport doit être configuré par l’administrateur pour **Autoriser la création manuelle de l’historique**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-116">In order to do this, the report history must be configured by the administrator to **Allow history to be created manually**.</span></span> <span data-ttu-id="1ed90-117">Pour plus d’informations, consultez [Limiter l’historique de rapport &#40;Gestionnaire de rapports&#41;](../reports/limit-report-history-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1ed90-117">For more information, see [Limit Report History &#40;Report Manager&#41;](../reports/limit-report-history-report-manager.md).</span></span>

4. <span data-ttu-id="1ed90-118">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-118">Click **Apply**.</span></span>

## <a name="to-automatically-add-all-snapshots-to-report-history"></a><span data-ttu-id="1ed90-119">Pour ajouter automatiquement tous les instantanés à un historique de rapport</span><span class="sxs-lookup"><span data-stu-id="1ed90-119">To automatically add all snapshots to report history</span></span>  
  
1. <span data-ttu-id="1ed90-120">Pour un rapport déjà configuré pour s'exécuter en tant qu'instantané d'exécution de rapport, vous pouvez définir des propriétés supplémentaires afin d'enregistrer une copie de l'instantané dans l'historique de rapport chaque fois qu'il est actualisé.</span><span class="sxs-lookup"><span data-stu-id="1ed90-120">For a report that is already configured to run as a report execution snapshot, you can set additional properties to save a copy of the snapshot to report history each time the snapshot is refreshed.</span></span>  
  
2. <span data-ttu-id="1ed90-121">Dans le Gestionnaire de rapports, accédez à la page **Contenu** , pointez sur l’élément pour lequel vous souhaitez consulter l’historique et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="1ed90-121">In Report Manager, navigate to the **Contents** page, hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
3. <span data-ttu-id="1ed90-122">Dans le menu déroulant, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-122">In the drop-down menu, click **Manage**.</span></span>  
  
4. <span data-ttu-id="1ed90-123">Cliquez sur **Options d’instantanés**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-123">Click **Snapshot Options**.</span></span>  
  
5. <span data-ttu-id="1ed90-124">Cochez la case **Stocker toutes les captures instantanées d’exécution de rapport dans l’historique**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-124">Select the check box for **Store all report execution snapshots in history**.</span></span>  
  
6. <span data-ttu-id="1ed90-125">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-125">Click **Apply**.</span></span>  
  
### <a name="to-automatically-add-snapshots-to-report-history-based-on-a-schedule"></a><span data-ttu-id="1ed90-126">Pour ajouter automatiquement tous les instantanés à un historique de rapport planifié</span><span class="sxs-lookup"><span data-stu-id="1ed90-126">To automatically add snapshots to report history based on a schedule</span></span>  
  
1. <span data-ttu-id="1ed90-127">Dans le Gestionnaire de rapports, accédez à la page **Contenu** , pointez sur l’élément pour lequel vous souhaitez consulter l’historique et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="1ed90-127">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
2. <span data-ttu-id="1ed90-128">Dans le menu déroulant, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-128">In the drop-down menu, click **Manage**.</span></span>  
  
3. <span data-ttu-id="1ed90-129">Cliquez sur **Options d’instantanés**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-129">Click **Snapshot Options**.</span></span>  
  
4. <span data-ttu-id="1ed90-130">Cochez la case **Utilisez la planification ci-dessous pour ajouter des instantanés à l’historique de rapport**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-130">Select the check box for **Use the following schedule to add snapshots to report history**.</span></span> <span data-ttu-id="1ed90-131">Effectuez une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ed90-131">Perform one of the following:</span></span>  
  
    - <span data-ttu-id="1ed90-132">Sélectionnez **Planification spécifique aux rapports**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-132">Select **Report-specific schedule**.</span></span> <span data-ttu-id="1ed90-133">Indiquez les détails de la planification, sélectionnez des dates de début et de fin pour cette opération, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-133">Fill in the schedule details, select the start and end dates for the schedule, and then click **OK**.</span></span>  
  
    - <span data-ttu-id="1ed90-134">Sélectionnez **Planification partagée**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-134">Select **Shared schedule**.</span></span> <span data-ttu-id="1ed90-135">Dans la liste, désignez la planification de votre choix.</span><span class="sxs-lookup"><span data-stu-id="1ed90-135">From the list, select the preferred schedule.</span></span>  
  
5. <span data-ttu-id="1ed90-136">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="1ed90-136">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed90-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ed90-137">See Also</span></span>

- [<span data-ttu-id="1ed90-138">Configurer les propriétés d’exécution d’un rapport &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="1ed90-138">Configure Execution Properties for a Report  &#40;Report Manager&#41;</span></span>](../reports/configure-execution-properties-for-a-report-report-manager.md)
- [<span data-ttu-id="1ed90-139">Ouvrir et fermer un rapport &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="1ed90-139">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)
- [<span data-ttu-id="1ed90-140">Limiter l’historique de rapport &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="1ed90-140">Limit Report History &#40;Report Manager&#41;</span></span>](../reports/limit-report-history-report-manager.md)
- [<span data-ttu-id="1ed90-141">Planifications</span><span class="sxs-lookup"><span data-stu-id="1ed90-141">Schedules</span></span>](../subscriptions/schedules.md)   
- [<span data-ttu-id="1ed90-142">Gestionnaire de rapports &#40;SSRS en mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="1ed90-142">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)