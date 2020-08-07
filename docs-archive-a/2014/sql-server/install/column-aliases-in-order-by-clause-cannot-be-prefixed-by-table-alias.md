---
title: Les alias de colonnes dans la clause ORDER BY ne peuvent pas avoir pour préfixe l’alias de table | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- aliases [SQL Server], columns
ms.assetid: fee7328f-6e8d-4005-930b-56fb6f17e0b2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 44333d778753a2f8761d32d181681b798e3bc409
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604943"
---
# <a name="column-aliases-in-order-by-clause-cannot-be-prefixed-by-table-alias"></a><span data-ttu-id="8bdb2-102">Les alias de colonne dans la clause ORDER BY ne peuvent pas avoir un alias de table pour préfixe</span><span class="sxs-lookup"><span data-stu-id="8bdb2-102">Column aliases in ORDER BY clause cannot be prefixed by table alias</span></span>
  <span data-ttu-id="8bdb2-103">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou version ultérieure, les alias de colonne dans la clause ORDER BY ne peuvent pas avoir l'alias de table pour préfixe.</span><span class="sxs-lookup"><span data-stu-id="8bdb2-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, column aliases in the ORDER BY clause cannot be prefixed by the table alias.</span></span>  
  
## <a name="component"></a><span data-ttu-id="8bdb2-104">Composant</span><span class="sxs-lookup"><span data-stu-id="8bdb2-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="8bdb2-105">Description</span><span class="sxs-lookup"><span data-stu-id="8bdb2-105">Description</span></span>  
 <span data-ttu-id="8bdb2-106">Par exemple, la requête suivante s'exécute dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], mais retourne une erreur dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bdb2-106">For example, the following query executes in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but returns an error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.l  
```  
  
 <span data-ttu-id="8bdb2-107">Le [!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] ne fait pas correspondre `p.l` dans la clause `ORDER BY` à une colonne valide dans la table.</span><span class="sxs-lookup"><span data-stu-id="8bdb2-107">The [!INCLUDE[ssDEversion10](../../includes/ssdeversion10-md.md)] does not match `p.l` in the `ORDER BY` clause to a valid column in the table.</span></span>  
  
### <a name="exception"></a><span data-ttu-id="8bdb2-108">Exception</span><span class="sxs-lookup"><span data-stu-id="8bdb2-108">Exception</span></span>  
 <span data-ttu-id="8bdb2-109">Si l'alias de colonne préfixé qui est spécifié dans la clause ORDER BY est un nom de colonne valide dans la table spécifiée, la requête s'exécute sans erreur ; dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], la sémantique de l'instruction peut être différente.</span><span class="sxs-lookup"><span data-stu-id="8bdb2-109">If the prefixed column alias that is specified in the ORDER BY clause is a valid column name in the specified table, the query executes without error; in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the semantics of the statement might be different.</span></span> <span data-ttu-id="8bdb2-110">Par exemple, l'alias de colonne (`id`) spécifié dans l'instruction suivante est un nom de colonne valide dans la table `sysobjects`.</span><span class="sxs-lookup"><span data-stu-id="8bdb2-110">For example, the column alias (`id`) specified in the following statement is a valid column name in the `sysobjects` table.</span></span> <span data-ttu-id="8bdb2-111">Dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], lorsque l'instruction s'exécute, l'opération `CAST` est effectuée une fois que le jeu de résultats a été trié.</span><span class="sxs-lookup"><span data-stu-id="8bdb2-111">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], when the statement executes, the `CAST` operation is performed after the result set is sorted.</span></span> <span data-ttu-id="8bdb2-112">Cela signifie que la colonne `name` est utilisée dans l'opération de tri.</span><span class="sxs-lookup"><span data-stu-id="8bdb2-112">This means the `name` column is used in the sort operation.</span></span> <span data-ttu-id="8bdb2-113">Dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], l'opération `CAST` se produit avant l'opération de tri.</span><span class="sxs-lookup"><span data-stu-id="8bdb2-113">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the `CAST` operation occurs before the sort operation.</span></span> <span data-ttu-id="8bdb2-114">Cela signifie que la colonne `id` dans la table est utilisée dans l'opération de tri et retourne le jeu de résultats dans un ordre inattendu.</span><span class="sxs-lookup"><span data-stu-id="8bdb2-114">This means the `id` column in the table is used in the sort operation and returns the result set in an unexpected order.</span></span>  
  
```  
SELECT CAST (o.name AS char(128)) AS id  
FROM sysobjects AS o  
ORDER BY o.id;  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="8bdb2-115">Action corrective</span><span class="sxs-lookup"><span data-stu-id="8bdb2-115">Corrective Action</span></span>  
 <span data-ttu-id="8bdb2-116">Modifiez les requêtes qui utilisent des alias de colonne préfixés par des alias de table dans la clause ORDER BY d'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="8bdb2-116">Modify queries that use column aliases prefixed by table aliases in the ORDER BY clause in either of the following ways:</span></span>  
  
-   <span data-ttu-id="8bdb2-117">N'ajoutez pas de préfixe à l'alias de colonne dans la clause ORDER BY, si possible.</span><span class="sxs-lookup"><span data-stu-id="8bdb2-117">Do not prefix the column alias in the ORDER BY clause, if possible.</span></span>  
  
-   <span data-ttu-id="8bdb2-118">Remplacez l'alias de colonne par le nom de la colonne.</span><span class="sxs-lookup"><span data-stu-id="8bdb2-118">Replace the column alias with the column name.</span></span>  
  
 <span data-ttu-id="8bdb2-119">Par exemple, les deux requêtes suivantes s'exécutent sans erreur dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="8bdb2-119">For example, both of the following queries execute without error in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY l  
  
USE AdventureWorks2012;  
GO  
SELECT FirstName AS f, LastName AS l  
FROM Person.Contact p  
ORDER BY p.LastName  
```  
  
## <a name="see-also"></a><span data-ttu-id="8bdb2-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8bdb2-120">See Also</span></span>  
 <span data-ttu-id="8bdb2-121">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8bdb2-121">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="8bdb2-122">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="8bdb2-122">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
