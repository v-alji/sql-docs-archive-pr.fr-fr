---
title: Créer une catégorie de travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, categories
- jobs [SQL Server Agent], categories
- categories [SQL Server Agent jobs]
ms.assetid: e24a6d38-d231-4f64-ab89-2d1ef6f5792c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f6daeeca6253861e8a9dcbb72faa2bd55eb2761
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704676"
---
# <a name="create-a-job-category"></a><span data-ttu-id="18426-102">Créer une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="18426-102">Create a Job Category</span></span>
  <span data-ttu-id="18426-103">Cette rubrique explique comment créer une catégorie de travaux dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)] ou de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects.</span><span class="sxs-lookup"><span data-stu-id="18426-103">This topic describes how to create a job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="18426-104">Agent contient des catégories de travail intégrées auxquelles vous pouvez affecter des travaux. Vous pouvez également créer une catégorie de travail et lui affecter les travaux.</span><span class="sxs-lookup"><span data-stu-id="18426-104">Agent provides built-in job categories that you can assign jobs to, or you can create a job category and assign jobs to it.</span></span> <span data-ttu-id="18426-105">Les catégories de travaux permettent d'organiser les travaux afin d'en faciliter le filtrage et le regroupement.</span><span class="sxs-lookup"><span data-stu-id="18426-105">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="18426-106">Par exemple, vous pouvez organiser tous vos travaux de sauvegarde de base de données dans la catégorie Maintenance de bases de données.</span><span class="sxs-lookup"><span data-stu-id="18426-106">For example, you can organize all your database backup jobs in the Database Maintenance category.</span></span> <span data-ttu-id="18426-107">Vous pouvez également créer vos propres catégories de travaux.</span><span class="sxs-lookup"><span data-stu-id="18426-107">You can also create your own job categories.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="18426-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="18426-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="18426-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="18426-109">Limitations and Restrictions</span></span>  
 <span data-ttu-id="18426-110">Les catégories multiserveurs n'existent que sur un serveur maître.</span><span class="sxs-lookup"><span data-stu-id="18426-110">Multiserver categories exist only on a master server.</span></span> <span data-ttu-id="18426-111">Il n’y a qu’une seule catégorie de travaux par défaut disponible sur un serveur maître : [**N’appartenant à aucune catégorie (Multiserveurs)**].</span><span class="sxs-lookup"><span data-stu-id="18426-111">There is only one default job category available on a master server: [**Uncategorized (Multi-Server)**].</span></span> <span data-ttu-id="18426-112">Lors du téléchargement d'un travail multiserveur, sa catégorie passe à **Travaux de MSX** sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="18426-112">When a multiserver job is downloaded, its category is changed to **Jobs From MSX** at the target server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="18426-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="18426-113">Security</span></span>  
 <span data-ttu-id="18426-114">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="18426-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="18426-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="18426-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="18426-116">Pour créer une catégorie de travail</span><span class="sxs-lookup"><span data-stu-id="18426-116">To create a job category</span></span>  
  
1.  <span data-ttu-id="18426-117">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer une catégorie de travaux.</span><span class="sxs-lookup"><span data-stu-id="18426-117">In **Object Explorer**, click the plus sign to expand the server where you want to create a job category.</span></span>  
  
2.  <span data-ttu-id="18426-118">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="18426-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="18426-119">Cliquez avec le bouton droit sur le dossier **Travaux** et sélectionnez **Gérer les catégories de travaux**.</span><span class="sxs-lookup"><span data-stu-id="18426-119">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="18426-120">Dans la boîte de dialogue **Gérer les catégories de travaux**_nom_serveur_ , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="18426-120">In the **Manage Job Categories**_server_name_ dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="18426-121">Dans la nouvelle boîte de dialogue, dans la zone **Nom** , entrez un nom pour la nouvelle catégorie de travaux.</span><span class="sxs-lookup"><span data-stu-id="18426-121">In the new dialog box, in the **Name** box, enter a name for the new job category.</span></span>  
  
6.  <span data-ttu-id="18426-122">Sélectionnez la case à cocher **Afficher tous les travaux** .</span><span class="sxs-lookup"><span data-stu-id="18426-122">Select the **Show all jobs** check box.</span></span> <span data-ttu-id="18426-123">Sélectionnez un ou plusieurs travaux pour la nouvelle catégorie en activant les cases à cocher correspondant aux travaux.</span><span class="sxs-lookup"><span data-stu-id="18426-123">Select one or more jobs for the new category by checking the boxes corresponding to the jobs.</span></span>  
  
7.  <span data-ttu-id="18426-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="18426-124">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="18426-125">Dans la boîte de dialogue **Gérer les catégories de travaux**_nom_serveur_ , cliquez sur **Actualiser** pour vous assurer que la nouvelle catégorie de travaux est active.</span><span class="sxs-lookup"><span data-stu-id="18426-125">In the **Manage Job Categories**_server_name_ dialog box, click **Refresh** to ensure that the new job category is active.</span></span> <span data-ttu-id="18426-126">Si tout se présente comme prévu, fermez cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="18426-126">If everything looks as expected, close this dialog box.</span></span>  
  
 <span data-ttu-id="18426-127">Pour plus d’informations sur ces boîtes de dialogue, consultez catégories de travaux [: gérer les catégories](job-categories-manage-job-categories.md) de travaux et les [Propriétés des catégories de travaux et nouvelle catégorie de travaux](job-categories-properties-new-job-category.md).</span><span class="sxs-lookup"><span data-stu-id="18426-127">For more information on these dialog boxes, see [Job Categories: Manage Job Categories](job-categories-manage-job-categories.md) and [Job Categories Properties and New Job Category](job-categories-properties-new-job-category.md).</span></span>  

##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="18426-128">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="18426-128">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-job-category"></a><span data-ttu-id="18426-129">Pour créer une catégorie de travail</span><span class="sxs-lookup"><span data-stu-id="18426-129">To create a job category</span></span>  
  
1.  <span data-ttu-id="18426-130">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18426-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="18426-131">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="18426-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="18426-132">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="18426-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- creates a local job category named AdminJobs   
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_category  
        @class=N'JOB',  
        @type=N'LOCAL',  
        @name=N'AdminJobs' ;  
    GO  
    ```  
  
 <span data-ttu-id="18426-133">Pour plus d’informations, consultez [sp_add_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="18426-133">For more information, see [sp_add_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-category-transact-sql).</span></span>  

##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="18426-134">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="18426-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="18426-135">**Pour créer une catégorie de travail**</span><span class="sxs-lookup"><span data-stu-id="18426-135">**To create a job category**</span></span>  
  
 <span data-ttu-id="18426-136">Appelez la classe `JobCategory` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18426-136">Call the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="18426-137">Pour obtenir un exemple de code, consultez [Planification des tâches administratives automatiques dans l’Agent SQL Server](sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="18426-137">For example code, see [Scheduling Automatic Administrative Tasks in SQL Server Agent](sql-server-agent.md).</span></span>  
