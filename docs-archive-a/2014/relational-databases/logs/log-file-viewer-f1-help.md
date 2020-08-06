---
title: Aide sur la visionneuse du fichier journal via la touche F1 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.errorlog.f1
helpviewer_keywords:
- Log File Viewer
ms.assetid: 2243845c-4880-4aa0-9ee8-0a97a128996b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6eadb4baa4a47202b40a9cde1eca896022f31d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603990"
---
# <a name="log-file-viewer-f1-help"></a><span data-ttu-id="07bd9-102">Aide sur la visionneuse du fichier journal via la touche F1</span><span class="sxs-lookup"><span data-stu-id="07bd9-102">Log File Viewer F1 Help</span></span>
  <span data-ttu-id="07bd9-103">La visionneuse du fichier journal affiche les informations de journalisation de nombreux composants différents.</span><span class="sxs-lookup"><span data-stu-id="07bd9-103">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="07bd9-104">Après avoir ouvert la visionneuse du fichier journal, utilisez le volet **Sélectionner les journaux** pour sélectionner les journaux à afficher.</span><span class="sxs-lookup"><span data-stu-id="07bd9-104">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="07bd9-105">Chaque journal affiche des colonnes appropriées à ce type de journal.</span><span class="sxs-lookup"><span data-stu-id="07bd9-105">Each log displays columns appropriate to that kind of log.</span></span>  
  
 <span data-ttu-id="07bd9-106">Les journaux disponibles dépendent de la manière dont la visionneuse du fichier journal est ouverte.</span><span class="sxs-lookup"><span data-stu-id="07bd9-106">The logs that are available depend on how Log File Viewer is opened.</span></span> <span data-ttu-id="07bd9-107">Pour plus d’informations, consultez [Ouvrir la Visionneuse du fichier journal](open-log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="07bd9-107">For more information, see [Open Log File Viewer](open-log-file-viewer.md).</span></span>  
  
 <span data-ttu-id="07bd9-108">Vous pouvez configurer le nombre de lignes qui s’affichent pour les journaux d’audit dans la page **Explorateur d’objets SQL Server/Commandes** de la boîte de dialogue **Outils/Options** .</span><span class="sxs-lookup"><span data-stu-id="07bd9-108">The number of rows that are displayed for audit logs can be configured on the **SQL Server Object Explorer/Commands** page of the **Tools/Options** dialog box.</span></span> <span data-ttu-id="07bd9-109">Pour obtenir la description des colonnes qui s’affichent pour les journaux d’audit, consultez [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="07bd9-109">For descriptions of the columns that are displayed for audit logs, see [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="07bd9-110">Options</span><span class="sxs-lookup"><span data-stu-id="07bd9-110">Options</span></span>  
 <span data-ttu-id="07bd9-111">**Charger le journal**</span><span class="sxs-lookup"><span data-stu-id="07bd9-111">**Load Log**</span></span>  
 <span data-ttu-id="07bd9-112">Ouvre une boîte de dialogue dans laquelle vous pouvez spécifier un fichier journal à charger.</span><span class="sxs-lookup"><span data-stu-id="07bd9-112">Open a dialog box where you can specify a log file to load.</span></span>  
  
 <span data-ttu-id="07bd9-113">**Export**</span><span class="sxs-lookup"><span data-stu-id="07bd9-113">**Export**</span></span>  
 <span data-ttu-id="07bd9-114">Ouvre une boîte de dialogue qui vous permet d’exporter les informations figurant dans la grille **Résumé du fichier journal** vers un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="07bd9-114">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
 <span data-ttu-id="07bd9-115">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="07bd9-115">**Refresh**</span></span>  
 <span data-ttu-id="07bd9-116">Actualise l'affichage des journaux sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="07bd9-116">Refresh the view of the selected logs.</span></span> <span data-ttu-id="07bd9-117">Le bouton **Actualiser** permet de relire les journaux sélectionnés à partir du serveur cible lors de l'application des paramètres de filtre.</span><span class="sxs-lookup"><span data-stu-id="07bd9-117">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
 <span data-ttu-id="07bd9-118">**Filter**</span><span class="sxs-lookup"><span data-stu-id="07bd9-118">**Filter**</span></span>  
 <span data-ttu-id="07bd9-119">Ouvre une boîte de dialogue qui vous permet de spécifier les paramètres utilisés pour filtrer le fichier journal, notamment **Connexion**, **Date**et d’autres critères de filtre **Général** .</span><span class="sxs-lookup"><span data-stu-id="07bd9-119">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
 <span data-ttu-id="07bd9-120">**action**</span><span class="sxs-lookup"><span data-stu-id="07bd9-120">**Search**</span></span>  
 <span data-ttu-id="07bd9-121">Permet de rechercher un texte spécifique dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="07bd9-121">Search the log file for specific text.</span></span> <span data-ttu-id="07bd9-122">La recherche des caractères génériques n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="07bd9-122">Searching with wildcard characters is not supported.</span></span>  
  
 <span data-ttu-id="07bd9-123">**Stop**</span><span class="sxs-lookup"><span data-stu-id="07bd9-123">**Stop**</span></span>  
 <span data-ttu-id="07bd9-124">Arrête le chargement des entrées du fichier-journal.</span><span class="sxs-lookup"><span data-stu-id="07bd9-124">Stops loading the log file entries.</span></span> <span data-ttu-id="07bd9-125">Par exemple, vous pouvez utiliser cette option si un fichier de journal distant ou hors connexion est long à charger, et que vous souhaitez seulement consulter les entrées les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="07bd9-125">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
 <span data-ttu-id="07bd9-126">**Résumé du fichier journal**</span><span class="sxs-lookup"><span data-stu-id="07bd9-126">**Log file summary**</span></span>  
 <span data-ttu-id="07bd9-127">Ce volet d'informations affiche un résumé du filtrage du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="07bd9-127">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="07bd9-128">Si le fichier n'est pas filtré, le texte suivant s'affiche : **Aucun filtre appliqué**.</span><span class="sxs-lookup"><span data-stu-id="07bd9-128">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="07bd9-129">Si un filtre est appliqué au journal, le texte suivant s’affiche : **Filtrer les entrées du journal pour :** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="07bd9-129">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
 <span data-ttu-id="07bd9-130">**Détails de la ligne sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="07bd9-130">**Selected row details**</span></span>  
 <span data-ttu-id="07bd9-131">Sélectionnez une ligne pour afficher des détails supplémentaires sur la ligne d'événement sélectionnée en bas de la page.</span><span class="sxs-lookup"><span data-stu-id="07bd9-131">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="07bd9-132">Vous pouvez changer l'ordre des colonnes en les faisant glisser sur la grille.</span><span class="sxs-lookup"><span data-stu-id="07bd9-132">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="07bd9-133">Vous pouvez redimensionner les colonnes en faisant glisser les barres de séparation des colonnes dans l'en-tête de la grille vers la gauche ou la droite.</span><span class="sxs-lookup"><span data-stu-id="07bd9-133">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="07bd9-134">Double-cliquez sur les barres de séparation des colonnes dans l'en-tête de la grille pour ajuster automatiquement la largeur de la colonne au contenu.</span><span class="sxs-lookup"><span data-stu-id="07bd9-134">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
 <span data-ttu-id="07bd9-135">**Instance**</span><span class="sxs-lookup"><span data-stu-id="07bd9-135">**Instance**</span></span>  
 <span data-ttu-id="07bd9-136">Nom de l'instance pour laquelle l'événement s'est produit.</span><span class="sxs-lookup"><span data-stu-id="07bd9-136">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="07bd9-137">Il est affiché sous la forme *nom de l'ordinateur*\\*nom de l'instance*.</span><span class="sxs-lookup"><span data-stu-id="07bd9-137">This is displayed as *computer name*\\*instance name*.</span></span>  
  
## <a name="frequently-displayed-columns"></a><span data-ttu-id="07bd9-138">Colonnes fréquemment affichées</span><span class="sxs-lookup"><span data-stu-id="07bd9-138">Frequently Displayed Columns</span></span>  
 <span data-ttu-id="07bd9-139">**Date**</span><span class="sxs-lookup"><span data-stu-id="07bd9-139">**Date**</span></span>  
 <span data-ttu-id="07bd9-140">Affiche la date de l'événement.</span><span class="sxs-lookup"><span data-stu-id="07bd9-140">Displays the date of the event.</span></span>  
  
 <span data-ttu-id="07bd9-141">**Source**</span><span class="sxs-lookup"><span data-stu-id="07bd9-141">**Source**</span></span>  
 <span data-ttu-id="07bd9-142">Affiche la fonctionnalité source à partir de laquelle l'événement est créé, par exemple le nom du service (comme MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="07bd9-142">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="07bd9-143">Ceci n'apparaît pas pour tous les types de journaux.</span><span class="sxs-lookup"><span data-stu-id="07bd9-143">This does not appear for all log types.</span></span>  
  
 <span data-ttu-id="07bd9-144">**Message**</span><span class="sxs-lookup"><span data-stu-id="07bd9-144">**Message**</span></span>  
 <span data-ttu-id="07bd9-145">Affiche les messages associés à l'événement.</span><span class="sxs-lookup"><span data-stu-id="07bd9-145">Displays any messages associated with the event.</span></span>  
  
 <span data-ttu-id="07bd9-146">**Type de journal**</span><span class="sxs-lookup"><span data-stu-id="07bd9-146">**Log Type**</span></span>  
 <span data-ttu-id="07bd9-147">Affiche le type de journal auquel appartient l'événement.</span><span class="sxs-lookup"><span data-stu-id="07bd9-147">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="07bd9-148">Tous les journaux sélectionnés s'affichent dans la fenêtre de résumé du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="07bd9-148">All selected logs appear in the log file summary window.</span></span>  
  
 <span data-ttu-id="07bd9-149">**Source du journal**</span><span class="sxs-lookup"><span data-stu-id="07bd9-149">**Log Source**</span></span>  
 <span data-ttu-id="07bd9-150">Affiche une description du journal source dans lequel l'événement est capturé.</span><span class="sxs-lookup"><span data-stu-id="07bd9-150">Displays a description of the source log in which the event is captured.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="07bd9-151">Autorisations</span><span class="sxs-lookup"><span data-stu-id="07bd9-151">Permissions</span></span>  
 <span data-ttu-id="07bd9-152">Pour accéder aux fichiers journaux pour les instances de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui sont en ligne, l’appartenance au rôle serveur fixe securityadmin est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="07bd9-152">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="07bd9-153">L’accès aux fichiers journaux des instances [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hors connexion nécessite un accès en lecture à l’espace de noms WMI **Root\Microsoft\SqlServer\ComputerManagement10** et au dossier où sont stockés les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="07bd9-153">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="07bd9-154">Pour plus d’informations, consultez la section Sécurité de la rubrique [Afficher les fichiers journaux hors connexion](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="07bd9-154">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07bd9-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07bd9-155">See Also</span></span>  
 <span data-ttu-id="07bd9-156">[Visionneuse du fichier journal](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="07bd9-156">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="07bd9-157">[Ouvrir la Visionneuse du fichier journal](open-log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="07bd9-157">[Open Log File Viewer](open-log-file-viewer.md) </span></span>  
 [<span data-ttu-id="07bd9-158">Afficher les fichiers journaux hors connexion</span><span class="sxs-lookup"><span data-stu-id="07bd9-158">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
