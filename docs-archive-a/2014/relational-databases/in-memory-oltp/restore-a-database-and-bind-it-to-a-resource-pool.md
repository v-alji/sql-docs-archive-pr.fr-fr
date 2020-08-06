---
title: Restaurer une base de données et la lier à un pool de ressources | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0d20a569-8a27-409c-bcab-0effefb48013
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0b518c93ca9d5e7157ceaa20d9548d7b6061017d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600013"
---
# <a name="restore-a-database-and-bind-it-to-a-resource-pool"></a><span data-ttu-id="2441c-102">Restaurer une base de données et la lier à un pool de ressources</span><span class="sxs-lookup"><span data-stu-id="2441c-102">Restore a Database and Bind it to a Resource Pool</span></span>
  <span data-ttu-id="2441c-103">Même si vous disposez de suffisamment de mémoire pour restaurer une base de données avec des tables optimisées en mémoire, suivez les meilleures pratiques et liez la base de données à un pool de ressources nommé.</span><span class="sxs-lookup"><span data-stu-id="2441c-103">Even though you have enough memory to restore a database with memory-optimized tables, you want to follow best practices and bind the database to a named resource pool.</span></span> <span data-ttu-id="2441c-104">Comme la base de données doit exister pour que vous puissiez la lier au pool, la restauration de votre base de données s'effectue en plusieurs étapes.</span><span class="sxs-lookup"><span data-stu-id="2441c-104">Since the database must exist before you can bind it to the pool restoring your database is a multi-step process.</span></span> <span data-ttu-id="2441c-105">Cette rubrique vous guide pas à pas dans ce processus.</span><span class="sxs-lookup"><span data-stu-id="2441c-105">This topic walks you through that process.</span></span>  
  
##  <a name="restore-with-norecovery"></a><span data-ttu-id="2441c-106">Effectuer la restauration avec NORECOVERY</span><span class="sxs-lookup"><span data-stu-id="2441c-106">Restore with NORECOVERY</span></span>  
 <span data-ttu-id="2441c-107">Lorsque vous restaurez une base de données avec l'option NORECOVERY, la base de données est créée et l'image disque est restaurée sans consommer de mémoire.</span><span class="sxs-lookup"><span data-stu-id="2441c-107">When you restore a database, NORECOVERY causes the database to be created and the disk image restored without consuming memory.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   FROM DISK = 'C:\IMOLTP_test\IMOLTP_DB.bak'  
   WITH NORECOVERY  
```  
  
##  <a name="create-the-resource-pool"></a><span data-ttu-id="2441c-108">Créer le pool de ressources</span><span class="sxs-lookup"><span data-stu-id="2441c-108">Create the resource pool</span></span>  
 <span data-ttu-id="2441c-109">Le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant crée un pool de ressources nommé Pool_IMOLTP avec la moitié de la mémoire disponible.</span><span class="sxs-lookup"><span data-stu-id="2441c-109">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a resource pool named Pool_IMOLTP with 50% of memory available for its use.</span></span>  <span data-ttu-id="2441c-110">Une fois le pool créé, Resource Governor est reconfiguré afin d'inclure Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="2441c-110">After the pool is created, the Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
CREATE RESOURCE POOL Pool_IMOLTP WITH (MAX_MEMORY_PERCENT = 50);  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
##  <a name="bind-the-database-and-resource-pool"></a><span data-ttu-id="2441c-111">Lier la base de données et le pool de ressources</span><span class="sxs-lookup"><span data-stu-id="2441c-111">Bind the database and resource pool</span></span>  
 <span data-ttu-id="2441c-112">Utilisez la fonction système `sp_xtp_bind_db_resource_pool` pour lier la base de données au pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="2441c-112">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="2441c-113">La fonction accepte deux paramètres : le nom de la base de données suivi du nom du pool de ressources.</span><span class="sxs-lookup"><span data-stu-id="2441c-113">The function takes two parameters: the database name followed by the resource pool name.</span></span>  
  
 <span data-ttu-id="2441c-114">Le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant définit une liaison de la base de données IMOLTP_DB au pool de ressources Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="2441c-114">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="2441c-115">La liaison ne prend pas effet tant que vous n'avez pas terminé l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="2441c-115">The binding does not become effective until you complete the next step.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
##  <a name="restore-with-recovery"></a><span data-ttu-id="2441c-116">Effectuer la restauration avec RECOVERY</span><span class="sxs-lookup"><span data-stu-id="2441c-116">Restore with RECOVERY</span></span>  
 <span data-ttu-id="2441c-117">Lorsque vous restaurez la base de données avec récupération, la base de données est mise en ligne et toutes les données sont restaurées.</span><span class="sxs-lookup"><span data-stu-id="2441c-117">When you restore the database with recovery the database is brought online and all the data restored.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   WITH RECOVERY  
```  
  
##  <a name="monitor-the-resource-pool-performance"></a><span data-ttu-id="2441c-118">Surveillance des performances des pools de ressources</span><span class="sxs-lookup"><span data-stu-id="2441c-118">Monitor the resource pool performance</span></span>  
 <span data-ttu-id="2441c-119">Une fois que la base de données est liée au pool de ressources nommé et qu'elle est restaurée avec récupération, surveillez l'objet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Statistiques des pools de ressources.</span><span class="sxs-lookup"><span data-stu-id="2441c-119">Once the database is bound to the named resource pool and restored with recovery, monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Resource Pool Stats Object.</span></span> <span data-ttu-id="2441c-120">Pour plus d'informations consultez [SQL Server, objet Statistiques des pools de ressources](../performance-monitor/sql-server-resource-pool-stats-object.md).</span><span class="sxs-lookup"><span data-stu-id="2441c-120">For more information see [SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2441c-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2441c-121">See Also</span></span>  
 <span data-ttu-id="2441c-122">[Lier une base de données avec des tables mémoire optimisées à un pool de ressources](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="2441c-122">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span></span>  
 <span data-ttu-id="2441c-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2441c-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="2441c-124">[SQLServer, objet Statistiques des pools de ressources](../performance-monitor/sql-server-resource-pool-stats-object.md) </span><span class="sxs-lookup"><span data-stu-id="2441c-124">[SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md) </span></span>  
 [<span data-ttu-id="2441c-125">sys.dm_resource_governor_resource_pools</span><span class="sxs-lookup"><span data-stu-id="2441c-125">sys.dm_resource_governor_resource_pools</span></span>](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql)  
  
  
