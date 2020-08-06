---
title: Tâche de nettoyage de maintenance (Plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.cleanup.f1
helpviewer_keywords:
- Maintenance Cleanup Task dialog box
ms.assetid: 022b679c-6799-4c13-9185-814224a20412
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9023881ff5cf5ba5ddd8c61aa179c5881162bf44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610631"
---
# <a name="maintenance-cleanup-task-maintenance-plan"></a><span data-ttu-id="b9daa-102">Tâche de nettoyage de maintenance (Plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="b9daa-102">Maintenance Cleanup Task (Maintenance Plan)</span></span>
  <span data-ttu-id="b9daa-103">Utilisez la **Tâche de nettoyage de maintenance** pour supprimer les anciens fichiers associés à des plans de maintenance, notamment les rapports texte créés par les plans de maintenance et les fichiers de sauvegarde de base de données.</span><span class="sxs-lookup"><span data-stu-id="b9daa-103">Use the **Maintenance Cleanup Task** to remove old files related to maintenance plans, including text reports created by maintenance plans and database backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9daa-104">La tâche de nettoyage de maintenance ne supprime pas automatiquement les fichiers dans les sous-dossiers du répertoire spécifié.</span><span class="sxs-lookup"><span data-stu-id="b9daa-104">The Maintenance Cleanup task does not automatically delete files in the subfolders of the specified directory.</span></span> <span data-ttu-id="b9daa-105">Cette fonctionnalité réduit la possibilité d'une attaque malveillante qui utilise la tâche de nettoyage de maintenance pour supprimer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="b9daa-105">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span> <span data-ttu-id="b9daa-106">Pour supprimer des fichiers dans les sous-dossiers de premier niveau, vous devez sélectionner **Inclure les sous-dossiers de premier niveau**.</span><span class="sxs-lookup"><span data-stu-id="b9daa-106">If you want to delete files in first-level subfolders, you must select **Include first-level subfolders**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b9daa-107">Options</span><span class="sxs-lookup"><span data-stu-id="b9daa-107">Options</span></span>  
 <span data-ttu-id="b9daa-108">**Connection**</span><span class="sxs-lookup"><span data-stu-id="b9daa-108">**Connection**</span></span>  
 <span data-ttu-id="b9daa-109">Affiche la connexion active.</span><span class="sxs-lookup"><span data-stu-id="b9daa-109">Displays the current connection.</span></span>  
  
 <span data-ttu-id="b9daa-110">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="b9daa-110">**New**</span></span>  
 <span data-ttu-id="b9daa-111">Crée une nouvelle connexion serveur à utiliser pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="b9daa-111">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="b9daa-112">La boîte de dialogue **Nouvelle connexion** est décrite ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b9daa-112">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="b9daa-113">**Fichiers de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="b9daa-113">**Backup files**</span></span>  
 <span data-ttu-id="b9daa-114">Supprimez les fichiers de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b9daa-114">Delete backup files.</span></span>  
  
 <span data-ttu-id="b9daa-115">**Rapports de texte du plan de maintenance**</span><span class="sxs-lookup"><span data-stu-id="b9daa-115">**Maintenance Plan text reports**</span></span>  
 <span data-ttu-id="b9daa-116">Supprimez les rapports texte des plans de maintenance exécutés précédemment.</span><span class="sxs-lookup"><span data-stu-id="b9daa-116">Delete text reports of previously run maintenance plans.</span></span>  
  
 <span data-ttu-id="b9daa-117">**Supprimer un fichier spécifique**</span><span class="sxs-lookup"><span data-stu-id="b9daa-117">**Delete specific file**</span></span>  
 <span data-ttu-id="b9daa-118">Supprimez le fichier spécifié dans la zone **Nom de fichier** .</span><span class="sxs-lookup"><span data-stu-id="b9daa-118">Delete the specific file provided in the **File name** box.</span></span>  
  
 <span data-ttu-id="b9daa-119">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="b9daa-119">**File name**</span></span>  
 <span data-ttu-id="b9daa-120">Chemin d'accès et nom du fichier à supprimer.</span><span class="sxs-lookup"><span data-stu-id="b9daa-120">Path and name of the file to be deleted.</span></span>  
  
 <span data-ttu-id="b9daa-121">**Rechercher dans le dossier et supprimer les fichiers en fonction de l'extension**</span><span class="sxs-lookup"><span data-stu-id="b9daa-121">**Search folder and delete files based on an extension**</span></span>  
 <span data-ttu-id="b9daa-122">Supprimez tous les fichiers contenant l'extension spécifiée dans le dossier spécifié.</span><span class="sxs-lookup"><span data-stu-id="b9daa-122">Delete all files with the specified extension in the specified folder.</span></span> <span data-ttu-id="b9daa-123">Utilisez cette option pour supprimer plusieurs fichiers à la fois, par exemple tous les fichiers de sauvegarde possédant l'extension .bak dans le dossier Mardi.</span><span class="sxs-lookup"><span data-stu-id="b9daa-123">Use this to delete multiple files at once, such as all backup files with the .bak extension, in the Tuesday folder.</span></span>  
  
 <span data-ttu-id="b9daa-124">**Folder**</span><span class="sxs-lookup"><span data-stu-id="b9daa-124">**Folder**</span></span>  
 <span data-ttu-id="b9daa-125">Chemin d'accès et nom du dossier contenant les fichiers à supprimer.</span><span class="sxs-lookup"><span data-stu-id="b9daa-125">Path and name of the folder containing the files to be deleted.</span></span>  
  
 <span data-ttu-id="b9daa-126">**Extension de fichier**</span><span class="sxs-lookup"><span data-stu-id="b9daa-126">**File extension**</span></span>  
 <span data-ttu-id="b9daa-127">Spécifiez l'extension de fichier des fichiers à supprimer.</span><span class="sxs-lookup"><span data-stu-id="b9daa-127">Provide the file extension of the files to be deleted.</span></span>  
  
 <span data-ttu-id="b9daa-128">**Inclure les sous-dossiers de premier niveau**</span><span class="sxs-lookup"><span data-stu-id="b9daa-128">**Include first-level subfolders**</span></span>  
 <span data-ttu-id="b9daa-129">Supprimez les fichiers portant l’extension spécifiée pour l’option **Extension de fichier** , des sous-dossiers de premier niveau situés dans le dossier défini dans l’option **Dossier**.</span><span class="sxs-lookup"><span data-stu-id="b9daa-129">Delete files with the extension specified for **File extension** from first-level subfolders under **Folder**.</span></span>  
  
 <span data-ttu-id="b9daa-130">**Supprimer les fichiers en fonction de l'ancienneté du fichier au moment de l'exécution de la tâche**</span><span class="sxs-lookup"><span data-stu-id="b9daa-130">**Delete files based on the age of the file at task run time**</span></span>  
 <span data-ttu-id="b9daa-131">Spécifiez l’ancienneté minimale des fichiers à supprimer en entrant un chiffre et une unité de temps dans la zone **Supprimer les fichiers antérieurs à** .</span><span class="sxs-lookup"><span data-stu-id="b9daa-131">Specify the minimum age of the files that you want to delete by providing a number, and unit of time in the **Delete files older than the following** box.</span></span>  
  
 <span data-ttu-id="b9daa-132">**Supprimer les fichiers antérieurs à**</span><span class="sxs-lookup"><span data-stu-id="b9daa-132">**Delete files older than the following**</span></span>  
 <span data-ttu-id="b9daa-133">Spécifiez l'ancienneté minimale des fichiers à supprimer en fournissant un chiffre et une unité de temps (Jour, Semaine, Mois ou Année).</span><span class="sxs-lookup"><span data-stu-id="b9daa-133">Specify the minimum age of the files that you want to delete by providing a number, and unit of time (Day, Week, Month, or Year).</span></span> <span data-ttu-id="b9daa-134">Les fichiers antérieurs au délai spécifié seront supprimés.</span><span class="sxs-lookup"><span data-stu-id="b9daa-134">Files older than the time frame specified will be deleted.</span></span>  
  
 <span data-ttu-id="b9daa-135">**Vue T-SQL**</span><span class="sxs-lookup"><span data-stu-id="b9daa-135">**View T-SQL**</span></span>  
 <span data-ttu-id="b9daa-136">Affiche les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] exécutées sur le serveur pour cette tâche, selon les options sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="b9daa-136">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9daa-137">Si le nombre d'objets impliqués est élevé, l'affichage des instructions peut prendre un temps considérable.</span><span class="sxs-lookup"><span data-stu-id="b9daa-137">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="b9daa-138">Boîte de dialogue Nouvelle connexion</span><span class="sxs-lookup"><span data-stu-id="b9daa-138">New Connection Dialog Box</span></span>  
 <span data-ttu-id="b9daa-139">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="b9daa-139">**Connection name**</span></span>  
 <span data-ttu-id="b9daa-140">Entrez un nom pour la nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="b9daa-140">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="b9daa-141">**Sélectionnez ou entrez un nom de serveur.**</span><span class="sxs-lookup"><span data-stu-id="b9daa-141">**Select or enter a server name**</span></span>  
 <span data-ttu-id="b9daa-142">Sélectionnez un serveur auquel établir la connexion pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="b9daa-142">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="b9daa-143">**...**</span><span class="sxs-lookup"><span data-stu-id="b9daa-143">**...**</span></span>  
 <span data-ttu-id="b9daa-144">Sélectionnez cette option pour visualiser la liste des serveurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="b9daa-144">Select to view the list of available servers.</span></span>  
  
 <span data-ttu-id="b9daa-145">**Entrez des informations pour vous connecter au serveur**</span><span class="sxs-lookup"><span data-stu-id="b9daa-145">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="b9daa-146">Spécifiez le mode d'authentification sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b9daa-146">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="b9daa-147">**Utiliser la sécurité intégrée à Windows NT**</span><span class="sxs-lookup"><span data-stu-id="b9daa-147">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="b9daa-148">Permet de se connecter à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] en utilisant l'authentification Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="b9daa-148">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="b9daa-149">**Utiliser un nom d'utilisateur et un mot de passe spécifiques**</span><span class="sxs-lookup"><span data-stu-id="b9daa-149">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="b9daa-150">Permet de se connecter à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] à l'aide de l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b9daa-150">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="b9daa-151">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b9daa-151">This option is not available.</span></span>  
  
 <span data-ttu-id="b9daa-152">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="b9daa-152">**User name**</span></span>  
 <span data-ttu-id="b9daa-153">Fournit le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="b9daa-153">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="b9daa-154">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b9daa-154">This option is not available.</span></span>  
  
 <span data-ttu-id="b9daa-155">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="b9daa-155">**Password**</span></span>  
 <span data-ttu-id="b9daa-156">Fournit un mot de passe à utiliser pour l'authentification.</span><span class="sxs-lookup"><span data-stu-id="b9daa-156">Provide a password to use when authenticating.</span></span> <span data-ttu-id="b9daa-157">Cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b9daa-157">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9daa-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9daa-158">See Also</span></span>  
 [<span data-ttu-id="b9daa-159">Plans de maintenance</span><span class="sxs-lookup"><span data-stu-id="b9daa-159">Maintenance Plans</span></span>](maintenance-plans.md)  
  
  
