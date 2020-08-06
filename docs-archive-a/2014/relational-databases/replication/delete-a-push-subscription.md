---
title: Supprimer un abonnement par émission de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing subscriptions
- push subscriptions [SQL Server replication], deleting
- deleting subscriptions
- subscriptions [SQL Server replication], push
ms.assetid: 3c4847e2-aed9-4488-b45d-8164422bdb10
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 912958e00d117f51c5dc95c0dc1247d278acb0ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601380"
---
# <a name="delete-a-push-subscription"></a><span data-ttu-id="43aef-102">Supprimer un abonnement par émission (push)</span><span class="sxs-lookup"><span data-stu-id="43aef-102">Delete a Push Subscription</span></span>
  <span data-ttu-id="43aef-103">Cette rubrique explique comment supprimer un abonnement par émission de données (push) dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)]ou d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="43aef-103">This topic describes how to delete a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="43aef-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="43aef-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="43aef-105">**Pour supprimer un abonnement par émission de données (push) à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="43aef-105">**To delete a push subscription, using:**</span></span>  
  
     [<span data-ttu-id="43aef-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43aef-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="43aef-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43aef-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="43aef-108">Objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="43aef-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="43aef-109">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43aef-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="43aef-110">Supprimez un abonnement par émission de données (push) sur le serveur de publication (à partir du dossier **Publications locales** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) ou sur l'Abonné (à partir du dossier **Publications locales** ).</span><span class="sxs-lookup"><span data-stu-id="43aef-110">Delete a push subscription at the Publisher (from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]) or the Subscriber (from the **Local Subscriptions** folder).</span></span> <span data-ttu-id="43aef-111">La suppression d'un abonnement ne supprime pas les objets ou les données de ce dernier : ils doivent être supprimés manuellement.</span><span class="sxs-lookup"><span data-stu-id="43aef-111">Deleting a subscription does not remove objects or data from the subscription; they must be removed manually.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-publisher"></a><span data-ttu-id="43aef-112">Pour supprimer un abonnement par envoi de données au niveau du serveur de publication</span><span class="sxs-lookup"><span data-stu-id="43aef-112">To delete a push subscription at the Publisher</span></span>  
  
1.  <span data-ttu-id="43aef-113">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="43aef-113">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="43aef-114">Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .</span><span class="sxs-lookup"><span data-stu-id="43aef-114">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="43aef-115">Développez la publication associée à l'abonnement à supprimer.</span><span class="sxs-lookup"><span data-stu-id="43aef-115">Expand the publication associated with the subscription you want to delete.</span></span>  
  
4.  <span data-ttu-id="43aef-116">Cliquez avec le bouton droit sur l'abonnement puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="43aef-116">Right-click the subscription, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="43aef-117">Dans la boîte de dialogue de confirmation, indiquez si vous souhaitez vous connecter à l'Abonné pour supprimer les informations d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="43aef-117">In the confirmation dialog box, select whether to connect to the Subscriber to delete subscription information.</span></span> <span data-ttu-id="43aef-118">Si vous désactivez la case à cocher **Se connecter à l'Abonné** , vous devrez vous connecter plus tard à l'Abonné pour supprimer les informations.</span><span class="sxs-lookup"><span data-stu-id="43aef-118">If you clear the **Connect to Subscriber** checkbox, you should connect to the Subscriber later to delete the information.</span></span>  
  
#### <a name="to-delete-a-push-subscription-at-the-subscriber"></a><span data-ttu-id="43aef-119">Pour supprimer un abonnement par envoi de données au niveau de l'Abonné</span><span class="sxs-lookup"><span data-stu-id="43aef-119">To delete a push subscription at the Subscriber</span></span>  
  
1.  <span data-ttu-id="43aef-120">Connectez-vous à l'Abonné dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="43aef-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="43aef-121">Développez le dossier **Réplication** , puis développez le dossier **Abonnements locaux** .</span><span class="sxs-lookup"><span data-stu-id="43aef-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="43aef-122">Cliquez avec le bouton droit sur l'abonnement à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="43aef-122">Right-click the subscription you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="43aef-123">Dans la boîte de dialogue de confirmation, indiquez si vous souhaitez vous connecter au serveur de publication pour supprimer les informations d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="43aef-123">In the confirmation dialog box, select whether to connect to the Publisher to delete subscription information.</span></span> <span data-ttu-id="43aef-124">Si vous désactivez la case à cocher **Se connecter au serveur de publication** , vous devez vous connecter ultérieurement au serveur de publication pour supprimer les informations.</span><span class="sxs-lookup"><span data-stu-id="43aef-124">If you clear the **Connect to Publisher** check box, you should connect to the Publisher later to delete the information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="43aef-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="43aef-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="43aef-126">Les abonnements par émission de données peuvent être supprimés par programme en utilisant des procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="43aef-126">Push subscriptions can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="43aef-127">Les procédures stockées utilisées dépendent du type de publication auquel l'abonnement appartient.</span><span class="sxs-lookup"><span data-stu-id="43aef-127">The stored procedures used depend on the type of publication to which the subscription belongs.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="43aef-128">Pour supprimer un abonnement par émission de données à une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="43aef-128">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="43aef-129">Dans la base de données de publication du serveur de publication, exécutez [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="43aef-129">At the Publisher on the publication database, execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span> <span data-ttu-id="43aef-130">Spécifiez **@publication** et **@subscriber** .</span><span class="sxs-lookup"><span data-stu-id="43aef-130">Specify **@publication** and **@subscriber**.</span></span> <span data-ttu-id="43aef-131">Affectez la valeur **all** à **@article**.</span><span class="sxs-lookup"><span data-stu-id="43aef-131">Specify a value of **all** for **@article**.</span></span> <span data-ttu-id="43aef-132">(Facultatif) Si le serveur de distribution n'est pas accessible, affectez la valeur **1** à **@ignore_distributor** pour supprimer l'abonnement sans supprimer les objets connexes au niveau du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="43aef-132">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="43aef-133">Dans la base de données d’abonnement de l’Abonné, exécutez [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) pour supprimer les métadonnées de réplication dans la base de données d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="43aef-133">At the Subscriber on the subscription database, execute [sp_subscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="43aef-134">Pour supprimer un abonnement par émission de données à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="43aef-134">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="43aef-135">Sur le serveur de publication, exécutez [sp_dropmergesubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), en spécifiant **@publication** **@subscriber** et **@subscriber_db** .</span><span class="sxs-lookup"><span data-stu-id="43aef-135">At the Publisher, execute [sp_dropmergesubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergesubscription-transact-sql), specifying **@publication**, **@subscriber** and **@subscriber_db**.</span></span> <span data-ttu-id="43aef-136">(Facultatif) Si le serveur de distribution n'est pas accessible, affectez la valeur **1** à **@ignore_distributor** pour supprimer l'abonnement sans supprimer les objets connexes au niveau du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="43aef-136">(Optional) If the Distributor cannot be accessed, specify a value of **1** for **@ignore_distributor** to delete the subscription without removing related objects at the Distributor.</span></span>  
  
2.  <span data-ttu-id="43aef-137">Dans la base de données d’abonnement de l’Abonné, exécutez [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="43aef-137">At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql).</span></span> <span data-ttu-id="43aef-138">Spécifiez **@publisher** , **@publisher_db** et **@publication** .</span><span class="sxs-lookup"><span data-stu-id="43aef-138">Specify **@publisher**, **@publisher_db**, and **@publication**.</span></span> <span data-ttu-id="43aef-139">Les métadonnées de fusion sont alors supprimées de la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="43aef-139">This removes merge metadata from the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="43aef-140">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43aef-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="43aef-141">Cet exemple supprime un abonnement par émission de données à une publication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="43aef-141">This example deletes a push subscription to a transactional publication.</span></span>  
  
 [!code-sql[HowTo#sp_droptransubscription](../../snippets/tsql/SQL15/replication/howto/tsql/droptranpullsub.sql#sp_droptransubscription)]  
  
 <span data-ttu-id="43aef-142">Cet exemple supprime un abonnement par émission de données à une publication de fusion.</span><span class="sxs-lookup"><span data-stu-id="43aef-142">This example deletes a push subscription to a merge publication.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergesubscription](../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepullsub.sql#sp_dropmergesubscription)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="43aef-143">Utilisation d'objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="43aef-143">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="43aef-144">Les classes RMO à utiliser pour supprimer un abonnement par émission de données dépendent du type de publication auquel l'abonnement par émission de données est souscrit.</span><span class="sxs-lookup"><span data-stu-id="43aef-144">The RMO classes that you use to delete a push subscription depend on the type of publication to which the push subscription is subscribed.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="43aef-145">Pour supprimer un abonnement par émission de données à une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="43aef-145">To delete a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="43aef-146">Créez une connexion à l'Abonné en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="43aef-146">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="43aef-147">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.TransSubscription>.</span><span class="sxs-lookup"><span data-stu-id="43aef-147">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class.</span></span>  
  
3.  <span data-ttu-id="43aef-148">Définissez les propriétés <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>et <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="43aef-148">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="43aef-149">Définissez la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créée à l'étape 1 pour la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="43aef-149">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="43aef-150">Vérifiez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> pour vous assurer que l'abonnement existe.</span><span class="sxs-lookup"><span data-stu-id="43aef-150">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="43aef-151">Si la valeur de cette propriété est `false`, les propriétés de l'abonnement ont été définies de manière incorrecte à l'étape 2, ou l'article n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="43aef-151">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="43aef-152">Appelez la méthode <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="43aef-152">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
#### <a name="to-delete-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="43aef-153">Pour supprimer un abonnement par émission de données à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="43aef-153">To delete a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="43aef-154">Créez une connexion à l'Abonné en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="43aef-154">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="43aef-155">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.MergeSubscription>.</span><span class="sxs-lookup"><span data-stu-id="43aef-155">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class.</span></span>  
  
3.  <span data-ttu-id="43aef-156">Définissez les propriétés <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>et <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="43aef-156">Set the <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>, and <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="43aef-157">Définissez la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créée à l'étape 1 pour la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="43aef-157">Set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="43aef-158">Vérifiez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> pour vous assurer que l'abonnement existe.</span><span class="sxs-lookup"><span data-stu-id="43aef-158">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the subscription exists.</span></span> <span data-ttu-id="43aef-159">Si la valeur de cette propriété est `false`, les propriétés de l'abonnement ont été définies de manière incorrecte à l'étape 2, ou l'article n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="43aef-159">If the value of this property is `false`, either the subscription properties in step 2 were defined incorrectly or the subscription does not exist.</span></span>  
  
6.  <span data-ttu-id="43aef-160">Appelez la méthode <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="43aef-160">Call the <xref:Microsoft.SqlServer.Replication.Subscription.Remove%2A> method.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="43aef-161">Exemples (RMO)</span><span class="sxs-lookup"><span data-stu-id="43aef-161">Examples (RMO)</span></span>  
 <span data-ttu-id="43aef-162">Vous pouvez supprimer par programme des abonnements par émission de données à l'aide d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="43aef-162">You can delete push subscriptions programmatically by using Replication Management Objects (RMO).</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="43aef-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43aef-163">See Also</span></span>  
 <span data-ttu-id="43aef-164">[S’abonner aux Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="43aef-164">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="43aef-165">Bonnes pratiques en matière de sécurité de la réplication</span><span class="sxs-lookup"><span data-stu-id="43aef-165">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
