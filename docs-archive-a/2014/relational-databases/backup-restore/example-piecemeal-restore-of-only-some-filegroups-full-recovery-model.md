---
title: 'Exemple : restauration fragmentaire de quelques groupes de fichiers (mode de restauration complète) | Microsoft Docs'
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
ms.assetid: bced4b54-e819-472b-b784-c72e14e72a0b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b3cb1a5ea33a5016c99fdf1f5a7f4e892c045b59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709679"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-full-recovery-model"></a><span data-ttu-id="f7412-102">Exemple : Restauration fragmentaire de quelques groupes de fichiers (mode de restauration complète)</span><span class="sxs-lookup"><span data-stu-id="f7412-102">Example: Piecemeal Restore of Only Some Filegroups (Full Recovery Model)</span></span>
  <span data-ttu-id="f7412-103">Cette rubrique concerne les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui relèvent du mode de récupération complète et qui contiennent plusieurs fichiers ou groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f7412-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="f7412-104">Une séquence de restauration fragmentaire restaure et récupère une base de données par étapes au niveau des groupes de fichiers, en commençant par le groupe de fichiers primaire et tous les groupes de fichiers secondaires en lecture-écriture.</span><span class="sxs-lookup"><span data-stu-id="f7412-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="f7412-105">Dans cet exemple, une base de données appelée `adb`qui utilise le mode de restauration complète, contient trois groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f7412-105">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="f7412-106">Le groupe de fichiers `A` est en lecture-écriture, et les groupes de fichiers `B` et `C` sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="f7412-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="f7412-107">Au départ, tous les groupes de fichiers sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="f7412-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="f7412-108">Le groupe de fichiers primaire et le groupe de fichiers `B` de la base de données `adb` semblent endommagés.</span><span class="sxs-lookup"><span data-stu-id="f7412-108">The primary and filegroup `B` of database `adb` appear to be damaged.</span></span> <span data-ttu-id="f7412-109">Le groupe de fichiers primaire est relativement petit et peut être restauré rapidement.</span><span class="sxs-lookup"><span data-stu-id="f7412-109">The primary filegroup is fairly small and can be restored quickly.</span></span> <span data-ttu-id="f7412-110">L'administrateur de la base de données décide de restaurer les groupes de fichiers à l'aide d'une séquence de restauration fragmentaire.</span><span class="sxs-lookup"><span data-stu-id="f7412-110">The database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="f7412-111">D'abord, le groupe de fichiers primaire et les journaux des transactions consécutifs sont restaurés, puis la base de données est récupérée.</span><span class="sxs-lookup"><span data-stu-id="f7412-111">First, the primary filegroup and the subsequent transaction logs are restored the database is recovered.</span></span>  
  
 <span data-ttu-id="f7412-112">Les groupes de fichiers intacts `A` et `C` contiennent des données critiques.</span><span class="sxs-lookup"><span data-stu-id="f7412-112">The intact filegroups `A` and `C` contain critical data.</span></span> <span data-ttu-id="f7412-113">Ils seront donc récupérés ensuite pour les mettre en ligne le plus vite possible.</span><span class="sxs-lookup"><span data-stu-id="f7412-113">Therefore, they will be recovered next to bring them online as quickly as possible.</span></span> <span data-ttu-id="f7412-114">Enfin le groupe de fichiers secondaire endommagé, `B`, est restauré et récupéré.</span><span class="sxs-lookup"><span data-stu-id="f7412-114">Finally, the damaged secondary filegroup, `B`, is restored and recovered.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="f7412-115">Séquences de restauration :</span><span class="sxs-lookup"><span data-stu-id="f7412-115">Restore Sequences:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7412-116">La syntaxe pour une séquence de restauration en ligne est la même que pour une séquence de restauration hors connexion.</span><span class="sxs-lookup"><span data-stu-id="f7412-116">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="f7412-117">Effectuez une sauvegarde de la fin du journal pour la base de données `adb`.</span><span class="sxs-lookup"><span data-stu-id="f7412-117">Create a tail log backup of database `adb`.</span></span> <span data-ttu-id="f7412-118">Cette étape est essentielle pour que les groupes de fichiers intacts `A` et `C` soient en phase avec le point de récupération de la base de données.</span><span class="sxs-lookup"><span data-stu-id="f7412-118">This step is essential to make the intact filegroups `A` and `C` current with the recovery point of the database.</span></span>  
  
    ```  
    BACKUP LOG adb TO tailLogBackup WITH NORECOVERY  
    ```  
  
2.  <span data-ttu-id="f7412-119">Restauration partielle du groupe de fichiers primaire.</span><span class="sxs-lookup"><span data-stu-id="f7412-119">Partial restore of the primary filegroup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='Primary' FROM backup   
    WITH PARTIAL, NORECOVERY  
    RESTORE LOG adb FROM backup1 WITH NORECOVERY  
    RESTORE LOG adb FROM backup2 WITH NORECOVERY  
    RESTORE LOG adb FROM backup3 WITH NORECOVERY  
    RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="f7412-120">Le groupe de fichiers primaire est déjà en ligne.</span><span class="sxs-lookup"><span data-stu-id="f7412-120">At this point the primary is online.</span></span> <span data-ttu-id="f7412-121">Les fichiers dans les groupes de fichiers `A`, `B`et `C` sont en attente de récupération et les groupes de fichiers sont hors connexion.</span><span class="sxs-lookup"><span data-stu-id="f7412-121">Files in filegroups `A`, `B`, and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
3.  <span data-ttu-id="f7412-122">Restauration en ligne des groupes de fichiers `A` et `C`.</span><span class="sxs-lookup"><span data-stu-id="f7412-122">Online restore of filegroups `A` and `C`.</span></span>  
  
     <span data-ttu-id="f7412-123">Étant donné que leurs données ne sont pas endommagées, ces groupes de fichiers n'ont pas besoin d'être restaurés à partir d'une sauvegarde, mais ils ont besoin d'être récupérés pour être mis en ligne.</span><span class="sxs-lookup"><span data-stu-id="f7412-123">Because their data is undamaged, these filegroups do not have to be restored from a backup, but they do have to be recovered to bring them online.</span></span>  
  
     <span data-ttu-id="f7412-124">L'administrateur de base de données récupère immédiatement `A` et `C` .</span><span class="sxs-lookup"><span data-stu-id="f7412-124">The database administrator recovers `A` and `C` immediately.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A', FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="f7412-125">À ce stade, le groupe de fichiers primaire et les groupes de fichiers `A` et `C` sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="f7412-125">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="f7412-126">Les fichiers du groupe de fichiers `B` restent en attente de récupération et le groupe de fichiers est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="f7412-126">Files in filegroup `B` remain recovery pending, with the filegroup offline.</span></span>  
  
4.  <span data-ttu-id="f7412-127">Restauration en ligne du groupe de fichiers `B`.</span><span class="sxs-lookup"><span data-stu-id="f7412-127">Online restore of filegroup `B`.</span></span>  
  
     <span data-ttu-id="f7412-128">Les fichiers du groupe de fichiers `B` sont restaurés à n'importe quel moment ensuite.</span><span class="sxs-lookup"><span data-stu-id="f7412-128">Files in filegroup `B` are restored any time thereafter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f7412-129">La sauvegarde du groupe de fichiers `B` a été effectuée après que le groupe de fichiers soit passé en lecture seule, ces fichiers n'ont donc pas besoin d'être restaurés par progression.</span><span class="sxs-lookup"><span data-stu-id="f7412-129">The backup of filegroup `B` was taken after the filegroup became read-only; therefore, these files do not have to be rolled forward.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY  
    ```  
  
     <span data-ttu-id="f7412-130">Tous les groupes de fichiers sont maintenant en ligne.</span><span class="sxs-lookup"><span data-stu-id="f7412-130">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="f7412-131">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="f7412-131">Additional Examples</span></span>  
  
-   [<span data-ttu-id="f7412-132">Exemple : restauration fragmentaire d’une base de données &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="f7412-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="f7412-133">Exemple : restauration fragmentaire de quelques groupes de fichiers uniquement &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="f7412-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="f7412-134">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="f7412-134">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="f7412-135">Exemple : restauration fragmentaire d’une base de données &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="f7412-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="f7412-136">Exemple : restauration en ligne d’un fichier en lecture/écriture &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="f7412-136">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="f7412-137">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="f7412-137">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="f7412-138"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f7412-138">See Also</span></span>  
 <span data-ttu-id="f7412-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f7412-139">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="f7412-140">[Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f7412-140">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="f7412-141">[Appliquer les sauvegardes du journal des transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f7412-141">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="f7412-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f7412-142">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="f7412-143">Restaurations fragmentaires &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f7412-143">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
