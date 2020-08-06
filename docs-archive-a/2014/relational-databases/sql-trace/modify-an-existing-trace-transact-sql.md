---
title: Modifier une trace existante (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], modifying
- modifying traces
ms.assetid: 8792b43f-2510-44e3-9239-e73ad8227b89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 55b8172ef8e6188059c484ab41f1a719e0e9f8c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601291"
---
# <a name="modify-an-existing-trace-transact-sql"></a><span data-ttu-id="3be58-102">Modifier une trace existante (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3be58-102">Modify an Existing Trace (Transact-SQL)</span></span>
  <span data-ttu-id="3be58-103">Cette rubrique décrit l'utilisation de procédures stockées pour modifier une trace existante.</span><span class="sxs-lookup"><span data-stu-id="3be58-103">This topic describes how to use stored procedures to modify an existing trace.</span></span>  
  
### <a name="to-modify-an-existing-trace"></a><span data-ttu-id="3be58-104">Pour modifier une trace existante</span><span class="sxs-lookup"><span data-stu-id="3be58-104">To modify an existing trace</span></span>  
  
1.  <span data-ttu-id="3be58-105">Si la trace est déjà en cours d’exécution, exécutez **sp_trace_setstatus** en spécifiant **\@status = 0**  pour l’arrêter.</span><span class="sxs-lookup"><span data-stu-id="3be58-105">If the trace is already running, execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="3be58-106">Pour modifier des événements de trace, exécutez **sp_trace_setevent** en spécifiant les modifications à l’aide des paramètres.</span><span class="sxs-lookup"><span data-stu-id="3be58-106">To modify trace events, execute **sp_trace_setevent** by specifying the changes through the parameters.</span></span> <span data-ttu-id="3be58-107">Dans l'ordre, les paramètres sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3be58-107">Listed in order, the parameters are:</span></span>  
  
    -   <span data-ttu-id="3be58-108">**@traceid**(ID de trace)</span><span class="sxs-lookup"><span data-stu-id="3be58-108">**@traceid** (Trace ID)</span></span>  
  
    -   <span data-ttu-id="3be58-109">**@eventid**(ID d’événement)</span><span class="sxs-lookup"><span data-stu-id="3be58-109">**@eventid** (Event ID)</span></span>  
  
    -   <span data-ttu-id="3be58-110">**@columnid**(ID de colonne)</span><span class="sxs-lookup"><span data-stu-id="3be58-110">**@columnid** (Column ID)</span></span>  
  
    -   <span data-ttu-id="3be58-111">**@on**SUR</span><span class="sxs-lookup"><span data-stu-id="3be58-111">**@on** (ON)</span></span>  
  
     <span data-ttu-id="3be58-112">Lorsque vous modifiez le **@on** paramètre, gardez à l’esprit son interaction avec le **@columnid** paramètre :</span><span class="sxs-lookup"><span data-stu-id="3be58-112">When you modify the **@on** parameter, keep in mind its interaction with the **@columnid** parameter:</span></span>  
  
    |<span data-ttu-id="3be58-113">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="3be58-113">ON</span></span>|<span data-ttu-id="3be58-114">ID de la colonne</span><span class="sxs-lookup"><span data-stu-id="3be58-114">Column ID</span></span>|<span data-ttu-id="3be58-115">Résultats</span><span class="sxs-lookup"><span data-stu-id="3be58-115">Result</span></span>|  
    |--------|---------------|------------|  
    |<span data-ttu-id="3be58-116">ON (**1**)</span><span class="sxs-lookup"><span data-stu-id="3be58-116">ON (**1**)</span></span>|<span data-ttu-id="3be58-117">NULL</span><span class="sxs-lookup"><span data-stu-id="3be58-117">NULL</span></span>|<span data-ttu-id="3be58-118">Événement activé.</span><span class="sxs-lookup"><span data-stu-id="3be58-118">Event is turned on.</span></span> <span data-ttu-id="3be58-119">Toutes les colonnes sont effacées.</span><span class="sxs-lookup"><span data-stu-id="3be58-119">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="3be58-120">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="3be58-120">NOT NULL</span></span>|<span data-ttu-id="3be58-121">La colonne est activée pour l'événement spécifié.</span><span class="sxs-lookup"><span data-stu-id="3be58-121">Column is turned on for the specified event.</span></span>|  
    |<span data-ttu-id="3be58-122">OFF (**0**)</span><span class="sxs-lookup"><span data-stu-id="3be58-122">OFF (**0**)</span></span>|<span data-ttu-id="3be58-123">NULL</span><span class="sxs-lookup"><span data-stu-id="3be58-123">NULL</span></span>|<span data-ttu-id="3be58-124">Événement désactivé.</span><span class="sxs-lookup"><span data-stu-id="3be58-124">Event is turned off.</span></span> <span data-ttu-id="3be58-125">Toutes les colonnes sont effacées.</span><span class="sxs-lookup"><span data-stu-id="3be58-125">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="3be58-126">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="3be58-126">NOT NULL</span></span>|<span data-ttu-id="3be58-127">La colonne est désactivée pour l'événement spécifié.</span><span class="sxs-lookup"><span data-stu-id="3be58-127">Column is turned off for the specified event.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="3be58-128">Contrairement aux procédures stockées standard, les paramètres de toutes les procédures stockées [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] (<strong>sp_trace_*xx*</strong>) sont strictement typés et ne prennent pas en charge la conversion automatique des types de données.</span><span class="sxs-lookup"><span data-stu-id="3be58-128">Unlike regular stored procedures, parameters of all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="3be58-129">Si ces paramètres ne sont pas appelés à l'aide des types de données appropriés pour les paramètres d'entrée tels qu'ils sont spécifiés dans la description de l'argument, la procédure stockée retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="3be58-129">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3be58-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3be58-130">See Also</span></span>  
 <span data-ttu-id="3be58-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3be58-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="3be58-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3be58-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="3be58-133">[Procédures stockées système &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3be58-133">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="3be58-134">Procédures stockées de SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3be58-134">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
