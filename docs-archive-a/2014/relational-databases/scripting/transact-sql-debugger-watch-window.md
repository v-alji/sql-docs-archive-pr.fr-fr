---
title: Espion (fenêtre)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Watch Window [Transact-SQL]
ms.assetid: 23f3baa4-14c2-4262-92f7-3f43fcfa0436
author: rothja
ms.author: jroth
ms.openlocfilehash: c2a3db9b095902fcb5620af91fb86d80f773d606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612215"
---
# <a name="watch-window"></a><span data-ttu-id="8f0d0-102">Espion (fenêtre)</span><span class="sxs-lookup"><span data-stu-id="8f0d0-102">Watch Window</span></span>
  <span data-ttu-id="8f0d0-103">La fenêtre **Espion** affiche des informations sur les expressions que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-103">The **Watch** window displays information about the expressions that you have selected.</span></span> <span data-ttu-id="8f0d0-104">Les fenêtres Espion peuvent être au nombre de quatre, au maximum : **Espion 1**, **Espion 2, Espion 3**et **Espion 4**.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-104">There can be up to four watch windows: **Watch 1**, **Watch 2, Watch 3**, and **Watch 4**.</span></span> <span data-ttu-id="8f0d0-105">Les expressions sont évaluées dans l’étendue du frame de pile des appels actuellement sélectionné dans la fenêtre **Pile des appels** .</span><span class="sxs-lookup"><span data-stu-id="8f0d0-105">The expressions are evaluated within the scope of the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="8f0d0-106">Vous devez être en mode débogage pour surveiller les variables et les expressions.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-106">You must be in debug mode to watch variables and expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="8f0d0-107">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="8f0d0-107">Task List</span></span>  
 <span data-ttu-id="8f0d0-108">**Pour accéder aux fenêtres Espion**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-108">**To access the Watch windows**</span></span>  
  
-   <span data-ttu-id="8f0d0-109">Dans le menu **Déboguer** , cliquez sur **Fenêtres**, sur **Espion**puis sur **Espion 1**, **Espion 2, Espion 3**ou **Espion 4**.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-109">On the **Debug** menu, click **Windows**, click **Watch**, and then click **Watch 1**, **Watch 2, Watch 3**, or **Watch 4**.</span></span>  
  
 <span data-ttu-id="8f0d0-110">**Pour modifier la valeur d'une expression**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-110">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="8f0d0-111">Cliquez avec le bouton droit sur l’expression, puis sélectionnez **Modifier la valeur**.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-111">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="8f0d0-112">Colonnes</span><span class="sxs-lookup"><span data-stu-id="8f0d0-112">Columns</span></span>  
 <span data-ttu-id="8f0d0-113">**Nom**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-113">**Name**</span></span>  
 <span data-ttu-id="8f0d0-114">Expressions répertoriées par le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f0d0-114">Are the expressions that are listed by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="8f0d0-115">Les expressions suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="8f0d0-115">The following expressions are supported:</span></span>  
  
-   <span data-ttu-id="8f0d0-116">variables ;</span><span class="sxs-lookup"><span data-stu-id="8f0d0-116">Variables.</span></span>  
  
-   <span data-ttu-id="8f0d0-117">Paramètres.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-117">Parameters.</span></span>  
  
-   <span data-ttu-id="8f0d0-118">Fonctions système dont le nom commence par @@.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-118">System functions whose name starts with @@.</span></span>  
  
-   <span data-ttu-id="8f0d0-119">Expressions générées par l’application d’opérateurs à une ou plusieurs variables, un ou plusieurs paramètres ou une ou plusieurs fonctions système, comme @IntegerCounter + 1 ou FirstName + LastName.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-119">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
-   <span data-ttu-id="8f0d0-120">Instructions Transact-SQL qui retournent une seule valeur, par exemple : SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-120">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
 <span data-ttu-id="8f0d0-121">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-121">**Value**</span></span>  
 <span data-ttu-id="8f0d0-122">Affiche la valeur retournée après que le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] a évalué l’expression spécifiée dans **Nom**.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-122">Displays the value that is returned after the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger evaluates the expression specified in **Name**.</span></span>  
  
 <span data-ttu-id="8f0d0-123">Si la longueur d'une expression dépasse la largeur de la colonne **Valeur** , une info-bulle affiche la valeur complète lorsque vous placez le pointeur sur la cellule **Valeur** de cette expression.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-123">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="8f0d0-124">La présence d'une icône de loupe dans une cellule **Valeur** indique que le visualiseur du débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] est disponible.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-124">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="8f0d0-125">Dans la liste, vous pouvez spécifier **Visualiseur de texte**, **Visualiseur XML**ou **Visualiseur HTML**.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-125">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="8f0d0-126">Pour démarrer un visualiseur du débogueur, cliquez sur l'icône de loupe.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-126">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="8f0d0-127">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] ouvre une boîte de dialogue qui affiche les données dans un format adapté au type de données.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="8f0d0-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="8f0d0-128">**Type**</span></span>  
 <span data-ttu-id="8f0d0-129">Affiche le type de données de l'expression.</span><span class="sxs-lookup"><span data-stu-id="8f0d0-129">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f0d0-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8f0d0-130">See Also</span></span>  
 <span data-ttu-id="8f0d0-131">[Débogueur Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="8f0d0-131">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="8f0d0-132">[Informations du débogueur Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="8f0d0-132">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="8f0d0-133">[Variables locales (fenêtre)](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="8f0d0-133">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="8f0d0-134">[Fenêtre Pile des appels](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="8f0d0-134">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="8f0d0-135">[Boîte de dialogue Espion express](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="8f0d0-135">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="8f0d0-136">Expressions &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8f0d0-136">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
