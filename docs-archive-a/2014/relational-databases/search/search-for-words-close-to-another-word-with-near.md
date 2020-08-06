---
title: Recherche de mots dans le voisinage d’autres mots avec NEAR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- word searches [full-text search]
- NEAR option [full-text search]
- phrase searches [full-text search]
- proximity searches [full-text search]
- full-text search [SQL Server], proximity searches
- full-text queries [SQL Server], proximity
- queries [full-text search], proximity
ms.assetid: 87520646-4865-49ae-8790-f766b80a41f3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c2d187ea3ed951ac6f17eb4babc5f4f77451d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704020"
---
# <a name="search-for-words-close-to-another-word-with-near"></a><span data-ttu-id="67f77-102">Recherche de mots dans le voisinage d'autres mots avec NEAR</span><span class="sxs-lookup"><span data-stu-id="67f77-102">Search for Words Close to Another Word with NEAR</span></span>
  <span data-ttu-id="67f77-103">Vous pouvez utiliser un terme de proximité (NEAR) dans un prédicat [CONTAINS](/sql/t-sql/queries/contains-transact-sql) ou une fonction [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) pour rechercher des mots ou des expressions à proximité les uns des autres.</span><span class="sxs-lookup"><span data-stu-id="67f77-103">You can use a proximity term (NEAR) in a [CONTAINS](/sql/t-sql/queries/contains-transact-sql) predicate or [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) function to search for words or phrases near one another.</span></span> <span data-ttu-id="67f77-104">Vous pouvez également spécifier le nombre maximal de termes de non-recherche qui séparent le premier et le dernier terme de recherche.</span><span class="sxs-lookup"><span data-stu-id="67f77-104">You can also specify the maximum number of non-search terms that separate the first and last search terms.</span></span> <span data-ttu-id="67f77-105">De plus, vous pouvez rechercher des mots ou des expressions dans n'importe quel ordre ou dans un ordre spécifié.</span><span class="sxs-lookup"><span data-stu-id="67f77-105">In addition, you can search for words or phrases in any order, or you can search for words and phrases in the order in which you specify them.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="67f77-106">prend en charge à la fois le [terme de proximité générique](#Generic_NEAR)précédent, qui est maintenant déconseillé et le [terme de proximité personnalisé](#Custom_NEAR), qui est nouveau dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67f77-106">supports both the earlier [generic proximity term](#Generic_NEAR), which is now deprecated, and the [custom proximity term](#Custom_NEAR), which is new in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
##  <a name="the-custom-proximity-term"></a><a name="Custom_NEAR"></a><span data-ttu-id="67f77-107">Terme de proximité personnalisé</span><span class="sxs-lookup"><span data-stu-id="67f77-107">The Custom Proximity Term</span></span>  
 <span data-ttu-id="67f77-108">Le terme de proximité personnalisé présente les nouvelles fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="67f77-108">The custom proximity term introduces the following new capabilities:</span></span>  
  
-   <span data-ttu-id="67f77-109">Vous pouvez spécifier le nombre maximal de termes de non-recherche, ou *distance maximale*, qui sépare le premier et le dernier terme de recherche pour établir une correspondance.</span><span class="sxs-lookup"><span data-stu-id="67f77-109">You can specify the maximum number of non-search terms, or *maximum distance*, that separates the first and last search terms in order to constitute a match.</span></span>  
  
-   <span data-ttu-id="67f77-110">Si vous spécifiez le nombre maximal de termes, vous pouvez également spécifier l'ordre dans lequel les termes de recherche doivent figurer dans les correspondances.</span><span class="sxs-lookup"><span data-stu-id="67f77-110">If you specify the maximum number of terms, you can also specify that matches must contain the search terms in the specified order.</span></span>  
  
 <span data-ttu-id="67f77-111">Pour être une correspondance valide, une chaîne de texte doit :</span><span class="sxs-lookup"><span data-stu-id="67f77-111">To qualify as a match, a string of text must:</span></span>  
  
-   <span data-ttu-id="67f77-112">commencer par l'un des termes de recherche spécifiés et se terminer par l'un des autres termes de recherche spécifiés ;</span><span class="sxs-lookup"><span data-stu-id="67f77-112">Start with one of the specified search terms and end with the one of the other specified search terms.</span></span>  
  
-   <span data-ttu-id="67f77-113">Contenir tous les termes de recherche spécifiés</span><span class="sxs-lookup"><span data-stu-id="67f77-113">Contain all of the specified search terms.</span></span>  
  
-   <span data-ttu-id="67f77-114">le nombre de termes de non-recherche, notamment de mots vides situés entre le premier et le dernier terme de recherche, doit être inférieur ou égal à la distance maximale, si celle-ci est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="67f77-114">The number of non-search terms, including stopwords, that occur between the first and last search terms must be less than or equal to the maximum distance, if specified.</span></span>  
  
 <span data-ttu-id="67f77-115">La syntaxe de base est la suivante :</span><span class="sxs-lookup"><span data-stu-id="67f77-115">The basic syntax is:</span></span>  
  
 <span data-ttu-id="67f77-116">NEAR (</span><span class="sxs-lookup"><span data-stu-id="67f77-116">NEAR (</span></span>  
  
 <span data-ttu-id="67f77-117">{</span><span class="sxs-lookup"><span data-stu-id="67f77-117">{</span></span>  
  
 <span data-ttu-id="67f77-118">*search_term* [,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="67f77-118">*search_term* [ ,...*n* ]</span></span>  
  
 |  
  
 <span data-ttu-id="67f77-119">(*search_term* [,... *n* ]) [, <maximum_distance> [, <match_order>]]</span><span class="sxs-lookup"><span data-stu-id="67f77-119">(*search_term* [ ,...*n* ] ) [, <maximum_distance> [, <match_order> ] ]</span></span>  
  
 <span data-ttu-id="67f77-120">}</span><span class="sxs-lookup"><span data-stu-id="67f77-120">}</span></span>  
  
 <span data-ttu-id="67f77-121">)</span><span class="sxs-lookup"><span data-stu-id="67f77-121">)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67f77-122">Pour plus d’informations sur la syntaxe de <terme_de_proximité_personnalisé>, consultez [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="67f77-122">For more information about the <custom_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="67f77-123">Par exemple, vous pourriez rechercher « John » à deux termes de distance de « Smith », comme suit :</span><span class="sxs-lookup"><span data-stu-id="67f77-123">For example, you could search for 'John' within two terms of 'Smith', as follows:</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((John, Smith), 2)')  
```  
  
 <span data-ttu-id="67f77-124">Les chaînes qui correspondent sont par exemple «`John Jacob Smith`» et «`Smith, John`».</span><span class="sxs-lookup"><span data-stu-id="67f77-124">Some examples of strings that match are "`John Jacob Smith`" and "`Smith, John`".</span></span> <span data-ttu-id="67f77-125">La chaîne «`John Jones knows Fred Smith`» contient trois termes de non-recherche intermédiaires, donc ce n'est pas une correspondance.</span><span class="sxs-lookup"><span data-stu-id="67f77-125">The string "`John Jones knows Fred Smith`" contains three intervening non-search terms, so it is not a match.</span></span>  
  
 <span data-ttu-id="67f77-126">Pour que les termes soient recherchés dans un ordre spécifié, vous pouvez modifier le terme de proximité de l'exemple en `NEAR((John, Smith),2, TRUE).` Cela permet de rechercher «`John`» à deux termes de distance de «`Smith`», mais uniquement à condition que «`John`» précède «`Smith`».</span><span class="sxs-lookup"><span data-stu-id="67f77-126">To require that the terms be found in the specified order, you would change the example proximity term to `NEAR((John, Smith),2, TRUE).` This searches for "`John`" within two terms of "`Smith`" but only when "`John`" precedes "`Smith`".</span></span> <span data-ttu-id="67f77-127">Dans une langue qui se lit de gauche à droite, tel que l'anglais, un exemple de chaîne correspondante est`John Jacob Smith`.</span><span class="sxs-lookup"><span data-stu-id="67f77-127">In a language that reads from left to right, such as English, an example of a string that matches is "`John Jacob Smith`".</span></span>  
  
 <span data-ttu-id="67f77-128">Notez que pour une langue qui se lit de droite à gauche, telle que l'arabe ou l'hébreu, le moteur d'indexation et de recherche en texte intégral applique les termes spécifiés dans l'ordre inverse.</span><span class="sxs-lookup"><span data-stu-id="67f77-128">Note that for a language that reads from right to left, such as Arabic or Hebrew, the Full-Text Engine applies the specified terms in reverse order.</span></span> <span data-ttu-id="67f77-129">De même, l'Explorateur d'objets de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] inverse automatiquement l'ordre d'affichage des mots spécifiés dans les langues s'écrivant de droite à gauche.</span><span class="sxs-lookup"><span data-stu-id="67f77-129">Also, Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] automatically reverses the display order of words specified in right-to-left languages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67f77-130">Pour plus d'informations, consultez « [Considérations supplémentaires concernant les recherches de proximité](#Additional_Considerations) », plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="67f77-130">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="how-maximum-distance-is-measured"></a><span data-ttu-id="67f77-131">Comment mesurer la distance maximale</span><span class="sxs-lookup"><span data-stu-id="67f77-131">How Maximum Distance Is Measured</span></span>  
 <span data-ttu-id="67f77-132">Une distance maximale spécifique, telle que 10 ou 25, détermine combien de termes de non-recherche, notamment les mots vides, peuvent séparer le premier et le dernier terme de recherche dans une chaîne donnée.</span><span class="sxs-lookup"><span data-stu-id="67f77-132">A specific maximum distance, such as 10 or 25, determines how many non-search terms, including stopwords, can occur between the first and last search terms in a given string.</span></span> <span data-ttu-id="67f77-133">Par exemple, `NEAR((dogs, cats, "hunting mice"), 3)` retournerait la ligne suivante, dans laquelle le nombre total de termes de non-recherche est trois («`enjoy`», «`but`» et «`avoid`») :</span><span class="sxs-lookup"><span data-stu-id="67f77-133">For example, `NEAR((dogs, cats, "hunting mice"), 3)` would return the following row, in which the total number of non-search terms is three ("`enjoy`", "`but`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="67f77-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="67f77-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span></span>  
  
 <span data-ttu-id="67f77-135">Le même terme de proximité ne retournerait pas la ligne suivante, car les quatre termes de non-recherche («`enjoy`», «`but`», «`usually`» et «`avoid`») dépassent la distance maximale :</span><span class="sxs-lookup"><span data-stu-id="67f77-135">The same proximity term would not return the following row, because the maximum distance is exceeded by the four non-search terms ("`enjoy`", "`but`", "`usually`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="67f77-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="67f77-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span></span>  
  
### <a name="combining-a-custom-proximity-term-with-other-terms"></a><span data-ttu-id="67f77-137">Combinaison d'un terme de proximité personnalisé avec d'autres termes</span><span class="sxs-lookup"><span data-stu-id="67f77-137">Combining a Custom Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="67f77-138">Vous pouvez combiner un terme de proximité personnalisé avec d'autres termes.</span><span class="sxs-lookup"><span data-stu-id="67f77-138">You can combine a custom proximity term with some other terms.</span></span> <span data-ttu-id="67f77-139">Vous pouvez utiliser AND (&), OR (|) ou AND NOT (&!) pour combiner un terme de proximité personnalisé avec un autre terme de proximité personnalisé, un terme simple ou un terme de préfixe.</span><span class="sxs-lookup"><span data-stu-id="67f77-139">You can use AND (&), OR (|), or AND NOT (&!) to combine a custom proximity term with another custom proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="67f77-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="67f77-140">For example:</span></span>  
  
-   <span data-ttu-id="67f77-141">CONTAINS('NEAR((*terme1*,*terme2*),5) AND *terme3*')</span><span class="sxs-lookup"><span data-stu-id="67f77-141">CONTAINS('NEAR((*term1*,*term2*),5) AND *term3*')</span></span>  
  
-   <span data-ttu-id="67f77-142">CONTAINS('NEAR((*terme1*,*terme2*),5) OR *terme3*')</span><span class="sxs-lookup"><span data-stu-id="67f77-142">CONTAINS('NEAR((*term1*,*term2*),5) OR *term3*')</span></span>  
  
-   <span data-ttu-id="67f77-143">CONTAINS('NEAR((*terme1*,*terme2*),5) AND NOT *terme3*')</span><span class="sxs-lookup"><span data-stu-id="67f77-143">CONTAINS('NEAR((*term1*,*term2*),5) AND NOT *term3*')</span></span>  
  
-   <span data-ttu-id="67f77-144">CONTAINS('NEAR((*terme1*,*terme2*),5) AND NEAR((*terme3*,*terme4*),2)')</span><span class="sxs-lookup"><span data-stu-id="67f77-144">CONTAINS('NEAR((*term1*,*term2*),5) AND NEAR((*term3*,*term4*),2)')</span></span>  
  
-   <span data-ttu-id="67f77-145">CONTAINS('NEAR((*terme1*,*terme2*),5) OR NEAR((*terme3*,*terme4*),2, TRUE)')</span><span class="sxs-lookup"><span data-stu-id="67f77-145">CONTAINS('NEAR((*term1*,*term2*),5) OR NEAR((*term3*,*term4*),2, TRUE)')</span></span>  
  
 <span data-ttu-id="67f77-146">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="67f77-146">For example,</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((term1, term2), 5, TRUE) AND term3')  
```  
  
 <span data-ttu-id="67f77-147">Vous ne pouvez pas combiner un terme de proximité personnalisé avec un terme de proximité générique (*terme1* near *terme2*), un terme de génération (ISABOUT...) ou un terme pondéré (FORMSOF...).</span><span class="sxs-lookup"><span data-stu-id="67f77-147">You cannot combine a custom proximity term with a generic proximity term (*term1* NEAR *term2*), a generation term (ISABOUT ...), or a weighted term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-custom-proximity-term"></a><span data-ttu-id="67f77-148">Exemple : utilisation du terme de proximité personnalisé</span><span class="sxs-lookup"><span data-stu-id="67f77-148">Example: Using the Custom Proximity Term</span></span>  
 <span data-ttu-id="67f77-149">L'exemple suivant recherche dans la table `Production.Document` de l'exemple de base de données `AdventureWorks2012` tous les résumés de document qui contiennent le mot « reflector » dans le même document que le mot « bracket ».</span><span class="sxs-lookup"><span data-stu-id="67f77-149">The following example searches the `Production.Document` table of the `AdventureWorks2012` sample database for all document summaries that contain the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable   
INNER JOIN CONTAINSTABLE(Production.Document, Document,  
  'NEAR(bracket, reflector)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
WHERE KEY_TBL.RANK > 50  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  

  
##  <a name="additional-considerations-for-proximity-searches"></a><a name="Additional_Considerations"></a><span data-ttu-id="67f77-150">Considérations supplémentaires pour les recherches de proximité</span><span class="sxs-lookup"><span data-stu-id="67f77-150">Additional Considerations for Proximity Searches</span></span>  
 <span data-ttu-id="67f77-151">Cette section présente des points à prendre en considération qui concernent à la fois les recherches de proximité génériques et personnalisées :</span><span class="sxs-lookup"><span data-stu-id="67f77-151">This section discusses consideration that affect both generic and custom proximity searches:</span></span>  
  
-   <span data-ttu-id="67f77-152">Chevauchement des occurrences des termes de recherche</span><span class="sxs-lookup"><span data-stu-id="67f77-152">Overlapping occurrences of search terms</span></span>  
  
     <span data-ttu-id="67f77-153">Les recherches de proximité ne cherchent toujours que des occurrences sans chevauchement.</span><span class="sxs-lookup"><span data-stu-id="67f77-153">All proximity searches always look for only non-overlapping occurrences.</span></span> <span data-ttu-id="67f77-154">Les occurrences des termes de recherche qui se chevauchent ne sont jamais validées comme des correspondances.</span><span class="sxs-lookup"><span data-stu-id="67f77-154">Overlapping occurrences of search terms never qualify as matches.</span></span> <span data-ttu-id="67f77-155">Par exemple, supposons le terme de proximité suivant, qui recherche «`A`» et «`AA`», dans cet ordre, à une distance maximale de deux termes :</span><span class="sxs-lookup"><span data-stu-id="67f77-155">For example, consider the following proximity term, which searches "`A`" and "`AA`" in this order with a maximum distance of two terms:</span></span>  
  
    ```  
    CONTAINS(column_name, 'NEAR((A,AA),2, TRUE')  
    ```  
  
     <span data-ttu-id="67f77-156">Les correspondances possibles sont, par exemple, «`AAA`», «`A.AA`» et «`A..AA`».</span><span class="sxs-lookup"><span data-stu-id="67f77-156">The possible matches are as "`AAA`", "`A.AA`", and "`A..AA`".</span></span> <span data-ttu-id="67f77-157">Les lignes contenant simplement «`AA`» ne correspondent pas.</span><span class="sxs-lookup"><span data-stu-id="67f77-157">Rows containing just "`AA`" would not match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="67f77-158">Vous pouvez spécifier des termes qui se chevauchent, par exemple, `NEAR("mountain bike", "bike trails")` ou `(NEAR(comfort*, comfortable), 5)`.</span><span class="sxs-lookup"><span data-stu-id="67f77-158">You can specify terms that overlap, for example, `NEAR("mountain bike", "bike trails")` or `(NEAR(comfort*, comfortable), 5)`.</span></span> <span data-ttu-id="67f77-159">Spécifier des termes qui se chevauchent rend la requête plus complexe en augmentant les permutations de correspondances possibles.</span><span class="sxs-lookup"><span data-stu-id="67f77-159">Specifying a overlapping terms increases the complexity of the query by increasing the possible match permutations.</span></span> <span data-ttu-id="67f77-160">Si vous spécifiez un grand nombre de termes se chevauchant, la requête peut échouer en raison de ressources insuffisantes.</span><span class="sxs-lookup"><span data-stu-id="67f77-160">If you specify a large number of such overlapping terms, the query can run out of resources and fail.</span></span> <span data-ttu-id="67f77-161">Dans ce cas, simplifiez la requête et réessayez.</span><span class="sxs-lookup"><span data-stu-id="67f77-161">If this occurs, simplify the query and try again.</span></span>  
  
-   <span data-ttu-id="67f77-162">NEAR générique et NEAR personnalisé (qu'une distance maximale soit spécifiée ou non) indiquent tous deux la distance logique entre les termes, plutôt que la distance absolue qui les sépare.</span><span class="sxs-lookup"><span data-stu-id="67f77-162">Both generic NEAR and custom NEAR (regardless of whether a maximum distance is specified) indicate the logical distance between terms, rather than the absolute distance between them.</span></span> <span data-ttu-id="67f77-163">Par exemple, les termes des différentes expressions ou phrases d'un paragraphe sont considérés comme plus éloignés que les termes situés dans une même expression ou phrase, indépendamment de leur proximité réelle, en supposant que leur relation soit moins étroite.</span><span class="sxs-lookup"><span data-stu-id="67f77-163">For example, terms within different phrases or sentences within a paragraph are treated as farther apart than terms in the same phrase or sentence, regardless of their actual proximity, on the assumption that they are less related.</span></span> <span data-ttu-id="67f77-164">De même, les termes situés dans des paragraphes différents sont considérés comme étant encore plus éloignés.</span><span class="sxs-lookup"><span data-stu-id="67f77-164">Likewise, terms in different paragraphs are treated as being even farther apart.</span></span> <span data-ttu-id="67f77-165">Si une correspondance comprend la fin d'une phrase, d'un paragraphe ou d'un chapitre, l'intervalle utilisé pour le classement d'un document est augmenté respectivement de 8, 128 ou 1024.</span><span class="sxs-lookup"><span data-stu-id="67f77-165">If a match spans the end of a sentence, paragraph, or chapter, the gap used for ranking a document is increased by 8, 128, or 1024, respectively.</span></span>  
  
-   <span data-ttu-id="67f77-166">Impact des termes de proximité sur le classement par la fonction CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="67f77-166">Impact of proximity terms on ranking by the CONTAINSTABLE function</span></span>  
  
     <span data-ttu-id="67f77-167">Lorsque NEAR est utilisé dans la fonction CONTAINSTABLE, le nombre de résultats dans un document par rapport à sa longueur, ainsi que la distance entre le premier et le dernier terme de recherche dans chacun des résultats, affectent le classement de chaque document.</span><span class="sxs-lookup"><span data-stu-id="67f77-167">When NEAR is used in the CONTAINSTABLE function, the number of hits in a document relative to its length as well as the distance between the first and last search terms in each of the hits affects the ranking of each document.</span></span> <span data-ttu-id="67f77-168">Pour un terme de proximité générique, si les termes de recherche trouvés sont séparés de >50 termes logiques, le classement retourné sur un document est 0.</span><span class="sxs-lookup"><span data-stu-id="67f77-168">For a generic proximity term, if the matched search terms are >50 logical terms apart, the rank returned on a document is 0.</span></span> <span data-ttu-id="67f77-169">Pour un terme de proximité personnalisé qui ne spécifie pas d'entier comme distance maximale, un document qui contient uniquement des résultats à intervalle de >100 termes logiques recevra un classement de 0.</span><span class="sxs-lookup"><span data-stu-id="67f77-169">For a custom proximity term that does not specify an integer as the maximum distance, a document that contains only hits whose gap is >100 logical terms will receive a ranking of 0.</span></span> <span data-ttu-id="67f77-170">Pour plus d'informations sur le classement des recherches de proximité personnalisées, consultez [Limit Search Results with RANK](limit-search-results-with-rank.md).</span><span class="sxs-lookup"><span data-stu-id="67f77-170">For more information about ranking of custom proximity searches, see [Limit Search Results with RANK](limit-search-results-with-rank.md).</span></span>  
  
-   <span data-ttu-id="67f77-171">Option de serveur **Transformer les mots parasites**</span><span class="sxs-lookup"><span data-stu-id="67f77-171">The **transform noise words** server option</span></span>  
  
     <span data-ttu-id="67f77-172">La valeur de l’option **Transformer les mots parasites** influe sur la manière dont [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] traite les mots vides, s’ils sont spécifiés dans les recherches de proximité.</span><span class="sxs-lookup"><span data-stu-id="67f77-172">The value of **transform noise words** impacts how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] treats stopwords if they are specified in proximity searches.</span></span> <span data-ttu-id="67f77-173">Pour plus d’informations, voir [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="67f77-173">For more information, see [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span></span>  
  

  
##  <a name="the-deprecated-generic-proximity-term"></a><a name="Generic_NEAR"></a><span data-ttu-id="67f77-174">Terme de proximité générique déconseillé</span><span class="sxs-lookup"><span data-stu-id="67f77-174">The Deprecated Generic Proximity Term</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="67f77-175">Nous vous recommandons d'utiliser le [terme de proximité personnalisé](#Custom_NEAR).</span><span class="sxs-lookup"><span data-stu-id="67f77-175">We recommend that you use the [custom proximity term](#Custom_NEAR).</span></span>  
  
 <span data-ttu-id="67f77-176">Un terme de proximité générique indique que les termes de recherche spécifiés doivent figurer dans un document pour qu’une correspondance soit retournée, indépendamment du nombre de termes de non-recherche (la *distance*) entre les termes de recherche.</span><span class="sxs-lookup"><span data-stu-id="67f77-176">A generic proximity term indicates that the specified search terms must all occur in a document for a match to be returned, regardless of the number of non-search terms (the *distance*) between the search terms.</span></span> <span data-ttu-id="67f77-177">La syntaxe de base est la suivante :</span><span class="sxs-lookup"><span data-stu-id="67f77-177">The basic syntax is:</span></span>  
  
 <span data-ttu-id="67f77-178">{ *search_term* {near | ~} *search_term* } [ ,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="67f77-178">{ *search_term* { NEAR | ~ } *search_term* } [ ,...*n* ]</span></span>  
  
 <span data-ttu-id="67f77-179">Par exemple, dans les exemples suivants, les mots « fox » et « chicken »doivent apparaître tous les deux, dans n'importe quel ordre, pour qu'une correspondance soit établie :</span><span class="sxs-lookup"><span data-stu-id="67f77-179">For example, in the following examples, the words 'fox' and 'chicken' must both appear, in either order, to produce a match:</span></span>  
  
-   `CONTAINS(column_name, 'fox NEAR chicken')`  
  
-   `CONTAINSTABLE(table_name, column_name, 'fox ~ chicken')`  
  
> [!NOTE]  
>  <span data-ttu-id="67f77-180">Pour plus d’informations sur la syntaxe de <terme_de_proximité_générique>, consultez [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="67f77-180">For information about the <generic_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="67f77-181">Pour plus d'informations, consultez « [Considérations supplémentaires concernant les recherches de proximité](#Additional_Considerations) », plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="67f77-181">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="combining-a-generic-proximity-term-with-other-terms"></a><span data-ttu-id="67f77-182">Combinaison d'un terme de proximité générique avec d'autres termes</span><span class="sxs-lookup"><span data-stu-id="67f77-182">Combining a Generic Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="67f77-183">Vous pouvez utiliser AND (&), OR (|) ou AND NOT (&!) pour combiner un terme de proximité générique avec un autre terme de proximité générique, un terme simple ou un terme de préfixe.</span><span class="sxs-lookup"><span data-stu-id="67f77-183">You can use AND (&), OR (|), or AND NOT (&!) to combine a generic proximity term with another generic proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="67f77-184">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="67f77-184">For example:</span></span>  
  
```  
CONTAINSTABLE (Production.ProductDescription,  
   Description,   
   '(light NEAR aluminum) OR  
   (lightweight NEAR aluminum)'  
)  
```  
  
 <span data-ttu-id="67f77-185">Vous ne pouvez pas combiner un terme de proximité générique avec un terme de proximité personnalisé, tel que `NEAR((term1,term2),5)` , un terme pondéré (ISABOUT...) ou un terme générationnel (FORMSOF...).</span><span class="sxs-lookup"><span data-stu-id="67f77-185">You cannot combine a generic proximity term with a custom proximity term, such as `NEAR((term1,term2),5)`, a weighted term (ISABOUT ...), or a generational term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-generic-proximity-term"></a><span data-ttu-id="67f77-186">Exemple : utilisation du terme de proximité générique</span><span class="sxs-lookup"><span data-stu-id="67f77-186">Example: Using the Generic Proximity Term</span></span>  
 <span data-ttu-id="67f77-187">L'exemple suivant utilise le terme de proximité générique pour rechercher le mot « reflector » dans le même document que le mot « bracket ».</span><span class="sxs-lookup"><span data-stu-id="67f77-187">The following example uses the generic proximity term to search for the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable INNER JOIN  
  CONTAINSTABLE(Production.Document, Document,  
  '(reflector NEAR bracket)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  
 <span data-ttu-id="67f77-188">Notez que vous pouvez aussi inverser l'ordre des termes dans CONTAINSTABLE pour obtenir le même résultat :</span><span class="sxs-lookup"><span data-stu-id="67f77-188">Notice that you can also reverse the terms in CONTAINSTABLE to get the same result:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(bracket NEAR reflector)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="67f77-189">Vous pouvez utiliser le caractère tilde (~) à la place du mot clé NEAR utilisé dans la requête précédente et obtenir les mêmes résultats :</span><span class="sxs-lookup"><span data-stu-id="67f77-189">You can use the tilde character (~) in place of the NEAR keyword in the earlier query, and get the same results:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="67f77-190">Il est possible de spécifier plusieurs mots ou expressions dans les conditions de recherche.</span><span class="sxs-lookup"><span data-stu-id="67f77-190">More than two words or phrases can be specified in the search conditions.</span></span> <span data-ttu-id="67f77-191">Par exemple, il est possible d'écrire :</span><span class="sxs-lookup"><span data-stu-id="67f77-191">For example, it is possible to write:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket ~ installation)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="67f77-192">Cela signifie que « reflector » doit figurer dans le même document que « bracket », et que « bracket » doit figurer dans le même document que « installation ».</span><span class="sxs-lookup"><span data-stu-id="67f77-192">This means that "reflector" must be in the same document as "bracket", and "bracket" must be in the same document as "installation".</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="67f77-193">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67f77-193">See Also</span></span>  
 <span data-ttu-id="67f77-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67f77-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="67f77-195">[Exécuter une requête avec une recherche en texte intégral](query-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="67f77-195">[Query with Full-Text Search](query-with-full-text-search.md) </span></span>  
 [<span data-ttu-id="67f77-196">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="67f77-196">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
