---
title: 'Exemple : restauration fragmentaire de quelques groupes de fichiers (mode de récupération simple) | Microsoft Docs'
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
ms.assetid: d7ad026c-5355-4308-9560-0dc843940d4f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8254ac96a269b6fb433759e5a649bf9df1b7feac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709676"
---
# <a name="example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model"></a><span data-ttu-id="fa785-102">Exemple : Restauration fragmentaire de quelques groupes de fichiers uniquement (mode de récupération simple)</span><span class="sxs-lookup"><span data-stu-id="fa785-102">Example: Piecemeal Restore of Only Some Filegroups (Simple Recovery Model)</span></span>
  <span data-ttu-id="fa785-103">Cette rubrique concerne les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] obéissant au mode de récupération simple et contenant un groupe de fichiers en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="fa785-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span>  
  
 <span data-ttu-id="fa785-104">Une séquence de restauration fragmentaire restaure et récupère une base de données par étapes au niveau des groupes de fichiers, en commençant par le groupe de fichiers primaire et tous les groupes de fichiers secondaires en lecture-écriture.</span><span class="sxs-lookup"><span data-stu-id="fa785-104">A piecemeal restore sequence restores and recovers a database in stages at the filegroup level, beginning with the primary and all read/write, secondary filegroups.</span></span>  
  
 <span data-ttu-id="fa785-105">Dans cet exemple, une base de données appelée `adb`qui utilise le mode de récupération simple, contient trois groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="fa785-105">In this example, a database named `adb`, which uses the simple recovery model, contains three filegroups.</span></span> <span data-ttu-id="fa785-106">Le groupe de fichiers `A` est en lecture-écriture, et les groupes de fichiers `B` et `C` sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="fa785-106">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="fa785-107">Au départ, tous les groupes de fichiers sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="fa785-107">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="fa785-108">Le groupe de fichiers primaire et le groupe de fichiers `B` de la base de données `adb` s'avèrent endommagés. L'administrateur de la base de données décide donc de les restaurer à l'aide d'une séquence de restauration fragmentaire.</span><span class="sxs-lookup"><span data-stu-id="fa785-108">The primary and filegroup `B` of database `adb` appear to be damaged; therefore, the database administrator decides to restore them by using a piecemeal restore sequence.</span></span> <span data-ttu-id="fa785-109">En mode de récupération simple, tous les groupes de fichiers en lecture-écriture doivent être restaurés à partir de la même sauvegarde partielle.</span><span class="sxs-lookup"><span data-stu-id="fa785-109">Under the simple recovery model, all read/write filegroups must be restored from the same partial backup.</span></span> <span data-ttu-id="fa785-110">Même si le groupe de fichiers `A` est intact, celui-ci doit être restauré avec le groupe de fichiers primaire pour s'assurer de sa cohérence (la base de données sera restaurée à un point dans le temps défini à la fin de la dernière sauvegarde partielle).</span><span class="sxs-lookup"><span data-stu-id="fa785-110">Although filegroup `A` is intact, it must be restored with the primary filegroup to make sure that they are consistent (the database will be restored to the point in time defined by the end of the last partial backup).</span></span> <span data-ttu-id="fa785-111">Le groupe de fichiers `C` est intact, mais il doit être récupéré pour être mis en ligne.</span><span class="sxs-lookup"><span data-stu-id="fa785-111">Filegroup `C` is intact, but it must be recovered to bring it online.</span></span> <span data-ttu-id="fa785-112">Bien que le groupe de fichiers `B`soit endommagé, il contient des données moins critiques que le groupe de fichiers `C`. Par conséquent, `B` sera restauré en dernier.</span><span class="sxs-lookup"><span data-stu-id="fa785-112">Filegroup `B`, although damaged, contains less critical data than Filegroup `C`; therefore, `B` will be restored last.</span></span>  
  
## <a name="restore-sequences"></a><span data-ttu-id="fa785-113">Séquences de restauration</span><span class="sxs-lookup"><span data-stu-id="fa785-113">Restore Sequences</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa785-114">La syntaxe pour une séquence de restauration en ligne est la même que pour une séquence de restauration hors connexion.</span><span class="sxs-lookup"><span data-stu-id="fa785-114">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
1.  <span data-ttu-id="fa785-115">Restauration partielle du groupe de fichiers primaire et du groupe de fichiers `A` à partir d'une sauvegarde partielle</span><span class="sxs-lookup"><span data-stu-id="fa785-115">Partial restore of the primary and filegroup `A` from a partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb READ_WRITE_FILEGROUPS FROM partial_backup   
    WITH PARTIAL, RECOVERY  
    ```  
  
     <span data-ttu-id="fa785-116">À ce stade, le groupe de fichiers primaire et le groupe de fichiers `A` sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="fa785-116">At this point the primary filegroup and filegroup `A` are online.</span></span> <span data-ttu-id="fa785-117">Les fichiers dans les groupes de fichiers `B` et `C` sont en attente de récupération et les groupes de fichiers sont hors connexion.</span><span class="sxs-lookup"><span data-stu-id="fa785-117">Files in filegroups `B` and `C` are recovery pending, and the filegroups are offline.</span></span>  
  
2.  <span data-ttu-id="fa785-118">Récupération en ligne du groupe de fichiers `C`.</span><span class="sxs-lookup"><span data-stu-id="fa785-118">Online recovery of filegroup `C`.</span></span>  
  
     <span data-ttu-id="fa785-119">Le groupe de fichiers `C` est cohérent car la sauvegarde partielle restaurée ci-dessus a été effectuée une fois que le groupe de fichiers `C` est passé en lecture seule, même si la restauration de la base de données a été effectuée antérieurement.</span><span class="sxs-lookup"><span data-stu-id="fa785-119">Filegroup `C` is consistent because the partial backup that was restored above was taken after filegroup `C` became read-only, although the database was taken back in time by the restore.</span></span> <span data-ttu-id="fa785-120">L'administrateur de la base de données récupère le groupe de fichiers `C`, sans le restaurer, pour le mettre en ligne.</span><span class="sxs-lookup"><span data-stu-id="fa785-120">The database administrator recovers the filegroup `C`, without restoring it, to bring it online.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='C' WITH RECOVERY  
    ```  
  
     <span data-ttu-id="fa785-121">À ce stade, le groupe de fichiers primaire et les groupes de fichiers `A` et `C` sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="fa785-121">At this point the primary and filegroups `A` and `C` are online.</span></span> <span data-ttu-id="fa785-122">Les fichiers du groupe de fichiers B restent en attente de récupération et le groupe de fichiers est hors connexion.</span><span class="sxs-lookup"><span data-stu-id="fa785-122">Files in filegroupB remain recovery pending, with the filegroup offline.</span></span>  
  
3.  <span data-ttu-id="fa785-123">Restauration en ligne du groupe de fichiers `B.`</span><span class="sxs-lookup"><span data-stu-id="fa785-123">Online restore of filegroup `B.`</span></span>  
  
     <span data-ttu-id="fa785-124">Les fichiers du groupe de fichiers `B` doivent être restaurés.</span><span class="sxs-lookup"><span data-stu-id="fa785-124">Files in filegroup `B` must be restored.</span></span> <span data-ttu-id="fa785-125">L'administrateur de la base de données restaure la sauvegarde du groupe de fichiers `B` effectuée après que ce groupe de fichiers `B` est passé en lecture seule et avant la sauvegarde partielle.</span><span class="sxs-lookup"><span data-stu-id="fa785-125">The database administrator restores the backup of filegroup `B` taken after filegroup `B` became read-only and before the partial backup.</span></span>  
  
    ```  
    RESTORE DATABASE adb FILEGROUP='B' FROM backup   
    WITH RECOVERY  
    ```  
  
     <span data-ttu-id="fa785-126">Tous les groupes de fichiers sont maintenant en ligne.</span><span class="sxs-lookup"><span data-stu-id="fa785-126">All filegroups are now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="fa785-127">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="fa785-127">Additional Examples</span></span>  
  
-   [<span data-ttu-id="fa785-128">Exemple : restauration fragmentaire d’une base de données &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="fa785-128">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="fa785-129">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="fa785-129">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="fa785-130">Exemple : restauration fragmentaire d’une base de données &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="fa785-130">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="fa785-131">Exemple : restauration fragmentaire de quelques groupes de fichiers &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="fa785-131">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="fa785-132">Exemple : restauration en ligne d’un fichier en lecture/écriture &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="fa785-132">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="fa785-133">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="fa785-133">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="fa785-134"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa785-134">See Also</span></span>  
 <span data-ttu-id="fa785-135">[Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fa785-135">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="fa785-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa785-136">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="fa785-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fa785-137">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="fa785-138">Restaurations fragmentaires &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fa785-138">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
