---
title: Ajouter ou modifier une expression de propriété | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- expressions [Integration Services], creating
- expressions [Integration Services], property expressions
ms.assetid: cb5da499-065f-4fa6-9f6d-5bc5f385241e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d6d12fbe46930818af2b47b59620963d39616e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611932"
---
# <a name="add-or-change-a-property-expression"></a><span data-ttu-id="2875e-102">Ajouter ou modifier une expression de propriété</span><span class="sxs-lookup"><span data-stu-id="2875e-102">Add or Change a Property Expression</span></span>
  <span data-ttu-id="2875e-103">Vous pouvez créer des expressions de propriété pour les packages, les tâches, les conteneurs de boucles For ou Foreach, les conteneurs de séquences, les gestionnaires d'événements, les gestionnaires de connexions aux niveaux des packages et du projet, ainsi que les modules fournisseurs d'informations.</span><span class="sxs-lookup"><span data-stu-id="2875e-103">You can create property expressions for packages, tasks, Foreach Loop containers, For Loop containers, Sequence containers, event handlers, package and project level connection managers, and log providers.</span></span>  
  
 <span data-ttu-id="2875e-104">Pour créer ou modifier des expressions de propriété, vous pouvez utiliser l’ **Éditeur d’expressions de la propriété** ou le **Générateur d’expressions**.</span><span class="sxs-lookup"><span data-stu-id="2875e-104">To create or change property expressions, you can use either the **Property Expressions Editor** or **Expression Builder**.</span></span> <span data-ttu-id="2875e-105">L’ **Éditeur d’expressions de la propriété** est accessible à partir des éditeurs personnalisés disponibles pour les tâches et conteneurs, et à partir de la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="2875e-105">The **Property Expressions Editor** can be accessed from either the custom editors that are available for tasks and containers, or from the **Properties** window.</span></span> <span data-ttu-id="2875e-106">Le**Générateur d’expressions** est accessible à partir de l’ **Éditeur d’expressions de la propriété**.</span><span class="sxs-lookup"><span data-stu-id="2875e-106">**Expression Builder** can be accessed from inside the **Property Expressions Editor**.</span></span> <span data-ttu-id="2875e-107">Vous pouvez écrire des expressions à la fois dans l’ **Éditeur d’expressions de la propriété** et dans le **Générateur d’expressions**, mais le **Générateur d’expressions** fournit un ensemble graphique d’outils qui simplifie la construction d’expressions complexes.</span><span class="sxs-lookup"><span data-stu-id="2875e-107">While you can write expressions in either the **Property Expressions Editor** or **Expression Builder**, **Expression Builder** provides a graphical set of tools that makes it simple to build complex expressions.</span></span>  
  
 <span data-ttu-id="2875e-108">Pour en savoir plus sur la syntaxe, les opérateurs et les fonctions fournis par [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], consultez [Opérateurs &#40;expression SSIS&#41;](operators-ssis-expression.md) et [Fonctions &#40;expression SSIS&#41;](functions-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="2875e-108">To learn more about the syntax, operators, and functions that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides, see [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) and [Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md).</span></span> <span data-ttu-id="2875e-109">La rubrique relative à chaque opérateur ou fonction inclut des exemples d'utilisation de cet opérateur ou de cette fonction dans une expression.</span><span class="sxs-lookup"><span data-stu-id="2875e-109">The topic for each operator or function includes examples of using that operator or function in an expression.</span></span> <span data-ttu-id="2875e-110">Pour obtenir des exemples d’expressions plus complexes, consultez [Expressions de propriété dans des packages](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="2875e-110">For examples of more complex expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
### <a name="to-create-or-change-a-property-expression"></a><span data-ttu-id="2875e-111">Pour créer ou modifier une expression de propriété</span><span class="sxs-lookup"><span data-stu-id="2875e-111">To create or change a property expression</span></span>  
  
1.  <span data-ttu-id="2875e-112">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet contenant le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] souhaité.</span><span class="sxs-lookup"><span data-stu-id="2875e-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="2875e-113">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir, puis effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2875e-113">In Solution Explorer, double-click the package to open it, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="2875e-114">Si l’élément est une tâche ou un conteneur, double-cliquez dessus, puis cliquez sur **Expressions** dans l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="2875e-114">If the item is a task or a container, double-click the item, and then click **Expressions** in the editor.</span></span>  
  
    -   <span data-ttu-id="2875e-115">Cliquez avec le bouton droit sur l’élément, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2875e-115">Right-click the item and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2875e-116">Cliquez sur la zone **Expressions**, puis sur les points de suspension (...).</span><span class="sxs-lookup"><span data-stu-id="2875e-116">Click in the **Expressions** box and then click the ellipsis (...).</span></span>  
  
4.  <span data-ttu-id="2875e-117">Dans l’ **Éditeur d’expressions de la propriété**, sélectionnez une propriété dans la liste **Propriété** , puis effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="2875e-117">In the **Property Expressions Editor**, select a property in the **Property** list, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="2875e-118">Tapez l’expression de propriété ou modifiez-la directement dans la colonne **Expression** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2875e-118">Type or change the property expression directly in the **Expression** column, and then click **OK**.</span></span>  
  
         <span data-ttu-id="2875e-119">-ou-</span><span class="sxs-lookup"><span data-stu-id="2875e-119">-or-</span></span>  
  
    -   <span data-ttu-id="2875e-120">Dans la ligne d’expression de la propriété, cliquez sur les points de suspension (...) pour ouvrir le **Générateur d’expressions**.</span><span class="sxs-lookup"><span data-stu-id="2875e-120">Click the ellipsis (...) in the expression row of the property to open the **Expression Builder**.</span></span>  
  
5.  <span data-ttu-id="2875e-121">(Facultatif) Dans le **Générateur d’expressions**, effectuez l’une des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="2875e-121">(Optional) In the **Expression Builder**, do any of the following tasks:</span></span>  
  
    -   <span data-ttu-id="2875e-122">Pour accéder aux variables système et aux variables définies par l’utilisateur, développez **Variables**.</span><span class="sxs-lookup"><span data-stu-id="2875e-122">To access system and user-defined variables, expand **Variables**.</span></span>  
  
    -   <span data-ttu-id="2875e-123">Pour accéder aux fonctions, conversions et opérateurs fournis par le langage d’expression [!INCLUDE[ssIS](../../includes/ssis-md.md)] , développez **Fonctions mathématiques**, **Fonctions de chaîne**, **Fonctions de date et d’heure**, **Fonctions NULL**, **Casts de type**et **Opérateurs**.</span><span class="sxs-lookup"><span data-stu-id="2875e-123">To access the functions, the casts, and the operators that the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression language provides, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators**.</span></span>  
  
    -   <span data-ttu-id="2875e-124">Pour générer ou modifier une expression dans le **Générateur d’expressions**, faites glisser les variables, colonnes, fonctions, opérateurs et conversions dans la zone **Expression** ou tapez l’expression dans la zone.</span><span class="sxs-lookup"><span data-stu-id="2875e-124">To build or change an expression in the **Expression Builder**, drag variables, columns, functions, operators, and casts to the **Expression** box, or type the expression in the box.</span></span>  
  
    -   <span data-ttu-id="2875e-125">Pour afficher le résultat de l’évaluation de l’expression, cliquez sur **Évaluer l’expression** dans le **Générateur d’expressions**.</span><span class="sxs-lookup"><span data-stu-id="2875e-125">To view the evaluation result of the expression, click **Evaluate Expression** in the **Expression Builder**.</span></span>  
  
         <span data-ttu-id="2875e-126">Si l'expression n'est pas valide, une alerte apparaît et décrit les erreurs de syntaxe dans l'expression.</span><span class="sxs-lookup"><span data-stu-id="2875e-126">If the expression is not valid, an alert appears that describes the syntax errors in the expression.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2875e-127">L'évaluation d'une expression n'affecte pas le résultat de l'évaluation de la propriété.</span><span class="sxs-lookup"><span data-stu-id="2875e-127">Evaluating an expression does not assign the evaluation result to the property.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2875e-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2875e-128">See Also</span></span>  
 <span data-ttu-id="2875e-129">[Expressions Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="2875e-129">[Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="2875e-130">[Expressions de propriété dans des packages](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="2875e-130">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="2875e-131">[Packages Integration Services &#40;SSIS&#41;](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="2875e-131">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="2875e-132">[Conteneurs Integration Services](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="2875e-132">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="2875e-133">[Tâches Integration Services](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="2875e-133">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="2875e-134">[Gestionnaires d’événements Integration Services &#40;SSIS&#41](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="2875e-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="2875e-135">[Connexions Integration Services &#40;SSIS&#41;](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="2875e-135">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="2875e-136">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2875e-136">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)  
  
  
