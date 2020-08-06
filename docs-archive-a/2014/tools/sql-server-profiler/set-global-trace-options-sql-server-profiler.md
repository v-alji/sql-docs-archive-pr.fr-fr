---
title: Définir les options globales de trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- global trace options [SQL Server]
ms.assetid: 2854608a-c3c7-4eb8-b567-034bfec4b1a9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2f0809ae11776e1bddf42c189b86f48689ff4859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601229"
---
# <a name="set-global-trace-options-sql-server-profiler"></a><span data-ttu-id="1094f-102">Définir les options globales de trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="1094f-102">Set Global Trace Options (SQL Server Profiler)</span></span>
  <span data-ttu-id="1094f-103">Cette rubrique décrit la définition des options qui s'appliquent à toutes les traces créées avec une instance [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]spécifique.</span><span class="sxs-lookup"><span data-stu-id="1094f-103">This topic describes how to set options that apply to all traces that are created with a specific instance of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-global-trace-options"></a><span data-ttu-id="1094f-104">Pour définir les options globales des traces</span><span class="sxs-lookup"><span data-stu-id="1094f-104">To set global trace options</span></span>  
  
1.  <span data-ttu-id="1094f-105">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="1094f-105">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1094f-106">Dans la boîte de dialogue **Options générales**, cliquez sur **Choisir la police**pour modifier les options d’affichage, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1094f-106">In the **General Options**dialog box, click **Choose Font**to modify the display options, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1094f-107">Vous pouvez sélectionner l’option **Démarrer le suivi juste après avoir établi la connexion**.</span><span class="sxs-lookup"><span data-stu-id="1094f-107">Optionally, select **Start tracing immediately after making connection**.</span></span>  
  
4.  <span data-ttu-id="1094f-108">Vous pouvez également sélectionner l’option **Mettre à jour la définition de la trace lors de la modification de la version du fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="1094f-108">Optionally, select **Update trace definition when provider version changes**.</span></span> <span data-ttu-id="1094f-109">Cette option fortement recommandée est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="1094f-109">This option is recommended and is selected by default.</span></span> <span data-ttu-id="1094f-110">Lorsqu'elle est sélectionnée, la définition de la trace est automatiquement mise à jour avec la version actuelle du serveur où la fonction de suivi s'effectue.</span><span class="sxs-lookup"><span data-stu-id="1094f-110">When this option is selected, the trace definition is automatically updated to the current version of the server where tracing is performed.</span></span>  
  
5.  <span data-ttu-id="1094f-111">Vous pouvez spécifier en option comment le serveur doit gérer les fichiers de substitution :</span><span class="sxs-lookup"><span data-stu-id="1094f-111">Optionally, specify how the server should manage rollover files:</span></span>  
  
    -   <span data-ttu-id="1094f-112">Sélectionnez **Charger tous les fichiers de substitution en séquence sans invite** pour charger automatiquement les fichiers de substitution pendant la relecture.</span><span class="sxs-lookup"><span data-stu-id="1094f-112">Select **Load all rollover files in sequence without prompting** to automatically load rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="1094f-113">Sélectionnez **Demander confirmation avant le chargement des fichiers de substitution** pour contrôler le chargement des fichiers de substitution pendant la relecture.</span><span class="sxs-lookup"><span data-stu-id="1094f-113">Select **Prompt before loading rollover files** to control rollover files during replay.</span></span>  
  
    -   <span data-ttu-id="1094f-114">Sélectionnez **Ne jamais charger les fichiers de substitution suivants** pour relire les fichiers un par un.</span><span class="sxs-lookup"><span data-stu-id="1094f-114">Select **Never load subsequent rollover files** to replay only one file at a time.</span></span>  
  
6.  <span data-ttu-id="1094f-115">Vous pouvez éventuellement définir les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1094f-115">Optionally, set replay options:</span></span>  
  
    -   <span data-ttu-id="1094f-116">**Nombre par défaut de threads de relecture** contrôle le nombre de threads de processeurs à utiliser pendant la relecture.</span><span class="sxs-lookup"><span data-stu-id="1094f-116">**Default number of replay threads** controls the number of processor threads to use during replay.</span></span> <span data-ttu-id="1094f-117">Un nombre de threads élevé accélère la relecture, mais dégrade les performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="1094f-117">A higher number of threads causes replay to complete faster, but causes server performance to degrade during replay.</span></span> <span data-ttu-id="1094f-118">La valeur recommandée est **4**.</span><span class="sxs-lookup"><span data-stu-id="1094f-118">The recommended setting is **4**.</span></span> <span data-ttu-id="1094f-119">Le tableau suivant répertorie les options disponibles :</span><span class="sxs-lookup"><span data-stu-id="1094f-119">The following table lists the available options:</span></span>  
  
        |<span data-ttu-id="1094f-120">Valeur</span><span class="sxs-lookup"><span data-stu-id="1094f-120">Value</span></span>|<span data-ttu-id="1094f-121">Description</span><span class="sxs-lookup"><span data-stu-id="1094f-121">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="1094f-122">**2**</span><span class="sxs-lookup"><span data-stu-id="1094f-122">**2**</span></span>|<span data-ttu-id="1094f-123">Valeur minimale.</span><span class="sxs-lookup"><span data-stu-id="1094f-123">Minimum value.</span></span> <span data-ttu-id="1094f-124">Utilisez deux threads pour la relecture.</span><span class="sxs-lookup"><span data-stu-id="1094f-124">Use two threads to replay.</span></span>|  
        |<span data-ttu-id="1094f-125">**4**</span><span class="sxs-lookup"><span data-stu-id="1094f-125">**4**</span></span>|<span data-ttu-id="1094f-126">Valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="1094f-126">Default value.</span></span>|  
        |<span data-ttu-id="1094f-127">**255**</span><span class="sxs-lookup"><span data-stu-id="1094f-127">**255**</span></span>|<span data-ttu-id="1094f-128">Valeur maximale.</span><span class="sxs-lookup"><span data-stu-id="1094f-128">Maximum value.</span></span> <span data-ttu-id="1094f-129">Une valeur maximale risque de nuire aux performances d'autres processus.</span><span class="sxs-lookup"><span data-stu-id="1094f-129">Setting a maximum value will impede performance for other processes.</span></span>|  
  
    -   <span data-ttu-id="1094f-130">L’option**Délai d’attente du moniteur d’intégrité par défaut (sec)** définit la durée maximale, en secondes, pendant laquelle un thread peut bloquer un autre processus.</span><span class="sxs-lookup"><span data-stu-id="1094f-130">**Default health monitor wait interval (sec)** sets the maximum amount of time that a replay thread can block another process in seconds.</span></span> <span data-ttu-id="1094f-131">Le tableau suivant indique les valeurs possibles.</span><span class="sxs-lookup"><span data-stu-id="1094f-131">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="1094f-132">Valeur</span><span class="sxs-lookup"><span data-stu-id="1094f-132">Value</span></span>|<span data-ttu-id="1094f-133">Description</span><span class="sxs-lookup"><span data-stu-id="1094f-133">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="1094f-134">**0**</span><span class="sxs-lookup"><span data-stu-id="1094f-134">**0**</span></span>|<span data-ttu-id="1094f-135">Valeur minimale.</span><span class="sxs-lookup"><span data-stu-id="1094f-135">Minimum value.</span></span> <span data-ttu-id="1094f-136">**0** signifie que [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] n’arrêtera jamais un processus de blocage.</span><span class="sxs-lookup"><span data-stu-id="1094f-136">A setting of **0** means that [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will never stop a blocking process.</span></span>|  
        |<span data-ttu-id="1094f-137">**3600**</span><span class="sxs-lookup"><span data-stu-id="1094f-137">**3600**</span></span>|<span data-ttu-id="1094f-138">Valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="1094f-138">Default value.</span></span> <span data-ttu-id="1094f-139">Autorise les processus de blocage dont la durée n’est pas supérieure à **3600** secondes (une heure).</span><span class="sxs-lookup"><span data-stu-id="1094f-139">Allow blocking processes that do not exceed **3600** seconds, or one hour.</span></span>|  
        |<span data-ttu-id="1094f-140">**86400**</span><span class="sxs-lookup"><span data-stu-id="1094f-140">**86400**</span></span>|<span data-ttu-id="1094f-141">Valeur maximale.</span><span class="sxs-lookup"><span data-stu-id="1094f-141">Maximum value.</span></span> <span data-ttu-id="1094f-142">Autorise les processus de blocage dont la durée n’est pas supérieure à **86400** secondes (un jour).</span><span class="sxs-lookup"><span data-stu-id="1094f-142">Allow blocking processes that do not exceed **86400** seconds, or one day.</span></span>|  
  
    -   <span data-ttu-id="1094f-143">L’option**Intervalle d’interrogation du moniteur d’intégrité par défaut (s)** définit la fréquence d’interrogation des threads de relecture des processus de blocage.</span><span class="sxs-lookup"><span data-stu-id="1094f-143">**Default health monitor poll interval (sec)** sets the frequency to poll replay threads for blocking processes.</span></span> <span data-ttu-id="1094f-144">Le tableau suivant indique les valeurs possibles.</span><span class="sxs-lookup"><span data-stu-id="1094f-144">The following table explains the values.</span></span>  
  
        |<span data-ttu-id="1094f-145">Valeur</span><span class="sxs-lookup"><span data-stu-id="1094f-145">Value</span></span>|<span data-ttu-id="1094f-146">Description</span><span class="sxs-lookup"><span data-stu-id="1094f-146">Description</span></span>|  
        |-----------|-----------------|  
        |<span data-ttu-id="1094f-147">**1**</span><span class="sxs-lookup"><span data-stu-id="1094f-147">**1**</span></span>|<span data-ttu-id="1094f-148">Valeur minimale.</span><span class="sxs-lookup"><span data-stu-id="1094f-148">Minimum value.</span></span> <span data-ttu-id="1094f-149">**1[!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] signifie que** interroge les processus de blocage une fois par seconde.</span><span class="sxs-lookup"><span data-stu-id="1094f-149">A setting of **1** means [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] will poll for blocking processes once per second.</span></span>|  
        |<span data-ttu-id="1094f-150">**60**</span><span class="sxs-lookup"><span data-stu-id="1094f-150">**60**</span></span>|<span data-ttu-id="1094f-151">Valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="1094f-151">Default value.</span></span> <span data-ttu-id="1094f-152">Interroge les processus de blocage une fois par minute.</span><span class="sxs-lookup"><span data-stu-id="1094f-152">Poll for blocking processes once per minute.</span></span>|  
        |<span data-ttu-id="1094f-153">**86400**</span><span class="sxs-lookup"><span data-stu-id="1094f-153">**86400**</span></span>|<span data-ttu-id="1094f-154">Valeur maximale.</span><span class="sxs-lookup"><span data-stu-id="1094f-154">Maximum value.</span></span> <span data-ttu-id="1094f-155">Interroge les processus de blocage une fois toutes les **86400** secondes (une fois par jour).</span><span class="sxs-lookup"><span data-stu-id="1094f-155">Poll for blocking processes once per **86400** seconds, or one day.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1094f-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1094f-156">See Also</span></span>  
 <span data-ttu-id="1094f-157">[Définir les valeurs par défaut de l’affichage des traces &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="1094f-157">[Set Trace Display Defaults &#40;SQL Server Profiler&#41;](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="1094f-158">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1094f-158">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
