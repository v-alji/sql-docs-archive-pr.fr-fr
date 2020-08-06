---
title: 'Étape 5 : Test des packages mis à jour | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 683e52e5-1c7e-49ab-9ffe-6a450a1c5776
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a075af2e030c8257d01abf5eba7d330b1cc8efe7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605577"
---
# <a name="step-5-testing-the-updated-packages"></a><span data-ttu-id="b85d4-102">Étape 5 : Test des packages mis à jour</span><span class="sxs-lookup"><span data-stu-id="b85d4-102">Step 5: Testing the Updated Packages</span></span>
  <span data-ttu-id="b85d4-103">Avant d'aborder la leçon suivante où vous allez créer l'application de déploiement qui sert à installer les packages sur l'ordinateur de destination, vous devez tester les packages.</span><span class="sxs-lookup"><span data-stu-id="b85d4-103">Before you go on to the next lesson, in which you will create the deployment bundle to use to install the tutorial packages on the destination computer, you should test the packages.</span></span> <span data-ttu-id="b85d4-104">A cours de cette tâche, vous allez exécuter les packages DataTransfer.dtsx et LoadXMLData que vous avez ajoutés au projet Didacticiel de déploiement puis étendus avec des configurations.</span><span class="sxs-lookup"><span data-stu-id="b85d4-104">In this task, you will run the packages, DataTransfer.dtsx and LoadXMLData, that you added to the Deployment Tutorial project and then extended with configurations.</span></span>  
  
 <span data-ttu-id="b85d4-105">Lors de l'exécution des packages, chaque exécutable du package prend la couleur vert au terme de son exécution correcte.</span><span class="sxs-lookup"><span data-stu-id="b85d4-105">When the packages run, each executable in the package becomes a green color as it completes successfully.</span></span> <span data-ttu-id="b85d4-106">Lorsque tous les exécutables sont vert, le package s'est achevé correctement.</span><span class="sxs-lookup"><span data-stu-id="b85d4-106">When all executables are green, the package has completed successfully.</span></span> <span data-ttu-id="b85d4-107">Vous pouvez aussi consulter la progression de l'exécution du package sous l'onglet **Progression** .</span><span class="sxs-lookup"><span data-stu-id="b85d4-107">You can also view the package execution progress on the **Progress** tab.</span></span>  
  
 <span data-ttu-id="b85d4-108">Si les packages ne s'exécutent pas correctement, vous devez les corriger avant d'aborder la leçon suivante.</span><span class="sxs-lookup"><span data-stu-id="b85d4-108">If the packages do not run successfully, you must fix them before you go on to the next lesson.</span></span>  
  
### <a name="to-run-the-datatransfer-package"></a><span data-ttu-id="b85d4-109">Pour exécuter le package DataTransfer</span><span class="sxs-lookup"><span data-stu-id="b85d4-109">To run the DataTransfer package</span></span>  
  
1.  <span data-ttu-id="b85d4-110">Dans l'Explorateur de solutions, cliquez sur DataTransfer.dtsx.</span><span class="sxs-lookup"><span data-stu-id="b85d4-110">In Solution Explorer, click DataTransfer.dtsx.</span></span>  
  
2.  <span data-ttu-id="b85d4-111">Dans le menu **Déboguer** , cliquez sur **Démarrer le débogage**.</span><span class="sxs-lookup"><span data-stu-id="b85d4-111">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="b85d4-112">Une fois l'exécution du package terminée, dans le menu **Déboguer** , cliquez sur **Arrêter le débogage**.</span><span class="sxs-lookup"><span data-stu-id="b85d4-112">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-run-the-loadxmldata-package"></a><span data-ttu-id="b85d4-113">Pour exécuter le package LoadXMLData</span><span class="sxs-lookup"><span data-stu-id="b85d4-113">To run the LoadXMLData package</span></span>  
  
1.  <span data-ttu-id="b85d4-114">Dans l'Explorateur de solutions, cliquez sur LoadXMLData.dtsx.</span><span class="sxs-lookup"><span data-stu-id="b85d4-114">In Solution Explorer, click LoadXMLData.dtsx.</span></span>  
  
2.  <span data-ttu-id="b85d4-115">Dans le menu **Déboguer** , cliquez sur **Démarrer le débogage**.</span><span class="sxs-lookup"><span data-stu-id="b85d4-115">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="b85d4-116">Une fois l'exécution du package terminée, dans le menu **Déboguer** , cliquez sur **Arrêter le débogage**.</span><span class="sxs-lookup"><span data-stu-id="b85d4-116">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="b85d4-117">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="b85d4-117">Next Lesson</span></span>  
 [<span data-ttu-id="b85d4-118">Leçon 2 : Création de l’application de déploiement</span><span class="sxs-lookup"><span data-stu-id="b85d4-118">Lesson 2: Creating the Deployment Bundle</span></span>](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md)  
  
<span data-ttu-id="b85d4-119">![Icône de Integration Services (petite)](media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b85d4-119">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b85d4-120">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="b85d4-120">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b85d4-121">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="b85d4-121">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b85d4-122">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="b85d4-122">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
