---
title: Informations de publication, Agents (Publication transactionnelle) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.downlevelagents.tran.f1
ms.assetid: 38ef2f54-53bb-4053-876d-86f8f06a4519
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1a3d50da15ea653a7911e65ad888d5997f47a3f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600792"
---
# <a name="publication-information-agents-transactional-publication"></a><span data-ttu-id="c9546-102">Informations de publication, Agents (Publication transactionnelle)</span><span class="sxs-lookup"><span data-stu-id="c9546-102">Publication Information, Agents (Transactional Publication)</span></span>
  <span data-ttu-id="c9546-103"> L’onglet **Agents** contient des informations récapitulatives sur les agents de la publication sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c9546-103">The **Agents** tab displays summary information on the agents for the selected publication.</span></span> <span data-ttu-id="c9546-104">Les informations sur l'Agent d'instantané et sur l'Agent de lecture du journal s'affichent pour toutes les publications transactionnelles.</span><span class="sxs-lookup"><span data-stu-id="c9546-104">Information on the Snapshot Agent and Log Reader Agent is displayed for all transactional publications.</span></span> <span data-ttu-id="c9546-105">Les informations sur l'Agent de lecture de la file d'attente s'affichent pour les publications transactionnelles qui ont des abonnements mis à jour en file d'attente.</span><span class="sxs-lookup"><span data-stu-id="c9546-105">Information on the Queue Reader Agent is displayed for those transactional publications that are enabled for queued updating subscriptions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9546-106">Options</span><span class="sxs-lookup"><span data-stu-id="c9546-106">Options</span></span>  
 <span data-ttu-id="c9546-107">Pour plus d'informations et en savoir plus sur les tâches associées à un agent, cliquez avec le bouton droit de la souris sur la ligne de l'Agent, puis cliquez sur une option dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="c9546-107">For more detailed information and tasks related to an agent, right-click the row for that agent, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="c9546-108">Pour modifier la façon dont la grille affiche les données, cliquez avec le bouton droit sur la grille, puis cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c9546-108">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="c9546-109">**Trier**: cette option vous permet d'effectuer un tri sur ou plusieurs colonnes dans la boîte de dialogue **Trier les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="c9546-109">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="c9546-110">**Choisir les colonnes à afficher**: cette option vous permet de sélectionner les colonnes à afficher et l'ordre d'affichage dans la boîte de dialogue **Choisir les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="c9546-110">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="c9546-111">**Filtre**: cette option vous permet de filtrer les lignes dans la grille selon les valeurs de colonne dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="c9546-111">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="c9546-112">**Effacer le filtre**: cette option vous permet d'effacer tous les paramètres du filtre pour la grille.</span><span class="sxs-lookup"><span data-stu-id="c9546-112">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="c9546-113">Les paramètres du filtre sont spécifiques à chaque grille.</span><span class="sxs-lookup"><span data-stu-id="c9546-113">Filter settings are specific to each grid.</span></span> <span data-ttu-id="c9546-114">La sélection et le tri des colonnes sont appliqués à toutes les grilles du même type, par exemple la grille de publications pour chaque serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="c9546-114">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="c9546-115">**État**</span><span class="sxs-lookup"><span data-stu-id="c9546-115">**Status**</span></span>  
 <span data-ttu-id="c9546-116">État de chaque agent de réplication associé à la publication.</span><span class="sxs-lookup"><span data-stu-id="c9546-116">The status of each replication agent associated with the publication.</span></span> <span data-ttu-id="c9546-117">La liste ci-dessous indique les valeurs d'état possibles :</span><span class="sxs-lookup"><span data-stu-id="c9546-117">The following list shows the possible status values:</span></span>  
  
-   <span data-ttu-id="c9546-118">Error</span><span class="sxs-lookup"><span data-stu-id="c9546-118">Error</span></span>  
  
-   <span data-ttu-id="c9546-119">Nouvelle tentative de la commande qui a échoué</span><span class="sxs-lookup"><span data-stu-id="c9546-119">Retrying failed commands</span></span>  
  
-   <span data-ttu-id="c9546-120">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="c9546-120">Not running</span></span>  
  
-   <span data-ttu-id="c9546-121">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="c9546-121">Running</span></span>  
  
-   <span data-ttu-id="c9546-122">Completed</span><span class="sxs-lookup"><span data-stu-id="c9546-122">Completed</span></span>  
  
 <span data-ttu-id="c9546-123">**Agent**</span><span class="sxs-lookup"><span data-stu-id="c9546-123">**Agent**</span></span>  
 <span data-ttu-id="c9546-124">Nom de chaque agent de réplication associé à la publication.</span><span class="sxs-lookup"><span data-stu-id="c9546-124">The name of each replication agent associated with the publication.</span></span> <span data-ttu-id="c9546-125">L'Agent de distribution est associé aux abonnements à cette publication.</span><span class="sxs-lookup"><span data-stu-id="c9546-125">The Distribution Agent is associated with subscriptions to this publication.</span></span> <span data-ttu-id="c9546-126">Pour plus d’informations, consultez [Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="c9546-126">For more information, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="c9546-127">**Dernière heure de début**</span><span class="sxs-lookup"><span data-stu-id="c9546-127">**Last Start Time**</span></span>  
 <span data-ttu-id="c9546-128">Heure du dernier démarrage de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="c9546-128">The last time the agent started.</span></span>  
  
 <span data-ttu-id="c9546-129">**Durée**</span><span class="sxs-lookup"><span data-stu-id="c9546-129">**Duration**</span></span>  
 <span data-ttu-id="c9546-130">Durée d'exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="c9546-130">The amount of time the agent has run.</span></span> <span data-ttu-id="c9546-131">La durée correspond au délai écoulé si l'Agent est actif ou au délai total si l'Agent a déjà été exécuté.</span><span class="sxs-lookup"><span data-stu-id="c9546-131">The time represents elapsed time if the agent is currently running and total time if the agent has run previously.</span></span>  
  
 <span data-ttu-id="c9546-132">**Dernière action**</span><span class="sxs-lookup"><span data-stu-id="c9546-132">**Last Action**</span></span>  
 <span data-ttu-id="c9546-133">La dernière action effectuée au cours de la dernière exécution de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="c9546-133">The last action performed during the most recent run of the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9546-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9546-134">See Also</span></span>  
 <span data-ttu-id="c9546-135">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c9546-135">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="c9546-136">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c9546-136">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="c9546-137">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="c9546-137">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
