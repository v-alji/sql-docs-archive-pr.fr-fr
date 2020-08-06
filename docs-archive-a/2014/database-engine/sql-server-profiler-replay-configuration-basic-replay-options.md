---
title: SQL Server Profiler-configuration de la relecture (options de relecture de base) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: 85a1dec6-9bbc-477a-86c5-b463db9ebb31
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cbf433c3108294909d91f7860136c0755b39b46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705367"
---
# <a name="sql-server-profiler---replay-configuration-basic-replay-options"></a><span data-ttu-id="061e9-102">Générateur de profils SQL Server – Configuration de la relecture (Options de relecture de base)</span><span class="sxs-lookup"><span data-stu-id="061e9-102">SQL Server Profiler - Replay Configuration (Basic Replay Options)</span></span>
  <span data-ttu-id="061e9-103">Dans la boîte de dialogue **Configuration de la relecture**, utilisez la page **Options de relecture de base** pour spécifier la manière de relire un fichier ou une table de trace.</span><span class="sxs-lookup"><span data-stu-id="061e9-103">In the **Replay Configuration** dialog box, use the **Basic Replay Options** page to specify how to replay a trace file or table.</span></span>  
  
 <span data-ttu-id="061e9-104">Pour afficher cette fenêtre, utilisez le [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] pour ouvrir un fichier de trace ou une table qui contient les événements appropriés pour la relecture.</span><span class="sxs-lookup"><span data-stu-id="061e9-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="061e9-105">Pour plus d’informations, consultez [Conditions préalables à la relecture](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="061e9-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="061e9-106">Lorsque le fichier ou la table de trace est ouvert, dans le menu **Relire** , cliquez sur **Début**, puis connectez-vous à l’instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] dans laquelle vous voulez relire la trace.</span><span class="sxs-lookup"><span data-stu-id="061e9-106">While the trace file or table is open, on the **Replay** menu, click **Start**, and then connect to the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where you want to replay the trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="061e9-107">Options</span><span class="sxs-lookup"><span data-stu-id="061e9-107">Options</span></span>  
 <span data-ttu-id="061e9-108">**Serveur de relecture**</span><span class="sxs-lookup"><span data-stu-id="061e9-108">**Replay server**</span></span>  
 <span data-ttu-id="061e9-109">Affiche l'instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à laquelle se connecter pour la relecture.</span><span class="sxs-lookup"><span data-stu-id="061e9-109">Displays the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to connect to for the replay.</span></span>  
  
 <span data-ttu-id="061e9-110">**Modifier...**</span><span class="sxs-lookup"><span data-stu-id="061e9-110">**Change...**</span></span>  
 <span data-ttu-id="061e9-111">Affiche la boîte de dialogue **Se connecter au serveur** pour se connecter à un autre serveur.</span><span class="sxs-lookup"><span data-stu-id="061e9-111">Launches the **Connect to Server** dialog box to connect to another server.</span></span>  
  
 <span data-ttu-id="061e9-112">**Enregistrer dans le fichier**</span><span class="sxs-lookup"><span data-stu-id="061e9-112">**Save to file**</span></span>  
 <span data-ttu-id="061e9-113">Permet d'enregistrer les résultats de relecture dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="061e9-113">Save the replay results to a file.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="061e9-114">affiche la boîte de dialogue de fichier standard, qui vous permet de spécifier l’emplacement où enregistrer le fichier.</span><span class="sxs-lookup"><span data-stu-id="061e9-114">displays the standard file dialog, where you can specify the location to save the file.</span></span>  
  
 <span data-ttu-id="061e9-115">**Enregistrer dans la table**</span><span class="sxs-lookup"><span data-stu-id="061e9-115">**Save to table**</span></span>  
 <span data-ttu-id="061e9-116">Permet d'enregistrer les résultats de relecture dans une table.</span><span class="sxs-lookup"><span data-stu-id="061e9-116">Save the replay results to a table.</span></span> [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="061e9-117">affiche la boîte de dialogue de sélection de table, qui vous permet de spécifier l’emplacement où enregistrer la table.</span><span class="sxs-lookup"><span data-stu-id="061e9-117">displays the table selection dialog, where you can specify the location to save the table.</span></span>  
  
 <span data-ttu-id="061e9-118">**Nombre de threads de relecture**</span><span class="sxs-lookup"><span data-stu-id="061e9-118">**Number of replay threads**</span></span>  
 <span data-ttu-id="061e9-119">Spécifiez le nombre de threads de relecture à utiliser simultanément.</span><span class="sxs-lookup"><span data-stu-id="061e9-119">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="061e9-120">Plus ce nombre est important, plus la relecture consomme de ressources, mais plus elle est rapide.</span><span class="sxs-lookup"><span data-stu-id="061e9-120">A higher number consumes more resources during replay, but replay is faster and more concurrent.</span></span>  
  
 <span data-ttu-id="061e9-121">**Relire les événements selon leur ordre de suivi**</span><span class="sxs-lookup"><span data-stu-id="061e9-121">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="061e9-122">Permet de relire les événements de manière séquentielle.</span><span class="sxs-lookup"><span data-stu-id="061e9-122">Replay events sequentially.</span></span> <span data-ttu-id="061e9-123">Utilisez cette option pour relire une trace pour un débogage.</span><span class="sxs-lookup"><span data-stu-id="061e9-123">Use this option if you are replaying a trace for debugging.</span></span>  
  
 <span data-ttu-id="061e9-124">**Relire les événements en utilisant plusieurs threads**</span><span class="sxs-lookup"><span data-stu-id="061e9-124">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="061e9-125">Permet de relire les événements de manière simultanée.</span><span class="sxs-lookup"><span data-stu-id="061e9-125">Replay events concurrently.</span></span> <span data-ttu-id="061e9-126">Cette option est plus rapide que la relecture séquentielle des événements, mais elle désactive le débogage.</span><span class="sxs-lookup"><span data-stu-id="061e9-126">This option is faster than replaying events sequentially, but disables debugging.</span></span> <span data-ttu-id="061e9-127">Les événements sont ordonnés à l'aide de leurs identificateurs de processus système (SPID).</span><span class="sxs-lookup"><span data-stu-id="061e9-127">The events are ordered within their system process identifiers (SPID).</span></span>  
  
 <span data-ttu-id="061e9-128">**Afficher les résultats de relecture**</span><span class="sxs-lookup"><span data-stu-id="061e9-128">**Display replay results**</span></span>  
 <span data-ttu-id="061e9-129">Permet d'afficher les résultats de relecture dans [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="061e9-129">Display replay results in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="061e9-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="061e9-130">See Also</span></span>  
 <span data-ttu-id="061e9-131">[Relire une table de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="061e9-131">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="061e9-132">[Relire un fichier de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="061e9-132">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="061e9-133">Relire des traces</span><span class="sxs-lookup"><span data-stu-id="061e9-133">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
