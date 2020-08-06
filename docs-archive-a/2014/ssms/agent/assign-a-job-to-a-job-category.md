---
title: Affecter un travail à une catégorie de travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], assigning
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- SQL Server Agent jobs, assigning
- assigning job to category
ms.assetid: a9ea65a2-1d73-4582-a335-63adeb450cb6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 208ff6722a9c18fd4dd0d061575f0d496af27810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614342"
---
# <a name="assign-a-job-to-a-job-category"></a><span data-ttu-id="e92b9-102">Affecter un travail à une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="e92b9-102">Assign a Job to a Job Category</span></span>
  <span data-ttu-id="e92b9-103">Cette rubrique décrit comment affecter des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] travaux de l’agent à des catégories de travaux dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="e92b9-103">This topic describes how to assign [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs to job categories in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="e92b9-104">Les catégories de travaux permettent d'organiser les travaux afin d'en faciliter le filtrage et le regroupement.</span><span class="sxs-lookup"><span data-stu-id="e92b9-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="e92b9-105">Par exemple, vous pouvez organiser tous vos travaux de sauvegarde de base de données dans la catégorie Maintenance de bases de données.</span><span class="sxs-lookup"><span data-stu-id="e92b9-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="e92b9-106">Vous pouvez affecter des travaux à des catégories de travaux intégrées, ou vous pouvez créer une catégorie de travaux définie par l’utilisateur, à laquelle vous affectez ensuite des travaux.</span><span class="sxs-lookup"><span data-stu-id="e92b9-106">You can assign jobs to built-in job categories, or you can create a user-defined job category and then assign jobs to that.</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e92b9-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e92b9-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e92b9-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e92b9-108">Security</span></span>  
 <span data-ttu-id="e92b9-109">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e92b9-109">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e92b9-110">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e92b9-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="e92b9-111">Pour affecter un travail à une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="e92b9-111">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="e92b9-112">Dans l' **Explorateur d'objets**, cliquez sur le signe plus pour développer le serveur sur lequel vous souhaitez affecter un travail à une catégorie de travaux.</span><span class="sxs-lookup"><span data-stu-id="e92b9-112">In **Object Explorer**, click the plus sign to expand the server where you want to assign a job to a job category.</span></span>  
  
2.  <span data-ttu-id="e92b9-113">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e92b9-113">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="e92b9-114">Cliquez sur le signe plus (+) pour développer le dossier **Travaux** .</span><span class="sxs-lookup"><span data-stu-id="e92b9-114">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="e92b9-115">Cliquez avec le bouton droit sur le travail à modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e92b9-115">Right-click the job you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="e92b9-116">Dans la boîte de dialogue **Propriétés du travail-**_job_name_ , dans la liste **catégorie** , sélectionnez la catégorie de travaux que vous voulez affecter au travail.</span><span class="sxs-lookup"><span data-stu-id="e92b9-116">In the **Job Properties -**_job_name_ dialog box, in the **Category** list, select the job category you want to assign to the job.</span></span>  
  
6.  <span data-ttu-id="e92b9-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e92b9-117">Click **OK**.</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="e92b9-118">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e92b9-118">Using Transact-SQL</span></span>  
  
#### <a name="to-assign-a-job-to-a-job-category"></a><span data-ttu-id="e92b9-119">Pour affecter un travail à une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="e92b9-119">To assign a job to a job category</span></span>  
  
1.  <span data-ttu-id="e92b9-120">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e92b9-120">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e92b9-121">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e92b9-121">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e92b9-122">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e92b9-122">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="e92b9-123">Pour plus d’informations, consultez [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e92b9-123">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="e92b9-124">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="e92b9-124">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="e92b9-125">**Pour affecter un travail à une catégorie de travaux**</span><span class="sxs-lookup"><span data-stu-id="e92b9-125">**To assign a job to a job category**</span></span>  
  
 <span data-ttu-id="e92b9-126">Utilisez la classe `JobCategory` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e92b9-126">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
  
  
