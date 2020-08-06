---
title: Surveiller des Agents de réplication | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], agents
- Log Reader Agent, monitoring
- Replication Monitor, agents
- Merge Agent, monitoring
- Queue Reader Agent, monitoring
- Snapshot Agent, monitoring
- agents [SQL Server replication], monitoring
- Distribution Agent, monitoring
ms.assetid: d06ed24f-82d7-4b9e-9e40-cc9780476a71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: baa22ef9e9f7c4621f76838e82c309d17f1e12a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603387"
---
# <a name="monitor-replication-agents"></a><span data-ttu-id="b7363-102">Surveiller des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="b7363-102">Monitor Replication Agents</span></span>
  <span data-ttu-id="b7363-103">Le Moniteur de réplication [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] offre une vue systémique de l’activité de réplication, mais il permet aussi de trouver directement des informations sur un agent spécifique.</span><span class="sxs-lookup"><span data-stu-id="b7363-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor provides a systemic view of replication activity, but also makes it straightforward to find information on a specific agent.</span></span> <span data-ttu-id="b7363-104">La liste suivante comprend chacun des agents, les onglets du moniteur de réplication sur lesquels ils peuvent être trouvés et un lien vers une rubrique qui explique comment accéder à ces onglets :</span><span class="sxs-lookup"><span data-stu-id="b7363-104">The following list includes each agent, the tabs in the Replication Monitor on which it can be found, and a link to a topic that explains how to access these tabs:</span></span>  
  
-   <span data-ttu-id="b7363-105">Les agents suivants sont associés à des publications dans le moniteur de réplication :</span><span class="sxs-lookup"><span data-stu-id="b7363-105">The following agents are associated with publications in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="b7363-106">Agent d'instantané</span><span class="sxs-lookup"><span data-stu-id="b7363-106">Snapshot Agent</span></span>  
  
    -   <span data-ttu-id="b7363-107">l'Agent de lecture du journal ;</span><span class="sxs-lookup"><span data-stu-id="b7363-107">Log Reader Agent</span></span>  
  
    -   <span data-ttu-id="b7363-108">Agent de lecture de la file d'attente</span><span class="sxs-lookup"><span data-stu-id="b7363-108">Queue Reader Agent</span></span>  
  
     <span data-ttu-id="b7363-109">Accédez aux informations et aux tâches associées à ces agents par le biais des onglets suivants : **Agents** (disponible pour chaque serveur de publication et publication) et **Avertissements** (disponible pour chaque publication).</span><span class="sxs-lookup"><span data-stu-id="b7363-109">Access information and tasks associated with these agents through the following tabs: **Agents** (available for each Publisher and publication) and **Warnings** (available for each publication).</span></span> <span data-ttu-id="b7363-110">Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b7363-110">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="b7363-111">Les agents suivants sont associés à des abonnements dans le moniteur de réplication :</span><span class="sxs-lookup"><span data-stu-id="b7363-111">The following agents are associated with subscriptions in Replication Monitor:</span></span>  
  
    -   <span data-ttu-id="b7363-112">Agent de distribution</span><span class="sxs-lookup"><span data-stu-id="b7363-112">Distribution Agent</span></span>  
  
    -   <span data-ttu-id="b7363-113">Agent de fusion</span><span class="sxs-lookup"><span data-stu-id="b7363-113">Merge Agent</span></span>  
  
     <span data-ttu-id="b7363-114">Accédez aux informations et aux tâches associées à ces agents par le biais des onglets suivants : **Liste de suivi des abonnements** (disponible pour chaque serveur de publication) ou **Tous les abonnements** (disponible pour chaque publication).</span><span class="sxs-lookup"><span data-stu-id="b7363-114">Access information and tasks associated with these agents through the following tabs: **Subscription Watch List** (available for each Publisher) or the **All Subscriptions** tab (available for each publication).</span></span> <span data-ttu-id="b7363-115">Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b7363-115">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
## <a name="using-sql-server-management-studio-to-monitor-replication-agents"></a><span data-ttu-id="b7363-116">Utiliser SQL Server Management Studio pour surveiller les agents de réplication</span><span class="sxs-lookup"><span data-stu-id="b7363-116">Using SQL Server Management Studio to Monitor Replication Agents</span></span>  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="b7363-117">[!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] fournit les boîtes de dialogue suivantes pour la surveillance des agents de réplication :</span><span class="sxs-lookup"><span data-stu-id="b7363-117">[!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] provides the following dialog boxes for monitoring replication agents:</span></span>  
  
-   <span data-ttu-id="b7363-118">**Afficher l'état de l'Agent d'instantané** (pour toutes les publications)</span><span class="sxs-lookup"><span data-stu-id="b7363-118">**View Snapshot Agent Status** (for all publications)</span></span>  
  
-   <span data-ttu-id="b7363-119">**Afficher l'état de l'Agent de lecture du journal** (pour toutes les publications transactionnelles)</span><span class="sxs-lookup"><span data-stu-id="b7363-119">**View Log Reader Agent Status** (for all transactional publications)</span></span>  
  
-   <span data-ttu-id="b7363-120">**Afficher l'état de synchronisation** (pour tous les abonnements ; cette boîte de dialogue permet d'accéder à l'Agent de distribution et à l'Agent de fusion)</span><span class="sxs-lookup"><span data-stu-id="b7363-120">**View Synchronization Status** (for all subscriptions; this dialog box allows access to the Distribution Agent and the Merge Agent)</span></span>  
  
 <span data-ttu-id="b7363-121">Le moniteur de réplication donne des informations supplémentaires sur chaque agent et permet la surveillance de l'Agent de lecture de la file d'attente, s'il est utilisé.</span><span class="sxs-lookup"><span data-stu-id="b7363-121">Replication Monitor provides additional information about each agent and provides monitoring for the Queue Reader Agent, if it is used.</span></span> <span data-ttu-id="b7363-122">Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b7363-122">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
#### <a name="to-monitor-the-snapshot-agent-and-log-reader-agent"></a><span data-ttu-id="b7363-123">Pour surveiller l'Agent d'instantané et l'Agent de lecture du journal</span><span class="sxs-lookup"><span data-stu-id="b7363-123">To monitor the Snapshot Agent and Log Reader Agent</span></span>  
  
1.  <span data-ttu-id="b7363-124">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="b7363-124">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b7363-125">Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .</span><span class="sxs-lookup"><span data-stu-id="b7363-125">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="b7363-126">Cliquez avec le bouton droit sur une publication, puis cliquez sur **Afficher l'état de l'Agent de lecture du journal** ou sur **Afficher l'état de l'Agent d'instantané**.</span><span class="sxs-lookup"><span data-stu-id="b7363-126">Right-click a publication, and then click **View Log Reader Agent Status** or **View Snapshot Agent Status**.</span></span>  
  
4.  <span data-ttu-id="b7363-127">Dans la boîte de dialogue **Afficher l'état de l'Agent de lecture du journal** ou **Afficher l'état de l'Agent d'instantané** :</span><span class="sxs-lookup"><span data-stu-id="b7363-127">In the **View Log Reader Agent Status** or **View Snapshot Agent Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="b7363-128">Affichez l'état de l'agent.</span><span class="sxs-lookup"><span data-stu-id="b7363-128">View agent status.</span></span>  
  
    -   <span data-ttu-id="b7363-129">Démarrez ou arrêtez l'agent si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b7363-129">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="b7363-130">Cliquez sur **Moniteur** pour lancer le **moniteur de réplication**.</span><span class="sxs-lookup"><span data-stu-id="b7363-130">Click **Monitor** to launch **Replication Monitor**.</span></span>  
  
5.  <span data-ttu-id="b7363-131">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="b7363-131">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-publisher"></a><span data-ttu-id="b7363-132">Pour surveiller l'Agent de distribution et l'Agent de fusion (à partir du serveur de publication)</span><span class="sxs-lookup"><span data-stu-id="b7363-132">To monitor the Distribution Agent and Merge Agent (from the Publisher)</span></span>  
  
1.  <span data-ttu-id="b7363-133">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="b7363-133">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b7363-134">Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .</span><span class="sxs-lookup"><span data-stu-id="b7363-134">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="b7363-135">Développez la publication pour l'abonnement que vous voulez surveiller.</span><span class="sxs-lookup"><span data-stu-id="b7363-135">Expand the publication for the subscription you want to monitor.</span></span>  
  
4.  <span data-ttu-id="b7363-136">Cliquez avec le bouton droit sur l'abonnement, puis sur **Afficher l'état de synchronisation**.</span><span class="sxs-lookup"><span data-stu-id="b7363-136">Right-click the subscription, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="b7363-137">Dans la boîte de dialogue **Afficher l'état de synchronisation** :</span><span class="sxs-lookup"><span data-stu-id="b7363-137">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="b7363-138">Affichez l'état de l'agent.</span><span class="sxs-lookup"><span data-stu-id="b7363-138">View agent status.</span></span>  
  
    -   <span data-ttu-id="b7363-139">Démarrez ou arrêtez l'agent si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b7363-139">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="b7363-140">Pour les abonnements par envoi de données (push), cliquez sur **Moniteur** pour lancer le **moniteur de réplication**.</span><span class="sxs-lookup"><span data-stu-id="b7363-140">For push subscriptions, click **Monitor** to launch **Replication Monitor**.</span></span>  
  
    -   <span data-ttu-id="b7363-141">Pour les abonnements par extraction de données (pull), cliquez sur **Afficher l'historique des travaux** pour lancer la **Visionneuse du fichier journal**, qui affiche le contenu du journal de l'agent.</span><span class="sxs-lookup"><span data-stu-id="b7363-141">For pull subscriptions, click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
6.  <span data-ttu-id="b7363-142">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="b7363-142">Click **Close**.</span></span>  
  
#### <a name="to-monitor-the-distribution-agent-and-merge-agent-from-the-subscriber"></a><span data-ttu-id="b7363-143">Pour surveiller l'Agent de distribution et l'Agent de fusion (à partir de l'Abonné)</span><span class="sxs-lookup"><span data-stu-id="b7363-143">To monitor the Distribution Agent and Merge Agent (from the Subscriber)</span></span>  
  
1.  <span data-ttu-id="b7363-144">Connectez-vous à l'Abonné dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="b7363-144">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b7363-145">Développez le dossier **Réplication** , puis développez le dossier **Abonnements locaux** .</span><span class="sxs-lookup"><span data-stu-id="b7363-145">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="b7363-146">Cliquez avec le bouton droit sur l'abonnement que vous voulez surveiller, puis sur **Afficher l'état de synchronisation**.</span><span class="sxs-lookup"><span data-stu-id="b7363-146">Right-click the subscription you want to monitor, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="b7363-147">Dans la boîte de dialogue **Afficher l'état de synchronisation** :</span><span class="sxs-lookup"><span data-stu-id="b7363-147">In the **View Synchronization Status** dialog box:</span></span>  
  
    -   <span data-ttu-id="b7363-148">Affichez l'état de l'agent.</span><span class="sxs-lookup"><span data-stu-id="b7363-148">View agent status.</span></span>  
  
    -   <span data-ttu-id="b7363-149">Démarrez ou arrêtez l'agent si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b7363-149">Start or stop the agent if necessary.</span></span>  
  
    -   <span data-ttu-id="b7363-150">Cliquez sur **Afficher l'historique des travaux** pour lancer la **Visionneuse du fichier journal**, qui affiche le contenu du journal de l'agent.</span><span class="sxs-lookup"><span data-stu-id="b7363-150">Click **View Job History** to launch the **Log File Viewer**, which displays output from the agent log.</span></span>  
  
5.  <span data-ttu-id="b7363-151">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="b7363-151">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7363-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7363-152">See Also</span></span>  
 <span data-ttu-id="b7363-153">[Surveillance de la réplication](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="b7363-153">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 [<span data-ttu-id="b7363-154">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="b7363-154">Replication Agents Overview</span></span>](../agents/replication-agents-overview.md)  
  
  
