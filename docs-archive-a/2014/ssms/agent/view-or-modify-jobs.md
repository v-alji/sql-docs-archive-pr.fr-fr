---
title: Afficher ou modifier les travaux | Documents Microsoft
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- jobs [SQL Server Agent], viewing
- modifying jobs
- viewing jobs
- SQL Server Agent jobs, viewing
- SQL Server Agent jobs, modifying
- displaying jobs
ms.assetid: 57f649b8-190c-4304-abd7-7ca5297deab7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d0d731d25c20597be3ac84adfacd8973e4a51cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699138"
---
# <a name="view-or-modify-jobs"></a><span data-ttu-id="0f23d-102">Afficher ou modifier les travaux</span><span class="sxs-lookup"><span data-stu-id="0f23d-102">View or Modify Jobs</span></span>
  <span data-ttu-id="0f23d-103">Vous pouvez afficher tout travail que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="0f23d-103">You can view any job you have created.</span></span> <span data-ttu-id="0f23d-104">Après avoir exécuté un travail, vous pouvez également afficher son historique.</span><span class="sxs-lookup"><span data-stu-id="0f23d-104">After you have run a job, you can also view its history.</span></span> <span data-ttu-id="0f23d-105">L'affichage de l'historique d'un travail vous permet de déterminer le moment de son exécution, l'état du travail dans son ensemble et l'état de chaque étape du travail.</span><span class="sxs-lookup"><span data-stu-id="0f23d-105">Viewing a job's history allows you to see when the job ran, the status of the job as a whole, and the status of each job step in the job.</span></span> <span data-ttu-id="0f23d-106">Il permet également de savoir si le travail a déjà échoué dans le passé, si sa dernière exécution s'est terminée correctement, ainsi que les résultats qu'il a générés à chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="0f23d-106">You can see whether the job ever failed in the past, when the job last completed successfully, and what output the job created each time the job ran.</span></span> <span data-ttu-id="0f23d-107">Les membres du rôle serveur fixe **sysadmin** peuvent afficher ou modifier n’importe quel travail, quel que soit son propriétaire.</span><span class="sxs-lookup"><span data-stu-id="0f23d-107">Members of the **sysadmin** fixed server role can view or modify any job, regardless of the owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f23d-108">Le travail doit avoir été exécuté au moins une fois pour qu'un historique des travaux existe.</span><span class="sxs-lookup"><span data-stu-id="0f23d-108">A job must have been executed at least one time for there to be a job history.</span></span> <span data-ttu-id="0f23d-109">Vous pouvez limiter la taille totale du journal d'historique des travaux et la taille par travail.</span><span class="sxs-lookup"><span data-stu-id="0f23d-109">You can limit the total size of the job history log and the size per job.</span></span>  
  
 <span data-ttu-id="0f23d-110">Enfin, vous pouvez modifier un travail pour qu'il réponde aux nouvelles exigences.</span><span class="sxs-lookup"><span data-stu-id="0f23d-110">Finally, you can modify a job to meet new requirements.</span></span> <span data-ttu-id="0f23d-111">Vous pouvez modifier :</span><span class="sxs-lookup"><span data-stu-id="0f23d-111">You can modify:</span></span>  
  
-   <span data-ttu-id="0f23d-112">les options de réponse ;</span><span class="sxs-lookup"><span data-stu-id="0f23d-112">Response options</span></span>  
  
-   <span data-ttu-id="0f23d-113">Planifications</span><span class="sxs-lookup"><span data-stu-id="0f23d-113">Schedules</span></span>  
  
-   <span data-ttu-id="0f23d-114">Étapes de travail</span><span class="sxs-lookup"><span data-stu-id="0f23d-114">Job steps</span></span>  
  
-   <span data-ttu-id="0f23d-115">Propriété</span><span class="sxs-lookup"><span data-stu-id="0f23d-115">Ownership</span></span>  
  
-   <span data-ttu-id="0f23d-116">la catégorie du travail ;</span><span class="sxs-lookup"><span data-stu-id="0f23d-116">Job category</span></span>  
  
-   <span data-ttu-id="0f23d-117">les serveurs cibles (travaux multiserveur uniquement).</span><span class="sxs-lookup"><span data-stu-id="0f23d-117">Target servers (multiserver jobs only)</span></span>  
  
 <span data-ttu-id="0f23d-118">Pour être certain que les modifications apportées aux travaux multiserveur entrent en vigueur, vous devez les publier dans la liste de téléchargement afin que les serveurs cibles puissent télécharger le travail mis à jour.</span><span class="sxs-lookup"><span data-stu-id="0f23d-118">To make sure that changes to multiserver jobs take effect, you must post the changes to the download list so that target servers can download the updated job.</span></span> <span data-ttu-id="0f23d-119">Pour vérifier que les serveurs cibles possèdent les définitions des travaux les plus récentes, publiez une instruction INSERT une fois le travail multiserveur mis à jour en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="0f23d-119">To ensure that target servers have the most current job definitions, post an INSERT instruction after you update the multiserver job as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="0f23d-120">Pour plus d’informations, consultez [sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0f23d-120">For more information, see [sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql).</span></span>  
  
 <span data-ttu-id="0f23d-121">Les membres du rôle serveur fixe **sysadmin** peuvent afficher la définition ou l’historique de n’importe quel travail, ainsi que modifier tout travail.</span><span class="sxs-lookup"><span data-stu-id="0f23d-121">Members of the **sysadmin** fixed server role can view the definition or history of any job, and can modify any job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0f23d-122">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="0f23d-122">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f23d-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="0f23d-123">**Description**</span></span>|<span data-ttu-id="0f23d-124">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="0f23d-124">**Topic**</span></span>|  
|<span data-ttu-id="0f23d-125">Explique comment afficher des travaux [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0f23d-125">Describes how to view [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="0f23d-126">View a Job</span><span class="sxs-lookup"><span data-stu-id="0f23d-126">View a Job</span></span>](view-a-job.md)|  
|<span data-ttu-id="0f23d-127">Explique comment afficher le journal d’historique des travaux [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0f23d-127">Describes how to view the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="0f23d-128">Afficher l’historique des travaux</span><span class="sxs-lookup"><span data-stu-id="0f23d-128">View the Job History</span></span>](view-the-job-history.md)|  
|<span data-ttu-id="0f23d-129">Explique comment supprimer le contenu du journal d’historique des travaux [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0f23d-129">Describes how to delete the contents of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history log.</span></span>|[<span data-ttu-id="0f23d-130">Effacer le journal d'historique des travaux</span><span class="sxs-lookup"><span data-stu-id="0f23d-130">Clear the Job History Log</span></span>](clear-the-job-history-log.md)|  
|<span data-ttu-id="0f23d-131">Explique comment définir des limites de taille dans les journaux d’historique des travaux [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0f23d-131">Describes how to set size limits for [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job history logs.</span></span>|[<span data-ttu-id="0f23d-132">Resize the Job History Log</span><span class="sxs-lookup"><span data-stu-id="0f23d-132">Resize the Job History Log</span></span>](resize-the-job-history-log.md)|  
|<span data-ttu-id="0f23d-133">Explique comment modifier les propriétés des travaux [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="0f23d-133">Describes how to change the properties of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="0f23d-134">Modifier un travail</span><span class="sxs-lookup"><span data-stu-id="0f23d-134">Modify a Job</span></span>](modify-a-job.md)|  
  
## <a name="see-also"></a><span data-ttu-id="0f23d-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f23d-135">See Also</span></span>  
 [<span data-ttu-id="0f23d-136">dbo.sysjobhistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f23d-136">dbo.sysjobhistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysjobhistory-transact-sql)  
  
  
