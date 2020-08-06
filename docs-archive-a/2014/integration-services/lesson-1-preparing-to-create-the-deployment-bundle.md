---
title: 'Leçon 1 : Préparation à la création du bundle de déploiement | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6fe283c-9856-4ba1-a497-e3912424fd18
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0deda2a81ddd86d4e40c1c546232b8056264508a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605568"
---
# <a name="lesson-1-preparing-to-create-the-deployment-bundle"></a><span data-ttu-id="9fcb8-102">Leçon 1 : préparation à la création de l'application de déploiement</span><span class="sxs-lookup"><span data-stu-id="9fcb8-102">Lesson 1: Preparing to Create the Deployment Bundle</span></span>
  <span data-ttu-id="9fcb8-103">Au cours de cette leçon, vous allez créer les dossiers de travail et les variables d'environnement qui prennent en charge le didacticiel, créer un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , ajouter plusieurs packages et leurs fichiers de prise en charge au projet et implémenter les configurations dans des packages.</span><span class="sxs-lookup"><span data-stu-id="9fcb8-103">In this lesson, you will create the working folders and environment variables that support the tutorial, create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add several packages and their supporting files to the project, and implement configurations in packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="9fcb8-104">déploie des packages sur la base d’un projet. Par conséquent, la première étape de création de l’application de déploiement consiste à rassembler tous les packages et les dépendances de package dans un seul projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9fcb8-104">deploys packages on a project basis; therefore, as the first step in creating the deployment bundle, you must collect all the packages and package dependencies into one [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="9fcb8-105">Il est souvent utile d'inclure d'autres informations dans les packages déployés : par exemple, vous allez aussi ajouter au projet un fichier Lisezmoi qui fournit la documentation de base pour ce groupe de packages.</span><span class="sxs-lookup"><span data-stu-id="9fcb8-105">Frequently it is useful to include other information with the deployed packages: for example you will also add to the project a Readme file that provides basic documentation for this group of packages.</span></span>  
  
 <span data-ttu-id="9fcb8-106">Après l'ajout des fichiers et des packages, vous allez ajouter des configurations aux packages qui n'utilisent pas encore de configurations.</span><span class="sxs-lookup"><span data-stu-id="9fcb8-106">After you have added the packages and files, you will add configurations to packages that do not already use configurations.</span></span> <span data-ttu-id="9fcb8-107">Les configurations mettent à jour les propriétés des packages et les objets de package au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="9fcb8-107">The configurations update properties of packages and package objects at run time.</span></span> <span data-ttu-id="9fcb8-108">Au cours d'une autre leçon, vous allez modifier les valeurs de ces configurations au cours du déploiement du package pour prendre en charge les packages dans l'environnement de déploiement.</span><span class="sxs-lookup"><span data-stu-id="9fcb8-108">In a later lesson, you will modify the values of these configurations during package deployment to support the packages in the deployed-to environment.</span></span>  
  
 <span data-ttu-id="9fcb8-109">Une fois les configurations ajoutées, vous devez ouvrir les packages dans le Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] , outil graphique [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] permettant d'élaborer des packages ETL, puis examiner les propriétés des packages et des éléments de package ainsi que les configurations de package pour mieux comprendre les problèmes que doit résoudre le déploiement.</span><span class="sxs-lookup"><span data-stu-id="9fcb8-109">After you have added the configurations, you should open the packages in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] graphical tool for building ETL packages, and examine the properties of packages and package elements as well as the package configurations to better understand the issues that the deployment needs to address.</span></span> <span data-ttu-id="9fcb8-110">Par exemple, un des packages extrait des données de fichiers texte, il faut donc mettre à jour l'emplacement des fichiers de données avant d'exécuter correctement les packages déployés.</span><span class="sxs-lookup"><span data-stu-id="9fcb8-110">For example, one of the packages extracts data from text files, so the location of the data files must be updated before the deployed packages will run successfully.</span></span>  
  
 <span data-ttu-id="9fcb8-111">**Durée estimée pour effectuer cette leçon :** 1 heure</span><span class="sxs-lookup"><span data-stu-id="9fcb8-111">**Estimated time to complete this lesson:** 1 hour</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="9fcb8-112">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="9fcb8-112">Lesson Tasks</span></span>  
 <span data-ttu-id="9fcb8-113">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="9fcb8-113">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="9fcb8-114">Étape 1 : Création des variables d’environnement et des dossiers de travail</span><span class="sxs-lookup"><span data-stu-id="9fcb8-114">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
-   [<span data-ttu-id="9fcb8-115">Étape 2 : Création du projet de déploiement</span><span class="sxs-lookup"><span data-stu-id="9fcb8-115">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
-   [<span data-ttu-id="9fcb8-116">Étape 3 : Ajout de packages et d’autres fichiers</span><span class="sxs-lookup"><span data-stu-id="9fcb8-116">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
-   [<span data-ttu-id="9fcb8-117">Étape 4 : Ajout de configurations de package</span><span class="sxs-lookup"><span data-stu-id="9fcb8-117">Step 4: Adding Package Configurations</span></span>](../integration-services/lesson-1-4-adding-package-configurations.md)  
  
-   [<span data-ttu-id="9fcb8-118">Étape 5 : Test des packages mis à jour</span><span class="sxs-lookup"><span data-stu-id="9fcb8-118">Step 5: Testing the Updated Packages</span></span>](../integration-services/lesson-1-5-testing-the-updated-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="9fcb8-119">Démarrer la leçon</span><span class="sxs-lookup"><span data-stu-id="9fcb8-119">Start the Lesson</span></span>  
 [<span data-ttu-id="9fcb8-120">Étape 1 : Création des variables d’environnement et des dossiers de travail</span><span class="sxs-lookup"><span data-stu-id="9fcb8-120">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
<span data-ttu-id="9fcb8-121">![Icône de Integration Services (petite)](media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9fcb8-121">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9fcb8-122">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="9fcb8-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9fcb8-123">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="9fcb8-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9fcb8-124">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="9fcb8-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
