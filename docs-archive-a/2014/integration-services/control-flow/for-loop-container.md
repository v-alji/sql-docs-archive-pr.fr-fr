---
title: Conteneur de boucles For | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.forloopcontainerdetails.f1
helpviewer_keywords:
- repeating control flow
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: 44cf7355-992b-4bbf-a28c-bfb012de06f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a6c864779237fdbf4dd249f87b7c06655293c047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600195"
---
# <a name="for-loop-container"></a><span data-ttu-id="318ce-102">Conteneur de boucles For</span><span class="sxs-lookup"><span data-stu-id="318ce-102">For Loop Container</span></span>
  <span data-ttu-id="318ce-103">Le conteneur de boucles For définit un flux de contrôle répétitif dans un package.</span><span class="sxs-lookup"><span data-stu-id="318ce-103">The For Loop container defines a repeating control flow in a package.</span></span> <span data-ttu-id="318ce-104">La mise en œuvre de la boucle est similaire à la structure de bouclage **For** des langages de programmation.</span><span class="sxs-lookup"><span data-stu-id="318ce-104">The loop implementation is similar to the **For** looping structure in programming languages.</span></span> <span data-ttu-id="318ce-105">Dans chaque répétition de la boucle, le conteneur de boucles For évalue une expression et répète son flux de travail jusqu'à ce que l'expression renvoie la valeur `False`.</span><span class="sxs-lookup"><span data-stu-id="318ce-105">In each repeat of the loop, the For Loop container evaluates an expression and repeats its workflow until the expression evaluates to `False`.</span></span>  
  
 <span data-ttu-id="318ce-106">Le conteneur de boucles For utilise les éléments suivants pour définir la boucle :</span><span class="sxs-lookup"><span data-stu-id="318ce-106">The For Loop container usesthe following elements to define the loop:</span></span>  
  
-   <span data-ttu-id="318ce-107">Une expression d'initialisation facultative qui attribue des valeurs aux compteurs de la boucle</span><span class="sxs-lookup"><span data-stu-id="318ce-107">An optional initialization expression that assigns values to the loop counters.</span></span>  
  
-   <span data-ttu-id="318ce-108">Une expression d'évaluation qui permet de déterminer si la boucle doit s'arrêter ou continuer</span><span class="sxs-lookup"><span data-stu-id="318ce-108">An evaluation expression that contains the expression used to test whether the loop should stop or continue.</span></span>  
  
-   <span data-ttu-id="318ce-109">Une expression d'itération facultative qui incrémente ou décrémente le compteur de la boucle</span><span class="sxs-lookup"><span data-stu-id="318ce-109">An optional iteration expression that increments or decrements the loop counter.</span></span>  
  
 <span data-ttu-id="318ce-110">Le schéma suivant illustre un conteneur de boucles For avec une tâche Envoyer un message.</span><span class="sxs-lookup"><span data-stu-id="318ce-110">The following diagram shows a For Loop container with a Send Mail task.</span></span> <span data-ttu-id="318ce-111">Si l'expression d'initialisation est `@Counter = 0`, que l'expression d'évaluation est `@Counter < 4`et que l'expression d'itération est `@Counter = @Counter + 1`, la boucle se répète quatre fois et envoie quatre messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="318ce-111">If the initialization expression is `@Counter = 0`, the evaluation expression is `@Counter < 4`, and the iteration expression is `@Counter = @Counter + 1`, the loop repeats four times and sends four e-mail messages.</span></span>  
  
 <span data-ttu-id="318ce-112">![Un conteneur de boucles For répète une tâche quatre fois](../media/ssis-forloop.gif "Un conteneur de boucles For répète une tâche quatre fois")</span><span class="sxs-lookup"><span data-stu-id="318ce-112">![A For Loop container repeats a task four times](../media/ssis-forloop.gif "A For Loop container repeats a task four times")</span></span>  
  
 <span data-ttu-id="318ce-113">Les expressions doivent être des expressions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] valides.</span><span class="sxs-lookup"><span data-stu-id="318ce-113">The expressions must be valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions.</span></span>  
  
 <span data-ttu-id="318ce-114">Pour créer les expressions d'initialisation et d'assignation, vous pouvez utiliser l'opérateur d'affectation (=).</span><span class="sxs-lookup"><span data-stu-id="318ce-114">To create the initialization and assignment expressions, you can use the assignment operator (=).</span></span> <span data-ttu-id="318ce-115">Cet opérateur n'est pas pris en charge par la grammaire d'expression Integration Services et ne peut être utilisé que par les types d'expression d'initialisation et d'assignation du conteneur de boucles For.</span><span class="sxs-lookup"><span data-stu-id="318ce-115">This operator is not otherwise supported by the Integration Services expression grammar and can only be used by the initialization and assignment expression types in the For Loop container.</span></span> <span data-ttu-id="318ce-116">Toute expression qui utilise l’opérateur d’affectation doit contenir la syntaxe `@Var = <expression>`, où **Var** représente une variable d’exécution et \<expression> indique une expression qui suit les règles de la syntaxe d’expression [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="318ce-116">Any expression that uses the assignment operator must have the syntax `@Var = <expression>`, where **Var** is a run-time variable and \<expression> is an expression that follows the rules of the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="318ce-117">L'expression peut comprendre les variables, les littéraux et l'ensemble des opérateurs et des fonctions pris en charge par la grammaire d'expression SSIS.</span><span class="sxs-lookup"><span data-stu-id="318ce-117">The expression can include the variables, literals, and any operators and functions that the SSIS expression grammar supports.</span></span> <span data-ttu-id="318ce-118">L'expression doit correspondre à une valeur dont le type de données peut être converti vers le type de données de la variable.</span><span class="sxs-lookup"><span data-stu-id="318ce-118">The expression must evaluate to a data type that can be cast to the data type of the variable.</span></span>  
  
 <span data-ttu-id="318ce-119">Un conteneur de boucles For ne peut avoir qu'une seule expression d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="318ce-119">A For Loop container can have only one evaluation expression.</span></span> <span data-ttu-id="318ce-120">Par conséquent, le conteneur de boucles For exécute tous ses éléments de flux de contrôle le même nombre de fois.</span><span class="sxs-lookup"><span data-stu-id="318ce-120">This means that the For Loop container runs all its control flow elements the same number of times.</span></span> <span data-ttu-id="318ce-121">Étant donné que le conteneur de boucles For peut comprendre d'autres conteneurs de boucles For, vous pouvez créer des boucles imbriquées et mettre en œuvre un bouclage complexe dans les packages.</span><span class="sxs-lookup"><span data-stu-id="318ce-121">Because the For Loop container can include other For Loop containers, you can build nested loops and implement complex looping in packages.</span></span>  
  
 <span data-ttu-id="318ce-122">Vous pouvez configurer une propriété de transaction sur le conteneur de boucles For afin de définir une transaction pour un sous-ensemble du flux de contrôle du package.</span><span class="sxs-lookup"><span data-stu-id="318ce-122">You can set a transaction property on the For Loop container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="318ce-123">Ainsi, vous pouvez gérer les transactions de façon plus précise.</span><span class="sxs-lookup"><span data-stu-id="318ce-123">In this way, you can manage transactions at a more granular level.</span></span> <span data-ttu-id="318ce-124">Par exemple, si un conteneur de boucles For répète un flux de contrôle qui met à jour plusieurs fois les données d'une table, vous pouvez configurer la boucle For et son flux de contrôle de manière à utiliser une transaction empêchant toute mise à jour si toutes les données ne sont pas mises à jour correctement.</span><span class="sxs-lookup"><span data-stu-id="318ce-124">For example, if a For Loop container repeats a control flow that updates data in a table multiple times, you can configure the For Loop and its control flow to use a transaction to ensure that if not all data is updated successfully, no data is updated.</span></span> <span data-ttu-id="318ce-125">Pour plus d’informations, consultez [Transactions Integration Services](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="318ce-125">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-for-loop-container"></a><span data-ttu-id="318ce-126">Configuration du conteneur de boucles For</span><span class="sxs-lookup"><span data-stu-id="318ce-126">Configuration of the For Loop Container</span></span>  
 <span data-ttu-id="318ce-127">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="318ce-127">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="318ce-128">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="318ce-128">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="318ce-129">Éditeur de boucle For</span><span class="sxs-lookup"><span data-stu-id="318ce-129">For Loop Editor</span></span>](../for-loop-editor.md)  
  
-   [<span data-ttu-id="318ce-130">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="318ce-130">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="318ce-131">Pour plus d’informations sur la définition par programmation de ces propriétés, consultez la documentation relative à la classe **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** dans le Guide du développeur.</span><span class="sxs-lookup"><span data-stu-id="318ce-131">For more information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="318ce-132">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="318ce-132">Related Tasks</span></span>  
 <span data-ttu-id="318ce-133">Pour plus d'informations sur la configuration d'un conteneur de boucles For, consultez les rubriques suivantes.</span><span class="sxs-lookup"><span data-stu-id="318ce-133">For information about how to configure a For Loop Container, see the following topics.</span></span>  
  
-   [<span data-ttu-id="318ce-134">Configurer un conteneur de boucles For</span><span class="sxs-lookup"><span data-stu-id="318ce-134">Configure a For Loop Container</span></span>](for-loop-container.md)  
  
-   [<span data-ttu-id="318ce-135">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="318ce-135">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="318ce-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="318ce-136">See Also</span></span>  
 <span data-ttu-id="318ce-137">[Flux de contrôle](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="318ce-137">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="318ce-138">Expressions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="318ce-138">Integration Services &#40;SSIS&#41; Expressions</span></span>](../expressions/integration-services-ssis-expressions.md)  
  
  
