---
title: Entrepôt de données de gestion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], management data warehouse
- data warehouse
- management data warehouse
ms.assetid: 9874a8b2-7ccd-494a-944c-ad33b30b5499
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 96eb26c3e273832aead4aa0421304df17dc5b8ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603552"
---
# <a name="management-data-warehouse"></a><span data-ttu-id="cffa0-102">entrepôt de données de gestion</span><span class="sxs-lookup"><span data-stu-id="cffa0-102">Management Data Warehouse</span></span>
  <span data-ttu-id="cffa0-103">L'entrepôt de données de gestion est une base de données relationnelle qui contient les données collectées à partir d'un serveur faisant office de cible de collecte de données.</span><span class="sxs-lookup"><span data-stu-id="cffa0-103">The management data warehouse is a relational database that contains the data that is collected from a server that is a data collection target.</span></span> <span data-ttu-id="cffa0-104">Ces données permettent de générer les rapports pour les jeux d'éléments de collecte de données système ainsi que de créer des rapports personnalisés.</span><span class="sxs-lookup"><span data-stu-id="cffa0-104">This data is used to generate the reports for the System Data collection sets, and can also be used to create custom reports.</span></span>  
  
 <span data-ttu-id="cffa0-105">L'infrastructure du collecteur de données définit les travaux et les plans de maintenance nécessaires pour implémenter les stratégies de rétention définies par l'administrateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="cffa0-105">The data collector infrastructure defines the jobs and maintenance plans that are needed to implement the retention policies defined by the database administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cffa0-106">Pour cette version du collecteur de données, l'entrepôt de données de gestion est créé à l'aide du mode de récupération simple, pour réduire la journalisation.</span><span class="sxs-lookup"><span data-stu-id="cffa0-106">For this release of the data collector, the management data warehouse is created using the Simple recovery model, to minimize logging.</span></span> <span data-ttu-id="cffa0-107">Vous devez implémenter le mode de récupération adapté à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cffa0-107">You should implement the appropriate recovery model for your organization.</span></span>  
  
## <a name="deploying-and-using-the-data-warehouse"></a><span data-ttu-id="cffa0-108">Déploiement et utilisation de l'entrepôt de données</span><span class="sxs-lookup"><span data-stu-id="cffa0-108">Deploying and Using the Data Warehouse</span></span>  
 <span data-ttu-id="cffa0-109">Vous pouvez installer l'entrepôt de données de gestion sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui exécute le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="cffa0-109">You can install the management data warehouse on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that runs the data collector.</span></span> <span data-ttu-id="cffa0-110">Toutefois, si les ressources ou les performances du serveur constituent un problème sur le serveur analysé, vous pouvez installer l'entrepôt de données de gestion sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cffa0-110">However, if server resources or performance is an issue on the server being monitored, you can install the management data warehouse on a different computer.</span></span>  
  
 <span data-ttu-id="cffa0-111">Les schémas requis et leurs objets pour les jeux d'éléments de collecte de données système prédéfinis sont créés lorsque vous créez l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="cffa0-111">The required schemas and their objects for the predefined system collection sets are created when you create the management data warehouse.</span></span> <span data-ttu-id="cffa0-112">Les schémas créés sont les schémas Core et Snapshots. Un troisième schéma, custom_snapshots, est créé lors de la création de jeux d’éléments de collecte définis par l’utilisateur qui incluent des éléments de collecte qui utilisent le type de collecteur Requête T-SQL générique.</span><span class="sxs-lookup"><span data-stu-id="cffa0-112">The schemas that are created are core and snapshots.A third schema, custom_snapshots, is created when user-defined collection sets are created that include collection items that use the Generic T-SQL Query collector type.</span></span>  
  
###### <a name="core-schema"></a><span data-ttu-id="cffa0-113">Schéma principal (Core)</span><span class="sxs-lookup"><span data-stu-id="cffa0-113">Core schema</span></span>  
 <span data-ttu-id="cffa0-114">Le schéma principal (Core) décrit les tables, les procédures stockées et les vues utilisées pour organiser et identifier les données collectées.</span><span class="sxs-lookup"><span data-stu-id="cffa0-114">The core schema describes the tables, stored procedures, and views that are used to organize and to identify collected data.</span></span> <span data-ttu-id="cffa0-115">Ces tables sont réparties entre toutes les tables de données créées pour les types de collecteurs individuels.</span><span class="sxs-lookup"><span data-stu-id="cffa0-115">These tables are shared among all the data tables created for individual collector types.</span></span> <span data-ttu-id="cffa0-116">Ce schéma est verrouillé et seul le propriétaire de la base de données de l'entrepôt de données de gestion peut le modifier.</span><span class="sxs-lookup"><span data-stu-id="cffa0-116">This schema is locked and can only be modified by the owner of the management data warehouse database.</span></span> <span data-ttu-id="cffa0-117">Les noms des tables de ce schéma incluent le préfixe « core ».</span><span class="sxs-lookup"><span data-stu-id="cffa0-117">The names of the tables in this schema are prefixed by "core".</span></span>  
  
 <span data-ttu-id="cffa0-118">Le tableau ci-dessous décrit les tables de base de données incluses dans le schéma principal.</span><span class="sxs-lookup"><span data-stu-id="cffa0-118">The following table describes the database tables in the core schema.</span></span> <span data-ttu-id="cffa0-119">Ces tables de base de données permettent au collecteur de données d'effectuer le suivi des données indiquant d'où les données proviennent, qui a inséré les données et quand elles ont été téléchargées vers l'entrepôt de données.</span><span class="sxs-lookup"><span data-stu-id="cffa0-119">These database tables enable the data collector to track where the data came from, who inserted it, and when it was uploaded to the data warehouse.</span></span>  
  
|<span data-ttu-id="cffa0-120">Nom de la table</span><span class="sxs-lookup"><span data-stu-id="cffa0-120">Table name</span></span>|<span data-ttu-id="cffa0-121">Description</span><span class="sxs-lookup"><span data-stu-id="cffa0-121">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="cffa0-122">core.performance_counter_report_group_items</span><span class="sxs-lookup"><span data-stu-id="cffa0-122">core.performance_counter_report_group_items</span></span>|<span data-ttu-id="cffa0-123">Stocke des informations sur la manière dont les rapports de l'entrepôt de données de gestion doivent regrouper et agréger les compteurs de performance.</span><span class="sxs-lookup"><span data-stu-id="cffa0-123">Stores information about how the management data warehouse reports should group and aggregate performance counters.</span></span>|  
|<span data-ttu-id="cffa0-124">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="cffa0-124">core.snapshots_internal</span></span>|<span data-ttu-id="cffa0-125">Identifie chaque nouvel instantané.</span><span class="sxs-lookup"><span data-stu-id="cffa0-125">Identifies each new snapshot.</span></span> <span data-ttu-id="cffa0-126">Une nouvelle ligne est insérée dans cette table lorsqu'un package de téléchargement commence à télécharger un nouveau lot de données.</span><span class="sxs-lookup"><span data-stu-id="cffa0-126">A new row is inserted into this table whenever an upload package starts uploading a new batch of data.</span></span>|  
|<span data-ttu-id="cffa0-127">core.snapshot_timetable_internal</span><span class="sxs-lookup"><span data-stu-id="cffa0-127">core.snapshot_timetable_internal</span></span>|<span data-ttu-id="cffa0-128">Stocke des informations sur les heures de l'instantané.</span><span class="sxs-lookup"><span data-stu-id="cffa0-128">Stores information about the snapshot times.</span></span> <span data-ttu-id="cffa0-129">L'heure de l'instantané est stockée dans une table séparée car de nombreux instantanés peuvent s'exécuter pratiquement en même temps.</span><span class="sxs-lookup"><span data-stu-id="cffa0-129">The snapshot time is stored in a separate table because many snapshots can happen at nearly the same time.</span></span>|  
|<span data-ttu-id="cffa0-130">core.source.info_internal</span><span class="sxs-lookup"><span data-stu-id="cffa0-130">core.source.info_internal</span></span>|<span data-ttu-id="cffa0-131">Stocke des informations sur la source de données.</span><span class="sxs-lookup"><span data-stu-id="cffa0-131">This table stores information about the data source.</span></span> <span data-ttu-id="cffa0-132">Cette table est mise à jour lorsqu'un nouveau jeu d'éléments de collecte commence à télécharger des données dans l'entrepôt de données.</span><span class="sxs-lookup"><span data-stu-id="cffa0-132">This table is updated whenever a new collection set starts uploading data to the data warehouse.</span></span>|  
|<span data-ttu-id="cffa0-133">core.supported_collector_types_internal</span><span class="sxs-lookup"><span data-stu-id="cffa0-133">core.supported_collector_types_internal</span></span>|<span data-ttu-id="cffa0-134">Contient les ID des types de collecteurs enregistrés qui peuvent télécharger des données vers l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="cffa0-134">Contains the IDs of registered collector types that can upload data to the management data warehouse.</span></span> <span data-ttu-id="cffa0-135">Cette table est mise à jour uniquement lorsque le schéma de l'entrepôt est mis à jour pour prendre en charge un nouveau type de collecteur.</span><span class="sxs-lookup"><span data-stu-id="cffa0-135">This table is only updated when the schema of the warehouse is updated to support a new collector type.</span></span> <span data-ttu-id="cffa0-136">Lorsque l'entrepôt de données de gestion est créé, cette table est remplie avec les ID des types de collecteurs fournis par le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="cffa0-136">When the management data warehouse is created, this table is populated with the IDs of the collector types provided by the data collector.</span></span>|  
|<span data-ttu-id="cffa0-137">core.wait_categories</span><span class="sxs-lookup"><span data-stu-id="cffa0-137">core.wait_categories</span></span>|<span data-ttu-id="cffa0-138">Contient les catégories utilisées pour grouper des types d'attente en fonction de la caractéristique wait_type.</span><span class="sxs-lookup"><span data-stu-id="cffa0-138">Contains the categories used to group wait types according to wait_type characteristic.</span></span>|  
|<span data-ttu-id="cffa0-139">core.wait_types</span><span class="sxs-lookup"><span data-stu-id="cffa0-139">core.wait_types</span></span>|<span data-ttu-id="cffa0-140">Contient les types d'attente reconnus par le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="cffa0-140">Contains the wait types recognized by the data collector.</span></span>|  
|<span data-ttu-id="cffa0-141">core.purge_info_internal</span><span class="sxs-lookup"><span data-stu-id="cffa0-141">core.purge_info_internal</span></span>|<span data-ttu-id="cffa0-142">Indique qu'une demande a été faite pour arrêter la suppression de données de l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="cffa0-142">Indicates that a request has been made to stop the removal of data from the management data warehouse.</span></span>|  
  
 <span data-ttu-id="cffa0-143">Les tables précédentes sont utilisées avec des tables de type de collecteur pour stocker des informations.</span><span class="sxs-lookup"><span data-stu-id="cffa0-143">The preceding tables are used with collector type tables to store information.</span></span> <span data-ttu-id="cffa0-144">Par exemple, le type de collecteur Trace SQL générique utilise les tables suivantes pour stocker les données de trace :</span><span class="sxs-lookup"><span data-stu-id="cffa0-144">For example, the Generic SQL Trace collector type uses the following tables to store trace data:</span></span>  
  
-   <span data-ttu-id="cffa0-145">core.source_info_internal</span><span class="sxs-lookup"><span data-stu-id="cffa0-145">core.source_info_internal</span></span>  
  
-   <span data-ttu-id="cffa0-146">core.snapshots_internal</span><span class="sxs-lookup"><span data-stu-id="cffa0-146">core.snapshots_internal</span></span>  
  
-   <span data-ttu-id="cffa0-147">snapshots.trace_info</span><span class="sxs-lookup"><span data-stu-id="cffa0-147">snapshots.trace_info</span></span>  
  
-   <span data-ttu-id="cffa0-148">snapshots.trace_data</span><span class="sxs-lookup"><span data-stu-id="cffa0-148">snapshots.trace_data</span></span>  
  
###### <a name="snapshots-schema"></a><span data-ttu-id="cffa0-149">Schéma des instantanés</span><span class="sxs-lookup"><span data-stu-id="cffa0-149">Snapshots schema</span></span>  
 <span data-ttu-id="cffa0-150">Le schéma des instantanés décrit les objets nécessaires au stockage et à la gestion des données collectées par les types de collecteurs fournis.</span><span class="sxs-lookup"><span data-stu-id="cffa0-150">The snapshots schema describes the objects needed to store and maintain the data collected by the collector types that are provided.</span></span> <span data-ttu-id="cffa0-151">Les tables dans ce schéma sont fixes et n'ont pas besoin d'être modifiées pendant la durée de vie du type de collecteur.</span><span class="sxs-lookup"><span data-stu-id="cffa0-151">The tables in this schema are fixed and do not need to be changed during the lifetime of the collector type.</span></span> <span data-ttu-id="cffa0-152">Si des modifications sont nécessaires, seuls les membres du rôle mdw_admin peuvent modifier le schéma.</span><span class="sxs-lookup"><span data-stu-id="cffa0-152">If changes are needed, the schema can only be changed by members of the mdw_admin role.</span></span> <span data-ttu-id="cffa0-153">Ces tables sont créées pour stocker les données collectées par les jeux d'éléments de collecte de données système.</span><span class="sxs-lookup"><span data-stu-id="cffa0-153">These tables are created to store the data collected by the System Data collection sets.</span></span>  
  
 <span data-ttu-id="cffa0-154">Les tables ci-dessous illustrent une partie du schéma de l'entrepôt de données de gestion qui est nécessaire pour les jeux d'éléments de collecte Activité du serveur et Statistiques de requête.</span><span class="sxs-lookup"><span data-stu-id="cffa0-154">The following tables illustrate a portion of the management data warehouse schema that is required for the Server Activity and Query Statistics collection sets.</span></span>  
  
-   <span data-ttu-id="cffa0-155">Tables des ressources au niveau du système</span><span class="sxs-lookup"><span data-stu-id="cffa0-155">System-level resource tables</span></span>  
  
    -   <span data-ttu-id="cffa0-156">**snapshots.os_wait_stats**</span><span class="sxs-lookup"><span data-stu-id="cffa0-156">**snapshots.os_wait_stats**</span></span>  
  
    -   <span data-ttu-id="cffa0-157">**snapshots.os_latch_stats**</span><span class="sxs-lookup"><span data-stu-id="cffa0-157">**snapshots.os_latch_stats**</span></span>  
  
    -   <span data-ttu-id="cffa0-158">**snapshots.os_schedulers**</span><span class="sxs-lookup"><span data-stu-id="cffa0-158">**snapshots.os_schedulers**</span></span>  
  
    -   `snapshots.os_memory_clerks`  
  
    -   <span data-ttu-id="cffa0-159">**snapshots.os_memory_nodes**</span><span class="sxs-lookup"><span data-stu-id="cffa0-159">**snapshots.os_memory_nodes**</span></span>  
  
    -   <span data-ttu-id="cffa0-160">snapshots.sql_process_and_system_memory</span><span class="sxs-lookup"><span data-stu-id="cffa0-160">snapshots.sql_process_and_system_memory</span></span>  
  
-   <span data-ttu-id="cffa0-161">Activité du système</span><span class="sxs-lookup"><span data-stu-id="cffa0-161">System activity</span></span>  
  
    -   <span data-ttu-id="cffa0-162">snapshots.active_sessions_and_requests</span><span class="sxs-lookup"><span data-stu-id="cffa0-162">snapshots.active_sessions_and_requests</span></span>  
  
-   <span data-ttu-id="cffa0-163">Statistiques sur les requêtes</span><span class="sxs-lookup"><span data-stu-id="cffa0-163">Query statistics</span></span>  
  
    -   <span data-ttu-id="cffa0-164">snapshots.query_stats</span><span class="sxs-lookup"><span data-stu-id="cffa0-164">snapshots.query_stats</span></span>  
  
-   <span data-ttu-id="cffa0-165">Statistiques d'E/S</span><span class="sxs-lookup"><span data-stu-id="cffa0-165">I/O statistics</span></span>  
  
    -   `snapshots.io_virtual_file_stats`  
  
-   <span data-ttu-id="cffa0-166">Texte et plan de requête</span><span class="sxs-lookup"><span data-stu-id="cffa0-166">Query text and plan</span></span>  
  
    -   <span data-ttu-id="cffa0-167">snapshots.notable_query_text</span><span class="sxs-lookup"><span data-stu-id="cffa0-167">snapshots.notable_query_text</span></span>  
  
    -   <span data-ttu-id="cffa0-168">snapshots.notable_query_plan</span><span class="sxs-lookup"><span data-stu-id="cffa0-168">snapshots.notable_query_plan</span></span>  
  
-   <span data-ttu-id="cffa0-169">Statistiques de requête normalisées</span><span class="sxs-lookup"><span data-stu-id="cffa0-169">Normalized query statistics</span></span>  
  
    -   <span data-ttu-id="cffa0-170">snapshots.distinct_queries</span><span class="sxs-lookup"><span data-stu-id="cffa0-170">snapshots.distinct_queries</span></span>  
  
    -   <span data-ttu-id="cffa0-171">snapshots.distinct_query_to_handle</span><span class="sxs-lookup"><span data-stu-id="cffa0-171">snapshots.distinct_query_to_handle</span></span>  
  
 <span data-ttu-id="cffa0-172">**Schéma custom_snapshots**</span><span class="sxs-lookup"><span data-stu-id="cffa0-172">**Custom_snapshots schema**</span></span>  
  
 <span data-ttu-id="cffa0-173">Le schéma custom_snapshots décrit les nouvelles tables et vues créées lorsque des types de collecteurs standard ou tiers sont utilisés pour créer des jeux d'éléments de collecte définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cffa0-173">The custom_snapshots schema describes new tables and views that are created when standard or third-party collector types are used to create user-defined collection sets.</span></span> <span data-ttu-id="cffa0-174">Tout type de collecteur qui requiert une nouvelle table de données pour un élément de collecte peut créer cette table dans ce schéma.</span><span class="sxs-lookup"><span data-stu-id="cffa0-174">Any collector type that requires a new data table for a collection item can create that table in this schema.</span></span> <span data-ttu-id="cffa0-175">Les nouvelles tables peuvent être ajoutées dans ce schéma par les membres du rôle mdw_writer.</span><span class="sxs-lookup"><span data-stu-id="cffa0-175">New tables can be added in this schema by members of the mdw_writer role.</span></span> <span data-ttu-id="cffa0-176">Toute autre modification du schéma ne peut être apportée que par des membres du rôle mdw_admin.</span><span class="sxs-lookup"><span data-stu-id="cffa0-176">Any other changes to the schema can only be made by members of the mdw_admin role.</span></span>  
  
 <span data-ttu-id="cffa0-177">Vous pouvez obtenir des informations détaillées sur le type et le contenu des données pour les colonnes de table de base de données en lisant la documentation de la procédure stockée du collecteur de données approprié pour chacune des tables.</span><span class="sxs-lookup"><span data-stu-id="cffa0-177">You can get detailed data type and content information for the database table columns by reading the documentation for the appropriate data collector stored procedure for each of the tables.</span></span>  
  
### <a name="best-practices"></a><span data-ttu-id="cffa0-178">Bonnes pratiques</span><span class="sxs-lookup"><span data-stu-id="cffa0-178">Best Practices</span></span>  
 <span data-ttu-id="cffa0-179">Lors de l'utilisation de l'entrepôt de données de gestion, nous vous recommandons d'appliquer les méthodes conseillées suivantes :</span><span class="sxs-lookup"><span data-stu-id="cffa0-179">When working with the management data warehouse, we recommend following these best practices:</span></span>  
  
-   <span data-ttu-id="cffa0-180">Ne modifiez pas les métadonnées des tables de l'entrepôt de données de gestion sauf si vous ajoutez un nouveau type de collecteur.</span><span class="sxs-lookup"><span data-stu-id="cffa0-180">Do not modify the metadata of management data warehouse tables unless you are adding a new collector type.</span></span>  
  
-   <span data-ttu-id="cffa0-181">Ne modifiez pas directement les données dans l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="cffa0-181">Do not directly modify the data in the management data warehouse.</span></span> <span data-ttu-id="cffa0-182">Le fait de modifier les données recueillies invalide leur légitimité.</span><span class="sxs-lookup"><span data-stu-id="cffa0-182">Changing the data that you have collected invalidates the legitimacy of the collected data.</span></span>  
  
-   <span data-ttu-id="cffa0-183">Au lieu d'utiliser directement les tables, recourez aux procédures stockées et aux fonctions documentées fournies avec le collecteur de données pour accéder aux données d'instance et d'application.</span><span class="sxs-lookup"><span data-stu-id="cffa0-183">Instead of directly using the tables, use the documented stored procedures and functions that are provided with the data collector to access instance and application data.</span></span> <span data-ttu-id="cffa0-184">Les noms et les définitions de tables peuvent changer, sont modifiés lorsque vous mettez à jour l'application et pourront différer dans des versions futures.</span><span class="sxs-lookup"><span data-stu-id="cffa0-184">The table names and definitions can change, do change when you update the application, and might change in future releases.</span></span>  
  
## <a name="change-history"></a><span data-ttu-id="cffa0-185">Historique des modifications</span><span class="sxs-lookup"><span data-stu-id="cffa0-185">Change History</span></span>  
  
|<span data-ttu-id="cffa0-186">Mise à jour du contenu</span><span class="sxs-lookup"><span data-stu-id="cffa0-186">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="cffa0-187">Ajout de la table core.performance_counter_report_group_items à la section « Schéma principal (Core) ».</span><span class="sxs-lookup"><span data-stu-id="cffa0-187">Added the core.performance_counter_report_group_items table to the "Core schema" section.</span></span>|  
|<span data-ttu-id="cffa0-188">Mise à jour de la liste de tables dans la section « Schéma des instantanés ».</span><span class="sxs-lookup"><span data-stu-id="cffa0-188">Updated the list of tables in the "Snapshots schema" section.</span></span> <span data-ttu-id="cffa0-189">Ajout de snapshots.os_memory_clerks, snapshots.sql_process_and_system_memory et snapshots.io_virtual_file_stats.</span><span class="sxs-lookup"><span data-stu-id="cffa0-189">Added snapshots.os_memory_clerks,snapshots.sql_process_and_system_memory, and snapshots.io_virtual_file_stats.</span></span> <span data-ttu-id="cffa0-190">Suppression de snapshots.os_process_memory et snapshots.distinct_query_stats.</span><span class="sxs-lookup"><span data-stu-id="cffa0-190">Removedsnapshots.os_process_memory and snapshots.distinct_query_stats.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cffa0-191">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cffa0-191">See Also</span></span>  
 <span data-ttu-id="cffa0-192">[Procédures stockées de l’entrepôt de données de gestion &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cffa0-192">[Management Data Warehouse Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/management-data-warehouse-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="cffa0-193">[Procédures stockées du collecteur de données &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cffa0-193">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="cffa0-194">[Collecte de données](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="cffa0-194">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="cffa0-195">Afficher un rapport de jeu d’éléments de collecte &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="cffa0-195">View a Collection Set Report &#40;SQL Server Management Studio&#41;</span></span>](view-a-collection-set-report-sql-server-management-studio.md)  
  
  
