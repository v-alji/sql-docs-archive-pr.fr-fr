---
title: Gérer et surveiller la recherche sémantique | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], managing
- semantic search [SQL Server], monitoring
ms.assetid: eb5c3b29-da70-42aa-aa97-7d35a3f1eb98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16e3af1d37f177dfe6d4e0cb090e7b8b0a4988d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702595"
---
# <a name="manage-and-monitor-semantic-search"></a><span data-ttu-id="65d19-102">Gérer et surveiller la recherche sémantique</span><span class="sxs-lookup"><span data-stu-id="65d19-102">Manage and Monitor Semantic Search</span></span>
  <span data-ttu-id="65d19-103">Décrit le processus d'indexation sémantique et les tâches associées à la gestion et au contrôle des index.</span><span class="sxs-lookup"><span data-stu-id="65d19-103">Describes the process of semantic indexing and the tasks related to managing and monitoring the indexes.</span></span>  
  
##  <a name="how-to-check-the-status-of-semantic-indexing"></a><a name="HowToMonitorStatus"></a><span data-ttu-id="65d19-104">Procédure : vérifier l’état de l’indexation sémantique</span><span class="sxs-lookup"><span data-stu-id="65d19-104">How To: Check the Status of Semantic Indexing</span></span>  
 <span data-ttu-id="65d19-105">**La première phase de l'indexation sémantique est-elle achevée ?**</span><span class="sxs-lookup"><span data-stu-id="65d19-105">**Is the first phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="65d19-106">Interrogez la vue de gestion dynamique, [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql), et vérifiez les colonnes **status** et **status_description**.</span><span class="sxs-lookup"><span data-stu-id="65d19-106">Query the dynamic management view, [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql), and check the **status** and **status_description** columns.</span></span>  
  
 <span data-ttu-id="65d19-107">La première phase de l'indexation inclut l'alimentation de l'index de mots clés de recherche en texte intégral et de l'index d'expressions clés sémantiques, ainsi que l'extraction de données de ressemblance de document.</span><span class="sxs-lookup"><span data-stu-id="65d19-107">The first phase of indexing includes the population of the full-text keyword index and the semantic key phrase index, as well as the extraction of document similarity data.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_index_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="65d19-108">**La seconde phase de l'indexation sémantique est-elle achevée ?**</span><span class="sxs-lookup"><span data-stu-id="65d19-108">**Is the second phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="65d19-109">Interrogez la vue de gestion dynamique, [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql), et vérifiez les colonnes **status** et **status_description**.</span><span class="sxs-lookup"><span data-stu-id="65d19-109">Query the dynamic management view, [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql), and check the **status** and **status_description** columns..</span></span>  
  
 <span data-ttu-id="65d19-110">La deuxième phase de l'indexation inclut l'alimentation de l'index de ressemblance de document sémantique.</span><span class="sxs-lookup"><span data-stu-id="65d19-110">The second phase of indexing includes the population of the semantic document similarity index.</span></span>  
  
```wql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_semantic_similarity_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
##  <a name="how-to-check-the-size-of-the-semantic-indexes"></a><a name="HowToCheckSize"></a><span data-ttu-id="65d19-111">Procédure : vérifier la taille des index sémantiques</span><span class="sxs-lookup"><span data-stu-id="65d19-111">How To: Check the Size of the Semantic Indexes</span></span>  
 <span data-ttu-id="65d19-112">**Quelle est la taille logique d'un index d'expressions clés sémantiques ou d'un index de ressemblance de document sémantique ?**</span><span class="sxs-lookup"><span data-stu-id="65d19-112">**What is the logical size of a semantic key phrase index or a semantic document similarity index?**</span></span>  
 <span data-ttu-id="65d19-113">Interrogez la vue de gestion dynamique, [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65d19-113">Query the dynamic management view, [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="65d19-114">La taille logique est affichée en nombre de pages d'index.</span><span class="sxs-lookup"><span data-stu-id="65d19-114">The logical size is displayed in number of index pages.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_db_fts_index_physical_stats WHERE object_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="65d19-115">**Quelle est la taille totale des index sémantiques et de recherche en texte intégral pour un catalogue de texte intégral ?**</span><span class="sxs-lookup"><span data-stu-id="65d19-115">**What is the total size of the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="65d19-116">Interrogez la propriété **IndexSize** de la fonction de métadonnées [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65d19-116">Query the **IndexSize** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'IndexSize')  
GO  
```  
  
 <span data-ttu-id="65d19-117">**Combien d'éléments sont indexés dans les index sémantiques et de recherche en texte intégral pour un catalogue de texte intégral ?**</span><span class="sxs-lookup"><span data-stu-id="65d19-117">**How many items are indexed in the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="65d19-118">Interrogez la propriété **ItemCount** de la fonction de métadonnées [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65d19-118">Query the **ItemCount** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'ItemCount')  
GO  
```  
  
##  <a name="how-to-force-the-population-of-the-semantic-indexes"></a><a name="HowToForcePopulation"></a><span data-ttu-id="65d19-119">Procédure : forcer le remplissage des index sémantiques</span><span class="sxs-lookup"><span data-stu-id="65d19-119">How To: Force the Population of the Semantic Indexes</span></span>  
 <span data-ttu-id="65d19-120">Vous pouvez forcer le remplissage des index sémantiques et de recherche en texte intégral à l'aide de la clause START/STOP/PAUSE ou RESUME POPULATION avec la même syntaxe et le même comportement que ceux décrits pour les index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="65d19-120">You can force the population of full-text and semantic indexes by using the START/STOP/PAUSE or RESUME POPULATION clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="65d19-121">Pour plus d’informations, consultez [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) et [Alimenter des index de recherche en texte intégral](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="65d19-121">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) and [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="65d19-122">Étant donné que l'indexation sémantique dépend de l'indexation de texte intégral, les index sémantiques ne sont remplis que lorsque les index de recherche en texte intégral associés le sont également.</span><span class="sxs-lookup"><span data-stu-id="65d19-122">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="65d19-123">**Exemple : démarrer une alimentation complète des index sémantiques et de recherche en texte intégral**</span><span class="sxs-lookup"><span data-stu-id="65d19-123">**Example: Start a full population of full-text and semantic indexes**</span></span>  
  
 <span data-ttu-id="65d19-124">L’exemple suivant démarre une alimentation complète des index sémantiques et de recherche en texte intégral en modifiant un index de recherche en texte intégral existant sur la table **Production.Document** dans l’exemple de base de données AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="65d19-124">The following example starts full population of both full-text and semantic indexes by altering an existing full-text index on the **Production.Document** table in the AdventureWorks2012 sample database.</span></span>  
  
```vb  
USE AdventureWorks2012  
GO  
  
ALTER FULLTEXT INDEX ON Production.Document  
    START FULL POPULATION  
GO  
```  
  
##  <a name="how-to-disable-or-re-enable-semantic-indexing"></a><a name="HowToDisableIndexing"></a><span data-ttu-id="65d19-125">Procédure : désactiver ou réactiver l’indexation sémantique</span><span class="sxs-lookup"><span data-stu-id="65d19-125">How To: Disable or Re-enable Semantic Indexing</span></span>  
 <span data-ttu-id="65d19-126">Vous pouvez activer ou désactiver l'indexation sémantique ou de texte intégral à l'aide de la clause ENABLE/DISABLE avec la même syntaxe et le même comportement que ceux décrits pour les index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="65d19-126">You can enable or disable full-text or semantic indexing by using the ENABLE/DISABLE clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="65d19-127">Pour plus d’informations, consultez [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65d19-127">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="65d19-128">Lorsque l'indexation sémantique est désactivée et suspendue, les requêtes sur les données sémantiques continuent de s'exécuter avec succès et retournent des données indexées précédemment.</span><span class="sxs-lookup"><span data-stu-id="65d19-128">When semantic indexing is disabled and suspended, queries over semantic data continue to work successfully and to return previously indexed data.</span></span> <span data-ttu-id="65d19-129">Ce comportement n'est pas cohérent avec le comportement de la recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="65d19-129">This behavior is not consistent with the behavior of Full-Text Search.</span></span>  
  
```sql  
-- To disable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name DISABLE  
GO  
  
-- To re-enable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name ENABLE  
GO  
```  
  
##  <a name="phases-of-semantic-indexing"></a><a name="SemanticIndexing"></a><span data-ttu-id="65d19-130">Phases de l’indexation sémantique</span><span class="sxs-lookup"><span data-stu-id="65d19-130">Phases of Semantic Indexing</span></span>  
 <span data-ttu-id="65d19-131">Une recherche sémantique indexe deux types de données pour chaque colonne sur laquelle elle est activée :</span><span class="sxs-lookup"><span data-stu-id="65d19-131">Semantic Search indexes two kinds of data for each column on which it is enabled:</span></span>  
  
1.  <span data-ttu-id="65d19-132">**Phrases clés**</span><span class="sxs-lookup"><span data-stu-id="65d19-132">**Key phrases**</span></span>  
  
2.  <span data-ttu-id="65d19-133">**Ressemblance de document**</span><span class="sxs-lookup"><span data-stu-id="65d19-133">**Document similarity**</span></span>  
  
 <span data-ttu-id="65d19-134">L'indexation sémantique se produit en deux phases, conjointement à l'indexation de texte intégral :</span><span class="sxs-lookup"><span data-stu-id="65d19-134">Semantic indexing occurs in two phases, in conjunction with full-text indexing:</span></span>  
  
1.  <span data-ttu-id="65d19-135">**Phase 1**.</span><span class="sxs-lookup"><span data-stu-id="65d19-135">**Phase 1**.</span></span> <span data-ttu-id="65d19-136">L'index de mots clés de texte intégral et l'index d'expressions clés sémantiques sont remplis en même temps, en parallèle.</span><span class="sxs-lookup"><span data-stu-id="65d19-136">The full-text keyword index and the semantic key phrase index are populated in parallel at the same time.</span></span> <span data-ttu-id="65d19-137">Les données requises pour indexer la ressemblance de document sont également extraites à ce moment.</span><span class="sxs-lookup"><span data-stu-id="65d19-137">The data required to index document similarity is also extracted at this time.</span></span>  
  
2.  <span data-ttu-id="65d19-138">**Phase 2**.</span><span class="sxs-lookup"><span data-stu-id="65d19-138">**Phase 2**.</span></span> <span data-ttu-id="65d19-139">L'index de ressemblance de document sémantique est rempli à son tour.</span><span class="sxs-lookup"><span data-stu-id="65d19-139">The semantic document similarity index is then populated.</span></span> <span data-ttu-id="65d19-140">Cet index dépend des deux index remplis à la phase précédente.</span><span class="sxs-lookup"><span data-stu-id="65d19-140">This index depends on both indexes that were populated in the preceding phase.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-semantic-indexes-are-not-populated"></a><a name="ProblemNotPopulated"></a><span data-ttu-id="65d19-141">Problème : les index sémantiques ne sont pas remplis</span><span class="sxs-lookup"><span data-stu-id="65d19-141">Problem: Semantic Indexes Are Not Populated</span></span>  
 <span data-ttu-id="65d19-142">**Les index de recherche en texte intégral associés sont-ils remplis ?**</span><span class="sxs-lookup"><span data-stu-id="65d19-142">**Are the associated full-text indexes populated?**</span></span>  
 <span data-ttu-id="65d19-143">Étant donné que l'indexation sémantique dépend de l'indexation de texte intégral, les index sémantiques ne sont remplis que lorsque les index de recherche en texte intégral associés le sont également.</span><span class="sxs-lookup"><span data-stu-id="65d19-143">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="65d19-144">**La recherche en texte intégral et la recherche sémantique sont-elles installées et configurées correctement ?**</span><span class="sxs-lookup"><span data-stu-id="65d19-144">**Are full-text search and semantic search properly installed and configured?**</span></span>  
 <span data-ttu-id="65d19-145">Pour plus d’informations, consultez [Installer et configurer la recherche sémantique](install-and-configure-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="65d19-145">For more information, see [Install and Configure Semantic Search](install-and-configure-semantic-search.md).</span></span>  
  
 <span data-ttu-id="65d19-146">**Le service FDHOST est-il indisponible, ou existe-t-il une autre condition qui provoquerait l'échec de l'indexation de texte intégral ?**</span><span class="sxs-lookup"><span data-stu-id="65d19-146">**Is the FDHOST service not available, or is there another condition that would cause full-text indexing to fail?**</span></span>  
 <span data-ttu-id="65d19-147">Pour plus d’informations, consultez [Résoudre l’indexation de recherche en texte intégral](troubleshoot-full-text-indexing.md).</span><span class="sxs-lookup"><span data-stu-id="65d19-147">For more information, see [Troubleshoot Full-Text Indexing](troubleshoot-full-text-indexing.md).</span></span>  
  
  
