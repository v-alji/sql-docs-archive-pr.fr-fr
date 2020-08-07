---
title: Récupérer un numéro séquentiel dans le journal (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log sequence numbers [SQL Server]
- STOPBEFOREMARK option [RESTORE statement]
- STOPATMARK option [RESTORE statement]
- point in time recovery [SQL Server]
- restoring databases [SQL Server], point in time
- recovery [SQL Server], databases
- restoring [SQL Server], point in time
- LSNs
- database recovery [SQL Server]
- database restores [SQL Server], point in time
ms.assetid: f7b3de5b-198d-448d-8c71-1cdd9239676c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4df55c3468fc009d86cffd58a837d6935f5ce14b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612427"
---
# <a name="recover-to-a-log-sequence-number-sql-server"></a><span data-ttu-id="91f47-102">Récupérer un numéro séquentiel dans le journal (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91f47-102">Recover to a Log Sequence Number (SQL Server)</span></span>
  <span data-ttu-id="91f47-103">Cette rubrique s'applique uniquement aux bases de données employant les modes de restauration complète ou de récupération utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="91f47-103">This topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
 <span data-ttu-id="91f47-104">Vous pouvez utiliser un numéro séquentiel dans le journal pour définir le point de récupération d'une opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="91f47-104">You can use a log sequence number (LSN) to define the recovery point for a restore operation.</span></span> <span data-ttu-id="91f47-105">Toutefois, cette fonctionnalité est spécialement conçue pour les fournisseurs d'outils et ne devrait pas être nécessaire dans la plupart des cas.</span><span class="sxs-lookup"><span data-stu-id="91f47-105">However, this is a specialized feature that is intended for tools vendors and is unlikely to be generally useful.</span></span>  
  
##  <a name="overview-of-log-sequence-numbers"></a><a name="LSNs"></a> <span data-ttu-id="91f47-106">Vue d'ensemble des numéros séquentiels dans le journal</span><span class="sxs-lookup"><span data-stu-id="91f47-106">Overview of Log Sequence Numbers</span></span>  
 <span data-ttu-id="91f47-107">Les numéros LSN sont utilisés en interne pendant une séquence RESTORE pour rechercher le point dans le temps par rapport auquel les données ont été restaurées.</span><span class="sxs-lookup"><span data-stu-id="91f47-107">LSNs are used internally during a RESTORE sequence to track the point in time to which data has been restored.</span></span> <span data-ttu-id="91f47-108">Lorsqu'une sauvegarde est restaurée, les données sont restaurées par rapport au numéro LSN qui correspond au point dans le temps à partir duquel la sauvegarde a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="91f47-108">When a backup is restored, the data is restored to the LSN corresponding to the point in time at which the backup was taken.</span></span> <span data-ttu-id="91f47-109">Les sauvegardes différentielles et de journaux font passer la base de données restaurée à une date ultérieure qui correspond à un numéro LSN supérieur.</span><span class="sxs-lookup"><span data-stu-id="91f47-109">Differential and log backups advance the restored database to a later time, which corresponds to a higher LSN.</span></span>  
  
 <span data-ttu-id="91f47-110">Chaque enregistrement du journal de transactions est identifié de manière unique par un numéro séquentiel dans le journal (LSN).</span><span class="sxs-lookup"><span data-stu-id="91f47-110">Every record in the transaction log is uniquely identified by a log sequence number (LSN).</span></span> <span data-ttu-id="91f47-111">Les numéros de séquence d'enregistrement sont ordonnés de sorte que si LSN2 est supérieur à LSN1, la modification décrite par l'enregistrement de journal référencé par LSN2 se produit après la modification décrite par le numéro LSN d'enregistrement de journal.</span><span class="sxs-lookup"><span data-stu-id="91f47-111">LSNs are ordered such that if LSN2 is greater than LSN1, the change described by the log record referred to by LSN2 occurred after the change described by the log record LSN.</span></span>  
  
 <span data-ttu-id="91f47-112">Le numéro LSN d'un enregistrement de journal qui correspond à l'occurrence d'un événement significatif peut s'avérer utile pour créer les séquences de restauration appropriées.</span><span class="sxs-lookup"><span data-stu-id="91f47-112">The LSN of a log record at which a significant event occurred can be useful for constructing correct restore sequences.</span></span> <span data-ttu-id="91f47-113">Étant donné que les LSN sont ordonnés, ils peuvent être comparés pour déterminer leur égalité et leur inégalité (c’est-à-dire,, **\<**, **>** **=** , **\<=**, **>=** ).</span><span class="sxs-lookup"><span data-stu-id="91f47-113">Because LSNs are ordered, they can be compared for equality and inequality (that is, **\<**, **>**, **=**, **\<=**, **>=**).</span></span> <span data-ttu-id="91f47-114">Ces comparaisons sont utiles pour créer des séquences de restauration.</span><span class="sxs-lookup"><span data-stu-id="91f47-114">Such comparisons are useful when constructing restore sequences.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91f47-115">Les numéros LSN sont des valeurs de type données `numeric`(25,0).</span><span class="sxs-lookup"><span data-stu-id="91f47-115">LSNs are values of data type `numeric`(25,0).</span></span> <span data-ttu-id="91f47-116">Les opérations arithmétiques (addition ou soustraction, par exemple) ne sont pas significatives et ne doivent pas être utilisées avec les numéros LSN.</span><span class="sxs-lookup"><span data-stu-id="91f47-116">Arithmetic operations (for example, addition or subtraction) are not meaningful and must not be used with LSNs.</span></span>  
  

  
## <a name="viewing-lsns-used-by-backup-and-restore"></a><span data-ttu-id="91f47-117">Affichage des numéros LSN utilisés par la sauvegarde et la restauration</span><span class="sxs-lookup"><span data-stu-id="91f47-117">Viewing LSNs Used by Backup and Restore</span></span>  
 <span data-ttu-id="91f47-118">Le numéro LSN d'un enregistrement de journal dans lequel un événement de sauvegarde et de restauration s'est produit peut être affiché en utilisant une ou plusieurs des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="91f47-118">The LSN of a log record at which a given backup and restore event occurred is viewable using one or more of the following:</span></span>  
  
-   [<span data-ttu-id="91f47-119">backupset</span><span class="sxs-lookup"><span data-stu-id="91f47-119">backupset</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
-   [<span data-ttu-id="91f47-120">backupfile</span><span class="sxs-lookup"><span data-stu-id="91f47-120">backupfile</span></span>](/sql/relational-databases/system-tables/backupfile-transact-sql)  
  
-   <span data-ttu-id="91f47-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="91f47-121">[sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql); [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql)</span></span>  
  
-   [<span data-ttu-id="91f47-122">RESTORE HEADERONLY</span><span class="sxs-lookup"><span data-stu-id="91f47-122">RESTORE HEADERONLY</span></span>](/sql/t-sql/statements/restore-statements-headeronly-transact-sql)  
  
-   [<span data-ttu-id="91f47-123">RESTORE FILELISTONLY</span><span class="sxs-lookup"><span data-stu-id="91f47-123">RESTORE FILELISTONLY</span></span>](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="91f47-124">Les numéros LSN figurent également dans les textes de message.</span><span class="sxs-lookup"><span data-stu-id="91f47-124">LSNs also appear in some message texts.</span></span>  
  
## <a name="transact-sql-syntax-for-restoring-to-an-lsn"></a><span data-ttu-id="91f47-125">Syntaxe Transact-SQL relative à la restauration d'après un LSN</span><span class="sxs-lookup"><span data-stu-id="91f47-125">Transact-SQL Syntax for Restoring to an LSN</span></span>  
 <span data-ttu-id="91f47-126">Grâce à l'instruction [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , vous pouvez vous arrêter à un LSN ou immédiatement avant ce point de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="91f47-126">By using a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, you can stop at or immediately before the LSN, as follows:</span></span>  
  
-   <span data-ttu-id="91f47-127">Utilisez la clause WITH STOPATMARK **='** lsn: _<numéro_lsn>_ **'** , où lsn: *\<lsnNumber>* correspond à une chaîne spécifiant que l’enregistrement du journal qui contient le LSN spécifié est le point de récupération.</span><span class="sxs-lookup"><span data-stu-id="91f47-127">Use the WITH STOPATMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record that contains the specified LSN is the recovery point.</span></span>  
  
     <span data-ttu-id="91f47-128">STOPATMARK permet la restauration par progression jusqu'au NSE et inclut l'enregistrement correspondant issu du journal, dans la restauration.</span><span class="sxs-lookup"><span data-stu-id="91f47-128">STOPATMARK roll forwards to the LSN and includes that log record in the roll forward.</span></span>  
  
-   <span data-ttu-id="91f47-129">Utilisez la clause WITH STOPBEFOREMARK **='** lsn: _<numéro_lsn>_ **'** , où lsn: *\<lsnNumber>* correspond à une chaîne spécifiant que l’entrée se trouvant dans le journal immédiatement avant celle qui contient le LSN spécifié est le point de récupération.</span><span class="sxs-lookup"><span data-stu-id="91f47-129">Use the WITH STOPBEFOREMARK **='** lsn:_<lsn_number>_**'** clause, where lsn:*\<lsnNumber>* is a string that specifies that the log record immediately before the log record that contains the specified LSN number is the recovery point.</span></span>  
  
     <span data-ttu-id="91f47-130">STOPBEFOREMARK permet la restauration par progression jusqu'au NSE mais exclut l'enregistrement correspondant, se trouvant dans le journal, de la restauration par progression.</span><span class="sxs-lookup"><span data-stu-id="91f47-130">STOPBEFOREMARK rolls forward to the LSN and excludes that log record from the roll forward.</span></span>  
  
 <span data-ttu-id="91f47-131">De façon générale, une transaction donnée est sélectionnée dans le but d'être incluse ou exclue.</span><span class="sxs-lookup"><span data-stu-id="91f47-131">Typically, a specific transaction is selected to be included or excluded.</span></span> <span data-ttu-id="91f47-132">Dans la pratique, et ce même s'il n'est pas requis, l'enregistrement spécifié dans le journal correspond à un enregistrement de validation de transaction.</span><span class="sxs-lookup"><span data-stu-id="91f47-132">Although not required, in practice, the specified log record is a transaction-commit record.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="91f47-133">Exemples</span><span class="sxs-lookup"><span data-stu-id="91f47-133">Examples</span></span>  
 <span data-ttu-id="91f47-134">L'exemple suivant suppose que la base de données `AdventureWorks` a été modifiée afin d'utiliser le mode de récupération complète.</span><span class="sxs-lookup"><span data-stu-id="91f47-134">The following example assumes that the `AdventureWorks` database has been changed to use the full recovery model.</span></span>  
  
```  
RESTORE LOG AdventureWorks FROM DISK = 'c:\adventureworks_log.bak'   
WITH STOPATMARK = 'lsn:15000000040000037'  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="91f47-135">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="91f47-135">Related Tasks</span></span>  
  
-   [<span data-ttu-id="91f47-136">Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="91f47-136">Restore a Database Backup &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-backup-using-ssms.md)  
  
-   [<span data-ttu-id="91f47-137">Sauvegarder un journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="91f47-137">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="91f47-138">Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="91f47-138">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
-   [<span data-ttu-id="91f47-139">Restaurer une base de données jusqu’au point d’échec en mode de récupération complète &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91f47-139">Restore a Database to the Point of Failure Under the Full Recovery Model &#40;Transact-SQL&#41;</span></span>](restore-database-to-point-of-failure-full-recovery.md)  
  
-   [<span data-ttu-id="91f47-140">Restaurer une base de données jusqu’à une transaction marquée &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="91f47-140">Restore a Database to a Marked Transaction &#40;SQL Server Management Studio&#41;</span></span>](restore-a-database-to-a-marked-transaction-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="91f47-141">Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="91f47-141">Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;</span></span>](restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="91f47-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="91f47-142">See Also</span></span>  
 <span data-ttu-id="91f47-143">[Appliquer les sauvegardes du journal des transactions &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91f47-143">[Apply Transaction Log Backups &#40;SQL Server&#41;](transaction-log-backups-sql-server.md) </span></span>  
 <span data-ttu-id="91f47-144">[Journal des transactions &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91f47-144">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="91f47-145">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="91f47-145">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
