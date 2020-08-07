---
title: Récupérer une base de données sans restaurer les données (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring [SQL Server], recovery-only
- recovery-only scenario [SQL Server]
- restoring databases [SQL Server], recovery-only
- recovery [SQL Server], recovery-only
- database recovery [SQL Server]
- database restores [SQL Server], recovery-only
- recovery [SQL Server], without restoring data
ms.assetid: 7e8fa620-315d-4e10-a718-23fa5171c09e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 04e4f78e51adb803bb65530c0b3b903aa7f76419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612431"
---
# <a name="recover-a-database-without-restoring-data-transact-sql"></a><span data-ttu-id="7a26e-102">Récupérer une base de données sans restaurer les données (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7a26e-102">Recover a Database Without Restoring Data (Transact-SQL)</span></span>
  <span data-ttu-id="7a26e-103">En général, toutes les données dans une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont restaurées avant que la base de données ne soit récupérée.</span><span class="sxs-lookup"><span data-stu-id="7a26e-103">Usually, all of the data in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is restored before the database is recovered.</span></span> <span data-ttu-id="7a26e-104">Toutefois, une opération de restauration peut récupérer une base de données sans réellement restaurer une sauvegarde, par exemple lors de la récupération d'un fichier en lecture seule qui est cohérent avec la base de données.</span><span class="sxs-lookup"><span data-stu-id="7a26e-104">However, a restore operation can recover a database without actually restoring a backup; for example, when recovering a read-only file that is consistent with the database.</span></span> <span data-ttu-id="7a26e-105">Il s’agit d’une *restauration avec récupération uniquement*.</span><span class="sxs-lookup"><span data-stu-id="7a26e-105">This is referred to as a *recovery-only restore*.</span></span> <span data-ttu-id="7a26e-106">Lorsque des données hors ligne sont déjà cohérentes avec la base de données et doivent uniquement être rendues disponibles, une restauration avec récupération uniquement termine la récupération de la base de données et met les données en ligne.</span><span class="sxs-lookup"><span data-stu-id="7a26e-106">When offline data is already consistent with the database and needs only to be made available, a recovery-only restore operation completes the recovery of the database and bring the data online.</span></span>  
  
 <span data-ttu-id="7a26e-107">Une restauration avec récupération uniquement peut se produire pour une base de données entière ou pour un ou plusieurs fichiers ou groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="7a26e-107">A recovery-only restore can occur for a whole database or for one or more a files or filegroups.</span></span>  
  
## <a name="recovery-only-database-restore"></a><span data-ttu-id="7a26e-108">Restauration de base de données avec récupération uniquement</span><span class="sxs-lookup"><span data-stu-id="7a26e-108">Recovery-Only Database Restore</span></span>  
 <span data-ttu-id="7a26e-109">Une restauration de base de données avec récupération uniquement est utile dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7a26e-109">A recovery-only database restore can be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="7a26e-110">Vous n'avez pas récupéré la base de données lors de la restauration de la dernière sauvegarde au cours d'une séquence de restauration, et vous voulez à présent récupérer cette base de données pour la mettre en ligne.</span><span class="sxs-lookup"><span data-stu-id="7a26e-110">You did not recover the database when restoring the last backup in a restore sequence, and you now want to recover the database to bring it online.</span></span>  
  
-   <span data-ttu-id="7a26e-111">La base de données est en mode veille, et vous voulez qu'elle puisse être mise à jour sans appliquer une autre sauvegarde de journal.</span><span class="sxs-lookup"><span data-stu-id="7a26e-111">The database is in standby mode, and you want to make the database updatable without applying another log backup.</span></span>  
  
 <span data-ttu-id="7a26e-112">La syntaxe [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) pour une restauration de base de données avec récupération uniquement est la suivante :</span><span class="sxs-lookup"><span data-stu-id="7a26e-112">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only database restore is as follows:</span></span>  
  
 <span data-ttu-id="7a26e-113">RESTORE DATABASE *nom_base_de_données* WITH RECOVERY</span><span class="sxs-lookup"><span data-stu-id="7a26e-113">RESTORE DATABASE *database_name* WITH RECOVERY</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a26e-114">La clause FROM **=** \<*backup_device>\* n'est pas destinée aux restaurations avec récupération uniquement, car aucune sauvegarde n'est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="7a26e-114">The FROM **=** \<*backup_device>\* clause is not used for recovery-only restores because no backup is necessary.</span></span>  
  
 <span data-ttu-id="7a26e-115">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="7a26e-115">**Example**</span></span>  
  
 <span data-ttu-id="7a26e-116">L'exemple suivant récupère l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] dans le cadre d'une opération de restauration sans restaurer les données.</span><span class="sxs-lookup"><span data-stu-id="7a26e-116">The following example recovers the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in a restore operation without restoring data.</span></span>  
  
```  
-- Restore database using WITH RECOVERY.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY  
```  
  
## <a name="recovery-only-file-restore"></a><span data-ttu-id="7a26e-117">Restauration de fichier avec récupération uniquement</span><span class="sxs-lookup"><span data-stu-id="7a26e-117">Recovery-Only File Restore</span></span>  
 <span data-ttu-id="7a26e-118">Une restauration de fichier avec récupération uniquement est utile dans la situation suivante :</span><span class="sxs-lookup"><span data-stu-id="7a26e-118">A recovery-only file restore can be useful in the following situation:</span></span>  
  
 <span data-ttu-id="7a26e-119">Une base de données est restaurée par fragments.</span><span class="sxs-lookup"><span data-stu-id="7a26e-119">A database is restored piecemeal.</span></span> <span data-ttu-id="7a26e-120">Une fois le groupe de fichiers primaire restauré, un ou plusieurs des fichiers non restaurés sont cohérents avec le nouvel état de la base de données, peut-être pour avoir été en lecture seule un moment.</span><span class="sxs-lookup"><span data-stu-id="7a26e-120">After restore of the primary filegroup is complete, one or more of the unrestored files are consistent with the new database state, perhaps because it has been read-only for some time.</span></span> <span data-ttu-id="7a26e-121">Ces fichiers doivent seulement être récupérés ; la copie des données n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="7a26e-121">These files only have to be recovered; data copying is unnecessary.</span></span>  
  
 <span data-ttu-id="7a26e-122">Une opération de restauration avec récupération uniquement met en ligne les données du groupe de fichiers hors connexion ; aucune phase de copie des données ni d'annulation ou de restauration par progression n'est effectuée.</span><span class="sxs-lookup"><span data-stu-id="7a26e-122">A recovery-only restore operation brings the data in the offline filegroup online; no data-copy, redo, or undo phase occurs.</span></span> <span data-ttu-id="7a26e-123">Pour plus d’informations sur les phases de restauration, consultez [Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a26e-123">For information about the phases of restore, see [Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md).</span></span>  
  
 <span data-ttu-id="7a26e-124">La syntaxe [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) pour une restauration de fichier avec récupération uniquement est la suivante :</span><span class="sxs-lookup"><span data-stu-id="7a26e-124">The [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) syntax for a recovery-only file restore is:</span></span>  
  
 <span data-ttu-id="7a26e-125">RESTAURER la base de données *database_name* {file **=** _logical_file_name_ | GROUPE **=** de fichiers _logical_filegroup_name_ } [ **,**... *n* ] avec récupération</span><span class="sxs-lookup"><span data-stu-id="7a26e-125">RESTORE DATABASE *database_name* { FILE **=**_logical_file_name_ | FILEGROUP **=**_logical_filegroup_name_ }[ **,**...*n* ] WITH RECOVERY</span></span>  
  
 <span data-ttu-id="7a26e-126">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="7a26e-126">**Example**</span></span>  
  
 <span data-ttu-id="7a26e-127">L'exemple suivant illustre une restauration de fichier avec récupération uniquement des fichiers dans un groupe de fichiers secondaire, `SalesGroup2`, dans la base de données `Sales` .</span><span class="sxs-lookup"><span data-stu-id="7a26e-127">The following example illustrates a recovery-only file restore of the files in a secondary filegroup, `SalesGroup2`, in the `Sales` database.</span></span> <span data-ttu-id="7a26e-128">Le groupe de fichiers primaire a déjà été restauré au cours de l'étape initiale d'une restauration fragmentaire, et `SalesGroup2` est cohérent avec le groupe de fichiers primaire restauré.</span><span class="sxs-lookup"><span data-stu-id="7a26e-128">The primary filegroup has already been restored as the initial step of a piecemeal restore, and `SalesGroup2` is consistent with the restored primary filegroup.</span></span> <span data-ttu-id="7a26e-129">La récupération de ce groupe de fichiers et sa mise en ligne ne requièrent qu'une seule instruction.</span><span class="sxs-lookup"><span data-stu-id="7a26e-129">Recovering this filegroup and bringing it online requires only a single statement.</span></span>  
  
```  
RESTORE DATABASE Sales FILEGROUP=SalesGroup2 WITH RECOVERY;  
```  
  
## <a name="examples-of-completing-a-piecemeal-restore-scenario-with-a-recovery-only-restore"></a><span data-ttu-id="7a26e-130">Exemples de finalisation d'un scénario de restauration fragmentaire à l'aide d'une restauration avec récupération uniquement</span><span class="sxs-lookup"><span data-stu-id="7a26e-130">Examples of Completing a Piecemeal Restore Scenario with a Recovery-Only Restore</span></span>  
 <span data-ttu-id="7a26e-131">**Mode de récupération simple**</span><span class="sxs-lookup"><span data-stu-id="7a26e-131">**Simple recovery model**</span></span>  
  
-   [<span data-ttu-id="7a26e-132">Exemple : restauration fragmentaire d’une base de données &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="7a26e-132">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="7a26e-133">Exemple : restauration fragmentaire de quelques groupes de fichiers uniquement &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="7a26e-133">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
 <span data-ttu-id="7a26e-134">**Mode de restauration complète**</span><span class="sxs-lookup"><span data-stu-id="7a26e-134">**Full recovery model**</span></span>  
  
-   [<span data-ttu-id="7a26e-135">Exemple : restauration fragmentaire d’une base de données &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="7a26e-135">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="7a26e-136">Exemple : restauration fragmentaire de quelques groupes de fichiers &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="7a26e-136">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Restore.SqlRestore%2A>  
  
## <a name="see-also"></a><span data-ttu-id="7a26e-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a26e-137">See Also</span></span>  
 <span data-ttu-id="7a26e-138">[Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a26e-138">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="7a26e-139">[Restaurations fragmentaires &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a26e-139">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="7a26e-140">[Restaurations de fichiers &#40;mode de récupération simple&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="7a26e-140">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="7a26e-141">[Restaurations de fichiers &#40;mode de récupération complète&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="7a26e-141">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="7a26e-142">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7a26e-142">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
