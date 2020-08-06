---
title: Éditeur de tâche FTP (page transfert de fichiers) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.filetransfer.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 37e52220-feb2-474c-ad88-fa1b1059acd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8094051e93c4165be6ae186bde394f9271d60669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602896"
---
# <a name="ftp-task-editor-file-transfer-page"></a><span data-ttu-id="265ca-102">Éditeur de tâche FTP (page Transfert de fichiers)</span><span class="sxs-lookup"><span data-stu-id="265ca-102">FTP Task Editor (File Transfer Page)</span></span>
  <span data-ttu-id="265ca-103">Utilisez la page **Transfert de fichiers** de l' **Éditeur de tâche FTP** pour configurer l'opération FTP qu'exécute la tâche.</span><span class="sxs-lookup"><span data-stu-id="265ca-103">Use the **File Transfer** page of the **FTP Task Editor** dialog box to configure the FTP operation that the task performs.</span></span>  
  
 <span data-ttu-id="265ca-104">Pour en savoir plus sur cette tâche, consultez [Tâche FTP](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="265ca-104">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="265ca-105">Options</span><span class="sxs-lookup"><span data-stu-id="265ca-105">Options</span></span>  
 <span data-ttu-id="265ca-106">**IsRemotePathVariable**</span><span class="sxs-lookup"><span data-stu-id="265ca-106">**IsRemotePathVariable**</span></span>  
 <span data-ttu-id="265ca-107">Indique si le chemin distant est stocké dans une variable.</span><span class="sxs-lookup"><span data-stu-id="265ca-107">Indicate whether the remote path is stored in a variable.</span></span> <span data-ttu-id="265ca-108">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="265ca-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="265ca-109">Valeur</span><span class="sxs-lookup"><span data-stu-id="265ca-109">Value</span></span>|<span data-ttu-id="265ca-110">Description</span><span class="sxs-lookup"><span data-stu-id="265ca-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="265ca-111">**True**</span><span class="sxs-lookup"><span data-stu-id="265ca-111">**True**</span></span>|<span data-ttu-id="265ca-112">Le chemin d'accès de destination est stocké dans une variable.</span><span class="sxs-lookup"><span data-stu-id="265ca-112">The destination path is stored in a variable.</span></span> <span data-ttu-id="265ca-113">Cette valeur affiche l'option dynamique **RemoteVariable**.</span><span class="sxs-lookup"><span data-stu-id="265ca-113">Selecting the value displays the dynamic option, **RemoteVariable**.</span></span>|  
|<span data-ttu-id="265ca-114">**False**</span><span class="sxs-lookup"><span data-stu-id="265ca-114">**False**</span></span>|<span data-ttu-id="265ca-115">Le chemin d'accès de destination est défini dans un gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="265ca-115">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="265ca-116">Cette valeur affiche l'option dynamique **RemovePath**.</span><span class="sxs-lookup"><span data-stu-id="265ca-116">Selecting the value displays the dynamic option, **RemotePath**.</span></span>|  
  
 <span data-ttu-id="265ca-117">**OverwriteFileAtDestination**</span><span class="sxs-lookup"><span data-stu-id="265ca-117">**OverwriteFileAtDestination**</span></span>  
 <span data-ttu-id="265ca-118">Indique si un fichier peut être remplacé dans la destination.</span><span class="sxs-lookup"><span data-stu-id="265ca-118">Specify whether a file at the destination can be overwritten.</span></span>  
  
 <span data-ttu-id="265ca-119">**IsLocalPathVariable**</span><span class="sxs-lookup"><span data-stu-id="265ca-119">**IsLocalPathVariable**</span></span>  
 <span data-ttu-id="265ca-120">Indique si le chemin local est stocké dans une variable.</span><span class="sxs-lookup"><span data-stu-id="265ca-120">Indicate whether the local path is stored in a variable.</span></span> <span data-ttu-id="265ca-121">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="265ca-121">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="265ca-122">Valeur</span><span class="sxs-lookup"><span data-stu-id="265ca-122">Value</span></span>|<span data-ttu-id="265ca-123">Description</span><span class="sxs-lookup"><span data-stu-id="265ca-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="265ca-124">**True**</span><span class="sxs-lookup"><span data-stu-id="265ca-124">**True**</span></span>|<span data-ttu-id="265ca-125">Le chemin d'accès de destination est stocké dans une variable.</span><span class="sxs-lookup"><span data-stu-id="265ca-125">The destination path is stored in a variable.</span></span> <span data-ttu-id="265ca-126">Cette valeur affiche l'option dynamique **LocalVariable**.</span><span class="sxs-lookup"><span data-stu-id="265ca-126">Selecting the value displays the dynamic option, **LocalVariable**.</span></span>|  
|<span data-ttu-id="265ca-127">**False**</span><span class="sxs-lookup"><span data-stu-id="265ca-127">**False**</span></span>|<span data-ttu-id="265ca-128">Le chemin d'accès de destination est défini dans un gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="265ca-128">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="265ca-129">Cette valeur affiche l'option dynamique **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="265ca-129">Selecting the value displays the dynamic option, **LocalPath**.</span></span>|  
  
 <span data-ttu-id="265ca-130">**opération**</span><span class="sxs-lookup"><span data-stu-id="265ca-130">**Operation**</span></span>  
 <span data-ttu-id="265ca-131">Sélectionnez l'opération FTP à exécuter.</span><span class="sxs-lookup"><span data-stu-id="265ca-131">Select the FTP operation to perform.</span></span> <span data-ttu-id="265ca-132">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="265ca-132">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="265ca-133">Valeur</span><span class="sxs-lookup"><span data-stu-id="265ca-133">Value</span></span>|<span data-ttu-id="265ca-134">Description</span><span class="sxs-lookup"><span data-stu-id="265ca-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="265ca-135">**Envoyer des fichiers**</span><span class="sxs-lookup"><span data-stu-id="265ca-135">**Send files**</span></span>|<span data-ttu-id="265ca-136">Envoie des fichiers.</span><span class="sxs-lookup"><span data-stu-id="265ca-136">Send files.</span></span> <span data-ttu-id="265ca-137">Cette valeur affiche les options dynamiques **LocalVariable**, **LocalPathRemoteVariable** et **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="265ca-137">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="265ca-138">**Recevoir des fichiers**</span><span class="sxs-lookup"><span data-stu-id="265ca-138">**Receive files**</span></span>|<span data-ttu-id="265ca-139">Reçoit des fichiers.</span><span class="sxs-lookup"><span data-stu-id="265ca-139">Receive files.</span></span> <span data-ttu-id="265ca-140">Cette valeur affiche les options dynamiques **LocalVariable**, **LocalPathRemoteVariable** et **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="265ca-140">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="265ca-141">**Créer un répertoire local**</span><span class="sxs-lookup"><span data-stu-id="265ca-141">**Create local directory**</span></span>|<span data-ttu-id="265ca-142">Crée un répertoire local.</span><span class="sxs-lookup"><span data-stu-id="265ca-142">Create a local directory.</span></span> <span data-ttu-id="265ca-143">Cette valeur affiche les options dynamiques **LocalVariable** et **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="265ca-143">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="265ca-144">**Créer un répertoire distant**</span><span class="sxs-lookup"><span data-stu-id="265ca-144">**Create remote directory**</span></span>|<span data-ttu-id="265ca-145">Crée un répertoire distant.</span><span class="sxs-lookup"><span data-stu-id="265ca-145">Create a remote directory.</span></span> <span data-ttu-id="265ca-146">Cette valeur affiche les options dynamiques **RemoteVariable** et **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="265ca-146">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotelPath**.</span></span>|  
|<span data-ttu-id="265ca-147">**Supprimer le répertoire local**</span><span class="sxs-lookup"><span data-stu-id="265ca-147">**Remove local directory**</span></span>|<span data-ttu-id="265ca-148">Supprime un répertoire local.</span><span class="sxs-lookup"><span data-stu-id="265ca-148">Removes a local directory.</span></span> <span data-ttu-id="265ca-149">Cette valeur affiche les options dynamiques **LocalVariable** et **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="265ca-149">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="265ca-150">**Supprimer le répertoire distant**</span><span class="sxs-lookup"><span data-stu-id="265ca-150">**Remove remote directory**</span></span>|<span data-ttu-id="265ca-151">Supprime un répertoire distant.</span><span class="sxs-lookup"><span data-stu-id="265ca-151">Remove a remote directory.</span></span> <span data-ttu-id="265ca-152">Cette valeur affiche les options dynamiques **RemoteVariable** et **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="265ca-152">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="265ca-153">**Supprimer des fichiers locaux**</span><span class="sxs-lookup"><span data-stu-id="265ca-153">**Delete local files**</span></span>|<span data-ttu-id="265ca-154">Supprime des fichiers locaux</span><span class="sxs-lookup"><span data-stu-id="265ca-154">Delete local files.</span></span> <span data-ttu-id="265ca-155">Cette valeur affiche les options dynamiques **LocalVariable** et **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="265ca-155">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="265ca-156">**Supprimer des fichiers distants**</span><span class="sxs-lookup"><span data-stu-id="265ca-156">**Delete remote files**</span></span>|<span data-ttu-id="265ca-157">Supprime des fichiers distants.</span><span class="sxs-lookup"><span data-stu-id="265ca-157">Delete remote files.</span></span> <span data-ttu-id="265ca-158">Cette valeur affiche les options dynamiques **RemoteVariable** et **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="265ca-158">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
  
 <span data-ttu-id="265ca-159">**IsTransferASCII**</span><span class="sxs-lookup"><span data-stu-id="265ca-159">**IsTransferASCII**</span></span>  
 <span data-ttu-id="265ca-160">Indique si les fichiers transférés vers et depuis le serveur FTP distant doivent être transférés en mode ASCII.</span><span class="sxs-lookup"><span data-stu-id="265ca-160">Indicate whether files transferred to and from the remote FTP server should be transferred in ASCII mode.</span></span>  
  
## <a name="isremotepathvariable-dynamic-options"></a><span data-ttu-id="265ca-161">Options dynamiques IsRemotePathVariable</span><span class="sxs-lookup"><span data-stu-id="265ca-161">IsRemotePathVariable Dynamic Options</span></span>  
  
### <a name="isremotepathvariable--true"></a><span data-ttu-id="265ca-162">IsRemotePathVariable = True</span><span class="sxs-lookup"><span data-stu-id="265ca-162">IsRemotePathVariable = True</span></span>  
 <span data-ttu-id="265ca-163">**RemoteVariable**</span><span class="sxs-lookup"><span data-stu-id="265ca-163">**RemoteVariable**</span></span>  
 <span data-ttu-id="265ca-164">Sélectionnez une variable définie par l’utilisateur existante ou cliquez sur \<**New variable...**> pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="265ca-164">Select an existing user-defined variable, or click \<**New variable...**> to create a user-defined variable.</span></span>  
  
 <span data-ttu-id="265ca-165">**Rubriques connexes :** [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), Ajouter une variable</span><span class="sxs-lookup"><span data-stu-id="265ca-165">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="isremotepathvariable--false"></a><span data-ttu-id="265ca-166">IsRemotePathVariable = False</span><span class="sxs-lookup"><span data-stu-id="265ca-166">IsRemotePathVariable = False</span></span>  
 <span data-ttu-id="265ca-167">**RemovePath**</span><span class="sxs-lookup"><span data-stu-id="265ca-167">**RemotePath**</span></span>  
 <span data-ttu-id="265ca-168">Sélectionnez un gestionnaire de connexions FTP ou cliquez sur \<**New connection...**> pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="265ca-168">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="265ca-169">**Rubriques connexes :** [Gestionnaires de connexions FTP](connection-manager/ftp-connection-manager.md), [Éditeur du gestionnaire de connexions FTP](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="265ca-169">**Related Topics:** [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
## <a name="islocalpathvariable-dynamic-options"></a><span data-ttu-id="265ca-170">Options dynamiques IsLocalPathVariable</span><span class="sxs-lookup"><span data-stu-id="265ca-170">IsLocalPathVariable Dynamic Options</span></span>  
  
### <a name="islocalpathvariable--true"></a><span data-ttu-id="265ca-171">IsLocalPathVariable = True</span><span class="sxs-lookup"><span data-stu-id="265ca-171">IsLocalPathVariable = True</span></span>  
 <span data-ttu-id="265ca-172">**LocalVariable**</span><span class="sxs-lookup"><span data-stu-id="265ca-172">**LocalVariable**</span></span>  
 <span data-ttu-id="265ca-173">Sélectionnez une variable définie par l’utilisateur existante ou cliquez sur \<**New variable...**> pour créer une variable.</span><span class="sxs-lookup"><span data-stu-id="265ca-173">Select an existing user-defined variable, or click \<**New variable...**> to create a variable.</span></span>  
  
 <span data-ttu-id="265ca-174">**Rubriques connexes :** [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), Ajouter une variable</span><span class="sxs-lookup"><span data-stu-id="265ca-174">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="islocalpathvariable--false"></a><span data-ttu-id="265ca-175">IsLocalPathVariable = False</span><span class="sxs-lookup"><span data-stu-id="265ca-175">IsLocalPathVariable = False</span></span>  
 <span data-ttu-id="265ca-176">**LocalPath**</span><span class="sxs-lookup"><span data-stu-id="265ca-176">**LocalPath**</span></span>  
 <span data-ttu-id="265ca-177">Sélectionnez un gestionnaire de connexions de fichiers existant ou cliquez sur \<**New connection...**> pour en créer un.</span><span class="sxs-lookup"><span data-stu-id="265ca-177">Select an existing File connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="265ca-178">**Rubriques connexes :**[Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="265ca-178">**Related Topics**: [Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="265ca-179">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="265ca-179">See Also</span></span>  
 <span data-ttu-id="265ca-180">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="265ca-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="265ca-181">[Éditeur de tâche FTP &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="265ca-181">[FTP Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="265ca-182">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="265ca-182">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
