---
title: Exécution de transactions distribuées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, performing distributed transactions
- SQL Server Native Client ODBC driver, transactions
- distributed transactions [ODBC]
- transactions [ODBC]
- ODBC, transactions
ms.assetid: 2c17fba0-7a3c-453c-91b7-f801e7b39ccb
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ec23fd1883749e35e67f888e26bdf031ccf7fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602805"
---
# <a name="performing-distributed-transactions"></a><span data-ttu-id="4a7fa-102">Exécution de transactions distribuées</span><span class="sxs-lookup"><span data-stu-id="4a7fa-102">Performing Distributed Transactions</span></span>
  <span data-ttu-id="4a7fa-103">Microsoft Distributed Transaction Coordinator (MS DTC) permet aux applications d'étendre des transactions à deux instances ou plus de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a7fa-103">The Microsoft Distributed Transaction Coordinator (MS DTC) allows applications to extend transactions across two or more instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4a7fa-104">Il permet également aux applications de participer à des transactions gérées par des gestionnaires de transactions qui respectent la norme XA DTP d'Open Group.</span><span class="sxs-lookup"><span data-stu-id="4a7fa-104">It also allows applications to participate in transactions managed by transaction managers that comply with the Open Group DTP XA standard.</span></span>  
  
 <span data-ttu-id="4a7fa-105">Normalement, toutes les commandes de gestion des transactions sont envoyées par l'intermédiaire du pilote ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client au serveur.</span><span class="sxs-lookup"><span data-stu-id="4a7fa-105">Normally, all transaction management commands are sent through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to the server.</span></span> <span data-ttu-id="4a7fa-106">L’application démarre une transaction en appelant [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) avec le mode de validation automatique désactivé.</span><span class="sxs-lookup"><span data-stu-id="4a7fa-106">The application starts a transaction by calling [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) with the autocommit mode turned off.</span></span> <span data-ttu-id="4a7fa-107">L’application effectue ensuite les mises à jour comprenant la transaction et appelle [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) avec l’option SQL_COMMIT ou SQL_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="4a7fa-107">The application then performs the updates comprising the transaction and calls [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) with either the SQL_COMMIT or SQL_ROLLBACK option.</span></span>  
  
 <span data-ttu-id="4a7fa-108">Toutefois, lorsque vous utilisez MS DTC, MS DTC devient le gestionnaire de transactions et l’application n’utilise plus **SQLEndTran**.</span><span class="sxs-lookup"><span data-stu-id="4a7fa-108">When using MS DTC, however, MS DTC becomes the transaction manager and the application no longer uses **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="4a7fa-109">Une fois inscrit dans une transaction distribuée, puis inscrit dans une deuxième transaction distribuée, le pilote [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC fait défection dans la transaction distribuée d'origine et s'inscrit dans la nouvelle transaction.</span><span class="sxs-lookup"><span data-stu-id="4a7fa-109">When enlisted in a distributed transaction, and then enlist in a second distributed transaction, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver defects from the original distributed transaction and enlists in the new transaction.</span></span> <span data-ttu-id="4a7fa-110">Pour plus d’informations, consultez le [Guide de référence du programmeur DTC](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span><span class="sxs-lookup"><span data-stu-id="4a7fa-110">For more information, see [DTC Programmer's Reference](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a7fa-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a7fa-111">See Also</span></span>  
 [<span data-ttu-id="4a7fa-112">Exécution de transactions &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4a7fa-112">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
