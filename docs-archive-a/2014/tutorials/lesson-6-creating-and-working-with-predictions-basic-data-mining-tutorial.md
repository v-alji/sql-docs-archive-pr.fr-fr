---
title: 'Leçon 6 : création et utilisation de prédictions (didacticiel sur l’exploration de données de base) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b213cb58-2c40-4c89-b08b-d3c36a4afad3
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d0a8bfdf83e96622a19ac72490e8602d12afc9df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603161"
---
# <a name="lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="275c5-102">Leçon 6 : création et utilisation de prédictions (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="275c5-102">Lesson 6: Creating and Working with Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="275c5-103">Vous avez élaboré, testé et exploré les modèles d'exploration de données que vous avez créés.</span><span class="sxs-lookup"><span data-stu-id="275c5-103">You have trained, tested, and explored the data mining models you created.</span></span> <span data-ttu-id="275c5-104">Maintenant vous êtes prêt à utiliser les modèles pour identifier les personnes les plus susceptibles de répondre à la nouvelle campagne de publipostage ciblée.</span><span class="sxs-lookup"><span data-stu-id="275c5-104">Now you are ready to use the models to identify the people most likely to respond to the new targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="275c5-105">Dans cette leçon vous allez créer une requête pour prédire quels clients sont susceptibles d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="275c5-105">In this lesson you will create a query to predict which customers are most likely to purchase a bike.</span></span> <span data-ttu-id="275c5-106">Vous allez également récupérer la *probabilité* que la prédiction soit correcte, afin que le service marketing puisse décider s’il faut ou non utiliser la prédiction.</span><span class="sxs-lookup"><span data-stu-id="275c5-106">You will also retrieve the *probability* that the prediction is correct, so the marketing department can decide whether to you can decide whether to use the prediction or not.</span></span>  
  
 <span data-ttu-id="275c5-107">Une fois que vous avez identifié les clients ayant une probabilité élevée d'acheter un vélo, vous allez extraire les détails des cas dans le modèle d'exploration de données pour extraire des noms et des informations de contact pour ces clients.</span><span class="sxs-lookup"><span data-stu-id="275c5-107">Once you have identified customers with a high probability of purchasing a bike, you will drill through to the details of the cases in the mining model to retrieve names and contact information for these customers.</span></span>  
  
 <span data-ttu-id="275c5-108">Cette leçon contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="275c5-108">This lesson contains the following topics:</span></span>  
  
 [<span data-ttu-id="275c5-109">Création de prédictions &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="275c5-109">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="275c5-110">Utilisation de l’extraction sur les données de structure &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="275c5-110">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="275c5-111">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="275c5-111">Next Lesson</span></span>  
 [<span data-ttu-id="275c5-112">Didacticiel sur l’exploration de données intermédiaire &#40;Analysis Services d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="275c5-112">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="275c5-113">Leçon précédente</span><span class="sxs-lookup"><span data-stu-id="275c5-113">Previous Lesson</span></span>  
 [<span data-ttu-id="275c5-114">Leçon 5 : tester les modèles &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="275c5-114">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="275c5-115">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="275c5-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="275c5-116">Création de prédictions &#40;Didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="275c5-116">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="275c5-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="275c5-117">See Also</span></span>  
 <span data-ttu-id="275c5-118">[Contenu du modèle d’exploration de données pour les modèles d’arbre de décision &#40;Analysis Services d’exploration de données&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="275c5-118">[Mining Model Content for Decision Tree Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="275c5-119">Créer une requête de prédiction à l’aide du Générateur de requêtes de prédiction</span><span class="sxs-lookup"><span data-stu-id="275c5-119">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
