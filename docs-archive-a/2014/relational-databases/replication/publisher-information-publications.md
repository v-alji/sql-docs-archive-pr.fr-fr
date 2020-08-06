---
title: Réplication SQL Server boîte de dialogue « informations sur le serveur de publication » | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.publications.f1
ms.assetid: 0b2e3d4e-03b7-4c31-8f96-48648d750010
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3797ae4f9fe8f42b4abec715c63bc627c2a62cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697889"
---
# <a name="sql-server-replication-publisher-information-dialog-box"></a><span data-ttu-id="8096f-102">Réplication SQL Server boîte de dialogue « informations sur le serveur de publication »</span><span class="sxs-lookup"><span data-stu-id="8096f-102">SQL Server Replication 'Publisher Information' dialog box</span></span>
  <span data-ttu-id="8096f-103">L'onglet **Publications** fournit des informations résumées pour toutes les publications sur le serveur de publication sélectionné dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="8096f-103">The **Publications** tab provides summary information for all publications at the Publisher selected in the left pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8096f-104">Options</span><span class="sxs-lookup"><span data-stu-id="8096f-104">Options</span></span>  
 <span data-ttu-id="8096f-105">Pour modifier la façon dont la grille affiche les données, cliquez avec le bouton droit sur la grille, puis cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="8096f-105">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="8096f-106">**Trier**: cette option vous permet d'effectuer un tri sur ou plusieurs colonnes dans la boîte de dialogue **Trier les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="8096f-106">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="8096f-107">**Choisir les colonnes à afficher**: cette option vous permet de sélectionner les colonnes à afficher et l'ordre d'affichage dans la boîte de dialogue **Choisir les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="8096f-107">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="8096f-108">**Filtre**: cette option vous permet de filtrer les lignes dans la grille selon les valeurs de colonne dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="8096f-108">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="8096f-109">**Effacer le filtre**: cette option vous permet d'effacer tous les paramètres du filtre pour la grille.</span><span class="sxs-lookup"><span data-stu-id="8096f-109">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="8096f-110">Les paramètres du filtre sont spécifiques à chaque grille.</span><span class="sxs-lookup"><span data-stu-id="8096f-110">Filter settings are specific to each grid.</span></span> <span data-ttu-id="8096f-111">La sélection et le tri des colonnes sont appliqués à toutes les grilles du même type, par exemple la grille de publications pour chaque serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="8096f-111">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="8096f-112">**État**</span><span class="sxs-lookup"><span data-stu-id="8096f-112">**Status**</span></span>  
 <span data-ttu-id="8096f-113">État de chaque publication déterminé par l'état de priorité la plus haute de ses abonnements.</span><span class="sxs-lookup"><span data-stu-id="8096f-113">The status of each publication, which is determined by the highest priority status of its subscriptions.</span></span> <span data-ttu-id="8096f-114">La grille contenant les informations de publication est triée par défaut par la colonne **État** .</span><span class="sxs-lookup"><span data-stu-id="8096f-114">By default, the grid containing publication information is sorted by the **Status** column.</span></span> <span data-ttu-id="8096f-115">La liste suivante répertorie les éventuelles valeurs d'état ainsi que leur ordre de tri (par exemple, les erreurs sont toujours affichées en haut de la grille) :</span><span class="sxs-lookup"><span data-stu-id="8096f-115">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid):</span></span>  
  
-   <span data-ttu-id="8096f-116">Error</span><span class="sxs-lookup"><span data-stu-id="8096f-116">Error</span></span>  
  
-   <span data-ttu-id="8096f-117">Critique pour les performances</span><span class="sxs-lookup"><span data-stu-id="8096f-117">Performance critical</span></span>  
  
-   <span data-ttu-id="8096f-118">Nouvelle tentative de la commande qui a échoué</span><span class="sxs-lookup"><span data-stu-id="8096f-118">Retrying failed command</span></span>  
  
-   <span data-ttu-id="8096f-119">OK</span><span class="sxs-lookup"><span data-stu-id="8096f-119">OK</span></span>  
  
 <span data-ttu-id="8096f-120">La valeur d'état **Critique pour les performances** est pertinente pour les abonnements transactionnels et de fusion. Pour les abonnements transactionnels, elle ne peut être affichée que si un seuil est défini.</span><span class="sxs-lookup"><span data-stu-id="8096f-120">The status value **Performance critical** is relevant for transactional subscriptions and merge subscriptions; for transactional subscriptions, it can be displayed only if a threshold is set.</span></span> <span data-ttu-id="8096f-121">Pour plus d’informations sur les mesures de performances et sur la définition des seuils, consultez [Analyser les performances avec le Moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md) et [Définir des seuils et des avertissements dans le Moniteur de réplication](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="8096f-121">For information on performance measurements and setting thresholds, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) and [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="8096f-122">**Publication**</span><span class="sxs-lookup"><span data-stu-id="8096f-122">**Publication**</span></span>  
 <span data-ttu-id="8096f-123">Nom de chaque publication, sous la forme *PublicationDatabaseName: PublicationName*.</span><span class="sxs-lookup"><span data-stu-id="8096f-123">The name of each publication, in the form *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="8096f-124">**Abonnements**</span><span class="sxs-lookup"><span data-stu-id="8096f-124">**Subscriptions**</span></span>  
 <span data-ttu-id="8096f-125">Nombre d'abonnements pour chaque publication.</span><span class="sxs-lookup"><span data-stu-id="8096f-125">The number of subscriptions for each publication.</span></span>  
  
 <span data-ttu-id="8096f-126">**Synchronisation**</span><span class="sxs-lookup"><span data-stu-id="8096f-126">**Synchronizing**</span></span>  
 <span data-ttu-id="8096f-127">Nombre d'abonnements pour chaque publication en cours de synchronisation :</span><span class="sxs-lookup"><span data-stu-id="8096f-127">The number of subscriptions for each publication that are currently synchronizing:</span></span>  
  
-   <span data-ttu-id="8096f-128">Pour la réplication transactionnelle, le terme « synchronisation » signifie que l'Agent de distribution est en cours d'exécution mais que les données ne sont pas nécessairement répliquées.</span><span class="sxs-lookup"><span data-stu-id="8096f-128">For transactional replication, "synchronizing" means that the Distribution Agent is running, but data is not necessarily being replicated.</span></span>  
  
-   <span data-ttu-id="8096f-129">Pour la réplication de fusion, le terme « synchronisation » signifie que l'Agent de fusion est en cours d'exécution et que les données sont en cours de réplication.</span><span class="sxs-lookup"><span data-stu-id="8096f-129">For merge replication, "synchronizing" means that the Merge Agent is running and that data is currently being replicated.</span></span>  
  
-   <span data-ttu-id="8096f-130">Pour la réplication d'instantané, le terme « synchronisation » signifie que l'Agent de distribution est en cours d'exécution et que les données sont en cours de réplication.</span><span class="sxs-lookup"><span data-stu-id="8096f-130">For snapshot replication, "synchronizing" means that the Distribution Agent is running and that data is currently being replicated.</span></span>  
  
 <span data-ttu-id="8096f-131">**Performance moyenne actuelle** et **Pire performance actuelle**</span><span class="sxs-lookup"><span data-stu-id="8096f-131">**Current Average Performance** and **Current Worst Performance**</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="8096f-132">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures uniquement.</span><span class="sxs-lookup"><span data-stu-id="8096f-132">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="8096f-133">Évaluations respectives des performances moyenne et pire pour tous les abonnements à une publication.</span><span class="sxs-lookup"><span data-stu-id="8096f-133">The average performance rating and the worst performance rating, respectively, for all subscriptions to a publication.</span></span> <span data-ttu-id="8096f-134">Ces évaluations sont basées sur les mesures les plus récentes prises par le moniteur de réplication. Elles ne reflètent pas les performances d'un abonnement dans le temps.</span><span class="sxs-lookup"><span data-stu-id="8096f-134">Ratings are based on the most recent measurements taken by Replication Monitor and do not reflect the performance of a subscription over time.</span></span>  
  
 <span data-ttu-id="8096f-135">Dans le cas de la réplication transactionnelle, le moniteur de réplication affiche une valeur uniquement pour les publications dont les seuils de performances sont définis.</span><span class="sxs-lookup"><span data-stu-id="8096f-135">For transactional replication, Replication Monitor displays a value only for publications that have performance thresholds defined.</span></span> <span data-ttu-id="8096f-136">Si des seuils de performances ne sont pas définis pour une publication, cette colonne contient **Non activé**.</span><span class="sxs-lookup"><span data-stu-id="8096f-136">If performance thresholds are not defined for a publication, this column displays **Not enabled**.</span></span> <span data-ttu-id="8096f-137">Dans le cas de la réplication de fusion, le moniteur de réplication affiche une valeur après cinq synchronisations avec au moins 50 modifications chacune via le même type de connexion (accès à distance ou LAN).</span><span class="sxs-lookup"><span data-stu-id="8096f-137">For merge replication, Replication Monitor displays a value after five synchronizations have occurred with 50 or more changes each over the same type of connection (dial-up or LAN).</span></span> <span data-ttu-id="8096f-138">S'il y a eu moins de cinq synchronisations avec au moins 50 modifications ou que la synchronisation la plus récente possède moins de 50 modifications, cette colonne est vide.</span><span class="sxs-lookup"><span data-stu-id="8096f-138">If there have been less than five synchronizations with 50 or more changes or the most recent synchronization has less than 50 changes, this column is blank.</span></span>  
  
 <span data-ttu-id="8096f-139">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="8096f-139">The performance rating is one of the following values:</span></span>  
  
-   <span data-ttu-id="8096f-140">Excellent</span><span class="sxs-lookup"><span data-stu-id="8096f-140">Excellent</span></span>  
  
-   <span data-ttu-id="8096f-141">Bonne</span><span class="sxs-lookup"><span data-stu-id="8096f-141">Good</span></span>  
  
-   <span data-ttu-id="8096f-142">Correcte</span><span class="sxs-lookup"><span data-stu-id="8096f-142">Fair</span></span>  
  
-   <span data-ttu-id="8096f-143">Médiocre</span><span class="sxs-lookup"><span data-stu-id="8096f-143">Poor</span></span>  
  
-   <span data-ttu-id="8096f-144">Critique</span><span class="sxs-lookup"><span data-stu-id="8096f-144">Critical</span></span>  
  
 <span data-ttu-id="8096f-145">Pour plus d’informations sur la définition des indices et des seuils de performances, consultez [Analyser les performances avec le Moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="8096f-145">For more information about how performance ratings are defined and how performance thresholds are set, see [Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8096f-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8096f-146">See Also</span></span>  
 <span data-ttu-id="8096f-147">[Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="8096f-147">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="8096f-148">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="8096f-148">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="8096f-149">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="8096f-149">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
