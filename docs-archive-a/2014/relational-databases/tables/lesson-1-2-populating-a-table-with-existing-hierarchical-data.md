---
title: Remplissage d’une table avec des données hiérarchiques existantes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: fd943d84-dbe6-4a05-912b-c88164998d80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 966548b11ad4697abc06de5c5c239a511f80b7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696704"
---
# <a name="populating-a-table-with-existing-hierarchical-data"></a><span data-ttu-id="c582d-102">Remplissage d'une table avec des données hiérarchiques existantes</span><span class="sxs-lookup"><span data-stu-id="c582d-102">Populating a Table with Existing Hierarchical Data</span></span>
  <span data-ttu-id="c582d-103"> Cette tâche crée une table et la remplit avec les données de la table **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="c582d-103">This task creates a new table and populates it with the data in the **EmployeeDemo** table.</span></span> <span data-ttu-id="c582d-104">Les étapes de cette tâche sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c582d-104">This task has the following steps:</span></span>  
  
-   <span data-ttu-id="c582d-105">Créez une nouvelle table qui contient une colonne `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="c582d-105">Create a new table that contains a `hierarchyid` column.</span></span> <span data-ttu-id="c582d-106">Cette colonne pourrait remplacer les colonnes **EmployeeID** et **ManagerID** existantes.</span><span class="sxs-lookup"><span data-stu-id="c582d-106">This column could replace the existing **EmployeeID** and **ManagerID** columns.</span></span> <span data-ttu-id="c582d-107">Toutefois, vous conserverez ces colonnes.</span><span class="sxs-lookup"><span data-stu-id="c582d-107">However, you will retain those columns.</span></span> <span data-ttu-id="c582d-108">Cela s'explique par le fait que les applications existantes peuvent faire référence à ces colonnes. De même, cela peut vous aider à comprendre les données après le transfert.</span><span class="sxs-lookup"><span data-stu-id="c582d-108">This is because existing applications might refer to those columns, and also to help you understand the data after the transfer.</span></span> <span data-ttu-id="c582d-109">La définition de table spécifie que **OrgNode** est la clé primaire, ce qui exige que la colonne contienne des valeurs uniques.</span><span class="sxs-lookup"><span data-stu-id="c582d-109">The table definition specifies that **OrgNode** is the primary key, which requires the column to contain unique values.</span></span> <span data-ttu-id="c582d-110">L’index cluster sur la colonne **OrgNode** stockera la date dans la séquence **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="c582d-110">The clustered index on the **OrgNode** column will store the date in **OrgNode** sequence.</span></span>  
  
-   <span data-ttu-id="c582d-111">Créez une table temporaire utilisée pour effectuer le suivi du nombre d'employés dont chaque responsable est le supérieur direct.</span><span class="sxs-lookup"><span data-stu-id="c582d-111">Create a temporary table that is used to track how many employees report directly to each manager.</span></span>  
  
-   <span data-ttu-id="c582d-112">Remplissez la nouvelle table en utilisant les données de la table **EmployeeDemo** .</span><span class="sxs-lookup"><span data-stu-id="c582d-112">Populate the new table by using data from the **EmployeeDemo** table.</span></span>  
  
### <a name="to-create-a-new-table-named-neworg"></a><span data-ttu-id="c582d-113">Pour créer une table nommée NewOrg</span><span class="sxs-lookup"><span data-stu-id="c582d-113">To create a new table named NewOrg</span></span>  
  
-   <span data-ttu-id="c582d-114">Dans une fenêtre de l’Éditeur de requête, exécutez le code suivant pour créer une table nommée **HumanResources.NewOrg**:</span><span class="sxs-lookup"><span data-stu-id="c582d-114">In a Query Editor window, run the following code to create a new table named **HumanResources.NewOrg**:</span></span>  
  
    ```  
    CREATE TABLE NewOrg  
    (  
      OrgNode hierarchyid,  
      EmployeeID int,  
      LoginID nvarchar(50),  
      ManagerID int  
    CONSTRAINT PK_NewOrg_OrgNode  
      PRIMARY KEY CLUSTERED (OrgNode)  
    );  
    GO  
    ```  
  
### <a name="to-create-a-temporary-table-named-children"></a><span data-ttu-id="c582d-115">Pour créer une table temporaire nommée #Children</span><span class="sxs-lookup"><span data-stu-id="c582d-115">To create a temporary table named #Children</span></span>  
  
1.  <span data-ttu-id="c582d-116">Créez une table temporaire nommée **#Children** avec une colonne nommée **Num** qui contiendra le nombre d’enfants pour chaque nœud :</span><span class="sxs-lookup"><span data-stu-id="c582d-116">Create a temporary table named **#Children** with a column named **Num** that will contain the number of children for each node:</span></span>  
  
    ```  
    CREATE TABLE #Children   
       (  
        EmployeeID int,  
        ManagerID int,  
        Num int  
    );  
    GO  
    ```  
  
2.  <span data-ttu-id="c582d-117">Ajoutez un index qui accélérera considérablement la requête qui remplit la table **NewOrg** :</span><span class="sxs-lookup"><span data-stu-id="c582d-117">Add an index that will significantly speed up the query that populates the **NewOrg** table:</span></span>  
  
    ```  
    CREATE CLUSTERED INDEX tmpind ON #Children(ManagerID, EmployeeID);  
    GO  
    ```  
  
### <a name="to-populate-the-neworg-table"></a><span data-ttu-id="c582d-118">Pour remplir la table NewOrg</span><span class="sxs-lookup"><span data-stu-id="c582d-118">To populate the NewOrg table</span></span>  
  
1.  <span data-ttu-id="c582d-119">Les requêtes récursives interdisent les sous-requêtes avec agrégats.</span><span class="sxs-lookup"><span data-stu-id="c582d-119">Recursive queries forbid subqueries with aggregates.</span></span> <span data-ttu-id="c582d-120">À la place, remplissez la table **#Children** avec le code suivant, qui utilise la méthode [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) pour remplir la colonne **Num** :</span><span class="sxs-lookup"><span data-stu-id="c582d-120">Instead, populate the **#Children** table with the following code, which uses the [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) method to populate the **Num** column:</span></span>  
  
    ```  
    INSERT #Children (EmployeeID, ManagerID, Num)  
    SELECT EmployeeID, ManagerID,  
      ROW_NUMBER() OVER (PARTITION BY ManagerID ORDER BY ManagerID)   
    FROM EmployeeDemo  
    GO  
  
    ```  
  
2.  <span data-ttu-id="c582d-121">Examinez la table **#Children** .</span><span class="sxs-lookup"><span data-stu-id="c582d-121">Review the **#Children** table.</span></span> <span data-ttu-id="c582d-122">Notez la façon dont la colonne **Num** contient des numéros séquentiels pour chaque responsable.</span><span class="sxs-lookup"><span data-stu-id="c582d-122">Note how the **Num** column contains sequential numbers for each manager.</span></span>  
  
    ```  
    SELECT * FROM #Children ORDER BY ManagerID, Num  
    GO  
  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     `EmployeeID ManagerID Num`  
  
     `---------- --------- ---`  
  
     `1        NULL       1`  
  
     `2         1         1`  
  
     `3         1         2`  
  
     `4         2         1`  
  
     `5         2         2`  
  
     `6         2         3`  
  
     `7         3         1`  
  
     `8         3         2`  
  
     `9         4         1`  
  
     `10        4         2`  
  
3.  <span data-ttu-id="c582d-123">Remplissez la table **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="c582d-123">Populate the **NewOrg** table.</span></span> <span data-ttu-id="c582d-124">Utilisez les méthodes GetRoot et ToString pour concaténer les valeurs **num** au `hierarchyid` format, puis mettez à jour la colonne **OrgNode** avec les valeurs hiérarchiques résultantes :</span><span class="sxs-lookup"><span data-stu-id="c582d-124">Use the GetRoot and ToString methods to concatenate the **Num** values into the `hierarchyid` format, and then update the **OrgNode** column with the resultant hierarchical values:</span></span>  
  
    ```  
    WITH paths(path, EmployeeID)   
    AS (  
    -- This section provides the value for the root of the hierarchy  
    SELECT hierarchyid::GetRoot() AS OrgNode, EmployeeID   
    FROM #Children AS C   
    WHERE ManagerID IS NULL   
  
    UNION ALL   
    -- This section provides values for all nodes except the root  
    SELECT   
    CAST(p.path.ToString() + CAST(C.Num AS varchar(30)) + '/' AS hierarchyid),   
    C.EmployeeID  
    FROM #Children AS C   
    JOIN paths AS p   
       ON C.ManagerID = P.EmployeeID   
    )  
    INSERT NewOrg (OrgNode, O.EmployeeID, O.LoginID, O.ManagerID)  
    SELECT P.path, O.EmployeeID, O.LoginID, O.ManagerID  
    FROM EmployeeDemo AS O   
    JOIN Paths AS P   
       ON O.EmployeeID = P.EmployeeID  
    GO  
  
    ```  
  
4.  <span data-ttu-id="c582d-125">Une colonne `hierarchyid` est plus compréhensible lorsque vous la convertissez au format caractère.</span><span class="sxs-lookup"><span data-stu-id="c582d-125">A `hierarchyid` column is more understandable when you convert it to character format.</span></span> <span data-ttu-id="c582d-126">Vérifiez les données de la table **NewOrg** en exécutant le code suivant, qui contient deux représentations de la colonne **OrgNode** :</span><span class="sxs-lookup"><span data-stu-id="c582d-126">Review the data in the **NewOrg** table by executing the following code, which contains two representations of the **OrgNode** column:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode, *   
    FROM NewOrg   
    ORDER BY LogicalNode;  
    GO  
  
    ```  
  
     <span data-ttu-id="c582d-127">La colonne **LogicalNode** convertit la `hierarchyid` colonne en un format de texte plus lisible qui représente la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="c582d-127">The **LogicalNode** column converts the `hierarchyid` column into a more readable text form that represents the hierarchy.</span></span> <span data-ttu-id="c582d-128">Dans les tâches restantes, vous utiliserez la méthode `ToString()` pour afficher le format logique des colonnes `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="c582d-128">In the remaining tasks, you will use the `ToString()` method to show the logical format of the `hierarchyid` columns.</span></span>  
  
5.  <span data-ttu-id="c582d-129">Supprimez la table temporaire, qui n'est plus nécessaire :</span><span class="sxs-lookup"><span data-stu-id="c582d-129">Drop the temporary table, which is no longer needed:</span></span>  
  
    ```  
    DROP TABLE #Children  
    GO  
    ```  
  
 <span data-ttu-id="c582d-130">La tâche suivante créera des index pour prendre en charge la structure hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="c582d-130">The next task will create indexes to support the hierarchical structure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c582d-131">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="c582d-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c582d-132">Optimisation de la table NewOrg</span><span class="sxs-lookup"><span data-stu-id="c582d-132">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
  
