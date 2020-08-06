---
title: Afficher et lire les fichiers journaux d’installation de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- displaying log files
- Setup [SQL Server], logs
- installation log files [SQL Server]
- installing SQL Server, logs
- errors [SQL Server], Setup
- logs [SQL Server], Setup
ms.assetid: 9d77af64-9084-4375-908a-d90f99535062
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 70f9bbb9a8ed72503dc6fe90077232748b2c4ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698514"
---
# <a name="view-and-read-sql-server-setup-log-files"></a><span data-ttu-id="6a097-102">Afficher et lire les fichiers journaux d’installation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a097-102">View and Read SQL Server Setup Log Files</span></span>
  <span data-ttu-id="6a097-103">Chaque exécution du programme d’installation crée des fichiers journaux qui sont créés avec un nouveau dossier de journal horodaté à l’adresse% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="6a097-103">Each execution of Setup creates log files are created with a new timestamped log folder at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span> <span data-ttu-id="6a097-104">Le format du nom du dossier de journal horodaté est AAAAMMJJ_hhmmss.</span><span class="sxs-lookup"><span data-stu-id="6a097-104">The time-stamped log folder name format is YYYYMMDD_hhmmss.</span></span> <span data-ttu-id="6a097-105">Lorsque le programme d'installation est exécuté en mode sans assistance, les journaux sont créés à l'emplacement % temp%\sqlsetup\*.log.</span><span class="sxs-lookup"><span data-stu-id="6a097-105">When Setup is run in an unattended mode, the logs are created at % temp%\sqlsetup\*.log.</span></span> <span data-ttu-id="6a097-106">Tous les fichiers du dossier de journal sont archivés dans le fichier Log\*.cab dans leur dossier de journal respectif.</span><span class="sxs-lookup"><span data-stu-id="6a097-106">All files in the logs folder are archived into the Log\*.cab file in their respective log folder.</span></span>  
  
 <span data-ttu-id="6a097-107">Une demande d'Installation typique passe par trois phases d'exécution :</span><span class="sxs-lookup"><span data-stu-id="6a097-107">A typical Setup request goes through three execution phases:</span></span>  
  
1.  <span data-ttu-id="6a097-108">Texte de règles globales</span><span class="sxs-lookup"><span data-stu-id="6a097-108">Global rules text</span></span>  
  
2.  <span data-ttu-id="6a097-109">Mise à jour du composant</span><span class="sxs-lookup"><span data-stu-id="6a097-109">Component update</span></span>  
  
3.  <span data-ttu-id="6a097-110">Action demandée par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="6a097-110">User-requested action</span></span>  
  
 <span data-ttu-id="6a097-111">Dans chaque phase, le programme d'installation génère des journaux résumés et détaillés, ainsi que des journaux supplémentaires si besoin est.</span><span class="sxs-lookup"><span data-stu-id="6a097-111">In each phase, Setup generates detail and summary logs with additional logs created as appropriate.</span></span> <span data-ttu-id="6a097-112">Le programme d'installation est appelé au moins trois fois par action d'installation demandée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6a097-112">Setup is called at least three times per user-requested Setup action.</span></span>  
  
 <span data-ttu-id="6a097-113">Les fichiers de banque de données contiennent un instantané de l'état de tous les objets de configuration qui sont suivis par le processus d'installation et qui sont utiles pour réparer les erreurs de configuration.</span><span class="sxs-lookup"><span data-stu-id="6a097-113">Datastore files contain a snapshot of the state of all configuration objects being tracked by the Setup process, and are useful for troubleshooting configuration errors.</span></span> <span data-ttu-id="6a097-114">Des vidages de fichiers XML sont créés pour les objets de banque de données pour chaque phase d'exécution.</span><span class="sxs-lookup"><span data-stu-id="6a097-114">XML file dumps are created for datastore objects for each execution phase.</span></span> <span data-ttu-id="6a097-115">Ils sont enregistrés dans leur propre sous-dossier de journal sous le dossier de journal horodaté, comme suit :</span><span class="sxs-lookup"><span data-stu-id="6a097-115">They are saved in their own log subfolder under the time-stamped log folder, as follows:</span></span>  
  
-   <span data-ttu-id="6a097-116">Datastore_GlobalRules</span><span class="sxs-lookup"><span data-stu-id="6a097-116">Datastore_GlobalRules</span></span>  
  
-   <span data-ttu-id="6a097-117">Datastore_ComponentUpdated</span><span class="sxs-lookup"><span data-stu-id="6a097-117">Datastore_ComponentUpdated</span></span>  
  
-   <span data-ttu-id="6a097-118">Magasin de données</span><span class="sxs-lookup"><span data-stu-id="6a097-118">Datastore</span></span>  
  
 <span data-ttu-id="6a097-119">Les sections suivantes décrivent les fichiers journaux d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6a097-119">The following sections describe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup log files.</span></span>  
  
## <a name="summary-text"></a><span data-ttu-id="6a097-120">Texte de résumé</span><span class="sxs-lookup"><span data-stu-id="6a097-120">Summary Text</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a097-121">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6a097-121">Overview</span></span>  
 <span data-ttu-id="6a097-122">Ce fichier montre les composants [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] détectés au cours de l'installation, l'environnement du système d'exploitation, les valeurs des paramètres de ligne de commande (si elles sont spécifiées) et l'état d'ensemble de chaque fichier MSI/MSP exécuté.</span><span class="sxs-lookup"><span data-stu-id="6a097-122">This file shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components that were detected during Setup, the operating system environment, command-line parameter values if they are specified, and the overall status of each MSI/MSP that was executed.</span></span>  
  
 <span data-ttu-id="6a097-123">Le journal comprend les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a097-123">The log is organized into the following sections:</span></span>  
  
-   <span data-ttu-id="6a097-124">un résumé d'ensemble de l'exécution ;</span><span class="sxs-lookup"><span data-stu-id="6a097-124">An overall summary of the execution</span></span>  
  
-   <span data-ttu-id="6a097-125">les propriétés et la configuration de l'ordinateur sur lequel le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été exécuté ;</span><span class="sxs-lookup"><span data-stu-id="6a097-125">Properties and the configuration of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup was run</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6a097-126">précédemment installées sur l'ordinateur ;</span><span class="sxs-lookup"><span data-stu-id="6a097-126">product features previously installed on the computer</span></span>  
  
-   <span data-ttu-id="6a097-127">la description des propriétés de la version d'installation et du package d'installation ;</span><span class="sxs-lookup"><span data-stu-id="6a097-127">Description of the installation version and installation package properties</span></span>  
  
-   <span data-ttu-id="6a097-128">les paramètres d'entrée d'exécution fournis au cours de l'installation ;</span><span class="sxs-lookup"><span data-stu-id="6a097-128">Runtime input settings that are provided during install</span></span>  
  
-   <span data-ttu-id="6a097-129">l'emplacement du fichier de configuration ;</span><span class="sxs-lookup"><span data-stu-id="6a097-129">Location of the configuration file</span></span>  
  
-   <span data-ttu-id="6a097-130">les détails des résultats d'exécution ;</span><span class="sxs-lookup"><span data-stu-id="6a097-130">Details of the execution results</span></span>  
  
-   <span data-ttu-id="6a097-131">les règles globales ;</span><span class="sxs-lookup"><span data-stu-id="6a097-131">Global rules</span></span>  
  
-   <span data-ttu-id="6a097-132">les règles spécifiques au scénario d'installation ;</span><span class="sxs-lookup"><span data-stu-id="6a097-132">Rules specific to the installation scenario</span></span>  
  
-   <span data-ttu-id="6a097-133">les règles ayant échoué ;</span><span class="sxs-lookup"><span data-stu-id="6a097-133">Failed rules</span></span>  
  
-   <span data-ttu-id="6a097-134">l'emplacement du fichier du rapport de règles.</span><span class="sxs-lookup"><span data-stu-id="6a097-134">Location of the rules report file</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a097-135">Emplacement</span><span class="sxs-lookup"><span data-stu-id="6a097-135">Location</span></span>  
 <span data-ttu-id="6a097-136">Il se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="6a097-136">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span>  
  
 <span data-ttu-id="6a097-137">Pour trouver les erreurs dans le fichier texte résumé, recherchez les mots clés « error » ou « failed » dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="6a097-137">To find errors in the summary text file, search the file by using the "error" or "failed" keywords.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmsstxt"></a><span data-ttu-id="6a097-138">Summary_engine-base_YYYYMMDD_HHMMss.txt</span><span class="sxs-lookup"><span data-stu-id="6a097-138">Summary_engine-base_YYYYMMDD_HHMMss.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a097-139">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6a097-139">Overview</span></span>  
 <span data-ttu-id="6a097-140">Le fichier de base summary_engine est semblable au fichier résumé et est généré au cours du flux de travail principal.</span><span class="sxs-lookup"><span data-stu-id="6a097-140">The summary_engine base file is similar to the summary file and is generated during the main workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a097-141">Emplacement</span><span class="sxs-lookup"><span data-stu-id="6a097-141">Location</span></span>  
 <span data-ttu-id="6a097-142">Il se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a097-142">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmss_componentupdatetxt"></a><span data-ttu-id="6a097-143">Summary_engine-base_YYYYMMDD_HHMMss_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="6a097-143">Summary_engine-base_YYYYMMDD_HHMMss_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a097-144">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6a097-144">Overview</span></span>  
 <span data-ttu-id="6a097-145">Le fichier journal résumé de mise à jour des composants est semblable au fichier résumé et est généré au cours du flux de travail de mise à jour des composants.</span><span class="sxs-lookup"><span data-stu-id="6a097-145">The component update summary log file is similar to the summary file and is generated during the component update workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a097-146">Emplacement</span><span class="sxs-lookup"><span data-stu-id="6a097-146">Location</span></span>  
 <span data-ttu-id="6a097-147">Il se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a097-147">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_versionnumbermmdd_hhmmss_globalrulestxt"></a><span data-ttu-id="6a097-148">Summary_engine base_ \<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="6a097-148">Summary_engine-base_\<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a097-149">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6a097-149">Overview</span></span>  
 <span data-ttu-id="6a097-150">Le fichier journal résumé des règles globales est semblable au fichier résumé généré au cours du flux de travail des règles globales.</span><span class="sxs-lookup"><span data-stu-id="6a097-150">The global rules summary log file is similar to the summary file generated during the global rules workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a097-151">Emplacement</span><span class="sxs-lookup"><span data-stu-id="6a097-151">Location</span></span>  
 <span data-ttu-id="6a097-152">Il se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a097-152">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detailtxt"></a><span data-ttu-id="6a097-153">Detail.txt</span><span class="sxs-lookup"><span data-stu-id="6a097-153">Detail.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a097-154">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6a097-154">Overview</span></span>  
 <span data-ttu-id="6a097-155">Detail.txt est généré pour le flux de travail principal, par exemple l'installation ou la mise à niveau, et fournit les détails de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="6a097-155">Detail.txt is generated for the main workflow such as install or upgrade, and provides the details of the execution.</span></span> <span data-ttu-id="6a097-156">Les journaux dans le fichier sont générés en fonction de l'heure à laquelle chaque action pour l'installation a été appelée, et indiquent l'ordre dans lequel les actions ont été exécutées et leurs dépendances.</span><span class="sxs-lookup"><span data-stu-id="6a097-156">The logs in the file are generated based on the time when each action for the installation was invoked, and show the order in which the actions were executed, and their dependencies.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a097-157">Emplacement</span><span class="sxs-lookup"><span data-stu-id="6a097-157">Location</span></span>  
 <span data-ttu-id="6a097-158">Il se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup</span><span class="sxs-lookup"><span data-stu-id="6a097-158">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup</span></span>  
  
 <span data-ttu-id="6a097-159">Bootstrap\Log\\<AAAAMMJJ_HHMM>\Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="6a097-159">Bootstrap\Log\\<YYYYMMDD_HHMM>\Detail.txt.</span></span>  
  
 <span data-ttu-id="6a097-160">Si une erreur se produit au cours du processus d'installation, l'exception ou l'erreur est journalisée à la fin de ce fichier.</span><span class="sxs-lookup"><span data-stu-id="6a097-160">If an error occurs during the Setup process, the exception or error are logged at the end of this file.</span></span> <span data-ttu-id="6a097-161">Pour trouver les erreurs dans ce fichier, examinez d'abord la fin du fichier, puis lancez une recherche sur les mots clés « error » ou « exception » dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="6a097-161">To find the errors in this file, first examine the end of the file followed by a search of the file for the "error" or "exception" keywords.</span></span>  
  
## <a name="detail_componentupdatetxt"></a><span data-ttu-id="6a097-162">Detail_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="6a097-162">Detail_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a097-163">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6a097-163">Overview</span></span>  
 <span data-ttu-id="6a097-164">Le fichier Detail_ComponentUpdate.txt est généré pour le flux de travail de mise à jour des composants et est semblable au fichier Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="6a097-164">The Detail_ComponentUpdate.txt file is generated for the component update workflow and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a097-165">Emplacement</span><span class="sxs-lookup"><span data-stu-id="6a097-165">Location</span></span>  
 <span data-ttu-id="6a097-166">Il se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a097-166">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detail_globalrulestxt"></a><span data-ttu-id="6a097-167">Detail_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="6a097-167">Detail_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a097-168">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6a097-168">Overview</span></span>  
 <span data-ttu-id="6a097-169">Le fichier Detail_GlobalRules.txt est généré pour l'exécution des règles globales et est semblable au fichier Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="6a097-169">Detail_GlobalRules.txt is generated for the global rules execution and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a097-170">Emplacement</span><span class="sxs-lookup"><span data-stu-id="6a097-170">Location</span></span>  
 <span data-ttu-id="6a097-171">Il se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a097-171">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="msi-log-files"></a><span data-ttu-id="6a097-172">Fichiers journaux MSI</span><span class="sxs-lookup"><span data-stu-id="6a097-172">MSI log files</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a097-173">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6a097-173">Overview</span></span>  
 <span data-ttu-id="6a097-174">Les fichiers journaux MSI fournissent des détails sur le processus du package d'installation.</span><span class="sxs-lookup"><span data-stu-id="6a097-174">The MSI log files provide details of the installation package process.</span></span> <span data-ttu-id="6a097-175">Ils sont générés par le programme MSIEXEC lors de l'installation du package spécifié.</span><span class="sxs-lookup"><span data-stu-id="6a097-175">They are generated by the MSIEXEC during the installation of the specified package.</span></span>  
  
 <span data-ttu-id="6a097-176">Types de fichiers journaux MSI :</span><span class="sxs-lookup"><span data-stu-id="6a097-176">Types of MSI log files:</span></span>  
  
-   <span data-ttu-id="6a097-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="6a097-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="6a097-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="6a097-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="6a097-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span><span class="sxs-lookup"><span data-stu-id="6a097-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a097-180">Emplacement</span><span class="sxs-lookup"><span data-stu-id="6a097-180">Location</span></span>  
 <span data-ttu-id="6a097-181">Les fichiers journaux msi se trouvent à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\<nom \> . log.</span><span class="sxs-lookup"><span data-stu-id="6a097-181">The MSI log files are located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\<Name\>.log.</span></span>  
  
 <span data-ttu-id="6a097-182">À la fin du fichier se trouve un résumé de l'exécution qui indique l'état de réussite ou d'échec et les propriétés.</span><span class="sxs-lookup"><span data-stu-id="6a097-182">At the end of the file is a summary of the execution which includes the success or failure status and properties.</span></span> <span data-ttu-id="6a097-183">Pour trouver l'erreur dans le fichier MSI, recherchez « value 3 ». Les erreurs se trouvent généralement à proximité de cette chaîne.</span><span class="sxs-lookup"><span data-stu-id="6a097-183">To find the error in the MSI file, search for "value 3" and usually the errors can be found close to the string.</span></span>  
  
## <a name="configurationfileini"></a><span data-ttu-id="6a097-184">ConfigurationFile.ini</span><span class="sxs-lookup"><span data-stu-id="6a097-184">ConfigurationFile.ini</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a097-185">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6a097-185">Overview</span></span>  
 <span data-ttu-id="6a097-186">Le fichier de configuration contient les paramètres d'entrée fournis au cours de l'installation.</span><span class="sxs-lookup"><span data-stu-id="6a097-186">The configuration file contains the input settings that are provided during installation.</span></span> <span data-ttu-id="6a097-187">Vous pouvez l'utiliser pour redémarrer l'installation sans entrer les paramètres manuellement.</span><span class="sxs-lookup"><span data-stu-id="6a097-187">It can be used to restart the installation without having to enter the settings manually.</span></span> <span data-ttu-id="6a097-188">Toutefois, les mots de passe pour les comptes, PID et certains paramètres ne sont pas enregistrés dans le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="6a097-188">However, passwords for the accounts, PID, and some parameters are not saved in the configuration file.</span></span> <span data-ttu-id="6a097-189">Les paramètres peuvent être soit ajoutés au fichier, soit fournis à l'aide de la ligne de commande ou de l'interface utilisateur du programme d'installation.</span><span class="sxs-lookup"><span data-stu-id="6a097-189">The settings can be either added to the file or provided by using the command line or the Setup user interface.</span></span> <span data-ttu-id="6a097-190">Pour plus d’informations, consultez [installer SQL Server 2014 à l’aide d’un fichier de configuration](install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="6a097-190">For more information, see [Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md).</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a097-191">Emplacement</span><span class="sxs-lookup"><span data-stu-id="6a097-191">Location</span></span>  
 <span data-ttu-id="6a097-192">Il se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a097-192">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="systemconfigurationcheck_reporthtm"></a><span data-ttu-id="6a097-193">SystemConfigurationCheck_Report.htm</span><span class="sxs-lookup"><span data-stu-id="6a097-193">SystemConfigurationCheck_Report.htm</span></span>  
  
### <a name="overview"></a><span data-ttu-id="6a097-194">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="6a097-194">Overview</span></span>  
 <span data-ttu-id="6a097-195">Le rapport de vérification de la configuration du système contient une brève description de chaque rôle exécuté et de l'état d'exécution.</span><span class="sxs-lookup"><span data-stu-id="6a097-195">The system configuration check report contains a short description for each executed rule, and the execution status.</span></span>  
  
### <a name="location"></a><span data-ttu-id="6a097-196">Emplacement</span><span class="sxs-lookup"><span data-stu-id="6a097-196">Location</span></span>  
 <span data-ttu-id="6a097-197">Il se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="6a097-197">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a097-198">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6a097-198">See Also</span></span>  
 <span data-ttu-id="6a097-199">[Rubriques de procédures relatives à l’installation](../../sql-server/install/installation-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="6a097-199">[Installation How-to Topics](../../sql-server/install/installation-how-to-topics.md) </span></span>  
 [<span data-ttu-id="6a097-200">Installer SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="6a097-200">Install SQL Server 2014</span></span>](install-sql-server.md)  
  
  
