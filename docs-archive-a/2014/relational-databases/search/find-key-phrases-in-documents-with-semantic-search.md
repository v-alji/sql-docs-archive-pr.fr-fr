---
title: Rechercher des expressions clés dans les documents avec la recherche sémantique | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], key phrase queries
ms.assetid: 6ee3676e-ed5d-43ec-aeca-1eed78967111
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8388fb704bf13f44d025e6e32a1450d537f61832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697865"
---
# <a name="find-key-phrases-in-documents-with-semantic-search"></a><span data-ttu-id="4064e-102">Rechercher des expressions clés dans les documents avec la recherche sémantique</span><span class="sxs-lookup"><span data-stu-id="4064e-102">Find Key Phrases in Documents with Semantic Search</span></span>
  <span data-ttu-id="4064e-103">Explique comment rechercher des expressions clés dans des documents ou des colonnes de texte configurés pour l'indexation sémantique statistique.</span><span class="sxs-lookup"><span data-stu-id="4064e-103">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-key-phrases-in-documents"></a><a name="BasicsQueryKey"></a><span data-ttu-id="4064e-104">Recherche d’expressions clés dans des documents</span><span class="sxs-lookup"><span data-stu-id="4064e-104">Finding Key Phrases in Documents</span></span>  
  
###  <a name="how-to-find-the-key-phrases-in-documents-with-semantickeyphrasetable"></a><a name="howtofind"></a><span data-ttu-id="4064e-105">Comment : Rechercher les expressions clés dans des documents avec SEMANTICKEYPHRASETABLE</span><span class="sxs-lookup"><span data-stu-id="4064e-105">How to: Find the Key Phrases in Documents with SEMANTICKEYPHRASETABLE</span></span>  
 <span data-ttu-id="4064e-106">Pour identifier les expressions clés dans des documents spécifiques, ou pour identifier des documents qui contiennent des expressions clés spécifiques, vous pouvez interroger la fonction [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4064e-106">To identify the key phrases in specific documents, or to identify documents that contain specific key phrases, query the function [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
 <span data-ttu-id="4064e-107">SEMANTICKEYPHRASETABLE retourne une table avec zéro, une ou plusieurs lignes pour les expressions clés associées aux colonnes de la table spécifiée.</span><span class="sxs-lookup"><span data-stu-id="4064e-107">SEMANTICKEYPHRASETABLE returns a table with zero, one, or more rows for those key phrases associated with columns in the specified table.</span></span> <span data-ttu-id="4064e-108">Cette fonction d'ensemble de lignes peut uniquement être référencée dans la clause FROM d'une instruction SELECT comme tout nom de table standard.</span><span class="sxs-lookup"><span data-stu-id="4064e-108">This rowset function can be referenced in the FROM clause of a SELECT statement as if it were a regular table name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4064e-109">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], seuls les mots isolés sont indexés pour la recherche sémantique ; les expressions constituées de plusieurs mots (ngrams) ne sont pas indexées.</span><span class="sxs-lookup"><span data-stu-id="4064e-109">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], only single words are indexed for semantic search; multi-word phrases (ngrams) are not indexed.</span></span> <span data-ttu-id="4064e-110">En outre, des formes différentes du même mot sont indexées séparément ; par exemple, « ordinateur » et « ordinateurs » sont indexés séparément.</span><span class="sxs-lookup"><span data-stu-id="4064e-110">Also, various forms of the same word are indexed separately; for example, "computer" and "computers" are indexed separately.</span></span>  
  
 <span data-ttu-id="4064e-111">Pour plus d’informations sur les paramètres requis par la fonction SEMANTICKEYPHRASETABLE, ainsi que sur la table de résultats qu’elle renvoie, consultez [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4064e-111">For detailed information about the parameters required by the SEMANTICKEYPHRASETABLE function, and about the table of results that it returns, see [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4064e-112">L'indexation sémantique et de texte intégral doit être activée pour les colonnes que vous ciblez.</span><span class="sxs-lookup"><span data-stu-id="4064e-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-1-find-the-top-key-phrases-in-a-specific-document"></a><a name="HowToTopPhrases"></a><span data-ttu-id="4064e-113">Exemple 1 : Rechercher les expressions clés de niveau supérieur dans un document spécifique</span><span class="sxs-lookup"><span data-stu-id="4064e-113">Example 1: Find the Top Key Phrases in a Specific Document</span></span>  
 <span data-ttu-id="4064e-114">L’exemple suivant extrait les 10 expressions clés de niveau supérieur du document spécifié par la variable @DocumentId dans la colonne Document de la table Production.Document de l’exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4064e-114">The following example retrieves the top 10 key phrases from the document specified by the @DocumentId variable in the Document column of the Production.Document table of the AdventureWorks sample database.</span></span> <span data-ttu-id="4064e-115">La variable @DocumentId représente une valeur de la colonne clé de l’index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="4064e-115">The @DocumentId variable represents a value from the key column of the full-text index.</span></span>  
  
```sql  
SELECT TOP(10) KEYP_TBL.keyphrase  
FROM SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document,  
    @DocumentId  
    ) AS KEYP_TBL  
ORDER BY KEYP_TBL.score DESC;  
GO  
```  
  
 <span data-ttu-id="4064e-116">La fonction **SEMANTICKEYPHRASETABLE** récupère efficacement ces résultats en utilisant une recherche d'index au lieu d'une analyse de table.</span><span class="sxs-lookup"><span data-stu-id="4064e-116">The **SEMANTICKEYPHRASETABLE** function retrieves these results efficiently by using an index seek instead of a table scan.</span></span>  
  
###  <a name="example-2-find-the-top-documents-that-contain-a-specific-key-phrase"></a><a name="HowToTopDocuments"></a><span data-ttu-id="4064e-117">Exemple 2 : Rechercher les documents de niveau supérieur qui contiennent une expression clé spécifique</span><span class="sxs-lookup"><span data-stu-id="4064e-117">Example 2: Find the Top Documents that Contain a Specific Key Phrase</span></span>  
 <span data-ttu-id="4064e-118">L’exemple suivant récupère les 25 premiers documents qui contiennent l’expression clé « bracket » dans la colonne Document de la table Production.Document de l’exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4064e-118">The following example retrieves the top 25 documents that contain the key phrase "Bracket" from the Document column of the Production.Document table of the AdventureWorks sample database.</span></span>  
  
```sql  
SELECT TOP (25) DOC_TBL.DocumentID, DOC_TBL.DocumentSummary  
FROM Production.Document AS DOC_TBL  
    INNER JOIN SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document  
    ) AS KEYP_TBL  
ON DOC_TBL.DocumentID = KEYP_TBL.document_key  
WHERE KEYP_TBL.keyphrase = 'Bracket'  
ORDER BY KEYP_TBL.Score DESC;  
GO  
```  
  
  
