---
title: Afficher l’activité du travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- viewing job activity
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- displaying job activity
ms.assetid: 5c284e5e-7775-435d-ac49-f3f12a27ddc7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 56b159952c83ed243c4c5d8012c76e5a2a248519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708904"
---
# <a name="view-job-activity"></a><span data-ttu-id="a389b-102">Afficher l’activité du travail</span><span class="sxs-lookup"><span data-stu-id="a389b-102">View Job Activity</span></span>
  <span data-ttu-id="a389b-103">Cette rubrique explique comment afficher l'état d'exécution des travaux de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a389b-103">This topic describes how to view the runtime state of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a389b-104">Lorsque le service [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent démarre, une nouvelle session est créée et la table **sysjobactivity** de la base de données **msdb** est remplie avec tous les travaux définis existants.</span><span class="sxs-lookup"><span data-stu-id="a389b-104">When the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service starts, a new session is created and the **sysjobactivity** table in the **msdb** database is populated with all the existing defined jobs.</span></span> <span data-ttu-id="a389b-105">Cette table enregistre l'activité du travail en cours et son état.</span><span class="sxs-lookup"><span data-stu-id="a389b-105">This table records current job activity and status.</span></span> <span data-ttu-id="a389b-106">Vous pouvez utiliser le Moniteur d'activité des travaux dans l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour afficher l'état actuel des travaux.</span><span class="sxs-lookup"><span data-stu-id="a389b-106">You can use the Job Activity Monitor in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to view the current state of jobs.</span></span> <span data-ttu-id="a389b-107">Si le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent se termine de manière inattendue, reportez-vous à la table **sysjobactivity** pour déterminer les travaux qui étaient en cours d'exécution au moment de l'interruption du service.</span><span class="sxs-lookup"><span data-stu-id="a389b-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service unexpectedly terminates, you can refer to the **sysjobactivity** table to see which jobs were being executed when the service terminated.</span></span>  
  
 <span data-ttu-id="a389b-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="a389b-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a389b-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="a389b-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a389b-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a389b-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a389b-111">**Pour afficher l'activité des travaux, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="a389b-111">**To view job activity, using:**</span></span>  
  
     [<span data-ttu-id="a389b-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a389b-112">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="a389b-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a389b-113">Transact-SQL</span></span>](#TSQL)  
  
## <a name="before-you-begin"></a><span data-ttu-id="a389b-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a389b-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a389b-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a389b-115">Security</span></span>  
 <span data-ttu-id="a389b-116">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="a389b-116">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="a389b-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a389b-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="a389b-118">Pour afficher l'activité des travaux</span><span class="sxs-lookup"><span data-stu-id="a389b-118">To view job activity</span></span>  
  
1.  <span data-ttu-id="a389b-119">Dans **l’Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], puis développez-la.</span><span class="sxs-lookup"><span data-stu-id="a389b-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a389b-120">Développez **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a389b-120">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a389b-121">Cliquez avec le bouton droit sur **Moniteur d’activité des travaux** , puis cliquez sur **Afficher l’activité du travail**.</span><span class="sxs-lookup"><span data-stu-id="a389b-121">Right-click **Job Activity Monitor** and click **View Job Activity**.</span></span>  
  
4.  <span data-ttu-id="a389b-122">Dans le **Moniteur d'activité des travaux**, vous trouverez des détails relatifs à chaque travail défini pour ce serveur.</span><span class="sxs-lookup"><span data-stu-id="a389b-122">In the **Job Activity Monitor**, you can view details about each job that is defined for this server.</span></span>  
  
5.  <span data-ttu-id="a389b-123">Cliquez avec le bouton droit sur un travail pour le démarrer, l'arrêter, l'activer ou le désactiver, actualiser son état tel qu'il est affiché dans le Moniteur d'activité des travaux, le supprimer ou encore afficher son historique ou ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="a389b-123">Right-click a job to start it, stop it, enable or disable it, refresh its status as displayed in the Job Activity Monitor, delete it, or view its history or properties.</span></span>  <span data-ttu-id="a389b-124">Pour démarrer, arrêter, activer, désactiver ou actualiser plusieurs travaux, sélectionnez plusieurs lignes dans le Moniteur d'activité des travaux et cliquez avec le bouton droit sur votre sélection.</span><span class="sxs-lookup"><span data-stu-id="a389b-124">To start, stop, enable or disable, or refresh multiple jobs, select multiple rows in the Job Activity Monitor, and right-click your selection.</span></span>  
  
6.  <span data-ttu-id="a389b-125">Pour mettre à jour le Moniteur d'activité des travaux, cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="a389b-125">To update the Job Activity Monitor, click **Refresh**.</span></span> <span data-ttu-id="a389b-126">Pour afficher moins de lignes, cliquez sur **Filtre** et saisissez les paramètres de filtre.</span><span class="sxs-lookup"><span data-stu-id="a389b-126">To view fewer rows, click **Filter** and enter filter parameters.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="a389b-127">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a389b-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-job-activity"></a><span data-ttu-id="a389b-128">Pour afficher l'activité des travaux</span><span class="sxs-lookup"><span data-stu-id="a389b-128">To view job activity</span></span>  
  
1.  <span data-ttu-id="a389b-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a389b-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a389b-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a389b-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a389b-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a389b-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- lists activity for all jobs that the current user has permission to view.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_jobactivity ;  
    GO  
    ```  
  
 <span data-ttu-id="a389b-132">Pour plus d’informations, consultez [sp_help_jobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a389b-132">For more information, see [sp_help_jobactivity &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-jobactivity-transact-sql).</span></span>  
  
  
