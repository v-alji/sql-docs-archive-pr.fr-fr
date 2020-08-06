---
title: Variables de table optimisées en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: bd102e95-53e2-4da6-9b8b-0e4f02d286d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: bec720c53c257240ee92274a6391ebc3f17faa25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610834"
---
# <a name="memory-optimized-table-variables"></a><span data-ttu-id="12172-102">Variables de table mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="12172-102">Memory-Optimized Table Variables</span></span>
  <span data-ttu-id="12172-103">En plus des tables mémoire optimisées (pour un accès efficace aux données) et des procédures stockées compilées en mode natif (pour une exécution efficace des requêtes et de la logique métier), [!INCLUDE[hek_2](../includes/hek-2-md.md)] introduit un troisième type d'objet : le type de table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="12172-103">In addition to memory-optimized tables (for efficient data access) and natively compiled stored procedures (for efficient query processing and business logic execution) [!INCLUDE[hek_2](../includes/hek-2-md.md)] introduces a third kind of object: the memory-optimized table type.</span></span> <span data-ttu-id="12172-104">Une variable de table créée avec un type de table mémoire optimisée est une variable de table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="12172-104">A table variable created using a memory-optimized table type is a memory-optimized table variable.</span></span>  
  
 <span data-ttu-id="12172-105">Les variables de table mémoire optimisée offrent les avantages suivants par rapport aux variables de table sur disque :</span><span class="sxs-lookup"><span data-stu-id="12172-105">Memory-optimized table variables offer the following advantages when compared to disk-based table variables:</span></span>  
  
-   <span data-ttu-id="12172-106">Les variables sont uniquement stockées dans la mémoire.</span><span class="sxs-lookup"><span data-stu-id="12172-106">The variables are only stored in memory.</span></span> <span data-ttu-id="12172-107">L'accès aux données est plus efficace car le type de table mémoire optimisée utilise le même algorithme et les mêmes structures de données mémoire optimisés utilisés pour les tables mémoire optimisées, en particulier lorsque les variables sont utilisées dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="12172-107">Data access is more efficient because memory-optimized table type use the same memory-optimized algorithm and data structures used for memory-optimized tables, especially when the variables are used in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="12172-108">Avec les variables de table mémoire optimisée, tempdb n'est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="12172-108">With memory-optimized table variables, there is no tempdb utilization.</span></span> <span data-ttu-id="12172-109">Les variables de table ne sont pas stockées dans tempdb et n'utilisent aucune ressource dans tempdb.</span><span class="sxs-lookup"><span data-stu-id="12172-109">Table variables are not stored in tempdb and do not use any resources in tempdb.</span></span>  
  
 <span data-ttu-id="12172-110">Les scénarios d'utilisation typiques des variables de table mémoire optimisée sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="12172-110">The typical usage scenarios for memory-optimized table variables are:</span></span>  
  
-   <span data-ttu-id="12172-111">Stockage de résultats intermédiaires et création d'ensembles de résultats uniques en fonction de plusieurs requêtes dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="12172-111">Storing intermediate results and creating single result sets based on multiple queries in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="12172-112">Passage des paramètres de la table à des procédures stockées compilées en mode natif et à des procédures stockées interprétées.</span><span class="sxs-lookup"><span data-stu-id="12172-112">Passing table-valued parameters into natively compiled stored procedures and interpreted stored procedures.</span></span>  
  
-   <span data-ttu-id="12172-113">Remplacement des variables de table sur disque, et dans certains cas, des tables #temp locales sur une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="12172-113">Replacing disk-based table variables, and in some cases #temp tables that are local to a stored procedure.</span></span> <span data-ttu-id="12172-114">Cela est particulièrement utile s'il y a beaucoup de contentions de tempdb dans le système.</span><span class="sxs-lookup"><span data-stu-id="12172-114">This is particularly useful if there is a lot of tempdb contention in the system.</span></span>  
  
-   <span data-ttu-id="12172-115">Les variables de table peuvent être utilisées pour simuler des curseurs dans les procédures stockées compilées en mode natif, ce qui peut vous aider à contourner les limitations concernant la surface d'exposition dans ces procédures.</span><span class="sxs-lookup"><span data-stu-id="12172-115">Table variables can be used to simulate cursors in natively compiled stored procedures, which can help you work around surface area limitations in natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="12172-116">Comme les tables mémoire optimisées, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] génère une DLL pour chaque type de table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="12172-116">Like memory-optimized tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] generates a DLL for each memory-optimized table type.</span></span> <span data-ttu-id="12172-117">(La compilation est appelée lorsque le type de table mémoire optimisée est créé et non lorsqu’il est utilisé pour créer des variables de table mémoire optimisée.) Cette DLL comprend les fonctions permettant d’accéder aux index et de récupérer des données à partir des variables de table.</span><span class="sxs-lookup"><span data-stu-id="12172-117">(Compilation is invoked when the memory-optimized table type is created and not when used to create memory-optimized table variables.) This DLL includes the functions for accessing indexes and retrieving data from the table variables.</span></span> <span data-ttu-id="12172-118">Lorsqu'une variable de table mémoire optimisée est déclarée en fonction du type de table, une instance de la table et des structures d'index correspondant au type de table est créée dans la session utilisateur.</span><span class="sxs-lookup"><span data-stu-id="12172-118">When a memory-optimized table variable is declared based on the table type, an instance of the table and index structures corresponding to the table type is created in the user session.</span></span> <span data-ttu-id="12172-119">La variable de table peut ensuite être utilisée de la même manière que les variables de table sur disque.</span><span class="sxs-lookup"><span data-stu-id="12172-119">The table variable can then be used in the same way as disk-based table variables.</span></span> <span data-ttu-id="12172-120">Vous pouvez insérer, mettre à jour, et supprimer des lignes dans la variable de table, et utiliser des variables dans les requêtes [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="12172-120">You can insert, update, and delete rows in the table variable, and you can use the variables in [!INCLUDE[tsql](../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="12172-121">Vous pouvez également passer les variables dans les procédures stockées compilées en mode natif et interprétées, comme paramètres de table (TVP).</span><span class="sxs-lookup"><span data-stu-id="12172-121">You can also pass the variables into natively compiled and interpreted stored procedures, as table-valued parameters (TVP).</span></span>  
  
 <span data-ttu-id="12172-122">L'exemple suivant illustre un type de table mémoire optimisée tiré de l'exemple basé sur AdventureWorks de l'OLTP en mémoire ([Exemple d'OLTP en mémoire SQL Server 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span><span class="sxs-lookup"><span data-stu-id="12172-122">The following sample shows a memory-optimized table type from the AdventureWorks-based In-Memory OLTP sample ([SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491)).</span></span>  
  
```sql
CREATE TYPE Sales.SalesOrderDetailType_inmem
   AS TABLE
(
   OrderQty         smallint   NOT NULL,
   ProductID        int        NOT NULL,

   SpecialOfferID   int        NOT NULL
      INDEX  IX_SpecialOfferID  NONCLUSTERED,

   LocalID          int        NOT NULL,

   INDEX IX_ProductID HASH (ProductID)
      WITH ( BUCKET_COUNT = 8 )
)
WITH ( MEMORY_OPTIMIZED = ON );
```  
  
 <span data-ttu-id="12172-123">L'exemple montre que la syntaxe des types de tables mémoire optimisées est similaire aux types de tables sur disque, avec les exceptions suivantes :</span><span class="sxs-lookup"><span data-stu-id="12172-123">The sample shows that the syntax of memory-optimized table types is similar to disk-based table types, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="12172-124">`MEMORY_OPTIMIZED=ON` indique que le type est une table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="12172-124">`MEMORY_OPTIMIZED=ON` indicates that the table type is memory-optimized.</span></span>  
  
-   <span data-ttu-id="12172-125">Le type doit avoir au moins un index.</span><span class="sxs-lookup"><span data-stu-id="12172-125">The type must have at least one index.</span></span> <span data-ttu-id="12172-126">Comme pour les tables mémoire optimisées, vous pouvez utiliser des index de hachage et non cluster.</span><span class="sxs-lookup"><span data-stu-id="12172-126">As with memory-optimized tables, you can use hash and nonclustered indexes.</span></span>  
  
     <span data-ttu-id="12172-127">Pour un index de hachage, le nombre de compartiments doit être égal à une à deux fois le nombre de clés d'index uniques attendu.</span><span class="sxs-lookup"><span data-stu-id="12172-127">For a hash index, the bucket count should be about one to two times the number of expected unique index keys.</span></span> <span data-ttu-id="12172-128">Pour plus d'informations, consultez [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="12172-128">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="12172-129">Les restrictions de type de données et de contrainte sur les tables mémoire optimisées s'appliquent également aux types de table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="12172-129">The data type and constraint restrictions on memory-optimized tables also apply to memory-optimized table types.</span></span> <span data-ttu-id="12172-130">Par exemple, dans [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] , les contraintes par défaut sont prises en charge, mais les contraintes de validation ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="12172-130">For example, in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] default constraints are supported, but check constraints are not.</span></span>  
  
 <span data-ttu-id="12172-131">Comme les tables mémoire optimisées, les variables de table mémoire optimisée :</span><span class="sxs-lookup"><span data-stu-id="12172-131">Like memory-optimized tables, memory-optimized table variables,</span></span>  
  
-   <span data-ttu-id="12172-132">ne prennent pas en charge les plans parallèles ;</span><span class="sxs-lookup"><span data-stu-id="12172-132">Do not support parallel plans.</span></span>  
  
-   <span data-ttu-id="12172-133">doivent tenir dans la mémoire et n'utilisent pas de ressources de disque.</span><span class="sxs-lookup"><span data-stu-id="12172-133">Must fit in memory and do not use disk resources.</span></span>  
  
 <span data-ttu-id="12172-134">Les variables de table sur disque existent dans tempdb.</span><span class="sxs-lookup"><span data-stu-id="12172-134">Disk-based table variables exist in tempdb.</span></span> <span data-ttu-id="12172-135">Les variables de table mémoire optimisée existent dans la base de données utilisateur (mais elles ne consomment pas de stockage et ne sont pas récupérées).</span><span class="sxs-lookup"><span data-stu-id="12172-135">Memory-optimized table variables exist in the user database (but they do not consume storage and are not recovered).</span></span>  
  
 <span data-ttu-id="12172-136">Vous ne pouvez pas créer une variable de table mémoire optimisée avec la syntaxe in-line.</span><span class="sxs-lookup"><span data-stu-id="12172-136">You cannot create a memory-optimized table variable using in-line syntax.</span></span> <span data-ttu-id="12172-137">Contrairement aux variables de table sur disque, vous devez créer d'abord un type.</span><span class="sxs-lookup"><span data-stu-id="12172-137">Unlike disk-based table variables, you must create a type first.</span></span>  
  
## <a name="table-valued-parameters"></a><span data-ttu-id="12172-138">Paramètres table</span><span class="sxs-lookup"><span data-stu-id="12172-138">Table-Valued Parameters</span></span>  
 <span data-ttu-id="12172-139">L'exemple de script suivant illustre la déclaration d'une variable de table comme type de table mémoire optimisée `Sales.SalesOrderDetailType_inmem`, l'insertion de trois lignes dans la variable, et le passage des variables comme TVP dans `Sales.usp_InsertSalesOrder_inmem`.</span><span class="sxs-lookup"><span data-stu-id="12172-139">The following sample script shows the declaration of a table variable as the memory-optimized table type `Sales.SalesOrderDetailType_inmem`, the insert of three rows into the variable, and passing the variable as a TVP into `Sales.usp_InsertSalesOrder_inmem`.</span></span>  
  
```sql  
DECLARE @od Sales.SalesOrderDetailType_inmem,  
  @SalesOrderID uniqueidentifier,  
  @DueDate datetime2 = SYSDATETIME()  
  
INSERT @od (LocalID, ProductID, OrderQty, SpecialOfferID) VALUES  
  (1, 888, 2, 1),  
  (2, 450, 13, 1),  
  (3, 841, 1, 1)  
  
EXEC Sales.usp_InsertSalesOrder_inmem  
  @SalesOrderID = @SalesOrderID,  
  @DueDate = @DueDate,  
 @OnlineOrderFlag = 1,  
  @SalesOrderDetails = @od  
```  
  
 <span data-ttu-id="12172-140">Les types de table mémoire optimisée peuvent être utilisés comme type pour les paramètres de table (TVP) de la procédure stockée et peuvent être référencés par des clients exactement comme des types de table et des TVP sur disque.</span><span class="sxs-lookup"><span data-stu-id="12172-140">Memory-optimized table types can be used as the type for stored procedure table-valued parameters (TVPs) and can be referenced by clients exactly the same as disk-based table types and TVPs.</span></span> <span data-ttu-id="12172-141">Par conséquent, l'appel de procédures stockées avec des TVP mémoire optimisés et de procédures stockées compilées en mode natif, fonctionne exactement comme l'appel de procédures stockées interprétées avec des TVP sur disque.</span><span class="sxs-lookup"><span data-stu-id="12172-141">Therefore, the invocation of stored procedures with memory-optimized TVPs, and natively compiled stored procedures works exactly the same as the invocation of interpreted stored procedures with disk-based TVPs.</span></span>  
  
## <a name="temp-table-replacement"></a><span data-ttu-id="12172-142">Remplacement de la table #temp</span><span class="sxs-lookup"><span data-stu-id="12172-142">#temp Table Replacement</span></span>  
 <span data-ttu-id="12172-143">L'exemple suivant illustre les types de table et les variables de table mémoire optimisée remplaçant les tables #temp locales sur une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="12172-143">The following sample shows memory-optimized table types and table variables as a replacement for #temp tables that are local to a stored procedure.</span></span>  
  
```sql  
-- Using SQL procedure and temp table  
CREATE TABLE #tempTable (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
  
CREATE PROCEDURE sqlProc  
AS  
BEGIN  
  TRUNCATE TABLE #tempTable  
  
  INSERT #tempTable VALUES (1)  
  INSERT #tempTable VALUES (2)  
  INSERT #tempTable VALUES (3)  
  SELECT * FROM #tempTable  
END  
GO  
  
-- Using natively compiled stored procedure and table variable  
CREATE TYPE TT AS TABLE (c INT NOT NULL PRIMARY KEY NONCLUSTERED)  
GO  
  
CREATE PROCEDURE NCSPProc  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
  DECLARE @tableVariable TT  
  INSERT @tableVariable VALUES (1)  
  INSERT @tableVariable VALUES (2)  
  INSERT @tableVariable VALUES (3)  
  SELECT c FROM @tableVariable  
END  
GO  
```  
  
## <a name="creating-a-single-result-set"></a><span data-ttu-id="12172-144">Création d'un seul ensemble de résultats</span><span class="sxs-lookup"><span data-stu-id="12172-144">Creating a Single Result Set</span></span>  
 <span data-ttu-id="12172-145">L'exemple suivant explique comment stocker des résultats intermédiaires et créer des ensembles de résultats uniques en fonction de plusieurs requêtes dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="12172-145">The following sample shows how to store intermediate results and create single result sets based on multiple queries in natively compiled stored procedures.</span></span> <span data-ttu-id="12172-146">L'exemple calcule l'union `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span><span class="sxs-lookup"><span data-stu-id="12172-146">The sample is computing the union `SELECT c1 FROM dbo.t1 UNION SELECT c1 FROM dbo.t2`.</span></span>  
  
```sql  
CREATE DATABASE hk  
GO  
ALTER DATABASE hk ADD FILEGROUP hk_mod CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE hk ADD FILE( NAME = 'hk_mod' , FILENAME = 'c:\data\hk_mod') TO FILEGROUP hk_mod;  
  
USE hk  
GO  
  
CREATE TYPE tab1 AS TABLE (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON)  
  
CREATE TABLE dbo.t1 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
CREATE TABLE dbo.t2 (c1 INT NOT NULL, INDEX idx NONCLUSTERED(c1)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
  
INSERT INTO dbo.t1 VALUES (1), (2)  
INSERT INTO dbo.t2 VALUES (3), (4)  
GO  
  
CREATE PROCEDURE dbo.p1  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
  AS  
  BEGIN ATOMIC WITH ( TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english' )  
  
    DECLARE @t dbo.tab1  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t1;  
  
    INSERT @t (c1)  
    SELECT c1 FROM dbo.t2;  
  
    SELECT c1 FROM @t;  
  END  
GO  
  
EXEC dbo.p1  
GO  
```  
  
## <a name="memory-consumption-for-table-variables"></a><span data-ttu-id="12172-147">Consommation de mémoire pour les variables de table</span><span class="sxs-lookup"><span data-stu-id="12172-147">Memory Consumption for Table Variables</span></span>  
 <span data-ttu-id="12172-148">La consommation de mémoire pour les variables de table est similaire aux tables mémoire optimisées, à l'exception des index non cluster.</span><span class="sxs-lookup"><span data-stu-id="12172-148">Memory consumption for table variables is similar to memory-optimized tables, with the exception of nonclustered indexes.</span></span> <span data-ttu-id="12172-149">Si vous insérez de nombreuses lignes dans des variables de table mémoire optimisée avec des index non cluster et si les clés d'index sont longues, ces variables utiliseront une quantité démesurée de mémoire.</span><span class="sxs-lookup"><span data-stu-id="12172-149">If you insert a lot of rows into memory-optimized table variables with nonclustered indexes and if the index keys are large, these table variables will use a disproportionate amount of memory.</span></span> <span data-ttu-id="12172-150">Les index non cluster sur les grandes de variables de table nécessitent proportionnellement plus de mémoire qu'un index non cluster pour le même nombre de lignes insérées dans une table (plus de mémoire dans les pages d'index).</span><span class="sxs-lookup"><span data-stu-id="12172-150">Nonclustered indexes on large table variables require proportionately more memory than a nonclustered index would require for the same number of rows inserted into a table (more memory in the index pages).</span></span>  
  
 <span data-ttu-id="12172-151">La mémoire pour les variables de table vient du pool de ressources du gouverneur de ressources de la base de données.</span><span class="sxs-lookup"><span data-stu-id="12172-151">Memory for table variables comes from the database's Resource Governor resource pool.</span></span>  
  
 <span data-ttu-id="12172-152">Contrairement aux tables mémoire optimisées, la mémoire consommée (lignes supprimées incluses) par les variables de table est libérée lorsque la variable de table sort de l'étendue.</span><span class="sxs-lookup"><span data-stu-id="12172-152">Unlike memory-optimized tables, the memory consumed (including deleted rows) by table variables is freed when the table variable goes out of scope.</span></span>  
  
 <span data-ttu-id="12172-153">La mémoire est prise en compte dans le cadre d'un seul consommateur de mémoire PGPOOL de la base de données.</span><span class="sxs-lookup"><span data-stu-id="12172-153">Memory is accounted for as part of the single PGPOOL memory consumer of the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12172-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12172-154">See Also</span></span>  
 [<span data-ttu-id="12172-155">Prise en charge de Transact-SQL pour OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="12172-155">Transact-SQL Support for In-Memory OLTP</span></span>](../relational-databases/in-memory-oltp/transact-sql-support-for-in-memory-oltp.md)  
  
  
