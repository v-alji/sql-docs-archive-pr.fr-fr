---
title: Restaurer une sauvegarde du journal des transactions (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.options.f1
- sql12.swb.restoretlog.general.f1
helpviewer_keywords:
- restore log
- backing up transaction logs [SQL Server], restoring
- transaction log backups [SQL Server], restoring
- restoring transaction logs [SQL Server], restoring backups
- transaction log restores [SQL Server], SQL Server Management Studio
ms.assetid: 1de2b888-78a6-4fb2-a647-ba4bf097caf3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fe4bbc199d6555bd490d25f92491100b8bbfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612416"
---
# <a name="restore-a-transaction-log-backup-sql-server"></a><span data-ttu-id="d8b81-102">Restaurer une sauvegarde de journal des transactions (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d8b81-102">Restore a Transaction Log Backup (SQL Server)</span></span>
  <span data-ttu-id="d8b81-103">Cette rubrique explique comment restaurer une sauvegarde du journal des transactions dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8b81-103">This topic describes how to restore a transaction log backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d8b81-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d8b81-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d8b81-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d8b81-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d8b81-106">Composants requis</span><span class="sxs-lookup"><span data-stu-id="d8b81-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="d8b81-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d8b81-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d8b81-108">**Pour restaurer une sauvegarde de journal des transactions à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="d8b81-108">**To restore a transaction log backup, using:**</span></span>  
  
     [<span data-ttu-id="d8b81-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8b81-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d8b81-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8b81-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   [<span data-ttu-id="d8b81-111">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="d8b81-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d8b81-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d8b81-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d8b81-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="d8b81-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="d8b81-114">Ces sauvegardes doivent être restaurées dans l'ordre de leur création.</span><span class="sxs-lookup"><span data-stu-id="d8b81-114">Backups must be restored in the order in which they were created.</span></span> <span data-ttu-id="d8b81-115">Avant de pouvoir restaurer une sauvegarde donnée du journal des transactions, vous devez restaurer les sauvegardes antérieures suivantes sans annuler les transactions non validées, autrement dit avec l'option WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d8b81-115">Before you can restore a particular transaction log backup, you must first restore the following previous backups without rolling back uncommitted transactions, that is WITH NORECOVERY:</span></span>  
  
    -   <span data-ttu-id="d8b81-116">La sauvegarde complète de la base de données et la dernière sauvegarde différentielle, s'il en existe, effectuée avant la sauvegarde donnée du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="d8b81-116">The full database backup and the last differential backup, if any, taken before the particular transaction log backup.</span></span> <span data-ttu-id="d8b81-117">Avant de créer la sauvegarde complète ou différentielle de base de données la plus récente, la base de données devait utiliser le mode de restauration complète ou le mode de récupération utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="d8b81-117">Before the most recent full or differential database backup was created, the database must have been using the full recovery model or bulk-logged recovery model.</span></span>  
  
    -   <span data-ttu-id="d8b81-118">Toutes les sauvegardes du journal des transactions effectuées après la sauvegarde complète de la base de données ou la sauvegarde différentielle (si vous la restaurez), mais avant la sauvegarde donnée du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="d8b81-118">All transaction log backups taken after the full database backup or the differential backup (if you restore one) and before the particular transaction log backup.</span></span> <span data-ttu-id="d8b81-119">Les sauvegardes du journal doivent être appliquées dans l'ordre dans lequel elles ont été créées, sans rupture dans la séquence de journaux.</span><span class="sxs-lookup"><span data-stu-id="d8b81-119">Log backups must be applied in the sequence in which they were created, without any gaps in the log chain.</span></span>  
  
         <span data-ttu-id="d8b81-120">Pour plus d’informations sur les sauvegardes du journal des transactions, consultez [Sauvegardes des journaux de transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) et [Appliquer les sauvegardes du journal de transactions &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d8b81-120">For more information about transaction log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) and [Apply Transaction Log Backups &#40;SQL Server&#41;](apply-transaction-log-backups-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d8b81-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d8b81-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d8b81-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d8b81-122">Permissions</span></span>  
 <span data-ttu-id="d8b81-123">Les autorisations RESTORE sont attribuées aux rôles dont les informations d'appartenance sont toujours immédiatement accessibles à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="d8b81-123">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="d8b81-124">Étant donné que l’appartenance au rôle de base de données fixe ne peut être contrôlée que quand la base de données est accessible et non endommagée, ce qui n’est pas toujours le cas lorsque RESTORE est exécuté, les membres du rôle de base de données fixe **db_owner** ne détiennent pas d’autorisations RESTORE.</span><span class="sxs-lookup"><span data-stu-id="d8b81-124">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d8b81-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d8b81-125">Using SQL Server Management Studio</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d8b81-126">La procédure de restauration normale consiste à sélectionner les sauvegardes des journaux dans la boîte de dialogue **Restaurer la base de données** en même temps que les sauvegardes de données et les sauvegardes différentielles.</span><span class="sxs-lookup"><span data-stu-id="d8b81-126">The normal process of a restore is to select the log backups in the **Restore Database** dialog box along with the data and differential backups.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="d8b81-127">Pour restaurer une sauvegarde de journal des transactions</span><span class="sxs-lookup"><span data-stu-id="d8b81-127">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="d8b81-128">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="d8b81-128">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="d8b81-129">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="d8b81-129">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="d8b81-130">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, pointez sur **Restaurer**, puis cliquez sur **Journal des transactions**, pour ouvrir la boîte de dialogue **Restaurer le journal des transactions** .</span><span class="sxs-lookup"><span data-stu-id="d8b81-130">Right-click the database, point to **Tasks**, point to **Restore**, and then click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d8b81-131">Si **Journal des transactions** est grisé, dans un premier temps, vous devrez peut-être restaurer une sauvegarde complète ou différentielle.</span><span class="sxs-lookup"><span data-stu-id="d8b81-131">If **Transaction Log** is grayed out, you may need to restore a full or differential backup first.</span></span> <span data-ttu-id="d8b81-132">Utilisez la boîte de dialogue **Sauvegarde de la base de données** .</span><span class="sxs-lookup"><span data-stu-id="d8b81-132">Use the **Database** backup dialog box.</span></span>  
  
4.  <span data-ttu-id="d8b81-133">Dans la zone de liste **Base de données** de la page **Général** , sélectionnez le nom d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="d8b81-133">On the **General** page, in the **Database** list box, select the name of a database.</span></span> <span data-ttu-id="d8b81-134">Seules les bases de données en état de restauration sont répertoriées.</span><span class="sxs-lookup"><span data-stu-id="d8b81-134">Only databases in the restoring state are listed.</span></span>  
  
5.  <span data-ttu-id="d8b81-135">Pour préciser la source et l'emplacement des jeux de sauvegarde à restaurer, cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d8b81-135">To specify the source and location of the backup sets to restore, click one of the following options:</span></span>  
  
    -   <span data-ttu-id="d8b81-136">**À partir de sauvegardes précédentes de la base de données**</span><span class="sxs-lookup"><span data-stu-id="d8b81-136">**From previous backups of database**</span></span>  
  
         <span data-ttu-id="d8b81-137">Sélectionnez la base de données à restaurer dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="d8b81-137">Select the database to restore from the drop-down list.</span></span> <span data-ttu-id="d8b81-138">La liste contient uniquement les bases de données qui ont été sauvegardées selon l'historique de sauvegarde **msdb** .</span><span class="sxs-lookup"><span data-stu-id="d8b81-138">The list contains only databases that have been backed up according to the **msdb** backup history.</span></span>  
  
    -   <span data-ttu-id="d8b81-139">**À partir d'un fichier ou d'une bande**</span><span class="sxs-lookup"><span data-stu-id="d8b81-139">**From file or tape**</span></span>  
  
         <span data-ttu-id="d8b81-140">Cliquez sur le bouton Parcourir ( **...** ) pour ouvrir la boîte de dialogue **Sélectionner les unités de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="d8b81-140">Click the browse (**...**) button to open the **Select backup devices** dialog box.</span></span> <span data-ttu-id="d8b81-141">Dans la zone **Type du média de sauvegarde** , sélectionnez l'un des types d'unités proposés.</span><span class="sxs-lookup"><span data-stu-id="d8b81-141">In the **Backup media type** box, select one of the listed device types.</span></span> <span data-ttu-id="d8b81-142">Pour sélectionner une ou plusieurs unités pour la zone **Support de sauvegarde** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d8b81-142">To select one or more devices for the **Backup media** box, click **Add**.</span></span>  
  
         <span data-ttu-id="d8b81-143">Après avoir ajouté les unités souhaitées à la zone de liste **Support de sauvegarde** , cliquez sur **OK** pour revenir à la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="d8b81-143">After you add the devices you want to the **Backup media** list box, click **OK** to return to the **General** page.</span></span>  
  
6.  <span data-ttu-id="d8b81-144">Dans la grille **Sélectionner les sauvegardes du journal des transactions à restaurer** , sélectionnez les sauvegardes à restaurer.</span><span class="sxs-lookup"><span data-stu-id="d8b81-144">In the **Select the transaction log backups to restore** grid, select the backups to restore.</span></span> <span data-ttu-id="d8b81-145">Cette grille répertorie les sauvegardes du journal des transactions disponibles pour la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d8b81-145">This grid lists the transaction log backups available for the selected database.</span></span> <span data-ttu-id="d8b81-146">Une sauvegarde du journal n'est disponible que si son **Premier NSE** est supérieur au **Dernier NSE** de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d8b81-146">A log backup is available only if its **First LSN** greater than the **Last LSN** of the database.</span></span> <span data-ttu-id="d8b81-147">Les sauvegardes des journaux sont affichées dans l'ordre des numéros séquentiels dans le journal (NSE) qu'elles contiennent et elles doivent être restaurées dans cet ordre.</span><span class="sxs-lookup"><span data-stu-id="d8b81-147">Log backups are listed in the order of the log sequence numbers (LSN) they contain, and they must be restored in this order.</span></span>  
  
     <span data-ttu-id="d8b81-148">Le tableau suivant répertorie les en-têtes de colonnes de la grille et décrit leur valeur.</span><span class="sxs-lookup"><span data-stu-id="d8b81-148">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="d8b81-149">En-tête</span><span class="sxs-lookup"><span data-stu-id="d8b81-149">Header</span></span>|<span data-ttu-id="d8b81-150">Valeur</span><span class="sxs-lookup"><span data-stu-id="d8b81-150">Value</span></span>|  
    |------------|-----------|  
    |<span data-ttu-id="d8b81-151">**Restauration**</span><span class="sxs-lookup"><span data-stu-id="d8b81-151">**Restore**</span></span>|<span data-ttu-id="d8b81-152">Les cases à cocher indiquent les jeux de sauvegarde à restaurer.</span><span class="sxs-lookup"><span data-stu-id="d8b81-152">Selected check boxes indicate the backup sets to be restored.</span></span>|  
    |<span data-ttu-id="d8b81-153">**Nom**</span><span class="sxs-lookup"><span data-stu-id="d8b81-153">**Name**</span></span>|<span data-ttu-id="d8b81-154">Nom du jeu de sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="d8b81-154">Name of the backup set.</span></span>|  
    |<span data-ttu-id="d8b81-155">**Composant**</span><span class="sxs-lookup"><span data-stu-id="d8b81-155">**Component**</span></span>|<span data-ttu-id="d8b81-156">Composant de sauvegarde : **Base de données**, **Fichier** ou \<blank> (pour les journaux des transactions).</span><span class="sxs-lookup"><span data-stu-id="d8b81-156">Backed-up component: **Database**, **File**, or \<blank> (for transaction logs).</span></span>|  
    |<span data-ttu-id="d8b81-157">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="d8b81-157">**Database**</span></span>|<span data-ttu-id="d8b81-158">Nom de la base de données impliquée dans la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d8b81-158">Name of the database involved in the backup operation.</span></span>|  
    |<span data-ttu-id="d8b81-159">**Date de début**</span><span class="sxs-lookup"><span data-stu-id="d8b81-159">**Start Date**</span></span>|<span data-ttu-id="d8b81-160">Date et heure de début de la sauvegarde, d'après les paramètres régionaux du client.</span><span class="sxs-lookup"><span data-stu-id="d8b81-160">Date and time when the backup operation began, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="d8b81-161">**Date de fin**</span><span class="sxs-lookup"><span data-stu-id="d8b81-161">**Finish Date**</span></span>|<span data-ttu-id="d8b81-162">Date et heure de fin de la sauvegarde, d'après les paramètres régionaux du client.</span><span class="sxs-lookup"><span data-stu-id="d8b81-162">Date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
    |<span data-ttu-id="d8b81-163">**Premier NSE**</span><span class="sxs-lookup"><span data-stu-id="d8b81-163">**First LSN**</span></span>|<span data-ttu-id="d8b81-164">Numéro séquentiel dans le journal correspondant à la première transaction dans le jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d8b81-164">Log sequence number of the first transaction in the backup set.</span></span> <span data-ttu-id="d8b81-165">Vide pour les sauvegardes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d8b81-165">Blank for file backups.</span></span>|  
    |<span data-ttu-id="d8b81-166">**Dernier NSE**</span><span class="sxs-lookup"><span data-stu-id="d8b81-166">**Last LSN**</span></span>|<span data-ttu-id="d8b81-167">Numéro séquentiel dans le journal correspondant à la dernière transaction dans le jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d8b81-167">Log sequence number of the last transaction in the backup set.</span></span> <span data-ttu-id="d8b81-168">Vide pour les sauvegardes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d8b81-168">Blank for file backups.</span></span>|  
    |<span data-ttu-id="d8b81-169">**NSE du point de contrôle**</span><span class="sxs-lookup"><span data-stu-id="d8b81-169">**Checkpoint LSN**</span></span>|<span data-ttu-id="d8b81-170">Numéro séquentiel dans le journal correspondant au point de contrôle le plus récent au moment où la sauvegarde a été créée.</span><span class="sxs-lookup"><span data-stu-id="d8b81-170">Log sequence number of the most recent checkpoint at the time the backup was created.</span></span>|  
    |<span data-ttu-id="d8b81-171">**Tous les NSE**</span><span class="sxs-lookup"><span data-stu-id="d8b81-171">**Full LSN**</span></span>|<span data-ttu-id="d8b81-172">Numéro séquentiel dans le journal correspondant à la sauvegarde complète la plus récente de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d8b81-172">Log sequence number of the most recent full database backup.</span></span>|  
    |<span data-ttu-id="d8b81-173">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="d8b81-173">**Server**</span></span>|<span data-ttu-id="d8b81-174">Nom de l'instance du moteur de base de données qui a effectué l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d8b81-174">Name of the Database Engine instance that performed the backup operation.</span></span>|  
    |<span data-ttu-id="d8b81-175">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="d8b81-175">**User Name**</span></span>|<span data-ttu-id="d8b81-176">Nom de l'utilisateur qui a effectué la restauration.</span><span class="sxs-lookup"><span data-stu-id="d8b81-176">Name of the user who performed the backup operation.</span></span>|  
    |<span data-ttu-id="d8b81-177">**Taille**</span><span class="sxs-lookup"><span data-stu-id="d8b81-177">**Size**</span></span>|<span data-ttu-id="d8b81-178">Taille du jeu de sauvegarde en octets.</span><span class="sxs-lookup"><span data-stu-id="d8b81-178">Size of the backup set in bytes.</span></span>|  
    |<span data-ttu-id="d8b81-179">**Position**</span><span class="sxs-lookup"><span data-stu-id="d8b81-179">**Position**</span></span>|<span data-ttu-id="d8b81-180">Position du jeu de sauvegarde dans le volume</span><span class="sxs-lookup"><span data-stu-id="d8b81-180">Position of the backup set in the volume.</span></span>|  
    |<span data-ttu-id="d8b81-181">**Expiration**</span><span class="sxs-lookup"><span data-stu-id="d8b81-181">**Expiration**</span></span>|<span data-ttu-id="d8b81-182">Date et heure d'expiration du jeu de sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="d8b81-182">Date and time the backup set expires.</span></span>|  
  
7.  <span data-ttu-id="d8b81-183">Sélectionnez l’un des suivants :</span><span class="sxs-lookup"><span data-stu-id="d8b81-183">Select one of the following:</span></span>  
  
    -   <span data-ttu-id="d8b81-184">**Limite dans le temps**</span><span class="sxs-lookup"><span data-stu-id="d8b81-184">**Point in time**</span></span>  
  
         <span data-ttu-id="d8b81-185">Conservez la valeur par défaut (**Le plus récent possible**) ou sélectionnez une date et une heure données en cliquant sur le bouton d’exploration pour ouvrir la boîte de dialogue **Limite de restauration dans le temps** .</span><span class="sxs-lookup"><span data-stu-id="d8b81-185">Either retain the default (**Most recent possible**) or select a specific date and time by clicking the browse button, which opens the **Point in Time Restore** dialog box.</span></span>  
  
    -   <span data-ttu-id="d8b81-186">**Transaction marquée**</span><span class="sxs-lookup"><span data-stu-id="d8b81-186">**Marked transaction**</span></span>  
  
         <span data-ttu-id="d8b81-187">Restaurez la base de données jusqu'à une transaction marquée auparavant.</span><span class="sxs-lookup"><span data-stu-id="d8b81-187">Restore the database to a previously marked transaction.</span></span> <span data-ttu-id="d8b81-188">Cette option ouvre la boîte de dialogue **Sélectionner une transaction marquée** . Celle-ci affiche une grille qui répertorie les transactions marquées disponibles dans les sauvegardes du journal des transactions sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="d8b81-188">Selecting this option launches the **Select Marked Transaction** dialog box, which displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
         <span data-ttu-id="d8b81-189">Par défaut, la restauration s'effectue jusqu'à la transaction marquée, en l'excluant.</span><span class="sxs-lookup"><span data-stu-id="d8b81-189">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="d8b81-190">Pour restaurer également la transaction marquée, sélectionnez **Inclure la transaction marquée**.</span><span class="sxs-lookup"><span data-stu-id="d8b81-190">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
         <span data-ttu-id="d8b81-191">Le tableau suivant répertorie les en-têtes de colonnes de la grille et décrit leur valeur.</span><span class="sxs-lookup"><span data-stu-id="d8b81-191">The following table lists the column headers of the grid and describes their values.</span></span>  
  
        |<span data-ttu-id="d8b81-192">En-tête</span><span class="sxs-lookup"><span data-stu-id="d8b81-192">Header</span></span>|<span data-ttu-id="d8b81-193">Valeur</span><span class="sxs-lookup"><span data-stu-id="d8b81-193">Value</span></span>|  
        |------------|-----------|  
        |\<blank>|<span data-ttu-id="d8b81-194">Affiche une case à cocher pour la sélection de la marque.</span><span class="sxs-lookup"><span data-stu-id="d8b81-194">Displays a checkbox for selecting the mark.</span></span>|  
        |<span data-ttu-id="d8b81-195">**Marque de transaction**</span><span class="sxs-lookup"><span data-stu-id="d8b81-195">**Transaction Mark**</span></span>|<span data-ttu-id="d8b81-196">Nom de la transaction marquée spécifiée par l'utilisateur lors de la validation de la transaction.</span><span class="sxs-lookup"><span data-stu-id="d8b81-196">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
        |<span data-ttu-id="d8b81-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="d8b81-197">**Date**</span></span>|<span data-ttu-id="d8b81-198">Date et heure de la validation de la transaction.</span><span class="sxs-lookup"><span data-stu-id="d8b81-198">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="d8b81-199">La date et l’heure sont affichées telles qu’enregistrées dans la table **msdbgmarkhistory** , et non dans l’option Date et heure de l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="d8b81-199">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
        |<span data-ttu-id="d8b81-200">**Description**</span><span class="sxs-lookup"><span data-stu-id="d8b81-200">**Description**</span></span>|<span data-ttu-id="d8b81-201">Description de la transaction marquée spécifiée par l'utilisateur lorsque la transaction a été validée (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="d8b81-201">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
        |<span data-ttu-id="d8b81-202">**LSN**</span><span class="sxs-lookup"><span data-stu-id="d8b81-202">**LSN**</span></span>|<span data-ttu-id="d8b81-203">Numéro séquentiel dans le journal de la transaction marquée.</span><span class="sxs-lookup"><span data-stu-id="d8b81-203">Log sequence number of the marked transaction.</span></span>|  
        |<span data-ttu-id="d8b81-204">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="d8b81-204">**Database**</span></span>|<span data-ttu-id="d8b81-205">Nom de la base de données où la transaction marquée a été validée.</span><span class="sxs-lookup"><span data-stu-id="d8b81-205">Name of the database where the marked transaction was committed.</span></span>|  
        |<span data-ttu-id="d8b81-206">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="d8b81-206">**User Name**</span></span>|<span data-ttu-id="d8b81-207">Nom de l'utilisateur de la base de données où la transaction marquée a été validée.</span><span class="sxs-lookup"><span data-stu-id="d8b81-207">Name of the database user who committed the marked transaction.</span></span>|  
  
8.  <span data-ttu-id="d8b81-208">Pour afficher ou sélectionner les options avancées, cliquez sur **Options** dans le volet **Sélectionner une page** .</span><span class="sxs-lookup"><span data-stu-id="d8b81-208">To view or select the advanced options, click **Options** in the **Select a page** pane.</span></span>  
  
9. <span data-ttu-id="d8b81-209">Dans la section **Options de restauration** , les options sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="d8b81-209">In the **Restore options** section, the choices are:</span></span>  
  
    -   <span data-ttu-id="d8b81-210">**Conserver les paramètres de la réplication (WITH KEEP_REPLICATION)**</span><span class="sxs-lookup"><span data-stu-id="d8b81-210">**Preserve the replication settings (WITH KEEP_REPLICATION)**</span></span>  
  
         <span data-ttu-id="d8b81-211">Conserve les paramètres de réplication lors de la restauration d'une base de données publiée sur un serveur autre que celui sur lequel la base de données a été créée.</span><span class="sxs-lookup"><span data-stu-id="d8b81-211">Preserves the replication settings when restoring a published database to a server other than the server where the database was created.</span></span>  
  
         <span data-ttu-id="d8b81-212">Cette option est disponible uniquement avec l’option **conserver la base de données opérationnelle en annulant les transactions non validées...** (décrite plus loin), ce qui équivaut à restaurer une sauvegarde avec l' `RECOVERY` option.</span><span class="sxs-lookup"><span data-stu-id="d8b81-212">This option is available only with the **Leave the database ready for use by rolling back the uncommitted transactions...** option (described later), which is equivalent to restoring a backup with the `RECOVERY` option.</span></span>  
  
         <span data-ttu-id="d8b81-213">L’activation de cette option revient à utiliser l' `KEEP_REPLICATION` option dans une [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instruction.</span><span class="sxs-lookup"><span data-stu-id="d8b81-213">Checking this option is equivalent to using the `KEEP_REPLICATION` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
    -   <span data-ttu-id="d8b81-214">**Demander confirmation avant chaque restauration de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="d8b81-214">**Prompt before restoring each backup**</span></span>  
  
         <span data-ttu-id="d8b81-215">Avant de restaurer chaque jeu de sauvegarde (après la première), cette option affiche la boîte de dialogue **Continuer la restauration** qui vous invite à préciser si vous voulez continuer la séquence de restauration.</span><span class="sxs-lookup"><span data-stu-id="d8b81-215">Before restoring each backup set (after the first), this option brings up the **Continue with Restore** dialog box, which asks you to indicate whether you want to continue the restore sequence.</span></span> <span data-ttu-id="d8b81-216">Ce dialogue affiche le nom du support de sauvegarde suivant (s'il est disponible), ainsi que le nom et la description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d8b81-216">This dialog displays the name of the next media set (if available), the backup set name, and backup set description.</span></span>  
  
         <span data-ttu-id="d8b81-217">Cette option est particulièrement utile lorsque vous devez changer des bandes de différents supports de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d8b81-217">This option is particularly useful when you must swap tapes for different media sets.</span></span> <span data-ttu-id="d8b81-218">Vous pouvez par exemple l'utiliser lorsque le serveur n'a qu'un périphérique à bandes.</span><span class="sxs-lookup"><span data-stu-id="d8b81-218">For example, you can use it when the server has only one tape device.</span></span> <span data-ttu-id="d8b81-219">Attendez d'être prêt à continuer avant de cliquer sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8b81-219">Wait until you are ready to proceed before clicking **OK**.</span></span>  
  
         <span data-ttu-id="d8b81-220">Cliquez sur **Non** pour laisser la base de données dans l'état de restauration.</span><span class="sxs-lookup"><span data-stu-id="d8b81-220">Clicking **No** leaves the database in the restoring state.</span></span> <span data-ttu-id="d8b81-221">Si vous le souhaitez, vous pouvez poursuivre la séquence de restauration lorsque la dernière restauration est terminée.</span><span class="sxs-lookup"><span data-stu-id="d8b81-221">At your convenience, you can continue the restore sequence after the last restore that completed.</span></span> <span data-ttu-id="d8b81-222">Si la sauvegarde suivante est une sauvegarde de données ou différentielle, utilisez à nouveau la tâche **Restaurer la base de données** .</span><span class="sxs-lookup"><span data-stu-id="d8b81-222">If the next backup is a data or differential backup, use the **Restore Database** task again.</span></span> <span data-ttu-id="d8b81-223">S'il s'agit d'une sauvegarde de journal, utilisez la tâche **Restaurer le journal des transactions** .</span><span class="sxs-lookup"><span data-stu-id="d8b81-223">If the next backup is a log backup, use the **Restore Transaction Log** task.</span></span>  
  
    -   <span data-ttu-id="d8b81-224">**Restreindre l'accès à la base de données restaurée (WITH RESTRICTED_USER)**</span><span class="sxs-lookup"><span data-stu-id="d8b81-224">**Restrict access to the restored database (WITH RESTRICTED_USER)**</span></span>  
  
         <span data-ttu-id="d8b81-225">Limite l’accès à la base de données restaurée aux membres de **db_owner**, **dbcreator**ou **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="d8b81-225">Makes the restored database available only to the members of **db_owner**, **dbcreator**, or **sysadmin**.</span></span>  
  
         <span data-ttu-id="d8b81-226">L’activation de cette option revient à utiliser l' `RESTRICTED_USER` option dans une [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instruction.</span><span class="sxs-lookup"><span data-stu-id="d8b81-226">Checking this option is synonymous to using the `RESTRICTED_USER` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
10. <span data-ttu-id="d8b81-227">Pour les options **État de récupération** , spécifiez l'état de la base de données après la restauration.</span><span class="sxs-lookup"><span data-stu-id="d8b81-227">For the **Recovery state** options, specify the state of the database after the restore operation.</span></span>  
  
    -   <span data-ttu-id="d8b81-228">**Laisser la base de données opérationnelle en restaurant les transactions non validées. Les journaux des transactions supplémentaires ne peuvent pas être restaurés. (RESTORE WITH RECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="d8b81-228">**Leave the database ready for use by rolling back uncommitted transactions. Additional transaction logs cannot be restored. (RESTORE WITH RECOVERY)**</span></span>  
  
         <span data-ttu-id="d8b81-229">Récupère la base de données.</span><span class="sxs-lookup"><span data-stu-id="d8b81-229">Recovers the database.</span></span> <span data-ttu-id="d8b81-230">Cette option est équivalente à l' `RECOVERY` option dans une [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instruction.</span><span class="sxs-lookup"><span data-stu-id="d8b81-230">This option is equivalent to the `RECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="d8b81-231">Choisissez cette option uniquement si vous ne voulez restaurer aucun fichier journal.</span><span class="sxs-lookup"><span data-stu-id="d8b81-231">Choose this option only if you have no log files you want to restore.</span></span>  
  
    -   <span data-ttu-id="d8b81-232">**Laisser la base de données non opérationnelle, et ne pas restaurer les transactions non validées. Les journaux des transactions supplémentaires peuvent être restaurés. (RESTORE WITH NORECOVERY)**</span><span class="sxs-lookup"><span data-stu-id="d8b81-232">**Leave the database non-operational, and do not roll back uncommitted transactions. Additional transaction logs can be restored. (RESTORE WITH NORECOVERY)**</span></span>  
  
         <span data-ttu-id="d8b81-233">Laisse la base de données non récupérée dans l'état `RESTORING`.</span><span class="sxs-lookup"><span data-stu-id="d8b81-233">Leaves the database unrecovered, in the `RESTORING` state.</span></span> <span data-ttu-id="d8b81-234">Cette option équivaut à utiliser l' `NORECOVERY` option dans une [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instruction.</span><span class="sxs-lookup"><span data-stu-id="d8b81-234">This option is equivalent to using the `NORECOVERY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="d8b81-235">Lorsque vous la choisissez, l'option **Conserver les paramètres de réplication** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d8b81-235">When you choose this option, the **Preserve replication settings** option is unavailable.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="d8b81-236">Pour une base de données secondaire ou miroir, sélectionnez toujours cette option.</span><span class="sxs-lookup"><span data-stu-id="d8b81-236">For a mirror or secondary database, always select this option.</span></span>  
  
    -   <span data-ttu-id="d8b81-237">**Laisser la base de données en lecture seule. Annulez les transactions non validées, mais enregistrez les actions d'annulation dans un fichier d'annulation afin de rendre réversibles les effets de la récupération. (RESTORE WITH STANDBY)**</span><span class="sxs-lookup"><span data-stu-id="d8b81-237">**Leave the database in read-only mode. Undo uncommitted transactions, but save the undo actions in a file so that recovery effects can be reversed. (RESTORE WITH STANDBY)**</span></span>  
  
         <span data-ttu-id="d8b81-238">Laisse la base de données dans un état de secours.</span><span class="sxs-lookup"><span data-stu-id="d8b81-238">Leaves the database in a standby state.</span></span> <span data-ttu-id="d8b81-239">Cette option équivaut à utiliser l' `STANDBY` option dans une [!INCLUDE[tsql](../../includes/tsql-md.md)] `RESTORE` instruction.</span><span class="sxs-lookup"><span data-stu-id="d8b81-239">This option is equivalent to using the `STANDBY` option in a [!INCLUDE[tsql](../../includes/tsql-md.md)]`RESTORE` statement.</span></span>  
  
         <span data-ttu-id="d8b81-240">Cette option nécessite de définir un fichier d'annulation.</span><span class="sxs-lookup"><span data-stu-id="d8b81-240">Choosing this option requires that you specify a standby file.</span></span>  
  
11. <span data-ttu-id="d8b81-241">Éventuellement, spécifiez un nom de fichier d'annulation dans la zone de texte **Fichiers d'annulation** .</span><span class="sxs-lookup"><span data-stu-id="d8b81-241">Optionally, specify a standby file name in the **Standby file** text box.</span></span> <span data-ttu-id="d8b81-242">Cette option est indispensable si vous laissez la base de données en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="d8b81-242">This option is required if you leave the database in read-only mode.</span></span> <span data-ttu-id="d8b81-243">Vous pouvez rechercher le fichier d'annulation ou taper son chemin d'accès dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="d8b81-243">You can browse for the standby file or type its pathname in the text box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d8b81-244">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8b81-244">Using Transact-SQL</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d8b81-245">Nous vous recommandons de toujours préciser de façon claire WITH NORECOVERY ou WITH RECOVERY dans chaque instruction RESTORE pour éliminer toute ambiguïté.</span><span class="sxs-lookup"><span data-stu-id="d8b81-245">We recommend that you always explicitly specify either WITH NORECOVERY or WITH RECOVERY in every RESTORE statement to eliminate ambiguity.</span></span> <span data-ttu-id="d8b81-246">Cela est particulièrement important lors de l'écriture de scripts.</span><span class="sxs-lookup"><span data-stu-id="d8b81-246">This is particularly important when writing scripts.</span></span>  
  
#### <a name="to-restore-a-transaction-log-backup"></a><span data-ttu-id="d8b81-247">Pour restaurer une sauvegarde de journal des transactions</span><span class="sxs-lookup"><span data-stu-id="d8b81-247">To restore a transaction log backup</span></span>  
  
1.  <span data-ttu-id="d8b81-248">Exécutez l'instruction RESTORE LOG pour appliquer la sauvegarde du journal des transactions, en spécifiant :</span><span class="sxs-lookup"><span data-stu-id="d8b81-248">Execute the RESTORE LOG statement to apply the transaction log backup, specifying:</span></span>  
  
    -   <span data-ttu-id="d8b81-249">le nom de la base de données à laquelle sera appliqué le journal des transactions ;</span><span class="sxs-lookup"><span data-stu-id="d8b81-249">The name of the database to which the transaction log will be applied.</span></span>  
  
    -   <span data-ttu-id="d8b81-250">l'unité de sauvegarde à partir de laquelle sera restaurée la sauvegarde du journal des transactions ;</span><span class="sxs-lookup"><span data-stu-id="d8b81-250">The backup device where the transaction log backup will be restored from.</span></span>  
  
    -   <span data-ttu-id="d8b81-251">la clause NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d8b81-251">The NORECOVERY clause.</span></span>  
  
     <span data-ttu-id="d8b81-252">La syntaxe de base pour cette instruction est la suivante :</span><span class="sxs-lookup"><span data-stu-id="d8b81-252">The basic syntax for this statement is as follows:</span></span>  
  
     <span data-ttu-id="d8b81-253">RESTORE LOG *nom_base_de_données* FROM <unité_de_sauvegarde> WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="d8b81-253">RESTORE LOG *database_name* FROM <backup_device> WITH NORECOVERY.</span></span>  
  
     <span data-ttu-id="d8b81-254">Où *nom_base_de_données* représente le nom de la base de données et <unité_de_sauvegarde> correspond au nom de l’unité qui contient la sauvegarde du journal en cours de restauration.</span><span class="sxs-lookup"><span data-stu-id="d8b81-254">Where *database_name* is the name of database and <backup_device>is the name of the device that contains the log backup being restored.</span></span>  
  
2.  <span data-ttu-id="d8b81-255">Répétez l'étape 1 pour chaque sauvegarde du journal des transactions à appliquer.</span><span class="sxs-lookup"><span data-stu-id="d8b81-255">Repeat step 1 for each transaction log backup you have to apply.</span></span>  
  
3.  <span data-ttu-id="d8b81-256">Après avoir restauré la dernière sauvegarde de votre séquence de restauration, utilisez l'une des instructions ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="d8b81-256">After restoring the last backup in your restore sequence, to recover the database use one of the following statements:</span></span>  
  
    -   <span data-ttu-id="d8b81-257">Récupérer la base de données dans le cadre de la dernière instruction RESTORE LOG :</span><span class="sxs-lookup"><span data-stu-id="d8b81-257">Recover the database as part of the last RESTORE LOG statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH RECOVERY;  
        GO  
        ```  
  
    -   <span data-ttu-id="d8b81-258">attendre de récupérer la base de données à l'aide d'une instruction séparée RESTORE DATABASE :</span><span class="sxs-lookup"><span data-stu-id="d8b81-258">Wait to recover the database by using a separate RESTORE DATABASE statement:</span></span>  
  
        ```  
        RESTORE LOG <database_name> FROM <backup_device> WITH NORECOVERY;   
        RESTORE DATABASE <database_name> WITH RECOVERY;  
        GO  
        ```  
  
         <span data-ttu-id="d8b81-259">Attendre de récupérer la base de données vous permet de vérifier si vous avez restauré toutes les sauvegardes de journaux nécessaires.</span><span class="sxs-lookup"><span data-stu-id="d8b81-259">Waiting to recover the database gives you the opportunity to verify that you have restored all of the necessary log backups.</span></span> <span data-ttu-id="d8b81-260">Cette méthode est souvent conseillée si vous effectuez une restauration limitée dans le temps.</span><span class="sxs-lookup"><span data-stu-id="d8b81-260">This approach is often advisable when you are performing a point-in-time restore.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d8b81-261">Si vous créez une base de données miroir, omettez l'étape de récupération.</span><span class="sxs-lookup"><span data-stu-id="d8b81-261">If you are creating a mirror database, omit the recovery step.</span></span> <span data-ttu-id="d8b81-262">Une base de données miroir doit rester dans l'état RESTORING.</span><span class="sxs-lookup"><span data-stu-id="d8b81-262">A mirror database must remain in the RESTORING state.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="d8b81-263">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d8b81-263">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="d8b81-264">Par défaut, la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] utilise le mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="d8b81-264">By default, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database uses the simple recovery model.</span></span> <span data-ttu-id="d8b81-265">Les exemples suivants nécessitent la modification de la base de données pour utiliser le mode de restauration complète, comme suit :</span><span class="sxs-lookup"><span data-stu-id="d8b81-265">The following examples require modifying the database to use the full recovery model, as follows:</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
```  
  
#### <a name="a-applying-a-single-transaction-log-backup"></a><span data-ttu-id="d8b81-266">R.</span><span class="sxs-lookup"><span data-stu-id="d8b81-266">A.</span></span> <span data-ttu-id="d8b81-267">Application d'une sauvegarde unique du journal des transactions</span><span class="sxs-lookup"><span data-stu-id="d8b81-267">Applying a single transaction log backup</span></span>  
 <span data-ttu-id="d8b81-268">Dans cet exemple, nous commençons par restaurer la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] à l'aide d'une sauvegarde complète de base de données qui réside sur une unité de sauvegarde nommée `AdventureWorks2012_1`.</span><span class="sxs-lookup"><span data-stu-id="d8b81-268">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="d8b81-269">Nous appliquons ensuite la première sauvegarde du journal des transactions qui réside sur une unité de sauvegarde nommée `AdventureWorks2012_log`.</span><span class="sxs-lookup"><span data-stu-id="d8b81-269">The example then applies the first transaction log backup that resides on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="d8b81-270">Enfin, nous récupérons la base de données.</span><span class="sxs-lookup"><span data-stu-id="d8b81-270">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
#### <a name="b-applying-multiple-transaction-log-backups"></a><span data-ttu-id="d8b81-271">B.</span><span class="sxs-lookup"><span data-stu-id="d8b81-271">B.</span></span> <span data-ttu-id="d8b81-272">Application de plusieurs sauvegardes du journal des transactions</span><span class="sxs-lookup"><span data-stu-id="d8b81-272">Applying multiple transaction log backups</span></span>  
 <span data-ttu-id="d8b81-273">Dans cet exemple, nous commençons par restaurer la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] à l'aide d'une sauvegarde complète de base de données qui réside sur une unité de sauvegarde nommée `AdventureWorks2012_1`.</span><span class="sxs-lookup"><span data-stu-id="d8b81-273">The following example starts by restoring the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database by using a full database backup that resides on a backup device named `AdventureWorks2012_1`.</span></span> <span data-ttu-id="d8b81-274">Nous appliquons ensuite, successivement, les premières sauvegardes du journal des transactions qui résident sur une unité de sauvegarde nommée `AdventureWorks2012_log`.</span><span class="sxs-lookup"><span data-stu-id="d8b81-274">The example then applies, one by one, the first three transaction log backups that reside on a backup device named `AdventureWorks2012_log`.</span></span> <span data-ttu-id="d8b81-275">Enfin, nous récupérons la base de données.</span><span class="sxs-lookup"><span data-stu-id="d8b81-275">Finally, the example recovers the database.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM AdventureWorks2012_1  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 1,  
   NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 2,  
   WITH NORECOVERY;  
GO  
RESTORE LOG AdventureWorks2012  
   FROM AdventureWorks2012_log  
   WITH FILE = 3,  
   WITH NORECOVERY;  
GO  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d8b81-276">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="d8b81-276">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d8b81-277">Sauvegarder un journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b81-277">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="d8b81-278">Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b81-278">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="d8b81-279">Restaurer une base de données jusqu’au point d’échec en mode de récupération complète &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b81-279">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="d8b81-280">Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b81-280">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
-   [<span data-ttu-id="d8b81-281">Restaurer une base de données jusqu’à une transaction marquée &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b81-281">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8b81-282">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8b81-282">See Also</span></span>  
 <span data-ttu-id="d8b81-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d8b81-283">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="d8b81-284">Appliquer les sauvegardes du journal de transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d8b81-284">Apply Transaction Log Backups &#40;SQL Server&#41;</span></span>](apply-transaction-log-backups-sql-server.md)  
  
  
