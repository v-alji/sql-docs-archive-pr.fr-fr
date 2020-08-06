---
title: 'Exemple : restauration en ligne d’un fichier en lecture/écriture (mode de récupération complète) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- online restores [SQL Server], full recovery model
- restore sequences [SQL Server], online
ms.assetid: 0dbeda81-1464-44ba-9011-914900096368
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5b99a3d97644c2a5f104173457f30fc5b3fd7188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601521"
---
# <a name="example-online-restore-of-a-read-write-file-full-recovery-model"></a><span data-ttu-id="5d775-102">Exemple : Restauration en ligne d’un fichier en lecture/écriture (mode de récupération complète)</span><span class="sxs-lookup"><span data-stu-id="5d775-102">Example: Online Restore of a Read-Write File (Full Recovery Model)</span></span>
  <span data-ttu-id="5d775-103">Cette rubrique concerne les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui relèvent du mode de récupération complète et qui contiennent plusieurs fichiers ou groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="5d775-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="5d775-104">Dans cet exemple, une base de données appelée `adb`qui utilise le mode de restauration complète, contient trois groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="5d775-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="5d775-105">Le groupe de fichiers `A` est en lecture-écriture, et les groupes de fichiers `B` et `C` sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5d775-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="5d775-106">Au départ, tous les groupes de fichiers sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="5d775-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="5d775-107">Le fichier `a1` du groupe de fichiers `A` est endommagé et l’administrateur de la base de données décide de le restaurer pendant que la base de données est en ligne.</span><span class="sxs-lookup"><span data-stu-id="5d775-107">File `a1` in filegroup `A` appears to be damaged, and the database administrator decides to restore it while the database remains online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d775-108">En mode de récupération simple, la restauration en ligne des données en lecture-écriture n'est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="5d775-108">Under the simple recovery model, online restore of read/write data is not allowed.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="5d775-109">Séquences de restauration</span><span class="sxs-lookup"><span data-stu-id="5d775-109">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d775-110">La syntaxe pour une séquence de restauration en ligne est la même que pour une séquence de restauration hors connexion.</span><span class="sxs-lookup"><span data-stu-id="5d775-110">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="5d775-111">Restauration en ligne du fichier `a1`.</span><span class="sxs-lookup"><span data-stu-id="5d775-111">Online restore of file `a1`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILE='a1' FROM backup   
    WITH NORECOVERY;  
    ```  
  
     <span data-ttu-id="5d775-112">À ce stade, le fichier a1 est dans l'état RESTORING et le groupe de fichiers A est hors ligne.</span><span class="sxs-lookup"><span data-stu-id="5d775-112">At this point, file a1 is in the RESTORING state, and filegroup A is offline.</span></span>  
  
2.  <span data-ttu-id="5d775-113">Après avoir restauré le fichier, l'administrateur de base de données effectue une nouvelle sauvegarde de fichier journal afin de s'assurer que le point auquel le fichier a été mis hors connexion est capturé.</span><span class="sxs-lookup"><span data-stu-id="5d775-113">After restoring the file, the database administrator takes a new log backup to make sure that the point at which the file went offline is captured.</span></span>  
  
    ```  
    BACKUP LOG adb TO log_backup3;   
    ```  
  
3.  <span data-ttu-id="5d775-114">Restauration en ligne des sauvegardes de fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="5d775-114">Online restore of log backups.</span></span>  
  
     <span data-ttu-id="5d775-115">L’administrateur restaure toutes les sauvegardes de journaux effectuées depuis la restauration de la sauvegarde de fichiers, en terminant par la sauvegarde de fichier journal la plus récente (*log_backup3*, effectuée à l’étape 2).</span><span class="sxs-lookup"><span data-stu-id="5d775-115">The administrator restores all the log backups taken since the restored file backup, ending with the latest log backup (*log_backup3*, taken in step 2).</span></span> <span data-ttu-id="5d775-116">Une fois restaurée la dernière sauvegarde, la base de données est récupérée.</span><span class="sxs-lookup"><span data-stu-id="5d775-116">After the last backup is restored, the database is recovered.</span></span>  
  
    ```  
    RESTORE LOG adb FROM log_backup1 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup2 WITH NORECOVERY;  
    RESTORE LOG adb FROM log_backup3 WITH NORECOVERY;  
    RESTORE LOG adb WITH RECOVERY;  
    ```  
  
     <span data-ttu-id="5d775-117">Le fichier `a1` est désormais en ligne.</span><span class="sxs-lookup"><span data-stu-id="5d775-117">File `a1` is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="5d775-118">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="5d775-118">Additional Examples</span></span>  
  
-   [<span data-ttu-id="5d775-119">Exemple : restauration fragmentaire d’une base de données &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="5d775-119">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="5d775-120">Exemple : restauration fragmentaire de quelques groupes de fichiers uniquement &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="5d775-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="5d775-121">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="5d775-121">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="5d775-122">Exemple : restauration fragmentaire d’une base de données &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="5d775-122">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="5d775-123">Exemple : restauration fragmentaire de quelques groupes de fichiers &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="5d775-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="5d775-124">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="5d775-124">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="5d775-125"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d775-125">See Also</span></span>  
 <span data-ttu-id="5d775-126">[Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5d775-126">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="5d775-127">[Restaurations fragmentaires &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5d775-127">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="5d775-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d775-128">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="5d775-129">[Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5d775-129">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="5d775-130">[Appliquer les sauvegardes du journal des transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5d775-130">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="5d775-131">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5d775-131">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
