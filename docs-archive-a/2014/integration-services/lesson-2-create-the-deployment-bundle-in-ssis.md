---
title: 'Leçon 2 : création de l’ensemble de déploiement | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab17289d-c3d4-4a5e-b7f5-4fea8ae21707
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 927bcd393e4b54e92971c197d93dcc1e2804dcd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611859"
---
# <a name="lesson-2-creating-the-deployment-bundle"></a><span data-ttu-id="50fa0-102">Leçon 2 : Création de l’application de déploiement</span><span class="sxs-lookup"><span data-stu-id="50fa0-102">Lesson 2: Creating the Deployment Bundle</span></span>
  <span data-ttu-id="50fa0-103">Dans la [Leçon 1 : Préparation à la création de l’application de déploiement](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md), vous avez créé le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] intitulé Didacticiel de déploiement, ajouté les packages et les fichiers de prise en charge au projet, et implémenté les configurations dans les packages.</span><span class="sxs-lookup"><span data-stu-id="50fa0-103">In [Lesson 1: Preparing to Create the Deployment Bundle](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md), you created the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project named Deployment Tutorial, added the packages and supporting files to the project, and implemented configurations in packages.</span></span>  
  
 <span data-ttu-id="50fa0-104">Au cours de cette leçon, vous allez créer l'application de déploiement, celle-ci correspond à un dossier contenant les éléments nécessaires pour installer des packages sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="50fa0-104">In this lesson, you will create the deployment bundle, which is a folder that contains the items that you need to install packages on another computer.</span></span> <span data-ttu-id="50fa0-105">Cette application inclut un manifeste de déploiement, des copies des packages et des copies des fichiers de prise en charge issus du projet de de didacticiel de déploiement.</span><span class="sxs-lookup"><span data-stu-id="50fa0-105">The deployment bundle will include a deployment manifest, copies of the packages, and copies of the supporting files from the Deployment Tutorial project.</span></span> <span data-ttu-id="50fa0-106">Le manifeste de déploiement répertorie les packages, les fichiers divers et les configurations dans l'application de déploiement.</span><span class="sxs-lookup"><span data-stu-id="50fa0-106">The deployment manifest lists the packages, miscellaneous files, and configurations in the deployment bundle.</span></span>  
  
 <span data-ttu-id="50fa0-107">Vous allez aussi vérifier la liste des fichiers de l'application de déploiement et examiner le contenu du manifeste.</span><span class="sxs-lookup"><span data-stu-id="50fa0-107">You will also verify the file list in the deployment bundle and examine the contents of the manifest.</span></span>  
  
 <span data-ttu-id="50fa0-108">**Durée estimée pour effectuer cette leçon :** 30 minutes</span><span class="sxs-lookup"><span data-stu-id="50fa0-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="50fa0-109">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="50fa0-109">Lesson Tasks</span></span>  
 <span data-ttu-id="50fa0-110">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="50fa0-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="50fa0-111">Étape 1 : Génération de l’utilitaire de déploiement</span><span class="sxs-lookup"><span data-stu-id="50fa0-111">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
-   [<span data-ttu-id="50fa0-112">Étape 2 : Vérification du bundle de déploiement</span><span class="sxs-lookup"><span data-stu-id="50fa0-112">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="50fa0-113">Démarrer la leçon</span><span class="sxs-lookup"><span data-stu-id="50fa0-113">Start the Lesson</span></span>  
 [<span data-ttu-id="50fa0-114">Étape 1 : Génération de l’utilitaire de déploiement</span><span class="sxs-lookup"><span data-stu-id="50fa0-114">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
<span data-ttu-id="50fa0-115">![Icône de Integration Services (petite)](media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="50fa0-115">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="50fa0-116">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="50fa0-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="50fa0-117">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="50fa0-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="50fa0-118">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="50fa0-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
