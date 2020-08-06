---
title: Création des vues et des procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating views and stored procedures
ms.assetid: 53a0426d-07d8-4b7c-aa21-22632753bad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 76f6ecec446536191e8be4b05547ba5fd44c9d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695091"
---
# <a name="creating-views-and-stored-procedures"></a><span data-ttu-id="f0a86-102">Création des vues et des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="f0a86-102">Creating Views and Stored Procedures</span></span>
  <span data-ttu-id="f0a86-103"> Dans la mesure où Mary peut accéder à la base de données **TestData**, vous pouvez créer des objets de base de données, tels qu’une vue et une procédure stockée, puis autoriser Mary à y accéder.</span><span class="sxs-lookup"><span data-stu-id="f0a86-103">Now that Mary can access the **TestData** database, you may want to create some database objects, such as a view and a stored procedure, and then grant Mary access to them.</span></span> <span data-ttu-id="f0a86-104">Une vue est une instruction SELECT stockée, et une procédure stockée correspond à une ou plusieurs instructions [!INCLUDE[tsql](../includes/tsql-md.md)] qui s'exécutent comme un traitement.</span><span class="sxs-lookup"><span data-stu-id="f0a86-104">A view is a stored SELECT statement, and a stored procedure is one or more [!INCLUDE[tsql](../includes/tsql-md.md)] statements that execute as a batch.</span></span>  
  
 <span data-ttu-id="f0a86-105">Les vues peuvent être interrogées comme des tables et n'acceptent pas de paramètres.</span><span class="sxs-lookup"><span data-stu-id="f0a86-105">Views are queried like tables and do not accept parameters.</span></span> <span data-ttu-id="f0a86-106">Les procédures stockées sont plus complexes que les vues.</span><span class="sxs-lookup"><span data-stu-id="f0a86-106">Stored procedures are more complex than views.</span></span> <span data-ttu-id="f0a86-107">Elles peuvent contenir des paramètres d'entrée et de sortie et peuvent contenir des instructions pour contrôler le flux du code, comme les instructions IF et WHILE.</span><span class="sxs-lookup"><span data-stu-id="f0a86-107">Stored procedures can have both input and output parameters and can contain statements to control the flow of the code, such as IF and WHILE statements.</span></span> <span data-ttu-id="f0a86-108">Il est recommandé de faire appel aux procédures stockées pour coder toutes les actions répétitives dans la base de données</span><span class="sxs-lookup"><span data-stu-id="f0a86-108">It is good programming practice to use stored procedures for all repetitive actions in the database.</span></span>  
  
 <span data-ttu-id="f0a86-109">Pour cet exemple, vous allez utiliser CREATE VIEW pour créer une vue qui sélectionne seulement deux des colonnes dans la table **Products** .</span><span class="sxs-lookup"><span data-stu-id="f0a86-109">For this example, you will use CREATE VIEW to create a view that selects only two of the columns in the **Products** table.</span></span> <span data-ttu-id="f0a86-110">Puis, vous allez utiliser l'instruction CREATE PROCEDURE pour créer une procédure stockée qui accepte un paramètre de prix et retourne uniquement les produits dont le prix est inférieur à la valeur de paramètre spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f0a86-110">Then, you will use CREATE PROCEDURE to create a stored procedure that accepts a price parameter and returns only those products that cost less than the specified parameter value.</span></span>  
  
### <a name="to-create-a-view"></a><span data-ttu-id="f0a86-111">Pour créer une vue</span><span class="sxs-lookup"><span data-stu-id="f0a86-111">To create a view</span></span>  
  
1.  <span data-ttu-id="f0a86-112">Exécutez l'instruction suivante pour créer une vue très simple qui exécute une instruction SELECT et retourne les noms et les prix de nos produits à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f0a86-112">Execute the following statement to create a very simple view that executes a select statement, and returns the names and prices of our products to the user.</span></span>  
  
    ```  
    CREATE VIEW vw_Names  
       AS  
       SELECT ProductName, Price FROM Products;  
    GO  
  
    ```  
  
### <a name="test-the-view"></a><span data-ttu-id="f0a86-113">Tester la vue</span><span class="sxs-lookup"><span data-stu-id="f0a86-113">Test the view</span></span>  
  
1.  <span data-ttu-id="f0a86-114">Les vues sont traitées comme des tables.</span><span class="sxs-lookup"><span data-stu-id="f0a86-114">Views are treated just like tables.</span></span> <span data-ttu-id="f0a86-115">Utilisez une instruction `SELECT` pour accéder à une vue.</span><span class="sxs-lookup"><span data-stu-id="f0a86-115">Use a `SELECT` statement to access a view.</span></span>  
  
    ```  
    SELECT * FROM vw_Names;  
    GO  
  
    ```  
  
### <a name="to-create-a-stored-procedure"></a><span data-ttu-id="f0a86-116">Pour créer une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="f0a86-116">To create a stored procedure</span></span>  
  
1.  <span data-ttu-id="f0a86-117">L'instruction suivante crée un nom de procédure stockée `pr_Names`, accepte un paramètre d'entrée nommé `@VarPrice` du type de données `money`.</span><span class="sxs-lookup"><span data-stu-id="f0a86-117">The following statement creates a stored procedure name `pr_Names`, accepts an input parameter named `@VarPrice` of data type `money`.</span></span> <span data-ttu-id="f0a86-118">La procédure stockée affiche l'instruction `Products less than` concaténée avec le paramètre d'entrée dont le type de données `money` est remplacé par un type de données character `varchar(10)`.</span><span class="sxs-lookup"><span data-stu-id="f0a86-118">The stored procedure prints the statement `Products less than` concatenated with the input parameter that is changed from the `money` data type into a `varchar(10)` character data type.</span></span> <span data-ttu-id="f0a86-119">Puis, la procédure exécute une instruction `SELECT` sur la vue et passe le paramètre d'entrée dans le cadre de la clause `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="f0a86-119">Then, the procedure executes a `SELECT` statement on the view, passing the input parameter as part of the `WHERE` clause.</span></span> <span data-ttu-id="f0a86-120">Cette opération retourne tous les produits dont le prix est inférieur à la valeur du paramètre d'entrée.</span><span class="sxs-lookup"><span data-stu-id="f0a86-120">This returns all products that cost less than the input parameter value.</span></span>  
  
    ```  
    CREATE PROCEDURE pr_Names @VarPrice money  
       AS  
       BEGIN  
          -- The print statement returns text to the user  
          PRINT 'Products less than ' + CAST(@VarPrice AS varchar(10));  
          -- A second statement starts here  
          SELECT ProductName, Price FROM vw_Names  
                WHERE Price < @varPrice;  
       END  
    GO  
  
    ```  
  
### <a name="test-the-stored-procedure"></a><span data-ttu-id="f0a86-121">Tester la procédure stockée</span><span class="sxs-lookup"><span data-stu-id="f0a86-121">Test the stored procedure</span></span>  
  
1.  <span data-ttu-id="f0a86-122">Pour tester la procédure stockée, tapez et exécutez l'instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="f0a86-122">To test the stored procedure, type and execute the following statement.</span></span> <span data-ttu-id="f0a86-123">La procédure doit retourner les noms des deux produits entrés dans la table `Products` à la leçon 1 avec un prix inférieur à `10.00`.</span><span class="sxs-lookup"><span data-stu-id="f0a86-123">The procedure should return the names of the two products entered into the `Products` table in Lesson 1 with a price that is less than `10.00`.</span></span>  
  
    ```  
    EXECUTE pr_Names 10.00;  
    GO  
  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f0a86-124">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="f0a86-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f0a86-125">Octroi de l'accès à un objet de base de données</span><span class="sxs-lookup"><span data-stu-id="f0a86-125">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
## <a name="see-also"></a><span data-ttu-id="f0a86-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0a86-126">See Also</span></span>  
 <span data-ttu-id="f0a86-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0a86-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 [<span data-ttu-id="f0a86-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0a86-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
