---
title: Performance, catégorie d’événement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Performance event category
- Performance event category [SQL Server]
- event classes [SQL Server], Performance event category
ms.assetid: 708f3585-d8be-4980-bbff-672d7c59397e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b0c076a4132298797313ecbf0874d9d2d4e453cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611768"
---
# <a name="performance-event-category"></a><span data-ttu-id="f0fa6-102">Catégorie d'événements Performance</span><span class="sxs-lookup"><span data-stu-id="f0fa6-102">Performance Event Category</span></span>
  <span data-ttu-id="f0fa6-103">Utilisez les classes d’événements **Performance** pour surveiller les classes d’événements **Showplan** et celles produites par l’exécution des opérateurs du langage de manipulation des données SQL (DML, Data Manipulation Language).</span><span class="sxs-lookup"><span data-stu-id="f0fa6-103">Use the **Performance** event category to monitor **Showplan** event classes and event classes that are produced from the execution of SQL data manipulation language (DML) operators.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f0fa6-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f0fa6-104">In This Section</span></span>  
  
|<span data-ttu-id="f0fa6-105">Rubrique</span><span class="sxs-lookup"><span data-stu-id="f0fa6-105">Topic</span></span>|<span data-ttu-id="f0fa6-106">Description</span><span class="sxs-lookup"><span data-stu-id="f0fa6-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f0fa6-107">Auto Stats, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="f0fa6-107">Auto Stats Event Class</span></span>](auto-stats-event-class.md)|<span data-ttu-id="f0fa6-108">Indique qu'une mise à jour automatique des statistiques d'index et de colonne a eu lieu.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-108">Indicates that an automatic updating of index and column statistics has occurred.</span></span>|  
|[<span data-ttu-id="f0fa6-109">Classe d’événements Degree of Parallelism &#40;7.0 Insert&#41;</span><span class="sxs-lookup"><span data-stu-id="f0fa6-109">Degree of Parallelism &#40;7.0 Insert&#41; Event Class</span></span>](degree-of-parallelism-7-0-insert-event-class.md)|<span data-ttu-id="f0fa6-110">Indique que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a exécuté une instruction SELECT, INSERT, UPDATE ou DELETE en utilisant un plan série ou parallèle.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-110">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a SELECT, INSERT, UPDATE, or DELETE statement using either a serial or parallel plan.</span></span> <span data-ttu-id="f0fa6-111">Le nombre d'unités centrales utilisées pour effectuer l'opération est également indiqué.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-111">The number of CPUs used to perform the operation is also reported.</span></span>|  
|[<span data-ttu-id="f0fa6-112">Performance Statistics, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="f0fa6-112">Performance Statistics Event Class</span></span>](performance-statistics-event-class.md)|<span data-ttu-id="f0fa6-113">Contrôle les performances des requêtes exécutées.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-113">Monitors performance of the queries that are being executed.</span></span>|  
|[<span data-ttu-id="f0fa6-114">Classe d'événements Showplan All</span><span class="sxs-lookup"><span data-stu-id="f0fa6-114">Showplan All Event Class</span></span>](showplan-all-event-class.md)|<span data-ttu-id="f0fa6-115">Identifie des opérateurs **Showplan** dans une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-115">Identifies **Showplan** operators within a SQL statement.</span></span>|  
|[<span data-ttu-id="f0fa6-116">Classe d'événements Showplan All for Query Compile</span><span class="sxs-lookup"><span data-stu-id="f0fa6-116">Showplan All for Query Compile Event Class</span></span>](showplan-all-for-query-compile-event-class.md)|<span data-ttu-id="f0fa6-117">Affiche des données temporelles de compilation pour des opérateurs **Showplan** .</span><span class="sxs-lookup"><span data-stu-id="f0fa6-117">Displays compile time data for **Showplan** operators.</span></span>|  
|[<span data-ttu-id="f0fa6-118">Classe d'événements Showplan Statistics Profile</span><span class="sxs-lookup"><span data-stu-id="f0fa6-118">Showplan Statistics Profile Event Class</span></span>](showplan-statistics-profile-event-class.md)|<span data-ttu-id="f0fa6-119">Affiche le coût estimé d'une requête.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-119">Displays the estimated cost of a query.</span></span>|  
|[<span data-ttu-id="f0fa6-120">Showplan XML, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="f0fa6-120">Showplan XML Event Class</span></span>](showplan-xml-event-class.md)|<span data-ttu-id="f0fa6-121">Identifie les opérateurs **Showplan** dans une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-121">Identifies the **Showplan** operators in a SQL statement.</span></span> <span data-ttu-id="f0fa6-122">La classe d'événements stocke chaque événement sous la forme d'un document XML bien défini.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-122">The event class stores each event as a well defined XML document.</span></span>|  
|[<span data-ttu-id="f0fa6-123">Classe d'événements Showplan XML for Query Compile</span><span class="sxs-lookup"><span data-stu-id="f0fa6-123">Showplan XML for Query Compile Event Class</span></span>](showplan-xml-for-query-compile-event-class.md)|<span data-ttu-id="f0fa6-124">Affiche des données temporelles de compilation pour des opérateurs **Showplan** au format XML.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-124">Displays compile time data for **Showplan** operators in XML format.</span></span>|  
|[<span data-ttu-id="f0fa6-125">Classe d'événements Showplan XML Statistics Profile</span><span class="sxs-lookup"><span data-stu-id="f0fa6-125">Showplan XML Statistics Profile Event Class</span></span>](showplan-xml-statistics-profile-event-class.md)|<span data-ttu-id="f0fa6-126">Identifie les opérateurs **Showplan** associés à une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-126">Identifies the **Showplan** operators associated with a SQL statement.</span></span> <span data-ttu-id="f0fa6-127">La sortie est un document XML.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-127">The output is an XML document.</span></span>|  
|[<span data-ttu-id="f0fa6-128">SQL:FullTextQuery, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="f0fa6-128">SQL:FullTextQuery Event Class</span></span>](sql-fulltextquery-event-class.md)|<span data-ttu-id="f0fa6-129">Indique que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a exécuté une requête de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-129">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a full-text query.</span></span>|  
|[<span data-ttu-id="f0fa6-130">Plan Guide Successful, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="f0fa6-130">Plan Guide Successful Event Class</span></span>](plan-guide-successful-event-class.md)|<span data-ttu-id="f0fa6-131">Indique que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a pu produire un plan d'exécution pour une requête ou un lot qui contenait un repère de plan.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-131">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] successfully produced an execution plan for a query or batch that contained a plan guide.</span></span>|  
|[<span data-ttu-id="f0fa6-132">Plan Guide Unsuccessful, classe d’événements</span><span class="sxs-lookup"><span data-stu-id="f0fa6-132">Plan Guide Unsuccessful Event Class</span></span>](plan-guide-unsuccessful-event-class.md)|<span data-ttu-id="f0fa6-133">Indique que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'a pas pu produire un plan d'exécution pour une requête ou un lot qui contenait un repère de plan.</span><span class="sxs-lookup"><span data-stu-id="f0fa6-133">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not produce an execution plan for a query or batch that contained a plan guide.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0fa6-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0fa6-134">See Also</span></span>  
 [<span data-ttu-id="f0fa6-135">Événements étendus</span><span class="sxs-lookup"><span data-stu-id="f0fa6-135">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
