---
title: Informations de publication, jetons de suivi (publication transactionnelle, SQL Server 2005 et versions ultérieures) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.tracertokens.f1
ms.assetid: a115ba95-17ae-45df-91bd-5a1a35f3745f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af84ab9b9122a55367780976056ce95aa597f62a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705008"
---
# <a name="publication-information-tracer-tokens-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="aac24-102">Informations de publication, jetons de suivi (publication transactionnelle, SQL Server 2005 et ultérieur)</span><span class="sxs-lookup"><span data-stu-id="aac24-102">Publication Information, Tracer Tokens (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="aac24-103"> L’onglet **Jetons de suivi** vous permet de contrôler la validité des connexions, mais aussi de paramétrer la mesure du temps de latence d’un système utilisant la réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="aac24-103">The **Tracer Tokens** tab allows you to validate connections and to measure the latency of a system that uses transactional replication.</span></span> <span data-ttu-id="aac24-104">Un jeton (une petite quantité de données) est écrit dans le journal des transactions de la base de données de publication et est marqué comme s'il s'agissait d'une transaction standard répliquée, puis est envoyé dans le système, permettant ainsi le calcul :</span><span class="sxs-lookup"><span data-stu-id="aac24-104">A token (a small amount of data) is written to the transaction log of the publication database, marked as though it were a typical replicated transaction, and sent through the system, allowing a calculation of:</span></span>  
  
-   <span data-ttu-id="aac24-105">du temps écoulé entre la validation d'une transaction par le serveur de publication et l'insertion de la commande qui en découle dans la base de données de distribution sur le serveur de distribution ;</span><span class="sxs-lookup"><span data-stu-id="aac24-105">How much time elapses between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span>  
  
-   <span data-ttu-id="aac24-106">du temps écoulé entre l'insertion d'une commande dans la base de données de distribution et la validation de la transaction qui en découle au niveau d'un Abonné.</span><span class="sxs-lookup"><span data-stu-id="aac24-106">How much time elapses between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span>  
  
 <span data-ttu-id="aac24-107">De par ces calculs, vous pouvez ainsi répondre à diverses questions, notamment :</span><span class="sxs-lookup"><span data-stu-id="aac24-107">From these calculations, you can answer a number of questions, including:</span></span>  
  
-   <span data-ttu-id="aac24-108">Quels Abonnés mettent le plus longtemps à recevoir une modification du serveur de publication ?</span><span class="sxs-lookup"><span data-stu-id="aac24-108">Which Subscribers take the longest to receive a change from the Publisher?</span></span>  
  
-   <span data-ttu-id="aac24-109">De l'ensemble des Abonnés prévus pour recevoir le jeton de suivi, lesquels, le cas échéant, ne l'ont pas reçu ?</span><span class="sxs-lookup"><span data-stu-id="aac24-109">Of the Subscribers expected to receive the tracer token, which, if any, have not received it?</span></span>  
  
## <a name="options"></a><span data-ttu-id="aac24-110">Options</span><span class="sxs-lookup"><span data-stu-id="aac24-110">Options</span></span>  
 <span data-ttu-id="aac24-111">Pour modifier la façon dont la grille affiche les données, cliquez avec le bouton droit sur la grille, puis cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="aac24-111">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="aac24-112">**Trier**: cette option vous permet d'effectuer un tri sur ou plusieurs colonnes dans la boîte de dialogue **Trier les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="aac24-112">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="aac24-113">**Choisir les colonnes à afficher**: cette option vous permet de sélectionner les colonnes à afficher et l'ordre d'affichage dans la boîte de dialogue **Choisir les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="aac24-113">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="aac24-114">**Filtre**: cette option vous permet de filtrer les lignes dans la grille selon les valeurs de colonne dans la boîte de dialogue **Paramètres du filtre** .</span><span class="sxs-lookup"><span data-stu-id="aac24-114">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="aac24-115">**Effacer le filtre**: cette option vous permet d'effacer tous les paramètres du filtre pour la grille.</span><span class="sxs-lookup"><span data-stu-id="aac24-115">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="aac24-116">Les paramètres du filtre sont spécifiques à chaque grille.</span><span class="sxs-lookup"><span data-stu-id="aac24-116">Filter settings are specific to each grid.</span></span> <span data-ttu-id="aac24-117">La sélection et le tri des colonnes sont appliqués à toutes les grilles du même type, par exemple la grille de publications pour chaque serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="aac24-117">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="aac24-118">**Insérer un suivi**</span><span class="sxs-lookup"><span data-stu-id="aac24-118">**Insert Tracer**</span></span>  
 <span data-ttu-id="aac24-119">Permet d'insérer en cliquant sur un jeton de suivi dans le journal des transactions sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="aac24-119">Click to insert a tracer token in the transaction log at the Publisher.</span></span>  
  
 <span data-ttu-id="aac24-120">**Heure de l'insertion**</span><span class="sxs-lookup"><span data-stu-id="aac24-120">**Time inserted**</span></span>  
 <span data-ttu-id="aac24-121">Permet de spécifier une heure à laquelle un jeton de suivi a été inséré afin d'afficher les informations relatives au temps de latence par rapport à cette heure.</span><span class="sxs-lookup"><span data-stu-id="aac24-121">Select a time at which a tracer token was inserted to display latency information from that time.</span></span> <span data-ttu-id="aac24-122">Par défaut, les informations du temps le plus récent sont celles affichées.</span><span class="sxs-lookup"><span data-stu-id="aac24-122">By default, information from the most recent time is displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aac24-123">Les informations de jeton de suivi sont conservées pour la même durée que toute autre donnée d'historique, elles-mêmes étant régies par la période de rétention des historiques définie dans la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="aac24-123">Tracer token information is retained for the same time period as other historical data, which is governed by the history retention period of the distribution database.</span></span> <span data-ttu-id="aac24-124">Pour plus d’informations sur la modification des propriétés de base de données de distribution, consultez [Afficher et modifier les propriétés d’un serveur de distribution ou d’un serveur de publication](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="aac24-124">For information about changing distribution database properties, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
 <span data-ttu-id="aac24-125">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="aac24-125">**Subscription**</span></span>  
 <span data-ttu-id="aac24-126">Nom de chaque abonnement à la publication.</span><span class="sxs-lookup"><span data-stu-id="aac24-126">The name of each subscription to the publication.</span></span>  
  
 <span data-ttu-id="aac24-127">**Du serveur de publication vers le serveur de distribution**</span><span class="sxs-lookup"><span data-stu-id="aac24-127">**Publisher to Distributor**</span></span>  
 <span data-ttu-id="aac24-128">Temps écoulé entre la validation d'une transaction par le serveur de publication et l'insertion de la commande qui en découle dans la base de données de distribution sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="aac24-128">The elapsed time between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span> <span data-ttu-id="aac24-129">La valeur **En attente** indique que le jeton n'est pas encore arrivé au serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="aac24-129">A value of **Pending** indicates that the token has not yet reached the Distributor.</span></span> <span data-ttu-id="aac24-130">Si cet état ne semble pas évoluer, vérifiez que l'Agent de lecture du journal est bien en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="aac24-130">If the pending state persists, ensure that the Log Reader Agent is running.</span></span>  
  
 <span data-ttu-id="aac24-131">**Du serveur de distribution vers l'Abonné**</span><span class="sxs-lookup"><span data-stu-id="aac24-131">**Distributor to Subscriber**</span></span>  
 <span data-ttu-id="aac24-132">Temps écoulé entre l'insertion d'une commande dans la base de données de distribution et la validation de la transaction qui en découle au niveau d'un Abonné.</span><span class="sxs-lookup"><span data-stu-id="aac24-132">The elapsed time between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span> <span data-ttu-id="aac24-133">La valeur **En attente** indique que le jeton n'est pas encore arrivé à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="aac24-133">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span> <span data-ttu-id="aac24-134">Si cet état persiste, vérifiez que l'Agent de distribution est bien en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="aac24-134">If the pending state persists, ensure that the Distribution Agent is running.</span></span>  
  
 <span data-ttu-id="aac24-135">**Latence totale**</span><span class="sxs-lookup"><span data-stu-id="aac24-135">**Total Latency**</span></span>  
 <span data-ttu-id="aac24-136">Temps écoulé entre la validation d'une transaction par le serveur de publication et la validation de la transaction qui en découle au niveau de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="aac24-136">The elapsed time between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="aac24-137">Cette option représente la latence du système de réplication pour un abonné donné au moment présent, du début de la procédure à sa fin.</span><span class="sxs-lookup"><span data-stu-id="aac24-137">This represents the end-to-end latency of the replication system for this Subscriber at this time.</span></span> <span data-ttu-id="aac24-138">La valeur **En attente** indique que le jeton n'est pas encore arrivé à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="aac24-138">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aac24-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aac24-139">See Also</span></span>  
 <span data-ttu-id="aac24-140">[Démarrer et arrêter un Agent de réplication &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="aac24-140">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="aac24-141">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="aac24-141">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="aac24-142">[Mesurer la latence et valider les connexions pour la réplication transactionnelle](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="aac24-142">[Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span></span>  
 <span data-ttu-id="aac24-143">[Surveiller les performances avec le moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="aac24-143">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="aac24-144">[Surveillance de la réplication](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="aac24-144">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="aac24-145">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="aac24-145">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
