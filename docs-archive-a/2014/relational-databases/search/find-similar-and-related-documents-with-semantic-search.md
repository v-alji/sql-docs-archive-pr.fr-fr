---
title: Rechercher des documents similaires ou connexes avec la recherche sémantique | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], document similarity queries
ms.assetid: 9f527883-031b-442f-8e95-24bc0151ecbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b11493b5b04fa9308e3afbe56176251225248338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614470"
---
# <a name="find-similar-and-related-documents-with-semantic-search"></a><span data-ttu-id="1283d-102">Rechercher des documents similaires ou connexes avec la recherche sémantique</span><span class="sxs-lookup"><span data-stu-id="1283d-102">Find Similar and Related Documents with Semantic Search</span></span>
  <span data-ttu-id="1283d-103">Explique comment rechercher des valeurs textuelles ou des documents similaires ou connexes et donne des informations sur leur similitude, dans des colonnes configurées pour l'indexation sémantique statistique.</span><span class="sxs-lookup"><span data-stu-id="1283d-103">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-similar-or-related-documents"></a><a name="BasicsQuerySimilar"></a><span data-ttu-id="1283d-104">Recherche de documents similaires ou connexes</span><span class="sxs-lookup"><span data-stu-id="1283d-104">Finding Similar or Related Documents</span></span>  
  
###  <a name="how-to-find-similar-or-related-documents-with-semanticsimilaritytable"></a><a name="HowToQuerySimilar"></a><span data-ttu-id="1283d-105">Comment : Rechercher des documents similaires ou connexes avec SEMANTICSIMILARITYTABLE</span><span class="sxs-lookup"><span data-stu-id="1283d-105">How To: Find Similar or Related Documents with SEMANTICSIMILARITYTABLE</span></span>  
 <span data-ttu-id="1283d-106">Pour identifier des documents similaires ou connexes dans une colonne spécifique, interrogez la fonction [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1283d-106">To identify similar or related documents in a specific column, query the function [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span></span>  
  
 <span data-ttu-id="1283d-107">**SEMANTICSIMILARITYTABLE** retourne une table de zéro, une ou plusieurs lignes pour les colonnes dont le contenu dans la colonne spécifiée est sémantiquement similaire au document spécifié.</span><span class="sxs-lookup"><span data-stu-id="1283d-107">**SEMANTICSIMILARITYTABLE** returns a table of zero, one, or more rows whose content in the specified column is semantically similar to the specified document.</span></span> <span data-ttu-id="1283d-108">Cette fonction d'ensemble de lignes peut être référencée dans la clause FROM d'une instruction SELECT comme un nom de table classique.</span><span class="sxs-lookup"><span data-stu-id="1283d-108">This rowset function can be referenced in the FROM clause of a SELECT statement like a regular table name.</span></span>  
  
 <span data-ttu-id="1283d-109">Vous ne pouvez pas rechercher des documents similaires dans plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="1283d-109">You cannot query across columns for similar documents.</span></span> <span data-ttu-id="1283d-110">La fonction **SEMANTICSIMILARITYTABLE** récupère uniquement des résultats provenant de la même colonne que la colonne source, qui est identifiée par l’argument **source_key** .</span><span class="sxs-lookup"><span data-stu-id="1283d-110">The **SEMANTICSIMILARITYTABLE** function only retrieves results from the same column as the source column, which is identified by the **source_key** argument.</span></span>  
  
 <span data-ttu-id="1283d-111">Pour plus d’informations sur les paramètres requis par la fonction **SEMANTICSIMILARITYTABLE** et sur la table de résultats qu’elle retourne, consultez [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1283d-111">For detailed information about the parameters required by the **SEMANTICSIMILARITYTABLE** function, and about the table of results that it returns, see [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1283d-112">L'indexation sémantique et de texte intégral doit être activée pour les colonnes que vous ciblez.</span><span class="sxs-lookup"><span data-stu-id="1283d-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-find-the-top-documents-that-are-similar-to-another-document"></a><a name="HowToIdentifySimilar"></a><span data-ttu-id="1283d-113">Exemple : Rechercher les documents de niveau supérieur qui sont similaires à un autre document</span><span class="sxs-lookup"><span data-stu-id="1283d-113">Example: Find the Top Documents That Are Similar to Another Document</span></span>  
 <span data-ttu-id="1283d-114">L’exemple suivant récupère les 10 premiers candidats similaires au candidat spécifié par *@CandidateID* dans la table HumanResources. JobCandidate de l’exemple de base de données AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="1283d-114">The following example retrieves the top 10 candidates who are similar to the candidate specified by *@CandidateID* from the HumanResources.JobCandidate table in the AdventureWorks2012 sample database.</span></span>  
  
```scr  
SELECT TOP(10) KEY_TBL.matched_document_key AS Candidate_ID  
FROM SEMANTICSIMILARITYTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume,  
    @CandidateID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
GO  
```  
  
##  <a name="finding-information-about-how-documents-are-similar-or-related"></a><a name="BasicsQuerySimilarity"></a><span data-ttu-id="1283d-115">Recherche d’informations sur la façon dont les documents sont similaires ou connexes</span><span class="sxs-lookup"><span data-stu-id="1283d-115">Finding Information about How Documents Are Similar or Related</span></span>  
  
###  <a name="how-to-find-information-about-how-documents-are-similar-or-related-with-semanticsimilaritydetailstable"></a><a name="HowToQuerySimilarity"></a><span data-ttu-id="1283d-116">Comment : Rechercher des informations sur la façon dont les documents sont similaires ou connexes avec SEMANTICSIMILARITYDETAILSTABLE</span><span class="sxs-lookup"><span data-stu-id="1283d-116">How To: Find Information about How Documents Are Similar or Related with SEMANTICSIMILARITYDETAILSTABLE</span></span>  
 <span data-ttu-id="1283d-117">Pour obtenir des informations sur les expressions clés qui rendent des documents similaires ou connexes, vous pouvez interroger la fonction [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1283d-117">To get information about the key phrases that make documents similar or related, you can query the function [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span></span>  
  
 <span data-ttu-id="1283d-118">**SEMANTICSIMILARITYDETAILSTABLE** retourne une table de zéro, une ou plusieurs lignes d’expressions clés communes dans deux documents (un document source et un document mis en correspondance) dont le contenu est similaire sémantiquement.</span><span class="sxs-lookup"><span data-stu-id="1283d-118">**SEMANTICSIMILARITYDETAILSTABLE** returns a table of zero, one, or more rows of key phrases common across two documents (a source document and a matched document) whose content is semantically similar.</span></span> <span data-ttu-id="1283d-119">Cette fonction d'ensemble de lignes peut être référencée dans la clause FROM d'une instruction SELECT comme un nom de table classique.</span><span class="sxs-lookup"><span data-stu-id="1283d-119">This rowset function can be referenced in the FROM clause of a SELECT statement like a regular table name.</span></span>  
  
 <span data-ttu-id="1283d-120">Pour plus d’informations sur les paramètres requis par la fonction **SEMANTICSIMILARITYDETAILSTABLE**, ainsi que sur la table de résultats qu’elle retourne, consultez [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1283d-120">For detailed information about the parameters required by the **SEMANTICSIMILARITYDETAILSTABLE** function, and about the table of results that it returns, see [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1283d-121">L'indexation sémantique et de texte intégral doit être activée pour les colonnes que vous ciblez.</span><span class="sxs-lookup"><span data-stu-id="1283d-121">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-find-the-top-key-phrases-that-are-similar-between-documents"></a><a name="HowToSimilarPhrases"></a><span data-ttu-id="1283d-122">Exemple : Rechercher les expressions clés de niveau supérieur qui sont similaires entre les documents</span><span class="sxs-lookup"><span data-stu-id="1283d-122">Example: Find the Top Key Phrases That Are Similar between Documents</span></span>  
 <span data-ttu-id="1283d-123">L'exemple suivant récupère les 5 expressions clés qui ont le score de similarité le plus élevé parmi les candidats spécifiés dans la table **HumanResources.JobCandidate** de l'exemple de base de données AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="1283d-123">The following example retrieves the 5 key phrases that have the highest similarity score between the specified candidates in **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span>  
  
```sql  
SELECT TOP(5) KEY_TBL.keyphrase, KEY_TBL.score  
FROM SEMANTICSIMILARITYDETAILSTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume, @CandidateID,  
    Resume, @MatchedID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
GO  
```  
  
  
