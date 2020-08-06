---
title: Utilisation d’SQL Server jeux de résultats par défaut | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetStmtAttr function
- ODBC cursors, default result sets
- cursors [ODBC], default result sets
- default result sets
- result sets [ODBC], default
- ODBC applications, cursors
ms.assetid: ee1db3e5-60eb-4425-8a6b-977eeced3f98
author: rothja
ms.author: jroth
ms.openlocfilehash: 18cd10dd95329f68a42497d2bea5ce63f345ceff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603513"
---
# <a name="using-sql-server-default-result-sets"></a><span data-ttu-id="02797-102">Utilisation de jeux de résultats SQL Server par défaut</span><span class="sxs-lookup"><span data-stu-id="02797-102">Using SQL Server Default Result Sets</span></span>
  <span data-ttu-id="02797-103">Les attributs de curseur ODBC par défaut sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="02797-103">The default ODBC cursor attributes are:</span></span>  
  
```  
SQLSetStmtAttr(hstmt, SQL_ATTR_CURSOR_TYPE, SQL_CURSOR_FORWARD_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_CONCURRENCY, SQL_CONCUR_READ_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_ARRAY_SIZE, 1, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="02797-104">Chaque fois que ces attributs sont définis sur leurs valeurs par défaut, le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client utilise un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] jeu de résultats par défaut.</span><span class="sxs-lookup"><span data-stu-id="02797-104">Whenever these attributes are set to their defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set.</span></span> <span data-ttu-id="02797-105">Les jeux de résultats par défaut peuvent être utilisés pour toute instruction SQL prise en charge par [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et s'avèrent la méthode de transfert la plus efficace d'un jeu de résultats entier au client.</span><span class="sxs-lookup"><span data-stu-id="02797-105">Default result sets can be used for any SQL statement supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and are the most efficient method of transferring an entire result set to the client.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]<span data-ttu-id="02797-106">a introduit la prise en charge de MARS (Multiple Active Result Sets); les applications peuvent désormais avoir plusieurs jeux de résultats par défaut actifs par connexion.</span><span class="sxs-lookup"><span data-stu-id="02797-106">introduced support for multiple active result sets (MARS); applications can now have more than one active default result set per connection.</span></span> <span data-ttu-id="02797-107">MARS n'est pas activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="02797-107">MARS is not enabled by default.</span></span>  
  
 <span data-ttu-id="02797-108">Avant [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], les jeux de résultats par défaut ne prenaient pas en charge plusieurs instructions actives sur la même connexion.</span><span class="sxs-lookup"><span data-stu-id="02797-108">Before [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], default result sets did not support multiple active statements on the same connection.</span></span> <span data-ttu-id="02797-109">Une fois qu'une instruction SQL était exécutée sur une connexion, le serveur n'acceptait pas de commandes (sauf une demande d'annulation du reste du jeu de résultats) du client sur cette connexion tant que toutes les lignes du jeu de résultats n'avaient pas été traitées.</span><span class="sxs-lookup"><span data-stu-id="02797-109">After an SQL statement is executed on a connection, the server does not accept commands (except a request to cancel the rest of the result set) from the client on that connection until all the rows in the result set have been processed.</span></span> <span data-ttu-id="02797-110">Pour annuler le reste d’un jeu de résultats partiellement traité, appelez [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) ou [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) avec le paramètre *fOption* défini sur SQL_CLOSE.</span><span class="sxs-lookup"><span data-stu-id="02797-110">To cancel the remainder of a partially processed result set, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with the *fOption* parameter set to SQL_CLOSE.</span></span> <span data-ttu-id="02797-111">Pour terminer un jeu de résultats partiellement traité et tester la présence d’un autre jeu de résultats, appelez [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="02797-111">To finish a partially processed result set and test for the presence of another result set, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span></span> <span data-ttu-id="02797-112">Si une application ODBC tente une commande sur un handle de connexion avant qu’un jeu de résultats par défaut ait été complètement traité, l’appel génère SQL_ERROR et un appel à **SQLGetDiagRec** retourne :</span><span class="sxs-lookup"><span data-stu-id="02797-112">If an ODBC application attempts a command on a connection handle before a default result set has been completely processed, the call generates SQL_ERROR and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState: "HY000", pfNativeError: 0  
szErrorMsg: "[Microsoft][SQL Server Native Client]  
                Connection is busy with results for another hstmt."  
```  
  
## <a name="see-also"></a><span data-ttu-id="02797-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02797-113">See Also</span></span>  
 [<span data-ttu-id="02797-114">Comment les curseurs sont implémentés</span><span class="sxs-lookup"><span data-stu-id="02797-114">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
