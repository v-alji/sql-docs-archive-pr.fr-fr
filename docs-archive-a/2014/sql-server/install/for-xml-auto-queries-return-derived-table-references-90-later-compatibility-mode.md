---
title: Les requêtes FOR XML AUTO retournent des références de tables dérivées dans les modes de compatibilité 90 ou ultérieur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FOR XML AUTO [SQL Server]
ms.assetid: 10c32f06-f7e1-40e0-8f79-6d921f2bef1d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 702cb2ca1d437dff03cee09c98d72082500709d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615001"
---
# <a name="for-xml-auto-queries-return-derived-table-references-in-90-or-later-compatibility-modes"></a><span data-ttu-id="3a516-102">Les requêtes FOR XML AUTO retournent des références de tables dérivées en mode de compatibilité 90 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="3a516-102">FOR XML AUTO queries return derived table references in 90 or later compatibility modes</span></span>
  <span data-ttu-id="3a516-103">Lorsque le niveau de compatibilité de la base de données est supérieur ou égal à 90, les requêtes FOR XML qui s'exécutent en mode AUTO retournent des références à des alias de table dérivée.</span><span class="sxs-lookup"><span data-stu-id="3a516-103">When the database compatibility level is set to 90 or later, FOR XML queries that execute in AUTO mode return references to derived table aliases.</span></span> <span data-ttu-id="3a516-104">Lorsque le niveau de compatibilité est égal à 80, les instructions FOR XML AUTO retournent des références à des tables de base qui définissent une table dérivée.</span><span class="sxs-lookup"><span data-stu-id="3a516-104">When the compatibility level is set to 80, FOR XML AUTO queries return references to the base tables that define a derived table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="3a516-105">Composant</span><span class="sxs-lookup"><span data-stu-id="3a516-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="3a516-106">Description</span><span class="sxs-lookup"><span data-stu-id="3a516-106">Description</span></span>  
 <span data-ttu-id="3a516-107">Imaginons, par exemple, la table suivante :</span><span class="sxs-lookup"><span data-stu-id="3a516-107">For example, consider the following table:</span></span>  
  
```  
CREATE TABLE Test(id int);  
INSERT INTO Test VALUES(1);  
INSERT INTO Test VALUES(2);  
```  
  
 <span data-ttu-id="3a516-108">La requête suivante, qui inclut une table dérivée, produit des résultats différents lorsque le niveau de comptabilité est égal à 80, 90 ou une valeur supérieure :</span><span class="sxs-lookup"><span data-stu-id="3a516-108">The following query, which includes a derived table, produces different results under compatibility levels 80, 90, or later:</span></span>  
  
```  
SELECT * FROM   
   (SELECT a.id AS a, b.id AS b   
    FROM Test a JOIN Test b ON a.id=b.id)  
AS DerivedTest   
FOR XML AUTO;  
```  
  
 <span data-ttu-id="3a516-109">Lorsque le niveau de compatibilité est égal à 80, la requête retourne les résultats suivants.</span><span class="sxs-lookup"><span data-stu-id="3a516-109">Under compatibility level 80, the query returns the following results.</span></span> <span data-ttu-id="3a516-110">Les résultats référencent les alias des tables de base `a` et `b` de la table dérivée au lieu de l'alias de la table dérivée.</span><span class="sxs-lookup"><span data-stu-id="3a516-110">The results reference the base table aliases `a` and `b` of the derived table instead of the derived table alias.</span></span>  
  
```  
<a a="1"><b b="1"/></a><a a="2"><b b="2"/></a>  
```  
  
 <span data-ttu-id="3a516-111">Lorsque le niveau de compatibilité est supérieur ou égal à 90, la requête retourne des références à l'alias de la table dérivée `DerivedTest` au lieu de références aux tables de base de la table dérivée.</span><span class="sxs-lookup"><span data-stu-id="3a516-111">Under compatibility level 90 or later, the query returns references to the derived table alias `DerivedTest` instead of to the derived table's base tables.</span></span>  
  
```  
<DerivedTest a="1" b="1"/><DerivedTest a="2" b="2"/>  
```  
  
## <a name="corrective-action"></a><span data-ttu-id="3a516-112">Action corrective</span><span class="sxs-lookup"><span data-stu-id="3a516-112">Corrective Action</span></span>  
 <span data-ttu-id="3a516-113">Modifiez votre application comme il convient pour prendre en compte les modifications dans les résultats des requêtes FOR XML AUTO qui incluent des tables dérivées et qui s'exécutent avec un niveau de compatibilité supérieur ou égal à 90.</span><span class="sxs-lookup"><span data-stu-id="3a516-113">Modify your application as required to account for the changes in results of FOR XML AUTO queries that include derived tables and that run under compatibility level 90 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a516-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3a516-114">See Also</span></span>  
 <span data-ttu-id="3a516-115">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="3a516-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="3a516-116">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="3a516-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
