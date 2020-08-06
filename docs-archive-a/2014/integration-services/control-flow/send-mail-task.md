---
title: Envoyer un message, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.f1
helpviewer_keywords:
- mail [Integration Services]
- Send Mail task
- e-mail [Integration Services]
- messages [Integration Services]
- sending messages
ms.assetid: fe0b7cbc-fe8e-4fe2-95b4-2953efff5869
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c93723f3c443705acc14226ce07f456da4d5a884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602249"
---
# <a name="send-mail-task"></a><span data-ttu-id="5054c-102">tache Envoyer un message</span><span class="sxs-lookup"><span data-stu-id="5054c-102">Send Mail Task</span></span>
  <span data-ttu-id="5054c-103">La tâche Envoyer un message envoie un message électronique.</span><span class="sxs-lookup"><span data-stu-id="5054c-103">The Send Mail task sends an e-mail message.</span></span> <span data-ttu-id="5054c-104">La tâche Envoyer un message permet à un package d'envoyer des messages en cas de réussite ou d'échec des tâches du flux de travail du package, ou d'envoyer des messages en réponse à un événement déclenché par le package au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="5054c-104">By using the Send Mail task, a package can send messages if tasks in the package workflow succeed or fail, or send messages in response to an event that the package raises at run time.</span></span> <span data-ttu-id="5054c-105">Par exemple, la tâche peut notifier à un administrateur de base de données la réussite ou l'échec de la tâche de sauvegarde de base de données.</span><span class="sxs-lookup"><span data-stu-id="5054c-105">For example, the task can notify a database administrator about the success or failure of the Backup Database task.</span></span>  
  
 <span data-ttu-id="5054c-106">Vous pouvez configurer la tâche Envoyer un message comme suit :</span><span class="sxs-lookup"><span data-stu-id="5054c-106">You can configure the Send Mail task in the following ways:</span></span>  
  
-   <span data-ttu-id="5054c-107">Fournissez le texte du message électronique.</span><span class="sxs-lookup"><span data-stu-id="5054c-107">Provide the message text for the e-mail message.</span></span>  
  
-   <span data-ttu-id="5054c-108">Indiquez une ligne d'objet pour le message électronique.</span><span class="sxs-lookup"><span data-stu-id="5054c-108">Provide a subject line for the e-mail message.</span></span>  
  
-   <span data-ttu-id="5054c-109">Définissez le niveau de priorité du message.</span><span class="sxs-lookup"><span data-stu-id="5054c-109">Set the priority level of the message.</span></span> <span data-ttu-id="5054c-110">La tâche prend en charge trois niveaux de priorité : normale, basse et haute.</span><span class="sxs-lookup"><span data-stu-id="5054c-110">The task supports three priority levels: normal, low, and high.</span></span>  
  
-   <span data-ttu-id="5054c-111">Indiquez les destinataires dans les lignes À, Cc et Cci.</span><span class="sxs-lookup"><span data-stu-id="5054c-111">Specify the recipients on the To, Cc, and Bcc lines.</span></span> <span data-ttu-id="5054c-112">Si la tâche spécifie plusieurs destinataires, ceux-ci sont séparés par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="5054c-112">If the task specifies multiple recipients, they are separated by semicolons.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5054c-113">Les lignes À, Cc et Cci sont limitées chacune à 256 caractères conformément aux normes Internet.</span><span class="sxs-lookup"><span data-stu-id="5054c-113">The To, Cc, and Bcc lines are limited to 256 characters each in accordance with Internet standards.</span></span>  
  
-   <span data-ttu-id="5054c-114">Incluez les pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="5054c-114">Include attachments.</span></span> <span data-ttu-id="5054c-115">Si la tâche spécifie plusieurs pièces jointes, celles-ci sont séparées par la barre verticale ( | ).</span><span class="sxs-lookup"><span data-stu-id="5054c-115">If the task specifies multiple attachments, they are separated by the pipe (|) character.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5054c-116">Si un fichier de pièce jointe n'existe pas lors de l'exécution du package, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="5054c-116">If an attachment file does not exist when the package runs, an error occurs.</span></span>  
  
-   <span data-ttu-id="5054c-117">Spécifiez le gestionnaire de connexions SMTP à utiliser.</span><span class="sxs-lookup"><span data-stu-id="5054c-117">Specify the SMTP connection manager to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5054c-118">Le gestionnaire de connexions SMTP prend en charge uniquement l'authentification anonyme et l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="5054c-118">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="5054c-119">Il ne prend pas en charge l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="5054c-119">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="5054c-120">Le texte du message peut être une chaîne indiquée par vos soins, ou bien une connexion à un fichier, ou le nom d'une variable qui contient le texte.</span><span class="sxs-lookup"><span data-stu-id="5054c-120">The message text can be a string that you provide, a connection to a file that contains the text, or the name of a variable that contains the text.</span></span> <span data-ttu-id="5054c-121">La tâche utilise un gestionnaire de connexions de fichiers pour se connecter à un fichier.</span><span class="sxs-lookup"><span data-stu-id="5054c-121">The task uses a File connection manager to connect to a file.</span></span> <span data-ttu-id="5054c-122">Pour plus d'informations, consultez [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5054c-122">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="5054c-123">La tâche utilise un gestionnaire de connexions SMTP pour se connecter à un serveur de messagerie.</span><span class="sxs-lookup"><span data-stu-id="5054c-123">The task uses an SMTP connection manager to connect to a mail server.</span></span> <span data-ttu-id="5054c-124">Pour plus d’informations, consultez [Gestionnaire de connexions SMTP](../connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5054c-124">For more information, see [SMTP Connection Manager](../connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="custom-logging-messages-available-on-the-send-mail-task"></a><span data-ttu-id="5054c-125">Messages de journalisation personnalisés disponibles dans la tâche Envoyer un message</span><span class="sxs-lookup"><span data-stu-id="5054c-125">Custom Logging Messages Available on the Send Mail Task</span></span>  
 <span data-ttu-id="5054c-126">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche Envoyer un message.</span><span class="sxs-lookup"><span data-stu-id="5054c-126">The following table lists the custom log entries for the Send Mail task.</span></span> <span data-ttu-id="5054c-127">Pour plus d’informations, consultez [Journalisation d’Integration Services &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) et [Messages personnalisés pour la journalisation](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="5054c-127">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="5054c-128">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="5054c-128">Log entry</span></span>|<span data-ttu-id="5054c-129">Description</span><span class="sxs-lookup"><span data-stu-id="5054c-129">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="5054c-130">Indique que la tâche a commencé l'envoi d'un message électronique.</span><span class="sxs-lookup"><span data-stu-id="5054c-130">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="5054c-131">Indique que la tâche a terminé l'envoi d'un message électronique.</span><span class="sxs-lookup"><span data-stu-id="5054c-131">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="5054c-132">Fournit des informations détaillées concernant la tâche.</span><span class="sxs-lookup"><span data-stu-id="5054c-132">Provides descriptive information about the task.</span></span>|  
  
## <a name="configuring-the-send-mail-task"></a><span data-ttu-id="5054c-133">Configuration de la tâche Envoyer un message</span><span class="sxs-lookup"><span data-stu-id="5054c-133">Configuring the Send Mail Task</span></span>  
 <span data-ttu-id="5054c-134">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="5054c-134">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="5054c-135">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="5054c-135">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="5054c-136">Éditeur de tâche Envoyer un message &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="5054c-136">Send Mail Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="5054c-137">Éditeur de tâche Envoyer un message &#40;page Courrier&#41;</span><span class="sxs-lookup"><span data-stu-id="5054c-137">Send Mail Task Editor &#40;Mail Page&#41;</span></span>](../send-mail-task-editor-mail-page.md)  
  
-   [<span data-ttu-id="5054c-138">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="5054c-138">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="5054c-139">Pour plus d'informations sur la définition par programmation de ces propriétés, cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="5054c-139">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.SendMailTask.SendMailTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="5054c-140">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="5054c-140">Related Tasks</span></span>  
 <span data-ttu-id="5054c-141">Pour obtenir des informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur [Définir les propriétés d’une tâche ou d’un conteneur](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="5054c-141">For information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="5054c-142">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="5054c-142">Related Content</span></span>  
  
-   <span data-ttu-id="5054c-143">Article technique [Procédure d'envoi de courrier électronique avec notification de remise en C#](https://go.microsoft.com/fwlink/?LinkId=237625)(Procédure d’envoi d’e-mail avec notification de remise en C#) sur shareourideas.com</span><span class="sxs-lookup"><span data-stu-id="5054c-143">Technical article, [How to send email with delivery notification in C#](https://go.microsoft.com/fwlink/?LinkId=237625), on shareourideas.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5054c-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5054c-144">See Also</span></span>  
 <span data-ttu-id="5054c-145">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="5054c-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="5054c-146">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="5054c-146">Control Flow</span></span>](control-flow.md)  
  
  
