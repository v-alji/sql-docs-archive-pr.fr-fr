---
title: Éditeur de tâche Envoyer un message (page courrier) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.mail.f1
helpviewer_keywords:
- Send Mail Task Editor
ms.assetid: adb385d5-ef24-4d18-b9ea-b39e00a7075e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 52cab62f3c88ea248b76061664547fd8f1314099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709767"
---
# <a name="send-mail-task-editor-mail-page"></a><span data-ttu-id="1f67d-102">Éditeur de tâche Envoyer un message (page Courrier)</span><span class="sxs-lookup"><span data-stu-id="1f67d-102">Send Mail Task Editor (Mail Page)</span></span>
  <span data-ttu-id="1f67d-103">Utilisez la page **Courrier** de la boîte de dialogue **Éditeur de tâche Envoyer un message** pour indiquer les destinataires d'un message, son type et sa priorité.</span><span class="sxs-lookup"><span data-stu-id="1f67d-103">Use the **Mail** page of the **Send Mail Task Editor** dialog box to specify recipients, message type, and priority for a message.</span></span> <span data-ttu-id="1f67d-104">Vous pouvez également joindre des fichiers au message.</span><span class="sxs-lookup"><span data-stu-id="1f67d-104">You can also attach files to the message.</span></span> <span data-ttu-id="1f67d-105">Le texte de ce courrier peut se présenter sous la forme d'une chaîne que vous précisez, d'une connexion à un fichier comportant le texte voulu ou le nom d'une variable contenant le texte en question.</span><span class="sxs-lookup"><span data-stu-id="1f67d-105">The message text can be a string you provide, a file connection to a file that contains the text, or the name of a variable that contains the text.</span></span>  
  
 <span data-ttu-id="1f67d-106">Pour en savoir plus sur cette tâche, consultez [Send Mail Task](control-flow/send-mail-task.md).</span><span class="sxs-lookup"><span data-stu-id="1f67d-106">To learn about this task, see [Send Mail Task](control-flow/send-mail-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f67d-107">Options</span><span class="sxs-lookup"><span data-stu-id="1f67d-107">Options</span></span>  
 <span data-ttu-id="1f67d-108">**SMTPConnection**</span><span class="sxs-lookup"><span data-stu-id="1f67d-108">**SMTPConnection**</span></span>  
 <span data-ttu-id="1f67d-109">Sélectionnez un gestionnaire de connexions SMTP dans la liste, ou cliquez sur **\<New connection...>** pour en créer un.</span><span class="sxs-lookup"><span data-stu-id="1f67d-109">Select an SMTP connection manager in the list, or click **\<New connection...>** to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1f67d-110">Le gestionnaire de connexions SMTP prend en charge uniquement l'authentification anonyme et l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="1f67d-110">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="1f67d-111">Il ne prend pas en charge l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="1f67d-111">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="1f67d-112">**Rubriques connexes :** [Gestionnaire de connexions SMTP](connection-manager/smtp-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="1f67d-112">**Related Topics:** [SMTP Connection Manager](connection-manager/smtp-connection-manager.md)</span></span>  
  
 <span data-ttu-id="1f67d-113">**From**</span><span class="sxs-lookup"><span data-stu-id="1f67d-113">**From**</span></span>  
 <span data-ttu-id="1f67d-114">Indique l'adresse électronique de l'expéditeur.</span><span class="sxs-lookup"><span data-stu-id="1f67d-114">Specify the e-mail address of the sender.</span></span>  
  
 <span data-ttu-id="1f67d-115">**To**</span><span class="sxs-lookup"><span data-stu-id="1f67d-115">**To**</span></span>  
 <span data-ttu-id="1f67d-116">Fournit les adresses de messagerie des destinataires séparées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="1f67d-116">Provide the e-mail addresses of the recipients, delimited by semicolons.</span></span>  
  
 <span data-ttu-id="1f67d-117">**Cc**</span><span class="sxs-lookup"><span data-stu-id="1f67d-117">**Cc**</span></span>  
 <span data-ttu-id="1f67d-118">Fournit les adresses de messagerie des individus destinés à recevoir une copie du message, séparées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="1f67d-118">Specify the e-mail addresses, delimited by semicolons, of individuals who also receive copies of the message.</span></span>  
  
 <span data-ttu-id="1f67d-119">**Cci**</span><span class="sxs-lookup"><span data-stu-id="1f67d-119">**Bcc**</span></span>  
 <span data-ttu-id="1f67d-120">Fournit les adresses de messagerie des individus destinés à recevoir une copie carbone invisible (Cci) du message, séparées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="1f67d-120">Specify the e-mail addresses, delimited by semicolons, of individuals who receive blind carbon copies (Bcc) copies of the message.</span></span>  
  
 <span data-ttu-id="1f67d-121">**Subject**</span><span class="sxs-lookup"><span data-stu-id="1f67d-121">**Subject**</span></span>  
 <span data-ttu-id="1f67d-122">Permet de spécifier l'objet du message électronique.</span><span class="sxs-lookup"><span data-stu-id="1f67d-122">Provide a subject for the e-mail message.</span></span>  
  
 <span data-ttu-id="1f67d-123">**MessageSourceType**</span><span class="sxs-lookup"><span data-stu-id="1f67d-123">**MessageSourceType**</span></span>  
 <span data-ttu-id="1f67d-124">Permet de sélectionner le type de source du message.</span><span class="sxs-lookup"><span data-stu-id="1f67d-124">Select the source type of the message.</span></span> <span data-ttu-id="1f67d-125">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="1f67d-125">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="1f67d-126">Valeur</span><span class="sxs-lookup"><span data-stu-id="1f67d-126">Value</span></span>|<span data-ttu-id="1f67d-127">Description</span><span class="sxs-lookup"><span data-stu-id="1f67d-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1f67d-128">**Entrée directe**</span><span class="sxs-lookup"><span data-stu-id="1f67d-128">**Direct input**</span></span>|<span data-ttu-id="1f67d-129">Permet de définir la source du texte du message.</span><span class="sxs-lookup"><span data-stu-id="1f67d-129">Set the source to the message text.</span></span> <span data-ttu-id="1f67d-130">Si cette valeur est sélectionnée, les options dynamiques incluses dans **MessageSource**s'affichent alors.</span><span class="sxs-lookup"><span data-stu-id="1f67d-130">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="1f67d-131">**Connexion de fichiers**</span><span class="sxs-lookup"><span data-stu-id="1f67d-131">**File connection**</span></span>|<span data-ttu-id="1f67d-132">Permet de définir la source du fichier contenant le texte du message.</span><span class="sxs-lookup"><span data-stu-id="1f67d-132">Set the source to the file that contains the message text.</span></span> <span data-ttu-id="1f67d-133">Si cette valeur est sélectionnée, les options dynamiques incluses dans **MessageSource**s'affichent alors.</span><span class="sxs-lookup"><span data-stu-id="1f67d-133">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="1f67d-134">**Variable**</span><span class="sxs-lookup"><span data-stu-id="1f67d-134">**Variable**</span></span>|<span data-ttu-id="1f67d-135">Permet d'attribuer à la source une variable contenant le texte du message.</span><span class="sxs-lookup"><span data-stu-id="1f67d-135">Set the source to a variable that contains the message text.</span></span> <span data-ttu-id="1f67d-136">Si cette valeur est sélectionnée, les options dynamiques incluses dans **MessageSource**s'affichent alors.</span><span class="sxs-lookup"><span data-stu-id="1f67d-136">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
  
 <span data-ttu-id="1f67d-137">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="1f67d-137">**Priority**</span></span>  
 <span data-ttu-id="1f67d-138">Permet d'indiquer la priorité à appliquer au message.</span><span class="sxs-lookup"><span data-stu-id="1f67d-138">Set the priority of the message.</span></span>  
  
 <span data-ttu-id="1f67d-139">**Pièces jointes**</span><span class="sxs-lookup"><span data-stu-id="1f67d-139">**Attachments**</span></span>  
 <span data-ttu-id="1f67d-140">Indique le nom des fichiers joints au message électronique, séparés par le caractère Barre verticale (|).</span><span class="sxs-lookup"><span data-stu-id="1f67d-140">Provide the file names of attachments to the e-mail message, delimited by the pipe (|) character.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f67d-141">Les lignes À, Cc et Cci sont limitées à 256 caractères, conformément aux Internet standards.</span><span class="sxs-lookup"><span data-stu-id="1f67d-141">The To, Cc, and Bcc lines are limited to 256 characters in accordance with Internet standards.</span></span>  
  
## <a name="messagesourcetype-dynamic-options"></a><span data-ttu-id="1f67d-142">Options dynamiques de MessageSourceType</span><span class="sxs-lookup"><span data-stu-id="1f67d-142">MessageSourceType Dynamic Options</span></span>  
  
### <a name="messagesourcetype--direct-input"></a><span data-ttu-id="1f67d-143">MessageSourceType = Entrée directe</span><span class="sxs-lookup"><span data-stu-id="1f67d-143">MessageSourceType = Direct Input</span></span>  
 <span data-ttu-id="1f67d-144">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="1f67d-144">**MessageSource**</span></span>  
 <span data-ttu-id="1f67d-145">Permet d’entrer le texte du message ou de cliquer sur le bouton d’exploration représenté par les points de suspension (...), puis de taper le message dans la boîte de dialogue **Source du message**.</span><span class="sxs-lookup"><span data-stu-id="1f67d-145">Type the message text or click the browse button (...) and then type the message in the **Message source** dialog box.</span></span>  
  
### <a name="messagesourcetype--file-connection"></a><span data-ttu-id="1f67d-146">MessageSourceType = Connexion de fichiers</span><span class="sxs-lookup"><span data-stu-id="1f67d-146">MessageSourceType = File connection</span></span>  
 <span data-ttu-id="1f67d-147">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="1f67d-147">**MessageSource**</span></span>  
 <span data-ttu-id="1f67d-148">Sélectionnez un gestionnaire de connexions de fichiers dans la liste ou cliquez sur \<**New connection...**> pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="1f67d-148">Select a File connection manager in the list or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="1f67d-149">**Rubriques connexes :** [Gestionnaire de connexions de fichiers](connection-manager/file-connection-manager.md), [Éditeur du gestionnaire de connexions de fichiers](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="1f67d-149">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="messagesourcetype--variable"></a><span data-ttu-id="1f67d-150">MessageSourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="1f67d-150">MessageSourceType = Variable</span></span>  
 <span data-ttu-id="1f67d-151">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="1f67d-151">**MessageSource**</span></span>  
 <span data-ttu-id="1f67d-152">Sélectionnez une variable dans la liste, ou cliquez sur \<**New variable...**> pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="1f67d-152">Select a variable in the list or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="1f67d-153">**Rubriques connexes :** [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Ajouter une variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="1f67d-153">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f67d-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f67d-154">See Also</span></span>  
 <span data-ttu-id="1f67d-155">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1f67d-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="1f67d-156">[Éditeur de tâche Envoyer un message &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="1f67d-156">[Send Mail Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="1f67d-157">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="1f67d-157">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
