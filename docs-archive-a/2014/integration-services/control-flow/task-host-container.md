---
title: Conteneur d’hôte de tâche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.taskhostcontainer.f1
helpviewer_keywords:
- containers [Integration Services], Task Host
- Task Host container
ms.assetid: 7394a2c2-1b07-427d-b94a-9792e7783d35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4429d564cea0f08d5c2408199a8f1837b38389b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613077"
---
# <a name="task-host-container"></a><span data-ttu-id="de09f-102">conteneur d'hôte de tâche</span><span class="sxs-lookup"><span data-stu-id="de09f-102">Task Host Container</span></span>
  <span data-ttu-id="de09f-103">Le conteneur d'hôte de tâche encapsule une seule tâche.</span><span class="sxs-lookup"><span data-stu-id="de09f-103">The task host container encapsulates a single task.</span></span> <span data-ttu-id="de09f-104">Dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , l'hôte de tâche n'est pas configuré séparément ; il est configuré lorsque vous définissez les propriétés de la tâche qu'il encapsule.</span><span class="sxs-lookup"><span data-stu-id="de09f-104">In [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the task host is not configured separately; instead, it is configured when you set the properties of the task it encapsulates.</span></span> <span data-ttu-id="de09f-105">Pour plus d'informations sur les tâches encapsulées par les conteneurs d’hôte de tâche, consultez [Tâches Integration Services](integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="de09f-105">For more information about the tasks that the task host containers encapsulate, see [Integration Services Tasks](integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="de09f-106">Ce conteneur étend l'utilisation des variables et des gestionnaires d'événements au niveau de la tâche.</span><span class="sxs-lookup"><span data-stu-id="de09f-106">This container extends the use of variables and event handlers to the task level.</span></span> <span data-ttu-id="de09f-107">Pour plus d’informations, consultez [Gestionnaires d’événements Integration Services &#40;SSIS&#41; ](../integration-services-ssis-event-handlers.md) et [Variables Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="de09f-107">For more information, see [Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) and [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md).</span></span>  
  
## <a name="configuration-of-the-task-host"></a><span data-ttu-id="de09f-108">Configuration de l'hôte de tâche</span><span class="sxs-lookup"><span data-stu-id="de09f-108">Configuration of the Task Host</span></span>  
 <span data-ttu-id="de09f-109">Vous pouvez définir les propriétés dans la fenêtre **Propriétés** de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="de09f-109">You can set properties in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="de09f-110">Pour plus d’informations sur la définition de ces propriétés dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], consultez [Définir les propriétés d’une tâche ou d’un conteneur](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="de09f-110">For information about setting these properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
 <span data-ttu-id="de09f-111">Pour plus d’informations sur la définition par programmation de ces propriétés, consultez <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="de09f-111">For information about programmatically setting these properties, see <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="de09f-112">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="de09f-112">Related Tasks</span></span>  
  
-   [<span data-ttu-id="de09f-113">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="de09f-113">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="de09f-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de09f-114">See Also</span></span>  
 [<span data-ttu-id="de09f-115">Conteneurs Integration Services</span><span class="sxs-lookup"><span data-stu-id="de09f-115">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
