---
title: bcp_writefmt | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_writefmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_writefmt function
ms.assetid: cb4c1d37-667d-4bcd-b13c-eb638bcc9b69
author: rothja
ms.author: jroth
ms.openlocfilehash: 13785469e0b02f63f14d28f0db87e77df3a15cfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611052"
---
# <a name="bcp_writefmt"></a><span data-ttu-id="4c2d8-102">bcp_writefmt</span><span class="sxs-lookup"><span data-stu-id="4c2d8-102">bcp_writefmt</span></span>
  <span data-ttu-id="4c2d8-103">Crée un fichier de format qui contient une description du format du fichier de données de copie en bloc actif.</span><span class="sxs-lookup"><span data-stu-id="4c2d8-103">Creates a format file containing a description of the format of the current bulk copy data file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c2d8-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4c2d8-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_writefmt (  
HDBC   
hdbc  
,  
LPCTSTR   
szFormatFile  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="4c2d8-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="4c2d8-105">Arguments</span></span>  
 <span data-ttu-id="4c2d8-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="4c2d8-106">*hdbc*</span></span>  
 <span data-ttu-id="4c2d8-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="4c2d8-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="4c2d8-108">*szFormatFile*</span><span class="sxs-lookup"><span data-stu-id="4c2d8-108">*szFormatFile*</span></span>  
 <span data-ttu-id="4c2d8-109">Chemin d'accès et nom de fichier du fichier utilisateur qui recevra les valeurs de format pour le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="4c2d8-109">Is the path and file name of the user file to receive format values for the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="4c2d8-110">Retours</span><span class="sxs-lookup"><span data-stu-id="4c2d8-110">Returns</span></span>  
 <span data-ttu-id="4c2d8-111">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="4c2d8-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c2d8-112">Notes</span><span class="sxs-lookup"><span data-stu-id="4c2d8-112">Remarks</span></span>  
 <span data-ttu-id="4c2d8-113">Le fichier de format spécifie le format de données d'un fichier de données créé par le biais d'une copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="4c2d8-113">The format file specifies the data format of a data file created by bulk copy.</span></span> <span data-ttu-id="4c2d8-114">Les appels aux méthodes [bcp_columns](bcp-columns.md) et [bcp_colfmt](bcp-colfmt.md) définissent le format du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="4c2d8-114">Calls to [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md) define the format of the data file.</span></span> <span data-ttu-id="4c2d8-115">**bcp_writefmt** enregistre cette définition dans le fichier référencé par l'argument *szFormatFile*.</span><span class="sxs-lookup"><span data-stu-id="4c2d8-115">**bcp_writefmt** saves this definition in the file referenced by *szFormatFile*.</span></span> <span data-ttu-id="4c2d8-116">Pour plus d'informations, consultez [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="4c2d8-116">For more information, see [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="4c2d8-117">Pour plus d’informations sur la structure des fichiers de format de données **BCP** , consultez [Importer et exporter des données en bloc à l’aide de l’utilitaire bcp &#40;SQL Server&#41;](../import-export/import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c2d8-117">For more information about the structure of **bcp** data format files, see [Import and Export Bulk Data by Using the bcp Utility &#40;SQL Server&#41;](../import-export/import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md).</span></span>  
  
 <span data-ttu-id="4c2d8-118">Pour charger un fichier de format enregistré, utilisez [bcp_readfmt](bcp-readfmt.md).</span><span class="sxs-lookup"><span data-stu-id="4c2d8-118">To load a saved format file, use [bcp_readfmt](bcp-readfmt.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c2d8-119">Le fichier de format produit par **bcp_writefmt** est pris en charge uniquement par les versions de l'utilitaire **bcp** distribuées à l'aide de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="4c2d8-119">The format file produced by **bcp_writefmt** is supported only by versions of the **bcp** utility distributed with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c2d8-120"> Exemple</span><span class="sxs-lookup"><span data-stu-id="4c2d8-120">Example</span></span>  
  
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
   _T("myErrors"),    DB_OUT) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_columns(hdbc, 3) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
bcp_colfmt(hdbc, 1, SQLCHARACTER, 0, SQL_VARLEN_DATA, '\t', 1, 1);  
bcp_colfmt(hdbc, 2, SQLCHARACTER, 0, SQL_VARLEN_DATA, '\t', 1, 2);  
bcp_colfmt(hdbc, 3, SQLCHARACTER, 0, SQL_VARLEN_DATA, '\t', 1, 3);  
  
if (bcp_writefmt(hdbc, _T("myFmtFile.fmt")) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_exec(hdbc, &nRowsProcessed) == SUCCEED)  
   {  
   printf_s("%ld rows copied from SQL Server\n", nRowsProcessed);  
   }  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c2d8-121"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c2d8-121">See Also</span></span>  
 [<span data-ttu-id="4c2d8-122">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="4c2d8-122">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
