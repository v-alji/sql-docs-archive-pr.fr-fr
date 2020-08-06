---
title: Défilement et extraction de lignes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- SQLFetchScroll function
- ODBC applications, cursors
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- fetching [ODBC]
- ODBC cursors, scrolling rows
ms.assetid: 9109f10d-326b-4a6d-8c97-831f60da8c4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 97586f82ddddb79581b0f9c027aa60d7822b472c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707508"
---
# <a name="scrolling-and-fetching-rows"></a><span data-ttu-id="b2af6-102">Défilement et extraction de lignes</span><span class="sxs-lookup"><span data-stu-id="b2af6-102">Scrolling and Fetching Rows</span></span>
  <span data-ttu-id="b2af6-103">Pour utiliser un curseur permettant le défilement, une application ODBC doit :</span><span class="sxs-lookup"><span data-stu-id="b2af6-103">To use a scrollable cursor, an ODBC application must:</span></span>  
  
-   <span data-ttu-id="b2af6-104">Définissez les fonctionnalités de curseur à l’aide de [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="b2af6-104">Set the cursor capabilities using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
-   <span data-ttu-id="b2af6-105">Ouvrez le curseur à l’aide de **SQLExecute** ou **SQLExecDirect**.</span><span class="sxs-lookup"><span data-stu-id="b2af6-105">Open the cursor using **SQLExecute** or **SQLExecDirect**.</span></span>  
  
-   <span data-ttu-id="b2af6-106">Faites défiler et récupérez des lignes à l’aide de **SQLFetch** ou [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="b2af6-106">Scroll and fetch rows using **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span>  
  
 <span data-ttu-id="b2af6-107">**SQLFetch** et **SQLFetchScroll** peuvent extraire des blocs de lignes à la fois.</span><span class="sxs-lookup"><span data-stu-id="b2af6-107">Both **SQLFetch** and **SQLFetchSroll** can fetch blocks of rows at a time.</span></span> <span data-ttu-id="b2af6-108">Le nombre de lignes retournées est spécifié à l’aide de **SQLSetStmtAttr** pour définir le paramètre SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="b2af6-108">The number of rows returned is specified by using **SQLSetStmtAttr** to set the SQL_ATTR_ROW_ARRAY_SIZE parameter.</span></span>  
  
 <span data-ttu-id="b2af6-109">Les applications ODBC peuvent utiliser **SQLFetch** pour effectuer une extraction à l’aide d’un curseur avant uniquement.</span><span class="sxs-lookup"><span data-stu-id="b2af6-109">ODBC applications can use **SQLFetch** to fetch through a forward-only cursor.</span></span>  
  
 <span data-ttu-id="b2af6-110">**SQLFetchScroll** est utilisé pour faire défiler un curseur.</span><span class="sxs-lookup"><span data-stu-id="b2af6-110">**SQLFetchScroll** is used to scroll around a cursor.</span></span> <span data-ttu-id="b2af6-111">**SQLFetchScroll** prend en charge l’extraction des ensembles de lignes suivant, précédent, premier et dernier en plus de l’extraction relative (extraction de *l’ensemble de* lignes à partir du début de l’ensemble de lignes actuel) et de l’extraction absolue (extraction de l’ensemble de lignes à partir de la ligne *n*).</span><span class="sxs-lookup"><span data-stu-id="b2af6-111">**SQLFetchScroll** supports fetching the next, prior, first, and last rowsets in addition to relative fetching (fetch the rowset *n* rows from the start of the current rowset) and absolute fetching (fetch the rowset starting at row *n*).</span></span> <span data-ttu-id="b2af6-112">Si *n* est négatif dans une extraction absolue, les lignes sont comptées à partir de la fin du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="b2af6-112">If *n* is negative in an absolute fetch, rows are counted from the end of the result set.</span></span> <span data-ttu-id="b2af6-113">Une extraction absolue de ligne -1 équivaut à l'extraction de l'ensemble de lignes qui démarre à la dernière ligne du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="b2af6-113">An absolute fetch of row -1 means to fetch the rowset that starts with the last row in the result set.</span></span>  
  
 <span data-ttu-id="b2af6-114">Les applications qui utilisent **SQLFetchScroll** uniquement pour ses fonctionnalités de curseur de bloc, telles que les rapports, sont susceptibles de traverser le jeu de résultats une seule fois, en utilisant uniquement l’option permettant d’extraire l’ensemble de lignes suivant.</span><span class="sxs-lookup"><span data-stu-id="b2af6-114">Applications that use **SQLFetchScroll** only for its block cursor capabilities, such as reports, are likely to pass through the result set a single time, using only the option to fetch the next rowset.</span></span> <span data-ttu-id="b2af6-115">En revanche, les applications basées sur l’écran peuvent tirer parti de toutes les fonctionnalités de **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="b2af6-115">Screen-based applications, on the other hand, can take advantage of all the capabilities of **SQLFetchScroll**.</span></span> <span data-ttu-id="b2af6-116">Si l’application définit la taille de l’ensemble de lignes sur le nombre de lignes affichées à l’écran et lie les mémoires tampons d’écran au jeu de résultats, elle peut traduire directement les opérations de barre de défilement en appels à **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="b2af6-116">If the application sets the rowset size to the number of rows displayed on the screen and binds the screen buffers to the result set, it can translate scroll bar operations directly to calls to **SQLFetchScroll**.</span></span>  
  
|<span data-ttu-id="b2af6-117">Opération de barre de défilement</span><span class="sxs-lookup"><span data-stu-id="b2af6-117">Scroll bar operation</span></span>|<span data-ttu-id="b2af6-118">Option de défilement SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="b2af6-118">SQLFetchScroll scrolling option</span></span>|  
|--------------------------|-------------------------------------|  
|<span data-ttu-id="b2af6-119">Page précédente</span><span class="sxs-lookup"><span data-stu-id="b2af6-119">Page up</span></span>|<span data-ttu-id="b2af6-120">SQL_FETCH_PRIOR</span><span class="sxs-lookup"><span data-stu-id="b2af6-120">SQL_FETCH_PRIOR</span></span>|  
|<span data-ttu-id="b2af6-121">Page suivante</span><span class="sxs-lookup"><span data-stu-id="b2af6-121">Page down</span></span>|<span data-ttu-id="b2af6-122">SQL_FETCH_NEXT</span><span class="sxs-lookup"><span data-stu-id="b2af6-122">SQL_FETCH_NEXT</span></span>|  
|<span data-ttu-id="b2af6-123">Ligne précédente</span><span class="sxs-lookup"><span data-stu-id="b2af6-123">Line up</span></span>|<span data-ttu-id="b2af6-124">SQL_FETCH_RELATIVE avec FetchOffset égal à-1</span><span class="sxs-lookup"><span data-stu-id="b2af6-124">SQL_FETCH_RELATIVE with FetchOffset equal to -1</span></span>|  
|<span data-ttu-id="b2af6-125">Ligne suivante</span><span class="sxs-lookup"><span data-stu-id="b2af6-125">Line down</span></span>|<span data-ttu-id="b2af6-126">SQL_FETCH_RELATIVE avec FetchOffset égal à 1</span><span class="sxs-lookup"><span data-stu-id="b2af6-126">SQL_FETCH_RELATIVE with FetchOffset equal to 1</span></span>|  
|<span data-ttu-id="b2af6-127">Case de défilement vers le haut</span><span class="sxs-lookup"><span data-stu-id="b2af6-127">Scroll box to top</span></span>|<span data-ttu-id="b2af6-128">SQL_FETCH_FIRST</span><span class="sxs-lookup"><span data-stu-id="b2af6-128">SQL_FETCH_FIRST</span></span>|  
|<span data-ttu-id="b2af6-129">Case de défilement vers le bas</span><span class="sxs-lookup"><span data-stu-id="b2af6-129">Scroll box to bottom</span></span>|<span data-ttu-id="b2af6-130">SQL_FETCH_LAST</span><span class="sxs-lookup"><span data-stu-id="b2af6-130">SQL_FETCH_LAST</span></span>|  
|<span data-ttu-id="b2af6-131">Position aléatoire de la case de défilement</span><span class="sxs-lookup"><span data-stu-id="b2af6-131">Random scroll box position</span></span>|<span data-ttu-id="b2af6-132">SQL_FETCH_ABSOLUTE</span><span class="sxs-lookup"><span data-stu-id="b2af6-132">SQL_FETCH_ABSOLUTE</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="b2af6-133">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b2af6-133">In This Section</span></span>  
  
-   [<span data-ttu-id="b2af6-134">Création de signets pour des lignes dans ODBC</span><span class="sxs-lookup"><span data-stu-id="b2af6-134">Bookmarking Rows in ODBC</span></span>](scrolling-and-fetching-rows-bookmarking-rows-in-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2af6-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2af6-135">See Also</span></span>  
 [<span data-ttu-id="b2af6-136">Utilisation de curseurs &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b2af6-136">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
