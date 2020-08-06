---
title: Afficher des informations sur une étape de travail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- displaying job step information
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- viewing job step information
ms.assetid: e3f06492-dc86-4e06-b186-ea58aff6d591
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d9fc6a006884bc564b5db2bfa8b168c8ae59149
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599783"
---
# <a name="view-job-step-information"></a><span data-ttu-id="2d3d5-102">View Job Step Information</span><span class="sxs-lookup"><span data-stu-id="2d3d5-102">View Job Step Information</span></span>
  <span data-ttu-id="2d3d5-103">Cette rubrique décrit comment afficher les détails d'une étape de travail dans la boîte de dialogue Propriétés de l'étape du travail.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-103">This topic describes how to view job step details in the Job Step Properties dialog.</span></span> <span data-ttu-id="2d3d5-104">Elle contient également des informations sur l'affichage de la sortie d'une étape de travail.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-104">It also includes information about viewing job step output.</span></span>  
  
-   <span data-ttu-id="2d3d5-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2d3d5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2d3d5-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2d3d5-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2d3d5-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2d3d5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2d3d5-108">**Pour afficher des informations sur une étape de travail, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="2d3d5-108">**To view job step information, using:**</span></span>  
  
     [<span data-ttu-id="2d3d5-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d3d5-109">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d3d5-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2d3d5-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2d3d5-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2d3d5-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2d3d5-112">Si l'étape du travail a été configurée pour écrire sa sortie dans une table ou un fichier et si le travail a été exécuté au moins une fois, vous pouvez afficher sa sortie dans la page **Avancé** de la boîte de dialogue **Propriétés de l'étape du travail** .</span><span class="sxs-lookup"><span data-stu-id="2d3d5-112">If the job step has been configured to write its output to a table or file and the job has run at least once, you can view its output on the **Advanced** page of the **Job Step Properties** dialog.</span></span> <span data-ttu-id="2d3d5-113">Lorsqu'un travail ou une étape de travail est supprimé, le journal de sortie est automatiquement supprimé.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-113">When a job or job step is deleted, the output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2d3d5-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2d3d5-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d3d5-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2d3d5-115">Permissions</span></span>  
 <span data-ttu-id="2d3d5-116">Affichez uniquement les travaux dont vous êtes propriétaire, à moins que vous ne soyez membre du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="2d3d5-116">You can view only those jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="2d3d5-117">Les membres de ce rôle peuvent afficher tous les travaux et tous les détails d'une étape de travail.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-117">Members of this role can view all jobs and job step details.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="2d3d5-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d3d5-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-step-information"></a><span data-ttu-id="2d3d5-119">Pour afficher des informations sur une étape de travail</span><span class="sxs-lookup"><span data-stu-id="2d3d5-119">To view job step information</span></span>  
  
1.  <span data-ttu-id="2d3d5-120">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2d3d5-121">Développez **Agent SQL Server**et **Travaux**, cliquez avec le bouton droit sur le travail contenant l’étape à modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that contains the job step to be viewed, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2d3d5-122">Dans la boîte de dialogue **Propriétés du travail** , cliquez sur l'onglet **Étapes** .</span><span class="sxs-lookup"><span data-stu-id="2d3d5-122">In the **Job Properties** dialog, click the **Steps** page.</span></span>  
  
4.  <span data-ttu-id="2d3d5-123">Cliquez sur l'étape de travail à afficher, puis sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-123">Click the job step to be viewed, and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="2d3d5-124">Dans la page **Général** de la boîte de dialogue **Propriétés de l'étape du travail** , vous pouvez afficher le type d'étape de travail et sa fonction.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-124">On the **General** page of the **Job Step Properties** dialog, you can view the type of job step and what it does.</span></span>  
  
6.  <span data-ttu-id="2d3d5-125">Cliquez sur la page **Avancé** pour afficher les mesures prises par l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si l'étape du travail réussit ou échoue, le nombre de fois où l'étape du travail doit être tentée, l'emplacement où est écrite la sortie de l'étape du travail et l'utilisateur pour lequel elle est exécutée.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-125">Click the **Advanced** page to view the actions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent takes if the job step succeeds or fails, how many times the job step should be attempted, where the job step output is written, and the user the job step runs as.</span></span>  
  
#### <a name="to-view-job-step-output"></a><span data-ttu-id="2d3d5-126">Pour afficher la sortie d'une étape de travail</span><span class="sxs-lookup"><span data-stu-id="2d3d5-126">To view job step output</span></span>  
  
1.  <span data-ttu-id="2d3d5-127">Dans la boîte de dialogue **Propriétés de l'étape du travail** , cliquez sur la page **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="2d3d5-127">In the **Job Step Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="2d3d5-128">Selon la version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à laquelle vous êtes connecté, vous pouvez afficher le fichier ou la table de sortie de l'étape de travail de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="2d3d5-128">Depending on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connected to, you can view either the job step output file or table as follows:</span></span>  
  
    -   <span data-ttu-id="2d3d5-129">Si vous êtes connecté à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou une version ultérieure, vous pouvez cliquer sur **Afficher** uniquement lorsque la case à cocher **Enregistrer un journal dans la table** est activée.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-129">When you are connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later, you can click **View** only when **Log to table** is checked.</span></span> <span data-ttu-id="2d3d5-130">Dans ce cas, la sortie de la table de travail est écrite dans la table **sysjobstepslogs** de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="2d3d5-130">In this case, the job step output is written to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
    -   <span data-ttu-id="2d3d5-131">Le bouton **Afficher** est désactivé lorsque le résultat de l'étape de travail est écrit dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-131">The **View** button is disabled when job step output is written to a file.</span></span> <span data-ttu-id="2d3d5-132">Pour afficher le fichier de sortie d'une étape de travail, utilisez le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="2d3d5-132">To view a job step output file, use Notepad.</span></span>  
  
  
