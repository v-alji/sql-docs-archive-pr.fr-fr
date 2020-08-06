---
title: Les opérateurs de jointure externe *= et =* ne sont pas pris en charge dans les modes de compatibilité 90 ou ultérieur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- =* join
- '*= join'
- joins [SQL Server]
ms.assetid: ca4aa11f-1048-411f-9c6c-3d0a8e319f2f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 357c729e6d53cc17f2e4c169dd66613b6cfd2f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704719"
---
# <a name="outer-join-operators--and--are-not-supported-in-90-or-later-compatibility-modes"></a><span data-ttu-id="fd53d-102">Les opérateurs de jointure externe \*= et =\* ne sont pas pris en charge en mode de compatibilité 90 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="fd53d-102">Outer join operators \*= and =\* are not supported in 90 or later compatibility modes</span></span>
  <span data-ttu-id="fd53d-103">Le conseiller de mise à niveau a détecté l’utilisation des opérateurs de jointure externe \* = et = \* .</span><span class="sxs-lookup"><span data-stu-id="fd53d-103">Upgrade Advisor detected the use of outer join operators \*= and =\*.</span></span> <span data-ttu-id="fd53d-104">Ces opérateurs ne sont pas pris en charge en mode de compatibilité 90 ou ultérieur.</span><span class="sxs-lookup"><span data-stu-id="fd53d-104">These operators are not supported in 90 or later compatibility modes.</span></span> <span data-ttu-id="fd53d-105">Lorsque vous effectuez une mise à niveau, les bases de données utilisateur conservent leur mode de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="fd53d-105">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="fd53d-106">Les instructions qui utilisent des opérateurs vont échouer.</span><span class="sxs-lookup"><span data-stu-id="fd53d-106">Statements that use these operators will fail.</span></span>  
  
## <a name="component"></a><span data-ttu-id="fd53d-107">Composant</span><span class="sxs-lookup"><span data-stu-id="fd53d-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="fd53d-108">Action corrective</span><span class="sxs-lookup"><span data-stu-id="fd53d-108">Corrective Action</span></span>  
 <span data-ttu-id="fd53d-109">Avant de modifier le mode de compatibilité de la base de données en 90 ou une version ultérieure, modifiez les instructions qui utilisent les opérateurs de jointure externe \* = et = \* pour utiliser des mots clés de jointure externe équivalents.</span><span class="sxs-lookup"><span data-stu-id="fd53d-109">Before you change the database compatibility mode to 90 or later, modify statements that use the outer join operators \*= and =\* to use equivalent OUTER JOIN keywords.</span></span> <span data-ttu-id="fd53d-110">L'exemple suivant affiche une requête qui utilise l'opérateur `\*=` et une requête équivalente qui utilise les mots clés `LEFT OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="fd53d-110">The following example shows a query that uses the `\*=` operator and an equivalent query that uses the `LEFT OUTER JOIN` keywords.</span></span>  
  
```  
-- This query uses an old-style outer join operator.  
USE pubs  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee, jobs   
WHERE employee.job_id *= jobs.job_id  
ORDER BY employee.job_id  
  
-- This query uses the ANSI standard keywords LEFT OUTER JOIN.  
USE pubs;  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
ORDER BY employee.job_id  
```  
  
 <span data-ttu-id="fd53d-111">Pour plus d'informations sur les jointures externes, consultez « Utilisation de jointures externes » dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fd53d-111">For more information about outer joins, see "Using Outer Joins" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd53d-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fd53d-112">See Also</span></span>  
 <span data-ttu-id="fd53d-113">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="fd53d-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="fd53d-114">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="fd53d-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
