---
title: S’abonner à des publications | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.conc.subtopubs.f1
helpviewer_keywords:
- subscriptions [SQL Server replication], about subscriptions
- pull subscriptions [SQL Server replication]
- subscriptions [SQL Server replication]
- push subscriptions [SQL Server replication], about push subscriptions
- merge replication subscribing [SQL Server replication]
- merge replication subscribing [SQL Server replication], about subscribing
- publications [SQL Server replication], subscribing
- push subscriptions [SQL Server replication]
- pull subscriptions [SQL Server replication], about pull subscriptions
- snapshot replication [SQL Server], subscribing
- transactional replication, subscribing
ms.assetid: 088ee30a-05ab-47c4-92ed-316b93e12445
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c565aae26c6d549eb67043168797d5fb059c8e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600759"
---
# <a name="subscribe-to-publications"></a><span data-ttu-id="1e2b6-102">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="1e2b6-102">Subscribe to Publications</span></span>
  <span data-ttu-id="1e2b6-103">Un abonnement est une demande de copie de données et d'objets de base de données d'une publication.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-103">A subscription is a request for a copy of the data and database objects in a publication.</span></span> <span data-ttu-id="1e2b6-104">Il définit la publication qui sera reçue, où et quand elle sera reçue.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-104">A subscription defines which publication will be received, and where and when it will be received.</span></span> <span data-ttu-id="1e2b6-105">Lorsque vous planifiez des abonnements, pensez à l'endroit où vous voulez qu'ait lieu le traitement de l'agent.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-105">When planning for subscriptions, consider where you want agent processing to occur.</span></span> <span data-ttu-id="1e2b6-106">Le type d'abonnement choisi détermine l'emplacement d'exécution de l'agent.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-106">The type of subscription you choose controls where the agent runs.</span></span> <span data-ttu-id="1e2b6-107">Avec un abonnement par envoi de données (push), l'Agent de fusion ou l'Agent de distribution s'exécute sur le serveur de distribution tandis qu'avec un abonnement par extraction de données (pull), les agents s'exécutent sur les Abonnés.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-107">With a push subscription, the Merge Agent or Distribution Agent runs at the Distributor, whereas with a pull subscription, agents run at the Subscribers.</span></span> <span data-ttu-id="1e2b6-108">Il n'est plus possible de modifier le type d'un abonnement une fois celui-ci créé.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-108">After a subscription is created, it cannot be changed from one type to another.</span></span>  
  
|<span data-ttu-id="1e2b6-109">Abonnement</span><span class="sxs-lookup"><span data-stu-id="1e2b6-109">Subscription</span></span>|<span data-ttu-id="1e2b6-110">Caractéristiques</span><span class="sxs-lookup"><span data-stu-id="1e2b6-110">Characteristics</span></span>|<span data-ttu-id="1e2b6-111">Cas d'utilisation</span><span class="sxs-lookup"><span data-stu-id="1e2b6-111">Use When</span></span>|  
|------------------|---------------------|--------------|  
|<span data-ttu-id="1e2b6-112">Abonnement envoyé</span><span class="sxs-lookup"><span data-stu-id="1e2b6-112">Push Subscription</span></span>|<span data-ttu-id="1e2b6-113">Avec un abonnement par envoi de données, le serveur de publication propage les modifications à un Abonné sans que ce dernier en ait fait la demande.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-113">With a push subscription, the Publisher propagates changes to a Subscriber without a request from the Subscriber.</span></span> <span data-ttu-id="1e2b6-114">Les modifications peuvent être envoyées à des Abonnés à la demande, en continu ou selon un horaire planifié.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-114">Changes can be pushed to Subscribers on demand, continuously, or on a scheduled basis.</span></span> <span data-ttu-id="1e2b6-115">L'Agent de distribution ou l'Agent de fusion s'exécute sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-115">The Distribution Agent or Merge Agent runs at the Distributor.</span></span>|<span data-ttu-id="1e2b6-116">Les données sont censées être synchronisées de façon permanente ou à intervalles fréquents et périodiques.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-116">Data will typically be synchronized continuously or on a frequently recurring schedule.</span></span><br /><br /> <span data-ttu-id="1e2b6-117">La publication nécessite un transfert en temps réel (ou presque) des données.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-117">Publications require near real-time movement of data.</span></span><br /><br /> <span data-ttu-id="1e2b6-118">L'augmentation de la charge imposée au processeur d'un serveur de distribution n'affecte pas les performances.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-118">The higher processor overhead at the Distributor does not affect performance.</span></span><br /><br /> <span data-ttu-id="1e2b6-119">Le plus souvent utilisé avec la réplication d'instantané et la réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-119">Most often used with snapshot and transactional replication.</span></span>|  
|<span data-ttu-id="1e2b6-120">Abonnement extrait</span><span class="sxs-lookup"><span data-stu-id="1e2b6-120">Pull Subscription</span></span>|<span data-ttu-id="1e2b6-121">Dans le cas d'un abonnement par extraction, l'Abonné demande à recevoir les modifications apportées sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-121">With a pull subscription, the Subscriber requests changes made at the Publisher.</span></span> <span data-ttu-id="1e2b6-122">Ce type d'abonnement permet à l'utilisateur sur l'Abonné de déterminer le moment où les modifications sont synchronisées.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-122">Pull subscriptions allow the user at the Subscriber to determine when the data changes are synchronized.</span></span> <span data-ttu-id="1e2b6-123">L'Agent de distribution ou l'Agent de fusion s'exécute sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-123">The Distribution Agent or the Merge Agent runs at the Subscriber.</span></span>|<span data-ttu-id="1e2b6-124">Avec ce type d'abonnement, les données sont en général synchronisées à la demande ou selon un horaire planifié plutôt qu'en continu.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-124">Data will typically be synchronized on demand or on a schedule rather than continuously.</span></span><br /><br /> <span data-ttu-id="1e2b6-125">La publication compte un grand nombre d'Abonnés et l'exécution de tous les agents sur un seul site ou sur le serveur de distribution entraînerait une consommation excessive des ressources.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-125">The publication has a large number of Subscribers, and/or it would be too resource-intensive to run all the agents at the Distributor.</span></span><br /><br /> <span data-ttu-id="1e2b6-126">Les abonnés sont autonomes, non connectés et/ou mobiles.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-126">Subscribers are autonomous, disconnected, and/or mobile.</span></span> <span data-ttu-id="1e2b6-127">Ils déterminent à quel moment ils se connectent et synchronisent les modifications.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-127">Subscribers will determine when they will connect and synchronize changes.</span></span><br /><br /> <span data-ttu-id="1e2b6-128">Le plus souvent utilisé avec la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-128">Most often used with merge replication.</span></span>|  
  
## <a name="merge-replication-subscription-types"></a><span data-ttu-id="1e2b6-129">Types d'abonnements de réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="1e2b6-129">Merge Replication Subscription Types</span></span>  
 <span data-ttu-id="1e2b6-130">Tous les types de réplication permettent des abonnements par envoi ou extraction de données.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-130">All replication types allow push and pull subscriptions.</span></span> <span data-ttu-id="1e2b6-131">La réplication de fusion fait la distinction entre deux types d'abonnement : les abonnements client et les abonnements serveur.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-131">Merge replication uses two additional terms to distinguish subscriptions: client subscriptions and server subscriptions.</span></span> <span data-ttu-id="1e2b6-132">Ces deux types d'abonnement sont utilisables avec les abonnements par envoi ou extraction de données.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-132">Both client and server subscription types can be used with push and pull subscriptions.</span></span> <span data-ttu-id="1e2b6-133">Les abonnements client sont adaptés à la plupart des Abonnés, tandis que les abonnements serveur sont généralement utilisés pour les Abonnés qui republient des données vers d'autres Abonnés.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-133">Client subscriptions are appropriate for most Subscribers, whereas server subscriptions are typically used for Subscribers that republish data to other Subscribers.</span></span> <span data-ttu-id="1e2b6-134">Le choix de l'abonnement a également une incidence sur la résolution des conflits.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-134">Subscription choice also affects conflict resolution.</span></span>  
  
## <a name="non-sql-server-subscribers"></a><span data-ttu-id="1e2b6-135">Non-SQL Server Subscribers</span><span class="sxs-lookup"><span data-stu-id="1e2b6-135">Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="1e2b6-136">Oracle et IBM DB2 peuvent s'abonner à des publications transactionnelles et des publications d'instantané à l'aide des abonnements par envoi de données.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-136">Oracle and IBM DB2 can subscribe to snapshot and transactional publications using push subscriptions.</span></span> <span data-ttu-id="1e2b6-137">Pour plus d’informations, consultez [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="1e2b6-137">For more information, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
## <a name="creating-subscriptions"></a><span data-ttu-id="1e2b6-138">Création d'abonnements</span><span class="sxs-lookup"><span data-stu-id="1e2b6-138">Creating Subscriptions</span></span>  
 <span data-ttu-id="1e2b6-139">Pour créer un abonnement, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1e2b6-139">To create a subscription, you supply the following information:</span></span>  
  
-   <span data-ttu-id="1e2b6-140">Nom de la publication.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-140">The name of the publication.</span></span>  
  
-   <span data-ttu-id="1e2b6-141">le nom de l'Abonné et de la base de données d'abonnement ;</span><span class="sxs-lookup"><span data-stu-id="1e2b6-141">The name of the Subscriber and the subscription database.</span></span>  
  
-   <span data-ttu-id="1e2b6-142">si l'Agent de distribution ou l'Agent de fusion s'exécute sur le serveur de distribution ou sur l'Abonné ;</span><span class="sxs-lookup"><span data-stu-id="1e2b6-142">Whether the Distribution Agent or Merge Agent runs at the Distributor or at the Subscriber.</span></span>  
  
-   <span data-ttu-id="1e2b6-143">si l'Agent de distribution ou l'Agent de fusion s'exécute en continu, selon un horaire planifié ou à la demande seulement ;</span><span class="sxs-lookup"><span data-stu-id="1e2b6-143">Whether the Distribution Agent or Merge Agent runs continuously, on a scheduled basis, or on demand only.</span></span>  
  
-   <span data-ttu-id="1e2b6-144">si l'Agent d'instantané doit créer un instantané initial pour l'abonnement et si l'Agent de distribution ou l'Agent de fusion doit appliquer cet instantané sur l'abonné ;</span><span class="sxs-lookup"><span data-stu-id="1e2b6-144">Whether the Snapshot Agent should create an initial snapshot for the subscription and whether the Distribution Agent or Merge Agent should apply that snapshot at the Subscriber.</span></span>  
  
-   <span data-ttu-id="1e2b6-145">les comptes sous lesquels l'Agent de distribution ou l'Agent de fusion s'exécute ;</span><span class="sxs-lookup"><span data-stu-id="1e2b6-145">Accounts under which the Distribution Agent or Merge Agent will run.</span></span>  
  
-   <span data-ttu-id="1e2b6-146">Pour la réplication de fusion, le type d'abonnement : serveur ou client.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-146">For merge replication, the type of subscription: server or client.</span></span>  
  
 <span data-ttu-id="1e2b6-147">**Pour créer un abonnement envoyé**</span><span class="sxs-lookup"><span data-stu-id="1e2b6-147">**To create a push subscription**</span></span>  
  
 [<span data-ttu-id="1e2b6-148">Créer un abonnement par émission de données</span><span class="sxs-lookup"><span data-stu-id="1e2b6-148">Create a Push Subscription</span></span>](create-a-push-subscription.md)  
  
 <span data-ttu-id="1e2b6-149">**Pour afficher ou modifier les propriétés d'un abonnement par envoi de données**</span><span class="sxs-lookup"><span data-stu-id="1e2b6-149">**To view or modify push subscription properties**</span></span>  
  
 [<span data-ttu-id="1e2b6-150">Afficher et modifier les propriétés d’un abonnement par émission (push)</span><span class="sxs-lookup"><span data-stu-id="1e2b6-150">View and Modify Push Subscription Properties</span></span>](view-and-modify-push-subscription-properties.md)  
  
 <span data-ttu-id="1e2b6-151">**Pour supprimer un abonnement par envoi de données**</span><span class="sxs-lookup"><span data-stu-id="1e2b6-151">**To delete a push subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="1e2b6-152">: [Supprimer un abonnement par émission (push)](delete-a-push-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="1e2b6-152">: [Delete a Push Subscription](delete-a-push-subscription.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e2b6-153">La suppression d'un abonnement n'entraîne pas la suppression des objets publiés sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="1e2b6-153">Deleting a subscription does not remove published objects from the Subscriber.</span></span>  
  
 <span data-ttu-id="1e2b6-154">**Pour créer un abonnement par extraction de données**</span><span class="sxs-lookup"><span data-stu-id="1e2b6-154">**To create a pull subscription**</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="1e2b6-155">: [Créer un abonnement par extraction de données (pull)](create-a-pull-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="1e2b6-155">: [Create a Pull Subscription](create-a-pull-subscription.md)</span></span>  
  
 <span data-ttu-id="1e2b6-156">**Pour afficher ou modifier les propriétés d'un abonnement extrait**</span><span class="sxs-lookup"><span data-stu-id="1e2b6-156">**To view or modify pull subscription properties**</span></span>  
  
 [<span data-ttu-id="1e2b6-157">Afficher et modifier les propriétés d’un abonnement par extraction (pull)</span><span class="sxs-lookup"><span data-stu-id="1e2b6-157">View and Modify Pull Subscription Properties</span></span>](view-and-modify-pull-subscription-properties.md)  
  
 <span data-ttu-id="1e2b6-158">**Pour supprimer un abonnement extrait**</span><span class="sxs-lookup"><span data-stu-id="1e2b6-158">**To delete a pull subscription**</span></span>  
  
 [<span data-ttu-id="1e2b6-159">Supprimer un abonnement par extraction (pull)</span><span class="sxs-lookup"><span data-stu-id="1e2b6-159">Delete a Pull Subscription</span></span>](delete-a-pull-subscription.md)  
  
## <a name="see-also"></a><span data-ttu-id="1e2b6-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e2b6-160">See Also</span></span>  
 <span data-ttu-id="1e2b6-161">[Sécuriser l’abonné](security/secure-the-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="1e2b6-161">[Secure the Subscriber](security/secure-the-subscriber.md) </span></span>  
 [<span data-ttu-id="1e2b6-162">Expiration et désactivation des abonnements</span><span class="sxs-lookup"><span data-stu-id="1e2b6-162">Subscription Expiration and Deactivation</span></span>](subscription-expiration-and-deactivation.md)  
  
  
