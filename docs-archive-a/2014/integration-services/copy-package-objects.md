---
title: Copier des objets de packages | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- control flow [Integration Services], copying objects
- copying package objects [Integration Services]
- data flow [Integration Services], copying objects
- connection managers [Integration Services], copying
ms.assetid: 99b85e5c-d6bd-4e7c-afe4-51f6ce151c2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3219f0023c9a28ed270adeb6fd2b795e3459c3e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602949"
---
# <a name="copy-package-objects"></a><span data-ttu-id="e9e0f-102">Copier des objets de packages</span><span class="sxs-lookup"><span data-stu-id="e9e0f-102">Copy Package Objects</span></span>
  <span data-ttu-id="e9e0f-103">Cette rubrique indique comment copier des éléments de flux de contrôle, des éléments de flux de données, ainsi que des gestionnaires de connexions dans un package ou entre des packages.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-103">This topic describes how to copy control flow items, data flow items, and connection managers within a package or between packages.</span></span>  
  
### <a name="to-copy-control-and-data-flow-items"></a><span data-ttu-id="e9e0f-104">Pour copier des éléments de flux de contrôle et de données</span><span class="sxs-lookup"><span data-stu-id="e9e0f-104">To copy control and data flow items</span></span>  
  
1.  <span data-ttu-id="e9e0f-105">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient les packages que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the packages that you want work with.</span></span>  
  
2.  <span data-ttu-id="e9e0f-106">Dans l'Explorateur de solutions, double-cliquez sur les packages entre lesquels vous souhaitez effectuer une copie.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-106">In Solution Explorer, double-click the packages that you want to copy between.</span></span>  
  
3.  <span data-ttu-id="e9e0f-107">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , cliquez sur l’onglet du package qui contient les éléments à copier, puis cliquez sur l’onglet **Flux de contrôle**, **Flux de données**ou **Gestionnaires d’événements** .</span><span class="sxs-lookup"><span data-stu-id="e9e0f-107">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the tab for the package that contains the items to copy and click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="e9e0f-108">Sélectionnez les éléments de flux de contrôle ou de flux de données à copier.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-108">Select the control flow or data flow items to copy.</span></span> <span data-ttu-id="e9e0f-109">Vous pouvez sélectionner des éléments un à la fois en appuyant sur la touche Maj et en cliquant sur l'élément, ou bien sélectionner des éléments en tant que groupe en faisant glisser le pointeur sur les éléments à sélectionner.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-109">You can either select items one at a time by pressing the Shift key and clicking the item or select items as a group by dragging the pointer across the items you want to select.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e9e0f-110">Les contraintes de précédence et les chemins d'accès qui connectent des éléments ne sont pas sélectionnés automatiquement lorsque vous sélectionnez les deux éléments qu'ils connectent.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-110">The precedence constraints and paths that connect items are not selected automatically when you select the two items that they connect.</span></span> <span data-ttu-id="e9e0f-111">Pour copier un flux de travail ordonné (segment d’un flux de contrôle ou d’un flux de données), veillez à copier également les contraintes de priorité et les chemins d’accès.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-111">To copy an ordered workflow-a segment of control flow or data flow-make sure to also copy the precedence constrains and the paths.</span></span>  
  
5.  <span data-ttu-id="e9e0f-112">Cliquez avec le bouton droit sur un élément sélectionné, puis cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-112">Right-click a selected item and click **Copy**.</span></span>  
  
6.  <span data-ttu-id="e9e0f-113">Dans le cas de copie d'éléments dans un package différent, cliquez sur le package de destination de la copie, puis cliquez sur l'onglet approprié pour le type d'élément.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-113">If copying items to a different package, click the package that you want to copy to, and then click the appropriate tab for the item type.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e9e0f-114">Vous ne pouvez pas copier un flux de données dans un package tant que le package ne contient pas au moins une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-114">You cannot copy a data flow to a package unless the package contains at least one Data Flow task.</span></span>  
  
7.  <span data-ttu-id="e9e0f-115">Cliquez avec le bouton droit, puis cliquez sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-115">Right-click and click **Paste**.</span></span>  
  
### <a name="to-copy-connection-managers"></a><span data-ttu-id="e9e0f-116">Pour copier des gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="e9e0f-116">To copy connection managers</span></span>  
  
1.  <span data-ttu-id="e9e0f-117">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient le package que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to work with.</span></span>  
  
2.  <span data-ttu-id="e9e0f-118">Dans l'Explorateur de solutions, double-cliquez sur le package.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-118">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="e9e0f-119">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , cliquez sur l’onglet **Flux de contrôle**, **Flux de données**ou **Gestionnaire d’événements** .</span><span class="sxs-lookup"><span data-stu-id="e9e0f-119">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
4.  <span data-ttu-id="e9e0f-120">Dans la zone **Gestionnaires de connexions** , cliquez avec le bouton droit sur le gestionnaire de connexions, puis cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-120">In the **Connection Managers** area, right-click the connection manager, and then click **Copy**.</span></span> <span data-ttu-id="e9e0f-121">Vous ne pouvez copier qu'un seul gestionnaire de connexions à la fois.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-121">You can copy only one connection manager at a time.</span></span>  
  
5.  <span data-ttu-id="e9e0f-122">Si vous copiez des éléments dans un package différent, cliquez sur le package de destination de la copie, puis cliquez sur l’onglet **Flux de contrôle**, **Flux de données**ou **Gestionnaire d’événements** .</span><span class="sxs-lookup"><span data-stu-id="e9e0f-122">If you are copying items to a different package, click the package that you want to copy to and then click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
6.  <span data-ttu-id="e9e0f-123">Cliquez avec le bouton droit sur **Gestionnaires de connexions** , puis cliquez sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="e9e0f-123">Right-click in the **Connection Managers** area and click **Paste**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9e0f-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9e0f-124">See Also</span></span>  
 <span data-ttu-id="e9e0f-125">[Flux de contrôle](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="e9e0f-125">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="e9e0f-126">[Flux de données](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="e9e0f-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 <span data-ttu-id="e9e0f-127">[Connexions Integration Services &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="e9e0f-127">[Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="e9e0f-128">Copier des éléments de projet</span><span class="sxs-lookup"><span data-stu-id="e9e0f-128">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
  
