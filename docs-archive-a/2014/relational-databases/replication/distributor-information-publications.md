---
title: Réplication SQL Server boîte de dialogue « informations sur le serveur de distribution » | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.Distributor.Publications.f1
- sql12.rep.monitor.Distributor.commonjobs..f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.merge.f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.snapshot.f1
- sql12.rep.monitor.Distributor.SubscriptionSummary.tran.f1
ms.assetid: 1f499277-7f12-42ba-8cf4-52b683434944
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ca0717a63c9660c225ec238e1e4d2423f7d01ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601371"
---
# <a name="distributor-information-dialog-box"></a><span data-ttu-id="3c253-102">Boîte de dialogue informations sur le serveur de distribution</span><span class="sxs-lookup"><span data-stu-id="3c253-102">Distributor Information Dialog Box</span></span> 
<span data-ttu-id="3c253-103">Cette rubrique fournit des informations sur la boîte de dialogue serveur de **distribution**</span><span class="sxs-lookup"><span data-stu-id="3c253-103">This topic provides information on the **Distributor** dialog box</span></span> 

## <a name="publications"></a><span data-ttu-id="3c253-104">Publications</span><span class="sxs-lookup"><span data-stu-id="3c253-104">Publications</span></span>

  <span data-ttu-id="3c253-105">L'onglet **Publications** fournit des informations résumées pour toutes les publications sur le serveur de distribution sélectionné dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="3c253-105">The **Publications** tab provides summary information for all publications at the Distributor that is selected in the left pane.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c253-106">Options</span><span class="sxs-lookup"><span data-stu-id="3c253-106">Options</span></span>  
 <span data-ttu-id="3c253-107">Les informations affichées relatives aux publications prises en charge par le serveur de distribution incluent une colonne qui contient l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-107">The information that is displayed about the publications supported by the Distributor includes a column that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span> <span data-ttu-id="3c253-108">Dans le cas contraire, les informations de publication sont les mêmes que les informations de publication fournies lorsque vous consultez des publications dans la vue Serveur de publication du Moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="3c253-108">Otherwise, the publication information is the same as the publication information that is provided when you view publications in the Publisher view of Replication Monitor.</span></span> <span data-ttu-id="3c253-109">Pour plus d'informations sur les colonnes de l'onglet **Publications** , consultez [Publisher Information, Publications](publisher-information-publications.md).</span><span class="sxs-lookup"><span data-stu-id="3c253-109">For more information about the columns in the **Publications** tab, see [Publisher Information, Publications](publisher-information-publications.md).</span></span>  

## <a name="subscription-watch-list"></a><span data-ttu-id="3c253-110">Liste de suivi des abonnements</span><span class="sxs-lookup"><span data-stu-id="3c253-110">Subscription watch list</span></span>

### <a name="transactional-replication"></a><span data-ttu-id="3c253-111">Réplication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="3c253-111">Transactional replication</span></span> 
  <span data-ttu-id="3c253-112">Les informations pour les abonnements transactionnels incluent le nom du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-112">Information for transactional subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="3c253-113">Dans le cas contraire, les fonctionnalités et les informations fournies dans cette boîte de dialogue sont les mêmes que celles de la vue Serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-113">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="3c253-114">Pour plus d’informations sur l’utilisation de cette boîte de dialogue, consultez [Informations sur le serveur de distribution, Liste de suivi des abonnements &#40;Publication transactionnelle, SQL Server 2005 et versions ultérieures&#41;](publisher-information-subscription-watch-list-transactional.md).</span><span class="sxs-lookup"><span data-stu-id="3c253-114">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Transactional Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-transactional.md).</span></span>  

### <a name="merge-replication"></a><span data-ttu-id="3c253-115">Réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="3c253-115">Merge replication</span></span>
  <span data-ttu-id="3c253-116">Les informations pour les abonnements de publication de fusion incluent le nom du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-116">Information for merge publication subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="3c253-117">Dans le cas contraire, les fonctionnalités et les informations fournies dans cette boîte de dialogue sont les mêmes que celles de la vue Serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-117">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="3c253-118">Pour plus d’informations sur l’utilisation de cette boîte de dialogue, consultez [Informations sur le serveur de publication, Liste de suivi des abonnements &#40;Publication de fusion, SQL Server 2005 et versions ultérieures&#41;](publisher-information-subscription-watch-list-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="3c253-118">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Merge Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-merge-publication.md).</span></span> 

### <a name="snapshot-replication"></a><span data-ttu-id="3c253-119">Réplication d'instantané</span><span class="sxs-lookup"><span data-stu-id="3c253-119">Snapshot replication</span></span>
  <span data-ttu-id="3c253-120">Les informations pour les abonnements de publication d'instantané incluent le nom du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-120">Information for snapshot publication subscriptions includes the name of the Publisher.</span></span> <span data-ttu-id="3c253-121">Dans le cas contraire, les fonctionnalités et les informations fournies dans cette boîte de dialogue sont les mêmes que celles de la vue Serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-121">Otherwise, the functionality and the information that is provided in this dialog box is the same as in the Publisher view.</span></span> <span data-ttu-id="3c253-122">Pour plus d’informations sur l’utilisation de cette boîte de dialogue, consultez [Informations sur le serveur de distribution, Liste de suivi des abonnements &#40;Publication d’instantané, SQL Server 2005 et versions ultérieures&#41;](publisher-information-subscription-watch-list-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="3c253-122">For more information about how to use this dialog box, see [Publisher Information, Subscription Watch List &#40;Snapshot Publication, SQL Server 2005 and Later&#41;](publisher-information-subscription-watch-list-snapshot.md).</span></span>  

## <a name="agents"></a><span data-ttu-id="3c253-123">Agents</span><span class="sxs-lookup"><span data-stu-id="3c253-123">Agents</span></span>
  <span data-ttu-id="3c253-124"> L’onglet **Agents** affiche des informations sur les agents et les travaux de maintenance associés au serveur de publication et à l’Abonné.</span><span class="sxs-lookup"><span data-stu-id="3c253-124">The **Agents** tab displays information about the agents and maintenance jobs that are associated with the Publisher and Subscriber.</span></span>  
  
 <span data-ttu-id="3c253-125">Les agents qui sont disponibles dans l'onglet **Agents** pour un serveur de distribution dans la vue Serveur de distribution incluent tous les agents qui sont disponibles dans l'onglet **Agents** pour un serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-125">The agents that are available in the **Agents** tab for a Distributor in Distributor view include all the agents that are available in the **Agents** tab for a Publisher.</span></span> <span data-ttu-id="3c253-126">Toutefois, l'onglet **Agents** pour un serveur de distribution dans la vue Serveur de distribution  inclut également un agent de distribution et un agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="3c253-126">However, the **Agents** tab for a Distributor in Distributor view also includes a Distributor Agent and a Merge Agent.</span></span>  
  
 <span data-ttu-id="3c253-127">Pour plus d'informations sur l'instantané, le lecteur de journal et les agents de lecture de file d'attente, et les travaux de maintenance, consultez [Publisher Information, Agents](publisher-information-agents.md).</span><span class="sxs-lookup"><span data-stu-id="3c253-127">For more information about the Snapshot, Log Reader, and Queue Reader agents, and maintenance jobs, see [Publisher Information, Agents](publisher-information-agents.md).</span></span> <span data-ttu-id="3c253-128">Remarquez que lorsque vous affichez les informations de l'agent sous l'onglet **Agents** pour un serveur de distribution, les informations du serveur de publication sont présentes pour les agents de lecture du journal et de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="3c253-128">Notice that when you are viewing agent information on the **Agents** tab for a Distributor, Publisher information is present for the Snapshot and Log Reader agents.</span></span> <span data-ttu-id="3c253-129">Toutefois, dans l'onglet **Agents** pour un serveur de distribution dans la vue Serveur de distribution, vous pouvez également sélectionner **Agent de distribution** et **Agent de fusion**.</span><span class="sxs-lookup"><span data-stu-id="3c253-129">However, in the **Agents** tab for a Distributor in Distributor view, you can also select **Distributor Agent** and **Merge Agent**.</span></span>  
  
### <a name="options"></a><span data-ttu-id="3c253-130">Options</span><span class="sxs-lookup"><span data-stu-id="3c253-130">Options</span></span>  
 <span data-ttu-id="3c253-131">Les sections suivantes décrivent les données qui sont affichées sous cet onglet pour l'agent de distribution et l'agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="3c253-131">The following sections describe the data that is displayed on this tab for the Distributor Agent and Merge Agent.</span></span>  
  
### <a name="distributor-agent"></a><span data-ttu-id="3c253-132">Agent de distribution</span><span class="sxs-lookup"><span data-stu-id="3c253-132">Distributor Agent</span></span>  
 <span data-ttu-id="3c253-133">**État**</span><span class="sxs-lookup"><span data-stu-id="3c253-133">**Status**</span></span>  
 <span data-ttu-id="3c253-134">État de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="3c253-134">The status of the agent.</span></span> <span data-ttu-id="3c253-135">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="3c253-135">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="3c253-136">Error</span><span class="sxs-lookup"><span data-stu-id="3c253-136">Error</span></span>    
-   <span data-ttu-id="3c253-137">Réessayer</span><span class="sxs-lookup"><span data-stu-id="3c253-137">Retry</span></span>    
-   <span data-ttu-id="3c253-138">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="3c253-138">Running</span></span>    
-   <span data-ttu-id="3c253-139">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="3c253-139">Not Running</span></span>    
-   <span data-ttu-id="3c253-140">Jamais démarré</span><span class="sxs-lookup"><span data-stu-id="3c253-140">Never started</span></span>  
  
 <span data-ttu-id="3c253-141">**Publisher**</span><span class="sxs-lookup"><span data-stu-id="3c253-141">**Publisher**</span></span>  
 <span data-ttu-id="3c253-142">Instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-142">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span>  
  
 <span data-ttu-id="3c253-143">**Publication**</span><span class="sxs-lookup"><span data-stu-id="3c253-143">**Publication**</span></span>  
 <span data-ttu-id="3c253-144">Nom de la publication à laquelle l'agent est associé.</span><span class="sxs-lookup"><span data-stu-id="3c253-144">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="3c253-145">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="3c253-145">**Subscription**</span></span>  
 <span data-ttu-id="3c253-146">Nom de l'abonnement, sous la forme : [*SubscriberName*].[*Database*].</span><span class="sxs-lookup"><span data-stu-id="3c253-146">The name of the subscription, in the form: [*SubscriberName*].[*Database*].</span></span>  
  
 <span data-ttu-id="3c253-147">**Type**</span><span class="sxs-lookup"><span data-stu-id="3c253-147">**Type**</span></span>  
 <span data-ttu-id="3c253-148">Type de réplication: émission, réception ou anonyme.</span><span class="sxs-lookup"><span data-stu-id="3c253-148">Type of replication: push, pull, or Anonymous.</span></span>  
  
 <span data-ttu-id="3c253-149">**Dernière heure de début**</span><span class="sxs-lookup"><span data-stu-id="3c253-149">**Last Start Time**</span></span>  
 <span data-ttu-id="3c253-150">Dernière heure à laquelle l'Agent a démarré.</span><span class="sxs-lookup"><span data-stu-id="3c253-150">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="3c253-151">**Durée**</span><span class="sxs-lookup"><span data-stu-id="3c253-151">**Duration**</span></span>  
 <span data-ttu-id="3c253-152">Durée pendant laquelle l'agent s'est exécuté.</span><span class="sxs-lookup"><span data-stu-id="3c253-152">The length of time that the agent has run.</span></span> <span data-ttu-id="3c253-153">Cette durée représente le temps actuel si l'agent est en cours d'exécution ou le temps total d'exécution s'il a été exécuté et s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="3c253-153">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="3c253-154">**Dernière action**</span><span class="sxs-lookup"><span data-stu-id="3c253-154">**Last Action**</span></span>  
 <span data-ttu-id="3c253-155">La dernière action effectuée au cours de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="3c253-155">The last action that was performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="3c253-156">**Vitesse de transmission**</span><span class="sxs-lookup"><span data-stu-id="3c253-156">**Delivery Rate**</span></span>  
 <span data-ttu-id="3c253-157">Vitesse, en commandes par seconde, à laquelle les commandes d'initialisation sont validées dans la base de données de distribution lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="3c253-157">The rate, in commands per second, at which initialization commands are committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="3c253-158">**Latence**</span><span class="sxs-lookup"><span data-stu-id="3c253-158">**Latency**</span></span>  
 <span data-ttu-id="3c253-159">Durée, en secondes, écoulée entre la modification la plus récente validée dans la base de données de publication et la commande correspondante validée dans la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="3c253-159">The time, in seconds, that has elapsed between the most recent change being committed in the publication database, and the corresponding command being committed in the distribution database.</span></span>  
  
 <span data-ttu-id="3c253-160">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="3c253-160">**#Trans**</span></span>  
 <span data-ttu-id="3c253-161">Nombre de transactions validées dans la base de données de distribution lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="3c253-161">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="3c253-162">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="3c253-162">**#Cmds**</span></span>  
 <span data-ttu-id="3c253-163">Nombre de commandes validées dans la base de données de distribution lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="3c253-163">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="3c253-164">Une commande est équivalente à une modification des données, par exemple une mise à jour.</span><span class="sxs-lookup"><span data-stu-id="3c253-164">A command is the same as a data change, such as an update.</span></span>  
  
 <span data-ttu-id="3c253-165">**Nb moy. de #Cmds**</span><span class="sxs-lookup"><span data-stu-id="3c253-165">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="3c253-166">Nombre moyen de commandes par transaction lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="3c253-166">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="merge-agent"></a><span data-ttu-id="3c253-167">Agent de fusion</span><span class="sxs-lookup"><span data-stu-id="3c253-167">Merge Agent</span></span>  
 <span data-ttu-id="3c253-168">**État**</span><span class="sxs-lookup"><span data-stu-id="3c253-168">**Status**</span></span>  
 <span data-ttu-id="3c253-169">État de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="3c253-169">The status of the agent.</span></span> <span data-ttu-id="3c253-170">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="3c253-170">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="3c253-171">Error</span><span class="sxs-lookup"><span data-stu-id="3c253-171">Error</span></span>    
-   <span data-ttu-id="3c253-172">Réessayer</span><span class="sxs-lookup"><span data-stu-id="3c253-172">Retry</span></span>    
-   <span data-ttu-id="3c253-173">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="3c253-173">Running</span></span>    
-   <span data-ttu-id="3c253-174">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="3c253-174">Not Running</span></span>    
-   <span data-ttu-id="3c253-175">Jamais démarré</span><span class="sxs-lookup"><span data-stu-id="3c253-175">Never started</span></span>  
  
 <span data-ttu-id="3c253-176">**Publisher**</span><span class="sxs-lookup"><span data-stu-id="3c253-176">**Publisher**</span></span>  
 <span data-ttu-id="3c253-177">Instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-177">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance of the Publisher.</span></span>  
  
 <span data-ttu-id="3c253-178">**Publication**</span><span class="sxs-lookup"><span data-stu-id="3c253-178">**Publication**</span></span>  
 <span data-ttu-id="3c253-179">Nom de la publication à laquelle l'agent est associé.</span><span class="sxs-lookup"><span data-stu-id="3c253-179">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="3c253-180">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="3c253-180">**Subscription**</span></span>  
 <span data-ttu-id="3c253-181">Nom de l'abonnement, sous la forme : [*SubscriberName*].[*Database*].</span><span class="sxs-lookup"><span data-stu-id="3c253-181">The name of the subscription, in the form: [*SubscriberName*].[*Database*].</span></span>  
  
 <span data-ttu-id="3c253-182">**Type**</span><span class="sxs-lookup"><span data-stu-id="3c253-182">**Type**</span></span>  
 <span data-ttu-id="3c253-183">Type de réplication: émission, réception ou anonyme.</span><span class="sxs-lookup"><span data-stu-id="3c253-183">Type of replication: push, pull, or Anonymous.</span></span>  
  
 <span data-ttu-id="3c253-184">**Dernière heure de début**</span><span class="sxs-lookup"><span data-stu-id="3c253-184">**Last Start Time**</span></span>  
 <span data-ttu-id="3c253-185">Dernière heure à laquelle l'Agent a démarré.</span><span class="sxs-lookup"><span data-stu-id="3c253-185">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="3c253-186">**Durée**</span><span class="sxs-lookup"><span data-stu-id="3c253-186">**Duration**</span></span>  
 <span data-ttu-id="3c253-187">Durée pendant laquelle l'agent s'est exécuté.</span><span class="sxs-lookup"><span data-stu-id="3c253-187">The length of time that the agent has run.</span></span> <span data-ttu-id="3c253-188">Cette durée représente le temps actuel si l'agent est en cours d'exécution ou le temps total d'exécution s'il a été exécuté et s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="3c253-188">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="3c253-189">**Dernière action**</span><span class="sxs-lookup"><span data-stu-id="3c253-189">**Last Action**</span></span>  
 <span data-ttu-id="3c253-190">La dernière action effectuée au cours de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="3c253-190">The last action that was performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="3c253-191">**Vitesse de transmission**</span><span class="sxs-lookup"><span data-stu-id="3c253-191">**Delivery Rate**</span></span>  
 <span data-ttu-id="3c253-192">Vitesse, en commandes par seconde, à laquelle les modifications sont validées dans la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="3c253-192">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="3c253-193">**Insertions du serveur de publication**</span><span class="sxs-lookup"><span data-stu-id="3c253-193">**Publisher Inserts**</span></span>  
 <span data-ttu-id="3c253-194">Nombre de commandes INSERT appliquées sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-194">Number of INSERT commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="3c253-195">**Mises à jour du serveur de publication**</span><span class="sxs-lookup"><span data-stu-id="3c253-195">**Publisher Updates**</span></span>  
 <span data-ttu-id="3c253-196">Nombre de commandes UPDATE appliquées sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-196">Number of UPDATE commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="3c253-197">**Suppressions du serveur de publication**</span><span class="sxs-lookup"><span data-stu-id="3c253-197">**Publisher Deletes**</span></span>  
 <span data-ttu-id="3c253-198">Nombre de commandes DELETE appliquées sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3c253-198">Number of DELETE commands applied at the Publisher.</span></span>  
  
 <span data-ttu-id="3c253-199">**Conflits du serveur de publication**</span><span class="sxs-lookup"><span data-stu-id="3c253-199">**Publisher Conflicts**</span></span>  
 <span data-ttu-id="3c253-200">Nombre de conflits sur le serveur de publication pendant le processus de fusion.</span><span class="sxs-lookup"><span data-stu-id="3c253-200">The number of conflicts occurring at the Publisher during the merge process.</span></span>  
  
 <span data-ttu-id="3c253-201">**Insertions de l'abonné**</span><span class="sxs-lookup"><span data-stu-id="3c253-201">**Subscriber Inserts**</span></span>  
 <span data-ttu-id="3c253-202">Nombre de commandes INSERT appliquées sur l'abonné.</span><span class="sxs-lookup"><span data-stu-id="3c253-202">Number of INSERT commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="3c253-203">**Mises à jour de l'abonné**</span><span class="sxs-lookup"><span data-stu-id="3c253-203">**Subscriber Updates**</span></span>  
 <span data-ttu-id="3c253-204">Nombre de commandes UPDATE appliquées sur l'abonné.</span><span class="sxs-lookup"><span data-stu-id="3c253-204">Number of UPDATE commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="3c253-205">**Suppressions de l'abonné**</span><span class="sxs-lookup"><span data-stu-id="3c253-205">**Subscriber Deletes**</span></span>  
 <span data-ttu-id="3c253-206">Nombre de commandes DELETE appliquées sur l'abonné.</span><span class="sxs-lookup"><span data-stu-id="3c253-206">Number of DELETE commands applied at the Subscriber.</span></span>  
  
 <span data-ttu-id="3c253-207">**Conflits de l'abonné**</span><span class="sxs-lookup"><span data-stu-id="3c253-207">**Subscriber Conflicts**</span></span>  
 <span data-ttu-id="3c253-208">Nombre de conflits sur l'abonné pendant le processus de fusion.</span><span class="sxs-lookup"><span data-stu-id="3c253-208">The number of conflicts occurring at the Subscriber during the merge process.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="3c253-209">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3c253-209">See Also</span></span>  
 <span data-ttu-id="3c253-210">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="3c253-210">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="3c253-211">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="3c253-211">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
