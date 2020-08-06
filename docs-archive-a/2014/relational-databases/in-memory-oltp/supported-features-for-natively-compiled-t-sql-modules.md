---
title: Constructions prises en charge dans les procédures stockées compilées en mode natif | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 05515013-28b5-4ccf-9a54-ae861448945b
author: rothja
ms.author: jroth
ms.openlocfilehash: 65e6e794c5858a68c4b2a9b298513911b487cf52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614063"
---
# <a name="supported-constructs-in-natively-compiled-stored-procedures"></a><span data-ttu-id="74c56-102">Constructions prises en charge dans les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="74c56-102">Supported Constructs in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="74c56-103">Cette rubrique contient la liste des fonctionnalités prises en charge pour les procédures stockées compilées en mode natif ([CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)) :</span><span class="sxs-lookup"><span data-stu-id="74c56-103">This topic contains a list of supported features for natively compiled stored procedures ([CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql)):</span></span>  
  
-   [<span data-ttu-id="74c56-104">Programmabilité dans les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="74c56-104">Programmability in Natively Compiled Stored Procedures</span></span>](#pncsp)  
  
-   [<span data-ttu-id="74c56-105">Opérateurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="74c56-105">Supported Operators</span></span>](#so)  
  
-   [<span data-ttu-id="74c56-106">Fonctions intégrées dans les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="74c56-106">Built-in Functions in Natively Compiled Stored Procedures</span></span>](#bfncsp)  
  
-   [<span data-ttu-id="74c56-107">Surface d'exposition de la requête dans des procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="74c56-107">Query Surface Area in Natively Compiled Stored Procedures</span></span>](#qsancsp)  
  
-   [<span data-ttu-id="74c56-108">Audit</span><span class="sxs-lookup"><span data-stu-id="74c56-108">Auditing</span></span>](#auditing)  
  
-   [<span data-ttu-id="74c56-109">Indicateurs de table, de requête et de jointure</span><span class="sxs-lookup"><span data-stu-id="74c56-109">Table, Query, and Join Hints</span></span>](#tqh)  
  
-   [<span data-ttu-id="74c56-110">Limitations sur le tri</span><span class="sxs-lookup"><span data-stu-id="74c56-110">Limitations on Sorting</span></span>](#los)  
  
 <span data-ttu-id="74c56-111">Pour plus d'informations sur les types de données pris en charge dans les procédures stockées compilées en mode natif, voir [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="74c56-111">For information on data types supported in natively compiled stored procedures, see [Supported Data Types](supported-data-types-for-in-memory-oltp.md).</span></span>  
  
 <span data-ttu-id="74c56-112">Pour plus d'informations sur les constructions qui ne sont pas prises en charge et sur la manière de contourner certaines des fonctionnalités qui ne sont pas prises en charge dans les procédures stockées compilées en mode natif, consultez [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="74c56-112">For complete information about unsupported constructs, and for information about how to work around some of the unsupported features in natively compiled stored procedures, see [Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md).</span></span> <span data-ttu-id="74c56-113">Pour plus d’informations sur les fonctionnalités non prises en charge, consultez [Les constructions Transact-SQL ne sont pas prises en charge par l’OLTP en mémoire](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="74c56-113">For more information about unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
##  <a name="programmability-in-natively-compiled-stored-procedures"></a><a name="pncsp"></a><span data-ttu-id="74c56-114">Programmabilité dans les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="74c56-114">Programmability in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="74c56-115">Les constructions suivantes sont admises :</span><span class="sxs-lookup"><span data-stu-id="74c56-115">The following are supported:</span></span>  
  
-   <span data-ttu-id="74c56-116">BEGIN ATOMIC (au niveau externe de la procédure stockée), LANGUAGE, ISOLATION LEVEL, DATEFORMAT et DATEFIRST</span><span class="sxs-lookup"><span data-stu-id="74c56-116">BEGIN ATOMIC (at the outer level of the stored procedure), LANGUAGE, ISOLATION LEVEL, DATEFORMAT, and DATEFIRST.</span></span>  
  
-   <span data-ttu-id="74c56-117">Variables déclarantes comme NULL ou NOT NULL</span><span class="sxs-lookup"><span data-stu-id="74c56-117">Declaring variables as NULL or NOT NULL.</span></span> <span data-ttu-id="74c56-118">Si une variable est déclarée NOT NULL, la déclaration doit avoir un initialiseur.</span><span class="sxs-lookup"><span data-stu-id="74c56-118">If a variable is declared as NOT NULL, the declaration must have an initializer.</span></span> <span data-ttu-id="74c56-119">Si une variable n'est pas déclarée NOT NULL, l'initialiseur est facultatif.</span><span class="sxs-lookup"><span data-stu-id="74c56-119">If a variable is not declared as NOT NULL, an initializer is optional.</span></span>  
  
-   <span data-ttu-id="74c56-120">IF et WHILE</span><span class="sxs-lookup"><span data-stu-id="74c56-120">IF and WHILE</span></span>  
  
-   <span data-ttu-id="74c56-121">INSERT/UPDATE/DELETE</span><span class="sxs-lookup"><span data-stu-id="74c56-121">INSERT/UPDATE/DELETE</span></span>  
  
     <span data-ttu-id="74c56-122">Les sous-requêtes ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="74c56-122">Subqueries are not supported.</span></span> <span data-ttu-id="74c56-123">Dans la clause WHERE ou HAVING, AND et BETWEEN sont pris en charge ; OR, NOT et IN ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="74c56-123">In the WHERE or HAVING clause, AND and BETWEEN are supported; OR, NOT, and IN are not supported.</span></span>  
  
-   <span data-ttu-id="74c56-124">Types de tables optimisées en mémoire et variables de table.</span><span class="sxs-lookup"><span data-stu-id="74c56-124">Memory-optimized table types and table variables.</span></span>  
  
-   <span data-ttu-id="74c56-125">RETURN</span><span class="sxs-lookup"><span data-stu-id="74c56-125">RETURN</span></span>  
  
-   <span data-ttu-id="74c56-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="74c56-126">SELECT</span></span>  
  
-   <span data-ttu-id="74c56-127">SET</span><span class="sxs-lookup"><span data-stu-id="74c56-127">SET</span></span>  
  
-   <span data-ttu-id="74c56-128">TRY/CATCH/THROW</span><span class="sxs-lookup"><span data-stu-id="74c56-128">TRY/CATCH/THROW</span></span>  
  
     <span data-ttu-id="74c56-129">Pour optimiser les performances, utilisez un bloc TRY/CATCH pour une procédure stockée compilée en mode natif entière.</span><span class="sxs-lookup"><span data-stu-id="74c56-129">To optimize performance, use a single TRY/CATCH block for an entire natively compiled stored procedure.</span></span>  
  
##  <a name="supported-operators"></a><a name="so"></a> <span data-ttu-id="74c56-130">Opérateurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="74c56-130">Supported Operators</span></span>  
 <span data-ttu-id="74c56-131">Les opérateurs suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="74c56-131">The following operators are supported.</span></span>  
  
-   <span data-ttu-id="74c56-132">Les [opérateurs de comparaison &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/comparison-operators-transact-sql) (par exemple, >, \<, > = et <=) sont pris en charge dans les conditions conditionnelles (if, while).</span><span class="sxs-lookup"><span data-stu-id="74c56-132">[Comparison Operators &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/comparison-operators-transact-sql) (for example, >, \<, >=, and <=) are supported in conditionals (IF, WHILE).</span></span>  
  
-   <span data-ttu-id="74c56-133">Opérateurs unaires (+, -).</span><span class="sxs-lookup"><span data-stu-id="74c56-133">Unary operators (+, -).</span></span>  
  
-   <span data-ttu-id="74c56-134">Opérateurs binaires (\*, /, +, -, % (modulo)).</span><span class="sxs-lookup"><span data-stu-id="74c56-134">Binary operators (\*, /, +, -, % (modulo)).</span></span>  
  
     <span data-ttu-id="74c56-135">L'opérateur plus (+) est pris en charge pour les nombres et les chaînes.</span><span class="sxs-lookup"><span data-stu-id="74c56-135">The plus operator (+) is supported on both numbers and strings.</span></span>  
  
-   <span data-ttu-id="74c56-136">Opérateurs logiques (AND, OR, NOT).</span><span class="sxs-lookup"><span data-stu-id="74c56-136">Logical operators (AND, OR, NOT).</span></span> <span data-ttu-id="74c56-137">OR et NOT sont pris en charge dans les instructions IF et WHILE mais pas dans les clauses WHERE ou HAVING.</span><span class="sxs-lookup"><span data-stu-id="74c56-137">OR and NOT are supported in IF and WHILE statements but not in WHERE or HAVING clauses.</span></span>  
  
-   <span data-ttu-id="74c56-138">Opérateurs au niveau du bit ~, &, |, et ^</span><span class="sxs-lookup"><span data-stu-id="74c56-138">Bitwise operators ~, &, |, and ^</span></span>  
  
##  <a name="built-in-functions-in-natively-compiled-stored-procedures"></a><a name="bfncsp"></a><span data-ttu-id="74c56-139">Fonctions intégrées dans les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="74c56-139">Built-in Functions in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="74c56-140">Les fonctions suivantes sont prises en charge dans les contraintes par défaut sur les tables optimisées en mémoire et dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="74c56-140">The following functions are supported in default constraints on memory-optimized tables and in natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="74c56-141">Fonctions mathématiques : ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANS, RAND, SIN, SQRT, SQUARE et TAN</span><span class="sxs-lookup"><span data-stu-id="74c56-141">Math Functions: ACOS, ASIN, ATAN, ATN2, COS, COT, DEGREES, EXP, LOG, LOG10, PI, POWER, RADIANS, RAND, SIN, SQRT, SQUARE, and TAN</span></span>  
  
-   <span data-ttu-id="74c56-142">Fonctions de date : CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME et YEAR.</span><span class="sxs-lookup"><span data-stu-id="74c56-142">Date Functions: CURRENT_TIMESTAMP, DATEADD, DATEDIFF, DATEFROMPARTS, DATEPART, DATETIME2FROMPARTS, DATETIMEFROMPARTS, DAY, EOMONTH, GETDATE, GETUTCDATE, MONTH, SMALLDATETIMEFROMPARTS, SYSDATETIME, SYSUTCDATETIME, and YEAR.</span></span>  
  
-   <span data-ttu-id="74c56-143">Fonctions de chaîne : LEN, LTRIM, RTRIM et SUBSTRING</span><span class="sxs-lookup"><span data-stu-id="74c56-143">String Functions: LEN, LTRIM, RTRIM, and SUBSTRING</span></span>  
  
-   <span data-ttu-id="74c56-144">Fonction d'identité : SCOPE_IDENTITY</span><span class="sxs-lookup"><span data-stu-id="74c56-144">Identity Function: SCOPE_IDENTITY</span></span>  
  
-   <span data-ttu-id="74c56-145">Fonctions NULL : ISNULL</span><span class="sxs-lookup"><span data-stu-id="74c56-145">NULL functions: ISNULL</span></span>  
  
-   <span data-ttu-id="74c56-146">Fonctions Uniqueidentifier : NEWID et NEWSEQUENTIALID</span><span class="sxs-lookup"><span data-stu-id="74c56-146">Uniqueidentifier functions: NEWID and NEWSEQUENTIALID</span></span>  
  
-   <span data-ttu-id="74c56-147">Fonctions d'erreur : ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY et ERROR_STATE</span><span class="sxs-lookup"><span data-stu-id="74c56-147">Error Functions: ERROR_LINE, ERROR_MESSAGE, ERROR_NUMBER, ERROR_PROCEDURE, ERROR_SEVERITY, and ERROR_STATE</span></span>  
  
-   <span data-ttu-id="74c56-148">Conversions : CAST et CONVERT.</span><span class="sxs-lookup"><span data-stu-id="74c56-148">Conversions: CAST and CONVERT.</span></span> <span data-ttu-id="74c56-149">Les conversions entre des chaînes de caractères Unicode et non-Unicode (n(var)char et (var)char) ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="74c56-149">Conversions between Unicode and non-Unicode character strings (n(var)char and (var)char) are not supported.</span></span>  
  
-   <span data-ttu-id="74c56-150">Fonctions système : @@rowcount.</span><span class="sxs-lookup"><span data-stu-id="74c56-150">System Functions: @@rowcount.</span></span> <span data-ttu-id="74c56-151">Les instructions dans les procédures stockées compilées en mode natif mettent à jour @@rowcount et vous pouvez utiliser @@rowcount dans une procédure stockée compilée en mode natif pour déterminer le nombre de lignes affectées par la dernière instruction exécutée dans cette procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="74c56-151">Statements inside natively compiled stored procedures update @@rowcount and you can use @@rowcount in a natively compiled stored procedure to determine the number of rows affected by the last statement executed within that natively compiled stored procedure.</span></span> <span data-ttu-id="74c56-152">Cependant, @@rowcount est réinitialisé à 0 au début et à la fin de l’exécution d’une procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="74c56-152">However, @@rowcount is reset to 0 at the start and at the end of the execution of a natively compiled stored procedure.</span></span>  
  
##  <a name="query-surface-area-in-natively-compiled-stored-procedures"></a><a name="qsancsp"></a><span data-ttu-id="74c56-153">Aire de requête dans les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="74c56-153">Query Surface Area in Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="74c56-154">Les constructions suivantes sont admises :</span><span class="sxs-lookup"><span data-stu-id="74c56-154">The following are supported:</span></span>  
  
-   <span data-ttu-id="74c56-155">BETWEEN</span><span class="sxs-lookup"><span data-stu-id="74c56-155">BETWEEN</span></span>  
  
-   <span data-ttu-id="74c56-156">Alias de noms de colonnes (en utilisant la syntaxe AS ou =).</span><span class="sxs-lookup"><span data-stu-id="74c56-156">Column name aliases (using either AS or = syntax).</span></span>  
  
-   <span data-ttu-id="74c56-157">CROSS JOIN et INNER JOIN sont uniquement prises en charge avec les requêtes SELECT.</span><span class="sxs-lookup"><span data-stu-id="74c56-157">CROSS JOIN and INNER JOIN, supported only with SELECT queries.</span></span>  
  
-   <span data-ttu-id="74c56-158">Les expressions sont prises en charge dans la liste de sélection et [dans &#40;clause Transact-SQL&#41;](/sql/t-sql/queries/where-transact-sql) si elles utilisent un opérateur pris en charge.</span><span class="sxs-lookup"><span data-stu-id="74c56-158">Expressions are supported in SELECT list and [WHERE &#40;Transact-SQL&#41;](/sql/t-sql/queries/where-transact-sql) clause if they use a supported operator.</span></span> <span data-ttu-id="74c56-159">Voir [Opérateurs pris en charge](#so) pour obtenir la liste des opérateurs actuellement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="74c56-159">See [Supported Operators](#so) for the list of currently-supported operators.</span></span>  
  
-   <span data-ttu-id="74c56-160">Prédicat de filtre IS [NOT] NULL</span><span class="sxs-lookup"><span data-stu-id="74c56-160">Filter predicate IS [NOT] NULL</span></span>  
  
-   <span data-ttu-id="74c56-161">FROM \<memory optimized table></span><span class="sxs-lookup"><span data-stu-id="74c56-161">FROM \<memory optimized table></span></span>  
  
-   <span data-ttu-id="74c56-162">[Regrouper par &#40;&#41;Transact-SQL](/sql/t-sql/queries/select-group-by-transact-sql) est pris en charge, ainsi que les fonctions d’agrégation AVG, COUNT, COUNT_BIG, min, Max et Sum.</span><span class="sxs-lookup"><span data-stu-id="74c56-162">[GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) is supported, along with the aggregate functions AVG, COUNT, COUNT_BIG, MIN, MAX, and SUM.</span></span> <span data-ttu-id="74c56-163">MIN et MAX ne sont pas pris en charge pour les types nvarchar, char, varchar, varchar, varbinary, et binary.</span><span class="sxs-lookup"><span data-stu-id="74c56-163">MIN and MAX are not supported for types nvarchar, char, varchar, varchar, varbinary, and binary.</span></span> <span data-ttu-id="74c56-164">La [clause Order by &#40;&#41;Transact-SQL](/sql/t-sql/queries/select-order-by-clause-transact-sql) est prise en charge avec [GROUP BY &#40;&#41;Transact-SQL](/sql/t-sql/queries/select-group-by-transact-sql) si une expression dans la liste order by apparaît textuellement dans la liste Group by.</span><span class="sxs-lookup"><span data-stu-id="74c56-164">[ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql) is supported with [GROUP BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-group-by-transact-sql) if an expression in the ORDER BY list appears verbatim in the GROUP BY list.</span></span> <span data-ttu-id="74c56-165">Par exemple, GROUP BY a + b ORDER BY a + b est pris en charge, mais GROUP BY a, b ORDER BY a + b n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="74c56-165">For example, GROUP BY a + b ORDER BY a + b is supported, but GROUP BY a, b ORDER BY a + b is not.</span></span>  
  
-   <span data-ttu-id="74c56-166">HAVING, assujetti aux mêmes limitations d'expression que la clause WHERE</span><span class="sxs-lookup"><span data-stu-id="74c56-166">HAVING, subject to the same expression limitations as the WHERE clause.</span></span>  
  
-   <span data-ttu-id="74c56-167">INSERT VALUES (une ligne par instruction) et INSERT SELECT</span><span class="sxs-lookup"><span data-stu-id="74c56-167">INSERT VALUES (one row per statement) and INSERT SELECT</span></span>  
  
-   <span data-ttu-id="74c56-168">CLASSEMENT par <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="74c56-168">ORDER BY <sup>1</sup></span></span>  
  
-   <span data-ttu-id="74c56-169">Prédicats qui ne référencent pas de colonne.</span><span class="sxs-lookup"><span data-stu-id="74c56-169">Predicates not referencing a column.</span></span>  
  
-   <span data-ttu-id="74c56-170">SELECT, UPDATE et DELETE</span><span class="sxs-lookup"><span data-stu-id="74c56-170">SELECT, UPDATE, and DELETE</span></span>  
  
-   <span data-ttu-id="74c56-171">PREMIERS <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="74c56-171">TOP <sup>1</sup></span></span>  
  
-   <span data-ttu-id="74c56-172">Affectation de variable dans la liste SELECT.</span><span class="sxs-lookup"><span data-stu-id="74c56-172">Variable assignment in the SELECT list.</span></span>  
  
-   <span data-ttu-id="74c56-173">OÙ... LES</span><span class="sxs-lookup"><span data-stu-id="74c56-173">WHERE ... AND</span></span>  
  
 <span data-ttu-id="74c56-174"><sup>1</sup> order by et Top sont pris en charge dans les procédures stockées compilées en mode natif, avec quelques restrictions :</span><span class="sxs-lookup"><span data-stu-id="74c56-174"><sup>1</sup> ORDER BY and TOP are supported in natively compiled stored procedures, with some restrictions:</span></span>  
  
-   <span data-ttu-id="74c56-175">Il n'existe aucune prise en charge de `DISTINCT` dans la clause `SELECT` ou `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="74c56-175">There is no support for `DISTINCT` in the `SELECT` or `ORDER BY` clause.</span></span>  
  
-   <span data-ttu-id="74c56-176">Il n'existe aucune prise en charge de `WITH TIES` ou `PERCENT` dans la clause `TOP`.</span><span class="sxs-lookup"><span data-stu-id="74c56-176">There is no support for `WITH TIES` or `PERCENT` in the `TOP` clause.</span></span>  
  
-   <span data-ttu-id="74c56-177">La clause `TOP` associée à `ORDER BY` ne prend pas en charge plus de 8 192 lignes lorsqu'une constante est utilisée dans la clause `TOP`.</span><span class="sxs-lookup"><span data-stu-id="74c56-177">`TOP` combined with `ORDER BY` does not support more than 8,192 when using a constant in the `TOP` clause.</span></span> <span data-ttu-id="74c56-178">Cette limite peut être abaissée lorsque la requête contient des jointures ou des fonctions d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="74c56-178">This limit may be lowered in case the query contains joins or aggregate functions.</span></span> <span data-ttu-id="74c56-179">Par exemple, avec une jointure (entre deux tables), la limite est de 4 096 lignes.</span><span class="sxs-lookup"><span data-stu-id="74c56-179">(For example, with one join (two tables), the limit is 4,096 rows.</span></span> <span data-ttu-id="74c56-180">Avec deux jointures (entre trois tables), la limite est de 2 730 lignes.</span><span class="sxs-lookup"><span data-stu-id="74c56-180">With two joins (three tables), the limit is 2,730 rows.)</span></span>  
  
     <span data-ttu-id="74c56-181">Vous pouvez obtenir plus de 8 192 résultats en stockant le nombre de lignes dans une variable :</span><span class="sxs-lookup"><span data-stu-id="74c56-181">You can obtain results greater than 8,192 by storing the number of rows in a variable:</span></span>  
  
    ```sql  
    DECLARE @v INT = 9000  
    SELECT TOP (@v) ... FROM ... ORDER BY ...  
    ```  
  
 <span data-ttu-id="74c56-182">Cependant, l'utilisation d'une constante dans la clause `TOP` donne de meilleurs résultats qu'une variable.</span><span class="sxs-lookup"><span data-stu-id="74c56-182">However, a constant in the `TOP` clause results in better performance compared to using a variable.</span></span>  
  
 <span data-ttu-id="74c56-183">Ces limitations ne s'appliquent pas à l'accès en [!INCLUDE[tsql](../../includes/tsql-md.md)] interprété sur les tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="74c56-183">These restrictions do not apply to interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] access on memory-optimized tables.</span></span>  
  
##  <a name="auditing"></a><a name="auditing"></a> <span data-ttu-id="74c56-184">Audit</span><span class="sxs-lookup"><span data-stu-id="74c56-184">Auditing</span></span>  
 <span data-ttu-id="74c56-185">L'audit au niveau de la procédure est pris en charge dans les procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="74c56-185">Procedure level auditing is supported in natively compiled stored procedures.</span></span> <span data-ttu-id="74c56-186">L'audit au niveau de l'instruction n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="74c56-186">Statement level auditing is not supported.</span></span>  
  
 <span data-ttu-id="74c56-187">Pour plus d'informations sur l'audit, consultez [Créer une spécification de l'audit du serveur et de la base de données](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="74c56-187">For more information about auditing, see [Create a Server Audit and Database Audit Specification](../security/auditing/create-a-server-audit-and-database-audit-specification.md).</span></span>  
  
##  <a name="table-query-and-join-hints"></a><a name="tqh"></a><span data-ttu-id="74c56-188">Indicateurs de table, de requête et de jointure</span><span class="sxs-lookup"><span data-stu-id="74c56-188">Table, Query, and Join Hints</span></span>  
 <span data-ttu-id="74c56-189">Les constructions suivantes sont admises :</span><span class="sxs-lookup"><span data-stu-id="74c56-189">The following are supported:</span></span>  
  
-   <span data-ttu-id="74c56-190">Indicateurs INDEX, FORCESCAN et FORCESEEK, dans la syntaxe des indicateurs de table ou dans la [Clause OPTION &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) de la requête.</span><span class="sxs-lookup"><span data-stu-id="74c56-190">INDEX, FORCESCAN, and FORCESEEK hints, either in table hints syntax or in [OPTION Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/option-clause-transact-sql) of the query.</span></span>  
  
-   <span data-ttu-id="74c56-191">FORCE ORDER</span><span class="sxs-lookup"><span data-stu-id="74c56-191">FORCE ORDER</span></span>  
  
-   <span data-ttu-id="74c56-192">INNER LOOP JOIN</span><span class="sxs-lookup"><span data-stu-id="74c56-192">INNER LOOP JOIN</span></span>  
  
-   <span data-ttu-id="74c56-193">OPTIMIZE FOR</span><span class="sxs-lookup"><span data-stu-id="74c56-193">OPTIMIZE FOR</span></span>  
  
 <span data-ttu-id="74c56-194">Pour plus d’informations, consultez [indicateurs &#40;&#41;Transact-SQL ](/sql/t-sql/queries/hints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="74c56-194">For more information, see [Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql).</span></span>  
  
##  <a name="limitations-on-sorting"></a><a name="los"></a> <span data-ttu-id="74c56-195">Limitations sur le tri</span><span class="sxs-lookup"><span data-stu-id="74c56-195">Limitations on Sorting</span></span>  
 <span data-ttu-id="74c56-196">Vous pouvez trier plus de 8000 lignes dans une requête qui utilise [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) et une [Clause ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="74c56-196">You can sort greater than 8,000 rows in a query that uses [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span> <span data-ttu-id="74c56-197">Toutefois, sans [Clause ORDER BY &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) peut trier jusqu’à 8000 lignes (moins s’il existe des jointures).</span><span class="sxs-lookup"><span data-stu-id="74c56-197">However, without [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) can sort up to 8,000 rows (fewer rows if there are joins).</span></span>  
  
 <span data-ttu-id="74c56-198">Si votre requête utilise à la fois l’opérateur [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) et une [Clause ORDER BY&#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), vous pouvez spécifier jusqu’à 8192 lignes pour l’opérateur TOP.</span><span class="sxs-lookup"><span data-stu-id="74c56-198">If your query uses both the [TOP &#40;Transact-SQL&#41;](/sql/t-sql/queries/top-transact-sql) operator and an [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql), you can specify up to 8192 rows for the TOP operator.</span></span> <span data-ttu-id="74c56-199">Si vous spécifiez plus de 8 192 lignes, le message d’erreur suivant s’affiche : **Msg 41398, Niveau 16, État 1, Procédure *\<procedureName>* , Ligne *\<lineNumber>* L’opérateur TOP peut retourner au maximum 8 192 lignes ; *\<number>* demandées.**</span><span class="sxs-lookup"><span data-stu-id="74c56-199">If you specify more than 8192 rows you get the error message: **Msg 41398, Level 16, State 1, Procedure *\<procedureName>*, Line *\<lineNumber>* The TOP operator can return a maximum of 8192 rows; *\<number>* was requested.**</span></span>  
  
 <span data-ttu-id="74c56-200">Si vous n'avez pas de clause TOP, triez les lignes avec ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="74c56-200">If you do not have a TOP clause, you can sort any number of rows with ORDER BY.</span></span>  
  
 <span data-ttu-id="74c56-201">Si vous n'utilisez pas de clause ORDER BY, utilisez une valeur entière avec l'opérateur TOP.</span><span class="sxs-lookup"><span data-stu-id="74c56-201">If you do not use an ORDER BY clause, you can use any integer value with the TOP operator.</span></span>  
  
 <span data-ttu-id="74c56-202">Exemple avec TOP N = 8192 : Compiles</span><span class="sxs-lookup"><span data-stu-id="74c56-202">Example with TOP N = 8192: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8192 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="74c56-203">Exemple avec TOP N > 8192 : Fails to compile.</span><span class="sxs-lookup"><span data-stu-id="74c56-203">Example with TOP N > 8192: Fails to compile.</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    SELECT TOP 8193 ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="74c56-204">La limitation de 8192 lignes s'applique uniquement à `TOP N` où `N` est une constante, comme dans les exemples précédents.</span><span class="sxs-lookup"><span data-stu-id="74c56-204">The 8192 row limitation only applies to `TOP N` where `N` is a constant, as in the preceding examples.</span></span>  <span data-ttu-id="74c56-205">Si `N` doit être supérieur à 8192, vous pouvez affecter la valeur à une variable et utiliser cette variable avec `TOP`.</span><span class="sxs-lookup"><span data-stu-id="74c56-205">If you need `N` greater than 8192 you can assign the value to a variable and use that variable with `TOP`.</span></span>  
  
 <span data-ttu-id="74c56-206">Exemple utilisant une variable : Compiles</span><span class="sxs-lookup"><span data-stu-id="74c56-206">Example using a variable: Compiles</span></span>  
  
```sql  
CREATE PROCEDURE testTop  
WITH EXECUTE AS OWNER, SCHEMABINDING, NATIVE_COMPILATION  
  AS  
  BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
    DECLARE @v int = 8193   
    SELECT TOP (@v) ShoppingCartId, CreatedDate, TotalPrice FROM dbo.ShoppingCart  
    ORDER BY ShoppingCartId DESC  
  END;  
GO  
```  
  
 <span data-ttu-id="74c56-207">**Limitations sur les lignes retournées :** il existe deux cas de figure qui peuvent potentiellement réduire le nombre de lignes retournées par l’opérateur TOP :</span><span class="sxs-lookup"><span data-stu-id="74c56-207">**Limitations on rows returned:** There are two cases where that can potentially reduce the number of rows that can be returned by the TOP operator:</span></span>  
  
-   <span data-ttu-id="74c56-208">L'utilisation de JOINs dans la requête.</span><span class="sxs-lookup"><span data-stu-id="74c56-208">Using JOINs in the query.</span></span>  <span data-ttu-id="74c56-209">L'impact de JOINs sur une limitation dépend du plan de requête.</span><span class="sxs-lookup"><span data-stu-id="74c56-209">The influence of JOINs on the limitation depends on the query plan.</span></span>  
  
-   <span data-ttu-id="74c56-210">L'utilisation de fonctions d'agrégation ou de références à des fonctions d'agrégation dans la clause ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="74c56-210">Using aggregate functions or references to aggregate functions in the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="74c56-211">La formule pour calculer la valeur maximale N prise en charge dans le pire des cas dans TOP est : `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span><span class="sxs-lookup"><span data-stu-id="74c56-211">The formula to calculate a worst case maximum supported N in TOP N is: `N = floor ( 65536 / number_of_tables * 8 + total_size+of+aggs )`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c56-212">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74c56-212">See Also</span></span>  
 <span data-ttu-id="74c56-213">[Procédures stockées compilées en mode natif](natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="74c56-213">[Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="74c56-214">Problèmes de migration pour les procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="74c56-214">Migration Issues for Natively Compiled Stored Procedures</span></span>](migration-issues-for-natively-compiled-stored-procedures.md)  
  
  
