---
title: Index sur les colonnes calculées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, index creation
- index creation [SQL Server], computed columns
- imprecise columns
- persisted computed columns
- precise [SQL Server]
ms.assetid: 8d17ac9c-f3af-4bbb-9cc1-5cf647e994c4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ecbca9e7838c4c9395a8bcb6e11351c40f7037f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709420"
---
# <a name="indexes-on-computed-columns"></a><span data-ttu-id="4bf16-102">Index sur les colonnes calculées</span><span class="sxs-lookup"><span data-stu-id="4bf16-102">Indexes on Computed Columns</span></span>
  <span data-ttu-id="4bf16-103">Vous pouvez définir des index sur des colonnes calculées si les règles suivantes sont respectées :</span><span class="sxs-lookup"><span data-stu-id="4bf16-103">You can define indexes on computed columns as long as the following requirements are met:</span></span>  
  
-   <span data-ttu-id="4bf16-104">Conditions requises liées à la propriété</span><span class="sxs-lookup"><span data-stu-id="4bf16-104">Ownership requirements</span></span>  
  
-   <span data-ttu-id="4bf16-105">Conditions requises liées au déterminisme</span><span class="sxs-lookup"><span data-stu-id="4bf16-105">Determinism requirements</span></span>  
  
-   <span data-ttu-id="4bf16-106">Conditions requises liées à la précision</span><span class="sxs-lookup"><span data-stu-id="4bf16-106">Precision requirements</span></span>  
  
-   <span data-ttu-id="4bf16-107">Conditions requises liées aux types de données</span><span class="sxs-lookup"><span data-stu-id="4bf16-107">Data type requirements</span></span>  
  
-   <span data-ttu-id="4bf16-108">Conditions requises liées à l'option SET</span><span class="sxs-lookup"><span data-stu-id="4bf16-108">SET option requirements</span></span>  
  
 <span data-ttu-id="4bf16-109">**Ownership Requirements**</span><span class="sxs-lookup"><span data-stu-id="4bf16-109">**Ownership Requirements**</span></span>  
  
 <span data-ttu-id="4bf16-110">Toutes les références de fonctions dans la colonne calculée doivent avoir le même propriétaire que la table.</span><span class="sxs-lookup"><span data-stu-id="4bf16-110">All function references in the computed column must have the same owner as the table.</span></span>  
  
 <span data-ttu-id="4bf16-111">**Determinism Requirements**</span><span class="sxs-lookup"><span data-stu-id="4bf16-111">**Determinism Requirements**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4bf16-112">Une expression est déterministe lorsqu'elle retourne toujours le même résultat pour un ensemble donné d'entrées.</span><span class="sxs-lookup"><span data-stu-id="4bf16-112">Expressions are deterministic if they always return the same result for a specified set of inputs.</span></span> <span data-ttu-id="4bf16-113">La propriété **IsDeterministic** de la fonction [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) indique si un paramètre *computed_column_expression* est déterministe ou non.</span><span class="sxs-lookup"><span data-stu-id="4bf16-113">The **IsDeterministic** property of the [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) function reports whether a *computed_column_expression* is deterministic.</span></span>  
  
 <span data-ttu-id="4bf16-114">Le paramètre *computed_column_expression* doit être déterministe.</span><span class="sxs-lookup"><span data-stu-id="4bf16-114">The *computed_column_expression* must be deterministic.</span></span> <span data-ttu-id="4bf16-115">Un paramètre *computed_column_expression* est déterministe quand une ou plusieurs des conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="4bf16-115">A *computed_column_expression* is deterministic when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="4bf16-116">Toutes les fonctions référencées par l'expression sont déterministes et précises,</span><span class="sxs-lookup"><span data-stu-id="4bf16-116">All functions that are referenced by the expression are deterministic and precise.</span></span> <span data-ttu-id="4bf16-117">notamment les fonctions définies par l'utilisateur et les fonctions intégrées.</span><span class="sxs-lookup"><span data-stu-id="4bf16-117">These functions include both user-defined and built-in functions.</span></span> <span data-ttu-id="4bf16-118">Pour plus d’informations, consultez [Fonctions déterministes et non déterministes](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span><span class="sxs-lookup"><span data-stu-id="4bf16-118">For more information, see [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span></span> <span data-ttu-id="4bf16-119">Les fonctions peuvent être imprécises si la colonne calculée est de type PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="4bf16-119">Functions might be imprecise if the computed column is PERSISTED.</span></span> <span data-ttu-id="4bf16-120">Pour plus d’informations, consultez [Création d’index sur des colonnes calculées persistantes](#BKMK_persisted) , plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4bf16-120">For more information, see [Creating Indexes on Persisted Computed Columns](#BKMK_persisted) later in this topic.</span></span>  
  
-   <span data-ttu-id="4bf16-121">Toutes les colonnes auxquelles l'expression fait référence proviennent de la table contenant la colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="4bf16-121">All columns that are referenced in the expression come from the table that contains the computed column.</span></span>  
  
-   <span data-ttu-id="4bf16-122">Aucune référence de colonne n'extrait de données provenant de plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="4bf16-122">No column reference pulls data from multiple rows.</span></span> <span data-ttu-id="4bf16-123">Par exemple, certaines fonctions d’agrégation, telles que SUM ou AVG, dépendent de données provenant de plusieurs lignes et rendraient un paramètre *computed_column_expression* non déterministe.</span><span class="sxs-lookup"><span data-stu-id="4bf16-123">For example, aggregate functions such as SUM or AVG depend on data from multiple rows and would make a *computed_column_expression* nondeterministic.</span></span>  
  
-   <span data-ttu-id="4bf16-124">Le paramètre *computed_column_expression* n’a pas d’accès aux données système ni utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4bf16-124">The *computed_column_expression* has no system data access or user data access.</span></span>  
  
 <span data-ttu-id="4bf16-125">Une colonne calculée qui contient une expression CLR (Common Language Runtime) doit être déterministe et marquée comme PERSISTED avant de pouvoir être indexée.</span><span class="sxs-lookup"><span data-stu-id="4bf16-125">Any computed column that contains a common language runtime (CLR) expression must be deterministic and marked PERSISTED before the column can be indexed.</span></span> <span data-ttu-id="4bf16-126">Les expressions de type CLR définies par l'utilisateur sont permises dans les définitions de colonnes calculées.</span><span class="sxs-lookup"><span data-stu-id="4bf16-126">CLR user-defined type expressions are allowed in computed column definitions.</span></span> <span data-ttu-id="4bf16-127">Les colonnes calculées de type CLR définies par l'utilisateur peuvent être indexées à condition que le type soit comparable.</span><span class="sxs-lookup"><span data-stu-id="4bf16-127">Computed columns whose type is a CLR user-defined type can be indexed as long as the type is comparable.</span></span> <span data-ttu-id="4bf16-128">Pour plus d’informations, consultez [Types CLR définis par l’utilisateur](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="4bf16-128">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4bf16-129">Lorsque vous faites référence aux littéraux de chaîne de type de données de date dans des colonnes calculées indexées dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il est recommandé de convertir explicitement le littéral dans le type de date souhaité à l'aide d'un style de format de date déterministe.</span><span class="sxs-lookup"><span data-stu-id="4bf16-129">When you refer to string literals of the date data type in indexed computed columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], we recommend that you explicitly convert the literal to the date type that you want by using a deterministic date format style.</span></span> <span data-ttu-id="4bf16-130">Pour obtenir la liste des styles de formats de date déterministes, consultez [CAST et CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4bf16-130">For a list of the date format styles that are deterministic, see [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span> <span data-ttu-id="4bf16-131">Les expressions qui impliquent une conversion implicite des chaînes de caractères en type de données de date sont considérées comme non déterministes, à moins que le niveau de compatibilité de la base de données ne soit réglé sur 80 ou sur une valeur inférieure.</span><span class="sxs-lookup"><span data-stu-id="4bf16-131">Expressions that involve implicit conversion of character strings to date data types are considered nondeterministic, unless the database compatibility level is set to 80 or earlier.</span></span> <span data-ttu-id="4bf16-132">Cela est dû au fait que les résultats dépendent des paramètres [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) et [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) de la session serveur.</span><span class="sxs-lookup"><span data-stu-id="4bf16-132">This is because the results depend on the [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) and [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) settings of the server session.</span></span> <span data-ttu-id="4bf16-133">Par exemple, les résultats de l'expression `CONVERT (datetime, '30 listopad 1996', 113)` dépendent du paramètre LANGUAGE, car la chaîne '`30 listopad 1996`' désigne des mois différents selon la langue.</span><span class="sxs-lookup"><span data-stu-id="4bf16-133">For example, the results of the expression `CONVERT (datetime, '30 listopad 1996', 113)` depend on the LANGUAGE setting because the string '`30 listopad 1996`' means different months in different languages.</span></span> <span data-ttu-id="4bf16-134">De même, dans l'expression `DATEADD(mm,3,'2000-12-01')`, le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] interprète la chaîne `'2000-12-01'` en se basant sur le paramètre DATEFORMAT.</span><span class="sxs-lookup"><span data-stu-id="4bf16-134">Similarly, in the expression `DATEADD(mm,3,'2000-12-01')`, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] interprets the string `'2000-12-01'` based on the DATEFORMAT setting.</span></span>  
>   
>  <span data-ttu-id="4bf16-135">La conversion implicite de données de caractères non Unicode entre les classements est aussi considérée comme non déterministe, à moins que le niveau de compatibilité soit égal ou inférieur à 80.</span><span class="sxs-lookup"><span data-stu-id="4bf16-135">Implicit conversion of non-Unicode character data between collations is also considered nondeterministic, unless the compatibility level is set to 80 or earlier.</span></span>  
>   
>  <span data-ttu-id="4bf16-136">Lorsque le niveau de compatibilité de la base de données est égal à 90, vous ne pouvez pas créer d'index sur les colonnes calculées qui contiennent ces expressions.</span><span class="sxs-lookup"><span data-stu-id="4bf16-136">When the database compatibility level setting is 90, you cannot create indexes on computed columns that contain these expressions.</span></span> <span data-ttu-id="4bf16-137">Cependant, les colonnes calculées existantes qui contiennent ces expressions provenant d'une base de données mise à niveau sont gérables.</span><span class="sxs-lookup"><span data-stu-id="4bf16-137">However, existing computed columns that contain these expressions from an upgraded database are maintainable.</span></span> <span data-ttu-id="4bf16-138">Si vous utilisez des colonnes calculées indexées contenant une chaîne implicite pour les conversions de dates, afin d'éviter tout endommagement éventuel d'index, assurez-vous que les paramètres LANGUAGE et DATEFORMAT sont cohérents dans vos bases de données et applications.</span><span class="sxs-lookup"><span data-stu-id="4bf16-138">If you use indexed computed columns that contain implicit string to date conversions, to avoid possible index corruption, make sure that the LANGUAGE and DATEFORMAT settings are consistent in your databases and applications.</span></span>  
  
 <span data-ttu-id="4bf16-139">**Precision Requirements**</span><span class="sxs-lookup"><span data-stu-id="4bf16-139">**Precision Requirements**</span></span>  
  
 <span data-ttu-id="4bf16-140">Le paramètre *computed_column_expression* doit être précis.</span><span class="sxs-lookup"><span data-stu-id="4bf16-140">The *computed_column_expression* must be precise.</span></span> <span data-ttu-id="4bf16-141">Un paramètre *computed_column_expression* est précis quand une ou plusieurs des conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="4bf16-141">A *computed_column_expression* is precise when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="4bf16-142">Ce n'est pas une expression composée de données de type `float` ou `real`.</span><span class="sxs-lookup"><span data-stu-id="4bf16-142">It is not an expression of the `float` or `real` data types.</span></span>  
  
-   <span data-ttu-id="4bf16-143">L'expression n'utilise pas de données de type `float` ou `real` dans sa définition.</span><span class="sxs-lookup"><span data-stu-id="4bf16-143">It does not use a `float` or `real` data type in its definition.</span></span> <span data-ttu-id="4bf16-144">Par exemple, dans l'instruction suivante, la colonne `y` est de type `int` et déterministe, mais pas précise.</span><span class="sxs-lookup"><span data-stu-id="4bf16-144">For example, in the following statement, column `y` is `int` and deterministic but not precise.</span></span>  
  
    ```  
    CREATE TABLE t2 (a int, b int, c int, x float,   
       y AS CASE x   
             WHEN 0 THEN a   
             WHEN 1 THEN b   
             ELSE c   
          END);  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="4bf16-145">Toute expression `float` ou `real` est considérée comme non précise et ne peut pas être une clé d'index. Autrement dit, une expression `float` ou `real` peut être utilisée dans une vue indexée mais pas en tant que clé.</span><span class="sxs-lookup"><span data-stu-id="4bf16-145">Any `float` or `real` expression is considered imprecise and cannot be a key of an index; a `float` or `real` expression can be used in an indexed view but not as a key.</span></span> <span data-ttu-id="4bf16-146">Ce point s'applique également aux colonnes calculées.</span><span class="sxs-lookup"><span data-stu-id="4bf16-146">This is true also for computed columns.</span></span> <span data-ttu-id="4bf16-147">Toute fonction, expression ou fonction définie par l'utilisateur est considérée imprécise si elle contient des expressions `float` ou `real`,</span><span class="sxs-lookup"><span data-stu-id="4bf16-147">Any function, expression, or user-defined function is considered imprecise if it contains any `float` or `real` expressions.</span></span> <span data-ttu-id="4bf16-148">même logiques (comparaisons).</span><span class="sxs-lookup"><span data-stu-id="4bf16-148">This includes logical ones (comparisons).</span></span>  
  
 <span data-ttu-id="4bf16-149">La propriété **IsPrecise** de la fonction COLUMNPROPERTY indique si un paramètre *computed_column_expression* est précis ou non.</span><span class="sxs-lookup"><span data-stu-id="4bf16-149">The **IsPrecise** property of the COLUMNPROPERTY function reports whether a *computed_column_expression* is precise.</span></span>  
  
 <span data-ttu-id="4bf16-150">**Data Type Requirements**</span><span class="sxs-lookup"><span data-stu-id="4bf16-150">**Data Type Requirements**</span></span>  
  
-   <span data-ttu-id="4bf16-151">La *computed_column_expression* définie pour la colonne calculée ne peut pas correspondre aux `text` `ntext` types de données, ou `image` .</span><span class="sxs-lookup"><span data-stu-id="4bf16-151">The *computed_column_expression* defined for the computed column cannot evaluate to the `text`, `ntext`, or `image` data types.</span></span>  
  
-   <span data-ttu-id="4bf16-152">Les colonnes calculées dérivées des types de données `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)` et `xml` peuvent être indexées tant que le type de données utilisé dans la colonne calculée lui permet d'être une colonne d'index clés.</span><span class="sxs-lookup"><span data-stu-id="4bf16-152">Computed columns derived from `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, and `xml` data types can be indexed as long as the computed column data type is allowable as an index key column.</span></span>  
  
-   <span data-ttu-id="4bf16-153">Les colonnes calculées dérivées des types de données `image`, `ntext` et `text` peuvent être des colonnes (incluses) non-clés dans un index non-cluster tant que le type de données utilisé dans la colonne calculée lui permet d'être une colonne d'index non-clés.</span><span class="sxs-lookup"><span data-stu-id="4bf16-153">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey (included) columns in a nonclustered index as long as the computed column data type is allowable as a nonkey index column.</span></span>  
  
 <span data-ttu-id="4bf16-154">**Conditions requises liées à l'option SET**</span><span class="sxs-lookup"><span data-stu-id="4bf16-154">**SET Option Requirements**</span></span>  
  
-   <span data-ttu-id="4bf16-155">L'option de niveau de connexion ANSI_NULLS doit être activée (ON) lors de l'exécution de l'instruction CREATE TABLE ou ALTER TABLE qui définit la colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="4bf16-155">The ANSI_NULLS connection-level option must be set to ON when the CREATE TABLE or ALTER TABLE statement that defines the computed column is executed.</span></span> <span data-ttu-id="4bf16-156">La fonction [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) indique si l’option est activée par le biais de la propriété **IsAnsiNullsOn** .</span><span class="sxs-lookup"><span data-stu-id="4bf16-156">The [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) function reports whether the option is on through the **IsAnsiNullsOn** property.</span></span>  
  
-   <span data-ttu-id="4bf16-157">La connexion sur laquelle l'index est créé, ainsi que toutes les connexions tentant d'exécuter des instructions INSERT, UPDATE ou DELETE appelées à modifier des valeurs de l'index, doivent comporter six options SET activées (ON) et une désactivée (OFF).</span><span class="sxs-lookup"><span data-stu-id="4bf16-157">The connection on which the index is created, and all connections trying INSERT, UPDATE, or DELETE statements that will change values in the index, must have six SET options set to ON and one option set to OFF.</span></span> <span data-ttu-id="4bf16-158">L'optimiseur ignore un index sur une colonne calculée dès qu'une instruction SELECT est exécutée par une connexion qui ne respecte pas ces paramètres d'options.</span><span class="sxs-lookup"><span data-stu-id="4bf16-158">The optimizer ignores an index on a computed column for any SELECT statement executed by a connection that does not have these same option settings.</span></span>  
  
    -   <span data-ttu-id="4bf16-159">L'option NUMERIC_ROUNDABORT doit être désactivée (OFF) et les options suivantes doivent être activées (ON) :</span><span class="sxs-lookup"><span data-stu-id="4bf16-159">The NUMERIC_ROUNDABORT option must be set to OFF, and the following options must be set to ON:</span></span>  
  
    -   <span data-ttu-id="4bf16-160">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="4bf16-160">ANSI_NULLS</span></span>  
  
    -   <span data-ttu-id="4bf16-161">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="4bf16-161">ANSI_PADDING</span></span>  
  
    -   <span data-ttu-id="4bf16-162">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="4bf16-162">ANSI_WARNINGS</span></span>  
  
    -   <span data-ttu-id="4bf16-163">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="4bf16-163">ARITHABORT</span></span>  
  
    -   <span data-ttu-id="4bf16-164">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="4bf16-164">CONCAT_NULL_YIELDS_NULL</span></span>  
  
    -   <span data-ttu-id="4bf16-165">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="4bf16-165">QUOTED_IDENTIFIER</span></span>  
  
     <span data-ttu-id="4bf16-166">L'affectation de la valeur ON à ANSI_WARNINGS affecte de manière implicite la valeur ON à ARITHABORT, lorsque le niveau de compatibilité de la base de données est d'au moins 90.</span><span class="sxs-lookup"><span data-stu-id="4bf16-166">Setting ANSI_WARNINGS to ON implicitly sets ARITHABORT to ON when the database compatibility level is set to 90 or higher.</span></span>  
  
##  <a name="creating-indexes-on-persisted-computed-columns"></a><a name="BKMK_persisted"></a> <span data-ttu-id="4bf16-167">Création d’index sur des colonnes calculées persistantes</span><span class="sxs-lookup"><span data-stu-id="4bf16-167">Creating Indexes on Persisted Computed Columns</span></span>  
 <span data-ttu-id="4bf16-168">Vous pouvez créer un index sur une colonne calculée définie par une expression déterministe mais non précise si la colonne est marquée comme PERSISTED dans l'instruction CREATE TABLE ou ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="4bf16-168">You can create an index on a computed column that is defined with a deterministic, but imprecise, expression if the column is marked PERSISTED in the CREATE TABLE or ALTER TABLE statement.</span></span> <span data-ttu-id="4bf16-169">Cela signifie que [!INCLUDE[ssDE](../../../includes/ssde-md.md)] utilise ces valeurs persistantes lorsqu’il crée un index sur la colonne et lorsque l’index est référencé dans une requête.</span><span class="sxs-lookup"><span data-stu-id="4bf16-169">This means that the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] uses these persisted values when it creates an index on the column, and when the index is referenced in a query.</span></span> <span data-ttu-id="4bf16-170">Cette option vous permet de créer un index sur une colonne calculée lorsque est à la [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)] fois déterministe et précis.</span><span class="sxs-lookup"><span data-stu-id="4bf16-170">This option enables you to create an index on a computed column when [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)], is both deterministic and precise.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="4bf16-171">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="4bf16-171">Related Content</span></span>  
 [<span data-ttu-id="4bf16-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4bf16-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/columnproperty-transact-sql)  
  
  
