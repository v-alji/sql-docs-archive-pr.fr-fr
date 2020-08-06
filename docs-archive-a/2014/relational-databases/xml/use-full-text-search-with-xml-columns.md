---
title: Utiliser la recherche en texte intégral avec des colonnes XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml columns [full-text search]
- indexes [full-text search]
ms.assetid: 8096cfc6-1836-4ed5-a769-a5d63b137171
author: rothja
ms.author: jroth
ms.openlocfilehash: 2b6b23933fde6a09d043c7055b0daa7c07035cdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697587"
---
# <a name="use-full-text-search-with-xml-columns"></a><span data-ttu-id="fe8dc-102">Utiliser la recherche en texte intégral avec des colonnes XML</span><span class="sxs-lookup"><span data-stu-id="fe8dc-102">Use Full-Text Search with XML Columns</span></span>
  <span data-ttu-id="fe8dc-103">Vous pouvez créer un index de texte intégral sur des colonnes XML de façon à indexer le contenu des valeurs XML tout en ignorant le balisage XML.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-103">You can create a full-text index on XML columns that indexes the content of the XML values, but ignores the XML markup.</span></span> <span data-ttu-id="fe8dc-104">Des balises d'éléments sont utilisées comme limites de jeton.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-104">Element tags are used as token boundaries.</span></span> <span data-ttu-id="fe8dc-105">Les éléments suivants sont indexés :</span><span class="sxs-lookup"><span data-stu-id="fe8dc-105">The following items are indexed:</span></span>  
  
-   <span data-ttu-id="fe8dc-106">Contenu des éléments XML.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-106">The content of XML elements.</span></span>  
  
-   <span data-ttu-id="fe8dc-107">Contenu des attributs XML de l'élément de premier niveau uniquement, à moins qu'il ne s'agisse de valeurs numériques.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-107">The content of XML attributes of the top-level element only, unless those values are numeric values.</span></span>  
  
 <span data-ttu-id="fe8dc-108">Lorsque cela est possible, vous pouvez associer une recherche en texte intégral et un index XML. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fe8dc-108">When possible, you can combine full-text search with XML index in the following way:</span></span>  
  
1.  <span data-ttu-id="fe8dc-109">Tout d'abord, filtrez les valeurs XML pertinentes à l'aide d'une recherche en texte intégral SQL.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-109">First, filter the XML values of interest by using SQL full-text search.</span></span>  
  
2.  <span data-ttu-id="fe8dc-110">Ensuite, interrogez les valeurs XML pour lesquelles il existe un index XML sur la colonne XML.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-110">Next, query those XML values that use XML index on the XML column.</span></span>  
  
## <a name="example-combining-full-text-search-with-xml-querying"></a><span data-ttu-id="fe8dc-111">Exemple : Association d’une recherche en texte intégral avec une requête XML</span><span class="sxs-lookup"><span data-stu-id="fe8dc-111">Example: Combining Full-text Search with XML Querying</span></span>  
 <span data-ttu-id="fe8dc-112">Une fois l'index de texte intégral créé sur la colonne XML, la requête suivante recherche une valeur XML contenant le mot « custom » dans le titre d'un livre :</span><span class="sxs-lookup"><span data-stu-id="fe8dc-112">After the full-text index has been created on the XML column, the following query checks that an XML value contains the word "custom" in the title of a book:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'custom')   
AND    xCol.exist('/book/title/text()[contains(.,"custom")]') =1  
```  
  
 <span data-ttu-id="fe8dc-113">La méthode **contains()** utilise l’index de texte intégral pour créer un sous-ensemble de valeurs XML contenant le mot « custom » à un endroit quelconque du document.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-113">The **contains()** method uses the full-text index to subset the XML values that contain the word "custom" anywhere in the document.</span></span> <span data-ttu-id="fe8dc-114">La clause **exist()** vérifie que le mot « custom » apparaît dans le titre d’un livre.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-114">The **exist()** clause ensures that the word "custom" occurs in the title of a book.</span></span>  
  
 <span data-ttu-id="fe8dc-115">Une recherche en texte intégral qui utilise **contains()** et la fonction XQuery **contains()** ont des sémantiques différentes.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-115">A full-text search that uses **contains()** and XQuery **contains()** has different semantics.</span></span> <span data-ttu-id="fe8dc-116">La dernière cherche à établir une concordance de sous-chaîne tandis que la première fait appel à la correspondance de mot clé avec extraction de radical.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-116">The latter is a substring match and the former is a token match that uses stemming.</span></span> <span data-ttu-id="fe8dc-117">Par conséquent, si la recherche porte sur la chaîne où figure « run » dans le titre, les équivalences incluront « run », « runs » et « running » puisque la recherche en texte intégral **contains()** et la fonction Xquery **contains()** sont toutes deux satisfaites.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-117">Therefore, if the search is for the string that has "run" in the title, the matches will include "run", "runs", and "running", because both the full-text **contains()** and the Xquery **contains()** are satisfied.</span></span> <span data-ttu-id="fe8dc-118">En revanche, la requête ne trouve pas le mot « customizable » dans le titre, car la recherche en texte intégral **contains()** échoue et la fonction Xquery **contains()** est satisfaite.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-118">However, the query does not match the word "customizable" in the title in that the full-text **contains()** fails, but the Xquery **contains()** is satisfied.</span></span> <span data-ttu-id="fe8dc-119">Généralement, pour une pure concordance de sous-chaîne, la clause **contains()** de texte intégral doit être supprimée.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-119">Generally, for pure substring match, the full-text **contains()** clause should be removed.</span></span>  
  
 <span data-ttu-id="fe8dc-120">De plus, la recherche en texte intégral se sert de l’extraction de radical tandis que la fonction XQuery **contains()** attend une correspondance littérale.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-120">Additionally, full-text search uses word stemming, but XQuery **contains()** is a literal match.</span></span> <span data-ttu-id="fe8dc-121">Cette différence est expliquée dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-121">This difference is illustrated in the next example.</span></span>  
  
## <a name="example-full-text-search-on-xml-values-using-stemming"></a><span data-ttu-id="fe8dc-122">Exemple : Recherche en texte intégral sur des valeurs XML à l’aide de l’extraction de radical</span><span class="sxs-lookup"><span data-stu-id="fe8dc-122">Example: Full-text Search on XML Values Using Stemming</span></span>  
 <span data-ttu-id="fe8dc-123">La vérification XQuery **contains()** exécutée dans l’exemple précédent ne peut généralement pas être éliminée.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-123">The XQuery **contains()** check that was performed in the previous example generally cannot be eliminated.</span></span> <span data-ttu-id="fe8dc-124">Prenons par exemple la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="fe8dc-124">Consider this query:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'run')   
```  
  
 <span data-ttu-id="fe8dc-125">Le mot « ran » du document correspond aux critères de recherche du fait de l'extraction de radical.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-125">The word "ran" in the document matches the search condition because of stemming.</span></span> <span data-ttu-id="fe8dc-126">De plus, le contexte de recherche n'est pas vérifié à l'aide de XQuery.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-126">Additionally, the search context is not checked by using XQuery.</span></span>  
  
 <span data-ttu-id="fe8dc-127">Lorsque le code XML est décomposé, à l'aide de AXSD, dans des colonnes relationnelles indexées en texte intégral, les requêtes XPath qui portent sur la vue XML ne lancent pas une recherche en texte intégral sur les tables sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="fe8dc-127">When XML is decomposed into relational columns by using AXSD that are full-text indexed, XPath queries that occur over the XML view do not perform full-text search on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe8dc-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe8dc-128">See Also</span></span>  
 [<span data-ttu-id="fe8dc-129">Index XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe8dc-129">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
