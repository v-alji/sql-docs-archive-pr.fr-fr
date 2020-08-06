---
title: Mise en miroir de bases de données et catalogues de texte intégral (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- full-text catalogs [SQL Server], database mirroring
- catalogs [SQL Server], database mirroring
ms.assetid: e34072ae-fe8a-462d-bb03-02fa0987f793
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 39929f4bed6edbd1e8ec5c1b72dbe8f7aefeec68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603021"
---
# <a name="database-mirroring-and-full-text-catalogs-sql-server"></a><span data-ttu-id="2b5d5-102">Mise en miroir de bases de données et catalogues de texte intégral (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2b5d5-102">Database Mirroring and Full-Text Catalogs (SQL Server)</span></span>
  <span data-ttu-id="2b5d5-103">Pour créer un miroir d'une base de données dotée d'un catalogue de texte intégral, utilisez les fonctions habituelles de sauvegarde pour créer une sauvegarde complète de la base de données principale, puis restaurez la copie de celle-ci sur le serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-103">To mirror a database that has a full-text catalog, use backup as usual to create a full database backup of the principal database, and then restore the backup to copy the database to the mirror server.</span></span> <span data-ttu-id="2b5d5-104">Pour plus d’informations, consultez [Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2b5d5-104">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
## <a name="full-text-catalog-and-indexes-before-failover"></a><span data-ttu-id="2b5d5-105">Catalogue et index de texte intégral avant basculement</span><span class="sxs-lookup"><span data-stu-id="2b5d5-105">Full-Text Catalog and Indexes Before Failover</span></span>  
 <span data-ttu-id="2b5d5-106">Dans une base de données miroir récemment créée, le catalogue de texte intégral est le même que lorsque la base de données a été sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-106">In a newly created mirror database, the full-text catalog is the same as when the database was backed up.</span></span> <span data-ttu-id="2b5d5-107">Une fois que la mise en miroir de la base de données a commencé, les modifications apportées au niveau du catalogue par les instructions DDL (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) sont enregistrées et envoyées au serveur miroir pour être relues sur la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-107">After database mirroring starts, any catalog-level changes that were made by DDL statements (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) are logged and sent to the mirror server to be replayed on the mirror database.</span></span> <span data-ttu-id="2b5d5-108">Cependant, les modifications au niveau de l'index ne sont pas répercutées sur la base de données miroir dans la mesure où celle-ci n'est pas connectée au serveur principal.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-108">However, index-level changes are not reproduced on the mirror database because it is not logged on to the principal server.</span></span> <span data-ttu-id="2b5d5-109">Par conséquent, les modifications affectant le contenu du catalogue de texte intégral sur la base de données principale ne sont pas synchronisées avec le contenu du catalogue de texte intégral sur la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-109">Therefore, as the contents of the full-text catalog change on the principal database, the contents of the full-text catalog on the mirror database are unsynchronized.</span></span>  
  
## <a name="full-text-indexes-after-failover"></a><span data-ttu-id="2b5d5-110">Index de texte intégral après basculement</span><span class="sxs-lookup"><span data-stu-id="2b5d5-110">Full-Text Indexes After Failover</span></span>  
 <span data-ttu-id="2b5d5-111">À l'issue d'un basculement, une analyse complète d'un index de texte intégral sur le nouveau serveur principal peut être utile ou nécessaire dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="2b5d5-111">After a failover, a full crawl of a full-text index on the new principal server might be required or useful in the following situations:</span></span>  
  
-   <span data-ttu-id="2b5d5-112">Si le suivi des modifications est désactivé sur un index de texte intégral, vous devez démarrer une analyse complète sur cet index à l'aide de l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="2b5d5-112">If change-tracking is turned OFF on a full text index, you must start a full crawl on that index by using the following statement:</span></span>  
  
     <span data-ttu-id="2b5d5-113">ALTER FULLTEXT INDEX ON *nom_table* START FULL POPULATION</span><span class="sxs-lookup"><span data-stu-id="2b5d5-113">ALTER FULLTEXT INDEX ON *table_name* START FULL POPULATION</span></span>  
  
-   <span data-ttu-id="2b5d5-114">Si un index de texte intégral est configuré pour le suivi des modifications automatique, cet index est synchronisé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-114">If a full-text index is configured for automatic change tracking, the full-text index is automatically synchronized.</span></span> <span data-ttu-id="2b5d5-115">Toutefois, la synchronisation ralentit les performances du texte intégral dans une certaine mesure.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-115">However, synchronization slows full-text performance somewhat.</span></span> <span data-ttu-id="2b5d5-116">Si les performances sont trop lentes, vous pouvez générer une analyse complète en désactivant le suivi des modifications et en le redéfinissant sur automatique :</span><span class="sxs-lookup"><span data-stu-id="2b5d5-116">If performance is too slow, you can cause a full crawl by setting change tracking off and then resetting it to automatic:</span></span>  
  
    -   <span data-ttu-id="2b5d5-117">Pour désactiver le suivi des modifications :</span><span class="sxs-lookup"><span data-stu-id="2b5d5-117">To set change tracking off:</span></span>  
  
         <span data-ttu-id="2b5d5-118">ALTER FULLTEXT INDEX ON *nom_table* SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="2b5d5-118">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING OFF</span></span>  
  
    -   <span data-ttu-id="2b5d5-119">Pour définir le suivi des modifications sur automatique :</span><span class="sxs-lookup"><span data-stu-id="2b5d5-119">To set on automatic change tracking to automatic:</span></span>  
  
         <span data-ttu-id="2b5d5-120">ALTER FULLTEXT INDEX ON *nom_table* SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="2b5d5-120">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING AUTO</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2b5d5-121">Pour savoir si le suivi automatique des modifications est activé, vous pouvez utiliser la fonction [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) pour interroger la propriété **TableFullTextBackgroundUpdateIndexOn** de la table.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-121">To see whether auto change tracking is on, you can use the [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) function to query the **TableFullTextBackgroundUpdateIndexOn** property of the table.</span></span>  
  
 <span data-ttu-id="2b5d5-122">Pour plus d’informations, consultez [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2b5d5-122">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b5d5-123">Le démarrage d'une analyse après basculement fonctionne de la même manière que le démarrage d'une analyse après une restauration.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-123">Starting a crawl after failover works the same as starting a crawl after a restore.</span></span>  
  
## <a name="after-forcing-service"></a><span data-ttu-id="2b5d5-124">Après avoir forcé le service</span><span class="sxs-lookup"><span data-stu-id="2b5d5-124">After Forcing Service</span></span>  
 <span data-ttu-id="2b5d5-125">Une fois que le service a été forcé sur le serveur miroir (perte de données possible), commencez une analyse complète.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-125">After service is forced to the mirror server (with possible data loss), start a full crawl.</span></span> <span data-ttu-id="2b5d5-126">La méthode à utiliser pour démarrer une analyse complète dépend si l'index de texte intégral fait l'objet d'un suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-126">The method to use for starting a full crawl depends on whether the full-text index is change tracked.</span></span> <span data-ttu-id="2b5d5-127">Pour plus d'informations, consultez « Index de texte intégral après basculement », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="2b5d5-127">For more information, see "Full-Text Indexes After Failover," earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b5d5-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b5d5-128">See Also</span></span>  
 <span data-ttu-id="2b5d5-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b5d5-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="2b5d5-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b5d5-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="2b5d5-131">[DROP FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b5d5-131">[DROP FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="2b5d5-132">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2b5d5-132">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="2b5d5-133">Sauvegarder et restaurer des catalogues et des index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="2b5d5-133">Back Up and Restore Full-Text Catalogs and Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
  
