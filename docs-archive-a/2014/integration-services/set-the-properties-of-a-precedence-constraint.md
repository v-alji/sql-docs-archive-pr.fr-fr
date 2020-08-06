---
title: Définir les propriétés d’une contrainte de précédence | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Precedence Constraint Editor dialog box
- precedence constraints [Integration Services], properties
ms.assetid: d990f600-5c09-4cd5-8528-0a58d79dc9f2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 55b95bdb79d801156bef6198bc0f57accb5d9517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613527"
---
# <a name="set-the-properties-of-a-precedence-constraint"></a><span data-ttu-id="4f59a-102">Définir les propriétés d'une contrainte de précédence</span><span class="sxs-lookup"><span data-stu-id="4f59a-102">Set the Properties of a Precedence Constraint</span></span>
  <span data-ttu-id="4f59a-103">Pour définir des propriétés sur des contraintes de précédence, vous pouvez utiliser l'un des outils suivants :</span><span class="sxs-lookup"><span data-stu-id="4f59a-103">To set properties on precedence constraints, you can use one of these tools:</span></span>  
  
-   <span data-ttu-id="4f59a-104">Vous pouvez utiliser la boîte de dialogue **Éditeur de contrainte de précédence** .</span><span class="sxs-lookup"><span data-stu-id="4f59a-104">You can use the **Precedence Constraint Editor** dialog box.</span></span>  
  
-   <span data-ttu-id="4f59a-105">Vous pouvez utiliser la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="4f59a-105">You can use the Properties window.</span></span> <span data-ttu-id="4f59a-106">La fenêtre Propriétés répertorie des propriétés permettant de configurer des contraintes de précédence qui ne sont pas disponibles dans la boîte de dialogue **Éditeur de contrainte de précédence** .</span><span class="sxs-lookup"><span data-stu-id="4f59a-106">The Properties window lists properties for configuring precedence constraints that are not available in the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="4f59a-107">Dans cette fenêtre, vous pouvez entrer une description et un nom pour la contrainte de précédence et configurer l'annotation à afficher pour la contrainte de précédence sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="4f59a-107">In the Properties window, you can provide a description and name of the precedence constraint, and configure the annotation to display for the precedence constraint on the design surface.</span></span>  
  
 <span data-ttu-id="4f59a-108">Les procédures ci-dessous montrent comment définir des propriétés sur des contraintes de précédence en utilisant chacun de ces outils.</span><span class="sxs-lookup"><span data-stu-id="4f59a-108">The following procedures describe how to set properties on precedence constraints by using each of these tools.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-precedence-constraint-editor"></a><span data-ttu-id="4f59a-109">Pour définir les propriétés d'une contrainte de précédence à l'aide de l'éditeur de contrainte de précédence</span><span class="sxs-lookup"><span data-stu-id="4f59a-109">To set the properties of a precedence constraint by using the Precedence Constraint Editor</span></span>  
  
1.  <span data-ttu-id="4f59a-110">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="4f59a-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="4f59a-111">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="4f59a-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4f59a-112">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="4f59a-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="4f59a-113">Double-cliquez sur la contrainte de précédence.</span><span class="sxs-lookup"><span data-stu-id="4f59a-113">Double-click the precedence constraint.</span></span>  
  
     <span data-ttu-id="4f59a-114">**L’Éditeur de contrainte de précédence** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="4f59a-114">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="4f59a-115">Dans la liste déroulante **Opération d’évaluation** , sélectionnez une opération d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="4f59a-115">In the **Evaluation operation** drop-down list, select an evaluation operation.</span></span>  
  
6.  <span data-ttu-id="4f59a-116">Dans la `Value` liste déroulante, sélectionnez le résultat d’exécution de l’exécutable de précédence.</span><span class="sxs-lookup"><span data-stu-id="4f59a-116">In the `Value` drop-down list, select the execution result of the precedence executable.</span></span>  
  
7.  <span data-ttu-id="4f59a-117">Si l’opération d’évaluation utilise une expression, dans la `Expression` zone, tapez une expression, puis cliquez sur **tester** pour évaluer l’expression.</span><span class="sxs-lookup"><span data-stu-id="4f59a-117">If the evaluation operation uses an expression, in the `Expression` box, type an expression, and click **Test** to evaluate the expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f59a-118">Les noms de variable respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="4f59a-118">Variable names are case-sensitive.</span></span>  
  
8.  <span data-ttu-id="4f59a-119">Si plusieurs tâches ou conteneurs sont connectés à l’exécutable avec restriction, sélectionnez **logique and** pour spécifier que les résultats d’exécution de tous les exécutables précédents doivent avoir la valeur `true` .</span><span class="sxs-lookup"><span data-stu-id="4f59a-119">If multiple tasks or containers are connected to the constrained executable, select **Logical AND** to specify that the execution results of all preceding executables must evaluate to `true`.</span></span> <span data-ttu-id="4f59a-120">Sélectionnez **or logique** pour spécifier qu’un seul résultat d’exécution doit correspondre à `true` .</span><span class="sxs-lookup"><span data-stu-id="4f59a-120">Select **Logical OR** to specify that only one execution result must evaluate to `true`.</span></span>  
  
9. <span data-ttu-id="4f59a-121">Cliquez sur **OK** pour fermer la boîte de dialogue **Éditeur de contrainte de précédence**.</span><span class="sxs-lookup"><span data-stu-id="4f59a-121">Click **OK** to close the **Precedence Constraint Editor**.</span></span>  
  
10. <span data-ttu-id="4f59a-122">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="4f59a-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-properties-window"></a><span data-ttu-id="4f59a-123">Pour définir les propriétés d'une contrainte de précédence à l'aide de la fenêtre Propriétés</span><span class="sxs-lookup"><span data-stu-id="4f59a-123">To set the properties of a precedence constraint by using the Properties window</span></span>  
  
1.  <span data-ttu-id="4f59a-124">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package à modifier.</span><span class="sxs-lookup"><span data-stu-id="4f59a-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to modify.</span></span>  
  
2.  <span data-ttu-id="4f59a-125">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="4f59a-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4f59a-126">Cliquez sur l’onglet **Flow Control** . Sur l’aire de conception de l’onglet **Flow Control** , cliquez avec le bouton droit sur la contrainte de précédence, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4f59a-126">Click the **Control Flow** tab. On the design surface of the **Control Flow** tab, right-click the precedence constraint, and then click **Properties**.</span></span> <span data-ttu-id="4f59a-127">Dans la fenêtre Propriétés, modifiez les valeurs des propriétés.</span><span class="sxs-lookup"><span data-stu-id="4f59a-127">In the Properties window, modify the property values.</span></span>  
  
4.  <span data-ttu-id="4f59a-128">Dans la fenêtre **Propriétés** , configurez les propriétés de lecture/écriture suivantes pour les contraintes de précédence :</span><span class="sxs-lookup"><span data-stu-id="4f59a-128">In the **Properties** window, set the following read/write properties of precedence constraints:</span></span>  
  
    |<span data-ttu-id="4f59a-129">Propriété Lecture/écriture</span><span class="sxs-lookup"><span data-stu-id="4f59a-129">Read/write property</span></span>|<span data-ttu-id="4f59a-130">Action de configuration</span><span class="sxs-lookup"><span data-stu-id="4f59a-130">Configuration action</span></span>|  
    |--------------------------|--------------------------|  
    |<span data-ttu-id="4f59a-131">Description</span><span class="sxs-lookup"><span data-stu-id="4f59a-131">Description</span></span>|<span data-ttu-id="4f59a-132">Fournissez une description.</span><span class="sxs-lookup"><span data-stu-id="4f59a-132">Provide a description.</span></span>|  
    |<span data-ttu-id="4f59a-133">EvalOp</span><span class="sxs-lookup"><span data-stu-id="4f59a-133">EvalOp</span></span>|<span data-ttu-id="4f59a-134">Sélectionnez une opération d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="4f59a-134">Select an evaluation operation.</span></span> <span data-ttu-id="4f59a-135">Si l' `Expression` opération, **ExpressionAndConstant**ou **ExpressionOrConstant** est sélectionnée, vous pouvez spécifier une expression.</span><span class="sxs-lookup"><span data-stu-id="4f59a-135">If the `Expression`, **ExpressionAndConstant**, or **ExpressionOrConstant** operation is selected, you can specify an expression.</span></span>|  
    |<span data-ttu-id="4f59a-136">Expression</span><span class="sxs-lookup"><span data-stu-id="4f59a-136">Expression</span></span>|<span data-ttu-id="4f59a-137">Si l'opération d'évaluation inclut une expression, fournissez une expression.</span><span class="sxs-lookup"><span data-stu-id="4f59a-137">If the evaluation operation includes and expression, provide an expression.</span></span> <span data-ttu-id="4f59a-138">L'expression doit prendre une valeur de type Boolean.</span><span class="sxs-lookup"><span data-stu-id="4f59a-138">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="4f59a-139">Pour plus d’informations sur le langage des expressions, consultez [Expressions Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4f59a-139">For more information about the expression language, see [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>|  
    |<span data-ttu-id="4f59a-140">LogicalAnd</span><span class="sxs-lookup"><span data-stu-id="4f59a-140">LogicalAnd</span></span>|<span data-ttu-id="4f59a-141">Défini `LogicalAnd` pour spécifier si la contrainte de précédence est évaluée de concert avec d’autres contraintes de précédence, lorsque plusieurs exécutables précèdent et sont liés à l’exécutable avec contrainte</span><span class="sxs-lookup"><span data-stu-id="4f59a-141">Set `LogicalAnd` to specify whether the precedence constraint is evaluated in concert with other precedence constraints, when multiple executables precede and are linked to the constrained executable</span></span>|  
    |<span data-ttu-id="4f59a-142">Nom</span><span class="sxs-lookup"><span data-stu-id="4f59a-142">Name</span></span>|<span data-ttu-id="4f59a-143">Mettez à jour le nom de la contrainte de précédence.</span><span class="sxs-lookup"><span data-stu-id="4f59a-143">Update the name of the precedence constraint.</span></span>|  
    |<span data-ttu-id="4f59a-144">ShowAnnotation</span><span class="sxs-lookup"><span data-stu-id="4f59a-144">ShowAnnotation</span></span>|<span data-ttu-id="4f59a-145">Spécifiez le type d'annotation à utiliser.</span><span class="sxs-lookup"><span data-stu-id="4f59a-145">Specify the type of annotation to use.</span></span> <span data-ttu-id="4f59a-146">Sélectionnez **Never** pour désactiver les annotations, **AsNeeded** pour activer l’annotation à la demande, **ConstraintName** pour annoter automatiquement en utilisant la valeur de la propriété Name, **ConstraintDescription** pour annoter automatiquement en utilisant la valeur de la propriété Description et **ConstraintOptions** pour annoter automatiquement en utilisant les valeurs des propriétés Value et Expression.</span><span class="sxs-lookup"><span data-stu-id="4f59a-146">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **ConstraintName** to automatically annotate using the value of the Name property, **ConstraintDescription** to automatically annotate using the value of the Description property, and **ConstraintOptions** to automatically annotate using the values of the Value and Expression properties.</span></span>|  
    |<span data-ttu-id="4f59a-147">Valeur</span><span class="sxs-lookup"><span data-stu-id="4f59a-147">Value</span></span>|<span data-ttu-id="4f59a-148">Si l’opération d’évaluation spécifiée dans la propriété EvalOP inclut une contrainte, sélectionnez le résultat d’exécution de l’exécutable de contrainte.</span><span class="sxs-lookup"><span data-stu-id="4f59a-148">If the evaluation operation specified in the EvalOP property includes a constraint, select the execution result of the constraining executable.</span></span>|  
  
5.  <span data-ttu-id="4f59a-149">Fermez la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="4f59a-149">Close the Properties window.</span></span>  
  
6.  <span data-ttu-id="4f59a-150">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="4f59a-150">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f59a-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f59a-151">See Also</span></span>  
 <span data-ttu-id="4f59a-152">[Contraintes de précédence](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="4f59a-152">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="4f59a-153">[Connecter des tâches et des conteneurs à l’aide d’une contrainte de précédence par défaut](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="4f59a-153">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="4f59a-154">[Définir la valeur d’une contrainte de précédence à l’aide du menu contextuel](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="4f59a-154">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 [<span data-ttu-id="4f59a-155">Utiliser une expression dans une contrainte de précédence</span><span class="sxs-lookup"><span data-stu-id="4f59a-155">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
