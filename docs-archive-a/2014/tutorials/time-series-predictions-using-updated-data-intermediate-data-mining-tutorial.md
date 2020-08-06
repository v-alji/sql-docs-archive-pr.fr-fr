---
title: Prédictions de séries chronologiques utilisant des données mises à jour (Didacticiel intermédiaire sur l’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af73681d-ce1c-4b6e-b195-6df3d2fb5275
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2017defaba74071b1a12bee14a5d8907e4c71cda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600374"
---
# <a name="time-series-predictions-using-updated-data-intermediate-data-mining-tutorial"></a><span data-ttu-id="0cbe4-102">Prédictions de série chronologique à l'aide des données mises à jour (Didacticiel intermédiaire sur l'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="0cbe4-102">Time Series Predictions using Updated Data (Intermediate Data Mining Tutorial)</span></span>
    
## <a name="creating-predictions-using-the-extended-sales-data"></a><span data-ttu-id="0cbe4-103">Création de prédictions à l'aide des données de ventes étendues</span><span class="sxs-lookup"><span data-stu-id="0cbe4-103">Creating Predictions using the Extended Sales Data</span></span>  
 <span data-ttu-id="0cbe4-104">Dans cette leçon, vous allez créer une requête de prédiction qui ajoute les nouvelles données de ventes au modèle.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-104">In this lesson, you will create a prediction query that adds the new sales data to the model.</span></span> <span data-ttu-id="0cbe4-105">En étendant le modèle avec de nouvelles données, vous pouvez obtenir des prédictions à jour qui comprennent les points de données les plus récents.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-105">By extending the model with new data, you can get up-to-date predictions that include the newest data points.</span></span>  
  
 <span data-ttu-id="0cbe4-106">La création de prédictions de série chronologique qui utilisent de nouvelles données est simple : vous ajoutez simplement le paramètre EXTEND_MODEL_CASES à la fonction [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) , spécifiez la source des nouvelles données et spécifiez le nombre de prédictions que vous souhaitez obtenir.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-106">Creating time series predictions that use new data is easy: you simply add the parameter EXTEND_MODEL_CASES to the [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) function, specify the source of the new data, and specify how many predictions you want to get.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0cbe4-107">Le paramètre EXTEND_MODEL_CASES est facultatif ; par défaut le modèle est étendu à chaque fois que vous créez une requête de prédiction de série chronologique en joignant de nouvelles données comme entrées.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-107">The parameter EXTEND_MODEL_CASES is optional; by default the model is extended any time that you create a time series prediction query by joining new data as inputs.</span></span>  
  
#### <a name="to-build-the-prediction-query-and-add-new-data"></a><span data-ttu-id="0cbe4-108">Pour générer la requête de prédiction et ajouter de nouvelles données</span><span class="sxs-lookup"><span data-stu-id="0cbe4-108">To build the prediction query and add new data</span></span>  
  
1.  <span data-ttu-id="0cbe4-109">Si le modèle n’est pas déjà ouvert, double-cliquez sur la structure de prévision et, dans le concepteur d’exploration de données, cliquez sur l’onglet **prédiction de modèle d’exploration** de données.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-109">If the model is not already open, double-click the Forecasting structure, and in Data Mining Designer, click the **Mining Model Prediction** tab.</span></span>  
  
2.  <span data-ttu-id="0cbe4-110">Dans le volet **modèle d’exploration de données** , la prévision de modèle doit déjà être sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-110">In the **Mining Model** pane, the model Forecasting should already be selected.</span></span> <span data-ttu-id="0cbe4-111">Si ce n’est pas le cas, cliquez sur **Sélectionner un modèle**, puis sélectionnez le modèle prévision.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-111">If it is not selected, click **Select Model**, and then select the model, Forecasting.</span></span>  
  
3.  <span data-ttu-id="0cbe4-112">Dans le volet **Sélectionner une ou plusieurs tables d’entrée** , cliquez sur **Sélectionner la table de cas**.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-112">In the **Select Input Table(s)** pane, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="0cbe4-113">Dans la boîte de dialogue **Sélectionner une table** , sélectionnez la source de données, [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cbe4-113">In the **Select Table** dialog box, select the data source, [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
     <span data-ttu-id="0cbe4-114">Dans la liste des vues de source de données, sélectionnez NewSalesData, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-114">From the list of data source views, select NewSalesData and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="0cbe4-115">Cliquez avec le bouton droit sur la surface de la zone de conception, puis sélectionnez **modifier les connexions**.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-115">Right-click the surface of the design area and select **Modify Connections**.</span></span>  
  
6.  <span data-ttu-id="0cbe4-116">À l’aide de la boîte de dialogue **modifier le mappage** , mappez les colonnes du modèle aux colonnes des données externes comme suit :</span><span class="sxs-lookup"><span data-stu-id="0cbe4-116">Using the **Modify Mapping** dialog box, map the columns in the model to the columns in the external data as follows:</span></span>  
  
    -   <span data-ttu-id="0cbe4-117">Mappez la colonne ReportingDate dans le modèle d’exploration de données à la colonne NewDate dans les données d’entrée.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-117">Map the ReportingDate column in the mining model to the NewDate column in the input data.</span></span>  
  
    -   <span data-ttu-id="0cbe4-118">Mappez la colonne Amount du modèle d’exploration de données à la colonne NewAmount dans les données d’entrée.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-118">Map the Amount column in the mining model to the NewAmount column in the input data.</span></span>  
  
    -   <span data-ttu-id="0cbe4-119">Mappez la colonne Quantity du modèle d’exploration de données à la colonne NewQty dans les données d’entrée.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-119">Map the Quantity column in the mining model to the NewQty column in the input data.</span></span>  
  
    -   <span data-ttu-id="0cbe4-120">Mappez la colonne ModelRegion dans le modèle d’exploration de données à la colonne de série dans les données d’entrée.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-120">Map the ModelRegion column in the mining model to the Series column in the input data.</span></span>  
  
7.  <span data-ttu-id="0cbe4-121">Vous allez maintenant générer la requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-121">Now you will build the prediction query.</span></span>  
  
     <span data-ttu-id="0cbe4-122">D'abord, ajoutez une colonne à la requête de prédiction pour générer la sortie de la série à laquelle la prédiction s'applique.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-122">First, add a column to the prediction query to output the series the prediction applies to.</span></span>  
  
    1.  <span data-ttu-id="0cbe4-123">Dans la grille, cliquez sur la première ligne vide, sous **source**, puis sélectionnez prévision.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-123">In the grid, click the first empty row, under **Source**, and then select Forecasting.</span></span>  
  
    2.  <span data-ttu-id="0cbe4-124">Dans la colonne **champ** , sélectionnez région du modèle et pour **alias**, tapez `Model Region` .</span><span class="sxs-lookup"><span data-stu-id="0cbe4-124">In the **Field** column, select Model Region and for **Alias**, type `Model Region`.</span></span>  
  
8.  <span data-ttu-id="0cbe4-125">Ensuite, ajoutez et modifiez la fonction de prédiction.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-125">Next, add and edit the prediction function.</span></span>  
  
    1.  <span data-ttu-id="0cbe4-126">Cliquez sur une ligne vide, et sous **source**, sélectionnez **fonction de prédiction**.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-126">Click an empty row, and under **Source**, select **Prediction Function**.</span></span>  
  
    2.  <span data-ttu-id="0cbe4-127">Pour **champ**, sélectionnez **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-127">For **Field**, select **PredictTimeSeries**.</span></span>  
  
    3.  <span data-ttu-id="0cbe4-128">Pour **alias**, tapez **valeurs prédites**.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-128">For **Alias**, type **Predicted Values**.</span></span>  
  
    4.  <span data-ttu-id="0cbe4-129">Faites glisser le champ Quantity du volet **modèle d’exploration de données** vers la colonne **Criteria/argument** .</span><span class="sxs-lookup"><span data-stu-id="0cbe4-129">Drag the field Quantity from the **Mining Model** pane into the **Criteria/Argument** column.</span></span>  
  
    5.  <span data-ttu-id="0cbe4-130">Dans la colonne **critères/argument** , après le nom du champ, tapez le texte suivant : **5, EXTEND_MODEL_CASES**</span><span class="sxs-lookup"><span data-stu-id="0cbe4-130">In the **Criteria/Argument** column, after the field name, type the following text:  **5,EXTEND_MODEL_CASES**</span></span>  
  
         <span data-ttu-id="0cbe4-131">Le texte complet de la zone de texte **critères/argument** doit se présenter comme suit :`[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span><span class="sxs-lookup"><span data-stu-id="0cbe4-131">The complete text of the **Criteria/Argument** text box should be as follows: `[Forecasting].[Quantity],5,EXTEND_MODEL_CASES`</span></span>  
  
9. <span data-ttu-id="0cbe4-132">Cliquez sur **résultats** et passez en revue les résultats.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-132">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="0cbe4-133">Les prédictions commencent en juillet (première tranche de temps après la fin des données d'origine) et se terminent dans en novembre (cinquième tranche de temps après la fin des données d'origine).</span><span class="sxs-lookup"><span data-stu-id="0cbe4-133">The predictions begin in July (the first time slice after the end of the original data) and end at November (the fifth time slice after the end of the original data).</span></span>  
  
 <span data-ttu-id="0cbe4-134">Vous pouvez voir que, pour utiliser ce type de requête de prédiction efficacement, vous devez savoir quand les anciennes données se terminent, ainsi que le nombre de tranches de temps présentes dans les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-134">You can see that to use this type of prediction query effectively, you need to know when the old data ends, as well as how many time slices there are in the new data.</span></span>  
  
 <span data-ttu-id="0cbe4-135">Par exemple, dans ce modèle, la série de données d'origine s'est terminée en juin et les données correspondent aux mois de juillet, août et septembre.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-135">For example, in this model, the original data series ended in June, and the data is for the months of July, August, and September.</span></span>  
  
 <span data-ttu-id="0cbe4-136">Les prédictions qui utilisent EXTEND_MODEL_CASES commencent toujours à la fin de la série de données d'origine.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-136">Predictions that use EXTEND_MODEL_CASES always begin at the end of the original data series.</span></span> <span data-ttu-id="0cbe4-137">Par conséquent, si vous souhaitez obtenir uniquement les prédictions pour les mois inconnus, vous devez spécifier le point de départ et le point d'arrêt de la prédiction.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-137">Therefore, if you want to get only the predictions for the unknown months, you need to specify the starting point and the end point for prediction.</span></span> <span data-ttu-id="0cbe4-138">Les deux valeurs sont spécifiées sous la forme d'un nombre de tranches de temps, en commençant par la fin des anciennes données.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-138">Both values are specified as a number of time slices starting at the end of the old data.</span></span>  
  
 <span data-ttu-id="0cbe4-139">La procédure suivante montre comment procéder.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-139">The following procedure demonstrates how to do this.</span></span>  
  
### <a name="change-the-start-and-end-points-of-the-predictions"></a><span data-ttu-id="0cbe4-140">Modifiez les points de départ et de fin des prédictions</span><span class="sxs-lookup"><span data-stu-id="0cbe4-140">Change the start and end points of the predictions</span></span>  
  
1.  <span data-ttu-id="0cbe4-141">Dans Générateur de requêtes de prédiction, cliquez sur **requête** pour basculer vers la vue DMX.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-141">In Prediction Query Builder, click **Query** to switch to DMX view.</span></span>  
  
2.  <span data-ttu-id="0cbe4-142">Localisez l'instruction DMX qui contient la fonction PredictTimeSeries et modifiez-la comme suit :</span><span class="sxs-lookup"><span data-stu-id="0cbe4-142">Locate the DMX statement that contains the PredictTimeSeries function and change it as follows:</span></span>  
  
     `PredictTimeSeries([Forecasting 12].[Quantity],4,6,EXTEND_MODEL_CASES)`  
  
3.  <span data-ttu-id="0cbe4-143">Cliquez sur **résultats** et passez en revue les résultats.</span><span class="sxs-lookup"><span data-stu-id="0cbe4-143">Click **Results** and review the results.</span></span>  
  
     <span data-ttu-id="0cbe4-144">À présent, les prédictions commencent en octobre (quatrième tranche de temps en partant de la fin des données d'origine) et se terminent en décembre (sixième tranche de temps en partant de la fin des données d'origine).</span><span class="sxs-lookup"><span data-stu-id="0cbe4-144">Now the predictions begin at October (the fourth time slice, counting from the end of the original data) and end at December (the sixth time slice, counting from the end of the original data).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0cbe4-145">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="0cbe4-145">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0cbe4-146">Prédictions de série chronologique utilisant des données de remplacement &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="0cbe4-146">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="0cbe4-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0cbe4-147">See Also</span></span>  
 <span data-ttu-id="0cbe4-148">[Référence technique de l’algorithme MTS (Microsoft Time Series)](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0cbe4-148">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="0cbe4-149">Contenu du modèle d’exploration de données pour les modèles de séries chronologiques &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="0cbe4-149">Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md)  
  
  
