---
title: Activer les sauvegardes coordonnées pour la réplication transactionnelle (programmation Transact-SQL de la réplication) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, backup and restore
- sp_replicationdboption
- sync with backup [SQL Server replication]
- coordinated backups [SQL Server replication]
- backups [SQL Server replication], transactional replication
ms.assetid: 73a914ba-8b2d-4f4d-ac1b-db9bac676a30
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 77405cd968fa917c3ccc799eb7d168782443eee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709244"
---
# <a name="enable-coordinated-backups-for-transactional-replication-replication-transact-sql-programming"></a><span data-ttu-id="5d7ed-102">Activer les sauvegardes coordonnées pour la réplication transactionnelle (programmation Transact-SQL de la réplication)</span><span class="sxs-lookup"><span data-stu-id="5d7ed-102">Enable Coordinated Backups for Transactional Replication (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="5d7ed-103">Lorsque vous activez une base de données pour la réplication transactionnelle, vous pouvez spécifier que toutes les transactions doivent être sauvegardées avant d'être remises à la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-103">When enabling a database for transactional replication, you can specify that all transactions must be backed up before being delivered to the distribution database.</span></span> <span data-ttu-id="5d7ed-104">Vous pouvez activer la sauvegarde coordonnée également sur la base de données de distribution afin que le journal des transactions de la base de données de publication ne soit pas tronqué tant que les transactions qui ont été propagées sur le serveur de distribution n'ont pas été sauvegardées.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-104">You can also enable coordinated backup on the distribution database so that the transaction log for the publication database is not truncated until transactions that have been propagated to the Distributor have been backed up.</span></span> <span data-ttu-id="5d7ed-105">Pour plus d’informations, voir [Stratégies de sauvegarde et de restauration de la réplication transactionnelle et d'instantané](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-105">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-database-published-with-transactional-replication"></a><span data-ttu-id="5d7ed-106">Pour activer les sauvegardes coordonnées d'une base de données publiée avec la réplication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="5d7ed-106">To enable coordinated backups for a database published with transactional replication</span></span>  
  
1.  <span data-ttu-id="5d7ed-107">Sur le serveur de publication, utilisez la fonction [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) pour retourner la propriété **IsSyncWithBackup** de la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-107">At the Publisher, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the publication database.</span></span> <span data-ttu-id="5d7ed-108">Si la fonction retourne **1**, les sauvegardes coordonnées sont déjà activées pour la base de données publiée.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-108">If the function returns **1**, coordinated backups are already enabled for the published database.</span></span>  
  
2.  <span data-ttu-id="5d7ed-109">Si la fonction de l’étape 1 retourne **0**, exécutez [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) sur le serveur de publication de la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-109">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="5d7ed-110">Spécifiez la valeur **sync with backup** pour **\@optname** et **true** pour **\@value**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-110">Specify a value of **sync with backup** for **\@optname**, and **true** for **\@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5d7ed-111">Si vous modifiez l'option **sync with backup** en **false**, le point de troncation de la base de données de publication sera mis à jour après que l'Agent de lecture du journal se soit exécuté ou après un intervalle si l'Agent de lecture du journal s'exécute continuellement.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-111">If you change the **sync with backup** option to **false**, the truncation point of the publication database will be updated after the Log Reader Agent runs, or after an interval if the Log Reader Agent is running continuously.</span></span> <span data-ttu-id="5d7ed-112">L’intervalle maximal est contrôlé par le paramètre d’agent **-MessageInterval** (lequel a une valeur par défaut de 30 secondes).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-112">The maximum interval is controlled by the **-MessageInterval** agent parameter (which has a default of 30 seconds).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-distribution-database"></a><span data-ttu-id="5d7ed-113">Pour activer des sauvegardes coordonnées pour une base de données de distribution</span><span class="sxs-lookup"><span data-stu-id="5d7ed-113">To enable coordinated backups for a distribution database</span></span>  
  
1.  <span data-ttu-id="5d7ed-114">Sur le serveur de distribution, utilisez la fonction [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) pour retourner la propriété **IsSyncWithBackup** de la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-114">At the Distributor, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the distribution database.</span></span> <span data-ttu-id="5d7ed-115">Si la fonction retourne **1**, les sauvegardes coordonnées sont déjà activées pour la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-115">If the function returns **1**, coordinated backups are already enabled for the distribution database.</span></span>  
  
2.  <span data-ttu-id="5d7ed-116">Si la fonction de l’étape 1 retourne **0**, exécutez [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) sur le serveur de distribution de la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-116">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="5d7ed-117">Spécifiez la valeur **sync with backup** pour \*\* \@ nom_option\*\* et **true** pour \*\* \@ value\*\*.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-117">Specify a value of **sync with backup** for **\@optname** and **true** for **\@value**.</span></span>  
  
### <a name="to-disable-coordinated-backups"></a><span data-ttu-id="5d7ed-118">Pour désactiver les sauvegardes coordonnées</span><span class="sxs-lookup"><span data-stu-id="5d7ed-118">To disable coordinated backups</span></span>  
  
1.  <span data-ttu-id="5d7ed-119">Sur le serveur de publication de la base de données de publication ou sur le serveur de distribution de la base de données de distribution, exécutez [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5d7ed-119">At either the Publisher on the publication database or at the Distributor on the distribution database, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span></span> <span data-ttu-id="5d7ed-120">Spécifiez la valeur **sync with backup** pour **\@optname** et **false** pour **\@value**.</span><span class="sxs-lookup"><span data-stu-id="5d7ed-120">Specify a value of **sync with backup** for **\@optname** and **false** for **\@value**.</span></span>  
  
  
