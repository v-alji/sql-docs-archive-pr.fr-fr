---
title: Remplissage d’une table hiérarchique à l’aide de méthodes hiérarchiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- HierarchyID
helpviewer_keywords:
- HierarchyID
ms.assetid: 2c95fa60-5b8e-4a05-ac09-cffe2b05900a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ef99d711a772a075f568a83f5d56fcecaaa598f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611653"
---
# <a name="populating-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="94ec9-102">Remplissage d'une table hiérarchique utilisant des méthodes hiérarchiques</span><span class="sxs-lookup"><span data-stu-id="94ec9-102">Populating a Hierarchical Table Using Hierarchical Methods</span></span>
  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="94ec9-103">a 8 employés travaillant dans le service Marketing.</span><span class="sxs-lookup"><span data-stu-id="94ec9-103">has 8 employees working in the Marketing department.</span></span> <span data-ttu-id="94ec9-104">La hiérarchie des employés se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="94ec9-104">The employee hierarchy looks like this:</span></span>  
  
 <span data-ttu-id="94ec9-105">**David**, **EmployeeID** 6, est le directeur du marketing.</span><span class="sxs-lookup"><span data-stu-id="94ec9-105">**David**, **EmployeeID** 6, is the Marketing Manager.</span></span> <span data-ttu-id="94ec9-106">**David**est le supérieur de trois spécialistes en marketing :</span><span class="sxs-lookup"><span data-stu-id="94ec9-106">Three Marketing Specialists report to **David**:</span></span>  
  
-   <span data-ttu-id="94ec9-107">**Sariya**, **EmployeeID** 46</span><span class="sxs-lookup"><span data-stu-id="94ec9-107">**Sariya**, **EmployeeID** 46</span></span>  
  
-   <span data-ttu-id="94ec9-108">**John**, **EmployeeID** 271</span><span class="sxs-lookup"><span data-stu-id="94ec9-108">**John**, **EmployeeID** 271</span></span>  
  
-   <span data-ttu-id="94ec9-109">**Jill**, **EmployeeID** 119</span><span class="sxs-lookup"><span data-stu-id="94ec9-109">**Jill**, **EmployeeID** 119</span></span>  
  
 <span data-ttu-id="94ec9-110">**Sariya** est la supérieure de l’assistante marketing**Wanida** ( **EmployeeID**269) et **John** est le supérieur de l’assistante marketing**Mary** ( **EmployeeID**272).</span><span class="sxs-lookup"><span data-stu-id="94ec9-110">Marketing Assistant **Wanida** (**EmployeeID** 269), reports to **Sariya**, and Marketing Assistant **Mary** (**EmployeeID** 272), reports to **John**.</span></span>  
  
### <a name="to-insert-the-root-of-the-hierarchy-tree"></a><span data-ttu-id="94ec9-111">Pour insérer la racine de la structure hiérarchique</span><span class="sxs-lookup"><span data-stu-id="94ec9-111">To insert the root of the hierarchy tree</span></span>  
  
1.  <span data-ttu-id="94ec9-112">L’exemple suivant permet d’insérer **David** (directeur du marketing) à la table, à la racine de la structure hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="94ec9-112">The following example inserts **David** the Marketing Manager into the table at the root of the hierarchy.</span></span> <span data-ttu-id="94ec9-113">La colonne **OrdLevel** est une colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="94ec9-113">The **OrdLevel** column is a computed column.</span></span> <span data-ttu-id="94ec9-114">Par conséquent, elle ne fait pas partie de l'instruction INSERT.</span><span class="sxs-lookup"><span data-stu-id="94ec9-114">Therefore, it is not part of the INSERT statement.</span></span> <span data-ttu-id="94ec9-115">La méthode [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) est utilisée pour remplir ce premier enregistrement en tant que racine de la structure hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="94ec9-115">This first record uses the [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) method to populate this first record as the root of the hierarchy.</span></span>  
  
    ```  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES (hierarchyid::GetRoot(), 6, 'David', 'Marketing Manager') ;  
    GO  
    ```  
  
2.  <span data-ttu-id="94ec9-116">Exécutez le code suivant pour examiner la ligne initiale de la table :</span><span class="sxs-lookup"><span data-stu-id="94ec9-116">Execute the following code to examine initial row in the table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    ```  
  
 <span data-ttu-id="94ec9-117">Comme dans la leçon précédente, nous allons utiliser la méthode `ToString()` pour convertir le type de données `hierarchyid` dans un format plus compréhensible.</span><span class="sxs-lookup"><span data-stu-id="94ec9-117">As in the previous lesson, we use the `ToString()` method to convert the `hierarchyid` data type to a format that is more easily understood.</span></span>  
  
### <a name="to-insert-a-subordinate-employee"></a><span data-ttu-id="94ec9-118">Pour insérer un employé subordonné</span><span class="sxs-lookup"><span data-stu-id="94ec9-118">To insert a subordinate employee</span></span>  
  
1.  <span data-ttu-id="94ec9-119">**David** est le supérieur de **Sariya**.</span><span class="sxs-lookup"><span data-stu-id="94ec9-119">**Sariya** reports to **David**.</span></span> <span data-ttu-id="94ec9-120">Pour insérer le nœud **de Sariya** , vous devez créer une valeur **OrgNode** appropriée de type de données `hierarchyid` .</span><span class="sxs-lookup"><span data-stu-id="94ec9-120">To insert **Sariya's** node, you must create an appropriate **OrgNode** value of data type `hierarchyid`.</span></span> <span data-ttu-id="94ec9-121">Le code suivant permet de créer une variable de type de données `hierarchyid` et de la remplir avec la valeur racine OrgNode de la table.</span><span class="sxs-lookup"><span data-stu-id="94ec9-121">The following code creates a variable of data type `hierarchyid` and populates it with the root OrgNode value of the table.</span></span> <span data-ttu-id="94ec9-122">Il utilise ensuite cette variable avec la méthode [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) pour insérer une ligne qui est un nœud subordonné.</span><span class="sxs-lookup"><span data-stu-id="94ec9-122">Then uses that variable with the [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) method to insert row that is a subordinate node.</span></span> <span data-ttu-id="94ec9-123">`GetDescendant` nécessite deux arguments.</span><span class="sxs-lookup"><span data-stu-id="94ec9-123">`GetDescendant` takes two arguments.</span></span> <span data-ttu-id="94ec9-124">Vérifiez les valeurs d'argument des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="94ec9-124">Review the following options for the argument values:</span></span>  
  
    -   <span data-ttu-id="94ec9-125">Si parent est NULL, `GetDescendant` retourne NULL.</span><span class="sxs-lookup"><span data-stu-id="94ec9-125">If parent is NULL, `GetDescendant` returns NULL.</span></span>  
  
    -   <span data-ttu-id="94ec9-126">Si parent n'est pas NULL et que enfant1 et enfant2 sont NULL, `GetDescendant` retourne un enfant de parent.</span><span class="sxs-lookup"><span data-stu-id="94ec9-126">If parent is not NULL, and both child1 and child2 are NULL, `GetDescendant` returns a child of parent.</span></span>  
  
    -   <span data-ttu-id="94ec9-127">Si parent et enfant1 ne sont pas NULL et que enfant2 est NULL, `GetDescendant` retourne un enfant de parent supérieur à enfant1.</span><span class="sxs-lookup"><span data-stu-id="94ec9-127">If parent and child1 are not NULL, and child2 is NULL, `GetDescendant` returns a child of parent greater than child1.</span></span>  
  
    -   <span data-ttu-id="94ec9-128">Si parent et enfant2 ne sont pas NULL et que enfant1 est NULL, `GetDescendant` retourne un enfant de parent inférieur à enfant2.</span><span class="sxs-lookup"><span data-stu-id="94ec9-128">If parent and child2 are not NULL and child1 is NULL, `GetDescendant` returns a child of parent less than child2.</span></span>  
  
    -   <span data-ttu-id="94ec9-129">Si parent, enfant1 et enfant 2 ne sont pas NULL, `GetDescendant` retourne un enfant de parent supérieur à enfant1 et inférieur à enfant2.</span><span class="sxs-lookup"><span data-stu-id="94ec9-129">If parent, child1, and child2 are all not NULL, `GetDescendant` returns a child of parent greater than child1 and less than child2.</span></span>  
  
     <span data-ttu-id="94ec9-130">Le code suivant utilise les arguments `(NULL, NULL)` du parent racine parce qu'il n'y pas encore de ligne dans la table, à l'exception de la racine.</span><span class="sxs-lookup"><span data-stu-id="94ec9-130">The following code uses the `(NULL, NULL)` arguments of the root parent because there are not yet any rows in the table except the root.</span></span> <span data-ttu-id="94ec9-131">Exécutez le code suivant pour insérer **Sariya**:</span><span class="sxs-lookup"><span data-stu-id="94ec9-131">Execute the following code to insert **Sariya**:</span></span>  
  
    ```  
    DECLARE @Manager hierarchyid   
    SELECT @Manager = hierarchyid::GetRoot()  
    FROM HumanResources.EmployeeOrg ;  
  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES  
    (@Manager.GetDescendant(NULL, NULL), 46, 'Sariya', 'Marketing Specialist') ;  
  
    ```  
  
2.  <span data-ttu-id="94ec9-132">Répétez la requête à partir de la première procédure pour interroger la table et voir comment les entrées apparaissent :</span><span class="sxs-lookup"><span data-stu-id="94ec9-132">Repeat the query from the first procedure to query the table and see how the entries appear:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    ```  
  
### <a name="to-create-a-procedure-for-entering-new-nodes"></a><span data-ttu-id="94ec9-133">Pour créer une procédure afin d'entrer de nouveaux nœuds</span><span class="sxs-lookup"><span data-stu-id="94ec9-133">To create a procedure for entering new nodes</span></span>  
  
1.  <span data-ttu-id="94ec9-134">Pour simplifier l’entrée des données, créez la procédure stockée suivante pour ajouter des employés à la table **EmployeeOrg** .</span><span class="sxs-lookup"><span data-stu-id="94ec9-134">To simplify entering data, create the following stored procedure to add employees to the **EmployeeOrg** table.</span></span> <span data-ttu-id="94ec9-135">La procédure accepte les valeurs d'entrée relatives à l'employé ajouté.</span><span class="sxs-lookup"><span data-stu-id="94ec9-135">The procedure accepts input values about the employee being added.</span></span> <span data-ttu-id="94ec9-136">Cela inclut **l’EmployeeID** du directeur du nouvel employé, le numéro **d’EmployeeID** du nouvel employé ainsi que leurs prénoms et titres respectifs.</span><span class="sxs-lookup"><span data-stu-id="94ec9-136">This includes the **EmployeeID** of the new employee's manager, the new employee's **EmployeeID** number, and their first name and title.</span></span> <span data-ttu-id="94ec9-137">La procédure utilise `GetDescendant()` ainsi que la méthode [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="94ec9-137">The procedure uses `GetDescendant()` and also the [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="94ec9-138">Exécutez le code suivant pour créer la procédure :</span><span class="sxs-lookup"><span data-stu-id="94ec9-138">Execute the following code to create the procedure:</span></span>  
  
    ```  
    CREATE PROC AddEmp(@mgrid int, @empid int, @e_name varchar(20), @title varchar(20))   
    AS   
    BEGIN  
       DECLARE @mOrgNode hierarchyid, @lc hierarchyid  
       SELECT @mOrgNode = OrgNode   
       FROM HumanResources.EmployeeOrg   
       WHERE EmployeeID = @mgrid  
       SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
       BEGIN TRANSACTION  
          SELECT @lc = max(OrgNode)   
          FROM HumanResources.EmployeeOrg   
          WHERE OrgNode.GetAncestor(1) =@mOrgNode ;  
  
          INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
          VALUES(@mOrgNode.GetDescendant(@lc, NULL), @empid, @e_name, @title)  
       COMMIT  
    END ;  
    GO  
    ```  
  
2.  <span data-ttu-id="94ec9-139">L’exemple suivant permet d’ajouter les 4 employés restants dont **David**est le supérieur direct ou indirect.</span><span class="sxs-lookup"><span data-stu-id="94ec9-139">The following example adds the remaining 4 employees that report directly or indirectly to **David**.</span></span>  
  
    ```  
    EXEC AddEmp 6, 271, 'John', 'Marketing Specialist' ;  
    EXEC AddEmp 6, 119, 'Jill', 'Marketing Specialist' ;  
    EXEC AddEmp 46, 269, 'Wanida', 'Marketing Assistant' ;  
    EXEC AddEmp 271, 272, 'Mary', 'Marketing Assistant' ;  
    ```  
  
3.  <span data-ttu-id="94ec9-140">Réexécutez la requête suivante pour vérifier les lignes de la table **EmployeeOrg** :</span><span class="sxs-lookup"><span data-stu-id="94ec9-140">Again, execute the following query examine the rows in the **EmployeeOrg** table:</span></span>  
  
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
    /2/          0x68    1        271        John    Marketing Specialist  
    /2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
    /3/          0x78    1        119        Jill    Marketing Specialist  
    ```  
  
 <span data-ttu-id="94ec9-141">La table est maintenant complètement remplie avec l'organisation du service Marketing.</span><span class="sxs-lookup"><span data-stu-id="94ec9-141">The table is now fully populated with the Marketing organization.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="94ec9-142">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="94ec9-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="94ec9-143">Interrogation d'une table hiérarchique à l'aide de méthodes hiérarchiques</span><span class="sxs-lookup"><span data-stu-id="94ec9-143">Querying a Hierarchical Table Using Hierarchy Methods</span></span>](lesson-2-3-querying-a-hierarchical-table-using-hierarchy-methods.md)  
  
  
