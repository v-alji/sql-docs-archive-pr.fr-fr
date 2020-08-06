---
title: Catégorie d’événements Erreurs et avertissements (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Errors and Warnings event category [SQL Server]
- SQL Server event classes, Errors and Warnings event category
- event classes [SQL Server], Errors and Warnings event category
ms.assetid: 249c19b5-af68-4433-80f6-337395176641
author: stevestein
ms.author: sstein
ms.openlocfilehash: d55f37f5401f60ddfeec340af1ae6d532eb6ad01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704064"
---
# <a name="errors-and-warnings-event-category-database-engine"></a><span data-ttu-id="e83e2-102">Catégorie d'événements Erreurs et avertissements (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="e83e2-102">Errors and Warnings Event Category (Database Engine)</span></span>
  <span data-ttu-id="e83e2-103">La catégorie d’événements **Erreurs et avertissements** contient des événements généraux d’erreurs et d’avertissements.</span><span class="sxs-lookup"><span data-stu-id="e83e2-103">The **Errors and Warnings** event category contains general error and warning events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e83e2-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e83e2-104">In This Section</span></span>  
  
|<span data-ttu-id="e83e2-105">Rubrique</span><span class="sxs-lookup"><span data-stu-id="e83e2-105">Topic</span></span>|<span data-ttu-id="e83e2-106">Description</span><span class="sxs-lookup"><span data-stu-id="e83e2-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e83e2-107">Attention, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="e83e2-107">Attention Event Class</span></span>](attention-event-class.md)|<span data-ttu-id="e83e2-108">Indique qu’un événement **Attention** s’est produit.</span><span class="sxs-lookup"><span data-stu-id="e83e2-108">Indicates that an **Attention** event has occurred.</span></span>|  
|[<span data-ttu-id="e83e2-109">Background Job Error, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="e83e2-109">Background Job Error Event Class</span></span>](background-job-error-event-class.md)|<span data-ttu-id="e83e2-110">Indique qu'un travail en arrière-plan s'est terminé anormalement.</span><span class="sxs-lookup"><span data-stu-id="e83e2-110">Indicates that a background job has terminated abnormally.</span></span>|  
|[<span data-ttu-id="e83e2-111">Bitmap Warning, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="e83e2-111">Bitmap Warning Event Class</span></span>](bitmap-warning-event-class.md)|<span data-ttu-id="e83e2-112">Indique que le filtrage Bitmap a été désactivé dans une requête.</span><span class="sxs-lookup"><span data-stu-id="e83e2-112">Indicates that bitmap filtering has been disabled in a query.</span></span>|  
|[<span data-ttu-id="e83e2-113">Blocked Process Report, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="e83e2-113">Blocked Process Report Event Class</span></span>](blocked-process-report-event-class.md)|<span data-ttu-id="e83e2-114">Indique qu'une tâche a été bloquée plus longtemps qu'une période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e83e2-114">Indicates that a task has been blocked for more than a specified amount of time.</span></span>|  
|[<span data-ttu-id="e83e2-115">CPU Threshold Exceeded, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="e83e2-115">CPU Threshold Exceeded Event Class</span></span>](cpu-threshold-exceeded-event-class.md)|<span data-ttu-id="e83e2-116">Indique que Resource Governor détecte une requête qui dépasse le seuil de l'UC spécifié.</span><span class="sxs-lookup"><span data-stu-id="e83e2-116">Indicates that the Resource Governor detects a query that exceeds the specified CPU threshold.</span></span>|  
|[<span data-ttu-id="e83e2-117">ErrorLog, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="e83e2-117">ErrorLog Event Class</span></span>](errorlog-event-class.md)|<span data-ttu-id="e83e2-118">Indique que les événements d'erreurs ont été enregistrés dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e83e2-118">Indicates that error events have been logged in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>|  
|[<span data-ttu-id="e83e2-119">Classe d'événements EventLog</span><span class="sxs-lookup"><span data-stu-id="e83e2-119">EventLog Event Class</span></span>](eventlog-event-class.md)|<span data-ttu-id="e83e2-120">Indique que les événements ont été consignés dans le journal des événements de Windows.</span><span class="sxs-lookup"><span data-stu-id="e83e2-120">Indicates that events have been logged in the Windows event log.</span></span>|  
|[<span data-ttu-id="e83e2-121">Classe d'événements Exception</span><span class="sxs-lookup"><span data-stu-id="e83e2-121">Exception Event Class</span></span>](exception-event-class.md)|<span data-ttu-id="e83e2-122">Indique qu'une exception s'est produite dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e83e2-122">Indicates that an exception has occurred in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="e83e2-123">Classe d'événements Exchange Spill</span><span class="sxs-lookup"><span data-stu-id="e83e2-123">Exchange Spill Event Class</span></span>](exchange-spill-event-class.md)|<span data-ttu-id="e83e2-124">Indique que des tampons de communication dans un plan de requête parallèle ont été écrits dans la base de données tempdb.</span><span class="sxs-lookup"><span data-stu-id="e83e2-124">Indicates that communication buffers in a parallel query plan have been written to the tempdb database.</span></span>|  
|[<span data-ttu-id="e83e2-125">Classe d'événements Execution Warnings</span><span class="sxs-lookup"><span data-stu-id="e83e2-125">Execution Warnings Event Class</span></span>](execution-warnings-event-class.md)|<span data-ttu-id="e83e2-126">Indique que des avertissements d'allocation de mémoire se sont produits lors de l'exécution d'une instruction ou d'une procédure stockée [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e83e2-126">Indicates that memory grant warnings occurred during the execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statement or stored procedure.</span></span>|  
|[<span data-ttu-id="e83e2-127">Classe d'événements Hash Warning</span><span class="sxs-lookup"><span data-stu-id="e83e2-127">Hash Warning Event Class</span></span>](hash-warning-event-class.md)|<span data-ttu-id="e83e2-128">Indique qu'une récurrence ou une interruption de hachage s'est produite pendant une opération de hachage.</span><span class="sxs-lookup"><span data-stu-id="e83e2-128">Indicates that a hash recursion or hash bailout has occurred during a hashing operation.</span></span>|  
|[<span data-ttu-id="e83e2-129">Classe d'événements Missing Column Statistics</span><span class="sxs-lookup"><span data-stu-id="e83e2-129">Missing Column Statistics Event Class</span></span>](missing-column-statistics-event-class.md)|<span data-ttu-id="e83e2-130">Indique que des statistiques de colonne qui auraient pu être utiles pour l'optimiseur ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="e83e2-130">Indicates that column statistics that could have been useful for the optimizer are not available.</span></span>|  
|[<span data-ttu-id="e83e2-131">Classe d'événements Missing Join Predicate</span><span class="sxs-lookup"><span data-stu-id="e83e2-131">Missing Join Predicate Event Class</span></span>](missing-join-predicate-event-class.md)|<span data-ttu-id="e83e2-132">Indique qu'une requête en cours d'exécution est sans prédicat de jointure.</span><span class="sxs-lookup"><span data-stu-id="e83e2-132">Indicates that a query is being executed that has no join predicate.</span></span>|  
|[<span data-ttu-id="e83e2-133">Classe d'événements Sort Warnings</span><span class="sxs-lookup"><span data-stu-id="e83e2-133">Sort Warnings Event Class</span></span>](sort-warnings-event-class.md)|<span data-ttu-id="e83e2-134">Indique que des opérations de tri ne peuvent pas être effectuées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="e83e2-134">Indicates that sort operations do not fit into memory.</span></span>|  
|[<span data-ttu-id="e83e2-135">User Error Message, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="e83e2-135">User Error Message Event Class</span></span>](user-error-message-event-class.md)|<span data-ttu-id="e83e2-136">Affiche des messages d'erreur vus par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e83e2-136">Displays error messages that are seen by the user.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e83e2-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e83e2-137">See Also</span></span>  
 [<span data-ttu-id="e83e2-138">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e83e2-138">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
