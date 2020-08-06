---
title: Boîte de dialogue Espion express
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.quickwatch
helpviewer_keywords:
- QuickWatch Dialog [Transact-SQL]
ms.assetid: d6bbb373-1452-41f2-bdc5-86ae689c3dc0
author: rothja
ms.author: jroth
ms.openlocfilehash: 48e4bda558b75bec0c81815c90feff9d6500a803
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613955"
---
# <a name="quickwatch-dialog-box"></a><span data-ttu-id="6cf72-102">Boîte de dialogue Espion express</span><span class="sxs-lookup"><span data-stu-id="6cf72-102">QuickWatch Dialog Box</span></span>
  <span data-ttu-id="6cf72-103">Utilisez la boîte de dialogue **Espion express** pour consulter rapidement le type de données et la valeur d’une expression [!INCLUDE[tsql](../../includes/tsql-md.md)] (par exemple, une variable ou un paramètre) pendant que vous déboguez le code [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cf72-103">Use the **QuickWatch** dialog box to quickly view the data type and value of one [!INCLUDE[tsql](../../includes/tsql-md.md)] expression, such as a variable or parameter, when you are debugging [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="6cf72-104">Pour surveiller plusieurs expressions, vous pouvez également ajouter l’expression à une fenêtre **Espion** .</span><span class="sxs-lookup"><span data-stu-id="6cf72-104">To watch multiple expressions, you can also add the expression to a **Watch** window.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="6cf72-105">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="6cf72-105">Task List</span></span>  
 <span data-ttu-id="6cf72-106">**Pour accéder à la boîte de dialogue Espion express**</span><span class="sxs-lookup"><span data-stu-id="6cf72-106">**To access the QuickWatch dialog box**</span></span>  
  
-   <span data-ttu-id="6cf72-107">Dans le menu **Déboguer** , cliquez sur **Espion express**.</span><span class="sxs-lookup"><span data-stu-id="6cf72-107">On the **Debug** menu, click **QuickWatch**.</span></span>  
  
 <span data-ttu-id="6cf72-108">**Pour afficher les informations relatives à une expression**</span><span class="sxs-lookup"><span data-stu-id="6cf72-108">**To view the information about an expression**</span></span>  
  
1.  <span data-ttu-id="6cf72-109">Dans la zone de liste **Expression** , tapez ou sélectionnez l’expression souhaitée.</span><span class="sxs-lookup"><span data-stu-id="6cf72-109">In the **Expression** list box, type or select the expression that you want.</span></span> <span data-ttu-id="6cf72-110">Les expressions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="6cf72-110">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] expressions are supported:</span></span>  
  
    -   <span data-ttu-id="6cf72-111">variables ;</span><span class="sxs-lookup"><span data-stu-id="6cf72-111">Variables.</span></span>  
  
    -   <span data-ttu-id="6cf72-112">Paramètres.</span><span class="sxs-lookup"><span data-stu-id="6cf72-112">Parameters.</span></span>  
  
    -   <span data-ttu-id="6cf72-113">Fonctions système dont le nom commence par @@.</span><span class="sxs-lookup"><span data-stu-id="6cf72-113">System functions whose name starts with @@.</span></span>  
  
    -   <span data-ttu-id="6cf72-114">Expressions générées par l’application d’opérateurs à une ou plusieurs variables, un ou plusieurs paramètres ou une ou plusieurs fonctions système, comme @IntegerCounter + 1 ou FirstName + LastName.</span><span class="sxs-lookup"><span data-stu-id="6cf72-114">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
    -   <span data-ttu-id="6cf72-115">Instructions Transact-SQL qui retournent une seule valeur, par exemple : SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span><span class="sxs-lookup"><span data-stu-id="6cf72-115">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
2.  <span data-ttu-id="6cf72-116">Cliquez sur **Réévaluer**.</span><span class="sxs-lookup"><span data-stu-id="6cf72-116">Click **Reevaluate**.</span></span>  
  
 <span data-ttu-id="6cf72-117">**Pour ajouter l'expression Espion express à la fenêtre Espion**</span><span class="sxs-lookup"><span data-stu-id="6cf72-117">**To add the QuickWatch expression to a Watch window**</span></span>  
  
-   <span data-ttu-id="6cf72-118">Cliquez sur **Ajouter un espion**.</span><span class="sxs-lookup"><span data-stu-id="6cf72-118">Click **Add Watch**.</span></span>  
  
 <span data-ttu-id="6cf72-119">**Pour modifier la valeur de l'expression Espion express**</span><span class="sxs-lookup"><span data-stu-id="6cf72-119">**To change the value of the QuickWatch expression**</span></span>  
  
-   <span data-ttu-id="6cf72-120">Cliquez avec le bouton droit sur l’expression, puis sélectionnez **Modifier la valeur**.</span><span class="sxs-lookup"><span data-stu-id="6cf72-120">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6cf72-121">Options</span><span class="sxs-lookup"><span data-stu-id="6cf72-121">Options</span></span>  
 <span data-ttu-id="6cf72-122">**Liste d'expressions**</span><span class="sxs-lookup"><span data-stu-id="6cf72-122">**Expression list**</span></span>  
 <span data-ttu-id="6cf72-123">Affiche l'expression sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6cf72-123">Displays the currently selected expression.</span></span> <span data-ttu-id="6cf72-124">La liste déroulante contient un ensemble d'expressions que vous pouvez choisir d'afficher.</span><span class="sxs-lookup"><span data-stu-id="6cf72-124">The drop-down list contains a set of expressions that you can select to display.</span></span> <span data-ttu-id="6cf72-125">Les expressions présentes dans la liste sont celles qui sont disponibles dans l’étendue du frame de pile sélectionné dans la fenêtre **Pile des appels** .</span><span class="sxs-lookup"><span data-stu-id="6cf72-125">The expressions in the list are those available in the scope of the stack frame that is currently selected in the **Call Stack** window.</span></span> <span data-ttu-id="6cf72-126">Pour afficher une autre expression, entrez-la ou sélectionnez-la dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6cf72-126">To display a different expression, either enter the expression or select it from list.</span></span> <span data-ttu-id="6cf72-127">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] prend en charge les expressions suivantes : variables, paramètres et fonctions système dont les noms commencent par @@.</span><span class="sxs-lookup"><span data-stu-id="6cf72-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports the following expressions: variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="6cf72-128">**Grille Valeur**</span><span class="sxs-lookup"><span data-stu-id="6cf72-128">**Value grid**</span></span>  
 <span data-ttu-id="6cf72-129">Affiche les propriétés de l'expression actuellement surveillée.</span><span class="sxs-lookup"><span data-stu-id="6cf72-129">Displays the properties of the expression that is currently being watched.</span></span>  
  
 <span data-ttu-id="6cf72-130">**Nom**</span><span class="sxs-lookup"><span data-stu-id="6cf72-130">**Name**</span></span>  
 <span data-ttu-id="6cf72-131">Expression [!INCLUDE[tsql](../../includes/tsql-md.md)] actuellement surveillée.</span><span class="sxs-lookup"><span data-stu-id="6cf72-131">Is the [!INCLUDE[tsql](../../includes/tsql-md.md)] expression being watched.</span></span>  
  
 <span data-ttu-id="6cf72-132">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="6cf72-132">**Value**</span></span>  
 <span data-ttu-id="6cf72-133">Affiche la valeur actuellement assignée à l'expression.</span><span class="sxs-lookup"><span data-stu-id="6cf72-133">Displays the value that is currently assigned to the expression.</span></span> <span data-ttu-id="6cf72-134">Si l'expression n'a pas de valeur, un espace est affiché.</span><span class="sxs-lookup"><span data-stu-id="6cf72-134">A blank is displayed when the expression currently has no value.</span></span>  
  
 <span data-ttu-id="6cf72-135">Si la longueur d'une expression dépasse la largeur de la colonne **Valeur** , une info-bulle affiche la valeur complète lorsque vous placez le pointeur sur la cellule **Valeur** de cette expression.</span><span class="sxs-lookup"><span data-stu-id="6cf72-135">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="6cf72-136">La présence d'une icône de loupe dans une cellule **Valeur** indique que le visualiseur du débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] est disponible.</span><span class="sxs-lookup"><span data-stu-id="6cf72-136">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="6cf72-137">Dans la liste, vous pouvez spécifier **Visualiseur de texte**, **Visualiseur XML**ou **Visualiseur HTML**.</span><span class="sxs-lookup"><span data-stu-id="6cf72-137">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="6cf72-138">Pour démarrer un visualiseur du débogueur, cliquez sur l'icône de loupe.</span><span class="sxs-lookup"><span data-stu-id="6cf72-138">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="6cf72-139">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] ouvre une boîte de dialogue qui affiche les données dans un format adapté au type de données.</span><span class="sxs-lookup"><span data-stu-id="6cf72-139">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="6cf72-140">**Type**</span><span class="sxs-lookup"><span data-stu-id="6cf72-140">**Type**</span></span>  
 <span data-ttu-id="6cf72-141">Affiche le type de données de l'expression.</span><span class="sxs-lookup"><span data-stu-id="6cf72-141">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf72-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6cf72-142">See Also</span></span>  
 <span data-ttu-id="6cf72-143">[Débogueur Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="6cf72-143">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="6cf72-144">[Informations du débogueur Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="6cf72-144">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="6cf72-145">[Espion (fenêtre)](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="6cf72-145">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="6cf72-146">[Variables locales (fenêtre)](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="6cf72-146">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="6cf72-147">[Fenêtre Pile des appels](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="6cf72-147">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 [<span data-ttu-id="6cf72-148">Expressions &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6cf72-148">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
  
  
