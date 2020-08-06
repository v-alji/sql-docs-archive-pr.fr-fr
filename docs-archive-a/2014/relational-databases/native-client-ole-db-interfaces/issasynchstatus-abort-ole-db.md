---
title: ISSAsynchStatus::Abort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: 2a4bd312-839a-45a8-a299-fc8609be9a2a
author: rothja
ms.author: jroth
ms.openlocfilehash: 0fb352b6541240126dcd4c60521b93d57d6839f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702883"
---
# <a name="issasynchstatusabort-ole-db"></a><span data-ttu-id="ee055-102">ISSAsynchStatus::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ee055-102">ISSAsynchStatus::Abort (OLE DB)</span></span>
  <span data-ttu-id="ee055-103">Annule une opération s'exécutant de manière asynchrone.</span><span class="sxs-lookup"><span data-stu-id="ee055-103">Cancels an asynchronously executing operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee055-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ee055-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(  
  HCHAPTER hChapter,  
  DBASYNCHOP eOperation);  
```  
  
## <a name="arguments"></a><span data-ttu-id="ee055-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="ee055-105">Arguments</span></span>  
 <span data-ttu-id="ee055-106">*hChapter*[in]</span><span class="sxs-lookup"><span data-stu-id="ee055-106">*hChapter*[in]</span></span>  
 <span data-ttu-id="ee055-107">Handle du chapitre pour lequel vous souhaitez abandonner l'opération.</span><span class="sxs-lookup"><span data-stu-id="ee055-107">The handle of the chapter for which to abort the operation.</span></span> <span data-ttu-id="ee055-108">Si l'objet appelé n'est pas un objet d'ensemble de lignes ou que l'opération ne s'applique pas à un chapitre, l'appelant doit attribuer la valeur DB_NULL_HCHAPTER à *hChapter* .</span><span class="sxs-lookup"><span data-stu-id="ee055-108">If the object being called is not a rowset object or the operation does not apply to a chapter, the caller must set *hChapter* to DB_NULL_HCHAPTER.</span></span>  
  
 <span data-ttu-id="ee055-109">*eOperation*[in]</span><span class="sxs-lookup"><span data-stu-id="ee055-109">*eOperation*[in]</span></span>  
 <span data-ttu-id="ee055-110">L'opération à abandonner.</span><span class="sxs-lookup"><span data-stu-id="ee055-110">The operation to abort.</span></span> <span data-ttu-id="ee055-111">Elle doit avoir la valeur suivante :</span><span class="sxs-lookup"><span data-stu-id="ee055-111">This should be the following value:</span></span>  
  
 <span data-ttu-id="ee055-112">DBASYNCHOP_OPEN : la demande d'annulation s'applique à l'ouverture ou au remplissage asynchrone d'un ensemble de lignes ou à l'initialisation asynchrone d'un objet source de données.</span><span class="sxs-lookup"><span data-stu-id="ee055-112">DBASYNCHOP_OPEN-The request to cancel applies to the asynchronous opening or population of a rowset or to the asynchronous initialization of a data source object.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="ee055-113">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="ee055-113">Return Code Values</span></span>  
 <span data-ttu-id="ee055-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee055-114">S_OK</span></span>  
 <span data-ttu-id="ee055-115">La demande d'annulation de l'opération asynchrone a été traitée.</span><span class="sxs-lookup"><span data-stu-id="ee055-115">The request to cancel the asynchronous operation was processed.</span></span> <span data-ttu-id="ee055-116">Cela ne garantit pas que l'opération ait été annulée.</span><span class="sxs-lookup"><span data-stu-id="ee055-116">This does not guarantee that the operation itself was canceled.</span></span> <span data-ttu-id="ee055-117">Pour déterminer si l'opération a bien été annulée, le consommateur doit appeler [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) et vérifier la présence de DB_E_CANCELED ; toutefois, il est possible qu'il ne soit pas retourné dans l'appel suivant.</span><span class="sxs-lookup"><span data-stu-id="ee055-117">To determine whether the operation was canceled, the consumer should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) and check for DB_E_CANCELED; however, it might not be returned in the very next call.</span></span>  
  
 <span data-ttu-id="ee055-118">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="ee055-118">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="ee055-119">L'opération asynchrone ne peut pas être annulée.</span><span class="sxs-lookup"><span data-stu-id="ee055-119">The asynchronous operation cannot be canceled.</span></span>  
  
 <span data-ttu-id="ee055-120">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="ee055-120">DB_E_CANCELED</span></span>  
 <span data-ttu-id="ee055-121">La demande d'abandon de l'opération asynchrone a été annulée au cours de notifications.</span><span class="sxs-lookup"><span data-stu-id="ee055-121">The request to abort the asynchronous operation was canceled during notifications.</span></span> <span data-ttu-id="ee055-122">L'opération est encore exécutée de manière asynchrone.</span><span class="sxs-lookup"><span data-stu-id="ee055-122">The operation is still being executed asynchronously.</span></span>  
  
 <span data-ttu-id="ee055-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ee055-123">E_FAIL</span></span>  
 <span data-ttu-id="ee055-124">Une erreur spécifique au fournisseur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="ee055-124">A provider-specific error occurred.</span></span>  
  
 <span data-ttu-id="ee055-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ee055-125">E_INVALIDARG</span></span>  
 <span data-ttu-id="ee055-126">Le paramètre *hChapter* n'est pas DB_NULL_HCHAPTER ou *eOperation* n'est pas DBASYNCH_OPEN.</span><span class="sxs-lookup"><span data-stu-id="ee055-126">The *hChapter* parameter is not DB_NULL_HCHAPTER or *eOperation* is not DBASYNCH_OPEN.</span></span>  
  
 <span data-ttu-id="ee055-127">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="ee055-127">E_UNEXPECTED</span></span>  
 <span data-ttu-id="ee055-128">**ISSAsynchStatus::Abort** a été appelé sur un objet source de données sur lequel **IDBInitialize::Initialize** n'a pas été appelé ou ne s'est pas terminé.</span><span class="sxs-lookup"><span data-stu-id="ee055-128">**ISSAsynchStatus::Abort** was called on a data source object on which **IDBInitialize::Initialize** has not been called, or has not completed.</span></span>  
  
 <span data-ttu-id="ee055-129">**ISSAsynchStatus :: Abort** a été appelé sur un objet source de données sur lequel **IDBInitialize :: Initialize** a été appelé, mais il a été annulé par la suite avant l’initialisation ou a dépassé le délai d’attente. L’objet source de données n’est toujours pas initialisé.</span><span class="sxs-lookup"><span data-stu-id="ee055-129">**ISSAsynchStatus::Abort** was called on a data source object on which **IDBInitialize::Initialize** was called but subsequently canceled before initialization, or has timed out. The data source object is still uninitialized.</span></span>  
  
 <span data-ttu-id="ee055-130">**ISSAsynchStatus::Abort** a été appelé sur un ensemble de lignes sur lequel **ITransaction::Commit** ou **ITransaction::Abort** a été appelé précédemment, et l'ensemble de lignes n'a pas survécu à la validation ou à l'abandon et se trouve dans un état passif.</span><span class="sxs-lookup"><span data-stu-id="ee055-130">**ISSAsynchStatus::Abort** was called on a rowset on which **ITransaction::Commit** or **ITransaction::Abort** was previously called, and the rowset did not survive the commit or abort and is in a zombie state.</span></span>  
  
 <span data-ttu-id="ee055-131">**ISSAsynchStatus::Abort** a été appelé sur un ensemble de lignes qui a été annulé de manière asynchrone dans sa phase d'initialisation.</span><span class="sxs-lookup"><span data-stu-id="ee055-131">**ISSAsynchStatus::Abort** was called on a rowset that was asynchronously canceled in its initialization phase.</span></span> <span data-ttu-id="ee055-132">L'ensemble de lignes se trouve dans un état zombie.</span><span class="sxs-lookup"><span data-stu-id="ee055-132">The rowset is in a zombie state.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee055-133">Notes</span><span class="sxs-lookup"><span data-stu-id="ee055-133">Remarks</span></span>  
 <span data-ttu-id="ee055-134">L'abandon de l'initialisation d'un ensemble de lignes ou d'un objet source de données peut laisser l'ensemble de lignes ou l'objet source de données dans un état zombie, de telle sorte que toutes les méthodes autres que **IUnknown** retournent E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="ee055-134">Aborting the initialization of a rowset or data source object might leave the rowset or data source object in a zombie state, such that all methods other than **IUnknown** methods return E_UNEXPECTED.</span></span> <span data-ttu-id="ee055-135">Lorsque cela se produit, la seule action possible pour le consommateur est de libérer l'ensemble de lignes ou l'objet source de données.</span><span class="sxs-lookup"><span data-stu-id="ee055-135">When this happens, the only possible action for the consumer is to release the rowset or data source object.</span></span>  
  
 <span data-ttu-id="ee055-136">Le fait d'appeler **ISSAsynchStatus::Abort** et de passer une valeur pour *eOperation* autre que DBASYNCHOP_OPEN retourne S_OK.</span><span class="sxs-lookup"><span data-stu-id="ee055-136">Calling **ISSAsynchStatus::Abort** and passing a value for *eOperation* other than DBASYNCHOP_OPEN returns S_OK.</span></span> <span data-ttu-id="ee055-137">Cela ne signifie pas pour autant que l'opération est terminée ou annulée.</span><span class="sxs-lookup"><span data-stu-id="ee055-137">This does not imply that the operation completed or was canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee055-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee055-138">See Also</span></span>  
 [<span data-ttu-id="ee055-139">Exécution d'opérations asynchrones</span><span class="sxs-lookup"><span data-stu-id="ee055-139">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
