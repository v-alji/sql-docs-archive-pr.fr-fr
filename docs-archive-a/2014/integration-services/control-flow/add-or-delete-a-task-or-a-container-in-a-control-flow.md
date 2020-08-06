---
title: Ajouter ou supprimer une tâche ou un conteneur dans un flux de contrôle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], adding
- adding tasks
- adding containers
- tasks [Integration Services], adding
ms.assetid: 653084c6-87a3-45d5-b458-914ecf24d56a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8338a4143358d732a974287e587f482dc5c36a22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610813"
---
# <a name="add-or-delete-a-task-or-a-container-in-a-control-flow"></a><span data-ttu-id="b164c-102">Ajouter ou supprimer une tâche ou un conteneur dans un flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="b164c-102">Add or Delete a Task or a Container in a Control Flow</span></span>
  <span data-ttu-id="b164c-103">Quand vous travaillez dans le concepteur de flux de contrôle, la boîte à outils du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] énumère les tâches proposées par [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pour créer le flux de contrôle d’un package.</span><span class="sxs-lookup"><span data-stu-id="b164c-103">When you are working in the control flow designer, the Toolbox in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer lists the tasks that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides for building control flow in a package.</span></span> <span data-ttu-id="b164c-104">Pour plus d’informations sur la boîte à outils, consultez [Boîte à outils SSIS](../ssis-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="b164c-104">For more information about the Toolbox, see [SSIS Toolbox](../ssis-toolbox.md).</span></span>  
  
 <span data-ttu-id="b164c-105">Un package peut inclure plusieurs instances de la même tâche.</span><span class="sxs-lookup"><span data-stu-id="b164c-105">A package can include multiple instances of the same task.</span></span> <span data-ttu-id="b164c-106">Chaque instance d'une tâche est identifiée de manière unique dans le package et vous pouvez configurer chaque instance différemment.</span><span class="sxs-lookup"><span data-stu-id="b164c-106">Each instance of a task is uniquely identified in the package, and you can configure each instance differently.</span></span>  
  
 <span data-ttu-id="b164c-107">Si vous supprimez une tâche, les contraintes de précédence connectant la tâche à d'autres tâches et les conteneurs du flux de contrôle sont également supprimés.</span><span class="sxs-lookup"><span data-stu-id="b164c-107">If you delete a task, the precedence constraints that connect the task to other tasks and containers in the control flow are also deleted.</span></span>  
  
 <span data-ttu-id="b164c-108">Les procédures ci-dessous décrivent comment ajouter ou supprimer une tâche ou un conteneur dans le flux de contrôle d'un package.</span><span class="sxs-lookup"><span data-stu-id="b164c-108">The following procedures describe how to add or delete a task or container in the control flow of a package.</span></span>  
  
### <a name="to-add-a-task-or-a-container-to-a-control-flow"></a><span data-ttu-id="b164c-109">Pour ajouter une tâche ou un conteneur à un flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="b164c-109">To add a task or a container to a control flow</span></span>  
  
1.  <span data-ttu-id="b164c-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="b164c-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b164c-111">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="b164c-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b164c-112">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="b164c-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="b164c-113">Pour ouvrir la **boîte à outils**, cliquez sur **Boîte à outils** dans le menu **Affichage** .</span><span class="sxs-lookup"><span data-stu-id="b164c-113">To open the **Toolbox**, click **Toolbox** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="b164c-114">Développez **Éléments de flux de contrôle** et **Tâches du plan de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="b164c-114">Expand **Control Flow Items** and **Maintenance Tasks**.</span></span>  
  
6.  <span data-ttu-id="b164c-115">Faites glisser des tâches et des conteneurs de la **boîte à outils** vers l’aire de conception de l’onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="b164c-115">Drag tasks and containers from the **Toolbox** to the design surface of the **Control Flow** tab.</span></span>  
  
7.  <span data-ttu-id="b164c-116">Connectez une tâche ou un conteneur du flux de contrôle du package à un autre composant du flux de contrôle en faisant glisser son connecteur vers cet autre composant.</span><span class="sxs-lookup"><span data-stu-id="b164c-116">Connect a task or container within the package control flow by dragging its connector to another component in the control flow.</span></span>  
  
8.  <span data-ttu-id="b164c-117">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="b164c-117">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-task-or-a-container-from-a-control-flow"></a><span data-ttu-id="b164c-118">Pour supprimer une tâche ou un conteneur d'un flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="b164c-118">To delete a task or a container from a control flow</span></span>  
  
1.  <span data-ttu-id="b164c-119">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="b164c-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b164c-120">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="b164c-120">In Solution Explorer, double-click the package to open it.</span></span> <span data-ttu-id="b164c-121">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="b164c-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="b164c-122">Cliquez sur l’onglet **Flux de contrôle** , cliquez avec le bouton droit sur la tâche ou le conteneur à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b164c-122">Click the **Control Flow** tab, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
    -   <span data-ttu-id="b164c-123">Ouvrez **Explorateur de package**.</span><span class="sxs-lookup"><span data-stu-id="b164c-123">Open **Package Explorer**.</span></span> <span data-ttu-id="b164c-124">Dans le dossier **Exécutables** , cliquez avec le bouton droit sur la tâche ou le conteneur à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b164c-124">From the **Executables** folder, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="b164c-125">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="b164c-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b164c-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b164c-126">See Also</span></span>  
 <span data-ttu-id="b164c-127">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b164c-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="b164c-128">[Conteneurs de Integration Services](integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="b164c-128">[Integration Services Containers](integration-services-containers.md) </span></span>  
 [<span data-ttu-id="b164c-129">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="b164c-129">Control Flow</span></span>](control-flow.md)  
  
  
