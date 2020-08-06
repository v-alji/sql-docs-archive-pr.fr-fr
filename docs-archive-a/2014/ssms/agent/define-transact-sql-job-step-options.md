---
title: Définir les options d’une étape de travail Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: b2a47057-f6fb-432b-a7b6-5d61f33a5d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc1d6412e52e74ce0c6d987d6189c0c72ffd7df7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696371"
---
# <a name="define-transact-sql-job-step-options"></a><span data-ttu-id="9eafa-102">Définir les options d'une étape de travail Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9eafa-102">Define Transact-SQL Job Step Options</span></span>
  <span data-ttu-id="9eafa-103">Cette rubrique explique comment définir les options des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] étapes de travail de l’agent [!INCLUDE[tsql](../../includes/tsql-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="9eafa-103">This topic describes how to define options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent [!INCLUDE[tsql](../../includes/tsql-md.md)] job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="9eafa-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="9eafa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9eafa-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="9eafa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9eafa-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9eafa-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9eafa-107">**Pour définir les options d'une étape de travail Transact-SQL, avec :** ,</span><span class="sxs-lookup"><span data-stu-id="9eafa-107">**To define Transact-SQL job step options, using:** ,</span></span>  
  
     [<span data-ttu-id="9eafa-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9eafa-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="9eafa-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="9eafa-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9eafa-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="9eafa-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9eafa-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9eafa-111">Security</span></span>  
 <span data-ttu-id="9eafa-112">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="9eafa-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="9eafa-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9eafa-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-transact-sql-job-step-options"></a><span data-ttu-id="9eafa-114">Pour définir les options d'une étape de travail Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9eafa-114">To define Transact-SQL job step options</span></span>  
  
1.  <span data-ttu-id="9eafa-115">Dans **l'Explorateur d'objets**, développez **Agent SQL Server**, développez **Travaux**, cliquez avec le bouton droit sur le travail que vous voulez modifier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9eafa-115">In **Object Explorer**, expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9eafa-116">Cliquez successivement sur la page **Étapes** , sur une étape de travail et sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9eafa-116">Click the **Steps** page, click a job step, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="9eafa-117">Dans la boîte de dialogue **Propriétés de l'étape de travail** , confirmez le type de travail **Script Transact-SQL (TSQL)**, puis sélectionnez la page **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="9eafa-117">On the **Job Step Properties** dialog, confirm that the job type is **Transact-SQL script (TSQL)**, and then select the **Advanced** page.</span></span>  
  
4.  <span data-ttu-id="9eafa-118">Définissez l'action à exécuter si le travail aboutit en sélectionnant l'option appropriée dans la liste **Action en cas de succès** .</span><span class="sxs-lookup"><span data-stu-id="9eafa-118">Specify an action to take if the job is successful by selecting from the **On success action** list.</span></span>  
  
5.  <span data-ttu-id="9eafa-119">Définissez le nombre de tentatives en entrant un nombre compris entre 0 et 9999 dans la zone **Tentatives de reprises** .</span><span class="sxs-lookup"><span data-stu-id="9eafa-119">Specify a number of retry attempts by entering a number from 0 to 9999 into the **Retry attempts** box.</span></span>  
  
6.  <span data-ttu-id="9eafa-120">Définissez une fréquence de tentative en entrant un nombre de minutes compris entre 0 et 9999 dans la zone **Intervalle de reprise** .</span><span class="sxs-lookup"><span data-stu-id="9eafa-120">Specify a retry interval by entering a number of minutes from 0 to 9999 into the **Retry interval** box.</span></span>  
  
7.  <span data-ttu-id="9eafa-121">Définissez l'action à exécuter si le travail échoue en sélectionnant l'option appropriée dans la liste **Action en cas d'échec** .</span><span class="sxs-lookup"><span data-stu-id="9eafa-121">Specify an action to take if the job fails by choosing from the **On failure action** list.</span></span>  
  
8.  <span data-ttu-id="9eafa-122">Si le travail est un script [!INCLUDE[tsql](../../includes/tsql-md.md)] , vous pouvez choisir les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9eafa-122">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="9eafa-123">Entrez le nom d'un **fichier de sortie**.</span><span class="sxs-lookup"><span data-stu-id="9eafa-123">Enter the name of an **Output file**.</span></span> <span data-ttu-id="9eafa-124">Par défaut, les données du fichier sont remplacées chaque fois que l'étape de travail s'exécute.</span><span class="sxs-lookup"><span data-stu-id="9eafa-124">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="9eafa-125">Si vous ne voulez pas remplacer les données, activez **Ajouter la sortie au fichier existant**.</span><span class="sxs-lookup"><span data-stu-id="9eafa-125">If you do not want the output file overwritten, check **Append output to existing file**.</span></span> <span data-ttu-id="9eafa-126">Cette option est uniquement disponible pour les membres du rôle de serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="9eafa-126">This option is only available to members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="9eafa-127">Notez que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ne permet pas aux utilisateurs d'afficher les fichiers arbitraires dans le système de fichiers. Vous ne pouvez donc pas utiliser [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] pour afficher les journaux d'étape de travail écrits dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="9eafa-127">Note that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] does not allow users to view arbitrary files on the file system, so you cannot use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to view job step logs that are written to the file system.</span></span>  
  
    -   <span data-ttu-id="9eafa-128">Activez **Enregistrer un journal dans la table** pour enregistrer l'étape de travail dans une table de base de données.</span><span class="sxs-lookup"><span data-stu-id="9eafa-128">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="9eafa-129">Par défaut, le contenu de la table est remplacé chaque fois que l'étape de travail s'exécute.</span><span class="sxs-lookup"><span data-stu-id="9eafa-129">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="9eafa-130">Si vous ne voulez pas remplacer les données, activez **Ajouter la sortie à l'entrée existante dans la table**.</span><span class="sxs-lookup"><span data-stu-id="9eafa-130">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="9eafa-131">Une fois l'étape de travail exécutée, vous pouvez afficher le contenu de la table en cliquant sur **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="9eafa-131">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="9eafa-132">Activez **Inclure la sortie de l'étape dans l'historique** pour inclure la sortie dans l'historique de l'étape.</span><span class="sxs-lookup"><span data-stu-id="9eafa-132">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="9eafa-133">Le résultat ne sera affiché que s'il n'y a pas d'erreur.</span><span class="sxs-lookup"><span data-stu-id="9eafa-133">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="9eafa-134">De même, le résultat peut être tronqué.</span><span class="sxs-lookup"><span data-stu-id="9eafa-134">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="9eafa-135">Si vous êtes membre du rôle de serveur fixe **sysadmin** et voulez exécuter cette étape de travail avec une connexion SQL différente, sélectionnez la connexion SQL dans la liste **Exécuter en tant qu'utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="9eafa-135">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="9eafa-136">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="9eafa-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="9eafa-137">**Pour définir les options d'une étape de travail Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="9eafa-137">**To define Transact-SQL job step options**</span></span>  
  
 <span data-ttu-id="9eafa-138">Utilisez la classe `JobStep` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9eafa-138">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
