---
title: Requêtes de bases de données croisées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a0305f5b-91bd-4d18-a2fc-ec235b062fd3
author: rothja
ms.author: jroth
ms.openlocfilehash: 4afbb580a55273ec241005493fd37f99e98ec0e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602837"
---
# <a name="cross-database-queries"></a><span data-ttu-id="899ec-102">Requêtes de bases de données croisées</span><span class="sxs-lookup"><span data-stu-id="899ec-102">Cross-Database Queries</span></span>
  <span data-ttu-id="899ec-103">Dans [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], les tables mémoire optimisées ne prennent pas en charge les transactions entre bases de données.</span><span class="sxs-lookup"><span data-stu-id="899ec-103">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], memory-optimized tables do not support cross-database transactions.</span></span> <span data-ttu-id="899ec-104">Vous ne pouvez pas accéder à une autre base de données à partir de la même transaction ou de la même requête qui accède également à une table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="899ec-104">You cannot access another database from the same transaction or the same query that also accesses a memory-optimized table.</span></span> <span data-ttu-id="899ec-105">Vous ne pouvez pas facilement copier les données d'une table d'une base de données, à une table mémoire optimisée d'une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="899ec-105">You cannot easily copy data from a table in one database, to a memory-optimized table in another database.</span></span>  
  
 <span data-ttu-id="899ec-106">Les variables de table ne sont pas transactionnelles.</span><span class="sxs-lookup"><span data-stu-id="899ec-106">Table variables are not transactional.</span></span> <span data-ttu-id="899ec-107">Par conséquent, les variables des tables mémoire optimisées peuvent être utilisées dans des requêtes de bases de données croisées, et peuvent donc faciliter le déplacement des données d'une base de données dans des tables mémoire optimisées dans une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="899ec-107">Therefore, memory-optimized table variables can be used in cross-database queries, and can thus facilitate moving data from one database into memory-optimized tables in another.</span></span> <span data-ttu-id="899ec-108">Vous pouvez utiliser deux transactions.</span><span class="sxs-lookup"><span data-stu-id="899ec-108">You can use two transactions.</span></span> <span data-ttu-id="899ec-109">Dans la première transaction, insérez les données de la table distante dans la variable.</span><span class="sxs-lookup"><span data-stu-id="899ec-109">In the first transaction, insert the data from the remote table into the variable.</span></span> <span data-ttu-id="899ec-110">Dans la seconde transaction, insérez les données dans la table mémoire optimisée locale depuis la variable.</span><span class="sxs-lookup"><span data-stu-id="899ec-110">In the second transaction, insert the data into the local memory-optimized table from the variable.</span></span>  
  
 <span data-ttu-id="899ec-111">Par exemple, pour copier la ligne de la table T1 dans la base de données db1 vers la table T2 dans DB2, en utilisant @v1 une variable de type dbo. TT1, vous pouvez utiliser ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="899ec-111">For example, to copy the row from table t1 in database db1 to table t2 in db2, using variable @v1 of type dbo.tt1, you can use something like:</span></span>  
  
```sql  
USE db2   
GO   
DECLARE @v1 dbo.tt1   
INSERT @v1 SELECT * FROM db1.dbo.t1   
INSERT dbo.t2 SELECT * FROM @v1   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="899ec-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="899ec-112">See Also</span></span>  
 [<span data-ttu-id="899ec-113">Migration vers OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="899ec-113">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
