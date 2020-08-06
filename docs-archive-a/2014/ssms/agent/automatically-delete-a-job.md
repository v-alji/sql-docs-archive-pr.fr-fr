---
title: Supprimer automatiquement un travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- dropping jobs
- SQL Server Agent jobs, removing
- automatic job removal
- jobs [SQL Server Agent], deleting
- deleting jobs
- removing jobs
ms.assetid: 92dbb6da-5919-4bde-9354-d454e9ea3da0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07a10ec4a31d553a548bfecdcba426e3b46a1782
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611502"
---
# <a name="automatically-delete-a-job"></a><span data-ttu-id="c62ad-102">Automatically Delete a Job</span><span class="sxs-lookup"><span data-stu-id="c62ad-102">Automatically Delete a Job</span></span>
  <span data-ttu-id="c62ad-103">Cette rubrique explique comment configurer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pour supprimer automatiquement des travaux lorsqu’ils réussissent, échouent ou se terminent à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="c62ad-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to automatically delete jobs when they succeed, fail, or complete by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="c62ad-104">Les réponses à un travail garantissent que les administrateurs de base de données ont connaissance de l'achèvement des travaux et de leur fréquence d'exécution.</span><span class="sxs-lookup"><span data-stu-id="c62ad-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="c62ad-105">Les réponses classiques à un travail peuvent être :</span><span class="sxs-lookup"><span data-stu-id="c62ad-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="c62ad-106">Une notification de l’opérateur, à l’aide de l’e-mail, de la radiomessagerie ou d’un message **net send** .</span><span class="sxs-lookup"><span data-stu-id="c62ad-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="c62ad-107">Utilisez une de ces réponses à un travail si l'opérateur doit exécuter une action en conséquence.</span><span class="sxs-lookup"><span data-stu-id="c62ad-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="c62ad-108">Par exemple, si un travail de sauvegarde se termine avec succès, l'opérateur doit être averti afin qu'il enlève la bande de sauvegarde et qu'il la mette en lieu sûr.</span><span class="sxs-lookup"><span data-stu-id="c62ad-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="c62ad-109">L'écriture d'un message d'événement dans le journal des applications Windows.</span><span class="sxs-lookup"><span data-stu-id="c62ad-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="c62ad-110">Vous pouvez choisir d'utiliser cette réponse uniquement en cas d'échec des travaux.</span><span class="sxs-lookup"><span data-stu-id="c62ad-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="c62ad-111">La suppression automatique du travail.</span><span class="sxs-lookup"><span data-stu-id="c62ad-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="c62ad-112">Utilisez cette réponse à un travail si vous êtes certain de ne plus avoir besoin d'exécuter ce travail à nouveau.</span><span class="sxs-lookup"><span data-stu-id="c62ad-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="c62ad-113">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c62ad-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c62ad-114">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c62ad-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c62ad-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c62ad-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c62ad-116">**Pour spécifier des réponses à un travail, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="c62ad-116">**To specify job responses, using:**</span></span>  
  
     [<span data-ttu-id="c62ad-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c62ad-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="c62ad-118">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c62ad-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c62ad-119">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c62ad-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c62ad-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c62ad-120">Security</span></span>  
 <span data-ttu-id="c62ad-121">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="c62ad-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="c62ad-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c62ad-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-automatically-delete-a-job"></a><span data-ttu-id="c62ad-123">Pour supprimer automatiquement un travail</span><span class="sxs-lookup"><span data-stu-id="c62ad-123">To automatically delete a job</span></span>  
  
1.  <span data-ttu-id="c62ad-124">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="c62ad-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c62ad-125">Développez **Agent SQL Server**, développez **Travaux**, cliquez avec le bouton droit sur le travail que vous souhaitez modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c62ad-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="c62ad-126">Sélectionnez la page **Notifications** .</span><span class="sxs-lookup"><span data-stu-id="c62ad-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="c62ad-127">Activez la case à cocher **Supprimer automatiquement le travail**, puis choisissez l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c62ad-127">Check **Automatically delete job**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="c62ad-128">Cliquez sur **Lors de la réussite du travail** pour supprimer l'état du travail lorsqu'il aboutit.</span><span class="sxs-lookup"><span data-stu-id="c62ad-128">Click **When the job succeeds** to delete the job status when it has completed successfully.</span></span>  
  
    -   <span data-ttu-id="c62ad-129">Cliquez sur **Lors de l'échec du travail** pour supprimer le travail lorsqu'il se termine par un échec.</span><span class="sxs-lookup"><span data-stu-id="c62ad-129">Click **When the job fails** to delete the job when it has completed unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="c62ad-130">Cliquez sur **Lorsque le travail est terminé** pour supprimer le travail quel que soit son état d'achèvement.</span><span class="sxs-lookup"><span data-stu-id="c62ad-130">Click **When the job completes** to delete the job regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="c62ad-131">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="c62ad-131">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="c62ad-132">**Pour supprimer automatiquement un travail**</span><span class="sxs-lookup"><span data-stu-id="c62ad-132">**To automatically delete a job**</span></span>  
  
 <span data-ttu-id="c62ad-133">Utilisez la propriété `DeleteLevel` de la classe `Job` à l'aide d'un langage de programmation tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c62ad-133">Use the `DeleteLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="c62ad-134">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="c62ad-134">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
  
  
