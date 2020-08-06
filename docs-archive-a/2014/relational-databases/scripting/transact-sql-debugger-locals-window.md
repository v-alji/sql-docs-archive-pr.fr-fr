---
title: Variables locales (fenêtre)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Locals Window [Transact-SQL]
ms.assetid: 59bea640-7823-4b4d-832c-f384d83cca2f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f8f62eb69a50d7543af41dddb9c62c842d17151
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613957"
---
# <a name="locals-window"></a><span data-ttu-id="6fc59-102">Variables locales (fenêtre)</span><span class="sxs-lookup"><span data-stu-id="6fc59-102">Locals Window</span></span>
  <span data-ttu-id="6fc59-103">La fenêtre **Variables locales** affiche des informations sur les expressions locales dans l'étendue actuelle du débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6fc59-103">The **Locals** window displays information about the local expressions in the current scope of the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="6fc59-104">L'étendue est définie selon le frame de pile des appels actuellement sélectionné dans la fenêtre **Pile des appels** .</span><span class="sxs-lookup"><span data-stu-id="6fc59-104">The scope is set to the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="6fc59-105">Vous devez être en mode débogage pour afficher les expressions locales.</span><span class="sxs-lookup"><span data-stu-id="6fc59-105">You must be in debug mode to display the local expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="6fc59-106">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="6fc59-106">Task List</span></span>  
 <span data-ttu-id="6fc59-107">**Pour accéder à la fenêtre Variables locales**</span><span class="sxs-lookup"><span data-stu-id="6fc59-107">**To access the Locals window**</span></span>  
  
-   <span data-ttu-id="6fc59-108">Dans le menu **Déboguer** , cliquez sur **Fenêtres**, puis sur **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="6fc59-108">On the **Debug** menu, click **Windows**, and then click **Locals**.</span></span>  
  
 <span data-ttu-id="6fc59-109">**Pour modifier la valeur d'une expression**</span><span class="sxs-lookup"><span data-stu-id="6fc59-109">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="6fc59-110">Cliquez avec le bouton droit sur l’expression, puis sélectionnez **Modifier la valeur**.</span><span class="sxs-lookup"><span data-stu-id="6fc59-110">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="6fc59-111">Colonnes</span><span class="sxs-lookup"><span data-stu-id="6fc59-111">Columns</span></span>  
 <span data-ttu-id="6fc59-112">**Nom**</span><span class="sxs-lookup"><span data-stu-id="6fc59-112">**Name**</span></span>  
 <span data-ttu-id="6fc59-113">Nom de l'expression locale.</span><span class="sxs-lookup"><span data-stu-id="6fc59-113">Is the name of the local expression.</span></span> <span data-ttu-id="6fc59-114">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] répertorie les variables, les paramètres et les fonctions système dont les noms commencent par @@.</span><span class="sxs-lookup"><span data-stu-id="6fc59-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger lists variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="6fc59-115">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="6fc59-115">**Value**</span></span>  
 <span data-ttu-id="6fc59-116">Affiche la valeur actuellement assignée à l'expression locale.</span><span class="sxs-lookup"><span data-stu-id="6fc59-116">Displays the value that is currently assigned to the local expression.</span></span> <span data-ttu-id="6fc59-117">Cette colonne est vide si aucune valeur n'a été assignée à l'expression.</span><span class="sxs-lookup"><span data-stu-id="6fc59-117">This column is blank when no value has been assigned to the expression.</span></span>  
  
 <span data-ttu-id="6fc59-118">Si la longueur d'une expression dépasse la largeur de la colonne **Valeur** , une info-bulle affiche la valeur complète lorsque vous placez le pointeur sur la cellule **Valeur** de cette expression.</span><span class="sxs-lookup"><span data-stu-id="6fc59-118">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="6fc59-119">La présence d'une icône de loupe dans une cellule **Valeur** indique que le visualiseur du débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] est disponible.</span><span class="sxs-lookup"><span data-stu-id="6fc59-119">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="6fc59-120">Dans la liste, vous pouvez spécifier **Visualiseur de texte**, **Visualiseur XML**ou **Visualiseur HTML**.</span><span class="sxs-lookup"><span data-stu-id="6fc59-120">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="6fc59-121">Pour démarrer un visualiseur du débogueur, cliquez sur l'icône de loupe.</span><span class="sxs-lookup"><span data-stu-id="6fc59-121">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="6fc59-122">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] ouvre une boîte de dialogue qui affiche les données dans un format adapté au type de données.</span><span class="sxs-lookup"><span data-stu-id="6fc59-122">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="6fc59-123">**Type**</span><span class="sxs-lookup"><span data-stu-id="6fc59-123">**Type**</span></span>  
 <span data-ttu-id="6fc59-124">Affiche le type de données de l'expression.</span><span class="sxs-lookup"><span data-stu-id="6fc59-124">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc59-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6fc59-125">See Also</span></span>  
 <span data-ttu-id="6fc59-126">[Débogueur Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="6fc59-126">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="6fc59-127">[Informations du débogueur Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="6fc59-127">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="6fc59-128">[Espion (fenêtre)](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="6fc59-128">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="6fc59-129">[Fenêtre Pile des appels](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="6fc59-129">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="6fc59-130">[Boîte de dialogue Espion express](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="6fc59-130">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="6fc59-131">Expressions &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6fc59-131">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
