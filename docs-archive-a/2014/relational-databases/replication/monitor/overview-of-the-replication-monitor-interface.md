---
title: Présentation de l’interface du moniteur de réplication | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor
- Replication Monitor, about Replication Monitor
ms.assetid: 078f0e34-7153-45c4-8725-778b5bef88da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d9b7edbd76153f23168ec9bcf4a286d5f7cbe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603382"
---
# <a name="overview-of-the-replication-monitor-interface"></a><span data-ttu-id="fdfac-102">Présentation de l'interface du moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="fdfac-102">Overview of the Replication Monitor Interface</span></span>
  <span data-ttu-id="fdfac-103">Le Moniteur de réplication [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] présente une vue axée sur le serveur de publication ou le serveur de distribution de toute l’activité de réplication dans un format à deux volets.</span><span class="sxs-lookup"><span data-stu-id="fdfac-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor presents a Publisher-focused view or Distributor-focused view of all replication activity in a two pane format.</span></span> <span data-ttu-id="fdfac-104">Vous ajoutez un serveur de publication au moniteur dans le volet gauche tandis que dans le volet droit, le moniteur affiche des informations sur le serveur de publication, ses publications, les abonnements à ces publications ainsi que les divers agents de réplication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-104">You add a Publisher to the monitor in the left pane, and in the right pane the monitor displays information on the Publisher, its publications, the subscriptions to those publications, and the various replication agents.</span></span> <span data-ttu-id="fdfac-105">Outre la présentation des informations pour la topologie de réplication, le moniteur de réplication vous permet d'effectuer diverses tâches, telles que le démarrage et l'arrêt d'agents, ainsi que la validation des données.</span><span class="sxs-lookup"><span data-stu-id="fdfac-105">In addition to presenting information for the replication topology, Replication Monitor allows you to perform a number of tasks, such as starting and stopping agents, and validating data.</span></span>  
  
## <a name="viewing-information-for-the-entire-topology"></a><span data-ttu-id="fdfac-106">Affichage d'informations relatives à la topologie complète</span><span class="sxs-lookup"><span data-stu-id="fdfac-106">Viewing Information for the Entire Topology</span></span>  
 <span data-ttu-id="fdfac-107">Le volet gauche du Moniteur de réplication affiche</span><span class="sxs-lookup"><span data-stu-id="fdfac-107">The left pane of Replication Monitor displays</span></span>  
  
-   <span data-ttu-id="fdfac-108">Les groupes de serveurs de publication, les serveurs de publication et les publications.</span><span class="sxs-lookup"><span data-stu-id="fdfac-108">Publisher groups, Publishers, and publications.</span></span>  
  
-   <span data-ttu-id="fdfac-109">Les serveurs de distribution, les serveurs de publication et les publications.</span><span class="sxs-lookup"><span data-stu-id="fdfac-109">Distributors, Publishers, and publications.</span></span>  
  
 <span data-ttu-id="fdfac-110">Pour afficher des informations dans le moniteur de réplication, vous devez d'abord ajouter un serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-110">To view any information in Replication Monitor, you must first add a Publisher.</span></span> <span data-ttu-id="fdfac-111">Pour plus d’informations, consultez [Ajouter et supprimer des serveurs de publication à partir du moniteur de réplication](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="fdfac-111">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="fdfac-112">Le volet gauche vous aide à répondre aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfac-112">The left pane helps answer the following questions:</span></span>  
  
-   <span data-ttu-id="fdfac-113">L'intégrité de mon système de réplication est-elle de bonne qualité ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-113">Is my replication system healthy?</span></span>  
  
     <span data-ttu-id="fdfac-114">L'intégrité du système de réplication est relativement correcte si aucune icône d'erreur n'apparaît en regard des nœuds dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="fdfac-114">The replication system is relatively healthy if there are no error icons on nodes in the left pane.</span></span> <span data-ttu-id="fdfac-115">Pour avoir une vue plus complète de l'intégrité du système, vous devez également vérifier l'onglet **Liste de suivi des abonnements** qui affiche des informations sur les abonnements susceptibles de poser problème.</span><span class="sxs-lookup"><span data-stu-id="fdfac-115">To get a more complete view of system health, you should also check the **Subscription Watch List** tab, which displays information on subscriptions that might require attention.</span></span>  
  
-   <span data-ttu-id="fdfac-116">Pourquoi un Agent de fonctionne pas ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-116">Why is an agent not running?</span></span>  
  
     <span data-ttu-id="fdfac-117">Un agent ne s'exécute pas à un moment donné soit parce qu'il n'est pas programmé pour le faire, soit parce qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="fdfac-117">An agent is not running at a particular time either because it is not scheduled to run or because an error has occurred.</span></span> <span data-ttu-id="fdfac-118">Si une erreur s'est produite, une icône d'erreur s'affiche en regard des nœuds appropriés dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="fdfac-118">If an error has occurred, an error icon is displayed on the appropriate nodes in the left pane.</span></span> <span data-ttu-id="fdfac-119">Par exemple, si l'Agent d'instantané d'une publication s'est arrêté du fait d'une erreur, une icône d'erreur s'affiche en regard du nœud Groupe du serveur de publication, Publication et des nœuds de publication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-119">For example, if the Snapshot Agent for a publication stopped because of an error, an error icon is displayed on the Publisher group, Publisher, and publication nodes.</span></span> <span data-ttu-id="fdfac-120">Les informations de résumé concernant l'Agent d'instantané sont affichées sous l'onglet **Agents** de la publication ; pour obtenir les informations détaillées sur l'erreur, double-cliquez sur l'Agent d'instantané.</span><span class="sxs-lookup"><span data-stu-id="fdfac-120">Summary information for the Snapshot Agent is displayed on the **Agents** tab for the publication; double click the Snapshot Agent on this tab for detailed error information.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-distributors"></a><span data-ttu-id="fdfac-121">Affichage d'informations et réalisation de tâches associées aux serveurs de distribution</span><span class="sxs-lookup"><span data-stu-id="fdfac-121">Viewing Information and Performing Tasks Related to Distributors</span></span>  
 <span data-ttu-id="fdfac-122">Le moniteur de réplication présente des informations sur les serveurs de distribution dans trois onglets :</span><span class="sxs-lookup"><span data-stu-id="fdfac-122">Replication Monitor displays information about Distributors on three tabs:</span></span>  
  
-   <span data-ttu-id="fdfac-123">Onglet**Publications**</span><span class="sxs-lookup"><span data-stu-id="fdfac-123">**Publications** tab</span></span>  
  
     <span data-ttu-id="fdfac-124">Cet onglet fournit des informations de résumé pour toutes les publications d'un serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="fdfac-124">This tab provides summary information for all publications of a Distributor.</span></span>  
  
-   <span data-ttu-id="fdfac-125">Onglet**Liste de suivi des abonnements**</span><span class="sxs-lookup"><span data-stu-id="fdfac-125">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="fdfac-126">Cet onglet fournit des informations sur les abonnements pour le serveur de distribution sélectionné.</span><span class="sxs-lookup"><span data-stu-id="fdfac-126">This tab provides information about subscriptions for the selected Distributor.</span></span> <span data-ttu-id="fdfac-127">Vous pouvez filtrer la liste des abonnements pour identifier les erreurs, les avertissements et les abonnements qui ne fonctionnent pas correctement.</span><span class="sxs-lookup"><span data-stu-id="fdfac-127">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="fdfac-128">Cet onglet vous permet également d'effectuer les tâches suivantes : accéder aux propriétés d'abonnement, accéder aux informations détaillées sur l'agent ou les agents associés à un abonnement, réinitialiser des abonnements et valider des abonnements.</span><span class="sxs-lookup"><span data-stu-id="fdfac-128">The tab also lets you to perform the following tasks: access subscription properties, access detailed information about the agent or agents associated with a subscription, reinitialize subscriptions, and validate subscriptions.</span></span>  
  
     <span data-ttu-id="fdfac-129">L'onglet **Liste de suivi des abonnements** vous aide à répondre aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfac-129">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="fdfac-130">Quels sont les abonnements lents ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-130">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="fdfac-131">Définissez des options dans cet onglet pour que les abonnements soient présentés dans la grille dans l'ordre de leurs performances.</span><span class="sxs-lookup"><span data-stu-id="fdfac-131">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="fdfac-132">L'intégrité de mon système de réplication est-elle de bonne qualité ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-132">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="fdfac-133">La grille de cet onglet présente des icônes d'erreur et d'avertissement pour tous les abonnements qui nécessitent une attention particulière.</span><span class="sxs-lookup"><span data-stu-id="fdfac-133">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="fdfac-134">Cet onglet n'est pas disponible pour les serveurs de distribution qui exécutent des versions de [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] ou versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="fdfac-134">This tab is not available for Distributors that are running versions of [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span>  
  
-   <span data-ttu-id="fdfac-135">Onglet**Agents**</span><span class="sxs-lookup"><span data-stu-id="fdfac-135">**Agents** tab</span></span>  
  
     <span data-ttu-id="fdfac-136">Cet onglet affiche les informations détaillées sur les agents et les travaux utilisés par tous les types de réplication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-136">This tab displays detailed information about the agents and jobs that are used by all types of replication.</span></span> <span data-ttu-id="fdfac-137">L'onglet permet également de démarrer et d'arrêter chaque agent ou travail.</span><span class="sxs-lookup"><span data-stu-id="fdfac-137">The tab also let you start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="fdfac-138">Le moniteur de réplication fournit également un menu contextuel pour le nœud Serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="fdfac-138">Replication Monitor also provides a context menu for the Distributor node.</span></span> <span data-ttu-id="fdfac-139">Cliquez avec le bouton droit sur un serveur de distribution dans le volet gauche pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfac-139">Right-click a Distributor in the left pane to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="fdfac-140">Ajouter un serveur de publication au moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-140">Add a Publisher to Replication Monitor.</span></span>  
  
-   <span data-ttu-id="fdfac-141">Modifier les paramètres du moniteur de réplication pour le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-141">Edit Replication Monitor settings for the Distributor.</span></span>  
  
-   <span data-ttu-id="fdfac-142">Basculer dans la vue Groupe de serveurs de publication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-142">Switch to the Publisher Group view.</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publishers"></a><span data-ttu-id="fdfac-143">Affichage d'informations et réalisation de tâches associées aux serveurs de publication</span><span class="sxs-lookup"><span data-stu-id="fdfac-143">Viewing Information and Performing Tasks Related to Publishers</span></span>  
 <span data-ttu-id="fdfac-144">Le moniteur de réplication présente des informations sur les serveurs de publication dans trois onglets :</span><span class="sxs-lookup"><span data-stu-id="fdfac-144">Replication Monitor displays information about Publishers on three tabs:</span></span>  
  
-   <span data-ttu-id="fdfac-145">Onglet**Publications**</span><span class="sxs-lookup"><span data-stu-id="fdfac-145">**Publications** tab</span></span>  
  
     <span data-ttu-id="fdfac-146">Cet onglet fournit des informations de résumé pour toutes les publications sur un serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-146">This tab provides summary information for all publications at a Publisher.</span></span>  
  
-   <span data-ttu-id="fdfac-147">Onglet**Liste de suivi des abonnements**</span><span class="sxs-lookup"><span data-stu-id="fdfac-147">**Subscription Watch List** tab</span></span>  
  
     <span data-ttu-id="fdfac-148">Cet onglet affiche des informations sur les abonnements provenant de toutes les publications disponibles sur le serveur de publication sélectionné.</span><span class="sxs-lookup"><span data-stu-id="fdfac-148">This tab is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="fdfac-149">Vous pouvez filtrer la liste des abonnements pour identifier les erreurs, les avertissements et les abonnements qui ne fonctionnent pas correctement.</span><span class="sxs-lookup"><span data-stu-id="fdfac-149">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="fdfac-150">Cet onglet vous permet également de : accéder aux propriétés d'abonnement, accéder aux informations détaillées sur l'agent ou les agents associés à un abonnement, réinitialiser des abonnements et valider des abonnements.</span><span class="sxs-lookup"><span data-stu-id="fdfac-150">The tab also allows you to: access subscription properties; access detailed information about the agent or agents associated with a subscription; reinitialize subscriptions; and validate subscriptions.</span></span>  
  
     <span data-ttu-id="fdfac-151">L'onglet **Liste de suivi des abonnements** vous aide à répondre aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfac-151">The **Subscription Watch List** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="fdfac-152">Quels sont les abonnements lents ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-152">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="fdfac-153">Définissez des options dans cet onglet pour que les abonnements soient présentés dans la grille dans l'ordre de leurs performances.</span><span class="sxs-lookup"><span data-stu-id="fdfac-153">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="fdfac-154">L'intégrité de mon système de réplication est-elle de bonne qualité ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-154">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="fdfac-155">La grille de cet onglet présente des icônes d'erreur et d'avertissement pour tous les abonnements qui nécessitent une attention particulière.</span><span class="sxs-lookup"><span data-stu-id="fdfac-155">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
     <span data-ttu-id="fdfac-156">Cet onglet ne s'affiche pas pour les serveurs de distribution exécutant des versions antérieures à [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdfac-156">This tab is not displayed for Distributors running versions prior to [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="fdfac-157">Onglet**Agents**</span><span class="sxs-lookup"><span data-stu-id="fdfac-157">**Agents** tab</span></span>  
  
     <span data-ttu-id="fdfac-158">Cet onglet affiche les informations détaillées sur les agents et les travaux utilisés par tous les types de réplication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-158">This tab displays detailed information about the agents and jobs used by all types of replication.</span></span> <span data-ttu-id="fdfac-159">L'onglet permet également de démarrer et d'arrêter chaque agent ou travail.</span><span class="sxs-lookup"><span data-stu-id="fdfac-159">The tab also allows you to start and stop each agent and job.</span></span>  
  
 <span data-ttu-id="fdfac-160">Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="fdfac-160">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="fdfac-161">Le moniteur de réplication fournit également un menu contextuel pour le nœud Serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-161">Replication Monitor also provides a context menu for the Publisher node.</span></span> <span data-ttu-id="fdfac-162">Cliquez avec le bouton droit sur un serveur de publication dans le volet gauche pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfac-162">Right-click a Publisher in the left pane to:</span></span>  
  
-   <span data-ttu-id="fdfac-163">modifier les paramètres du moniteur de réplication pour le serveur de publication ;</span><span class="sxs-lookup"><span data-stu-id="fdfac-163">Edit Replication Monitor settings for the Publisher</span></span>  
  
-   <span data-ttu-id="fdfac-164">supprimer le serveur de publication du moniteur de réplication ;</span><span class="sxs-lookup"><span data-stu-id="fdfac-164">Remove the Publisher from Replication Monitor</span></span>  
  
-   <span data-ttu-id="fdfac-165">afficher et modifier des profils d'agents ;</span><span class="sxs-lookup"><span data-stu-id="fdfac-165">View and edit agent profiles</span></span>  
  
-   <span data-ttu-id="fdfac-166">vous connecter ou vous déconnecter du serveur de distribution qui stocke des informations sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-166">Connect to or disconnect from the Distributor that stores information about the Publisher</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-publications"></a><span data-ttu-id="fdfac-167">Affichage d'informations et réalisation de tâches associées aux publications</span><span class="sxs-lookup"><span data-stu-id="fdfac-167">Viewing Information and Performing Tasks Related to Publications</span></span>  
 <span data-ttu-id="fdfac-168">Le moniteur de réplication présente des informations sur les publications dans trois onglets ainsi que dans plusieurs fenêtres de détails :</span><span class="sxs-lookup"><span data-stu-id="fdfac-168">Replication Monitor displays information about publications on three tabs and a number of detail windows:</span></span>  
  
-   <span data-ttu-id="fdfac-169">Onglet**Tous les abonnements**</span><span class="sxs-lookup"><span data-stu-id="fdfac-169">**All Subscriptions** tab</span></span>  
  
     <span data-ttu-id="fdfac-170">Cet onglet montre des informations sur tous les abonnements à la publication sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fdfac-170">This tab displays information about all subscriptions to the selected publication.</span></span> <span data-ttu-id="fdfac-171">Par défaut, cet onglet est trié par ordre de priorité : erreurs, puis avertissements, ensuite dans l'ordre croissant des performances (les abonnements les moins performants étant tout en haut).</span><span class="sxs-lookup"><span data-stu-id="fdfac-171">By default, this tab is sorted in priority order: errors, then warnings, then in increasing order of performance, with any poorly performing subscriptions at the top.</span></span>  
  
     <span data-ttu-id="fdfac-172">L'onglet **Tous les abonnements** vous aide à répondre aux questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfac-172">The **All Subscriptions** tab helps answer the following questions:</span></span>  
  
    -   <span data-ttu-id="fdfac-173">Quels sont les abonnements lents ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-173">Which subscriptions are slow?</span></span>  
  
         <span data-ttu-id="fdfac-174">Définissez des options dans cet onglet pour que les abonnements soient présentés dans la grille dans l'ordre de leurs performances.</span><span class="sxs-lookup"><span data-stu-id="fdfac-174">Set options on this tab so that the grid displays subscriptions in order by their relative performance.</span></span>  
  
    -   <span data-ttu-id="fdfac-175">L'intégrité de mon système de réplication est-elle de bonne qualité ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-175">Is my replication system healthy?</span></span>  
  
         <span data-ttu-id="fdfac-176">La grille de cet onglet présente des icônes d'erreur et d'avertissement pour tous les abonnements qui nécessitent une attention particulière.</span><span class="sxs-lookup"><span data-stu-id="fdfac-176">The grid on this tab displays error and warning icons for any subscriptions that require your attention.</span></span>  
  
-   <span data-ttu-id="fdfac-177">Onglet**Agents**</span><span class="sxs-lookup"><span data-stu-id="fdfac-177">**Agents** tab</span></span>  
  
     <span data-ttu-id="fdfac-178">Cet onglet affiche des informations sur les agents utilisés par la réplication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-178">This tab displays information about the agents that are used by replication.</span></span> <span data-ttu-id="fdfac-179">Cet onglet affiche des informations sur les agents suivants :</span><span class="sxs-lookup"><span data-stu-id="fdfac-179">This tab displays information about the following agents:</span></span>  
  
    -   <span data-ttu-id="fdfac-180">Agent d'instantané, utilisé par toutes les publications</span><span class="sxs-lookup"><span data-stu-id="fdfac-180">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="fdfac-181">Agent de lecture du journal, utilisé par toutes les publications transactionnelles</span><span class="sxs-lookup"><span data-stu-id="fdfac-181">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="fdfac-182">Agent de lecture de la file d'attente, utilisé par les publications transactionnelles qui possèdent des abonnements mis à jour en attente</span><span class="sxs-lookup"><span data-stu-id="fdfac-182">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="fdfac-183">L'onglet permet aussi d'effectuer les tâches suivantes : accéder aux informations détaillées à propos de chaque agent, et démarrer ou arrêter chaque agent.</span><span class="sxs-lookup"><span data-stu-id="fdfac-183">The tab also allows for you to perform the following tasks: access detailed information about each agent, and start and stop each agent.</span></span> <span data-ttu-id="fdfac-184">Pour plus d'informations sur les agents associés aux abonnements (l'Agent de distribution et l'Agent de fusion), consultez la section « Affichage d'informations et réalisation de tâches associées aux abonnements » dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="fdfac-184">For information about agents that are associated with subscriptions (the Distribution Agent and Merge Agent), see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
-   <span data-ttu-id="fdfac-185">Onglets**Avertissements**</span><span class="sxs-lookup"><span data-stu-id="fdfac-185">**Warnings** tab</span></span>  
  
     <span data-ttu-id="fdfac-186">Cet onglet permet de spécifier des avertissements et des alertes pour les agents.</span><span class="sxs-lookup"><span data-stu-id="fdfac-186">This tab enables you to specify warnings and alerts for agents.</span></span> <span data-ttu-id="fdfac-187">Pour plus d’informations, voir [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="fdfac-187">For more information, see [Set Thresholds and Warnings in Replication Monitor](set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="fdfac-188">Onglet**Jetons de suivi** (réplication transactionnelle uniquement)</span><span class="sxs-lookup"><span data-stu-id="fdfac-188">**Tracer Tokens** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="fdfac-189">Cet onglet permet de mesurer la latence, à savoir le temps écoulé entre la validation d'une transaction sur le serveur de publication et la validation de la transaction correspondante sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="fdfac-189">This tab allows you to measure latency, the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="fdfac-190">Cet onglet vous aide à répondre à la question suivante :</span><span class="sxs-lookup"><span data-stu-id="fdfac-190">This tab helps answers the following question:</span></span>  
  
    -   <span data-ttu-id="fdfac-191">Combien de temps mettra une transaction validée maintenant pour atteindre un Abonné avec la réplication transactionnelle ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-191">How long will it take a transaction committed now to reach a Subscriber in transactional replication?</span></span>  
  
         <span data-ttu-id="fdfac-192">Affichez le temps total que met une transaction pour se déplacer dans le système et comparez-le aux temps précédents.</span><span class="sxs-lookup"><span data-stu-id="fdfac-192">View the total time for a transaction to travel through the system and also compare it to previous times.</span></span>  
  
     <span data-ttu-id="fdfac-193">Cet onglet ne s'affiche pas pour les serveurs de distribution exécutant [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] ou des versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="fdfac-193">This tab is not displayed for Distributors running [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or earlier.</span></span> <span data-ttu-id="fdfac-194">Pour plus d’informations sur les jetons de suivi, consultez [Mesurer la latence et valider les connexions pour la réplication transactionnelle](measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="fdfac-194">For more information on tracer tokens, see [Measure Latency and Validate Connections for Transactional Replication](measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="fdfac-195">les fenêtres de détails concernant les agents associés à une publication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-195">Detail windows for the agents associated with a publication.</span></span> <span data-ttu-id="fdfac-196">Les agents suivants sont associés aux publications :</span><span class="sxs-lookup"><span data-stu-id="fdfac-196">The following agents are associated with publications:</span></span>  
  
    -   <span data-ttu-id="fdfac-197">Agent d'instantané, utilisé par toutes les publications</span><span class="sxs-lookup"><span data-stu-id="fdfac-197">The Snapshot Agent, which is used by all publications.</span></span>  
  
    -   <span data-ttu-id="fdfac-198">Agent de lecture du journal, utilisé par toutes les publications transactionnelles</span><span class="sxs-lookup"><span data-stu-id="fdfac-198">The Log Reader Agent, which is used by all transactional publications.</span></span>  
  
    -   <span data-ttu-id="fdfac-199">Agent de lecture de la file d'attente, utilisé par les publications transactionnelles qui possèdent des abonnements mis à jour en attente</span><span class="sxs-lookup"><span data-stu-id="fdfac-199">The Queue Reader Agent, which is used by transactional publications enabled for queued updating subscriptions.</span></span>  
  
     <span data-ttu-id="fdfac-200">Dans le moniteur de réplication, double-cliquez sur un agent pour accéder aux informations dans une fenêtre de détails.</span><span class="sxs-lookup"><span data-stu-id="fdfac-200">Double-click an agent in Replication Monitor to access information in a detail window.</span></span> <span data-ttu-id="fdfac-201">En plus des agents répertoriés ci-dessus, il existe des agents associés aux abonnements : l'agent de distribution pour les abonnements à l'instantané et aux publications transactionnelles et l'agent de fusion pour les abonnements à des publications de fusion.</span><span class="sxs-lookup"><span data-stu-id="fdfac-201">In addition to the agents listed above, there are agents associated with subscriptions: the Distribution Agent for subscriptions to snapshot and transactional publications; and the Merge Agent for subscriptions to merge publications.</span></span> <span data-ttu-id="fdfac-202">Pour plus d'informations, consultez la section « Affichage d'informations et réalisation de tâches associées aux abonnements » dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="fdfac-202">For more information, see the section "Viewing Information and Performing Tasks Related to Subscriptions" in this topic.</span></span>  
  
     <span data-ttu-id="fdfac-203">Les fenêtres de détails des agents fournissent des informations sur les sessions des agents, notamment l'heure de début, l'heure de fin, la durée et les opérations effectuées dans une session.</span><span class="sxs-lookup"><span data-stu-id="fdfac-203">The agent detail windows provide information about agent sessions, including start time, end time, duration, and the actions performed in a session.</span></span> <span data-ttu-id="fdfac-204">Elles vous aident à répondre à la question suivante :</span><span class="sxs-lookup"><span data-stu-id="fdfac-204">They help to answer the following question:</span></span>  
  
    -   <span data-ttu-id="fdfac-205">Pourquoi un Agent de fonctionne pas ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-205">Why is an agent not running?</span></span>  
  
         <span data-ttu-id="fdfac-206">Les messages d'erreur disponibles fournissent des informations détaillées sur la raison de la non-exécution d'un agent et constituent un point de départ à la résolution des problèmes liés aux agents associés à une publication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-206">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a publication.</span></span>  
  
 <span data-ttu-id="fdfac-207">Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="fdfac-207">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="fdfac-208">Le moniteur de réplication fournit également un menu contextuel pour le nœud de publications.</span><span class="sxs-lookup"><span data-stu-id="fdfac-208">Replication Monitor also provides a context menu for the publications node.</span></span> <span data-ttu-id="fdfac-209">Cliquez avec le bouton droit sur un serveur de publication dans le volet gauche pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfac-209">Right-click a publication in the left pane to:</span></span>  
  
-   <span data-ttu-id="fdfac-210">réinitialiser tous les abonnements à une publication ;</span><span class="sxs-lookup"><span data-stu-id="fdfac-210">Reinitialize all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="fdfac-211">valider tous les abonnements à une publication ;</span><span class="sxs-lookup"><span data-stu-id="fdfac-211">Validate all subscriptions to a publication</span></span>  
  
-   <span data-ttu-id="fdfac-212">générer un instantané pour une publication ;</span><span class="sxs-lookup"><span data-stu-id="fdfac-212">Generate a snapshot for a publication</span></span>  
  
-   <span data-ttu-id="fdfac-213">afficher et modifier les propriétés d'une publication.</span><span class="sxs-lookup"><span data-stu-id="fdfac-213">View and edit publication properties</span></span>  
  
## <a name="viewing-information-and-performing-tasks-related-to-subscriptions"></a><span data-ttu-id="fdfac-214">Affichage d'informations et réalisation de tâches associées aux abonnements</span><span class="sxs-lookup"><span data-stu-id="fdfac-214">Viewing Information and Performing Tasks Related to Subscriptions</span></span>  
 <span data-ttu-id="fdfac-215">Le moniteur de réplication présente des informations sur les abonnements dans plusieurs onglets.</span><span class="sxs-lookup"><span data-stu-id="fdfac-215">Replication Monitor displays information about subscriptions on a number of different tabs.</span></span> <span data-ttu-id="fdfac-216">Dans le moniteur de réplication, double-cliquez sur un abonnement pour accéder à ces onglets dans une fenêtre de détails.</span><span class="sxs-lookup"><span data-stu-id="fdfac-216">Double-click a subscription in Replication Monitor to access these tabs in a detail window.</span></span> <span data-ttu-id="fdfac-217">Tous les onglets sont utiles pour répondre à la question « Pourquoi un agent ne s'exécute-t-il pas ? »</span><span class="sxs-lookup"><span data-stu-id="fdfac-217">All of the tabs are useful in answering the question "Why is an agent not running?"</span></span> <span data-ttu-id="fdfac-218">Les messages d'erreur disponibles fournissent des informations détaillées sur la raison de la non-exécution d'un agent et constituent un point de départ à la résolution des problèmes liés aux agents associés à un abonnement.</span><span class="sxs-lookup"><span data-stu-id="fdfac-218">The error messages available provide detailed information on why an agent is not running and provide a starting point for troubleshooting issues with the agents associated with a subscription.</span></span>  
  
-   <span data-ttu-id="fdfac-219">**Tous les abonnements** et **Liste de suivi des abonnements**</span><span class="sxs-lookup"><span data-stu-id="fdfac-219">**All Subscriptions tab** and **Subscription Watch List tab.**</span></span>  
  
     <span data-ttu-id="fdfac-220">Ces onglets sont décrits plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="fdfac-220">These tabs are described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="fdfac-221">Onglet**Historique du serveur de publication vers le serveur de distribution** (réplication transactionnelle uniquement)</span><span class="sxs-lookup"><span data-stu-id="fdfac-221">**Publisher to Distributor History** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="fdfac-222">Cet onglet présente des informations sur l'Agent de lecture du journal pour une publication (identique à la fenêtre de détails de l'Agent de lecture du journal).</span><span class="sxs-lookup"><span data-stu-id="fdfac-222">This tab displays information on the Log Reader Agent for a publication (the tab is identical to the Log Reader Agent details window).</span></span>  
  
-   <span data-ttu-id="fdfac-223">Onglet**Historique du serveur de distribution vers l'Abonné** (réplication d'instantané et réplication transactionnelle)</span><span class="sxs-lookup"><span data-stu-id="fdfac-223">**Distributor to Subscriber History** tab (snapshot replication and transactional replication)</span></span>  
  
     <span data-ttu-id="fdfac-224">Cet onglet présente des informations sur l'Agent de distribution pour un abonnement.</span><span class="sxs-lookup"><span data-stu-id="fdfac-224">This tab displays information on the Distribution Agent for a subscription.</span></span>  
  
-   <span data-ttu-id="fdfac-225">Onglet**Commandes non distribuées** (réplication transactionnelle uniquement)</span><span class="sxs-lookup"><span data-stu-id="fdfac-225">**Undistributed Commands** tab (transactional replication only)</span></span>  
  
     <span data-ttu-id="fdfac-226">Cet onglet présente des informations sur le nombre de commandes de la base de données de distribution qui n'ont pas été remises à l'Abonné sélectionné, ainsi que le temps estimé de remise de ces commandes.</span><span class="sxs-lookup"><span data-stu-id="fdfac-226">This tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="fdfac-227">Cet onglet vous aide à répondre à la question « Quel est le retard de mon abonnement ? »</span><span class="sxs-lookup"><span data-stu-id="fdfac-227">The tab helps answer the question, "How far behind is my subscription?"</span></span> <span data-ttu-id="fdfac-228">Cet onglet ne s'affiche pas pour les serveurs de distribution exécutant des versions antérieures à SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="fdfac-228">This tab is not displayed for Distributors running versions prior to SQL Server 2005.</span></span>  
  
-   <span data-ttu-id="fdfac-229">Onglet**Historique de synchronisation** (réplication de fusion uniquement)</span><span class="sxs-lookup"><span data-stu-id="fdfac-229">**Synchronization History** tab (merge replication only)</span></span>  
  
     <span data-ttu-id="fdfac-230">Cet onglet présente des informations sur l'Agent de fusion pour un abonnement.</span><span class="sxs-lookup"><span data-stu-id="fdfac-230">This tab displays information on the Merge Agent for a subscription.</span></span> <span data-ttu-id="fdfac-231">Il vous aide à répondre à la question suivante :</span><span class="sxs-lookup"><span data-stu-id="fdfac-231">This tab helps answer the following question:</span></span>  
  
    -   <span data-ttu-id="fdfac-232">Pourquoi mon abonnement de fusion est-il lent ?</span><span class="sxs-lookup"><span data-stu-id="fdfac-232">Why is my merge subscription slow?</span></span>  
  
         <span data-ttu-id="fdfac-233">Cet onglet fournit des statistiques détaillées sur chaque article traité pendant la synchronisation, notamment la durée de chaque phase de traitement (téléchargement des modifications amont/aval, etc.).</span><span class="sxs-lookup"><span data-stu-id="fdfac-233">This tab provides detailed statistics for each article processed during synchronization, including the amount of time spent in each processing phase (uploading changes, downloading changes, and so on).</span></span> <span data-ttu-id="fdfac-234">Il permet d'identifier les tables qui provoquent des ralentissements et il est l'emplacement idéal pour résoudre les problèmes de performances posés par les abonnements de fusion.</span><span class="sxs-lookup"><span data-stu-id="fdfac-234">It can help pinpoint specific tables that are causing slowdowns and is the best place to troubleshoot performance issues with merge subscriptions.</span></span>  
  
 <span data-ttu-id="fdfac-235">Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="fdfac-235">For more information, see [View Information and Perform Tasks using Replication Monitor](view-information-and-perform-tasks-replication-monitor.md).</span></span>
  
## <a name="viewing-information-and-performing-tasks-related-to-agent-profiles"></a><span data-ttu-id="fdfac-236">Affichage d'informations et réalisation de tâches associées aux profils d'agents</span><span class="sxs-lookup"><span data-stu-id="fdfac-236">Viewing Information and Performing Tasks Related to Agent Profiles</span></span>  
 <span data-ttu-id="fdfac-237">Le moniteur de réplication inclut plusieurs boîtes de dialogue permettant de gérer les profils d'agents.</span><span class="sxs-lookup"><span data-stu-id="fdfac-237">Replication Monitor includes a number of dialog boxes for managing agent profiles.</span></span> <span data-ttu-id="fdfac-238">Les profils d'agents sont des ensembles de paramètres qui déterminent le comportement des agents.</span><span class="sxs-lookup"><span data-stu-id="fdfac-238">Agent profiles are sets of parameters for an agent that determine agent behavior.</span></span> <span data-ttu-id="fdfac-239">Pour plus d'informations, voir [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="fdfac-239">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span> <span data-ttu-id="fdfac-240">Les boîtes de dialogue sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdfac-240">The dialog boxes are:</span></span>  
  
-   <span data-ttu-id="fdfac-241">**Profils de l’Agent**</span><span class="sxs-lookup"><span data-stu-id="fdfac-241">**Agent Profiles**</span></span>  
  
     <span data-ttu-id="fdfac-242">Cette boîte de dialogue vous permet de : modifier les propriétés des profils, créer et supprimer des profils, spécifier un profil par défaut et spécifier que tous les agents d'un type donné (tels les Agents d'instantané) doivent utiliser un profil donné.</span><span class="sxs-lookup"><span data-stu-id="fdfac-242">This dialog box allows you to: change the properties of profiles; create and delete profiles; specify a default profile; and specify that all agents of a specific type (such as Snapshot Agents) should use a given profile.</span></span>  
  
-   <span data-ttu-id="fdfac-243">**\<AgentProfileName> Propriétés**</span><span class="sxs-lookup"><span data-stu-id="fdfac-243">**\<AgentProfileName> Properties**</span></span>  
  
     <span data-ttu-id="fdfac-244">Cette boîte de dialogue vous permet d'afficher et de modifier les paramètres d'un profil.</span><span class="sxs-lookup"><span data-stu-id="fdfac-244">This dialog box allows you to view and edit the parameter settings in a profile.</span></span>  
  
-   <span data-ttu-id="fdfac-245">**Nouveau profil de l'Agent**</span><span class="sxs-lookup"><span data-stu-id="fdfac-245">**New Agent Profile**</span></span>  
  
     <span data-ttu-id="fdfac-246">Cette boîte de dialogue vous permet de créer un profil incluant en option les valeurs d'un profil existant.</span><span class="sxs-lookup"><span data-stu-id="fdfac-246">This dialog box allows you to create a new profile, optionally including the values from an existing profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfac-247">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fdfac-247">See Also</span></span>  
 [<span data-ttu-id="fdfac-248">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="fdfac-248">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
