---
title: Gérer la mise en forme du code
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- indenting code [SQL Server]
- displaying URLs
- code formatting [SQL Server Management Studio]
- collapsing text
- formats [SQL Server], code formatting in SQL Server Management Studio
- hiding text
- formats [SQL Server]
- text [SQL Server], code formats
- automatic indentation
- converting text to lower case
- Query Editor [SQL Server Management Studio], managing code formats
- URL displayed in code [SQL Server Management Studio]
- converting text to upper case
- text [SQL Server]
- unindenting code
ms.assetid: ddbac4d2-6bdc-4467-a352-e869ec880eed
author: rothja
ms.author: jroth
ms.openlocfilehash: 873848c8aee575b47f7a3d8c31d8392cba5ed12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614478"
---
# <a name="manage-code-formatting"></a><span data-ttu-id="c1026-102">Gérer la mise en forme du code</span><span class="sxs-lookup"><span data-stu-id="c1026-102">Manage Code Formatting</span></span>
  <span data-ttu-id="c1026-103">Dans l'éditeur, vous pouvez mettre en forme votre code avec des mises en retrait, du texte caché, des URL, etc.</span><span class="sxs-lookup"><span data-stu-id="c1026-103">With the Editor you can format your code with indenting, hidden text, URLs, and so forth.</span></span> <span data-ttu-id="c1026-104">Vous pouvez également mettre en forme automatiquement votre code à l'aide de la fonction de mise en retrait intelligente.</span><span class="sxs-lookup"><span data-stu-id="c1026-104">You can also auto-format your code as you type by using Smart Indenting.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="c1026-105">Mise en retrait</span><span class="sxs-lookup"><span data-stu-id="c1026-105">Indenting</span></span>  
 <span data-ttu-id="c1026-106">Vous avez le choix entre trois styles de mise en retrait du texte.</span><span class="sxs-lookup"><span data-stu-id="c1026-106">You can choose three different styles of text indenting.</span></span> <span data-ttu-id="c1026-107">Vous pouvez également spécifier le nombre d'espaces correspondant à une mise en retrait ou une tabulation, et déterminer si l'Éditeur de code applique la mise en retrait au moyen de tabulations ou d'espaces.</span><span class="sxs-lookup"><span data-stu-id="c1026-107">You can also specify how many spaces compose a single indentation or tab, and whether the Editor uses tabs or space characters when indenting.</span></span>  
  
#### <a name="to-choose-an-indenting-style"></a><span data-ttu-id="c1026-108">Pour choisir un style de mise en retrait</span><span class="sxs-lookup"><span data-stu-id="c1026-108">To choose an indenting style</span></span>  
  
1.  <span data-ttu-id="c1026-109">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="c1026-109">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="c1026-110">Cliquez sur **Éditeur de texte**.</span><span class="sxs-lookup"><span data-stu-id="c1026-110">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="c1026-111">Cliquez sur le dossier, puis sélectionnez **Tous les langages** pour définir la mise en retrait pour tous les langages.</span><span class="sxs-lookup"><span data-stu-id="c1026-111">Click the folder, and select **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="c1026-112">Cliquez sur **Tabulations**.</span><span class="sxs-lookup"><span data-stu-id="c1026-112">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="c1026-113">Cliquez sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1026-113">Click one of the following options:</span></span>  
  
    -   <span data-ttu-id="c1026-114">**Aucun**.</span><span class="sxs-lookup"><span data-stu-id="c1026-114">**None**.</span></span> <span data-ttu-id="c1026-115">Le curseur se positionne au début de la ligne suivante.</span><span class="sxs-lookup"><span data-stu-id="c1026-115">The cursor goes to the beginning of the next line.</span></span>  
  
    -   <span data-ttu-id="c1026-116">**Bloquer**.</span><span class="sxs-lookup"><span data-stu-id="c1026-116">**Block**.</span></span> <span data-ttu-id="c1026-117">Le curseur aligne la ligne suivante sur la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="c1026-117">The cursor aligns the next line with the previous line.</span></span>  
  
    -   <span data-ttu-id="c1026-118">**Intelligente** (par défaut).</span><span class="sxs-lookup"><span data-stu-id="c1026-118">**Smart** (Default).</span></span> <span data-ttu-id="c1026-119">Le service du langage détermine le style de mise en retrait approprié à utiliser.</span><span class="sxs-lookup"><span data-stu-id="c1026-119">The language service determines the appropriate indenting style to use.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1026-120">Certains langages n'offrent pas toutes ces options de mise en retrait.</span><span class="sxs-lookup"><span data-stu-id="c1026-120">Some languages do not offer all three indenting options.</span></span>  
  
#### <a name="to-change-indent-tab-settings"></a><span data-ttu-id="c1026-121">Pour modifier les paramètres des tabulations de mise en retrait</span><span class="sxs-lookup"><span data-stu-id="c1026-121">To change indent tab settings</span></span>  
  
1.  <span data-ttu-id="c1026-122">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="c1026-122">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="c1026-123">Cliquez sur **Éditeur de texte**.</span><span class="sxs-lookup"><span data-stu-id="c1026-123">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="c1026-124">Sélectionnez le dossier pour **Tous les langages** pour définir la mise en retrait pour tous les langages.</span><span class="sxs-lookup"><span data-stu-id="c1026-124">Select the folder for **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="c1026-125">Cliquez sur **Tabulations**.</span><span class="sxs-lookup"><span data-stu-id="c1026-125">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="c1026-126">Pour spécifier des caractères de tabulation pour les opérations de tabulation et de mise en retrait, cliquez sur **Conserver les tabulations**.</span><span class="sxs-lookup"><span data-stu-id="c1026-126">To specify tab characters for tab and indent operations, click **Keep tabs**.</span></span> <span data-ttu-id="c1026-127">Pour spécifier des espaces, sélectionnez **Insérer des espaces**.</span><span class="sxs-lookup"><span data-stu-id="c1026-127">To specify space characters, select **Insert spaces**.</span></span>  
  
     <span data-ttu-id="c1026-128">Si vous sélectionnez **Insérer des espaces**, vous pouvez entrer le nombre d’espaces représenté par chaque tabulation ou mise en retrait, respectivement sous **Taille des tabulations** ou **Taille du retrait**.</span><span class="sxs-lookup"><span data-stu-id="c1026-128">If you select **Insert Spaces**, enter the number of space characters each tab or indent represents under **Tab Size** or **Indent Size**, respectively.</span></span>  
  
#### <a name="to-indent-code"></a><span data-ttu-id="c1026-129">Pour mettre du code en retrait</span><span class="sxs-lookup"><span data-stu-id="c1026-129">To indent code</span></span>  
  
1.  <span data-ttu-id="c1026-130">Sélectionnez le texte que vous souhaitez mettre en retrait.</span><span class="sxs-lookup"><span data-stu-id="c1026-130">Select the text you want to indent.</span></span>  
  
2.  <span data-ttu-id="c1026-131">Appuyez sur TAB ou cliquez sur le bouton **Retrait** dans la barre d’outils Standard.</span><span class="sxs-lookup"><span data-stu-id="c1026-131">Press TAB, or click the **Indent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-unindent-code"></a><span data-ttu-id="c1026-132">Pour annuler la mise en retrait du code</span><span class="sxs-lookup"><span data-stu-id="c1026-132">To unindent code</span></span>  
  
1.  <span data-ttu-id="c1026-133">Sélectionnez le texte dont vous souhaitez annuler la mise en retrait.</span><span class="sxs-lookup"><span data-stu-id="c1026-133">Select the text you want to unindent.</span></span>  
  
2.  <span data-ttu-id="c1026-134">Appuyez sur Maj+Tab ou cliquez sur le bouton **Annuler la mise en retrait** dans la barre d’outils Standard.</span><span class="sxs-lookup"><span data-stu-id="c1026-134">Press SHIFT+TAB, or click the **Unindent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-automatically-indent-all-of-your-code"></a><span data-ttu-id="c1026-135">Pour mettre automatiquement en retrait la totalité du code</span><span class="sxs-lookup"><span data-stu-id="c1026-135">To automatically indent all of your code</span></span>  
  
1.  <span data-ttu-id="c1026-136">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="c1026-136">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="c1026-137">Cliquez sur **Éditeur de texte**.</span><span class="sxs-lookup"><span data-stu-id="c1026-137">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="c1026-138">Cliquez sur **Tous les langages**.</span><span class="sxs-lookup"><span data-stu-id="c1026-138">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="c1026-139">Cliquez sur **Tabulations**.</span><span class="sxs-lookup"><span data-stu-id="c1026-139">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="c1026-140">Cliquez sur **Intelligente**.</span><span class="sxs-lookup"><span data-stu-id="c1026-140">Click **Smart**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1026-141">L’option **Intelligente** n’est pas disponible pour certains langages.</span><span class="sxs-lookup"><span data-stu-id="c1026-141">The **Smart** option is not available for some languages.</span></span>  
  
#### <a name="to-convert-white-space-to-tabs"></a><span data-ttu-id="c1026-142">Pour convertir un espace en tabulations</span><span class="sxs-lookup"><span data-stu-id="c1026-142">To convert white space to tabs</span></span>  
  
1.  <span data-ttu-id="c1026-143">Sélectionnez le texte qui contient l'espace que vous souhaitez convertir en tabulations.</span><span class="sxs-lookup"><span data-stu-id="c1026-143">Select the text whose white space you want to convert to tabs.</span></span>  
  
2.  <span data-ttu-id="c1026-144">Dans le menu **Edition** , pointez sur **Avancée**, puis cliquez sur **Remplacer les espaces par des tabulations**.</span><span class="sxs-lookup"><span data-stu-id="c1026-144">On the **Edit** menu, point to **Advanced**, and click **Tabify Selection**.</span></span>  
  
#### <a name="to-convert-tabs-to-spaces"></a><span data-ttu-id="c1026-145">Pour convertir des tabulations en espaces</span><span class="sxs-lookup"><span data-stu-id="c1026-145">To convert tabs to spaces</span></span>  
  
1.  <span data-ttu-id="c1026-146">Sélectionnez le texte qui contient les tabulations que vous souhaitez convertir en espaces.</span><span class="sxs-lookup"><span data-stu-id="c1026-146">Select the text whose tabs you want to convert to spaces.</span></span>  
  
2.  <span data-ttu-id="c1026-147">Dans le menu **Edition** , pointez sur **Avancée**, puis cliquez sur **Remplacer les tabulations par des espaces**.</span><span class="sxs-lookup"><span data-stu-id="c1026-147">On the **Edit** menu, point to **Advanced**, and click **Untabify Selection**.</span></span>  
  
 <span data-ttu-id="c1026-148">Le comportement de ces commandes dépend des paramètres de tabulation définis dans la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="c1026-148">The behavior of these commands depends on the tab settings in the **Options** dialog box.</span></span> <span data-ttu-id="c1026-149">Par exemple, si le paramètre de tabulation a pour valeur quatre, **Remplacer les espaces par des tabulations** crée une tabulation pour tout groupe de quatre espaces contigus alors que **Remplacer les tabulations par des espaces** crée quatre espaces pour chaque tabulation.</span><span class="sxs-lookup"><span data-stu-id="c1026-149">For example, if the tab setting is 4, **Tabify Selection** creates a tab for every 4 contiguous spaces, and **Untabify Selection** creates 4 spaces for every tab.</span></span>  
  
## <a name="converting-text-to-upper-and-lower-case"></a><span data-ttu-id="c1026-150">Conversion de texte en majuscules et en minuscules</span><span class="sxs-lookup"><span data-stu-id="c1026-150">Converting Text to Upper and Lower Case</span></span>  
 <span data-ttu-id="c1026-151">Des commandes vous permettent de convertir du texte en majuscules ou en minuscules.</span><span class="sxs-lookup"><span data-stu-id="c1026-151">You can use commands to convert text to all uppercase or lower case.</span></span>  
  
#### <a name="to-switch-text-to-upper-or-lower-case"></a><span data-ttu-id="c1026-152">Pour convertir du texte en majuscules ou minuscules</span><span class="sxs-lookup"><span data-stu-id="c1026-152">To switch text to upper or lower case</span></span>  
  
1.  <span data-ttu-id="c1026-153">Sélectionnez le texte à convertir.</span><span class="sxs-lookup"><span data-stu-id="c1026-153">Select the text you want to convert.</span></span>  
  
2.  <span data-ttu-id="c1026-154">Pour convertir du texte en majuscules, appuyez sur Ctrl+Maj+U ou cliquez sur **Mettre en majuscules** dans le sous-menu **Avancée** du menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="c1026-154">To convert text to uppercase, press CTRL+SHIFT+U, or click **Make Uppercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
3.  <span data-ttu-id="c1026-155">Pour convertir du texte en minuscules, appuyez sur Ctrl+Maj+L ou cliquez sur **Mettre en minuscules** dans le sous-menu **Avancée** du menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="c1026-155">To convert text to lowercase, press CTRL+SHIFT+L, or click **Make Lowercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1026-156">Pour obtenir la liste complète des touches de raccourci clavier, consultez [Raccourcis clavier dans SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="c1026-156">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="displaying-and-linking-to-urls"></a><span data-ttu-id="c1026-157">Affichage et liaison à des URL</span><span class="sxs-lookup"><span data-stu-id="c1026-157">Displaying and Linking to URLs</span></span>  
 <span data-ttu-id="c1026-158">Vous pouvez créer et gérer des URL interactives dans votre code.</span><span class="sxs-lookup"><span data-stu-id="c1026-158">You can create and display clickable URLs in your code.</span></span> <span data-ttu-id="c1026-159">Par défaut, les URL :</span><span class="sxs-lookup"><span data-stu-id="c1026-159">By default, the URLs:</span></span>  
  
-   <span data-ttu-id="c1026-160">sont soulignées ;</span><span class="sxs-lookup"><span data-stu-id="c1026-160">Are underlined.</span></span>  
  
-   <span data-ttu-id="c1026-161">entraînent la transformation du pointeur de la souris en une main lorsque vous passez par-dessus ;</span><span class="sxs-lookup"><span data-stu-id="c1026-161">Change the mouse pointer to a hand when you move over them.</span></span>  
  
-   <span data-ttu-id="c1026-162">ouvrent le site correspondant lorsque vous cliquez une fois dessus, pour autant que l'URL soit valide.</span><span class="sxs-lookup"><span data-stu-id="c1026-162">Open the URL when clicked, if the URL is valid.</span></span>  
  
#### <a name="to-display-a-clickable-url"></a><span data-ttu-id="c1026-163">Pour afficher une URL interactive</span><span class="sxs-lookup"><span data-stu-id="c1026-163">To display a clickable URL</span></span>  
  
1.  <span data-ttu-id="c1026-164">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="c1026-164">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="c1026-165">Cliquez sur **Éditeur de texte**.</span><span class="sxs-lookup"><span data-stu-id="c1026-165">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="c1026-166">Pour modifier l’option pour un seul langage, cliquez sur le dossier de celui-ci, puis sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="c1026-166">To change the option for only one language, click that language folder and then click **General**.</span></span> <span data-ttu-id="c1026-167">Pour modifier l’option pour tous les langages, cliquez sur **Tous les langages** , puis sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="c1026-167">To change the option for all languages, click **All Languages** and then click **General**.</span></span>  
  
4.  <span data-ttu-id="c1026-168">Sélectionnez **Activer la navigation dans les URL par simple clic**.</span><span class="sxs-lookup"><span data-stu-id="c1026-168">Select **Enable single-click URL navigation**.</span></span>  
  
  
