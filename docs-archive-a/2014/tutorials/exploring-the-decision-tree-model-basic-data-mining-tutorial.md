---
title: Exploration du modèle d’arbre de décision (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2e1472c2-3f3e-4dae-acb3-62fca374d397
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a2c7f063d7cb73cdc431fb1bc94188c9266c10c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703552"
---
# <a name="exploring-the-decision-tree-model-basic-data-mining-tutorial"></a><span data-ttu-id="452d7-102">Exploration du modèle Decision Tree (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="452d7-102">Exploring the Decision Tree Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="452d7-103">L'algorithme MDT ([!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Tree) prédit quelles colonnes influencent la décision d'acheter un vélo en fonction des colonnes restantes dans le jeu d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="452d7-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm predicts which columns influence the decision to purchase a bike based upon the remaining columns in the training set.</span></span>  
  

  
##  <a name="decision-tree-tab"></a><a name="Decision_Tree_Tab"></a><span data-ttu-id="452d7-104">Onglet arbre de décision</span><span class="sxs-lookup"><span data-stu-id="452d7-104">Decision Tree Tab</span></span>  
 <span data-ttu-id="452d7-105">Sous l’onglet **arbre de décision** , vous pouvez afficher les arbres de décision pour chaque attribut prévisible dans le jeu de données.</span><span class="sxs-lookup"><span data-stu-id="452d7-105">On the **Decision Tree** tab, you can view decision trees for every predictable attribute in the dataset.</span></span>  
  
 <span data-ttu-id="452d7-106">Dans ce cas, le modèle prédit une seule colonne, Bike Buyer, de sorte qu’il n’y a qu’un seul arbre à afficher.</span><span class="sxs-lookup"><span data-stu-id="452d7-106">In this case, the model predicts only one column, Bike Buyer, so there is only one tree to view.</span></span> <span data-ttu-id="452d7-107">S’il y avait plus d’arborescences, vous pouvez utiliser la zone d' **arborescence** pour choisir une autre arborescence.</span><span class="sxs-lookup"><span data-stu-id="452d7-107">If there were more trees, you could use the **Tree** box to choose another tree.</span></span>  
  
 <span data-ttu-id="452d7-108">Lorsque vous affichez le `TM_Decision_Tree` modèle dans la visionneuse d’arbre de décision, vous pouvez voir les attributs les plus importants sur le côté gauche du graphique.</span><span class="sxs-lookup"><span data-stu-id="452d7-108">As you view the `TM_Decision_Tree` model in the Decision Tree viewer, you can see the most important attributes at the left side of the chart.</span></span> <span data-ttu-id="452d7-109">« Le plus important » signifie que ces attributs ont la plus grande influence sur le résultat.</span><span class="sxs-lookup"><span data-stu-id="452d7-109">"Most important" means that these attributes have the greatest influence on the outcome.</span></span> <span data-ttu-id="452d7-110">Les attributs plus bas dans l'arborescence (à droite du graphique) ont moins d'importance.</span><span class="sxs-lookup"><span data-stu-id="452d7-110">Attributes further down the tree (to the right of the chart) have less of an effect.</span></span>  
  
 <span data-ttu-id="452d7-111">Dans cet exemple, l'âge est le facteur le plus important pour prédire les achats de vélo.</span><span class="sxs-lookup"><span data-stu-id="452d7-111">In this example, age is the single most important factor in predicting bike buying.</span></span> <span data-ttu-id="452d7-112">Le modèle regroupe les clients par âge, puis indique l'attribut le plus important suivant pour chaque catégorie d'âge.</span><span class="sxs-lookup"><span data-stu-id="452d7-112">The model groups customers by age, and then shows the next more important attribute for each age group.</span></span> <span data-ttu-id="452d7-113">Par exemple, dans le groupe de clients âgés de 34 à 40 ans, le nombre de voitures possédées est le facteur de prédiction le plus important après l'âge.</span><span class="sxs-lookup"><span data-stu-id="452d7-113">For example, in the group of customers aged 34 to 40, the number of cars owned is the strongest predictor after age.</span></span>  
  
#### <a name="to-explore-the-model-in-the-decision-tree-tab"></a><span data-ttu-id="452d7-114">Pour explorer le modèle sous l'onglet Arbre de décision</span><span class="sxs-lookup"><span data-stu-id="452d7-114">To explore the model in the Decision Tree tab</span></span>  
  
1.  <span data-ttu-id="452d7-115">Sélectionnez l’onglet **visionneuse de modèle d’exploration** de données dans le concepteur d’exploration de **données**.</span><span class="sxs-lookup"><span data-stu-id="452d7-115">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
     <span data-ttu-id="452d7-116">Par défaut, le concepteur s’ouvre sur le premier modèle qui a été ajouté à la structure, dans ce cas, `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="452d7-116">By default, the designer opens to the first model that was added to the structure -- in this case, `TM_Decision_Tree`.</span></span>  
  
2.  <span data-ttu-id="452d7-117">Utilisez les boutons de la loupe pour ajuster la taille d'affichage de l'arbre.</span><span class="sxs-lookup"><span data-stu-id="452d7-117">Use the magnifying glass buttons to adjust the size of the tree display.</span></span>  
  
     <span data-ttu-id="452d7-118">Par défaut, la visionneuse d'arborescences [!INCLUDE[msCoName](../includes/msconame-md.md)] affiche uniquement les trois premiers niveaux de l'arbre.</span><span class="sxs-lookup"><span data-stu-id="452d7-118">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Tree Viewer shows only the first three levels of the tree.</span></span> <span data-ttu-id="452d7-119">Si l'arbre contient moins de trois niveaux, la visionneuse affiche uniquement les niveaux existants.</span><span class="sxs-lookup"><span data-stu-id="452d7-119">If the tree contains fewer than three levels, the viewer shows only the existing levels.</span></span> <span data-ttu-id="452d7-120">Vous pouvez afficher plus de niveaux à l’aide du curseur **afficher le niveau** ou de la liste **expansion par défaut** .</span><span class="sxs-lookup"><span data-stu-id="452d7-120">You can view more levels by using the **Show Level** slider or the **Default Expansion** list.</span></span>  
  
3.  <span data-ttu-id="452d7-121">**Affichez le niveau** de diaporama sur la quatrième barre.</span><span class="sxs-lookup"><span data-stu-id="452d7-121">Slide **Show Level** to the fourth bar.</span></span>  
  
4.  <span data-ttu-id="452d7-122">Remplacez la valeur d' **arrière-plan** par `1` .</span><span class="sxs-lookup"><span data-stu-id="452d7-122">Change the **Background** value to `1`.</span></span>  
  
     <span data-ttu-id="452d7-123">En modifiant le paramètre d' **arrière-plan** , vous pouvez rapidement voir le nombre de cas dans chaque nœud qui ont la valeur cible de `1` pour [vélo Buyer].</span><span class="sxs-lookup"><span data-stu-id="452d7-123">By changing the **Background** setting, you can quickly see the number of cases in each node that have the target value of `1` for [Bike Buyer].</span></span> <span data-ttu-id="452d7-124">Souvenez-vous que dans ce scénario particulier, chaque cas représente un client.</span><span class="sxs-lookup"><span data-stu-id="452d7-124">Remember that in this particular scenario, each case represents a customer.</span></span> <span data-ttu-id="452d7-125">La valeur `1` indique que le client a acheté un vélo précédemment ; la valeur **0** indique que le client n’a pas acheté de vélo.</span><span class="sxs-lookup"><span data-stu-id="452d7-125">The value `1` indicates that the customer previously purchased a bike; the value **0** indicates that the customer has not purchased a bike.</span></span> <span data-ttu-id="452d7-126">Plus l'ombrage du nœud est foncé, plus le pourcentage de cas dans le nœud possédant la valeur cible est élevé.</span><span class="sxs-lookup"><span data-stu-id="452d7-126">The darker the shading of the node, the higher the percentage of cases in the node that have the target value.</span></span>  
  
5.  <span data-ttu-id="452d7-127">Placez le curseur sur le nœud étiqueté **tout**.</span><span class="sxs-lookup"><span data-stu-id="452d7-127">Place your cursor over the node labeled **All**.</span></span> <span data-ttu-id="452d7-128">Une info-bulle affiche les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="452d7-128">An tooltip will display the following information:</span></span>  
  
    -   <span data-ttu-id="452d7-129">Nombre total de cas</span><span class="sxs-lookup"><span data-stu-id="452d7-129">Total number of cases</span></span>  
  
    -   <span data-ttu-id="452d7-130">Nombre de cas n'ayant pas acheté de vélo</span><span class="sxs-lookup"><span data-stu-id="452d7-130">Number of non bike buyer cases</span></span>  
  
    -   <span data-ttu-id="452d7-131">Nombre de cas ayant acheté un vélo</span><span class="sxs-lookup"><span data-stu-id="452d7-131">Number of bike buyer cases</span></span>  
  
    -   <span data-ttu-id="452d7-132">Nombre de cas avec des valeurs manquantes pour [Bike Buyer]</span><span class="sxs-lookup"><span data-stu-id="452d7-132">Number of cases with missing values for [Bike Buyer]</span></span>  
  
     <span data-ttu-id="452d7-133">Vous pouvez également placer votre curseur au-dessus d'un nœud dans l'arbre pour voir la condition requise afin d'atteindre ce nœud depuis le nœud qui le précède.</span><span class="sxs-lookup"><span data-stu-id="452d7-133">Alternately, place your cursor over any node in the tree to see the condition that is required to reach that node from the node that comes before it.</span></span> <span data-ttu-id="452d7-134">Vous pouvez également afficher ces mêmes informations dans la **légende d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="452d7-134">You can also view this same information in the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="452d7-135">Cliquez sur le nœud pour **Age >= 34 et < 41**.</span><span class="sxs-lookup"><span data-stu-id="452d7-135">Click on the node for **Age >=34 and < 41**.</span></span> <span data-ttu-id="452d7-136">L'histogramme s'affiche sous la forme d'une fine barre horizontale sur le nœud et représente la distribution des clients dans cette tranche d'âge qui ont acheté (rose) et qui n'ont pas acheté (bleu) un vélo par le passé.</span><span class="sxs-lookup"><span data-stu-id="452d7-136">The histogram is displayed as a thin horizontal bar across the node and represents the distribution of customers in this age range who previously did (pink) and did not (blue) purchase a bike.</span></span> <span data-ttu-id="452d7-137">La visionneuse nous indique qu'il est probable que les clients âgés de 34 à 40 ans possèdent une seule voiture ou n'en possédant aucune achètent un vélo.</span><span class="sxs-lookup"><span data-stu-id="452d7-137">The Viewer shows us that customers between the ages of 34 and 40 with one or no cars are likely to purchase a bike.</span></span> <span data-ttu-id="452d7-138">En approfondissant, nous découvrons que la probabilité d'acheter un vélo augmente si le client est en fait âgé de 38 à 40 ans.</span><span class="sxs-lookup"><span data-stu-id="452d7-138">Taking it one step further, we find that the likelihood to purchase a bike increases if the customer is actually age 38 to 40.</span></span>  
  
 <span data-ttu-id="452d7-139">Étant donné que vous avez activé l'extraction lorsque vous avez créé la structure et le modèle, vous pouvez extraire des informations détaillées des cas du modèle et de la structure d'exploration de données, notamment les colonnes qui n'ont pas été incluses dans le modèle d'exploration de données (par exemple, emailAddress, FirstName).</span><span class="sxs-lookup"><span data-stu-id="452d7-139">Because you enabled drillthrough when you created the structure and model, you can retrieve detailed information from the model cases and mining structure, including those columns that were not included in the mining model (e.g., emailAddress, FirstName).</span></span>  
  
 <span data-ttu-id="452d7-140">Pour plus d’informations, consultez [Requêtes d’extraction &#40;exploration de données&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="452d7-140">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-drill-through-to-case-data"></a><span data-ttu-id="452d7-141">Pour extraire des données de cas</span><span class="sxs-lookup"><span data-stu-id="452d7-141">To drill through to case data</span></span>  
  
1.  <span data-ttu-id="452d7-142">Cliquez avec le bouton droit sur un nœud et sélectionnez **extraire** , puis **colonnes de modèle uniquement**.</span><span class="sxs-lookup"><span data-stu-id="452d7-142">Right-click a node, and select **Drill Through** then **Model Columns Only**.</span></span>  
  
     <span data-ttu-id="452d7-143">Les détails de chaque cas d'apprentissage s'affichent au format feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="452d7-143">The details for each training case are displayed in spreadsheet format.</span></span> <span data-ttu-id="452d7-144">Ces détails viennent de la vue vTargetMail que vous avez sélectionnée comme table de cas lors de la génération de la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="452d7-144">These details come from the vTargetMail view that you selected as the case table when building the mining structure.</span></span>  
  
2.  <span data-ttu-id="452d7-145">Cliquez avec le bouton droit sur un nœud, puis sélectionnez **extraire** **les colonnes de structure et de modèle**.</span><span class="sxs-lookup"><span data-stu-id="452d7-145">Right-click a node, and select **Drill Through** then **Model and Structure Columns**.</span></span>  
  
     <span data-ttu-id="452d7-146">La même feuille de calcul s'affiche avec les colonnes de structure ajoutées à la fin.</span><span class="sxs-lookup"><span data-stu-id="452d7-146">The same spreadsheet displays with the structure columns appended to the end.</span></span>  
  
  
###  <a name="dependency-network-tab"></a><a name="Dependency_Network_Tab"></a><span data-ttu-id="452d7-147">Onglet réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="452d7-147">Dependency Network Tab</span></span>  
 <span data-ttu-id="452d7-148">L’onglet **réseau de dépendances** affiche les relations entre les attributs qui contribuent à la capacité prédictive du modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="452d7-148">The **Dependency Network** tab displays the relationships between the attributes that contribute to the predictive ability of the mining model.</span></span> <span data-ttu-id="452d7-149">La Visionneuse du réseau de dépendance renforce nos conclusions selon lesquelles l'âge et la région sont des facteurs importants pour prédire l'achat de vélos.</span><span class="sxs-lookup"><span data-stu-id="452d7-149">The Dependency Network viewer reinforces our findings that Age and Region are important factors in predicting bike buying.</span></span>  
  
##### <a name="to-explore-the-model-in-the-dependency-network-tab"></a><span data-ttu-id="452d7-150">Pour explorer le modèle sous l'onglet Réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="452d7-150">To explore the model in the Dependency Network tab</span></span>  
  
1.  <span data-ttu-id="452d7-151">Cliquez sur le `Bike Buyer` nœud pour identifier ses dépendances.</span><span class="sxs-lookup"><span data-stu-id="452d7-151">Click the `Bike Buyer` node to identify its dependencies.</span></span>  
  
     <span data-ttu-id="452d7-152">Le nœud central pour le réseau de dépendances, `Bike Buyer` , représente l’attribut prévisible dans le modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="452d7-152">The center node for the dependency network, `Bike Buyer`, represents the predictable attribute in the mining model.</span></span> <span data-ttu-id="452d7-153">Le graphique met en surbrillance les nœuds connectés qui ont un impact sur l'attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="452d7-153">The graph highlights any connected nodes that have an effect on the predictable attribute.</span></span>  
  
2.  <span data-ttu-id="452d7-154">Ajustez le curseur **tous les liens** pour identifier l’attribut le plus influent.</span><span class="sxs-lookup"><span data-stu-id="452d7-154">Adjust the **All Links** slider to identify the most influential attribute.</span></span>  
  
     <span data-ttu-id="452d7-155">Lorsque vous faites glisser le curseur vers le dessous, les attributs qui n’ont qu’un effet faible sur la colonne [Bike Buyer] sont supprimés du graphique.</span><span class="sxs-lookup"><span data-stu-id="452d7-155">As you drag down the slider, attributes that have only a weak effect on the [Bike Buyer] column are removed from the graph.</span></span> <span data-ttu-id="452d7-156">En ajustant le curseur, vous découvrez que l'âge et la région sont les facteurs les plus importants pour prédire si quelqu'un va acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="452d7-156">By adjusting the slider, you can discover that Age and Region are the greatest factors in predicting whether someone is a bike buyer.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="452d7-157">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="452d7-157">Related Tasks</span></span>  
 <span data-ttu-id="452d7-158">Consultez les rubriques suivantes pour explorer les données à l'aide d'autres types de modèles.</span><span class="sxs-lookup"><span data-stu-id="452d7-158">See these topics to explore the data using the other kinds of models.</span></span>  
  
-   [<span data-ttu-id="452d7-159">Exploration du modèle de clustering &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="452d7-159">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="452d7-160">Exploration du modèle Naive Bayes &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="452d7-160">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="452d7-161">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="452d7-161">Next Task in Lesson</span></span>  
 [<span data-ttu-id="452d7-162">Exploration du modèle de clustering &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="452d7-162">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="452d7-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="452d7-163">See Also</span></span>  
 <span data-ttu-id="452d7-164">[Tâches de la visionneuse de modèle d’exploration de données et procédures](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="452d7-164">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="452d7-165">[Onglet arbre de décision &#40;visionneuse de modèle d’exploration de données&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="452d7-165">[Decision Tree Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="452d7-166">[Onglet réseau de dépendances &#40;la visionneuse de modèle d’exploration de données&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="452d7-166">[Dependency Network Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="452d7-167">Explorer un modèle à l'aide de la visionneuse d'arborescences Microsoft</span><span class="sxs-lookup"><span data-stu-id="452d7-167">Browse a Model Using the Microsoft Tree Viewer</span></span>](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
  
