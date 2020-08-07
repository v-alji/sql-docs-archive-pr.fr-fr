---
title: Afficher le journal des erreurs de SQL Server Agent (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- viewing SQL Server Agent error logs
- displaying SQL Server Agent error logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: de920425-fa44-469f-b83d-49e3f97e97f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: b88214a158a970a754c5f313bde3d53f2652ae73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703732"
---
# <a name="view-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="a6158-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a6158-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="a6158-103">Cette rubrique décrit comment afficher le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6158-103">This topic describes how to view the  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a6158-104">La visionneuse du fichier journal affiche les informations de journalisation de nombreux composants différents.</span><span class="sxs-lookup"><span data-stu-id="a6158-104">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="a6158-105">Après avoir ouvert la visionneuse du fichier journal, utilisez le volet **Sélectionner les journaux** pour sélectionner les journaux à afficher.</span><span class="sxs-lookup"><span data-stu-id="a6158-105">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="a6158-106">Chaque journal affiche des colonnes appropriées à ce type de journal.</span><span class="sxs-lookup"><span data-stu-id="a6158-106">Each log displays columns appropriate to that kind of log.</span></span> <span data-ttu-id="a6158-107">Les journaux disponibles dépendent de la manière dont la visionneuse du fichier journal est ouverte.</span><span class="sxs-lookup"><span data-stu-id="a6158-107">The logs that are available depend on how Log File Viewer is opened.</span></span>  
  
 <span data-ttu-id="a6158-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="a6158-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a6158-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="a6158-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a6158-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="a6158-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a6158-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a6158-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="a6158-112">Pour afficher le journal des erreurs de l'Agent SQL Server à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6158-112">To view the SQL Server Agent error log, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a6158-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a6158-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a6158-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="a6158-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a6158-115">Cependant, l'Explorateur d'objets affiche le nœud de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uniquement si vous avez l'autorisation de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="a6158-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a6158-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a6158-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a6158-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a6158-117">Permissions</span></span>  
 <span data-ttu-id="a6158-118">Pour exécuter ses fonctions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être configuré pour utiliser les informations d'identification d'un compte qui est membre du rôle serveur fixe **sysadmin** dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6158-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a6158-119">Le compte doit avoir les autorisations Windows suivantes :</span><span class="sxs-lookup"><span data-stu-id="a6158-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="a6158-120">Ouvrir une session en tant que service (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="a6158-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="a6158-121">Remplacer un jeton de niveau processus (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="a6158-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="a6158-122">Outrepasser le contrôle de parcours (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="a6158-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="a6158-123">Changer les quotas de mémoire d'un processus (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="a6158-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="a6158-124">Pour plus d’informations sur les autorisations Windows requises pour le compte de service de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent, consultez [Sélectionner un compte pour le service SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md) et configurer les [comptes de service Windows et les autorisations](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a6158-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a6158-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a6158-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-ssnoversion-agent-error-log"></a><span data-ttu-id="a6158-126">Pour afficher le journal des erreurs de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6158-126">To view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log</span></span>  
  
1.  <span data-ttu-id="a6158-127">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient le journal des erreurs de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="a6158-127">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to view.</span></span>  
  
2.  <span data-ttu-id="a6158-128">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a6158-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="a6158-129">Cliquez sur le signe plus (+) pour développer le dossier **Journaux d'erreurs** .</span><span class="sxs-lookup"><span data-stu-id="a6158-129">Click the plus sign to expand the **Error Logs** folder.</span></span>  
  
4.  <span data-ttu-id="a6158-130">Cliquez avec le bouton droit sur le journal d’erreurs que vous souhaitez afficher et sélectionnez **Afficher le journal de l’Agent**.</span><span class="sxs-lookup"><span data-stu-id="a6158-130">Right-click the error log you want to view and select **View Agent Log**.</span></span>  
  
     <span data-ttu-id="a6158-131">Les options suivantes sont disponibles dans la boîte de dialogue **Visionneuse du fichier journal -**_nom_serveur_ :</span><span class="sxs-lookup"><span data-stu-id="a6158-131">The following options are available in the **Log File Viewer -**_server_name_ dialog box:</span></span>  
  
     <span data-ttu-id="a6158-132">**Charger le journal**</span><span class="sxs-lookup"><span data-stu-id="a6158-132">**Load Log**</span></span>  
     <span data-ttu-id="a6158-133">Ouvre une boîte de dialogue dans laquelle vous pouvez spécifier un fichier journal à charger.</span><span class="sxs-lookup"><span data-stu-id="a6158-133">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="a6158-134">**Export**</span><span class="sxs-lookup"><span data-stu-id="a6158-134">**Export**</span></span>  
     <span data-ttu-id="a6158-135">Ouvre une boîte de dialogue qui vous permet d’exporter les informations figurant dans la grille **Résumé du fichier journal** vers un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a6158-135">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="a6158-136">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="a6158-136">**Refresh**</span></span>  
     <span data-ttu-id="a6158-137">Actualise l'affichage des journaux sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="a6158-137">Refresh the view of the selected logs.</span></span> <span data-ttu-id="a6158-138">Le bouton **Actualiser** permet de relire les journaux sélectionnés à partir du serveur cible lors de l'application des paramètres de filtre.</span><span class="sxs-lookup"><span data-stu-id="a6158-138">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="a6158-139">**Filter**</span><span class="sxs-lookup"><span data-stu-id="a6158-139">**Filter**</span></span>  
     <span data-ttu-id="a6158-140">Ouvre une boîte de dialogue qui vous permet de spécifier les paramètres utilisés pour filtrer le fichier journal, notamment **Connexion**, **Date**et d’autres critères de filtre **Général** .</span><span class="sxs-lookup"><span data-stu-id="a6158-140">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="a6158-141">**action**</span><span class="sxs-lookup"><span data-stu-id="a6158-141">**Search**</span></span>  
     <span data-ttu-id="a6158-142">Permet de rechercher un texte spécifique dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="a6158-142">Search the log file for specific text.</span></span> <span data-ttu-id="a6158-143">La recherche des caractères génériques n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a6158-143">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="a6158-144">**Stop**</span><span class="sxs-lookup"><span data-stu-id="a6158-144">**Stop**</span></span>  
     <span data-ttu-id="a6158-145">Arrête le chargement des entrées du fichier-journal.</span><span class="sxs-lookup"><span data-stu-id="a6158-145">Stops loading the log file entries.</span></span> <span data-ttu-id="a6158-146">Par exemple, vous pouvez utiliser cette option si un fichier de journal distant ou hors connexion est long à charger, et que vous souhaitez seulement consulter les entrées les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="a6158-146">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="a6158-147">**Résumé du fichier journal**</span><span class="sxs-lookup"><span data-stu-id="a6158-147">**Log file summary**</span></span>  
     <span data-ttu-id="a6158-148">Ce volet d'informations affiche un résumé du filtrage du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="a6158-148">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="a6158-149">Si le fichier n'est pas filtré, le texte suivant s'affiche : **Aucun filtre appliqué**.</span><span class="sxs-lookup"><span data-stu-id="a6158-149">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="a6158-150">Si un filtre est appliqué au journal, le texte suivant s’affiche : **Filtrer les entrées du journal pour :** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="a6158-150">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="a6158-151">**Détails de la ligne sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="a6158-151">**Selected row details**</span></span>  
     <span data-ttu-id="a6158-152">Sélectionnez une ligne pour afficher des détails supplémentaires sur la ligne d'événement sélectionnée en bas de la page.</span><span class="sxs-lookup"><span data-stu-id="a6158-152">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="a6158-153">Vous pouvez changer l'ordre des colonnes en les faisant glisser sur la grille.</span><span class="sxs-lookup"><span data-stu-id="a6158-153">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="a6158-154">Vous pouvez redimensionner les colonnes en faisant glisser les barres de séparation des colonnes dans l'en-tête de la grille vers la gauche ou la droite.</span><span class="sxs-lookup"><span data-stu-id="a6158-154">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="a6158-155">Double-cliquez sur les barres de séparation des colonnes dans l'en-tête de la grille pour ajuster automatiquement la largeur de la colonne au contenu.</span><span class="sxs-lookup"><span data-stu-id="a6158-155">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="a6158-156">**Instance**</span><span class="sxs-lookup"><span data-stu-id="a6158-156">**Instance**</span></span>  
     <span data-ttu-id="a6158-157">Nom de l'instance pour laquelle l'événement s'est produit.</span><span class="sxs-lookup"><span data-stu-id="a6158-157">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="a6158-158">Il est affiché sous la forme *nom de l'ordinateur*\\*nom de l'instance*.</span><span class="sxs-lookup"><span data-stu-id="a6158-158">This is displayed as *computer name*\\*instance name*.</span></span>  
  
     <span data-ttu-id="a6158-159">**Date**</span><span class="sxs-lookup"><span data-stu-id="a6158-159">**Date**</span></span>  
     <span data-ttu-id="a6158-160">Affiche la date de l'événement.</span><span class="sxs-lookup"><span data-stu-id="a6158-160">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="a6158-161">**Source**</span><span class="sxs-lookup"><span data-stu-id="a6158-161">**Source**</span></span>  
     <span data-ttu-id="a6158-162">Affiche la fonctionnalité source à partir de laquelle l'événement est créé, par exemple le nom du service (comme MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="a6158-162">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="a6158-163">Ceci n'apparaît pas pour tous les types de journaux.</span><span class="sxs-lookup"><span data-stu-id="a6158-163">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="a6158-164">**Message**</span><span class="sxs-lookup"><span data-stu-id="a6158-164">**Message**</span></span>  
     <span data-ttu-id="a6158-165">Affiche les messages associés à l'événement.</span><span class="sxs-lookup"><span data-stu-id="a6158-165">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="a6158-166">**Type de journal**</span><span class="sxs-lookup"><span data-stu-id="a6158-166">**Log Type**</span></span>  
     <span data-ttu-id="a6158-167">Affiche le type de journal auquel appartient l'événement.</span><span class="sxs-lookup"><span data-stu-id="a6158-167">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="a6158-168">Tous les journaux sélectionnés s'affichent dans la fenêtre de résumé du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="a6158-168">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="a6158-169">**Source du journal**</span><span class="sxs-lookup"><span data-stu-id="a6158-169">**Log Source**</span></span>  
     <span data-ttu-id="a6158-170">Affiche une description du journal source dans lequel l'événement est capturé.</span><span class="sxs-lookup"><span data-stu-id="a6158-170">Displays a description of the source log in which the event is captured.</span></span>  
  
5.  <span data-ttu-id="a6158-171">Lorsque vous avez terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a6158-171">When finished, click **Close**.</span></span>  
  
  
