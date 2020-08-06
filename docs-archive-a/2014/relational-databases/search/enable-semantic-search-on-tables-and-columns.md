---
title: Activer la recherche sémantique sur les tables et les colonnes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], enabling
ms.assetid: 895d220c-6749-4954-9dd3-2ea4c6a321ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f11ba654f7cc34f521990e8c420d41885d3c55b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702644"
---
# <a name="enable-semantic-search-on-tables-and-columns"></a><span data-ttu-id="467c2-102">Activer la recherche sémantique sur les tables et les colonnes</span><span class="sxs-lookup"><span data-stu-id="467c2-102">Enable Semantic Search on Tables and Columns</span></span>
  <span data-ttu-id="467c2-103">Décrit la procédure d'activation ou de désactivation de l'indexation sémantique statistique sur des colonnes sélectionnées qui contiennent des documents ou du texte.</span><span class="sxs-lookup"><span data-stu-id="467c2-103">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 <span data-ttu-id="467c2-104">La recherche sémantique statistique utilise les index créés par la recherche en texte intégral et crée des index supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="467c2-104">Statistical Semantic Search uses the indexes that are created by Full-Text Search, and creates additional indexes.</span></span> <span data-ttu-id="467c2-105">Conséquence de cette dépendance sur la recherche en texte intégral, vous créez un index sémantique lorsque vous définissez un nouvel index de recherche en texte intégral ou lorsque vous modifiez un index de recherche en texte intégral existant.</span><span class="sxs-lookup"><span data-stu-id="467c2-105">As a result of this dependency on full-text search, you create a new semantic index when you define a new full-text index, or when you alter an existing full-text index.</span></span> <span data-ttu-id="467c2-106">Vous pouvez créer un index sémantique à l'aide d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] ou en utilisant l'Assistant Indexation de texte intégral et d'autres boîtes de dialogue de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], comme décrit dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="467c2-106">You can create a new semantic index by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or by using the Full-Text Indexing Wizard and other dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as described in this topic.</span></span>  
  
##  <a name="creating-a-semantic-index"></a><a name="BasicEnabling"></a><span data-ttu-id="467c2-107">Création d’un index sémantique</span><span class="sxs-lookup"><span data-stu-id="467c2-107">Creating a Semantic Index</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-semantic-index"></a><a name="reqenable"></a><span data-ttu-id="467c2-108">Exigences et restrictions relatives à la création d’un index sémantique</span><span class="sxs-lookup"><span data-stu-id="467c2-108">Requirements and Restrictions for Creating a Semantic Index</span></span>  
  
-   <span data-ttu-id="467c2-109">Vous pouvez créer un index sur des objets de base de données pris en charge pour l'indexation de texte intégral, notamment les tables et les vues indexées.</span><span class="sxs-lookup"><span data-stu-id="467c2-109">You can create an index on any of the database objects that are supported for full-text indexing, including tables and indexed views.</span></span>  
  
-   <span data-ttu-id="467c2-110">Avant de pouvoir activer l'indexation sémantique pour des colonnes spécifiques, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="467c2-110">Before you can enable semantic indexing for specific columns, the following prerequisites must exist:</span></span>  
  
    -   <span data-ttu-id="467c2-111">Un catalogue de texte intégral doit exister pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="467c2-111">A full-text catalog must exist for the database.</span></span>  
  
    -   <span data-ttu-id="467c2-112">La table doit avoir un index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-112">The table must have a full-text index.</span></span>  
  
    -   <span data-ttu-id="467c2-113">Les colonnes sélectionnées doivent participer à l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-113">The selected columns must participate in the full-text index.</span></span>  
  
     <span data-ttu-id="467c2-114">Vous pouvez créer et activer toutes ces conditions préalables en même temps.</span><span class="sxs-lookup"><span data-stu-id="467c2-114">You can create and enable all these requirements at the same time.</span></span>  
  
-   <span data-ttu-id="467c2-115">Vous pouvez créer un index sémantique sur des colonnes présentant l'un des types de données pris en charge pour l'indexation de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-115">You can create a semantic index on columns that have any of the data types that are supported for full-text indexing.</span></span> <span data-ttu-id="467c2-116">Pour plus d’informations, consultez [Créer et gérer des index de recherche en texte intégral](create-and-manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="467c2-116">For more information, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md).</span></span>  
  
-   <span data-ttu-id="467c2-117">Vous pouvez spécifier tout type de document pris en charge pour l'indexation de texte intégral pour des colonnes `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="467c2-117">You can specify any document type that is supported for full-text indexing for `varbinary(max)` columns.</span></span> <span data-ttu-id="467c2-118">Pour plus d'informations, consultez [Procédure : déterminer les types de documents pouvant être indexés](#doctypes) dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="467c2-118">For more information, see [How To: Determine Which Document Types Can Be Indexed](#doctypes) in this topic.</span></span>  
  
-   <span data-ttu-id="467c2-119">L’indexation sémantique crée deux types d’index pour les colonnes que vous sélectionnez : un index d’expressions clés et un index de similarité de document.</span><span class="sxs-lookup"><span data-stu-id="467c2-119">Semantic indexing creates two types of indexes for the columns that you select - an index of key phrases, and an index of document similarity.</span></span> <span data-ttu-id="467c2-120">Vous ne pouvez pas sélectionner un seul type d'index lorsque vous activez l'indexation sémantique.</span><span class="sxs-lookup"><span data-stu-id="467c2-120">You cannot select only one type of index or the other when you enable semantic indexing.</span></span> <span data-ttu-id="467c2-121">En revanche, vous interroger ces deux index de manière indépendante.</span><span class="sxs-lookup"><span data-stu-id="467c2-121">However you can query these two indexes independently.</span></span> <span data-ttu-id="467c2-122">Pour plus d’informations, consultez [Rechercher des expressions clés dans les documents avec la recherche sémantique](find-key-phrases-in-documents-with-semantic-search.md) et [Rechercher des documents similaires ou connexes avec la recherche sémantique](find-similar-and-related-documents-with-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="467c2-122">For more information, see [Find Key Phrases in Documents with Semantic Search](find-key-phrases-in-documents-with-semantic-search.md) and [Find Similar and Related Documents with Semantic Search](find-similar-and-related-documents-with-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="467c2-123">Si vous ne spécifiez pas de LCID explicitement pour un index sémantique, seules la langue principale et ses statistiques linguistiques associées sont utilisées pour l'indexation sémantique.</span><span class="sxs-lookup"><span data-stu-id="467c2-123">If you do not explicitly specify an LCID for a semantic index, then only the primary language and its associated language statistics are used for semantic indexing.</span></span>  
  
-   <span data-ttu-id="467c2-124">Si vous spécifiez une langue pour une colonne pour laquelle le modèle linguistique n'est pas disponible, la création de l'index échoue et retourne un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="467c2-124">If you specify a language for a column for which the language model is not available, the creation of the index fails and returns an error message.</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-no-full-text-index"></a><a name="HowToEnableCreate"></a><span data-ttu-id="467c2-125">Procédure : créer un index sémantique lorsqu’il n’y a pas d’index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="467c2-125">How To: Create a Semantic Index When There Is No Full-Text Index</span></span>  
 <span data-ttu-id="467c2-126">Lorsque vous créez un index de recherche en texte intégral avec l’instruction **CREATE FULLTEXT INDEX** , vous avez la possibilité d’activer l’indexation sémantique au niveau de la colonne en spécifiant le mot clé **STATISTICAL_SEMANTICS** dans le cadre de la définition de la colonne.</span><span class="sxs-lookup"><span data-stu-id="467c2-126">When you create a new full-text index with the **CREATE FULLTEXT INDEX** statement, you can enable semantic indexing at the column level by specifying the keyword **STATISTICAL_SEMANTICS** as part of the column definition.</span></span> <span data-ttu-id="467c2-127">Vous pouvez également activer l'indexation sémantique lorsque vous utilisez l'Assistant Indexation de texte intégral pour créer un index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-127">You can also enable semantic indexing when you use the Full-Text Indexing Wizard to create a new full-text index.</span></span>  
  
 <span data-ttu-id="467c2-128">**Créer un index sémantique à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="467c2-128">**Create a new semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="467c2-129">Appelez l’instruction **CREATE FULLTEXT INDEX** et spécifiez **STATISTICAL_SEMANTICS** pour chaque colonne sur laquelle vous souhaitez créer un index sémantique.</span><span class="sxs-lookup"><span data-stu-id="467c2-129">Call the **CREATE FULLTEXT INDEX** statement and specify **STATISTICAL_SEMANTICS** for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="467c2-130">Pour plus d’informations sur toutes les options de cette instruction, consultez [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="467c2-130">For more information about all the options for this statement, see [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="467c2-131">**Exemple 1 : créer un index unique, un index de recherche en texte intégral et un index sémantique**</span><span class="sxs-lookup"><span data-stu-id="467c2-131">**Example 1: Create a unique index, full-text index, and semantic index**</span></span>  
  
 <span data-ttu-id="467c2-132">L’exemple suivant crée un catalogue de texte intégral par défaut, **ft**. L’exemple crée ensuite un index unique sur la colonne **JobCandidateID** de la table **HumanResources.JobCandidate** de l’exemple de base de données AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="467c2-132">The following example creates a default full-text catalog, **ft**. The example then creates a unique index on the **JobCandidateID** column of the **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="467c2-133">Cet index unique est requis en tant que colonne clé pour un index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-133">This unique index is required as the key column for a full-text index.</span></span> <span data-ttu-id="467c2-134">L’exemple crée ensuite un index de recherche en texte intégral et un index sémantique sur la colonne **Resume** .</span><span class="sxs-lookup"><span data-stu-id="467c2-134">The example then creates a full-text index and a semantic index on the **Resume** column.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG ft AS DEFAULT  
GO  
  
CREATE UNIQUE INDEX ui_ukJobCand  
    ON HumanResources.JobCandidate(JobCandidateID)  
GO  
  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate  
    (Resume  
        Language 1033  
        Statistical_Semantics  
    )   
    KEY INDEX JobCandidateID   
    WITH STOPLIST = SYSTEM  
GO  
```  
  
 <span data-ttu-id="467c2-135">**Exemple 2 : créer un index sémantique et de recherche en texte intégral sur plusieurs colonnes avec remplissage différé de l'index**</span><span class="sxs-lookup"><span data-stu-id="467c2-135">**Example 2: Create a full-text and semantic index on several columns with delayed index population**</span></span>  
  
 <span data-ttu-id="467c2-136">L’exemple suivant crée un catalogue de texte intégral, **documents_catalog**, dans l’exemple de base de données AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="467c2-136">The following example creates a full-text catalog, **documents_catalog**, in the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="467c2-137">L'exemple crée ensuite un index de recherche en texte intégral qui utilise ce nouveau catalogue.</span><span class="sxs-lookup"><span data-stu-id="467c2-137">The example then creates a full-text index that uses this new catalog.</span></span> <span data-ttu-id="467c2-138">L’index de recherche en texte intégral est créé sur les colonnes **Title**, **DocumentSummary**et **Document** de la table **Production.Document** , tandis que l’index sémantique est uniquement créé sur la colonne **Document** .</span><span class="sxs-lookup"><span data-stu-id="467c2-138">The full-text index is created on the **Title**, **DocumentSummary**, and **Document** columns of the **Production.Document** table, while the semantic index is only created on the **Document** column.</span></span> <span data-ttu-id="467c2-139">Cet index de recherche en texte intégral utilise le catalogue de texte intégral nouvellement créé et un index de clé unique existant, **PK_Document_DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="467c2-139">This full-text index uses the newly-created full-text catalog and an existing unique key index, **PK_Document_DocumentID**.</span></span> <span data-ttu-id="467c2-140">Comme recommandé, cette clé d'index est créée sur une colonne d'entiers, **DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="467c2-140">As recommended, this index key is created on an integer column, **DocumentID**.</span></span> <span data-ttu-id="467c2-141">L'exemple spécifie le LCID de l'anglais, 1033, qui est la langue des données dans les colonnes.</span><span class="sxs-lookup"><span data-stu-id="467c2-141">The example specifies the LCID for English, 1033, which is the language of the data in the columns.</span></span>  
  
 <span data-ttu-id="467c2-142">Cet exemple spécifie également que le suivi des modifications est désactivé et sans remplissage.</span><span class="sxs-lookup"><span data-stu-id="467c2-142">This example also specifies that change tracking is off with no population.</span></span> <span data-ttu-id="467c2-143">Plus tard, durant les heures creuses, cet exemple utilise une instruction **ALTER FULLTEXT INDEX** pour démarrer un remplissage complet sur le nouvel index et activer le suivi automatique des modifications.</span><span class="sxs-lookup"><span data-stu-id="467c2-143">Later, during off-peak hours, the example uses an **ALTER FULLTEXT INDEX** statement to start a full population on the new index and enable automatic change tracking.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG documents_catalog  
GO  
  
CREATE FULLTEXT INDEX ON Production.Document  
    (   
    Title  
        Language 1033,   
    DocumentSummary  
        Language 1033,   
    Document   
        TYPE COLUMN FileExtension  
        Language 1033  
        Statistical_Semantics  
    )  
    KEY INDEX PK_Document_DocumentID  
        ON documents_catalog  
        WITH CHANGE_TRACKING OFF, NO POPULATION  
GO  
```  
  
 <span data-ttu-id="467c2-144">Plus tard, pendant une heure creuse, l'index est rempli :</span><span class="sxs-lookup"><span data-stu-id="467c2-144">Later, at an off-peak time, the index is populated:</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document SET CHANGE_TRACKING AUTO  
GO  
```  
  
 <span data-ttu-id="467c2-145">**Créer un nouvel index sémantique à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="467c2-145">**Create a new semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="467c2-146">Exécutez l’Assistant Indexation de texte intégral et activez **Sémantiques statistiques** dans la page **Sélectionner les colonnes de la table** pour chaque colonne sur laquelle vous souhaitez créer un index sémantique.</span><span class="sxs-lookup"><span data-stu-id="467c2-146">Run the Full-Text Indexing Wizard and enable **Statistical Semantics** on the **Select Table Columns** page for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="467c2-147">Pour plus d’informations, notamment sur le démarrage de l’Assistant Indexation de texte intégral, consultez [Utiliser l’Assistant Indexation de texte intégral](use-the-full-text-indexing-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="467c2-147">For more information, including information about how to start the Full-Text Indexing Wizard, see [Use the Full-Text Indexing Wizard](use-the-full-text-indexing-wizard.md).</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-an-existing-full-text-index"></a><a name="HowToEnableAlter"></a><span data-ttu-id="467c2-148">Procédure : créer un index sémantique lorsqu’il existe un index de recherche en texte intégral existant</span><span class="sxs-lookup"><span data-stu-id="467c2-148">How To: Create a Semantic Index When There Is an Existing Full-Text Index</span></span>  
 <span data-ttu-id="467c2-149">Vous pouvez ajouter l’indexation sémantique lorsque vous modifiez un index de recherche en texte intégral existant avec l’instruction **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="467c2-149">You can add semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="467c2-150">Vous pouvez également ajouter l'indexation sémantique à l'aide de différentes boîtes de dialogue dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="467c2-150">You can also add semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="467c2-151">**Ajouter un index sémantique à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="467c2-151">**Add a semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="467c2-152">Appelez l’instruction **ALTER FULLTEXT INDEX** avec les options décrites ci-dessous pour chaque colonne sur laquelle vous souhaitez ajouter un index sémantique.</span><span class="sxs-lookup"><span data-stu-id="467c2-152">Call the **ALTER FULLTEXT INDEX** statement with the options described below for each column on which you want to add a semantic index.</span></span> <span data-ttu-id="467c2-153">Pour plus d’informations sur toutes les options de cette instruction, consultez [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="467c2-153">For more information about all the options for this statement, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="467c2-154">Les index sémantiques et de recherche en texte intégral sont à nouveau remplis après un appel à **ALTER**, sauf spécification contraire de votre part.</span><span class="sxs-lookup"><span data-stu-id="467c2-154">Both full-text and semantic indexes are repopulated after a call to **ALTER**, unless you specify otherwise.</span></span>  
  
-   <span data-ttu-id="467c2-155">Pour ajouter l’indexation de texte intégral uniquement à une colonne, utilisez la syntaxe **ADD** .</span><span class="sxs-lookup"><span data-stu-id="467c2-155">To add full-text indexing only to a column, use the **ADD** syntax.</span></span>  
  
-   <span data-ttu-id="467c2-156">Pour ajouter l’indexation sémantique et de texte intégral à une colonne, utilisez la syntaxe **ADD** avec l’option **STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="467c2-156">To add both full-text and semantic indexing to a column, use the **ADD** syntax with the **STATISTICAL_SEMANTICS** option.</span></span>  
  
-   <span data-ttu-id="467c2-157">Pour ajouter l’indexation sémantique à une colonne dont l’indexation de texte intégral est déjà activée, utilisez l’option **ADD STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="467c2-157">To add semantic indexing to a column that is already enabled for full-text indexing, use the **ADD STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="467c2-158">Vous ne pouvez ajouter l'indexation sémantique qu'à une colonne dans une instruction **ALTER** individuelle.</span><span class="sxs-lookup"><span data-stu-id="467c2-158">You can only add semantic indexing to one column in a single **ALTER** statement.</span></span>  
  
 <span data-ttu-id="467c2-159">**Exemple : ajouter l'indexation sémantique à une colonne dont l'indexation de texte intégral est déjà activée**</span><span class="sxs-lookup"><span data-stu-id="467c2-159">**Example: Add semantic indexing to a column that already has full-text indexing**</span></span>  
  
 <span data-ttu-id="467c2-160">L’exemple suivant modifie un index de recherche en texte intégral existant sur la table **Production.Document** de l’exemple de base de données AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="467c2-160">The following example alters an existing full-text index on **Production.Document** table in AdventureWorks2012 sample database.</span></span> <span data-ttu-id="467c2-161">Il ajoute un index sémantique sur la colonne **Document** de la table **Production.Document** , qui comporte déjà un index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-161">The example adds a semantic index on the **Document** column of the **Production.Document** table, which already has a full-text index.</span></span> <span data-ttu-id="467c2-162">L'exemple spécifie que l'index ne sera pas rempli à nouveau automatiquement.</span><span class="sxs-lookup"><span data-stu-id="467c2-162">The example specifies that the index will not be repopulated automatically.</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document  
    ALTER COLUMN Document  
        ADD Statistical_Semantics  
    WITH NO POPULATION  
GO  
```  
  
 <span data-ttu-id="467c2-163">**Ajouter un index sémantique à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="467c2-163">**Add a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="467c2-164">Vous pouvez modifier les colonnes activées pour l’indexation de texte intégral et sémantique dans la page **Colonnes d’index de recherche en texte intégral** de la boîte de dialogue **Propriétés d’index de recherche en texte intégral** .</span><span class="sxs-lookup"><span data-stu-id="467c2-164">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="467c2-165">Pour plus d’informations, consultez [Gérer les index de recherche en texte intégral](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="467c2-165">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-an-existing-index"></a><a name="addreq"></a><span data-ttu-id="467c2-166">Exigences et restrictions relatives à la modification d’un index existant</span><span class="sxs-lookup"><span data-stu-id="467c2-166">Requirements and Restrictions for Altering an Existing Index</span></span>  
  
-   <span data-ttu-id="467c2-167">Vous ne pouvez pas modifier un index existant pendant que le remplissage de l'index est en cours.</span><span class="sxs-lookup"><span data-stu-id="467c2-167">You cannot alter an existing index while population of the index is in progress.</span></span> <span data-ttu-id="467c2-168">Pour plus d’informations sur la surveillance de la progression du remplissage d’index, consultez [Gérer et surveiller la recherche sémantique](manage-and-monitor-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="467c2-168">For more information on monitoring the progress of index population, see [Manage and Monitor Semantic Search](manage-and-monitor-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="467c2-169">Vous ne pouvez pas ajouter d'indexation à une colonne, ni modifier ou supprimer l'indexation pour la même colonne, dans un appel unique à l'instruction **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="467c2-169">You cannot add indexing to a column, and alter or drop indexing for the same column, in a single call to the **ALTER FULLTEXT INDEX** statement.</span></span>  
  
##  <a name="dropping-a-semantic-index"></a><a name="dropping"></a><span data-ttu-id="467c2-170">Suppression d’un index sémantique</span><span class="sxs-lookup"><span data-stu-id="467c2-170">Dropping a Semantic Index</span></span>  
  
###  <a name="how-to-drop-a-semantic-index"></a><a name="drophow"></a><span data-ttu-id="467c2-171">Comment : supprimer un index sémantique</span><span class="sxs-lookup"><span data-stu-id="467c2-171">How to: Drop a Semantic Index</span></span>  
 <span data-ttu-id="467c2-172">Vous pouvez supprimer l’indexation sémantique lorsque vous modifiez un index de recherche en texte intégral existant avec l’instruction **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="467c2-172">You can drop semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="467c2-173">Vous pouvez également supprimer l'indexation sémantique à l'aide de différentes boîtes de dialogue dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="467c2-173">You can also drop semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="467c2-174">**Supprimer un index sémantique à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="467c2-174">**Drop a semantic index by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="467c2-175">Pour supprimer l’indexation sémantique d’une ou de plusieurs colonnes, appelez l’instruction **ALTER FULLTEXT INDEX** avec l’option **ALTER COLUMN***nom_colonne***DROP STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="467c2-175">To drop semantic indexing only from a column or columns, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="467c2-176">Vous pouvez supprimer l'indexation de plusieurs colonnes dans une instruction **ALTER** unique.</span><span class="sxs-lookup"><span data-stu-id="467c2-176">You can drop the indexing from multiple columns in a single **ALTER** statement.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP STATISTICAL_SEMANTICS  
    GO  
    ```  
  
-   <span data-ttu-id="467c2-177">Pour supprimer à la fois l’indexation sémantique et de texte intégral d’une colonne, appelez l’instruction **ALTER FULLTEXT index** avec l’option **ALTER COLUMN***column_name***Drop** .</span><span class="sxs-lookup"><span data-stu-id="467c2-177">To drop both full-text and semantic indexing from a column, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP** option.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP  
    GO  
    ```  
  
 <span data-ttu-id="467c2-178">**Supprimer un index sémantique à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="467c2-178">**Drop a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="467c2-179">Vous pouvez modifier les colonnes activées pour l’indexation de texte intégral et sémantique dans la page **Colonnes d’index de recherche en texte intégral** de la boîte de dialogue **Propriétés d’index de recherche en texte intégral** .</span><span class="sxs-lookup"><span data-stu-id="467c2-179">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="467c2-180">Pour plus d’informations, consultez [Gérer les index de recherche en texte intégral](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="467c2-180">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-dropping-a-semantic-index"></a><a name="dropreq"></a><span data-ttu-id="467c2-181">Exigences et restrictions relatives à la suppression d’un index sémantique</span><span class="sxs-lookup"><span data-stu-id="467c2-181">Requirements and Restrictions for Dropping a Semantic Index</span></span>  
  
-   <span data-ttu-id="467c2-182">Vous ne pouvez pas supprimer l'indexation de texte intégral d'une colonne tout en conservant l'indexation sémantique.</span><span class="sxs-lookup"><span data-stu-id="467c2-182">You cannot drop full-text indexing from a column while retaining semantic indexing.</span></span> <span data-ttu-id="467c2-183">L'indexation sémantique dépend de l'indexation de texte intégral pour les résultats de ressemblance de document.</span><span class="sxs-lookup"><span data-stu-id="467c2-183">Semantic indexing depends on full-text indexing for document similarity results.</span></span>  
  
-   <span data-ttu-id="467c2-184">Vous ne pouvez pas spécifier l'option **NO POPULATION** lorsque vous supprimez l'indexation sémantique de la dernière colonne d'une table pour laquelle l'indexation sémantique a été activée.</span><span class="sxs-lookup"><span data-stu-id="467c2-184">You cannot specify the **NO POPULATION** option when you drop semantic indexing from the last column in a table for which semantic indexing was enabled.</span></span> <span data-ttu-id="467c2-185">Un cycle de remplissage est obligatoire pour supprimer les résultats indexés précédemment.</span><span class="sxs-lookup"><span data-stu-id="467c2-185">A population cycle is required to remove the results that were indexed previously.</span></span>  
  
## <a name="checking-whether-semantic-search-is-enabled-on-database-objects"></a><span data-ttu-id="467c2-186">Vérification de l'activation de la recherche sémantique sur des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="467c2-186">Checking Whether Semantic Search Is Enabled on Database Objects</span></span>  
  
###  <a name="how-to-check-whether-semantic-search-is-enabled-on-database-objects"></a><a name="HowToCheckEnabled"></a><span data-ttu-id="467c2-187">Procédure : vérifier si la recherche sémantique est activée sur des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="467c2-187">How To: Check Whether Semantic Search Is Enabled on Database Objects</span></span>  
 <span data-ttu-id="467c2-188">**La recherche sémantique est-elle activée pour une base de données ?**</span><span class="sxs-lookup"><span data-stu-id="467c2-188">**Is semantic search enabled for a database?**</span></span>  
 <span data-ttu-id="467c2-189">Interrogez la propriété **IsFullTextEnabled** de la fonction de métadonnées [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="467c2-189">Query the **IsFullTextEnabled** property of the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="467c2-190">Une valeur de retour de 1 indique que la recherche en texte intégral et la recherche sémantique sont activées pour la base de données ; une valeur de retour de 0 indique qu'elles ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="467c2-190">A return value of 1 indicates that full-text search and semantic search are enabled for the database; a return value of 0 indicates that they are not enabled.</span></span>  
  
```sql  
SELECT DATABASEPROPERTYEX('database_name', 'IsFullTextEnabled')  
GO  
```  
  
 <span data-ttu-id="467c2-191">**La recherche sémantique est-elle activée pour une table ?**</span><span class="sxs-lookup"><span data-stu-id="467c2-191">**Is semantic search enabled for a table?**</span></span>  
 <span data-ttu-id="467c2-192">Interrogez la propriété **TableFullTextSemanticExtraction** de la fonction de métadonnées [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="467c2-192">Query the **TableFullTextSemanticExtraction** property of the [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="467c2-193">Une valeur de retour de 1 indique que la recherche sémantique est activée pour la table ; une valeur de retour de 0 indique qu'elle n'est pas activée.</span><span class="sxs-lookup"><span data-stu-id="467c2-193">A return value of 1 indicates that semantic search is enabled for the table; a return value of 0 indicates that it is not enabled.</span></span>  
  
```scr  
SELECT OBJECTPROPERTYEX(OBJECT_ID('table_name'), 'TableFullTextSemanticExtraction')  
GO  
```  
  
 <span data-ttu-id="467c2-194">**La recherche sémantique est-elle activée pour une colonne ?**</span><span class="sxs-lookup"><span data-stu-id="467c2-194">**Is semantic search enabled for a column?**</span></span>  
 <span data-ttu-id="467c2-195">Pour déterminer si la recherche sémantique est activée pour une colonne spécifique :</span><span class="sxs-lookup"><span data-stu-id="467c2-195">To determine whether semantic search is enabled for a specific column:</span></span>  
  
-   <span data-ttu-id="467c2-196">Interrogez la propriété **StatisticalSemantics** de la fonction de métadonnées [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="467c2-196">Query the **StatisticalSemantics** property of the [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql) metadata function.</span></span>  
  
     <span data-ttu-id="467c2-197">Une valeur de retour de 1 indique que la recherche sémantique est activée pour la colonne ; une valeur de retour de 0 indique qu'elle n'est pas activée.</span><span class="sxs-lookup"><span data-stu-id="467c2-197">A return value of 1 indicates that semantic search is enabled for the column; a return value of 0 indicates that it is not enabled.</span></span>  
  
    ```sql  
    SELECT COLUMNPROPERTY(OBJECT_ID('table_name'), 'column_name', 'StatisticalSemantics')  
    GO  
    ```  
  
-   <span data-ttu-id="467c2-198">Interrogez l’affichage catalogue [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) de l’index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-198">Query the catalog view [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) for the full-text index.</span></span>  
  
     <span data-ttu-id="467c2-199">Une valeur 1 dans la colonne **statistical_semantics** indique que la colonne spécifiée est activée pour l’indexation sémantique en plus de l’indexation de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-199">A value of 1 in the **statistical_semantics** column indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
    ```sql  
    SELECT * FROM sys.fulltext_index_columns WHERE object_id = OBJECT_ID('table_name')  
    GO  
    ```  
  
-   <span data-ttu-id="467c2-200">Dans l’Explorateur d’objets dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], cliquez avec le bouton droit sur une colonne, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="467c2-200">In Object Explorer in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click on a column and select **Properties**.</span></span> <span data-ttu-id="467c2-201">Dans la page **Général** de la boîte de dialogue **Propriétés de la colonne** , vérifiez la valeur de la propriété **Statistical Semantics** .</span><span class="sxs-lookup"><span data-stu-id="467c2-201">On the **General** page of the **Column Properties** dialog box, check the value of the **Statistical Semantics** property.</span></span>  
  
     <span data-ttu-id="467c2-202">Une valeur True indique que la colonne spécifiée est activée pour l'indexation sémantique en plus de l'indexation de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-202">A value of True indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
## <a name="determining-what-can-be-indexed-for-semantic-search"></a><span data-ttu-id="467c2-203">Déterminer ce qui peut être indexé pour la recherche sémantique</span><span class="sxs-lookup"><span data-stu-id="467c2-203">Determining What Can Be Indexed for Semantic Search</span></span>  
  
###  <a name="how-to-check-which-languages-are-supported-for-semantic-search"></a><a name="HowToCheckLanguages"></a><span data-ttu-id="467c2-204">Comment : vérifier les langues prises en charge pour la recherche sémantique</span><span class="sxs-lookup"><span data-stu-id="467c2-204">How To: Check Which Languages Are Supported for Semantic Search</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="467c2-205">Moins de langues sont prises en charge pour l'indexation sémantique que pour l'indexation de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-205">Fewer languages are supported for semantic indexing than for full-text indexing.</span></span> <span data-ttu-id="467c2-206">Par conséquent, il peut y avoir des colonnes que vous pouvez indexer pour la recherche en texte intégral, mais pas pour la recherche sémantique.</span><span class="sxs-lookup"><span data-stu-id="467c2-206">As a result, there may be columns that you can index for full-text search, but not for semantic search.</span></span>  
  
 <span data-ttu-id="467c2-207">Interrogez l’affichage catalogue [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="467c2-207">Query the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.fulltext_semantic_languages  
GO  
```  
  
 <span data-ttu-id="467c2-208">Les langues suivantes sont prises en charge pour l'indexation sémantique.</span><span class="sxs-lookup"><span data-stu-id="467c2-208">The following languages are supported for semantic indexing.</span></span> <span data-ttu-id="467c2-209">Cette liste représente la sortie de l’affichage catalogue [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), classée par LCID.</span><span class="sxs-lookup"><span data-stu-id="467c2-209">This list represents the output of the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), ordered by LCID.</span></span>  
  
|<span data-ttu-id="467c2-210">Langage</span><span class="sxs-lookup"><span data-stu-id="467c2-210">Language</span></span>|<span data-ttu-id="467c2-211">LCID</span><span class="sxs-lookup"><span data-stu-id="467c2-211">LCID</span></span>|  
|--------------|----------|  
|<span data-ttu-id="467c2-212">Allemand</span><span class="sxs-lookup"><span data-stu-id="467c2-212">German</span></span>|<span data-ttu-id="467c2-213">1031</span><span class="sxs-lookup"><span data-stu-id="467c2-213">1031</span></span>|  
|<span data-ttu-id="467c2-214">Anglais (US)</span><span class="sxs-lookup"><span data-stu-id="467c2-214">English (US)</span></span>|<span data-ttu-id="467c2-215">1033</span><span class="sxs-lookup"><span data-stu-id="467c2-215">1033</span></span>|  
|<span data-ttu-id="467c2-216">Français</span><span class="sxs-lookup"><span data-stu-id="467c2-216">French</span></span>|<span data-ttu-id="467c2-217">1036</span><span class="sxs-lookup"><span data-stu-id="467c2-217">1036</span></span>|  
|<span data-ttu-id="467c2-218">Italien</span><span class="sxs-lookup"><span data-stu-id="467c2-218">Italian</span></span>|<span data-ttu-id="467c2-219">1040</span><span class="sxs-lookup"><span data-stu-id="467c2-219">1040</span></span>|  
|<span data-ttu-id="467c2-220">Portugais (Brésil)</span><span class="sxs-lookup"><span data-stu-id="467c2-220">Portuguese (Brazil)</span></span>|<span data-ttu-id="467c2-221">1046</span><span class="sxs-lookup"><span data-stu-id="467c2-221">1046</span></span>|  
|<span data-ttu-id="467c2-222">Russe</span><span class="sxs-lookup"><span data-stu-id="467c2-222">Russian</span></span>|<span data-ttu-id="467c2-223">1049</span><span class="sxs-lookup"><span data-stu-id="467c2-223">1049</span></span>|  
|<span data-ttu-id="467c2-224">Suédois</span><span class="sxs-lookup"><span data-stu-id="467c2-224">Swedish</span></span>|<span data-ttu-id="467c2-225">1053</span><span class="sxs-lookup"><span data-stu-id="467c2-225">1053</span></span>|  
|<span data-ttu-id="467c2-226">Anglais (Royaume-Uni)</span><span class="sxs-lookup"><span data-stu-id="467c2-226">English (UK)</span></span>|<span data-ttu-id="467c2-227">2057</span><span class="sxs-lookup"><span data-stu-id="467c2-227">2057</span></span>|  
|<span data-ttu-id="467c2-228">Portugais (Portugal)</span><span class="sxs-lookup"><span data-stu-id="467c2-228">Portuguese (Portugal)</span></span>|<span data-ttu-id="467c2-229">2070</span><span class="sxs-lookup"><span data-stu-id="467c2-229">2070</span></span>|  
|<span data-ttu-id="467c2-230">Espagnol</span><span class="sxs-lookup"><span data-stu-id="467c2-230">Spanish</span></span>|<span data-ttu-id="467c2-231">3082</span><span class="sxs-lookup"><span data-stu-id="467c2-231">3082</span></span>|  
  
###  <a name="how-to-determine-which-document-types-can-be-indexed"></a><a name="doctypes"></a><span data-ttu-id="467c2-232">Comment : déterminer les types de documents qui peuvent être indexés</span><span class="sxs-lookup"><span data-stu-id="467c2-232">How To: Determine Which Document Types Can Be Indexed</span></span>  
 <span data-ttu-id="467c2-233">Interrogez l’affichage catalogue [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="467c2-233">Query the catalog view [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span></span>  
  
 <span data-ttu-id="467c2-234">Si le type de document que vous souhaitez indexer ne figure pas dans la liste des types pris en charge, vous devrez peut-être rechercher, télécharger et installer des filtres supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="467c2-234">If the document type that you want to index is not in the list of supported types, then you may have to locate, download, and install additional filters.</span></span> <span data-ttu-id="467c2-235">Pour plus d’informations, consultez [Afficher ou modifier des filtres et des analyseurs lexicaux inscrits](view-or-change-registered-filters-and-word-breakers.md).</span><span class="sxs-lookup"><span data-stu-id="467c2-235">For more information, see [View or Change Registered Filters and Word Breakers](view-or-change-registered-filters-and-word-breakers.md).</span></span>  
  
##  <a name="best-practice-consider-creating-a-separate-filegroup-for-the-full-text-and-semantic-indexes"></a><a name="BestPracticeFilegroup"></a><span data-ttu-id="467c2-236">Bonne pratique : envisagez de créer un groupe de fichiers distinct pour les index sémantiques et de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="467c2-236">Best Practice: Consider Creating a Separate Filegroup for the Full-Text and Semantic Indexes</span></span>  
 <span data-ttu-id="467c2-237">Créez un groupe de fichiers séparé pour les index sémantiques et de recherche en texte intégral si l'allocation d'espace disque pose problème.</span><span class="sxs-lookup"><span data-stu-id="467c2-237">Consider creating a separate filegroup for the full-text and semantic indexes if disk space allocation is a concern.</span></span> <span data-ttu-id="467c2-238">Les index sémantiques sont créés dans le même groupe de fichiers que l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="467c2-238">The semantic indexes are created in the same filegroup as the full-text index.</span></span> <span data-ttu-id="467c2-239">Un index sémantique entièrement rempli peut contenir un grand nombre de données.</span><span class="sxs-lookup"><span data-stu-id="467c2-239">A fully populated semantic index may contain large amount of data.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-searching-on-specific-column-returns-no-results"></a><a name="IssueNoResults"></a><span data-ttu-id="467c2-240">Problème : la recherche sur une colonne spécifique ne retourne aucun résultat</span><span class="sxs-lookup"><span data-stu-id="467c2-240">Problem: Searching on Specific Column Returns No Results</span></span>  
 <span data-ttu-id="467c2-241">**Est-ce qu'un LCID non-Unicode a été spécifié pour une langue Unicode ?**</span><span class="sxs-lookup"><span data-stu-id="467c2-241">**Was a non-Unicode LCID specified for a Unicode language?**</span></span>  
 <span data-ttu-id="467c2-242">Il est possible d'activer l'indexation sémantique sur un type de colonne non-Unicode avec un LCID de langue qui comporte uniquement des termes Unicode, tels que LCID 1049 pour le russe.</span><span class="sxs-lookup"><span data-stu-id="467c2-242">It is possible to enable semantic indexing on a non-Unicode column type with an LCID for a language that only has Unicode words, such as LCID 1049 for Russian.</span></span> <span data-ttu-id="467c2-243">Dans ce cas, aucun résultat ne sera jamais retourné des index sémantiques sur cette colonne.</span><span class="sxs-lookup"><span data-stu-id="467c2-243">In this case, no results will ever be returned from the semantic indexes on this column.</span></span>  
  
  
