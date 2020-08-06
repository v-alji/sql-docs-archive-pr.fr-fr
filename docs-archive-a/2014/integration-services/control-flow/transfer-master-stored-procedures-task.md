---
title: Transfert de procédures stockées de master, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfermasterspstask.f1
helpviewer_keywords:
- Transfer Master Stored Procedures task [Integration Services]
ms.assetid: 81702560-48a3-46d1-a469-e41304c7af8e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1915a3129eeb6e14c4315c37f2c6c2bf5b0d5412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708520"
---
# <a name="transfer-master-stored-procedures-task"></a><span data-ttu-id="faaa0-102">Tâche de transfert de procédures stockées de master</span><span class="sxs-lookup"><span data-stu-id="faaa0-102">Transfer Master Stored Procedures Task</span></span>
  <span data-ttu-id="faaa0-103">La tâche de transfert de procédures stockées de master transfère une ou plusieurs procédures stockées définies par l’utilisateur entre les bases de données **master** sur des instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="faaa0-103">The Transfer Master Stored Procedures task transfers one or more user-defined stored procedures between **master** databases on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="faaa0-104">Pour transférer une procédure stockée à partir de la base de données **master** , le propriétaire de la procédure doit être dbo.</span><span class="sxs-lookup"><span data-stu-id="faaa0-104">To transfer a stored procedure from the **master** database, the owner of the procedure must be dbo.</span></span>  
  
 <span data-ttu-id="faaa0-105">La tâche de transfert de procédures stockées de master peut être configurée pour transférer toutes les procédures stockées ou seulement des procédures spécifiées.</span><span class="sxs-lookup"><span data-stu-id="faaa0-105">The Transfer Master Stored Procedures task can be configured to transfer all stored procedures or only specified stored procedures.</span></span> <span data-ttu-id="faaa0-106">Cette tâche ne copie pas les procédures stockées système.</span><span class="sxs-lookup"><span data-stu-id="faaa0-106">This task does not copy system stored procedures.</span></span>  
  
 <span data-ttu-id="faaa0-107">Les procédures stockées de master à transférer peuvent déjà exister à l'emplacement de destination.</span><span class="sxs-lookup"><span data-stu-id="faaa0-107">The master stored procedures to be transferred may already exist on the destination.</span></span> <span data-ttu-id="faaa0-108">La tâche de transfert de procédures stockées de master peut être configurée pour traiter les procédures stockées existantes de différentes façons :</span><span class="sxs-lookup"><span data-stu-id="faaa0-108">The Transfer Master Stored Procedures task can be configured to handle existing stored procedures in the following ways:</span></span>  
  
-   <span data-ttu-id="faaa0-109">Remplacer les procédures stockées existantes.</span><span class="sxs-lookup"><span data-stu-id="faaa0-109">Overwrite existing stored procedures.</span></span>  
  
-   <span data-ttu-id="faaa0-110">Provoquer l'échec de la tâche lorsque des procédures stockées dupliquées existent.</span><span class="sxs-lookup"><span data-stu-id="faaa0-110">Fail the task when duplicate stored procedures exist.</span></span>  
  
-   <span data-ttu-id="faaa0-111">Ignorer les procédures stockées dupliquées.</span><span class="sxs-lookup"><span data-stu-id="faaa0-111">Skip duplicate stored procedures.</span></span>  
  
 <span data-ttu-id="faaa0-112">À l'exécution, la tâche de transfert des procédures stockées de master se connecte aux serveurs source et destination en utilisant deux gestionnaires de connexions SMO.</span><span class="sxs-lookup"><span data-stu-id="faaa0-112">At run time, the Transfer Master Stored Procedures task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="faaa0-113">Les gestionnaires de connexions SMO sont configurés indépendamment de la tâche de transfert des procédures stockées de master, puis référencés dans celle-ci.</span><span class="sxs-lookup"><span data-stu-id="faaa0-113">The SMO connection managers are configured separately from the Transfer Master Stored Procedures task, and then referenced in the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="faaa0-114">Les gestionnaires de connexions SMO spécifient le serveur et le mode d'authentification à utiliser lors de l'accès au serveur.</span><span class="sxs-lookup"><span data-stu-id="faaa0-114">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="faaa0-115">Pour plus d'informations, consultez [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="faaa0-115">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
## <a name="transferring-stored-procedures-between-instances-of-sql-server"></a><span data-ttu-id="faaa0-116">Transfert de procédures stockées entre des instances de SQL Server</span><span class="sxs-lookup"><span data-stu-id="faaa0-116">Transferring Stored Procedures Between Instances of SQL Server</span></span>  
 <span data-ttu-id="faaa0-117">La tâche de transfert de procédures stockées de master prend en charge une source et une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="faaa0-117">The Transfer Master Stored Procedures task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="faaa0-118">Événements</span><span class="sxs-lookup"><span data-stu-id="faaa0-118">Events</span></span>  
 <span data-ttu-id="faaa0-119">La tâche génère un événement d'information qui indique le nombre de procédures stockées transférées et un événement d'avertissement lorsque qu'une procédure stockée est remplacée.</span><span class="sxs-lookup"><span data-stu-id="faaa0-119">The task raises an information event that reports the number of stored procedures transferred and a warning event when a stored procedure is overwritten.</span></span>  
  
 <span data-ttu-id="faaa0-120">La tâche de transfert des procédures stockées de master n'indique pas les stades intermédiaires de l'avancement du transfert des connexions : elle signale la tâche comme réalisée à 0 % ou à 100 %.</span><span class="sxs-lookup"><span data-stu-id="faaa0-120">The Transfer Master Stored Procedures task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="faaa0-121">Valeur d'exécution</span><span class="sxs-lookup"><span data-stu-id="faaa0-121">Execution Value</span></span>  
 <span data-ttu-id="faaa0-122">La valeur d'exécution, définie dans la propriété `ExecutionValue` de la tâche, renvoie le nombre de procédures stockées transférées.</span><span class="sxs-lookup"><span data-stu-id="faaa0-122">The execution value, defined in the `ExecutionValue` property of the task, returns the number of stored procedures transferred.</span></span> <span data-ttu-id="faaa0-123">En affectant une variable définie par l'utilisateur à la propriété `ExecValueVariable` de la tâche de transfert des procédures stockées de master, les informations sur le transfert des procédures stockées peuvent être rendues disponibles aux autres objets du package.</span><span class="sxs-lookup"><span data-stu-id="faaa0-123">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Master Stored Procedures task, information about the stored procedure transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="faaa0-124">Pour plus d’informations, consultez [Variables Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) et [Utiliser des variables dans des packages](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="faaa0-124">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="faaa0-125">Entrées du journal</span><span class="sxs-lookup"><span data-stu-id="faaa0-125">Log Entries</span></span>  
 <span data-ttu-id="faaa0-126">La tâche de transfert des procédures stockées comporte les entrées de journal personnalisées suivantes :</span><span class="sxs-lookup"><span data-stu-id="faaa0-126">The Transfer Master Stored Procedures task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="faaa0-127">TransferStoredProceduresTaskStartTransferringObjects Cette entrée du journal indique que le transfert a commencé.</span><span class="sxs-lookup"><span data-stu-id="faaa0-127">TransferStoredProceduresTaskStartTransferringObjects  This log entry reports that the transfer has started.</span></span> <span data-ttu-id="faaa0-128">L'entrée du journal inclut l'heure de début.</span><span class="sxs-lookup"><span data-stu-id="faaa0-128">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="faaa0-129">TransferSStoredProceduresTaskFinishedTransferringObjects Cette entrée du journal indique que le transfert est terminé.</span><span class="sxs-lookup"><span data-stu-id="faaa0-129">TransferSStoredProceduresTaskFinishedTransferringObjects  This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="faaa0-130">L'entrée du journal inclut l'heure de fin.</span><span class="sxs-lookup"><span data-stu-id="faaa0-130">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="faaa0-131">En outre, une entrée de journal pour l'événement `OnInformation` indique le nombre de procédures stockées qui ont été transférées et une entrée de journal pour l'événement `OnWarning` est générée pour chaque procédure stockée remplacée à l'emplacement de destination.</span><span class="sxs-lookup"><span data-stu-id="faaa0-131">In addition, a log entry for the `OnInformation` event reports the number of stored procedures that were transferred, and a log entry for the `OnWarning` event is written for each stored procedure on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="faaa0-132">Sécurité et autorisations</span><span class="sxs-lookup"><span data-stu-id="faaa0-132">Security and Permissions</span></span>  
 <span data-ttu-id="faaa0-133">L’utilisateur doit avoir l’autorisation d’afficher la liste des procédures stockées dans la base de données **master** sur la source et doit être un membre du rôle serveur sysadmin ou disposer de l’autorisation de créer des procédures stockées dans la base de données **master** sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="faaa0-133">The user must have permission to view the list of stored procedure in the **master** database on the source, and must be a member of the sysadmin server role or have permission to created stored procedures in the **master** database on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-master-stored-procedures-task"></a><span data-ttu-id="faaa0-134">Configuration de la tâche de transfert de procédures stockées de master</span><span class="sxs-lookup"><span data-stu-id="faaa0-134">Configuration of the Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="faaa0-135">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="faaa0-135">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="faaa0-136">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="faaa0-136">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="faaa0-137">Éditeur de tâche de transfert de procédures stockées de master &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="faaa0-137">Transfer Master Stored Procedures Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="faaa0-138">Éditeur de tâche de transfert de procédures stockées de master &#40;page Procédures stockées&#41;</span><span class="sxs-lookup"><span data-stu-id="faaa0-138">Transfer Master Stored Procedures Task Editor &#40;Stored Procedures Page&#41;</span></span>](../transfer-master-stored-procedures-task-editor-stored-procedures-page.md)  
  
-   [<span data-ttu-id="faaa0-139">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="faaa0-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="faaa0-140">Pour plus d'informations sur la définition par programmation de ces propriétés, cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="faaa0-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferStoredProceduresTask.TransferStoredProceduresTask>  
  
### <a name="configuring-the-transfer-master-stored-procedures-task-programmatically"></a><span data-ttu-id="faaa0-141">Configuration par programmation de la tâche de transfert de procédures stockées de master</span><span class="sxs-lookup"><span data-stu-id="faaa0-141">Configuring the Transfer Master Stored Procedures Task Programmatically</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="faaa0-142">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="faaa0-142">Related Tasks</span></span>  
 <span data-ttu-id="faaa0-143">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="faaa0-143">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="faaa0-144">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="faaa0-144">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="faaa0-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="faaa0-145">See Also</span></span>  
 <span data-ttu-id="faaa0-146">[Tâche de transfert d'objets SQL Server](transfer-sql-server-objects-task.md) </span><span class="sxs-lookup"><span data-stu-id="faaa0-146">[Transfer SQL Server Objects Task](transfer-sql-server-objects-task.md) </span></span>  
 <span data-ttu-id="faaa0-147">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="faaa0-147">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="faaa0-148">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="faaa0-148">Control Flow</span></span>](control-flow.md)  
  
  
