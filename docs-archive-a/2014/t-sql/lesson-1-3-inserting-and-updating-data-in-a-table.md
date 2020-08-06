---
title: Insertion et mise à jour des données dans une table (tutoriel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- inserting and updating data
ms.assetid: 514dc87a-b829-43b5-8fc8-1a400a260284
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0646019f166e1c2cc126a4cc7d2ed8f27a7bd2f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611432"
---
# <a name="inserting-and-updating-data-in-a-table-tutorial"></a><span data-ttu-id="739f1-102">Insertion et mise à jour des données dans une table (Didacticiel)</span><span class="sxs-lookup"><span data-stu-id="739f1-102">Inserting and Updating Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="739f1-103"> Une fois que vous avez créé la table **Products**, vous pouvez insérer des données dans la table à l’aide de l’instruction INSERT.</span><span class="sxs-lookup"><span data-stu-id="739f1-103">Now that you have created the **Products** table, you are ready to insert data into the table by using the INSERT statement.</span></span> <span data-ttu-id="739f1-104">Une fois les données insérées, vous allez modifier le contenu d'une ligne à l'aide d'une l'instruction UPDATE.</span><span class="sxs-lookup"><span data-stu-id="739f1-104">After the data is inserted, you will change the content of a row by using an UPDATE statement.</span></span> <span data-ttu-id="739f1-105">Vous allez utiliser la clause WHERE de l'instruction UPDATE pour restreindre la mise à jour à une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="739f1-105">You will use the WHERE clause of the UPDATE statement to restrict the update to a single row.</span></span> <span data-ttu-id="739f1-106">Les quatre instructions entrent les données suivantes.</span><span class="sxs-lookup"><span data-stu-id="739f1-106">The four statements will enter the following data.</span></span>  
  
|<span data-ttu-id="739f1-107">ProductID</span><span class="sxs-lookup"><span data-stu-id="739f1-107">ProductID</span></span>|<span data-ttu-id="739f1-108">ProductName</span><span class="sxs-lookup"><span data-stu-id="739f1-108">ProductName</span></span>|<span data-ttu-id="739f1-109">Price</span><span class="sxs-lookup"><span data-stu-id="739f1-109">Price</span></span>|<span data-ttu-id="739f1-110">ProductDescription</span><span class="sxs-lookup"><span data-stu-id="739f1-110">ProductDescription</span></span>|  
|---------------|-----------------|-----------|------------------------|  
|<span data-ttu-id="739f1-111">1</span><span class="sxs-lookup"><span data-stu-id="739f1-111">1</span></span>|<span data-ttu-id="739f1-112">Clamp</span><span class="sxs-lookup"><span data-stu-id="739f1-112">Clamp</span></span>|<span data-ttu-id="739f1-113">12.48</span><span class="sxs-lookup"><span data-stu-id="739f1-113">12.48</span></span>|<span data-ttu-id="739f1-114">Workbench clamp</span><span class="sxs-lookup"><span data-stu-id="739f1-114">Workbench clamp</span></span>|  
|<span data-ttu-id="739f1-115">50</span><span class="sxs-lookup"><span data-stu-id="739f1-115">50</span></span>|<span data-ttu-id="739f1-116">Screwdriver</span><span class="sxs-lookup"><span data-stu-id="739f1-116">Screwdriver</span></span>|<span data-ttu-id="739f1-117">3.17</span><span class="sxs-lookup"><span data-stu-id="739f1-117">3.17</span></span>|<span data-ttu-id="739f1-118">Flat head</span><span class="sxs-lookup"><span data-stu-id="739f1-118">Flat head</span></span>|  
|<span data-ttu-id="739f1-119">75</span><span class="sxs-lookup"><span data-stu-id="739f1-119">75</span></span>|<span data-ttu-id="739f1-120">Tire Bar</span><span class="sxs-lookup"><span data-stu-id="739f1-120">Tire Bar</span></span>||<span data-ttu-id="739f1-121">Outil pour changer des pneus.</span><span class="sxs-lookup"><span data-stu-id="739f1-121">Tool for changing tires.</span></span>|  
|<span data-ttu-id="739f1-122">3000</span><span class="sxs-lookup"><span data-stu-id="739f1-122">3000</span></span>|<span data-ttu-id="739f1-123">3mm Bracket</span><span class="sxs-lookup"><span data-stu-id="739f1-123">3mm Bracket</span></span>|<span data-ttu-id="739f1-124">52</span><span class="sxs-lookup"><span data-stu-id="739f1-124">.52</span></span>||  
  
 <span data-ttu-id="739f1-125">La syntaxe de base est la suivante : INSERT, nom de table, liste de colonnes, VALUES, puis la liste des valeurs à insérer.</span><span class="sxs-lookup"><span data-stu-id="739f1-125">The basic syntax is: INSERT, table name, column list, VALUES, and then a list of the values to be inserted.</span></span> <span data-ttu-id="739f1-126">Les deux tirets en début de ligne indiquent que celle-ci est un commentaire et que le texte sera ignoré par le compilateur.</span><span class="sxs-lookup"><span data-stu-id="739f1-126">The two hyphens in front of a line indicate that the line is a comment and the text will be ignored by the compiler.</span></span> <span data-ttu-id="739f1-127">Dans ce cas, le commentaire décrit une variation autorisée de la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="739f1-127">In this case, the comment describes a permissible variation of the syntax.</span></span>  
  
### <a name="to-insert-data-into-a-table"></a><span data-ttu-id="739f1-128">Pour insérer des données dans une table</span><span class="sxs-lookup"><span data-stu-id="739f1-128">To insert data into a table</span></span>  
  
1.  <span data-ttu-id="739f1-129">Exécutez l'instruction suivante pour insérer une ligne dans la table `Products` créée au cours de la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="739f1-129">Execute the following statement to insert a row into the `Products` table that was created in the previous task.</span></span> <span data-ttu-id="739f1-130">Voici la syntaxe de base :</span><span class="sxs-lookup"><span data-stu-id="739f1-130">This is the basic syntax.</span></span>  
  
    ```  
    -- Standard syntax  
    INSERT dbo.Products (ProductID, ProductName, Price, ProductDescription)  
        VALUES (1, 'Clamp', 12.48, 'Workbench clamp')  
    GO  
  
    ```  
  
2.  <span data-ttu-id="739f1-131">L'instruction suivante montre comment vous pouvez modifier l'ordre dans lequel les paramètres sont fournis en alternant la position de `ProductID` et `ProductName` dans la liste des champs (entre parenthèses) et dans la liste des valeurs.</span><span class="sxs-lookup"><span data-stu-id="739f1-131">The following statement shows how you can change the order in which the parameters are provided by switching the placement of the `ProductID` and `ProductName` in both the field list (in parentheses) and in the values list.</span></span>  
  
    ```  
    -- Changing the order of the columns  
    INSERT dbo.Products (ProductName, ProductID, Price, ProductDescription)  
        VALUES ('Screwdriver', 50, 3.17, 'Flat head')  
    GO  
  
    ```  
  
3.  <span data-ttu-id="739f1-132">L'instruction suivante montre que les noms des colonnes sont facultatifs tant que les valeurs sont répertoriées dans le bon ordre.</span><span class="sxs-lookup"><span data-stu-id="739f1-132">The following statement demonstrates that the names of the columns are optional, as long as the values are listed in the correct order.</span></span> <span data-ttu-id="739f1-133">Cette syntaxe est courante mais n'est pas recommandée car elle peut rendre votre code difficile à comprendre.</span><span class="sxs-lookup"><span data-stu-id="739f1-133">This syntax is common but is not recommended because it might be harder for others to understand your code.</span></span> <span data-ttu-id="739f1-134">`NULL` est spécifié pour la colonne `Price` car le prix du produit n’est pas encore connu.</span><span class="sxs-lookup"><span data-stu-id="739f1-134">`NULL` is specified for the `Price` column because the price for this product is not yet known.</span></span>  
  
    ```  
    -- Skipping the column list, but keeping the values in order  
    INSERT dbo.Products  
        VALUES (75, 'Tire Bar', NULL, 'Tool for changing tires.')  
    GO  
  
    ```  
  
4.  <span data-ttu-id="739f1-135">Le nom de schéma est facultatif tant que vous accédez et modifiez une table dans votre schéma par défaut.</span><span class="sxs-lookup"><span data-stu-id="739f1-135">The schema name is optional as long as you are accessing and changing a table in your default schema.</span></span> <span data-ttu-id="739f1-136">Comme la colonne `ProductDescription` autorise les valeurs Null et qu'aucune valeur n'est fournie, le nom de colonne et la valeur `ProductDescription` peuvent être supprimés de l'instruction complètement.</span><span class="sxs-lookup"><span data-stu-id="739f1-136">Because the `ProductDescription` column allows null values and no value is being provided, the `ProductDescription` column name and value can be dropped from the statement completely.</span></span>  
  
    ```  
    -- Dropping the optional dbo and dropping the ProductDescription column  
    INSERT Products (ProductID, ProductName, Price)  
        VALUES (3000, '3mm Bracket', .52)  
    GO  
    ```  
  
### <a name="to-update-the-products-table"></a><span data-ttu-id="739f1-137">Pour mettre à jour la table Products</span><span class="sxs-lookup"><span data-stu-id="739f1-137">To update the products table</span></span>  
  
1.  <span data-ttu-id="739f1-138">Tapez et exécutez l'instruction `UPDATE` suivante pour remplacer le `ProductName` du deuxième produit à partir de `Screwdriver`par `Flat Head Screwdriver`.</span><span class="sxs-lookup"><span data-stu-id="739f1-138">Type and execute the following `UPDATE` statement to change the `ProductName` of the second product from `Screwdriver`, to `Flat Head Screwdriver`.</span></span>  
  
    ```  
    UPDATE dbo.Products  
        SET ProductName = 'Flat Head Screwdriver'  
        WHERE ProductID = 50  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="739f1-139">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="739f1-139">Next Task in Lesson</span></span>  
 [<span data-ttu-id="739f1-140">Lecture des données dans une table &#40;Didacticiel&#41;</span><span class="sxs-lookup"><span data-stu-id="739f1-140">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="739f1-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="739f1-141">See Also</span></span>  
 <span data-ttu-id="739f1-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="739f1-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 [<span data-ttu-id="739f1-143">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="739f1-143">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
