---
title: Exécuter directement une instruction (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
ms.assetid: b690f9de-66e1-4ee5-ab6a-121346fb5f85
author: rothja
ms.author: jroth
ms.openlocfilehash: 2aeada906a925cff93455ffd92e7c17822a80124
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599970"
---
# <a name="execute-a-statement-directly-odbc"></a><span data-ttu-id="c8176-102">Exécuter directement une instruction (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c8176-102">Execute a Statement Directly (ODBC)</span></span>
    
### <a name="to-execute-a-statement-directly-and-one-time-only"></a><span data-ttu-id="c8176-103">Pour exécuter une instruction directement et une seule fois</span><span class="sxs-lookup"><span data-stu-id="c8176-103">To execute a statement directly and one time only</span></span>  
  
1.  <span data-ttu-id="c8176-104">Si l'instruction contient des marqueurs de paramètres, utilisez [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) pour lier chaque paramètre à une variable de programme.</span><span class="sxs-lookup"><span data-stu-id="c8176-104">If the statement has parameter markers, use [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind each parameter to a program variable.</span></span> <span data-ttu-id="c8176-105">Remplissez les variables de programme de valeurs de données, puis configurez tous les paramètres de données en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c8176-105">Fill the program variables with data values, and then set up any data-at-execution parameters.</span></span>  
  
2.  <span data-ttu-id="c8176-106">Appelez [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) pour exécuter l'instruction.</span><span class="sxs-lookup"><span data-stu-id="c8176-106">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span>  
  
3.  <span data-ttu-id="c8176-107">Si vous utilisez des paramètres d'entrée de données en cours d'exécution, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) retourne SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="c8176-107">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="c8176-108">Envoyez les données par segments à l'aide de [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) et [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="c8176-108">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-column-wise-parameter-binding"></a><span data-ttu-id="c8176-109">Pour exécuter plusieurs fois une instruction au moyen d'une liaison de paramètre selon les colonnes</span><span class="sxs-lookup"><span data-stu-id="c8176-109">To execute a statement multiple times by using column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="c8176-110">Appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) pour définir les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="c8176-110">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="c8176-111">Définissez SQL_ATTR_PARAMSET_SIZE au nombre de jeux (S) de paramètres.</span><span class="sxs-lookup"><span data-stu-id="c8176-111">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="c8176-112">Définissez SQL_ATTR_PARAM_BIND_TYPE à SQL_PARAMETER_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="c8176-112">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
     <span data-ttu-id="c8176-113">Définissez l'attribut SQL_ATTR_PARAMS_PROCESSED_PTR de sorte qu'il pointe vers une variable SQLUINTEGER contenant le nombre de paramètres traités.</span><span class="sxs-lookup"><span data-stu-id="c8176-113">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="c8176-114">Définissez SQL_ATTR_PARAMS_STATUS_PTR de sorte qu'il pointe vers un tableau [S] de variables SQLUSSMALLINT contenant les indicateurs d'état de paramètre.</span><span class="sxs-lookup"><span data-stu-id="c8176-114">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="c8176-115">Pour chaque marqueur de paramètre :</span><span class="sxs-lookup"><span data-stu-id="c8176-115">For each parameter marker:</span></span>  
  
     <span data-ttu-id="c8176-116">Allouez un tableau de S mémoires tampons de paramètres pour stocker les valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="c8176-116">Allocate an array of S parameter buffers to store data values.</span></span>  
  
     <span data-ttu-id="c8176-117">Allouez un tableau de S mémoires tampons de paramètres pour stocker les longueurs de données.</span><span class="sxs-lookup"><span data-stu-id="c8176-117">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
     <span data-ttu-id="c8176-118">Appelez [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) pour lier les tableaux de valeur de données et de longueur de données de paramètre au paramètre d'instruction.</span><span class="sxs-lookup"><span data-stu-id="c8176-118">Call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
     <span data-ttu-id="c8176-119">Configurez toutes les paramètres d'image ou de texte de données en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c8176-119">Set up any data-at-execution text or image parameters.</span></span>  
  
     <span data-ttu-id="c8176-120">Mettez les valeurs de données S et les longueurs de données S dans les tableaux de paramètres liés.</span><span class="sxs-lookup"><span data-stu-id="c8176-120">Put S data values and S data lengths into the bound parameter arrays.</span></span>  
  
3.  <span data-ttu-id="c8176-121">Appelez [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) pour exécuter l'instruction.</span><span class="sxs-lookup"><span data-stu-id="c8176-121">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="c8176-122">Le pilote exécute efficacement l'instruction S fois, une fois pour chaque jeu de paramètres.</span><span class="sxs-lookup"><span data-stu-id="c8176-122">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
4.  <span data-ttu-id="c8176-123">Si vous utilisez des paramètres d'entrée de données en cours d'exécution, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) retourne SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="c8176-123">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="c8176-124">Envoyez les données par segments à l'aide de [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) et [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="c8176-124">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-row-wise-parameter-binding"></a><span data-ttu-id="c8176-125">Pour exécuter plusieurs fois une instruction au moyen d'une liaison de paramètre selon les lignes</span><span class="sxs-lookup"><span data-stu-id="c8176-125">To execute a statement multiple times by using row-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="c8176-126">Allouez un tableau [S] de structures, où S est le nombre de jeux de paramètres.</span><span class="sxs-lookup"><span data-stu-id="c8176-126">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="c8176-127">La structure dispose d'un élément pour chaque paramètre et chaque élément contient deux parties :</span><span class="sxs-lookup"><span data-stu-id="c8176-127">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
     <span data-ttu-id="c8176-128">La première partie est une variable du type de données approprié destinée à contenir les données de paramètres.</span><span class="sxs-lookup"><span data-stu-id="c8176-128">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
     <span data-ttu-id="c8176-129">La deuxième partie est une variable SQLINTEGER destinée à contenir l'indicateur d'état.</span><span class="sxs-lookup"><span data-stu-id="c8176-129">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="c8176-130">Appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) pour définir les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="c8176-130">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="c8176-131">Définissez SQL_ATTR_PARAMSET_SIZE au nombre de jeux (S) de paramètres.</span><span class="sxs-lookup"><span data-stu-id="c8176-131">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="c8176-132">Définissez SQL_ATTR_PARAM_BIND_TYPE à la taille de la structure allouée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="c8176-132">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
     <span data-ttu-id="c8176-133">Définissez l'attribut SQL_ATTR_PARAMS_PROCESSED_PTR de sorte qu'il pointe vers une variable SQLUINTEGER contenant le nombre de paramètres traités.</span><span class="sxs-lookup"><span data-stu-id="c8176-133">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="c8176-134">Définissez SQL_ATTR_PARAMS_STATUS_PTR de sorte qu'il pointe vers un tableau [S] de variables SQLUSSMALLINT contenant les indicateurs d'état de paramètre.</span><span class="sxs-lookup"><span data-stu-id="c8176-134">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="c8176-135">Pour chaque marqueur de paramètre, appelez [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) pour diriger les pointeurs de valeur de données et de longueur de données de paramètre vers leurs variables dans le premier élément du tableau de structures alloué à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="c8176-135">For each parameter marker, call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to point the parameter's data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="c8176-136">Si le paramètre est un paramètre de données en cours d'exécution, installez-le.</span><span class="sxs-lookup"><span data-stu-id="c8176-136">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
4.  <span data-ttu-id="c8176-137">Remplissez le tableau de tampons de paramètres liés avec les valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="c8176-137">Fill the bound parameter buffer array with data values.</span></span>  
  
5.  <span data-ttu-id="c8176-138">Appelez [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) pour exécuter l'instruction.</span><span class="sxs-lookup"><span data-stu-id="c8176-138">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="c8176-139">Le pilote exécute efficacement l'instruction S fois, une fois pour chaque jeu de paramètres.</span><span class="sxs-lookup"><span data-stu-id="c8176-139">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
6.  <span data-ttu-id="c8176-140">Si vous utilisez des paramètres d'entrée de données en cours d'exécution, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) retourne SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="c8176-140">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="c8176-141">Envoyez les données par segments à l'aide de [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) et [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="c8176-141">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
 <span data-ttu-id="c8176-142">**Remarque** En règle générale, la liaison selon les colonnes et les lignes est davantage employée avec les fonctions [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) et [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) qu'avec [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span><span class="sxs-lookup"><span data-stu-id="c8176-142">**Note** Column-wise and row-wise binding are more typically used in conjunction with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) and [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) than with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8176-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c8176-143">See Also</span></span>  
 [<span data-ttu-id="c8176-144">Rubriques de procédures relatives à l’exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c8176-144">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
