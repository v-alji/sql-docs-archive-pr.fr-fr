---
title: Onglet gestionnaires d’événements | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.eventhandlerwindow.f1
ms.assetid: 94fc8916-8032-490c-b9d5-ded8b6217e49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5f25a9b0d602a3189feab797b7ef9c333decabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610764"
---
# <a name="event-handlers-tab"></a><span data-ttu-id="30420-102">Onglet Gestionnaires d'événements</span><span class="sxs-lookup"><span data-stu-id="30420-102">Event Handlers Tab</span></span>
  <span data-ttu-id="30420-103">Utilisez l’onglet **Gestionnaires d’événements** du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] pour créer un flux de contrôle dans un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30420-103">Use the **Event Handlers** tab of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to build a control flow in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="30420-104">Un gestionnaire d'événements est exécuté en réponse à un événement déclenché par le package ou par une tâche ou un conteneur du package.</span><span class="sxs-lookup"><span data-stu-id="30420-104">An event handler runs in response to an event raised by the package or by a task or container in the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="30420-105">Options</span><span class="sxs-lookup"><span data-stu-id="30420-105">Options</span></span>  
 <span data-ttu-id="30420-106">**Exécutable**</span><span class="sxs-lookup"><span data-stu-id="30420-106">**Executable**</span></span>  
 <span data-ttu-id="30420-107">Sélectionnez l'exécutable pour lequel vous souhaitez créer un gestionnaire d'événements.</span><span class="sxs-lookup"><span data-stu-id="30420-107">Select the executable for which you want to build an event handler.</span></span> <span data-ttu-id="30420-108">L'exécutable peut être un package ou une tâche ou des conteneurs du package.</span><span class="sxs-lookup"><span data-stu-id="30420-108">The executable can be the package, or a task or containers in the package.</span></span>  
  
 <span data-ttu-id="30420-109">**Gestionnaire d’événements**</span><span class="sxs-lookup"><span data-stu-id="30420-109">**Event handler**</span></span>  
 <span data-ttu-id="30420-110">Sélectionnez un type de gestionnaire d'événements.</span><span class="sxs-lookup"><span data-stu-id="30420-110">Select a type of event handler.</span></span> <span data-ttu-id="30420-111">Créez le gestionnaire d’événements en faisant glisser les éléments à partir de la **Boîte à outils**.</span><span class="sxs-lookup"><span data-stu-id="30420-111">Create the event handler by dragging items from the **Toolbox**.</span></span>  
  
 <span data-ttu-id="30420-112">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="30420-112">**Delete**</span></span>  
 <span data-ttu-id="30420-113">Sélectionnez un gestionnaire d’événements et supprimez-le du package en cliquant sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="30420-113">Select an event handler, and remove it from the package by clicking **Delete**.</span></span>  
  
 <span data-ttu-id="30420-114">**Cliquez ici pour créer un \<event handler name> pour l’exécutable \<executable name>**</span><span class="sxs-lookup"><span data-stu-id="30420-114">**Click here to create an \<event handler name> for the executable \<executable name>**</span></span>  
 <span data-ttu-id="30420-115">Cliquez pour créer le gestionnaire d'événements.</span><span class="sxs-lookup"><span data-stu-id="30420-115">Click to create the event handler.</span></span>  
  
 <span data-ttu-id="30420-116">Pour créer le flux de contrôle, faites glisser les objets graphiques qui représentent les tâches et les conteneurs [!INCLUDE[ssIS](../includes/ssis-md.md)] de la **Boîte à outils** vers l’onglet **Gestionnaires d’événements** , puis connectez-les en utilisant des contraintes de priorité pour définir leur ordre d’exécution.</span><span class="sxs-lookup"><span data-stu-id="30420-116">Create the control flow by dragging graphical objects that represent [!INCLUDE[ssIS](../includes/ssis-md.md)] tasks and containers from the **Toolbox** to the design surface of the **Event Handlers** tab, and then connecting the objects by using precedence constraints to define the sequence in which they run.</span></span>  
  
 <span data-ttu-id="30420-117">Par ailleurs, pour ajouter des annotations, cliquez avec le bouton droit dans l’aire de conception puis, dans le menu qui s’affiche, cliquez sur **Ajouter une annotation**.</span><span class="sxs-lookup"><span data-stu-id="30420-117">Additionally, to add annotations, right-click the design surface, and then on the menu, click **Add Annotation**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30420-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="30420-118">See Also</span></span>  
 <span data-ttu-id="30420-119">[Gestionnaires d’événements Integration Services &#40;SSIS&#41](integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="30420-119">[Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="30420-120">[Flux de contrôle](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="30420-120">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="30420-121">[Concepteur SSIS](ssis-designer.md) </span><span class="sxs-lookup"><span data-stu-id="30420-121">[SSIS Designer](ssis-designer.md) </span></span>  
 [<span data-ttu-id="30420-122">Gestionnaires d’événements Integration Services &#40;SSIS&#41</span><span class="sxs-lookup"><span data-stu-id="30420-122">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
