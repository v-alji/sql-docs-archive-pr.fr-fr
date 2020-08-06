---
title: Exploration d’un modèle de prévision | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- forecasting [data mining]
- mining models, viewing
- mining model, time series
- time series [data mining]
ms.assetid: ad35a528-1949-4048-8678-3b9760c1c88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d0b188c4ed6fba9bc5b1082725b17c99081c1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602563"
---
# <a name="browsing-a-forecasting-model"></a><span data-ttu-id="ae7cf-102">Exploration d'un modèle de prévision</span><span class="sxs-lookup"><span data-stu-id="ae7cf-102">Browsing a Forecasting Model</span></span>
  <span data-ttu-id="ae7cf-103">Lorsque vous ouvrez un modèle de prévision à l’aide de **Parcourir**, le modèle est affiché dans une visionneuse interactive, similaire à la visionneuse de modèle de série chronologique dans [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae7cf-103">When you open a forecasting model using **Browse**, the model is displayed in an interactive viewer, similar to the time series model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="ae7cf-104">La visionneuse permet d'explorer les tendances, de comparer les séries, de créer des prédictions et d'obtenir des informations sur le modèle et les données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-104">The viewer helps you explore trends, compare series, create predictions, and get information about the model and the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="ae7cf-105">Explorer le modèle</span><span class="sxs-lookup"><span data-stu-id="ae7cf-105">Explore the Model</span></span>  
 <span data-ttu-id="ae7cf-106">La visionneuse de **recherche** pour les modèles de prévision fournit une vue graphique, qui montre les tendances au fil du temps et vous permet de créer des prédictions, ainsi qu’une vue de modèle, qui représente la série chronologique sous la forme d’un arbre de décision ou d’un arbre de régression.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-106">The **Browse** viewer for forecasting models provides a chart view, which shows the trends over time and lets you create predictions, and a model view, which represents the time series as a decision tree or a regression tree.</span></span>  
  
-   [<span data-ttu-id="ae7cf-107">Vue de graphique</span><span class="sxs-lookup"><span data-stu-id="ae7cf-107">Chart view</span></span>](#bkmk_charts)  
  
-   [<span data-ttu-id="ae7cf-108">Vue Modèle</span><span class="sxs-lookup"><span data-stu-id="ae7cf-108">Model view</span></span>](#bkmk_Model)  
  
 <span data-ttu-id="ae7cf-109">Pour expérimenter un modèle de prévision, vous pouvez utiliser les exemples de données de l’onglet Prévision du classeur d’exemples de données, puis générer un modèle de série chronologique à l’aide de l' [Assistant prévision &#40;les compléments d’exploration de données pour excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) dans le ruban **exploration de données** , ou [prévoir &#40;outils d’analyse de table pour Excel&#41;](forecast-table-analysis-tools-for-excel.md) dans le ruban **analyser** .</span><span class="sxs-lookup"><span data-stu-id="ae7cf-109">To experiment with a forecasting model, you can use the sample data on the Forecast tab of the sample data workbook, and build a time series model using the [Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) in the **Data Mining** ribbon, or [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) in the **Analyze** ribbon.</span></span>  
  
###  <a name="chart"></a><a name="bkmk_charts"></a><span data-ttu-id="ae7cf-110">Nuages</span><span class="sxs-lookup"><span data-stu-id="ae7cf-110">Chart</span></span>  
 <span data-ttu-id="ae7cf-111">L’onglet **graphique** affiche la tendance dans vos séries de données au fil du temps, ainsi que les valeurs prédites.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-111">The **Chart** tab displays the trend in your data series over time, together with the predicted values.</span></span> <span data-ttu-id="ae7cf-112">L'axe vertical du graphique représente les valeurs de la série et l'axe horizontal le temps.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-112">The vertical axis of the chart represents the values of the series, and the horizontal axis represents time.</span></span>  
  
##### <a name="explore-the-forecasting-chart"></a><span data-ttu-id="ae7cf-113">Explorer le graphique de prévision</span><span class="sxs-lookup"><span data-stu-id="ae7cf-113">Explore the forecasting chart</span></span>  
  
1.  <span data-ttu-id="ae7cf-114">Ce modèle contient plusieurs séries chronologiques, mais pour simplifier le graphique, affichez une seule ou quelques séries associées uniquement.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-114">This model contains multiple time series, but to simplify the chart, you can display a single series, or just a few related series.</span></span>  
  
     <span data-ttu-id="ae7cf-115">![prédictions historiques dans le modèle de prévision](media/dm13-forecast-chart-historicpredictions.gif "prédictions historiques dans le modèle de prévision")</span><span class="sxs-lookup"><span data-stu-id="ae7cf-115">![historical predictions in the forecasting model](media/dm13-forecast-chart-historicpredictions.gif "historical predictions in the forecasting model")</span></span>  
  
     <span data-ttu-id="ae7cf-116">Utilisez ces cases à cocher pour sélectionner la prévision pour « North America » seulement, et uniquement pour « Sales Amount ».</span><span class="sxs-lookup"><span data-stu-id="ae7cf-116">Use the check boxes to select the forecast for just North America, and just for sales Amount.</span></span>  
  
2.  <span data-ttu-id="ae7cf-117">Cliquez sur **étapes de prédiction** et tapez une nouvelle valeur pour contrôler le nombre de valeurs de temps futures que vous souhaitez afficher dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-117">Click **Prediction Steps** and type a new value to control how many future time values you want to see in the chart.</span></span>  
  
     <span data-ttu-id="ae7cf-118">La valeur par défaut est 5.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-118">The default is 5.</span></span>  
  
3.  <span data-ttu-id="ae7cf-119">Cliquez sur n’importe quel point de la ligne, historique ou futur, pour afficher les valeurs exactes de ce point dans le temps, affichées dans la **légende d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-119">Click any point in the line, either historical or future, to see the exact values for that point in time, displayed in the **Mining Legend**.</span></span>  
  
4.  <span data-ttu-id="ae7cf-120">Le graphique affiche à la fois les données historiques et les données futures.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-120">The chart displays both historical and future data.</span></span> <span data-ttu-id="ae7cf-121">Notez la ligne en pointillé, avec un arrière-plan ombré.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-121">Note the dotted line, with a shaded background.</span></span> <span data-ttu-id="ae7cf-122">Ces valeurs sont les prédictions futures, en fonction du modèle.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-122">These values are the future predictions, based on the model.</span></span>  
  
     <span data-ttu-id="ae7cf-123">Les données historiques (que vous avez utilisées pour créer le modèle) sont affichées à gauche du graphique.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-123">The historical data (which you used to build the model) is shown in the left side of the chart.</span></span>  
  
5.  <span data-ttu-id="ae7cf-124">Sélectionnez l’option **afficher les prédictions historiques** pour avoir une idée de la stabilité de la série chronologique.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-124">Select the **Show historic predictions** option to get a sense for the stability of the time series.</span></span>  
  
     <span data-ttu-id="ae7cf-125">![prévisions pour une série unique dans le modèle](media/dm13-forecast-chart-singleseries.gif "prévisions pour une série unique dans le modèle")</span><span class="sxs-lookup"><span data-stu-id="ae7cf-125">![forecasts for a single series in the model](media/dm13-forecast-chart-singleseries.gif "forecasts for a single series in the model")</span></span>  
  
     <span data-ttu-id="ae7cf-126">Les prédictions historiques sont des valeurs prédites en fonction de la série jusqu'à ce point précis, et sont comparées aux valeurs historiques effectives.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-126">Historical predictions are values predicted based on the series to that point, which are compared to actual historical values.</span></span> <span data-ttu-id="ae7cf-127">Si la ligne en pointillé (avec les valeurs prédites) est très éloignée de la ligne continue (les valeurs effectives), cela indique que la première partie de la série ne prédit pas de façon précise les valeurs ultérieures.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-127">If the dotted line (with the predicted values) is far apart from the solid line (the actual values), it means the first part of the series perhaps does not accurately predict the later values.</span></span> <span data-ttu-id="ae7cf-128">Vous avez peut être besoin de plus de données, ou bien cela peut simplement indiquer une volatilité dans le cycle.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-128">You might need more data, or it might simply be an indicator of volatility in the cycle.</span></span>  
  
6.  <span data-ttu-id="ae7cf-129">Sélectionnez l’option **afficher les écarts** pour afficher les barres d’erreur dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-129">Select the **Show Deviations** option to display error bars in the chart.</span></span>  
  
     <span data-ttu-id="ae7cf-130">Les barres d'erreur vous permettent d'évaluer visuellement la variabilité des prédictions.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-130">The error bars let you visually assess the variability of the predictions.</span></span> <span data-ttu-id="ae7cf-131">La qualité des prédictions varie en fonction de vos données sources, mais en augmentant le nombre d'étapes de prédiction, vous devez constater une augmentation stable des déviations.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-131">The quality of predictions varies depending on your source data, but as you increase the number of prediction steps, you should see the deviations steadily increase.</span></span>  
  
 <span data-ttu-id="ae7cf-132">**Conseils**</span><span class="sxs-lookup"><span data-stu-id="ae7cf-132">**Tips**</span></span>  
  
-   <span data-ttu-id="ae7cf-133">Pour activer/désactiver l’affichage de la **légende d’exploration de données**, cliquez avec le bouton droit sur n’importe quel point du graphique.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-133">To toggle display of the **Mining Legend**, right-click any point in the chart.</span></span>  
  
     <span data-ttu-id="ae7cf-134">Vous pouvez afficher une plage de temps spécifique en cliquant sur le graphique, en faisant glisser une plage de temps dans le graphique, puis en recliquant pour effectuer un zoom avant sur la plage sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-134">You can view a specific time range by clicking the chart, dragging a time selection across the chart, and then clicking again to zoom in on the selected range.</span></span>  
  
-   <span data-ttu-id="ae7cf-135">Pour obtenir une copie du graphique actif, cliquez sur **copier dans Excel**, puis cliquez sur une feuille de calcul dans Excel.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-135">To get a copy of the current chart, click **Copy to Excel**, then click a worksheet in Excel.</span></span> <span data-ttu-id="ae7cf-136">Un graphique est inséré sur la feuille avec toutes les options définies, y compris la légende.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-136">A graphic is inserted in the sheet using all the options you had set, including a legend.</span></span>  
  
     <span data-ttu-id="ae7cf-137">Toutefois, ce graphique est statique et vous ne pouvez pas modifier la légende ou afficher les données sous-jacentes ; Si vous avez besoin d’une vue graphique plus interactive, utilisez les [visionneuses Visio](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="ae7cf-137">However, this graphic is static so you cannot edit the legend or view the underlying data; if you need a more interactive chart view, use the [Visio viewers](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span></span>  
  
-   <span data-ttu-id="ae7cf-138">Cliquez sur **ABS** dans la barre de menus de la visionneuse pour basculer entre les courbes absolues et relatives.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-138">Click **Abs** in the viewer menu bar to toggle between absolute and relative curves.</span></span>  
  
     <span data-ttu-id="ae7cf-139">Cette option est utile si votre graphique contient plusieurs modèles, mais l'échelle des données pour chaque modèle est très différente.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-139">This option is useful if your chart contains multiple models, but the scale of the data for each model is very different.</span></span>  
  
     <span data-ttu-id="ae7cf-140">Par exemple, si les boutiques de la région Pacifique sont récentes et les ventes sont faibles, et si les valeurs absolues sont utilisées, la ligne indiquant les ventes Pacifique peut paraître plate, ce qui rend difficile de suivre les changements effectifs par rapport à d'autres modèles pouvant être affichés à une échelle plus normale.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-140">For example, if the Pacific region stores were new and sales were low, and if absolute values are used, the line showing Pacific sales might appear flat, making it difficult to see actual changes, whereas the other models would be displayed at a more normal scale.</span></span>  
  
     <span data-ttu-id="ae7cf-141">En basculant la vue pour utiliser des valeurs relatives, vous normalisez l'échelle des différents modèles et vous affichez les différences en pourcentage des modifications.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-141">By switching the view to use relative values, you can normalize the scale of different models, and display differences as a percent of change.</span></span> <span data-ttu-id="ae7cf-142">Lorsque la modification est relative sur chaque modèle, tous les modèles peuvent être affichés dans le même graphique sans distorsion significative.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-142">When change is relative to each model, they can be displayed in the same graph without significant distortion.</span></span>  
  
 [<span data-ttu-id="ae7cf-143">Explorer le modèle</span><span class="sxs-lookup"><span data-stu-id="ae7cf-143">Explore the Model</span></span>](#bkmk_Top)  
  
###  <a name="model"></a><a name="bkmk_Model"></a><span data-ttu-id="ae7cf-144">Modélisation</span><span class="sxs-lookup"><span data-stu-id="ae7cf-144">Model</span></span>  
 <span data-ttu-id="ae7cf-145">Un modèle de prévision peut également être représenté sous la forme d'un arbre de décision, ou bien, si la série est principalement linéaire, sous la forme d'un modèle de régression.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-145">A forecasting model can also be represented as a decision tree, or, if the series is mostly linear, a regression model.</span></span>  
  
 <span data-ttu-id="ae7cf-146">Par exemple, dans ce modèle il y a une différence dans la formule de régression en fonction d'une certaine condition, par conséquent, l'arbre se ramifie en trois branches, chacune avec une formule de régression différente.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-146">For example, in this model, there is a difference in the regression formula based on a certain condition, so the tree splits into two branches, each with a different regression formula.</span></span>  
  
 <span data-ttu-id="ae7cf-147">![Filtrer une série unique dans le modèle de prévision](media/dm13-forecast-model-northamerica.gif "Filtrer une série unique dans le modèle de prévision")</span><span class="sxs-lookup"><span data-stu-id="ae7cf-147">![Filter single series in the forecasting model](media/dm13-forecast-model-northamerica.gif "Filter single series in the forecasting model")</span></span>  
  
##### <a name="explore-the-forecasting-model-as-a-tree"></a><span data-ttu-id="ae7cf-148">Explorer le modèle de prévision sous forme d'arborescence</span><span class="sxs-lookup"><span data-stu-id="ae7cf-148">Explore the forecasting model as a tree</span></span>  
  
1.  <span data-ttu-id="ae7cf-149">Cliquez sur la liste déroulante **arborescence** et choisissez un modèle à afficher.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-149">Click the **Tree** dropdown list and choose a model to display.</span></span>  
  
     <span data-ttu-id="ae7cf-150">Un arbre distinct ou un nœud de régression est affiché pour chaque attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-150">A separate tree or regression node is displayed for each predictable attribute.</span></span> <span data-ttu-id="ae7cf-151">Par exemple, si vos données comprennent les ventes pour l'Europe, l'Amérique du Nord et le Pacifique, il y aura trois modèles différents, un pour chaque série de données.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-151">For example, if your data contains sales for Europe, North America, and the Pacific, there would three different models, one for each data series.</span></span>  
  
2.  <span data-ttu-id="ae7cf-152">Faites glisser le curseur **afficher le niveau** pour filtrer les niveaux inférieurs de l’arborescence et concentrez-vous sur les fractionnements les plus importants.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-152">Drag the **Show Level** slider to filter out lower levels of the tree, and focus on the most important splits.</span></span>  
  
3.  <span data-ttu-id="ae7cf-153">Cliquez sur chaque nœud pour afficher des statistiques descriptives dans la **légende d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-153">Click each node to view some descriptive statistics in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="ae7cf-154">Lorsque vous immobilisez la souris sur un nœud, une info-bulle affiche également les mêmes statistiques, ainsi que la formule complète décrivant le nœud.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-154">As you pause over a node with the mouse, a ToolTip also displays the same statistics, as well as the full formula describing that node.</span></span>  
  
4.  <span data-ttu-id="ae7cf-155">Si vous souhaitez copier les informations dans la **légende d’exploration**de données, cliquez avec le bouton droit sur la **légende d’exploration**de données, sélectionnez **copier**, puis cliquez à l’intérieur de votre feuille de calcul Excel.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-155">If you want to copy the information in the **Mining Legend**, right-click the **Mining Legend**, select **Copy**, and click inside your Excel worksheet.</span></span> <span data-ttu-id="ae7cf-156">L’option **copier dans Excel** copie le graphique, pas les statistiques.</span><span class="sxs-lookup"><span data-stu-id="ae7cf-156">The **Copy to Excel** option copies the graph, not the statistics.</span></span>  
  
 [<span data-ttu-id="ae7cf-157">Explorer le modèle</span><span class="sxs-lookup"><span data-stu-id="ae7cf-157">Explore the Model</span></span>](#bkmk_Top)  
  
## <a name="see-also"></a><span data-ttu-id="ae7cf-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae7cf-158">See Also</span></span>  
 [<span data-ttu-id="ae7cf-159">Exploration des modèles dans Excel &#40;SQL Server les compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="ae7cf-159">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
