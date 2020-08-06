---
title: Démarrer un travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], starting
- SQL Server Agent jobs, starting
- starting jobs
ms.assetid: cec9f7f7-d0a7-4239-9dc5-a69c011ebaa0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d5af895df518a915dacd953331b9139471933aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705852"
---
# <a name="start-a-job"></a><span data-ttu-id="5a0e4-102">Démarrer un travail</span><span class="sxs-lookup"><span data-stu-id="5a0e4-102">Start a Job</span></span>
  <span data-ttu-id="5a0e4-103">Cette rubrique explique comment démarrer l’exécution d’un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] travail de l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-103">This topic describes how to start running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="5a0e4-104">Un travail est une série d'actions exécutées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5a0e4-105">Agent peuvent être exécutés sur un serveur local ou sur plusieurs serveurs distants.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-105">Agent jobs can run on one local server or on multiple remote servers.</span></span>  
  
-   <span data-ttu-id="5a0e4-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5a0e4-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5a0e4-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5a0e4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5a0e4-108">**Pour démarrer un travail, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5a0e4-108">**To start a job, using:**</span></span>  
  
     [<span data-ttu-id="5a0e4-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a0e4-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="5a0e4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5a0e4-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="5a0e4-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="5a0e4-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5a0e4-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5a0e4-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5a0e4-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5a0e4-113">Security</span></span>  
 <span data-ttu-id="5a0e4-114">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="5a0e4-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="5a0e4-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a0e4-115">Using SQL Server Management Studio</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="5a0e4-116">Pour démarrer un travail</span><span class="sxs-lookup"><span data-stu-id="5a0e4-116">To start a job</span></span>  
  
1.  <span data-ttu-id="5a0e4-117">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5a0e4-118">Développez **Agent SQL Server** et développez **Travaux**.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-118">Expand **SQL Server Agent,** and expand **Jobs**.</span></span> <span data-ttu-id="5a0e4-119">Selon la façon dont vous voulez démarrer le travail, procédez de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="5a0e4-119">Depending on how you want the job to start, do one of the following:</span></span>  
  
    -   <span data-ttu-id="5a0e4-120">Si vous travaillez sur un seul serveur, si vous travaillez sur un serveur cible ou si vous exécutez un travail de serveur local sur un serveur maître, cliquez avec le bouton droit sur le travail à démarrer et cliquez sur **Démarrer le travail**.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-120">If you are working on a single server, or working on a target server, or running a local server job on a master server, right-click the job you want to start, and then click **Start Job**.</span></span>  
  
    -   <span data-ttu-id="5a0e4-121">Pour démarrer plusieurs travaux, cliquez avec le bouton droit sur **Moniteur d'activité des travaux**, puis cliquez sur **Afficher l'activité du travail**.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-121">If you want to start multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="5a0e4-122">Dans le Moniteur d'activité des travaux, vous pouvez sélectionner plusieurs travaux. Pour cela, cliquez avec le bouton droit sur votre sélection et cliquez sur **Démarrer les travaux**.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-122">In the Job Activity Monitor you can select multiple jobs, right-click your selection, and click **Start Jobs**.</span></span>  
  
    -   <span data-ttu-id="5a0e4-123">Si vous travaillez sur un serveur maître et souhaitez que tous les serveurs cibles exécutent le travail simultanément, cliquez avec le bouton droit sur le travail à démarrer, cliquez sur **Démarrer le travail**, puis sur **Démarrer sur tous les serveurs cibles**.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-123">If you are working on a master server and want all targeted servers to run the job simultaneously, right-click the job you want to start, click **Start Job**, and then click **Start on all targeted servers**.</span></span>  
  
    -   <span data-ttu-id="5a0e4-124">Si vous travaillez sur un serveur maître et souhaitez spécifier les serveurs cibles pour le travail, cliquez avec le bouton droit sur le travail à démarrer, cliquez sur **Démarrer le travail**, puis sur **Démarrer sur les serveurs cibles spécifiques**.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-124">If you are working on a master server and want to specify target servers for the job, right-click the job you want to start, click **Start Job**, and then click **Start on specific target servers**.</span></span> <span data-ttu-id="5a0e4-125">Dans la boîte de dialogue **Publier les instructions à télécharger** , activez la case à cocher **Serveurs cibles sélectionnés** , puis sélectionnez chacun des serveurs cibles sur lesquels ce travail doit s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-125">In the **Post Download Instructions** dialog box, select the **These target servers** check box, and then select each target server on which this job should run.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="5a0e4-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5a0e4-126">Using Transact-SQL</span></span>  
  
### <a name="to-start-a-job"></a><span data-ttu-id="5a0e4-127">Pour démarrer un travail</span><span class="sxs-lookup"><span data-stu-id="5a0e4-127">To start a job</span></span>  
  
1.  <span data-ttu-id="5a0e4-128">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a0e4-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5a0e4-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5a0e4-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- starts a job named Weekly Sales Data Backup.    
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_start_job N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="5a0e4-131">Pour plus d’informations, consultez [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5a0e4-131">For more information, see [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="5a0e4-132">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="5a0e4-132">Using SQL Server Management Objects</span></span>  

### <a name="to-start-a-job"></a><span data-ttu-id="5a0e4-133">Pour démarrer un travail</span><span class="sxs-lookup"><span data-stu-id="5a0e4-133">To start a job</span></span>
  
 <span data-ttu-id="5a0e4-134">Appelez la méthode `Start` de la classe `Job` à l'aide d'un langage de programmation tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a0e4-134">Call the `Start` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="5a0e4-135">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="5a0e4-135">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
