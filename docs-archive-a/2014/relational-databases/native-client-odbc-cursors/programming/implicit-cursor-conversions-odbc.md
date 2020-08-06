---
title: Conversions de curseurs implicites (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, implicit cursor conversions
- implicit cursor conversions
- cursors [ODBC], implicit cursor conversions
ms.assetid: fe29a58d-8448-4512-9ffd-b414784ba338
author: rothja
ms.author: jroth
ms.openlocfilehash: ff8350c71a853e39ff1d35a1f3fba6e8e1944934
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612295"
---
# <a name="implicit-cursor-conversions-odbc"></a><span data-ttu-id="54d59-102">Conversions de curseurs implicites (ODBC)</span><span class="sxs-lookup"><span data-stu-id="54d59-102">Implicit Cursor Conversions (ODBC)</span></span>
  <span data-ttu-id="54d59-103">Les applications peuvent demander un type de curseur à l’aide de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) , puis exécuter une instruction SQL qui n’est pas prise en charge par les curseurs côté serveur du type demandé.</span><span class="sxs-lookup"><span data-stu-id="54d59-103">Applications can request a cursor type through [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) and then execute an SQL statement that is not supported by server cursors of the type requested.</span></span> <span data-ttu-id="54d59-104">Un appel à **SQLExecute** ou à **SQLExecDirect** retourne SQL_SUCCESS_WITH_INFO et **SQLGetDiagRec** retourne :</span><span class="sxs-lookup"><span data-stu-id="54d59-104">A call to **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", *pfNativeError = 0,  
szErrorMsg="[Microsoft][SQL Server Native Client] Cursor type changed"  
```  
  
 <span data-ttu-id="54d59-105">L’application peut déterminer le type de curseur qui est maintenant utilisé en appelant **SQLGetStmtOption** défini sur SQL_CURSOR_TYPE.</span><span class="sxs-lookup"><span data-stu-id="54d59-105">The application can determine what type of cursor is now being used by calling **SQLGetStmtOption** set to SQL_CURSOR_TYPE.</span></span> <span data-ttu-id="54d59-106">La conversion de type de curseur s'applique à une seule instruction.</span><span class="sxs-lookup"><span data-stu-id="54d59-106">The cursor type conversion applies to only one statement.</span></span> <span data-ttu-id="54d59-107">**SQLExecDirect** ou **SQLExecute** suivant seront effectués à l’aide des paramètres de curseur d’instruction d’origine.</span><span class="sxs-lookup"><span data-stu-id="54d59-107">The next **SQLExecDirect** or **SQLExecute** will be done using the original statement cursor settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d59-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54d59-108">See Also</span></span>  
 [<span data-ttu-id="54d59-109">Détails de programmation de curseur &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="54d59-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
