---
title: 'Propriétés de l’étape du travail : nouvelle étape du travail (page général) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepgeneral.f1
ms.assetid: 8d1885ba-4386-4528-8f2b-68c16852720c
author: stevestein
ms.author: sstein
ms.openlocfilehash: c76e1ecb69a1475ec102f143a6a1ca34fbf91e3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612064"
---
# <a name="job-step-properties-new-job-step-general-page"></a><span data-ttu-id="377b1-102">Propriétés de l’étape du travail : Nouvelle étape du travail (page Général)</span><span class="sxs-lookup"><span data-stu-id="377b1-102">Job Step Properties: New Job Step (General Page)</span></span>
  <span data-ttu-id="377b1-103">Utilisez cette page pour afficher et modifier les propriétés d’une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] étape de travail de l’agent ou pour définir une nouvelle étape de travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step, or to define a new job step.</span></span>  
  
 <span data-ttu-id="377b1-104">Pour naviguer vers cette page, dans l’Explorateur d’objets [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , développez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, cliquez avec le bouton droit sur **Travaux**, cliquez sur **Nouvelles tâches**, sélectionnez la page **Étapes** et cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="377b1-104">To navigate to this page, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, click **New Jobs**, select the **Steps** page, and click **New**.</span></span> <span data-ttu-id="377b1-105">Vous pouvez également accéder à cette page en cliquant avec le bouton droit sur un travail dans l’Explorateur d’objets, en cliquant sur **Propriétés**, en sélectionnant la page **Étapes** et en cliquant sur **Nouveau**, **Insérer**ou **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="377b1-105">You can also navigate to this page by right-clicking a job in Object Explorer, clicking **Properties**, selecting the **Steps** page, and clicking **New**, **Insert**, or **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="377b1-106">Options</span><span class="sxs-lookup"><span data-stu-id="377b1-106">Options</span></span>  
 <span data-ttu-id="377b1-107">**Nom de l’étape**</span><span class="sxs-lookup"><span data-stu-id="377b1-107">**Step name**</span></span>  
 <span data-ttu-id="377b1-108">Définissez le nom de l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-108">Set the name of the job step.</span></span>  
  
 <span data-ttu-id="377b1-109">**Type**</span><span class="sxs-lookup"><span data-stu-id="377b1-109">**Type**</span></span>  
 <span data-ttu-id="377b1-110">Définissez le sous-système utilisé par l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-110">Set the subsystem that the job step uses.</span></span> <span data-ttu-id="377b1-111">En fonction du sous-système sélectionné, les options affichées pour définir l'étape du travail changent.</span><span class="sxs-lookup"><span data-stu-id="377b1-111">Based on the subsystem you choose, the options displayed for defining the job step change.</span></span>  
  
 <span data-ttu-id="377b1-112">**Exécuter en tant que**</span><span class="sxs-lookup"><span data-stu-id="377b1-112">**Run as**</span></span>  
 <span data-ttu-id="377b1-113">Définissez le compte proxy pour l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-113">Set the proxy account for the job step.</span></span> <span data-ttu-id="377b1-114">Les membres du rôle serveur fixe sysadmin peuvent également spécifier le **Compte de service SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="377b1-114">Members of the sysadmin fixed server role may also specify the **SQL Agent Service Account**.</span></span>  
  
 <span data-ttu-id="377b1-115">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="377b1-115">**Database**</span></span>  
 <span data-ttu-id="377b1-116">Définissez la base de données où est exécutée l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-116">Set the database that the job step runs in.</span></span> <span data-ttu-id="377b1-117">Cette option est disponible pour tous les types d'étapes de travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-117">This option is not available for all job step types.</span></span>  
  
 <span data-ttu-id="377b1-118">**Commande**</span><span class="sxs-lookup"><span data-stu-id="377b1-118">**Command**</span></span>  
 <span data-ttu-id="377b1-119">Définissez la commande exécutée par l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-119">Set the command that the job step runs.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="377b1-120">Options des étapes de travail Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="377b1-120">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="377b1-121">**Ouvrir**</span><span class="sxs-lookup"><span data-stu-id="377b1-121">**Open**</span></span>  
 <span data-ttu-id="377b1-122">Charge la commande à partir d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="377b1-122">Load the command from a file.</span></span>  
  
 <span data-ttu-id="377b1-123">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-123">**Select All**</span></span>  
 <span data-ttu-id="377b1-124">Sélectionne le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-124">Select the text of the command.</span></span>  
  
 <span data-ttu-id="377b1-125">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-125">**Copy**</span></span>  
 <span data-ttu-id="377b1-126">Copie le texte sélectionné dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-126">Copy the selected text to the Clipboard.</span></span>  
  
 <span data-ttu-id="377b1-127">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-127">**Paste**</span></span>  
 <span data-ttu-id="377b1-128">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-128">Paste the contents of the Clipboard.</span></span>  
  
 <span data-ttu-id="377b1-129">**Analyser**.</span><span class="sxs-lookup"><span data-stu-id="377b1-129">**Parse**</span></span>  
 <span data-ttu-id="377b1-130">Vérifie la syntaxe de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-130">Check the syntax of the command.</span></span>  
  
## <a name="options-for-activex-script-job-steps"></a><span data-ttu-id="377b1-131">Options pour les étapes de travail Script ActiveX</span><span class="sxs-lookup"><span data-stu-id="377b1-131">Options for ActiveX Script Job Steps</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="377b1-132">Le sous-système de création de scripts ActiveX sera supprimé de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans une version future de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="377b1-132">The ActiveX Scripting subsystem will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="377b1-133">Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="377b1-133">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="377b1-134">**VBScript**</span><span class="sxs-lookup"><span data-stu-id="377b1-134">**VBScript**</span></span>  
 <span data-ttu-id="377b1-135">Définit [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition en tant que langage des étapes de travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-135">Specify [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition as the language for the job steps.</span></span>  
  
 <span data-ttu-id="377b1-136">**JScript**</span><span class="sxs-lookup"><span data-stu-id="377b1-136">**JScript**</span></span>  
 <span data-ttu-id="377b1-137">Définit JScript en tant que langage des étapes de travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-137">Specify JScript as the language for the job steps.</span></span>  
  
 <span data-ttu-id="377b1-138">**Autres**</span><span class="sxs-lookup"><span data-stu-id="377b1-138">**Other**</span></span>  
 <span data-ttu-id="377b1-139">Tapez le nom du langage des étapes de travail écrites dans un autre langage de script.</span><span class="sxs-lookup"><span data-stu-id="377b1-139">Type the name of the language for job steps written in another scripting language.</span></span>  
  
 <span data-ttu-id="377b1-140">**Ouvrir**</span><span class="sxs-lookup"><span data-stu-id="377b1-140">**Open**</span></span>  
 <span data-ttu-id="377b1-141">Charge la commande à partir d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="377b1-141">Load the command from a file.</span></span>  
  
 <span data-ttu-id="377b1-142">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-142">**Select All**</span></span>  
 <span data-ttu-id="377b1-143">Sélectionne le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-143">Select the text of the command.</span></span>  
  
 <span data-ttu-id="377b1-144">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-144">**Copy**</span></span>  
 <span data-ttu-id="377b1-145">Copie le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-145">Copy the selected text.</span></span>  
  
 <span data-ttu-id="377b1-146">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-146">**Paste**</span></span>  
 <span data-ttu-id="377b1-147">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-147">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="377b1-148">Options des étapes de travail du système d'exploitation (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="377b1-148">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="377b1-149">**Traiter le code de sortie d'une commande réussie**</span><span class="sxs-lookup"><span data-stu-id="377b1-149">**Process exit code of a successful command**</span></span>  
 <span data-ttu-id="377b1-150">Tapez le code de sortie renvoyé par la commande pour indiquer la réussite de son exécution.</span><span class="sxs-lookup"><span data-stu-id="377b1-150">Type the exit code that the command returns to indicate success.</span></span>  
  
 <span data-ttu-id="377b1-151">**Ouvrir**</span><span class="sxs-lookup"><span data-stu-id="377b1-151">**Open**</span></span>  
 <span data-ttu-id="377b1-152">Charge la commande à partir d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="377b1-152">Load the command from a file.</span></span>  
  
 <span data-ttu-id="377b1-153">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-153">**Select All**</span></span>  
 <span data-ttu-id="377b1-154">Sélectionne le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-154">Select the text of the command.</span></span>  
  
 <span data-ttu-id="377b1-155">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-155">**Copy**</span></span>  
 <span data-ttu-id="377b1-156">Copie le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-156">Copy the selected text.</span></span>  
  
 <span data-ttu-id="377b1-157">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-157">**Paste**</span></span>  
 <span data-ttu-id="377b1-158">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-158">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="377b1-159">Options des étapes de travail PowerShell</span><span class="sxs-lookup"><span data-stu-id="377b1-159">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="377b1-160">**Ouvrir**</span><span class="sxs-lookup"><span data-stu-id="377b1-160">**Open**</span></span>  
 <span data-ttu-id="377b1-161">Charge le script à partir d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="377b1-161">Load the script from a file.</span></span>  
  
 <span data-ttu-id="377b1-162">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-162">**Select All**</span></span>  
 <span data-ttu-id="377b1-163">Sélectionne le texte du script.</span><span class="sxs-lookup"><span data-stu-id="377b1-163">Select the text of the script.</span></span>  
  
 <span data-ttu-id="377b1-164">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-164">**Copy**</span></span>  
 <span data-ttu-id="377b1-165">Copie le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-165">Copy the selected text.</span></span>  
  
 <span data-ttu-id="377b1-166">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-166">**Paste**</span></span>  
 <span data-ttu-id="377b1-167">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-167">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-distributor-job-steps"></a><span data-ttu-id="377b1-168">Options pour les étapes de travail Serveur de distribution de réplication</span><span class="sxs-lookup"><span data-stu-id="377b1-168">Options for Replication Distributor Job Steps</span></span>  
 <span data-ttu-id="377b1-169">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-169">**Select All**</span></span>  
 <span data-ttu-id="377b1-170">Sélectionne le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-170">Select the text of the command.</span></span>  
  
 <span data-ttu-id="377b1-171">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-171">**Copy**</span></span>  
 <span data-ttu-id="377b1-172">Copie le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-172">Copy the selected text.</span></span>  
  
 <span data-ttu-id="377b1-173">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-173">**Paste**</span></span>  
 <span data-ttu-id="377b1-174">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-174">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-merge-job-steps"></a><span data-ttu-id="377b1-175">Options pour les étapes de travail Fusion de réplication</span><span class="sxs-lookup"><span data-stu-id="377b1-175">Options for Replication Merge Job Steps</span></span>  
 <span data-ttu-id="377b1-176">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-176">**Select All**</span></span>  
 <span data-ttu-id="377b1-177">Sélectionne le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-177">Select the text of the command.</span></span>  
  
 <span data-ttu-id="377b1-178">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-178">**Copy**</span></span>  
 <span data-ttu-id="377b1-179">Copie le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-179">Copy the selected text.</span></span>  
  
 <span data-ttu-id="377b1-180">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-180">**Paste**</span></span>  
 <span data-ttu-id="377b1-181">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-181">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="377b1-182">Options des étapes de travail de l'Agent de lecture de file d'attente de la réplication</span><span class="sxs-lookup"><span data-stu-id="377b1-182">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="377b1-183">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="377b1-183">**Database**</span></span>  
 <span data-ttu-id="377b1-184">Base de données à utiliser pour l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-184">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="377b1-185">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-185">**Select All**</span></span>  
 <span data-ttu-id="377b1-186">Sélectionne le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-186">Select the text of the command.</span></span>  
  
 <span data-ttu-id="377b1-187">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-187">**Copy**</span></span>  
 <span data-ttu-id="377b1-188">Copie le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-188">Copy the selected text.</span></span>  
  
 <span data-ttu-id="377b1-189">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-189">**Paste**</span></span>  
 <span data-ttu-id="377b1-190">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-190">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-snapshot-job-steps"></a><span data-ttu-id="377b1-191">Options pour les étapes de travail d'instantané de réplication</span><span class="sxs-lookup"><span data-stu-id="377b1-191">Options for Replication Snapshot Job Steps</span></span>  
 <span data-ttu-id="377b1-192">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-192">**Select All**</span></span>  
 <span data-ttu-id="377b1-193">Sélectionne le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-193">Select the text of the command.</span></span>  
  
 <span data-ttu-id="377b1-194">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-194">**Copy**</span></span>  
 <span data-ttu-id="377b1-195">Copie le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-195">Copy the selected text.</span></span>  
  
 <span data-ttu-id="377b1-196">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-196">**Paste**</span></span>  
 <span data-ttu-id="377b1-197">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-197">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-transaction-log-reader-job-steps"></a><span data-ttu-id="377b1-198">Options pour les étapes de travail Lecteur du journal des transactions de réplication</span><span class="sxs-lookup"><span data-stu-id="377b1-198">Options for Replication Transaction-Log Reader Job Steps</span></span>  
 <span data-ttu-id="377b1-199">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-199">**Select All**</span></span>  
 <span data-ttu-id="377b1-200">Sélectionne le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-200">Select the text of the command.</span></span>  
  
 <span data-ttu-id="377b1-201">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-201">**Copy**</span></span>  
 <span data-ttu-id="377b1-202">Copie le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-202">Copy the selected text.</span></span>  
  
 <span data-ttu-id="377b1-203">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-203">**Paste**</span></span>  
 <span data-ttu-id="377b1-204">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-204">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-command-job-steps"></a><span data-ttu-id="377b1-205">Options pour les étapes de travail Commande SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="377b1-205">Options for SQL Server Analysis Services Command Job Steps</span></span>  
 <span data-ttu-id="377b1-206">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="377b1-206">**Server**</span></span>  
 <span data-ttu-id="377b1-207">Sélectionnez le serveur sur lequel vous souhaitez exécuter l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-207">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="377b1-208">**Ouvrir**</span><span class="sxs-lookup"><span data-stu-id="377b1-208">**Open**</span></span>  
 <span data-ttu-id="377b1-209">Charge la commande à partir d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="377b1-209">Load the command from a file.</span></span>  
  
 <span data-ttu-id="377b1-210">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-210">**Select All**</span></span>  
 <span data-ttu-id="377b1-211">Sélectionne le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-211">Select the text of the command.</span></span>  
  
 <span data-ttu-id="377b1-212">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-212">**Copy**</span></span>  
 <span data-ttu-id="377b1-213">Copie le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-213">Copy the selected text.</span></span>  
  
 <span data-ttu-id="377b1-214">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-214">**Paste**</span></span>  
 <span data-ttu-id="377b1-215">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-215">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-query-job-steps"></a><span data-ttu-id="377b1-216">Options pour les étapes de travail Requête SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="377b1-216">Options for SQL Server Analysis Services Query Job Steps</span></span>  
 <span data-ttu-id="377b1-217">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="377b1-217">**Server**</span></span>  
 <span data-ttu-id="377b1-218">Sélectionnez le serveur sur lequel vous souhaitez exécuter l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-218">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="377b1-219">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="377b1-219">**Database**</span></span>  
 <span data-ttu-id="377b1-220">Base de données à utiliser pour l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-220">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="377b1-221">**Ouvrir**</span><span class="sxs-lookup"><span data-stu-id="377b1-221">**Open**</span></span>  
 <span data-ttu-id="377b1-222">Charge la commande à partir d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="377b1-222">Load the command from a file.</span></span>  
  
 <span data-ttu-id="377b1-223">**Sélectionner tout**</span><span class="sxs-lookup"><span data-stu-id="377b1-223">**Select All**</span></span>  
 <span data-ttu-id="377b1-224">Sélectionne le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-224">Select the text of the command.</span></span>  
  
 <span data-ttu-id="377b1-225">**Copier**</span><span class="sxs-lookup"><span data-stu-id="377b1-225">**Copy**</span></span>  
 <span data-ttu-id="377b1-226">Copie le texte sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-226">Copy the selected text.</span></span>  
  
 <span data-ttu-id="377b1-227">**Coller**</span><span class="sxs-lookup"><span data-stu-id="377b1-227">**Paste**</span></span>  
 <span data-ttu-id="377b1-228">Colle le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="377b1-228">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-integration-services-package-execution-job-steps"></a><span data-ttu-id="377b1-229">Options pour les étapes de travail Exécution du package Integration Services</span><span class="sxs-lookup"><span data-stu-id="377b1-229">Options for Integration Services Package Execution Job Steps</span></span>  
  
### <a name="general-tab"></a><span data-ttu-id="377b1-230">Onglet Général</span><span class="sxs-lookup"><span data-stu-id="377b1-230">General Tab</span></span>  
 <span data-ttu-id="377b1-231">Spécifiez l'emplacement du package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) et la méthode d'authentification à utiliser.</span><span class="sxs-lookup"><span data-stu-id="377b1-231">Specify where the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package is located and what authentication method to use.</span></span> <span data-ttu-id="377b1-232">Les options suivantes sont disponibles quand vous sélectionnez cet onglet :</span><span class="sxs-lookup"><span data-stu-id="377b1-232">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="377b1-233">**Source du package**</span><span class="sxs-lookup"><span data-stu-id="377b1-233">**Package source**</span></span>  
 <span data-ttu-id="377b1-234">Spécifiez l'emplacement où est stocké le package [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="377b1-234">Specify where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="377b1-235">Choisissez l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="377b1-235">Choose one of the following:</span></span>  
  
-   <span data-ttu-id="377b1-236">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="377b1-236">**SQL Server**</span></span>  
  
-   <span data-ttu-id="377b1-237">**Système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="377b1-237">**File system**</span></span>  
  
-   <span data-ttu-id="377b1-238">**Magasin de packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="377b1-238">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="377b1-239">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="377b1-239">**Server**</span></span>  
 <span data-ttu-id="377b1-240">Tapez le nom du serveur où est stocké le package [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="377b1-240">Type the server name where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="377b1-241">Cette option n’est disponible que si **SQL Server** ou **Magasin de packages SSIS** est spécifié dans **Source du package**.</span><span class="sxs-lookup"><span data-stu-id="377b1-241">This option is only available when **SQL Server** or **SSIS Package Store** is specified for **Package Source**.</span></span>  
  
 <span data-ttu-id="377b1-242">**Utiliser l'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="377b1-242">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="377b1-243">Les connexions à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisent l'authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="377b1-243">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="377b1-244">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="377b1-244">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="377b1-245">Les connexions à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisent l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="377b1-245">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="377b1-246">Si vous sélectionnez cette méthode d’authentification, entrez le **Nom d’utilisateur** et le **Mot de passe**appropriés.</span><span class="sxs-lookup"><span data-stu-id="377b1-246">If this method of authentication is selected, enter the appropriate **User name** and **Password**.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="377b1-247">est fournie dans un souci de compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="377b1-247">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="377b1-248">Pour une sécurité renforcée, utilisez l'authentification Windows dans la mesure du possible.</span><span class="sxs-lookup"><span data-stu-id="377b1-248">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="377b1-249">**Package**</span><span class="sxs-lookup"><span data-stu-id="377b1-249">**Package**</span></span>  
 <span data-ttu-id="377b1-250">Tapez l'emplacement du package.</span><span class="sxs-lookup"><span data-stu-id="377b1-250">Type the location of the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="377b1-251">Pour les packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] protégés par mot de passe, cliquez sur l’onglet **Configurations** pour entrer le mot de passe dans la boîte de dialogue **Mot de passe du package** .</span><span class="sxs-lookup"><span data-stu-id="377b1-251">For password-protected [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages, click the **Configurations** tab to enter the password in the **Package Password** dialog box.</span></span> <span data-ttu-id="377b1-252">Sinon, le travail de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent chargé d'exécuter le package protégé par mot de passe échouera.</span><span class="sxs-lookup"><span data-stu-id="377b1-252">Otherwise, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that executes the password-protected package will fail.</span></span>  
  
### <a name="configurations-tab"></a><span data-ttu-id="377b1-253">Onglet Configurations</span><span class="sxs-lookup"><span data-stu-id="377b1-253">Configurations Tab</span></span>  
 <span data-ttu-id="377b1-254">Spécifiez les options de configuration du package [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="377b1-254">Specify configuration options for the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span> <span data-ttu-id="377b1-255">Lorsque vous sélectionnez cet onglet, les options suivantes sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="377b1-255">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="377b1-256">**Fichiers de configuration**</span><span class="sxs-lookup"><span data-stu-id="377b1-256">**Configuration files**</span></span>  
 <span data-ttu-id="377b1-257">Répertorie les fichiers de configuration pour le package.</span><span class="sxs-lookup"><span data-stu-id="377b1-257">Lists the configuration files for the package.</span></span>  
  
 <span data-ttu-id="377b1-258">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="377b1-258">**Add**</span></span>  
 <span data-ttu-id="377b1-259">Ajoute un fichier de configuration pour le package.</span><span class="sxs-lookup"><span data-stu-id="377b1-259">Add a configuration file for the package.</span></span>  
  
 <span data-ttu-id="377b1-260">**Remove**</span><span class="sxs-lookup"><span data-stu-id="377b1-260">**Remove**</span></span>  
 <span data-ttu-id="377b1-261">Supprime un fichier de configuration pour le package.</span><span class="sxs-lookup"><span data-stu-id="377b1-261">Remove a configuration file for the package.</span></span>  
  
 <span data-ttu-id="377b1-262">**Monter**</span><span class="sxs-lookup"><span data-stu-id="377b1-262">**Move Up**</span></span>  
 <span data-ttu-id="377b1-263">Déplace le fichier de configuration sélectionné vers le haut.</span><span class="sxs-lookup"><span data-stu-id="377b1-263">Move the selected configuration file up.</span></span>  
  
 <span data-ttu-id="377b1-264">**Descendre**</span><span class="sxs-lookup"><span data-stu-id="377b1-264">**Move Down**</span></span>  
 <span data-ttu-id="377b1-265">Déplace le fichier de configuration sélectionné vers le bas.</span><span class="sxs-lookup"><span data-stu-id="377b1-265">Move the selected configuration file down.</span></span>  
  
### <a name="command-files-tab"></a><span data-ttu-id="377b1-266">Onglet Fichiers de commandes</span><span class="sxs-lookup"><span data-stu-id="377b1-266">Command Files Tab</span></span>  
 <span data-ttu-id="377b1-267">Sélectionnez les fichiers de commandes pour le package.</span><span class="sxs-lookup"><span data-stu-id="377b1-267">Select command files for the package.</span></span> <span data-ttu-id="377b1-268">Les fichiers de commandes sont traités dans l'ordre dans lequel ils apparaissent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="377b1-268">Command files are processed in the order in which they appear in the list.</span></span> <span data-ttu-id="377b1-269">Les options suivantes sont disponibles quand vous sélectionnez cet onglet :</span><span class="sxs-lookup"><span data-stu-id="377b1-269">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="377b1-270">**Fichiers de commandes**</span><span class="sxs-lookup"><span data-stu-id="377b1-270">**Command files**</span></span>  
 <span data-ttu-id="377b1-271">Répertorie les fichiers de commandes pour le package.</span><span class="sxs-lookup"><span data-stu-id="377b1-271">Lists the command files for the package.</span></span>  
  
 <span data-ttu-id="377b1-272">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="377b1-272">**Add**</span></span>  
 <span data-ttu-id="377b1-273">Ajoute un fichier de commandes.</span><span class="sxs-lookup"><span data-stu-id="377b1-273">Add a command file.</span></span>  
  
 <span data-ttu-id="377b1-274">**Remove**</span><span class="sxs-lookup"><span data-stu-id="377b1-274">**Remove**</span></span>  
 <span data-ttu-id="377b1-275">Supprime le fichier de commandes sélectionné.</span><span class="sxs-lookup"><span data-stu-id="377b1-275">Remove the selected command file.</span></span>  
  
 <span data-ttu-id="377b1-276">**Monter**</span><span class="sxs-lookup"><span data-stu-id="377b1-276">**Move Up**</span></span>  
 <span data-ttu-id="377b1-277">Déplace le fichier de commandes sélectionné vers le haut.</span><span class="sxs-lookup"><span data-stu-id="377b1-277">Move the selected command file up.</span></span>  
  
 <span data-ttu-id="377b1-278">**Descendre**</span><span class="sxs-lookup"><span data-stu-id="377b1-278">**Move Down**</span></span>  
 <span data-ttu-id="377b1-279">Déplace le fichier de commandes sélectionné vers le bas.</span><span class="sxs-lookup"><span data-stu-id="377b1-279">Move the selected command file down.</span></span>  
  
### <a name="data-sources-tab"></a><span data-ttu-id="377b1-280">Onglet Sources de données</span><span class="sxs-lookup"><span data-stu-id="377b1-280">Data Sources Tab</span></span>  
 <span data-ttu-id="377b1-281">Sous cet onglet, vous pouvez consulter les sources de données spécifiées dans le package.</span><span class="sxs-lookup"><span data-stu-id="377b1-281">View the data sources specified in the package on this tab.</span></span>  
  
 <span data-ttu-id="377b1-282">**Gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="377b1-282">**Connection Manager**</span></span>  
 <span data-ttu-id="377b1-283">Affichez le nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="377b1-283">View the name of the data source.</span></span>  
  
 <span data-ttu-id="377b1-284">**Description**</span><span class="sxs-lookup"><span data-stu-id="377b1-284">**Description**</span></span>  
 <span data-ttu-id="377b1-285">Affichez la description de la source de données.</span><span class="sxs-lookup"><span data-stu-id="377b1-285">View the description of the data source.</span></span>  
  
 <span data-ttu-id="377b1-286">**Chaîne de connexion**</span><span class="sxs-lookup"><span data-stu-id="377b1-286">**Connection String**</span></span>  
 <span data-ttu-id="377b1-287">Affiche la chaîne de connexion de la source de données.</span><span class="sxs-lookup"><span data-stu-id="377b1-287">View the connection string for the data source.</span></span>  
  
### <a name="execution-options-tab"></a><span data-ttu-id="377b1-288">Onglet Options d'exécution</span><span class="sxs-lookup"><span data-stu-id="377b1-288">Execution Options Tab</span></span>  
 <span data-ttu-id="377b1-289">Sous cet onglet, vous pouvez consulter ou modifier les options d'exécution pour le package.</span><span class="sxs-lookup"><span data-stu-id="377b1-289">View or change the execution options for the package on this tab.</span></span>  
  
 <span data-ttu-id="377b1-290">**Mettre le package en échec en cas d'avertissements de validation**</span><span class="sxs-lookup"><span data-stu-id="377b1-290">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="377b1-291">Sélectionnez cette option pour faire échouer l'exécution du package en cas d'avertissements de validation.</span><span class="sxs-lookup"><span data-stu-id="377b1-291">Select this option for package execution to fail if validation warnings occur.</span></span>  
  
 <span data-ttu-id="377b1-292">**Valider le package sans l'exécuter**</span><span class="sxs-lookup"><span data-stu-id="377b1-292">**Validate package without executing**</span></span>  
 <span data-ttu-id="377b1-293">Sélectionnez cette option pour que l'étape du travail valide le package, mais ne l'exécute pas.</span><span class="sxs-lookup"><span data-stu-id="377b1-293">Select this option for the job step to validate, but not execute, the package.</span></span>  
  
 <span data-ttu-id="377b1-294">**Maximum d'exécutables simultanés**</span><span class="sxs-lookup"><span data-stu-id="377b1-294">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="377b1-295">Nombre maximal de fichiers exécutables pouvant être exécutés en même temps.</span><span class="sxs-lookup"><span data-stu-id="377b1-295">Maximum number of executable files that can run at one time.</span></span>  
  
 <span data-ttu-id="377b1-296">**Activer les points de contrôle de package**</span><span class="sxs-lookup"><span data-stu-id="377b1-296">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="377b1-297">Sélectionnez cette option pour que l'étape du travail utilise les points de vérification du package.</span><span class="sxs-lookup"><span data-stu-id="377b1-297">Select this option for the job step to use package checkpoints.</span></span>  
  
 <span data-ttu-id="377b1-298">**Fichier de point de contrôle**</span><span class="sxs-lookup"><span data-stu-id="377b1-298">**Checkpoint file**</span></span>  
 <span data-ttu-id="377b1-299">Tapez le nom du fichier de point de vérification du package.</span><span class="sxs-lookup"><span data-stu-id="377b1-299">Type the name of the package checkpoint file.</span></span>  
  
 <span data-ttu-id="377b1-300">**...**</span><span class="sxs-lookup"><span data-stu-id="377b1-300">**...**</span></span>  
 <span data-ttu-id="377b1-301">Naviguez jusqu'au fichier de point de vérification du package.</span><span class="sxs-lookup"><span data-stu-id="377b1-301">Browse to find the package checkpoint file.</span></span>  
  
 <span data-ttu-id="377b1-302">**Substituer les options de redémarrage**</span><span class="sxs-lookup"><span data-stu-id="377b1-302">**Override restart options**</span></span>  
 <span data-ttu-id="377b1-303">Sélectionnez cette option pour spécifier les options de redémarrage de cette étape de travail qui sont différentes des options de redémarrage spécifiées dans le package.</span><span class="sxs-lookup"><span data-stu-id="377b1-303">Select this option to specify restart options for this job step that are different from the restart options specified in the package.</span></span>  
  
 <span data-ttu-id="377b1-304">**Option de redémarrage**</span><span class="sxs-lookup"><span data-stu-id="377b1-304">**Restart option**</span></span>  
 <span data-ttu-id="377b1-305">Sélectionnez l'action à appliquer lorsque le package redémarre.</span><span class="sxs-lookup"><span data-stu-id="377b1-305">Select the action to take when the package restarts.</span></span>  
  
### <a name="logging-tab"></a><span data-ttu-id="377b1-306">Onglet Enregistrement</span><span class="sxs-lookup"><span data-stu-id="377b1-306">Logging Tab</span></span>  
 <span data-ttu-id="377b1-307">Sous cet onglet, vous pouvez consulter ou modifier les modules fournisseur d'informations du package.</span><span class="sxs-lookup"><span data-stu-id="377b1-307">View or change the log providers for the package on this tab.</span></span>  
  
 <span data-ttu-id="377b1-308">**Module fournisseur d’informations**</span><span class="sxs-lookup"><span data-stu-id="377b1-308">**Log Provider**</span></span>  
 <span data-ttu-id="377b1-309">Sélectionnez le ClassID du module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="377b1-309">Select the ClassID for the log provider.</span></span>  
  
 <span data-ttu-id="377b1-310">**Chaîne de configuration**</span><span class="sxs-lookup"><span data-stu-id="377b1-310">**Configuration String**</span></span>  
 <span data-ttu-id="377b1-311">Tapez la chaîne de configuration du module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="377b1-311">Type the configuration string for the log provider.</span></span>  
  
 <span data-ttu-id="377b1-312">**Remove**</span><span class="sxs-lookup"><span data-stu-id="377b1-312">**Remove**</span></span>  
 <span data-ttu-id="377b1-313">Supprime le module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="377b1-313">Removes the log provider.</span></span>  
  
### <a name="set-values-tab"></a><span data-ttu-id="377b1-314">Onglet Valeurs définies</span><span class="sxs-lookup"><span data-stu-id="377b1-314">Set Values Tab</span></span>  
 <span data-ttu-id="377b1-315">Sous cet onglet, vous pouvez consulter ou modifier les valeurs des propriétés du package.</span><span class="sxs-lookup"><span data-stu-id="377b1-315">View or change property values for the package on this tab.</span></span>  
  
 <span data-ttu-id="377b1-316">**Chemin de la propriété**</span><span class="sxs-lookup"><span data-stu-id="377b1-316">**Property path**</span></span>  
 <span data-ttu-id="377b1-317">Permet de consulter ou de modifier le chemin d'accès de la propriété.</span><span class="sxs-lookup"><span data-stu-id="377b1-317">View or change the path for the property.</span></span>  
  
 <span data-ttu-id="377b1-318">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="377b1-318">**Value**</span></span>  
 <span data-ttu-id="377b1-319">Permet de consulter ou de modifier la valeur de la propriété.</span><span class="sxs-lookup"><span data-stu-id="377b1-319">View or change the value for the property.</span></span>  
  
 <span data-ttu-id="377b1-320">**Remove**</span><span class="sxs-lookup"><span data-stu-id="377b1-320">**Remove**</span></span>  
 <span data-ttu-id="377b1-321">Supprime la propriété.</span><span class="sxs-lookup"><span data-stu-id="377b1-321">Removes the property.</span></span>  
  
### <a name="verification-tab"></a><span data-ttu-id="377b1-322">Onglet Vérification</span><span class="sxs-lookup"><span data-stu-id="377b1-322">Verification Tab</span></span>  
 <span data-ttu-id="377b1-323">Sous cet onglet, vous pouvez sélectionner les options de vérification pour l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="377b1-323">Select the verification options for the job step on this tab.</span></span>  
  
 <span data-ttu-id="377b1-324">**Exécuter uniquement les packages signés**</span><span class="sxs-lookup"><span data-stu-id="377b1-324">**Execute only signed packages**</span></span>  
 <span data-ttu-id="377b1-325">Exécute uniquement les packages qui ont été signés.</span><span class="sxs-lookup"><span data-stu-id="377b1-325">Run only packages that have been signed.</span></span> <span data-ttu-id="377b1-326">Lorsque cette option est sélectionnée, l'étape du travail échoue si le package n'est pas signé.</span><span class="sxs-lookup"><span data-stu-id="377b1-326">When this option is selected, the job step fails if the package is unsigned.</span></span>  
  
 <span data-ttu-id="377b1-327">**Vérifier la build du package**</span><span class="sxs-lookup"><span data-stu-id="377b1-327">**Verify package build**</span></span>  
 <span data-ttu-id="377b1-328">Exécute uniquement les packages dotés d'un numéro de build spécifique.</span><span class="sxs-lookup"><span data-stu-id="377b1-328">Run only packages with a specific build number.</span></span> <span data-ttu-id="377b1-329">Lorsque cette option est sélectionnée, l'étape du travail échoue si le package n'a pas le numéro de build spécifié.</span><span class="sxs-lookup"><span data-stu-id="377b1-329">When this option is selected, the job step fails if the package does not have the specified build number.</span></span>  
  
 <span data-ttu-id="377b1-330">**Créer**</span><span class="sxs-lookup"><span data-stu-id="377b1-330">**Build**</span></span>  
 <span data-ttu-id="377b1-331">Tapez le numéro de build du package.</span><span class="sxs-lookup"><span data-stu-id="377b1-331">Type the build number of the package.</span></span>  
  
 <span data-ttu-id="377b1-332">**Vérifier l'ID de package**</span><span class="sxs-lookup"><span data-stu-id="377b1-332">**Verify package ID**</span></span>  
 <span data-ttu-id="377b1-333">Exécute uniquement les packages dotés d'un ID spécifique.</span><span class="sxs-lookup"><span data-stu-id="377b1-333">Run only packages with a specific ID.</span></span> <span data-ttu-id="377b1-334">Lorsque cette option est sélectionnée, l'étape du travail échoue si le package n'a pas l'ID spécifié.</span><span class="sxs-lookup"><span data-stu-id="377b1-334">When this option is selected, the job step fails if the package does not have the specified ID.</span></span>  
  
 <span data-ttu-id="377b1-335">**ID du package**</span><span class="sxs-lookup"><span data-stu-id="377b1-335">**Package ID**</span></span>  
 <span data-ttu-id="377b1-336">Tapez l'ID du package.</span><span class="sxs-lookup"><span data-stu-id="377b1-336">Type the package ID.</span></span>  
  
 <span data-ttu-id="377b1-337">**Vérifier l'ID de version**</span><span class="sxs-lookup"><span data-stu-id="377b1-337">**Verify version ID**</span></span>  
 <span data-ttu-id="377b1-338">Exécute uniquement les packages dotés d'un ID de version spécifique.</span><span class="sxs-lookup"><span data-stu-id="377b1-338">Run only packages with a specific version ID.</span></span> <span data-ttu-id="377b1-339">Lorsque cette option est sélectionnée, l'étape du travail échoue si le package n'a pas l'ID de version spécifié.</span><span class="sxs-lookup"><span data-stu-id="377b1-339">When this option is selected, the job step fails if the package does not have the specified version ID.</span></span>  
  
 <span data-ttu-id="377b1-340">**ID de version**</span><span class="sxs-lookup"><span data-stu-id="377b1-340">**Version ID**</span></span>  
 <span data-ttu-id="377b1-341">Tapez l'ID de version.</span><span class="sxs-lookup"><span data-stu-id="377b1-341">Type the version ID.</span></span>  
  
### <a name="command-line-tab"></a><span data-ttu-id="377b1-342">Onglet Ligne de commande</span><span class="sxs-lookup"><span data-stu-id="377b1-342">Command Line Tab</span></span>  
 <span data-ttu-id="377b1-343">Spécifiez les options de ligne de commande du package.</span><span class="sxs-lookup"><span data-stu-id="377b1-343">Specify command-line options for the package.</span></span> <span data-ttu-id="377b1-344">Lorsque vous sélectionnez cet onglet, les options suivantes sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="377b1-344">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="377b1-345">**Restaurer les options d'origine**</span><span class="sxs-lookup"><span data-stu-id="377b1-345">**Restore the original options**</span></span>  
 <span data-ttu-id="377b1-346">Utilise les options de ligne de commande définies dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="377b1-346">Use the command-line options set in this dialog.</span></span>  
  
 <span data-ttu-id="377b1-347">**Modifier la ligne de commande manuellement**</span><span class="sxs-lookup"><span data-stu-id="377b1-347">**Edit the command line manually**</span></span>  
 <span data-ttu-id="377b1-348">Spécifiez les options dans la fenêtre de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="377b1-348">Specify options in the command-line window.</span></span>  
  
 <span data-ttu-id="377b1-349">**Ligne de commande**</span><span class="sxs-lookup"><span data-stu-id="377b1-349">**Command line**</span></span>  
 <span data-ttu-id="377b1-350">Tapez les options de ligne de commande à utiliser pour ce package.</span><span class="sxs-lookup"><span data-stu-id="377b1-350">Type the command line options to use for this package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377b1-351">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="377b1-351">See Also</span></span>  
 <span data-ttu-id="377b1-352">[Gérer les étapes de travail](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="377b1-352">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="377b1-353">[Travaux de SQL Server Agent pour les packages](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span><span class="sxs-lookup"><span data-stu-id="377b1-353">[SQL Server Agent Jobs for Packages](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span></span>  
 [<span data-ttu-id="377b1-354">Administration de l’Agent de réplication</span><span class="sxs-lookup"><span data-stu-id="377b1-354">Replication Agent Administration</span></span>](../../relational-databases/replication/agents/replication-agent-administration.md)  
  
  
