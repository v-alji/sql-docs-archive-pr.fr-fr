---
title: bcp_readfmt | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_readfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_readfmt function
ms.assetid: 654001c8-ae9f-425c-b820-f0191bf89367
author: rothja
ms.author: jroth
ms.openlocfilehash: 37032ec276be8b914d73e834453cc5d87cdedbbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603504"
---
# <a name="bcp_readfmt"></a><span data-ttu-id="3d499-102">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="3d499-102">bcp_readfmt</span></span>
  <span data-ttu-id="3d499-103">Lit la définition du format du fichier de données à partir du fichier de format spécifié.</span><span class="sxs-lookup"><span data-stu-id="3d499-103">Reads a data file format definition from the specified format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d499-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3d499-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_readfmt (  
HDBC   
hdbc  
,  
LPCTSTR   
szFormatFile  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3d499-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="3d499-105">Arguments</span></span>  
 <span data-ttu-id="3d499-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="3d499-106">*hdbc*</span></span>  
 <span data-ttu-id="3d499-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="3d499-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="3d499-108">*szFormatFile*</span><span class="sxs-lookup"><span data-stu-id="3d499-108">*szFormatFile*</span></span>  
 <span data-ttu-id="3d499-109">Chemin d'accès et nom du fichier contenant les valeurs de format du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="3d499-109">Is the path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="3d499-110">Retours</span><span class="sxs-lookup"><span data-stu-id="3d499-110">Returns</span></span>  
 <span data-ttu-id="3d499-111">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="3d499-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d499-112">Notes</span><span class="sxs-lookup"><span data-stu-id="3d499-112">Remarks</span></span>  
 <span data-ttu-id="3d499-113">Après avoir `bcp_readfmt` lu les valeurs de format, il effectue les appels appropriés à [bcp_columns](bcp-columns.md) et [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="3d499-113">After `bcp_readfmt` reads the format values, it makes the appropriate calls to [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span> <span data-ttu-id="3d499-114">Vous n'avez nul besoin d'analyser un fichier de format et d'exécuter ces appels.</span><span class="sxs-lookup"><span data-stu-id="3d499-114">There is no need for you to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="3d499-115">Pour rendre un fichier de format persistant, appelez [bcp_writefmt](bcp-writefmt.md).</span><span class="sxs-lookup"><span data-stu-id="3d499-115">To persist a format file, call [bcp_writefmt](bcp-writefmt.md).</span></span> <span data-ttu-id="3d499-116">Les appels à `bcp_readfmt` peuvent référencer des formats enregistrés.</span><span class="sxs-lookup"><span data-stu-id="3d499-116">Calls to `bcp_readfmt` can reference saved formats.</span></span> <span data-ttu-id="3d499-117">Pour plus d'informations, consultez [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="3d499-117">For more information, see [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="3d499-118">L’utilitaire de copie en bloc (**BCP**) peut également enregistrer des formats de données définis par l’utilisateur dans des fichiers qui peuvent être référencés par `bcp_readfmt` .</span><span class="sxs-lookup"><span data-stu-id="3d499-118">Alternately, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by `bcp_readfmt`.</span></span> <span data-ttu-id="3d499-119">Pour plus d’informations sur l’utilitaire **BCP** et la structure des fichiers de format de données **BCP** , consultez [importation et exportation en bloc de données &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3d499-119">For more information about the **bcp** utility and the structure of **bcp** data format files, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="3d499-120">La `BCPDELAYREADFMT` valeur du paramètre *eOption* de [bcp_control](bcp-control.md) modifie le comportement de bcp_readfmt.</span><span class="sxs-lookup"><span data-stu-id="3d499-120">The `BCPDELAYREADFMT` value of the *eOption* parameter of [bcp_control](bcp-control.md) modifies the behavior of bcp_readfmt.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3d499-121">Le fichier de format a dû être produit par la version 4.2 ou version ultérieure de l'utilitaire **bcp** .</span><span class="sxs-lookup"><span data-stu-id="3d499-121">The format file must have been produced by version 4.2 or later of the **bcp** utility.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d499-122"> Exemple</span><span class="sxs-lookup"><span data-stu-id="3d499-122">Example</span></span>  
  
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
if (bcp_init(hdbc, _T("myTable"), _T("myData.csv"),  
   _T("myErrors"),    DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_readfmt(hdbc, _T("myFmtFile.fmt")) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_exec(hdbc, &nRowsProcessed) == SUCCEED)  
   {  
   cout << nRowsProcessed << " rows copied to SQL Server\n";  
   }  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d499-123"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d499-123">See Also</span></span>  
 [<span data-ttu-id="3d499-124">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="3d499-124">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
