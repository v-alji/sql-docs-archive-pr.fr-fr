---
title: Ajouter un gestionnaire d’événements à un package | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- event handlers [Integration Services], creating
ms.assetid: 5e56885d-8658-480a-bed9-3f2f8003fd78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 007d81a395e06ac5a97210cd3e3ed6eea91aee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604709"
---
# <a name="add-an-event-handler-to-a-package"></a><span data-ttu-id="8a6d0-102">Ajouter un gestionnaire d'événements à un package</span><span class="sxs-lookup"><span data-stu-id="8a6d0-102">Add an Event Handler to a Package</span></span>
  <span data-ttu-id="8a6d0-103">Lors de l'exécution, les conteneurs et les tâches déclenchent des événements.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-103">At run time, containers and tasks raise events.</span></span> <span data-ttu-id="8a6d0-104">Vous pouvez créer des gestionnaires d'événements personnalisés qui répondent à ces événements en exécutant un flux de travail.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-104">You can create custom event handlers that respond to these events by running a workflow when the event is raised.</span></span> <span data-ttu-id="8a6d0-105">Vous pouvez ainsi créer un gestionnaire d'événements qui envoie un message électronique lorsqu'une tâche échoue.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-105">For example, you can create an event handler that sends an e-mail message when a task fails.</span></span>  
  
 <span data-ttu-id="8a6d0-106">Un gestionnaire d'événements est similaire à un package.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-106">An event handler is similar to a package.</span></span> <span data-ttu-id="8a6d0-107">Comme un package, il peut définir la portée des variables et inclure un flux de contrôle et des flux de données facultatifs.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-107">Like a package, an event handler can provide scope for variables, and includes a control flow and optional data flows.</span></span> <span data-ttu-id="8a6d0-108">Vous pouvez créer des gestionnaires d'événements pour les packages, le conteneur de boucles Foreach, le conteneur de boucles For, le conteneur Sequence et toutes les tâches.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-108">You can build event handlers for packages, the Foreach Loop container, the For Loop container, the Sequence container, and all tasks.</span></span>  
  
 <span data-ttu-id="8a6d0-109">Vous pouvez pour cela utiliser l’aire de conception de l’onglet **Gestionnaires d’événements** du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8a6d0-109">You create event handlers by using the design surface of the **Event Handlers** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="8a6d0-110">Quand l’onglet **Gestionnaires d’événements** est actif, les nœuds **Éléments de flux de contrôle** et **Tâches du plan de maintenance** de la Boîte à outils du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] contiennent la tâche et les conteneurs permettant de créer le flux de contrôle dans le gestionnaire d’événements.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-110">When the **Event Handlers** tab is active, the **Control Flow Items** and **Maintenance Plan Tasks** nodes of the Toolbox in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer contain the task and containers for building the control flow in the event handler.</span></span> <span data-ttu-id="8a6d0-111">Les nœuds **Sources de flux de données**, **Transformations**et **Destinations du flux de données** contiennent les sources de données, les transformations et les destinations permettant de créer les flux de données dans le gestionnaire d’événements.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-111">The **Data Flow Sources**, **Transformations**, **and Data Flow Destinations** nodes contain the data sources, transformations, and destinations for building the data flows in the event handler.</span></span> <span data-ttu-id="8a6d0-112">Pour plus d’informations, consultez [Flux de contrôle](control-flow/control-flow.md) et [Flux de données](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8a6d0-112">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="8a6d0-113">L’onglet **Gestionnaires d’événements** contient aussi une zone **Gestionnaires de connexions** dans laquelle vous pouvez créer et modifier les gestionnaires de connexions utilisés par les gestionnaires d’événements pour se connecter aux serveurs et aux sources de données.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-113">The **Event Handlers** tab also includes the **Connections** Managers area where you can create and modify the connection managers that event handlers use to connect to servers and data sources.</span></span> <span data-ttu-id="8a6d0-114">Pour plus d’informations, consultez [Créer des gestionnaires de connexions](../../2014/integration-services/create-connection-managers.md).</span><span class="sxs-lookup"><span data-stu-id="8a6d0-114">For more information, see [Create Connection Managers](../../2014/integration-services/create-connection-managers.md).</span></span>  
  
### <a name="to-create-an-event-handler"></a><span data-ttu-id="8a6d0-115">Pour créer un gestionnaire d'événements</span><span class="sxs-lookup"><span data-stu-id="8a6d0-115">To create an event handler</span></span>  
  
1.  <span data-ttu-id="8a6d0-116">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8a6d0-117">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8a6d0-118">Cliquez sur l’onglet **Gestionnaires d’événements** .</span><span class="sxs-lookup"><span data-stu-id="8a6d0-118">Click the **Event Handlers** tab.</span></span>  
  
     <span data-ttu-id="8a6d0-119">![Capture d’écran de l’aire de conception avec le gestionnaire d’événements](media/eventhandlers.gif "Capture d’écran de l’aire de conception avec le gestionnaire d’événements")</span><span class="sxs-lookup"><span data-stu-id="8a6d0-119">![Screenshot of design surface with event handler](media/eventhandlers.gif "Screenshot of design surface with event handler")</span></span>  
  
     <span data-ttu-id="8a6d0-120">La création du flux de contrôle et des flux de données dans le gestionnaire d'événements est identique à la création du flux de contrôle et des flux de données dans un package.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-120">Creating the control flow and data flows in an event handler is similar to creating the control flow and data flows in a package.</span></span> <span data-ttu-id="8a6d0-121">Pour plus d’informations, consultez [Flux de contrôle](control-flow/control-flow.md) et [Flux de données](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8a6d0-121">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
4.  <span data-ttu-id="8a6d0-122">Dans la liste **Exécutable** , sélectionnez l’exécutable pour lequel vous voulez créer un gestionnaire d’événements.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-122">In the **Executable** list, select the executable for which you want to create an event handler.</span></span>  
  
5.  <span data-ttu-id="8a6d0-123">Dans la liste **Gestionnaire d’événements** , sélectionnez le gestionnaire d’événements que vous voulez créer.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-123">In the **Event handler** list, select the event handler you want to build.</span></span>  
  
6.  <span data-ttu-id="8a6d0-124">Cliquez sur le lien situé dans l’aire de conception de l’onglet **Gestionnaire d’événements** .</span><span class="sxs-lookup"><span data-stu-id="8a6d0-124">Click the link on the design surface of the **Event Handler** tab.</span></span>  
  
7.  <span data-ttu-id="8a6d0-125">Ajoutez des éléments de flux de contrôle au gestionnaire d'événements et connectez ces éléments à l'aide d'une contrainte de priorité, en faisant glisser la contrainte d'un élément de flux de contrôle à l'autre.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-125">Add control flow items to the event handler, and connect items using a precedence constraint by dragging the constraint from one control flow item to another.</span></span> <span data-ttu-id="8a6d0-126">Pour plus d’informations, consultez [Control Flow](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8a6d0-126">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
8.  <span data-ttu-id="8a6d0-127">Si vous le souhaitez, vous pouvez ajouter une tâche de flux de données puis, dans l’aire de conception de l’onglet **Flux de données** , créer un flux de données pour le gestionnaire d’événements.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-127">Optionally, add a Data Flow task, and on the design surface of the **Data Flow** tab, create a data flow for the event handler.</span></span> <span data-ttu-id="8a6d0-128">Pour en savoir plus, voir [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8a6d0-128">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
9. <span data-ttu-id="8a6d0-129">Dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés** pour enregistrer le package.</span><span class="sxs-lookup"><span data-stu-id="8a6d0-129">On the **File** menu, click **Save Selected Items** to save the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a6d0-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a6d0-130">See Also</span></span>  
 <span data-ttu-id="8a6d0-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="8a6d0-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span></span>  
 [<span data-ttu-id="8a6d0-132">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8a6d0-132">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
