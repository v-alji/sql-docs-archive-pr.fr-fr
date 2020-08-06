---
title: Traiter les résultats (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- processing results [ODBC]
ms.assetid: 4810fe3f-78ee-4f0d-8bcc-a4659fbcf46f
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a22e9d7280f88de7799c31d2d0611e5299043d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706439"
---
# <a name="process-results-odbc"></a><span data-ttu-id="a0ef1-102">Traiter des résultats (ODBC)</span><span class="sxs-lookup"><span data-stu-id="a0ef1-102">Process Results (ODBC)</span></span>
    
### <a name="to-process-results"></a><span data-ttu-id="a0ef1-103">Pour traiter des résultats</span><span class="sxs-lookup"><span data-stu-id="a0ef1-103">To process results</span></span>  
  
1.  <span data-ttu-id="a0ef1-104">Récupérez les informations du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-104">Retrieve result set information.</span></span>  
  
2.  <span data-ttu-id="a0ef1-105">Si des colonnes dépendantes sont utilisées, pour chaque colonne à lier, appelez [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) pour lier une mémoire tampon de programme à la colonne.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-105">If bound columns are used, for each column you want to bind to, call [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) to bind a program buffer to the column.</span></span>  
  
3.  <span data-ttu-id="a0ef1-106">Pour chaque ligne de l'ensemble de résultats :</span><span class="sxs-lookup"><span data-stu-id="a0ef1-106">For each row in the result set:</span></span>  
  
    -   <span data-ttu-id="a0ef1-107">Appelez [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) pour obtenir la ligne suivante.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-107">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) to get the next row.</span></span>  
  
    -   <span data-ttu-id="a0ef1-108">Si les colonnes dépendantes sont utilisées, utilisez les données à présent disponibles dans les mémoires tampons des colonnes dépendantes.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-108">If bound columns are used, use the data now available in the bound column buffers.</span></span>  
  
    -   <span data-ttu-id="a0ef1-109">Si des colonnes indépendantes sont utilisées, appelez [SQLGetData](../native-client-odbc-api/sqlgetdata.md) une ou plusieurs fois pour obtenir les données pour les colonnes indépendantes après la dernière colonne dépendante.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-109">If unbound columns are used, call [SQLGetData](../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column.</span></span> <span data-ttu-id="a0ef1-110">Les appels à `SQLGetData` doivent être dans l’ordre de plus en plus élevé du numéro de colonne.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-110">Calls to `SQLGetData` should be in increasing order of column number.</span></span>  
  
    -   <span data-ttu-id="a0ef1-111">Appelez plusieurs fois `SQLGetData` pour obtenir des données à partir d'une colonne text ou image.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-111">Call `SQLGetData` multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="a0ef1-112">Quand [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) signale la fin du jeu de résultats en retournant SQL_NO_DATA, appelez [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) pour déterminer si un autre jeu de résultats est disponible.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-112">When [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) signals the end of the result set by returning SQL_NO_DATA, call [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="a0ef1-113">S'il retourne SQL_SUCCESS, un autre jeu de résultats est disponible.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-113">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="a0ef1-114">S'il retourne SQL_NO_DATA, aucun autre jeu de résultats n'est disponible.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-114">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="a0ef1-115">S’il retourne SQL_SUCCESS_WITH_INFO ou SQL_ERROR, appelez [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) pour déterminer si la sortie à partir d’une instruction PRINT ou RAISERROR est disponible.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-115">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
         <span data-ttu-id="a0ef1-116">Si des paramètres d'instruction liés sont utilisés pour les paramètres de sortie ou la valeur de retour d'une procédure stockée, utilisez les données à présent disponibles dans les mémoires tampons de paramètres liés.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-116">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span> <span data-ttu-id="a0ef1-117">Par ailleurs, quand des paramètres liés sont utilisés, chaque appel à [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) ou à [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) aura exécuté l’instruction SQL *S* fois, où *S* est le nombre d’éléments présents dans le tableau de paramètres liés.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-117">Also, when bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement *S* times, where *S* is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="a0ef1-118">Cela signifie qu’il y aura *S* jeux de résultats à traiter, où chaque jeu de résultats comprend tous les jeux de résultats, les paramètres de sortie et les codes de retour habituellement retournés par une exécution unique de l’instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-118">This means that there will be *S* sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0ef1-119">Lorsqu'un jeu de résultats contient des lignes calculées, chaque ligne calculée est rendue disponible comme un jeu de résultats distinct.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-119">When a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="a0ef1-120">Ces jeux de résultats calculés sont intercalés au sein des lignes normales et séparent les lignes normales en plusieurs jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-120">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
5.  <span data-ttu-id="a0ef1-121">Vous pouvez également appeler [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) avec SQL_UNBIND pour libérer tous les tampons de colonnes liées éventuels.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-121">Optionally, call [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
6.  <span data-ttu-id="a0ef1-122">Si un autre jeu de résultats est disponible, allez à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="a0ef1-122">If another result set is available, go to Step 1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0ef1-123">Pour annuler le traitement d’un jeu de résultats avant que [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) ne retourne SQL_NO_DATA, appelez [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="a0ef1-123">To cancel processing a result set before [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) returns SQL_NO_DATA, call [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ef1-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0ef1-124">See Also</span></span>  
 [<span data-ttu-id="a0ef1-125">Rubriques de procédures relatives au traitement des résultats &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a0ef1-125">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
  
