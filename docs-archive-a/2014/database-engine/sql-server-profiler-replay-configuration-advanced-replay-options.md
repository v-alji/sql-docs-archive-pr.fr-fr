---
title: SQL Server Profiler-configuration de la relecture (options de relecture avancées) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.generaloptions.advanced.f1
helpviewer_keywords:
- Replay Configuration dialog box
ms.assetid: b4eb34f7-3af6-4a44-ba7e-2b8430ec3cd7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95070d8defb5b7778859ce470aaa8cfc85955ba6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705371"
---
# <a name="sql-server-profiler---replay-configuration-advanced-replay-options"></a><span data-ttu-id="c16a7-102">Générateur de profils SQL Server - Configuration de la relecture (Options de relecture avancées)</span><span class="sxs-lookup"><span data-stu-id="c16a7-102">SQL Server Profiler - Replay Configuration (Advanced Replay Options)</span></span>
  <span data-ttu-id="c16a7-103">Dans la boîte de dialogue **Configuration de la relecture** , utilisez l’onglet **Options de relecture avancées** pour spécifier le mode de relecture d’un fichier de trace.</span><span class="sxs-lookup"><span data-stu-id="c16a7-103">In the **Replay Configuration** dialog box, use the **Advanced Replay Options** tab to specify how to replay a trace file.</span></span>  
  
 <span data-ttu-id="c16a7-104">Pour afficher cette fenêtre, utilisez le [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] pour ouvrir un fichier de trace ou une table qui contient les événements appropriés pour la relecture.</span><span class="sxs-lookup"><span data-stu-id="c16a7-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace file or table that contains the appropriate events for replay.</span></span> <span data-ttu-id="c16a7-105">Pour plus d’informations, consultez [Conditions préalables à la relecture](../tools/sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c16a7-105">For more information, see [Replay Requirements](../tools/sql-server-profiler/replay-requirements.md).</span></span> <span data-ttu-id="c16a7-106">Après avoir ouvert le fichier de trace ou la table, dans le menu **Relecture** , cliquez sur **Démarrer**, connectez-vous à l’instance de SQL Server sur laquelle vous voulez relire la trace, puis cliquez sur l’onglet **Options de relecture avancées** .</span><span class="sxs-lookup"><span data-stu-id="c16a7-106">While the trace file or table is open, on the **Replay** menu, click **Start**, connect to the instance of SQL Server where you want to replay the trace, and then click the **Advanced Replay Options** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c16a7-107">Options</span><span class="sxs-lookup"><span data-stu-id="c16a7-107">Options</span></span>  
 <span data-ttu-id="c16a7-108">**Relire les SPID système**</span><span class="sxs-lookup"><span data-stu-id="c16a7-108">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="c16a7-109">Spécifie si le [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] relit les SPID système.</span><span class="sxs-lookup"><span data-stu-id="c16a7-109">Specifies whether [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] replays system process identifiers (SPIDs).</span></span>  
  
 <span data-ttu-id="c16a7-110">**Relire un SPID uniquement**</span><span class="sxs-lookup"><span data-stu-id="c16a7-110">**Replay one SPID only**</span></span>  
 <span data-ttu-id="c16a7-111">Ne relit que l'activité du fichier de trace source qui est relative au SPID sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c16a7-111">Replays only the activity in the source trace file that is related to the selected SPID.</span></span>  
  
 <span data-ttu-id="c16a7-112">**SPID à relire**</span><span class="sxs-lookup"><span data-stu-id="c16a7-112">**SPID to replay**</span></span>  
 <span data-ttu-id="c16a7-113">Spécifiez le SPID à relire.</span><span class="sxs-lookup"><span data-stu-id="c16a7-113">Specify which SPID to replay.</span></span>  
  
 <span data-ttu-id="c16a7-114">**Limiter la relecture par date et heure**</span><span class="sxs-lookup"><span data-stu-id="c16a7-114">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="c16a7-115">Activez cette option pour ne relire qu'une partie du fichier de trace source.</span><span class="sxs-lookup"><span data-stu-id="c16a7-115">Check to replay only a portion of the source trace file.</span></span>  
  
 <span data-ttu-id="c16a7-116">**Heure de début**</span><span class="sxs-lookup"><span data-stu-id="c16a7-116">**Start time**</span></span>  
 <span data-ttu-id="c16a7-117">Date et heure auxquelles la relecture doit commencer dans le fichier de trace source.</span><span class="sxs-lookup"><span data-stu-id="c16a7-117">Date and time in the source trace file where the replay should start.</span></span>  
  
 <span data-ttu-id="c16a7-118">**Heure de fin**</span><span class="sxs-lookup"><span data-stu-id="c16a7-118">**End time**</span></span>  
 <span data-ttu-id="c16a7-119">Date et heure auxquelles la relecture doit se terminer dans le fichier de trace source.</span><span class="sxs-lookup"><span data-stu-id="c16a7-119">Date and time in the source trace file where the replay should stop.</span></span>  
  
 <span data-ttu-id="c16a7-120">**Délai d'attente du moniteur d'intégrité (sec.)**</span><span class="sxs-lookup"><span data-stu-id="c16a7-120">**Health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="c16a7-121">Spécifiez le délai d'attente de la relecture, en secondes.</span><span class="sxs-lookup"><span data-stu-id="c16a7-121">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="c16a7-122">La valeur par défaut est 3 600 secondes (1 heure).</span><span class="sxs-lookup"><span data-stu-id="c16a7-122">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="c16a7-123">Ce paramètre affecte la durée d'exécution d'un processus autorisée avant son interruption par le moniteur d'intégrité.</span><span class="sxs-lookup"><span data-stu-id="c16a7-123">This setting affects the amount of time a process is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="c16a7-124">**Intervalle d'interrogation du moniteur d'intégrité par défaut (sec)**</span><span class="sxs-lookup"><span data-stu-id="c16a7-124">**Health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="c16a7-125">Spécifiez, en secondes, l'intervalle d'interrogation du moniteur d'intégrité pendant la relecture.</span><span class="sxs-lookup"><span data-stu-id="c16a7-125">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="c16a7-126">La valeur par défaut est 60 secondes.</span><span class="sxs-lookup"><span data-stu-id="c16a7-126">Default is 60 seconds.</span></span> <span data-ttu-id="c16a7-127">Cette valeur permet à l'utilisateur de configurer la fréquence à laquelle le moniteur d'intégrité interroge les candidats à l'arrêt.</span><span class="sxs-lookup"><span data-stu-id="c16a7-127">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
 <span data-ttu-id="c16a7-128">**Activer le moniteur de processus bloqués de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="c16a7-128">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="c16a7-129">Active un processus qui recherche les processus bloqués ou les processus de blocage.</span><span class="sxs-lookup"><span data-stu-id="c16a7-129">Enables a process that searches for blocked or blocking processes.</span></span>  
  
 <span data-ttu-id="c16a7-130">**Délai d'attente du moniteur de processus bloqués (s)**</span><span class="sxs-lookup"><span data-stu-id="c16a7-130">**Blocked processes monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="c16a7-131">Configure la fréquence à laquelle le moniteur de processus recherche les processus bloqués ou les processus de blocage.</span><span class="sxs-lookup"><span data-stu-id="c16a7-131">Configures how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c16a7-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c16a7-132">See Also</span></span>  
 <span data-ttu-id="c16a7-133">[Relire une table de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c16a7-133">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c16a7-134">[Relire un fichier de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c16a7-134">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="c16a7-135">Relire des traces</span><span class="sxs-lookup"><span data-stu-id="c16a7-135">Replay Traces</span></span>](../tools/sql-server-profiler/replay-traces.md)  
  
  
