---
title: Conteneur de séquences | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sequencecontainer.f1
helpviewer_keywords:
- Sequence container
- grouping control flows
- containers [Integration Services], Sequence
- subset control flow [Integration Services]
ms.assetid: 7731f91e-b8b3-4d96-a0d9-73f568547cb3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b972f923e2134363ba1b378beebebbeb1e5d6bb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611206"
---
# <a name="sequence-container"></a><span data-ttu-id="51404-102">conteneur de séquences</span><span class="sxs-lookup"><span data-stu-id="51404-102">Sequence Container</span></span>
  <span data-ttu-id="51404-103">Le conteneur de séquences définit un flux de contrôle représentant un sous-ensemble du flux de contrôle du package.</span><span class="sxs-lookup"><span data-stu-id="51404-103">The Sequence container defines a control flow that is a subset of the package control flow.</span></span> <span data-ttu-id="51404-104">Les conteneurs de séquences regroupent le package en plusieurs flux de contrôle distincts contenant chacun un ou plusieurs conteneurs et tâches exécutés dans le flux de contrôle global du package.</span><span class="sxs-lookup"><span data-stu-id="51404-104">Sequence containers group the package into multiple separate control flows, each containing one or more tasks and containers that run within the overall package control flow.</span></span>  
  
 <span data-ttu-id="51404-105">Le conteneur de séquences peut inclure plusieurs tâches et d'autres conteneurs.</span><span class="sxs-lookup"><span data-stu-id="51404-105">The Sequence container can include multiple tasks in addition to other containers.</span></span> <span data-ttu-id="51404-106">L'ajout de tâches et de conteneurs à un conteneur de séquences est identique à l'ajout de ces éléments à un package. La seule différence est que vous faites glisser les tâches et les conteneurs dans le conteneur de séquences au lieu de les glisser dans le conteneur de package.</span><span class="sxs-lookup"><span data-stu-id="51404-106">Adding tasks and containers to a Sequence container is similar to adding them to a package, except you drag the tasks and containers to the Sequence container instead of to the package container.</span></span> <span data-ttu-id="51404-107">Si le conteneur de séquences inclut plusieurs tâches ou conteneurs, vous pouvez les connecter à l'aide de contraintes de précédence de la même manière que dans un package.</span><span class="sxs-lookup"><span data-stu-id="51404-107">If the Sequence container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="51404-108">Pour plus d’informations, consultez [Contraintes de précédence](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="51404-108">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="51404-109">L'utilisation d'un conteneur de séquences présente de nombreux avantages :</span><span class="sxs-lookup"><span data-stu-id="51404-109">There are many benefits of using a Sequence container:</span></span>  
  
-   <span data-ttu-id="51404-110">Désactivation des groupes de tâches afin de concentrer le débogage du package sur un seul sous-ensemble de son flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="51404-110">Disabling groups of tasks to focus package debugging on one subset of the package control flow.</span></span>  
  
-   <span data-ttu-id="51404-111">Centralisation de la gestion des propriétés de plusieurs tâches en définissant les propriétés sur un conteneur de séquences plutôt que sur les différentes tâches</span><span class="sxs-lookup"><span data-stu-id="51404-111">Managing properties on multiple tasks in one location by setting properties on a Sequence container instead of on the individual tasks.</span></span>  
  
     <span data-ttu-id="51404-112">Vous pouvez ainsi affecter la valeur `Disable` à la propriété `True` du conteneur de séquences afin de désactiver toutes les tâches et tous les conteneurs du conteneur de séquences.</span><span class="sxs-lookup"><span data-stu-id="51404-112">For example, you can set the `Disable` property of the Sequence container to `True` to disable all the tasks and containers in the Sequence container.</span></span>  
  
-   <span data-ttu-id="51404-113">Attribution d'une étendue aux variables utilisées par un groupe de tâches et de conteneurs apparentés</span><span class="sxs-lookup"><span data-stu-id="51404-113">Providing scope for variables that a group of related tasks and containers use.</span></span>  
  
-   <span data-ttu-id="51404-114">Regroupement de nombreuses tâches pour vous permettre de les gérer plus facilement, en réduisant et en développant le conteneur de séquences.</span><span class="sxs-lookup"><span data-stu-id="51404-114">Grouping many tasks so you can more easily managed them by collapsing and expanding the Sequence container.</span></span>  
  
     <span data-ttu-id="51404-115">Vous pouvez aussi créer des groupes de tâches, qui peuvent être réduits et développés à partir de la zone **Groupe** .</span><span class="sxs-lookup"><span data-stu-id="51404-115">You can also create task groups, which expand and collapse using the **Group** box.</span></span> <span data-ttu-id="51404-116">Cependant, la zone **Groupe** est une fonctionnalité disponible au moment de la conception qui ne contient aucune propriété et n’affiche aucun comportement au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="51404-116">However, the **Group** box is a design-time feature that has no properties or run-time behavior.</span></span> <span data-ttu-id="51404-117">Pour plus d’informations, consultez [Grouper ou dissocier des composants](../group-or-ungroup-components.md)</span><span class="sxs-lookup"><span data-stu-id="51404-117">For more information, see [Group or Ungroup Components](../group-or-ungroup-components.md)</span></span>  
  
-   <span data-ttu-id="51404-118">Configurez un attribut de transaction sur le conteneur de séquences afin de définir une transaction pour un sous-ensemble du flux de contrôle du package.</span><span class="sxs-lookup"><span data-stu-id="51404-118">Set a transaction attribute on the Sequence container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="51404-119">Ainsi, vous pouvez gérer les transactions de façon plus précise.</span><span class="sxs-lookup"><span data-stu-id="51404-119">In this way, you can manage transactions at a more granular level.</span></span>  
  
     <span data-ttu-id="51404-120">Par exemple, si un conteneur de séquences comprend deux tâches apparentées, l'une supprimant des données d'une table et l'autre insérant celles-ci dans une table, vous pouvez configurer une transaction de manière à ce que l'action de suppression soit annulée en cas d'échec de l'action d'insertion.</span><span class="sxs-lookup"><span data-stu-id="51404-120">For example, if a Sequence container includes two related tasks, one task that deletes data in a table and another task that inserts data into a table, you can configure a transaction to ensure that the delete action is rolled back if the insert action fails.</span></span> <span data-ttu-id="51404-121">Pour plus d’informations, consultez [Transactions Integration Services](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="51404-121">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-sequence-container"></a><span data-ttu-id="51404-122">Configuration du conteneur de séquences</span><span class="sxs-lookup"><span data-stu-id="51404-122">Configuration of the Sequence Container</span></span>  
 <span data-ttu-id="51404-123">Le conteneur de séquences ne possède pas d’interface utilisateur personnalisée et vous ne pouvez le configurer que dans la fenêtre **Propriétés** de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="51404-123">The Sequence container has no custom user interface and you can configure it only in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="51404-124">Pour plus d’informations sur la définition par programmation de ces propriétés, consultez la documentation relative à la classe **T:Microsoft.SqlServer.Dts.Runtime.Sequence** dans le Guide du développeur.</span><span class="sxs-lookup"><span data-stu-id="51404-124">For information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.Sequence** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="51404-125">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="51404-125">Related Tasks</span></span>  
 <span data-ttu-id="51404-126">Pour plus d’informations sur la définition des propriétés du composant dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], consultez [Définir les propriétés d’une tâche ou d’un conteneur](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="51404-126">For information about how to set properties of the component in the [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51404-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51404-127">See Also</span></span>  
 <span data-ttu-id="51404-128">[Ajouter ou supprimer une tâche ou un conteneur dans un flux de contrôle](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="51404-128">[Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="51404-129">[Connecter des tâches et des conteneurs à l’aide d’une contrainte de précédence par défaut](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="51404-129">[Connect Tasks and Containers by Using a Default Precedence Constraint](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="51404-130">Conteneurs Integration Services</span><span class="sxs-lookup"><span data-stu-id="51404-130">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
