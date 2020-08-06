---
title: Étude de la structure actuelle de la table Employee | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- examining the current structure of the employee
ms.assetid: d546a820-105a-417d-ac35-44a6d1d70ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7f63773ebc1f28fb24f8f1000c3f87ee4d50544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599848"
---
# <a name="examining-the-current-structure-of-the-employee-table"></a><span data-ttu-id="985a9-102">Étude de la structure actuelle de la table Employee</span><span class="sxs-lookup"><span data-stu-id="985a9-102">Examining the Current Structure of the Employee Table</span></span>
  <span data-ttu-id="985a9-103"> L’exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] contient une table **Employee** dans le schéma **HumanResources**.</span><span class="sxs-lookup"><span data-stu-id="985a9-103">The sample [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database contains an **Employee** table in the **HumanResources** schema.</span></span> <span data-ttu-id="985a9-104">Afin d'éviter de modifier la table d'origine, cette étape effectue une copie de la table **Employee** , nommée **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="985a9-104">To avoid changing the original table, this step makes a copy of the **Employee** table named **EmployeeDemo**.</span></span> <span data-ttu-id="985a9-105">Pour simplifier l'exemple, vous ne copiez que cinq colonnes de la table d'origine.</span><span class="sxs-lookup"><span data-stu-id="985a9-105">To simplify the example, you only copy five columns from the original table.</span></span> <span data-ttu-id="985a9-106">Ensuite, vous interrogez la table **HumanResources. EmployeeDemo** pour vérifier comment les données sont structurées dans une table sans utiliser le `hierarchyid` type de données.</span><span class="sxs-lookup"><span data-stu-id="985a9-106">Then, you query the **HumanResources.EmployeeDemo** table to review how the data is structured in a table without using the `hierarchyid` data type.</span></span>  
  
### <a name="to-copy-the-employee-table"></a><span data-ttu-id="985a9-107">Pour copier la table Employee</span><span class="sxs-lookup"><span data-stu-id="985a9-107">To copy the Employee table</span></span>  
  
1.  <span data-ttu-id="985a9-108">Dans une fenêtre de l'Éditeur de requête, exécutez le code suivant pour copier la structure et les données de la table **Employee** dans une nouvelle table nommée **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="985a9-108">In a Query Editor window, run the following code to copy the table structure and data from the **Employee** table into a new table named **EmployeeDemo**.</span></span>  
  
    ```  
    USE AdventureWorks ;  
    GO  
  
    SELECT EmployeeID, LoginID, ManagerID, Title, HireDate   
    INTO HumanResources.EmployeeDemo   
    FROM HumanResources.Employee ;  
    GO  
    ```  
  
### <a name="to-examine-the-structure-and-data-of-the-employeedemo-table"></a><span data-ttu-id="985a9-109">Pour examiner la structure et les données de la table EmployeeDemo</span><span class="sxs-lookup"><span data-stu-id="985a9-109">To examine the structure and data of the EmployeeDemo table</span></span>  
  
-   <span data-ttu-id="985a9-110">Cette nouvelle table **EmployeeDemo** représente une table classique dans une base de données existante que vous pouvez souhaiter migrer vers une nouvelle structure.</span><span class="sxs-lookup"><span data-stu-id="985a9-110">This new **EmployeeDemo** table represents a typical table in an existing database that you might want to migrate to a new structure.</span></span> <span data-ttu-id="985a9-111">Dans une fenêtre de l'Éditeur de requête, exécutez le code suivant pour voir comment la table utilise une jointure réflexive pour afficher les relations employé/responsable :</span><span class="sxs-lookup"><span data-stu-id="985a9-111">In a Query Editor window, run the following code to show how the table uses a self join to display the employee/manager relationships:</span></span>  
  
    ```  
    SELECT   
         Mgr.EmployeeID AS MgrID, Mgr.LoginID AS Manager,   
         Emp.EmployeeID AS E_ID, Emp.LoginID, Emp.Title  
    FROM HumanResources.EmployeeDemo AS Emp  
    LEFT JOIN HumanResources.EmployeeDemo AS Mgr  
    ON Emp.ManagerID = Mgr.EmployeeID  
    ORDER BY MgrID, E_ID  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    MgrID Manager                 E_ID LoginID                  Title  
    NULL NULL                      109 adventure-works\ken0     Chief Executive Officer  
    3    adventure-works\roberto0  4   adventure-works\rob0     Senior Tool Designer  
    3    adventure-works\roberto0  9   adventure-works\gail0    Design Engineer  
    3    adventure-works\roberto0  11  adventure-works\jossef0  Design Engineer  
    3    adventure-works\roberto0  158 adventure-works\dylan0   Research and Development Manager  
    3    adventure-works\roberto0  263 adventure-works\ovidiu0  Senior Tool Designer  
    3    adventure-works\roberto0  267 adventure-works\michael8 Senior Design Engineer  
    3    adventure-works\roberto0  270 adventure-works\sharon0  Design Engineer  
    6    adventure-works\david0    2   adventure-works\kevin0   Marketing Assistant  
    ...  
    ```  
  
     <span data-ttu-id="985a9-112">Les résultats se poursuivent pour un total de 290 lignes.</span><span class="sxs-lookup"><span data-stu-id="985a9-112">The results continue for a total of 290 rows.</span></span>  
  
 <span data-ttu-id="985a9-113">Notez que le résultat de la clause `ORDER BY` a provoqué le regroupement des subordonnés directs de chaque niveau de gestion.</span><span class="sxs-lookup"><span data-stu-id="985a9-113">Notice that the `ORDER BY` clause caused the output to list the direct reports of each management level together.</span></span> <span data-ttu-id="985a9-114">Par exemple, les sept subordonnés directs de **MgrID** 3 (roberto0) sont regroupés les uns à côté des autres.</span><span class="sxs-lookup"><span data-stu-id="985a9-114">For instance, all seven of the direct reports of **MgrID** 3 (roberto0) are listed adjacent to each other.</span></span> <span data-ttu-id="985a9-115">Il est beaucoup plus difficile, bien que pas impossible, de regrouper tous ceux dont **MgrID** 3 est le supérieur final.</span><span class="sxs-lookup"><span data-stu-id="985a9-115">Although not impossible, it is much more difficult to group all those who eventually report to **MgrID** 3.</span></span>  
  
 <span data-ttu-id="985a9-116">Dans la tâche suivante, nous créerons une table avec un type de données `hierarchyid` et déplacerons les données dans la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="985a9-116">In the next task, we will create a new table with a `hierarchyid` data type, and move the data into the new table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="985a9-117">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="985a9-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="985a9-118">Remplissage d'une table avec des données hiérarchiques existantes</span><span class="sxs-lookup"><span data-stu-id="985a9-118">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
  
