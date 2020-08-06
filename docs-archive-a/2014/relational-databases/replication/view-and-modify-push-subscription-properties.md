---
title: Afficher et modifier les propriétés d’un abonnement par émission de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- push subscriptions [SQL Server replication], properties
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], modifying
- modifying replication properties, push subscriptions
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 801d2995-7aa5-4626-906e-c8190758ec71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1506d4f83fcfb94d62efd01c4d6447048fecfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706360"
---
# <a name="view-and-modify-push-subscription-properties"></a><span data-ttu-id="9a84f-102">Afficher et modifier les propriétés d'un abonnement par émission (push)</span><span class="sxs-lookup"><span data-stu-id="9a84f-102">View and Modify Push Subscription Properties</span></span>
  <span data-ttu-id="9a84f-103">Cette rubrique décrit comment afficher et modifier les propriétés de l'abonnement par émission (push) dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)]ou d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="9a84f-103">This topic describes how to view and modify push subscription properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="9a84f-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="9a84f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9a84f-105">**Pour afficher et modifier les propriétés d'un abonnement par émission (push) à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="9a84f-105">**To view and modify push subscription properties, using:**</span></span>  
  
     [<span data-ttu-id="9a84f-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9a84f-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9a84f-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9a84f-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="9a84f-108">Objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="9a84f-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9a84f-109">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9a84f-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="9a84f-110">Affichez et modifiez les propriétés d'abonnement par envoi de données (push) du serveur de publication dans :</span><span class="sxs-lookup"><span data-stu-id="9a84f-110">View and modify push subscription properties from the Publisher in:</span></span>  
  
-   <span data-ttu-id="9a84f-111">La boîte de dialogue **Propriétés de l'abonnement - \<Publisher>: \<PublicationDatabase>** disponible dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a84f-111">The **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, which is available from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="9a84f-112">L'onglet **Tous les abonnements** , disponible dans le Moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="9a84f-112">The **All Subscriptions** tab, which is available in Replication Monitor.</span></span> <span data-ttu-id="9a84f-113">Pour plus d’informations sur le démarrage du Moniteur de réplication, consultez [Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="9a84f-113">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-management-studio"></a><span data-ttu-id="9a84f-114">Pour afficher et modifier les propriétés d'abonnement par envoi de données (push) dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="9a84f-114">To view and modify push subscription properties in Management Studio</span></span>  
  
1.  <span data-ttu-id="9a84f-115">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="9a84f-115">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="9a84f-116">Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .</span><span class="sxs-lookup"><span data-stu-id="9a84f-116">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="9a84f-117">Développez la publication appropriée, cliquez avec le bouton droit sur un abonnement puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9a84f-117">Expand the appropriate publication, right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="9a84f-118">Modifiez les propriétés si nécessaire, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a84f-118">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-replication-monitor"></a><span data-ttu-id="9a84f-119">Pour afficher et modifier les propriétés d'abonnement par envoi de données (push) dans le Moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="9a84f-119">To view and modify push subscription properties in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="9a84f-120">Développez un groupe Serveur de publication dans le volet gauche du moniteur de réplication, développez un serveur de publication puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="9a84f-120">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="9a84f-121">Cliquez sur l'onglet **Tous les abonnements** .</span><span class="sxs-lookup"><span data-stu-id="9a84f-121">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="9a84f-122">Cliquez avec le bouton droit sur un abonnement, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9a84f-122">Right-click a subscription, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="9a84f-123">Modifiez les propriétés si nécessaire, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a84f-123">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9a84f-124">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9a84f-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="9a84f-125">Il est possible de modifier des abonnements par émission de données et d'accéder à leurs propriétés, par programme, à l'aide des procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="9a84f-125">Push subscriptions can be modified and their properties accessed programmatically using replication stored procedures.</span></span> <span data-ttu-id="9a84f-126">Les procédures stockées utilisées dépendent du type de publication auquel l'abonnement appartient.</span><span class="sxs-lookup"><span data-stu-id="9a84f-126">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="9a84f-127">Pour afficher les propriétés d'un abonnement par émission de données à une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="9a84f-127">To view the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="9a84f-128">Exécutez [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql)sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="9a84f-128">At the Publisher on the publication database, execute [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span> <span data-ttu-id="9a84f-129">Spécifiez **@publication** , **@subscriber** et la valeur **All** pour **@article** .</span><span class="sxs-lookup"><span data-stu-id="9a84f-129">Specify **@publication**, **@subscriber**, and a value of **all** for **@article**.</span></span>  
  
2.  <span data-ttu-id="9a84f-130">Exécutez [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), en spécifiant **@subscriber**.</span><span class="sxs-lookup"><span data-stu-id="9a84f-130">At the Publisher on the publication database, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="9a84f-131">Pour modifier les propriétés d'un abonnement par émission de données à une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="9a84f-131">To change the properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="9a84f-132">Exécutez [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql), en spécifiant **@subscriber** et tous les paramètres des propriétés d'Abonné en cours de modification.</span><span class="sxs-lookup"><span data-stu-id="9a84f-132">At the Publisher on the publication database, execute [sp_changesubscriber](/sql/relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql), specifying **@subscriber** and any parameters for the Subscriber properties being changed.</span></span>  
  
2.  <span data-ttu-id="9a84f-133">Exécutez [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql)sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="9a84f-133">At the Publisher on the publication database, execute [sp_changesubscription](/sql/relational-databases/system-stored-procedures/sp-changesubscription-transact-sql).</span></span> <span data-ttu-id="9a84f-134">Spécifiez **@publication** , **@subscriber** , **@destination_db** , la valeur **All** pour **@article** , la propriété d’abonnement qui est modifiée comme **@property** et la nouvelle valeur comme **@value** .</span><span class="sxs-lookup"><span data-stu-id="9a84f-134">Specify **@publication**, **@subscriber**, **@destination_db**, a value of **all** for **@article**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span> <span data-ttu-id="9a84f-135">Cela modifie les paramètres de sécurité de l'abonnement par émission de données.</span><span class="sxs-lookup"><span data-stu-id="9a84f-135">This changes security settings for the push subscription.</span></span>  
  
3.  <span data-ttu-id="9a84f-136">(Facultatif) Pour modifier les propriétés des packages DTS (Data Transformation Services) d'un abonnement, exécutez [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) sur la base de données d'abonnement de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="9a84f-136">(Optional) To change the Data Transformation Services (DTS) package properties of a subscription, execute [sp_changesubscriptiondtsinfo](/sql/relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="9a84f-137">Spécifiez l’ID de la tâche de Agent de distribution pour **@jobid** et les propriétés de package DTS suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a84f-137">Specify the ID of the Distribution Agent job for **@jobid** and the following DTS package properties:</span></span>  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     <span data-ttu-id="9a84f-138">Cela modifie les propriétés de package DTS d'un abonnement.</span><span class="sxs-lookup"><span data-stu-id="9a84f-138">This changes the DTS package properties of a subscription.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a84f-139">L'ID de travail peut être obtenu en exécutant [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a84f-139">The job ID can be obtained by executing [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql).</span></span>  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="9a84f-140">Pour afficher les propriétés d'un abonnement par émission de données à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="9a84f-140">To view the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="9a84f-141">Exécutez [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql)sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="9a84f-141">At the Publisher on the publication database, execute [sp_helpmergesubscription](/sql/relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql).</span></span> <span data-ttu-id="9a84f-142">Spécifiez **@publication** et **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="9a84f-142">Specify **@publication** and **@subscriber**.</span></span>  
  
2.  <span data-ttu-id="9a84f-143">Sur le serveur de publication, exécutez [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), en spécifiant **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="9a84f-143">At the Publisher, execute [sp_helpsubscriberinfo](/sql/relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql), specifying **@subscriber**.</span></span>  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="9a84f-144">Pour modifier les propriétés d'un abonnement par émission de données à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="9a84f-144">To change the properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="9a84f-145">Exécutez [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql)sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="9a84f-145">At the Publisher on the publication database, execute [sp_changemergesubscription](/sql/relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql).</span></span> <span data-ttu-id="9a84f-146">Spécifiez **@publication** , **@subscriber** ,, **@subscriber_db** la propriété d’abonnement qui est modifiée comme **@property** , et la nouvelle valeur comme **@value** .</span><span class="sxs-lookup"><span data-stu-id="9a84f-146">Specify **@publication**, **@subscriber**, **@subscriber_db**, the subscription property being changed as **@property**, and the new value as **@value**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="9a84f-147">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9a84f-147">Example (Transact-SQL)</span></span>  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="9a84f-148">Utilisation d'objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="9a84f-148">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="9a84f-149">Les classes RMO à utiliser pour afficher ou modifier les propriétés d'un abonnement par émission de données dépendent du type de publication auquel l'abonnement par émission de données a été souscrit.</span><span class="sxs-lookup"><span data-stu-id="9a84f-149">The RMO classes you use to view or modify push subscription properties depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="9a84f-150">Pour afficher ou modifier les propriétés d'un abonnement par émission de données à une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="9a84f-150">To view or modify properties of a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="9a84f-151">Créez une connexion au serveur de publication en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9a84f-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9a84f-152">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.TransSubscription>.</span><span class="sxs-lookup"><span data-stu-id="9a84f-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="9a84f-153">Définissez les propriétés <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>et <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="9a84f-153">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="9a84f-154">Définissez la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créée à l'étape 1 pour le paramètre de propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="9a84f-154">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="9a84f-155">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> pour obtenir les propriétés de l'objet.</span><span class="sxs-lookup"><span data-stu-id="9a84f-155">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="9a84f-156">Si cette méthode retourne `false`, soit les propriétés de l'abonnement ont été définies de manière incorrecte à l'étape 3, soit l'abonnement n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="9a84f-156">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="9a84f-157">(Facultatif) Pour modifier des propriétés, modifiez la valeur d'une des propriétés <xref:Microsoft.SqlServer.Replication.TransSubscription> qui peuvent être définies, puis appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="9a84f-157">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.TransSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="9a84f-158">(Facultatif) Pour afficher les nouveaux paramètres, appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> pour recharger les propriétés pour l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="9a84f-158">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="9a84f-159">Pour afficher ou modifier les propriétés d'un abonnement par émission de données à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="9a84f-159">To view or modify properties of a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="9a84f-160">Créez une connexion à l'Abonné en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9a84f-160">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9a84f-161">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.MergeSubscription>.</span><span class="sxs-lookup"><span data-stu-id="9a84f-161">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="9a84f-162">Définissez les propriétés <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>et <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> .</span><span class="sxs-lookup"><span data-stu-id="9a84f-162">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="9a84f-163">Définissez la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créée à l'étape 1 pour le paramètre de propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="9a84f-163">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property setting.</span></span>  
  
5.  <span data-ttu-id="9a84f-164">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> pour obtenir les propriétés de l'objet.</span><span class="sxs-lookup"><span data-stu-id="9a84f-164">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object.</span></span> <span data-ttu-id="9a84f-165">Si cette méthode retourne `false`, soit les propriétés de l'abonnement ont été définies de manière incorrecte à l'étape 3, soit l'abonnement n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="9a84f-165">If this method returns `false`, either the subscription properties in step 3 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="9a84f-166">(Facultatif) Pour modifier des propriétés, modifiez la valeur d'une des propriétés <xref:Microsoft.SqlServer.Replication.MergeSubscription> qui peuvent être définies, puis appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="9a84f-166">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> properties that can be set, and then call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="9a84f-167">(Facultatif) Pour afficher les nouveaux paramètres, appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> pour recharger les propriétés pour l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="9a84f-167">(Optional) To view the new settings, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> method to reload the properties for the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a84f-168">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a84f-168">See Also</span></span>  
 <span data-ttu-id="9a84f-169">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9a84f-169">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="9a84f-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="9a84f-170">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="9a84f-171">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="9a84f-171">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
