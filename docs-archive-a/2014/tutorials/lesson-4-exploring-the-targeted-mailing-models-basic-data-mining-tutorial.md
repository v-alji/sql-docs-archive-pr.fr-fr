---
title: 'Leçon 4 : exploration des modèles de publipostage ciblés (didacticiel sur l’exploration de données de base) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e00c5b9-a9f8-4503-99ee-377c9cc02d7f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 8659350b126164e06550acdbecec04bb07499c55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704455"
---
# <a name="lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial"></a><span data-ttu-id="b96b4-102">Leçon 4 : Exploration des modèles de publipostage ciblé (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="b96b4-102">Lesson 4: Exploring the Targeted Mailing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="b96b4-103">Une fois que les modèles inclus dans votre projet sont traités, vous pouvez les explorer pour rechercher des tendances intéressantes.</span><span class="sxs-lookup"><span data-stu-id="b96b4-103">After the models in your project have been processed, you can explore them to look for interesting trends.</span></span> <span data-ttu-id="b96b4-104">Étant donné que les motifs peuvent être complexes et difficiles en examinant simplement des nombres, l'exploration de données SQL Server fournit des outils visuels qui vous aident à analyser les données et à comprendre les règles et les relations que les algorithmes ont découvert dans les données.</span><span class="sxs-lookup"><span data-stu-id="b96b4-104">Because patterns can be complex and difficult simply by looking at numbers, SQL Server Data Mining provides some visual tools that help you investigate the data and understand the rules and relationships that the algorithms have discovered within the data.</span></span> <span data-ttu-id="b96b4-105">Utilisez également un large éventail de tests de précision pour valider votre dataset ou découvrir quel modèle est le plus performant avant de le déployer.</span><span class="sxs-lookup"><span data-stu-id="b96b4-105">You can also use a variety of accuracy tests to validate your dataset or discover which model performs best before you deploy it.</span></span>  
  
 <span data-ttu-id="b96b4-106">Lorsque vous utilisez [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour explorer vos modèles, chaque modèle que vous avez créé est listé dans l’onglet **visionneuse de modèle d’exploration** de données du concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b96b4-106">When you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to explore your models, each model you created is listed in the **Mining Model Viewer** tab in Data Mining Designer.</span></span> <span data-ttu-id="b96b4-107">Vous pouvez utiliser les visionneuses pour explorer les modèles.</span><span class="sxs-lookup"><span data-stu-id="b96b4-107">You can use the viewers to explore the models.</span></span> <span data-ttu-id="b96b4-108">Ces visionneuses sont également disponibles dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b96b4-108">These viewers are also available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b96b4-109">Chaque algorithme que vous avez utilisé pour créer un modèle dans [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] retourne un type différent de résultat.</span><span class="sxs-lookup"><span data-stu-id="b96b4-109">Each algorithm that you used to build a model in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] returns a different type of result.</span></span> <span data-ttu-id="b96b4-110">Par conséquent, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] fournit des visionneuses personnalisées pour chaque type de modèle d'apprentissage automatique.</span><span class="sxs-lookup"><span data-stu-id="b96b4-110">Therefore, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides custom viewers for each type of machine learning model.</span></span>  
  
 <span data-ttu-id="b96b4-111">Si vous souhaitez obtenir des détails, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] fournit également une visionneuse HTML, appelée **visionneuse de l’arborescence de contenu générique**, qui affiche des informations détaillées sur les données du modèle et les modèles trouvés, dans un format semi-tabulaire.</span><span class="sxs-lookup"><span data-stu-id="b96b4-111">If you want to get into details, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] also provides an HTML viewer, called the **Generic Content Tree Viewer**, that displays detailed information about the model data and any patterns that were found, in a semi-tabular format.</span></span> <span data-ttu-id="b96b4-112">Pour plus d’informations, consultez [Explorer un modèle à l’aide de la visionneuse de l’arborescence de contenu générique Microsoft](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="b96b4-112">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span></span>  
  
 <span data-ttu-id="b96b4-113">Dans cette leçon, vous allez examiner les résultats de vos trois modèles.</span><span class="sxs-lookup"><span data-stu-id="b96b4-113">In this lesson you will look at the results from your three models.</span></span> <span data-ttu-id="b96b4-114">Chaque type de modèle est basé sur un algorithme différent et fournit un aperçu différent des données.</span><span class="sxs-lookup"><span data-stu-id="b96b4-114">Each model type is based on a different algorithm and provides different insights into the data.</span></span>  
  
-   <span data-ttu-id="b96b4-115">Le modèle Decision Tree vous indique les facteurs qui influencent l'achat de vélos.</span><span class="sxs-lookup"><span data-stu-id="b96b4-115">The Decision Tree model tells you about factors that influence bike buying.</span></span>  
  
-   <span data-ttu-id="b96b4-116">Le modèle Clustering regroupe vos clients selon des attributs qui incluent leur comportement d'achat de vélo et d'autres attributs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="b96b4-116">The Clustering model groups your customers by attributes that include their bike buying behavior and other selected attributes.</span></span>  
  
-   <span data-ttu-id="b96b4-117">Le modèle Naive Bayes vous permet d'explorer la relation entre différents attributs.</span><span class="sxs-lookup"><span data-stu-id="b96b4-117">The Naive Bayes model enables you to explore the relationship between different attributes.</span></span>  
  
 <span data-ttu-id="b96b4-118">Consultez les rubriques suivantes pour en savoir plus sur les visionneuses de modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b96b4-118">See the following topics to learn more about each of the mining model viewers.</span></span>  
  
-   [<span data-ttu-id="b96b4-119">Exploration du modèle d’arbre de décision &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="b96b4-119">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="b96b4-120">Exploration du modèle de clustering &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="b96b4-120">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="b96b4-121">Exploration du modèle Naive Bayes &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="b96b4-121">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="b96b4-122">Les trois modèles peuvent être affichés à l’aide de la **visionneuse de l’arborescence de contenu générique**, pour extraire des formules, des valeurs de données, etc.</span><span class="sxs-lookup"><span data-stu-id="b96b4-122">All three models can be viewed using the **Generic Content Tree Viewer**, to extract formulas, data values, and so forth.</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="b96b4-123">Première tâche de la leçon</span><span class="sxs-lookup"><span data-stu-id="b96b4-123">First Task in Lesson</span></span>  
 [<span data-ttu-id="b96b4-124">Exploration du modèle d’arbre de décision &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="b96b4-124">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="b96b4-125">Leçon précédente</span><span class="sxs-lookup"><span data-stu-id="b96b4-125">Previous Lesson</span></span>  
 [<span data-ttu-id="b96b4-126">Leçon 3 : Ajout et traitement des modèles</span><span class="sxs-lookup"><span data-stu-id="b96b4-126">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="b96b4-127">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="b96b4-127">Next Lesson</span></span>  
 [<span data-ttu-id="b96b4-128">Leçon 5 : tester les modèles &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="b96b4-128">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="b96b4-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b96b4-129">See Also</span></span>  
 <span data-ttu-id="b96b4-130">[Tâches de la visionneuse de modèle d’exploration de données et procédures](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="b96b4-130">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="b96b4-131">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="b96b4-131">Data Mining Model Viewers</span></span>](../../2014/analysis-services/data-mining/data-mining-model-viewers.md)  
  
  
