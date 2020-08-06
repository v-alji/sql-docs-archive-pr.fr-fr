---
title: Tâche Réorganiser l’index (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.defrag.f1
helpviewer_keywords:
- Reorganize Index Task dialog box
ms.assetid: e9cbebbd-f36f-4176-9832-382a46ac946c
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bbb154045b781f8a92dfce9c9d2f6ee2d819c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603966"
---
# <a name="reorganize-index-task-maintenance-plan"></a><span data-ttu-id="31a0d-102">Tâche Réorganiser l'index (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="31a0d-102">Reorganize Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="31a0d-103">Utilisez la boîte de dialogue **Tâche Réorganiser l’index** pour réordonner les pages d’index dans un ordre qui rend les recherches plus efficaces.</span><span class="sxs-lookup"><span data-stu-id="31a0d-103">Use the **ReorganizeIndex Task** dialog to move index pages into a more efficient search order.</span></span> <span data-ttu-id="31a0d-104">Cette tâche utilise l'instruction `ALTER INDEX REORGANIZE` avec des bases de données [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31a0d-104">This task uses the `ALTER INDEX REORGANIZE` statement with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] databases.</span></span>  
  
## <a name="options"></a><span data-ttu-id="31a0d-105">Options</span><span class="sxs-lookup"><span data-stu-id="31a0d-105">Options</span></span>  
 <span data-ttu-id="31a0d-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="31a0d-106">**Connection**</span></span>  
 <span data-ttu-id="31a0d-107">Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="31a0d-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="31a0d-108">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="31a0d-108">**New**</span></span>  
 <span data-ttu-id="31a0d-109">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="31a0d-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="31a0d-110">La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="31a0d-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="31a0d-111">**Bases de données**</span><span class="sxs-lookup"><span data-stu-id="31a0d-111">**Databases**</span></span>  
 <span data-ttu-id="31a0d-112">Spécifie les bases de données faisant l'objet de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="31a0d-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="31a0d-113">**Toutes les bases de données**</span><span class="sxs-lookup"><span data-stu-id="31a0d-113">**All databases**</span></span>  
  
     <span data-ttu-id="31a0d-114">Génère un plan de maintenance qui exécute des tâches de maintenance sur toutes les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à l'exception de tempdb.</span><span class="sxs-lookup"><span data-stu-id="31a0d-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="31a0d-115">**Toutes les bases de données système**</span><span class="sxs-lookup"><span data-stu-id="31a0d-115">**All system databases**</span></span>  
  
     <span data-ttu-id="31a0d-116">Génère un plan de maintenance qui exécute des tâches de maintenance sur chaque base de données système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à l'exception de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="31a0d-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="31a0d-117">Aucune tâche de maintenance n'est exécutée sur les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31a0d-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="31a0d-118">**Toutes les bases de données utilisateur**</span><span class="sxs-lookup"><span data-stu-id="31a0d-118">**All user databases**</span></span>  
  
     <span data-ttu-id="31a0d-119">Génère un plan de maintenance qui exécute des tâches de maintenance sur toutes les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31a0d-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="31a0d-120">Aucune tâche de maintenance n'est exécutée sur les bases de données système de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31a0d-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="31a0d-121">**Ces bases de données**</span><span class="sxs-lookup"><span data-stu-id="31a0d-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="31a0d-122">Génère un plan de maintenance qui n'exécute les tâches de maintenance que sur les bases de données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="31a0d-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="31a0d-123">Si vous choisissez cette option, sélectionnez au moins une base de données.</span><span class="sxs-lookup"><span data-stu-id="31a0d-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="31a0d-124">**Object**</span><span class="sxs-lookup"><span data-stu-id="31a0d-124">**Object**</span></span>  
 <span data-ttu-id="31a0d-125">Limite la grille de **Sélection** à l’affichage des tables et/ou des vues.</span><span class="sxs-lookup"><span data-stu-id="31a0d-125">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="31a0d-126">**Sélection**</span><span class="sxs-lookup"><span data-stu-id="31a0d-126">**Selection**</span></span>  
 <span data-ttu-id="31a0d-127">Spécifie les tables ou les index faisant l'objet de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="31a0d-127">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="31a0d-128">Non disponible quand **Tables et vues** est sélectionné dans la zone **Objet** .</span><span class="sxs-lookup"><span data-stu-id="31a0d-128">Not available when **Tables and Views** is selected in the **Object** box.</span></span>  
  
 <span data-ttu-id="31a0d-129">**Compacter les objets importants**</span><span class="sxs-lookup"><span data-stu-id="31a0d-129">**Compact large objects**</span></span>  
 <span data-ttu-id="31a0d-130">Annule l'allocation de l'espace pour les tables et les vues si possible.</span><span class="sxs-lookup"><span data-stu-id="31a0d-130">Deallocate space for tables and views when possible.</span></span> <span data-ttu-id="31a0d-131">Cette option utilise `ALTER INDEX LOB_COMPACTION = ON`.</span><span class="sxs-lookup"><span data-stu-id="31a0d-131">This option uses `ALTER INDEX LOB_COMPACTION = ON`.</span></span>  
  
 <span data-ttu-id="31a0d-132">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="31a0d-132">**View T-SQL**</span></span>  
 <span data-ttu-id="31a0d-133">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="31a0d-133">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31a0d-134">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="31a0d-134">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="31a0d-135">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="31a0d-135">New Connection Dialog Box</span></span>  
 <span data-ttu-id="31a0d-136">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="31a0d-136">**Connection name**</span></span>  
 <span data-ttu-id="31a0d-137">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="31a0d-137">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="31a0d-138">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="31a0d-138">**Select or enter a server name**</span></span>  
 <span data-ttu-id="31a0d-139">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="31a0d-139">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="31a0d-140">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="31a0d-140">**Refresh**</span></span>  
 <span data-ttu-id="31a0d-141">Actualise la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="31a0d-141">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="31a0d-142">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="31a0d-142">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="31a0d-143">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="31a0d-143">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="31a0d-144">**Utiliser la sécurité intégrée à Windows NT**</span><span class="sxs-lookup"><span data-stu-id="31a0d-144">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="31a0d-145">Permet de se connecter à une instance du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] avec l’authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="31a0d-145">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="31a0d-146">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="31a0d-146">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="31a0d-147">Permet de se connecter à une instance du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] en utilisant l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31a0d-147">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="31a0d-148">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="31a0d-148">This option is not available.</span></span>  
  
 <span data-ttu-id="31a0d-149">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="31a0d-149">**User name**</span></span>  
 <span data-ttu-id="31a0d-150">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="31a0d-150">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="31a0d-151">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="31a0d-151">This option is not available.</span></span>  
  
 <span data-ttu-id="31a0d-152">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="31a0d-152">**Password**</span></span>  
 <span data-ttu-id="31a0d-153">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="31a0d-153">Provide a password to use when authenticating.</span></span> <span data-ttu-id="31a0d-154">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="31a0d-154">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a0d-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31a0d-155">See Also</span></span>  
 <span data-ttu-id="31a0d-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="31a0d-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="31a0d-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="31a0d-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql)  
  
  
