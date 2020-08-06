---
title: Moteur des Événements étendus SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], engine
ms.assetid: d74642a5-42b9-4a15-aa3d-f98bfe695050
author: rothja
ms.author: jroth
ms.openlocfilehash: ef11ac8e2cfaf39d2bca90f1d5d52439989ee327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600908"
---
# <a name="sql-server-extended-events-engine"></a><span data-ttu-id="ee6d8-102">Moteur des Événements étendus SQL Server</span><span class="sxs-lookup"><span data-stu-id="ee6d8-102">SQL Server Extended Events Engine</span></span>
  <span data-ttu-id="ee6d8-103">Le moteur des Événements étendus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est une collection de services et d'objets qui :</span><span class="sxs-lookup"><span data-stu-id="ee6d8-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events engine is a collection of services and objects that:</span></span>  
  
-   <span data-ttu-id="ee6d8-104">activent la définition d'événements ;</span><span class="sxs-lookup"><span data-stu-id="ee6d8-104">Enable the definition of events.</span></span>  
  
-   <span data-ttu-id="ee6d8-105">activent les données d'événement de traitement ;</span><span class="sxs-lookup"><span data-stu-id="ee6d8-105">Enable processing event data.</span></span>  
  
-   <span data-ttu-id="ee6d8-106">gèrent les services et objets des Événements étendus dans le système ;</span><span class="sxs-lookup"><span data-stu-id="ee6d8-106">Manage Extended Events services and objects in the system.</span></span>  
  
-   <span data-ttu-id="ee6d8-107">tiennent à jour une liste de sessions Événements étendus et gèrent l'accès à cette liste.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-107">Maintain a list of Extended Events sessions and manage access to that list.</span></span>  
  
 <span data-ttu-id="ee6d8-108">Le moteur des Événements étendus ne fournit lui-même aucun événement ni aucune action à entreprendre lors du déclenchement d'un événement.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-108">The Extended Events engine itself does not provide any events or actions to take when an event fires.</span></span> <span data-ttu-id="ee6d8-109">Les processus qui utilisent le moteur des Événements étendus définissent l'interaction avec le moteur.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-109">The processes that use the Extended Events engine define interaction with the engine.</span></span> <span data-ttu-id="ee6d8-110">Ces processus ajoutent des points d'événement et fournissent les actions à entreprendre en réponse au déclenchement d'un événement.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-110">These processes add event points and supply the actions to take in response to event firing.</span></span>  
  
 <span data-ttu-id="ee6d8-111">L'illustration ci-dessous montre une vue simplifiée d'une session Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-111">The following illustration shows a simplified view of an Extended Events session.</span></span> <span data-ttu-id="ee6d8-112">Pour plus d’informations, consultez [Sessions Événements étendus SQL Server](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-112">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
 <span data-ttu-id="ee6d8-113">![Architecture détaillée des événements étendus](../../database-engine/media/xearchitecturedetailed.gif "Architecture détaillée des événements étendus")</span><span class="sxs-lookup"><span data-stu-id="ee6d8-113">![Detailed extended events architecture](../../database-engine/media/xearchitecturedetailed.gif "Detailed extended events architecture")</span></span>  
  
 <span data-ttu-id="ee6d8-114">Notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="ee6d8-114">Note the following:</span></span>  
  
-   <span data-ttu-id="ee6d8-115">Chaque processus Windows peut avoir un ou plusieurs modules (**processus Win32**, **module Win32**).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-115">Each Windows process can have one or more modules (**Win32 process**, **Win32 module**).</span></span> <span data-ttu-id="ee6d8-116">Ils sont également appelés *binaires* ou *modules exécutables*.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-116">These are also known as *binaries* or *executable modules*.</span></span>  
  
-   <span data-ttu-id="ee6d8-117">Chaque module de processus Windows peut contenir un ou plusieurs packages des Événements étendus (**Package**), qui contiennent un ou plusieurs objets des Événements étendus (**Type**, **Cible**, **Action**, **Mappage**, **Prédicat**et **Événement**).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-117">Each of the Windows process modules can contain one or more Extended Events packages (**Package**), which contain one or more Extended Events objects (**Type**, **Target**, **Action**, **Map**, **Predicate**, and **Event**).</span></span>  
  
-   <span data-ttu-id="ee6d8-118">Au sein d’un processus hôte, il ne peut exister qu’une seule instance du moteur des Événements étendus (**Moteur des Événements étendus**), qui effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ee6d8-118">Inside a host process there can only be one instance of the Extended Events engine (**Extended event engine**), which:</span></span>  
  
    -   <span data-ttu-id="ee6d8-119">Gérer certains aspects de la session (par exemple, l'énumération des sessions).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-119">Manages some aspects of the session (for example, enumerating sessions).</span></span>  
  
    -   <span data-ttu-id="ee6d8-120">Traiter la distribution (**Répartiteur**).</span><span class="sxs-lookup"><span data-stu-id="ee6d8-120">Handles dispatching (**Dispatcher**).</span></span> <span data-ttu-id="ee6d8-121">Cela est similaire à un pool de threads.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-121">This is similar to a thread pool.</span></span>  
  
    -   <span data-ttu-id="ee6d8-122">Gérer les mémoires tampons (**Mémoire tampon**) pour les événements.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-122">Handles memory buffers (**Buffer**) for events.</span></span> <span data-ttu-id="ee6d8-123">Lorsque les mémoires tampons sont pleines, elles sont distribuées aux cibles.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-123">When buffers are filled, the buffers are dispatched to targets.</span></span>  
  
-   <span data-ttu-id="ee6d8-124">Une fois qu’une session a été créée et que les événements sont liés facultativement à la session (**Contexte de session**) :</span><span class="sxs-lookup"><span data-stu-id="ee6d8-124">After a session is created and events are optionally bound to the session (**Session context**):</span></span>  
  
    -   <span data-ttu-id="ee6d8-125">des instances de cibles (**Instance cible**) peuvent également être créées et ajoutées à la session ;</span><span class="sxs-lookup"><span data-stu-id="ee6d8-125">Instances of targets (**Target instance**) may be also be created and added to the session.</span></span>  
  
    -   <span data-ttu-id="ee6d8-126">lorsque les mémoires tampons sont pleines, elles sont distribuées aux cibles.</span><span class="sxs-lookup"><span data-stu-id="ee6d8-126">When buffers are filled, those buffers are dispatched to targets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee6d8-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee6d8-127">See Also</span></span>  
 [<span data-ttu-id="ee6d8-128">Événements étendus</span><span class="sxs-lookup"><span data-stu-id="ee6d8-128">Extended Events</span></span>](extended-events.md)  
  
  
