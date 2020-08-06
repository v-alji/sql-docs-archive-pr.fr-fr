---
title: La mise à niveau modifiera les abonnements de mise à jour en attente qui utilisent Message Queuing | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication]
- MSMQ [SQL Server replication]
- queues [SQL Server replication]
- queued updating subscriptions [SQL Server replication]
ms.assetid: 97944de3-fbad-4db1-939a-dcd550bf5893
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d44cbad43d75634cbf8660110cc879522265c54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710128"
---
# <a name="upgrading-will-modify-queued-updating-subscriptions-that-use-message-queuing"></a><span data-ttu-id="182d1-102">La mise à niveau modifiera les abonnements de mise à jour en attente qui utilisent Message Queuing</span><span class="sxs-lookup"><span data-stu-id="182d1-102">Upgrading will modify queued updating subscriptions that use Message Queuing</span></span>
  <span data-ttu-id="182d1-103">Le Conseiller de mise à niveau a détecté que vous possédez un ou plusieurs abonnements de mise à jour en attente qui utilisent [!INCLUDE[msCoName](../../includes/msconame-md.md)] Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="182d1-103">Upgrade Advisor detected that you might have one or more queued updating subscriptions that use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="182d1-104">Étant donné que la réplication ne prend plus en charge Message Queuing, les abonnements seront modifiés afin d'utiliser une file d'attente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="182d1-104">Replication no longer supports Message Queuing; therefore, the subscriptions will be modified to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span>  
  
 <span data-ttu-id="182d1-105">Seule une valeur **SQL** est autorisée.</span><span class="sxs-lookup"><span data-stu-id="182d1-105">Only a value of **sql** is allowed.</span></span> <span data-ttu-id="182d1-106">Les publications existantes qui utilisent Message Queuing sont modifiées lors de la mise à niveau afin de prendre en charge une file d'attente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="182d1-106">Existing publications that use Message Queuing are modified during upgrade to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span> <span data-ttu-id="182d1-107">Si certaines de vos applications dépendent de la mise à jour en attente à l'aide de Message Queuing, vous devrez les réécrire pour qu'elles puissent utiliser une file d'attente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="182d1-107">If you have applications that depend on queued updating using Message Queuing, these applications will have to be rewritten to accommodate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] queue.</span></span> <span data-ttu-id="182d1-108">Pour plus d'informations sur les abonnements de mise à jour en attente, consultez la rubrique « Abonnements pouvant être mis à jour pour la réplication transactionnelle » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="182d1-108">For more information about queued updating subscriptions, see "Updatable Subscriptions for Transactional Replication" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="182d1-109">La mise à niveau vers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supprime les files d'attente d'abonnement Message Queuing existantes si le service Message Queuing est parallèlement en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="182d1-109">Upgrade will remove the existing Message Queuing subscription queues if the Message Queuing service is running while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being upgraded.</span></span>  
  
 <span data-ttu-id="182d1-110">Si le service Message Queuing n'est pas en cours d'exécution, supprimez les files d'attente manuellement une fois la mise à niveau achevée.</span><span class="sxs-lookup"><span data-stu-id="182d1-110">If the Message Queuing service is not running, remove the queues manually after upgrade is complete.</span></span> <span data-ttu-id="182d1-111">Pour plus d'informations sur la suppression des files d'attente, consultez la documentation de Windows.</span><span class="sxs-lookup"><span data-stu-id="182d1-111">For more information about how to remove queues, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="182d1-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="182d1-112">See Also</span></span>  
 [<span data-ttu-id="182d1-113">Problèmes de mise à niveau de la réplication</span><span class="sxs-lookup"><span data-stu-id="182d1-113">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
