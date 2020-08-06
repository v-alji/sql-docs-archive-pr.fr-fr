---
title: Prise en charge des transactions distribuées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- distributed transactions [OLE DB]
- MS DTC
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
- ITransactionJoin interface
- MS DTC, about distributed transaction support
ms.assetid: d250b43b-9260-4ea4-90cc-57d9a2f67ea7
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a30a44dc007852922aa71685728b26e5bb872c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706407"
---
# <a name="supporting-distributed-transactions"></a><span data-ttu-id="fb500-102">Prise en charge des transactions distribuées</span><span class="sxs-lookup"><span data-stu-id="fb500-102">Supporting Distributed Transactions</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="fb500-103">Les consommateurs du fournisseur OLE DB Native Client peuvent utiliser la méthode **ITransactionJoin :: JoinTransaction** pour participer à une transaction distribuée coordonnée par Microsoft Distributed Transaction Coordinator (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="fb500-103">Native Client OLE DB provider consumers can use the **ITransactionJoin::JoinTransaction** method to participate in a distributed transaction coordinated by Microsoft Distributed Transaction Coordinator (MS DTC).</span></span>  
  
 <span data-ttu-id="fb500-104">MS DTC expose les objets COM qui permettent aux clients d'initialiser des transactions coordonnées et d'y participer sur plusieurs connexions à diverses banques de données.</span><span class="sxs-lookup"><span data-stu-id="fb500-104">MS DTC exposes COM objects that allow clients to initiate and participate in coordinated transactions across multiple connections to a variety of data stores.</span></span> <span data-ttu-id="fb500-105">Pour lancer une transaction, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consommateur du fournisseur OLE DB Native Client utilise l’interface MS DTC **ITransactionDispenser** .</span><span class="sxs-lookup"><span data-stu-id="fb500-105">To initiate a transaction, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses the MS DTC **ITransactionDispenser** interface.</span></span> <span data-ttu-id="fb500-106">Le membre **BeginTransaction** de **ITransactionDispenser** retourne une référence sur un objet de transaction distribué.</span><span class="sxs-lookup"><span data-stu-id="fb500-106">The **BeginTransaction** member of **ITransactionDispenser** returns a reference on a distributed transaction object.</span></span> <span data-ttu-id="fb500-107">Cette référence est passée au [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client à l’aide de **JoinTransaction**.</span><span class="sxs-lookup"><span data-stu-id="fb500-107">This reference is passed to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider using **JoinTransaction**.</span></span>  
  
 <span data-ttu-id="fb500-108">MS DTC prend en charge l'abandon et la validation asynchrones sur les transactions distribuées.</span><span class="sxs-lookup"><span data-stu-id="fb500-108">MS DTC supports asynchronous commit and abort on distributed transactions.</span></span> <span data-ttu-id="fb500-109">Pour la notification sur l’état de transaction asynchrone, le consommateur implémente l’interface **ITransactionOutcomeEvents** et connecte l’interface à un objet de transaction MS DTC.</span><span class="sxs-lookup"><span data-stu-id="fb500-109">For notification on asynchronous transaction status, the consumer implements the **ITransactionOutcomeEvents** interface and connects the interface to an MS DTC transaction object.</span></span>  
  
 <span data-ttu-id="fb500-110">Pour les transactions distribuées, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client implémente les paramètres **ITransactionJoin :: JoinTransaction** comme suit.</span><span class="sxs-lookup"><span data-stu-id="fb500-110">For distributed transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransactionJoin::JoinTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="fb500-111">Paramètre</span><span class="sxs-lookup"><span data-stu-id="fb500-111">Parameter</span></span>|<span data-ttu-id="fb500-112">Description</span><span class="sxs-lookup"><span data-stu-id="fb500-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb500-113">*punkTransactionCoord*</span><span class="sxs-lookup"><span data-stu-id="fb500-113">*punkTransactionCoord*</span></span>|<span data-ttu-id="fb500-114">Pointeur vers un objet de transaction MS DTC.</span><span class="sxs-lookup"><span data-stu-id="fb500-114">A pointer to an MS DTC transaction object.</span></span>|  
|<span data-ttu-id="fb500-115">*IsoLevel*</span><span class="sxs-lookup"><span data-stu-id="fb500-115">*IsoLevel*</span></span>|<span data-ttu-id="fb500-116">Ignoré par le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="fb500-116">Ignored by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="fb500-117">Le niveau d'isolation pour les transactions coordonnées MS DTC est déterminé lorsque le consommateur acquiert un objet de transaction à partir de MS DTC.</span><span class="sxs-lookup"><span data-stu-id="fb500-117">The isolation level for MS DTC-coordinated transactions is determined when the consumer acquires a transaction object from MS DTC.</span></span>|  
|<span data-ttu-id="fb500-118">*IsoFlags*</span><span class="sxs-lookup"><span data-stu-id="fb500-118">*IsoFlags*</span></span>|<span data-ttu-id="fb500-119">Doit être égal à 0.</span><span class="sxs-lookup"><span data-stu-id="fb500-119">Must be 0.</span></span> <span data-ttu-id="fb500-120">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client retourne XACT_E_NOISORETAIN si une autre valeur est spécifiée par le consommateur.</span><span class="sxs-lookup"><span data-stu-id="fb500-120">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOISORETAIN if any other value is specified by the consumer.</span></span>|  
|<span data-ttu-id="fb500-121">*POtherOptions*</span><span class="sxs-lookup"><span data-stu-id="fb500-121">*POtherOptions*</span></span>|<span data-ttu-id="fb500-122">Si la valeur n’est pas NULL, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client demande l’objet d’options à partir de l’interface.</span><span class="sxs-lookup"><span data-stu-id="fb500-122">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="fb500-123">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client retourne XACT_E_NOTIMEOUT si le membre *ulTimeout* de l’objet d’options n’est pas égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="fb500-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="fb500-124">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client ignore la valeur du membre *szDescription* .</span><span class="sxs-lookup"><span data-stu-id="fb500-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
  
 <span data-ttu-id="fb500-125">Cet exemple coordonne la transaction à l'aide de MS DTC.</span><span class="sxs-lookup"><span data-stu-id="fb500-125">This example coordinates transaction by using MS DTC.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*       pIDBCreateSession   = NULL;  
ITransactionJoin*       pITransactionJoin   = NULL;  
IDBCreateCommand*       pIDBCreateCommand   = NULL;  
IRowset*                pIRowset            = NULL;  
  
// Transaction dispenser and transaction from MS DTC.  
ITransactionDispenser*  pITransactionDispenser = NULL;  
ITransaction*           pITransaction       = NULL;  
  
    HRESULT             hr;  
  
// Get the command creation interface for the session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
// Get a transaction dispenser object from MS DTC and  
// start a transaction.  
if (FAILED(hr = DtcGetTransactionManager(NULL, NULL,  
    IID_ITransactionDispenser, 0, 0, NULL,  
    (void**) &pITransactionDispenser)))  
    {  
    // Process error message from MS DTC, release any references,  
    // and then return.  
    }  
if (FAILED(hr = pITransactionDispenser->BeginTransaction(  
    NULL, ISOLATIONLEVEL_READCOMMITTED, ISOFLAG_RETAIN_DONTCARE,  
    NULL, &pITransaction)))  
    {  
    // Process error message from MS DTC, release any references,  
    // and then return.  
    }  
  
// Join the transaction.  
if (FAILED(pIDBCreateCommand->QueryInterface(IID_ITransactionJoin,  
    (void**) &pITransactionJoin)))  
    {  
    // Process failure to get an interface, release any references, and  
    // then return.  
    }  
if (FAILED(pITransactionJoin->JoinTransaction(  
    (IUnknown*) pITransaction, 0, 0, NULL)))  
    {  
    // Process join failure, release any references, and then return.  
    }  
  
// Get data into a rowset, then update the data. Functions are not  
// illustrated in this example.  
if (FAILED(hr = ExecuteCommand(pIDBCreateCommand, &pIRowset)))  
    {  
    // Release any references and return.  
    }  
  
// If rowset data update fails, then terminate the transaction, else  
// commit. The example doesn't retain the rowset.  
if (FAILED(hr = UpdateDataInRowset(pIRowset, bDelayedUpdate)))  
    {  
    // Get error from update, then abort.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, 0, 0)))  
        {  
        // Get error from failed commit.  
        //  
        // If a distributed commit fails, application logic could  
        // analyze failure and retry. In this example, terminate. The   
        // consumer must resolve this somehow.  
        pITransaction->Abort(NULL, FALSE, FALSE);  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Un-enlist from the distributed transaction by setting   
// the transaction object pointer to NULL.  
if (FAILED(pITransactionJoin->JoinTransaction(  
    (IUnknown*) NULL, 0, 0, NULL)))  
    {  
    // Process failure, and then return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb500-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb500-126">See Also</span></span>  
 [<span data-ttu-id="fb500-127">Transactions</span><span class="sxs-lookup"><span data-stu-id="fb500-127">Transactions</span></span>](transactions.md)  
  
  
