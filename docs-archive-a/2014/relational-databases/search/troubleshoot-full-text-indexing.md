---
title: Résoudre l’indexation de texte intégral | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- indexes [full-text search]
- troubleshooting [SQL Server], full-text search
- troubleshooting [full-text search]
ms.assetid: 964c43a8-5019-4179-82aa-63cd0ef592ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eaca5fcf2dfbac57fc6d3ba6178251927d15aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614469"
---
# <a name="troubleshoot-full-text-indexing"></a><span data-ttu-id="e5d81-102">Résoudre l’indexation de texte intégral</span><span class="sxs-lookup"><span data-stu-id="e5d81-102">Troubleshoot Full-Text Indexing</span></span>
     
##  <a name="troubleshoot-full-text-indexing-failures"></a><a name="failure"></a> <span data-ttu-id="e5d81-103">Dépanner les échecs de l'indexation de texte intégral</span><span class="sxs-lookup"><span data-stu-id="e5d81-103">Troubleshoot Full-Text Indexing Failures</span></span>  
 <span data-ttu-id="e5d81-104">Lors du remplissage ou de la gestion d'un index de recherche en texte intégral, il est possible que l'indexeur de texte intégral, pour les raisons détaillées ci-dessous, ne parvienne pas à indexer une ou plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="e5d81-104">While populating or maintaining a full-text index, the full-text indexer, for reasons described below, might fail to index one or more rows.</span></span> <span data-ttu-id="e5d81-105">Ces erreurs au niveau des lignes n'empêchent pas l'achèvement du remplissage.</span><span class="sxs-lookup"><span data-stu-id="e5d81-105">These row-level errors do not prevent the population from completing.</span></span> <span data-ttu-id="e5d81-106">L'indexeur ignore ces lignes, et leur contenu ne peut donc pas être interrogé.</span><span class="sxs-lookup"><span data-stu-id="e5d81-106">The indexer skips these rows, which means that you are not able to query for content contained in these rows.</span></span>  
  
 <span data-ttu-id="e5d81-107">Les défaillances d'indexation peuvent se produire dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="e5d81-107">Indexing failures can occur when:</span></span>  
  
-   <span data-ttu-id="e5d81-108">L'indexeur ne peut pas trouver ou charger un composant de filtre ou d'analyseurs lexicaux.</span><span class="sxs-lookup"><span data-stu-id="e5d81-108">The indexer cannot find or load a filter or word breaker component.</span></span> <span data-ttu-id="e5d81-109">Ce problème peut se produire si la ligne de la table contient un format de document ou un contenu dans une langue qui n'a pas été inscrite avec l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5d81-109">This failure can occur if the table row contains a document format or content in a language that has not been registered with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e5d81-110">Il peut également se produire si le composant inscrit de l'analyseur lexical ou du filtre n'est pas signé, ou en cas d'échec de la vérification de la signature lors de son chargement.</span><span class="sxs-lookup"><span data-stu-id="e5d81-110">This failure can also happen if the registered word breaker or filter component was not signed or failed signature verification when it was being loaded.</span></span>  
  
-   <span data-ttu-id="e5d81-111">Un composant, par exemple un analyseur lexical ou un filtre, échoue et renvoie une erreur à l'indexeur.</span><span class="sxs-lookup"><span data-stu-id="e5d81-111">A component, such as a word breaker or filter, fails and returns an error to the indexer.</span></span> <span data-ttu-id="e5d81-112">Cette situation peut se produire si le document en cours d'indexation est endommagé, interdisant au filtre d'extraire le texte du document.</span><span class="sxs-lookup"><span data-stu-id="e5d81-112">This can happen if the document being indexed is corrupt and the filter is unable to extract text from the document.</span></span> <span data-ttu-id="e5d81-113">Elle peut également survenir lorsqu'un composant est incapable de traiter le contenu d'une même ligne au-delà d'une certaine taille, en raison de limitations de mémoire sur l'hôte de démon de filtre de texte intégral (fdhost.exe).</span><span class="sxs-lookup"><span data-stu-id="e5d81-113">This can also occur when a component is unable to handle the content of a single row above a certain size, due to memory limits on the full-text filter daemon host (fdhost.exe).</span></span>  
  
 <span data-ttu-id="e5d81-114">Pour chaque défaillance au niveau d'une ligne, le journal de l'analyse contient des détails sur les raisons qui l'ont provoquée.</span><span class="sxs-lookup"><span data-stu-id="e5d81-114">For each row-level failure, the crawl log contains details on the reason for the failure.</span></span> <span data-ttu-id="e5d81-115">Le nombre d'erreurs est résumé à la fin d'un remplissage complet ou incrémentiel.</span><span class="sxs-lookup"><span data-stu-id="e5d81-115">The error counts are summarized at the end of a full or incremental population.</span></span>  
  
 <span data-ttu-id="e5d81-116">D'autres défaillances peuvent avoir un effet sur le processus d'indexation lui-même et empêcher l'achèvement du remplissage :</span><span class="sxs-lookup"><span data-stu-id="e5d81-116">There are other failures that can impact the indexing process itself and prevent the population from completing:</span></span>  
  
-   <span data-ttu-id="e5d81-117">L'index de texte intégral dépasse le nombre maximal de lignes admissibles dans un catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="e5d81-117">The full-text index exceeds the limit for the number of rows that can be contained in a full-text catalog.</span></span>  
  
-   <span data-ttu-id="e5d81-118">Un index cluster ou un index clé de texte intégral sur la table en cours d'indexation est modifié, supprimé ou reconstruit.</span><span class="sxs-lookup"><span data-stu-id="e5d81-118">A clustered index or full-text key index on the table being indexed gets altered, dropped, or rebuilt.</span></span>  
  
-   <span data-ttu-id="e5d81-119">Une défaillance matérielle ou l'endommagement d'un disque provoque l'endommagement du catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="e5d81-119">A hardware failure or disk corruption results in the corruption of the full-text catalog.</span></span>  
  
-   <span data-ttu-id="e5d81-120">Un groupe de fichiers contenant la table en cours d'indexation de texte intégral est mis hors ligne ou en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e5d81-120">A file group that contains the table being full-text indexed goes offline, or is made read-only.</span></span>  
  
 <span data-ttu-id="e5d81-121">Il convient de consulter le journal d'analyse à la fin de toutes les opérations lourdes de remplissage d'index de texte intégral ou lorsqu'un remplissage ne s'est pas achevé.</span><span class="sxs-lookup"><span data-stu-id="e5d81-121">You should view the crawl log at the end of any significant full-text index population operation, or when you find that a population did not complete.</span></span>  
  
### <a name="unsigned-components"></a><span data-ttu-id="e5d81-122">Composants non signés</span><span class="sxs-lookup"><span data-stu-id="e5d81-122">Unsigned Components</span></span>  
 <span data-ttu-id="e5d81-123">Par défaut, l'indexeur de texte intégral requiert que les filtres et les analyseurs lexicaux qu'il charge soient signés.</span><span class="sxs-lookup"><span data-stu-id="e5d81-123">By default, the full-text indexer requires the filters and word breakers that it loads to be signed.</span></span> <span data-ttu-id="e5d81-124">S'ils ne sont pas signés, ce qui arrive parfois lorsque des composants personnalisés sont installés, vous devez configurer l'indexeur de texte intégral pour qu'il ignore la vérification de signature.</span><span class="sxs-lookup"><span data-stu-id="e5d81-124">If they are not signed, which is the case sometimes when custom components are installed, you must configure the full-text indexer to ignore signature verification.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e5d81-125">Le fait d'ignorer la vérification de signature réduit la sécurité de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5d81-125">Ignoring signature verification makes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] less secure.</span></span> <span data-ttu-id="e5d81-126">Il est recommandé de signer tous les composants que vous implémentez ou de vérifier que tous les composants que vous achetez sont signés.</span><span class="sxs-lookup"><span data-stu-id="e5d81-126">We recommend that you sign any components that you implement or ensure that any components that you acquire are signed.</span></span> <span data-ttu-id="e5d81-127">Pour plus d’informations sur la signature des composants, consultez [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e5d81-127">For information about signing components, see [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  

  
##  <a name="full-text-index-in-inconsistent-state-after-transaction-log-restored"></a><a name="state"></a> <span data-ttu-id="e5d81-128">Index de recherche en texte intégral dans un état non cohérent une fois le journal des transactions restauré</span><span class="sxs-lookup"><span data-stu-id="e5d81-128">Full-Text Index in Inconsistent State after Transaction Log Restored</span></span>  
 <span data-ttu-id="e5d81-129">Lors de la restauration du journal des transactions d'une base de données, il arrive qu'un message d'avertissement s'affiche en indiquant que l'index de recherche en texte intégral n'est pas dans un état cohérent.</span><span class="sxs-lookup"><span data-stu-id="e5d81-129">When restoring the transaction log of a database, you might see a warning indicating that the full-text index is not in a consistent state.</span></span> <span data-ttu-id="e5d81-130">Cela se produit lorsque l'index de recherche en texte intégral d'une table est modifié après la sauvegarde de la base de données.</span><span class="sxs-lookup"><span data-stu-id="e5d81-130">The reason for this is that the full-text index on a table was modified after the database was backed up.</span></span> <span data-ttu-id="e5d81-131">Pour rendre un état cohérent à l'index de recherche en texte intégral, vous devez exécuter un remplissage complet (analyse) sur la table.</span><span class="sxs-lookup"><span data-stu-id="e5d81-131">To bring the full-text index to a consistent state, you must run a full population (crawl) on the table.</span></span> <span data-ttu-id="e5d81-132">Pour plus d’informations, consultez [Alimenter des index de recherche en texte intégral](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e5d81-132">For more information, see [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="e5d81-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5d81-133">See Also</span></span>  
 <span data-ttu-id="e5d81-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e5d81-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="e5d81-135">Alimenter des index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="e5d81-135">Populate Full-Text Indexes</span></span>](../indexes/indexes.md)  
  
  
