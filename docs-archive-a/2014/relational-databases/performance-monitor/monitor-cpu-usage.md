---
title: Surveiller l’utilisation de l’UC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server], CPU usage
- tuning databases [SQL Server], CPU usage
- processors [SQL Server], monitoring usage
- database performance [SQL Server], CPU usage
- monitoring CPU usage [SQL Server]
- server performance [SQL Server], CPU usage
- database monitoring [SQL Server], CPU usage
- monitoring [SQL Server], CPU usage
- processors [SQL Server]
- CPU [SQL Server], monitoring
- monitoring server performance [SQL Server], CPU usage
ms.assetid: 2a02a3b6-07b2-4ad0-8a24-670414d19812
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f08d49348fd25593f27a87f2b0123f7ce43e35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707408"
---
# <a name="monitor-cpu-usage"></a><span data-ttu-id="97bbf-102">Surveiller l'utilisation de l'UC</span><span class="sxs-lookup"><span data-stu-id="97bbf-102">Monitor CPU Usage</span></span>
  <span data-ttu-id="97bbf-103">Surveillez régulièrement une instance Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afin de déterminer si les taux d'utilisation de l'unité centrale restent dans des limites normales.</span><span class="sxs-lookup"><span data-stu-id="97bbf-103">Monitor an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically to determine whether CPU usage rates are within normal ranges.</span></span> <span data-ttu-id="97bbf-104">Un taux d'utilisation de l'unité centrale régulièrement élevé peut mettre en évidence le besoin d'une mise à niveau de celle-ci ou d'un ajout de plusieurs processeurs.</span><span class="sxs-lookup"><span data-stu-id="97bbf-104">A continually high rate of CPU usage may indicate the need to upgrade the CPU or add multiple processors.</span></span> <span data-ttu-id="97bbf-105">Sinon, si une application sollicite constamment l'unité centrale, cela implique un paramétrage incorrect ou une conception médiocre de cette dernière.</span><span class="sxs-lookup"><span data-stu-id="97bbf-105">Alternatively, a high CPU usage rate may indicate a poorly tuned or designed application.</span></span> <span data-ttu-id="97bbf-106">En optimisant l'application vous réduirez l'utilisation de l'unité centrale.</span><span class="sxs-lookup"><span data-stu-id="97bbf-106">Optimizing the application can lower CPU utilization.</span></span>  
  
 <span data-ttu-id="97bbf-107">Une bonne manière de déterminer ce besoin consiste à utiliser le compteur **Processeur : % Temps processeur** du Moniteur système.</span><span class="sxs-lookup"><span data-stu-id="97bbf-107">An efficient way to determine CPU usage is to use the **Processor:% Processor Time** counter in System Monitor.</span></span> <span data-ttu-id="97bbf-108">Ce compteur surveille le temps nécessaire à l'unité centrale pour traiter un thread inactif.</span><span class="sxs-lookup"><span data-stu-id="97bbf-108">This counter monitors the amount of time the CPU spends executing a thread that is not idle.</span></span> <span data-ttu-id="97bbf-109">Une valeur régulièrement comprise entre 80 et 90 % peut indiquer un besoin de mise à niveau de l'unité centrale ou d'ajout de processeurs.</span><span class="sxs-lookup"><span data-stu-id="97bbf-109">A consistent state of 80 percent to 90 percent may indicate the need to upgrade your CPU or add more processors.</span></span> <span data-ttu-id="97bbf-110">Dans le cas de systèmes multiprocesseurs, surveillez une instance séparée de ce compteur pour chaque processeur.</span><span class="sxs-lookup"><span data-stu-id="97bbf-110">For multiprocessor systems, monitor a separate instance of this counter for each processor.</span></span> <span data-ttu-id="97bbf-111">Cette valeur représente la somme du temps processeur pour un processeur spécifique.</span><span class="sxs-lookup"><span data-stu-id="97bbf-111">This value represents the sum of processor time on a specific processor.</span></span> <span data-ttu-id="97bbf-112">Pour déterminer la moyenne pour tous les processeurs, utilisez plutôt le compteur **Système : % temps total processeur** .</span><span class="sxs-lookup"><span data-stu-id="97bbf-112">To determine the average for all processors, use the **System: %Total Processor Time** counter instead.</span></span>  
  
 <span data-ttu-id="97bbf-113">Éventuellement, vous pouvez également surveiller les compteurs suivants pour contrôler l'utilisation du processeur :</span><span class="sxs-lookup"><span data-stu-id="97bbf-113">Optionally, you can also monitor the following counters to monitor processor usage:</span></span>  
  
-   <span data-ttu-id="97bbf-114">**Processeur : % temps privilégié**</span><span class="sxs-lookup"><span data-stu-id="97bbf-114">**Processor: % Privileged Time**</span></span>  
  
     <span data-ttu-id="97bbf-115">Indique en pourcentage le temps consacré par le processeur aux commandes du noyau Microsoft Windows, telles que l'exécution des requêtes d'E/S [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97bbf-115">Corresponds to the percentage of time the processor spends on execution of Microsoft Windows kernel commands, such as processing of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] I/O requests.</span></span> <span data-ttu-id="97bbf-116">Si ce compteur est constamment élevé lorsque les compteurs **Disque physique** le sont également, envisagez un sous-système de disque plus rapide ou efficace.</span><span class="sxs-lookup"><span data-stu-id="97bbf-116">If this counter is consistently high when the **Physical Disk** counters are high, consider installing a faster or more efficient disk subsystem.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="97bbf-117">Différents contrôleurs de disques et pilotes utilisent des durées variables de temps de traitement des noyaux.</span><span class="sxs-lookup"><span data-stu-id="97bbf-117">Different disk controllers and drivers use different amounts of kernel processing time.</span></span> <span data-ttu-id="97bbf-118">Des contrôleurs et pilotes efficaces sollicitent moins de temps de traitement, accordant ainsi davantage de temps de traitement aux applications utilisateur, ce qui permet d'accroître le débit global.</span><span class="sxs-lookup"><span data-stu-id="97bbf-118">Efficient controllers and drivers use less privileged time, leaving more processing time available for user applications, increasing overall throughput.</span></span>  
  
-   <span data-ttu-id="97bbf-119">**Processeur : % temps utilisateur**</span><span class="sxs-lookup"><span data-stu-id="97bbf-119">**Processor: %User Time**</span></span>  
  
     <span data-ttu-id="97bbf-120">Indique en pourcentage le temps consacré par le processeur aux processus utilisateur tels que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97bbf-120">Corresponds to the percentage of time that the processor spends on executing user processes such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="97bbf-121">**Système : Longueur de la file du processeur**</span><span class="sxs-lookup"><span data-stu-id="97bbf-121">**System: Processor Queue Length**</span></span>  
  
     <span data-ttu-id="97bbf-122">Indique le nombre de threads en attente de temps processeur.</span><span class="sxs-lookup"><span data-stu-id="97bbf-122">Corresponds to the number of threads waiting for processor time.</span></span> <span data-ttu-id="97bbf-123">Un encombrement du processeur survient quand les threads d'un processus demandent plus de cycles processeur qu'il n'y en a de disponibles.</span><span class="sxs-lookup"><span data-stu-id="97bbf-123">A processor bottleneck develops when threads of a process require more processor cycles than are available.</span></span> <span data-ttu-id="97bbf-124">Si de nombreux processus essaient d'utiliser le temps du processeur, vous devez peut-être installer un processeur plus rapide.</span><span class="sxs-lookup"><span data-stu-id="97bbf-124">If more than a few processes attempt to utilize the processor's time, you might need to install a faster processor.</span></span> <span data-ttu-id="97bbf-125">Si vous avez un système multiprocesseur, vous pouvez ajouter un processeur.</span><span class="sxs-lookup"><span data-stu-id="97bbf-125">Or, if you have a multiprocessor system, you could add a processor.</span></span>  
  
 <span data-ttu-id="97bbf-126">Quand vous examinez l'utilisation du processeur, tenez compte du type de travail que l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] effectue.</span><span class="sxs-lookup"><span data-stu-id="97bbf-126">When you examine processor usage, consider the type of work that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs.</span></span> <span data-ttu-id="97bbf-127">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] effectue beaucoup de calculs (ex. requêtes impliquant des agrégats ou requêtes liées à la mémoire et qui ne nécessitent aucune E/S sur disque), il est alors possible d'utiliser 100 % du temps processeur.</span><span class="sxs-lookup"><span data-stu-id="97bbf-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs many calculations, such as queries involving aggregates or memory-bound queries that require no disk I/O, 100 percent of the processor's time can be used.</span></span> <span data-ttu-id="97bbf-128">Si cela nuit aux performances d'autres applications, essayez de modifier la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="97bbf-128">If this causes the performance of other applications to suffer, try changing the workload.</span></span> <span data-ttu-id="97bbf-129">Par exemple, dédiez l'ordinateur à l'exécution de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97bbf-129">For example, dedicate the computer to running the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="97bbf-130">Des taux d'utilisation proches de 100 %, quand de nombreuses requêtes client sont en cours de traitement, peuvent indiquer que les processus s'accumulent, en attente de temps processeur, et provoquent un goulet d'étranglement.</span><span class="sxs-lookup"><span data-stu-id="97bbf-130">Usage rates around 100 percent, where many client requests are being processed, may indicate that processes are queuing up, waiting for processor time, and causing a bottleneck.</span></span> <span data-ttu-id="97bbf-131">Vous pouvez résoudre ce problème en ajoutant des processeurs plus puissants.</span><span class="sxs-lookup"><span data-stu-id="97bbf-131">Resolve the problem by adding faster processors.</span></span>  
  
  
