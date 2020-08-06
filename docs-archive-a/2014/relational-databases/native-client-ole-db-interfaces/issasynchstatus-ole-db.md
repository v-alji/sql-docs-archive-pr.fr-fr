---
title: ISSAsynchStatus (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSAsynchStatus interface
ms.assetid: c643f09f-9ccc-4d8b-9243-3cde86c2bd46
author: rothja
ms.author: jroth
ms.openlocfilehash: 4489f9d1ad576d49d885842f6969f9b61065791c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603490"
---
# <a name="issasynchstatus-ole-db"></a><span data-ttu-id="cd667-102">ISSAsynchStatus (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="cd667-102">ISSAsynchStatus (OLE DB)</span></span>
  <span data-ttu-id="cd667-103">**ISSAsynchStatus** expose la prise en charge des opérations asynchrones [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd667-103">**ISSAsynchStatus** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asynchronous operations.</span></span> <span data-ttu-id="cd667-104">Il s'agit d'une interface facultative qui hérite de l'interface OLE DB de base **IDBAsynchStatus**.</span><span class="sxs-lookup"><span data-stu-id="cd667-104">This is an optional interface that inherits from the core OLE DB interface **IDBAsynchStatus**.</span></span> <span data-ttu-id="cd667-105">Outre les méthodes **Abort** et **GetStatus** héritées de **IDBAsynchStatus**, **ISSAsynchStatus** fournit une nouvelle méthode qui permet d'attendre qu'une opération asynchrone se termine ou qu'un délai d'expiration soit dépassé.</span><span class="sxs-lookup"><span data-stu-id="cd667-105">In addition to the **Abort** and **GetStatus** methods inherited from **IDBAsynchStatus**, **ISSAsynchStatus** provides one new method that is used to wait until an asynchronous operation has completed or a time-out occurs.</span></span>  
  
|<span data-ttu-id="cd667-106">Méthode</span><span class="sxs-lookup"><span data-stu-id="cd667-106">Method</span></span>|<span data-ttu-id="cd667-107">Description</span><span class="sxs-lookup"><span data-stu-id="cd667-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd667-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cd667-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span></span>](issasynchstatus-abort-ole-db.md)|<span data-ttu-id="cd667-109">Annule une opération s'exécutant de manière asynchrone.</span><span class="sxs-lookup"><span data-stu-id="cd667-109">Cancels an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="cd667-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cd667-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-getstatus-ole-db.md)|<span data-ttu-id="cd667-111">Retourne l'état d'une opération s'exécutant de manière asynchrone.</span><span class="sxs-lookup"><span data-stu-id="cd667-111">Returns the status of an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="cd667-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="cd667-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span></span>](issasynchstatus-waitforasynchcompletion-ole-db.md)|<span data-ttu-id="cd667-113">Attend que l'opération s'exécutant de façon asynchrone se termine ou qu'un délai d'expiration soit dépassé.</span><span class="sxs-lookup"><span data-stu-id="cd667-113">Waits until the asynchronously executing operation is complete or a time-out occurs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd667-114">Notes</span><span class="sxs-lookup"><span data-stu-id="cd667-114">Remarks</span></span>  
 <span data-ttu-id="cd667-115">L'implémentation **ISSAsynchStatus** de la méthode **ISSAsynchStatus::GetStatus** est identique à la méthode **IDBAsynchStatus::GetStatus** , à la différence près que si l'initialisation d'un objet source de données est abandonnée, E_UNEXPECTED est retourné au lieu de DB_E_CANCELED (bien que **ISSAsynchStatus::WaitForAsynchCompletion** retourne DB_E_CANCELED).</span><span class="sxs-lookup"><span data-stu-id="cd667-115">The **ISSAsynchStatus** implementation of the **ISSAsynchStatus::GetStatus** method is the same as the **IDBAsynchStatus::GetStatus** method except that if the initialization of a data source object is aborted, E_UNEXPECTED is returned rather than DB_E_CANCELED (although **ISSAsynchStatus::WaitForAsynchCompletion** returns DB_E_CANCELED).</span></span> <span data-ttu-id="cd667-116">Cela est dû au fait que l'objet source de données ne reste pas dans l'état habituel après une opération d'abandon, afin que d'autres tentatives d'initialisation puissent avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="cd667-116">This is because the data source object is not left in the usual state following an abort operation, so that further initialization operations may be attempted.</span></span>  
  
 <span data-ttu-id="cd667-117">Les méthodes suivantes prennent en charge l'utilisation d'une exécution asynchrone dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="cd667-117">The following methods support the use of asynchronous execution in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="cd667-118">**ICommand::Execute**</span><span class="sxs-lookup"><span data-stu-id="cd667-118">**ICommand::Execute**</span></span>  
  
-   <span data-ttu-id="cd667-119">**IOpenRowset::OpenRowset**</span><span class="sxs-lookup"><span data-stu-id="cd667-119">**IOpenRowset::OpenRowset**</span></span>  
  
-   <span data-ttu-id="cd667-120">**IMultipleResults::GetResult**</span><span class="sxs-lookup"><span data-stu-id="cd667-120">**IMultipleResults::GetResult**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd667-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cd667-121">See Also</span></span>  
 <span data-ttu-id="cd667-122">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="cd667-122">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 [<span data-ttu-id="cd667-123">Exécution d'opérations asynchrones</span><span class="sxs-lookup"><span data-stu-id="cd667-123">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
