---
title: Informations sur le serveur de publication, liste de suivi des abonnements (publication transactionnelle, SQL Server 2005 et versions ultérieures) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.tran.f1
ms.assetid: 6bc64ddb-5c86-4681-a391-77fc1d3c4e6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bf6d151b75bca1dbfd2e5ad8f7601fb1002e84be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599890"
---
# <a name="publisher-information-subscription-watch-list-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="3e159-102">Informations sur le serveur de publication, Liste de suivi des abonnements (Publication transactionnelle, SQL Server 2005 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="3e159-102">Publisher Information, Subscription Watch List (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="3e159-103">L'onglet **Liste de suivi des abonnements** est disponible pour les serveurs de distribution qui exécutent SQL Server 2005 et les versions ultérieures. Il permet d'afficher des informations sur les abonnements depuis toutes les publications disponibles sur le serveur de publication sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3e159-103">The **Subscription Watch List** tab is available for Distributors running SQL Server 2005 and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="3e159-104">Vous pouvez filtrer la liste des abonnements pour identifier les erreurs, les avertissements et les abonnements qui ne fonctionnent pas correctement.</span><span class="sxs-lookup"><span data-stu-id="3e159-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="3e159-105">Cet onglet fournit à l'administrateur un emplacement central pour contrôler toute l'activité de réplication sur un serveur de publication : le Moniteur de réplication affiche tous les abonnements nécessitant une attention, en fonction du type de réplication sélectionné et de l'option choisie dans la zone de liste déroulante **Afficher** .</span><span class="sxs-lookup"><span data-stu-id="3e159-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="3e159-106">Du fait que les éléments affichés dans cet onglet reposent sur l'état et les performances actuelles, les abonnements sont affichés sur cette page uniquement s'ils correspondent à l'option actuelle de la zone de liste **Afficher** .</span><span class="sxs-lookup"><span data-stu-id="3e159-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3e159-107">Options</span><span class="sxs-lookup"><span data-stu-id="3e159-107">Options</span></span>  
 <span data-ttu-id="3e159-108">Pour plus d'informations et en savoir plus sur les tâches associées à un abonnement, cliquez avec le bouton droit de la souris sur la ligne de l'abonnement, puis cliquez sur une option dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="3e159-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="3e159-109">Pour modifier la façon dont la grille affiche les données, cliquez avec le bouton droit sur la grille, puis cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e159-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="3e159-110">**Trier**: cette option vous permet d'effectuer un tri sur ou plusieurs colonnes dans la boîte de dialogue **Trier les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="3e159-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="3e159-111">**Choisir les colonnes à afficher**: cette option vous permet de sélectionner les colonnes à afficher et l'ordre d'affichage dans la boîte de dialogue **Choisir les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="3e159-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="3e159-112">**Filtre**: cette option vous permet de filtrer les lignes dans la grille selon les valeurs de colonne dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="3e159-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="3e159-113">**Effacer le filtre**: cette option vous permet d'effacer tous les paramètres du filtre pour la grille.</span><span class="sxs-lookup"><span data-stu-id="3e159-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="3e159-114">Les paramètres du filtre sont spécifiques à chaque grille.</span><span class="sxs-lookup"><span data-stu-id="3e159-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="3e159-115">La sélection et le tri des colonnes sont appliqués à toutes les grilles du même type, par exemple la grille de publications pour chaque serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3e159-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="3e159-116">**Afficher les abonnements transactionnels**</span><span class="sxs-lookup"><span data-stu-id="3e159-116">**Show Transactional Subscriptions**</span></span>  
 <span data-ttu-id="3e159-117">Sélectionnez le type des abonnements (transactionnel, instantané ou fusion) à afficher pour le serveur de publication sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3e159-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="3e159-118">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="3e159-118">**Show**</span></span>  
 <span data-ttu-id="3e159-119">Sélectionnez les états d'abonnement à afficher pour le type d'abonnement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3e159-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="3e159-120">Par exemple, vous pouvez afficher uniquement les abonnements associés à une erreur.</span><span class="sxs-lookup"><span data-stu-id="3e159-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="3e159-121">**État**</span><span class="sxs-lookup"><span data-stu-id="3e159-121">**Status**</span></span>  
 <span data-ttu-id="3e159-122">État de chaque abonnement déterminé par l'état de l'Agent de distribution ou l'Agent de lecture du journal (la priorité la plus haute est affichée ; l'état peut être également déterminé par l'Agent de lecture de la file d'attente si des abonnements mis à jour en attente sont utilisés).</span><span class="sxs-lookup"><span data-stu-id="3e159-122">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="3e159-123">Par défaut, la grille qui contient des informations d'abonnement est triée en fonction de la colonne **État** (puis en fonction de la colonne **Performances** pour les abonnements ayant le même état).</span><span class="sxs-lookup"><span data-stu-id="3e159-123">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="3e159-124">La liste suivante contient toutes les valeurs d'état possibles et l'ordre de tri des valeurs (par exemple, les erreurs sont toujours affichées dans la partie supérieure de la grille).</span><span class="sxs-lookup"><span data-stu-id="3e159-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="3e159-125">Error</span><span class="sxs-lookup"><span data-stu-id="3e159-125">Error</span></span>  
  
-   <span data-ttu-id="3e159-126">Critique pour les performances</span><span class="sxs-lookup"><span data-stu-id="3e159-126">Performance critical</span></span>  
  
-   <span data-ttu-id="3e159-127">Expire bientôt/Expiré</span><span class="sxs-lookup"><span data-stu-id="3e159-127">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="3e159-128">Abonnement non initialisé</span><span class="sxs-lookup"><span data-stu-id="3e159-128">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="3e159-129">Nouvelle tentative de la commande qui a échoué</span><span class="sxs-lookup"><span data-stu-id="3e159-129">Retrying failed command</span></span>  
  
-   <span data-ttu-id="3e159-130">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="3e159-130">Not Running</span></span>  
  
-   <span data-ttu-id="3e159-131">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="3e159-131">Running</span></span>  
  
 <span data-ttu-id="3e159-132">L'ordre de tri détermine également la valeur affichée lorsqu'un abonnement a plusieurs états.</span><span class="sxs-lookup"><span data-stu-id="3e159-132">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="3e159-133">Si, par exemple, un abonnement a une erreur et expire bientôt, la colonne **État** affiche **Erreur**.</span><span class="sxs-lookup"><span data-stu-id="3e159-133">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="3e159-134">Les valeurs d'état **Critique pour les performances**, **Expire bientôt/Expiré**et **Abonnement non initialisé** sont des avertissements.</span><span class="sxs-lookup"><span data-stu-id="3e159-134">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="3e159-135">Lorsqu'un avertissement est affiché, la colonne **État** s'affiche également si un agent est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="3e159-135">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="3e159-136">Par exemple, l'état peut être **En cours d'exécution, Critique pour les performances**.</span><span class="sxs-lookup"><span data-stu-id="3e159-136">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="3e159-137">Les valeurs d'état **Critique pour les performances** et **Expire bientôt/Expiré** s'affichent uniquement si des seuils sont définis.</span><span class="sxs-lookup"><span data-stu-id="3e159-137">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="3e159-138">Pour plus d’informations sur les mesures de performances et sur la définition des seuils, consultez [Analyser les performances avec le Moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md) et [Définir des seuils et des avertissements dans le Moniteur de réplication](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="3e159-138">For information about performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="3e159-139">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="3e159-139">**Subscription**</span></span>  
 <span data-ttu-id="3e159-140">Nom de chaque abonnement, au format : *NomAbonné: NomBaseDonnéesAbonnements*.</span><span class="sxs-lookup"><span data-stu-id="3e159-140">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="3e159-141">**Publication**</span><span class="sxs-lookup"><span data-stu-id="3e159-141">**Publication**</span></span>  
 <span data-ttu-id="3e159-142">Nom de la publication avec laquelle un abonnement se synchronise, au format : *NomBaseDonnéesPublication: NomPublication*.</span><span class="sxs-lookup"><span data-stu-id="3e159-142">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="3e159-143">**Performances**</span><span class="sxs-lookup"><span data-stu-id="3e159-143">**Performance**</span></span>  
 <span data-ttu-id="3e159-144">La valeur de performance de chaque abonnement est basée sur les dernières mesures relevées par le Moniteur de réplication et n'affecte pas les performances historiques.</span><span class="sxs-lookup"><span data-stu-id="3e159-144">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="3e159-145">Les performances sont mesurées pour les abonnements aux publications ayant des seuils définis. Si des seuils de performances ne sont pas définis pour une publication, cette colonne contient **Non activé**.</span><span class="sxs-lookup"><span data-stu-id="3e159-145">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="3e159-146">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e159-146">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="3e159-147">Excellent</span><span class="sxs-lookup"><span data-stu-id="3e159-147">Excellent</span></span>  
  
-   <span data-ttu-id="3e159-148">Bonne</span><span class="sxs-lookup"><span data-stu-id="3e159-148">Good</span></span>  
  
-   <span data-ttu-id="3e159-149">Correcte</span><span class="sxs-lookup"><span data-stu-id="3e159-149">Fair</span></span>  
  
-   <span data-ttu-id="3e159-150">Médiocre</span><span class="sxs-lookup"><span data-stu-id="3e159-150">Poor</span></span>  
  
-   <span data-ttu-id="3e159-151">Critique</span><span class="sxs-lookup"><span data-stu-id="3e159-151">Critical</span></span>  
  
 <span data-ttu-id="3e159-152">Si les performances sont critiques, **Critique pour les performances** figure dans la colonne **État** .</span><span class="sxs-lookup"><span data-stu-id="3e159-152">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="3e159-153">Pour plus d’informations sur la définition des indices et des seuils de performances, consultez [Analyser les performances avec le Moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="3e159-153">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="3e159-154">**Latence**</span><span class="sxs-lookup"><span data-stu-id="3e159-154">**Latency**</span></span>  
 <span data-ttu-id="3e159-155">Délai moyen qui s'écoule entre la validation d'une transaction sur le serveur de publication et la validation de la transaction correspondante au niveau de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="3e159-155">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="3e159-156">La latence affichée est basée sur les dernières mesures relevées par le Moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="3e159-156">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="3e159-157">Pour plus d’informations sur la mesure de la latence, consultez [Mesurer la latence et valider les connexions pour la réplication transactionnelle](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="3e159-157">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="3e159-158">**Dernière synchronisation**</span><span class="sxs-lookup"><span data-stu-id="3e159-158">**Last Synchronization**</span></span>  
 <span data-ttu-id="3e159-159">Heure de la dernière exécution de l'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="3e159-159">The time when the Distribution Agent last ran.</span></span> <span data-ttu-id="3e159-160">Si la synchronisation est en cours, **Opération en cours** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="3e159-160">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e159-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e159-161">See Also</span></span>  
 <span data-ttu-id="3e159-162">[Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="3e159-162">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="3e159-163">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="3e159-163">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="3e159-164">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="3e159-164">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
