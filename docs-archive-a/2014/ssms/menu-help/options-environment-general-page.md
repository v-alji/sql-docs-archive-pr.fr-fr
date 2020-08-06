---
title: Options (environnement-page général) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.SQLEnvironmentOptions
ms.assetid: c32ccdb8-2cf8-4c78-b474-a3abd3dbbd13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7712c568b478bd2ba958237ba3204246657b3a72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614965"
---
# <a name="options-environment-general-page"></a><span data-ttu-id="2cc2a-102">Options (Environnement - Page Général)</span><span class="sxs-lookup"><span data-stu-id="2cc2a-102">Options (Environment-General Page)</span></span>
  <span data-ttu-id="2cc2a-103">Utilisez la boîte de dialogue **Options** pour configurer les actions de démarrage [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], les options de gestion des fenêtres générales ainsi que d’autres paramètres généraux.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-103">Use the **Options** dialog box to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] startup actions, general window management options, and other general settings.</span></span> <span data-ttu-id="2cc2a-104">Dans le menu **Outils** , cliquez sur **Options**, développez le dossier **Environnement** , puis cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-104">On the **Tools** menu, click **Options**, expand the **Environment** folder, and then click **General**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2cc2a-105">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="2cc2a-105">UI element list</span></span>  
 <span data-ttu-id="2cc2a-106">**Au démarrage**</span><span class="sxs-lookup"><span data-stu-id="2cc2a-106">**At startup**</span></span>  
 <span data-ttu-id="2cc2a-107">Sélectionnez l'action que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] doit exécuter au démarrage.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-107">Select the action for [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to perform when it is started.</span></span> <span data-ttu-id="2cc2a-108">Les options sont :</span><span class="sxs-lookup"><span data-stu-id="2cc2a-108">The options are:</span></span>  
  
-   <span data-ttu-id="2cc2a-109">**Ouvrir l'Explorateur d'objets** : demande l'établissement d'une connexion, puis ouvre l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-109">**Open Object Explorer** prompts for a connection and then opens Object Explorer.</span></span>  
  
-   <span data-ttu-id="2cc2a-110">**Ouvrir la fenêtre de nouvelle requête** : demande l'établissement d'une connexion, puis ouvre l'Éditeur de requête SQL.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-110">**Open new query window** prompts for a connection and then opens SQL Query Editor.</span></span>  
  
-   <span data-ttu-id="2cc2a-111">**Ouvrir l'Explorateur d'objets et la nouvelle requête** : demande l'établissement d'une connexion, puis ouvre l'Explorateur d'objets et l'Éditeur de requête SQL également.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-111">**Open Object Explorer and new query** prompts for a connection, then opens both Object Explorer and SQL Query Editor with that connection.</span></span>  
  
-   <span data-ttu-id="2cc2a-112">**Ouvrir l'environnement vide** : ouvre [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sans la fenêtre de l'Éditeur de requête SQL et sans connecter l'Explorateur d'objets à un serveur.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-112">**Open empty environment** opens [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] without a SQL Query editor window and without connecting Object Explorer to a server.</span></span>  
  
 <span data-ttu-id="2cc2a-113">**Masquer les objets système dans l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="2cc2a-113">**Hide system objects in Object Explorer**</span></span>  
 <span data-ttu-id="2cc2a-114">Cocher cette case pour enlever les bases de données système, les tables système, les vues système et les procédures stockées système de l'arborescence de l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-114">Select this check box to remove the system databases, system tables, system views, and system stored procedures from tree view in Object Explorer.</span></span> <span data-ttu-id="2cc2a-115">Les fonctions système et les types de données système ne sont pas masqués.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-115">System functions and system data types are not hidden.</span></span> <span data-ttu-id="2cc2a-116">Cette option s'applique uniquement aux instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et n'affecte pas les serveurs déjà connectés à l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-116">This option only applies to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and does not affect servers already connected in Object Explorer.</span></span>  
  
## <a name="environment-layout"></a><span data-ttu-id="2cc2a-117">Disposition d'environnement</span><span class="sxs-lookup"><span data-stu-id="2cc2a-117">Environment Layout</span></span>  
 <span data-ttu-id="2cc2a-118">Vous devez fermer, puis rouvrir [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour passer du mode d'environnement documents avec onglet au mode d'environnement MDI.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-118">You must close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change between tabbed document and multiple-document interface (MDI) environment mode.</span></span>  
  
 <span data-ttu-id="2cc2a-119">**Documents avec onglet**</span><span class="sxs-lookup"><span data-stu-id="2cc2a-119">**Tabbed documents**</span></span>  
 <span data-ttu-id="2cc2a-120">Activez cette option pour afficher des fenêtres de documents reliées sous la forme d'onglets dans les éditeurs.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-120">Select this option to display document windows that are tabbed together within editors.</span></span> <span data-ttu-id="2cc2a-121">Les fenêtres de documents présentées sous la forme d'onglets s'avèrent utiles pour agencer plusieurs documents ouverts et pour passer d'un document à un autre.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-121">Tabbed document windows are useful for organizing and switching between multiple open documents.</span></span>  
  
 <span data-ttu-id="2cc2a-122">**Environnement MDI**</span><span class="sxs-lookup"><span data-stu-id="2cc2a-122">**MDI environment**</span></span>  
 <span data-ttu-id="2cc2a-123">Activez cette option pour ouvrir les documents dans un environnement MDI.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-123">Select this option to open documents in a MDI environment.</span></span> <span data-ttu-id="2cc2a-124">Les fenêtres de documents MDI s'avèrent utiles pour gagner de l'espace à l'écran (cet espace serait occupé par des onglets dans un environnement de documents avec onglet).</span><span class="sxs-lookup"><span data-stu-id="2cc2a-124">MDI document windows are useful for gaining the screen space that is otherwise taken up by the tabs in the tabbed documents environment.</span></span> <span data-ttu-id="2cc2a-125">Quand vous travaillez en mode MDI, vous pouvez passer d'un document à un autre en appuyant sur Ctrk+Tab ou vous pouvez utiliser les options de mosaïque du menu **Fenêtre** .</span><span class="sxs-lookup"><span data-stu-id="2cc2a-125">When working in MDI mode, you can switch between documents by pressing CTRL+TAB, or you can use the tile options located on the **Window** menu.</span></span>  
  
## <a name="docked-tool-window-behavior"></a><span data-ttu-id="2cc2a-126">Comportement de la fenêtre Outils ancrée</span><span class="sxs-lookup"><span data-stu-id="2cc2a-126">Docked Tool Window Behavior</span></span>  
 <span data-ttu-id="2cc2a-127">**Le bouton Fermer affecte uniquement l'onglet actif**</span><span class="sxs-lookup"><span data-stu-id="2cc2a-127">**Close button affects active tab only**</span></span>  
 <span data-ttu-id="2cc2a-128">Spécifie que ce bouton ne ferme que la fenêtre Outils qui est active et non les autres fenêtres Outils de l'ensemble ancré.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-128">Specifies that when this check box is selected, only the tool window that has focus currently is closed and not all of the tool windows in the docked set.</span></span> <span data-ttu-id="2cc2a-129">Par défaut, cette case à cocher est activée.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-129">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="2cc2a-130">**Le bouton Masquer automatiquement affecte uniquement l'onglet actif**</span><span class="sxs-lookup"><span data-stu-id="2cc2a-130">**Auto Hide button affects active tab only**</span></span>  
 <span data-ttu-id="2cc2a-131">Spécifie que ce bouton ne masque automatiquement que la fenêtre Outils qui est active et non les autres fenêtres Outils de l'ensemble ancré.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-131">Specifies that when this check box is selected, only the tool window that has focus currently is hidden automatically, not all of the tool windows in the docked set.</span></span> <span data-ttu-id="2cc2a-132">Par défaut, cette case est décochée.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-132">By default, this check box is cleared.</span></span>  
  
## <a name="display"></a><span data-ttu-id="2cc2a-133">Afficher</span><span class="sxs-lookup"><span data-stu-id="2cc2a-133">Display</span></span>  
 <span data-ttu-id="2cc2a-134">**Affiche n fichiers dans la liste des derniers fichiers utilisés**</span><span class="sxs-lookup"><span data-stu-id="2cc2a-134">**Display n files in recently used list**</span></span>  
 <span data-ttu-id="2cc2a-135">Personnalise le nombre de projets et de fichiers récents qui apparaissent dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="2cc2a-135">Customizes the number of recent projects and recent files that appear on the **File** menu.</span></span> <span data-ttu-id="2cc2a-136">Entrez un nombre compris entre 1 et 24.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-136">Type a number between 1 and 24.</span></span> <span data-ttu-id="2cc2a-137">Valeur par défaut : 4.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-137">The default is 4.</span></span> <span data-ttu-id="2cc2a-138">Vous pouvez ainsi facilement récupérer les projets de script et les fichiers récemment utilisés.</span><span class="sxs-lookup"><span data-stu-id="2cc2a-138">This is an easy way to retrieve recently used script projects and files and script projects.</span></span>  
  
  
