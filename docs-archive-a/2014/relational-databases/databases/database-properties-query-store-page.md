---
title: Propriétés de la base de données (page Magasin de requêtes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql13.swb.databaseproperties.querystore.f1
ms.assetid: da47d75e-291a-4305-acef-4b0aaf5215da
author: stevestein
ms.author: sstein
ms.openlocfilehash: bab0d9b697e9ad9ec4b27f320d26b9b9edb5944e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702956"
---
# <a name="database-properties-query-store-page"></a><span data-ttu-id="3a41e-102">Propriétés de la base de données (page Magasin de requêtes)</span><span class="sxs-lookup"><span data-stu-id="3a41e-102">Database Properties (Query Store Page)</span></span>
  <span data-ttu-id="3a41e-103">Accédez à cette page depuis la base de données principale et utilisez-la pour configurer et modifier les propriétés du magasin de requêtes de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3a41e-103">Access this page from the principal database, and use it to configure and to modify the properties of the database query store.</span></span> <span data-ttu-id="3a41e-104">Ces options peuvent également être configurées à l'aide des [options ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="3a41e-104">These options can also be configure by using the [ALTER DATABASE SET options](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span> <span data-ttu-id="3a41e-105">Pour plus d'informations sur le magasin de requêtes, consultez [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="3a41e-105">For information about the query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="3a41e-106">**S'applique à**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a41e-106">**Applies to**: [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].</span></span>|  
  
## <a name="options"></a><span data-ttu-id="3a41e-107">Options</span><span class="sxs-lookup"><span data-stu-id="3a41e-107">Options</span></span>  
 <span data-ttu-id="3a41e-108">Activer</span><span class="sxs-lookup"><span data-stu-id="3a41e-108">Enable</span></span>  
 <span data-ttu-id="3a41e-109">Active et désactive le magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="3a41e-109">Enables and disables the query store.</span></span>  
  
 <span data-ttu-id="3a41e-110">Mode d'opération</span><span class="sxs-lookup"><span data-stu-id="3a41e-110">Operation Mode</span></span>  
 <span data-ttu-id="3a41e-111">Les valeurs valides sont READ_ONLY et READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="3a41e-111">Valid values are READ_ONLY and READ_WRITE.</span></span> <span data-ttu-id="3a41e-112">En mode READ_WRITE, le magasin de requête collecte et conserve les informations sur le plan de requête et les statistiques d'exécution.</span><span class="sxs-lookup"><span data-stu-id="3a41e-112">In READ_WRITE mode, the query store collects and persists query plan and runtime execution statistics information.</span></span> <span data-ttu-id="3a41e-113">En mode READ_ONLY, les informations peuvent être lues à partir du magasin de requête, mais les nouvelles informations ne sont pas ajoutées.</span><span class="sxs-lookup"><span data-stu-id="3a41e-113">In READ_ONLY mode, information can be read from the query store, but new information is not added.</span></span> <span data-ttu-id="3a41e-114">Si la valeur maximale de l'espace du magasin de requête allouée est épuisée, le mode d'opération du magasin de requêtes passe en READ_ONLY.</span><span class="sxs-lookup"><span data-stu-id="3a41e-114">If the maximum allocated space of the query store has been exhausted, the query store will change its operation mode to READ_ONLY.</span></span>  
  
 <span data-ttu-id="3a41e-115">Mode d'opération (réel)</span><span class="sxs-lookup"><span data-stu-id="3a41e-115">Operation Mode (Actual)</span></span>  
 <span data-ttu-id="3a41e-116">Obtient le mode de fonctionnement réel du magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="3a41e-116">Gets the actual operation mode of the query store.</span></span>  
  
 <span data-ttu-id="3a41e-117">Mode d'opération (demandé)</span><span class="sxs-lookup"><span data-stu-id="3a41e-117">Operation Mode (Requested)</span></span>  
 <span data-ttu-id="3a41e-118">Obtient et définit le mode de fonctionnement souhaité du magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="3a41e-118">Gets and sets the desired operation mode of the query store.</span></span>  
  
 <span data-ttu-id="3a41e-119">Intervalle de vidange des données (minutes)</span><span class="sxs-lookup"><span data-stu-id="3a41e-119">Data Flush Interval (Minutes)</span></span>  
 <span data-ttu-id="3a41e-120">Détermine la fréquence à laquelle les données écrites sur le magasin de requête magasin est conservée sur le disque.</span><span class="sxs-lookup"><span data-stu-id="3a41e-120">Determines the frequency at which data written to the query store is persisted to disk.</span></span> <span data-ttu-id="3a41e-121">Pour optimiser les performances, les données collectées par le magasin de requête sont écrites de façon asynchrone sur le disque.</span><span class="sxs-lookup"><span data-stu-id="3a41e-121">To optimize for performance, data collected by the query store is asynchronously written to the disk.</span></span> <span data-ttu-id="3a41e-122">La fréquence à laquelle ce transfert asynchrone se produit est configurée.</span><span class="sxs-lookup"><span data-stu-id="3a41e-122">The frequency at which this asynchronous transfer occurs is configured.</span></span>  
  
 <span data-ttu-id="3a41e-123">Intervalle de collecte des statistiques</span><span class="sxs-lookup"><span data-stu-id="3a41e-123">Statistics Collection Interval</span></span>  
 <span data-ttu-id="3a41e-124">Obtient et définit la valeur de l'intervalle de collecte des statistiques.</span><span class="sxs-lookup"><span data-stu-id="3a41e-124">Gets and sets the statistics collection interval value.</span></span>  
  
 <span data-ttu-id="3a41e-125">Taille maximale (Mo)</span><span class="sxs-lookup"><span data-stu-id="3a41e-125">Max Size (MB)</span></span>  
 <span data-ttu-id="3a41e-126">Obtient et définit l'espace total alloué au magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="3a41e-126">Gets and sets the total space allocated to the query store.</span></span>  
  
 <span data-ttu-id="3a41e-127">Seuil de requêtes périmées (jours)</span><span class="sxs-lookup"><span data-stu-id="3a41e-127">Stale Query Threshold (Days)</span></span>  
 <span data-ttu-id="3a41e-128">Obtient et définit le seuil de requêtes périmées.</span><span class="sxs-lookup"><span data-stu-id="3a41e-128">Gets and sets the stale query threshold.</span></span> <span data-ttu-id="3a41e-129">Configurez l'argument STALE_QUERY_THRESHOLD_DAYS pour spécifier le nombre de jours de conservation des données dans le magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="3a41e-129">Configure the STALE_QUERY_THRESHOLD_DAYS argument to specify the number of days to retain data in the query store.</span></span>  
  
 <span data-ttu-id="3a41e-130">Purger les données de requête</span><span class="sxs-lookup"><span data-stu-id="3a41e-130">Purge Query Data</span></span>  
 <span data-ttu-id="3a41e-131">Supprime le contenu du magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="3a41e-131">Removes the contents of the query store.</span></span>  
  
 <span data-ttu-id="3a41e-132">Graphiques à secteurs</span><span class="sxs-lookup"><span data-stu-id="3a41e-132">Pie Charts</span></span>  
 <span data-ttu-id="3a41e-133">Le graphique de gauche montre la consommation totale du fichier de base de données sur le disque et la partie du fichier qui est remplie avec les données du magasin de requêtes.</span><span class="sxs-lookup"><span data-stu-id="3a41e-133">The left chart shows the total database file consumption on the disk, and the portion of the file which is filled with the query store data.</span></span>  
  
 <span data-ttu-id="3a41e-134">Le graphique de droite montre la partie du quota de magasin de requêtes actuellement utilisé.</span><span class="sxs-lookup"><span data-stu-id="3a41e-134">The right chart shows the portion of the query store quota which is currently used up.</span></span> <span data-ttu-id="3a41e-135">Notez que le quota n'est pas affiché dans le graphique de gauche.</span><span class="sxs-lookup"><span data-stu-id="3a41e-135">Note that the quota is not shown in the left chart.</span></span> <span data-ttu-id="3a41e-136">Le quota peut dépasser la taille actuelle de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3a41e-136">The quota may exceed the current size of the database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a41e-137">Notes</span><span class="sxs-lookup"><span data-stu-id="3a41e-137">Remarks</span></span>  
 <span data-ttu-id="3a41e-138">La fonctionnalité de magasin de requêtes fournit aux administrateurs de bases de données des informations sur le choix de plan de requête et les performances.</span><span class="sxs-lookup"><span data-stu-id="3a41e-138">The query store feature provides DBAs with insight on query plan choice and performance.</span></span> <span data-ttu-id="3a41e-139">Elle simplifie la résolution des problèmes de performances en vous permettant de trouver rapidement les différences de performances provoquées par un changement de plan de requête.</span><span class="sxs-lookup"><span data-stu-id="3a41e-139">It simplifies performance troubleshooting by enabling you to quickly find performance differences caused by changes in query plans.</span></span> <span data-ttu-id="3a41e-140">La fonctionnalité capture automatiquement l'historique des requêtes, des plans et des statistiques d'exécution et les conserve à des fins de consultation.</span><span class="sxs-lookup"><span data-stu-id="3a41e-140">The feature automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.</span></span> <span data-ttu-id="3a41e-141">Elle sépare les données en périodes, ce qui vous permet de voir les modèles d'utilisation de base de données et de comprendre à quel moment le changement de plan de requête a eu lieu sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="3a41e-141">It separates data by time windows, allowing you to see database usage patterns and understand when query plan changes happened on the server.</span></span> <span data-ttu-id="3a41e-142">Le magasin de requêtes peut être configuré à l'aide de la page de propriétés de la base de données du magasin de requêtes ou de l’option [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) .</span><span class="sxs-lookup"><span data-stu-id="3a41e-142">The query store can be configured by using this query store database property page, or by using the [ALTER DATABASE SET](/sql/t-sql/statements/alter-database-transact-sql-set-options) option.</span></span> <span data-ttu-id="3a41e-143">Le magasin de requêtes présente les informations via la boîte de dialogue [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a41e-143">The query store presents information by using a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] dialog box.</span></span> <span data-ttu-id="3a41e-144">Pour plus d'informations sur le magasin de requêtes, consultez [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span><span class="sxs-lookup"><span data-stu-id="3a41e-144">For more information about query store, see [Monitoring Performance By Using the Query Store](../performance/monitoring-performance-by-using-the-query-store.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a41e-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3a41e-145">See Also</span></span>  
 <span data-ttu-id="3a41e-146">[Procédures stockées du Magasin des requêtes &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3a41e-146">[Query Store Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="3a41e-147">Affichages catalogue du magasin de requêtes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3a41e-147">Query Store Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/query-store-catalog-views-transact-sql)  
  
  
