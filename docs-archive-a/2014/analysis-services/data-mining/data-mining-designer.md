---
title: Concepteur d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], structure
- mining structures [Analysis Services], modifying
- data mining editor [Analysis Services]
- Data Mining Designer
- data mining [Analysis Services], modifying
ms.assetid: 2540db5b-2bf3-4b6c-87c8-79c48d71acce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 820cde158dfabff525081060369daace0e83c8dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601178"
---
# <a name="data-mining-designer"></a><span data-ttu-id="050f2-102">Concepteur d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="050f2-102">Data Mining Designer</span></span>
  <span data-ttu-id="050f2-103">Le concepteur d’exploration de données est l’environnement principal dans lequel vous utilisez des modèles d’exploration de données dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="050f2-103">Data Mining Designer is the primary environment in which you work with mining models in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="050f2-104">Pour accéder au concepteur, vous pouvez sélectionner une structure d'exploration de données existante ou utiliser l'Assistant Exploration de données pour créer une structure d'exploration de données et un modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="050f2-104">You can access the designer either by selecting an existing mining structure, or by using the Data Mining Wizard to create a new mining structure and mining model.</span></span> <span data-ttu-id="050f2-105">Vous pouvez utiliser le Concepteur d'exploration de données pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="050f2-105">You can use Data Mining Designer to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="050f2-106">modifier la structure d'exploration de données et le modèle d'exploration de données initialement créés par l'Assistant Exploration de données ;</span><span class="sxs-lookup"><span data-stu-id="050f2-106">Modify the mining structure and the mining model that were initially created by the Data Mining Wizard.</span></span>  
  
-   <span data-ttu-id="050f2-107">créer de nouveaux modèles d'après une structure d'exploration de données existante ;</span><span class="sxs-lookup"><span data-stu-id="050f2-107">Create new models based on an existing mining structure.</span></span>  
  
-   <span data-ttu-id="050f2-108">instruire et parcourir des modèles d'exploration de données ;</span><span class="sxs-lookup"><span data-stu-id="050f2-108">Train and browse mining models.</span></span>  
  
-   <span data-ttu-id="050f2-109">comparer des modèles à l'aide de graphiques d'analyse de précision ;</span><span class="sxs-lookup"><span data-stu-id="050f2-109">Compare models by using accuracy charts.</span></span>  
  
-   <span data-ttu-id="050f2-110">créer des requêtes de prédictions basées sur des modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="050f2-110">Create prediction queries based on mining models.</span></span>  
  
## <a name="mining-structure-tab"></a><span data-ttu-id="050f2-111">Onglet Structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="050f2-111">Mining Structure Tab</span></span>  
 <span data-ttu-id="050f2-112">Utilisez l’onglet **Structure d’exploration de données** pour ajouter des colonnes et modifier les propriétés d’une structure d’exploration de données existante.</span><span class="sxs-lookup"><span data-stu-id="050f2-112">Use the **Mining Structure** tab to add columns and modify the properties of an existing mining structure.</span></span> <span data-ttu-id="050f2-113">Les tâches et les rubriques suivantes fournissent d'autres informations sur l'utilisation des structures d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="050f2-113">The following tasks and topics provide more information about working with mining structures:</span></span>  
  
 [<span data-ttu-id="050f2-114">Structures d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="050f2-114">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="050f2-115">Tâches de la structure d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="050f2-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
## <a name="mining-models-tab"></a><span data-ttu-id="050f2-116">Onglet Modèles d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="050f2-116">Mining Models Tab</span></span>  
 <span data-ttu-id="050f2-117">Utilisez l’onglet **Modèles d’exploration de données** pour gérer les modèles d’exploration de données existants et pour créer des modèles.</span><span class="sxs-lookup"><span data-stu-id="050f2-117">Use the **Mining Models** tab to manage existing mining models and to create new models.</span></span> <span data-ttu-id="050f2-118">Les modèles d’exploration de données sont toujours basés sur une structure d’exploration de données existante.</span><span class="sxs-lookup"><span data-stu-id="050f2-118">Mining models are always based on an existing mining structure .</span></span>  
  
 <span data-ttu-id="050f2-119">Sous l’onglet **Modèles d’exploration de données** , vous pouvez modifier le type d’algorithme, ajouter ou supprimer des colonnes associées à la structure du modèle, ajuster des propriétés de colonne propres aux algorithmes, spécifier l’utilisation des colonnes de modèle d’exploration de données et ajuster les paramètres d’algorithme associés au modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="050f2-119">In the **Mining Models** tab, you can change the algorithm type, add or remove columns that are associated with the model structure, adjust algorithm-specific column properties, specify the mining model column usage, and adjust algorithm parameters that are associated with the mining model.</span></span> <span data-ttu-id="050f2-120">Vous pouvez également traiter la structure d'exploration de données avec les modèles sélectionnés ou tous les modèles associés.</span><span class="sxs-lookup"><span data-stu-id="050f2-120">You can also process the mining structure together with selected models or with all the associated models.</span></span>  
  
 <span data-ttu-id="050f2-121">Consultez les rubriques suivantes pour plus d'informations sur l'utilisation des modèles d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="050f2-121">See the following topics for more information about working with mining models:</span></span>  
  
 [<span data-ttu-id="050f2-122">Modèles d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="050f2-122">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="050f2-123">Tâches du modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="050f2-123">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
## <a name="mining-model-viewer-tab"></a><span data-ttu-id="050f2-124">Onglet Visionneuse de modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="050f2-124">Mining Model Viewer Tab</span></span>  
 <span data-ttu-id="050f2-125">Utilisez l’onglet **Visionneuse de modèle d’exploration de données** pour explorer visuellement vos modèles d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="050f2-125">Use the **Mining Model Viewer** tab to visually explore your mining models.</span></span> <span data-ttu-id="050f2-126">Chaque modèle d'exploration de données est associé à une visionneuse personnalisée qui affiche le contenu spécifique à ce modèle.</span><span class="sxs-lookup"><span data-stu-id="050f2-126">Each mining model is associated with a custom viewer that displays content that is specific to that model.</span></span> <span data-ttu-id="050f2-127">Vous pouvez également afficher le contenu du modèle d'exploration de données à l'aide de l'utilitaire Microsoft Mining Content Viewer.</span><span class="sxs-lookup"><span data-stu-id="050f2-127">You can also view mining model content by using the content viewer.</span></span>  
  
 <span data-ttu-id="050f2-128">Consultez les rubriques suivantes pour plus d'informations sur l'exploration des modèles d'exploration de données avec les visionneuses d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="050f2-128">See the following topics for more information about exploring mining models with the data mining viewers:</span></span>  
  
 [<span data-ttu-id="050f2-129">Visionneuses de modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="050f2-129">Data Mining Model Viewers</span></span>](data-mining-model-viewers.md)  
  
 [<span data-ttu-id="050f2-130">Tâches de la visionneuse de modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="050f2-130">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
## <a name="mining-accuracy-chart-tab"></a><span data-ttu-id="050f2-131">Onglet Graphique d'analyse de précision de l'exploration de données</span><span class="sxs-lookup"><span data-stu-id="050f2-131">Mining Accuracy Chart Tab</span></span>  
 <span data-ttu-id="050f2-132">Utilisez l’onglet **Graphique d’analyse de précision de l’exploration de données** pour tester la précision prédictive d’un modèle d’exploration de données unique ou pour comparer l’efficacité de plusieurs modèles d’exploration de données appartenant à la même structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="050f2-132">Use the **Mining Accuracy Chart** tab to test the predictive accuracy of a single mining model, or to compare the effectiveness of multiple mining models contained within a mining structure.</span></span> <span data-ttu-id="050f2-133">Cet onglet contient des outils pour filtrer les données, sélectionner des modèles d'exploration de données et afficher les résultats dans un graphique de courbes d'élévation, dans un graphique des bénéfices ou dans une matrice de classification.</span><span class="sxs-lookup"><span data-stu-id="050f2-133">The tab contains tools for filtering the data, selecting mining models, and displaying the results in a lift chart, profit chart, or classification matrix.</span></span>  
  
 <span data-ttu-id="050f2-134">Consultez les rubriques suivantes pour plus d'informations sur le test et la validation des modèles d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="050f2-134">See the following topics for more information about testing and validating mining models:</span></span>  
  
 [<span data-ttu-id="050f2-135">Test et validation &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="050f2-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
 [<span data-ttu-id="050f2-136">Tâches de test et validation et procédures &#40;exploration des données&#41;</span><span class="sxs-lookup"><span data-stu-id="050f2-136">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
## <a name="mining-model-prediction-tab"></a><span data-ttu-id="050f2-137">Onglet Prévision de modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="050f2-137">Mining Model Prediction Tab</span></span>  
 <span data-ttu-id="050f2-138">L’onglet **Prévision de modèle d’exploration de données** contient le Générateur de requêtes de prédictions, que vous pouvez utiliser pour créer une requête de prédiction DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="050f2-138">The **Mining Model Prediction** tab includes Prediction Query Builder, which you can use to create a Data Mining Extensions (DMX) prediction query.</span></span> <span data-ttu-id="050f2-139">Cet onglet contient également des outils pour spécifier des modèles d'exploration de données et des tables d'entrée, mapper les colonnes du modèle d'exploration de données vers les colonnes de la table d'entrée, ajouter des fonctions à une requête et pour spécifier des critères pour chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="050f2-139">The tab contains tools for specifying mining models and input tables, mapping the columns in the mining model to columns in the input table, adding functions to a query, and specifying criteria for each column.</span></span>  
  
 <span data-ttu-id="050f2-140">Une fois que vous avez conçu une requête, cet onglet vous propose différents affichages pour afficher les résultats de la requête et pour modifier manuellement la requête.</span><span class="sxs-lookup"><span data-stu-id="050f2-140">After you design a query, you can use different views in the tab to display the results of the query and to modify the query manually.</span></span> <span data-ttu-id="050f2-141">Vous pouvez également enregistrer les résultats de la requête dans une table de base de données.</span><span class="sxs-lookup"><span data-stu-id="050f2-141">You can also save the results of the query to a table in a database.</span></span>  
  
 <span data-ttu-id="050f2-142">Consultez les rubriques suivantes pour plus d'informations sur la création de requêtes d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="050f2-142">See the following topics for more information about creating data mining queries:</span></span>  
  
 [<span data-ttu-id="050f2-143">Requêtes d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="050f2-143">Data Mining Queries</span></span>](data-mining-queries.md)  
  
 [<span data-ttu-id="050f2-144">Tâches de requête d’exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="050f2-144">Data Mining Query Tasks and How-tos</span></span>](data-mining-query-tasks-and-how-tos.md)  
  
## <a name="see-also"></a><span data-ttu-id="050f2-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="050f2-145">See Also</span></span>  
 [<span data-ttu-id="050f2-146">Solutions d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="050f2-146">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
  
