---
title: 'Leçon 3 : installation de packages | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 87bc4d82-39d8-424f-886f-98cf1e4bb07a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f8b58cee7bd8e16cd0ca2e726dc8e5eff2cfec5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604628"
---
# <a name="lesson-3-installing-packages"></a><span data-ttu-id="ae86c-102">Leçon 3 : Installation des packages</span><span class="sxs-lookup"><span data-stu-id="ae86c-102">Lesson 3: Installing Packages</span></span>
  <span data-ttu-id="ae86c-103">Dans [la leçon 2 : création de l’ensemble de déploiement](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md), vous avez créé un utilitaire de déploiement et créé l’ensemble de déploiement qui contient les éléments que vous devez installer sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ae86c-103">In [Lesson 2: Creating the Deployment Bundle](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md), you built a deployment utility and created the deployment bundle that contains the items that you must install packages on another computer.</span></span> <span data-ttu-id="ae86c-104">Vous avez vérifié également la liste de fichiers dans l'application de déploiement et examiné le contenu du fichier de manifeste créé lorsque vous avez créé l'utilitaire de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ae86c-104">You also verified the file list in the deployment bundle and examined the contents of the manifest file that was created when you built the deployment utility.</span></span>  
  
 <span data-ttu-id="ae86c-105">Dans cette leçon, vous allez copier l'application de déploiement dans l'ordinateur de destination et exécuter l'Assistant Installation de package pour installer les packages, les dépendances de package et les fichiers annexes sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ae86c-105">In this lesson, you will copy the deployment bundle to the destination computer and then run the Package Installation Wizard to install the packages, package dependencies, and ancillary files on that computer.</span></span> <span data-ttu-id="ae86c-106">Les packages seront installés dans la **msdb** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] base de données msdb et les autres éléments seront installés dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ae86c-106">The packages will be installed in the **msdb**[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database and the other items will be installed in the file system.</span></span> <span data-ttu-id="ae86c-107">Une fois le package installé, vous allez tester le déploiement en exécutant les packages à partir de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] à l'aide de l'utilitaire d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="ae86c-107">After you complete the package installation, you will test the deployment by running the packages from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] using the Execute Package Utility.</span></span>  
  
 <span data-ttu-id="ae86c-108">**Durée estimée pour effectuer cette leçon :** 30 minutes</span><span class="sxs-lookup"><span data-stu-id="ae86c-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="ae86c-109">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="ae86c-109">Lesson Tasks</span></span>  
 <span data-ttu-id="ae86c-110">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ae86c-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="ae86c-111">Étape 1 : Copier le bundle de déploiement</span><span class="sxs-lookup"><span data-stu-id="ae86c-111">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
-   [<span data-ttu-id="ae86c-112">Étape 2 : Exécution de l’Assistant Installation de package</span><span class="sxs-lookup"><span data-stu-id="ae86c-112">Step 2: Running the Package Installation Wizard</span></span>](../integration-services/lesson-3-2-running-the-package-installation-wizard.md)  
  
-   [<span data-ttu-id="ae86c-113">Étape 3 : Test des packages déployés</span><span class="sxs-lookup"><span data-stu-id="ae86c-113">Step 3: Testing the Deployed Packages</span></span>](../integration-services/lesson-3-3-testing-the-deployed-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="ae86c-114">Démarrer la leçon</span><span class="sxs-lookup"><span data-stu-id="ae86c-114">Start the Lesson</span></span>  
 [<span data-ttu-id="ae86c-115">Étape 1 : Copier le bundle de déploiement</span><span class="sxs-lookup"><span data-stu-id="ae86c-115">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
<span data-ttu-id="ae86c-116">![Icône de Integration Services (petite)](media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ae86c-116">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ae86c-117">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="ae86c-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ae86c-118">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="ae86c-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ae86c-119">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="ae86c-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
