---
title: Recherche sémantique (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server]
- semantic search [SQL Server], overview
- statistical semantic search [SQL Server]
- statistical semantic search [SQL Server], overview
ms.assetid: cd8faa9d-07db-420d-93f4-a2ea7c974b97
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 91062864b77ba3c62a87d66b8ff93068f9c10c8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704012"
---
# <a name="semantic-search-sql-server"></a><span data-ttu-id="31efe-102">Recherche sémantique (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="31efe-102">Semantic Search (SQL Server)</span></span>
  <span data-ttu-id="31efe-103">La recherche sémantique statistique donne un éclairage sur des documents non structurés stockés dans des bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en extrayant et en indexant des *expressions clés*statistiquement pertinentes.</span><span class="sxs-lookup"><span data-stu-id="31efe-103">Statistical Semantic Search provides deep insight into unstructured documents stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases by extracting and indexing statistically relevant *key phrases*.</span></span> <span data-ttu-id="31efe-104">Elle utilise également ces expressions clés pour identifier et indexer des *documents similaires ou connexes*.</span><span class="sxs-lookup"><span data-stu-id="31efe-104">Then it also uses these key phrases to identify and index *documents that are similar or related*.</span></span>  
  
 <span data-ttu-id="31efe-105">Vous pouvez interroger ces index sémantiques à l'aide de trois fonctions d'ensemble de lignes Transact-SQL pour récupérer les résultats sous forme de données structurées.</span><span class="sxs-lookup"><span data-stu-id="31efe-105">You query these semantic indexes by using three Transact-SQL rowset functions to retrieve the results as structured data.</span></span>  
  
##  <a name="what-can-i-do-with-semantic-search"></a><a name="whatcanido"></a><span data-ttu-id="31efe-106">Que puis-je faire avec la recherche sémantique ?</span><span class="sxs-lookup"><span data-stu-id="31efe-106">What Can I Do with Semantic Search?</span></span>  
 <span data-ttu-id="31efe-107">La recherche sémantique s'appuie sur la fonctionnalité de recherche en texte intégral existante dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mais permet de nouveaux scénarios qui vont au-delà des recherches par mot clé.</span><span class="sxs-lookup"><span data-stu-id="31efe-107">Semantic search builds upon the existing full-text search feature in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but enables new scenarios that extend beyond keyword searches.</span></span> <span data-ttu-id="31efe-108">Tandis que la recherche en texte intégral vous permet d’interroger des *mots* dans un document, la recherche sémantique porte sur la *signification* du document.</span><span class="sxs-lookup"><span data-stu-id="31efe-108">While full-text search lets you query the *words* in a document, semantic search lets you query the *meaning* of the document.</span></span> <span data-ttu-id="31efe-109">Les solutions désormais possibles incluent l'extraction automatique de balises, la découverte de contenu connexe et la navigation hiérarchique à travers du contenu similaire.</span><span class="sxs-lookup"><span data-stu-id="31efe-109">Solutions that are now possible include automatic tag extraction, related content discovery, and hierarchical navigation across similar content.</span></span> <span data-ttu-id="31efe-110">Par exemple, vous pouvez interroger l'index d'expressions clés afin de générer la taxonomie d'une organisation ou d'un corpus de documents.</span><span class="sxs-lookup"><span data-stu-id="31efe-110">For example, you can query the index of key phrases to build the taxonomy for an organization, or for a corpus of documents.</span></span> <span data-ttu-id="31efe-111">Ou encore interroger l'index de ressemblance de document pour identifier des curriculum vitae qui correspondent à une description de poste.</span><span class="sxs-lookup"><span data-stu-id="31efe-111">Or, you can query the document similarity index to identify resumes that match a job description.</span></span>  
  
 <span data-ttu-id="31efe-112">Les exemples qui suivent illustrent les fonctions de la recherche sémantique.</span><span class="sxs-lookup"><span data-stu-id="31efe-112">The following examples demonstrate the capabilities of Semantic Search.</span></span>  
  
###  <a name="find-the-key-phrases-in-a-document"></a><a name="find1"></a><span data-ttu-id="31efe-113">Rechercher les expressions clés dans un document</span><span class="sxs-lookup"><span data-stu-id="31efe-113">Find the Key Phrases in a Document</span></span>  
 <span data-ttu-id="31efe-114">La requête suivante obtient les expressions clés qui ont été identifiées dans le document témoin.</span><span class="sxs-lookup"><span data-stu-id="31efe-114">The following query gets the key phrases that were identified in the sample document.</span></span> <span data-ttu-id="31efe-115">Elle présente les résultats par ordre décroissant du score qui indique l'importance statistique de chaque expression clé.</span><span class="sxs-lookup"><span data-stu-id="31efe-115">It presents the results in descending order by the score that ranks the statistical significance of each key phrase.</span></span> <span data-ttu-id="31efe-116">Cette requête appelle la fonction [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="31efe-116">This query calls the [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql) function.</span></span>  
  
```sql  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS Title, keyphrase, score  
    FROM SEMANTICKEYPHRASETABLE(Documents, *, @DocID)  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-similar-or-related-documents"></a><a name="find2"></a><span data-ttu-id="31efe-117">Rechercher des documents similaires ou connexes</span><span class="sxs-lookup"><span data-stu-id="31efe-117">Find Similar or Related Documents</span></span>  
 <span data-ttu-id="31efe-118">La requête suivante obtient les documents qui ont été identifiés comme similaires ou en rapport avec le document témoin.</span><span class="sxs-lookup"><span data-stu-id="31efe-118">The following query gets the documents that were identified as similar or related to the sample document.</span></span> <span data-ttu-id="31efe-119">Elle présente les résultats par ordre décroissant du score qui indique la similarité des deux documents.</span><span class="sxs-lookup"><span data-stu-id="31efe-119">It presents the results in descending order by the score that ranks the similarity of the 2 documents.</span></span> <span data-ttu-id="31efe-120">Cette requête appelle la fonction [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="31efe-120">This query calls the [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql) function.</span></span>  
  
```vb  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS SourceTitle, DocumentTitle AS MatchedTitle,  
        DocumentID, score  
    FROM SEMANTICSIMILARITYTABLE(Documents, *, @DocID)  
    INNER JOIN Documents ON DocumentID = matched_document_key  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-the-key-phrases-that-make-documents-similar-or-related"></a><a name="find3"></a><span data-ttu-id="31efe-121">Rechercher les expressions clés qui rendent des documents similaires ou connexes</span><span class="sxs-lookup"><span data-stu-id="31efe-121">Find the Key Phrases That Make Documents Similar or Related</span></span>  
 <span data-ttu-id="31efe-122">La requête suivante obtient les expressions clés qui rendent les deux documents témoin similaires ou en rapport avec un autre.</span><span class="sxs-lookup"><span data-stu-id="31efe-122">The following query gets the key phrases that make the 2 sample documents similar or related to one another.</span></span> <span data-ttu-id="31efe-123">Elle présente les résultats par ordre décroissant du score qui indique le poids de chaque expression clé.</span><span class="sxs-lookup"><span data-stu-id="31efe-123">It presents the results in descending order by the score that ranks the weight of each key phrase.</span></span> <span data-ttu-id="31efe-124">Cette requête appelle la fonction [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="31efe-124">This query calls the [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql) function.</span></span>  
  
```sql  
SET @SourceTitle = 'first.docx'  
SET @MatchedTitle = 'second.docx'  
  
SELECT @SourceDocID = DocumentID FROM Documents WHERE DocumentTitle = @SourceTitle  
SELECT @MatchedDocID = DocumentID FROM Documents WHERE DocumentTitle = @MatchedTitle  
  
SELECT @SourceTitle AS SourceTitle, @MatchedTitle AS MatchedTitle, keyphrase, score  
    FROM semanticsimilaritydetailstable(Documents, DocumentContent,  
        @SourceDocID, DocumentContent, @MatchedDocID)  
    ORDER BY score DESC  
  
```  
  
  
  
##  <a name="storing-documents-in-sql-server"></a><a name="store"></a><span data-ttu-id="31efe-125">Stockage de documents dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="31efe-125">Storing Documents in SQL Server</span></span>  
 <span data-ttu-id="31efe-126">Avant de pouvoir indexer les documents avec la recherche sémantique, vous devez les stocker dans une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31efe-126">Before you can index documents with Semantic Search, you have to store the documents in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="31efe-127">La fonctionnalité FileTable dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] fait des documents et des fichiers non structurés des éléments de premier ordre de la base de données relationnelle.</span><span class="sxs-lookup"><span data-stu-id="31efe-127">The FileTable feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] makes unstructured files and documents first-class citizens of the relational database.</span></span> <span data-ttu-id="31efe-128">Par conséquent, les développeurs de base de données peuvent manipuler des documents avec des données structurées dans les opérations reposant sur des ensembles Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="31efe-128">As a result, database developers can manipulate documents together with structured data in Transact-SQL set-based operations.</span></span>  
  
 <span data-ttu-id="31efe-129">Pour plus d’informations sur la fonctionnalité FileTable, consultez [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="31efe-129">For more information about the FileTable feature, see [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span></span> <span data-ttu-id="31efe-130">Pour plus d’informations sur la fonctionnalité FILESTREAM, qui est une autre option pour stocker des documents dans la base de données, consultez [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="31efe-130">For information about the FILESTREAM feature, which is another option for storing documents in the database, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="31efe-131">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="31efe-131">Related Tasks</span></span>  
 [<span data-ttu-id="31efe-132">Installer et configurer la recherche sémantique</span><span class="sxs-lookup"><span data-stu-id="31efe-132">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)  
 <span data-ttu-id="31efe-133">Décrit les conditions préalables à une recherche sémantique statistique, ainsi que la procédure d'installation ou de vérification de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="31efe-133">Describes the prerequisites for statistical semantic search and how to install or check them.</span></span>  
  
 [<span data-ttu-id="31efe-134">Activer la recherche sémantique sur les tables et les colonnes</span><span class="sxs-lookup"><span data-stu-id="31efe-134">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)  
 <span data-ttu-id="31efe-135">Décrit la procédure d'activation ou de désactivation de l'indexation sémantique statistique sur des colonnes sélectionnées qui contiennent des documents ou du texte.</span><span class="sxs-lookup"><span data-stu-id="31efe-135">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 [<span data-ttu-id="31efe-136">Rechercher des expressions clés dans les documents avec la recherche sémantique</span><span class="sxs-lookup"><span data-stu-id="31efe-136">Find Key Phrases in Documents with Semantic Search</span></span>](find-key-phrases-in-documents-with-semantic-search.md)  
 <span data-ttu-id="31efe-137">Explique comment rechercher des expressions clés dans des documents ou des colonnes de texte configurés pour l'indexation sémantique statistique.</span><span class="sxs-lookup"><span data-stu-id="31efe-137">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="31efe-138">Rechercher des documents similaires ou connexes avec la recherche sémantique</span><span class="sxs-lookup"><span data-stu-id="31efe-138">Find Similar and Related Documents with Semantic Search</span></span>](find-similar-and-related-documents-with-semantic-search.md)  
 <span data-ttu-id="31efe-139">Explique comment rechercher des valeurs textuelles ou des documents similaires ou connexes et donne des informations sur leur similitude, dans des colonnes configurées pour l'indexation sémantique statistique.</span><span class="sxs-lookup"><span data-stu-id="31efe-139">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="31efe-140">Gérer et surveiller la recherche sémantique</span><span class="sxs-lookup"><span data-stu-id="31efe-140">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)  
 <span data-ttu-id="31efe-141">Décrit le processus d'indexation sémantique et les tâches associées à l'analyse et à la gestion des index.</span><span class="sxs-lookup"><span data-stu-id="31efe-141">Describes the process of semantic indexing and the tasks related to monitoring and managing the indexes.</span></span>  
  
##  <a name="related-content"></a><a name="relcontent"></a> <span data-ttu-id="31efe-142">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="31efe-142">Related Content</span></span>  
 [<span data-ttu-id="31efe-143">DDL, fonctions, procédures stockées et vues de recherche sémantique</span><span class="sxs-lookup"><span data-stu-id="31efe-143">Semantic Search DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
 <span data-ttu-id="31efe-144">Répertorie les instructions Transact-SQL et les objets de base de données SQL Server ajoutés ou modifiés pour prendre en charge la recherche sémantique statistique.</span><span class="sxs-lookup"><span data-stu-id="31efe-144">Lists the Transact-SQL statements and the SQL Server database objects added or changed to support statistical semantic search.</span></span>  
  
  
