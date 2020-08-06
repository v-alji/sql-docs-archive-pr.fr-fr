---
title: Éditeur de tâche Observateur d’événement WMI (page Options WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatcher.wmiquery.f1
helpviewer_keywords:
- WMI Event Watcher Task Editor
ms.assetid: 525f3de7-a021-4e52-9939-3a83c88f131a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d7d95501f6442df3723261c970c7a90f48cbdc87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703080"
---
# <a name="wmi-event-watcher-task-editor-wmi-options-page"></a><span data-ttu-id="ffa46-102">Éditeur de tâche Observateur d'événement WMI (page Options WMI)</span><span class="sxs-lookup"><span data-stu-id="ffa46-102">WMI Event Watcher Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="ffa46-103">Utilisez la page **Options WMI** de la boîte de dialogue **Éditeur de tâche Observateur d'événement WMI** pour définir la source de la requête WQL (Windows Management Instrumentation Query Language) et le mode de réponse de la tâche Observateur d'événement WMI aux événements WMI (Microsoft Windows Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="ffa46-103">Use the **WMI Options** page of the **WMI Event Watcher Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and how the WMI Event Watcher task responds to Microsoft Windows Instrumentation (WMI) events.</span></span>  
  
 <span data-ttu-id="ffa46-104">Pour en savoir plus sur cette tâche, consultez [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span><span class="sxs-lookup"><span data-stu-id="ffa46-104">To learn about this task, see [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span></span> <span data-ttu-id="ffa46-105">Pour plus d’informations sur le langage de requêtes WMI (WQL), consultez la rubrique [Requêtes avec WQL](https://go.microsoft.com/fwlink/?LinkId=79045)dans la documentation Windows Management Instrumentation de la bibliothèque MSDN.</span><span class="sxs-lookup"><span data-stu-id="ffa46-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="ffa46-106">Options statiques</span><span class="sxs-lookup"><span data-stu-id="ffa46-106">Static Options</span></span>  
 <span data-ttu-id="ffa46-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="ffa46-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="ffa46-108">Sélectionnez un gestionnaire de connexions WMI dans la liste ou cliquez sur \<**New WMI Connection...**> pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="ffa46-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="ffa46-109">**Rubriques connexes :** [Gestionnaire de connexions WMI](connection-manager/wmi-connection-manager.md), [Éditeur du gestionnaire de connexions WMI](../../2014/integration-services/wmi-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="ffa46-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="ffa46-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="ffa46-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="ffa46-111">Sélectionnez le type de la source de la requête WQL que la tâche exécute.</span><span class="sxs-lookup"><span data-stu-id="ffa46-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="ffa46-112">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="ffa46-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="ffa46-113">Valeur</span><span class="sxs-lookup"><span data-stu-id="ffa46-113">Value</span></span>|<span data-ttu-id="ffa46-114">Description</span><span class="sxs-lookup"><span data-stu-id="ffa46-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ffa46-115">**Entrée directe**</span><span class="sxs-lookup"><span data-stu-id="ffa46-115">**Direct input**</span></span>|<span data-ttu-id="ffa46-116">Définit la source d'une requête WQL.</span><span class="sxs-lookup"><span data-stu-id="ffa46-116">Set the source to a WQL query.</span></span> <span data-ttu-id="ffa46-117">Cette valeur affiche l'option dynamique **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="ffa46-117">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="ffa46-118">**Connexion de fichiers**</span><span class="sxs-lookup"><span data-stu-id="ffa46-118">**File connection**</span></span>|<span data-ttu-id="ffa46-119">Sélectionnez un fichier qui contient la requête WQL.</span><span class="sxs-lookup"><span data-stu-id="ffa46-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="ffa46-120">Cette valeur affiche l'option dynamique **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="ffa46-120">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="ffa46-121">**Variable**</span><span class="sxs-lookup"><span data-stu-id="ffa46-121">**Variable**</span></span>|<span data-ttu-id="ffa46-122">Définit la source dans une variable qui définit la requête WQL.</span><span class="sxs-lookup"><span data-stu-id="ffa46-122">Set the source to a variable that defines WQL query.</span></span> <span data-ttu-id="ffa46-123">Cette valeur affiche l'option dynamique **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="ffa46-123">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
  
 <span data-ttu-id="ffa46-124">**ActionAtEvent**</span><span class="sxs-lookup"><span data-stu-id="ffa46-124">**ActionAtEvent**</span></span>  
 <span data-ttu-id="ffa46-125">Indiquez si l’événement WMI consigne l’événement et lance l’action [!INCLUDE[ssIS](../includes/ssis-md.md)] , ou consigne uniquement l’événement.</span><span class="sxs-lookup"><span data-stu-id="ffa46-125">Specify whether the WMI event logs the event and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] action, or only logs the event.</span></span>  
  
 <span data-ttu-id="ffa46-126">**AfterEvent**</span><span class="sxs-lookup"><span data-stu-id="ffa46-126">**AfterEvent**</span></span>  
 <span data-ttu-id="ffa46-127">Indiquez si la tâche aboutit ou échoue lorsqu'elle reçoit l'événement WMI, ou si elle continue d'observer l'occurrence de l'événement.</span><span class="sxs-lookup"><span data-stu-id="ffa46-127">Specify whether the task succeeds or fails after it receives the WMI event, or if the task continues watching for the event to occur again.</span></span>  
  
 <span data-ttu-id="ffa46-128">**ActionAtTimeout**</span><span class="sxs-lookup"><span data-stu-id="ffa46-128">**ActionAtTimeout**</span></span>  
 <span data-ttu-id="ffa46-129">Indiquez si la tâche consigne la temporisation d'une requête WMI et déclenche un événement [!INCLUDE[ssIS](../includes/ssis-md.md)] en réponse, ou si elle consigne uniquement la temporisation.</span><span class="sxs-lookup"><span data-stu-id="ffa46-129">Specify whether the task logs a WMI query time-out and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] event in response, or only logs the time-out.</span></span>  
  
 <span data-ttu-id="ffa46-130">**AfterTimeout**</span><span class="sxs-lookup"><span data-stu-id="ffa46-130">**AfterTimeout**</span></span>  
 <span data-ttu-id="ffa46-131">Indiquez si la tâche aboutit ou échoue en réponse à une temporisation, ou si elle continue d'observer l'occurrence d'une temporisation.</span><span class="sxs-lookup"><span data-stu-id="ffa46-131">Specify whether the task succeeds or fails in response to a time-out, or if the task continues watching for another time-out to recur.</span></span>  
  
 <span data-ttu-id="ffa46-132">**NumberOfEvents**</span><span class="sxs-lookup"><span data-stu-id="ffa46-132">**NumberOfEvents**</span></span>  
 <span data-ttu-id="ffa46-133">Indiquez le nombre d'événements à observer.</span><span class="sxs-lookup"><span data-stu-id="ffa46-133">Specify the number of events to watch for.</span></span>  
  
 <span data-ttu-id="ffa46-134">**Délai d'expiration**</span><span class="sxs-lookup"><span data-stu-id="ffa46-134">**Timeout**</span></span>  
 <span data-ttu-id="ffa46-135">Indiquez le délai en secondes avant l'occurrence de l'événement.</span><span class="sxs-lookup"><span data-stu-id="ffa46-135">Specify the number of seconds to wait for the event to occur.</span></span> <span data-ttu-id="ffa46-136">La valeur 0 indique qu'aucun délai n'a lieu.</span><span class="sxs-lookup"><span data-stu-id="ffa46-136">A value of 0 means that no time-out is in effect.</span></span>  
  
## <a name="wqlquerysource-dynamic-options"></a><span data-ttu-id="ffa46-137">Options dynamiques WQLQuerySource</span><span class="sxs-lookup"><span data-stu-id="ffa46-137">WQLQuerySource Dynamic Options</span></span>  
  
### <a name="wqlquerysource--direct-input"></a><span data-ttu-id="ffa46-138">WQLQuerySource = Entrée directe</span><span class="sxs-lookup"><span data-stu-id="ffa46-138">WQLQuerySource = Direct input</span></span>  
 <span data-ttu-id="ffa46-139">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="ffa46-139">**WQLQuerySource**</span></span>  
 <span data-ttu-id="ffa46-140">Fournissez une requête ou cliquez sur les points de suspension (...) et entrez une requête en utilisant la boîte de dialogue **Requête WQL**.</span><span class="sxs-lookup"><span data-stu-id="ffa46-140">Provide a query, or click the ellipsis button (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysource--file-connection"></a><span data-ttu-id="ffa46-141">WQLQuerySource = Connexion de fichiers</span><span class="sxs-lookup"><span data-stu-id="ffa46-141">WQLQuerySource = File connection</span></span>  
 <span data-ttu-id="ffa46-142">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="ffa46-142">**WQLQuerySource**</span></span>  
 <span data-ttu-id="ffa46-143">Sélectionnez un gestionnaire de connexions de fichiers dans la liste ou cliquez sur \<**New connection...**> pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="ffa46-143">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="ffa46-144">**Rubriques connexes :** [Gestionnaire de connexions de fichiers](connection-manager/file-connection-manager.md), [Éditeur du gestionnaire de connexions de fichiers](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="ffa46-144">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysource--variable"></a><span data-ttu-id="ffa46-145">WQLQuerySource = Variable</span><span class="sxs-lookup"><span data-stu-id="ffa46-145">WQLQuerySource = Variable</span></span>  
 <span data-ttu-id="ffa46-146">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="ffa46-146">**WQLQuerySource**</span></span>  
 <span data-ttu-id="ffa46-147">Sélectionnez une variable dans la liste, ou cliquez sur \<**New variable...**> pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="ffa46-147">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="ffa46-148">**Rubriques connexes :** [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Ajouter une variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="ffa46-148">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa46-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ffa46-149">See Also</span></span>  
 <span data-ttu-id="ffa46-150">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ffa46-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ffa46-151">[Éditeur de tâche Observateur d’événement WMI &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="ffa46-151">[WMI Event Watcher Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="ffa46-152">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="ffa46-152">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="ffa46-153">Tâche Lecteur de données WMI</span><span class="sxs-lookup"><span data-stu-id="ffa46-153">WMI Data Reader Task</span></span>](control-flow/wmi-data-reader-task.md)  
  
  
