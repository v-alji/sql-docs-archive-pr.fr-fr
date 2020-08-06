---
title: Éditeur de contrainte de précédence | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.precedenceconstraint.f1
helpviewer_keywords:
- Precedence Constraint Editor dialog box
ms.assetid: b10d4330-6e35-4037-b309-ef56efcd60c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6853d1974f4276361d60e1d73b34c72a366a7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602875"
---
# <a name="precedence-constraint-editor"></a><span data-ttu-id="940fa-102">Éditeur de contrainte de précédence</span><span class="sxs-lookup"><span data-stu-id="940fa-102">Precedence Constraint Editor</span></span>
  <span data-ttu-id="940fa-103">Utilisez la boîte de dialogue **Éditeur de contrainte de précédence** pour configurer les contraintes de précédence.</span><span class="sxs-lookup"><span data-stu-id="940fa-103">Use the **Precedence Constraint Editor** dialog box to configure precedence constraints.</span></span>  
  
## <a name="options"></a><span data-ttu-id="940fa-104">Options</span><span class="sxs-lookup"><span data-stu-id="940fa-104">Options</span></span>  
 <span data-ttu-id="940fa-105">**Opération d’évaluation**</span><span class="sxs-lookup"><span data-stu-id="940fa-105">**Evaluation operation**</span></span>  
 <span data-ttu-id="940fa-106">Spécifiez l'opération d'évaluation utilisée par la contrainte de précédence.</span><span class="sxs-lookup"><span data-stu-id="940fa-106">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="940fa-107">Ces opérations sont : **Contrainte**, **Expression**, **Expression et contrainte** et **Expression ou contrainte**.</span><span class="sxs-lookup"><span data-stu-id="940fa-107">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
 <span data-ttu-id="940fa-108">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="940fa-108">**Value**</span></span>  
 <span data-ttu-id="940fa-109">Spécifiez la valeur de contrainte : **Réussite**, **Échec** ou **À l'achèvement**.</span><span class="sxs-lookup"><span data-stu-id="940fa-109">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="940fa-110"> La ligne de contrainte de précédence est verte pour **Réussite**, mise en surbrillance pour **Échec**et bleue pour **À l'achèvement**.</span><span class="sxs-lookup"><span data-stu-id="940fa-110">The precedence constraint line is green for **Success**, highlighted for **Failure**, and blue for **Completion**.</span></span>  
  
 <span data-ttu-id="940fa-111">**Expression**</span><span class="sxs-lookup"><span data-stu-id="940fa-111">**Expression**</span></span>  
 <span data-ttu-id="940fa-112">Si vous utilisez les opérations **Expression**, **Expression et contrainte**ou **Expression ou contrainte**, tapez une expression ou lancez le Générateur d’expressions pour créer l’expression.</span><span class="sxs-lookup"><span data-stu-id="940fa-112">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression or launch the Expression Builder to create the expression.</span></span> <span data-ttu-id="940fa-113">L'expression doit prendre une valeur de type Boolean.</span><span class="sxs-lookup"><span data-stu-id="940fa-113">The expression must evaluate to a Boolean.</span></span>  
  
 <span data-ttu-id="940fa-114">**Test**</span><span class="sxs-lookup"><span data-stu-id="940fa-114">**Test**</span></span>  
 <span data-ttu-id="940fa-115">Validez l'expression.</span><span class="sxs-lookup"><span data-stu-id="940fa-115">Validate the expression.</span></span>  
  
 <span data-ttu-id="940fa-116">**ET logique**</span><span class="sxs-lookup"><span data-stu-id="940fa-116">**Logical AND**</span></span>  
 <span data-ttu-id="940fa-117">Sélectionnez cette option pour spécifier que plusieurs contraintes de précédence sur le même exécutable doivent être évaluées ensemble.</span><span class="sxs-lookup"><span data-stu-id="940fa-117">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="940fa-118">Toutes les contraintes doivent prendre la valeur `True`.</span><span class="sxs-lookup"><span data-stu-id="940fa-118">All constraints must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="940fa-119">Ce type de contrainte de précédence s'affiche sous forme de ligne pleine verte, mise en surbrillance ou bleue.</span><span class="sxs-lookup"><span data-stu-id="940fa-119">This type of precedence constraint appears as a solid green, highlighted or blue line.</span></span>  
  
 <span data-ttu-id="940fa-120">**OU logique**</span><span class="sxs-lookup"><span data-stu-id="940fa-120">**Logical OR**</span></span>  
 <span data-ttu-id="940fa-121">Sélectionnez cette option pour spécifier que plusieurs contraintes de précédence sur le même exécutable doivent être évaluées ensemble.</span><span class="sxs-lookup"><span data-stu-id="940fa-121">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="940fa-122">Une contrainte au moins doit prendre la valeur `True`.</span><span class="sxs-lookup"><span data-stu-id="940fa-122">At least one constraint must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="940fa-123">Ce type de contrainte de précédence s'affiche sous forme de ligne pointillée verte, mise en surbrillance ou bleue.</span><span class="sxs-lookup"><span data-stu-id="940fa-123">This type of precedence constraint appears as a dotted green, highlighted, or blue line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="940fa-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="940fa-124">See Also</span></span>  
 <span data-ttu-id="940fa-125">[Contraintes de précédence](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="940fa-125">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="940fa-126">[Tâches Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="940fa-126">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="940fa-127">[Conteneurs de Integration Services](control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="940fa-127">[Integration Services Containers](control-flow/integration-services-containers.md) </span></span>  
 [<span data-ttu-id="940fa-128">Expressions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="940fa-128">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
