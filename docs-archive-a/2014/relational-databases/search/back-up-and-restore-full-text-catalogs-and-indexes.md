---
title: Sauvegarder et restaurer des catalogues et des index de recherche en texte intégrals | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], backing up
- full-text search [SQL Server], back up and restore
- recovery [full-text search]
- backups [SQL Server], full-text indexes
- full-text indexes [SQL Server], restoring
- restore operations [full-text search]
ms.assetid: 6a4080d9-e43f-4b7b-a1da-bebf654c1194
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c0df49c03325da375427c6566799f374fcc9dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613400"
---
# <a name="back-up-and-restore-full-text-catalogs-and-indexes"></a><span data-ttu-id="29bdb-102">Sauvegarder et restaurer des catalogues et des index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="29bdb-102">Back Up and Restore Full-Text Catalogs and Indexes</span></span>
  <span data-ttu-id="29bdb-103">Cette rubrique explique comment sauvegarder et des index de recherche en texte intégral créés dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29bdb-103">This topic explains how to back up and restore full-text indexes created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="29bdb-104">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le catalogue de texte intégral est un concept logique qui ne réside pas dans un groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="29bdb-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the full-text catalog is a logical concept and does not reside in a filegroup.</span></span> <span data-ttu-id="29bdb-105">Par conséquent, pour sauvegarder un catalogue de texte intégral dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous devez identifier tous les groupes de fichiers contenant un index de recherche en texte intégral qui appartiennent au catalogue.</span><span class="sxs-lookup"><span data-stu-id="29bdb-105">Therefore, to back up a full-text catalog in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must identify every filegroup that contains a full-text index that belongs to the catalog.</span></span> <span data-ttu-id="29bdb-106">Vous devez ensuite enregistrer ces groupes de fichiers, un par un.</span><span class="sxs-lookup"><span data-stu-id="29bdb-106">Then you must back up those filegroups, one by one.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="29bdb-107">Il est possible d'importer des catalogues de texte intégral lors de la mise à niveau d'une base de données [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29bdb-107">It is possible to import full-text catalogs when upgrading a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database.</span></span> <span data-ttu-id="29bdb-108">Chaque catalogue de texte intégral importé est un fichier de base de données dans son propre groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="29bdb-108">Each imported full-text catalog is a database file in its own filegroup.</span></span> <span data-ttu-id="29bdb-109">Pour sauvegarder un catalogue importé, sauvegardez simplement son groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="29bdb-109">To back up an imported catalog, simply back up its filegroup.</span></span> <span data-ttu-id="29bdb-110">Pour plus d’informations, consultez [Sauvegarde et restauration de catalogues de texte intégral](https://go.microsoft.com/fwlink/?LinkID=121052)dans la documentation en ligne de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29bdb-110">For more information, see [Backing Up and Restoring Full-Text Catalogs](https://go.microsoft.com/fwlink/?LinkID=121052), in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Books Online.</span></span>  
  
##  <a name="backing-up-the-full-text-indexes-of-a-full-text-catalog"></a><a name="backingup"></a> <span data-ttu-id="29bdb-111">Sauvegarde des index de recherche en texte intégral d'un catalogue de texte intégral</span><span class="sxs-lookup"><span data-stu-id="29bdb-111">Backing Up the Full-Text Indexes of a Full-Text Catalog</span></span>  
  
###  <a name="finding-the-full-text-indexes-of-a-full-text-catalog"></a><a name="Find_FTIs_of_a_Catalog"></a> <span data-ttu-id="29bdb-112">Recherche des index de recherche en texte intégral d'un catalogue de texte intégral</span><span class="sxs-lookup"><span data-stu-id="29bdb-112">Finding the Full-Text Indexes of a Full-Text Catalog</span></span>  
 <span data-ttu-id="29bdb-113">Vous pouvez extraire les propriétés des index de recherche en texte intégral en utilisant l’instruction [SELECT](/sql/t-sql/queries/select-transact-sql) suivante, qui sélectionne des colonnes à partir des affichages catalogue [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) et [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="29bdb-113">You can retrieve the properties of the full-text indexes by using the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement, which selects columns from the [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) and [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) catalog views.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @TableID int;  
SET @TableID = (SELECT OBJECT_ID('AdventureWorks2012.Production.Product'));  
SELECT object_name(@TableID), i.is_enabled, i.change_tracking_state,   
   i.has_crawl_completed, i.crawl_type, c.name as fulltext_catalog_name   
   FROM sys.fulltext_indexes i, sys.fulltext_catalogs c   
   WHERE i.fulltext_catalog_id = c.fulltext_catalog_id;  
GO  
```  
  

  
###  <a name="finding-the-filegroup-or-file-that-contains-a-full-text-index"></a><a name="Find_FG_of_FTI"></a> <span data-ttu-id="29bdb-114">Recherche du groupe de fichiers ou du fichier qui contient un index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="29bdb-114">Finding the Filegroup or File That Contains a Full-Text Index</span></span>  
 <span data-ttu-id="29bdb-115">Lorsqu'un index de recherche en texte intégral est créé, il est placé à l'un des emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="29bdb-115">When a full-text index is created, it is placed in one of the following locations:</span></span>  
  
-   <span data-ttu-id="29bdb-116">Groupe de fichiers spécifié par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="29bdb-116">A user-specified filegroup.</span></span>  
  
-   <span data-ttu-id="29bdb-117">Le même groupe de fichiers que la table de base ou la vue pour une table non partitionnée.</span><span class="sxs-lookup"><span data-stu-id="29bdb-117">The same filegroup as base table or view, for a nonpartitioned table.</span></span>  
  
-   <span data-ttu-id="29bdb-118">Le groupe de fichiers primaire, pour une table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="29bdb-118">The primary filegroup, for a partitioned table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29bdb-119">Pour plus d’informations sur la création d’un index de texte intégral, consultez [Créer et gérer des index de recherche en texte intégral](create-and-manage-full-text-indexes.md) et [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="29bdb-119">For information about creating a full-text index, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) and [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="29bdb-120">Pour rechercher le groupe de fichiers de l’index de recherche en texte intégral sur une table ou une vue, utilisez la requête ci-dessous, où *nom_objet* est le nom de la table ou de la vue :</span><span class="sxs-lookup"><span data-stu-id="29bdb-120">To find the filegroup of full-text index on a table or view, use the following query, where *object_name* is the name of the table or view:</span></span>  
  
```  
SELECT name FROM sys.filegroups f, sys.fulltext_indexes i   
   WHERE f.data_space_id = i.data_space_id   
      and i.object_id = object_id('object_name');  
GO  
  
```  
  

  
###  <a name="backing-up-the-filegroups-that-contain-full-text-indexes"></a><a name="Back_up_FTIs_of_FTC"></a> <span data-ttu-id="29bdb-121">Sauvegarde des groupes de fichiers qui contiennent des index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="29bdb-121">Backing Up the Filegroups That Contain Full-Text Indexes</span></span>  
 <span data-ttu-id="29bdb-122">Après avoir recherché les groupes de fichiers qui contiennent les index d'un catalogue de texte intégral, vous devez sauvegarder chacun des groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="29bdb-122">After you find the filegroups that contain the indexes of a full-text catalog, you need back up each of the filegroups.</span></span> <span data-ttu-id="29bdb-123">Durant le processus de sauvegarde, il est impossible de supprimer ou d'ajouter des catalogues de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="29bdb-123">During the backup process, full-text catalogs may not be dropped or added.</span></span>  
  
 <span data-ttu-id="29bdb-124">La première sauvegarde d'un groupe de fichiers doit être une sauvegarde de fichiers complète.</span><span class="sxs-lookup"><span data-stu-id="29bdb-124">The first backup of a filegroup must be a full file backup.</span></span> <span data-ttu-id="29bdb-125">Après avoir créé une sauvegarde complète d'un fichier ou d'un groupe de fichiers, vous pouvez créer une série d'une ou de plusieurs sauvegardes de fichiers différentielles basées sur cette sauvegarde de fichiers complète.</span><span class="sxs-lookup"><span data-stu-id="29bdb-125">After you have created a full file backup for a filegroup, you could back up only the changes in a filegroup by creating a series of one or more differential file backups that are based on the full file backup.</span></span>  
  
 <span data-ttu-id="29bdb-126">**Pour sauvegarder les fichiers et groupes de fichiers**</span><span class="sxs-lookup"><span data-stu-id="29bdb-126">**To back up files and filegroups**</span></span>  
  
-   [<span data-ttu-id="29bdb-127">Sauvegarder des fichiers et des groupes de fichiers &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="29bdb-127">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="29bdb-128">BACKUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="29bdb-128">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  

  
##  <a name="restoring-a-full-text-index"></a><a name="Restore_FTI"></a> <span data-ttu-id="29bdb-129">Restauration d'un index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="29bdb-129">Restoring a Full-Text Index</span></span>  
 <span data-ttu-id="29bdb-130">La restauration d'un groupe de fichiers sauvegardés restaure les fichiers de l'index de recherche en texte intégral, ainsi que les autres fichiers dans le groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="29bdb-130">Restoring a backed-up filegroup restores the full-text index files, as well as the other files in the filegroup.</span></span> <span data-ttu-id="29bdb-131">Par défaut, le groupe de fichiers est restauré à l'emplacement du disque sur lequel le groupe de fichiers a été sauvegardé.</span><span class="sxs-lookup"><span data-stu-id="29bdb-131">By default, the filegroup is restored to the disk location on which the filegroup was backed up.</span></span>  
  
 <span data-ttu-id="29bdb-132">Si une table indexée de texte intégral était en ligne et qu'un remplissage s'exécutait lorsque la sauvegarde a été créée, le remplissage reprend après la restauration.</span><span class="sxs-lookup"><span data-stu-id="29bdb-132">If a full-text indexed table was online and a population was running when the backup was created, the population is resumed after the restore.</span></span>  
  
 <span data-ttu-id="29bdb-133">**Pour restaurer un groupe de fichiers**</span><span class="sxs-lookup"><span data-stu-id="29bdb-133">**To restore a filegroup**</span></span>  
  
-   [<span data-ttu-id="29bdb-134">Restaurer des fichiers et des groupes de fichiers &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="29bdb-134">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="29bdb-135">Restaurer des fichiers et groupes de fichiers en remplaçant des fichiers existants &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="29bdb-135">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="29bdb-136">Restaurer des fichiers à un nouvel emplacement &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="29bdb-136">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="29bdb-137">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="29bdb-137">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  

  
## <a name="see-also"></a><span data-ttu-id="29bdb-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29bdb-138">See Also</span></span>  
 <span data-ttu-id="29bdb-139">[Gérer et surveiller la recherche en texte intégral pour une instance de serveur](manage-and-monitor-full-text-search-for-a-server-instance.md) </span><span class="sxs-lookup"><span data-stu-id="29bdb-139">[Manage and Monitor Full-Text Search for a Server Instance](manage-and-monitor-full-text-search-for-a-server-instance.md) </span></span>  
 [<span data-ttu-id="29bdb-140">Mise à niveau de la fonction de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="29bdb-140">Upgrade Full-Text Search</span></span>](upgrade-full-text-search.md)  
  
  
