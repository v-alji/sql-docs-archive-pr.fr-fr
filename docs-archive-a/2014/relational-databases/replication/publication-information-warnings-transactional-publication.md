---
title: Informations de publication, avertissements (publication transactionnelle, SQL Server 2005 et versions ultérieures) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.tran.f1
ms.assetid: 4d4baf1d-d0a1-4d09-bec7-137811f43f09
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac7ab0f712fe69d3736985921d70b0ce200d474
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702703"
---
# <a name="publication-information-warnings-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="55d35-102">Informations de publication, Avertissements (Publication transactionnelle, SQL Server 2005 et version ultérieure)</span><span class="sxs-lookup"><span data-stu-id="55d35-102">Publication Information, Warnings (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="55d35-103">L'onglet **Avertissements** est disponible pour les serveurs de distribution qui exécutent [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="55d35-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="55d35-104">L'onglet **Avertissements** vous permet d'effectuer les tâches suivantes selon la publication sélectionnée :</span><span class="sxs-lookup"><span data-stu-id="55d35-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="55d35-105">activer l'affichage des avertissements dans le Moniteur de réplication ;</span><span class="sxs-lookup"><span data-stu-id="55d35-105">Enable warnings to be displayed in Replication Monitor.</span></span>  
  
-   <span data-ttu-id="55d35-106">définir des seuils associés aux avertissements ;</span><span class="sxs-lookup"><span data-stu-id="55d35-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="55d35-107">définir des alertes associées aux avertissements ;</span><span class="sxs-lookup"><span data-stu-id="55d35-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="55d35-108">Avertissements, seuils et alertes</span><span class="sxs-lookup"><span data-stu-id="55d35-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="55d35-109">Le moniteur de réplication affiche par défaut des avertissements relatifs aux abonnements non initialisés : l’état **Abonnement non initialisé** s’affiche en tant qu’avertissement dans la colonne **État** des pages incluant des informations propres aux abonnements.</span><span class="sxs-lookup"><span data-stu-id="55d35-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="55d35-110">Pour les publications transactionnelles, vous pouvez indiquer si ces conditions additionnelles génèrent des avertissements :</span><span class="sxs-lookup"><span data-stu-id="55d35-110">For transactional publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="55d35-111">Expiration d'abonnement imminente.</span><span class="sxs-lookup"><span data-stu-id="55d35-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="55d35-112">Cet événement correspond à l'option **Avertir si un abonnement expire avant le seuil défini**.</span><span class="sxs-lookup"><span data-stu-id="55d35-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="55d35-113">Si le seuil précisé est atteint ou dépassé, l'état de l'abonnement se change alors en **Expire bientôt/Expiré** (à moins qu'un problème dont la priorité est supérieure doit être affiché avant l'état de l'abonnement).</span><span class="sxs-lookup"><span data-stu-id="55d35-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="55d35-114">Dépassement de la latence spécifiée.</span><span class="sxs-lookup"><span data-stu-id="55d35-114">Exceeding the specified latency.</span></span> <span data-ttu-id="55d35-115">Délai qui s'écoule entre la validation d'une transaction sur le serveur de publication et la validation de la transaction correspondante au niveau de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="55d35-115">This is the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="55d35-116">Ceci correspond à l'option **Avertir si la latence dépasse le seuil**.</span><span class="sxs-lookup"><span data-stu-id="55d35-116">This corresponds to the option **Warn if latency exceeds the threshold**.</span></span> <span data-ttu-id="55d35-117">Si le seuil défini est atteint, l'état d'abonnement est affiché sous la forme **Critique pour les performances** (à moins qu'une erreur ayant une priorité plus élevée ne doive être affichée).</span><span class="sxs-lookup"><span data-stu-id="55d35-117">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="55d35-118">Le seuil est également utilisé pour fournir une valeur de performance qui est affichée dans la colonne **Performances** des pages qui contiennent des informations d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="55d35-118">The threshold is also used to provide a performance rating, which is displayed in the **Performance** column of pages that include subscription information.</span></span> <span data-ttu-id="55d35-119">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="55d35-119">The performance rating is one of the following values:</span></span>  
  
    -   <span data-ttu-id="55d35-120">Excellent</span><span class="sxs-lookup"><span data-stu-id="55d35-120">Excellent</span></span>  
  
    -   <span data-ttu-id="55d35-121">Bien</span><span class="sxs-lookup"><span data-stu-id="55d35-121">Good</span></span>  
  
    -   <span data-ttu-id="55d35-122">Moyen</span><span class="sxs-lookup"><span data-stu-id="55d35-122">Fair</span></span>  
  
    -   <span data-ttu-id="55d35-123">Médiocre</span><span class="sxs-lookup"><span data-stu-id="55d35-123">Poor</span></span>  
  
    -   <span data-ttu-id="55d35-124">Critique</span><span class="sxs-lookup"><span data-stu-id="55d35-124">Critical</span></span>  
  
 <span data-ttu-id="55d35-125">Activer un avertissement entraîne également la définition d'un seuil.</span><span class="sxs-lookup"><span data-stu-id="55d35-125">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="55d35-126">Si, par exemple, vous activez l'avertissement **Avertir si la latence dépasse le seuil**, sélectionnez le délai entre la validation de la transaction sur le serveur de publication et la validation de la transaction au niveau de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="55d35-126">For example, if you enable the warning **Warn if latency exceeds the threshold**, select the amount of time allowable between a transaction being committed at the Publisher and the transaction being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="55d35-127">L'atteinte d'un seuil déclenche un avertissement dans le Moniteur de réplication, mais également une alerte.</span><span class="sxs-lookup"><span data-stu-id="55d35-127">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="55d35-128">Les alertes sont définies en cliquant sur **Configurer des alertes** et en fournissant les informations nécessaires dans la boîte de dialogue **Configurer les alertes de réplication** .</span><span class="sxs-lookup"><span data-stu-id="55d35-128">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="55d35-129">Options</span><span class="sxs-lookup"><span data-stu-id="55d35-129">Options</span></span>  
 <span data-ttu-id="55d35-130">**Activé**</span><span class="sxs-lookup"><span data-stu-id="55d35-130">**Enabled**</span></span>  
 <span data-ttu-id="55d35-131">Permet d'activer un avertissement et de définir un seuil.</span><span class="sxs-lookup"><span data-stu-id="55d35-131">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="55d35-132">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="55d35-132">**Warning**</span></span>  
 <span data-ttu-id="55d35-133">Description de l'avertissement associé à un seuil.</span><span class="sxs-lookup"><span data-stu-id="55d35-133">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="55d35-134">**Seuil**</span><span class="sxs-lookup"><span data-stu-id="55d35-134">**Threshold**</span></span>  
 <span data-ttu-id="55d35-135">Permet de spécifier une valeur pour le seuil.</span><span class="sxs-lookup"><span data-stu-id="55d35-135">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="55d35-136">**Configurer des alertes**</span><span class="sxs-lookup"><span data-stu-id="55d35-136">**Configure Alerts**</span></span>  
 <span data-ttu-id="55d35-137">Sélectionnez une ligne dans la grille **Avertissements** , puis cliquez sur **Configurer des alertes** pour ouvrir la boîte de dialogue **Configurer des alertes de réplication** .</span><span class="sxs-lookup"><span data-stu-id="55d35-137">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="55d35-138">Cette boîte de dialogue permet de définir une alerte associée au seuil et à l'avertissement sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="55d35-138">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="55d35-139">**Ignorer les modifications**</span><span class="sxs-lookup"><span data-stu-id="55d35-139">**Discard Changes**</span></span>  
 <span data-ttu-id="55d35-140">Permet d'annuler les modifications apportées aux avertissements et aux seuils.</span><span class="sxs-lookup"><span data-stu-id="55d35-140">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55d35-141">Cliquer sur **Ignorer les modifications** n'affecte en rien les alertes définies dans la boîte de dialogue **Configurer les alertes de réplication** .</span><span class="sxs-lookup"><span data-stu-id="55d35-141">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="55d35-142">**Save Changes**</span><span class="sxs-lookup"><span data-stu-id="55d35-142">**Save Changes**</span></span>  
 <span data-ttu-id="55d35-143">Permet d'enregistrer toute modification apportée aux avertissements et aux seuils.</span><span class="sxs-lookup"><span data-stu-id="55d35-143">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d35-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="55d35-144">See Also</span></span>  
 <span data-ttu-id="55d35-145">[Démarrer le moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="55d35-145">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="55d35-146">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="55d35-146">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="55d35-147">[Surveiller les performances avec le moniteur de réplication](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="55d35-147">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="55d35-148">[Surveillance de la réplication](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="55d35-148">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="55d35-149">Définir des seuils et des avertissements dans le moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="55d35-149">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
