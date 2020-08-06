---
title: MSSQLSERVER_17884 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17884 (Database Engine error)
ms.assetid: 8d05ba05-3f71-4dc3-bd81-2ea5ac9fe843
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd5beca2a7dfd20afbf9eff196d89452ef3533d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702943"
---
# <a name="mssqlserver_17884"></a><span data-ttu-id="28b67-102">MSSQLSERVER_17884</span><span class="sxs-lookup"><span data-stu-id="28b67-102">MSSQLSERVER_17884</span></span>
    
## <a name="details"></a><span data-ttu-id="28b67-103">Détails</span><span class="sxs-lookup"><span data-stu-id="28b67-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28b67-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="28b67-104">Product Name</span></span>|<span data-ttu-id="28b67-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="28b67-105">SQL Server</span></span>|  
|<span data-ttu-id="28b67-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="28b67-106">Event ID</span></span>|<span data-ttu-id="28b67-107">17884</span><span class="sxs-lookup"><span data-stu-id="28b67-107">17884</span></span>|  
|<span data-ttu-id="28b67-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="28b67-108">Event Source</span></span>|<span data-ttu-id="28b67-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="28b67-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="28b67-110">Composant</span><span class="sxs-lookup"><span data-stu-id="28b67-110">Component</span></span>|<span data-ttu-id="28b67-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="28b67-111">SQLEngine</span></span>|  
|<span data-ttu-id="28b67-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="28b67-112">Symbolic Name</span></span>|<span data-ttu-id="28b67-113">SRV_SCHEDULER_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="28b67-113">SRV_SCHEDULER_DEADLOCK</span></span>|  
|<span data-ttu-id="28b67-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="28b67-114">Message Text</span></span>|<span data-ttu-id="28b67-115">Les nouvelles requêtes à traiter sur le nœud %d n'ont pas été sélectionnées par un thread de travail au cours des %d dernières secondes.</span><span class="sxs-lookup"><span data-stu-id="28b67-115">New queries assigned to process on Node %d have not been picked  up by a worker thread in the last %d seconds.</span></span> <span data-ttu-id="28b67-116">Les requêtes qui provoquent des blocages ou dont l'exécution est longue peuvent causer cette situation ainsi qu'une dégradation du temps de réponse du client.</span><span class="sxs-lookup"><span data-stu-id="28b67-116">Blocking or long-running queries can contribute to this condition, and may degrade client response time.</span></span> <span data-ttu-id="28b67-117">Utilisez l'option de configuration "max worker threads" pour augmenter le nombre de threads autorisés, ou optimisez les requêtes en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="28b67-117">Use the "max worker threads" configuration option to increase number  of allowable threads, or optimize current running queries.</span></span>  <span data-ttu-id="28b67-118">Utilisation du processus SQL : %d%%.</span><span class="sxs-lookup"><span data-stu-id="28b67-118">SQL Process Utilization: %d%%.</span></span> <span data-ttu-id="28b67-119">Système inactif : %d%%.</span><span class="sxs-lookup"><span data-stu-id="28b67-119">System Idle: %d%%.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28b67-120">Explication</span><span class="sxs-lookup"><span data-stu-id="28b67-120">Explanation</span></span>  
 <span data-ttu-id="28b67-121">Il n'y a aucun signe de progression dans chacun des planificateurs, ce qui pourrait être causé par des blocages où aucun thread ne peut avancer et/ou aucun nouveau travail ne peut être sélectionné et traité.</span><span class="sxs-lookup"><span data-stu-id="28b67-121">There is no sign of progress in each of the schedulers and could be caused by deadlocks where none of the threads can advance and/or no new work can be picked up and processed.</span></span> <span data-ttu-id="28b67-122">Si l'utilisation du processus est faible, d'autres processus sur l'ordinateur entraînent peut-être une insuffisance du processus de serveur au niveau du microprocesseur.</span><span class="sxs-lookup"><span data-stu-id="28b67-122">If process utilization is low then other processes on the machine may be causing the server process CPU starvation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28b67-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="28b67-123">User Action</span></span>  
 <span data-ttu-id="28b67-124">Déterminez la cause du blocage et l'absence de progression, et résolvez la situation en conséquence.</span><span class="sxs-lookup"><span data-stu-id="28b67-124">Determine why there is blocking and no progress being made and resolve situation accordingly.</span></span> <span data-ttu-id="28b67-125">Si l'utilisation du processus est faible, vérifiez la charge sur le système générée par d'autres processus.</span><span class="sxs-lookup"><span data-stu-id="28b67-125">If process utilization is low check the load on the system caused by other processes.</span></span>  
  
  
