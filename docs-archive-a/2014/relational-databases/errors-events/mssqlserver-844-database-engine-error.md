---
title: MSSQLSERVER_844 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 844 (Database Engine error)
ms.assetid: 2060c886-1226-4066-bc0c-de90a1cfb82b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4870d6e43ec12b49033ea3b5f88fa0d0cdd597a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604022"
---
# <a name="mssqlserver_844"></a><span data-ttu-id="decad-102">MSSQLSERVER_844</span><span class="sxs-lookup"><span data-stu-id="decad-102">MSSQLSERVER_844</span></span>
    
## <a name="details"></a><span data-ttu-id="decad-103">Détails</span><span class="sxs-lookup"><span data-stu-id="decad-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="decad-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="decad-104">Product Name</span></span>|<span data-ttu-id="decad-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="decad-105">SQL Server</span></span>|  
|<span data-ttu-id="decad-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="decad-106">Event ID</span></span>|<span data-ttu-id="decad-107">844</span><span class="sxs-lookup"><span data-stu-id="decad-107">844</span></span>|  
|<span data-ttu-id="decad-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="decad-108">Event Source</span></span>|<span data-ttu-id="decad-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="decad-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="decad-110">Composant</span><span class="sxs-lookup"><span data-stu-id="decad-110">Component</span></span>|<span data-ttu-id="decad-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="decad-111">SQLEngine</span></span>|  
|<span data-ttu-id="decad-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="decad-112">Symbolic Name</span></span>|<span data-ttu-id="decad-113">BUFLATCH_TIMEOUT_CONTINUE</span><span class="sxs-lookup"><span data-stu-id="decad-113">BUFLATCH_TIMEOUT_CONTINUE</span></span>|  
|<span data-ttu-id="decad-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="decad-114">Message Text</span></span>|<span data-ttu-id="decad-115">Un dépassement de délai s'est produit lors de l'attente du verrou de tampon -- type %d, bp %p, page %d:%d, état %#x, ID de base de données : %d, ID d'unité d'allocation : %I64d%ls, tâche 0x%p : %d, temps d'attente %d, indicateurs 0x%I64x, tâche propriétaire 0x%p.</span><span class="sxs-lookup"><span data-stu-id="decad-115">Time-out occurred while waiting for buffer latch -- type %d, bp %p, page %d:%d, stat %#x, database id: %d, allocation unit id: %I64d%ls, task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span>  <span data-ttu-id="decad-116">Poursuite de l'attente.</span><span class="sxs-lookup"><span data-stu-id="decad-116">Continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="decad-117">Explication</span><span class="sxs-lookup"><span data-stu-id="decad-117">Explanation</span></span>  
 <span data-ttu-id="decad-118">Un processus attend d'acquérir un verrou.</span><span class="sxs-lookup"><span data-stu-id="decad-118">A process is waiting to acquire a latch.</span></span> <span data-ttu-id="decad-119">Ce problème peut provenir d'une opération d'E/S qui tarde à s'achever.</span><span class="sxs-lookup"><span data-stu-id="decad-119">This problem can be caused by an I/O operation taking too long to complete.</span></span> <span data-ttu-id="decad-120">Le plus souvent, ce type d'erreur provient d'autres tâches qui bloquent les processus système.</span><span class="sxs-lookup"><span data-stu-id="decad-120">Typically this type of error is the result of other tasks blocking system processes.</span></span> <span data-ttu-id="decad-121">Dans d'autres cas, elle est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="decad-121">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="decad-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="decad-122">User Action</span></span>  
 <span data-ttu-id="decad-123">Pour prévenir cette erreur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="decad-123">Try the following to prevent this error from occurring:</span></span>  
  
-   <span data-ttu-id="decad-124">Réduisez la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="decad-124">Reduce workload.</span></span>  
  
-   <span data-ttu-id="decad-125">Recherchez les erreurs d'E/S assimilées dans le journal des erreurs ou le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="decad-125">Check for associated I/O failures in error log or event log.</span></span> <span data-ttu-id="decad-126">Les erreurs d'E/S révèlent généralement un disque défectueux.</span><span class="sxs-lookup"><span data-stu-id="decad-126">I/O failures typically point to a disk malfunction.</span></span>  
  
-   <span data-ttu-id="decad-127">Recherchez dans le journal des erreurs les tâches improductives et d’autres erreurs critiques.</span><span class="sxs-lookup"><span data-stu-id="decad-127">Check the error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="decad-128">Si des erreurs critiques telles que les assertions surviennent fréquemment, corrigez-les.</span><span class="sxs-lookup"><span data-stu-id="decad-128">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="decad-129">Si le problème persiste, contactez le service de support technique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="decad-129">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
