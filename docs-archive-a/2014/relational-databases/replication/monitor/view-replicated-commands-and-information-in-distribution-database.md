---
title: Afficher les commandes répliquées et d’autres informations dans la base de données de distribution (programmation Transact-SQL de la réplication) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_browsereplcmds
- transactional replication, monitoring
- distribution databases [SQL Server replication], viewing replicated commands
- viewing replicated commands
ms.assetid: 9c20acec-8fab-4483-b9c1-dfe3768f85dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fb5850277d685f2ecf6471fa4bf9814579b2843e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709167"
---
# <a name="view-replicated-commands-and-other-information-in-the-distribution-database-replication-transact-sql-programming"></a><span data-ttu-id="e0121-102">Afficher les commandes répliquées et autres informations dans la base de données de distribution (programmation Transact-SQL de la réplication)</span><span class="sxs-lookup"><span data-stu-id="e0121-102">View Replicated Commands and Other Information in the Distribution Database (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="e0121-103">Lors de l'utilisation de la réplication transactionnelle, les commandes de transaction sont stockées dans la base de données de distribution jusqu'à ce que l'Agent de distribution les propage sur tous les Abonnés ou qu'un Agent de distribution sur l'Abonné extrait les modifications.</span><span class="sxs-lookup"><span data-stu-id="e0121-103">When using transactional replication, transaction commands are stored in the distribution database until the Distribution Agent propagates them to all Subscribers or a Distribution Agent at the Subscriber pulls the changes.</span></span> <span data-ttu-id="e0121-104">Ces commandes en attente dans la base de données de distribution peuvent être affichées par programmation à l'aide de procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="e0121-104">These pending commands in the distribution database can be viewed programmatically using replication stored procedures.</span></span> <span data-ttu-id="e0121-105">Pour plus d’informations, consultez [Procédures stockées de réplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e0121-105">For more information, see [Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-from-all-transactional-publications-in-the-distribution-database"></a><span data-ttu-id="e0121-106">Pour afficher les commandes répliquées de toutes les publications transactionnelles de la base de données de distribution</span><span class="sxs-lookup"><span data-stu-id="e0121-106">To view replicated commands from all transactional publications in the distribution database</span></span>  
  
1.  <span data-ttu-id="e0121-107">Sur la base de données de distribution du serveur de distribution, exécutez [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e0121-107">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-in-the-distribution-database-from-a-specific-article-or-from-a-specific-database-published-using-transactional-replication"></a><span data-ttu-id="e0121-108">Pour afficher les commandes répliquées de la base de données de distribution à partir d'un article spécifique ou d'une base de données spécifique publiée à l'aide de la réplication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="e0121-108">To view replicated commands in the distribution database from a specific article or from a specific database published using transactional replication</span></span>  
  
1.  <span data-ttu-id="e0121-109">(Facultatif) Sur la base de données de publication du serveur de publication, exécutez [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e0121-109">(Optional) At the Publisher on the publication database, execute [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql).</span></span> <span data-ttu-id="e0121-110">Spécifier une \*\* \@ publication\*\* et un \*\* \@ article\*\*.</span><span class="sxs-lookup"><span data-stu-id="e0121-110">Specify **\@publication** and **\@article**.</span></span> <span data-ttu-id="e0121-111">Notez la valeur de **article_id** dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="e0121-111">Note the value of **article id** in the result set.</span></span>  
  
2.  <span data-ttu-id="e0121-112">Sur la base de données de distribution du serveur de distribution, exécutez [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e0121-112">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span> <span data-ttu-id="e0121-113">Facultatif Spécifiez l’ID d’article de l’étape 2 pour \*\* \@ article_id\*\*.</span><span class="sxs-lookup"><span data-stu-id="e0121-113">(Optional) Specify the article ID from step 2 for **\@article_id**.</span></span> <span data-ttu-id="e0121-114">Facultatif Spécifiez l’ID de la base de données de publication pour \*\* \@ publisher_database_id\*\*, qui peut être obtenue à partir de la colonne **database_id** de l’affichage catalogue [sys. databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e0121-114">(Optional) Specify the ID of the publication database for **\@publisher_database_id**, which can be obtained from the **database_id** column in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0121-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0121-115">See Also</span></span>  
 [<span data-ttu-id="e0121-116">Surveiller la réplication par programmation</span><span class="sxs-lookup"><span data-stu-id="e0121-116">Programmatically Monitor Replication</span></span>](../monitoring-replication.md)  
  
  
