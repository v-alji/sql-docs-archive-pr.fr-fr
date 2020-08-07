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
# <a name="install-sql-server-2014-offline-documentation"></a>Installer SQL Server Documentation hors connexion 2014

Cet article explique comment télécharger et afficher le contenu SQL Server 2014 hors connexion. Le contenu hors connexion vous permet d’accéder à la documentation sans connexion Internet (bien qu’une connexion Internet soit initialement requise pour le téléchargement).

La technique implique l’utilisation du menu **aide** de SQL Server Management Studio (SSMS) pour accéder à l’utilitaire de la visionneuse d’aide (HlpViewer.exe).

La documentation hors connexion est disponible pour les versions de SQL Server dans la plage de 2012-2019, et peut-être également pour d’autres versions ultérieures. Même si vous pouvez consulter le contenu des [versions précédentes en ligne](https://docs.microsoft.com/previous-versions/sql/), une option hors connexion offre un moyen pratique d’accéder à l’ancien contenu.

- [SQL Server 2014](#sql-server-2014-offline-content)
- [SQL Server 2012](#sql-server-2012-offline-content)

Pour plus d’SQL Server 2016 et versions ultérieures, consultez leur documentation spécifique à la version pour savoir comment ces versions gèrent leur documentation hors connexion.

## <a name="sql-server-2014-offline-content"></a>Contenu hors connexion pour SQL Server 2014

> [!IMPORTANT]
> Le contenu Transact-SQL de SQL 2014 est uniquement disponible hors connexion.

Les étapes suivantes expliquent comment charger le contenu hors connexion de SQL Server 2014.

1. Téléchargez la [documentation produit pour Microsoft SQL Server 2014 pour les environnements protégés par un pare-feu restreints par un proxy](https://www.microsoft.com/download/details.aspx?id=42557) à partir du centre de téléchargement et enregistrez-la dans un dossier.

2. Décompressez le fichier pour afficher le fichier *. MSHA* .

   ![Fichier d’installation de la documentation d’aide de SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. Dans SSMS, sélectionnez **Ajouter et supprimer le contenu d’aide** dans le menu Aide.

   ![HelpViewer - Ajouter et supprimer le contenu](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   La visionneuse d’aide s’ouvre et affiche l’onglet Gérer le contenu.

4. Pour installer le contenu d’aide le plus récent, choisissez **Disque** sous Source d’installation, puis cliquez sur les points de suspension (...).

   ![Visionneuse d’aide - Gérer la source du disque de contenu](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > L’option Chemin d’accès au stockage local sous l’onglet Gérer le contenu indique l’emplacement sur l’ordinateur local où est situé le contenu. Pour changer d’emplacement, sélectionnez **Déplacer**, entrez un chemin de dossier différent dans le champ **Vers**, puis sélectionnez **OK**.
   Si l’installation de l’aide échoue après avoir modifié le chemin d’accès du magasin local, fermez et rouvrez la visionneuse d’aide. Vérifiez que le nouvel emplacement apparaît dans le chemin d’accès du magasin local, puis recommencez l’installation.

5. Localisez le dossier dans lequel vous avez décompressé le contenu. Sélectionnez le fichier **HelpContentSetup.msha** dans le dossier, puis sélectionnez **Ouvrir**.

   ![Ouvrir le fichier d’aide de SQL Server 2014 Setup.msha](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. Saisissez *SQL Server 2014* dans la barre de recherche. Une fois que vous voyez le contenu 2014 disponible, sélectionnez **Ajouter** en regard de chaque package de contenu (livre) que vous souhaitez installer dans la visionneuse d’aide, puis sélectionnez **Mettre à jour**.

   ![Recherche de livres SQL Server 2014 dans la visionneuse d’aide](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Livres SQL Server 2014 - Ajouter et mettre à jour dans la visionneuse d’aide](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > Si la visionneuse d’aide se fige (se bloque) lors de l’ajout de contenu, remplacez la ligne cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" dans le fichier%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings ou HlpViewer_VisualStudiox_en-US. Settings par une date ultérieure. Pour plus d’informations sur ce problème, consultez [La visionneuse d’aide Visual Studio se fige sur l’écran de démarrage](/visualstudio/welcome-to-visual-studio).

7. Vous pouvez vérifier que le contenu SQL Server 2014 est installé en effectuant une recherche dans le volet de contenu à gauche pour *SQL Server 2014*.

   ![Livres SQL Server 2014 automatiquement mis à jour](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a>Contenu hors connexion SQL Server 2012

Les étapes suivantes expliquent comment charger le contenu hors connexion de SQL Server 2012

1. Téléchargez la [documentation produit pour Microsoft SQL Server 2012 pour les environnements protégés par un pare-feu restreints par un proxy](https://www.microsoft.com/download/details.aspx?id=35750) à partir du centre de téléchargement et enregistrez-la dans un dossier.

2. Décompressez le fichier pour afficher le fichier *. MSHA* .

   ![Fichier d’installation du contenu de l’aide SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. Dans SSMS, sélectionnez **Ajouter et supprimer le contenu d’aide** dans le menu Aide.

   ![HelpViewer - Ajouter et supprimer le contenu](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   La visionneuse d’aide s’ouvre et affiche l’onglet Gérer le contenu.

4. Pour installer le contenu d’aide le plus récent, choisissez **Disque** sous Source d’installation, puis cliquez sur les points de suspension (...).

   ![Visionneuse d’aide - Gérer la source du disque de contenu](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > L’option Chemin d’accès au stockage local sous l’onglet Gérer le contenu indique l’emplacement sur l’ordinateur local où est situé le contenu. Pour changer d’emplacement, sélectionnez **Déplacer**, entrez un chemin de dossier différent dans le champ **Vers**, puis sélectionnez **OK**.
   Si l’installation de l’aide échoue après avoir modifié le chemin d’accès du magasin local, fermez et rouvrez la visionneuse d’aide. Vérifiez que le nouvel emplacement apparaît dans le chemin d’accès du magasin local, puis recommencez l’installation.

5. Localisez le dossier dans lequel vous avez décompressé le contenu. Sélectionnez le fichier **HelpContentSetup.msha** dans le dossier, puis sélectionnez **Ouvrir**.

   ![Ouvrir le fichier d’aide de SQL Server 2012 Setup.msha](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. Saisissez *SQL Server 2012* dans la barre de recherche. Une fois que vous voyez le contenu 2012 disponible, sélectionnez **Ajouter** en regard de chaque package de contenu (livre) que vous souhaitez installer dans la visionneuse d’aide, puis sélectionnez **Mettre à jour**.

   ![Recherche de livres SQL Server 2012 dans la visionneuse d’aide](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Livres SQL Server 2012 - Ajouter et mettre à jour dans la visionneuse d’aide](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > Si la visionneuse d’aide se fige (se bloque) lors de l’ajout de contenu, remplacez la ligne cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" dans le fichier%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings ou HlpViewer_VisualStudiox_en-US. Settings par une date ultérieure. Pour plus d’informations sur ce problème, consultez [La visionneuse d’aide Visual Studio se fige sur l’écran de démarrage](/visualstudio/welcome-to-visual-studio).

7. Vous pouvez vérifier que le contenu SQL Server 2012 est chargé en effectuant une recherche dans le volet de contenu à gauche pour *SQL Server 2012*.

   ![Documentation SQL Server 2012 mise à jour automatiquement](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a>Voir la documentation hors connexion

Vous pouvez afficher SQL Server contenu de l’aide à l’aide du menu **aide** de la dernière version de SQL Server Management Studio (SSMS).

### <a name="view-offline-help-content-in-ssms"></a>Afficher le contenu de l’aide hors connexion dans SSMS

Pour afficher l’aide installée dans SSMS, sélectionnez **Lancer dans la visionneuse d’aide** dans le menu Aide, afin de lancer la visionneuse d’aide.

   ![Lancer dans la visionneuse d’aide](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

La visionneuse d’aide s’ouvre et affiche l’onglet Gérer le contenu, avec la table des matières de l’aide installée dans le volet gauche. Sélectionnez les articles dans la table des matières pour les afficher dans le volet droit.

> [!Important]
> Si le volet de contenu n’est pas visible, sélectionnez Contenu dans la marge gauche. Sélectionnez l’icône représentant une punaise pour garder le volet de contenu ouvert.  

   ![Visionneuse d’aide avec du contenu](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)
