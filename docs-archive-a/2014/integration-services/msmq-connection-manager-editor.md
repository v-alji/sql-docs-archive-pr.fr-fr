---
title: Éditeur du gestionnaire de connexions MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msmqconnectionmanager.f1
helpviewer_keywords:
- MSMQ Connection Manager Editor
ms.assetid: ef842cb4-82da-4550-85fe-9bedbc1e77c7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41d4231ce121d596c8d818485eccf5ddf6127470
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601558"
---
# <a name="msmq-connection-manager-editor"></a><span data-ttu-id="b69c5-102">Éditeur du gestionnaire de connexions MSMQ</span><span class="sxs-lookup"><span data-stu-id="b69c5-102">MSMQ Connection Manager Editor</span></span>
  <span data-ttu-id="b69c5-103">La boîte de dialogue **Gestionnaire de connexions MSMQ** permet de spécifier le chemin d’une file d’attente de messages MSMQ (Message Queuing).</span><span class="sxs-lookup"><span data-stu-id="b69c5-103">Use the **MSMQ Connection Manager** dialog box to specify the path to a Message Queuing (also known as MSMQ) message queue.</span></span>  
  
 <span data-ttu-id="b69c5-104">Pour en savoir plus sur le gestionnaire de connexions MSMQ, consultez [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b69c5-104">To learn more about the MSMQ connection manager, see [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b69c5-105">Le gestionnaire de connexions MSMQ prend en charge les files d'attente privées et publiques locales et les files d'attente publiques distantes.</span><span class="sxs-lookup"><span data-stu-id="b69c5-105">The MSMQ connection manager supports local public and private queues and remote public queues.</span></span> <span data-ttu-id="b69c5-106">Il ne prend pas en charge les files d'attente privées distantes.</span><span class="sxs-lookup"><span data-stu-id="b69c5-106">It does not support remote private queues.</span></span> <span data-ttu-id="b69c5-107">Pour une solution de contournement qui utilise la tâche de script, consultez [Envoi vers une file d'attente de messages privée distante à l'aide de la tâche de script](control-flow/script-task.md).</span><span class="sxs-lookup"><span data-stu-id="b69c5-107">For a workaround that uses the Script Task, see [Sending to a Remote Private Message Queue with the Script Task](control-flow/script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b69c5-108">Options</span><span class="sxs-lookup"><span data-stu-id="b69c5-108">Options</span></span>  
 <span data-ttu-id="b69c5-109">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b69c5-109">**Name**</span></span>  
 <span data-ttu-id="b69c5-110">Fournissez un nom unique pour le gestionnaire de connexions MSMQ dans le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="b69c5-110">Provide a unique name for the MSMQ connection manager in the workflow.</span></span> <span data-ttu-id="b69c5-111">Le nom fourni sera affiché dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b69c5-111">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="b69c5-112">**Description**</span><span class="sxs-lookup"><span data-stu-id="b69c5-112">**Description**</span></span>  
 <span data-ttu-id="b69c5-113">Décrivez le gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="b69c5-113">Describe the connection manager.</span></span> <span data-ttu-id="b69c5-114">Il est recommandé d'indiquer ici l'usage auquel le gestionnaire de connexions est destiné, de sorte que les packages soient correctement documentés et plus faciles à gérer.</span><span class="sxs-lookup"><span data-stu-id="b69c5-114">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="b69c5-115">**Chemin d’accès**</span><span class="sxs-lookup"><span data-stu-id="b69c5-115">**Path**</span></span>  
 <span data-ttu-id="b69c5-116">Tapez le chemin d'accès complet de la file d'attente de messages.</span><span class="sxs-lookup"><span data-stu-id="b69c5-116">Type the complete path of the message queue.</span></span> <span data-ttu-id="b69c5-117">Le format du chemin d'accès dépend du type de file d'attente.</span><span class="sxs-lookup"><span data-stu-id="b69c5-117">The format of the path depends on the type of queue.</span></span>  
  
|<span data-ttu-id="b69c5-118">Type de file d'attente</span><span class="sxs-lookup"><span data-stu-id="b69c5-118">Queue type</span></span>|<span data-ttu-id="b69c5-119">Exemple de chemin d'accès</span><span class="sxs-lookup"><span data-stu-id="b69c5-119">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="b69c5-120">Public</span><span class="sxs-lookup"><span data-stu-id="b69c5-120">Public</span></span>|<span data-ttu-id="b69c5-121">\<computer name>\\<nom_file_d’attente\></span><span class="sxs-lookup"><span data-stu-id="b69c5-121">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="b69c5-122">Privé</span><span class="sxs-lookup"><span data-stu-id="b69c5-122">Private</span></span>|<span data-ttu-id="b69c5-123">\<computer name>\Private$\\<nom_file_d’attente\></span><span class="sxs-lookup"><span data-stu-id="b69c5-123">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="b69c5-124">Vous pouvez utiliser "." pour représenter l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="b69c5-124">You can use "." to represent the local computer.</span></span>  
  
 <span data-ttu-id="b69c5-125">**Test**</span><span class="sxs-lookup"><span data-stu-id="b69c5-125">**Test**</span></span>  
 <span data-ttu-id="b69c5-126">Après avoir configuré le gestionnaire de connexions MSMQ, vérifiez si la connexion est opérationnelle en cliquant sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="b69c5-126">After configuring the MSMQ connection manager, confirm that the connection is viable by clicking **Test**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b69c5-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b69c5-127">See Also</span></span>  
 [<span data-ttu-id="b69c5-128">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="b69c5-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
