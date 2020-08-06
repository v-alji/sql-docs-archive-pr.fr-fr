---
title: Packages d’événements étendus SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], packages
- xe
ms.assetid: 6bcb04fc-ca04-48f4-b96a-20b604973447
author: rothja
ms.author: jroth
ms.openlocfilehash: 45c452300c008d486bd1f4ab4c92b5f76b96ecd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600906"
---
# <a name="sql-server-extended-events-packages"></a><span data-ttu-id="4ec6c-102">Packages d’événements étendus SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ec6c-102">SQL Server Extended Events Packages</span></span>
  <span data-ttu-id="4ec6c-103">Un package est un conteneur d'objets d'événements étendus [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4ec6c-103">A package is a container for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Extended Events objects.</span></span> <span data-ttu-id="4ec6c-104">Il existe trois sortes de packages Événements étendus :</span><span class="sxs-lookup"><span data-stu-id="4ec6c-104">There are three kinds of Extended Events packages, which include the following:</span></span>  
  
-   <span data-ttu-id="4ec6c-105">package0 - objets système d'événements étendus.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-105">package0 - Extended Events system objects.</span></span> <span data-ttu-id="4ec6c-106">Il s'agit du package par défaut.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-106">This is the default package.</span></span>  
  
-   <span data-ttu-id="4ec6c-107">sqlserver - objets connexes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4ec6c-107">sqlserver - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] related objects.</span></span>  
  
-   <span data-ttu-id="4ec6c-108">sqlos - objets du système d'exploitation [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SQLOS).</span><span class="sxs-lookup"><span data-stu-id="4ec6c-108">sqlos - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Operating System (SQLOS) related objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ec6c-109">Le package SecAudit est utilisé par [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-109">The SecAudit package is used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit.</span></span> <span data-ttu-id="4ec6c-110">Aucun des objets du package n'est disponible via le langage de définition de données (DDL) Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-110">None of the objects in the package are available through the Extended Events data definition language (DDL).</span></span>  
  
 <span data-ttu-id="4ec6c-111">Les packages sont identifiés par un nom, un GUID et le module binaire qui contient le package.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-111">Packages are identified by a name, a GUID, and the binary module that contains the package.</span></span> <span data-ttu-id="4ec6c-112">Pour plus d’informations, consultez [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4ec6c-112">For more information, see [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span></span>  
  
 <span data-ttu-id="4ec6c-113">Un package peut contenir l'ensemble ou une partie des objets suivants, présentés plus en détails ultérieurement dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="4ec6c-113">A package can contain any or all of the following objects, which are discussed in greater detail later in this topic:</span></span>  
  
-   <span data-ttu-id="4ec6c-114">Événements</span><span class="sxs-lookup"><span data-stu-id="4ec6c-114">Events</span></span>  
  
-   <span data-ttu-id="4ec6c-115">Cibles</span><span class="sxs-lookup"><span data-stu-id="4ec6c-115">Targets</span></span>  
  
-   <span data-ttu-id="4ec6c-116">Actions</span><span class="sxs-lookup"><span data-stu-id="4ec6c-116">Actions</span></span>  
  
-   <span data-ttu-id="4ec6c-117">Types</span><span class="sxs-lookup"><span data-stu-id="4ec6c-117">Types</span></span>  
  
-   <span data-ttu-id="4ec6c-118">Prédicats</span><span class="sxs-lookup"><span data-stu-id="4ec6c-118">Predicates</span></span>  
  
-   <span data-ttu-id="4ec6c-119">Maps</span><span class="sxs-lookup"><span data-stu-id="4ec6c-119">Maps</span></span>  
  
 <span data-ttu-id="4ec6c-120">Des objets de packages différents peuvent être mélangés dans une session d'événements.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-120">Objects from different packages can be mixed in an event session.</span></span> <span data-ttu-id="4ec6c-121">Pour plus d’informations, consultez [Sessions Événements étendus SQL Server](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6c-121">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
## <a name="package-contents"></a><span data-ttu-id="4ec6c-122">Contenu des packages</span><span class="sxs-lookup"><span data-stu-id="4ec6c-122">Package Contents</span></span>  
 <span data-ttu-id="4ec6c-123">L'illustration suivante montre les objets qui peuvent exister dans des packages, inclus dans un module.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-123">The following illustration shows the objects that can exist in packages, which are contained in a module.</span></span> <span data-ttu-id="4ec6c-124">Un module peut être un exécutable ou une bibliothèque de liens dynamiques.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-124">A module can be an executable or a dynamic link library.</span></span>  
  
 <span data-ttu-id="4ec6c-125">![Relation d’un module, de packages et d’objets](../../database-engine/media/xepackagesobjects.gif "Relation d’un module, de packages et d’objets")</span><span class="sxs-lookup"><span data-stu-id="4ec6c-125">![The relationship of a module, packages, and object](../../database-engine/media/xepackagesobjects.gif "The relationship of a module, packages, and object")</span></span>  
  
### <a name="events"></a><span data-ttu-id="4ec6c-126">Événements</span><span class="sxs-lookup"><span data-stu-id="4ec6c-126">Events</span></span>  
 <span data-ttu-id="4ec6c-127">Les événements surveillent les détails intéressants dans le chemin d'exécution d'un programme, tel que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ec6c-127">Events are monitoring points of interest in the execution path of a program, such as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4ec6c-128">Le déclenchement d'un événement indique que le détail intéressant s'est manifesté et fournit les informations d'état correspondant au moment du déclenchement de l'événement.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-128">An event firing carries with it the fact that the point of interest was reached, and state information from the time the event was fired.</span></span>  
  
 <span data-ttu-id="4ec6c-129">Les événements peuvent être utilisés uniquement à des fins de suivi ou pour déclencher des actions.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-129">Events can be used solely for tracing purposes or for triggering actions.</span></span> <span data-ttu-id="4ec6c-130">Ces actions peuvent être synchrones ou asynchrones.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-130">These actions can either be synchronous or asynchronous.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ec6c-131">Un événement n'a aucune connaissance des actions susceptibles d'être déclenchées en réponse à son déclenchement.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-131">An event does not have any knowledge of the actions that may be triggered in response to the event firing.</span></span>  
  
 <span data-ttu-id="4ec6c-132">Un jeu d'événements dans un package ne peut pas changer une fois que le package a été enregistré avec les événements étendus.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-132">A set of events in a package cannot change after the package is registered with Extended Events.</span></span>  
  
 <span data-ttu-id="4ec6c-133">Tous les événements ont un schéma avec contrôle de version qui définit leur contenu.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-133">All events have a versioned schema which defines their contents.</span></span> <span data-ttu-id="4ec6c-134">Ce schéma est composé de colonnes d'événements de types déterminés.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-134">This schema is composed of event columns with well defined types.</span></span> <span data-ttu-id="4ec6c-135">Un événement d'un type spécifique doit toujours fournir ses données exactement dans le même ordre que celui spécifié dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-135">An event of a specific type must always provide its data in exactly the same order that is specified in the schema.</span></span> <span data-ttu-id="4ec6c-136">Toutefois, une cible d'événement n'a pas à consommer toutes les données fournies.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-136">However, an event target does not have to consume all the data that is provided.</span></span>  
  
#### <a name="event-categorization"></a><span data-ttu-id="4ec6c-137">Catégorisation des événements</span><span class="sxs-lookup"><span data-stu-id="4ec6c-137">Event Categorization</span></span>  
 <span data-ttu-id="4ec6c-138">Les événements étendus utilisent un modèle de catégorisation d'événements semblable au suivi d'événements pour Windows.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-138">Extended Events uses an event categorization model similar to Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="4ec6c-139">Deux propriétés d'événement sont utilisées pour la catégorisation, canal et mot clé.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-139">Two event properties are used for categorization, channel and keyword.</span></span> <span data-ttu-id="4ec6c-140">L'utilisation de ces propriétés prend en charge l'intégration des événements étendus avec le suivi ETW et ses outils.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-140">Using these properties supports the integration of Extended Events with ETW and its tools.</span></span>  
  
 <span data-ttu-id="4ec6c-141">**Channel**</span><span class="sxs-lookup"><span data-stu-id="4ec6c-141">**Channel**</span></span>  
  
 <span data-ttu-id="4ec6c-142">Un canal identifie le public concerné par un événement.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-142">A channel identifies the audience for an event.</span></span> <span data-ttu-id="4ec6c-143">Ces canaux sont décrits dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-143">These channels are described in the following table.</span></span>  
  
|<span data-ttu-id="4ec6c-144">Terme</span><span class="sxs-lookup"><span data-stu-id="4ec6c-144">Term</span></span>|<span data-ttu-id="4ec6c-145">Définition</span><span class="sxs-lookup"><span data-stu-id="4ec6c-145">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="4ec6c-146">Admin</span><span class="sxs-lookup"><span data-stu-id="4ec6c-146">Admin</span></span>|<span data-ttu-id="4ec6c-147">Les événements administratifs sont principalement destinés aux utilisateurs finaux, aux administrateurs et au support technique.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-147">Admin events are primarily targeted to the end users, administrators, and support.</span></span> <span data-ttu-id="4ec6c-148">Les événements détectés dans les canaux administratifs font référence à un problème avec une solution déterminée qu'un administrateur peut mettre en place.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-148">The events that are found in the admin channels indicate a problem with a well-defined solution that an administrator can act on.</span></span> <span data-ttu-id="4ec6c-149">Par exemple, le fait qu'une application ne puisse pas se connecter à une imprimante correspond à un événement administratif.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-149">An example of an admin event is when an application fails to connect to a printer.</span></span> <span data-ttu-id="4ec6c-150">Ces événements font l'objet d'une documentation détaillée ou sont accompagnés d'un message qui indique la procédure à suivre pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-150">These events are either well-documented or have a message associated with them that tells the reader what to do to rectify the problem.</span></span>|  
|<span data-ttu-id="4ec6c-151">En fonctionnement</span><span class="sxs-lookup"><span data-stu-id="4ec6c-151">Operational</span></span>|<span data-ttu-id="4ec6c-152">Les événements opérationnels permettent d'analyser et de diagnostiquer un problème ou une occurrence.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-152">Operational events are used for analyzing and diagnosing a problem or occurrence.</span></span> <span data-ttu-id="4ec6c-153">Ils peuvent être utilisés pour déclencher des outils ou des tâches selon le problème ou l'occurrence.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-153">They can be used to trigger tools or tasks based on the problem or occurrence.</span></span> <span data-ttu-id="4ec6c-154">Par exemple, le fait qu'une imprimante soit ajoutée ou supprimée dans un système correspond à un événement opérationnel.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-154">An example of an operational event is when a printer is added or removed from a system.</span></span>|  
|<span data-ttu-id="4ec6c-155">Analytiques</span><span class="sxs-lookup"><span data-stu-id="4ec6c-155">Analytic</span></span>|<span data-ttu-id="4ec6c-156">Les événements analytiques sont publiés selon un volume élevé.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-156">Analytic events are published in high volume.</span></span> <span data-ttu-id="4ec6c-157">Ils décrivent le fonctionnement des programmes et sont généralement utilisés dans les enquêtes sur les performances.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-157">They describe program operation and are typically used in performance investigations.</span></span>|  
|<span data-ttu-id="4ec6c-158">Débogage</span><span class="sxs-lookup"><span data-stu-id="4ec6c-158">Debug</span></span>|<span data-ttu-id="4ec6c-159">Les événements de débogage sont utilisés uniquement par les développeurs pour diagnostiquer un problème afin de le résoudre.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-159">Debug events are used solely by developers to diagnose a problem for debugging.</span></span><br /><br /> <span data-ttu-id="4ec6c-160">Remarque : les événements du canal de débogage renvoient des données d’État propres à l’implémentation interne.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-160">Note: Events in the Debug channel return internal implementation-specific state data.</span></span> <span data-ttu-id="4ec6c-161">Les schémas et les données renvoyées par les événements sont susceptibles de changer ou de ne plus être compatibles avec les prochaines versions de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-161">The schemas and data that the events return may change or become invalid in future versions of SQL Server.</span></span> <span data-ttu-id="4ec6c-162">Par conséquent, les événements du canal de débogage pourront être changés ou supprimés dans les versions à venir de SQL Server sans notification.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-162">Therefore, events in the Debug channel may change or be removed in future versions of SQL Server without notice.</span></span>|  
  
 <span data-ttu-id="4ec6c-163">**Mot clé**</span><span class="sxs-lookup"><span data-stu-id="4ec6c-163">**Keyword**</span></span>  
  
 <span data-ttu-id="4ec6c-164">Un mot clé est spécifique à une application et permet un regroupement plus fin d'événements associés, ce qui vous permet de spécifier et de récupérer plus aisément un événement que vous souhaitez utiliser dans une session.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-164">A keyword is application specific and enables a finer-grained grouping of related events, which makes it easier for you to specify and retrieve an event that you want to use in a session.</span></span> <span data-ttu-id="4ec6c-165">Vous pouvez utiliser la requête suivante pour obtenir des informations sur un mot clé.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-165">You can use the following query to obtain keyword information.</span></span>  
  
```  
select map_value Keyword from sys.dm_xe_map_values  
where name = 'keyword_map'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="4ec6c-166">Les mots clés correspondent étroitement au regroupement actuel des événements SQL Trace.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-166">Keywords map closely to the current grouping of SQL Trace events.</span></span>  
  
### <a name="targets"></a><span data-ttu-id="4ec6c-167">Cibles</span><span class="sxs-lookup"><span data-stu-id="4ec6c-167">Targets</span></span>  
 <span data-ttu-id="4ec6c-168">Les cibles sont des consommateurs d'événements.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-168">Targets are event consumers.</span></span> <span data-ttu-id="4ec6c-169">Les cibles traitent des événements, de façon synchrone sur le thread qui déclenche l'événement ou de façon asynchrone sur un thread fourni par le système.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-169">Targets process events, either synchronously on the thread that fires the event or asynchronously on a system provided thread.</span></span> <span data-ttu-id="4ec6c-170">Les événements étendus fournissent plusieurs cibles que vous pouvez utiliser d'une manière appropriée pour diriger les données de sortie des événements.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-170">Extended Events provides several targets that you can use as appropriate for directing event output.</span></span> <span data-ttu-id="4ec6c-171">Pour plus d'informations, consultez [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="4ec6c-171">For more information, see [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span></span>  
  
### <a name="actions"></a><span data-ttu-id="4ec6c-172">Actions</span><span class="sxs-lookup"><span data-stu-id="4ec6c-172">Actions</span></span>  
 <span data-ttu-id="4ec6c-173">Une action est une réponse de programmation ou une série de réponses à un événement.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-173">An action is a programmatic response or series of responses to an event.</span></span> <span data-ttu-id="4ec6c-174">Les actions sont liées à un événement et chaque événement peut posséder un ensemble unique d'actions.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-174">Actions are bound to an event, and each event may have a unique set of actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ec6c-175">Des actions prévues pour un ensemble spécifique d'événements ne peuvent pas être liées à des événements inconnus.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-175">Actions that are intended for a specific set of events cannot bind to unknown events.</span></span>  
  
 <span data-ttu-id="4ec6c-176">Une action liée à un événement est appelée de façon synchrone sur le thread qui a déclenché l'événement.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-176">An action bound to an event is invoked synchronously on the thread that fired the event.</span></span> <span data-ttu-id="4ec6c-177">Il existe de nombreux types d'actions et elles présentent une gamme étendue de capacités.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-177">There are many types of actions and they have a wide range of capabilities.</span></span> <span data-ttu-id="4ec6c-178">Les actions peuvent correspondre aux opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4ec6c-178">Actions can:</span></span>  
  
-   <span data-ttu-id="4ec6c-179">capturer un vidage de pile et inspecter des données ;</span><span class="sxs-lookup"><span data-stu-id="4ec6c-179">Capture a stack dump and inspect data.</span></span>  
  
-   <span data-ttu-id="4ec6c-180">stocker des informations d'état dans un contexte local par le biais du stockage de variables ;</span><span class="sxs-lookup"><span data-stu-id="4ec6c-180">Store state information in a local context using variable storage.</span></span>  
  
-   <span data-ttu-id="4ec6c-181">agréger des données d'événement ;</span><span class="sxs-lookup"><span data-stu-id="4ec6c-181">Aggregate event data.</span></span>  
  
-   <span data-ttu-id="4ec6c-182">ajouter des données à des données d'événement.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-182">Append data to event data.</span></span>  
  
 <span data-ttu-id="4ec6c-183">Voici quelques exemples typiques et bien connus d'actions :</span><span class="sxs-lookup"><span data-stu-id="4ec6c-183">Some typical and well known examples of actions are:</span></span>  
  
-   <span data-ttu-id="4ec6c-184">Gestionnaire de vidage de pile</span><span class="sxs-lookup"><span data-stu-id="4ec6c-184">Stack dumper</span></span>  
  
-   <span data-ttu-id="4ec6c-185">Détection du plan d'exécution ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uniquement)</span><span class="sxs-lookup"><span data-stu-id="4ec6c-185">Execution plan detection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="4ec6c-186">collection de pile ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uniquement)</span><span class="sxs-lookup"><span data-stu-id="4ec6c-186">stack collection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   <span data-ttu-id="4ec6c-187">Exécuter des calculs statistiques à l'exécution</span><span class="sxs-lookup"><span data-stu-id="4ec6c-187">Run time statistics calculation</span></span>  
  
-   <span data-ttu-id="4ec6c-188">Collecter les entrées utilisateur en cas d'exception</span><span class="sxs-lookup"><span data-stu-id="4ec6c-188">Gather user input on exception</span></span>  
  
### <a name="predicates"></a><span data-ttu-id="4ec6c-189">Prédicats</span><span class="sxs-lookup"><span data-stu-id="4ec6c-189">Predicates</span></span>  
 <span data-ttu-id="4ec6c-190">Les prédicats sont un ensemble de règles logiques qui permettent d'évaluer des événements lorsqu'ils sont traités.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-190">Predicates are a set of logical rules that are used to evaluate events when they are processed.</span></span> <span data-ttu-id="4ec6c-191">Cela permet à l'utilisateur d'événements étendus de capturer de manière sélective des données d'événement en fonction de critères spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-191">This enables the Extended Events user to selectively capture event data based on specific criteria.</span></span>  
  
 <span data-ttu-id="4ec6c-192">Les prédicats peuvent stocker des données dans un contexte local qui peut être utilisé pour créer des prédicats qui retournent la valeur true une fois toutes les *n* minutes ou toutes les *n* fois qu’un événement est déclenché.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-192">Predicates can store data in a local context that can be used for creating predicates that return true once every *n* minutes or every *n* times that an event fires.</span></span> <span data-ttu-id="4ec6c-193">Ce stockage de contexte local permet également de mettre à jour dynamiquement le prédicat, en supprimant le déclenchement futur des événements si les événements contiennent des données semblables.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-193">This local context storage can also be used to dynamically update the predicate, thereby suppressing future event firing if the events contain similar data.</span></span>  
  
 <span data-ttu-id="4ec6c-194">Les prédicats ont la capacité de récupérer les informations de contexte, telles que l'ID de thread, ainsi que des données spécifiques à l'événement.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-194">Predicates have the ability to retrieve context information, such as the thread ID, as well as event specific data.</span></span> <span data-ttu-id="4ec6c-195">Les prédicats sont évalués en tant qu'expressions booléennes complètes et prennent en charge le court-circuit au premier point où il apparaît que l'expression entière est fausse.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-195">Predicates are evaluated as full Boolean expressions, and support short circuiting at the first point where the entire expression is found to be false.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ec6c-196">Les prédicats avec effets secondaires ne peuvent pas être évalués en cas d'échec d'un contrôle de prédicat antérieur.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-196">Predicates with side effects may not be evaluated if an earlier predicate check fails.</span></span>  
  
### <a name="types"></a><span data-ttu-id="4ec6c-197">Types</span><span class="sxs-lookup"><span data-stu-id="4ec6c-197">Types</span></span>  
 <span data-ttu-id="4ec6c-198">Comme les données sont une collection d'octets enchaînés, la longueur et les caractéristiques de la collection d'octets sont requises pour interpréter les données.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-198">Because data is a collection of bytes strung together, the length and characteristics of the byte collection are required in order to interpret the data.</span></span> <span data-ttu-id="4ec6c-199">Ces informations sont encapsulées dans l'objet Type.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-199">This information is encapsulated in the Type object.</span></span> <span data-ttu-id="4ec6c-200">Les types suivants sont fournis pour les objets de package :</span><span class="sxs-lookup"><span data-stu-id="4ec6c-200">The following types are provided for package objects:</span></span>  
  
-   <span data-ttu-id="4ec6c-201">event</span><span class="sxs-lookup"><span data-stu-id="4ec6c-201">event</span></span>  
  
-   <span data-ttu-id="4ec6c-202">action</span><span class="sxs-lookup"><span data-stu-id="4ec6c-202">action</span></span>  
  
-   <span data-ttu-id="4ec6c-203">target</span><span class="sxs-lookup"><span data-stu-id="4ec6c-203">target</span></span>  
  
-   <span data-ttu-id="4ec6c-204">pred_source</span><span class="sxs-lookup"><span data-stu-id="4ec6c-204">pred_source</span></span>  
  
-   <span data-ttu-id="4ec6c-205">pred_compare</span><span class="sxs-lookup"><span data-stu-id="4ec6c-205">pred_compare</span></span>  
  
-   <span data-ttu-id="4ec6c-206">type</span><span class="sxs-lookup"><span data-stu-id="4ec6c-206">type</span></span>  
  
 <span data-ttu-id="4ec6c-207">Pour plus d’informations, consultez [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4ec6c-207">For more information, see [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span></span>  
  
### <a name="maps"></a><span data-ttu-id="4ec6c-208">Maps</span><span class="sxs-lookup"><span data-stu-id="4ec6c-208">Maps</span></span>  
 <span data-ttu-id="4ec6c-209">Une table de mappage mappe une valeur interne à une chaîne, ce qui permet à un utilisateur de savoir ce que la valeur représente.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-209">A map table maps an internal value to a string, which enables a user to know what the value represents.</span></span> <span data-ttu-id="4ec6c-210">Au lieu d'obtenir simplement une valeur numérique, un utilisateur peut obtenir une description explicite de la valeur interne.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-210">Instead of only being able to obtain a numeric value, a user can get a meaningful description of the internal value.</span></span> <span data-ttu-id="4ec6c-211">La requête ci-dessous indique comment obtenir les valeurs de mappage.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-211">The following query shows how to obtain map values.</span></span>  
  
```  
select map_key, map_value from sys.dm_xe_map_values  
where name = 'lock_mode'  
```  
  
 <span data-ttu-id="4ec6c-212">La requête précédente produit la sortie ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-212">The preceding query produces the following output.</span></span>  
  
 `map_key     map_value`  
  
 `---------------------`  
  
 `0           NL`  
  
 `1           SCH_S`  
  
 `2           SCH_M`  
  
 `3           S`  
  
 `4           U`  
  
 `5           X`  
  
 `6           IS`  
  
 `7           IU`  
  
 `8           IX`  
  
 `9           SIU`  
  
 `10          SIX`  
  
 `11          UIX`  
  
 `12          BU`  
  
 `13          RS_S`  
  
 `14          RS_U`  
  
 `15          RI_NL`  
  
 `16          RI_S`  
  
 `17          RI_U`  
  
 `18          RI_X`  
  
 `19          RX_S`  
  
 `20          RX_U`  
  
 `21          RX_X`  
  
 `21          RX_X`  
  
 <span data-ttu-id="4ec6c-213">En utilisant cette table comme exemple, supposez que vous possédez une colonne nommée mode et que sa valeur est 5.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-213">Using this table as an example, assume that you have a column named mode, and its value is 5.</span></span> <span data-ttu-id="4ec6c-214">Le tableau indique que 5 correspond à X, ce qui signifie que le type de verrou est Exclusif.</span><span class="sxs-lookup"><span data-stu-id="4ec6c-214">The table indicates that 5 maps to X, which means the lock type is Exclusive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec6c-215">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4ec6c-215">See Also</span></span>  
 <span data-ttu-id="4ec6c-216">[SQL Server les sessions événements étendus](sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="4ec6c-216">[SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md) </span></span>  
 <span data-ttu-id="4ec6c-217">[Moteur d’événements étendus SQL Server](sql-server-extended-events-engine.md) </span><span class="sxs-lookup"><span data-stu-id="4ec6c-217">[SQL Server Extended Events Engine](sql-server-extended-events-engine.md) </span></span>  
 [<span data-ttu-id="4ec6c-218">Cibles des Événements étendus SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ec6c-218">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
