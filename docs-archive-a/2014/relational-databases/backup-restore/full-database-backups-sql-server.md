---
title: Sauvegardes complètes de bases de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- backups [SQL Server], database
- backing up databases [SQL Server], full backups
- estimating database backup size
- backing up [SQL Server], size of backup
- database backups [SQL Server], full backups
- size [SQL Server], backups
- database backups [SQL Server], about backing up databases
ms.assetid: 4d933d19-8d21-4aa1-8153-d230cb3a3f99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ee871b6cabbe6c2b2cb4f444fd1e2d42d711dfbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699827"
---
# <a name="full-database-backups-sql-server"></a><span data-ttu-id="2f474-102">Sauvegardes complètes de bases de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2f474-102">Full Database Backups (SQL Server)</span></span>
  <span data-ttu-id="2f474-103">Une sauvegarde complète de base de données permet de sauvegarder l'intégralité d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="2f474-103">A full database backup backs up the whole database.</span></span> <span data-ttu-id="2f474-104">Ce type de sauvegarde comprend une partie du journal des transactions afin que toute la base de données puisse être récupérée après la restauration d'une sauvegarde complète de la base de données.</span><span class="sxs-lookup"><span data-stu-id="2f474-104">This includes part of the transaction log so that the full database can be recovered after a full database backup is restored.</span></span> <span data-ttu-id="2f474-105">Les sauvegardes complètes de base de données représentent la base de données à l'issue de l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="2f474-105">Full database backups represent the database at the time the backup finished.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="2f474-106">À mesure que la taille d'une base de données augmente, les sauvegardes complètes de base de données nécessitent davantage de temps et d'espace de stockage.</span><span class="sxs-lookup"><span data-stu-id="2f474-106">As a database increases in size full database backups take more time to finish and require more storage space.</span></span> <span data-ttu-id="2f474-107">Par conséquent, pour les bases de données volumineuses, il est conseillé de compléter les sauvegardes complètes avec une série de *sauvegardes différentielles de base de données*.</span><span class="sxs-lookup"><span data-stu-id="2f474-107">Therefore, for a large database, you might want to supplement a full database backup with a series of *differential database backups*.</span></span> <span data-ttu-id="2f474-108">Pour plus d’informations, consultez [Sauvegardes différentielles &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2f474-108">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f474-109">TRUSTWORTHY a la valeur OFF pour une sauvegarde de base de données.</span><span class="sxs-lookup"><span data-stu-id="2f474-109">TRUSTWORTHY is set to OFF on a database backup.</span></span> <span data-ttu-id="2f474-110">Pour plus d’informations sur la façon d’affecter la valeur ON à TRUSTWORTHY, consultez [Options ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="2f474-110">For information about how to set TRUSTWORTHY to ON, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="2f474-111">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="2f474-111">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="2f474-112">Sauvegardes de base de données en mode de récupération simple</span><span class="sxs-lookup"><span data-stu-id="2f474-112">Database Backups Under the Simple Recovery Model</span></span>](#DbBuRMs)  
  
-   [<span data-ttu-id="2f474-113">Sauvegardes de base de données en mode de récupération complète</span><span class="sxs-lookup"><span data-stu-id="2f474-113">Database Backups Under the Full Recovery Model</span></span>](#DbBuRMf)  
  
-   [<span data-ttu-id="2f474-114">Utiliser une sauvegarde complète pour restaurer la base de données</span><span class="sxs-lookup"><span data-stu-id="2f474-114">Use a Full Database Backup to Restore the Database</span></span>](#RestoreDbBu)  
  
-   [<span data-ttu-id="2f474-115">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="2f474-115">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="database-backups-under-the-simple-recovery-model"></a><a name="DbBuRMs"></a> <span data-ttu-id="2f474-116">Sauvegardes de base de données en mode de récupération simple</span><span class="sxs-lookup"><span data-stu-id="2f474-116">Database Backups Under the Simple Recovery Model</span></span>  
 <span data-ttu-id="2f474-117">En mode de récupération simple, après chaque sauvegarde, la base de données est exposée à des pertes de travaux potentielles en cas de sinistre.</span><span class="sxs-lookup"><span data-stu-id="2f474-117">Under the simple recovery model, after each backup, the database is exposed to potential work loss if a disaster were to occur.</span></span> <span data-ttu-id="2f474-118">Le risque de perte de travail augmente après chaque mise à jour et ce, jusqu'à la sauvegarde suivante, après laquelle le risque de perte de travail redevient nul et un nouveau cycle de risque de perte de travail commence.</span><span class="sxs-lookup"><span data-stu-id="2f474-118">The work-loss exposure increases with each update until the next backup, when the work-loss exposure returns to zero and a new cycle of work-loss exposure starts.</span></span> <span data-ttu-id="2f474-119">Le risque de perte de travail augmente au fil du temps entre les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="2f474-119">Work-loss exposure increases over time between backups.</span></span> <span data-ttu-id="2f474-120">La figure ci-dessous montre le risque de perte de travail pour une stratégie de sauvegarde qui utilise uniquement des sauvegardes complètes de base de données.</span><span class="sxs-lookup"><span data-stu-id="2f474-120">The following illustration shows the work-loss exposure for a backup strategy that uses only full database backups.</span></span>  
  
 <span data-ttu-id="2f474-121">![Affiche le risque de perte du travail entre les sauvegardes de base de données](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Montre le risque de perte du travail entre les sauvegardes de base de données")</span><span class="sxs-lookup"><span data-stu-id="2f474-121">![Shows work-loss exposure between database backups](../../database-engine/media/bnr-rmsimple-1-fulldb-backups.gif "Shows work-loss exposure between database backups")</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="2f474-122">Exemple ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="2f474-122">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="2f474-123">L'exemple ci-dessous illustre la création d'une sauvegarde complète de base de données à l'aide de WITH FORMAT afin de remplacer les sauvegardes existantes et créer un jeu de supports.</span><span class="sxs-lookup"><span data-stu-id="2f474-123">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span>  
  
```  
-- Back up the AdventureWorks2012 database to new media set.  
BACKUP DATABASE AdventureWorks2012  
    TO DISK = 'Z:\SQLServerBackups\AdventureWorksSimpleRM.bak'   
    WITH FORMAT;  
GO  
```  
  
##  <a name="database-backups-under-the-full-recovery-model"></a><a name="DbBuRMf"></a> <span data-ttu-id="2f474-124">Sauvegardes de base de données en mode de récupération complète</span><span class="sxs-lookup"><span data-stu-id="2f474-124">Database Backups Under the Full Recovery Model</span></span>  
 <span data-ttu-id="2f474-125">Pour les bases de données qui font appel au mode de récupération complète et au mode de récupération utilisant les journaux de transactions, les sauvegardes de base de données sont nécessaires, mais pas suffisantes.</span><span class="sxs-lookup"><span data-stu-id="2f474-125">For databases that use full and bulk-logged recovery, database backups are necessary but not sufficient.</span></span> <span data-ttu-id="2f474-126">Les sauvegardes des journaux de transactions sont également requises.</span><span class="sxs-lookup"><span data-stu-id="2f474-126">Transaction log backups are also required.</span></span> <span data-ttu-id="2f474-127">La figure ci-dessous montre la stratégie de sauvegarde la moins complexe possible en mode de restauration complète.</span><span class="sxs-lookup"><span data-stu-id="2f474-127">The following illustration shows the least complex backup strategy that is possible under the full recovery model.</span></span>  
  
 <span data-ttu-id="2f474-128">![Séries de sauvegardes complètes de base de données et de sauvegardes de journal](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Séries de sauvegardes complètes de base de données et de sauvegardes de journal")</span><span class="sxs-lookup"><span data-stu-id="2f474-128">![Series of full database backups and log backups](../../database-engine/media/bnr-rmfull-1-fulldb-log-backups.gif "Series of full database backups and log backups")</span></span>  
  
 <span data-ttu-id="2f474-129">Pour plus d’informations sur la façon de créer des sauvegardes de journaux, consultez [Sauvegardes des journaux de transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2f474-129">For information about how to create log backups, see [Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md).</span></span>  
  
### <a name="example--tsql"></a><span data-ttu-id="2f474-130">Exemple ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span><span class="sxs-lookup"><span data-stu-id="2f474-130">Example ( [!INCLUDE[tsql](../../../includes/tsql-md.md)])</span></span>  
 <span data-ttu-id="2f474-131">L'exemple ci-dessous illustre la création d'une sauvegarde complète de base de données à l'aide de WITH FORMAT afin de remplacer les sauvegardes existantes et créer un jeu de supports.</span><span class="sxs-lookup"><span data-stu-id="2f474-131">The following example shows how to create a full database backup by using WITH FORMAT to overwrite any existing backups and create a new media set.</span></span> <span data-ttu-id="2f474-132">Puis, l'exemple sauvegarde le journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="2f474-132">Then, the example backs up the transaction log.</span></span> <span data-ttu-id="2f474-133">Dans la réalité, vous seriez amené à effectuer une série de sauvegardes de fichier journal normales.</span><span class="sxs-lookup"><span data-stu-id="2f474-133">In a real-life situation, you would have to perform a series of regular log backups.</span></span> <span data-ttu-id="2f474-134">Dans le cadre de cet exemple, l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] est défini pour utiliser le mode de récupération complète.</span><span class="sxs-lookup"><span data-stu-id="2f474-134">For this example, the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database is set to use the full recovery model.</span></span>  
  
```  
USE master;  
ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
GO  
-- Back up the AdventureWorks2012 database to new media set (backup set 1).  
BACKUP DATABASE AdventureWorks2012  
  TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak'   
  WITH FORMAT;  
GO  
--Create a routine log backup (backup set 2).  
BACKUP LOG AdventureWorks2012 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012FullRM.bak';  
GO  
```  
  
##  <a name="use-a-full-database-backup-to-restore-the-database"></a><a name="RestoreDbBu"></a> <span data-ttu-id="2f474-135">Utiliser une sauvegarde complète pour restaurer la base de données</span><span class="sxs-lookup"><span data-stu-id="2f474-135">Use a Full Database Backup to Restore the Database</span></span>  
 <span data-ttu-id="2f474-136">Vous pouvez recréer une base de données dans son intégralité en la restaurant à n'importe quel emplacement, en une seule étape, à partir d'une sauvegarde complète de base de données.</span><span class="sxs-lookup"><span data-stu-id="2f474-136">You can re-create a whole database in one step by restoring the database from a full database backup to any location.</span></span> <span data-ttu-id="2f474-137">La sauvegarde contient une partie suffisante du journal des transactions pour vous permettre de récupérer la base de données à l'issue de l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="2f474-137">Enough of the transaction log is included in the backup to let you recover the database to the time when the backup finished.</span></span> <span data-ttu-id="2f474-138">La base de données restaurée retrouve l'état qui était le sien à l'issue de la sauvegarde de base de données sans les transactions non validées.</span><span class="sxs-lookup"><span data-stu-id="2f474-138">The restored database matches the state of the original database when the database backup finished, minus any uncommitted transactions.</span></span> <span data-ttu-id="2f474-139">Dans le mode de récupération complète, vous devez restaurer toutes les sauvegardes ultérieures des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="2f474-139">Under the full recovery model, you should then restore all subsequent transaction log backups.</span></span> <span data-ttu-id="2f474-140">Une fois la base de données récupérée, les transactions non validées sont restaurées.</span><span class="sxs-lookup"><span data-stu-id="2f474-140">When the database is recovered, uncommitted transactions are rolled back.</span></span>  
  
 <span data-ttu-id="2f474-141">Pour plus d’informations, consultez [Restaurations complètes de bases de données &#40;mode de récupération simple&#41;](complete-database-restores-simple-recovery-model.md) ou [Restaurations complètes de bases de données &#40;mode de récupération complète&#41;](complete-database-restores-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="2f474-141">For more information, see [Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) or [Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2f474-142">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="2f474-142">Related Tasks</span></span>  
 <span data-ttu-id="2f474-143">**Pour créer une sauvegarde de base de données complète**</span><span class="sxs-lookup"><span data-stu-id="2f474-143">**To create a full database backup**</span></span>  
  
-   [<span data-ttu-id="2f474-144">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2f474-144">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   <span data-ttu-id="2f474-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span><span class="sxs-lookup"><span data-stu-id="2f474-145"><xref:Microsoft.SqlServer.Management.Smo.Backup.SqlBackup%2A> (SMO)</span></span>  
  
 <span data-ttu-id="2f474-146">**Pour planifier des travaux de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="2f474-146">**To schedule backup jobs**</span></span>  
  
 [<span data-ttu-id="2f474-147">Utiliser l'Assistant Plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="2f474-147">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f474-148"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f474-148">See Also</span></span>  
 <span data-ttu-id="2f474-149">[Sauvegarde et restauration des bases de données SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="2f474-149">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="2f474-150">[Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2f474-150">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="2f474-151">Sauvegarde et restauration de bases de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2f474-151">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
  
