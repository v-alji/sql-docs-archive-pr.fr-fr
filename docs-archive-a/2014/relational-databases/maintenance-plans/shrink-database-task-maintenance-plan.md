---
title: Tâche Réduire la base de données (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.shrink.f1
- Shrink Database Task
- Shrink Database(s) Task
helpviewer_keywords:
- Shrink Database Task dialog box
ms.assetid: a9874cac-cded-4145-9c38-8aafd267dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8ee6060a4ee6ca3272434cf3d9115638a675e62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699534"
---
# <a name="shrink-database-task-maintenance-plan"></a><span data-ttu-id="1bbd2-102">Tâche Réduire la base de données (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="1bbd2-102">Shrink Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="1bbd2-103">Utilisez la boîte de dialogue **Tâche Réduire la base de données** pour créer une tâche qui tente de réduire la taille des bases de données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-103">Use the **Shrink Database Task** dialog to create a task that attempts to reduce the size of the selected databases.</span></span> <span data-ttu-id="1bbd2-104">Utilisez les options ci-dessous pour déterminer la quantité d'espace inutilisé à conserver dans la base de données après sa réduction (plus le pourcentage est élevé, moins la base la base de données sera réduite).</span><span class="sxs-lookup"><span data-stu-id="1bbd2-104">Use the options below to determine the amount of unused space to remain in the database after the database is shrunk (the larger the percentage, the less the database can shrink).</span></span> <span data-ttu-id="1bbd2-105">La valeur est calculée à partir du pourcentage des données effectivement présentes dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-105">The value is based on the percentage of the actual data in the database.</span></span> <span data-ttu-id="1bbd2-106">Par exemple, une base de données de 100 Mo qui contiendrait 60 Mo de données et 40 Mo d'espace libre, avec un pourcentage d'espace libre de 50 %, pourrait conduire à 60 Mo de données et 30 Mo d'espace libre (en effet, 50 % de 60 Mo font 30 Mo).</span><span class="sxs-lookup"><span data-stu-id="1bbd2-106">For example, a 100-MB database containing 60 MB of data and 40 MB of free space, with a free space percentage of 50 percent, would result in 60 MB of data and 30 MB of free space (because 50 percent of 60 MB is 30 MB).</span></span> <span data-ttu-id="1bbd2-107">Seul l'espace supplémentaire de la base de données est éliminé.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-107">Only excess space in the database is eliminated.</span></span> <span data-ttu-id="1bbd2-108">Les valeurs valides sont comprises entre 0 et 100.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-108">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="1bbd2-109">La réduction des fichiers de données permet de récupérer de l'espace en déplaçant des pages de données de la fin du fichier vers un espace inoccupé plus proche de l'avant du fichier.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-109">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="1bbd2-110">Lorsqu'une quantité d'espace libre suffisante est créée à la fin du fichier, des pages de données à la fin du fichier peuvent être désallouées et retournées au système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-110">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="1bbd2-111">Les données qui sont déplacées pour réduire un fichier peuvent être dispersées à n'importe quel emplacement disponible dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-111">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="1bbd2-112">Cela provoque la fragmentation de l'index et peut ralentir les performances des requêtes qui recherchent une plage de l'index.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-112">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="1bbd2-113">Pour éliminer la fragmentation, reconstruisez les index dans le fichier après réduction.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-113">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
 <span data-ttu-id="1bbd2-114">Cette tâche exécute l'instruction DBCC SHRINKDATABASE.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-114">This task executes the DBCC SHRINKDATABASE statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1bbd2-115">Options</span><span class="sxs-lookup"><span data-stu-id="1bbd2-115">Options</span></span>  
 <span data-ttu-id="1bbd2-116">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-116">**Connection**</span></span>  
 <span data-ttu-id="1bbd2-117">Sélectionnez la connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-117">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="1bbd2-118">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-118">**New**</span></span>  
 <span data-ttu-id="1bbd2-119">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-119">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="1bbd2-120">La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-120">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="1bbd2-121">**Bases de données**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-121">**Databases**</span></span>  
 <span data-ttu-id="1bbd2-122">Spécifie les bases de données faisant l'objet de cette tâche.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-122">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="1bbd2-123">**Toutes les bases de données**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-123">**All databases**</span></span>  
  
     <span data-ttu-id="1bbd2-124">Génère un plan de maintenance qui exécute les tâches de maintenance sur toutes les bases de données [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], à l’exception de tempdb.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-124">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="1bbd2-125">**Toutes les bases de données système**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-125">**All system databases**</span></span>  
  
     <span data-ttu-id="1bbd2-126">Génère un plan de maintenance qui exécute des tâches de maintenance sur chaque base de données système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à l'exception de tempdb.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-126">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="1bbd2-127">Aucune tâche de maintenance n'est exécutée sur les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-127">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="1bbd2-128">**Toutes les bases de données utilisateur**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-128">**All user databases**</span></span>  
  
     <span data-ttu-id="1bbd2-129">Génère un plan de maintenance qui exécute des tâches de maintenance sur toutes les bases de données créées par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-129">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="1bbd2-130">Aucune tâche de maintenance n'est exécutée sur les bases de données système de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bbd2-130">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="1bbd2-131">**Ces bases de données**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-131">**These databases**</span></span>  
  
     <span data-ttu-id="1bbd2-132">Génère un plan de maintenance qui n'exécute les tâches de maintenance que sur les bases de données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-132">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="1bbd2-133">Si vous choisissez cette option, sélectionnez au moins une base de données.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-133">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1bbd2-134">Les plans de maintenance sont exécutés uniquement sur des bases de données définies au niveau de compatibilité 80 ou plus.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-134">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="1bbd2-135">Les bases de données définies au niveau de compatibilité 70 ou moins ne sont pas affichées.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-135">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="1bbd2-136">**Réduire la base de données lorsqu'elle excède**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-136">**Shrink database when it grows beyond**</span></span>  
 <span data-ttu-id="1bbd2-137">Indiquez la taille de base de données (en mégaoctets) qui doit être atteinte pour que l'exécution de la tâche soit déclenchée.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-137">Specify the size in megabytes that causes the task to execute.</span></span>  
  
 <span data-ttu-id="1bbd2-138">**Quantité d'espace disponible restant après réduction**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-138">**Amount of free space to remain after shrink**</span></span>  
 <span data-ttu-id="1bbd2-139">Arrête la réduction lorsque l'espace libre dans les fichiers de base de données atteint cette taille.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-139">Stop shrinking when free space in database files reaches this size.</span></span>  
  
 <span data-ttu-id="1bbd2-140">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-140">**View T-SQL**</span></span>  
 <span data-ttu-id="1bbd2-141">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-141">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bbd2-142">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-142">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="1bbd2-143">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="1bbd2-143">New Connection Dialog Box</span></span>  
 <span data-ttu-id="1bbd2-144">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-144">**Connection name**</span></span>  
 <span data-ttu-id="1bbd2-145">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-145">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="1bbd2-146">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-146">**Select or enter a server name**</span></span>  
 <span data-ttu-id="1bbd2-147">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-147">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="1bbd2-148">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-148">**Refresh**</span></span>  
 <span data-ttu-id="1bbd2-149">Actualise la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-149">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="1bbd2-150">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-150">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="1bbd2-151">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-151">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="1bbd2-152">**Utiliser la sécurité intégrée de Windows NT**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-152">**Use Windows NT Integrated security**</span></span>  
 <span data-ttu-id="1bbd2-153">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec l’authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-153">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="1bbd2-154">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-154">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="1bbd2-155">Permet de se connecter à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bbd2-155">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="1bbd2-156">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-156">This option is not available.</span></span>  
  
 <span data-ttu-id="1bbd2-157">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-157">**User name**</span></span>  
 <span data-ttu-id="1bbd2-158">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-158">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="1bbd2-159">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-159">This option is not available.</span></span>  
  
 <span data-ttu-id="1bbd2-160">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="1bbd2-160">**Password**</span></span>  
 <span data-ttu-id="1bbd2-161">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-161">Provide a password to use when authenticating.</span></span> <span data-ttu-id="1bbd2-162">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="1bbd2-162">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bbd2-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1bbd2-163">See Also</span></span>  
 [<span data-ttu-id="1bbd2-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1bbd2-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql)  
  
  
