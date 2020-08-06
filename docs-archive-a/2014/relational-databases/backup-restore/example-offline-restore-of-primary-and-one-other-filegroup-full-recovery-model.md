---
title: 'Exemple : restauration hors ligne des groupes de fichiers primaire et d’un autre groupe de fichiers (mode de récupération complète) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- offline restores [SQL Server]
- restore sequences [SQL Server], offline
ms.assetid: 7d6c50eb-dc84-4d66-855a-0b5f1bd89737
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6f845927fdd74fba476139fccbf9a5fa112d434e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613475"
---
# <a name="example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model"></a><span data-ttu-id="09b2a-102">Exemple : restauration hors ligne du groupe de fichiers primaire et d'un autre groupe de fichiers (mode de restauration complète)</span><span class="sxs-lookup"><span data-stu-id="09b2a-102">Example: Offline Restore of Primary and One Other Filegroup (Full Recovery Model)</span></span>
  <span data-ttu-id="09b2a-103">Cette rubrique concerne uniquement les bases de données contenant plusieurs groupes de fichiers et obéissant au mode de récupération complète.</span><span class="sxs-lookup"><span data-stu-id="09b2a-103">This topic is relevant only for databases under the full recovery model that contain multiple filegroups.</span></span>  
  
 <span data-ttu-id="09b2a-104">Dans cet exemple, une base de données appelée `adb` contient trois groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="09b2a-104">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="09b2a-105">Les groupes de fichiers `A` et `C` sont en lecture-écriture, et le groupe de fichiers `B` est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="09b2a-105">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="09b2a-106">Le groupe de fichiers primaire et le groupe de fichiers `B` sont endommagés, tandis que les groupes de fichiers `A` et `C` sont intacts.</span><span class="sxs-lookup"><span data-stu-id="09b2a-106">The primary filegroup and filegroup `B` are damaged, but filegroups `A` and `C` are intact.</span></span> <span data-ttu-id="09b2a-107">Avant le sinistre, tous les groupes de fichiers étaient en ligne.</span><span class="sxs-lookup"><span data-stu-id="09b2a-107">Before the disaster, all the filegroups were online.</span></span>  
  
 <span data-ttu-id="09b2a-108">L'administrateur de base de données décide de restaurer et de récupérer le groupe de fichiers primaire et le groupe de fichiers `B`.</span><span class="sxs-lookup"><span data-stu-id="09b2a-108">The database administrator decides to restore and recover the primary filegroup and filegroup `B`.</span></span> <span data-ttu-id="09b2a-109">La base de données utilise le mode de restauration complète ; par conséquent, avant le début de la restauration, il convient d'effectuer une sauvegarde de la fin du journal sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="09b2a-109">The database is using the full recovery model; therefore, before the restore starts, a tail-log backup must be taken of the database.</span></span> <span data-ttu-id="09b2a-110">Lorsque la base de données se retrouve en ligne, les groupes de fichiers `A` et `C` sont automatiquement mis en ligne.</span><span class="sxs-lookup"><span data-stu-id="09b2a-110">When the database comes on line, Filegroups `A` and `C` are automatically brought online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09b2a-111">La séquence de restauration hors connexion a moins d'étapes qu'une restauration en ligne d'un fichier en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="09b2a-111">The offline restore sequence has fewer steps than an online restore of a read-only file.</span></span> <span data-ttu-id="09b2a-112">Pour obtenir un exemple, consultez [Exemple : Restauration en ligne d’un fichier en lecture seule &#40;Mode de récupération complète&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="09b2a-112">For an example, see [Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-only-file-full-recovery-model.md).</span></span> <span data-ttu-id="09b2a-113">Toutefois, la totalité de la base de données se trouve hors connexion tout au long de la séquence.</span><span class="sxs-lookup"><span data-stu-id="09b2a-113">However, the whole database is offline for the duration of the sequence.</span></span>  
  
## <a name="tail-log-backup"></a><span data-ttu-id="09b2a-114">Sauvegarde de la fin du journal</span><span class="sxs-lookup"><span data-stu-id="09b2a-114">Tail-Log Backup</span></span>  
 <span data-ttu-id="09b2a-115">Avant de restaurer la base de données, l'administrateur de la base de données doit sauvegarder la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="09b2a-115">Before restoring the database, the database administrator must back up the tail of the log.</span></span> <span data-ttu-id="09b2a-116">La base de données étant endommagée, la création de la sauvegarde de la fin du journal requiert l'utilisation de l'option NO_TRUNCATE :</span><span class="sxs-lookup"><span data-stu-id="09b2a-116">Because the database is damaged, creating the tail-log backup requires using the NO_TRUNCATE option:</span></span>  
  
```  
BACKUP LOG adb TO tailLogBackup   
   WITH NORECOVERY, NO_TRUNCATE  
```  
  
 <span data-ttu-id="09b2a-117">La sauvegarde de la fin du journal est la dernière sauvegarde appliquée dans les séquences de restauration qui suivent.</span><span class="sxs-lookup"><span data-stu-id="09b2a-117">The tail-log backup is the last backup that is applied in the following restore sequences.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="09b2a-118">Séquence de restauration</span><span class="sxs-lookup"><span data-stu-id="09b2a-118">Restore Sequence</span></span>  
 <span data-ttu-id="09b2a-119">Pour restaurer le groupe de fichiers primaire et le groupe de fichiers `B`, l'administrateur de base de données utilise une séquence de restauration sans l'option PARTIAL, comme suit :</span><span class="sxs-lookup"><span data-stu-id="09b2a-119">To restore the primary filegroup and filegroup `B`, the database administrator uses a restore sequence without the PARTIAL option, as follows:</span></span>  
  
```  
RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
WITH NORECOVERY  
RESTORE DATABASE adb FILEGROUP='B' FROM backup2   
WITH NORECOVERY  
RESTORE LOG adb FROM backup3 WITH NORECOVERY  
RESTORE LOG adb FROM backup4 WITH NORECOVERY  
RESTORE LOG adb FROM backup5 WITH NORECOVERY  
RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
```  
  
 <span data-ttu-id="09b2a-120">Les fichiers non restaurés sont automatiquement mis en ligne.</span><span class="sxs-lookup"><span data-stu-id="09b2a-120">The files that are not restored are automatically brought online.</span></span> <span data-ttu-id="09b2a-121">Tous les groupes de fichiers sont désormais en ligne.</span><span class="sxs-lookup"><span data-stu-id="09b2a-121">All the filegroups are now online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b2a-122"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09b2a-122">See Also</span></span>  
 <span data-ttu-id="09b2a-123">[Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="09b2a-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="09b2a-124">[Restaurations fragmentaires &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="09b2a-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="09b2a-125">[Restaurations de fichiers &#40;mode de récupération complète&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="09b2a-125">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="09b2a-126">[Appliquer les sauvegardes du journal des transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="09b2a-126">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 [<span data-ttu-id="09b2a-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="09b2a-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
