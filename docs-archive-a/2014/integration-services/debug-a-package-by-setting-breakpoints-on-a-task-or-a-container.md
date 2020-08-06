---
title: Déboguer un package en définissant des points d’arrêt sur une tâche ou un conteneur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], breakpoints
- breakpoints [Integration Services]
- tasks [Integration Services], breakpoints
ms.assetid: e7fa106a-2221-403a-bb74-efc9f12bb450
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 21e334faff95e63e59bbf9c40fdf7e479de949da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602215"
---
# <a name="debug-a-package-by-setting-breakpoints-on-a-task-or-a-container"></a><span data-ttu-id="30454-102">Déboguer un package en définissant des points d'arrêt sur une tâche ou un conteneur</span><span class="sxs-lookup"><span data-stu-id="30454-102">Debug a Package by Setting Breakpoints on a Task or a Container</span></span>
  <span data-ttu-id="30454-103">Cette section décrit la procédure de définition des points d'arrêt dans un package, une tâche, un conteneur de boucle For ou Foreach ou un conteneur de séquences.</span><span class="sxs-lookup"><span data-stu-id="30454-103">This procedure describes how to set breakpoints in a package, a task, a For Loop container, a Foreach Loop container, or a Sequence container.</span></span>  
  
### <a name="to-set-breakpoints-in-a-package-a-task-or-a-container"></a><span data-ttu-id="30454-104">Pour définir des points d'arrêt dans un package, une tâche ou un conteneur</span><span class="sxs-lookup"><span data-stu-id="30454-104">To set breakpoints in a package, a task, or a container</span></span>  
  
1.  <span data-ttu-id="30454-105">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="30454-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="30454-106">Double-cliquez sur le package dans lequel vous souhaitez définir des points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="30454-106">Double-click the package in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="30454-107">Dans le concepteur SSIS, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="30454-107">In SSIS Designer, do the following:</span></span>  
  
    -   <span data-ttu-id="30454-108">Pour définir des points d’arrêt dans l’objet package, cliquez sur l’onglet **Flux de contrôle** , placez le curseur n’importe où sur l’arrière-plan de l’aire de conception, cliquez avec le bouton droit, puis cliquez sur **Modifier les points d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="30454-108">To set breakpoints in the package object, click the **Control Flow** tab, place the cursor anywhere on the background of the design surface, right-click, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="30454-109">Pour définir des points d’arrêt dans un flux de contrôle de package, cliquez sur l’onglet **Flux de contrôle** , cliquez avec le bouton droit sur une tâche, un conteneur de boucle For ou Foreach ou un conteneur de séquences, puis cliquez sur **Modifier les points d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="30454-109">To set breakpoints in a package control flow, click the **Control Flow** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="30454-110">Pour définir des points d’arrêt dans un gestionnaire d’événements, cliquez sur l’onglet **Gestionnaire d’événements** , cliquez avec le bouton droit sur une tâche, un conteneur de boucle For ou Foreach ou un conteneur de séquences, puis cliquez sur **Modifier les points d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="30454-110">To set breakpoints in an event handler, click the **Event Handler** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
4.  <span data-ttu-id="30454-111">Dans la boîte de dialogue **Définir les points d’arrêt \<container name>** , sélectionnez les points d’arrêt à activer.</span><span class="sxs-lookup"><span data-stu-id="30454-111">In the **Set Breakpoints \<container name>** dialog box, select the breakpoints to enable.</span></span>  
  
5.  <span data-ttu-id="30454-112">Vous pouvez également modifier le type du nombre d'accès et la valeur du nombre d'accès pour chaque point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="30454-112">Optionally, modify the hit count type and the hit count number for each breakpoint.</span></span>  
  
6.  <span data-ttu-id="30454-113">Pour enregistrer le package, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="30454-113">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30454-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="30454-114">See Also</span></span>  
 <span data-ttu-id="30454-115">[Outils de dépannage pour le développement des packages](troubleshooting/troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="30454-115">[Troubleshooting Tools for Package Development](troubleshooting/troubleshooting-tools-for-package-development.md) </span></span>  
 <span data-ttu-id="30454-116">[Déboguer un script en définissant des points d’arrêt dans une tâche de script et un composant script](data-flow/transformations/script-component.md) </span><span class="sxs-lookup"><span data-stu-id="30454-116">[Debug a Script by Setting Breakpoints in a Script Task and Script Component](data-flow/transformations/script-component.md) </span></span>  
 <span data-ttu-id="30454-117">[Codage et débogage de la tâche de script](control-flow/script-task.md) </span><span class="sxs-lookup"><span data-stu-id="30454-117">[Coding and Debugging the Script Task](control-flow/script-task.md) </span></span>  
 [<span data-ttu-id="30454-118">Codage et débogage du composant Script</span><span class="sxs-lookup"><span data-stu-id="30454-118">Coding and Debugging the Script Component</span></span>](extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md)  
  
  
