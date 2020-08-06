---
title: Tâche Vérifier l’intégrité de la base de données (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.integrity.f1
- sql12.swb.maint.integrity.f1
helpviewer_keywords:
- Check Database Integrity Task dialog box
ms.assetid: 3534494a-5dfe-4738-b49a-e7fabd731c47
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f786755a3b7ed5d991b4cf0e32c067e355c111ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612316"
---
# <a name="check-database-integrity-task-maintenance-plan"></a><span data-ttu-id="84cf6-102">Tâche Vérifier l'intégrité de la base de données (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="84cf6-102">Check Database Integrity Task (Maintenance Plan)</span></span>
  <span data-ttu-id="84cf6-103">Utilisez la boîte de dialogue **Tâche Vérifier l’intégrité de la base de données** pour vérifier l’intégrité d’allocation et de structure des tables utilisateur et système et des index de la base de données, en exécutant l’instruction `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="84cf6-103">Use the **Check Database Integrity Task** dialog to check the allocation and structural integrity of user and system tables, and indexes in the database, by running the `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="84cf6-104">L'exécution de `DBCC` garantit que tous les problèmes d'intégrité de la base de données seront rapportés, ce qui permet de les signaler plus tard à l'administrateur système ou au propriétaire de la base de données.</span><span class="sxs-lookup"><span data-stu-id="84cf6-104">Running `DBCC` ensures that any integrity problems with the database are reported, thereby allowing them to be addressed later by a system administrator or database owner.</span></span>  
  
## <a name="options"></a><span data-ttu-id="84cf6-105">Options</span><span class="sxs-lookup"><span data-stu-id="84cf6-105">Options</span></span>  
 <span data-ttu-id="84cf6-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="84cf6-106">**Connection**</span></span>  
 <span data-ttu-id="84cf6-107">Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="84cf6-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="84cf6-108">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="84cf6-108">**New**</span></span>  
 <span data-ttu-id="84cf6-109">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="84cf6-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="84cf6-110">La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="84cf6-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="84cf6-111">**Bases de données**</span><span class="sxs-lookup"><span data-stu-id="84cf6-111">**Databases**</span></span>  
 <span data-ttu-id="84cf6-112">Spécifie les bases de données faisant l'objet de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="84cf6-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="84cf6-113">**Toutes les bases de données**</span><span class="sxs-lookup"><span data-stu-id="84cf6-113">**All databases**</span></span>  
  
     <span data-ttu-id="84cf6-114">Génère un plan de maintenance qui exécute les tâches de maintenance sur toutes les bases de données [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], à l’exception de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="84cf6-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except **tempdb**.</span></span>  
  
-   <span data-ttu-id="84cf6-115">**Toutes les bases de données système**</span><span class="sxs-lookup"><span data-stu-id="84cf6-115">**All system databases**</span></span>  
  
     <span data-ttu-id="84cf6-116">Génère un plan de maintenance qui exécute des tâches de maintenance sur chaque base de données système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à l'exception de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="84cf6-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="84cf6-117">Aucune tâche de maintenance n'est exécutée sur les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="84cf6-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="84cf6-118">**Toutes les bases de données utilisateur**</span><span class="sxs-lookup"><span data-stu-id="84cf6-118">**All user databases**</span></span>  
  
     <span data-ttu-id="84cf6-119">Génère un plan de maintenance qui exécute des tâches de maintenance sur toutes les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="84cf6-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="84cf6-120">Aucune tâche de maintenance n'est exécutée sur les bases de données système de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="84cf6-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="84cf6-121">**Ces bases de données**</span><span class="sxs-lookup"><span data-stu-id="84cf6-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="84cf6-122">Génère un plan de maintenance qui n'exécute les tâches de maintenance que sur les bases de données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="84cf6-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="84cf6-123">Si vous choisissez cette option, sélectionnez au moins une base de données.</span><span class="sxs-lookup"><span data-stu-id="84cf6-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="84cf6-124">Les plans de maintenance sont exécutés uniquement sur des bases de données définies au niveau de compatibilité 80 ou plus.</span><span class="sxs-lookup"><span data-stu-id="84cf6-124">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="84cf6-125">Les bases de données définies au niveau de compatibilité 70 ou moins ne sont pas affichées.</span><span class="sxs-lookup"><span data-stu-id="84cf6-125">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="84cf6-126">**Inclure les index**</span><span class="sxs-lookup"><span data-stu-id="84cf6-126">**Include indexes**</span></span>  
 <span data-ttu-id="84cf6-127">Vérifie l'intégrité de toutes les pages d'index ainsi que des pages de données des tables.</span><span class="sxs-lookup"><span data-stu-id="84cf6-127">Check the integrity of all the index pages as well as the table data pages.</span></span>  
  
 <span data-ttu-id="84cf6-128">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="84cf6-128">**View T-SQL**</span></span>  
 <span data-ttu-id="84cf6-129">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="84cf6-129">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84cf6-130">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="84cf6-130">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="84cf6-131">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="84cf6-131">New Connection Dialog Box</span></span>  
 <span data-ttu-id="84cf6-132">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="84cf6-132">**Connection name**</span></span>  
 <span data-ttu-id="84cf6-133">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="84cf6-133">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="84cf6-134">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="84cf6-134">**Select or enter a server name**</span></span>  
 <span data-ttu-id="84cf6-135">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="84cf6-135">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="84cf6-136">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="84cf6-136">**Refresh**</span></span>  
 <span data-ttu-id="84cf6-137">Actualise la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="84cf6-137">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="84cf6-138">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="84cf6-138">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="84cf6-139">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="84cf6-139">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="84cf6-140">**Utiliser la sécurité intégrée à Windows NT**</span><span class="sxs-lookup"><span data-stu-id="84cf6-140">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="84cf6-141">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="84cf6-141">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="84cf6-142">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="84cf6-142">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="84cf6-143">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84cf6-143">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="84cf6-144">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="84cf6-144">This option is not available.</span></span>  
  
 <span data-ttu-id="84cf6-145">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="84cf6-145">**User name**</span></span>  
 <span data-ttu-id="84cf6-146">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="84cf6-146">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="84cf6-147">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="84cf6-147">This option is not available.</span></span>  
  
 <span data-ttu-id="84cf6-148">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="84cf6-148">**Password**</span></span>  
 <span data-ttu-id="84cf6-149">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="84cf6-149">Provide a password to use when authenticating.</span></span> <span data-ttu-id="84cf6-150">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="84cf6-150">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84cf6-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84cf6-151">See Also</span></span>  
 [<span data-ttu-id="84cf6-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="84cf6-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
