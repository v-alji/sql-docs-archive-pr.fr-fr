---
title: Observateur d’événement WMI, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatchertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Event Watcher task [Integration Services]
ms.assetid: b5bb52e9-a77e-41e1-93f9-d4c3bc6b2c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: be20624e5ccdf665e6274f647c342498e9c0f0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708515"
---
# <a name="wmi-event-watcher-task"></a><span data-ttu-id="2c54e-102">Tâche Observateur d'événement WMI</span><span class="sxs-lookup"><span data-stu-id="2c54e-102">WMI Event Watcher Task</span></span>
  <span data-ttu-id="2c54e-103">La tâche Observateur d'événement WMI observe les événements WMI (Windows Management Instrumentation) à l'aide d'une requête d'événement WQL (Windows Management Instrumentation Query Language) pour spécifier les événements dignes d'intérêt.</span><span class="sxs-lookup"><span data-stu-id="2c54e-103">The WMI Event Watcher task watches for a Windows Management Instrumentation (WMI) event using a Management Instrumentation Query Language (WQL) event query to specify events of interest.</span></span> <span data-ttu-id="2c54e-104">Vous pouvez utiliser la tâche Observateur d'événement WMI pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2c54e-104">You can use the WMI Event Watcher task for the following purposes:</span></span>  
  
-   <span data-ttu-id="2c54e-105">Attendre la notification signalant que des fichiers ont été ajoutés à un dossier, puis initier le traitement du fichier.</span><span class="sxs-lookup"><span data-stu-id="2c54e-105">Wait for notification that files have been added to a folder and then initiate the processing of the file.</span></span>  
  
-   <span data-ttu-id="2c54e-106">Exécuter un package qui supprime des fichiers lorsque la mémoire disponible sur un serveur tombe en deçà d'un pourcentage spécifique.</span><span class="sxs-lookup"><span data-stu-id="2c54e-106">Run a package that deletes files when the available memory on a server drops lower than a specified percentage.</span></span>  
  
-   <span data-ttu-id="2c54e-107">Observer l'installation d'une application, puis exécuter un package qui utilise cette application.</span><span class="sxs-lookup"><span data-stu-id="2c54e-107">Watch for installation of an application, and then run a package that uses the application.</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="2c54e-108">inclut une tâche qui lit les informations WMI.</span><span class="sxs-lookup"><span data-stu-id="2c54e-108">includes a task that reads WMI information.</span></span>  
  
 <span data-ttu-id="2c54e-109">Pour plus d'informations sur cette tâche, cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="2c54e-109">For more information about this task, click the following topic:</span></span>  
  
-   [<span data-ttu-id="2c54e-110">Tâche Lecteur de données WMI</span><span class="sxs-lookup"><span data-stu-id="2c54e-110">WMI Data Reader Task</span></span>](wmi-data-reader-task.md)  
  
## <a name="wql-queries"></a><span data-ttu-id="2c54e-111">Requêtes WQL</span><span class="sxs-lookup"><span data-stu-id="2c54e-111">WQL Queries</span></span>  
 <span data-ttu-id="2c54e-112">WQL est un dialecte de SQL avec des extensions qui permettent de prendre en charge la notification d'événement WMI et d'autres fonctionnalités spécifiques à WMI.</span><span class="sxs-lookup"><span data-stu-id="2c54e-112">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="2c54e-113">Pour plus d'informations sur WQL, consultez la documentation Windows Management Instrumentation dans [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="2c54e-113">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c54e-114">Les classes WMI varient d'une version de Windows à l'autre.</span><span class="sxs-lookup"><span data-stu-id="2c54e-114">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="2c54e-115">La requête suivante observe la notification signalant que l'utilisation du processeur est supérieure à 40 %.</span><span class="sxs-lookup"><span data-stu-id="2c54e-115">The following query watches for notification that the CPU use is more than 40 percent.</span></span>  
  
```  
SELECT * from __InstanceModificationEvent WITHIN 2 WHERE TargetInstance ISA 'Win32_Processor' and TargetInstance.LoadPercentage > 40  
```  
  
 <span data-ttu-id="2c54e-116">La requête suivante observe la notification signalant qu'un fichier a été ajouté à un dossier.</span><span class="sxs-lookup"><span data-stu-id="2c54e-116">The following query watches for notification that a file has been added to a folder.</span></span>  
  
```  
SELECT * FROM __InstanceCreationEvent WITHIN 10 WHERE TargetInstance ISA "CIM_DirectoryContainsFile" and TargetInstance.GroupComponent= "Win32_Directory.Name=\"c:\\\\WMIFileWatcher\""   
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-event-watcher-task"></a><span data-ttu-id="2c54e-117">Messages de journalisation personnalisés disponibles dans la tâche Observateur d'événement WMI</span><span class="sxs-lookup"><span data-stu-id="2c54e-117">Custom Logging Messages Available on the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="2c54e-118">Le tableau suivant répertorie les entrées de journal personnalisées de la tâche Observateur d'événement WMI.</span><span class="sxs-lookup"><span data-stu-id="2c54e-118">The following table lists the custom log entries for the WMI Event Watcher task.</span></span> <span data-ttu-id="2c54e-119">Pour plus d’informations, consultez [Journalisation d’Integration Services &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) et [Messages personnalisés pour la journalisation](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="2c54e-119">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="2c54e-120">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="2c54e-120">Log entry</span></span>|<span data-ttu-id="2c54e-121">Description</span><span class="sxs-lookup"><span data-stu-id="2c54e-121">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="2c54e-122">Indique qu'un événement surveillé par la tâche s'est produit.</span><span class="sxs-lookup"><span data-stu-id="2c54e-122">Indicates that an event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="2c54e-123">Indique que le délai de la tâche a expiré.</span><span class="sxs-lookup"><span data-stu-id="2c54e-123">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="2c54e-124">Indique que la tâche a commencé l'exécution de la requête WQL.</span><span class="sxs-lookup"><span data-stu-id="2c54e-124">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="2c54e-125">L'entrée inclut la requête.</span><span class="sxs-lookup"><span data-stu-id="2c54e-125">The entry includes the query.</span></span>|  
  
## <a name="configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="2c54e-126">Configuration de la tâche Observateur d'événement WMI</span><span class="sxs-lookup"><span data-stu-id="2c54e-126">Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="2c54e-127">Vous pouvez configurer la tâche Lecteur de données WMI de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="2c54e-127">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="2c54e-128">Spécifiez le gestionnaire de connexions WMI à utiliser.</span><span class="sxs-lookup"><span data-stu-id="2c54e-128">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="2c54e-129">Spécifiez la source de la requête WQL.</span><span class="sxs-lookup"><span data-stu-id="2c54e-129">Specify the source of the WQL query.</span></span> <span data-ttu-id="2c54e-130">Celle-ci peut être externe à la tâche, une variable ou un fichier, ou la requête peut être stockée dans une propriété de tâche.</span><span class="sxs-lookup"><span data-stu-id="2c54e-130">The source can be external to the task, a variable or a file, or the query can be stored in a task property.</span></span>  
  
-   <span data-ttu-id="2c54e-131">Spécifiez l'action exécutée par la tâche lorsque l'événement WMI se produit.</span><span class="sxs-lookup"><span data-stu-id="2c54e-131">Specify the action that the task takes when the WMI event occurs.</span></span> <span data-ttu-id="2c54e-132">Vous pouvez enregistrer la notification d'événement et l'état après l'événement ou déclencher des événements [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personnalisés qui fournissent des informations associées à l'événement WMI, à la notification et à l'état après l'événement.</span><span class="sxs-lookup"><span data-stu-id="2c54e-132">You can log the event notification and the status after the event, or raise custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] events that provide information associated with the WMI event, the notification, and the status after the event.</span></span>  
  
-   <span data-ttu-id="2c54e-133">Définissez la manière dont la tâche répond à l'événement.</span><span class="sxs-lookup"><span data-stu-id="2c54e-133">Define how the task responds to the event.</span></span> <span data-ttu-id="2c54e-134">La tâche peut être configurée de façon à réussir ou à échouer, selon l'événement, ou elle peut simplement observer encore l'événement.</span><span class="sxs-lookup"><span data-stu-id="2c54e-134">The task can be configured to succeed or fail, depending on the event, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="2c54e-135">Spécifiez l'action exécutée par la tâche lorsque le délai d'attente de requête WMI arrive à expiration. Vous pouvez enregistrer le délai d’attente et l’état après le délai d’attente ou bien déclencher un événement [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] personnalisé, indiquant que l’événement WMI a dépassé le délai d’attente, et enregistrant le délai d’attente et l’état après le délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="2c54e-135">Specify the action the task takes when the WMI query times out. You can log the time-out and the status after time-out, or raise a custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] event, indicating that the WMI event timed out and logging the time-out and time-out status.</span></span>  
  
-   <span data-ttu-id="2c54e-136">Définissez la manière dont la tâche répond au délai d'attente. La tâche peut être configurée de façon à réussir ou à échouer, ou elle peut simplement observer encore l'événement.</span><span class="sxs-lookup"><span data-stu-id="2c54e-136">Define how the task responds to the time-out. The task can be configured to succeed or fail, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="2c54e-137">Spécifiez le nombre de fois où la tâche observe l'événement.</span><span class="sxs-lookup"><span data-stu-id="2c54e-137">Specify the number of times the task watches for the event.</span></span>  
  
-   <span data-ttu-id="2c54e-138">Spécifiez le délai d'attente.</span><span class="sxs-lookup"><span data-stu-id="2c54e-138">Specify the time-out.</span></span>  
  
 <span data-ttu-id="2c54e-139">Si la source est un fichier, la tâche Observateur d'événement WMI utilise un gestionnaire de connexions de fichiers pour se connecter au fichier.</span><span class="sxs-lookup"><span data-stu-id="2c54e-139">If the source is a file, the WMI Event Watcher task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="2c54e-140">Pour plus d'informations, consultez [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2c54e-140">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="2c54e-141">La tâche Observateur d'événement WMI utilise un gestionnaire de connexions WMI pour se connecter au serveur à partir duquel elle lit les informations WMI.</span><span class="sxs-lookup"><span data-stu-id="2c54e-141">The WMI Event Watcher task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="2c54e-142">Pour plus d'informations, consultez [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2c54e-142">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
 <span data-ttu-id="2c54e-143">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="2c54e-143">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="2c54e-144">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="2c54e-144">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="2c54e-145">Éditeur de tâche Observateur d’événement WMI &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="2c54e-145">WMI Event Watcher Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="2c54e-146">Éditeur de tâche Observateur d’événement WMI &#40;page Options WMI&#41;</span><span class="sxs-lookup"><span data-stu-id="2c54e-146">WMI Event Watcher Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-event-watcher-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="2c54e-147">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="2c54e-147">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="2c54e-148">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="2c54e-148">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="2c54e-149">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="2c54e-149">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="2c54e-150">Configuration par programmation de la tâche Observateur d'événement WMI</span><span class="sxs-lookup"><span data-stu-id="2c54e-150">Programmatic Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="2c54e-151">Pour plus d'informations sur la définition par programme de ces propriétés, cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="2c54e-151">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiEventWatcherTask.WmiEventWatcherTask>  
  
  
