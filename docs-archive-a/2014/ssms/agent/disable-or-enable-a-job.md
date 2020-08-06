---
title: Activer ou désactiver un travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- stopping jobs
- disabling jobs
- SQL Server Agent jobs, disabling
- jobs [SQL Server Agent], disabling
ms.assetid: 5041261f-0c32-4d4a-8bee-59a6c16200dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42fe7cbeed1e2ff3f93b1afef52b165a7d660ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600471"
---
# <a name="disable-or-enable-a-job"></a><span data-ttu-id="5a647-102">Activer ou désactiver un travail</span><span class="sxs-lookup"><span data-stu-id="5a647-102">Disable or Enable a Job</span></span>
  <span data-ttu-id="5a647-103">Cette rubrique explique comment désactiver un travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a647-103">This topic describes how to disable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5a647-104">Lorsque vous désactivez un travail, celui-ci n'est pas supprimé et peut être éventuellement réactivé.</span><span class="sxs-lookup"><span data-stu-id="5a647-104">When you disable a job, it is not deleted and can be enabled again when necessary.</span></span>  
  
 <span data-ttu-id="5a647-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5a647-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5a647-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5a647-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5a647-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5a647-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5a647-108">**Pour activer ou désactiver un travail, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5a647-108">**To disable or enable a job, using:**</span></span>  
  
     [<span data-ttu-id="5a647-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a647-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="5a647-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5a647-110">Transact-SQL</span></span>](#TSQL)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5a647-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5a647-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5a647-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5a647-112">Security</span></span>  
 <span data-ttu-id="5a647-113">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="5a647-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="5a647-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a647-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="5a647-115">Pour activer ou désactiver un travail</span><span class="sxs-lookup"><span data-stu-id="5a647-115">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="5a647-116">Dans **l’Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], puis développez-la.</span><span class="sxs-lookup"><span data-stu-id="5a647-116">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5a647-117">Développez **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="5a647-117">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="5a647-118">Développez **Travaux**, puis cliquez avec le bouton droit sur le travail à désactiver ou à activer.</span><span class="sxs-lookup"><span data-stu-id="5a647-118">Expand **Jobs**, and then right-click the job that you want to disable or enable.</span></span>  
  
4.  <span data-ttu-id="5a647-119">Pour désactiver un travail, cliquez sur **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="5a647-119">To disable a job, click **Disable**.</span></span> <span data-ttu-id="5a647-120">Pour activer un travail, cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="5a647-120">To enable a job, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="5a647-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5a647-121">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-job"></a><span data-ttu-id="5a647-122">Pour activer ou désactiver un travail</span><span class="sxs-lookup"><span data-stu-id="5a647-122">To disable or enable a job</span></span>  
  
1.  <span data-ttu-id="5a647-123">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a647-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5a647-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5a647-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5a647-125">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5a647-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the name, description, and enables status of the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @new_name = N'NightlyBackups -- Disabled',  
        @description = N'Nightly backups disabled during server migration.',  
        @enabled = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="5a647-126">Pour plus d’informations, consultez [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5a647-126">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
