---
title: CPU Threshold Exceeded, classe d’événements | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- CPU Threshold Exceeded Event Class
ms.assetid: eb106f7d-baa3-4a2b-96b2-f9fe0844057d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07b51e1a6f08f48c601b00d2dcb67bc6d09006f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601502"
---
# <a name="cpu-threshold-exceeded-event-class"></a><span data-ttu-id="a9f06-102">Classe d'événements CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="a9f06-102">CPU Threshold Exceeded Event Class</span></span>
  <span data-ttu-id="a9f06-103">La classe d'événements CPU Threshold Exceeded indique que Resource Governor détecte une requête qui dépasse le seuil de l'UC spécifié pour REQUEST_MAX_CPU_TIME_SEC.</span><span class="sxs-lookup"><span data-stu-id="a9f06-103">The CPU Threshold Exceeded event class indicates that Resource Governor detects a query that exceeds the CPU threshold specified for REQUEST_MAX_CPU_TIME_SEC.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9f06-104">L'intervalle de détection pour cet événement est cinq secondes.</span><span class="sxs-lookup"><span data-stu-id="a9f06-104">The detection interval for this event is five seconds.</span></span> <span data-ttu-id="a9f06-105">Il est garanti qu'un événement sera généré si une requête dépasse la limite spécifiée d'au moins cinq secondes.</span><span class="sxs-lookup"><span data-stu-id="a9f06-105">It is guaranteed that an event will be generated if a query exceeds the specified limit by at least five seconds.</span></span> <span data-ttu-id="a9f06-106">Toutefois, si une requête dépasse le seuil spécifié de moins de cinq secondes, sa détection peut être manquée selon le moment d'exécution de la requête et l'heure de la dernière analyse de détection.</span><span class="sxs-lookup"><span data-stu-id="a9f06-106">However, if a query exceeds the specified threshold by less than five seconds, its detection might be missed depending on the timing of the query and the time of last detection sweep.</span></span>  
  
## <a name="cpu-threshold-exceeded-data-columns"></a><span data-ttu-id="a9f06-107">Colonnes de données CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="a9f06-107">CPU Threshold Exceeded Data Columns</span></span>  
  
|<span data-ttu-id="a9f06-108">Nom de la colonne de données</span><span class="sxs-lookup"><span data-stu-id="a9f06-108">Data column name</span></span>|<span data-ttu-id="a9f06-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="a9f06-109">Data type</span></span>|<span data-ttu-id="a9f06-110">Description</span><span class="sxs-lookup"><span data-stu-id="a9f06-110">Description</span></span>|<span data-ttu-id="a9f06-111">ID de la colonne</span><span class="sxs-lookup"><span data-stu-id="a9f06-111">Column ID</span></span>|<span data-ttu-id="a9f06-112">Filtrable</span><span class="sxs-lookup"><span data-stu-id="a9f06-112">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="a9f06-113">UC</span><span class="sxs-lookup"><span data-stu-id="a9f06-113">CPU</span></span>|`int`|<span data-ttu-id="a9f06-114">Utilisation de l'UC en millisecondes.</span><span class="sxs-lookup"><span data-stu-id="a9f06-114">CPU usage in milliseconds.</span></span>|<span data-ttu-id="a9f06-115">18</span><span class="sxs-lookup"><span data-stu-id="a9f06-115">18</span></span>|<span data-ttu-id="a9f06-116">Oui</span><span class="sxs-lookup"><span data-stu-id="a9f06-116">Yes</span></span>|  
|<span data-ttu-id="a9f06-117">EventClass</span><span class="sxs-lookup"><span data-stu-id="a9f06-117">EventClass</span></span>|`int`|<span data-ttu-id="a9f06-118">214</span><span class="sxs-lookup"><span data-stu-id="a9f06-118">214</span></span>|<span data-ttu-id="a9f06-119">27</span><span class="sxs-lookup"><span data-stu-id="a9f06-119">27</span></span>|<span data-ttu-id="a9f06-120">Non</span><span class="sxs-lookup"><span data-stu-id="a9f06-120">No</span></span>|  
|<span data-ttu-id="a9f06-121">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="a9f06-121">EventSubClass</span></span>|`int`|<span data-ttu-id="a9f06-122">Violation de la limite de l'UC.</span><span class="sxs-lookup"><span data-stu-id="a9f06-122">CPU limit violation.</span></span>|<span data-ttu-id="a9f06-123">21</span><span class="sxs-lookup"><span data-stu-id="a9f06-123">21</span></span>|<span data-ttu-id="a9f06-124">Oui</span><span class="sxs-lookup"><span data-stu-id="a9f06-124">Yes</span></span>|  
|<span data-ttu-id="a9f06-125">GroupID</span><span class="sxs-lookup"><span data-stu-id="a9f06-125">GroupID</span></span>|`int`|<span data-ttu-id="a9f06-126">ID de groupe où la violation s'est produite.</span><span class="sxs-lookup"><span data-stu-id="a9f06-126">Group ID where the violation occurred.</span></span>|<span data-ttu-id="a9f06-127">66</span><span class="sxs-lookup"><span data-stu-id="a9f06-127">66</span></span>|<span data-ttu-id="a9f06-128">Oui</span><span class="sxs-lookup"><span data-stu-id="a9f06-128">Yes</span></span>|  
|<span data-ttu-id="a9f06-129">OwnerID</span><span class="sxs-lookup"><span data-stu-id="a9f06-129">OwnerID</span></span>|`int`|<span data-ttu-id="a9f06-130">SPID du processus qui a provoqué la violation.</span><span class="sxs-lookup"><span data-stu-id="a9f06-130">SPID of the process that caused the violation.</span></span>|<span data-ttu-id="a9f06-131">58</span><span class="sxs-lookup"><span data-stu-id="a9f06-131">58</span></span>|<span data-ttu-id="a9f06-132">Oui</span><span class="sxs-lookup"><span data-stu-id="a9f06-132">Yes</span></span>|  
|<span data-ttu-id="a9f06-133">SPID</span><span class="sxs-lookup"><span data-stu-id="a9f06-133">SPID</span></span>|`int`|<span data-ttu-id="a9f06-134">ID du processus serveur qui déclenche cet événement.</span><span class="sxs-lookup"><span data-stu-id="a9f06-134">ID of the server process that fires this event.</span></span><br /><br /> <span data-ttu-id="a9f06-135">Remarque : il peut être différent du SPID de l’utilisateur réel si un thread système valide l’utilisation de l’UC comme une tâche en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="a9f06-135">Note: This can differ from the actual user SPID if a system thread validates CPU usage as a background task.</span></span>|<span data-ttu-id="a9f06-136">12</span><span class="sxs-lookup"><span data-stu-id="a9f06-136">12</span></span>|<span data-ttu-id="a9f06-137">Oui</span><span class="sxs-lookup"><span data-stu-id="a9f06-137">Yes</span></span>|  
|<span data-ttu-id="a9f06-138">StartTime</span><span class="sxs-lookup"><span data-stu-id="a9f06-138">StartTime</span></span>|`datetime`|<span data-ttu-id="a9f06-139">Heure de déclenchement de cet événement.</span><span class="sxs-lookup"><span data-stu-id="a9f06-139">The time when this event fired.</span></span>|<span data-ttu-id="a9f06-140">14</span><span class="sxs-lookup"><span data-stu-id="a9f06-140">14</span></span>|<span data-ttu-id="a9f06-141">Oui</span><span class="sxs-lookup"><span data-stu-id="a9f06-141">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9f06-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a9f06-142">See Also</span></span>  
 [<span data-ttu-id="a9f06-143">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a9f06-143">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
