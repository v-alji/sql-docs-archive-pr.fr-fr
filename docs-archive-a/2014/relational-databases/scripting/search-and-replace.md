---
title: Recherche et remplacement
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- match case [SQL Server]
- undo operations
- searches [SQL Server Management Studio]
- replacing text
- quick search and replaces [SQL Server Management Studio]
- Query Editor [SQL Server Management Studio], undo
- Query Editor [SQL Server Management Studio], searching
- regular expressions [SQL Server Management Studio]
- finding text [SQL Server Management Studio]
- text [SQL Server], search and replace operations
- finding [SQL Server Management Studio]
- locating text
- Query Editor [SQL Server Management Studio], replacing text
- Find and Replace dialog box
- wildcard options [SQL Server Management Studio]
- match whole word [SQL Server]
- searches [SQL Server Management Studio], replacing
ms.assetid: 3641c7b3-3e3e-4ddd-af82-c15b50004f94
author: rothja
ms.author: jroth
ms.openlocfilehash: 55422fa7201213477426c7bc25c45ff05acf8945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602041"
---
# <a name="search-and-replace"></a><span data-ttu-id="39376-102">Recherche et remplacement</span><span class="sxs-lookup"><span data-stu-id="39376-102">Search and Replace</span></span>
  <span data-ttu-id="39376-103">Il existe plusieurs méthodes différentes pour rechercher et remplacer du texte.</span><span class="sxs-lookup"><span data-stu-id="39376-103">There are several different ways to find and replace text.</span></span> <span data-ttu-id="39376-104">Dans le menu **Edition** , la commande **Rechercher et remplacer** propose quatre options : **Recherche rapide**, **Remplacement rapide**, **Rechercher dans les fichiers**ou **Remplacer dans les fichiers**.</span><span class="sxs-lookup"><span data-stu-id="39376-104">On the **Edit** menu, **Find and Replace** offers four choices: **Quick Find**, **Quick Replace**, **Find in Files**, or **Replace in Files**.</span></span> <span data-ttu-id="39376-105">Chaque option ouvre une version de la boîte de dialogue **Rechercher et remplacer** .</span><span class="sxs-lookup"><span data-stu-id="39376-105">Each of these opens versions of the **Find and Replace** dialog box.</span></span> <span data-ttu-id="39376-106">Vous pouvez également effectuer une recherche sans l'aide de l'une de ces boîtes de dialogue. Pour ce faire, il vous suffit d'utiliser les touches de raccourci clavier de la recherche incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="39376-106">You can also search without a dialog box by using incremental search keyboard shortcut keys.</span></span> <span data-ttu-id="39376-107">Ces techniques vous permettent de contrôler la portée de l'opération de recherche et de remplacement et de choisir la méthode de révision des occurrences trouvées et des remplacements.</span><span class="sxs-lookup"><span data-stu-id="39376-107">These techniques allow you to control the scope of find and replace, and choose the method of reviewing search matches and replacements.</span></span>  
  
 <span data-ttu-id="39376-108">Tenez compte des informations suivantes lorsque vous recherchez et remplacez du texte :</span><span class="sxs-lookup"><span data-stu-id="39376-108">You should consider the following when you search and replace text:</span></span>  
  
-   <span data-ttu-id="39376-109">Les options définies dans la boîte de dialogue **Rechercher et remplacer** affectent toutes les recherches.</span><span class="sxs-lookup"><span data-stu-id="39376-109">Options set in the **Find and Replace** dialog box affect all the searches.</span></span> <span data-ttu-id="39376-110">Ces options comprennent **Respecter la casse**, **Mot entier**, **Rechercher vers le haut**, **Rechercher le texte masqué**, **Caractères génériques**, **Expressions régulières**, **Regarder dans tous les documents ouverts**et **Regarder dans le projet en cours**.</span><span class="sxs-lookup"><span data-stu-id="39376-110">These options include **Match case**, **Match whole word**, **Search up**, **Search hidden text**, **Wildcards**, **Regular Expressions**, **Look in All Open Documents**, and **Look in Current Project**.</span></span> <span data-ttu-id="39376-111">Les options ne sont pas toutes disponibles dans toutes les versions de la boîte de dialogue **Rechercher et remplacer** .</span><span class="sxs-lookup"><span data-stu-id="39376-111">All options are not available in all versions of the **Find and Replace** dialog box.</span></span>  
  
-   <span data-ttu-id="39376-112">La commande**Annuler** est disponible uniquement pour les documents qui sont restés ouverts après une opération de remplacement.</span><span class="sxs-lookup"><span data-stu-id="39376-112">**Undo** is available only for documents left open after a replace operation.</span></span>  
  
-   <span data-ttu-id="39376-113">L’action**Annuler** pour une opération **Remplacer tout** qui s’étend sur plusieurs fichiers est considérée comme une action en bloc sur tous les fichiers affectés.</span><span class="sxs-lookup"><span data-stu-id="39376-113">**Undo** for a **Replace All** operation that spans more than one file is considered a single, bulk action across all the affected files.</span></span> <span data-ttu-id="39376-114">Par conséquent, vous ne pouvez pas annuler des modifications dans certains fichiers et les conserver dans d'autres.</span><span class="sxs-lookup"><span data-stu-id="39376-114">That is, you cannot undo the change in some files while retaining the change in other files.</span></span>  
  
 <span data-ttu-id="39376-115">En règle générale, vous ne pouvez pas rechercher des éléments avec des vues graphiques.</span><span class="sxs-lookup"><span data-stu-id="39376-115">Generally, you cannot search items with graphical views.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39376-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39376-116">See Also</span></span>  
 <span data-ttu-id="39376-117">[Effectuer une recherche incrémentielle dans un document actif](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="39376-117">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="39376-118">[Effectuer une recherche de façon interactive dans des documents](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="39376-118">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="39376-119">[Effectuer une recherche dans des documents à l'aide des listes de résultats](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="39376-119">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="39376-120">[Rechercher du texte avec des caractères génériques](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="39376-120">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="39376-121">Rechercher du texte avec des expressions régulières</span><span class="sxs-lookup"><span data-stu-id="39376-121">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
