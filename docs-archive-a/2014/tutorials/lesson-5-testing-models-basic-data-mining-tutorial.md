---
title: 'Leçon 5 : test de modèles (didacticiel sur l’exploration de données de base) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9a7ddcf-2b01-485f-bbb5-62638b303bc6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: fcfd9a9e90d9c6800af4dfd1599bbdd62d9520ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703519"
---
# <a name="lesson-5-testing-models-basic-data-mining-tutorial"></a><span data-ttu-id="de83c-102">Leçon 5 : test de modèles (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="de83c-102">Lesson 5: Testing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="de83c-103">Maintenant que vous avez traité le modèle à l'aide du jeu d'apprentissage du scénario de publipostage ciblé, vous allez tester vos modèles par rapport au jeu de test.</span><span class="sxs-lookup"><span data-stu-id="de83c-103">Now that you have processed the model by using the targeted mailing scenario training set, you will test your models against the testing set.</span></span> <span data-ttu-id="de83c-104">La validation est une étape importante du processus d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="de83c-104">Validation is an important step in the data mining process.</span></span> <span data-ttu-id="de83c-105">Il est important de savoir si vos modèles d'exploration de données pour le publipostage ciblé sont efficaces sur des données réelles avant de les déployer dans un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="de83c-105">Knowing how well your targeted mailing mining models perform against real data is important before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="de83c-106">Comme les données dans le jeu de test contiennent déjà des valeurs connues pour l'achat de vélo, il est facile de déterminer si les prédictions du modèle sont correctes.</span><span class="sxs-lookup"><span data-stu-id="de83c-106">Because the data in the testing set already contains known values for bike buying, it is easy to determine whether the model's predictions are correct.</span></span> <span data-ttu-id="de83c-107">Le modèle qui effectue le mieux sera utilisé par le [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] service marketing pour identifier les clients de la campagne de publipostage ciblée.</span><span class="sxs-lookup"><span data-stu-id="de83c-107">The model that performs the best will be used by the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department to identify the customers for their targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="de83c-108">Dans cette leçon vous allez valider vos modèles à l'aide de plusieurs méthodes :</span><span class="sxs-lookup"><span data-stu-id="de83c-108">In this lesson you will validate your models using multiple methods:</span></span>  
  
1.  <span data-ttu-id="de83c-109">Vous allez effectuer des prédictions par rapport au jeu de test afin de déterminer la précision du modèle sur les résultats connus.</span><span class="sxs-lookup"><span data-stu-id="de83c-109">You'll make predictions against the testing set to see how accurate the model is on known results.</span></span> <span data-ttu-id="de83c-110">Vous allez utiliser un *graphique de courbes d’élévation* pour mesurer son efficacité.</span><span class="sxs-lookup"><span data-stu-id="de83c-110">You'll use a *lift chart* to measure its effectiveness.</span></span>  
  
     [<span data-ttu-id="de83c-111">Test de la précision à l’aide de graphiques de courbes d’élévation &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="de83c-111">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
2.  <span data-ttu-id="de83c-112">Vous allez tester vos modèles sur un sous-ensemble filtré des données.</span><span class="sxs-lookup"><span data-stu-id="de83c-112">You will test your models on a filtered subset of the data.</span></span> <span data-ttu-id="de83c-113">Comparez plusieurs modèles dans le même graphique de courbes d'élévation.</span><span class="sxs-lookup"><span data-stu-id="de83c-113">You can compare multiple models in the same lift chart.</span></span>  
  
     [<span data-ttu-id="de83c-114">Test d’un modèle filtré &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="de83c-114">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="de83c-115">Pour plus d’informations sur la validation de modèle en général, consultez [concepts d’exploration de données](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="de83c-115">For more information about how model validation in general, see [Data Mining Concepts](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="de83c-116">Première tâche de la leçon</span><span class="sxs-lookup"><span data-stu-id="de83c-116">First Task in Lesson</span></span>  
 [<span data-ttu-id="de83c-117">Test de la précision à l’aide de graphiques de courbes d’élévation &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="de83c-117">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="de83c-118">Leçon précédente</span><span class="sxs-lookup"><span data-stu-id="de83c-118">Previous Lesson</span></span>  
 [<span data-ttu-id="de83c-119">Leçon 4 : exploration des modèles de publipostage ciblés &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="de83c-119">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="de83c-120">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="de83c-120">Next Lesson</span></span>  
 [<span data-ttu-id="de83c-121">Leçon 6 : création et utilisation de prédictions &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="de83c-121">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="de83c-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de83c-122">See Also</span></span>  
 <span data-ttu-id="de83c-123">[Onglet graphique de courbes d’élévation &#40;vue graphique d’analyse de précision de l’exploration de données&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="de83c-123">[Lift Chart Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span></span>  
 <span data-ttu-id="de83c-124">[Graphique de courbes d’élévation &#40;Analysis Services d’exploration de données&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="de83c-124">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="de83c-125">[Test et validation &#40;l’exploration de données&#41;](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="de83c-125">[Testing and Validation &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="de83c-126">[Onglet matrice de classification &#40;vue graphique d’analyse de précision de l’exploration de données&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="de83c-126">[Classification Matrix Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span></span>  
 [<span data-ttu-id="de83c-127">Matrice de classification &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="de83c-127">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/classification-matrix-analysis-services-data-mining.md)  
  
  
