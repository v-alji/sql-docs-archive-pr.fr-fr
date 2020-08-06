---
title: Types de réplication | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], types
ms.assetid: c1655e8d-d14c-455a-a7f9-9d2f43e88ab4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5576331004eca44bc32dbde8f430284f75e6eb70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702676"
---
# <a name="types-of-replication"></a><span data-ttu-id="e6267-102">Types de réplication</span><span class="sxs-lookup"><span data-stu-id="e6267-102">Types of Replication</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="e6267-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournit les types de réplication suivants à utiliser dans des applications distribuées :</span><span class="sxs-lookup"><span data-stu-id="e6267-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following types of replication for use in distributed applications:</span></span>  
  
-   <span data-ttu-id="e6267-104">Réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="e6267-104">Transactional replication.</span></span> <span data-ttu-id="e6267-105">Pour plus d’informations, consultez [Réplication transactionnelle](transactional/transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e6267-105">For more information, see [Transactional Replication](transactional/transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="e6267-106">Réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="e6267-106">Merge replication.</span></span> <span data-ttu-id="e6267-107">Pour plus d’informations, consultez [Réplication de fusion](merge/merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e6267-107">For more information, see [Merge Replication](merge/merge-replication.md).</span></span>  
  
-   <span data-ttu-id="e6267-108">Réplication d'instantané.</span><span class="sxs-lookup"><span data-stu-id="e6267-108">Snapshot replication.</span></span> <span data-ttu-id="e6267-109">Pour plus d’informations, consultez [Réplication d’instantané](snapshot-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e6267-109">For more information, see [Snapshot Replication](snapshot-replication.md).</span></span>  
  
 <span data-ttu-id="e6267-110">Le type de réplication que vous choisissez pour une application dépend de nombreux facteurs, dont l'environnement physique de la réplication, le type et la quantité de données à répliquer et si les données sont ou non mises à jour sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="e6267-110">The type of replication you choose for an application depends on many factors, including the physical replication environment, the type and quantity of data to be replicated, and whether the data is updated at the Subscriber.</span></span> <span data-ttu-id="e6267-111">L'environnement physique comprend le nombre et l'emplacement des ordinateurs impliqués dans la réplication et le fait que ces ordinateurs sont des clients (stations de travail, ordinateurs portables ou ordinateurs de poche) ou des serveurs.</span><span class="sxs-lookup"><span data-stu-id="e6267-111">The physical environment includes the number and location of computers involved in replication and whether these computers are clients (workstations, laptops, or handheld devices) or servers.</span></span>  
  
 <span data-ttu-id="e6267-112">Chaque type de réplication commence par une synchronisation initiale des objets publiés entre le serveur de publication et les Abonnés.</span><span class="sxs-lookup"><span data-stu-id="e6267-112">Each type of replication typically begins with an initial synchronization of the published objects between the Publisher and Subscribers.</span></span> <span data-ttu-id="e6267-113">Cette synchronisation peut être effectuée par réplication avec un *instantané*, qui est une copie de tous les objets et de toutes les données spécifiées par une publication.</span><span class="sxs-lookup"><span data-stu-id="e6267-113">This initial synchronization can be performed by replication with a *snapshot*, which is a copy of all of the objects and data specified by a publication.</span></span> <span data-ttu-id="e6267-114">Quand l'instantané est créé, il est remis aux Abonnés.</span><span class="sxs-lookup"><span data-stu-id="e6267-114">After the snapshot is created, it is delivered to the Subscribers.</span></span> <span data-ttu-id="e6267-115">Pour certaines applications, la réplication d'instantané est tout ce qui est requis.</span><span class="sxs-lookup"><span data-stu-id="e6267-115">For some applications, snapshot replication is all that is required.</span></span> <span data-ttu-id="e6267-116">Pour d'autres types d'applications, il est important que les modifications de données suivantes soient transmises à l'Abonné de façon incrémentielle au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="e6267-116">For other types of applications, it is important that subsequent data changes flow to the Subscriber incrementally over time.</span></span> <span data-ttu-id="e6267-117">Certaines applications requièrent aussi que les modifications transitent en sens inverse, de l'Abonné vers le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="e6267-117">Some applications also require that changes flow from the Subscriber back to the Publisher.</span></span> <span data-ttu-id="e6267-118">La réplication transactionnelle et la réplication de fusion comportent des options pour ces types d'applications.</span><span class="sxs-lookup"><span data-stu-id="e6267-118">Transactional replication and merge replication provide options for these types of applications.</span></span>  
  
 <span data-ttu-id="e6267-119">Les modifications des données ne font pas l'objet d'un suivi dans la réplication d'instantané : chaque fois qu'un instantané est appliqué, il remplace complètement les données existantes.</span><span class="sxs-lookup"><span data-stu-id="e6267-119">Data changes are not tracked for snapshot replication; each time a snapshot is applied, it completely overwrites the existing data.</span></span> <span data-ttu-id="e6267-120">La réplication transactionnelle fait le suivi des modifications via le journal des transactions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; la réplication de fusion fait le suivi des modifications via des déclencheurs et des tables de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="e6267-120">Transactional replication tracks changes through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction log, and merge replication tracks changes through triggers and metadata tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6267-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6267-121">See Also</span></span>  
 [<span data-ttu-id="e6267-122">Présentation des Agents de réplication</span><span class="sxs-lookup"><span data-stu-id="e6267-122">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
