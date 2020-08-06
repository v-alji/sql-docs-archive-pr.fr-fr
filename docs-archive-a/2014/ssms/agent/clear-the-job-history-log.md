---
title: Effacer le journal d’historique des travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- clearing job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 34b9398a-c409-4040-8ea1-0deceb18f961
author: stevestein
ms.author: sstein
ms.openlocfilehash: 813c2c7c86a769eea09a093f2de999460d78ef54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614335"
---
# <a name="clear-the-job-history-log"></a><span data-ttu-id="4102a-102">Effacer le journal d'historique des travaux</span><span class="sxs-lookup"><span data-stu-id="4102a-102">Clear the Job History Log</span></span>
  <span data-ttu-id="4102a-103">Cette rubrique explique comment supprimer le contenu du journal d' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] historique des travaux de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , de ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="4102a-103">This topic describes how to delete the contents of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="4102a-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="4102a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4102a-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="4102a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4102a-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4102a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4102a-107">**Pour effacer le journal d'historique des travaux, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="4102a-107">**To clear the job history log, using:**</span></span>  
  
     [<span data-ttu-id="4102a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4102a-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="4102a-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4102a-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="4102a-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="4102a-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4102a-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4102a-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4102a-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4102a-112">Security</span></span>  
 <span data-ttu-id="4102a-113">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="4102a-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="4102a-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4102a-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="4102a-115">Pour effacer le journal d'historique des travaux</span><span class="sxs-lookup"><span data-stu-id="4102a-115">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="4102a-116">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="4102a-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4102a-117">Développez **SQL Server Agent**, puis **Travaux**.</span><span class="sxs-lookup"><span data-stu-id="4102a-117">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="4102a-118">Cliquez avec le bouton droit sur un travail, puis cliquez sur **Afficher l’historique**.</span><span class="sxs-lookup"><span data-stu-id="4102a-118">Right-click a job and click **View history**.</span></span>  
  
4.  <span data-ttu-id="4102a-119">Dans la **Visionneuse du fichier journal**, sélectionnez le travail pour lequel vous souhaitez effacer l'historique, puis effectuez une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4102a-119">In the **Log File Viewer**, select the job for which you want to clear history, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="4102a-120">Cliquez sur **Supprimer**, puis sur **Supprimer tout l'historique** dans la boîte de dialogue **Supprimer l'historique** .</span><span class="sxs-lookup"><span data-stu-id="4102a-120">Click **Delete**, and then click **Delete all history** in the **Delete History** dialog.</span></span> <span data-ttu-id="4102a-121">Vous pouvez supprimer tous les historique ou uniquement celui qui est antérieur à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="4102a-121">You can delete all job history or only history that is older than a specified date.</span></span> <span data-ttu-id="4102a-122">Si vous souhaitez supprimer tout l'historique, cliquez sur **Supprimer tout l'historique**.</span><span class="sxs-lookup"><span data-stu-id="4102a-122">If you want to remove all job history, click **Delete all history**.</span></span> <span data-ttu-id="4102a-123">Si vous souhaitez supprimer uniquement les historiques anciens, cliquez sur **Supprimer l'historique avant**et spécifiez une date.</span><span class="sxs-lookup"><span data-stu-id="4102a-123">If you only want to remove older job history logs, click **Delete history before**, and then specify a date.</span></span>  
  
    -   <span data-ttu-id="4102a-124">Cliquez sur **État du travail** si vous souhaitez effacer l'historique d'un travail multiserveur.</span><span class="sxs-lookup"><span data-stu-id="4102a-124">Click **Job status** if you want to clear the history log of a multiserver job.</span></span> <span data-ttu-id="4102a-125">Cliquez sur **Travail**, puis sur un nom de travail et enfin sur **Afficher l'historique des travaux distants**.</span><span class="sxs-lookup"><span data-stu-id="4102a-125">Click **Job**, click a job name, and then click **View Remote Job History**.</span></span>  
  
5.  <span data-ttu-id="4102a-126">Cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="4102a-126">Click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="4102a-127">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4102a-127">Using Transact-SQL</span></span>  
  
#### <a name="to-clear-the-job-history-log"></a><span data-ttu-id="4102a-128">Pour effacer le journal d'historique des travaux</span><span class="sxs-lookup"><span data-stu-id="4102a-128">To clear the job history log</span></span>  
  
1.  <span data-ttu-id="4102a-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4102a-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4102a-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4102a-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4102a-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4102a-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- example removes the history for a job named NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_purge_jobhistory  
        @job_name = N'NightlyBackups' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="4102a-132">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="4102a-132">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="4102a-133">**Pour effacer le journal d'historique des travaux**</span><span class="sxs-lookup"><span data-stu-id="4102a-133">**To clear the job history log**</span></span>  
  
 <span data-ttu-id="4102a-134">Utilisez la méthode `PurgeJobHistory` de la classe `JobServer` à l'aide d'un langage de programmation tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4102a-134">Use the `PurgeJobHistory` method of the `JobServer` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="4102a-135">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="4102a-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
