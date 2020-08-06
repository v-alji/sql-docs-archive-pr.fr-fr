---
title: Exploration d’un modèle de clustering | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- clustering [data mining]
- mining model, clustering
ms.assetid: 7f3f0949-d791-403a-88e2-54cb1a803dae
author: minewiskan
ms.author: owend
ms.openlocfilehash: f1d508603acd29fde981bddc5642b54ca9413f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602581"
---
# <a name="browsing-a-clustering-model"></a><span data-ttu-id="4a283-102">Exploration d'un modèle de clustering</span><span class="sxs-lookup"><span data-stu-id="4a283-102">Browsing a Clustering Model</span></span>
  <span data-ttu-id="4a283-103">Lorsque vous ouvrez un modèle de clustering à l’aide de l’outil **Parcourir**, le modèle est affiché dans une visionneuse interactive, similaire à la visionneuse de clustering dans [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a283-103">When you open a clustering model using **Browse**, the model is displayed in an interactive viewer, similar to the clustering viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4a283-104">Cette visionneuse vous aide à explorer les clusters qui ont été créés et à comprendre les caractéristiques de cluster.</span><span class="sxs-lookup"><span data-stu-id="4a283-104">The viewer helps you explore the clusters that were created, and understand cluster characteristics.</span></span> <span data-ttu-id="4a283-105">Vous pouvez également comparer des segments individuels avec d'autres segments ou avec la population, et mettre en évidence les différences.</span><span class="sxs-lookup"><span data-stu-id="4a283-105">You can also compare and contrast individual segments with other segments or with the population.</span></span>  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="4a283-106">Explorer le modèle</span><span class="sxs-lookup"><span data-stu-id="4a283-106">Explore the Model</span></span>  
 <span data-ttu-id="4a283-107">La fenêtre **Parcourir** comprend les outils suivants pour vous aider à comprendre votre modèle de clustering et à explorer les attributs des groupes de données sous-jacents :</span><span class="sxs-lookup"><span data-stu-id="4a283-107">The **Browse** window includes the following tools to help you understand your clustering model and explore the attributes of the underlying data groups:</span></span>  
  
-   [<span data-ttu-id="4a283-108">Diagramme de cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-108">Cluster Diagram</span></span>](#BKMK_ClusterDiagram)  
  
-   [<span data-ttu-id="4a283-109">Profils du cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-109">Cluster Profiles</span></span>](#BKMK_ClusterProfiles)  
  
-   [<span data-ttu-id="4a283-110">Caractéristiques du cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-110">Cluster Characteristics</span></span>](#BKMK_ClusterCharacteristics)  
  
-   [<span data-ttu-id="4a283-111">Discrimination de cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-111">Cluster Discrimination</span></span>](#BKMK_ClusterDiscrimination)  
  
 <span data-ttu-id="4a283-112">Pour expérimenter un modèle de clustering, vous pouvez utiliser les exemples de données de l’onglet formation du classeur d’exemples de données et créer un modèle de clustering à l’aide de l' [Assistant cluster &#40;compléments d’exploration de données pour Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) et toutes les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="4a283-112">To experiment with a clustering model, you can use the sample data on the Training tab of the sample data workbook, and build a clustering model using [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) and all the defaults.</span></span>  
  
###  <a name="cluster-diagram"></a><a name="BKMK_ClusterDiagram"></a><span data-ttu-id="4a283-113">Diagramme de cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-113">Cluster Diagram</span></span>  
 <span data-ttu-id="4a283-114">L’onglet **diagramme de cluster** affiche tous les clusters qui se trouvent dans un modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="4a283-114">The **Cluster Diagram** tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="4a283-115">Vous pouvez voir ici le nombre important de regroupements différents qui ont été détectés dans votre jeu de données, ainsi que leur proximité les uns par rapport aux autres.</span><span class="sxs-lookup"><span data-stu-id="4a283-115">Here you can see how many different groupings were found in your data set, and how near or far they are from each other.</span></span>  
  
##### <a name="explore-the-cluster-diagram"></a><span data-ttu-id="4a283-116">Explorer le diagramme de cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-116">Explore the cluster diagram</span></span>  
  
1.  <span data-ttu-id="4a283-117">Cliquez sur Cluster 1 dans le diagramme.</span><span class="sxs-lookup"><span data-stu-id="4a283-117">Click Cluster 1 in the diagram.</span></span>  
  
     <span data-ttu-id="4a283-118">Notez comment les lignes grises reliant tous les clusters changent pour mettre en surbrillance en bleu vif les lignes menant au cluster sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4a283-118">Note how the gray lines connecting all clusters change so that lines leading to the selected cluster are highlighted in bright blue.</span></span>  
  
     <span data-ttu-id="4a283-119">![introduction du diagramme de cluster](media/dm13-cluster-diagram-intro.gif "introduction du diagramme de cluster")</span><span class="sxs-lookup"><span data-stu-id="4a283-119">![cluster diagram intro](media/dm13-cluster-diagram-intro.gif "cluster diagram intro")</span></span>  
  
     <span data-ttu-id="4a283-120">L'intensité de la ligne reliant un cluster à un autre représente le niveau de similarité des clusters.</span><span class="sxs-lookup"><span data-stu-id="4a283-120">The intensity of the line that connects one cluster to another represents the strength of the similarity of the clusters.</span></span> <span data-ttu-id="4a283-121">Si l'ombrage est clair ou inexistant, les clusters ne sont pas très similaires.</span><span class="sxs-lookup"><span data-stu-id="4a283-121">If the shading is light or nonexistent, the clusters are not very similar.</span></span> <span data-ttu-id="4a283-122">Plus la ligne est sombre, plus la similarité entre les deux clusters est importante.</span><span class="sxs-lookup"><span data-stu-id="4a283-122">As the line becomes darker, it indicates that the similarity between the two clusters is stronger.</span></span>  
  
2.  <span data-ttu-id="4a283-123">Cliquez et faites glisser le curseur à gauche du diagramme de cluster pour modifier le nombre de lignes affichées par la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="4a283-123">Click and drag the slider to the left of the cluster diagram, to adjust how many lines the viewer shows.</span></span>  
  
     <span data-ttu-id="4a283-124">Lorsque vous faites glisser le curseur vers le bas, seuls les liens les plus forts entre les clusters sont affichés.</span><span class="sxs-lookup"><span data-stu-id="4a283-124">When you drag the slider down, only the strongest links between clusters are shown.</span></span> <span data-ttu-id="4a283-125">Cela vous aide à vous concentrer sur les groupes associés.</span><span class="sxs-lookup"><span data-stu-id="4a283-125">This helps you focus on related groups.</span></span>  
  
3.  <span data-ttu-id="4a283-126">Notez le contrôle de **variable d’ombrage** dans l’angle supérieur droit de la fenêtre du **diagramme de cluster** .</span><span class="sxs-lookup"><span data-stu-id="4a283-126">Notice the **Shading Variable** control in the upper right corner of the **Cluster Diagram** window.</span></span>  
  
     <span data-ttu-id="4a283-127">Par défaut, il est défini sur **remplissage**.</span><span class="sxs-lookup"><span data-stu-id="4a283-127">By default, it is set to **Population**.</span></span> <span data-ttu-id="4a283-128">Cela signifie que les clusters les plus foncés bénéficient d'une meilleure prise en charge.</span><span class="sxs-lookup"><span data-stu-id="4a283-128">What this means is that the darker clusters have greater support.</span></span>  
  
4.  <span data-ttu-id="4a283-129">Placez le curseur de la souris au niveau d'un cluster.</span><span class="sxs-lookup"><span data-stu-id="4a283-129">Pause over any cluster with the cursor.</span></span>  
  
     <span data-ttu-id="4a283-130">Une info-bulle est affichée pour indiquer la population de ce cluster.</span><span class="sxs-lookup"><span data-stu-id="4a283-130">A ToolTip is displayed that contains the population of that cluster.</span></span>  
  
5.  <span data-ttu-id="4a283-131">Maintenant, cliquez sur la liste déroulante **variable d’ombrage** et choisissez la variable **Age** .</span><span class="sxs-lookup"><span data-stu-id="4a283-131">Now, click the **Shading Variable** dropdown list and choose the **Age** variable.</span></span> <span data-ttu-id="4a283-132">Dans ce cas, une liste de valeurs apparaît dans la zone de texte **État** .</span><span class="sxs-lookup"><span data-stu-id="4a283-132">As you do so, a list of values appears in the **State** text box.</span></span>  
  
     <span data-ttu-id="4a283-133">La colonne d'âge utilisée comme entrée de ce modèle contient des valeurs numériques continues, mais pour les besoins du clustering, l'algorithme discrétise toujours les nombres.</span><span class="sxs-lookup"><span data-stu-id="4a283-133">The Age column used as input to this model contains continuous numeric values, but for the purpose of clustering, the algorithm always discretizes numbers.</span></span> <span data-ttu-id="4a283-134">Ici, vous pouvez voir les emplacements ou les groupes créés par l’algorithme, par exemple « très faible ( \<=27)" and "Very High (> = 63) ».</span><span class="sxs-lookup"><span data-stu-id="4a283-134">Here you can see the bins, or groups that the algorithm created, such as "Very Low (\<=27)" and "Very High (>=63)".</span></span>  
  
6.  <span data-ttu-id="4a283-135">Dans les listes déroulantes **État** , sélectionnez **très élevé** pour voir comment le diagramme change.</span><span class="sxs-lookup"><span data-stu-id="4a283-135">From the **State** dropdown lists, select **Very High** and see how the diagram changes.</span></span>  
  
     <span data-ttu-id="4a283-136">En modifiant la variable d'ombrage, vous pouvez voir d'un coup d'œil les clusters qui contiennent une plus grande part de cette catégorie d'âge cible, ainsi que les clusters qui contiennent très peu de clients dans cette catégorie d'âge.</span><span class="sxs-lookup"><span data-stu-id="4a283-136">By changing the shading variable, you can see at a glance which clusters contain more of this targeted age group, and which clusters contain very few customers in this age group.</span></span>  
  
     <span data-ttu-id="4a283-137">![Modifier le diagramme de cluster pour afficher l'âge](media/dm13-cluster-diagramshadebyage.gif "Modifier le diagramme de cluster pour afficher l'âge")</span><span class="sxs-lookup"><span data-stu-id="4a283-137">![Modify the cluster diagram to show age](media/dm13-cluster-diagramshadebyage.gif "Modify the cluster diagram to show age")</span></span>  
  
     <span data-ttu-id="4a283-138">Plus l'ombrage est foncé, plus la proportion de l'attribut cible et la distribution de valeurs sont importantes pour ce cluster.</span><span class="sxs-lookup"><span data-stu-id="4a283-138">The darker the shading, the larger the proportion of the target attribute and value distribution that cluster.</span></span>  
  
7.  <span data-ttu-id="4a283-139">Recherchez le cluster ombré le plus foncé lorsque la **variable d’ombrage** est définie sur Age >65.</span><span class="sxs-lookup"><span data-stu-id="4a283-139">Locate the cluster that is shaded darkest when the **Shading Variable** is set to Age >65.</span></span>  
  
     <span data-ttu-id="4a283-140">Pointez le curseur de la souris sur le cluster.</span><span class="sxs-lookup"><span data-stu-id="4a283-140">Hover the mouse over the cluster.</span></span>  
  
     <span data-ttu-id="4a283-141">La valeur affichée dans l'info-bulle indique maintenant la population de clients de ce cluster qui ont plus de 65 ans.</span><span class="sxs-lookup"><span data-stu-id="4a283-141">The value displayed in the ToolTip now shows you the population of customers in this cluster who are over 65.</span></span>  
  
8.  <span data-ttu-id="4a283-142">Cliquez avec le bouton droit sur le cluster et sélectionnez **Renommer le cluster**.</span><span class="sxs-lookup"><span data-stu-id="4a283-142">Right-click the cluster and select **Rename Cluster**.</span></span> <span data-ttu-id="4a283-143">Tapez un nouveau nom descriptif, par exemple plus de **65**.</span><span class="sxs-lookup"><span data-stu-id="4a283-143">Type a new name that is descriptive, such as **Over 65**.</span></span> <span data-ttu-id="4a283-144">Le nouveau nom est enregistré avec le modèle sur le serveur et peut être utilisé pour identifier le cluster dans les autres vues de clustering.</span><span class="sxs-lookup"><span data-stu-id="4a283-144">The new name is saved with the model to the server and can be used for identifying the cluster in the other clustering views.</span></span>  
  
 [<span data-ttu-id="4a283-145">Retour au début</span><span class="sxs-lookup"><span data-stu-id="4a283-145">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-profiles"></a><a name="BKMK_ClusterProfiles"></a><span data-ttu-id="4a283-146">Profils de cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-146">Cluster Profiles</span></span>  
 <span data-ttu-id="4a283-147">L’onglet **profils du cluster** vous permet de comparer la composition de tous les clusters en un clin d’œil.</span><span class="sxs-lookup"><span data-stu-id="4a283-147">The **Cluster Profiles** tab lets you compare the makeup of all clusters at a glance.</span></span> <span data-ttu-id="4a283-148">C'est le point de départ idéal pour vous familiariser avec le modèle.</span><span class="sxs-lookup"><span data-stu-id="4a283-148">This is a good place to start when you are getting familiar with the model.</span></span> <span data-ttu-id="4a283-149">Cette vue sera également utile ultérieurement, si vous avez exploré un cluster particulier et que vous devez déterminer ceux qui y sont associés.</span><span class="sxs-lookup"><span data-stu-id="4a283-149">This view is also useful later on, if you have been exploring a particular cluster and decide you need to find related ones.</span></span>  
  
 <span data-ttu-id="4a283-150">Les **profils de cluster** vous donnent également une bonne vue d’ensemble de la façon dont les clusters sont différents.</span><span class="sxs-lookup"><span data-stu-id="4a283-150">**Cluster Profiles** also gives you a good overview of how the clusters are different from each other.</span></span> <span data-ttu-id="4a283-151">Par conséquent, vous apprécierez peut-être le côté pratique de cette vue pour donner à chaque cluster un nom descriptif.</span><span class="sxs-lookup"><span data-stu-id="4a283-151">Therefore, you might find it convenient to use this view to give each cluster a descriptive name.</span></span>  
  
##### <a name="explore-the-cluster-profiles"></a><span data-ttu-id="4a283-152">Explorer les profils de cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-152">Explore the cluster profiles</span></span>  
  
1.  <span data-ttu-id="4a283-153">Cliquez sur la cellule relative aux occupations, dans la colonne **États** , pour afficher la liste de toutes les valeurs pour profession.</span><span class="sxs-lookup"><span data-stu-id="4a283-153">Click the cell for Occupations, in the **States** column, to see the list of all values for Occupation.</span></span>  
  
2.  <span data-ttu-id="4a283-154">Déplacez maintenant le curseur sur la profession dans les profils de cluster.</span><span class="sxs-lookup"><span data-stu-id="4a283-154">Now move the cursor over Occupation in the cluster profiles.</span></span>  
  
     <span data-ttu-id="4a283-155">L'info-bulle affiche la distribution des professions dans ce cluster.</span><span class="sxs-lookup"><span data-stu-id="4a283-155">The ToolTip shows the distribution of occupations in that cluster.</span></span>  
  
     <span data-ttu-id="4a283-156">![Afficher les valeurs détaillées dans les info-bulles ou la légende](media/dm13-cluster-profile-age-tooltip.gif "Afficher les valeurs détaillées dans les info-bulles ou la légende")</span><span class="sxs-lookup"><span data-stu-id="4a283-156">![View detailed values in Tooltips or in Legend](media/dm13-cluster-profile-age-tooltip.gif "View detailed values in Tooltips or in Legend")</span></span>  
  
     <span data-ttu-id="4a283-157">Notez que, dans certains clusters (tels que celui du graphique), la liste des professions n’est pas complète et que certaines professions sont remplacées par l’étiquette **autre**.</span><span class="sxs-lookup"><span data-stu-id="4a283-157">Notice that, in some clusters (such as the one in the graphic), the list of occupations is not complete, and some occupations are replaced with the label, **Other**.</span></span>  
  
     <span data-ttu-id="4a283-158">Cela est inhérent à la conception ; en effet, il peut être difficile de faire la différence entre plusieurs barres de petite taille dans un histogramme.</span><span class="sxs-lookup"><span data-stu-id="4a283-158">This is by design, because it can be hard to tell the difference between many small bars in a histogram.</span></span> <span data-ttu-id="4a283-159">Par défaut, seules les barres de la plus grande importance sont conservées et les barres restantes sont regroupées dans un **autre** compartiment gris.</span><span class="sxs-lookup"><span data-stu-id="4a283-159">By default only the bars of highest importance are retained, and the remaining bars are grouped together into a gray **Other** bucket.</span></span>  
  
     <span data-ttu-id="4a283-160">Pour modifier le nombre de barres visibles dans un histogramme, utilisez l’option barres de l' **histogramme**.</span><span class="sxs-lookup"><span data-stu-id="4a283-160">To change the number of bars that are visible in any histogram, use the option **Histogram bars**.</span></span>  
  
3.  <span data-ttu-id="4a283-161">Notez que la colonne **Age** est différente des autres.</span><span class="sxs-lookup"><span data-stu-id="4a283-161">Note that the **Age** column looks different from the others.</span></span> <span data-ttu-id="4a283-162">Cliquez sur le losange dans le graphique utilisé pour représenter l'âge.</span><span class="sxs-lookup"><span data-stu-id="4a283-162">Click the diamond in the chart used to represent Age.</span></span>  
  
     <span data-ttu-id="4a283-163">La colonne Age (Âge) contenait à l'origine uniquement des nombres continus.</span><span class="sxs-lookup"><span data-stu-id="4a283-163">The column Age originally contained only continuous numbers.</span></span> <span data-ttu-id="4a283-164">L'algorithme de clustering requiert des valeurs discrètes ; il a donc regroupé les valeurs numériques de la colonne d'âge dans un nombre limité de tranches d'âges, en fonction de la distribution de valeurs.</span><span class="sxs-lookup"><span data-stu-id="4a283-164">The clustering algorithm requires discrete values, so it grouped the numeric values in the Age column into a limited number of age groups, based on the distribution of values.</span></span>  
  
4.  <span data-ttu-id="4a283-165">Cliquez sur l'un des graphiques en losange dans un profil de cluster.</span><span class="sxs-lookup"><span data-stu-id="4a283-165">Click one of the diamond charts in a cluster profile.</span></span>  
  
     <span data-ttu-id="4a283-166">Ces graphiques en losange sont affichés uniquement lorsque les données sources utilisent des valeurs numériques continues.</span><span class="sxs-lookup"><span data-stu-id="4a283-166">These diamond charts are displayed only when the source data uses continuous numeric values.</span></span> <span data-ttu-id="4a283-167">Les graphiques en losange fournissent des statistiques descriptives utiles, y compris la moyenne et l'écart type pour cette valeur dans chaque cluster :</span><span class="sxs-lookup"><span data-stu-id="4a283-167">The diamond charts provide some useful descriptive statistics, including the mean and standard deviation for that value in each cluster:</span></span>  
  
    -   <span data-ttu-id="4a283-168">La ligne dans le graphique en losange représente la plage de valeurs pour l'attribut.</span><span class="sxs-lookup"><span data-stu-id="4a283-168">The line in the diamond chart represents the range of values for the attribute.</span></span> <span data-ttu-id="4a283-169">Les valeurs s’affichent également dans la colonne **États** à gauche du graphique **profils** .</span><span class="sxs-lookup"><span data-stu-id="4a283-169">The values are also shown in the **States** column at the left of the **Profiles** chart.</span></span>  
  
    -   <span data-ttu-id="4a283-170">Le centre du losange est positionné à la moyenne du nœud.</span><span class="sxs-lookup"><span data-stu-id="4a283-170">The center of the diamond is positioned at the mean for the node.</span></span>  
  
    -   <span data-ttu-id="4a283-171">La largeur du losange représente la variance de l'attribut à ce nœud.</span><span class="sxs-lookup"><span data-stu-id="4a283-171">The width of the diamond represents the variance of the attribute at that node.</span></span> <span data-ttu-id="4a283-172">Par conséquent, un losange plus étroit indique que le nœud peut créer une prédiction plus précise.</span><span class="sxs-lookup"><span data-stu-id="4a283-172">Therefore, a thinner diamond indicates that the node can create a more accurate prediction.</span></span>  
  
5.  <span data-ttu-id="4a283-173">Pour libérer de l’espace dans le graphique, cliquez avec le bouton droit sur un cluster que vous n’avez pas besoin d’afficher immédiatement, puis sélectionnez **masquer la colonne**.</span><span class="sxs-lookup"><span data-stu-id="4a283-173">To make more room in the graph, right-click a cluster you don't need to view right away, and select **Hide Column**.</span></span> <span data-ttu-id="4a283-174">Cela ne le supprime pas du modèle, il suffit de réduire temporairement la colonne.</span><span class="sxs-lookup"><span data-stu-id="4a283-174">This doesn't delete it from the model, just collapses the column temporarily.</span></span>  
  
     <span data-ttu-id="4a283-175">Pour afficher les clusters que vous avez masqués, vous pouvez cliquer et faire glisser le bord de la colonne, ou sélectionner le nom du cluster dans la liste, **plus de clusters**.</span><span class="sxs-lookup"><span data-stu-id="4a283-175">To view clusters that you've hidden, you can click and drag the column edge, or select the cluster name from the list, **More clusters**.</span></span>  
  
6.  <span data-ttu-id="4a283-176">Faites défiler la liste des attributs vers le bas jusqu'à ce que vous trouviez Bike Buyer, puis recherchez le cluster présentant le pourcentage le plus élevé de valeurs Oui.</span><span class="sxs-lookup"><span data-stu-id="4a283-176">Scroll down the attribute list till you find Bike Buyer, and then find the cluster that has the highest percentage of Yes values.</span></span>  
  
     <span data-ttu-id="4a283-177">Cliquez avec le bouton droit sur l’en-tête de la colonne pour le cluster que vous souhaitez renommer, sélectionnez **Renommer le cluster**et tapez **Bike**Buyers.</span><span class="sxs-lookup"><span data-stu-id="4a283-177">Right-click the column heading for the cluster that you want to rename, select **Rename cluster**, and type **Bike Buyers**.</span></span>  
  
     <span data-ttu-id="4a283-178">Le nouveau nom de cluster est persistant dans toutes les vues, et sur le serveur, jusqu'à ce que vous traitiez une nouvelle fois le modèle.</span><span class="sxs-lookup"><span data-stu-id="4a283-178">The new cluster name is persisted in all views, and on the server, until you reprocess the model.</span></span>  
  
     <span data-ttu-id="4a283-179">![Renommer les clusters pour faciliter l'utilisation d'un graphique](media/dm13-cluster-rename.gif "Renommer les clusters pour faciliter l'utilisation d'un graphique")</span><span class="sxs-lookup"><span data-stu-id="4a283-179">![Rename clusters to make chart easier to use](media/dm13-cluster-rename.gif "Rename clusters to make chart easier to use")</span></span>  
  
 <span data-ttu-id="4a283-180">**Conseils**</span><span class="sxs-lookup"><span data-stu-id="4a283-180">**Tips**</span></span>  
  
-   <span data-ttu-id="4a283-181">Cliquez sur un en-tête de colonne pour trier les attributs par ordre d'importance pour ce cluster.</span><span class="sxs-lookup"><span data-stu-id="4a283-181">Click a column heading to sort the attributes in order of importance for that cluster.</span></span>  
  
-   <span data-ttu-id="4a283-182">Faites glisser les colonnes pour les réorganiser dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="4a283-182">Drag columns to reorder them in the viewer.</span></span>  
  
-   <span data-ttu-id="4a283-183">Cliquez sur une cellule du graphique profils pour afficher des statistiques détaillées dans la **légende d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="4a283-183">Click any cell in the profiles chart to view detailed statistics in the **Mining Legend**.</span></span>  
  
-   <span data-ttu-id="4a283-184">Cliquez avec le bouton droit sur une cellule et sélectionnez **colonnes du modèle d’extraction** pour copier les données sous-jacentes dans une nouvelle feuille de calcul Excel.</span><span class="sxs-lookup"><span data-stu-id="4a283-184">Right-click any cell and select **Drillthrough model columns** to output the underlying data to a new worksheet in Excel.</span></span>  
  
-   <span data-ttu-id="4a283-185">Cliquez avec le bouton droit sur l’en-tête de colonne du cluster et sélectionnez **extraction pour structurer les données** pour obtenir des informations détaillées sur les membres du cluster qui n’étaient pas inclus dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="4a283-185">Right-click the cluster's column heading and select **Drillthrough to structure data** to get detailed information about the cluster members that wasn't included in the model.</span></span>  
  
     <span data-ttu-id="4a283-186">Par exemple, si vous profilez des clients, vous pouvez conserver les informations de contact dans les données sous-jacentes (la structure d’exploration de données) mais ne pas les inclure dans le modèle, car elles ne sont pas utiles pour l’analyse.</span><span class="sxs-lookup"><span data-stu-id="4a283-186">For example, if you are profiling customers, you might leave the contact information in the underlying data (the mining structure) but not include it in the model, because it's not useful for analysis.</span></span> <span data-ttu-id="4a283-187">Cependant, une fois que les clients ont été attribués à des clusters, vous pouvez afficher les informations détaillées à l'aide de l'extraction.</span><span class="sxs-lookup"><span data-stu-id="4a283-187">However, after customers have been assigned to clusters, you can view the detailed data by using drillthrough.</span></span>  
  
 [<span data-ttu-id="4a283-188">Retour au début</span><span class="sxs-lookup"><span data-stu-id="4a283-188">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-characteristics"></a><a name="BKMK_ClusterCharacteristics"></a><span data-ttu-id="4a283-189">Caractéristiques du cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-189">Cluster Characteristics</span></span>  
 <span data-ttu-id="4a283-190">La vue Caractéristiques du cluster vous permet de vraiment explorer un cluster unique, afin de rechercher les attributs qui caractérisent le plus fortement ce groupe de données.</span><span class="sxs-lookup"><span data-stu-id="4a283-190">The Cluster Characteristics view lets you really explore a single cluster, to find which attributes most strongly characterize this group of data.</span></span>  
  
##### <a name="explore-the-cluster-characteristics"></a><span data-ttu-id="4a283-191">Explorer les caractéristiques du cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-191">Explore the cluster characteristics</span></span>  
  
1.  <span data-ttu-id="4a283-192">Sélectionnez le cluster **supérieur à 65** dans la liste des **clusters** .</span><span class="sxs-lookup"><span data-stu-id="4a283-192">Select the **Over 65** cluster from the **Cluster** list.</span></span>  
  
     <span data-ttu-id="4a283-193">Après avoir sélectionné un cluster, vous pouvez examiner en détail les caractéristiques qui composent ce cluster spécifique.</span><span class="sxs-lookup"><span data-stu-id="4a283-193">After you select a cluster, you can see in detail the characteristics that make up that specific cluster.</span></span>  
  
     <span data-ttu-id="4a283-194">Les attributs contenus dans le cluster sont répertoriés dans les colonnes **Variables** et l'état de l'attribut répertorié est répertorié dans la colonne **Valeurs** .</span><span class="sxs-lookup"><span data-stu-id="4a283-194">The attributes that the cluster contains are listed in the **Variables** columns, and the state of the listed attribute is listed in the **Values** column.</span></span>  
  
     <span data-ttu-id="4a283-195">Les États d’attribut sont répertoriés par ordre d’importance, accompagnés de leur probabilité dans ce cluster, représentés sous la forme d’une barre de couleur dans la colonne **probabilité** .</span><span class="sxs-lookup"><span data-stu-id="4a283-195">Attribute states are listed in order of importance, accompanied by their probability in this cluster, represented as a colored bar in the **Probability** column.</span></span>  
  
     <span data-ttu-id="4a283-196">![Caractéristiques d'un modèle de clustering](media/dm13-cluster-characteristics.gif "Caractéristiques d'un modèle de clustering")</span><span class="sxs-lookup"><span data-stu-id="4a283-196">![Characteristics of a clustering model](media/dm13-cluster-characteristics.gif "Characteristics of a clustering model")</span></span>  
  
2.  <span data-ttu-id="4a283-197">Cliquez sur la colonne **variables** pour trier par attribut.</span><span class="sxs-lookup"><span data-stu-id="4a283-197">Click the **Variables** column to sort by attribute.</span></span>  
  
     <span data-ttu-id="4a283-198">En modifiant la variable de tri, vous pouvez voir plus facilement comment les valeurs des variables telles que le revenu ou le fait d'être propriétaire d'une voiture, sont distribuées dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="4a283-198">By changing the sort variable, you can more easily see how values for variables such as income or car ownership are distributed in the group.</span></span>  
  
3.  <span data-ttu-id="4a283-199">Cliquez sur **copier dans Excel**.</span><span class="sxs-lookup"><span data-stu-id="4a283-199">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="4a283-200">Une nouvelle feuille de calcul est ajoutée à votre classeur ; elle contient les caractéristiques du cluster sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4a283-200">A new worksheet is added to your workbook that contains the characteristics of the selected cluster.</span></span>  
  
4.  <span data-ttu-id="4a283-201">Choisissez maintenant un autre cluster dans la liste, **Bike**Buyers.</span><span class="sxs-lookup"><span data-stu-id="4a283-201">Now choose a different cluster from the list, **Bike Buyers**.</span></span>  
  
5.  <span data-ttu-id="4a283-202">Cliquez sur **copier dans Excel**.</span><span class="sxs-lookup"><span data-stu-id="4a283-202">Click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="4a283-203">Notez que le nouveau graphique des caractéristiques du cluster est ajouté sur sa propre feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="4a283-203">Note that the new cluster characteristics chart is added on its own worksheet.</span></span> <span data-ttu-id="4a283-204">Vous pouvez le déplacer sur la même feuille de calcul que l’autre profil pour faciliter sa comparaison, ce que vous ferez à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="4a283-204">You can move it onto the same worksheet as the other profile to make it easier to compare them, which you'll do in the next step.</span></span>  
  
 <span data-ttu-id="4a283-205">**Conseils**</span><span class="sxs-lookup"><span data-stu-id="4a283-205">**Tips**</span></span>  
  
-   <span data-ttu-id="4a283-206">Notez que la caractéristique principale du client dans le cluster plus de 65 est qu’il n’achète pas votre produit.</span><span class="sxs-lookup"><span data-stu-id="4a283-206">Note that the primary characteristic of the customer in the Over 65 cluster is that they don't buy your product!</span></span> <span data-ttu-id="4a283-207">Si vous souhaitez en connaître la raison, vous pouvez parcourir les clusters et comparer les groupes, ou vous pouvez créer un modèle associé à l'aide d'un algorithme qui se prête à l'exploration des causes et des résultats, par exemple un modèle d'arbre de décision ou un modèle Naïve Bayes.</span><span class="sxs-lookup"><span data-stu-id="4a283-207">If you want to know why this is so, you can browse clusters and compare groups, or you might create a related model using an algorithm that is good at exploring causes and outcomes, such as a decision tree model or a Naïve Bayes model.</span></span>  
  
-   <span data-ttu-id="4a283-208">Si vous voulez obtenir la liste complète des attributs et des probabilités pour ce cluster (ou l'ensemble des clusters), vous pouvez créer une requête.</span><span class="sxs-lookup"><span data-stu-id="4a283-208">If you want to get a complete list of attributes and probabilities for this cluster (or all clusters) you can create a query.</span></span> <span data-ttu-id="4a283-209">Pour obtenir des exemples de requêtes sur des modèles de clustering, consultez [exemples de requêtes de modèle de clustering](data-mining/clustering-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="4a283-209">For examples of queries on clustering models, see [Clustering Model Query Examples](data-mining/clustering-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="4a283-210">Retour au début</span><span class="sxs-lookup"><span data-stu-id="4a283-210">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="cluster-discrimination"></a><a name="BKMK_ClusterDiscrimination"></a><span data-ttu-id="4a283-211">Discrimination de cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-211">Cluster Discrimination</span></span>  
 <span data-ttu-id="4a283-212">Vous utilisez l’onglet **discrimination de cluster** pour comparer les attributs entre deux clusters, ou entre un cluster et tous les autres cas du jeu de données.</span><span class="sxs-lookup"><span data-stu-id="4a283-212">You use the **Cluster Discrimination** tab to compare attributes between two clusters, or between a cluster and all the other cases in the data set.</span></span>  
  
 <span data-ttu-id="4a283-213">Pour mettre en évidence les fonctionnalités de cette visionneuse, nous allons la comparer aux tables côte à côte dans Excel que vous avez créées en fonction de la vue des **caractéristiques du cluster** .</span><span class="sxs-lookup"><span data-stu-id="4a283-213">To highlight the features of this viewer, we'll compare it to the side-by-side tables in Excel that you created based on the **Cluster Characteristics** view.</span></span>  
  
##### <a name="explore-cluster-discrimination"></a><span data-ttu-id="4a283-214">Explorer la discrimination de cluster</span><span class="sxs-lookup"><span data-stu-id="4a283-214">Explore cluster discrimination</span></span>  
  
1.  <span data-ttu-id="4a283-215">Utilisez les listes **Cluster 1** et **Cluster 2** pour sélectionner les clusters à comparer.</span><span class="sxs-lookup"><span data-stu-id="4a283-215">Use the **Cluster 1** and **Cluster 2** lists to select the clusters to compare.</span></span>  
  
    -   <span data-ttu-id="4a283-216">Pour Cluster 1, sélectionnez les plus de 65 ans.</span><span class="sxs-lookup"><span data-stu-id="4a283-216">For Cluster 1, select Over 65.</span></span>  
  
    -   <span data-ttu-id="4a283-217">Pour Cluster 2, sélectionnez Bike Buyers.</span><span class="sxs-lookup"><span data-stu-id="4a283-217">For Cluster 2, select Bike Buyers.</span></span>  
  
     <span data-ttu-id="4a283-218">La comparaison doit ressembler au graphique suivant.</span><span class="sxs-lookup"><span data-stu-id="4a283-218">The comparison should look similar to the following graphic.</span></span>  
  
     <span data-ttu-id="4a283-219">![comparaison de clusters dans un modèle](media/dm13-cluster-compareclusters.gif "comparaison de clusters dans un modèle")</span><span class="sxs-lookup"><span data-stu-id="4a283-219">![comparing clusters in a model](media/dm13-cluster-compareclusters.gif "comparing clusters in a model")</span></span>  
  
     <span data-ttu-id="4a283-220">Notez que, en arrière-plan, la visionneuse de **discrimination de cluster** envoie des requêtes complexes au serveur d’exploration de données, afin d’extraire les attributs les plus importants en distinguant les deux groupes, ce qui facilite la comparaison de deux ensembles de clients.</span><span class="sxs-lookup"><span data-stu-id="4a283-220">Note that, under the covers, the **Cluster Discrimination** viewer sends complex queries to the data mining server, to extract the attributes that are most important in distinguishing between the two groups, making it easier to compare two sets of customers.</span></span>  
  
2.  <span data-ttu-id="4a283-221">Cliquez sur l’une des colonnes **favorables..** ..</span><span class="sxs-lookup"><span data-stu-id="4a283-221">Click either of the **Favors...** columns.</span></span>  
  
     <span data-ttu-id="4a283-222">La barre à la droite de l'attribut et de la liste des valeurs montre les fonctionnalités ou les valeurs qui sont les plus importantes en tant que caractéristique du cluster sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4a283-222">The bar to the right of the attribute and value list shows which features or values are most important as a characteristic of the selected cluster.</span></span>  
  
3.  <span data-ttu-id="4a283-223">Comparez maintenant les listes dans Excel.</span><span class="sxs-lookup"><span data-stu-id="4a283-223">Now compare the lists in Excel.</span></span>  
  
     <span data-ttu-id="4a283-224">![Diagramme de réseau de dépendances pour un modèle d'association](media/dm13-comparing-profiles-in-excel.gif "Diagramme de réseau de dépendances pour un modèle d'association")</span><span class="sxs-lookup"><span data-stu-id="4a283-224">![Dependency network graph for an association model](media/dm13-comparing-profiles-in-excel.gif "Dependency network graph for an association model")</span></span>  
  
     <span data-ttu-id="4a283-225">Comme les statistiques sous-jacentes qui étaient utilisées pour créer l'image dans la visionneuse sont enregistrées dans Excel sous forme de tableaux, vous pouvez filtrer et trier, ou encore afficher les valeurs réelles de probabilité.</span><span class="sxs-lookup"><span data-stu-id="4a283-225">Because the underlying statistics that were used to build the image in the viewer are saved to Excel as tables, you can filter and sort, and view the actual probability values.</span></span>  
  
     <span data-ttu-id="4a283-226">En plus d'utiliser Excel, nous vous recommandons d'essayer la visionneuse de cluster pour Visio, qui vous permet également non seulement d'afficher des points de données, mais aussi de modifier en profondeur et d'améliorer le graphique.</span><span class="sxs-lookup"><span data-stu-id="4a283-226">In addition to using Excel, we recommend that you try the cluster viewer for Visio, which also allows you to not just view data points but also extensively modify and enhance the graph.</span></span> <span data-ttu-id="4a283-227">Pour plus d’informations, consultez la [procédure pas à pas relative au diagramme de Cluster &#40;compléments d’exploration de données&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="4a283-227">For more information, see [Cluster Diagram Walkthrough &#40;Data Mining Add-ins&#41;](cluster-diagram-walkthrough-data-mining-add-ins.md).</span></span>  
  
 <span data-ttu-id="4a283-228">**Conseils**</span><span class="sxs-lookup"><span data-stu-id="4a283-228">**Tips**</span></span>  
  
 <span data-ttu-id="4a283-229">Après avoir obtenu des informations sur les groupes de clients, essayez d’utiliser le [scénario de simulation &#40;les outils d’analyse de table pour excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) ou le scénario de recherche de l' [objectif &#40;les outils d’analyse de table pour Excel&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) Tools, afin d’explorer les facteurs du modèle qui peuvent être modifiés pour affecter le résultat.</span><span class="sxs-lookup"><span data-stu-id="4a283-229">After getting some insights into groups of customers, try using the [What-If Scenario &#40;Table Analysis Tools for Excel&#41;](what-if-scenario-table-analysis-tools-for-excel.md) or [Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;](goal-seek-scenario-table-analysis-tools-for-excel.md) tools, to explore factors in the model that might be changed to affect the outcome.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a283-230">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a283-230">See Also</span></span>  
 <span data-ttu-id="4a283-231">[Exploration des modèles dans Excel &#40;SQL Server les compléments d’exploration de données&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="4a283-231">[Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="4a283-232">Assistant de cluster &#40;des compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4a283-232">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
  
