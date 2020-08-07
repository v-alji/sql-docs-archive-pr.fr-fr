---
title: Basculer vers une base de données secondaire de copie des journaux de transaction (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server]
- secondary data files [SQL Server], manual fail over
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: edfe5d59-4287-49c1-96c9-dd56212027bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 164e2809e4eff5a14ef54124df7c7ca9077793ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703251"
---
# <a name="fail-over-to-a-log-shipping-secondary-sql-server"></a><span data-ttu-id="f34c8-102">Basculer vers une base de données secondaire de copie des journaux de transaction (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f34c8-102">Fail Over to a Log Shipping Secondary (SQL Server)</span></span>
  <span data-ttu-id="f34c8-103">Le basculement vers une base de données secondaire de copie des journaux de transactions est utile en cas d'échec ou d'un besoin de maintenance de l'instance du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="f34c8-103">Failing over to a log shipping secondary is useful if the primary server instance fails or requires maintenance.</span></span>  
  
## <a name="preparing-for-a-controlled-failover"></a><span data-ttu-id="f34c8-104">Préparation en vue d'un basculement contrôlé</span><span class="sxs-lookup"><span data-stu-id="f34c8-104">Preparing for a Controlled Failover</span></span>  
 <span data-ttu-id="f34c8-105">En règle générale, les bases de données primaire et secondaire ne sont pas synchronisées, car la base de données primaire est en permanence mise à jour après son dernier travail de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f34c8-105">Typically, the primary and secondary databases are unsynchronized, because the primary database continues to be updated after its latest backup job.</span></span> <span data-ttu-id="f34c8-106">De même, dans certains cas, les sauvegardes récentes du journal des transactions n'ont pas été copiées dans les instances du serveur secondaire ou certaines copies des sauvegardes du journal n'ont peut-être pas encore été appliquées dans la base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="f34c8-106">Also, in some cases, recent transaction log backups have not been copied to the secondary server instances, or some copied log backups might still not have been applied to the secondary database.</span></span> <span data-ttu-id="f34c8-107">Si possible, nous vous recommandons de commencer par synchroniser l'ensemble des bases de données secondaires avec la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="f34c8-107">We recommend that you begin by synchronizing all of the secondary databases with the primary database, if possible.</span></span>  
  
 <span data-ttu-id="f34c8-108">Pour plus d’informations sur l’opération de copie des journaux de transaction, consultez [À propos de la copie des journaux de transaction &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f34c8-108">For information about log shipping jobs, see [About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span></span>  
  
## <a name="failing-over"></a><span data-ttu-id="f34c8-109">Basculement</span><span class="sxs-lookup"><span data-stu-id="f34c8-109">Failing Over</span></span>  
 <span data-ttu-id="f34c8-110">Pour basculer vers une base de données secondaire :</span><span class="sxs-lookup"><span data-stu-id="f34c8-110">To fail over to a secondary database:</span></span>  
  
1.  <span data-ttu-id="f34c8-111">Copiez tous les fichiers de sauvegarde non copiés du partage de sauvegarde vers le dossier de destination de copie de chaque serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="f34c8-111">Copy any uncopied backup files from the backup share to the copy destination folder of each secondary server.</span></span>  
  
2.  <span data-ttu-id="f34c8-112">Appliquez à la suite toutes les sauvegardes non appliquées du journal des transactions à chaque base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="f34c8-112">Apply any unapplied transaction log backups in sequence to each secondary database.</span></span> <span data-ttu-id="f34c8-113">Pour plus d’informations, consultez [Appliquer les sauvegardes du journal de transactions &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f34c8-113">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="f34c8-114">Si la base de données primaire est accessible, sauvegardez le journal des transactions actif et appliquez la sauvegarde du journal aux bases de données secondaires.</span><span class="sxs-lookup"><span data-stu-id="f34c8-114">If the primary database is accessible, back up the active transaction log and apply the log backup to the secondary databases.</span></span>  
  
     <span data-ttu-id="f34c8-115">Si l'instance du serveur principal d'origine n'est pas endommagée, sauvegardez la fin du journal des transactions de la base de données primaire à l'aide de l'option WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="f34c8-115">If the original primary server instance is not damaged, back up the tail of the transaction log of the primary database using WITH NORECOVERY.</span></span> <span data-ttu-id="f34c8-116">Cette opération laisse la base de données en état de restauration et donc inaccessible aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f34c8-116">This leaves the database in the restoring state and therefore unavailable to users.</span></span> <span data-ttu-id="f34c8-117">Par la suite, vous pouvez la restaurer par progression en appliquant les sauvegardes du journal des transactions à partir de la base de données primaire de remplacement.</span><span class="sxs-lookup"><span data-stu-id="f34c8-117">Eventually you will be able to roll this database forward by applying transaction log backups from the replacement primary database.</span></span>  
  
     <span data-ttu-id="f34c8-118">Pour plus d’informations, consultez [Sauvegardes du journal des transactions &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f34c8-118">For more information, see [Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="f34c8-119">Une fois que les serveurs secondaires sont synchronisés, vous pouvez basculer vers celui de votre choix en récupérant sa base de données secondaire et en redirigeant des clients vers cette instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="f34c8-119">After the secondary servers are synchronized, you can fail over to whichever one you prefer by recovering its secondary database and redirecting clients to that server instance.</span></span> <span data-ttu-id="f34c8-120">La récupération place la base de données dans un état cohérent et permet sa mise en ligne.</span><span class="sxs-lookup"><span data-stu-id="f34c8-120">Recovering puts the database into a consistent state and brings it online.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f34c8-121">Lorsque vous rendez une base de données secondaire disponible, vous devez vous assurer que ses métadonnées sont cohérentes avec celles de la base de données primaire d'origine.</span><span class="sxs-lookup"><span data-stu-id="f34c8-121">When you make a secondary database available, you should ensure that its metadata is consistent with the metadata of the original primary database.</span></span> <span data-ttu-id="f34c8-122">Pour plus d’informations, consultez [Gérer les métadonnées durant la mise à disposition d’une base de données sur une autre instance de serveur &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="f34c8-122">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
5.  <span data-ttu-id="f34c8-123">Une fois que vous avez récupéré une base de données secondaire, vous pouvez la reconfigurer en tant que base de données primaire pour d'autres bases de données secondaires.</span><span class="sxs-lookup"><span data-stu-id="f34c8-123">After you have recovered a secondary database, you can reconfigure it to act as a primary database for other secondary databases.</span></span>  
  
     <span data-ttu-id="f34c8-124">Si aucune autre base de données secondaire n’est disponible, consultez [Configurer la copie des journaux de transaction &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f34c8-124">If no other secondary database is available, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f34c8-125">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="f34c8-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f34c8-126">Changer des rôles entre les serveurs primaire et secondaire de copie des journaux de transaction &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f34c8-126">Change Roles Between Primary and Secondary Log Shipping Servers &#40;SQL Server&#41;</span></span>](change-roles-between-primary-and-secondary-log-shipping-servers-sql-server.md)  
  
-   [<span data-ttu-id="f34c8-127">Gestion des connexions et des travaux après un basculement de rôle &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f34c8-127">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="f34c8-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f34c8-128">See Also</span></span>  
 <span data-ttu-id="f34c8-129">[Tables et procédures stockées liées à la copie des journaux de transaction](log-shipping-tables-and-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="f34c8-129">[Log Shipping Tables and Stored Procedures](log-shipping-tables-and-stored-procedures.md) </span></span>  
 <span data-ttu-id="f34c8-130">[À propos de la copie des journaux des transactions &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f34c8-130">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="f34c8-131">Sauvegardes de la fin du journal &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f34c8-131">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/tail-log-backups-sql-server.md)  
  
  
