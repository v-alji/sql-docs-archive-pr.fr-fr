---
title: Supprimer une publication | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing publications
- publications [SQL Server replication], deleting
- articles [SQL Server replication], deleting
- deleting publications
ms.assetid: 408a1360-12ee-4896-ac94-482ae839593b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d2b39a326d59333868b4f8015eb9a2e59d59e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709140"
---
# <a name="delete-a-publication"></a><span data-ttu-id="6f984-102">Supprimer une publication</span><span class="sxs-lookup"><span data-stu-id="6f984-102">Delete a Publication</span></span>
  <span data-ttu-id="6f984-103">Cette rubrique explique comment supprimer une publication dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="6f984-103">This topic describes how to delete a publication in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="6f984-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="6f984-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6f984-105">**Pour supprimer une publication à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="6f984-105">**To delete a publication, using:**</span></span>  
  
     [<span data-ttu-id="6f984-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6f984-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6f984-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6f984-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="6f984-108">Objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="6f984-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6f984-109">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6f984-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6f984-110">Supprimer les publications dans le dossier **Publications locales** de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f984-110">Delete publications from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-a-publication"></a><span data-ttu-id="6f984-111">Pour supprimer une publication</span><span class="sxs-lookup"><span data-stu-id="6f984-111">To delete a publication</span></span>  
  
1.  <span data-ttu-id="6f984-112">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="6f984-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="6f984-113">Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .</span><span class="sxs-lookup"><span data-stu-id="6f984-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="6f984-114">Cliquez avec le bouton droit sur la publication à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6f984-114">Right-click the publication you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6f984-115">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6f984-115">Using Transact-SQL</span></span>  
 <span data-ttu-id="6f984-116">Il est possible de supprimer des publications par programme en utilisant les procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="6f984-116">Publications can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="6f984-117">Les procédures stockées à utiliser dépendent du type de publication à supprimer.</span><span class="sxs-lookup"><span data-stu-id="6f984-117">The stored procedures that you use depend on the type of publication being deleted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f984-118">La suppression d'une publication ne supprime pas les objets publiés de la base de données de publication ni les objets correspondants de la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="6f984-118">Deleting a publication does not remove published objects from the publication database or the corresponding objects from the subscription database.</span></span> <span data-ttu-id="6f984-119">Utilisez la commande `DROP <object>` pour supprimer manuellement ces objets, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6f984-119">Use the `DROP <object>` command to manually remove these objects if necessary.</span></span>  
  
#### <a name="to-delete-a-snapshot-or-transactional-publication"></a><span data-ttu-id="6f984-120">Pour supprimer une publication d'instantané ou une publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="6f984-120">To delete a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="6f984-121">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f984-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="6f984-122">Pour supprimer une publication unique, exécutez [sp_droppublication](/sql/relational-databases/system-stored-procedures/sp-droppublication-transact-sql) sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="6f984-122">To delete a single publication, execute [sp_droppublication](/sql/relational-databases/system-stored-procedures/sp-droppublication-transact-sql) at the Publisher on the publication database.</span></span>  
  
    -   <span data-ttu-id="6f984-123">Pour supprimer toutes les publications et tous les objets de réplication d'une base de données publiée, exécutez [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="6f984-123">To delete all publications in and remove all replication objects from a published database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) at the Publisher.</span></span> <span data-ttu-id="6f984-124">Spécifiez une valeur `tran` pour \*\* \@ type\*\*.</span><span class="sxs-lookup"><span data-stu-id="6f984-124">Specify a value of `tran` for **\@type**.</span></span> <span data-ttu-id="6f984-125">(Facultatif) Si le serveur de distribution est inaccessible ou si l’état de la base de données est suspect ou hors connexion, spécifiez la valeur **1** pour **\@force**.</span><span class="sxs-lookup"><span data-stu-id="6f984-125">(Optional) If the Distributor cannot be accessed or if the status of the database is suspect or offline, specify a value of **1** for **\@force**.</span></span> <span data-ttu-id="6f984-126">(Facultatif) Spécifiez le nom de la base de données pour **\@dbname** si [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) n’est pas exécuté sur la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="6f984-126">(Optional) Specify the name of the database for **\@dbname** if [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) is not executed on the publication database.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="6f984-127">Spécifier la valeur **1** pour **\@force** peut laisser des objets de publication liés à la réplication dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6f984-127">Specifying a value of **1** for **\@force** may leave replication-related publishing objects in the database.</span></span>  
  
2.  <span data-ttu-id="6f984-128">(Facultatif) Si cette base de données n’a pas d’autres publications, exécutez [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) pour désactiver la publication de la base de données actuelle à l’aide de la réplication transactionnelle ou d’instantané.</span><span class="sxs-lookup"><span data-stu-id="6f984-128">(Optional) If this database has no other publications, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) to disable publication of the current database using snapshot or transactional replication.</span></span>  
  
3.  <span data-ttu-id="6f984-129">(Facultatif) Exécutez [sp_subscription_cleanup](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) sur la base de données d'abonnement de l'Abonné pour supprimer toutes les métadonnées de réplication restantes dans la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="6f984-129">(Optional) At the Subscriber on the subscription database, execute [sp_subscription_cleanup](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove any remaining replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-merge-publication"></a><span data-ttu-id="6f984-130">Pour supprimer une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="6f984-130">To delete a merge publication</span></span>  
  
1.  <span data-ttu-id="6f984-131">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f984-131">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="6f984-132">Pour supprimer une publication unique, exécutez [sp_dropmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepublication-transact-sql) sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="6f984-132">To delete a single publication, execute [sp_dropmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepublication-transact-sql) at the Publisher on the publication database.</span></span>  
  
    -   <span data-ttu-id="6f984-133">Pour supprimer toutes les publications et tous les objets de réplication d'une base de données publiée, exécutez [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="6f984-133">To delete all publications in and remove all replication objects from a published database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) at the Publisher.</span></span> <span data-ttu-id="6f984-134">Spécifiez une valeur `merge` pour \*\* \@ type\*\*.</span><span class="sxs-lookup"><span data-stu-id="6f984-134">Specify a value of `merge` for **\@type**.</span></span> <span data-ttu-id="6f984-135">(Facultatif) Si le serveur de distribution est inaccessible ou si l’état de la base de données est suspect ou hors connexion, spécifiez la valeur **1** pour **\@force**.</span><span class="sxs-lookup"><span data-stu-id="6f984-135">(Optional) If the Distributor cannot be accessed or if the status of the database is suspect or offline, specify a value of **1** for **\@force**.</span></span> <span data-ttu-id="6f984-136">(Facultatif) Spécifiez le nom de la base de données pour **\@dbname** si [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) n’est pas exécuté sur la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="6f984-136">(Optional) Specify the name of the database for **\@dbname** if [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) is not executed on the publication database.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="6f984-137">Spécifier la valeur **1** pour **\@force** peut laisser des objets de publication liés à la réplication dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6f984-137">Specifying a value of **1** for **\@force** may leave replication-related publishing objects in the database.</span></span>  
  
2.  <span data-ttu-id="6f984-138">(Facultatif) Si cette base de données n’a pas d’autres publications, exécutez [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) pour désactiver la publication de la base de données actuelle à l’aide de la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="6f984-138">(Optional) If this database has no other publications, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) to disable publication of the current database using merge replication.</span></span>  
  
3.  <span data-ttu-id="6f984-139">(Facultatif) Exécutez [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) sur la base de données d’abonnement de l’Abonné pour supprimer toutes les métadonnées de réplication restantes dans la base de données d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="6f984-139">(Optional) At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) to remove any remaining replication metadata in the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="6f984-140">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6f984-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="6f984-141">Cet exemple montre comment supprimer une publication transactionnelle et désactiver la publication transactionnelle d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="6f984-141">This example shows how to remove a transactional publication and disable transactional publishing for a database.</span></span> <span data-ttu-id="6f984-142">Cet exemple suppose que tous les abonnements ont été supprimés précédemment.</span><span class="sxs-lookup"><span data-stu-id="6f984-142">This example assumes that all subscriptions were previously removed.</span></span> <span data-ttu-id="6f984-143">Pour plus d'informations, consultez [Delete a Pull Subscription](../delete-a-pull-subscription.md) ou [Delete a Push Subscription](../delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="6f984-143">For more information, see [Delete a Pull Subscription](../delete-a-pull-subscription.md) or [Delete a Push Subscription](../delete-a-push-subscription.md).</span></span>  
  
 [!code-sql[HowTo#sp_droppublication](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droppublication)]  
  
 <span data-ttu-id="6f984-144">Cet exemple montre comment supprimer une publication de fusion et désactiver la publication de fusion d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="6f984-144">This example shows how to remove a merge publication and disable merge publishing for a database.</span></span> <span data-ttu-id="6f984-145">Cet exemple suppose que tous les abonnements ont été supprimés précédemment.</span><span class="sxs-lookup"><span data-stu-id="6f984-145">This example assumes that all subscriptions were previously removed.</span></span> <span data-ttu-id="6f984-146">Pour plus d'informations, consultez [Delete a Pull Subscription](../delete-a-pull-subscription.md) ou [Delete a Push Subscription](../delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="6f984-146">For more information, see [Delete a Pull Subscription](../delete-a-pull-subscription.md) or [Delete a Push Subscription](../delete-a-push-subscription.md).</span></span>  
  
 [!code-sql[HowTo#sp_dropmergepublication](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergepublication)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="6f984-147">Utilisation d'objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="6f984-147">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="6f984-148">Vous pouvez supprimer des publications par programme à l'aide d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="6f984-148">You can delete publications programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="6f984-149">Les classes RMO que vous utilisez pour supprimer une publication dépendent du type de publication que vous supprimez.</span><span class="sxs-lookup"><span data-stu-id="6f984-149">The RMO classes that you use to remove a publication depend on the type of publication you remove.</span></span>  
  
#### <a name="to-remove-a-snapshot-or-transactional-publication"></a><span data-ttu-id="6f984-150">Pour supprimer une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="6f984-150">To remove a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="6f984-151">Créez une connexion au serveur de publication en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="6f984-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="6f984-152">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.TransPublication>.</span><span class="sxs-lookup"><span data-stu-id="6f984-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPublication> class.</span></span>  
  
3.  <span data-ttu-id="6f984-153">Définissez les propriétés <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> et <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> de la publication, et définissez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> avec la connexion créée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="6f984-153">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="6f984-154">Vérifiez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> pour vous assurer que la publication existe.</span><span class="sxs-lookup"><span data-stu-id="6f984-154">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the publication exists.</span></span> <span data-ttu-id="6f984-155">Si la valeur de cette propriété est `false`, les propriétés de la publication définies à l'étape 3 sont incorrectes ou la publication n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="6f984-155">If the value of this property is `false`, either the publication properties in step 3 were defined incorrectly or the publication does not exist.</span></span>  
  
5.  <span data-ttu-id="6f984-156">Appelez la méthode <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="6f984-156">Call the <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> method.</span></span>  
  
6.  <span data-ttu-id="6f984-157">(Facultatif) Si aucune autre publication transactionnelle n'existe pour cette base de données, vous pouvez désactiver la base de données pour la publication transactionnelle en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="6f984-157">(Optional) If no other transactional publications exist for this database, the database can be disabled for transactional publishing as follows:</span></span>  
  
    1.  <span data-ttu-id="6f984-158">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.ReplicationDatabase>.</span><span class="sxs-lookup"><span data-stu-id="6f984-158">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> class.</span></span> <span data-ttu-id="6f984-159">Affectez à la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> l'instance de <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="6f984-159">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the instance of <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1.</span></span>  
  
    2.  <span data-ttu-id="6f984-160">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="6f984-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="6f984-161">Si cette méthode retourne `false`, confirmez que la base de données existe.</span><span class="sxs-lookup"><span data-stu-id="6f984-161">If this method returns `false`, confirm that the database exists.</span></span>  
  
    3.  <span data-ttu-id="6f984-162">Affectez à la propriété <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A> la valeur `false`.</span><span class="sxs-lookup"><span data-stu-id="6f984-162">Set the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A> property to `false`.</span></span>  
  
    4.  <span data-ttu-id="6f984-163">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="6f984-163">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="6f984-164">Fermez les connexions.</span><span class="sxs-lookup"><span data-stu-id="6f984-164">Close the connections.</span></span>  
  
#### <a name="to-remove-a-merge-publication"></a><span data-ttu-id="6f984-165">Pour supprimer une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="6f984-165">To remove a merge publication</span></span>  
  
1.  <span data-ttu-id="6f984-166">Créez une connexion au serveur de publication en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="6f984-166">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="6f984-167">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.MergePublication>.</span><span class="sxs-lookup"><span data-stu-id="6f984-167">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePublication> class.</span></span>  
  
3.  <span data-ttu-id="6f984-168">Définissez les propriétés <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> et <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> de la publication, et définissez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> avec la connexion créée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="6f984-168">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="6f984-169">Vérifiez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> pour vous assurer que la publication existe.</span><span class="sxs-lookup"><span data-stu-id="6f984-169">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the publication exists.</span></span> <span data-ttu-id="6f984-170">Si la valeur de cette propriété est `false`, les propriétés de la publication définies à l'étape 3 sont incorrectes ou la publication n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="6f984-170">If the value of this property is `false`, either the publication properties in step 3 were defined incorrectly or the publication does not exist.</span></span>  
  
5.  <span data-ttu-id="6f984-171">Appelez la méthode <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="6f984-171">Call the <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> method.</span></span>  
  
6.  <span data-ttu-id="6f984-172">(Facultatif) Si aucune autre publication de fusion n'existe pour cette base de données, vous pouvez désactiver la base de données pour la publication de fusion en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="6f984-172">(Optional) If no other merge publications exist for this database, the database can be disabled for merge publishing as follows:</span></span>  
  
    1.  <span data-ttu-id="6f984-173">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.ReplicationDatabase>.</span><span class="sxs-lookup"><span data-stu-id="6f984-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> class.</span></span> <span data-ttu-id="6f984-174">Affectez à la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> l'instance de <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="6f984-174">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the instance of <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from Step 1.</span></span>  
  
    2.  <span data-ttu-id="6f984-175">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="6f984-175">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="6f984-176">Si cette méthode retourne `false`, vérifiez que la base de données existe.</span><span class="sxs-lookup"><span data-stu-id="6f984-176">If this method returns `false`, verify that the database exists.</span></span>  
  
    3.  <span data-ttu-id="6f984-177">Affectez à la propriété <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> la valeur `false`.</span><span class="sxs-lookup"><span data-stu-id="6f984-177">Set the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> property to `false`.</span></span>  
  
    4.  <span data-ttu-id="6f984-178">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="6f984-178">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="6f984-179">Fermez les connexions.</span><span class="sxs-lookup"><span data-stu-id="6f984-179">Close the connections.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="6f984-180">Exemples (RMO)</span><span class="sxs-lookup"><span data-stu-id="6f984-180">Examples (RMO)</span></span>  
 <span data-ttu-id="6f984-181">L'exemple suivant supprime une publication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="6f984-181">The following example deletes a transactional publication.</span></span> <span data-ttu-id="6f984-182">Si aucune autre publication transactionnelle n'existe pour cette base de données, la publication transactionnelle est également désactivée.</span><span class="sxs-lookup"><span data-stu-id="6f984-182">If no other transactional publications exist for this database, transactional publishing is also disabled.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpub)]  
  
 <span data-ttu-id="6f984-183">L'exemple suivant supprime une publication de fusion.</span><span class="sxs-lookup"><span data-stu-id="6f984-183">The following example deletes a merge publication.</span></span> <span data-ttu-id="6f984-184">Si aucune autre publication de fusion n'existe pour cette base de données, la publication de fusion est également désactivée.</span><span class="sxs-lookup"><span data-stu-id="6f984-184">If no other merge publications exist for this database, merge publishing is also disabled.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropMergePub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropmergepub)]  
  
 [!code-vb[HowTo#rmo_vb_DropMergePub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropmergepub)]  
  
## <a name="see-also"></a><span data-ttu-id="6f984-185">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6f984-185">See Also</span></span>  
 <span data-ttu-id="6f984-186">[Concepts liés aux procédures stockées système de réplication](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="6f984-186">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="6f984-187">Publier des données et des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="6f984-187">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  
