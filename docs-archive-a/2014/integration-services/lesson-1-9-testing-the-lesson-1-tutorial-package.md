---
title: 'Étape 9 : Test du package du didacticiel de la leçon 1 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9aee7acf-797b-46f2-830d-80ab64a9f0b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dff1132489c1683430b1003e88f5037664b11983
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605569"
---
# <a name="step-9-testing-the-lesson-1-tutorial-package"></a><span data-ttu-id="9bc6b-102">Étape 9 : Test du package du tutoriel de la leçon 1</span><span class="sxs-lookup"><span data-stu-id="9bc6b-102">Step 9: Testing the Lesson 1 Tutorial Package</span></span>
  <span data-ttu-id="9bc6b-103">Au cours de cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="9bc6b-103">In this lesson, you have done the following tasks:</span></span>  
  
-   <span data-ttu-id="9bc6b-104">création d'un nouveau projet [!INCLUDE[ssIS](../includes/ssis-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="9bc6b-104">Created a new [!INCLUDE[ssIS](../includes/ssis-md.md)] project.</span></span>  
  
-   <span data-ttu-id="9bc6b-105">configuration des gestionnaires de connexions dont le package a besoin pour se connecter aux données sources et de destination ;</span><span class="sxs-lookup"><span data-stu-id="9bc6b-105">Configured the connection managers that the package needs to connect to the source and destination data.</span></span>  
  
-   <span data-ttu-id="9bc6b-106">ajout d'un flux de données qui récupère les données à partir d'une source de fichier plat, effectue les transformations de recherche nécessaires sur les données et configure les données pour la destination.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-106">Added a data flow that takes the data from a flat file source, performs the necessary Lookup transformations on the data, and configures the data for the destination.</span></span>  
  
 <span data-ttu-id="9bc6b-107">Le package est à présent terminé.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-107">Your package is now complete!</span></span> <span data-ttu-id="9bc6b-108">Il est temps de le tester.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-108">It is time to test your package.</span></span>  
  
## <a name="checking-the-package-layout"></a><span data-ttu-id="9bc6b-109">Vérification de la disposition du package</span><span class="sxs-lookup"><span data-stu-id="9bc6b-109">Checking the Package Layout</span></span>  
 <span data-ttu-id="9bc6b-110">Avant de tester le package, vous devez vérifier que le flux de contrôle et le flux de données dans le package de la leçon 1 contiennent les objets affichés dans les diagrammes suivants.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-110">Before you test the package you should verify that the control and data flows in the Lesson 1 package contain the objects shown in the following diagrams.</span></span>  
  
 <span data-ttu-id="9bc6b-111">**Flux de contrôle**</span><span class="sxs-lookup"><span data-stu-id="9bc6b-111">**Control Flow**</span></span>  
  
 <span data-ttu-id="9bc6b-112">![Flux de contrôle dans le package](../../2014/tutorials/media/task9lesson1control.gif "Flux de contrôle dans le package")</span><span class="sxs-lookup"><span data-stu-id="9bc6b-112">![Control flow in package](../../2014/tutorials/media/task9lesson1control.gif "Control flow in package")</span></span>  
  
 <span data-ttu-id="9bc6b-113">**Flux de données**</span><span class="sxs-lookup"><span data-stu-id="9bc6b-113">**Data Flow**</span></span>  
  
 <span data-ttu-id="9bc6b-114">![Flux de données dans le package](../../2014/tutorials/media/task9lesson1data.gif "Flux de données dans le package")</span><span class="sxs-lookup"><span data-stu-id="9bc6b-114">![Data flow in package](../../2014/tutorials/media/task9lesson1data.gif "Data flow in package")</span></span>  
  
### <a name="to-run-the-lesson-1-tutorial-package"></a><span data-ttu-id="9bc6b-115">Pour exécuter le package du didacticiel de la leçon 1</span><span class="sxs-lookup"><span data-stu-id="9bc6b-115">To run the Lesson 1 tutorial package</span></span>  
  
1.  <span data-ttu-id="9bc6b-116">Dans le menu **Déboguer**, cliquez sur **Démarrer le débogage**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-116">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="9bc6b-117">Le package s'exécute et 1 097 lignes sont ajoutées à la table de faits **FactCurrency** de la base de données **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-117">The package will run, resulting in 1097 rows successfully added into the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span>  
  
2.  <span data-ttu-id="9bc6b-118">Une fois l'exécution du package terminée, dans le menu **Déboguer** , cliquez sur **Arrêter le débogage**.</span><span class="sxs-lookup"><span data-stu-id="9bc6b-118">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="9bc6b-119">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="9bc6b-119">Next Lesson</span></span>  
 [<span data-ttu-id="9bc6b-120">Leçon 2 : Ajout d’un bouclage</span><span class="sxs-lookup"><span data-stu-id="9bc6b-120">Lesson 2: Adding Looping</span></span>](../integration-services/lesson-2-adding-looping-with-ssis.md)  
  
## <a name="see-also"></a><span data-ttu-id="9bc6b-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9bc6b-121">See Also</span></span>  
 [<span data-ttu-id="9bc6b-122">Exécution de projets et de packages</span><span class="sxs-lookup"><span data-stu-id="9bc6b-122">Execution of Projects and Packages</span></span>](packages/run-integration-services-ssis-packages.md)  
  
  
