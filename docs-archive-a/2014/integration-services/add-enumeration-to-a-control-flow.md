---
title: Ajouter une énumération à un contrôle Flow | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding enumerations
- Foreach Loop containers
- control flow [Integration Services], enumerations
- repeating workflows
- enumerations [Integration Services]
ms.assetid: f212b5fb-3cc4-422e-9b7c-89eb769a812a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59b8569880fdf1a49f5f2ca1f6841841f9790af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604697"
---
# <a name="add-enumeration-to-a-control-flow"></a><span data-ttu-id="f6bea-102">Ajouter une énumération à un flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="f6bea-102">Add Enumeration to a Control Flow</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="f6bea-103">inclut le conteneur de boucles Foreach, un élément de flux de contrôle qui permet de facilement inclure une construction de boucle énumérant les fichiers et objets du flux de contrôle d’un package.</span><span class="sxs-lookup"><span data-stu-id="f6bea-103">includes the Foreach Loop container, a control flow element that makes it simple to include a looping construct that enumerates files and objects in the control flow of a package.</span></span> <span data-ttu-id="f6bea-104">Pour plus d’informations, consultez [Conteneur de boucles Foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="f6bea-104">For more information, see [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="f6bea-105">Le conteneur de boucles Foreach n'offre aucune fonctionnalité ; il ne fournit que la structure dans laquelle vous créez le flux de contrôle répété, spécifiez un type d'énumérateur et configurez l'énumérateur.</span><span class="sxs-lookup"><span data-stu-id="f6bea-105">The Foreach Loop container provides no functionality; it provides only the structure in which you build the repeatable control flow, specify an enumerator type, and configure the enumerator.</span></span> <span data-ttu-id="f6bea-106">Pour fournir une fonctionnalité de conteneur, vous devez inclure au moins une tâche dans le conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="f6bea-106">To provide container functionality, you must include at least one task in the Foreach Loop container.</span></span> <span data-ttu-id="f6bea-107">Pour plus d’informations, consultez [Tâches Integration Services](control-flow/integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="f6bea-107">For more information, see [Integration Services Tasks](control-flow/integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="f6bea-108">Le conteneur de boucles Foreach peut inclure un flux de contrôle avec plusieurs tâches, ainsi que d'autres conteneurs.</span><span class="sxs-lookup"><span data-stu-id="f6bea-108">The Foreach Loop container can include a control flow with multiple tasks and other containers.</span></span> <span data-ttu-id="f6bea-109">Que vous ajoutiez des tâches et des conteneurs à un conteneur de boucles Foreach ou à un package, l'opération est la même, sauf que vous faites glisser les tâches et les conteneurs vers le conteneur de boucles Foreach plutôt que vers le package.</span><span class="sxs-lookup"><span data-stu-id="f6bea-109">Adding tasks and containers to a Foreach Loop container is similar to adding them to a package, except you drag the tasks and containers to the Foreach Loop container instead of to the package.</span></span> <span data-ttu-id="f6bea-110">Si le conteneur de boucles Foreach contient plusieurs tâches ou conteneurs, vous pouvez les connecter à l'aide de contraintes de précédence, tout comme dans un package.</span><span class="sxs-lookup"><span data-stu-id="f6bea-110">If the Foreach Loop container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="f6bea-111">Pour plus d’informations, consultez [Contraintes de précédence](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="f6bea-111">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
### <a name="to-implement-a-foreach-loop-container-in-a-control-flow"></a><span data-ttu-id="f6bea-112">Pour implémenter un conteneur de boucles Foreach dans un flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="f6bea-112">To implement a Foreach Loop container in a control flow</span></span>  
  
1.  <span data-ttu-id="f6bea-113">Ajoutez le conteneur de boucles Foreach au package.</span><span class="sxs-lookup"><span data-stu-id="f6bea-113">Add the Foreach Loop container to the package.</span></span> <span data-ttu-id="f6bea-114">Pour plus d’informations, consultez [Ajouter ou supprimer une tâche ou un conteneur dans un workflow de contrôle](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span><span class="sxs-lookup"><span data-stu-id="f6bea-114">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="f6bea-115">.</span><span class="sxs-lookup"><span data-stu-id="f6bea-115">.</span></span>  
  
2.  <span data-ttu-id="f6bea-116">Ajoutez des tâches et des conteneurs au conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="f6bea-116">Add tasks and containers to the Foreach Loop container.</span></span> <span data-ttu-id="f6bea-117">Pour plus d’informations, consultez [Ajouter ou supprimer une tâche ou un conteneur dans un workflow de contrôle](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span><span class="sxs-lookup"><span data-stu-id="f6bea-117">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="f6bea-118">.</span><span class="sxs-lookup"><span data-stu-id="f6bea-118">.</span></span>  
  
3.  <span data-ttu-id="f6bea-119">Connectez les tâches et les conteneurs du conteneur de boucles Foreach à l'aide de contraintes de précédence.</span><span class="sxs-lookup"><span data-stu-id="f6bea-119">Connect tasks and containers in the Foreach Loop container using precedence constraints.</span></span> <span data-ttu-id="f6bea-120">Pour plus d’informations, consultez [Connecter des tâches et des conteneurs à l’aide d’une contrainte de précédence par défaut](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="f6bea-120">For more information, see [Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span></span>  
  
4.  <span data-ttu-id="f6bea-121">Configurez le conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="f6bea-121">Configure the Foreach Loop container.</span></span> <span data-ttu-id="f6bea-122">Pour plus d’informations, consultez [Configurer un conteneur de boucles Foreach](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="f6bea-122">For more information, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6bea-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6bea-123">See Also</span></span>  
 <span data-ttu-id="f6bea-124">[Ajouter ou supprimer une tâche ou un conteneur dans un workflow de contrôle](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="f6bea-124">[Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="f6bea-125">[Grouper ou dissocier des composants](group-or-ungroup-components.md) </span><span class="sxs-lookup"><span data-stu-id="f6bea-125">[Group or Ungroup Components](group-or-ungroup-components.md) </span></span>  
 <span data-ttu-id="f6bea-126">[Contraintes de précédence](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="f6bea-126">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="f6bea-127">[Ajouter une itération à un workflow de contrôle](add-iteration-to-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="f6bea-127">[Add Iteration to a Control Flow](add-iteration-to-a-control-flow.md) </span></span>  
 [<span data-ttu-id="f6bea-128">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="f6bea-128">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
