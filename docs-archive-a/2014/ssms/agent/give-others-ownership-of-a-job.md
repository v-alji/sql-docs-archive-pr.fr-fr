---
title: Attribuer la propriété d’un travail à d’autres utilisateurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], owners
- owners [SQL Server], jobs
- SQL Server Agent jobs, owners
ms.assetid: 2ded5e9c-4251-4fb1-a047-99f13d150b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2cf03fdc9031ce9761125d95619438837f2959bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600458"
---
# <a name="give-others-ownership-of-a-job"></a><span data-ttu-id="a81b1-102">Attribuer la propriété d'un travail à d'autres utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a81b1-102">Give Others Ownership of a Job</span></span>
  <span data-ttu-id="a81b1-103">Cette rubrique explique comment réassigner la propriété des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] travaux de l’agent à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a81b1-103">This topic describes how to reassign ownership of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to another user.</span></span>  
  
-   <span data-ttu-id="a81b1-104">**Avant de commencer :**  [Limitations et restrictions](#Restrictions), [sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="a81b1-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="a81b1-105">**Pour attribuer la propriété d'un travail à d'autres utilisateurs, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="a81b1-105">**To give others ownership of a job, using:**</span></span>  
  
     [<span data-ttu-id="a81b1-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a81b1-106">SQL Server Management Studio</span></span>](#SSMSProc2)  
  
     [<span data-ttu-id="a81b1-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a81b1-107">Transact-SQL</span></span>](#TsqlProc2)  
  
     [<span data-ttu-id="a81b1-108">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="a81b1-108">SQL Server Management Objects</span></span>](#SMOProc2)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a81b1-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a81b1-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a81b1-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="a81b1-110">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a81b1-111">Pour créer un travail, l'utilisateur doit être membre de l'un des rôles de base de données fixes de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="a81b1-111">To create a job, a user must be a member of one of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="a81b1-112">Un travail ne peut être modifié que par son propriétaire ou par les membres du rôle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="a81b1-112">A job can be edited only by its owner or members of the **sysadmin** role.</span></span> <span data-ttu-id="a81b1-113">Pour plus d’informations sur les rôles de base de données fixe de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, consultez [Rôles de base de données fixe de SQL Server Agent](sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a81b1-113">For more information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles, see [SQL Server Agent Fixed Database Roles](sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="a81b1-114">Vous devez être administrateur système pour modifier le propriétaire d'un travail.</span><span class="sxs-lookup"><span data-stu-id="a81b1-114">You must be a system administrator to change the owner of a job.</span></span>  
  
 <span data-ttu-id="a81b1-115">L'attribution d'un travail à une autre connexion ne garantit pas que le nouveau propriétaire dispose des autorisations nécessaires pour exécuter le travail.</span><span class="sxs-lookup"><span data-stu-id="a81b1-115">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a81b1-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a81b1-116">Security</span></span>  
 <span data-ttu-id="a81b1-117">Pour des raisons de sécurité, seul le propriétaire du travail ou un membre du rôle **sysadmin** peut modifier la définition du travail.</span><span class="sxs-lookup"><span data-stu-id="a81b1-117">For security reasons, only the job owner or a member of the **sysadmin** role can change the definition of the job.</span></span> <span data-ttu-id="a81b1-118">Seuls les membres du rôle serveur fixe **sysadmin** peuvent attribuer la propriété du travail à d'autres utilisateurs et peuvent exécuter n'importe quel travail, quel qu'en soit le propriétaire.</span><span class="sxs-lookup"><span data-stu-id="a81b1-118">Only members of the **sysadmin** fixed server role can assign job ownership to other users, and they can run any job, regardless of the job owner.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a81b1-119">Si vous transférez la propriété d’un travail à un utilisateur qui n’est pas membre du rôle serveur fixe **sysadmin** et que ce travail exécute des étapes qui nécessitent des comptes proxy (par exemple l’exécution de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] ), vérifiez que l’utilisateur en question a accès à ce compte proxy, sinon le travail échouera.</span><span class="sxs-lookup"><span data-stu-id="a81b1-119">If you change job ownership to a user who is not a member of the **sysadmin** fixed server role, and the job is executing job steps that require proxy accounts (for example, [!INCLUDE[ssIS](../../includes/ssis-md.md)] package execution), make sure that the user has access to that proxy account or else the job will fail.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a81b1-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a81b1-120">Permissions</span></span>  
 <span data-ttu-id="a81b1-121">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="a81b1-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProc2"></a> <span data-ttu-id="a81b1-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a81b1-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a81b1-123">**Pour attribuer la propriété d'un travail à d'autres utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="a81b1-123">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="a81b1-124">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="a81b1-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a81b1-125">Développez **SQL Server Agent**, développez **Travaux**, cliquez avec le bouton droit de la souris sur le travail, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="a81b1-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="a81b1-126">Dans la liste **Propriétaire** , sélectionnez une connexion.</span><span class="sxs-lookup"><span data-stu-id="a81b1-126">In the **Owner** list, select a login.</span></span> <span data-ttu-id="a81b1-127">Vous devez être administrateur système pour modifier le propriétaire d'un travail.</span><span class="sxs-lookup"><span data-stu-id="a81b1-127">You must be a system administrator to change the owner of a job.</span></span>  
  
     <span data-ttu-id="a81b1-128">L'attribution d'un travail à une autre connexion ne garantit pas que le nouveau propriétaire dispose des autorisations nécessaires pour exécuter le travail.</span><span class="sxs-lookup"><span data-stu-id="a81b1-128">Assigning a job to another login does not guarantee that the new owner has sufficient permission to run the job successfully.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProc2"></a> <span data-ttu-id="a81b1-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a81b1-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="a81b1-130">**Pour attribuer la propriété d'un travail à d'autres utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="a81b1-130">**To give others ownership of a job**</span></span>  
  
1.  <span data-ttu-id="a81b1-131">Dans l'Explorateur d'objets, connectez-vous à une instance du moteur de base de données et développez-la.</span><span class="sxs-lookup"><span data-stu-id="a81b1-131">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a81b1-132">Dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a81b1-132">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a81b1-133">Dans la fenêtre de requête, entrez les instructions suivantes qui utilisent la procédure stockée système [sp_manage_jobs_by_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="a81b1-133">In the query window, enter the following statements that use the [sp_manage_jobs_by_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-manage-jobs-by-login-transact-sql) system stored procedure.</span></span> <span data-ttu-id="a81b1-134">L'exemple suivant réaffecte tous les travaux de `danw` à `fran??oisa`.</span><span class="sxs-lookup"><span data-stu-id="a81b1-134">The following example reassigns all jobs from `danw` to `fran??oisa`.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_manage_jobs_by_login  
        @action = N'REASSIGN',  
        @current_owner_login_name = N'danw',  
        @new_owner_login_name = N'fran??oisa' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMOProc2"></a><span data-ttu-id="a81b1-135">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="a81b1-135">Using SQL Server Management Objects</span></span>  

### <a name="to-give-others-ownership-of-a-job"></a><span data-ttu-id="a81b1-136">Pour attribuer la propriété d'un travail à d'autres utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a81b1-136">To give others ownership of a job</span></span>
  
1.  <span data-ttu-id="a81b1-137">Appelez la classe `Job` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a81b1-137">Call the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="a81b1-138">Pour obtenir un exemple de code, consultez [Planification des tâches administratives automatiques dans l’Agent SQL Server](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="a81b1-138">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a81b1-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a81b1-139">See Also</span></span>  
 <span data-ttu-id="a81b1-140">[Implémenter des travaux](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="a81b1-140">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="a81b1-141">Créer des travaux</span><span class="sxs-lookup"><span data-stu-id="a81b1-141">Create Jobs</span></span>](create-jobs.md)  
