---
title: 'Propriétés de l’étape du travail : nouvelle étape du travail (page avancé) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepadvanced.f1
ms.assetid: bdecfd4f-bcd8-4ba2-8ada-fbb636314f40
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42820ffbdbb89261e839b5d1011f3a91b5841c86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705860"
---
# <a name="job-step-properties-new-job-step-advanced-page"></a><span data-ttu-id="117ad-102">Propriétés de l’étape du travail : Nouvelle étape du travail (page Avancé)</span><span class="sxs-lookup"><span data-stu-id="117ad-102">Job Step Properties: New Job Step (Advanced Page)</span></span>
  <span data-ttu-id="117ad-103">Utilisez cette page pour afficher et modifier les propriétés d’une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] étape de travail de l’agent.</span><span class="sxs-lookup"><span data-stu-id="117ad-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step.</span></span>  
  
## <a name="options"></a><span data-ttu-id="117ad-104">Options</span><span class="sxs-lookup"><span data-stu-id="117ad-104">Options</span></span>  
 <span data-ttu-id="117ad-105">**Action en cas de succès**</span><span class="sxs-lookup"><span data-stu-id="117ad-105">**On success action**</span></span>  
 <span data-ttu-id="117ad-106">Définit l'action que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit exécuter si l'étape de travail réussit.</span><span class="sxs-lookup"><span data-stu-id="117ad-106">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step succeeds.</span></span>  
  
 <span data-ttu-id="117ad-107">**Nouvelles tentatives**</span><span class="sxs-lookup"><span data-stu-id="117ad-107">**Retry attempts**</span></span>  
 <span data-ttu-id="117ad-108">Définit le nombre de tentatives effectuées par l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour reprendre une étape de travail qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="117ad-108">Sets the number of times that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent attempts to retry a failed job step.</span></span>  
  
 <span data-ttu-id="117ad-109">**Intervalle de reprise (minutes)**</span><span class="sxs-lookup"><span data-stu-id="117ad-109">**Retry interval (minutes)**</span></span>  
 <span data-ttu-id="117ad-110">Définit le délai d'attente entre les tentatives de reprise par l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="117ad-110">Sets the amount of time for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to wait between retry attempts.</span></span>  
  
 <span data-ttu-id="117ad-111">**Action en cas d'échec**</span><span class="sxs-lookup"><span data-stu-id="117ad-111">**On failure action**</span></span>  
 <span data-ttu-id="117ad-112">Définit l'action que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit exécuter si l'étape de travail échoue.</span><span class="sxs-lookup"><span data-stu-id="117ad-112">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step fails.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="117ad-113">Options des étapes de travail Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="117ad-113">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="117ad-114">**Fichier de sortie**</span><span class="sxs-lookup"><span data-stu-id="117ad-114">**Output file**</span></span>  
 <span data-ttu-id="117ad-115">Définit le fichier à utiliser comme sortie avec l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-115">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="117ad-116">Cette option est disponible uniquement pour les membres du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="117ad-116">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="117ad-117">**...**</span><span class="sxs-lookup"><span data-stu-id="117ad-117">**...**</span></span>  
 <span data-ttu-id="117ad-118">Permet de rechercher le fichier à utiliser comme sortie pour les résultats de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-118">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="117ad-119">**Visualiser**</span><span class="sxs-lookup"><span data-stu-id="117ad-119">**View**</span></span>  
 <span data-ttu-id="117ad-120">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , ce bouton est désactivé pour l’affichage des fichiers de sortie.</span><span class="sxs-lookup"><span data-stu-id="117ad-120">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="117ad-121">Utilisez plutôt le Bloc-Notes pour afficher les fichiers de sortie d'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-121">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="117ad-122">**Ajouter la sortie au fichier existant**</span><span class="sxs-lookup"><span data-stu-id="117ad-122">**Append output to existing file**</span></span>  
 <span data-ttu-id="117ad-123">Ajoute la sortie au contenu existant du fichier.</span><span class="sxs-lookup"><span data-stu-id="117ad-123">Append output to the existing contents of the file.</span></span> <span data-ttu-id="117ad-124">Sinon, le contenu précédent du fichier est remplacé à chaque exécution de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-124">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="117ad-125">**Enregistrer un journal dans la table**</span><span class="sxs-lookup"><span data-stu-id="117ad-125">**Log to table**</span></span>  
 <span data-ttu-id="117ad-126">Consigne la sortie de l'étape de travail dans la table **sysjobstepslogs** de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="117ad-126">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="117ad-127">**Visualiser**</span><span class="sxs-lookup"><span data-stu-id="117ad-127">**View**</span></span>  
 <span data-ttu-id="117ad-128">Quand l'étape de travail a été exécutée au moins une fois, cliquez sur **Afficher** pour afficher sa sortie dans la table.</span><span class="sxs-lookup"><span data-stu-id="117ad-128">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="117ad-129">**Ajouter la sortie à l'entrée existante dans la table**</span><span class="sxs-lookup"><span data-stu-id="117ad-129">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="117ad-130">Ajoute la sortie au contenu existant de la table.</span><span class="sxs-lookup"><span data-stu-id="117ad-130">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="117ad-131">Sinon, le contenu précédent de la table est remplacé à chaque exécution de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-131">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="117ad-132">**Inclure la sortie de l'étape dans l'historique**</span><span class="sxs-lookup"><span data-stu-id="117ad-132">**Include step output in history**</span></span>  
 <span data-ttu-id="117ad-133">Sélectionnez cette option pour inclure la sortie de l'étape de travail dans l'historique des travaux.</span><span class="sxs-lookup"><span data-stu-id="117ad-133">Select this option to include output from the job step in the job history.</span></span>  
  
 <span data-ttu-id="117ad-134">**Exécuter en tant qu'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="117ad-134">**Run as user**</span></span>  
 <span data-ttu-id="117ad-135">Si vous êtes membre du rôle serveur fixe **sysadmin** , vous pouvez sélectionner une autre connexion SQL pour exécuter cette étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-135">If you are a member of the **sysadmin** fixed server role, you can select another SQL login to run this job step.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="117ad-136">Options des étapes de travail du système d'exploitation (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="117ad-136">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="117ad-137">**Fichier de sortie**</span><span class="sxs-lookup"><span data-stu-id="117ad-137">**Output file**</span></span>  
 <span data-ttu-id="117ad-138">Définit le fichier à utiliser comme sortie avec l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-138">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="117ad-139">**...**</span><span class="sxs-lookup"><span data-stu-id="117ad-139">**...**</span></span>  
 <span data-ttu-id="117ad-140">Permet de rechercher le fichier à utiliser comme sortie pour les résultats de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-140">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="117ad-141">**Visualiser**</span><span class="sxs-lookup"><span data-stu-id="117ad-141">**View**</span></span>  
 <span data-ttu-id="117ad-142">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , ce bouton est désactivé pour l’affichage des fichiers de sortie.</span><span class="sxs-lookup"><span data-stu-id="117ad-142">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="117ad-143">Utilisez plutôt le Bloc-Notes pour afficher les fichiers de sortie d'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-143">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="117ad-144">**Ajouter la sortie au fichier existant**</span><span class="sxs-lookup"><span data-stu-id="117ad-144">**Append output to existing file**</span></span>  
 <span data-ttu-id="117ad-145">Ajoute la sortie de l'étape de travail au contenu précédent du fichier à chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="117ad-145">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="117ad-146">**Enregistrer un journal dans la table**</span><span class="sxs-lookup"><span data-stu-id="117ad-146">**Log to table**</span></span>  
 <span data-ttu-id="117ad-147">Consigne la sortie de l'étape de travail dans la table **sysjobstepslogs** de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="117ad-147">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="117ad-148">**Visualiser**</span><span class="sxs-lookup"><span data-stu-id="117ad-148">**View**</span></span>  
 <span data-ttu-id="117ad-149">Quand l'étape de travail a été exécutée au moins une fois, cliquez sur **Afficher** pour afficher sa sortie dans la table.</span><span class="sxs-lookup"><span data-stu-id="117ad-149">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="117ad-150">**Ajouter la sortie à l'entrée existante dans la table**</span><span class="sxs-lookup"><span data-stu-id="117ad-150">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="117ad-151">Ajoute la sortie au contenu existant de la table.</span><span class="sxs-lookup"><span data-stu-id="117ad-151">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="117ad-152">Sinon, le contenu précédent de la table est remplacé à chaque exécution de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-152">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="117ad-153">**Inclure la sortie de l'étape dans l'historique**</span><span class="sxs-lookup"><span data-stu-id="117ad-153">**Include step output in history**</span></span>  
 <span data-ttu-id="117ad-154">Sélectionnez cette option pour inclure la sortie de l'étape de travail dans l'historique des travaux.</span><span class="sxs-lookup"><span data-stu-id="117ad-154">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="117ad-155">Options des étapes de travail PowerShell</span><span class="sxs-lookup"><span data-stu-id="117ad-155">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="117ad-156">**Fichier de sortie**</span><span class="sxs-lookup"><span data-stu-id="117ad-156">**Output file**</span></span>  
 <span data-ttu-id="117ad-157">Définit le fichier à utiliser comme sortie avec l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-157">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="117ad-158">**...**</span><span class="sxs-lookup"><span data-stu-id="117ad-158">**...**</span></span>  
 <span data-ttu-id="117ad-159">Permet de rechercher le fichier à utiliser comme sortie pour les résultats de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-159">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="117ad-160">**Visualiser**</span><span class="sxs-lookup"><span data-stu-id="117ad-160">**View**</span></span>  
 <span data-ttu-id="117ad-161">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , ce bouton est désactivé pour l’affichage des fichiers de sortie.</span><span class="sxs-lookup"><span data-stu-id="117ad-161">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="117ad-162">Utilisez plutôt le Bloc-Notes pour afficher les fichiers de sortie d'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-162">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="117ad-163">**Ajouter la sortie au fichier existant**</span><span class="sxs-lookup"><span data-stu-id="117ad-163">**Append output to existing file**</span></span>  
 <span data-ttu-id="117ad-164">Ajoute la sortie de l'étape de travail au contenu précédent du fichier à chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="117ad-164">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="117ad-165">**Enregistrer un journal dans la table**</span><span class="sxs-lookup"><span data-stu-id="117ad-165">**Log to table**</span></span>  
 <span data-ttu-id="117ad-166">Consigne la sortie de l'étape de travail dans la table **sysjobstepslogs** de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="117ad-166">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="117ad-167">**Visualiser**</span><span class="sxs-lookup"><span data-stu-id="117ad-167">**View**</span></span>  
 <span data-ttu-id="117ad-168">Quand l'étape de travail a été exécutée au moins une fois, cliquez sur **Afficher** pour afficher sa sortie dans la table.</span><span class="sxs-lookup"><span data-stu-id="117ad-168">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="117ad-169">**Ajouter la sortie à l'entrée existante dans la table**</span><span class="sxs-lookup"><span data-stu-id="117ad-169">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="117ad-170">Ajoute la sortie au contenu existant de la table.</span><span class="sxs-lookup"><span data-stu-id="117ad-170">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="117ad-171">Sinon, le contenu précédent de la table est remplacé à chaque exécution de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-171">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="117ad-172">**Inclure la sortie de l'étape dans l'historique**</span><span class="sxs-lookup"><span data-stu-id="117ad-172">**Include step output in history**</span></span>  
 <span data-ttu-id="117ad-173">Sélectionnez cette option pour inclure la sortie de l'étape de travail dans l'historique des travaux.</span><span class="sxs-lookup"><span data-stu-id="117ad-173">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="117ad-174">Options des étapes de travail de l'Agent de lecture de file d'attente de la réplication</span><span class="sxs-lookup"><span data-stu-id="117ad-174">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="117ad-175">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="117ad-175">**Server**</span></span>  
 <span data-ttu-id="117ad-176">Définit le serveur à utiliser pour l'étape de travail de l'Agent de lecture de file d'attente de la réplication.</span><span class="sxs-lookup"><span data-stu-id="117ad-176">Sets the server to use for a replication queue reader job step.</span></span>  
  
 <span data-ttu-id="117ad-177">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="117ad-177">**Database**</span></span>  
 <span data-ttu-id="117ad-178">Définit la base de données à utiliser pour l'étape de travail de l'Agent de lecture de file d'attente de la réplication.</span><span class="sxs-lookup"><span data-stu-id="117ad-178">Sets the database to use for a replication queue reader job step.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-job-steps"></a><span data-ttu-id="117ad-179">Options des étapes de travail de SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="117ad-179">Options for SQL Server Analysis Services Job Steps</span></span>  
 <span data-ttu-id="117ad-180">**Fichier de sortie**</span><span class="sxs-lookup"><span data-stu-id="117ad-180">**Output file**</span></span>  
 <span data-ttu-id="117ad-181">Définit le fichier à utiliser comme sortie avec l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-181">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="117ad-182">Cette option est disponible uniquement pour les membres du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="117ad-182">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="117ad-183">**...**</span><span class="sxs-lookup"><span data-stu-id="117ad-183">**...**</span></span>  
 <span data-ttu-id="117ad-184">Permet de rechercher le fichier à utiliser comme sortie pour les résultats de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-184">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="117ad-185">**Visualiser**</span><span class="sxs-lookup"><span data-stu-id="117ad-185">**View**</span></span>  
 <span data-ttu-id="117ad-186">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], ce bouton est désactivé pour l'affichage des fichiers de sortie.</span><span class="sxs-lookup"><span data-stu-id="117ad-186">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="117ad-187">Utilisez plutôt le Bloc-Notes pour afficher les fichiers de sortie d'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-187">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="117ad-188">**Ajouter la sortie au fichier existant**</span><span class="sxs-lookup"><span data-stu-id="117ad-188">**Append output to existing file**</span></span>  
 <span data-ttu-id="117ad-189">Ajoute la sortie au contenu existant du fichier.</span><span class="sxs-lookup"><span data-stu-id="117ad-189">Append output to the existing contents of the file.</span></span> <span data-ttu-id="117ad-190">Sinon, le contenu précédent du fichier est remplacé à chaque exécution de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-190">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="117ad-191">**Enregistrer un journal dans la table**</span><span class="sxs-lookup"><span data-stu-id="117ad-191">**Log to table**</span></span>  
 <span data-ttu-id="117ad-192">Consigne la sortie de l'étape de travail dans la table **sysjobstepslogs** de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="117ad-192">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="117ad-193">**Visualiser**</span><span class="sxs-lookup"><span data-stu-id="117ad-193">**View**</span></span>  
 <span data-ttu-id="117ad-194">Quand l'étape de travail a été exécutée au moins une fois, cliquez sur **Afficher** pour afficher sa sortie dans la table.</span><span class="sxs-lookup"><span data-stu-id="117ad-194">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="117ad-195">**Ajouter la sortie à l'entrée existante dans la table**</span><span class="sxs-lookup"><span data-stu-id="117ad-195">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="117ad-196">Ajoute la sortie au contenu existant de la table.</span><span class="sxs-lookup"><span data-stu-id="117ad-196">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="117ad-197">Sinon, le contenu précédent de la table est remplacé à chaque exécution de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="117ad-197">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="117ad-198">**Inclure la sortie de l'étape dans l'historique**</span><span class="sxs-lookup"><span data-stu-id="117ad-198">**Include step output in history**</span></span>  
 <span data-ttu-id="117ad-199">Sélectionnez cette option pour inclure la sortie de l'étape de travail dans l'historique des travaux.</span><span class="sxs-lookup"><span data-stu-id="117ad-199">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117ad-200">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="117ad-200">See Also</span></span>  
 [<span data-ttu-id="117ad-201">Gérer les étapes de travail</span><span class="sxs-lookup"><span data-stu-id="117ad-201">Manage Job Steps</span></span>](manage-job-steps.md)  
  
  
