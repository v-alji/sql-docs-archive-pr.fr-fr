---
title: Grouper ou dissocier des composants | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- grouping containers
- tasks [Integration Services], grouping
- containers [Integration Services], grouping
- grouping tasks
ms.assetid: 34320838-c271-4f8c-90b3-1254690890bb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6811dffca41a12fe0afeeeb334e0107ac127c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601576"
---
# <a name="group-or-ungroup-components"></a><span data-ttu-id="41e17-102">Grouper ou dissocier des composants</span><span class="sxs-lookup"><span data-stu-id="41e17-102">Group or Ungroup Components</span></span>
  <span data-ttu-id="41e17-103">Les onglets **Flux de contrôle**, **Flux de données**et **Gestionnaires d’événements** du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] prennent en charge le groupement réductible.</span><span class="sxs-lookup"><span data-stu-id="41e17-103">The **Control Flow**, **Data Flow**, and **Event Handlers** tabs in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer supports collapsible grouping.</span></span> <span data-ttu-id="41e17-104">Si un package contient plusieurs composants, les onglets peuvent être encombrés, ce qui rend difficile l'affichage simultané de tous les composants et la recherche de l'élément avec lequel vous souhaitez travailler.</span><span class="sxs-lookup"><span data-stu-id="41e17-104">If a package has many components, the tabs can become crowded, making it difficult to view all the components at one time and to locate the item with which you want to work.</span></span> <span data-ttu-id="41e17-105">La fonctionnalité de groupement réductible permet d'économiser de l'espace sur la surface de travail et de faciliter l'utilisation des packages volumineux.</span><span class="sxs-lookup"><span data-stu-id="41e17-105">The collapsible grouping feature can conserve space on the work surface and make it easier to work with large packages.</span></span>  
  
 <span data-ttu-id="41e17-106">Vous sélectionnez les composants à grouper, vous les groupez, puis vous développez ou réduisez les groupes selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="41e17-106">You select the components that you want to group, group them, and then expand or collapse the groups to suit your work.</span></span> <span data-ttu-id="41e17-107">Le développement d'un groupe donne accès aux propriétés des composants du groupe.</span><span class="sxs-lookup"><span data-stu-id="41e17-107">Expanding a group provides access to the properties of the components in the group.</span></span> <span data-ttu-id="41e17-108">Les contraintes de précédence qui connectent les tâches et conteneurs sont incluses automatiquement dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="41e17-108">The precedence constraints that connect tasks and containers are automatically included in the group.</span></span>  
  
 <span data-ttu-id="41e17-109">Voici quelques observations concernant le regroupement des composants.</span><span class="sxs-lookup"><span data-stu-id="41e17-109">The following are considerations for grouping components.</span></span>  
  
-   <span data-ttu-id="41e17-110">Pour regrouper des composants, le flux de contrôle, le flux de données ou le gestionnaire d'événements doivent contenir plusieurs composants.</span><span class="sxs-lookup"><span data-stu-id="41e17-110">To group components, the control flow, data flow, or event handler must contain more than one component.</span></span>  
  
-   <span data-ttu-id="41e17-111">Les groupes peuvent également être imbriqués, ce qui rend possible la création de groupes à l'intérieur d'autres groupes.</span><span class="sxs-lookup"><span data-stu-id="41e17-111">Groups can also be nested, making it possible to create groups within groups.</span></span> <span data-ttu-id="41e17-112">La surface de dessin peut implémenter plusieurs groupes non imbriqués, mais un composant ne peut appartenir qu'à un seul groupe, à moins que les groupes soient imbriqués.</span><span class="sxs-lookup"><span data-stu-id="41e17-112">The design surface can implement multiple un-nested groups, but a component can belong to only one group, unless the groups are nested.</span></span>  
  
-   <span data-ttu-id="41e17-113">Lors de l'enregistrement d'un package, le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] enregistre le groupement mais celui-ci n'a aucun effet sur l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="41e17-113">When a package is saved, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the grouping, but the grouping has no effect on package execution.</span></span> <span data-ttu-id="41e17-114">La possibilité de grouper les composants est une fonctionnalité de conception ; elle n'affecte pas le comportement d'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="41e17-114">The ability to group components is a design-time feature; it does not affect the run-time behavior of the package.</span></span>  
  
### <a name="to-group-components"></a><span data-ttu-id="41e17-115">Pour regrouper des composants</span><span class="sxs-lookup"><span data-stu-id="41e17-115">To group components</span></span>  
  
1.  <span data-ttu-id="41e17-116">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="41e17-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="41e17-117">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="41e17-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="41e17-118">Cliquez sur l’onglet **Flux de contrôle**, **Flux de données**ou **Gestionnaires d’événements** .</span><span class="sxs-lookup"><span data-stu-id="41e17-118">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="41e17-119">Sur l’aire de conception de l’onglet, sélectionnez les composants que vous souhaitez grouper, cliquez avec le bouton droit sur un composant sélectionné, puis cliquez sur **Groupe**.</span><span class="sxs-lookup"><span data-stu-id="41e17-119">On the design surface of the tab, select the components you want to group, right-click a selected component, and then click **Group**.</span></span>  
  
5.  <span data-ttu-id="41e17-120">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="41e17-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-ungroup-components"></a><span data-ttu-id="41e17-121">Pour dissocier des composants</span><span class="sxs-lookup"><span data-stu-id="41e17-121">To ungroup components</span></span>  
  
1.  <span data-ttu-id="41e17-122">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="41e17-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="41e17-123">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="41e17-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="41e17-124">Cliquez sur l’onglet **Flux de contrôle**, **Flux de données**ou **Gestionnaires d’événements** .</span><span class="sxs-lookup"><span data-stu-id="41e17-124">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="41e17-125">Sur l’aire de conception de l’onglet, sélectionnez le groupe qui contient le composant que vous souhaitez dissocier, cliquez avec le bouton droit sur le composant sélectionné, puis cliquez sur **Dissocier**.</span><span class="sxs-lookup"><span data-stu-id="41e17-125">On the design surface of the tab, select the group that contains the component you want to ungroup, right-click, and then click **Ungroup**.</span></span>  
  
5.  <span data-ttu-id="41e17-126">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="41e17-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e17-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41e17-127">See Also</span></span>  
 [<span data-ttu-id="41e17-128">Ajouter ou supprimer une tâche ou un conteneur dans un flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="41e17-128">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
     
 [<span data-ttu-id="41e17-129">Connecter des tâches et des conteneurs à l’aide d’une contrainte de précédence par défaut</span><span class="sxs-lookup"><span data-stu-id="41e17-129">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md)  
  
  
