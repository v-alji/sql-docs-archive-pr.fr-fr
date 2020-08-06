---
title: Gérer les événements | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- event-triggered jobs [SQL Server]
- forwarding events [SQL Server]
- alerts [SQL Server], forwarded events
- alerts [SQL Server], management servers
- SQL Server Agent alerts, management servers
ms.assetid: 8f4ee7f5-80df-49fd-b2b8-d020e04b6e1b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ca6d56440b06d285cbb90f8d92325d59a452c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695259"
---
# <a name="manage-events"></a><span data-ttu-id="f5e03-102">Gérer les événements</span><span class="sxs-lookup"><span data-stu-id="f5e03-102">Manage Events</span></span>
  <span data-ttu-id="f5e03-103">Vous pouvez transférer à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tous les messages d'événements qui correspondent à un niveau de gravité d'erreur ou le dépassent.</span><span class="sxs-lookup"><span data-stu-id="f5e03-103">You can forward to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all event messages that meet or exceed a specific error severity level.</span></span> <span data-ttu-id="f5e03-104">Cette fonction est qualifiée de *transfert d'événements*.</span><span class="sxs-lookup"><span data-stu-id="f5e03-104">This is called *event forwarding*.</span></span> <span data-ttu-id="f5e03-105">Le serveur de transfert est un serveur dédié qui peut également être un serveur maître.</span><span class="sxs-lookup"><span data-stu-id="f5e03-105">The forwarding server is a dedicated server that can also be a master server.</span></span> <span data-ttu-id="f5e03-106">Le transfert d'événements permet de centraliser la gestion des alertes pour un groupe de serveurs, réduisant ainsi la charge de travail sur les serveurs à utilisation intense.</span><span class="sxs-lookup"><span data-stu-id="f5e03-106">You can use event forwarding to centralize alert management for a group of servers, thereby reducing the workload on heavily used servers.</span></span>  
  
 <span data-ttu-id="f5e03-107">Lorsqu'un serveur reçoit des événements pour un groupe d'autres serveurs, le serveur qui reçoit les événements est qualifié de *serveur de gestion des alertes*.</span><span class="sxs-lookup"><span data-stu-id="f5e03-107">When one server receives events for a group of other servers, the server that receives events is called an *alerts management server*.</span></span> <span data-ttu-id="f5e03-108">Dans un environnement multiserveur, il est recommandé de désigner le serveur maître comme serveur de gestion des alertes.</span><span class="sxs-lookup"><span data-stu-id="f5e03-108">In a multiserver environment, you designate the master server as the alerts management server.</span></span>  
  
## <a name="advantages-of-using-an-alerts-management-server"></a><span data-ttu-id="f5e03-109">Avantages de l'utilisation du serveur de gestion des alertes</span><span class="sxs-lookup"><span data-stu-id="f5e03-109">Advantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="f5e03-110">Les avantages liés à la désignation d'un serveur de gestion des alertes sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="f5e03-110">The advantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="f5e03-111">**Centralisation**.</span><span class="sxs-lookup"><span data-stu-id="f5e03-111">**Centralization**.</span></span> <span data-ttu-id="f5e03-112">Il est possible d'effectuer un contrôle centralisé et une vue consolidée des événements de plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d'un seul serveur.</span><span class="sxs-lookup"><span data-stu-id="f5e03-112">Centralized control and a consolidated view of the events of several instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are possible from a single server.</span></span>  
  
-   <span data-ttu-id="f5e03-113">**Extensibilité**.</span><span class="sxs-lookup"><span data-stu-id="f5e03-113">**Scalability**.</span></span> <span data-ttu-id="f5e03-114">De nombreux serveurs physiques peuvent être administrés comme un serveur logique unique.</span><span class="sxs-lookup"><span data-stu-id="f5e03-114">Many physical servers can be administered as one logical server.</span></span> <span data-ttu-id="f5e03-115">En fonction des besoins, vous pouvez ajouter et supprimer des serveurs dans ce groupe de serveurs physiques.</span><span class="sxs-lookup"><span data-stu-id="f5e03-115">You can add or remove servers to this physical server group as needed.</span></span>  
  
-   <span data-ttu-id="f5e03-116">**Efficacité**.</span><span class="sxs-lookup"><span data-stu-id="f5e03-116">**Efficiency**.</span></span> <span data-ttu-id="f5e03-117">Le temps de configuration est réduit car vous ne devez définir les alertes et les opérateurs qu'une seule fois.</span><span class="sxs-lookup"><span data-stu-id="f5e03-117">Configuration time is reduced, because you need to define alerts and operators only once.</span></span>  
  
## <a name="disadvantages-of-using-an-alerts-management-server"></a><span data-ttu-id="f5e03-118">Inconvénients de l'utilisation du serveur de gestion des alertes</span><span class="sxs-lookup"><span data-stu-id="f5e03-118">Disadvantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="f5e03-119">Les inconvénients liés à la désignation d'un serveur de gestion des alertes sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="f5e03-119">The disadvantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="f5e03-120">**Augmentation du trafic**.</span><span class="sxs-lookup"><span data-stu-id="f5e03-120">**Increased traffic**.</span></span> <span data-ttu-id="f5e03-121">Le transfert d'événements à un serveur de gestion des alertes peut augmenter le trafic réseau.</span><span class="sxs-lookup"><span data-stu-id="f5e03-121">Forwarding events to an alerts management server can increase network traffic.</span></span> <span data-ttu-id="f5e03-122">Cette augmentation peut être modérée en limitant le transfert d'événements aux événements qui se situent au-dessus d'un niveau de gravité désigné.</span><span class="sxs-lookup"><span data-stu-id="f5e03-122">This increase can be moderated by restricting event forwarding to events that are above a designated severity level.</span></span>  
  
-   <span data-ttu-id="f5e03-123">**Point de défaillance unique**.</span><span class="sxs-lookup"><span data-stu-id="f5e03-123">**Single point of failure**.</span></span> <span data-ttu-id="f5e03-124">Si le serveur de gestion des alertes se déconnecte, aucune alerte n'est émise pour aucun événement sur le groupe de serveurs géré.</span><span class="sxs-lookup"><span data-stu-id="f5e03-124">If the alerts management server goes offline, no alerts are issued for any event on the managed group of servers.</span></span>  
  
-   <span data-ttu-id="f5e03-125">**Charge du serveur**.</span><span class="sxs-lookup"><span data-stu-id="f5e03-125">**Server load**.</span></span> <span data-ttu-id="f5e03-126">La gestion des alertes des événements transférés provoque une augmentation de la charge de traitement sur le serveur de gestion des alertes.</span><span class="sxs-lookup"><span data-stu-id="f5e03-126">Handling alerts for the forwarded events causes an increased processing load on the alerts management server.</span></span>  
  
## <a name="guidelines-for-using-an-alerts-management-server"></a><span data-ttu-id="f5e03-127">Directives concernant l'utilisation d'un serveur de gestion des alertes</span><span class="sxs-lookup"><span data-stu-id="f5e03-127">Guidelines for Using an Alerts Management Server</span></span>  
 <span data-ttu-id="f5e03-128">Lors de la configuration d'un serveur de gestion des alertes, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f5e03-128">When configuring an alerts management server, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="f5e03-129">Afin de recevoir les événements transférés, le serveur de gestion des alertes doit être une instance par défaut de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f5e03-129">In order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="f5e03-130">Évitez d'exécuter des applications critiques ou qui nécessitent une utilisation intensive sur le serveur de gestion des alertes.</span><span class="sxs-lookup"><span data-stu-id="f5e03-130">Avoid running critical or heavily used applications on the alerts management server.</span></span>  
  
-   <span data-ttu-id="f5e03-131">Planifiez avec soin le trafic réseau impliqué dans la configuration de plusieurs serveurs pour partager le même serveur de gestion des alertes.</span><span class="sxs-lookup"><span data-stu-id="f5e03-131">Carefully plan for the network traffic involved in configuring many servers to share the same alerts management server.</span></span> <span data-ttu-id="f5e03-132">En cas d'encombrement, réduisez le nombre de serveurs utilisant un serveur particulier de gestion des alertes.</span><span class="sxs-lookup"><span data-stu-id="f5e03-132">If congestion results, reduce the number of servers that use a particular alerts management server.</span></span>  
  
     <span data-ttu-id="f5e03-133">Les serveurs inscrits dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] constituent la liste des serveurs disponibles devant être choisis par ce serveur comme serveur de transfert des alertes.</span><span class="sxs-lookup"><span data-stu-id="f5e03-133">The servers that are registered within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] constitute the list of servers available to be chosen by that server as the alerts-forwarding server.</span></span>  
  
-   <span data-ttu-id="f5e03-134">Définissez sur l'instance locale de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] les alertes qui nécessitent une réponse serveur spécifique, au lieu de transférer les alertes aux serveurs de gestion des alertes.</span><span class="sxs-lookup"><span data-stu-id="f5e03-134">Define alerts on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that require a server-specific response, instead of forwarding the alerts to the alerts management server.</span></span>  
  
     <span data-ttu-id="f5e03-135">Le serveur de gestion des alertes considère tous les serveurs qui lui transfèrent des événements comme un ensemble logique.</span><span class="sxs-lookup"><span data-stu-id="f5e03-135">The alerts management server views all the servers forwarding to it as a logical whole.</span></span> <span data-ttu-id="f5e03-136">Par exemple, un serveur de gestion des alertes répond de la même façon à un événement 605 émanant du serveur A ou du serveur B.</span><span class="sxs-lookup"><span data-stu-id="f5e03-136">For example, an alerts management server responds in the same way to a 605 event from server A and a 605 event from server B.</span></span>  
  
-   <span data-ttu-id="f5e03-137">Après avoir configuré votre système d'alerte, vérifiez régulièrement la présence d'événements de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans le journal des applications Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="f5e03-137">After configuring your alert system, periodically check the Microsoft Windows application log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events.</span></span>  
  
     <span data-ttu-id="f5e03-138">Les conditions d'échec rencontrées par le moteur d'alertes sont consignées dans le journal des applications Windows local avec le nom source « Agent SQL Server ».</span><span class="sxs-lookup"><span data-stu-id="f5e03-138">Failure conditions encountered by the alerts engine are written to the local Windows application log with a source name of "SQL Server Agent."</span></span> <span data-ttu-id="f5e03-139">Par exemple, si l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas envoyer par courrier électronique une notification telle qu'elle a été définie, un événement est consigné dans le journal des applications.</span><span class="sxs-lookup"><span data-stu-id="f5e03-139">For example, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent cannot send an e-mail notification as it has been defined, an event is logged in the application log.</span></span>  
  
 <span data-ttu-id="f5e03-140">Si une alerte définie localement est désactivée et si un événement qui aurait dû déclencher l'alerte se produit, l'événement est transféré au serveur de gestion des alertes (s'il remplit la condition de transfert d'alerte).</span><span class="sxs-lookup"><span data-stu-id="f5e03-140">If a locally defined alert is inactivated, and an event occurs that would have caused the alert to fire, the event is forwarded to the alerts management server (if it satisfies the alert-forwarding condition).</span></span> <span data-ttu-id="f5e03-141">Ce transfert permet la mise en fonction ou non de priorités locales (alertes définies localement qui sont également définies sur le serveur de gestion des alertes) sur le site local, selon les besoins de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5e03-141">This forwarding allows local overrides (alerts defined locally that are also defined on the alerts management server) to be turned off and on as needed by the user at the local site.</span></span> <span data-ttu-id="f5e03-142">Vous pouvez également demander que les événements soient transférés, même s'ils sont gérés par des alertes locales.</span><span class="sxs-lookup"><span data-stu-id="f5e03-142">You can also request that events always be forwarded, even if they are also handled by local alerts.</span></span>  
  
 <span data-ttu-id="f5e03-143">Les tâches suivantes sont courantes pour la gestion des événements dans un environnement multiserveur :</span><span class="sxs-lookup"><span data-stu-id="f5e03-143">The following are common tasks for managing events in a multiserver environment:</span></span>  
  
 <span data-ttu-id="f5e03-144">**Pour désigner un serveur de gestion des alertes**</span><span class="sxs-lookup"><span data-stu-id="f5e03-144">**To designate an alerts management server**</span></span>  
  
-   [<span data-ttu-id="f5e03-145">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f5e03-145">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
 <span data-ttu-id="f5e03-146">**Pour définir la réponse à une alerte**</span><span class="sxs-lookup"><span data-stu-id="f5e03-146">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="f5e03-147">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f5e03-147">SQL Server Management Studio</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f5e03-148">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f5e03-148">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
## <a name="running-event-triggered-jobs"></a><span data-ttu-id="f5e03-149">Exécution des travaux déclenchés par un événement</span><span class="sxs-lookup"><span data-stu-id="f5e03-149">Running Event-Triggered Jobs</span></span>  
 <span data-ttu-id="f5e03-150">Vous pouvez définir un travail à exécuter en réponse à une alerte.</span><span class="sxs-lookup"><span data-stu-id="f5e03-150">You can define a job to be executed in response to an alert.</span></span> <span data-ttu-id="f5e03-151">Par exemple, vous pouvez exécuter un travail qui corrige un problème détecté par l'alerte ou approfondit son diagnostic.</span><span class="sxs-lookup"><span data-stu-id="f5e03-151">For example, you can execute a job that corrects or further diagnoses a problem detected by the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5e03-152">Un travail pouvant déclencher un événement, veillez à ne pas créer de boucle récursive de travail d'alerte.</span><span class="sxs-lookup"><span data-stu-id="f5e03-152">Because a job can raise an event, be careful not to create a recursive alert-job loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e03-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5e03-153">See Also</span></span>  
 [<span data-ttu-id="f5e03-154">Messagessys.sys&#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f5e03-154">sys.sysmessages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysmessages-transact-sql)  
  
  
