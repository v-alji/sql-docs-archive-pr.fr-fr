---
title: Transactions, catégorie d’événement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Transactions event category
- event classes [SQL Server], Transactions event category
- Transactions event category [SQL Server]
ms.assetid: bfc75c5b-7115-49d8-9148-a0c84ee66a9a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b68a91fb166797c220cb0c4f5cf2607ca267538
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612365"
---
# <a name="transactions-event-category"></a><span data-ttu-id="cfea1-102">Catégorie d'événements Transactions</span><span class="sxs-lookup"><span data-stu-id="cfea1-102">Transactions Event Category</span></span>
  <span data-ttu-id="cfea1-103">Les classes d’événements **Transactions** permettent de surveiller l’état des transactions.</span><span class="sxs-lookup"><span data-stu-id="cfea1-103">The **Transactions** event classes can be used to monitor the status of transactions.</span></span> <span data-ttu-id="cfea1-104">Les noms de classes d’événements portant le préfixe **TM:** sont utilisées pour assurer le suivi des opérations liées aux transactions qui sont envoyées à travers l’interface de gestion des transactions.</span><span class="sxs-lookup"><span data-stu-id="cfea1-104">The event class names that are prefixed with **TM:** are used to track the transaction-related operations that are sent through the transaction management interface.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfea1-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="cfea1-105">In This Section</span></span>  
  
|<span data-ttu-id="cfea1-106">Rubrique</span><span class="sxs-lookup"><span data-stu-id="cfea1-106">Topic</span></span>|<span data-ttu-id="cfea1-107">Description</span><span class="sxs-lookup"><span data-stu-id="cfea1-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cfea1-108">DTCTransaction, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="cfea1-108">DTCTransaction Event Class</span></span>](dtctransaction-event-class.md)|<span data-ttu-id="cfea1-109">Assure le suivi des transactions coordonnées par [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="cfea1-109">Tracks transactions coordinated by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="cfea1-110">Ce sont les transactions distribuées entre plusieurs bases de données ou instances du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfea1-110">These are transactions distributed between two or more databases or instances of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>|  
|[<span data-ttu-id="cfea1-111">Classe d'événements SQLTransaction</span><span class="sxs-lookup"><span data-stu-id="cfea1-111">SQLTransaction Event Class</span></span>](sqltransaction-event-class.md)|<span data-ttu-id="cfea1-112">Surveille les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN et ROLLBACK TRAN.</span><span class="sxs-lookup"><span data-stu-id="cfea1-112">Tracks [!INCLUDE[tsql](../../includes/tsql-md.md)] BEGIN TRAN, COMMIT TRAN, SAVE TRAN, and ROLLBACK TRAN statements.</span></span>|  
|[<span data-ttu-id="cfea1-113">Classe d'événements TM: Begin Tran Completed</span><span class="sxs-lookup"><span data-stu-id="cfea1-113">TM: Begin Tran Completed Event Class</span></span>](tm-begin-tran-completed-event-class.md)|<span data-ttu-id="cfea1-114">Indique qu'une demande BEGIN TRANSACTION est terminée.</span><span class="sxs-lookup"><span data-stu-id="cfea1-114">Indicates that a BEGIN TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="cfea1-115">Classe d'événements TM: Begin Tran Starting</span><span class="sxs-lookup"><span data-stu-id="cfea1-115">TM: Begin Tran Starting Event Class</span></span>](tm-begin-tran-starting-event-class.md)|<span data-ttu-id="cfea1-116">Indique qu'une demande BEGIN TRANSACTION démarre.</span><span class="sxs-lookup"><span data-stu-id="cfea1-116">Indicates that a BEGIN TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="cfea1-117">Classe d'événements TM: Commit Tran Completed</span><span class="sxs-lookup"><span data-stu-id="cfea1-117">TM: Commit Tran Completed Event Class</span></span>](tm-commit-tran-completed-event-class.md)|<span data-ttu-id="cfea1-118">Indique qu'une demande COMMIT TRANSACTION est terminée.</span><span class="sxs-lookup"><span data-stu-id="cfea1-118">Indicates that a COMMIT TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="cfea1-119">Classe d'événements TM: Commit Tran Starting</span><span class="sxs-lookup"><span data-stu-id="cfea1-119">TM: Commit Tran Starting Event Class</span></span>](tm-commit-tran-starting-event-class.md)|<span data-ttu-id="cfea1-120">Indique qu'une demande COMMIT TRANSACTION démarre.</span><span class="sxs-lookup"><span data-stu-id="cfea1-120">Indicates that a COMMIT TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="cfea1-121">Classe d'événements TM: Promote Tran Completed</span><span class="sxs-lookup"><span data-stu-id="cfea1-121">TM: Promote Tran Completed Event Class</span></span>](tm-promote-tran-completed-event-class.md)|<span data-ttu-id="cfea1-122">Indique qu'une demande PROMOTE TRANSACTION est terminée.</span><span class="sxs-lookup"><span data-stu-id="cfea1-122">Indicates that a PROMOTE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="cfea1-123">Classe d'événements TM: Promote Tran Starting</span><span class="sxs-lookup"><span data-stu-id="cfea1-123">TM: Promote Tran Starting Event Class</span></span>](tm-promote-tran-starting-event-class.md)|<span data-ttu-id="cfea1-124">Indique qu'une demande PROMOTE TRANSACTION démarre.</span><span class="sxs-lookup"><span data-stu-id="cfea1-124">Indicates that a PROMOTE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="cfea1-125">Classe d'événements TM: Rollback Tran Completed</span><span class="sxs-lookup"><span data-stu-id="cfea1-125">TM: Rollback Tran Completed Event Class</span></span>](tm-rollback-tran-completed-event-class.md)|<span data-ttu-id="cfea1-126">Indique qu'une demande ROLLBACK TRANSACTION est terminée.</span><span class="sxs-lookup"><span data-stu-id="cfea1-126">Indicates that a ROLLBACK TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="cfea1-127">Classe d'événements TM: Rollback Tran Starting</span><span class="sxs-lookup"><span data-stu-id="cfea1-127">TM: Rollback Tran Starting Event Class</span></span>](tm-rollback-tran-starting-event-class.md)|<span data-ttu-id="cfea1-128">Indique qu'une demande ROLLBACK TRANSACTION démarre.</span><span class="sxs-lookup"><span data-stu-id="cfea1-128">Indicates that a ROLLBACK TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="cfea1-129">Classe d'événements TM: Save Tran Completed</span><span class="sxs-lookup"><span data-stu-id="cfea1-129">TM: Save Tran Completed Event Class</span></span>](tm-save-tran-completed-event-class.md)|<span data-ttu-id="cfea1-130">Indique qu'une demande SAVE TRANSACTION est terminée.</span><span class="sxs-lookup"><span data-stu-id="cfea1-130">Indicates that a SAVE TRANSACTION request has completed.</span></span>|  
|[<span data-ttu-id="cfea1-131">Classe d'événements TM: Save Tran Starting</span><span class="sxs-lookup"><span data-stu-id="cfea1-131">TM: Save Tran Starting Event Class</span></span>](tm-save-tran-starting-event-class.md)|<span data-ttu-id="cfea1-132">Indique qu'une demande SAVE TRANSACTION démarre.</span><span class="sxs-lookup"><span data-stu-id="cfea1-132">Indicates that a SAVE TRANSACTION request is starting.</span></span>|  
|[<span data-ttu-id="cfea1-133">TransactionLog, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="cfea1-133">TransactionLog Event Class</span></span>](transactionlog-event-class.md)|<span data-ttu-id="cfea1-134">Assure le suivi du moment où les transactions sont écrites dans un journal des transactions de la base de données.</span><span class="sxs-lookup"><span data-stu-id="cfea1-134">Tracks when transactions are written to a database transaction log.</span></span>|  
  
  
