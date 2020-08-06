---
title: Traitement des instructions qui génèrent des messages | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- PRINT statement
- messages [ODBC], statements generating messages
- statements [ODBC], message generation
- errors [ODBC], statements generating messages
- SQL Server Native Client ODBC driver, errors
- STATISTICS IO option
- STATISTICS TIME option
- DBCC statements
- SQLExecute function
- RAISERROR statement
- SQLGetDiagRec function
- ODBC error handling, statements generating messages
- SQLExecDirect function
ms.assetid: 672ebdc5-7fa1-4ceb-8d52-fd25ef646654
author: rothja
ms.author: jroth
ms.openlocfilehash: c26376eabb756d356dd71fb3bd8284a6b11dced7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698177"
---
# <a name="processing-statements-that-generate-messages"></a><span data-ttu-id="a1cef-102">Traitement des instructions qui génèrent des messages</span><span class="sxs-lookup"><span data-stu-id="a1cef-102">Processing Statements That Generate Messages</span></span>
  <span data-ttu-id="a1cef-103">Les options STATISTICS TIME et STATISTICS IO de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] SET sont utilisées pour obtenir des informations qui aident au diagnostic des requêtes longues.</span><span class="sxs-lookup"><span data-stu-id="a1cef-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement options STATISTICS TIME and STATISTICS IO are used to get information that aids in diagnosing long-running queries.</span></span> <span data-ttu-id="a1cef-104">Les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prennent aussi en charge l'option SHOWPLAN pour analyser les plans de requête.</span><span class="sxs-lookup"><span data-stu-id="a1cef-104">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] also support the SHOWPLAN option for analyzing query plans.</span></span> <span data-ttu-id="a1cef-105">Une application ODBC peut définir ces options en exécutant les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1cef-105">An ODBC application can set these options by executing the following statements:</span></span>  
  
```  
SQLExecDirect(hstmt, "SET SHOWPLAN ON", SQL_NTS);  
SQLExecDirect(hstmt, "SET STATISTICS TIME ON", SQL_NTS90  
);  
SQLExecDirect(hstmt, "SET STATISTICS IO ON", SQL_NTS);  
```  
  
 <span data-ttu-id="a1cef-106">Lorsque SET STATISTICs TIME ou SET SHOWPLAN sont ACTIVÉs, **SQLExecute** et **SQLExecDirect** retournent SQL_SUCCESS_WITH_INFO et, à ce stade, l’application peut récupérer la sortie Showplan ou Statistics Time en appelant **SQLGetDiagRec** jusqu’à ce qu’elle retourne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="a1cef-106">When SET STATISTICS TIME or SET SHOWPLAN are ON, **SQLExecute** and **SQLExecDirect** return SQL_SUCCESS_WITH_INFO, and, at that point, the application can retrieve the SHOWPLAN or STATISTICS TIME output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="a1cef-107">Chaque ligne des données SHOWPLAN est retournée au format suivant :</span><span class="sxs-lookup"><span data-stu-id="a1cef-107">Each line of SHOWPLAN data comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError=6223,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]   
              Table Scan"  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a1cef-108">version 7.0 a remplacé l'option SHOWPLAN par SHOWPLAN_ALL et SHOWPLAN_TEXT, qui retournent l'une et l'autre la sortie comme jeu de résultats, et non comme ensemble de messages.</span><span class="sxs-lookup"><span data-stu-id="a1cef-108">version 7.0 replaced the SHOWPLAN option with SHOWPLAN_ALL and SHOWPLAN_TEXT, both of which return output as a result set, not a set of messages.</span></span>  
  
 <span data-ttu-id="a1cef-109">Chaque ligne de STATISTICS TIME est retournée au format suivant :</span><span class="sxs-lookup"><span data-stu-id="a1cef-109">Each line of STATISTICS TIME comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3613,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
   SQL Server Parse and Compile Time: cpu time = 0 ms."  
```  
  
 <span data-ttu-id="a1cef-110">La sortie de SET STATISTICS IO n'est pas disponible jusqu'à la fin d'un jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="a1cef-110">The output of SET STATISTICS IO is not available until the end of a result set.</span></span> <span data-ttu-id="a1cef-111">Pour accéder à la sortie des statistiques d’e/s, l’application appelle **SQLGetDiagRec** au moment où **SQLFetch** ou [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) retourne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="a1cef-111">To get STATISTICS IO output, the application calls **SQLGetDiagRec** at the time **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) returns SQL_NO_DATA.</span></span> <span data-ttu-id="a1cef-112">La sortie de STATISTICS IO est retournée au format suivant :</span><span class="sxs-lookup"><span data-stu-id="a1cef-112">The output of STATISTICS IO comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3615,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table: testshow  scan count 1,  logical reads: 1,  
   physical reads: 0."  
```  
  
## <a name="using-dbcc-statements"></a><span data-ttu-id="a1cef-113">Utilisation des instructions DBCC</span><span class="sxs-lookup"><span data-stu-id="a1cef-113">Using DBCC Statements</span></span>  
 <span data-ttu-id="a1cef-114">Les instructions DBCC retournent leurs données comme messages, non comme jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="a1cef-114">DBCC statements return their data as messages, not result sets.</span></span> <span data-ttu-id="a1cef-115">**SQLExecDirect** ou **SQLExecute** retournent SQL_SUCCESS_WITH_INFO, et l’application récupère la sortie en appelant **SQLGetDiagRec** jusqu’à ce qu’elle retourne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="a1cef-115">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and the application retrieves the output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="a1cef-116">Par exemple, l'instruction suivante retourne SQL_SUCCESS_WITH_INFO :</span><span class="sxs-lookup"><span data-stu-id="a1cef-116">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect(hstmt, "DBCC CHECKTABLE(Authors)", SQL_NTS);  
```  
  
 <span data-ttu-id="a1cef-117">Les appels à **SQLGetDiagRec** retournent :</span><span class="sxs-lookup"><span data-stu-id="a1cef-117">Calls to **SQLGetDiagRec** return:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 2536,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Checking authors"  
szSqlState = "01000", *pfNativeError = 2579,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   The total number of data pages in this table is 1."  
szSqlState = "01000", *pfNativeError = 7929,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table has 23 data rows."  
szSqlState = "01000", *pfNativeError = 2528  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   DBCC execution completed. If DBCC printed error messages,  
   see your System Administrator."  
```  
  
## <a name="using-print-and-raiserror-statements"></a><span data-ttu-id="a1cef-118">Utilisation des instructions PRINT et RAISERROR</span><span class="sxs-lookup"><span data-stu-id="a1cef-118">Using PRINT and RAISERROR Statements</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="a1cef-119">Les instructions PRINT et RAISERROR renvoient également des données en appelant **SQLGetDiagRec**.</span><span class="sxs-lookup"><span data-stu-id="a1cef-119">PRINT and RAISERROR statements also return data by calling **SQLGetDiagRec**.</span></span> <span data-ttu-id="a1cef-120">Les instructions PRINT forcent l’exécution de l’instruction SQL à retourner SQL_SUCCESS_WITH_INFO, et un appel ultérieur à **SQLGetDiagRec** retourne une valeur *SQLSTATE* de 01000.</span><span class="sxs-lookup"><span data-stu-id="a1cef-120">PRINT statements cause the SQL statement execution to return SQL_SUCCESS_WITH_INFO, and a subsequent call to **SQLGetDiagRec** returns a *SQLState* of 01000.</span></span> <span data-ttu-id="a1cef-121">Une erreur RAISERROR avec une gravité égale ou inférieure à dix se comporte de la même façon que PRINT.</span><span class="sxs-lookup"><span data-stu-id="a1cef-121">A RAISERROR with a severity of ten or lower behaves the same as PRINT.</span></span> <span data-ttu-id="a1cef-122">Une instruction RAISERROR dont le niveau de gravité est supérieur ou égal à 11 provoque le retour de l’instruction EXECUTE SQL_ERROR et un appel ultérieur à **SQLGetDiagRec** retourne *SQLSTATE* 42000.</span><span class="sxs-lookup"><span data-stu-id="a1cef-122">A RAISERROR with a severity of 11 or higher causes the execute to return SQL_ERROR, and a subsequent call to **SQLGetDiagRec** returns *SQLState* 42000.</span></span> <span data-ttu-id="a1cef-123">Par exemple, l'instruction suivante retourne SQL_SUCCESS_WITH_INFO :</span><span class="sxs-lookup"><span data-stu-id="a1cef-123">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "PRINT  'Some message' ", SQL_NTS);  
```  
  
 <span data-ttu-id="a1cef-124">L’appel de **SQLGetDiagRec** retourne :</span><span class="sxs-lookup"><span data-stu-id="a1cef-124">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 0,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Some message"  
```  
  
 <span data-ttu-id="a1cef-125">L'instruction suivante retourne SQL_SUCCESS_WITH_INFO :</span><span class="sxs-lookup"><span data-stu-id="a1cef-125">The following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 1.', 10, -1)",  
   SQL_NTS)  
```  
  
 <span data-ttu-id="a1cef-126">L’appel de **SQLGetDiagRec** retourne :</span><span class="sxs-lookup"><span data-stu-id="a1cef-126">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 1."  
```  
  
 <span data-ttu-id="a1cef-127">L'instruction suivante retourne SQL_ERROR :</span><span class="sxs-lookup"><span data-stu-id="a1cef-127">The following statement returns SQL_ERROR:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 2.', 11, -1)", SQL_NTS)  
```  
  
 <span data-ttu-id="a1cef-128">L’appel de **SQLGetDiagRec** retourne :</span><span class="sxs-lookup"><span data-stu-id="a1cef-128">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "42000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 2."  
```  
  
 <span data-ttu-id="a1cef-129">Le minutage de l’appel de **SQLGetDiagRec** est essentiel lorsque la sortie des instructions Print ou RAISERROR est incluse dans un jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="a1cef-129">The timing of calling **SQLGetDiagRec** is critical when output from PRINT or RAISERROR statements is included in a result set.</span></span> <span data-ttu-id="a1cef-130">L’appel de **SQLGetDiagRec** pour récupérer la sortie Print ou RAISERROR doit être effectué immédiatement après l’instruction qui reçoit SQL_ERROR ou SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="a1cef-130">The call to **SQLGetDiagRec** to retrieve the PRINT or RAISERROR output must be made immediately after the statement that receives SQL_ERROR or SQL_SUCCESS_WITH_INFO.</span></span> <span data-ttu-id="a1cef-131">Cela est simple lorsqu'une seule instruction SQL est exécutée, comme dans les exemples ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a1cef-131">This is straightforward when only a single SQL statement is executed, as in the examples above.</span></span> <span data-ttu-id="a1cef-132">Dans ce cas, l’appel à **SQLExecDirect** ou **SQLExecute** retourne SQL_ERROR ou SQL_SUCCESS_WITH_INFO et **SQLGetDiagRec** peut ensuite être appelé.</span><span class="sxs-lookup"><span data-stu-id="a1cef-132">In these cases, the call to **SQLExecDirect** or **SQLExecute** returns SQL_ERROR or SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** can then be called.</span></span> <span data-ttu-id="a1cef-133">La situation est moins simple lors du codage de boucles pour gérer la sortie d'un lot d'instructions SQL ou lors de l'exécution de procédures stockées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1cef-133">It is less straightforward when coding loops to handle the output of a batch of SQL statements or when executing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span>  
  
 <span data-ttu-id="a1cef-134">Dans ce cas, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retourne un jeu de résultats pour chaque instruction SELECT exécutée dans un lot ou une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="a1cef-134">In this case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns a result set for every SELECT statement executed in a batch or stored procedure.</span></span> <span data-ttu-id="a1cef-135">Si le lot ou la procédure contient les instructions PRINT ou RAISERROR, leur sortie est entrelacée avec les jeux de résultats des instructions SELECT.</span><span class="sxs-lookup"><span data-stu-id="a1cef-135">If the batch or procedure contains PRINT or RAISERROR statements, the output for these is interleaved with the SELECT statement result sets.</span></span> <span data-ttu-id="a1cef-136">Si la première instruction du traitement ou de la procédure est PRINT ou RAISERROR, **SQLExecute** ou **SQLExecDirect** retourne SQL_SUCCESS_WITH_INFO ou SQL_ERROR, et l’application doit appeler **SQLGetDiagRec** jusqu’à ce qu’elle retourne SQL_NO_DATA pour récupérer les informations Print ou RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="a1cef-136">If the first statement in the batch or procedure is a PRINT or RAISERROR, the **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, and the application needs to call **SQLGetDiagRec** until it returns SQL_NO_DATA to retrieve the PRINT or RAISERROR information.</span></span>  
  
 <span data-ttu-id="a1cef-137">Si l’instruction PRINT ou RAISERROR vient après une instruction SQL (telle qu’une instruction SELECT), les informations PRINT ou RAISERROR sont retournées lorsque [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)positionne sur le jeu de résultats contenant l’erreur.</span><span class="sxs-lookup"><span data-stu-id="a1cef-137">If the PRINT or RAISERROR statement comes after an SQL statement (such as a SELECT statement), then the PRINT or RAISERROR information is returned when [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)positions on the result set containing the error.</span></span> <span data-ttu-id="a1cef-138">**SQLMoreResults** retourne SQL_SUCCESS_WITH_INFO ou SQL_ERROR selon la gravité du message.</span><span class="sxs-lookup"><span data-stu-id="a1cef-138">**SQLMoreResults** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR depending on the severity of the message.</span></span> <span data-ttu-id="a1cef-139">Les messages sont récupérés en appelant **SQLGetDiagRec** jusqu’à ce qu’il retourne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="a1cef-139">Messages are retrieved by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1cef-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1cef-140">See Also</span></span>  
 [<span data-ttu-id="a1cef-141">Gestion des erreurs et des messages</span><span class="sxs-lookup"><span data-stu-id="a1cef-141">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
