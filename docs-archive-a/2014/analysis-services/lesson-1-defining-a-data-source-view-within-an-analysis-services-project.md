---
title: 'Leçon 1 : définition d’une vue de source de données dans un projet Analysis Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7d3ffabd-78ae-4204-8323-29949d030c16
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a3d69225217154e5072d0cd34349a247730ddaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707967"
---
# <a name="lesson-1-defining-a-data-source-view-within-an-analysis-services-project"></a><span data-ttu-id="aa6f2-102">Leçon 1 : Définition d'une vue de source de données dans un projet Analysis Services</span><span class="sxs-lookup"><span data-stu-id="aa6f2-102">Lesson 1: Defining a Data Source View within an Analysis Services Project</span></span>
  <span data-ttu-id="aa6f2-103">La conception d’une application Business Intelligence dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] commence par la création d’un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa6f2-103">Designing a business intelligence application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with creating an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="aa6f2-104">Dans ce projet, vous devez définir tous les éléments de votre solution, en commençant par une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-104">Within this project, you define all the elements of your solution, starting with a data source view.</span></span>  
  
 <span data-ttu-id="aa6f2-105">Cette leçon contient les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="aa6f2-105">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="aa6f2-106">Création d'un projet Analysis Services</span><span class="sxs-lookup"><span data-stu-id="aa6f2-106">Creating an Analysis Services Project</span></span>](lesson-1-1-creating-an-analysis-services-project.md)  
 <span data-ttu-id="aa6f2-107">Au cours de cette tâche, vous allez créer le projet du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , basé sur un modèle multidimensionnel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aa6f2-107">In this task, you create the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, based on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional model template.</span></span>  
  
 [<span data-ttu-id="aa6f2-108">Définition d’une source de données</span><span class="sxs-lookup"><span data-stu-id="aa6f2-108">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
 <span data-ttu-id="aa6f2-109">Au cours de cette tâche, vous allez spécifier la base de données **AdventureWorksDW2012** comme source de données pour les dimensions et les cubes [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que vous définirez dans les leçons suivantes.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-109">In this task, you specify the **AdventureWorksDW2012** database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dimensions and cubes that you will define in subsequent lessons.</span></span>  
  
 [<span data-ttu-id="aa6f2-110">Définition d'une vue de source de données</span><span class="sxs-lookup"><span data-stu-id="aa6f2-110">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
 <span data-ttu-id="aa6f2-111">Au cours de cette tâche, vous allez définir une vue unifiée unique des métadonnées issues des tables sélectionnées dans la base de données **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="aa6f2-111">In this task, you define a single unified view of the metadata from selected tables in the **AdventureWorksDW2012** database.</span></span>  
  
 [<span data-ttu-id="aa6f2-112">Modification des noms de tables par défaut</span><span class="sxs-lookup"><span data-stu-id="aa6f2-112">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
 <span data-ttu-id="aa6f2-113">Au cours de cette tâche, vous allez modifier les noms des tables dans la vue de source de données, de façon à ce que les noms des prochains objets [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que vous définirez soient plus conviviaux.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-113">In this task, you modify table names in the data source view, so that the names of subsequent [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects that you define will be more user-friendly.</span></span>  
  
 <span data-ttu-id="aa6f2-114">Comparez vos résultats au fichier d'exemple de projet construit pour cette leçon.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-114">Compare your results against a sample project file that was built for this lesson.</span></span> <span data-ttu-id="aa6f2-115">Pour plus d’informations sur le téléchargement des exemples de projets associés à ce didacticiel, consultez les [Projets de modèle multidimensionnels SSAS pour SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) dans la page d’exemples de produits de Codeplex.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-115">For more information about downloading the sample projects that go with this tutorial, see [SSAS Multidimensional Model Projects for SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) on the product samples page on codeplex.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="aa6f2-116">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="aa6f2-116">Next Lesson</span></span>  
 [<span data-ttu-id="aa6f2-117">Leçon 2 : Définition et déploiement d'un cube</span><span class="sxs-lookup"><span data-stu-id="aa6f2-117">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="aa6f2-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aa6f2-118">See Also</span></span>  
 <span data-ttu-id="aa6f2-119">[Créer un projet Analysis Services &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="aa6f2-119">[Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span></span>  
 <span data-ttu-id="aa6f2-120">[Sources de données prises en charge &#40;SSAS multidimensionnel&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="aa6f2-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="aa6f2-121">[Vues de sources de données dans les modèles multidimensionnels](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="aa6f2-121">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="aa6f2-122">[Scénario du didacticiel Analysis Services](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="aa6f2-122">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="aa6f2-123">Modélisation multidimensionnelle &#40;didacticiel Adventure Works&#41;</span><span class="sxs-lookup"><span data-stu-id="aa6f2-123">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
