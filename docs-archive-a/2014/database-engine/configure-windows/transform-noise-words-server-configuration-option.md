---
title: transform noise words (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- full-text queries [SQL Server], performance
- transform noise words option
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 69bd388e-a86c-4de4-b5d5-d093424d9c57
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 49de4a381de3e998073a73c284e3e3e5960f4921
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706704"
---
# <a name="transform-noise-words-server-configuration-option"></a><span data-ttu-id="98d49-102">transform noise words (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="98d49-102">transform noise words Server Configuration Option</span></span>
  <span data-ttu-id="98d49-103">Utilisez l' `transform noise words` option de configuration de serveur pour supprimer un message d’erreur si des mots parasites, autrement dit des [mots vides](../../relational-databases/search/full-text-search.md), provoquent le retour de lignes nulles d’une opération booléenne sur une requête de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="98d49-103">Use the `transform noise words` server configuration option to suppress an error message if noise words, that is [stopwords](../../relational-databases/search/full-text-search.md), cause a Boolean operation on a full-text query to return zero rows.</span></span> <span data-ttu-id="98d49-104">Cette option est utile pour les requêtes de texte intégral qui utilisent le prédicat CONTAINS dans lequel les opérations booléennes ou les opérations de proximité (NEAR) incluent des mots parasites.</span><span class="sxs-lookup"><span data-stu-id="98d49-104">This option is useful for full-text queries that use the CONTAINS predicate in which Boolean operations or NEAR operations include noise words.</span></span> <span data-ttu-id="98d49-105">Les valeurs possibles sont décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="98d49-105">The possible values are described in the following table.</span></span>  
  
|<span data-ttu-id="98d49-106">Valeur</span><span class="sxs-lookup"><span data-stu-id="98d49-106">Value</span></span>|<span data-ttu-id="98d49-107">Description</span><span class="sxs-lookup"><span data-stu-id="98d49-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="98d49-108">0</span><span class="sxs-lookup"><span data-stu-id="98d49-108">0</span></span>|<span data-ttu-id="98d49-109">Les mots parasites (ou mots vides) ne sont pas transformés.</span><span class="sxs-lookup"><span data-stu-id="98d49-109">Noise words (or stopwords) are not transformed.</span></span> <span data-ttu-id="98d49-110">Lorsqu'une requête de texte intégral contient des mots parasites, la requête retourne des lignes nulles, et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] génère un avertissement.</span><span class="sxs-lookup"><span data-stu-id="98d49-110">When a full-text query contains noise words, the query returns zero rows, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] raises a warning.</span></span> <span data-ttu-id="98d49-111">Il s'agit du comportement par défaut.</span><span class="sxs-lookup"><span data-stu-id="98d49-111">This is the default behavior.</span></span><br /><br /> <span data-ttu-id="98d49-112">Notez que l’avertissement est un avertissement au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="98d49-112">Note that the warning is a run-time warning.</span></span> <span data-ttu-id="98d49-113">Par conséquent, si la clause de texte intégral dans la requête n'est pas exécutée, l'avertissement n'est pas généré.</span><span class="sxs-lookup"><span data-stu-id="98d49-113">Therefore, if the full-text clause in the query is not executed, the warning is not raised.</span></span> <span data-ttu-id="98d49-114">Pour une requête locale, un seul avertissement est généré, même lorsqu'il y a plusieurs clauses de requêtes de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="98d49-114">For a local query, only one warning is raised, even when there are multiple full-text query clauses.</span></span> <span data-ttu-id="98d49-115">Pour une requête distante, le serveur lié peut ne pas relayer l'erreur ; par conséquent, l'avertissement peut ne pas être généré.</span><span class="sxs-lookup"><span data-stu-id="98d49-115">For a remote query, the linked server might not relay the error; therefore, the warning might not be raised.</span></span>|  
|<span data-ttu-id="98d49-116">1</span><span class="sxs-lookup"><span data-stu-id="98d49-116">1</span></span>|<span data-ttu-id="98d49-117">Les mots parasites (ou mots vides) sont transformés.</span><span class="sxs-lookup"><span data-stu-id="98d49-117">Noise words (or stopwords) are transformed.</span></span> <span data-ttu-id="98d49-118">Ils sont ignorés, et le reste de la requête est évalué.</span><span class="sxs-lookup"><span data-stu-id="98d49-118">They are ignored, and the rest of the query is evaluated.</span></span><br /><br /> <span data-ttu-id="98d49-119">Si des mots parasites sont spécifiés dans un terme de proximité, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] les supprime.</span><span class="sxs-lookup"><span data-stu-id="98d49-119">If noise words are specified in a proximity term, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] removes them.</span></span> <span data-ttu-id="98d49-120">Par exemple, le mot parasite `is` est supprimé de `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, en transformant la requête de recherche en `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span><span class="sxs-lookup"><span data-stu-id="98d49-120">For example, the noise word `is` is removed from `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, transforming the search query into `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span></span> <span data-ttu-id="98d49-121">Notez que `CONTAINS(<column_name>, 'NEAR(hello,is)')` serait transformé en `CONTAINS(<column_name>, hello)` , car il n'existe qu'un seul terme de recherche valide.</span><span class="sxs-lookup"><span data-stu-id="98d49-121">Notice that `CONTAINS(<column_name>, 'NEAR(hello,is)')` would be transformed into simply `CONTAINS(<column_name>, hello)` because there is only one valid search term.</span></span>|  
  
## <a name="effects-of-the-transform-noise-words-setting"></a><span data-ttu-id="98d49-122">Effets du paramètre Transformer les mots parasites</span><span class="sxs-lookup"><span data-stu-id="98d49-122">Effects of the transform noise words Setting</span></span>  
 <span data-ttu-id="98d49-123">Cette section illustre le comportement des requêtes qui contiennent un mot parasite, « `the` », sous les autres paramètres de `transform noise words`.</span><span class="sxs-lookup"><span data-stu-id="98d49-123">This section illustrates the behavior of queries containing a noise word, "`the`", under the alternate settings of `transform noise words`.</span></span>  <span data-ttu-id="98d49-124">Il est supposé que les chaînes de la requête de texte intégral de l'exemple sont exécutées par rapport à une ligne de table qui contient les données suivantes : `[1, "The black cat"]`.</span><span class="sxs-lookup"><span data-stu-id="98d49-124">The sample full-text query strings are assumed to be run against a table row containing the following data: `[1, "The black cat"]`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98d49-125">Tous ces scénarios peuvent générer un avertissement de mot parasite.</span><span class="sxs-lookup"><span data-stu-id="98d49-125">All such scenarios can generate a noise word warning.</span></span>  
  
-   <span data-ttu-id="98d49-126">Avec transform noise words défini sur 0 :</span><span class="sxs-lookup"><span data-stu-id="98d49-126">With transform noise words set to 0:</span></span>  
  
    |<span data-ttu-id="98d49-127">Chaîne de requête</span><span class="sxs-lookup"><span data-stu-id="98d49-127">Query string</span></span>|<span data-ttu-id="98d49-128">Résultats</span><span class="sxs-lookup"><span data-stu-id="98d49-128">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="98d49-129">"`cat`" AND "`the`"</span><span class="sxs-lookup"><span data-stu-id="98d49-129">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="98d49-130">Aucun résultat (Le comportement est le même pour "`the`" AND "`cat`".)</span><span class="sxs-lookup"><span data-stu-id="98d49-130">No results (The behavior is the same for "`the`" AND "`cat`".)</span></span>|  
    |<span data-ttu-id="98d49-131">"`cat`" NEAR "`the`"</span><span class="sxs-lookup"><span data-stu-id="98d49-131">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="98d49-132">Aucun résultat (Le comportement est le même pour "`the`" NEAR "`cat`".)</span><span class="sxs-lookup"><span data-stu-id="98d49-132">No results (The behavior is the same for "`the`" NEAR "`cat`".)</span></span>|  
    |<span data-ttu-id="98d49-133">"`the`" AND NOT "`black`"</span><span class="sxs-lookup"><span data-stu-id="98d49-133">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="98d49-134">Aucun résultat</span><span class="sxs-lookup"><span data-stu-id="98d49-134">No results</span></span>|  
    |<span data-ttu-id="98d49-135">"`black`" AND NOT "`the`"</span><span class="sxs-lookup"><span data-stu-id="98d49-135">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="98d49-136">Aucun résultat</span><span class="sxs-lookup"><span data-stu-id="98d49-136">No results</span></span>|  
  
-   <span data-ttu-id="98d49-137">Avec transform noise words défini sur 1 :</span><span class="sxs-lookup"><span data-stu-id="98d49-137">With transform noise words set to 1:</span></span>  
  
    |<span data-ttu-id="98d49-138">Chaîne de requête</span><span class="sxs-lookup"><span data-stu-id="98d49-138">Query string</span></span>|<span data-ttu-id="98d49-139">Résultats</span><span class="sxs-lookup"><span data-stu-id="98d49-139">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="98d49-140">"`cat`" AND "`the`"</span><span class="sxs-lookup"><span data-stu-id="98d49-140">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="98d49-141">Accès à la ligne portant l'ID 1</span><span class="sxs-lookup"><span data-stu-id="98d49-141">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="98d49-142">"`cat`" NEAR "`the`"</span><span class="sxs-lookup"><span data-stu-id="98d49-142">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="98d49-143">Accès à la ligne portant l'ID 1</span><span class="sxs-lookup"><span data-stu-id="98d49-143">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="98d49-144">"`the`" AND NOT "`black`"</span><span class="sxs-lookup"><span data-stu-id="98d49-144">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="98d49-145">Aucun résultat</span><span class="sxs-lookup"><span data-stu-id="98d49-145">No results</span></span>|  
    |<span data-ttu-id="98d49-146">"`black`" AND NOT "`the`"</span><span class="sxs-lookup"><span data-stu-id="98d49-146">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="98d49-147">Accès à la ligne portant l'ID 1</span><span class="sxs-lookup"><span data-stu-id="98d49-147">Hit for row with ID 1</span></span>|  
  
## <a name="example"></a><span data-ttu-id="98d49-148">Exemple</span><span class="sxs-lookup"><span data-stu-id="98d49-148">Example</span></span>  
 <span data-ttu-id="98d49-149">L'exemple suivant affecte la valeur `1` à `transform noise words`.</span><span class="sxs-lookup"><span data-stu-id="98d49-149">The following example sets `transform noise words` to `1`.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
GO  
sp_configure 'transform noise words', 1;  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="98d49-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98d49-150">See Also</span></span>  
 <span data-ttu-id="98d49-151">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98d49-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="98d49-152">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98d49-152">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
