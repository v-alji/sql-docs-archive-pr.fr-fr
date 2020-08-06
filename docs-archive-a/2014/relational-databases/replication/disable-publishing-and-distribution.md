---
title: Désactiver la publication et la distribution | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- disabling publishing
- publishing [SQL Server replication], disabling
- distribution disabling [SQL Server replication]
- removing replication
- replication [SQL Server], removing
- disabling replication
- disabling distribution
ms.assetid: 6d4a1474-4d13-4826-8be2-80050fafa8a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8843dac310d1e023fe7ce63eded02c9e1bed3731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601376"
---
# <a name="disable-publishing-and-distribution"></a><span data-ttu-id="2dd11-102">Désactiver la publication et la distribution</span><span class="sxs-lookup"><span data-stu-id="2dd11-102">Disable Publishing and Distribution</span></span>
  <span data-ttu-id="2dd11-103">Cette rubrique explique comment désactiver la publication et la distribution dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]ou d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="2dd11-103">This topic describes how to disable publishing and distribution in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="2dd11-104">Vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2dd11-104">You can do the following:</span></span>  
  
-   <span data-ttu-id="2dd11-105">Supprimer toutes les bases de données de distribution sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-105">Delete all distribution databases on the Distributor.</span></span>  
  
-   <span data-ttu-id="2dd11-106">Désactiver tous les serveurs de publication utilisant le serveur de distribution et supprimer toutes les publications situées sur ces serveurs de publication.</span><span class="sxs-lookup"><span data-stu-id="2dd11-106">Disable all Publishers that use the Distributor and delete all publications on those Publishers.</span></span>  
  
-   <span data-ttu-id="2dd11-107">Supprimer tous les abonnements aux publications.</span><span class="sxs-lookup"><span data-stu-id="2dd11-107">Delete all subscriptions to the publications.</span></span> <span data-ttu-id="2dd11-108">Les données des bases de données de publication et d'abonnement ne sont pas supprimées ; elles perdent toutefois leur lien de synchronisation aux bases de données de publication.</span><span class="sxs-lookup"><span data-stu-id="2dd11-108">Data in the publication and subscription databases will not be deleted; however, it loses its synchronization relationship to any publication databases.</span></span> <span data-ttu-id="2dd11-109">Si vous souhaitez supprimer les données de l'Abonné, faites-le manuellement.</span><span class="sxs-lookup"><span data-stu-id="2dd11-109">If you want the data at the Subscriber to be deleted, you must delete it manually.</span></span>  
  
 <span data-ttu-id="2dd11-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2dd11-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2dd11-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2dd11-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2dd11-112">Composants requis</span><span class="sxs-lookup"><span data-stu-id="2dd11-112">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="2dd11-113">**Pour désactiver la publication et la distribution à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="2dd11-113">**To disable publishing and distribution, using:**</span></span>  
  
     [<span data-ttu-id="2dd11-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2dd11-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2dd11-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2dd11-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="2dd11-116">Objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="2dd11-116">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2dd11-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2dd11-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="2dd11-118">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="2dd11-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="2dd11-119">Pour désactiver la publication et la distribution, toutes les bases de données de distribution et de publication doivent être en ligne.</span><span class="sxs-lookup"><span data-stu-id="2dd11-119">To disable publishing and distribution, all distribution and publication databases must be online.</span></span> <span data-ttu-id="2dd11-120">S'il existe des *instantanés de base de données* pour les bases de données de distribution ou de publication, vous devez les supprimer avant de désactiver la publication et la distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-120">If any *database snapshots* exist for distribution or publication databases, they must be dropped before disabling publishing and distribution.</span></span> <span data-ttu-id="2dd11-121">Un instantané de base de données est une copie hors ligne en lecture seule d'une base de données et n'a pas de lien avec un instantané de réplication.</span><span class="sxs-lookup"><span data-stu-id="2dd11-121">A database snapshot is a read-only offline copy of a database and is not related to a replication snapshot.</span></span> <span data-ttu-id="2dd11-122">Pour plus d’informations, consultez [Instantanés de base de données &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2dd11-122">For more information, see [Database Snapshots &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2dd11-123">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2dd11-123">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="2dd11-124">Désactivez la publication et la distribution à l'aide de l'Assistant Désactivation de publication et de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-124">Disable publishing and distribution by using the Disable Publishing and Distribution Wizard.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="2dd11-125">Pour désactiver la publication et la distribution</span><span class="sxs-lookup"><span data-stu-id="2dd11-125">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="2dd11-126">Connectez-vous au serveur de publication ou au serveur de distribution que vous souhaitez désactiver dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="2dd11-126">Connect to the Publisher or Distributor you want to disable in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="2dd11-127">Cliquez avec le bouton droit sur le dossier **Réplication** , puis cliquez sur **Désactiver la publication et la distribution**.</span><span class="sxs-lookup"><span data-stu-id="2dd11-127">Right-click the **Replication** folder, and then click **Disable Publishing and Distribution**.</span></span>  
  
3.  <span data-ttu-id="2dd11-128">Exécutez les étapes de l'Assistant Désactivation de la publication et de la distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-128">Complete the steps in the Disable Publishing and Distribution Wizard.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2dd11-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2dd11-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="2dd11-130">La publication et la distribution peuvent être désactivées par programme à l'aide des procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="2dd11-130">Publishing and distributing can be disabled programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="2dd11-131">Pour désactiver la publication et la distribution</span><span class="sxs-lookup"><span data-stu-id="2dd11-131">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="2dd11-132">Arrêtez tous les travaux liés à la réplication.</span><span class="sxs-lookup"><span data-stu-id="2dd11-132">Stop all replication-related jobs.</span></span> <span data-ttu-id="2dd11-133">Pour obtenir la liste des noms de travaux, consultez la section « Sécurité de l'Agent dans l'Agent SQL Server » de [Modèle de sécurité de l'Agent de réplication](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="2dd11-133">For a list of job names, see the "Agent Security Under SQL Server Agent" section of [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
2.  <span data-ttu-id="2dd11-134">Exécutez [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) sur la base de données d'abonnement de chaque Abonné pour supprimer des objets de réplication de la base de données.</span><span class="sxs-lookup"><span data-stu-id="2dd11-134">At each Subscriber on the subscription database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span> <span data-ttu-id="2dd11-135">Cette procédure stockée ne supprimera pas les travaux de réplication sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-135">This stored procedure will not remove replication jobs at the Distributor.</span></span>  
  
3.  <span data-ttu-id="2dd11-136">Exécutez [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) sur la base de données de publication du serveur de publication pour supprimer des objets de réplication de la base de données.</span><span class="sxs-lookup"><span data-stu-id="2dd11-136">At the Publisher on the publication database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span>  
  
4.  <span data-ttu-id="2dd11-137">Si le serveur de publication utilise un serveur de distribution distant, exécutez [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2dd11-137">If the Publisher uses a remote Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span></span>  
  
5.  <span data-ttu-id="2dd11-138">Sur le serveur de distribution, exécutez [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2dd11-138">At the Distributor, execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span> <span data-ttu-id="2dd11-139">Cette procédure stockée doit être exécutée une fois pour chaque serveur de publication inscrit sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-139">This stored procedure should be run once for each Publisher registered at the Distributor.</span></span>  
  
6.  <span data-ttu-id="2dd11-140">Sur le serveur de distribution, exécutez [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) pour supprimer la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-140">At the Distributor, execute [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) to delete the distribution database.</span></span> <span data-ttu-id="2dd11-141">Cette procédure stockée doit être exécutée une fois pour chaque base de données de distribution sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-141">This stored procedure should be run once for each distribution database at the Distributor.</span></span> <span data-ttu-id="2dd11-142">Cela supprime également tous les travaux de l'Agent de lecture de la file d'attente associés à la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-142">This also removes any Queue Reader Agent jobs associated with the distribution database.</span></span>  
  
7.  <span data-ttu-id="2dd11-143">Sur le serveur de distribution, exécutez [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) pour supprimer la désignation de serveur de distribution du serveur.</span><span class="sxs-lookup"><span data-stu-id="2dd11-143">At the Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) to remove the Distributor designation from the server.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2dd11-144">Si tous les objets de publication et de distribution de la réplication ne sont pas supprimés avant l'exécution de [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) et [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql), ces procédures retourneront une erreur.</span><span class="sxs-lookup"><span data-stu-id="2dd11-144">If all replication publishing and distribution objects are not dropped before you execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) and [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql), these procedures will return an error.</span></span> <span data-ttu-id="2dd11-145">Pour supprimer tous les objets liés à la réplication lorsqu’un serveur de publication ou un serveur de distribution est supprimé, le paramètre \*\* \@ no_checks\*\* doit avoir la valeur **1**.</span><span class="sxs-lookup"><span data-stu-id="2dd11-145">To drop all replication-related objects when a Publisher or Distributor is dropped, the **\@no_checks** parameter must be set to **1**.</span></span> <span data-ttu-id="2dd11-146">Si un serveur de publication ou un serveur de distribution est hors connexion ou inaccessible, le paramètre \*\* \@ ignore_distributor\*\* peut avoir la valeur **1** afin de pouvoir être supprimé. Toutefois, tous les objets de publication et de distribution restants doivent être supprimés manuellement.</span><span class="sxs-lookup"><span data-stu-id="2dd11-146">If a Publisher or Distributor is offline or unreachable, the **\@ignore_distributor** parameter can be set to **1** so that they can be dropped; however, any publishing and distributing objects left behind must be removed manually.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="2dd11-147">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2dd11-147">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="2dd11-148">Cet exemple de script supprime des objets de réplication de la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="2dd11-148">This example script removes replication objects from the subscription database.</span></span>  
  
 [!code-sql[HowTo#sp_removedbreplication](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_removedbreplication)]  
  
 <span data-ttu-id="2dd11-149">Cet exemple de script désactive la publication et la distribution sur un serveur faisant office de serveur de publication et de serveur de distribution et supprime la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-149">This example script disables publishing and distribution on a server that is a Publisher and Distributor and drops the distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_DropDistPub](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_dropdistpub)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="2dd11-150">Utilisation d'objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="2dd11-150">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="2dd11-151">Pour désactiver la publication et la distribution</span><span class="sxs-lookup"><span data-stu-id="2dd11-151">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="2dd11-152">Supprimez tous les abonnements aux publications qui utilisent le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-152">Remove all subscriptions to publications that use the Distributor.</span></span> <span data-ttu-id="2dd11-153">Pour plus d'informations, consultez [Delete a Pull Subscription](delete-a-pull-subscription.md) et [Delete a Push Subscription](delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="2dd11-153">For more information, see [Delete a Pull Subscription](delete-a-pull-subscription.md) and [Delete a Push Subscription](delete-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="2dd11-154">Supprimez toutes les publications qui utilisent le serveur de distribution et désactivez la publication pour toutes les bases de données si le serveur de publication et le serveur de distribution se trouvent sur le même serveur.</span><span class="sxs-lookup"><span data-stu-id="2dd11-154">Remove all publications that use the Distributor, and disable publishing for all databases if the Publisher and Distributor are on the same server.</span></span> <span data-ttu-id="2dd11-155">Pour plus d'informations, voir [Delete a Publication](publish/delete-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="2dd11-155">For more information, see [Delete a Publication](publish/delete-a-publication.md).</span></span>  
  
3.  <span data-ttu-id="2dd11-156">Créez une connexion au serveur de distribution en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="2dd11-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
4.  <span data-ttu-id="2dd11-157">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.</span><span class="sxs-lookup"><span data-stu-id="2dd11-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="2dd11-158">Spécifiez la propriété <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> et passez l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créé à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="2dd11-158">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property, and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
5.  <span data-ttu-id="2dd11-159">(Facultatif) Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> pour obtenir les propriétés de l'objet et vérifier que le serveur de publication existe.</span><span class="sxs-lookup"><span data-stu-id="2dd11-159">(Optional) Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object and verify that the Publisher exists.</span></span> <span data-ttu-id="2dd11-160">Si cette méthode retourne `false`, le nom du serveur de publication défini à l'étape 4 est incorrect ou le serveur de publication n'est pas utilisé par ce serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-160">If this method returns `false`, the Publisher name set in step 4 was incorrect or the Publisher is not used by this Distributor.</span></span>  
  
6.  <span data-ttu-id="2dd11-161">Appelez la méthode <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="2dd11-161">Call the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> method.</span></span> <span data-ttu-id="2dd11-162">Transmettez la valeur `true` pour *force* si le serveur de publication et le serveur de distribution se trouvent sur des serveurs différents, et lorsque le serveur de publication doit être désinstallé au niveau du serveur de distribution sans commencer par vérifier que les publications n’existent plus sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="2dd11-162">Pass a value of `true` for *force* if the Publisher and Distributor are on different servers, and when the Publisher should be uninstalled at the Distributor without first verifying that publications no longer exist at the Publisher.</span></span>  
  
7.  <span data-ttu-id="2dd11-163">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="2dd11-163">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="2dd11-164">Passez l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créé à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="2dd11-164">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
8.  <span data-ttu-id="2dd11-165">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> .</span><span class="sxs-lookup"><span data-stu-id="2dd11-165">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> method.</span></span> <span data-ttu-id="2dd11-166">Transmettez la valeur `true` de *force* pour supprimer tous les objets de réplication sur le serveur de distribution sans vérifier d’abord que toutes les bases de données de publication locales ont été désactivées et que les bases de données de distribution ont été désinstallées.</span><span class="sxs-lookup"><span data-stu-id="2dd11-166">Pass a value of `true` for *force* to remove all replication objects at the Distributor without first verifying that all local publication databases have been disabled, and distribution databases have been uninstalled.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="2dd11-167">Exemples (RMO)</span><span class="sxs-lookup"><span data-stu-id="2dd11-167">Examples (RMO)</span></span>  
 <span data-ttu-id="2dd11-168">Cet exemple supprime l'inscription du serveur de publication au niveau du serveur de distribution, supprime la base de données de distribution et désinstalle le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-168">This example removes the Publisher registration at the Distributor, drops the distribution database, and uninstalls the Distributor.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpub)]  
  
 <span data-ttu-id="2dd11-169">Cet exemple désinstalle le serveur de distribution sans commencer par désactiver les bases de données de publication locales ni supprimer la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="2dd11-169">This example uninstalls the Distributor without first disabling local publication databases or dropping the distribution database.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPubForce](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpubforce)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPubForce](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpubforce)]  
  
## <a name="see-also"></a><span data-ttu-id="2dd11-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2dd11-170">See Also</span></span>  
 <span data-ttu-id="2dd11-171">[Concepts liés à RMO (Replication Management Objects)](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="2dd11-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 [<span data-ttu-id="2dd11-172">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="2dd11-172">Replication System Stored Procedures Concepts</span></span>](concepts/replication-system-stored-procedures-concepts.md)  
  
  
