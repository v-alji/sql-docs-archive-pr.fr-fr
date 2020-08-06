---
title: Sauvegarder la base de données, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.backupdatabasetask.f1
helpviewer_keywords:
- database backups [Integration Services]
- Back Up Database task [Integration Services]
- backing up databases [Integration Services]
- transaction log backups [Integration Services]
- backing up transaction logs [Integration Services]
ms.assetid: b8839d71-13b7-41f2-a434-cb95020e79d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b0980d89cc915121414dd7d3c89be6f4d72eb715
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602954"
---
# <a name="back-up-database-task"></a><span data-ttu-id="e2058-102">Tâche Sauvegarder la base de données</span><span class="sxs-lookup"><span data-stu-id="e2058-102">Back Up Database Task</span></span>
  <span data-ttu-id="e2058-103">La tâche Sauvegarder la base de données effectue différents types de sauvegardes de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2058-103">The Back Up Database task performs different types of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database backups.</span></span> <span data-ttu-id="e2058-104">Pour plus d’informations, consultez [Sauvegarder et restaurer des bases de données SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e2058-104">For more information, see [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="e2058-105">La tâche Sauvegarder la base de données permet à un package de sauvegarder une ou plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="e2058-105">By using the Back Up Database task, a package can back up a single database or multiple databases.</span></span> <span data-ttu-id="e2058-106">Si la tâche ne sauvegarde qu'une seule base de données, vous pouvez choisir le composant de sauvegarde : la base de données ou ses fichiers et groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e2058-106">If the task backs up only a single database, you can choose the backup component: the database, or its files and filegroups.</span></span>  
  
## <a name="supported-recover-models-and-backup-types"></a><span data-ttu-id="e2058-107">Modes de récupération et types de sauvegarde pris en charge</span><span class="sxs-lookup"><span data-stu-id="e2058-107">Supported Recover Models and Backup Types</span></span>  
 <span data-ttu-id="e2058-108">Le tableau suivant décrit les modes de récupération et les types de sauvegarde pris en charge par la tâche Sauvegarder la base de données.</span><span class="sxs-lookup"><span data-stu-id="e2058-108">The following table lists the recovery models and backup types that the Back Up Database task supports.</span></span>  
  
|<span data-ttu-id="e2058-109">mode de récupération</span><span class="sxs-lookup"><span data-stu-id="e2058-109">Recovery model</span></span>|<span data-ttu-id="e2058-110">Base de données</span><span class="sxs-lookup"><span data-stu-id="e2058-110">Database</span></span>|<span data-ttu-id="e2058-111">Base de données différentielle</span><span class="sxs-lookup"><span data-stu-id="e2058-111">Database differential</span></span>|<span data-ttu-id="e2058-112">Journal des transactions</span><span class="sxs-lookup"><span data-stu-id="e2058-112">Transaction log</span></span>|<span data-ttu-id="e2058-113">Fichier ou différentielle de fichiers</span><span class="sxs-lookup"><span data-stu-id="e2058-113">File or file differential</span></span>|  
|--------------------|--------------|---------------------------|---------------------|-------------------------------|  
|<span data-ttu-id="e2058-114">Simple</span><span class="sxs-lookup"><span data-stu-id="e2058-114">Simple</span></span>|<span data-ttu-id="e2058-115">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="e2058-115">Required</span></span>|<span data-ttu-id="e2058-116">Facultatif</span><span class="sxs-lookup"><span data-stu-id="e2058-116">Optional</span></span>|<span data-ttu-id="e2058-117">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="e2058-117">Not supported</span></span>|<span data-ttu-id="e2058-118">Non pris en charge</span><span class="sxs-lookup"><span data-stu-id="e2058-118">Not supported</span></span>|  
|<span data-ttu-id="e2058-119">Complète</span><span class="sxs-lookup"><span data-stu-id="e2058-119">Full</span></span>|<span data-ttu-id="e2058-120">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="e2058-120">Required</span></span>|<span data-ttu-id="e2058-121">Facultatif</span><span class="sxs-lookup"><span data-stu-id="e2058-121">Optional</span></span>|<span data-ttu-id="e2058-122">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="e2058-122">Required</span></span>|<span data-ttu-id="e2058-123">Facultatif</span><span class="sxs-lookup"><span data-stu-id="e2058-123">Optional</span></span>|  
|<span data-ttu-id="e2058-124">Bulk-logged</span><span class="sxs-lookup"><span data-stu-id="e2058-124">Bulk-logged</span></span>|<span data-ttu-id="e2058-125">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="e2058-125">Required</span></span>|<span data-ttu-id="e2058-126">Facultatif</span><span class="sxs-lookup"><span data-stu-id="e2058-126">Optional</span></span>|<span data-ttu-id="e2058-127">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="e2058-127">Required</span></span>|<span data-ttu-id="e2058-128">Facultatif</span><span class="sxs-lookup"><span data-stu-id="e2058-128">Optional</span></span>|  
  
 <span data-ttu-id="e2058-129">La tâche Sauvegarder la base de données encapsule une instruction Transact-SQL BACKUP.</span><span class="sxs-lookup"><span data-stu-id="e2058-129">The Back Up Database task encapsulates a Transact-SQL BACKUP statement.</span></span> <span data-ttu-id="e2058-130">Pour plus d’informations, consultez [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e2058-130">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
## <a name="configuration-of-the-back-up-database-task"></a><span data-ttu-id="e2058-131">Configuration de la tâche Sauvegarder la base de données</span><span class="sxs-lookup"><span data-stu-id="e2058-131">Configuration of the Back Up Database Task</span></span>  
 <span data-ttu-id="e2058-132">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2058-132">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e2058-133">Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e2058-133">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="e2058-134">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="e2058-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e2058-135">Tâche Sauvegarder la base de données &#40;Plan de maintenance&#41;</span><span class="sxs-lookup"><span data-stu-id="e2058-135">Back Up Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/options-in-the-back-up-database-task-for-maintenance-plan.md)  
  
 <span data-ttu-id="e2058-136">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="e2058-136">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e2058-137">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="e2058-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
