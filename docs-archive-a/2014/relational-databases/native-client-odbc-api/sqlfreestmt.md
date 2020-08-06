---
title: SQLFreeStmt | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFreeStmt function
ms.assetid: d9666d0b-3446-480e-bf1a-10b01213e411
author: rothja
ms.author: jroth
ms.openlocfilehash: d38237b53ed994fd3272f9e129564320f88c6e37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603964"
---
# <a name="sqlfreestmt"></a><span data-ttu-id="459be-102">SQLFreeStmt</span><span class="sxs-lookup"><span data-stu-id="459be-102">SQLFreeStmt</span></span>
  <span data-ttu-id="459be-103">**SQLFreeStmt** n'est pas recommandé dans ODBC 3.0 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="459be-103">**SQLFreeStmt** is not recommended in ODBC 3.0 and later.</span></span> <span data-ttu-id="459be-104">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client prend en charge toutes les valeurs *Option* définies pour **SQLFreeStmt**.</span><span class="sxs-lookup"><span data-stu-id="459be-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports all defined *Option* values for **SQLFreeStmt**.</span></span> <span data-ttu-id="459be-105">Toutefois, [SQLCloseCursor](sqlclosecursor.md), [SQLBindParameter](sqlbindparameter.md), [SQLBindCol](sqlbindcol.md), **SQLSetDescField**et [SQLFreeHandle](sqlfreehandle.md) remplacent ou dupliquent la fonction de **SQLFreeStmt** et doivent être utilisés à la place.</span><span class="sxs-lookup"><span data-stu-id="459be-105">However, [SQLCloseCursor](sqlclosecursor.md), [SQLBindParameter](sqlbindparameter.md), [SQLBindCol](sqlbindcol.md), **SQLSetDescField**, and [SQLFreeHandle](sqlfreehandle.md) replace or duplicate the function of **SQLFreeStmt** and should be used instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="459be-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="459be-106">See Also</span></span>  
 <span data-ttu-id="459be-107">[SQLFreeStmt fonction)](https://go.microsoft.com/fwlink/?LinkId=59346) </span><span class="sxs-lookup"><span data-stu-id="459be-107">[SQLFreeStmt Function](https://go.microsoft.com/fwlink/?LinkId=59346) </span></span>  
 [<span data-ttu-id="459be-108">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="459be-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
