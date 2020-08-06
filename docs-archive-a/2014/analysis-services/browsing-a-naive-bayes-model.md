---
title: Exploration d’un modèle Naive Bayes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9160b48-3beb-439c-9694-f084e1afa625
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3b0d18cd74e71f1ef18bffd6b0998e0b326e887a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602559"
---
# <a name="browsing-a-naive-bayes-model"></a><span data-ttu-id="1e248-102">Navigation dans un modèle Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="1e248-102">Browsing a Naive Bayes Model</span></span>
  <span data-ttu-id="1e248-103">Lorsque vous ouvrez un modèle Naïve Bayes à l’aide de l’outil **Parcourir**, le modèle est affiché dans une visionneuse interactive avec quatre volets différents.</span><span class="sxs-lookup"><span data-stu-id="1e248-103">When you open a Naïve Bayes model using **Browse**, the model is displayed in an interactive viewer with four different panes.</span></span> <span data-ttu-id="1e248-104">Utilisez la visionneuse pour explorer les corrélations et obtenez des informations sur le modèle et les données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="1e248-104">Use the viewer to explore correlations, and get information about the model and the underlying data.</span></span>  
  
-   [<span data-ttu-id="1e248-105">Réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="1e248-105">Dependency Network</span></span>](#bkmk_DepNet)  
  
-   [<span data-ttu-id="1e248-106">Profils d'attribut</span><span class="sxs-lookup"><span data-stu-id="1e248-106">Attribute Profiles</span></span>](#bkmk_AttProf)  
  
-   [<span data-ttu-id="1e248-107">Caractéristiques d’attribut</span><span class="sxs-lookup"><span data-stu-id="1e248-107">Attribute Characteristics</span></span>](#bkmk_AttChar)  
  
-   [<span data-ttu-id="1e248-108">Discrimination d’attribut</span><span class="sxs-lookup"><span data-stu-id="1e248-108">Attribute Discrimination</span></span>](#bkmk_AttDisc)  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="1e248-109">Explorer le modèle</span><span class="sxs-lookup"><span data-stu-id="1e248-109">Explore the Model</span></span>  
 <span data-ttu-id="1e248-110">Le but de la visionneuse est de vous aider à explorer les interactions entre les attributs d'entrée et de sortie (entrées et variables dépendantes) qui ont été découvertes par le modèle [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes.</span><span class="sxs-lookup"><span data-stu-id="1e248-110">The purpose of the viewer is to help you explore the interaction between input and output attributes (inputs and dependent variables) that were discovered by the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes model.</span></span>  
  
 <span data-ttu-id="1e248-111">Si vous souhaitez faire des essais avec la visionneuse Naïve Bayes, utilisez l' [Assistant de classification &#40;les compléments d’exploration de données pour Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) Assistant dans le ruban exploration de données, cliquez sur l’option **avancé** et modifiez l’algorithme pour utiliser l’algorithme Naïve Bayes</span><span class="sxs-lookup"><span data-stu-id="1e248-111">If you want to experiment with the Naïve Bayes viewer, use the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard in the Data Mining ribbon, click the **Advanced** option, and change the algorithm to use the Naïve Bayes algorithm</span></span>  
  
 <span data-ttu-id="1e248-112">Pour ces exemples, nous avons utilisé les données sources dans l’exemple de classeur et regroupé la colonne **Yearly Income**en cinq groupes de revenus, de **très bas** à **très élevé**.</span><span class="sxs-lookup"><span data-stu-id="1e248-112">For these examples, we used the Source data in the sample workbook, and grouped the column, **Yearly Income**, into five income groups, from **Very Low** to **Very High**.</span></span> <span data-ttu-id="1e248-113">Le modèle Naïve Bayes a ensuite analysé les facteurs corrélés à chaque catégorie de revenu.</span><span class="sxs-lookup"><span data-stu-id="1e248-113">The Naïve Bayes model then analyzed the factors correlated with each income category.</span></span>  
  
###  <a name="dependency-network"></a><a name="bkmk_DepNet"></a><span data-ttu-id="1e248-114">Réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="1e248-114">Dependency Network</span></span>  
 <span data-ttu-id="1e248-115">La première fenêtre que vous allez utiliser est le **réseau de dépendances**.</span><span class="sxs-lookup"><span data-stu-id="1e248-115">The first window you'll use is the **Dependency Network**.</span></span> <span data-ttu-id="1e248-116">Elle vous présente d'un coup d'œil les entrées qui sont étroitement corrélées avec le résultat sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1e248-116">It shows you at a glance which inputs are closely correlated to the selected outcome.</span></span>  
  
 <span data-ttu-id="1e248-117">![réseau de dépendances dans la visionneuse Naive Bayes](media/dm13-nb.gif "réseau de dépendances dans la visionneuse Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="1e248-117">![dependency network in Naive Bayes viewer](media/dm13-nb.gif "dependency network in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-dependency-network"></a><span data-ttu-id="1e248-118">Explorer le réseau de dépendances</span><span class="sxs-lookup"><span data-stu-id="1e248-118">Explore the dependency network</span></span>  
  
1.  <span data-ttu-id="1e248-119">Tout d’abord, cliquez sur le résultat cible, **Yearly Income**, qui est représenté sous la forme d’un nœud dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="1e248-119">First, click the target outcome, **Yearly Income**, which is represented as a node in the graph.</span></span>  
  
     <span data-ttu-id="1e248-120">Les nœuds en surbrillance qui entourent la variable cible sont ceux qui sont statistiquement corrélés avec ce résultat.</span><span class="sxs-lookup"><span data-stu-id="1e248-120">The highlighted nodes surrounding the target variable are those that are statistically correlated with this outcome.</span></span> <span data-ttu-id="1e248-121">Utilisez la légende au bas de la visionneuse pour comprendre la nature de la relation.</span><span class="sxs-lookup"><span data-stu-id="1e248-121">Use the legend at the bottom of the viewer to understand the nature of the relationship.</span></span>  
  
2.  <span data-ttu-id="1e248-122">Cliquez sur le curseur à gauche de la visionneuse et faites-le glisser vers le bas.</span><span class="sxs-lookup"><span data-stu-id="1e248-122">Click the slider at the left of the viewer and drag it downward.</span></span>  
  
     <span data-ttu-id="1e248-123">Ce contrôle filtre les variables indépendantes, en fonction de l'intensité des dépendances.</span><span class="sxs-lookup"><span data-stu-id="1e248-123">This control filters the independent variables, based on the strengths of the dependencies.</span></span> <span data-ttu-id="1e248-124">Lorsque vous faites glisser le curseur vers le bas, seuls les liens les plus forts restent dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="1e248-124">When you drag the slider down, only the strongest links remain in the graph.</span></span>  
  
3.  <span data-ttu-id="1e248-125">Après avoir filtré le graphique, cliquez sur le bouton Copier la **vue du graphique**.</span><span class="sxs-lookup"><span data-stu-id="1e248-125">After you have filtered the graph, click the button, **Copy Graph View**.</span></span> <span data-ttu-id="1e248-126">Sélectionnez ensuite une feuille de calcul dans Excel, puis appuyez sur Ctrl+V.</span><span class="sxs-lookup"><span data-stu-id="1e248-126">Then select a worksheet in Excel, and press Ctrl+V.</span></span>  
  
     <span data-ttu-id="1e248-127">Cette option copie la vue sélectionnée, y compris les filtres et la mise en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="1e248-127">This option copies the view that you have selected, including filters and highlighting.</span></span>  
  
 [<span data-ttu-id="1e248-128">Retour au début</span><span class="sxs-lookup"><span data-stu-id="1e248-128">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-profiles"></a><a name="bkmk_AttProf"></a><span data-ttu-id="1e248-129">Profils d’attribut</span><span class="sxs-lookup"><span data-stu-id="1e248-129">Attribute Profiles</span></span>  
 <span data-ttu-id="1e248-130">Les fenêtres **profils d’attribut** vous donnent une indication visuelle sur la façon dont toutes les autres variables sont liées aux résultats individuels.</span><span class="sxs-lookup"><span data-stu-id="1e248-130">The **Attribute Profiles** windows gives you a visual indication of how all other variables are related to the individual outcomes.</span></span>  
  
##### <a name="explore-the-profiles"></a><span data-ttu-id="1e248-131">Explorer les profils</span><span class="sxs-lookup"><span data-stu-id="1e248-131">Explore the profiles</span></span>  
  
1.  <span data-ttu-id="1e248-132">Pour masquer certaines valeurs de manière à pouvoir comparer plus facilement les résultats, cliquez sur l'en-tête de colonne et faites-le glisser sous une autre colonne.</span><span class="sxs-lookup"><span data-stu-id="1e248-132">To hide some values so that you can more easily compare outcomes, click the column heading and drag it under another column.</span></span>  
  
     <span data-ttu-id="1e248-133">![profils d'attribut dans la visionneuse Naive Bayes](media/dm13-nb-attprof.gif "profils d'attribut dans la visionneuse Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="1e248-133">![attribute profiles in Naive Bayes viewer](media/dm13-nb-attprof.gif "attribute profiles in Naive Bayes viewer")</span></span>  
  
2.  <span data-ttu-id="1e248-134">Cliquez dans n’importe quelle cellule pour afficher la distribution des valeurs dans la **légende d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="1e248-134">Click in any cell to view the distribution of values in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="1e248-135">Les attributs associés à des résultats différents étant affichés visuellement, il est facile de repérer des corrélations intéressantes, telles que le mode de distribution des revenus par région.</span><span class="sxs-lookup"><span data-stu-id="1e248-135">Because the attributes associated with different outcomes are displayed visually, it is easy to spot interesting correlations, such as how incomes are distributed by region.</span></span>  
  
3.  <span data-ttu-id="1e248-136">Pour obtenir les données sous-jacentes de cette vue, cliquez sur **copier dans Excel**.</span><span class="sxs-lookup"><span data-stu-id="1e248-136">To obtain the data underlying this view, click **Copy to Excel**.</span></span> <span data-ttu-id="1e248-137">Un tableau est généré dans une nouvelle feuille de calcul qui affiche les corrélations entre les différents attributs et résultats.</span><span class="sxs-lookup"><span data-stu-id="1e248-137">A table is generated in a new worksheet that shows the correlations among individual attributes and outcomes.</span></span> <span data-ttu-id="1e248-138">Dans ce tableau Excel, vous pouvez masquer ou filtrer facilement les colonnes.</span><span class="sxs-lookup"><span data-stu-id="1e248-138">In this Excel table you can easily hide or filter columns.</span></span>  
  
 [<span data-ttu-id="1e248-139">Retour au début</span><span class="sxs-lookup"><span data-stu-id="1e248-139">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-characteristics"></a><a name="bkmk_AttChar"></a> <span data-ttu-id="1e248-140">Caractéristiques d'attribut</span><span class="sxs-lookup"><span data-stu-id="1e248-140">Attribute Characteristics</span></span>  
 <span data-ttu-id="1e248-141">La vue **caractéristiques d’attribut** est utile pour l’examen approfondi d’une variable de résultat particulière et les facteurs de contribution.</span><span class="sxs-lookup"><span data-stu-id="1e248-141">The **Attribute Characteristics** view is useful for in-depth examination of a particular outcome variable and the contributing factors.</span></span>  
  
 <span data-ttu-id="1e248-142">![caractéristiques d'attribut dans la visionneuse Naive Bayes](media/dm13-nb-viewer.gif "caractéristiques d'attribut dans la visionneuse Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="1e248-142">![attribute characteristics in Naive Bayes viewer](media/dm13-nb-viewer.gif "attribute characteristics in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-attribute-characteristics"></a><span data-ttu-id="1e248-143">Explorer les caractéristiques d'attribut</span><span class="sxs-lookup"><span data-stu-id="1e248-143">Explore the attribute characteristics</span></span>  
  
1.  <span data-ttu-id="1e248-144">Cliquez sur **valeur** et sélectionnez un élément dans la **valeur**.</span><span class="sxs-lookup"><span data-stu-id="1e248-144">Click **Value** and select an item from the **Value**.</span></span>  
  
     <span data-ttu-id="1e248-145">À mesure que vous sélectionnez un résultat cible, le graphique est actualisé afin d'afficher les facteurs les plus fortement associés au résultat, triés par ordre d'importance.</span><span class="sxs-lookup"><span data-stu-id="1e248-145">As you select a target outcome, the graph updates to show the factors that are most strongly associated with the outcome, sorted by importance.</span></span>  
  
     <span data-ttu-id="1e248-146">Notez que si vous créez un modèle à l’aide de l’option [analyser les influenceurs clés &#40;les outils d’analyse de table pour Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) , vous pouvez créer des modèles qui ont plusieurs attributs prévisibles.</span><span class="sxs-lookup"><span data-stu-id="1e248-146">Note that if you create a model using the [Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) option, you can create models that have more than one predictable attribute.</span></span> <span data-ttu-id="1e248-147">Cependant, tous les autres assistants des compléments d'exploration de données vous limitent à un attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="1e248-147">However, all other wizards in the Data Mining add-ins limit you to one predictable attribute.</span></span>  
  
2.  <span data-ttu-id="1e248-148">Cliquez sur **copier dans Excel** pour créer une table, dans une nouvelle feuille de calcul, qui répertorie les scores pour tous les attributs associés au résultat cible sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1e248-148">Click **Copy to Excel** to create a table, in a new worksheet, listing the scores for all attributes that are related to the selected target outcome.</span></span>  
  
 [<span data-ttu-id="1e248-149">Retour au début</span><span class="sxs-lookup"><span data-stu-id="1e248-149">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-discrimination"></a><a name="bkmk_AttDisc"></a> <span data-ttu-id="1e248-150">Discrimination d'attribut</span><span class="sxs-lookup"><span data-stu-id="1e248-150">Attribute Discrimination</span></span>  
 <span data-ttu-id="1e248-151">La vue **discrimination d’attribut** permet de comparer deux résultats, ou un résultat et tous les autres résultats.</span><span class="sxs-lookup"><span data-stu-id="1e248-151">The **Attribute Discrimination** view helps compare two outcomes, or one outcome vs. all other outcomes.</span></span>  
  
 <span data-ttu-id="1e248-152">![discrimination d'attribut dans la visionneuse Naive Bayes](media/dm13-nb-attdisc.gif "discrimination d'attribut dans la visionneuse Naive Bayes")</span><span class="sxs-lookup"><span data-stu-id="1e248-152">![attribute discrimination in Naive Bayes viewer](media/dm13-nb-attdisc.gif "attribute discrimination in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-attribute-discrimination"></a><span data-ttu-id="1e248-153">Explorer la discrimination d'attribut</span><span class="sxs-lookup"><span data-stu-id="1e248-153">Explore attribute discrimination</span></span>  
  
1.  <span data-ttu-id="1e248-154">Utilisez les contrôles, **valeur 1** et **valeur 2**, pour sélectionner les résultats que vous souhaitez comparer.</span><span class="sxs-lookup"><span data-stu-id="1e248-154">Use the controls, **Value 1** and **Value 2**, to select the outcomes that you want to compare.</span></span>  
  
     <span data-ttu-id="1e248-155">Par exemple, dans ce modèle, il existait des attributs intéressants dans le groupe faible revenu, donc nous choisissons le groupe revenu le plus bas dans la première liste déroulante et nous choisissons **tous les autres États** dans la deuxième liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="1e248-155">For example, in this model there were some interesting attributes in the low income group, so we chose the lowest income group in the first dropdown list, and chose **All other states** in the second dropdown list.</span></span>  
  
     <span data-ttu-id="1e248-156">Les attributs sont triés par ordre d'importance (calculée en fonction des données d'apprentissage).</span><span class="sxs-lookup"><span data-stu-id="1e248-156">The attributes are sorted by order of importance (calculated based on the training data).</span></span> <span data-ttu-id="1e248-157">Par conséquent, la profession est le facteur le plus étroitement corrélé avec le revenu (du moins pour ce groupe cible),</span><span class="sxs-lookup"><span data-stu-id="1e248-157">Therefore, occupation is the factor most closely correlated with income (for this target group, at least),</span></span>  
  
     <span data-ttu-id="1e248-158">Pour afficher les chiffres exacts, cliquez sur la barre de couleur et affichez la **légende d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="1e248-158">To see the exact figures, click the colored bar and view the **Mining Legend**.</span></span>  
  
2.  <span data-ttu-id="1e248-159">Notez que les revenus les plus bas sont également corrélés à la zone Europe.</span><span class="sxs-lookup"><span data-stu-id="1e248-159">Note that lower incomes are also correlated with the Europe region.</span></span>  
  
     <span data-ttu-id="1e248-160">Le modèle Naïve Bayes ne prend pas en charge l'exploration ; toutefois, si vous souhaitez analyser les cas associés à ce groupe de résultats, vous pouvez utiliser une requête.</span><span class="sxs-lookup"><span data-stu-id="1e248-160">The Naïve Bayes model does not support drilldown; however, if you wanted to investigate the cases associated with this outcome group, you could use a query.</span></span> <span data-ttu-id="1e248-161">Pour plus d’informations sur les requêtes sur ce type de modèle, consultez [exemples de requêtes de modèle Naive Bayes](data-mining/naive-bayes-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="1e248-161">For information about queries on this type of model, see [Naive Bayes Model Query Examples](data-mining/naive-bayes-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="1e248-162">Retour au début</span><span class="sxs-lookup"><span data-stu-id="1e248-162">Back To Top</span></span>](#BKMK_Tabs)  
  
## <a name="see-also"></a><span data-ttu-id="1e248-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e248-163">See Also</span></span>  
 [<span data-ttu-id="1e248-164">Exploration des modèles dans Excel &#40;SQL Server les compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="1e248-164">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
