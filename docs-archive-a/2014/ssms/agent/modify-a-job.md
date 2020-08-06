---
title: Modifier un travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], modifying
- modifying jobs
- SQL Server Agent jobs, modifying
ms.assetid: dd5e5f20-20c4-4ab9-a19a-db87577dcd43
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0d25830ad119a1f5f344a4dcf318c35bee5f86ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603796"
---
# <a name="modify-a-job"></a><span data-ttu-id="40996-102">Modifier un travail</span><span class="sxs-lookup"><span data-stu-id="40996-102">Modify a Job</span></span>
  <span data-ttu-id="40996-103">Cette rubrique explique comment modifier les propriétés des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] travaux de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , de ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="40996-103">This topic describes how to change the properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="40996-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="40996-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="40996-105">**Avant de commencer :** ,</span><span class="sxs-lookup"><span data-stu-id="40996-105">**Before you begin:** ,</span></span>  
  
     [<span data-ttu-id="40996-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="40996-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="40996-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="40996-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="40996-108">**Pour modifier un travail, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="40996-108">**To modify a job, using:**</span></span>  
  
     [<span data-ttu-id="40996-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="40996-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="40996-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="40996-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="40996-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="40996-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="40996-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="40996-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="40996-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="40996-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="40996-114">Un travail maître [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ne peut pas être ciblé sur des serveurs locaux et distants à la fois.</span><span class="sxs-lookup"><span data-stu-id="40996-114">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="40996-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="40996-115">Security</span></span>  
 <span data-ttu-id="40996-116">Vous pouvez modifier uniquement les travaux dont vous êtes propriétaire, à moins d'être membre du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="40996-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="40996-117">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="40996-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="40996-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="40996-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="40996-119">Pour modifier un travail</span><span class="sxs-lookup"><span data-stu-id="40996-119">To modify a job</span></span>  
  
1.  <span data-ttu-id="40996-120">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="40996-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="40996-121">Développez **SQL Server Agent**et **Travaux**, cliquez avec le bouton droit sur le travail à modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="40996-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="40996-122">Dans la boîte de dialogue **Propriétés du travail** , mettez à jour les propriétés, les étapes, la planification, les alertes et les notifications du travail en utilisant les pages correspondantes.</span><span class="sxs-lookup"><span data-stu-id="40996-122">In the **Job Properties** dialog box, update the job's properties, steps, schedule, alerts, and notifications using the corresponding pages.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="40996-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="40996-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-job"></a><span data-ttu-id="40996-124">Pour modifier un travail</span><span class="sxs-lookup"><span data-stu-id="40996-124">To modify a job</span></span>  
  
1.  <span data-ttu-id="40996-125">Dans l'Explorateur d'objets, connectez-vous à une instance du moteur de base de données et développez-la.</span><span class="sxs-lookup"><span data-stu-id="40996-125">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="40996-126">Dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="40996-126">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="40996-127">Dans la fenêtre de requête, utilisez les procédures stockées système suivantes pour modifier un travail.</span><span class="sxs-lookup"><span data-stu-id="40996-127">In the query window, use the following system stored procedures to modify a job.</span></span>  
  
    -   <span data-ttu-id="40996-128">Exécutez [sp_update_job &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) pour modifier les attributs d’un travail.</span><span class="sxs-lookup"><span data-stu-id="40996-128">Execute [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql) to change the attributes of a job.</span></span>  
  
    -   <span data-ttu-id="40996-129">Exécutez [sp_update_schedule &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) pour modifier les détails de planification d’une définition de travail.</span><span class="sxs-lookup"><span data-stu-id="40996-129">Execute [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql) to change the scheduling details for a job definition.</span></span>  
  
    -   <span data-ttu-id="40996-130">Exécutez [sp_add_jobstep &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) pour ajouter de nouvelles étapes de travail.</span><span class="sxs-lookup"><span data-stu-id="40996-130">Execute [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql) to add new job steps.</span></span>  
  
    -   <span data-ttu-id="40996-131">Exécutez [sp_update_jobstep &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) pour modifier les étapes de travail existantes.</span><span class="sxs-lookup"><span data-stu-id="40996-131">Execute [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) to change pre-existing job steps.</span></span>  
  
    -   <span data-ttu-id="40996-132">Exécutez [sp_delete_jobstep &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) pour supprimer une étape d’un travail.</span><span class="sxs-lookup"><span data-stu-id="40996-132">Execute [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql) to remove a job step from a job.</span></span>  
  
    -   <span data-ttu-id="40996-133">Procédures stockées supplémentaires pour modifier un travail maître de l'Agent SQL Server :</span><span class="sxs-lookup"><span data-stu-id="40996-133">Additional stored procedures to modify any SQL Server Agent master job:</span></span>  
  
        -   <span data-ttu-id="40996-134">Exécutez [sp_delete_jobserver &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) pour supprimer un serveur actuellement associé à un travail.</span><span class="sxs-lookup"><span data-stu-id="40996-134">Execute [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql) to delete a server currently associated with a job.</span></span>  
  
        -   <span data-ttu-id="40996-135">Exécutez [sp_add_jobserver &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) pour associer un serveur au travail en cours.</span><span class="sxs-lookup"><span data-stu-id="40996-135">Execute [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql) to associate a server with the current job.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="40996-136">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="40996-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="40996-137">**Pour modifier un travail**</span><span class="sxs-lookup"><span data-stu-id="40996-137">**To modify a job**</span></span>  
  
 <span data-ttu-id="40996-138">Utilisez la classe `Job` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40996-138">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="40996-139">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="40996-139">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
