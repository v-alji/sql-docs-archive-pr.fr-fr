---
title: Utiliser Microsoft Distributed Transaction Coordinator (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, using
ms.assetid: 12a275e1-8c7e-436d-8a4e-b7bee853b35c
author: rothja
ms.author: jroth
ms.openlocfilehash: f7b7da33066a9f4edd01037738ed91155340e6ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604430"
---
# <a name="use-microsoft-distributed-transaction-coordinator-odbc"></a><span data-ttu-id="ccef9-102">Utiliser Microsoft Distributed Transaction Coordinator (ODBC)</span><span class="sxs-lookup"><span data-stu-id="ccef9-102">Use Microsoft Distributed Transaction Coordinator (ODBC)</span></span>
    
### <a name="to-update-two-or-more-sql-servers-by-using-ms-dtc"></a><span data-ttu-id="ccef9-103">Pour mettre à jour plusieurs serveurs SQL en utilisant MS DTC</span><span class="sxs-lookup"><span data-stu-id="ccef9-103">To update two or more SQL Servers by using MS DTC</span></span>  
  
1.  <span data-ttu-id="ccef9-104">Connectez-vous à MS DTC en utilisant la fonction MS DTC OLE DtcGetTransactionManager.</span><span class="sxs-lookup"><span data-stu-id="ccef9-104">Connect to MS DTC by using the MS DTC OLE DtcGetTransactionManager function.</span></span> <span data-ttu-id="ccef9-105">Pour plus d'informations sur MS DTC, consultez Microsoft Distributed Transaction Coordinator.</span><span class="sxs-lookup"><span data-stu-id="ccef9-105">For information about MS DTC, see Microsoft Distributed Transaction Coordinator.</span></span>  
  
2.  <span data-ttu-id="ccef9-106">Appelez SQL DriverConnect une fois pour chaque connexion Microsoft SQL Server que vous souhaitez établir.</span><span class="sxs-lookup"><span data-stu-id="ccef9-106">Call SQL DriverConnect once for each Microsoft SQL Server connection you want to establish.</span></span>  
  
3.  <span data-ttu-id="ccef9-107">Appelez la fonction MS DTC OLE ITransactionDispenser::BeginTransaction pour commencer une transaction MS DTC et obtenir un objet Transaction qui représente la transaction.</span><span class="sxs-lookup"><span data-stu-id="ccef9-107">Call the MS DTC OLE ITransactionDispenser::BeginTransaction function to begin an MS DTC transaction and obtain a Transaction object that represents the transaction.</span></span>  
  
4.  <span data-ttu-id="ccef9-108">Appelez [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) une ou plusieurs fois pour chaque connexion ODBC que vous souhaitez inscrire dans la transaction MS DTC.</span><span class="sxs-lookup"><span data-stu-id="ccef9-108">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) one or more times for each ODBC connection you want to enlist in the MS DTC transaction.</span></span> <span data-ttu-id="ccef9-109">Le deuxième paramètre [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) doit être SQL_ATTR_ENLIST_IN_DTC et le troisième paramètre doit être l’objet Transaction (obtenu à l’Étape 3).</span><span class="sxs-lookup"><span data-stu-id="ccef9-109">[SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) second parameter must be SQL_ATTR_ENLIST_IN_DTC and third parameter must be the Transaction object (obtained in Step 3).</span></span>  
  
5.  <span data-ttu-id="ccef9-110">Appelez [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) une fois pour chaque serveur SQL Server à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="ccef9-110">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) once for each SQL Server you want to update.</span></span>  
  
6.  <span data-ttu-id="ccef9-111">Appelez la fonction MS DTC OLE ITransaction::Commit pour valider la transaction MS DTC.</span><span class="sxs-lookup"><span data-stu-id="ccef9-111">Call the MS DTC OLE ITransaction::Commit function to commit the MS DTC transaction.</span></span> <span data-ttu-id="ccef9-112">L'objet Transaction n'est plus valide.</span><span class="sxs-lookup"><span data-stu-id="ccef9-112">The Transaction object is no longer valid.</span></span>  
  
 <span data-ttu-id="ccef9-113">Pour effectuer une série de transactions MS DTC, répétez les Étapes 3 à 6.</span><span class="sxs-lookup"><span data-stu-id="ccef9-113">To perform a series of MS DTC transactions, repeat Steps 3 through 6.</span></span>  
  
 <span data-ttu-id="ccef9-114">Pour libérer la référence à l'objet Transaction, appelez la fonction MS DTC OLE ITransaction::Return.</span><span class="sxs-lookup"><span data-stu-id="ccef9-114">To release the reference to the Transaction object, call the MS DTC OLE ITransaction::Return function.</span></span>  
  
 <span data-ttu-id="ccef9-115">Pour utiliser une connexion ODBC avec une transaction MS DTC, puis utiliser la même connexion avec une transaction SQL Server locale, appelez [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) avec SQL_DTC_DONE.</span><span class="sxs-lookup"><span data-stu-id="ccef9-115">To use an ODBC connection with an MS DTC transaction, and then use the same connection with a local SQL Server transaction, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_DTC_DONE.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ccef9-116">Vous pouvez également appeler [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) puis [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) pour chaque SQL Server au lieu de les appeler comme suggéré précédemment aux Étapes 4 et 5.</span><span class="sxs-lookup"><span data-stu-id="ccef9-116">You can also call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) and [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) in turn for each SQL Server instead of calling them as suggested earlier in Steps 4 and 5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccef9-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ccef9-117">See Also</span></span>  
 [<span data-ttu-id="ccef9-118">Exécution de transactions &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ccef9-118">Performing Transactions &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
