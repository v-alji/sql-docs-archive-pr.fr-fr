---
title: Identificateur de la base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- regular identifiers [SQL Server]
- identifiers [SQL Server]
- names [SQL Server], identifiers
- identifiers [SQL Server], about identifiers
- SQL Server identifiers
- Transact-SQL identifiers
- database objects [SQL Server], names
ms.assetid: 171291bb-f57f-4ad1-8cea-0b092d5d150c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 347b20c12a0ac5edd82172741377617aa0fe12c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604563"
---
# <a name="database-identifiers"></a><span data-ttu-id="cddea-102">Identificateur de la base de données</span><span class="sxs-lookup"><span data-stu-id="cddea-102">Database Identifiers</span></span>
  <span data-ttu-id="cddea-103">Le nom d'un objet d'une base de données est son identificateur.</span><span class="sxs-lookup"><span data-stu-id="cddea-103">The database object name is referred to as its identifier.</span></span> <span data-ttu-id="cddea-104">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], tous les éléments peuvent avoir un identificateur.</span><span class="sxs-lookup"><span data-stu-id="cddea-104">Everything in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can have an identifier.</span></span> <span data-ttu-id="cddea-105">Les serveurs, les bases de données et les objets de bases de données tels que les tables, les vues, les colonnes, les index, les déclencheurs, les procédures, les contraintes, les règles, etc. peuvent avoir des identificateurs.</span><span class="sxs-lookup"><span data-stu-id="cddea-105">Servers, databases, and database objects, such as tables, views, columns, indexes, triggers, procedures, constraints, and rules, can have identifiers.</span></span> <span data-ttu-id="cddea-106">La plupart des objets doivent avoir un identificateur ; les identificateurs sont facultatifs pour certains objets, tels que les contraintes.</span><span class="sxs-lookup"><span data-stu-id="cddea-106">Identifiers are required for most objects, but are optional for some objects such as constraints.</span></span>  
  
 <span data-ttu-id="cddea-107">L'identificateur d'un objet est créé lors de la définition de l'objet.</span><span class="sxs-lookup"><span data-stu-id="cddea-107">An object identifier is created when the object is defined.</span></span> <span data-ttu-id="cddea-108">L'identificateur est ensuite utilisé pour référencer l'objet.</span><span class="sxs-lookup"><span data-stu-id="cddea-108">The identifier is then used to reference the object.</span></span> <span data-ttu-id="cddea-109">L'instruction suivante, par exemple, crée une table avec l'identificateur `TableX`, et deux colonnes avec les identificateurs `KeyCol` et `Description`:</span><span class="sxs-lookup"><span data-stu-id="cddea-109">For example, the following statement creates a table with the identifier `TableX`, and two columns with the identifiers `KeyCol` and `Description`:</span></span>  
  
```  
CREATE TABLE TableX  
(KeyCol INT PRIMARY KEY, Description nvarchar(80))  
```  
  
 <span data-ttu-id="cddea-110">Cette table comporte également une contrainte sans nom.</span><span class="sxs-lookup"><span data-stu-id="cddea-110">This table also has an unnamed constraint.</span></span> <span data-ttu-id="cddea-111">La contrainte `PRIMARY KEY` n'a pas d'identificateur.</span><span class="sxs-lookup"><span data-stu-id="cddea-111">The `PRIMARY KEY` constraint has no identifier.</span></span>  
  
 <span data-ttu-id="cddea-112">Le classement d'un identificateur dépend du niveau auquel il est défini.</span><span class="sxs-lookup"><span data-stu-id="cddea-112">The collation of an identifier depends on the level at which it is defined.</span></span> <span data-ttu-id="cddea-113">Le classement par défaut de l'instance est assigné aux identificateurs d'objets qui sont au niveau de l'instance, tels que les noms de connexion et de base de données.</span><span class="sxs-lookup"><span data-stu-id="cddea-113">Identifiers of instance-level objects, such as logins and database names, are assigned the default collation of the instance.</span></span> <span data-ttu-id="cddea-114">Le classement par défaut de la base de données est affecté aux identificateurs d'objets qui appartiennent à la base de données, tels que les noms des tables, des vues et des colonnes.</span><span class="sxs-lookup"><span data-stu-id="cddea-114">Identifiers of objects in a database, such as tables, views, and column names, are assigned the default collation of the database.</span></span> <span data-ttu-id="cddea-115">Par exemple, deux tables dont les noms diffèrent uniquement au niveau de la casse peuvent être créées dans une base de données dont le classement respecte la casse, mais pas dans une base de données dont le classement ne respecte pas la casse.</span><span class="sxs-lookup"><span data-stu-id="cddea-115">For example, two tables with names that differ only in case can be created in a database that has case-sensitive collation, but cannot be created in a database that has case-insensitive collation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cddea-116">Les noms de variables, ou les paramètres des fonctions et des procédures stockées doivent toujours respecter les règles des identificateurs [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cddea-116">The names of variables, or the parameters of functions and stored procedures must comply with the rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
## <a name="classes-of-identifiers"></a><span data-ttu-id="cddea-117">Classes d'identificateurs</span><span class="sxs-lookup"><span data-stu-id="cddea-117">Classes of Identifiers</span></span>  
 <span data-ttu-id="cddea-118">Il existe deux classes d'identificateurs :</span><span class="sxs-lookup"><span data-stu-id="cddea-118">There are two classes of identifiers:</span></span>  
  
 <span data-ttu-id="cddea-119">Identificateurs réguliers</span><span class="sxs-lookup"><span data-stu-id="cddea-119">Regular identifiers</span></span>  
 <span data-ttu-id="cddea-120">Les identificateurs réguliers respectent les règles relatives au format des identificateurs.</span><span class="sxs-lookup"><span data-stu-id="cddea-120">Comply with the rules for the format of identifiers.</span></span> <span data-ttu-id="cddea-121">Ils ne sont pas délimités lorsqu'ils sont utilisés dans des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cddea-121">Regular identifiers are not delimited when they are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
SELECT *  
FROM TableX  
WHERE KeyCol = 124  
```  
  
 <span data-ttu-id="cddea-122">Identificateurs délimités</span><span class="sxs-lookup"><span data-stu-id="cddea-122">Delimited identifiers</span></span>  
 <span data-ttu-id="cddea-123">Les identificateurs délimités sont mis entre guillemets (") ou entre crochets ([ ]).</span><span class="sxs-lookup"><span data-stu-id="cddea-123">Are enclosed in double quotation marks (") or brackets ([ ]).</span></span> <span data-ttu-id="cddea-124">Les identificateurs qui respectent les règles relatives au format des identificateurs peuvent ne pas être délimités.</span><span class="sxs-lookup"><span data-stu-id="cddea-124">Identifiers that comply with the rules for the format of identifiers might not be delimited.</span></span> <span data-ttu-id="cddea-125">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="cddea-125">For example:</span></span>  
  
```  
SELECT *  
FROM [TableX]         --Delimiter is optional.  
WHERE [KeyCol] = 124  --Delimiter is optional.  
```  
  
 <span data-ttu-id="cddea-126">Ceux qui ne respectent pas ces règles ne peuvent être utilisés dans une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] qu'en étant délimités.</span><span class="sxs-lookup"><span data-stu-id="cddea-126">Identifiers that do not comply with all the rules for identifiers must be delimited in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="cddea-127">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="cddea-127">For example:</span></span>  
  
```  
SELECT *  
FROM [My Table]      --Identifier contains a space and uses a reserved keyword.  
WHERE [order] = 10   --Identifier is a reserved keyword.  
```  
  
 <span data-ttu-id="cddea-128">Qu'ils soient réguliers ou délimités, les identificateurs doivent contenir de 1 à 128 caractères.</span><span class="sxs-lookup"><span data-stu-id="cddea-128">Both regular and delimited identifiers must contain from 1 through 128 characters.</span></span> <span data-ttu-id="cddea-129">Dans le cas des tables temporaires locales, l'identificateur peut contenir jusqu'à 116 caractères.</span><span class="sxs-lookup"><span data-stu-id="cddea-129">For local temporary tables, the identifier can have a maximum of 116 characters.</span></span>  
  
## <a name="rules-for-regular-identifiers"></a><span data-ttu-id="cddea-130">Règles pour identificateurs réguliers</span><span class="sxs-lookup"><span data-stu-id="cddea-130">Rules for Regular Identifiers</span></span>  
 <span data-ttu-id="cddea-131">Les noms de variables, de fonctions et de procédures stockées doivent toujours respecter les règles suivantes portant sur les identificateurs [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cddea-131">The names of variables, functions, and stored procedures must comply with the following rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
1.  <span data-ttu-id="cddea-132">Le premier caractère doit être l'un des suivants :</span><span class="sxs-lookup"><span data-stu-id="cddea-132">The first character must be one of the following:</span></span>  
  
    -   <span data-ttu-id="cddea-133">Une des lettres définies par Unicode Standard 3,2.</span><span class="sxs-lookup"><span data-stu-id="cddea-133">A letter as defined by the Unicode Standard 3.2.</span></span> <span data-ttu-id="cddea-134">Elles incluent les caractères latins de a à z et de A à Z ainsi que des caractères alphabétiques d'autres langues.</span><span class="sxs-lookup"><span data-stu-id="cddea-134">The Unicode definition of letters includes Latin characters from a through z, from A through Z, and also letter characters from other languages.</span></span>  
  
    -   <span data-ttu-id="cddea-135">Les symboles trait de soulignement (_), arobase (@) ou dièse (#).</span><span class="sxs-lookup"><span data-stu-id="cddea-135">The underscore (_), at sign (@), or number sign (#).</span></span>  
  
         <span data-ttu-id="cddea-136">Certains symboles au début d'un identificateur ont une signification particulière dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cddea-136">Certain symbols at the beginning of an identifier have special meaning in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cddea-137">Un identificateur régulier qui commence par le signe arobase (@) dénote toujours une variable ou un paramètre local et ne peut pas être utilisé comme le nom d'un autre type d'objet.</span><span class="sxs-lookup"><span data-stu-id="cddea-137">A regular identifier that starts with the at sign always denotes a local variable or parameter and cannot be used as the name of any other type of object.</span></span> <span data-ttu-id="cddea-138">Un identificateur commençant par un symbole numéro indique un objet temporaire (table ou procédure).</span><span class="sxs-lookup"><span data-stu-id="cddea-138">An identifier that starts with a number sign denotes a temporary table or procedure.</span></span> <span data-ttu-id="cddea-139">Un identificateur commençant par le double signe # (##) indique un objet temporaire global.</span><span class="sxs-lookup"><span data-stu-id="cddea-139">An identifier that starts with double number signs (##) denotes a global temporary object.</span></span> <span data-ttu-id="cddea-140">Bien que les symboles dièse (#) et double dièse (##) puissent être utilisés pour commencer les noms d'autres types d'objets, nous ne recommandons pas cette pratique.</span><span class="sxs-lookup"><span data-stu-id="cddea-140">Although the number sign or double number sign characters can be used to begin the names of other types of objects, we do not recommend this practice.</span></span>  
  
         <span data-ttu-id="cddea-141">Le nom de certaines fonctions [!INCLUDE[tsql](../../includes/tsql-md.md)] commence par un double arobas (@@).</span><span class="sxs-lookup"><span data-stu-id="cddea-141">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] functions have names that start with double at signs (@@).</span></span> <span data-ttu-id="cddea-142">Pour éviter toute confusion avec ces fonctions, n’utilisez pas de noms commençant par @@.</span><span class="sxs-lookup"><span data-stu-id="cddea-142">To avoid confusion with these functions, you should not use names that start with @@.</span></span>  
  
2.  <span data-ttu-id="cddea-143">Les caractères suivants peuvent inclure les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="cddea-143">Subsequent characters can include the following:</span></span>  
  
    -   <span data-ttu-id="cddea-144">Des lettres définies dans Unicode Standard 3,2.</span><span class="sxs-lookup"><span data-stu-id="cddea-144">Letters as defined in the Unicode Standard 3.2.</span></span>  
  
    -   <span data-ttu-id="cddea-145">Des nombres décimaux de Basic Latin ou d'autres scripts nationaux.</span><span class="sxs-lookup"><span data-stu-id="cddea-145">Decimal numbers from either Basic Latin or other national scripts.</span></span>  
  
    -   <span data-ttu-id="cddea-146">L'arobase, le symbole dollar ($), le symbole dièse ou le trait de soulignement.</span><span class="sxs-lookup"><span data-stu-id="cddea-146">The at sign, dollar sign ($), number sign, or underscore.</span></span>  
  
3.  <span data-ttu-id="cddea-147">L'identificateur ne doit pas être un mot réservé [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cddea-147">The identifier must not be a [!INCLUDE[tsql](../../includes/tsql-md.md)] reserved word.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cddea-148">conserve les majuscules et les minuscules des mots réservés.</span><span class="sxs-lookup"><span data-stu-id="cddea-148">reserves both the uppercase and lowercase versions of reserved words.</span></span> <span data-ttu-id="cddea-149">Un identificateur qui ne respecte pas toutes ces règles doit toujours être délimité par des crochets ou des guillemets doubles lors de son utilisation dans une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cddea-149">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span> <span data-ttu-id="cddea-150">Les mots réservés dépendent du niveau de compatibilité de la base de données.</span><span class="sxs-lookup"><span data-stu-id="cddea-150">The words that are reserved depend on the database compatibility level.</span></span> <span data-ttu-id="cddea-151">Vous pouvez définir ce niveau avec l’instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) .</span><span class="sxs-lookup"><span data-stu-id="cddea-151">This level can be set by using the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) statement.</span></span>  
  
4.  <span data-ttu-id="cddea-152">Les espaces incorporés ou les caractères spéciaux ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="cddea-152">Embedded spaces or special characters are not allowed.</span></span>  
  
5.  <span data-ttu-id="cddea-153">L'utilisation de caractères supplémentaires n'est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="cddea-153">Supplementary characters are not allowed.</span></span>  
  
 <span data-ttu-id="cddea-154">Un identificateur qui ne respecte pas toutes ces règles doit toujours être délimité par des crochets ou des guillemets doubles lors de son utilisation dans une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cddea-154">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cddea-155">Certaines règles relatives au format des identificateurs réguliers dépendent du niveau de compatibilité de la base de données.</span><span class="sxs-lookup"><span data-stu-id="cddea-155">Some rules for the format of regular identifiers depend on the database compatibility level.</span></span> <span data-ttu-id="cddea-156">Vous pouvez définir ce niveau avec [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="cddea-156">This level can be set by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cddea-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cddea-157">See Also</span></span>  
 <span data-ttu-id="cddea-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="cddea-159">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-159">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="cddea-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span></span>  
 <span data-ttu-id="cddea-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="cddea-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span></span>  
 <span data-ttu-id="cddea-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="cddea-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="cddea-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 <span data-ttu-id="cddea-166">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-166">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="cddea-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="cddea-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="cddea-169">[Mots clés réservés &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-169">[Reserved Keywords &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span></span>  
 <span data-ttu-id="cddea-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cddea-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="cddea-171">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cddea-171">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
