---
title: 'Exemple : restauration fragmentaire d’une base de données (Mode de restauration complète) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- piecemeal restores [SQL Server], full recovery model
- restore sequences [SQL Server], piecemeal
ms.assetid: 0a84892d-2f7a-4e77-b2d0-d68b95595210
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5cfccccdbdc0c4fb3b189ee0a9fa3aeaf426578b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704207"
---
# <a name="example-piecemeal-restore-of-database-full-recovery-model"></a><span data-ttu-id="1c4c8-102">Exemple : Restauration fragmentaire d'une base de données (Mode de restauration complète)</span><span class="sxs-lookup"><span data-stu-id="1c4c8-102">Example: Piecemeal Restore of Database (Full Recovery Model)</span></span>
  <span data-ttu-id="1c4c8-103">Une séquence de restauration fragmentaire restaure et récupère une base de données par étape au niveau des groupes de fichiers, en commençant par le groupe de fichiers primaire, suivi des groupes fichiers secondaires en lecture-écriture.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read-write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="1c4c8-104">Dans cet exemple, la base de données `adb` est restaurée sur un nouvel ordinateur après un problème grave.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="1c4c8-105">La base de données utilise le mode de restauration complète ; par conséquent, avant le début de la restauration, il convient d'effectuer une sauvegarde de la fin du journal sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-105">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="1c4c8-106">Avant le sinistre, tous les groupes de fichiers sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="1c4c8-107">Groupe de fichiers `B` en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-107">Filegroup `B` is read-only.</span></span> <span data-ttu-id="1c4c8-108">Tous les groupes de fichiers secondaires doivent être restaurés, mais dans l'ordre de priorité suivant : `A` (le plus élevé), `C`et enfin `B`</span><span class="sxs-lookup"><span data-stu-id="1c4c8-108">All of the secondary filegroups must be restored, but they are restored in order of importance: `A` (highest), `C`, and lastly `B`.</span></span> <span data-ttu-id="1c4c8-109">Dans cet exemple, il y a quatre sauvegardes de journal, dont la sauvegarde de la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-109">In this example, there are four log backups, including the tail-log backup.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="1c4c8-110">Sauvegarde de la fin du journal</span><span class="sxs-lookup"><span data-stu-id="1c4c8-110">Tail-Log Backup</span></span>  
 <span data-ttu-id="1c4c8-111">Avant de restaurer la base de données, l'administrateur de la base de données doit sauvegarder la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-111">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="1c4c8-112">La base de données étant endommagée, la création de la sauvegarde de la fin du journal requiert l'utilisation de l'option NO_TRUNCATE :</span><span class="sxs-lookup"><span data-stu-id="1c4c8-112">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="1c4c8-113">La sauvegarde de la fin du journal est la dernière sauvegarde appliquée dans les séquences de restauration qui suivent.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-113">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="1c4c8-114">Séquences de restauration</span><span class="sxs-lookup"><span data-stu-id="1c4c8-114">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c4c8-115">La syntaxe pour une séquence de restauration en ligne est la même que pour une séquence de restauration hors connexion.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-115">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="1c4c8-116">Restauration partielle du groupe de fichiers primaire et secondaire `A`.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-116">Partial restore of the primary and secondary filegroup `A`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
       WITH PARTIAL, NORECOVERY  
    RESTORE DATABASE adb FILEGROUP='A' FROM backup2   
       WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
2.  <span data-ttu-id="1c4c8-117">Restauration en ligne du groupe de fichiers `C`.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-117">Online restore of filegroup `C`.</span></span>  
  
     <span data-ttu-id="1c4c8-118">À ce stade, le groupe de fichiers primaire et le groupe de fichiers secondaire `A` sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-118">At this point, the primary filegroup and secondary filegroup `A` are online.</span></span> <span data-ttu-id="1c4c8-119">Tous les fichiers dans les groupes de fichiers `B` et `C` sont en attente de récupération, et les groupes de fichiers sont hors connexion.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-119">All the files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
     <span data-ttu-id="1c4c8-120">Les messages de la dernière instruction `RESTORE LOG` (étape 1) indiquent que la restauration des transactions impliquant le groupe de fichiers `C` a été différée parce que ce groupe de fichiers n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-120">Messages from the last `RESTORE LOG` statement in step 1 indicate that rollback of transactions that involve filegroup `C` was deferred, because this filegroup is not available.</span></span> <span data-ttu-id="1c4c8-121">Les opérations courantes peuvent continuer, mais des verrous sont détenus par ces transactions et la troncation du fichier journal ne peut pas avoir lieu tant que la restauration n'est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-121">Regular operations can continue, but locks are held by these transactions and log truncation will not occur until the rollback can complete.</span></span>  
  
     <span data-ttu-id="1c4c8-122">Dans la deuxième séquence de restauration, l'administrateur de base de données restaure le groupe de fichiers `C`:</span><span class="sxs-lookup"><span data-stu-id="1c4c8-122">In the second restore sequence, the database administrator restores filegroup `C`:</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' FROM backup2a WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM backup4 WITH NORECOVERY  
    RESTORE LOG adb FROM backup5 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="1c4c8-123">À ce stade, le groupe de fichiers primaire et les groupes de fichiers `A` et `C` sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-123">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="1c4c8-124">Les fichiers du groupe de fichiers `B` restent en attente de récupération et le groupe de fichiers est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-124">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span> <span data-ttu-id="1c4c8-125">Les transactions différées ont été résolues et la troncation du fichier journal a lieu.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-125">Deferred transactions have been resolved, and log truncation occurs.</span></span>  
  
3.  <span data-ttu-id="1c4c8-126">Restauration en ligne du groupe de fichiers `B`.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-126">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="1c4c8-127">Dans la troisième séquence de restauration, l'administrateur de base de données restaure le groupe de fichiers `B`.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-127">In the third restore sequence, the database administrator restores filegroup `B`.</span></span> <span data-ttu-id="1c4c8-128">La sauvegarde du groupe de fichiers `B` a été effectuée après que le groupe de fichiers soit passé en lecture seule ; ces fichiers n'ont donc pas besoin d'être restaurés par progression au cours de la récupération.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-128">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, it does not have to be rolled forward during recovery.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup2b WITH RECOVERY  
    ```  
  
     <span data-ttu-id="1c4c8-129">Tous les groupes de fichiers sont maintenant en ligne.</span><span class="sxs-lookup"><span data-stu-id="1c4c8-129">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="1c4c8-130">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="1c4c8-130">Additional Examples</span></span>  
  
-   [<span data-ttu-id="1c4c8-131">Exemple : restauration fragmentaire d’une base de données &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="1c4c8-131">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="1c4c8-132">Exemple : restauration fragmentaire de quelques groupes de fichiers uniquement &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="1c4c8-132">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="1c4c8-133">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="1c4c8-133">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="1c4c8-134">Exemple : restauration fragmentaire de quelques groupes de fichiers &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="1c4c8-134">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="1c4c8-135">Exemple : restauration en ligne d’un fichier en lecture/écriture &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="1c4c8-135">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="1c4c8-136">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="1c4c8-136">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="1c4c8-137"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c4c8-137">See Also</span></span>  
 <span data-ttu-id="1c4c8-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c4c8-138">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="1c4c8-139">[Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1c4c8-139">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="1c4c8-140">[Appliquer les sauvegardes du journal des transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1c4c8-140">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="1c4c8-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c4c8-141">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="1c4c8-142">Restaurations fragmentaires &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1c4c8-142">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
