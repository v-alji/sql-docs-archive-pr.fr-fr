---
title: Réorganiser l’index, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.reorganizeindextask.f1
helpviewer_keywords:
- reorganizing indexes
- Reorganize Index task [Integration Services]
- indexes [Integration Services]
ms.assetid: 9ed87861-e5c3-4fcd-8760-d112f4c0af0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3f910391bd3a5a35770bb677bc17c91a00ace457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611212"
---
# <a name="reorganize-index-task"></a><span data-ttu-id="97861-102">Tâche Réorganiser l'index</span><span class="sxs-lookup"><span data-stu-id="97861-102">Reorganize Index Task</span></span>
  <span data-ttu-id="97861-103">La tâche Réorganiser l'index réorganise les index dans les vues et les tables de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97861-103">The Reorganize Index task reorganizes indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="97861-104">Pour plus d’informations sur la gestion des index, consultez [Réorganiser et reconstruire des index](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="97861-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="97861-105">La tâche Réorganiser l'index permet à un package de réorganiser les index dans une ou plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="97861-105">By using the Reorganize Index task, a package can reorganize indexes in a single database or multiple databases.</span></span> <span data-ttu-id="97861-106">Si la tâche réorganise uniquement les index d'une base de données, vous pouvez choisir les vues ou les tables dont les index sont à réorganiser.</span><span class="sxs-lookup"><span data-stu-id="97861-106">If the task reorganizes only the indexes in a single database, you can choose the views or the tables whose indexes the task reorganizes.</span></span> <span data-ttu-id="97861-107">En outre, la tâche Réorganiser l'index comprend une option qui permet de compacter les données d'objets volumineux.</span><span class="sxs-lookup"><span data-stu-id="97861-107">The Reorganize Index task also includes an option to compact large object data.</span></span> <span data-ttu-id="97861-108">Les données d'objets volumineux peuvent avoir les types de données suivants : `image`, `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)` ou `xml`.</span><span class="sxs-lookup"><span data-stu-id="97861-108">Large object data is data with the `image`, `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, or `xml` data type.</span></span> <span data-ttu-id="97861-109">Pour plus d’informations, consultez [Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="97861-109">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
 <span data-ttu-id="97861-110">La tâche Réorganiser l'index encapsule l'instruction Transact-SQL ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="97861-110">The Reorganize Index task encapsulates the Transact-SQL ALTER INDEX statement.</span></span> <span data-ttu-id="97861-111">Si vous choisissez de compacter les données d'objet volumineux, l'instruction utilise la clause REORGANIZE WITH (LOB_COMPACTION = ON), sinon l'option LOB_COMPACTION a pour valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="97861-111">If you choose to compact large object data, the statement uses the REORGANIZE WITH (LOB_COMPACTION = ON) clause, otherwise LOB_COMPACTION is set to OFF.</span></span> <span data-ttu-id="97861-112">Pour plus d’informations, consultez [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="97861-112">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="97861-113">Le temps que prend la tâche à créer l'instruction Transact-SQL qu'elle exécute est proportionnel au nombre d'index qu'elle réorganise.</span><span class="sxs-lookup"><span data-stu-id="97861-113">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of indexes the task reorganizes.</span></span> <span data-ttu-id="97861-114">Si la tâche est configurée de manière à réorganiser les index dans toutes les tables et vues d'une base de données avec de nombreux index ou à réorganiser les index de plusieurs bases de données, elle peut prendre beaucoup de temps pour générer l'instruction Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="97861-114">If the task is configured to reorganize indexes in all the tables and views in a database that holds a large number of indexes, or to reorganize indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-reorganize-index-task"></a><span data-ttu-id="97861-115">Configuration de la tâche Réorganiser l'index</span><span class="sxs-lookup"><span data-stu-id="97861-115">Configuration of the Reorganize Index Task</span></span>  
 <span data-ttu-id="97861-116">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97861-116">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="97861-117">Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97861-117">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="97861-118">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="97861-118">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="97861-119">Tâche Réorganiser l’index &#40;Plan de maintenance&#41;</span><span class="sxs-lookup"><span data-stu-id="97861-119">Reorganize Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/reorganize-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="97861-120">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="97861-120">Related Tasks</span></span>  
 <span data-ttu-id="97861-121">Pour plus d’informations sur la façon de définir ces propriétés dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , consultez [Définir les propriétés d’une tâche ou d’un conteneur](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="97861-121">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97861-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97861-122">See Also</span></span>  
 <span data-ttu-id="97861-123">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="97861-123">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="97861-124">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="97861-124">Control Flow</span></span>](control-flow.md)  
  
  
