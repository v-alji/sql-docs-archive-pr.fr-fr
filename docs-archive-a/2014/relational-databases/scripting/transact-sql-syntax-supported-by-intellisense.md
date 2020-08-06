---
title: Syntaxe Transact-SQL prise en charge par IntelliSense
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- Transact-SQL IntelliSense
- IntelliSense [SQL Server], Transact-SQL syntax
ms.assetid: 194e8f4f-fd7e-4f32-a169-f23531128004
author: rothja
ms.author: jroth
ms.openlocfilehash: b3d34fc79dd7817e64b34b61083415477860ce97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702667"
---
# <a name="transact-sql-syntax-supported-by-intellisense"></a><span data-ttu-id="2e80e-102">Syntaxe Transact-SQL prise en charge par IntelliSense</span><span class="sxs-lookup"><span data-stu-id="2e80e-102">Transact-SQL Syntax Supported by IntelliSense</span></span>
  <span data-ttu-id="2e80e-103">Cette rubrique décrit les instructions et les éléments syntaxiques [!INCLUDE[tsql](../../includes/tsql-md.md)] pris en charge par IntelliSense dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e80e-103">This topic describes the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and syntax elements that are supported by IntelliSense in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="statements-supported-by-intellisense"></a><span data-ttu-id="2e80e-104">Instructions prises en charge par IntelliSense</span><span class="sxs-lookup"><span data-stu-id="2e80e-104">Statements Supported by IntelliSense</span></span>  
 <span data-ttu-id="2e80e-105">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], IntelliSense prend uniquement en charge les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] les plus couramment utilisées.</span><span class="sxs-lookup"><span data-stu-id="2e80e-105">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], IntelliSense supports only the most commonly used [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="2e80e-106">Certaines conditions générales de l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] peuvent nuire au bon fonctionnement d’IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="2e80e-106">Some general [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor conditions might prevent IntelliSense from functioning.</span></span> <span data-ttu-id="2e80e-107">Pour plus d’informations, consultez [Résolution des problèmes liés à IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="2e80e-107">For more information, see [Troubleshooting IntelliSense &#40;SQL Server Management Studio&#41;](troubleshooting-intellisense.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e80e-108">IntelliSense n'est pas disponible pour les objets de base de données chiffrés, tels que les procédures stockées ou les fonctions définies par l'utilisateur chiffrées.</span><span class="sxs-lookup"><span data-stu-id="2e80e-108">IntelliSense is not available for encrypted database objects, such as encrypted stored procedures or user-defined functions.</span></span> <span data-ttu-id="2e80e-109">L'aide et les infos express sur les paramètres ne sont pas disponibles pour les paramètres de procédures stockées étendues et les types définis par l'utilisateur de l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="2e80e-109">Parameter help and Quick Info are not available for the parameters of extended stored procedures and CLR Integration user-defined types.</span></span>  
  
### <a name="select-statement"></a><span data-ttu-id="2e80e-110">Instruction SELECT</span><span class="sxs-lookup"><span data-stu-id="2e80e-110">SELECT Statement</span></span>  
 <span data-ttu-id="2e80e-111">L’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] fournit la prise en charge IntelliSense pour les éléments syntaxiques suivants de l’instruction SELECT :</span><span class="sxs-lookup"><span data-stu-id="2e80e-111">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor provides IntelliSense support for the following syntax elements in the SELECT statement:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2e80e-112">SELECT</span><span class="sxs-lookup"><span data-stu-id="2e80e-112">SELECT</span></span>|<span data-ttu-id="2e80e-113">WHERE</span><span class="sxs-lookup"><span data-stu-id="2e80e-113">WHERE</span></span>|  
|<span data-ttu-id="2e80e-114">FROM</span><span class="sxs-lookup"><span data-stu-id="2e80e-114">FROM</span></span>|<span data-ttu-id="2e80e-115">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="2e80e-115">ORDER BY</span></span>|  
|<span data-ttu-id="2e80e-116">HAVING</span><span class="sxs-lookup"><span data-stu-id="2e80e-116">HAVING</span></span>|<span data-ttu-id="2e80e-117">UNION</span><span class="sxs-lookup"><span data-stu-id="2e80e-117">UNION</span></span>|  
|<span data-ttu-id="2e80e-118">FOR</span><span class="sxs-lookup"><span data-stu-id="2e80e-118">FOR</span></span>|<span data-ttu-id="2e80e-119">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="2e80e-119">GROUP BY</span></span>|  
|<span data-ttu-id="2e80e-120">Haut de la page</span><span class="sxs-lookup"><span data-stu-id="2e80e-120">TOP</span></span>|<span data-ttu-id="2e80e-121">OPTION (conseil)</span><span class="sxs-lookup"><span data-stu-id="2e80e-121">OPTION (hint)</span></span>|  
  
### <a name="additional-transact-sql-statements-that-are-supported"></a><span data-ttu-id="2e80e-122">Instructions Transact-SQL supplémentaires prises en charge</span><span class="sxs-lookup"><span data-stu-id="2e80e-122">Additional Transact-SQL Statements That Are Supported</span></span>  
 <span data-ttu-id="2e80e-123">L’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] fournit également la prise en charge IntelliSense pour les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="2e80e-123">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor also provides IntelliSense support for [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are shown in the following table.</span></span>  
  
|<span data-ttu-id="2e80e-124">Instruction Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e80e-124">Transact-SQL statement</span></span>|<span data-ttu-id="2e80e-125">Syntaxe prise en charge</span><span class="sxs-lookup"><span data-stu-id="2e80e-125">Syntax supported</span></span>|  
|-----------------------------|----------------------|  
|[<span data-ttu-id="2e80e-126">INSERT</span><span class="sxs-lookup"><span data-stu-id="2e80e-126">INSERT</span></span>](/sql/t-sql/statements/insert-transact-sql)|<span data-ttu-id="2e80e-127">Toute la syntaxe, sauf la clause *execute_statement* .</span><span class="sxs-lookup"><span data-stu-id="2e80e-127">All syntax, except the *execute_statement* clause.</span></span>|  
|[<span data-ttu-id="2e80e-128">UPDATE</span><span class="sxs-lookup"><span data-stu-id="2e80e-128">UPDATE</span></span>](/sql/t-sql/queries/update-transact-sql)|<span data-ttu-id="2e80e-129">Toute la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="2e80e-129">All syntax.</span></span>|  
|[<span data-ttu-id="2e80e-130">DELETE</span><span class="sxs-lookup"><span data-stu-id="2e80e-130">DELETE</span></span>](/sql/t-sql/statements/delete-transact-sql)|<span data-ttu-id="2e80e-131">Toute la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="2e80e-131">All syntax.</span></span>|  
|[<span data-ttu-id="2e80e-132">DECLARE @local_variable</span><span class="sxs-lookup"><span data-stu-id="2e80e-132">DECLARE @local_variable</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)|<span data-ttu-id="2e80e-133">Toute la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="2e80e-133">All syntax.</span></span>|  
|[<span data-ttu-id="2e80e-134">DÉFINIE@local_variable</span><span class="sxs-lookup"><span data-stu-id="2e80e-134">SET @local_variable</span></span>](/sql/t-sql/language-elements/set-local-variable-transact-sql)|<span data-ttu-id="2e80e-135">Toute la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="2e80e-135">All syntax.</span></span>|  
|[<span data-ttu-id="2e80e-136">EXECUTE</span><span class="sxs-lookup"><span data-stu-id="2e80e-136">EXECUTE</span></span>](/sql/t-sql/language-elements/execute-transact-sql)|<span data-ttu-id="2e80e-137">Exécution des procédures stockées définies par l'utilisateur, des procédures stockées système, des fonctions définies par l'utilisateur et des fonctions système.</span><span class="sxs-lookup"><span data-stu-id="2e80e-137">Execution of user-defined stored procedures, system stored procedures, user-defined functions, and system functions.</span></span>|  
|[<span data-ttu-id="2e80e-138">CREATE TABLE</span><span class="sxs-lookup"><span data-stu-id="2e80e-138">CREATE TABLE</span></span>](/sql/t-sql/statements/create-table-transact-sql)|<span data-ttu-id="2e80e-139">Toute la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="2e80e-139">All syntax.</span></span>|  
|[<span data-ttu-id="2e80e-140">CREATE VIEW</span><span class="sxs-lookup"><span data-stu-id="2e80e-140">CREATE VIEW</span></span>](/sql/t-sql/statements/create-view-transact-sql)|<span data-ttu-id="2e80e-141">Toute la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="2e80e-141">All syntax.</span></span>|  
|[<span data-ttu-id="2e80e-142">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="2e80e-142">CREATE PROCEDURE</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)|<span data-ttu-id="2e80e-143">Toute syntaxe, avec les exceptions suivantes :</span><span class="sxs-lookup"><span data-stu-id="2e80e-143">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="2e80e-144">Il n'existe aucune prise en charge IntelliSense pour la clause EXTERNAL NAME.</span><span class="sxs-lookup"><span data-stu-id="2e80e-144">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="2e80e-145">Dans la clause AS, IntelliSense prend uniquement en charge les instructions et la syntaxe répertoriées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="2e80e-145">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="2e80e-146">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="2e80e-146">ALTER PROCEDURE</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)|<span data-ttu-id="2e80e-147">Toute syntaxe, avec les exceptions suivantes :</span><span class="sxs-lookup"><span data-stu-id="2e80e-147">All syntax, with the following exceptions:</span></span><br /><br /> <span data-ttu-id="2e80e-148">Il n'existe aucune prise en charge IntelliSense pour la clause EXTERNAL NAME.</span><span class="sxs-lookup"><span data-stu-id="2e80e-148">There is no IntelliSense support for the EXTERNAL NAME clause.</span></span><br /><br /> <span data-ttu-id="2e80e-149">Dans la clause AS, IntelliSense prend uniquement en charge les instructions et la syntaxe répertoriées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="2e80e-149">In the AS clause, IntelliSense supports only the statements and syntax that are listed in this topic.</span></span>|  
|[<span data-ttu-id="2e80e-150">USE</span><span class="sxs-lookup"><span data-stu-id="2e80e-150">USE</span></span>](/sql/t-sql/language-elements/use-transact-sql)|<span data-ttu-id="2e80e-151">Toute la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="2e80e-151">All syntax.</span></span>|  
  
## <a name="intellisense-in-supported-statements"></a><span data-ttu-id="2e80e-152">IntelliSense dans les instructions prises en charge</span><span class="sxs-lookup"><span data-stu-id="2e80e-152">IntelliSense in Supported Statements</span></span>  
 <span data-ttu-id="2e80e-153">IntelliSense dans l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] prend en charge les éléments syntaxiques suivants quand ils sont utilisés dans l’une des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] prises en charge :</span><span class="sxs-lookup"><span data-stu-id="2e80e-153">IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports the following syntax elements when they are used in one of the supported [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
-   <span data-ttu-id="2e80e-154">Tous les types de jointure, y compris APPLY.</span><span class="sxs-lookup"><span data-stu-id="2e80e-154">All join types, including APPLY</span></span>  
  
-   <span data-ttu-id="2e80e-155">PIVOT et UNPIVOT.</span><span class="sxs-lookup"><span data-stu-id="2e80e-155">PIVOT and UNPIVOT</span></span>  
  
-   <span data-ttu-id="2e80e-156">Références aux objets de base de données suivants :</span><span class="sxs-lookup"><span data-stu-id="2e80e-156">References to the following database objects:</span></span>  
  
    -   <span data-ttu-id="2e80e-157">Bases de données et schémas</span><span class="sxs-lookup"><span data-stu-id="2e80e-157">Databases and schemas</span></span>  
  
    -   <span data-ttu-id="2e80e-158">Tables, vues, fonctions table et expressions de table</span><span class="sxs-lookup"><span data-stu-id="2e80e-158">Tables, views, table-valued functions, and table expressions</span></span>  
  
    -   <span data-ttu-id="2e80e-159">Colonnes</span><span class="sxs-lookup"><span data-stu-id="2e80e-159">Columns</span></span>  
  
    -   <span data-ttu-id="2e80e-160">Procédures et paramètres de procédure</span><span class="sxs-lookup"><span data-stu-id="2e80e-160">Procedures and procedure parameters</span></span>  
  
    -   <span data-ttu-id="2e80e-161">Fonctions scalaires et expressions scalaires</span><span class="sxs-lookup"><span data-stu-id="2e80e-161">Scalar functions and scalar expressions</span></span>  
  
    -   <span data-ttu-id="2e80e-162">Variables locales</span><span class="sxs-lookup"><span data-stu-id="2e80e-162">Local variables</span></span>  
  
    -   <span data-ttu-id="2e80e-163">Expressions de table communes</span><span class="sxs-lookup"><span data-stu-id="2e80e-163">Common table expressions (CTE)</span></span>  
  
-   <span data-ttu-id="2e80e-164">Objets de base de données référencés uniquement dans une instruction CREATE ou ALTER du script ou du lot, mais qui n'existent pas dans la base de données parce que le script ou le lot n'a pas encore été exécuté.</span><span class="sxs-lookup"><span data-stu-id="2e80e-164">Database objects that are referenced only in CREATE or ALTER statements in the script or batch, but which do not exist in the database because the script or batch has not yet been run.</span></span> <span data-ttu-id="2e80e-165">Ces objets sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="2e80e-165">These objects are as follows:</span></span>  
  
    -   <span data-ttu-id="2e80e-166">Tables et procédures spécifiées dans une instruction CREATE TABLE ou CREATE PROCEDURE du script ou du lot.</span><span class="sxs-lookup"><span data-stu-id="2e80e-166">Tables and procedures that have been specified in a CREATE TABLE or CREATE PROCEDURE statement in the script or batch.</span></span>  
  
    -   <span data-ttu-id="2e80e-167">Modifications des tables et procédures spécifiées dans une instruction ALTER TABLE ou ALTER PROCEDURE du script ou lot.</span><span class="sxs-lookup"><span data-stu-id="2e80e-167">Changes to tables and procedures that have been specified in an ALTER TABLE or ALTER PROCEDURE statement in the script or batch.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e80e-168">IntelliSense n'est pas disponible pour les colonnes d'une instruction CREATE VIEW tant que l'instruction CREATE VIEW n'a pas été exécutée.</span><span class="sxs-lookup"><span data-stu-id="2e80e-168">IntelliSense is not available for the columns of a CREATE VIEW statement until the CREATE VIEW statement has been executed.</span></span>  
  
 <span data-ttu-id="2e80e-169">IntelliSense n'est pas fourni pour les éléments précédemment répertoriés lorsqu'ils sont utilisés dans d'autres instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e80e-169">IntelliSense is not provided for the previously listed elements when they are used in other [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="2e80e-170">Par exemple, il existe une prise en charge IntelliSense pour les noms de colonne utilisés dans une instruction SELECT, mais pas pour les colonnes utilisées dans l'instruction CREATE FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="2e80e-170">For example, there is IntelliSense support for column names that are used in a SELECT statement, but not for columns that are used in the CREATE FUNCTION statement.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2e80e-171">Exemples</span><span class="sxs-lookup"><span data-stu-id="2e80e-171">Examples</span></span>  
 <span data-ttu-id="2e80e-172">Dans un script ou lot [!INCLUDE[tsql](../../includes/tsql-md.md)] , IntelliSense dans l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] prend uniquement en charge les instructions et la syntaxe répertoriées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="2e80e-172">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor supports only the statements and syntax that are listed in this topic.</span></span> <span data-ttu-id="2e80e-173">Les exemples de code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivants indiquent les instructions et les éléments syntaxiques pris en charge par IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="2e80e-173">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code examples show what statements and syntax elements IntelliSense supports.</span></span> <span data-ttu-id="2e80e-174">Par exemple, dans le lot suivant, IntelliSense est disponible pour l'instruction `SELECT` lorsqu'elle est codée seule, mais pas lorsque `SELECT` est contenue dans une instruction `CREATE FUNCTION`</span><span class="sxs-lookup"><span data-stu-id="2e80e-174">For example, in the following batch, IntelliSense is available for the `SELECT` statement when it is coded by itself, but not when the `SELECT` is contained in a `CREATE FUNCTION` statement.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Name  
FROM Production.Product  
WHERE Name LIKE N'Road-250%' and Color = N'Red';  
GO  
CREATE FUNCTION Production.ufn_Red250 ()  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT Name  
    FROM AdventureWorks2012.Production.Product  
    WHERE Name LIKE N'Road-250%'  
      AND Color = N'Red'  
);GO  
```  
  
 <span data-ttu-id="2e80e-175">Ces fonctionnalités s'appliquent également aux jeux d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] de la clause AS d'une instruction CREATE PROCEDURE ou ALTER PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="2e80e-175">This functionality also applies to the sets of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the AS clause of a CREATE PROCEDURE or ALTER PROCEDURE statement.</span></span>  
  
 <span data-ttu-id="2e80e-176">Dans un script ou lot [!INCLUDE[tsql](../../includes/tsql-md.md)] , IntelliSense prend en charge les objets spécifiés dans une instruction CREATE ou ALTER ; toutefois, ces objets n'existent pas dans la base de données parce que les instructions n'ont pas été exécutées.</span><span class="sxs-lookup"><span data-stu-id="2e80e-176">Within a [!INCLUDE[tsql](../../includes/tsql-md.md)] script or batch, IntelliSense supports objects that have been specified in a CREATE or ALTER statement; however, these objects do not exist in the database because the statements have not been executed.</span></span> <span data-ttu-id="2e80e-177">Par exemple, vous pouvez entrer le code suivant dans l'éditeur de requête :</span><span class="sxs-lookup"><span data-stu-id="2e80e-177">For example, you might enter the following code in the Query Editor:</span></span>  
  
```  
USE MyTestDB;  
GO  
CREATE TABLE MyTable  
    (PrimaryKeyCol   INT PRIMARY KEY,  
    FirstNameCol      NVARCHAR(50),  
   LastNameCol       NVARCHAR(50));  
GO  
SELECT   
```  
  
 <span data-ttu-id="2e80e-178">Après que vous avez tapé `SELECT`, IntelliSense répertorie **PrimaryKeyCol**, **FirstNameCol**et **LastNameCol** comme éléments possibles dans la liste de sélection, même si le script n'a pas été exécuté et que `MyTable` n'existe pas encore dans `MyTestDB`.</span><span class="sxs-lookup"><span data-stu-id="2e80e-178">After you type `SELECT`, IntelliSense lists **PrimaryKeyCol**, **FirstNameCol**, and **LastNameCol** as possible elements in the select list, even if the script has not been executed and `MyTable` does not yet exist in `MyTestDB`.</span></span>  
  
  
