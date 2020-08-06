---
title: Retour de données à partir d’une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], returning data
- returning data from stored procedure
ms.assetid: 7a428ffe-cd87-4f42-b3f1-d26aa8312bf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 472ca5cf27f7e7ea2b18daa961c19faadcf2251f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615107"
---
# <a name="return-data-from-a-stored-procedure"></a><span data-ttu-id="7e57e-102">Retour de données à partir d'une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="7e57e-102">Return Data from a Stored Procedure</span></span>
  <span data-ttu-id="7e57e-103">Il existe deux méthodes permettant de retourner des jeux de résultats ou des données d'une procédure vers un programme appelant : les paramètres de sortie et les codes de retour.</span><span class="sxs-lookup"><span data-stu-id="7e57e-103">There are two ways of returning result sets or data from a procedure to a calling program: output parameters and return codes.</span></span> <span data-ttu-id="7e57e-104">Cette rubrique fournit des informations sur ces deux approches.</span><span class="sxs-lookup"><span data-stu-id="7e57e-104">This topic provides information on both approaches.</span></span>  
  
## <a name="returning-data-using-an-output-parameter"></a><span data-ttu-id="7e57e-105">Retour de données à l'aide d'un paramètre de sortie</span><span class="sxs-lookup"><span data-stu-id="7e57e-105">Returning Data Using an Output Parameter</span></span>  
 <span data-ttu-id="7e57e-106">Si vous spécifiez le mot clé OUTPUT pour un paramètre dans la définition de procédure, la procédure peut retourner la valeur actuelle du paramètre au programme appelant lors de la sortie de la procédure.</span><span class="sxs-lookup"><span data-stu-id="7e57e-106">If you specify the OUTPUT keyword for a parameter in the procedure definition, the procedure can return the current value of the parameter to the calling program when the procedure exits.</span></span> <span data-ttu-id="7e57e-107">Pour enregistrer la valeur du paramètre dans une variable afin que le programme appelant puisse l'utiliser, ce dernier doit inclure le mot clé OUTPUT lorsqu'il exécute la procédure.</span><span class="sxs-lookup"><span data-stu-id="7e57e-107">To save the value of the parameter in a variable that can be used in the calling program, the calling program must use the OUTPUT keyword when executing the procedure.</span></span> <span data-ttu-id="7e57e-108">Pour plus d’informations sur les types de données qui peuvent être utilisés comme paramètres de sortie, consultez [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7e57e-108">For more information about what data types can be used as output parameters, see [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span>  
  
### <a name="examples-of-output-parameter"></a><span data-ttu-id="7e57e-109">Exemples de paramètre de sortie</span><span class="sxs-lookup"><span data-stu-id="7e57e-109">Examples of Output Parameter</span></span>  
 <span data-ttu-id="7e57e-110">L'exemple ci-dessous illustre une procédure avec un paramètre d'entrée et un paramètre de sortie.</span><span class="sxs-lookup"><span data-stu-id="7e57e-110">The following example shows a procedure with an input and an output parameter.</span></span> <span data-ttu-id="7e57e-111">Le paramètre `@SalesPerson` doit recevoir une valeur d'entrée spécifiée par le programme appelant.</span><span class="sxs-lookup"><span data-stu-id="7e57e-111">The `@SalesPerson` parameter would receive an input value specified by the calling program.</span></span> <span data-ttu-id="7e57e-112">L’instruction SELECT utilise la valeur passée dans le paramètre d’entrée pour obtenir la valeur `SalesYTD` correcte.</span><span class="sxs-lookup"><span data-stu-id="7e57e-112">The SELECT statement uses the value passed into the input parameter to obtain the correct `SalesYTD` value.</span></span> <span data-ttu-id="7e57e-113">L’instruction SELECT affecte également la valeur au paramètre de sortie `@SalesYTD` , qui retourne la valeur au programme appelant quand la procédure se termine.</span><span class="sxs-lookup"><span data-stu-id="7e57e-113">The SELECT statement also assigns the value to the `@SalesYTD` output parameter, which returns the value to the calling program when the procedure exits.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.uspGetEmployeeSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.uspGetEmployeeSalesYTD;  
GO  
CREATE PROCEDURE Sales.uspGetEmployeeSalesYTD  
@SalesPerson nvarchar(50),  
@SalesYTD money OUTPUT  
AS    
  
    SET NOCOUNT ON;  
    SELECT @SalesYTD = SalesYTD  
    FROM Sales.SalesPerson AS sp  
    JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
    WHERE LastName = @SalesPerson;  
RETURN  
GO  
  
```  
  
 <span data-ttu-id="7e57e-114">L’exemple suivant appelle la procédure créée dans le premier exemple et enregistre la valeur de sortie retournée par la procédure appelée dans la variable `@SalesYTD` , qui est locale pour le programme appelant.</span><span class="sxs-lookup"><span data-stu-id="7e57e-114">The following example calls the procedure created in the first example and saves the output value returned from the called procedure in the `@SalesYTD` variable, which is local to the calling program.</span></span>  
  
```  
-- Declare the variable to receive the output value of the procedure.  
DECLARE @SalesYTDBySalesPerson money;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTDBySalesPerson  
EXECUTE Sales.uspGetEmployeeSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDBySalesPerson OUTPUT;  
-- Display the value returned by the procedure.  
PRINT 'Year-to-date sales for this employee is ' +   
    convert(varchar(10),@SalesYTDBySalesPerson);  
GO  
  
```  
  
 <span data-ttu-id="7e57e-115">Des valeurs d'entrée peuvent également être définies pour les paramètres OUTPUT lorsque la procédure est exécutée.</span><span class="sxs-lookup"><span data-stu-id="7e57e-115">Input values can also be specified for OUTPUT parameters when the procedure is executed.</span></span> <span data-ttu-id="7e57e-116">Ainsi, la procédure peut recevoir une valeur du programme appelant, la modifier ou l'utiliser pour exécuter des opérations, puis retourner la nouvelle valeur au programme appelant.</span><span class="sxs-lookup"><span data-stu-id="7e57e-116">This allows the procedure to receive a value from the calling program, change or perform operations with the value, and then return the new value to the calling program.</span></span> <span data-ttu-id="7e57e-117">Dans l’exemple précédent, la variable `@SalesYTDBySalesPerson` peut recevoir une valeur avant que le programme appelle la procédure `Sales.uspGetEmployeeSalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="7e57e-117">In the previous example, the `@SalesYTDBySalesPerson` variable can be assigned a value before the program calls the `Sales.uspGetEmployeeSalesYTD` procedure.</span></span> <span data-ttu-id="7e57e-118">L’instruction d’exécution passe alors la valeur de la variable `@SalesYTDBySalesPerson` au paramètre OUTPUT `@SalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="7e57e-118">The execute statement would pass the `@SalesYTDBySalesPerson` variable value into the `@SalesYTD` OUTPUT parameter.</span></span> <span data-ttu-id="7e57e-119">Ensuite, dans le corps de la procédure, la valeur peut être utilisée pour des calculs qui génèrent une nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="7e57e-119">Then in the procedure body, the value could be used for calculations that generate a new value.</span></span> <span data-ttu-id="7e57e-120">La nouvelle valeur est repassée hors de la procédure par le paramètre OUTPUT, mettant à jour la valeur dans la variable `@SalesYTDBySalesPerson` quand la procédure se termine.</span><span class="sxs-lookup"><span data-stu-id="7e57e-120">The new value would be passed back out of the procedure through the OUTPUT parameter, updating the value in the `@SalesYTDBySalesPerson` variable when the procedure exits.</span></span> <span data-ttu-id="7e57e-121">Ce mécanisme est souvent appelé « capacité de passage par référence ».</span><span class="sxs-lookup"><span data-stu-id="7e57e-121">This is often referred to as "pass-by-reference capability."</span></span>  
  
 <span data-ttu-id="7e57e-122">Si vous spécifiez OUTPUT pour un paramètre lorsque vous appelez une procédure alors que le paramètre n'est pas défini avec OUTPUT dans la définition de la procédure, vous obtiendrez un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="7e57e-122">If you specify OUTPUT for a parameter when you call a procedure and that parameter is not defined by using OUTPUT in the procedure definition, you get an error message.</span></span> <span data-ttu-id="7e57e-123">Il est néanmoins possible d'exécuter une procédure avec des paramètres output et de ne pas spécifier OUTPUT lors de l'exécution de la procédure.</span><span class="sxs-lookup"><span data-stu-id="7e57e-123">However, you can execute a procedure with output parameters and not specify OUTPUT when executing the procedure.</span></span> <span data-ttu-id="7e57e-124">Aucune erreur n'est retournée, mais vous ne pouvez pas utiliser la valeur de sortie dans le programme appelant.</span><span class="sxs-lookup"><span data-stu-id="7e57e-124">No error is returned, but you cannot use the output value in the calling program.</span></span>  
  
### <a name="using-the-cursor-data-type-in-output-parameters"></a><span data-ttu-id="7e57e-125">Utilisation du type de données Cursor dans des paramètres OUTPUT</span><span class="sxs-lookup"><span data-stu-id="7e57e-125">Using the Cursor Data Type in OUTPUT Parameters</span></span>  
 [!INCLUDE[tsql](../../../includes/tsql-md.md)]<span data-ttu-id="7e57e-126">les procédures ne peuvent utiliser le `cursor` type de données que pour les paramètres OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="7e57e-126">procedures can use the `cursor` data type only for OUTPUT parameters.</span></span> <span data-ttu-id="7e57e-127">Si le `cursor` type de données est spécifié pour un paramètre, les mots clés Varying et Output doivent être spécifiés pour ce paramètre dans la définition de la procédure.</span><span class="sxs-lookup"><span data-stu-id="7e57e-127">If the `cursor` data type is specified for a parameter, both the VARYING and OUTPUT keywords must be specified for that parameter in the procedure definition.</span></span> <span data-ttu-id="7e57e-128">Un paramètre peut être spécifié comme OUTPUT uniquement, mais si le mot clé VARYing est spécifié dans la déclaration du paramètre, le type de données doit être `cursor` et le mot clé OUTPUT doit également être spécifié.</span><span class="sxs-lookup"><span data-stu-id="7e57e-128">A parameter can be specified as only OUTPUT but if the VARYING keyword is specified in the parameter declaration, the data type must be `cursor` and the OUTPUT keyword must also be specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e57e-129">Le type de données `cursor` ne peut pas être lié à des variables d'application par l'intermédiaire des API de base de données, telles que OLE DB, ODBC, ADO et DB-Library.</span><span class="sxs-lookup"><span data-stu-id="7e57e-129">The `cursor` data type cannot be bound to application variables through the database APIs such as OLE DB, ODBC, ADO, and DB-Library.</span></span> <span data-ttu-id="7e57e-130">Les paramètres OUTPUT devant être liés avant qu'une application puisse exécuter une procédure, les procédures qui contiennent des paramètres OUTPUT de type `cursor` ne peuvent pas être appelées à partir des API de base de données.</span><span class="sxs-lookup"><span data-stu-id="7e57e-130">Because OUTPUT parameters must be bound before an application can execute a procedure, procedures with `cursor` OUTPUT parameters cannot be called from the database APIs.</span></span> <span data-ttu-id="7e57e-131">Ces procédures peuvent être appelées à partir de traitements, procédures ou déclencheurs [!INCLUDE[tsql](../../../includes/tsql-md.md)] seulement lorsque la variable OUTPUT de type `cursor` est affectée à une variable [!INCLUDE[tsql](../../../includes/tsql-md.md)] locale de type `cursor`.</span><span class="sxs-lookup"><span data-stu-id="7e57e-131">These procedures can be called from [!INCLUDE[tsql](../../../includes/tsql-md.md)] batches, procedures, or triggers only when the `cursor` OUTPUT variable is assigned to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] local `cursor` variable.</span></span>  
  
### <a name="rules-for-cursor-output-parameters"></a><span data-ttu-id="7e57e-132">Règles pour les paramètres de sortie de curseur</span><span class="sxs-lookup"><span data-stu-id="7e57e-132">Rules for Cursor Output Parameters</span></span>  
 <span data-ttu-id="7e57e-133">Les règles suivantes régissent les paramètres de sortie de type `cursor` lors de l'exécution de la procédure :</span><span class="sxs-lookup"><span data-stu-id="7e57e-133">The following rules pertain to `cursor` output parameters when the procedure is executed:</span></span>  
  
-   <span data-ttu-id="7e57e-134">Dans le cas d'un curseur avant uniquement, les lignes renvoyées dans le jeu de résultats du curseur sont seulement celles situées au niveau de la position du curseur ou au-delà de celui-ci, à la fin de la procédure, par exemple :</span><span class="sxs-lookup"><span data-stu-id="7e57e-134">For a forward-only cursor, the rows returned in the cursor's result set are only those rows at and beyond the position of the cursor at the conclusion of the procedure execution, for example:</span></span>  
  
    -   <span data-ttu-id="7e57e-135">Un curseur ne permettant pas le défilement est ouvert dans une procédure, dans un jeu de résultats de 100 lignes, appelé RS.</span><span class="sxs-lookup"><span data-stu-id="7e57e-135">A nonscrollable cursor is opened in a procedure on a result set named RS of 100 rows.</span></span>  
  
    -   <span data-ttu-id="7e57e-136">La procédure extrait les 5 premières lignes du jeu de résultats RS.</span><span class="sxs-lookup"><span data-stu-id="7e57e-136">The procedure fetches the first 5 rows of result set RS.</span></span>  
  
    -   <span data-ttu-id="7e57e-137">La procédure est renvoyée vers son appelant.</span><span class="sxs-lookup"><span data-stu-id="7e57e-137">The procedure returns to its caller.</span></span>  
  
    -   <span data-ttu-id="7e57e-138">Le jeu de résultats RS renvoyé à l'appelant est constitué des lignes 6 à 100 de RS et le curseur dans l'appelant est placé avant la première ligne de RS.</span><span class="sxs-lookup"><span data-stu-id="7e57e-138">The result set RS returned to the caller consists of rows from 6 through 100 of RS, and the cursor in the caller is positioned before the first row of RS.</span></span>  
  
-   <span data-ttu-id="7e57e-139">Dans le cas d'un curseur avant uniquement, si le curseur se trouve avant la première ligne lorsque la procédure existe, la totalité du jeu de résultats est renvoyée au traitement d'instructions, à la procédure ou au déclencheur appelant.</span><span class="sxs-lookup"><span data-stu-id="7e57e-139">For a forward-only cursor, if the cursor is positioned before the first row when the procedure exits, the entire result set is returned to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="7e57e-140">Lorsqu'elle est renvoyée, la position du curseur est fixée au début de la première ligne.</span><span class="sxs-lookup"><span data-stu-id="7e57e-140">When returned, the cursor position is set before the first row.</span></span>  
  
-   <span data-ttu-id="7e57e-141">Dans le cas d'un curseur avant uniquement, si le curseur est placé au-delà de la fin de la dernière ligne lorsque la procédure existe, le système renvoie un jeu de résultats vide au traitement d'instructions, à la procédure ou au déclencheur appelant.</span><span class="sxs-lookup"><span data-stu-id="7e57e-141">For a forward-only cursor, if the cursor is positioned beyond the end of the last row when the procedure exits, an empty result set is returned to the calling batch, procedure, or trigger.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e57e-142">Un jeu de résultats vide est différent d'une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="7e57e-142">An empty result set is not the same as a null value.</span></span>  
  
-   <span data-ttu-id="7e57e-143">Dans le cas d'un curseur permettant le défilement, toutes les lignes du jeu de résultats sont renvoyées au traitement d'instructions, à la procédure ou au déclencheur appelant lorsque la procédure existe.</span><span class="sxs-lookup"><span data-stu-id="7e57e-143">For a scrollable cursor, all the rows in the result set are returned to the calling batch, procedure, or trigger when the procedure exits.</span></span> <span data-ttu-id="7e57e-144">Lors du renvoi, la position du curseur est conservée à la position de la dernière extraction exécutée dans la procédure.</span><span class="sxs-lookup"><span data-stu-id="7e57e-144">When returned, the cursor position is left at the position of the last fetch executed in the procedure.</span></span>  
  
-   <span data-ttu-id="7e57e-145">Pour tous les types de curseur, si le curseur est fermé, une valeur NULL est repassée au traitement d'instructions, à la procédure ou au déclencheur appelant.</span><span class="sxs-lookup"><span data-stu-id="7e57e-145">For any type of cursor, if the cursor is closed, then a null value is passed back to the calling batch, procedure, or trigger.</span></span> <span data-ttu-id="7e57e-146">Cette situation se produit également si un curseur est affecté à un paramètre mais qu'il n'a jamais été ouvert.</span><span class="sxs-lookup"><span data-stu-id="7e57e-146">This will also be the case if a cursor is assigned to a parameter, but that cursor is never opened.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e57e-147">L'état fermé n'a d'importance qu'au moment du retour.</span><span class="sxs-lookup"><span data-stu-id="7e57e-147">The closed state matters only at return time.</span></span> <span data-ttu-id="7e57e-148">Par exemple, vous pouvez fermer un curseur au cours de l'exécution de la procédure, le rouvrir plus tard dans la procédure et renvoyer le jeu de résultats de ce curseur au traitement d'instructions, à la procédure ou au déclencheur appelant.</span><span class="sxs-lookup"><span data-stu-id="7e57e-148">For example, it is valid to close a cursor part of the way through the procedure, to open it again later in the procedure, and return that cursor's result set to the calling batch, procedure, or trigger.</span></span>  
  
### <a name="examples-of-cursor-output-parameters"></a><span data-ttu-id="7e57e-149">Exemples de paramètres de sortie de curseur</span><span class="sxs-lookup"><span data-stu-id="7e57e-149">Examples of Cursor Output Parameters</span></span>  
 <span data-ttu-id="7e57e-150">Dans l’exemple suivant, vous créez une procédure qui spécifiait un paramètre de sortie, `@currency` _ `cursor` à l’aide du `cursor` type de données.</span><span class="sxs-lookup"><span data-stu-id="7e57e-150">In the following example, a procedure is created that specified an output parameter, `@currency`_`cursor` using the `cursor` data type.</span></span> <span data-ttu-id="7e57e-151">La procédure stockée est ensuite appelée dans un traitement.</span><span class="sxs-lookup"><span data-stu-id="7e57e-151">The procedure is then called in a batch.</span></span>  
  
 <span data-ttu-id="7e57e-152">Commencez par créer la procédure qui déclare puis ouvre un curseur dans la table Currency.</span><span class="sxs-lookup"><span data-stu-id="7e57e-152">First, create the procedure that declares and then opens a cursor on the Currency table.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspCurrencyCursor', 'P' ) IS NOT NULL  
    DROP PROCEDURE dbo.uspCurrencyCursor;  
GO  
CREATE PROCEDURE dbo.uspCurrencyCursor   
    @CurrencyCursor CURSOR VARYING OUTPUT  
AS  
    SET NOCOUNT ON;  
    SET @CurrencyCursor = CURSOR  
    FORWARD_ONLY STATIC FOR  
      SELECT CurrencyCode, Name  
      FROM Sales.Currency;  
    OPEN @CurrencyCursor;  
GO  
  
```  
  
 <span data-ttu-id="7e57e-153">Ensuite, exécutez un traitement d'instructions qui déclare une variable curseur locale, exécute la procédure pour affecter le curseur à la variable locale et extrait les lignes du curseur.</span><span class="sxs-lookup"><span data-stu-id="7e57e-153">Next, execute a batch that declares a local cursor variable, executes the procedure to assign the cursor to the local variable, and then fetches the rows from the cursor.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @MyCursor CURSOR;  
EXEC dbo.uspCurrencyCursor @CurrencyCursor = @MyCursor OUTPUT;  
WHILE (@@FETCH_STATUS = 0)  
BEGIN;  
     FETCH NEXT FROM @MyCursor;  
END;  
CLOSE @MyCursor;  
DEALLOCATE @MyCursor;  
GO  
  
```  
  
## <a name="returning-data-using-a-return-code"></a><span data-ttu-id="7e57e-154">Renvoi de données au moyen d'un code de retour</span><span class="sxs-lookup"><span data-stu-id="7e57e-154">Returning Data Using a Return Code</span></span>  
 <span data-ttu-id="7e57e-155">Une procédure peut retourner une valeur entière appelée « code de retour » pour indiquer l'état d'exécution d'une procédure.</span><span class="sxs-lookup"><span data-stu-id="7e57e-155">A procedure can return an integer value called a return code to indicate the execution status of a procedure.</span></span> <span data-ttu-id="7e57e-156">Le code de retour d'une procédure se définit au moyen de l'instruction RETURN.</span><span class="sxs-lookup"><span data-stu-id="7e57e-156">You specify the return code for a procedure using the RETURN statement.</span></span> <span data-ttu-id="7e57e-157">Comme dans le cas des paramètres OUTPUT, vous devez enregistrer le code de retour dans une variable lors de l'exécution de la procédure afin de pouvoir utiliser sa valeur dans le programme appelant.</span><span class="sxs-lookup"><span data-stu-id="7e57e-157">As with OUTPUT parameters, you must save the return code in a variable when the procedure is executed in order to use the return code value in the calling program.</span></span> <span data-ttu-id="7e57e-158">Par exemple, la variable `@result` d’assignation de type de données `int` est utilisée pour stocker le code de retour de la procédure `my_proc` , par exemple :</span><span class="sxs-lookup"><span data-stu-id="7e57e-158">For example, the assignment variable `@result` of data type `int` is used to store the return code from the procedure `my_proc`, such as:</span></span>  
  
```  
DECLARE @result int;  
EXECUTE @result = my_proc;  
```  
  
 <span data-ttu-id="7e57e-159">Les codes de retour sont couramment utilisés dans les blocs de contrôle de flux des procédures pour définir la valeur du code de retour pour chaque situation d'erreur possible.</span><span class="sxs-lookup"><span data-stu-id="7e57e-159">Return codes are commonly used in control-of-flow blocks within procedures to set the return code value for each possible error situation.</span></span> <span data-ttu-id="7e57e-160">Vous pouvez utiliser la fonction @@ERROR après une instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] pour détecter si une erreur s’est produite pendant l’exécution de l’instruction.</span><span class="sxs-lookup"><span data-stu-id="7e57e-160">You can use the @@ERROR function after a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to detect whether an error occurred during the execution of the statement.</span></span>  
  
### <a name="examples-of-return-codes"></a><span data-ttu-id="7e57e-161">Exemples de codes de retour</span><span class="sxs-lookup"><span data-stu-id="7e57e-161">Examples of Return Codes</span></span>  
 <span data-ttu-id="7e57e-162">L'exemple suivant illustre la procédure `usp_GetSalesYTD` de gestion d'erreurs qui définit les valeurs du code de retour pour diverses erreurs.</span><span class="sxs-lookup"><span data-stu-id="7e57e-162">The following example shows the `usp_GetSalesYTD` procedure with error handling that sets special return code values for various errors.</span></span> <span data-ttu-id="7e57e-163">Le tableau suivant montre la valeur entière attribuée par la procédure à chaque erreur possible, et la signification correspondante pour chaque valeur.</span><span class="sxs-lookup"><span data-stu-id="7e57e-163">The following table shows the integer value that is assigned by the procedure to each possible error, and the corresponding meaning for each value.</span></span>  
  
|<span data-ttu-id="7e57e-164">Valeur du code de retour</span><span class="sxs-lookup"><span data-stu-id="7e57e-164">Return code value</span></span>|<span data-ttu-id="7e57e-165">Signification</span><span class="sxs-lookup"><span data-stu-id="7e57e-165">Meaning</span></span>|  
|-----------------------|-------------|  
|<span data-ttu-id="7e57e-166">0</span><span class="sxs-lookup"><span data-stu-id="7e57e-166">0</span></span>|<span data-ttu-id="7e57e-167">Exécution réussie.</span><span class="sxs-lookup"><span data-stu-id="7e57e-167">Successful execution.</span></span>|  
|<span data-ttu-id="7e57e-168">1</span><span class="sxs-lookup"><span data-stu-id="7e57e-168">1</span></span>|<span data-ttu-id="7e57e-169">La valeur du paramètre nécessaire n'est pas spécifiée.</span><span class="sxs-lookup"><span data-stu-id="7e57e-169">Required parameter value is not specified.</span></span>|  
|<span data-ttu-id="7e57e-170">2</span><span class="sxs-lookup"><span data-stu-id="7e57e-170">2</span></span>|<span data-ttu-id="7e57e-171">Valeur du paramètre spécifiée non valide.</span><span class="sxs-lookup"><span data-stu-id="7e57e-171">Specified parameter value is not valid.</span></span>|  
|<span data-ttu-id="7e57e-172">3</span><span class="sxs-lookup"><span data-stu-id="7e57e-172">3</span></span>|<span data-ttu-id="7e57e-173">Erreur lors de l'obtention de la valeur des ventes.</span><span class="sxs-lookup"><span data-stu-id="7e57e-173">Error has occurred getting sales value.</span></span>|  
|<span data-ttu-id="7e57e-174">4</span><span class="sxs-lookup"><span data-stu-id="7e57e-174">4</span></span>|<span data-ttu-id="7e57e-175">Valeur des ventes NULL trouvée pour le vendeur.</span><span class="sxs-lookup"><span data-stu-id="7e57e-175">NULL sales value found for the salesperson.</span></span>|  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID('Sales.usp_GetSalesYTD', 'P') IS NOT NULL  
    DROP PROCEDURE Sales.usp_GetSalesYTD;  
GO  
CREATE PROCEDURE Sales.usp_GetSalesYTD  
@SalesPerson nvarchar(50) = NULL,  -- NULL default value  
@SalesYTD money = NULL OUTPUT  
AS    
  
-- Validate the @SalesPerson parameter.  
IF @SalesPerson IS NULL  
   BEGIN  
       PRINT 'ERROR: You must specify a last name for the sales person.'  
       RETURN(1)  
   END  
ELSE  
   BEGIN  
   -- Make sure the value is valid.  
   IF (SELECT COUNT(*) FROM HumanResources.vEmployee  
          WHERE LastName = @SalesPerson) = 0  
      RETURN(2)  
   END  
-- Get the sales for the specified name and   
-- assign it to the output parameter.  
SELECT @SalesYTD = SalesYTD   
FROM Sales.SalesPerson AS sp  
JOIN HumanResources.vEmployee AS e ON e.BusinessEntityID = sp.BusinessEntityID  
WHERE LastName = @SalesPerson;  
-- Check for SQL Server errors.  
IF @@ERROR <> 0   
   BEGIN  
      RETURN(3)  
   END  
ELSE  
   BEGIN  
   -- Check to see if the ytd_sales value is NULL.  
     IF @SalesYTD IS NULL  
       RETURN(4)   
     ELSE  
      -- SUCCESS!!  
        RETURN(0)  
   END  
-- Run the stored procedure without specifying an input value.  
EXEC Sales.usp_GetSalesYTD;  
GO  
-- Run the stored procedure with an input value.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
-- Execute the procedure specifying a last name for the input parameter  
-- and saving the output value in the variable @SalesYTD  
EXECUTE Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
PRINT N'Year-to-date sales for this employee is ' +  
    CONVERT(varchar(10), @SalesYTDForSalesPerson);  
  
```  
  
 <span data-ttu-id="7e57e-176">L'exemple suivant crée un programme chargé de gérer les codes de retour retournés par la procédure `usp_GetSalesYTD` .</span><span class="sxs-lookup"><span data-stu-id="7e57e-176">The following example creates a program to handle the return codes that are returned from the `usp_GetSalesYTD` procedure.</span></span>  
  
```  
-- Declare the variables to receive the output value and return code   
-- of the procedure.  
DECLARE @SalesYTDForSalesPerson money, @ret_code int;  
  
-- Execute the procedure with a title_id value  
-- and save the output value and return code in variables.  
EXECUTE @ret_code = Sales.usp_GetSalesYTD  
    N'Blythe', @SalesYTD = @SalesYTDForSalesPerson OUTPUT;  
--  Check the return codes.  
IF @ret_code = 0  
BEGIN  
   PRINT 'Procedure executed successfully'  
   -- Display the value returned by the procedure.  
   PRINT 'Year-to-date sales for this employee is ' + CONVERT(varchar(10),@SalesYTDForSalesPerson)  
END  
ELSE IF @ret_code = 1  
   PRINT 'ERROR: You must specify a last name for the sales person.'  
ELSE IF @ret_code = 2   
   PRINT 'EERROR: You must enter a valid last name for the sales person.'  
ELSE IF @ret_code = 3  
   PRINT 'ERROR: An error occurred getting sales value.'  
ELSE IF @ret_code = 4  
   PRINT 'ERROR: No sales recorded for this employee.'     
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e57e-177">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7e57e-177">See Also</span></span>  
 <span data-ttu-id="7e57e-178">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e57e-178">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="7e57e-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e57e-179">[PRINT &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/print-transact-sql) </span></span>  
 <span data-ttu-id="7e57e-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e57e-180">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="7e57e-181">[Curseurs](../cursors.md) </span><span class="sxs-lookup"><span data-stu-id="7e57e-181">[Cursors](../cursors.md) </span></span>  
 <span data-ttu-id="7e57e-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e57e-182">[RETURN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/return-transact-sql) </span></span>  
 [<span data-ttu-id="7e57e-183">@@ERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7e57e-183">@@ERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/error-transact-sql)  
  
  
