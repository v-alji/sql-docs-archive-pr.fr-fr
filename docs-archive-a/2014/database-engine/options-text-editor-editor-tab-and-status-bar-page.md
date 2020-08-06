---
title: 'Options (éditeur de texte : onglet Éditeur et page barre d’État) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.editorcontextsettings
- VS.ToolsOptionsPages.Text_Editor.EditorTabAndStatusBar
ms.assetid: e4815678-7885-4631-878f-c6a2b857ee05
author: rothja
ms.author: jroth
ms.openlocfilehash: 920b7d48b5f7a2472a521af21c8217b1adba486a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613128"
---
# <a name="options-text-editor-editor-tab-and-status-bar-page"></a><span data-ttu-id="5ba8a-102">Options (Éditeur de texte : onglet Éditeur et page Barre d’état)</span><span class="sxs-lookup"><span data-stu-id="5ba8a-102">Options (Text Editor: Editor Tab and Status Bar Page)</span></span>
  <span data-ttu-id="5ba8a-103">L' **onglet Éditeur et la page Barre d'état** vous permettent de personnaliser les informations affichées par les éditeurs de requête [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ba8a-103">The **Editor Tab and Status Bar Page** lets you customize the information displayed by the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Query Editors.</span></span> <span data-ttu-id="5ba8a-104">Vous pouvez spécifier le niveau d'informations affiché dans l'onglet et la barre d'état de la fenêtre Éditeur de requête, et indiquer si la barre d'état doit apparaître en haut ou en bas de la fenêtre de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-104">You can specify the level of information displayed in the tab and status bar of the Query Editor window, and whether the status bar appears at the top or bottom of the editor window.</span></span>  
  
## <a name="option-settings-by-editor"></a><span data-ttu-id="5ba8a-105">Paramètres d'option par éditeur</span><span class="sxs-lookup"><span data-stu-id="5ba8a-105">Option Settings by Editor</span></span>  
 <span data-ttu-id="5ba8a-106">L'onglet d'éditeur et la barre d'état sont disponibles dans tous les éditeurs [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , mais ils présentent différents niveaux de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-106">The editor tab and the status bar are available in all of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, but have different levels of functionality.</span></span>  
  
 <span data-ttu-id="5ba8a-107">L'Éditeur de requête du moteur de base de données peut se connecter à un groupe de serveurs, auquel cas il ouvre des connexions à toutes les instances dans le groupe de serveurs et peut exécuter simultanément la même requête sur chaque connexion.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-107">The Database Engine Query Editor can connect to a server group, in which case it opens connections to all the instances in the Server Group and can simultaneously run the same query on each connection.</span></span> <span data-ttu-id="5ba8a-108">Vous pouvez utiliser ce dialogue pour spécifier que la barre d'état offre des couleurs différentes en cas de connexion à plusieurs instances plutôt qu'à une seule. Pour modifier les options de résultats multi-serveur, utilisez la page [Options (Résultats de la requête/SQL Server/Multi-serveur)](../../2014/database-engine/options-query-results-sql-server-multi-server.md) .</span><span class="sxs-lookup"><span data-stu-id="5ba8a-108">You can use this dialog to specify that the status bar has different colors when connected to multiple instances rather than one instance.To change the multi-server results options, use the [Options (Query Results/SQL Server/Multi-Server)](../../2014/database-engine/options-query-results-sql-server-multi-server.md) page.</span></span>  
  
## <a name="status-bar-content"></a><span data-ttu-id="5ba8a-109">Contenu de la barre d'état</span><span class="sxs-lookup"><span data-stu-id="5ba8a-109">Status Bar Content</span></span>  
 <span data-ttu-id="5ba8a-110">Indique les informations qui apparaissent dans la barre d'état de l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-110">Specifies the information that appears in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="5ba8a-111">**Afficher la durée d'exécution**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-111">**Display execution time**</span></span>  
 <span data-ttu-id="5ba8a-112">Inclut l'heure d'exécution du script.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-112">Includes the script execution time.</span></span> <span data-ttu-id="5ba8a-113">Les paramètres sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="5ba8a-113">The settings are as follows:</span></span>  
  
 <span data-ttu-id="5ba8a-114">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-114">**None**</span></span>  
 <span data-ttu-id="5ba8a-115">La barre d'état n'affiche pas d'informations horaires.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-115">The status bar displays no time information.</span></span>  
  
 <span data-ttu-id="5ba8a-116">**Effet**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-116">**End**</span></span>  
 <span data-ttu-id="5ba8a-117">La barre d'état affiche l'heure réelle du jour pendant l'exécution du script.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-117">The status bar displays the current time of day while the script is running.</span></span> <span data-ttu-id="5ba8a-118">À l'achèvement du script, l'affichage indique l'heure du jour à laquelle le script s'est terminé.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-118">When the script completes, the display shows the time of day that the script completed.</span></span>  
  
 <span data-ttu-id="5ba8a-119">**Temps écoulé**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-119">**Elapsed**</span></span>  
 <span data-ttu-id="5ba8a-120">La barre d'état affiche la durée d'exécution du script.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-120">The status bar displays the length of time that the script has been running.</span></span> <span data-ttu-id="5ba8a-121">Lorsque le script s'achève, l'affichage indique la durée nécessaire pour exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-121">When the script completes, the display shows how much time was taken to run the script.</span></span>  
  
 <span data-ttu-id="5ba8a-122">**Inclure le nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-122">**Include database name**</span></span>  
 <span data-ttu-id="5ba8a-123">Inclut le nom de la base de données actuelle pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-123">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="5ba8a-124">Lorsque l'éditeur de requête s'affiche pour la première fois, il s'agit de la base de données par défaut pour le compte de connexion.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-124">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="5ba8a-125">Le contexte de base de données peut être modifié ultérieurement en utilisant l'instruction USE Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-125">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="5ba8a-126">**Inclut le nom de la connexion**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-126">**Include login name**</span></span>  
 <span data-ttu-id="5ba8a-127">Inclut le nom de la connexion.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-127">Includes the login name.</span></span>  
  
 <span data-ttu-id="5ba8a-128">**Inclure le nombre de lignes**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-128">**Include row count**</span></span>  
 <span data-ttu-id="5ba8a-129">Inclut un nombre de lignes qui ont été traitées par le script en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-129">Includes a count of the rows that have been processed by the script that is currently executing.</span></span>  
  
 <span data-ttu-id="5ba8a-130">**Inclure le nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-130">**Include server name**</span></span>  
 <span data-ttu-id="5ba8a-131">Inclut le nom du serveur.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-131">Includes the server name.</span></span> <span data-ttu-id="5ba8a-132">Pour les connexions locales, il s'agit du nom de l'instance.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-132">For local connections, this is the instance name.</span></span> <span data-ttu-id="5ba8a-133">Pour les connexions distantes, il s'agit du nom de l'ordinateur distant et du nom de l'instance.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-133">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="status-bar-layout-and-colors"></a><span data-ttu-id="5ba8a-134">Couleurs et disposition de la barre d'état</span><span class="sxs-lookup"><span data-stu-id="5ba8a-134">Status Bar Layout and Colors</span></span>  
 <span data-ttu-id="5ba8a-135">Spécifie les couleurs des éléments de la barre d'état de l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-135">Specifies the colors for items in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="5ba8a-136">**Grouper les connexions**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-136">**Group connections**</span></span>  
 <span data-ttu-id="5ba8a-137">Définit la couleur de la barre d'état lorsque l'éditeur de requête a plusieurs connexions.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-137">Set the color of the status bar when the Query Editor has more than one connection.</span></span>  
  
 <span data-ttu-id="5ba8a-138">**Connexions à un seul serveur**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-138">**Single server connections**</span></span>  
 <span data-ttu-id="5ba8a-139">Définit la couleur de la barre d'état lorsque l'éditeur de requête a une seule connexion.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-139">Set the color of the status bar when the Query Editor has one connection.</span></span>  
  
 <span data-ttu-id="5ba8a-140">**Emplacement de la barre d'état**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-140">**Status bar location**</span></span>  
 <span data-ttu-id="5ba8a-141">Spécifie l'emplacement de la barre d'état.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-141">Specifies the location of the status bar.</span></span> <span data-ttu-id="5ba8a-142">Les paramètres sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="5ba8a-142">The settings are as follows:</span></span>  
  
 <span data-ttu-id="5ba8a-143">**Top**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-143">**Top**</span></span>  
 <span data-ttu-id="5ba8a-144">La barre d'état apparaît en haut de la fenêtre de l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-144">The status bar appears at the top of the Query Editor window.</span></span>  
  
 <span data-ttu-id="5ba8a-145">**Bas**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-145">**Bottom**</span></span>  
 <span data-ttu-id="5ba8a-146">La barre d'état apparaît au bas de la fenêtre de l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-146">The status bar appears at the bottom of the Query Editor window.</span></span>  
  
## <a name="tab-text"></a><span data-ttu-id="5ba8a-147">Texte de l'onglet</span><span class="sxs-lookup"><span data-stu-id="5ba8a-147">Tab Text</span></span>  
 <span data-ttu-id="5ba8a-148">Spécifie le texte qui apparaît dans l'onglet situé dans la partie supérieure d'une fenêtre de l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-148">Specifies the text that appears in the tab at the top of a Query Editor window.</span></span> <span data-ttu-id="5ba8a-149">Si le texte est trop long à afficher, vous pouvez consulter la chaîne complète dans l'info-bulle qui s'affiche lorsque vous pointez sur l'onglet.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-149">If the text is too long to display, you can view the full string in a tooltip that is displayed if you hover over the tab.</span></span>  
  
 <span data-ttu-id="5ba8a-150">**Inclure le nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-150">**Include database name**</span></span>  
 <span data-ttu-id="5ba8a-151">Inclut le nom de la base de données actuelle pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-151">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="5ba8a-152">Lorsque l'éditeur de requête s'affiche pour la première fois, il s'agit de la base de données par défaut pour le compte de connexion.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-152">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="5ba8a-153">Le contexte de base de données peut être modifié ultérieurement en utilisant l'instruction USE Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-153">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="5ba8a-154">**Inclure le nom du fichier**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-154">**Include file name**</span></span>  
 <span data-ttu-id="5ba8a-155">Inclut le nom du fichier où est stocké le script.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-155">Includes the name of the file where the script is stored.</span></span>  
  
 <span data-ttu-id="5ba8a-156">**Inclure le dossier**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-156">**Include folder name**</span></span>  
 <span data-ttu-id="5ba8a-157">Inclut le chemin d'accès du dossier où est stocké le fichier script.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-157">Includes the path of the folder where the script file is stored.</span></span>  
  
 <span data-ttu-id="5ba8a-158">**Inclut le nom de la connexion**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-158">**Include login name**</span></span>  
 <span data-ttu-id="5ba8a-159">Inclut le nom de la connexion.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-159">Includes the login name.</span></span>  
  
 <span data-ttu-id="5ba8a-160">**Inclure le nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="5ba8a-160">**Include server name**</span></span>  
 <span data-ttu-id="5ba8a-161">Inclut le nom du serveur.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-161">Includes the server name.</span></span> <span data-ttu-id="5ba8a-162">Pour les connexions locales, il s'agit du nom de l'instance.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-162">For local connections, this is the instance name.</span></span> <span data-ttu-id="5ba8a-163">Pour les connexions distantes, il s'agit du nom de l'ordinateur distant et du nom de l'instance.</span><span class="sxs-lookup"><span data-stu-id="5ba8a-163">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba8a-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ba8a-164">See Also</span></span>  
 <span data-ttu-id="5ba8a-165">[Options &#40;environnement : pages de polices et de couleurs&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span><span class="sxs-lookup"><span data-stu-id="5ba8a-165">[Options &#40;Environment: Fonts and Colors Page&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span></span>  
 [<span data-ttu-id="5ba8a-166">Codage en couleurs dans les éditeurs de requête</span><span class="sxs-lookup"><span data-stu-id="5ba8a-166">Color Coding in Query Editors</span></span>](../relational-databases/scripting/color-coding-in-query-editors.md)  
  
  
