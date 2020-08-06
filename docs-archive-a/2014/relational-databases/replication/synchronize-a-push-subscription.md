---
title: Synchroniser un abonnement par émission de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], push subscriptions
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], synchronizing
ms.assetid: 0cfa7ae5-91d3-4a4f-9edf-a852d45783b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fb2f7bd961748272d6cd67e3412b09d9370a6f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701027"
---
# <a name="synchronize-a-push-subscription"></a><span data-ttu-id="87a43-102">Synchroniser un abonnement par émission (push)</span><span class="sxs-lookup"><span data-stu-id="87a43-102">Synchronize a Push Subscription</span></span>
  <span data-ttu-id="87a43-103">Cette rubrique explique comment synchroniser un abonnement par émission de données (push) dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], d' [agents de réplication](agents/replication-agents-overview.md)ou d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="87a43-103">This topic describes how to synchronize a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="87a43-104">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="87a43-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="87a43-105">Les abonnements sont synchronisés par l'Agent de distribution (pour la réplication transactionnelle et d'instantané) ou l'Agent de fusion (pour la réplication de fusion).</span><span class="sxs-lookup"><span data-stu-id="87a43-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="87a43-106">Les agents peuvent s'exécuter en continu, à la demande ou selon une planification.</span><span class="sxs-lookup"><span data-stu-id="87a43-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="87a43-107">Pour plus d’informations sur la spécification de planifications de synchronisation, consultez [Spécifier des planifications de synchronisation](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="87a43-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="87a43-108">Synchronisez un abonnement à la demande à partir des dossiers **Publications locales** et **Abonnements locaux** dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], et sous l’onglet **Tous les abonnements** du moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="87a43-108">Synchronize a subscription on demand from the **Local Publications** and **Local Subscriptions** folders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and the **All Subscriptions** tab in Replication Monitor.</span></span> <span data-ttu-id="87a43-109">Les abonnements aux publications Oracle ne peuvent pas être synchronisés à la demande à partir de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="87a43-109">Subscriptions to Oracle publications cannot be synchronized on demand from the Subscriber.</span></span> <span data-ttu-id="87a43-110">Pour plus d’informations sur le démarrage du Moniteur de réplication, consultez [Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="87a43-110">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-publisher"></a><span data-ttu-id="87a43-111">Pour synchroniser un abonnement par envoi de données à la demande dans Management Studio (sur le serveur de publication)</span><span class="sxs-lookup"><span data-stu-id="87a43-111">To synchronize a push subscription on demand in Management Studio (at the Publisher)</span></span>  
  
1.  <span data-ttu-id="87a43-112">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="87a43-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="87a43-113">Développez le dossier **Réplication** , puis développez le dossier **Publications locales** .</span><span class="sxs-lookup"><span data-stu-id="87a43-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="87a43-114">Développez la publication pour laquelle vous souhaitez synchroniser des abonnements.</span><span class="sxs-lookup"><span data-stu-id="87a43-114">Expand the publication for which you want to synchronize subscriptions.</span></span>  
  
4.  <span data-ttu-id="87a43-115">Cliquez avec le bouton droit sur l'abonnement à synchroniser, puis cliquez sur **Afficher l'état de synchronisation**.</span><span class="sxs-lookup"><span data-stu-id="87a43-115">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="87a43-116">Dans la boîte de dialogue **Afficher l'état de synchronisation - \<Subscriber>:\<SubscriptionDatabase>** cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="87a43-116">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="87a43-117">Lorsque la synchronisation est terminée, le message **Synchronisation terminée** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="87a43-117">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="87a43-118">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="87a43-118">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-subscriber"></a><span data-ttu-id="87a43-119">Pour synchroniser un abonnement par envoi de données à la demande dans Management Studio (sur l'Abonné)</span><span class="sxs-lookup"><span data-stu-id="87a43-119">To synchronize a push subscription on demand in Management Studio (at the Subscriber)</span></span>  
  
1.  <span data-ttu-id="87a43-120">Connectez-vous à l'Abonné dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="87a43-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="87a43-121">Développez le dossier **Réplication** , puis développez le dossier **Abonnements locaux** .</span><span class="sxs-lookup"><span data-stu-id="87a43-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="87a43-122">Cliquez avec le bouton droit sur l'abonnement à synchroniser, puis cliquez sur **Afficher l'état de synchronisation**.</span><span class="sxs-lookup"><span data-stu-id="87a43-122">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="87a43-123">Un message sur l'établissement d'une connexion avec le serveur de distribution s'affiche.</span><span class="sxs-lookup"><span data-stu-id="87a43-123">A message is displayed about establishing a connection to the Distributor.</span></span> <span data-ttu-id="87a43-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="87a43-124">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="87a43-125">Dans la boîte de dialogue **Afficher l'état de synchronisation – \<Subscriber>:\<SubscriptionDatabase>** cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="87a43-125">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="87a43-126">Lorsque la synchronisation est terminée, le message **Synchronisation terminée** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="87a43-126">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="87a43-127">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="87a43-127">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-replication-monitor"></a><span data-ttu-id="87a43-128">Pour synchroniser un abonnement par envoi de données à la demande dans le moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="87a43-128">To synchronize a push subscription on demand in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="87a43-129">Dans le moniteur de réplication, développez un groupe de serveurs de publication dans le volet gauche, développez un serveur de publication, puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="87a43-129">In Replication Monitor, expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="87a43-130">Cliquez sur l'onglet **Tous les abonnements** .</span><span class="sxs-lookup"><span data-stu-id="87a43-130">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="87a43-131">Cliquez avec le bouton droit sur l'abonnement que vous souhaitez synchroniser, puis cliquez sur **Démarrer la synchronisation**.</span><span class="sxs-lookup"><span data-stu-id="87a43-131">Right-click the subscription you want to synchronize, and then click **Start Synchronizing**.</span></span>  
  
4.  <span data-ttu-id="87a43-132">Pour afficher l'avancement de la synchronisation, cliquez avec le bouton droit sur l'abonnement, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="87a43-132">To view synchronization progress, right-click the subscription, and then click **View Details**.</span></span>  
  
##  <a name="using-replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="87a43-133">Utilisation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="87a43-133">Using Replication Agents</span></span>  
 <span data-ttu-id="87a43-134">Les abonnements par envoi de données (push) peuvent être synchronisés par le biais de la programmation et à la demande en appelant le fichier exécutable de l'Agent de réplication approprié à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="87a43-134">Push subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="87a43-135">Le fichier exécutable de l'Agent de réplication qui est appelé dépend du type de publication à laquelle l'abonnement par envoi de données (push) appartient.</span><span class="sxs-lookup"><span data-stu-id="87a43-135">The replication agent executable file that is invoked will depend on the type of publication to which the push subscription belongs.</span></span>  
  
#### <a name="to-start-the-distribution-agent-to-synchronize-a-push-subscription-to-a-transactional-publication"></a><span data-ttu-id="87a43-136">Pour démarrer l'Agent de distribution et synchroniser un abonnement par envoi de données (push) vers une publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="87a43-136">To start the Distribution Agent to synchronize a push subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="87a43-137">À partir de l'invite de commandes ou dans un fichier de commandes sur le serveur de distribution, exécutez **distrib.exe**.</span><span class="sxs-lookup"><span data-stu-id="87a43-137">From the command prompt or in a batch file at the Distributor, execute **distrib.exe**.</span></span> <span data-ttu-id="87a43-138">Spécifiez les arguments suivants sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="87a43-138">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="87a43-139">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="87a43-139">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="87a43-140">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="87a43-140">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="87a43-141">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="87a43-141">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="87a43-142">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="87a43-142">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="87a43-143">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="87a43-143">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="87a43-144">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="87a43-144">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="87a43-145">Si vous utilisez l'authentification SQL Server, vous devez également spécifier les arguments suivants :</span><span class="sxs-lookup"><span data-stu-id="87a43-145">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="87a43-146">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="87a43-146">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="87a43-147">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="87a43-147">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="87a43-148">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="87a43-148">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="87a43-149">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="87a43-149">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="87a43-150">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="87a43-150">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="87a43-151">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="87a43-151">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="87a43-152">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="87a43-152">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="87a43-153">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="87a43-153">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="87a43-154">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="87a43-154">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
#### <a name="to-start-the-merge-agent-to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="87a43-155">Pour démarrer l'Agent de fusion et synchroniser un abonnement par envoi de données (push) vers une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="87a43-155">To start the Merge Agent to synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="87a43-156">À partir de l'invite de commandes ou dans un fichier de commandes sur le serveur de distribution, exécutez **replmerg.exe**.</span><span class="sxs-lookup"><span data-stu-id="87a43-156">From the command prompt or in a batch file at the Distributor, execute **replmerg.exe**.</span></span> <span data-ttu-id="87a43-157">Spécifiez les arguments suivants sur la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="87a43-157">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="87a43-158">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="87a43-158">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="87a43-159">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="87a43-159">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="87a43-160">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="87a43-160">**-Publication**</span></span>  
  
    -   <span data-ttu-id="87a43-161">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="87a43-161">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="87a43-162">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="87a43-162">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="87a43-163">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="87a43-163">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="87a43-164">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="87a43-164">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="87a43-165">Si vous utilisez l'authentification SQL Server, vous devez également spécifier les arguments suivants :</span><span class="sxs-lookup"><span data-stu-id="87a43-165">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="87a43-166">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="87a43-166">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="87a43-167">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="87a43-167">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="87a43-168">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="87a43-168">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="87a43-169">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="87a43-169">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="87a43-170">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="87a43-170">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="87a43-171">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="87a43-171">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="87a43-172">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="87a43-172">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="87a43-173">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="87a43-173">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="87a43-174">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="87a43-174">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="87a43-175">Exemples (Agents de réplication)</span><span class="sxs-lookup"><span data-stu-id="87a43-175">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="87a43-176">L'exemple suivant démarre l'Agent de distribution pour synchroniser un abonnement par envoi de données (push).</span><span class="sxs-lookup"><span data-stu-id="87a43-176">The following example starts the Distribution Agent to synchronize a push subscription.</span></span>  
  
 
```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksProductsTran  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4
```
  
 <span data-ttu-id="87a43-177">L'exemple suivant démarre l'Agent de fusion pour synchroniser un abonnement par envoi de données (push).</span><span class="sxs-lookup"><span data-stu-id="87a43-177">The following example starts the Merge Agent to synchronize a push subscription.</span></span>  

```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksSalesOrdersMerge  
  
REM -- Start the Merge Agent.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher %Publisher%   
-Subscriber  %Subscriber%  -Distributor %Publisher% -PublisherDB  %PublicationDB%   
-SubscriberDB %SubscriptionDB% -Publication %Publication% -PublisherSecurityMode 1   
-OutputVerboseLevel 3  -Output -SubscriberSecurityMode 1  -SubscriptionType 0   
-DistributorSecurityMode 1
```
  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="87a43-178">Utilisation d'objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="87a43-178">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="87a43-179">Vous pouvez synchroniser des abonnements par envoi de données par programme à l'aide des objets RMO (Replication Management Objects) et gérer l'accès au code pour les fonctionnalités de l'Agent de réplication.</span><span class="sxs-lookup"><span data-stu-id="87a43-179">You can synchronize push subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="87a43-180">Les classes que vous utilisez pour créer un abonnement par envoi de données dépendent du type de publication à laquelle l'abonnement appartient.</span><span class="sxs-lookup"><span data-stu-id="87a43-180">The classes that you use to synchronize a push subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87a43-181">Si vous voulez démarrer une synchronisation qui s'exécute de façon autonome sans affecter votre application, démarrez l'agent en mode asynchrone.</span><span class="sxs-lookup"><span data-stu-id="87a43-181">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="87a43-182">Toutefois, si vous souhaitez contrôler la sortie de la synchronisation et recevoir les rappels de l'Agent pendant le processus de synchronisation (par exemple, pour afficher une barre de progression), vous devez démarrer l'Agent en mode synchrone.</span><span class="sxs-lookup"><span data-stu-id="87a43-182">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, if you want to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="87a43-183">Pour Abonnés [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] , vous devez démarrer l’agent en mode synchrone.</span><span class="sxs-lookup"><span data-stu-id="87a43-183">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="87a43-184">Pour synchroniser un abonnement par envoi de données vers un instantané ou une publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="87a43-184">To synchronize a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="87a43-185">Créez une connexion au serveur de distribution en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="87a43-185">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="87a43-186">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.TransSubscription> et définissez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="87a43-186">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class and set the following properties:</span></span>  
  
    -   <span data-ttu-id="87a43-187">Nom de la base de données de publication pour <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-187">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="87a43-188">Le nom de la publication à laquelle l'abonnement appartient pour <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-188">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="87a43-189">Nom de la base de données d'abonnements pour <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-189">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="87a43-190">Nom de l'abonné pour <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-190">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="87a43-191">La connexion créée à l'étape 1 pour <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-191">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="87a43-192">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> pour obtenir les propriétés d'abonnement restantes.</span><span class="sxs-lookup"><span data-stu-id="87a43-192">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="87a43-193">Si cette méthode retourne `false`, vérifiez que l'abonnement existe.</span><span class="sxs-lookup"><span data-stu-id="87a43-193">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="87a43-194">Démarrez l'Agent de distribution sur le serveur de distribution selon l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="87a43-194">Start the Distribution Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="87a43-195">Appelez la méthode <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> sur l'instance de <xref:Microsoft.SqlServer.Replication.TransSubscription> obtenue à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="87a43-195">Call the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransSubscription> from step 2.</span></span> <span data-ttu-id="87a43-196">Cette méthode démarre l'Agent de distribution en mode asynchrone et votre application récupère immédiatement le contrôle pendant l'exécution du travail de l'agent.</span><span class="sxs-lookup"><span data-stu-id="87a43-196">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="87a43-197">Vous ne pouvez pas appeler cette méthode si l'abonnement a été créé avec la valeur `false` pour <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-197">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="87a43-198">Obtenez une instance de la classe <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> à partir de la propriété <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> et appelez la méthode <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="87a43-198">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="87a43-199">Cette méthode démarre l'agent en mode synchrone, et le travail d'agent en cours d'exécution conserve le contrôle.</span><span class="sxs-lookup"><span data-stu-id="87a43-199">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="87a43-200">Lors de l'exécution synchrone, vous pouvez gérer l'événement <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> pendant l'exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="87a43-200">During synchronous execution you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="87a43-201">Pour synchroniser un abonnement par envoi de données vers une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="87a43-201">To synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="87a43-202">Créez une connexion au serveur de distribution en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="87a43-202">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="87a43-203">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.MergeSubscription> et définissez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="87a43-203">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="87a43-204">Nom de la base de données de publication pour <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-204">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="87a43-205">Le nom de la publication à laquelle l'abonnement appartient pour <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-205">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="87a43-206">Nom de la base de données d'abonnements pour <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-206">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="87a43-207">Nom de l'abonné pour <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-207">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="87a43-208">La connexion créée à l'étape 1 pour <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-208">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="87a43-209">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> pour obtenir les propriétés d'abonnement restantes.</span><span class="sxs-lookup"><span data-stu-id="87a43-209">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="87a43-210">Si cette méthode retourne `false`, vérifiez que l'abonnement existe.</span><span class="sxs-lookup"><span data-stu-id="87a43-210">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="87a43-211">Démarrez l'Agent de distribution sur le serveur de distribution selon l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="87a43-211">Start the Merge Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="87a43-212">Appelez la méthode <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> sur l'instance de <xref:Microsoft.SqlServer.Replication.MergeSubscription> obtenue à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="87a43-212">Call the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergeSubscription> from step 2.</span></span> <span data-ttu-id="87a43-213">Cette méthode démarre l'Agent de fusion en mode asynchrone et votre application récupère immédiatement le contrôle pendant l'exécution du travail de l'agent.</span><span class="sxs-lookup"><span data-stu-id="87a43-213">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="87a43-214">Vous ne pouvez pas appeler cette méthode si l'abonnement a été créé avec la valeur `false` pour <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a43-214">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="87a43-215">Obtenez une instance de la classe <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> à partir de la propriété <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> et appelez la méthode <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="87a43-215">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="87a43-216">Cette méthode démarre l'Agent de fusion en mode synchrone, et le travail d'agent en cours d'exécution conserve le contrôle.</span><span class="sxs-lookup"><span data-stu-id="87a43-216">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="87a43-217">Au cours de l'exécution synchrone, vous pouvez gérer l'événement <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> pendant que l'agent est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="87a43-217">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="87a43-218">Exemples (RMO)</span><span class="sxs-lookup"><span data-stu-id="87a43-218">Examples (RMO)</span></span>  
 <span data-ttu-id="87a43-219">Cet exemple synchronise un abonnement par envoi de données vers une publication transactionnelle, dans laquelle l'Agent est démarré en mode asynchrone à l'aide du travail de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="87a43-219">This example synchronizes a push subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub_withjob)]  
  
 <span data-ttu-id="87a43-220">Cet exemple synchronise un abonnement par envoi de données vers une publication transactionnelle, dans laquelle l'Agent est démarré en mode synchrone.</span><span class="sxs-lookup"><span data-stu-id="87a43-220">This example synchronizes a push subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub)]  
  
 <span data-ttu-id="87a43-221">Cet exemple synchronise un abonnement par envoi de données vers une publication de fusion, dans laquelle l'Agent est démarré en mode asynchrone à l'aide du travail de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="87a43-221">This example synchronizes a push subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub_withjob)]  
  
 <span data-ttu-id="87a43-222">Cet exemple synchronise un abonnement par envoi de données vers une publication de fusion, dans laquelle l'Agent est démarré en mode synchrone.</span><span class="sxs-lookup"><span data-stu-id="87a43-222">This example synchronizes a push subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="87a43-223">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="87a43-223">See Also</span></span>  
 <span data-ttu-id="87a43-224">[Concepts liés à RMO (Replication Management Objects)](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="87a43-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="87a43-225">[Synchroniser les données](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="87a43-225">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="87a43-226">Bonnes pratiques en matière de sécurité de la réplication</span><span class="sxs-lookup"><span data-stu-id="87a43-226">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
