---
title: Modèle d’application pour partitionner des tables mémoire optimisées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 3f867763-a8e6-413a-b015-20e9672cc4d1
author: rothja
ms.author: jroth
ms.openlocfilehash: d2633cdf1b631a1d9209adf26f4773e27c4c44c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601458"
---
# <a name="application-pattern-for-partitioning-memory-optimized-tables"></a><span data-ttu-id="dd485-102">Modèle d'application pour partitionner des tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="dd485-102">Application Pattern for Partitioning Memory-Optimized Tables</span></span>
  [!INCLUDE[hek_2](../../includes/hek-2-md.md)] <span data-ttu-id="dd485-103">prend en charge un modèle selon lequel une quantité limitée de données actives est conservée dans une table optimisée en mémoire, tandis que les données auxquelles on accède moins fréquemment sont traitées sur le disque.</span><span class="sxs-lookup"><span data-stu-id="dd485-103">supports a pattern where a limited amount of active data is kept in a memory-optimized table, while less-frequently accessed data is processed on disk.</span></span> <span data-ttu-id="dd485-104">En général, c'est un scénario où les données sont stockées en fonction d'une clé `datetime`.</span><span class="sxs-lookup"><span data-stu-id="dd485-104">Typically, this would be a scenario where data is stored based on a `datetime` key.</span></span>  
  
 <span data-ttu-id="dd485-105">Pour émuler les tables partitionnées avec les tables mémoire optimisées, conservez une table partitionnée et une table mémoire optimisée avec un schéma commun.</span><span class="sxs-lookup"><span data-stu-id="dd485-105">You can emulate partitioned tables with memory-optimized tables by maintaining a partitioned table and a memory-optimized table with a common schema.</span></span> <span data-ttu-id="dd485-106">Les données actives sont insérées et mises à jour dans la table mémoire optimisée, alors que les données les moins fréquemment sollicitées sont conservées dans la table partitionnée traditionnelle.</span><span class="sxs-lookup"><span data-stu-id="dd485-106">Current data would be inserted and updated in the memory-optimized table, while less-frequently accessed data would be maintained in the traditional partitioned table.</span></span>  
  
 <span data-ttu-id="dd485-107">Une application qui sait que les données actives sont dans une table mémoire optimisée peut utiliser des procédures stockées compilées en mode natif pour accéder aux données.</span><span class="sxs-lookup"><span data-stu-id="dd485-107">An application that knows that the active data is in a memory-optimized table can use natively compiled stored procedures to access the data.</span></span> <span data-ttu-id="dd485-108">Les opérations qui doivent accéder à la plage de données complète, ou qui peuvent ne pas savoir quelle table contient les données appropriées, utilisent le langage [!INCLUDE[tsql](../../includes/tsql-md.md)] interprété pour joindre la table mémoire optimisée à la table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="dd485-108">Operations that need to access the entire span of data, or which may not know which table holds relevant data, use interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] to join the memory-optimized table with the partitioned table.</span></span>  
  
 <span data-ttu-id="dd485-109">Ce basculement de partition s'effectue comme suit :</span><span class="sxs-lookup"><span data-stu-id="dd485-109">This partition switch is described as follows:</span></span>  
  
-   <span data-ttu-id="dd485-110">Insérez des données de la table de l'OLTP en mémoire dans une table de mise en lots, en utilisant si possible une date de coupure.</span><span class="sxs-lookup"><span data-stu-id="dd485-110">Insert data from the In-Memory OLTP table into a staging table, possibly using a cutoff date.</span></span>  
  
-   <span data-ttu-id="dd485-111">Supprimez les données de la table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="dd485-111">Delete the same data from the memory-optimized table.</span></span>  
  
-   <span data-ttu-id="dd485-112">Basculez dans la table de mise en lots.</span><span class="sxs-lookup"><span data-stu-id="dd485-112">Swap in the staging table.</span></span>  
  
-   <span data-ttu-id="dd485-113">Ajoutez la partition active.</span><span class="sxs-lookup"><span data-stu-id="dd485-113">Add the active partition.</span></span>  
  
 <span data-ttu-id="dd485-114">![Basculement de partition.](../../database-engine/media/hekaton-partitioned-tables.gif "Basculement de partition.")</span><span class="sxs-lookup"><span data-stu-id="dd485-114">![Partition switch.](../../database-engine/media/hekaton-partitioned-tables.gif "Partition switch.")</span></span>  
<span data-ttu-id="dd485-115">Maintenance de données actives</span><span class="sxs-lookup"><span data-stu-id="dd485-115">Active Data Maintenance</span></span>  
  
 <span data-ttu-id="dd485-116">Les actions qui commencent par Deleting ActiveOrders doivent être effectuées pendant une période de maintenance pour éviter des requêtes sans données pendant l'intervalle entre la suppression des données et le basculement dans la table de mise en lots.</span><span class="sxs-lookup"><span data-stu-id="dd485-116">The actions starting with Deleting ActiveOrders need to be done during a maintenance window to avoid queries missing data during the time between deleting data and switching in the staging table.</span></span>  
  
 <span data-ttu-id="dd485-117">Pour obtenir un exemple, consultez [Partitionnement au niveau de l’application](application-level-partitioning.md).</span><span class="sxs-lookup"><span data-stu-id="dd485-117">For a related sample, see [Application-Level Partitioning](application-level-partitioning.md).</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="dd485-118">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="dd485-118">Code Sample</span></span>  
 <span data-ttu-id="dd485-119">L'exemple suivant montre comment utiliser une table mémoire optimisée avec une table sur disque partitionnée.</span><span class="sxs-lookup"><span data-stu-id="dd485-119">The following sample shows how to use a memory-optimized table with a partitioned disk-based table.</span></span> <span data-ttu-id="dd485-120">Les données couramment utilisées sont stockées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="dd485-120">Frequently-used data is stored in memory.</span></span> <span data-ttu-id="dd485-121">Pour enregistrer les données sur le disque, créez une partition et copiez les données dans la table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="dd485-121">To save the data to disk, create a new partition and copy the data to the partitioned table.</span></span>  
  
 <span data-ttu-id="dd485-122">La première partie de cet exemple permet de créer la base de données et les objets nécessaires.</span><span class="sxs-lookup"><span data-stu-id="dd485-122">The first part of this sample creates the database and necessary objects.</span></span> <span data-ttu-id="dd485-123">La deuxième partie de l'exemple montre comment déplacer des données d'une table mémoire optimisée dans une table partitionnée.</span><span class="sxs-lookup"><span data-stu-id="dd485-123">The second part of the sample shows how to move data from a memory-optimized table into a partitioned table.</span></span>  
  
```sql  
CREATE DATABASE partitionsample;  
GO  
  
-- enable for In-Memory OLTP - change file path as needed  
ALTER DATABASE partitionsample ADD FILEGROUP partitionsample_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE partitionsample ADD FILE( NAME = 'partitionsample_mod' , FILENAME = 'c:\data\partitionsample_mod') TO FILEGROUP partitionsample_mod;  
GO  
  
USE partitionsample;  
GO  
  
-- frequently used portion of the SalesOrders - memory-optimized  
  
CREATE TABLE dbo.SalesOrders_hot (  
   so_id INT IDENTITY PRIMARY KEY NONCLUSTERED,  
   cust_id INT NOT NULL,  
   so_date DATETIME2 NOT NULL INDEX ix_date NONCLUSTERED,  
   so_total MONEY NOT NULL,  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- cold portion of the SalesOrders - partitioned disk-based table  
CREATE PARTITION FUNCTION [ByDatePF](datetime2) AS RANGE RIGHT   
   FOR VALUES();  
GO  
  
CREATE PARTITION SCHEME [ByDateRange]   
   AS PARTITION [ByDatePF]   
   ALL TO ([PRIMARY]);  
GO  
  
CREATE TABLE dbo.SalesOrders_cold (  
   so_id INT NOT NULL,  
   cust_id INT NOT NULL,  
   so_date DATETIME2 NOT NULL,  
   so_total MONEY NOT NULL,  
   CONSTRAINT PK_SalesOrders_cold PRIMARY KEY (so_id, so_date),  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc)  
) ON [ByDateRange](so_date)  
GO  
  
-- table for temporary partitions  
CREATE TABLE dbo.SalesOrders_cold_staging (  
   so_id INT NOT NULL,  
   cust_id INT NOT NULL,  
   so_date datetime2 NOT NULL,  
   so_total MONEY NOT NULL,  
   CONSTRAINT PK_SalesOrders_cold_staging PRIMARY KEY (so_id, so_date),  
   INDEX ix_date_total NONCLUSTERED (so_date desc, so_total desc),  
   CONSTRAINT CHK_SalesOrders_cold_staging CHECK (so_date >= '1900-01-01')  
)  
GO  
  
-- aggregate view of the hot and cold data  
CREATE VIEW dbo.SalesOrders  
AS SELECT so_id,  
   cust_id,  
   so_date,  
   so_total,  
   1 AS 'is_hot'  
   FROM dbo.SalesOrders_hot  
   UNION ALL  
   SELECT so_id,  
          cust_id,  
          so_date,  
          so_total,  
          0 AS 'is_hot'  
          FROM dbo.SalesOrders_cold;  
GO  
  
-- move all sales orders up to the split date to cold storage  
CREATE PROCEDURE dbo.usp_SalesOrdersOffloadToCold @splitdate datetime2  
   AS  
   BEGIN  
      BEGIN TRANSACTION;  
      -- create new heap based on the hot data to be moved to cold storage  
      INSERT INTO dbo.SalesOrders_cold_staging WITH( TABLOCKX)  
      SELECT so_id , cust_id , so_date , so_total  
         FROM dbo.SalesOrders_hot WITH ( serializable)  
         WHERE so_date <= @splitdate;  
  
      -- remove moved data  
      DELETE FROM dbo.SalesOrders_hot WITH( SERIALIZABLE)  
         WHERE so_date <= @splitdate;  
  
      -- update partition function, and switch in new partition  
      ALTER PARTITION SCHEME [ByDateRange] NEXT USED [PRIMARY];  
  
      DECLARE @p INT = ( SELECT MAX( partition_number) FROM sys.partitions WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold'));  
      EXEC sp_executesql N'alter table dbo.SalesOrders_cold_staging  
         SWITCH TO dbo.SalesOrders_cold partition @i' , N'@i int' , @i = @p;  
  
      ALTER PARTITION FUNCTION [ByDatePF]()  
      SPLIT RANGE( @splitdate);  
  
      -- modify constraint on staging table to align with new partition  
      ALTER TABLE dbo.SalesOrders_cold_staging DROP CONSTRAINT CHK_SalesOrders_cold_staging;  
  
      DECLARE @s nvarchar( 100) = CONVERT( nvarchar( 100) , @splitdate , 121);  
      DECLARE @sql nvarchar( 1000) = N'alter table dbo.SalesOrders_cold_staging   
         add constraint CHK_SalesOrders_cold_staging check (so_date > ''' + @s + ''')';  
      PRINT @sql;  
      EXEC sp_executesql @sql;  
  
      COMMIT;  
END;  
GO  
  
-- insert sample values in the hot table  
INSERT INTO dbo.SalesOrders_hot VALUES(1,SYSDATETIME(), 1);   
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(1, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(1, SYSDATETIME(), 1);  
GO  
  
-- verify contents of the table  
SELECT *  FROM dbo.SalesOrders;  
GO  
  
-- offload all sales orders to date to cold storage  
DECLARE  @t datetime2 = SYSDATETIME();  
EXEC dbo.usp_SalesOrdersOffloadToCold @t;  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- verify partitions  
SELECT OBJECT_NAME( object_id) , * FROM sys.dm_db_partition_stats ps  
   WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold');  
  
-- insert more rows in the hot table  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
INSERT INTO dbo.SalesOrders_hot VALUES(2, SYSDATETIME(), 1);  
GO  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- offload all sales orders to date to cold storage  
DECLARE @t datetime2 = SYSDATETIME();  
EXEC dbo.usp_SalesOrdersOffloadToCold @t;  
  
-- verify contents of the tables  
SELECT * FROM dbo.SalesOrders;  
GO  
  
-- verify partitions  
SELECT OBJECT_NAME( object_id) , partition_number , row_count  FROM sys.dm_db_partition_stats ps  
  WHERE object_id = OBJECT_ID( 'dbo.SalesOrders_cold') AND index_id = 1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd485-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd485-124">See Also</span></span>  
 [<span data-ttu-id="dd485-125">Tables à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="dd485-125">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
