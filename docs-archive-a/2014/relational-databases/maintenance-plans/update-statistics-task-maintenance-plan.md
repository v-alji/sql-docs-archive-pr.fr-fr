---
title: Tâche Mettre à jour les statistiques (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.statistics.f1
helpviewer_keywords:
- Updates Statistics Task dialog box
ms.assetid: 22902fd0-eb39-4f18-af94-3fcb69d2a3a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486ef2da96785ed200900f497435117ef6437cb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614589"
---
# <a name="update-statistics-task-maintenance-plan"></a><span data-ttu-id="5b910-102">Tâche Mettre à jour les statistiques (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="5b910-102">Update Statistics Task (Maintenance Plan)</span></span>
  <span data-ttu-id="5b910-103">Utilisez la boîte de dialogue **Tâche Mettre à jour les statistiques** pour mettre à jour les informations [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relatives aux données des tables et des index.</span><span class="sxs-lookup"><span data-stu-id="5b910-103">Use the **Update Statistics Task** dialog to update [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information about the data in the tables and indexes.</span></span> <span data-ttu-id="5b910-104">Cette tâche rééchantillonne les statistiques de distribution de chaque index créé dans les tables utilisateur de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5b910-104">This task resamples the distribution statistics of each index created on user tables in the database.</span></span> <span data-ttu-id="5b910-105">Les statistiques de distribution servent à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour optimiser la navigation dans les tables pendant le traitement des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b910-105">The distribution statistics are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize navigation through tables during the processing of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="5b910-106">Pour collecter automatiquement les statistiques de distribution, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] échantillonne périodiquement les données de la table correspondant à chaque index.</span><span class="sxs-lookup"><span data-stu-id="5b910-106">To build the distribution statistics automatically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically samples the data in the corresponding table for each index.</span></span> <span data-ttu-id="5b910-107">La taille de cet échantillonnage est calculée en fonction du nombre de lignes de la table et de la fréquence de modification des données.</span><span class="sxs-lookup"><span data-stu-id="5b910-107">This size of the sample is based on the number of rows in the table and the frequency of data modification.</span></span> <span data-ttu-id="5b910-108">Utilisez cette option pour effectuer un échantillonnage supplémentaire à l'aide du pourcentage spécifié de données des tables.</span><span class="sxs-lookup"><span data-stu-id="5b910-108">Use this option to perform an additional sampling using the specified percentage of data in the tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5b910-109">utilise ces informations pour créer des plans de requête améliorés.</span><span class="sxs-lookup"><span data-stu-id="5b910-109">uses this information to create better query plans.</span></span>  
  
 <span data-ttu-id="5b910-110">Cette tâche exécute l'instruction UPDATE STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="5b910-110">This task executes the UPDATE STATISTICS statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5b910-111">Options</span><span class="sxs-lookup"><span data-stu-id="5b910-111">Options</span></span>  
 <span data-ttu-id="5b910-112">**Connection**</span><span class="sxs-lookup"><span data-stu-id="5b910-112">**Connection**</span></span>  
 <span data-ttu-id="5b910-113">Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="5b910-113">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="5b910-114">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="5b910-114">**New**</span></span>  
 <span data-ttu-id="5b910-115">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="5b910-115">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="5b910-116">La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="5b910-116">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="5b910-117">**Bases de données**</span><span class="sxs-lookup"><span data-stu-id="5b910-117">**Databases**</span></span>  
 <span data-ttu-id="5b910-118">Spécifie les bases de données faisant l'objet de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="5b910-118">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="5b910-119">**Toutes les bases de données**</span><span class="sxs-lookup"><span data-stu-id="5b910-119">**All databases**</span></span>  
  
     <span data-ttu-id="5b910-120">Génère un plan de maintenance qui exécute les tâches de maintenance sur toutes les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à l'exception de tempdb.</span><span class="sxs-lookup"><span data-stu-id="5b910-120">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, except tempdb.</span></span>  
  
-   <span data-ttu-id="5b910-121">**Toutes les bases de données système**</span><span class="sxs-lookup"><span data-stu-id="5b910-121">**All system databases**</span></span>  
  
     <span data-ttu-id="5b910-122">Génère un plan de maintenance qui exécute des tâches de maintenance sur chaque base de données système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à l'exception de tempdb.</span><span class="sxs-lookup"><span data-stu-id="5b910-122">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="5b910-123">Aucune tâche de maintenance n'est exécutée sur les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5b910-123">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="5b910-124">**Toutes les bases de données utilisateur**</span><span class="sxs-lookup"><span data-stu-id="5b910-124">**All user databases**</span></span>  
  
     <span data-ttu-id="5b910-125">Génère un plan de maintenance qui exécute des tâches de maintenance sur toutes les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5b910-125">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="5b910-126">Aucune tâche de maintenance n'est exécutée sur les bases de données système de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b910-126">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="5b910-127">**Ces bases de données**</span><span class="sxs-lookup"><span data-stu-id="5b910-127">**These specific databases**</span></span>  
  
     <span data-ttu-id="5b910-128">Génère un plan de maintenance qui n'exécute les tâches de maintenance que sur les bases de données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="5b910-128">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="5b910-129">Si vous choisissez cette option, sélectionnez au moins une base de données.</span><span class="sxs-lookup"><span data-stu-id="5b910-129">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="5b910-130">**Remarque** Les plans de maintenance sont exécutés uniquement sur des bases de données définies avec un niveau de compatibilité 80 ou plus.</span><span class="sxs-lookup"><span data-stu-id="5b910-130">**Note** Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="5b910-131">Les bases de données définies au niveau de compatibilité 70 ou moins ne sont pas affichées.</span><span class="sxs-lookup"><span data-stu-id="5b910-131">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="5b910-132">**Object**</span><span class="sxs-lookup"><span data-stu-id="5b910-132">**Object**</span></span>  
 <span data-ttu-id="5b910-133">Limite la grille de **Sélection** à l’affichage des tables et/ou des vues.</span><span class="sxs-lookup"><span data-stu-id="5b910-133">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="5b910-134">**Sélection**</span><span class="sxs-lookup"><span data-stu-id="5b910-134">**Selection**</span></span>  
 <span data-ttu-id="5b910-135">Spécifie les tables ou les index faisant l'objet de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="5b910-135">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="5b910-136">Non disponible quand **Tables et vues** est sélectionné dans la zone Objet.</span><span class="sxs-lookup"><span data-stu-id="5b910-136">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="5b910-137">**Toutes les statistiques existantes**</span><span class="sxs-lookup"><span data-stu-id="5b910-137">**All existing statistics**</span></span>  
 <span data-ttu-id="5b910-138">Met à jour les statistiques pour les colonnes et les index.</span><span class="sxs-lookup"><span data-stu-id="5b910-138">Update statistics for both columns and indexes.</span></span>  
  
 <span data-ttu-id="5b910-139">**Statistiques de colonnes uniquement**</span><span class="sxs-lookup"><span data-stu-id="5b910-139">**Column statistics only**</span></span>  
 <span data-ttu-id="5b910-140">Met à jour les statistiques de colonnes uniquement.</span><span class="sxs-lookup"><span data-stu-id="5b910-140">Only update column statistics.</span></span>  
  
 <span data-ttu-id="5b910-141">**Statistiques d'index uniquement**</span><span class="sxs-lookup"><span data-stu-id="5b910-141">**Index statistics only**</span></span>  
 <span data-ttu-id="5b910-142">Met à jour les statistiques d'index uniquement.</span><span class="sxs-lookup"><span data-stu-id="5b910-142">Only update index statistics.</span></span>  
  
 <span data-ttu-id="5b910-143">**Type d'analyse**</span><span class="sxs-lookup"><span data-stu-id="5b910-143">**Scan type**</span></span>  
 <span data-ttu-id="5b910-144">Type d'analyse destinée à la collecte des statistiques mises à jour.</span><span class="sxs-lookup"><span data-stu-id="5b910-144">Type of scan used to gather updated statistics.</span></span>  
  
 <span data-ttu-id="5b910-145">**Analyse complète**</span><span class="sxs-lookup"><span data-stu-id="5b910-145">**Full scan**</span></span>  
 <span data-ttu-id="5b910-146">Lit toutes les lignes de la table ou de la vue pour rassembler les statistiques.</span><span class="sxs-lookup"><span data-stu-id="5b910-146">Read all rows in the table or view to gather the statistics.</span></span>  
  
 <span data-ttu-id="5b910-147">**Exemple par**</span><span class="sxs-lookup"><span data-stu-id="5b910-147">**Sample by**</span></span>  
 <span data-ttu-id="5b910-148">Spécifie le pourcentage de la table ou de la vue indexée, ou le nombre de lignes à échantillonner lors de la collecte des statistiques de tables ou vues volumineuses.</span><span class="sxs-lookup"><span data-stu-id="5b910-148">Specify the percentage of the table or indexed view, or the number of rows to sample when collecting statistics for larger tables or views.</span></span>  
  
 <span data-ttu-id="5b910-149">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="5b910-149">**View T-SQL**</span></span>  
 <span data-ttu-id="5b910-150">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="5b910-150">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b910-151">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="5b910-151">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="5b910-152">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="5b910-152">New Connection Dialog Box</span></span>  
 <span data-ttu-id="5b910-153">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="5b910-153">**Connection name**</span></span>  
 <span data-ttu-id="5b910-154">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="5b910-154">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="5b910-155">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="5b910-155">**Select or enter a server name**</span></span>  
 <span data-ttu-id="5b910-156">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="5b910-156">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="5b910-157">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="5b910-157">**Refresh**</span></span>  
 <span data-ttu-id="5b910-158">Actualise la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="5b910-158">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="5b910-159">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="5b910-159">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="5b910-160">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="5b910-160">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="5b910-161">**Utiliser la sécurité intégrée à Windows NT**</span><span class="sxs-lookup"><span data-stu-id="5b910-161">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="5b910-162">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec l’authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="5b910-162">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="5b910-163">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="5b910-163">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="5b910-164">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b910-164">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="5b910-165">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="5b910-165">This option is not available.</span></span>  
  
 <span data-ttu-id="5b910-166">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="5b910-166">**User name**</span></span>  
 <span data-ttu-id="5b910-167">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="5b910-167">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="5b910-168">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="5b910-168">This option is not available.</span></span>  
  
 <span data-ttu-id="5b910-169">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="5b910-169">**Password**</span></span>  
 <span data-ttu-id="5b910-170">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="5b910-170">Provide a password to use when authenticating.</span></span> <span data-ttu-id="5b910-171">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="5b910-171">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b910-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5b910-172">See Also</span></span>  
 [<span data-ttu-id="5b910-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5b910-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
