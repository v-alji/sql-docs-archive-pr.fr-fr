---
title: Éditeur de tâche lecteur de données WMI (page Options WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.wmiquery.f1
helpviewer_keywords:
- WMI Data Reader Task Editor
ms.assetid: 4b8d4716-882d-41b0-b77e-e0e2741a2cd5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfb28e7f8f352f708085bf664757391a05869752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613506"
---
# <a name="wmi-data-reader-task-editor-wmi-options-page"></a><span data-ttu-id="866e6-102">Éditeur de tâche Lecteur de données WMI (page Options WMI)</span><span class="sxs-lookup"><span data-stu-id="866e6-102">WMI Data Reader Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="866e6-103">Utilisez la page **Options WMI** de la boîte de dialogue **Éditeur de tâche Lecteur de données WMI** pour définir la source de la requête WQL (Windows Management Instrumentation Query Language) et la destination du résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="866e6-103">Use the **WMI Options** page of the **WMI Data Reader Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and the destination of the query result.</span></span>  
  
 <span data-ttu-id="866e6-104">Pour en savoir plus sur cette tâche, consultez [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span><span class="sxs-lookup"><span data-stu-id="866e6-104">To learn about this task, see [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span></span> <span data-ttu-id="866e6-105">Pour plus d’informations sur le langage de requêtes WMI (WQL), consultez la rubrique [Requêtes avec WQL](https://go.microsoft.com/fwlink/?LinkId=79045)dans la documentation Windows Management Instrumentation de la bibliothèque MSDN.</span><span class="sxs-lookup"><span data-stu-id="866e6-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="866e6-106">Options statiques</span><span class="sxs-lookup"><span data-stu-id="866e6-106">Static Options</span></span>  
 <span data-ttu-id="866e6-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="866e6-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="866e6-108">Sélectionnez un gestionnaire de connexions WMI dans la liste ou cliquez sur \<**New WMI Connection...**> pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="866e6-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="866e6-109">**Rubriques connexes :** [Gestionnaire de connexions WMI](connection-manager/wmi-connection-manager.md), [Éditeur du gestionnaire de connexions WMI](../../2014/integration-services/wmi-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="866e6-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="866e6-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="866e6-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="866e6-111">Sélectionnez le type de la source de la requête WQL que la tâche exécute.</span><span class="sxs-lookup"><span data-stu-id="866e6-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="866e6-112">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="866e6-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="866e6-113">Valeur</span><span class="sxs-lookup"><span data-stu-id="866e6-113">Value</span></span>|<span data-ttu-id="866e6-114">Description</span><span class="sxs-lookup"><span data-stu-id="866e6-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="866e6-115">**Entrée directe**</span><span class="sxs-lookup"><span data-stu-id="866e6-115">**Direct input**</span></span>|<span data-ttu-id="866e6-116">Définit la source d'une requête WQL.</span><span class="sxs-lookup"><span data-stu-id="866e6-116">Set the source to a WQL query.</span></span> <span data-ttu-id="866e6-117">Si vous sélectionnez cette valeur, l'option dynamique **WQLQuerySourceType**s'affiche.</span><span class="sxs-lookup"><span data-stu-id="866e6-117">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="866e6-118">**Connexion de fichiers**</span><span class="sxs-lookup"><span data-stu-id="866e6-118">**File connection**</span></span>|<span data-ttu-id="866e6-119">Sélectionnez un fichier qui contient la requête WQL.</span><span class="sxs-lookup"><span data-stu-id="866e6-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="866e6-120">Si vous sélectionnez cette valeur, l'option dynamique **WQLQuerySourceType**s'affiche.</span><span class="sxs-lookup"><span data-stu-id="866e6-120">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="866e6-121">**Variable**</span><span class="sxs-lookup"><span data-stu-id="866e6-121">**Variable**</span></span>|<span data-ttu-id="866e6-122">Définissez la source dans une variable qui définit la requête WQL.</span><span class="sxs-lookup"><span data-stu-id="866e6-122">Set the source to a variable that defines the WQL query.</span></span> <span data-ttu-id="866e6-123">Si vous sélectionnez cette valeur, l'option dynamique **WQLQuerySourceType**s'affiche.</span><span class="sxs-lookup"><span data-stu-id="866e6-123">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
  
 <span data-ttu-id="866e6-124">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="866e6-124">**OutputType**</span></span>  
 <span data-ttu-id="866e6-125">Indiquez si la sortie doit être une table de données, une valeur de propriété ou un nom et une valeur de propriété.</span><span class="sxs-lookup"><span data-stu-id="866e6-125">Specify whether the output should be a data table, property value, or property name and value.</span></span>  
  
 <span data-ttu-id="866e6-126">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="866e6-126">**OverwriteDestination**</span></span>  
 <span data-ttu-id="866e6-127">Indique s'il faut conserver ou remplacer les données d'origine dans le fichier ou la variable de destination, ou leur ajouter des données.</span><span class="sxs-lookup"><span data-stu-id="866e6-127">Specifies whether to keep, overwrite, or append to the original data in the destination file or variable.</span></span>  
  
 <span data-ttu-id="866e6-128">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="866e6-128">**DestinationType**</span></span>  
 <span data-ttu-id="866e6-129">Sélectionnez le type de la destination de la requête WQL que la tâche exécute.</span><span class="sxs-lookup"><span data-stu-id="866e6-129">Select the destination type of the WQL query that the task runs.</span></span> <span data-ttu-id="866e6-130">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="866e6-130">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="866e6-131">Valeur</span><span class="sxs-lookup"><span data-stu-id="866e6-131">Value</span></span>|<span data-ttu-id="866e6-132">Description</span><span class="sxs-lookup"><span data-stu-id="866e6-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="866e6-133">**Connexion de fichiers**</span><span class="sxs-lookup"><span data-stu-id="866e6-133">**File connection**</span></span>|<span data-ttu-id="866e6-134">Sélectionnez un fichier pour y enregistrer le résultat de la requête WQL.</span><span class="sxs-lookup"><span data-stu-id="866e6-134">Select a file to save the results of the WQL query in.</span></span> <span data-ttu-id="866e6-135">Cette valeur affiche l'option dynamique **DestinationType**.</span><span class="sxs-lookup"><span data-stu-id="866e6-135">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
|<span data-ttu-id="866e6-136">**Variable**</span><span class="sxs-lookup"><span data-stu-id="866e6-136">**Variable**</span></span>|<span data-ttu-id="866e6-137">Définissez la variable de stockage du résultat de la requête WQL.</span><span class="sxs-lookup"><span data-stu-id="866e6-137">Set the variable to store the results of the WQL query in.</span></span> <span data-ttu-id="866e6-138">Cette valeur affiche l'option dynamique **DestinationType**.</span><span class="sxs-lookup"><span data-stu-id="866e6-138">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
  
## <a name="wqlquerysourcetype-dynamic-options"></a><span data-ttu-id="866e6-139">Options dynamiques WQLQuerySourceType</span><span class="sxs-lookup"><span data-stu-id="866e6-139">WQLQuerySourceType Dynamic Options</span></span>  
  
### <a name="wqlquerysourcetype--direct-input"></a><span data-ttu-id="866e6-140">WQLQuerySourceType = Entrée directe</span><span class="sxs-lookup"><span data-stu-id="866e6-140">WQLQuerySourceType = Direct input</span></span>  
 <span data-ttu-id="866e6-141">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="866e6-141">**WQLQuerySource**</span></span>  
 <span data-ttu-id="866e6-142">Fournissez une requête ou cliquez sur le bouton de sélection (...) et entrez une requête en utilisant la boîte de dialogue **Requête WQL**.</span><span class="sxs-lookup"><span data-stu-id="866e6-142">Provide a query, or click the ellipsis (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysourcetype--file-connection"></a><span data-ttu-id="866e6-143">WQLQuerySourceType = Connexion de fichiers</span><span class="sxs-lookup"><span data-stu-id="866e6-143">WQLQuerySourceType = File connection</span></span>  
 <span data-ttu-id="866e6-144">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="866e6-144">**WQLQuerySource**</span></span>  
 <span data-ttu-id="866e6-145">Sélectionnez un gestionnaire de connexions de fichiers dans la liste ou cliquez sur \<**New connection...**> pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="866e6-145">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="866e6-146">**Rubriques connexes :** [Gestionnaire de connexions de fichiers](connection-manager/file-connection-manager.md), [Éditeur du gestionnaire de connexions de fichiers](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="866e6-146">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysourcetype--variable"></a><span data-ttu-id="866e6-147">WQLQuerySourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="866e6-147">WQLQuerySourceType = Variable</span></span>  
 <span data-ttu-id="866e6-148">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="866e6-148">**WQLQuerySource**</span></span>  
 <span data-ttu-id="866e6-149">Sélectionnez une variable dans la liste, ou cliquez sur \<**New variable...**> pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="866e6-149">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="866e6-150">**Rubriques connexes :** [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Ajouter une variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="866e6-150">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="destinationtype-dynamic-options"></a><span data-ttu-id="866e6-151">Options dynamiques DestinationType</span><span class="sxs-lookup"><span data-stu-id="866e6-151">DestinationType Dynamic Options</span></span>  
  
### <a name="destinationtype--file-connection"></a><span data-ttu-id="866e6-152">DestinationType = Connexion de fichiers</span><span class="sxs-lookup"><span data-stu-id="866e6-152">DestinationType = File connection</span></span>  
 <span data-ttu-id="866e6-153">**Destination**</span><span class="sxs-lookup"><span data-stu-id="866e6-153">**Destination**</span></span>  
 <span data-ttu-id="866e6-154">Sélectionnez un gestionnaire de connexions de fichiers dans la liste ou cliquez sur \<**New connection...**> pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="866e6-154">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="866e6-155">**Rubriques connexes :** [Gestionnaire de connexions de fichiers](connection-manager/file-connection-manager.md), [Éditeur du gestionnaire de connexions de fichiers](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="866e6-155">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="destinationtype--variable"></a><span data-ttu-id="866e6-156">DestinationType = Variable</span><span class="sxs-lookup"><span data-stu-id="866e6-156">DestinationType = Variable</span></span>  
 <span data-ttu-id="866e6-157">**Destination**</span><span class="sxs-lookup"><span data-stu-id="866e6-157">**Destination**</span></span>  
 <span data-ttu-id="866e6-158">Sélectionnez une variable dans la liste, ou cliquez sur \<**New variable...**> pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="866e6-158">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="866e6-159">**Rubriques connexes :** [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Ajouter une variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="866e6-159">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="866e6-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="866e6-160">See Also</span></span>  
 <span data-ttu-id="866e6-161">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="866e6-161">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="866e6-162">[Éditeur de tâche lecteur de données WMI &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="866e6-162">[WMI Data Reader Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="866e6-163">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="866e6-163">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="866e6-164">Tâche Observateur d’événement WMI</span><span class="sxs-lookup"><span data-stu-id="866e6-164">WMI Event Watcher Task</span></span>](control-flow/wmi-event-watcher-task.md)  
  
  
