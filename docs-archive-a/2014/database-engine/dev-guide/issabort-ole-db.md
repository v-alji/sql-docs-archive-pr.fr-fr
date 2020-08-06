---
title: Méthode ISSAbort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- ISSAbort interface
ms.assetid: 7c4df482-4a83-4da0-802b-3637b507693a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7195311fefe3f0f1b7b4d6d789aa8d8487bc3bfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709847"
---
# <a name="issabort-ole-db"></a><span data-ttu-id="8be4e-102">ISSAbort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="8be4e-102">ISSAbort (OLE DB)</span></span>
  <span data-ttu-id="8be4e-103">L'interface **ISSAbort** , exposée dans le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, fournit la méthode [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) utilisée pour annuler l'ensemble de lignes actuel, plus les commandes regroupées par lot avec la commande ayant généré initialement l'ensemble de lignes et dont l'exécution n'est pas encore achevée.</span><span class="sxs-lookup"><span data-stu-id="8be4e-103">The **ISSAbort** interface, which is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, provides the [ISSAbort::Abort](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md) method that is used to cancel the current rowset plus any commands batched with the command that initially generated the rowset, and that have not yet completed execution.</span></span>  
  
 <span data-ttu-id="8be4e-104">**ISSAbort** est une interface propre au fournisseur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client disponible en utilisant **QueryInterface** sur l'objet **IMultipleResults** retourné par **ICommand::Execute** ou **IOpenRowset::OpenRowset**.</span><span class="sxs-lookup"><span data-stu-id="8be4e-104">**ISSAbort** is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider-specific interface available by using **QueryInterface** on the **IMultipleResults** object returned by **ICommand::Execute** or **IOpenRowset::OpenRowset**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8be4e-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8be4e-105">In This Section</span></span>  
  
|<span data-ttu-id="8be4e-106">Méthode</span><span class="sxs-lookup"><span data-stu-id="8be4e-106">Method</span></span>|<span data-ttu-id="8be4e-107">Description</span><span class="sxs-lookup"><span data-stu-id="8be4e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8be4e-108">Méthode ISSAbort :: Abort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8be4e-108">ISSAbort::Abort &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-interfaces/issabort-abort-ole-db.md)|<span data-ttu-id="8be4e-109">Annule l'ensemble de lignes actuel plus toutes les commandes par lot associées à la commande actuelle.</span><span class="sxs-lookup"><span data-stu-id="8be4e-109">Cancels the current rowset plus any batched commands associated with the current command.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8be4e-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8be4e-110">See Also</span></span>  
 [<span data-ttu-id="8be4e-111">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8be4e-111">Interfaces &#40;OLE DB&#41;</span></span>](../../../2014/database-engine/dev-guide/interfaces-ole-db.md)  
  
  
