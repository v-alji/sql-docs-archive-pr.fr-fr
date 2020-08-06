---
title: Agent de lecture du journal | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.logreaderagent.f1
helpviewer_keywords:
- Log Reader Agent dialog box
ms.assetid: 300a3c46-0e48-4334-99c0-9ee690d2ef4f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2b908e43cf97350fee2913e8cc6bab30a1bcd0dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707364"
---
# <a name="log-reader-agent"></a><span data-ttu-id="6bdae-102">l'Agent de lecture du journal ;</span><span class="sxs-lookup"><span data-stu-id="6bdae-102">Log Reader Agent</span></span>
  <span data-ttu-id="6bdae-103">La boîte de dialogue **Agent de lecture du journal** affiche des informations détaillées sur l'Agent de lecture du journal, notamment l'état, l'historique, les messages d'information et messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="6bdae-103">The **Log Reader Agent** dialog box displays detailed information on the Log Reader Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6bdae-104">Options</span><span class="sxs-lookup"><span data-stu-id="6bdae-104">Options</span></span>  
 <span data-ttu-id="6bdae-105">Dans le menu **Affichage** , sélectionnez les sessions de l'Agent de lecture du journal à afficher. Sélectionnez ensuite une session particulière dans la grille étiquetée **Sessions de l'Agent de lecture du journal**.</span><span class="sxs-lookup"><span data-stu-id="6bdae-105">Select which Log Reader Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Log Reader Agent**.</span></span> <span data-ttu-id="6bdae-106">Des informations détaillées sur cette session s'affichent dans la grille étiquetée **Actions dans la session sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="6bdae-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="6bdae-107">Si la session sélectionnée s'est terminée sur une erreur, la zone de texte étiquetée **Détails de l'erreur ou message de la session sélectionnée** s'affiche également.</span><span class="sxs-lookup"><span data-stu-id="6bdae-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="6bdae-108">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="6bdae-108">**View**</span></span>  
 <span data-ttu-id="6bdae-109">Sélectionnez les sessions de l'Agent de lecture du journal à afficher.</span><span class="sxs-lookup"><span data-stu-id="6bdae-109">Select which Log Reader Agent sessions to view.</span></span> <span data-ttu-id="6bdae-110">L'Agent de lecture du journal s'exécute généralement en permanence : il se peut donc qu'il n'y ait qu'une session à afficher.</span><span class="sxs-lookup"><span data-stu-id="6bdae-110">The Log Reader Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="6bdae-111">**État**</span><span class="sxs-lookup"><span data-stu-id="6bdae-111">**Status**</span></span>  
 <span data-ttu-id="6bdae-112">État de l'Agent de lecture du journal.</span><span class="sxs-lookup"><span data-stu-id="6bdae-112">The status of the Log Reader Agent.</span></span> <span data-ttu-id="6bdae-113">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="6bdae-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="6bdae-114">Error</span><span class="sxs-lookup"><span data-stu-id="6bdae-114">Error</span></span>  
  
-   <span data-ttu-id="6bdae-115">Nouvelle tentative de la commande qui a échoué</span><span class="sxs-lookup"><span data-stu-id="6bdae-115">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="6bdae-116">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="6bdae-116">Not running</span></span>  
  
-   <span data-ttu-id="6bdae-117">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="6bdae-117">Running</span></span>  
  
 <span data-ttu-id="6bdae-118">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="6bdae-118">**Start Time**</span></span>  
 <span data-ttu-id="6bdae-119">Heure d'ouverture de la session.</span><span class="sxs-lookup"><span data-stu-id="6bdae-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="6bdae-120">**Heure de fin**</span><span class="sxs-lookup"><span data-stu-id="6bdae-120">**End Time**</span></span>  
 <span data-ttu-id="6bdae-121">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="6bdae-121">The end time of the session.</span></span> <span data-ttu-id="6bdae-122">Si l'agent ne s'est pas arrêté, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="6bdae-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="6bdae-123">**Durée**</span><span class="sxs-lookup"><span data-stu-id="6bdae-123">**Duration**</span></span>  
 <span data-ttu-id="6bdae-124">Durée d'exécution de l'Agent de lecture du journal dans cette session.</span><span class="sxs-lookup"><span data-stu-id="6bdae-124">The amount of time the Log Reader Agent has run in this session.</span></span> <span data-ttu-id="6bdae-125">Cette durée représente le temps écoulé si l'agent est en cours d'exécution et le temps total de la session si l'agent de la session s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="6bdae-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="6bdae-126">**Message d’erreur**</span><span class="sxs-lookup"><span data-stu-id="6bdae-126">**Error Message**</span></span>  
 <span data-ttu-id="6bdae-127">Si une session s'est terminée sur une erreur, ce champ affiche le dernier message d'erreur enregistré par l'Agent de lecture du journal.</span><span class="sxs-lookup"><span data-stu-id="6bdae-127">If a session ended in an error, this field displays the last error message logged by the Log Reader Agent.</span></span> <span data-ttu-id="6bdae-128">Dans le cas contraire, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="6bdae-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="6bdae-129">**Message d'action**</span><span class="sxs-lookup"><span data-stu-id="6bdae-129">**Action Message**</span></span>  
 <span data-ttu-id="6bdae-130">Tous les messages d'information ou d'erreur que l'Agent de lecture du journal a enregistrés pendant la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6bdae-130">All informational messages and error messages that the Log Reader Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="6bdae-131">**Heure de l'action**</span><span class="sxs-lookup"><span data-stu-id="6bdae-131">**Action Time**</span></span>  
 <span data-ttu-id="6bdae-132">Heure à laquelle l'action décrite dans la colonne **Message d'action** s'est déroulée.</span><span class="sxs-lookup"><span data-stu-id="6bdae-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="6bdae-133">**Détails de l'erreur ou message de la session sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="6bdae-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="6bdae-134">S'affiche uniquement si la session sélectionnée affiche une valeur **Erreur** dans la colonne **État** .</span><span class="sxs-lookup"><span data-stu-id="6bdae-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="6bdae-135">La zone de texte affiche des informations d'erreur détaillées, ainsi que la commande émise au moment de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="6bdae-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="6bdae-136">Elle comporte également des liens vers des informations supplémentaires à propos de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="6bdae-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bdae-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6bdae-137">See Also</span></span>  
 <span data-ttu-id="6bdae-138">[Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="6bdae-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="6bdae-139">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="6bdae-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="6bdae-140">[Surveillance de la réplication](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="6bdae-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="6bdae-141">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="6bdae-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
