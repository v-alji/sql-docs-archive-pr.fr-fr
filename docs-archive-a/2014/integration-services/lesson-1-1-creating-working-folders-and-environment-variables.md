---
title: 'Étape 1 : Création des variables d’environnement et des dossiers de travail | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 45091ba2-ea3d-4399-9814-489d812b42cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 63308d406e230538e5ca8b90dbb55bb802759bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605597"
---
# <a name="step-1-creating-working-folders-and-environment-variables"></a><span data-ttu-id="433d5-102">Étape 1 : Création des variables d’environnement et des dossiers de travail</span><span class="sxs-lookup"><span data-stu-id="433d5-102">Step 1: Creating Working Folders and Environment Variables</span></span>
  <span data-ttu-id="433d5-103">Dans cette tâche, vous allez créer le dossier de travail (C:\DeploymentTutorial) et les nouvelles variables d'environnement système (`DataTransfer` et `LoadXMLData`) que vous utiliserez dans les tâches de didacticiel ultérieures.</span><span class="sxs-lookup"><span data-stu-id="433d5-103">In this task, you will create the working folder (C:\DeploymentTutorial) and the new system environment variables (`DataTransfer` and `LoadXMLData`) that you will use in later tutorial tasks.</span></span>  
  
 <span data-ttu-id="433d5-104">Le dossier de travail se trouve à la racine du lecteur C.</span><span class="sxs-lookup"><span data-stu-id="433d5-104">The working folder is at the root of the C drive.</span></span> <span data-ttu-id="433d5-105">Vous pouvez utiliser un lecteur ou un emplacement différent si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="433d5-105">If you must use a different drive or location, you can do that.</span></span> <span data-ttu-id="433d5-106">Cependant, vous devez prendre note de cet emplacement et vous en servir lorsque le didacticiel vous renvoie à l'emplacement du dossier de travail DeploymentTutorial.</span><span class="sxs-lookup"><span data-stu-id="433d5-106">However, you need to note this location and then use it wherever the tutorial refers to the location of the DeploymentTutorial working folder.</span></span>  
  
 <span data-ttu-id="433d5-107">Dans une prochaine leçon, vous allez déployer dans la table sysssispackages de la base de données msdb[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , des packages enregistrés dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="433d5-107">In a later lesson, you will deploy packages that are saved to the file system to the sysssispackages table in the msdb[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="433d5-108">Idéalement, vous allez déployer les packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="433d5-108">Ideally you will deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to a different computer.</span></span> <span data-ttu-id="433d5-109">Si cela n'est pas possible, ce didacticiel peut néanmoins vous apporter beaucoup d'informations si vous déployez les packages vers une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] qui se trouve sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="433d5-109">If that is not possible, you can still learn a lot from doing this tutorial by deploying the packages to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is on the local computer.</span></span> <span data-ttu-id="433d5-110">Les variables d'environnement utilisées sur les ordinateurs locaux et de destination ont les mêmes noms de variables mais contiennent des valeurs différentes.</span><span class="sxs-lookup"><span data-stu-id="433d5-110">The environment variables that are used on the local and destination computers have the same variable names, but different values are stored in the variables.</span></span> <span data-ttu-id="433d5-111">Par exemple, sur l'ordinateur local, la valeur de la variable d'environnement `DataTransfer` référence le dossier C:\DeploymentTutorial, tandis que sur l'ordinateur cible, la variable d'environnement `DataTransfer` référence le dossier C:\DeploymentTutorialInstall.</span><span class="sxs-lookup"><span data-stu-id="433d5-111">For example, on the local computer, the value of the environment variable `DataTransfer` references the C:\DeploymentTutorial folder, whereas on the target computer the environment variable `DataTransfer` references the C:\DeploymentTutorialInstall folder.</span></span>  
  
 <span data-ttu-id="433d5-112">Si vous envisagez de déployer sur l'ordinateur local, il vous suffit de créer un seul jeu de variables d'environnement ; cependant, vous devez mettre à jour la valeur des variables d'environnement avec une valeur appropriée avant d'effectuer le déploiement local.</span><span class="sxs-lookup"><span data-stu-id="433d5-112">If you plan to deploy to the local computer, you need to create only one set of environment variables; however, you will need to update the value of the environment variables to an appropriate value before you do the local deployment.</span></span>  
  
 <span data-ttu-id="433d5-113">Si vous envisagez de déployer les packages sur un autre ordinateur, vous devez créer deux jeux de variables d'environnement : un jeu pour l'ordinateur local et un jeu pour l'ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="433d5-113">If you plan to deploy the packages to a different computer, you must create two sets of environment variables: one set for the local computer, and one set for the destination computer.</span></span> <span data-ttu-id="433d5-114">Vous pouvez désormais créer seulement les variables destinées à l'ordinateur source, et celles destinées à l'ordinateur de destination ultérieurement, mais les variables d'environnement et le dossier doivent figurer sur l'ordinateur de destination avant que vous puissiez installer les packages sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="433d5-114">You can create only the variables for the source computer now, and create the variables for the destination computer later, but you must have both the folder and environment variables available on the destination computer before you can install the packages on that computer.</span></span>  
  
### <a name="to-create-the-local-working-folder"></a><span data-ttu-id="433d5-115">Pour créer le dossier de travail local</span><span class="sxs-lookup"><span data-stu-id="433d5-115">To create the local working folder</span></span>  
  
1.  <span data-ttu-id="433d5-116">Cliquez avec le bouton droit sur le menu Démarrer et cliquez sur Explorer.</span><span class="sxs-lookup"><span data-stu-id="433d5-116">Right-click the Start menu, and click Explore.</span></span>  
  
2.  <span data-ttu-id="433d5-117">Cliquez sur **Disque local (C:)** .</span><span class="sxs-lookup"><span data-stu-id="433d5-117">Click **Local Disk (C:)**.</span></span>  
  
3.  <span data-ttu-id="433d5-118">Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Dossier**.</span><span class="sxs-lookup"><span data-stu-id="433d5-118">On the **File** menu, point to **New**, and then click **Folder**.</span></span>  
  
4.  <span data-ttu-id="433d5-119">Renommez le nouveau dossier `DeploymentTutorial` .</span><span class="sxs-lookup"><span data-stu-id="433d5-119">Rename New Folder to `DeploymentTutorial`.</span></span>  
  
### <a name="to-create-local-environment-variables"></a><span data-ttu-id="433d5-120">Pour créer des variables d'environnement locales</span><span class="sxs-lookup"><span data-stu-id="433d5-120">To create local environment variables</span></span>  
  
1.  <span data-ttu-id="433d5-121">Dans le menu **Démarrer** , cliquez sur **Panneau de configuration**.</span><span class="sxs-lookup"><span data-stu-id="433d5-121">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="433d5-122">Dans le Panneau de configuration, double-cliquez sur **Système**.</span><span class="sxs-lookup"><span data-stu-id="433d5-122">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="433d5-123">Dans la boîte de dialogue **Propriétés système** , cliquez sur l’onglet **Avancé** , puis sur **Variables d’environnement**.</span><span class="sxs-lookup"><span data-stu-id="433d5-123">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="433d5-124">Dans la boîte de dialogue **Variables d’environnement** , dans le cadre **Variables système** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="433d5-124">In the **Environment Variables** dialog box, in the **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="433d5-125">Dans la boîte de dialogue **nouvelle variable système** , tapez `DataTransfer` dans la zone nom de la **variable** , puis `C:\DeploymentTutorial\datatransferconfig.dtsconfig` dans la zone valeur de la **variable** .</span><span class="sxs-lookup"><span data-stu-id="433d5-125">In the **New System Variable** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorial\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="433d5-126">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="433d5-126">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="433d5-127">Cliquez à nouveau sur **nouveau** , puis tapez `LoadXMLData` dans la zone nom de la **variable** et `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` dans la zone valeur de la **variable** .</span><span class="sxs-lookup"><span data-stu-id="433d5-127">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="433d5-128">Cliquez sur **OK** pour quitter la boîte de dialogue **Variables d’environnement** .</span><span class="sxs-lookup"><span data-stu-id="433d5-128">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="433d5-129">Cliquez sur **OK** pour quitter la boîte de dialogue **Propriétés système** .</span><span class="sxs-lookup"><span data-stu-id="433d5-129">Click **OK** to exit the **System Properties** dialog box.\</span></span>  
  
10. <span data-ttu-id="433d5-130">Redémarrez l'ordinateur si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="433d5-130">Optionally, restart your computer.</span></span> <span data-ttu-id="433d5-131">Si vous ne redémarrez pas l'ordinateur, le nom de la nouvelle variable ne sera pas affiché dans l'Assistant Configuration de package, mais vous pouvez quand même l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="433d5-131">If you do not restart the computer, the name of the new variable will not be displayed in the Package Configuration Wizard, but you can still use it.</span></span>  
  
### <a name="to-create-destination-environment-variables"></a><span data-ttu-id="433d5-132">Pour créer des variables d'environnement de destination</span><span class="sxs-lookup"><span data-stu-id="433d5-132">To create destination environment variables</span></span>  
  
1.  <span data-ttu-id="433d5-133">Dans le menu **Démarrer** , cliquez sur **Panneau de configuration**.</span><span class="sxs-lookup"><span data-stu-id="433d5-133">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="433d5-134">Dans le Panneau de configuration, double-cliquez sur **Système**.</span><span class="sxs-lookup"><span data-stu-id="433d5-134">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="433d5-135">Dans la boîte de dialogue **Propriétés système** , cliquez sur l’onglet **Avancé** , puis sur **Variables d’environnement**.</span><span class="sxs-lookup"><span data-stu-id="433d5-135">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="433d5-136">Dans la boîte de dialogue **Variables d’environnement** , dans le cadre **Variables système** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="433d5-136">In the **Environment Variables** dialog box, in **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="433d5-137">Dans la boîte de dialogue **nouvelles variables système** , tapez `DataTransfer` dans la zone nom de la **variable** et `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` dans la zone valeur de la **variable** .</span><span class="sxs-lookup"><span data-stu-id="433d5-137">In the **New System Variables** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="433d5-138">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="433d5-138">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="433d5-139">Cliquez à nouveau sur **nouveau** , puis tapez `LoadXMLData` dans la zone nom de la **variable** et `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` dans la zone valeur de la **variable** .</span><span class="sxs-lookup"><span data-stu-id="433d5-139">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="433d5-140">Cliquez sur **OK** pour quitter la boîte de dialogue **Variables d’environnement** .</span><span class="sxs-lookup"><span data-stu-id="433d5-140">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="433d5-141">Cliquez sur **OK** pour quitter la boîte de dialogue **Propriétés système** .</span><span class="sxs-lookup"><span data-stu-id="433d5-141">Click **OK** to exit the **System Properties** dialog box.\</span></span>  
  
10. <span data-ttu-id="433d5-142">Redémarrez l'ordinateur si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="433d5-142">Optionally, restart your computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="433d5-143">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="433d5-143">Next Task in Lesson</span></span>  
 [<span data-ttu-id="433d5-144">Étape 2 : Création du projet de déploiement</span><span class="sxs-lookup"><span data-stu-id="433d5-144">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
<span data-ttu-id="433d5-145">![Icône de Integration Services (petite)](media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="433d5-145">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="433d5-146">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="433d5-146">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="433d5-147">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="433d5-147">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="433d5-148">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="433d5-148">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
