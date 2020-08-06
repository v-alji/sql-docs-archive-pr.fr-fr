---
title: Utilisation d’une instruction (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC]
ms.assetid: f7573f8f-6f21-4e03-8dd5-a5f2ea4878cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ff3bc8c545cc9b55f0da3bb31d68d1ecbb5b547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707492"
---
# <a name="use-a-statement-odbc"></a><span data-ttu-id="027e8-102">Utiliser une instruction (ODBC)</span><span class="sxs-lookup"><span data-stu-id="027e8-102">Use a Statement (ODBC)</span></span>
    
### <a name="to-use-a-statement"></a><span data-ttu-id="027e8-103">Pour utiliser une instruction</span><span class="sxs-lookup"><span data-stu-id="027e8-103">To use a statement</span></span>  
  
1.  <span data-ttu-id="027e8-104">Appelez [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) avec SQL_HANDLE_STMT comme *HandleType* de manière à allouer un descripteur d’instruction.</span><span class="sxs-lookup"><span data-stu-id="027e8-104">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a *HandleType* of SQL_HANDLE_STMT to allocate a statement handle.</span></span>  
  
2.  <span data-ttu-id="027e8-105">Si vous le souhaitez, appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) pour définir des options d’instruction ou [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) pour obtenir des attributs d’instruction.</span><span class="sxs-lookup"><span data-stu-id="027e8-105">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set statement options or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get statement attributes.</span></span>  
  
     <span data-ttu-id="027e8-106">Pour utiliser des curseurs côté serveur, vous devez affecter aux attributs de curseur des valeurs autres que leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="027e8-106">To use server cursors, you must set cursor attributes to values other than their defaults.</span></span>  
  
3.  <span data-ttu-id="027e8-107">Si vous le souhaitez et si l'instruction doit être exécutée plusieurs fois, préparez son exécution avec la fonction [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360).</span><span class="sxs-lookup"><span data-stu-id="027e8-107">Optionally, if the statement will be executed several times, prepare the statement for execution with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span>  
  
4.  <span data-ttu-id="027e8-108">Si vous le souhaitez et si l'instruction a des marqueurs de paramètres liés, liez ces marqueurs de paramètres à des variables de programme à l'aide de [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="027e8-108">Optionally, if the statement has bound parameter markers, bind the parameter markers to program variables by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="027e8-109">Si l'instruction a été préparée, vous pouvez appeler [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) et [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number et characteristics of the parameters.</span><span class="sxs-lookup"><span data-stu-id="027e8-109">If the statement was prepared, you can call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) and [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number and characteristics of the parameters.</span></span>  
  
5.  <span data-ttu-id="027e8-110">Exécutez une instruction directement en utilisant SQLExecDirect.</span><span class="sxs-lookup"><span data-stu-id="027e8-110">Execute a statement directly by using SQLExecDirect.</span></span>  
  
     <span data-ttu-id="027e8-111">\- ou -</span><span class="sxs-lookup"><span data-stu-id="027e8-111">\- or -</span></span>  
  
     <span data-ttu-id="027e8-112">Si l'instruction a été préparée, exécutez-la plusieurs fois à l'aide de [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span><span class="sxs-lookup"><span data-stu-id="027e8-112">If the statement was prepared, execute it multiple times by using [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span></span>  
  
     <span data-ttu-id="027e8-113">\- ou -</span><span class="sxs-lookup"><span data-stu-id="027e8-113">\- or -</span></span>  
  
     <span data-ttu-id="027e8-114">Appelez une fonction de catalogue qui retourne des résultats.</span><span class="sxs-lookup"><span data-stu-id="027e8-114">Call a catalog function, which returns results.</span></span>  
  
6.  <span data-ttu-id="027e8-115">Traitez les résultats en liant les colonnes du jeu de résultats aux variables de programme, en déplaçant des données des colonnes de jeu de résultats vers des variables de programme à l'aide de [SQLGetData](../../native-client-odbc-api/sqlgetdata.md), ou une combinaison des deux méthodes.</span><span class="sxs-lookup"><span data-stu-id="027e8-115">Process the results by binding the result set columns to program variables, by moving data from the result set columns to program variables by using [SQLGetData](../../native-client-odbc-api/sqlgetdata.md), or a combination of the two methods.</span></span>  
  
     <span data-ttu-id="027e8-116">Extrayez une ligne à la fois dans le jeu de résultats d'une instruction.</span><span class="sxs-lookup"><span data-stu-id="027e8-116">Fetch through the result set of a statement one row at a time.</span></span>  
  
     <span data-ttu-id="027e8-117">\- ou -</span><span class="sxs-lookup"><span data-stu-id="027e8-117">\- or -</span></span>  
  
     <span data-ttu-id="027e8-118">Extrayez plusieurs lignes à la fois dans le jeu de résultats en utilisant un curseur de bloc.</span><span class="sxs-lookup"><span data-stu-id="027e8-118">Fetch through the result set several rows at a time by using a block cursor.</span></span>  
  
     <span data-ttu-id="027e8-119">\- ou -</span><span class="sxs-lookup"><span data-stu-id="027e8-119">\- or -</span></span>  
  
     <span data-ttu-id="027e8-120">Appelez [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) pour déterminer le nombre de lignes affectées par une instruction INSERT, UPDATE ou DELETE.</span><span class="sxs-lookup"><span data-stu-id="027e8-120">Call [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) to determine the number of rows affected by an INSERT, UPDATE, or DELETE statement.</span></span>  
  
     <span data-ttu-id="027e8-121">Si l'instruction SQL peut avoir plusieurs jeux de résultats, appelez [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) à la fin de chaque jeu de résultats pour savoir si des jeux de résultats supplémentaires doivent être traités.</span><span class="sxs-lookup"><span data-stu-id="027e8-121">If the SQL statement can have multiple result sets, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) at the end of each result set to see if there are additional result sets to process.</span></span>  
  
7.  <span data-ttu-id="027e8-122">Une fois les résultats traités, les actions suivantes peuvent être nécessaires pour rendre le descripteur d'instruction disponible pour exécuter une nouvelle instruction :</span><span class="sxs-lookup"><span data-stu-id="027e8-122">After results are processed, the following actions may be necessary to make the statement handle available to execute a new statement:</span></span>  
  
    -   <span data-ttu-id="027e8-123">Si vous n'avez pas appelé [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) jusqu'à ce qu'il ait retourné SQL_NO_DATA, appelez [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) pour fermer le curseur.</span><span class="sxs-lookup"><span data-stu-id="027e8-123">If you did not call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) until it returned SQL_NO_DATA, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) to close the cursor.</span></span>  
  
    -   <span data-ttu-id="027e8-124">Si vous avez lié des marqueurs de paramètres à des variables de programme, appelez [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) avec *Option* ayant la valeur SQL_RESET_PARAMS pour libérer les paramètres liés.</span><span class="sxs-lookup"><span data-stu-id="027e8-124">If you bound parameter markers to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_RESET_PARAMS to free the bound parameters.</span></span>  
  
    -   <span data-ttu-id="027e8-125">Si vous avez lié des colonnes de jeu de résultats à des variables de programme, appelez [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) avec *Option* ayant la valeur SQL_UNBIND pour libérer les colonnes liées.</span><span class="sxs-lookup"><span data-stu-id="027e8-125">If you bound result set columns to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_UNBIND to free the bound columns.</span></span>  
  
    -   <span data-ttu-id="027e8-126">Pour réutiliser le descripteur d'instruction, allez à l'Étape 2.</span><span class="sxs-lookup"><span data-stu-id="027e8-126">To reuse the statement handle, go to Step 2.</span></span>  
  
8.  <span data-ttu-id="027e8-127">Appelez [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) avec SQL_HANDLE_STMT comme *HandleType* pour libérer le descripteur d’instruction.</span><span class="sxs-lookup"><span data-stu-id="027e8-127">Call [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) with a *HandleType* of SQL_HANDLE_STMT to free the statement handle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="027e8-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="027e8-128">See Also</span></span>  
 [<span data-ttu-id="027e8-129">Rubriques de procédures relatives à l’exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="027e8-129">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
