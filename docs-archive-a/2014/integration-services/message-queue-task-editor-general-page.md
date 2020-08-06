---
title: Éditeur de tâche MSMQ (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.general.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 09368b18-37a5-4321-a173-7cfe5d42d2a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dcec75f3a4dd85efb7c97226c592d6b1e1bb26ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614732"
---
# <a name="message-queue-task-editor-general-page"></a><span data-ttu-id="63f2a-102">Éditeur de tâche MSMQ (page Général)</span><span class="sxs-lookup"><span data-stu-id="63f2a-102">Message Queue Task Editor (General Page)</span></span>
  <span data-ttu-id="63f2a-103">Utilisez la page **Général** de la boîte de dialogue **Éditeur de tâche MSMQ** pour nommer et décrire la tâche MSMQ, pour spécifier le format du message et indiquer si la tâche envoie ou reçoit des messages.</span><span class="sxs-lookup"><span data-stu-id="63f2a-103">Use the **General page** of the **Message Queue Task Editor** dialog box to name and describe the Message Queue task, to specify the message format, and to indicate whether the task sends or receives messages.</span></span>  
  
 <span data-ttu-id="63f2a-104">Pour en savoir plus sur cette tâche, consultez [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="63f2a-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="63f2a-105">Options</span><span class="sxs-lookup"><span data-stu-id="63f2a-105">Options</span></span>  
 <span data-ttu-id="63f2a-106">**Nom**</span><span class="sxs-lookup"><span data-stu-id="63f2a-106">**Name**</span></span>  
 <span data-ttu-id="63f2a-107">Attribuez un nom unique à la tâche MSMQ.</span><span class="sxs-lookup"><span data-stu-id="63f2a-107">Provide a unique name for the Message Queue task.</span></span> <span data-ttu-id="63f2a-108">Ce nom sert d'étiquette à l'icône de la tâche.</span><span class="sxs-lookup"><span data-stu-id="63f2a-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63f2a-109">Les noms de tâche doivent être uniques dans un package.</span><span class="sxs-lookup"><span data-stu-id="63f2a-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="63f2a-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="63f2a-110">**Description**</span></span>  
 <span data-ttu-id="63f2a-111">Tapez la description de la tâche MSMQ.</span><span class="sxs-lookup"><span data-stu-id="63f2a-111">Type a description of the Message Queue task.</span></span>  
  
 <span data-ttu-id="63f2a-112">**Use2000Format**</span><span class="sxs-lookup"><span data-stu-id="63f2a-112">**Use2000Format**</span></span>  
 <span data-ttu-id="63f2a-113">Indiquez si le format 2000 de Message Queuing (ou MSMQ) doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="63f2a-113">Indicate whether to use the 2000 format of Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="63f2a-114">Par défaut, il s’agit de `False`.</span><span class="sxs-lookup"><span data-stu-id="63f2a-114">The default is `False`.</span></span>  
  
 <span data-ttu-id="63f2a-115">**MSMQConnection**</span><span class="sxs-lookup"><span data-stu-id="63f2a-115">**MSMQConnection**</span></span>  
 <span data-ttu-id="63f2a-116">Sélectionnez un gestionnaire de connexions MSMQ existant ou cliquez sur \<**New connection...**> pour en créer un.</span><span class="sxs-lookup"><span data-stu-id="63f2a-116">Select an existing MSMQ connection manager or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="63f2a-117">**Rubriques connexes :** [Gestionnaire de connexions MSMQ](connection-manager/msmq-connection-manager.md), [Éditeur du gestionnaire de connexions MSMQ](../../2014/integration-services/msmq-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="63f2a-117">**Related Topics**: [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md), [MSMQ Connection Manager Editor](../../2014/integration-services/msmq-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="63f2a-118">**Message**</span><span class="sxs-lookup"><span data-stu-id="63f2a-118">**Message**</span></span>  
 <span data-ttu-id="63f2a-119">Spécifiez si la tâche MSMQ envoie ou reçoit des messages.</span><span class="sxs-lookup"><span data-stu-id="63f2a-119">Specify whether the Message Queue task sends or receive messages.</span></span> <span data-ttu-id="63f2a-120">Si vous sélectionnez l’option **Envoyer un message**, la page Envoyer est répertoriée dans le volet gauche de la boîte de dialogue ; si vous sélectionnez l’option **Recevoir un message**, la page Recevoir est répertoriée.</span><span class="sxs-lookup"><span data-stu-id="63f2a-120">If you select **Send message**, the Send page is listed in the left pane of the dialog box; if you select **Receive message**, the Receive page is listed.</span></span> <span data-ttu-id="63f2a-121">Par défaut, cette valeur est définie sur **Envoyer un message**.</span><span class="sxs-lookup"><span data-stu-id="63f2a-121">By default, this value is set to **Send message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f2a-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="63f2a-122">See Also</span></span>  
 <span data-ttu-id="63f2a-123">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="63f2a-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="63f2a-124">[Éditeur de tâche MSMQ &#40;page de réception&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="63f2a-124">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 <span data-ttu-id="63f2a-125">[Éditeur de tâche MSMQ &#40;page envoyer&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="63f2a-125">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 [<span data-ttu-id="63f2a-126">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="63f2a-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
