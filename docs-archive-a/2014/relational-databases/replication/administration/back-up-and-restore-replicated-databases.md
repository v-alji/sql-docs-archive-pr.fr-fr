---
title: Sauvegarder et restaurer des bases de données répliquées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- backups [SQL Server replication]
- administering replication, restoring
- backing up replicated databases
- backups [SQL Server replication], about backups
- restoring replicated databases [SQL Server replication]
- recovery [SQL Server replication], about recovery
- restoring databases [SQL Server], replicated databases
- backing up databases [SQL Server], replicated databases
- restoring [SQL Server replication], about restoring
- recovery [SQL Server replication]
- replication [SQL Server], administering
- distribution databases [SQL Server replication], backing up
- restoring [SQL Server replication]
- administering replication, backing up
ms.assetid: 04588807-21e7-4bbe-9727-b72f692cffa7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e91505bacf67f7f4628bd1b3f6b2cc78a6bc4c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610615"
---
# <a name="back-up-and-restore-replicated-databases"></a><span data-ttu-id="94518-102">Sauvegarder et restaurer des bases de données répliquées</span><span class="sxs-lookup"><span data-stu-id="94518-102">Back Up and Restore Replicated Databases</span></span>
  <span data-ttu-id="94518-103">Les bases de données répliquées nécessitent une attention toute particulière en ce qui concerne la sauvegarde et la restauration de données.</span><span class="sxs-lookup"><span data-stu-id="94518-103">Replicated databases require special attention with regards to backing up and restoring data.</span></span> <span data-ttu-id="94518-104">Cette rubrique fournit des informations introductives et des liens vers des informations plus complètes sur les stratégies de sauvegarde et de restauration pour chaque type de réplication.</span><span class="sxs-lookup"><span data-stu-id="94518-104">This topic provides introductory information and links to further information on backup and restore strategies for each type of replication.</span></span>  
  
 <span data-ttu-id="94518-105">La réplication prend en charge la restauration de bases de données répliquées sur le même serveur et dans la même base de données à partir desquels la sauvegarde a été créée.</span><span class="sxs-lookup"><span data-stu-id="94518-105">Replication supports restoring replicated databases to the same server and database from which the backup was created.</span></span> <span data-ttu-id="94518-106">Si vous restaurez une sauvegarde d'une base de données répliquée sur un autre serveur ou dans une autre base de données, les paramètres de réplication ne peuvent pas être conservés.</span><span class="sxs-lookup"><span data-stu-id="94518-106">If you restore a backup of a replicated database to another server or database, replication settings cannot be preserved.</span></span> <span data-ttu-id="94518-107">Dans ce cas, vous devez recréer toutes les publications et tous les abonnements après la restauration des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="94518-107">In this case, you must recreate all publications and subscriptions after backups are restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94518-108">Il est possible de restaurer une base de données répliquée vers un serveur mis en veille à condition que la copie des journaux de transaction soit utilisée.</span><span class="sxs-lookup"><span data-stu-id="94518-108">It is possible to restore a replicated database to a standby server if log shipping is being used.</span></span> <span data-ttu-id="94518-109">Pour plus d’informations, consultez [Copie des journaux de transaction et réplication &#40;SQL Server&#41;](../../../database-engine/log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="94518-109">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../../../database-engine/log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="94518-110">Les bases de données répliquées et leurs bases de données système associées doivent être sauvegardées régulièrement.</span><span class="sxs-lookup"><span data-stu-id="94518-110">Replicated databases and their associated system databases should be backed up regularly.</span></span> <span data-ttu-id="94518-111">Sauvegardez les bases de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="94518-111">Back up the following databases:</span></span>  
  
-   <span data-ttu-id="94518-112">La base de données de publication au niveau du serveur de publication</span><span class="sxs-lookup"><span data-stu-id="94518-112">The publication database at the Publisher</span></span>  
  
-   <span data-ttu-id="94518-113">La base de données de distribution au niveau du serveur de distribution</span><span class="sxs-lookup"><span data-stu-id="94518-113">The distribution database at the Distributor</span></span>  
  
-   <span data-ttu-id="94518-114">La base de données d'abonnement sur chaque Abonné</span><span class="sxs-lookup"><span data-stu-id="94518-114">The subscription database at each Subscriber</span></span>  
  
-   <span data-ttu-id="94518-115">Bases de données système **master** et **msdb** sur le serveur de publication, sur le serveur de distribution et sur tous les Abonnés.</span><span class="sxs-lookup"><span data-stu-id="94518-115">The **master** and **msdb** system databases at the Publisher, Distributor and all Subscribers.</span></span> <span data-ttu-id="94518-116">Il est recommandé de sauvegarder ces bases de données en même temps, ainsi que la base de données de réplication appropriée.</span><span class="sxs-lookup"><span data-stu-id="94518-116">These databases should be backed up at the same time as each other and the relevant replication database.</span></span> <span data-ttu-id="94518-117">Par exemple, sauvegardez les bases de données **master** et **msdb** au niveau du serveur de publication en même temps que la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="94518-117">For example, back up the **master** and **msdb** databases at the Publisher at the same time you back up the publication database.</span></span> <span data-ttu-id="94518-118">Si la base de données de publication est restaurée, vérifiez que les bases de données **master** et **msdb** sont cohérentes avec la base de données de publication en termes de configuration de la réplication et de paramètres.</span><span class="sxs-lookup"><span data-stu-id="94518-118">If the publication database is restored, ensure that the **master** and **msdb** database are consistent with the publication database in terms of replication configuration and settings.</span></span>  
  
 <span data-ttu-id="94518-119">Si vous effectuez des sauvegardes régulières des journaux, toutes les modifications liées à la réplication doivent être capturées dans les sauvegardes des journaux.</span><span class="sxs-lookup"><span data-stu-id="94518-119">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="94518-120">Si vous n'effectuez pas de sauvegardes de fichiers journaux, une sauvegarde doit être effectuée chaque fois qu'une modification portant sur un paramètre de réplication a lieu.</span><span class="sxs-lookup"><span data-stu-id="94518-120">If you do not perform log backups, a backup should be performed whenever a setting relevant to replication is changed.</span></span> <span data-ttu-id="94518-121">Pour en savoir plus, voir [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span><span class="sxs-lookup"><span data-stu-id="94518-121">For more information, see [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span></span>  
  
## <a name="backup-and-restore-strategies"></a><span data-ttu-id="94518-122">Stratégies de sauvegarde et de restauration</span><span class="sxs-lookup"><span data-stu-id="94518-122">Backup and Restore Strategies</span></span>  
 <span data-ttu-id="94518-123">Les stratégies de sauvegarde et de restauration de chaque nœud d'une topologie de réplication sont différentes selon le type de réplication utilisé.</span><span class="sxs-lookup"><span data-stu-id="94518-123">The strategies for backing up and restoring each node in a replication topology differ according to the type of replication used.</span></span> <span data-ttu-id="94518-124">Pour plus d'informations sur les stratégies de sauvegarde et de restauration pour chaque type de réplication, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="94518-124">For information on backup and restore strategies for each type of replication, see the following topics:</span></span>  
  
-   [<span data-ttu-id="94518-125">Stratégies de sauvegarde et de restauration de la réplication transactionnelle et d’instantané</span><span class="sxs-lookup"><span data-stu-id="94518-125">Strategies for Backing Up and Restoring Snapshot and Transactional Replication</span></span>](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md)  
  
-   [<span data-ttu-id="94518-126">Stratégies de sauvegarde et de restauration de la réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="94518-126">Strategies for Backing Up and Restoring Merge Replication</span></span>](strategies-for-backing-up-and-restoring-merge-replication.md)  
  
 <span data-ttu-id="94518-127">Quelle que soit votre stratégie de récupération, conservez toujours dans un endroit sûr un script à jour de vos paramètres de réplication.</span><span class="sxs-lookup"><span data-stu-id="94518-127">As part of any recovery strategy, always keep a current script of your replication settings in a safe location.</span></span> <span data-ttu-id="94518-128">En cas de panne sur un serveur, ou si vous avez besoin de créer un environnement de test, vous pouvez modifier ce script en changeant des références de nom de serveur et l'utiliser pour recréer vos paramètres de réplication.</span><span class="sxs-lookup"><span data-stu-id="94518-128">In the event of server failure or the need to set up a test environment, you can modify the script by changing server name references, and it can be used to help recreate your replication settings.</span></span> <span data-ttu-id="94518-129">Outre vos paramètres de réplication courants, prévoyez d'intégrer dans un script l'activation et la désactivation de la réplication.</span><span class="sxs-lookup"><span data-stu-id="94518-129">In addition to scripting your current replication settings, you should script the enabling and disabling of replication.</span></span> <span data-ttu-id="94518-130">Pour plus d'informations sur les scripts d'objets de réplication, consultez [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="94518-130">For information about scripting replication objects, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94518-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94518-131">See Also</span></span>  
 <span data-ttu-id="94518-132">[Sauvegarde et restauration des bases de données SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="94518-132">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="94518-133">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="94518-133">Best Practices for Replication Administration</span></span>](best-practices-for-replication-administration.md)  
  
  
