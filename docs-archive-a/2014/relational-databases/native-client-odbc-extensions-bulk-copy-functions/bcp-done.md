---
title: bcp_done | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_done
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_done function
ms.assetid: e59b3f16-5b59-40da-880f-f3edf657d1ee
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9b0cbcc927fcd10c2d81b3c5c3d39bb80a8e9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599982"
---
# <a name="bcp_done"></a><span data-ttu-id="73aa6-102">bcp_done</span><span class="sxs-lookup"><span data-stu-id="73aa6-102">bcp_done</span></span>
  <span data-ttu-id="73aa6-103">Termine une copie en bloc réalisée avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bcp_sendrow [entre des variables de programme et](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="73aa6-103">Ends a bulk copy from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performed with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73aa6-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="73aa6-104">Syntax</span></span>  
  
```  
  
DBINT bcp_done (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="73aa6-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="73aa6-105">Arguments</span></span>  
 <span data-ttu-id="73aa6-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="73aa6-106">*hdbc*</span></span>  
 <span data-ttu-id="73aa6-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="73aa6-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="73aa6-108">Retours</span><span class="sxs-lookup"><span data-stu-id="73aa6-108">Returns</span></span>  
 <span data-ttu-id="73aa6-109">Le nombre de lignes enregistrées de manière permanente après le dernier appel à [bcp_batch](bcp-batch.md) , ou -1 en cas d'erreur.</span><span class="sxs-lookup"><span data-stu-id="73aa6-109">The number of rows permanently saved after the last call to [bcp_batch](bcp-batch.md) or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73aa6-110">Notes</span><span class="sxs-lookup"><span data-stu-id="73aa6-110">Remarks</span></span>  
 <span data-ttu-id="73aa6-111">Appelez **bcp_done** après le dernier appel à [bcp_sendrow](bcp-sendrow.md) ou [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="73aa6-111">Call **bcp_done** after the last call to [bcp_sendrow](bcp-sendrow.md) or [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="73aa6-112">L'échec de l'appel à **bcp_done** après la copie de toutes les données génère des erreurs.</span><span class="sxs-lookup"><span data-stu-id="73aa6-112">Failure to call **bcp_done** after copying all data results in errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73aa6-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="73aa6-113">See Also</span></span>  
 [<span data-ttu-id="73aa6-114">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="73aa6-114">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
