---
title: Informations de publication, Agents (Publication de fusion) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.downlevelagents.merge.f1
ms.assetid: 73ff590a-20da-4f10-b592-c60b7226d22b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8562a24066efd7cdad01f5559e97d8493a0f73a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600797"
---
# <a name="publication-information-agents-merge-publication"></a><span data-ttu-id="79710-102">Informations de publication, Agents (Publication de fusion)</span><span class="sxs-lookup"><span data-stu-id="79710-102">Publication Information, Agents (Merge Publication)</span></span>
  <span data-ttu-id="79710-103">L'onglet **Agents** contient des informations résumées sur l'Agent d'instantané de la publication sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="79710-103">The **Agents** tab displays summary information on the Snapshot Agent for the selected publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="79710-104">Options</span><span class="sxs-lookup"><span data-stu-id="79710-104">Options</span></span>  
 <span data-ttu-id="79710-105">Pour plus d'informations et en savoir plus sur les tâches associées à l'Agent d'instantané, cliquez avec le bouton droit de la souris sur l'Agent, puis cliquez sur une option dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="79710-105">For more detailed information and tasks related to the Snapshot Agent, right-click the row for the agent, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="79710-106">Pour modifier la façon dont la grille affiche les données, cliquez avec le bouton droit sur la grille, puis cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="79710-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="79710-107">**Trier**: cette option vous permet d'effectuer un tri sur ou plusieurs colonnes dans la boîte de dialogue **Trier les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="79710-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="79710-108">**Choisir les colonnes à afficher**: cette option vous permet de sélectionner les colonnes à afficher et l'ordre d'affichage dans la boîte de dialogue **Choisir les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="79710-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="79710-109">**Filtre**: cette option vous permet de filtrer les lignes dans la grille selon les valeurs de colonne dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="79710-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="79710-110">**Effacer le filtre**: cette option vous permet d'effacer tous les paramètres du filtre pour la grille.</span><span class="sxs-lookup"><span data-stu-id="79710-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="79710-111">Les paramètres du filtre sont spécifiques à chaque grille.</span><span class="sxs-lookup"><span data-stu-id="79710-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="79710-112">La sélection et le tri des colonnes sont appliqués à toutes les grilles du même type, par exemple la grille de publications pour chaque serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="79710-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="79710-113">**État**</span><span class="sxs-lookup"><span data-stu-id="79710-113">**Status**</span></span>  
 <span data-ttu-id="79710-114">État de l'Agent d'instantané.</span><span class="sxs-lookup"><span data-stu-id="79710-114">The status of the Snapshot Agent.</span></span> <span data-ttu-id="79710-115">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="79710-115">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="79710-116">Error</span><span class="sxs-lookup"><span data-stu-id="79710-116">Error</span></span>  
  
-   <span data-ttu-id="79710-117">Nouvelle tentative de la commande qui a échoué</span><span class="sxs-lookup"><span data-stu-id="79710-117">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="79710-118">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="79710-118">Not running</span></span>  
  
-   <span data-ttu-id="79710-119">Completed</span><span class="sxs-lookup"><span data-stu-id="79710-119">Completed</span></span>  
  
 <span data-ttu-id="79710-120">**Agent**</span><span class="sxs-lookup"><span data-stu-id="79710-120">**Agent**</span></span>  
 <span data-ttu-id="79710-121">L'Agent d'instantané.</span><span class="sxs-lookup"><span data-stu-id="79710-121">The Snapshot Agent.</span></span> <span data-ttu-id="79710-122">Il s'agit du seul Agent associé à une publication de fusion.</span><span class="sxs-lookup"><span data-stu-id="79710-122">This is the only agent associated with a merge publication.</span></span> <span data-ttu-id="79710-123">L'Agent de fusion est associé aux abonnements à cette publication.</span><span class="sxs-lookup"><span data-stu-id="79710-123">The Merge Agent is associated with subscriptions to this publication.</span></span> <span data-ttu-id="79710-124">Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="79710-124">For more information, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="79710-125">**Dernière heure de début**</span><span class="sxs-lookup"><span data-stu-id="79710-125">**Last Start Time**</span></span>  
 <span data-ttu-id="79710-126">Heure du dernier démarrage de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="79710-126">The last time the agent started.</span></span>  
  
 <span data-ttu-id="79710-127">**Durée**</span><span class="sxs-lookup"><span data-stu-id="79710-127">**Duration**</span></span>  
 <span data-ttu-id="79710-128">Durée d'exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="79710-128">The amount of time the agent has run.</span></span> <span data-ttu-id="79710-129">La durée correspond au délai écoulé si l'Agent est actif ou au délai total si l'Agent a déjà été exécuté.</span><span class="sxs-lookup"><span data-stu-id="79710-129">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="79710-130">**Dernière action**</span><span class="sxs-lookup"><span data-stu-id="79710-130">**Last Action**</span></span>  
 <span data-ttu-id="79710-131">La dernière action effectuée au cours de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="79710-131">The last action performed during the most recent run of the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79710-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79710-132">See Also</span></span>  
 <span data-ttu-id="79710-133">[Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="79710-133">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="79710-134">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="79710-134">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="79710-135">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="79710-135">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
