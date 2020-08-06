---
title: 'Leçon 2 : définition et déploiement d’un cube | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bb62e3c9-462f-4ad2-ac8e-92e2f9e9cc28
author: minewiskan
ms.author: owend
ms.openlocfilehash: a2c043920ac646ec4da9eaa2aace4bf6f48e694c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612595"
---
# <a name="lesson-2-defining-and-deploying-a-cube"></a><span data-ttu-id="42eed-102">Leçon 2 : Définition et déploiement d'un cube</span><span class="sxs-lookup"><span data-stu-id="42eed-102">Lesson 2: Defining and Deploying a Cube</span></span>
  <span data-ttu-id="42eed-103">Une fois que vous avez défini une vue de source de données dans votre [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projet, vous êtes prêt à définir un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube initial.</span><span class="sxs-lookup"><span data-stu-id="42eed-103">After you define a data source view in your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you are ready to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 <span data-ttu-id="42eed-104">Vous pouvez également définir un cube et ses dimensions en une même phase, en utilisant l'Assistant Cube.</span><span class="sxs-lookup"><span data-stu-id="42eed-104">You can define a cube and its dimensions in a single pass using the Cube Wizard.</span></span> <span data-ttu-id="42eed-105">Vous pouvez également définir une ou plusieurs dimensions, puis utiliser l'Assistant Cube pour définir un cube qui utilise ces dimensions.</span><span class="sxs-lookup"><span data-stu-id="42eed-105">Alternatively, you can define one or more dimensions and then use the Cube Wizard to define a cube that uses those dimensions.</span></span> <span data-ttu-id="42eed-106">Si vous concevez une solution complexe, vous démarrez généralement en définissant les dimensions.</span><span class="sxs-lookup"><span data-stu-id="42eed-106">If you are designing a complex solution, you generally start by defining the dimensions.</span></span> <span data-ttu-id="42eed-107">Pour plus d’informations, consultez [Dimensions dans les modèles multidimensionnels](multidimensional-models/dimensions-in-multidimensional-models.md) ou [Cubes dans les modèles multidimensionnels](multidimensional-models/cubes-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="42eed-107">For more information, see [Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) or [Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42eed-108">Les projets achevés de toutes les leçons de ce didacticiel sont disponibles en ligne.</span><span class="sxs-lookup"><span data-stu-id="42eed-108">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="42eed-109">Vous pouvez sauter des leçons en utilisant le projet achevé de la leçon précédente comme point de départ.</span><span class="sxs-lookup"><span data-stu-id="42eed-109">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="42eed-110">[Cliquez ici](https://go.microsoft.com/fwlink/?LinkID=221866) pour télécharger les exemples de projet de ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="42eed-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="42eed-111">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="42eed-111">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="42eed-112">Définition d'une dimension</span><span class="sxs-lookup"><span data-stu-id="42eed-112">Defining a Dimension</span></span>](lesson-2-1-defining-a-dimension.md)  
 <span data-ttu-id="42eed-113">Au cours de cette tâche, vous allez utiliser l'Assistant Dimension pour définir une dimension.</span><span class="sxs-lookup"><span data-stu-id="42eed-113">In this task, you use the Dimension Wizard to define a dimension.</span></span>  
  
 [<span data-ttu-id="42eed-114">Définition d’un cube</span><span class="sxs-lookup"><span data-stu-id="42eed-114">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
 <span data-ttu-id="42eed-115">Au cours de cette tâche, vous allez utiliser l'Assistant Cube pour définir un cube [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] initial.</span><span class="sxs-lookup"><span data-stu-id="42eed-115">In this task, you use the Cube Wizard to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 [<span data-ttu-id="42eed-116">Ajout d'attributs aux dimensions</span><span class="sxs-lookup"><span data-stu-id="42eed-116">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
 <span data-ttu-id="42eed-117">Au cours de cette tâche, vous allez ajouter des attributs aux dimensions que vous avez créées.</span><span class="sxs-lookup"><span data-stu-id="42eed-117">In this task, you add attributes to the dimensions that you created.</span></span>  
  
 [<span data-ttu-id="42eed-118">Vérification des propriétés de cube et de dimension</span><span class="sxs-lookup"><span data-stu-id="42eed-118">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
 <span data-ttu-id="42eed-119">Au cours de cette tâche, vous allez examiner la structure du cube que vous avez défini en utilisant l'Assistant Cube.</span><span class="sxs-lookup"><span data-stu-id="42eed-119">In this task, you review the structure of the cube that you defined by using the Cube Wizard.</span></span>  
  
 [<span data-ttu-id="42eed-120">Déploiement d'un projet Analysis Services</span><span class="sxs-lookup"><span data-stu-id="42eed-120">Deploying an Analysis Services Project</span></span>](lesson-2-5-deploying-an-analysis-services-project.md)  
 <span data-ttu-id="42eed-121">Au cours de cette tâche, vous allez déployer le projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sur votre instance locale de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], et découvrir certaines propriétés de déploiement.</span><span class="sxs-lookup"><span data-stu-id="42eed-121">In this task, you deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project to your local instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], and learn about certain deployment properties.</span></span>  
  
 [<span data-ttu-id="42eed-122">Exploration du cube</span><span class="sxs-lookup"><span data-stu-id="42eed-122">Browsing the Cube</span></span>](lesson-2-6-browsing-the-cube.md)  
 <span data-ttu-id="42eed-123">Au cours de cette tâche, vous allez explorer le cube et les données de dimension à l'aide d'Excel ou du Concepteur de requêtes MDX.</span><span class="sxs-lookup"><span data-stu-id="42eed-123">In this task, you browse the cube and dimension data by using Excel or the MDX query designer.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="42eed-124">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="42eed-124">Next Lesson</span></span>  
 [<span data-ttu-id="42eed-125">Leçon 3 : Modification des mesures, des attributs et des hiérarchies</span><span class="sxs-lookup"><span data-stu-id="42eed-125">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>](lesson-3-modifying-measures-attributes-and-hierarchies.md)  
  
## <a name="see-also"></a><span data-ttu-id="42eed-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="42eed-126">See Also</span></span>  
 <span data-ttu-id="42eed-127">[Scénario du didacticiel Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="42eed-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="42eed-128">[La modélisation multidimensionnelle &#40;le didacticiel Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="42eed-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="42eed-129">[Dimensions dans les modèles multidimensionnels](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="42eed-129">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="42eed-130">[Cubes dans les modèles multidimensionnels](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="42eed-130">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="42eed-131">[Configurez Analysis Services propriétés du projet &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="42eed-131">[Configure Analysis Services Project Properties &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span></span>  
 <span data-ttu-id="42eed-132">[Générer des projets de Analysis Services &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="42eed-132">[Build Analysis Services Projects &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span></span>  
 [<span data-ttu-id="42eed-133">Déployer des projets Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="42eed-133">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
  
