---
title: Agent d’instantané | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.snapshotagent.f1
helpviewer_keywords:
- Snapshot Agent dialog box
ms.assetid: b715e621-2cd5-4a15-8f58-a341aa8ef5e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 925f2d3841b5dded6c8504a4a05dc60e61024161
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614495"
---
# <a name="snapshot-agent"></a><span data-ttu-id="d6843-102">Agent d'instantané</span><span class="sxs-lookup"><span data-stu-id="d6843-102">Snapshot Agent</span></span>
  <span data-ttu-id="d6843-103">La boîte de dialogue **Agent d'instantané** affiche des informations détaillées concernant l'Agent d'instantané, notamment son état, son historique, des messages d'information ainsi que tout message d'erreur s'y rapportant.</span><span class="sxs-lookup"><span data-stu-id="d6843-103">The **Snapshot Agent** dialog box displays detailed information on the Snapshot Agent, including status, history, informational messages, and any error messages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d6843-104">Options</span><span class="sxs-lookup"><span data-stu-id="d6843-104">Options</span></span>  
 <span data-ttu-id="d6843-105">Sélectionnez les sessions de l'Agent d'instantané à afficher à partir du menu **Affichage** , puis sélectionnez une session particulière dans la grille **Sessions de l'Agent d'instantané**.</span><span class="sxs-lookup"><span data-stu-id="d6843-105">Select which Snapshot Agent sessions to view from the **View** menu, and then select a specific session in the grid labeled **Sessions of the Snapshot Agent**.</span></span> <span data-ttu-id="d6843-106">Des informations détaillées sur cette session s'affichent dans la grille étiquetée **Actions dans la session sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="d6843-106">Detailed information on this session is displayed in the grid labeled **Actions in the selected session**.</span></span> <span data-ttu-id="d6843-107">Si la session sélectionnée s'est terminée sur une erreur, la zone de texte étiquetée **Détails de l'erreur ou message de la session sélectionnée** s'affiche également.</span><span class="sxs-lookup"><span data-stu-id="d6843-107">If the selected session ended in an error, the text area labeled **Error details or message of the selected session** is also displayed.</span></span>  
  
 <span data-ttu-id="d6843-108">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="d6843-108">**View**</span></span>  
 <span data-ttu-id="d6843-109">Permet de sélectionner les sessions de l'Agent d'instantané à afficher.</span><span class="sxs-lookup"><span data-stu-id="d6843-109">Select which Snapshot Agent sessions to view.</span></span>  
  
 <span data-ttu-id="d6843-110">**État**</span><span class="sxs-lookup"><span data-stu-id="d6843-110">**Status**</span></span>  
 <span data-ttu-id="d6843-111">État de l'Agent d'instantané.</span><span class="sxs-lookup"><span data-stu-id="d6843-111">The status of the Snapshot Agent.</span></span> <span data-ttu-id="d6843-112">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="d6843-112">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="d6843-113">Error</span><span class="sxs-lookup"><span data-stu-id="d6843-113">Error</span></span>  
  
-   <span data-ttu-id="d6843-114">Nouvelle tentative de la commande qui a échoué</span><span class="sxs-lookup"><span data-stu-id="d6843-114">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="d6843-115">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="d6843-115">Not running</span></span>  
  
-   <span data-ttu-id="d6843-116">Completed</span><span class="sxs-lookup"><span data-stu-id="d6843-116">Completed</span></span>  
  
 <span data-ttu-id="d6843-117">**Start Time**</span><span class="sxs-lookup"><span data-stu-id="d6843-117">**Start Time**</span></span>  
 <span data-ttu-id="d6843-118">Heure d'ouverture de la session.</span><span class="sxs-lookup"><span data-stu-id="d6843-118">The start time of the session.</span></span>  
  
 <span data-ttu-id="d6843-119">**Heure de fin**</span><span class="sxs-lookup"><span data-stu-id="d6843-119">**End Time**</span></span>  
 <span data-ttu-id="d6843-120">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="d6843-120">The end time of the session.</span></span> <span data-ttu-id="d6843-121">Si l'agent ne s'est pas arrêté, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="d6843-121">If the agent has not stopped, this field is empty.</span></span>  
  
 <span data-ttu-id="d6843-122">**Durée**</span><span class="sxs-lookup"><span data-stu-id="d6843-122">**Duration**</span></span>  
 <span data-ttu-id="d6843-123">Durée pendant laquelle l'Agent d'instantané s'est exécuté lors de la session en cours.</span><span class="sxs-lookup"><span data-stu-id="d6843-123">The amount of time the Snapshot Agent has run in this session.</span></span> <span data-ttu-id="d6843-124">Cette durée représente le temps écoulé si l'agent est en cours d'exécution et le temps total de la session si l'agent de la session s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="d6843-124">The time represents elapsed time if the agent is currently running and the total time of the session if the agent session has ended.</span></span>  
  
 <span data-ttu-id="d6843-125">**Message d’erreur**</span><span class="sxs-lookup"><span data-stu-id="d6843-125">**Error Message**</span></span>  
 <span data-ttu-id="d6843-126">Si une session s'est terminée sur une erreur, ce champ affiche alors le dernier message d'erreur consigné dans le journal par l'Agent d'instantané.</span><span class="sxs-lookup"><span data-stu-id="d6843-126">If a session ended in an error, this field displays the last error message logged by the Snapshot Agent.</span></span> <span data-ttu-id="d6843-127">Dans le cas contraire, ce champ est vide.</span><span class="sxs-lookup"><span data-stu-id="d6843-127">If a session did not end in an error, this field is blank.</span></span>  
  
 <span data-ttu-id="d6843-128">**Message d'action**</span><span class="sxs-lookup"><span data-stu-id="d6843-128">**Action Message**</span></span>  
 <span data-ttu-id="d6843-129">Correspond à tous les messages d'information et d'erreur que l'Agent d'instantané a consignés dans le journal lors de la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d6843-129">All informational messages and error messages that the Snapshot Agent has logged during the selected session.</span></span>  
  
 <span data-ttu-id="d6843-130">**Heure de l'action**</span><span class="sxs-lookup"><span data-stu-id="d6843-130">**Action Time**</span></span>  
 <span data-ttu-id="d6843-131">Heure à laquelle l'action décrite dans la colonne **Message d'action** s'est déroulée.</span><span class="sxs-lookup"><span data-stu-id="d6843-131">The time at which the action described in the **Action Message** column was performed.</span></span>  
  
 <span data-ttu-id="d6843-132">**Détails de l'erreur ou message de la session sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="d6843-132">**Error details or message of the selected session**</span></span>  
 <span data-ttu-id="d6843-133">S'affiche uniquement si la session sélectionnée affiche une valeur **Erreur** dans la colonne **État** .</span><span class="sxs-lookup"><span data-stu-id="d6843-133">Is displayed only if the selected session displays a value of **Error** in the **Status** column.</span></span> <span data-ttu-id="d6843-134">La zone de texte affiche des informations d'erreur détaillées, ainsi que la commande émise au moment de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="d6843-134">This text area displays detailed error information and the command that was attempted at the time of the error.</span></span> <span data-ttu-id="d6843-135">Elle comporte également des liens vers des informations supplémentaires à propos de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="d6843-135">It also includes links to additional content related to the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6843-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6843-136">See Also</span></span>  
 <span data-ttu-id="d6843-137">[Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d6843-137">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="d6843-138">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="d6843-138">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="d6843-139">[Surveillance de la réplication](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d6843-139">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="d6843-140">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="d6843-140">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
