---
title: ISSAbort::Abort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAbort::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: a5bca169-694b-4895-84ac-e8fba491e479
author: rothja
ms.author: jroth
ms.openlocfilehash: 3daad53087c876af8dc46bccc9c4bf7952976067
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702887"
---
# <a name="issabortabort-ole-db"></a><span data-ttu-id="f7b80-102">ISSAbort::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f7b80-102">ISSAbort::Abort (OLE DB)</span></span>
  <span data-ttu-id="f7b80-103">Annule l'ensemble de lignes actuel plus toutes les commandes par lot associées à la commande actuelle.</span><span class="sxs-lookup"><span data-stu-id="f7b80-103">Cancels the current rowset plus any batched commands associated with the current command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b80-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f7b80-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="f7b80-105">Notes</span><span class="sxs-lookup"><span data-stu-id="f7b80-105">Remarks</span></span>  
 <span data-ttu-id="f7b80-106">Si la commande abandonnée se trouve dans une procédure stockée, l'exécution de la procédure stockée (et de toutes les procédures ayant appelé cette procédure) sera annulée, tout comme le lot de commandes contenant l'appel de procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="f7b80-106">If the command being aborted is in a stored procedure, execution of the stored procedure (and any procedures which had called that procedure) will be terminated as well as the command batch which contains the stored procedure call.</span></span> <span data-ttu-id="f7b80-107">Si le serveur est en cours de transfert d'un jeu de résultats vers le client, cette opération sera arrêtée.</span><span class="sxs-lookup"><span data-stu-id="f7b80-107">If the server is in the process of transferring a result set to the client, this will be stopped.</span></span> <span data-ttu-id="f7b80-108">Si le client ne souhaite pas consommer un jeu de résultats, l'appel de la méthode **ISSAbort::Abort** avant la diffusion de l'ensemble de lignes permettra d'accélérer cette dernière. En revanche, si une transaction est ouverte et si XACT_ABORT est défini sur ON (c'est-à-dire activé), la transaction sera restaurée lors de l'appel de la méthode **ISSAbort::Abort** .</span><span class="sxs-lookup"><span data-stu-id="f7b80-108">If the client does not want to consume a result set, calling **ISSAbort::Abort** before releasing the rowset will speed up the rowset release, but if there is an open transaction and XACT_ABORT is ON, the transaction will be rolled back when **ISSAbort::Abort** is called</span></span>  
  
 <span data-ttu-id="f7b80-109">Dès que **ISSAbort::Abort** retourne S_OK, l'interface **IMultipleResults** associée adopte un état inutilisable et retourne DB_E_CANCELED à tous les appels de méthode (sauf pour les méthodes définies par l'interface **IUnknown** ) jusqu'à ce qu'elle soit diffusée.</span><span class="sxs-lookup"><span data-stu-id="f7b80-109">After **ISSAbort::Abort** returns S_OK, the associated **IMultipleResults** interface enters a unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface) until it is released.</span></span> <span data-ttu-id="f7b80-110">Si une interface **IRowset** a été obtenue à partir de l'interface **IMultipleResults** avant un appel à **à Abort**, elle adopte également un état inutilisable et retourne DB_E_CANCELED à tous les appels de méthode (sauf pour les méthodes définies par l'interface **IUnknown** et **IRowset::ReleaseRows**) jusqu'à ce qu'elle soit diffusée après l'appel en bonne et due forme de la méthode **ISSAbort::Abort**.</span><span class="sxs-lookup"><span data-stu-id="f7b80-110">If an **IRowset** had been obtained from **IMultipleResults** prior to a call to **Abort**, it also enters an unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface and **IRowset::ReleaseRows**) until it is released after a successful call to **ISSAbort::Abort**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7b80-111">À compter de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], si l’état XACT_ABORT du serveur est défini sur ON, l’exécution de la méthode **ISSAbort::Abort** prend fin et restaure toutes les transactions implicites ou explicites actuelles lors de la connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7b80-111">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if the server XACT_ABORT state is ON, executing **ISSAbort::Abort** will terminate and roll back any current implicit or explicit transaction when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f7b80-112">Les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'abandonneront pas la transaction actuelle.</span><span class="sxs-lookup"><span data-stu-id="f7b80-112">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not abort the current transaction.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="f7b80-113">Arguments</span><span class="sxs-lookup"><span data-stu-id="f7b80-113">Arguments</span></span>  
 <span data-ttu-id="f7b80-114">Aucun.</span><span class="sxs-lookup"><span data-stu-id="f7b80-114">None.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="f7b80-115">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="f7b80-115">Return Code Values</span></span>  
 <span data-ttu-id="f7b80-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7b80-116">S_OK</span></span>  
 <span data-ttu-id="f7b80-117">La méthode **ISSAbort::Abort** retourne S_OK si le lot a été annulé ou bien DB_E_CANTCANCEL dans le cas inverse.</span><span class="sxs-lookup"><span data-stu-id="f7b80-117">The **ISSAbort::Abort** method returns S_OK if the batch was canceled and DB_E_CANTCANCEL otherwise.</span></span> <span data-ttu-id="f7b80-118">Si le lot a déjà été annulé, DB_E_CANCELED est retourné.</span><span class="sxs-lookup"><span data-stu-id="f7b80-118">If the batch has already been canceled, DB_E_CANCELED is returned.</span></span>  
  
 <span data-ttu-id="f7b80-119">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="f7b80-119">DB_E_CANCELED</span></span>  
 <span data-ttu-id="f7b80-120">Le lot a déjà été annulé.</span><span class="sxs-lookup"><span data-stu-id="f7b80-120">The batch has already been canceled.</span></span>  
  
 <span data-ttu-id="f7b80-121">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="f7b80-121">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="f7b80-122">Le lot n'a pas été annulé.</span><span class="sxs-lookup"><span data-stu-id="f7b80-122">The batch was not canceled.</span></span>  
  
 <span data-ttu-id="f7b80-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f7b80-123">E_FAIL</span></span>  
 <span data-ttu-id="f7b80-124">Une erreur spécifique au fournisseur s’est produite ; Pour plus d’informations, utilisez l’interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="f7b80-124">A provider specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="f7b80-125">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="f7b80-125">E_UNEXPECTED</span></span>  
 <span data-ttu-id="f7b80-126">L'appel à la méthode était inattendu.</span><span class="sxs-lookup"><span data-stu-id="f7b80-126">The call to the method was unexpected.</span></span> <span data-ttu-id="f7b80-127">Par exemple, l'objet est dans un état zombie parce que la méthode **ISSAbort::Abort** a déjà été appelée.</span><span class="sxs-lookup"><span data-stu-id="f7b80-127">For example, the object is in a zombie state because **ISSAbort::Abort** has already been called.</span></span>  
  
 <span data-ttu-id="f7b80-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f7b80-128">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="f7b80-129">Erreur de mémoire insuffisante.</span><span class="sxs-lookup"><span data-stu-id="f7b80-129">Out of memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b80-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f7b80-130">See Also</span></span>  
 [<span data-ttu-id="f7b80-131">Méthode ISSAbort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="f7b80-131">ISSAbort &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/issabort-ole-db.md)  
  
  
