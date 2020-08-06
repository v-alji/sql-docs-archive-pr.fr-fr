---
title: Afficher la taille du fichier partiellement alloué d’un instantané de base de données (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- snapshots [SQL Server database snapshots], sparse files
- space [SQL Server], sparse files
- sparse files [SQL Server]
- size [SQL Server], sparse files
- maximum sparse file size
- database snapshots [SQL Server], sparse files
- space [SQL Server], database snapshots
ms.assetid: 1867c5f8-d57c-46d3-933d-3642ab0a8e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: 424399b9915c8e7e26e1076fd2e553aafe06fcf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704143"
---
# <a name="view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql"></a><span data-ttu-id="9d092-102">Afficher la taille du fichier partiellement alloué d'un instantané de base de données (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9d092-102">View the Size of the Sparse File of a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="9d092-103">Cette rubrique explique comment utiliser [!INCLUDE[tsql](../../includes/tsql-md.md)] pour vérifier qu'un fichier de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est un fichier partiellement alloué et pour déterminer ses tailles réelle et maximale.</span><span class="sxs-lookup"><span data-stu-id="9d092-103">This topic describes how to use [!INCLUDE[tsql](../../includes/tsql-md.md)] to verify that a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database file is a sparse file and to find out its actual and maximum sizes.</span></span> <span data-ttu-id="9d092-104">Les fichiers partiellement alloués, qui sont une fonctionnalité du système de fichiers NTFS, sont utilisés par les instantanés de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d092-104">Sparse files, which are a feature of the NTFS file system, are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshots.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9d092-105">Pendant la création d'un instantané de base de données, ces fichiers partiellement alloués sont créés et nommés par l'instruction CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="9d092-105">During database snapshot creation, sparse files are created by using the file names in the CREATE DATABASE statement.</span></span> <span data-ttu-id="9d092-106">Ces noms de fichiers sont stockés dans **sys.master_files** dans la colonne **physical_name** .</span><span class="sxs-lookup"><span data-stu-id="9d092-106">These file names are stored in **sys.master_files** in the **physical_name** column.</span></span> <span data-ttu-id="9d092-107">Dans **sys.database_files** (dans la base de données source ou dans l’instantané), la colonne **physical_name** contient toujours les noms des fichiers de la base de données source.</span><span class="sxs-lookup"><span data-stu-id="9d092-107">In **sys.database_files** (whether in the source database or in a snapshot), the **physical_name** column always contains the names of the source database files.</span></span>  
  
## <a name="verify-that-a-database-file-is-a-sparse-file"></a><span data-ttu-id="9d092-108">Vérifier qu'un fichier de base de données est un fichier partiellement alloué</span><span class="sxs-lookup"><span data-stu-id="9d092-108">Verify that a Database File is a Sparse File</span></span>  
  
1.  <span data-ttu-id="9d092-109">Sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9d092-109">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="9d092-110">Sélectionnez la colonne **is_sparse** soit dans **sys.database_files** dans l’instantané de la base de données, soit dans **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="9d092-110">Select the **is_sparse** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="9d092-111">La valeur indique si le fichier est un fichier partiellement alloué, comme suit :</span><span class="sxs-lookup"><span data-stu-id="9d092-111">The value indicates whether the file is a sparse file, as follows:</span></span>  
  
     <span data-ttu-id="9d092-112">1 = le fichier est un fichier partiellement alloué.</span><span class="sxs-lookup"><span data-stu-id="9d092-112">1 = File is a sparse file.</span></span>  
  
     <span data-ttu-id="9d092-113">0 = le fichier n'est pas un fichier partiellement alloué.</span><span class="sxs-lookup"><span data-stu-id="9d092-113">0 = File is not a sparse file.</span></span>  
  
## <a name="find-out-the-actual-size-of-a-sparse-file"></a><span data-ttu-id="9d092-114">Pour connaître la taille réelle d'un fichier partiellement alloué</span><span class="sxs-lookup"><span data-stu-id="9d092-114">Find Out the Actual Size of a Sparse File</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9d092-115">La taille d’un fichier partiellement alloué augmente par incréments de 64 kilo-octets (Ko). Il s’agit donc toujours d’un multiple de 64 Ko.</span><span class="sxs-lookup"><span data-stu-id="9d092-115">Sparse files grow in 64-kilobyte (KB) increments; thus, the size of a sparse file on disk is always a multiple of 64 KB.</span></span>  
  
 <span data-ttu-id="9d092-116">Pour afficher le nombre d’octets actuellement utilisé sur le disque par chaque fichier partiellement alloué d’un instantané, interrogez la colonne **size_on_disk_bytes** de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vue de gestion dynamique [sys. dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="9d092-116">To view the number of bytes that each sparse file of a snapshot is currently using on disk, query the **size_on_disk_bytes** column of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][sys.dm_io_virtual_file_stats](/sql/relational-databases/system-dynamic-management-views/sys-dm-io-virtual-file-stats-transact-sql) dynamic management view.</span></span>  
  
 <span data-ttu-id="9d092-117">Pour afficher l’espace disque occupé par un fichier partiellement alloué, cliquez avec le bouton droit sur le fichier dans Microsoft Windows, cliquez sur **Propriétés**et notez la valeur indiquée dans **Taille sur le disque** .</span><span class="sxs-lookup"><span data-stu-id="9d092-117">To view the disk space used by a sparse file, right-click the file in Microsoft Windows, click **Properties**, and look at the **Size on disk** value.</span></span>  
  
## <a name="find-out-the-maximum-size-of-a-sparse-file"></a><span data-ttu-id="9d092-118">Pour connaître la taille maximale d'un fichier partiellement alloué</span><span class="sxs-lookup"><span data-stu-id="9d092-118">Find Out the Maximum Size of a Sparse File</span></span>  
 <span data-ttu-id="9d092-119">La taille maximale d'un fichier partiellement alloué correspond à la taille du fichier de la base de données source au moment de la création de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="9d092-119">The maximum size to which a sparse can grow is the size of the corresponding source database file at the time of the snapshot creation.</span></span> <span data-ttu-id="9d092-120">Pour connaître la taille de ce fichier, utilisez une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d092-120">To learn this size, you can use one of the following alternatives:</span></span>  
  
-   <span data-ttu-id="9d092-121">Utilisation de l'invite de commandes Windows :</span><span class="sxs-lookup"><span data-stu-id="9d092-121">Using Windows Command Prompt:</span></span>  
  
    1.  <span data-ttu-id="9d092-122">Utilisez les commandes **dir** de Windows.</span><span class="sxs-lookup"><span data-stu-id="9d092-122">Use Windows **dir** commands.</span></span>  
  
    2.  <span data-ttu-id="9d092-123">Sélectionnez le fichier partiellement alloué, ouvrez la boîte de dialogue **Propriétés** dans Windows et relevez la valeur du champ **Taille** .</span><span class="sxs-lookup"><span data-stu-id="9d092-123">Select the sparse file, open the file **Properties** dialog box in Windows, and look at the **Size** value.</span></span>  
  
-   <span data-ttu-id="9d092-124">Sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9d092-124">On the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
     <span data-ttu-id="9d092-125">Sélectionnez la colonne **size** soit dans **sys.database_files** dans l’instantané de la base de données, soit dans **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="9d092-125">Select the **size** column from either **sys.database_files** in the database snapshot or from **sys.master_files**.</span></span> <span data-ttu-id="9d092-126">La valeur de la colonne **size** reflète l'espace maximal que l'instantané peut utiliser en pages SQL. Cette valeur correspond à celle du champ **Taille** de Windows, sauf qu'elle est exprimée en termes de nombre de pages SQL dans le fichier ; la taille en octets étant :</span><span class="sxs-lookup"><span data-stu-id="9d092-126">The value of **size** column reflects the maximum space, in SQL pages, that the snapshot can ever use; this value is equivalent to the Windows **Size** field, except that it is represented in terms of the number of SQL pages in the file; the size in bytes is:</span></span>  
  
     <span data-ttu-id="9d092-127">( *nombre_de_pages* \* 8192)</span><span class="sxs-lookup"><span data-stu-id="9d092-127">( *number_of_pages* \* 8192)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d092-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d092-128">See Also</span></span>  
 <span data-ttu-id="9d092-129">[Instantanés de base de données &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9d092-129">[Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md) </span></span>  
 <span data-ttu-id="9d092-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d092-130">[sys.fn_virtualfilestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-virtualfilestats-transact-sql) </span></span>  
 <span data-ttu-id="9d092-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d092-131">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 [<span data-ttu-id="9d092-132">sys.master_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d092-132">sys.master_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)  
  
  
