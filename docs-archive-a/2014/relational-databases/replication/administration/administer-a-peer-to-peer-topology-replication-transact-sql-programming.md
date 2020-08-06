---
title: Administrer une topologie d’égal à égal (programmation Transact-SQL de la réplication) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, peer-to-peer replication
ms.assetid: 4d0fa941-f9ea-4a14-aed9-34df593fc6f2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a73af1c1f3a7196d87f77681ee9d62a3ef248a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603416"
---
# <a name="administer-a-peer-to-peer-topology-replication-transact-sql-programming"></a><span data-ttu-id="e40ec-102">Administrer une topologie d'égal à égal (programmation Transact-SQL de la réplication)</span><span class="sxs-lookup"><span data-stu-id="e40ec-102">Administer a Peer-to-Peer Topology (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="e40ec-103">L'administration d'une topologie d'égal à égal est semblable à celle d'une topologie de réplication transactionnelle typique, mais plusieurs zones méritent une attention particulière.</span><span class="sxs-lookup"><span data-stu-id="e40ec-103">Administering a peer-to-peer topology is similar to administering a typical transactional replication topology, but there are a number of areas with special considerations.</span></span> <span data-ttu-id="e40ec-104">La principale différence dans l'administration d'une topologie d'égal à égal est que certaines modifications requièrent que le système soit *suspendu*.</span><span class="sxs-lookup"><span data-stu-id="e40ec-104">The principal difference in administering a peer-to-peer topology is that some changes require the system to be *quiesced*.</span></span> <span data-ttu-id="e40ec-105">Suspendre un système revient à interrompre toute activité sur les tables publiées de tous les nœuds et à vérifier que chaque nœud a reçu toutes les modifications des autres nœuds.</span><span class="sxs-lookup"><span data-stu-id="e40ec-105">Quiescing a system involves stopping activity on published tables at all nodes and ensuring that each node has received all changes from all other nodes.</span></span> <span data-ttu-id="e40ec-106">Pour plus d’informations, consultez [Suspendre une topologie de réplication &#40;programmation Transact-SQL de la réplication&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="e40ec-106">For more information, see [Quiesce a Replication Topology &#40;Replication Transact-SQL Programming&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e40ec-107">Dans une topologie d'égal à égal, le serveur de distribution ne peut pas utiliser une version antérieure de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] par rapport à celle d'un abonné à un abonnement par extraction.</span><span class="sxs-lookup"><span data-stu-id="e40ec-107">In a peer-to-peer topology, the distributor cannot be using an earlier version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] than a pull subscriber.</span></span>  
  
### <a name="to-add-an-article-to-an-existing-configuration"></a><span data-ttu-id="e40ec-108">Pour ajouter un article à une configuration existante</span><span class="sxs-lookup"><span data-stu-id="e40ec-108">To add an article to an existing configuration</span></span>  
  
1.  <span data-ttu-id="e40ec-109">Suspendez le système.</span><span class="sxs-lookup"><span data-stu-id="e40ec-109">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="e40ec-110">Arrêtez l'Agent de distribution à chaque nœud de la topologie.</span><span class="sxs-lookup"><span data-stu-id="e40ec-110">Stop the Distribution Agent at each node in the topology.</span></span> <span data-ttu-id="e40ec-111">Pour plus d’informations, consultez [Concepts des exécutables de l’agent de réplication](../concepts/replication-agent-executables-concepts.md) ou [Démarrer et arrêter un Agent de réplication &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e40ec-111">For more information, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
3.  <span data-ttu-id="e40ec-112">Exécutez l'instruction CREATE TABLE pour ajouter la nouvelle table à chaque nœud de la topologie.</span><span class="sxs-lookup"><span data-stu-id="e40ec-112">Execute the CREATE TABLE statement to add the new table at each node in the topology.</span></span>  
  
4.  <span data-ttu-id="e40ec-113">Copiez manuellement en bloc les données de la nouvelle table sur tous les nœuds à l'aide de l' [utilitaire bcp](../../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="e40ec-113">Bulk copy the data for the new table manually at all nodes by using the [bcp utility](../../../tools/bcp-utility.md).</span></span>  
  
5.  <span data-ttu-id="e40ec-114">Exécutez [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) pour créer l'article sur chaque nœud de la topologie.</span><span class="sxs-lookup"><span data-stu-id="e40ec-114">Execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) to create the new article at each node in the topology.</span></span> <span data-ttu-id="e40ec-115">Pour plus d’informations, consultez [définir un Article](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="e40ec-115">For more information, see [Define an Article](../publish/define-an-article.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e40ec-116">Après l'exécution de [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) , la réplication ajoute automatiquement l'article aux abonnements de la topologie.</span><span class="sxs-lookup"><span data-stu-id="e40ec-116">After [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) is executed, replication automatically adds the article to the subscriptions in the topology.</span></span>  
  
6.  <span data-ttu-id="e40ec-117">Redémarrez les Agents de distribution sur chaque nœud de la topologie.</span><span class="sxs-lookup"><span data-stu-id="e40ec-117">Restart the Distribution Agents at each node in the topology.</span></span>  
  
### <a name="to-make-schema-changes-to-a-publication-database"></a><span data-ttu-id="e40ec-118">Pour apporter des modifications de schéma à une base de données de publication</span><span class="sxs-lookup"><span data-stu-id="e40ec-118">To make schema changes to a publication database</span></span>  
  
1.  <span data-ttu-id="e40ec-119">Suspendez le système.</span><span class="sxs-lookup"><span data-stu-id="e40ec-119">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="e40ec-120">Exécutez les instructions de langage de définition de données (DDL) pour modifier le schéma des tables publiées.</span><span class="sxs-lookup"><span data-stu-id="e40ec-120">Execute the data definition language (DDL) statements to modify the schema of published tables.</span></span> <span data-ttu-id="e40ec-121">Pour plus d’informations sur les modifications de schéma prises en charge, consultez [Modifier le schéma dans les bases de données de publication](../publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e40ec-121">For more information about supported schema changes, see [Make Schema Changes on Publication Databases](../publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
3.  <span data-ttu-id="e40ec-122">Avant de reprendre l'activité sur les tables publiées, suspendez à nouveau le système.</span><span class="sxs-lookup"><span data-stu-id="e40ec-122">Before you resume activity on published tables, quiesce the system again.</span></span> <span data-ttu-id="e40ec-123">Vous garantissez ainsi que les modifications de schéma ont été reçues par tous les nœuds avant que de nouvelles modifications de données ne soient répliquées.</span><span class="sxs-lookup"><span data-stu-id="e40ec-123">This ensures that schema changes have been received by all nodes before any new data changes are replicated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e40ec-124">Exemple</span><span class="sxs-lookup"><span data-stu-id="e40ec-124">Example</span></span>  
 <span data-ttu-id="e40ec-125">L'exemple suivant montre comment ajouter un nouvel article de table à une topologie existante de réplication d'égal à égal et composée de deux nœuds.</span><span class="sxs-lookup"><span data-stu-id="e40ec-125">The following example demonstrates how to add a new table article to an existing peer-to-peer replication topology that has two nodes.</span></span>  
  
 [!code-sql[HowTo#sp_addp2particle_createtables](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createtables)]  
  
 [!code-sql[HowTo#sp_addp2particle_cmdline](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_cmdline)]  
  
 [!code-sql[HowTo#sp_addp2particle_createarticle](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createarticle)]  
  
## <a name="see-also"></a><span data-ttu-id="e40ec-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e40ec-126">See Also</span></span>  
 <span data-ttu-id="e40ec-127">[FAQ sur l’administration de la réplication](frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="e40ec-127">[Replication Administration FAQ](frequently-asked-questions-for-replication-administrators.md) </span></span>  
 <span data-ttu-id="e40ec-128">[Sauvegarde et restauration des bases de données SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="e40ec-128">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="e40ec-129">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="e40ec-129">Peer-to-Peer Transactional Replication</span></span>](../transactional/peer-to-peer-transactional-replication.md)  
  
  
