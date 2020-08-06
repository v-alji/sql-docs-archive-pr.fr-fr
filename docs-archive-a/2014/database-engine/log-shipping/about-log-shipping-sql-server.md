---
title: À propos de la copie des journaux de transaction (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary servers [SQL Server]
- log shipping [SQL Server], jobs
- copy jobs [SQL Server]
- primary databases [SQL Server]
- log shipping [SQL Server], monitoring
- log shipping [SQL Server], about log shipping
- alert jobs [SQL Server]
- availability [SQL Server]
- jobs [SQL Server], log shipping
- monitor servers [SQL Server]
- restore jobs [SQL Server]
- log shipping [SQL Server]
- backup jobs [SQL Server]
- primary servers [SQL Server]
ms.assetid: 55da6b94-3a4b-4bae-850f-4bf7f6e918ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbf36e0ddd94ec0ab0a40a448e50602decfc0645
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698495"
---
# <a name="about-log-shipping-sql-server"></a><span data-ttu-id="a5b46-102">À propos de la copie des journaux de transaction (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a5b46-102">About Log Shipping (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a5b46-103">permet d'envoyer automatiquement les sauvegardes du journal des transactions à partir d'une *base de données primaire* sur une instance du *serveur principal* vers une ou plusieurs *bases de données secondaires* sur des instances distinctes du *serveur secondaire* .</span><span class="sxs-lookup"><span data-stu-id="a5b46-103">Log shipping allows you to automatically send transaction log backups from a *primary database* on a *primary server* instance to one or more *secondary databases* on separate *secondary server* instances.</span></span> <span data-ttu-id="a5b46-104">Les sauvegardes du journal des transactions sont appliquées individuellement à chacune des bases de données secondaires.</span><span class="sxs-lookup"><span data-stu-id="a5b46-104">The transaction log backups are applied to each of the secondary databases individually.</span></span> <span data-ttu-id="a5b46-105">Une troisième instance de serveur facultatif, appelée *serveur moniteur*, enregistre l'historique et l'état des opérations de sauvegarde ainsi que de restauration, puis déclenche éventuellement des alertes si ces opérations ne sont pas effectuées selon la planification établie.</span><span class="sxs-lookup"><span data-stu-id="a5b46-105">An optional third server instance, known as the *monitor server*, records the history and status of backup and restore operations and, optionally, raises alerts if these operations fail to occur as scheduled.</span></span>  
  
 <span data-ttu-id="a5b46-106">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="a5b46-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="a5b46-107">Avantages</span><span class="sxs-lookup"><span data-stu-id="a5b46-107">Benefits</span></span>](#Benefits)  
  
-   [<span data-ttu-id="a5b46-108">Termes et définitions</span><span class="sxs-lookup"><span data-stu-id="a5b46-108">Terms and Definitions</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="a5b46-109">Vue d'ensemble de la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="a5b46-109">Log Shipping Overview</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="a5b46-110">Interopérabilité</span><span class="sxs-lookup"><span data-stu-id="a5b46-110">Interoperability</span></span>](#Interoperability)  
  
-   [<span data-ttu-id="a5b46-111">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a5b46-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="a5b46-112">Avantages</span><span class="sxs-lookup"><span data-stu-id="a5b46-112">Benefits</span></span>  
  
-   <span data-ttu-id="a5b46-113">Fournit une solution de récupération d'urgence pour une base de données primaire unique et une ou plusieurs bases de données secondaires, chacune sur une instance distincte de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5b46-113">Provides a disaster-recovery solution for a single primary database and one or more secondary databases, each on a separate instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="a5b46-114">Prend en charge un accès limité en lecture seule aux bases de données secondaires (pendant l'intervalle entre des travaux de restauration).</span><span class="sxs-lookup"><span data-stu-id="a5b46-114">Supports limited read-only access to secondary databases (during the interval between restore jobs).</span></span>  
  
-   <span data-ttu-id="a5b46-115">Possibilité de spécifier un délai défini par l'utilisateur entre la sauvegarde du fichier journal de la base de données primaire par le serveur principal et la restauration (application) de la sauvegarde du fichier journal par les serveurs secondaires.</span><span class="sxs-lookup"><span data-stu-id="a5b46-115">Allows a user-specified delay between when the primary server backs up the log of the primary database and when the secondary servers must restore (apply) the log backup.</span></span> <span data-ttu-id="a5b46-116">Un délai plus long peut s'avérer utile en cas, par exemple, de modification accidentelle des données sur la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="a5b46-116">A longer delay can be useful, for example, if data is accidentally changed on the primary database.</span></span> <span data-ttu-id="a5b46-117">Si la modification accidentelle est remarquée rapidement, un délai peut vous permettre de récupérer à partir de la base de données secondaire les données n'ayant pas encore été modifiées, avant que la modification n'y soit reflétée.</span><span class="sxs-lookup"><span data-stu-id="a5b46-117">If the accidental change is noticed quickly, a delay can let you retrieve still unchanged data from a secondary database before the change is reflected there.</span></span>  
  
##  <a name="terms-and-definitions"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="a5b46-118">Termes et définitions</span><span class="sxs-lookup"><span data-stu-id="a5b46-118">Terms and Definitions</span></span>  
 <span data-ttu-id="a5b46-119">serveur principal</span><span class="sxs-lookup"><span data-stu-id="a5b46-119">primary server</span></span>  
 <span data-ttu-id="a5b46-120">Instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est votre serveur de production.</span><span class="sxs-lookup"><span data-stu-id="a5b46-120">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is your production server.</span></span>  
  
 <span data-ttu-id="a5b46-121">base de données primaire</span><span class="sxs-lookup"><span data-stu-id="a5b46-121">primary database</span></span>  
 <span data-ttu-id="a5b46-122">Base de données sur le serveur principal que vous souhaitez sauvegarder sur un autre serveur.</span><span class="sxs-lookup"><span data-stu-id="a5b46-122">The database on the primary server that you want to back up to another server.</span></span> <span data-ttu-id="a5b46-123">Toute l'administration de la configuration de la copie des journaux de transaction à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] s'exécute à partir de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="a5b46-123">All administration of the log shipping configuration through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is performed from the primary database.</span></span>  
  
 <span data-ttu-id="a5b46-124">serveur secondaire</span><span class="sxs-lookup"><span data-stu-id="a5b46-124">secondary server</span></span>  
 <span data-ttu-id="a5b46-125">Instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] où vous souhaitez conserver une copie de secours semi-automatique de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="a5b46-125">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where you want to keep a warm standby copy of your primary database.</span></span>  
  
 <span data-ttu-id="a5b46-126">base de données secondaire</span><span class="sxs-lookup"><span data-stu-id="a5b46-126">secondary database</span></span>  
 <span data-ttu-id="a5b46-127">Copie de secours semi-automatique de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="a5b46-127">The warm standby copy of the primary database.</span></span> <span data-ttu-id="a5b46-128">La base de données secondaire peut être dans l'état RECOVERING ou STANDBY, dans lequel elle est disponible pour un accès limité en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="a5b46-128">The secondary database may be in either the RECOVERING state or the STANDBY state, which leaves the database available for limited read-only access.</span></span>  
  
 <span data-ttu-id="a5b46-129">serveur moniteur</span><span class="sxs-lookup"><span data-stu-id="a5b46-129">monitor server</span></span>  
 <span data-ttu-id="a5b46-130">Instance facultative de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui assure le suivi de tous les détails de la copie des journaux de transaction, tels que :</span><span class="sxs-lookup"><span data-stu-id="a5b46-130">An optional instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that tracks all of the details of log shipping, including:</span></span>  
  
-   <span data-ttu-id="a5b46-131">le jour et l'heure de la dernière sauvegarde du journal des transactions de la base de données primaire ;</span><span class="sxs-lookup"><span data-stu-id="a5b46-131">When the transaction log on the primary database was last backed up.</span></span>  
  
-   <span data-ttu-id="a5b46-132">le jour et l'heure de la dernière copie ou restauration des fichiers de sauvegarde par les serveurs secondaires ;</span><span class="sxs-lookup"><span data-stu-id="a5b46-132">When the secondary servers last copied and restored the backup files.</span></span>  
  
-   <span data-ttu-id="a5b46-133">les informations concernant les alertes éventuelles d'échec de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a5b46-133">Information about any backup failure alerts.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a5b46-134">Une fois que le serveur moniteur a été configuré, il ne peut pas être modifié sans suppression préalable de la copie des journaux de transaction.</span><span class="sxs-lookup"><span data-stu-id="a5b46-134">Once the monitor server has been configured, it cannot be changed without removing log shipping first.</span></span>  
  
 <span data-ttu-id="a5b46-135">travail de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a5b46-135">backup job</span></span>  
 <span data-ttu-id="a5b46-136">Travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui exécute l'opération de sauvegarde, enregistre l'historique sur le serveur local et sur le serveur moniteur, puis supprime les fichiers de sauvegarde et informations d'historiques obsolètes.</span><span class="sxs-lookup"><span data-stu-id="a5b46-136">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that  performs the backup operation, logs history to the local server and the monitor server, and deletes old backup files and history information.</span></span> <span data-ttu-id="a5b46-137">Si la copie des journaux de transaction est activée, la catégorie de travaux « Sauvegarde de l'envoi de journaux » est créée sur l'instance du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="a5b46-137">When log shipping is enabled, the job category "Log Shipping Backup" is created on the primary server instance.</span></span>  
  
 <span data-ttu-id="a5b46-138">travail de copie</span><span class="sxs-lookup"><span data-stu-id="a5b46-138">copy job</span></span>  
 <span data-ttu-id="a5b46-139">Travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui copie les fichiers de sauvegarde à partir du serveur principal vers une destination configurable sur le serveur secondaire, puis enregistre l'historique sur le serveur secondaire ainsi que sur le serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="a5b46-139">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that copies the backup files from the primary server to a configurable destination on the secondary server and logs history on the secondary server and the monitor server.</span></span> <span data-ttu-id="a5b46-140">Si la copie des journaux de transaction est activée sur une base de données, la catégorie de travaux « Copie des journaux de transaction » est créée sur chaque serveur secondaire dans une configuration de la copie des journaux de transaction.</span><span class="sxs-lookup"><span data-stu-id="a5b46-140">When log shipping is enabled on a database, the job category "Log Shipping Copy" is created on each secondary server in a log shipping configuration.</span></span>  
  
 <span data-ttu-id="a5b46-141">travail de restauration</span><span class="sxs-lookup"><span data-stu-id="a5b46-141">restore job</span></span>  
 <span data-ttu-id="a5b46-142">Travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui restaure les fichiers de sauvegarde copiés dans les bases de données secondaires.</span><span class="sxs-lookup"><span data-stu-id="a5b46-142">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that restores the copied backup files to the secondary databases.</span></span> <span data-ttu-id="a5b46-143">Il enregistre l'historique sur le serveur local et sur le serveur moniteur, puis supprime les fichiers et informations d'historiques obsolètes.</span><span class="sxs-lookup"><span data-stu-id="a5b46-143">It logs history on the local server and the monitor server, and deletes old files and old history information.</span></span> <span data-ttu-id="a5b46-144">Lorsque la copie des journaux de transaction est activée sur une base de données, la catégorie de travaux « Restauration de la copie des journaux de transaction » est créée sur l'instance du serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="a5b46-144">When log shipping is enabled on a database, the job category "Log Shipping Restore" is created on the secondary server instance.</span></span>  
  
 <span data-ttu-id="a5b46-145">travail d'alerte</span><span class="sxs-lookup"><span data-stu-id="a5b46-145">alert job</span></span>  
 <span data-ttu-id="a5b46-146">Travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui déclenche des alertes pour les bases de données primaire et secondaire lorsqu'une opération de sauvegarde ou de restauration ne se termine pas correctement dans un seuil spécifié.</span><span class="sxs-lookup"><span data-stu-id="a5b46-146">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that raises alerts for primary and secondary databases when a backup or restore operation does not complete successfully within a specified threshold.</span></span> <span data-ttu-id="a5b46-147">Lorsque la copie des journaux de transaction est activée sur une base de données, la catégorie de travaux « Alerte de la copie des journaux de transaction » est créée sur l'instance du serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="a5b46-147">When log shipping is enabled on a database, job category "Log Shipping Alert" is created on the monitor server instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="a5b46-148">Pour chaque alerte, vous devez spécifier un numéro d'alerte.</span><span class="sxs-lookup"><span data-stu-id="a5b46-148">For each alert, you need to specify an alert number.</span></span> <span data-ttu-id="a5b46-149">En outre, veillez à configurer l'alerte de manière à avertir un opérateur lorsqu'une alerte est générée.</span><span class="sxs-lookup"><span data-stu-id="a5b46-149">Also, be sure to configure the alert to notify an operator when an alert is raised.</span></span>  
  
##  <a name="log-shipping-overview"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="a5b46-150">Vue d'ensemble de la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="a5b46-150">Log Shipping Overview</span></span>  
 <span data-ttu-id="a5b46-151">La copie des journaux de transaction comprend trois opérations :</span><span class="sxs-lookup"><span data-stu-id="a5b46-151">Log shipping consists of three operations:</span></span>  
  
1.  <span data-ttu-id="a5b46-152">sauvegarde du journal des transactions au niveau de l'instance du serveur principal ;</span><span class="sxs-lookup"><span data-stu-id="a5b46-152">Back up the transaction log at the primary server instance.</span></span>  
  
2.  <span data-ttu-id="a5b46-153">copie du fichier du journal des transactions sur l'instance du serveur secondaire ;</span><span class="sxs-lookup"><span data-stu-id="a5b46-153">Copy the transaction log file to the secondary server instance.</span></span>  
  
3.  <span data-ttu-id="a5b46-154">restauration de la sauvegarde du journal sur l'instance du serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="a5b46-154">Restore the log backup on the secondary server instance.</span></span>  
  
 <span data-ttu-id="a5b46-155">Le journal peut être envoyé à plusieurs instances de serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="a5b46-155">The log can be shipped to multiple secondary server instances.</span></span> <span data-ttu-id="a5b46-156">Dans ce cas, les opérations 2 et 3 sont répétées pour chaque instance de serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="a5b46-156">In such cases, operations 2 and 3 are duplicated for each secondary server instance.</span></span>  
  
 <span data-ttu-id="a5b46-157">Une configuration de la copie des journaux de transaction ne bascule pas automatiquement du serveur principal au serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="a5b46-157">A log shipping configuration does not automatically fail over from the primary server to the secondary server.</span></span> <span data-ttu-id="a5b46-158">Si la base de données primaire devient indisponible, toute base de données secondaire peut être mise en ligne manuellement.</span><span class="sxs-lookup"><span data-stu-id="a5b46-158">If the primary database becomes unavailable, any of the secondary databases can be brought online manually.</span></span>  
  
 <span data-ttu-id="a5b46-159">Vous pouvez utiliser une base de données secondaire pour générer des rapports.</span><span class="sxs-lookup"><span data-stu-id="a5b46-159">You can use a secondary database for reporting purposes.</span></span>  
  
 <span data-ttu-id="a5b46-160">En outre, vous pouvez configurer des alertes pour votre configuration de copie des journaux de transaction.</span><span class="sxs-lookup"><span data-stu-id="a5b46-160">In addition, you can configure alerts for your log shipping configuration.</span></span>  
  
### <a name="a-typical-log-shipping-configuration"></a><span data-ttu-id="a5b46-161">Configuration standard de la copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="a5b46-161">A Typical Log Shipping Configuration</span></span>  
 <span data-ttu-id="a5b46-162">La figure ci-dessous illustre une configuration de la copie des journaux de transaction avec une instance du serveur principal, trois instances du serveur secondaire et une instance de serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="a5b46-162">The following figure shows a log shipping configuration with the primary server instance, three secondary server instances, and a monitor server instance.</span></span> <span data-ttu-id="a5b46-163">La figure illustre les étapes des travaux de sauvegarde, copie et restauration :</span><span class="sxs-lookup"><span data-stu-id="a5b46-163">The figure illustrates the steps performed by backup, copy, and restorejobs, as follows:</span></span>  
  
1.  <span data-ttu-id="a5b46-164">L'instance du serveur principal effectue le travail de sauvegarde pour sauvegarder le journal des transactions sur la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="a5b46-164">The primary server instance runs the backup job to back up the transaction log on the primary database.</span></span> <span data-ttu-id="a5b46-165">Cette instance de serveur place ensuite la sauvegarde du journal dans un fichier journal primaire de sauvegarde, qu'il envoie vers le dossier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a5b46-165">This server instance then places the log backup into a primary log-backup file, which it sends to the backup folder.</span></span>  <span data-ttu-id="a5b46-166">Dans cette figure, le dossier de sauvegarde se trouve dans un répertoire partagé (le *partage de sauvegarde*).</span><span class="sxs-lookup"><span data-stu-id="a5b46-166">In this figure, the backup folder is on a shared directory-the *backup share*.</span></span>  
  
2.  <span data-ttu-id="a5b46-167">Chacune des trois instances du serveur secondaire effectue son propre travail de copie pour copier le fichier journal primaire de sauvegarde dans son dossier local de destination propre.</span><span class="sxs-lookup"><span data-stu-id="a5b46-167">Each of the three secondary server instances runs its own copy job to copy the primary log-backup file to its own local destination folder.</span></span>  
  
3.  <span data-ttu-id="a5b46-168">Chaque instance du serveur secondaire effectue son propre travail de restauration pour restaurer la sauvegarde du journal à partir du dossier local de destination vers la base de données secondaire locale.</span><span class="sxs-lookup"><span data-stu-id="a5b46-168">Each secondary server instance runs its own restore job to restore the log backup from the local destination folder onto the local secondary database.</span></span>  
  
 <span data-ttu-id="a5b46-169">Les instances des serveurs principal et secondaire envoient leur propre historique et leur propre état vers l'instance du serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="a5b46-169">The primary and secondary server instances send their own history and status to the monitor server instance.</span></span>  
  
 <span data-ttu-id="a5b46-170">![Configuration affichant les travaux de sauvegarde, de copie et de restauration](../media/ls-typical-configuration.gif "Configuration affichant les travaux de sauvegarde, de copie et de restauration")</span><span class="sxs-lookup"><span data-stu-id="a5b46-170">![Configuration showing backup, copy, & restore jobs](../media/ls-typical-configuration.gif "Configuration showing backup, copy, & restore jobs")</span></span>  
  
##  <a name="interoperability"></a><a name="Interoperability"></a> <span data-ttu-id="a5b46-171">Interopérabilité</span><span class="sxs-lookup"><span data-stu-id="a5b46-171">Interoperability</span></span>  
 <span data-ttu-id="a5b46-172">La copie des journaux de transaction peut être utilisée avec les fonctionnalités ou les composants de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]suivants :</span><span class="sxs-lookup"><span data-stu-id="a5b46-172">Log shipping can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="a5b46-173">Conditions préalables à la migration de la copie des journaux de session vers groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-173">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
-   [<span data-ttu-id="a5b46-174">Mise en miroir de bases de données et copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-174">Database Mirroring and Log Shipping &#40;SQL Server&#41;</span></span>](../database-mirroring/database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="a5b46-175">Copie des journaux de transaction et réplication &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-175">Log Shipping and Replication &#40;SQL Server&#41;</span></span>](log-shipping-and-replication-sql-server.md)  
  
> [!NOTE]  
>  [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] <span data-ttu-id="a5b46-176">et la mise en miroir de bases de données s’excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="a5b46-176">and database mirroring are mutually exclusive.</span></span> <span data-ttu-id="a5b46-177">Une base de données configurée pour une de ces fonctionnalités ne peut pas être configurée pour l'autre.</span><span class="sxs-lookup"><span data-stu-id="a5b46-177">A database that is configured for one of these features cannot be configured for the other.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a5b46-178">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a5b46-178">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a5b46-179">Mise à niveau de la copie des journaux de transaction vers SQL Server 2014 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-179">Upgrade Log Shipping to SQL Server 2014 &#40;Transact-SQL&#41;</span></span>](upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [<span data-ttu-id="a5b46-180">Configurer la copie des journaux de transaction &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-180">Configure Log Shipping &#40;SQL Server&#41;</span></span>](configure-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="a5b46-181">Ajouter une base de données secondaire dans une configuration de copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-181">Add a Secondary Database to a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="a5b46-182">Supprimer une base de données secondaire dans une configuration de copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-182">Remove a Secondary Database from a Log Shipping Configuration &#40;SQL Server&#41;</span></span>](remove-a-secondary-database-from-a-log-shipping-configuration-sql-server.md)  
  
-   [<span data-ttu-id="a5b46-183">Supprimer la copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-183">Remove Log Shipping &#40;SQL Server&#41;</span></span>](remove-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="a5b46-184">Afficher le rapport de la copie des journaux de transaction &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-184">View the Log Shipping Report &#40;SQL Server Management Studio&#41;</span></span>](view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="a5b46-185">Surveiller la copie des journaux de transaction &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-185">Monitor Log Shipping &#40;Transact-SQL&#41;</span></span>](monitor-log-shipping-transact-sql.md)  
  
-   [<span data-ttu-id="a5b46-186">Basculer vers un serveur secondaire d’envoi de journaux &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-186">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="a5b46-187">Basculer vers un serveur secondaire d’envoi de journaux &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-187">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
-   [<span data-ttu-id="a5b46-188">Gestion des connexions et des travaux après un basculement de rôle &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-188">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="a5b46-189">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5b46-189">See Also</span></span>  
 [<span data-ttu-id="a5b46-190">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b46-190">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](../availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md)  
  
  
