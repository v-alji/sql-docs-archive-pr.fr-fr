---
title: Exploration du modèle Naive Bayes (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b06708d5-4477-4a51-bf8d-0b1e3c1f9ebb
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a26fa972e1ed50e2f4107026210a5935fcb86d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703548"
---
# <a name="exploring-the-naive-bayes-model-basic-data-mining-tutorial"></a><span data-ttu-id="ea031-102">Exploration du modèle Naive Bayes (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="ea031-102">Exploring the Naive Bayes Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="ea031-103">L' [!INCLUDE[msCoName](../includes/msconame-md.md)] algorithme Naive Bayes fournit plusieurs méthodes pour afficher l’interaction entre l’achat de vélo et les attributs d’entrée.</span><span class="sxs-lookup"><span data-stu-id="ea031-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm provides several methods for displaying the interaction between bike buying and the input attributes.</span></span>  
  
 <span data-ttu-id="ea031-104">La [!INCLUDE[msCoName](../includes/msconame-md.md)] visionneuse Naive Bayes fournit les onglets suivants pour l’exploration des modèles d’exploration de données Naive Bayes :</span><span class="sxs-lookup"><span data-stu-id="ea031-104">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes Viewer provides the following tabs for use in exploring Naive Bayes mining models:</span></span>  
  
 
  
##  <a name="dependency-network"></a><a name="DependencyNetwork"></a><span data-ttu-id="ea031-105">Réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="ea031-105">Dependency Network</span></span>  
 <span data-ttu-id="ea031-106">L’onglet **réseau de dépendances** fonctionne de la même façon que l’onglet **réseau de dépendances** de la [!INCLUDE[msCoName](../includes/msconame-md.md)] visionneuse de l’arborescence.</span><span class="sxs-lookup"><span data-stu-id="ea031-106">The **Dependency Network** tab works in the same way as the **Dependency Network** tab for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer.</span></span> <span data-ttu-id="ea031-107">Chaque nœud dans la visionneuse représente un attribut et les lignes entre les nœuds représentent des relations.</span><span class="sxs-lookup"><span data-stu-id="ea031-107">Each node in the viewer represents an attribute, and the lines between nodes represent relationships.</span></span> <span data-ttu-id="ea031-108">Dans la visionneuse, vous pouvez voir tous les attributs qui ont une incidence sur l'état de l'attribut prédictible Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="ea031-108">In the viewer, you can see all the attributes that affect the state of the predictable attribute, Bike Buyer.</span></span>  
  
#### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="ea031-109">Pour explorer le modèle sous l'onglet Réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="ea031-109">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="ea031-110">Utilisez la liste **modèle d’exploration de données** en haut de l’onglet **visionneuse de modèle d’exploration** de données pour basculer vers le `TM_NaiveBayes` modèle.</span><span class="sxs-lookup"><span data-stu-id="ea031-110">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_NaiveBayes` model.</span></span>  
  
2.  <span data-ttu-id="ea031-111">Utilisez la liste **visionneuse** pour basculer vers la **visionneuse Microsoft Naive Bayes**.</span><span class="sxs-lookup"><span data-stu-id="ea031-111">Use the **Viewer** list to switch to **Microsoft Naive Bayes Viewer**.</span></span>  
  
3.  <span data-ttu-id="ea031-112">Cliquez sur le `Bike Buyer` nœud pour identifier ses dépendances.</span><span class="sxs-lookup"><span data-stu-id="ea031-112">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="ea031-113">L'ombrage rose indique que tous les attributs ont des répercussions sur l'achat de vélos.</span><span class="sxs-lookup"><span data-stu-id="ea031-113">The pink shading indicates that all of the attributes have an effect on bike buying.</span></span>  
  
4.  <span data-ttu-id="ea031-114">Ajustez le curseur pour identifier l'attribut le plus influent.</span><span class="sxs-lookup"><span data-stu-id="ea031-114">Adjust the slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="ea031-115">Si vous faites glisser le curseur vers le bas, seuls les attributs qui ont la plus grande incidence sur la colonne [Bike Buyer] restent affichés.</span><span class="sxs-lookup"><span data-stu-id="ea031-115">As you lower the slider, only the attributes that have the greatest effect on the [Bike Buyer] column remain.</span></span> <span data-ttu-id="ea031-116">En ajustant le curseur, vous pouvez constater que les attributs les plus influents sont : le nombre de voitures possédées, la distance domicile-travail, et le nombre total d'enfants.</span><span class="sxs-lookup"><span data-stu-id="ea031-116">By adjusting the slider, you can discover that a few of the most influential attributes are: number of cars owned, commute distance, and total number of children.</span></span>  
 
  
##  <a name="attribute-profiles"></a><a name="AttributeProfiles"></a><span data-ttu-id="ea031-117">Profils d’attribut</span><span class="sxs-lookup"><span data-stu-id="ea031-117">Attribute Profiles</span></span>  
 <span data-ttu-id="ea031-118">L’onglet **profils d’attribut** décrit comment les différents États des attributs d’entrée affectent le résultat de l’attribut prévisible.</span><span class="sxs-lookup"><span data-stu-id="ea031-118">The **Attribute Profiles** tab describes how different states of the input attributes affect the outcome of the predictable attribute.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-profiles-tab"></a><span data-ttu-id="ea031-119">Pour explorer le modèle sous l'onglet Profils d'attribut</span><span class="sxs-lookup"><span data-stu-id="ea031-119">To explore the model in the Attribute Profiles tab</span></span>  
  
1.  <span data-ttu-id="ea031-120">Dans la zone **prévisible** , vérifiez que `Bike Buyer` est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ea031-120">In the **Predictable** box, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="ea031-121">Si la **légende d’exploration de données** bloque l’affichage des **profils d’attribut**, déplacez-le hors de la voie.</span><span class="sxs-lookup"><span data-stu-id="ea031-121">If the **Mining Legend** is blocking display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="ea031-122">Dans la zone barres de l' **histogramme** , sélectionnez **5**.</span><span class="sxs-lookup"><span data-stu-id="ea031-122">In the **Histogram** bars box, select **5**.</span></span>  
  
     <span data-ttu-id="ea031-123">Dans notre modèle, 5 est le nombre maximal d'états pour toute variable.</span><span class="sxs-lookup"><span data-stu-id="ea031-123">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
     <span data-ttu-id="ea031-124">Les attributs qui affectent l'état de cet attribut prédictible sont présentés avec les valeurs de chaque état des attributs d'entrée et avec leurs distributions dans chaque état de l'attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="ea031-124">The attributes that affect the state of this predictable attribute are listed together with the values of each state of the input attributes and their distributions in each state of the predictable attribute.</span></span>  
  
4.  <span data-ttu-id="ea031-125">Dans la colonne **attributs** , recherchez **Number Cars possédé**.</span><span class="sxs-lookup"><span data-stu-id="ea031-125">In the **Attributes** column, find **Number Cars Owned**.</span></span>  <span data-ttu-id="ea031-126">Remarquez les différences dans les histogrammes pour les acheteurs de vélo (colonne intitulée 1) et les non-acheteurs (colonne intitulée 0).</span><span class="sxs-lookup"><span data-stu-id="ea031-126">Notice the differences in the histograms for bike buyers (column labeled 1) and non-buyers (column labeled 0).</span></span> <span data-ttu-id="ea031-127">Une personne avec zéro ou une voiture est beaucoup plus susceptible d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="ea031-127">A person with zero or one car is much more likely to buy a bike.</span></span>  
  
5.  <span data-ttu-id="ea031-128">Double-cliquez sur la cellule **Number Cars possédé** de la colonne Bike Buyer (colonne intitulée 1).</span><span class="sxs-lookup"><span data-stu-id="ea031-128">Double-click the **Number Cars Owned** cell in the bike buyer (column labeled 1) column.</span></span>  
  
     <span data-ttu-id="ea031-129">La **légende d’exploration de données** affiche une vue plus détaillée.</span><span class="sxs-lookup"><span data-stu-id="ea031-129">The **Mining Legend** displays a more detailed view.</span></span>  
  
  
##  <a name="attribute-characteristics"></a><a name="AttributeCharacteristics"></a> <span data-ttu-id="ea031-130">Caractéristiques d'attribut</span><span class="sxs-lookup"><span data-stu-id="ea031-130">Attribute Characteristics</span></span>  
 <span data-ttu-id="ea031-131">Avec l’onglet **caractéristiques d’attribut** , vous pouvez sélectionner un attribut et une valeur pour voir la fréquence à laquelle les valeurs d’autres attributs apparaissent dans les cas de valeur sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="ea031-131">With the **Attribute Characteristics** tab, you can select an attribute and value to see how frequently values for other attributes appear in the selected value cases.</span></span>  
  
#### <a name="to-explore-the-model-in-the-attribute-characteristics-tab"></a><span data-ttu-id="ea031-132">Pour explorer le modèle sous l'onglet Caractéristiques d'attribut</span><span class="sxs-lookup"><span data-stu-id="ea031-132">To explore the model in the Attribute Characteristics tab</span></span>  
  
1.  <span data-ttu-id="ea031-133">Dans la liste **attribut** , vérifiez que `Bike Buyer` est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ea031-133">In the **Attribute** list, verify that `Bike Buyer` is selected.</span></span>  
  
2.  <span data-ttu-id="ea031-134">Définissez la **valeur** sur **1**.</span><span class="sxs-lookup"><span data-stu-id="ea031-134">Set the **Value** to **1**.</span></span>  
  
     <span data-ttu-id="ea031-135">Dans la visionneuse, vous constaterez que les clients qui n'ont pas d'enfants, font des trajets courts entre leur domicile et bureau, et habitent dans la région North America sont plus susceptibles d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="ea031-135">In the viewer, you will see that customers who have no children at home, short commutes, and live in the North America region are more likely to buy a bike.</span></span>  
  
  
##  <a name="attribute-discrimination"></a><a name="AttributeDiscrimination"></a> <span data-ttu-id="ea031-136">Discrimination d'attribut</span><span class="sxs-lookup"><span data-stu-id="ea031-136">Attribute Discrimination</span></span>  
 <span data-ttu-id="ea031-137">Avec l’onglet **discrimination d’attribut** , vous pouvez examiner la relation entre deux valeurs discrètes de l’achat de vélos et d’autres valeurs d’attribut.</span><span class="sxs-lookup"><span data-stu-id="ea031-137">With the **Attribute Discrimination** tab, you can investigate the relationship between two discrete values of bike buying and other attribute values.</span></span> <span data-ttu-id="ea031-138">Étant donné que le `TM_NaiveBayes` modèle n’a que deux États, 1 et 0, il n’est pas nécessaire d’apporter des modifications à la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="ea031-138">Because the `TM_NaiveBayes` model has only two states, 1 and 0, you do not have to make any changes to the viewer.</span></span>  
  
 <span data-ttu-id="ea031-139">Dans la visionneuse, vous constatez que les personnes qui ne sont pas propriétaires de voitures achètent généralement des vélos et que les personnes propriétaires de deux voitures n'en achètent généralement pas.</span><span class="sxs-lookup"><span data-stu-id="ea031-139">In the viewer, you can see that people who do not own cars tend to buy bicycles, and people who own two cars tend not to buy bicycles.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ea031-140">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ea031-140">Related Tasks</span></span>  
 <span data-ttu-id="ea031-141">Voir les rubriques qui suivent pour explorer les autres modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="ea031-141">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="ea031-142">Exploration du modèle d’arbre de décision &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ea031-142">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="ea031-143">Exploration du modèle de clustering &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ea031-143">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="ea031-144">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="ea031-144">Next Lesson</span></span>  
 [<span data-ttu-id="ea031-145">Leçon 5 : tester les modèles &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ea031-145">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="ea031-146">Tâche précédente de la leçon</span><span class="sxs-lookup"><span data-stu-id="ea031-146">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="ea031-147">Exploration du modèle de clustering &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="ea031-147">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ea031-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea031-148">See Also</span></span>  
 <span data-ttu-id="ea031-149">[Parcourir un modèle à l’aide de Microsoft Naive Bayes Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ea031-149">[Browse a Model Using the Microsoft Naive Bayes Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md) </span></span>  
 <span data-ttu-id="ea031-150">[Onglet discrimination d’attribut &#40;la visionneuse de modèle d’exploration de données&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ea031-150">[Attribute Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="ea031-151">[Onglet Profils d’attribut &#40;visionneuse de modèle d’exploration de données&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ea031-151">[Attribute Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="ea031-152">[Onglet caractéristiques d’attribut &#40;visionneuse de modèle d’exploration de données&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="ea031-152">[Attribute Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/attribute-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="ea031-153">Onglet réseau de dépendances &#40;la visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="ea031-153">Dependency Network Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md)  
  
  
