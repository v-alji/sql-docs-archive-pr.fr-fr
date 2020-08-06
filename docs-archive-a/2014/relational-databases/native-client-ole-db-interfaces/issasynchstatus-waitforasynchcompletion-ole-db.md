---
title: ISSAsynchStatus::WaitForAsynchCompletion (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- WaitForAsynchCompletion method
ms.assetid: 9f65e9e7-eb93-47a1-bc42-acd4649fbd0e
author: rothja
ms.author: jroth
ms.openlocfilehash: f57211d1c62535828704dc971e345b412c284cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603489"
---
# <a name="issasynchstatuswaitforasynchcompletion-ole-db"></a><span data-ttu-id="0a96d-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0a96d-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span></span>
  <span data-ttu-id="0a96d-103">Attend que l'opération s'exécutant de façon asynchrone se termine ou qu'un délai d'expiration soit dépassé.</span><span class="sxs-lookup"><span data-stu-id="0a96d-103">Waits until the asynchronously executing operation is complete or until a time-out occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a96d-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0a96d-104">Syntax</span></span>  
  
```  
  
HRESULT WaitForAsynchCompletion(   
  DWORD dwMillisecTimeOut);  
```  
  
## <a name="arguments"></a><span data-ttu-id="0a96d-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="0a96d-105">Arguments</span></span>  
 <span data-ttu-id="0a96d-106">*dwMillisecTimeOut*[in]</span><span class="sxs-lookup"><span data-stu-id="0a96d-106">*dwMillisecTimeOut*[in]</span></span>  
 <span data-ttu-id="0a96d-107">Délai en millisecondes.</span><span class="sxs-lookup"><span data-stu-id="0a96d-107">Time-out in milliseconds.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="0a96d-108">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="0a96d-108">Return Code Values</span></span>  
 <span data-ttu-id="0a96d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a96d-109">S_OK</span></span>  
 <span data-ttu-id="0a96d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a96d-110">The method succeeded.</span></span>  
  
 <span data-ttu-id="0a96d-111">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="0a96d-111">E_UNEXPECTED</span></span>  
 <span data-ttu-id="0a96d-112">Un ensemble de lignes est dans un état inutilisé, car **ITransaction::Commit** ou **ITransaction::Abort** a été appelé, ou l'ensemble de lignes a été annulé pendant sa phase d'initialisation.</span><span class="sxs-lookup"><span data-stu-id="0a96d-112">A rowset is in an unused state because **ITransaction::Commit** or **ITransaction::Abort** has been called or the rowset was cancelled during its initialization phase.</span></span>  
  
 <span data-ttu-id="0a96d-113">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="0a96d-113">DB_E_CANCELED</span></span>  
 <span data-ttu-id="0a96d-114">Le traitement asynchrone a été annulé pendant le remplissage de l'ensemble de lignes ou l'initialisation de l'objet source de données.</span><span class="sxs-lookup"><span data-stu-id="0a96d-114">Asynchronous processing was cancelled during rowset population or data source object initialization.</span></span>  
  
 <span data-ttu-id="0a96d-115">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="0a96d-115">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="0a96d-116">L'opération n'est pas encore terminée même si le délai d'expiration spécifié a été atteint.</span><span class="sxs-lookup"><span data-stu-id="0a96d-116">The operation has not yet completed even though specified time-out has been reached.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a96d-117">Outre les valeurs de code de retour répertoriées ci-dessus, la méthode **ISSAsynchStatus::WaitForAsynchCompletion** prend également en charge les valeurs de code de retour retournées par les méthodes OLEDB **ICommand::Execute** et **IDBInitialize::Initialize** principales.</span><span class="sxs-lookup"><span data-stu-id="0a96d-117">In addition to the return code values listed above, the **ISSAsynchStatus::WaitForAsynchCompletion** method also supports the return code values returned by the core OLEDB **ICommand::Execute** and **IDBInitialize::Initialize** methods.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a96d-118">Notes</span><span class="sxs-lookup"><span data-stu-id="0a96d-118">Remarks</span></span>  
 <span data-ttu-id="0a96d-119">La méthode **ISSAsynchStatus::WaitForAsynchCompletion** n'est pas retournée tant que la valeur du délai d'attente (en millisecondes) n'est pas passée ou que l'opération en attente n'est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="0a96d-119">The **ISSAsynchStatus::WaitForAsynchCompletion** method will not return until the time-out value (in milliseconds) has passed or the pending operation is done.</span></span> <span data-ttu-id="0a96d-120">L’objet **Command** a une propriété **CommandTimeout** qui contrôle le nombre de secondes pendant lesquelles une requête doit s’exécuter avant l’expiration du délai d’attente. La propriété **CommandTimeout** est ignorée si elle est utilisée conjointement avec la méthode **ISSAsynchStatus :: WaitForAsynchCompletion** .</span><span class="sxs-lookup"><span data-stu-id="0a96d-120">The **Command** object has a **CommandTimeout** property that controls the number of seconds a query will run before timing out. The **CommandTimeout** property will be ignored if used in conjunction with **ISSAsynchStatus::WaitForAsynchCompletion** method.</span></span>  
  
 <span data-ttu-id="0a96d-121">La propriété relative au délai d'expiration est ignorée pour les opérations asynchrones.</span><span class="sxs-lookup"><span data-stu-id="0a96d-121">The time-out property is ignored for asynchronous operations.</span></span> <span data-ttu-id="0a96d-122">Le paramètre de délai d'expiration de **ISSAsynchStatus::WaitForAsynchCompletion** spécifie la durée maximale qui doit s'écouler avant que le contrôle ne soit retourné à l'appelant.</span><span class="sxs-lookup"><span data-stu-id="0a96d-122">The time-out parameter of **ISSAsynchStatus::WaitForAsynchCompletion** specifies the maximum amount of time that will elapse before control is returned to the caller.</span></span> <span data-ttu-id="0a96d-123">Si ce délai expire, DB_S_ASYNCHRONOUS est retourné.</span><span class="sxs-lookup"><span data-stu-id="0a96d-123">If this time-out expires, DB_S_ASYNCHRONOUS will be returned.</span></span> <span data-ttu-id="0a96d-124">L'expiration des délais d'attente n'annule jamais les opérations asynchrones.</span><span class="sxs-lookup"><span data-stu-id="0a96d-124">Time-outs never cancel asynchronous operations.</span></span> <span data-ttu-id="0a96d-125">Si l'application doit annuler une opération asynchrone qui ne se termine pas dans un délai imparti, elle doit attendre l'expiration du délai, puis annuler explicitement l'opération si DB_S_ASYNCHRONOUS est retourné.</span><span class="sxs-lookup"><span data-stu-id="0a96d-125">If the application needs to cancel an asynchronous operation that does not complete within a time-out period, it must wait for the time-out and then explicitly cancel the operation if DB_S_ASYNCHRONOUS is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a96d-126">Quand les composants du service OLE DB sont utilisés, S_OK peut être retourné quand DB_S_ASYNCHRONOUS est attendu ; ainsi, les applications doivent appeler [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) pour vérifier l’état d’achèvement quand S_OK ou DB_S_ASYNCHRONOUS est retourné.</span><span class="sxs-lookup"><span data-stu-id="0a96d-126">When the OLE DB Service Components are used, S_OK may be returned when DB_S_ASYNCHRONOUS is expected, so applications should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) to check for completion when S_OK or DB_S_ASYNCHRONOUS is returned.</span></span>  
  
 <span data-ttu-id="0a96d-127">Si la valeur de *dwMillisecTimeOut* est INFINITE, la méthode **ISSAsynchStatus::WaitForAsynchCompletion** se bloque jusqu'à ce que l'opération soit terminée.</span><span class="sxs-lookup"><span data-stu-id="0a96d-127">If the *dwMillisecTimeOut* value is set to INFINITE, the **ISSAsynchStatus::WaitForAsynchCompletion** method blocks until the operation is done.</span></span> <span data-ttu-id="0a96d-128">Si la valeur de *dwMillisecTimeOut* est 0, la méthode est retournée immédiatement avec l'état de l'opération en attente.</span><span class="sxs-lookup"><span data-stu-id="0a96d-128">If the *dwMillisecTimeOut* value is set to 0, then the method will return immediately with the status of the pending operation.</span></span> <span data-ttu-id="0a96d-129">Si le délai d'attente expire avant que l'opération ne soit terminée, DB_S_ASYNCHRONOUS est retourné.</span><span class="sxs-lookup"><span data-stu-id="0a96d-129">If the time-out expires before the operation is complete DB_S_ASYNCHRONOUS will be returned.</span></span>  
  
 <span data-ttu-id="0a96d-130">Si l'opération se termine avant l'expiration du délai d'attente, le HRESULT retourné correspond au HRESULT retourné par l'opération (HRESULT retourné si l'opération était effectuée de façon synchrone).</span><span class="sxs-lookup"><span data-stu-id="0a96d-130">If the operation completes before the time-out expires, the returned HRESULT will be the HRESULT returned by the operation (the HRESULT that would have been returned had the operation been performed synchronously).</span></span>  
  
 <span data-ttu-id="0a96d-131">De plus, la propriété SSPROP_ISSAsynchStatus a été ajoutée au jeu de propriétés DBPROPSET_SQLSERVERROWSET.</span><span class="sxs-lookup"><span data-stu-id="0a96d-131">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="0a96d-132">Les fournisseurs qui prennent en charge l’interface [ISSAsynchStatus](issasynchstatus-ole-db.md) doivent implémenter cette propriété avec la valeur VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="0a96d-132">Providers that support the [ISSAsynchStatus](issasynchstatus-ole-db.md) interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a96d-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a96d-133">See Also</span></span>  
 <span data-ttu-id="0a96d-134">[Exécution d’opérations asynchrones](../native-client/features/performing-asynchronous-operations.md) </span><span class="sxs-lookup"><span data-stu-id="0a96d-134">[Performing Asynchronous Operations](../native-client/features/performing-asynchronous-operations.md) </span></span>  
 [<span data-ttu-id="0a96d-135">ISSAsynchStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="0a96d-135">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-ole-db.md)  
  
  
