---
title: Fenêtre Points d'arrêt
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Breakpoints Window [Transact-SQL]
ms.assetid: bad88d10-fdd5-4d3d-b5ea-a4f063847485
author: rothja
ms.author: jroth
ms.openlocfilehash: 077d501e581ed5baaac45cc6bbbb34e0040730e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612748"
---
# <a name="breakpoints-window"></a><span data-ttu-id="480b0-102">Fenêtre Points d'arrêt</span><span class="sxs-lookup"><span data-stu-id="480b0-102">Breakpoints Window</span></span>
  <span data-ttu-id="480b0-103">La fenêtre **Points d’arrêt** répertorie tous les points d’arrêt définis dans l’éditeur de requête actuel du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="480b0-103">The **Breakpoints** window lists all the breakpoints that are set in the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="480b0-104">Pour gérer les points d’arrêt, utilisez la barre d’outils de la fenêtre **Points d’arrêt** .</span><span class="sxs-lookup"><span data-stu-id="480b0-104">To manage the breakpoints, use the toolbar in the **Breakpoints** window.</span></span> <span data-ttu-id="480b0-105">Les points d'arrêt sont des emplacements dans le code où l'exécution s'interrompt en mode débogage pour que vous puissiez consulter les données de débogage.</span><span class="sxs-lookup"><span data-stu-id="480b0-105">Breakpoints are locations in the code where execution pauses in debug mode so that you can view debugging data.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="480b0-106">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="480b0-106">Task List</span></span>  
 <span data-ttu-id="480b0-107">**Pour accéder à la fenêtre Points d'arrêt**</span><span class="sxs-lookup"><span data-stu-id="480b0-107">**To access the Breakpoints window**</span></span>  
  
-   <span data-ttu-id="480b0-108">Dans le menu **Déboguer** , cliquez sur **Fenêtres**, puis sur **Points d'arrêt**.</span><span class="sxs-lookup"><span data-stu-id="480b0-108">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
## <a name="breakpoints-window-columns"></a><span data-ttu-id="480b0-109">Colonnes de la fenêtre Points d'arrêt</span><span class="sxs-lookup"><span data-stu-id="480b0-109">Breakpoints Window Columns</span></span>  
 <span data-ttu-id="480b0-110">Par défaut, la fenêtre **Point d’arrêt** contient les colonnes suivantes.</span><span class="sxs-lookup"><span data-stu-id="480b0-110">By default, the **Breakpoints** window lists the following columns.</span></span>  
  
 <span data-ttu-id="480b0-111">**Nom**</span><span class="sxs-lookup"><span data-stu-id="480b0-111">**Name**</span></span>  
 <span data-ttu-id="480b0-112">Affiche le nom du point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="480b0-112">Displays the name of the breakpoint.</span></span> <span data-ttu-id="480b0-113">Les noms de points d'arrêt sont fournis par le débogueur.</span><span class="sxs-lookup"><span data-stu-id="480b0-113">Breakpoint names are provided by the debugger.</span></span> <span data-ttu-id="480b0-114">Ce nom comprend le nom de la fenêtre de l'éditeur de requête du moteur de base de données qui contient le point d'arrêt, ainsi que le numéro de ligne correspondant au point d'arrêt dans l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="480b0-114">This name includes the name of Database Engine Query Editor window that contains the breakpoint, and the line number in the Query Editor on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="480b0-115">**Condition**</span><span class="sxs-lookup"><span data-stu-id="480b0-115">**Condition**</span></span>  
 <span data-ttu-id="480b0-116">Affiche **(aucune condition)** .</span><span class="sxs-lookup"><span data-stu-id="480b0-116">Displays **(no condition)**.</span></span> <span data-ttu-id="480b0-117">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] ne prend pas en charge la définition de conditions de point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="480b0-117">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint conditions.</span></span>  
  
 <span data-ttu-id="480b0-118">**Nombre d'accès**</span><span class="sxs-lookup"><span data-stu-id="480b0-118">**Hit Count**</span></span>  
 <span data-ttu-id="480b0-119">Affiche**toujours s’arrêter**.</span><span class="sxs-lookup"><span data-stu-id="480b0-119">Displays**breaks always**.</span></span>  
  
 <span data-ttu-id="480b0-120">Vous pouvez ajouter et supprimer les colonnes suivantes en les sélectionnant dans la liste **Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="480b0-120">You can add and remove the following columns by selecting them on the **Columns** list.</span></span>  
  
 <span data-ttu-id="480b0-121">**Filter**</span><span class="sxs-lookup"><span data-stu-id="480b0-121">**Filter**</span></span>  
 <span data-ttu-id="480b0-122">Affiche **(aucun)** .</span><span class="sxs-lookup"><span data-stu-id="480b0-122">Displays **(none)**.</span></span> <span data-ttu-id="480b0-123">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] ne prend pas en charge la définition de filtres de point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="480b0-123">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint filters.</span></span>  
  
 <span data-ttu-id="480b0-124">**Lorsqu'il est atteint**</span><span class="sxs-lookup"><span data-stu-id="480b0-124">**When Hit**</span></span>  
 <span data-ttu-id="480b0-125">Affiche **Arrêter**.</span><span class="sxs-lookup"><span data-stu-id="480b0-125">Displays **Break**.</span></span>  
  
 <span data-ttu-id="480b0-126">**Langage**</span><span class="sxs-lookup"><span data-stu-id="480b0-126">**Language**</span></span>  
 <span data-ttu-id="480b0-127">Affiche **Transact-SQL** pour [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="480b0-127">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="480b0-128">**Fonction**</span><span class="sxs-lookup"><span data-stu-id="480b0-128">**Function**</span></span>  
 <span data-ttu-id="480b0-129">Affiche le numéro de la ligne où le point d'arrêt est défini.</span><span class="sxs-lookup"><span data-stu-id="480b0-129">Displays the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="480b0-130">**File**</span><span class="sxs-lookup"><span data-stu-id="480b0-130">**File**</span></span>  
 <span data-ttu-id="480b0-131">Affiche le nom du fichier source qui contient le point d'arrêt, ainsi que le numéro de la ligne où le point d'arrêt est défini.</span><span class="sxs-lookup"><span data-stu-id="480b0-131">Displays the name of the source file that contains the breakpoint, and the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="480b0-132">**Adresse**</span><span class="sxs-lookup"><span data-stu-id="480b0-132">**Address**</span></span>  
 <span data-ttu-id="480b0-133">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] ne prend pas en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="480b0-133">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="480b0-134">**Processus**</span><span class="sxs-lookup"><span data-stu-id="480b0-134">**Process**</span></span>  
 <span data-ttu-id="480b0-135">Affiche **[SQL]** pour indiquer qu’il s’agit d’un processus du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="480b0-135">Displays **[SQL]** to indicate that this is a [!INCLUDE[ssDE](../../includes/ssde-md.md)] process.</span></span> <span data-ttu-id="480b0-136">Ce libellé est suivi du nom de l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] dans laquelle le code s'exécute.</span><span class="sxs-lookup"><span data-stu-id="480b0-136">This is followed by the name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the code executes.</span></span>  
  
## <a name="breakpoints-window-toolbar"></a><span data-ttu-id="480b0-137">Barre d'outils de la fenêtre Points d'arrêt</span><span class="sxs-lookup"><span data-stu-id="480b0-137">Breakpoints Window Toolbar</span></span>  
 <span data-ttu-id="480b0-138">Lorsque la fenêtre active de l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] contient des points d’arrêt actifs, la fenêtre **Points d’arrêt** affiche une barre d’outils qui permet de gérer les points d’arrêt.</span><span class="sxs-lookup"><span data-stu-id="480b0-138">When the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window has active breakpoints, the **Breakpoints** window displays a toolbar that can be used to manage the breakpoints.</span></span>  
  
 <span data-ttu-id="480b0-139">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="480b0-139">**Delete**</span></span>  
 <span data-ttu-id="480b0-140">Supprime le point d'arrêt sélectionné.</span><span class="sxs-lookup"><span data-stu-id="480b0-140">Deletes the selected breakpoint.</span></span>  
  
 <span data-ttu-id="480b0-141">**Supprimer tous les points d'arrêt**</span><span class="sxs-lookup"><span data-stu-id="480b0-141">**Delete All Breakpoints**</span></span>  
 <span data-ttu-id="480b0-142">Supprime tous les points d’arrêt affichés dans la fenêtre **Points d’arrêt** .</span><span class="sxs-lookup"><span data-stu-id="480b0-142">Deletes all breakpoints that are displayed in the **Breakpoints** window.</span></span>  
  
 <span data-ttu-id="480b0-143">**Désactiver tous les points d'arrêt**</span><span class="sxs-lookup"><span data-stu-id="480b0-143">**Disable All Breakpoints**</span></span>  
 <span data-ttu-id="480b0-144">Désactive tous les points d'arrêt de sorte qu'ils n'arrêtent plus l'exécution du code ; toutefois, les points d'arrêt subsistent.</span><span class="sxs-lookup"><span data-stu-id="480b0-144">Disables all breakpoints so that they no longer stop code execution; however, the breakpoints remain.</span></span> <span data-ttu-id="480b0-145">Lorsque tous les points d’arrêt sont désactivés, ce bouton devient **Activer tous les points d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="480b0-145">When all the breakpoints are disabled, this button becomes **Enable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="480b0-146">**Activer tous les points d’arrêt**</span><span class="sxs-lookup"><span data-stu-id="480b0-146">**Enable All Breakpoints**</span></span>  
 <span data-ttu-id="480b0-147">Active tous les points d'arrêt de sorte qu'ils arrêtent l'exécution du code.</span><span class="sxs-lookup"><span data-stu-id="480b0-147">Enables all breakpoints so that they stop code execution.</span></span> <span data-ttu-id="480b0-148">Lorsque tous les points d’arrêt sont activés, ce bouton devient **Désactiver tous les points d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="480b0-148">When all breakpoints are enabled, this button becomes **Disable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="480b0-149">**Atteindre le code source**</span><span class="sxs-lookup"><span data-stu-id="480b0-149">**Go To Source Code**</span></span>  
 <span data-ttu-id="480b0-150">Place le curseur sur la ligne de l'éditeur de requête qui contient le point d'arrêt sélectionné.</span><span class="sxs-lookup"><span data-stu-id="480b0-150">Positions the cursor on the line in the Query Editor that contains the selected breakpoint.</span></span>  
  
 <span data-ttu-id="480b0-151">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="480b0-151">**Columns**</span></span>  
 <span data-ttu-id="480b0-152">Répertorie toutes les colonnes qui peuvent être affichées dans la fenêtre **Points d’arrêt** .</span><span class="sxs-lookup"><span data-stu-id="480b0-152">Lists all the columns that can be displayed in the **Breakpoints** window.</span></span> <span data-ttu-id="480b0-153">Les colonnes qui sont affichées sont indiquées par une case à cocher.</span><span class="sxs-lookup"><span data-stu-id="480b0-153">A check box indicates the columns that are displayed.</span></span> <span data-ttu-id="480b0-154">Pour ajouter ou supprimer une colonne dans la fenêtre **Points d’arrêt** , sélectionnez la colonne dans la liste.</span><span class="sxs-lookup"><span data-stu-id="480b0-154">To add or remove a column in the **Breakpoints** window, select the column on the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480b0-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="480b0-155">See Also</span></span>  
 [<span data-ttu-id="480b0-156">Débogueur Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="480b0-156">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
