---
title: Analyse des performances et surveillance de l’activité du serveur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- activity monitoring [SQL Server]
- traces [SQL Server], how-to topics
- monitoring server performance [SQL Server], activity monitoring
- stored procedures [SQL Server], traces
- performance [SQL Server], servers
- servers [SQL Server], performance
- SQL Server Profiler, how-to topics
- SQL Server Management Studio [SQL Server], monitoring system
- Profiler [SQL Server Profiler], how-to topics
ms.assetid: f9abe48d-d6e9-4c38-a355-fc5eb5a95a25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0fa7902d68c587a7733f07ceb8daccd3a6a98fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614561"
---
# <a name="server-performance-and-activity-monitoring"></a><span data-ttu-id="4237f-102">Analyse des performances et surveillance de l'activité du serveur</span><span class="sxs-lookup"><span data-stu-id="4237f-102">Server Performance and Activity Monitoring</span></span>
  <span data-ttu-id="4237f-103">Le but de la surveillance des bases de données est d'évaluer le fonctionnement d'un serveur.</span><span class="sxs-lookup"><span data-stu-id="4237f-103">The goal of monitoring databases is to assess how a server is performing.</span></span> <span data-ttu-id="4237f-104">Une surveillance efficace implique la prise d'instantanés périodiques des performances actuelles afin d'isoler les processus à l’origine des problèmes, ainsi que la collecte de données en continu pour suivre de près les tendances des performances.</span><span class="sxs-lookup"><span data-stu-id="4237f-104">Effective monitoring involves taking periodic snapshots of current performance to isolate processes that are causing problems, and gathering data continuously over time to track performance trends.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="4237f-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le système d’exploitation [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows fournissent des utilitaires qui permettent de contrôler les conditions actuelles de la base de données et de suivre le niveau de performance à mesure que les conditions évoluent.</span><span class="sxs-lookup"><span data-stu-id="4237f-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows operating system provide utilities that let you view the current condition of the database and to track performance as conditions change.</span></span>  
  
 <span data-ttu-id="4237f-106">La section suivante contient des rubriques qui décrivent comment utiliser les outils d'analyse des performances et de l'activité de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et de Windows.</span><span class="sxs-lookup"><span data-stu-id="4237f-106">The following section contains topics that describe how to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows performance and activity monitoring tools.</span></span> <span data-ttu-id="4237f-107">Elle contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4237f-107">It contains the following topics:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4237f-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="4237f-108">In This Section</span></span>  
 <span data-ttu-id="4237f-109">**Pour effectuer une analyse des tâches à l'aide des outils Windows**</span><span class="sxs-lookup"><span data-stu-id="4237f-109">**To perform monitoring tasks with Windows tools**</span></span>  
  
-   [<span data-ttu-id="4237f-110">Démarrer le Moniteur système &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-110">Start System Monitor &#40;Windows&#41;</span></span>](start-system-monitor-windows.md)  
  
-   [<span data-ttu-id="4237f-111">Afficher le journal des applications Windows &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-111">View the Windows Application Log &#40;Windows&#41;</span></span>](view-the-windows-application-log-windows-10.md)  
  
 <span data-ttu-id="4237f-112">**Pour créer des alertes de base de données SQL Server à l'aide des outils Windows**</span><span class="sxs-lookup"><span data-stu-id="4237f-112">**To create SQL Server database alerts with Windows tools**</span></span>  
  
-   [<span data-ttu-id="4237f-113">Configurer une alerte de base de données SQL Server &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-113">Set Up a SQL Server Database Alert &#40;Windows&#41;</span></span>](set-up-a-sql-server-database-alert-windows.md)  
  
 <span data-ttu-id="4237f-114">**Pour effectuer une analyse des tâches à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="4237f-114">**To perform monitoring tasks with SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="4237f-115">Afficher le journal des erreurs SQL Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-115">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="4237f-116">Ouvrir le Moniteur d’activité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-116">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)  
  
 <span data-ttu-id="4237f-117">**Pour effectuer une analyse des tâches à l'aide de Trace SQL en utilisant des procédures stockées écrites en Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="4237f-117">**To perform monitoring tasks with SQL Trace by using Transact-SQL stored procedures**</span></span>  
  
-   [<span data-ttu-id="4237f-118">Créer une trace &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-118">Create a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
-   [<span data-ttu-id="4237f-119">Définir un filtre de trace &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-119">Set a Trace Filter &#40;Transact-SQL&#41;</span></span>](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md)  
  
-   [<span data-ttu-id="4237f-120">Modifier une trace existante &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-120">Modify an Existing Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/modify-an-existing-trace-transact-sql.md)  
  
-   [<span data-ttu-id="4237f-121">Afficher une trace enregistrée &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-121">View a Saved Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-a-saved-trace-transact-sql.md)  
  
-   [<span data-ttu-id="4237f-122">Afficher des informations de filtrage &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-122">View Filter Information &#40;Transact-SQL&#41;</span></span>](../sql-trace/view-filter-information-transact-sql.md)  
  
-   [<span data-ttu-id="4237f-123">Supprimer une trace &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-123">Delete a Trace &#40;Transact-SQL&#41;</span></span>](../sql-trace/delete-a-trace-transact-sql.md)  
  
 <span data-ttu-id="4237f-124">**Pour créer et modifier des traces à l'aide du Générateur de profils SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4237f-124">**To create and modify traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="4237f-125">Créer une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-125">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-126">Définir les options globales de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-126">Set Global Trace Options &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-127">Spécifier les événements et les colonnes de données d’un fichier de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-127">Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-128">Créer un script Transact-SQL pour exécuter une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-128">Create a Transact-SQL Script for Running a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-transact-sql-script-for-running-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-129">Enregistrer des résultats d’une trace dans un fichier &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-129">Save Trace Results to a File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-130">Définir la taille maximale d’un fichier de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-130">Set a Maximum File Size for a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-file-size-for-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-131">Enregistrer des résultats d’une trace dans une table &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-131">Save Trace Results to a Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-132">Définir la taille maximale d’une table de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-132">Set a Maximum Table Size for a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-a-maximum-table-size-for-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-133">Filtrer des événements dans une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-133">Filter Events in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-134">Afficher des informations de filtre &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-134">View Filter Information &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-135">Modifier un filtre &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-135">Modify a Filter &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-136">Filtrer des événements en fonction de leur heure de début &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-136">Filter Events Based on the Event Start Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-start-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-137">Filtrer des événements en fonction de leur heure de fin &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-137">Filter Events Based on the Event End Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-138">Filtrer des ID du processus serveur &#40;SPID&#41; dans une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-138">Filter Server Process IDs &#40;SPIDs&#41; in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/filter-server-process-ids-spids-in-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-139">Organiser les colonnes affichées dans une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-139">Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="4237f-140">**Pour démarrer, suspendre et arrêter des traces à l'aide du Générateur de profils SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4237f-140">**To start, pause, and stop traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="4237f-141">Démarrer automatiquement une trace après s’être connecté à un serveur &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-141">Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-142">Suspendre une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-142">Pause a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/pause-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-143">Arrêter une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-143">Stop a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/stop-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-144">Exécuter une trace après qu’elle a été suspendue ou arrêtée &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-144">Run a Trace After It Has Been Paused or Stopped &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/run-a-trace-after-it-has-been-paused-or-stopped-sql-server-profiler.md)  
  
 <span data-ttu-id="4237f-145">**Pour ouvrir des traces et configurer la façon dont elles sont affichées à l'aide du Générateur de profils SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4237f-145">**To open traces and configure how traces are displayed by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="4237f-146">Ouvrir un fichier de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-146">Open a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-147">Ouvrir une table de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-147">Open a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-148">Effacer une fenêtre de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-148">Clear a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/clear-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-149">Fermer une fenêtre de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-149">Close a Trace Window &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/close-a-trace-window-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-150">Définir les valeurs par défaut des définitions de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-150">Set Trace Definition Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-definition-defaults-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-151">Définir les valeurs par défaut de l’affichage des traces &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-151">Set Trace Display Defaults &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="4237f-152">**Pour rejouer des traces à l'aide du Générateur de profils SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4237f-152">**To replay traces by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="4237f-153">Relire un fichier de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-153">Replay a Trace File &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-154">Relire une table de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-154">Replay a Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-155">Relire un seul événement à la fois &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-155">Replay a Single Event at a Time &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-single-event-at-a-time-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-156">Relire jusqu’à un point d’arrêt &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-156">Replay to a Breakpoint &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-breakpoint-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-157">Relire jusqu’à un curseur &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-157">Replay to a Cursor &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-to-a-cursor-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-158">Relire un script Transact-SQL &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-158">Replay a Transact-SQL Script &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/replay-a-transact-sql-script-sql-server-profiler.md)  
  
 <span data-ttu-id="4237f-159">**Pour créer, modifier et utiliser des modèles de traces à l'aide du Générateur de profils SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4237f-159">**To create, modify, and use trace templates by using SQL Server Profiler**</span></span>  
  
-   [<span data-ttu-id="4237f-160">Créer un modèle de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-160">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/create-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-161">Modifier un modèle de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-161">Modify a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-162">Dériver un modèle à partir d’une trace en cours d’exécution &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-162">Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-163">Dériver un modèle à partir d’un fichier de trace ou d’une table de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-163">Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-164">Exporter un modèle de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-164">Export a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/export-a-trace-template-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-165">Importer un modèle de trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-165">Import a Trace Template &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/import-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="4237f-166">**Pour utiliser les traces du Générateur de profils SQL Server afin de collecter et de surveiller les performances du serveur**</span><span class="sxs-lookup"><span data-stu-id="4237f-166">**To use SQL Server Profiler traces to collect and monitor server performance**</span></span>  
  
-   [<span data-ttu-id="4237f-167">Retrouver une valeur ou une colonne de données au cours de l’exécution d’une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-167">Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-168">Enregistrer les événements Deadlock Graph &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-168">Save Deadlock Graphs &#40;SQL Server Profiler&#41;</span></span>](save-deadlock-graphs-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-169">Enregistrer séparément des événements Showplan XML &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-169">Save Showplan XML Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-170">Enregistrer les événements Showplan XML Statistics Profile séparément &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-170">Save Showplan XML Statistics Profile Events Separately &#40;SQL Server Profiler&#41;</span></span>](save-showplan-xml-statistics-profile-events-separately-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-171">Extraire un script d’une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-171">Extract a Script from a Trace &#40;SQL Server Profiler&#41;</span></span>](../../tools/sql-server-profiler/extract-a-script-from-a-trace-sql-server-profiler.md)  
  
-   [<span data-ttu-id="4237f-172">Corréler une trace aux données du journal de performances Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4237f-172">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../../database-engine/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
