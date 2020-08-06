---
title: Mettre à jour les statistiques, tâche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.updatestatisticstask.f1
helpviewer_keywords:
- updating statistics
- Update Statistics task [Integration Services]
ms.assetid: 0247483b-f092-4511-8fa8-3610108bd1bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1507ada1e4fa087901383930fce4996c191fb553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600161"
---
# <a name="update-statistics-task"></a><span data-ttu-id="a32f2-102">Tâche Mettre à jour les statistiques</span><span class="sxs-lookup"><span data-stu-id="a32f2-102">Update Statistics Task</span></span>
  <span data-ttu-id="a32f2-103">La tâche Mettre à jour les statistiques met à jour les informations sur la distribution des valeurs de clé pour un ou plusieurs groupes de statistiques (collections) dans la table ou la vue indexée spécifiées.</span><span class="sxs-lookup"><span data-stu-id="a32f2-103">The Update Statistics task updates information about the distribution of key values for one or more statistics groups (collections) in the specified table or indexed view.</span></span> <span data-ttu-id="a32f2-104">Pour plus d’informations, consultez [Statistiques](../../relational-databases/statistics/statistics.md).</span><span class="sxs-lookup"><span data-stu-id="a32f2-104">For more information, see [Statistics](../../relational-databases/statistics/statistics.md).</span></span>  
  
 <span data-ttu-id="a32f2-105">La tâche Mettre à jour les statistiques permet à un package de mettre à jour les statistiques d'une ou plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="a32f2-105">By using the Update Statistics task, a package can update statistics for a single database or multiple databases.</span></span> <span data-ttu-id="a32f2-106">Si la tâche met à jour uniquement les statistiques d'une base de données, vous pouvez choisir les vues ou les tables concernées par cette mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a32f2-106">If the task updates only the statistics in a single database, you can choose the views or the tables whose statistics the task updates.</span></span> <span data-ttu-id="a32f2-107">Vous pouvez configurer la mise à jour de manière à actualiser toutes les statistiques ou uniquement celles des colonnes ou des index.</span><span class="sxs-lookup"><span data-stu-id="a32f2-107">You can configure the update to update all statistics, column statistics only, or index statistics only.</span></span>  
  
 <span data-ttu-id="a32f2-108">Cette tâche encapsule une instruction UPDATE STATISTICS, qui comprend les clauses et les arguments suivants :</span><span class="sxs-lookup"><span data-stu-id="a32f2-108">This task encapsulates an UPDATE STATISTICS statement, including the following arguments and clauses:</span></span>  
  
-   <span data-ttu-id="a32f2-109">Argument *nom_table* ou *nom_vue* .</span><span class="sxs-lookup"><span data-stu-id="a32f2-109">The *table_name* or *view_name* argument.</span></span>  
  
-   <span data-ttu-id="a32f2-110">Si la mise à jour s'applique à toutes les statistiques, la clause WITH ALL est implicite.</span><span class="sxs-lookup"><span data-stu-id="a32f2-110">If the update applies to all statistics, the WITH ALL clause is implied.</span></span>  
  
-   <span data-ttu-id="a32f2-111">Si la mise à jour s'applique uniquement aux colonnes, la clause WITH COLUMN est incluse.</span><span class="sxs-lookup"><span data-stu-id="a32f2-111">If the update applies only to columns, the WITH COLUMN clause is included.</span></span>  
  
-   <span data-ttu-id="a32f2-112">Si la mise à jour s'applique uniquement aux index, la clause WITH INDEX est incluse.</span><span class="sxs-lookup"><span data-stu-id="a32f2-112">If the update applies only to indexes, the WITH INDEX clause is included.</span></span>  
  
 <span data-ttu-id="a32f2-113">Si la tâche Mettre à jour les statistiques met à jour les statistiques dans plusieurs bases de données, elle exécute plusieurs instructions UPDATE STATISTICS, à raison d'une pour chaque table ou vue.</span><span class="sxs-lookup"><span data-stu-id="a32f2-113">If the Update Statistics task updates statistics in multiple databases, the task runs multiple UPDATE STATISTICS statements, one for each table or view.</span></span> <span data-ttu-id="a32f2-114">Toutes les instances de l’instruction UPDATE STATISTICS utilisent la même clause, mais différentes valeurs pour *nom_table* ou pour *nom_vue* .</span><span class="sxs-lookup"><span data-stu-id="a32f2-114">All instances of UPDATE STATISTICS use the same clause, but different *table_name* or *view_name* values.</span></span> <span data-ttu-id="a32f2-115">Pour plus d’informations, consultez [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) et [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a32f2-115">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) and [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a32f2-116">Le temps que prend la tâche à créer l'instruction Transact-SQL qu'elle exécute est proportionnel au nombre de statistiques qu'elle met à jour.</span><span class="sxs-lookup"><span data-stu-id="a32f2-116">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of statistics the task updates.</span></span> <span data-ttu-id="a32f2-117">Si la tâche est configurée de manière à mettre à jour les statistiques de toutes les tables et vues d'une base de données avec un grand nombre d'index ou à mettre à jour les statistiques de plusieurs bases de données, elle peut prendre beaucoup de temps pour générer l'instruction Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a32f2-117">If the task is configured to update statistics in all the tables and views in a database with a large number of indexes, or to update statistics in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-update-statistics-task"></a><span data-ttu-id="a32f2-118">Configuration de la tâche Mettre à jour les statistiques</span><span class="sxs-lookup"><span data-stu-id="a32f2-118">Configuration of the Update Statistics Task</span></span>  
 <span data-ttu-id="a32f2-119">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a32f2-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a32f2-120">Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a32f2-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="a32f2-121">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="a32f2-121">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="a32f2-122">Tâche Mettre à jour les statistiques &#40;Plan de maintenance&#41;</span><span class="sxs-lookup"><span data-stu-id="a32f2-122">Update Statistics Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/update-statistics-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="a32f2-123">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a32f2-123">Related Tasks</span></span>  
 <span data-ttu-id="a32f2-124">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="a32f2-124">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="a32f2-125">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="a32f2-125">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="a32f2-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a32f2-126">See Also</span></span>  
 <span data-ttu-id="a32f2-127">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="a32f2-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="a32f2-128">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="a32f2-128">Control Flow</span></span>](control-flow.md)  
  
  
