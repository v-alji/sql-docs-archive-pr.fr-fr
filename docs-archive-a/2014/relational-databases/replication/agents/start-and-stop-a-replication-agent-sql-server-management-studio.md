---
title: Démarrer et arrêter un Agent de réplication (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], stopping
- agents [SQL Server replication], starting
ms.assetid: 97977c4a-8c7c-4a22-9480-69aa812bd1e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40e329e0f04e8a54a2d5a40c30aff418da2cd65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601398"
---
# <a name="start-and-stop-a-replication-agent-sql-server-management-studio"></a><span data-ttu-id="16c43-102">Démarrer et arrêter un Agent de réplication (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="16c43-102">Start and Stop a Replication Agent (SQL Server Management Studio)</span></span>
  <span data-ttu-id="16c43-103">Démarrez et arrêtez des agents à partir du dossier **Travaux** et du dossier **Réplication** de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou à partir du moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="16c43-103">Start and stop agents from the **Jobs** folder and the **Replication** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from Replication Monitor.</span></span> <span data-ttu-id="16c43-104">Démarrez et arrêtez les Agents et les travaux suivants :</span><span class="sxs-lookup"><span data-stu-id="16c43-104">Start and stop the following agents and jobs:</span></span>  
  
-   <span data-ttu-id="16c43-105">Agent d'instantané, utilisé par toutes les publications</span><span class="sxs-lookup"><span data-stu-id="16c43-105">The Snapshot Agent, which is used by all publications.</span></span>  
  
-   <span data-ttu-id="16c43-106">Agent de lecture du journal, utilisé par toutes les publications transactionnelles</span><span class="sxs-lookup"><span data-stu-id="16c43-106">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
-   <span data-ttu-id="16c43-107">Agent de lecture de la file d'attente, utilisé par les publications transactionnelles qui possèdent des abonnements mis à jour en attente</span><span class="sxs-lookup"><span data-stu-id="16c43-107">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="16c43-108">Agent de distribution, qui synchronise les abonnements aux publications transactionnelles et d'instantané</span><span class="sxs-lookup"><span data-stu-id="16c43-108">The Distribution Agent, which synchronizes subscriptions to transactional and snapshot publications.</span></span>  
  
-   <span data-ttu-id="16c43-109">Agent de fusion, qui synchronise les abonnements aux publications de fusion</span><span class="sxs-lookup"><span data-stu-id="16c43-109">The Merge Agent, which synchronizes subscriptions to merge publications.</span></span>  
  
-   <span data-ttu-id="16c43-110">Travaux de maintenance de la réplication</span><span class="sxs-lookup"><span data-stu-id="16c43-110">Replication maintenance jobs.</span></span>  
  
 <span data-ttu-id="16c43-111">Pour plus d’informations sur le démarrage de l’Agent de fusion et de l’Agent de Distribution, consultez [Synchroniser un abonnement par émission de données](../synchronize-a-push-subscription.md) et [Synchroniser un abonnement par extraction](../synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="16c43-111">For more information about starting the Merge Agent and the Distribution Agent, see [Synchronize a Push Subscription](../synchronize-a-push-subscription.md) and [Synchronize a Pull Subscription](../synchronize-a-pull-subscription.md).</span></span> <span data-ttu-id="16c43-112">Pour plus d’informations sur les travaux de maintenance, consultez [Exécuter des travaux de maintenance de réplication &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="16c43-112">For more information about maintenance jobs, see [Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md).</span></span>  
  
 <span data-ttu-id="16c43-113">Pour plus d’informations sur le démarrage du Moniteur de réplication, consultez [Démarrer le Moniteur de réplication](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="16c43-113">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-or-log-reader-agent-from-management-studio"></a><span data-ttu-id="16c43-114">Pour démarrer et arrêter un Agent d'instantané ou un Agent de lecture du journal à partir de Management Studio</span><span class="sxs-lookup"><span data-stu-id="16c43-114">To start and stop a Snapshot Agent or Log Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="16c43-115">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]puis développez le nœud du serveur et le dossier **Réplication** .</span><span class="sxs-lookup"><span data-stu-id="16c43-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node and the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="16c43-116">Développez le dossier **Publications locales** , puis cliquez avec le bouton droit sur une publication.</span><span class="sxs-lookup"><span data-stu-id="16c43-116">Expand the **Local Publications** folder, and then right-click a publication.</span></span>  
  
3.  <span data-ttu-id="16c43-117">Cliquez sur **Afficher l'état de l'Agent d'instantané** ou **Afficher l'état de l'Agent de lecture du journal**.</span><span class="sxs-lookup"><span data-stu-id="16c43-117">Click **View Snapshot Agent Status** or **View Log Reader Agent Status**.</span></span>  
  
4.  <span data-ttu-id="16c43-118">Cliquez sur **Démarrer** ou sur **Arrêter**.</span><span class="sxs-lookup"><span data-stu-id="16c43-118">Click **Start** or **Stop**.</span></span>  
  
### <a name="to-start-and-stop-a-queue-reader-agent-from-management-studio"></a><span data-ttu-id="16c43-119">Pour démarrer et arrêter un Agent de lecture de file d'attente à partir de Management Studio</span><span class="sxs-lookup"><span data-stu-id="16c43-119">To start and stop a Queue Reader Agent from Management Studio</span></span>  
  
1.  <span data-ttu-id="16c43-120">Connectez-vous au serveur de distribution dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="16c43-120">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="16c43-121">Développez le dossier **Agent SQL Server** puis développez le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="16c43-121">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="16c43-122">Cliquez avec le bouton droit sur le travail de l'agent puis cliquez sur **Démarrer le travail** ou **Arrêter le travail**.</span><span class="sxs-lookup"><span data-stu-id="16c43-122">Right-click the job for the agent, and then click **Start Job** or **Stop Job**.</span></span> <span data-ttu-id="16c43-123">Le nom du travail de l’Agent de lecture de la file d’attente est au format **[\<Distributor>].\<integer>** .</span><span class="sxs-lookup"><span data-stu-id="16c43-123">The name of the job for the Queue Reader Agent is in the form **[\<Distributor>].\<integer>**.</span></span>  
  
### <a name="to-start-and-stop-a-snapshot-agent-log-reader-agent-or-queue-reader-agent-from-replication-monitor"></a><span data-ttu-id="16c43-124">Pour démarrer et arrêter un Agent d'instantané, un Agent de lecture du journal ou un Agent de lecture de file d'attente dans le moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="16c43-124">To start and stop a Snapshot Agent, Log Reader Agent, or Queue Reader Agent from Replication Monitor</span></span>  
  
1.  <span data-ttu-id="16c43-125">Développez un groupe de serveurs de publication dans le volet gauche, développez un serveur de publication, puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="16c43-125">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="16c43-126">Cliquez sur l'onglet **Agents** .</span><span class="sxs-lookup"><span data-stu-id="16c43-126">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="16c43-127">Cliquez avec le bouton droit sur un Agent puis cliquez sur **Démarrer l'Agent** ou **Arrêter l'Agent**.</span><span class="sxs-lookup"><span data-stu-id="16c43-127">Right-click an agent, and then click **Start Agent** or **Stop Agent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c43-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16c43-128">See Also</span></span>  
 <span data-ttu-id="16c43-129">[Surveillance de la réplication](../monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="16c43-129">[Monitoring Replication](../monitoring-replication.md) </span></span>  
 <span data-ttu-id="16c43-130">[Concepts des exécutables de l’Agent de réplication](../concepts/replication-agent-executables-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="16c43-130">[Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) </span></span>  
 [<span data-ttu-id="16c43-131">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="16c43-131">Replication Agents Overview</span></span>](replication-agents-overview.md)  
  
  
