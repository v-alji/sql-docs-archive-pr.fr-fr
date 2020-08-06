---
title: Gérer des travaux à l’échelle d’une entreprise | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver job management [SQL Server]
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
- target servers [SQL Server], job changes
ms.assetid: 4fe7f6c6-f89b-4430-979c-4994a5dcf7a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 385435302b2e987c86afb17eaebf90e91bc93e56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603799"
---
# <a name="manage-jobs-across-an-enterprise"></a><span data-ttu-id="97c5d-102">Gérer des travaux à l'échelle d'une entreprise</span><span class="sxs-lookup"><span data-stu-id="97c5d-102">Manage Jobs Across an Enterprise</span></span>
  <span data-ttu-id="97c5d-103">Si vous apportez des modifications à des définitions de travaux multiserveur en dehors de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , vous devez poster les modifications dans la liste de téléchargement afin que les serveurs cibles puissent télécharger à nouveau le travail mis à jour.</span><span class="sxs-lookup"><span data-stu-id="97c5d-103">If you make changes to multiserver job definitions outside [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must post the changes to the download list so that target servers can download the updated job again.</span></span> <span data-ttu-id="97c5d-104">Pour vous assurer que les serveurs cibles possèdent les définitions des travaux les plus récentes, publiez une instruction INSERT après avoir mis à jour les travaux multiserveur. Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="97c5d-104">To ensure that target servers have current job definitions, post an INSERT instruction after you update the multiserver job, as follows:</span></span>  
  
```  
EXECUTE sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="97c5d-105">Pour notifier les serveurs cibles qu'un travail multiserveur a été modifié, vous devez appeler la commande précédente après avoir utilisé l'une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="97c5d-105">To notify target servers that a multiserver job has been modified, you must invoke the preceding command after using any of the following procedures:</span></span>  
  
-   [<span data-ttu-id="97c5d-106">sp_add_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="97c5d-106">sp_add_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql)  
  
-   [<span data-ttu-id="97c5d-107">sp_update_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="97c5d-107">sp_update_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql)  
  
-   [<span data-ttu-id="97c5d-108">sp_delete_jobstep (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="97c5d-108">sp_delete_jobstep (Transact-SQL)</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql)  
  
-   [<span data-ttu-id="97c5d-109">sp_attach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="97c5d-109">sp_attach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql)  
  
-   [<span data-ttu-id="97c5d-110">sp_detach_schedule &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="97c5d-110">sp_detach_schedule &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-schedule-transact-sql)  
  
    > [!NOTE]  
    >  <span data-ttu-id="97c5d-111">Il n'est pas nécessaire d'appeler **sp_post_msx_operation** après avoir appelé **sp_update_job** ou **sp_delete_job**, car ces procédures stockées publient automatiquement les modifications nécessaires dans la liste de téléchargements.</span><span class="sxs-lookup"><span data-stu-id="97c5d-111">It is not necessary to call **sp_post_msx_operation** after you call **sp_update_job** or **sp_delete_job**, because these stored procedures post the required changes to the download list automatically.</span></span>  
  
 <span data-ttu-id="97c5d-112">Ci-dessous figurent des tâches courantes permettant de gérer les travaux à l'échelle d'une entreprise :</span><span class="sxs-lookup"><span data-stu-id="97c5d-112">The following are common tasks for managing jobs across an enterprise:</span></span>  
  
 <span data-ttu-id="97c5d-113">**Pour vérifier l'état d'un serveur cible**</span><span class="sxs-lookup"><span data-stu-id="97c5d-113">**To check the status of a target server**</span></span>  
  
-   [<span data-ttu-id="97c5d-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97c5d-114">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-targetserver-transact-sql)  
  
-   [<span data-ttu-id="97c5d-115">SMO (SQL Server Management Objects)</span><span class="sxs-lookup"><span data-stu-id="97c5d-115">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="97c5d-116">**Pour modifier les serveurs cibles associés à un travail**</span><span class="sxs-lookup"><span data-stu-id="97c5d-116">**To change the target servers for a job**</span></span>  
  
-   [<span data-ttu-id="97c5d-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97c5d-117">SQL Server Management Studio</span></span>](modify-the-target-servers-for-a-job.md)  
  
-   [<span data-ttu-id="97c5d-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97c5d-118">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql)  
  
-   [<span data-ttu-id="97c5d-119">SMO (SQL Server Management Objects)</span><span class="sxs-lookup"><span data-stu-id="97c5d-119">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="97c5d-120">**Pour modifier l'emplacement d'un serveur cible**</span><span class="sxs-lookup"><span data-stu-id="97c5d-120">**To change the location of a target server**</span></span>  
  
-   [<span data-ttu-id="97c5d-121">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97c5d-121">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="97c5d-122">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97c5d-122">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)  
  
-   [<span data-ttu-id="97c5d-123">SMO (SQL Server Management Objects)</span><span class="sxs-lookup"><span data-stu-id="97c5d-123">SQL Server Management Objects (SMO)</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
 <span data-ttu-id="97c5d-124">**Pour synchroniser les horloges des serveurs cibles**</span><span class="sxs-lookup"><span data-stu-id="97c5d-124">**To synchronize target server clocks**</span></span>  
  
-   [<span data-ttu-id="97c5d-125">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97c5d-125">SQL Server Management Studio</span></span>](synchronize-target-server-clocks-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="97c5d-126">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97c5d-126">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql)  
  
 <span data-ttu-id="97c5d-127">**Pour forcer l'interrogation d'un serveur maître par un serveur cible**</span><span class="sxs-lookup"><span data-stu-id="97c5d-127">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="97c5d-128">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97c5d-128">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="97c5d-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97c5d-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="97c5d-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97c5d-130">See Also</span></span>  
 [<span data-ttu-id="97c5d-131">Gérer les événements</span><span class="sxs-lookup"><span data-stu-id="97c5d-131">Manage Events</span></span>](manage-events.md)  
  
  
