---
title: MSSQLSERVER_845 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 845 (Database Engine error)
ms.assetid: 8fff6ad4-234c-44be-b123-e25d5e1cd63e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 24bfb8b3758d0656dad96e4af4ed3b94aa51e07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604018"
---
# <a name="mssqlserver_845"></a><span data-ttu-id="880cc-102">MSSQLSERVER_845</span><span class="sxs-lookup"><span data-stu-id="880cc-102">MSSQLSERVER_845</span></span>
    
## <a name="details"></a><span data-ttu-id="880cc-103">Détails</span><span class="sxs-lookup"><span data-stu-id="880cc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="880cc-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="880cc-104">Product Name</span></span>|<span data-ttu-id="880cc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="880cc-105">SQL Server</span></span>|  
|<span data-ttu-id="880cc-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="880cc-106">Event ID</span></span>|<span data-ttu-id="880cc-107">845</span><span class="sxs-lookup"><span data-stu-id="880cc-107">845</span></span>|  
|<span data-ttu-id="880cc-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="880cc-108">Event Source</span></span>|<span data-ttu-id="880cc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="880cc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="880cc-110">Composant</span><span class="sxs-lookup"><span data-stu-id="880cc-110">Component</span></span>|<span data-ttu-id="880cc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="880cc-111">SQLEngine</span></span>|  
|<span data-ttu-id="880cc-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="880cc-112">Symbolic Name</span></span>|<span data-ttu-id="880cc-113">BUFLATCH_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="880cc-113">BUFLATCH_TIMEOUT</span></span>|  
|<span data-ttu-id="880cc-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="880cc-114">Message Text</span></span>|<span data-ttu-id="880cc-115">Dépassement du délai lors de l'attente du type de verrou de mémoire tampon %d, page %S_PGID, ID de base de données %d.</span><span class="sxs-lookup"><span data-stu-id="880cc-115">Time-out occurred while waiting for buffer latch type %d for page %S_PGID, database ID %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="880cc-116">Explication</span><span class="sxs-lookup"><span data-stu-id="880cc-116">Explanation</span></span>  
 <span data-ttu-id="880cc-117">Un processus était en attente d’obtention d’un verrou, mais n’a pas pu se le procurer suite à l’expiration du délai.</span><span class="sxs-lookup"><span data-stu-id="880cc-117">A process was waiting to acquire a latch, but the process waited until the time limit expired and failed to acquire one.</span></span> <span data-ttu-id="880cc-118">Cette situation peut se produire si une opération d'E/S prend trop de temps à s'accomplir, souvent à cause d'autres tâches qui bloquent les processus système.</span><span class="sxs-lookup"><span data-stu-id="880cc-118">This can occur if an I/O operation takes too long to complete, usually as a result of other tasks blocking system processes.</span></span> <span data-ttu-id="880cc-119">Dans d'autres cas, elle est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="880cc-119">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="880cc-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="880cc-120">User Action</span></span>  
 <span data-ttu-id="880cc-121">L'exécution des tâches suivantes peut éviter cette erreur :</span><span class="sxs-lookup"><span data-stu-id="880cc-121">Performing the following tasks may prevent this error:</span></span>  
  
-   <span data-ttu-id="880cc-122">Réduisez la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="880cc-122">Reduce the workload.</span></span>  
  
-   <span data-ttu-id="880cc-123">Recherchez des erreurs d'E/S associées dans le journal des erreurs ou le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="880cc-123">Verify whether there are associated I/O failures in the error log or event log.</span></span> <span data-ttu-id="880cc-124">Les erreurs d'E/S sont généralement liées à un disque défectueux.</span><span class="sxs-lookup"><span data-stu-id="880cc-124">I/O failures are typically caused by disk malfunction.</span></span>  
  
-   <span data-ttu-id="880cc-125">Recherchez dans le journal des erreurs les tâches improductives et d'autres erreurs critiques.</span><span class="sxs-lookup"><span data-stu-id="880cc-125">Check error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="880cc-126">Si des erreurs critiques telles que les assertions surviennent fréquemment, corrigez-les.</span><span class="sxs-lookup"><span data-stu-id="880cc-126">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="880cc-127">Si le problème persiste, contactez le service de support technique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="880cc-127">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
