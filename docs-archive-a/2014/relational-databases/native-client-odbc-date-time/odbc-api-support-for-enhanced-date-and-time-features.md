---
title: Prise en charge des API ODBC pour les fonctionnalités de date et d’heure améliorées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- date/time [ODBC], API support
ms.assetid: 430c029d-f8c1-4de7-a9dd-330e9b6bfc20
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b5225850b427e411e1e9e15e9fcd7780f473440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706476"
---
# <a name="odbc-api-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="786ca-102">Prise en charge des fonctionnalités de date et heure améliorées par l’API ODBC</span><span class="sxs-lookup"><span data-stu-id="786ca-102">ODBC API Support for Enhanced Date and Time Features</span></span>
  <span data-ttu-id="786ca-103">Les API ODBC suivantes prennent en charge les fonctionnalités de date/heure améliorées :</span><span class="sxs-lookup"><span data-stu-id="786ca-103">The following ODBC APIs support enhanced date and time functionality:</span></span>  
  
-   [<span data-ttu-id="786ca-104">SQLBindCol</span><span class="sxs-lookup"><span data-stu-id="786ca-104">SQLBindCol</span></span>](../native-client-odbc-api/sqlbindcol.md)  
  
-   [<span data-ttu-id="786ca-105">SQLBindParameter</span><span class="sxs-lookup"><span data-stu-id="786ca-105">SQLBindParameter</span></span>](../native-client-odbc-api/sqlbindparameter.md)  
  
-   [<span data-ttu-id="786ca-106">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="786ca-106">SQLColAttribute</span></span>](../native-client-odbc-api/sqlcolattribute.md)  
  
-   [<span data-ttu-id="786ca-107">SQLColumns</span><span class="sxs-lookup"><span data-stu-id="786ca-107">SQLColumns</span></span>](../native-client-odbc-api/sqlcolumns.md)  
  
-   [<span data-ttu-id="786ca-108">SQLDescribeCol</span><span class="sxs-lookup"><span data-stu-id="786ca-108">SQLDescribeCol</span></span>](../native-client-odbc-api/sqldescribecol.md)  
  
-   [<span data-ttu-id="786ca-109">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="786ca-109">SQLDescribeParam</span></span>](../native-client-odbc-api/sqldescribeparam.md)  
  
-   [<span data-ttu-id="786ca-110">SQLFetch</span><span class="sxs-lookup"><span data-stu-id="786ca-110">SQLFetch</span></span>](../native-client-odbc-api/sqlfetch.md)  
  
-   [<span data-ttu-id="786ca-111">SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="786ca-111">SQLFetchScroll</span></span>](../native-client-odbc-api/sqlfetchscroll.md)  
  
-   [<span data-ttu-id="786ca-112">SQLGetData</span><span class="sxs-lookup"><span data-stu-id="786ca-112">SQLGetData</span></span>](../native-client-odbc-api/sqlgetdata.md)  
  
-   [<span data-ttu-id="786ca-113">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="786ca-113">SQLGetDescField</span></span>](../native-client-odbc-api/sqlgetdescfield.md)  
  
-   [<span data-ttu-id="786ca-114">SQLGetDescRec</span><span class="sxs-lookup"><span data-stu-id="786ca-114">SQLGetDescRec</span></span>](../native-client-odbc-api/sqlgetdescrec.md)  
  
-   [<span data-ttu-id="786ca-115">SQLGetTypeInfo</span><span class="sxs-lookup"><span data-stu-id="786ca-115">SQLGetTypeInfo</span></span>](../native-client-odbc-api/sqlgettypeinfo.md)  
  
-   [<span data-ttu-id="786ca-116">SQLProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="786ca-116">SQLProcedureColumns</span></span>](../native-client-odbc-api/sqlprocedurecolumns.md)  
  
-   [<span data-ttu-id="786ca-117">SQLPutData</span><span class="sxs-lookup"><span data-stu-id="786ca-117">SQLPutData</span></span>](../native-client-odbc-api/sqlputdata.md)  
  
-   [<span data-ttu-id="786ca-118">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="786ca-118">SQLSetDescField</span></span>](../native-client-odbc-api/sqlsetdescfield.md)  
  
-   [<span data-ttu-id="786ca-119">SQLSetDescRec</span><span class="sxs-lookup"><span data-stu-id="786ca-119">SQLSetDescRec</span></span>](../native-client-odbc-api/sqlsetdescrec.md)  
  
-   [<span data-ttu-id="786ca-120">SQLSpecialColumns</span><span class="sxs-lookup"><span data-stu-id="786ca-120">SQLSpecialColumns</span></span>](../native-client-odbc-api/sqlspecialcolumns.md)  
  
 <span data-ttu-id="786ca-121">Les API de copie en bloc suivantes prennent en charge les fonctionnalités de date/heure améliorées :</span><span class="sxs-lookup"><span data-stu-id="786ca-121">The following bulk copy APIs support enhanced date and time functionality:</span></span>  
  
-   [<span data-ttu-id="786ca-122">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="786ca-122">bcp_bind</span></span>](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)  
  
-   [<span data-ttu-id="786ca-123">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="786ca-123">bcp_colfmt</span></span>](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)  
  
-   [<span data-ttu-id="786ca-124">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="786ca-124">bcp_getcolfmt</span></span>](../native-client-odbc-extensions-bulk-copy-functions/bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="786ca-125">bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="786ca-125">bcp_gettypename</span></span>](../native-client-odbc-extensions-bulk-copy-functions/bcp-gettypename.md)  
  
-   [<span data-ttu-id="786ca-126">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="786ca-126">bcp_setcolfmt</span></span>](../native-client-odbc-extensions-bulk-copy-functions/bcp-setcolfmt.md)  
  
## <a name="see-also"></a><span data-ttu-id="786ca-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="786ca-127">See Also</span></span>  
 [<span data-ttu-id="786ca-128">Améliorations de la date et de l’heure &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="786ca-128">Date and Time Improvements &#40;ODBC&#41;</span></span>](date-and-time-improvements-odbc.md)  
  
  
