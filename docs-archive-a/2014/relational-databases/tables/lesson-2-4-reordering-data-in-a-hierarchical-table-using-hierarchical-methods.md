---
title: Réorganisation de données dans une table hiérarchique à l’aide de méthodes hiérarchiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 7b8064c7-62c6-488d-84d2-57a5828fb907
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac6c93f359a81a80af81182120f213564680de0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600721"
---
# <a name="reordering-data-in-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="d21d6-102">Réorganisation de données dans une table hiérarchique à l'aide de méthodes hiérarchiques</span><span class="sxs-lookup"><span data-stu-id="d21d6-102">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>
  <span data-ttu-id="d21d6-103">La réorganisation d'une hiérarchie est une tâche de maintenance courante.</span><span class="sxs-lookup"><span data-stu-id="d21d6-103">Reorganizing a hierarchy is a common maintenance task.</span></span> <span data-ttu-id="d21d6-104">Dans cette tâche, nous utiliserons une instruction UPDATE avec la méthode [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) pour déplacer en premier lieu une seule ligne vers un nouvel emplacement dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="d21d6-104">In this task, we will use an UPDATE statement with the [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) method to first move a single row to a new location in the hierarchy.</span></span> <span data-ttu-id="d21d6-105">Puis, nous déplacerons la totalité d'une sous-arborescence vers un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="d21d6-105">Then we will move an entire sub-tree to a new location.</span></span>  
  
 <span data-ttu-id="d21d6-106">La méthode `GetReparentedValue` accepte deux arguments.</span><span class="sxs-lookup"><span data-stu-id="d21d6-106">The `GetReparentedValue` method takes two arguments.</span></span> <span data-ttu-id="d21d6-107">Le premier argument décrit la partie de la hiérarchie à modifier.</span><span class="sxs-lookup"><span data-stu-id="d21d6-107">The first argument describes the part of the hierarchy to be modified.</span></span> <span data-ttu-id="d21d6-108">Par exemple, si une hiérarchie est **/1/4/2/3/** et que vous souhaitez modifier la section **/1/4/** , la hiérarchie devient **/2/1/2/3/**, laissant les deux derniers nœuds (**2/3 /**) inchangés. Les nœuds à modifier (**/1/4/**) doivent être spécifiés comme premier argument.</span><span class="sxs-lookup"><span data-stu-id="d21d6-108">For example, if a hierarchy is **/1/4/2/3/** and you want to change the **/1/4/** section, the hierarchy becomes **/2/1/2/3/**, leaving the last two nodes (**2/3/**) unchanged, you must provide the changing nodes (**/1/4/**) as the first argument.</span></span> <span data-ttu-id="d21d6-109">Le deuxième argument fournit le nouveau niveau de hiérarchie, dans notre exemple **/2/1/**.</span><span class="sxs-lookup"><span data-stu-id="d21d6-109">The second argument provides the new hierarchy level, in our example **/2/1/**.</span></span> <span data-ttu-id="d21d6-110">Les deux arguments ne doivent pas nécessairement contenir le même nombre de niveaux.</span><span class="sxs-lookup"><span data-stu-id="d21d6-110">The two arguments do not have to contain the same number of levels.</span></span>  
  
### <a name="to-move-a-single-row-to-a-new-location-in-the-hierarchy"></a><span data-ttu-id="d21d6-111">Pour déplacer une ligne unique vers un nouvel emplacement dans la hiérarchie</span><span class="sxs-lookup"><span data-stu-id="d21d6-111">To move a single row to a new location in the hierarchy</span></span>  
  
1.  <span data-ttu-id="d21d6-112">Sariya est actuellement la supérieure de Wanida.</span><span class="sxs-lookup"><span data-stu-id="d21d6-112">Currently Wanida reports to Sariya.</span></span> <span data-ttu-id="d21d6-113">Dans cette procédure, vous déplacez Wanida du nœud **/1/1/,** où elle se trouve actuellement, pour que Jill soit sa supérieure.</span><span class="sxs-lookup"><span data-stu-id="d21d6-113">In this procedure, you move Wanida from her current node **/1/1/,** so that she reports to Jill.</span></span> <span data-ttu-id="d21d6-114">Son nouveau nœud deviendra ainsi **/3/1/** . **/1/** sera donc le premier argument et **/3/** le second.</span><span class="sxs-lookup"><span data-stu-id="d21d6-114">Her new node will become **/3/1/** so **/1/** is the first argument and **/3/** is the second.</span></span> <span data-ttu-id="d21d6-115">Ceux-ci correspondent aux valeurs **OrgNode** de Sariya et de Jill.</span><span class="sxs-lookup"><span data-stu-id="d21d6-115">These correspond to the **OrgNode** values of Sariya and Jill.</span></span> <span data-ttu-id="d21d6-116">Exécutez le code suivant pour déplacer Wanida de l'organisation de Sariya vers celle de Jill :</span><span class="sxs-lookup"><span data-stu-id="d21d6-116">Execute the following code to move Wanida from Sariya's organization to Jill's:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid , @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @CurrentEmployee = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 269 ;   
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 46 ;   
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 119 ;   
  
    UPDATE HumanResources.EmployeeOrg  
    SET OrgNode = @CurrentEmployee. GetReparentedValue(@OldParent, @NewParent)   
    WHERE OrgNode = @CurrentEmployee ;  
    GO  
    ```  
  
2.  <span data-ttu-id="d21d6-117">Exécutez le code suivant pour afficher le résultat :</span><span class="sxs-lookup"><span data-stu-id="d21d6-117">Execute the following code to see the result:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     <span data-ttu-id="d21d6-118">Wanida se trouve maintenant au nœud **/3/1/**.</span><span class="sxs-lookup"><span data-stu-id="d21d6-118">Wanida is now at node **/3/1/**.</span></span>  
  
### <a name="to-reorganize-a-section-of-a-hierarchy"></a><span data-ttu-id="d21d6-119">Pour réorganiser une section d'une hiérarchie</span><span class="sxs-lookup"><span data-stu-id="d21d6-119">To reorganize a section of a hierarchy</span></span>  
  
1.  <span data-ttu-id="d21d6-120">Pour montrer comment déplacer simultanément un plus grand nombre de personnes, exécutez d'abord le code suivant pour ajouter un subalterne interne à Wanida :</span><span class="sxs-lookup"><span data-stu-id="d21d6-120">To demonstrate how to move a larger number of people at the same time, first execute the following code to add an intern reporting to Wanida:</span></span>  
  
    ```  
    EXEC AddEmp 269, 291, 'Kevin', 'Marketing Intern'  ;  
    GO  
    ```  
  
2.  <span data-ttu-id="d21d6-121">Kevin est désormais le subalterne de Wanida, elle-même subalterne de Jill, elle-même subalterne de David.</span><span class="sxs-lookup"><span data-stu-id="d21d6-121">Now Kevin reports to Wanida, who reports to Jill, who reports to David.</span></span> <span data-ttu-id="d21d6-122">Cela signifie que Kevin est au niveau **/3/1/1/**.</span><span class="sxs-lookup"><span data-stu-id="d21d6-122">That means that Kevin is at level **/3/1/1/**.</span></span> <span data-ttu-id="d21d6-123">Pour déplacer tous les subalternes de Jill vers un nouveau responsable, nous allons mettre à jour tous les nœuds qui ont **/3/** comme valeur **OrgNode** vers une nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="d21d6-123">To move all of Jill's subordinates to a new manager, we will update all nodes that have **/3/** as their **OrgNode** to a new value.</span></span> <span data-ttu-id="d21d6-124">Exécutez le code suivant pour mettre à jour Wanida de sorte que Sariya soit sa supérieure, en conservant Kevin comme subalterne de Wanida :</span><span class="sxs-lookup"><span data-stu-id="d21d6-124">Execute the following code to update Wanida to report to Sariya, but keep  Kevin reporting to Wanida:</span></span>  
  
    ```  
    DECLARE @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 119 ; -- Jill  
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ; -- Sariya  
    DECLARE children_cursor CURSOR FOR  
    SELECT OrgNode FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @OldParent;  
    DECLARE @ChildId hierarchyid;  
    OPEN children_cursor  
    FETCH NEXT FROM children_cursor INTO @ChildId;  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
    START:  
        DECLARE @NewId hierarchyid;  
        SELECT @NewId = @NewParent.GetDescendant(MAX(OrgNode), NULL)  
        FROM HumanResources.EmployeeOrg WHERE OrgNode.GetAncestor(1) = @NewParent;  
  
        UPDATE HumanResources.EmployeeOrg  
        SET OrgNode = OrgNode.GetReparentedValue(@ChildId, @NewId)  
        WHERE OrgNode.IsDescendantOf(@ChildId) = 1;  
        IF @@error <> 0 GOTO START -- On error, retry  
            FETCH NEXT FROM children_cursor INTO @ChildId;  
    END  
    CLOSE children_cursor;  
    DEALLOCATE children_cursor;  
  
    ```  
  
3.  <span data-ttu-id="d21d6-125">Exécutez le code suivant pour afficher le résultat :</span><span class="sxs-lookup"><span data-stu-id="d21d6-125">Execute the following code to see the result:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
------------ ------- -------- ---------- ------- -----------------  
/            Ox      0        6          David   Marketing Manager  
/1/          0x58    1        46         Sariya  Marketing Specialist  
/1/1/        0x5AC0  2        269        Wanida  Marketing Assistant  
/1/1//2      0x5AD0  3        291        Kevin   Marketing Intern  
/2/          0x68    1        271        John    Marketing Specialist  
/2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
/3/          0x78    1        119        Jill    Marketing Specialist  
```  
  
 <span data-ttu-id="d21d6-126">La totalité de l'arborescence de l'organisation dont Jill était la supérieure (Wanida et Kevin) a maintenant Sariya comme supérieure.</span><span class="sxs-lookup"><span data-stu-id="d21d6-126">The entire organizational tree that had reported to Jill (both Wanida and Kevin) now reports to Sariya.</span></span>  
  
 <span data-ttu-id="d21d6-127">Pour obtenir une procédure stockée qui réorganise une section d’une hiérarchie, consultez la section « Déplacement de sous-arborescences » de [Déplacement de sous-arborescences](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span><span class="sxs-lookup"><span data-stu-id="d21d6-127">For a stored procedure to reorganize a section of a hierarchy, see the "Moving Subtrees" section of [Moving Subtrees](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d21d6-128">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="d21d6-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d21d6-129">Résumé : Gestion de données dans une table hiérarchique</span><span class="sxs-lookup"><span data-stu-id="d21d6-129">Summary: Managing Data in a Hierarchical Table</span></span>](lesson-2-5-summary-managing-data-in-a-hierarchical-table.md)  
  
  
