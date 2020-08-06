---
title: Instructions relatives à la logique de nouvelle tentative pour les transactions sur les tables optimisées en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2a35c37-4449-49ee-8bba-928028f1de66
author: stevestein
ms.author: sstein
ms.openlocfilehash: c9ffaccefb8d4e0a3044c4858a06029fd4350354
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701580"
---
# <a name="guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables"></a><span data-ttu-id="abf5e-102">Instructions pour la logique de nouvelle tentative des transactions sur des tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="abf5e-102">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>
  <span data-ttu-id="abf5e-103">Certaines conditions d'erreur peuvent se produire lors de l'accès des transactions aux tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="abf5e-103">There are error conditions that occur with transactions that access memory-optimized tables.</span></span>  
  
-   41302. <span data-ttu-id="abf5e-104">La transaction en cours a tenté de mettre à jour un enregistrement lui-même mis à jour depuis le démarrage de la transaction.</span><span class="sxs-lookup"><span data-stu-id="abf5e-104">The current transaction attempted to update a record that has been updated since the transaction started.</span></span>  
  
-   41305. <span data-ttu-id="abf5e-105">La transaction en cours n'a pas été validée en raison d'un échec de validation REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="abf5e-105">The current transaction failed to commit due to a repeatable read validation failure.</span></span>  
  
-   41325. <span data-ttu-id="abf5e-106">La transaction en cours n'a pas été validée en raison d'un échec de validation SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="abf5e-106">The current transaction failed to commit due to a serializable validation failure.</span></span>  
  
-   41301. <span data-ttu-id="abf5e-107">Une transaction précédente à la transaction actuelle a pris une dépendance ou a été abandonnée, et la transaction en cours ne peut plus être validée.</span><span class="sxs-lookup"><span data-stu-id="abf5e-107">A previous transaction that the current transaction took a dependency on has aborted, and the current transaction can no longer commit.</span></span>  
  
 <span data-ttu-id="abf5e-108">Ces erreurs sont souvent dues à une interférence entre des transactions exécutées simultanément.</span><span class="sxs-lookup"><span data-stu-id="abf5e-108">A common cause of these errors is interference between concurrently executing transaction.</span></span> <span data-ttu-id="abf5e-109">L'action corrective habituelle consiste à réessayer la transaction.</span><span class="sxs-lookup"><span data-stu-id="abf5e-109">The common corrective action is to retry the transaction.</span></span>  
  
 <span data-ttu-id="abf5e-110">Pour plus d’informations sur ces conditions d’erreur, consultez la section relative à la détection de conflit, à la validation et aux vérifications de dépendance de validation dans les [transactions dans les tables optimisées en mémoire](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="abf5e-110">For more information about these error conditions, see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="abf5e-111">Les blocages (code d'erreur 1205) ne peuvent pas se produire pour les tables mémoire optimisées,</span><span class="sxs-lookup"><span data-stu-id="abf5e-111">Deadlocks (error code 1205) cannot occur for memory-optimized tables.</span></span> <span data-ttu-id="abf5e-112">car celles-ci n'utilisent pas de verrous.</span><span class="sxs-lookup"><span data-stu-id="abf5e-112">Locks are not used for memory-optimized tables.</span></span> <span data-ttu-id="abf5e-113">Toutefois, si l'application contient déjà une logique de nouvelle tentative pour les blocages, la logique existante peut être étendue pour inclure les nouveaux codes d'erreur.</span><span class="sxs-lookup"><span data-stu-id="abf5e-113">However, if the application already contains retry logic for deadlocks, the existing logic could be extended to include the new error codes.</span></span>  
  
## <a name="considerations-for-retrying"></a><span data-ttu-id="abf5e-114">Considérations relatives à la logique de nouvelle tentative</span><span class="sxs-lookup"><span data-stu-id="abf5e-114">Considerations for Retrying</span></span>  
 <span data-ttu-id="abf5e-115">Les applications rencontreront généralement des conflits entre les transactions et devront implémenter une logique de nouvelle tentative pour les résoudre.</span><span class="sxs-lookup"><span data-stu-id="abf5e-115">Applications will typically encounter conflicts between transactions and need to implement retry logic to resolve those conflicts.</span></span> <span data-ttu-id="abf5e-116">Le nombre des conflits rencontrés dépend de plusieurs facteurs :</span><span class="sxs-lookup"><span data-stu-id="abf5e-116">The number of conflicts encountered depends on a number of factors:</span></span>  
  
-   <span data-ttu-id="abf5e-117">Contention de lignes individuelles.</span><span class="sxs-lookup"><span data-stu-id="abf5e-117">Contention for individual rows.</span></span> <span data-ttu-id="abf5e-118">Plus le nombre de transactions tentant de mettre à jour la même ligne est élevé, plus le risque de conflits augmente.</span><span class="sxs-lookup"><span data-stu-id="abf5e-118">The potential for conflicts increases as the number of transactions attempting to update the same row increases.</span></span>  
  
-   <span data-ttu-id="abf5e-119">Nombre de lignes lues par les transactions REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="abf5e-119">Number of rows read by REPEATABLE READ transactions.</span></span> <span data-ttu-id="abf5e-120">Plus le nombre de lignes lues est important, plus il est probable que certaines de ces lignes soient mises à jour par des transactions simultanées.</span><span class="sxs-lookup"><span data-stu-id="abf5e-120">The more rows read, the greater the chance that some of these rows are updated by concurrent transactions.</span></span> <span data-ttu-id="abf5e-121">Cela génère des échecs de validation REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="abf5e-121">This causes repeatable read validation failures.</span></span>  
  
-   <span data-ttu-id="abf5e-122">Taille des plages d'analyse utilisées par les transactions SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="abf5e-122">Size of the scan ranges used by SERIALIZABLE transactions.</span></span> <span data-ttu-id="abf5e-123">Plus les plages d'analyse sont grandes, plus il est probable que des transactions simultanées génèrent des lignes fantômes, provoquant des échecs de validation SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="abf5e-123">The larger the scan ranges, the higher the chance that concurrent transactions will introduce phantom rows, causing serializable validation failures.</span></span>  
  
     <span data-ttu-id="abf5e-124">Une application peut difficilement éviter ces conflits, qui nécessitent une logique de nouvelle tentative.</span><span class="sxs-lookup"><span data-stu-id="abf5e-124">It is difficult for an application to avoid these conflicts, requiring retry logic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="abf5e-125">Les transactions en lecture-écriture qui accèdent aux tables mémoire optimisées requièrent une logique de nouvelle tentative.</span><span class="sxs-lookup"><span data-stu-id="abf5e-125">Read-write transactions that access memory-optimized tables require retry logic.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-natively-compiled-stored-procedures"></a><span data-ttu-id="abf5e-126">Considérations relatives aux transactions en lecture seule et aux procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="abf5e-126">Considerations for Read-Only Transactions and Natively Compiled Stored Procedures</span></span>  
 <span data-ttu-id="abf5e-127">Les transactions en lecture seule qui couvrent une seule exécution d'une procédure stockée compilée en mode natif ne nécessitent pas de validation pour les transactions REPEATABLE READ et SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="abf5e-127">Read-only transactions that span a single execution of a natively compiled stored procedure do not require validation for REPEATABLE READ and SERIALIZABLE transactions.</span></span> <span data-ttu-id="abf5e-128">Les conflits d'écriture ne peuvent pas être dus à une transaction qui est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="abf5e-128">Write conflicts cannot occur due to a transaction being read-only.</span></span>  
  
 <span data-ttu-id="abf5e-129">Toutefois, des échecs de dépendance peuvent encore se produire.</span><span class="sxs-lookup"><span data-stu-id="abf5e-129">However, dependency failures can still occur.</span></span> <span data-ttu-id="abf5e-130">Les échecs de dépendance sont plus rares que les erreurs résultant des conflits.</span><span class="sxs-lookup"><span data-stu-id="abf5e-130">Dependency failures are rarer than errors resulting from conflicts.</span></span> <span data-ttu-id="abf5e-131">Par conséquent, dans la plupart des cas, une logique de nouvelle tentative spécifique n'est pas requise pour les transactions en lecture seule qui couvrent des exécutions uniques des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="abf5e-131">Therefore, in many cases, specific retry logic is not required for read-only transactions that span single executions of natively compiled stored procedures.</span></span>  
  
### <a name="considerations-for-read-only-transactions-and-cross-container-transactions"></a><span data-ttu-id="abf5e-132">Considérations relatives aux transactions en lecture seule et aux transactions entre conteneurs</span><span class="sxs-lookup"><span data-stu-id="abf5e-132">Considerations for Read-Only Transactions and Cross-Container Transactions</span></span>  
 <span data-ttu-id="abf5e-133">Les transactions en lecture seule entre conteneurs, qui sont des transactions démarrées en dehors du contexte d'une procédure stockée compilée en mode natif, n'effectuent pas de validation si toutes les tables mémoire optimisées sont accessibles avec l'isolation SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="abf5e-133">Read-only cross-container transactions, which are transactions that are started outside the context of a natively compiled stored procedure, do not perform validation if the memory-optimized tables are all accessed under SNAPSHOT isolation.</span></span> <span data-ttu-id="abf5e-134">Toutefois, lorsque les tables mémoire optimisées sont accessibles avec l'isolation REPEATABLE READ ou SERIALIZABLE, la validation est exécutée au moment de la validation.</span><span class="sxs-lookup"><span data-stu-id="abf5e-134">However, when memory-optimized tables are accessed under REPEATABLE READ or SERIALIZABLE isolation, validation is performed at commit time.</span></span> <span data-ttu-id="abf5e-135">Dans ce cas, la logique de nouvelle tentative peut être nécessaire.</span><span class="sxs-lookup"><span data-stu-id="abf5e-135">In this case, retry logic may be required.</span></span>  
  
 <span data-ttu-id="abf5e-136">Pour plus d’informations, consultez la section sur les transactions entre conteneurs dans les [niveaux d’isolation des transactions](../../2014/database-engine/transaction-isolation-levels.md).</span><span class="sxs-lookup"><span data-stu-id="abf5e-136">For more information, see the section on Cross-Container Transactions in [Transaction Isolation Levels](../../2014/database-engine/transaction-isolation-levels.md).</span></span>  
  
## <a name="implementing-retry-logic"></a><span data-ttu-id="abf5e-137">Implémenter la logique de nouvelle tentative</span><span class="sxs-lookup"><span data-stu-id="abf5e-137">Implementing Retry Logic</span></span>  
 <span data-ttu-id="abf5e-138">Comme avec toutes les transactions qui ont accès aux tables mémoire optimisées, vous devez prendre en compte la logique de nouvelle tentative pour gérer les problèmes potentiels, tels que des conflits d'écriture (code d'erreur 41302) ou les problèmes de dépendance (code d'erreur 41301).</span><span class="sxs-lookup"><span data-stu-id="abf5e-138">As with all transactions that access memory-optimized tables, you need to consider retry logic to handle potential failures, such as write conflicts (error code 41302) or dependency failures (error code 41301).</span></span> <span data-ttu-id="abf5e-139">Dans la plupart des applications le taux d'échec est bas, mais il est encore nécessaire de gérer les erreurs en effectuant une nouvelle tentative de transaction.</span><span class="sxs-lookup"><span data-stu-id="abf5e-139">In most applications the failure rate will be low, but it is still necessary to handle failures by retrying the transaction.</span></span> <span data-ttu-id="abf5e-140">Les deux méthodes suggérées pour implémenter la logique de nouvelle tentative sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="abf5e-140">Two suggested ways of implementing retry logic are:</span></span>  
  
-   <span data-ttu-id="abf5e-141">Nouvelles tentatives côté client.</span><span class="sxs-lookup"><span data-stu-id="abf5e-141">Client-side retries.</span></span> <span data-ttu-id="abf5e-142">Les nouvelles tentatives côté client constituent la méthode privilégiée pour implémenter la logique de nouvelle tentative en général.</span><span class="sxs-lookup"><span data-stu-id="abf5e-142">Client-side retries is the preferred way to implement retry logic in the general case.</span></span> <span data-ttu-id="abf5e-143">L'application cliente décèle l'erreur retournée par la transaction, et effectue une nouvelle tentative de transaction.</span><span class="sxs-lookup"><span data-stu-id="abf5e-143">The client application catches the error thrown by the transaction, and retries the transaction.</span></span> <span data-ttu-id="abf5e-144">Si une application cliente existante possède une logique de nouvelle tentative pour gérer les blocages, vous pouvez étendre l'application de façon à gérer les codes d'erreur.</span><span class="sxs-lookup"><span data-stu-id="abf5e-144">If an existing client application has retry logic to handle deadlocks, you can extend the application to handle the new error codes.</span></span>  
  
-   <span data-ttu-id="abf5e-145">Utilisation d'une procédure stockée de wrapper.</span><span class="sxs-lookup"><span data-stu-id="abf5e-145">Using a wrapper stored procedure.</span></span> <span data-ttu-id="abf5e-146">Le client appelle une procédure stockée en [!INCLUDE[tsql](../includes/tsql-md.md)] interprété qui appelle la procédure stockée compilée en mode natif ou exécute la transaction.</span><span class="sxs-lookup"><span data-stu-id="abf5e-146">The client calls an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that calls the natively compiled stored procedure or executes the transaction.</span></span> <span data-ttu-id="abf5e-147">La procédure de wrapper utilise ensuite la logique try/catch pour déceler l'erreur et effectuer une nouvelle tentative d'appel de procédure si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="abf5e-147">The wrapper procedure then uses try/catch logic to catch the error and retry the procedure call if needed.</span></span> <span data-ttu-id="abf5e-148">Il est possible que le résultat soit retourné au client avant l'échec, et le client ne peut pas l'ignorer.</span><span class="sxs-lookup"><span data-stu-id="abf5e-148">It is possible that results are returned to the client before the failure, and the client would not know to discard them.</span></span> <span data-ttu-id="abf5e-149">Par conséquent, il est préférable d'utiliser cette méthode uniquement avec des procédures stockées compilées en mode natif qui ne retournent aucun jeu de résultats au client.</span><span class="sxs-lookup"><span data-stu-id="abf5e-149">Therefore, to be safe, it is best to use this method only with natively compiled stored procedures that do not return any result sets to the client.</span></span>  
  
 <span data-ttu-id="abf5e-150">La logique de nouvelle tentative peut être implémentée en [!INCLUDE[tsql](../includes/tsql-md.md)] ou dans le code de l'application dans la couche intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="abf5e-150">The retry logic can be implemented either in [!INCLUDE[tsql](../includes/tsql-md.md)] or in the application code in the mid-tier.</span></span>  
  
 <span data-ttu-id="abf5e-151">Voici deux raisons pour prendre en considération la logique de nouvelle tentative :</span><span class="sxs-lookup"><span data-stu-id="abf5e-151">Two possible reasons to consider the retry logic are:</span></span>  
  
-   <span data-ttu-id="abf5e-152">L'application cliente applique la logique de nouvelle tentative pour d'autres codes d'erreur, comme 1205, que vous pouvez étendre.</span><span class="sxs-lookup"><span data-stu-id="abf5e-152">The client application has retry logic for other error codes, such as 1205, which you can extend.</span></span>  
  
-   <span data-ttu-id="abf5e-153">Les conflits sont rares, mais il est important de réduire la latence de bout en bout à l'aide d'une exécution préparée.</span><span class="sxs-lookup"><span data-stu-id="abf5e-153">Conflicts are rare, and it is important to reduce end-to-end latency by using prepared execution.</span></span> <span data-ttu-id="abf5e-154">Pour plus d’informations sur l’exécution directe de procédures stockées compilées en mode natif, consultez [procédures stockées compilées en mode natif](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="abf5e-154">For more information about executing natively compiled stored procedures directly, see [Natively Compiled Stored Procedures](../relational-databases/in-memory-oltp/natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="abf5e-155">L'exemple suivant illustre la logique de nouvelle tentative dans une procédure stockée en [!INCLUDE[tsql](../includes/tsql-md.md)] interprété qui contient un appel à une procédure stockée compilée en mode natif ou à une transaction entre conteneurs.</span><span class="sxs-lookup"><span data-stu-id="abf5e-155">The following sample shows retry logic in an interpreted [!INCLUDE[tsql](../includes/tsql-md.md)] stored procedure that contains a call either to a natively compiled stored procedure or to a cross-container transaction.</span></span>  
  
```sql  
CREATE PROCEDURE usp_my_procedure @param1 type1, @param2 type2, ...  
AS  
BEGIN  
  -- number of retries - tune based on the workload  
  DECLARE @retry INT = 10  
  
  WHILE (@retry > 0)  
  BEGIN  
    BEGIN TRY  
  
      -- exec usp_my_native_proc @param1, @param2, ...  
  
      --       or  
  
      -- BEGIN TRANSACTION  
      --   ...  
      -- COMMIT TRANSACTION  
  
      SET @retry = 0  
    END TRY  
    BEGIN CATCH  
      SET @retry -= 1  
  
      -- the error number for deadlocks (1205) does not need to be included for   
      -- transactions that do not access disk-based tables  
      IF (@retry > 0 AND error_number() in (41302, 41305, 41325, 41301, 1205))  
      BEGIN  
        -- these error conditions are transaction dooming - rollback the transaction  
        -- this is not needed if the transaction spans a single native proc execution  
        --   as the native proc will simply rollback when an error is thrown   
        IF XACT_STATE() = -1  
          ROLLBACK TRANSACTION  
  
        -- use a delay if there is a high rate of write conflicts (41302)  
        --   length of delay should depend on the typical duration of conflicting transactions  
        -- WAITFOR DELAY '00:00:00.001'  
      END  
      ELSE  
      BEGIN  
        -- insert custom error handling for other error conditions here  
  
        -- throw if this is not a qualifying error condition  
        ;THROW  
      END  
    END CATCH  
  END  
END  
```  
  
## <a name="see-also"></a><span data-ttu-id="abf5e-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="abf5e-156">See Also</span></span>  
 <span data-ttu-id="abf5e-157">[Fonctionnement des transactions sur les tables optimisées en mémoire](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="abf5e-157">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="abf5e-158">[Transactions dans les tables optimisées en mémoire](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="abf5e-158">[Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="abf5e-159">Instructions pour les niveaux d'isolement des transactions sur les tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="abf5e-159">Guidelines for Transaction Isolation Levels with Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md)  
  
  
