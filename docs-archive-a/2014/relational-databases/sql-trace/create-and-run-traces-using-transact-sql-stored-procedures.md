---
title: Créer et exécuter des traces à l’aide de procédures stockées Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 80347417-338d-4bea-8885-91fae5181cfe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2905ce2822598502ef6337d1a083fb6fde001c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611005"
---
# <a name="create-and-run-traces-using-transact-sql-stored-procedures"></a><span data-ttu-id="3525b-102">Créer et exécuter des traces à l'aide de procédures stockées Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="3525b-102">Create and Run Traces Using Transact-SQL Stored Procedures</span></span>
  <span data-ttu-id="3525b-103">Le processus de trace à l'aide de la trace SQL varie en fonction de la façon dont vous avez créé et exécuté votre trace, à savoir au moyen du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] de Microsoft ou via les procédures stockées système.</span><span class="sxs-lookup"><span data-stu-id="3525b-103">The process of tracing with SQL Trace varies depending on whether you create and run your trace by using Microsoft [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or by using system stored procedures.</span></span>  
  
 <span data-ttu-id="3525b-104">Une alternative au [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]est représentée par les procédures stockées système [!INCLUDE[tsql](../../includes/tsql-md.md)] qui permettent de créer et d'exécuter des traces.</span><span class="sxs-lookup"><span data-stu-id="3525b-104">As an alternative to [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create and run traces.</span></span> <span data-ttu-id="3525b-105">La procédure de trace à l'aide des procédures stockées système est la suivante :</span><span class="sxs-lookup"><span data-stu-id="3525b-105">The process of tracing by using system stored procedures is as follows:</span></span>  
  
1.  <span data-ttu-id="3525b-106">Créez une trace en exécutant **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="3525b-106">Create a trace by using **sp_trace_create**.</span></span>  
  
2.  <span data-ttu-id="3525b-107">Ajoutez des événements à l’aide de **sp_trace_setevent**.</span><span class="sxs-lookup"><span data-stu-id="3525b-107">Add events with **sp_trace_setevent**.</span></span>  
  
3.  <span data-ttu-id="3525b-108">(Facultatif) Définissez un filtre avec **sp_trace_setfilter**.</span><span class="sxs-lookup"><span data-stu-id="3525b-108">(Optional) Set a filter with **sp_trace_setfilter**.</span></span>  
  
4.  <span data-ttu-id="3525b-109">Démarrez la trace avec **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="3525b-109">Start the trace with **sp_trace_setstatus**.</span></span>  
  
5.  <span data-ttu-id="3525b-110">Arrêtez la trace avec **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="3525b-110">Stop the trace with **sp_trace_setstatus**.</span></span>  
  
6.  <span data-ttu-id="3525b-111">Fermez la trace avec **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="3525b-111">Close the trace with **sp_trace_setstatus**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3525b-112">L'utilisation des procédures stockées système [!INCLUDE[tsql](../../includes/tsql-md.md)] crée une trace serveur qui garantit qu'aucun événement ne sera perdu aussi longtemps qu'il restera de la place sur le disque et qu'aucune erreur d'écriture ne se produira.</span><span class="sxs-lookup"><span data-stu-id="3525b-112">Using [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures creates a server-side trace, which guarantees that no events will be lost as long as there is space on the disk and no write errors occur.</span></span> <span data-ttu-id="3525b-113">Si le disque est plein ou s'il présente une défaillance, l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] continuera à s'exécuter, mais la trace s'arrêtera.</span><span class="sxs-lookup"><span data-stu-id="3525b-113">If the disk becomes full or the disk fails, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance continues to run, but tracing stops.</span></span> <span data-ttu-id="3525b-114">Si l'option **c2 audit mode** est définie et qu'il se produit une erreur d'écriture, la trace cesse et l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'arrête.</span><span class="sxs-lookup"><span data-stu-id="3525b-114">If the **c2 audit mode** is set, and there is a write failure, tracing stops and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span> <span data-ttu-id="3525b-115">Pour plus d’informations sur le paramètre **Mode d’audit c2** , consultez [Mode d’audit C2 (option de configuration de serveur)](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="3525b-115">For more information about the **c2 audit mode** setting, see [c2 audit mode Server Configuration Option](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3525b-116">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3525b-116">In This Section</span></span>  
  
|<span data-ttu-id="3525b-117">Rubrique</span><span class="sxs-lookup"><span data-stu-id="3525b-117">Topic</span></span>|<span data-ttu-id="3525b-118">Description</span><span class="sxs-lookup"><span data-stu-id="3525b-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3525b-119">Optimiser Trace SQL</span><span class="sxs-lookup"><span data-stu-id="3525b-119">Optimize SQL Trace</span></span>](sql-trace.md)|<span data-ttu-id="3525b-120">Contient des informations sur les manières de réduire les effets de la trace sur les performances du système.</span><span class="sxs-lookup"><span data-stu-id="3525b-120">Contains information about ways you can reduce the effects of tracing on system performance.</span></span>|  
|[<span data-ttu-id="3525b-121">Filtrer une trace</span><span class="sxs-lookup"><span data-stu-id="3525b-121">Filter a Trace</span></span>](filter-a-trace.md)|<span data-ttu-id="3525b-122">Contient des informations sur l'utilisation de filtres pour la trace.</span><span class="sxs-lookup"><span data-stu-id="3525b-122">Contains information about using filters for tracing.</span></span>|  
|[<span data-ttu-id="3525b-123">Limiter les tailles de fichier et de table de trace</span><span class="sxs-lookup"><span data-stu-id="3525b-123">Limit Trace File and Table Sizes</span></span>](limit-trace-file-and-table-sizes.md)|<span data-ttu-id="3525b-124">Contient des informations sur la façon de limiter la taille des fichiers et des tables où les données de trace sont écrites.</span><span class="sxs-lookup"><span data-stu-id="3525b-124">Contains information about how to limit the size of files and tables where trace data is written.</span></span> <span data-ttu-id="3525b-125">Notez que seul le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] peut écrire les données de trace dans des tables.</span><span class="sxs-lookup"><span data-stu-id="3525b-125">Note that only [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can write trace information to tables.</span></span>|  
|[<span data-ttu-id="3525b-126">Planifier les traces</span><span class="sxs-lookup"><span data-stu-id="3525b-126">Schedule Traces</span></span>](schedule-traces.md)|<span data-ttu-id="3525b-127">Contient des informations sur la façon de définir l'heure de démarrage et l'heure de fin de la trace.</span><span class="sxs-lookup"><span data-stu-id="3525b-127">Contains information about how to set the start time and the end time for tracing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3525b-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3525b-128">See Also</span></span>  
 <span data-ttu-id="3525b-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3525b-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="3525b-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3525b-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="3525b-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3525b-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span></span>  
 [<span data-ttu-id="3525b-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3525b-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
  
