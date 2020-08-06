---
title: SQLSTATE (codes d’erreur ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- ODBC error handling, cause information
- messages [ODBC], cause information
- SQLSTATEs
- errors [ODBC], cause information
ms.assetid: 84cce528-edb0-473f-a85f-3eb87fbe2cf3
author: rothja
ms.author: jroth
ms.openlocfilehash: ff3ec0a5cdc8f24f34e42849f7c8f6d1d9d41478
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599990"
---
# <a name="sqlstate-odbc-error-codes"></a><span data-ttu-id="996a3-102">SQLSTATE (codes d'erreur ODBC)</span><span class="sxs-lookup"><span data-stu-id="996a3-102">SQLSTATE (ODBC Error Codes)</span></span>
  <span data-ttu-id="996a3-103">SQLSTATE fournit des informations détaillées à propos de la cause d'un avertissement ou d'une erreur.</span><span class="sxs-lookup"><span data-stu-id="996a3-103">SQLSTATE provides detailed information about the cause of a warning or error.</span></span> <span data-ttu-id="996a3-104">Pour les erreurs qui se produisent dans la source de données détectées et retournées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client mappe le numéro d’erreur native retourné au SQLSTATE approprié.</span><span class="sxs-lookup"><span data-stu-id="996a3-104">For errors that occur in the data source detected and returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps the returned native error number to the appropriate SQLSTATE.</span></span> <span data-ttu-id="996a3-105">Si aucun code d’erreur ODBC n’est mappé à un numéro d’erreur natif, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client retourne SQLSTATE 42000 (« erreur de syntaxe ou violation d’accès »).</span><span class="sxs-lookup"><span data-stu-id="996a3-105">If a native error number does not have an ODBC error code to map to, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns SQLSTATE 42000 ("syntax error or access violation").</span></span> <span data-ttu-id="996a3-106">Pour les erreurs détectées par le pilote, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client génère le SQLSTATE approprié.</span><span class="sxs-lookup"><span data-stu-id="996a3-106">For errors that are detected by the driver, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver generates the appropriate SQLSTATE.</span></span>  
  
 <span data-ttu-id="996a3-107">Pour plus d'informations sur les codes d'erreur d'état, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="996a3-107">For more information about the state error codes, see the following topics:</span></span>  
  
-   [<span data-ttu-id="996a3-108">Annexe A : Codes d’erreur ODBC</span><span class="sxs-lookup"><span data-stu-id="996a3-108">Appendix A: ODBC Error Codes</span></span>](https://go.microsoft.com/fwlink/?LinkId=89356)  
  
-   [<span data-ttu-id="996a3-109">Mappages SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="996a3-109">SQLSTATE Mappings</span></span>](https://go.microsoft.com/fwlink/?LinkId=89355)  
  
## <a name="see-also"></a><span data-ttu-id="996a3-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="996a3-110">See Also</span></span>  
 [<span data-ttu-id="996a3-111">Gestion des erreurs et des messages</span><span class="sxs-lookup"><span data-stu-id="996a3-111">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
