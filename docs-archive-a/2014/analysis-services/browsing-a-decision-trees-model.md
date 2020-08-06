---
title: Exploration d’un modèle d’arbres de décision | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- tree viewer
- mining model, decision tree
- decision tree [data mining]
- dependency network
ms.assetid: 6b3dd1ae-caff-41c3-817b-802dc020ff88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 809d2e494cfa7a6c4078acf95c2c70a0e68c188d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602566"
---
# <a name="browsing-a-decision-trees-model"></a><span data-ttu-id="72624-102">Exploration d'un modèle Arbre de décision</span><span class="sxs-lookup"><span data-stu-id="72624-102">Browsing a Decision Trees Model</span></span>
  <span data-ttu-id="72624-103">Lorsque vous ouvrez un modèle de classification à l’aide de **Parcourir**, le modèle est affiché dans une visionneuse de l’arbre de décision interactif, similaire à la [!INCLUDE[msCoName](../includes/msconame-md.md)] visionneuse des arbres de décision dans [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="72624-103">When you open a classification model using **Browse**, the model is displayed in an interactive decision tree viewer, similar to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="72624-104">La visionneuse affiche les résultats de la classification sous la forme d'un graphique qui est conçu pour mettre en évidence les critères qui différencient un groupe de données d'un autre.</span><span class="sxs-lookup"><span data-stu-id="72624-104">The viewer displays the results of classification as a graph that is designed to highlight the criteria that differentiate one group of data from another.</span></span> <span data-ttu-id="72624-105">Vous pouvez également explorer des sous-ensembles individuels de l'arborescence et récupérer les données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="72624-105">You can also drill down into individual subsets of the tree and retrieve the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="72624-106">Explorer le modèle</span><span class="sxs-lookup"><span data-stu-id="72624-106">Explore the Model</span></span>  
 <span data-ttu-id="72624-107">Les modèles fondés sur l'algorithme MDT comportent un certain nombre d'informations intéressantes à explorer.</span><span class="sxs-lookup"><span data-stu-id="72624-107">Models based on the Decision Trees algorithm have lots of interesting information to explore.</span></span> <span data-ttu-id="72624-108">La fenêtre **Parcourir** comprend les onglets et les volets suivants pour vous aider à apprendre les modèles et à prédire les résultats à l’aide du graphique :</span><span class="sxs-lookup"><span data-stu-id="72624-108">The **Browse** window includes the following tabs and panes to help you learn the patterns and predict outcomes using the graph:</span></span>  
  
-   [<span data-ttu-id="72624-109">Decision Tree</span><span class="sxs-lookup"><span data-stu-id="72624-109">Decision Tree</span></span>](#BKMK_DecisionTree)  
  
-   [<span data-ttu-id="72624-110">Réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="72624-110">Dependency Network</span></span>](#BKMK_DNetwork)  
  
 <span data-ttu-id="72624-111">Pour expérimenter avec un modèle d'arbre de décision, vous pouvez utiliser les exemples de données sous l'onglet Données d'apprentissage (ou Données source) du classeur Exemples de données, puis créer un modèle d'arbre de décision en utilisant Bike Buyer comme attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="72624-111">To experiment with a decision trees model, you can use the sample data on the Training Data (or Source Data) tab of the sample data workbook, and build a decision tree model using Bike Buyer as the predictable attribute.</span></span>  
  
###  <a name="decision-tree"></a><a name="BKMK_DecisionTree"></a><span data-ttu-id="72624-112">Arbre de décision</span><span class="sxs-lookup"><span data-stu-id="72624-112">Decision Tree</span></span>  
 <span data-ttu-id="72624-113">Cette vue est conçue pour vous aider à comprendre et à explorer les facteurs qui mènent à un résultat.</span><span class="sxs-lookup"><span data-stu-id="72624-113">This view is intended to help you understand and explore the factors that lead to an outcome.</span></span>  
  
 <span data-ttu-id="72624-114">Le graphique d'arbre de décision peut être lu de gauche à droite, comme suit :</span><span class="sxs-lookup"><span data-stu-id="72624-114">The decision tree graph can be read from left to right as follows:</span></span>  
  
-   <span data-ttu-id="72624-115">Les rectangles, appelés *nœuds*, contiennent des sous-ensembles de données.</span><span class="sxs-lookup"><span data-stu-id="72624-115">The rectangles, which are referred to as *nodes*, contain subsets of the data.</span></span> <span data-ttu-id="72624-116">L'étiquette sur le nœud vous indique les caractéristiques de définition de ce sous-ensemble.</span><span class="sxs-lookup"><span data-stu-id="72624-116">The label on the node tells you the defining characteristics of that subset.</span></span>  
  
-   <span data-ttu-id="72624-117">Le nœud le plus à gauche, intitulé **All**, représente le jeu de données complet.</span><span class="sxs-lookup"><span data-stu-id="72624-117">The leftmost node, labeled **All**, represents the complete data set.</span></span> <span data-ttu-id="72624-118">Tous les nœuds suivants représentent des sous-ensembles des données.</span><span class="sxs-lookup"><span data-stu-id="72624-118">All subsequent nodes represent subsets of the data.</span></span>  
  
-   <span data-ttu-id="72624-119">Un arbre de décision contient de nombreuses *divisions*, ou emplacements où les données divergent en plusieurs ensembles en fonction d’attributs.</span><span class="sxs-lookup"><span data-stu-id="72624-119">A decision tree contains many *splits*, or places where the data diverges into multiple sets based on attributes.</span></span>  
  
     <span data-ttu-id="72624-120">Par exemple, le premier fractionnement de l'exemple de modèle divise le dataset en trois groupes d'âges.</span><span class="sxs-lookup"><span data-stu-id="72624-120">For example, the first split in the sample model divides the dataset into three groups by age.</span></span>  
  
-   <span data-ttu-id="72624-121">Le fractionnement juste après le nœud **tous** est le plus important, car il affiche la condition principale qui divise ce jeu de données.</span><span class="sxs-lookup"><span data-stu-id="72624-121">The split immediately after the **All** node is most important because it shows the primary condition that divides this dataset.</span></span>  
  
     <span data-ttu-id="72624-122">Des fractionnements supplémentaires apparaissent à droite.</span><span class="sxs-lookup"><span data-stu-id="72624-122">Additional splits occur to the right.</span></span> <span data-ttu-id="72624-123">Ainsi, lors de l'analyse de différents segments de l'arborescence, vous pouvez découvrir les attributs qui influaient le plus sur le comportement d'achat.</span><span class="sxs-lookup"><span data-stu-id="72624-123">Thus, by analyzing different segments of the tree, you can learn which attributes had the most influence on purchasing behavior.</span></span>  
  
 <span data-ttu-id="72624-124">![Diagramme de réseau de dépendances pour un modèle d'association](media/dm13-dec-tree-split-definition.gif "Diagramme de réseau de dépendances pour un modèle d'association")</span><span class="sxs-lookup"><span data-stu-id="72624-124">![Dependency network graph for an association model](media/dm13-dec-tree-split-definition.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="72624-125">Grâce à ces informations, vous pouvez cibler une campagne marketing sur les clients qui ont peut-être simplement besoin d'être encouragés pour effectuer un achat.</span><span class="sxs-lookup"><span data-stu-id="72624-125">Using this information, you might focus a marketing campaign on customers that might simply need encouragement to make a purchase.</span></span>  
  
##### <a name="explore-the-decision-tree"></a><span data-ttu-id="72624-126">Explorer l'arbre de décision</span><span class="sxs-lookup"><span data-stu-id="72624-126">Explore the decision tree</span></span>  
  
1.  <span data-ttu-id="72624-127">Cliquez sur le nœud **tout** , puis examinez la **légende d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="72624-127">Click the **All** node, and look at the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="72624-128">Elle affiche le nombre exact de cas dans le jeu de données d'apprentissage, ainsi qu'une décomposition des résultats.</span><span class="sxs-lookup"><span data-stu-id="72624-128">It displays the exact count of cases in the training data set, as well as a breakdown of the outcomes.</span></span>  
  
     <span data-ttu-id="72624-129">Vous pouvez afficher les mêmes informations dans une info-bulle si vous maintenez le pointeur de la souris au niveau d'un nœud.</span><span class="sxs-lookup"><span data-stu-id="72624-129">You can view the same information in a tooltip if you pause the mouse over a node.</span></span>  
  
2.  <span data-ttu-id="72624-130">Cliquez sur les signes plus et moins en regard de chaque nœud afin de développer ou de réduire l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="72624-130">Click the plus and minus signs next to each node to expand or collapse the tree.</span></span>  
  
     <span data-ttu-id="72624-131">Vous pouvez également utiliser le curseur **afficher le niveau** pour développer ou réduire l’arborescence.</span><span class="sxs-lookup"><span data-stu-id="72624-131">You can also use the **Show Level** slider to expand or shrink the tree.</span></span>  
  
3.  <span data-ttu-id="72624-132">Vous avez remarqué que certains nœuds sont plus foncés que d'autres ?</span><span class="sxs-lookup"><span data-stu-id="72624-132">Notice that some nodes are darker than others?</span></span>  
  
     <span data-ttu-id="72624-133">Par défaut, l' **alimentation** est utilisée comme variable d’ombrage, ce qui signifie que l’intensité de la couleur montre les nœuds les plus pris en charge.</span><span class="sxs-lookup"><span data-stu-id="72624-133">By default, **Population** is used as the shading variable, which means that the intensity of the color shows you which nodes have the most support.</span></span>  
  
     <span data-ttu-id="72624-134">Par conséquent, le nœud situé le plus à gauche est le plus foncé, car il contient le dataset entier.</span><span class="sxs-lookup"><span data-stu-id="72624-134">Therefore the leftmost node is darkest, because it contains the entire dataset.</span></span>  
  
4.  <span data-ttu-id="72624-135">Remplacez la valeur de l' **arrière-plan** de **tous les cas** par **Oui**.</span><span class="sxs-lookup"><span data-stu-id="72624-135">Change the value for **Background** from **All Cases** to **Yes**.</span></span>  
  
     <span data-ttu-id="72624-136">![modifier le graphique de l'arbre de décision pour mettre en surbrillance les acheteurs](media/dm13-dectreeshadedbuyer.gif "modifier le graphique de l'arbre de décision pour mettre en surbrillance les acheteurs")</span><span class="sxs-lookup"><span data-stu-id="72624-136">![changing decision tree graph to highlight buyers](media/dm13-dectreeshadedbuyer.gif "changing decision tree graph to highlight buyers")</span></span>  
  
5.  <span data-ttu-id="72624-137">Maintenant, l'intensité de la couleur vous indique le nombre de clients dans chaque nœud qui ont acheté un vélo, ce qui correspond au comportement qui vous intéresse.</span><span class="sxs-lookup"><span data-stu-id="72624-137">Now the intensity of the color tells you how many customers in each node purchased a bike, which is the behavior you are interested in.</span></span>  
  
     <span data-ttu-id="72624-138">Notez les barres de couleur dans chaque nœud.</span><span class="sxs-lookup"><span data-stu-id="72624-138">Notice the colored bars within each node.</span></span> <span data-ttu-id="72624-139">Il s'agit d'un histogramme qui montre la distribution des résultats dans ce sous-ensemble de données.</span><span class="sxs-lookup"><span data-stu-id="72624-139">This is a histogram that shows the distribution of outcomes within this subset of data.</span></span> <span data-ttu-id="72624-140">Par exemple, dans l’arbre de décision Sample Bike Buyer, la barre de couleur affiche la proportion des clients qui ont acheté des vélos (valeurs Oui) par rapport à ceux qui n’en ont pas (aucune valeur).</span><span class="sxs-lookup"><span data-stu-id="72624-140">For example, in the sample Bike Buyer decision tree, the colored bar shows the proportion of customers who bought bikes (Yes values) vs. those who did not (No values).</span></span> <span data-ttu-id="72624-141">Pour obtenir les valeurs exactes, vous pouvez cliquer sur le nœud et afficher la **légende d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="72624-141">To get the exact values, you can click the node and view the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="72624-142">En suivant le graphique, vous pouvez voir comment chaque sous-ensemble de données est à son tour décomposé en groupes plus petits, ainsi que les attributs qui sont le plus utile lors de la prédiction d'un résultat.</span><span class="sxs-lookup"><span data-stu-id="72624-142">By following the graph, you can see how each subset of data is further decomposed into smaller groups, and which attributes are most useful in predicting an outcome.</span></span>  
  
     <span data-ttu-id="72624-143">Il suffit d'observer l'intensité de l'ombrage pour pouvoir se concentrer sur quelques groupes d'intérêt et obtenir des données plus détaillées à leur sujet pour effectuer une comparaison.</span><span class="sxs-lookup"><span data-stu-id="72624-143">Just by looking at the intensity of the shading, you can focus on a couple groups of interest, and get more detailed data on them for comparison.</span></span> <span data-ttu-id="72624-144">Par exemple, ces groupes présentent une probabilité relativement élevée d'acheter des vélos :</span><span class="sxs-lookup"><span data-stu-id="72624-144">For example, these groups have a fairly high probability of buying bikes:</span></span>  
  
    -   <span data-ttu-id="72624-145">Âge >= 32 et \< 53 and Yearly Income > = 26000 et enfants = 0</span><span class="sxs-lookup"><span data-stu-id="72624-145">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children = 0</span></span>  
  
         <span data-ttu-id="72624-146">Nombre total de cas : 1150</span><span class="sxs-lookup"><span data-stu-id="72624-146">Total cases: 1150</span></span>  
  
         <span data-ttu-id="72624-147">Probabilité d’achat de vélo : 18%</span><span class="sxs-lookup"><span data-stu-id="72624-147">Bike buyer probability: 18%</span></span>  
  
    -   <span data-ttu-id="72624-148">Age >= 32 et \< 53 and Yearly Income > = 26000 et enfants not = 0 et matrimonial Status = 'single'</span><span class="sxs-lookup"><span data-stu-id="72624-148">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children not = 0 and Marital Status = 'Single'</span></span>  
  
         <span data-ttu-id="72624-149">Total des cas : 402</span><span class="sxs-lookup"><span data-stu-id="72624-149">Total cases: 402</span></span>  
  
         <span data-ttu-id="72624-150">Probabilité d'acheter un vélo : 16 %</span><span class="sxs-lookup"><span data-stu-id="72624-150">Bike buyer probability: 16%</span></span>  
  
7.  <span data-ttu-id="72624-151">Modifiez la valeur de l' **arrière-plan** de **Oui** à **non** et observez la façon dont le graphique change.</span><span class="sxs-lookup"><span data-stu-id="72624-151">Change the value for **Background** from **Yes** to **No** and see how the graph changes.</span></span>  
  
     <span data-ttu-id="72624-152">![Diagramme de réseau de dépendances pour un modèle d'association](media/dm13-dec-tree-background-no.gif "Diagramme de réseau de dépendances pour un modèle d'association")</span><span class="sxs-lookup"><span data-stu-id="72624-152">![Dependency network graph for an association model](media/dm13-dec-tree-background-no.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="72624-153">**Conseils**</span><span class="sxs-lookup"><span data-stu-id="72624-153">**Tips**</span></span>  
  
-   <span data-ttu-id="72624-154">Si vos données peuvent être divisées en plusieurs séries, un modèle différent est créé pour chaque jeu de données à modéliser.</span><span class="sxs-lookup"><span data-stu-id="72624-154">If your data can be divided into multiple series, a different model is built for each set of data that you want to model.</span></span>  
  
-   <span data-ttu-id="72624-155">Dans l’exemple de modèle de données, il n’y a qu’un seul résultat prévisible, mais supposons que vous disposiez d’informations sur l’achat d’un plan de service par le client et que vous souhaitiez le prédire également.</span><span class="sxs-lookup"><span data-stu-id="72624-155">In the sample data model, there is only one predictable outcome - Bike Buyer - but suppose you had information about whether the customer purchased a service plan and wanted to predict that as well.</span></span> <span data-ttu-id="72624-156">Dans ce cas, vous placeriez ces données dans une colonne distincte et vous incluriez deux attributs prédictibles au modèle.</span><span class="sxs-lookup"><span data-stu-id="72624-156">In that case you would have that data in a separate column, and include two predictable attributes in the model.</span></span>  
  
     <span data-ttu-id="72624-157">Cliquez sur l’option **histogramme** , dans le coin supérieur gauche du volet arbre de décision, pour modifier le nombre maximal d’États qui peuvent apparaître dans les histogrammes de l’arbre.</span><span class="sxs-lookup"><span data-stu-id="72624-157">Click the **Histogram** option, in the upper left corner of the Decision Tree pane, to change the maximum number of states that can appear in the histograms in the tree.</span></span> <span data-ttu-id="72624-158">Cette option est utile si l'attribut prévisible possède de nombreux états.</span><span class="sxs-lookup"><span data-stu-id="72624-158">This is useful if the predictable attribute has many states.</span></span> <span data-ttu-id="72624-159">Les états s'affichent dans un histogramme par ordre de fréquence de gauche à droite.</span><span class="sxs-lookup"><span data-stu-id="72624-159">The states appear in a histogram in order of popularity from left to right.</span></span>  
  
-   <span data-ttu-id="72624-160">Vous pouvez également utiliser les options de l’onglet **arbre de décision** pour modifier l’affichage de l’arborescence, en effectuant un zoom avant ou arrière ou en redimensionnant le graphique pour l’ajuster à la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="72624-160">You can also use the options on the **Decision Tree** tab to affect how the tree is displayed, by zooming in or out, or sizing the graph to fit the window.</span></span>  
  
-   <span data-ttu-id="72624-161">Utilisez **Expansion par défaut** pour définir le nombre de niveaux par défaut affichés pour tous les arbres du modèle.</span><span class="sxs-lookup"><span data-stu-id="72624-161">Use **Default Expansion** to set the default number of levels that are displayed for all trees in the model.</span></span>  
  
-   <span data-ttu-id="72624-162">Sélectionnez **afficher le nom long** pour afficher le nom complet de l’attribut, y compris la source de données.</span><span class="sxs-lookup"><span data-stu-id="72624-162">Select **Show long name** to display the full name of the attribute, including the data source.</span></span> <span data-ttu-id="72624-163">Les noms longs et les noms courts sont identiques, sauf si vos cas proviennent d'une source de données différente des attributs de chaque cas.</span><span class="sxs-lookup"><span data-stu-id="72624-163">Short names and long names are the same unless your cases are obtained from a different data source than the attributes for each case.</span></span>  
  
 [<span data-ttu-id="72624-164">Retour au début</span><span class="sxs-lookup"><span data-stu-id="72624-164">Back To Top</span></span>](#bkmk_Top)  
  
###  <a name="dependency-network"></a><a name="BKMK_DNetwork"></a><span data-ttu-id="72624-165">Réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="72624-165">Dependency Network</span></span>  
 <span data-ttu-id="72624-166">La vue **réseau de dépendances** affiche les connexions entre les attributs d’entrée et les attributs prévisibles du modèle.</span><span class="sxs-lookup"><span data-stu-id="72624-166">The **Dependency Network** view displays the connections between the input attributes and the predictable attributes in the model.</span></span>  
  
1.  <span data-ttu-id="72624-167">Cliquez et faites glisser le curseur à gauche de la visionneuse</span><span class="sxs-lookup"><span data-stu-id="72624-167">Click and drag the slider at the left of the viewer</span></span>  
  
     <span data-ttu-id="72624-168">Dans la position supérieure, toutes les connexions sont affichées.</span><span class="sxs-lookup"><span data-stu-id="72624-168">At the top position, all connections are shown.</span></span> <span data-ttu-id="72624-169">Lorsque vous faites glisser le curseur vers le bas, la visionneuse affiche uniquement les liens les plus forts.</span><span class="sxs-lookup"><span data-stu-id="72624-169">When you drag the slider down, only the strongest links are shown in the viewer.</span></span>  
  
2.  <span data-ttu-id="72624-170">Cliquez maintenant sur le nœud Bike Buyer (Acheteur de vélo).</span><span class="sxs-lookup"><span data-stu-id="72624-170">Now click the Bike Buyer node.</span></span>  
  
     <span data-ttu-id="72624-171">![Vue du réseau de dépendances pour les arbres de décision](media/dm13-dectree-depnet.gif "Vue du réseau de dépendances pour les arbres de décision")</span><span class="sxs-lookup"><span data-stu-id="72624-171">![Dependency network view for decision trees](media/dm13-dectree-depnet.gif "Dependency network view for decision trees")</span></span>  
  
     <span data-ttu-id="72624-172">Lorsque vous sélectionnez un nœud, la visionneuse met en surbrillance les dépendances propres à ce nœud.</span><span class="sxs-lookup"><span data-stu-id="72624-172">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="72624-173">Dans ce cas, la visionneuse met en surbrillance chaque nœud qui aide à prédire le résultat.</span><span class="sxs-lookup"><span data-stu-id="72624-173">In this case, the viewer highlights each node that helps predict the outcome.</span></span>  
  
3.  <span data-ttu-id="72624-174">Si la visionneuse contient de nombreux nœuds, vous pouvez rechercher des nœuds spécifiques à l’aide du bouton **Rechercher un nœud** .</span><span class="sxs-lookup"><span data-stu-id="72624-174">If the viewer contains many nodes, you can search for specific nodes by using the **Find Node** button.</span></span> <span data-ttu-id="72624-175">En cliquant sur **Rechercher un nœud** , vous ouvrez la boîte de dialogue **Rechercher un nœud** dans laquelle vous pouvez utiliser un filtre pour rechercher et sélectionner des nœuds spécifiques.</span><span class="sxs-lookup"><span data-stu-id="72624-175">Clicking **Find Node** opens the **Find Node** dialog box, in which you can use a filter to search for and select specific nodes.</span></span>  
  
4.  <span data-ttu-id="72624-176">La légende en bas de la visionneuse associe des codes de couleur au type de dépendance apparaissant dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="72624-176">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="72624-177">Par exemple, lorsque vous sélectionnez un nœud prévisible, le nœud prévisible est surligné en turquoise et les nœuds permettant de prédire le nœud sélectionné sont surlignés en orange.</span><span class="sxs-lookup"><span data-stu-id="72624-177">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="72624-178">Retour au début</span><span class="sxs-lookup"><span data-stu-id="72624-178">Back To Top</span></span>](#bkmk_Top)  
  
### <a name="drill-through-to-underlying-data"></a><span data-ttu-id="72624-179">Explorer les données sous-jacentes</span><span class="sxs-lookup"><span data-stu-id="72624-179">Drill through to Underlying Data</span></span>  
 <span data-ttu-id="72624-180">Plusieurs types de modèles prennent en charge la possibilité d’effectuer une *extraction* du modèle vers les données de cas sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="72624-180">Several types of models support the ability to *drill through* from the model to the underlying case data.</span></span> <span data-ttu-id="72624-181">Cela peut se révéler très utile si vous voulez contacter les clients dans un segment particulier ou extraire les données pour poursuivre l'analyse.</span><span class="sxs-lookup"><span data-stu-id="72624-181">This can be very useful if you want to contact customers in a particular segment or pull out the data to perform further analysis.</span></span>  
  
##### <a name="get-case-data"></a><span data-ttu-id="72624-182">Obtenir les données de cas</span><span class="sxs-lookup"><span data-stu-id="72624-182">Get case data</span></span>  
  
1.  <span data-ttu-id="72624-183">Cliquez avec le bouton droit sur le nœud de l'arborescence qui contient les données désirées, puis sélectionnez l'une de ces options :</span><span class="sxs-lookup"><span data-stu-id="72624-183">Right-click the node in the tree that contains the desired data and select one of these options:</span></span>  
  
    -   <span data-ttu-id="72624-184">**Extraire le modèle**.</span><span class="sxs-lookup"><span data-stu-id="72624-184">**Drill Through Model**.</span></span> <span data-ttu-id="72624-185">Cette option permet d'obtenir les cas qui appartiennent au nœud sélectionné et de les enregistrer dans un tableau Excel.</span><span class="sxs-lookup"><span data-stu-id="72624-185">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="72624-186">Vous obtenez uniquement les colonnes de données ayant été réellement utilisées lors de la génération du modèle.</span><span class="sxs-lookup"><span data-stu-id="72624-186">You get back only the columns of data that were actually used in building the model.</span></span>  
  
    -   <span data-ttu-id="72624-187">**Extraire les colonnes de structure**.</span><span class="sxs-lookup"><span data-stu-id="72624-187">**Drill Through Structure Columns**.</span></span> <span data-ttu-id="72624-188">Cette option permet d'obtenir les cas qui appartiennent au nœud sélectionné et de les enregistrer dans un tableau Excel.</span><span class="sxs-lookup"><span data-stu-id="72624-188">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="72624-189">Vous pouvez obtenir toutes les informations qui étaient disponibles dans les données sous-jacentes quand vous les avez créées, même si une colonne n’a pas été utilisée dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="72624-189">You get all information that was available in the underlying data when you built it, even of a column wasn't used in the model.</span></span> <span data-ttu-id="72624-190">Par exemple, vous avez peut-être exclu l'adresse et le code postal du client car ces champs ne sont pas utiles pour l'analyse, mais vous les avez laissés dans la structure.</span><span class="sxs-lookup"><span data-stu-id="72624-190">For example, you might have excluded the customer address and zip code because those fields are not useful with analysis, but left them in the structure.</span></span>  
  
     <span data-ttu-id="72624-191">Revenez dans Excel pour afficher vos données.</span><span class="sxs-lookup"><span data-stu-id="72624-191">Return to Excel to view your data.</span></span> <span data-ttu-id="72624-192">La visionneuse Parcourir exécute une requête, enregistre les données dans un tableau dans une nouvelle feuille de calcul, puis étiquette les résultats.</span><span class="sxs-lookup"><span data-stu-id="72624-192">The Browse viewer runs a query, saves the data to a table in a new worksheet, and labels the results.</span></span>  
  
     <span data-ttu-id="72624-193">![les résultats de l'extraction sont enregistrés dans Excel](media/dm13-dectree-drillthroughresults.gif "les résultats de l'extraction sont enregistrés dans Excel")</span><span class="sxs-lookup"><span data-stu-id="72624-193">![results of drillthrough are saved to Excel](media/dm13-dectree-drillthroughresults.gif "results of drillthrough are saved to Excel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72624-194">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="72624-194">See Also</span></span>  
 [<span data-ttu-id="72624-195">Exploration des modèles dans Excel &#40;SQL Server les compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="72624-195">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
