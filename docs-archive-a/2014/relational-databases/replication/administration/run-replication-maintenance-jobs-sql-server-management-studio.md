---
title: Exécuter des travaux de maintenance de réplication (SQL Server Management Studio)| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server replication]
ms.assetid: 0dc485a0-5a50-41eb-a29d-f2b2fb920174
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9dc27c65e96a9f956ffa6d3edf9c72ed52f721a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705080"
---
# <a name="run-replication-maintenance-jobs-sql-server-management-studio"></a><span data-ttu-id="b0c76-102">Exécuter des travaux de maintenance de réplication (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b0c76-102">Run Replication Maintenance Jobs (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b0c76-103">Les travaux de maintenance de la réplication sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="b0c76-103">Replication uses the following maintenance jobs:</span></span>  
  
-   <span data-ttu-id="b0c76-104">**Réinitialiser les abonnements présentant des erreurs de validation de données**</span><span class="sxs-lookup"><span data-stu-id="b0c76-104">**Reinitialize subscriptions having data validation failures**</span></span>
-   <span data-ttu-id="b0c76-105">**Nettoyage de l'historique de l'agent : distribution**</span><span class="sxs-lookup"><span data-stu-id="b0c76-105">**Agent history clean up: distribution**</span></span>
-   <span data-ttu-id="b0c76-106">**Actualisateur d'analyse de réplication pour la distribution.**</span><span class="sxs-lookup"><span data-stu-id="b0c76-106">**Replication monitoring refresher for distribution.**</span></span>
-   <span data-ttu-id="b0c76-107">**Contrôle des agents de réplication**</span><span class="sxs-lookup"><span data-stu-id="b0c76-107">**Replication agents checkup**</span></span>
-   <span data-ttu-id="b0c76-108">**Nettoyage de la distribution : distribution**</span><span class="sxs-lookup"><span data-stu-id="b0c76-108">**Distribution clean up: distribution**</span></span>
-   <span data-ttu-id="b0c76-109">**Nettoyage de l'abonnement expiré**</span><span class="sxs-lookup"><span data-stu-id="b0c76-109">**Expired subscription clean up**</span></span>  
  
 <span data-ttu-id="b0c76-110">Démarrez et arrêtez ces travaux à partir du dossier **Travaux** de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] et à partir de l’onglet **Agents** du moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="b0c76-110">Start and stop these jobs from the **Jobs** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="b0c76-111">Pour plus d’informations sur le démarrage du Moniteur de réplication, consultez [Démarrer le Moniteur de réplication](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b0c76-111">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span> <span data-ttu-id="b0c76-112">Affichez et modifiez les propriétés de chaque travail dans la boîte de dialogue **Propriétés du travail - \<Job>** , qui est disponible à partir du même dossier et du même onglet.</span><span class="sxs-lookup"><span data-stu-id="b0c76-112">View and modify properties for each job in the **Job Properties - \<Job>** dialog box, which is available from the same folder and tab.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="b0c76-113">Pour démarrer ou arrêter un travail de maintenance de réplication dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0c76-113">To start or stop a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="b0c76-114">Connectez-vous au serveur de distribution dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="b0c76-114">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b0c76-115">Développez le dossier **Agent SQL Server** puis développez le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="b0c76-115">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="b0c76-116">Cliquez avec le bouton droit sur un travail, puis cliquez sur **Démarrer le travail** ou sur **Arrêter le travail**.</span><span class="sxs-lookup"><span data-stu-id="b0c76-116">Right-click a job, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="b0c76-117">Pour démarrer ou arrêter un travail de maintenance de réplication dans le moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="b0c76-117">To start or stop a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="b0c76-118">Développez un groupe du serveur de publication dans le moniteur de réplication, puis sélectionnez un serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="b0c76-118">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="b0c76-119">Cliquez sur l'onglet **Agents** .</span><span class="sxs-lookup"><span data-stu-id="b0c76-119">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="b0c76-120">Cliquez avec le bouton droit sur un travail dans la grille, puis cliquez sur **Démarrer le travail** ou sur **Arrêter le travail**.</span><span class="sxs-lookup"><span data-stu-id="b0c76-120">Right-click a job in the grid, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="b0c76-121">Pour afficher et modifier les propriétés d'un travail de maintenance de réplication dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="b0c76-121">To view and modify properties for a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="b0c76-122">Connectez-vous au serveur de distribution dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="b0c76-122">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b0c76-123">Développez le dossier **Agent SQL Server** puis développez le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="b0c76-123">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="b0c76-124">Cliquez avec le bouton droit sur un travail, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b0c76-124">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b0c76-125">Dans la boîte de dialogue **Propriétés du travail - \<Job>** , modifiez les propriétés selon les besoins, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0c76-125">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="b0c76-126">Pour afficher et modifier les propriétés d'un travail de maintenance de réplication dans le moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="b0c76-126">To view and modify properties for a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="b0c76-127">Développez un groupe du serveur de publication dans le moniteur de réplication, puis sélectionnez un serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="b0c76-127">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="b0c76-128">Cliquez sur l'onglet **Agents** .</span><span class="sxs-lookup"><span data-stu-id="b0c76-128">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="b0c76-129">Cliquez avec le bouton droit sur un travail dans la grille, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b0c76-129">Right-click a job in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b0c76-130">Dans la boîte de dialogue **Propriétés du travail - \<Job>** , modifiez les propriétés selon les besoins, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0c76-130">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c76-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0c76-131">See Also</span></span>  
 <span data-ttu-id="b0c76-132">[Démarrer et arrêter un Agent de réplication &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b0c76-132">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="b0c76-133">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="b0c76-133">[View Information and Perform Tasks using Replication Monitor](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="b0c76-134">Administration de l’Agent de réplication</span><span class="sxs-lookup"><span data-stu-id="b0c76-134">Replication Agent Administration</span></span>](../agents/replication-agent-administration.md)  
  
  
