---
title: Fenêtre Liste d'erreurs
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- error list window
- SQL Server Management Studio [SQL Server], error list window
ms.assetid: fae6327d-e268-44ae-a474-4a8f8f843129
author: rothja
ms.author: jroth
ms.openlocfilehash: 00455c339344b7b38a48500c49d139aa52df6116
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613960"
---
# <a name="error-list-window-management-studio"></a><span data-ttu-id="73164-102">Fenêtre Liste d'erreurs (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="73164-102">Error List Window (Management Studio)</span></span>
  <span data-ttu-id="73164-103">La [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Liste d’erreurs**de** répertorie les erreurs syntaxiques et sémantiques générées par le code IntelliSense dans l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73164-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Error List** displays the syntax and semantic errors that are generated from the IntelliSense code in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
## <a name="features-of-the-error-list"></a><span data-ttu-id="73164-104">Fonctionnalités de la Liste d'erreurs</span><span class="sxs-lookup"><span data-stu-id="73164-104">Features of the Error List</span></span>  
 <span data-ttu-id="73164-105">La **Liste d'erreurs** fournit les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="73164-105">The **Error List** provides the following functionality:</span></span>  
  
-   <span data-ttu-id="73164-106">Lorsque vous modifiez des scripts, la **Liste d’erreurs** répertorie les erreurs et les avertissements produits par IntelliSense dans l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73164-106">As you edit scripts, the **Error List** displays the errors and warnings produced by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="73164-107">Vous pouvez double-cliquer sur une entrée de message d'erreur pour examiner l'onglet du fichier de script qui a généré l'erreur et vous rendre à l'endroit où l'erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="73164-107">You can double-click any error message entry to focus on the tab for the script file that generated the error, and move to the error location.</span></span>  
  
-   <span data-ttu-id="73164-108">Vous pouvez filtrer les entrées à afficher, ainsi que les colonnes d'informations à afficher pour chaque entrée.</span><span class="sxs-lookup"><span data-stu-id="73164-108">You can filter which entries you want to display, and which columns of information you want appear for each entry.</span></span>  
  
-   <span data-ttu-id="73164-109">Lorsque vous corrigez une erreur, l'entrée correspondante est supprimée de la **Liste d'erreurs**.</span><span class="sxs-lookup"><span data-stu-id="73164-109">After you fix an error, the error entry is removed from the **Error List**.</span></span>  
  
-   <span data-ttu-id="73164-110">Lorsque vous fermez l'onglet pour un fichier de script [!INCLUDE[tsql](../../includes/tsql-md.md)] , les erreurs relatives à ce fichier sont supprimées de la **Liste d'erreurs**.</span><span class="sxs-lookup"><span data-stu-id="73164-110">When you close the tab for a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file, the errors for that file are removed from the **Error List**.</span></span>  
  
## <a name="working-with-the-error-list"></a><span data-ttu-id="73164-111">Utilisation de la Liste d'erreurs</span><span class="sxs-lookup"><span data-stu-id="73164-111">Working with the Error List</span></span>  
 <span data-ttu-id="73164-112">Pour afficher la **Liste d'erreurs**, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="73164-112">To display the **Error List**, do one of the following:</span></span>  
  
-   <span data-ttu-id="73164-113">Dans le menu **Affichage** , cliquez sur **Liste d'erreurs**.</span><span class="sxs-lookup"><span data-stu-id="73164-113">On the **View** menu, click **Error List**.</span></span>  
  
-   <span data-ttu-id="73164-114">Utilisez le raccourci clavier Ctrl+\\, Ctrl+E.</span><span class="sxs-lookup"><span data-stu-id="73164-114">Enter the keyboard shortcut CTRL+\\, CTRL+E.</span></span>  
  
 <span data-ttu-id="73164-115">Après avoir ouvert la **Liste d'erreurs**, vous pouvez personnaliser l'affichage en effectuant les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="73164-115">After you open the **Error List**, you can customize your view by performing the following actions:</span></span>  
  
-   <span data-ttu-id="73164-116">Pour trier la liste, cliquez sur n'importe quel en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="73164-116">To sort the list, click any column header.</span></span> <span data-ttu-id="73164-117">Pour trier à nouveau sur une colonne supplémentaire, appuyez sur la touche MAJ et maintenez-la enfoncée tout en cliquant sur un autre en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="73164-117">To sort again by an additional column, press and hold the SHIFT key, and then click another column header.</span></span>  
  
-   <span data-ttu-id="73164-118">Pour sélectionner les colonnes qui sont affichées et celles qui sont masquées, sélectionnez **Afficher les colonnes** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="73164-118">To select which columns are displayed and which are hidden, select **Show Columns** from the shortcut menu.</span></span>  
  
-   <span data-ttu-id="73164-119">Pour modifier l'ordre dans lequel les colonnes sont affichées, faites glisser les en-têtes de votre choix vers la droite ou la gauche.</span><span class="sxs-lookup"><span data-stu-id="73164-119">To change the order in which columns are displayed, drag any column header to the left or right.</span></span>  
  
 <span data-ttu-id="73164-120">La **Liste d'erreurs** ne contient pas de liens vers des informations supplémentaires sur des erreurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="73164-120">The **Error List** does not link to additional information about specific errors.</span></span>  
  
## <a name="transact-sql-errors-in-management-studio"></a><span data-ttu-id="73164-121">Erreurs Transact-SQL dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="73164-121">Transact-SQL Errors in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="73164-122">affiche les erreurs pour les scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] aux emplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="73164-122">displays errors for [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in the following locations:</span></span>  
  
-   <span data-ttu-id="73164-123">La **Liste d’erreurs** contient toutes les erreurs syntaxiques et sémantiques détectées par IntelliSense dans l’éditeur du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73164-123">The **Error List** contains all syntax and semantic errors found by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor.</span></span> <span data-ttu-id="73164-124">Cette liste d'erreurs est mise à jour dynamiquement au fur et à mesure que vous modifiez des scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73164-124">This list of errors is dynamically updated as you edit [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="73164-125">La liste inclut toutes les erreurs que l’éditeur a identifiées dans chaque script [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73164-125">The list includes all errors that the editor has found in each [!INCLUDE[tsql](../../includes/tsql-md.md)] script.</span></span> <span data-ttu-id="73164-126">L'éditeur n'arrête pas l'analyse d'un fichier lorsque des erreurs ont été identifiées dans un script.</span><span class="sxs-lookup"><span data-stu-id="73164-126">The editor does not stop parsing a file after encountering errors in a script.</span></span> <span data-ttu-id="73164-127">Dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], IntelliSense dans l’éditeur du [!INCLUDE[ssDE](../../includes/ssde-md.md)] ne prend pas en charge tous les éléments syntaxiques [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73164-127">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="73164-128">La **Liste d'erreurs** contient uniquement les erreurs de la syntaxe [!INCLUDE[tsql](../../includes/tsql-md.md)] prise en charge par IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="73164-128">The **Error List** contains only errors from the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax that is supported by IntelliSense.</span></span>  
  
-   <span data-ttu-id="73164-129">L’onglet **Messages** en bas de la fenêtre de l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] affiche les erreurs et les messages retournés par le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] lorsqu’un script [!INCLUDE[tsql](../../includes/tsql-md.md)] est exécuté.</span><span class="sxs-lookup"><span data-stu-id="73164-129">The **Messages** tab at the bottom of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window displays all errors and messages that are returned by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] when a [!INCLUDE[tsql](../../includes/tsql-md.md)] script is executed.</span></span> <span data-ttu-id="73164-130">Cette liste ne change pas jusqu'à ce que vous exécutiez à nouveau le script.</span><span class="sxs-lookup"><span data-stu-id="73164-130">This list does not change until you execute the script again.</span></span> <span data-ttu-id="73164-131">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] arrête d’analyser un lot s’il détecte une ou deux erreurs de compilation ; par conséquent, l’onglet **Messages** peut ne pas répertorier toutes les erreurs d’un script.</span><span class="sxs-lookup"><span data-stu-id="73164-131">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stops parsing a batch after it finds one or two compile errors; therefore, the **Messages** tab might not list all errors in a script.</span></span>  
  
 <span data-ttu-id="73164-132">Parfois, des erreurs sont répertoriées dans les deux emplacements.</span><span class="sxs-lookup"><span data-stu-id="73164-132">Sometimes errors are listed in both locations.</span></span> <span data-ttu-id="73164-133">Par exemple, un fichier de script peut contenir une erreur de syntaxe qui est répertoriée dans la **Liste d'erreurs**.</span><span class="sxs-lookup"><span data-stu-id="73164-133">For example, a script file might have a syntax error that is listed in the **Error List**.</span></span> <span data-ttu-id="73164-134">Si vous exécutez le script avant de corriger l’erreur, l’analyseur du [!INCLUDE[ssDE](../../includes/ssde-md.md)] peut détecter la même condition et retourner une autre copie du message d’erreur sous l’onglet **Messages** .</span><span class="sxs-lookup"><span data-stu-id="73164-134">If you execute the script before you correct the error, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] parser can detect the same condition and return another copy of the error message in the **Messages** tab.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73164-135">La **Liste d’erreurs** affiche uniquement les erreurs de l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] ; elle n’affiche pas les erreurs des éditeurs MDX, DMX ni XML/A.</span><span class="sxs-lookup"><span data-stu-id="73164-135">The **Error List** only displays errors from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor; it does not display errors from the MDX, DMX, or XML/A Editors.</span></span> <span data-ttu-id="73164-136">Toutes les erreurs MDX, DMX et XML/A sont affichées sous l’onglet **Messages** de ces éditeurs.</span><span class="sxs-lookup"><span data-stu-id="73164-136">All MDX, DMX, and XML/A errors are displayed in the **Messages** tab in those editors.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="73164-137">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="73164-137">UI element list</span></span>  
 <span data-ttu-id="73164-138">Lorsque la **Liste d'erreurs** est ouverte, les informations sont affichées dans les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="73164-138">When the **Error List** is open, the information is displayed in the following columns:</span></span>  
  
 <span data-ttu-id="73164-139">**Ordre par défaut**</span><span class="sxs-lookup"><span data-stu-id="73164-139">**Default Order**</span></span>  
 <span data-ttu-id="73164-140">Affiche un entier qui indique l'ordre dans lequel une entrée a été générée.</span><span class="sxs-lookup"><span data-stu-id="73164-140">Displays an integer that indicates the order in which an entry was generated.</span></span>  
  
 <span data-ttu-id="73164-141">**Description**</span><span class="sxs-lookup"><span data-stu-id="73164-141">**Description**</span></span>  
 <span data-ttu-id="73164-142">Affiche le texte de l'entrée de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="73164-142">Displays the text of the error entry.</span></span> <span data-ttu-id="73164-143">Les descriptions longues s'étendent sur plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="73164-143">Lengthy descriptions wrap onto additional lines.</span></span>  
  
 <span data-ttu-id="73164-144">**File**</span><span class="sxs-lookup"><span data-stu-id="73164-144">**File**</span></span>  
 <span data-ttu-id="73164-145">Affiche le nom du fichier de script qui a généré l'erreur.</span><span class="sxs-lookup"><span data-stu-id="73164-145">Displays the name of the script file that generated the error.</span></span>  
  
 <span data-ttu-id="73164-146">**Ligne**</span><span class="sxs-lookup"><span data-stu-id="73164-146">**Line**</span></span>  
 <span data-ttu-id="73164-147">Affiche un entier qui indique la ligne du code contenant l'erreur.</span><span class="sxs-lookup"><span data-stu-id="73164-147">Displays an integer that indicates which line of the code includes the error.</span></span>  
  
 <span data-ttu-id="73164-148">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="73164-148">**Column**</span></span>  
 <span data-ttu-id="73164-149">Affiche un entier qui indique la position de l'erreur dans la ligne de code.</span><span class="sxs-lookup"><span data-stu-id="73164-149">Displays an integer that indicates the position of the error in the line of code.</span></span>  
  
 <span data-ttu-id="73164-150">**Projet**</span><span class="sxs-lookup"><span data-stu-id="73164-150">**Project**</span></span>  
 <span data-ttu-id="73164-151">Affiche le nom du projet qui comprend le fichier de script.</span><span class="sxs-lookup"><span data-stu-id="73164-151">Displays the name of the project that includes the script file.</span></span>  
