---
title: Supprimer un instantané de base de données (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- removing database snapshots
- deleting database snapshots
- database snapshots [SQL Server], deleting
ms.assetid: ad70ec97-d5fb-41aa-b72a-915e74b61b76
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0d9d912a092e581fad7d3d53504309f63ba1806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600067"
---
# <a name="drop-a-database-snapshot-transact-sql"></a><span data-ttu-id="0d401-102">supprimer un instantané de base de données (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0d401-102">Drop a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="0d401-103">La suppression d'un instantané de base de données entraîne la suppression de l'instantané de base de données dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ainsi que celle des fichiers partiellement alloués utilisés par l'instantané.</span><span class="sxs-lookup"><span data-stu-id="0d401-103">Dropping a database snapshot deletes the database snapshot from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and deletes the sparse files that are used by the snapshot.</span></span> <span data-ttu-id="0d401-104">Lorsque vous supprimez un instantané de base de données, toutes ses connexions utilisateur sont terminées.</span><span class="sxs-lookup"><span data-stu-id="0d401-104">When you drop a database snapshot, all user connections to it are terminated.</span></span>  
  
## <a name="security"></a><span data-ttu-id="0d401-105">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0d401-105">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0d401-106">Autorisations</span><span class="sxs-lookup"><span data-stu-id="0d401-106">Permissions</span></span>  
 <span data-ttu-id="0d401-107">Tout utilisateur doté des autorisations DROP DATABASE peut supprimer un instantané de base de données.</span><span class="sxs-lookup"><span data-stu-id="0d401-107">Any user with DROP DATABASE permissions can drop a database snapshot.</span></span>  
  
##  <a name="how-to-drop-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0d401-108">Procédure de suppresssion d'un instantané de base de données (à l'aide de Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0d401-108">How to Drop a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="0d401-109">**Pour supprimer un instantané de base de données**</span><span class="sxs-lookup"><span data-stu-id="0d401-109">**To drop a database snapshot**</span></span>  
  
1.  <span data-ttu-id="0d401-110">Identifiez l'instantané à supprimer.</span><span class="sxs-lookup"><span data-stu-id="0d401-110">Identify the database snapshot that you want to drop.</span></span> <span data-ttu-id="0d401-111">Vous pouvez afficher les instantanés d'une base de données dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d401-111">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0d401-112">Pour plus d’informations, consultez [Afficher un instantané de base de données &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0d401-112">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="0d401-113">Exécutez l’instruction [DROP DATABASE](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) en définissant le nom de l’instantané de base de données à supprimer.</span><span class="sxs-lookup"><span data-stu-id="0d401-113">Issue a [DROP DATABASE](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) statement, specifying the name of the database snapshot to be dropped.</span></span> <span data-ttu-id="0d401-114">La syntaxe est la suivante :</span><span class="sxs-lookup"><span data-stu-id="0d401-114">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="0d401-115">DROP DATABASE *nom_instantané_base_de_données* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="0d401-115">DROP DATABASE *database_snapshot_name* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="0d401-116">où *nom_instantané_base_de_données* est le nom de l’instantané de base de données à supprimer.</span><span class="sxs-lookup"><span data-stu-id="0d401-116">Where *database_snapshot_name* is the name of the database snapshot to be dropped.</span></span>  
  
####  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="0d401-117">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0d401-117">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="0d401-118">L'exemple suivant supprime un instantané de base de données nommé SalesSnapshot0600 sans affecter la base de données source.</span><span class="sxs-lookup"><span data-stu-id="0d401-118">This example drops a database snapshot named SalesSnapshot0600, without affecting the source database.</span></span>  
  
```  
DROP DATABASE SalesSnapshot0600 ;  
```  
  
 <span data-ttu-id="0d401-119">Les connexions utilisateur à SalesSnapshot0600 sont terminées, et tous les fichiers physiques partiellement alloués du système de fichiers NTFS utilisés par l'instantané sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="0d401-119">Any user connections to SalesSnapshot0600 are terminated, and all of the NTFS file system sparse files used by the snapshot are deleted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d401-120">Pour plus d’informations sur l’utilisation des fichiers partiellement alloués par les instantanés de base de données, consultez [Instantanés de base de données &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0d401-120">For information about the use of sparse files by database snapshots, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0d401-121">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="0d401-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="0d401-122">Créer un instantané de base de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0d401-122">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="0d401-123">Afficher un instantané de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0d401-123">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="0d401-124">Rétablir une base de données dans l’état d’un instantané de base de données</span><span class="sxs-lookup"><span data-stu-id="0d401-124">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="0d401-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d401-125">See Also</span></span>  
 <span data-ttu-id="0d401-126">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0d401-126">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 [<span data-ttu-id="0d401-127">Instantanés de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0d401-127">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
