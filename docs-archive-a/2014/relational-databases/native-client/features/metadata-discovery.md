---
title: Découverte des métadonnées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: ec3c0f4f-f838-43ce-85f2-cf2761e2aac5
author: rothja
ms.author: jroth
ms.openlocfilehash: 571df9f21ab46a53c8aba7907039ce02afd6ad05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698069"
---
# <a name="metadata-discovery"></a><span data-ttu-id="89206-102">Découverte des métadonnées</span><span class="sxs-lookup"><span data-stu-id="89206-102">Metadata Discovery</span></span>
  <span data-ttu-id="89206-103">L'amélioration de découverte des métadonnées dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] permet aux applications [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client de s'assurer que les métadonnées de colonne ou de paramètre retournées par l'exécution d'une requête sont identiques ou compatibles avec le format des métadonnées que vous avez spécifié avant l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="89206-103">The metadata discovery improvement in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] allows [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client applications to ensure that column or parameter metadata returned from the execution of a query is identical to or compatible with the metadata format you specified before you executed the query.</span></span> <span data-ttu-id="89206-104">Vous recevrez une erreur si les métadonnées retournées après l'exécution de la requête ne sont pas compatibles avec le format des métadonnées que vous avez spécifié avant l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="89206-104">You will receive an error if the metadata returned after query execution is not compatible with the metadata format you specified before query execution.</span></span>  
  
 <span data-ttu-id="89206-105">Dans les fonctions bcp et ODBC, et dans les interfaces IBCPSession et  IBCPSession2, vous pouvez maintenant spécifier une lecture différée (découverte des métadonnées retardée) pour éviter la découverte de métadonnées pour des opérations de requête.</span><span class="sxs-lookup"><span data-stu-id="89206-105">In bcp and ODBC functions, and IBCPSession and IBCPSession2 interfaces, you can now specify a delayed read (delayed metadata discovery) to avoid metadata discovery for query out operations.</span></span> <span data-ttu-id="89206-106">Cela améliore la performance et élimine les échecs de découverte des métadonnées.</span><span class="sxs-lookup"><span data-stu-id="89206-106">This improves performance and eliminates metadata discovery failures.</span></span>  
  
 <span data-ttu-id="89206-107">Si vous développez une application à l'aide de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , mais que vous vous connectez à une version du serveur antérieure à [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], les fonctionnalités de découverte des métadonnées correspondront à la version du serveur.</span><span class="sxs-lookup"><span data-stu-id="89206-107">If you develop an application using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] but connect to a server version earlier than [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], metadata discovery functionality will correspond to the version of the server.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89206-108">Notes</span><span class="sxs-lookup"><span data-stu-id="89206-108">Remarks</span></span>  
 <span data-ttu-id="89206-109">Les fonctions bcp suivantes ont été améliorées dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] afin de fournir une fonctionnalité améliorée de découverte des métadonnées :</span><span class="sxs-lookup"><span data-stu-id="89206-109">The following bcp functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="89206-110">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="89206-110">bcp_columns</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md)  
  
-   [<span data-ttu-id="89206-111">bcp_control</span><span class="sxs-lookup"><span data-stu-id="89206-111">bcp_control</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md)  
  
-   [<span data-ttu-id="89206-112">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="89206-112">bcp_getcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="89206-113">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="89206-113">bcp_readfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md)  
  
-   [<span data-ttu-id="89206-114">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="89206-114">bcp_setcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setcolfmt.md)  
  
 <span data-ttu-id="89206-115">Vous noterez également une amélioration des performances lors de la spécification du format de métadonnées à l'aide de [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md).</span><span class="sxs-lookup"><span data-stu-id="89206-115">You will also see a performance improvement when specifying metadata format using [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md).</span></span>  
  
 <span data-ttu-id="89206-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) a un nouveau *eOption* pour contrôler le comportement de bcp_readfmt : `BCPDELAYREADFMT` .</span><span class="sxs-lookup"><span data-stu-id="89206-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) has a new *eOption* to control the behavior of bcp_readfmt: `BCPDELAYREADFMT`.</span></span>  
  
 <span data-ttu-id="89206-117">Les fonctions ODBC suivantes ont été améliorées dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] pour fournir une fonctionnalité améliorée de découverte des métadonnées :</span><span class="sxs-lookup"><span data-stu-id="89206-117">The following ODBC functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="89206-118">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="89206-118">SQLNumResultCols</span></span>](../../native-client-odbc-api/sqlnumresultcols.md)  
  
-   [<span data-ttu-id="89206-119">SQLDescribeCol</span><span class="sxs-lookup"><span data-stu-id="89206-119">SQLDescribeCol</span></span>](../../native-client-odbc-api/sqldescribecol.md)  
  
-   [<span data-ttu-id="89206-120">SQLNumParams</span><span class="sxs-lookup"><span data-stu-id="89206-120">SQLNumParams</span></span>](../../native-client-odbc-api/sqlnumparams.md)  
  
-   [<span data-ttu-id="89206-121">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="89206-121">SQLDescribeParam</span></span>](../../native-client-odbc-api/sqldescribeparam.md)  
  
 <span data-ttu-id="89206-122">Les fonctions membres OLE DB suivantes ont été améliorées dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] pour fournir une fonctionnalité améliorée de découverte des métadonnées :</span><span class="sxs-lookup"><span data-stu-id="89206-122">The following OLE DB member functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   <span data-ttu-id="89206-123">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="89206-123">IColumnsInfo::GetColumnInfo</span></span>  
  
-   <span data-ttu-id="89206-124">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="89206-124">IColumnsRowset::GetColumnsRowset</span></span>  
  
-   <span data-ttu-id="89206-125">ICommandWithParameters::GetParameterInfo (voir [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md) pour plus d’informations)</span><span class="sxs-lookup"><span data-stu-id="89206-125">ICommandWithParameters::GetParameterInfo (see [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md) for more information)</span></span>  
  
 <span data-ttu-id="89206-126">Vous noterez également une amélioration des performances lors de la spécification du format de métadonnées avec IBCPSession::BCPSetBulkMode</span><span class="sxs-lookup"><span data-stu-id="89206-126">You will also see a performance improvement when specifying metadata format using IBCPSession::BCPSetBulkMode</span></span>  
  
 <span data-ttu-id="89206-127">La découverte améliorée des métadonnées  dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client est possible grâce à l'ajout de deux procédures stockées dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="89206-127">The improved metadata discovery in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is possible because of the addition of two stored procedures in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:</span></span>  
  
-   <span data-ttu-id="89206-128">sp_describe_first_result_set</span><span class="sxs-lookup"><span data-stu-id="89206-128">sp_describe_first_result_set</span></span>  
  
-   <span data-ttu-id="89206-129">sp_describe_undeclared_parameters</span><span class="sxs-lookup"><span data-stu-id="89206-129">sp_describe_undeclared_parameters</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89206-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89206-130">See Also</span></span>  
 [<span data-ttu-id="89206-131">Fonctionnalités de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="89206-131">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
