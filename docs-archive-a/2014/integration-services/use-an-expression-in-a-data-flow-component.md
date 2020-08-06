---
title: Utiliser une expression dans un composant de Data Flow | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], data flow
- expressions [Integration Services], data flow components
ms.assetid: 9181b998-d24a-41fb-bb3c-14eee34f910d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 653bf468d0af6d44c5abe7344fcc13f93f86b430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703092"
---
# <a name="use-an-expression-in-a-data-flow-component"></a><span data-ttu-id="eb183-102">Utiliser une expression dans un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="eb183-102">Use an Expression in a Data Flow Component</span></span>
  <span data-ttu-id="eb183-103">Cette procédure permet d'ajouter une expression à la transformation de fractionnement conditionnel ou à la transformation de colonne dérivée.</span><span class="sxs-lookup"><span data-stu-id="eb183-103">This procedure describes how to add an expression to the Conditional Split transformation or to the Derived Column transformation.</span></span> <span data-ttu-id="eb183-104">La transformation de fractionnement conditionnel utilise des expressions pour définir les conditions qui dirigent les lignes de données vers une sortie de transformation et la transformation de colonne dérivée utilise des expressions pour définir les valeurs affectées aux colonnes.</span><span class="sxs-lookup"><span data-stu-id="eb183-104">The Conditional Split transformation uses expressions to define the conditions that direct data rows to a transformation output, and the Derived Column transformation uses expressions to define values assigned to columns.</span></span>  
  
 <span data-ttu-id="eb183-105">Pour implémenter une expression dans une transformation, le package doit déjà inclure au moins une tâche de flux de données et une source.</span><span class="sxs-lookup"><span data-stu-id="eb183-105">To implement an expression in a transformation, the package must already include at least one Data Flow task and a source.</span></span> <span data-ttu-id="eb183-106">Pour plus d'informations sur l'ajout d'éléments aux packages, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb183-106">For information about adding items to packages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="eb183-107">Ajouter ou supprimer une tâche ou un conteneur dans un flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="eb183-107">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
    
  
-   [<span data-ttu-id="eb183-108">Ajouter ou supprimer un composant dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="eb183-108">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
-   [<span data-ttu-id="eb183-109">Connecter des composants dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="eb183-109">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)  
  
### <a name="to-create-an-expression"></a><span data-ttu-id="eb183-110">Pour créer une expression</span><span class="sxs-lookup"><span data-stu-id="eb183-110">To create an expression</span></span>  
  
1.  <span data-ttu-id="eb183-111">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="eb183-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="eb183-112">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="eb183-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="eb183-113">Dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , cliquez sur l’onglet **Flux de contrôle** , puis cliquez sur la tâche de flux de données contenant le flux de données dans lequel vous voulez implémenter une expression.</span><span class="sxs-lookup"><span data-stu-id="eb183-113">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow** tab, and then click the Data Flow task that contains the data flow in which you want to implement an expression.</span></span>  
  
4.  <span data-ttu-id="eb183-114">Cliquez sur l’onglet **Flux de données** , et faites glisser une transformation de fractionnement conditionnel ou de colonne dérivée de la **Boîte à outils** jusqu’à l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="eb183-114">Click the **Data Flow** tab, and drag either a Conditional Split or Derived Column transformation from the **Toolbox** to the design surface.</span></span>  
  
5.  <span data-ttu-id="eb183-115">Faites glisser le connecteur vert de la source ou d'une transformation vers la transformation de fractionnement conditionnel ou de colonne dérivée.</span><span class="sxs-lookup"><span data-stu-id="eb183-115">Drag the green connector from the source or a transformation to the Conditional Split or Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="eb183-116">Double-cliquez sur la transformation pour ouvrir sa boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="eb183-116">Double-click the transformation to open its dialog box.</span></span>  
  
7.  <span data-ttu-id="eb183-117">Dans le volet gauche, développez **Variables** pour afficher les variables système et définies par l’utilisateur, et développez **Colonnes** pour afficher les colonnes d’entrée de transformation.</span><span class="sxs-lookup"><span data-stu-id="eb183-117">In the left pane, expand **Variables** to display system and user-defined variables, and expand **Columns** to display the transformation input columns.</span></span>  
  
8.  <span data-ttu-id="eb183-118">Dans le volet droit, développez **Fonctions mathématiques**, **Fonctions de chaîne**, **Fonctions de date et d’heure**, **Fonctions NULL**, **Casts de type**et **Opérateurs** pour accéder aux fonctions, conversions et opérateurs fournis par la grammaire d’expression.</span><span class="sxs-lookup"><span data-stu-id="eb183-118">In the right pane, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators** to access the functions, the casts, and the operators that the expression grammar provides.</span></span>  
  
9. <span data-ttu-id="eb183-119">Selon la transformation, effectuez l'une des opérations suivantes pour générer une expression :</span><span class="sxs-lookup"><span data-stu-id="eb183-119">Depending on the transformation, do one of the following to build an expression:</span></span>  
  
    -   <span data-ttu-id="eb183-120">Dans la boîte de dialogue **Éditeur de transformation de fractionnement conditionnel** , faites glisser les variables, colonnes, fonctions, conversions et opérateurs vers la colonne **Condition** .</span><span class="sxs-lookup"><span data-stu-id="eb183-120">In the **Conditional Split Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Condition** column.</span></span> <span data-ttu-id="eb183-121">Vous pouvez également aussi taper une expression directement dans la colonne **Condition** .</span><span class="sxs-lookup"><span data-stu-id="eb183-121">Alternatively, you can type an expression directly in the **Condition** column.</span></span>  
  
    -   <span data-ttu-id="eb183-122">Dans la boîte de dialogue **Éditeur de transformation de colonne dérivée** , faites glisser les variables, colonnes, fonctions, conversions et opérateurs vers la colonne **Expression** .</span><span class="sxs-lookup"><span data-stu-id="eb183-122">In the **Derived Column Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Expression** column.</span></span> <span data-ttu-id="eb183-123">Vous pouvez également taper une expression directement dans la colonne **Expression** .</span><span class="sxs-lookup"><span data-stu-id="eb183-123">Alternatively, you can type an expression directly in the **Expression** column.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="eb183-124">Quand la colonne **Condition** ou **Expression** n’est plus active, le texte de l’expression peut être mis en surbrillance, ce qui indique que la syntaxe de l’expression est incorrecte.</span><span class="sxs-lookup"><span data-stu-id="eb183-124">When you remove the focus from the **Condition** column or the **Expression** column, the expression text might be highlighted to indicate that the expression syntax is incorrect.</span></span>  
  
10. <span data-ttu-id="eb183-125">Cliquez sur **OK** pour quitter la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="eb183-125">Click **OK** to exit the dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eb183-126">Si l'expression n'est pas valide, une alerte apparaît et décrit les erreurs de syntaxe de l'expression.</span><span class="sxs-lookup"><span data-stu-id="eb183-126">If the expression is not valid, an alert appears describing the syntax errors in the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb183-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eb183-127">See Also</span></span>  
 <span data-ttu-id="eb183-128">[Integration Services &#40;des expressions de&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="eb183-128">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="eb183-129">[Transformation de fractionnement conditionnel](data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="eb183-129">[Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="eb183-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="eb183-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span></span>  
 <span data-ttu-id="eb183-131">[Tâche de flux de données](control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="eb183-131">[Data Flow Task](control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="eb183-132">Flux de données</span><span class="sxs-lookup"><span data-stu-id="eb183-132">Data Flow</span></span>](data-flow/data-flow.md)  
  
  
