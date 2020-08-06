---
title: Lecteur de données WMI, tâche | Documents Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Data Reader task [Integration Services]
ms.assetid: dae57067-0275-4ac3-8f34-1b9d169f1112
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1d2f16a28e8b6c94c7275468dedb6d2dfec76d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602245"
---
# <a name="wmi-data-reader-task"></a><span data-ttu-id="8835c-102">Tâche Lecteur de données WMI</span><span class="sxs-lookup"><span data-stu-id="8835c-102">WMI Data Reader Task</span></span>
  <span data-ttu-id="8835c-103">La tâche Lecteur de données WMI exécute des requêtes au moyen du langage de requête WMI (Windows Management Instrumentation) qui retournent des informations à partir de WMI sur un système informatique.</span><span class="sxs-lookup"><span data-stu-id="8835c-103">The WMI Data Reader task runs queries using the Windows Management Instrumentation (WMI) Query Language that returns information from WMI about a computer system.</span></span> <span data-ttu-id="8835c-104">Vous pouvez utiliser la tâche Lecteur de données WMI pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="8835c-104">You can use the WMI Data Reader task for the following purposes:</span></span>  
  
-   <span data-ttu-id="8835c-105">Interrogation des journaux des événements Windows sur un ordinateur local ou distant et écriture des informations dans un fichier ou une variable.</span><span class="sxs-lookup"><span data-stu-id="8835c-105">Query the Windows event logs on a local or remote computer and write the information to a file or variable.</span></span>  
  
-   <span data-ttu-id="8835c-106">Obtention d'informations sur la présence, l'état ou les propriétés de composants matériels, puis utilisation de ces informations pour déterminer si d'autres tâches du flux de contrôle doivent être exécutées.</span><span class="sxs-lookup"><span data-stu-id="8835c-106">Obtain information about the presence, state, or properties of hardware components, and then use this information to determine whether other tasks in the control flow should run.</span></span>  
  
-   <span data-ttu-id="8835c-107">Obtention d'une liste d'applications et détermination de la version de chaque application installée.</span><span class="sxs-lookup"><span data-stu-id="8835c-107">Get a list of applications and determine what version of each application is installed.</span></span>  
  
 <span data-ttu-id="8835c-108">Vous pouvez configurer la tâche Lecteur de données WMI de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="8835c-108">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="8835c-109">Spécifiez le gestionnaire de connexions WMI à utiliser.</span><span class="sxs-lookup"><span data-stu-id="8835c-109">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="8835c-110">Spécifiez la source de la requête WQL.</span><span class="sxs-lookup"><span data-stu-id="8835c-110">Specify the source of the WQL query.</span></span> <span data-ttu-id="8835c-111">La requête peut être stockée dans une propriété de tâche ou en dehors de la tâche, dans une variable ou un fichier.</span><span class="sxs-lookup"><span data-stu-id="8835c-111">The query can be stored in a task property, or the query can be stored outside the task, in a variable or a file.</span></span>  
  
-   <span data-ttu-id="8835c-112">Définissez le format des résultats de requêtes WQL.</span><span class="sxs-lookup"><span data-stu-id="8835c-112">Define the format of the WQL query results.</span></span> <span data-ttu-id="8835c-113">La tâche prend en charge un format de table, de paire nom/valeur de propriété ou de valeur de propriété.</span><span class="sxs-lookup"><span data-stu-id="8835c-113">The task supports a table, property name/value pair, or property value format.</span></span>  
  
-   <span data-ttu-id="8835c-114">Spécifiez la destination de la requête.</span><span class="sxs-lookup"><span data-stu-id="8835c-114">Specify the destination of the query.</span></span> <span data-ttu-id="8835c-115">La destination peut être une variable ou un fichier.</span><span class="sxs-lookup"><span data-stu-id="8835c-115">The destination can be a variable or a file.</span></span>  
  
-   <span data-ttu-id="8835c-116">Indiquez si les résultats sont ajoutés à la destination de la requête ou si celle-ci est remplacée ou conservée.</span><span class="sxs-lookup"><span data-stu-id="8835c-116">Indicate whether the query destination is overwritten, kept, or appended.</span></span>  
  
 <span data-ttu-id="8835c-117">Si la source ou la destination est un fichier, la tâche Lecteur de données WMI utilise un gestionnaire de connexions de fichiers pour se connecter au fichier.</span><span class="sxs-lookup"><span data-stu-id="8835c-117">If the source or destination is a file, the WMI Data Reader task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="8835c-118">Pour plus d'informations, consultez [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8835c-118">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="8835c-119">La tâche Lecteur de données WMI utilise un gestionnaire de connexions WMI pour se connecter au serveur à partir duquel elle lit les informations WMI.</span><span class="sxs-lookup"><span data-stu-id="8835c-119">The WMI Data Reader task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="8835c-120">Pour plus d'informations, consultez [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8835c-120">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="wql-query"></a><span data-ttu-id="8835c-121">Requête WQL</span><span class="sxs-lookup"><span data-stu-id="8835c-121">WQL Query</span></span>  
 <span data-ttu-id="8835c-122">WQL est un dialecte de SQL avec des extensions qui permettent de prendre en charge la notification d'événement WMI et d'autres fonctionnalités spécifiques à WMI.</span><span class="sxs-lookup"><span data-stu-id="8835c-122">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="8835c-123">Pour plus d'informations sur WQL, consultez la documentation Windows Management Instrumentation dans [MSDN Library](https://go.microsoft.com/fwlink/?linkid=7022).</span><span class="sxs-lookup"><span data-stu-id="8835c-123">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=7022).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8835c-124">Les classes WMI varient d'une version de Windows à l'autre.</span><span class="sxs-lookup"><span data-stu-id="8835c-124">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="8835c-125">La requête WQL suivante retourne des entrées dans le journal des événements d'application.</span><span class="sxs-lookup"><span data-stu-id="8835c-125">The following WQL query returns entries in the Application log event.</span></span>  
  
```  
SELECT * FROM Win32_NTLogEvent WHERE LogFile = 'Application' AND (SourceName='SQLISService' OR SourceName='SQLISPackage') AND TimeGenerated > '20050117'  
```  
  
 <span data-ttu-id="8835c-126">La requête WQL suivante retourne des informations sur les disques logiques.</span><span class="sxs-lookup"><span data-stu-id="8835c-126">The following WQL query returns logical disk information.</span></span>  
  
```  
SELECT FreeSpace, DeviceId, Size, SystemName, Description FROM Win32_LlogicalDisk  
```  
  
 <span data-ttu-id="8835c-127">La requête WQL suivante retourne une liste des mises à jour QFE (Quick Fix Engineering) du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="8835c-127">The following WQL query returns a list of the quick fix engineering (QFE) updates to the operating system.</span></span>  
  
```  
Select * FROM Win32_QuickFixEngineering  
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-data-reader-task"></a><span data-ttu-id="8835c-128">Messages de journalisation personnalisés disponibles dans la tâche Lecteur de données WMI</span><span class="sxs-lookup"><span data-stu-id="8835c-128">Custom Logging Messages Available on the WMI Data Reader Task</span></span>  
 <span data-ttu-id="8835c-129">Le tableau suivant répertorie les entrées de journal personnalisées de la tâche Lecteur de données WMI.</span><span class="sxs-lookup"><span data-stu-id="8835c-129">The following table lists the custom log entries for the WMI Data Reader task.</span></span> <span data-ttu-id="8835c-130">Pour plus d’informations, consultez [Journalisation d’Integration Services &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) et [Messages personnalisés pour la journalisation](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="8835c-130">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="8835c-131">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="8835c-131">Log entry</span></span>|<span data-ttu-id="8835c-132">Description</span><span class="sxs-lookup"><span data-stu-id="8835c-132">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="8835c-133">Indique que la tâche a commencé la lecture des données WMI.</span><span class="sxs-lookup"><span data-stu-id="8835c-133">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="8835c-134">Indique la requête WQL que la tâche a exécutée.</span><span class="sxs-lookup"><span data-stu-id="8835c-134">Reports the WQL query that the task ran.</span></span>|  
  
## <a name="configuration-of-the-wmi-data-reader-task"></a><span data-ttu-id="8835c-135">Configuration de la tâche Lecteur de données WMI</span><span class="sxs-lookup"><span data-stu-id="8835c-135">Configuration of the WMI Data Reader Task</span></span>  
 <span data-ttu-id="8835c-136">Vous pouvez définir les propriétés par programmation ou par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8835c-136">You can set properties programmatically or through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="8835c-137">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8835c-137">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8835c-138">Éditeur de tâche Lecteur de données WMI &#40;page Options WMI&#41;</span><span class="sxs-lookup"><span data-stu-id="8835c-138">WMI Data Reader Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-data-reader-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="8835c-139">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="8835c-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="8835c-140">Pour plus d'informations sur la définition par programmation de ces propriétés, cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="8835c-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiDataReaderTask.WmiDataReaderTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="8835c-141">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="8835c-141">Related Tasks</span></span>  
 <span data-ttu-id="8835c-142">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="8835c-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="8835c-143">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="8835c-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="8835c-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8835c-144">See Also</span></span>  
 <span data-ttu-id="8835c-145">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="8835c-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="8835c-146">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="8835c-146">Control Flow</span></span>](control-flow.md)  
  
  
