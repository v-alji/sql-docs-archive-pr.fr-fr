---
title: Connecter des tâches et des conteneurs à l’aide d’une contrainte de précédence par défaut | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- default precedence constraints
- containers [Integration Services], precedence constraints
ms.assetid: 8f31f15f-98ff-4c35-b41f-8b8cfd148d75
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 00207172babdb41b1030e77e71a2c8bc3b99799d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706651"
---
# <a name="connect-tasks-and-containers-by-using-a-default-precedence-constraint"></a><span data-ttu-id="b2bee-102">Connecter des tâches et des conteneurs à l'aide d'une contrainte de précédence par défaut</span><span class="sxs-lookup"><span data-stu-id="b2bee-102">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>
  <span data-ttu-id="b2bee-103">Les contraintes de précédence connectent deux exécutables.</span><span class="sxs-lookup"><span data-stu-id="b2bee-103">Precedence constraints connect two executables.</span></span> <span data-ttu-id="b2bee-104">Un exécutable peut être une tâche quelconque ou encore un conteneur de boucles For, de boucles Foreach ou un conteneur Sequence.</span><span class="sxs-lookup"><span data-stu-id="b2bee-104">An executable can be any task or a For Loop, Foreach Loop, or Sequence container.</span></span> <span data-ttu-id="b2bee-105">Cette procédure décrit comment définir le comportement par défaut des contraintes de précédence et comment connecter des exécutables à l'aide de contraintes de précédence par défaut.</span><span class="sxs-lookup"><span data-stu-id="b2bee-105">This procedure describes how to set the default behavior for precedence constraints, and how to connect executables using the default precedence constraints.</span></span>  
  
## <a name="creating-default-precedence-constraints"></a><span data-ttu-id="b2bee-106">Création de contraintes de précédence par défaut</span><span class="sxs-lookup"><span data-stu-id="b2bee-106">Creating Default Precedence Constraints</span></span>  
 <span data-ttu-id="b2bee-107">Lors de la première utilisation du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)], la valeur par défaut d'une contrainte de précédence est `Success`.</span><span class="sxs-lookup"><span data-stu-id="b2bee-107">When you first use [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the default value of a precedence constraint is `Success`.</span></span> <span data-ttu-id="b2bee-108">Suivez les étapes ci-dessous pour configurer le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] de sorte qu'il utilise une valeur par défaut différente pour les contraintes de précédence.</span><span class="sxs-lookup"><span data-stu-id="b2bee-108">Follow these steps to configure [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to use a different default value for precedence constraints.</span></span>  
  
#### <a name="to-set-the-default-value-for-precedence-constraints"></a><span data-ttu-id="b2bee-109">Pour définir la valeur par défaut des contraintes de précédence</span><span class="sxs-lookup"><span data-stu-id="b2bee-109">To set the default value for precedence constraints</span></span>  
  
1.  <span data-ttu-id="b2bee-110">Ouvrez [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2bee-110">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="b2bee-111">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="b2bee-111">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="b2bee-112">Dans la boîte de dialogue **Options** , développez **Concepteurs Business Intelligence** , puis **Concepteurs de services d’intégration**.</span><span class="sxs-lookup"><span data-stu-id="b2bee-112">In the **Options** dialog box, expand **Business Intelligence Designers,** and then expand **Integration Services Designers**.</span></span>  
  
4.  <span data-ttu-id="b2bee-113">Cliquez sur **Connexion automatique flux de contrôle** , puis sélectionnez **Connecter une nouvelle forme sur la forme sélectionnée par défaut**.</span><span class="sxs-lookup"><span data-stu-id="b2bee-113">Click **Control Flow Auto Connect** and select **Connect a new shape to the selected shape by default**.</span></span>  
  
5.  <span data-ttu-id="b2bee-114">Dans la liste déroulante, choisissez **Utiliser une contrainte Failure (échec) pour la nouvelle forme** ou **Utiliser une contrainte Completion (fin) pour la nouvelle forme**.</span><span class="sxs-lookup"><span data-stu-id="b2bee-114">In the drop-down list, choose either **Use a Failure constraint for the new shape** or **Use a Completion constraint for the new shape**.</span></span>  
  
6.  <span data-ttu-id="b2bee-115">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2bee-115">Click **OK**.</span></span>  
  
#### <a name="to-create-a-default-precedence-constraint"></a><span data-ttu-id="b2bee-116">Pour créer une contrainte de précédence par défaut</span><span class="sxs-lookup"><span data-stu-id="b2bee-116">To create a default precedence constraint</span></span>  
  
1.  <span data-ttu-id="b2bee-117">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="b2bee-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b2bee-118">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="b2bee-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b2bee-119">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="b2bee-119">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="b2bee-120">Sur la surface de dessin de l’onglet **Flux de contrôle** , cliquez sur la tâche ou le conteneur et faites glisser son connecteur vers l’exécutable auquel vous voulez que la contrainte de précédence s’applique.</span><span class="sxs-lookup"><span data-stu-id="b2bee-120">On the design surface of the **Control Flow** tab, click the task or container and drag its connector to the executable to which you want the precedence constraint to apply.</span></span>  
  
5.  <span data-ttu-id="b2bee-121">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="b2bee-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bee-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2bee-122">See Also</span></span>  
 <span data-ttu-id="b2bee-123">[Contraintes de précédence](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="b2bee-123">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="b2bee-124">[Définir la valeur d’une contrainte de précédence à l’aide du menu contextuel](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="b2bee-124">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="b2bee-125">[Définir les propriétés d’une contrainte de précédence](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="b2bee-125">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="b2bee-126">Utiliser une expression dans une contrainte de précédence</span><span class="sxs-lookup"><span data-stu-id="b2bee-126">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
