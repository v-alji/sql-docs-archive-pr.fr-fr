---
title: Options (éditeur de texte-toutes les langues-page onglets) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: bd715d6b-f873-41d4-aa10-57b7098b61cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 13f791e34b2099e8c0492c25886ee6b37ef1a1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613126"
---
# <a name="options-text-editor---all-languages--tabs-page"></a><span data-ttu-id="b3b5d-102">Options (Éditeur de texte - Toutes les langues - Page Onglets)</span><span class="sxs-lookup"><span data-stu-id="b3b5d-102">Options (Text Editor - All Languages -Tabs Page)</span></span>
  <span data-ttu-id="b3b5d-103">Cette boîte de dialogue vous permet de définir le comportement de tabulation des cinq éditeurs de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3b5d-103">Use this dialog box to set the tabbing behavior in all five of the editors in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b3b5d-104">Pour afficher ces options, sélectionnez **Options** dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="b3b5d-104">To display these options, click **Options** on the **Tools** menu.</span></span> <span data-ttu-id="b3b5d-105">Sélectionnez le dossier **Éditeur de texte** , développez le dossier **Tous les langages** , puis cliquez sur **Tabulations**.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-105">Select the **Text Editor** folder, expand the **All Languages** folder and then click **Tabs**.</span></span>  
  
## <a name="tabbing-options-by-editor"></a><span data-ttu-id="b3b5d-106">Options de tabulation par éditeur</span><span class="sxs-lookup"><span data-stu-id="b3b5d-106">Tabbing Options by Editor</span></span>  
 <span data-ttu-id="b3b5d-107">Vous devez utilisez les boîtes de dialogue **Tous les langages** pour définir les options des éditeurs DMX, MDX et SQL Server Compact.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-107">You must use the **All Languages** dialogs to set options for the DMX, MDX, and SQL Server Compact editors.</span></span> <span data-ttu-id="b3b5d-108">Les options définies ici s'appliquent aussi aux éditeurs de texte brut, Transact-SQL et XML, mais vous pouvez définir les options de ces éditeurs séparément en développant les sous-dossiers de ces langages et en sélectionnant leur page d'options.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-108">Options set here are also applied to the Plain Text, Transact-SQL, and XML editors, but you can set options separately for those editors by expanding the subfolders for those languages and selecting their option pages.</span></span> <span data-ttu-id="b3b5d-109">Certains langages ne prennent pas en charge toutes les options de tabulation.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-109">Some languages do not support all of the tabbing options.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b3b5d-110">Si vous définissez une option à l’aide de cette boîte de dialogue, mais que vous voulez un paramétrage différent pour les éditeurs de texte brut, Transact-SQL ou XML, vous devrez définir les options de ces éditeurs après avoir appliqué les sélections effectuées dans la boîte de dialogue **Tous les langages**.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-110">If you set an option using this dialog, but want a different setting for the Plain Text, Transact-SQL, or XML editors, you must set the options for those editors after applying your selections in the **All Languages** dialog.</span></span>  
  
 <span data-ttu-id="b3b5d-111">Le message « Les paramètres de mise en retrait (ou de tabulation) pour les formats de texte individuels sont en conflit » s'affiche lorsque différents paramètres ont été sélectionnés pour des éditeurs particuliers.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-111">The message "The indentation (or tab) settings for individual text formats conflict with each other" is displayed when different settings have been selected for particular editors.</span></span> <span data-ttu-id="b3b5d-112">Ce rappel s'affiche notamment si l'option **Mise en retrait** est sélectionnée pour **Texte brut**, et **Aucun** pour **XML**.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-112">For example, this reminder is displayed if the **Block indenting** option is selected for **Plain Text**, but **None** is selected for **XML**.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="b3b5d-113">Mise en retrait</span><span class="sxs-lookup"><span data-stu-id="b3b5d-113">Indenting</span></span>  
 <span data-ttu-id="b3b5d-114">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="b3b5d-114">**None**</span></span>  
 <span data-ttu-id="b3b5d-115">Lorsque cette option est activée, la nouvelle ligne créée grâce à la touche ENTRÉE n'est pas mise en retrait.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-115">When this option is selected, the new line created when you press ENTER is not indented.</span></span> <span data-ttu-id="b3b5d-116">Le curseur est placé au niveau de la première colonne de la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-116">The cursor is placed at the first column of the new line.</span></span>  
  
 <span data-ttu-id="b3b5d-117">**Bloquer**</span><span class="sxs-lookup"><span data-stu-id="b3b5d-117">**Block**</span></span>  
 <span data-ttu-id="b3b5d-118">Lorsque cette option est activée, la nouvelle ligne créée grâce à la touche ENTRÉE est automatiquement mise en retrait à la même distance que la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-118">When this option is selected, the new line created when you press ENTER is automatically indented the same distance as the previous line was indented.</span></span>  
  
 <span data-ttu-id="b3b5d-119">**Intelligente**</span><span class="sxs-lookup"><span data-stu-id="b3b5d-119">**Smart**</span></span>  
 <span data-ttu-id="b3b5d-120">Lorsque cette option est activée, la nouvelle ligne créée grâce à la touche ENTRÉE est positionnée en fonction du contexte.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-120">When this option is selected, the new line created when you press ENTER is positioned according to the context.</span></span>  
  
## <a name="tabs"></a><span data-ttu-id="b3b5d-121">Tabulations</span><span class="sxs-lookup"><span data-stu-id="b3b5d-121">Tabs</span></span>  
 <span data-ttu-id="b3b5d-122">**Taille des tabulation**</span><span class="sxs-lookup"><span data-stu-id="b3b5d-122">**Tab size**</span></span>  
 <span data-ttu-id="b3b5d-123">Définit la distance en espaces entre les taquets de tabulation.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-123">Sets the distance in spaces between tab stops.</span></span> <span data-ttu-id="b3b5d-124">La valeur par défaut est quatre espaces.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-124">The default is four spaces.</span></span>  
  
 <span data-ttu-id="b3b5d-125">**Taille du retrait**</span><span class="sxs-lookup"><span data-stu-id="b3b5d-125">**Indent size**</span></span>  
 <span data-ttu-id="b3b5d-126">Définit la taille en espaces d'une mise en retrait automatique.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-126">Sets the size in spaces of an automatic indentation.</span></span> <span data-ttu-id="b3b5d-127">La valeur par défaut est quatre espaces.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-127">The default is four spaces.</span></span> <span data-ttu-id="b3b5d-128">Des tabulations et/ou des espaces seront insérés pour occuper la taille spécifiée.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-128">Tab characters, space characters, or both will be inserted to fill the specified size.</span></span>  
  
 <span data-ttu-id="b3b5d-129">**Insérer des espaces**</span><span class="sxs-lookup"><span data-stu-id="b3b5d-129">**Insert spaces**</span></span>  
 <span data-ttu-id="b3b5d-130">Lorsque cette option est activée, les opérations de mise en retrait insèrent uniquement des espaces et non des tabulations.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-130">When this option is selected, indent operations insert only space characters, not tab characters.</span></span> <span data-ttu-id="b3b5d-131">Si l'option **Taille du retrait** a la valeur 5, par exemple, cinq espaces sont insérés lorsque vous appuyez sur TAB ou que vous cliquez sur le bouton **Augmenter le retrait** de la barre d'outils de la fenêtre principale de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3b5d-131">If **Indent size** is set to 5, for example, then five space characters are inserted whenever you press the TAB key or click the **Increase Indent** button on the toolbar of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] main window.</span></span>  
  
 <span data-ttu-id="b3b5d-132">**Conserver les tabulations**</span><span class="sxs-lookup"><span data-stu-id="b3b5d-132">**Keep tabs**</span></span>  
 <span data-ttu-id="b3b5d-133">Lorsque cette option est activée, les opérations de mise en retrait insèrent autant de tabulations que possible.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-133">When this option is selected, indent operations insert as many tab characters as possible.</span></span> <span data-ttu-id="b3b5d-134">Chaque tabulation remplit le nombre d'espaces spécifié dans **Taille de tabulation**.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-134">Each tab character fills the number of spaces specified in **Tab size**.</span></span> <span data-ttu-id="b3b5d-135">Si la valeur de **Taille du retrait** n'est pas un multiple pair de la valeur de **Taille de tabulation**, des espaces sont ajoutés pour remplir la différence.</span><span class="sxs-lookup"><span data-stu-id="b3b5d-135">If **Indent size** is not an even multiple of **Tab size**, space characters are added to fill in the difference.</span></span>  
  
  
