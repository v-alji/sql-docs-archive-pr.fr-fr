---
title: Transfert de travaux, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.f1
helpviewer_keywords:
- Transfer Jobs task [Integration Services]
ms.assetid: 1bf33885-9c5b-47e4-a549-f5920b66a1de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d692934d5f7c8c1449b123ee8b9caf1d8bb34744
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600168"
---
# <a name="transfer-jobs-task"></a><span data-ttu-id="14737-102">Tâche de transfert de travaux</span><span class="sxs-lookup"><span data-stu-id="14737-102">Transfer Jobs Task</span></span>
  <span data-ttu-id="14737-103">La tâche de transfert de travaux transfère un ou plusieurs travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] entre des instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14737-103">The Transfer Jobs task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="14737-104">La tâche de transfert de travaux peut être configurée pour transférer tous les travaux ou seulement certains travaux spécifiés.</span><span class="sxs-lookup"><span data-stu-id="14737-104">The Transfer Jobs task can be configured to transfer all jobs, or only specified jobs.</span></span> <span data-ttu-id="14737-105">Vous pouvez également spécifier si les travaux transférés sont activés lorsqu'ils arrivent à destination.</span><span class="sxs-lookup"><span data-stu-id="14737-105">You can also indicate whether the transferred jobs are enabled at the destination.</span></span>  
  
 <span data-ttu-id="14737-106">Les travaux à transférer peuvent déjà exister à l'emplacement de destination.</span><span class="sxs-lookup"><span data-stu-id="14737-106">The jobs to be transferred may already exist on the destination.</span></span> <span data-ttu-id="14737-107">La tâche de transfert de travaux peut être configurée pour traiter les travaux existants de différentes manières :</span><span class="sxs-lookup"><span data-stu-id="14737-107">The Transfer Jobs task can be configured to handle existing jobs in the following ways:</span></span>  
  
-   <span data-ttu-id="14737-108">Remplacer les travaux existants.</span><span class="sxs-lookup"><span data-stu-id="14737-108">Overwrite existing jobs.</span></span>  
  
-   <span data-ttu-id="14737-109">Provoquer l'échec de la tâche lorsque des travaux dupliqués existent.</span><span class="sxs-lookup"><span data-stu-id="14737-109">Fail the task when duplicate jobs exist.</span></span>  
  
-   <span data-ttu-id="14737-110">Ignorer les travaux dupliqués.</span><span class="sxs-lookup"><span data-stu-id="14737-110">Skip duplicate jobs.</span></span>  
  
 <span data-ttu-id="14737-111">À l'exécution, la tâche de transfert de travaux se connecte aux serveurs source et destination en utilisant un ou deux gestionnaires de connexions SMO.</span><span class="sxs-lookup"><span data-stu-id="14737-111">At run time, the Transfer Jobs task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="14737-112">Le gestionnaire de connexions SMO est configuré indépendamment de la tâche de transfert de travaux, puis il est référencé dans celle-ci.</span><span class="sxs-lookup"><span data-stu-id="14737-112">The SMO connection manager is configured separately from the Transfer Jobs task, and then is referenced in the Transfer Jobs task.</span></span> <span data-ttu-id="14737-113">Le gestionnaire de connexions SMO spécifie le serveur et le mode d'authentification à utiliser lors de l'accès au serveur.</span><span class="sxs-lookup"><span data-stu-id="14737-113">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="14737-114">Pour plus d'informations, consultez [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="14737-114">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-jobs-between-instances-of-sql-server"></a><span data-ttu-id="14737-115">Transfert de travaux entre des instances de SQL Server</span><span class="sxs-lookup"><span data-stu-id="14737-115">Transferring Jobs Between Instances of SQL Server</span></span>  
 <span data-ttu-id="14737-116">La tâche de transfert de travaux prend en charge une source et une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14737-116">The Transfer Jobs task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="14737-117">Chacune des versions peut être utilisée indifféremment comme source ou comme destination.</span><span class="sxs-lookup"><span data-stu-id="14737-117">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="14737-118">Événements</span><span class="sxs-lookup"><span data-stu-id="14737-118">Events</span></span>  
 <span data-ttu-id="14737-119">La tâche de transfert de travaux génère un événement d'information qui indique le nombre de travaux transférés et un événement d'avertissement quand un travail est remplacé.</span><span class="sxs-lookup"><span data-stu-id="14737-119">The Transfer Jobs task raises an information event that reports the number of jobs transferred and a warning event when a job is overwritten.</span></span> <span data-ttu-id="14737-120">La tâche n'indique pas les stades intermédiaires de l'avancement du transfert de travaux ; elle ne signale qu'une réalisation à 0 % ou à 100 %.</span><span class="sxs-lookup"><span data-stu-id="14737-120">The task does not report incremental progress of the job transfer; it reports only 0% and 100% completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="14737-121">Valeur d'exécution</span><span class="sxs-lookup"><span data-stu-id="14737-121">Execution Value</span></span>  
 <span data-ttu-id="14737-122">La valeur d’exécution, définie dans la `ExecutionValue` propriété de la tâche, retourne le nombre de travaux qui sont transférés.</span><span class="sxs-lookup"><span data-stu-id="14737-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of jobs that are transferred.</span></span> <span data-ttu-id="14737-123">En affectant une variable définie par l'utilisateur à la propriété `ExecValueVariable` de la tâche de transfert de travaux, les informations sur le transfert de travaux peuvent être rendues disponibles pour d'autres objets du package.</span><span class="sxs-lookup"><span data-stu-id="14737-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Jobs task, information about the job transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="14737-124">Pour plus d’informations, consultez [Variables Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) et [Utiliser des variables dans des packages](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="14737-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="14737-125">Entrées du journal</span><span class="sxs-lookup"><span data-stu-id="14737-125">Log Entries</span></span>  
 <span data-ttu-id="14737-126">La tâche de transfert de travaux comporte les entrées du journal personnalisées suivantes :</span><span class="sxs-lookup"><span data-stu-id="14737-126">The Transfer Jobs task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="14737-127">TransferJobsTaskStarTransferringObjects   Cette entrée du journal indique que le transfert a commencé.</span><span class="sxs-lookup"><span data-stu-id="14737-127">TransferJobsTaskStarTransferringObjects   This log entry reports that the transfer has started.</span></span> <span data-ttu-id="14737-128">L'entrée du journal inclut l'heure de début.</span><span class="sxs-lookup"><span data-stu-id="14737-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="14737-129">TransferJobsTaskFinishedTransferringObjects   Cette entrée du journal indique que le transfert est terminé.</span><span class="sxs-lookup"><span data-stu-id="14737-129">TransferJobsTaskFinishedTransferringObjects    This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="14737-130">L'entrée du journal inclut l'heure de fin.</span><span class="sxs-lookup"><span data-stu-id="14737-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="14737-131">En outre, une entrée de journal pour l'événement `OnInformation` indique le nombre de travaux qui ont été transférés et une entrée de journal pour l'événement `OnWarning` est générée pour chaque travail remplacé à l'emplacement de destination.</span><span class="sxs-lookup"><span data-stu-id="14737-131">In addition, a log entry for the `OnInformation` event reports the number of jobs that were transferred and a log entry for the `OnWarning` event is written for each job on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="14737-132">Sécurité et autorisations</span><span class="sxs-lookup"><span data-stu-id="14737-132">Security and Permissions</span></span>  
 <span data-ttu-id="14737-133">Pour transférer des travaux, l'utilisateur doit être un membre du rôle serveur fixe sysadmin ou de l'un des rôles de base de données fixes de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur la base de données msdb à la fois sur les instances source et destination de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14737-133">To transfer jobs, the user must be a member of the sysadmin fixed server role or one of the fixed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles on the msdb database on the both the source and destination instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="configuration-of-the-transfer-jobs-task"></a><span data-ttu-id="14737-134">Configuration de la tâche de transfert de travaux</span><span class="sxs-lookup"><span data-stu-id="14737-134">Configuration of the Transfer Jobs Task</span></span>  
 <span data-ttu-id="14737-135">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="14737-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="14737-136">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="14737-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="14737-137">Éditeur de tâche de transfert de travaux &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="14737-137">Transfer Jobs Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="14737-138">Éditeur de tâche de transfert de travaux &#40;page Travaux&#41;</span><span class="sxs-lookup"><span data-stu-id="14737-138">Transfer Jobs Task Editor &#40;Jobs Page&#41;</span></span>](../transfer-jobs-task-editor-jobs-page.md)  
  
-   [<span data-ttu-id="14737-139">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="14737-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="14737-140">Pour plus d'informations sur la définition par programmation de ces propriétés, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="14737-140">For information about programmatically setting these properties, click the of the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferJobsTask.TransferJobsTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="14737-141">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="14737-141">Related Tasks</span></span>  
 <span data-ttu-id="14737-142">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="14737-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="14737-143">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="14737-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="14737-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14737-144">See Also</span></span>  
 <span data-ttu-id="14737-145">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="14737-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="14737-146">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="14737-146">Control Flow</span></span>](control-flow.md)  
  
  
