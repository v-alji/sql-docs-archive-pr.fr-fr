---
title: Afficher un travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], viewing
- viewing jobs
- SQL Server Agent jobs, viewing
- displaying jobs
ms.assetid: d2241a3f-dbcf-433c-b7bc-f96bdf0eac8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 26406aaf2ba0ac4809eb7ac2c84799469d0468d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614974"
---
# <a name="view-a-job"></a><span data-ttu-id="f1fed-102">View a Job</span><span class="sxs-lookup"><span data-stu-id="f1fed-102">View a Job</span></span>
  <span data-ttu-id="f1fed-103">Cette rubrique explique comment afficher [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] des travaux de l’agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1fed-103">This topic describes how to view [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f1fed-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f1fed-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f1fed-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f1fed-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f1fed-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1fed-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f1fed-107">**Pour consulter un travail, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="f1fed-107">**To view a job, using:**</span></span>  
  
     [<span data-ttu-id="f1fed-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1fed-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="f1fed-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1fed-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="f1fed-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="f1fed-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f1fed-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f1fed-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f1fed-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1fed-112">Security</span></span>  
 <span data-ttu-id="f1fed-113">Vous pouvez afficher uniquement les travaux dont vous êtes propriétaire, sauf si vous êtes membre du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f1fed-113">You can only view jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="f1fed-114">Les membres de ce rôle peuvent afficher tous les travaux.</span><span class="sxs-lookup"><span data-stu-id="f1fed-114">Members of this role can view all jobs.</span></span> <span data-ttu-id="f1fed-115">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="f1fed-115">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="f1fed-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1fed-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="f1fed-117">Pour afficher un travail</span><span class="sxs-lookup"><span data-stu-id="f1fed-117">To view a job</span></span>  
  
1.  <span data-ttu-id="f1fed-118">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="f1fed-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f1fed-119">Développez **SQL Server Agent**, puis **Travaux**.</span><span class="sxs-lookup"><span data-stu-id="f1fed-119">Expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="f1fed-120">Cliquez avec le bouton droit sur un travail, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f1fed-120">Right-click a job, and then click **Properties**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="f1fed-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1fed-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-job"></a><span data-ttu-id="f1fed-122">Pour afficher un travail</span><span class="sxs-lookup"><span data-stu-id="f1fed-122">To view a job</span></span>  
  
1.  <span data-ttu-id="f1fed-123">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1fed-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f1fed-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f1fed-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f1fed-125">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f1fed-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- lists all aspects of the information for the job NightlyBackups.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_job  
        @job_name = N'NightlyBackups',  
        @job_aspect = N'ALL' ;  
    GO  
    ```  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="f1fed-126">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="f1fed-126">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="f1fed-127">**Pour afficher un travail**</span><span class="sxs-lookup"><span data-stu-id="f1fed-127">**To view a job**</span></span>  
  
 <span data-ttu-id="f1fed-128">Utilisez la classe `Job` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1fed-128">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="f1fed-129">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="f1fed-129">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
