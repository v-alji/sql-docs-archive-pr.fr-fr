---
title: Utiliser Windows PowerShell dans les étapes de travail de l’Agent SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f25f7549-c9b3-4618-85f2-c9a08adbe0e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8c100e2eaf1f9b706087bd991fbc268540c29a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604594"
---
# <a name="run-windows-powershell-steps-in-sql-server-agent"></a><span data-ttu-id="98ada-102">Utiliser Windows PowerShell dans les étapes de travail de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="98ada-102">Run Windows PowerShell Steps in SQL Server Agent</span></span>
  <span data-ttu-id="98ada-103">Utilisez SQL Server Agent pour exécuter des scripts PowerShell SQL Server à des horaires planifiés.</span><span class="sxs-lookup"><span data-stu-id="98ada-103">Use SQL Server Agent to run SQL Server PowerShell scripts at schedule times.</span></span>  
  
1.  <span data-ttu-id="98ada-104">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="98ada-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="98ada-105">**Pour exécuter PowerShell à partir de SQL Server Agent avec :**  [Étape de travail PowerShell](#PShellJob), [Etape de travail invite de commandes](#CmdExecJob)</span><span class="sxs-lookup"><span data-stu-id="98ada-105">**To run PowerShell from SQL Server Agent, using:**  [PowerShell Job Step](#PShellJob), [Command Prompt Job Step](#CmdExecJob)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="98ada-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="98ada-106">Before You Begin</span></span>  
 <span data-ttu-id="98ada-107">Il y a plusieurs types d'étapes de travail de l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98ada-107">There are several types of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="98ada-108">Chaque type est associé à un sous-système qui implémente un environnement spécifique, tel qu'un agent de réplication ou un environnement d'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="98ada-108">Each type is associated with a subsystem that implements a specific environment, such as a replication agent or command prompt environment.</span></span> <span data-ttu-id="98ada-109">Vous pouvez coder les scripts Windows PowerShell, puis utiliser l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour les inclure dans les travaux qui s'exécutent à des heures planifiées ou en réponse à des événements [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98ada-109">You can code Windows PowerShell scripts, and then use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to include the scripts in jobs that run at scheduled times or in response to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="98ada-110">Les scripts Windows PowerShell peuvent être exécutés à l'aide d'une étape de travail d'invite de commandes ou d'une étape de travail PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98ada-110">Windows PowerShell scripts can be run using either a command prompt job step or a PowerShell job step.</span></span>  
  
1.  <span data-ttu-id="98ada-111">Utilisez une étape du travail PowerShell pour que le sous-système de l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] exécute l'utilitaire `sqlps`, qui lance PowerShell 2.0 et importe le module `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="98ada-111">Use a PowerShell job step to have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent subsystem run the `sqlps` utility, which launches PowerShell 2.0 and imports the `sqlps` module.</span></span>  
  
2.  <span data-ttu-id="98ada-112">Utilisez une étape du travail d'invite de commandes pour exécuter PowerShell.exe et spécifiez un script qui importe le module `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="98ada-112">Use a command prompt job step to run PowerShell.exe, and specify a script that imports the `sqlps` module.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="98ada-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="98ada-113">Limitations and Restrictions</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="98ada-114">Chaque étape de travail de l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] qui exécute PowerShell avec le module `sqlps` lance un processus qui consomme environ 20 Mo de mémoire.</span><span class="sxs-lookup"><span data-stu-id="98ada-114">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job step that runs PowerShell with the `sqlps` module launches a process which consumes approximately 20 MB of memory.</span></span> <span data-ttu-id="98ada-115">L'exécution simultanée d'un grand nombre d'étapes de travail Windows PowerShell peut nuire aux performances.</span><span class="sxs-lookup"><span data-stu-id="98ada-115">Running large numbers of concurrent Windows PowerShell job steps can adversely impact performance.</span></span>  
  
##  <a name="create-a-powershell-job-step"></a><a name="PShellJob"></a><span data-ttu-id="98ada-116">Créer une étape de travail PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ada-116">Create a PowerShell Job Step</span></span>  
 <span data-ttu-id="98ada-117">**Pour créer une étape de travail PowerShell**</span><span class="sxs-lookup"><span data-stu-id="98ada-117">**To create a PowerShell job step**</span></span>  
  
1.  <span data-ttu-id="98ada-118">Développez **SQL Server Agent**, créez un travail ou cliquez avec le bouton droit de la souris sur un travail existant, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="98ada-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="98ada-119">Pour plus d'informations sur la création d'un travail, consultez [Création de travaux](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="98ada-119">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="98ada-120">Dans la boîte de dialogue **Propriétés du travail** , cliquez sur la page **Étapes** , puis sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="98ada-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="98ada-121">Dans la boîte de dialogue **Nouvelle étape du travail** , tapez un **nom d'étape**de travail.</span><span class="sxs-lookup"><span data-stu-id="98ada-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="98ada-122">Dans la liste **Type** , cliquez sur **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="98ada-122">In the **Type** list, click **PowerShell**.</span></span>  
  
5.  <span data-ttu-id="98ada-123">Dans la liste **Exécuter en tant que** , sélectionnez le compte proxy avec les informations d'identification que le travail utilisera.</span><span class="sxs-lookup"><span data-stu-id="98ada-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
6.  <span data-ttu-id="98ada-124">Dans la zone **Commande** , tapez la syntaxe du script PowerShell qui sera exécuté pour l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="98ada-124">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="98ada-125">Vous pouvez aussi cliquer sur **Ouvrir** et sélectionner un fichier contenant la syntaxe du script.</span><span class="sxs-lookup"><span data-stu-id="98ada-125">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
7.  <span data-ttu-id="98ada-126">Cliquez sur la page **Avancé** pour paramétrer les options suivantes pour l'étape de travail : l'action à exécuter si l'étape de travail échoue ou réussit, le nombre de tentatives d'exécution de l'étape de travail que doit effectuer l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et la fréquence de ces tentatives.</span><span class="sxs-lookup"><span data-stu-id="98ada-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="create-a-command-prompt-job-step"></a><a name="CmdExecJob"></a><span data-ttu-id="98ada-127">Créer une étape de travail d’invite de commandes</span><span class="sxs-lookup"><span data-stu-id="98ada-127">Create a Command Prompt Job Step</span></span>  
 <span data-ttu-id="98ada-128">**Pour créer une étape de travail CmdExec**</span><span class="sxs-lookup"><span data-stu-id="98ada-128">**To create a CmdExec job step**</span></span>  
  
1.  <span data-ttu-id="98ada-129">Développez **SQL Server Agent**, créez un travail ou cliquez avec le bouton droit de la souris sur un travail existant, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="98ada-129">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="98ada-130">Pour plus d'informations sur la création d'un travail, consultez [Création de travaux](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="98ada-130">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="98ada-131">Dans la boîte de dialogue **Propriétés du travail** , cliquez sur la page **Étapes** , puis sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="98ada-131">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="98ada-132">Dans la boîte de dialogue **Nouvelle étape du travail** , tapez un **nom d'étape**de travail.</span><span class="sxs-lookup"><span data-stu-id="98ada-132">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="98ada-133">Dans la liste **Type** , choisissez **Système d’exploitation (CmdExec)**.</span><span class="sxs-lookup"><span data-stu-id="98ada-133">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
5.  <span data-ttu-id="98ada-134">Dans la liste **Exécuter en tant que** , sélectionnez le compte proxy avec les informations d'identification que doit utiliser le travail.</span><span class="sxs-lookup"><span data-stu-id="98ada-134">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="98ada-135">Par défaut, les étapes de travail CmdExec s'exécutent dans le contexte du compte de service SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="98ada-135">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
6.  <span data-ttu-id="98ada-136">Dans la zone **Traiter le code de sortie d'une commande réussie** , entrez une valeur comprise entre 0 et 999999.</span><span class="sxs-lookup"><span data-stu-id="98ada-136">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
7.  <span data-ttu-id="98ada-137">Dans la zone **Commande** , entrez powershell.exe avec des paramètres spécifiant le script PowerShell à exécuter.</span><span class="sxs-lookup"><span data-stu-id="98ada-137">In the **Command** box, enter powershell.exe with parameters specifying the PowerShell script to be run.</span></span>  
  
8.  <span data-ttu-id="98ada-138">Cliquez sur la page **Avancé** pour définir les options d'étape de travail, telles que l'action à exécuter lorsque l'étape de travail aboutit ou échoue, le nombre de tentatives d'exécution de l'étape de travail que doit effectuer l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et le fichier où [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] peut écrire la sortie de l'étape de travail.</span><span class="sxs-lookup"><span data-stu-id="98ada-138">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="98ada-139">Seuls les membres du rôle de serveur fixe **sysadmin** peuvent écrire une sortie d'étape de travail dans un fichier du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="98ada-139">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ada-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98ada-140">See Also</span></span>  
 [<span data-ttu-id="98ada-141">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="98ada-141">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
