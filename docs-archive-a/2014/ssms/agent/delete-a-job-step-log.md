---
title: Supprimer un journal d’étapes de travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [SQL Server Agent]
- deleting job step logs
- logs [SQL Server], jobs
- removing job step logs
ms.assetid: ee20c6cd-0258-4550-bdb0-71e86a0fb330
author: stevestein
ms.author: sstein
ms.openlocfilehash: de7c64c4d7cf461eef563ae6989e043d125c6f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610951"
---
# <a name="delete-a-job-step-log"></a><span data-ttu-id="f0472-102">Supprimer un journal d’étapes de travail</span><span class="sxs-lookup"><span data-stu-id="f0472-102">Delete a Job Step Log</span></span>
  <span data-ttu-id="f0472-103">Cette rubrique explique comment supprimer un journal d'étapes de travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0472-103">This topic describes how to delete a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step log.</span></span>  
  
-   <span data-ttu-id="f0472-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f0472-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f0472-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f0472-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f0472-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0472-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f0472-107">**Pour supprimer un journal d'étapes de travail de SQL Server Agent, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="f0472-107">**To delete a SQL Server Agent job step log, using:**</span></span>  
  
     [<span data-ttu-id="f0472-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0472-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="f0472-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0472-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="f0472-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="f0472-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f0472-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f0472-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f0472-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f0472-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f0472-113">Lorsque des étapes de travail sont supprimées, leur journal de sortie est automatiquement supprimé.</span><span class="sxs-lookup"><span data-stu-id="f0472-113">When job steps are deleted their output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f0472-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0472-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f0472-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f0472-115">Permissions</span></span>  
 <span data-ttu-id="f0472-116">Vous pouvez modifier uniquement les travaux dont vous êtes propriétaire, à moins d'être membre du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f0472-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="f0472-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0472-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="f0472-118">Pour supprimer un journal d'étapes de travail de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f0472-118">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="f0472-119">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="f0472-119">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f0472-120">Développez **SQL Server Agent**et **Travaux**, cliquez avec le bouton droit sur le travail à modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f0472-120">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f0472-121">Dans la boîte de dialogue **Propriétés du travail** , supprimez l'étape de travail sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f0472-121">In the **Job Properties** dialog box, delete the selected job step.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="f0472-122">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0472-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a><span data-ttu-id="f0472-123">Pour supprimer un journal d'étapes de travail de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f0472-123">To delete a SQL Server Agent job step log</span></span>  
  
1.  <span data-ttu-id="f0472-124">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0472-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0472-125">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f0472-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0472-126">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f0472-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- removes the job step log for step 2 in the job Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobsteplog  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 2;  
    GO  
    ```  
  
 <span data-ttu-id="f0472-127">Pour plus d’informations, consultez [sp_delete_jobsteplog &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0472-127">For more information, see [sp_delete_jobsteplog &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="f0472-128">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="f0472-128">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="f0472-129">Utilisez les méthodes `DeleteJobStepLogs` de la classe `Job` à l'aide d'un langage de programmation tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0472-129">Use the `DeleteJobStepLogs` methods of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="f0472-130">Pour plus d’informations, consultez[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="f0472-130">For more information, see[SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
```powershell
# Delete all job step log files that have ID values larger than 5.  
$srv = New-Object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = $srv.JobServer.Jobs["Test Job"]  
$jb.DeleteJobStepLogs(5)  
```
