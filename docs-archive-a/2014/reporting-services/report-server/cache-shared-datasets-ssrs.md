---
title: Mettre en cache les datasets partagés (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4acb1bbe-1c04-4979-b893-dc1b1c5039b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5b08149b075ae3fd267baf2dad0ca342457958c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611568"
---
# <a name="cache-shared-datasets-ssrs"></a><span data-ttu-id="09b49-102">Mettre en cache les datasets partagés (SSRS)</span><span class="sxs-lookup"><span data-stu-id="09b49-102">Cache Shared Datasets (SSRS)</span></span>
  <span data-ttu-id="09b49-103">Les résultats de la requête pour un dataset partagé peuvent être copiés vers un cache afin de fournir des données cohérentes pour plusieurs rapports et améliorer le temps de réponse pour la requête de dataset.</span><span class="sxs-lookup"><span data-stu-id="09b49-103">Query results for a shared dataset can be copied to a cache to provide consistent data for multiple reports and to improve response time for the dataset query.</span></span> <span data-ttu-id="09b49-104">Comme pour les rapports, vous pouvez configurer un dataset partagé à mettre en cache lors de la première utilisation ou en spécifiant une planification.</span><span class="sxs-lookup"><span data-stu-id="09b49-104">Like reports, you can configure a shared dataset to be cached on first use or by specifying a schedule.</span></span>  
  
 <span data-ttu-id="09b49-105">Un dataset partagé peut être inclus dans plusieurs rapports ou dans le cadre de définitions de composant.</span><span class="sxs-lookup"><span data-stu-id="09b49-105">A shared dataset can be included in multiple reports or as part of component definitions.</span></span> <span data-ttu-id="09b49-106">En mettant en cache le dataset partagé, vous fournissez un jeu cohérent de données pour tous les rapports qui l'utilisent, et vous réduisez également le nombre d'exécution de la requête de dataset par rapport à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="09b49-106">By caching the shared dataset, you provide a consistent set of data for all reports that use it, and also reduce the number of times that the dataset query runs against the external data source.</span></span>  
  
 <span data-ttu-id="09b49-107">La liste suivante fournit des exemples de situations dans lesquelles il convient de mettre en cache un dataset partagé :</span><span class="sxs-lookup"><span data-stu-id="09b49-107">The following list provides examples of when to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="09b49-108">La requête met longtemps à s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="09b49-108">The query takes a substantial amount of time to run.</span></span>  
  
-   <span data-ttu-id="09b49-109">La requête accepte des paramètres, mais la plupart du temps, le nombre de combinaisons de paramètres est réduit.</span><span class="sxs-lookup"><span data-stu-id="09b49-109">The query takes parameters, but most of the time, the number of parameter combinations is small.</span></span> <span data-ttu-id="09b49-110">Chaque combinaison crée des résultats de requête mis en cache.</span><span class="sxs-lookup"><span data-stu-id="09b49-110">Each combination creates cached query results.</span></span>  
  
-   <span data-ttu-id="09b49-111">La requête s'exécute à des heures prédictibles du jour, de la semaine ou du mois.</span><span class="sxs-lookup"><span data-stu-id="09b49-111">The query runs at predictable times of the day, week, or month.</span></span>  
  
-   <span data-ttu-id="09b49-112">La requête s'exécute comme le résultat d'une référence de dataset partagé dans un rapport remis via la messagerie électronique, où un grand nombre de personnes sont susceptibles de cliquer sur le lien dans une courte plage horaire.</span><span class="sxs-lookup"><span data-stu-id="09b49-112">The query runs as the result of a shared dataset reference in a report that is delivered via e-mail, where a large number of people are likely to click the link in a short span of time.</span></span>  
  
-   <span data-ttu-id="09b49-113">La liste suivante fournit des exemples de situations dans lesquelles il ne convient pas de mettre en cache un dataset partagé :</span><span class="sxs-lookup"><span data-stu-id="09b49-113">The following list provides examples of when not to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="09b49-114">Les résultats de la requête doivent toujours inclure les données les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="09b49-114">The query results must always include the most recent data.</span></span>  
  
-   <span data-ttu-id="09b49-115">La requête s'exécute rapidement.</span><span class="sxs-lookup"><span data-stu-id="09b49-115">The query runs quickly.</span></span>  
  
-   <span data-ttu-id="09b49-116">La requête s'exécute peu souvent.</span><span class="sxs-lookup"><span data-stu-id="09b49-116">The query runs infrequently.</span></span>  
  
-   <span data-ttu-id="09b49-117">La requête accepte des paramètres, le nombre de combinaisons de paramètres est élevé, et aucune combinaison n'est plus probable qu'une autre.</span><span class="sxs-lookup"><span data-stu-id="09b49-117">The query takes parameters, the number of parameter combinations is large, and no combination is more likely than another.</span></span>  
  
-   <span data-ttu-id="09b49-118">La source de données sur laquelle est basé le dataset partagé a une Invite ou des informations d'identification intégrées de Windows.</span><span class="sxs-lookup"><span data-stu-id="09b49-118">The data source that the shared dataset is based on has Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="09b49-119">Le filtre de dataset partagé ou la requête contient une expression avec une référence à la collection globale Utilisateur.</span><span class="sxs-lookup"><span data-stu-id="09b49-119">The shared dataset filter or the query contains an expression with a reference to the global collection User.</span></span>  
  
 <span data-ttu-id="09b49-120">Si un utilisateur choisit des valeurs de paramètre de rapport qui diffèrent des valeurs par défaut spécifiées pour le jeu de résultats mis en cache, la requête de dataset s'exécute activement et les résultats mis en cache ne sont pas utilisés pour cette requête.</span><span class="sxs-lookup"><span data-stu-id="09b49-120">If a user chooses report parameter values that differ from the default values that are specified for the cached result set, the dataset query runs actively and the cached results are not used for that query.</span></span>  
  
## <a name="caching-shared-datasets"></a><span data-ttu-id="09b49-121">Mise en cache des datasets partagés</span><span class="sxs-lookup"><span data-stu-id="09b49-121">Caching Shared Datasets</span></span>  
 <span data-ttu-id="09b49-122">Pour activer la mise en cache pour un dataset partagé, vous devez sélectionner l'option de cache sur le dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="09b49-122">To enable caching for a shared dataset, you must select the cache option on the shared dataset.</span></span> <span data-ttu-id="09b49-123">Une fois la mise en cache activée, les résultats de la requête pour un dataset partagé sont copiés vers le cache lors de la première utilisation.</span><span class="sxs-lookup"><span data-stu-id="09b49-123">After caching is enabled, the query results for a shared dataset are copied to the cache on first use.</span></span> <span data-ttu-id="09b49-124">Si le dataset partagé a des paramètres, chaque combinaison de paramètres crée une entrée dans le cache.</span><span class="sxs-lookup"><span data-stu-id="09b49-124">If the shared dataset has parameters, each combination of parameters creates a new entry in the cache.</span></span>  
  
 <span data-ttu-id="09b49-125">Pendant que les résultats de la requête pour une combinaison de paramètres spécifique sont dans le cache, chaque rapport lancé pour le traitement et qui inclut une référence au dataset partagé avec ces valeurs de paramètre utilisera les données en mémoire cache.</span><span class="sxs-lookup"><span data-stu-id="09b49-125">While the query results for a specific parameter combination are in the cache, each report that is launched for processing and that includes a reference to the shared dataset with those parameter values will use the cached data.</span></span>  
  
 <span data-ttu-id="09b49-126">Vous pouvez spécifier la durée pendant laquelle conserver les données dans le cache avant leur expiration.</span><span class="sxs-lookup"><span data-stu-id="09b49-126">You can specify how long to keep data in the cache before it expires.</span></span> <span data-ttu-id="09b49-127">Pour plus d’informations, consultez [Page Mise en cache, datasets partagés &#40;Gestionnaire de rapports&#41;](../caching-page-shared-datasets-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="09b49-127">For more information, see [Caching Page, Shared Datasets &#40;Report Manager&#41;](../caching-page-shared-datasets-report-manager.md).</span></span>  
  
## <a name="preloading-the-cache"></a><span data-ttu-id="09b49-128">Préchargement du cache</span><span class="sxs-lookup"><span data-stu-id="09b49-128">Preloading the Cache</span></span>  
 <span data-ttu-id="09b49-129">Vous pouvez précharger le cache en créant un plan d'actualisation du cache.</span><span class="sxs-lookup"><span data-stu-id="09b49-129">You can preload the cache by creating a cache refresh plan.</span></span> <span data-ttu-id="09b49-130">Avec un plan d'actualisation, vous pouvez spécifier la fréquence d'actualisation du cache à l'aide d'une planification spécifique par élément ou d'une planification partagée.</span><span class="sxs-lookup"><span data-stu-id="09b49-130">With a refresh plan, you can specify how often to refresh the cache by using an item-specific schedule or a shared schedule.</span></span> <span data-ttu-id="09b49-131">Pour éviter qu'il y ait plusieurs entrées du cache pour le même élément, la planification que vous spécifiez doit permettre suffisamment de temps pour le traitement des requêtes sur la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="09b49-131">To avoid multiple cache entries for the same item, the schedule that you specify should allow enough time for query processing on the external data source.</span></span> <span data-ttu-id="09b49-132">Par exemple, si la requête prend 20 minutes pour s'exécuter, la planification d'actualisation doit être supérieure à 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="09b49-132">For example, if the query takes 20 minutes to run, the refresh schedule should be greater than 20 minutes.</span></span> <span data-ttu-id="09b49-133">Pour plus d'informations, consultez [Schedules](../subscriptions/schedules.md).</span><span class="sxs-lookup"><span data-stu-id="09b49-133">For more information, see [Schedules](../subscriptions/schedules.md).</span></span>  
  
 <span data-ttu-id="09b49-134">Pour créer un plan d'actualisation du cache pour un dataset partagé, les conditions suivantes s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="09b49-134">To create a cache refresh plan for a shared dataset, the following conditions apply.</span></span>  
  
-   <span data-ttu-id="09b49-135">Le dataset partagé doit être activé pour la mise en cache.</span><span class="sxs-lookup"><span data-stu-id="09b49-135">The shared dataset must be enabled for caching.</span></span>  
  
-   <span data-ttu-id="09b49-136">La source de données partagée dont dépend le dataset partagé ne peut pas utiliser une Invite ou des informations d'identification intégrées de Windows.</span><span class="sxs-lookup"><span data-stu-id="09b49-136">The shared data source that the shared dataset depends on cannot use Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="09b49-137">Si le dataset partagé accepte des paramètres, vous devez spécifier des valeurs statiques par défaut pour chaque paramètre qui n'est pas marqué en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="09b49-137">If the shared dataset has parameters, you must specify static default values for each parameter that is not marked read-only.</span></span> <span data-ttu-id="09b49-138">Les paramètres en lecture seule utiliseront toujours la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="09b49-138">Read-only parameters will always use the default value.</span></span> <span data-ttu-id="09b49-139">Pour mettre en cache un dataset partagé pour plusieurs combinaisons de paramètres, vous devez créer un plan d'actualisation du cache distinct pour chaque combinaison de valeurs.</span><span class="sxs-lookup"><span data-stu-id="09b49-139">To cache a shared dataset for multiple combinations of parameters, you must create a separate cache refresh plan for each combination of values.</span></span> <span data-ttu-id="09b49-140">Les paramètres ne peuvent pas contenir de références à d'autres datasets.</span><span class="sxs-lookup"><span data-stu-id="09b49-140">Parameters cannot contain references to other datasets.</span></span>  
  
-   <span data-ttu-id="09b49-141">Chaque plan d'actualisation du cache est associé à un seul dataset partagé ou rapport.</span><span class="sxs-lookup"><span data-stu-id="09b49-141">Each cache refresh plan is associated with only one shared dataset or report.</span></span>  
  
-   <span data-ttu-id="09b49-142">Vous devez avoir des autorisations ReadPolicy et UpdatePolicy sur le dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="09b49-142">You must have ReadPolicy and UpdatePolicy permissions on the shared dataset.</span></span>  
  
 <span data-ttu-id="09b49-143">Les plans d'actualisation du cache s'appliquent aux datasets partagés et aux rapports.</span><span class="sxs-lookup"><span data-stu-id="09b49-143">Cache refresh plans apply to both shared datasets and reports.</span></span> <span data-ttu-id="09b49-144">Pour plus d’informations, consultez [Options d’actualisation du cache &#40;Gestionnaire de rapports&#41;](../cache-refresh-options-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="09b49-144">For more information, see [Cache Refresh Options &#40;Report Manager&#41;](../cache-refresh-options-report-manager.md).</span></span>  
  
## <a name="conditions-that-cause-cache-expiration"></a><span data-ttu-id="09b49-145">Conditions entraînant l'expiration du cache</span><span class="sxs-lookup"><span data-stu-id="09b49-145">Conditions that Cause Cache Expiration</span></span>  
 <span data-ttu-id="09b49-146">Les conditions suivantes peuvent provoquer le fait qu'un cache de dataset partagé devienne non valide.</span><span class="sxs-lookup"><span data-stu-id="09b49-146">The following conditions can cause a shared dataset cache to become not valid.</span></span>  
  
-   <span data-ttu-id="09b49-147">Une condition de planification expire.</span><span class="sxs-lookup"><span data-stu-id="09b49-147">A schedule condition expires.</span></span> <span data-ttu-id="09b49-148">Le cache dépasse le délai d'attente imparti ou atteint l'heure d'expiration.</span><span class="sxs-lookup"><span data-stu-id="09b49-148">The cache times out or the expiration time occurs.</span></span>  
  
-   <span data-ttu-id="09b49-149">Une planification partagée est supprimée.</span><span class="sxs-lookup"><span data-stu-id="09b49-149">A shared schedule is deleted.</span></span>  
  
-   <span data-ttu-id="09b49-150">Modifications apportées à une planification partagée.</span><span class="sxs-lookup"><span data-stu-id="09b49-150">Changes to a shared schedule.</span></span> <span data-ttu-id="09b49-151">Les planifications partagées peuvent être suspendues, ce qui affecte également l'expiration d'un cache.</span><span class="sxs-lookup"><span data-stu-id="09b49-151">Shared schedules can be paused, which also affects when a cache expires.</span></span>  
  
-   <span data-ttu-id="09b49-152">La définition de la requête pour le dataset partagé change.</span><span class="sxs-lookup"><span data-stu-id="09b49-152">The query definition for the shared dataset changes.</span></span>  
  
-   <span data-ttu-id="09b49-153">Les informations d'identification pour la source de données partagée dont dépend le dataset partagé changent.</span><span class="sxs-lookup"><span data-stu-id="09b49-153">The credentials for the shared data source that the shared dataset depends on change.</span></span>  
  
-   <span data-ttu-id="09b49-154">Les options de cache pour le dataset partagé changent.</span><span class="sxs-lookup"><span data-stu-id="09b49-154">The cache options for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="09b49-155">Les valeurs par défaut pour les paramètres en lecture seule pour le dataset partagé changent.</span><span class="sxs-lookup"><span data-stu-id="09b49-155">The default values for read-only parameters for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="09b49-156">Les filtres qui font partie de la définition du dataset partagé changent.</span><span class="sxs-lookup"><span data-stu-id="09b49-156">The filters that are part of the shared dataset definition change.</span></span>  
  
-   <span data-ttu-id="09b49-157">Le dataset partagé est supprimé du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="09b49-157">The shared dataset is deleted from the report server.</span></span> <span data-ttu-id="09b49-158">Lorsqu'un dataset partagé est supprimé, les copies mises en cache associées et les plans d'actualisation du cache sont également supprimés.</span><span class="sxs-lookup"><span data-stu-id="09b49-158">When a shared dataset is deleted, associated cached copies and cache refresh plans are also deleted.</span></span>  
  
 <span data-ttu-id="09b49-159">Les mises à jour apportées aux plans d'actualisation du cache pour les datasets partagés n'affectent pas les rapports qui sont déjà traités.</span><span class="sxs-lookup"><span data-stu-id="09b49-159">Updates to cache refresh plans for shared datasets do not affect reports that are already being processed.</span></span> <span data-ttu-id="09b49-160">La mise à jour d'un plan d'actualisation du cache affecte uniquement les futurs lancements de rapports qui font référence au dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="09b49-160">Updating a cache refresh plan affects only future launches of reports that reference the shared dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b49-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09b49-161">See Also</span></span>  
 [<span data-ttu-id="09b49-162">Gérer des datasets partagés</span><span class="sxs-lookup"><span data-stu-id="09b49-162">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
