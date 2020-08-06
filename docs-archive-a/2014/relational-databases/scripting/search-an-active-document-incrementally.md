---
title: Effectuer une recherche incrémentielle dans un document actif
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], incremental
- Query Editor [SQL Server Management Studio], incremental search
- incremental searches [SQL Server Management Studio]
ms.assetid: 490bb36c-dd43-4219-9e2a-ff27046b9395
author: rothja
ms.author: jroth
ms.openlocfilehash: aefc2f0b7abff5992a8f4f7817e564ef1b72009d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602044"
---
# <a name="search-an-active-document-incrementally"></a><span data-ttu-id="c7318-102">Effectuer une recherche incrémentielle dans un document actif</span><span class="sxs-lookup"><span data-stu-id="c7318-102">Search an Active Document Incrementally</span></span>
  <span data-ttu-id="c7318-103">Vous pouvez effectuer une recherche incrémentielle dans un document ou une fenêtre unique en entrant du texte.</span><span class="sxs-lookup"><span data-stu-id="c7318-103">You can search a single document or window incrementally by entering text.</span></span> <span data-ttu-id="c7318-104">L'opération de recherche met en surbrillance le premier ensemble de caractères qui correspond aux caractères entrés pendant la recherche incrémentielle dans le document ou la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="c7318-104">The search operation highlights the first set of characters that matches the characters entered during the incremental search in the document or window.</span></span> <span data-ttu-id="c7318-105">La recherche incrémentielle recherche automatiquement l'ensemble du texte dans un document ou une fenêtre, à l'exception du texte caché.</span><span class="sxs-lookup"><span data-stu-id="c7318-105">Incremental search automatically searches all of the text within a document or window except for text that has been hidden.</span></span>  
  
 <span data-ttu-id="c7318-106">Quand l’option **Respecter la casse** est activée, la recherche incrémentielle utilise les critères de votre recherche précédente.</span><span class="sxs-lookup"><span data-stu-id="c7318-106">For the **Match case** option, incremental search uses the criteria from your previous search.</span></span> <span data-ttu-id="c7318-107">Par exemple, si vous avez effectué une recherche dans plusieurs fichiers à l’aide de la boîte de dialogue **Rechercher dans les fichiers** et que vous avez sélectionné l’option **Respecter la casse**, la prochaine recherche incrémentielle respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="c7318-107">For example, if you searched across multiple files using the **Find in Files** dialog box and select **Match Case**, and you next search incrementally, the search will be case-sensitive.</span></span>  
  
### <a name="to-search-incrementally"></a><span data-ttu-id="c7318-108">Pour effectuer une recherche incrémentielle</span><span class="sxs-lookup"><span data-stu-id="c7318-108">To search incrementally</span></span>  
  
1.  <span data-ttu-id="c7318-109">Ouvrez le fichier ou la fenêtre dans laquelle vous souhaitez effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="c7318-109">Open the file or window to you want to search.</span></span>  
  
2.  <span data-ttu-id="c7318-110">Dans le menu **Edition** , pointez sur **Avancée**, puis cliquez sur **Recherche incrémentielle**.</span><span class="sxs-lookup"><span data-stu-id="c7318-110">On the **Edit** menu, point to **Advanced**, and then click **Incremental Search**.</span></span>  
  
     <span data-ttu-id="c7318-111">L'icône du curseur se transforme en jumelles avec une flèche qui indique le sens de la recherche et la barre d'état affiche le texte « Recherche incrémentielle ».</span><span class="sxs-lookup"><span data-stu-id="c7318-111">The cursor icon changes to a binocular with an arrow, indicating the search direction, and the status bar displays "Incremental Search."</span></span>  
  
3.  <span data-ttu-id="c7318-112">Commencez à taper la chaîne de texte à rechercher.</span><span class="sxs-lookup"><span data-stu-id="c7318-112">Begin typing the text string.</span></span>  
  
     <span data-ttu-id="c7318-113">La barre d'état affiche le texte que vous entrez et l'éditeur met en surbrillance la première occurrence trouvée.</span><span class="sxs-lookup"><span data-stu-id="c7318-113">The status bar displays the text you are entering while the editor highlights the first occurrence that matches the text.</span></span> <span data-ttu-id="c7318-114">À mesure que vous tapez, l'éditeur progresse et surligne l'occurrence suivante.</span><span class="sxs-lookup"><span data-stu-id="c7318-114">As you continue typing, the editor moves to the next match and highlights it.</span></span> <span data-ttu-id="c7318-115">S'il ne trouve pas de chaîne identique, la barre d'état affiche le texte suivant.</span><span class="sxs-lookup"><span data-stu-id="c7318-115">If no matches are available, the status bar displays the following.</span></span>  
  
    ```  
    Incremental Search: <text> (not found)  
    ```  
  
 <span data-ttu-id="c7318-116">Les recherches incrémentielles sont effectuées à partir de l'emplacement courant du document, de haut en bas et de gauche à droite.</span><span class="sxs-lookup"><span data-stu-id="c7318-116">Incremental searches are performed from the current location in the document downwards from left to right.</span></span> <span data-ttu-id="c7318-117">Les recherches incrémentielles peuvent être effectuées à l'aide de touches de raccourci clavier.</span><span class="sxs-lookup"><span data-stu-id="c7318-117">Incremental searches can be done using keyboard shortcut keys.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7318-118">Pour obtenir la liste complète des touches de raccourci clavier, consultez [Raccourcis clavier dans SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="c7318-118">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7318-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7318-119">See Also</span></span>  
 <span data-ttu-id="c7318-120">[Recherche et remplacement](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="c7318-120">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="c7318-121">[Effectuer une recherche de façon interactive dans des documents](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="c7318-121">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="c7318-122">[Effectuer une recherche dans des documents à l'aide des listes de résultats](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="c7318-122">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="c7318-123">[Rechercher du texte avec des caractères génériques](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="c7318-123">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="c7318-124">Rechercher du texte avec des expressions régulières</span><span class="sxs-lookup"><span data-stu-id="c7318-124">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
