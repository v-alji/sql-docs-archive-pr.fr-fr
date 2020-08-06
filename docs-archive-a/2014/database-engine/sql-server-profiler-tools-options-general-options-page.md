---
title: SQL Server Profiler-Tools-Options (page Options générales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.generaloptions.f1
helpviewer_keywords:
- General Options dialog box
ms.assetid: a888246d-ccfe-415f-bbdc-d6adafac250a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fad4d3529482835367898276a973bd7c8827b553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611939"
---
# <a name="sql-server-profiler---tools-options-general-options-page"></a><span data-ttu-id="6c200-102">SQL Server Profiler-Tools-Options (page Options générales)</span><span class="sxs-lookup"><span data-stu-id="6c200-102">SQL Server Profiler - Tools-Options (General Options Page)</span></span>
  <span data-ttu-id="6c200-103">Utilisez la boîte de dialogue **Options générales** pour afficher ou spécifier les options ci-après.</span><span class="sxs-lookup"><span data-stu-id="6c200-103">Use the **General Options** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6c200-104">Options</span><span class="sxs-lookup"><span data-stu-id="6c200-104">Options</span></span>  
  
### <a name="display-options"></a><span data-ttu-id="6c200-105">Options d'affichage</span><span class="sxs-lookup"><span data-stu-id="6c200-105">Display Options</span></span>  
 <span data-ttu-id="6c200-106">**Nom de la police**</span><span class="sxs-lookup"><span data-stu-id="6c200-106">**Font name**</span></span>  
 <span data-ttu-id="6c200-107">Affiche le nom de la police utilisée dans la grille des résultats de trace pendant les traces.</span><span class="sxs-lookup"><span data-stu-id="6c200-107">Displays the name of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="6c200-108">**Taille de police**</span><span class="sxs-lookup"><span data-stu-id="6c200-108">**Font size**</span></span>  
 <span data-ttu-id="6c200-109">Affiche la taille de la police utilisée dans la grille des résultats de trace pendant les traces.</span><span class="sxs-lookup"><span data-stu-id="6c200-109">Displays the size of the font used in the trace results grid during traces.</span></span>  
  
 <span data-ttu-id="6c200-110">**Choisir la police**</span><span class="sxs-lookup"><span data-stu-id="6c200-110">**Choose Font**</span></span>  
 <span data-ttu-id="6c200-111">Ouvre une boîte de dialogue permettant de modifier les paramètres de police.</span><span class="sxs-lookup"><span data-stu-id="6c200-111">Opens a dialog to change the font settings.</span></span>  
  
 <span data-ttu-id="6c200-112">**Utiliser des paramètres régionaux pour afficher les valeurs de date et d'heure**</span><span class="sxs-lookup"><span data-stu-id="6c200-112">**Use regional settings to display date and time values**</span></span>  
 <span data-ttu-id="6c200-113">Affiche les valeurs de date et d'heure selon les paramètres régionaux configurés sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="6c200-113">Displays date and time values in regional settings configured for your computer.</span></span> <span data-ttu-id="6c200-114">Si vous ne sélectionnez pas cette option, les valeurs de date et d'heure sont affichées dans le format fixe de Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], qui comprend les millisecondes.</span><span class="sxs-lookup"><span data-stu-id="6c200-114">If you do not select this option, the date and time values are displayed in the fixed format used by Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], which includes milliseconds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c200-115">En cochant et en décochant cette case, vous modifiez le format d’affichage des colonnes de temps comme **StartTime** et **EndTime**.</span><span class="sxs-lookup"><span data-stu-id="6c200-115">Toggling this checkbox changes the time columns display format such as **StartTime** and **EndTime**.</span></span> <span data-ttu-id="6c200-116">Toutefois, vous ne modifiez pas les paramètres de valeur **DateTime** dans les événements de langage ou les appels de procédure distante (RPC).</span><span class="sxs-lookup"><span data-stu-id="6c200-116">However, it does not change the **DateTime** value parameters inside the language events or remote procedure calls (RPCs).</span></span>  
  
 <span data-ttu-id="6c200-117">**Afficher les valeurs dans la colonne Durée en microsecondes**</span><span class="sxs-lookup"><span data-stu-id="6c200-117">**Show values in Duration column in microseconds**</span></span>  
 <span data-ttu-id="6c200-118">Affiche les valeurs en microsecondes dans la colonne de données **Durée** des traces.</span><span class="sxs-lookup"><span data-stu-id="6c200-118">Displays the values in microseconds in the **Duration** data column of traces.</span></span> <span data-ttu-id="6c200-119">Par défaut, la colonne **Durée** affiche les valeurs en millisecondes.</span><span class="sxs-lookup"><span data-stu-id="6c200-119">By default, the **Duration** column displays values in milliseconds.</span></span>  
  
### <a name="tracing-options"></a><span data-ttu-id="6c200-120">Options de suivi</span><span class="sxs-lookup"><span data-stu-id="6c200-120">Tracing Options</span></span>  
 <span data-ttu-id="6c200-121">**Démarrer le suivi juste après avoir établi la connexion**</span><span class="sxs-lookup"><span data-stu-id="6c200-121">**Start tracing immediately after making connection**</span></span>  
 <span data-ttu-id="6c200-122">Commence une trace utilisant le modèle par défaut dès qu'une connexion est établie.</span><span class="sxs-lookup"><span data-stu-id="6c200-122">Begin a trace using the default template as soon as a connection is made.</span></span>  
  
 <span data-ttu-id="6c200-123">**Mettre à jour la définition de la trace lors de la modification de la version du fournisseur**</span><span class="sxs-lookup"><span data-stu-id="6c200-123">**Update trace definition when provider version changes**</span></span>  
 <span data-ttu-id="6c200-124">Applique la définition de trace la plus récente à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] lorsque le fournisseur est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="6c200-124">Apply the most current trace definition to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when the provider is updated.</span></span> <span data-ttu-id="6c200-125">Cette option n'est pas activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="6c200-125">This item is not checked by default.</span></span> <span data-ttu-id="6c200-126">Elle force le [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] à interroger le serveur sur la définition de trace et à recréer le fichier sur le disque le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="6c200-126">This forces [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to query the server for the trace definition and re-create, if one exists, the file on disk.</span></span>  
  
### <a name="file-rollover-options"></a><span data-ttu-id="6c200-127">Options de substitution de fichier</span><span class="sxs-lookup"><span data-stu-id="6c200-127">File Rollover Options</span></span>  
 <span data-ttu-id="6c200-128">**Charger tous les fichiers de substitution en séquence sans invite**</span><span class="sxs-lookup"><span data-stu-id="6c200-128">**Load all rollover files in sequence without prompting**</span></span>  
 <span data-ttu-id="6c200-129">Charge automatiquement les fichiers de substitution lorsqu'un fichier de trace est ouvert.</span><span class="sxs-lookup"><span data-stu-id="6c200-129">Load rollover files automatically when a trace file is opened.</span></span> <span data-ttu-id="6c200-130">Si plusieurs fichiers ont été créés pendant le suivi, la sélection de cette option charge automatiquement tous les fichiers de substitution.</span><span class="sxs-lookup"><span data-stu-id="6c200-130">If more than one file was created while tracing, selecting this option automatically loads all rollover files.</span></span>  
  
 <span data-ttu-id="6c200-131">**Demander confirmation avant le chargement des fichiers de substitution**</span><span class="sxs-lookup"><span data-stu-id="6c200-131">**Prompt before loading rollover files**</span></span>  
 <span data-ttu-id="6c200-132">Le [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] vous demande confirmation avant l'ajout d'un fichier de substitution lorsqu'un fichier de trace est ouvert.</span><span class="sxs-lookup"><span data-stu-id="6c200-132">Have [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] prompt you before adding a rollover file when a trace file is opened.</span></span>  
  
 <span data-ttu-id="6c200-133">**Ne jamais charger les fichiers de substitution suivants**</span><span class="sxs-lookup"><span data-stu-id="6c200-133">**Never load subsequent rollover files**</span></span>  
 [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] <span data-ttu-id="6c200-134">ne charge jamais les fichiers de substitution suivants quand un fichier de trace est ouvert.</span><span class="sxs-lookup"><span data-stu-id="6c200-134">never loads subsequent rollover files when a trace file is opened.</span></span>  
  
### <a name="replay-options"></a><span data-ttu-id="6c200-135">Options de relecture</span><span class="sxs-lookup"><span data-stu-id="6c200-135">Replay Options</span></span>  
 <span data-ttu-id="6c200-136">**Nombre par défaut de threads de relecture**</span><span class="sxs-lookup"><span data-stu-id="6c200-136">**Default number of replay threads**</span></span>  
 <span data-ttu-id="6c200-137">Spécifiez le nombre de threads de relecture à utiliser simultanément.</span><span class="sxs-lookup"><span data-stu-id="6c200-137">Specify the number of replay threads to use concurrently.</span></span> <span data-ttu-id="6c200-138">Un nombre élevé consomme davantage de ressources pendant la relecture, mais améliore la simultanéité de relecture.</span><span class="sxs-lookup"><span data-stu-id="6c200-138">A higher number consumes more resources during replay, but increases replay concurrency.</span></span>  
  
 <span data-ttu-id="6c200-139">**Délai d'attente du moniteur d'intégrité par défaut (sec)**</span><span class="sxs-lookup"><span data-stu-id="6c200-139">**Default health monitor wait interval (sec)**</span></span>  
 <span data-ttu-id="6c200-140">Spécifiez le délai d'attente de la relecture, en secondes.</span><span class="sxs-lookup"><span data-stu-id="6c200-140">Specify the wait interval to replay in seconds.</span></span> <span data-ttu-id="6c200-141">La valeur par défaut est 3 600 secondes (1 heure).</span><span class="sxs-lookup"><span data-stu-id="6c200-141">Default is 3600 seconds (1 hour).</span></span> <span data-ttu-id="6c200-142">Ce paramètre affecte la durée d'exécution d'un thread autorisée avant son interruption par le moniteur d'intégrité.</span><span class="sxs-lookup"><span data-stu-id="6c200-142">This setting affects the amount of time a thread is allowed to run before being terminated by the health monitor.</span></span>  
  
 <span data-ttu-id="6c200-143">**Intervalle d'interrogation du moniteur d'intégrité par défaut (sec)**</span><span class="sxs-lookup"><span data-stu-id="6c200-143">**Default health monitor poll interval (sec)**</span></span>  
 <span data-ttu-id="6c200-144">Spécifiez, en secondes, l'intervalle d'interrogation du moniteur d'intégrité pendant la relecture.</span><span class="sxs-lookup"><span data-stu-id="6c200-144">Specify the health monitor poll interval during replay in seconds.</span></span> <span data-ttu-id="6c200-145">La valeur par défaut est 60 secondes.</span><span class="sxs-lookup"><span data-stu-id="6c200-145">Default is 60 seconds.</span></span> <span data-ttu-id="6c200-146">Cette valeur permet à l'utilisateur de configurer la fréquence à laquelle le moniteur d'intégrité interroge les candidats à l'arrêt.</span><span class="sxs-lookup"><span data-stu-id="6c200-146">This value allows the user to configure how often the health monitor polls for candidates for termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c200-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c200-147">See Also</span></span>  
 <span data-ttu-id="6c200-148">[Démarrer automatiquement une trace après s’être connecté à un serveur &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6c200-148">[Start a Trace Automatically after Connecting to a Server &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/start-a-trace-automatically-after-connecting-to-a-server-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6c200-149">[Définir les valeurs par défaut de l’affichage des traces &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6c200-149">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6c200-150">[Relire une table de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6c200-150">[Replay a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6c200-151">[Relire un fichier de trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6c200-151">[Replay a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/replay-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6c200-152">[Relire les traces](../tools/sql-server-profiler/replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="6c200-152">[Replay Traces](../tools/sql-server-profiler/replay-traces.md) </span></span>  
 <span data-ttu-id="6c200-153">[Définir les options de trace globales &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6c200-153">[Set Global Trace Options &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/set-global-trace-options-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="6c200-154">[Modèles et autorisations du générateur de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="6c200-154">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="6c200-155">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6c200-155">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
