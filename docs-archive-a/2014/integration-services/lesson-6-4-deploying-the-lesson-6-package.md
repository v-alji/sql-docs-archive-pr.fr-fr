---
title: 'Étape 4 : Déploiement du package de la Leçon 6 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b613cef7-7993-4d89-a429-a8251d74d435
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c5109dc96af138bbd0c8c0087e8b73cf3bac435
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614739"
---
# <a name="step-4-deploying-the-lesson-6-package"></a><span data-ttu-id="e84af-102">Étape 4 : Déploiement du package de la leçon 6</span><span class="sxs-lookup"><span data-stu-id="e84af-102">Step 4: Deploying the Lesson 6 Package</span></span>
  <span data-ttu-id="e84af-103">Pour déployer le package, vous devez l'ajouter au catalogue SSISDB dans Integration Services sur une instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e84af-103">Deploying the package involves adding the package to the SSISDB catalog in Integration Services on an instance of SQL Server.</span></span> <span data-ttu-id="e84af-104">Dans cette leçon, vous allez ajouter le package de la leçon 6 au catalogue SSISDB, définir le paramètre, puis exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="e84af-104">In this lesson you will add the Lesson 6 package to the SSISDB catalog, set the parameter, and execute the package.</span></span> <span data-ttu-id="e84af-105">Dans le cadre de cette leçon, vous utiliserez SQL Server Management Studio pour ajouter le package de la leçon 6 au catalogue SSISDB et déployer le package.</span><span class="sxs-lookup"><span data-stu-id="e84af-105">For this lesson you will use SQL Server Management Studio to add the Lesson 6 package to the SSISDB catalog, and deploy the package.</span></span> <span data-ttu-id="e84af-106">Une fois le package déployé, vous modifierez le paramètre de façon à ce qu'il pointe vers un nouvel emplacement, puis vous exécuterez le package.</span><span class="sxs-lookup"><span data-stu-id="e84af-106">After deploying the package you will modify the parameter to point to a new location then execute the package.</span></span>  
  
 <span data-ttu-id="e84af-107">Dans cette leçon, vous allez :</span><span class="sxs-lookup"><span data-stu-id="e84af-107">In this lesson you will:</span></span>  
  
-   <span data-ttu-id="e84af-108">ajouter le package au catalogue SSISDB dans le nœud SSIS dans SQL Server ;</span><span class="sxs-lookup"><span data-stu-id="e84af-108">Add the package to the SSISDB catalog in the SSIS node in SQL Server.</span></span>  
  
-   <span data-ttu-id="e84af-109">déployer le package ;</span><span class="sxs-lookup"><span data-stu-id="e84af-109">Deploy the package.</span></span>  
  
-   <span data-ttu-id="e84af-110">définir la valeur de paramètre du package ;</span><span class="sxs-lookup"><span data-stu-id="e84af-110">Set the package parameter value.</span></span>  
  
-   <span data-ttu-id="e84af-111">exécuter le package dans SSMS.</span><span class="sxs-lookup"><span data-stu-id="e84af-111">Execute the package in SSMS.</span></span>  
  
### <a name="to-locate-or-add-the-ssisdb-catalog"></a><span data-ttu-id="e84af-112">Pour rechercher ou ajouter le catalogue SSISDB</span><span class="sxs-lookup"><span data-stu-id="e84af-112">To Locate or add the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="e84af-113">Cliquez sur Démarrer, pointez sur Tous les programmes, pointez sur Microsoft SQL Server 2012, puis cliquez sur SQL Management Studio.</span><span class="sxs-lookup"><span data-stu-id="e84af-113">Click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Management Studio.</span></span>  
  
2.  <span data-ttu-id="e84af-114">Dans la boîte de dialogue Se connecter au serveur, vérifiez les paramètres par défaut, puis cliquez sur Se connecter.</span><span class="sxs-lookup"><span data-stu-id="e84af-114">On the Connect to Server dialog box, verify the default settings, and then click Connect.</span></span> <span data-ttu-id="e84af-115">Pour vous connecter, la zone Nom du serveur doit contenir le nom de l'ordinateur sur lequel SQL Server est installé.</span><span class="sxs-lookup"><span data-stu-id="e84af-115">To connect, the Server name box must contain the name of the computer where SQL Server is installed.</span></span> <span data-ttu-id="e84af-116">Si le moteur de base de données est une instance nommée, la zone Nom du serveur doit également contenir le nom de l’instance au format <nom_ordinateur>\\<nom_instance>.</span><span class="sxs-lookup"><span data-stu-id="e84af-116">If the Database Engine is a named instance, the Server name box should also contain the instance name in the format <computer_name>\\<instance_name>.</span></span>  
  
3.  <span data-ttu-id="e84af-117">Dans l'Explorateur d'objets, développez Catalogues Integration Services.</span><span class="sxs-lookup"><span data-stu-id="e84af-117">In Object Explorer expand Integration Services Catalogs.</span></span>  
  
4.  <span data-ttu-id="e84af-118">Si aucun catalogue ne figure sous Catalogues Integration Services, ajoutez le catalogue SSISDB.</span><span class="sxs-lookup"><span data-stu-id="e84af-118">If there are no catalogs listed under Integration Services Catalogs then add the SSISDB catalog.</span></span>  
  
5.  <span data-ttu-id="e84af-119">Pour ajouter le catalogue SSISDB, cliquez avec le bouton droit sur Catalogues Integration Services, puis cliquez sur Créer un catalogue.</span><span class="sxs-lookup"><span data-stu-id="e84af-119">To Add the SSISDB catalog, right-click Integration Services Catalogs and click Create Catalog.</span></span>  
  
6.  <span data-ttu-id="e84af-120">Dans la boîte de dialogue Créer un catalogue, sélectionnez Activer l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="e84af-120">On the Create Catalog dialog box select Enable CLR Integration.</span></span>  
  
7.  <span data-ttu-id="e84af-121">Dans la zone Mot de passe, tapez un nouveau mot de passe, puis entrez-le une nouvelle fois dans la zone Retapez le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="e84af-121">In the Password box, type a new password then type it again in the Retype Password box.</span></span> <span data-ttu-id="e84af-122">Veillez à mémoriser le mot de passe que vous tapez.</span><span class="sxs-lookup"><span data-stu-id="e84af-122">Be sure to remember the password you type.</span></span>  
  
8.  <span data-ttu-id="e84af-123">Cliquez sur OK pour ajouter le catalogue SSISDB.</span><span class="sxs-lookup"><span data-stu-id="e84af-123">Click OK to add the SSISDB catalog.</span></span>  
  
### <a name="to-add-the-package-to-the-ssisdb-catalog"></a><span data-ttu-id="e84af-124">Pour ajouter le package au catalogue SSISDB</span><span class="sxs-lookup"><span data-stu-id="e84af-124">To add the package to the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="e84af-125">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur SSISDB, puis cliquez sur Créer un dossier.</span><span class="sxs-lookup"><span data-stu-id="e84af-125">In Object Explorer, right-click SSISDB and click Create Folder.</span></span>  
  
2.  <span data-ttu-id="e84af-126">Dans la boîte de dialogue Créer un dossier, tapez SSIS Tutorial dans la zone Nom du dossier, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e84af-126">In the Create Folder dialog box type SSIS Tutorial in the Folder name box and click OK.</span></span>  
  
3.  <span data-ttu-id="e84af-127">Développez le dossier SSIS Tutorial, cliquez avec le bouton droit sur Projets, puis cliquez sur Importer un package.</span><span class="sxs-lookup"><span data-stu-id="e84af-127">Expand the SSIS Tutorial folder, right-click Projects, and click Import Packages.</span></span>  
  
4.  <span data-ttu-id="e84af-128">Dans la page Introduction de l'Assistant Conversion de projet Integration Services, cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="e84af-128">On the Integration Services Project Conversion Wizard Introduction page click Next.</span></span>  
  
5.  <span data-ttu-id="e84af-129">Dans la page Localiser les packages, vérifiez que l'option Système de fichiers est sélectionnée dans la liste Source, puis cliquez sur Parcourir.</span><span class="sxs-lookup"><span data-stu-id="e84af-129">On the Locate Packages page, ensure that File system is selected in the Source list, then click Browse.</span></span>  
  
6.  <span data-ttu-id="e84af-130">Dans la boîte de dialogue Rechercher un dossier, naviguez jusqu'au dossier contenant le projet SSIS Tutorial, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e84af-130">On the Browse For Folder dialog box, browse to the folder containing the SSIS Tutorial project, then click OK.</span></span>  
  
7.  <span data-ttu-id="e84af-131">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="e84af-131">Click Next.</span></span>  
  
8.  <span data-ttu-id="e84af-132">Dans la page Sélectionner les packages, les six packages SSIS Tutorial doivent apparaître.</span><span class="sxs-lookup"><span data-stu-id="e84af-132">On the Select Packages page you should see all six packages from the SSIS Tutorial.</span></span> <span data-ttu-id="e84af-133">Dans la liste Packages, sélectionnez Lesson 6.dtsx, puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="e84af-133">In the Packages list, select Lesson 6.dtsx, then click Next.</span></span>  
  
9. <span data-ttu-id="e84af-134">Dans la page Sélectionner la destination, tapez SSIS Tutorial Deployment dans la zone Nom du projet, puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="e84af-134">On the Select Destination page, type SSIS Tutorial Deployment in the Project Name box then click Next.</span></span>  
  
10. <span data-ttu-id="e84af-135">Cliquez sur Suivant dans chacune des pages restantes de l'Assistant jusqu'à ce que vous arriviez à la page Vérifier.</span><span class="sxs-lookup"><span data-stu-id="e84af-135">Click Next on each of the remaining wizard pages until you get to the Review page.</span></span>  
  
11. <span data-ttu-id="e84af-136">Dans la page Vérifier, cliquez sur Convertir.</span><span class="sxs-lookup"><span data-stu-id="e84af-136">On the Review page, click Convert.</span></span>  
  
12. <span data-ttu-id="e84af-137">Une fois la conversion terminée, cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="e84af-137">When the conversion completes, click Close.</span></span>  
  
 <span data-ttu-id="e84af-138">Quand vous fermez l'Assistant Conversion de projet Integration Services, SSIS affiche l'Assistant Déploiement d'Integration Services.</span><span class="sxs-lookup"><span data-stu-id="e84af-138">When you close the Integration Services Project Conversion Wizard, SSIS displays the Integration Services Deployment Wizard.</span></span> <span data-ttu-id="e84af-139">Vous allez à présent utiliser cet Assistant pour déployer le package de la leçon 6.</span><span class="sxs-lookup"><span data-stu-id="e84af-139">You will use this wizard now to deploy the Lesson 6 package.</span></span>  
  
1.  <span data-ttu-id="e84af-140">Dans la page Introduction de l'Assistant Déploiement d'Integration Services, passez en revue les étapes à suivre pour déployer le projet, puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="e84af-140">On the Integration Services Deployment Wizard Introduction page, review the steps for deploying the project, then click Next.</span></span>  
  
2.  <span data-ttu-id="e84af-141">Dans la page Sélectionner la destination, vérifiez que le nom du serveur est l'instance de SQL Server contenant le catalogue SSISDB et que le chemin d'accès indique SSIS Tutorial Deployment, puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="e84af-141">On the Select Destination page verify that the server name is the instance of SQL Server containing the SSISDB catalog and that the path shows SSIS Tutorial Deployment, then click Next.</span></span>  
  
3.  <span data-ttu-id="e84af-142">Dans la page Vérifier, passez en revue le résumé, puis cliquez sur Déployer.</span><span class="sxs-lookup"><span data-stu-id="e84af-142">On the Review page, review the Summary then click Deploy.</span></span>  
  
4.  <span data-ttu-id="e84af-143">Une fois le déploiement terminé, cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="e84af-143">When the deployment completes, click Close.</span></span>  
  
5.  <span data-ttu-id="e84af-144">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur Catalogues Integration Services, puis cliquez sur Actualiser.</span><span class="sxs-lookup"><span data-stu-id="e84af-144">In Object Explorer, right-click Integration Services Catalogs and click Refresh.</span></span>  
  
6.  <span data-ttu-id="e84af-145">Développez Catalogues Integration Services, puis SSISDB.</span><span class="sxs-lookup"><span data-stu-id="e84af-145">Expand Integration Services Catalogs then expand SSISDB.</span></span> <span data-ttu-id="e84af-146">Continuez à développer l'arborescence sous SSIS Tutorial jusqu'à ce que le projet soit entièrement développé.</span><span class="sxs-lookup"><span data-stu-id="e84af-146">Continue to Expand the tree under SSIS Tutorial until you have completely expanded the project.</span></span> <span data-ttu-id="e84af-147">Le package Lesson 6.dtsx doit apparaître sous le nœud Packages du nœud SSIS Tutorial Deployment.</span><span class="sxs-lookup"><span data-stu-id="e84af-147">You should see Lesson 6.dtsx under the Packages node of the SSIS Tutorial Deployment node.</span></span>  
  
 <span data-ttu-id="e84af-148">Pour vérifier que le package est complet, cliquez avec le bouton droit sur Lesson 6.dtsx, puis cliquez sur Configurer.</span><span class="sxs-lookup"><span data-stu-id="e84af-148">To verify that the package is complete, right-click Lesson 6.dtsx and click Configure.</span></span> <span data-ttu-id="e84af-149">Dans la boîte de dialogue Configurer, sélectionnez Paramètres, puis vérifiez la présence des entrées suivantes : Lesson 6.dtsx en tant que conteneur, VarFolderName en tant que nom et le chemin d'accès à New Sample Data en tant que valeur. Ensuite, cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="e84af-149">On the Configure dialog box, select Parameters and verify that there is an entry with Lesson 6.dtsx as the Container, VarFolderName as the Name and the path to New Sample Data as the value, then click Close.</span></span>  
  
 <span data-ttu-id="e84af-150">Avant de continuer, créez un dossier d'exemple de données, nommez-le Sample Data Two, puis copiez dans celui-ci trois des exemples de fichiers d'origine.</span><span class="sxs-lookup"><span data-stu-id="e84af-150">Before continuing create a new sample data folder, name it Sample Data Two, and copy any three of the original sample files into it.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="e84af-151">Pour créer et remplir un nouveau dossier de données exemple</span><span class="sxs-lookup"><span data-stu-id="e84af-151">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="e84af-152">Dans l’Explorateur Windows, au niveau racine de votre lecteur (par exemple, C:\\), créez un dossier appelé Sample Data Two.</span><span class="sxs-lookup"><span data-stu-id="e84af-152">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named Sample Data Two.</span></span>  
  
2.  <span data-ttu-id="e84af-153">Ouvrez le dossier C:\Program Files\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Creating a Simple ETL Package\Sample Data, puis copiez trois des exemples de fichiers à partir du dossier.</span><span class="sxs-lookup"><span data-stu-id="e84af-153">Open the c:\Program Files\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Creating a Simple ETL Package\Sample Data folder and then copy any three of the sample files from the folder.</span></span>  
  
3.  <span data-ttu-id="e84af-154">Dans le dossier New Sample Data, collez les fichiers que vous venez de copier.</span><span class="sxs-lookup"><span data-stu-id="e84af-154">In the New Sample Data folder, paste the copied files.</span></span>  
  
### <a name="to-change-the-package-parameter-to-point-to-the-new-sample-data"></a><span data-ttu-id="e84af-155">Pour faire pointer le paramètre du package vers le nouvel exemple de données</span><span class="sxs-lookup"><span data-stu-id="e84af-155">To change the package parameter to point to the new sample data</span></span>  
  
1.  <span data-ttu-id="e84af-156">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur Lesson 6.dtsx, puis cliquez sur Configurer.</span><span class="sxs-lookup"><span data-stu-id="e84af-156">In Object Explorer, right click Lesson 6.dtsx and click Configure.</span></span>  
  
2.  <span data-ttu-id="e84af-157">Dans la boîte de dialogue Configurer, remplacez la valeur du paramètre par le chemin d'accès à Sample Data Two.</span><span class="sxs-lookup"><span data-stu-id="e84af-157">On the Configure dialog box, change the parameter value to the path to Sample Data Two.</span></span> <span data-ttu-id="e84af-158">Par exemple, C:\Sample Data Two, si vous avez placé le nouveau dossier dans le dossier racine du lecteur C.</span><span class="sxs-lookup"><span data-stu-id="e84af-158">For example C:\Sample Data Two if you placed the new folder in the root folder on the C drive.</span></span>  
  
3.  <span data-ttu-id="e84af-159">Cliquez sur OK pour fermer la boîte de dialogue Configurer.</span><span class="sxs-lookup"><span data-stu-id="e84af-159">Click OK to close the Configure dialog box.</span></span>  
  
### <a name="to-test-the-lesson-6-package-deployment"></a><span data-ttu-id="e84af-160">Pour tester le déploiement du package de la leçon 6</span><span class="sxs-lookup"><span data-stu-id="e84af-160">To test the Lesson 6 package deployment</span></span>  
  
1.  <span data-ttu-id="e84af-161">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur Lesson 6.dtsx, puis cliquez sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="e84af-161">In Object Explorer, right click Lesson 6.dtsx and click Execute.</span></span>  
  
2.  <span data-ttu-id="e84af-162">Dans la boîte de dialogue Exécuter le package, cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e84af-162">On the Execute Package dialog box, click OK.</span></span>  
  
3.  <span data-ttu-id="e84af-163">Dans la zone de message, cliquez sur Oui pour ouvrir le rapport Vue d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="e84af-163">On the message dialog box click Yes to open Overview Report.</span></span>  
  
 <span data-ttu-id="e84af-164">Le rapport Vue d'ensemble du package s'affiche avec le nom du package et une synthèse d'état.</span><span class="sxs-lookup"><span data-stu-id="e84af-164">The Overview report for the package is displayed showing the name of the package and a status summary.</span></span> <span data-ttu-id="e84af-165">La section Vue d'ensemble de l'exécution indique le résultat de chaque tâche dans le package. Quant à la section Paramètres utilisés, elle indique les noms et les valeurs de tous les paramètres utilisés dans l'exécution du package, y compris VarFolderName.</span><span class="sxs-lookup"><span data-stu-id="e84af-165">The Execution Overview section shows the result from each task in the package and the Parameters Used section shows the names and values of all parameters used in the package execution, including VarFolderName.</span></span>  
  
  
