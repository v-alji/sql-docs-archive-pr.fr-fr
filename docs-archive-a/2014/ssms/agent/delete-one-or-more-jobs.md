---
title: Supprimer un ou plusieurs travaux | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, deleting
- dropping jobs
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 67dcdad0-57b2-431c-b77f-4ffc926af93d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 436625f9ad629a6b0e574aa046059f4e7e9c2bf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601262"
---
# <a name="delete-one-or-more-jobs"></a><span data-ttu-id="4d940-102">Supprimer un ou plusieurs travaux</span><span class="sxs-lookup"><span data-stu-id="4d940-102">Delete One or More Jobs</span></span>
  <span data-ttu-id="4d940-103">Cette rubrique explique comment supprimer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] des travaux de l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , de ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="4d940-103">This topic describes how to delete [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4d940-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4d940-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4d940-105">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4d940-105">Security</span></span>  
 <span data-ttu-id="4d940-106">Vous ne pouvez supprimer que les travaux dont vous êtes propriétaire, à moins que vous ne soyez membre du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4d940-106">Unless you are a member of the **sysadmin** fixed server role, you can only delete jobs that you own.</span></span>  
  
 
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="4d940-107">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4d940-107">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="4d940-108">Pour supprimer un travail</span><span class="sxs-lookup"><span data-stu-id="4d940-108">To delete a job</span></span>  
  
1.  <span data-ttu-id="4d940-109">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="4d940-109">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4d940-110">Développez **Agent SQL Server**, développez **Travaux**, cliquez avec le bouton droit sur le travail à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="4d940-110">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="4d940-111">Dans la boîte de dialogue **Supprimer un objet** , confirmez que le travail à supprimer est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4d940-111">In the **Delete Object** dialog box, confirm that the job you intend to delete is selected.</span></span>  
  
4.  <span data-ttu-id="4d940-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d940-112">Click **OK**.</span></span>  
  
#### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="4d940-113">Pour supprimer plusieurs travaux</span><span class="sxs-lookup"><span data-stu-id="4d940-113">To delete multiple jobs</span></span>  
  
1.  <span data-ttu-id="4d940-114">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="4d940-114">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4d940-115">Développez **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4d940-115">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="4d940-116">Cliquez avec le bouton droit sur **moniteur d’activité des travaux**, puis cliquez sur Afficher l’activité du **travail**.</span><span class="sxs-lookup"><span data-stu-id="4d940-116">Right-click **Job Activity Monitor**, and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="4d940-117">Dans le moniteur d’activité des travaux, sélectionnez les travaux à supprimer, cliquez avec le bouton droit sur la sélection, puis choisissez **Supprimer les travaux**.</span><span class="sxs-lookup"><span data-stu-id="4d940-117">In the Job Activity Monitor, select the jobs you want to delete, right-click your selection, and choose **Delete jobs**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="4d940-118">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d940-118">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-job"></a><span data-ttu-id="4d940-119">Pour supprimer un travail</span><span class="sxs-lookup"><span data-stu-id="4d940-119">To delete a job</span></span>  
  
1.  <span data-ttu-id="4d940-120">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d940-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4d940-121">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4d940-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4d940-122">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4d940-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC sp_delete_job  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="4d940-123">Pour plus d’informations, consultez [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4d940-123">For more information, see [sp_delete_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-job-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="4d940-124">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="4d940-124">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-multiple-jobs"></a><span data-ttu-id="4d940-125">Pour supprimer plusieurs travaux</span><span class="sxs-lookup"><span data-stu-id="4d940-125">To delete multiple jobs</span></span>
  
 <span data-ttu-id="4d940-126">Utilisez la classe `JobCollection` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d940-126">Use the `JobCollection` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="4d940-127">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="4d940-127">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
