---
title: Supprimer des travaux | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- delete jobs
ms.assetid: bffb915e-bc84-4417-aa35-183243ca3312
author: stevestein
ms.author: sstein
ms.openlocfilehash: f66387a1334f91c29b8edddad293d76064430b39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705880"
---
# <a name="delete-jobs"></a><span data-ttu-id="b051c-102">travaux, supprimer</span><span class="sxs-lookup"><span data-stu-id="b051c-102">Delete Jobs</span></span>
  <span data-ttu-id="b051c-103">Un travail est constitué d'une série d'opérations spécifiques exécutées de manière séquentielle par l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b051c-103">A job is a specified series of operations performed sequentially by SQL Server Agent.</span></span> <span data-ttu-id="b051c-104">Par défaut, les travaux ne sont pas supprimés lorsque l'exécution se termine.</span><span class="sxs-lookup"><span data-stu-id="b051c-104">By default, jobs are not deleted when execution finishes.</span></span> <span data-ttu-id="b051c-105">Vous pouvez supprimer un ou plusieurs travaux [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent indépendamment de la réussite ou de l'échec du travail.</span><span class="sxs-lookup"><span data-stu-id="b051c-105">You can delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs regardless of success or failure of the job.</span></span> <span data-ttu-id="b051c-106">Vous pouvez également configurer l'Agent [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour supprimer automatiquement des travaux quand ils réussissent, échouent ou s'achèvent.</span><span class="sxs-lookup"><span data-stu-id="b051c-106">You can also configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>  
  
 <span data-ttu-id="b051c-107">Par défaut, les membres du rôle serveur fixe **sysadmin** peuvent exécuter la procédure stockée système [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) pour supprimer un travail.</span><span class="sxs-lookup"><span data-stu-id="b051c-107">By default, members of the **sysadmin** fixed server role can execute the [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql) system stored procedure to delete a job.</span></span> <span data-ttu-id="b051c-108">Les autres utilisateurs doivent disposer de l'un des rôles de base de données fixes suivants de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans la base de données **msdb** :</span><span class="sxs-lookup"><span data-stu-id="b051c-108">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="b051c-109">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="b051c-109">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="b051c-110">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="b051c-110">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="b051c-111">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="b051c-111">**SQLAgentOperatorRole**</span></span>  
  
 <span data-ttu-id="b051c-112">Pour en savoir plus sur les autorisations de ces rôles, consultez [Rôles de base de données fixes de l'Agent SQL Server](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b051c-112">For details about the permissions of these roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="b051c-113">Les membres du rôle serveur fixe **sysadmin** peuvent exécuter **sp_delete_job** pour supprimer un travail.</span><span class="sxs-lookup"><span data-stu-id="b051c-113">Members of the **sysadmin** fixed server role can execute **sp_delete_job** to delete any job.</span></span> <span data-ttu-id="b051c-114">Un utilisateur qui n'est pas membre du rôle serveur fixe **sysadmin** n'a le droit de supprimer que les travaux dont il est propriétaire.</span><span class="sxs-lookup"><span data-stu-id="b051c-114">A user that is not a member of the **sysadmin** fixed server role can only delete jobs owned by that user.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b051c-115">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="b051c-115">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b051c-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="b051c-116">**Description**</span></span>|<span data-ttu-id="b051c-117">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="b051c-117">**Topic**</span></span>|  
|<span data-ttu-id="b051c-118">Explique comment supprimer un ou plusieurs travaux de l'Agent [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b051c-118">Describes how to delete one or more [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>|[<span data-ttu-id="b051c-119">Supprimer un ou plusieurs travaux</span><span class="sxs-lookup"><span data-stu-id="b051c-119">Delete One or More Jobs</span></span>](delete-one-or-more-jobs.md)|  
|<span data-ttu-id="b051c-120">Explique comment configurer l'Agent [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour supprimer automatiquement des travaux quand ils réussissent, échouent ou s'achèvent.</span><span class="sxs-lookup"><span data-stu-id="b051c-120">Describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to automatically delete jobs when they succeed, fail, or complete.</span></span>|[<span data-ttu-id="b051c-121">Automatically Delete a Job</span><span class="sxs-lookup"><span data-stu-id="b051c-121">Automatically Delete a Job</span></span>](automatically-delete-a-job.md)|  
  
  
