---
title: Exploration du modèle de clustering (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ce8aa034-161b-473f-baec-9c29e0a8e5f5
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: cca9d395fece59f607c8faf209128b9d32663a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710080"
---
# <a name="exploring-the-clustering-model-basic-data-mining-tutorial"></a><span data-ttu-id="17dc4-102">Exploration du modèle de clustering (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="17dc4-102">Exploring the Clustering Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="17dc4-103">L' [!INCLUDE[msCoName](../includes/msconame-md.md)] algorithme de clustering regroupe les cas en clusters qui contiennent des caractéristiques similaires.</span><span class="sxs-lookup"><span data-stu-id="17dc4-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm groups cases into clusters that contain similar characteristics.</span></span> <span data-ttu-id="17dc4-104">Ces regroupements sont utiles pour l'exploration des données, l'identification d'anomalies dans les données et la création de prédictions.</span><span class="sxs-lookup"><span data-stu-id="17dc4-104">These groupings are useful for exploring data, identifying anomalies in the data, and creating predictions.</span></span>  
  
 <span data-ttu-id="17dc4-105">[!INCLUDE[msCoName](../includes/msconame-md.md)] Cluster Viewer fournit les onglets suivants pour explorer les modèles d'exploration de données de clustering :</span><span class="sxs-lookup"><span data-stu-id="17dc4-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Cluster Viewer provides the following tabs for use in exploring clustering mining models:</span></span>  
  

  
##  <a name="cluster-diagram-tab"></a><a name="ClusterDiagramTab"></a><span data-ttu-id="17dc4-106">Onglet diagramme de cluster</span><span class="sxs-lookup"><span data-stu-id="17dc4-106">Cluster Diagram Tab</span></span>  
 <span data-ttu-id="17dc4-107">L'onglet Diagramme de cluster affiche tous les clusters qui sont dans un modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="17dc4-107">The Cluster Diagram tab displays all the clusters that are in a mining model.</span></span> <span data-ttu-id="17dc4-108">Les lignes entre les clusters représentent le lien logique et sont plus ou moins ombrées selon le degré de similitude entre les clusters.</span><span class="sxs-lookup"><span data-stu-id="17dc4-108">The lines between the clusters represent "closeness" and are shaded based on how similar the clusters are.</span></span> <span data-ttu-id="17dc4-109">La couleur actuelle de chaque cluster représente la fréquence de la variable et l'état dans le cluster.</span><span class="sxs-lookup"><span data-stu-id="17dc4-109">The actual color of each cluster represents the frequency of the variable and the state in the cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-diagram-tab"></a><span data-ttu-id="17dc4-110">Pour explorer le modèle dans l'onglet Diagramme de cluster</span><span class="sxs-lookup"><span data-stu-id="17dc4-110">To explore the model in the Cluster Diagram tab</span></span>  
  
1.  <span data-ttu-id="17dc4-111">Utilisez la liste **modèle d’exploration de données** en haut de l’onglet **visionneuse de modèle d’exploration** de données pour basculer vers le `TM_Clustering` modèle.</span><span class="sxs-lookup"><span data-stu-id="17dc4-111">Use the **Mining Model** list at the top of the **Mining Model Viewer** tab to switch to the `TM_Clustering` model.</span></span>  
  
2.  <span data-ttu-id="17dc4-112">Dans la liste **visionneuse** , sélectionnez **Microsoft Cluster Viewer**.</span><span class="sxs-lookup"><span data-stu-id="17dc4-112">In the **Viewer** list, select **Microsoft Cluster Viewer**.</span></span>  
  
3.  <span data-ttu-id="17dc4-113">Dans la zone **variable d’ombrage** , sélectionnez **vélos Buyer**.</span><span class="sxs-lookup"><span data-stu-id="17dc4-113">In the **Shading Variable** box, select **Bike Buyer**.</span></span>  
  
     <span data-ttu-id="17dc4-114">La variable par défaut est **remplissage**, mais vous pouvez la remplacer par n’importe quel attribut du modèle, afin de découvrir les clusters qui contiennent des membres ayant les attributs souhaités.</span><span class="sxs-lookup"><span data-stu-id="17dc4-114">The default variable is **Population**, but you can change this to any attribute in the model, to discover which clusters contain members that have the attributes you want.</span></span>  
  
4.  <span data-ttu-id="17dc4-115">Sélectionnez **1** dans la zone **État** pour explorer les cas où un vélo a été acheté.</span><span class="sxs-lookup"><span data-stu-id="17dc4-115">Select **1** in the **State** box to explore those cases where a bike was purchased.</span></span>  
  
     <span data-ttu-id="17dc4-116">La légende **densité** décrit la densité de la paire état d’attribut sélectionnée dans la variable d’ombrage et l’État.</span><span class="sxs-lookup"><span data-stu-id="17dc4-116">The **Density** legend describes the density of the attribute state pair selected in the Shading Variable and the State.</span></span> <span data-ttu-id="17dc4-117">Dans cet exemple, il nous dit que le clusterwith l’ombrage le plus foncé a le pourcentage le plus élevé d’acheteurs de vélos.</span><span class="sxs-lookup"><span data-stu-id="17dc4-117">In this example it tells us that the clusterwith the darkest shading has the highest percentage of bike buyers.</span></span>  
  
5.  <span data-ttu-id="17dc4-118">Arrêtez votre souris sur le cluster avec l'ombrage le plus foncé.</span><span class="sxs-lookup"><span data-stu-id="17dc4-118">Pause your mouse over the cluster with the darkest shading.</span></span>  
  
     <span data-ttu-id="17dc4-119">Une info-bulle affiche le pourcentage des cas qui ont l'attribut, `Bike Buyer = 1`.</span><span class="sxs-lookup"><span data-stu-id="17dc4-119">A tooltip displays the percentage of cases that have the attribute, `Bike Buyer = 1`.</span></span>  
  
6.  <span data-ttu-id="17dc4-120">Sélectionnez le cluster ayant la densité la plus élevée, cliquez avec le bouton droit sur le cluster, sélectionnez **Renommer le cluster** et tapez Bike Buyers **High** pour une identification ultérieure.</span><span class="sxs-lookup"><span data-stu-id="17dc4-120">Select the cluster that has the highest density, right-click the cluster, select **Rename Cluster** and type **Bike Buyers High** for later identification.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="17dc4-121">Recherchez le cluster qui a l'ombrage le plus clair (et la densité la plus faible).</span><span class="sxs-lookup"><span data-stu-id="17dc4-121">Find the cluster that has the lightest shading (and the lowest density).</span></span> <span data-ttu-id="17dc4-122">Cliquez avec le bouton droit sur le cluster, sélectionnez **Renommer le cluster** et tapez Bike Buyers **Low**.</span><span class="sxs-lookup"><span data-stu-id="17dc4-122">Right-click the cluster, select **Rename Cluster** and type **Bike Buyers Low**.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="17dc4-123">Cliquez sur le cluster Bike Buyers **High** et faites-le glisser vers une zone du volet qui vous donnera un aperçu clair de ses connexions aux autres clusters.</span><span class="sxs-lookup"><span data-stu-id="17dc4-123">Click the **Bike Buyers High** cluster and drag it to an area of the pane that will give you a clear view of its connections to the other clusters.</span></span>  
  
     <span data-ttu-id="17dc4-124">Lorsque vous sélectionnez un cluster, les lignes qui connectent ce cluster aux autres clusters sont mises en surbrillance, afin que vous puissiez consulter facilement toutes les relations du cluster.</span><span class="sxs-lookup"><span data-stu-id="17dc4-124">When you select a cluster, the lines that connect this cluster to other clusters are highlighted, so that you can easily see all the relationships for this cluster.</span></span> <span data-ttu-id="17dc4-125">Lorsque le cluster n'est pas sélectionné, vous pouvez connaître d'après l'obscurité des lignes le degré de force des relations entre tous les clusters du diagramme.</span><span class="sxs-lookup"><span data-stu-id="17dc4-125">When the cluster is not selected, you can tell by the darkness of the lines how strong the relationships are amongst all the clusters in the diagram.</span></span> <span data-ttu-id="17dc4-126">Si l'ombrage est clair ou inexistant, les clusters ne sont pas très similaires.</span><span class="sxs-lookup"><span data-stu-id="17dc4-126">If the shading is light or nonexistent, the clusters are not very similar.</span></span>  
  
9. <span data-ttu-id="17dc4-127">En utilisant le curseur à gauche du réseau, vous pouvez appliquer un filtre pour exclure les liens les moins forts et rechercher les clusters liés par une relation étroite.</span><span class="sxs-lookup"><span data-stu-id="17dc4-127">Use the slider to the left of the network, to filter out the weaker links and find the clusters with the closest relationships.</span></span> <span data-ttu-id="17dc4-128">Le service marketing [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] peut vouloir associer les clusters similaires pour déterminer la meilleure méthode pour remettre le publipostage ciblé.</span><span class="sxs-lookup"><span data-stu-id="17dc4-128">The [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department might want to combine similar clusters together when determining the best method for delivering the targeted mailing.</span></span>  
  

  
##  <a name="cluster-profiles-tab"></a><a name="ClusterProfilesTab"></a><span data-ttu-id="17dc4-129">Onglet Profils du cluster</span><span class="sxs-lookup"><span data-stu-id="17dc4-129">Cluster Profiles Tab</span></span>  
 <span data-ttu-id="17dc4-130">L’onglet **profils du cluster** fournit une vue d’ensemble du `TM_Clustering` modèle.</span><span class="sxs-lookup"><span data-stu-id="17dc4-130">The **Cluster Profiles** tab provides an overall view of the `TM_Clustering` model.</span></span> <span data-ttu-id="17dc4-131">L’onglet **profils du cluster** contient une colonne pour chaque cluster du modèle.</span><span class="sxs-lookup"><span data-stu-id="17dc4-131">The **Cluster Profiles** tab contains a column for each cluster in the model.</span></span> <span data-ttu-id="17dc4-132">La première colonne contient la liste des attributs associés à au moins un cluster.</span><span class="sxs-lookup"><span data-stu-id="17dc4-132">The first column lists the attributes that are associated with at least one cluster.</span></span> <span data-ttu-id="17dc4-133">Les autres colonnes de la visionneuse contiennent la distribution des états d'un attribut pour chaque cluster.</span><span class="sxs-lookup"><span data-stu-id="17dc4-133">The rest of the viewer contains the distribution of the states of an attribute for each cluster.</span></span> <span data-ttu-id="17dc4-134">La distribution d’une variable discrète est indiquée sous la forme d’une barre de couleur avec le nombre maximal de barres affichées dans la liste barres de l' **histogramme** .</span><span class="sxs-lookup"><span data-stu-id="17dc4-134">The distribution of a discrete variable is shown as a colored bar with the maximum number of bars displayed in the **Histogram bars** list.</span></span> <span data-ttu-id="17dc4-135">Les attributs continus sont affichés avec un graphique en losange qui représente l'écart moyen et l'écart type dans chaque cluster.</span><span class="sxs-lookup"><span data-stu-id="17dc4-135">Continuous attributes are displayed with a diamond chart, which represents the mean and standard deviation in each cluster.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-profiles-tab"></a><span data-ttu-id="17dc4-136">Pour explorer le modèle dans l'onglet Profils du cluster</span><span class="sxs-lookup"><span data-stu-id="17dc4-136">To explore the model in the Cluster Profiles tab</span></span>  
  
1.  <span data-ttu-id="17dc4-137">Définissez barres de l' **histogramme** sur **5**.</span><span class="sxs-lookup"><span data-stu-id="17dc4-137">Set **Histogram** bars to **5**.</span></span>  
  
     <span data-ttu-id="17dc4-138">Dans notre modèle, 5 est le nombre maximal d'états pour toute variable.</span><span class="sxs-lookup"><span data-stu-id="17dc4-138">In our model, 5 is the maximum number of states for any one variable.</span></span>  
  
2.  <span data-ttu-id="17dc4-139">Si la **légende d’exploration de données** bloque l’affichage des **profils d’attribut**, déplacez-le hors de la voie.</span><span class="sxs-lookup"><span data-stu-id="17dc4-139">If the **Mining Legend** blocks the display of the **Attribute profiles**, move it out of the way.</span></span>  
  
3.  <span data-ttu-id="17dc4-140">Sélectionnez la colonne Bike Buyers **High** et faites-la glisser vers la droite de la colonne **population** .</span><span class="sxs-lookup"><span data-stu-id="17dc4-140">Select the **Bike Buyers High** column and drag it to the right of the **Population** column.</span></span>  
  
4.  <span data-ttu-id="17dc4-141">Sélectionnez la colonne Bike Buyers **Low** et faites-la glisser vers la droite de la colonne Bike Buyers **High** .</span><span class="sxs-lookup"><span data-stu-id="17dc4-141">Select the **Bike Buyers Low** column and drag it to the right of the **Bike Buyers High** column.</span></span>  
  
5.  <span data-ttu-id="17dc4-142">Cliquez sur la colonne Bike Buyers **High** .</span><span class="sxs-lookup"><span data-stu-id="17dc4-142">Click the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="17dc4-143">La colonne **variables** est triée par ordre d’importance pour ce cluster.</span><span class="sxs-lookup"><span data-stu-id="17dc4-143">The **Variables** column is sorted in order of importance for that cluster.</span></span> <span data-ttu-id="17dc4-144">Faites défiler la colonne et examinez les caractéristiques du cluster Bike Buyer High.</span><span class="sxs-lookup"><span data-stu-id="17dc4-144">Scroll through the column and review characteristics of the Bike Buyer High cluster.</span></span> <span data-ttu-id="17dc4-145">Par exemple, elles sont plus susceptibles d'effectuer des trajets courts domicile-travail.</span><span class="sxs-lookup"><span data-stu-id="17dc4-145">For example, they are more likely to have a short commute.</span></span>  
  
6.  <span data-ttu-id="17dc4-146">Double-cliquez sur la cellule **Age** dans la colonne Bike Buyers **High** .</span><span class="sxs-lookup"><span data-stu-id="17dc4-146">Double-click the **Age** cell in the **Bike Buyers High** column.</span></span>  
  
     <span data-ttu-id="17dc4-147">La **légende d’exploration de données** affiche une vue plus détaillée et vous pouvez voir la tranche d’âge de ces clients, ainsi que l’âge moyen.</span><span class="sxs-lookup"><span data-stu-id="17dc4-147">The **Mining Legend** displays a more detailed view and you can see the age range of these customers as well as the mean age.</span></span>  
  
7.  <span data-ttu-id="17dc4-148">Cliquez avec le bouton droit sur la colonne Bike Buyers **Low** et sélectionnez **masquer la colonne**.</span><span class="sxs-lookup"><span data-stu-id="17dc4-148">Right-click the **Bike Buyers Low** column and select **Hide Column**.</span></span>  
  

  
##  <a name="cluster-characteristics-tab"></a><a name="ClusterCharacteristicsTab"></a><span data-ttu-id="17dc4-149">Onglet caractéristiques du cluster</span><span class="sxs-lookup"><span data-stu-id="17dc4-149">Cluster Characteristics Tab</span></span>  
 <span data-ttu-id="17dc4-150">Avec l’onglet **caractéristiques du cluster** , vous pouvez examiner plus en détail les caractéristiques qui composent un cluster.</span><span class="sxs-lookup"><span data-stu-id="17dc4-150">With the **Cluster Characteristics** tab, you can examine in more detail the characteristics that make up a cluster.</span></span> <span data-ttu-id="17dc4-151">Au lieu de comparer les caractéristiques de tous les clusters (comme dans l'onglet Profils du cluster), vous pouvez explorer un cluster à la fois.</span><span class="sxs-lookup"><span data-stu-id="17dc4-151">Instead of comparing the characteristics of all of the clusters (as in the Cluster Profiles tab), you can explore one cluster at a time.</span></span> <span data-ttu-id="17dc4-152">Par exemple, si vous sélectionnez **Bike** Buyers High dans la liste **cluster** , vous pouvez voir les caractéristiques des clients dans ce cluster.</span><span class="sxs-lookup"><span data-stu-id="17dc4-152">For example, if you select **Bike Buyers High** from the **Cluster** list, you can see the characteristics of the customers in this cluster.</span></span> <span data-ttu-id="17dc4-153">Même si l'affichage est différent de la visionneuse Profils du cluster, les conclusions sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="17dc4-153">Though the display is different from the Cluster Profiles viewer, the findings are the same.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="17dc4-154">À moins que vous n’ayez défini une valeur initiale pour **HoldoutSeed**, les résultats varient chaque fois que vous traitez le modèle.</span><span class="sxs-lookup"><span data-stu-id="17dc4-154">Unless you set an initial value for **holdoutseed**, results will vary each time you process the model.</span></span> <span data-ttu-id="17dc4-155">Pour plus d’informations, consultez [élément HoldoutSeed](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span><span class="sxs-lookup"><span data-stu-id="17dc4-155">For more information, see [HoldoutSeed Element](https://docs.microsoft.com/bi-reference/assl/properties/holdoutseed-element)</span></span>  
  

  
##  <a name="cluster-discrimination-tab"></a><a name="ClusterDiscriminationTab"></a><span data-ttu-id="17dc4-156">Onglet discrimination de cluster</span><span class="sxs-lookup"><span data-stu-id="17dc4-156">Cluster Discrimination Tab</span></span>  
 <span data-ttu-id="17dc4-157">L’onglet **discrimination de cluster** vous permet d’explorer les caractéristiques qui distinguent un cluster d’un autre.</span><span class="sxs-lookup"><span data-stu-id="17dc4-157">With the **Cluster Discrimination** tab, you can explore the characteristics that distinguish one cluster from another.</span></span> <span data-ttu-id="17dc4-158">Une fois que vous avez sélectionné deux clusters, l’un dans la liste **cluster 1** et l’autre dans la liste **cluster 2** , la visionneuse calcule les différences entre les clusters et affiche une liste des attributs qui distinguent la plupart des clusters.</span><span class="sxs-lookup"><span data-stu-id="17dc4-158">After you select two clusters, one from the **Cluster 1** list, and one from the **Cluster 2** list, the viewer calculates the differences between the clusters and displays a list of the attributes that distinguish the clusters most.</span></span>  
  
#### <a name="to-explore-the-model-in-the-cluster-discrimination-tab"></a><span data-ttu-id="17dc4-159">Pour explorer le modèle dans l'onglet Discrimination de cluster</span><span class="sxs-lookup"><span data-stu-id="17dc4-159">To explore the model in the Cluster Discrimination tab</span></span>  
  
1.  <span data-ttu-id="17dc4-160">Dans la zone **cluster 1** , sélectionnez **Bike**Buyers High.</span><span class="sxs-lookup"><span data-stu-id="17dc4-160">In the **Cluster 1** box, select **Bike Buyers High**.</span></span>  
  
2.  <span data-ttu-id="17dc4-161">Dans la zone **cluster 2** , sélectionnez **Bike**Buyers Low.</span><span class="sxs-lookup"><span data-stu-id="17dc4-161">In the **Cluster 2** box, select **Bike Buyers Low**.</span></span>  
  
3.  <span data-ttu-id="17dc4-162">Cliquez sur **variables** pour trier par ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="17dc4-162">Click **Variables** to sort alphabetically.</span></span>  
  
     <span data-ttu-id="17dc4-163">Parmi les différences les plus importantes entre les clients dans les clusters les plus **bas** et les **acheteurs de vélo** , citons l’âge, la propriété de la voiture, le nombre d’enfants et la région.</span><span class="sxs-lookup"><span data-stu-id="17dc4-163">Some of the more substantial differences among the customers in the **Bike Buyers Low** and **Bike Buyers High** clusters include age, car ownership, number of children, and region.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="17dc4-164">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="17dc4-164">Related Tasks</span></span>  
 <span data-ttu-id="17dc4-165">Voir les rubriques qui suivent pour explorer les autres modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="17dc4-165">See the following topics to explore the other mining models.</span></span>  
  
-   [<span data-ttu-id="17dc4-166">Exploration du modèle d’arbre de décision &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="17dc4-166">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="17dc4-167">Exploration du modèle Naive Bayes &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="17dc4-167">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="17dc4-168">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="17dc4-168">Next Task in Lesson</span></span>  
 [<span data-ttu-id="17dc4-169">Exploration du modèle Naive Bayes &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="17dc4-169">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="17dc4-170">Tâche précédente de la leçon</span><span class="sxs-lookup"><span data-stu-id="17dc4-170">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="17dc4-171">Exploration du modèle d’arbre de décision &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="17dc4-171">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="17dc4-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17dc4-172">See Also</span></span>  
 <span data-ttu-id="17dc4-173">[Parcourir un modèle à l’aide de Microsoft Cluster Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="17dc4-173">[Browse a Model Using the Microsoft Cluster Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-cluster-viewer.md) </span></span>  
 <span data-ttu-id="17dc4-174">[Onglet discrimination de cluster &#40;la visionneuse de modèle d’exploration de données&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="17dc4-174">[Cluster Discrimination Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-discrimination-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="17dc4-175">[Onglet Profils du cluster &#40;la visionneuse de modèle d’exploration de données&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="17dc4-175">[Cluster Profiles Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-profiles-tab-mining-model-viewer.md) </span></span>  
 <span data-ttu-id="17dc4-176">[Onglet caractéristiques du cluster &#40;la visionneuse de modèle d’exploration de données&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="17dc4-176">[Cluster Characteristics Tab &#40;Mining Model Viewer&#41;](../../2014/analysis-services/cluster-characteristics-tab-mining-model-viewer.md) </span></span>  
 [<span data-ttu-id="17dc4-177">Onglet diagramme de cluster &#40;visionneuse de modèle d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="17dc4-177">Cluster Diagram Tab &#40;Mining Model Viewer&#41;</span></span>](../../2014/analysis-services/cluster-diagram-tab-mining-model-viewer.md)  
  
  
