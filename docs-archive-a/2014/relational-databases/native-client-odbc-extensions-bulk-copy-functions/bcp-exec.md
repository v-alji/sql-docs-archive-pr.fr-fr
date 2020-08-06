---
title: bcp_exec | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_exec
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_exec function
ms.assetid: b23ea2cc-8545-4873-b0c1-57e76b0a3a7b
author: rothja
ms.author: jroth
ms.openlocfilehash: f925c6cb1e3a36f79ba4f560a06c5b6d499ece4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599980"
---
# <a name="bcp_exec"></a><span data-ttu-id="46437-102">bcp_exec</span><span class="sxs-lookup"><span data-stu-id="46437-102">bcp_exec</span></span>
  <span data-ttu-id="46437-103">Exécute une copie en bloc complète des données entre une table de base de données et un fichier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="46437-103">Executes a complete bulk copy of data between a database table and a user file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46437-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="46437-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_exec (  
HDBC   
hdbc  
,  
LPDBINT   
pnRowsProcessed  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="46437-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="46437-105">Arguments</span></span>  
 <span data-ttu-id="46437-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="46437-106">*hdbc*</span></span>  
 <span data-ttu-id="46437-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="46437-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="46437-108">*pnRowsProcessed*</span><span class="sxs-lookup"><span data-stu-id="46437-108">*pnRowsProcessed*</span></span>  
 <span data-ttu-id="46437-109">Pointeur vers un DBINT.</span><span class="sxs-lookup"><span data-stu-id="46437-109">Is a pointer to a DBINT.</span></span> <span data-ttu-id="46437-110">La fonction **bcp_exec** remplit ce DBINT avec le nombre de lignes copiées avec succès.</span><span class="sxs-lookup"><span data-stu-id="46437-110">The **bcp_exec** function fills this DBINT with the number of rows successfully copied.</span></span> <span data-ttu-id="46437-111">Si *pnRowsProcessed* a la valeur NULL, la fonction **bcp_exec**l'ignore.</span><span class="sxs-lookup"><span data-stu-id="46437-111">If *pnRowsProcessed* is NULL, it is ignored by **bcp_exec**.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="46437-112">Retours</span><span class="sxs-lookup"><span data-stu-id="46437-112">Returns</span></span>  
 <span data-ttu-id="46437-113">SUCCEED, SUCCEED_ASYNC ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="46437-113">SUCCEED, SUCCEED_ASYNC, or FAIL.</span></span> <span data-ttu-id="46437-114">La fonction **bcp_exec** retourne SUCCEED si toutes les lignes sont copiées.</span><span class="sxs-lookup"><span data-stu-id="46437-114">The **bcp_exec** function returns SUCCEED if all rows are copied.</span></span> <span data-ttu-id="46437-115">**bcp_exec** retourne SUCCEED_ASYNC si une opération de copie en bloc asynchrone est toujours en attente.</span><span class="sxs-lookup"><span data-stu-id="46437-115">**bcp_exec** returns SUCCEED_ASYNC if an asynchronous bulk copy operation is still outstanding.</span></span> <span data-ttu-id="46437-116">**bcp_exec** retourne FAIL en cas d'échec total ou si le nombre de lignes générant des erreurs atteint la valeur spécifiée pour BCPMAXERRS à l'aide de [bcp_control](bcp-control.md).</span><span class="sxs-lookup"><span data-stu-id="46437-116">**bcp_exec** returns FAIL if a complete failure occurs, or if the number of rows generating errors reaches the value specified for BCPMAXERRS using [bcp_control](bcp-control.md).</span></span> <span data-ttu-id="46437-117">La valeur par défaut de BCPMAXERRS est 10.</span><span class="sxs-lookup"><span data-stu-id="46437-117">BCPMAXERRS defaults to 10.</span></span> <span data-ttu-id="46437-118">L'option BCPMAXERRS affecte uniquement les erreurs de syntaxe détectées par le fournisseur lorsqu'elle lit les données du fichier de données (et non les lignes transmises au serveur).</span><span class="sxs-lookup"><span data-stu-id="46437-118">The BCPMAXERRS option affects only the syntax errors detected by the provider while reading the rows from the data file (and not the rows sent to the server).</span></span> <span data-ttu-id="46437-119">Le serveur interrompt le lot dès qu'il détecte une erreur avec une ligne.</span><span class="sxs-lookup"><span data-stu-id="46437-119">Server aborts the batch when it detects an error with a row.</span></span> <span data-ttu-id="46437-120">Vérifiez le paramètre *pnRowsProcessed* correspondant au nombre de lignes copiées avec succès.</span><span class="sxs-lookup"><span data-stu-id="46437-120">Check the *pnRowsProcessed* parameter for the number of rows successfully copied.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46437-121">Notes</span><span class="sxs-lookup"><span data-stu-id="46437-121">Remarks</span></span>  
 <span data-ttu-id="46437-122">En fonction de la valeur du paramètre *eDirection* dans [bcp_init](bcp-init.md), cette fonction copie les données d'un fichier utilisateur vers une table de base de données ou inversement.</span><span class="sxs-lookup"><span data-stu-id="46437-122">This function copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter in [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="46437-123">Avant d'appeler **bcp_exec**, appelez **bcp_init** avec un nom de fichier utilisateur valide.</span><span class="sxs-lookup"><span data-stu-id="46437-123">Before calling **bcp_exec**, call **bcp_init** with a valid user file name.</span></span> <span data-ttu-id="46437-124">L'échec de cette opération entraîne une erreur.</span><span class="sxs-lookup"><span data-stu-id="46437-124">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="46437-125">**bcp_exec** est la seule fonction de copie en bloc qui est susceptible d'être en attente pendant une durée prolongée.</span><span class="sxs-lookup"><span data-stu-id="46437-125">**bcp_exec** is the only bulk copy function that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="46437-126">Il s'agit par conséquent de la seule fonction de copie en bloc qui prend en charge le mode asynchrone.</span><span class="sxs-lookup"><span data-stu-id="46437-126">It is therefore the only bulk copy function that supports asynchronous mode.</span></span> <span data-ttu-id="46437-127">Pour définir le mode asynchrone, utilisez [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) pour définir SQL_ATTR_ASYNC_ENABLE to SQL_ASYNC_ENABLE_ON avant d'appeler la fonction **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="46437-127">To set asynchronous mode, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set SQL_ATTR_ASYNC_ENABLE to SQL_ASYNC_ENABLE_ON before calling **bcp_exec**.</span></span> <span data-ttu-id="46437-128">Pour tester son exécution en bonne et due forme, appelez la méthode **bcp_exec** avec les mêmes paramètres.</span><span class="sxs-lookup"><span data-stu-id="46437-128">To test for completion, call **bcp_exec** with the same parameters.</span></span> <span data-ttu-id="46437-129">Si la copie en bloc n'a pas encore été exécutée, **bcp_exec** retourne SUCCEED_ASYNC.</span><span class="sxs-lookup"><span data-stu-id="46437-129">If the bulk copy has not yet completed, **bcp_exec** returns SUCCEED_ASYNC.</span></span> <span data-ttu-id="46437-130">Il retourne également dans *pnRowsProcessed* un état du nombre de lignes envoyées au serveur.</span><span class="sxs-lookup"><span data-stu-id="46437-130">It also returns in *pnRowsProcessed* a status count of the number of rows that have been sent to the server.</span></span> <span data-ttu-id="46437-131">Les lignes envoyées au serveur sont validées uniquement une fois la fin du lot atteinte.</span><span class="sxs-lookup"><span data-stu-id="46437-131">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
 <span data-ttu-id="46437-132">Pour plus d’informations sur la modification avec rupture dans la copie en bloc à compter de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , consultez [exécution d’opérations de copie en bloc &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="46437-132">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46437-133">Exemple</span><span class="sxs-lookup"><span data-stu-id="46437-133">Example</span></span>  
 <span data-ttu-id="46437-134">L'exemple ci-après décrit comment utiliser la fonction **bcp_exec**:</span><span class="sxs-lookup"><span data-stu-id="46437-134">The following example shows how to use **bcp_exec**:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("pubs..authors"), _T("authors.sav"), NULL, DB_OUT)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Now, execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   if (nRowsProcessed == -1)  
      {  
      printf_s("No rows processed on bulk copy execution.\n");  
      }  
   else  
      {  
      printf_s("Incomplete bulk copy.   Only %ld row%s copied.\n",  
         nRowsProcessed, (nRowsProcessed == 1) ? "": "s");  
      }  
   return;  
   }  
  
printf_s("%ld rows processed.\n", nRowsProcessed);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="46437-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46437-135">See Also</span></span>  
 [<span data-ttu-id="46437-136">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="46437-136">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
