---
title: Exécuter pas à pas du code Transact-SQL
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, debugging code
- Transact-SQL debugger, step over
- Transact-SQL debugger, step out
- Transact-SQL debugger, step into
ms.assetid: e09079b8-c4c9-42b4-821b-4ce81a98a086
author: rothja
ms.author: jroth
ms.openlocfilehash: 48cb307130c65729640864a26bdf1dfaf344b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612757"
---
# <a name="step-through-transact-sql-code"></a><span data-ttu-id="246a2-102">Exécuter pas à pas du code Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="246a2-102">Step Through Transact-SQL Code</span></span>
  <span data-ttu-id="246a2-103">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] vous permet de contrôler les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] qui sont exécutées dans une fenêtre de l'éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="246a2-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger enables you to control which [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are run in a [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span> <span data-ttu-id="246a2-104">Vous pouvez suspendre le débogueur au niveau d'instructions individuelles, puis afficher l'état des éléments de code à ce stade.</span><span class="sxs-lookup"><span data-stu-id="246a2-104">You can pause the debugger on individual statements and then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="246a2-105">Points d’arrêt</span><span class="sxs-lookup"><span data-stu-id="246a2-105">Breakpoints</span></span>  
 <span data-ttu-id="246a2-106">Un point d'arrêt indique au débogueur de suspendre l'exécution à une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] spécifique.</span><span class="sxs-lookup"><span data-stu-id="246a2-106">A breakpoint signals the debugger to pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="246a2-107">Pour plus d'informations sur les points d'arrêt, consultez Utilisation de points d'arrêt Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="246a2-107">For more information about breakpoints, see Using Transact-SQL Breakpoints.</span></span>  
  
## <a name="controlling-statement-execution"></a><span data-ttu-id="246a2-108">Contrôle de l'exécution d'instructions</span><span class="sxs-lookup"><span data-stu-id="246a2-108">Controlling Statement Execution</span></span>  
 <span data-ttu-id="246a2-109">Dans le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] , vous pouvez spécifier les options suivantes pour exécuter le code [!INCLUDE[tsql](../../includes/tsql-md.md)] à partir de l'instruction actuelle :</span><span class="sxs-lookup"><span data-stu-id="246a2-109">In the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can specify the following options for executing from the current statement in [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
-   <span data-ttu-id="246a2-110">Exécuter le code jusqu'au point d'arrêt suivant.</span><span class="sxs-lookup"><span data-stu-id="246a2-110">Run to the next breakpoint.</span></span>  
  
-   <span data-ttu-id="246a2-111">Effectuer un pas à pas détaillé dans l'instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="246a2-111">Step into the next statement.</span></span>  
  
     <span data-ttu-id="246a2-112">Si l'instruction suivante appelle une procédure stockée, une fonction ou un déclencheur [!INCLUDE[tsql](../../includes/tsql-md.md)] , le débogueur affiche une nouvelle fenêtre de l'éditeur de requête contenant le code du module.</span><span class="sxs-lookup"><span data-stu-id="246a2-112">If the next statement invokes a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, function, or trigger, the debugger displays a new Query Editor window that contains the code of the module.</span></span> <span data-ttu-id="246a2-113">La fenêtre est en mode débogage, et l'exécution s'arrête à la première instruction dans le module.</span><span class="sxs-lookup"><span data-stu-id="246a2-113">The window is in debug mode, and execution pauses on the first statement in the module.</span></span> <span data-ttu-id="246a2-114">Vous pouvez ensuite parcourir le code du module, en définissant par exemple des points d'arrêt ou en exécutant le code pas à pas.</span><span class="sxs-lookup"><span data-stu-id="246a2-114">You can then move through the module code, for example, by setting breakpoints or stepping through the code.</span></span>  
  
-   <span data-ttu-id="246a2-115">Effectuer un pas à pas principal dans l'instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="246a2-115">Step over the next statement.</span></span>  
  
     <span data-ttu-id="246a2-116">L'instruction suivante est exécutée.</span><span class="sxs-lookup"><span data-stu-id="246a2-116">The next statement is executed.</span></span> <span data-ttu-id="246a2-117">Toutefois, si l'instruction appelle une procédure stockée, une fonction ou un déclencheur, le code de module s'exécute jusqu'à ce qu'il se termine, et les résultats sont retournés au code appelant.</span><span class="sxs-lookup"><span data-stu-id="246a2-117">However, if the statement invokes a stored procedure, function, or trigger, the module code runs until it finishes, and the results are returned to the calling code.</span></span> <span data-ttu-id="246a2-118">Si vous êtes certain qu'une procédure stockée ne comporte aucune erreur, vous pouvez faire un pas à pas principal.</span><span class="sxs-lookup"><span data-stu-id="246a2-118">If you are sure there are no errors in a stored procedure, you can step over it.</span></span> <span data-ttu-id="246a2-119">L'exécution s'arrête à l'instruction qui suit l'appel à la procédure stockée, à la fonction ou au déclencheur.</span><span class="sxs-lookup"><span data-stu-id="246a2-119">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="246a2-120">Effectuer un pas à pas sortant dans une procédure stockée, une fonction ou un déclencheur.</span><span class="sxs-lookup"><span data-stu-id="246a2-120">Step out of a stored procedure, function, or trigger.</span></span>  
  
     <span data-ttu-id="246a2-121">L'exécution s'arrête à l'instruction qui suit l'appel à la procédure stockée, à la fonction ou au déclencheur.</span><span class="sxs-lookup"><span data-stu-id="246a2-121">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="246a2-122">Exécuter le code à partir de l'emplacement actuel jusqu'à l'emplacement actuel du pointeur et ignorer tous les points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="246a2-122">Run from the current location to the current location of the pointer, and ignore all breakpoints.</span></span>  
  
 <span data-ttu-id="246a2-123">Le tableau suivant répertorie les différentes façons dont vous pouvez contrôler l'exécution des instructions dans le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="246a2-123">The following table lists the various ways in which you can control how statements execute in the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span>  
  
|<span data-ttu-id="246a2-124">Action</span><span class="sxs-lookup"><span data-stu-id="246a2-124">Action</span></span>|<span data-ttu-id="246a2-125">Procédure</span><span class="sxs-lookup"><span data-stu-id="246a2-125">Procedure</span></span>|  
|------------|---------------|  
|<span data-ttu-id="246a2-126">Exécuter toutes les instructions à partir de l'instruction actuelle jusqu'au point d'arrêt suivant</span><span class="sxs-lookup"><span data-stu-id="246a2-126">Run all statements from the current statement to the next breakpoint</span></span>|<span data-ttu-id="246a2-127">Dans le menu **Déboguer**, cliquez sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="246a2-127">On the **Debug** menu, click **Continue**.</span></span><br /><br /> <span data-ttu-id="246a2-128">Dans la barre d’outils **Déboguer** , cliquez sur le bouton **Continuer** .</span><span class="sxs-lookup"><span data-stu-id="246a2-128">On the **Debug** toolbar, click the **Continue** button.</span></span>|  
|<span data-ttu-id="246a2-129">Effectuer un pas à pas détaillé dans l'instruction ou le module suivant</span><span class="sxs-lookup"><span data-stu-id="246a2-129">Step into the next statement or module</span></span>|<span data-ttu-id="246a2-130">Dans le menu **Déboguer** , cliquez sur **pas à pas détaillé**.</span><span class="sxs-lookup"><span data-stu-id="246a2-130">On the **Debug** menu, click **Step Into**.</span></span><br /><br /> <span data-ttu-id="246a2-131">Dans la barre d’outils **Déboguer** , cliquez sur le bouton **pas à pas détaillé** .</span><span class="sxs-lookup"><span data-stu-id="246a2-131">On the **Debug** toolbar, click the **Step Into** button.</span></span><br /><br /> <span data-ttu-id="246a2-132">Appuyez sur F11.</span><span class="sxs-lookup"><span data-stu-id="246a2-132">Press F11.</span></span>|  
|<span data-ttu-id="246a2-133">Effectuer un pas à pas principal dans l'instruction ou le module suivant</span><span class="sxs-lookup"><span data-stu-id="246a2-133">Step over the next statement or module</span></span>|<span data-ttu-id="246a2-134">Dans le menu **Déboguer**, cliquez sur **Pas à pas principal**.</span><span class="sxs-lookup"><span data-stu-id="246a2-134">On the **Debug** menu, click **Step Over**.</span></span><br /><br /> <span data-ttu-id="246a2-135">Dans la barre d’outils **Déboguer** , cliquez sur le bouton **pas à pas principal** .</span><span class="sxs-lookup"><span data-stu-id="246a2-135">On the **Debug** toolbar, click the **Step Over** button.</span></span><br /><br /> <span data-ttu-id="246a2-136">Appuyez sur F10.</span><span class="sxs-lookup"><span data-stu-id="246a2-136">Press F10.</span></span>|  
|<span data-ttu-id="246a2-137">Effectuer un pas à pas sortant dans un module</span><span class="sxs-lookup"><span data-stu-id="246a2-137">Step out of a module</span></span>|<span data-ttu-id="246a2-138">Dans le menu **Déboguer** , cliquez sur **pas à pas sortant**.</span><span class="sxs-lookup"><span data-stu-id="246a2-138">On the **Debug** menu, click **Step Out**.</span></span><br /><br /> <span data-ttu-id="246a2-139">Dans la barre d’outils **Déboguer** , cliquez sur le bouton **pas à pas sortant** .</span><span class="sxs-lookup"><span data-stu-id="246a2-139">On the **Debug** toolbar, click the **Step Out** button.</span></span><br /><br /> <span data-ttu-id="246a2-140">Appuyez sur Maj+F11.</span><span class="sxs-lookup"><span data-stu-id="246a2-140">Press SHIFT+F11.</span></span>|  
|<span data-ttu-id="246a2-141">Exécuter le code jusqu'à l'emplacement du curseur actuel</span><span class="sxs-lookup"><span data-stu-id="246a2-141">Run to the current cursor location</span></span>|<span data-ttu-id="246a2-142">Cliquez avec le bouton droit dans la fenêtre de l’éditeur de requête, puis cliquez sur **Exécuter jusqu’au curseur**.</span><span class="sxs-lookup"><span data-stu-id="246a2-142">Right-click in the Query Editor window, and then click **Run To Cursor**.</span></span><br /><br /> <span data-ttu-id="246a2-143">Appuyez sur Ctrl+F10.</span><span class="sxs-lookup"><span data-stu-id="246a2-143">Press CTRL+F10.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="246a2-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="246a2-144">See Also</span></span>  
 [<span data-ttu-id="246a2-145">Informations du débogueur Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="246a2-145">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
