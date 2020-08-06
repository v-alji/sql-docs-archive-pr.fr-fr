---
title: Spécifier les paramètres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- parameters [SQL Server], stored procedures
- stored procedures [SQL Server], parameters
- output parameters [SQL Server]
- input parameters [SQL Server]
ms.assetid: 902314fe-5f9c-4d0d-a0b7-27e67c9c70ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: d93a04281839c4db26cbab16ac166af3cdb7c9a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615106"
---
# <a name="specify-parameters"></a><span data-ttu-id="60402-102">Spécifier les paramètres</span><span class="sxs-lookup"><span data-stu-id="60402-102">Specify Parameters</span></span>
  <span data-ttu-id="60402-103">En spécifiant les paramètres de la procédure, les programmes appelants peuvent passer des valeurs dans le corps de la procédure.</span><span class="sxs-lookup"><span data-stu-id="60402-103">By specifying procedure parameters, calling programs are able to pass values into the body of the procedure.</span></span> <span data-ttu-id="60402-104">Ces valeurs peuvent être utilisées à plusieurs fins pendant l'exécution de la procédure.</span><span class="sxs-lookup"><span data-stu-id="60402-104">Those values can be used for a variety of purposes during procedure execution.</span></span> <span data-ttu-id="60402-105">Les paramètres de la procédure peuvent également retourner des valeurs au programme appelant si le paramètre est marqué comme paramètre OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="60402-105">Procedure parameters can also return values to the calling program if the parameter is marked as an OUTPUT parameter.</span></span>  
  
 <span data-ttu-id="60402-106">Une procédure peut contenir jusqu'à 2100 paramètres ; chacun ayant un nom, un type de données et une direction.</span><span class="sxs-lookup"><span data-stu-id="60402-106">A procedure can have a maximum of 2100 parameters; each assigned a name, data type, and direction.</span></span> <span data-ttu-id="60402-107">Éventuellement, les paramètres peuvent avoir des valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="60402-107">Optionally, parameters can be assigned default values.</span></span>  
  
 <span data-ttu-id="60402-108">La section suivante fournit des informations sur la transmission des valeurs dans les paramètres et sur la façon dont chacun des attributs de paramètre est utilisé lors d'un appel de procédure.</span><span class="sxs-lookup"><span data-stu-id="60402-108">The following section provides information about passing values into parameters and about how each of the parameter attributes is used during a procedure call.</span></span>  
  
## <a name="passing-values-into-parameters"></a><span data-ttu-id="60402-109">Transmission de valeurs dans les paramètres</span><span class="sxs-lookup"><span data-stu-id="60402-109">Passing Values into Parameters</span></span>  
 <span data-ttu-id="60402-110">Les valeurs des paramètres fournies avec un appel de procédure doivent être des constantes ou une variable ; un nom de fonction ne peut pas être utilisé comme valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="60402-110">The parameter values supplied with a procedure call must be constants or a variable; a function name cannot be used as a parameter value.</span></span> <span data-ttu-id="60402-111">Les variables peuvent être des variables système ou des variables définies par l'utilisateur, comme \@\@spid.</span><span class="sxs-lookup"><span data-stu-id="60402-111">Variables can be user-defined or system variables such as \@\@spid.</span></span>  
  
 <span data-ttu-id="60402-112">Les exemples suivants illustrent la transmission de valeurs de paramètres à la procédure `uspGetWhereUsedProductID`.</span><span class="sxs-lookup"><span data-stu-id="60402-112">The following examples demonstrate passing parameter values to the procedure `uspGetWhereUsedProductID`.</span></span> <span data-ttu-id="60402-113">Ils indiquent comment transmettre des paramètres sous forme de constantes et de variables. Ils décrivent également comment utiliser une variable pour transmettre la valeur d'une fonction.</span><span class="sxs-lookup"><span data-stu-id="60402-113">They illustrate how to pass parameters as constants and variables and also how to use a variable to pass the value of a function.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Passing values as constants.  
EXEC dbo.uspGetWhereUsedProductID 819, '20050225';  
GO  
-- Passing values as variables.  
DECLARE @ProductID int, @CheckDate datetime;  
SET @ProductID = 819;  
SET @CheckDate = '20050225';  
EXEC dbo.uspGetWhereUsedProductID @ProductID, @CheckDate;  
GO  
-- Try to use a function as a parameter value.  
-- This produces an error message.  
EXEC dbo.uspGetWhereUsedProductID 819, GETDATE();  
GO  
-- Passing the function value as a variable.  
DECLARE @CheckDate datetime;  
SET @CheckDate = GETDATE();  
EXEC dbo.uspGetWhereUsedProductID 819, @CheckDate;  
GO  
```  
  
## <a name="specifying-parameter-names"></a><span data-ttu-id="60402-114">Spécification des noms de paramètres</span><span class="sxs-lookup"><span data-stu-id="60402-114">Specifying Parameter Names</span></span>  
 <span data-ttu-id="60402-115">Dans le cadre de la création d'une procédure et de la déclaration d'un nom de paramètre, le nom de ce dernier doit commencer par un seul caractère \@ et être unique dans la portée de la procédure.</span><span class="sxs-lookup"><span data-stu-id="60402-115">When creating a procedure and declaring a parameter name, the parameter name must begin with a single \@ character and must be unique in the scope of the procedure.</span></span>  
  
 <span data-ttu-id="60402-116">En nommant explicitement les paramètres et en attribuant les valeurs appropriées à chaque paramètre dans un appel de procédure, il est possible de fournir les paramètres dans n'importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="60402-116">Explicitly naming the parameters and assigning the appropriate values to each parameter in a procedure call allows the parameters to be supplied in any order.</span></span> <span data-ttu-id="60402-117">Par exemple, si la procédure **my_proc** attend trois paramètres nommés **\@first**, **\@second** et **\@third**, les valeurs qui lui sont transmises peuvent être assignées aux noms de paramètres, par exemple : `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span><span class="sxs-lookup"><span data-stu-id="60402-117">For example, if the procedure **my_proc** expects three parameters named **\@first**, **\@second**, and **\@third**, the values passed to the procedure can be assigned to the parameter names, such as: `EXECUTE my_proc @second = 2, @first = 1, @third = 3;`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60402-118">Si une valeur de paramètre est fournie sous la forme **\@paramètre =** _valeur_, tous les paramètres suivants doivent être indiqués de cette manière.</span><span class="sxs-lookup"><span data-stu-id="60402-118">If one parameter value is supplied in the form **\@parameter =**_value_, all subsequent parameters must be supplied in this manner.</span></span> <span data-ttu-id="60402-119">Si les valeurs des paramètres ne sont pas transmises sous la forme **\@paramètre =** _valeur_, elles doivent être indiquées dans le même ordre (de gauche à droite) que les paramètres répertoriés dans l’instruction CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="60402-119">If the parameter values are not passed in the form **\@parameter =**_value_, the values must be supplied in the identical order (left to right) as the parameters are listed in the CREATE PROCEDURE statement.</span></span>  
> 
> [!WARNING]
>  <span data-ttu-id="60402-120">Un paramètre transmis sous la forme **\@paramètre =** _valeur_, mais mal orthographié, générera une erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et empêchera l’exécution de la procédure.</span><span class="sxs-lookup"><span data-stu-id="60402-120">Any parameter passed in the form **\@parameter =**_value_ with the parameter misspelled, will cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate an error and prevent procedure execution.</span></span>  
  
## <a name="specifying-parameter-data-types"></a><span data-ttu-id="60402-121">Spécification des types de données de paramètre</span><span class="sxs-lookup"><span data-stu-id="60402-121">Specifying Parameter Data Types</span></span>  
 <span data-ttu-id="60402-122">Les paramètres doivent être définis avec un type de données lorsqu'ils sont déclarés dans une instruction CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="60402-122">Parameters must be defined with a data type when they are declared in a CREATE PROCEDURE statement.</span></span> <span data-ttu-id="60402-123">Le type de données d'un paramètre détermine le type et la plage de valeurs admis pour le paramètre lorsque la procédure est appelée.</span><span class="sxs-lookup"><span data-stu-id="60402-123">The data type of a parameter determines the type and range of values that are accepted for the parameter when the procedure is called.</span></span> <span data-ttu-id="60402-124">Par exemple, si vous définissez un paramètre avec le type de données `tinyint`, seules les valeurs numériques comprises entre 0 et 255 sont acceptées lorsqu'elles sont passées à ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="60402-124">For example, if you define a parameter with a `tinyint` data type, only numeric values ranging from 0 to 255 are accepted when passed into that parameter.</span></span> <span data-ttu-id="60402-125">Une erreur est renvoyée lorsqu'une procédure est exécutée avec une valeur incompatible avec le type de données.</span><span class="sxs-lookup"><span data-stu-id="60402-125">An error is returned if a procedure is executed with a value incompatible with the data type.</span></span>  
  
## <a name="specifying-parameter-default-values"></a><span data-ttu-id="60402-126">Spécification des valeurs de paramètres par défaut</span><span class="sxs-lookup"><span data-stu-id="60402-126">Specifying Parameter Default Values</span></span>  
 <span data-ttu-id="60402-127">Un paramètre est considéré comme facultatif si une valeur par défaut est spécifiée lorsqu'il est déclaré.</span><span class="sxs-lookup"><span data-stu-id="60402-127">A parameter is considered optional if the parameter has a default value specified when it is declared.</span></span> <span data-ttu-id="60402-128">Il n'est pas nécessaire de fournir une valeur pour un paramètre optionnel dans un appel de procédure.</span><span class="sxs-lookup"><span data-stu-id="60402-128">It is not necessary to provide a value for an optional parameter in a procedure call.</span></span>  
  
 <span data-ttu-id="60402-129">La valeur par défaut d'un paramètre est utilisée lorsque :</span><span class="sxs-lookup"><span data-stu-id="60402-129">The default value of a parameter is used when:</span></span>  
  
-   <span data-ttu-id="60402-130">Aucune valeur n'est spécifiée pour le paramètre dans l'appel de procédure.</span><span class="sxs-lookup"><span data-stu-id="60402-130">No value for the parameter is specified in the procedure call.</span></span>  
  
-   <span data-ttu-id="60402-131">Le mot clé DEFAULT est spécifié comme valeur dans l'appel de procédure.</span><span class="sxs-lookup"><span data-stu-id="60402-131">The DEFAULT keyword is specified as the value in the procedure call.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="60402-132">Si la valeur par défaut est une chaîne de caractères contenant des espaces ou des signes de ponctuation ou si elle débute par un nombre (par exemple, 6xxx), elle doit figurer entre guillemets simples.</span><span class="sxs-lookup"><span data-stu-id="60402-132">If the default value is a character string that contains embedded blanks or punctuation, or if it starts with a number (for example, 6xxx), it must be enclosed in single, straight quotation marks.</span></span>  
  
 <span data-ttu-id="60402-133">Si aucune valeur ne peut être spécifiée correctement comme valeur par défaut pour le paramètre, spécifiez NULL comme valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="60402-133">If no value can be specified appropriately as a default for the parameter, specify NULL as the default.</span></span> <span data-ttu-id="60402-134">Il est judicieux que la procédure retourne un message personnalisé lorsqu'elle est exécutée sans valeur pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="60402-134">It is a good idea to have the procedure return a customized message if the procedure is executed without a value for the parameter.</span></span>  
  
 <span data-ttu-id="60402-135">L'exemple suivant crée la procédure `usp_GetSalesYTD` avec un paramètre d'entrée, `@SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="60402-135">The following example creates the `usp_GetSalesYTD` procedure with one input parameter, `@SalesPerson`.</span></span> <span data-ttu-id="60402-136">La valeur NULL est désignée comme valeur par défaut pour le paramètre et est utilisée dans les instructions de gestion des erreurs afin de retourner un message d'erreur personnalisé lorsque la procédure est exécutée sans qu'une valeur n'ait été spécifiée pour le paramètre `@SalesPerson` .</span><span class="sxs-lookup"><span data-stu-id="60402-136">NULL is assigned as the default value for the parameter and is used in error handling statements to return a custom error message for cases when the procedure is executed without a value for the `@SalesPerson` parameter.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetSalesYTD  
@SalesPerson nvarchar(50) = NULL  -- NULL default value  
AS   
    SET NOCOUNT ON;   
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
BEGIN  
   PRINT 'ERROR: You must specify the last name of the sales person.'  
   RETURN  
END  
-- Get the sales for the specified sales person and   
-- assign it to the output parameter.  
SELECT SalesYTD  
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="60402-137">L'exemple suivant exécute la procédure.</span><span class="sxs-lookup"><span data-stu-id="60402-137">The following example executes the procedure.</span></span> <span data-ttu-id="60402-138">La première instruction exécute la procédure sans spécifier de valeur d'entrée.</span><span class="sxs-lookup"><span data-stu-id="60402-138">The first statement executes the procedure without specifying an input value.</span></span> <span data-ttu-id="60402-139">Les instructions de gestion des erreurs dans la procédure retournent le message d'erreur personnalisé.</span><span class="sxs-lookup"><span data-stu-id="60402-139">This causes the error handling statements in the procedure to return the custom error message.</span></span> <span data-ttu-id="60402-140">La deuxième instruction fournit une valeur d'entrée et retourne l'ensemble de résultats attendu.</span><span class="sxs-lookup"><span data-stu-id="60402-140">The second statement supplies an input value and returns the expected result set.</span></span>  
  
```  
-- Run the procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the procedure with an input value.  
EXEC Sales.usp_GetSalesYTD N'Blythe';  
GO  
```  
  
 <span data-ttu-id="60402-141">Bien que vous puissiez omettre des paramètres ayant des valeurs par défaut, la liste des paramètres peut seulement être tronquée.</span><span class="sxs-lookup"><span data-stu-id="60402-141">Although parameters for which defaults have been supplied can be omitted, the list of parameters can only be truncated.</span></span> <span data-ttu-id="60402-142">Par exemple, si une procédure a cinq paramètres, le quatrième et le cinquième peuvent être omis.</span><span class="sxs-lookup"><span data-stu-id="60402-142">For example, if a procedure has five parameters, both the fourth and the fifth parameters can be omitted.</span></span> <span data-ttu-id="60402-143">Toutefois, le quatrième ne peut pas être ignoré tant que le cinquième est précisé, sauf si les paramètres sont transmis sous la forme **\@paramètre =** _valeur_.</span><span class="sxs-lookup"><span data-stu-id="60402-143">However the fourth parameter cannot be skipped as long as the fifth parameter is included, unless the parameters are supplied in the form **\@parameter =**_value_.</span></span>  
  
## <a name="specifying-parameter-direction"></a><span data-ttu-id="60402-144">Spécification de la direction du paramètre</span><span class="sxs-lookup"><span data-stu-id="60402-144">Specifying Parameter Direction</span></span>  
 <span data-ttu-id="60402-145">La direction d'un paramètre peut être une entrée (une valeur passée dans le corps de la procédure) ou une sortie (la procédure retourne une valeur au programme appelant).</span><span class="sxs-lookup"><span data-stu-id="60402-145">The direction of a parameter is either input, a value is passed into the body of the procedure, or output, the procedure returns a value to the calling program.</span></span> <span data-ttu-id="60402-146">La valeur par défaut est un paramètre d'entrée.</span><span class="sxs-lookup"><span data-stu-id="60402-146">The default is an input parameter.</span></span>  
  
 <span data-ttu-id="60402-147">Pour spécifier un paramètre de sortie, vous devez indiquer le mot clé OUTPUT dans la définition du paramètre contenue dans l'instruction CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="60402-147">To specify an output parameter, the OUTPUT keyword must be specified in the definition of the parameter in the CREATE PROCEDURE statement.</span></span> <span data-ttu-id="60402-148">La procédure retourne la valeur actuelle du paramètre de sortie au programme appelant lorsqu'elle se termine.</span><span class="sxs-lookup"><span data-stu-id="60402-148">The procedure returns the current value of the output parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="60402-149">Le programme appelant doit également utiliser le mot clé OUTPUT lorsqu'il exécute la procédure pour enregistrer la valeur du paramètre dans une variable, qu'il pourra ensuite utiliser.</span><span class="sxs-lookup"><span data-stu-id="60402-149">The calling program must also use the OUTPUT keyword when executing the procedure to save the parameter's value in a variable that can be used in the calling program.</span></span>  
  
 <span data-ttu-id="60402-150">L'exemple suivant crée la procédure `Production.usp`_`GetList` qui retourne la liste des produits dont le prix ne dépasse pas un montant spécifié.</span><span class="sxs-lookup"><span data-stu-id="60402-150">The following example creates the `Production.usp`_`GetList` procedure, which returns a list of products that have prices that do not exceed a specified amount.</span></span> <span data-ttu-id="60402-151">Cet exemple représente l'utilisation de plusieurs instructions SELECT et de plusieurs paramètres OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="60402-151">The example shows using multiple SELECT statements and multiple OUTPUT parameters.</span></span> <span data-ttu-id="60402-152">Les paramètres OUTPUT permettent à une procédure externe, à un traitement ou à plusieurs instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] d'accéder à un ensemble de valeurs pendant l'exécution de la procédure.</span><span class="sxs-lookup"><span data-stu-id="60402-152">OUTPUT parameters allow an external procedure, a batch, or more than one [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to access a value set during the procedure execution.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'Production.uspGetList', 'P' ) IS NOT NULL   
    DROP PROCEDURE Production.uspGetList;  
GO  
CREATE PROCEDURE Production.uspGetList @Product varchar(40)   
    , @MaxPrice money   
    , @ComparePrice money OUTPUT  
    , @ListPrice money OUT  
AS  
    SET NOCOUNT ON;  
    SELECT p.[Name] AS Product, p.ListPrice AS 'List Price'  
    FROM Production.Product AS p  
    JOIN Production.ProductSubcategory AS s   
      ON p.ProductSubcategoryID = s.ProductSubcategoryID  
    WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice;  
-- Populate the output variable @ListPprice.  
SET @ListPrice = (SELECT MAX(p.ListPrice)  
        FROM Production.Product AS p  
        JOIN  Production.ProductSubcategory AS s   
          ON p.ProductSubcategoryID = s.ProductSubcategoryID  
        WHERE s.[Name] LIKE @Product AND p.ListPrice < @MaxPrice);  
-- Populate the output variable @compareprice.  
SET @ComparePrice = @MaxPrice;  
GO  
  
```  
  
 <span data-ttu-id="60402-153">Exécutez `usp_GetList` afin de retourner la liste des produits [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] (vélos) qui coûtent moins de 700 $.</span><span class="sxs-lookup"><span data-stu-id="60402-153">Execute `usp_GetList` to return a list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] products (Bikes) that cost less than $700.</span></span> <span data-ttu-id="60402-154">Les paramètres OUTPUT **\@cost** et **\@compareprices** sont utilisés en conjonction avec un langage de contrôle de flux afin de retourner un message dans la fenêtre **Messages**.</span><span class="sxs-lookup"><span data-stu-id="60402-154">The OUTPUT parameters **\@cost** and **\@compareprices** are used with control-of-flow language to return a message in the **Messages** window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="60402-155">La variable OUTPUT doit être définie pendant la création de la procédure et pendant l'utilisation de la variable.</span><span class="sxs-lookup"><span data-stu-id="60402-155">The OUTPUT variable must be defined during the procedure creation and also during the use of the variable.</span></span> <span data-ttu-id="60402-156">Le nom du paramètre et celui de la variable ne doivent pas nécessairement correspondre.</span><span class="sxs-lookup"><span data-stu-id="60402-156">The parameter name and variable name do not have to match.</span></span> <span data-ttu-id="60402-157">En revanche, le type de données et le positionnement du paramètre doivent correspondre (sauf en cas d’utilisation de **\@listprice=** _variable_).</span><span class="sxs-lookup"><span data-stu-id="60402-157">However, the data type and parameter positioning must match (unless **\@listprice=** _variable_ is used).</span></span>  
  
```  
DECLARE @ComparePrice money, @Cost money ;  
EXECUTE Production.uspGetList '%Bikes%', 700,   
    @ComparePrice OUT,   
    @Cost OUTPUT  
IF @Cost <= @ComparePrice   
BEGIN  
    PRINT 'These products can be purchased for less than   
    $'+RTRIM(CAST(@ComparePrice AS varchar(20)))+'.'  
END  
ELSE  
    PRINT 'The prices for all products in this category exceed   
    $'+ RTRIM(CAST(@ComparePrice AS varchar(20)))+'.';  
  
```  
  
 <span data-ttu-id="60402-158">Voici le jeu de résultats partiel :</span><span class="sxs-lookup"><span data-stu-id="60402-158">Here is the partial result set:</span></span>  
  
```  
Product                                            List Price  
-------------------------------------------------- ------------------  
Road-750 Black, 58                                 539.99  
Mountain-500 Silver, 40                            564.99  
Mountain-500 Silver, 42                            564.99  
...  
Road-750 Black, 48                                 539.99  
Road-750 Black, 52                                 539.99  
  
(14 row(s) affected)  
  
These items can be purchased for less than $700.00.  
```  
  
## <a name="see-also"></a><span data-ttu-id="60402-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60402-159">See Also</span></span>  
 [<span data-ttu-id="60402-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="60402-160">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
