---
title: Créer une trace (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], example
- traces [SQL Server], creating
ms.assetid: 79dd4254-e3c6-467a-bb6f-f99e51757e99
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 35644891b2dca8359d6dc68fbddb67288d241cb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611004"
---
# <a name="create-a-trace-transact-sql"></a><span data-ttu-id="54776-102">Créer une trace (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="54776-102">Create a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="54776-103">Cette rubrique explique comment créer une trace à l'aide de procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="54776-103">This topic describes how to use stored procedures to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="54776-104">Pour créer une trace</span><span class="sxs-lookup"><span data-stu-id="54776-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="54776-105">Exécutez **sp_trace_create** avec les paramètres nécessaires afin de créer une nouvelle trace.</span><span class="sxs-lookup"><span data-stu-id="54776-105">Execute **sp_trace_create** with the required parameters to create a new trace.</span></span> <span data-ttu-id="54776-106">La nouvelle trace est à l’état arrêté (*status* a la valeur **0**).</span><span class="sxs-lookup"><span data-stu-id="54776-106">The new trace will be in a stopped state (*status* is **0**).</span></span>  
  
2.  <span data-ttu-id="54776-107">Exécutez **sp_trace_setevent** avec les paramètres requis pour choisir les événements et les colonnes que vous voulez tracer.</span><span class="sxs-lookup"><span data-stu-id="54776-107">Execute **sp_trace_setevent** with the required parameters to select the events and columns to trace.</span></span>  
  
3.  <span data-ttu-id="54776-108">Vous pouvez aussi exécuter **sp_trace_setfilter** pour définir un ou plusieurs filtres.</span><span class="sxs-lookup"><span data-stu-id="54776-108">Optionally, execute **sp_trace_setfilter** to set any or a combination of filters.</span></span>  
  
     <span data-ttu-id="54776-109">**sp_trace_setevent** et **sp_trace_setfilter** ne peuvent être exécutées que sur des traces existantes arrêtées.</span><span class="sxs-lookup"><span data-stu-id="54776-109">**sp_trace_setevent** and **sp_trace_setfilter** can be executed only on existing traces that are stopped.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="54776-110">Contrairement aux procédures stockées standard, les paramètres de toutes les procédures stockées de SQL Server Profiler (<strong>sp_trace_*xx*</strong>) sont strictement typés et ne prennent pas en charge la conversion automatique des types de données.</span><span class="sxs-lookup"><span data-stu-id="54776-110">Unlike regular stored procedures, parameters of all SQL Server Profiler stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="54776-111">Si ces paramètres ne sont pas appelés à l'aide des types de données appropriés pour les paramètres d'entrée tels qu'ils sont spécifiés dans la description de l'argument, la procédure stockée retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="54776-111">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54776-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="54776-112">Example</span></span>  
 <span data-ttu-id="54776-113">L'exemple de code suivant montre comment créer une trace à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54776-113">The following code demonstrates creating a trace using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="54776-114">Il est divisé en trois sections : création de la trace, remplissage du fichier de trace et arrêt de la trace.</span><span class="sxs-lookup"><span data-stu-id="54776-114">It is in three sections: creating the trace, populating the trace file, and stopping the trace.</span></span> <span data-ttu-id="54776-115">Personnalisez la trace en ajoutant les événements dont vous souhaitez effectuer le suivi.</span><span class="sxs-lookup"><span data-stu-id="54776-115">Customize the trace by adding the events that you want to trace.</span></span> <span data-ttu-id="54776-116">Pour obtenir la liste des événements et des colonnes, consultez [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54776-116">For the list of events and columns, see [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql).</span></span>  
  
 <span data-ttu-id="54776-117">Le code suivant crée une trace, y ajoute des événements, puis la démarre :</span><span class="sxs-lookup"><span data-stu-id="54776-117">The following code creates a trace, adds events to the trace, and then starts the trace:</span></span>  
  
```  
DECLARE @RC int, @TraceID int, @on BIT  
EXEC @rc = sp_trace_create @TraceID output, 0, N'C:\SampleTrace'  
  
-- Select the return code to see if the trace creation was successful.  
SELECT RC = @RC, TraceID = @TraceID  
  
-- Set the events and data columns you need to capture.  
SELECT @on = 1  
  
-- 10 is RPC:Completed event. 1 is TextData column.   
EXEC sp_trace_setevent @TraceID, 10, 1, @on   
-- 13 is SQL:BatchStarting, 11 is LoginName  
EXEC sp_trace_setevent @TraceID, 13, 11, @on   
-- 13 is SQL:BatchStarting, 14 is StartTime  
EXEC sp_trace_setevent @TraceID, 13, 14, @on   
-- 12 is SQL:BatchCompleted, 15 is EndTime  
EXEC sp_trace_setevent @TraceID, 12, 15, @on   
-- 13 is SQL:BatchStarting, 1 is TextData  
EXEC sp_trace_setevent @TraceID, 13, 1, @on   
  
-- Set any filter. Not provided in this example  
--EXEC sp_trace_setfilter 1, 10, 0, 6, N'%Profiler%'  
  
-- Start Trace (status 1 = start)  
EXEC @RC = sp_trace_setstatus @TraceID, 1  
GO  
  
```  
  
## <a name="example"></a><span data-ttu-id="54776-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="54776-118">Example</span></span>  
 <span data-ttu-id="54776-119">Maintenant que la trace a été créée et démarrée, exécutez le code ci-dessous pour la remplir avec l'activité.</span><span class="sxs-lookup"><span data-stu-id="54776-119">Now that the trace has been created and started, execute the following code to populate the trace with activity.</span></span>  
  
```  
SELECT * FROM master.sys.databases  
GO  
SELECT * FROM ::fn_trace_getinfo(default)  
GO  
  
```  
  
## <a name="example"></a><span data-ttu-id="54776-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="54776-120">Example</span></span>  
 <span data-ttu-id="54776-121">La trace peut être arrêtée et redémarrée à tout moment.</span><span class="sxs-lookup"><span data-stu-id="54776-121">The trace can be stopped and restarted at any time.</span></span> <span data-ttu-id="54776-122">Dans cet exemple, exécutez le code ci-dessous pour arrêter et fermer la trace, puis supprimer sa définition.</span><span class="sxs-lookup"><span data-stu-id="54776-122">In this example, execute the following code to stop the trace, close the trace, and delete the trace definition.</span></span>  
  
```  
DECLARE @TraceID int  
-- Populate a variable with the trace_id of the current trace  
SELECT  @TraceID = TraceID FROM ::fn_trace_getinfo(default) WHERE VALUE = N'C:\SampleTrace.trc'  
  
-- First stop the trace.   
EXEC sp_trace_setstatus @TraceID, 0  
  
-- Close and then delete its definition from SQL Server.   
EXEC sp_trace_setstatus @TraceID, 2  
  
```  
  
## <a name="example"></a><span data-ttu-id="54776-123">Exemple</span><span class="sxs-lookup"><span data-stu-id="54776-123">Example</span></span>  
 <span data-ttu-id="54776-124">Pour examiner le fichier de trace, ouvrez le fichier SampleTrace.trc à l'aide de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54776-124">To examine the trace file, open the SampleTrace.trc file using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54776-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54776-125">See Also</span></span>  
 <span data-ttu-id="54776-126">[Procédures stockées de SQL Server Profiler &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54776-126">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="54776-127">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54776-127">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="54776-128">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54776-128">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="54776-129">sp_trace_setfilter &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="54776-129">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)  
  
  
