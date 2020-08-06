---
title: bcp_batch | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_batch
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_batch function
ms.assetid: 0bda489e-86bc-4a7e-80f6-96047e03f281
author: rothja
ms.author: jroth
ms.openlocfilehash: 24cdf6e2934c2b80a55d8fa1fcc572a976b636ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605387"
---
# <a name="bcp_batch"></a><span data-ttu-id="eccad-102">bcp_batch</span><span class="sxs-lookup"><span data-stu-id="eccad-102">bcp_batch</span></span>
  <span data-ttu-id="eccad-103">Valide toutes les lignes précédemment copiées en bloc à partir de variables de programme et envoyées à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="eccad-103">Commits all rows previously bulk copied from program variables and sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eccad-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="eccad-104">Syntax</span></span>  
  
```  
  
DBINT bcp_batch (HDBC  
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="eccad-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="eccad-105">Arguments</span></span>  
 <span data-ttu-id="eccad-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="eccad-106">*hdbc*</span></span>  
 <span data-ttu-id="eccad-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="eccad-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="eccad-108">Retours</span><span class="sxs-lookup"><span data-stu-id="eccad-108">Returns</span></span>  
 <span data-ttu-id="eccad-109">Le nombre de lignes enregistrées après le dernier appel à **bcp_batch**, ou -1 en cas d'erreur.</span><span class="sxs-lookup"><span data-stu-id="eccad-109">The number of rows saved after the last call to **bcp_batch**, or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eccad-110">Notes</span><span class="sxs-lookup"><span data-stu-id="eccad-110">Remarks</span></span>  
 <span data-ttu-id="eccad-111">Les lots de copie en bloc définissent des transactions.</span><span class="sxs-lookup"><span data-stu-id="eccad-111">Bulk copy batches define transactions.</span></span> <span data-ttu-id="eccad-112">Lorsqu'une application utilise [bcp_bind](bcp-bind.md) et **bcp_sendrow** pour copier en bloc des lignes à partir de variables de programme dans des tables SQL Server, les lignes sont validées uniquement lorsque le programme appelle **bcp_batch** ou [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="eccad-112">When an application uses [bcp_bind](bcp-bind.md) and **bcp_sendrow** to bulk copy rows from program variables to SQL Server tables, the rows are committed only when the program calls **bcp_batch** or [bcp_done](bcp-done.md).</span></span>  
  
 <span data-ttu-id="eccad-113">Vous pouvez appeler **bcp_batch** une fois chaque *n* lignes ou lorsqu'il y a une accalmie dans les données entrantes (comme dans une application de télémesure).</span><span class="sxs-lookup"><span data-stu-id="eccad-113">You can call **bcp_batch** once every *n* rows or when there is a lull in incoming data (as in a telemetry application).</span></span> <span data-ttu-id="eccad-114">Si une application n'appelle pas **bcp_batch** , les lignes copiées en bloc sont validées uniquement lorsque **bcp_done** est appelé.</span><span class="sxs-lookup"><span data-stu-id="eccad-114">If an application does not call **bcp_batch** the bulk copied rows are committed only when **bcp_done** is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eccad-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eccad-115">See Also</span></span>  
 [<span data-ttu-id="eccad-116">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="eccad-116">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
