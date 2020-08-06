---
title: Relire une table de trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 6a0ad817-3d8d-4495-889d-c66a7ef9e8bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: f3c26858fa852686bc3d9ccf4a26d47e04852647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702219"
---
# <a name="replay-a-trace-table-sql-server-profiler"></a><span data-ttu-id="c9604-102">Relire une table de trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c9604-102">Replay a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="c9604-103">La relecture est la possibilité d'ouvrir une trace enregistrée et de la relire.</span><span class="sxs-lookup"><span data-stu-id="c9604-103">Replay is the ability to open a saved trace and replay it again.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="c9604-104">contient un moteur de lecture à plusieurs threads capable de simuler les connexions utilisateur et l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9604-104">features a multithreaded playback engine that can simulate user connections and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="c9604-105">La relecture est utile pour résoudre les problèmes d'applications ou de processus.</span><span class="sxs-lookup"><span data-stu-id="c9604-105">Replay is useful to troubleshoot an application or process problem.</span></span> <span data-ttu-id="c9604-106">Lorsque vous identifiez le problème et appliquez des corrections, exécutez la trace qui a détecté le problème potentiel sur l'application ou le processus corrigé.</span><span class="sxs-lookup"><span data-stu-id="c9604-106">When you identify the problem and implement corrections, run the trace that found the potential problem against the corrected application or process.</span></span> <span data-ttu-id="c9604-107">Relisez ensuite la trace d'origine et comparez les résultats.</span><span class="sxs-lookup"><span data-stu-id="c9604-107">Then, replay the original trace and compare results.</span></span>  
  
 <span data-ttu-id="c9604-108">En plus des autres classes d'événements que vous voulez analyser, des classes d'événements spécifiques doivent être capturées pour permettre la relecture.</span><span class="sxs-lookup"><span data-stu-id="c9604-108">In addition to any other event classes you want to monitor, specific event classes must be captured to enable replay.</span></span> <span data-ttu-id="c9604-109">Ces événements sont capturés par défaut si vous utilisez le modèle de trace **TSQL_Replay** .</span><span class="sxs-lookup"><span data-stu-id="c9604-109">These events are captured by default if you use the **TSQL_Replay** trace template.</span></span> <span data-ttu-id="c9604-110">Pour plus d’informations, consultez [Conditions préalables à la relecture](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9604-110">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
### <a name="to-replay-a-trace-table"></a><span data-ttu-id="c9604-111">Pour relire une table de trace</span><span class="sxs-lookup"><span data-stu-id="c9604-111">To replay a trace table</span></span>  
  
1.  <span data-ttu-id="c9604-112">Ouvrez une table de trace contenant les classes d'événements nécessaires à la relecture.</span><span class="sxs-lookup"><span data-stu-id="c9604-112">Open a trace table that contains the event classes necessary for replay.</span></span>  
  
2.  <span data-ttu-id="c9604-113">Dans le menu **Relire** , cliquez sur **Démarrer**, puis connectez-vous à l’instance de serveur sur laquelle vous voulez relire la trace.</span><span class="sxs-lookup"><span data-stu-id="c9604-113">On the **Replay** menu, click **Start**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="c9604-114">Dans la boîte de dialogue **Configuration de la relecture** , sous l’onglet **Options de relecture de base** , spécifiez **Serveur de relecture**.</span><span class="sxs-lookup"><span data-stu-id="c9604-114">In the **Replay Configuration** dialog box, on the **Basic Replay Options** tab, specify **Replay server**.</span></span> <span data-ttu-id="c9604-115">Cliquez sur **Modifier** pour modifier le serveur affiché dans la zone **Serveur de relecture** .</span><span class="sxs-lookup"><span data-stu-id="c9604-115">Click **Change** to change the server that is displayed in the **Replay server** box.</span></span>  
  
4.  <span data-ttu-id="c9604-116">Si vous le souhaitez, sélectionnez l'une des destinations suivantes afin d'y enregistrer la relecture :</span><span class="sxs-lookup"><span data-stu-id="c9604-116">Optionally, select one of the following destinations in which to save the replay:</span></span>  
  
    -   <span data-ttu-id="c9604-117">**Enregistrer dans le fichier** , ce qui spécifie un fichier dans lequel la relecture sera enregistrée.</span><span class="sxs-lookup"><span data-stu-id="c9604-117">**Save to file,** which specifies a file in which to save the replay.</span></span>  
  
    -   <span data-ttu-id="c9604-118">**Enregistrer dans la table**: spécifie une table de la base de données dans laquelle la relecture sera enregistrée.</span><span class="sxs-lookup"><span data-stu-id="c9604-118">**Save to table**, which specifies a database table in which to save the replay.</span></span>  
  
5.  <span data-ttu-id="c9604-119">Choisissez **Relire les événements selon leur ordre de suivi**ou **Relire les événements en utilisant plusieurs threads**.</span><span class="sxs-lookup"><span data-stu-id="c9604-119">Choose either **Replay the events in the order they were traced**or **Replay events using multiple threads**.</span></span> <span data-ttu-id="c9604-120">Le tableau suivant explique la différence entre ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="c9604-120">The following table explains the difference between these settings.</span></span>  
  
    |<span data-ttu-id="c9604-121">Option</span><span class="sxs-lookup"><span data-stu-id="c9604-121">Option</span></span>|<span data-ttu-id="c9604-122">Description</span><span class="sxs-lookup"><span data-stu-id="c9604-122">Description</span></span>|  
    |------------|-----------------|  
    |<span data-ttu-id="c9604-123">**Relire les événements selon leur ordre de suivi**</span><span class="sxs-lookup"><span data-stu-id="c9604-123">**Replay events in the order they were traced**</span></span>|<span data-ttu-id="c9604-124">Permet de relire les événements selon l'ordre dans lequel ils ont été enregistrés.</span><span class="sxs-lookup"><span data-stu-id="c9604-124">Replays events in the order they were recorded.</span></span> <span data-ttu-id="c9604-125">Cette option active le débogage.</span><span class="sxs-lookup"><span data-stu-id="c9604-125">This option enables debugging.</span></span>|  
    |<span data-ttu-id="c9604-126">**Relire les événements en utilisant plusieurs threads**</span><span class="sxs-lookup"><span data-stu-id="c9604-126">**Replay events using multiple threads**</span></span>|<span data-ttu-id="c9604-127">Cette option utilise plusieurs threads pour relire chaque événement indépendamment de la séquence.</span><span class="sxs-lookup"><span data-stu-id="c9604-127">This option uses multiple threads to replay each event regardless of the sequence.</span></span> <span data-ttu-id="c9604-128">Cette option optimise les performances.</span><span class="sxs-lookup"><span data-stu-id="c9604-128">This option optimizes performance.</span></span>|  
  
6.  <span data-ttu-id="c9604-129">Sélectionnez **Afficher les résultats de relecture** pour consulter la relecture lorsqu’elle a lieu.</span><span class="sxs-lookup"><span data-stu-id="c9604-129">Select **Display replay results** to view the replay as it occurs.</span></span>  
  
7.  <span data-ttu-id="c9604-130">Vous pouvez aussi cliquer sur l’onglet **Options de relecture avancées**pour spécifier les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c9604-130">Optionally, click the **Advanced Replay Options**tab to specify the following options:</span></span>  
  
    -   <span data-ttu-id="c9604-131">Pour relire tous les ID de processus de serveur (SPID), sélectionnez **Relire les SPID système**.</span><span class="sxs-lookup"><span data-stu-id="c9604-131">To replay all server process IDs (SPIDs), select **Replay system SPIDs**.</span></span>  
  
    -   <span data-ttu-id="c9604-132">Pour limiter la relecture aux processus appartenant à un SPID spécifique, sélectionnez **Relire un SPID uniquement**.</span><span class="sxs-lookup"><span data-stu-id="c9604-132">To limit the replay to processes belonging to a specific SPID, select **Replay one SPID only**.</span></span> <span data-ttu-id="c9604-133">Dans la zone **SPID à relire**, tapez le SPID.</span><span class="sxs-lookup"><span data-stu-id="c9604-133">In the **SPID to replay**box, type the SPID.</span></span>  
  
    -   <span data-ttu-id="c9604-134">Pour relire les événements qui se sont produits pendant une période de temps spécifique, sélectionnez **Limiter la relecture par date et heure**.</span><span class="sxs-lookup"><span data-stu-id="c9604-134">To replay events that occurred during a specific time period, select **Limit replay by date and time**.</span></span> <span data-ttu-id="c9604-135">Sélectionnez une date et une heure pour **Heure de début**et **Heure de fin**afin de spécifier la période à inclure dans la relecture.</span><span class="sxs-lookup"><span data-stu-id="c9604-135">Select a date and time for the **Start time**and **End time**to specify the time period to include in the replay.</span></span>  
  
    -   <span data-ttu-id="c9604-136">Pour contrôler la façon dont [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gère les processus pendant la relecture, configurez les **Options du moniteur d’intégrité**.</span><span class="sxs-lookup"><span data-stu-id="c9604-136">To control how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manages processes during replay, configure **Health Monitor Options**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9604-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9604-137">See Also</span></span>  
 <span data-ttu-id="c9604-138">[Autorisations nécessaires pour exécuter SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c9604-138">[Permissions Required to Run SQL Server Profiler](sql-server-profiler.md) </span></span>  
 <span data-ttu-id="c9604-139">[Relire des traces](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="c9604-139">[Replay Traces](replay-traces.md) </span></span>  
 <span data-ttu-id="c9604-140">[Ouvrir une table de trace &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="c9604-140">[Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="c9604-141">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c9604-141">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
