---
title: Effectuer une recherche de façon interactive dans des documents
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- interactive searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], interactive
- Query Editor [SQL Server Management Studio], interactive search
ms.assetid: dae65ac5-67af-45c6-a6e0-952fea26d680
author: rothja
ms.author: jroth
ms.openlocfilehash: 5603db77ea4f58d4bb036635a23ec3cfa400a818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613964"
---
# <a name="search-documents-interactively"></a><span data-ttu-id="4840e-102">Effectuer une recherche de façon interactive dans des documents</span><span class="sxs-lookup"><span data-stu-id="4840e-102">Search Documents Interactively</span></span>
  <span data-ttu-id="4840e-103">La boîte de dialogue **Rechercher et remplacer** vous permet d’effectuer une recherche dans un ou plusieurs fichiers ouverts, ou encore dans une ou plusieurs fenêtres ouvertes, puis de faire défiler les occurrences trouvées l’une après l’autre.</span><span class="sxs-lookup"><span data-stu-id="4840e-103">Using the **Find and Replace** dialog box, you can search one or more open files or windows and move through the search matches one by one.</span></span> <span data-ttu-id="4840e-104">Cette technique vous permet de voir chaque occurrence trouvée dans le contexte du texte qui la contient.</span><span class="sxs-lookup"><span data-stu-id="4840e-104">This technique allows you to review each individual search match in the context of the text around the match.</span></span> <span data-ttu-id="4840e-105">Vous avez également la possibilité d’effectuer des opérations de recherche en bloc et de voir les occurrences trouvées dans un format de rapport à l’aide de la boîte de dialogue **Rechercher et remplacer** .</span><span class="sxs-lookup"><span data-stu-id="4840e-105">You also have the option of performing bulk find operations and reviewing search matches in report format using the **Find and Replace** dialog box.</span></span>  
  
### <a name="to-search-all-open-documents"></a><span data-ttu-id="4840e-106">Pour effectuer une recherche dans tous les documents ouverts</span><span class="sxs-lookup"><span data-stu-id="4840e-106">To search all open documents</span></span>  
  
1.  <span data-ttu-id="4840e-107">Ouvrez les éléments dans lesquels vous voulez effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="4840e-107">Open the items you wish to search.</span></span>  
  
2.  <span data-ttu-id="4840e-108">Dans le menu **Modifier** , pointez sur **Rechercher et remplacer** , puis cliquez sur **Recherche rapide**.</span><span class="sxs-lookup"><span data-stu-id="4840e-108">On the **Edit** menu, point to **Find and Replace,** and then click **QuickFind**.</span></span>  
  
3.  <span data-ttu-id="4840e-109">Dans la zone de texte **Rechercher et remplacer** , entrez le texte à rechercher.</span><span class="sxs-lookup"><span data-stu-id="4840e-109">In the **Find and Replace** text box, enter the text to search for.</span></span>  
  
4.  <span data-ttu-id="4840e-110">Dans la liste **Regarder dans** , sélectionnez **Tous les documents ouverts**.</span><span class="sxs-lookup"><span data-stu-id="4840e-110">In the **Look in** list, select **All Open Documents**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4840e-111">Quand vous sélectionnez **Tous les documents ouverts** , il est possible que certains fichiers ouverts soient ignorés pendant la recherche.</span><span class="sxs-lookup"><span data-stu-id="4840e-111">Certain open files might not be searched when **All Open Documents** is selected.</span></span> <span data-ttu-id="4840e-112">Seuls les fichiers ouverts dans une vue texte, telle que la vue Code, sont inclus dans les recherches.</span><span class="sxs-lookup"><span data-stu-id="4840e-112">Only files currently open in a textual view, such as Code view, are included in searches.</span></span> <span data-ttu-id="4840e-113">Les fichiers dans une vue Concepteur de ne sont pas inclus.</span><span class="sxs-lookup"><span data-stu-id="4840e-113">Files in Designer view are not included in searches.</span></span>  
  
5.  <span data-ttu-id="4840e-114">Sélectionnez d'autres options pour affiner la recherche.</span><span class="sxs-lookup"><span data-stu-id="4840e-114">Select additional search options to increase the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="4840e-115">Cliquez sur **Suivant** pour lancer la recherche et continuez de cliquer sur **Suivant** jusqu’à ce que le dernier fichier ait été analysé.</span><span class="sxs-lookup"><span data-stu-id="4840e-115">Click **Find Next** to start the search, and continue clicking **Find Next** until the last file has been searched.</span></span>  
  
 <span data-ttu-id="4840e-116">Lorsque la recherche atteint le début ou la fin du document, un message s'affiche dans la barre d'état.</span><span class="sxs-lookup"><span data-stu-id="4840e-116">When the search passes the beginning or end of the document, a message is displayed in the status bar.</span></span> <span data-ttu-id="4840e-117">Lorsqu'elle revient à son point de départ, une boîte de message apparaît.</span><span class="sxs-lookup"><span data-stu-id="4840e-117">A message box appears when the search reaches the starting point of the search.</span></span>  
  
#### <a name="to-replace-in-all-active-files-interactively"></a><span data-ttu-id="4840e-118">Pour effectuer un remplacement interactif dans tous les fichiers actifs</span><span class="sxs-lookup"><span data-stu-id="4840e-118">To replace in all active files interactively</span></span>  
  
1.  <span data-ttu-id="4840e-119">Dans le menu **Edition** , pointez sur **Rechercher et remplacer**, puis cliquez sur **Remplacement rapide**.</span><span class="sxs-lookup"><span data-stu-id="4840e-119">On the **Edit** menu, point to **Find and Replace**, and then click **QuickReplace**.</span></span>  
  
2.  <span data-ttu-id="4840e-120">Dans la zone de texte **Rechercher** , entrez le texte à rechercher.</span><span class="sxs-lookup"><span data-stu-id="4840e-120">In the **Find what** box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="4840e-121">Dans la zone de texte **Remplacer par** , entrez le texte qui doit remplacer le texte recherché.</span><span class="sxs-lookup"><span data-stu-id="4840e-121">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="4840e-122">Dans la liste **Regarder dans** , sélectionnez **Tous les documents ouverts**.</span><span class="sxs-lookup"><span data-stu-id="4840e-122">In the **Look in** list, select **All Open Documents**.</span></span>  
  
5.  <span data-ttu-id="4840e-123">Cliquez sur **Remplacer**et continuez de cliquer sur **Remplacer** jusqu’à ce que la dernière occurrence trouvée dans le dernier fichier ait été remplacée.</span><span class="sxs-lookup"><span data-stu-id="4840e-123">Click **Replace**, and continue clicking **Replace** until the last match in the last file has been replaced.</span></span> <span data-ttu-id="4840e-124">Cliquez sur **Suivant** pour ignorer une occurrence que vous ne souhaitez pas remplacer.</span><span class="sxs-lookup"><span data-stu-id="4840e-124">Click **Find Next** to skip a match you do not want to replace.</span></span>  
  
     <span data-ttu-id="4840e-125">-ou-</span><span class="sxs-lookup"><span data-stu-id="4840e-125">-or-</span></span>  
  
     <span data-ttu-id="4840e-126">Cliquez sur **Remplacer tout** pour remplacer toutes les occurrences.</span><span class="sxs-lookup"><span data-stu-id="4840e-126">Choose **Replace All** to replace all matches.</span></span> <span data-ttu-id="4840e-127">Un message affiche alors le nombre total de remplacements effectués.</span><span class="sxs-lookup"><span data-stu-id="4840e-127">A message box appears, listing the total number of replacements.</span></span>  
  
 <span data-ttu-id="4840e-128">La commande **Remplacer tout** remplace toutes les occurrences trouvées, y compris celles que vous avez ignorées en cliquant sur le bouton **Suivant** .</span><span class="sxs-lookup"><span data-stu-id="4840e-128">The **Replace All** command replaces all search matches, including those you have skipped with the **Find Next** button.</span></span> <span data-ttu-id="4840e-129">Pour annuler l’action du bouton **Remplacer tout**, cliquez sur **Annuler** dans le menu **Edition** avant de fermer un fichier.</span><span class="sxs-lookup"><span data-stu-id="4840e-129">To cancel **Replace All**, click **Undo** from the **Edit** menu before closing any of the files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4840e-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4840e-130">See Also</span></span>  
 <span data-ttu-id="4840e-131">[Effectuer une recherche incrémentielle dans un document actif](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="4840e-131">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="4840e-132">[Recherche et remplacement](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="4840e-132">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="4840e-133">[Effectuer une recherche dans des documents à l'aide des listes de résultats](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="4840e-133">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="4840e-134">[Rechercher du texte avec des caractères génériques](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="4840e-134">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="4840e-135">Rechercher du texte avec des expressions régulières</span><span class="sxs-lookup"><span data-stu-id="4840e-135">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
