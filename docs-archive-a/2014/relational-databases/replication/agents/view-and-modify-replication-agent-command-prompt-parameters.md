---
title: Afficher et modifier les paramètres d’invite de commandes de l’agent de réplication (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], command prompt parameters
ms.assetid: 45f2e781-c21d-4b44-8992-89f60fb3d022
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 752f674c21bb66c7b64e399e30e4917512431195
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601397"
---
# <a name="view-and-modify-replication-agent-command-prompt-parameters-sql-server-management-studio"></a><span data-ttu-id="f8bb3-102">Afficher et modifier des paramètres d'invite de commandes d'un Agent de réplication (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f8bb3-102">View and Modify Replication Agent Command Prompt Parameters (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f8bb3-103">Les Agents de réplication sont des fichiers exécutables qui acceptent des paramètres de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-103">Replication agents are executables that accept command line parameters.</span></span> <span data-ttu-id="f8bb3-104">Par défaut, les Agents [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] s'exécutent dans des étapes de travail d'Agent , et ces paramètres peuvent être affichés et modifiés à l'aide de la boîte de dialogue **Propriétés du travail – \<Job>** .</span><span class="sxs-lookup"><span data-stu-id="f8bb3-104">By default, agents run under [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job steps, so these parameters can be viewed and modified using the **Job Properties - \<Job>** dialog box.</span></span> <span data-ttu-id="f8bb3-105">Cette boîte de dialogue est disponible dans le dossier **Travaux** de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] et sous l'onglet **Agents** du moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-105">This dialog box is available from the **Jobs** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="f8bb3-106">Pour plus d’informations sur le démarrage du Moniteur de réplication, consultez [Démarrer le Moniteur de réplication](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="f8bb3-106">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8bb3-107">Les modifications apportées aux paramètres prennent effet au prochain démarrage de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-107">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="f8bb3-108">Si l'Agent fonctionne en continu, vous devez l'arrêter, puis le redémarrer.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-108">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
 <span data-ttu-id="f8bb3-109">Bien que les paramètres puissent être modifiés directement, il est plus courant de les modifier dans un profil d'Agent.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-109">Although parameters can be modified directly, it is more common to modify them through an agent profile.</span></span> <span data-ttu-id="f8bb3-110">Pour plus d'informations, voir [Replication Agent Profiles](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f8bb3-110">For more information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="f8bb3-111">Si vous accédez à des travaux d'Agent à partir du dossier **Travaux** , utilisez la table ci-dessous pour déterminer le nom du travail d'Agent et les paramètres disponibles pour chaque Agent.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-111">If you access agent jobs from the **Jobs** folder, use the following table to determine the agent job name and the parameters available for each agent.</span></span>  
  
|<span data-ttu-id="f8bb3-112">Agent</span><span class="sxs-lookup"><span data-stu-id="f8bb3-112">Agent</span></span>|<span data-ttu-id="f8bb3-113">Nom du travail</span><span class="sxs-lookup"><span data-stu-id="f8bb3-113">Job name</span></span>|<span data-ttu-id="f8bb3-114">Pour obtenir une liste de paramètres, consultez...</span><span class="sxs-lookup"><span data-stu-id="f8bb3-114">For a list of parameters, see...</span></span>|  
|-----------|--------------|------------------------------------|  
|<span data-ttu-id="f8bb3-115">Agent d'instantané</span><span class="sxs-lookup"><span data-stu-id="f8bb3-115">Snapshot Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<integer>**|[<span data-ttu-id="f8bb3-116">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="f8bb3-116">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="f8bb3-117">Agent d'instantané pour une partition de publication de fusion</span><span class="sxs-lookup"><span data-stu-id="f8bb3-117">Snapshot Agent for a merge publication partition</span></span>|<span data-ttu-id="f8bb3-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span><span class="sxs-lookup"><span data-stu-id="f8bb3-118">**Dyn_\<Publisher>-\<PublicationDatabase>-\<Publication>-\<GUID>**</span></span>|[<span data-ttu-id="f8bb3-119">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="f8bb3-119">Replication Snapshot Agent</span></span>](replication-snapshot-agent.md)|  
|<span data-ttu-id="f8bb3-120">l'Agent de lecture du journal ;</span><span class="sxs-lookup"><span data-stu-id="f8bb3-120">Log Reader Agent</span></span>|**\<Publisher>-\<PublicationDatabase>-\<integer>**|[<span data-ttu-id="f8bb3-121">Agent de lecture du journal des réplications</span><span class="sxs-lookup"><span data-stu-id="f8bb3-121">Replication Log Reader Agent</span></span>](replication-log-reader-agent.md)|  
|<span data-ttu-id="f8bb3-122">Agent de fusion pour les abonnements extraits</span><span class="sxs-lookup"><span data-stu-id="f8bb3-122">Merge Agent for pull subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<integer>**|[<span data-ttu-id="f8bb3-123">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="f8bb3-123">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="f8bb3-124">Agent de fusion pour abonnements par envoi de données (push)</span><span class="sxs-lookup"><span data-stu-id="f8bb3-124">Merge Agent for push subscriptions</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="f8bb3-125">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="f8bb3-125">Replication Merge Agent</span></span>](replication-merge-agent.md)|  
|<span data-ttu-id="f8bb3-126">Agent de distribution pour abonnements par envoi de données (push)</span><span class="sxs-lookup"><span data-stu-id="f8bb3-126">Distribution Agent for push subscriptions</span></span>|<span data-ttu-id="f8bb3-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f8bb3-127">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>** <sup>1</sup></span></span>|[<span data-ttu-id="f8bb3-128">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="f8bb3-128">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="f8bb3-129">Agent de distribution pour abonnements par extraction de données (pull)</span><span class="sxs-lookup"><span data-stu-id="f8bb3-129">Distribution Agent for pull subscriptions</span></span>|<span data-ttu-id="f8bb3-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f8bb3-130">**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<SubscriptionDatabase>-\<GUID>** <sup>2</sup></span></span>|[<span data-ttu-id="f8bb3-131">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="f8bb3-131">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="f8bb3-132">Agent de distribution pour les abonnements par envoi de données aux Abonnés non SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8bb3-132">Distribution Agent for push subscriptions to non-SQL Server Subscribers</span></span>|**\<Publisher>-\<PublicationDatabase>-\<Publication>-\<Subscriber>-\<integer>**|[<span data-ttu-id="f8bb3-133">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="f8bb3-133">Replication Distribution Agent</span></span>](replication-distribution-agent.md)|  
|<span data-ttu-id="f8bb3-134">Agent de lecture de la file d'attente</span><span class="sxs-lookup"><span data-stu-id="f8bb3-134">Queue Reader Agent</span></span>|<span data-ttu-id="f8bb3-135">**[\<Distributor>].\<integer>**</span><span class="sxs-lookup"><span data-stu-id="f8bb3-135">**[\<Distributor>].\<integer>**</span></span>|[<span data-ttu-id="f8bb3-136">Agent de lecture de la file d’attente de réplication</span><span class="sxs-lookup"><span data-stu-id="f8bb3-136">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)|  
  
 <span data-ttu-id="f8bb3-137"><sup>1</sup> Pour les abonnements envoyés aux publications Oracle, le nom est \*\*\<Publisher>-\<Publisher**> au lieu de **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="f8bb3-137"><sup>1</sup> For push subscriptions to Oracle publications, it is \*\*\<Publisher>-\<Publisher**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
 <span data-ttu-id="f8bb3-138"><sup>2</sup> Pour les abonnements extraits aux publications Oracle, le nom est \*\*\<Publisher>-\<DistributionDatabase**> au lieu de **\<Publisher>-\<PublicationDatabase>**</span><span class="sxs-lookup"><span data-stu-id="f8bb3-138"><sup>2</sup> For pull subscriptions to Oracle publications, it is \*\*\<Publisher>-\<DistributionDatabase**> rather than **\<Publisher>-\<PublicationDatabase>**</span></span>  
  
### <a name="to-view-and-modify-replication-agent-command-line-parameters-from-management-studio"></a><span data-ttu-id="f8bb3-139">Pour afficher et modifier les paramètres de ligne de commande de l'Agent de réplication à partir de Management Studio</span><span class="sxs-lookup"><span data-stu-id="f8bb3-139">To view and modify replication agent command line parameters from Management Studio</span></span>  
  
1.  <span data-ttu-id="f8bb3-140">Connectez-vous à l'ordinateur approprié dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur :</span><span class="sxs-lookup"><span data-stu-id="f8bb3-140">Connect to the appropriate computer in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node:</span></span>  
  
    -   <span data-ttu-id="f8bb3-141">Pour l'Agent de distribution et l'Agent de fusion pour les abonnements par extraction de données, connectez-vous à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-141">For the Distribution Agent and Merge Agent for pull subscriptions, connect to the Subscriber.</span></span>  
  
    -   <span data-ttu-id="f8bb3-142">Pour tous les autres agents, connectez-vous au serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-142">For all other agents, connect to the Distributor.</span></span>  
  
2.  <span data-ttu-id="f8bb3-143">Développez le dossier **Agent SQL Server** puis développez le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="f8bb3-143">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="f8bb3-144">Cliquez avec le bouton droit sur un travail, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-144">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f8bb3-145">Dans la page **Étapes** de la boîte de dialogue **Propriétés du travail – \<Job>** , sélectionnez l’étape **Exécution de l’Agent**, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-145">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="f8bb3-146">Dans la boîte de dialogue **Propriétés de l'étape du travail - Exécution de l'Agent** , modifiez le champ **Commande** .</span><span class="sxs-lookup"><span data-stu-id="f8bb3-146">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="f8bb3-147">Cliquez sur **OK** dans les deux boîtes de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-147">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-distribution-agent-and-merge-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="f8bb3-148">Pour afficher et modifier les paramètres de ligne de commande de l'Agent de distribution et de l'Agent de fusion à partir du Moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="f8bb3-148">To view and modify Distribution Agent and Merge Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="f8bb3-149">Développez un groupe Serveur de publication dans le volet gauche du moniteur de réplication, développez un serveur de publication puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-149">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="f8bb3-150">Cliquez sur l'onglet **Tous les abonnements** .</span><span class="sxs-lookup"><span data-stu-id="f8bb3-150">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="f8bb3-151">Cliquez avec le bouton droit sur un abonnement, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-151">Right-click a subscription, and then click **View Details**.</span></span>  
  
4.  <span data-ttu-id="f8bb3-152">Dans la fenêtre d' **abonnement \< SubscriptionName> \*\* , cliquez sur **action**, puis sur \*\* \<AgentName> Propriétés du travail**.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-152">In the **Subscription \< SubscriptionName>** window, click **Action**, and then click **\<AgentName> Job Properties**.</span></span>  
  
5.  <span data-ttu-id="f8bb3-153">Dans la page **Étapes** de la boîte de dialogue **Propriétés du travail – \<Job>** , sélectionnez l’étape **Exécution de l’Agent**, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-153">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="f8bb3-154">Dans la boîte de dialogue **Propriétés de l'étape du travail - Exécution de l'Agent** , modifiez le champ **Commande** .</span><span class="sxs-lookup"><span data-stu-id="f8bb3-154">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
7.  <span data-ttu-id="f8bb3-155">Cliquez sur **OK** dans les deux boîtes de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-155">Click **OK** on both dialog boxes.</span></span>  
  
### <a name="to-view-and-modify-snapshot-agent-log-reader-agent-and-queue-reader-agent-command-line-parameters-from-replication-monitor"></a><span data-ttu-id="f8bb3-156">Pour afficher et modifier les paramètres de ligne de commande de l'Agent d'instantané, de l'Agent de lecture du journal et de l'Agent de lecture de la file d'attente à partir du Moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="f8bb3-156">To view and modify Snapshot Agent, Log Reader Agent, and Queue Reader Agent command line parameters from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="f8bb3-157">Développez un groupe Serveur de publication dans le volet gauche du moniteur de réplication, développez un serveur de publication puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-157">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="f8bb3-158">Cliquez sur l'onglet **Agents** .</span><span class="sxs-lookup"><span data-stu-id="f8bb3-158">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="f8bb3-159">Cliquez avec le bouton droit sur un Agent dans la grille puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-159">Right-click an agent in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f8bb3-160">Dans la page **Étapes** de la boîte de dialogue **Propriétés du travail – \<Job>** , sélectionnez l’étape **Exécution de l’Agent**, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-160">On the **Steps** page of the **Job Properties - \<Job>** dialog box, select the step **Run agent**, and then click **Edit**.</span></span>  
  
5.  <span data-ttu-id="f8bb3-161">Dans la boîte de dialogue **Propriétés de l'étape du travail - Exécution de l'Agent** , modifiez le champ **Commande** .</span><span class="sxs-lookup"><span data-stu-id="f8bb3-161">In the **Job Step Properties - Run agent** dialog box, edit the **Command** field.</span></span>  
  
6.  <span data-ttu-id="f8bb3-162">Cliquez sur **OK** dans les deux boîtes de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f8bb3-162">Click **OK** on both dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8bb3-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8bb3-163">See Also</span></span>  
 <span data-ttu-id="f8bb3-164">[Administration de l’Agent de réplication](replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="f8bb3-164">[Replication Agent Administration](replication-agent-administration.md) </span></span>  
 <span data-ttu-id="f8bb3-165">[Concepts des exécutables de l’Agent de réplication](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="f8bb3-165">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="f8bb3-166">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="f8bb3-166">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
