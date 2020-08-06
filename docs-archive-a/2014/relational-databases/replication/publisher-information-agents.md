---
title: Informations sur le serveur de publication, Agents | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.commonjobs.f1
ms.assetid: 2346c00d-c269-45a1-af14-68e7fd7ebd7e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bdd2055ed022257524bc4d2784bdc333537be855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600782"
---
# <a name="publisher-information-agents"></a><span data-ttu-id="70dde-102">Informations sur le serveur de publication, Agents</span><span class="sxs-lookup"><span data-stu-id="70dde-102">Publisher Information, Agents</span></span>
  <span data-ttu-id="70dde-103">L'onglet **Agents** affiche des informations sur les agents et les travaux de maintenance associés au serveur de publication :</span><span class="sxs-lookup"><span data-stu-id="70dde-103">The **Agents** tab displays information about the agents and maintenance jobs that are associated with the Publisher:</span></span>  
  
-   <span data-ttu-id="70dde-104">Agent d'instantané, affiché pour toutes les publications</span><span class="sxs-lookup"><span data-stu-id="70dde-104">Snapshot Agent, which is displayed for all publications.</span></span>  
  
-   <span data-ttu-id="70dde-105">Agent de lecture du journal, affiché pour toutes les publications transactionnelles</span><span class="sxs-lookup"><span data-stu-id="70dde-105">Log Reader Agent, which is displayed for all transactional publications.</span></span>  
  
-   <span data-ttu-id="70dde-106">Agent de lecture de la file d'attente, affiché pour les publications transactionnelles qui ont des abonnements mis à jour en file d'attente</span><span class="sxs-lookup"><span data-stu-id="70dde-106">Queue Reader Agent, which is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="70dde-107">Travaux de maintenance, affichés pour toutes les publications :</span><span class="sxs-lookup"><span data-stu-id="70dde-107">Maintenance jobs, displayed for all publications:</span></span>  
  
    -   <span data-ttu-id="70dde-108">Réinitialiser les abonnements présentant des erreurs lors la validation de données</span><span class="sxs-lookup"><span data-stu-id="70dde-108">Reinitialize subscriptions that have data validation failures</span></span>  
  
    -   <span data-ttu-id="70dde-109">Nettoyage de l'historique de l'Agent : distribution</span><span class="sxs-lookup"><span data-stu-id="70dde-109">Agent history cleanup: distribution</span></span>  
  
    -   <span data-ttu-id="70dde-110">Actualisateur d'analyse de réplication pour la distribution</span><span class="sxs-lookup"><span data-stu-id="70dde-110">Replication monitoring refresher for distribution</span></span>  
  
    -   <span data-ttu-id="70dde-111">Contrôle des agents de réplication</span><span class="sxs-lookup"><span data-stu-id="70dde-111">Replication agents checkup</span></span>  
  
    -   <span data-ttu-id="70dde-112">Nettoyage de distribution : distribution</span><span class="sxs-lookup"><span data-stu-id="70dde-112">Distribution cleanup: distribution</span></span>  
  
    -   <span data-ttu-id="70dde-113">Nettoyage de l'abonnement expiré</span><span class="sxs-lookup"><span data-stu-id="70dde-113">Expired subscription cleanup</span></span>  
  
 <span data-ttu-id="70dde-114">Pour plus d’informations sur ces travaux, consultez [Administration de l’Agent de réplication](agents/replication-agent-administration.md).</span><span class="sxs-lookup"><span data-stu-id="70dde-114">For more information about these jobs, see [Replication Agent Administration](agents/replication-agent-administration.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="70dde-115">Options</span><span class="sxs-lookup"><span data-stu-id="70dde-115">Options</span></span>  
 <span data-ttu-id="70dde-116">Pour afficher des informations sur un agent ou un travail, sélectionnez l'option de votre choix dans le menu déroulant **Types d'agents et de travaux** .</span><span class="sxs-lookup"><span data-stu-id="70dde-116">To display information about an agent or job, select from the **Agent and Job Types** drop-down menu.</span></span> <span data-ttu-id="70dde-117">Pour des informations plus détaillées et obtenir des tâches en relation avec un Agent ou un travail, cliquez avec le bouton droit sur la ligne correspondant à cet Agent ou à ce travail, puis cliquez sur une option dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="70dde-117">For more detailed information and tasks that are related to an agent or job, right-click the row for that agent or job, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="70dde-118">Pour modifier la façon dont la grille affiche les données, cliquez avec le bouton droit sur la grille, puis cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="70dde-118">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="70dde-119">**Trier**: cette option vous permet d'effectuer un tri sur ou plusieurs colonnes dans la boîte de dialogue **Trier les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="70dde-119">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="70dde-120">**Choisir les colonnes à afficher**: cette option vous permet de sélectionner les colonnes à afficher et l'ordre d'affichage dans la boîte de dialogue **Choisir les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="70dde-120">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="70dde-121">**Filtre**: cette option vous permet de filtrer les lignes dans la grille selon les valeurs de colonne dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="70dde-121">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="70dde-122">**Effacer le filtre**: cette option vous permet d'effacer tous les paramètres du filtre pour la grille.</span><span class="sxs-lookup"><span data-stu-id="70dde-122">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="70dde-123">Les paramètres du filtre sont spécifiques à chaque grille.</span><span class="sxs-lookup"><span data-stu-id="70dde-123">Filter settings are specific to each grid.</span></span> <span data-ttu-id="70dde-124">La sélection et le tri des colonnes sont appliqués à toutes les grilles du même type, par exemple la grille de publications pour chaque serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="70dde-124">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="70dde-125">Les sections suivantes décrivent les données qui sont affichées sous cet onglet pour chaque agent ou travail.</span><span class="sxs-lookup"><span data-stu-id="70dde-125">The following sections describe the data that is displayed on this tab for each agent or job.</span></span>  
  
### <a name="snapshot-agent"></a><span data-ttu-id="70dde-126">Agent d'instantané</span><span class="sxs-lookup"><span data-stu-id="70dde-126">Snapshot Agent</span></span>  
 <span data-ttu-id="70dde-127">**État**</span><span class="sxs-lookup"><span data-stu-id="70dde-127">**Status**</span></span>  
 <span data-ttu-id="70dde-128">État de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-128">The status of the agent.</span></span> <span data-ttu-id="70dde-129">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="70dde-129">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="70dde-130">Error</span><span class="sxs-lookup"><span data-stu-id="70dde-130">Error</span></span>  
  
-   <span data-ttu-id="70dde-131">Recommencer</span><span class="sxs-lookup"><span data-stu-id="70dde-131">Retry</span></span>  
  
-   <span data-ttu-id="70dde-132">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="70dde-132">Running</span></span>  
  
-   <span data-ttu-id="70dde-133">Completed</span><span class="sxs-lookup"><span data-stu-id="70dde-133">Completed</span></span>  
  
 <span data-ttu-id="70dde-134">**Publication**</span><span class="sxs-lookup"><span data-stu-id="70dde-134">**Publication**</span></span>  
 <span data-ttu-id="70dde-135">Nom de la publication à laquelle l'agent est associé.</span><span class="sxs-lookup"><span data-stu-id="70dde-135">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="70dde-136">**Dernière heure de début**</span><span class="sxs-lookup"><span data-stu-id="70dde-136">**Last Start Time**</span></span>  
 <span data-ttu-id="70dde-137">Dernière heure à laquelle l'Agent a démarré.</span><span class="sxs-lookup"><span data-stu-id="70dde-137">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="70dde-138">**Durée**</span><span class="sxs-lookup"><span data-stu-id="70dde-138">**Duration**</span></span>  
 <span data-ttu-id="70dde-139">Durée pendant laquelle l'agent s'est exécuté.</span><span class="sxs-lookup"><span data-stu-id="70dde-139">The length of time the agent has run.</span></span> <span data-ttu-id="70dde-140">Cette durée représente le temps actuel si l'agent est en cours d'exécution ou le temps total d'exécution s'il a été exécuté et s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="70dde-140">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="70dde-141">**Dernière action**</span><span class="sxs-lookup"><span data-stu-id="70dde-141">**Last Action**</span></span>  
 <span data-ttu-id="70dde-142">La dernière action effectuée au cours de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-142">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="70dde-143">**Vitesse de transmission**</span><span class="sxs-lookup"><span data-stu-id="70dde-143">**Delivery Rate**</span></span>  
 <span data-ttu-id="70dde-144">Vitesse, en commandes par seconde, à laquelle les commandes d'initialisation sont validées dans la base de données de distribution lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-144">The rate, in commands per second, at which initialization commands are committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="70dde-145">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="70dde-145">**#Trans**</span></span>  
 <span data-ttu-id="70dde-146">Nombre de transactions validées dans la base de données de distribution lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-146">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="70dde-147">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="70dde-147">**#Cmds**</span></span>  
 <span data-ttu-id="70dde-148">Nombre de commandes validées dans la base de données de distribution lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-148">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="70dde-149">Une commande est équivalente à une modification des données, par exemple une mise à jour.</span><span class="sxs-lookup"><span data-stu-id="70dde-149">A command is equivalent to a data change, such as an update.</span></span>  
  
### <a name="log-reader-agent"></a><span data-ttu-id="70dde-150">l'Agent de lecture du journal ;</span><span class="sxs-lookup"><span data-stu-id="70dde-150">Log Reader Agent</span></span>  
 <span data-ttu-id="70dde-151">**État**</span><span class="sxs-lookup"><span data-stu-id="70dde-151">**Status**</span></span>  
 <span data-ttu-id="70dde-152">État de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-152">The status of the agent.</span></span> <span data-ttu-id="70dde-153">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="70dde-153">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="70dde-154">Error</span><span class="sxs-lookup"><span data-stu-id="70dde-154">Error</span></span>  
  
-   <span data-ttu-id="70dde-155">Recommencer</span><span class="sxs-lookup"><span data-stu-id="70dde-155">Retry</span></span>  
  
-   <span data-ttu-id="70dde-156">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="70dde-156">Running</span></span>  
  
-   <span data-ttu-id="70dde-157">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="70dde-157">Not running</span></span>  
  
 <span data-ttu-id="70dde-158">**Base de données de publication**</span><span class="sxs-lookup"><span data-stu-id="70dde-158">**Publication Database**</span></span>  
 <span data-ttu-id="70dde-159">Nom de la publication à laquelle l'agent est associé.</span><span class="sxs-lookup"><span data-stu-id="70dde-159">The name of the publication with which the agent is associated.</span></span>  
  
 <span data-ttu-id="70dde-160">**Dernière heure de début**</span><span class="sxs-lookup"><span data-stu-id="70dde-160">**Last Start Time**</span></span>  
 <span data-ttu-id="70dde-161">Dernière heure à laquelle l'Agent a démarré.</span><span class="sxs-lookup"><span data-stu-id="70dde-161">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="70dde-162">**Durée**</span><span class="sxs-lookup"><span data-stu-id="70dde-162">**Duration**</span></span>  
 <span data-ttu-id="70dde-163">Durée pendant laquelle l'agent s'est exécuté.</span><span class="sxs-lookup"><span data-stu-id="70dde-163">The length of time the agent has run.</span></span> <span data-ttu-id="70dde-164">Cette durée représente le temps actuel si l'agent est en cours d'exécution ou le temps total d'exécution s'il a été exécuté et s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="70dde-164">The time represents elapsed time if the agent is currently running, and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="70dde-165">**Dernière action**</span><span class="sxs-lookup"><span data-stu-id="70dde-165">**Last Action**</span></span>  
 <span data-ttu-id="70dde-166">La dernière action effectuée au cours de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-166">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="70dde-167">**Vitesse de transmission**</span><span class="sxs-lookup"><span data-stu-id="70dde-167">**Delivery Rate**</span></span>  
 <span data-ttu-id="70dde-168">Vitesse, en commandes par seconde, à laquelle les modifications sont validées dans la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="70dde-168">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="70dde-169">**Latence**</span><span class="sxs-lookup"><span data-stu-id="70dde-169">**Latency**</span></span>  
 <span data-ttu-id="70dde-170">Durée, en secondes, écoulée entre la modification la plus récente validée dans la base de données de publication et la commande correspondante validée dans la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="70dde-170">The amount of time, in seconds, that has elapsed between the most recent change being committed in the publication database, and the corresponding command being committed in the distribution database.</span></span>  
  
 <span data-ttu-id="70dde-171">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="70dde-171">**#Trans**</span></span>  
 <span data-ttu-id="70dde-172">Nombre de transactions validées dans la base de données de distribution lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-172">The number of transactions committed in the distribution database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="70dde-173">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="70dde-173">**#Cmds**</span></span>  
 <span data-ttu-id="70dde-174">Nombre de commandes validées dans la base de données de distribution lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-174">The number of commands committed in the distribution database during the most recent run of the agent.</span></span> <span data-ttu-id="70dde-175">Une commande est équivalente à une modification des données, par exemple une mise à jour.</span><span class="sxs-lookup"><span data-stu-id="70dde-175">A command is equivalent to a data change, such as an update.</span></span>  
  
 <span data-ttu-id="70dde-176">**Nb moy. de #Cmds**</span><span class="sxs-lookup"><span data-stu-id="70dde-176">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="70dde-177">Nombre moyen de commandes par transaction lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-177">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="queue-reader-agent"></a><span data-ttu-id="70dde-178">Agent de lecture de la file d'attente</span><span class="sxs-lookup"><span data-stu-id="70dde-178">Queue Reader Agent</span></span>  
 <span data-ttu-id="70dde-179">**État**</span><span class="sxs-lookup"><span data-stu-id="70dde-179">**Status**</span></span>  
 <span data-ttu-id="70dde-180">État de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-180">The status of the agent.</span></span> <span data-ttu-id="70dde-181">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="70dde-181">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="70dde-182">Error</span><span class="sxs-lookup"><span data-stu-id="70dde-182">Error</span></span>  
  
-   <span data-ttu-id="70dde-183">Recommencer</span><span class="sxs-lookup"><span data-stu-id="70dde-183">Retry</span></span>  
  
-   <span data-ttu-id="70dde-184">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="70dde-184">Running</span></span>  
  
-   <span data-ttu-id="70dde-185">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="70dde-185">Not running</span></span>  
  
 <span data-ttu-id="70dde-186">**Base de données de distribution**</span><span class="sxs-lookup"><span data-stu-id="70dde-186">**Distribution Database**</span></span>  
 <span data-ttu-id="70dde-187">Nom de la base de données de distribution à laquelle l'Agent est associé.</span><span class="sxs-lookup"><span data-stu-id="70dde-187">The name of the distribution database with which the agent is associated.</span></span>  
  
 <span data-ttu-id="70dde-188">**Dernière heure de début**</span><span class="sxs-lookup"><span data-stu-id="70dde-188">**Last Start Time**</span></span>  
 <span data-ttu-id="70dde-189">Dernière heure à laquelle l'Agent a démarré.</span><span class="sxs-lookup"><span data-stu-id="70dde-189">The last time at which the agent started.</span></span>  
  
 <span data-ttu-id="70dde-190">**Durée**</span><span class="sxs-lookup"><span data-stu-id="70dde-190">**Duration**</span></span>  
 <span data-ttu-id="70dde-191">Durée pendant laquelle l'agent s'est exécuté.</span><span class="sxs-lookup"><span data-stu-id="70dde-191">The length of time the agent has run.</span></span> <span data-ttu-id="70dde-192">La durée correspond au délai écoulé si l'Agent est actif ou au délai total si l'Agent a déjà été exécuté.</span><span class="sxs-lookup"><span data-stu-id="70dde-192">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="70dde-193">**Dernière action**</span><span class="sxs-lookup"><span data-stu-id="70dde-193">**Last Action**</span></span>  
 <span data-ttu-id="70dde-194">La dernière action effectuée au cours de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-194">The last action performed during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="70dde-195">**Vitesse de transmission**</span><span class="sxs-lookup"><span data-stu-id="70dde-195">**Delivery Rate**</span></span>  
 <span data-ttu-id="70dde-196">Vitesse, en commandes par seconde, à laquelle les modifications sont validées dans la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="70dde-196">The rate, in commands per second, at which changes are committed in the distribution database.</span></span>  
  
 <span data-ttu-id="70dde-197">**Latence**</span><span class="sxs-lookup"><span data-stu-id="70dde-197">**Latency**</span></span>  
 <span data-ttu-id="70dde-198">Durée, en secondes, écoulée entre la modification la plus récente validée dans une base de données d'abonnement et la commande correspondante validée dans la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="70dde-198">The amount of time, in seconds, that has elapsed between the most recent change being committed in a subscription database, and the corresponding command being committed in the publication database.</span></span>  
  
 <span data-ttu-id="70dde-199">**#Trans**</span><span class="sxs-lookup"><span data-stu-id="70dde-199">**#Trans**</span></span>  
 <span data-ttu-id="70dde-200">Nombre de transactions validées dans la base de données de publication lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-200">The number of transactions committed in the publication database during the most recent run of the agent.</span></span>  
  
 <span data-ttu-id="70dde-201">**#Cmds**</span><span class="sxs-lookup"><span data-stu-id="70dde-201">**#Cmds**</span></span>  
 <span data-ttu-id="70dde-202">Nombre de commandes validées dans la base de données de publication lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-202">The number of commands committed in the publication database during the most recent run of the agent.</span></span> <span data-ttu-id="70dde-203">Une commande est équivalente à une modification des données, par exemple une mise à jour.</span><span class="sxs-lookup"><span data-stu-id="70dde-203">A command is equivalent to a data change, such as an update.</span></span>  
  
 <span data-ttu-id="70dde-204">**Nb moy. de #Cmds**</span><span class="sxs-lookup"><span data-stu-id="70dde-204">**Avg. #Cmds**</span></span>  
 <span data-ttu-id="70dde-205">Nombre moyen de commandes par transaction lors de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="70dde-205">The average number of commands per transaction during the most recent run of the agent.</span></span>  
  
### <a name="maintenance-jobs"></a><span data-ttu-id="70dde-206">Travaux de maintenance</span><span class="sxs-lookup"><span data-stu-id="70dde-206">Maintenance Jobs</span></span>  
 <span data-ttu-id="70dde-207">**État**</span><span class="sxs-lookup"><span data-stu-id="70dde-207">**Status**</span></span>  
 <span data-ttu-id="70dde-208">État de chaque travail.</span><span class="sxs-lookup"><span data-stu-id="70dde-208">The status of each job.</span></span> <span data-ttu-id="70dde-209">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="70dde-209">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="70dde-210">Error</span><span class="sxs-lookup"><span data-stu-id="70dde-210">Error</span></span>  
  
-   <span data-ttu-id="70dde-211">Recommencer</span><span class="sxs-lookup"><span data-stu-id="70dde-211">Retry</span></span>  
  
-   <span data-ttu-id="70dde-212">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="70dde-212">Running</span></span>  
  
-   <span data-ttu-id="70dde-213">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="70dde-213">Not running</span></span>  
  
 <span data-ttu-id="70dde-214">**Travail**</span><span class="sxs-lookup"><span data-stu-id="70dde-214">**Job**</span></span>  
 <span data-ttu-id="70dde-215">Nom du travail.</span><span class="sxs-lookup"><span data-stu-id="70dde-215">The name of the job.</span></span>  
  
 <span data-ttu-id="70dde-216">**Dernière heure de début**</span><span class="sxs-lookup"><span data-stu-id="70dde-216">**Last Start Time**</span></span>  
 <span data-ttu-id="70dde-217">Dernière heure à laquelle le travail a démarré.</span><span class="sxs-lookup"><span data-stu-id="70dde-217">The last time at which the job started.</span></span>  
  
 <span data-ttu-id="70dde-218">**Durée**</span><span class="sxs-lookup"><span data-stu-id="70dde-218">**Duration**</span></span>  
 <span data-ttu-id="70dde-219">Durée d'exécution du travail.</span><span class="sxs-lookup"><span data-stu-id="70dde-219">The length of time the job has run.</span></span> <span data-ttu-id="70dde-220">Cette durée correspond au temps écoulé si le travail est en cours d'exécution et à la durée totale si le travail a été accompli précédemment.</span><span class="sxs-lookup"><span data-stu-id="70dde-220">The time represents elapsed time if the job is currently running, and total time if the job has run previously.</span></span>  
  
 <span data-ttu-id="70dde-221">**Dernière action**</span><span class="sxs-lookup"><span data-stu-id="70dde-221">**Last Action**</span></span>  
 <span data-ttu-id="70dde-222">Dernière action effectuée lors de la dernière exécution du travail.</span><span class="sxs-lookup"><span data-stu-id="70dde-222">The last action performed during the most recent run of the job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70dde-223">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70dde-223">See Also</span></span>  
 <span data-ttu-id="70dde-224">[Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="70dde-224">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="70dde-225">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="70dde-225">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="70dde-226">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="70dde-226">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
