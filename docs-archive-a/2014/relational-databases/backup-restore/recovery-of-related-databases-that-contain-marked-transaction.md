---
title: Récupération de bases de données associées contenant une transaction marquée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction logs [SQL Server], marks
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- transactions [SQL Server], recovering to a mark
- database recovery [SQL Server]
- marked transactions [SQL Server], restoring
- database restores [SQL Server], point in time
ms.assetid: 77a0d9c0-978a-4891-8b0d-a4256c81c3f8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b968322f92c7a135adb5fd0733b5774e7562bc39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705200"
---
# <a name="recovery-of-related--databases-that-contain-marked-transaction"></a><span data-ttu-id="6cac9-102">Récupération de bases de données associées contenant une transaction marquée</span><span class="sxs-lookup"><span data-stu-id="6cac9-102">Recovery of Related  Databases That Contain Marked Transaction</span></span>
  <span data-ttu-id="6cac9-103">Cette rubrique s'applique uniquement aux bases de données qui contiennent des transactions marquées et qui utilisent le mode de récupération complète ou le mode de récupération utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="6cac9-103">This topic is relevant only for databases that contain marked transactions and that use the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="6cac9-104">Pour plus d’informations sur la configuration requise pour la restauration à un point de récupération spécifique, consultez [Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="6cac9-104">For information about the requirements for restoring to a specific recovery point, see [Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6cac9-105">prend en charge l'insertion de marques nommées dans le journal des transactions afin de permettre la récupération jusqu'à une marque particulière.</span><span class="sxs-lookup"><span data-stu-id="6cac9-105">supports inserting named marks into the transaction log to allow recovery to that specific mark.</span></span> <span data-ttu-id="6cac9-106">Les marques de journal sont transactionnelles et ne sont insérées que si leurs transactions associées sont validées.</span><span class="sxs-lookup"><span data-stu-id="6cac9-106">Log marks are transaction specific and are inserted only if their associated transaction commits.</span></span> <span data-ttu-id="6cac9-107">Par conséquent, des marques peuvent être liées à un travail spécifique, et vous pouvez récupérer jusqu'à un point incluant ou excluant ce travail.</span><span class="sxs-lookup"><span data-stu-id="6cac9-107">As a result, marks can be tied to specific work, and you can recover to a point that includes or excludes this work.</span></span>  
  
 <span data-ttu-id="6cac9-108">Avant d'insérer des marques nommées dans le journal des transactions, prenez en compte les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6cac9-108">Before you insert named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="6cac9-109">les marques de transaction occupant de l'espace dans le journal, utilisez-les seulement pour les transactions ayant un rôle significatif dans la stratégie de récupération de la base de données ;</span><span class="sxs-lookup"><span data-stu-id="6cac9-109">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="6cac9-110">Après la validation d'une transaction marquée, une ligne est insérée dans la table [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) de la base de données **msdb**.</span><span class="sxs-lookup"><span data-stu-id="6cac9-110">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="6cac9-111">si une transaction marquée s'étend à plusieurs bases de données sur le même serveur de bases de données ou sur différents serveurs, les marques doivent être enregistrées dans les journaux de toutes les bases de données concernées.</span><span class="sxs-lookup"><span data-stu-id="6cac9-111">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span> <span data-ttu-id="6cac9-112">Pour plus d’informations, consultez [Utiliser les transactions marquées pour récupérer des bases de données associées uniformément &#40;mode de récupération complète&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="6cac9-112">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cac9-113">Pour plus d’informations sur la façon de marquer les transactions, consultez [Utiliser les transactions marquées pour récupérer des bases de données associées uniformément &#40;mode de récupération complète&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="6cac9-113">For information about how to mark transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-inserting-named-marks-into-a-transaction-log"></a><span data-ttu-id="6cac9-114">Syntaxe Transact-SQL permettant d'insérer des marques nommées dans un journal des transactions</span><span class="sxs-lookup"><span data-stu-id="6cac9-114">Transact-SQL Syntax for Inserting Named Marks into a Transaction Log</span></span>  
 <span data-ttu-id="6cac9-115">Pour insérer des marques dans les journaux des transactions, utilisez l’instruction [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) et la clause WITH MARK [*description*].</span><span class="sxs-lookup"><span data-stu-id="6cac9-115">To insert marks into the transaction logs, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="6cac9-116">La marque a le même nom que la transaction.</span><span class="sxs-lookup"><span data-stu-id="6cac9-116">The mark is named the same as the transaction.</span></span> <span data-ttu-id="6cac9-117">La *description* facultative est une description textuelle de la marque, pas le nom de la marque.</span><span class="sxs-lookup"><span data-stu-id="6cac9-117">The optional *description* is a textual description of the mark, not the mark name.</span></span> <span data-ttu-id="6cac9-118">Par exemple, le nom de la transaction et de la marque créé dans l'instruction `BEGIN TRANSACTION` suivante est `Tx1`:</span><span class="sxs-lookup"><span data-stu-id="6cac9-118">For example, the name of both the transaction and the mark that is created in the following `BEGIN TRANSACTION` statement is `Tx1`:</span></span>  
  
```wmimof  
BEGIN TRANSACTION Tx1 WITH MARK 'not the mark name, just a description'    
```  
  
 <span data-ttu-id="6cac9-119">Le journal des transactions enregistre le nom de la marque (nom de la transaction), la description, la base de données, l'utilisateur, les informations de `datetime`, et le numéro séquentiel dans le journal (LSN, Log Sequence Number).</span><span class="sxs-lookup"><span data-stu-id="6cac9-119">The transaction log records the mark name (transaction name), description, database, user, `datetime` information, and the log sequence number (LSN).</span></span> <span data-ttu-id="6cac9-120">Les informations de `datetime` sont utilisées conjointement avec le nom de la marque pour identifier celle-ci de façon univoque.</span><span class="sxs-lookup"><span data-stu-id="6cac9-120">The `datetime` information is used with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="6cac9-121">Pour plus d’informations sur la façon d’insérer une marque dans une transaction qui s’étend sur plusieurs bases de données, consultez [Utiliser les transactions marquées pour récupérer des bases de données associées uniformément &#40;mode de récupération complète&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="6cac9-121">For information about how to insert a mark into a transaction that spans multiple databases, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
## <a name="transact-sql-syntax-for-recovering-to-a-mark"></a><span data-ttu-id="6cac9-122">Syntaxe Transact-SQL permettant de réaliser une récupération jusqu'à une marque</span><span class="sxs-lookup"><span data-stu-id="6cac9-122">Transact-SQL Syntax for Recovering to a Mark</span></span>  
 <span data-ttu-id="6cac9-123">Quand vous ciblez une transaction marquée à l’aide d’une instruction[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql), vous pouvez utiliser l’une des clauses suivantes pour vous arrêter à la marque ou juste avant celle-ci :</span><span class="sxs-lookup"><span data-stu-id="6cac9-123">When you target a marked transaction by using a[RESTORE LOG](/sql/t-sql/statements/restore-statements-transact-sql)statement, you can use one the following clauses to stop at or immediately before the mark:</span></span>  
  
-   <span data-ttu-id="6cac9-124">Utilisez la clause WITH STOPATMARK = **' *`<mark_name>`* '** pour spécifier que la transaction marquée est le point de récupération.</span><span class="sxs-lookup"><span data-stu-id="6cac9-124">Use the WITH STOPATMARK = **'*`<mark_name>`*'** clause to specify that the marked transaction is the recovery point.</span></span>  
  
     <span data-ttu-id="6cac9-125">L'option STOPATMARK effectue une restauration par progression jusqu'à la marque et inclut la transaction marquée dans cette restauration.</span><span class="sxs-lookup"><span data-stu-id="6cac9-125">STOPATMARK rolls forward to the mark and includes the marked transaction in the roll forward.</span></span>  
  
-   <span data-ttu-id="6cac9-126">Utilisez la clause with STOPBEFOREMARK = **' *`<mark_name>`* '** pour spécifier que l’enregistrement de journal situé juste avant la marque est le point de récupération.</span><span class="sxs-lookup"><span data-stu-id="6cac9-126">Use the WITH STOPBEFOREMARK = **'*`<mark_name>`*'** clause to specify that the log record that is immediately before the mark is the recovery point.</span></span>  
  
     <span data-ttu-id="6cac9-127">L'option STOPBEFOREMARK effectue une restauration par progression jusqu'à la marque et exclut la transaction marquée de cette restauration.</span><span class="sxs-lookup"><span data-stu-id="6cac9-127">STOPBEFOREMARK rolls forward to the mark and excludes marked the transaction from the roll forward.</span></span>  
  
 <span data-ttu-id="6cac9-128">Les options STOPATMARK et STOPBEFOREMARK prennent toutes les deux en charge une clause AFTER *datetime* facultative.</span><span class="sxs-lookup"><span data-stu-id="6cac9-128">The STOPATMARK and STOPBEFOREMARK options both support an optional AFTER *datetime* clause.</span></span> <span data-ttu-id="6cac9-129">Lorsqu'ils sont utilisés avec *datetime* , il n'est pas nécessaire que les noms de marque soient uniques.</span><span class="sxs-lookup"><span data-stu-id="6cac9-129">When *datetime* is used, mark names do not have to be unique.</span></span>  
  
 <span data-ttu-id="6cac9-130">Si la clause AFTER *datetime* est omise, la restauration par progression s'arrête à la première marque portant le nom spécifié.</span><span class="sxs-lookup"><span data-stu-id="6cac9-130">If AFTER *datetime* is omitted, roll forward stops at the first mark that has the specified name.</span></span> <span data-ttu-id="6cac9-131">Si une valeur est spécifiée pour AFTER *datetime* , la récupération par progression s'arrête à la première marque portant le nom spécifié, à *datetime*exactement ou après.</span><span class="sxs-lookup"><span data-stu-id="6cac9-131">If AFTER *datetime* is specified, roll forward stops at the first mark that has the specified name, exactly at or after *datetime*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cac9-132">Comme dans le cas de toute opération de restauration dans le temps, la récupération jusqu'à une marque n'est pas permise pendant les périodes où la base de données subit des opérations journalisées en bloc.</span><span class="sxs-lookup"><span data-stu-id="6cac9-132">As in all point-in-time restore operations, recovering to a mark is disallowed when the database is undergoing operations that are bulk-logged.</span></span>  
  
 <span data-ttu-id="6cac9-133">**Pour effectuer une restauration jusqu'à une transaction marquée**</span><span class="sxs-lookup"><span data-stu-id="6cac9-133">**To restore to a marked transaction**</span></span>  
  
 [<span data-ttu-id="6cac9-134">Restaurer une base de données jusqu’à une transaction marquée &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6cac9-134">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
 [<span data-ttu-id="6cac9-135">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6cac9-135">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
### <a name="preparing-the-log-backups"></a><span data-ttu-id="6cac9-136">Préparation des sauvegardes de journaux</span><span class="sxs-lookup"><span data-stu-id="6cac9-136">Preparing the Log Backups</span></span>  
 <span data-ttu-id="6cac9-137">Dans cet exemple, il serait parfaitement envisageable d'appliquer la stratégie de sauvegarde appropriée suivante aux bases de données :</span><span class="sxs-lookup"><span data-stu-id="6cac9-137">For this example, an appropriate backup strategy for these related databases would be the following:</span></span>  
  
1.  <span data-ttu-id="6cac9-138">Utilisation du mode de récupération complète pour les deux bases de données.</span><span class="sxs-lookup"><span data-stu-id="6cac9-138">Use the full recovery model for both databases.</span></span>  
  
2.  <span data-ttu-id="6cac9-139">Création d'une sauvegarde complète de chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="6cac9-139">Create a full backup of each database.</span></span>  
  
     <span data-ttu-id="6cac9-140">Les bases de données peuvent être sauvegardées l'une après l'autre ou de façon simultanée.</span><span class="sxs-lookup"><span data-stu-id="6cac9-140">The databases can be backed up sequentially or simultaneously.</span></span>  
  
3.  <span data-ttu-id="6cac9-141">Préalablement à la sauvegarde du journal des transactions, le marquage d'une transaction qui s'exécute dans toutes les bases de données.</span><span class="sxs-lookup"><span data-stu-id="6cac9-141">Before backing up the transaction log, mark a transaction that executes in all databases.</span></span> <span data-ttu-id="6cac9-142">Pour plus d’informations sur la façon de créer les transactions marquées, consultez [Utiliser les transactions marquées pour récupérer des bases de données associées uniformément &#40;mode de récupération complète&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span><span class="sxs-lookup"><span data-stu-id="6cac9-142">For information about how to create the marked transactions, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md).</span></span>  
  
4.  <span data-ttu-id="6cac9-143">Sauvegarde du journal des transactions sur chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="6cac9-143">Back up the transaction log on each database.</span></span>  
  
### <a name="recovering-the-database-to-a-marked-transaction"></a><span data-ttu-id="6cac9-144">Récupération de la base de données jusqu'à une transaction marquée</span><span class="sxs-lookup"><span data-stu-id="6cac9-144">Recovering the Database to a Marked Transaction</span></span>  
 <span data-ttu-id="6cac9-145">**Pour restaurer la sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="6cac9-145">**To restore the backup**</span></span>  
  
1.  <span data-ttu-id="6cac9-146">Créez des [sauvegardes de la fin du journal](tail-log-backups-sql-server.md) pour les bases de données non endommagées, si possible.</span><span class="sxs-lookup"><span data-stu-id="6cac9-146">Create [tail-log backups](tail-log-backups-sql-server.md) of the undamaged databases, if possible.</span></span>  
  
2.  <span data-ttu-id="6cac9-147">Restaurez la sauvegarde complète de base de données la plus récente pour chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="6cac9-147">Restore the most recent full database backup of each database.</span></span>  
  
3.  <span data-ttu-id="6cac9-148">Identifiez la transaction marquée la plus récente disponible dans toutes les sauvegardes des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="6cac9-148">Identify the most recent marked transaction that is available in all of the transaction log backups.</span></span> <span data-ttu-id="6cac9-149">Ces informations sont stockées dans la table **logmarkhistory** de la base de données **msdb** de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="6cac9-149">This information is stored in the **logmarkhistory** table in the **msdb** database on each server.</span></span>  
  
4.  <span data-ttu-id="6cac9-150">Identifiez les sauvegardes de journaux de toutes les bases de données associées contenant cette marque.</span><span class="sxs-lookup"><span data-stu-id="6cac9-150">Identify the log backups for all related databases that contain this mark.</span></span>  
  
5.  <span data-ttu-id="6cac9-151">Restaurez chaque sauvegarde de journal en vous arrêtant à la transaction marquée.</span><span class="sxs-lookup"><span data-stu-id="6cac9-151">Restore each log backup, stopping at the marked transaction.</span></span>  
  
6.  <span data-ttu-id="6cac9-152">Récupérez chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="6cac9-152">Recover each database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cac9-153"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6cac9-153">See Also</span></span>  
 <span data-ttu-id="6cac9-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cac9-154">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="6cac9-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6cac9-155">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="6cac9-156">[Appliquer les sauvegardes du journal des transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6cac9-156">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="6cac9-157">[Utiliser les transactions marquées pour récupérer des bases de données associées uniformément &#40;mode de récupération complète&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span><span class="sxs-lookup"><span data-stu-id="6cac9-157">[Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) </span></span>  
 <span data-ttu-id="6cac9-158">[Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6cac9-158">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="6cac9-159">[Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="6cac9-159">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="6cac9-160">Planifier et exécuter des séquences de restauration &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="6cac9-160">Plan and Perform Restore Sequences &#40;Full Recovery Model&#41;</span></span>](plan-and-perform-restore-sequences-full-recovery-model.md)  
  
  
