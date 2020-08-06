---
title: Propriétés de la base de données (page Groupes de fichiers) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.filegroups.f1
ms.assetid: 8d06e859-73dd-4019-b6e8-99c5c5297697
author: stevestein
ms.author: sstein
ms.openlocfilehash: d0546a17491ed5d3b36890a605c5faa922c24fe6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604550"
---
# <a name="database-properties-filegroups-page"></a><span data-ttu-id="b1aa3-102">Propriétés de la base de données (page Groupes de fichiers)</span><span class="sxs-lookup"><span data-stu-id="b1aa3-102">Database Properties (Filegroups Page)</span></span>
  <span data-ttu-id="b1aa3-103">Cette page vous permet d'afficher les groupes de fichiers existants ou d'ajouter un nouveau groupe de fichiers à la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-103">Use this page to view the filegroups or add a new filegroup to the selected database.</span></span> <span data-ttu-id="b1aa3-104">Il existe trois types de groupes de fichiers : les groupes de fichiers de *ligne* , les groupes de fichiers de données FILESTREAM et les groupes de fichiers optimisés en mémoire.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-104">Filegroup types are separated into *row* filegroups, FILESTREAM data, and memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="b1aa3-105">Les groupes de fichiers de ligne contiennent des données régulières et des fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-105">Row filegroups contain regular data and log files.</span></span> <span data-ttu-id="b1aa3-106">Les groupes de fichiers de données FILESTREAM contiennent des fichiers de données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-106">FILESTREAM data filegroups contain FILESTREAM data files.</span></span> <span data-ttu-id="b1aa3-107">Ces fichiers de données comportent des informations sur la manière dont les données des objets BLOB (Binary Large Objects) sont stockées sur le système de fichiers lorsque vous utilisez le stockage FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-107">These data files store information about how binary large object (BLOB) data is stored on the file system when you are using FILESTREAM storage.</span></span> <span data-ttu-id="b1aa3-108">Les deux types de groupes de fichiers disposent des mêmes options.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-108">The options are the same for both types of filegroups.</span></span>  
  
 <span data-ttu-id="b1aa3-109">Si FILESTREAM n'est pas activé, la section **Filestream** ne sera pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-109">If FILESTREAM is not enabled, the **Filestream** section will not be available.</span></span> <span data-ttu-id="b1aa3-110">Vous pouvez activer le stockage FILESTREAM dans la boîte de dialogue [Propriétés du serveur (page Avancé)](../../database-engine/configure-windows/server-properties-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="b1aa3-110">You can enable FILESTREAM storage by using [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md).</span></span>  
  
 <span data-ttu-id="b1aa3-111">Pour plus d’informations sur la manière dont [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise les groupes de fichiers de ligne, consultez [Groupes de fichiers et fichiers de base de données](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="b1aa3-111">For information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses row filegroups, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span> <span data-ttu-id="b1aa3-112">Pour plus d’informations sur les données et groupes de fichiers FILESTREAM, consultez [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b1aa3-112">For more information about FILESTREAM data and filegroups, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="b1aa3-113">Les groupes de fichiers optimisés en mémoire sont nécessaires pour toute base de données devant contenir une ou plusieurs tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-113">Memory-optimized file groups are required for a database to contain one or more memory-optimized tables.</span></span>  
  
## <a name="row-and-filestream-data-filegroup-options"></a><span data-ttu-id="b1aa3-114">Options des groupes de fichiers de ligne et de données FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="b1aa3-114">Row and FILESTREAM Data Filegroup Options</span></span>  
 <span data-ttu-id="b1aa3-115">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b1aa3-115">**Name**</span></span>  
 <span data-ttu-id="b1aa3-116">Entrez le nom du groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-116">Enter the name of the filegroup.</span></span>  
  
 <span data-ttu-id="b1aa3-117">**Fichiers**</span><span class="sxs-lookup"><span data-stu-id="b1aa3-117">**Files**</span></span>  
 <span data-ttu-id="b1aa3-118">Indique le nombre de fichiers contenus dans le groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-118">Displays the count of files in the filegroup.</span></span>  
  
 <span data-ttu-id="b1aa3-119">**Lecture seule**</span><span class="sxs-lookup"><span data-stu-id="b1aa3-119">**Read-only**</span></span>  
 <span data-ttu-id="b1aa3-120">Sélectionnez cette option pour attribuer au groupe de fichiers l'état lecture seule.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-120">Select to set the filegroup to a read-only status.</span></span>  
  
 <span data-ttu-id="b1aa3-121">**Par défaut**</span><span class="sxs-lookup"><span data-stu-id="b1aa3-121">**Default**</span></span>  
 <span data-ttu-id="b1aa3-122">Sélectionnez cette option pour définir ce groupe de fichiers comme groupe de fichiers par défaut.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-122">Select to make this filegroup the default filegroup.</span></span> <span data-ttu-id="b1aa3-123">Vous pouvez définir un groupe de fichiers de ligne par défaut et un groupe de fichiers par défaut pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-123">You can have one default filegroup for rows and one default filegroup for FILESTREAM data.</span></span>  
  
 <span data-ttu-id="b1aa3-124">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="b1aa3-124">**Add**</span></span>  
 <span data-ttu-id="b1aa3-125">Ajoute une nouvelle ligne vide dans la grille qui répertorie les groupes de fichiers associés à la base de données.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-125">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="b1aa3-126">**Remove**</span><span class="sxs-lookup"><span data-stu-id="b1aa3-126">**Remove**</span></span>  
 <span data-ttu-id="b1aa3-127">Supprime la ligne sélectionnée des groupes de fichiers de la grille.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-127">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="memory-optimized-data-filegroup-options"></a><span data-ttu-id="b1aa3-128">Options des groupes de fichiers optimisés en mémoire</span><span class="sxs-lookup"><span data-stu-id="b1aa3-128">Memory-Optimized Data Filegroup Options</span></span>  
 <span data-ttu-id="b1aa3-129">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b1aa3-129">**Name**</span></span>  
 <span data-ttu-id="b1aa3-130">Entrez le nom du groupe de fichiers optimisé en mémoire.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-130">Enter the name of the memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="b1aa3-131">**Fichiers FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="b1aa3-131">**Filestream Files**</span></span>  
 <span data-ttu-id="b1aa3-132">Affiche le nombre de fichiers (conteneurs) figurant dans le groupe de fichiers de données optimisé en mémoire.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-132">Displays the number of files (containers) in the memory-optimized data filegroup.</span></span> <span data-ttu-id="b1aa3-133">Vous pouvez ajouter des conteneurs sur la page **Fichiers** .</span><span class="sxs-lookup"><span data-stu-id="b1aa3-133">You can add containers in the **Files** page.</span></span>  
  
 <span data-ttu-id="b1aa3-134">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="b1aa3-134">**Add**</span></span>  
 <span data-ttu-id="b1aa3-135">Ajoute une nouvelle ligne vide dans la grille qui répertorie les groupes de fichiers associés à la base de données.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-135">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="b1aa3-136">**Remove**</span><span class="sxs-lookup"><span data-stu-id="b1aa3-136">**Remove**</span></span>  
 <span data-ttu-id="b1aa3-137">Supprime la ligne sélectionnée des groupes de fichiers de la grille.</span><span class="sxs-lookup"><span data-stu-id="b1aa3-137">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1aa3-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1aa3-138">See Also</span></span>  
 <span data-ttu-id="b1aa3-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1aa3-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="b1aa3-140">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b1aa3-140">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
