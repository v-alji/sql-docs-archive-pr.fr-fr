---
title: SQLCancel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLCancel function
ms.assetid: d4c965ae-c1ac-4e9d-b4b9-32b561401106
author: rothja
ms.author: jroth
ms.openlocfilehash: dc3d86229501f80b25fb077788d1835a5f4f5c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604444"
---
# <a name="sqlcancel"></a><span data-ttu-id="bc653-102">SQLCancel</span><span class="sxs-lookup"><span data-stu-id="bc653-102">SQLCancel</span></span>
  <span data-ttu-id="bc653-103">La rubrique [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) indique que dans ODBC 2. x, si une application appelle `SQLCancel` quand aucun traitement n’est effectué sur l’instruction, `SQLCancel` a le même effet qu' `SQLFreeStmt` avec l' `SQL_CLOSE` option ; ce comportement est défini uniquement pour l’exhaustivité et les applications doivent appeler `SQLFreeStmt` ou fermer les `SQLCloseCursor` curseurs.</span><span class="sxs-lookup"><span data-stu-id="bc653-103">The [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) topic says that in ODBC 2.x, if an application calls `SQLCancel` when no processing is being done on the statement, `SQLCancel` has the same effect as `SQLFreeStmt` with the `SQL_CLOSE` option; this behavior is defined only for completeness and applications should call `SQLFreeStmt` or `SQLCloseCursor` to close cursors.</span></span> <span data-ttu-id="bc653-104">Mais même si votre application [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client définit 3.5.x ou version ultérieure pour l'API ODBC, la fonction `SQLCancel` utilisera le comportement ODBC 2.x.</span><span class="sxs-lookup"><span data-stu-id="bc653-104">But even if your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client application sets the ODBC API version to be 3.5.x or later, the `SQLCancel` function will use the ODBC 2.x behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc653-105">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc653-105">See Also</span></span>  
 <span data-ttu-id="bc653-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span><span class="sxs-lookup"><span data-stu-id="bc653-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span></span>  
 [<span data-ttu-id="bc653-107">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="bc653-107">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
