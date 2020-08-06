---
title: Lots d’instructions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC], batches
- batches [ODBC]
- ODBC applications, statements
- multiple statements, batches
- SQLMoreResults function
- SQLExecDirect function
ms.assetid: 057d7c1c-1428-4780-9447-a002ea741188
author: rothja
ms.author: jroth
ms.openlocfilehash: 4818b67766dafe851035041c8fd5137a0dfade73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600864"
---
# <a name="batches-of-statements"></a><span data-ttu-id="24f2b-102">Lots d'instructions</span><span class="sxs-lookup"><span data-stu-id="24f2b-102">Batches of Statements</span></span>
  <span data-ttu-id="24f2b-103">Un lot d' [!INCLUDE[tsql](../../../includes/tsql-md.md)] instructions contient plusieurs instructions, séparées par un point-virgule (;), créé dans une chaîne unique transmise à la [fonction](https://go.microsoft.com/fwlink/?LinkId=59360) **SQLExecDirect** ou SQLPrepare.</span><span class="sxs-lookup"><span data-stu-id="24f2b-103">A batch of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements contains two or more statements, separated by a semicolon (;), built into a single string passed to **SQLExecDirect** or [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span> <span data-ttu-id="24f2b-104">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="24f2b-104">For example:</span></span>  
  
```  
SQLExecDirect(hstmt,   
    "SELECT * FROM Authors; SELECT * FROM Titles",  
    SQL_NTS);  
```  
  
 <span data-ttu-id="24f2b-105">Les lots peuvent se révéler plus efficaces que la soumission des instructions séparément car le trafic réseau est souvent réduit.</span><span class="sxs-lookup"><span data-stu-id="24f2b-105">Batches can be more efficient than submitting statements separately because network traffic is often reduced.</span></span> <span data-ttu-id="24f2b-106">Utilisez [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) pour être positionné sur le jeu de résultats suivant lorsque vous avez terminé avec le jeu de résultats actuel.</span><span class="sxs-lookup"><span data-stu-id="24f2b-106">Use [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to get positioned on the next result set when finished with the current result set.</span></span>  
  
 <span data-ttu-id="24f2b-107">Les lots peuvent toujours être utilisés lorsque les attributs de curseur ODBC sont définis sur les valeurs par défaut d'un curseur avant uniquement en lecture seule avec une taille d'ensemble de lignes de 1.</span><span class="sxs-lookup"><span data-stu-id="24f2b-107">Batches can always be used when the ODBC cursor attributes are set to the defaults of a forward-only, read-only cursor with a rowset size of 1.</span></span>  
  
 <span data-ttu-id="24f2b-108">Si un lot est exécuté lors de l'utilisation de curseurs côté serveur contre [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], le curseur côté serveur est converti implicitement en un jeu de résultats par défaut.</span><span class="sxs-lookup"><span data-stu-id="24f2b-108">If a batch is executed when using server cursors against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="24f2b-109">**SQLExecDirect** ou **SQLExecute** retournent SQL_SUCCESS_WITH_INFO, et un appel à **SQLGetDiagRec** retourne :</span><span class="sxs-lookup"><span data-stu-id="24f2b-109">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", pfNativeError = 0  
szErrorMsg = "[Microsoft][SQL Server Native Server Native Client]Cursor type changed."  
```  
  
## <a name="see-also"></a><span data-ttu-id="24f2b-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24f2b-110">See Also</span></span>  
 [<span data-ttu-id="24f2b-111">Exécution d’instructions &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="24f2b-111">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
