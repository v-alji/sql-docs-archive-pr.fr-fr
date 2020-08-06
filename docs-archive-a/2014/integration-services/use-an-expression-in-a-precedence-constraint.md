---
title: Utiliser une expression dans une contrainte de précédence | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- precedence constraints [Integration Services], adding expressions
- expressions [Integration Services], adding
ms.assetid: 601038bb-3b17-42ac-b09d-5b3a82fb6564
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a997efa448a8381cc8251cd4cbf69dc59f8968e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701286"
---
# <a name="use-an-expression-in-a-precedence-constraint"></a><span data-ttu-id="2ad9c-102">Utiliser une expression dans une contrainte de précédence</span><span class="sxs-lookup"><span data-stu-id="2ad9c-102">Use an Expression in a Precedence Constraint</span></span>
  <span data-ttu-id="2ad9c-103">Cette procédure explique comment ajouter une expression à une contrainte de précédence via la boîte de dialogue **Éditeur de contrainte de précédence** .</span><span class="sxs-lookup"><span data-stu-id="2ad9c-103">This procedure describes how to add an expression to a precedence constraint by using the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="2ad9c-104">Pour pouvoir ajouter une expression à une contrainte de précédence, le package doit inclure au moins deux exécutables (des tâches ou des conteneurs) qui doivent être connectés par une contrainte de précédence.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-104">Before you can add an expression to a precedence constraint, the package must include at least two executables, either tasks or containers, and they must be connected by a precedence constraint.</span></span>  
  
### <a name="to-add-an-expression-to-a-precedence-constraint"></a><span data-ttu-id="2ad9c-105">Pour ajouter une expression à une contrainte de précédence</span><span class="sxs-lookup"><span data-stu-id="2ad9c-105">To add an expression to a precedence constraint</span></span>  
  
1.  <span data-ttu-id="2ad9c-106">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="2ad9c-107">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="2ad9c-108">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="2ad9c-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="2ad9c-109">Dans l’aire de conception de l’onglet **Flux de contrôle** , double-cliquez sur la contrainte de précédence.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-109">On the design surface of the **Control Flow** tab, double-click the precedence constraint.</span></span> <span data-ttu-id="2ad9c-110">**L’Éditeur de contrainte de précédence** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-110">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="2ad9c-111">Sélectionnez **Expression**, **Expression et contrainte**ou **Expression ou contrainte** dans la liste **Opération d’évaluation** .</span><span class="sxs-lookup"><span data-stu-id="2ad9c-111">Select **Expression**, **Expression and Constraint**, or **Expression or Constraint** in the **Evaluation operation** list.</span></span>  
  
6.  <span data-ttu-id="2ad9c-112">Tapez une expression dans la zone de texte **Expression** ou lancez le Générateur d’expressions pour créer une expression.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-112">Type an expression in the **Expression** text box or launch the Expression Builder to create an expression.</span></span>  
  
7.  <span data-ttu-id="2ad9c-113">Pour valider la syntaxe de l’expression, cliquez sur **Tester**.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-113">To validate the expression syntax, click **Test**.</span></span>  
  
8.  <span data-ttu-id="2ad9c-114">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="2ad9c-114">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad9c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ad9c-115">See Also</span></span>  
 <span data-ttu-id="2ad9c-116">[Contraintes de précédence](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="2ad9c-116">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="2ad9c-117">[Connecter des tâches et des conteneurs à l’aide d’une contrainte de précédence par défaut](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="2ad9c-117">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="2ad9c-118">[Définir la valeur d’une contrainte de précédence à l’aide du menu contextuel](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="2ad9c-118">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="2ad9c-119">[Définir les propriétés d’une contrainte de précédence](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="2ad9c-119">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="2ad9c-120">Expressions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2ad9c-120">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
