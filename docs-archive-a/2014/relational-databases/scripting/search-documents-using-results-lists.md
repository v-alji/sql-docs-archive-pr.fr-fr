---
title: Effectuer une recherche dans des documents à l'aide des listes de résultats
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], result lists
- result list searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], multiple files
- Query Editor [SQL Server Management Studio], search multiple files
ms.assetid: 275e1b6c-fbd0-4408-af77-35903f90657c
author: rothja
ms.author: jroth
ms.openlocfilehash: 58ff3754bc1667de75426e52b3ddd855e7d1a348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613959"
---
# <a name="search-documents-using-results-lists"></a><span data-ttu-id="736f5-102">Effectuer une recherche dans des documents à l'aide des listes de résultats</span><span class="sxs-lookup"><span data-stu-id="736f5-102">Search Documents Using Results Lists</span></span>
  <span data-ttu-id="736f5-103">À l’aide de la boîte de dialogue **Rechercher et remplacer** , vous pouvez rechercher et remplacer du texte dans tous les fichiers d’un projet, d’une solution ou d’un dossier du système de fichiers, même s’ils ne sont pas ouverts dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="736f5-103">Using the **Find and Replace** dialog box, you can search and replace text in all files in a project or solution or in a file system folder, even when they are not open in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="736f5-104">Les occurrences trouvées lors d’une recherche effectuée dans la boîte de dialogue **Rechercher et remplacer** s’affichent dans les fenêtres Résultats de la recherche 1 et Résultats de la recherche 2, ce qui vous permet de voir le texte exact de la ligne contenant le résultat.</span><span class="sxs-lookup"><span data-stu-id="736f5-104">Matches from searches that were performed with the **Find and Replace** dialog box appear in the Find Results 1 and Find Results 2 windows, which allows you to view the exact text from the line containing the match.</span></span>  
  
### <a name="to-search-in-multiple-files"></a><span data-ttu-id="736f5-105">Pour effectuer une recherche dans plusieurs fichiers</span><span class="sxs-lookup"><span data-stu-id="736f5-105">To search in multiple files</span></span>  
  
1.  <span data-ttu-id="736f5-106">Dans le menu **Edition** , pointez sur **Rechercher et remplacer** , puis cliquez sur **Rechercher dans les fichiers**.</span><span class="sxs-lookup"><span data-stu-id="736f5-106">On the **Edit** menu, point to **Find and Replace,** and then click **Find in Files**.</span></span>  
  
2.  <span data-ttu-id="736f5-107">Dans la zone de texte **Rechercher** , entrez le texte à rechercher.</span><span class="sxs-lookup"><span data-stu-id="736f5-107">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="736f5-108">Dans la liste **Regarder dans** , cliquez sur **Tous les documents ouverts**, **Projet en cours**, **Solution complète**ou tapez un chemin de répertoire.</span><span class="sxs-lookup"><span data-stu-id="736f5-108">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
4.  <span data-ttu-id="736f5-109">Dans la liste **Types de fichiers** , sélectionnez l’un des jeux d’extensions de fichier répertoriés ou entrez les extensions correspondant aux types de fichiers à analyser en les séparant par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="736f5-109">In the **File types** list, select one of the listed sets of file extensions or enter the extensions for the types of files to be searched, separated by semicolons.</span></span> <span data-ttu-id="736f5-110">Spécifiez \*.\* pour effectuer la recherche dans tous les fichiers du répertoire sélectionné dans la liste déroulante **Regarder dans** .</span><span class="sxs-lookup"><span data-stu-id="736f5-110">Use \*.\* to search all files in the directory listed in the **Look in** drop-down list.</span></span>  
  
5.  <span data-ttu-id="736f5-111">Sélectionnez d'autres options pour affiner la recherche.</span><span class="sxs-lookup"><span data-stu-id="736f5-111">Select from the remaining search options to improve the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="736f5-112">Cliquez sur **Rechercher** pour commencer la recherche.</span><span class="sxs-lookup"><span data-stu-id="736f5-112">Click **Find** to begin the search.</span></span>  
  
 <span data-ttu-id="736f5-113">Les résultats de la recherche s'affichent par défaut dans la fenêtre Résultats de la recherche 1.</span><span class="sxs-lookup"><span data-stu-id="736f5-113">The matches for the search appear in the Find Results 1 window by default.</span></span> <span data-ttu-id="736f5-114">Vous pouvez parcourir les résultats de la recherche en double-cliquant sur chaque entrée de la fenêtre Résultats de la recherche 1.</span><span class="sxs-lookup"><span data-stu-id="736f5-114">You can browse the search matches by double-clicking each entry in the Find Results 1 window.</span></span> <span data-ttu-id="736f5-115">Pour afficher les résultats de la recherche dans une nouvelle fenêtre, cochez la case **Afficher dans Rechercher 2**.</span><span class="sxs-lookup"><span data-stu-id="736f5-115">To view the search results in a new window, select **Display in Find 2**.</span></span>  
  
#### <a name="to-replace-across-multiple-files-or-folders"></a><span data-ttu-id="736f5-116">Pour effectuer un remplacement dans plusieurs fichiers ou dossiers</span><span class="sxs-lookup"><span data-stu-id="736f5-116">To replace across multiple files or folders</span></span>  
  
1.  <span data-ttu-id="736f5-117">Dans le menu **Edition** , pointez sur **Rechercher et remplacer** , puis cliquez sur **Remplacer dans les fichiers**.</span><span class="sxs-lookup"><span data-stu-id="736f5-117">On the **Edit** menu, point to **Find and Replace,** and then click **Replace in Files**.</span></span>  
  
2.  <span data-ttu-id="736f5-118">Dans la zone de texte **Rechercher** , entrez le texte à rechercher.</span><span class="sxs-lookup"><span data-stu-id="736f5-118">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="736f5-119">Dans la zone de texte **Remplacer par** , entrez le texte qui doit remplacer le texte recherché.</span><span class="sxs-lookup"><span data-stu-id="736f5-119">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="736f5-120">Dans la liste **Regarder dans** , cliquez sur **Tous les documents ouverts**, **Projet en cours**, **Solution complète**ou tapez un chemin de répertoire.</span><span class="sxs-lookup"><span data-stu-id="736f5-120">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
5.  <span data-ttu-id="736f5-121">Cliquez sur **Remplacer** pour remplacer le résultat de la recherche en cours par le texte spécifié dans la zone **Remplacer par** .</span><span class="sxs-lookup"><span data-stu-id="736f5-121">Click **Replace** to replace the current search match with the text in the **Replace with** box.</span></span> <span data-ttu-id="736f5-122">Vous pouvez ignorer une occurrence isolée en cliquant sur **Suivant** ou l’ensemble d’un fichier en cliquant sur **Ignorer le fichier**.</span><span class="sxs-lookup"><span data-stu-id="736f5-122">You can skip a single match by clicking **Find Next** or skip an entire file clicking **Skip File**.</span></span>  
  
     <span data-ttu-id="736f5-123">\- ou -</span><span class="sxs-lookup"><span data-stu-id="736f5-123">\- or -</span></span>  
  
     <span data-ttu-id="736f5-124">Cliquez sur **Remplacer tout** pour remplacer toutes les occurrences trouvées par le texte spécifié dans la zone **Remplacer par** .</span><span class="sxs-lookup"><span data-stu-id="736f5-124">Choose **Replace all** to replace all search matches with the text in the **Replace with** box.</span></span> <span data-ttu-id="736f5-125">Cochez la case **Conserver les fichiers modifiés ouverts après un remplacement global** si vous souhaitez annuler certains remplacements à un autre moment.</span><span class="sxs-lookup"><span data-stu-id="736f5-125">Select **Keep modified files open after Replace All** if you want to undo some of the replacements at another time.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="736f5-126">La commande**Remplacer tout** remplace toutes les occurrences trouvées, notamment celles que vous avez ignouées en cliquant sur le bouton **Ignouer le fichier** ou **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="736f5-126">**Replace all** replaces all search matches, including those in files you have skipped with **Skip File** or **Find Next**.</span></span> <span data-ttu-id="736f5-127">Vous pouvez utiliser **Annuler** uniquement pour les remplacements effectués dans des fichiers restant ouverts après cette opération.</span><span class="sxs-lookup"><span data-stu-id="736f5-127">You can only use **Undo** for replacements made in files that remain open after the replacement operation.</span></span>  
  
 <span data-ttu-id="736f5-128">Les informations relatives aux remplacements s'affichent par défaut dans la fenêtre Résultats de la recherche 1.</span><span class="sxs-lookup"><span data-stu-id="736f5-128">Replacement information appears in the Find Results 1 window by default.</span></span> <span data-ttu-id="736f5-129">Vous pouvez parcourir les remplacements en double-cliquant sur chaque entrée de la fenêtre Résultats de la recherche 1.</span><span class="sxs-lookup"><span data-stu-id="736f5-129">You can browse replacements by double-clicking each entry in the Find Results 1 window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="736f5-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="736f5-130">See Also</span></span>  
 <span data-ttu-id="736f5-131">[Recherche et remplacement](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="736f5-131">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="736f5-132">[Effectuer une recherche de façon interactive dans des documents](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="736f5-132">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="736f5-133">[Rechercher du texte avec des caractères génériques](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="736f5-133">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="736f5-134">Rechercher du texte avec des expressions régulières</span><span class="sxs-lookup"><span data-stu-id="736f5-134">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
