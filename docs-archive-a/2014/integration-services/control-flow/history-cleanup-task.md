---
title: Nettoyage d’historique, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.historycleanuptask.f1
helpviewer_keywords:
- history tables [SQL Server]
- History Cleanup task [Integration Services]
ms.assetid: 5defc5b9-dfd3-4859-a7fe-ac8c2b5480f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84bc697b7fb18269fc581cea51e111aebc82c15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600182"
---
# <a name="history-cleanup-task"></a><span data-ttu-id="b2de3-102">Tâche de nettoyage d'historique</span><span class="sxs-lookup"><span data-stu-id="b2de3-102">History Cleanup Task</span></span>
  <span data-ttu-id="b2de3-103">La tâche de nettoyage d'historique supprime des entrées dans les tables d'historique suivantes de la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb.</span><span class="sxs-lookup"><span data-stu-id="b2de3-103">The History Cleanup task deletes entries in the following history tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
-   <span data-ttu-id="b2de3-104">backupfile</span><span class="sxs-lookup"><span data-stu-id="b2de3-104">backupfile</span></span>  
  
-   <span data-ttu-id="b2de3-105">backupfilegroup</span><span class="sxs-lookup"><span data-stu-id="b2de3-105">backupfilegroup</span></span>  
  
-   <span data-ttu-id="b2de3-106">backupmediafamily</span><span class="sxs-lookup"><span data-stu-id="b2de3-106">backupmediafamily</span></span>  
  
-   <span data-ttu-id="b2de3-107">backupmediaset</span><span class="sxs-lookup"><span data-stu-id="b2de3-107">backupmediaset</span></span>  
  
-   <span data-ttu-id="b2de3-108">backupset</span><span class="sxs-lookup"><span data-stu-id="b2de3-108">backupset</span></span>  
  
-   <span data-ttu-id="b2de3-109">restorefile</span><span class="sxs-lookup"><span data-stu-id="b2de3-109">restorefile</span></span>  
  
-   <span data-ttu-id="b2de3-110">restorefilegroup</span><span class="sxs-lookup"><span data-stu-id="b2de3-110">restorefilegroup</span></span>  
  
-   <span data-ttu-id="b2de3-111">restorehistory</span><span class="sxs-lookup"><span data-stu-id="b2de3-111">restorehistory</span></span>  
  
 <span data-ttu-id="b2de3-112">Grâce à la tâche de nettoyage d'historique, un package peut supprimer des données d'historique relatives aux activités de sauvegarde et de restauration, aux travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et aux plans de maintenance de base de données.</span><span class="sxs-lookup"><span data-stu-id="b2de3-112">By using the History Cleanup task, a package can delete historical data related to backup and restore activities, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, and database maintenance plans.</span></span>  
  
 <span data-ttu-id="b2de3-113">Cette tâche encapsule la procédure stockée système sp_delete_backuphistory et lui transmet la date spécifiée en guise d'argument.</span><span class="sxs-lookup"><span data-stu-id="b2de3-113">This task encapsulates the sp_delete_backuphistory system stored procedure and passes the specified date to the procedure as an argument.</span></span> <span data-ttu-id="b2de3-114">Pour plus d’informations, consultez [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2de3-114">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
## <a name="configuration-of-the-history-cleanup-task"></a><span data-ttu-id="b2de3-115">Configuration de la tâche de nettoyage d'historique</span><span class="sxs-lookup"><span data-stu-id="b2de3-115">Configuration of the History Cleanup Task</span></span>  
 <span data-ttu-id="b2de3-116">La tâche possède une propriété qui permet de spécifier la plus ancienne date des données conservées dans les tables d'historique.</span><span class="sxs-lookup"><span data-stu-id="b2de3-116">The task includes a property for specifying the oldest date of data retained in the history tables.</span></span> <span data-ttu-id="b2de3-117">Vous pouvez indiquer la date en nombre de jours, de semaines, de mois ou d'années par rapport au jour actuel ; la tâche convertit automatiquement l'intervalle en une date.</span><span class="sxs-lookup"><span data-stu-id="b2de3-117">You can indicate the date by number of days, weeks, months, or years from the current day, and the task automatically translates the interval to a date.</span></span>  
  
 <span data-ttu-id="b2de3-118">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2de3-118">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="b2de3-119">Cette tâche se trouve dans la section **Tâches du plan de maintenance** de la **boîte à outils** du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2de3-119">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="b2de3-120">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="b2de3-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="b2de3-121">Tâche de nettoyage d’historique &#40;Plan de maintenance&#41;</span><span class="sxs-lookup"><span data-stu-id="b2de3-121">History Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/history-cleanup-task-maintenance-plan.md)  
  
 <span data-ttu-id="b2de3-122">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="b2de3-122">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="b2de3-123">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="b2de3-123">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2de3-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2de3-124">See Also</span></span>  
 <span data-ttu-id="b2de3-125">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b2de3-125">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="b2de3-126">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="b2de3-126">Control Flow</span></span>](control-flow.md)  
  
  
