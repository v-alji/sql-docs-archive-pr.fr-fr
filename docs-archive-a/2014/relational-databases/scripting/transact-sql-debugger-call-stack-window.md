---
title: Fenêtre Pile des appels
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Call Stack Window [Transact-SQL]
ms.assetid: ddb0b19c-87cd-4883-bcb8-ec09ffb30369
author: rothja
ms.author: jroth
ms.openlocfilehash: b4b72e484ade696be81ebac8ea4eed9be295edf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613409"
---
# <a name="call-stack-window"></a><span data-ttu-id="b9c61-102">Fenêtre Pile des appels</span><span class="sxs-lookup"><span data-stu-id="b9c61-102">Call Stack Window</span></span>
  <span data-ttu-id="b9c61-103">La fenêtre **Pile des appels** affiche les modules de la pile des appels, ainsi que les types de données et les valeurs des paramètres transmis aux modules.</span><span class="sxs-lookup"><span data-stu-id="b9c61-103">The **Call Stack** window displays the modules on the call stack, and the data types and values of any parameters that are passed to the modules.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="b9c61-104">Les modules incluent des déclencheurs, des fonctions et des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="b9c61-104">modules include stored procedures, functions, and triggers.</span></span> <span data-ttu-id="b9c61-105">Pour afficher la pile des appels, vous devez être en mode débogage.</span><span class="sxs-lookup"><span data-stu-id="b9c61-105">To display the call stack, you must be in debug mode.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="b9c61-106">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="b9c61-106">Task List</span></span>  
 <span data-ttu-id="b9c61-107">**Pour accéder à la fenêtre Pile des appels**</span><span class="sxs-lookup"><span data-stu-id="b9c61-107">**To access the Call Stack window**</span></span>  
  
-   <span data-ttu-id="b9c61-108">Dans le menu **Déboguer** , cliquez sur **Fenêtres**, puis sur **Pile des appels**.</span><span class="sxs-lookup"><span data-stu-id="b9c61-108">On the **Debug** menu, click **Windows**, and then click **Call Stack**.</span></span>  
  
 <span data-ttu-id="b9c61-109">**Pour modifier le frame de pile des appels actuel**</span><span class="sxs-lookup"><span data-stu-id="b9c61-109">**To change the current Call Stack frame**</span></span>  
  
 <span data-ttu-id="b9c61-110">Vous pouvez utiliser l'une des procédures suivantes pour faire d'un frame de pile le frame actuel :</span><span class="sxs-lookup"><span data-stu-id="b9c61-110">You can use either of the following procedures to make a stack frame the current frame:</span></span>  
  
-   <span data-ttu-id="b9c61-111">Cliquez avec le bouton droit sur le frame de pile, puis cliquez sur **Basculer vers le frame**.</span><span class="sxs-lookup"><span data-stu-id="b9c61-111">Right-click the stack frame, and then click **Switch To Frame**.</span></span>  
  
-   <span data-ttu-id="b9c61-112">Double-cliquez sur le frame de pile.</span><span class="sxs-lookup"><span data-stu-id="b9c61-112">Double-click the stack frame.</span></span>  
  
 <span data-ttu-id="b9c61-113">**Pour afficher la source d'un frame autre que le frame actuel**</span><span class="sxs-lookup"><span data-stu-id="b9c61-113">**To view the source of a frame other than the current frame**</span></span>  
  
-   <span data-ttu-id="b9c61-114">Cliquez avec le bouton droit sur le frame de pile, puis cliquez sur **Atteindre le code source**.</span><span class="sxs-lookup"><span data-stu-id="b9c61-114">Right-click the stack frame, and then click **Go To Source Code**.</span></span>  
  
## <a name="stack-frames"></a><span data-ttu-id="b9c61-115">Frames de pile</span><span class="sxs-lookup"><span data-stu-id="b9c61-115">Stack Frames</span></span>  
 <span data-ttu-id="b9c61-116">Chaque ligne figurant dans la fenêtre **Pile des appels[!INCLUDE[tsql](../../includes/tsql-md.md)] s’appelle un frame de pile et représente soit un appel d’un fichier de script** à un module, soit un appel d’un module à un autre.</span><span class="sxs-lookup"><span data-stu-id="b9c61-116">Each row in the **Call Stack** window is called a stack frame and represents either a call from a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file to a module or a call from one module to another.</span></span> <span data-ttu-id="b9c61-117">Le frame de pile qui figure au bas de l’écran représente la ligne de la fenêtre de l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] qui a effectué le premier appel dans la pile.</span><span class="sxs-lookup"><span data-stu-id="b9c61-117">The bottom stack frame in the display indicates the line in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window that made the first call into the stack.</span></span> <span data-ttu-id="b9c61-118">La ligne du haut représente la ligne dans laquelle le débogueur a suspendu l’exécution ; elle est identifiée par une flèche jaune dans la marge de gauche de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="b9c61-118">The top row indicates the line on which the debugger paused execution, and is identified by a yellow arrow in the left margin of the window.</span></span> <span data-ttu-id="b9c61-119">Chaque ligne intermédiaire indique le module et le numéro de ligne du code source qui a appelé le frame de pile situé immédiatement au-dessus.</span><span class="sxs-lookup"><span data-stu-id="b9c61-119">Each intermediate row indicates the module and the line number of the source code that called the next higher stack frame.</span></span>  
  
 <span data-ttu-id="b9c61-120">Toutes les expressions figurant dans les fenêtres **Variables locales**, **Espion**et **Espion express** sont évaluées en fonction du frame de pile actuel.</span><span class="sxs-lookup"><span data-stu-id="b9c61-120">All expressions in the **Locals**, **Watch**, and **QuickWatch** windows are evaluated based on the current stack frame.</span></span> <span data-ttu-id="b9c61-121">La fenêtre de l'éditeur de requête affiche le code pour le frame actuel.</span><span class="sxs-lookup"><span data-stu-id="b9c61-121">The Query Editor window displays the code for the current frame.</span></span> <span data-ttu-id="b9c61-122">Par défaut, le frame de pile actuel est le frame dans lequel le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] a suspendu l’exécution.</span><span class="sxs-lookup"><span data-stu-id="b9c61-122">By default, the current stack frame is the frame in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger paused execution.</span></span> <span data-ttu-id="b9c61-123">Quand vous passez du frame de pile actuel à un autre frame, les expressions contenues dans les fenêtres **Variables locales**, **Espion**et **Espion express** sont réévaluées dans le contexte du nouveau frame, et le code source du nouveau frame est affiché dans la fenêtre de l’éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="b9c61-123">When you change the current stack frame to another frame, the expressions in the **Locals**, **Watch**, and **QuickWatch** windows are reevaluated in the context of the new frame, and the source code of the new frame is displayed in the Query Editor window.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="b9c61-124">Colonnes</span><span class="sxs-lookup"><span data-stu-id="b9c61-124">Columns</span></span>  
 <span data-ttu-id="b9c61-125">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b9c61-125">**Name**</span></span>  
 <span data-ttu-id="b9c61-126">Affiche les informations relatives à un module de la pile des appels.</span><span class="sxs-lookup"><span data-stu-id="b9c61-126">Displays information about a module on the call stack.</span></span>  
  
 <span data-ttu-id="b9c61-127">Pour la ligne inférieure de la pile des appels, **Nom** répertorie la fenêtre source de l’éditeur de requête et le numéro de ligne du premier appel de la pile.</span><span class="sxs-lookup"><span data-stu-id="b9c61-127">For the bottom row in the call stack, **Name** lists the Query Editor source window and line number of the first call into the stack.</span></span> <span data-ttu-id="b9c61-128">Pour les autres lignes, **Nom** présente le format **Module(Instance.Database)(ParmList) LineNumber**.</span><span class="sxs-lookup"><span data-stu-id="b9c61-128">For the other rows, **Name** has the format **Module(Instance.Database)(ParmList) LineNumber**.</span></span>  
  
 <span data-ttu-id="b9c61-129">**Module**</span><span class="sxs-lookup"><span data-stu-id="b9c61-129">**Module**</span></span>  
 <span data-ttu-id="b9c61-130">Nom de la procédure stockée ou de la fonction qui a appelé le frame suivant.</span><span class="sxs-lookup"><span data-stu-id="b9c61-130">Is the name of the stored procedure, function, or stored procedure that called to the next frame.</span></span>  
  
 <span data-ttu-id="b9c61-131">**Instance.Database**</span><span class="sxs-lookup"><span data-stu-id="b9c61-131">**Instance.Database**</span></span>  
 <span data-ttu-id="b9c61-132">Instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et base de données qui détiennent le module.</span><span class="sxs-lookup"><span data-stu-id="b9c61-132">Is the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the database that is holding the module.</span></span>  
  
 <span data-ttu-id="b9c61-133">**ParmList**</span><span class="sxs-lookup"><span data-stu-id="b9c61-133">**ParmList**</span></span>  
 <span data-ttu-id="b9c61-134">Indique le type de données, le nom et la valeur de chaque paramètre transmis lors de l'appel au module.</span><span class="sxs-lookup"><span data-stu-id="b9c61-134">Indicates the data type, name, and value for each parameter that is passed in during the call to the module.</span></span>  
  
 <span data-ttu-id="b9c61-135">**LineNumber**</span><span class="sxs-lookup"><span data-stu-id="b9c61-135">**LineNumber**</span></span>  
 <span data-ttu-id="b9c61-136">Pour toutes les lignes à l’exception de la ligne du haut, **LineNumber** indique la ligne du module qui a appelé le frame.</span><span class="sxs-lookup"><span data-stu-id="b9c61-136">For all rows except the top row, **LineNumber** indicates which line in the module called to the frame.</span></span> <span data-ttu-id="b9c61-137">Pour la ligne du haut, **LineNumber** indique la ligne que le débogueur est en train de traiter.</span><span class="sxs-lookup"><span data-stu-id="b9c61-137">For the top row, **LineNumber** indicates the line on which the debugger is currently focused.</span></span>  
  
 <span data-ttu-id="b9c61-138">**Langage**</span><span class="sxs-lookup"><span data-stu-id="b9c61-138">**Language**</span></span>  
 <span data-ttu-id="b9c61-139">Affiche **Transact-SQL** pour [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9c61-139">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c61-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9c61-140">See Also</span></span>  
 <span data-ttu-id="b9c61-141">[Débogueur Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="b9c61-141">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="b9c61-142">[Informations sur le débogueur Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="b9c61-142">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 [<span data-ttu-id="b9c61-143">Exécuter pas à pas du code Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9c61-143">Step Through Transact-SQL Code</span></span>](step-through-transact-sql-code.md)  
