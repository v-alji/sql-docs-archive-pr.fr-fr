---
title: Arrêter un travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
ms.assetid: 4249328a-24d8-4284-9d1d-7d04ed90e3d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 78986e85dd8ee808f5fb621182d903a94bbc5eb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695247"
---
# <a name="stop-a-job"></a><span data-ttu-id="d017e-102">Arrêter un travail</span><span class="sxs-lookup"><span data-stu-id="d017e-102">Stop a Job</span></span>
  <span data-ttu-id="d017e-103">Cette rubrique explique comment arrêter un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] travail de l’agent.</span><span class="sxs-lookup"><span data-stu-id="d017e-103">This topic describes how to stop a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="d017e-104">Un travail est une suite d'actions effectuées par SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="d017e-104">A job is a specified series of actions that SQL Server Agent performs.</span></span>  
  
-   <span data-ttu-id="d017e-105">**Avant de commencer :** ,</span><span class="sxs-lookup"><span data-stu-id="d017e-105">**Before you begin:**  ,</span></span>  
  
     [<span data-ttu-id="d017e-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d017e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d017e-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d017e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d017e-108">**Pour arrêter un travail, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="d017e-108">**To stop a job, using:**</span></span>  
  
     [<span data-ttu-id="d017e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d017e-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="d017e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d017e-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="d017e-111">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d017e-111">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d017e-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d017e-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d017e-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d017e-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d017e-114">Si un travail exécute une étape de type **CmdExec** ou **PowerShell**, le processus en cours d’exécution (par exemple, MyProgram.exe) est obligé de s’arrêter prématurément.</span><span class="sxs-lookup"><span data-stu-id="d017e-114">If a job is currently executing a step of type **CmdExec** or **PowerShell**, the process that is being run (for example, MyProgram.exe) is forced to end prematurely.</span></span> <span data-ttu-id="d017e-115">Cela peut provoquer un comportement imprévisible ; par exemple, des fichiers utilisés par le processus peuvent être laissés ouverts.</span><span class="sxs-lookup"><span data-stu-id="d017e-115">This can cause unpredictable behavior, such as files that are being used by the process being held open.</span></span>  
  
-   <span data-ttu-id="d017e-116">Dans le cas d'un travail multiserveur, une instruction STOP pour le travail est envoyée à tous les serveurs cibles du travail.</span><span class="sxs-lookup"><span data-stu-id="d017e-116">For a multiserver job, a STOP instruction for the job is posted to all target servers of the job.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d017e-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d017e-117">Security</span></span>  
 <span data-ttu-id="d017e-118">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="d017e-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="d017e-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d017e-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-stop-a-job"></a><span data-ttu-id="d017e-120">Pour arrêter un travail</span><span class="sxs-lookup"><span data-stu-id="d017e-120">To stop a job</span></span>  
  
1.  <span data-ttu-id="d017e-121">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="d017e-121">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d017e-122">Développez **SQL Server Agent**, **Travaux**, cliquez avec le bouton droit sur le travail à arrêter, puis cliquez sur **Arrêter le travail**.</span><span class="sxs-lookup"><span data-stu-id="d017e-122">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to stop, and then click **Stop Job**.</span></span>  
  
3.  <span data-ttu-id="d017e-123">Pour arrêter plusieurs travaux, cliquez avec le bouton droit sur **Moniteur d’activité des travaux**, puis cliquez sur **Afficher l’activité du travail**.</span><span class="sxs-lookup"><span data-stu-id="d017e-123">If you want to stop multiple jobs, right-click **Job Activity Monitor**, and then click **View Job Activity**.</span></span> <span data-ttu-id="d017e-124">Dans le Moniteur d’activité des travaux, sélectionnez les travaux à arrêter, cliquez avec le bouton droit sur votre sélection, puis cliquez sur **Arrêter les travaux**.</span><span class="sxs-lookup"><span data-stu-id="d017e-124">In the Job Activity Monitor, select the jobs you want to stop, right-click your selection, and then click **Stop Jobs**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="d017e-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d017e-125">Using Transact-SQL</span></span>  
  
### <a name="to-stop-a-job"></a><span data-ttu-id="d017e-126">Pour arrêter un travail</span><span class="sxs-lookup"><span data-stu-id="d017e-126">To stop a job</span></span>  
  
1.  <span data-ttu-id="d017e-127">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d017e-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d017e-128">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d017e-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d017e-129">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d017e-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- stops a job named Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_stop_job  
        N'Weekly Sales Data Backup' ;  
    GO  
    ```  
  
 <span data-ttu-id="d017e-130">Pour plus d’informations, consultez [sp_stop_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d017e-130">For more information, see [sp_stop_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-stop-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="d017e-131">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d017e-131">Using SQL Server Management Objects</span></span>  

### <a name="to-stop-a-job"></a><span data-ttu-id="d017e-132">Pour arrêter un travail</span><span class="sxs-lookup"><span data-stu-id="d017e-132">To stop a job</span></span>
  
 <span data-ttu-id="d017e-133">Appelez la méthode `Stop` de la classe `Job` à l'aide d'un langage de programmation tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d017e-133">Call the `Stop` method of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="d017e-134">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="d017e-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
