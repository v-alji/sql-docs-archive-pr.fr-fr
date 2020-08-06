---
title: Définir des seuils et des avertissements dans le Moniteur de réplication | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server replication]
- Merge Agent, thresholds and warnings
- Distribution Agent, thresholds and warnings
- thresholds [SQL Server replication]
- Replication Monitor, thresholds and warnings
- monitoring performance [SQL Server replication], thresholds and warnings
ms.assetid: 3a409c2c-b77e-4001-b81a-1dcd918618ec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f34878a6398df34e55e6dd3783f2da736bee0959
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709188"
---
# <a name="set-thresholds-and-warnings-in-replication-monitor"></a><span data-ttu-id="29dae-102">Définir des seuils et des avertissements dans le Moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="29dae-102">Set Thresholds and Warnings in Replication Monitor</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="29dae-103">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] moniteur de réplication affiche des informations d’État pour les publications et les abonnements.</span><span class="sxs-lookup"><span data-stu-id="29dae-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor displays status information for publications and subscriptions.</span></span> <span data-ttu-id="29dae-104">Par défaut, le Moniteur de réplication affiche des avertissements uniquement pour les abonnements non initialisés, mais vous pouvez activer les avertissements pour d'autres conditions.</span><span class="sxs-lookup"><span data-stu-id="29dae-104">By default, Replication Monitor displays warnings only for uninitialized subscriptions, but you can enable warnings for other conditions.</span></span> <span data-ttu-id="29dae-105">Il est recommandé d'activer les avertissements pour votre topologie, afin que vous soyez informés de l'état et des performances en temps voulu.</span><span class="sxs-lookup"><span data-stu-id="29dae-105">It is recommended that you enable warnings for your topology, so that you are informed about status and performance in a timely manner.</span></span>  
  
 <span data-ttu-id="29dae-106">Quand vous activez un avertissement, vous spécifiez un seuil.</span><span class="sxs-lookup"><span data-stu-id="29dae-106">When you enable a warning, you specify a threshold.</span></span> <span data-ttu-id="29dae-107">Lorsque ce seuil est atteint ou dépassé, un avertissement est affiché (à moins qu'un problème plus important ne doive être affiché).</span><span class="sxs-lookup"><span data-stu-id="29dae-107">When that threshold is met or exceeded, a warning is displayed (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="29dae-108">L'atteinte d'un seuil déclenche un avertissement dans le Moniteur de réplication, mais également une alerte.</span><span class="sxs-lookup"><span data-stu-id="29dae-108">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="29dae-109">Vous pouvez activer des avertissements pour les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="29dae-109">You can enable warnings for the following conditions:</span></span>  
  
-   <span data-ttu-id="29dae-110">Expiration imminente d'un abonnement</span><span class="sxs-lookup"><span data-stu-id="29dae-110">Imminent subscription expiration</span></span>  
  
     <span data-ttu-id="29dae-111">Ceci concerne tous les types de réplications.</span><span class="sxs-lookup"><span data-stu-id="29dae-111">This applies to all types of replication.</span></span> <span data-ttu-id="29dae-112">Si le seuil spécifié est atteint ou dépassé, l'état de l'abonnement s'affiche sous la forme **Expire bientôt/Expiré**.</span><span class="sxs-lookup"><span data-stu-id="29dae-112">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired**.</span></span>  
  
-   <span data-ttu-id="29dae-113">Dépassement de la latence spécifiée (la quantité de temps qui s'écoule entre la validation d'une transaction sur le serveur de publication et la validation de la transaction correspondante sur l'Abonné).</span><span class="sxs-lookup"><span data-stu-id="29dae-113">Exceeding the specified latency (the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber).</span></span>  
  
     <span data-ttu-id="29dae-114">Ceci s'applique à la réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="29dae-114">This applies to transactional replication.</span></span> <span data-ttu-id="29dae-115">Si le seuil spécifié est atteint ou dépassé, l'état de l'abonnement s'affiche sous la forme **Critique pour les performances**.</span><span class="sxs-lookup"><span data-stu-id="29dae-115">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical**.</span></span>  
  
-   <span data-ttu-id="29dae-116">Dépassement du temps de synchronisation spécifié.</span><span class="sxs-lookup"><span data-stu-id="29dae-116">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="29dae-117">Ceci s'applique à la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="29dae-117">This applies to merge replication.</span></span> <span data-ttu-id="29dae-118">Si le seuil spécifié est atteint ou dépassé, l'état affiché est **Fusion longue**.</span><span class="sxs-lookup"><span data-stu-id="29dae-118">If the specified threshold is met or exceeded, the status is displayed as **Long-running merge**.</span></span> <span data-ttu-id="29dae-119">Vous pouvez spécifier des seuils différents pour des connexions à distance et des connexions sur réseau local.</span><span class="sxs-lookup"><span data-stu-id="29dae-119">You can specify different thresholds for dialup and Local Area Network (LAN) connections.</span></span>  
  
-   <span data-ttu-id="29dae-120">Impossibilité de traiter le nombre de lignes spécifié dans un intervalle de temps donné.</span><span class="sxs-lookup"><span data-stu-id="29dae-120">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="29dae-121">Ceci s'applique à la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="29dae-121">This applies to merge replication.</span></span> <span data-ttu-id="29dae-122">Si le seuil spécifié est atteint ou dépassé, l'état affiché est **Critique pour les performances**.</span><span class="sxs-lookup"><span data-stu-id="29dae-122">If the specified threshold is met or exceeded, the status is displayed as **Performance critical**.</span></span> <span data-ttu-id="29dae-123">Vous pouvez spécifier des seuils différents pour des connexions à distance et des connexions sur réseau local.</span><span class="sxs-lookup"><span data-stu-id="29dae-123">You can specify different thresholds for dialup and LAN connections.</span></span>  
  
 <span data-ttu-id="29dae-124">Pour plus d’informations sur les avertissements de type **Critique pour les performances** et **Fusion longue**, consultez [Analyser les performances avec le Moniteur de réplication](monitor-performance-with-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="29dae-124">For more information on the warnings **Performance critical** and **Long-running merge**, see [Monitor Performance with Replication Monitor](monitor-performance-with-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="29dae-125">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="29dae-125">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="29dae-126">Définir des seuils et des avertissements pour une publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="29dae-126">Set thresholds and warnings for a transactional publication</span></span>](#Transactional)  
  
-   [<span data-ttu-id="29dae-127">Définir des seuils et des avertissements pour une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="29dae-127">Set thresholds and warnings for a merge publication</span></span>](#Merge)  
  
-   [<span data-ttu-id="29dae-128">Définir des seuils et des avertissements pour une publication d'instantané</span><span class="sxs-lookup"><span data-stu-id="29dae-128">Set thresholds and warnings for a snapshot publication</span></span>](#Snapshot)  
  
##  <a name="to-set-thresholds-and-warnings-for-a-transactional-publication"></a><a name="Transactional"></a> <span data-ttu-id="29dae-129">Pour définir des seuils et des avertissements pour une publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="29dae-129">To set thresholds and warnings for a transactional publication</span></span>  
  
1.  <span data-ttu-id="29dae-130">Développez un groupe de serveurs de publication dans le volet gauche, développez un serveur de publication, puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="29dae-130">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="29dae-131">Cliquez sur l’onglet **avertissements** . Pour afficher plus d’informations sur les options de cet onglet, cliquez sur **aide** dans la barre de menus.</span><span class="sxs-lookup"><span data-stu-id="29dae-131">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="29dae-132">Sélectionnez un avertissement en activant la case à cocher appropriée : **Avertir si un abonnement expire avant le seuil défini** ou **Avertir si la latence dépasse le seuil**.</span><span class="sxs-lookup"><span data-stu-id="29dae-132">Enable a warning by selecting the appropriate check box: **Warn if a subscription will expire within the threshold** or **Warn if latency exceeds the threshold**.</span></span>  
  
4.  <span data-ttu-id="29dae-133">Définissez un seuil pour les avertissements dans la colonne **Seuil** .</span><span class="sxs-lookup"><span data-stu-id="29dae-133">Set a threshold for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="29dae-134">Si, par exemple, vous avez sélectionné **Avertir si la latence dépasse le seuil** à l'étape 3, vous pouvez choisir une latence de **60 secondes** dans la colonne **Seuil** .</span><span class="sxs-lookup"><span data-stu-id="29dae-134">For example, if you selected **Warn if latency exceeds the threshold** in step 3, you could select a latency of **60 seconds** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="29dae-135">Cliquez sur **Enregistrer les modifications**.</span><span class="sxs-lookup"><span data-stu-id="29dae-135">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="29dae-136">Pour configurer une alerte pour un seuil</span><span class="sxs-lookup"><span data-stu-id="29dae-136">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="29dae-137">Cliquez sur **Configurer des alertes**.</span><span class="sxs-lookup"><span data-stu-id="29dae-137">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="29dae-138">Dans la boîte de dialogue **Configurer des alertes de réplication** , sélectionnez une alerte puis cliquez sur **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="29dae-138">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="29dae-139">Cette boîte de dialogue affiche des alertes pour tous les types de publications, y compris des alertes qui ne sont pas liées à la surveillance des seuils.</span><span class="sxs-lookup"><span data-stu-id="29dae-139">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="29dae-140">Pour plus d’informations, consultez [Utiliser les alertes pour les événements des agents de réplication](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="29dae-140">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="29dae-141">Définissez les options dans la boîte de dialogue **\<AlertName>Propriétés de l’alerte** :</span><span class="sxs-lookup"><span data-stu-id="29dae-141">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="29dae-142">Sur la page **Général** , cliquez sur **Activer**; spécifiez la base de données à laquelle l'alerte doit s'appliquer.</span><span class="sxs-lookup"><span data-stu-id="29dae-142">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="29dae-143">Sur la page **Réponse** , spécifiez si un courrier électronique doit être envoyé et/ou si un travail doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="29dae-143">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="29dae-144">Sur la page **Options** , personnalisez le texte de la réponse.</span><span class="sxs-lookup"><span data-stu-id="29dae-144">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="29dae-145">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="29dae-145">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-merge-publication"></a><a name="Merge"></a><span data-ttu-id="29dae-146">Définir des seuils et des avertissements pour une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="29dae-146">Set thresholds and warnings for a merge publication</span></span>  
  
1.  <span data-ttu-id="29dae-147">Développez un groupe de serveurs de publication dans le volet gauche, développez un serveur de publication, puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="29dae-147">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="29dae-148">Cliquez sur l’onglet **avertissements** . Pour afficher des informations supplémentaires sur les options de cet onglet, cliquez sur **aide** dans la barre de menus.</span><span class="sxs-lookup"><span data-stu-id="29dae-148">Click the **Warnings** tab. To view more information about the options on this tab, click **Help** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="29dae-149">Sélectionnez un avertissement en activant la case à cocher appropriée :</span><span class="sxs-lookup"><span data-stu-id="29dae-149">Enable a warning by selecting the appropriate check box:</span></span>  
  
    -   <span data-ttu-id="29dae-150">**Avertir si un abonnement expire avant le seuil défini**</span><span class="sxs-lookup"><span data-stu-id="29dae-150">**Warn if a subscription will expire within the threshold**</span></span>  
  
    -   <span data-ttu-id="29dae-151">**Avertir si la durée de la fusion pour les connexions d'accès à distance dépasse le seuil**</span><span class="sxs-lookup"><span data-stu-id="29dae-151">**Warn if a merge length for dialup connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="29dae-152">**Avertir si la durée de la fusion pour les connexions LAN dépasse le seuil**</span><span class="sxs-lookup"><span data-stu-id="29dae-152">**Warn if a merge length for LAN connections exceeds the threshold**</span></span>  
  
    -   <span data-ttu-id="29dae-153">**Avertir si les lignes fusionnées par seconde pour les connexions LAN sont inférieures au seuil**</span><span class="sxs-lookup"><span data-stu-id="29dae-153">**Warn if rows merged per second for LAN connections is less than the threshold**</span></span>  
  
    -   <span data-ttu-id="29dae-154">**Avertir si les lignes fusionnées par seconde pour les connexions d'accès à distance sont inférieures au seuil**</span><span class="sxs-lookup"><span data-stu-id="29dae-154">**Warn if rows merged per second for dialup connections is less than the threshold**</span></span>  
  
4.  <span data-ttu-id="29dae-155">Définissez les seuils pour les avertissements dans la colonne **Seuil** .</span><span class="sxs-lookup"><span data-stu-id="29dae-155">Set thresholds for the warnings in the **Threshold** column.</span></span> <span data-ttu-id="29dae-156">Par exemple, si vous avez sélectionné **Avertir si la durée de la fusion pour les connexions d'accès à distance dépasse le seuil** à l'étape 3, vous pouvez sélectionner une durée de **10 minutes** dans la colonne **Seuil** .</span><span class="sxs-lookup"><span data-stu-id="29dae-156">For example, if you selected **Warn if a merge length for dialup connections exceeds the threshold** in step 3, you could select a time of **10 minutes** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="29dae-157">Cliquez sur **Enregistrer les modifications**.</span><span class="sxs-lookup"><span data-stu-id="29dae-157">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="29dae-158">Pour configurer une alerte pour un seuil</span><span class="sxs-lookup"><span data-stu-id="29dae-158">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="29dae-159">Cliquez sur **Configurer des alertes**.</span><span class="sxs-lookup"><span data-stu-id="29dae-159">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="29dae-160">Dans la boîte de dialogue **Configurer des alertes de réplication** , sélectionnez une alerte puis cliquez sur **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="29dae-160">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="29dae-161">Cette boîte de dialogue affiche des alertes pour tous les types de publications, y compris des alertes qui ne sont pas liées à la surveillance des seuils.</span><span class="sxs-lookup"><span data-stu-id="29dae-161">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span>  
  
3.  <span data-ttu-id="29dae-162">Définissez les options dans la boîte de dialogue **\<AlertName>Propriétés de l’alerte** :</span><span class="sxs-lookup"><span data-stu-id="29dae-162">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="29dae-163">Sur la page **Général** , cliquez sur **Activer**; spécifiez la base de données à laquelle l'alerte doit s'appliquer.</span><span class="sxs-lookup"><span data-stu-id="29dae-163">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="29dae-164">Sur la page **Réponse** , spécifiez si un courrier électronique doit être envoyé et/ou si un travail doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="29dae-164">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="29dae-165">Sur la page **Options** , personnalisez le texte de la réponse.</span><span class="sxs-lookup"><span data-stu-id="29dae-165">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="29dae-166">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="29dae-166">Click **Close**.</span></span>  
  
##  <a name="set-thresholds-and-warnings-for-a-snapshot-publication"></a><a name="Snapshot"></a><span data-ttu-id="29dae-167">Définir des seuils et des avertissements pour une publication d’instantané</span><span class="sxs-lookup"><span data-stu-id="29dae-167">Set thresholds and warnings for a snapshot publication</span></span>  
  
1.  <span data-ttu-id="29dae-168">Développez un groupe de serveurs de publication dans le volet gauche, développez un serveur de publication, puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="29dae-168">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="29dae-169">Cliquez sur l’onglet **avertissements** . Pour afficher plus d’informations sur les options de cet onglet, cliquez sur **aide** dans le menu supérieur.</span><span class="sxs-lookup"><span data-stu-id="29dae-169">Click the **Warnings** tab. To view more information about the options on this tab click **Help** on the top menu.</span></span>  
  
3.  <span data-ttu-id="29dae-170">Activez un avertissement en sélectionnant la case à cocher **Avertir si un abonnement expire avant le seuil défini**.</span><span class="sxs-lookup"><span data-stu-id="29dae-170">Enable a warning by selecting the check box **Warn if a subscription will expire within the threshold**.</span></span>  
  
4.  <span data-ttu-id="29dae-171">Définissez un seuil pour l'avertissement dans la colonne **Seuil** .</span><span class="sxs-lookup"><span data-stu-id="29dae-171">Set a threshold for the warning in the **Threshold** column.</span></span> <span data-ttu-id="29dae-172">Par exemple, vous pouvez sélectionner une valeur de **70%** dans la colonne **Seuil** .</span><span class="sxs-lookup"><span data-stu-id="29dae-172">For example, you could select a value of **70%** in the **Threshold** column.</span></span>  
  
5.  <span data-ttu-id="29dae-173">Cliquez sur **Enregistrer les modifications**.</span><span class="sxs-lookup"><span data-stu-id="29dae-173">Click **Save Changes**.</span></span>  
  
#### <a name="to-configure-an-alert-for-a-threshold"></a><span data-ttu-id="29dae-174">Pour configurer une alerte pour un seuil</span><span class="sxs-lookup"><span data-stu-id="29dae-174">To configure an alert for a threshold</span></span>  
  
1.  <span data-ttu-id="29dae-175">Cliquez sur **Configurer des alertes**.</span><span class="sxs-lookup"><span data-stu-id="29dae-175">Click **Configure Alerts**.</span></span>  
  
2.  <span data-ttu-id="29dae-176">Dans la boîte de dialogue **Configurer des alertes de réplication** , sélectionnez une alerte puis cliquez sur **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="29dae-176">In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.</span></span>  
  
     <span data-ttu-id="29dae-177">Cette boîte de dialogue affiche des alertes pour tous les types de publications, y compris des alertes qui ne sont pas liées à la surveillance des seuils.</span><span class="sxs-lookup"><span data-stu-id="29dae-177">This dialog box displays alerts for all publication types, including alerts that are not related to monitoring thresholds.</span></span> <span data-ttu-id="29dae-178">Pour plus d’informations, consultez [Utiliser les alertes pour les événements des agents de réplication](../agents/use-alerts-for-replication-agent-events.md).</span><span class="sxs-lookup"><span data-stu-id="29dae-178">For more information, see [Use Alerts for Replication Agent Events](../agents/use-alerts-for-replication-agent-events.md).</span></span>  
  
3.  <span data-ttu-id="29dae-179">Définissez les options dans la boîte de dialogue **\<AlertName>Propriétés de l’alerte** :</span><span class="sxs-lookup"><span data-stu-id="29dae-179">Set options in the **\<AlertName> alert properties** dialog box:</span></span>  
  
    -   <span data-ttu-id="29dae-180">Sur la page **Général** , cliquez sur **Activer**; spécifiez la base de données à laquelle l'alerte doit s'appliquer.</span><span class="sxs-lookup"><span data-stu-id="29dae-180">On the **General** page, click **Enable**; specify which database the alert should apply to.</span></span>  
  
    -   <span data-ttu-id="29dae-181">Sur la page **Réponse** , spécifiez si un courrier électronique doit être envoyé et/ou si un travail doit être effectué.</span><span class="sxs-lookup"><span data-stu-id="29dae-181">On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.</span></span>  
  
    -   <span data-ttu-id="29dae-182">Sur la page **Options** , personnalisez le texte de la réponse.</span><span class="sxs-lookup"><span data-stu-id="29dae-182">On the **Options** page, customize the text of the response.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="29dae-183">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="29dae-183">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29dae-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29dae-184">See Also</span></span>  
 [<span data-ttu-id="29dae-185">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="29dae-185">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
