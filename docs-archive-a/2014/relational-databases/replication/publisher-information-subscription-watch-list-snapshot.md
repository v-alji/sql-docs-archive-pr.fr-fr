---
title: Informations sur le serveur de publication, liste de suivi des abonnements (publication d’instantané, SQL Server 2005 et versions ultérieures) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.snapshot.f1
ms.assetid: 2ebeee62-7f54-4c77-9d37-15708bc5cc23
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ea44958c81465570c036ab7dd83247fb55652f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701051"
---
# <a name="publisher-information-subscription-watch-list-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="f296d-102">Informations du serveur de publication, Liste de suivi des abonnements (Publication d'instantanés, SQL Server 2005 et ultérieure)</span><span class="sxs-lookup"><span data-stu-id="f296d-102">Publisher Information, Subscription Watch List (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="f296d-103"> L’onglet **Liste de suivi des abonnements** est disponible pour les serveurs de distribution qui exécutent [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et les versions ultérieures. Il permet d’afficher des informations sur les abonnements depuis toutes les publications disponibles sur le serveur de publication sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f296d-103">The **Subscription Watch List** tab is available for Distributors running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="f296d-104">Vous pouvez filtrer la liste des abonnements pour identifier les erreurs, les avertissements et les abonnements qui ne fonctionnent pas correctement.</span><span class="sxs-lookup"><span data-stu-id="f296d-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="f296d-105">Cet onglet fournit à l'administrateur un emplacement central pour contrôler toute l'activité de réplication sur un serveur de publication : le Moniteur de réplication affiche tous les abonnements nécessitant une attention, en fonction du type de réplication sélectionné et de l'option choisie dans la zone de liste déroulante **Afficher** .</span><span class="sxs-lookup"><span data-stu-id="f296d-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="f296d-106">Du fait que les éléments affichés dans cet onglet reposent sur l'état et les performances actuelles, les abonnements sont affichés sur cette page uniquement s'ils correspondent à l'option actuelle de la zone de liste **Afficher** .</span><span class="sxs-lookup"><span data-stu-id="f296d-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f296d-107">Options</span><span class="sxs-lookup"><span data-stu-id="f296d-107">Options</span></span>  
 <span data-ttu-id="f296d-108">Pour plus d'informations et en savoir plus sur les tâches associées à un abonnement, cliquez avec le bouton droit de la souris sur la ligne de l'abonnement, puis cliquez sur une option dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="f296d-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="f296d-109">Pour modifier la façon dont la grille affiche les données, cliquez avec le bouton droit sur la grille, puis cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f296d-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="f296d-110">**Trier**: cette option vous permet d'effectuer un tri sur ou plusieurs colonnes dans la boîte de dialogue **Trier les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="f296d-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="f296d-111">**Choisir les colonnes à afficher**: cette option vous permet de sélectionner les colonnes à afficher et l'ordre d'affichage dans la boîte de dialogue **Choisir les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="f296d-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="f296d-112">**Filtre**: cette option vous permet de filtrer les lignes dans la grille selon les valeurs de colonne dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="f296d-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="f296d-113">**Effacer le filtre**: cette option vous permet d'effacer tous les paramètres du filtre pour la grille.</span><span class="sxs-lookup"><span data-stu-id="f296d-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="f296d-114">Les paramètres du filtre sont spécifiques à chaque grille.</span><span class="sxs-lookup"><span data-stu-id="f296d-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="f296d-115">La sélection et le tri des colonnes sont appliqués à toutes les grilles du même type, par exemple la grille de publications pour chaque serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="f296d-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="f296d-116">**Afficher les abonnements aux instantanés**</span><span class="sxs-lookup"><span data-stu-id="f296d-116">**Show Snapshot Subscriptions**</span></span>  
 <span data-ttu-id="f296d-117">Sélectionnez le type des abonnements (transactionnel, instantané ou fusion) à afficher pour le serveur de publication sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f296d-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="f296d-118">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="f296d-118">**Show**</span></span>  
 <span data-ttu-id="f296d-119">Sélectionnez les états d'abonnement à afficher pour le type d'abonnement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f296d-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="f296d-120">Par exemple, vous pouvez afficher uniquement les abonnements associés à une erreur.</span><span class="sxs-lookup"><span data-stu-id="f296d-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="f296d-121">**État**</span><span class="sxs-lookup"><span data-stu-id="f296d-121">**Status**</span></span>  
 <span data-ttu-id="f296d-122">État de chaque abonnement, déterminé par l'état de l'Agent d'instantané ou l'Agent de distribution (la priorité d'état la plus haute est affichée).</span><span class="sxs-lookup"><span data-stu-id="f296d-122">The status of each subscription, which is determined by the status of the Snapshot Agent or the Distribution Agent (the higher priority status is displayed).</span></span>  
  
 <span data-ttu-id="f296d-123">Par défaut, la grille qui contient des informations d'abonnement est triée en fonction de la colonne **État** .</span><span class="sxs-lookup"><span data-stu-id="f296d-123">By default, the grid containing subscription information is sorted by the **Status** column.</span></span> <span data-ttu-id="f296d-124">La liste suivante contient toutes les valeurs d'état possibles et l'ordre de tri des valeurs (par exemple, les erreurs sont toujours affichées dans la partie supérieure de la grille).</span><span class="sxs-lookup"><span data-stu-id="f296d-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="f296d-125">Error</span><span class="sxs-lookup"><span data-stu-id="f296d-125">Error</span></span>  
  
-   <span data-ttu-id="f296d-126">Expire bientôt/Expiré</span><span class="sxs-lookup"><span data-stu-id="f296d-126">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="f296d-127">Abonnement non initialisé</span><span class="sxs-lookup"><span data-stu-id="f296d-127">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="f296d-128">Nouvelle tentative de la commande qui a échoué</span><span class="sxs-lookup"><span data-stu-id="f296d-128">Retrying failed command</span></span>  
  
-   <span data-ttu-id="f296d-129">Synchronisation</span><span class="sxs-lookup"><span data-stu-id="f296d-129">Synchronizing</span></span>  
  
-   <span data-ttu-id="f296d-130">Sans synchronisation</span><span class="sxs-lookup"><span data-stu-id="f296d-130">Not synchronizing</span></span>  
  
 <span data-ttu-id="f296d-131">L'ordre de tri détermine également la valeur affichée lorsqu'un abonnement a plusieurs états.</span><span class="sxs-lookup"><span data-stu-id="f296d-131">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="f296d-132">Si, par exemple, un abonnement a une erreur et expire bientôt, la colonne **État** affiche **Erreur**.</span><span class="sxs-lookup"><span data-stu-id="f296d-132">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="f296d-133">Les valeurs d'état **Expire bientôt/Expiré** et **Abonnement non initialisé** sont des avertissements.</span><span class="sxs-lookup"><span data-stu-id="f296d-133">The status values **Expiring soon/Expired** and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="f296d-134">Lorsqu'un avertissement est affiché, la colonne **État** s'affiche également si un agent est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="f296d-134">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="f296d-135">Par exemple, l'état peut être **En cours d'exécution, Expire bientôt/Expiré**.</span><span class="sxs-lookup"><span data-stu-id="f296d-135">For example, the status could be **Running, Expiring soon/Expired**.</span></span>  
  
 <span data-ttu-id="f296d-136">La valeur d'état **Expire bientôt/Expiré** s'affiche uniquement si un seuil est défini.</span><span class="sxs-lookup"><span data-stu-id="f296d-136">The status value **Expiring soon/Expired** is displayed only if a threshold is set.</span></span> <span data-ttu-id="f296d-137">Pour plus d’informations sur la définition des seuils, consultez [Définir des seuils et des avertissements dans le Moniteur de réplication](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="f296d-137">For information on setting thresholds, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="f296d-138">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="f296d-138">**Subscription**</span></span>  
 <span data-ttu-id="f296d-139">Nom de chaque abonnement, au format : *NomAbonné: NomBaseDonnéesAbonnements*.</span><span class="sxs-lookup"><span data-stu-id="f296d-139">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="f296d-140">**Publication**</span><span class="sxs-lookup"><span data-stu-id="f296d-140">**Publication**</span></span>  
 <span data-ttu-id="f296d-141">Nom de la publication avec laquelle un abonnement se synchronise, au format : *NomBaseDonnéesPublication: NomPublication*.</span><span class="sxs-lookup"><span data-stu-id="f296d-141">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="f296d-142">**Dernière synchronisation**</span><span class="sxs-lookup"><span data-stu-id="f296d-142">**Last Synchronization**</span></span>  
 <span data-ttu-id="f296d-143">Heure de la dernière exécution de l'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="f296d-143">The time at which the Distribution Agent last ran.</span></span> <span data-ttu-id="f296d-144">Si la synchronisation est en cours, **Opération en cours** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f296d-144">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f296d-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f296d-145">See Also</span></span>  
 <span data-ttu-id="f296d-146">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f296d-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="f296d-147">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="f296d-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="f296d-148">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="f296d-148">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
