---
title: 'Exemple : restauration fragmentaire d’une base de données (Mode de restauration simple) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], simple recovery model
- restore sequences [SQL Server], piecemeal
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: 9834b14a-4e56-4654-b190-c2a38624b6b4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69de84fa2ff3a853eb9926549ad4859d2f1ae38e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704204"
---
# <a name="example-piecemeal-restore-of-database-simple-recovery-model"></a><span data-ttu-id="01c45-102">Exemple : Restauration fragmentaire d’une base de données (mode de récupération simple)</span><span class="sxs-lookup"><span data-stu-id="01c45-102">Example: Piecemeal Restore of Database (Simple Recovery Model)</span></span>
  <span data-ttu-id="01c45-103">Une séquence de restauration fragmentaire restaure et récupère une base de données par étapes au niveau des groupes de fichiers, en commençant par le groupe de fichiers primaire et tous les groupes de fichiers secondaires en lecture-écriture.</span><span class="sxs-lookup"><span data-stu-id="01c45-103">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, starting with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="01c45-104">Dans cet exemple, la base de données `adb` est restaurée sur un nouvel ordinateur après un problème grave.</span><span class="sxs-lookup"><span data-stu-id="01c45-104">In this example, database `adb` is restored to a new computer after a disaster.</span></span> <span data-ttu-id="01c45-105">La base de données utilise le mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="01c45-105">The database is using the simple recovery model.</span></span> <span data-ttu-id="01c45-106">Avant le sinistre, tous les groupes de fichiers sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="01c45-106">Before the disaster, all the filegroups are online.</span></span> <span data-ttu-id="01c45-107">Les groupes de fichiers `A` et `C` sont en lecture-écriture, et le groupe de fichiers `B` est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="01c45-107">Filegroups `A` and `C` are read/write, and filegroup `B` is read-only.</span></span> <span data-ttu-id="01c45-108">Le groupe de fichiers `B` est passé en lecture seule avant la sauvegarde partielle la plus récente qui contient le groupe de fichiers principal et les groupes de fichiers secondaires en lecture-écriture, `A` et `C`.</span><span class="sxs-lookup"><span data-stu-id="01c45-108">Filegroup `B` became read-only before the most recent partial backup, which contains the primary filegroup and the read/write secondary filegroups, `A` and `C`.</span></span> <span data-ttu-id="01c45-109">Après le passage du groupe de fichiers `B` en lecture seule, une sauvegarde de fichiers séparée du groupe de fichiers `B` a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="01c45-109">After filegroup `B` became read-only, a separate file backup of filegroup `B` was taken.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="01c45-110">Séquences de restauration</span><span class="sxs-lookup"><span data-stu-id="01c45-110">Restore Sequences</span></span>  
  
1.  <span data-ttu-id="01c45-111">Restauration partielle des groupes de fichiers primaires `A` et `C`.</span><span class="sxs-lookup"><span data-stu-id="01c45-111">Partial restore of the primary and filegroups `A` and `C`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='A',FILEGROUP='C'   
       FROM partial_backup   
       WITH PARTIAL, RECOVERY;  
  
    ```  
  
     <span data-ttu-id="01c45-112">À ce stade, le groupe de fichiers primaire et les groupes de fichiers `A` et `C` sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="01c45-112">At this point, the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="01c45-113">Tous les fichiers du groupe de fichiers `B` sont en attente de récupération et le groupe de fichiers est hors connexion.</span><span class="sxs-lookup"><span data-stu-id="01c45-113">All files in filegroup `B` are recovery pending, and the filegroup is offline.</span></span>  
  
2.  <span data-ttu-id="01c45-114">Restauration en ligne du groupe de fichiers `B`.</span><span class="sxs-lookup"><span data-stu-id="01c45-114">Online restore of filegroup `B`.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup WITH RECOVERY;  
  
    ```  
  
     <span data-ttu-id="01c45-115">Tous les groupes de fichiers sont maintenant en ligne.</span><span class="sxs-lookup"><span data-stu-id="01c45-115">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="01c45-116">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="01c45-116">Additional Examples</span></span>  
  
-   [<span data-ttu-id="01c45-117">Exemple : restauration fragmentaire de quelques groupes de fichiers uniquement &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="01c45-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="01c45-118">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="01c45-118">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="01c45-119">Exemple : restauration fragmentaire d’une base de données &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="01c45-119">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="01c45-120">Exemple : restauration fragmentaire de quelques groupes de fichiers &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="01c45-120">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="01c45-121">Exemple : restauration en ligne d’un fichier en lecture/écriture &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="01c45-121">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="01c45-122">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="01c45-122">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="01c45-123"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01c45-123">See Also</span></span>  
 <span data-ttu-id="01c45-124">[Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="01c45-124">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="01c45-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01c45-125">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="01c45-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01c45-126">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="01c45-127">Restaurations fragmentaires &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="01c45-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
