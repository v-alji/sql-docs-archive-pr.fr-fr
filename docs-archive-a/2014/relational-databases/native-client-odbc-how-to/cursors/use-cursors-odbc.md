---
title: Utiliser des curseurs (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], how to topics
ms.assetid: c502736f-bca0-45c3-ae25-d2ad52d296bf
author: rothja
ms.author: jroth
ms.openlocfilehash: e08156b03407c7a05d86278c11482a568d651f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599977"
---
# <a name="use-cursors-odbc"></a><span data-ttu-id="ac01c-102">Utiliser des curseurs (ODBC)</span><span class="sxs-lookup"><span data-stu-id="ac01c-102">Use Cursors (ODBC)</span></span>
    
### <a name="to-use-cursors"></a><span data-ttu-id="ac01c-103">Pour utiliser des curseurs</span><span class="sxs-lookup"><span data-stu-id="ac01c-103">To use cursors</span></span>  
  
1.  <span data-ttu-id="ac01c-104">Appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) pour définir les attributs de curseur souhaités :</span><span class="sxs-lookup"><span data-stu-id="ac01c-104">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the desired cursor attributes:</span></span>  
  
     <span data-ttu-id="ac01c-105">Définissez les attributs SQL_ATTR_CURSOR_TYPE et SQL_ATTR_CONCURRENCY (option par défaut).</span><span class="sxs-lookup"><span data-stu-id="ac01c-105">Set the SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY attributes (this is the preferred option).</span></span>  
  
     <span data-ttu-id="ac01c-106">ou</span><span class="sxs-lookup"><span data-stu-id="ac01c-106">Or</span></span>  
  
     <span data-ttu-id="ac01c-107">Définissez les attributs SQL_CURSOR_SCROLLABLE et SQL_CURSOR_SENSITIVITY.</span><span class="sxs-lookup"><span data-stu-id="ac01c-107">Set the SQL_CURSOR_SCROLLABLE and SQL_CURSOR_SENSITIVITY attributes.</span></span>  
  
2.  <span data-ttu-id="ac01c-108">Appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) pour définir la taille de l’ensemble de lignes en utilisant l’attribut SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="ac01c-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the rowset size by using the SQL_ATTR_ROW_ARRAY_SIZE attribute.</span></span>  
  
3.  <span data-ttu-id="ac01c-109">Vous pouvez également appeler [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) pour définir un nom de curseur si des mises à jour positionnées seront effectuées à l’aide de la clause WHERE CURRENT OF.</span><span class="sxs-lookup"><span data-stu-id="ac01c-109">Optionally, call [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) to set a cursor name if positioned updates will be done by using the WHERE CURRENT OF clause.</span></span>  
  
4.  <span data-ttu-id="ac01c-110">Exécutez l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="ac01c-110">Execute the SQL statement.</span></span>  
  
5.  <span data-ttu-id="ac01c-111">Vous pouvez également appeler [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) pour obtenir le nom de curseur si des mises à jour positionnées seront effectuées à l’aide de la clause WHERE CURRENT OF et si un nom de curseur n’a pas été fourni avec [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="ac01c-111">Optionally, call [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) to get the cursor name if positioned updates will be done by using the WHERE CURRENT OF clause and a cursor name was not supplied with [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) in Step 3.</span></span>  
  
6.  <span data-ttu-id="ac01c-112">Appelez [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) pour obtenir le nombre de colonnes (C) dans l’ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="ac01c-112">Call [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns (C) in the rowset.</span></span>  
  
     <span data-ttu-id="ac01c-113">Utilisez la liaison selon les colonnes</span><span class="sxs-lookup"><span data-stu-id="ac01c-113">Use column-wise binding.</span></span>  
  
     <span data-ttu-id="ac01c-114">\- ou -</span><span class="sxs-lookup"><span data-stu-id="ac01c-114">\- or -</span></span>  
  
     <span data-ttu-id="ac01c-115">Utilisez la liaison selon les lignes.</span><span class="sxs-lookup"><span data-stu-id="ac01c-115">Use row-wise binding.</span></span>  
  
7.  <span data-ttu-id="ac01c-116">Extrayez des ensembles de lignes à partir du curseur, comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="ac01c-116">Fetch rowsets from the cursor as desired.</span></span>  
  
8.  <span data-ttu-id="ac01c-117">Appelez [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) pour déterminer si un autre jeu de résultats est disponible.</span><span class="sxs-lookup"><span data-stu-id="ac01c-117">Call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="ac01c-118">S'il retourne SQL_SUCCESS, un autre jeu de résultats est disponible.</span><span class="sxs-lookup"><span data-stu-id="ac01c-118">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="ac01c-119">S'il retourne SQL_NO_DATA, aucun autre jeu de résultats n'est disponible.</span><span class="sxs-lookup"><span data-stu-id="ac01c-119">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="ac01c-120">S’il retourne SQL_SUCCESS_WITH_INFO ou SQL_ERROR, appelez [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) pour déterminer si la sortie à partir d’une instruction PRINT ou RAISERROR est disponible.</span><span class="sxs-lookup"><span data-stu-id="ac01c-120">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
     <span data-ttu-id="ac01c-121">Si des paramètres d'instruction liés sont utilisés pour les paramètres de sortie ou la valeur de retour d'une procédure stockée, utilisez les données à présent disponibles dans les mémoires tampons de paramètres liés.</span><span class="sxs-lookup"><span data-stu-id="ac01c-121">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span>  
  
     <span data-ttu-id="ac01c-122">Quand des paramètres liés sont utilisés, chaque appel à [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) ou à [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) aura exécuté l’instruction SQL S fois, où S est le nombre d’éléments présents dans le tableau de paramètres liés.</span><span class="sxs-lookup"><span data-stu-id="ac01c-122">When bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement S times, where S is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="ac01c-123">Cela signifie qu'il y aura S jeux de résultats à traiter, où chaque jeu de résultats comprend l'ensemble des jeux de résultats, des paramètres de sortie et des codes de retour habituellement retournés par une exécution unique de l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="ac01c-123">This means that there will be S sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
     <span data-ttu-id="ac01c-124">Notez que lorsqu'un jeu de résultats contient des lignes calculées, chaque ligne calculée est rendue disponible comme un jeu de résultats distinct.</span><span class="sxs-lookup"><span data-stu-id="ac01c-124">Note that when a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="ac01c-125">Ces jeux de résultats calculés sont intercalés au sein des lignes normales et séparent les lignes normales en plusieurs jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="ac01c-125">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
9. <span data-ttu-id="ac01c-126">Vous pouvez également appeler [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) avec SQL_UNBIND pour libérer tous les tampons de colonnes liées éventuels.</span><span class="sxs-lookup"><span data-stu-id="ac01c-126">Optionally, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
10. <span data-ttu-id="ac01c-127">Si un autre jeu de résultats est disponible, allez à l'étape 6.</span><span class="sxs-lookup"><span data-stu-id="ac01c-127">If another result set is available, go to Step 6.</span></span>  
  
     <span data-ttu-id="ac01c-128">À l’étape 9, l’appel de [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) sur un jeu de résultats partiellement traité efface le reste du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="ac01c-128">In Step 9, calling [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) on a partially processed result set clears the remainder of the result set.</span></span> <span data-ttu-id="ac01c-129">Une autre méthode pour effacer un jeu de résultats partiellement traité consiste à appeler [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="ac01c-129">Another way to clear a partially processed result set is to call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
     <span data-ttu-id="ac01c-130">Vous pouvez contrôler le type de curseur utilisé en définissant SQL_ATTR_CURSOR_TYPE et SQL_ATTR_CONCURRENCY ou en définissant SQL_ATTR_CURSOR_SENSITIVITY et SQL_ATTR_CURSOR_SCROLLABLE.</span><span class="sxs-lookup"><span data-stu-id="ac01c-130">You can control the type of cursor used by setting either SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="ac01c-131">Vous ne devez pas combiner les deux méthodes de spécification de comportement du curseur.</span><span class="sxs-lookup"><span data-stu-id="ac01c-131">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac01c-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac01c-132">See Also</span></span>  
 [<span data-ttu-id="ac01c-133">Rubriques de procédures relatives à l’utilisation des curseurs &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ac01c-133">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
