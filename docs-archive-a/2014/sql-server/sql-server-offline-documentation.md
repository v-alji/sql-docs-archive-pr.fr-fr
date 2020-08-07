---
title: Documents hors connexion pour SQL Server 2014
description: Découvrez comment installer la documentation hors connexion pour SQL Server 2014. Utilisez SQL Server Management Studio (SSMS) pour afficher le contenu hors connexion.
ms.prod: sql
ms.technology: install
ms.topic: conceptual
ms.assetid: 51f8a08c-51d0-41d8-8bc5-1cb4d42622fb
author: markingmyname
ms.author: maghan
ms.reviewer: carlrab
ms.date: 07/19/2020
ms.openlocfilehash: bfd4adc658a203f8e2d22ef77ce0381084e36363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604822"
---
# <a name="install-sql-server-2014-offline-documentation"></a><span data-ttu-id="ad0b4-104">Installer SQL Server Documentation hors connexion 2014</span><span class="sxs-lookup"><span data-stu-id="ad0b4-104">Install SQL Server 2014 offline documentation</span></span>

<span data-ttu-id="ad0b4-105">Cet article explique comment télécharger et afficher le contenu SQL Server 2014 hors connexion.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-105">This article describes how to download and view offline SQL Server 2014 content.</span></span> <span data-ttu-id="ad0b4-106">Le contenu hors connexion vous permet d’accéder à la documentation sans connexion Internet (bien qu’une connexion Internet soit initialement requise pour le téléchargement).</span><span class="sxs-lookup"><span data-stu-id="ad0b4-106">Offline content enables you to access the documentation without an internet connection (although an internet connection is initially required to download it).</span></span>

<span data-ttu-id="ad0b4-107">La technique implique l’utilisation du menu **aide** de SQL Server Management Studio (SSMS) pour accéder à l’utilitaire de la visionneuse d’aide (HlpViewer.exe).</span><span class="sxs-lookup"><span data-stu-id="ad0b4-107">The technique involves using the **Help** menu of SQL Server Management Studio (SSMS), to access the Help Viewer utility (HlpViewer.exe).</span></span>

<span data-ttu-id="ad0b4-108">La documentation hors connexion est disponible pour les versions de SQL Server dans la plage de 2012-2019, et peut-être également pour d’autres versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-108">Offline documentation is available for versions of SQL Server in the range of 2012-2019, and perhaps for additional later versions too.</span></span> <span data-ttu-id="ad0b4-109">Même si vous pouvez consulter le contenu des [versions précédentes en ligne](https://docs.microsoft.com/previous-versions/sql/), une option hors connexion offre un moyen pratique d’accéder à l’ancien contenu.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-109">Although you can view content for [previous versions online](https://docs.microsoft.com/previous-versions/sql/), an offline option provides a convenient way to access the older content.</span></span>

- [<span data-ttu-id="ad0b4-110">SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ad0b4-110">SQL Server 2014</span></span>](#sql-server-2014-offline-content)
- [<span data-ttu-id="ad0b4-111">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="ad0b4-111">SQL Server 2012</span></span>](#sql-server-2012-offline-content)

<span data-ttu-id="ad0b4-112">Pour plus d’SQL Server 2016 et versions ultérieures, consultez leur documentation spécifique à la version pour savoir comment ces versions gèrent leur documentation hors connexion.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-112">For SQL Server 2016 and later versions, see their version-specific documentation to learn how those versions handle their offline documentation.</span></span>

## <a name="sql-server-2014-offline-content"></a><span data-ttu-id="ad0b4-113">Contenu hors connexion pour SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ad0b4-113">SQL Server 2014 offline content</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad0b4-114">Le contenu Transact-SQL de SQL 2014 est uniquement disponible hors connexion.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-114">SQL 2014 Transact-SQL content is only available offline.</span></span>

<span data-ttu-id="ad0b4-115">Les étapes suivantes expliquent comment charger le contenu hors connexion de SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-115">The following steps explain how to load offline content for SQL Server 2014.</span></span>

1. <span data-ttu-id="ad0b4-116">Téléchargez la [documentation produit pour Microsoft SQL Server 2014 pour les environnements protégés par un pare-feu restreints par un proxy](https://www.microsoft.com/download/details.aspx?id=42557) à partir du centre de téléchargement et enregistrez-la dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-116">Download the [Product Documentation for Microsoft SQL Server 2014 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=42557) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="ad0b4-117">Décompressez le fichier pour afficher le fichier *. MSHA* .</span><span class="sxs-lookup"><span data-stu-id="ad0b4-117">Unzip the file to view the *.msha* file.</span></span>

   ![Fichier d’installation de la documentation d’aide de SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. <span data-ttu-id="ad0b4-119">Dans SSMS, sélectionnez **Ajouter et supprimer le contenu d’aide** dans le menu Aide.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-119">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![HelpViewer - Ajouter et supprimer le contenu](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="ad0b4-121">La visionneuse d’aide s’ouvre et affiche l’onglet Gérer le contenu.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-121">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="ad0b4-122">Pour installer le contenu d’aide le plus récent, choisissez **Disque** sous Source d’installation, puis cliquez sur les points de suspension (...).</span><span class="sxs-lookup"><span data-stu-id="ad0b4-122">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Visionneuse d’aide - Gérer la source du disque de contenu](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="ad0b4-124">L’option Chemin d’accès au stockage local sous l’onglet Gérer le contenu indique l’emplacement sur l’ordinateur local où est situé le contenu.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-124">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="ad0b4-125">Pour changer d’emplacement, sélectionnez **Déplacer**, entrez un chemin de dossier différent dans le champ **Vers**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-125">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="ad0b4-126">Si l’installation de l’aide échoue après avoir modifié le chemin d’accès du magasin local, fermez et rouvrez la visionneuse d’aide.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-126">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="ad0b4-127">Vérifiez que le nouvel emplacement apparaît dans le chemin d’accès du magasin local, puis recommencez l’installation.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-127">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="ad0b4-128">Localisez le dossier dans lequel vous avez décompressé le contenu.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-128">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="ad0b4-129">Sélectionnez le fichier **HelpContentSetup.msha** dans le dossier, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-129">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Ouvrir le fichier d’aide de SQL Server 2014 Setup.msha](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. <span data-ttu-id="ad0b4-131">Saisissez *SQL Server 2014* dans la barre de recherche.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-131">Type in *sql server 2014* in the search bar.</span></span> <span data-ttu-id="ad0b4-132">Une fois que vous voyez le contenu 2014 disponible, sélectionnez **Ajouter** en regard de chaque package de contenu (livre) que vous souhaitez installer dans la visionneuse d’aide, puis sélectionnez **Mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-132">Once you see the 2014 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Recherche de livres SQL Server 2014 dans la visionneuse d’aide](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Livres SQL Server 2014 - Ajouter et mettre à jour dans la visionneuse d’aide](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="ad0b4-135">Si la visionneuse d’aide se fige (se bloque) lors de l’ajout de contenu, remplacez la ligne cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" dans le fichier%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings ou HlpViewer_VisualStudiox_en-US. Settings par une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-135">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="ad0b4-136">Pour plus d’informations sur ce problème, consultez [La visionneuse d’aide Visual Studio se fige sur l’écran de démarrage](/visualstudio/welcome-to-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ad0b4-136">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="ad0b4-137">Vous pouvez vérifier que le contenu SQL Server 2014 est installé en effectuant une recherche dans le volet de contenu à gauche pour *SQL Server 2014*.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-137">You can verify that the SQL Server 2014 content installed by searching under the content pane on the left for *sql server 2014*.</span></span>

   ![Livres SQL Server 2014 automatiquement mis à jour](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a><span data-ttu-id="ad0b4-139">Contenu hors connexion SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="ad0b4-139">SQL Server 2012 offline content</span></span>

<span data-ttu-id="ad0b4-140">Les étapes suivantes expliquent comment charger le contenu hors connexion de SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="ad0b4-140">The following steps explain how to load offline content for SQL Server 2012</span></span>

1. <span data-ttu-id="ad0b4-141">Téléchargez la [documentation produit pour Microsoft SQL Server 2012 pour les environnements protégés par un pare-feu restreints par un proxy](https://www.microsoft.com/download/details.aspx?id=35750) à partir du centre de téléchargement et enregistrez-la dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-141">Download the [Product Documentation for Microsoft SQL Server 2012 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=35750) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="ad0b4-142">Décompressez le fichier pour afficher le fichier *. MSHA* .</span><span class="sxs-lookup"><span data-stu-id="ad0b4-142">Unzip the file to view the *.msha* file.</span></span>

   ![Fichier d’installation du contenu de l’aide SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. <span data-ttu-id="ad0b4-144">Dans SSMS, sélectionnez **Ajouter et supprimer le contenu d’aide** dans le menu Aide.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-144">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![HelpViewer - Ajouter et supprimer le contenu](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="ad0b4-146">La visionneuse d’aide s’ouvre et affiche l’onglet Gérer le contenu.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-146">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="ad0b4-147">Pour installer le contenu d’aide le plus récent, choisissez **Disque** sous Source d’installation, puis cliquez sur les points de suspension (...).</span><span class="sxs-lookup"><span data-stu-id="ad0b4-147">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Visionneuse d’aide - Gérer la source du disque de contenu](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="ad0b4-149">L’option Chemin d’accès au stockage local sous l’onglet Gérer le contenu indique l’emplacement sur l’ordinateur local où est situé le contenu.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-149">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="ad0b4-150">Pour changer d’emplacement, sélectionnez **Déplacer**, entrez un chemin de dossier différent dans le champ **Vers**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-150">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="ad0b4-151">Si l’installation de l’aide échoue après avoir modifié le chemin d’accès du magasin local, fermez et rouvrez la visionneuse d’aide.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-151">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="ad0b4-152">Vérifiez que le nouvel emplacement apparaît dans le chemin d’accès du magasin local, puis recommencez l’installation.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-152">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="ad0b4-153">Localisez le dossier dans lequel vous avez décompressé le contenu.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-153">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="ad0b4-154">Sélectionnez le fichier **HelpContentSetup.msha** dans le dossier, puis sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-154">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Ouvrir le fichier d’aide de SQL Server 2012 Setup.msha](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. <span data-ttu-id="ad0b4-156">Saisissez *SQL Server 2012* dans la barre de recherche.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-156">Type in *sql server 2012* in the search bar.</span></span> <span data-ttu-id="ad0b4-157">Une fois que vous voyez le contenu 2012 disponible, sélectionnez **Ajouter** en regard de chaque package de contenu (livre) que vous souhaitez installer dans la visionneuse d’aide, puis sélectionnez **Mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-157">Once you see the 2012 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Recherche de livres SQL Server 2012 dans la visionneuse d’aide](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Livres SQL Server 2012 - Ajouter et mettre à jour dans la visionneuse d’aide](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="ad0b4-160">Si la visionneuse d’aide se fige (se bloque) lors de l’ajout de contenu, remplacez la ligne cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" dans le fichier%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings ou HlpViewer_VisualStudiox_en-US. Settings par une date ultérieure.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-160">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="ad0b4-161">Pour plus d’informations sur ce problème, consultez [La visionneuse d’aide Visual Studio se fige sur l’écran de démarrage](/visualstudio/welcome-to-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ad0b4-161">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="ad0b4-162">Vous pouvez vérifier que le contenu SQL Server 2012 est chargé en effectuant une recherche dans le volet de contenu à gauche pour *SQL Server 2012*.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-162">You can verify that the SQL Server 2012 content is loaded by searching under the content pane on the left for *sql server 2012*.</span></span>

   ![Documentation SQL Server 2012 mise à jour automatiquement](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a><span data-ttu-id="ad0b4-164">Voir la documentation hors connexion</span><span class="sxs-lookup"><span data-stu-id="ad0b4-164">View offline documentation</span></span>

<span data-ttu-id="ad0b4-165">Vous pouvez afficher SQL Server contenu de l’aide à l’aide du menu **aide** de la dernière version de SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="ad0b4-165">You can view SQL Server help content using the **HELP** menu in the latest version of SQL Server Management Studio (SSMS).</span></span>

### <a name="view-offline-help-content-in-ssms"></a><span data-ttu-id="ad0b4-166">Afficher le contenu de l’aide hors connexion dans SSMS</span><span class="sxs-lookup"><span data-stu-id="ad0b4-166">View offline help content in SSMS</span></span>

<span data-ttu-id="ad0b4-167">Pour afficher l’aide installée dans SSMS, sélectionnez **Lancer dans la visionneuse d’aide** dans le menu Aide, afin de lancer la visionneuse d’aide.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-167">To view the installed help in SSMS, select **Launch in Help Viewer** from the Help menu, to launch the Help Viewer.</span></span>

   ![Lancer dans la visionneuse d’aide](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

<span data-ttu-id="ad0b4-169">La visionneuse d’aide s’ouvre et affiche l’onglet Gérer le contenu, avec la table des matières de l’aide installée dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-169">Help Viewer opens to the Manage Content tab, with the installed help table of contents in the left pane.</span></span> <span data-ttu-id="ad0b4-170">Sélectionnez les articles dans la table des matières pour les afficher dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-170">select articles in the table of contents to display them in the right pane.</span></span>

> [!Important]
> <span data-ttu-id="ad0b4-171">Si le volet de contenu n’est pas visible, sélectionnez Contenu dans la marge gauche.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-171">If the contents pane is not visible, select Contents on the left margin.</span></span> <span data-ttu-id="ad0b4-172">Sélectionnez l’icône représentant une punaise pour garder le volet de contenu ouvert.</span><span class="sxs-lookup"><span data-stu-id="ad0b4-172">select the pushpin icon to keep the contents pane open.</span></span>  

   ![Visionneuse d’aide avec du contenu](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)
