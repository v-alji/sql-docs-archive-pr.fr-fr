---
title: Migration des contraintes de vérification et de clé étrangère | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: e0a1a1e4-0062-4872-93c3-cd91b7a43c23
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4bacd7a9c5c00fc6abbb763eaa02dca9493fa513
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610833"
---
# <a name="migrating-check-and-foreign-key-constraints"></a><span data-ttu-id="8c00b-102">Migration des contraintes de validation et de clé étrangère</span><span class="sxs-lookup"><span data-stu-id="8c00b-102">Migrating Check and Foreign Key Constraints</span></span>
  <span data-ttu-id="8c00b-103">Les contraintes de validation et de clés étrangères ne sont pas prises en charge dans [!INCLUDE[hek_2](../includes/hek-2-md.md)] dans [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c00b-103">Check and foreign key constraints are not supported in [!INCLUDE[hek_2](../includes/hek-2-md.md)] in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="8c00b-104">Ces constructions sont généralement utilisées pour appliquer l'intégrité logique des données au schéma et peuvent être importantes pour conserver la précision fonctionnelle des applications.</span><span class="sxs-lookup"><span data-stu-id="8c00b-104">These constructs are usually used to enforce logical data integrity in the schema and can be important to maintaining the functional correctness of applications.</span></span>  
  
 <span data-ttu-id="8c00b-105">Les contrôles d'intégrité logique sur une table, comme les contraintes de validation et de clés étrangères, nécessitent un traitement supplémentaire sur les transactions et doivent généralement être évités pour les applications sensibles aux performances.</span><span class="sxs-lookup"><span data-stu-id="8c00b-105">Logical integrity checks on a table such as check and foreign key constraints require additional processing on transactions and should generally be avoided for performance-sensitive applications.</span></span> <span data-ttu-id="8c00b-106">Toutefois, si de tels contrôles sont cruciaux pour votre application, il existe deux solutions.</span><span class="sxs-lookup"><span data-stu-id="8c00b-106">However, if such checks are crucial to your application, there exist two workarounds.</span></span>  
  
## <a name="checking-constraints-after-an-insert-update-or-delete-operation"></a><span data-ttu-id="8c00b-107">Vérification des contraintes après une opération d'insertion, de mise à jour ou de suppression</span><span class="sxs-lookup"><span data-stu-id="8c00b-107">Checking Constraints After an Insert, Update, or Delete Operation</span></span>  
 <span data-ttu-id="8c00b-108">Cette solution est optimiste, basée sur l'hypothèse que la majorité des modifications n'enfreint pas les contraintes.</span><span class="sxs-lookup"><span data-stu-id="8c00b-108">This workaround is optimistic, based on the assumption that the majority of changes do not violate the constraints.</span></span> <span data-ttu-id="8c00b-109">Avec cette solution, les données sont modifiées avant que les contraintes ne soient évaluées.</span><span class="sxs-lookup"><span data-stu-id="8c00b-109">In this workaround, data is modified first before the constraints are evaluated.</span></span> <span data-ttu-id="8c00b-110">Si une contrainte n'est pas respectée, elle est détectée, mais la modification n'est pas annulée.</span><span class="sxs-lookup"><span data-stu-id="8c00b-110">If a constraint is violated, it would be detected, but the change will not be rolled back.</span></span>  
  
 <span data-ttu-id="8c00b-111">L'avantage de cette solution est qu'elle présente un impact minimal sur les performances, car la modification de données n'est pas bloquée par les vérifications de contraintes.</span><span class="sxs-lookup"><span data-stu-id="8c00b-111">This workaround has the advantage of having minimal impact on performance because data modification is not blocked by constraint checks.</span></span> <span data-ttu-id="8c00b-112">Toutefois, si une modification qui enfreint une ou plusieurs contraintes est apportée, le processus d'annulation de cette modification peut prendre beaucoup de temps.</span><span class="sxs-lookup"><span data-stu-id="8c00b-112">However, if a change that violates one or more constraints does occur, the process to roll back that change could take a long time.</span></span>  
  
## <a name="enforcing-constraints-before-an-insert-update-or-delete-operation"></a><span data-ttu-id="8c00b-113">Application des contraintes avant une opération d'insertion, de mise à jour ou de suppression</span><span class="sxs-lookup"><span data-stu-id="8c00b-113">Enforcing Constraints Before an Insert, Update, or Delete Operation</span></span>  
 <span data-ttu-id="8c00b-114">Cette solution émule le comportement des contraintes [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c00b-114">This workaround emulates the behavior of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] constraints.</span></span> <span data-ttu-id="8c00b-115">Les contraintes sont vérifiées avant la modification des données et mettent fin à la transaction si un contrôle échoue.</span><span class="sxs-lookup"><span data-stu-id="8c00b-115">The constraints are checked before data modification occurs and will terminate the transaction if a check fails.</span></span> <span data-ttu-id="8c00b-116">Cette méthode implique une altération des performances lors de la modification de données, mais garantit que les données d'une table respectent toujours les contraintes.</span><span class="sxs-lookup"><span data-stu-id="8c00b-116">This method incurs a performance penalty on data modifications, but ensures that data inside a table always satisfies the constraints.</span></span>  
  
 <span data-ttu-id="8c00b-117">Utilisez cette solution lorsque l'intégrité logique des données s'avère indispensable pour la précision et que des modifications risquant d'enfreindre une contrainte sont probables.</span><span class="sxs-lookup"><span data-stu-id="8c00b-117">Use this workaround when logical data integrity is crucial to correctness and modifications that violate a constraint are likely.</span></span> <span data-ttu-id="8c00b-118">Cependant, pour garantir l'intégrité, toutes les modifications de données doivent se produire dans les procédures stockées qui incluent ces mises en conformité.</span><span class="sxs-lookup"><span data-stu-id="8c00b-118">However, to guarantee integrity, all data modifications must occur through stored procedures that include these enforcements.</span></span> <span data-ttu-id="8c00b-119">Les modifications via des requêtes ad hoc et autres procédures stockées n'appliqueront pas ces contraintes et, par conséquent, peuvent ne pas les respecter, sans avertissement.</span><span class="sxs-lookup"><span data-stu-id="8c00b-119">Modifications through ad-hoc queries and other stored procedures will not enforce these constraints and therefore may violate them with no warning.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="8c00b-120">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="8c00b-120">Sample Code</span></span>  
 <span data-ttu-id="8c00b-121">Les exemples suivants sont basés sur la base de données AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="8c00b-121">The following samples are based on the AdventureWorks2012 database.</span></span> <span data-ttu-id="8c00b-122">Plus précisément, ces exemples sont basés sur la table [Sales].[SalesOrderDetail] et ses contraintes de validation et de clés étrangères associées, en plus de l'index unique.</span><span class="sxs-lookup"><span data-stu-id="8c00b-122">Specifically, these samples are based on the [Sales].[SalesOrderDetail] table and its associated check and foreign key constraints in addition to the unique index.</span></span>  
  
 <span data-ttu-id="8c00b-123">Les procédures stockées spécifiées ici concernent les opérations d'incrustation uniquement.</span><span class="sxs-lookup"><span data-stu-id="8c00b-123">The stored procedures specified here are for inset operations only.</span></span> <span data-ttu-id="8c00b-124">Les procédures stockées pour les opérations de mise à jour et de suppression présentent normalement des structures identiques.</span><span class="sxs-lookup"><span data-stu-id="8c00b-124">Stored procedures for update and delete operations should have similar structures.</span></span>  
  
## <a name="table-definition-for-the-workarounds"></a><span data-ttu-id="8c00b-125">Définition de table pour les solutions de contournement</span><span class="sxs-lookup"><span data-stu-id="8c00b-125">Table Definition for the Workarounds</span></span>  
 <span data-ttu-id="8c00b-126">Avant la conversion en table mémoire optimisée, la définition de [Sales].[SalesOrderDetail] se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="8c00b-126">Before converting to a memory-optimized table, the definition for [Sales].[SalesOrderDetail] is as follows:</span></span>  
  
```sql  
USE [AdventureWorks2012]  
GO  
  
CREATE TABLE [Sales].[SalesOrderDetail]([SalesOrderID] [int] NOT NULL,  
   [SalesOrderDetailID] [int] IDENTITY(1,1) NOT NULL,  
   [CarrierTrackingNumber] [nvarchar](25) NULL,  
   [OrderQty] [smallint] NOT NULL,  
   [ProductID] [int] NOT NULL,  
   [SpecialOfferID] [int] NOT NULL,  
   [UnitPrice] [money] NOT NULL,  
   [UnitPriceDiscount] [money] NOT NULL CONSTRAINT [DF_SalesOrderDetail_UnitPriceDiscount]  DEFAULT ((0.0)),  
   [LineTotal]  AS (isnull(([UnitPrice]*((1.0)-[UnitPriceDiscount]))*[OrderQty],(0.0))),  
   [rowguid] [uniqueidentifier] ROWGUIDCOL  NOT NULL CONSTRAINT [DF_SalesOrderDetail_rowguid]  DEFAULT (newid()),  
   [ModifiedDate] [datetime] NOT NULL CONSTRAINT [DF_SalesOrderDetail_ModifiedDate]  DEFAULT (getdate()),  
 CONSTRAINT [PK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID] PRIMARY KEY CLUSTERED   
(  
   [SalesOrderID] ASC,  
   [SalesOrderDetailID] ASC  
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]  
  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID] FOREIGN KEY([SalesOrderID])  
REFERENCES [Sales].[SalesOrderHeader] ([SalesOrderID])  
ON DELETE CASCADE  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID] FOREIGN KEY([SpecialOfferID], [ProductID])  
REFERENCES [Sales].[SpecialOfferProduct] ([SpecialOfferID], [ProductID])  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_OrderQty] CHECK  (([OrderQty]>(0)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_OrderQty]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_UnitPrice] CHECK  (([UnitPrice]>=(0.00)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_UnitPrice]  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail]  WITH CHECK ADD  CONSTRAINT [CK_SalesOrderDetail_UnitPriceDiscount] CHECK  (([UnitPriceDiscount]>=(0.00)))  
GO  
  
ALTER TABLE [Sales].[SalesOrderDetail] CHECK CONSTRAINT [CK_SalesOrderDetail_UnitPriceDiscount]  
GO  
```  
  
 <span data-ttu-id="8c00b-127">Suite à la conversion en table mémoire optimisée, la définition de [Sales].[SalesOrderDetail] se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="8c00b-127">After converting to a memory-optimized table, the definition for [Sales].[SalesOrderDetail] is as follows:</span></span>  
  
 <span data-ttu-id="8c00b-128">Notez que rowguid n'est plus un ROWGUIDCOL, car il n'est pas pris en charge dans [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c00b-128">Note that rowguid is no longer a ROWGUIDCOL as it is not supported in [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="8c00b-129">La colonne a été supprimée.</span><span class="sxs-lookup"><span data-stu-id="8c00b-129">The column has been removed.</span></span> <span data-ttu-id="8c00b-130">En outre, LineTotal est une colonne calculée et n'est pas abordé dans cet article ; il a donc également été supprimé.</span><span class="sxs-lookup"><span data-stu-id="8c00b-130">In addition, LineTotal is a computed column and out of scope for this article, so it also has been removed.</span></span>  
  
```sql  
USE [AdventureWorks2012]  
GO  
  
CREATE TABLE [Sales].[SalesOrderDetail]([SalesOrderID] [int] NOT NULL,  
   [SalesOrderDetailID] [int] IDENTITY(1,1) NOT NULL,  
   [CarrierTrackingNumber] [nvarchar](25) NULL,  
   [OrderQty] [smallint] NOT NULL,  
   [ProductID] [int] NOT NULL,  
   [SpecialOfferID] [int] NOT NULL,  
   [UnitPrice] [money] NOT NULL,  
   [UnitPriceDiscount] [money] NOT NULL CONSTRAINT [DF_SalesOrderDetail_UnitPriceDiscount]  DEFAULT ((0.0)),  
   [ModifiedDate] [datetime] NOT NULL CONSTRAINT [DF_SalesOrderDetail_ModifiedDate]  DEFAULT (getdate()),  
   CONSTRAINT [PK_SalesOrderDetail_SalesOrderID_SalesOrderDetailID] PRIMARY KEY NONCLUSTERED   
   (  
      [SalesOrderID] ASC,  
      [SalesOrderDetailID] ASC  
   ),  
   INDEX [AK_SalesOrderDetail_rowguid] NONCLUSTERED HASH ([rowguid]) WITH (BUCKET_COUNT = 1048576),  
   INDEX [IX_SalesOrderDetail_ProductId] NONCLUSTERED ([ProductId] ASC)) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
  
GO  
```  
  
## <a name="checking-constraints-after-an-insert-update-or-delete-operation"></a><span data-ttu-id="8c00b-131">Vérification des contraintes après une opération d'insertion, de mise à jour ou de suppression</span><span class="sxs-lookup"><span data-stu-id="8c00b-131">Checking Constraints After an Insert, Update, or Delete Operation</span></span>  
  
```sql  
USE AdventureWorks2012  
GO  
  
CREATE PROCEDURE Sales.usp_insert_SalesOrderDetails   
   @SalesOrderId int, @CarrierTrackingNumber nvarchar(25) = null, @OrderQty smallint, @ProductId int, @SpecialOfferID int,   
   @UnitPrice money, @UnitPriceDiscount money = 0.00, @ModifiedDate datetime = null  
AS  
BEGIN  
BEGIN TRANSACTION   
   -- handle defaults for the insert.  
   -- This is to make the insert logic less complex. Default constraints on the table should be in sync with this logic.  
   -- Conversely, you can write an INSERT statement for each case where one or more values for the three columns with default constraints are not specified.  
   IF @ModifiedDate = null SET @ModifiedDate = GETDATE()  
  
   -- Insert the row.  
   INSERT INTO Sales.SalesOrderDetail   
      (SalesOrderID, CarrierTrackingNumber, OrderQty, ProductID, SpecialOfferID, UnitPrice, UnitPriceDiscount, ModifiedDate)  
   VALUES   
      (@SalesOrderId, @CarrierTrackingNumber, @OrderQty, @ProductID, @SpecialOfferID, @UnitPrice, @UnitPriceDiscount, , @ModifiedDate)   
  
   -- Now handle constraints  
   DECLARE @violations TABLE   
   (   
      ConstraintName sysname,  
      ViolatedValue1 sql_variant,  
      ViolatedValue2 sql_variant  
   )  
  
   -- FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID  
   IF NOT EXISTS (SELECT soh.SalesOrderId AS [Exists] FROM Sales.SalesOrderHeader soh WHERE soh.SalesOrderID = @SalesOrderId)   
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID', @SalesOrderId, NULL)  
   -- FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID  
   IF NOT EXISTS (SELECT sop.SpecialOfferID, sop.ProductID FROM [Sales].[SpecialOfferProduct] sop WHERE sop.SpecialOfferID = @SpecialOfferID AND sop.ProductID = @ProductId)  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID', @SpecialOfferId, @ProductId)  
   -- CK_SalesOrderDetail_OrderQty  
   IF NOT @OrderQty > 0   
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_OrderQty', @OrderQty, NULL)  
   -- CK_SalesOrderDetail_UnitPrice  
   IF NOT @UnitPrice >= 0.00  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_UnitPrice', @UnitPrice, NULL)  
   -- CK_SalesOrderDetail_UnitPriceDiscout  
   IF NOT @UnitPriceDiscount >= 0.00  
      INSERT INTO @violations (ConstraintName, ViolatedValue1, ViolatedValue2)   
      VALUES (N'CK_SalesOrderDetail_UnitPriceDiscount', @UnitPriceDiscount, NULL)  
  
   -- Return a rowset containing violated constraints. On an item that doesn't violate anything, should return an empty rowset.  
   SELECT ConstraintName, ViolatedValue1, ViolatedValue2 FROM @violations  
   COMMIT TRANSACTION  
END  
```  
  
## <a name="enforcing-constraints-before-an-insert-update-or-delete-operation"></a><span data-ttu-id="8c00b-132">Application des contraintes avant une opération d'insertion, de mise à jour ou de suppression</span><span class="sxs-lookup"><span data-stu-id="8c00b-132">Enforcing Constraints Before an Insert, Update or Delete Operation</span></span>  
  
```sql  
USE AdventureWorks2012  
GO  
  
CREATE PROCEDURE Sales.usp_insert_SalesOrderDetails   
   @SalesOrderId int, @CarrierTrackingNumber nvarchar(25) = null, @OrderQty smallint, @ProductId int, @SpecialOfferID int,   
   @UnitPrice money, @UnitPriceDiscount money = 0.00, @ModifiedDate datetime = null  
AS  
BEGIN  
BEGIN TRY  
   BEGIN TRANSACTION  
   -- Verify the constraints first.  
   -- FK_SalesOrderDetail_SalesOrderHeader_SalesOrderID  
   IF NOT EXISTS (SELECT soh.SalesOrderId FROM Sales.SalesOrderHeader soh WHERE soh.SalesOrderID = @SalesOrderId)   
      THROW 50547, N'This SalesOrderId does not exist in SalesOrderHeader', 1  
   -- FK_SalesOrderDetail_SpecialOfferProduct_SpecialOfferIDProductID  
   IF NOT EXISTS (SELECT sop.SpecialOfferID, sop.ProductID FROM [Sales].[SpecialOfferProduct] sop WHERE sop.SpecialOfferID = @SpecialOfferID AND sop.ProductID = @ProductId)  
      THROW 50547, N'This combination of SpecialOfferID and ProductID does not exist in SpecialOfferProduct', 1   
   -- CK_SalesOrderDetail_OrderQty  
   IF NOT @OrderQty > 0   
      THROW 50547, N'OrderQty must be greater than zero.', 1  
   -- CK_SalesOrderDetail_UnitPrice  
   IF NOT @UnitPrice >= 0.00  
      THROW 50547, N'UnitPrice cannot be negative.', 1  
   -- CK_SalesOrderDetail_UnitPriceDiscout  
   IF NOT @UnitPriceDiscount >= 0.00  
      THROW 50547, N'UnitPriceDiscount cannot be negative', 1  
  
   -- All verifications have now passed. Proceed to insert.  
  
   -- handle defaults for the insert.  
   -- This is to make the insert logic less complex. Default constraints on the table should be in sync with this logic.  
   -- Conversely, you can write an INSERT statement for each case where one or more values for the three columns with default constraints are not specified.  
  
   IF @ModifiedDate = null SET @ModifiedDate = GETDATE()  
  
   -- Calculate computed columnn and store it.  
   DECLARE @LineTotal numeric(38, 6)  
   SET @LineTotal = (isnull((@UnitPrice * ((1.0) - @UnitPriceDiscount)) * @OrderQty, (0.0)))  
  
   -- Insert the row.  
   INSERT INTO Sales.SalesOrderDetail   
      (SalesOrderID, CarrierTrackingNumber, OrderQty, ProductID, SpecialOfferID, UnitPrice, UnitPriceDiscount, ModifiedDate)  
   VALUES   
      (@SalesOrderId, @CarrierTrackingNumber, @OrderQty, @ProductID, @SpecialOfferID, @UnitPrice, @UnitPriceDiscount, @ModifiedDate)  
   COMMIT TRANSACTION  
END TRY  
BEGIN CATCH  
   IF @@TRANCOUNT > 0  
      ROLLBACK TRANSACTION  
      THROW;  
END CATCH  
END  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c00b-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c00b-133">See Also</span></span>  
 [<span data-ttu-id="8c00b-134">Migration vers OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="8c00b-134">Migrating to In-Memory OLTP</span></span>](../relational-databases/in-memory-oltp/migrating-to-in-memory-oltp.md)  
  
  
