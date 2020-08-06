---
title: Accès concurrentiel au curseur (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- concurrency [ODBC]
- cursors [ODBC], concurrency
- ODBC cursors, concurrency
ms.assetid: 68228ece-cbf1-4f19-bfdc-053884c1af48
author: rothja
ms.author: jroth
ms.openlocfilehash: c47f24152978fedf8f2c3d49ec3b721969712814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612297"
---
# <a name="cursor-concurrency-odbc"></a><span data-ttu-id="47bdf-102">Accès concurrentiel au curseur (ODBC)</span><span class="sxs-lookup"><span data-stu-id="47bdf-102">Cursor Concurrency (ODBC)</span></span>
  <span data-ttu-id="47bdf-103">Les opérations de curseur, comme les types de curseurs, sont affectées par les options d'accès concurrentiel définies par l'application.</span><span class="sxs-lookup"><span data-stu-id="47bdf-103">Cursor operations, like cursor types, are affected by the concurrency options set by the application.</span></span> <span data-ttu-id="47bdf-104">Les options d’accès concurrentiel sont définies à l’aide de l’option SQL_ATTR_CONCURRENCY de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="47bdf-104">Concurrency options are set using the SQL_ATTR_CONCURRENCY option of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="47bdf-105">Les types d'accès concurrentiel sont :</span><span class="sxs-lookup"><span data-stu-id="47bdf-105">The concurrency types are:</span></span>  
  
-   <span data-ttu-id="47bdf-106">Lecture seule (SQL_CONCUR_READONLY)</span><span class="sxs-lookup"><span data-stu-id="47bdf-106">Read-only (SQL_CONCUR_READONLY)</span></span>  
  
-   <span data-ttu-id="47bdf-107">Valeurs (SQL_CONCUR_VALUES)</span><span class="sxs-lookup"><span data-stu-id="47bdf-107">Values (SQL_CONCUR_VALUES)</span></span>  
  
-   <span data-ttu-id="47bdf-108">Version de ligne (SQL_CONCUR_ROWVER)</span><span class="sxs-lookup"><span data-stu-id="47bdf-108">Row version (SQL_CONCUR_ROWVER)</span></span>  
  
-   <span data-ttu-id="47bdf-109">Verrou (SQL_CONCUR_LOCK)</span><span class="sxs-lookup"><span data-stu-id="47bdf-109">Lock (SQL_CONCUR_LOCK)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47bdf-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47bdf-110">See Also</span></span>  
 [<span data-ttu-id="47bdf-111">Propriétés de curseur</span><span class="sxs-lookup"><span data-stu-id="47bdf-111">Cursor Properties</span></span>](cursor-properties.md)  
  
  
