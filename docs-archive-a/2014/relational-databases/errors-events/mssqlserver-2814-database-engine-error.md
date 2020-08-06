---
title: MSSQLSERVER_2814 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2814 (Database Engine error)
ms.assetid: 22800748-9be9-4511-9428-6b8b40e5bef9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 26b1fae5b683ed72cb93c3f81981bd41e2f4ad4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605489"
---
# <a name="mssqlserver_2814"></a><span data-ttu-id="d8977-102">MSSQLSERVER_2814</span><span class="sxs-lookup"><span data-stu-id="d8977-102">MSSQLSERVER_2814</span></span>
    
## <a name="details"></a><span data-ttu-id="d8977-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d8977-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8977-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d8977-104">Product Name</span></span>|<span data-ttu-id="d8977-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8977-105">SQL Server</span></span>|  
|<span data-ttu-id="d8977-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d8977-106">Event ID</span></span>|<span data-ttu-id="d8977-107">2814</span><span class="sxs-lookup"><span data-stu-id="d8977-107">2814</span></span>|  
|<span data-ttu-id="d8977-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d8977-108">Event Source</span></span>|<span data-ttu-id="d8977-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d8977-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d8977-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d8977-110">Component</span></span>|<span data-ttu-id="d8977-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d8977-111">SQLEngine</span></span>|  
|<span data-ttu-id="d8977-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d8977-112">Symbolic Name</span></span>|<span data-ttu-id="d8977-113">PR_POSSIBLE_INFINITE_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="d8977-113">PR_POSSIBLE_INFINITE_RECOMPILE</span></span>|  
|<span data-ttu-id="d8977-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d8977-114">Message Text</span></span>|<span data-ttu-id="d8977-115">Recompilation infinie détectée pour SQLHANDLE %hs, PlanHandle %hs, décalage de début %d, décalage de fin %d.</span><span class="sxs-lookup"><span data-stu-id="d8977-115">A possible infinite recompile was detected for SQLHANDLE %hs, PlanHandle %hs, starting offset %d, ending offset %d.</span></span> <span data-ttu-id="d8977-116">Dernière raison de la recompilation : %d.</span><span class="sxs-lookup"><span data-stu-id="d8977-116">The last recompile reason was %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8977-117">Explication</span><span class="sxs-lookup"><span data-stu-id="d8977-117">Explanation</span></span>  
 <span data-ttu-id="d8977-118">Une ou plusieurs instructions ont provoqué la recompilation du lot de requêtes au moins 50 fois.</span><span class="sxs-lookup"><span data-stu-id="d8977-118">One or more statements caused the query batch to recompile at least 50 times.</span></span> <span data-ttu-id="d8977-119">L'instruction spécifiée doit être corrigée pour éviter d'autres recompilations.</span><span class="sxs-lookup"><span data-stu-id="d8977-119">The specified statement should be corrected to avoid further recompilations.</span></span>  
  
 <span data-ttu-id="d8977-120">Le tableau suivant répertorie les raisons de la recompilation.</span><span class="sxs-lookup"><span data-stu-id="d8977-120">The following table lists the reasons for recompilation.</span></span>  
  
|<span data-ttu-id="d8977-121">Code de la raison</span><span class="sxs-lookup"><span data-stu-id="d8977-121">Reason code</span></span>|<span data-ttu-id="d8977-122">Description</span><span class="sxs-lookup"><span data-stu-id="d8977-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d8977-123">1</span><span class="sxs-lookup"><span data-stu-id="d8977-123">1</span></span>|<span data-ttu-id="d8977-124">Schéma modifié</span><span class="sxs-lookup"><span data-stu-id="d8977-124">Schema changed</span></span>|  
|<span data-ttu-id="d8977-125">2</span><span class="sxs-lookup"><span data-stu-id="d8977-125">2</span></span>|<span data-ttu-id="d8977-126">Statistiques modifiées</span><span class="sxs-lookup"><span data-stu-id="d8977-126">Statistics changed</span></span>|  
|<span data-ttu-id="d8977-127">3</span><span class="sxs-lookup"><span data-stu-id="d8977-127">3</span></span>|<span data-ttu-id="d8977-128">Compilation différée</span><span class="sxs-lookup"><span data-stu-id="d8977-128">Deferred compile</span></span>|  
|<span data-ttu-id="d8977-129">4</span><span class="sxs-lookup"><span data-stu-id="d8977-129">4</span></span>|<span data-ttu-id="d8977-130">Option Set modifiée</span><span class="sxs-lookup"><span data-stu-id="d8977-130">Set option changed</span></span>|  
|<span data-ttu-id="d8977-131">5</span><span class="sxs-lookup"><span data-stu-id="d8977-131">5</span></span>|<span data-ttu-id="d8977-132">Table temporaire modifiée</span><span class="sxs-lookup"><span data-stu-id="d8977-132">Temp table changed</span></span>|  
|<span data-ttu-id="d8977-133">6</span><span class="sxs-lookup"><span data-stu-id="d8977-133">6</span></span>|<span data-ttu-id="d8977-134">Ensemble de lignes à distance modifié</span><span class="sxs-lookup"><span data-stu-id="d8977-134">Remote rowset changed</span></span>|  
|<span data-ttu-id="d8977-135">7</span><span class="sxs-lookup"><span data-stu-id="d8977-135">7</span></span>|<span data-ttu-id="d8977-136">Autorisations de recherche modifiées</span><span class="sxs-lookup"><span data-stu-id="d8977-136">For Browse permissions changed</span></span>|  
|<span data-ttu-id="d8977-137">8</span><span class="sxs-lookup"><span data-stu-id="d8977-137">8</span></span>|<span data-ttu-id="d8977-138">Environnement de notification de requête modifié</span><span class="sxs-lookup"><span data-stu-id="d8977-138">Query notification environment changed</span></span>|  
|<span data-ttu-id="d8977-139">9</span><span class="sxs-lookup"><span data-stu-id="d8977-139">9</span></span>|<span data-ttu-id="d8977-140">Affichage partition modifié</span><span class="sxs-lookup"><span data-stu-id="d8977-140">Partition view changed</span></span>|  
|<span data-ttu-id="d8977-141">10</span><span class="sxs-lookup"><span data-stu-id="d8977-141">10</span></span>|<span data-ttu-id="d8977-142">Options de curseur modifiées</span><span class="sxs-lookup"><span data-stu-id="d8977-142">Cursor options changed</span></span>|  
|<span data-ttu-id="d8977-143">11</span><span class="sxs-lookup"><span data-stu-id="d8977-143">11</span></span>|<span data-ttu-id="d8977-144">Option (recompilation) demandée.</span><span class="sxs-lookup"><span data-stu-id="d8977-144">Option (recompile) requested</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="d8977-145">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d8977-145">User Action</span></span>  
  
1.  <span data-ttu-id="d8977-146">Affichez l'instruction qui engendre la recompilation en exécutant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="d8977-146">View the statement causing the recompilation by running the following query.</span></span> <span data-ttu-id="d8977-147">Remplacez les espaces réservés *sql_handle*, *starting_offset*, *ending_offset*, et *plan_handle* par les valeurs spécifiées dans le message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="d8977-147">Replace the *sql_handle*, *starting_offset*, *ending_offset*, and *plan_handle* placeholders with the values specified in the error message.</span></span> <span data-ttu-id="d8977-148">Notez que les colonnes **database_name** et **object_name** seront NULL pour les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc et préparées.</span><span class="sxs-lookup"><span data-stu-id="d8977-148">Note that the **database_name** and **object_name** columns will be NULL for ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="d8977-149">SELECT DB_NAME(st.dbid) AS database_name</span><span class="sxs-lookup"><span data-stu-id="d8977-149">SELECT DB_NAME(st.dbid) AS database_name</span></span>  
  
     <span data-ttu-id="d8977-150">, OBJECT_NAME(st.objectid) AS object_name</span><span class="sxs-lookup"><span data-stu-id="d8977-150">, OBJECT_NAME(st.objectid) AS object_name</span></span>  
  
     <span data-ttu-id="d8977-151">, st.text</span><span class="sxs-lookup"><span data-stu-id="d8977-151">, st.text</span></span>  
  
     <span data-ttu-id="d8977-152">FROM sys.dm_exec_query_stats AS qs</span><span class="sxs-lookup"><span data-stu-id="d8977-152">FROM sys.dm_exec_query_stats AS qs</span></span>  
  
     <span data-ttu-id="d8977-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span><span class="sxs-lookup"><span data-stu-id="d8977-153">CROSS APPLY sys.dm_exec_sql_text (*sql_handle*) AS st</span></span>  
  
     <span data-ttu-id="d8977-154">WHERE qs.statement_start_offset = *starting_offset*</span><span class="sxs-lookup"><span data-stu-id="d8977-154">WHERE qs.statement_start_offset = *starting_offset*</span></span>  
  
     <span data-ttu-id="d8977-155">AND qs.statement_end_offset = *ending_offset*</span><span class="sxs-lookup"><span data-stu-id="d8977-155">AND qs.statement_end_offset = *ending_offset*</span></span>  
  
     <span data-ttu-id="d8977-156">AND qs.plan_handle = *plan_handle*;</span><span class="sxs-lookup"><span data-stu-id="d8977-156">AND qs.plan_handle = *plan_handle*;</span></span>  
  
2.  <span data-ttu-id="d8977-157">En fonction de la description du code de la raison, modifiez l'instruction, le lot ou la procédure pour éviter les recompilations.</span><span class="sxs-lookup"><span data-stu-id="d8977-157">Based on the reason code description, modify the statement, batch, or procedure to avoid recompilations.</span></span> <span data-ttu-id="d8977-158">Par exemple, une procédure stockée peut contenir une ou plusieurs instructions SET.</span><span class="sxs-lookup"><span data-stu-id="d8977-158">For example, a stored procedure may contain one or more SET statements.</span></span> <span data-ttu-id="d8977-159">Ces instructions doivent être supprimées de la procédure.</span><span class="sxs-lookup"><span data-stu-id="d8977-159">These statements should be removed from the procedure.</span></span> <span data-ttu-id="d8977-160">Pour plus d’exemples de causes de recompilation et de résolutions, consultez [Batch Compilation, Recompilation, and Plan Caching Issues in SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="d8977-160">For additional examples of recompilation causes and resolutions, see [Batch Compilation, Recompilation, and Plan Caching Issues in SQL Server 2005](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/administrator/cc966425(v=technet.10)).</span></span>  
  
3.  <span data-ttu-id="d8977-161">Si le problème persiste, contactez les services d'assistance Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8977-161">If the problem persists, contact Microsoft Customer Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8977-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8977-162">See Also</span></span>  
 [<span data-ttu-id="d8977-163">Classe d'événements SQL:StmtRecompile</span><span class="sxs-lookup"><span data-stu-id="d8977-163">SQL:StmtRecompile Event Class</span></span>](../event-classes/sql-stmtrecompile-event-class.md)  
  
  
