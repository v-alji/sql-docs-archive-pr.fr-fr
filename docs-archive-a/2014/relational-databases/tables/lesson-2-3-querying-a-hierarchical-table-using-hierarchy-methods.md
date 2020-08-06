---
title: Interrogation d’une table hiérarchique à l’aide de méthodes hiérarchiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 3b4f7dae-65b5-4d8d-8641-87aba9aa692d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c86c8e8678fc821dc3796a511349c1c3498bdb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610988"
---
# <a name="querying-a-hierarchical-table-using-hierarchy-methods"></a><span data-ttu-id="b5f98-102">Interrogation d'une table hiérarchique à l'aide de méthodes hiérarchiques</span><span class="sxs-lookup"><span data-stu-id="b5f98-102">Querying a Hierarchical Table Using Hierarchy Methods</span></span>
  <span data-ttu-id="b5f98-103">Maintenant que la table HumanResources.EmployeeOrg est entièrement remplie, cette tâche vous indiquera comment interroger la hiérarchie à l'aide de certaines des méthodes hiérarchiques.</span><span class="sxs-lookup"><span data-stu-id="b5f98-103">Now that the HumanResources.EmployeeOrg table is fully populated, this task will show you how to query the hierarchy using some of the hierarchical methods.</span></span>  
  
### <a name="to-find-subordinate-nodes"></a><span data-ttu-id="b5f98-104">Pour rechercher des nœuds subordonnés</span><span class="sxs-lookup"><span data-stu-id="b5f98-104">To find subordinate nodes</span></span>  
  
1.  <span data-ttu-id="b5f98-105">Sariya a un employé subordonné.</span><span class="sxs-lookup"><span data-stu-id="b5f98-105">Sariya has one subordinate employee.</span></span> <span data-ttu-id="b5f98-106">Pour rechercher les subordonnés de Sariya, exécutez la requête suivante qui utilise la méthode [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) :</span><span class="sxs-lookup"><span data-stu-id="b5f98-106">To query for Sariya's subordinates, execute the following query that uses the [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) method:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.IsDescendantOf(@CurrentEmployee ) = 1 ;  
    ```  
  
     <span data-ttu-id="b5f98-107">Le résultat répertorie Sariya et Wanida.</span><span class="sxs-lookup"><span data-stu-id="b5f98-107">The result lists both Sariya and Wanida.</span></span> <span data-ttu-id="b5f98-108">Sariya est répertoriée car elle est la descendante au niveau 0.</span><span class="sxs-lookup"><span data-stu-id="b5f98-108">Sariya is listed because she is the descendant at the 0 level.</span></span> <span data-ttu-id="b5f98-109">Wanida est la descendante au niveau 1.</span><span class="sxs-lookup"><span data-stu-id="b5f98-109">Wanida is the descendant at the 1 level.</span></span>  
  
2.  <span data-ttu-id="b5f98-110">Vous pouvez également créer des requêtes sur ces informations à l’aide de la méthode [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="b5f98-110">You can also query for this information by using the [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="b5f98-111">`GetAncestor` prend un argument pour le niveau que vous tentez de retourner.</span><span class="sxs-lookup"><span data-stu-id="b5f98-111">`GetAncestor` takes an argument for the level that you are trying to return.</span></span> <span data-ttu-id="b5f98-112">Étant donné que Wanida est un niveau plus bas que Sariya, utilisez `GetAncestor(1)` comme indiqué dans le code suivant :</span><span class="sxs-lookup"><span data-stu-id="b5f98-112">Since Wanida is one level underneath Sariya, use `GetAncestor(1)` as demonstrated in the following code:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="b5f98-113">Cette fois-ci, le résultat répertorie uniquement Wanida.</span><span class="sxs-lookup"><span data-stu-id="b5f98-113">This time the result lists only Wanida.</span></span>  
  
3.  <span data-ttu-id="b5f98-114">Modifiez maintenant `@CurrentEmployee` sur David (EmployeeID 6) et le niveau sur 2.</span><span class="sxs-lookup"><span data-stu-id="b5f98-114">Now change the `@CurrentEmployee` to David (EmployeeID 6) and the level to 2.</span></span> <span data-ttu-id="b5f98-115">Exécutez le code suivant pour retourner également Wanida :</span><span class="sxs-lookup"><span data-stu-id="b5f98-115">Execute the following to also return Wanida:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 6 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(2) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="b5f98-116">Cette fois-ci, le résultat répertorie également Mary, deux niveaux plus bas, dont David est également le supérieur.</span><span class="sxs-lookup"><span data-stu-id="b5f98-116">This time, you also receive Mary who also reports to David, two levels down.</span></span>  
  
### <a name="to-use-getroot-and-getlevel"></a><span data-ttu-id="b5f98-117">Pour utiliser GetRoot et GetLevel</span><span class="sxs-lookup"><span data-stu-id="b5f98-117">To use GetRoot, and GetLevel</span></span>  
  
1.  <span data-ttu-id="b5f98-118">À mesure que la hiérarchie s'agrandit, il devient plus difficile de déterminer l'emplacement des membres dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="b5f98-118">As the hierarchy grows larger it is more difficult to determine where the members are in the hierarchy.</span></span> <span data-ttu-id="b5f98-119">La méthode [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) permet de déterminer le nombre de niveaux sous chaque ligne dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="b5f98-119">Use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to find how many levels down each row is in the hierarchy.</span></span> <span data-ttu-id="b5f98-120">Exécutez le code suivant pour consulter les niveaux de toutes les lignes :</span><span class="sxs-lookup"><span data-stu-id="b5f98-120">Execute the following code to view the levels of all the rows:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode.GetLevel() AS EmpLevel, *  
    FROM HumanResources.EmployeeOrg ;  
    GO  
  
    ```  
  
2.  <span data-ttu-id="b5f98-121">La méthode [GetRoot](/sql/t-sql/data-types/getroot-database-engine) permet de rechercher le nœud racine dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="b5f98-121">Use the [GetRoot](/sql/t-sql/data-types/getroot-database-engine) method to find the root node in the hierarchy.</span></span> <span data-ttu-id="b5f98-122">Le code suivant retourne la ligne unique qui est la racine :</span><span class="sxs-lookup"><span data-stu-id="b5f98-122">The following code returns the single row which is the root:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode = hierarchyid::GetRoot() ;  
    GO  
  
    ```  
  
 <span data-ttu-id="b5f98-123">La tâche suivante réorganisera la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="b5f98-123">The next task will reorganize the hierarchy.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b5f98-124">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="b5f98-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b5f98-125">Réorganisation de données dans une table hiérarchique à l'aide de méthodes hiérarchiques</span><span class="sxs-lookup"><span data-stu-id="b5f98-125">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-4-reordering-data-in-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
