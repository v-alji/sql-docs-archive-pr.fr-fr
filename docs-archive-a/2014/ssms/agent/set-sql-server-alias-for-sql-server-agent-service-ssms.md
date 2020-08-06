---
title: Définir un filtre de trace (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- traces [SQL Server], filters
ms.assetid: 7b976a84-7381-43a6-a828-ba83ada71cbe
author: stevestein
ms.author: sstein
ms.openlocfilehash: 47d797c84a05f50da026280f6e197f965d804426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611490"
---
# <a name="set-a-trace-filter-transact-sql"></a><span data-ttu-id="fdfca-102">Définir un filtre de trace (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fdfca-102">Set a Trace Filter (Transact-SQL)</span></span>
  <span data-ttu-id="fdfca-103">Cette rubrique explique comment utiliser des procédures stockées pour créer un filtre qui n'extrait que les informations requises lors d'un événement en cours de traçage.</span><span class="sxs-lookup"><span data-stu-id="fdfca-103">This topic describes how to use stored procedures to create a filter that retrieves only the information you need on an event being traced.</span></span>  
  
### <a name="to-set-a-trace-filter"></a><span data-ttu-id="fdfca-104">Pour définir un filtre de trace</span><span class="sxs-lookup"><span data-stu-id="fdfca-104">To set a trace filter</span></span>  
  
1.  <span data-ttu-id="fdfca-105">Si la trace est déjà en cours d’exécution, exécutez **sp_trace_setstatus** en spécifiant **\@status = 0**  pour l’arrêter.</span><span class="sxs-lookup"><span data-stu-id="fdfca-105">If the trace is already running, execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="fdfca-106">Exécutez **sp_trace_setfilter** pour configurer le type d’informations extraites pour l’événement dont vous voulez suivre la trace.</span><span class="sxs-lookup"><span data-stu-id="fdfca-106">Execute **sp_trace_setfilter** to configure the type of information to retrieve for the event being traced.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fdfca-107">Contrairement aux procédures stockées standard, les paramètres de toutes les procédures stockées [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] (<strong>sp_trace_*xx*</strong>) sont strictement typés et ne prennent pas en charge la conversion automatique des types de données.</span><span class="sxs-lookup"><span data-stu-id="fdfca-107">Unlike regular stored procedures, parameters of all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="fdfca-108">Si ces paramètres ne sont pas appelés avec des types de données appropriés pour les paramètres d'entrée tels qu'ils sont spécifiés dans la description de l'argument, la procédure stockée renvoie une erreur.</span><span class="sxs-lookup"><span data-stu-id="fdfca-108">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure will return an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfca-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fdfca-109">See Also</span></span>  
 <span data-ttu-id="fdfca-110">[Filtrer une trace](../../relational-databases/sql-trace/filter-a-trace.md) </span><span class="sxs-lookup"><span data-stu-id="fdfca-110">[Filter a Trace](../../relational-databases/sql-trace/filter-a-trace.md) </span></span>  
 <span data-ttu-id="fdfca-111">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdfca-111">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span></span>  
 <span data-ttu-id="fdfca-112">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdfca-112">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="fdfca-113">[Procédures stockées système &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdfca-113">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="fdfca-114">Procédures stockées de SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fdfca-114">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
