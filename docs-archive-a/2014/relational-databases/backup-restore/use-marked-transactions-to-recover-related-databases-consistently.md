---
title: Utiliser des transactions marquées pour récupérer des bases de données associées de manière cohérente (mode de récupération complète) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- transaction marks [SQL Server]
- marked transactions [SQL Server]
- database restores [SQL Server], inserting transaction marks for
- recovery [SQL Server], related databases
- restoring databases [SQL Server], related database recovery
- database restores [SQL Server], related databases
- marked transactions [SQL Server], creating
- BEGIN TRAN...WITH MARK statement
- two-phase commit
ms.assetid: 50a73574-1a69-448e-83dd-9abcc7cb7e1a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8dd368ad14f6e521fb8d504bdea774e3088c2522
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705191"
---
# <a name="use-marked-transactions-to-recover-related-databases-consistently-full-recovery-model"></a><span data-ttu-id="6a75a-102">Utiliser les transactions marquées pour récupérer des bases de données associées uniformément (mode de récupération complète)</span><span class="sxs-lookup"><span data-stu-id="6a75a-102">Use Marked Transactions to Recover Related Databases Consistently (Full Recovery Model)</span></span>
  <span data-ttu-id="6a75a-103">Cette rubrique s'applique uniquement aux bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] employant le mode de récupération complète ou le mode de récupération utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="6a75a-103">This topic is relevant only for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="6a75a-104">Quand vous effectuez des mises à jour associées vers plusieurs bases de données ( *bases de données associées*), vous pouvez utiliser des marques de transaction pour les récupérer à un point cohérent d’un point de vue logique.</span><span class="sxs-lookup"><span data-stu-id="6a75a-104">When you make related updates to two or more databases, *related databases*, you can use transaction marks to recover them to a logically consistent point.</span></span> <span data-ttu-id="6a75a-105">Cependant, cette récupération perd les transactions validées après la marque utilisée comme point de récupération.</span><span class="sxs-lookup"><span data-stu-id="6a75a-105">However, this recovery loses any transaction that is committed after the mark that was used as the recovery point.</span></span> <span data-ttu-id="6a75a-106">Le marquage des transactions est adapté uniquement au test des bases de données associées ou si vous êtes prêt à risquer la perte des transactions validées récemment.</span><span class="sxs-lookup"><span data-stu-id="6a75a-106">Marking transactions is suitable only when you are testing related databases or when you are willing to lose recently committed transactions.</span></span>  
  
 <span data-ttu-id="6a75a-107">Le marquage régulier des transactions associées dans chaque base de données associée établit une série de points de récupération dans les bases de données.</span><span class="sxs-lookup"><span data-stu-id="6a75a-107">Routinely marking related transactions in every related database establishes a series of common recovery points in the databases.</span></span> <span data-ttu-id="6a75a-108">Les marques de transaction sont enregistrées dans le journal des transactions et incluses dans les sauvegardes du journal.</span><span class="sxs-lookup"><span data-stu-id="6a75a-108">The transaction marks are recorded in the transaction log and included in log backups.</span></span> <span data-ttu-id="6a75a-109">En cas de sinistre, vous pouvez restaurer chaque base de données à la même marque de transaction pour les récupérer à un point cohérent.</span><span class="sxs-lookup"><span data-stu-id="6a75a-109">In the event of a disaster, you can restore each of the databases to the same transaction mark to recover them to a consistent point.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a75a-110">Les sauvegardes du journal sur les différentes bases de données peuvent être créées indépendamment et ne doivent pas être simultanées.</span><span class="sxs-lookup"><span data-stu-id="6a75a-110">Log backups on the different databases can be created independently of each other and do not have to be simultaneous.</span></span>  
  
 <span data-ttu-id="6a75a-111">La récupération des bases de données associées dans les scénarios suivants nécessite de disposer déjà de transactions marquées dans chaque base de données associée :</span><span class="sxs-lookup"><span data-stu-id="6a75a-111">Recovering related databases in the following scenarios requires that you have already marked transactions in every related database:</span></span>  
  
-   <span data-ttu-id="6a75a-112">Un ou plusieurs journaux des transactions sont détruits.</span><span class="sxs-lookup"><span data-stu-id="6a75a-112">One or more transaction logs are destroyed.</span></span> <span data-ttu-id="6a75a-113">Vous devez restaurer l’ensemble des bases de données dans un état cohérent au moment de votre dernière sauvegarde de journal.</span><span class="sxs-lookup"><span data-stu-id="6a75a-113">You have to restore the set of databases to a consistent state at the time of your last log backup.</span></span>  
  
-   <span data-ttu-id="6a75a-114">Vous devez restaurer la totalité des bases de données dans un état mutuellement cohérent correspondant à un moment antérieur dans le temps.</span><span class="sxs-lookup"><span data-stu-id="6a75a-114">You have to restore the entire set of databases to a mutually consistent state at some earlier point in time.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6a75a-115">Vous ne pouvez récupérer des bases de données associées qu'en fonction d'une transaction marquée, et non d'un moment précis.</span><span class="sxs-lookup"><span data-stu-id="6a75a-115">You can recover related databases only to a marked transaction, not to a specific point in time.</span></span>  
  
 <span data-ttu-id="6a75a-116">Pour des informations sur la création des marquages de transactions, consultez « Création des transactions marquées » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6a75a-116">For information about how to create marking transactions, see "Creating the Marked Transactions," later in this topic.</span></span>  
  
## <a name="typical-scenario-for-using-marked-transactions"></a><span data-ttu-id="6a75a-117">Scénario classique d'utilisation des transactions marquées</span><span class="sxs-lookup"><span data-stu-id="6a75a-117">Typical Scenario for Using Marked Transactions</span></span>  
 <span data-ttu-id="6a75a-118">Ce scénario inclut les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a75a-118">A typical scenario for using marked transactions includes the following steps:</span></span>  
  
1.  <span data-ttu-id="6a75a-119">la création d'une sauvegarde complète ou différentielle de chaque base de données associée ;</span><span class="sxs-lookup"><span data-stu-id="6a75a-119">Create a full or differential database backup of each of the related databases.</span></span>  
  
2.  <span data-ttu-id="6a75a-120">le marquage d'un verrou de transaction dans toutes les bases de données ;</span><span class="sxs-lookup"><span data-stu-id="6a75a-120">Mark a transaction block in all the databases.</span></span>  
  
3.  <span data-ttu-id="6a75a-121">la sauvegarde du journal des transactions pour toutes les bases de données ;</span><span class="sxs-lookup"><span data-stu-id="6a75a-121">Back up the transaction log for all the databases.</span></span>  
  
4.  <span data-ttu-id="6a75a-122">la restauration des sauvegardes de base de données à l'aide de WITH NORECOVERY ;</span><span class="sxs-lookup"><span data-stu-id="6a75a-122">Restore database backups WITH NORECOVERY.</span></span>  
  
5.  <span data-ttu-id="6a75a-123">la restauration des journaux à l'aide de WITH STOPATMARK.</span><span class="sxs-lookup"><span data-stu-id="6a75a-123">Restore logs WITH STOPATMARK.</span></span>  
  
## <a name="considerations-for-using-marked-transactions"></a><span data-ttu-id="6a75a-124">Considérations relatives à l'utilisation des transactions marquées</span><span class="sxs-lookup"><span data-stu-id="6a75a-124">Considerations for Using Marked Transactions</span></span>  
 <span data-ttu-id="6a75a-125">Avant d'insérer des marques nommées dans le journal des transactions, prenez en compte les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6a75a-125">Before inserting named marks into the transaction log, consider the following:</span></span>  
  
-   <span data-ttu-id="6a75a-126">les marques de transaction occupant de l'espace dans le journal, utilisez-les seulement pour les transactions ayant un rôle significatif dans la stratégie de récupération de la base de données ;</span><span class="sxs-lookup"><span data-stu-id="6a75a-126">Because transaction marks consume log space, use them only for transactions that play a significant role in the database recovery strategy.</span></span>  
  
-   <span data-ttu-id="6a75a-127">Après la validation d'une transaction marquée, une ligne est insérée dans la table [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) de la base de données **msdb**.</span><span class="sxs-lookup"><span data-stu-id="6a75a-127">After a marked transaction commits, a row is inserted in the [logmarkhistory](/sql/relational-databases/system-tables/logmarkhistory-transact-sql) table in **msdb**.</span></span>  
  
-   <span data-ttu-id="6a75a-128">si une transaction marquée s'étend à plusieurs bases de données sur le même serveur de bases de données ou sur différents serveurs, les marques doivent être enregistrées dans les journaux de toutes les bases de données concernées.</span><span class="sxs-lookup"><span data-stu-id="6a75a-128">If a marked transaction spans multiple databases on the same database server or on different servers, the marks must be recorded in the logs of all the affected databases.</span></span>  
  
## <a name="creating-the-marked-transactions"></a><span data-ttu-id="6a75a-129">Création des transactions marquées</span><span class="sxs-lookup"><span data-stu-id="6a75a-129">Creating the Marked Transactions</span></span>  
 <span data-ttu-id="6a75a-130">Pour créer une transaction marquée, utilisez l’instruction [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) et la clause WITH MARK [*description*].</span><span class="sxs-lookup"><span data-stu-id="6a75a-130">To create a marked transaction, use the [BEGIN TRANSACTION](/sql/t-sql/language-elements/begin-transaction-transact-sql) statement and the WITH MARK [*description*] clause.</span></span> <span data-ttu-id="6a75a-131">La *description* facultative est une description textuelle de la marque.</span><span class="sxs-lookup"><span data-stu-id="6a75a-131">The optional *description* is a textual description of the mark.</span></span> <span data-ttu-id="6a75a-132">Un nom de marque pour la transaction est requis.</span><span class="sxs-lookup"><span data-stu-id="6a75a-132">A mark name for the transaction is required.</span></span> <span data-ttu-id="6a75a-133">Un nom de marque peut être réutilisé.</span><span class="sxs-lookup"><span data-stu-id="6a75a-133">A mark name can be reused.</span></span> <span data-ttu-id="6a75a-134">Le journal des transactions enregistre le nom de la marque, la description, la base de données, l'utilisateur, la date et l'heure, et le numéro séquentiel dans le journal (LSN, Log Sequence Number).</span><span class="sxs-lookup"><span data-stu-id="6a75a-134">The transaction log records the mark name, description, database, user, datetime information, and the log sequence number (LSN).</span></span> <span data-ttu-id="6a75a-135">Les informations de date et d'heure sont utilisées conjointement avec le nom de la marque pour identifier celle-ci de façon univoque.</span><span class="sxs-lookup"><span data-stu-id="6a75a-135">The datetime information is used along with the mark name to uniquely identify the mark.</span></span>  
  
 <span data-ttu-id="6a75a-136">**Pour créer des transactions marquées dans un jeu de bases de données :**</span><span class="sxs-lookup"><span data-stu-id="6a75a-136">**To create marked transactions in a set of databases:**</span></span>  
  
1.  <span data-ttu-id="6a75a-137">Nommez la transaction dans l'instruction BEGIN TRAN et utilisez la clause WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="6a75a-137">Name the transaction in the BEGIN TRAN statement and use the WITH MARK clause</span></span>  
  
     <span data-ttu-id="6a75a-138">Vous pouvez imbriquer l’instruction BEGIN TRAN *nom_nouvelle_marque* WITH MARK au sein d’une transaction existante.</span><span class="sxs-lookup"><span data-stu-id="6a75a-138">You can nest the statement BEGIN TRAN *new_mark_name* WITH MARK within an existing transaction.</span></span> <span data-ttu-id="6a75a-139">La valeur de *nom_nouvelle_marque* correspond au nom de la marque de la transaction, même si la transaction a un nom de transaction.</span><span class="sxs-lookup"><span data-stu-id="6a75a-139">The value of *new_mark_name* is the mark name for the transaction, even if the transaction possesses a transaction name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6a75a-140">Si vous émettez une deuxième instruction BEGIN TRAN...WITH MARK, celle-ci est ignorée mais génère un message d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="6a75a-140">If you issue a second nested BEGIN TRAN...WITH MARK, that statement is skipped but causes a warning message.</span></span>  
  
2.  <span data-ttu-id="6a75a-141">Exécutez une mise à jour sur toutes les bases de données dans le jeu.</span><span class="sxs-lookup"><span data-stu-id="6a75a-141">Run an update against all of the databases in the set.</span></span>  
  
     <span data-ttu-id="6a75a-142">La marque d'une transaction spécifique est insérée dans les journaux de transaction uniquement sur l'instance du serveur où est exécutée l'instruction BEGIN TRAN...WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="6a75a-142">The mark for a specific transaction is inserted into transaction logs only on the server instance where the BEGIN TRAN...WITH MARK statement is executed.</span></span> <span data-ttu-id="6a75a-143">La marque de transaction est placée dans le journal de transaction de chaque base de données mise à jour par la transaction marquée sur cette instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="6a75a-143">The transaction mark is placed in the transaction log of every database updated by the marked transaction on that server instance.</span></span> <span data-ttu-id="6a75a-144">Si les bases de données résident sur différentes instances du serveur, des marques identiques doivent être créées sur chaque instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="6a75a-144">If the databases reside on different server instances, identical marks must be created on each of the server instances.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="6a75a-145">Exemples</span><span class="sxs-lookup"><span data-stu-id="6a75a-145">Examples</span></span>  
 <span data-ttu-id="6a75a-146">L'exemple suivant restaure le journal des transactions jusqu'à la marque dans la transaction marquée nommée `ListPriceUpdate`.</span><span class="sxs-lookup"><span data-stu-id="6a75a-146">The following example restores the transaction log to the mark in the marked transaction named `ListPriceUpdate`.</span></span>  
  
```sql  
USE AdventureWorks  
GO  
BEGIN TRANSACTION ListPriceUpdate  
   WITH MARK 'UPDATE Product list prices';  
GO  
  
UPDATE Production.Product  
   SET ListPrice = ListPrice * 1.10  
   WHERE ProductNumber LIKE 'BK-%';  
GO  
  
COMMIT TRANSACTION ListPriceUpdate;  
GO  
  
-- Time passes. Regular database   
-- and log backups are taken.  
-- An error occurs in the database.  
USE master  
GO  
  
RESTORE DATABASE AdventureWorks  
FROM AdventureWorksBackups  
WITH FILE = 3, NORECOVERY;  
GO  
  
RESTORE LOG AdventureWorks  
   FROM AdventureWorksBackups   
   WITH FILE = 4,  
   RECOVERY,   
   STOPATMARK = 'ListPriceUpdate';  
```  
  
## <a name="forcing-a-mark-to-spread-to-other-servers"></a><span data-ttu-id="6a75a-147">Distribution forcée d'une marque à d'autres serveurs</span><span class="sxs-lookup"><span data-stu-id="6a75a-147">Forcing a Mark to Spread to Other Servers</span></span>  
 <span data-ttu-id="6a75a-148">Le nom d'une marque de transaction n’est pas automatiquement distribué à un autre serveur au moment où la transaction atteint ce dernier.</span><span class="sxs-lookup"><span data-stu-id="6a75a-148">A transaction mark name is not automatically distributed to another server as the transaction spreads there.</span></span> <span data-ttu-id="6a75a-149">Pour forcer la distribution de la marque aux autres serveurs, vous devez écrire une procédure stockée contenant une instruction BEGIN TRAN *nom* WITH MARK.</span><span class="sxs-lookup"><span data-stu-id="6a75a-149">To force the mark to spread to the other servers, a stored procedure must be written that contains a BEGIN TRAN *name* WITH MARK statement.</span></span> <span data-ttu-id="6a75a-150">Cette procédure stockée doit ensuite être exécutée sur le serveur distant en fonction de la portée de la transaction dans le serveur d'origine.</span><span class="sxs-lookup"><span data-stu-id="6a75a-150">That stored procedure must then be executed on the remote server under the scope of the transaction in the originating server.</span></span>  
  
 <span data-ttu-id="6a75a-151">Supposons, par exemple, qu'une base de données partitionnée existe sur plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a75a-151">For example, consider a partitioned database that exists on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6a75a-152">Sur chaque instance se trouve une base de données nommée `coyote`.</span><span class="sxs-lookup"><span data-stu-id="6a75a-152">On each instance is a database named `coyote`.</span></span> <span data-ttu-id="6a75a-153">Créez d’abord une procédure stockée, par exemple `sp_SetMark`, dans chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="6a75a-153">First, in every database, create a stored procedure, for example, `sp_SetMark`.</span></span>  
  
```sql  
CREATE PROCEDURE sp_SetMark  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION @name WITH MARK  
UPDATE coyote.dbo.Marks SET one = 1  
COMMIT TRANSACTION;  
GO  
```  
  
 <span data-ttu-id="6a75a-154">Ensuite, créez une procédure stockée `sp_MarkAll` contenant une transaction qui place une marque dans chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="6a75a-154">Next, create stored procedure `sp_MarkAll` containing a transaction that places a mark in every database.</span></span> <span data-ttu-id="6a75a-155">`sp_MarkAll` peut être exécutée à partir de n’importe quelle instance.</span><span class="sxs-lookup"><span data-stu-id="6a75a-155">`sp_MarkAll` can be run from any of the instances.</span></span>  
  
```sql  
CREATE PROCEDURE sp_MarkAll  
@name nvarchar (128)  
AS  
BEGIN TRANSACTION  
EXEC instance0.coyote.dbo.sp_SetMark @name  
EXEC instance1.coyote.dbo.sp_SetMark @name  
EXEC instance2.coyote.dbo.sp_SetMark @name  
COMMIT TRANSACTION;  
GO  
```  
  
### <a name="two-phase-commit"></a><span data-ttu-id="6a75a-156">validation en deux temps</span><span class="sxs-lookup"><span data-stu-id="6a75a-156">Two-Phase Commit</span></span>  
 <span data-ttu-id="6a75a-157">La validation d'une transaction distribuée s'effectue en deux étapes : préparation et validation.</span><span class="sxs-lookup"><span data-stu-id="6a75a-157">Committing a distributed transaction occurs in two phases: prepare and commit.</span></span> <span data-ttu-id="6a75a-158">Lorsqu’une transaction marquée est validée, l’enregistrement du journal de validation pour chaque base de données dans la transaction marquée est placé dans le journal à un point où il n’existe aucun doute concernant les transactions dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="6a75a-158">When a marked transaction is committed, the commit log record for each database in the marked transaction is placed in the log at a point where there are no in-doubt transactions in any of the logs.</span></span> <span data-ttu-id="6a75a-159">À partir de ce point, il est garanti qu’il n’existe aucune transaction qui apparaît comme validée dans un journal, mais pas dans un autre.</span><span class="sxs-lookup"><span data-stu-id="6a75a-159">At this point, it is guaranteed that there are no transactions that appear as committed in one log, but not committed in another log.</span></span>  
  
 <span data-ttu-id="6a75a-160">Les étapes suivantes accomplissent cela lors de la validation d’une transaction marquée :</span><span class="sxs-lookup"><span data-stu-id="6a75a-160">The following steps accomplish this during the commit of a marked transaction:</span></span>  
  
1.  <span data-ttu-id="6a75a-161">La phase de préparation d’une transaction marquée bloque toutes les nouvelles préparations et validations.</span><span class="sxs-lookup"><span data-stu-id="6a75a-161">Prepare phase of a marking transaction stalls all new prepares and commits.</span></span>  
  
2.  <span data-ttu-id="6a75a-162">Seules les validations de transactions déjà préparées sont autorisées à continuer.</span><span class="sxs-lookup"><span data-stu-id="6a75a-162">Only commits of already prepared transactions are allowed to continue.</span></span>  
  
3.  <span data-ttu-id="6a75a-163">Le marquage des transactions attend ensuite toutes les transactions préparées à traiter (avec un délai d’attente).</span><span class="sxs-lookup"><span data-stu-id="6a75a-163">Marking transaction then waits for all prepared transactions to drain (with time-out).</span></span>  
  
4.  <span data-ttu-id="6a75a-164">La transaction marquée est préparée puis validée.</span><span class="sxs-lookup"><span data-stu-id="6a75a-164">Marked transaction is prepared and committed.</span></span>  
  
5.  <span data-ttu-id="6a75a-165">Le blocage des nouvelles préparations et validations est supprimé.</span><span class="sxs-lookup"><span data-stu-id="6a75a-165">The stall of new prepares and commits is removed.</span></span>  
  
 <span data-ttu-id="6a75a-166">Ces blocages générés par des transactions marquées qui s’étendent à plusieurs bases de données peuvent atténuer les performances de traitement de transactions sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="6a75a-166">The stalls generated by marked transactions that span multiple databases can reduce the transaction processing performance of the server.</span></span>  
  
 <span data-ttu-id="6a75a-167">Il est recommandé de ne pas exécuter simultanément des transactions marquées.</span><span class="sxs-lookup"><span data-stu-id="6a75a-167">We recommend that you do not run concurrent marked transactions.</span></span> <span data-ttu-id="6a75a-168">Il est rare mais possible qu’une transaction marquée distribuée en cours de validation se bloque avec d’autres transactions analogues également en cours de validation.</span><span class="sxs-lookup"><span data-stu-id="6a75a-168">It is rare but possible for the commit of a distributed marked transaction to deadlock with other distributed marked transactions that are committing at the same time.</span></span> <span data-ttu-id="6a75a-169">Dans ce cas, la transaction marquée est choisie comme victime du blocage et est annulée.</span><span class="sxs-lookup"><span data-stu-id="6a75a-169">When this happens, the marking transaction is chosen as the deadlock victim and is rolled back.</span></span> <span data-ttu-id="6a75a-170">Lorsque cette erreur se produit, l’application peut tester à nouveau la transaction marquée.</span><span class="sxs-lookup"><span data-stu-id="6a75a-170">When this error occurs, the application can retry the marked transaction.</span></span> <span data-ttu-id="6a75a-171">Lorsque plusieurs transactions marquées tentent une validation simultanée, l’éventualité d’un verrouillage est plus élevée.</span><span class="sxs-lookup"><span data-stu-id="6a75a-171">When multiple marked transactions try to commit concurrently, there is a higher probability of deadlock.</span></span>  
  
## <a name="recovering-to-a-marked-transaction"></a><span data-ttu-id="6a75a-172">Récupération jusqu'à une transaction marquée</span><span class="sxs-lookup"><span data-stu-id="6a75a-172">Recovering to a Marked Transaction</span></span>  
 <span data-ttu-id="6a75a-173">Pour plus d’informations sur la manière de récupérer une base de données qui contient des transactions marquées jusqu’à une marque particulière ou juste avant, consultez [Récupération de bases de données associées contenant une transaction marquée](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="6a75a-173">For information about how to recover a database that contains marked transactions to or just before a particular mark, see [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a75a-174"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6a75a-174">See Also</span></span>  
 <span data-ttu-id="6a75a-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6a75a-175">[BEGIN DISTRIBUTED TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-distributed-transaction-transact-sql) </span></span>  
 <span data-ttu-id="6a75a-176">[Sauvegarder et restaurer des bases de données système &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6a75a-176">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="6a75a-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6a75a-177">[BEGIN TRANSACTION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/begin-transaction-transact-sql) </span></span>  
 <span data-ttu-id="6a75a-178">[Appliquer les sauvegardes du journal des transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6a75a-178">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="6a75a-179">[Sauvegardes complètes de bases de données &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6a75a-179">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="6a75a-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6a75a-180">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="6a75a-181">Récupération de bases de données associées contenant une transaction marquée</span><span class="sxs-lookup"><span data-stu-id="6a75a-181">Recovery of Related  Databases That Contain Marked Transaction</span></span>](recovery-of-related-databases-that-contain-marked-transaction.md)  
  
  
