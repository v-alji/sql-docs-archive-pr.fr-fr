---
title: Préparer et exécuter une instruction (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
- statement preparation
ms.assetid: 0adecc63-4da5-486c-bc48-09a004a2fae6
author: rothja
ms.author: jroth
ms.openlocfilehash: 607d8ad1509eca1204f6d029842b04120d3f5d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707491"
---
# <a name="prepare-and-execute-a-statement-odbc"></a><span data-ttu-id="4e2e2-102">Préparer et exécuter une instruction (ODBC)</span><span class="sxs-lookup"><span data-stu-id="4e2e2-102">Prepare and Execute a Statement (ODBC)</span></span>
    
### <a name="to-prepare-a-statement-once-and-then-execute-it-multiple-times"></a><span data-ttu-id="4e2e2-103">Pour préparer une instruction une fois, puis l'exécuter plusieurs fois</span><span class="sxs-lookup"><span data-stu-id="4e2e2-103">To prepare a statement once, and then execute it multiple times</span></span>  
  
1.  <span data-ttu-id="4e2e2-104">Appelez la fonction [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) pour préparer l'instruction.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-104">Call [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) to prepare the statement.</span></span>  
  
2.  <span data-ttu-id="4e2e2-105">Éventuellement, appelez [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) pour déterminer le nombre de paramètres dans l'instruction préparée.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-105">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
3.  <span data-ttu-id="4e2e2-106">Éventuellement, pour chaque paramètre dans l'instruction préparée :</span><span class="sxs-lookup"><span data-stu-id="4e2e2-106">Optionally, for each parameter in the prepared statement:</span></span>  
  
    -   <span data-ttu-id="4e2e2-107">Appelez [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) pour obtenir des informations sur les paramètres.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-107">Call [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to get parameter information.</span></span>  
  
    -   <span data-ttu-id="4e2e2-108">Liez chaque paramètre à une variable de programme à l'aide de [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="4e2e2-108">Bind each parameter to a program variable by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="4e2e2-109">Configurez tous les paramètres de données en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-109">Set up any data-at-execution parameters.</span></span>  
  
4.  <span data-ttu-id="4e2e2-110">Pour chaque exécution d'une instruction préparée :</span><span class="sxs-lookup"><span data-stu-id="4e2e2-110">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="4e2e2-111">Si l'instruction a des marqueurs de paramètres, mettez les valeurs de données dans la mémoire tampon de paramètre lié.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-111">If the statement has parameter markers, put the data values into the bound parameter buffer.</span></span>  
  
    -   <span data-ttu-id="4e2e2-112">Appelez [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) pour exécuter l'instruction préparée.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-112">Call [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="4e2e2-113">Si des paramètres d'entrée de données en cours d'exécution sont utilisés, [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) retourne SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-113">If data-at-execution input parameters are used, [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="4e2e2-114">Envoyez les données par segments à l'aide de [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) et [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="4e2e2-114">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-prepare-a-statement-with-column-wise-parameter-binding"></a><span data-ttu-id="4e2e2-115">Pour préparer une instruction avec la liaison de paramètre selon les colonnes</span><span class="sxs-lookup"><span data-stu-id="4e2e2-115">To prepare a statement with column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="4e2e2-116">Appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) pour définir les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="4e2e2-116">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="4e2e2-117">Définissez SQL_ATTR_PARAMSET_SIZE au nombre de jeux (S) de paramètres.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-117">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="4e2e2-118">Définissez SQL_ATTR_PARAM_BIND_TYPE à SQL_PARAMETER_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-118">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="4e2e2-119">Définissez l'attribut SQL_ATTR_PARAMS_PROCESSED_PTR de sorte qu'il pointe vers une variable SQLUINTEGER contenant le nombre de paramètres traités.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-119">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="4e2e2-120">Définissez SQL_ATTR_PARAMS_STATUS_PTR de sorte qu'il pointe vers un tableau [S] de variables SQLUSSMALLINT contenant les indicateurs d'état de paramètre.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-120">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="4e2e2-121">Appelez SQLPrepare pour préparer l’instruction.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-121">Call SQLPrepare to prepare the statement.</span></span>  
  
3.  <span data-ttu-id="4e2e2-122">Éventuellement, appelez [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) pour déterminer le nombre de paramètres dans l'instruction préparée.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-122">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
4.  <span data-ttu-id="4e2e2-123">Si vous le souhaitez, pour chaque paramètre de l’instruction préparée, appelez SQLDescribeParam pour obtenir des informations sur les paramètres.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-123">Optionally, for each parameter in the prepared statement, call SQLDescribeParam to get parameter information.</span></span>  
  
5.  <span data-ttu-id="4e2e2-124">Pour chaque marqueur de paramètre :</span><span class="sxs-lookup"><span data-stu-id="4e2e2-124">For each parameter marker:</span></span>  
  
    -   <span data-ttu-id="4e2e2-125">Allouez un tableau de S mémoires tampons de paramètres pour stocker les valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-125">Allocate an array of S parameter buffers to store data values.</span></span>  
  
    -   <span data-ttu-id="4e2e2-126">Allouez un tableau de S mémoires tampons de paramètres pour stocker les longueurs de données.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-126">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="4e2e2-127">Appelez SQLBindParameter pour lier les tableaux de valeur de données et de longueur de données de paramètre au paramètre d'instruction.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-127">Call SQLBindParameter to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
    -   <span data-ttu-id="4e2e2-128">Si le paramètre est un paramètre d'image ou de texte de données en cours d'exécution, installez-le.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-128">If the parameter is a data-at-execution text or image parameter, set it up.</span></span>  
  
    -   <span data-ttu-id="4e2e2-129">Si des paramètres de données en cours d'exécution sont utilisés, installez-les.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-129">If any data-at-execution parameters are used, set them up.</span></span>  
  
6.  <span data-ttu-id="4e2e2-130">Pour chaque exécution d'une instruction préparée :</span><span class="sxs-lookup"><span data-stu-id="4e2e2-130">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="4e2e2-131">Mettez les valeurs de données S et les longueurs de données S dans les tableaux de paramètres liés.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-131">Put the S data values and S data lengths into the bound parameter arrays.</span></span>  
  
    -   <span data-ttu-id="4e2e2-132">Appelez SQLExecute pour exécuter l'instruction préparée.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-132">Call SQLExecute to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="4e2e2-133">Si des paramètres d'entrée de données en cours d'exécution sont utilisés, SQLExecute retourne SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-133">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="4e2e2-134">Envoyez les données par segments à l'aide de SQLParamData et SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-134">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
### <a name="to-prepare-a-statement-with-row-wise-bound-parameters"></a><span data-ttu-id="4e2e2-135">Pour préparer une instruction avec des paramètres liés selon les lignes</span><span class="sxs-lookup"><span data-stu-id="4e2e2-135">To prepare a statement with row-wise bound parameters</span></span>  
  
1.  <span data-ttu-id="4e2e2-136">Allouez un tableau [S] de structures, où S est le nombre de jeux de paramètres.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-136">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="4e2e2-137">La structure dispose d'un élément pour chaque paramètre et chaque élément contient deux parties :</span><span class="sxs-lookup"><span data-stu-id="4e2e2-137">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="4e2e2-138">La première partie est une variable du type de données approprié destinée à contenir les données de paramètres.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-138">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
    -   <span data-ttu-id="4e2e2-139">La deuxième partie est une variable SQLINTEGER destinée à contenir l'indicateur d'état.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-139">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="4e2e2-140">Appelez [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) pour définir les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="4e2e2-140">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="4e2e2-141">Définissez SQL_ATTR_PARAMSET_SIZE au nombre de jeux (S) de paramètres.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-141">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="4e2e2-142">Définissez SQL_ATTR_PARAM_BIND_TYPE à la taille de la structure allouée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-142">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="4e2e2-143">Définissez l'attribut SQL_ATTR_PARAMS_PROCESSED_PTR de sorte qu'il pointe vers une variable SQLUINTEGER contenant le nombre de paramètres traités.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-143">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="4e2e2-144">Définissez SQL_ATTR_PARAMS_STATUS_PTR de sorte qu'il pointe vers un tableau [S] de variables SQLUSSMALLINT contenant les indicateurs d'état de paramètre.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-144">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="4e2e2-145">Appelez SQLPrepare pour préparer l’instruction.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-145">Call SQLPrepare to prepare the statement.</span></span>  
  
4.  <span data-ttu-id="4e2e2-146">Pour chaque marqueur de paramètre, appelez SQLBindParameter pour pointer la valeur des données de paramètre et le pointeur de longueur des données vers leurs variables dans le premier élément du tableau de structures alloué à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-146">For each parameter marker, call SQLBindParameter to point the parameter data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="4e2e2-147">Si le paramètre est un paramètre de données en cours d'exécution, installez-le.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-147">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
5.  <span data-ttu-id="4e2e2-148">Pour chaque exécution d'une instruction préparée :</span><span class="sxs-lookup"><span data-stu-id="4e2e2-148">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="4e2e2-149">Remplissez le tableau de tampons de paramètres liés avec les valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-149">Fill the bound parameter buffer array with data values.</span></span>  
  
    -   <span data-ttu-id="4e2e2-150">Appelez SQLExecute pour exécuter l'instruction préparée.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-150">Call SQLExecute to execute the prepared statement.</span></span> <span data-ttu-id="4e2e2-151">Le pilote exécute efficacement l'instruction SQL S fois, une fois pour chaque jeu de paramètres.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-151">The driver efficiently executes the SQL statement S times, once for each set of parameters.</span></span>  
  
    -   <span data-ttu-id="4e2e2-152">Si des paramètres d'entrée de données en cours d'exécution sont utilisés, SQLExecute retourne SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-152">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="4e2e2-153">Envoyez les données par segments à l'aide de SQLParamData et SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="4e2e2-153">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2e2-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e2e2-154">See Also</span></span>  
 [<span data-ttu-id="4e2e2-155">Rubriques de procédures relatives à l’exécution de requêtes &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4e2e2-155">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
