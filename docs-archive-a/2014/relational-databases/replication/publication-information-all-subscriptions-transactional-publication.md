---
title: Informations de publication, Tous les abonnements (Publication transactionnelle) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.allsubscriptions.tran.f1
ms.assetid: 7073350c-f667-4f70-88e9-152c9a1b08dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ccc34bbe0933f4558478bd1d8276898219016e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602076"
---
# <a name="publication-information-all-subscriptions-transactional-publication"></a><span data-ttu-id="3124a-102">Informations de publication, Tous les abonnements (Publication transactionnelle)</span><span class="sxs-lookup"><span data-stu-id="3124a-102">Publication Information, All Subscriptions (Transactional Publication)</span></span>
  <span data-ttu-id="3124a-103"> L’onglet **Tous les abonnements** contient des informations sur tous les abonnements à la publication transactionnelle sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3124a-103">The **All Subscriptions** tab displays information on all subscriptions to the selected transactional publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3124a-104">Options</span><span class="sxs-lookup"><span data-stu-id="3124a-104">Options</span></span>  
 <span data-ttu-id="3124a-105">Pour plus d'informations et en savoir plus sur les tâches associées à un abonnement, cliquez avec le bouton droit de la souris sur la ligne de l'abonnement, puis cliquez sur une option dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="3124a-105">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="3124a-106">Pour modifier la façon dont la grille affiche les données, cliquez avec le bouton droit sur la grille, puis cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="3124a-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="3124a-107">**Trier**: cette option vous permet d'effectuer un tri sur ou plusieurs colonnes dans la boîte de dialogue **Trier les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="3124a-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="3124a-108">**Choisir les colonnes à afficher**: cette option vous permet de sélectionner les colonnes à afficher et l'ordre d'affichage dans la boîte de dialogue **Choisir les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="3124a-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="3124a-109">**Filtre**: cette option vous permet de filtrer les lignes dans la grille selon les valeurs de colonne dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="3124a-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="3124a-110">**Effacer le filtre**: cette option vous permet d'effacer tous les paramètres du filtre pour la grille.</span><span class="sxs-lookup"><span data-stu-id="3124a-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="3124a-111">Les paramètres du filtre sont spécifiques à chaque grille.</span><span class="sxs-lookup"><span data-stu-id="3124a-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="3124a-112">La sélection et le tri des colonnes sont appliqués à toutes les grilles du même type, par exemple la grille de publications pour chaque serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="3124a-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="3124a-113">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="3124a-113">**Show**</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="3124a-114">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures uniquement.</span><span class="sxs-lookup"><span data-stu-id="3124a-114">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="3124a-115">Sélectionnez les états d'abonnement à afficher pour le type d'abonnement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3124a-115">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="3124a-116">Par exemple, vous pouvez afficher uniquement les abonnements associés à une erreur.</span><span class="sxs-lookup"><span data-stu-id="3124a-116">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="3124a-117">**État**</span><span class="sxs-lookup"><span data-stu-id="3124a-117">**Status**</span></span>  
 <span data-ttu-id="3124a-118">État de chaque abonnement déterminé par l'état de l'Agent de distribution ou l'Agent de lecture du journal (la priorité la plus haute est affichée ; l'état peut être également déterminé par l'Agent de lecture de la file d'attente si des abonnements mis à jour en attente sont utilisés).</span><span class="sxs-lookup"><span data-stu-id="3124a-118">The status of each subscription, which is determined by the status of the Distribution Agent or the Log Reader Agent (the higher priority status is displayed; the status can also be determined by the Queue Reader Agent if queued updating subscriptions are used).</span></span>  
  
 <span data-ttu-id="3124a-119">Par défaut, la grille qui contient des informations d'abonnement est triée en fonction de la colonne **État** (puis en fonction de la colonne **Performances** pour les abonnements ayant le même état).</span><span class="sxs-lookup"><span data-stu-id="3124a-119">By default, the grid containing subscription information is sorted by the **Status** column (and then sorted by the **Performance** column for those subscriptions with the same status).</span></span> <span data-ttu-id="3124a-120">La liste suivante contient toutes les valeurs d'état possibles et l'ordre de tri des valeurs (par exemple, les erreurs sont toujours affichées dans la partie supérieure de la grille).</span><span class="sxs-lookup"><span data-stu-id="3124a-120">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="3124a-121">Error</span><span class="sxs-lookup"><span data-stu-id="3124a-121">Error</span></span>  
  
-   <span data-ttu-id="3124a-122">Critique pour les performances ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures uniquement)</span><span class="sxs-lookup"><span data-stu-id="3124a-122">Performance critical ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="3124a-123">Expire bientôt/Expiré ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures uniquement)</span><span class="sxs-lookup"><span data-stu-id="3124a-123">Expiring soon/Expired ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="3124a-124">Abonnement non initialisé ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures uniquement)</span><span class="sxs-lookup"><span data-stu-id="3124a-124">Uninitialized subscription ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="3124a-125">Nouvelle tentative de la commande qui a échoué</span><span class="sxs-lookup"><span data-stu-id="3124a-125">Retrying failed command</span></span>  
  
-   <span data-ttu-id="3124a-126">Non exécuté</span><span class="sxs-lookup"><span data-stu-id="3124a-126">Not Running</span></span>  
  
-   <span data-ttu-id="3124a-127">Exécution en cours</span><span class="sxs-lookup"><span data-stu-id="3124a-127">Running</span></span>  
  
 <span data-ttu-id="3124a-128">L'ordre de tri détermine également la valeur affichée lorsqu'un abonnement a plusieurs états.</span><span class="sxs-lookup"><span data-stu-id="3124a-128">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="3124a-129">Si, par exemple, un abonnement a une erreur et expire bientôt, la colonne **État** affiche **Erreur**.</span><span class="sxs-lookup"><span data-stu-id="3124a-129">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="3124a-130">Les valeurs d'état **Critique pour les performances**, **Expire bientôt/Expiré**et **Abonnement non initialisé** sont des avertissements.</span><span class="sxs-lookup"><span data-stu-id="3124a-130">The status values **Performance critical**, **Expiring soon/Expired**, and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="3124a-131">Lorsqu'un avertissement est affiché, la colonne **État** s'affiche également si un agent est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="3124a-131">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="3124a-132">Par exemple, l'état peut être **En cours d'exécution, Critique pour les performances**.</span><span class="sxs-lookup"><span data-stu-id="3124a-132">For example, the status could be **Running, Performance critical**.</span></span>  
  
 <span data-ttu-id="3124a-133">Les valeurs d'état **Critique pour les performances** et **Expire bientôt/Expiré** s'affichent uniquement si des seuils sont définis.</span><span class="sxs-lookup"><span data-stu-id="3124a-133">The status values **Performance critical** and **Expiring soon/Expired** are displayed only if thresholds are set.</span></span> <span data-ttu-id="3124a-134">Pour plus d’informations sur les mesures de performances et sur la définition des seuils, consultez [Analyser les performances avec le Moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md) et [Définir des seuils et des avertissements dans le Moniteur de réplication](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="3124a-134">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="3124a-135">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="3124a-135">**Subscription**</span></span>  
 <span data-ttu-id="3124a-136">Nom de chaque abonnement, au format : *NomAbonné: NomBaseDonnéesAbonnements*.</span><span class="sxs-lookup"><span data-stu-id="3124a-136">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="3124a-137">**Performances**</span><span class="sxs-lookup"><span data-stu-id="3124a-137">**Performance**</span></span>  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="3124a-138">et versions ultérieures uniquement.</span><span class="sxs-lookup"><span data-stu-id="3124a-138">and later versions only.</span></span> <span data-ttu-id="3124a-139">La valeur de performance de chaque abonnement est basée sur les dernières mesures relevées par le Moniteur de réplication et n'affecte pas les performances historiques.</span><span class="sxs-lookup"><span data-stu-id="3124a-139">The performance rating for each subscription is based on the most recent measurements taken by Replication Monitor and does not reflect historical performance.</span></span> <span data-ttu-id="3124a-140">Les performances sont mesurées pour les abonnements aux publications ayant des seuils définis. Si des seuils de performances ne sont pas définis pour une publication, cette colonne contient **Non activé**.</span><span class="sxs-lookup"><span data-stu-id="3124a-140">Performance is measured for subscriptions to publications that have performance thresholds defined; if performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="3124a-141">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3124a-141">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="3124a-142">Excellent</span><span class="sxs-lookup"><span data-stu-id="3124a-142">Excellent</span></span>  
  
-   <span data-ttu-id="3124a-143">Bien</span><span class="sxs-lookup"><span data-stu-id="3124a-143">Good</span></span>  
  
-   <span data-ttu-id="3124a-144">Moyen</span><span class="sxs-lookup"><span data-stu-id="3124a-144">Fair</span></span>  
  
-   <span data-ttu-id="3124a-145">Médiocre</span><span class="sxs-lookup"><span data-stu-id="3124a-145">Poor</span></span>  
  
-   <span data-ttu-id="3124a-146">Critique</span><span class="sxs-lookup"><span data-stu-id="3124a-146">Critical</span></span>  
  
 <span data-ttu-id="3124a-147">Si les performances sont critiques, **Critique pour les performances** figure dans la colonne **État** .</span><span class="sxs-lookup"><span data-stu-id="3124a-147">If performance is critical, **Performance Critical** is displayed in the **Status** column.</span></span> <span data-ttu-id="3124a-148">Pour plus d’informations sur la fixation des valeurs et des seuils de performances, consultez [Analyser les performances avec le Moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="3124a-148">For more information on how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="3124a-149">**Latence**</span><span class="sxs-lookup"><span data-stu-id="3124a-149">**Latency**</span></span>  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="3124a-150">et versions ultérieures uniquement.</span><span class="sxs-lookup"><span data-stu-id="3124a-150">and later versions only.</span></span> <span data-ttu-id="3124a-151">Délai moyen qui s'écoule entre la validation d'une transaction sur le serveur de publication et la validation de la transaction correspondante au niveau de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="3124a-151">The average amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="3124a-152">La latence affichée est basée sur les dernières mesures relevées par le Moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="3124a-152">The latency displayed is based on the most recent measurements taken by Replication Monitor.</span></span> <span data-ttu-id="3124a-153">Pour plus d’informations sur la mesure de la latence, consultez [Mesurer la latence et valider les connexions pour la réplication transactionnelle](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="3124a-153">For more information about measuring latency, see [Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3124a-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3124a-154">See Also</span></span>  
 <span data-ttu-id="3124a-155">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="3124a-155">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="3124a-156">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="3124a-156">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="3124a-157">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="3124a-157">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
