---
title: Éditeur de tâche d’exécution de package | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executepackagetask.parameter.F1
- sql12.dts.designer.executepackagetask.package.f1
- sql12.dts.designer.executepackagetask.general.f1
ms.assetid: c2c96b4f-eb10-4d8b-be34-88edfd0785fb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b9b2e18516e1f5c1b7af56bd1e84ef875557fd49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610748"
---
# <a name="execute-package-task-editor"></a><span data-ttu-id="59f5c-102">Éditeur de tâche d'exécution de package</span><span class="sxs-lookup"><span data-stu-id="59f5c-102">Execute Package Task Editor</span></span>
  <span data-ttu-id="59f5c-103">Utilisez l'Éditeur de tâche d'exécution de package pour configurer la tâche d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="59f5c-103">Use the Execute Package Task Editor to configure the Execute Package Task.</span></span> <span data-ttu-id="59f5c-104">La tâche d'exécution de package étend les fonctionnalités d'entreprise de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en permettant à des packages d'exécuter d'autres packages au sein d'un flux de travail.</span><span class="sxs-lookup"><span data-stu-id="59f5c-104">The Execute Package task extends the enterprise capabilities of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by letting packages run other packages as part of a workflow.</span></span>  
  
 <span data-ttu-id="59f5c-105">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="59f5c-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="59f5c-106">Ouvrir l'Éditeur de tâche d'exécution de package</span><span class="sxs-lookup"><span data-stu-id="59f5c-106">Open the Execute Package Task Editor</span></span>](#open)  
  
-   [<span data-ttu-id="59f5c-107">Définir les options sur la page Général</span><span class="sxs-lookup"><span data-stu-id="59f5c-107">Set the Options on the General Page</span></span>](#general)  
  
-   [<span data-ttu-id="59f5c-108">Définir les options sur la page Package</span><span class="sxs-lookup"><span data-stu-id="59f5c-108">Set the Options on the Package Page</span></span>](#package)  
  
-   [<span data-ttu-id="59f5c-109">Définir les options sur la page Liaisons de paramètre</span><span class="sxs-lookup"><span data-stu-id="59f5c-109">Set the Options on the Parameter Bindings Page</span></span>](#parameter)  
  
##  <a name="open-the-execute-package-task-editor"></a><a name="open"></a> <span data-ttu-id="59f5c-110">Ouvrir l'Éditeur de tâche d'exécution de package</span><span class="sxs-lookup"><span data-stu-id="59f5c-110">Open the Execute Package Task Editor</span></span>  
  
1.  <span data-ttu-id="59f5c-111">Ouvrez un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] qui contient une tâche d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="59f5c-111">Open an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] that contains an Execute Package task.</span></span>  
  
2.  <span data-ttu-id="59f5c-112">Cliquez avec le bouton droit sur la tâche dans le Concepteur SSIS, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="59f5c-112">Right-click the task in the SSIS Designer, and then click **Edit**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="59f5c-113">Définir les options sur la page Général</span><span class="sxs-lookup"><span data-stu-id="59f5c-113">Set the Options on the General Page</span></span>  
 <span data-ttu-id="59f5c-114">**Nom**</span><span class="sxs-lookup"><span data-stu-id="59f5c-114">**Name**</span></span>  
 <span data-ttu-id="59f5c-115">Fournissez un nom unique pour la tâche d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="59f5c-115">Provide a unique name for the Execute Package task.</span></span> <span data-ttu-id="59f5c-116">Ce nom sert d'étiquette à l'icône de la tâche.</span><span class="sxs-lookup"><span data-stu-id="59f5c-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59f5c-117">Les noms de tâche doivent être uniques dans un package.</span><span class="sxs-lookup"><span data-stu-id="59f5c-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="59f5c-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="59f5c-118">**Description**</span></span>  
 <span data-ttu-id="59f5c-119">Entrez une description de la tâche d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="59f5c-119">Type a description of the Execute Package task.</span></span>  
  
##  <a name="set-the-options-on-the-package-page"></a><a name="package"></a> <span data-ttu-id="59f5c-120">Définir les options sur la page Package</span><span class="sxs-lookup"><span data-stu-id="59f5c-120">Set the Options on the Package Page</span></span>  
 <span data-ttu-id="59f5c-121">**ReferenceType**</span><span class="sxs-lookup"><span data-stu-id="59f5c-121">**ReferenceType**</span></span>  
 <span data-ttu-id="59f5c-122">Sélectionnez **Référence du projet** pour les packages enfants qui sont dans le projet.</span><span class="sxs-lookup"><span data-stu-id="59f5c-122">Select **Project Reference** for child packages that are in the project.</span></span> <span data-ttu-id="59f5c-123">Sélectionnez **Référence externe** pour les packages enfants situés en dehors du package.</span><span class="sxs-lookup"><span data-stu-id="59f5c-123">Select **External Reference** for child packages that are located outside the package</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59f5c-124">L’option **ReferenceType** est en lecture seule et est définie sur **Référence externe** si le projet qui contient le package n’a pas été converti en modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="59f5c-124">The **ReferenceType** option is ready-only and set to **External Reference** if the project that contains the package has not been converted to the project deployment model.</span></span> <span data-ttu-id="59f5c-125">Pour plus d’informations sur la conversion, consultez [Déployer des projets sur le serveur Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="59f5c-125">For more information about conversion, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="59f5c-126">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="59f5c-126">**Password**</span></span>  
 <span data-ttu-id="59f5c-127">Si le package enfant s’avère protégé par un mot de passe, indiquez ce dernier ou cliquez sur le bouton représentant des points de suspension (...) afin de définir un nouveau mot de passe.</span><span class="sxs-lookup"><span data-stu-id="59f5c-127">If the child package is password protected, provide the password for the child package, or click the ellipsis button (...) and create a new password for the child package.</span></span>  
  
 `ExecuteOutOfProcess`  
 <span data-ttu-id="59f5c-128">Spécifiez si le package enfant s'exécute dans le processus du package parent ou dans un processus distinct.</span><span class="sxs-lookup"><span data-stu-id="59f5c-128">Specify whether the child package runs in the process of the parent package or in a separate process.</span></span> <span data-ttu-id="59f5c-129">Par défaut, la propriété ExecuteOutOfProcess a de la tâche d’exécution de package a la valeur `False` , et le package enfant s’exécute dans le même processus que le package parent.</span><span class="sxs-lookup"><span data-stu-id="59f5c-129">By default, the ExecuteOutOfProcess property of the Execute Package task is set to `False`, and the child package runs in the same process as the parent package.</span></span> <span data-ttu-id="59f5c-130">Si vous affectez la valeur `true` à cette propriété, le package enfant s'exécute dans un processus indépendant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-130">If you set this property to `true`, the child package runs in a separate process.</span></span> <span data-ttu-id="59f5c-131">Cela peut ralentir le lancement du package enfant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-131">This may slow down the launching of the child package.</span></span> <span data-ttu-id="59f5c-132">En outre, si vous avez défini la propriété sur `true`, vous ne pouvez pas déboguer le package dans une installation d'outils uniquement ; vous devez installer le produit [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59f5c-132">In addition, if set the property to `true`, you cannot debug the package in a tools-only install; you must install the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] product.</span></span> <span data-ttu-id="59f5c-133">Pour plus d’informations, consultez [Installer Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="59f5c-133">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
### <a name="referencetype-dynamic-options"></a><span data-ttu-id="59f5c-134">Options dynamiques de ReferenceType</span><span class="sxs-lookup"><span data-stu-id="59f5c-134">ReferenceType Dynamic Options</span></span>  
  
#### <a name="referencetype--external-reference"></a><span data-ttu-id="59f5c-135">ReferenceType = Référence externe</span><span class="sxs-lookup"><span data-stu-id="59f5c-135">ReferenceType = External Reference</span></span>  
 <span data-ttu-id="59f5c-136">**Lieu**</span><span class="sxs-lookup"><span data-stu-id="59f5c-136">**Location**</span></span>  
 <span data-ttu-id="59f5c-137">Sélectionnez l'emplacement du package enfant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-137">Select the location of the child package.</span></span> <span data-ttu-id="59f5c-138">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-138">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="59f5c-139">Valeur</span><span class="sxs-lookup"><span data-stu-id="59f5c-139">Value</span></span>|<span data-ttu-id="59f5c-140">Description</span><span class="sxs-lookup"><span data-stu-id="59f5c-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="59f5c-141">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="59f5c-141">**SQL Server**</span></span>|<span data-ttu-id="59f5c-142">Définissez l'emplacement d'une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59f5c-142">Set the location to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="59f5c-143">**Système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="59f5c-143">**File system**</span></span>|<span data-ttu-id="59f5c-144">Permet de définir l'emplacement du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="59f5c-144">Set the location to the file system.</span></span>|  
  
 <span data-ttu-id="59f5c-145">**Connection**</span><span class="sxs-lookup"><span data-stu-id="59f5c-145">**Connection**</span></span>  
 <span data-ttu-id="59f5c-146">Sélectionnez le type d’emplacement de stockage du package enfant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-146">Select the type of storage location for the child package.</span></span>  
  
 <span data-ttu-id="59f5c-147">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="59f5c-147">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="59f5c-148">Permet d'afficher le nom du package.</span><span class="sxs-lookup"><span data-stu-id="59f5c-148">Displays the package name.</span></span>  
  
#### <a name="referencetype--project-reference"></a><span data-ttu-id="59f5c-149">ReferenceType = Référence du projet</span><span class="sxs-lookup"><span data-stu-id="59f5c-149">ReferenceType = Project Reference</span></span>  
 <span data-ttu-id="59f5c-150">**PackageNameFromProjectReference**</span><span class="sxs-lookup"><span data-stu-id="59f5c-150">**PackageNameFromProjectReference**</span></span>  
 <span data-ttu-id="59f5c-151">Sélectionnez un package contenu dans le projet, qui sera le package enfant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-151">Select a package contained in the project, to be the child package.</span></span>  
  
### <a name="location-dynamic-options"></a><span data-ttu-id="59f5c-152">Options dynamiques pour la définition de l'emplacement</span><span class="sxs-lookup"><span data-stu-id="59f5c-152">Location Dynamic Options</span></span>  
  
#### <a name="location--sql-server"></a><span data-ttu-id="59f5c-153">Emplacement = SQL Server</span><span class="sxs-lookup"><span data-stu-id="59f5c-153">Location = SQL Server</span></span>  
 <span data-ttu-id="59f5c-154">**Connection**</span><span class="sxs-lookup"><span data-stu-id="59f5c-154">**Connection**</span></span>  
 <span data-ttu-id="59f5c-155">Sélectionnez un gestionnaire de connexions OLE DB existant dans la liste ou cliquez sur \<**New connection...**> pour en créer un.</span><span class="sxs-lookup"><span data-stu-id="59f5c-155">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="59f5c-156">**Rubriques connexes :** [Gestionnaire de connexions OLE DB](connection-manager/ole-db-connection-manager.md), [Configurer le gestionnaire de connexions OLE DB](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="59f5c-156">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="59f5c-157">**PackageName**</span><span class="sxs-lookup"><span data-stu-id="59f5c-157">**PackageName**</span></span>  
 <span data-ttu-id="59f5c-158">Permet d’entrer le nom du package enfant ou de cliquer sur le bouton représenté par des points de suspension (...) pour atteindre le package.</span><span class="sxs-lookup"><span data-stu-id="59f5c-158">Type the name of the child package, or click the ellipsis (...) and then locate the package.</span></span>  
  
#### <a name="location--file-system"></a><span data-ttu-id="59f5c-159">Emplacement = Système de fichiers</span><span class="sxs-lookup"><span data-stu-id="59f5c-159">Location = File system</span></span>  
 <span data-ttu-id="59f5c-160">**Connection**</span><span class="sxs-lookup"><span data-stu-id="59f5c-160">**Connection**</span></span>  
 <span data-ttu-id="59f5c-161">Sélectionnez un gestionnaire de connexions de fichiers dans la liste ou cliquez sur \<**New connection...**> pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="59f5c-161">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="59f5c-162">**Rubriques connexes :** [Gestionnaire de connexions de fichiers](connection-manager/file-connection-manager.md), [Éditeur du gestionnaire de connexions de fichiers](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="59f5c-162">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="59f5c-163">**PackageNameReadOnly**</span><span class="sxs-lookup"><span data-stu-id="59f5c-163">**PackageNameReadOnly**</span></span>  
 <span data-ttu-id="59f5c-164">Permet d'afficher le nom du package.</span><span class="sxs-lookup"><span data-stu-id="59f5c-164">Displays the package name.</span></span>  
  
##  <a name="set-the-options-on-the-parameter-bindings-page"></a><a name="parameter"></a> <span data-ttu-id="59f5c-165">Définir les options sur la page Liaisons de paramètre</span><span class="sxs-lookup"><span data-stu-id="59f5c-165">Set the Options on the Parameter Bindings Page</span></span>  
 <span data-ttu-id="59f5c-166">Vous pouvez passer des valeurs du package parent ou du projet au package enfant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-166">You can pass values from the parent package or the project, to the child package.</span></span> <span data-ttu-id="59f5c-167">Le projet doit utiliser le modèle de déploiement de projet et le package enfant doit être contenu dans le même projet qui contient le package parent.</span><span class="sxs-lookup"><span data-stu-id="59f5c-167">The project must use the project deployment model and the child package must be contained in the same project that contains the parent package.</span></span>  
  
 <span data-ttu-id="59f5c-168">Pour plus d’informations sur la conversion de projets en modèle de déploiement de projet, consultez [Déployer des projets sur le serveur Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="59f5c-168">For information about converting projects to the project deployment model, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="59f5c-169">**Paramètre de package enfant**</span><span class="sxs-lookup"><span data-stu-id="59f5c-169">**Child package parameter**</span></span>  
 <span data-ttu-id="59f5c-170">Entrez ou sélectionnez un nom pour le paramètre de package enfant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-170">Enter or select a name for the child package parameter.</span></span>  
  
 <span data-ttu-id="59f5c-171">**Variable ou paramètre de liaison**</span><span class="sxs-lookup"><span data-stu-id="59f5c-171">**Binding parameter or variable**</span></span>  
 <span data-ttu-id="59f5c-172">Sélectionnez le paramètre ou la variable contenant la valeur que vous souhaitez transmettre au package enfant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-172">Select the parameter or variable that contains the value that you want to pass to the child package.</span></span>  
  
 <span data-ttu-id="59f5c-173">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="59f5c-173">**Add**</span></span>  
 <span data-ttu-id="59f5c-174">Cliquez pour mapper un paramètre ou une variable à un paramètre de package enfant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-174">Click to map a parameter or variable to a child package parameter.</span></span>  
  
 <span data-ttu-id="59f5c-175">**Remove**</span><span class="sxs-lookup"><span data-stu-id="59f5c-175">**Remove**</span></span>  
 <span data-ttu-id="59f5c-176">Cliquez pour supprimer un mappage entre un paramètre ou une variable et un paramètre de package enfant.</span><span class="sxs-lookup"><span data-stu-id="59f5c-176">Click to remove a mapping between a parameter or variable and a child package parameter.</span></span>  
  
  
