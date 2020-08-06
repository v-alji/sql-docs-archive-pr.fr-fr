---
title: Supprimer une catégorie de travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- deleting job category
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
- removing job category
ms.assetid: 47a7640b-20b3-4639-ab37-b6fc73575e6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: e96dd0461f3dace138b7822cdbaaa2fa242e2cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696368"
---
# <a name="delete-a-job-category"></a><span data-ttu-id="335e6-102">Supprimer une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="335e6-102">Delete a Job Category</span></span>
  <span data-ttu-id="335e6-103">Cette rubrique explique comment supprimer une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] catégorie de travaux de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="335e6-103">This topic describes how to delete a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="335e6-104">Les catégories de travaux permettent d'organiser les travaux afin d'en faciliter le filtrage et le regroupement.</span><span class="sxs-lookup"><span data-stu-id="335e6-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="335e6-105">Par exemple, vous pouvez organiser tous vos travaux de sauvegarde de base de données dans la catégorie Maintenance de bases de données.</span><span class="sxs-lookup"><span data-stu-id="335e6-105">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span>  

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="335e6-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="335e6-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="335e6-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="335e6-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="335e6-108">Lorsque vous supprimez une catégorie de travaux définie par l'utilisateur, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vous invite à réaffecter les travaux qui en dépendent à une autre catégorie de travaux.</span><span class="sxs-lookup"><span data-stu-id="335e6-108">When you delete a user-defined job category, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent prompts you to reassign the jobs that are assigned to it to another job category.</span></span> <span data-ttu-id="335e6-109">Seules les catégories de travaux définies par l'utilisateur peuvent être supprimées.</span><span class="sxs-lookup"><span data-stu-id="335e6-109">You can only delete user-defined job categories.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="335e6-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="335e6-110">Security</span></span>  
 <span data-ttu-id="335e6-111">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="335e6-111">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="335e6-112">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="335e6-112">Using SQL Server Management Studio</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="335e6-113">Pour supprimer une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="335e6-113">To delete a job category</span></span>  
  
1.  <span data-ttu-id="335e6-114">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez supprimer une catégorie de travaux.</span><span class="sxs-lookup"><span data-stu-id="335e6-114">In **Object Explorer**, click the plus sign to expand the server where you want to delete a job category.</span></span>  
  
2.  <span data-ttu-id="335e6-115">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="335e6-115">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="335e6-116">Cliquez avec le bouton droit sur le dossier **Travaux** et sélectionnez **Gérer les catégories de travaux**.</span><span class="sxs-lookup"><span data-stu-id="335e6-116">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="335e6-117">Dans la boîte de dialogue **Gérer les catégories de travaux**_nom_serveur_ , sélectionnez la catégorie de travaux à supprimer.</span><span class="sxs-lookup"><span data-stu-id="335e6-117">In the **Manage Job Categories**_server_name_ dialog box, select the job category to delete.</span></span>  
  
5.  <span data-ttu-id="335e6-118">Cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="335e6-118">Click **Delete**.</span></span>  
  
6.  <span data-ttu-id="335e6-119">Dans la boîte de dialogue **Catégories de travaux** , cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="335e6-119">In the **Job Categories** dialog box, click **Yes**.</span></span>  
  
7.  <span data-ttu-id="335e6-120">Fermez la boîte de dialogue **Gérer les catégories de travaux**_nom_serveur_ .</span><span class="sxs-lookup"><span data-stu-id="335e6-120">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="335e6-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="335e6-121">Using Transact-SQL</span></span>  
  
### <a name="to-delete-a-job-category"></a><span data-ttu-id="335e6-122">Pour supprimer une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="335e6-122">To delete a job category</span></span>  
  
1.  <span data-ttu-id="335e6-123">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="335e6-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="335e6-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="335e6-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="335e6-125">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="335e6-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- deletes the job category named AdminJobs.  
    USE msdb ;  
    GO   
    EXEC dbo.sp_delete_category  
        @name = N'AdminJobs',  
        @class = N'JOB' ;  
    GO  
    ```  
  
 <span data-ttu-id="335e6-126">Pour plus d’informations, consultez [sp_delete_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="335e6-126">For more information, see [sp_delete_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-category-transact-sql).</span></span>  

  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="335e6-127">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="335e6-127">Using SQL Server Management Objects</span></span>  

### <a name="to-delete-a-job-category"></a><span data-ttu-id="335e6-128">Pour supprimer une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="335e6-128">To delete a job category</span></span>
  
 <span data-ttu-id="335e6-129">Appelez la classe `JobCategory` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="335e6-129">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
