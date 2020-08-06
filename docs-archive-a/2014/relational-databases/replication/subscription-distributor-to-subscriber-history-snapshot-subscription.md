---
title: Abonnement, Historique du serveur de distribution vers l’abonné (Abonnement aux instantanés) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.snapshot.f1
ms.assetid: d3575964-f287-4bcf-8d2e-f81a33141b25
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fe894e23e7ad7fef9c328334740eff73164130a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708156"
---
# <a name="subscription-distributor-to-subscriber-history-snapshot-subscription"></a><span data-ttu-id="e3287-102">Abonnement, Historique du serveur de distribution vers l'Abonné (abonnement aux instantanés)</span><span class="sxs-lookup"><span data-stu-id="e3287-102">Subscription, Distributor to Subscriber History (Snapshot Subscription)</span></span>
  <span data-ttu-id="e3287-103">L'onglet **Historique du serveur de distribution vers l'Abonné** affiche des informations détaillées sur l'Agent de distribution, y compris l'état, l'historique, des messages d'information et d'éventuels messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e3287-103">The **Distributor to Subscriber History** tab displays detailed information on the Distribution Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e3287-104">Options</span><span class="sxs-lookup"><span data-stu-id="e3287-104">Options</span></span>  
 <span data-ttu-id="e3287-105">Dans le menu **Affichage** , sélectionnez les sessions de l'Agent de distribution à afficher. Sélectionnez ensuite une session particulière dans la grille étiquetée **Sessions de l'Agent de distribution**.</span><span class="sxs-lookup"><span data-stu-id="e3287-105">Select which Distribution Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Distribution Agent**.</span></span> <span data-ttu-id="e3287-106">Des informations détaillées sur cette session s'affichent dans la grille étiquetée **Actions dans la session sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="e3287-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="e3287-107">Si la session sélectionnée s'est terminée sur une erreur, la zone de texte étiquetée **Détails de l'erreur ou message de la session sélectionnée** s'affiche également.</span><span class="sxs-lookup"><span data-stu-id="e3287-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="e3287-108">**Visualiser**</span><span class="sxs-lookup"><span data-stu-id="e3287-108">**View**</span></span>  
 <span data-ttu-id="e3287-109">Sélectionnez les sessions de l'Agent de distribution à afficher.</span><span class="sxs-lookup"><span data-stu-id="e3287-109">Select which Distribution Agent sessions to view.</span></span>  
  
 <span data-ttu-id="e3287-110">**État**</span><span class="sxs-lookup"><span data-stu-id="e3287-110">**Status**</span></span>  
 <span data-ttu-id="e3287-111">État de l'Agent de distribution</span><span class="sxs-lookup"><span data-stu-id="e3287-111">The status of the Distribution Agent.</span></span> <span data-ttu-id="e3287-112">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="e3287-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="e3287-113">Error</span><span class="sxs-lookup"><span data-stu-id="e3287-113">Error</span></span>  
  
-   <span data-ttu-id="e3287-114">Completed</span><span class="sxs-lookup"><span data-stu-id="e3287-114">Completed</span></span>  
  
-   <span data-ttu-id="e3287-115">Nouvel essai</span><span class="sxs-lookup"><span data-stu-id="e3287-115">Retrying</span></span>  
  
-   <span data-ttu-id="e3287-116">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="e3287-116">Running</span></span>  
  
 <span data-ttu-id="e3287-117">**Heure de début**</span><span class="sxs-lookup"><span data-stu-id="e3287-117">**Start Time**</span></span>  
 <span data-ttu-id="e3287-118">Heure d'ouverture de la session.</span><span class="sxs-lookup"><span data-stu-id="e3287-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="e3287-119">**Heure de fin**</span><span class="sxs-lookup"><span data-stu-id="e3287-119">**End Time**</span></span>  
 <span data-ttu-id="e3287-120">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="e3287-120">The end time of the session.</span></span> <span data-ttu-id="e3287-121">Si l'agent ne s'est pas arrêté, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="e3287-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="e3287-122">**Durée**</span><span class="sxs-lookup"><span data-stu-id="e3287-122">**Duration**</span></span>  
 <span data-ttu-id="e3287-123">Durée d'exécution de l'Agent de distribution dans cette session.</span><span class="sxs-lookup"><span data-stu-id="e3287-123">The amount of time the Distribution Agent has run in this session.</span></span> <span data-ttu-id="e3287-124">Cette durée représente le temps écoulé si l'agent est en cours d'exécution et le temps total de la session si l'agent de la session s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="e3287-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session had ended.</span></span>  
  
 <span data-ttu-id="e3287-125">**Message d’erreur**</span><span class="sxs-lookup"><span data-stu-id="e3287-125">**Error Message**</span></span>  
 <span data-ttu-id="e3287-126">Si une session s'est terminée sur une erreur, ce champ affiche le dernier message d'erreur enregistré par l'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="e3287-126">If a session ended in an error, this field displays the last error message logged by the Distribution Agent.</span></span> <span data-ttu-id="e3287-127">Dans le cas contraire, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="e3287-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="e3287-128">**Message d'action**</span><span class="sxs-lookup"><span data-stu-id="e3287-128">**Action Message**</span></span>  
 <span data-ttu-id="e3287-129">Tous les messages d'information ou d'erreur que l'Agent de distribution a enregistrés pendant la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e3287-129">All informational messages and error messages that the Distribution Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="e3287-130">**Heure de l'action**</span><span class="sxs-lookup"><span data-stu-id="e3287-130">**Action Time**</span></span>  
 <span data-ttu-id="e3287-131">Heure à laquelle l'action décrite dans la colonne **Message d'action** s'est déroulée.</span><span class="sxs-lookup"><span data-stu-id="e3287-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="e3287-132">**Détails de l'erreur ou message de la session sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="e3287-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="e3287-133">S'affiche uniquement si la session sélectionnée affiche une valeur **Erreur** dans la colonne **État** .</span><span class="sxs-lookup"><span data-stu-id="e3287-133">Displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="e3287-134">La zone de texte affiche des informations d'erreur détaillées, ainsi que la commande émise au moment de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="e3287-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="e3287-135">Elle comporte également des liens vers des informations supplémentaires à propos de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="e3287-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3287-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e3287-136">See Also</span></span>  
 <span data-ttu-id="e3287-137">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="e3287-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="e3287-138">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="e3287-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="e3287-139">[Surveillance de la réplication](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="e3287-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="e3287-140">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="e3287-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
