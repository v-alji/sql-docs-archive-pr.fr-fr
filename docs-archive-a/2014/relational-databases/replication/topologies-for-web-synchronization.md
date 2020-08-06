---
title: Topologies pour la synchronisation web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Web synchronization, topologies
- IIS server configuration [SQL Server replication]
ms.assetid: 59444faf-bcb6-4421-a3df-8715753e453b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5e28ca5a222e2286d154c16ef41d3147dc56e25a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610597"
---
# <a name="topologies-for-web-synchronization"></a><span data-ttu-id="72885-102">Topologies pour la synchronisation Web</span><span class="sxs-lookup"><span data-stu-id="72885-102">Topologies for Web Synchronization</span></span>
  <span data-ttu-id="72885-103">Vous pouvez choisir parmi différentes topologies de réplication de synchronisation web [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72885-103">You can choose from a variety of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Web synchronization replication topologies.</span></span> <span data-ttu-id="72885-104">Les façons courantes de configurer une synchronisation Web sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="72885-104">Common ways to configure Web synchronization include:</span></span>  
  
-   <span data-ttu-id="72885-105">Serveur unique</span><span class="sxs-lookup"><span data-stu-id="72885-105">Single server</span></span>  
  
-   <span data-ttu-id="72885-106">Deux serveurs</span><span class="sxs-lookup"><span data-stu-id="72885-106">Two servers</span></span>  
  
-   <span data-ttu-id="72885-107">Plusieurs systèmes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) et la republication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72885-107">Multiple [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) systems and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] republishing</span></span>  
  
 <span data-ttu-id="72885-108">Pour obtenir des informations sur la configuration de la synchronisation Web, consultez [Configurer la synchronisation Web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="72885-108">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="single-server"></a><span data-ttu-id="72885-109">Serveur unique</span><span class="sxs-lookup"><span data-stu-id="72885-109">Single Server</span></span>  
 <span data-ttu-id="72885-110">Dans la topologie la plus simple, IIS, le serveur de publication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le serveur de distribution [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] résident tous trois sur le même serveur.</span><span class="sxs-lookup"><span data-stu-id="72885-110">In the simplest topology, IIS, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor all reside on a single server.</span></span> <span data-ttu-id="72885-111">Les Abonnés se synchronisent en se connectant à IIS sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="72885-111">Subscribers synchronize by connecting to IIS on the Publisher.</span></span> <span data-ttu-id="72885-112">Le serveur de publication peut être situé derrière un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="72885-112">The Publisher can be located behind a firewall.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72885-113">Cette configuration est recommandée uniquement pour les scénarios intranet.</span><span class="sxs-lookup"><span data-stu-id="72885-113">This configuration is recommended only for intranet scenarios.</span></span> <span data-ttu-id="72885-114">Pour les autres scénarios, il est recommandé que le serveur IIS et les serveurs de publication et de distribution [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] soient placés sur des ordinateurs distincts.</span><span class="sxs-lookup"><span data-stu-id="72885-114">For other scenarios, it is recommended that the IIS server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher/Distributor be on separate computers.</span></span>  
  
 <span data-ttu-id="72885-115">![Synchronisation web avec un serveur unique](media/web-sync02.gif "Synchronisation web avec un serveur unique")</span><span class="sxs-lookup"><span data-stu-id="72885-115">![Web synchronization with a single server](media/web-sync02.gif "Web synchronization with a single server")</span></span>  
  
## <a name="two-servers"></a><span data-ttu-id="72885-116">Deux serveurs</span><span class="sxs-lookup"><span data-stu-id="72885-116">Two Servers</span></span>  
 <span data-ttu-id="72885-117">Vous pouvez placer IIS sur un serveur et configurer les serveurs de publication et de distribution [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un autre serveur.</span><span class="sxs-lookup"><span data-stu-id="72885-117">You can place IIS on one server and configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher and Distributor on another server.</span></span> <span data-ttu-id="72885-118">Le serveur exécutant IIS peut être isolé d'Internet par un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="72885-118">The server running IIS can be isolated from the Internet by a firewall.</span></span> <span data-ttu-id="72885-119">Les Abonnés se synchronisent en se connectant à IIS.</span><span class="sxs-lookup"><span data-stu-id="72885-119">Subscribers synchronize by connecting to IIS.</span></span>  
  
 <span data-ttu-id="72885-120">![Synchronisation web avec deux serveurs](media/web-sync03.gif "Synchronisation web avec deux serveurs")</span><span class="sxs-lookup"><span data-stu-id="72885-120">![Web synchronization with two servers](media/web-sync03.gif "Web synchronization with two servers")</span></span>  
  
## <a name="multiple-iis-systems-and-sql-server-republishing"></a><span data-ttu-id="72885-121">Plusieurs systèmes IIS et la republication SQL Server</span><span class="sxs-lookup"><span data-stu-id="72885-121">Multiple IIS Systems and SQL Server Republishing</span></span>  
 <span data-ttu-id="72885-122">Si vous devez prendre en charge un très grand nombre d'Abonnés qui se synchronisent au même moment, vous pouvez partitionner le travail entre plusieurs ordinateurs exécutant IIS.</span><span class="sxs-lookup"><span data-stu-id="72885-122">If you need to support very large numbers of Subscribers that synchronize at the same time, you can partition the work across multiple computers running IIS.</span></span>  
  
 <span data-ttu-id="72885-123">![Synchronisation web avec plusieurs serveurs IIS](media/web-sync04.gif "Synchronisation web avec plusieurs serveurs IIS")</span><span class="sxs-lookup"><span data-stu-id="72885-123">![Web synchronization with multiple IIS servers](media/web-sync04.gif "Web synchronization with multiple IIS servers")</span></span>  
  
 <span data-ttu-id="72885-124">Si un équilibrage de charge est encore nécessaire sur l'ordinateur exécutant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez créer une hiérarchie de republication sur plusieurs ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="72885-124">If further load balancing is required on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can create a republishing hierarchy on multiple computers.</span></span> <span data-ttu-id="72885-125">Le serveur de publication de niveau supérieur publie les données vers les Abonnés, qui à leur tour republient ces données, équilibrant la charge des requêtes en provenance des Abonnés.</span><span class="sxs-lookup"><span data-stu-id="72885-125">The top-level Publisher publishes data to Subscribers, which in turn republish the data, load balancing requests from the Subscribers.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72885-126">Les Abonnés ne peuvent effectuer des synchronisations qu'avec un serveur de publication donné.</span><span class="sxs-lookup"><span data-stu-id="72885-126">Subscribers can only synchronize with a specific Publisher.</span></span> <span data-ttu-id="72885-127">Par exemple, un Abonné au serveur de republication A ne peut effectuer aucune synchronisation avec le serveur de republication B si le serveur A n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="72885-127">For example, a Subscriber to republisher A cannot synchronize with republisher B when A is not available.</span></span>  
  
 <span data-ttu-id="72885-128">![Synchronisation web avec republication](media/web-sync05.gif "Synchronisation web avec republication")</span><span class="sxs-lookup"><span data-stu-id="72885-128">![Web synchronization with republishing](media/web-sync05.gif "Web synchronization with republishing")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72885-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="72885-129">See Also</span></span>  
 <span data-ttu-id="72885-130">[Configurer la synchronisation web](configure-web-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="72885-130">[Configure Web Synchronization](configure-web-synchronization.md) </span></span>  
 [<span data-ttu-id="72885-131">Synchronisation web pour la réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="72885-131">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
