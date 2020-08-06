---
title: 'Démonstration : optimisation des performances de l’OLTP en mémoire | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c6def45d-d2d4-4d24-8068-fab4cd94d8cc
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4858e4c35263ab3dd1d9fdcf55a2b136dd8eeaf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605430"
---
# <a name="demonstration-performance-improvement-of-in-memory-oltp"></a><span data-ttu-id="da1a5-102">Démonstration : Optimisation des performances de l'OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="da1a5-102">Demonstration: Performance Improvement of In-Memory OLTP</span></span>
  <span data-ttu-id="da1a5-103">Cet exemple illustre les améliorations des performances obtenues avec l'OLTP en mémoire en comparant les différences des temps de réponse lors de l'exécution d'une requête Transact-SQL identique sur des tables optimisées en mémoire et des tables sur disque classiques.</span><span class="sxs-lookup"><span data-stu-id="da1a5-103">This example shows performance improvements when using In-Memory OLTP by comparing differences in response times when running an identical Transact-SQL query against memory-optimized and traditional disk-based tables.</span></span> <span data-ttu-id="da1a5-104">En outre, une procédure stockée compilée en mode natif est également créée (selon la même requête), puis exécutée pour montrer que vous obtenez généralement les meilleurs temps de réponse lors de l'interrogation d'une table optimisée en mémoire avec une procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="da1a5-104">Additionally, a natively-compiled stored procedure is also created (based on the same query) and then run to demonstrate that you typically get the best response times when querying a memory-optimized table with a natively-compiled stored procedure.</span></span> <span data-ttu-id="da1a5-105">Cet exemple ne montre qu'un aspect des améliorations des performances lors de l'accès aux données dans des tables optimisées en mémoire : l'efficacité de l'accès aux données lors de l'exécution d'insertions.</span><span class="sxs-lookup"><span data-stu-id="da1a5-105">This sample only shows one aspect of performance improvements when accessing data in memory-optimized tables; data access efficiency when performing inserts.</span></span> <span data-ttu-id="da1a5-106">Cet échantillon est monothread et ne tire pas profit des avantages de concurrence de l'OLTP en mémoire.</span><span class="sxs-lookup"><span data-stu-id="da1a5-106">This sample is single-threaded and does not take advantage of the concurrency benefits of In-Memory OLTP.</span></span> <span data-ttu-id="da1a5-107">Une charge de travail utilisant la concurrence aura des gains de performance supérieurs.</span><span class="sxs-lookup"><span data-stu-id="da1a5-107">A workload that uses concurrency will see a greater performance gain.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da1a5-108">Un autre exemple illustrant les tables optimisées en mémoire est disponible dans [l’exemple d’OLTP en mémoire SQL Server 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="da1a5-108">Another sample demonstrating memory-optimized tables is available at [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="da1a5-109">Pour exécuter cet exemple, vous allez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="da1a5-109">To complete this sample you will perform the following:</span></span>  
  
1.  <span data-ttu-id="da1a5-110">Créez une base de données nommée **imoltp** et modifiez ses détails de fichier pour la configurer pour l’utilisation de l’OLTP en mémoire.</span><span class="sxs-lookup"><span data-stu-id="da1a5-110">Create a database named **imoltp** and alter its file details to set it up for using In-Memory OLTP.</span></span>  
  
2.  <span data-ttu-id="da1a5-111">créer les objets de base de données pour notre exemple : trois tables et une procédure stockée compilée en mode natif ;</span><span class="sxs-lookup"><span data-stu-id="da1a5-111">Create the database objects for our sample: three tables and a natively-compiled stored procedure.</span></span>  
  
3.  <span data-ttu-id="da1a5-112">exécuter les différentes requêtes et afficher les temps de réponse pour chacune d'elles.</span><span class="sxs-lookup"><span data-stu-id="da1a5-112">Run the different queries and display the response times for each query.</span></span>  
  
 <span data-ttu-id="da1a5-113">Pour configurer la base de données **imoltp** pour notre exemple, commencez par créer un dossier vide : **c:\ imoltp_data**, puis exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="da1a5-113">To setup the **imoltp** database for our example, first create an empty folder: **c:\imoltp_data**, and then run the following code:</span></span>  
  
```sql  
USE master  
GO  
  
-- Create a new database.  
CREATE DATABASE imoltp  
GO  
  
-- Prepare the database for In-Memory OLTP by  
-- adding a memory-optimized filegroup to the database.  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_file_group  
    CONTAINS MEMORY_OPTIMIZED_DATA;  
  
-- Add a file (to hold the memory-optimized data) to the new filegroup.  
ALTER DATABASE imoltp ADD FILE (name='imoltp_file', filename='c:\imoltp_data\imoltp_file')  
    TO FILEGROUP imoltp_file_group;  
GO  
  
```  
  
 <span data-ttu-id="da1a5-114">Ensuite, exécutez le code suivant pour créer la table sur disque, deux (2) tables optimisées en mémoire et la procédure stockée compilée en mode natif pour illustrer les différentes méthodes d'accès aux données :</span><span class="sxs-lookup"><span data-stu-id="da1a5-114">Next, run the following code to create the disk-based table, two (2) memory-optimized tables, and the natively-compiled stored procedure that will be used to demonstrate the different data access methods:</span></span>  
  
```sql  
USE imoltp  
GO  
  
-- If the tables or stored procedure already exist, drop them to start clean.  
IF EXISTS (SELECT NAME FROM sys.objects WHERE NAME = 'DiskBasedTable')  
   DROP TABLE [dbo].[DiskBasedTable]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects WHERE NAME = 'InMemTable')  
   DROP TABLE [dbo].[InMemTable]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects  WHERE NAME = 'InMemTable2')  
   DROP TABLE [dbo].[InMemTable2]  
GO  
  
IF EXISTS (SELECT NAME FROM sys.objects  WHERE NAME = 'usp_InsertData')  
   DROP PROCEDURE [dbo].[usp_InsertData]  
GO  
  
-- Create a traditional disk-based table.  
CREATE TABLE [dbo].[DiskBasedTable] (  
  c1 INT NOT NULL PRIMARY KEY,  
  c2 NCHAR(48) NOT NULL  
)  
GO  
  
-- Create a memory-optimized table.  
CREATE TABLE [dbo].[InMemTable] (  
  c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT=1000000),  
  c2 NCHAR(48) NOT NULL  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY = SCHEMA_AND_DATA);  
GO  
  
-- Create a 2nd memory-optimized table.  
CREATE TABLE [dbo].[InMemTable2] (  
  c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT=1000000),  
  c2 NCHAR(48) NOT NULL  
) WITH (MEMORY_OPTIMIZED=ON, DURABILITY = SCHEMA_AND_DATA);  
GO  
  
-- Create a natively-compiled stored procedure.  
CREATE PROCEDURE [dbo].[usp_InsertData]   
  @rowcount INT,  
  @c NCHAR(48)  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
  AS   
  BEGIN ATOMIC   
  WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
  DECLARE @i INT = 1;  
  WHILE @i <= @rowcount  
  BEGIN  
    INSERT INTO [dbo].[inMemTable2](c1,c2) VALUES (@i, @c);  
    SET @i += 1;  
  END  
END  
GO  
  
```  
  
 <span data-ttu-id="da1a5-115">L'installation est terminée et nous sommes prêts à exécuter les requêtes qui affichent les temps de réponse comparant les performances entre les méthodes d'accès aux données.</span><span class="sxs-lookup"><span data-stu-id="da1a5-115">The setup is complete and we are ready to execute the queries that will display the response times comparing the performance between the data access methods.</span></span>  
  
 <span data-ttu-id="da1a5-116">Pour exécuter l'exemple, exécutez le code suivant plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="da1a5-116">To complete the example run the following code multiple times.</span></span> <span data-ttu-id="da1a5-117">Ignorez les résultats de la première exécution, qui sont négativement affectés par l'allocation de mémoire initiale.</span><span class="sxs-lookup"><span data-stu-id="da1a5-117">Ignore the results from the first run which is negatively affected by initial memory allocation.</span></span>  
  
```sql  
SET STATISTICS TIME OFF;  
SET NOCOUNT ON;  
  
-- Delete data from all tables to reset the example.  
DELETE FROM [dbo].[DiskBasedTable]   
    WHERE [c1]>0  
GO  
DELETE FROM [dbo].[inMemTable]   
    WHERE [c1]>0  
GO  
DELETE FROM [dbo].[InMemTable2]   
    WHERE [c1]>0  
GO  
  
-- Declare parameters for the test queries.  
DECLARE @i INT = 1;  
DECLARE @rowcount INT = 100000;  
DECLARE @c NCHAR(48) = N'12345678901234567890123456789012345678';  
DECLARE @timems INT;  
DECLARE @starttime datetime2 = sysdatetime();  
  
-- Disk-based table queried with interpreted Transact-SQL.  
BEGIN TRAN  
  WHILE @I <= @rowcount  
  BEGIN  
    INSERT INTO [dbo].[DiskBasedTable](c1,c2) VALUES (@i, @c);  
    SET @i += 1;  
  END  
COMMIT  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (disk-based table with interpreted Transact-SQL).';  
  
-- Memory-optimized table queried with interpreted Transact-SQL.  
SET @i = 1;  
SET @starttime = sysdatetime();  
  
BEGIN TRAN  
  WHILE @i <= @rowcount  
    BEGIN  
      INSERT INTO [dbo].[InMemTable](c1,c2) VALUES (@i, @c);  
      SET @i += 1;  
    END  
COMMIT  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (memory-optimized table with interpreted Transact-SQL).';  
  
-- Memory-optimized table queried with a natively-compiled stored procedure.  
SET @starttime = sysdatetime();  
  
EXEC usp_InsertData @rowcount, @c;  
  
SET @timems = datediff(ms, @starttime, sysdatetime());  
SELECT CAST(@timems AS VARCHAR(10)) + ' ms (memory-optimized table with natively-compiled stored procedure).';  
  
```  
  
 <span data-ttu-id="da1a5-118">Les résultats attendus fournissent les temps de réponse réels qui montrent comment l'utilisation des tables optimisées en mémoire et des procédures stockées compilées en mode natif offre généralement des temps de réponse plus courts que les mêmes charges de travail exécutées sur des tables sur disque classiques.</span><span class="sxs-lookup"><span data-stu-id="da1a5-118">The expected results provide actual response times showing how using memory-optimized tables and natively-compiled stored procedures typically provides consistently faster response times than the same workloads running against traditional disk-based tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da1a5-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da1a5-119">See Also</span></span>  
 <span data-ttu-id="da1a5-120">[Extensions à AdventureWorks pour présenter l’OLTP en mémoire](../../database-engine/extensions-to-adventureworks-to-demonstrate-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="da1a5-120">[Extensions to AdventureWorks to Demonstrate In-Memory OLTP](../../database-engine/extensions-to-adventureworks-to-demonstrate-in-memory-oltp.md) </span></span>  
 <span data-ttu-id="da1a5-121">[OLTP en mémoire &#40;optimisation en mémoire&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="da1a5-121">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 <span data-ttu-id="da1a5-122">[Tables optimisées en mémoire](memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="da1a5-122">[Memory-Optimized Tables](memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="da1a5-123">[Procédures stockées compilées en mode natif](natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="da1a5-123">[Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) </span></span>  
 <span data-ttu-id="da1a5-124">[Exigences liées à l’utilisation des tables à mémoire optimisée](requirements-for-using-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="da1a5-124">[Requirements for Using Memory-Optimized Tables](requirements-for-using-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="da1a5-125">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="da1a5-125">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="da1a5-126">[Options de fichiers et de groupes de fichiers ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span><span class="sxs-lookup"><span data-stu-id="da1a5-126">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span></span>  
 [<span data-ttu-id="da1a5-127">CRÉER des tables à procédure et à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="da1a5-127">CREATE PROCEDURE and Memory-Optimized Tables</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
