---
title: MSSQLSERVER_4186 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4186 (Database Engine error)
ms.assetid: 1ae88554-f291-45bc-a186-6f41d9cd0fca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 525c1c3bd6e631044b8bc7f17b2c2a01aeb1ef8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600972"
---
# <a name="mssqlserver_4186"></a><span data-ttu-id="bcc4b-102">MSSQLSERVER_4186</span><span class="sxs-lookup"><span data-stu-id="bcc4b-102">MSSQLSERVER_4186</span></span>
    
## <a name="details"></a><span data-ttu-id="bcc4b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="bcc4b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bcc4b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="bcc4b-104">Product Name</span></span>|<span data-ttu-id="bcc4b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bcc4b-105">SQL Server</span></span>|  
|<span data-ttu-id="bcc4b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="bcc4b-106">Event ID</span></span>|<span data-ttu-id="bcc4b-107">4186</span><span class="sxs-lookup"><span data-stu-id="bcc4b-107">4186</span></span>|  
|<span data-ttu-id="bcc4b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="bcc4b-108">Event Source</span></span>|<span data-ttu-id="bcc4b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bcc4b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bcc4b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="bcc4b-110">Component</span></span>|<span data-ttu-id="bcc4b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bcc4b-111">SQLEngine</span></span>|  
|<span data-ttu-id="bcc4b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="bcc4b-112">Symbolic Name</span></span>||  
|<span data-ttu-id="bcc4b-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="bcc4b-113">Message Text</span></span>|<span data-ttu-id="bcc4b-114">La colonne '%ls.%.\*ls' ne peut pas être référencée dans la clause OUTPUT parce que la définition de colonne contient une sous-requête ou référence une fonction qui offre un accès aux données utilisateur ou système.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-114">Column '%ls.%.\*ls' cannot be referenced in the OUTPUT clause because the column definition contains a subquery or references a function that performs user or system data access.</span></span> <span data-ttu-id="bcc4b-115">Une fonction est censée par défaut offrir un accès aux données si elle n'est pas liée au schéma.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-115">A function is assumed by default to perform data access if it is not schemabound.</span></span> <span data-ttu-id="bcc4b-116">Pensez à supprimer la sous-requête ou la fonction de la définition de colonne ou à supprimer la colonne de la clause OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-116">Consider removing the subquery or function from the column definition or removing the column from the OUTPUT clause.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bcc4b-117">Explication</span><span class="sxs-lookup"><span data-stu-id="bcc4b-117">Explanation</span></span>  
 <span data-ttu-id="bcc4b-118">Pour empêcher tout comportement non déterministe, la clause OUTPUT ne peut pas référencer une colonne d'une vue ou fonction table lorsque cette colonne est définie par l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="bcc4b-118">To prevent nondeterministic behavior, the OUTPUT clause cannot reference a column from a view or inline table-valued function when that column is defined by one of the following methods:</span></span>  
  
-   <span data-ttu-id="bcc4b-119">Une sous-requête.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-119">A subquery.</span></span>  
  
-   <span data-ttu-id="bcc4b-120">Une fonction définie par l'utilisateur qui offre un accès à des données utilisateur ou système, ou qui est supposée permettre d'y accéder.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-120">A user-defined function that performs user or system data access, or is assumed to perform such access.</span></span>  
  
-   <span data-ttu-id="bcc4b-121">Une colonne calculée qui contient une fonction définie par l’utilisateur qui effectue un accès aux données utilisateur ou système dans sa définition.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-121">A computed column that contains a user-defined function that performs user or system data access in its definition.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="bcc4b-122">Exemples</span><span class="sxs-lookup"><span data-stu-id="bcc4b-122">Examples</span></span>  
 <span data-ttu-id="bcc4b-123">**Colonne de vue définie par une sous-requête**</span><span class="sxs-lookup"><span data-stu-id="bcc4b-123">**View Column Defined by a Subquery**</span></span>  
  
 <span data-ttu-id="bcc4b-124">L'exemple suivant crée une vue qui utilise une sous-requête dans la liste de sélection pour définir la colonne `State`.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-124">The following example creates a view that uses a subquery in the select list to define the column `State`.</span></span> <span data-ttu-id="bcc4b-125">Une instruction UPDATE référence ensuite la colonne `State` dans la clause OUTPUT et échoue en raison de la sous-requête dans la liste de sélection.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-125">An UPDATE statement then references the `State` column in the OUTPUT clause and fails because ob the subquery in the select list.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW dbo.V1  
AS  
    SELECT City,  
-- subquery to return the State name  
           (SELECT Name FROM Person.StateProvince AS sp   
            WHERE sp.StateProvinceID = a.StateProvinceID) AS State  
    FROM Person.Address AS a;  
GO  
--Reference the State column in the OUTPUT clause of an UPDATE statement  
UPDATE dbo.V1   
SET City = City + 'Test'   
OUTPUT deleted.City, deleted.State, inserted.City, inserted.State  
WHERE State = 'Texas';  
GO  
```  
  
 <span data-ttu-id="bcc4b-126">**Colonne de vue définie par une fonction**</span><span class="sxs-lookup"><span data-stu-id="bcc4b-126">**View Column Defined by a Function**</span></span>  
  
 <span data-ttu-id="bcc4b-127">L’exemple suivant crée une vue qui utilise la fonction scalaire d’accès aux données `dbo.ufnGetStock` dans la liste de sélection pour définir la colonne `CurrentInventory`.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-127">The following example creates a view that uses the data accessing, scalar function `dbo.ufnGetStock` in the select list to define the column `CurrentInventory`.</span></span> <span data-ttu-id="bcc4b-128">Une instruction UPDATE référence ensuite la colonne `CurrentInventory` dans la clause OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-128">An UPDATE statement then references the `CurrentInventory` column in the OUTPUT clause .</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW Production.ReorderLevels  
AS  
    SELECT ProductID, ProductModelID, ReorderPoint,  
           dbo.ufnGetStock(ProductID) AS CurrentInventory  
    FROM Production.Product;  
GO  
  
UPDATE Production.ReorderLevels  
SET ReorderPoint += CurrentInventory  
OUTPUT deleted.ReorderPoint, deleted.CurrentInventory,  
       inserted.ReorderPoint, inserted.CurrentInventory  
WHERE ProductModelID BETWEEN 75 and 80;  
```  
  
## <a name="user-action"></a><span data-ttu-id="bcc4b-129">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="bcc4b-129">User Action</span></span>  
 <span data-ttu-id="bcc4b-130">L'erreur 4186 peut être corrigée de l'une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="bcc4b-130">Error 4186 can be corrected in one of the following ways:</span></span>  
  
-   <span data-ttu-id="bcc4b-131">Utilisez des jointures au lieu de sous-requêtes pour définir la colonne dans la vue ou fonction.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-131">Use joins instead of subqueries to define the column in the view or function.</span></span> <span data-ttu-id="bcc4b-132">Par exemple, vous pouvez réécrire la vue `dbo.V1` de la façon suivante.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-132">For example, you can rewrite the view `dbo.V1` as follows.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE VIEW dbo.V1  
    AS  
        SELECT City, sp.Name AS State  
        FROM Person.Address AS a   
        JOIN Person.StateProvince AS sp   
        ON sp.StateProvinceID = a.StateProvinceID;  
    ```  
  
-   <span data-ttu-id="bcc4b-133">Examinez la définition de la fonction définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-133">Examine the definition of the user-defined function.</span></span> <span data-ttu-id="bcc4b-134">Si la fonction n'effectue pas accès aux données utilisateur ou système, modifiez la fonction de façon à y inclure la clause WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-134">If the function does not perform user or system data access, alter the function to include the WITH SCHEMABINDING clause.</span></span>  
  
-   <span data-ttu-id="bcc4b-135">Supprimez la colonne de la clause OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="bcc4b-135">Remove the column from the OUTPUT clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc4b-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bcc4b-136">See Also</span></span>  
 [<span data-ttu-id="bcc4b-137">OUTPUT, clause &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bcc4b-137">OUTPUT Clause &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/output-clause-transact-sql)  
  
  
