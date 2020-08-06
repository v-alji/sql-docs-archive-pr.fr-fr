---
title: Restauration fragmentaire de bases de données avec des tables mémoire optimisées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 732c9721-8dd4-481d-8ff9-1feaaa63f84f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ed23f08d40e23b1d43c1b642f4089fe77646b675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706492"
---
# <a name="piecemeal-restore-of-databases-with-memory-optimized-tables"></a><span data-ttu-id="98eae-102">Restauration fragmentaire de bases de données avec des tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="98eae-102">Piecemeal Restore of Databases With Memory-Optimized Tables</span></span>
  <span data-ttu-id="98eae-103">La restauration fragmentaire est prise en charge sur les bases de données avec des tables mémoire optimisées, à l'exception d'une restriction décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="98eae-103">Piecemeal restore is supported on databases with memory-optimized tables except for one restriction described below.</span></span> <span data-ttu-id="98eae-104">Pour plus d’informations sur la sauvegarde et restauration fragmentaires, consultez [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) et [Restaurations fragmentaires &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="98eae-104">For more information about piecemeal backup and restore, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [Piecemeal Restores &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span></span>  
  
 <span data-ttu-id="98eae-105">Un groupe de fichiers mémoire optimisé doit être sauvegardé et restauré avec le groupe de fichiers principal.</span><span class="sxs-lookup"><span data-stu-id="98eae-105">A memory-optimized filegroup must be backed up and restored together with the primary filegroup:</span></span>  
  
-   <span data-ttu-id="98eae-106">Si vous sauvegardez (ou restaurez) le groupe de fichiers principal, vous devez spécifier le groupe de fichiers mémoire optimisé.</span><span class="sxs-lookup"><span data-stu-id="98eae-106">If you back up (or restore) the primary filegroup you must specify the memory-optimized filegroup.</span></span>  
  
-   <span data-ttu-id="98eae-107">Si vous sauvegardez (ou restaurez) le groupe de fichiers mémoire optimisé, vous devez spécifier le groupe de fichiers principal.</span><span class="sxs-lookup"><span data-stu-id="98eae-107">If you backup (or restore) the memory-optimized filegroup you must specify the primary filegroup.</span></span>  
  
 <span data-ttu-id="98eae-108">Principaux scénarios de sauvegarde et de restauration fragmentaires</span><span class="sxs-lookup"><span data-stu-id="98eae-108">Key scenarios for piecemeal backup and restore are,</span></span>  
  
-   <span data-ttu-id="98eae-109">La sauvegarde fragmentaire vous permet de réduire la taille de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="98eae-109">Piecemeal backup allows you to reduce the size of backup.</span></span> <span data-ttu-id="98eae-110">Exemples :</span><span class="sxs-lookup"><span data-stu-id="98eae-110">Some examples:</span></span>  
  
    -   <span data-ttu-id="98eae-111">Configurez la sauvegarde de base de données de façon à ce qu'elle se produise à différentes heures ou différents jours pour réduire l'impact sur la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="98eae-111">Configure the database backup to occur at different times or days to minimize the impact on the workload.</span></span> <span data-ttu-id="98eae-112">Par exemple, une base de données très volumineuse (de plus de 1 To) où une sauvegarde complète de la base de données ne peut pas être effectuée dans le temps alloué pour la maintenance de la base de données.</span><span class="sxs-lookup"><span data-stu-id="98eae-112">One example is a very large database (greater than 1 TB) where a full database backup cannot complete in the time allocated for database maintenance.</span></span> <span data-ttu-id="98eae-113">Dans ce cas, utilisez une sauvegarde fragmentaire pour sauvegarder la base de données complète en plusieurs sauvegardes fragmentaires.</span><span class="sxs-lookup"><span data-stu-id="98eae-113">In that situation, you can use piecemeal backup to backup the full database in multiple piecemeal backups.</span></span>  
  
    -   <span data-ttu-id="98eae-114">Si un groupe de fichiers est indiqué comme étant en lecture seule, il ne nécessite pas de sauvegarde du journal des transactions après qu'il a été marqué en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="98eae-114">If a filegroup is marked read-only, it does not require a transaction log backup after it was marked read-only.</span></span> <span data-ttu-id="98eae-115">Vous pouvez choisir de sauvegarder le groupe de fichiers une seule fois après son marquage en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="98eae-115">You can choose to back up the filegroup only once after marking it read-only.</span></span>  
  
-   <span data-ttu-id="98eae-116">Restauration fragmentaire.</span><span class="sxs-lookup"><span data-stu-id="98eae-116">Piecemeal restore.</span></span>  
  
    -   <span data-ttu-id="98eae-117">Le but d'une restauration fragmentaire consiste à mettre en ligne les parties critiques de base de données sans attendre toutes les données.</span><span class="sxs-lookup"><span data-stu-id="98eae-117">The goal of a piecemeal restore is to bring the critical parts of database online without waiting for all the data.</span></span> <span data-ttu-id="98eae-118">Par exemple, si une base de données contient des données partitionnées, les partitions les plus anciennes sont rarement utilisées.</span><span class="sxs-lookup"><span data-stu-id="98eae-118">One example is if a database has partitioned data, such that older partitions are only used rarely.</span></span> <span data-ttu-id="98eae-119">Vous pouvez les restaurer uniquement si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="98eae-119">You can restore them only on an as-needed basis.</span></span> <span data-ttu-id="98eae-120">Il en va de même pour les groupes de fichiers qui contiennent, par exemple, des données d'historique.</span><span class="sxs-lookup"><span data-stu-id="98eae-120">Similar for filegroups that contain, for example, historical data.</span></span>  
  
    -   <span data-ttu-id="98eae-121">Utilisez la réparation de page pour résoudre l'altération de page lors de la restauration spécifique de la page.</span><span class="sxs-lookup"><span data-stu-id="98eae-121">Using page repair, you can fix page corruption by specifically restoring the page.</span></span> <span data-ttu-id="98eae-122">Pour plus d’informations, consultez [Restaurer des pages &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="98eae-122">For more information, see [Restore Pages &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span></span>  
  
## <a name="samples"></a><span data-ttu-id="98eae-123">Exemples</span><span class="sxs-lookup"><span data-stu-id="98eae-123">Samples</span></span>  
 <span data-ttu-id="98eae-124">Les exemples utilisent le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="98eae-124">The examples use the following schema:</span></span>  
  
```  
CREATE DATABASE imoltp  
ON PRIMARY (name = imoltp_primary1, filename = 'c:\data\imoltp_data1.mdf')  
LOG ON (name = imoltp_log, filename = 'c:\data\imoltp_log.ldf')  
GO  
  
ALTER DATABASE imoltp ADD FILE (name = imoltp_primary2, filename = 'c:\data\imoltp_data2.ndf')  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_secondary  
ALTER DATABASE imoltp ADD FILE (name = imoltp_secondary, filename = 'c:\data\imoltp_secondary.ndf') TO FILEGROUP imoltp_secondary  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_mod CONTAINS MEMORY_OPTIMIZED_DATA   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod1', filename='c:\data\imoltp_mod1') TO FILEGROUP imoltp_mod   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod2', filename='c:\data\imoltp_mod2') TO FILEGROUP imoltp_mod   
GO  
```  
  
### <a name="backup"></a><span data-ttu-id="98eae-125">Sauvegarde</span><span class="sxs-lookup"><span data-stu-id="98eae-125">Backup</span></span>  
 <span data-ttu-id="98eae-126">Cet exemple montre comment sauvegarder le groupe de fichiers principal et le groupe de fichiers mémoire optimisé.</span><span class="sxs-lookup"><span data-stu-id="98eae-126">This sample shows how to backup the primary filegroup and the memory-optimized filegroup.</span></span> <span data-ttu-id="98eae-127">Vous devez spécifier le groupe de fichiers principal et le groupe de fichiers mémoire optimisé.</span><span class="sxs-lookup"><span data-stu-id="98eae-127">You must specify both primary and memory-optimized filegroup together.</span></span>  
  
```  
backup database imoltp filegroup='primary', filegroup='imoltp_mod' to disk='c:\data\imoltp.dmp' with init  
```  
  
 <span data-ttu-id="98eae-128">L'exemple suivant montre qu'une sauvegarde d'un ou plusieurs groupes de fichiers autres que le groupe de fichiers principal et le groupe de fichiers mémoire optimisé est similaire dans les bases de données sans tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="98eae-128">The following sample shows that a back up of filegroup(s) other than primary and memory-optimized filegroup works similar to the databases without memory-optimized tables.</span></span> <span data-ttu-id="98eae-129">La commande suivante permet de sauvegarder le groupe de fichiers secondaire</span><span class="sxs-lookup"><span data-stu-id="98eae-129">The following command backups up the secondary filegroup</span></span>  
  
```  
backup database imoltp filegroup='imoltp_secondary' to disk='c:\data\imoltp_secondary.dmp' with init  
```  
  
### <a name="restore"></a><span data-ttu-id="98eae-130">Restaurer</span><span class="sxs-lookup"><span data-stu-id="98eae-130">Restore</span></span>  
 <span data-ttu-id="98eae-131">Cet exemple montre comment restaurer le groupe de fichiers principal et le groupe de fichiers mémoire optimisé ensemble.</span><span class="sxs-lookup"><span data-stu-id="98eae-131">The following sample shows how to restore the primary filegroup and memory-optimized filegroup together.</span></span>  
  
```  
restore database imoltp filegroup = 'primary', filegroup = 'imoltp_mod'   
from disk='c:\data\imoltp.dmp' with partial, norecovery  
  
--restore the transaction log  
 RESTORE LOG [imoltp] FROM DISK = N'c:\data\imoltp_log.dmp' WITH  FILE = 1,  NOUNLOAD,  STATS = 10  
GO  
```  
  
 <span data-ttu-id="98eae-132">L'exemple suivant montre que la restauration d'un ou plusieurs groupes de fichiers autres que le groupe de fichiers principal et le groupe de fichiers mémoire optimisé est similaire dans les bases de données sans tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="98eae-132">The next sample shows that restoring filegroup(s) other than the primary and memory-optimized filegroup works similar to the databases without memory-optimized tables</span></span>  
  
```  
RESTORE DATABASE [imoltp] FILE = N'imoltp_secondary'   
FROM  DISK = N'c:\data\imoltp_secondary.dmp' WITH  FILE = 1,  RECOVERY,  NOUNLOAD,  STATS = 10  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="98eae-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98eae-133">See Also</span></span>  
 [<span data-ttu-id="98eae-134">Sauvegarder, restaurer et récupérer des tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="98eae-134">Backup, Restore, and Recovery of Memory-Optimized Tables</span></span>](../../database-engine/backup-restore-and-recovery-of-memory-optimized-tables.md)  
  
  
