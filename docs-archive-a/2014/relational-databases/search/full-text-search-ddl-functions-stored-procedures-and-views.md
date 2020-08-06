---
title: DDL, fonctions, procédures stockées et vues de la recherche en texte intégral | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: 98c36715-4195-482e-a4a3-d93ff65b75f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 29b026ac60fd3f7d00ca519c4ced84533ce9740f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613401"
---
# <a name="full-text-search-ddl-functions-stored-procedures-and-views"></a><span data-ttu-id="cc922-102">DDL, fonctions, procédures stockées et vues de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="cc922-102">Full-Text Search DDL, Functions, Stored Procedures, and Views</span></span>
  <span data-ttu-id="cc922-103">Répertorie les instructions Transact-SQL et les objets de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui prennent en charge la recherche en texte intégral, y compris la fonctionnalité de recherche de propriété.</span><span class="sxs-lookup"><span data-stu-id="cc922-103">Lists the Transact-SQL statements and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects that support full-text search, including the property search feature.</span></span>  
  
 <span data-ttu-id="cc922-104">Cette liste n'inclut pas les objets déconseillés.</span><span class="sxs-lookup"><span data-stu-id="cc922-104">This list does not include deprecated objects.</span></span>  
  
 <span data-ttu-id="cc922-105">Pour obtenir la liste des objets de base de données qui prennent en charge la recherche sémantique, consultez [Semantic Search DDL, Functions, Stored Procedures, and Views](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="cc922-105">For the list of database objects that support semantic search, see [Semantic Search DDL, Functions, Stored Procedures, and Views](../views/views.md).</span></span>  
  
##  <a name="transact-sql-data-definition-language-ddl-statements"></a><a name="ddl"></a> <span data-ttu-id="cc922-106">Instructions DDL (Data Definition Language, langage de définition de données) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cc922-106">Transact-SQL Data Definition Language (DDL) Statements</span></span>  
  
-   [<span data-ttu-id="cc922-107">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-107">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-catalog-transact-sql)  
  
-   [<span data-ttu-id="cc922-108">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-108">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
-   [<span data-ttu-id="cc922-109">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-109">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql)  
  
-   [<span data-ttu-id="cc922-110">CREATE SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-110">CREATE SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-search-property-list-transact-sql)  
  
-   [<span data-ttu-id="cc922-111">ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-111">ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql)  
  
-   [<span data-ttu-id="cc922-112">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-112">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
-   [<span data-ttu-id="cc922-113">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-113">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql)  
  
-   [<span data-ttu-id="cc922-114">ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-114">ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-search-property-list-transact-sql)  
  
-   [<span data-ttu-id="cc922-115">DROP FULLTEXT CATALOG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-115">DROP FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-catalog-transact-sql)  
  
-   [<span data-ttu-id="cc922-116">DROP FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-116">DROP FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-index-transact-sql)  
  
-   [<span data-ttu-id="cc922-117">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-117">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
-   [<span data-ttu-id="cc922-118">DROP SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-118">DROP SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-search-property-list-transact-sql)  
  
##  <a name="system-predicates-and-functions"></a><a name="func"></a> <span data-ttu-id="cc922-119">Prédicats et fonctions système</span><span class="sxs-lookup"><span data-stu-id="cc922-119">System Predicates and Functions</span></span>  
  
-   [<span data-ttu-id="cc922-120">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-120">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
-   [<span data-ttu-id="cc922-121">CONTAINSTABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-121">CONTAINSTABLE &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/containstable-transact-sql)  
  
-   [<span data-ttu-id="cc922-122">FREETEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-122">FREETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/freetext-transact-sql)  
  
-   [<span data-ttu-id="cc922-123">FREETEXTTABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-123">FREETEXTTABLE &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/freetexttable-transact-sql)  
  
##  <a name="system-metadata-functions"></a><a name="meta"></a> <span data-ttu-id="cc922-124">Fonctions de métadonnées système</span><span class="sxs-lookup"><span data-stu-id="cc922-124">System Metadata Functions</span></span>  
  
-   [<span data-ttu-id="cc922-125">COLUMNPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-125">COLUMNPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/columnproperty-transact-sql)  
  
-   [<span data-ttu-id="cc922-126">FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-126">FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql)  
  
-   [<span data-ttu-id="cc922-127">FULLTEXTSERVICEPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-127">FULLTEXTSERVICEPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/fulltextserviceproperty-transact-sql)  
  
-   [<span data-ttu-id="cc922-128">INDEXPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-128">INDEXPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/indexproperty-transact-sql)  
  
-   [<span data-ttu-id="cc922-129">OBJECTPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-129">OBJECTPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/objectpropertyex-transact-sql)  
  
-   [<span data-ttu-id="cc922-130">OBJECTPROPERTYEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-130">OBJECTPROPERTYEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/objectproperty-transact-sql)  
  
-   [<span data-ttu-id="cc922-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
  
##  <a name="system-stored-procedures"></a><a name="proc"></a> <span data-ttu-id="cc922-132">Procédures stockées système</span><span class="sxs-lookup"><span data-stu-id="cc922-132">System Stored Procedures</span></span>  
  
-   [<span data-ttu-id="cc922-133">sp_fulltext_keymappings &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-133">sp_fulltext_keymappings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-keymappings-transact-sql)  
  
-   [<span data-ttu-id="cc922-134">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-134">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql)  
  
-   [<span data-ttu-id="cc922-135">sp_fulltext_pendingchanges &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-135">sp_fulltext_pendingchanges &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-pendingchanges-transact-sql)  
  
-   [<span data-ttu-id="cc922-136">sp_fulltext_service &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-136">sp_fulltext_service &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql)  
  
-   [<span data-ttu-id="cc922-137">sp_help_fulltext_system_components &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-137">sp_help_fulltext_system_components &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql)  
  
##  <a name="system-views---catalog-views"></a><a name="cat"></a> <span data-ttu-id="cc922-138">Vues système - Affichages catalogue</span><span class="sxs-lookup"><span data-stu-id="cc922-138">System Views - Catalog Views</span></span>  
  
-   [<span data-ttu-id="cc922-139">sys.fulltext_catalogs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-139">sys.fulltext_catalogs &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql)  
  
-   [<span data-ttu-id="cc922-140">sys.fulltext_document_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-140">sys.fulltext_document_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql)  
  
-   [<span data-ttu-id="cc922-141">sys.fulltext_index_catalog_usages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-141">sys.fulltext_index_catalog_usages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-index-catalog-usages-transact-sql)  
  
-   [<span data-ttu-id="cc922-142">sys.fulltext_index_columns &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-142">sys.fulltext_index_columns &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql)  
  
-   [<span data-ttu-id="cc922-143">sys.fulltext_index_fragments &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-143">sys.fulltext_index_fragments &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-index-fragments-transact-sql)  
  
-   [<span data-ttu-id="cc922-144">sys.fulltext_indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-144">sys.fulltext_indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql)  
  
-   [<span data-ttu-id="cc922-145">sys.fulltext_languages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-145">sys.fulltext_languages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql)  
  
-   [<span data-ttu-id="cc922-146">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-146">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
-   [<span data-ttu-id="cc922-147">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-147">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
-   [<span data-ttu-id="cc922-148">sys.fulltext_system_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-148">sys.fulltext_system_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-system-stopwords-transact-sql)  
  
-   [<span data-ttu-id="cc922-149">sys.registered_search_properties &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-149">sys.registered_search_properties &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-properties-transact-sql)  
  
-   [<span data-ttu-id="cc922-150">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-150">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-property-lists-transact-sql)  
  
##  <a name="system-views---dynamic-management-views"></a><a name="dmv"></a> <span data-ttu-id="cc922-151">Vues système – Vues de gestion dynamique</span><span class="sxs-lookup"><span data-stu-id="cc922-151">System Views - Dynamic Management Views</span></span>  
  
-   [<span data-ttu-id="cc922-152">sys.dm_fts_active_catalogs &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-152">sys.dm_fts_active_catalogs &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-active-catalogs-transact-sql)  
  
-   [<span data-ttu-id="cc922-153">sys.dm_fts_fdhosts &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-153">sys.dm_fts_fdhosts &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-fdhosts-transact-sql)  
  
-   [<span data-ttu-id="cc922-154">sys.dm_fts_index_keywords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-154">sys.dm_fts_index_keywords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-transact-sql)  
  
-   [<span data-ttu-id="cc922-155">sys.dm_fts_index_keywords_by_document &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-155">sys.dm_fts_index_keywords_by_document &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-by-document-transact-sql)  
  
-   [<span data-ttu-id="cc922-156">sys.dm_fts_index_keywords_by_property &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-156">sys.dm_fts_index_keywords_by_property &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-by-property-transact-sql)  
  
-   [<span data-ttu-id="cc922-157">sys.dm_fts_index_population &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-157">sys.dm_fts_index_population &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql)  
  
-   [<span data-ttu-id="cc922-158">sys.dm_fts_memory_buffers &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-158">sys.dm_fts_memory_buffers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-memory-buffers-transact-sql)  
  
-   [<span data-ttu-id="cc922-159">sys.dm_fts_memory_pools &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-159">sys.dm_fts_memory_pools &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-memory-pools-transact-sql)  
  
-   [<span data-ttu-id="cc922-160">sys.dm_fts_outstanding_batches &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-160">sys.dm_fts_outstanding_batches &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-outstanding-batches-transact-sql)  
  
-   [<span data-ttu-id="cc922-161">sys.dm_fts_parser &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-161">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
-   [<span data-ttu-id="cc922-162">sys.dm_fts_population_ranges &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cc922-162">sys.dm_fts_population_ranges &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-population-ranges-transact-sql)  
  
  
