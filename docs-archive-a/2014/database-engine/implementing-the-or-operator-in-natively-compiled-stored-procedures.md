---
title: Implémentation de l’opérateur OR dans les procédures stockées compilées en mode natif | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2528e74-2b1c-48cb-861b-c4e57b51ac35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ed762e062cbc6831eb46784ef71fc7889850676
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703283"
---
# <a name="implementing-the-or-operator-in-natively-compiled-stored-procedures"></a><span data-ttu-id="93da7-102">Implémentation de l'opérateur OR dans les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="93da7-102">Implementing the OR Operator in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="93da7-103">Les opérateurs OR ne sont pas pris en charge dans les prédicats de requête des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="93da7-103">OR operators are not supported in query predicates in natively compiled stored procedures.</span></span> <span data-ttu-id="93da7-104">Les opérateurs NOT n'étant pas pris en charge non plus dans les prédicats de requête des procédures stockées compilées en mode natif, les effets des opérateurs OR ne peuvent pas être simulés en utilisant uniquement des opérateurs logiques équivalents.</span><span class="sxs-lookup"><span data-stu-id="93da7-104">Because NOT operators are also not supported in query predicates in natively compiled stored procedures, the effects of OR operators cannot be simulated through the use of equivalent logical operators alone.</span></span> <span data-ttu-id="93da7-105">Toutefois, les effets d'un opérateur OR peuvent être simulés avec des variables de table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="93da7-105">However, the effects of an OR operator may be simulated with memory-optimized table variables.</span></span>  
  
## <a name="or-operator-in-where-clause"></a><span data-ttu-id="93da7-106">Opérateur OR dans la clause WHERE</span><span class="sxs-lookup"><span data-stu-id="93da7-106">OR Operator in WHERE Clause</span></span>  
 <span data-ttu-id="93da7-107">Si vous avez un opérateur OR dans une clause WHERE, vous pouvez utiliser la méthode suivante pour simuler son comportement :</span><span class="sxs-lookup"><span data-stu-id="93da7-107">If you have an OR operator in a WHERE clause, you can use the following approach to simulate its behavior:</span></span>  
  
1.  <span data-ttu-id="93da7-108">Créez une variable de table mémoire optimisée avec le schéma approprié.</span><span class="sxs-lookup"><span data-stu-id="93da7-108">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="93da7-109">Cela nécessite un type de table mémoire optimisée prédéfini.</span><span class="sxs-lookup"><span data-stu-id="93da7-109">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="93da7-110">En commençant par l'opérateur OR de niveau supérieur, séparez la clause WHERE en deux parties selon les prédicats joints par l'opérateur OR.</span><span class="sxs-lookup"><span data-stu-id="93da7-110">Starting with the top level OR operator, separate the WHERE clause into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="93da7-111">Si vous avez plusieurs opérateurs OR dans une clause WHERE, vous devrez peut-être effectuer cette opération plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="93da7-111">If you have more than one OR operator in a WHERE clause, you may need to do this more than once.</span></span> <span data-ttu-id="93da7-112">Répétez cette étape jusqu'à ce qu'il ne reste plus aucun opérateur OR.</span><span class="sxs-lookup"><span data-stu-id="93da7-112">Repeat this step until no OR operators remain.</span></span> <span data-ttu-id="93da7-113">Prenons l'exemple du prédicat suivant :</span><span class="sxs-lookup"><span data-stu-id="93da7-113">For example, if you have the following predicate:</span></span>  
  
    ```  
    pred1 OR (pred2 AND (pred3 OR pred4)) OR (pred5 AND pred6)  
    ```  
  
     <span data-ttu-id="93da7-114">Après cette étape, vous devriez avoir les prédicats suivants :</span><span class="sxs-lookup"><span data-stu-id="93da7-114">After this step, you should have the following predicates:</span></span>  
  
    ```  
    pred1  
    pred5 AND pred6  
    pred2 AND pred3  
    pred2 AND pred4  
    ```  
  
3.  <span data-ttu-id="93da7-115">Exécutez une requête avec chacune des deux parties figurant dans l'étape 2 en tant que prédicat.</span><span class="sxs-lookup"><span data-stu-id="93da7-115">Execute a query with each of the two parts found in Step 2 as the predicate.</span></span> <span data-ttu-id="93da7-116">Insérez le résultat de chaque requête dans la variable de table mémoire optimisée créée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="93da7-116">Insert the result for each query into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="93da7-117">Si nécessaire, supprimez les doublons de la variable de table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="93da7-117">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="93da7-118">Utilisez le contenu de la variable de table mémoire optimisée comme résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="93da7-118">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="93da7-119">L'exemple suivant utilise les tables de la base de données AdventureWorks2012 mises à jour pour [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93da7-119">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="93da7-120">Pour télécharger les fichiers de cet exemple, accédez à [bases de données AdventureWorks-2012, 2008R2 et 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="93da7-120">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="93da7-121">Pour appliquer [!INCLUDE[hek_2](../includes/hek-2-md.md)] l’exemple de code à AdventureWorks2012, accédez à [SQL Server exemple d’OLTP en mémoire 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="93da7-121">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="93da7-122">Ajoutez la procédure stockée suivante à la base de données.</span><span class="sxs-lookup"><span data-stu-id="93da7-122">Add the following stored procedure to the database.</span></span> <span data-ttu-id="93da7-123">Nous convertirons cette procédure stockée pour utiliser la compilation native.</span><span class="sxs-lookup"><span data-stu-id="93da7-123">We will convert this stored procedure to use native compilation.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_ondisk  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
AS BEGIN  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  WHERE  s.SalesOrderId = @SalesOrderId  
      OR s.SalesOrderDetailId = @SalesOrderDetailId  
      OR s.CarrierTrackingNumber = @CarrierTrackingNumber  
      OR s.ProductID = @ProductId  
      OR (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
END  
GO  
```  
  
 <span data-ttu-id="93da7-124">Après la conversion, la table et le schéma de la procédure stockée seront comme suit.</span><span class="sxs-lookup"><span data-stu-id="93da7-124">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesOrderDetailType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailTempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  recordcount int not null  
  INDEX ix_fuzzySearchSalesOrderDetailTempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_inmem  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.fuzzySearchSalesOrderDetailType  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderId = @SalesOrderId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderDetailId = @SalesOrderDetailId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.CarrierTrackingNumber COLLATE Latin1_General_BIN2 = @CarrierTrackingNumber COLLATE Latin1_General_BIN2   
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.ProductID = @ProductId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
  
  -- After the above statements, there will be duplicates inside @retValue  
  -- Delete the duplicates from @retValue  
  DECLARE @duplicates Sales.fuzzySearchSalesOrderDetailTempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, recordcount)   
  SELECT SalesOrderId, SalesOrderDetailId, COUNT(*) AS recordCount  
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId  
  
  -- Now we have one row per pair  
  -- clear and rebuild the result set  
  DELETE FROM @retValue  
  
  INSERT INTO @retValue  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates d ON s.SalesOrderId = d.SalesOrderId AND s.SalesOrderDetailId = d.SalesOrderDetailId  
  
  -- After this every pair of (SalesOrderId, SalesOrderDetailId) in @retValue should be unique.  
  SELECT SalesorderId, SalesOrderDetailId, ModifiedDate FROM @retValue  
END  
GO  
```  
  
## <a name="or-operator-in-join-condition"></a><span data-ttu-id="93da7-125">Opérateur OR dans une condition JOIN</span><span class="sxs-lookup"><span data-stu-id="93da7-125">OR Operator in JOIN Condition</span></span>  
 <span data-ttu-id="93da7-126">Si vous avez un opérateur OR dans une condition JOIN d'une instruction SELECT, vous pouvez utiliser la méthode suivante pour simuler son comportement.</span><span class="sxs-lookup"><span data-stu-id="93da7-126">If you have an OR operator in a JOIN condition of a SELECT statement, you may use the following approach to simulate its behavior.</span></span> <span data-ttu-id="93da7-127">Si vous avez plusieurs opérateurs OR dans une condition JOIN, ou si vous avez plusieurs conditions JOIN avec des opérateurs OR, vous devrez peut-être effectuer cette opération plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="93da7-127">If you have more than one OR operator in a JOIN condition or you have multiple JOIN condition with OR operators, you may need to do this more than once.</span></span>  
  
 <span data-ttu-id="93da7-128">Si vous avez des conditions OUTER JOIN, vous pouvez combiner cette solution de contournement avec celle pour les conditions OUTER JOIN.</span><span class="sxs-lookup"><span data-stu-id="93da7-128">If you have OUTER JOIN conditions, you may combine this workaround with the workaround for OUTER JOIN conditions.</span></span>  
  
1.  <span data-ttu-id="93da7-129">Créez une variable de table mémoire optimisée avec le schéma approprié.</span><span class="sxs-lookup"><span data-stu-id="93da7-129">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="93da7-130">Cela nécessite un type de table mémoire optimisée prédéfini.</span><span class="sxs-lookup"><span data-stu-id="93da7-130">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="93da7-131">Séparez le prédicat dans la condition de jointure en deux parties selon les prédicats joints par l'opérateur OR.</span><span class="sxs-lookup"><span data-stu-id="93da7-131">Separate the predicate in the JOIN condition into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="93da7-132">Si vous avez plusieurs conditions JOIN, vous devrez peut-être effectuer cette opération pour chaque condition JOIN, puis créer un jeu de combinaisons des fragments résultants.</span><span class="sxs-lookup"><span data-stu-id="93da7-132">If you have multiple JOIN conditions, you may need to do this for each JOIN condition and then create a set of combinations of the resulting fragments.</span></span> <span data-ttu-id="93da7-133">Par exemple, si vous avez trois conditions JOIN avec un opérateur OR dans chaque condition JOIN, vous pouvez avoir 2x2x2=8 prédicats.</span><span class="sxs-lookup"><span data-stu-id="93da7-133">For example, if you have three JOIN conditions with one OR operator in each JOIN condition, you may have 2x2x2=8 predicates.</span></span>  
  
3.  <span data-ttu-id="93da7-134">Pour chaque prédicat généré par l'étape 2, créez une requête qui insèrera son résultat dans la variable de table mémoire optimisée créée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="93da7-134">For each predicate produced by Step 2, create a query that will insert its result into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="93da7-135">Si nécessaire, supprimez les doublons de la variable de table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="93da7-135">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="93da7-136">Utilisez le contenu de la variable de table mémoire optimisée comme résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="93da7-136">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="93da7-137">L'exemple suivant utilise les tables de la base de données AdventureWorks2012 mises à jour pour [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93da7-137">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="93da7-138">Pour télécharger les fichiers de cet exemple, accédez à [bases de données AdventureWorks-2012, 2008R2 et 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="93da7-138">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="93da7-139">Pour appliquer [!INCLUDE[hek_2](../includes/hek-2-md.md)] l’exemple de code à AdventureWorks2012, accédez à [SQL Server exemple d’OLTP en mémoire 2014](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="93da7-139">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="93da7-140">Ajoutez la procédure stockée suivante à la base de données.</span><span class="sxs-lookup"><span data-stu-id="93da7-140">Add the following stored procedure to the database.</span></span> <span data-ttu-id="93da7-141">Nous convertirons cette procédure stockée pour utiliser la compilation native.</span><span class="sxs-lookup"><span data-stu-id="93da7-141">We will convert this stored procedure to use native compilation.</span></span> <span data-ttu-id="93da7-142">Cet exemple utilise des conditions INNER JOIN.</span><span class="sxs-lookup"><span data-stu-id="93da7-142">This sample uses INNER JOIN conditions.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_ondisk  
  @SpecialOfferId int  
AS BEGIN  
  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  JOIN Sales.SpecialOffer_onDisk offer   
    ON s.SpecialOfferID = offer.SpecialOfferID   
    OR s.ProductID IN (SELECT ProductId FROM Sales.SpecialOfferProduct sop WHERE sop.SpecialOfferID = @SpecialOfferId)  
END  
```  
  
 <span data-ttu-id="93da7-143">Après la conversion, la table et le schéma de la procédure stockée seront comme suit.</span><span class="sxs-lookup"><span data-stu-id="93da7-143">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_Type AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesSpecialOffers_Type NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_TempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  recordcount int null  
  INDEX ix_fuzzySearchSalesSpecialOffers_TempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_inmem  
  @SpecialOfferId int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.FuzzySearchSalesSpecialOffers_Type  
  
  -- Find all special offers matching the conditions  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOffer_inmem offer   
    ON s.SpecialOfferID = offer.SpecialOfferID  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOfferProduct_inmem sop   
    ON sop.SpecialOfferId = @SpecialOfferId AND s.ProductID = sop.ProductId  
  
  -- Now we need to remove the duplicates from @matchingSpecialOffers  
  DECLARE @duplicates Sales.fuzzySearchSalesSpecialOffers_TempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, SpecialOfferid, recordcount)  
  SELECT SalesOrderId, SalesOrderDetailId, SpecialOfferId, COUNT(*)   
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId, SpecialOfferId  
  
  -- now there should be no duplicates within @duplicate  
  -- use @duplicate for join.  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates offer   
    ON    s.SalesOrderId = offer.SalesOrderId   
      AND s.SalesOrderDetailId = offer.SalesOrderDetailID   
      AND s.SpecialOfferId = offer.SpecialOfferId  
END  
GO  
```  
  
## <a name="side-effects"></a><span data-ttu-id="93da7-144">Effets secondaires</span><span class="sxs-lookup"><span data-stu-id="93da7-144">Side Effects</span></span>  
 <span data-ttu-id="93da7-145">Si vous avez plusieurs opérateurs OR dans la clause WHERE ou la condition JOIN, le nombre de requêtes que vous devez exécuter pour simuler le comportement peut augmenter de manière exponentielle.</span><span class="sxs-lookup"><span data-stu-id="93da7-145">If you have more than one OR operator in the WHERE clause or JOIN condition, the number of queries you need to execute to simulate the behavior may increase exponentially.</span></span> <span data-ttu-id="93da7-146">Cela peut ralentir les performances des requêtes et augmenter l'utilisation de la mémoire à cause de la nécessité d'utiliser des variables de table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="93da7-146">This may slow down query performance and may increase memory usage due to the need to use memory-optimized table variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93da7-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93da7-147">See Also</span></span>  
 [<span data-ttu-id="93da7-148">Problèmes de migration pour les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="93da7-148">Migration Issues for Natively Compiled Stored Procedures</span></span>](../relational-databases/in-memory-oltp/migration-issues-for-natively-compiled-stored-procedures.md)  
  
