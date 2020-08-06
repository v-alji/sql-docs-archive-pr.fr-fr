---
title: Reconstruire l’index, tâche| Documents Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rebuildindextask.f1
helpviewer_keywords:
- rebuilding indexes
- indexes [Integration Services]
- Rebuild Index task
ms.assetid: 021884dd-e72d-47b2-99e8-b741410509c3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33bbe25bc8c47f4f749f95dbb7096c3a76c25297
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611214"
---
# <a name="rebuild-index-task"></a><span data-ttu-id="91417-102">tâche Reconstruire l'index</span><span class="sxs-lookup"><span data-stu-id="91417-102">Rebuild Index Task</span></span>
  <span data-ttu-id="91417-103">La tâche Reconstruire l'index reconstruit les index dans les vues et les tables de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91417-103">The Rebuild Index task rebuilds indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="91417-104">Pour plus d’informations sur la gestion des index, consultez [Réorganiser et reconstruire des index](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="91417-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="91417-105">La tâche Reconstruire l'index permet à un package de reconstruire les index dans une ou plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="91417-105">By using the Rebuild Index task, a package can rebuild indexes in a single database or multiple databases.</span></span> <span data-ttu-id="91417-106">Si la tâche reconstruit uniquement les index d'une base de données, vous pouvez choisir les vues et les tables dont la tâche reconstruit les index.</span><span class="sxs-lookup"><span data-stu-id="91417-106">If the task rebuilds only the indexes in a single database, you can choose the views and tables whose indexes the task rebuilds.</span></span>  
  
 <span data-ttu-id="91417-107">Cette tâche encapsule une instruction ALTER INDEX REBUILD avec les options de reconstruction d'index suivantes :</span><span class="sxs-lookup"><span data-stu-id="91417-107">This task encapsulates an ALTER INDEX REBUILD statement with the following index rebuild options:</span></span>  
  
-   <span data-ttu-id="91417-108">Spécifiez un pourcentage FILLFACTOR ou utilisez la quantité d'origine de FILLFACTOR.</span><span class="sxs-lookup"><span data-stu-id="91417-108">Specify a FILLFACTOR percentage or use the original FILLFACTOR amount.</span></span>  
  
-   <span data-ttu-id="91417-109">Attribuez au paramètre PAD_INDEX la valeur ON afin d'allouer l'espace disponible spécifié par FILLFACTOR aux pages de niveau intermédiaire de l'index.</span><span class="sxs-lookup"><span data-stu-id="91417-109">Set PAD_INDEX = ON to allocate the free space specified by FILLFACTOR to the intermediate-level pages of the index.</span></span>  
  
-   <span data-ttu-id="91417-110">Attribuez au paramètre SORT_IN_TEMPDB la valeur ON afin de stocker dans tempdb le résultat intermédiaire du tri utilisé pour reconstruire l'index.</span><span class="sxs-lookup"><span data-stu-id="91417-110">Set SORT_IN_TEMPDB = ON to store the intermediate sort result used to rebuild the index in tempdb.</span></span> <span data-ttu-id="91417-111">Lorsque le résultat intermédiaire du tri a pour valeur OFF, il est stocké dans la même base de données que l'index.</span><span class="sxs-lookup"><span data-stu-id="91417-111">When the intermediate sort result is set to OFF, the result is stored in the same database as the index.</span></span>  
  
-   <span data-ttu-id="91417-112">Attribuez au paramètre IGNORE_DUP_KEY la valeur ON pour permettre une opération d'insertion de plusieurs lignes incluant les enregistrements qui violent des contraintes uniques afin d'insérer les enregistrements qui ne violent pas les contraintes uniques.</span><span class="sxs-lookup"><span data-stu-id="91417-112">Set IGNORE_DUP_KEY = ON to allow a multirow insert operation that includes records that violate unique constraints to insert the records that do not violate the unique constraints.</span></span>  
  
-   <span data-ttu-id="91417-113">Attribuez au paramètre ONLINE la valeur ON pour ne pas appliquer de verrous de table, afin que les requêtes ou les mises à jour portant sur la table sous-jacente puissent être exécutées pendant la réindexation.</span><span class="sxs-lookup"><span data-stu-id="91417-113">Set ONLINE = ON to not hold table locks so that queries or updates to the underlying table can proceed during re-indexing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91417-114">Les opérations d’index en ligne ne sont pas disponibles dans toutes les éditions de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91417-114">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="91417-115">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="91417-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="91417-116">Pour plus d’informations sur l’instruction ALTER INDEX et sur les options de reconstruction d’index, consultez [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="91417-116">For more information about the ALTER INDEX statement and index rebuild options, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="91417-117">Le temps que prend la tâche pour créer l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] qu'elle exécute est proportionnel au nombre d'index qu'elle reconstruit.</span><span class="sxs-lookup"><span data-stu-id="91417-117">The time the task takes to create the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that the task runs is proportionate to the number of indexes the task rebuilds.</span></span> <span data-ttu-id="91417-118">Si la tâche est configurée de manière à reconstruire les index dans toutes les tables et vues d'une base de données possédant de nombreux index ou à reconstruire les index de plusieurs bases de données, elle peut prendre un temps considérable pour générer l'instruction Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="91417-118">If the task is configured to rebuild indexes in all the tables and views in a database with a large number of indexes, or to rebuild indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-rebuild-index-task"></a><span data-ttu-id="91417-119">Configuration de la tâche Reconstruire l'index</span><span class="sxs-lookup"><span data-stu-id="91417-119">Configuration of the Rebuild Index Task</span></span>  
 <span data-ttu-id="91417-120">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91417-120">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="91417-121">Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91417-121">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="91417-122">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="91417-122">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
 [<span data-ttu-id="91417-123">Tâche Reconstruire l’index &#40;Plan de maintenance&#41;</span><span class="sxs-lookup"><span data-stu-id="91417-123">Rebuild Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/rebuild-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="91417-124">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="91417-124">Related Tasks</span></span>  
 <span data-ttu-id="91417-125">Pour plus d’informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , consultez [Définir les propriétés d’une tâche ou d’un conteneur](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="91417-125">For more about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91417-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="91417-126">See Also</span></span>  
 <span data-ttu-id="91417-127">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="91417-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="91417-128">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="91417-128">Control Flow</span></span>](control-flow.md)  
  
  
