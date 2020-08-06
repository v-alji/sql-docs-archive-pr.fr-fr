---
title: Afficher ou modifier le mode de récupération d’une base de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], recovery models
- recovery [SQL Server], recovery model
- backing up databases [SQL Server], recovery models
- recovery models [SQL Server], switching
- recovery models [SQL Server], viewing
- database restores [SQL Server], recovery models
- modifying database recovery models
ms.assetid: 94918d1d-7c10-4be7-bf9f-27e00b003a0f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 889080301109938f0514bd6b81265c100237ab60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703012"
---
# <a name="view-or-change-the-recovery-model-of-a-database-sql-server"></a><span data-ttu-id="e998f-102">Afficher ou modifier le mode de récupération d'une base de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e998f-102">View or Change the Recovery Model of a Database (SQL Server)</span></span>
  <span data-ttu-id="e998f-103">Cette rubrique explique comment afficher ou modifier le mode de récupération d'une base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e998f-103">This topic describes how to view or change the recovery model of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e998f-104">Un *mode de récupération* est une propriété de base de données qui contrôle la façon dont les transactions sont journalisées, précise si le journal des transactions nécessite (et permet) une sauvegarde et spécifie les types d’opérations de restauration disponibles.</span><span class="sxs-lookup"><span data-stu-id="e998f-104">A *recovery model* is a database property that controls how transactions are logged, whether the transaction log requires (and allows) backing up, and what kinds of restore operations are available.</span></span> <span data-ttu-id="e998f-105">Il existe trois modes de récupération : simple, complète et utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="e998f-105">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="e998f-106">En règle générale, une base de données utilise le mode de restauration complète ou le mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="e998f-106">Typically, a database uses the full recovery model or simple recovery model.</span></span> <span data-ttu-id="e998f-107">Il est possible de modifier le mode de récupération d'une base de données à tout moment.</span><span class="sxs-lookup"><span data-stu-id="e998f-107">A database can be switched to another recovery model at any time.</span></span> <span data-ttu-id="e998f-108">La base de données **model** définit le mode de récupération par défaut des nouvelles bases de données.</span><span class="sxs-lookup"><span data-stu-id="e998f-108">The **model** database sets the default recovery model of new databases.</span></span>  
  
 <span data-ttu-id="e998f-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="e998f-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e998f-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="e998f-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e998f-111">Recommandations</span><span class="sxs-lookup"><span data-stu-id="e998f-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e998f-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e998f-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e998f-113">**Pour afficher ou modifier le mode de récupération d'une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="e998f-113">**To view or change the recovery model of a database, using:**</span></span>  
  
     [<span data-ttu-id="e998f-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e998f-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e998f-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e998f-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="e998f-116">**Recommandations de suivi :**  [Après avoir modifié le mode de récupération](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="e998f-116">**Follow Up Recommendations:**  [After You Change the Recovery Model](#FollowUp)</span></span>  
  
-   [<span data-ttu-id="e998f-117">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="e998f-117">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e998f-118">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e998f-118">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e998f-119">Recommandations</span><span class="sxs-lookup"><span data-stu-id="e998f-119">Recommendations</span></span>  
  
-   <span data-ttu-id="e998f-120">Avant de passer en mode de récupération complète ou en mode de récupération utilisant les journaux de transactions, sauvegardez le journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="e998f-120">Before switching from the full recovery or bulk-logged recovery model, back up the transaction log.</span></span>  
  
-   <span data-ttu-id="e998f-121">La récupération jusqu'à une date et heure n'est pas possible dans le mode de récupération utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="e998f-121">Point-in-time recovery is not possible with bulk-logged model.</span></span> <span data-ttu-id="e998f-122">Par conséquent, si vous exécutez des transactions en mode de récupération utilisant les journaux de transactions, pouvant nécessiter une restauration du journal des transactions, ces transactions peuvent être exposées à des pertes de données.</span><span class="sxs-lookup"><span data-stu-id="e998f-122">Therefore, if you run transactions under the bulk-logged recovery model that might require a transaction log restore, these transactions could be exposed to data loss.</span></span> <span data-ttu-id="e998f-123">Pour optimiser la possibilité de récupérer les données dans un scénario de récupération après sinistre, nous vous recommandons de passer au mode de récupération utilisant les journaux de transactions dans les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="e998f-123">To maximize data recoverability in a disaster-recovery scenario, we recommend that you switch to the bulk-logged recovery model only under the following conditions:</span></span>  
  
    -   <span data-ttu-id="e998f-124">Les utilisateurs ne sont pas actuellement autorisés dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e998f-124">Users are currently not allowed in the database.</span></span>  
  
    -   <span data-ttu-id="e998f-125">Toutes modifications effectuées au cours du traitement en bloc sont récupérables sans une restauration du journal en réexécutant, par exemple, les processus en bloc.</span><span class="sxs-lookup"><span data-stu-id="e998f-125">All modifications made during bulk processing are recoverable without depending on taking a log backup; for example, by re-running the bulk processes.</span></span>  
  
     <span data-ttu-id="e998f-126">Si ces deux conditions sont satisfaites, vous ne serez pas exposé à des pertes de données lors d'une restauration du journal des transactions sauvegardé en mode de récupération utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="e998f-126">If you satisfy these two conditions, you will not be exposed to any data loss while restoring a transaction log that was backed up under the bulk-logged recovery model..</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e998f-127">Si vous adoptez le mode de récupération complète pendant une opération en bloc, la journalisation des opérations en bloc passe de la journalisation minimale à la journalisation complète, et inversement.</span><span class="sxs-lookup"><span data-stu-id="e998f-127">If you switch to the full recovery model during a bulk operation, the logging of the bulk operation changes from minimal logging to full logging, and vice versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e998f-128">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e998f-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e998f-129">Autorisations</span><span class="sxs-lookup"><span data-stu-id="e998f-129">Permissions</span></span>  
 <span data-ttu-id="e998f-130">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="e998f-130">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e998f-131">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e998f-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-recovery-model"></a><span data-ttu-id="e998f-132">Pour afficher ou modifier le mode de récupération</span><span class="sxs-lookup"><span data-stu-id="e998f-132">To view or change the recovery model</span></span>  
  
1.  <span data-ttu-id="e998f-133">Après vous être connecté à l'instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], dans l'Explorateur d'objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="e998f-133">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="e998f-134">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="e998f-134">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="e998f-135">Cliquez avec le bouton droit de la souris sur la base de données, puis cliquez sur **Propriétés**pour ouvrir la boîte de dialogue **Propriétés de la base de données** .</span><span class="sxs-lookup"><span data-stu-id="e998f-135">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="e998f-136">Dans le volet **Sélectionner une page** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="e998f-136">In the **Select a page** pane, click **Options**.</span></span>  
  
5.  <span data-ttu-id="e998f-137">Le mode de récupération actuel s'affiche dans la zone de liste **Mode de récupération** .</span><span class="sxs-lookup"><span data-stu-id="e998f-137">The current recovery model is displayed in the **Recovery model** list box.</span></span>  
  
6.  <span data-ttu-id="e998f-138">Au besoin, pour modifier le mode de récupération, sélectionnez un autre mode dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e998f-138">Optionally, to change the recovery model select a different model list.</span></span> <span data-ttu-id="e998f-139">Les choix sont **Complet**, **Journalisé en bloc**ou **Simple**.</span><span class="sxs-lookup"><span data-stu-id="e998f-139">The choices are **Full**, **Bulk-logged**, or **Simple**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e998f-140">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e998f-140">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-recovery-model"></a><span data-ttu-id="e998f-141">Pour afficher le mode de récupération</span><span class="sxs-lookup"><span data-stu-id="e998f-141">To view the recovery model</span></span>  
  
1.  <span data-ttu-id="e998f-142">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e998f-142">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e998f-143">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e998f-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e998f-144">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e998f-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e998f-145">Cet exemple montre comment interroger l'affichage catalogue [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) pour connaître le mode de récupération de la base de données **model** .</span><span class="sxs-lookup"><span data-stu-id="e998f-145">This example shows how to query the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view to learn the recovery model of the **model** database.</span></span>  
  
```sql  
SELECT name, recovery_model_desc  
   FROM sys.databases  
      WHERE name = 'model' ;  
GO  
  
```  
  
#### <a name="to-change-the-recovery-model"></a><span data-ttu-id="e998f-146">Pour modifier le mode de récupération</span><span class="sxs-lookup"><span data-stu-id="e998f-146">To change the recovery model</span></span>  
  
1.  <span data-ttu-id="e998f-147">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e998f-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e998f-148">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e998f-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e998f-149">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e998f-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e998f-150">Cet exemple montre comment modifier le mode de récupération de la base de données `model` en `FULL` à l'aide de l'option `SET RECOVERY` de l'instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="e998f-150">This example shows how to change the recovery model in the `model` database to `FULL` by using the `SET RECOVERY` option of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options) statement.</span></span>  
  
```sql  
USE master ;  
ALTER DATABASE model SET RECOVERY FULL ;  
```  
  
##  <a name="follow-up-recommendations-after-you-change-the-recovery-model"></a><a name="FollowUp"></a><span data-ttu-id="e998f-151">Recommandations de suivi : après avoir modifié le mode de récupération</span><span class="sxs-lookup"><span data-stu-id="e998f-151">Follow Up Recommendations: After You Change the Recovery Model</span></span>  
  
-   <span data-ttu-id="e998f-152">**Après un changement de mode de récupération complète ou de mode de récupération utilisant les journaux de transactions**</span><span class="sxs-lookup"><span data-stu-id="e998f-152">**After switching between the full and bulk-logged recovery models**</span></span>  
  
    -   <span data-ttu-id="e998f-153">Repassez immédiatement en mode de récupération complète après avoir effectué les opérations en bloc.</span><span class="sxs-lookup"><span data-stu-id="e998f-153">After completing the bulk operations, immediately switch back to full recovery mode.</span></span>  
  
    -   <span data-ttu-id="e998f-154">Après être passé du mode de récupération utilisant les journaux de transactions au mode de récupération complète, sauvegardez le journal.</span><span class="sxs-lookup"><span data-stu-id="e998f-154">After switching from the bulk-logged recovery model back to the full recovery model, back up the log.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e998f-155">Votre stratégie de sauvegarde ne change pas : continuez à effectuer régulièrement des sauvegardes des bases de données, des sauvegardes des journaux et des sauvegardes différentielles.</span><span class="sxs-lookup"><span data-stu-id="e998f-155">Your backup strategy remains the same: continue performing periodic database, log, and differential backups.</span></span>  
  
-   <span data-ttu-id="e998f-156">**Après basculement à partir du mode de récupération simple**</span><span class="sxs-lookup"><span data-stu-id="e998f-156">**After switching from the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="e998f-157">Aussitôt après être passé en mode de restauration complète ou en mode de récupération utilisant les journaux de transactions, procédez à une sauvegarde de base de données complète ou différentielle pour lancer la séquence de journaux.</span><span class="sxs-lookup"><span data-stu-id="e998f-157">Immediately after switching to the full recovery model or bulk-logged recovery model, take a full or differential database backup to start the log chain.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e998f-158">Le passage au mode de restauration complète ou mode de récupération utilisant les journaux de transactions n'est effectif qu'après la première sauvegarde de base de données.</span><span class="sxs-lookup"><span data-stu-id="e998f-158">The switch to the full or bulk-logged recovery model takes effect only after the first data backup.</span></span>  
  
    -   <span data-ttu-id="e998f-159">Planifiez des sauvegardes de journaux régulières et mettez à jour votre plan de restauration en conséquence.</span><span class="sxs-lookup"><span data-stu-id="e998f-159">Schedule regular log backups, and update your restore plan accordingly.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="e998f-160">Si vous ne sauvegardez pas assez souvent le journal, il est susceptible de s'étendre jusqu'à manquer de l'espace disque nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e998f-160">If you do not back up the log frequently enough, the transaction log can expand until it runs out of disk space.</span></span>  
  
-   <span data-ttu-id="e998f-161">**Après basculement en mode de récupération simple**</span><span class="sxs-lookup"><span data-stu-id="e998f-161">**After switching to the simple recovery model**</span></span>  
  
    -   <span data-ttu-id="e998f-162">Mettez fin à tous les travaux planifiés afin de sauvegarder le journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="e998f-162">Discontinue any scheduled jobs for backing up the transaction log.</span></span>  
  
    -   <span data-ttu-id="e998f-163">Assurez-vous que des sauvegardes des bases de données régulières sont planifiées.</span><span class="sxs-lookup"><span data-stu-id="e998f-163">Ensure periodic database backups are scheduled.</span></span> <span data-ttu-id="e998f-164">La sauvegarde de votre base de données est essentielle pour protéger vos données et tronquer la partie inactive du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="e998f-164">Backing up your database is essential both to protect your data and to truncate the inactive portion of the transaction log.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e998f-165">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="e998f-165">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e998f-166">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e998f-166">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="e998f-167">Sauvegarder un journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e998f-167">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="e998f-168">Créer un travail</span><span class="sxs-lookup"><span data-stu-id="e998f-168">Create a Job</span></span>](../../ssms/agent/create-a-job.md)  
  
-   [<span data-ttu-id="e998f-169">Disable or Enable a Job</span><span class="sxs-lookup"><span data-stu-id="e998f-169">Disable or Enable a Job</span></span>](../../ssms/agent/disable-or-enable-a-job.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="e998f-170">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="e998f-170">Related Content</span></span>  
  
-   <span data-ttu-id="e998f-171">[Plans de maintenance de base de données](../maintenance-plans/maintenance-plans.md) (dans la documentation en ligne de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="e998f-171">[Database Maintenance Plans](../maintenance-plans/maintenance-plans.md) (in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e998f-172"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e998f-172">See Also</span></span>  
 <span data-ttu-id="e998f-173">[Modes de récupération &#40;SQL Server&#41;](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e998f-173">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="e998f-174">[Journal des transactions &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e998f-174">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="e998f-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e998f-175">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="e998f-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e998f-176">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="e998f-177">Modes de récupération &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e998f-177">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
