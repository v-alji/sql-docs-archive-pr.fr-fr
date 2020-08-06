---
title: Réduire la base de données, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.shrinkdatabasetask.f1
helpviewer_keywords:
- Shrink Database task
- database shrinking [Integration Services]
- shrinking databases
ms.assetid: e66286f8-97b1-4e5a-86b4-e56f1932b7d5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 587777928e362e87e4b691e3c46167c1239984cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613083"
---
# <a name="shrink-database-task"></a><span data-ttu-id="f3bbb-102">tâche Réduire la base de données</span><span class="sxs-lookup"><span data-stu-id="f3bbb-102">Shrink Database Task</span></span>
  <span data-ttu-id="f3bbb-103">La tâche Réduire la base de données réduit la taille des fichiers journaux et de données de bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f3bbb-103">The Shrink Database task reduces the size of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database data and log files.</span></span>  
  
 <span data-ttu-id="f3bbb-104">La tâche Réduire la base de données permet à un package de réduire les fichiers d'une ou plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="f3bbb-104">By using the Shrink Database task, a package can shrink files for a single database or multiple databases.</span></span>  
  
 <span data-ttu-id="f3bbb-105">La réduction des fichiers de données permet de récupérer de l'espace en déplaçant des pages de données de la fin du fichier vers un espace inoccupé plus proche de l'avant du fichier.</span><span class="sxs-lookup"><span data-stu-id="f3bbb-105">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="f3bbb-106">Lorsqu'une quantité d'espace libre suffisante est créée à la fin du fichier, des pages de données à la fin du fichier peuvent être désallouées et retournées au système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f3bbb-106">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="f3bbb-107">Les données qui sont déplacées pour réduire un fichier peuvent être dispersées à n'importe quel emplacement disponible dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="f3bbb-107">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="f3bbb-108">Cela provoque la fragmentation de l'index et peut ralentir les performances des requêtes qui recherchent une plage de l'index.</span><span class="sxs-lookup"><span data-stu-id="f3bbb-108">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="f3bbb-109">Pour éliminer la fragmentation, reconstruisez les index dans le fichier après réduction.</span><span class="sxs-lookup"><span data-stu-id="f3bbb-109">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="commands"></a><span data-ttu-id="f3bbb-110">Commandes</span><span class="sxs-lookup"><span data-stu-id="f3bbb-110">Commands</span></span>  
 <span data-ttu-id="f3bbb-111">La tâche Réduire la base de données encapsule une commande DBCC SHRINKDATABASE, avec les options et les arguments suivants :</span><span class="sxs-lookup"><span data-stu-id="f3bbb-111">The Shrink Database task encapsulates a DBCC SHRINKDATABASE command, including the following arguments and options:</span></span>  
  
-   <span data-ttu-id="f3bbb-112">*database_name*</span><span class="sxs-lookup"><span data-stu-id="f3bbb-112">*database_name*</span></span>  
  
-   <span data-ttu-id="f3bbb-113">*target_percent*</span><span class="sxs-lookup"><span data-stu-id="f3bbb-113">*target_percent*</span></span>  
  
-   <span data-ttu-id="f3bbb-114">NOTRUNCATE ou TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="f3bbb-114">NOTRUNCATE or TRUNCATEONLY.</span></span>  
  
 <span data-ttu-id="f3bbb-115">Si la tâche de réduction de base de données réduit plusieurs bases de données, la tâche exécute plusieurs commandes SHRINKDATABASE, une pour chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="f3bbb-115">If the Shrink Database task shrinks multiple databases, the task runs multiple SHRINKDATABASE commands, one for each database.</span></span> <span data-ttu-id="f3bbb-116">Toutes les instances de la commande SHRINKDATABASE utilisent les mêmes valeurs d’argument, sauf pour l’argument *database_name* .</span><span class="sxs-lookup"><span data-stu-id="f3bbb-116">All instances of the SHRINKDATABASE command use the same argument values, except for the *database_name* argument.</span></span> <span data-ttu-id="f3bbb-117">Pour plus d’informations, consultez [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f3bbb-117">For more information, see [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span></span>  
  
## <a name="configuration-of-the-shrink-database-task"></a><span data-ttu-id="f3bbb-118">Configuration de la tâche Réduire la base de données</span><span class="sxs-lookup"><span data-stu-id="f3bbb-118">Configuration of the Shrink Database Task</span></span>  
 <span data-ttu-id="f3bbb-119">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f3bbb-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="f3bbb-120">Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f3bbb-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="f3bbb-121">Pour plus d’informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="f3bbb-121">For more information about the properties that you can set in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="f3bbb-122">Tâche Réduire la base de données &#40;Plan de maintenance&#41;</span><span class="sxs-lookup"><span data-stu-id="f3bbb-122">Shrink Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/shrink-database-task-maintenance-plan.md)  
  
 <span data-ttu-id="f3bbb-123">Pour plus d’informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="f3bbb-123">For more information about setting these properties in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="f3bbb-124">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="f3bbb-124">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
