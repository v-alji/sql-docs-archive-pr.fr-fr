---
title: MSSQLSERVER_14421 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 14421 (Database Engine error)
ms.assetid: 03e76d4a-d463-4673-8843-08e4ecaefe27
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d6bc793911797c334d87238ec46531f7afbf63ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612910"
---
# <a name="mssqlserver_14421"></a><span data-ttu-id="9b7cd-102">MSSQLSERVER_14421</span><span class="sxs-lookup"><span data-stu-id="9b7cd-102">MSSQLSERVER_14421</span></span>
    
## <a name="details"></a><span data-ttu-id="9b7cd-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9b7cd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b7cd-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9b7cd-104">Product Name</span></span>|<span data-ttu-id="9b7cd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b7cd-105">SQL Server</span></span>|  
|<span data-ttu-id="9b7cd-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9b7cd-106">Event ID</span></span>|<span data-ttu-id="9b7cd-107">14421</span><span class="sxs-lookup"><span data-stu-id="9b7cd-107">14421</span></span>|  
|<span data-ttu-id="9b7cd-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9b7cd-108">Event Source</span></span>|<span data-ttu-id="9b7cd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9b7cd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9b7cd-110">Composant</span><span class="sxs-lookup"><span data-stu-id="9b7cd-110">Component</span></span>|<span data-ttu-id="9b7cd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9b7cd-111">SQLEngine</span></span>|  
|<span data-ttu-id="9b7cd-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="9b7cd-112">Symbolic Name</span></span>|<span data-ttu-id="9b7cd-113">SQLErrorNum14421</span><span class="sxs-lookup"><span data-stu-id="9b7cd-113">SQLErrorNum14421</span></span>|  
|<span data-ttu-id="9b7cd-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9b7cd-114">Message Text</span></span>|<span data-ttu-id="9b7cd-115">La base de données secondaire d'envoi des journaux %s.%s a dépassé le seuil de restauration de %d minutes et n'est pas synchronisée. Aucune restauration n'a été effectuée depuis %d minutes.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-115">The log shipping secondary database %s.%s has restore threshold of %d minutes and is out of sync. No restore was performed for %d minutes.</span></span> <span data-ttu-id="9b7cd-116">La latence de la restauration est de %d minutes.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-116">Restored latency is %d minutes.</span></span> <span data-ttu-id="9b7cd-117">Vérifiez les informations du journal de l'agent et du moniteur de copie des journaux de transaction.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-117">Check agent log and logshipping monitor information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9b7cd-118">Explication</span><span class="sxs-lookup"><span data-stu-id="9b7cd-118">Explanation</span></span>  
 <span data-ttu-id="9b7cd-119">Ce message indique que la copie des journaux de transaction n'est plus synchronisée en cas de dépassement du seuil de restauration.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-119">This message indicates that log shipping is out of synchronization beyond the restore threshold.</span></span> <span data-ttu-id="9b7cd-120">Le seuil de restauration correspond au nombre de minutes qui peuvent s'écouler entre les opérations de restauration avant qu'un message soit généré.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-120">The restore threshold is the number of minutes that can elapse between restore operations before a message is generated.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="9b7cd-121">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="9b7cd-121">Possible Causes</span></span>  
 <span data-ttu-id="9b7cd-122">Ce message n'indique pas nécessairement un problème avec la copie des journaux de transaction.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-122">This message does not necessarily indicate a problem with log shipping.</span></span> <span data-ttu-id="9b7cd-123">Il peut, en fait, indiquer l'un des problèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="9b7cd-123">Instead, this message might indicate one of the following problems:</span></span>  
  
-   <span data-ttu-id="9b7cd-124">Le travail de restauration n'est pas en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-124">The restore job is not running.</span></span>  
  
     <span data-ttu-id="9b7cd-125">Le travail peut ne pas s'exécuter pour les raisons suivantes : le service Agent SQL Server sur l'instance du serveur secondaire n'est pas en cours d'exécution, le travail est désactivé ou la planification du travail a été modifiée.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-125">Possible causes of the job not running include the following: the SQL Server Agent service on the secondary server instance is not running, the job is disabled, or the schedule of the job has been changed.</span></span>  
  
-   <span data-ttu-id="9b7cd-126">Le travail de restauration est en échec.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-126">The restore job is failing.</span></span>  
  
     <span data-ttu-id="9b7cd-127">Le travail peut échouer pour les raisons suivantes : le chemin d'accès du dossier de restauration n'est pas valide, le disque est plein ou toute autre raison pouvant entraîner l'échec de l'instruction RESTORE.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-127">Possible causes of the job failing include the following: the restore folder path is not valid, the disk is full, or any other reason that the RESTORE statement could fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9b7cd-128">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9b7cd-128">User Action</span></span>  
 <span data-ttu-id="9b7cd-129">Pour résoudre le problème qui est à l'origine de ce message :</span><span class="sxs-lookup"><span data-stu-id="9b7cd-129">To troubleshoot this message:</span></span>  
  
-   <span data-ttu-id="9b7cd-130">Assurez-vous que le service Agent SQL Server est en cours d'exécution pour l'instance du serveur secondaire et que le travail de restauration pour cette base de données secondaire est activé et est planifié pour s'exécuter à la fréquence appropriée.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-130">Make sure that the SQL Server Agent service is running for the secondary server instance and that the restore job for this secondary database is enabled and is scheduled to run at the appropriate frequency.</span></span>  
  
-   <span data-ttu-id="9b7cd-131">Il est possible que le travail de restauration sur le serveur secondaire soit en échec.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-131">The restore job on the secondary server might be failing.</span></span> <span data-ttu-id="9b7cd-132">Dans ce cas, vérifiez l'historique des travaux de restauration pour déterminer la cause de l'échec.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-132">In this case, check the job history for the restore job to look for the cause.</span></span>  
  
-   <span data-ttu-id="9b7cd-133">Il se peut que le travail de restauration de la copie des journaux de transaction, qui s’exécute sur l’instance du serveur secondaire, ne puisse pas se connecter à l’instance du serveur moniteur pour mettre à jour la table **log_shipping_monitor_secondary**.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-133">The log shipping restore job, which runs on the secondary server instance, might not be able to connect to the monitor server instance to update the **log_shipping_monitor_secondary** table.</span></span> <span data-ttu-id="9b7cd-134">Ceci peut être dû à un problème d'authentification entre l'instance du serveur moniteur et l'instance du serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-134">This might be caused by an authentication problem between the monitor server instance and the secondary server instance.</span></span>  
  
-   <span data-ttu-id="9b7cd-135">La valeur du seuil d'alerte de sauvegarde est peut-être incorrecte.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-135">The backup alert threshold might have an incorrect value.</span></span> <span data-ttu-id="9b7cd-136">Dans l'idéal, cette valeur doit être au moins trois fois supérieure à la fréquence du travail de restauration.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-136">Ideally, this value is set to at least three times the frequency of the restore job.</span></span> <span data-ttu-id="9b7cd-137">Si vous modifiez la fréquence du travail de restauration une fois que la copie des journaux de transaction est configurée et fonctionnelle, la valeur du seuil d'alerte de sauvegarde doit être mise à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-137">If you change the frequency of the restore job after log shipping is configured and functional, you must update the value of the backup alert threshold accordingly.</span></span>  
  
-   <span data-ttu-id="9b7cd-138">Lorsque l’instance du serveur moniteur est mise hors connexion et qu’elle revient ensuite en ligne, la table **log_shipping_monitor_secondary** n’est pas mise à jour avec les valeurs actuelles avant l’exécution du travail de message d’alerte.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-138">When the monitor server instance goes offline and then comes back online, the **log_shipping_monitor_secondary** table is not updated with the current values before the alert message job runs.</span></span> <span data-ttu-id="9b7cd-139">L'erreur 14421 peut survenir lorsqu'un travail de restauration est effectué et retourne le message « Impossible de trouver un fichier de sauvegarde du journal pouvant être appliqué à la base de données secondaire ».</span><span class="sxs-lookup"><span data-stu-id="9b7cd-139">Error 14421 can be raised when a restore job succeeds with, "Could not find a log backup file that could be applied to secondary database."</span></span> <span data-ttu-id="9b7cd-140">Dans ce cas, l'heure de restauration n'est pas mise à jour.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-140">When this occurs, the restore time is not updated.</span></span> <span data-ttu-id="9b7cd-141">La cause de l'erreur peut alors être liée à un problème du travail de copie.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-141">The cause of the error in this case might be an issue with the copy job.</span></span>  
  
     <span data-ttu-id="9b7cd-142">Pour mettre à jour les tables du serveur moniteur afin qu’elles contiennent les données les plus récentes pour la base de données secondaire, exécutez **sp_refresh_log_shipping_monitor** sur l’instance du serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-142">To update the monitor tables with the latest data for the secondary database, run **sp_refresh_log_shipping_monitor** on the secondary server instance.</span></span>  
  
-   <span data-ttu-id="9b7cd-143">La date ou l'heure est incorrecte sur l'instance du serveur secondaire ou du serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-143">On the secondary or monitor server instance, the date or time is incorrect.</span></span> <span data-ttu-id="9b7cd-144">Ceci peut également générer des messages d'alerte.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-144">This may also generate alert messages.</span></span> <span data-ttu-id="9b7cd-145">Il est possible que la date ou l'heure système ait été modifiée sur l'une des deux instances.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-145">Possibly the system date or time was modified on the one of them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b7cd-146">Une différence de fuseaux horaires entre les deux instances de serveurs ne pose généralement aucun problème.</span><span class="sxs-lookup"><span data-stu-id="9b7cd-146">Different time zones for the two server instances should not cause a problem.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7cd-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b7cd-147">See Also</span></span>  
 <span data-ttu-id="9b7cd-148">[log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b7cd-148">[log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="9b7cd-149">[À propos de la copie des journaux des transactions &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b7cd-149">[About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="9b7cd-150">[sp_help_log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b7cd-150">[sp_help_log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="9b7cd-151">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b7cd-151">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span></span>  
 [<span data-ttu-id="9b7cd-152">À propos de la copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9b7cd-152">About Log Shipping &#40;SQL Server&#41;</span></span>](../../database-engine/log-shipping/about-log-shipping-sql-server.md)  
  
  
