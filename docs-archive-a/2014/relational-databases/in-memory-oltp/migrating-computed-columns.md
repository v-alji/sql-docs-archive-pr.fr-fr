---
title: Migration de colonnes calculées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 64a9eade-22c3-4a9d-ab50-956219e08df1
author: rothja
ms.author: jroth
ms.openlocfilehash: feb50ef64f42d95913ad4e13f9a79e6e0e4ecad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709456"
---
# <a name="migrating-computed-columns"></a><span data-ttu-id="03f08-102">Migration de colonnes calculées</span><span class="sxs-lookup"><span data-stu-id="03f08-102">Migrating Computed Columns</span></span>
  <span data-ttu-id="03f08-103">Les colonnes calculées ne sont pas prises en charge dans les tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="03f08-103">Computed columns are not supported in memory-optimized tables.</span></span> <span data-ttu-id="03f08-104">Toutefois, vous pouvez simuler une colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="03f08-104">However, you can simulate a computed column.</span></span>  
  
 <span data-ttu-id="03f08-105">Pensez à rendre vos colonnes calculées persistantes lorsque vous migrez vos tables sur disque vers des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="03f08-105">You should consider the need to persist your computed columns when you migrate your disk-based tables to memory-optimized tables.</span></span> <span data-ttu-id="03f08-106">Les performances des tables mémoire optimisées et des procédures stockées compilées en mode natif peuvent remettre en cause le besoin de persistance.</span><span class="sxs-lookup"><span data-stu-id="03f08-106">The different performance characteristics of memory-optimized tables and natively compiled stored procedures may negate the need for persistence.</span></span>  
  
## <a name="non-persisted-computed-columns"></a><span data-ttu-id="03f08-107">Colonnes calculées non persistantes</span><span class="sxs-lookup"><span data-stu-id="03f08-107">Non-Persisted Computed Columns</span></span>  
 <span data-ttu-id="03f08-108">Pour simuler les effets d'une colonne calculée non persistante, créez une vue sur la table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="03f08-108">To simulate the effects of a non-persisted computed column, create a view on the memory-optimized table.</span></span> <span data-ttu-id="03f08-109">Dans l'instruction SELECT qui définit la vue, ajoutez la définition de colonne calculée dans la vue.</span><span class="sxs-lookup"><span data-stu-id="03f08-109">In the SELECT statement that defines the view, add the computed column definition into the view.</span></span> <span data-ttu-id="03f08-110">Excepté dans une procédure stockée compilée en mode natif, les requêtes qui utilisent des valeurs de la colonne calculée doivent être lues dans la vue.</span><span class="sxs-lookup"><span data-stu-id="03f08-110">Except in a natively compiled stored procedure, queries that use values from the computed column should read from the view.</span></span> <span data-ttu-id="03f08-111">Dans les procédures stockées compilées en mode natif, vous devez mettre à jour les instructions de sélection (SELECT), de mise à jour (UPDATE) ou de suppression (DELETE) conformément à votre définition de colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="03f08-111">Inside natively compiled stored procedures, you should update any select, update, or delete statement according to your computed column definition.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is not persisted.  
CREATE VIEW dbo.v_order_details AS  
   SELECT  
      OrderId,  
      ProductId,  
      SalePrice,  
      Quantity,  
      Quantity * SalePrice AS Total  
   FROM dbo.order_details  
```  
  
## <a name="persisted-computed-columns"></a><span data-ttu-id="03f08-112">Colonnes calculées persistantes</span><span class="sxs-lookup"><span data-stu-id="03f08-112">Persisted Computed Columns</span></span>  
 <span data-ttu-id="03f08-113">Pour simuler les effets d'une colonne calculée persistante, créez une procédure stockée pour insérer dans la table et une autre pour mettre à jour la table.</span><span class="sxs-lookup"><span data-stu-id="03f08-113">To simulate the effects of a persisted computed column, create a stored procedure for inserting into the table and another stored procedure for updating the table.</span></span> <span data-ttu-id="03f08-114">Lors de l'insertion ou de la mise à jour de la table, appelez ces procédures stockées pour effectuer ces tâches.</span><span class="sxs-lookup"><span data-stu-id="03f08-114">When inserting or updating the table, invoke these stored procedures to perform these tasks.</span></span> <span data-ttu-id="03f08-115">Dans les procédures stockées, calculez la valeur du champ calculé en fonction des entrées, de façon semblable au mode de définition de la colonne calculée sur la table sur disque d'origine.</span><span class="sxs-lookup"><span data-stu-id="03f08-115">Inside the stored procedures, calculate the value for the computed field according to the inputs, much like how the computed column is defined on the original disk-based table.</span></span> <span data-ttu-id="03f08-116">Ensuite, insérez ou mettez à jour la table selon les besoins dans la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="03f08-116">Then, insert or update the table as needed inside the stored procedure.</span></span>  
  
```sql  
-- Schema for the table dbo.OrderDetails:  
-- OrderId int not null primary key,  
-- ProductId int not null,  
-- SalePrice money not null,  
-- Quantity int not null,  
-- Total money not null  
--  
-- Total is computed as SalePrice * Quantity and is persisted.  
-- we need to create insert and update procedures to calculate Total.  
CREATE PROCEDURE sp_insert_order_details   
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
-- for bulk inserts, accept a table-valued parameter into the stored procedure  
-- and use an INSERT INTO SELECT statement.  
DECLARE @total money = @SalePrice * @Quantity  
INSERT INTO dbo.OrderDetails (OrderId, ProductId, SalePrice, Quantity, Total)  
VALUES (@OrderId, @ProductId, @SalePrice, @Quantity, @total)  
END  
GO  
  
CREATE PROCEDURE sp_update_order_details_by_id  
@OrderId int, @ProductId int, @SalePrice money, @Quantity int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (LANGUAGE = N'english', TRANSACTION ISOLATION LEVEL = SNAPSHOT)  
-- compute the value here.   
-- this stored procedure works with single rows only.  
DECLARE @total money = @SalePrice * @Quantity  
UPDATE dbo.OrderDetails   
SET ProductId = @ProductId, SalePrice = @SalePrice, Quantity = @Quantity, Total = @total  
WHERE OrderId = @OrderId  
END  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="03f08-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03f08-117">See Also</span></span>  
 [<span data-ttu-id="03f08-118">Migration vers OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="03f08-118">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
