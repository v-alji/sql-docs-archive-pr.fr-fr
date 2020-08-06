---
title: Définir les propriétés d’une tâche ou d’un conteneur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], properties
ms.assetid: 52d47ca4-fb8c-493d-8b2b-48bb269f859b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0a4c556b94af02c2f874f2740a70b1294c35e653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709732"
---
# <a name="set-the-properties-of-a-task-or-container"></a><span data-ttu-id="fcc20-102">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="fcc20-102">Set the Properties of a Task or Container</span></span>
  <span data-ttu-id="fcc20-103">Vous pouvez définir la plupart des propriétés des tâches et des conteneurs à l’aide de la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="fcc20-103">You can set most properties of tasks and containers by using the **Properties** window.</span></span> <span data-ttu-id="fcc20-104">Les seules exceptions sont les propriétés des collections de tâches et les propriétés trop complexes à définir dans la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="fcc20-104">The exceptions are properties of task collections and properties that are too complex to set by using the **Properties** window.</span></span> <span data-ttu-id="fcc20-105">Par exemple, vous ne pouvez pas configurer l’énumérateur utilisé par le conteneur de boucles Foreach dans la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="fcc20-105">For example, you cannot configure the enumerator that the Foreach Loop container uses in the **Properties** window.</span></span> <span data-ttu-id="fcc20-106">Vous devez utiliser un éditeur de tâche ou de conteneur pour définir ces propriétés complexes.</span><span class="sxs-lookup"><span data-stu-id="fcc20-106">You must use a task or container editor to set these complex properties.</span></span> <span data-ttu-id="fcc20-107">La plupart des éditeurs de tâche et de conteneur possèdent plusieurs nœuds contenant chacun des propriétés connexes.</span><span class="sxs-lookup"><span data-stu-id="fcc20-107">Most task and container editors have multiple nodes and each node contains related properties.</span></span> <span data-ttu-id="fcc20-108">Le nom du nœud indique l'objet des propriétés contenues dans le nœud.</span><span class="sxs-lookup"><span data-stu-id="fcc20-108">The name of the node indicates the subject of the properties that the node contains.</span></span>  
  
 <span data-ttu-id="fcc20-109">Les procédures suivantes décrivent comment définir les propriétés d’une tâche ou d’un conteneur en utilisant les fenêtres **Propriétés** ou l’éditeur de tâche ou de conteneur correspondant.</span><span class="sxs-lookup"><span data-stu-id="fcc20-109">The following procedures describe how to set the properties of a task or container by using either the **Properties** windows, or the corresponding task or container editor.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-the-properties-window"></a><span data-ttu-id="fcc20-110">Pour définir les propriétés d'une tâche ou d'un conteneur à l'aide de la fenêtre Propriétés</span><span class="sxs-lookup"><span data-stu-id="fcc20-110">To set the properties of a task or container by using the Properties window</span></span>  
  
1.  <span data-ttu-id="fcc20-111">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="fcc20-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="fcc20-112">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="fcc20-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="fcc20-113">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="fcc20-113">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="fcc20-114">Sur l’aire de conception de l’onglet **Flux de contrôle** , cliquez avec le bouton droit sur la tâche ou le conteneur, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="fcc20-114">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="fcc20-115">Dans la fenêtre **Propriétés** , mettez à jour la valeur de la propriété.</span><span class="sxs-lookup"><span data-stu-id="fcc20-115">In the **Properties** window, update the property value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcc20-116">Vous pouvez définir les propriétés en tapant une valeur directement dans la zone de texte ou en sélectionnant une valeur dans une liste.</span><span class="sxs-lookup"><span data-stu-id="fcc20-116">Most properties can be set by typing a value directly in the text box, or by selecting a value from a list.</span></span> <span data-ttu-id="fcc20-117">Néanmoins, certaines propriétés sont plus complexes et disposent d'un éditeur de propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="fcc20-117">However, some properties are more complex and have a custom property editor.</span></span> <span data-ttu-id="fcc20-118">Pour définir la propriété, cliquez dans la zone de texte, puis sur le bouton Générer **(...)** pour ouvrir l’éditeur personnalisé.</span><span class="sxs-lookup"><span data-stu-id="fcc20-118">To set the property, click in the text box, and then click the build **(...)** button to open the custom editor.</span></span>  
  
6.  <span data-ttu-id="fcc20-119">Si vous le souhaitez, créez des expressions de propriété afin de mettre à jour de manière dynamique les propriétés de la tâche ou du conteneur.</span><span class="sxs-lookup"><span data-stu-id="fcc20-119">Optionally, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="fcc20-120">Pour plus d’informations, consultez [Ajouter ou modifier une Expression de propriété](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="fcc20-120">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="fcc20-121">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="fcc20-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-a-task-or-container-editor"></a><span data-ttu-id="fcc20-122">Pour définir les propriétés d'une tâche ou d'un conteneur à l'aide d'un éditeur de tâche ou de conteneur</span><span class="sxs-lookup"><span data-stu-id="fcc20-122">To set the properties of a task or container by using a task or container editor</span></span>  
  
1.  <span data-ttu-id="fcc20-123">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="fcc20-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="fcc20-124">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="fcc20-124">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="fcc20-125">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="fcc20-125">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="fcc20-126">Sur l’aire de conception de l’onglet **Flux de contrôle** , cliquez avec le bouton droit sur la tâche ou le conteneur, puis cliquez sur **Modifier** pour ouvrir l’éditeur de tâche ou de conteneur correspondant.</span><span class="sxs-lookup"><span data-stu-id="fcc20-126">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Edit** to open the corresponding task or container editor.</span></span>  
  
     <span data-ttu-id="fcc20-127">Pour plus d’informations sur la configuration du conteneur de boucles For, consultez [Configurer un conteneur de boucles For](control-flow/for-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="fcc20-127">For information about how to configure the For Loop container, see [Configure a For Loop Container](control-flow/for-loop-container.md).</span></span>  
  
     <span data-ttu-id="fcc20-128">Pour plus d’informations sur la configuration du conteneur de boucles Foreach, consultez [configurer un conteneur de boucles Foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="fcc20-128">For information about how to configure the Foreach Loop container, see [Configure a Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fcc20-129">Le conteneur de séquences ne possède pas d'éditeur personnalisé.</span><span class="sxs-lookup"><span data-stu-id="fcc20-129">The Sequence container has no custom editor.</span></span>  
  
5.  <span data-ttu-id="fcc20-130">Si l'éditeur de tâche ou de conteneur comporte plusieurs nœuds, cliquez sur celui qui contient la propriété à définir.</span><span class="sxs-lookup"><span data-stu-id="fcc20-130">If the task or container editor has multiple nodes, click the node that contains the property that you want to set.</span></span>  
  
6.  <span data-ttu-id="fcc20-131">Si vous le souhaitez, cliquez sur **Expressions** , puis dans la page **Expressions** , créez des expressions de propriété afin de mettre à jour dynamiquement les propriétés de la tâche ou du conteneur.</span><span class="sxs-lookup"><span data-stu-id="fcc20-131">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="fcc20-132">Pour plus d’informations, consultez [Ajouter ou modifier une Expression de propriété](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="fcc20-132">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="fcc20-133">Mettez à jour la valeur de la propriété.</span><span class="sxs-lookup"><span data-stu-id="fcc20-133">Update the property value.</span></span>  
  
8.  <span data-ttu-id="fcc20-134">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="fcc20-134">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc20-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcc20-135">See Also</span></span>  
 <span data-ttu-id="fcc20-136">[Tâches Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="fcc20-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="fcc20-137">Conteneurs Integration Services</span><span class="sxs-lookup"><span data-stu-id="fcc20-137">Integration Services Containers</span></span>](control-flow/integration-services-containers.md)  
  
  
