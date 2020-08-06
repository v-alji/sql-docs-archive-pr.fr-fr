---
title: SQL Server Agent, objet JobSteps | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- JobSteps object
- SQLAgent:JobSteps
ms.assetid: 44f9983c-1753-4fe0-8475-973aa2460b3a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3759303807714e2bb7f71f59e644bc485d36cfcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602790"
---
# <a name="sql-server-agent-jobsteps-object"></a><span data-ttu-id="c30c6-102">SQL Server Agent, objet JobSteps</span><span class="sxs-lookup"><span data-stu-id="c30c6-102">SQL Server Agent, JobSteps Object</span></span>
  <span data-ttu-id="c30c6-103">L'objet de performance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] JobSteps **de l'Agent** intègre des compteurs de performances chargés de fournir des informations sur les étapes de travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c30c6-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **JobSteps** performance object contains performance counters that report information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="c30c6-104">Le tableau ci-dessous répertorie les compteurs inclus dans cet objet.</span><span class="sxs-lookup"><span data-stu-id="c30c6-104">The table below lists the counters that this object contains.</span></span>  
  
 <span data-ttu-id="c30c6-105">Le tableau suivant énumère les compteurs **SQLAgent:JobSteps** .</span><span class="sxs-lookup"><span data-stu-id="c30c6-105">The table below contains the **SQLAgent:JobSteps** counters.</span></span>  
  
|<span data-ttu-id="c30c6-106">Nom</span><span class="sxs-lookup"><span data-stu-id="c30c6-106">Name</span></span>|<span data-ttu-id="c30c6-107">Description</span><span class="sxs-lookup"><span data-stu-id="c30c6-107">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="c30c6-108">**Étapes actives**</span><span class="sxs-lookup"><span data-stu-id="c30c6-108">**Active steps**</span></span>|<span data-ttu-id="c30c6-109">Ce compteur fait état du nombre d'étapes de travail en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c30c6-109">This counter reports the number of job steps currently running.</span></span>|  
|<span data-ttu-id="c30c6-110">**Étapes en attente**</span><span class="sxs-lookup"><span data-stu-id="c30c6-110">**Queued steps**</span></span>|<span data-ttu-id="c30c6-111">Ce compteur fait état du nombre d'étapes de travail en mesure d'être exécutées par l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mais dont l'exécution n'a pas encore commencé.</span><span class="sxs-lookup"><span data-stu-id="c30c6-111">This counter reports the number of job steps that are ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run, but which have not yet started running.</span></span>|  
|<span data-ttu-id="c30c6-112">**Total des tentatives d'exécution d'une étape**</span><span class="sxs-lookup"><span data-stu-id="c30c6-112">**Total step retries**</span></span>|<span data-ttu-id="c30c6-113">Ce compteur indique le nombre de fois que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a retenté une étape de travail depuis le dernier redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="c30c6-113">This counter reports the total number of times that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has retried a job step since the last server restart.</span></span>|  
  
 <span data-ttu-id="c30c6-114">Chaque compteur de l'objet contient les instances suivantes :</span><span class="sxs-lookup"><span data-stu-id="c30c6-114">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="c30c6-115">Instance</span><span class="sxs-lookup"><span data-stu-id="c30c6-115">Instance</span></span>|<span data-ttu-id="c30c6-116">Description</span><span class="sxs-lookup"><span data-stu-id="c30c6-116">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c30c6-117">**_Total**</span><span class="sxs-lookup"><span data-stu-id="c30c6-117">**_Total**</span></span>|<span data-ttu-id="c30c6-118">Informations relatives à toutes les étapes de travail</span><span class="sxs-lookup"><span data-stu-id="c30c6-118">Information for all job steps.</span></span>|  
|<span data-ttu-id="c30c6-119">**ActiveScripting**</span><span class="sxs-lookup"><span data-stu-id="c30c6-119">**ActiveScripting**</span></span>|<span data-ttu-id="c30c6-120">Informations relatives aux étapes de travail qui utilisent le sous-système **ActiveScripting**</span><span class="sxs-lookup"><span data-stu-id="c30c6-120">Information for job steps that use the **ActiveScripting** subsystem.</span></span>|  
|<span data-ttu-id="c30c6-121">**ANALYSISCOMMAND**</span><span class="sxs-lookup"><span data-stu-id="c30c6-121">**ANALYSISCOMMAND**</span></span>|<span data-ttu-id="c30c6-122">Informations relatives aux étapes de travail qui utilisent le sous-système ANALYSISCOMMAND</span><span class="sxs-lookup"><span data-stu-id="c30c6-122">Information for job steps that use the ANALYSISCOMMAND subsystem.</span></span>|  
|<span data-ttu-id="c30c6-123">**ANALYSISQUERY**</span><span class="sxs-lookup"><span data-stu-id="c30c6-123">**ANALYSISQUERY**</span></span>|<span data-ttu-id="c30c6-124">Informations relatives aux étapes de travail qui utilisent le sous-système ANALYSISQUERY</span><span class="sxs-lookup"><span data-stu-id="c30c6-124">Information for job steps that use the ANALYSISQUERY subsystem.</span></span>|  
|<span data-ttu-id="c30c6-125">**CmdExec**</span><span class="sxs-lookup"><span data-stu-id="c30c6-125">**CmdExec**</span></span>|<span data-ttu-id="c30c6-126">Informations relatives aux étapes de travail qui utilisent le sous-système **CmdExec**</span><span class="sxs-lookup"><span data-stu-id="c30c6-126">Information for job steps that use the **CmdExec** subsystem.</span></span>|  
|<span data-ttu-id="c30c6-127">**Distribution**</span><span class="sxs-lookup"><span data-stu-id="c30c6-127">**Distribution**</span></span>|<span data-ttu-id="c30c6-128">Informations relatives aux étapes de travail qui utilisent le sous-système **Distribution**</span><span class="sxs-lookup"><span data-stu-id="c30c6-128">Information for job steps that use the **Distribution** subsystem.</span></span>|  
|<span data-ttu-id="c30c6-129">**Dts**</span><span class="sxs-lookup"><span data-stu-id="c30c6-129">**Dts**</span></span>|<span data-ttu-id="c30c6-130">Informations relatives aux étapes de travail qui utilisent le sous-système [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c30c6-130">Information for job steps that use the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] subsystem.</span></span>|  
|<span data-ttu-id="c30c6-131">**LogReader**</span><span class="sxs-lookup"><span data-stu-id="c30c6-131">**LogReader**</span></span>|<span data-ttu-id="c30c6-132">Informations relatives aux étapes de travail qui utilisent le sous-système **LogReader**</span><span class="sxs-lookup"><span data-stu-id="c30c6-132">Information for job steps that use the **LogReader** subsystem.</span></span>|  
|<span data-ttu-id="c30c6-133">**Fusionner**</span><span class="sxs-lookup"><span data-stu-id="c30c6-133">**Merge**</span></span>|<span data-ttu-id="c30c6-134">Informations relatives aux étapes de travail qui utilisent le sous-système **Merge**</span><span class="sxs-lookup"><span data-stu-id="c30c6-134">Information for job steps that use the **Merge** subsystem.</span></span>|  
|<span data-ttu-id="c30c6-135">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c30c6-135">**PowerShell**</span></span>|<span data-ttu-id="c30c6-136">Informations relatives aux étapes de travail qui utilisent le sous-système **PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c30c6-136">Information for job steps that use the **PowerShell** subsystem.</span></span>|  
|<span data-ttu-id="c30c6-137">**QueueReader**</span><span class="sxs-lookup"><span data-stu-id="c30c6-137">**QueueReader**</span></span>|<span data-ttu-id="c30c6-138">Informations relatives aux étapes de travail qui utilisent le sous-système **QueueReader**</span><span class="sxs-lookup"><span data-stu-id="c30c6-138">Information for job steps that use the **QueueReader** subsystem.</span></span>|  
|<span data-ttu-id="c30c6-139">**Instantané**</span><span class="sxs-lookup"><span data-stu-id="c30c6-139">**Snapshot**</span></span>|<span data-ttu-id="c30c6-140">Informations relatives aux étapes de travail qui utilisent le sous-système **Snapshot**</span><span class="sxs-lookup"><span data-stu-id="c30c6-140">Information for job steps that use the **Snapshot** subsystem.</span></span>|  
|<span data-ttu-id="c30c6-141">**TSQL**</span><span class="sxs-lookup"><span data-stu-id="c30c6-141">**TSQL**</span></span>|<span data-ttu-id="c30c6-142">Informations relatives aux étapes de travail qui exécutent [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c30c6-142">Information for job steps that execute [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c30c6-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c30c6-143">See Also</span></span>  
 <span data-ttu-id="c30c6-144">[Gérer les étapes de travail](../../ssms/agent/manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="c30c6-144">[Manage Job Steps](../../ssms/agent/manage-job-steps.md) </span></span>  
 <span data-ttu-id="c30c6-145">[Utiliser des objets de performance](../../ssms/agent/use-performance-objects.md) </span><span class="sxs-lookup"><span data-stu-id="c30c6-145">[Use Performance Objects](../../ssms/agent/use-performance-objects.md) </span></span>  
 [<span data-ttu-id="c30c6-146">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="c30c6-146">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
