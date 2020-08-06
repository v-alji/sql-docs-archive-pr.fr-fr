---
title: Détails de l’implémentation de l’API ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQL Server Native Client ODBC driver, SQL Server-specific behaviors
- ODBC, SQL Server-specific behaviors
- functions [ODBC]
ms.assetid: dca92489-f179-4b1f-997c-adcc46aa17a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 1af47924090e7cb1df8ed7907ba0f793b9df2420
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708288"
---
# <a name="odbc-api-implementation-details"></a><span data-ttu-id="dc040-102">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="dc040-102">ODBC API Implementation Details</span></span>
  <span data-ttu-id="dc040-103">Cette section fournit des informations sur les fonctions ODBC qui présentent des comportements spécifiques à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lorsqu'elles sont utilisées avec le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="dc040-103">This section documents the ODBC functions that exhibit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific behaviors when used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="dc040-104">Toutes les fonctions ODBC ne sont pas documentées ici.</span><span class="sxs-lookup"><span data-stu-id="dc040-104">Not all ODBC functions are documented here.</span></span> <span data-ttu-id="dc040-105">Les rubriques individuelles présentent uniquement les problèmes spécifiques à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour une fonction ODBC.</span><span class="sxs-lookup"><span data-stu-id="dc040-105">The individual topics only discuss the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific issues for an ODBC function.</span></span> <span data-ttu-id="dc040-106">Elles ne constituent pas une référence complète pour les fonctions ODBC.</span><span class="sxs-lookup"><span data-stu-id="dc040-106">They are not a complete reference for the ODBC functions.</span></span>  
  
 <span data-ttu-id="dc040-107">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client se conforme à la spécification d'ODBC 3.51 et, si vous utilisez le kit de développement logiciel (SDK) Windows 7, avec la spécification ODBC 3.8.</span><span class="sxs-lookup"><span data-stu-id="dc040-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with the ODBC 3.51 specification and, if you are using the Windows 7 SDK, with the ODBC 3.8 specification.</span></span> <span data-ttu-id="dc040-108">Pour obtenir une référence ODBC complète, consultez le guide [de référence du programmeur ODBC](https://go.microsoft.com/fwlink/?LinkId=45250) en ligne.</span><span class="sxs-lookup"><span data-stu-id="dc040-108">For a comprehensive ODBC reference, view the [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250) online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc040-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="dc040-109">In This Section</span></span>  
  
-   [<span data-ttu-id="dc040-110">SQLBindCol</span><span class="sxs-lookup"><span data-stu-id="dc040-110">SQLBindCol</span></span>](sqlbindcol.md)  
  
-   [<span data-ttu-id="dc040-111">SQLBindParameter</span><span class="sxs-lookup"><span data-stu-id="dc040-111">SQLBindParameter</span></span>](sqlbindparameter.md)  
  
-   [<span data-ttu-id="dc040-112">SQLBrowseConnect</span><span class="sxs-lookup"><span data-stu-id="dc040-112">SQLBrowseConnect</span></span>](sqlbrowseconnect.md)  
  
-   [<span data-ttu-id="dc040-113">SQLCancel</span><span class="sxs-lookup"><span data-stu-id="dc040-113">SQLCancel</span></span>](sqlcancel.md)  
  
-   [<span data-ttu-id="dc040-114">SQLCloseCursor</span><span class="sxs-lookup"><span data-stu-id="dc040-114">SQLCloseCursor</span></span>](sqlclosecursor.md)  
  
-   [<span data-ttu-id="dc040-115">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="dc040-115">SQLColAttribute</span></span>](sqlcolattribute.md)  
  
-   [<span data-ttu-id="dc040-116">SQLColumnPrivileges</span><span class="sxs-lookup"><span data-stu-id="dc040-116">SQLColumnPrivileges</span></span>](sqlcolumnprivileges.md)  
  
-   [<span data-ttu-id="dc040-117">SQLColumns</span><span class="sxs-lookup"><span data-stu-id="dc040-117">SQLColumns</span></span>](sqlcolumns.md)  
  
-   [<span data-ttu-id="dc040-118">SQLConfigDataSource</span><span class="sxs-lookup"><span data-stu-id="dc040-118">SQLConfigDataSource</span></span>](sqlconfigdatasource.md)  
  
-   [<span data-ttu-id="dc040-119">SQLConnect</span><span class="sxs-lookup"><span data-stu-id="dc040-119">SQLConnect</span></span>](sqlconnect.md)  
  
-   [<span data-ttu-id="dc040-120">SQLDescribeCol</span><span class="sxs-lookup"><span data-stu-id="dc040-120">SQLDescribeCol</span></span>](sqldescribecol.md)  
  
-   [<span data-ttu-id="dc040-121">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="dc040-121">SQLDescribeParam</span></span>](sqldescribeparam.md)  
  
-   [<span data-ttu-id="dc040-122">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="dc040-122">SQLDriverConnect</span></span>](sqldriverconnect.md)  
  
-   [<span data-ttu-id="dc040-123">SQLDrivers</span><span class="sxs-lookup"><span data-stu-id="dc040-123">SQLDrivers</span></span>](sqldrivers.md)  
  
-   [<span data-ttu-id="dc040-124">SQLEndTran</span><span class="sxs-lookup"><span data-stu-id="dc040-124">SQLEndTran</span></span>](sqlendtran.md)  
  
-   [<span data-ttu-id="dc040-125">SQLExecDirect</span><span class="sxs-lookup"><span data-stu-id="dc040-125">SQLExecDirect</span></span>](sqlexecdirect.md)  
  
-   [<span data-ttu-id="dc040-126">SQLExecute</span><span class="sxs-lookup"><span data-stu-id="dc040-126">SQLExecute</span></span>](sqlexecute.md)  
  
-   [<span data-ttu-id="dc040-127">SQLFetch</span><span class="sxs-lookup"><span data-stu-id="dc040-127">SQLFetch</span></span>](sqlfetch.md)  
  
-   [<span data-ttu-id="dc040-128">SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="dc040-128">SQLFetchScroll</span></span>](sqlfetchscroll.md)  
  
-   [<span data-ttu-id="dc040-129">SQLForeignKeys</span><span class="sxs-lookup"><span data-stu-id="dc040-129">SQLForeignKeys</span></span>](sqlforeignkeys.md)  
  
-   [<span data-ttu-id="dc040-130">SQLFreeHandle</span><span class="sxs-lookup"><span data-stu-id="dc040-130">SQLFreeHandle</span></span>](sqlfreehandle.md)  
  
-   [<span data-ttu-id="dc040-131">SQLFreeStmt</span><span class="sxs-lookup"><span data-stu-id="dc040-131">SQLFreeStmt</span></span>](sqlfreestmt.md)  
  
-   [<span data-ttu-id="dc040-132">SQLGetConnectAttr</span><span class="sxs-lookup"><span data-stu-id="dc040-132">SQLGetConnectAttr</span></span>](sqlgetconnectattr.md)  
  
-   [<span data-ttu-id="dc040-133">SQLGetCursorName</span><span class="sxs-lookup"><span data-stu-id="dc040-133">SQLGetCursorName</span></span>](sqlgetcursorname.md)  
  
-   [<span data-ttu-id="dc040-134">SQLGetData</span><span class="sxs-lookup"><span data-stu-id="dc040-134">SQLGetData</span></span>](sqlgetdata.md)  
  
-   [<span data-ttu-id="dc040-135">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="dc040-135">SQLGetDescField</span></span>](sqlgetdescfield.md)  
  
-   [<span data-ttu-id="dc040-136">SQLGetDescRec</span><span class="sxs-lookup"><span data-stu-id="dc040-136">SQLGetDescRec</span></span>](sqlgetdescrec.md)  
  
-   [<span data-ttu-id="dc040-137">SQLGetDiagField</span><span class="sxs-lookup"><span data-stu-id="dc040-137">SQLGetDiagField</span></span>](sqlgetdiagfield.md)  
  
-   [<span data-ttu-id="dc040-138">SQLGetFunctions</span><span class="sxs-lookup"><span data-stu-id="dc040-138">SQLGetFunctions</span></span>](sqlgetfunctions.md)  
  
-   [<span data-ttu-id="dc040-139">SQLGetInfo</span><span class="sxs-lookup"><span data-stu-id="dc040-139">SQLGetInfo</span></span>](sqlgetinfo.md)  
  
-   [<span data-ttu-id="dc040-140">SQLGetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="dc040-140">SQLGetStmtAttr</span></span>](sqlgetstmtattr.md)  
  
-   [<span data-ttu-id="dc040-141">SQLGetTypeInfo</span><span class="sxs-lookup"><span data-stu-id="dc040-141">SQLGetTypeInfo</span></span>](sqlgettypeinfo.md)  
  
-   [<span data-ttu-id="dc040-142">SQLMoreResults</span><span class="sxs-lookup"><span data-stu-id="dc040-142">SQLMoreResults</span></span>](sqlmoreresults.md)  
  
-   [<span data-ttu-id="dc040-143">SQLNativeSql</span><span class="sxs-lookup"><span data-stu-id="dc040-143">SQLNativeSql</span></span>](sqlnativesql.md)  
  
-   [<span data-ttu-id="dc040-144">SQLNumParams</span><span class="sxs-lookup"><span data-stu-id="dc040-144">SQLNumParams</span></span>](sqlnumparams.md)  
  
-   [<span data-ttu-id="dc040-145">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="dc040-145">SQLNumResultCols</span></span>](sqlnumresultcols.md)  
  
-   [<span data-ttu-id="dc040-146">SQLParamData</span><span class="sxs-lookup"><span data-stu-id="dc040-146">SQLParamData</span></span>](sqlparamdata.md)  
  
-   [<span data-ttu-id="dc040-147">SQLPrimaryKeys</span><span class="sxs-lookup"><span data-stu-id="dc040-147">SQLPrimaryKeys</span></span>](sqlprimarykeys.md)  
  
-   [<span data-ttu-id="dc040-148">SQLProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="dc040-148">SQLProcedureColumns</span></span>](sqlprocedurecolumns.md)  
  
-   [<span data-ttu-id="dc040-149">SQLProcedures</span><span class="sxs-lookup"><span data-stu-id="dc040-149">SQLProcedures</span></span>](sqlprocedures.md)  
  
-   [<span data-ttu-id="dc040-150">SQLPutData</span><span class="sxs-lookup"><span data-stu-id="dc040-150">SQLPutData</span></span>](sqlputdata.md)  
  
-   [<span data-ttu-id="dc040-151">SQLRowCount</span><span class="sxs-lookup"><span data-stu-id="dc040-151">SQLRowCount</span></span>](sqlrowcount.md)  
  
-   [<span data-ttu-id="dc040-152">SQLSetConnectAttr</span><span class="sxs-lookup"><span data-stu-id="dc040-152">SQLSetConnectAttr</span></span>](sqlsetconnectattr.md)  
  
-   [<span data-ttu-id="dc040-153">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="dc040-153">SQLSetDescField</span></span>](sqlsetdescfield.md)  
  
-   [<span data-ttu-id="dc040-154">SQLSetDescRec</span><span class="sxs-lookup"><span data-stu-id="dc040-154">SQLSetDescRec</span></span>](sqlsetdescrec.md)  
  
-   [<span data-ttu-id="dc040-155">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="dc040-155">SQLSetEnvAttr</span></span>](sqlsetenvattr.md)  
  
-   [<span data-ttu-id="dc040-156">SQLSetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="dc040-156">SQLSetStmtAttr</span></span>](sqlsetstmtattr.md)  
  
-   [<span data-ttu-id="dc040-157">SQLSpecialColumns</span><span class="sxs-lookup"><span data-stu-id="dc040-157">SQLSpecialColumns</span></span>](sqlspecialcolumns.md)  
  
-   [<span data-ttu-id="dc040-158">SQLStatistics</span><span class="sxs-lookup"><span data-stu-id="dc040-158">SQLStatistics</span></span>](../statistics/statistics.md)  
  
-   [<span data-ttu-id="dc040-159">SQLTablePrivileges</span><span class="sxs-lookup"><span data-stu-id="dc040-159">SQLTablePrivileges</span></span>](sqltableprivileges.md)  
  
-   [<span data-ttu-id="dc040-160">SQLTables</span><span class="sxs-lookup"><span data-stu-id="dc040-160">SQLTables</span></span>](sqltables.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc040-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dc040-161">See Also</span></span>  
 <span data-ttu-id="dc040-162">[Référence de&#41; ODBC SQL Server Native Client &#40;](../../database-engine/dev-guide/sql-server-native-client-odbc-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dc040-162">[SQL Server Native Client &#40;ODBC&#41; Reference](../../database-engine/dev-guide/sql-server-native-client-odbc-reference.md) </span></span>  
 [<span data-ttu-id="dc040-163">Génération d’applications avec SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="dc040-163">Building Applications with SQL Server Native Client</span></span>](../native-client/applications/building-applications-with-sql-server-native-client.md)  
  
  
