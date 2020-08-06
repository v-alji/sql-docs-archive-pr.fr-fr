---
title: MSSQLSERVER_207 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 207 (Database Engine error)
ms.assetid: d1ab00c7-0331-437a-84fe-bae53b82feec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd6044c08ecd5a73f539bfbc1139d6257c2db9d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698261"
---
# <a name="mssqlserver_207"></a><span data-ttu-id="2f44e-102">MSSQLSERVER_207</span><span class="sxs-lookup"><span data-stu-id="2f44e-102">MSSQLSERVER_207</span></span>
    
## <a name="details"></a><span data-ttu-id="2f44e-103">Détails</span><span class="sxs-lookup"><span data-stu-id="2f44e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f44e-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="2f44e-104">Product Name</span></span>|<span data-ttu-id="2f44e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2f44e-105">SQL Server</span></span>|  
|<span data-ttu-id="2f44e-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="2f44e-106">Event ID</span></span>|<span data-ttu-id="2f44e-107">207</span><span class="sxs-lookup"><span data-stu-id="2f44e-107">207</span></span>|  
|<span data-ttu-id="2f44e-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="2f44e-108">Event Source</span></span>|<span data-ttu-id="2f44e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2f44e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2f44e-110">Composant</span><span class="sxs-lookup"><span data-stu-id="2f44e-110">Component</span></span>|<span data-ttu-id="2f44e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2f44e-111">SQLEngine</span></span>|  
|<span data-ttu-id="2f44e-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="2f44e-112">Symbolic Name</span></span>|<span data-ttu-id="2f44e-113">SQ_BADCOL</span><span class="sxs-lookup"><span data-stu-id="2f44e-113">SQ_BADCOL</span></span>|  
|<span data-ttu-id="2f44e-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="2f44e-114">Message Text</span></span>|<span data-ttu-id="2f44e-115">Nom de colonne non valide : '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="2f44e-115">Invalid column name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2f44e-116">Explication</span><span class="sxs-lookup"><span data-stu-id="2f44e-116">Explanation</span></span>  
 <span data-ttu-id="2f44e-117">Cette erreur de requête peut être causée par l'un des problèmes suivants.</span><span class="sxs-lookup"><span data-stu-id="2f44e-117">This query error can be caused by one of the following problems.</span></span>  
  
-   <span data-ttu-id="2f44e-118">Le nom de colonne est mal orthographié ou la colonne n'existe pas dans les tables spécifiées.</span><span class="sxs-lookup"><span data-stu-id="2f44e-118">The column name is misspelled or the column does not exist in any of the specified tables.</span></span>  
  
-   <span data-ttu-id="2f44e-119">Le classement de la base de données respecte la casse et la casse du nom de colonne spécifié dans la requête ne correspond pas à celle de la colonne définie dans la table.</span><span class="sxs-lookup"><span data-stu-id="2f44e-119">The collation of the database is case-sensitive and the case of the column name specified in the query does not match the case of the column defined in the table.</span></span> <span data-ttu-id="2f44e-120">Par exemple, quand une colonne est définie dans une table en tant que **LastName** et que la base de données utilise un classement qui respecte la casse, les requêtes qui font référence à cette colonne en tant que **Lastname** ou **lastname** retournent l’erreur 207, car le nom de colonne ne correspond pas.</span><span class="sxs-lookup"><span data-stu-id="2f44e-120">For example, when a column is defined in a table as **LastName** and the database uses a case-sensitive collation, queries that refer to the column as **Lastname** or **lastname** will cause error 207 to return because the column name does not match.</span></span>  
  
-   <span data-ttu-id="2f44e-121">Un alias de colonne, défini dans la clause SELECT, est référencé dans une autre clause telle que WHERE ou GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="2f44e-121">A column alias, defined in the SELECT clause, is referenced in another clause such as a WHERE or GROUP BY clause.</span></span> <span data-ttu-id="2f44e-122">Par exemple, la requête suivante définit l'alias de colonne `Year` dans la clause SELECT et y fait référence dans la clause GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="2f44e-122">For example, the following query defines the column alias `Year` in the SELECT clause and refers to it in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year, SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY Year;  
    ```  
  
     <span data-ttu-id="2f44e-123">En raison de l'ordre dans lequel les clauses de requête sont logiquement traitées, l'exemple retourne l'erreur 207.</span><span class="sxs-lookup"><span data-stu-id="2f44e-123">Due to the order in which query clauses are logically processed, the example returns error 207.</span></span> <span data-ttu-id="2f44e-124">L'ordre de traitement est le suivant :</span><span class="sxs-lookup"><span data-stu-id="2f44e-124">The processing order is as follows:</span></span>  
  
    1.  <span data-ttu-id="2f44e-125">FROM</span><span class="sxs-lookup"><span data-stu-id="2f44e-125">FROM</span></span>  
  
    2.  <span data-ttu-id="2f44e-126">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="2f44e-126">ON</span></span>  
  
    3.  <span data-ttu-id="2f44e-127">JOIN</span><span class="sxs-lookup"><span data-stu-id="2f44e-127">JOIN</span></span>  
  
    4.  <span data-ttu-id="2f44e-128">WHERE</span><span class="sxs-lookup"><span data-stu-id="2f44e-128">WHERE</span></span>  
  
    5.  <span data-ttu-id="2f44e-129">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="2f44e-129">GROUP BY</span></span>  
  
    6.  <span data-ttu-id="2f44e-130">WITH CUBE ou WITH ROLLUP</span><span class="sxs-lookup"><span data-stu-id="2f44e-130">WITH CUBE or WITH ROLLUP</span></span>  
  
    7.  <span data-ttu-id="2f44e-131">HAVING</span><span class="sxs-lookup"><span data-stu-id="2f44e-131">HAVING</span></span>  
  
    8.  <span data-ttu-id="2f44e-132">SELECT</span><span class="sxs-lookup"><span data-stu-id="2f44e-132">SELECT</span></span>  
  
    9. <span data-ttu-id="2f44e-133">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="2f44e-133">DISTINCT</span></span>  
  
    10. <span data-ttu-id="2f44e-134">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="2f44e-134">ORDER BY</span></span>  
  
    11. <span data-ttu-id="2f44e-135">Haut de la page</span><span class="sxs-lookup"><span data-stu-id="2f44e-135">TOP</span></span>  
  
     <span data-ttu-id="2f44e-136">Étant donné qu'un alias de colonne n'est pas défini tant que la clause SELECT n'est pas traitée, le nom d'alias est inconnu lorsque la clause GROUP BY est traitée.</span><span class="sxs-lookup"><span data-stu-id="2f44e-136">Because a column alias is not defined until the SELECT clause is processed, the alias name is unknown when the GROUP BY clause is processed.</span></span>  
  
-   <span data-ttu-id="2f44e-137">L’instruction MERGE génère cette erreur quand la clause *<merge_matched>* fait référence à des colonnes de la table source mais qu’aucune ligne n’est retournée par la table source dans la clause WHEN NOT MATCHED BY SOURCE.</span><span class="sxs-lookup"><span data-stu-id="2f44e-137">The MERGE statement raises this error when the *<merge_matched>* clause references columns in the source table but no rows are returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="2f44e-138">L'erreur se produit car les colonnes dans la table source sont inaccessibles lorsque aucune ligne n'est retournée à la requête.</span><span class="sxs-lookup"><span data-stu-id="2f44e-138">The error occurs because the columns in the source table cannot be accessed when no rows are returned to the query.</span></span> <span data-ttu-id="2f44e-139">Par exemple, la clause `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` peut faire en sorte que l'instruction échoue si `Col1` dans la table source est inaccessible.</span><span class="sxs-lookup"><span data-stu-id="2f44e-139">For example, the clause `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` may cause the statement to fail if `Col1` in the source table is inaccessible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2f44e-140">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="2f44e-140">User Action</span></span>  
 <span data-ttu-id="2f44e-141">Vérifiez les informations suivantes et corrigez l'instruction comme il convient.</span><span class="sxs-lookup"><span data-stu-id="2f44e-141">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="2f44e-142">Le nom de colonne existe dans la table et il est correctement orthographié.</span><span class="sxs-lookup"><span data-stu-id="2f44e-142">The column name exists in the table and is spelled correctly.</span></span> <span data-ttu-id="2f44e-143">L’exemple suivant interroge la vue de catalogue **sys.columns** pour retourner tous les noms de colonnes pour une table donnée.</span><span class="sxs-lookup"><span data-stu-id="2f44e-143">The following example queries the **sys.columns** catalog view to return all column names for a given table.</span></span>  
  
    ```  
    SELECT name FROM sys.columns WHERE object_id = OBJECT_ID('schema_name.table_name');  
    ```  
  
-   <span data-ttu-id="2f44e-144">Respect de la casse du classement de base de données.</span><span class="sxs-lookup"><span data-stu-id="2f44e-144">The case sensitivity of the database collation.</span></span> <span data-ttu-id="2f44e-145">L'instruction suivante retourne le classement de la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="2f44e-145">The following statement returns the collation of the specified database.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="2f44e-146">L’abréviation CS dans le nom du classement indique que celui-ci respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="2f44e-146">The abbreviation CS in the collation name indicates the collation is case-sensitive.</span></span> <span data-ttu-id="2f44e-147">Par exemple, Latin1_General_CS_AS indique un classement qui respecte la casse et les accents.</span><span class="sxs-lookup"><span data-stu-id="2f44e-147">For example, Latin1_General_CS_AS is a case-sensitive and accent-sensitive collation.</span></span> <span data-ttu-id="2f44e-148">Modifiez le nom de colonne de sorte qu'il corresponde au nom de colonne tel que défini dans la table.</span><span class="sxs-lookup"><span data-stu-id="2f44e-148">Modify the column name to match the case of the column name as it is defined in the table.</span></span>  
  
-   <span data-ttu-id="2f44e-149">Un alias de colonne est référencé de manière incorrecte.</span><span class="sxs-lookup"><span data-stu-id="2f44e-149">A column alias is referenced incorrectly.</span></span> <span data-ttu-id="2f44e-150">Modifiez l'instruction en répétant l'expression qui définit l'alias dans la clause appropriée ou en utilisant une table dérivée.</span><span class="sxs-lookup"><span data-stu-id="2f44e-150">Modify the statement by repeating the expression that defines the alias in the appropriate clause or by using a derived table.</span></span> <span data-ttu-id="2f44e-151">L'exemple suivant répète les expressions qui définissent l'alias `Year` dans la clause GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="2f44e-151">The following example repeats the expressions that define the `Year` alias in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year ,SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY DATEPART(yyyy,OrderDate);  
    ```  
  
     <span data-ttu-id="2f44e-152">L'exemple suivant utilise une table dérivée pour rendre le nom d'alias accessible à d'autres clauses dans la requête.</span><span class="sxs-lookup"><span data-stu-id="2f44e-152">The following example uses a derived table to make the alias name available to other clauses in the query.</span></span> <span data-ttu-id="2f44e-153">Notez que l'alias `Year` est défini dans la clause FROM, qui est traitée en premier, ce qui rend l'alias accessible pour une utilisation dans d'autres clauses de la requête.</span><span class="sxs-lookup"><span data-stu-id="2f44e-153">Notice that the alias `Year` is defined in the FROM clause, which is processed first, and so makes the alias available for use in other clauses in the query.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT d.Year, SUM(TotalDue) AS Total  
    FROM (SELECT DATEPART(yyyy,OrderDate) AS Year, TotalDue  
          FROM Sales.SalesOrderHeader)AS d  
    GROUP BY Year;  
    ```  
  
-   <span data-ttu-id="2f44e-154">La clause WHEN NOT MATCHED BY SOURCE de l'instruction MERGE fait référence à une valeur accessible.</span><span class="sxs-lookup"><span data-stu-id="2f44e-154">The WHEN NOT MATCHED BY SOURCE clause in the MERGE statement refers to a value that can be accessed.</span></span> <span data-ttu-id="2f44e-155">Modifiez l'instruction MERGE de façon qu'une ligne au moins soit retournée par la table source dans la clause WHEN NOT MATCHED BY SOURCE.</span><span class="sxs-lookup"><span data-stu-id="2f44e-155">Modify the MERGE statement so that at least one row is returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="2f44e-156">Par exemple, vous devrez peut-être ajouter ou modifier le critère de recherche spécifié pour la clause.</span><span class="sxs-lookup"><span data-stu-id="2f44e-156">For example, you might need to add or revise the search condition specified for the clause.</span></span> <span data-ttu-id="2f44e-157">Vous pouvez aussi modifier la clause de façon à spécifier une valeur qui ne fait pas référence à la table source.</span><span class="sxs-lookup"><span data-stu-id="2f44e-157">Alternatively, you can modify the clause to specify a value that does not reference the source table.</span></span> <span data-ttu-id="2f44e-158">Par exemple : `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span><span class="sxs-lookup"><span data-stu-id="2f44e-158">For example, `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f44e-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f44e-159">See Also</span></span>  
 <span data-ttu-id="2f44e-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f44e-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span></span>  
 <span data-ttu-id="2f44e-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f44e-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span></span>  
 <span data-ttu-id="2f44e-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f44e-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="2f44e-163">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f44e-163">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
