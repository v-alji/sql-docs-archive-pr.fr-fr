---
title: Afficher l’historique des travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- viewing job history
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
- displaying job history
ms.assetid: 3bbd1556-abdb-48a3-b249-546eace76343
author: stevestein
ms.author: sstein
ms.openlocfilehash: e84fafdaeddb5748a8129cd5d71d667db7e5fa37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703724"
---
# <a name="view-the-job-history"></a><span data-ttu-id="a5976-102">Afficher l'historique des travaux</span><span class="sxs-lookup"><span data-stu-id="a5976-102">View the Job History</span></span>
  <span data-ttu-id="a5976-103">Cette rubrique explique comment afficher le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Journal d’historique des travaux de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , de ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="a5976-103">This topic describes how to view the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="a5976-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="a5976-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a5976-105">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a5976-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a5976-106">**Pour afficher le journal d'historique des travaux, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="a5976-106">**To view the job history log, using:**</span></span>  
  
     [<span data-ttu-id="a5976-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a5976-107">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="a5976-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a5976-108">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="a5976-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="a5976-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a5976-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a5976-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a5976-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a5976-111">Security</span></span>  
 <span data-ttu-id="a5976-112">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="a5976-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="a5976-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a5976-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="a5976-114">Pour afficher le journal d'historique des travaux</span><span class="sxs-lookup"><span data-stu-id="a5976-114">To view the job history log</span></span>  
  
1.  <span data-ttu-id="a5976-115">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="a5976-115">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a5976-116">Développez **SQL Server Agent**, puis **Travaux**.</span><span class="sxs-lookup"><span data-stu-id="a5976-116">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="a5976-117">Cliquez avec le bouton droit sur un travail, puis cliquez sur **Afficher l’historique**.</span><span class="sxs-lookup"><span data-stu-id="a5976-117">Right-click a job, and then click **View History**.</span></span>  
  
4.  <span data-ttu-id="a5976-118">Dans la visionneuse du fichier journal, consultez l'historique des travaux.</span><span class="sxs-lookup"><span data-stu-id="a5976-118">In the Log File Viewer, view the job history.</span></span>  
  
5.  <span data-ttu-id="a5976-119">Pour mettre à jour l'historique des travaux, cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="a5976-119">To update the job history, click **Refresh**.</span></span> <span data-ttu-id="a5976-120">Pour réduire le nombre de lignes affichées, cliquez sur le bouton **Filtre** , puis définissez les paramètres de filtrage.</span><span class="sxs-lookup"><span data-stu-id="a5976-120">To view fewer rows, click the **Filter** button and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="a5976-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a5976-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-job-history-log"></a><span data-ttu-id="a5976-122">Pour afficher le journal d'historique des travaux</span><span class="sxs-lookup"><span data-stu-id="a5976-122">To view the job history log</span></span>  
  
1.  <span data-ttu-id="a5976-123">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5976-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a5976-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a5976-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a5976-125">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a5976-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all job information for the NightlyBackups job.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobhistory   
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
 <span data-ttu-id="a5976-126">Pour plus d’informations, consultez [sp_help_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a5976-126">For more information, see [sp_help_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobhistory-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="a5976-127">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="a5976-127">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="a5976-128">**Pour afficher le journal d'historique des travaux**</span><span class="sxs-lookup"><span data-stu-id="a5976-128">**To view the job history log**</span></span>  
  
 <span data-ttu-id="a5976-129">Appelez la méthode `EnumHistory` de la classe `Job` à l'aide d'un langage de programmation tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5976-129">Call the `EnumHistory` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="a5976-130">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="a5976-130">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
