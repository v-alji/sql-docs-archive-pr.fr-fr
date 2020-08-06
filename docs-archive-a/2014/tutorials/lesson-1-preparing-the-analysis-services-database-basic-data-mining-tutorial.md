---
title: 'Leçon 1 : préparation de la base de données Analysis Services (didacticiel sur l’exploration de données de base) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a796977-6568-4705-9d27-86a9b36658c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 07647a940851fbdbdc65357e168747662dc88380
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710076"
---
# <a name="lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial"></a><span data-ttu-id="82e14-102">Leçon 1 : préparation de la base de données Analysis Services (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="82e14-102">Lesson 1: Preparing the Analysis Services Database (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="82e14-103">Vous êtes un nouvel employé de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] qui a été chargé de concevoir une application décisionnelle dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82e14-103">You are a new employee of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] who has been tasked with designing a business intelligence application in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]<span data-ttu-id="82e14-104">espère tirer parti de votre [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] expérience d’exploration de données pour découvrir des informations intéressantes et exploitables sur les personnes qui ont acheté des vélos.</span><span class="sxs-lookup"><span data-stu-id="82e14-104">hopes to leverage your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data mining experience to discover interesting and actionable information about people who have purchased bicycles.</span></span> <span data-ttu-id="82e14-105">Vous devrez ensuite prédire quels prospects sont les plus susceptibles d'acheter un vélo à l'avenir.</span><span class="sxs-lookup"><span data-stu-id="82e14-105">They then want you to predict which prospective customers are most likely to purchase a bicycle in the future.</span></span>  
  
 <span data-ttu-id="82e14-106">La conception de cette application dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] commence par la création dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] d’un [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projet basé sur le [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] modèle de projet pour la modélisation multidimensionnelle et l’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="82e14-106">Designing this application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with the creation in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project template for multidimensional modeling and data mining.</span></span> <span data-ttu-id="82e14-107">Après avoir créé un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], vous devez définir une ou plusieurs sources de données.</span><span class="sxs-lookup"><span data-stu-id="82e14-107">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you define one or more data sources.</span></span> <span data-ttu-id="82e14-108">Ensuite, vous définissez une vue des métadonnées, appelée *vue de source de données*, à partir des tables et des vues sélectionnées à partir des sources de données.</span><span class="sxs-lookup"><span data-stu-id="82e14-108">Then, you define a view of the metadata, called a *data source view*, from selected tables and views from the data sources.</span></span>  
  
 <span data-ttu-id="82e14-109">Au cours de cette leçon, vous allez créer un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], définir une source de données unique et ajouter un sous-ensemble de tables dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="82e14-109">In this lesson, you will create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, define a single data source, and add a subset of tables to a data source view.</span></span> <span data-ttu-id="82e14-110">Cette leçon inclut les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="82e14-110">This lesson includes the following tasks:</span></span>  
  
 [<span data-ttu-id="82e14-111">Création d’un projet Analysis Services &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="82e14-111">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="82e14-112">Création d’une source de données &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="82e14-112">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="82e14-113">Création d’une vue de source de données &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="82e14-113">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="82e14-114">Première tâche de la leçon</span><span class="sxs-lookup"><span data-stu-id="82e14-114">First Task in Lesson</span></span>  
 [<span data-ttu-id="82e14-115">Création d’un projet Analysis Services &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="82e14-115">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="82e14-116">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="82e14-116">Next Lesson</span></span>  
 [<span data-ttu-id="82e14-117">Leçon 2 : création d’une structure de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="82e14-117">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="82e14-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82e14-118">See Also</span></span>  
 <span data-ttu-id="82e14-119">[Vues de sources de données dans les modèles multidimensionnels](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span><span class="sxs-lookup"><span data-stu-id="82e14-119">[Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span></span>  
 <span data-ttu-id="82e14-120">[Sources de données prises en charge &#40;SSAS multidimensionnel&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="82e14-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span></span>  
 <span data-ttu-id="82e14-121">[Générer des projets de Analysis Services &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="82e14-121">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="82e14-122">Création d'un projet Analysis Services</span><span class="sxs-lookup"><span data-stu-id="82e14-122">Creating an Analysis Services Project</span></span>](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md)  
  
  
