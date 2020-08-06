---
title: Options de relecture (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
- health monitor [SQL Server]
- Replay Configuration dialog box
ms.assetid: 58761a25-a84f-4a90-9c61-97700bc5ad9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 695a1431145813f0a7829626a380e510d0e602e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705736"
---
# <a name="replay-options-sql-server-profiler"></a><span data-ttu-id="cbacf-102">Options de relecture (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="cbacf-102">Replay Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="cbacf-103">Avant de relire une trace capturée avec [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], spécifiez les options de relecture dans la boîte de dialogue **Configuration de la relecture** .</span><span class="sxs-lookup"><span data-stu-id="cbacf-103">Before replaying a captured trace with [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], specify replay options in the **Replay Configuration** dialog box.</span></span> <span data-ttu-id="cbacf-104">Pour accéder à cette boîte de dialogue, ouvrez le fichier ou la table de trace de relecture dans [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], puis cliquez sur **Démarrer** dans le menu **Relire**.</span><span class="sxs-lookup"><span data-stu-id="cbacf-104">To launch this dialog box, open the replay trace file or table in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and on the **Replay** menu, click **Start**.</span></span> <span data-ttu-id="cbacf-105">Pour savoir quelles autorisations sont nécessaires pour relire une trace, consultez [Autorisations nécessaires pour exécuter SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="cbacf-105">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="cbacf-106">Cette rubrique décrit les options spécifiées avec la boîte de dialogue **Configuration de la relecture** .</span><span class="sxs-lookup"><span data-stu-id="cbacf-106">This topic describes the options specified with the **Replay Configuration** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbacf-107">Nous recommandons d'utiliser Distributed Replay Utility pour relire des applications OLTP exigeantes (avec de nombreuses connexions simultanées actives ou un débit élevé).</span><span class="sxs-lookup"><span data-stu-id="cbacf-107">We recommend using the Distributed Replay Utility for replaying an intensive OLTP application (with many active concurrent connections or high throughput).</span></span> <span data-ttu-id="cbacf-108">Distributed Replay Utility peut relire les données de trace de plusieurs ordinateurs, en simulant mieux les charges de travail sensibles.</span><span class="sxs-lookup"><span data-stu-id="cbacf-108">The Distributed Replay Utility can replay trace data from multiple computers, better simulating a mission-critical workload.</span></span> <span data-ttu-id="cbacf-109">Pour plus d'informations, consultez [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="cbacf-109">For more information, see [SQL Server Distributed Replay](../distributed-replay/sql-server-distributed-replay.md).</span></span>  
  
## <a name="basic-replay-options"></a><span data-ttu-id="cbacf-110">Options de relecture de base</span><span class="sxs-lookup"><span data-stu-id="cbacf-110">Basic Replay Options</span></span>  
 <span data-ttu-id="cbacf-111">**Serveur de relecture**</span><span class="sxs-lookup"><span data-stu-id="cbacf-111">**Replay server**</span></span>  
 <span data-ttu-id="cbacf-112">Le serveur est le nom de l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur lequel vous souhaitez relire la trace.</span><span class="sxs-lookup"><span data-stu-id="cbacf-112">The server is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] against which you want to replay the trace.</span></span> <span data-ttu-id="cbacf-113">Le serveur doit remplir les conditions préalables de relecture mentionnées dans la section [Conditions préalables à la relecture](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbacf-113">The server must adhere to the replay requirements described in [Replay Requirements](replay-requirements.md)."</span></span>  
  
 <span data-ttu-id="cbacf-114">**Enregistrer dans le fichier**</span><span class="sxs-lookup"><span data-stu-id="cbacf-114">**Save to file**</span></span>  
 <span data-ttu-id="cbacf-115">Le fichier de sortie contenant le résultat de la relecture de la trace est écrit et pourra être affiché ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="cbacf-115">The output file where the result of replaying the trace is written for later viewing.</span></span> <span data-ttu-id="cbacf-116">Par défaut, le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] n'affiche à l'écran que les résultats de la relecture de la trace.</span><span class="sxs-lookup"><span data-stu-id="cbacf-116">By default, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] displays only the results of replaying the trace on the screen.</span></span>  
  
 <span data-ttu-id="cbacf-117">**Enregistrer dans la table**</span><span class="sxs-lookup"><span data-stu-id="cbacf-117">**Save to table**</span></span>  
 <span data-ttu-id="cbacf-118">La table de base de données contenant le résultat de la relecture de la trace est écrite et pourra être affichée ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="cbacf-118">The database table where the result of replaying the trace is written for later viewing.</span></span>  
  
 <span data-ttu-id="cbacf-119">**Nombre de threads de relecture**</span><span class="sxs-lookup"><span data-stu-id="cbacf-119">**Number of replay threads**</span></span>  
 <span data-ttu-id="cbacf-120">Spécifiez le nombre de threads de relecture à utiliser simultanément.</span><span class="sxs-lookup"><span data-stu-id="cbacf-120">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="cbacf-121">Un nombre élevé consomme davantage de ressources pendant la relecture, mais accélère la relecture.</span><span class="sxs-lookup"><span data-stu-id="cbacf-121">A higher number consumes more resources during replay, but replay is faster.</span></span> <span data-ttu-id="cbacf-122">L'ordre des événements n'est pas totalement conservé en cas d'utilisation de plusieurs threads.</span><span class="sxs-lookup"><span data-stu-id="cbacf-122">Event ordering is not fully maintained when multiple threads are used.</span></span>  
  
 <span data-ttu-id="cbacf-123">**Relire les événements selon leur ordre de suivi**</span><span class="sxs-lookup"><span data-stu-id="cbacf-123">**Replay events in the order they were traced**</span></span>  
 <span data-ttu-id="cbacf-124">Permet d’utiliser des méthodes de débogage telles que la trace pas à pas dans chaque trace.</span><span class="sxs-lookup"><span data-stu-id="cbacf-124">Allows you to use debugging methods such as stepping through each trace.</span></span> <span data-ttu-id="cbacf-125">Si cette option n'est pas sélectionnée, la relecture ne garantit pas que les événements sont relus dans un ordre cohérent avec l'ordre de leur capture initiale.</span><span class="sxs-lookup"><span data-stu-id="cbacf-125">If this option is not selected, replay does not guarantee that events are replayed in an order that is consistent with the order in which events were originally captured.</span></span>  
  
 <span data-ttu-id="cbacf-126">**Relire les événements en utilisant plusieurs threads**</span><span class="sxs-lookup"><span data-stu-id="cbacf-126">**Replay events using multiple threads**</span></span>  
 <span data-ttu-id="cbacf-127">Optimise les performances et désactive le débogage.</span><span class="sxs-lookup"><span data-stu-id="cbacf-127">Optimizes performance and disables debugging.</span></span> <span data-ttu-id="cbacf-128">Les événements sont relus dans l'ordre dans lequel ils ont été enregistrés pour un SPID (ID du processus serveur) particulier, mais l'ordre des SPID n'est pas garanti.</span><span class="sxs-lookup"><span data-stu-id="cbacf-128">Events are replayed in the order they were recorded for a particular server process ID (SPID), but ordering of SPIDs is not guaranteed.</span></span>  
  
 <span data-ttu-id="cbacf-129">**Afficher les résultats de relecture**</span><span class="sxs-lookup"><span data-stu-id="cbacf-129">**Display replay results**</span></span>  
 <span data-ttu-id="cbacf-130">Affiche les résultats de la relecture.</span><span class="sxs-lookup"><span data-stu-id="cbacf-130">Display the results of the replay.</span></span> <span data-ttu-id="cbacf-131">Il s'agit de l'option par défaut.</span><span class="sxs-lookup"><span data-stu-id="cbacf-131">This is the default option.</span></span> <span data-ttu-id="cbacf-132">Si la trace que vous relisez est très importante, vous pouvez désactiver cette option pour libérer de l’espace disque.</span><span class="sxs-lookup"><span data-stu-id="cbacf-132">If the trace you are replaying is very large, you may want to disable this to save disk space.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cbacf-133">Pour des performances de relecture optimales, il est recommandé de sélectionner de relire les événements à l’aide de plusieurs threads, et de ne pas choisir d'afficher les résultats de la relecture.</span><span class="sxs-lookup"><span data-stu-id="cbacf-133">For best replay performance, we recommend that you select to replay events using multiple threads, and do not select to display the replay results.</span></span>  
  
## <a name="advanced-replay-options"></a><span data-ttu-id="cbacf-134">Options de relecture avancées</span><span class="sxs-lookup"><span data-stu-id="cbacf-134">Advanced Replay Options</span></span>  
 <span data-ttu-id="cbacf-135">**Relire les SPID système**</span><span class="sxs-lookup"><span data-stu-id="cbacf-135">**Replay system SPIDs**</span></span>  
 <span data-ttu-id="cbacf-136">Relit tous les SPID.</span><span class="sxs-lookup"><span data-stu-id="cbacf-136">Replay all SPIDs.</span></span> <span data-ttu-id="cbacf-137">Il s'agit de l'option par défaut.</span><span class="sxs-lookup"><span data-stu-id="cbacf-137">This is the default option.</span></span>  
  
 <span data-ttu-id="cbacf-138">**Relire un SPID uniquement**</span><span class="sxs-lookup"><span data-stu-id="cbacf-138">**Replay one SPID only**</span></span>  
 <span data-ttu-id="cbacf-139">Relit le numéro de SPID que vous choisissez dans la liste.</span><span class="sxs-lookup"><span data-stu-id="cbacf-139">Replays the SPID number you choose from the list.</span></span>  
  
 <span data-ttu-id="cbacf-140">**Limiter la relecture par date et heure**</span><span class="sxs-lookup"><span data-stu-id="cbacf-140">**Limit replay by date and time**</span></span>  
 <span data-ttu-id="cbacf-141">Relit la trace pour l’ **Heure de début** et l’ **Heure de fin**spécifiées.</span><span class="sxs-lookup"><span data-stu-id="cbacf-141">Replays the trace for the specified **Start time** and **End time**.</span></span>  
  
 <span data-ttu-id="cbacf-142">**Délai d'attente du moniteur d'intégrité**</span><span class="sxs-lookup"><span data-stu-id="cbacf-142">**Health monitor wait interval**</span></span>  
 <span data-ttu-id="cbacf-143">Définit la durée pendant laquelle un processus est autorisé à s'exécuter avant que le moniteur d'intégrité y mette fin.</span><span class="sxs-lookup"><span data-stu-id="cbacf-143">Sets the amount of time a process is allowed to run before the health monitor terminates it.</span></span>  
  
 <span data-ttu-id="cbacf-144">**Intervalle d'interrogation du moniteur d'intégrité**</span><span class="sxs-lookup"><span data-stu-id="cbacf-144">**Health monitor poll interval**</span></span>  
 <span data-ttu-id="cbacf-145">Définit la fréquence à laquelle le moniteur d'intégrité interroge les candidats pour les arrêter.</span><span class="sxs-lookup"><span data-stu-id="cbacf-145">Sets how often the health monitor polls candidates for termination.</span></span>  
  
 <span data-ttu-id="cbacf-146">**Activer le moniteur de processus bloqués de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="cbacf-146">**Enable SQL Server blocked processes monitor**</span></span>  
 <span data-ttu-id="cbacf-147">Définit la fréquence à laquelle le moniteur de processus recherche les processus bloqués ou les processus de blocage.</span><span class="sxs-lookup"><span data-stu-id="cbacf-147">Sets how often the blocked processes monitor searches for blocked or blocking processes.</span></span>  
  
## <a name="about-the-health-monitor"></a><span data-ttu-id="cbacf-148">À propos du moniteur d'intégrité</span><span class="sxs-lookup"><span data-stu-id="cbacf-148">About the Health Monitor</span></span>  
 <span data-ttu-id="cbacf-149">Le moniteur d'intégrité est un thread d'application qui surveille les processus simulés impliqués dans la relecture d'une trace, et met fin aux processus bloqués au cours de la relecture.</span><span class="sxs-lookup"><span data-stu-id="cbacf-149">The health monitor is an application thread that monitors the simulated processes involved in replaying a trace, and ends those processes that are blocked within the replay.</span></span> <span data-ttu-id="cbacf-150">Sous l’onglet **Options de relecture avancées** de la boîte de dialogue **Configuration de la relecture** , vous pouvez spécifier combien de temps le moniteur d’intégrité doit attendre (en secondes) avant de mettre fin à un processus bloqué (**Délai d’attente du moniteur d’intégrité**).</span><span class="sxs-lookup"><span data-stu-id="cbacf-150">In the **Advanced Replay Options** tab of the **Replay Configuration** dialog box, you can specify how long the health monitor should wait in seconds before ending a blocked process (**Health monitor wait interval**).</span></span> <span data-ttu-id="cbacf-151">Si vous affectez à cet intervalle la valeur 0, le moniteur d'intégrité ne met jamais fin aux processus de blocage simulés dans la trace en cours de relecture.</span><span class="sxs-lookup"><span data-stu-id="cbacf-151">If you set this interval to 0, the health monitor never ends simulated blocking processes in the replaying trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbacf-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbacf-152">See Also</span></span>  
 <span data-ttu-id="cbacf-153">[Relire des traces](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="cbacf-153">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="cbacf-154">[Conditions requises pour la relecture](replay-requirements.md) </span><span class="sxs-lookup"><span data-stu-id="cbacf-154">[Replay Requirements](replay-requirements.md) </span></span>  
 [<span data-ttu-id="cbacf-155">Considérations sur la relecture des traces &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="cbacf-155">Considerations for Replaying Traces &#40;SQL Server Profiler&#41;</span></span>](considerations-for-replaying-traces-sql-server-profiler.md)  
  
  
