---
title: Éditeur de tâche MSMQ (page recevoir) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.receive.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 7028756d-1dcc-480c-bbcd-e9654f0772a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f45aa579d37d1fdd3a3124eea972014ce839fdc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710716"
---
# <a name="message-queue-task-editor-receive-page"></a><span data-ttu-id="8f61d-102">Éditeur de tâche MSMQ (page Recevoir)</span><span class="sxs-lookup"><span data-stu-id="8f61d-102">Message Queue Task Editor (Receive Page)</span></span>
  <span data-ttu-id="8f61d-103">La page **Recevoir** de la boîte de dialogue **Éditeur de tâche MSMQ** permet de configurer une tâche MSMQ pour recevoir des messages MSMQ (Message Queuing) [!INCLUDE[msCoName](../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f61d-103">Use the **Receive** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to receive [!INCLUDE[msCoName](../includes/msconame-md.md)] Message Queuing (MSMQ) messages.</span></span>  
  
 <span data-ttu-id="8f61d-104">Pour en savoir plus sur cette tâche, consultez [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="8f61d-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8f61d-105">Options</span><span class="sxs-lookup"><span data-stu-id="8f61d-105">Options</span></span>  
 <span data-ttu-id="8f61d-106">**RemoveFromMessageQueue**</span><span class="sxs-lookup"><span data-stu-id="8f61d-106">**RemoveFromMessageQueue**</span></span>  
 <span data-ttu-id="8f61d-107">Indiquez si vous voulez supprimer le message de la file d'attente après sa réception.</span><span class="sxs-lookup"><span data-stu-id="8f61d-107">Indicate whether to remove the message from the queue after it is received.</span></span> <span data-ttu-id="8f61d-108">par défaut, cette valeur est définie sur `False`.</span><span class="sxs-lookup"><span data-stu-id="8f61d-108">By default, this value is set to `False`.</span></span>  
  
 <span data-ttu-id="8f61d-109">**ErrorIfMessageTimeOut**</span><span class="sxs-lookup"><span data-stu-id="8f61d-109">**ErrorIfMessageTimeOut**</span></span>  
 <span data-ttu-id="8f61d-110">Indiquez si la tâche échoue lorsque le message expire, en affichant un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="8f61d-110">Indicate whether the task fails when the message times out, displaying an error message.</span></span> <span data-ttu-id="8f61d-111">Par défaut, il s’agit de `False`.</span><span class="sxs-lookup"><span data-stu-id="8f61d-111">The default is `False`.</span></span>  
  
 <span data-ttu-id="8f61d-112">**TimeoutAfter**</span><span class="sxs-lookup"><span data-stu-id="8f61d-112">**TimeoutAfter**</span></span>  
 <span data-ttu-id="8f61d-113">Si vous choisissez d'afficher un message d'erreur sur l'échec de la tâche, définissez le nombre de secondes qui précèdent le message d'expiration.</span><span class="sxs-lookup"><span data-stu-id="8f61d-113">If you choose to display an error message on task failure, specify the number of seconds to wait before displaying the time-out message.</span></span>  
  
 <span data-ttu-id="8f61d-114">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="8f61d-114">**MessageType**</span></span>  
 <span data-ttu-id="8f61d-115">Sélectionnez le type de message :</span><span class="sxs-lookup"><span data-stu-id="8f61d-115">Select the message type.</span></span> <span data-ttu-id="8f61d-116">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="8f61d-116">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="8f61d-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="8f61d-117">Value</span></span>|<span data-ttu-id="8f61d-118">Description</span><span class="sxs-lookup"><span data-stu-id="8f61d-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8f61d-119">**Message de fichiers de données**</span><span class="sxs-lookup"><span data-stu-id="8f61d-119">**Data file message**</span></span>|<span data-ttu-id="8f61d-120">Le message est stocké dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="8f61d-120">The message is stored in a file.</span></span> <span data-ttu-id="8f61d-121">La sélection de cette valeur affiche l'option dynamique **DataFileMessage**.</span><span class="sxs-lookup"><span data-stu-id="8f61d-121">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="8f61d-122">**Message de type variable**</span><span class="sxs-lookup"><span data-stu-id="8f61d-122">**Variable message**</span></span>|<span data-ttu-id="8f61d-123">Le message est stocké dans une variable.</span><span class="sxs-lookup"><span data-stu-id="8f61d-123">The message is stored in a variable.</span></span> <span data-ttu-id="8f61d-124">Cette valeur affiche l'option dynamique **VariableMessage**.</span><span class="sxs-lookup"><span data-stu-id="8f61d-124">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="8f61d-125">**Message de type chaîne**</span><span class="sxs-lookup"><span data-stu-id="8f61d-125">**String message**</span></span>|<span data-ttu-id="8f61d-126">Le message est stocké dans la tâche MSMQ.</span><span class="sxs-lookup"><span data-stu-id="8f61d-126">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="8f61d-127">Cette valeur affiche l'option dynamique **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="8f61d-127">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
|<span data-ttu-id="8f61d-128">**Message de type chaîne pour la variable**</span><span class="sxs-lookup"><span data-stu-id="8f61d-128">**String message to variable**</span></span>|<span data-ttu-id="8f61d-129">Le message</span><span class="sxs-lookup"><span data-stu-id="8f61d-129">The message</span></span><br /><br /> <span data-ttu-id="8f61d-130">Cette valeur affiche l'option dynamique **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="8f61d-130">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="8f61d-131">Options dynamiques MessageType</span><span class="sxs-lookup"><span data-stu-id="8f61d-131">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="8f61d-132">MessageType = Message de fichiers de données</span><span class="sxs-lookup"><span data-stu-id="8f61d-132">MessageType = Data file message</span></span>  
 <span data-ttu-id="8f61d-133">**SaveFileAs**</span><span class="sxs-lookup"><span data-stu-id="8f61d-133">**SaveFileAs**</span></span>  
 <span data-ttu-id="8f61d-134">Tapez le chemin du fichier à utiliser ou cliquez sur le bouton avec des points de suspension **(...)** et recherchez le fichier.</span><span class="sxs-lookup"><span data-stu-id="8f61d-134">Type the path of the file to use, or click the ellipsis button **(...)** and then locate the file.</span></span>  
  
 <span data-ttu-id="8f61d-135">**Remplacer**</span><span class="sxs-lookup"><span data-stu-id="8f61d-135">**Overwrite**</span></span>  
 <span data-ttu-id="8f61d-136">Indiquez si vous voulez remplacer les données dans un fichier existant lors de l'enregistrement du contenu d'un message de fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="8f61d-136">Indicate whether to overwrite the data in an existing file when saving the contents of a data file message.</span></span> <span data-ttu-id="8f61d-137">Par défaut, il s’agit de `False`.</span><span class="sxs-lookup"><span data-stu-id="8f61d-137">The default is `False`.</span></span>  
  
 <span data-ttu-id="8f61d-138">**Filter**</span><span class="sxs-lookup"><span data-stu-id="8f61d-138">**Filter**</span></span>  
 <span data-ttu-id="8f61d-139">Indiquez si vous voulez appliquer un filtre au message.</span><span class="sxs-lookup"><span data-stu-id="8f61d-139">Specify whether to apply a filter to the message.</span></span> <span data-ttu-id="8f61d-140">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="8f61d-140">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="8f61d-141">Valeur</span><span class="sxs-lookup"><span data-stu-id="8f61d-141">Value</span></span>|<span data-ttu-id="8f61d-142">Description</span><span class="sxs-lookup"><span data-stu-id="8f61d-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8f61d-143">**Aucun filtre**</span><span class="sxs-lookup"><span data-stu-id="8f61d-143">**No filter**</span></span>|<span data-ttu-id="8f61d-144">La tâche ne filtre pas les messages.</span><span class="sxs-lookup"><span data-stu-id="8f61d-144">The task does not filter messages.</span></span> <span data-ttu-id="8f61d-145">Cette valeur affiche l’option dynamique **IdentifierReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="8f61d-145">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="8f61d-146">**À partir du package**</span><span class="sxs-lookup"><span data-stu-id="8f61d-146">**From package**</span></span>|<span data-ttu-id="8f61d-147">Le message reçoit uniquement les messages du package spécifié.</span><span class="sxs-lookup"><span data-stu-id="8f61d-147">The message receives only messages from the specified package.</span></span> <span data-ttu-id="8f61d-148">Cette valeur affiche l’option dynamique **Identifier**.</span><span class="sxs-lookup"><span data-stu-id="8f61d-148">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="8f61d-149">Options dynamiques de filtrage</span><span class="sxs-lookup"><span data-stu-id="8f61d-149">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="8f61d-150">Filtrer = Aucun filtre</span><span class="sxs-lookup"><span data-stu-id="8f61d-150">Filter = No filter</span></span>  
 <span data-ttu-id="8f61d-151">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="8f61d-151">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="8f61d-152">Cette option est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="8f61d-152">This option is read-only.</span></span> <span data-ttu-id="8f61d-153">Elle peut être vide ou contenir le GUID d'un package lorsque la propriété Filtrer a été définie.</span><span class="sxs-lookup"><span data-stu-id="8f61d-153">It may be blank or contain the GUID of a package when the Filter property was previously set.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="8f61d-154">Filtrer = À partir du package</span><span class="sxs-lookup"><span data-stu-id="8f61d-154">Filter = From package</span></span>  
 <span data-ttu-id="8f61d-155">**Identificateur**</span><span class="sxs-lookup"><span data-stu-id="8f61d-155">**Identifier**</span></span>  
 <span data-ttu-id="8f61d-156">Si vous choisissez d’appliquer un filtre, tapez l’identificateur unique du package à partir duquel les messages peuvent être reçus, ou cliquez sur le bouton de sélection **(...)** et spécifiez le package.</span><span class="sxs-lookup"><span data-stu-id="8f61d-156">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="8f61d-157">**Rubriques connexes :** [Sélectionner un package](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="8f61d-157">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="8f61d-158">MessageType = Message de type variable</span><span class="sxs-lookup"><span data-stu-id="8f61d-158">MessageType = Variable message</span></span>  
 <span data-ttu-id="8f61d-159">**Filter**</span><span class="sxs-lookup"><span data-stu-id="8f61d-159">**Filter**</span></span>  
 <span data-ttu-id="8f61d-160">Indiquez si vous voulez appliquer un filtre aux messages.</span><span class="sxs-lookup"><span data-stu-id="8f61d-160">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="8f61d-161">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="8f61d-161">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="8f61d-162">Valeur</span><span class="sxs-lookup"><span data-stu-id="8f61d-162">Value</span></span>|<span data-ttu-id="8f61d-163">Description</span><span class="sxs-lookup"><span data-stu-id="8f61d-163">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8f61d-164">**Aucun filtre**</span><span class="sxs-lookup"><span data-stu-id="8f61d-164">**No filter**</span></span>|<span data-ttu-id="8f61d-165">La tâche ne filtre pas les messages.</span><span class="sxs-lookup"><span data-stu-id="8f61d-165">The task does not filter messages.</span></span> <span data-ttu-id="8f61d-166">Cette valeur affiche l’option dynamique **IdentifierReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="8f61d-166">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="8f61d-167">**À partir du package**</span><span class="sxs-lookup"><span data-stu-id="8f61d-167">**From package**</span></span>|<span data-ttu-id="8f61d-168">Le message reçoit uniquement les messages du package spécifié.</span><span class="sxs-lookup"><span data-stu-id="8f61d-168">The message receives only messages from the specified package.</span></span> <span data-ttu-id="8f61d-169">Cette valeur affiche l’option dynamique **Identifier**.</span><span class="sxs-lookup"><span data-stu-id="8f61d-169">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
 <span data-ttu-id="8f61d-170">**Variable**</span><span class="sxs-lookup"><span data-stu-id="8f61d-170">**Variable**</span></span>  
 <span data-ttu-id="8f61d-171">Tapez le nom de la variable, ou cliquez sur \<**New variable...**> et définissez une nouvelle variable.</span><span class="sxs-lookup"><span data-stu-id="8f61d-171">Type the variable name, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="8f61d-172">**Rubriques connexes :** [Ajouter une variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="8f61d-172">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="8f61d-173">Options dynamiques de filtrage</span><span class="sxs-lookup"><span data-stu-id="8f61d-173">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="8f61d-174">Filtrer = Aucun filtre</span><span class="sxs-lookup"><span data-stu-id="8f61d-174">Filter = No filter</span></span>  
 <span data-ttu-id="8f61d-175">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="8f61d-175">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="8f61d-176">Cette option est vide.</span><span class="sxs-lookup"><span data-stu-id="8f61d-176">This option is blank.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="8f61d-177">Filtrer = À partir du package</span><span class="sxs-lookup"><span data-stu-id="8f61d-177">Filter = From package</span></span>  
 <span data-ttu-id="8f61d-178">**Identificateur**</span><span class="sxs-lookup"><span data-stu-id="8f61d-178">**Identifier**</span></span>  
 <span data-ttu-id="8f61d-179">Si vous choisissez d’appliquer un filtre, tapez l’identificateur unique du package à partir duquel les messages peuvent être reçus, ou cliquez sur le bouton de sélection **(...)** et spécifiez le package.</span><span class="sxs-lookup"><span data-stu-id="8f61d-179">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="8f61d-180">**Rubriques connexes :** [Sélectionner un package](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="8f61d-180">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="8f61d-181">MessageType = Message de type chaîne</span><span class="sxs-lookup"><span data-stu-id="8f61d-181">MessageType = String message</span></span>  
 <span data-ttu-id="8f61d-182">**Compare**</span><span class="sxs-lookup"><span data-stu-id="8f61d-182">**Compare**</span></span>  
 <span data-ttu-id="8f61d-183">Indiquez si vous voulez appliquer un filtre aux messages.</span><span class="sxs-lookup"><span data-stu-id="8f61d-183">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="8f61d-184">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="8f61d-184">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="8f61d-185">Valeur</span><span class="sxs-lookup"><span data-stu-id="8f61d-185">Value</span></span>|<span data-ttu-id="8f61d-186">Description</span><span class="sxs-lookup"><span data-stu-id="8f61d-186">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8f61d-187">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="8f61d-187">**None**</span></span>|<span data-ttu-id="8f61d-188">Les messages ne sont pas comparés.</span><span class="sxs-lookup"><span data-stu-id="8f61d-188">Messages are not compared.</span></span>|  
|<span data-ttu-id="8f61d-189">**Correspondance exacte**</span><span class="sxs-lookup"><span data-stu-id="8f61d-189">**Exact match**</span></span>|<span data-ttu-id="8f61d-190">Les messages doivent correspondre exactement à la chaîne figurant dans l’option **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="8f61d-190">Messages must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="8f61d-191">**Ignorer la casse**</span><span class="sxs-lookup"><span data-stu-id="8f61d-191">**Ignore case**</span></span>|<span data-ttu-id="8f61d-192">Le message doit correspondre à la chaîne figurant dans l’option **CompareString** , mais la comparaison ne tient pas compte de la casse.</span><span class="sxs-lookup"><span data-stu-id="8f61d-192">Message must match the string in the **CompareString** option, but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="8f61d-193">**Contenant**</span><span class="sxs-lookup"><span data-stu-id="8f61d-193">**Containing**</span></span>|<span data-ttu-id="8f61d-194">Le message doit contenir la chaîne figurant dans l’option **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="8f61d-194">Message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="8f61d-195">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="8f61d-195">**CompareString**</span></span>  
 <span data-ttu-id="8f61d-196">Si l’option **Comparer** n’est pas définie sur **Aucun**, indiquez la chaîne à laquelle le message doit être comparé.</span><span class="sxs-lookup"><span data-stu-id="8f61d-196">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
### <a name="messagetype--string-message-to-variable"></a><span data-ttu-id="8f61d-197">MessageType = Message de type chaîne pour la variable</span><span class="sxs-lookup"><span data-stu-id="8f61d-197">MessageType = String message to variable</span></span>  
 <span data-ttu-id="8f61d-198">**Compare**</span><span class="sxs-lookup"><span data-stu-id="8f61d-198">**Compare**</span></span>  
 <span data-ttu-id="8f61d-199">Indiquez si vous voulez appliquer un filtre aux messages.</span><span class="sxs-lookup"><span data-stu-id="8f61d-199">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="8f61d-200">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="8f61d-200">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="8f61d-201">Valeur</span><span class="sxs-lookup"><span data-stu-id="8f61d-201">Value</span></span>|<span data-ttu-id="8f61d-202">Description</span><span class="sxs-lookup"><span data-stu-id="8f61d-202">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8f61d-203">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="8f61d-203">**None**</span></span>|<span data-ttu-id="8f61d-204">Les messages ne sont pas comparés.</span><span class="sxs-lookup"><span data-stu-id="8f61d-204">Messages are not compared.</span></span>|  
|<span data-ttu-id="8f61d-205">**Correspondance exacte**</span><span class="sxs-lookup"><span data-stu-id="8f61d-205">**Exact match**</span></span>|<span data-ttu-id="8f61d-206">Le message doit correspondre exactement à la chaîne figurant dans l’option **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="8f61d-206">The message must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="8f61d-207">**Ignorer la casse**</span><span class="sxs-lookup"><span data-stu-id="8f61d-207">**Ignore case**</span></span>|<span data-ttu-id="8f61d-208">Le message doit correspondre à la chaîne figurant dans l’option **CompareString** , mais la comparaison ne tient pas compte de la casse.</span><span class="sxs-lookup"><span data-stu-id="8f61d-208">The message must match the string in the **CompareString** option but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="8f61d-209">**Contenant**</span><span class="sxs-lookup"><span data-stu-id="8f61d-209">**Containing**</span></span>|<span data-ttu-id="8f61d-210">Le message doit contenir la chaîne figurant dans l’option **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="8f61d-210">The message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="8f61d-211">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="8f61d-211">**CompareString**</span></span>  
 <span data-ttu-id="8f61d-212">Si l’option **Comparer** n’est pas définie sur **Aucun**, indiquez la chaîne à laquelle le message doit être comparé.</span><span class="sxs-lookup"><span data-stu-id="8f61d-212">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
 <span data-ttu-id="8f61d-213">**Variable**</span><span class="sxs-lookup"><span data-stu-id="8f61d-213">**Variable**</span></span>  
 <span data-ttu-id="8f61d-214">Tapez le nom de la variable qui doit contenir le message reçu, ou cliquez sur \<**New variable...**> et définissez une nouvelle variable.</span><span class="sxs-lookup"><span data-stu-id="8f61d-214">Type the name of the variable to hold the received message, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="8f61d-215">**Rubriques connexes :** [Ajouter une variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="8f61d-215">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f61d-216">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8f61d-216">See Also</span></span>  
 <span data-ttu-id="8f61d-217">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8f61d-217">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8f61d-218">[Éditeur de tâche MSMQ &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="8f61d-218">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="8f61d-219">[Éditeur de tâche MSMQ &#40;page envoyer&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="8f61d-219">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 <span data-ttu-id="8f61d-220">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="8f61d-220">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="8f61d-221">Tâche MSMQ</span><span class="sxs-lookup"><span data-stu-id="8f61d-221">Message Queue Task</span></span>](control-flow/message-queue-task.md)  
  
  
