---
title: Vue d’ensemble de la sauvegarde (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], backing up data
- backups [SQL Server]
- database backups [SQL Server]
- backup types [SQL Server]
- data backups [SQL Server]
- backing up tables [SQL Server]
- database restores [SQL Server], backups
- backing up [SQL Server], about backing up
- restoring [SQL Server], backup types
- backups [SQL Server], about
- backups [SQL Server], table-level backups unsupported
ms.assetid: 09a6e0c2-d8fd-453f-9aac-4ff24a97dc1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60fbd0341c4e29c6f98cc4d5fe5a2cfabc9b703f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614683"
---
# <a name="backup-overview-sql-server"></a><span data-ttu-id="a586a-102">Backup Overview (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a586a-102">Backup Overview (SQL Server)</span></span>
  <span data-ttu-id="a586a-103">Cette rubrique présente le composant de sauvegarde de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a586a-103">This topic introduces the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup component.</span></span> <span data-ttu-id="a586a-104">La sauvegarde de votre base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est essentielle pour protéger vos données.</span><span class="sxs-lookup"><span data-stu-id="a586a-104">Backing up your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is essential for protecting your data.</span></span> <span data-ttu-id="a586a-105">Cette discussion couvre les types de sauvegardes et les restrictions liées aux sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="a586a-105">This discussion covers backup types, and backup restrictions.</span></span> <span data-ttu-id="a586a-106">La rubrique présente également les unités et les supports de sauvegarde de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a586a-106">The topic also introduces [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices and backup media.</span></span>  
  
 <span data-ttu-id="a586a-107">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="a586a-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="a586a-108">Composants et concepts</span><span class="sxs-lookup"><span data-stu-id="a586a-108">Components and Concepts</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="a586a-109">Compression de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a586a-109">Backup Compression</span></span>](#BackupCompression)  
  
-   [<span data-ttu-id="a586a-110">Restrictions sur les opérations de sauvegarde dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="a586a-110">Restrictions on Backup Operations in SQL Server</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="a586a-111">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a586a-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="components-and-concepts"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="a586a-112">Composants et concepts</span><span class="sxs-lookup"><span data-stu-id="a586a-112">Components and Concepts</span></span>  
 <span data-ttu-id="a586a-113">sauvegarder [verbe]</span><span class="sxs-lookup"><span data-stu-id="a586a-113">back up [verb]</span></span>  
 <span data-ttu-id="a586a-114">Copie les données ou les enregistrements de journal d'une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou de son journal des transactions sur une unité de sauvegarde, telle qu'un disque, pour créer une sauvegarde de données ou de journal.</span><span class="sxs-lookup"><span data-stu-id="a586a-114">Copies the data or log records from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database or its transaction log to a backup device, such as a disk, to create a data backup or log backup.</span></span>  
  
 <span data-ttu-id="a586a-115">sauvegarde [nom]</span><span class="sxs-lookup"><span data-stu-id="a586a-115">backup [noun]</span></span>  
 <span data-ttu-id="a586a-116">Copie de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui peut être utilisée pour restaurer et récupérer les données après une défaillance.</span><span class="sxs-lookup"><span data-stu-id="a586a-116">A copy of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data that can be used to restore and recover the data after a failure.</span></span> <span data-ttu-id="a586a-117">Une sauvegarde des données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est créée au niveau d'une base de données, ou d'un ou de plusieurs de ses fichiers ou groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a586a-117">A backup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data is created at the level of a database or one or more of its files or filegroups.</span></span> <span data-ttu-id="a586a-118">Vous ne pouvez pas créer de sauvegardes au niveau des tables.</span><span class="sxs-lookup"><span data-stu-id="a586a-118">Table-level backups cannot be created.</span></span> <span data-ttu-id="a586a-119">Outre les sauvegardes de données, le mode de récupération complète nécessite la création de sauvegardes du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="a586a-119">In addition to data backups, the full recovery model requires creating backups of the transaction log.</span></span>  
  
 [<span data-ttu-id="a586a-120">mode de récupération</span><span class="sxs-lookup"><span data-stu-id="a586a-120">recovery model</span></span>](recovery-models-sql-server.md)  
 <span data-ttu-id="a586a-121">Propriété de base de données qui contrôle la maintenance du journal des transactions sur une base de données.</span><span class="sxs-lookup"><span data-stu-id="a586a-121">A database property that controls transaction log maintenance on a database.</span></span> <span data-ttu-id="a586a-122">Il existe trois modes de récupération : simple, complète et utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="a586a-122">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="a586a-123">Le mode de récupération de base de données détermine les spécifications de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="a586a-123">The recovery model of database determines its backup and restore requirements.</span></span>  
  
 [<span data-ttu-id="a586a-124">restore</span><span class="sxs-lookup"><span data-stu-id="a586a-124">restore</span></span>](restore-and-recovery-overview-sql-server.md)  
 <span data-ttu-id="a586a-125">Processus à plusieurs phases qui copie toutes les données et les pages des journaux à partir d'une sauvegarde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifiée dans une base de données spécifiée, puis restaure toutes les transactions journalisées dans la sauvegarde en appliquant les modifications journalisées pour rétablir un état ultérieur des données.</span><span class="sxs-lookup"><span data-stu-id="a586a-125">A multi-phase process that copies all the data and log pages from a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to a specified database, and then rolls forward all the transactions that are logged in the backup by applying logged changes to bring the data forward in time.</span></span>  
  
 <span data-ttu-id="a586a-126">**Types de sauvegardes**</span><span class="sxs-lookup"><span data-stu-id="a586a-126">**Types of Backups**</span></span>  
  
 [<span data-ttu-id="a586a-127">Sauvegarde de copie uniquement</span><span class="sxs-lookup"><span data-stu-id="a586a-127">copy-only backup</span></span>](copy-only-backups-sql-server.md)  
 <span data-ttu-id="a586a-128">Sauvegarde d'utilisation particulière qui est indépendante de la séquence normale des sauvegardes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a586a-128">A special-use backup that is independent of the regular sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
 <span data-ttu-id="a586a-129">sauvegarde de données</span><span class="sxs-lookup"><span data-stu-id="a586a-129">data backup</span></span>  
 <span data-ttu-id="a586a-130">Sauvegarde de données dans une base de données complète (sauvegarde de base de données), une base de données partielle (sauvegarde partielle) ou un ensemble de fichiers ou groupes de fichiers (sauvegarde de fichiers).</span><span class="sxs-lookup"><span data-stu-id="a586a-130">A backup of data in a complete database (a database backup), a partial database (a partial backup), or a set of data files or filegroups (a file backup).</span></span>  
  
 [<span data-ttu-id="a586a-131">sauvegarde de base de données</span><span class="sxs-lookup"><span data-stu-id="a586a-131">database backup</span></span>](full-database-backups-sql-server.md)  
 <span data-ttu-id="a586a-132">Sauvegarde d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="a586a-132">A backup of a database.</span></span> <span data-ttu-id="a586a-133">Les sauvegardes complètes de base de données représentent l'intégralité de la base de données à l'issue de l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a586a-133">Full database backups represent the whole database at the time the backup finished.</span></span> <span data-ttu-id="a586a-134">Les sauvegardes différentielles contiennent uniquement les modifications apportées à la base de données depuis sa plus récente sauvegarde complète de base de données.</span><span class="sxs-lookup"><span data-stu-id="a586a-134">Differential database backups contain only changes made to the database since its most recent full database backup.</span></span>  
  
 [<span data-ttu-id="a586a-135">sauvegarde différentielle</span><span class="sxs-lookup"><span data-stu-id="a586a-135">differential backup</span></span>](full-database-backups-sql-server.md)  
 <span data-ttu-id="a586a-136">Sauvegarde de données basée sur la dernière sauvegarde complète d’une base de données complète ou partielle ou d’un ensemble de fichiers de données ou de groupes de fichiers ( *base différentielle*) et qui contient uniquement les extensions de données ayant changé depuis la base différentielle.</span><span class="sxs-lookup"><span data-stu-id="a586a-136">A data backup that is based on the latest full backup of a complete or partial database or a set of data files or filegroups (the *differential base*) and that contains only the data extents that have changed since the differential base.</span></span>  
  
 <span data-ttu-id="a586a-137">Une sauvegarde différentielle partielle n'enregistre que les extensions de données qui ont changé dans les groupes de fichiers depuis la sauvegarde partielle précédente, appelée la base de la sauvegarde différentielle.</span><span class="sxs-lookup"><span data-stu-id="a586a-137">A differential partial backup records only the data extents that have changed in the filegroups since the previous partial backup, known as the base for the differential.</span></span>  
  
 <span data-ttu-id="a586a-138">sauvegarde complète</span><span class="sxs-lookup"><span data-stu-id="a586a-138">full backup</span></span>  
 <span data-ttu-id="a586a-139">Sauvegarde de données qui contient toutes les données d'une base de données particulière ou d'un jeu de groupes de fichiers ou de fichiers, ainsi qu'une partie suffisante du journal pour permettre la récupération de ces données.</span><span class="sxs-lookup"><span data-stu-id="a586a-139">A data backup that contains all the data in a specific database or set of filegroups or files, and also enough log to allow for recovering that data.</span></span>  
  
 [<span data-ttu-id="a586a-140">sauvegarde de fichier journal</span><span class="sxs-lookup"><span data-stu-id="a586a-140">log backup</span></span>](transaction-log-backups-sql-server.md)  
 <span data-ttu-id="a586a-141">Sauvegarde des journaux des transactions qui inclut tous les enregistrements des journaux qui n'ont pas été sauvegardés lors d'une sauvegarde de fichier journal précédente.</span><span class="sxs-lookup"><span data-stu-id="a586a-141">A backup of transaction logs that includes all log records that were not backed up in a previous log backup.</span></span> <span data-ttu-id="a586a-142">(mode de récupération complète)</span><span class="sxs-lookup"><span data-stu-id="a586a-142">(full recovery model)</span></span>  
  
 [<span data-ttu-id="a586a-143">sauvegarde de fichiers</span><span class="sxs-lookup"><span data-stu-id="a586a-143">file backup</span></span>](full-file-backups-sql-server.md)  
 <span data-ttu-id="a586a-144">Sauvegarde d'un ou de plusieurs fichiers ou groupes de fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="a586a-144">A backup of one or more database files or filegroups.</span></span>  
  
 [<span data-ttu-id="a586a-145">sauvegarde partielle</span><span class="sxs-lookup"><span data-stu-id="a586a-145">partial backup</span></span>](partial-backups-sql-server.md)  
 <span data-ttu-id="a586a-146">Contient des données provenant uniquement de certains des groupes de fichiers dans une base de données, y compris les données du groupe de fichiers primaire, de chaque groupe de fichiers en lecture-écriture, ainsi que, éventuellement, de tout fichier spécifié en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="a586a-146">Contains data from only some of the filegroups in a database, including the data in the primary filegroup, every read/write filegroup, and any optionally-specified read-only files.</span></span>  
  
 <span data-ttu-id="a586a-147">**Termes et définitions des supports de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="a586a-147">**Backup Media Terms and Definitions**</span></span>  
  
 [<span data-ttu-id="a586a-148">unité de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a586a-148">backup device</span></span>](backup-devices-sql-server.md)  
 <span data-ttu-id="a586a-149">Unité de disque ou de bande sur laquelle les sauvegardes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont écrites et à partir de laquelle elles peuvent être restaurées.</span><span class="sxs-lookup"><span data-stu-id="a586a-149">A disk or tape device to which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups are written and from which they can be restored.</span></span> <span data-ttu-id="a586a-150">Les sauvegardes SQL Server peuvent également être écrites dans un service de stockage Blob Azure, et le format d’ **URL** est utilisé pour spécifier la destination et le nom du fichier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a586a-150">SQL Server backups can also be written to an Azure Blob storage service, and **URL** format is used to specify the destination and the name of the backup file..</span></span> <span data-ttu-id="a586a-151">Pour plus d’informations, voir [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)(en anglais).</span><span class="sxs-lookup"><span data-stu-id="a586a-151">For more information, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 [<span data-ttu-id="a586a-152">support de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a586a-152">backup media</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="a586a-153">Une ou plusieurs bandes ou un ou plusieurs fichiers disque sur lesquels une ou plusieurs sauvegardes ont été écrites.</span><span class="sxs-lookup"><span data-stu-id="a586a-153">One or more tapes or disk files to which one or more backup have been written.</span></span>  
  
 [<span data-ttu-id="a586a-154">jeu de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a586a-154">backup set</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="a586a-155">Contenu de sauvegarde ajouté à un jeu de supports par une opération de sauvegarde réussie.</span><span class="sxs-lookup"><span data-stu-id="a586a-155">The backup content that is added to a media set by a successful backup operation.</span></span>  
  
 [<span data-ttu-id="a586a-156">famille de supports</span><span class="sxs-lookup"><span data-stu-id="a586a-156">media family</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="a586a-157">Sauvegardes créées sur une seule unité qui n'est pas mise en miroir ou sur un ensemble d'unités en miroir dans un jeu de supports</span><span class="sxs-lookup"><span data-stu-id="a586a-157">Backups created on a single nonmirrored device or a set of mirrored devices in a media set</span></span>  
  
 [<span data-ttu-id="a586a-158">jeu de supports</span><span class="sxs-lookup"><span data-stu-id="a586a-158">media set</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="a586a-159">Ensemble ordonné de supports de sauvegarde (bandes ou fichiers disque) sur lequel une ou plusieurs opérations de sauvegarde ont été écrites en utilisant un type et un nombre fixes d'unités de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="a586a-159">An ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span>  
  
 [<span data-ttu-id="a586a-160">jeu de supports en miroir</span><span class="sxs-lookup"><span data-stu-id="a586a-160">mirrored media set</span></span>](mirrored-backup-media-sets-sql-server.md)  
 <span data-ttu-id="a586a-161">Plusieurs copies (miroirs) d'un jeu de supports.</span><span class="sxs-lookup"><span data-stu-id="a586a-161">Multiple copies (mirrors) of a media set.</span></span>  
  
##  <a name="backup-compression"></a><a name="BackupCompression"></a><span data-ttu-id="a586a-162">Compression de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a586a-162">Backup Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="a586a-163">et les versions ultérieures prennent en charge la compression des sauvegardes. [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et les versions ultérieures peuvent restaurer une sauvegarde compressée.</span><span class="sxs-lookup"><span data-stu-id="a586a-163">and later versions support compressing backups, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions can restore a compressed backup.</span></span> <span data-ttu-id="a586a-164">Pour plus d’informations, consultez [Compression de sauvegardes &#40;SQL Server&#41;](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a586a-164">For more information, see [Backup Compression &#40;SQL Server&#41;](backup-compression-sql-server.md).</span></span>  
  
##  <a name="restrictions-on-backup-operations-in-sql-server"></a><a name="Restrictions"></a><span data-ttu-id="a586a-165">Restrictions sur les opérations de sauvegarde dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="a586a-165">Restrictions on Backup Operations in SQL Server</span></span>  
 <span data-ttu-id="a586a-166">La sauvegarde peut être effectuée si la base de données est en ligne et en cours d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="a586a-166">Backup can occur while the database is online and being used.</span></span> <span data-ttu-id="a586a-167">Cependant, les restrictions suivantes existent.</span><span class="sxs-lookup"><span data-stu-id="a586a-167">However, the following restrictions exist.</span></span>  
  
### <a name="offline-data-cannot-be-backed-up"></a><span data-ttu-id="a586a-168">Il n'est pas possible de sauvegarder les données hors connexion</span><span class="sxs-lookup"><span data-stu-id="a586a-168">Offline Data Cannot Be Backed Up</span></span>  
 <span data-ttu-id="a586a-169">Toute sauvegarde qui fait implicitement ou explicitement référence à des données hors connexion échoue.</span><span class="sxs-lookup"><span data-stu-id="a586a-169">Any backup operation that implicitly or explicitly references data that is offline fails.</span></span> <span data-ttu-id="a586a-170">Voici quelques exemples classiques de cette situation :</span><span class="sxs-lookup"><span data-stu-id="a586a-170">Some typical examples include the following:</span></span>  
  
-   <span data-ttu-id="a586a-171">Vous demandez une sauvegarde complète de la base de données, mais un groupe de fichiers de la base de données est hors connexion.</span><span class="sxs-lookup"><span data-stu-id="a586a-171">You request a full database backup, but one filegroup of the database is offline.</span></span> <span data-ttu-id="a586a-172">Comme tous les groupes de fichiers sont implicitement inclus dans une sauvegarde complète de base de données, cette opération échoue.</span><span class="sxs-lookup"><span data-stu-id="a586a-172">Because all filegroups are implicitly included in a full database backup, this operation fails.</span></span>  
  
     <span data-ttu-id="a586a-173">Pour sauvegarder cette base de données, vous pouvez utiliser une sauvegarde de fichiers et spécifier uniquement les groupes de fichiers en ligne.</span><span class="sxs-lookup"><span data-stu-id="a586a-173">To back up this database, you can use a file backup and specify only the filegroups that are online.</span></span>  
  
-   <span data-ttu-id="a586a-174">Vous demandez une sauvegarde partielle, mais un groupe de fichiers en lecture-écriture est hors connexion.</span><span class="sxs-lookup"><span data-stu-id="a586a-174">You request a partial backup, but a read/write filegroup is offline.</span></span> <span data-ttu-id="a586a-175">Du fait que tous les groupes de fichiers en lecture-écriture sont indispensables pour une sauvegarde partielle, cette opération échoue.</span><span class="sxs-lookup"><span data-stu-id="a586a-175">Because all read/write filegroups are required for a partial backup, the operation fails.</span></span>  
  
-   <span data-ttu-id="a586a-176">Vous demandez une sauvegarde de fichiers spécifiques, mais un fichier n'est pas en ligne.</span><span class="sxs-lookup"><span data-stu-id="a586a-176">You request a file backup of specific files, but one of the files is not online.</span></span> <span data-ttu-id="a586a-177">L'opération échoue.</span><span class="sxs-lookup"><span data-stu-id="a586a-177">The operation fails.</span></span> <span data-ttu-id="a586a-178">Pour sauvegarder les fichiers en ligne, vous pouvez supprimer le fichier hors connexion de la liste des fichiers et recommencer l'opération.</span><span class="sxs-lookup"><span data-stu-id="a586a-178">To back up the online files, you can omit the offline file from the file list and repeat the operation.</span></span>  
  
 <span data-ttu-id="a586a-179">En règle générale, une sauvegarde de journal aboutit même si un ou plusieurs fichiers de données ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="a586a-179">Typically, a log backup succeeds even if one or more data files are unavailable.</span></span> <span data-ttu-id="a586a-180">Cependant, si un fichier contient des modifications journalisées en bloc et effectuées en mode de récupération utilisant les journaux de transactions, tous les fichiers doivent être en ligne pour que la sauvegarde aboutisse.</span><span class="sxs-lookup"><span data-stu-id="a586a-180">However, if any file contains bulk-logged changes made under the bulk-logged recovery model, all the files must be online for the backup to succeed.</span></span>  
  
### <a name="concurrency-restrictions-during-backup"></a><span data-ttu-id="a586a-181">Restrictions d'accès concurrentiel lors d'une sauvegarde</span><span class="sxs-lookup"><span data-stu-id="a586a-181">Concurrency Restrictions During Backup</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a586a-182">recourt à un processus de sauvegarde en ligne pour permettre qu'une base de données soit sauvegardée alors qu'elle est encore utilisée.</span><span class="sxs-lookup"><span data-stu-id="a586a-182">uses an online backup process to allow for a database backup while the database is still being used.</span></span> <span data-ttu-id="a586a-183">Lors d'une sauvegarde, la plupart des opérations sont possibles ; par exemple, les instructions INSERT, UPDATE et DELETE sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="a586a-183">During a backup, most operations are possible; for example, INSERT, UPDATE, or DELETE statements are allowed during a backup operation.</span></span> <span data-ttu-id="a586a-184">Cependant, si vous tentez une opération de sauvegarde pendant qu'un fichier de base de données est en cours de création ou de suppression, l'opération de sauvegarde attend que la création ou la suppression soit terminée ou que le délai d'attente de la sauvegarde expire.</span><span class="sxs-lookup"><span data-stu-id="a586a-184">However, if you try to start a backup operation while a database file is being created or deleted, the backup operation waits until the create or delete operation is finished or the backup times out.</span></span>  
  
 <span data-ttu-id="a586a-185">Parmi les opérations qui ne peuvent pas être effectuées lors d'une sauvegarde de base de données ou d'une sauvegarde du journal des transactions, citons :</span><span class="sxs-lookup"><span data-stu-id="a586a-185">Operations that cannot run during a database backup or transaction log backup include the following:</span></span>  
  
-   <span data-ttu-id="a586a-186">Les opérations de gestion des fichiers telles que l'instruction ALTER DATABASE employées avec l'option ADD FILE ou REMOVE FILE.</span><span class="sxs-lookup"><span data-stu-id="a586a-186">File-management operations such as the ALTER DATABASE statement with either the ADD FILE or REMOVE FILE options.</span></span>  
  
-   <span data-ttu-id="a586a-187">Les opérations de compactage de base de données ou de fichier.</span><span class="sxs-lookup"><span data-stu-id="a586a-187">Shrink database or shrink file operations.</span></span> <span data-ttu-id="a586a-188">Cela comprend également les opérations de compactage automatique.</span><span class="sxs-lookup"><span data-stu-id="a586a-188">This includes auto-shrink operations.</span></span>  
  
-   <span data-ttu-id="a586a-189">Si vous tentez de créer ou de supprimer un fichier de base de données pendant qu'une opération de sauvegarde est en cours, la création ou la suppression échoue.</span><span class="sxs-lookup"><span data-stu-id="a586a-189">If you try to create or delete a database file while a backup operation is in progress, the create or delete operation fails.</span></span>  
  
 <span data-ttu-id="a586a-190">Si une opération de sauvegarde chevauche une opération de compactage ou de gestion des fichiers, un conflit se produit.</span><span class="sxs-lookup"><span data-stu-id="a586a-190">If a backup operation overlaps with a file-management operation or shrink operation, a conflict occurs.</span></span> <span data-ttu-id="a586a-191">Quelle que soit l'opération effectuée la première, la seconde opération attend que le verrou défini par la première opération expire. (Le délai d'expiration est contrôlé par un paramètre d'expiration de la session). Si le verrou est libéré au cours du délai d'expiration, la seconde opération se poursuit.</span><span class="sxs-lookup"><span data-stu-id="a586a-191">Regardless of which of the conflicting operation began first, the second operation waits for the lock set by the first operation to time out. (The time-out period is controlled by a session time-out setting.) If the lock is released during the time-out period, the second operation continues.</span></span> <span data-ttu-id="a586a-192">Si le verrou expire, la seconde opération échoue.</span><span class="sxs-lookup"><span data-stu-id="a586a-192">If the lock times out, the second operation fails.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a586a-193">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a586a-193">Related Tasks</span></span>  
 <span data-ttu-id="a586a-194">**Pour utiliser des unités et supports de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="a586a-194">**To work with backup devices and backup media**</span></span>  
  
-   [<span data-ttu-id="a586a-195">Définir une unité de sauvegarde logique pour un fichier de disque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-195">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="a586a-196">Définir une unité de sauvegarde logique pour un lecteur de bande &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-196">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="a586a-197">Spécifier un disque ou une bande comme destination de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-197">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="a586a-198">Supprimer une unité de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-198">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="a586a-199">Définir la date d’expiration d’une sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-199">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="a586a-200">Afficher le contenu d’un fichier ou d’une bande de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-200">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="a586a-201">Afficher les fichiers de données et les fichiers journaux dans un jeu de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-201">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="a586a-202">Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-202">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="a586a-203">Restaurer une sauvegarde à partir d’une unité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-203">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
-   [<span data-ttu-id="a586a-204">Tutoriel : Sauvegarde et restauration SQL Server avec le service Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="a586a-204">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
 <span data-ttu-id="a586a-205">**Pour créer une sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="a586a-205">**To create a backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a586a-206">Pour réaliser des sauvegardes partielles ou de copie uniquement, vous devez utiliser l’instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] [BACKUP](/sql/t-sql/statements/backup-transact-sql) avec l’option PARTIAL ou COPY_ONLY, respectivement.</span><span class="sxs-lookup"><span data-stu-id="a586a-206">For partial or copy-only backups, you must use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement with the PARTIAL or COPY_ONLY option, respectively.</span></span>  
  
-   [<span data-ttu-id="a586a-207">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-207">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="a586a-208">Sauvegarder un journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-208">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="a586a-209">Sauvegarder des fichiers et des groupes de fichiers &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-209">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="a586a-210">Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-210">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="a586a-211">Sauvegarder le journal des transactions lorsque la base de données est endommagée &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-211">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
-   [<span data-ttu-id="a586a-212">Activer ou désactiver des sommes de contrôle de sauvegarde au cours d’opérations de sauvegarde ou de restauration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-212">Enable or Disable Backup Checksums During Backup or Restore &#40;SQL Server&#41;</span></span>](enable-or-disable-backup-checksums-during-backup-or-restore-sql-server.md)  
  
-   [<span data-ttu-id="a586a-213">Spécifier si une opération de sauvegarde ou de restauration continue ou s’arrête après la survenue d’une erreur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-213">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
-   [<span data-ttu-id="a586a-214">Utiliser Resource Governor pour limiter l’utilisation de l’UC par compression de la sauvegarde &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-214">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="a586a-215">Tutoriel : Sauvegarde et restauration SQL Server avec le service Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="a586a-215">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="a586a-216">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a586a-216">See Also</span></span>  
 <span data-ttu-id="a586a-217">[Sauvegarde et restauration des bases de données SQL Server](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="a586a-217">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="a586a-218">[Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a586a-218">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="a586a-219">[Plans de maintenance](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="a586a-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 <span data-ttu-id="a586a-220">[Journal des transactions &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a586a-220">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="a586a-221">Modes de récupération &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a586a-221">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
