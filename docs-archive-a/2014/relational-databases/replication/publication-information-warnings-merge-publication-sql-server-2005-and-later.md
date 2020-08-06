---
title: Informations de publication, avertissements (publication de fusion, SQL Server 2005 et versions ultérieures) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.merge.f1
ms.assetid: 9bef3565-5f13-42ac-8723-ebe55b0c11e6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 75f58a4cd9bd84791acf7fd9d28147ef3bbd6232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610610"
---
# <a name="publication-information-warnings-merge-publication-sql-server-2005-and-later"></a><span data-ttu-id="dc849-102">Informations de publication, Avertissements (Publication de fusion, SQL Server 2005 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="dc849-102">Publication Information, Warnings (Merge Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="dc849-103">L'onglet **Avertissements** est disponible pour les serveurs de distribution qui exécutent [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="dc849-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="dc849-104">L'onglet **Avertissements** vous permet d'effectuer les tâches suivantes selon la publication sélectionnée :</span><span class="sxs-lookup"><span data-stu-id="dc849-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="dc849-105">activer les avertissements ;</span><span class="sxs-lookup"><span data-stu-id="dc849-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="dc849-106">définir des seuils associés aux avertissements ;</span><span class="sxs-lookup"><span data-stu-id="dc849-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="dc849-107">définir des alertes associées aux avertissements ;</span><span class="sxs-lookup"><span data-stu-id="dc849-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="dc849-108">Avertissements, seuils et alertes</span><span class="sxs-lookup"><span data-stu-id="dc849-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="dc849-109">Le moniteur de réplication affiche par défaut des avertissements relatifs aux abonnements non initialisés : l’état **Abonnement non initialisé** s’affiche en tant qu’avertissement dans la colonne **État** des pages incluant des informations propres aux abonnements.</span><span class="sxs-lookup"><span data-stu-id="dc849-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="dc849-110">Dans le cas de publications de fusion, vous pouvez indiquer si les conditions complémentaires suivantes constituent un motif pour lancer un avertissement :</span><span class="sxs-lookup"><span data-stu-id="dc849-110">For merge publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="dc849-111">Expiration d'abonnement imminente.</span><span class="sxs-lookup"><span data-stu-id="dc849-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="dc849-112">Cet événement correspond à l'option **Avertir si un abonnement expire avant le seuil défini**.</span><span class="sxs-lookup"><span data-stu-id="dc849-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="dc849-113">Si le seuil précisé est atteint ou dépassé, l'état de l'abonnement se change alors en **Expire bientôt/Expiré** (à moins qu'un problème dont la priorité est supérieure doit être affiché avant l'état de l'abonnement).</span><span class="sxs-lookup"><span data-stu-id="dc849-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="dc849-114">Dépassement du temps de synchronisation spécifié.</span><span class="sxs-lookup"><span data-stu-id="dc849-114">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="dc849-115">Ce problème correspond aux options **Avertir si la durée de la fusion pour les connexions d'accès à distance dépasse le seuil** et **Avertir si la durée de la fusion pour les connexions LAN dépasse le seuil**.</span><span class="sxs-lookup"><span data-stu-id="dc849-115">This corresponds to the options **Warn if a merge length for dialup connections exceeds the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="dc849-116">Ces deux seuils peuvent être définis, mais seulement un des deux n'est utilisé lors d'une synchronisation donnée.</span><span class="sxs-lookup"><span data-stu-id="dc849-116">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="dc849-117">L'Agent de fusion applique en effet le seuil approprié selon le type de connexion.</span><span class="sxs-lookup"><span data-stu-id="dc849-117">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="dc849-118">Si le seuil précisé est atteint ou dépassé, l'état de l'abonnement se change alors en **Fusion longue** (à moins qu'un problème dont la priorité est supérieure doit être affiché avant l'état de l'abonnement).</span><span class="sxs-lookup"><span data-stu-id="dc849-118">If the specified threshold is met or exceeded, the subscription status is displayed as **Long-running merge** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="dc849-119">Impossibilité de traiter le nombre de lignes spécifié dans un intervalle de temps donné.</span><span class="sxs-lookup"><span data-stu-id="dc849-119">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="dc849-120">Cela correspond aux options **Avertir si les lignes fusionnées par seconde pour les connexions d'accès à distance sont inférieures au seuil** et **Avertir si la durée de la fusion pour les connexions LAN dépasse le seuil**.</span><span class="sxs-lookup"><span data-stu-id="dc849-120">This corresponds to the options **Warn if rows merged per second for dialup connections is less than the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="dc849-121">Ces deux seuils peuvent être définis, mais seulement un des deux n'est utilisé lors d'une synchronisation donnée.</span><span class="sxs-lookup"><span data-stu-id="dc849-121">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="dc849-122">L'Agent de fusion applique en effet le seuil approprié selon le type de connexion.</span><span class="sxs-lookup"><span data-stu-id="dc849-122">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="dc849-123">Si le seuil défini est atteint, l'état d'abonnement est affiché sous la forme **Critique pour les performances** (à moins qu'une erreur ayant une priorité plus élevée ne doive être affichée).</span><span class="sxs-lookup"><span data-stu-id="dc849-123">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="dc849-124">Activer un avertissement entraîne également la définition d'un seuil.</span><span class="sxs-lookup"><span data-stu-id="dc849-124">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="dc849-125">Par exemple, si vous activez l'avertissement **Avertir si la durée de la fusion pour les connexions LAN dépasse le seuil**, définissez le temps maximal autorisé à l'opération de synchronisation de fusion.</span><span class="sxs-lookup"><span data-stu-id="dc849-125">For example, if you enable the warning **Warn if a merge length for LAN connections exceeds the threshold**, set the maximum allowable length of time for a merge synchronization.</span></span>  
  
 <span data-ttu-id="dc849-126">L'atteinte d'un seuil déclenche un avertissement dans le Moniteur de réplication, mais également une alerte.</span><span class="sxs-lookup"><span data-stu-id="dc849-126">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="dc849-127">Les alertes sont définies en cliquant sur **Configurer des alertes** et en fournissant les informations nécessaires dans la boîte de dialogue **Configurer les alertes de réplication** .</span><span class="sxs-lookup"><span data-stu-id="dc849-127">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dc849-128">Options</span><span class="sxs-lookup"><span data-stu-id="dc849-128">Options</span></span>  
 <span data-ttu-id="dc849-129">**Activé**</span><span class="sxs-lookup"><span data-stu-id="dc849-129">**Enabled**</span></span>  
 <span data-ttu-id="dc849-130">Permet d'activer un avertissement et de définir un seuil.</span><span class="sxs-lookup"><span data-stu-id="dc849-130">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="dc849-131">**Alert**</span><span class="sxs-lookup"><span data-stu-id="dc849-131">**Alert**</span></span>  
 <span data-ttu-id="dc849-132">Sélectionnez pour activer le paramètre d'alerte pour un avertissement de réplication donné.</span><span class="sxs-lookup"><span data-stu-id="dc849-132">Select to enable the alert setting for a given replication warning.</span></span>  
  
 <span data-ttu-id="dc849-133">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="dc849-133">**Warning**</span></span>  
 <span data-ttu-id="dc849-134">Description de l'avertissement associé à un seuil.</span><span class="sxs-lookup"><span data-stu-id="dc849-134">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="dc849-135">**Seuil**</span><span class="sxs-lookup"><span data-stu-id="dc849-135">**Threshold**</span></span>  
 <span data-ttu-id="dc849-136">Permet de spécifier une valeur pour le seuil.</span><span class="sxs-lookup"><span data-stu-id="dc849-136">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="dc849-137">**Configurer des alertes**</span><span class="sxs-lookup"><span data-stu-id="dc849-137">**Configure Alerts**</span></span>  
 <span data-ttu-id="dc849-138">Sélectionnez une ligne dans la grille **Avertissements** , puis cliquez sur **Configurer des alertes** pour ouvrir la boîte de dialogue **Configurer des alertes de réplication** .</span><span class="sxs-lookup"><span data-stu-id="dc849-138">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="dc849-139">Cette boîte de dialogue permet de définir une alerte associée au seuil et à l'avertissement sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="dc849-139">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="dc849-140">**Ignorer les modifications**</span><span class="sxs-lookup"><span data-stu-id="dc849-140">**Discard Changes**</span></span>  
 <span data-ttu-id="dc849-141">Permet d'annuler les modifications apportées aux avertissements et aux seuils.</span><span class="sxs-lookup"><span data-stu-id="dc849-141">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc849-142">Cliquer sur **Ignorer les modifications** n'affecte en rien les alertes définies dans la boîte de dialogue **Configurer les alertes de réplication** .</span><span class="sxs-lookup"><span data-stu-id="dc849-142">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="dc849-143">**Save Changes**</span><span class="sxs-lookup"><span data-stu-id="dc849-143">**Save Changes**</span></span>  
 <span data-ttu-id="dc849-144">Permet d'enregistrer toute modification apportée aux avertissements et aux seuils.</span><span class="sxs-lookup"><span data-stu-id="dc849-144">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc849-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dc849-145">See Also</span></span>  
 <span data-ttu-id="dc849-146">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="dc849-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="dc849-147">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="dc849-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="dc849-148">[Surveiller les performances avec le moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="dc849-148">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="dc849-149">[Surveillance de la réplication](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="dc849-149">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="dc849-150">Définir des seuils et des avertissements dans le moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="dc849-150">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
