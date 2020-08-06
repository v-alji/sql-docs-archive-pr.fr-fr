---
title: Tâche Reconstruire l’index (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reindex.f1
- reindex
helpviewer_keywords:
- Rebuild Index Task dialog box
ms.assetid: 33e2940b-139f-4563-b0cb-5683f08bd879
author: rothja
ms.author: jroth
ms.openlocfilehash: bc9d7c85a72c34cee1ef7af8cb4b4f25f918a3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603968"
---
# <a name="rebuild-index-task-maintenance-plan"></a><span data-ttu-id="b55e0-102">Tâche Reconstruire l'index (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="b55e0-102">Rebuild Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="b55e0-103">Utilisez la boîte de dialogue **Tâche Reconstruire l’index** pour recréer les index des tables de la base de données en définissant un nouveau facteur de remplissage.</span><span class="sxs-lookup"><span data-stu-id="b55e0-103">Use the **Rebuild Index Task** dialog to re-create the indexes on the tables in the database with a new fill factor.</span></span> <span data-ttu-id="b55e0-104">Le facteur de remplissage détermine la quantité d'espace disponible sur chaque page de l'index pour permettre l'extension ultérieure de l'index.</span><span class="sxs-lookup"><span data-stu-id="b55e0-104">The fill factor determines the amount of empty space on each page in the index, to accommodate future expansion.</span></span> <span data-ttu-id="b55e0-105">Au fur et à mesure que des données sont ajoutées à la table, l'espace libre se remplit parce que le facteur de remplissage n'est pas conservé.</span><span class="sxs-lookup"><span data-stu-id="b55e0-105">As data is added to the table, the free space fills because the fill factor is not maintained.</span></span> <span data-ttu-id="b55e0-106">Réorganiser les pages d'index et les données permet de recouvrer de l'espace libre.</span><span class="sxs-lookup"><span data-stu-id="b55e0-106">Reorganizing data and index pages can re-establish the free space.</span></span>  
  
 <span data-ttu-id="b55e0-107">La **Tâche Reconstruire l'index** utilise l'instruction ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="b55e0-107">The **Rebuild Index Task** uses the ALTER INDEX statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b55e0-108">Options</span><span class="sxs-lookup"><span data-stu-id="b55e0-108">Options</span></span>  
 <span data-ttu-id="b55e0-109">**Connection**</span><span class="sxs-lookup"><span data-stu-id="b55e0-109">**Connection**</span></span>  
 <span data-ttu-id="b55e0-110">Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="b55e0-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="b55e0-111">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="b55e0-111">**New**</span></span>  
 <span data-ttu-id="b55e0-112">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="b55e0-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="b55e0-113">La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b55e0-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="b55e0-114">**Bases de données**</span><span class="sxs-lookup"><span data-stu-id="b55e0-114">**Databases**</span></span>  
 <span data-ttu-id="b55e0-115">Spécifie les bases de données faisant l'objet de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="b55e0-115">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="b55e0-116">**Toutes les bases de données**</span><span class="sxs-lookup"><span data-stu-id="b55e0-116">**All databases**</span></span>  
  
     <span data-ttu-id="b55e0-117">Génère un plan de maintenance qui exécute des tâches de maintenance sur toutes les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à l'exception de tempdb.</span><span class="sxs-lookup"><span data-stu-id="b55e0-117">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="b55e0-118">**Toutes les bases de données système**</span><span class="sxs-lookup"><span data-stu-id="b55e0-118">**All system databases**</span></span>  
  
     <span data-ttu-id="b55e0-119">Génère un plan de maintenance qui exécute des tâches de maintenance sur chaque base de données système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à l'exception de tempdb.</span><span class="sxs-lookup"><span data-stu-id="b55e0-119">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="b55e0-120">Aucune tâche de maintenance n'est exécutée sur les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b55e0-120">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="b55e0-121">**Toutes les bases de données utilisateur**</span><span class="sxs-lookup"><span data-stu-id="b55e0-121">**All user databases**</span></span>  
  
     <span data-ttu-id="b55e0-122">Génère un plan de maintenance qui exécute des tâches de maintenance sur toutes les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b55e0-122">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="b55e0-123">Aucune tâche de maintenance n'est exécutée sur les bases de données système de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b55e0-123">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="b55e0-124">**Ces bases de données**</span><span class="sxs-lookup"><span data-stu-id="b55e0-124">**These specific databases**</span></span>  
  
     <span data-ttu-id="b55e0-125">Génère un plan de maintenance qui n'exécute les tâches de maintenance que sur les bases de données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="b55e0-125">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="b55e0-126">Si vous choisissez cette option, sélectionnez au moins une base de données.</span><span class="sxs-lookup"><span data-stu-id="b55e0-126">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b55e0-127">Les plans de maintenance sont exécutés uniquement sur des bases de données définies au niveau de compatibilité 80 ou plus.</span><span class="sxs-lookup"><span data-stu-id="b55e0-127">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="b55e0-128">Les bases de données définies au niveau de compatibilité 70 ou moins ne sont pas affichées.</span><span class="sxs-lookup"><span data-stu-id="b55e0-128">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="b55e0-129">**Object**</span><span class="sxs-lookup"><span data-stu-id="b55e0-129">**Object**</span></span>  
 <span data-ttu-id="b55e0-130">Limite la grille de **Sélection** à l’affichage des tables et/ou des vues.</span><span class="sxs-lookup"><span data-stu-id="b55e0-130">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="b55e0-131">**Sélection**</span><span class="sxs-lookup"><span data-stu-id="b55e0-131">**Selection**</span></span>  
 <span data-ttu-id="b55e0-132">Spécifie les tables ou les index faisant l'objet de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="b55e0-132">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="b55e0-133">Non disponible quand **Tables et vues** est sélectionné dans la zone Objet.</span><span class="sxs-lookup"><span data-stu-id="b55e0-133">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="b55e0-134">**Réorganiser les pages avec la quantité d'espace disponible par défaut**</span><span class="sxs-lookup"><span data-stu-id="b55e0-134">**Reorganize pages with the default amount of free space**</span></span>  
 <span data-ttu-id="b55e0-135">Permet de supprimer les index sur les tables de la base de données et de les recréer avec le facteur de remplissage spécifié lors de la création des index.</span><span class="sxs-lookup"><span data-stu-id="b55e0-135">Drop the indexes on the tables in the database and re-create them with the fill factor that was specified when the indexes were created.</span></span>  
  
 <span data-ttu-id="b55e0-136">**Modifier l’espace libre par pourcentage de page à**</span><span class="sxs-lookup"><span data-stu-id="b55e0-136">**Change free space per page percentage to**</span></span>  
 <span data-ttu-id="b55e0-137">Provoque la suppression des index des tables de la base de données et leur recréation avec un nouveau facteur de remplissage calculé automatiquement, la quantité d'espace libre spécifiée étant réservée dans les pages d'index.</span><span class="sxs-lookup"><span data-stu-id="b55e0-137">Drop the indexes on the tables in the database and re-create them with a new, automatically calculated fill factor, thereby reserving the specified amount of free space on the index pages.</span></span> <span data-ttu-id="b55e0-138">Plus le pourcentage est élevé, plus il y a d'espace libre réservé dans les pages d'index et plus l'index croît.</span><span class="sxs-lookup"><span data-stu-id="b55e0-138">The higher the percentage, the more free space is reserved on the index pages, and the larger the index grows.</span></span> <span data-ttu-id="b55e0-139">Les valeurs valides sont comprises entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="b55e0-139">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="b55e0-140">**Trier les résultats dans tempdb**</span><span class="sxs-lookup"><span data-stu-id="b55e0-140">**Sort results in tempdb**</span></span>  
 <span data-ttu-id="b55e0-141">Utilisez l' `SORT_IN_TEMPDB` option, qui détermine l’emplacement de stockage temporaire des résultats de tri intermédiaires générés pendant la création de l’index.</span><span class="sxs-lookup"><span data-stu-id="b55e0-141">Use the `SORT_IN_TEMPDB`option, which determines where the intermediate sort results, generated during index creation, are temporarily stored.</span></span> <span data-ttu-id="b55e0-142">Si aucune opération de tri n’est requise ou si le tri peut être effectué dans la mémoire, l’option `SORT_IN_TEMPDB`est ignorée.</span><span class="sxs-lookup"><span data-stu-id="b55e0-142">If a sort operation is not required, or if the sort can be performed in memory, the `SORT_IN_TEMPDB`option is ignored.</span></span>  
  
 <span data-ttu-id="b55e0-143">**Conserver l'index en ligne lors de la réindexation**</span><span class="sxs-lookup"><span data-stu-id="b55e0-143">**Keep index online while reindexing**</span></span>  
 <span data-ttu-id="b55e0-144">Utilisez l'option `ONLINE` qui permet aux utilisateurs d'accéder à la table sous-jacente ou aux données d'index cluster, ainsi qu'à tous les index non-cluster associés au cours des opérations d'index.</span><span class="sxs-lookup"><span data-stu-id="b55e0-144">Use the `ONLINE` option which allows users to access the underlying table or clustered index data and any associated nonclustered indexes during index operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b55e0-145">Les opérations d’index en ligne ne sont pas disponibles dans toutes les éditions de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b55e0-145">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b55e0-146">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="b55e0-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="b55e0-147">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="b55e0-147">**View T-SQL**</span></span>  
 <span data-ttu-id="b55e0-148">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="b55e0-148">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b55e0-149">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="b55e0-149">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="b55e0-150">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="b55e0-150">New Connection Dialog Box</span></span>  
 <span data-ttu-id="b55e0-151">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="b55e0-151">**Connection name**</span></span>  
 <span data-ttu-id="b55e0-152">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="b55e0-152">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="b55e0-153">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="b55e0-153">**Select or enter a server name**</span></span>  
 <span data-ttu-id="b55e0-154">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="b55e0-154">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="b55e0-155">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="b55e0-155">**Refresh**</span></span>  
 <span data-ttu-id="b55e0-156">Actualise la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="b55e0-156">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="b55e0-157">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="b55e0-157">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="b55e0-158">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b55e0-158">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="b55e0-159">**Utiliser la sécurité intégrée à Windows NT**</span><span class="sxs-lookup"><span data-stu-id="b55e0-159">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="b55e0-160">Se connecte à une instance de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] à l'aide de l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="b55e0-160">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="b55e0-161">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="b55e0-161">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="b55e0-162">Se connecte à une instance de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] à l'aide de l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b55e0-162">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="b55e0-163">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b55e0-163">This option is not available.</span></span>  
  
 <span data-ttu-id="b55e0-164">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="b55e0-164">**User name**</span></span>  
 <span data-ttu-id="b55e0-165">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="b55e0-165">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="b55e0-166">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b55e0-166">This option is not available.</span></span>  
  
 <span data-ttu-id="b55e0-167">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="b55e0-167">**Password**</span></span>  
 <span data-ttu-id="b55e0-168">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="b55e0-168">Provide a password to use when authenticating.</span></span> <span data-ttu-id="b55e0-169">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b55e0-169">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b55e0-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b55e0-170">See Also</span></span>  
 <span data-ttu-id="b55e0-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b55e0-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="b55e0-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b55e0-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span></span>  
 <span data-ttu-id="b55e0-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b55e0-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="b55e0-174">[Option SORT_IN_TEMPDB pour les index](../indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="b55e0-174">[SORT_IN_TEMPDB Option For Indexes](../indexes/indexes.md) </span></span>  
 <span data-ttu-id="b55e0-175">[Instructions pour les opérations d'index en ligne](../indexes/guidelines-for-online-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="b55e0-175">[Guidelines for Online Index Operations](../indexes/guidelines-for-online-index-operations.md) </span></span>  
 <span data-ttu-id="b55e0-176">[Fonctionnement des opérations d'index en ligne](../indexes/how-online-index-operations-work.md) </span><span class="sxs-lookup"><span data-stu-id="b55e0-176">[How Online Index Operations Work](../indexes/how-online-index-operations-work.md) </span></span>  
 [<span data-ttu-id="b55e0-177">Exécuter des opérations en ligne sur les index</span><span class="sxs-lookup"><span data-stu-id="b55e0-177">Perform Index Operations Online</span></span>](../indexes/perform-index-operations-online.md)  
  
  
