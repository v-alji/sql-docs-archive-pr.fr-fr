---
title: Prise en charge des transactions locales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- autocommit mode
- transactions [OLE DB]
- ITransactionLocal interface
- SQL Server Native Client OLE DB provider, transactions
- local transactions [OLE DB]
ms.assetid: 78f2e5fc-b6fb-4eda-9f71-991a4d6c4902
author: rothja
ms.author: jroth
ms.openlocfilehash: a9bc11a038e56517aa42619117c371c1319b9ffe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612779"
---
# <a name="supporting-local-transactions"></a><span data-ttu-id="95d61-102">Prise en charge des transactions locales</span><span class="sxs-lookup"><span data-stu-id="95d61-102">Supporting Local Transactions</span></span>
  <span data-ttu-id="95d61-103">Une session délimite l’étendue de la transaction pour une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction locale du fournisseur OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="95d61-103">A session delimits transaction scope for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider local transaction.</span></span> <span data-ttu-id="95d61-104">Quand, à la direction d’un consommateur, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client soumet une requête à une instance connectée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la demande constitue une unité de travail pour le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="95d61-104">When, at the direction of a consumer, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider submits a request to a connected instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the request constitutes a unit of work for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="95d61-105">Les transactions locales encapsulent toujours une ou plusieurs unités de travail sur une seule [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session Native Client OLE DB fournisseur.</span><span class="sxs-lookup"><span data-stu-id="95d61-105">Local transactions always wrap one or more units of work on a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider session.</span></span>  
  
 <span data-ttu-id="95d61-106">En utilisant le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mode de validation automatique du fournisseur OLE DB Native Client par défaut, une unité de travail unique est traitée comme l’étendue d’une transaction locale.</span><span class="sxs-lookup"><span data-stu-id="95d61-106">Using the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider autocommit mode, a single unit of work is treated as the scope of a local transaction.</span></span> <span data-ttu-id="95d61-107">Une seule unité participe à la transaction locale.</span><span class="sxs-lookup"><span data-stu-id="95d61-107">Only one unit participates in the local transaction.</span></span> <span data-ttu-id="95d61-108">Lorsqu’une session est créée, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client commence une transaction pour la session.</span><span class="sxs-lookup"><span data-stu-id="95d61-108">When a session is created, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a transaction for the session.</span></span> <span data-ttu-id="95d61-109">Une fois que l'unité de travail a été exécutée avec succès, le travail est validé.</span><span class="sxs-lookup"><span data-stu-id="95d61-109">Upon successful completion of a work unit, the work is committed.</span></span> <span data-ttu-id="95d61-110">En cas d'échec, tout travail commencé est annulé et l'erreur est signalée au consommateur.</span><span class="sxs-lookup"><span data-stu-id="95d61-110">On failure, any work begun is rolled back and the error is reported to the consumer.</span></span> <span data-ttu-id="95d61-111">Dans les deux cas, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client commence une nouvelle transaction locale pour la session afin que tout le travail soit effectué dans une transaction.</span><span class="sxs-lookup"><span data-stu-id="95d61-111">In either case, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider begins a new local transaction for the session so that all work is conducted within a transaction.</span></span>  
  
 <span data-ttu-id="95d61-112">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consommateur du fournisseur OLE DB Native Client peut diriger un contrôle plus précis sur l’étendue de la transaction locale à l’aide de l’interface **ITransactionLocal** .</span><span class="sxs-lookup"><span data-stu-id="95d61-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer can direct more precise control over local transaction scope by using the **ITransactionLocal** interface.</span></span> <span data-ttu-id="95d61-113">Lorsqu’une session de consommateur démarre une transaction, toutes les unités de travail de la session entre le point de départ de la transaction et les appels éventuels de la méthode **Commit** ou **Abort** sont traités comme une unité atomique.</span><span class="sxs-lookup"><span data-stu-id="95d61-113">When a consumer session initiates a transaction, all session work units between the transaction start point and the eventual **Commit** or **Abort** method calls are treated as an atomic unit.</span></span> <span data-ttu-id="95d61-114">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client commence implicitement une transaction lorsqu’il y est invité par le consommateur.</span><span class="sxs-lookup"><span data-stu-id="95d61-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implicitly begins a transaction when directed to do so by the consumer.</span></span> <span data-ttu-id="95d61-115">Si le consommateur ne demande pas la rétention, la session revient au comportement parent du niveau de la transaction, soit le plus généralement le mode de validation automatique.</span><span class="sxs-lookup"><span data-stu-id="95d61-115">If the consumer does not request retention, the session reverts to parent transaction-level behavior, most commonly autocommit mode.</span></span>  
  
 <span data-ttu-id="95d61-116">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client prend en charge les paramètres **ITransactionLocal :: StartTransaction** comme suit.</span><span class="sxs-lookup"><span data-stu-id="95d61-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ITransactionLocal::StartTransaction** parameters as follows.</span></span>  
  
|<span data-ttu-id="95d61-117">Paramètre</span><span class="sxs-lookup"><span data-stu-id="95d61-117">Parameter</span></span>|<span data-ttu-id="95d61-118">Description</span><span class="sxs-lookup"><span data-stu-id="95d61-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95d61-119">*isoLevel*[in]</span><span class="sxs-lookup"><span data-stu-id="95d61-119">*isoLevel*[in]</span></span>|<span data-ttu-id="95d61-120">Niveau d'isolation à utiliser avec cette transaction.</span><span class="sxs-lookup"><span data-stu-id="95d61-120">The isolation level to be used with this transaction.</span></span> <span data-ttu-id="95d61-121">Dans les transactions locales, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client prend en charge les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="95d61-121">In local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the following:</span></span><br /><br /> <span data-ttu-id="95d61-122">-ISOLATIONLEVEL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="95d61-122">-   ISOLATIONLEVEL_UNSPECIFIED</span></span><br /><span data-ttu-id="95d61-123">-ISOLATIONLEVEL_CHAOS</span><span class="sxs-lookup"><span data-stu-id="95d61-123">-   ISOLATIONLEVEL_CHAOS</span></span><br /><span data-ttu-id="95d61-124">-ISOLATIONLEVEL_READUNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="95d61-124">-   ISOLATIONLEVEL_READUNCOMMITTED</span></span><br /><span data-ttu-id="95d61-125">-ISOLATIONLEVEL_READCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="95d61-125">-   ISOLATIONLEVEL_READCOMMITTED</span></span><br /><span data-ttu-id="95d61-126">-ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="95d61-126">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="95d61-127">-ISOLATIONLEVEL_CURSORSTABILITY</span><span class="sxs-lookup"><span data-stu-id="95d61-127">-   ISOLATIONLEVEL_CURSORSTABILITY</span></span><br /><span data-ttu-id="95d61-128">-ISOLATIONLEVEL_REPEATABLEREAD</span><span class="sxs-lookup"><span data-stu-id="95d61-128">-   ISOLATIONLEVEL_REPEATABLEREAD</span></span><br /><span data-ttu-id="95d61-129">-ISOLATIONLEVEL_SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="95d61-129">-   ISOLATIONLEVEL_SERIALIZABLE</span></span><br /><span data-ttu-id="95d61-130">-ISOLATIONLEVEL_ISOLATED</span><span class="sxs-lookup"><span data-stu-id="95d61-130">-   ISOLATIONLEVEL_ISOLATED</span></span><br /><span data-ttu-id="95d61-131">-ISOLATIONLEVEL_SNAPSHOT **Remarque :** à compter de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , ISOLATIONLEVEL_SNAPSHOT est valide pour l’argument *isoLevel* , que la gestion de version soit activée ou non pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="95d61-131">-   ISOLATIONLEVEL_SNAPSHOT **Note:**  Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], ISOLATIONLEVEL_SNAPSHOT is valid for the *isoLevel* argument whether or not versioning is enabled for the database.</span></span> <span data-ttu-id="95d61-132">Cependant, une erreur se produit si l'utilisateur essaie d'exécuter une instruction et que le suivi des versions n'est pas activé et/ou que la base de données n'est pas en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="95d61-132">However, an error will occur if the user attempts to execute a statement and versioning is not enabled and/or the database is not read-only.</span></span> <span data-ttu-id="95d61-133">De plus, l’erreur XACT_E_ISOLATIONLEVEL se produit si ISOLATIONLEVEL_SNAPSHOT est spécifié comme *isoLevel* lors de la connexion à une version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieure à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95d61-133">In addition, the error XACT_E_ISOLATIONLEVEL will occur if ISOLATIONLEVEL_SNAPSHOT is specified as the *isoLevel* when connected to a version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>|  
|<span data-ttu-id="95d61-134">*isoFlags*[in]</span><span class="sxs-lookup"><span data-stu-id="95d61-134">*isoFlags*[in]</span></span>|<span data-ttu-id="95d61-135">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client retourne une erreur pour toute valeur autre que zéro.</span><span class="sxs-lookup"><span data-stu-id="95d61-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns an error for any value other than zero.</span></span>|  
|<span data-ttu-id="95d61-136">*pOtherOptions*[in]</span><span class="sxs-lookup"><span data-stu-id="95d61-136">*pOtherOptions*[in]</span></span>|<span data-ttu-id="95d61-137">Si la valeur n’est pas NULL, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client demande l’objet d’options à partir de l’interface.</span><span class="sxs-lookup"><span data-stu-id="95d61-137">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider requests the options object from the interface.</span></span> <span data-ttu-id="95d61-138">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client retourne XACT_E_NOTIMEOUT si le membre *ulTimeout* de l’objet d’options n’est pas égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="95d61-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTIMEOUT if the options object's *ulTimeout* member is not zero.</span></span> <span data-ttu-id="95d61-139">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client ignore la valeur du membre *szDescription* .</span><span class="sxs-lookup"><span data-stu-id="95d61-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider ignores the value of the *szDescription* member.</span></span>|  
|<span data-ttu-id="95d61-140">*pulTransactionLevel*[out]</span><span class="sxs-lookup"><span data-stu-id="95d61-140">*pulTransactionLevel*[out]</span></span>|<span data-ttu-id="95d61-141">Si la valeur n’est pas NULL, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client retourne le niveau imbriqué de la transaction.</span><span class="sxs-lookup"><span data-stu-id="95d61-141">If not NULL, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns the nested level of the transaction.</span></span>|  
  
 <span data-ttu-id="95d61-142">Pour les transactions locales, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client implémente les paramètres **ITransaction :: Abort** comme suit.</span><span class="sxs-lookup"><span data-stu-id="95d61-142">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Abort** parameters as follows.</span></span>  
  
|<span data-ttu-id="95d61-143">Paramètre</span><span class="sxs-lookup"><span data-stu-id="95d61-143">Parameter</span></span>|<span data-ttu-id="95d61-144">Description</span><span class="sxs-lookup"><span data-stu-id="95d61-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95d61-145">*pboidReason*[in]</span><span class="sxs-lookup"><span data-stu-id="95d61-145">*pboidReason*[in]</span></span>|<span data-ttu-id="95d61-146">Ignoré s'il est défini.</span><span class="sxs-lookup"><span data-stu-id="95d61-146">Ignored if set.</span></span> <span data-ttu-id="95d61-147">Peut être égal à NULL en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="95d61-147">Can safely be NULL.</span></span>|  
|<span data-ttu-id="95d61-148">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="95d61-148">*fRetaining*[in]</span></span>|<span data-ttu-id="95d61-149">Lorsque la valeur est TRUE, une nouvelle transaction est commencée implicitement pour la session.</span><span class="sxs-lookup"><span data-stu-id="95d61-149">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="95d61-150">La transaction doit être validée ou terminée par le consommateur.</span><span class="sxs-lookup"><span data-stu-id="95d61-150">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="95d61-151">Quand la valeur est FALSe, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client revient en mode de validation automatique pour la session.</span><span class="sxs-lookup"><span data-stu-id="95d61-151">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="95d61-152">*fAsync*[in]</span><span class="sxs-lookup"><span data-stu-id="95d61-152">*fAsync*[in]</span></span>|<span data-ttu-id="95d61-153">L’abandon asynchrone n’est pas pris en charge par le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="95d61-153">Asynchronous abort is not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="95d61-154">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client retourne XACT_E_NOTSUPPORTED si la valeur n’est pas false.</span><span class="sxs-lookup"><span data-stu-id="95d61-154">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED if the value is not FALSE.</span></span>|  
  
 <span data-ttu-id="95d61-155">Pour les transactions locales, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client implémente les paramètres **ITransaction :: Commit** comme suit.</span><span class="sxs-lookup"><span data-stu-id="95d61-155">For local transactions, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements **ITransaction::Commit** parameters as follows.</span></span>  
  
|<span data-ttu-id="95d61-156">Paramètre</span><span class="sxs-lookup"><span data-stu-id="95d61-156">Parameter</span></span>|<span data-ttu-id="95d61-157">Description</span><span class="sxs-lookup"><span data-stu-id="95d61-157">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95d61-158">*fRetaining*[in]</span><span class="sxs-lookup"><span data-stu-id="95d61-158">*fRetaining*[in]</span></span>|<span data-ttu-id="95d61-159">Lorsque la valeur est TRUE, une nouvelle transaction est commencée implicitement pour la session.</span><span class="sxs-lookup"><span data-stu-id="95d61-159">When TRUE, a new transaction is implicitly begun for the session.</span></span> <span data-ttu-id="95d61-160">La transaction doit être validée ou terminée par le consommateur.</span><span class="sxs-lookup"><span data-stu-id="95d61-160">The transaction must be committed or terminated by the consumer.</span></span> <span data-ttu-id="95d61-161">Quand la valeur est FALSe, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client revient en mode de validation automatique pour la session.</span><span class="sxs-lookup"><span data-stu-id="95d61-161">When FALSE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reverts to autocommit mode for the session.</span></span>|  
|<span data-ttu-id="95d61-162">*grfTC*[in]</span><span class="sxs-lookup"><span data-stu-id="95d61-162">*grfTC*[in]</span></span>|<span data-ttu-id="95d61-163">Les retours asynchrones et de phase 1 ne sont pas pris en charge par le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="95d61-163">Asynchronous and phase one returns are not supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="95d61-164">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client retourne XACT_E_NOTSUPPORTED pour toute valeur autre que XACTTC_SYNC.</span><span class="sxs-lookup"><span data-stu-id="95d61-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns XACT_E_NOTSUPPORTED for any value other than XACTTC_SYNC.</span></span>|  
|<span data-ttu-id="95d61-165">*grfRM*[in]</span><span class="sxs-lookup"><span data-stu-id="95d61-165">*grfRM*[in]</span></span>|<span data-ttu-id="95d61-166">Doit être égal à 0.</span><span class="sxs-lookup"><span data-stu-id="95d61-166">Must be 0.</span></span>|  
  
 <span data-ttu-id="95d61-167">Les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ensembles de lignes du fournisseur Native Client OLE DB sur la session sont conservés lors d’une opération de validation ou d’abandon locale basée sur les valeurs des propriétés de l’ensemble de lignes DBPROP_ABORTPRESERVE et DBPROP_COMMITPRESERVE.</span><span class="sxs-lookup"><span data-stu-id="95d61-167">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are preserved on a local commit or abort operation based on the values of the rowset properties DBPROP_ABORTPRESERVE and DBPROP_COMMITPRESERVE.</span></span> <span data-ttu-id="95d61-168">Par défaut, ces propriétés sont VARIANT_FALSE et tous les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ensembles de lignes de fournisseur OLE DB Native Client de la session sont perdus après une opération d’abandon ou de validation.</span><span class="sxs-lookup"><span data-stu-id="95d61-168">By default, these properties are both VARIANT_FALSE and all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets on the session are lost following an abort or commit operation.</span></span>  
  
 <span data-ttu-id="95d61-169">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client n’implémente pas l’interface **ITransactionObject** .</span><span class="sxs-lookup"><span data-stu-id="95d61-169">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not implement the **ITransactionObject** interface.</span></span> <span data-ttu-id="95d61-170">La tentative d'un consommateur pour extraire une référence sur l'interface retourne E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="95d61-170">A consumer attempt to retrieve a reference on the interface returns E_NOINTERFACE.</span></span>  
  
 <span data-ttu-id="95d61-171">L’exemple suivant utilise **ITransactionLocal**.</span><span class="sxs-lookup"><span data-stu-id="95d61-171">This example uses **ITransactionLocal**.</span></span>  
  
```  
// Interfaces used in the example.  
IDBCreateSession*   pIDBCreateSession   = NULL;  
ITransaction*       pITransaction       = NULL;  
IDBCreateCommand*   pIDBCreateCommand   = NULL;  
IRowset*            pIRowset            = NULL;  
  
HRESULT             hr;  
  
// Get the command creation and local transaction interfaces for the  
// session.  
if (FAILED(hr = pIDBCreateSession->CreateSession(NULL,  
     IID_IDBCreateCommand, (IUnknown**) &pIDBCreateCommand)))  
    {  
    // Process error from session creation. Release any references and  
    // return.  
    }  
  
if (FAILED(hr = pIDBCreateCommand->QueryInterface(IID_ITransactionLocal,  
    (void**) &pITransaction)))  
    {  
    // Process error. Release any references and return.  
    }  
  
// Start the local transaction.  
if (FAILED(hr = ((ITransactionLocal*) pITransaction)->StartTransaction(  
    ISOLATIONLEVEL_REPEATABLEREAD, 0, NULL, NULL)))  
    {  
    // Process error from StartTransaction. Release any references and  
    // return.  
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
    // Get error from update, then terminate.  
    pITransaction->Abort(NULL, FALSE, FALSE);  
    }  
else  
    {  
    if (FAILED(hr = pITransaction->Commit(FALSE, XACTTC_SYNC, 0)))  
        {  
        // Get error from failed commit.  
        }  
    }  
  
if (FAILED(hr))  
    {  
    // Update of data or commit failed. Release any references and  
    // return.  
    }  
  
// Release any references and continue.  
```  
  
## <a name="see-also"></a><span data-ttu-id="95d61-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95d61-172">See Also</span></span>  
 <span data-ttu-id="95d61-173">[Transactions](transactions.md) </span><span class="sxs-lookup"><span data-stu-id="95d61-173">[Transactions](transactions.md) </span></span>  
 [<span data-ttu-id="95d61-174">Utilisation de l’isolation d’instantané</span><span class="sxs-lookup"><span data-stu-id="95d61-174">Working with Snapshot Isolation</span></span>](../native-client/features/working-with-snapshot-isolation.md)  
  
  
