---
title: Abonnement, historique de synchronisation (abonnement de fusion, SQL Server 2005 et versions ultérieures) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.synchhistory.f1
- sql12.rep.monitor.subscription.downlevelsynchhistory.f1
ms.assetid: 85f666f6-14ee-4f19-b385-e5cc508aabe4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49fe19f22976116813ac2454b2d08fc1fe47d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612768"
---
# <a name="subscription-synchronization-history-merge-subscription-sql-server-2005-and-later"></a><span data-ttu-id="e83c6-102">Abonnement, Historique de synchronisation (Abonnement de fusion, SQL Server 2005 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="e83c6-102">Subscription, Synchronization History (Merge Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="e83c6-103">L'onglet **Historique de synchronisation** contient des informations détaillées sur l'Agent de fusion, notamment l'état, les statistiques d'articles, l'historique, les messages d'information et les messages d'erreur éventuels.</span><span class="sxs-lookup"><span data-stu-id="e83c6-103">The **Synchronization History** tab displays detailed information on the Merge Agent, including status, article statistics, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e83c6-104">Options</span><span class="sxs-lookup"><span data-stu-id="e83c6-104">Options</span></span>  
 <span data-ttu-id="e83c6-105">Sélectionnez les sessions de l'Agent de fusion à afficher dans le menu **Afficher** , puis sélectionnez une session dans la grille **Sessions de l'Agent de fusion**.</span><span class="sxs-lookup"><span data-stu-id="e83c6-105">Select which Merge Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Merge Agent**.</span></span> <span data-ttu-id="e83c6-106">Les informations détaillées sur cette session figurent dans la grille **Articles traités dans la session sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="e83c6-106">Detailed information on this session is displayed in the grid labeled **Articles processed in the selected session**.</span></span>  
  
 <span data-ttu-id="e83c6-107">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="e83c6-107">**View**</span></span>  
 <span data-ttu-id="e83c6-108">Sélectionnez les sessions de l'Agent de fusion à afficher.</span><span class="sxs-lookup"><span data-stu-id="e83c6-108">Select which Merge Agent sessions to view.</span></span>  
  
 <span data-ttu-id="e83c6-109">**État**</span><span class="sxs-lookup"><span data-stu-id="e83c6-109">**Status**</span></span>  
 <span data-ttu-id="e83c6-110">État de l'Agent de fusion à la fin de la session.</span><span class="sxs-lookup"><span data-stu-id="e83c6-110">The status of the Merge Agent at the end of the session.</span></span> <span data-ttu-id="e83c6-111">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="e83c6-111">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="e83c6-112">Error</span><span class="sxs-lookup"><span data-stu-id="e83c6-112">Error</span></span>  
  
-   <span data-ttu-id="e83c6-113">Completed</span><span class="sxs-lookup"><span data-stu-id="e83c6-113">Completed</span></span>  
  
-   <span data-ttu-id="e83c6-114">Nouvel essai</span><span class="sxs-lookup"><span data-stu-id="e83c6-114">Retrying</span></span>  
  
-   <span data-ttu-id="e83c6-115">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="e83c6-115">Running</span></span>  
  
 <span data-ttu-id="e83c6-116">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="e83c6-116">**Start Time**</span></span>  
 <span data-ttu-id="e83c6-117">Heure d'ouverture de la session.</span><span class="sxs-lookup"><span data-stu-id="e83c6-117">The start time of the session.</span></span>  
  
 <span data-ttu-id="e83c6-118">**Heure de fin**</span><span class="sxs-lookup"><span data-stu-id="e83c6-118">**End Time**</span></span>  
 <span data-ttu-id="e83c6-119">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="e83c6-119">The end time of the session.</span></span> <span data-ttu-id="e83c6-120">Si l'agent ne s'est pas arrêté, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="e83c6-120">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="e83c6-121">**Durée**</span><span class="sxs-lookup"><span data-stu-id="e83c6-121">**Duration**</span></span>  
 <span data-ttu-id="e83c6-122">Durée d'exécution de l'Agent de fusion au cours d'une session.</span><span class="sxs-lookup"><span data-stu-id="e83c6-122">The amount of time the Merge Agent has run in a session.</span></span> <span data-ttu-id="e83c6-123">La durée correspond au délai écoulé si l'Agent est actif ou au délai total si l'Agent a déjà été exécuté.</span><span class="sxs-lookup"><span data-stu-id="e83c6-123">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="e83c6-124">**Commandes téléchargées**</span><span class="sxs-lookup"><span data-stu-id="e83c6-124">**Uploaded Commands**</span></span>  
 <span data-ttu-id="e83c6-125">Nombre de lignes téléchargées en amont au cours de la session de l'Agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="e83c6-125">The number of rows uploaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="e83c6-126">**Commandes téléchargées**</span><span class="sxs-lookup"><span data-stu-id="e83c6-126">**Downloaded Commands**</span></span>  
 <span data-ttu-id="e83c6-127">Nombre de lignes téléchargées en aval au cours de la session de l'Agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="e83c6-127">The number of rows downloaded during the Merge Agent session.</span></span>  
  
 <span data-ttu-id="e83c6-128">**Message d’erreur**</span><span class="sxs-lookup"><span data-stu-id="e83c6-128">**Error Message**</span></span>  
 <span data-ttu-id="e83c6-129">Si la session s'est terminée par une erreur, ce champ contient le dernier message d'erreur consigné par l'Agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="e83c6-129">If a session ended in an error, this field displays the last error message logged by the Merge Agent.</span></span> <span data-ttu-id="e83c6-130">Dans le cas contraire, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="e83c6-130">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="e83c6-131">**Article**</span><span class="sxs-lookup"><span data-stu-id="e83c6-131">**Article**</span></span>  
 <span data-ttu-id="e83c6-132">Nom de chaque article dans la publication, et phases de traitement suivantes de l'ensemble de la publication :</span><span class="sxs-lookup"><span data-stu-id="e83c6-132">The name of each article in the publication, and the following processing phases for the entire publication:</span></span>  
  
-   <span data-ttu-id="e83c6-133">**Initialisation**.</span><span class="sxs-lookup"><span data-stu-id="e83c6-133">**Initialization**.</span></span> <span data-ttu-id="e83c6-134">Fait référence au démarrage de l'Agent de fusion ; n'est pas identique à l'initialisation d'un abonnement qui implique d'appliquer un instantané.</span><span class="sxs-lookup"><span data-stu-id="e83c6-134">This refers to starting the Merge Agent; this is not synonymous with initializing a subscription, which involves applying a snapshot.</span></span>  
  
-   <span data-ttu-id="e83c6-135">**Modifications de schéma et insertions en bloc**.</span><span class="sxs-lookup"><span data-stu-id="e83c6-135">**Schema changes and bulk inserts**.</span></span>  
  
-   <span data-ttu-id="e83c6-136">**Télécharger les modifications vers le serveur de publication**.</span><span class="sxs-lookup"><span data-stu-id="e83c6-136">**Upload changes to Publisher**.</span></span>  
  
-   <span data-ttu-id="e83c6-137">**Téléchargement des modifications vers l'Abonné**.</span><span class="sxs-lookup"><span data-stu-id="e83c6-137">**Download changes to Subscriber**.</span></span>  
  
 <span data-ttu-id="e83c6-138">Les phases sont incluses pour que la grille puisse afficher la durée et le pourcentage de temps total correspondant à chaque phase dans la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e83c6-138">The phases are included so that the grid can display the amount of time and percentage of total time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="e83c6-139">**% du total**</span><span class="sxs-lookup"><span data-stu-id="e83c6-139">**% of total**</span></span>  
 <span data-ttu-id="e83c6-140">Pourcentage du temps de traitement total correspondant à chaque phase dans la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e83c6-140">The percentage of total processing time that each phase accounts for in the selected session.</span></span>  
  
 <span data-ttu-id="e83c6-141">**Durée**</span><span class="sxs-lookup"><span data-stu-id="e83c6-141">**Duration**</span></span>  
 <span data-ttu-id="e83c6-142">Durée passée dans chaque phase de traitement.</span><span class="sxs-lookup"><span data-stu-id="e83c6-142">The amount of time spent in each processing phase.</span></span> <span data-ttu-id="e83c6-143">La durée correspond au délai écoulé si l'Agent de fusion est en cours d'exécution au cours de la session ou au délai total s'il a déjà été exécuté.</span><span class="sxs-lookup"><span data-stu-id="e83c6-143">The time represents elapsed time if the Merge Agent is currently running for the session and total time if the Merge Agent has run previously.</span></span>  
  
 <span data-ttu-id="e83c6-144">**Inserts**</span><span class="sxs-lookup"><span data-stu-id="e83c6-144">**Inserts**</span></span>  
 <span data-ttu-id="e83c6-145">Nombre de lignes insérées dans cette phase de la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e83c6-145">The number of rows inserted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="e83c6-146">**Mises à jour**</span><span class="sxs-lookup"><span data-stu-id="e83c6-146">**Updates**</span></span>  
 <span data-ttu-id="e83c6-147">Nombre de lignes mises à jour dans cette phase de la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e83c6-147">The number of rows updated in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="e83c6-148">**Suppressions**</span><span class="sxs-lookup"><span data-stu-id="e83c6-148">**Deletes**</span></span>  
 <span data-ttu-id="e83c6-149">Nombre de lignes supprimées dans cette phase de la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e83c6-149">The number of rows deleted in this phase of the selected session.</span></span>  
  
 <span data-ttu-id="e83c6-150">**Conflits**</span><span class="sxs-lookup"><span data-stu-id="e83c6-150">**Conflicts**</span></span>  
 <span data-ttu-id="e83c6-151">Nombre de conflits dans la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e83c6-151">The number of conflicts in the selected session.</span></span>  
  
 <span data-ttu-id="e83c6-152">**Modifications de schéma**</span><span class="sxs-lookup"><span data-stu-id="e83c6-152">**Schema Changes**</span></span>  
 <span data-ttu-id="e83c6-153">Nombre de modifications de schéma dans la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e83c6-153">The number of schema changes in the selected session.</span></span> <span data-ttu-id="e83c6-154">Ces modifications peuvent résulter : des modifications de schéma répliquées depuis la base de données de publication, de l'ajout ou de la suppression d'articles et de la modification des propriétés d'article ou de publication.</span><span class="sxs-lookup"><span data-stu-id="e83c6-154">Schema changes can result from: schema changes being replicated from the publication database; adding or dropping articles; and changes to article or publication properties.</span></span>  
  
 <span data-ttu-id="e83c6-155">**Dernier message de la session sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="e83c6-155">**Last message of the selected session**</span></span>  
 <span data-ttu-id="e83c6-156">Cette zone de texte contient le dernier message dans la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e83c6-156">This text area displays the last message in the selected session.</span></span> <span data-ttu-id="e83c6-157">Si une erreur se produit, elle contient des informations détaillées sur l'erreur et la commande qui a été exécutée lors de l'occurrence de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="e83c6-157">If an error has occurred, it displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="e83c6-158">Elle comporte également des liens vers des informations supplémentaires à propos de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="e83c6-158">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e83c6-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e83c6-159">See Also</span></span>  
 <span data-ttu-id="e83c6-160">[Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="e83c6-160">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="e83c6-161">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="e83c6-161">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="e83c6-162">[Surveillance de la réplication](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="e83c6-162">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="e83c6-163">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="e83c6-163">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
