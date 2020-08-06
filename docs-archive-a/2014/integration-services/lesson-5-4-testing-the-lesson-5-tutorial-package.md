---
title: 'Étape 4 : Test du package du didacticiel de la leçon 5 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5215b77d-c2ec-4b25-a3de-ca49ea197d74
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 76e4692de4daa9ddd6ed0e418bed5cda74ec7650
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602884"
---
# <a name="step-4-testing-the-lesson-5-tutorial-package"></a><span data-ttu-id="1a133-102">Étape 4 : Test du package du tutoriel de la leçon 5</span><span class="sxs-lookup"><span data-stu-id="1a133-102">Step 4: Testing the Lesson 5 Tutorial Package</span></span>
  <span data-ttu-id="1a133-103">Au moment de l'exécution, votre package récupère la valeur de la propriété `Directory` à partir d'une variable mise à jour à l'exécution au lieu d'utiliser le nom du répertoire d'origine spécifié lors de la création du package.</span><span class="sxs-lookup"><span data-stu-id="1a133-103">At run time, your package will obtain the value for the `Directory` property from a variable updated at run time, rather than using the original directory name that you specified when you created the package.</span></span> <span data-ttu-id="1a133-104">La valeur de cette variable est remplie par le fichier SSISTutorial.dtsConfig.</span><span class="sxs-lookup"><span data-stu-id="1a133-104">The value of the variable is populated by the SSISTutorial.dtsConfig file.</span></span>  
  
 <span data-ttu-id="1a133-105">Pour vérifier si le package met à jour la propriété Directory avec la nouvelle valeur lors de l'exécution, exécutez tout simplement le package.</span><span class="sxs-lookup"><span data-stu-id="1a133-105">To verify that the package updates the Directory property with the new value during run time, simply execute the package.</span></span> <span data-ttu-id="1a133-106">Étant donné que seuls trois fichiers de données exemple ont été copiés dans le nouveau répertoire, le flux de données ne sera exécuté que trois fois au lieu de parcourir les 14 fichiers du dossier d'origine.</span><span class="sxs-lookup"><span data-stu-id="1a133-106">Because only three sample data files were copied to the new directory, the data flow will run only three times, rather than iterate through the 14 files in the original folder.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="1a133-107">Vérification de la disposition du package</span><span class="sxs-lookup"><span data-stu-id="1a133-107">Checking the Package Layout</span></span>  
 <span data-ttu-id="1a133-108">Avant de tester le package, vous devez vérifier que le flux de contrôle et le flux de données dans le package de la leçon 5 contiennent les objets affichés dans les diagrammes suivants.</span><span class="sxs-lookup"><span data-stu-id="1a133-108">Before you test the package you should verify that the control and data flows in the Lesson 5 package contains the objects shown in the following diagrams.</span></span> <span data-ttu-id="1a133-109">Le flux de contrôle doit être identique au flux de contrôle de la leçon 4.</span><span class="sxs-lookup"><span data-stu-id="1a133-109">The control flow should be identical to the control flow in lesson 4.</span></span> <span data-ttu-id="1a133-110">Le flux de données doit être identique au flux de données de la leçon 4.</span><span class="sxs-lookup"><span data-stu-id="1a133-110">The data flow should be identical to the data flow in lessons 4.</span></span>  
  
 <span data-ttu-id="1a133-111">**Flux de contrôle**</span><span class="sxs-lookup"><span data-stu-id="1a133-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="1a133-112">![Flux de contrôle dans le package](../../2014/tutorials/media/task4lesson2control.gif "Flux de contrôle dans le package")</span><span class="sxs-lookup"><span data-stu-id="1a133-112">![Control flow in package](../../2014/tutorials/media/task4lesson2control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="1a133-113">**Flux de données**</span><span class="sxs-lookup"><span data-stu-id="1a133-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="1a133-114">![Flux de données dans le package](../../2014/tutorials/media/task9lesson1data.gif "Flux de données dans le package")</span><span class="sxs-lookup"><span data-stu-id="1a133-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-test-the-lesson-5-tutorial-package"></a><span data-ttu-id="1a133-115">Pour tester le package du didacticiel Lesson 5</span><span class="sxs-lookup"><span data-stu-id="1a133-115">To test the Lesson 5 tutorial package</span></span>  
  
1.  <span data-ttu-id="1a133-116">Dans le menu **Déboguer**, cliquez sur **Démarrer le débogage**.</span><span class="sxs-lookup"><span data-stu-id="1a133-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
2.  <span data-ttu-id="1a133-117">Une fois l’exécution du package terminée, dans le menu **Déboguer** , cliquez sur **arrêter le débogage**.</span><span class="sxs-lookup"><span data-stu-id="1a133-117">After the package has completed running, on the **Debug** menu, and then click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="1a133-118">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="1a133-118">Next Lesson</span></span>  
 [<span data-ttu-id="1a133-119">Leçon 6 : Utilisation des paramètres dans le modèle de déploiement de projet</span><span class="sxs-lookup"><span data-stu-id="1a133-119">Lesson 6: Using Parameters with the Project Deployment Model</span></span>](../integration-services/lesson-6-using-parameters-with-the-project-deployment-model-in-ssis.md)  
  
  
