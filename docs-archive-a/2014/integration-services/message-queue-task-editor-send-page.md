---
title: Éditeur de tâche MSMQ (page Envoyer) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.send.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 565aa079-ac44-4407-8efc-cddab839de30
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3534e1a8b475f22064ef7f2283c2e70eb561294f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710715"
---
# <a name="message-queue-task-editor-send-page"></a><span data-ttu-id="9168f-102">Éditeur de tâche MSMQ (page Envoyer)</span><span class="sxs-lookup"><span data-stu-id="9168f-102">Message Queue Task Editor (Send Page)</span></span>
  <span data-ttu-id="9168f-103">Utilisez la page **Envoyer** de la boîte de dialogue **Éditeur de tâche MSMQ** pour configurer une tâche MSMQ afin d’envoyer des messages depuis un package [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9168f-103">Use the **Send** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to send messages from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="9168f-104">Pour en savoir plus sur cette tâche, consultez [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="9168f-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9168f-105">Options</span><span class="sxs-lookup"><span data-stu-id="9168f-105">Options</span></span>  
 <span data-ttu-id="9168f-106">**UseEncryption**</span><span class="sxs-lookup"><span data-stu-id="9168f-106">**UseEncryption**</span></span>  
 <span data-ttu-id="9168f-107">Indiquez si le message doit être chiffré.</span><span class="sxs-lookup"><span data-stu-id="9168f-107">Indicate whether to encrypt the message.</span></span> <span data-ttu-id="9168f-108">Par défaut, il s’agit de `False`.</span><span class="sxs-lookup"><span data-stu-id="9168f-108">The default is `False`.</span></span>  
  
 <span data-ttu-id="9168f-109">**EncryptionAlgorithm**</span><span class="sxs-lookup"><span data-stu-id="9168f-109">**EncryptionAlgorithm**</span></span>  
 <span data-ttu-id="9168f-110">Si vous utilisez le chiffrement, définissez le nom de l'algorithme de chiffrement à utiliser.</span><span class="sxs-lookup"><span data-stu-id="9168f-110">If you choose to use encryption, specify the name of the encryption algorithm to use.</span></span> <span data-ttu-id="9168f-111">La tâche MSMQ peut utiliser les algorithmes RC2 et RC4.</span><span class="sxs-lookup"><span data-stu-id="9168f-111">The Message Queue task can use the RC2 and RC4 algorithms.</span></span> <span data-ttu-id="9168f-112">La valeur par défaut est **RC2**.</span><span class="sxs-lookup"><span data-stu-id="9168f-112">The default is **RC2**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9168f-113">L'algorithme RC4 est uniquement pris en charge pour des raisons de compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="9168f-113">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="9168f-114">Le nouveau matériel ne peut être chiffré à l'aide de RC4 ou de RC4_128 que lorsque la base de données se trouve dans le niveau de compatibilité 90 ou 100.</span><span class="sxs-lookup"><span data-stu-id="9168f-114">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="9168f-115">(Non recommandé.) Utilisez à la place un algorithme plus récent, tel qu'un des algorithmes AES.</span><span class="sxs-lookup"><span data-stu-id="9168f-115">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="9168f-116">Dans la version actuelle de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], le matériel chiffré à l'aide de RC4 ou de RC4_128 peut être déchiffré dans n'importe quel niveau de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="9168f-116">In the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9168f-117">Il s'agit des algorithmes de chiffrement que la technologie Message Queuing (ou MSMQ) prend en charge.</span><span class="sxs-lookup"><span data-stu-id="9168f-117">These are the encryption algorithms that the Message Queuing (also known as MSMQ) technology supports.</span></span> <span data-ttu-id="9168f-118">Ces deux algorithmes de chiffrement sont aujourd'hui considérés comme faibles du point de vue du chiffrement par rapport aux algorithmes plus récents, non encore pris en charge par la technologie Microsoft Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="9168f-118">Both of these encryption algorithms are now considered cryptographically weak compared to newer algorithms, which Message Queuing does not yet support.</span></span> <span data-ttu-id="9168f-119">Par conséquent, vous devez minutieusement évaluer vos besoins en matière de chiffrement si vous souhaitez envoyer des messages à l'aide de la tâche MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9168f-119">Therefore, you should consider your cryptography needs carefully when sending messages using the Message Queue task.</span></span>  
  
 <span data-ttu-id="9168f-120">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="9168f-120">**MessageType**</span></span>  
 <span data-ttu-id="9168f-121">Sélectionnez le type de message :</span><span class="sxs-lookup"><span data-stu-id="9168f-121">Select the message type.</span></span> <span data-ttu-id="9168f-122">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="9168f-122">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="9168f-123">Valeur</span><span class="sxs-lookup"><span data-stu-id="9168f-123">Value</span></span>|<span data-ttu-id="9168f-124">Description</span><span class="sxs-lookup"><span data-stu-id="9168f-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9168f-125">**Message de fichiers de données**</span><span class="sxs-lookup"><span data-stu-id="9168f-125">**Data file message**</span></span>|<span data-ttu-id="9168f-126">Le message est stocké dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="9168f-126">The message is stored in a file.</span></span> <span data-ttu-id="9168f-127">La sélection de cette valeur affiche l'option dynamique **DataFileMessage**.</span><span class="sxs-lookup"><span data-stu-id="9168f-127">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="9168f-128">**Message de type variable**</span><span class="sxs-lookup"><span data-stu-id="9168f-128">**Variable message**</span></span>|<span data-ttu-id="9168f-129">Le message est stocké dans une variable.</span><span class="sxs-lookup"><span data-stu-id="9168f-129">The message is stored in a variable.</span></span> <span data-ttu-id="9168f-130">Cette valeur affiche l'option dynamique **VariableMessage**.</span><span class="sxs-lookup"><span data-stu-id="9168f-130">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="9168f-131">**Message de type chaîne**</span><span class="sxs-lookup"><span data-stu-id="9168f-131">**String message**</span></span>|<span data-ttu-id="9168f-132">Le message est stocké dans la tâche MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9168f-132">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="9168f-133">Cette valeur affiche l'option dynamique **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="9168f-133">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="9168f-134">Options dynamiques MessageType</span><span class="sxs-lookup"><span data-stu-id="9168f-134">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="9168f-135">MessageType = Message de fichiers de données</span><span class="sxs-lookup"><span data-stu-id="9168f-135">MessageType = Data file message</span></span>  
 <span data-ttu-id="9168f-136">**DataFileMessage**</span><span class="sxs-lookup"><span data-stu-id="9168f-136">**DataFileMessage**</span></span>  
 <span data-ttu-id="9168f-137">Tapez le chemin du fichier de données ou cliquez sur le bouton avec les points de suspension **(...)** et recherchez le fichier.</span><span class="sxs-lookup"><span data-stu-id="9168f-137">Type the path of the data file, or click the ellipsis **(...)** and then locate the file.</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="9168f-138">MessageType = Message de type variable</span><span class="sxs-lookup"><span data-stu-id="9168f-138">MessageType = Variable message</span></span>  
 <span data-ttu-id="9168f-139">**VariableMessage**</span><span class="sxs-lookup"><span data-stu-id="9168f-139">**VariableMessage**</span></span>  
 <span data-ttu-id="9168f-140">Tapez les noms de variables ou cliquez sur les points de suspension **(...)** et sélectionnez les variables.</span><span class="sxs-lookup"><span data-stu-id="9168f-140">Type the variable names, or click the ellipsis **(...)** and then select the variables.</span></span> <span data-ttu-id="9168f-141">Les variables sont séparées par des virgules.</span><span class="sxs-lookup"><span data-stu-id="9168f-141">Variables are separated by commas.</span></span>  
  
 <span data-ttu-id="9168f-142">**Rubriques connexes :** Sélectionner des variables</span><span class="sxs-lookup"><span data-stu-id="9168f-142">**Related Topics:** Select Variables</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="9168f-143">MessageType = Message de type chaîne</span><span class="sxs-lookup"><span data-stu-id="9168f-143">MessageType = String message</span></span>  
 <span data-ttu-id="9168f-144">**StringMessage**</span><span class="sxs-lookup"><span data-stu-id="9168f-144">**StringMessage**</span></span>  
 <span data-ttu-id="9168f-145">Tapez le message de type chaîne ou cliquez sur les points de suspension **(...)** et entrez le message dans la boîte de dialogue **Entrer le message de type chaîne** .</span><span class="sxs-lookup"><span data-stu-id="9168f-145">Type the string message, or click the ellipsis **(...)** and then type the message in the **Enter String Message** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9168f-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9168f-146">See Also</span></span>  
 <span data-ttu-id="9168f-147">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9168f-147">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9168f-148">[Éditeur de tâche MSMQ &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="9168f-148">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="9168f-149">[Éditeur de tâche MSMQ &#40;page de réception&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="9168f-149">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 [<span data-ttu-id="9168f-150">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="9168f-150">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
