---
title: Implémentation d’une instruction CASE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 2f82db01-da7e-4a7d-8bc0-48b245e6f768
author: rothja
ms.author: jroth
ms.openlocfilehash: 27059cc09d5507bf2548b23b60f3c2f485c3fe36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706500"
---
# <a name="implementing-a-case-statement"></a><span data-ttu-id="f7a14-102">Implémentation d'une instruction CASE</span><span class="sxs-lookup"><span data-stu-id="f7a14-102">Implementing a CASE Statement</span></span>
  <span data-ttu-id="f7a14-103">Les instructions CASE ne sont pas prises en charge dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="f7a14-103">Case statements are not supported in natively compiled stored procedures.</span></span> <span data-ttu-id="f7a14-104">L'exemple suivant illustre une méthode permettant d'implémenter les fonctionnalités d'une instruction CASE dans une procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="f7a14-104">The following sample shows a way to implement the functionality of a case statement in a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="f7a14-105">Il utilise une variable de table pour construire un seul jeu de résultats, qui n'est appropriée que lors du traitement d'un nombre limité de lignes, car elle implique de créer une copie supplémentaire des lignes de données.</span><span class="sxs-lookup"><span data-stu-id="f7a14-105">The samples uses a table variable to construct a single result set, which is only suitable when processing a limited number of rows, as it involves creating an additional copy of the data rows.</span></span>  
  
 <span data-ttu-id="f7a14-106">Vous devez tester les performances de cette solution, pour vous assurer qu'elle s'exécute comme prévu dans votre application.</span><span class="sxs-lookup"><span data-stu-id="f7a14-106">You should test the performance of this workaround, to be sure that it performs as expected in your application.</span></span>  
  
```  
-- original query  
SELECT   
   SalesOrderID,   
   CASE (OnlineOrderFlag)   
   WHEN 1 THEN N'Order placed online by customer'  
   ELSE N'Order placed by sales person'  
   END  
FROM Sales.SalesOrderHeader_inmem  
  
--  workaround for CASE in natively compiled stored procedures  
--  use a table for the single resultset  
CREATE TYPE dbo.SOHOnlineOrderResult AS TABLE  
(  
   SalesOrderID uniqueidentifier not null index ix_SalesOrderID,  
     OrderFlag nvarchar(100) not null  
) with (memory_optimized=on)  
go  
  
-- natively compiled stored procedure that includes the query  
CREATE PROCEDURE dbo.usp_SOHOnlineOrderResult  
   WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
   AS BEGIN ATOMIC WITH  
      (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE=N'us_english')  
  
   -- table variable for creating the single resultset  
   DECLARE @result dbo.SOHOnlineOrderResult  
  
   -- CASE OnlineOrderFlag=1  
   INSERT @result   
   SELECT SalesOrderID, N'Order placed online by customer'  
      FROM Sales.SalesOrderHeader_inmem  
      WHERE OnlineOrderFlag=1  
  
   -- ELSE  
   INSERT @result   
   SELECT SalesOrderID, placed by sales person'  
      FROM Sales.SalesOrderHeader_inmem  
      WHERE OnlineOrderFlag!=1  
  
   -- return single resultset  
   SELECT SalesOrderID, OrderFlag FROM @result  
END  
GO  
  
EXEC dbo.usp_SOHOnlineOrderResult  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7a14-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f7a14-107">See Also</span></span>  
 <span data-ttu-id="f7a14-108">[Problèmes de migration pour les procédures stockées compilées en mode natif](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="f7a14-108">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="f7a14-109">Constructions Transact-SQL non prises en charge par In-Memory OLTP</span><span class="sxs-lookup"><span data-stu-id="f7a14-109">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
  
