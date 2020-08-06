---
title: Création d’un projet de Analysis Services (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 784c0401-0358-4117-9c85-4e8220ce71d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 83eb808bc7d18ebe715d309d9f911c010ee172d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601223"
---
# <a name="creating-an-analysis-services-project-basic-data-mining-tutorial"></a><span data-ttu-id="f904d-102">Création d'un projet Analysis Services (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="f904d-102">Creating an Analysis Services Project (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="f904d-103">Chaque [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projet définit les objets dans une [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] base de données unique.</span><span class="sxs-lookup"><span data-stu-id="f904d-103">Each [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project defines the objects in a single [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="f904d-104">Une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] contient plusieurs types d'objets.</span><span class="sxs-lookup"><span data-stu-id="f904d-104">An [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database can contains many different types of objects</span></span>  
  
-   <span data-ttu-id="f904d-105">Modèles multidimensionnels (cubes)</span><span class="sxs-lookup"><span data-stu-id="f904d-105">Multidimensional models (cubes)</span></span>  
  
-   <span data-ttu-id="f904d-106">Structures et modèles d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f904d-106">Mining structures and mining models</span></span>  
  
-   <span data-ttu-id="f904d-107">Objets de prise en charge, tels que des sources de données, des vues de source de données et des assemblys personnalisés</span><span class="sxs-lookup"><span data-stu-id="f904d-107">Supporting objects such as data sources, data source views, and custom assemblies</span></span>  
  
 <span data-ttu-id="f904d-108">Notez que vous **n'avez pas** besoin d'un cube pour effectuer l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="f904d-108">Note that you **do not** require a cube to do data mining.</span></span> <span data-ttu-id="f904d-109">Si vous devez effectuer l'exploration de données sur un cube existant, vous devez ajouter les modèles d'exploration de données au projet utilisé pour générer le cube.</span><span class="sxs-lookup"><span data-stu-id="f904d-109">If you need to perform data mining on an existing cube, you should add the data mining models to the same project you used to build the cube.</span></span> <span data-ttu-id="f904d-110">Cependant, dans la plupart des cas, vous créez vos modèles sur des sources de données relationnelles, par exemple un entrepôt de données, et vous obtenez de meilleures performances si un cube n'est pas impliqué.</span><span class="sxs-lookup"><span data-stu-id="f904d-110">However, for most purposes you can build your models on relational data sources, such as a data warehouse, and get better performance if a cube is not involved.</span></span>  
  
 <span data-ttu-id="f904d-111">Dans ce didacticiel vous allez utiliser un entrepôt de données relationnelles, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], comme source de données.</span><span class="sxs-lookup"><span data-stu-id="f904d-111">In this tutorial you will use a relational data warehouse, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], as the data source.</span></span> <span data-ttu-id="f904d-112">Vous allez déployer tous vos objets d'exploration de données sur une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] nommée `BasicDataMining`, utilisée uniquement pour l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="f904d-112">You will deploy all your data mining objects to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database named `BasicDataMining`, used just for data mining.</span></span>  
  
 <span data-ttu-id="f904d-113">Par défaut, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilise l'instance **localhost** pour les nouveaux projets.</span><span class="sxs-lookup"><span data-stu-id="f904d-113">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses the **localhost** instance for new projects.</span></span> <span data-ttu-id="f904d-114">Si vous utilisez une instance nommée ou un serveur différent, vous devez d'abord créer et ouvrir le projet, puis modifier le nom de l'instance.</span><span class="sxs-lookup"><span data-stu-id="f904d-114">If you are using a named instance or a different server, you must first create and open the project and then change the instance name.</span></span>  
  
 <span data-ttu-id="f904d-115">Pour plus d'informations sur les projets [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , consultez [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span><span class="sxs-lookup"><span data-stu-id="f904d-115">For more information about [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projects, see [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span></span>  
  
### <a name="to-create-an-analysis-services-project"></a><span data-ttu-id="f904d-116">Pour créer un projet Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f904d-116">To create an Analysis Services project</span></span>  
  
1.  <span data-ttu-id="f904d-117">Ouvrez [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f904d-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="f904d-118">Dans le menu **Fichier** , pointez sur **Nouveau**, puis sélectionnez **Projet**.</span><span class="sxs-lookup"><span data-stu-id="f904d-118">On the **File** menu, point to **New**, and then select **Project**.</span></span>  
  
3.  <span data-ttu-id="f904d-119">Vérifiez que l'option **Projets Business Intelligence** est sélectionnée dans le volet **Types de projets** .</span><span class="sxs-lookup"><span data-stu-id="f904d-119">Verify that **Business Intelligence Projects** is selected in the **Project types** pane.</span></span>  
  
4.  <span data-ttu-id="f904d-120">Dans le volet **Modèles** , sélectionnez **Projet multidimensionnel et d'exploration de données Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="f904d-120">In the **Templates** pane, select **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
5.  <span data-ttu-id="f904d-121">Dans la zone **nom** , nommez le nouveau projet `BasicDataMining` .</span><span class="sxs-lookup"><span data-stu-id="f904d-121">In the **Name** box, name the new project `BasicDataMining`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-change-the-instance-where-data-mining-objects-are-stored"></a><span data-ttu-id="f904d-122">Pour modifier les instances de stockage des objets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f904d-122">To change the instance where data mining objects are stored</span></span>  
  
1.  <span data-ttu-id="f904d-123">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], dans le menu **Projet** , sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f904d-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Project** menu, select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f904d-124">Dans la partie gauche du volet **Pages de propriétés** , sous **Propriétés de configuration**, cliquez sur **Déploiement**.</span><span class="sxs-lookup"><span data-stu-id="f904d-124">On the left side of the **Property Pages** pane, under **Configuration Properties**, click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="f904d-125">Dans la partie droite du volet **Pages de propriétés** , sous **Cible**, vérifiez que le nom du **Serveur** est **localhost**.</span><span class="sxs-lookup"><span data-stu-id="f904d-125">On the right side of the **Property Pages** pane, under **Target**, verify that the **Server** name is **localhost**.</span></span> <span data-ttu-id="f904d-126">Si vous utilisez une instance différente, tapez le nom de l'instance.</span><span class="sxs-lookup"><span data-stu-id="f904d-126">If you are using a different instance, type the name of the instance.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f904d-127">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="f904d-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f904d-128">Création d’une source de données &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="f904d-128">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="f904d-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f904d-129">See Also</span></span>  
 <span data-ttu-id="f904d-130">[Générer des projets de Analysis Services &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="f904d-130">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="f904d-131">Créer un projet Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="f904d-131">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/create-an-analysis-services-project-ssdt)  
  
  
