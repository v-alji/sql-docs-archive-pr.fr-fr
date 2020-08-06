---
title: Création d’une table (tutoriel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating tables
ms.assetid: 653f2dd3-36a2-4bd5-8703-71a57d244661
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: c772f2527bd5ddb8a6759cbaa72d8aed9277f5cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611436"
---
# <a name="creating-a-table-tutorial"></a><span data-ttu-id="771a0-102">Création d'une table (Didacticiel)</span><span class="sxs-lookup"><span data-stu-id="771a0-102">Creating a Table (Tutorial)</span></span>
  <span data-ttu-id="771a0-103">Pour créer une table, vous devez fournir un nom pour la table et les noms et les types de données de chaque colonne dans la table.</span><span class="sxs-lookup"><span data-stu-id="771a0-103">To create a table, you must provide a name for the table, and the names and data types of each column in the table.</span></span> <span data-ttu-id="771a0-104">Il est aussi recommandé d'indiquer si les valeurs Null sont autorisées dans chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="771a0-104">It is also a good practice to indicate whether null values are allowed in each column.</span></span>  
  
 <span data-ttu-id="771a0-105">La plupart des tables possèdent une clé primaire constituée d'une ou plusieurs colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="771a0-105">Most tables have a primary key, made up of one or more columns of the table.</span></span> <span data-ttu-id="771a0-106">Une clé primaire est toujours unique.</span><span class="sxs-lookup"><span data-stu-id="771a0-106">A primary key is always unique.</span></span> <span data-ttu-id="771a0-107">Le [!INCLUDE[ssDE](../includes/ssde-md.md)] applique la restriction qui veut que les valeurs de clé primaire ne peuvent pas être répétées dans la table.</span><span class="sxs-lookup"><span data-stu-id="771a0-107">The [!INCLUDE[ssDE](../includes/ssde-md.md)] will enforce the restriction that any primary key value cannot be repeated in the table.</span></span>  
  
 <span data-ttu-id="771a0-108">Pour obtenir une liste des types de données et des liens contenant une description individuelle, consultez [Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="771a0-108">For a list of data types and links for a description of each, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="771a0-109">Vous pouvez configurer le [!INCLUDE[ssDE](../includes/ssde-md.md)] pour qu’il respecte la casse ou non.</span><span class="sxs-lookup"><span data-stu-id="771a0-109">The [!INCLUDE[ssDE](../includes/ssde-md.md)] can be installed as case sensitive or non-case sensitive.</span></span> <span data-ttu-id="771a0-110">Si vous installez le [!INCLUDE[ssDE](../includes/ssde-md.md)] pour qu’il respecte la casse, les noms des objets doivent toujours avoir la même casse.</span><span class="sxs-lookup"><span data-stu-id="771a0-110">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as case sensitive, object names must always have the same case.</span></span> <span data-ttu-id="771a0-111">Par exemple, une table nommée OrderData est différente d'une table nommée ORDERDATA.</span><span class="sxs-lookup"><span data-stu-id="771a0-111">For example, a table named OrderData is a different table from a table named ORDERDATA.</span></span> <span data-ttu-id="771a0-112">Si le [!INCLUDE[ssDE](../includes/ssde-md.md)] ne respecte pas la casse, ces deux noms de tables sont considérés comme une seule et même table, et ce nom ne peut être utilisé qu’une fois.</span><span class="sxs-lookup"><span data-stu-id="771a0-112">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as non-case sensitive, those two table names are considered to be the same table, and that name can only be used one time.</span></span>  
  
### <a name="to-create-a-database-to-contain-the-new-table"></a><span data-ttu-id="771a0-113">Pour créer une base de données qui contient la nouvelle table</span><span class="sxs-lookup"><span data-stu-id="771a0-113">To create a database to contain the new table</span></span>  
  
-   <span data-ttu-id="771a0-114">Entrez le code suivant dans une fenêtre de l'Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="771a0-114">Enter the following code into a Query Editor window.</span></span>  
  
    ```  
    USE master;  
    GO  
  
    --Delete the TestData database if it exists.  
    IF EXISTS(SELECT * from sys.databases WHERE name='TestData')  
    BEGIN  
        DROP DATABASE TestData;  
    END  
  
    --Create a new database called TestData.  
    CREATE DATABASE TestData;  
    Press the F5 key to execute the code and create the database.  
    ```  
  
### <a name="switch-the-query-editor-connection-to-the-testdata-database"></a><span data-ttu-id="771a0-115">Passer la connexion de l'Éditeur de requête à la base de données TestData</span><span class="sxs-lookup"><span data-stu-id="771a0-115">Switch the Query Editor connection to the TestData database</span></span>  
  
-   <span data-ttu-id="771a0-116">Dans une fenêtre Éditeur de requêtes, tapez et exécutez le code suivant pour modifier votre connexion à la base de données `TestData` .</span><span class="sxs-lookup"><span data-stu-id="771a0-116">In a Query Editor window, type and execute the following code to change your connection to the `TestData` database.</span></span>  
  
    ```  
    USE TestData  
    GO  
    ```  
  
### <a name="to-create-a-table"></a><span data-ttu-id="771a0-117">Pour créer une table</span><span class="sxs-lookup"><span data-stu-id="771a0-117">To create a table</span></span>  
  
-   <span data-ttu-id="771a0-118">Dans une fenêtre Éditeur de requêtes, tapez et exécutez le code suivant pour créer une simple table nommée `Products`.</span><span class="sxs-lookup"><span data-stu-id="771a0-118">In a Query Editor window, type and execute the following code to create a simple table named `Products`.</span></span> <span data-ttu-id="771a0-119">Les colonnes de la table sont nommées `ProductID`, `ProductName`, `Price`, et `ProductDescription`.</span><span class="sxs-lookup"><span data-stu-id="771a0-119">The columns in the table are named `ProductID`, `ProductName`, `Price`, and `ProductDescription`.</span></span> <span data-ttu-id="771a0-120">La colonne `ProductID` est la clé primaire de la table.</span><span class="sxs-lookup"><span data-stu-id="771a0-120">The `ProductID` column is the primary key of the table.</span></span> <span data-ttu-id="771a0-121">`int`, `varchar(25)`, `money`et `text` sont tous des types de données.</span><span class="sxs-lookup"><span data-stu-id="771a0-121">`int`, `varchar(25)`, `money`, and `text` are all data types.</span></span> <span data-ttu-id="771a0-122">Seules les colonnes `Price` et `ProductionDescription` peuvent n'avoir aucune données lors de l'insertion ou de la modification d'une ligne.</span><span class="sxs-lookup"><span data-stu-id="771a0-122">Only the `Price` and `ProductionDescription` columns can have no data when a row is inserted or changed.</span></span> <span data-ttu-id="771a0-123">Cette instruction contient un élément facultatif (`dbo.`) appelé un schéma.</span><span class="sxs-lookup"><span data-stu-id="771a0-123">This statement contains an optional element (`dbo.`) called a schema.</span></span> <span data-ttu-id="771a0-124">Le schéma est l'objet de base de données qui est propriétaire de la table.</span><span class="sxs-lookup"><span data-stu-id="771a0-124">The schema is the database object that owns the table.</span></span> <span data-ttu-id="771a0-125">Si vous êtes administrateur, `dbo` est le schéma par défaut.</span><span class="sxs-lookup"><span data-stu-id="771a0-125">If you are an administrator, `dbo` is the default schema.</span></span> <span data-ttu-id="771a0-126">`dbo` représente le propriétaire de la base de données.</span><span class="sxs-lookup"><span data-stu-id="771a0-126">`dbo` stands for database owner.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products  
       (ProductID int PRIMARY KEY NOT NULL,  
        ProductName varchar(25) NOT NULL,  
        Price money NULL,  
        ProductDescription text NULL)  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="771a0-127">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="771a0-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="771a0-128">Insertion et mise à jour des données dans une table &#40;Didacticiel&#41;</span><span class="sxs-lookup"><span data-stu-id="771a0-128">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](../t-sql/lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="771a0-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="771a0-129">See Also</span></span>  
 [<span data-ttu-id="771a0-130">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="771a0-130">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
