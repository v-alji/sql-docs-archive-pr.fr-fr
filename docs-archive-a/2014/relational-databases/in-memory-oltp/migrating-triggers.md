---
title: Migration de déclencheurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: ad5385c5-5a50-40ca-a319-97d5606b8511
author: rothja
ms.author: jroth
ms.openlocfilehash: 25965e7cce84b0dcfcd3b6ce6176e8ad3ddabc6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709447"
---
# <a name="migrating-triggers"></a><span data-ttu-id="1d77c-102">Migration de déclencheurs</span><span class="sxs-lookup"><span data-stu-id="1d77c-102">Migrating Triggers</span></span>
  <span data-ttu-id="1d77c-103">Cette rubrique présente les déclencheurs DDL et DML et les tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="1d77c-103">This topic discusses DDL and DML triggers and memory-optimized tables.</span></span>  
  
 <span data-ttu-id="1d77c-104">Les déclencheurs LOGON sont des déclencheurs définis pour se déclencher sur les événements LOGON.</span><span class="sxs-lookup"><span data-stu-id="1d77c-104">LOGON triggers are triggers defined to fire on LOGON events.</span></span> <span data-ttu-id="1d77c-105">Ces déclencheurs n'affectent pas les tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="1d77c-105">LOGON triggers do not affect memory-optimized tables.</span></span>  
  
## <a name="ddl-triggers"></a><span data-ttu-id="1d77c-106">Déclencheurs DDL</span><span class="sxs-lookup"><span data-stu-id="1d77c-106">DDL Triggers</span></span>  
 <span data-ttu-id="1d77c-107">Les déclencheurs DDL sont des déclencheurs définis pour se déclencher lorsqu'une instruction CREATE, ALTER, DROP, GRANT, DENY, REVOKE ou UPDATE STATISTICS est exécutée sur la base de données ou sur le serveur sur lequel elle est définie.</span><span class="sxs-lookup"><span data-stu-id="1d77c-107">DDL triggers are triggers defined to fire when a CREATE, ALTER, DROP, GRANT, DENY, REVOKE, or UPDATE STATISTICS statement is executed on the database or server on which it is defined.</span></span>  
  
 <span data-ttu-id="1d77c-108">Il est impossible de créer des tables mémoire optimisées si la base de données ou le serveur contient un ou plusieurs déclencheurs DDL définis sur l'événement CREATE_TABLE ou un groupe d'événements qui inclut cet événement.</span><span class="sxs-lookup"><span data-stu-id="1d77c-108">You cannot create memory-optimized tables if the database or server has one or more DDL trigger defined on CREATE_TABLE or any event group that includes it.</span></span> <span data-ttu-id="1d77c-109">Il est impossible de supprimer une table mémoire optimisée si la base de données ou le serveur contient un ou plusieurs déclencheurs DDL définis sur l'événement DROP_TABLE ou un groupe d'événements qui inclut cet événement.</span><span class="sxs-lookup"><span data-stu-id="1d77c-109">You cannot drop a memory-optimized table if the database or server has one or more DDL trigger defined on DROP_TABLE or any event group that includes it.</span></span>  
  
 <span data-ttu-id="1d77c-110">Il est impossible de créer des procédures stockées compilées en mode natif s'il existe un ou plusieurs déclencheurs DDL définis sur les événements CREATE_PROCEDURE, DROP_PROCEDURE ou un groupe d'événements qui inclut ces événements.</span><span class="sxs-lookup"><span data-stu-id="1d77c-110">You cannot create natively compiled stored procedures if there are one or more DDL triggers on CREATE_PROCEDURE, DROP_PROCEDURE, or any event group that includes those events.</span></span>  
  
## <a name="dml-triggers"></a><span data-ttu-id="1d77c-111">Déclencheurs DML</span><span class="sxs-lookup"><span data-stu-id="1d77c-111">DML Triggers</span></span>  
 <span data-ttu-id="1d77c-112">Les déclencheurs DML ne peuvent pas être définis sur les tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="1d77c-112">DML triggers cannot be defined on memory-optimized tables.</span></span> <span data-ttu-id="1d77c-113">Cependant, OLTP en mémoire vous permet d'obtenir un effet similaire aux déclencheurs DML si vous utilisez explicitement des procédures stockées pour insérer, mettre à jour ou supprimer des données.</span><span class="sxs-lookup"><span data-stu-id="1d77c-113">However, In-Memory OLTP allows you to achieve an effect similar to DML triggers if you explicitly use stored procedures to insert, update, or delete data.</span></span> <span data-ttu-id="1d77c-114">Si votre système contient des requêtes ad hoc, convertissez-les de façon à utiliser ces procédures stockées à la place afin de simuler l'effet des déclencheurs DML.</span><span class="sxs-lookup"><span data-stu-id="1d77c-114">If your system contains ad-hoc queries, convert them to use these stored procedures instead to simulate the effect of DML triggers.</span></span>  
  
 <span data-ttu-id="1d77c-115">Selon l'événement déclencheur (FOR/AFTER ou INSTEAD OF), vous pouvez inclure le contenu du déclencheur dans la procédure stockée appropriée qui exécute l'instruction INSERT, UPDATE ou DELETE sur cette table.</span><span class="sxs-lookup"><span data-stu-id="1d77c-115">Depending on the trigger event (FOR/AFTER or INSTEAD OF), you may include the content of the trigger in the appropriate stored procedure that performs INSERT, UPDATE, or DELETE on that table.</span></span> <span data-ttu-id="1d77c-116">Par exemple, lorsque vous migrez un déclencheur AFTER INSERT, vous pouvez modifier la procédure stockée qui effectue l'opération d'insertion en ajoutant le contenu du déclencheur après l'instruction INSERT appropriée.</span><span class="sxs-lookup"><span data-stu-id="1d77c-116">For example, when migrating an AFTER INSERT trigger, you could alter the stored procedure that performs the insert operation by including the content of the trigger after the appropriate INSERT statement.</span></span>  
  
 <span data-ttu-id="1d77c-117">Utilisez une procédure stockée interprétée ou une procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="1d77c-117">You can use an interpreted stored procedure or a natively compiled stored procedure.</span></span> <span data-ttu-id="1d77c-118">La plupart les constructions [!INCLUDE[tsql](../../includes/tsql-md.md)] dans une procédure stockée interprétée s'exécutent sur une table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="1d77c-118">Most [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs in an interpreted stored procedure can execute on a memory-optimized table.</span></span> <span data-ttu-id="1d77c-119">Toutefois, seul un sous-ensemble de constructions [!INCLUDE[tsql](../../includes/tsql-md.md)] est pris en charge dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="1d77c-119">However, only a subset of [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs are supported in natively compiled stored procedures.</span></span> <span data-ttu-id="1d77c-120">Pour plus d'informations sur la prise en charge de [!INCLUDE[tsql](../../includes/tsql-md.md)] sur les tables mémoire optimisées, consultez [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1d77c-120">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support on memory-optimized tables, see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span> <span data-ttu-id="1d77c-121">Pour plus d'informations sur la prise en charge de [!INCLUDE[tsql](../../includes/tsql-md.md)] dans les procédures stockées compilées en mode natif, consultez [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="1d77c-121">For information on [!INCLUDE[tsql](../../includes/tsql-md.md)] support in natively compiled stored procedures, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="1d77c-122">Voici un exemple simple de simulation du comportement des déclencheurs DML sur une table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="1d77c-122">The following is a simple example of simulating DML trigger behavior on a memory-optimized table.</span></span>  
  
 <span data-ttu-id="1d77c-123">La base de données contient les objets suivants, définis dans un script en tant qu'instructions CREATE TABLE, CREATE TRIGGER et CREATE PROCEDURE :</span><span class="sxs-lookup"><span data-stu-id="1d77c-123">The database contains the following objects, scripted as CREATE TABLE, CREATE TRIGGER, and CREATE PROCEDURE statements:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null primary key,  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
)  
GO  
  
CREATE TRIGGER tr_order_details_insteadof_insert  
ON OrderDetails  
INSTEAD OF INSERT AS  
BEGIN  
   DECLARE @pid int, @qty_buy int, @qty_remain int  
   SELECT @pid = ProductId, @qty_buy = Quantity FROM inserted  
   SELECT @qty_remain = Quantity FROM Inventory WHERE ProductId = @pid  
   IF (@qty_remain <= @qty_buy)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      SELECT OrderId, ProductId, SalePrice, Quantity, Total FROM inserted  
      UPDATE Inventory SET Quantity = Quantity - @qty_buy WHERE ProductId = @pid  
   END  
END  
GO  
  
CREATE TRIGGER tr_order_details_after_update  
ON OrderDetails  
AFTER UPDATE AS  
BEGIN  
   INSERT INTO UpdateNotifications (OrderId, UpdateTime) SELECT OrderId, GETDATE() FROM inserted     
END  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
AS BEGIN  
   INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
   VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
AS BEGIN  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
END  
GO  
```  
  
 <span data-ttu-id="1d77c-124">Les objets suivants sont fonctionnellement équivalents à l'état de prémigration :</span><span class="sxs-lookup"><span data-stu-id="1d77c-124">The following objects are functionally equivalent to the pre-migration state:</span></span>  
  
```sql  
CREATE TABLE OrderDetails  
(  
   OrderId int not null PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 1048576),  
   ProductId int not null,  
   SalePrice money not null,  
   Quantity int not null,  
   Total money not null,  
   IsDeleted bit not null DEFAULT (0)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE Inventory  
(  
   ProductId int not null PRIMARY KEY NONCLUSTERED,  
   Quantity int not null  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE TABLE UpdateNotifications  
(  
   OrderId int not null,  
   UpdateTime datetime2 not null  
   CONSTRAINT pk_updateNotifications PRIMARY KEY NONCLUSTERED (OrderId, UpdateTime)  
) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
GO  
  
CREATE PROCEDURE sp_insert_order_details   
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   DECLARE @qty_remain int  
   SELECT @qty_remain = Quantity FROM dbo.Inventory WHERE ProductId = @ProductId  
   IF (@qty_remain <= @Quantity)  
      THROW 51000, N'Insufficient inventory!', 1  
   ELSE  
   BEGIN  
      INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)   
      VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
      UPDATE dbo.Inventory SET Quantity = Quantity - @Quantity WHERE ProductId = @ProductId  
   END  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
   @OrderId int, @ProductId int, @SalePrice money, @Quantity int, @Total money  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'English')  
   UPDATE dbo.OrderDetails   
   SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
   WHERE OrderId = @OrderId  
   INSERT INTO dbo.UpdateNotifications (OrderId, UpdateTime) VALUES (@OrderId, GETDATE())  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d77c-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1d77c-125">See Also</span></span>  
 [<span data-ttu-id="1d77c-126">Migration vers OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="1d77c-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
