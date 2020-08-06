---
title: Informations de publication, Tous les abonnements (Publication d’instantané) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.allsubscriptions.snapshot.f1
ms.assetid: 7ce656c2-6e60-4625-8955-1daff641070c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 75eb85adae46481ddd4360f095c00060af5677fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610609"
---
# <a name="publication-information-all-subscriptions-snapshot-publication"></a><span data-ttu-id="4e46e-102">Informations de publication, Tous les abonnements (Publication d'instantané)</span><span class="sxs-lookup"><span data-stu-id="4e46e-102">Publication Information, All Subscriptions (Snapshot Publication)</span></span>
  <span data-ttu-id="4e46e-103">L'onglet **Tous les abonnements** contient des informations sur tous les abonnements à la publication d'instantané sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4e46e-103">The **All Subscriptions** tab displays information on all subscriptions to the selected snapshot publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4e46e-104">Options</span><span class="sxs-lookup"><span data-stu-id="4e46e-104">Options</span></span>  
 <span data-ttu-id="4e46e-105">Pour plus d'informations et en savoir plus sur les tâches associées à un abonnement, cliquez avec le bouton droit de la souris sur la ligne de l'abonnement, puis cliquez sur une option dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="4e46e-105">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="4e46e-106">Pour modifier la façon dont la grille affiche les données, cliquez avec le bouton droit sur la grille, puis cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e46e-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="4e46e-107">**Trier**: cette option vous permet d'effectuer un tri sur ou plusieurs colonnes dans la boîte de dialogue **Trier les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="4e46e-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="4e46e-108">**Choisir les colonnes à afficher**: cette option vous permet de sélectionner les colonnes à afficher et l'ordre d'affichage dans la boîte de dialogue **Choisir les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="4e46e-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="4e46e-109">**Filtre**: cette option vous permet de filtrer les lignes dans la grille selon les valeurs de colonne dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="4e46e-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="4e46e-110">**Effacer le filtre**: cette option vous permet d'effacer tous les paramètres du filtre pour la grille.</span><span class="sxs-lookup"><span data-stu-id="4e46e-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="4e46e-111">Les paramètres du filtre sont spécifiques à chaque grille.</span><span class="sxs-lookup"><span data-stu-id="4e46e-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="4e46e-112">La sélection et le tri des colonnes sont appliqués à toutes les grilles du même type, par exemple la grille de publications pour chaque serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="4e46e-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="4e46e-113">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="4e46e-113">**Show**</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="4e46e-114">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures uniquement.</span><span class="sxs-lookup"><span data-stu-id="4e46e-114">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="4e46e-115">Sélectionnez les états d'abonnement à afficher pour le type d'abonnement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4e46e-115">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="4e46e-116">Par exemple, vous pouvez afficher uniquement les abonnements associés à une erreur.</span><span class="sxs-lookup"><span data-stu-id="4e46e-116">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="4e46e-117">**État**</span><span class="sxs-lookup"><span data-stu-id="4e46e-117">**Status**</span></span>  
 <span data-ttu-id="4e46e-118">État de chaque abonnement, déterminé par l'état de l'Agent d'instantané ou l'Agent de distribution (la priorité d'état la plus haute est affichée).</span><span class="sxs-lookup"><span data-stu-id="4e46e-118">The status of each subscription, which is determined by the status of the Snapshot Agent or the Distribution Agent (the higher priority status is displayed).</span></span>  
  
 <span data-ttu-id="4e46e-119">Par défaut, la grille qui contient des informations d'abonnement est triée en fonction de la colonne **État** .</span><span class="sxs-lookup"><span data-stu-id="4e46e-119">By default, the grid containing subscription information is sorted by the **Status** column.</span></span> <span data-ttu-id="4e46e-120">La liste suivante contient toutes les valeurs d'état possibles et l'ordre de tri des valeurs (par exemple, les erreurs sont toujours affichées dans la partie supérieure de la grille).</span><span class="sxs-lookup"><span data-stu-id="4e46e-120">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="4e46e-121">Error</span><span class="sxs-lookup"><span data-stu-id="4e46e-121">Error</span></span>  
  
-   <span data-ttu-id="4e46e-122">Expire bientôt/Expiré ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures uniquement)</span><span class="sxs-lookup"><span data-stu-id="4e46e-122">Expiring soon/Expired ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="4e46e-123">Abonnement non initialisé ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures uniquement)</span><span class="sxs-lookup"><span data-stu-id="4e46e-123">Uninitialized subscription ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="4e46e-124">Nouvelle tentative de la commande qui a échoué</span><span class="sxs-lookup"><span data-stu-id="4e46e-124">Retrying failed command</span></span>  
  
-   <span data-ttu-id="4e46e-125">Synchronisation</span><span class="sxs-lookup"><span data-stu-id="4e46e-125">Synchronizing</span></span>  
  
-   <span data-ttu-id="4e46e-126">Sans synchronisation</span><span class="sxs-lookup"><span data-stu-id="4e46e-126">Not synchronizing</span></span>  
  
 <span data-ttu-id="4e46e-127">L'ordre de tri détermine également la valeur affichée lorsqu'un abonnement a plusieurs états.</span><span class="sxs-lookup"><span data-stu-id="4e46e-127">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="4e46e-128">Si, par exemple, un abonnement a une erreur et expire bientôt, la colonne **État** affiche **Erreur**.</span><span class="sxs-lookup"><span data-stu-id="4e46e-128">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="4e46e-129">Les valeurs d'état **Expire bientôt/Expiré** et **Abonnement non initialisé** sont des avertissements.</span><span class="sxs-lookup"><span data-stu-id="4e46e-129">The status values **Expiring soon/Expired** and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="4e46e-130">Lorsqu'un avertissement est affiché, la colonne **État** s'affiche également si un agent est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="4e46e-130">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="4e46e-131">Par exemple, l'état peut être **En cours d'exécution, Expire bientôt/Expiré**.</span><span class="sxs-lookup"><span data-stu-id="4e46e-131">For example, the status could be **Running, Expiring soon/Expired**.</span></span>  
  
 <span data-ttu-id="4e46e-132">La valeur d'état **Expire bientôt/Expiré** s'affiche uniquement si un seuil est défini.</span><span class="sxs-lookup"><span data-stu-id="4e46e-132">The status value **Expiring soon/Expired** is displayed only if a threshold is set.</span></span> <span data-ttu-id="4e46e-133">Pour plus d’informations sur la définition des seuils, consultez [Définir des seuils et des avertissements dans le Moniteur de réplication](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="4e46e-133">For information on setting thresholds, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="4e46e-134">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="4e46e-134">**Subscription**</span></span>  
 <span data-ttu-id="4e46e-135">Nom de chaque abonnement, au format : *NomAbonné: NomBaseDonnéesAbonnements*.</span><span class="sxs-lookup"><span data-stu-id="4e46e-135">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="4e46e-136">**Dernière synchronisation**</span><span class="sxs-lookup"><span data-stu-id="4e46e-136">**Last Synchronization**</span></span>  
 <span data-ttu-id="4e46e-137">Heure de la dernière exécution de l'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="4e46e-137">The time at which the Distribution Agent last ran.</span></span> <span data-ttu-id="4e46e-138">Si la synchronisation est en cours, **Opération en cours** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="4e46e-138">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e46e-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e46e-139">See Also</span></span>  
 <span data-ttu-id="4e46e-140">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4e46e-140">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="4e46e-141">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4e46e-141">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="4e46e-142">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="4e46e-142">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
