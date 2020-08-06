---
title: Gestionnaire de connexions MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], message queues
- connection managers [Integration Services], MSMQ
- MSMQ connection manager
- message queue connections [Integration Services]
ms.assetid: a86900e2-450e-479f-b207-e1b02361d395
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c51866eeef281f6587bf281461e4faa2278308d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613092"
---
# <a name="msmq-connection-manager"></a><span data-ttu-id="9e6ad-102">Gestionnaire de connexions MSMQ</span><span class="sxs-lookup"><span data-stu-id="9e6ad-102">MSMQ Connection Manager</span></span>
  <span data-ttu-id="9e6ad-103">Un gestionnaire de connexions MSMQ permet à un package de se connecter à une file d'attente de messages qui utilise Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="9e6ad-103">An MSMQ connection manager enables a package to connect to a message queue that uses Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="9e6ad-104">La tâche MSMQ incluse dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilise un gestionnaire de connexions MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-104">The Message Queue task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an MSMQ connection manager.</span></span>  
  
 <span data-ttu-id="9e6ad-105">Lorsque vous ajoutez un gestionnaire de connexions MSMQ à un package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera résolu en une connexion MSMQ au moment de l'exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la collection `Connections` sur le package.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-105">When you add an MSMQ connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an MSMQ connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="9e6ad-106">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `MSMQ`.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-106">The `ConnectionManagerType` property of the connection manager is set to `MSMQ`.</span></span>  
  
 <span data-ttu-id="9e6ad-107">Vous pouvez configurer le gestionnaire de connexions MSMQ de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="9e6ad-107">You can configure an MSMQ connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="9e6ad-108">Spécifiez une chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-108">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="9e6ad-109">Spécifiez le chemin d'accès à la file d'attente de messages à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-109">Provide the path of the message queue to connect to.</span></span>  
  
 <span data-ttu-id="9e6ad-110">Le format du chemin dépend du type de file d'attente, comme le montre le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-110">The format of the path depends on the type of queue, as shown in the following table.</span></span>  
  
|<span data-ttu-id="9e6ad-111">Type de file d'attente</span><span class="sxs-lookup"><span data-stu-id="9e6ad-111">Queue type</span></span>|<span data-ttu-id="9e6ad-112">Exemple de chemin d'accès</span><span class="sxs-lookup"><span data-stu-id="9e6ad-112">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="9e6ad-113">Public</span><span class="sxs-lookup"><span data-stu-id="9e6ad-113">Public</span></span>|<span data-ttu-id="9e6ad-114">\<computer name>\\<nom_file_d’attente\></span><span class="sxs-lookup"><span data-stu-id="9e6ad-114">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="9e6ad-115">Privé</span><span class="sxs-lookup"><span data-stu-id="9e6ad-115">Private</span></span>|<span data-ttu-id="9e6ad-116">\<computer name>\Private$\\<nom_file_d’attente\></span><span class="sxs-lookup"><span data-stu-id="9e6ad-116">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="9e6ad-117">Vous pouvez utiliser un point (.) pour représenter l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-117">You can use a period (.) to represent the local computer.</span></span>  
  
## <a name="configuration-of-the-msmq-connection-manager"></a><span data-ttu-id="9e6ad-118">Configuration du gestionnaire de connexions MSMQ</span><span class="sxs-lookup"><span data-stu-id="9e6ad-118">Configuration of the MSMQ Connection Manager</span></span>  
 <span data-ttu-id="9e6ad-119">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="9e6ad-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="9e6ad-120">Pour plus d’informations sur les propriétés que vous pouvez définir dans le Concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Éditeur du gestionnaire de connexions MSMQ](../msmq-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="9e6ad-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [MSMQ Connection Manager Editor](../msmq-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="9e6ad-121">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="9e6ad-121">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6ad-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9e6ad-122">See Also</span></span>  
 <span data-ttu-id="9e6ad-123">[Tâche MSMQ](../control-flow/message-queue-task.md) </span><span class="sxs-lookup"><span data-stu-id="9e6ad-123">[Message Queue Task](../control-flow/message-queue-task.md) </span></span>  
 [<span data-ttu-id="9e6ad-124">Connexions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="9e6ad-124">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
