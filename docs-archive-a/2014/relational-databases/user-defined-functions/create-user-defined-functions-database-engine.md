---
title: Créer des fonctions définies par l’utilisateur (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- SCHEMABINDING clause
- schema-bound functions [SQL Server]
- user-defined functions [SQL Server], creating
- CREATE FUNCTION statement
- valid statements [SQL Server]
ms.assetid: f0d5dd10-73fd-4e05-9177-07f56552bdf7
author: rothja
ms.author: jroth
ms.openlocfilehash: 790fa1b969f933890e050311173fcde3f12c37ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613864"
---
# <a name="create-user-defined-functions-database-engine"></a><span data-ttu-id="202de-102">Créer des fonctions définies par l'utilisateur (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="202de-102">Create User-defined Functions (Database Engine)</span></span>
  <span data-ttu-id="202de-103">Cette rubrique décrit comment créer une fonction définie par l'utilisateur dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="202de-103">This topic describes how to create a user-defined function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="202de-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="202de-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="202de-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="202de-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="202de-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="202de-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="202de-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="202de-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="202de-108">**Pour créer une fonction définie par l'utilisateur :**</span><span class="sxs-lookup"><span data-stu-id="202de-108">**To create a user-defined function:**</span></span>  
  
     [<span data-ttu-id="202de-109">Créer une fonction scalaire</span><span class="sxs-lookup"><span data-stu-id="202de-109">Create a Scalar Function</span></span>](#Scalar)  
  
     [<span data-ttu-id="202de-110">Créer une fonction table</span><span class="sxs-lookup"><span data-stu-id="202de-110">Create a Table-valued Function</span></span>](#TVF)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="202de-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="202de-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="202de-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="202de-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="202de-113">Les fonctions définies par l'utilisateur ne permettent pas d'exécuter des actions qui modifient l'état des bases de données.</span><span class="sxs-lookup"><span data-stu-id="202de-113">User-defined functions cannot be used to perform actions that modify the database state.</span></span>  
  
-   <span data-ttu-id="202de-114">Les fonctions définies par l'utilisateur ne peuvent pas contenir de clause OUTPUT INTO avec une table comme cible.</span><span class="sxs-lookup"><span data-stu-id="202de-114">User-defined functions cannot contain an OUTPUT INTO clause that has a table as its target.</span></span>  
  
-   <span data-ttu-id="202de-115">Les fonctions définies par l'utilisateur ne peuvent pas renvoyer plusieurs jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="202de-115">User-defined functions can not return multiple result sets.</span></span> <span data-ttu-id="202de-116">Utilisez une procédure stockée si vous devez renvoyer plusieurs jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="202de-116">Use a stored procedure if you need to return multiple result sets.</span></span>  
  
-   <span data-ttu-id="202de-117">La gestion des erreurs est restreinte dans une fonction définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="202de-117">Error handling is restricted in a user-defined function.</span></span> <span data-ttu-id="202de-118">Une fonction UDF ne prend pas en charge les tentatives... CATCH @ERROR ou RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="202de-118">A UDF does not support TRY...CATCH, @ERROR or RAISERROR.</span></span>  
  
-   <span data-ttu-id="202de-119">Les fonctions définies par l'utilisateur ne peuvent pas appeler une procédure stockée, mais elles peuvent appeler une procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="202de-119">User-defined functions cannot call a stored procedure, but can call an extended stored procedure.</span></span>  
  
-   <span data-ttu-id="202de-120">Les fonctions définies par l'utilisateur ne peuvent pas utiliser des tables SQL dynamiques ou temporaires.</span><span class="sxs-lookup"><span data-stu-id="202de-120">User-defined functions cannot make use of dynamic SQL or temp tables.</span></span> <span data-ttu-id="202de-121">Les variables de table sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="202de-121">Table variables are allowed.</span></span>  
  
-   <span data-ttu-id="202de-122">Les instructions SET ne sont pas autorisées dans une fonction définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="202de-122">SET statements are not allowed in a user-defined function.</span></span>  
  
-   <span data-ttu-id="202de-123">La clause FOR XML n'est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="202de-123">The FOR XML clause is not allowed</span></span>  
  
-   <span data-ttu-id="202de-124">Les fonctions définies par l'utilisateur peuvent être imbriquées ; en d'autres termes, une fonction définie par l'utilisateur peut en appeler une autre.</span><span class="sxs-lookup"><span data-stu-id="202de-124">User-defined functions can be nested; that is, one user-defined function can call another.</span></span> <span data-ttu-id="202de-125">Le niveau d'imbrication est incrémenté lorsque la fonction appelée commence à s'exécuter, et décrémenté lorsque l'exécution est terminée.</span><span class="sxs-lookup"><span data-stu-id="202de-125">The nesting level is incremented when the called function starts execution, and decremented when the called function finishes execution.</span></span> <span data-ttu-id="202de-126">Les fonctions définies par l'utilisateur peuvent être imbriquées jusqu'à 32 niveaux.</span><span class="sxs-lookup"><span data-stu-id="202de-126">User-defined functions can be nested up to 32 levels.</span></span> <span data-ttu-id="202de-127">Le dépassement des niveaux d'imbrication maximum autorisés, provoque l'échec de la totalité de la chaîne de fonctions appelantes.</span><span class="sxs-lookup"><span data-stu-id="202de-127">Exceeding the maximum levels of nesting causes the whole calling function chain to fail.</span></span> <span data-ttu-id="202de-128">Toute référence à du code managé depuis une fonction Transact-SQL définie par l'utilisateur compte pour un niveau parmi les 32 niveaux d'imbrication possibles.</span><span class="sxs-lookup"><span data-stu-id="202de-128">Any reference to managed code from a Transact-SQL user-defined function counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="202de-129">Les méthodes appelées à partir du code managé ne comptent pas par rapport à cette limite.</span><span class="sxs-lookup"><span data-stu-id="202de-129">Methods invoked from within managed code do not count against this limit.</span></span>  
  
-   <span data-ttu-id="202de-130">Les instructions Service Broker suivantes ne peuvent pas être incluses dans la définition d'une fonction Transact-SQL définie par l'utilisateur :</span><span class="sxs-lookup"><span data-stu-id="202de-130">The following Service Broker statements cannot be included in the definition of a Transact-SQL user-defined function:</span></span>  
  
    -   <span data-ttu-id="202de-131">BEGIN DIALOG CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="202de-131">BEGIN DIALOG CONVERSATION</span></span>  
  
    -   <span data-ttu-id="202de-132">END CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="202de-132">END CONVERSATION</span></span>  
  
    -   <span data-ttu-id="202de-133">GET CONVERSATION GROUP</span><span class="sxs-lookup"><span data-stu-id="202de-133">GET CONVERSATION GROUP</span></span>  
  
    -   <span data-ttu-id="202de-134">MOVE CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="202de-134">MOVE CONVERSATION</span></span>  
  
    -   <span data-ttu-id="202de-135">RECEIVE</span><span class="sxs-lookup"><span data-stu-id="202de-135">RECEIVE</span></span>  
  
    -   <span data-ttu-id="202de-136">SEND</span><span class="sxs-lookup"><span data-stu-id="202de-136">SEND</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="202de-137">Sécurité</span><span class="sxs-lookup"><span data-stu-id="202de-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="202de-138">Autorisations</span><span class="sxs-lookup"><span data-stu-id="202de-138">Permissions</span></span>  
 <span data-ttu-id="202de-139">Nécessite l'autorisation CREATE FUNCTION dans la base de données et l'autorisation ALTER sur le schéma dans lequel la fonction est en cours de création.</span><span class="sxs-lookup"><span data-stu-id="202de-139">Requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span> <span data-ttu-id="202de-140">Si la fonction spécifie un type défini par l'utilisateur, elle requiert l'autorisation EXECUTE sur le type.</span><span class="sxs-lookup"><span data-stu-id="202de-140">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="scalar-functions"></a><a name="Scalar"></a><span data-ttu-id="202de-141">Fonctions scalaires</span><span class="sxs-lookup"><span data-stu-id="202de-141">Scalar Functions</span></span>  
 <span data-ttu-id="202de-142">L'exemple suivant illustre la création d'une fonction scalaire à instructions multiples dans la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="202de-142">The following example creates a multistatement scalar function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="202de-143">À partir d'une valeur d'entrée unique ( `ProductID`), la fonction retourne une valeur de donnée unique, en l'occurrence, la quantité totale du produit spécifié en stock.</span><span class="sxs-lookup"><span data-stu-id="202de-143">The function takes one input value, a `ProductID`, and returns a single data value, the aggregated quantity of the specified product in inventory.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufnGetInventoryStock', N'FN') IS NOT NULL  
    DROP FUNCTION ufnGetInventoryStock;  
GO  
CREATE FUNCTION dbo.ufnGetInventoryStock(@ProductID int)  
RETURNS int   
AS   
-- Returns the stock level for the product.  
BEGIN  
    DECLARE @ret int;  
    SELECT @ret = SUM(p.Quantity)   
    FROM Production.ProductInventory p   
    WHERE p.ProductID = @ProductID   
        AND p.LocationID = '6';  
     IF (@ret IS NULL)   
        SET @ret = 0;  
    RETURN @ret;  
END;  
GO  
  
```  
  
 <span data-ttu-id="202de-144">Dans l'exemple suivant, la fonction `ufnGetInventoryStock` est utilisée pour déterminer la quantité en stock des produits dont la valeur `ProductModelID` est comprise entre 75 et 80.</span><span class="sxs-lookup"><span data-stu-id="202de-144">The following example uses the `ufnGetInventoryStock` function to return the current inventory quantity for products that have a `ProductModelID` between 75 and 80.</span></span>  
  
```  
SELECT ProductModelID, Name, dbo.ufnGetInventoryStock(ProductID)AS CurrentSupply  
FROM Production.Product  
WHERE ProductModelID BETWEEN 75 and 80;  
  
```  
  
##  <a name="table-valued-functions"></a><a name="TVF"></a><span data-ttu-id="202de-145">Fonctions table</span><span class="sxs-lookup"><span data-stu-id="202de-145">Table-Valued Functions</span></span>  
 <span data-ttu-id="202de-146">L'exemple suivant crée une fonction table en ligne dans la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="202de-146">The following example creates an inline table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="202de-147">À partir d'un paramètre d'entrée unique (storeID), la fonction retourne les colonnes `ProductID`, `Name`, ainsi que le total cumulé des ventes ( `YTD Total` ) pour chaque produit vendu au magasin du client.</span><span class="sxs-lookup"><span data-stu-id="202de-147">The function takes one input parameter, a customer (store) ID, and returns the columns `ProductID`, `Name`, and the aggregate of year-to-date sales as `YTD Total` for each product sold to the store.</span></span>  
  
```  
IF OBJECT_ID (N'Sales.ufn_SalesByStore', N'IF') IS NOT NULL  
    DROP FUNCTION Sales.ufn_SalesByStore;  
GO  
CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
    FROM Production.Product AS P   
    JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
    JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
    JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
    WHERE C.StoreID = @storeid  
    GROUP BY P.ProductID, P.Name  
);  
  
```  
  
 <span data-ttu-id="202de-148">L'exemple suivant appelle la fonction et spécifie l'ID client 602.</span><span class="sxs-lookup"><span data-stu-id="202de-148">The following example invokes the function and specifies customer ID 602.</span></span>  
  
```  
SELECT * FROM Sales.ufn_SalesByStore (602);  
  
```  
  
 <span data-ttu-id="202de-149">L'exemple suivant crée une fonction table dans la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="202de-149">The following example creates a table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="202de-150">À partir d'un paramètre d'entrée unique, `EmployeeID` , la fonction retourne la liste de tous les employés qui sont sous la responsabilité directe ou indirecte de l'employé spécifié.</span><span class="sxs-lookup"><span data-stu-id="202de-150">The function takes a single input parameter, an `EmployeeID` and returns a list of all the employees who report to the specified employee directly or indirectly.</span></span> <span data-ttu-id="202de-151">La fonction est ensuite appelée en spécifiant l'ID d'employé 19.</span><span class="sxs-lookup"><span data-stu-id="202de-151">The function is then invoked specifying employee ID 109.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufn_FindReports', N'TF') IS NOT NULL  
    DROP FUNCTION dbo.ufn_FindReports;  
GO  
CREATE FUNCTION dbo.ufn_FindReports (@InEmpID INTEGER)  
RETURNS @retFindReports TABLE   
(  
    EmployeeID int primary key NOT NULL,  
    FirstName nvarchar(255) NOT NULL,  
    LastName nvarchar(255) NOT NULL,  
    JobTitle nvarchar(50) NOT NULL,  
    RecursionLevel int NOT NULL  
)  
--Returns a result set that lists all the employees who report to the   
--specific employee directly or indirectly.*/  
AS  
BEGIN  
WITH EMP_cte(EmployeeID, OrganizationNode, FirstName, LastName, JobTitle, RecursionLevel) -- CTE name and columns  
    AS (  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, 0 -- Get the initial list of Employees for Manager n  
        FROM HumanResources.Employee e   
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        WHERE e.BusinessEntityID = @InEmpID  
        UNION ALL  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, RecursionLevel + 1 -- Join recursive member to anchor  
        FROM HumanResources.Employee e   
            INNER JOIN EMP_cte  
            ON e.OrganizationNode.GetAncestor(1) = EMP_cte.OrganizationNode  
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        )  
-- copy the required columns to the result of the function   
   INSERT @retFindReports  
   SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
   FROM EMP_cte   
   RETURN  
END;  
GO  
-- Example invocation  
SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
FROM dbo.ufn_FindReports(1);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="202de-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="202de-152">See Also</span></span>  
 <span data-ttu-id="202de-153">[Fonctions définies par l’utilisateur](user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="202de-153">[User-Defined Functions](user-defined-functions.md) </span></span>  
 [<span data-ttu-id="202de-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="202de-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
