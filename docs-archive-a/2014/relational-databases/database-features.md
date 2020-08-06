---
title: Fonctionnalités de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 04518abb-8581-47c8-a601-ee9136c3c0eb
author: rothja
ms.author: jroth
ms.openlocfilehash: 56b9f9ba9cc6e11ea82b822ae10b31710c8617b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611116"
---
# <a name="database-features"></a><span data-ttu-id="07e63-102">Fonctionnalités de base de données</span><span class="sxs-lookup"><span data-stu-id="07e63-102">Database Features</span></span>
  <span data-ttu-id="07e63-103">Cette section contient les fonctionnalités et les tâches associées aux bases de données, aux objets de base de données, aux types de données, ainsi que les mécanismes pour utiliser ou pour gérer des données.</span><span class="sxs-lookup"><span data-stu-id="07e63-103">This section contains the features and tasks associated with databases, database objects, data types, and the mechanisms used to work with or manage data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07e63-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="07e63-104">In This Section</span></span>  
  
|||
|--|--|
|[<span data-ttu-id="07e63-105">Bases de données</span><span class="sxs-lookup"><span data-stu-id="07e63-105">Databases</span></span>](databases/databases.md)|[<span data-ttu-id="07e63-106">Sauvegarder et restaurer des bases de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="07e63-106">Back Up and Restore of SQL Server Databases</span></span>](backup-restore/back-up-and-restore-of-sql-server-databases.md)|  
|[<span data-ttu-id="07e63-107">Tables</span><span class="sxs-lookup"><span data-stu-id="07e63-107">Tables</span></span>](tables/tables.md)|[<span data-ttu-id="07e63-108">Numéros de séquence</span><span class="sxs-lookup"><span data-stu-id="07e63-108">Sequence Numbers</span></span>](sequence-numbers/sequence-numbers.md)|[<span data-ttu-id="07e63-109">Importation et exportation en bloc de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="07e63-109">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](import-export/bulk-import-and-export-of-data-sql-server.md)|  
|[<span data-ttu-id="07e63-110">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="07e63-110">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](in-memory-oltp/in-memory-oltp-in-memory-optimization.md)|[<span data-ttu-id="07e63-111">Déclencheurs DDL</span><span class="sxs-lookup"><span data-stu-id="07e63-111">DDL Triggers</span></span>](triggers/ddl-triggers.md)|[<span data-ttu-id="07e63-112">Data Compression</span><span class="sxs-lookup"><span data-stu-id="07e63-112">Data Compression</span></span>](data-compression/data-compression.md)|  
|[<span data-ttu-id="07e63-113">Index</span><span class="sxs-lookup"><span data-stu-id="07e63-113">Indexes</span></span>](indexes/indexes.md)|[<span data-ttu-id="07e63-114">Déclencheurs DML</span><span class="sxs-lookup"><span data-stu-id="07e63-114">DML Triggers</span></span>](triggers/dml-triggers.md)|[<span data-ttu-id="07e63-115">Objets OLE Automation dans Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="07e63-115">OLE Automation Objects in Transact-SQL</span></span>](stored-procedures/ole-automation-objects-in-transact-sql.md)|  
|[<span data-ttu-id="07e63-116">Tables et index partitionnés</span><span class="sxs-lookup"><span data-stu-id="07e63-116">Partitioned Tables and Indexes</span></span>](partitions/partitioned-tables-and-indexes.md)|[<span data-ttu-id="07e63-117">Synonymes &#40;moteur de base de données &#41;</span><span class="sxs-lookup"><span data-stu-id="07e63-117">Synonyms &#40;Database Engine&#41;</span></span>](synonyms/synonyms-database-engine.md)|[<span data-ttu-id="07e63-118">Notifications d’événements</span><span class="sxs-lookup"><span data-stu-id="07e63-118">Event Notifications</span></span>](service-broker/event-notifications.md)|  
|[<span data-ttu-id="07e63-119">Views</span><span class="sxs-lookup"><span data-stu-id="07e63-119">Views</span></span>](views/views.md)|[<span data-ttu-id="07e63-120">Données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="07e63-120">XML Data &#40;SQL Server&#41;</span></span>](xml/xml-data-sql-server.md)|[<span data-ttu-id="07e63-121">Surveillance et réglage des performances</span><span class="sxs-lookup"><span data-stu-id="07e63-121">Monitor and Tune for Performance</span></span>](performance/monitor-and-tune-for-performance.md)|  
|[<span data-ttu-id="07e63-122">Procédures stockées &#40;moteur de base de données &#41;</span><span class="sxs-lookup"><span data-stu-id="07e63-122">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures/stored-procedures-database-engine.md)|[<span data-ttu-id="07e63-123">Données spatiales &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="07e63-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial/spatial-data-sql-server.md)||  
|[<span data-ttu-id="07e63-124">Rechercher &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="07e63-124">Search &#40;SQL Server&#41;</span></span>](../database-engine/search-sql-server.md)|[<span data-ttu-id="07e63-125">Objets binaires volumineux &#40;Objet BLOB&#41; Données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="07e63-125">Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;</span></span>](blob/binary-large-object-blob-data-sql-server.md)||  
|[<span data-ttu-id="07e63-126">Fonctions définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="07e63-126">User-Defined Functions</span></span>](user-defined-functions/user-defined-functions.md)|[<span data-ttu-id="07e63-127">Applications de la couche Données</span><span class="sxs-lookup"><span data-stu-id="07e63-127">Data-tier Applications</span></span>](data-tier-applications/data-tier-applications.md)||  
|[<span data-ttu-id="07e63-128">Statistiques</span><span class="sxs-lookup"><span data-stu-id="07e63-128">Statistics</span></span>](statistics/statistics.md)|[<span data-ttu-id="07e63-129">Journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="07e63-129">The Transaction Log &#40;SQL Server&#41;</span></span>](logs/the-transaction-log-sql-server.md)||  
|[<span data-ttu-id="07e63-130">Repères de plan</span><span class="sxs-lookup"><span data-stu-id="07e63-130">Plan Guides</span></span>](performance/plan-guides.md)|[<span data-ttu-id="07e63-131">Points de contrôle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="07e63-131">Database Checkpoints &#40;SQL Server&#41;</span></span>](logs/database-checkpoints-sql-server.md)||  
  
  
