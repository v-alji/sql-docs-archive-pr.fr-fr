---
title: Messages personnalisés pour la journalisation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], custom
- writing log entries
- SSIS packages, logs
- custom messages for logging [Integration Services]
ms.assetid: 3c74bba9-02b7-4bf5-bad5-19278b680730
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b9f450c74ef6d46876adfde45729c71b3262449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605660"
---
# <a name="custom-messages-for-logging"></a><span data-ttu-id="e0c85-102">Messages personnalisés pour la journalisation</span><span class="sxs-lookup"><span data-stu-id="e0c85-102">Custom Messages for Logging</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="e0c85-103">fournit un ensemble complet d'événements personnalisés permettant d'écrire des entrées de journal pour des packages et bon nombre de tâches.</span><span class="sxs-lookup"><span data-stu-id="e0c85-103">provides a rich set of custom events for writing log entries for packages and many tasks.</span></span> <span data-ttu-id="e0c85-104">Vous pouvez utiliser ces entrées pour enregistrer des informations détaillées sur l'avancement, les résultats et les problèmes d'exécution en enregistrant des événements prédéfinis ou des messages définis par l'utilisateur en vue d'une analyse ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e0c85-104">You can use these entries to save detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="e0c85-105">Vous pouvez ainsi enregistrer l'heure de début et de fin d'une insertion en bloc pour identifier des problèmes de performances lors de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="e0c85-105">For example, you can record when a bulk insert begins and ends to identify performance issues when the package runs.</span></span>  
  
 <span data-ttu-id="e0c85-106">Les entrées de journal personnalisées constituent un ensemble qui se distingue de l'ensemble des événements de journalisation standard, disponibles pour les packages et tous les conteneurs et tâches.</span><span class="sxs-lookup"><span data-stu-id="e0c85-106">The custom log entries are a different set of entries than the set of standard logging events that are available for packages and all containers and tasks.</span></span> <span data-ttu-id="e0c85-107">Ces entrées sont conçues pour capturer des informations utiles sur une tâche spécifique d'un package.</span><span class="sxs-lookup"><span data-stu-id="e0c85-107">The custom log entries are tailored to capture useful information about a specific task in a package.</span></span> <span data-ttu-id="e0c85-108">Par exemple, l'une des entrées de journal personnalisées pour la tâche d'exécution de requêtes SQL consigne l'instruction SQL que la tâche exécute dans le journal.</span><span class="sxs-lookup"><span data-stu-id="e0c85-108">For example, one of the custom log entries for the Execute SQL task records the SQL statement that the task executes in the log.</span></span>  
  
 <span data-ttu-id="e0c85-109">Toutes les entrées de journal contiennent des informations de date et d'heure, y compris les entrées qui sont écrites automatiquement au début et à la fin d'un package.</span><span class="sxs-lookup"><span data-stu-id="e0c85-109">All log entries include date and time information, including the log entries that are automatically written when a package begins and finishes.</span></span> <span data-ttu-id="e0c85-110">La plupart des événements de journal écrivent plusieurs entrées dans le journal.</span><span class="sxs-lookup"><span data-stu-id="e0c85-110">Many of the log events write multiple entries to the log.</span></span> <span data-ttu-id="e0c85-111">C'est généralement le cas lorsque l'événement comprend plusieurs phases.</span><span class="sxs-lookup"><span data-stu-id="e0c85-111">This typically occurs when the event has different phases.</span></span> <span data-ttu-id="e0c85-112">Par exemple, l'événement du journal `ExecuteSQLExecutingQuery` consigne trois entrées : la première après que la tâche acquiert une connexion à la base de données, la seconde après que la tâche commence à préparer l'instruction SQL et la troisième à la fin de l'exécution de l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="e0c85-112">For example, the `ExecuteSQLExecutingQuery` log event writes three entries: one entry after the task acquires a connection to the database, another after the task starts to prepare the SQL statement, and one more after the execution of the SQL statement is completed.</span></span>  
  
 <span data-ttu-id="e0c85-113">Les objets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] suivants possèdent des entrées de journal personnalisées :</span><span class="sxs-lookup"><span data-stu-id="e0c85-113">The following [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects have custom log entries:</span></span>  
  
 [<span data-ttu-id="e0c85-114">Package</span><span class="sxs-lookup"><span data-stu-id="e0c85-114">Package</span></span>](#Package)  
  
 [<span data-ttu-id="e0c85-115">Tâche d’insertion en bloc</span><span class="sxs-lookup"><span data-stu-id="e0c85-115">Bulk Insert Task</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="e0c85-116">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="e0c85-116">Data Flow Task</span></span>](#DataFlow)  
  
 [<span data-ttu-id="e0c85-117">Tâche d'exécution DTS 2000</span><span class="sxs-lookup"><span data-stu-id="e0c85-117">Execute DTS 2000 Task</span></span>](#ExecuteDTS200)  
  
 [<span data-ttu-id="e0c85-118">Tâche d’exécution de processus</span><span class="sxs-lookup"><span data-stu-id="e0c85-118">Execute Process Task</span></span>](#ExecuteProcess)  
  
 [<span data-ttu-id="e0c85-119">Tache d’exécution de requêtes SQL</span><span class="sxs-lookup"><span data-stu-id="e0c85-119">Execute SQL Task</span></span>](#ExecuteSQL)  
  
 [<span data-ttu-id="e0c85-120">Tâches du système de fichiers</span><span class="sxs-lookup"><span data-stu-id="e0c85-120">File System Task</span></span>](#FileSystem)  
  
 [<span data-ttu-id="e0c85-121">Tâche FTP</span><span class="sxs-lookup"><span data-stu-id="e0c85-121">FTP Task</span></span>](#FTP)  
  
 [<span data-ttu-id="e0c85-122">Tâche MSMQ</span><span class="sxs-lookup"><span data-stu-id="e0c85-122">Message Queue Task</span></span>](#MessageQueue)  
  
 [<span data-ttu-id="e0c85-123">Tâche de script</span><span class="sxs-lookup"><span data-stu-id="e0c85-123">Script Task</span></span>](#Script)  
  
 [<span data-ttu-id="e0c85-124">Tache Envoyer un message</span><span class="sxs-lookup"><span data-stu-id="e0c85-124">Send Mail Task</span></span>](#SendMail)  
  
 [<span data-ttu-id="e0c85-125">Tâche de transfert de bases de données</span><span class="sxs-lookup"><span data-stu-id="e0c85-125">Transfer Database Task</span></span>](#TransferDatabase)  
  
 [<span data-ttu-id="e0c85-126">Tâche de transfert de messages d’erreur</span><span class="sxs-lookup"><span data-stu-id="e0c85-126">Transfer Error Messages Task</span></span>](#TransferErrorMessages)  
  
 [<span data-ttu-id="e0c85-127">Tâche de transfert de travaux</span><span class="sxs-lookup"><span data-stu-id="e0c85-127">Transfer Jobs Task</span></span>](#TransferJobs)  
  
 [<span data-ttu-id="e0c85-128">Tâche de transfert de connexions</span><span class="sxs-lookup"><span data-stu-id="e0c85-128">Transfer Logins Task</span></span>](#TransferLogins)  
  
 [<span data-ttu-id="e0c85-129">Tâche de transfert de procédures stockées de master</span><span class="sxs-lookup"><span data-stu-id="e0c85-129">Transfer Master Stored Procedures Task</span></span>](#TransferMasterStoredProcedures)  
  
 [<span data-ttu-id="e0c85-130">Tâche de transfert d’objets SQL Server</span><span class="sxs-lookup"><span data-stu-id="e0c85-130">Transfer SQL Server Objects Task</span></span>](#TransferSQLServerObjects)  
  
 [<span data-ttu-id="e0c85-131">Tâche de services Web</span><span class="sxs-lookup"><span data-stu-id="e0c85-131">Web Services Task</span></span>](#WebServices)  
  
 [<span data-ttu-id="e0c85-132">Tâche Lecteur de données WMI</span><span class="sxs-lookup"><span data-stu-id="e0c85-132">WMI Data Reader Task</span></span>](#WMIDataReader)  
  
 [<span data-ttu-id="e0c85-133">Tâche Observateur d’événement WMI</span><span class="sxs-lookup"><span data-stu-id="e0c85-133">WMI Event Watcher Task</span></span>](#WMIEventWatcher)  
  
 [<span data-ttu-id="e0c85-134">Tâche XML</span><span class="sxs-lookup"><span data-stu-id="e0c85-134">XML Task</span></span>](#XML)  
  
## <a name="log-entries"></a><span data-ttu-id="e0c85-135">Entrées du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-135">Log Entries</span></span>  
  
###  <a name="package"></a><a name="Package"></a> <span data-ttu-id="e0c85-136">Package</span><span class="sxs-lookup"><span data-stu-id="e0c85-136">Package</span></span>  
 <span data-ttu-id="e0c85-137">Le tableau suivant répertorie les entrées de journal personnalisées pour les packages.</span><span class="sxs-lookup"><span data-stu-id="e0c85-137">The following table lists the custom log entries for packages.</span></span>  
  
|<span data-ttu-id="e0c85-138">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-138">Log entry</span></span>|<span data-ttu-id="e0c85-139">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-139">Description</span></span>|  
|---------------|-----------------|  
|`PackageStart`|<span data-ttu-id="e0c85-140">Indique que le package a commencé à s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="e0c85-140">Indicates that the package began to run.</span></span><br /><br /> <span data-ttu-id="e0c85-141">Remarque : cette entrée de journal est automatiquement écrite dans le journal.</span><span class="sxs-lookup"><span data-stu-id="e0c85-141">Note: This log entry is automatically written to the log.</span></span> <span data-ttu-id="e0c85-142">Vous ne pouvez pas l'exclure.</span><span class="sxs-lookup"><span data-stu-id="e0c85-142">You cannot exclude it.</span></span>|  
|`PackageEnd`|<span data-ttu-id="e0c85-143">Indique que le package est terminé.</span><span class="sxs-lookup"><span data-stu-id="e0c85-143">Indicates that the package completed.</span></span><br /><br /> <span data-ttu-id="e0c85-144">Remarque : cette entrée de journal est automatiquement écrite dans le journal.</span><span class="sxs-lookup"><span data-stu-id="e0c85-144">Note: This log entry is automatically written to the log.</span></span> <span data-ttu-id="e0c85-145">Vous ne pouvez pas l'exclure.</span><span class="sxs-lookup"><span data-stu-id="e0c85-145">You cannot exclude it.</span></span>|  
|`Diagnostic`|<span data-ttu-id="e0c85-146">Fournit des informations sur la configuration système qui affecte l'exécution du package, notamment le nombre d'exécutables pouvant s'exécuter simultanément.</span><span class="sxs-lookup"><span data-stu-id="e0c85-146">Provides information about the system configuration that affects package execution such as the number executables that can be run concurrently.</span></span><br /><br /> <span data-ttu-id="e0c85-147">L'entrée de journal `Diagnostic` inclut également des entrées avant et après les appels effectués auprès des fournisseurs de données externes.</span><span class="sxs-lookup"><span data-stu-id="e0c85-147">The `Diagnostic` log entry also includes before and after entries for calls to external data providers.</span></span> <span data-ttu-id="e0c85-148">Pour plus d’informations, voir [Outils de dépannage de la connectivité des packages](troubleshooting/troubleshooting-tools-for-package-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="e0c85-148">For more information, see [Troubleshooting Tools Package Connectivity](troubleshooting/troubleshooting-tools-for-package-connectivity.md).</span></span>|  
  
###  <a name="bulk-insert-task"></a><a name="BulkInsert"></a> <span data-ttu-id="e0c85-149">Tâche d'insertion en bloc</span><span class="sxs-lookup"><span data-stu-id="e0c85-149">Bulk Insert Task</span></span>  
 <span data-ttu-id="e0c85-150">Le tableau suivant répertorie les entrées de journal personnalisées de la tâche d'insertion en bloc.</span><span class="sxs-lookup"><span data-stu-id="e0c85-150">The following table lists the custom log entries for the Bulk Insert task.</span></span>  
  
|<span data-ttu-id="e0c85-151">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-151">Log entry</span></span>|<span data-ttu-id="e0c85-152">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-152">Description</span></span>|  
|---------------|-----------------|  
|`DTSBulkInsertTaskBegin`|<span data-ttu-id="e0c85-153">Indique que l'insertion en bloc a commencé.</span><span class="sxs-lookup"><span data-stu-id="e0c85-153">Indicates that the bulk insert began.</span></span>|  
|`DTSBulkInsertTaskEnd`|<span data-ttu-id="e0c85-154">Indique que l'insertion en bloc est terminée.</span><span class="sxs-lookup"><span data-stu-id="e0c85-154">Indicates that the bulk insert finished.</span></span>|  
|`DTSBulkInsertTaskInfos`|<span data-ttu-id="e0c85-155">Fournit des informations détaillées concernant la tâche.</span><span class="sxs-lookup"><span data-stu-id="e0c85-155">Provides descriptive information about the task.</span></span>|  
  
###  <a name="data-flow-task"></a><a name="DataFlow"></a> <span data-ttu-id="e0c85-156">Data Flow Task</span><span class="sxs-lookup"><span data-stu-id="e0c85-156">Data Flow Task</span></span>  
 <span data-ttu-id="e0c85-157">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="e0c85-157">The following table lists the custom log entries for the Data Flow task.</span></span>  
  
|<span data-ttu-id="e0c85-158">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-158">Log entry</span></span>|<span data-ttu-id="e0c85-159">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-159">Description</span></span>|  
|---------------|-----------------|  
|`BufferSizeTuning`|<span data-ttu-id="e0c85-160">Indique que la tâche de flux de données a modifié la taille du tampon.</span><span class="sxs-lookup"><span data-stu-id="e0c85-160">Indicates that the Data Flow task changed the size of the buffer.</span></span> <span data-ttu-id="e0c85-161">L'entrée de journal décrit les raisons de cette modification de taille et indique la nouvelle taille temporaire du tampon.</span><span class="sxs-lookup"><span data-stu-id="e0c85-161">The log entry describes the reasons for the size change and lists the temporary new buffer size.</span></span>|  
|`OnPipelinePostEndOfRowset`|<span data-ttu-id="e0c85-162">Indique qu'un composant a reçu son signal de fin d'ensemble de lignes, défini par le dernier appel de la méthode `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="e0c85-162">Denotes that a component has been given its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="e0c85-163">Une entrée est écrite pour chaque composant du flux de données qui traite l'entrée.</span><span class="sxs-lookup"><span data-stu-id="e0c85-163">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="e0c85-164">L'entrée inclut le nom du composant.</span><span class="sxs-lookup"><span data-stu-id="e0c85-164">The entry includes the name of the component.</span></span>|  
|`OnPipelinePostPrimeOutput`|<span data-ttu-id="e0c85-165">Indique que le composant a terminé son dernier appel de la méthode `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="e0c85-165">Indicates that the component has completed its last call to the `PrimeOutput` method.</span></span> <span data-ttu-id="e0c85-166">Selon le flux de données, plusieurs entrées de journal peuvent être écrites.</span><span class="sxs-lookup"><span data-stu-id="e0c85-166">Depending on the data flow, multiple log entries may be written.</span></span> <span data-ttu-id="e0c85-167">Si le composant est une source, cela signifie que le composant a terminé le traitement des lignes.</span><span class="sxs-lookup"><span data-stu-id="e0c85-167">If the component is a source, this means that the component has finished processing rows.</span></span>|  
|`OnPipelinePreEndOfRowset`|<span data-ttu-id="e0c85-168">Indique qu'un composant est sur le point de recevoir son signal de fin d'ensemble de lignes, défini par le dernier appel de la méthode `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="e0c85-168">Indicates that a component is about to receive its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="e0c85-169">Une entrée est écrite pour chaque composant du flux de données qui traite l'entrée.</span><span class="sxs-lookup"><span data-stu-id="e0c85-169">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="e0c85-170">L'entrée inclut le nom du composant.</span><span class="sxs-lookup"><span data-stu-id="e0c85-170">The entry includes the name of the component.</span></span>|  
|`OnPipelinePrePrimeOutput`|<span data-ttu-id="e0c85-171">Indique que le composant est sur le point de recevoir son appel de la méthode `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="e0c85-171">Indicates that the component is about to receive its call from the `PrimeOutput` method.</span></span> <span data-ttu-id="e0c85-172">Selon le flux de données, plusieurs entrées de journal peuvent être écrites.</span><span class="sxs-lookup"><span data-stu-id="e0c85-172">Depending on the data flow, multiple log entries may be written.</span></span>|  
|`OnPipelineRowsSent`|<span data-ttu-id="e0c85-173">Indique le nombre de lignes fournies à une entrée de composant par un appel de la méthode `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="e0c85-173">Reports the number of rows provided to a component input by a call to the `ProcessInput` method.</span></span> <span data-ttu-id="e0c85-174">L'entrée du journal inclut le nom du composant.</span><span class="sxs-lookup"><span data-stu-id="e0c85-174">The log entry includes the component name.</span></span>|  
|`PipelineBufferLeak`|<span data-ttu-id="e0c85-175">Donne des informations sur tout composant qui maintient l'activité des tampons après la fermeture du gestionnaire de tampons.</span><span class="sxs-lookup"><span data-stu-id="e0c85-175">Provides information about any component that kept buffers alive after the buffer manager goes away.</span></span> <span data-ttu-id="e0c85-176">Cela signifie que des ressources des tampons n'ont pas été libérées et qu'elles peuvent provoquer des fuites de mémoire.</span><span class="sxs-lookup"><span data-stu-id="e0c85-176">This means that buffers resources were not released and may cause memory leaks.</span></span> <span data-ttu-id="e0c85-177">L'entrée du journal fournit le nom du composant et l'ID du tampon.</span><span class="sxs-lookup"><span data-stu-id="e0c85-177">The log entry provides the name of the component and the ID of the buffer.</span></span>|  
|`PipelineExecutionPlan`|<span data-ttu-id="e0c85-178">Indique le plan d'exécution du flux de données.</span><span class="sxs-lookup"><span data-stu-id="e0c85-178">Reports the execution plan of the data flow.</span></span> <span data-ttu-id="e0c85-179">L'entrée du journal donne des informations sur la façon dont les tampons sont envoyés aux composants.</span><span class="sxs-lookup"><span data-stu-id="e0c85-179">It provides information about how buffers will be sent to components.</span></span> <span data-ttu-id="e0c85-180">Ces informations, conjuguées à l'entrée PipelineExecutionTrees, décrivent ce qui se passe dans la tâche.</span><span class="sxs-lookup"><span data-stu-id="e0c85-180">This information, in combination with the PipelineExecutionTrees entry, describes what is occurring in the task.</span></span>|  
|`PipelineExecutionTrees`|<span data-ttu-id="e0c85-181">Indique les arborescences d'exécution de la disposition du flux de données.</span><span class="sxs-lookup"><span data-stu-id="e0c85-181">Reports the execution trees of the layout in the data flow.</span></span> <span data-ttu-id="e0c85-182">Le planificateur du moteur du flux de données utilise les arborescences pour construire le plan d’exécution du flux de données.</span><span class="sxs-lookup"><span data-stu-id="e0c85-182">The scheduler of the data flow engine use the trees to build the execution plan of the data flow.</span></span>|  
|`PipelineInitialization`|<span data-ttu-id="e0c85-183">Donne des informations d'initialisation relatives à la tâche.</span><span class="sxs-lookup"><span data-stu-id="e0c85-183">Provides initialization information about the task.</span></span> <span data-ttu-id="e0c85-184">Ces informations incluent les répertoires à utiliser pour le stockage temporaire des données blob, la taille par défaut de la mémoire tampon, ainsi que le nombre de lignes contenues dans une mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="e0c85-184">This information includes the directories to use for temporary storage of BLOB data, the default buffer size, and the number of rows in a buffer.</span></span> <span data-ttu-id="e0c85-185">Selon la configuration de la tâche de flux de données, plusieurs entrées de journal peuvent être écrites.</span><span class="sxs-lookup"><span data-stu-id="e0c85-185">Depending on the configuration of the Data Flow task, multiple log entries may be written.</span></span>|  
  
###  <a name="execute-dts-2000-task"></a><a name="ExecuteDTS200"></a> <span data-ttu-id="e0c85-186">Tâche d'exécution DTS 2000</span><span class="sxs-lookup"><span data-stu-id="e0c85-186">Execute DTS 2000 Task</span></span>  
 <span data-ttu-id="e0c85-187">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche d'exécution DTS 2000.</span><span class="sxs-lookup"><span data-stu-id="e0c85-187">The following table lists the custom log entries for the Execute DTS 2000 task.</span></span>  
  
|<span data-ttu-id="e0c85-188">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-188">Log entry</span></span>|<span data-ttu-id="e0c85-189">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-189">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteDTS80PackageTaskBegin`|<span data-ttu-id="e0c85-190">Indique que la tâche a commencé l'exécution d'un package DTS 2000.</span><span class="sxs-lookup"><span data-stu-id="e0c85-190">Indicates that the task began to run a DTS 2000 package.</span></span>|  
|`ExecuteDTS80PackageTaskEnd`|<span data-ttu-id="e0c85-191">Indique que la tâche est terminée.</span><span class="sxs-lookup"><span data-stu-id="e0c85-191">Indicates that the task finished.</span></span><br /><br /> <span data-ttu-id="e0c85-192">Remarque : il est possible que le package DTS 2000 continue à s’exécuter à la fin de la tâche.</span><span class="sxs-lookup"><span data-stu-id="e0c85-192">Note: The DTS 2000 package may continue to run after the task ends.</span></span>|  
|`ExecuteDTS80PackageTaskTaskInfo`|<span data-ttu-id="e0c85-193">Fournit des informations détaillées concernant la tâche.</span><span class="sxs-lookup"><span data-stu-id="e0c85-193">Provides descriptive information about the task.</span></span>|  
|`ExecuteDTS80PackageTaskTaskResult`|<span data-ttu-id="e0c85-194">Indique le résultat d'exécution du package DTS 2000 que la tâche a exécuté.</span><span class="sxs-lookup"><span data-stu-id="e0c85-194">Reports the execution result of the DTS 2000 package that the task ran.</span></span>|  
  
###  <a name="execute-process-task"></a><a name="ExecuteProcess"></a> <span data-ttu-id="e0c85-195">Tâche d'exécution de processus</span><span class="sxs-lookup"><span data-stu-id="e0c85-195">Execute Process Task</span></span>  
 <span data-ttu-id="e0c85-196">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche d'exécution de processus.</span><span class="sxs-lookup"><span data-stu-id="e0c85-196">The following table lists the custom log entries for the Execute Process task.</span></span>  
  
|<span data-ttu-id="e0c85-197">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-197">Log entry</span></span>|<span data-ttu-id="e0c85-198">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-198">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteProcessExecutingProcess`|<span data-ttu-id="e0c85-199">Donne des informations sur le processus d'exécution de l'exécutable dont est chargé la tâche.</span><span class="sxs-lookup"><span data-stu-id="e0c85-199">Provides information about the process of running the executable that the task is configured to run.</span></span><br /><br /> <span data-ttu-id="e0c85-200">Deux entrées de journal sont écrites.</span><span class="sxs-lookup"><span data-stu-id="e0c85-200">Two log entries are written.</span></span> <span data-ttu-id="e0c85-201">La première contient des informations sur le nom et l'emplacement de l'exécutable que la tâche exécute, tandis que la seconde enregistre la sortie de l'exécutable.</span><span class="sxs-lookup"><span data-stu-id="e0c85-201">One contains information about the name and location of the executable that the task runs, and the other records the exit from the executable.</span></span>|  
|`ExecuteProcessVariableRouting`|<span data-ttu-id="e0c85-202">Fournit des informations sur les variables qui doivent être acheminées vers l'entrée et les sorties de l'exécutable.</span><span class="sxs-lookup"><span data-stu-id="e0c85-202">Provides information about which variables are routed to the input and outputs of the executable.</span></span> <span data-ttu-id="e0c85-203">Les entrées du journal sont écrites pour stdin (l'entrée), stdout (la sortie) et stderr (la sortie des erreurs).</span><span class="sxs-lookup"><span data-stu-id="e0c85-203">Log entries are written for stdin (the input), stdout (the output), and stderr (the error output).</span></span>|  
  
###  <a name="execute-sql-task"></a><a name="ExecuteSQL"></a> <span data-ttu-id="e0c85-204">Tache d'exécution de requêtes SQL</span><span class="sxs-lookup"><span data-stu-id="e0c85-204">Execute SQL Task</span></span>  
 <span data-ttu-id="e0c85-205">Le tableau suivant décrit les entrées de journal personnalisées pour la tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="e0c85-205">The following table describes the custom log entry for the Execute SQL task.</span></span>  
  
|<span data-ttu-id="e0c85-206">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-206">Log entry</span></span>|<span data-ttu-id="e0c85-207">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-207">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteSQLExecutingQuery`|<span data-ttu-id="e0c85-208">Fournit des informations sur les phases d'exécution de l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="e0c85-208">Provides information about the execution phases of the SQL statement.</span></span> <span data-ttu-id="e0c85-209">Des entrées de journal sont écrites lorsque la tâche acquiert la connexion à la base de données, lorsqu'elle commence à préparer l'instruction SQL et à la fin de l'exécution de l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="e0c85-209">Log entries are written when the task acquires connection to the database, when the task starts to prepare the SQL statement, and after the execution of the SQL statement is completed.</span></span> <span data-ttu-id="e0c85-210">L'entrée de journal concernant la phase de préparation inclut l'instruction SQL que la tâche utilise.</span><span class="sxs-lookup"><span data-stu-id="e0c85-210">The log entry for the prepare phase includes the SQL statement that the task uses.</span></span>|  
  
###  <a name="file-system-task"></a><a name="FileSystem"></a> <span data-ttu-id="e0c85-211">Tâches du système de fichiers</span><span class="sxs-lookup"><span data-stu-id="e0c85-211">File System Task</span></span>  
 <span data-ttu-id="e0c85-212">Le tableau suivant décrit l'entrée de journal personnalisée pour la tâche de système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e0c85-212">The following table describes the custom log entry for the File System task.</span></span>  
  
|<span data-ttu-id="e0c85-213">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-213">Log entry</span></span>|<span data-ttu-id="e0c85-214">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-214">Description</span></span>|  
|---------------|-----------------|  
|`FileSystemOperation`|<span data-ttu-id="e0c85-215">Indique l'opération que la tâche effectue.</span><span class="sxs-lookup"><span data-stu-id="e0c85-215">Reports the operation that the task performs.</span></span> <span data-ttu-id="e0c85-216">L'entrée de journal est écrite au démarrage de l'opération du système de fichiers et inclut des informations sur la source et la destination.</span><span class="sxs-lookup"><span data-stu-id="e0c85-216">The log entry is written when the file system operation starts and includes information about the source and destination.</span></span>|  
  
###  <a name="ftp-task"></a><a name="FTP"></a> <span data-ttu-id="e0c85-217">Tâche FTP</span><span class="sxs-lookup"><span data-stu-id="e0c85-217">FTP Task</span></span>  
 <span data-ttu-id="e0c85-218">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche FTP.</span><span class="sxs-lookup"><span data-stu-id="e0c85-218">The following table lists the custom log entries for the FTP task.</span></span>  
  
|<span data-ttu-id="e0c85-219">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-219">Log entry</span></span>|<span data-ttu-id="e0c85-220">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-220">Description</span></span>|  
|---------------|-----------------|  
|`FTPConnectingToServer`|<span data-ttu-id="e0c85-221">Indique que la tâche a lancé une connexion au serveur FTP.</span><span class="sxs-lookup"><span data-stu-id="e0c85-221">Indicates that the task initiated a connection to the FTP server.</span></span>|  
|`FTPOperation`|<span data-ttu-id="e0c85-222">Indique le démarrage et le type d'une opération FTP effectuée par la tâche.</span><span class="sxs-lookup"><span data-stu-id="e0c85-222">Reports the beginning of and the type of FTP operation that the task performs.</span></span>|  
  
###  <a name="message-queue-task"></a><a name="MessageQueue"></a> <span data-ttu-id="e0c85-223">Tâche MSMQ</span><span class="sxs-lookup"><span data-stu-id="e0c85-223">Message Queue Task</span></span>  
 <span data-ttu-id="e0c85-224">Le tableau suivant répertorie les entrées de journal personnalisées de la tâche MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e0c85-224">The following table lists the custom log entries for the Message Queue task.</span></span>  
  
|<span data-ttu-id="e0c85-225">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-225">Log entry</span></span>|<span data-ttu-id="e0c85-226">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-226">Description</span></span>|  
|---------------|-----------------|  
|`MSMQAfterOpen`|<span data-ttu-id="e0c85-227">Indique que la tâche a fini d'ouvrir la file d'attente des messages.</span><span class="sxs-lookup"><span data-stu-id="e0c85-227">Indicates that the task finished opening the message queue.</span></span>|  
|`MSMQBeforeOpen`|<span data-ttu-id="e0c85-228">Indique que la tâche a commencé l'ouverture de la file d'attente des messages.</span><span class="sxs-lookup"><span data-stu-id="e0c85-228">Indicates that the task began to open the message queue.</span></span>|  
|`MSMQBeginReceive`|<span data-ttu-id="e0c85-229">Indique que la tâche a commencé la réception d'un message.</span><span class="sxs-lookup"><span data-stu-id="e0c85-229">Indicates that the task began to receive a message.</span></span>|  
|`MSMQBeginSend`|<span data-ttu-id="e0c85-230">Indique que la tâche a commencé l'envoi d'un message.</span><span class="sxs-lookup"><span data-stu-id="e0c85-230">Indicates that the task began to send a message.</span></span>|  
|`MSMQEndReceive`|<span data-ttu-id="e0c85-231">Indique que la tâche a terminé la réception d'un message.</span><span class="sxs-lookup"><span data-stu-id="e0c85-231">Indicates that the task finished receiving a message.</span></span>|  
|`MSMQEndSend`|<span data-ttu-id="e0c85-232">Indique que la tâche a terminé l’envoi d’un message.</span><span class="sxs-lookup"><span data-stu-id="e0c85-232">Indicates that the task finished sending a message</span></span>|  
|`MSMQTaskInfo`|<span data-ttu-id="e0c85-233">Fournit des informations détaillées concernant la tâche.</span><span class="sxs-lookup"><span data-stu-id="e0c85-233">Provides descriptive information about the task.</span></span>|  
|`MSMQTaskTimeOut`|<span data-ttu-id="e0c85-234">Indique que le délai de la tâche a expiré.</span><span class="sxs-lookup"><span data-stu-id="e0c85-234">Indicates that the task timed out.</span></span>|  
  
###  <a name="script-task"></a><a name="Script"></a> <span data-ttu-id="e0c85-235">Tâche de script</span><span class="sxs-lookup"><span data-stu-id="e0c85-235">Script Task</span></span>  
 <span data-ttu-id="e0c85-236">Le tableau suivant décrit l'entrée de journal personnalisée pour la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="e0c85-236">The following table describes the custom log entry for the Script task.</span></span>  
  
|<span data-ttu-id="e0c85-237">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-237">Log entry</span></span>|<span data-ttu-id="e0c85-238">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-238">Description</span></span>|  
|---------------|-----------------|  
|`ScriptTaskLogEntry`|<span data-ttu-id="e0c85-239">Indique les résultats de l'implémentation de la journalisation dans le script.</span><span class="sxs-lookup"><span data-stu-id="e0c85-239">Reports the results of implementing logging in the script.</span></span> <span data-ttu-id="e0c85-240">Une entrée de journal est écrite pour chaque appel de la méthode `Log` de l'objet `Dts`.</span><span class="sxs-lookup"><span data-stu-id="e0c85-240">A log entry is written for each call to the `Log` method of the `Dts` object.</span></span> <span data-ttu-id="e0c85-241">L'entrée est écrite à l'exécution du code.</span><span class="sxs-lookup"><span data-stu-id="e0c85-241">The entry is written when the code is run.</span></span> <span data-ttu-id="e0c85-242">Pour plus d’informations, consultez [Journalisation dans la tâche de script](extending-packages-scripting/task/logging-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="e0c85-242">For more information, see [Logging in the Script Task](extending-packages-scripting/task/logging-in-the-script-task.md).</span></span>|  
  
###  <a name="send-mail-task"></a><a name="SendMail"></a> <span data-ttu-id="e0c85-243">Tâche Envoyer un message</span><span class="sxs-lookup"><span data-stu-id="e0c85-243">Send Mail Task</span></span>  
 <span data-ttu-id="e0c85-244">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche Envoyer un message.</span><span class="sxs-lookup"><span data-stu-id="e0c85-244">The following table lists the custom log entries for the Send Mail task.</span></span>  
  
|<span data-ttu-id="e0c85-245">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-245">Log entry</span></span>|<span data-ttu-id="e0c85-246">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-246">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="e0c85-247">Indique que la tâche a commencé l'envoi d'un message électronique.</span><span class="sxs-lookup"><span data-stu-id="e0c85-247">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="e0c85-248">Indique que la tâche a terminé l'envoi d'un message électronique.</span><span class="sxs-lookup"><span data-stu-id="e0c85-248">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="e0c85-249">Fournit des informations détaillées concernant la tâche.</span><span class="sxs-lookup"><span data-stu-id="e0c85-249">Provides descriptive information about the task.</span></span>|  
  
###  <a name="transfer-database-task"></a><a name="TransferDatabase"></a> <span data-ttu-id="e0c85-250">Tâche de transfert de bases de données</span><span class="sxs-lookup"><span data-stu-id="e0c85-250">Transfer Database Task</span></span>  
 <span data-ttu-id="e0c85-251">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche de transfert de bases de données.</span><span class="sxs-lookup"><span data-stu-id="e0c85-251">The following table lists the custom log entries for the Transfer Database task.</span></span>  
  
|<span data-ttu-id="e0c85-252">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-252">Log entry</span></span>|<span data-ttu-id="e0c85-253">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-253">Description</span></span>|  
|---------------|-----------------|  
|`SourceDB`|<span data-ttu-id="e0c85-254">Spécifie la base de données que la tâche a copiée.</span><span class="sxs-lookup"><span data-stu-id="e0c85-254">Specifies the database that the task copied.</span></span>|  
|`SourceSQLServer`|<span data-ttu-id="e0c85-255">Spécifie l'ordinateur à partir duquel la base de données a été copiée.</span><span class="sxs-lookup"><span data-stu-id="e0c85-255">Specifies the computer from which the database was copied.</span></span>|  
  
###  <a name="transfer-error-messages-task"></a><a name="TransferErrorMessages"></a> <span data-ttu-id="e0c85-256">Tâche de transfert de messages d'erreur</span><span class="sxs-lookup"><span data-stu-id="e0c85-256">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="e0c85-257">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche de transfert de messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e0c85-257">The following table lists the custom log entries for the Transfer Error Messages task.</span></span>  
  
|<span data-ttu-id="e0c85-258">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-258">Log entry</span></span>|<span data-ttu-id="e0c85-259">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-259">Description</span></span>|  
|---------------|-----------------|  
|`TransferErrorMessagesTaskFinishedTransferringObjects`|<span data-ttu-id="e0c85-260">Indique que la tâche a terminé le transfert des messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e0c85-260">Indicates that the task finished transferring error messages.</span></span>|  
|`TransferErrorMessagesTaskStartTransferringObjects`|<span data-ttu-id="e0c85-261">Indique que la tâche a commencé le transfert des messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e0c85-261">Indicates that the task started to transfer error messages.</span></span>|  
  
###  <a name="transfer-jobs-task"></a><a name="TransferJobs"></a> <span data-ttu-id="e0c85-262">Tâche de transfert de travaux</span><span class="sxs-lookup"><span data-stu-id="e0c85-262">Transfer Jobs Task</span></span>  
 <span data-ttu-id="e0c85-263">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche de transfert de travaux.</span><span class="sxs-lookup"><span data-stu-id="e0c85-263">The following table lists the custom log entries for the Transfer Jobs task.</span></span>  
  
|<span data-ttu-id="e0c85-264">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-264">Log entry</span></span>|<span data-ttu-id="e0c85-265">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-265">Description</span></span>|  
|---------------|-----------------|  
|`TransferJobsTaskFinishedTransferringObjects`|<span data-ttu-id="e0c85-266">Indique que la tâche a terminé le transfert des travaux de l’Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0c85-266">Indicates that the task finished transferring [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.</span></span>|  
|`TransferJobsTaskStartTransferringObjects`|<span data-ttu-id="e0c85-267">Indique que la tâche a commencé le transfert des travaux de l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0c85-267">Indicates that the task started to transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.</span></span>|  
  
###  <a name="transfer-logins-task"></a><a name="TransferLogins"></a> <span data-ttu-id="e0c85-268">Tâche de transfert de connexions</span><span class="sxs-lookup"><span data-stu-id="e0c85-268">Transfer Logins Task</span></span>  
 <span data-ttu-id="e0c85-269">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche de transfert de connexions.</span><span class="sxs-lookup"><span data-stu-id="e0c85-269">The following table lists the custom log entries for the Transfer Logins task.</span></span>  
  
|<span data-ttu-id="e0c85-270">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-270">Log entry</span></span>|<span data-ttu-id="e0c85-271">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-271">Description</span></span>|  
|---------------|-----------------|  
|`TransferLoginsTaskFinishedTransferringObjects`|<span data-ttu-id="e0c85-272">Indique que la tâche a terminé le transfert des connexions.</span><span class="sxs-lookup"><span data-stu-id="e0c85-272">Indicates that the task finished transferring logins.</span></span>|  
|`TransferLoginsTaskStartTransferringObjects`|<span data-ttu-id="e0c85-273">Indique que la tâche a commencé le transfert des connexions.</span><span class="sxs-lookup"><span data-stu-id="e0c85-273">Indicates that the task started to transfer logins.</span></span>|  
  
###  <a name="transfer-master-stored-procedures-task"></a><a name="TransferMasterStoredProcedures"></a> <span data-ttu-id="e0c85-274">Tâche de transfert de procédures stockées de master</span><span class="sxs-lookup"><span data-stu-id="e0c85-274">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="e0c85-275">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche de transfert de procédures stockées de master.</span><span class="sxs-lookup"><span data-stu-id="e0c85-275">The following table lists the custom log entries for the Transfer Master Stored Procedures task.</span></span>  
  
|<span data-ttu-id="e0c85-276">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-276">Log entry</span></span>|<span data-ttu-id="e0c85-277">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-277">Description</span></span>|  
|---------------|-----------------|  
|`TransferStoredProceduresTaskFinishedTransferringObjects`|<span data-ttu-id="e0c85-278">Indique que la tâche a terminé le transfert des procédures stockées définies par l’utilisateur qui existent dans la base de données **master** .</span><span class="sxs-lookup"><span data-stu-id="e0c85-278">Indicates that the task finished transferring user-defined stored procedures that are stored in the **master** database.</span></span>|  
|`TransferStoredProceduresTaskStartTransferringObjects`|<span data-ttu-id="e0c85-279">Indique que la tâche a commencé le transfert des procédures stockées définies par l’utilisateur qui existent dans la base de données **master** .</span><span class="sxs-lookup"><span data-stu-id="e0c85-279">Indicates that the task started to transfer user-defined stored procedures that are stored in the **master** database.</span></span>|  
  
###  <a name="transfer-sql-server-objects-task"></a><a name="TransferSQLServerObjects"></a> <span data-ttu-id="e0c85-280">Tâche de transfert d'objets SQL Server</span><span class="sxs-lookup"><span data-stu-id="e0c85-280">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="e0c85-281">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche de transfert d'objets [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0c85-281">The following table lists the custom log entries for the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
|<span data-ttu-id="e0c85-282">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-282">Log entry</span></span>|<span data-ttu-id="e0c85-283">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-283">Description</span></span>|  
|---------------|-----------------|  
|`TransferSqlServerObjectsTaskFinishedTransferringObjects`|<span data-ttu-id="e0c85-284">Indique que la tâche a terminé le transfert des objets de base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0c85-284">Indicates that the task finished transferring [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database objects.</span></span>|  
|`TransferSqlServerObjectsTaskStartTransferringObjects`|<span data-ttu-id="e0c85-285">Indique que la tâche a commencé le transfert des objets de base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0c85-285">Indicates that the task started to transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database objects.</span></span>|  
  
###  <a name="web-services-task"></a><a name="WebServices"></a> <span data-ttu-id="e0c85-286">Tâche de services Web</span><span class="sxs-lookup"><span data-stu-id="e0c85-286">Web Services Task</span></span>  
 <span data-ttu-id="e0c85-287">Le tableau suivant répertorie les entrées de journal personnalisées pour la tâche de services Web.</span><span class="sxs-lookup"><span data-stu-id="e0c85-287">The following table lists the custom log entries that you can enable for the Web Services task.</span></span>  
  
|<span data-ttu-id="e0c85-288">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-288">Log entry</span></span>|<span data-ttu-id="e0c85-289">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-289">Description</span></span>|  
|---------------|-----------------|  
|`WSTaskBegin`|<span data-ttu-id="e0c85-290">La tâche a commencé à accéder à un service Web.</span><span class="sxs-lookup"><span data-stu-id="e0c85-290">The task began to access a Web service.</span></span>|  
|`WSTaskEnd`|<span data-ttu-id="e0c85-291">La tâche a terminé une méthode de service Web.</span><span class="sxs-lookup"><span data-stu-id="e0c85-291">The task completed a Web service method.</span></span>|  
|`WSTaskInfo`|<span data-ttu-id="e0c85-292">Donne des informations détaillées relatives à la tâche.</span><span class="sxs-lookup"><span data-stu-id="e0c85-292">Descriptive information about the task.</span></span>|  
  
###  <a name="wmi-data-reader-task"></a><a name="WMIDataReader"></a> <span data-ttu-id="e0c85-293">Tâche Lecteur de données WMI</span><span class="sxs-lookup"><span data-stu-id="e0c85-293">WMI Data Reader Task</span></span>  
 <span data-ttu-id="e0c85-294">Le tableau suivant répertorie les entrées de journal personnalisées de la tâche Lecteur de données WMI.</span><span class="sxs-lookup"><span data-stu-id="e0c85-294">The following table lists the custom log entries for the WMI Data Reader task.</span></span>  
  
|<span data-ttu-id="e0c85-295">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-295">Log entry</span></span>|<span data-ttu-id="e0c85-296">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-296">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="e0c85-297">Indique que la tâche a commencé la lecture des données WMI.</span><span class="sxs-lookup"><span data-stu-id="e0c85-297">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="e0c85-298">Indique la requête WQL que la tâche a exécutée.</span><span class="sxs-lookup"><span data-stu-id="e0c85-298">Reports the WQL query that the task ran.</span></span>|  
  
###  <a name="wmi-event-watcher-task"></a><a name="WMIEventWatcher"></a> <span data-ttu-id="e0c85-299">Tâche Observateur d'événement WMI</span><span class="sxs-lookup"><span data-stu-id="e0c85-299">WMI Event Watcher Task</span></span>  
 <span data-ttu-id="e0c85-300">Le tableau suivant répertorie les entrées de journal personnalisées de la tâche Observateur d'événement WMI.</span><span class="sxs-lookup"><span data-stu-id="e0c85-300">The following table lists the custom log entries for the WMI Event Watcher task.</span></span>  
  
|<span data-ttu-id="e0c85-301">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-301">Log entry</span></span>|<span data-ttu-id="e0c85-302">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-302">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="e0c85-303">Indique que l'événement surveillé par la tâche s'est produit.</span><span class="sxs-lookup"><span data-stu-id="e0c85-303">Denotes that the event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="e0c85-304">Indique que le délai de la tâche a expiré.</span><span class="sxs-lookup"><span data-stu-id="e0c85-304">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="e0c85-305">Indique que la tâche a commencé l'exécution de la requête WQL.</span><span class="sxs-lookup"><span data-stu-id="e0c85-305">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="e0c85-306">L'entrée inclut la requête.</span><span class="sxs-lookup"><span data-stu-id="e0c85-306">The entry includes the query.</span></span>|  
  
###  <a name="xml-task"></a><a name="XML"></a> <span data-ttu-id="e0c85-307">Tâche XML</span><span class="sxs-lookup"><span data-stu-id="e0c85-307">XML Task</span></span>  
 <span data-ttu-id="e0c85-308">Le tableau suivant décrit l'entrée de journal personnalisée de la tâche XML.</span><span class="sxs-lookup"><span data-stu-id="e0c85-308">The following table describes the custom log entry for the XML task.</span></span>  
  
|<span data-ttu-id="e0c85-309">Entrée du journal</span><span class="sxs-lookup"><span data-stu-id="e0c85-309">Log entry</span></span>|<span data-ttu-id="e0c85-310">Description</span><span class="sxs-lookup"><span data-stu-id="e0c85-310">Description</span></span>|  
|---------------|-----------------|  
|`XMLOperation`|<span data-ttu-id="e0c85-311">Fournit des informations sur l'opération que la tâche effectue.</span><span class="sxs-lookup"><span data-stu-id="e0c85-311">Provides information about the operation that the task performs</span></span>|   
  
## <a name="see-also"></a><span data-ttu-id="e0c85-312">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0c85-312">See Also</span></span>  
 [<span data-ttu-id="e0c85-313">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e0c85-313">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
