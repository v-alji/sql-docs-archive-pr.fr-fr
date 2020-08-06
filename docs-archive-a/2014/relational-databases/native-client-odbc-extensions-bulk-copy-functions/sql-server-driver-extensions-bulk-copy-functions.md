---
title: Fonctions de copie en bloc | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], functions
- ODBC, bulk copy operations
- functions [ODBC]
ms.assetid: 6526b892-1d58-4f55-8335-f09887f6ea02
author: rothja
ms.author: jroth
ms.openlocfilehash: 02dba8cf4d510d2ec5f20e600302bb692c749f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611053"
---
# <a name="bulk-copy-functions"></a><span data-ttu-id="0f16b-102">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="0f16b-102">Bulk Copy Functions</span></span>
  <span data-ttu-id="0f16b-103">L'extension API de copie en bloc du pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client  spécifique à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permet aux applications clientes d'ajouter rapidement des lignes de données à une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou d'en extraire.</span><span class="sxs-lookup"><span data-stu-id="0f16b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific bulk-copy API extension of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver allows client applications to rapidly add data rows to, or extract data rows from, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="0f16b-104">Lorsque vous utilisez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, vous pouvez faire référence aux fonctions de copie en bloc (BCP) dans SQLNCLI11.LIB et SQLNCLI.H.</span><span class="sxs-lookup"><span data-stu-id="0f16b-104">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, you can reference the bulk copy functions (BCP) in SQLNCLI11.LIB and SQLNCLI.H.</span></span>  
  
 <span data-ttu-id="0f16b-105">Toute application qui utilise une fonction API de copie en bloc (BCP) doit être liée à la bibliothèque (.lib) fournie avec le pilote (.dll) utilisé par l'application.</span><span class="sxs-lookup"><span data-stu-id="0f16b-105">An application that uses BCP API function calls should link with the library (.lib) that shipped with the driver (.dll) used by the application.</span></span> <span data-ttu-id="0f16b-106">Une application BCP ne doit pas être liée à plus d'une bibliothèque de pilote.</span><span class="sxs-lookup"><span data-stu-id="0f16b-106">A BCP application should not link with more than one driver library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f16b-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0f16b-107">In This Section</span></span>  
  
-   [<span data-ttu-id="0f16b-108">bcp_batch</span><span class="sxs-lookup"><span data-stu-id="0f16b-108">bcp_batch</span></span>](bcp-batch.md)  
  
-   [<span data-ttu-id="0f16b-109">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="0f16b-109">bcp_bind</span></span>](bcp-bind.md)  
  
-   [<span data-ttu-id="0f16b-110">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="0f16b-110">bcp_colfmt</span></span>](bcp-colfmt.md)  
  
-   [<span data-ttu-id="0f16b-111">bcp_collen</span><span class="sxs-lookup"><span data-stu-id="0f16b-111">bcp_collen</span></span>](bcp-collen.md)  
  
-   [<span data-ttu-id="0f16b-112">bcp_colptr</span><span class="sxs-lookup"><span data-stu-id="0f16b-112">bcp_colptr</span></span>](bcp-colptr.md)  
  
-   [<span data-ttu-id="0f16b-113">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="0f16b-113">bcp_columns</span></span>](bcp-columns.md)  
  
-   [<span data-ttu-id="0f16b-114">bcp_control</span><span class="sxs-lookup"><span data-stu-id="0f16b-114">bcp_control</span></span>](bcp-control.md)  
  
-   [<span data-ttu-id="0f16b-115">bcp_done</span><span class="sxs-lookup"><span data-stu-id="0f16b-115">bcp_done</span></span>](bcp-done.md)  
  
-   [<span data-ttu-id="0f16b-116">bcp_exec</span><span class="sxs-lookup"><span data-stu-id="0f16b-116">bcp_exec</span></span>](bcp-exec.md)  
  
-   [<span data-ttu-id="0f16b-117">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="0f16b-117">bcp_getcolfmt</span></span>](bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="0f16b-118">bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="0f16b-118">bcp_gettypename</span></span>](bcp-gettypename.md)  
  
-   [<span data-ttu-id="0f16b-119">bcp_init</span><span class="sxs-lookup"><span data-stu-id="0f16b-119">bcp_init</span></span>](bcp-init.md)  
  
-   [<span data-ttu-id="0f16b-120">bcp_moretext</span><span class="sxs-lookup"><span data-stu-id="0f16b-120">bcp_moretext</span></span>](bcp-moretext.md)  
  
-   [<span data-ttu-id="0f16b-121">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="0f16b-121">bcp_readfmt</span></span>](bcp-readfmt.md)  
  
-   [<span data-ttu-id="0f16b-122">bcp_sendrow</span><span class="sxs-lookup"><span data-stu-id="0f16b-122">bcp_sendrow</span></span>](bcp-sendrow.md)  
  
-   [<span data-ttu-id="0f16b-123">bcp_setbulkmode</span><span class="sxs-lookup"><span data-stu-id="0f16b-123">bcp_setbulkmode</span></span>](bcp-setbulkmode.md)  
  
-   [<span data-ttu-id="0f16b-124">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="0f16b-124">bcp_setcolfmt</span></span>](bcp-setcolfmt.md)  
  
-   [<span data-ttu-id="0f16b-125">bcp_writefmt</span><span class="sxs-lookup"><span data-stu-id="0f16b-125">bcp_writefmt</span></span>](bcp-writefmt.md)  
  
## <a name="see-also"></a><span data-ttu-id="0f16b-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f16b-126">See Also</span></span>  
 <span data-ttu-id="0f16b-127">[Extensions du pilote SQL Server](../../database-engine/dev-guide/sql-server-driver-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="0f16b-127">[SQL Server Driver Extensions](../../database-engine/dev-guide/sql-server-driver-extensions.md) </span></span>  
 [<span data-ttu-id="0f16b-128">Exécution d’opérations de copie en bloc &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="0f16b-128">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md)  
  
  
