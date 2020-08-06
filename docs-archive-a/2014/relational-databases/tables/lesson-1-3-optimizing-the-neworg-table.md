---
title: Optimisation de la table NewOrg | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- optimizing tables
ms.assetid: 89ff6d37-94c0-4773-8be9-dde943fff023
author: stevestein
ms.author: sstein
ms.openlocfilehash: 39c09a3a73051e7a61f3a62a125232d83d1570c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599845"
---
# <a name="optimizing-the-neworg-table"></a><span data-ttu-id="4508f-102">Optimisation de la table NewOrg</span><span class="sxs-lookup"><span data-stu-id="4508f-102">Optimizing the NewOrg Table</span></span>
  <span data-ttu-id="4508f-103">La table **NewOrd** que vous avez créée dans la tâche [remplissage d’une table avec des données hiérarchiques existantes](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) contient toutes les informations relatives aux employés et représente la structure hiérarchique à l’aide d’un `hierarchyid` type de données.</span><span class="sxs-lookup"><span data-stu-id="4508f-103">The **NewOrd** table that you created in the [Populating a Table with Existing Hierarchical Data](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) task contains all the employee information, and represents the hierarchical structure by using a `hierarchyid` data type.</span></span> <span data-ttu-id="4508f-104">Cette tâche ajoute de nouveaux index pour prendre en charge les recherches sur la colonne `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="4508f-104">This task adds new indexes to support searches on the `hierarchyid` column.</span></span>  
  
## <a name="clustered-index"></a><span data-ttu-id="4508f-105">Index cluster</span><span class="sxs-lookup"><span data-stu-id="4508f-105">Clustered Index</span></span>  
 <span data-ttu-id="4508f-106">La `hierarchyid` colonne (**OrgNode**) est la clé primaire de la table **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="4508f-106">The `hierarchyid` column (**OrgNode**) is the primary key for the **NewOrg** table.</span></span> <span data-ttu-id="4508f-107">Quand la table a été créée, elle contenait un index cluster nommé **PK_NewOrg_OrgNode** pour forcer l’unicité de la colonne **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="4508f-107">When the table was created, it contained a clustered index named **PK_NewOrg_OrgNode** to enforce the uniqueness of the **OrgNode** column.</span></span> <span data-ttu-id="4508f-108">Cet index cluster prend également en charge une recherche à profondeur prioritaire de la table.</span><span class="sxs-lookup"><span data-stu-id="4508f-108">This clustered index also supports a depth-first search of the table.</span></span>  
  
## <a name="nonclustered-index"></a><span data-ttu-id="4508f-109">Index non cluster</span><span class="sxs-lookup"><span data-stu-id="4508f-109">Nonclustered Index</span></span>  
 <span data-ttu-id="4508f-110">Cette étape crée deux index non cluster pour prendre en charge des recherches typiques.</span><span class="sxs-lookup"><span data-stu-id="4508f-110">This step creates two nonclustered indexes to support typical searches.</span></span>  
  
#### <a name="to-index-the-neworg-table-for-efficient-searches"></a><span data-ttu-id="4508f-111">Pour indexer la table NewOrg en vue d'effectuer recherches efficaces</span><span class="sxs-lookup"><span data-stu-id="4508f-111">To index the NewOrg table for efficient searches</span></span>  
  
1.  <span data-ttu-id="4508f-112">Pour faciliter les requêtes au même niveau de la hiérarchie, utilisez la méthode [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) pour créer une colonne calculée qui contient le niveau dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="4508f-112">To help queries at the same level in the hierarchy, use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to create a computed column that contains the level in the hierarchy.</span></span> <span data-ttu-id="4508f-113">Créez ensuite un index composite sur le niveau et `Hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="4508f-113">Then, create a composite index on the level and the `Hierarchyid`.</span></span> <span data-ttu-id="4508f-114">Exécutez le code suivant pour créer la colonne calculée et l'index à largeur prioritaire :</span><span class="sxs-lookup"><span data-stu-id="4508f-114">Run the following code to create the computed column and the breadth-first index:</span></span>  
  
    ```  
    ALTER TABLE NewOrg   
       ADD H_Level AS OrgNode.GetLevel() ;  
    CREATE UNIQUE INDEX EmpBFInd   
       ON NewOrg(H_Level, OrgNode) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="4508f-115">Créez un index unique sur la colonne **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="4508f-115">Create a unique index on the **EmployeeID** column.</span></span> <span data-ttu-id="4508f-116">Il s’agit de la recherche singleton classique d’un seul employé par numéro **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="4508f-116">This is the traditional singleton lookup of a single employee by **EmployeeID** number.</span></span> <span data-ttu-id="4508f-117">Exécutez le code suivant pour créer un index sur **EmployeeID**:</span><span class="sxs-lookup"><span data-stu-id="4508f-117">Run the following code to create an index on **EmployeeID**:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmpIDs_unq ON NewOrg(EmployeeID) ;  
    GO  
    ```  
  
3.  <span data-ttu-id="4508f-118">Exécutez le code suivant pour récupérer des données de la table dans l'ordre de chacun des trois index :</span><span class="sxs-lookup"><span data-stu-id="4508f-118">Run the following code to retrieve data from the table in the order of each of the three indexes:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID  
    FROM NewOrg   
    ORDER BY OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY H_Level, OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY EmployeeID;  
    GO  
    ```  
  
4.  <span data-ttu-id="4508f-119">Comparez les jeux de résultats pour voir comment l'ordre est stocké dans chaque type d'index.</span><span class="sxs-lookup"><span data-stu-id="4508f-119">Compare the result sets to see how the order is stored in each type of index.</span></span> <span data-ttu-id="4508f-120">Seules les quatre premières lignes de chaque de sortie suivent.</span><span class="sxs-lookup"><span data-stu-id="4508f-120">Only the first four rows of each output follow.</span></span>  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     <span data-ttu-id="4508f-121">Index à profondeur prioritaire : les enregistrements d'employés sont stockés à proximité de leur responsable.</span><span class="sxs-lookup"><span data-stu-id="4508f-121">Depth-first index: Employee records are stored adjacent to their manager.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     <span data-ttu-id="4508f-122">Index avec**EmployeeID**prioritaire : les lignes sont stockées dans l’ordre des **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="4508f-122">**EmployeeID**-first index: Rows are stored in **EmployeeID** sequence.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
> [!NOTE]  
>  <span data-ttu-id="4508f-123">Pour les diagrammes qui affichent la différence entre un index à profondeur prioritaire et un index à largeur prioritaire, consultez [Données hiérarchiques &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4508f-123">For diagrams that show the difference between a depth-first index and a breadth-first index, see [Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span></span>  
  
#### <a name="to-drop-the-unnecessary-columns"></a><span data-ttu-id="4508f-124">Pour supprimer les colonnes inutiles</span><span class="sxs-lookup"><span data-stu-id="4508f-124">To drop the unnecessary columns</span></span>  
  
1.  <span data-ttu-id="4508f-125">La colonne **ManagerID** représente la relation employé/responsable, qui est maintenant représentée par la colonne **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="4508f-125">The **ManagerID** column represents the employee/manager relationship, which is now represented by the **OrgNode** column.</span></span> <span data-ttu-id="4508f-126">Si les autres applications n’ont pas besoin de la colonne **ManagerID** , vous pouvez envisager de la supprimer à l’aide de l’instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="4508f-126">If other applications do not need the **ManagerID** column, consider dropping it by using the following statement:</span></span>  
  
    ```  
    ALTER TABLE NewOrg DROP COLUMN ManagerID ;  
    GO  
    ```  
  
2.  <span data-ttu-id="4508f-127">La colonne **EmployeeID** est également redondante.</span><span class="sxs-lookup"><span data-stu-id="4508f-127">The **EmployeeID** column is also redundant.</span></span> <span data-ttu-id="4508f-128">La colonne **OrgNode** identifie chaque employé de façon univoque.</span><span class="sxs-lookup"><span data-stu-id="4508f-128">The **OrgNode** column uniquely identifies each employee.</span></span> <span data-ttu-id="4508f-129">Si les autres applications n’ont pas besoin de la colonne **EmployeeID** , vous pouvez envisager de supprimer l’index puis la colonne, en utilisant le code suivant :</span><span class="sxs-lookup"><span data-stu-id="4508f-129">If other applications do not need the **EmployeeID** column, consider dropping the index and then the column by using the following code:</span></span>  
  
    ```  
    DROP INDEX EmpIDs_unq ON NewOrg ;  
    ALTER TABLE NewOrg DROP COLUMN EmployeeID ;  
    GO  
    ```  
  
#### <a name="to-replace-the-original-table-with-the-new-table"></a><span data-ttu-id="4508f-130">Pour remplacer la table d'origine par la nouvelle table</span><span class="sxs-lookup"><span data-stu-id="4508f-130">To replace the original table with the new table</span></span>  
  
1.  <span data-ttu-id="4508f-131">Si votre table d’origine contenait des index ou contraintes supplémentaires, ajoutez-les à la table **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="4508f-131">If your original table contained any additional indexes or constraints, add them to the **NewOrg** table.</span></span>  
  
2.  <span data-ttu-id="4508f-132">Remplacez l’ancienne table **EmployeeDemo** par la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="4508f-132">Replace the old **EmployeeDemo** table with the new table.</span></span> <span data-ttu-id="4508f-133">Exécutez le code suivant pour supprimer l'ancienne table, puis renommez la nouvelle table avec l'ancien nom :</span><span class="sxs-lookup"><span data-stu-id="4508f-133">Run the following code to drop the old table, and then rename the new table with the old name:</span></span>  
  
    ```  
    DROP TABLE EmployeeDemo ;  
    GO  
    sp_rename 'NewOrg', EmployeeDemo ;  
    GO  
    ```  
  
3.  <span data-ttu-id="4508f-134">Exécutez le code suivant pour examiner la table finale :</span><span class="sxs-lookup"><span data-stu-id="4508f-134">Run the following code to examine the final table:</span></span>  
  
    ```  
    SELECT * FROM EmployeeDemo ;  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4508f-135">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="4508f-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4508f-136">Résumé : Conversion d’une table en une structure hiérarchique</span><span class="sxs-lookup"><span data-stu-id="4508f-136">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
  
