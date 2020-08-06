---
title: Afficher et modifier les propriétés d’un abonnement par extraction | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- modifying subscriptions
- viewing replication properties
- modifying replication properties, pull subscriptions
- pull subscriptions [SQL Server replication], modifying
- subscriptions [SQL Server replication], pull
- pull subscriptions [SQL Server replication], properties
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 1601e54f-86f0-49e8-b023-87a5d1def033
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b847a22d31bbf3ea7540c55339fe27531134125
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600754"
---
# <a name="view-and-modify-pull-subscription-properties"></a><span data-ttu-id="ad069-102">Afficher et modifier les propriétés d'un abonnement par extraction (pull)</span><span class="sxs-lookup"><span data-stu-id="ad069-102">View and Modify Pull Subscription Properties</span></span>
  <span data-ttu-id="ad069-103">Cette rubrique décrit comment afficher et modifier les propriétés de l'abonnement par extraction (pull) dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)]ou d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="ad069-103">This topic describes how to view and modify pull subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="ad069-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ad069-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ad069-105">**Pour afficher et modifier les propriétés d'un abonnement par extraction à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="ad069-105">**To view and modify pull subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="ad069-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad069-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ad069-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad069-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="ad069-108">Objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="ad069-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ad069-109">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad069-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ad069-110">Affichez les propriétés de l'abonnement par extraction à partir du serveur de Publication ou de l'Abonné dans la boîte de dialogue **Propriétés de l'abonnement - \<Publisher> : \<PublicationDatabase>** , disponible dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad069-110">View pull subscription properties from the Publisher or the Subscriber in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ad069-111">Vous pouvez modifier des propriétés ou en afficher d'autres sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="ad069-111">More properties are visible from the Subscriber, and properties can be modified at the Subscriber.</span></span> <span data-ttu-id="ad069-112">Vous pouvez également afficher des propriétés à partir du serveur de publication sous l'onglet **Tous les abonnements** , disponible dans le moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="ad069-112">You can also view properties from the Publisher on the **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="ad069-113">Pour plus d’informations sur le démarrage du Moniteur de réplication, consultez [Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ad069-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-management-studio"></a><span data-ttu-id="ad069-114">Pour afficher des propriétés d'extraction d'abonnement à partir du serveur de publication dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad069-114">To view pull subscription properties from the Publisher in Management Studio</span></span>  
  
1.  <span data-ttu-id="ad069-115">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="ad069-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="ad069-116">Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .</span><span class="sxs-lookup"><span data-stu-id="ad069-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="ad069-117">Développez la publication appropriée, cliquez avec le bouton droit sur un abonnement puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ad069-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ad069-118">Affichez les propriétés, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad069-118">View properties, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-pull-subscription-properties-from-the-subscriber-in-management-studio"></a><span data-ttu-id="ad069-119">Pour afficher et modifier des propriétés d'extraction d'abonnement à partir de l'Abonné dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad069-119">To view and modify pull subscription properties from the Subscriber in Management Studio</span></span>  
  
1.  <span data-ttu-id="ad069-120">Connectez-vous à l'Abonné dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="ad069-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="ad069-121">Développez le dossier **Réplication** , puis développez le dossier **Abonnements locaux** .</span><span class="sxs-lookup"><span data-stu-id="ad069-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="ad069-122">Cliquez avec le bouton droit sur un abonnement, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ad069-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ad069-123">Modifiez les propriétés si nécessaire, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad069-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-pull-subscription-properties-from-the-publisher-in-replication-monitor"></a><span data-ttu-id="ad069-124">Pour afficher des propriétés d'extraction d'abonnement à partir du serveur de publication dans le moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="ad069-124">To view pull subscription properties from the Publisher in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="ad069-125">Développez un groupe Serveur de publication dans le volet gauche du moniteur de réplication, développez un serveur de publication puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="ad069-125">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="ad069-126">Cliquez sur l'onglet **Tous les abonnements** .</span><span class="sxs-lookup"><span data-stu-id="ad069-126">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="ad069-127">Cliquez avec le bouton droit sur un abonnement, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ad069-127">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ad069-128">Affichez les propriétés, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad069-128">View properties, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ad069-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad069-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="ad069-130">Il est possible de modifier des abonnements par extraction et d'accéder par programme à leurs propriétés en utilisant des procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="ad069-130">Pull subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="ad069-131">Les procédures stockées utilisées dépendent du type de publication auquel l'abonnement appartient.</span><span class="sxs-lookup"><span data-stu-id="ad069-131">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="ad069-132">Pour afficher les propriétés d'un abonnement par extraction à une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="ad069-132">To view the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="ad069-133">Sur l'Abonné, exécutez [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad069-133">At the Subscriber, execute [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql).</span></span> <span data-ttu-id="ad069-134">Spécifiez **@publisher** , **@publisher_db** et **@publication** .</span><span class="sxs-lookup"><span data-stu-id="ad069-134">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="ad069-135">Des informations relatives à l'abonnement qui est stocké dans les tables système de l'Abonné sont alors renvoyées.</span><span class="sxs-lookup"><span data-stu-id="ad069-135">This returns information about the subscription that is stored in system tables at the Subscriber.</span></span>  
  
2.  <span data-ttu-id="ad069-136">Sur l'Abonné, exécutez [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad069-136">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="ad069-137">Spécifiez **@publisher** ,, **@publisher_db** et l' **@publication** une des valeurs suivantes pour **@publication_type** :</span><span class="sxs-lookup"><span data-stu-id="ad069-137">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@publication_type**:</span></span>  
  
    -   <span data-ttu-id="ad069-138">**0** - l'abonnement appartient à une publication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="ad069-138">**0** - Subscription belongs to a transactional publication.</span></span>  
  
    -   <span data-ttu-id="ad069-139">**1** - l'abonnement appartient à une publication d'instantané.</span><span class="sxs-lookup"><span data-stu-id="ad069-139">**1** - Subscription belongs to a snapshot publication.</span></span>  
  
3.  <span data-ttu-id="ad069-140">Sur le serveur de publication, exécutez [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad069-140">At the Publisher, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="ad069-141">Spécifiez **@publication** et **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="ad069-141">Specify **@publication** and **@subscriber**.</span></span>  
  
4.  <span data-ttu-id="ad069-142">Sur le serveur de publication, exécutez [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), en spécifiant **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="ad069-142">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="ad069-143">Des informations relatives à l'Abonné sont alors affichées.</span><span class="sxs-lookup"><span data-stu-id="ad069-143">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="ad069-144">Pour modifier les propriétés d'un abonnement par extraction à une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="ad069-144">To change the properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="ad069-145">Sur l’abonné, exécutez [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), en spécifiant,, **@publisher** **@publisher_db** **@publication** , une valeur **0** (transactionnel) ou **1** (instantané) pour **@publication_type** , la propriété d’abonnement qui est modifiée comme **@property** et la nouvelle valeur comme **@value** .</span><span class="sxs-lookup"><span data-stu-id="ad069-145">At the Subscriber, execute [sp_change_subscription_properties](/sql/relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql), specifying **@publisher**, **@publisher_db**, **@publication**, a value of either **0** (transactional) or **1** (snapshot) for **@publication_type**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
2.  <span data-ttu-id="ad069-146">(Facultatif) Dans la base de données d'abonnement de l'Abonné, exécutez [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad069-146">(Optional) At the Subscriber on the subscription database, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql).</span></span> <span data-ttu-id="ad069-147">Spécifiez l’ID de la tâche de Agent de distribution pour **@jobid** et les propriétés de package DTS (Data Transformation Services) suivantes :</span><span class="sxs-lookup"><span data-stu-id="ad069-147">Specify the ID of the Distribution Agent job for **@jobid**, and the following Data Transformation Services (DTS) package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="ad069-148">Cela modifie les propriétés de package DTS d'un abonnement.</span><span class="sxs-lookup"><span data-stu-id="ad069-148">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ad069-149">L'ID de travail peut être obtenu en exécutant [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad069-149">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="ad069-150">Pour afficher les propriétés d'un abonnement par extraction à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="ad069-150">To view the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="ad069-151">Sur l'Abonné, exécutez [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad069-151">At the Subscriber, execute [sp_helpmergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergepullsubscription-transact-sql).</span></span> <span data-ttu-id="ad069-152">Spécifiez **@publisher** , **@publisher_db** et **@publication** .</span><span class="sxs-lookup"><span data-stu-id="ad069-152">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span>  
  
2.  <span data-ttu-id="ad069-153">Sur l'Abonné, exécutez [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad069-153">At the Subscriber, execute [sp_helpsubscription_properties](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-properties-transact-sql).</span></span> <span data-ttu-id="ad069-154">Spécifiez **@publisher** ,, **@publisher_db** **@publication** et une valeur de 2 pour **@publication_type** .</span><span class="sxs-lookup"><span data-stu-id="ad069-154">Specify **@publisher**, **@publisher_db**, **@publication**, and a value of 2 for **@publication_type**.</span></span>  
  
3.  <span data-ttu-id="ad069-155">Sur le serveur de publication, exécutez [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) pour afficher les informations d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="ad069-155">At the Publisher, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql) to display subscription information.</span></span> <span data-ttu-id="ad069-156">Pour renvoyer des informations sur un abonnement spécifique, vous devez spécifier **@publication** , **@subscriber** et la valeur **pull** pour **@subscription_type** .</span><span class="sxs-lookup"><span data-stu-id="ad069-156">To return information on a specific subscription, you must specify **@publication**, **@subscriber**, and a value of **pull** for **@subscription_type**.</span></span>  
  
4.  <span data-ttu-id="ad069-157">Sur le serveur de publication, exécutez [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), en spécifiant **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="ad069-157">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span> <span data-ttu-id="ad069-158">Des informations relatives à l'Abonné sont alors affichées.</span><span class="sxs-lookup"><span data-stu-id="ad069-158">This displays information about the Subscriber.</span></span>  
  
#### <a name="to-change-the-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="ad069-159">Pour modifier les propriétés d'un abonnement par extraction à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="ad069-159">To change the properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="ad069-160">Sur l'Abonné, exécutez [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ad069-160">At the Subscriber, execute [sp_changemergepullsubscription](/sql/relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql).</span></span> <span data-ttu-id="ad069-161">Spécifiez **@publication** , **@publisher** ,, **@publisher_db** la propriété d’abonnement qui est modifiée comme **@property** , et la nouvelle valeur comme **@value** .</span><span class="sxs-lookup"><span data-stu-id="ad069-161">Specify **@publication**, **@publisher**, **@publisher_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="ad069-162">Utilisation d'objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="ad069-162">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="ad069-163">Les classes RMO à utiliser pour afficher ou modifier les propriétés d'abonnements par extraction dépendent du type de publication auquel l'abonnement par extraction est souscrit.</span><span class="sxs-lookup"><span data-stu-id="ad069-163">The RMO classes you use to view or modify pull subscription properties depend on the type of publication to which the pull subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="ad069-164">Pour afficher ou modifier les propriétés d'un abonnement par extraction à une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="ad069-164">To view or modify properties of a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="ad069-165">Créez une connexion à l'Abonné en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="ad069-165">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="ad069-166">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.TransPullSubscription>.</span><span class="sxs-lookup"><span data-stu-id="ad069-166">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="ad069-167">Définissez les propriétés <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>et <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="ad069-167">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="ad069-168">Définissez la connexion créée à l'étape 1 pour la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="ad069-168">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="ad069-169">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> pour obtenir les propriétés de l'objet.</span><span class="sxs-lookup"><span data-stu-id="ad069-169">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="ad069-170">Si cette méthode retourne `false`, soit les propriétés de l'abonnement ont été définies de manière incorrecte à l'étape 3, soit l'abonnement n'existe pas sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ad069-170">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="ad069-171">(Facultatif) Pour modifier des propriétés, modifiez la valeur d'une des propriétés <xref:Microsoft.SqlServer.Replication.TransPullSubscription> qui peuvent être définies, puis appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="ad069-171">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="ad069-172">(Facultatif) Pour consulter les nouveaux paramètres, appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> pour recharger les propriétés pour l'article.</span><span class="sxs-lookup"><span data-stu-id="ad069-172">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="ad069-173">Fermez toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="ad069-173">Close all connections.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="ad069-174">Pour afficher ou modifier les propriétés d'un abonnement par extraction à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="ad069-174">To view or modify properties of a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="ad069-175">Créez une connexion à l'Abonné en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="ad069-175">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="ad069-176">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.MergePullSubscription>.</span><span class="sxs-lookup"><span data-stu-id="ad069-176">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class.</span></span>  
  
3.  <span data-ttu-id="ad069-177">Définissez les propriétés <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>et <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="ad069-177">Set the <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>, and <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="ad069-178">Définissez la connexion créée à l'étape 1 pour la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="ad069-178">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="ad069-179">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> pour obtenir les propriétés de l'objet.</span><span class="sxs-lookup"><span data-stu-id="ad069-179">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="ad069-180">Si cette méthode retourne `false`, soit les propriétés de l'abonnement ont été définies de manière incorrecte à l'étape 3, soit l'abonnement n'existe pas sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ad069-180">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist on the server.</span></span>  
  
6.  <span data-ttu-id="ad069-181">(Facultatif) Pour modifier des propriétés, modifiez la valeur d'une des propriétés <xref:Microsoft.SqlServer.Replication.MergePullSubscription> qui peuvent être définies, puis appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="ad069-181">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="ad069-182">(Facultatif) Pour consulter les nouveaux paramètres, appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> pour recharger les propriétés pour l'article.</span><span class="sxs-lookup"><span data-stu-id="ad069-182">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the article.</span></span>  
  
8.  <span data-ttu-id="ad069-183">Fermez toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="ad069-183">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad069-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ad069-184">See Also</span></span>  
 <span data-ttu-id="ad069-185">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="ad069-185">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="ad069-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="ad069-186">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="ad069-187">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="ad069-187">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
