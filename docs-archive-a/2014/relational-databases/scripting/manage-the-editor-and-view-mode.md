---
title: Gérer l'Éditeur et le mode d'affichage
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], managing window behavior
- workbench view modes [SQL Server Management Studio]
- full screen mode [SQL Server Management Studio]
- fonts [SQL Server Management Studio]
- word wraps [SQL Server Management Studio]
- virtual space mode [SQL Server Management Studio]
- splitting document views
- displaying line numbers
- view modes [SQL Server Management Studio]
ms.assetid: 25c58a14-9f94-4296-9770-7d84c6bc3969
author: rothja
ms.author: jroth
ms.openlocfilehash: 36788b1fe831a6c15c4aa0668d1759c088fcaa73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613420"
---
# <a name="manage-the-editor-and-view-mode"></a><span data-ttu-id="0a5a5-102">Gérer l'Éditeur et le mode d'affichage</span><span class="sxs-lookup"><span data-stu-id="0a5a5-102">Manage the Editor and View Mode</span></span>
  <span data-ttu-id="0a5a5-103">L'Éditeur offre plusieurs moyens de contrôler l'affichage du code.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-103">The Editor gives you a number of ways to control the view of your code.</span></span>  
  
## <a name="changing-the-view-mode"></a><span data-ttu-id="0a5a5-104">Changement du mode d'affichage</span><span class="sxs-lookup"><span data-stu-id="0a5a5-104">Changing the View Mode</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="0a5a5-105">propose un mode d’affichage appelé **Documents avec onglet**, qui permet d’ouvrir plusieurs éditeurs et documents en même temps et d’y accéder au moyen des onglets situés dans la partie supérieure de l’Éditeur.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-105">features a view mode called **Tabbed Documents**, which allows you to open multiple editors and documents simultaneously and access them through tabs at the top of the Editor.</span></span> <span data-ttu-id="0a5a5-106">Vous pouvez également ouvrir l'environnement [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] dans le mode MD, dans lequel il est possible d'attacher les fenêtres sans les onglets, de les organiser, de les réduire, etc.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-106">You can alternatively open the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] environment in Multiple Document Interface (MDI) mode, which joins windows without the tabs, and allows each window to be tiled, minimized, and so on.</span></span>  
  
#### <a name="to-switch-between-view-modes"></a><span data-ttu-id="0a5a5-107">Pour passer d'un mode d'affichage à un autre</span><span class="sxs-lookup"><span data-stu-id="0a5a5-107">To switch between view modes</span></span>  
  
1.  <span data-ttu-id="0a5a5-108">Cliquez sur **Options** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="0a5a5-108">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="0a5a5-109">Cliquez sur **Environnement**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-109">Click **Environment**.</span></span> <span data-ttu-id="0a5a5-110">Cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-110">Click **General**.</span></span>  
  
3.  <span data-ttu-id="0a5a5-111">Cliquez sur **Documents avec onglet** ou sur **Environnement MDI**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-111">Click **Tabbed documents** or **MDI environment**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a5a5-112">Les modifications sont prises en compte uniquement une fois [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] redémarré.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-112">The changes will not take effect until [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is restarted.</span></span>  
  
## <a name="splitting-the-view"></a><span data-ttu-id="0a5a5-113">Fractionnement de l'affichage</span><span class="sxs-lookup"><span data-stu-id="0a5a5-113">Splitting the View</span></span>  
 <span data-ttu-id="0a5a5-114">Une fenêtre d'Éditeur peut être fractionnée en deux volets distincts afin de faciliter les opérations de modification.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-114">An Editor window can be split into two separate parts for easier editing.</span></span>  
  
#### <a name="to-split-a-window"></a><span data-ttu-id="0a5a5-115">Pour fractionner une fenêtre</span><span class="sxs-lookup"><span data-stu-id="0a5a5-115">To split a window</span></span>  
  
1.  <span data-ttu-id="0a5a5-116">Cliquez sur la barre de fractionnement (située au-dessus de la barre de défilement).</span><span class="sxs-lookup"><span data-stu-id="0a5a5-116">Click the splitter bar (located above the scroll bar).</span></span>  
  
2.  <span data-ttu-id="0a5a5-117">Faites glisser la barre de fractionnement vers le bas.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-117">Drag the splitter bar downward.</span></span>  
  
3.  <span data-ttu-id="0a5a5-118">Pour revenir à un affichage ne contenant qu'un seul volet, double-cliquez sur la barre qui scinde la fenêtre en deux volets.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-118">To go back to a single pane, double-click the splitter bar dividing the two panes.</span></span>  
  
 <span data-ttu-id="0a5a5-119">Le nouveau volet contient le même document et toute modification apportée dans un volet est reflétée dans l'autre volet à condition que cet autre volet affiche la même partie du document.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-119">The new pane contains the same document, and any changes made to one pane are reflected in the other pane as long as that pane displays the same place in the document.</span></span>  
  
## <a name="word-wrap"></a><span data-ttu-id="0a5a5-120">Retour automatique à la ligne</span><span class="sxs-lookup"><span data-stu-id="0a5a5-120">Word Wrap</span></span>  
 <span data-ttu-id="0a5a5-121">Lorsque vous activez le retour automatique à la ligne, la barre de défilement horizontale est supprimée et les lignes de code qui dépassent la largeur de la fenêtre de l'Éditeur sont renvoyées automatiquement à la ligne affichée suivante, au lieu de se poursuivre latéralement.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-121">When you activate Word Wrap, the horizontal scrollbar is removed and lines of code that exceed the width of the Editor's window size automatically wraps to the next displayed line rather than scrolling off the side of the window.</span></span>  
  
#### <a name="to-activate-word-wrap"></a><span data-ttu-id="0a5a5-122">Pour activer le retour automatique à la ligne</span><span class="sxs-lookup"><span data-stu-id="0a5a5-122">To activate word wrap</span></span>  
  
1.  <span data-ttu-id="0a5a5-123">Cliquez sur **Options** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="0a5a5-123">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="0a5a5-124">Cliquez sur **Éditeur de texte**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-124">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="0a5a5-125">Ouvrez le dossier de langage approprié (ou **Tous les langages** pour que tous les langages soient pris en compte).</span><span class="sxs-lookup"><span data-stu-id="0a5a5-125">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="0a5a5-126">Sélectionnez **Retour automatique à la ligne**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-126">Select **Word wrap**.</span></span>  
  
## <a name="enabling-virtual-space-mode"></a><span data-ttu-id="0a5a5-127">Activation du mode Espace virtuel</span><span class="sxs-lookup"><span data-stu-id="0a5a5-127">Enabling Virtual Space Mode</span></span>  
 <span data-ttu-id="0a5a5-128">Quand le mode **Espace virtuel** est activé, l’Éditeur se comporte comme si l’espace après la fin de chaque ligne se composait d’un nombre infini d’espaces, ce qui permet aux lignes de code de se poursuivre en dehors de la zone latérale visible de l’écran.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-128">In **Virtual Space** mode, the Editor acts as if the space past the end of each line is filled with an infinite number of spaces, allowing code lines to continue off the side of the visible screen area.</span></span>  
  
#### <a name="to-enable-virtual-space-mode"></a><span data-ttu-id="0a5a5-129">Pour activer le mode Espace virtuel</span><span class="sxs-lookup"><span data-stu-id="0a5a5-129">To enable Virtual Space mode</span></span>  
  
1.  <span data-ttu-id="0a5a5-130">Cliquez sur **Options** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="0a5a5-130">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="0a5a5-131">Cliquez sur **Éditeur de texte**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-131">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="0a5a5-132">Ouvrez le dossier de langage approprié (ou **Tous les langages** pour que tous les langages soient pris en compte).</span><span class="sxs-lookup"><span data-stu-id="0a5a5-132">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="0a5a5-133">Sélectionnez **Activer l’espace virtuel**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-133">Select **Enable virtual space**.</span></span>  
  
 <span data-ttu-id="0a5a5-134">Lorsque le mode Espace virtuel n'est pas activé, le curseur passe de la fin d'une ligne au premier caractère de la ligne suivante et inversement.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-134">When Virtual Space mode is not enabled, the cursor wraps from the end of one line to the first character of the next line and vice-versa.</span></span>  
  
## <a name="displaying-line-numbers"></a><span data-ttu-id="0a5a5-135">affichage des numéros de ligne</span><span class="sxs-lookup"><span data-stu-id="0a5a5-135">Displaying Line Numbers</span></span>  
 <span data-ttu-id="0a5a5-136">Vous pouvez activer la numérotation des lignes dans votre code.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-136">You can turn on line numbering in your code.</span></span> <span data-ttu-id="0a5a5-137">Les numéros de ligne sont utiles pour se déplacer dans le code.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-137">Line numbers are useful for navigating code.</span></span> <span data-ttu-id="0a5a5-138">Pour plus d’informations, consultez [Navigation dans le code et le texte](navigate-code-and-text.md).</span><span class="sxs-lookup"><span data-stu-id="0a5a5-138">For more information, see [Navigate Code and Text](navigate-code-and-text.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a5a5-139">L'activation de la numérotation des lignes ne signifie pas que ces numéros soient repris sur le document imprimé.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-139">Turning on line numbering does not mean that the document will print with line numbers.</span></span> <span data-ttu-id="0a5a5-140">Pour imprimer les numéros de ligne, cochez la case **Numéros de ligne** dans la commande **Mise en page** du menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="0a5a5-140">For line numbers to print, you must select the **Line numbers** check box in the **Page Setup** command on the **File** menu.</span></span>  
  
#### <a name="to-display-line-numbers-in-code"></a><span data-ttu-id="0a5a5-141">Pour afficher les numéros de ligne dans le code</span><span class="sxs-lookup"><span data-stu-id="0a5a5-141">To display line numbers in code</span></span>  
  
1.  <span data-ttu-id="0a5a5-142">Cliquez sur **Options** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="0a5a5-142">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="0a5a5-143">Cliquez sur **Éditeur de texte**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-143">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="0a5a5-144">Cliquez sur **Tous les langages**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-144">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="0a5a5-145">Cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-145">Click **General**.</span></span>  
  
5.  <span data-ttu-id="0a5a5-146">Sélectionnez **Numéros de ligne**.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-146">Select **Line numbers**.</span></span>  
  
 <span data-ttu-id="0a5a5-147">Pour choisir de numéroter les lignes uniquement pour certains langages de programmation, sélectionnez **Numéros de ligne** dans le dossier de langage approprié.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-147">To specify line numbering for only some programming languages, select **Line Numbers** in the appropriate folder.</span></span>  
  
## <a name="enabling-full-screen-mode"></a><span data-ttu-id="0a5a5-148">Activation du mode Plein écran</span><span class="sxs-lookup"><span data-stu-id="0a5a5-148">Enabling Full Screen Mode</span></span>  
 <span data-ttu-id="0a5a5-149">Vous pouvez choisir de masquer toutes les fenêtres Outil et d'afficher uniquement les fenêtres de document en activant le mode Plein écran.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-149">You can choose to hide all tool windows and view only document windows by enabling Full Screen mode.</span></span>  
  
#### <a name="to-enable-full-screen-mode"></a><span data-ttu-id="0a5a5-150">Pour activer le mode Plein écran</span><span class="sxs-lookup"><span data-stu-id="0a5a5-150">To enable Full Screen mode</span></span>  
  
1.  <span data-ttu-id="0a5a5-151">Appuyez sur ALT+MAJ+ENTRÉE pour activer le mode Plein écran.</span><span class="sxs-lookup"><span data-stu-id="0a5a5-151">Press ALT+SHIFT+ENTER to toggle Full Screen mode.</span></span>  
  
## <a name="using-auto-hide-all"></a><span data-ttu-id="0a5a5-152">Utilisation de l'option Masquer tout automatiquement</span><span class="sxs-lookup"><span data-stu-id="0a5a5-152">Using Auto Hide All</span></span>  
  
#### <a name="to-hide-all-the-tool-windows-at-once"></a><span data-ttu-id="0a5a5-153">Pour masquer toutes les fenêtres Outil en même temps</span><span class="sxs-lookup"><span data-stu-id="0a5a5-153">To hide all the tool windows at once</span></span>  
  
1.  <span data-ttu-id="0a5a5-154">Dans le menu **Fenêtre** , sélectionnez **Masquer tout automatiquement** .</span><span class="sxs-lookup"><span data-stu-id="0a5a5-154">Select **Auto Hide All** on the **Window** menu.</span></span>  
  
  
