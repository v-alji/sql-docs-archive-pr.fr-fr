---
title: Synchroniser un abonnement par extraction | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- pull subscriptions [SQL Server replication], synchronizing
- synchronization [SQL Server replication], pull subscriptions
- subscriptions [SQL Server replication], pull
ms.assetid: 3ca24b23-fdc3-408e-8208-a2ace48fc8e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 826622cd17862c0535e60c01baab756af2b2996b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610601"
---
# <a name="synchronize-a-pull-subscription"></a><span data-ttu-id="1081c-102">Synchroniser un abonnement par extraction</span><span class="sxs-lookup"><span data-stu-id="1081c-102">Synchronize a Pull Subscription</span></span>
  <span data-ttu-id="1081c-103">Cette rubrique explique comment synchroniser un abonnement par extraction de données (pull) dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], d' [agents de réplication](agents/replication-agents-overview.md)ou d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="1081c-103">This topic describes how to synchronize a pull subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1081c-104">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1081c-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1081c-105">Les abonnements sont synchronisés par l'Agent de distribution (pour la réplication transactionnelle et d'instantané) ou l'Agent de fusion (pour la réplication de fusion).</span><span class="sxs-lookup"><span data-stu-id="1081c-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="1081c-106">Les agents peuvent s'exécuter en continu, à la demande ou selon une planification.</span><span class="sxs-lookup"><span data-stu-id="1081c-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="1081c-107">Pour plus d’informations sur la spécification de planifications de synchronisation, consultez [Spécifier des planifications de synchronisation](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="1081c-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="1081c-108">Synchronisez un abonnement à la demande à partir du dossier **Publications locales** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1081c-108">Synchronize a subscription on demand from the **Local Subscriptions** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-on-demand-in-management-studio"></a><span data-ttu-id="1081c-109">Pour synchroniser à la demande un abonnement par extraction de données dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="1081c-109">To synchronize a pull subscription on demand in Management Studio</span></span>  
  
1.  <span data-ttu-id="1081c-110">Connectez-vous à l'Abonné dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="1081c-110">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="1081c-111">Développez le dossier **Réplication** , puis développez le dossier **Abonnements locaux** .</span><span class="sxs-lookup"><span data-stu-id="1081c-111">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="1081c-112">Cliquez avec le bouton droit sur l'abonnement à synchroniser, puis cliquez sur **Afficher l'état de synchronisation**.</span><span class="sxs-lookup"><span data-stu-id="1081c-112">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="1081c-113">Dans la boîte de dialogue **Afficher l'état de synchronisation - \<Subscriber>:\<SubscriptionDatabase>** cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="1081c-113">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="1081c-114">Lorsque la synchronisation est terminée, le message **Synchronisation terminée** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="1081c-114">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
5.  <span data-ttu-id="1081c-115">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="1081c-115">Click **Close**.</span></span>  
  
##  <a name="replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="1081c-116">Replication Agents</span><span class="sxs-lookup"><span data-stu-id="1081c-116">Replication Agents</span></span>  
 <span data-ttu-id="1081c-117">Les abonnements par extraction de données (pull) peuvent être synchronisés par le biais de la programmation et à la demande en appelant le fichier exécutable de l'Agent de réplication approprié à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="1081c-117">Pull subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="1081c-118">Le fichier exécutable de l'Agent de réplication qui est appelé dépend du type de publication à laquelle l'abonnement par extraction de données (pull) appartient.</span><span class="sxs-lookup"><span data-stu-id="1081c-118">The replication agent executable file that is invoked will depend on the type of publication to which the pull subscription belongs.</span></span> <span data-ttu-id="1081c-119">Pour plus d'informations, voir [Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1081c-119">For more information, see [Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1081c-120">Les Agents de réplication se connectent au serveur local au moyen des informations d'identification d'authentification Windows de l'utilisateur qui a démarré l'agent à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="1081c-120">Replication agents connect to the local server using the Windows Authentication credentials of the user who started the agent from the command prompt.</span></span> <span data-ttu-id="1081c-121">Ces informations d'identification Windows sont également utilisées lors de la connexion à des serveurs distants au moyen de l'authentification intégrée Windows.</span><span class="sxs-lookup"><span data-stu-id="1081c-121">These Windows credentials are also used when connecting to remote servers using Windows Integrated Authentication.</span></span>  
  
#### <a name="to-start-the-distribution-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="1081c-122">Pour démarrer l'Agent de distribution à partir de l'invite de commandes ou à partir d'un fichier de commandes</span><span class="sxs-lookup"><span data-stu-id="1081c-122">To start the distribution agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="1081c-123">À partir de l'invite de commandes ou dans un fichier de commandes, démarrez l' [Agent de distribution de réplication](agents/replication-distribution-agent.md) en exécutant **distrib.exe**et en spécifiant les arguments suivant sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="1081c-123">From the command prompt or in a batch file, start the [Replication Distribution Agent](agents/replication-distribution-agent.md) by running **distrib.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="1081c-124">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="1081c-124">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="1081c-125">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="1081c-125">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="1081c-126">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="1081c-126">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="1081c-127">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="1081c-127">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="1081c-128">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="1081c-128">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="1081c-129">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="1081c-129">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="1081c-130">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="1081c-130">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="1081c-131">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="1081c-131">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="1081c-132">Si vous utilisez l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devez également spécifier les arguments suivants :</span><span class="sxs-lookup"><span data-stu-id="1081c-132">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="1081c-133">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="1081c-133">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="1081c-134">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="1081c-134">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="1081c-135">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="1081c-135">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="1081c-136">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="1081c-136">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="1081c-137">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="1081c-137">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="1081c-138">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="1081c-138">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="1081c-139">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="1081c-139">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="1081c-140">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="1081c-140">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="1081c-141">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="1081c-141">**-SubscriberSecurityMode** = **0**</span></span>  
  
#### <a name="to-start-the-merge-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="1081c-142">Pour démarrer l'Agent de fusion à partir de l'invite de commandes ou à partir d'un fichier de commandes</span><span class="sxs-lookup"><span data-stu-id="1081c-142">To start the merge agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="1081c-143">À partir de l'invite de commandes ou dans un fichier de commandes, démarrez l' [Agent de fusion de réplication](agents/replication-merge-agent.md) en exécutant **replmerg.exe**et en spécifiant les arguments suivant sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="1081c-143">From the command prompt or in a batch file, start the [Replication Merge Agent](agents/replication-merge-agent.md) by running **replmerg.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="1081c-144">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="1081c-144">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="1081c-145">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="1081c-145">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="1081c-146">**-PublisherSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="1081c-146">**-PublisherSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="1081c-147">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="1081c-147">**-Publication**</span></span>  
  
    -   <span data-ttu-id="1081c-148">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="1081c-148">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="1081c-149">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="1081c-149">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="1081c-150">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="1081c-150">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="1081c-151">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="1081c-151">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="1081c-152">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="1081c-152">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="1081c-153">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="1081c-153">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="1081c-154">Si vous utilisez l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devez également spécifier les arguments suivants :</span><span class="sxs-lookup"><span data-stu-id="1081c-154">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="1081c-155">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="1081c-155">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="1081c-156">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="1081c-156">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="1081c-157">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="1081c-157">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="1081c-158">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="1081c-158">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="1081c-159">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="1081c-159">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="1081c-160">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="1081c-160">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="1081c-161">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="1081c-161">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="1081c-162">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="1081c-162">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="1081c-163">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="1081c-163">**-SubscriberSecurityMode** = **0**</span></span>  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="1081c-164">Exemples (Agents de réplication)</span><span class="sxs-lookup"><span data-stu-id="1081c-164">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="1081c-165">L'exemple suivant démarre l'Agent de distribution pour synchroniser un abonnement par extraction de données (pull).</span><span class="sxs-lookup"><span data-stu-id="1081c-165">The following example starts the Distribution Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="1081c-166">Toutes les connexions sont effectuées au moyen de l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="1081c-166">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_synctranpullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/synctranpullsub_10.bat)]  
  
 <span data-ttu-id="1081c-167">L'exemple suivant démarre l'Agent de fusion pour synchroniser un abonnement par extraction de données (pull).</span><span class="sxs-lookup"><span data-stu-id="1081c-167">The following example starts the Merge Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="1081c-168">Toutes les connexions sont effectuées au moyen de l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="1081c-168">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_syncmergepullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/syncmergepullsub_10.bat)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="1081c-169">Utilisation d'objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="1081c-169">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="1081c-170">Vous pouvez synchroniser des abonnements par extraction de données (pull) au moyen d'objets RMO (Replication Management Objects) et d'un accès par code managé aux fonctionnalités de l'Agent de réplication.</span><span class="sxs-lookup"><span data-stu-id="1081c-170">You can synchronize pull subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="1081c-171">Les classes que vous utilisez pour synchroniser un abonnement par extraction de données (pull) sont fonction du type de publication à laquelle l'abonnement appartient.</span><span class="sxs-lookup"><span data-stu-id="1081c-171">The classes you use to synchronize a pull subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1081c-172">Si vous voulez démarrer une synchronisation qui s'exécute de façon autonome sans affecter votre application, démarrez l'agent en mode asynchrone.</span><span class="sxs-lookup"><span data-stu-id="1081c-172">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="1081c-173">Toutefois, si vous voulez analyser le résultat de la synchronisation et recevoir des rappels à partir de l'agent au cours du processus de synchronisation (par exemple, pour afficher une barre de progression), démarrez l'agent en mode synchrone.</span><span class="sxs-lookup"><span data-stu-id="1081c-173">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="1081c-174">Pour Abonnés [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] , vous devez démarrer l’agent en mode synchrone.</span><span class="sxs-lookup"><span data-stu-id="1081c-174">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="1081c-175">Pour synchroniser un abonnement par extraction vers une publication d'instantané ou transactionnelle</span><span class="sxs-lookup"><span data-stu-id="1081c-175">To synchronize a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="1081c-176">Créez une connexion à l'Abonné en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="1081c-176">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="1081c-177">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.TransPullSubscription> et définissez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="1081c-177">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="1081c-178">Le nom de la base de données d'abonnement pour <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="1081c-178">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="1081c-179">Le nom de la publication à laquelle l'abonnement appartient pour <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="1081c-179">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="1081c-180">le nom de la base de données de publication pour <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>;</span><span class="sxs-lookup"><span data-stu-id="1081c-180">The name of the publication database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="1081c-181">Le nom du serveur de publication pour <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span><span class="sxs-lookup"><span data-stu-id="1081c-181">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="1081c-182">La connexion créée à l'étape 1 pour <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="1081c-182">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="1081c-183">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> pour obtenir les propriétés d'abonnement restantes.</span><span class="sxs-lookup"><span data-stu-id="1081c-183">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="1081c-184">Si cette méthode retourne `false`, vérifiez que l'abonnement existe.</span><span class="sxs-lookup"><span data-stu-id="1081c-184">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="1081c-185">Démarrez l'Agent de distribution sur l'Abonné de l'une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="1081c-185">Start the Distribution Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="1081c-186">Appelez la méthode <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> sur l'instance de <xref:Microsoft.SqlServer.Replication.TransPullSubscription> obtenue à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="1081c-186">Call the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransPullSubscription> from step 2.</span></span> <span data-ttu-id="1081c-187">Cette méthode démarre l'Agent de distribution en mode asynchrone et votre application récupère immédiatement le contrôle pendant l'exécution du travail de l'agent.</span><span class="sxs-lookup"><span data-stu-id="1081c-187">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="1081c-188">Vous ne pouvez pas appeler cette méthode pour les Abonnés [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] ou si l'abonnement a été créé avec la valeur `false` pour <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (la valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="1081c-188">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="1081c-189">Obtenez une instance de la classe <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> à partir de la propriété <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> et appelez la méthode <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="1081c-189">Get an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="1081c-190">Cette méthode démarre l'agent en mode synchrone, et le travail d'agent en cours d'exécution conserve le contrôle.</span><span class="sxs-lookup"><span data-stu-id="1081c-190">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="1081c-191">Au cours de l'exécution synchrone, vous pouvez gérer l'événement <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> pendant que l'agent est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="1081c-191">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1081c-192">Si vous avez spécifié la valeur `false` pour <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (valeur par défaut) lorsque vous avez créé l’abonnement par extraction, vous devez également spécifier <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A> , <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A> et éventuellement, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> et <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> parce que les métadonnées liées au travail de l’agent pour l’abonnement ne sont pas disponibles dans [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1081c-192">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A>, and optionally <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> and <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="1081c-193">Pour synchroniser un abonnement par extraction de données (pull) vers une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="1081c-193">To synchronize a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="1081c-194">Créez une connexion à l'Abonné en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="1081c-194">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="1081c-195">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.MergePullSubscription> et définissez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="1081c-195">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="1081c-196">Le nom de la base de données d'abonnement pour <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="1081c-196">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="1081c-197">Le nom de la publication à laquelle l'abonnement appartient pour <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="1081c-197">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="1081c-198">Le nom de la base de données publiée pour <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="1081c-198">The name of the published database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="1081c-199">Le nom du serveur de publication pour <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span><span class="sxs-lookup"><span data-stu-id="1081c-199">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="1081c-200">La connexion créée à l'étape 1 pour <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="1081c-200">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="1081c-201">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> pour obtenir les propriétés d'abonnement restantes.</span><span class="sxs-lookup"><span data-stu-id="1081c-201">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="1081c-202">Si cette méthode retourne `false`, vérifiez que l'abonnement existe.</span><span class="sxs-lookup"><span data-stu-id="1081c-202">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="1081c-203">Démarrez l'Agent de fusion sur l'Abonné de l'une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="1081c-203">Start the Merge Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="1081c-204">Appelez la méthode <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> sur l'instance de <xref:Microsoft.SqlServer.Replication.MergePullSubscription> obtenue à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="1081c-204">Call the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergePullSubscription> from step 2.</span></span> <span data-ttu-id="1081c-205">Cette méthode démarre l'Agent de fusion en mode asynchrone et votre application récupère immédiatement le contrôle pendant l'exécution du travail de l'agent.</span><span class="sxs-lookup"><span data-stu-id="1081c-205">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="1081c-206">Vous ne pouvez pas appeler cette méthode pour les Abonnés [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] ou si l'abonnement a été créé avec la valeur `false` pour <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (la valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="1081c-206">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="1081c-207">Obtenez une instance de la classe <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> à partir de la propriété <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> et appelez la méthode <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="1081c-207">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="1081c-208">Cette méthode démarre l'Agent de fusion en mode synchrone, et le travail d'agent en cours d'exécution conserve le contrôle.</span><span class="sxs-lookup"><span data-stu-id="1081c-208">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="1081c-209">Au cours de l'exécution synchrone, vous pouvez gérer l'événement <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> pendant que l'agent est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="1081c-209">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1081c-210">Si vous avez spécifié la valeur `false` pour <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (valeur par défaut) lorsque vous avez créé l’abonnement par extraction, vous devez également spécifier <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A> et, éventuellement,, et <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> parce que les métadonnées associées au travail de l’agent pour l’abonnement ne sont pas disponibles dans [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1081c-210">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A>, and optionally <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A>, and <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="1081c-211">Exemples (RMO)</span><span class="sxs-lookup"><span data-stu-id="1081c-211">Examples (RMO)</span></span>  
 <span data-ttu-id="1081c-212">Cet exemple synchronise un abonnement par envoi de données (pull) vers une publication transactionnelle, où l'agent est démarré en mode asynchrone au moyen du travail d'agent.</span><span class="sxs-lookup"><span data-stu-id="1081c-212">This example synchronizes a pull subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub_withjob)]  
  
 <span data-ttu-id="1081c-213">Cet exemple synchronise un abonnement par envoi de données (pull) vers une publication transactionnelle, où l'agent est démarré en mode synchrone.</span><span class="sxs-lookup"><span data-stu-id="1081c-213">This example synchronizes a pull subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub)]  
  
 <span data-ttu-id="1081c-214">Cet exemple synchronise un abonnement par envoi de données (pull) vers une publication de fusion, où l'agent est démarré en mode asynchrone au moyen du travail d'agent.</span><span class="sxs-lookup"><span data-stu-id="1081c-214">This example synchronizes a pull subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_withjob)]  
  
 <span data-ttu-id="1081c-215">Cet exemple synchronise un abonnement par envoi de données (pull) vers une publication de fusion, où l'agent est démarré en mode synchrone.</span><span class="sxs-lookup"><span data-stu-id="1081c-215">This example synchronizes a pull subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub)]  
  
 <span data-ttu-id="1081c-216">Cet exemple synchronise un abonnement par extraction de données (pull) vers une publication de fusion au moyen de la synchronisation Web.</span><span class="sxs-lookup"><span data-stu-id="1081c-216">This example synchronizes a pull subscription to a merge publication using Web synchronization.</span></span> <span data-ttu-id="1081c-217">Dans la mesure où l'abonnement a été créé sans le travail d'agent et les métadonnées d'abonnement associées, l'agent doit être démarré en mode synchrone et des informations d'abonnement supplémentaires sont fournies.</span><span class="sxs-lookup"><span data-stu-id="1081c-217">The subscription was created without the agent job and related subscription metadata, so the agent must be started synchronously and additional subscription information is supplied.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_NoJobWebSync](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_nojobwebsync)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_NoJobWebSync](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_nojobwebsync)]  
  
## <a name="see-also"></a><span data-ttu-id="1081c-218">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1081c-218">See Also</span></span>  
 <span data-ttu-id="1081c-219">[Synchroniser les données](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="1081c-219">[Synchronize Data](synchronize-data.md) </span></span>  
 <span data-ttu-id="1081c-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="1081c-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="1081c-221">Bonnes pratiques en matière de sécurité de la réplication</span><span class="sxs-lookup"><span data-stu-id="1081c-221">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
