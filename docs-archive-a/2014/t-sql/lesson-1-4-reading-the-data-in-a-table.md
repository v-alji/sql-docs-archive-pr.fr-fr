---
title: Lecture des données dans une table (tutoriel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- reading data in a table
ms.assetid: 532232c9-3d41-45cd-9150-de67a1cbfcf5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4bdaaeeddf8f35792c536624abfe6ff11b2dbd2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611433"
---
# <a name="reading-the-data-in-a-table-tutorial"></a><span data-ttu-id="39b76-102">Lecture des données dans une table (Didacticiel)</span><span class="sxs-lookup"><span data-stu-id="39b76-102">Reading the Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="39b76-103">Utilisez l'instruction SELECT pour lire les données dans une table.</span><span class="sxs-lookup"><span data-stu-id="39b76-103">Use the SELECT statement to read the data in a table.</span></span> <span data-ttu-id="39b76-104">L'instruction SELECT est une des instructions [!INCLUDE[tsql](../includes/tsql-md.md)] les plus importantes et dont la syntaxe comporte beaucoup de variations.</span><span class="sxs-lookup"><span data-stu-id="39b76-104">The SELECT statement is one of the most important [!INCLUDE[tsql](../includes/tsql-md.md)] statements, and there are many variations in the syntax.</span></span> <span data-ttu-id="39b76-105">Pour ce didacticiel, vous allez travailler avec cinq versions simples.</span><span class="sxs-lookup"><span data-stu-id="39b76-105">For this tutorial, you will work with five simple versions.</span></span>  
  
### <a name="to-read-the-data-in-a-table"></a><span data-ttu-id="39b76-106">Pour lire les données dans une table</span><span class="sxs-lookup"><span data-stu-id="39b76-106">To read the data in a table</span></span>  
  
1.  <span data-ttu-id="39b76-107">Tapez et exécutez les instructions suivantes pour lire les données dans la table `Products` .</span><span class="sxs-lookup"><span data-stu-id="39b76-107">Type and execute the following statements to read the data in the `Products` table.</span></span>  
  
    ```  
    -- The basic syntax for reading data from a single table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
    GO  
  
    ```  
  
2.  <span data-ttu-id="39b76-108">Vous pouvez utiliser un astérisque pour sélectionner toutes les colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="39b76-108">You can use an asterisk to select all the columns in the table.</span></span> <span data-ttu-id="39b76-109">Cette opération s'utilise souvent dans les requêtes ad hoc.</span><span class="sxs-lookup"><span data-stu-id="39b76-109">This is often used in ad hoc queries.</span></span> <span data-ttu-id="39b76-110">Vous devez fournir la liste de la colonne dans votre code permanent pour que l'instruction retourne les colonnes prédites, même si une nouvelle colonne est ajoutée à la table ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="39b76-110">You should provide the column list in you permanent code so that the statement will return the predicted columns, even if a new column is added to the table later.</span></span>  
  
    ```  
    -- Returns all columns in the table  
    -- Does not use the optional schema, dbo  
    SELECT * FROM Products  
    GO  
  
    ```  
  
3.  <span data-ttu-id="39b76-111">Vous pouvez omettre les colonnes que vous ne souhaitez pas retourner.</span><span class="sxs-lookup"><span data-stu-id="39b76-111">You can omit columns that you do not want to return.</span></span> <span data-ttu-id="39b76-112">Les colonnes seront retournées dans leur ordre d'apparition.</span><span class="sxs-lookup"><span data-stu-id="39b76-112">The columns will be returned in the order that they are listed.</span></span>  
  
    ```  
    -- Returns only two of the columns from the table  
    SELECT ProductName, Price  
        FROM dbo.Products  
    GO  
  
    ```  
  
4.  <span data-ttu-id="39b76-113">Utilisez une clause `WHERE` pour limiter les lignes retournées à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="39b76-113">Use a `WHERE` clause to limit the rows that are returned to the user.</span></span>  
  
    ```  
    -- Returns only two of the records in the table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
        WHERE ProductID < 60  
    GO  
  
    ```  
  
5.  <span data-ttu-id="39b76-114">Vous pouvez travailler avec les valeurs des colonnes à mesure qu'elles sont retournées.</span><span class="sxs-lookup"><span data-stu-id="39b76-114">You can work with the values in the columns as they are returned.</span></span> <span data-ttu-id="39b76-115">L'exemple suivant effectue une opération mathématique sur la colonne `Price` .</span><span class="sxs-lookup"><span data-stu-id="39b76-115">The following example performs a mathematical operation on the `Price` column.</span></span> <span data-ttu-id="39b76-116">Les colonnes ayant été modifiées de cette manière n'ont pas de nom sauf si vous en fournissez un à l'aide du mot clé `AS` .</span><span class="sxs-lookup"><span data-stu-id="39b76-116">Columns that have been changed in this way will not have a name unless you provide one by using the `AS` keyword.</span></span>  
  
    ```  
    -- Returns ProductName and the Price including a 7% tax  
    -- Provides the name CustomerPays for the calculated column  
    SELECT ProductName, Price * 1.07 AS CustomerPays  
        FROM dbo.Products  
    GO  
    ```  
  
## <a name="functions-that-are-useful-in-a-select-statement"></a><span data-ttu-id="39b76-117">Fonctions utiles dans une instruction SELECT</span><span class="sxs-lookup"><span data-stu-id="39b76-117">Functions That Are Useful in a SELECT Statement</span></span>  
 <span data-ttu-id="39b76-118">Pour des informations sur certaines fonctions que vous pouvez utiliser pour travailler avec des données dans les instructions SELECT, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="39b76-118">For information about some functions that you can use to work with data in SELECT statements, see the following topics:</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="39b76-119">Fonctions de chaîne &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="39b76-119">String Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/string-functions-transact-sql)|[<span data-ttu-id="39b76-120">Types de données et fonctions de date et d’heure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="39b76-120">Date and Time Data Types and Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|  
|[<span data-ttu-id="39b76-121">Fonctions mathématiques &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="39b76-121">Mathematical Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)|[<span data-ttu-id="39b76-122">Fonctions texte et image &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="39b76-122">Text and Image Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/text-and-image-functions-textptr-transact-sql)|  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="39b76-123">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="39b76-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="39b76-124">Résumé : Création des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="39b76-124">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="39b76-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39b76-125">See Also</span></span>  
 [<span data-ttu-id="39b76-126">SELECT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="39b76-126">SELECT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/select-transact-sql)  
  
  
