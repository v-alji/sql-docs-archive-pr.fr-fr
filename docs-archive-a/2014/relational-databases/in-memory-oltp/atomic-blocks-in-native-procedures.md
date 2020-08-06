---
title: Blocs atomiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 40e0e749-260c-4cfc-a848-444d30c09d85
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ca8f5b4d767ef0fe836cd260f8d12dd5b40c75d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601455"
---
# <a name="atomic-blocks"></a><span data-ttu-id="8d98e-102">Blocs Atomic</span><span class="sxs-lookup"><span data-stu-id="8d98e-102">Atomic Blocks</span></span>
  <span data-ttu-id="8d98e-103">`BEGIN ATOMIC` fait partie de la norme SQL ANSI.</span><span class="sxs-lookup"><span data-stu-id="8d98e-103">`BEGIN ATOMIC` is part of the ANSI SQL standard.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8d98e-104">prend en charge les blocs Atomic au niveau supérieur des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="8d98e-104">supports atomic blocks only at the top-level of natively compiled stored procedures.</span></span>  
  
-   <span data-ttu-id="8d98e-105">Chaque procédure stockée compilée en mode natif contient précisément un bloc d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d98e-105">Every natively compiled stored procedure contains exactly one block of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="8d98e-106">Il s'agit d'un bloc ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="8d98e-106">This is an ATOMIC block.</span></span>  
  
-   <span data-ttu-id="8d98e-107">Les procédures stockées [!INCLUDE[tsql](../../includes/tsql-md.md)] interprétées en mode non natif et les lots ad hoc ne prennent pas en charge les blocs Atomic.</span><span class="sxs-lookup"><span data-stu-id="8d98e-107">Non-native, interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and ad hoc batches do not support atomic blocks.</span></span>  
  
 <span data-ttu-id="8d98e-108">Les blocs Atomic sont exécutés (atomiquement) dans la transaction.</span><span class="sxs-lookup"><span data-stu-id="8d98e-108">Atomic blocks are executed (atomically) within the transaction.</span></span> <span data-ttu-id="8d98e-109">Toutes les instructions du bloc réussissent ou l'intégralité du bloc est restauré au point de sauvegarde créé au démarrage du bloc.</span><span class="sxs-lookup"><span data-stu-id="8d98e-109">Either all statements in the block succeed or the entire block will be rolled back to the savepoint that was created at the start of the block.</span></span> <span data-ttu-id="8d98e-110">En outre, les paramètres de session sont fixes pour le bloc Atomic.</span><span class="sxs-lookup"><span data-stu-id="8d98e-110">In addition, the session settings are fixed for the atomic block.</span></span> <span data-ttu-id="8d98e-111">Le fait d'exécuter le même bloc Atomic dans des sessions avec des paramètres différents génère le même comportement, indépendamment des paramètres de la session active.</span><span class="sxs-lookup"><span data-stu-id="8d98e-111">Executing the same atomic block in sessions with different settings will result in the same behavior, independent of the settings of the current session.</span></span>  
  
## <a name="transactions-and-error-handling"></a><span data-ttu-id="8d98e-112">Transactions et gestion des erreurs</span><span class="sxs-lookup"><span data-stu-id="8d98e-112">Transactions and Error Handling</span></span>  
 <span data-ttu-id="8d98e-113">Si une transaction existe déjà dans une session (parce qu'un lot a exécuté une instruction `BEGIN TRANSACTION` et la transaction reste active), le démarrage d'un bloc Atomic crée un point de sauvegarde dans la transaction.</span><span class="sxs-lookup"><span data-stu-id="8d98e-113">If a transaction already exists on a session (because a batch executed a `BEGIN TRANSACTION` statement and the transaction remains active), then starting an atomic block will create a savepoint in the transaction.</span></span> <span data-ttu-id="8d98e-114">Si le bloc se termine sans exception, le point de sauvegarde créé pour le bloc est validé, mais la transaction ne sera pas validée avant la validation de la transaction au niveau de la session.</span><span class="sxs-lookup"><span data-stu-id="8d98e-114">If the block exits without an exception, the savepoint that was created for the block commits, but the transaction will not commit until the transaction at the session level commits.</span></span> <span data-ttu-id="8d98e-115">Si le bloc lève une exception, les effets du bloc sont restaurés, mais la transaction au niveau de la session se poursuit, à moins que l'exception ne condamne la transaction.</span><span class="sxs-lookup"><span data-stu-id="8d98e-115">If the block throws an exception, the effects of the block are rolled back but the transaction at the session level will proceed, unless the exception is transaction-dooming.</span></span> <span data-ttu-id="8d98e-116">Par exemple, un conflit d'écriture condamne la transaction, mais pas une erreur de conversion de type.</span><span class="sxs-lookup"><span data-stu-id="8d98e-116">For example a write conflict is transaction-dooming, but not a type casting error.</span></span>  
  
 <span data-ttu-id="8d98e-117">S'il n'y a pas de transactions actives dans une session, `BEGIN ATOMIC` démarre une nouvelle transaction.</span><span class="sxs-lookup"><span data-stu-id="8d98e-117">If there is no active transaction on a session, `BEGIN ATOMIC` will start a new transaction.</span></span> <span data-ttu-id="8d98e-118">Si aucune exception n'est levée en dehors de l'étendue du bloc, la transaction est validée à la fin du bloc.</span><span class="sxs-lookup"><span data-stu-id="8d98e-118">If no exception is thrown outside the scope of the block, the transaction will be committed at the end of the block.</span></span> <span data-ttu-id="8d98e-119">Si le bloc lève une exception (autrement dit, l'exception n'est pas interceptée et n'est pas gérée dans le bloc), la transaction est restaurée.</span><span class="sxs-lookup"><span data-stu-id="8d98e-119">If the block throws an exception (that is, the exception is not caught and handled within the block), the transaction will be rolled back.</span></span> <span data-ttu-id="8d98e-120">Pour les transactions couvrant un bloc Atomic (une procédure stockée compilée en mode natif), vous n'avez pas besoin d'écrire d'instructions `BEGIN TRANSACTION` et `COMMIT` ou `ROLLBACK` explicites.</span><span class="sxs-lookup"><span data-stu-id="8d98e-120">For transactions that span a single atomic block (a single natively compiled stored procedure), you do not need to write explicit `BEGIN TRANSACTION` and `COMMIT` or `ROLLBACK` statements.</span></span>  
  
 <span data-ttu-id="8d98e-121">Les procédures stockées compilées en mode natif prennent en charge les constructions `TRY`, `CATCH` et `THROW` pour la gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="8d98e-121">Natively compiled stored procedures support the `TRY`, `CATCH`, and `THROW` constructs for error handling.</span></span> <span data-ttu-id="8d98e-122">`RAISERROR` n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8d98e-122">`RAISERROR` is not supported.</span></span>  
  
 <span data-ttu-id="8d98e-123">L'exemple suivant illustre le comportement de gestion des erreurs avec les blocs Atomic et les procédures stockées compilées en mode natif :</span><span class="sxs-lookup"><span data-stu-id="8d98e-123">The following example illustrates the error handling behavior with atomic blocks and natively compiled stored procedures:</span></span>  
  
```sql  
-- sample table  
CREATE TABLE dbo.t1 (  
  c1 int not null primary key nonclustered  
)  
WITH (MEMORY_OPTIMIZED=ON)  
GO  
  
-- sample proc that inserts 2 rows  
CREATE PROCEDURE dbo.usp_t1 @v1 bigint not null, @v2 bigint not null  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS  
BEGIN ATOMIC  
WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english', DELAYED_DURABILITY = ON)  
  
  INSERT dbo.t1 VALUES (@v1)  
  INSERT dbo.t1 VALUES (@v2)  
  
END  
GO  
  
-- insert two rows  
EXEC dbo.usp_t1 1, 2  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify the rows 1 and 2 were committed  
SELECT c1 FROM dbo.t1  
GO  
  
-- execute proc with arithmetic overflow  
EXEC dbo.usp_t1 3, 4444444444444  
GO  
-- expected error message:  
-- Msg 8115, Level 16, State 0, Procedure usp_t1  
-- Arithmetic overflow error converting bigint to data type int.  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 was not committed; usp_t1 has been rolled back  
SELECT c1 FROM dbo.t1  
GO  
  
-- start a new transaction  
BEGIN TRANSACTION  
  -- insert rows 3 and 4  
  EXEC dbo.usp_t1 3, 4  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify the rows 3 and 4 were inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
  -- catch the arithmetic overflow error  
  BEGIN TRY  
    EXEC dbo.usp_t1 5, 4444444444444  
  END TRY  
  BEGIN CATCH  
    PRINT N'Error occurred: ' + error_message()  
  END CATCH  
  
  -- verify there is still an active transaction  
  SELECT @@TRANCOUNT  
  
  -- verify rows 3 and 4 are still in the table, and row 5 has not been inserted  
  SELECT c1 FROM dbo.t1 WITH (SNAPSHOT)   
  ORDER BY c1  
  
COMMIT  
GO  
  
-- verify we have no active transaction  
SELECT @@TRANCOUNT  
GO  
  
-- verify rows 3 and 4 has been committed  
SELECT c1 FROM dbo.t1  
ORDER BY c1  
GO  
```  
  
 <span data-ttu-id="8d98e-124">Les messages d'erreur suivants propres aux tables optimisées en mémoire condamnent les transactions.</span><span class="sxs-lookup"><span data-stu-id="8d98e-124">The following error messages specific to memory-optimized tables are transaction dooming.</span></span> <span data-ttu-id="8d98e-125">S'ils apparaissent dans l'étendue d'un bloc Atomic, ils entraînent l'abandon de la transaction : 10772, 41301, 41302, 41305, 41325, 41332 et 41333.</span><span class="sxs-lookup"><span data-stu-id="8d98e-125">If they occur in the scope of an atomic block, they will cause the transaction to abort: 10772, 41301, 41302, 41305, 41325, 41332, and 41333.</span></span>  
  
## <a name="session-settings"></a><span data-ttu-id="8d98e-126">Paramètres de session</span><span class="sxs-lookup"><span data-stu-id="8d98e-126">Session Settings</span></span>  
 <span data-ttu-id="8d98e-127">Les paramètres de session dans les blocs Atomic sont fixes lorsque la procédure stockée est compilée.</span><span class="sxs-lookup"><span data-stu-id="8d98e-127">The session settings in atomic blocks are fixed when the stored procedure is compiled.</span></span> <span data-ttu-id="8d98e-128">Certains paramètres peuvent être spécifiés avec `BEGIN ATOMIC` tandis que les autres paramètres sont toujours fixes avec la même valeur.</span><span class="sxs-lookup"><span data-stu-id="8d98e-128">Some settings can be specified with `BEGIN ATOMIC` while other settings are always fixed to the same value.</span></span>  
  
 <span data-ttu-id="8d98e-129">Les options suivantes sont requises avec `BEGIN ATOMIC` :</span><span class="sxs-lookup"><span data-stu-id="8d98e-129">The following options are required with `BEGIN ATOMIC`:</span></span>  
  
|<span data-ttu-id="8d98e-130">Paramètre obligatoire</span><span class="sxs-lookup"><span data-stu-id="8d98e-130">Required Setting</span></span>|<span data-ttu-id="8d98e-131">Description</span><span class="sxs-lookup"><span data-stu-id="8d98e-131">Description</span></span>|  
|----------------------|-----------------|  
|`TRANSACTION ISOLATION LEVEL`|<span data-ttu-id="8d98e-132">Les valeurs prises en charge sont `SNAPSHOT`, `REPEATABLEREAD` et `SERIALIZABLE`.</span><span class="sxs-lookup"><span data-stu-id="8d98e-132">Supported values are `SNAPSHOT`, `REPEATABLEREAD`, and `SERIALIZABLE`.</span></span>|  
|`LANGUAGE`|<span data-ttu-id="8d98e-133">Détermine les formats de date et d'heure, et les messages système.</span><span class="sxs-lookup"><span data-stu-id="8d98e-133">Determines date and time formats and system messages.</span></span> <span data-ttu-id="8d98e-134">Tous les langages et les alias dans [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8d98e-134">All languages and aliases in [sys.syslanguages &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) are supported.</span></span>|  
  
 <span data-ttu-id="8d98e-135">Les paramètres suivants sont facultatifs :</span><span class="sxs-lookup"><span data-stu-id="8d98e-135">The following settings are optional:</span></span>  
  
|<span data-ttu-id="8d98e-136">Paramètre facultatif</span><span class="sxs-lookup"><span data-stu-id="8d98e-136">Optional Setting</span></span>|<span data-ttu-id="8d98e-137">Description</span><span class="sxs-lookup"><span data-stu-id="8d98e-137">Description</span></span>|  
|----------------------|-----------------|  
|`DATEFORMAT`|<span data-ttu-id="8d98e-138">Tous les formats de date [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8d98e-138">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date formats are supported.</span></span> <span data-ttu-id="8d98e-139">Lorsqu'il est spécifié, `DATEFORMAT` remplace le format de date par défaut associé à `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="8d98e-139">When specified, `DATEFORMAT` overrides the default date format associated with `LANGUAGE`.</span></span>|  
|`DATEFIRST`|<span data-ttu-id="8d98e-140">Lorsqu'il est spécifié, `DATEFIRST` remplace la valeur par défaut associée à `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="8d98e-140">When specified, `DATEFIRST` overrides the default associated with `LANGUAGE`.</span></span>|  
|`DELAYED_DURABILITY`|<span data-ttu-id="8d98e-141">Les valeurs prises en charge sont `OFF` et `ON`.</span><span class="sxs-lookup"><span data-stu-id="8d98e-141">Supported values are `OFF` and `ON`.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="8d98e-142">Les validations de transactions peuvent avoir une durabilité complète, la durabilité par défaut ou une durabilité retardée. Pour plus d’informations, consultez [Contrôler la durabilité d’une transaction](../logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="8d98e-142">transaction commits can be either fully durable, the default, or delayed durable.For more information, see [Control Transaction Durability](../logs/control-transaction-durability.md).</span></span>|  
  
 <span data-ttu-id="8d98e-143">Les options SET suivantes ont la même valeur système par défaut pour tous les blocs Atomic de toutes les procédures stockées compilées en mode natif :</span><span class="sxs-lookup"><span data-stu-id="8d98e-143">The following SET options have the same system default value for all atomic blocks in all natively compiled stored procedures:</span></span>  
  
|<span data-ttu-id="8d98e-144">Option SET</span><span class="sxs-lookup"><span data-stu-id="8d98e-144">Set Option</span></span>|<span data-ttu-id="8d98e-145">Valeur système par défaut pour les blocs Atomic</span><span class="sxs-lookup"><span data-stu-id="8d98e-145">System Default for Atomic Blocks</span></span>|  
|----------------|--------------------------------------|  
|<span data-ttu-id="8d98e-146">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="8d98e-146">ANSI_NULLS</span></span>|<span data-ttu-id="8d98e-147">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="8d98e-147">ON</span></span>|  
|<span data-ttu-id="8d98e-148">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="8d98e-148">ANSI_PADDING</span></span>|<span data-ttu-id="8d98e-149">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="8d98e-149">ON</span></span>|  
|<span data-ttu-id="8d98e-150">ANSI_WARNING</span><span class="sxs-lookup"><span data-stu-id="8d98e-150">ANSI_WARNING</span></span>|<span data-ttu-id="8d98e-151">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="8d98e-151">ON</span></span>|  
|<span data-ttu-id="8d98e-152">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="8d98e-152">ARITHABORT</span></span>|<span data-ttu-id="8d98e-153">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="8d98e-153">ON</span></span>|  
|<span data-ttu-id="8d98e-154">ARITHIGNORE</span><span class="sxs-lookup"><span data-stu-id="8d98e-154">ARITHIGNORE</span></span>|<span data-ttu-id="8d98e-155">OFF</span><span class="sxs-lookup"><span data-stu-id="8d98e-155">OFF</span></span>|  
|<span data-ttu-id="8d98e-156">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="8d98e-156">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="8d98e-157">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="8d98e-157">ON</span></span>|  
|<span data-ttu-id="8d98e-158">IDENTITY_INSERT</span><span class="sxs-lookup"><span data-stu-id="8d98e-158">IDENTITY_INSERT</span></span>|<span data-ttu-id="8d98e-159">OFF</span><span class="sxs-lookup"><span data-stu-id="8d98e-159">OFF</span></span>|  
|<span data-ttu-id="8d98e-160">NOCOUNT</span><span class="sxs-lookup"><span data-stu-id="8d98e-160">NOCOUNT</span></span>|<span data-ttu-id="8d98e-161">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="8d98e-161">ON</span></span>|  
|<span data-ttu-id="8d98e-162">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="8d98e-162">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="8d98e-163">OFF</span><span class="sxs-lookup"><span data-stu-id="8d98e-163">OFF</span></span>|  
|<span data-ttu-id="8d98e-164">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="8d98e-164">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="8d98e-165">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="8d98e-165">ON</span></span>|  
|<span data-ttu-id="8d98e-166">ROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="8d98e-166">ROWCOUNT</span></span>|<span data-ttu-id="8d98e-167">0</span><span class="sxs-lookup"><span data-stu-id="8d98e-167">0</span></span>|  
|<span data-ttu-id="8d98e-168">TEXTSIZE</span><span class="sxs-lookup"><span data-stu-id="8d98e-168">TEXTSIZE</span></span>|<span data-ttu-id="8d98e-169">0</span><span class="sxs-lookup"><span data-stu-id="8d98e-169">0</span></span>|  
|<span data-ttu-id="8d98e-170">XACT_ABORT</span><span class="sxs-lookup"><span data-stu-id="8d98e-170">XACT_ABORT</span></span>|<span data-ttu-id="8d98e-171">OFF</span><span class="sxs-lookup"><span data-stu-id="8d98e-171">OFF</span></span><br /><br /> <span data-ttu-id="8d98e-172">Les exceptions qui ne sont pas interceptées entraînent la restauration des blocs Atomic, mais pas l'abandon de la transaction, sauf si l'erreur condamne la transaction.</span><span class="sxs-lookup"><span data-stu-id="8d98e-172">Uncaught exceptions cause the atomic block to roll back, but not cause the transaction to abort unless the error is transaction dooming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d98e-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d98e-173">See Also</span></span>  
 [<span data-ttu-id="8d98e-174">Procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="8d98e-174">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
