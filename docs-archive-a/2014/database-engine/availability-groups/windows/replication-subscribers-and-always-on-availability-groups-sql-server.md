---
title: Abonnés et groupes de disponibilité AlwaysOn de réplication (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/16/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover subscribers with AlwaysOn
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 0995f269-0580-43ed-b8bf-02b9ad2d7ee6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 449b5ac416f2ae86395c40a984678ed4258b3b85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610861"
---
# <a name="replication-subscribers-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="4cfa8-102">Abonnés de réplication et groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4cfa8-102">Replication Subscribers and AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="4cfa8-103">Lorsqu'un groupe de disponibilité AlwaysOn contenant une base de données est un abonné de réplication et bascule, l'abonnement de réplication peut échouer.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-103">When an AlwaysOn availability group containing a database that is a replication subscriber fails over, the replication subscription might fail.</span></span> <span data-ttu-id="4cfa8-104">Pour les abonnés de réplication par émission transactionnelle, l’agent de distribution continue la réplication automatiquement après un basculement si l’abonnement a été créé avec le nom de l’écouteur de groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-104">For transactional replication push subscribers, the distribution agent will continue to replicate automatically after a failover if the subscription was created using the AG listener name.</span></span> <span data-ttu-id="4cfa8-105">Pour les abonnés de réplication par réception transactionnelle, l’agent de distribution continue la réplication automatiquement après un basculement si l’abonnement a été créé avec le nom de l’écouteur de groupe de disponibilité et que le serveur de l’Abonné d’origine fonctionne.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-105">For transactional replication pull subscribers, the distribution agent will continue to replicate automatically after a failover, if the subscription was created using the AG listener name and the original subscriber server is up and running.</span></span> <span data-ttu-id="4cfa8-106">C’est parce que les travaux de l’agent de distribution sont uniquement créés sur l’Abonné d’origine (réplica principal du groupe de disponibilité).</span><span class="sxs-lookup"><span data-stu-id="4cfa8-106">This is because the distribution agent jobs only get created on the original subscriber (primary replica of the AG).</span></span> <span data-ttu-id="4cfa8-107">Pour les abonnés de fusion, un administrateur de réplication doit reconfigurer l'abonné manuellement, en recréant l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-107">For merge subscribers, a replication administrator must manually reconfigure the subscriber, by recreating the subscription.</span></span>  
  
## <a name="what-is-supported"></a><span data-ttu-id="4cfa8-108">Ce qui est pris en charge</span><span class="sxs-lookup"><span data-stu-id="4cfa8-108">What is Supported</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="4cfa8-109">prend en charge le basculement automatique du serveur de publication, le basculement automatique des abonnés transactionnels et le basculement manuel des abonnés de fusion.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-109">replication supports the automatic failover of the publisher, the automatic failover of transactional subscribers, and the manual failover of merge subscribers.</span></span> <span data-ttu-id="4cfa8-110">Le basculement d'un serveur de distribution dans une base de données de disponibilité n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-110">The failover of a distributor on an availability database is not supported.</span></span> <span data-ttu-id="4cfa8-111">AlwaysOn ne peut pas être combiné avec Websync et [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-111">AlwaysOn cannot be combined with Websync and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact scenarios.</span></span>  
  
 <span data-ttu-id="4cfa8-112">**Basculement d'un abonnement de fusion par extraction de données (pull)**</span><span class="sxs-lookup"><span data-stu-id="4cfa8-112">**Failover of a Merge Pull Subscription**</span></span>  
  
 <span data-ttu-id="4cfa8-113">Un abonnement par extraction échoue lors d'un basculement de groupe de disponibilité, car l'agent d'extraction de données ne trouve pas les travaux stockés dans la base de données **msdb** de l'instance de serveur qui héberge le réplica principal, qui n'est pas disponible parce que l'instance de serveur a échoué.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-113">A pull subscription fails upon availability group failover, because pull agent cannot find the jobs stored in the **msdb** database of the server instance that hosts the primary replica; which is not available because the server instance has failed.</span></span>  
  
 <span data-ttu-id="4cfa8-114">**Basculement d'un abonnement de fusion par émission de données (push)**</span><span class="sxs-lookup"><span data-stu-id="4cfa8-114">**Failover of a Merge Push Subscription**</span></span>  
  
 <span data-ttu-id="4cfa8-115">Un abonnement par émission de données échoue lors du basculement d'un groupe de disponibilité, car l'agent de transmission de type push ne peut plus se connecter à la base de données d'abonnement d'origine sur l'abonné d'origine.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-115">A push subscription fails upon availability group failover, because the push agent can no longer connect to original subscription database on original subscriber.</span></span>  
  
## <a name="how-to-create-transactional-subscription-in-an-alwayson-environment"></a><span data-ttu-id="4cfa8-116">Procédure de création d'un abonnement transactionnel dans un environnement AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="4cfa8-116">How to Create Transactional Subscription in an AlwaysOn Environment</span></span>  
 <span data-ttu-id="4cfa8-117">Pour la réplication transactionnelle, utilisez la procédure suivante pour configurer et basculer un groupe de disponibilité d'abonné :</span><span class="sxs-lookup"><span data-stu-id="4cfa8-117">For transactional replication, use the following steps to configure and failover a subscriber availability group:</span></span>  
  
1.  <span data-ttu-id="4cfa8-118">Avant de créer l'abonnement, ajoutez la base de données de l'abonné au groupe de disponibilité AlwaysOn approprié.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-118">Before creating the subscription, add the subscriber database to the appropriate AlwaysOn availability group.</span></span>  
  
2.  <span data-ttu-id="4cfa8-119">Ajoutez l'écouteur de groupe de disponibilité de l'abonné en tant que serveur lié à tous les nœuds du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-119">Add the subscriber's availability group Listener as a linked server to all nodes of the availability group.</span></span> <span data-ttu-id="4cfa8-120">Cette étape garantit que tous les partenaires de basculement potentiels ont connaissance de l'écouteur et peuvent s'y connecter.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-120">This step ensures that all potential failover partners are aware of and can connect to the listener.</span></span>  
  
3.  <span data-ttu-id="4cfa8-121">À l'aide du script de la section **Création d'un abonnement de réplication transactionnelle par émission de données** ci-dessous, créez l'abonnement avec le nom de l'écouteur du groupe de disponibilité de l'abonné.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-121">Using the script in the **Creating a Transactional Replication Push Subscription** section below, create the subscription using the name of the availability group listener of the subscriber.</span></span> <span data-ttu-id="4cfa8-122">Après un basculement, le nom de l'écouteur demeure valide, alors que le nom du serveur réel de l'abonné dépend du nœud réel qui est devenu le nouveau nœud principal.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-122">After a failover, the listener name will always remain valid, whereas the actual server name of the subscriber will depend on the actual node that became the new primary.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4cfa8-123">L'abonnement doit être créé à l'aide d'un script [!INCLUDE[tsql](../../../includes/tsql-md.md)] ; il ne peut pas être créé à l'aide de [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cfa8-123">The subscription must be created by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script and cannot be created using [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="4cfa8-124">Pour la création d'un abonnement par extraction de données :</span><span class="sxs-lookup"><span data-stu-id="4cfa8-124">If creating a pull subscription:</span></span>  
  
    1.  <span data-ttu-id="4cfa8-125">Dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], sur le nœud principal de l'abonné, ouvrez l'arborescence de l'Agent [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cfa8-125">In [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], on the primary subscriber node, open the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent tree.</span></span>  
  
    2.  <span data-ttu-id="4cfa8-126">Identifiez le travail de l' **Agent de distribution par extraction de données** et modifiez le travail.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-126">Identify the **Pull Distribution Agent** job and edit the job.</span></span>  
  
    3.  <span data-ttu-id="4cfa8-127">À l'étape de travail **Exécution de l'Agent** , vérifiez les paramètres `-Publisher` et `-Distributor` .</span><span class="sxs-lookup"><span data-stu-id="4cfa8-127">On the **Run Agent** job step, check the `-Publisher` and `-Distributor` parameters.</span></span> <span data-ttu-id="4cfa8-128">Assurez-vous que ces paramètres contiennent les noms corrects du serveur direct et de l'instance du serveur de publication et du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-128">Make sure that these parameters contain the correct direct server and instance names of the publisher and distributor server.</span></span>  
  
    4.  <span data-ttu-id="4cfa8-129">Remplacez le paramètre `-Subscriber` par le nom de l'écouteur de groupe de disponibilité de l'abonné.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-129">Change the `-Subscriber` parameter to the subscriber's availability group listener name.</span></span>  
  
 <span data-ttu-id="4cfa8-130">Si vous créez votre abonnement en suivant ces étapes, vous n’aurez aucune action à accomplir après un basculement.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-130">When you create your subscription following these steps, then you won't have to do anything after a failover.</span></span>  
  
## <a name="creating-a-transactional-replication-push-subscription"></a><span data-ttu-id="4cfa8-131">Création d'un abonnement de réplication transactionnelle par émission de données</span><span class="sxs-lookup"><span data-stu-id="4cfa8-131">Creating a Transactional Replication Push Subscription</span></span>  
  
```  
-- commands to execute at the publisher, in the publisher database:  
use [<publisher database name>]  
EXEC sp_addsubscription @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @destination_db = N'<subscriber database name>',   
       @subscription_type = N'Push',   
       @sync_type = N'automatic', @article = N'all', @update_mode = N'read only', @subscriber_type = 0;  
GO  
  
EXEC sp_addpushsubscription_agent @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @subscriber_db = N'<subscriber database name>',   
       @job_login = null, @job_password = null, @subscriber_security_mode = 1;  
GO  
```  
  
## <a name="to-resume-the-merge-agents-after-the-availability-group-of-the-subscriber-fails-over"></a><span data-ttu-id="4cfa8-132">Pour récupérer les agents de fusion après le basculement du groupe de disponibilité de l'abonné</span><span class="sxs-lookup"><span data-stu-id="4cfa8-132">To Resume the Merge Agents After the Availability Group of the Subscriber Fails Over</span></span>  
 <span data-ttu-id="4cfa8-133">Pour une réplication de fusion, un administrateur de réplication doit reconfigurer l'abonné manuellement en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="4cfa8-133">For merge replication, a replication administrator must manually reconfigure the subscriber with the following steps:</span></span>  
  
1.  <span data-ttu-id="4cfa8-134">Exécutez `sp_subscription_cleanup` pour supprimer l'ancien abonnement de l'abonné.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-134">Execute `sp_subscription_cleanup` to remove the old subscription for the subscriber.</span></span> <span data-ttu-id="4cfa8-135">Effectuez cette action sur le nouveau réplica principal (qui était auparavant le réplica secondaire).</span><span class="sxs-lookup"><span data-stu-id="4cfa8-135">Perform this action on the new primary replica (which was formerly the secondary replica).</span></span>  
  
2.  <span data-ttu-id="4cfa8-136">Recréez l'abonnement en en créant un nouveau, en commençant par un nouvel instantané.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-136">Recreate the subscription by creating a new subscription, beginning with a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4cfa8-137">Le processus actuel n'est pas pratique pour les abonnés de réplication de fusion ; toutefois, le scénario principal de la réplication de fusion implique des utilisateurs déconnectés (bureaux, ordinateurs portables, appareils combinés téléphoniques) qui n'utilisent pas les groupes de disponibilité AlwaysOn sur l'abonné.</span><span class="sxs-lookup"><span data-stu-id="4cfa8-137">The current process is inconvenient for merge replication subscribers, however the main scenario for merge replication is disconnected users (desktops, laptops, handset devices) which will not use AlwaysOn availability groups on the subscriber.</span></span>  
  
  
