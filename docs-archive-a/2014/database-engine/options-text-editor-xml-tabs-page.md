---
title: 'Options (éditeur de texte : XML : page tabulations) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Tabs
ms.assetid: 13bf5f8c-aba3-4c05-b8bb-eb475797c9bd
author: rothja
ms.author: jroth
ms.openlocfilehash: 3047d6c05ffb88d07a4bf2e5b1d4143412046c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694680"
---
# <a name="options-text-editorxmltabs-page"></a><span data-ttu-id="f91db-102">Options (page Éditeur de texte : XML : Tabulations)</span><span class="sxs-lookup"><span data-stu-id="f91db-102">Options (Text Editor:XML:Tabs Page)</span></span>
  <span data-ttu-id="f91db-103">Cette boîte de dialogue vous permet de modifier le comportement de tabulation de l'Éditeur XML, qui permet de modifier des documents XML.</span><span class="sxs-lookup"><span data-stu-id="f91db-103">This dialog box lets you change the tabbing behavior of the XML Editor, which is used to edit XML documents.</span></span> <span data-ttu-id="f91db-104">Pour afficher ces paramètres, cliquez sur **Options** dans le menu **Outils** , développez le dossier **Éditeur de texte** , puis le sous-dossier **XML** , et cliquez ensuite sur **Tabulations**.</span><span class="sxs-lookup"><span data-stu-id="f91db-104">To display these settings, click **Options** on the **Tools** menu, expand the **Text Editor** folder, expand the **XML** subfolder and then click **Tabs**.</span></span>  
  
## <a name="setting-options-in-multiple-locations"></a><span data-ttu-id="f91db-105">Définition d'options en plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="f91db-105">Setting Options in Multiple Locations</span></span>  
 <span data-ttu-id="f91db-106">Les options de l'Éditeur XML peuvent également être définies dans la boîte de dialogue **Tous les langages Général** .</span><span class="sxs-lookup"><span data-stu-id="f91db-106">Options for the XML Editor can also be set in the **All Languages General** dialog.</span></span> <span data-ttu-id="f91db-107">Si vous utilisez les boîtes de dialogue **tous les langages** pour définir des options différentes pour les autres [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] éditeurs, comme les éditeurs DMX ou MDX, vous devez réinitialiser les options de l’éditeur XML à l’aide de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f91db-107">If you use the **All Languages** dialogs to set different options for the other [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, such as the DMX or MDX editors, you must reset the XML Editor options using this dialog.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="f91db-108">Mise en retrait</span><span class="sxs-lookup"><span data-stu-id="f91db-108">Indenting</span></span>  
 <span data-ttu-id="f91db-109">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="f91db-109">**None**</span></span>  
 <span data-ttu-id="f91db-110">Lorsque cette option est activée, la nouvelle ligne créée grâce à la touche ENTRÉE n'est pas mise en retrait.</span><span class="sxs-lookup"><span data-stu-id="f91db-110">When this option is selected, the new line created when you press ENTER is not indented.</span></span> <span data-ttu-id="f91db-111">Le curseur est placé au niveau de la première colonne de la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="f91db-111">The cursor is placed at the first column of the new line.</span></span>  
  
 <span data-ttu-id="f91db-112">**Bloquer**</span><span class="sxs-lookup"><span data-stu-id="f91db-112">**Block**</span></span>  
 <span data-ttu-id="f91db-113">Lorsque cette option est sélectionnée, la nouvelle ligne créée lorsque vous appuyez sur Entrée est automatiquement mise en retrait comme la ligne précédente.</span><span class="sxs-lookup"><span data-stu-id="f91db-113">When this option is selected, the new line created when you press ENTER is automatically indented the same distance as the previous line.</span></span>  
  
 <span data-ttu-id="f91db-114">**Intelligente**</span><span class="sxs-lookup"><span data-stu-id="f91db-114">**Smart**</span></span>  
 <span data-ttu-id="f91db-115">Lorsque cette option est activée, la nouvelle ligne créée grâce à la touche ENTRÉE est positionnée en fonction du contexte.</span><span class="sxs-lookup"><span data-stu-id="f91db-115">When this option is selected, the new line created when you press ENTER is positioned according to the context.</span></span> <span data-ttu-id="f91db-116">Par exemple, après une accolade ouvrante ({), les lignes incluses sont automatiquement mises en retrait d'une tabulation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="f91db-116">For example, after an opening brace ({), the included lines are automatically indented an extra tab stop.</span></span> <span data-ttu-id="f91db-117">L'accolade fermante (}) correspondante est réalignée sur l'accolade ouvrante.</span><span class="sxs-lookup"><span data-stu-id="f91db-117">The matching closing brace (}) is realigned with its opening brace.</span></span>  
  
## <a name="tabs"></a><span data-ttu-id="f91db-118">Tabulations</span><span class="sxs-lookup"><span data-stu-id="f91db-118">Tabs</span></span>  
 <span data-ttu-id="f91db-119">**Taille des tabulation**</span><span class="sxs-lookup"><span data-stu-id="f91db-119">**Tab size**</span></span>  
 <span data-ttu-id="f91db-120">Définit la distance en espaces entre les taquets de tabulation.</span><span class="sxs-lookup"><span data-stu-id="f91db-120">Sets the distance in spaces between tab stops.</span></span> <span data-ttu-id="f91db-121">La valeur par défaut est quatre espaces.</span><span class="sxs-lookup"><span data-stu-id="f91db-121">The default is four spaces.</span></span>  
  
 <span data-ttu-id="f91db-122">**Taille du retrait**</span><span class="sxs-lookup"><span data-stu-id="f91db-122">**Indent size**</span></span>  
 <span data-ttu-id="f91db-123">Définit la taille en espaces d'une mise en retrait automatique.</span><span class="sxs-lookup"><span data-stu-id="f91db-123">Sets the size in spaces of an automatic indentation.</span></span> <span data-ttu-id="f91db-124">La valeur par défaut est quatre espaces.</span><span class="sxs-lookup"><span data-stu-id="f91db-124">The default is four spaces.</span></span> <span data-ttu-id="f91db-125">Des tabulations et/ou des espaces sont insérés pour occuper la taille spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f91db-125">Tab characters, space characters, or both are inserted to fill the specified size.</span></span>  
  
 <span data-ttu-id="f91db-126">**Insérer des espaces**</span><span class="sxs-lookup"><span data-stu-id="f91db-126">**Insert spaces**</span></span>  
 <span data-ttu-id="f91db-127">Lorsque cette option est activée, les opérations de mise en retrait insèrent uniquement des espaces et non des tabulations.</span><span class="sxs-lookup"><span data-stu-id="f91db-127">When this option is selected, indent operations insert only space characters, not tab characters.</span></span> <span data-ttu-id="f91db-128">Si par exemple **taille du retrait** a la valeur 5, cinq espaces sont insérés à chaque fois que vous appuyez sur la touche Tab ou que vous cliquez sur le bouton **augmenter le retrait** de la barre d’outils de la fenêtre principale [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f91db-128">If **Indent size** is set to 5, for example, then five space characters are inserted whenever you press the TAB key or click the **Increase Indent** button on the toolbar in the main [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] window.</span></span>  
  
 <span data-ttu-id="f91db-129">**Conserver les tabulations**</span><span class="sxs-lookup"><span data-stu-id="f91db-129">**Keep tabs**</span></span>  
 <span data-ttu-id="f91db-130">Lorsque cette option est activée, les opérations de mise en retrait insèrent autant de tabulations que possible.</span><span class="sxs-lookup"><span data-stu-id="f91db-130">When this option is selected, indent operations insert as many tab characters as possible.</span></span> <span data-ttu-id="f91db-131">Chaque tabulation remplit le nombre d'espaces spécifié dans **Taille de tabulation**.</span><span class="sxs-lookup"><span data-stu-id="f91db-131">Each tab character fills the number of spaces specified in **Tab size**.</span></span> <span data-ttu-id="f91db-132">Si la valeur de **Taille du retrait** n'est pas un multiple pair de la valeur de **Taille de tabulation**, des espaces sont ajoutés pour remplir la différence.</span><span class="sxs-lookup"><span data-stu-id="f91db-132">If **Indent size** is not an even multiple of **Tab size**, space characters are added to fill in the difference.</span></span>  
  
  
