---
title: MSSQLSERVER_30053 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 8ad23889-e243-4bd7-bc3e-150403399d89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 02d6262f93ef3dbbc9834053f864046b4dca30f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605486"
---
# <a name="mssqlserver_30053"></a><span data-ttu-id="86a8c-102">MSSQLSERVER_30053</span><span class="sxs-lookup"><span data-stu-id="86a8c-102">MSSQLSERVER_30053</span></span>
    
## <a name="details"></a><span data-ttu-id="86a8c-103">Détails</span><span class="sxs-lookup"><span data-stu-id="86a8c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86a8c-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="86a8c-104">Product Name</span></span>|<span data-ttu-id="86a8c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="86a8c-105">SQL Server</span></span>|  
|<span data-ttu-id="86a8c-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="86a8c-106">Event ID</span></span>|<span data-ttu-id="86a8c-107">30053</span><span class="sxs-lookup"><span data-stu-id="86a8c-107">30053</span></span>|  
|<span data-ttu-id="86a8c-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="86a8c-108">Event Source</span></span>|<span data-ttu-id="86a8c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="86a8c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="86a8c-110">Composant</span><span class="sxs-lookup"><span data-stu-id="86a8c-110">Component</span></span>|<span data-ttu-id="86a8c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="86a8c-111">SQLEngine</span></span>|  
|<span data-ttu-id="86a8c-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="86a8c-112">Symbolic Name</span></span>|<span data-ttu-id="86a8c-113">FTXT_QUERY_E_WORDBREAKINGTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="86a8c-113">FTXT_QUERY_E_WORDBREAKINGTIMEOUT</span></span>|  
|<span data-ttu-id="86a8c-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="86a8c-114">Message Text</span></span>|<span data-ttu-id="86a8c-115">L'analyse lexicale a expiré pour la chaîne de requête de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="86a8c-115">Word breaking timed out for the full-text query string.</span></span> <span data-ttu-id="86a8c-116">Cela peut se produire si l'analyseur lexical a mis beaucoup de temps à traiter la chaîne de requête de texte intégral ou si un grand nombre de requêtes sont exécutées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="86a8c-116">This can happen if the wordbreaker took a long time to process the full-text query string, or if a large number of queries are running on the server.</span></span> <span data-ttu-id="86a8c-117">Essayez de réexécuter la requête en condition de charge moins élevée.</span><span class="sxs-lookup"><span data-stu-id="86a8c-117">Try running the query again under a lighter load.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="86a8c-118">Explication</span><span class="sxs-lookup"><span data-stu-id="86a8c-118">Explanation</span></span>  
 <span data-ttu-id="86a8c-119">Une erreur de dépassement de délai de l'analyse lexicale peut se produire dans les cas de figure suivants :</span><span class="sxs-lookup"><span data-stu-id="86a8c-119">A word-breaking timeout error can occur in the following situations:</span></span>  
  
-   <span data-ttu-id="86a8c-120">L'analyseur lexical pour le langage de requête est configuré de manière incorrecte ; par exemple, ses paramètres du Registre sont incorrects.</span><span class="sxs-lookup"><span data-stu-id="86a8c-120">The word breaker for the query language is configured incorrectly; for example, its registry settings are incorrect.</span></span>  
  
-   <span data-ttu-id="86a8c-121">L'analyseur lexical présente des dysfonctionnements pour une chaîne de requête spécifique.</span><span class="sxs-lookup"><span data-stu-id="86a8c-121">The word breaker malfunctions for a specific query string.</span></span>  
  
-   <span data-ttu-id="86a8c-122">L'analyseur lexical retourne une trop grande quantité de données pour une chaîne de requête spécifique.</span><span class="sxs-lookup"><span data-stu-id="86a8c-122">The word breaker returns too much data for a specific query string.</span></span> <span data-ttu-id="86a8c-123">Les données excédentaires sont considérées comme une attaque de dépassement de mémoire tampon potentielle, ce qui entraîne l'arrêt du processus de démon de filtre (fdhost.exe), qui héberge les services d'analyse lexicale.</span><span class="sxs-lookup"><span data-stu-id="86a8c-123">Excess data is treated as a potential buffer overrun attack, and shuts down the filter daemon process (fdhost.exe), which hosts the word-breaking services.</span></span>  
  
-   <span data-ttu-id="86a8c-124">La configuration du processus de démon de filtre est incorrecte.</span><span class="sxs-lookup"><span data-stu-id="86a8c-124">The filter daemon process configuration is incorrect.</span></span>  
  
     <span data-ttu-id="86a8c-125">Les problèmes de configuration les plus courants sont les suivants : expiration du mot de passe ou existence d'une stratégie de domaine qui empêche la connexion du compte de démon de filtre.</span><span class="sxs-lookup"><span data-stu-id="86a8c-125">The most common configuration problems are password expiration or a domain policy that prevents the filter daemon account from logging on.</span></span>  
  
-   <span data-ttu-id="86a8c-126">Une charge de travail de requête très importante s'exécute sur l'instance de serveur ; par exemple, l'analyseur lexical prend beaucoup de temps pour traiter la chaîne de requête de texte intégral, ou un grand nombre de requêtes s'exécutent sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="86a8c-126">A very heavy query workload is running on the server instance; for example, the word-breaker took a long time to process the full-text query string, or a large number of queries are running on the server.</span></span> <span data-ttu-id="86a8c-127">Notez qu'il s'agit de la cause la plus improbable.</span><span class="sxs-lookup"><span data-stu-id="86a8c-127">Note that this is the least likely cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="86a8c-128">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="86a8c-128">User Action</span></span>  
 <span data-ttu-id="86a8c-129">Sélectionnez l'action utilisateur appropriée en fonction de la cause probable du délai d'attente, comme suit :</span><span class="sxs-lookup"><span data-stu-id="86a8c-129">Select the user action that is appropriate to the probable cause of the timeout, as follows:</span></span>  
  
|<span data-ttu-id="86a8c-130">Cause probable</span><span class="sxs-lookup"><span data-stu-id="86a8c-130">Probable cause</span></span>|<span data-ttu-id="86a8c-131">Action requise</span><span class="sxs-lookup"><span data-stu-id="86a8c-131">User action</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="86a8c-132">L'analyseur lexical du langage de requête est configuré de manière incorrecte.</span><span class="sxs-lookup"><span data-stu-id="86a8c-132">The word breaker for the query language is configured incorrectly.</span></span>|<span data-ttu-id="86a8c-133">Si vous utilisez un analyseur lexical tiers, il est peut-être enregistré de manière incorrecte auprès du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="86a8c-133">If you are using a third-party word breaker it might be incorrectly registered with the operating system.</span></span> <span data-ttu-id="86a8c-134">Dans ce cas, réenregistrez l'analyseur lexical.</span><span class="sxs-lookup"><span data-stu-id="86a8c-134">In this case, re-register the word breaker.</span></span> <span data-ttu-id="86a8c-135">Pour plus d’informations, consultez [Rétablir la version précédente des analyseurs lexicaux utilisés par la recherche](../search/revert-the-word-breakers-used-by-search-to-the-previous-version.md).</span><span class="sxs-lookup"><span data-stu-id="86a8c-135">For more information, see [Revert the Word Breakers Used by Search to the Previous Version](../search/revert-the-word-breakers-used-by-search-to-the-previous-version.md).</span></span>|  
|<span data-ttu-id="86a8c-136">L'analyseur lexical présente des dysfonctionnements pour une chaîne de requête spécifique.</span><span class="sxs-lookup"><span data-stu-id="86a8c-136">The word breaker malfunctions for a specific query string.</span></span>|<span data-ttu-id="86a8c-137">Si l'analyseur lexical est pris en charge par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contactez le service clientèle et le support technique Microsoft.</span><span class="sxs-lookup"><span data-stu-id="86a8c-137">If the word breaker is supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contact Microsoft Customer Service and Support.</span></span>|  
|<span data-ttu-id="86a8c-138">L'analyseur lexical retourne une trop grande quantité de données pour une chaîne de requête spécifique.</span><span class="sxs-lookup"><span data-stu-id="86a8c-138">The word breaker returns too much data for a specific query string.</span></span>|<span data-ttu-id="86a8c-139">Si l'analyseur lexical est pris en charge par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contactez le service clientèle et le support technique Microsoft.</span><span class="sxs-lookup"><span data-stu-id="86a8c-139">If the word breaker is supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contact Microsoft Customer Service and Support.</span></span>|  
|<span data-ttu-id="86a8c-140">La configuration du processus de démon de filtre est incorrecte.</span><span class="sxs-lookup"><span data-stu-id="86a8c-140">The filter daemon process configuration is incorrect.</span></span>|<span data-ttu-id="86a8c-141">Assurez-vous que vous utilisez le mot de passe actuel et qu'une stratégie de domaine n'empêche pas le compte du démon du filtre de se connecter.</span><span class="sxs-lookup"><span data-stu-id="86a8c-141">Ensure that you are using the current password and that a domain policy is not preventing the filter daemon account from logging on.</span></span>|  
|<span data-ttu-id="86a8c-142">Une charge de traitement de requêtes très importante s'exécute sur l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="86a8c-142">A very heavy query workload is running on the server instance.</span></span>|<span data-ttu-id="86a8c-143">Essayez de réexécuter la requête en condition de charge moins élevée.</span><span class="sxs-lookup"><span data-stu-id="86a8c-143">Try running the query again under a lighter load.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86a8c-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="86a8c-144">See Also</span></span>  
 <span data-ttu-id="86a8c-145">[Définir le compte de service du lanceur de démon de filtre de texte intégral](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="86a8c-145">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="86a8c-146">[Recherche en texte intégral](../search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="86a8c-146">[Full-Text Search](../search/full-text-search.md) </span></span>  
 <span data-ttu-id="86a8c-147">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="86a8c-147">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="86a8c-148">[Configurer et gérer les analyseurs lexicaux et les générateurs de formes dérivées pour la recherche](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="86a8c-148">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="86a8c-149">Configurer et gérer des filtres pour la recherche</span><span class="sxs-lookup"><span data-stu-id="86a8c-149">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
