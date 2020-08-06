---
title: Création d’une table à l’aide du type de données hierarchyid | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 0d1f361f-336c-4571-99d1-f4813b2d9fc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2c9b59795949e11cabd21b0be8de844b33d73c37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708148"
---
# <a name="creating-a-table-using-the-hierarchyid-data-type"></a><span data-ttu-id="f9e00-102">Création d'une table à l'aide du type de données hierarchyid</span><span class="sxs-lookup"><span data-stu-id="f9e00-102">Creating a Table Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="f9e00-103">L'exemple suivant crée une table nommée EmployeeOrg qui inclut des données sur les employés ainsi que leur hiérarchie de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="f9e00-103">The following example creates a table named EmployeeOrg, which includes employee data together with their reporting hierarchy.</span></span> <span data-ttu-id="f9e00-104">Cet exemple crée la table dans la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , mais cela est facultatif.</span><span class="sxs-lookup"><span data-stu-id="f9e00-104">The example creates the table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, but that is optional.</span></span> <span data-ttu-id="f9e00-105">Pour que l'exemple reste simple, cette table ne comporte que cinq colonnes :</span><span class="sxs-lookup"><span data-stu-id="f9e00-105">To keep the example simple, this table includes only five columns:</span></span>  
  
-   <span data-ttu-id="f9e00-106">OrgNode est une colonne `hierarchyid` qui stocke la relation hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="f9e00-106">OrgNode is a `hierarchyid` column that stores the hierarchical relationship.</span></span>  
  
-   <span data-ttu-id="f9e00-107">OrgLevel est une colonne calculée en fonction de la colonne OrgNode qui stocke chaque niveau de nœuds dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="f9e00-107">OrgLevel is a computed column, based on the OrgNode column that stores each nodes level in the hierarchy.</span></span> <span data-ttu-id="f9e00-108">Elle sera utilisée pour un index à largeur prioritaire.</span><span class="sxs-lookup"><span data-stu-id="f9e00-108">It will be used for a breadth-first index.</span></span>  
  
-   <span data-ttu-id="f9e00-109">EmployeeID contient le numéro d'identification d'employé qui est habituellement utilisé pour les applications telles que les salaires.</span><span class="sxs-lookup"><span data-stu-id="f9e00-109">EmployeeID contains the typical employee identification number that is used for applications such as payroll.</span></span> <span data-ttu-id="f9e00-110">Dans le nouveau développement d'applications, les applications peuvent utiliser la colonne OrgNode ; cette colonne EmployeeID séparée n'est donc pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f9e00-110">In new application development, applications can use the OrgNode column and this separate EmployeeID column is not needed.</span></span>  
  
-   <span data-ttu-id="f9e00-111">EmpName contient le nom de l'employé.</span><span class="sxs-lookup"><span data-stu-id="f9e00-111">EmpName contains the name of the employee.</span></span>  
  
-   <span data-ttu-id="f9e00-112">Titre contient le titre de l'employé.</span><span class="sxs-lookup"><span data-stu-id="f9e00-112">Title contains the title of the employee.</span></span>  
  
### <a name="to-create-the-employeeorg-table"></a><span data-ttu-id="f9e00-113">Pour créer la table EmployeeOrg</span><span class="sxs-lookup"><span data-stu-id="f9e00-113">To create the EmployeeOrg table</span></span>  
  
1.  <span data-ttu-id="f9e00-114">Dans une fenêtre de l'Éditeur de requête, exécutez le code suivant pour créer la table `EmployeeOrg` .</span><span class="sxs-lookup"><span data-stu-id="f9e00-114">In a Query Editor window, run the following code to create the `EmployeeOrg` table.</span></span> <span data-ttu-id="f9e00-115">Lorsque la colonne `OrgNode` est définie comme clé primaire avec un index cluster, un index à profondeur prioritaire est créé :</span><span class="sxs-lookup"><span data-stu-id="f9e00-115">Specifying the `OrgNode` column as the primary key with a clustered index will create a depth-first index:</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    CREATE TABLE HumanResources.EmployeeOrg  
    (  
       OrgNode hierarchyid PRIMARY KEY CLUSTERED,  
       OrgLevel AS OrgNode.GetLevel(),  
       EmployeeID int UNIQUE NOT NULL,  
       EmpName varchar(20) NOT NULL,  
       Title varchar(20) NULL  
    ) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="f9e00-116">Exécutez le code suivant pour créer un index composite sur les colonnes `OrgLevel` et `OrgNode` afin de prendre en charge des recherches à largeur prioritaire efficaces :</span><span class="sxs-lookup"><span data-stu-id="f9e00-116">Run the following code to create a composite index on the `OrgLevel` and `OrgNode` columns to support efficient breadth-first searches:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmployeeOrgNc1   
    ON HumanResources.EmployeeOrg(OrgLevel, OrgNode) ;  
    GO  
    ```  
  
 <span data-ttu-id="f9e00-117">La table est maintenant prête à recevoir les données.</span><span class="sxs-lookup"><span data-stu-id="f9e00-117">The table is now ready for data.</span></span> <span data-ttu-id="f9e00-118">La tâche suivante remplira la table à l'aide de méthodes hiérarchiques.</span><span class="sxs-lookup"><span data-stu-id="f9e00-118">The next task will populate the table by using hierarchical methods.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f9e00-119">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="f9e00-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f9e00-120">Remplissage d'une table hiérarchique utilisant des méthodes hiérarchiques</span><span class="sxs-lookup"><span data-stu-id="f9e00-120">Populating a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-2-populating-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
