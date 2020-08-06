---
title: Prérequis pour une journalisation minimale dans l’importation en bloc | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- minimal logging [SQL Server]
- logged bulk copy [SQL Server]
- logs [SQL Server], minimal logging
- minimally logged operations [SQL Server]
- bulk importing [SQL Server], minimal logging
ms.assetid: bd1dac6b-6ef8-4735-ad4e-67bb42dc4f66
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4711e25dcfcc99e14894e47166638673c61a6831
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708404"
---
# <a name="prerequisites-for-minimal-logging-in-bulk-import"></a><span data-ttu-id="ecbdb-102">Prérequis pour une journalisation minimale dans l’importation en bloc</span><span class="sxs-lookup"><span data-stu-id="ecbdb-102">Prerequisites for Minimal Logging in Bulk Import</span></span>
  <span data-ttu-id="ecbdb-103">Pour une base de données en mode de récupération complète, toutes les opérations d'insertion de lignes effectuées par importation en bloc sont entièrement enregistrées dans le journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-103">For a database under the full recovery model, all row-insert operations that are performed by bulk import are fully logged in the transaction log.</span></span> <span data-ttu-id="ecbdb-104">Les importations de données de grande taille peuvent entraîner un remplissage rapide du journal des transactions si le mode de récupération complète est utilisé.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-104">Large data imports can cause the transaction log to fill rapidly if the full recovery model is used.</span></span> <span data-ttu-id="ecbdb-105">Par opposition, en mode de récupération simple ou en mode de récupération utilisant les journaux de transactions, la journalisation minimale des opérations d'importation en bloc réduit la possibilité qu'une importation en bloc remplira l'espace de journal.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-105">In contrast, under the simple recovery model or bulk-logged recovery model, minimal logging of bulk-import operations reduces the possibility that a bulk-import operation will fill the log space.</span></span> <span data-ttu-id="ecbdb-106">La journalisation minimale est également plus efficace qu'une journalisation complète.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-106">Minimal logging is also more efficient than full logging.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ecbdb-107">Le mode de récupération utilisant les journaux de transactions est conçu pour remplacer temporairement le mode de récupération complète durant les grandes opérations en bloc.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-107">The bulk-logged recovery model is designed to temporarily replace the full recovery model during large bulk operations.</span></span>  
  
## <a name="table-requirements-for-minimally-logging-bulk-import-operations"></a><span data-ttu-id="ecbdb-108">Conditions à remplir par les tables pour la journalisation minimale des opérations d'importation en bloc</span><span class="sxs-lookup"><span data-stu-id="ecbdb-108">Table Requirements for Minimally Logging Bulk-Import Operations</span></span>  
 <span data-ttu-id="ecbdb-109">La journalisation minimale nécessite que la table cible remplisse les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ecbdb-109">Minimal logging requires that the target table meets the following conditions:</span></span>  
  
-   <span data-ttu-id="ecbdb-110">La table n'est pas en cours de réplication.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-110">The table is not being replicated.</span></span>  
  
-   <span data-ttu-id="ecbdb-111">Le verrouillage de la table est activé (à l'aide de TABLOCK).</span><span class="sxs-lookup"><span data-stu-id="ecbdb-111">Table locking is specified (using TABLOCK).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ecbdb-112">Bien que les insertions de données ne soient pas consignées dans le journal des transactions lors des opérations d'importation en bloc à journalisation minimale, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] consigne tout de même les allocations d'extensions chaque fois qu'une nouvelle extension est allouée à la table.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-112">Although data insertions are not logged in the transaction log during a minimally logged bulk-import operation, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] still logs extent allocations each time a new extent is allocated to the table.</span></span>  
  
-   <span data-ttu-id="ecbdb-113">La table n'est pas une table mémoire optimisée.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-113">Table is not a memory-optimized table.</span></span>  
  
 <span data-ttu-id="ecbdb-114">La possibilité de journalisation minimale pour une table dépend également du fait que celle-ci soit indexée et, si elle l'est, du fait qu'elle soit vide :</span><span class="sxs-lookup"><span data-stu-id="ecbdb-114">Whether minimal logging can occur for a table also depends on whether the table is indexed and, if so, whether the table is empty:</span></span>  
  
-   <span data-ttu-id="ecbdb-115">Si la table ne possède aucun index, les pages de données bénéficient de la journalisation minimale.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-115">If the table has no indexes, data pages are minimally logged.</span></span>  
  
-   <span data-ttu-id="ecbdb-116">Si la table ne possède pas d'index cluster, mais possède un ou plusieurs index non cluster, les pages de données bénéficient toujours de la journalisation minimale.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-116">If the table has no clustered index but has one or more nonclustered indexes, data pages are always minimally logged.</span></span> <span data-ttu-id="ecbdb-117">La manière dont les pages d'index sont journalisées dépend toutefois du remplissage de la table :</span><span class="sxs-lookup"><span data-stu-id="ecbdb-117">How index pages are logged, however, depends on whether the table is empty:</span></span>  
  
    -   <span data-ttu-id="ecbdb-118">Si la table est vide, les pages d'index bénéficient de la journalisation minimale.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-118">If the table is empty, index pages are minimally logged.</span></span>  
  
    -   <span data-ttu-id="ecbdb-119">Si la table n'est pas vide, les pages d'index bénéficient de la journalisation complète.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-119">If table is non-empty, index pages are fully logged.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="ecbdb-120">Si vous démarrez avec une table vide et importez les données en bloc en plusieurs traitements, les pages de données et d'index bénéficient de la journalisation minimale pour le premier traitement, mais à partir du deuxième traitement, seules les pages de données bénéficient de cette journalisation minimale.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-120">If you start with an empty table and bulk import the data in multiple batches, both index and data pages are minimally logged for the first batch, but beginning with the second batch, only data pages are minimally logged.</span></span>  
  
-   <span data-ttu-id="ecbdb-121">Si la table possède un index cluster et est vide, les pages de données et d'index bénéficient de la journalisation minimale.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-121">If the table has a clustered index and is empty, both data and index pages are minimally logged.</span></span> <span data-ttu-id="ecbdb-122">Par contre, si une table possède un index cluster et n'est pas vide, les pages de données et d'index bénéficient de la journalisation complète, quel que soit le mode de récupération choisi.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-122">In contrast, if a table has a clustered index and is non-empty, data pages and index pages are both fully logged regardless of the recovery model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ecbdb-123">Si vous démarrez avec une table vide et importez les données en bloc en plusieurs traitements, les pages de données et d'index bénéficient de la journalisation minimale pour le premier traitement, mais à partir du deuxième traitement, seules les pages de données bénéficient de la journalisation en bloc.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-123">If you start with an empty table and bulk import the data in batches, both index and data pages are minimally logged for the first batch, but from the second batch onwards, only data pages are bulk logged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ecbdb-124">Lorsque la réplication transactionnelle est activée, les opérations BULK INSERT sont entièrement journalisées, même dans le mode de récupération utilisant les journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="ecbdb-124">When transactional replication is enabled, BULK INSERT operations are fully logged even under the Bulk Logged recovery model.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ecbdb-125">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ecbdb-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ecbdb-126">Afficher ou modifier le mode de récupération d’une base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbdb-126">View or Change the Recovery Model of a Database &#40;SQL Server&#41;</span></span>](../backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="ecbdb-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ecbdb-127">See Also</span></span>  
 <span data-ttu-id="ecbdb-128">[Modes de récupération &#40;SQL Server&#41;](../backup-restore/recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ecbdb-128">[Recovery Models &#40;SQL Server&#41;](../backup-restore/recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="ecbdb-129">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ecbdb-129">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="ecbdb-130">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecbdb-130">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="ecbdb-131">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecbdb-131">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="ecbdb-132">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecbdb-132">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="ecbdb-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecbdb-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="ecbdb-134">[Indicateurs de table &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="ecbdb-134">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 [<span data-ttu-id="ecbdb-135">INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbdb-135">INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/insert-transact-sql)  
  
  
