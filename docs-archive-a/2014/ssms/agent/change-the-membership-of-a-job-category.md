---
title: Modifier l’appartenance d’une catégorie de travaux | Documents Microsoft
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
- members [SQL Server], job categories
ms.assetid: 6a18f7f0-eb50-485f-a9c7-df31ae0f994e
author: stevestein
ms.author: sstein
ms.openlocfilehash: d9ed0db394f63594937ad923734b07fed8050955
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614339"
---
# <a name="change-the-membership-of-a-job-category"></a><span data-ttu-id="57483-102">Modifier l'appartenance d'une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="57483-102">Change the Membership of a Job Category</span></span>
  <span data-ttu-id="57483-103">Cette rubrique explique comment modifier l'appartenance de la catégorie de travaux dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)]ou de SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="57483-103">This topic describes how to change the membership of the job category in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="57483-104">Les catégories de travaux permettent d'organiser les travaux afin d'en faciliter le filtrage et le regroupement.</span><span class="sxs-lookup"><span data-stu-id="57483-104">Job categories help you organize your jobs for easy filtering and grouping.</span></span> <span data-ttu-id="57483-105">Vous pouvez créer vos propres catégories de travaux.</span><span class="sxs-lookup"><span data-stu-id="57483-105">You can create your own job categories.</span></span> <span data-ttu-id="57483-106">Vous pouvez également modifier l'appartenance aux catégories des travaux de l'Agent Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="57483-106">You can also change Microsoft SQL Server Agent jobs membership in job categories.</span></span>  
  
 <span data-ttu-id="57483-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="57483-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="57483-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="57483-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="57483-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="57483-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="57483-110">**Pour modifier l'appartenance d'une catégorie de travaux, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="57483-110">**To change the membership of a job category, using:**</span></span>  
  
     [<span data-ttu-id="57483-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57483-111">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="57483-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57483-112">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="57483-113">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="57483-113">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="57483-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="57483-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="57483-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="57483-115">Security</span></span>  
 <span data-ttu-id="57483-116">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="57483-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="57483-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="57483-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="57483-118">Pour modifier l'appartenance d'une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="57483-118">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="57483-119">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez modifier une catégorie de travaux.</span><span class="sxs-lookup"><span data-stu-id="57483-119">In **Object Explorer**, click the plus sign to expand the server where you want to edit a job category.</span></span>  
  
2.  <span data-ttu-id="57483-120">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="57483-120">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="57483-121">Cliquez avec le bouton droit sur le dossier **Travaux** et sélectionnez **Gérer les catégories de travaux**.</span><span class="sxs-lookup"><span data-stu-id="57483-121">Right-click the **Jobs** folder and select **Manage Job Categories**.</span></span>  
  
4.  <span data-ttu-id="57483-122">Dans la boîte de dialogue **Gérer les catégories de travaux**_nom_serveur_ , sélectionnez la catégorie de travaux que vous souhaitez modifier, puis cliquez sur **Afficher les travaux**.</span><span class="sxs-lookup"><span data-stu-id="57483-122">In the **Manage Job Categories**_server_name_ dialog box, select the job category that you want to edit, and then click **View Jobs**.</span></span>  
  
5.  <span data-ttu-id="57483-123">Sélectionnez la case à cocher **Afficher tous les travaux** .</span><span class="sxs-lookup"><span data-stu-id="57483-123">Select the **Show all jobs** check box.</span></span>  
  
6.  <span data-ttu-id="57483-124">Pour ajouter un travail à la catégorie, dans la grille principale, sélectionnez la case à cocher correspondant au travail dans la colonne **Sélectionner** .</span><span class="sxs-lookup"><span data-stu-id="57483-124">To add a job to the category, in the main grid, select the check box in the **Select** column corresponding to the job.</span></span> <span data-ttu-id="57483-125">Pour supprimer un travail de la catégorie, désactivez la case à cocher correspondante.</span><span class="sxs-lookup"><span data-stu-id="57483-125">To remove a job from the category, clear the box.</span></span> <span data-ttu-id="57483-126">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="57483-126">When finished, click **OK**.</span></span>  
  
7.  <span data-ttu-id="57483-127">Fermez la boîte de dialogue **Gérer les catégories de travaux**_nom_serveur_ .</span><span class="sxs-lookup"><span data-stu-id="57483-127">Close the **Manage Job Categories**_server_name_ dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="57483-128">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="57483-128">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-membership-of-a-job-category"></a><span data-ttu-id="57483-129">Pour modifier l'appartenance d'une catégorie de travaux</span><span class="sxs-lookup"><span data-stu-id="57483-129">To change the membership of a job category</span></span>  
  
1.  <span data-ttu-id="57483-130">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57483-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="57483-131">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="57483-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="57483-132">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="57483-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adding a new job category to the "NightlyBackups" job  
    USE msdb ;  
    GO  
    EXEC dbo.sp_update_job  
        @job_name = N'NightlyBackups',  
        @category_name = N'[Uncategorized (Local)]';  
    GO  
    ```  
  
 <span data-ttu-id="57483-133">Pour plus d’informations, consultez [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="57483-133">For more information, see [sp_update_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-job-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="57483-134">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="57483-134">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="57483-135">**Pour modifier l'appartenance d'une catégorie de travaux**</span><span class="sxs-lookup"><span data-stu-id="57483-135">**To change the membership of a job category**</span></span>  
  
 <span data-ttu-id="57483-136">Utilisez la classe `JobCategory` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57483-136">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
