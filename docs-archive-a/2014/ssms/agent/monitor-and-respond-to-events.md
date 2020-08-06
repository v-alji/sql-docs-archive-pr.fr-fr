---
title: Surveiller et répondre aux événements | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- notifications [SQL Server], alert
- events [SQL Server], alerts
- alerts [SQL Server]
- notifications [SQL Server]
- events [SQL Server], automatically responding to
- administrator notifications [SQL Server Agent]
- automatic event responses
- SQL Server Agent alerts
- monitoring [SQL Server], events
- responding to events automatically
ms.assetid: f7fbe155-5b68-4777-bc71-a47637471f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: afdf1beffd6099fce84f03a8ba65f7de9abb8f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699180"
---
# <a name="monitor-and-respond-to-events"></a><span data-ttu-id="a8e18-102">Surveiller et répondre aux événements</span><span class="sxs-lookup"><span data-stu-id="a8e18-102">Monitor and Respond to Events</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a8e18-103">Agent peut surveiller les *événements* et répondre automatiquement à ces derniers, par exemple des messages de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], des conditions de performances particulières et des événements WMI (Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="a8e18-103">Agent can monitor and automatically respond to *events*, such as messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], specific performance conditions, and Windows Management Instrumentation (WMI) events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a8e18-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a8e18-104">In This Section</span></span>  
 [<span data-ttu-id="a8e18-105">Alertes</span><span class="sxs-lookup"><span data-stu-id="a8e18-105">Alerts</span></span>](alerts.md)  
 <span data-ttu-id="a8e18-106">Contient des informations sur la façon de nommer une alerte et de sélectionner les événements ou conditions de performances auxquels les alertes répondent.</span><span class="sxs-lookup"><span data-stu-id="a8e18-106">Contains information about naming an alert and selecting the events or performance conditions to which alerts respond.</span></span>  
  
 [<span data-ttu-id="a8e18-107">Créer un événement défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a8e18-107">Create a User-Defined Event</span></span>](create-a-user-defined-event.md)  
 <span data-ttu-id="a8e18-108">Contient des informations sur la façon de créer des événements autres que ceux qui sont prédéfinis par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8e18-108">Contains information about how to create events other than those that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="a8e18-109">Opérateurs</span><span class="sxs-lookup"><span data-stu-id="a8e18-109">Operators</span></span>](operators.md)  
 <span data-ttu-id="a8e18-110">Contient des informations sur la création d'alias pour les administrateurs, alias que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut utiliser pour envoyer des notifications lorsque les travaux échouent ou réussissent.</span><span class="sxs-lookup"><span data-stu-id="a8e18-110">Contains information about creating aliases for administrators that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can use to send notifications when jobs fail or succeed.</span></span>  
  
## <a name="about-monitoring-and-responding-to-events"></a><span data-ttu-id="a8e18-111">À propos de la surveillance et de la réponse aux événements</span><span class="sxs-lookup"><span data-stu-id="a8e18-111">About Monitoring and Responding to Events</span></span>  
 <span data-ttu-id="a8e18-112">Les réponses automatiques aux événements sont appelées *alertes*.</span><span class="sxs-lookup"><span data-stu-id="a8e18-112">Automated responses to events are called *alerts*.</span></span> <span data-ttu-id="a8e18-113">Vous pouvez définir une alerte sur un ou plusieurs événements pour spécifier la façon dont vous voulez que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y réponde lorsqu'ils se produisent.</span><span class="sxs-lookup"><span data-stu-id="a8e18-113">You can define an alert on one or more events to specify how you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to their occurrence.</span></span> <span data-ttu-id="a8e18-114">Une alerte peut répondre à un événement en notifiant un administrateur ou en exécutant un travail, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="a8e18-114">An alert can respond to an event by notifying an administrator or running a job, or both.</span></span> <span data-ttu-id="a8e18-115">Une alerte peut également transmettre un événement au journal des applications Microsoft Windows d'un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a8e18-115">An alert can also forward an event to the Microsoft Windows application log on a different computer.</span></span> <span data-ttu-id="a8e18-116">Par exemple, vous pouvez spécifier qu'un opérateur soit notifié immédiatement si un événement de gravité 19 se produit.</span><span class="sxs-lookup"><span data-stu-id="a8e18-116">For example, you can specify that an operator be notified immediately if an event of severity 19 occurs.</span></span> <span data-ttu-id="a8e18-117">En définissant des alertes, les administrateurs de bases de données peuvent surveiller et gérer plus efficacement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8e18-117">By defining alerts, database administrators can more effectively monitor and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a8e18-118">Agent ne répond qu’aux événements pour lesquels une alerte a été définie.</span><span class="sxs-lookup"><span data-stu-id="a8e18-118">Agent only responds to events for which an alert is defined.</span></span> <span data-ttu-id="a8e18-119">La méthode qu'utilise l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour surveiller les événements dépend du type d'événement.</span><span class="sxs-lookup"><span data-stu-id="a8e18-119">The method that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uses to monitor events depends on the type of event.</span></span>  
  
 <span data-ttu-id="a8e18-120">Lorsqu'une alerte de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est définie sur un compteur de performance, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] le surveille directement.</span><span class="sxs-lookup"><span data-stu-id="a8e18-120">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert is defined for a performance counter, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent directly monitors the performance counter.</span></span> <span data-ttu-id="a8e18-121">Pour un événement WMI, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inscrit une requête d'événement pour cet événement.</span><span class="sxs-lookup"><span data-stu-id="a8e18-121">For a WMI event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registers an event query for the WMI event.</span></span>  
  
 <span data-ttu-id="a8e18-122">Pour répondre aux messages de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] surveille le journal des applications Windows.</span><span class="sxs-lookup"><span data-stu-id="a8e18-122">To respond to messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent monitors the Windows application log.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a8e18-123">Agent ne peut répondre qu’aux messages qui apparaissent dans ce journal.</span><span class="sxs-lookup"><span data-stu-id="a8e18-123">Agent can only respond to messages that appear in this log.</span></span> <span data-ttu-id="a8e18-124">Par défaut, SQL Server enregistre les événements suivants dans le journal des applications Windows :</span><span class="sxs-lookup"><span data-stu-id="a8e18-124">By default, SQL Server logs the following messages in the Windows application log:</span></span>  
  
-   <span data-ttu-id="a8e18-125">Erreurs sysmessages dont le niveau de gravité est supérieur ou égal à 19.</span><span class="sxs-lookup"><span data-stu-id="a8e18-125">Severity 19 or higher sysmessages errors.</span></span>  
  
     <span data-ttu-id="a8e18-126">Si vous souhaitez également journaliser des erreurs sysmessages particulières dont le niveau de gravité est inférieur à 19, utilisez la procédure stockée sp_altermessage pour désigner ces erreurs comme étant « toujours journalisées ».</span><span class="sxs-lookup"><span data-stu-id="a8e18-126">If you also want to log specific sysmessages errors that have a severity lower than 19, use the sp_altermessage stored procedure to designate such errors as "always logged".</span></span>  
  
-   <span data-ttu-id="a8e18-127">Toute instruction RAISERROR appelée à l'aide de la syntaxe WITH LOG.</span><span class="sxs-lookup"><span data-stu-id="a8e18-127">Any RAISERROR statement invoked by using the WITH LOG syntax.</span></span>  
  
     <span data-ttu-id="a8e18-128">RAISERROR WITH LOG est la méthode conseillée pour écrire dans le journal des applications Windows à partir d'une instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8e18-128">Using RAISERROR WITH LOG is the recommended way to write to the Windows application log from an instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="a8e18-129">Tout événement d'application consigné dans le journal à l'aide de xp_logevent.</span><span class="sxs-lookup"><span data-stu-id="a8e18-129">Any application event that is logged by using xp_logevent.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8e18-130">La journalisation des événements d'applications consomme de l'espace et peut conduire le journal des applications Windows à dépasser sa taille maximale.</span><span class="sxs-lookup"><span data-stu-id="a8e18-130">Logging application events consumes log space and can cause the Windows application log to exceed its maximum size.</span></span> <span data-ttu-id="a8e18-131">Assurez-vous que la taille du journal des applications Windows est suffisante pour éviter la perte d'informations liées aux événements SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8e18-131">Make sure that the maximum Windows application log size is large enough to avoid loss of SQL Server event information.</span></span>  
  
 <span data-ttu-id="a8e18-132">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] journalise un message, le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent compare le message aux alertes définies par l'administrateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8e18-132">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logs a message, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service compares the message against the alerts defined by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="a8e18-133">Quelle que soit la source de l'événement, le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent répond à l'événement en exécutant les tâches spécifiées dans l'alerte de cet événement.</span><span class="sxs-lookup"><span data-stu-id="a8e18-133">Regardless of the source of the event, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service responds to the event by performing the tasks specified in the alert for the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e18-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8e18-134">See Also</span></span>  
 [<span data-ttu-id="a8e18-135">sp_altermessage &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a8e18-135">sp_altermessage &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
  
