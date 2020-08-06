---
title: Restaurer une base de données jusqu’au point de défaillance en mode de récupération complète (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- point of failure [SQL Server]
- restoring databases [SQL Server], point of failure
- database restores [SQL Server], point of failure
ms.assetid: 04106e18-bbf7-4a5e-a2e1-3d65319814d5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95b73660ebb44f4daffe6eaefd873699cfbbd8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604574"
---
# <a name="restore-a-database-to-the-point-of-failure-under-the-full-recovery-model-transact-sql"></a><span data-ttu-id="d2f50-102">Restaurer une base de données jusqu'au point d'échec en mode de récupération complète (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d2f50-102">Restore a Database to the Point of Failure Under the Full Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="d2f50-103">Cette rubrique explique comment restaurer jusqu'au point d'échec.</span><span class="sxs-lookup"><span data-stu-id="d2f50-103">This topic explains how to restore to the point of failure.</span></span> <span data-ttu-id="d2f50-104">Cette rubrique s'applique uniquement aux bases de données employant les modes de restauration complète ou de récupération utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="d2f50-104">The topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
### <a name="to-restore-to-the-point-of-failure"></a><span data-ttu-id="d2f50-105">Pour restaurer jusqu'au point d'échec</span><span class="sxs-lookup"><span data-stu-id="d2f50-105">To restore to the point of failure</span></span>  
  
1.  <span data-ttu-id="d2f50-106">Sauvegardez la fin du journal en exécutant l’instruction [BACKUP](/sql/t-sql/statements/backup-transact-sql) de base suivante :</span><span class="sxs-lookup"><span data-stu-id="d2f50-106">Back up the tail of the log by running the following basic [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
    ```  
    BACKUP LOG <database_name> TO <backup_device>   
       WITH NORECOVERY, NO_TRUNCATE;  
    ```  
  
2.  <span data-ttu-id="d2f50-107">Restaurez une sauvegarde de base de données complète en exécutant l’instruction [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) de base suivante :</span><span class="sxs-lookup"><span data-stu-id="d2f50-107">Restore a full database backup by running the following basic [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
3.  <span data-ttu-id="d2f50-108">Restaurez, éventuellement, une sauvegarde de base de données différentielle en exécutant l'instruction de base suivante RESTORE DATABASE :</span><span class="sxs-lookup"><span data-stu-id="d2f50-108">Optionally, restore a differential database backup by running the following basic RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
4.  <span data-ttu-id="d2f50-109">Appliquez chaque journal des transactions, y compris la sauvegarde de la fin du journal que vous avez créée à l'étape 1, en spécifiant WITH NORECOVERY dans l'instruction RESTORE LOG :</span><span class="sxs-lookup"><span data-stu-id="d2f50-109">Apply each transaction log, including the tail-log backup you created in step 1, by specifying WITH NORECOVERY in the RESTORE LOG statement:</span></span>  
  
    ```  
    RESTORE LOG <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
5.  <span data-ttu-id="d2f50-110">Récupérez la base de données en exécutant l'instruction RESTORE DATABASE suivante :</span><span class="sxs-lookup"><span data-stu-id="d2f50-110">Recover the database by running the following RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name>   
       WITH RECOVERY;  
    ```  
  
## <a name="example"></a><span data-ttu-id="d2f50-111"> Exemple</span><span class="sxs-lookup"><span data-stu-id="d2f50-111">Example</span></span>  
 <span data-ttu-id="d2f50-112">Avant de pouvoir exécuter cet exemple, vous devez terminer les préparations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d2f50-112">Before you can run the example, you must complete the following preparations:</span></span>  
  
1.  <span data-ttu-id="d2f50-113">Le mode de récupération par défaut de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] est le mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="d2f50-113">The default recovery model of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database is the simple recovery model.</span></span> <span data-ttu-id="d2f50-114">Étant donné que ce mode de récupération ne prend pas en charge la restauration jusqu’au point de défaillance, définissez [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] pour utiliser le mode de restauration complète en exécutant l’instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) suivante :</span><span class="sxs-lookup"><span data-stu-id="d2f50-114">Because this recovery model does not support restoring to the point of a failure, set [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] to use the full recovery model by running the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
    ```  
  
2.  <span data-ttu-id="d2f50-115">Créez une sauvegarde de base de données complète à l'aide de l'instruction suivante BACKUP :</span><span class="sxs-lookup"><span data-stu-id="d2f50-115">Create a full database back of the database by using the following BACKUP statement:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Data.bck';  
    ```  
  
3.  <span data-ttu-id="d2f50-116">Créez une sauvegarde de routine des journaux :</span><span class="sxs-lookup"><span data-stu-id="d2f50-116">Create a routine log backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Log.bck';  
    ```  
  
 <span data-ttu-id="d2f50-117">L'exemple suivant restaure les sauvegardes créées précédemment, après la création d'une sauvegarde de la fin du journal de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d2f50-117">The following example restores the backups that are created previously, after creating a tail-log backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="d2f50-118">(Cette étape suppose que le disque du journal est accessible).</span><span class="sxs-lookup"><span data-stu-id="d2f50-118">(This step assumes that the log disk can be accessed.)</span></span>  
  
 <span data-ttu-id="d2f50-119">Commencez par créer une sauvegarde de la fin du journal de la base de données qui capture le journal actif et laisse la base de données à l'état de restauration.</span><span class="sxs-lookup"><span data-stu-id="d2f50-119">First, the example creates a tail-log backup of the database that captures the active log and leaves the database in the Restoring state.</span></span> <span data-ttu-id="d2f50-120">Puis, l'exemple restaure la sauvegarde de base de données, applique la sauvegarde de routine des journaux créée précédemment et applique la sauvegarde de la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="d2f50-120">Then, the example restores the database backup, applies the routine log backup created previously, and applies the tail-log backup.</span></span> <span data-ttu-id="d2f50-121">Enfin, l'exemple récupère la base de données dans une étape séparée.</span><span class="sxs-lookup"><span data-stu-id="d2f50-121">Finally, the example recovers the database in a separate step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2f50-122">Le comportement par défaut consiste à récupérer une base de données en même temps que l'instruction qui restaure la sauvegarde finale.</span><span class="sxs-lookup"><span data-stu-id="d2f50-122">The default behavior is to recover a database as part of the statement that restores the final backup.</span></span>  
  
```  
/* Example of restoring a to the point of failure */  
-- Step 1: Create a tail-log backup by using WITH NORECOVERY.  
BACKUP LOG AdventureWorks2012  
   TO DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 2: Restore the full database backup.  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Data.bck'  
   WITH NORECOVERY;  
GO  
-- Step 3: Restore the first transaction log backup.  
RESTORE LOG AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 4: Restore the tail-log backup.  
RESTORE LOG AdventureWorks2012  
   FROM  DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 5: Recover the database.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2f50-123"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d2f50-123">See Also</span></span>  
 <span data-ttu-id="d2f50-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2f50-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="d2f50-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2f50-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
