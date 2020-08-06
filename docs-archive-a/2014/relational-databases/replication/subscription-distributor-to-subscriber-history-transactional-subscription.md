---
title: Abonnement, historique du serveur de distribution vers l’abonné (abonnement transactionnel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.disttosub.f1
ms.assetid: 1aad5b82-592e-4907-92f7-b90794175be5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5cb9d708b75a9414725907530c7454cdba26d135
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708159"
---
# <a name="subscription-distributor-to-subscriber-history-transactional-subscription"></a><span data-ttu-id="9b37d-102">Abonnement, Historique du serveur de distribution vers l'Abonné (Abonnement transactionnel)</span><span class="sxs-lookup"><span data-stu-id="9b37d-102">Subscription, Distributor to Subscriber History (Transactional Subscription)</span></span>
  <span data-ttu-id="9b37d-103">L'onglet **Historique du serveur de distribution vers l'Abonné** affiche des informations détaillées sur l'Agent de distribution, y compris l'état, l'historique, des messages d'information et d'éventuels messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="9b37d-103">The **Distributor to Subscriber History** tab displays detailed information on the Distribution Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9b37d-104">Options</span><span class="sxs-lookup"><span data-stu-id="9b37d-104">Options</span></span>  
 <span data-ttu-id="9b37d-105">Dans le menu **Affichage** , sélectionnez les sessions de l'Agent de distribution à afficher. Sélectionnez ensuite une session particulière dans la grille étiquetée **Sessions de l'Agent de distribution**.</span><span class="sxs-lookup"><span data-stu-id="9b37d-105">Select which Distribution Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Distribution Agent**.</span></span> <span data-ttu-id="9b37d-106">Des informations détaillées sur cette session s'affichent dans la grille étiquetée **Actions dans la session sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="9b37d-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="9b37d-107">Si la session sélectionnée s'est terminée sur une erreur, la zone de texte étiquetée **Détails de l'erreur ou message de la session sélectionnée** s'affiche également.</span><span class="sxs-lookup"><span data-stu-id="9b37d-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="9b37d-108">**Visualiser**</span><span class="sxs-lookup"><span data-stu-id="9b37d-108">**View**</span></span>  
 <span data-ttu-id="9b37d-109">Sélectionnez les sessions de l'Agent de distribution à afficher.</span><span class="sxs-lookup"><span data-stu-id="9b37d-109">Select which Distribution Agent sessions to view.</span></span> <span data-ttu-id="9b37d-110">Comme l'agent de distribution s'exécute généralement en continu, il se peut qu'il n'y ait qu'une seule session à afficher.</span><span class="sxs-lookup"><span data-stu-id="9b37d-110">The Distribution Agent typically runs continuously, therefore there might be only one session to view.</span></span>  
  
 <span data-ttu-id="9b37d-111">**État**</span><span class="sxs-lookup"><span data-stu-id="9b37d-111">**Status**</span></span>  
 <span data-ttu-id="9b37d-112">État de l'Agent de distribution</span><span class="sxs-lookup"><span data-stu-id="9b37d-112">The status of the Distribution Agent.</span></span> <span data-ttu-id="9b37d-113">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="9b37d-113">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="9b37d-114">Error</span><span class="sxs-lookup"><span data-stu-id="9b37d-114">Error</span></span>  
  
-   <span data-ttu-id="9b37d-115">Completed</span><span class="sxs-lookup"><span data-stu-id="9b37d-115">Completed</span></span>  
  
-   <span data-ttu-id="9b37d-116">Nouvel essai</span><span class="sxs-lookup"><span data-stu-id="9b37d-116">Retrying</span></span>  
  
-   <span data-ttu-id="9b37d-117">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="9b37d-117">Running</span></span>  
  
 <span data-ttu-id="9b37d-118">**Heure de début**</span><span class="sxs-lookup"><span data-stu-id="9b37d-118">**Start Time**</span></span>  
 <span data-ttu-id="9b37d-119">Heure d'ouverture de la session.</span><span class="sxs-lookup"><span data-stu-id="9b37d-119">The start time of the session.</span></span>  
  
 <span data-ttu-id="9b37d-120">**Heure de fin**</span><span class="sxs-lookup"><span data-stu-id="9b37d-120">**End Time**</span></span>  
 <span data-ttu-id="9b37d-121">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="9b37d-121">The end time of the session.</span></span> <span data-ttu-id="9b37d-122">Si l'agent ne s'est pas arrêté, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="9b37d-122">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="9b37d-123">**Durée**</span><span class="sxs-lookup"><span data-stu-id="9b37d-123">**Duration**</span></span>  
 <span data-ttu-id="9b37d-124">Durée d'exécution de l'Agent de distribution dans cette session.</span><span class="sxs-lookup"><span data-stu-id="9b37d-124">The amount of time the Distribution Agent has run in this session.</span></span> <span data-ttu-id="9b37d-125">Cette durée représente le temps écoulé si l'agent est en cours d'exécution et le temps total de la session si l'agent de la session s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="9b37d-125">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="9b37d-126">**Message d’erreur**</span><span class="sxs-lookup"><span data-stu-id="9b37d-126">**Error Message**</span></span>  
 <span data-ttu-id="9b37d-127">Si une session s'est terminée sur une erreur, ce champ affiche le dernier message d'erreur enregistré par l'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="9b37d-127">If a session ended in an error, this field displays the last error message logged by the Distribution Agent.</span></span> <span data-ttu-id="9b37d-128">Dans le cas contraire, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="9b37d-128">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="9b37d-129">**Message d'action**</span><span class="sxs-lookup"><span data-stu-id="9b37d-129">**Action Message**</span></span>  
 <span data-ttu-id="9b37d-130">Tous les messages d'information ou d'erreur que l'Agent de distribution a enregistrés pendant la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9b37d-130">All informational messages and error messages that the Distribution Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="9b37d-131">**Heure de l'action**</span><span class="sxs-lookup"><span data-stu-id="9b37d-131">**Action Time**</span></span>  
 <span data-ttu-id="9b37d-132">Heure à laquelle l'action décrite dans la colonne **Message d'action** s'est déroulée.</span><span class="sxs-lookup"><span data-stu-id="9b37d-132">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="9b37d-133">**Détails de l'erreur ou message de la session sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="9b37d-133">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="9b37d-134">S'affiche uniquement si la session sélectionnée affiche une valeur **Erreur** dans la colonne **État** .</span><span class="sxs-lookup"><span data-stu-id="9b37d-134">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="9b37d-135">La zone de texte affiche des informations d'erreur détaillées, ainsi que la commande émise au moment de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="9b37d-135">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="9b37d-136">Elle comporte également des liens vers des informations supplémentaires à propos de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="9b37d-136">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b37d-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b37d-137">See Also</span></span>  
 <span data-ttu-id="9b37d-138">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9b37d-138">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="9b37d-139">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9b37d-139">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="9b37d-140">[Surveillance de la réplication](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="9b37d-140">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="9b37d-141">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="9b37d-141">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
