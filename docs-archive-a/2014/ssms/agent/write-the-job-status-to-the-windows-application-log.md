---
title: Écrire l’état du travail dans le journal des applications Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- SQL Server Agent jobs, status
- writing job status to log
- jobs [SQL Server Agent], status
- logs [SQL Server], jobs
ms.assetid: 3b813702-8f61-40ec-bf3b-ce9deb7e68be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67bdd7948d1722e49976d5e48b571c684431cd1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703715"
---
# <a name="write-the-job-status-to-the-windows-application-log"></a><span data-ttu-id="1384f-102">Write the Job Status to the Windows Application Log</span><span class="sxs-lookup"><span data-stu-id="1384f-102">Write the Job Status to the Windows Application Log</span></span>
  <span data-ttu-id="1384f-103">Cette rubrique explique comment configurer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pour écrire l’état du travail dans le journal des événements des applications Windows à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , de [!INCLUDE[tsql](../../includes/tsql-md.md)] ou de SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="1384f-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to write job status to the Windows application event log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="1384f-104">Les réponses à un travail garantissent que les administrateurs de base de données ont connaissance de l'achèvement des travaux et de leur fréquence d'exécution.</span><span class="sxs-lookup"><span data-stu-id="1384f-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="1384f-105">Les réponses classiques à un travail peuvent être :</span><span class="sxs-lookup"><span data-stu-id="1384f-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="1384f-106">Une notification de l’opérateur, à l’aide de l’e-mail, de la radiomessagerie ou d’un message **net send** .</span><span class="sxs-lookup"><span data-stu-id="1384f-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span> <span data-ttu-id="1384f-107">Utilisez une de ces réponses à un travail si l'opérateur doit exécuter une action en conséquence.</span><span class="sxs-lookup"><span data-stu-id="1384f-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="1384f-108">Par exemple, si un travail de sauvegarde se termine avec succès, l'opérateur doit être averti afin qu'il enlève la bande de sauvegarde et qu'il la mette en lieu sûr.</span><span class="sxs-lookup"><span data-stu-id="1384f-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="1384f-109">L'écriture d'un message d'événement dans le journal des applications Windows.</span><span class="sxs-lookup"><span data-stu-id="1384f-109">Writing an event message to the Windows application log.</span></span> <span data-ttu-id="1384f-110">Vous pouvez choisir d'utiliser cette réponse uniquement en cas d'échec des travaux.</span><span class="sxs-lookup"><span data-stu-id="1384f-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="1384f-111">La suppression automatique du travail.</span><span class="sxs-lookup"><span data-stu-id="1384f-111">Automatically deleting the job.</span></span> <span data-ttu-id="1384f-112">Utilisez cette réponse à un travail si vous êtes certain de ne plus avoir besoin d'exécuter ce travail à nouveau.</span><span class="sxs-lookup"><span data-stu-id="1384f-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="1384f-113">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="1384f-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1384f-114">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="1384f-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1384f-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="1384f-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1384f-116">**Pour écrire l'état du travail dans le journal des applications Windows, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="1384f-116">**To write the job status to the Windows application log, using:**</span></span>  
  
     [<span data-ttu-id="1384f-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1384f-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="1384f-118">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="1384f-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1384f-119">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="1384f-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1384f-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="1384f-120">Security</span></span>  
 <span data-ttu-id="1384f-121">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="1384f-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="1384f-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1384f-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="1384f-123">Pour écrire l'état du travail dans le journal des applications Windows</span><span class="sxs-lookup"><span data-stu-id="1384f-123">To write job status to the Windows application log</span></span>  
  
1.  <span data-ttu-id="1384f-124">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="1384f-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1384f-125">Développez **Agent SQL Server**, développez **Travaux**, cliquez avec le bouton droit sur le travail que vous souhaitez modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="1384f-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="1384f-126">Sélectionnez la page **Notifications** .</span><span class="sxs-lookup"><span data-stu-id="1384f-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="1384f-127">Activez **Écrire dans le journal des événements des applications Windows**, puis choisissez :</span><span class="sxs-lookup"><span data-stu-id="1384f-127">Check **Write to Windows application event log**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="1384f-128">Cliquez sur**Lors de la réussite du travail**pour inscrire l’état du travail à la fin du travail.</span><span class="sxs-lookup"><span data-stu-id="1384f-128">Click**When the job succeeds**to log the job status when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="1384f-129">Cliquez sur**Lors de l’échec du travail**pour inscrire l’état du travail une fois qu’il a échoué.</span><span class="sxs-lookup"><span data-stu-id="1384f-129">Click**When the job fails**to log the job status when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="1384f-130">Cliquez sur**Lorsque le travail est terminé** pour inscrire l’état du travail quelle que soit la manière dont il s’est terminé.</span><span class="sxs-lookup"><span data-stu-id="1384f-130">Click**When the job completes** to log the job status regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="1384f-131">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="1384f-131">Using SQL Server Management Objects</span></span>  

### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="1384f-132">Pour écrire l'état du travail dans le journal des applications Windows</span><span class="sxs-lookup"><span data-stu-id="1384f-132">To write job status to the Windows application log</span></span>
  
 <span data-ttu-id="1384f-133">Appelez la propriété `EventLogLevel` de la classe `Job` à l'aide d'un langage de programmation tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1384f-133">Call the `EventLogLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
 <span data-ttu-id="1384f-134">L'exemple de code suivant définit le travail pour qu'il génère une entrée de journal des événements du système d'exploitation lorsque l'exécution d'une tâche se termine.</span><span class="sxs-lookup"><span data-stu-id="1384f-134">The following code example sets the job to generate an operating system event log entry when the job execution finishes.</span></span>  
  
```powershell
$srv = new-object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = new-object Microsoft.SqlServer.Management.Smo.Agent.Job($srv.JobServer, "Test Job")  
$jb.EventLogLevel = [Microsoft.SqlServer.Management.Smo.Agent.CompletionAction]::Always  
```  
