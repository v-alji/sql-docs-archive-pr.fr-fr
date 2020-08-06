---
title: Recompiler une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- sp_recompile
- WITH RECOMPILE clause
- recompiling stored procedures
- stored procedures [SQL Server], recompiling
ms.assetid: b90deb27-0099-4fe7-ba60-726af78f7c18
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a9bc0e1d4baecb7f4c66b83b57081ed3131123d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615111"
---
# <a name="recompile-a-stored-procedure"></a><span data-ttu-id="5befd-102">Recompiler une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="5befd-102">Recompile a Stored Procedure</span></span>
  <span data-ttu-id="5befd-103">Cette rubrique explique comment recompiler une procédure stockée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5befd-103">This topic describes how to recompile a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5befd-104">Il existe trois façons d’effectuer cette opération : `WITH RECOMPILE` option dans la définition de la procédure ou lorsque la procédure est appelée, l' `RECOMPILE` indicateur de requête sur des instructions individuelles ou à l’aide de la `sp_recompile` procédure stockée système.</span><span class="sxs-lookup"><span data-stu-id="5befd-104">There are three ways to do this: `WITH RECOMPILE` option in the procedure definition or when the procedure is called, the `RECOMPILE` query hint on individual statements, or by using the `sp_recompile` system stored procedure.</span></span> <span data-ttu-id="5befd-105">Cette rubrique décrit l’utilisation de l’option WITH RECOMPILE lors de la création d’une définition de procédure et de l’exécution d’une procédure existante.</span><span class="sxs-lookup"><span data-stu-id="5befd-105">This topic describes using the WITH RECOMPILE option when creating a procedure definition and executing an existing procedure.</span></span> <span data-ttu-id="5befd-106">Elle décrit également l’utilisation de la procédure stockée système sp_recompile pour recompiler une procédure existante.</span><span class="sxs-lookup"><span data-stu-id="5befd-106">It also describes using the sp_recompile system stored procedure to recompile an existing procedure.</span></span>  
  
 <span data-ttu-id="5befd-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5befd-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5befd-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5befd-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5befd-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="5befd-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5befd-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5befd-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5befd-111">**Pour recompiler une procédure stockée à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="5befd-111">**To recompile a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="5befd-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5befd-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5befd-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5befd-113">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5befd-114">Recommandations</span><span class="sxs-lookup"><span data-stu-id="5befd-114">Recommendations</span></span>  
  
-   <span data-ttu-id="5befd-115">Quand une procédure est compilée pour la première fois ou recompilée, son plan de requête est optimisé pour l’état actuel de la base de données et de ses objets.</span><span class="sxs-lookup"><span data-stu-id="5befd-115">When a procedure is compiled for the first time or recompiled, the procedure's query plan is optimized for the current state of the database and its objects.</span></span> <span data-ttu-id="5befd-116">Si une base de données subit des modifications significatives au niveau de ses données ou de sa structure, la recompilation de la procédure a pour effet de mettre à jour et d’optimiser son plan de requête en fonction de ces modifications.</span><span class="sxs-lookup"><span data-stu-id="5befd-116">If a database undergoes significant changes to its data or structure, recompiling a procedure updates and optimizes the procedure's query plan for those changes.</span></span> <span data-ttu-id="5befd-117">Les performances de traitement de la procédure peuvent s’en trouver améliorées.</span><span class="sxs-lookup"><span data-stu-id="5befd-117">This can improve the procedure's processing performance.</span></span>  
  
-   <span data-ttu-id="5befd-118">Parfois, la recompilation de procédure doit être forcée, et parfois elle se produit automatiquement.</span><span class="sxs-lookup"><span data-stu-id="5befd-118">There are times when procedure recompilation must be forced and other times when it occurs automatically.</span></span> <span data-ttu-id="5befd-119">La recompilation automatique se produit chaque fois que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] redémarre.</span><span class="sxs-lookup"><span data-stu-id="5befd-119">Automatic recompiling occurs whenever [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is restarted.</span></span> <span data-ttu-id="5befd-120">Elle se produit également si une table sous-jacente référencée par la procédure a été modifiée au niveau de sa conception physique.</span><span class="sxs-lookup"><span data-stu-id="5befd-120">It also occurs if an underlying table referenced by the procedure has undergone physical design changes.</span></span>  
  
-   <span data-ttu-id="5befd-121">Une autre raison pour forcer la recompilation d'une procédure est de contrer le comportement de détection des paramètres de la compilation de la procédure.</span><span class="sxs-lookup"><span data-stu-id="5befd-121">Another reason to force a procedure to recompile is to counteract the "parameter sniffing" behavior of procedure compilation.</span></span> <span data-ttu-id="5befd-122">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exécute des procédures, les valeurs des paramètres utilisés par la procédure lors de sa compilation sont incluses dans le cadre de la génération du plan de requête.</span><span class="sxs-lookup"><span data-stu-id="5befd-122">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes procedures, any parameter values that are used by the procedure when it compiles are included as part of generating the query plan.</span></span> <span data-ttu-id="5befd-123">Si ces valeurs représentent les valeurs standard utilisées pour appeler ultérieurement la procédure, celle-ci bénéficie du plan de requête à chaque compilation et exécution.</span><span class="sxs-lookup"><span data-stu-id="5befd-123">If these values represent the typical ones with which the procedure is subsequently called, then the procedure benefits from the query plan every time that it compiles and executes.</span></span> <span data-ttu-id="5befd-124">Si les valeurs des paramètres de la procédure sont atypiques, l'application forcée d'une recompilation et un nouveau plan défini en fonction des valeurs des paramètres peuvent améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="5befd-124">If parameter values on the procedure are frequently atypical, forcing a recompile of the procedure and a new plan based on different parameter values can improve performance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5befd-125">permet la recompilation des procédures au niveau de l’instruction.</span><span class="sxs-lookup"><span data-stu-id="5befd-125">features statement-level recompilation of procedures.</span></span> <span data-ttu-id="5befd-126">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recompile des procédures, seule l'instruction ayant provoqué la recompilation est compilée, et non la procédure toute entière.</span><span class="sxs-lookup"><span data-stu-id="5befd-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recompiles stored procedures, only the statement that caused the recompilation is compiled, instead of the complete procedure.</span></span>  
  
-   <span data-ttu-id="5befd-127">Si certaines requêtes d'une procédure utilisent régulièrement des valeurs atypiques ou temporaires, les performances des procédures peuvent être améliorées en utilisant l'indicateur de requête RECOMPILE à l'intérieur de ces requêtes.</span><span class="sxs-lookup"><span data-stu-id="5befd-127">If certain queries in a procedure regularly use atypical or temporary values, procedure performance can be improved by using the RECOMPILE query hint inside those queries.</span></span> <span data-ttu-id="5befd-128">Étant donné que seules les requêtes utilisant l'indicateur de requête seront recompilées au lieu de la procédure complète, le comportement de recompilation de l'instruction de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]est reproduit.</span><span class="sxs-lookup"><span data-stu-id="5befd-128">Since only the queries using the query hint will be recompiled instead of the complete procedure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]'s statement-level recompilation behavior is mimicked.</span></span> <span data-ttu-id="5befd-129">Cependant, en plus d'utiliser les valeurs des paramètres actuels de la procédure, l'indicateur de requête RECOMPILE utilise également les valeurs des variables locales à l'intérieur de la procédure stockée lorsque vous compilez l'instruction.</span><span class="sxs-lookup"><span data-stu-id="5befd-129">But in addition to using the procedure's current parameter values, the RECOMPILE query hint also uses the values of any local variables inside the stored procedure when you compile the statement.</span></span> <span data-ttu-id="5befd-130">Pour plus d’informations, consultez [Indicateur de requête (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="5befd-130">For more information, see [Query Hint (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5befd-131">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5befd-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5befd-132">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5befd-132">Permissions</span></span>  
 <span data-ttu-id="5befd-133">`WITH RECOMPILE`Option</span><span class="sxs-lookup"><span data-stu-id="5befd-133">`WITH RECOMPILE` Option</span></span>  
 <span data-ttu-id="5befd-134">Si cette option est utilisée lorsque la définition de la procédure est créée, elle nécessite l'autorisation CREATE PROCEDURE dans la base de données et l'autorisation ALTER sur le schéma dans lequel la procédure est créée.</span><span class="sxs-lookup"><span data-stu-id="5befd-134">If this option is used when the procedure definition is created, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="5befd-135">Si cette option est utilisée dans une instruction EXECUTE, elle nécessite des autorisations EXECUTE sur la procédure.</span><span class="sxs-lookup"><span data-stu-id="5befd-135">If this option is used in an EXECUTE statement, it requires EXECUTE permissions on the procedure.</span></span> <span data-ttu-id="5befd-136">Aucune autorisation n'est requise sur l'instruction EXECUTE elle-même, mais une autorisation est requise sur la procédure référencée dans l'instruction EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="5befd-136">Permissions are not required on the EXECUTE statement itself but execute permissions are required on the procedure referenced in the EXECUTE statement.</span></span> <span data-ttu-id="5befd-137">Pour plus d’informations, consultez [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5befd-137">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
 <span data-ttu-id="5befd-138">`RECOMPILE`Indicateur de requête</span><span class="sxs-lookup"><span data-stu-id="5befd-138">`RECOMPILE` Query Hint</span></span>  
 <span data-ttu-id="5befd-139">Cette fonctionnalité est utilisée lorsque la procédure est créée et l’indicateur est inclus dans les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] de la procédure.</span><span class="sxs-lookup"><span data-stu-id="5befd-139">This feature is used when the procedure is created and the hint is included in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure.</span></span> <span data-ttu-id="5befd-140">Par conséquent, elle nécessite l'autorisation CREATE PROCEDURE dans la base de données et l'autorisation ALTER sur le schéma dans lequel la procédure est créée.</span><span class="sxs-lookup"><span data-stu-id="5befd-140">Therefore, it requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
 <span data-ttu-id="5befd-141">`sp_recompile`Procédure stockée système</span><span class="sxs-lookup"><span data-stu-id="5befd-141">`sp_recompile` System Stored Procedure</span></span>  
 <span data-ttu-id="5befd-142">Nécessite l'autorisation ALTER pour la procédure spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5befd-142">Requires ALTER permission on the specified procedure.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5befd-143">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5befd-143">Using Transact-SQL</span></span>  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="5befd-144">Pour recompiler une procédure stockée à l'aide de l'option WITH RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="5befd-144">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="5befd-145">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5befd-145">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5befd-146">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5befd-146">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5befd-147">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5befd-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5befd-148">Cet exemple crée la définition de la procédure.</span><span class="sxs-lookup"><span data-stu-id="5befd-148">This example creates the procedure definition.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'dbo.uspProductByVendor', 'P' ) IS NOT NULL   
    DROP PROCEDURE dbo.uspProductByVendor;  
GO  
CREATE PROCEDURE dbo.uspProductByVendor @Name varchar(30) = '%'  
WITH RECOMPILE  
AS  
    SET NOCOUNT ON;  
    SELECT v.Name AS 'Vendor name', p.Name AS 'Product name'  
    FROM Purchasing.Vendor AS v   
    JOIN Purchasing.ProductVendor AS pv   
      ON v.BusinessEntityID = pv.BusinessEntityID   
    JOIN Production.Product AS p   
      ON pv.ProductID = p.ProductID  
    WHERE v.Name LIKE @Name;  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-the-with-recompile-option"></a><span data-ttu-id="5befd-149">Pour recompiler une procédure stockée à l'aide de l'option WITH RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="5befd-149">To recompile a stored procedure by using the WITH RECOMPILE option</span></span>  
  
1.  <span data-ttu-id="5befd-150">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5befd-150">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5befd-151">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5befd-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5befd-152">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5befd-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5befd-153">Cet exemple crée une procédure simple qui retourne tous les employés (prénom et nom), leur poste et le nom de leur service à partir d'une vue.</span><span class="sxs-lookup"><span data-stu-id="5befd-153">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="5befd-154">Puis, copiez et collez le second exemple de code dans la fenêtre de requête et cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5befd-154">And then copy and paste the second code example into the query window and click **Execute**.</span></span> <span data-ttu-id="5befd-155">La procédure est alors exécutée et son plan de requête recompilé.</span><span class="sxs-lookup"><span data-stu-id="5befd-155">This executes the procedure and recompiles the procedure's query plan.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXECUTE HumanResources.uspGetAllEmployees WITH RECOMPILE;  
GO  
  
```  
  
#### <a name="to-recompile-a-stored-procedure-by-using-sp_recompile"></a><span data-ttu-id="5befd-156">Pour recompiler une procédure stockée à l'aide de sp_recompile</span><span class="sxs-lookup"><span data-stu-id="5befd-156">To recompile a stored procedure by using sp_recompile</span></span>  
  
1.  <span data-ttu-id="5befd-157">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5befd-157">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5befd-158">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5befd-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5befd-159">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5befd-159">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5befd-160">Cet exemple crée une procédure simple qui retourne tous les employés (prénom et nom), leur poste et le nom de leur service à partir d'une vue.</span><span class="sxs-lookup"><span data-stu-id="5befd-160">This example creates a simple procedure that returns all employees (first and last names supplied), their job titles, and their department names from a view.</span></span>  
  
     <span data-ttu-id="5befd-161">Ensuite, copiez et collez l'exemple suivant dans la fenêtre de requête et cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5befd-161">Then, copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5befd-162">Cela n'exécute pas la procédure mais la marque pour la recompilation de sorte que son plan de requête sera mis à jour à la prochaine exécution.</span><span class="sxs-lookup"><span data-stu-id="5befd-162">This does not execute the procedure but it does mark the procedure to be recompiled so that its query plan is updated the next time that the procedure is executed.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_recompile N'HumanResources.uspGetAllEmployees';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5befd-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5befd-163">See Also</span></span>  
 <span data-ttu-id="5befd-164">[Créer une procédure stockée](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5befd-164">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="5befd-165">[Modifier une procédure stockée](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5befd-165">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="5befd-166">[Renommer une procédure stockée](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5befd-166">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="5befd-167">[Afficher la définition d'une procédure stockée](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5befd-167">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="5befd-168">[Afficher les dépendances d’une procédure stockée](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5befd-168">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="5befd-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5befd-169">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
