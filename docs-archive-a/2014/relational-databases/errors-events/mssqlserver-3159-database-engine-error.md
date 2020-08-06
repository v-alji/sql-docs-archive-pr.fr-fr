---
title: MSSQLSERVER_3159 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3159 (Database Engine error)
ms.assetid: c93c1003-0e3a-40aa-9873-44a0f5b8b57e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b469842b2aab15980c72ea01e46270c55ef29e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605475"
---
# <a name="mssqlserver_3159"></a><span data-ttu-id="046ce-102">MSSQLSERVER_3159</span><span class="sxs-lookup"><span data-stu-id="046ce-102">MSSQLSERVER_3159</span></span>
    
## <a name="details"></a><span data-ttu-id="046ce-103">Détails</span><span class="sxs-lookup"><span data-stu-id="046ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="046ce-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="046ce-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="046ce-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="046ce-105">Event ID</span></span>|<span data-ttu-id="046ce-106">3159</span><span class="sxs-lookup"><span data-stu-id="046ce-106">3159</span></span>|  
|<span data-ttu-id="046ce-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="046ce-107">Event Source</span></span>|<span data-ttu-id="046ce-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="046ce-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="046ce-109">Composant</span><span class="sxs-lookup"><span data-stu-id="046ce-109">Component</span></span>|<span data-ttu-id="046ce-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="046ce-110">SQLEngine</span></span>|  
|<span data-ttu-id="046ce-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="046ce-111">Symbolic Name</span></span>|<span data-ttu-id="046ce-112">LDDB_LOGNOTBACKEDUP</span><span class="sxs-lookup"><span data-stu-id="046ce-112">LDDB_LOGNOTBACKEDUP</span></span>|  
|<span data-ttu-id="046ce-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="046ce-113">Message Text</span></span>|<span data-ttu-id="046ce-114">La fin du journal pour la base de données "%ls" n'a pas été sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="046ce-114">The tail of the log for the database "%ls" has not been backed up.</span></span> <span data-ttu-id="046ce-115">Utilisez BACKUP LOG WITH NORECOVERY pour sauvegarder le journal s'il contient des travaux que vous ne voulez pas perdre.</span><span class="sxs-lookup"><span data-stu-id="046ce-115">Use BACKUP LOG WITH NORECOVERY to back up the log if it contains work that you do not want to lose.</span></span> <span data-ttu-id="046ce-116">Utilisez la clause WITH REPLACE ou WITH STOPAT de l'instruction RESTORE pour remplacer simplement le contenu du journal.</span><span class="sxs-lookup"><span data-stu-id="046ce-116">Use the WITH REPLACE or WITH STOPAT clause of the RESTORE statement to just overwrite the contents of the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="046ce-117">Explication</span><span class="sxs-lookup"><span data-stu-id="046ce-117">Explanation</span></span>  
 <span data-ttu-id="046ce-118">Dans la plupart des cas, en mode de restauration complète ou en mode de récupération utilisant les journaux de transactions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exige que vous sauvegardiez la fin du journal pour capturer les enregistrements du journal qui n'ont pas encore été sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="046ce-118">In most cases, under the full or bulk-logged recovery models, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires that you back up the tail of the log to capture the log records that have not yet been backed up.</span></span> <span data-ttu-id="046ce-119">Une sauvegarde de la fin du journal effectuée juste avant une opération de restauration s'appelle une « sauvegarde de la fin du journal ».</span><span class="sxs-lookup"><span data-stu-id="046ce-119">A log backup taken of the tail of the log just before a restore operation is called a tail-log backup.</span></span>  
  
 <span data-ttu-id="046ce-120">Si vous récupérez une base de données jusqu'à la défaillance, la sauvegarde de la fin du journal est la dernière sauvegarde pertinente du plan de récupération.</span><span class="sxs-lookup"><span data-stu-id="046ce-120">When you are recovering a database to the point of a failure, the tail-log backup is the last backup of interest in the recovery plan.</span></span> <span data-ttu-id="046ce-121">Si vous ne pouvez pas effectuer la sauvegarde de la fin du journal, vous pouvez récupérer une base de données uniquement jusqu'à la fin de la dernière sauvegarde ayant été créée avant la défaillance.</span><span class="sxs-lookup"><span data-stu-id="046ce-121">If you cannot back up the tail of the log, you can recover a database only to the end of the last backup that was created before the failure.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="046ce-122">requiert habituellement la réalisation d'une sauvegarde de la fin du journal avant que vous commenciez à restaurer une base de données.</span><span class="sxs-lookup"><span data-stu-id="046ce-122">usually requires that you take a tail-log backup before you start to restore a database.</span></span> <span data-ttu-id="046ce-123">Une sauvegarde de la fin du journal empêche la perte de données et préserve la continuité de la séquence de journaux de transactions consécutifs.</span><span class="sxs-lookup"><span data-stu-id="046ce-123">The tail-log backup prevents work loss and keeps the log chain intact.</span></span> <span data-ttu-id="046ce-124">Néanmoins, tous les scénarios de restauration ne nécessitent pas une sauvegarde de la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="046ce-124">However, not all restore scenarios require a tail-log backup.</span></span> <span data-ttu-id="046ce-125">Vous n'êtes pas obligé de disposer d'une sauvegarde de la fin du journal si le point de récupération est contenu dans une sauvegarde de journal antérieure ou si vous déplacez ou remplacez (par écrasement) la base de données et ne souhaitez pas la restaurer à un point donné après la sauvegarde la plus récente.</span><span class="sxs-lookup"><span data-stu-id="046ce-125">You do not have to have a tail-log backup if the recovery point is included in an earlier log backup, or if you are moving or replacing (overwriting) the database and do not need to restore it to a point of time after the most recent backup.</span></span> <span data-ttu-id="046ce-126">De plus, si les fichiers journaux sont endommagés et une sauvegarde de la fin du journal ne peut pas être créée, vous devez restaurer la base de données sans utiliser une sauvegarde de la fin du journal.</span><span class="sxs-lookup"><span data-stu-id="046ce-126">Also, if the log files are damaged and a tail-log backup cannot be created, you must restore the database without using a tail-log backup.</span></span> <span data-ttu-id="046ce-127">Les transactions validées après la dernière sauvegarde de journal sont perdues.</span><span class="sxs-lookup"><span data-stu-id="046ce-127">Any transactions committed after the latest log backup are lost.</span></span> <span data-ttu-id="046ce-128">Pour plus d’informations, consultez « Restauration sans utiliser de sauvegarde de la fin du journal » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="046ce-128">For more information, see "Restoring Without Using a Tail-Log Backup," later in this topic.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="046ce-129">L'option REPLACE doit être utilisée rarement et uniquement après un examen attentif.</span><span class="sxs-lookup"><span data-stu-id="046ce-129">REPLACE should be used rarely, and only after careful consideration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="046ce-130">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="046ce-130">User Action</span></span>  
 <span data-ttu-id="046ce-131">Effectuez une sauvegarde de la fin du journal et retentez l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="046ce-131">Take a tail-log backup, and retry the restore operation.</span></span>  
  
 <span data-ttu-id="046ce-132">Si vous ne pouvez pas sauvegarder la fin du journal, utilisez la clause WITH STOPAT ou WITH REPLACE dans vos instructions RESTORE.</span><span class="sxs-lookup"><span data-stu-id="046ce-132">If you cannot back up the tail of the log, use WITH STOPAT or WITH REPLACE in your RESTORE statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="046ce-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="046ce-133">See Also</span></span>  
 <span data-ttu-id="046ce-134">[Restaurer une base de données SQL Server jusqu’à une limite dans le temps &#40;mode de récupération complète&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="046ce-134">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="046ce-135">[Sauvegardez le journal des transactions lorsque la base de données est endommagée &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="046ce-135">[Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span></span>  
 <span data-ttu-id="046ce-136">[Sauvegarder un journal des transactions &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="046ce-136">[Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="046ce-137">Sauvegardes de la fin du journal &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="046ce-137">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/tail-log-backups-sql-server.md)  
  
  
