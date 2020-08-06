---
title: Création de prédictions de série chronologique (didacticiel sur l’exploration de données intermédiaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: fb22cffa-ac99-4d34-ac4a-9c93068e33e8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1175cdffd1512e0cb876b9565dd0727a9f094c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602693"
---
# <a name="creating-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="0065e-102">Création de prédictions de série chronologique (Didacticiel intermédiaire sur l'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="0065e-102">Creating Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="0065e-103">Dans les tâches précédentes de cette leçon, vous avez créé un modèle de série chronologique et exploré les résultats.</span><span class="sxs-lookup"><span data-stu-id="0065e-103">In the previous tasks in this lesson, you created a time series model and explored the results.</span></span> <span data-ttu-id="0065e-104">Par défaut, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] crée toujours un jeu de cinq (5) prédictions pour un modèle de série chronologique et affiche les valeurs prédites dans le graphique de prévision.</span><span class="sxs-lookup"><span data-stu-id="0065e-104">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] always creates a set of five (5) predictions for a time series model and displays the predicted values as part of the forecasting chart.</span></span> <span data-ttu-id="0065e-105">Toutefois, vous pouvez également créer des prévisions en générant des requêtes de prédiction DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="0065e-105">However, you can also create forecasts by building Data Mining Extensions (DMX) prediction queries.</span></span>  
  
 <span data-ttu-id="0065e-106">Dans cette tâche, vous allez créer une requête de prédiction qui génère les mêmes prédictions que celles affichées dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="0065e-106">In this task, you will create a prediction query that generates the same predictions that you saw in the viewer.</span></span> <span data-ttu-id="0065e-107">Cette tâche suppose que vous avez déjà suivi les leçons du didacticiel sur l'exploration de données de base et que vous savez utiliser le Générateur de requêtes de prédiction.</span><span class="sxs-lookup"><span data-stu-id="0065e-107">This task assumes that you have already completed the lessons in the Basic Data Mining Tutorial and are familiar with how to use Prediction Query Builder.</span></span> <span data-ttu-id="0065e-108">Vous allez maintenant apprendre à créer des requêtes spécifiques aux modèles de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="0065e-108">You will now learn how to create queries specific to time series models.</span></span>  
  
## <a name="creating-time-series-predictions"></a><span data-ttu-id="0065e-109">Création de prédictions de séries chronologiques</span><span class="sxs-lookup"><span data-stu-id="0065e-109">Creating Time Series Predictions</span></span>  
 <span data-ttu-id="0065e-110">La première étape dans la création d'une requête de prédiction consiste généralement à sélectionner un modèle d'exploration de données et une table d'entrée.</span><span class="sxs-lookup"><span data-stu-id="0065e-110">Typically, the first step in creating a prediction query is to select a mining model and input table.</span></span> <span data-ttu-id="0065e-111">Toutefois, un modèle de série chronologique ne nécessite pas d'entrée supplémentaire pour une prédiction normale.</span><span class="sxs-lookup"><span data-stu-id="0065e-111">However, a time series model does not require additional input for a regular prediction.</span></span> <span data-ttu-id="0065e-112">Par conséquent, vous n'avez pas besoin de spécifier une nouvelle source de données pour faire des prédictions, sauf si vous ajoutez des données au modèle ou en remplacez.</span><span class="sxs-lookup"><span data-stu-id="0065e-112">Therefore, you do not need to specify a new source of data when making predictions, unless you are adding data to the model or replacing the data.</span></span>  
  
 <span data-ttu-id="0065e-113">Pour cette leçon, vous devez spécifier le nombre d'étapes de prédiction.</span><span class="sxs-lookup"><span data-stu-id="0065e-113">For this lesson, you must specify the number of prediction steps.</span></span> <span data-ttu-id="0065e-114">Vous pouvez spécifier le nom de la série pour obtenir une prédiction d'une combinaison particulière d'un produit et d'une région.</span><span class="sxs-lookup"><span data-stu-id="0065e-114">You can specify the series name, to get a prediction for a particular combination of a product and a region.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="0065e-115">Pour sélectionner un modèle et une table d'entrée</span><span class="sxs-lookup"><span data-stu-id="0065e-115">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="0065e-116">Sous l’onglet **prédiction de modèle d’exploration** de données du concepteur d’exploration de données, dans la zone modèle d' **exploration** de données, cliquez sur **Sélectionner un modèle**.</span><span class="sxs-lookup"><span data-stu-id="0065e-116">On the **Mining Model Prediction** tab of the Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="0065e-117">Dans la boîte de dialogue **Sélectionner le modèle d’exploration de données** , développez la structure prévision, sélectionnez le modèle **prévision** dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0065e-117">In the **Select Mining Model** dialog box, expand the Forecasting structure, select the **Forecasting** model from the list, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="0065e-118">Ignorer la zone **Sélectionner une ou plusieurs tables d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="0065e-118">Ignore the **Select Input Table(s)** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0065e-119">Pour un modèle de série chronologique, vous n'avez pas besoin de spécifier une entrée séparée sauf si vous faites de la prédiction croisée.</span><span class="sxs-lookup"><span data-stu-id="0065e-119">For a time series model, you do not need to specify a separate input unless you are doing cross-prediction.</span></span>  
  
4.  <span data-ttu-id="0065e-120">Dans la colonne **source** , dans la grille de l’onglet **prédiction de modèle d’exploration de données** , cliquez sur la cellule de la première ligne vide, puis sélectionnez **prévision modèle d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="0065e-120">In the **Source** column, in the grid on the **Mining Model Prediction** tab, click the cell in the first empty row, and then select **Forecasting mining model**.</span></span>  
  
5.  <span data-ttu-id="0065e-121">Dans la colonne **champ** , sélectionnez **région du modèle**.</span><span class="sxs-lookup"><span data-stu-id="0065e-121">In the **Field** column, select **Model Region**.</span></span>  
  
     <span data-ttu-id="0065e-122">Cette action ajoute l'identificateur de série à la requête de prédiction pour indiquer la combinaison de modèle et de région à laquelle la prédiction s'applique.</span><span class="sxs-lookup"><span data-stu-id="0065e-122">This action adds the series identifier to the prediction query to indicate the combination of model and region to which the prediction applies.</span></span>  
  
6.  <span data-ttu-id="0065e-123">Cliquez sur la ligne vide suivante dans la colonne **source** , puis sélectionnez **fonction de prédiction**.</span><span class="sxs-lookup"><span data-stu-id="0065e-123">Click the next empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
7.  <span data-ttu-id="0065e-124">Dans la colonne **champ** , sélectionnez **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="0065e-124">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0065e-125">Vous pouvez utiliser également la fonction `Predict` avec des modèles de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="0065e-125">You can also use the `Predict` function with time series models.</span></span> <span data-ttu-id="0065e-126">Toutefois, par défaut, la fonction Predict crée une seule prédiction pour chaque série.</span><span class="sxs-lookup"><span data-stu-id="0065e-126">However, by default, the Predict function creates only one prediction for each series.</span></span> <span data-ttu-id="0065e-127">Par conséquent, pour spécifier plusieurs étapes de prédiction, vous devez utiliser la fonction **PredictTimeSeries** .</span><span class="sxs-lookup"><span data-stu-id="0065e-127">Therefore, to specify multiple prediction steps, you must use the **PredictTimeSeries** function.</span></span>  
  
8.  <span data-ttu-id="0065e-128">Dans le volet **modèle d’exploration de données** , sélectionnez la colonne modèle d’exploration de données, **amount.**</span><span class="sxs-lookup"><span data-stu-id="0065e-128">In the **Mining Model** pane, select the mining model column, **Amount.**</span></span> <span data-ttu-id="0065e-129">Faites glisser amount vers la zone **critères/arguments** pour la fonction **PredictTimeSeries** que vous avez ajoutée précédemment.</span><span class="sxs-lookup"><span data-stu-id="0065e-129">Drag Amount to the **Criteria/Arguments** box for the **PredictTimeSeries** function that you added earlier.</span></span>  
  
9. <span data-ttu-id="0065e-130">Cliquez sur la zone **critères/arguments** , puis tapez une virgule, suivie de **5**, après le nom du champ.</span><span class="sxs-lookup"><span data-stu-id="0065e-130">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="0065e-131">Le texte de la zone **critères/arguments** doit maintenant afficher les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="0065e-131">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[Amount],5`  
  
10. <span data-ttu-id="0065e-132">Dans la colonne **alias** , tapez `PredictAmount` .</span><span class="sxs-lookup"><span data-stu-id="0065e-132">In the **Alias** column, type `PredictAmount`.</span></span>  
  
11. <span data-ttu-id="0065e-133">Cliquez sur la ligne vide suivante dans la colonne **source** , puis sélectionnez à nouveau **fonction de prédiction** .</span><span class="sxs-lookup"><span data-stu-id="0065e-133">Click the next empty row in the **Source** column, and then select **Prediction Function** again.</span></span>  
  
12. <span data-ttu-id="0065e-134">Dans la colonne **champ** , sélectionnez **PredictTimeSeries**.</span><span class="sxs-lookup"><span data-stu-id="0065e-134">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
13. <span data-ttu-id="0065e-135">Dans le volet **modèle d’exploration de données** , sélectionnez la colonne Quantity, puis faites-la glisser dans la zone **critères/arguments** pour la deuxième fonction **PredictTimeSeries** .</span><span class="sxs-lookup"><span data-stu-id="0065e-135">In the **Mining Model** pane, select the column Quantity, and then drag it into the **Criteria/Arguments** box for the second **PredictTimeSeries** function.</span></span>  
  
14. <span data-ttu-id="0065e-136">Cliquez sur la zone **critères/arguments** , puis tapez une virgule, suivie de **5**, après le nom du champ.</span><span class="sxs-lookup"><span data-stu-id="0065e-136">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="0065e-137">Le texte de la zone **critères/arguments** doit maintenant afficher les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="0065e-137">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[ Quantity],5`  
  
15. <span data-ttu-id="0065e-138">Dans la colonne **alias** , tapez `PredictQuantity` .</span><span class="sxs-lookup"><span data-stu-id="0065e-138">In the **Alias** column, type `PredictQuantity`.</span></span>  
  
16. <span data-ttu-id="0065e-139">Cliquez sur **basculer vers l’affichage des résultats de la requête**.</span><span class="sxs-lookup"><span data-stu-id="0065e-139">Click **Switch to query result view**.</span></span>  
  
     <span data-ttu-id="0065e-140">Les résultats de la requête sont affichés sous forme de tableau.</span><span class="sxs-lookup"><span data-stu-id="0065e-140">The results of the query are displayed in tabular format.</span></span>  
  
 <span data-ttu-id="0065e-141">N'oubliez pas que vous avez créé trois types différents de résultats dans le générateur de requête, un type qui utilise des valeurs d'une colonne, et deux autres types qui reçoivent des valeurs prédites d'une fonction de prédiction.</span><span class="sxs-lookup"><span data-stu-id="0065e-141">Remember that you created three different types of results in the query builder, one that uses values from a column, and two that get predicted values from a prediction function.</span></span> <span data-ttu-id="0065e-142">Par conséquent, les résultats de la requête contiennent trois colonnes séparées.</span><span class="sxs-lookup"><span data-stu-id="0065e-142">Therefore, the results of the query contain three separate columns.</span></span> <span data-ttu-id="0065e-143">La première colonne contient la liste des combinaisons de produit et de région.</span><span class="sxs-lookup"><span data-stu-id="0065e-143">The first column contains the list of product and region combinations.</span></span> <span data-ttu-id="0065e-144">Les deuxième et troisième colonnes contiennent chacune une table imbriquée de résultats de prédiction.</span><span class="sxs-lookup"><span data-stu-id="0065e-144">The second and third columns each contain a nested table of prediction results.</span></span> <span data-ttu-id="0065e-145">Chaque table imbriquée contient les valeurs prédites et d'étape, comme dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="0065e-145">Each nested table contains the time step and predicted values, such as the following table:</span></span>  
  
 <span data-ttu-id="0065e-146">Exemples de résultats (les montants sont tronqués à deux décimales) :</span><span class="sxs-lookup"><span data-stu-id="0065e-146">Example results (amounts are truncated to two decimal places):</span></span>  
  
 <span data-ttu-id="0065e-147">**M200 Europe PredictAmount**</span><span class="sxs-lookup"><span data-stu-id="0065e-147">**M200 Europe PredictAmount**</span></span>  
  
|<span data-ttu-id="0065e-148">$TIME</span><span class="sxs-lookup"><span data-stu-id="0065e-148">$TIME</span></span>|<span data-ttu-id="0065e-149">Montant</span><span class="sxs-lookup"><span data-stu-id="0065e-149">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="0065e-150">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-150">7/25/2008</span></span>|<span data-ttu-id="0065e-151">99978,00</span><span class="sxs-lookup"><span data-stu-id="0065e-151">99978.00</span></span>|  
|<span data-ttu-id="0065e-152">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-152">8/25/2008</span></span>|<span data-ttu-id="0065e-153">145575,07</span><span class="sxs-lookup"><span data-stu-id="0065e-153">145575.07</span></span>|  
|<span data-ttu-id="0065e-154">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-154">9/25/2008</span></span>|<span data-ttu-id="0065e-155">116835,19</span><span class="sxs-lookup"><span data-stu-id="0065e-155">116835.19</span></span>|  
|<span data-ttu-id="0065e-156">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-156">10/25/2008</span></span>|<span data-ttu-id="0065e-157">116537,38</span><span class="sxs-lookup"><span data-stu-id="0065e-157">116537.38</span></span>|  
|<span data-ttu-id="0065e-158">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-158">11/25/2008</span></span>|<span data-ttu-id="0065e-159">107760,55</span><span class="sxs-lookup"><span data-stu-id="0065e-159">107760.55</span></span>|  
  
 <span data-ttu-id="0065e-160">**M200 Europe PredictQuantity**</span><span class="sxs-lookup"><span data-stu-id="0065e-160">**M200 Europe PredictQuantity**</span></span>  
  
|<span data-ttu-id="0065e-161">$TIME</span><span class="sxs-lookup"><span data-stu-id="0065e-161">$TIME</span></span>|<span data-ttu-id="0065e-162">Quantité</span><span class="sxs-lookup"><span data-stu-id="0065e-162">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="0065e-163">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-163">7/25/2008</span></span>|<span data-ttu-id="0065e-164">52</span><span class="sxs-lookup"><span data-stu-id="0065e-164">52</span></span>|  
|<span data-ttu-id="0065e-165">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-165">8/25/2008</span></span>|<span data-ttu-id="0065e-166">67</span><span class="sxs-lookup"><span data-stu-id="0065e-166">67</span></span>|  
|<span data-ttu-id="0065e-167">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-167">9/25/2008</span></span>|<span data-ttu-id="0065e-168">58</span><span class="sxs-lookup"><span data-stu-id="0065e-168">58</span></span>|  
|<span data-ttu-id="0065e-169">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-169">10/25/2008</span></span>|<span data-ttu-id="0065e-170">57</span><span class="sxs-lookup"><span data-stu-id="0065e-170">57</span></span>|  
|<span data-ttu-id="0065e-171">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-171">11/25/2008</span></span>|<span data-ttu-id="0065e-172">54</span><span class="sxs-lookup"><span data-stu-id="0065e-172">54</span></span>|  
  
 <span data-ttu-id="0065e-173">**M200 Amérique du Nord-PredictAmount**</span><span class="sxs-lookup"><span data-stu-id="0065e-173">**M200 North America - PredictAmount**</span></span>  
  
|<span data-ttu-id="0065e-174">$TIME</span><span class="sxs-lookup"><span data-stu-id="0065e-174">$TIME</span></span>|<span data-ttu-id="0065e-175">Montant</span><span class="sxs-lookup"><span data-stu-id="0065e-175">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="0065e-176">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-176">7/25/2008</span></span>|<span data-ttu-id="0065e-177">348533,93</span><span class="sxs-lookup"><span data-stu-id="0065e-177">348533.93</span></span>|  
|<span data-ttu-id="0065e-178">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-178">8/25/2008</span></span>|<span data-ttu-id="0065e-179">340097,98</span><span class="sxs-lookup"><span data-stu-id="0065e-179">340097.98</span></span>|  
|<span data-ttu-id="0065e-180">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-180">9/25/2008</span></span>|<span data-ttu-id="0065e-181">257986,19</span><span class="sxs-lookup"><span data-stu-id="0065e-181">257986.19</span></span>|  
|<span data-ttu-id="0065e-182">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-182">10/25/2008</span></span>|<span data-ttu-id="0065e-183">374658,24</span><span class="sxs-lookup"><span data-stu-id="0065e-183">374658.24</span></span>|  
|<span data-ttu-id="0065e-184">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-184">11/25/2008</span></span>|<span data-ttu-id="0065e-185">379241,44</span><span class="sxs-lookup"><span data-stu-id="0065e-185">379241.44</span></span>|  
  
 <span data-ttu-id="0065e-186">**M200 Amérique du Nord-PredictQuantity**</span><span class="sxs-lookup"><span data-stu-id="0065e-186">**M200 North America - PredictQuantity**</span></span>  
  
|<span data-ttu-id="0065e-187">$TIME</span><span class="sxs-lookup"><span data-stu-id="0065e-187">$TIME</span></span>|<span data-ttu-id="0065e-188">Quantité</span><span class="sxs-lookup"><span data-stu-id="0065e-188">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="0065e-189">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-189">7/25/2008</span></span>|<span data-ttu-id="0065e-190">272</span><span class="sxs-lookup"><span data-stu-id="0065e-190">272</span></span>|  
|<span data-ttu-id="0065e-191">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-191">8/25/2008</span></span>|<span data-ttu-id="0065e-192">152</span><span class="sxs-lookup"><span data-stu-id="0065e-192">152</span></span>|  
|<span data-ttu-id="0065e-193">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-193">9/25/2008</span></span>|<span data-ttu-id="0065e-194">250</span><span class="sxs-lookup"><span data-stu-id="0065e-194">250</span></span>|  
|<span data-ttu-id="0065e-195">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-195">10/25/2008</span></span>|<span data-ttu-id="0065e-196">181</span><span class="sxs-lookup"><span data-stu-id="0065e-196">181</span></span>|  
|<span data-ttu-id="0065e-197">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="0065e-197">11/25/2008</span></span>|<span data-ttu-id="0065e-198">290</span><span class="sxs-lookup"><span data-stu-id="0065e-198">290</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="0065e-199">Les dates utilisées dans l'exemple de base de données ont changé pour cette version.</span><span class="sxs-lookup"><span data-stu-id="0065e-199">The dates that are used in the sample database have changed for this release.</span></span> <span data-ttu-id="0065e-200">Si vous utilisez une version antérieure des exemples de données, vous pouvez obtenir des résultats différents.</span><span class="sxs-lookup"><span data-stu-id="0065e-200">If you are using an earlier version of the sample data, you might see different results.</span></span>  
  
## <a name="saving-the-prediction-results"></a><span data-ttu-id="0065e-201">Enregistrement des résultats de prédiction</span><span class="sxs-lookup"><span data-stu-id="0065e-201">Saving the Prediction Results</span></span>  
 <span data-ttu-id="0065e-202">Différentes options s'offrent à vous pour l'utilisation des résultats de prédiction.</span><span class="sxs-lookup"><span data-stu-id="0065e-202">You have several different options for using the prediction results.</span></span> <span data-ttu-id="0065e-203">Vous pouvez aplatir les résultats, copier les données de la vue Résultats et les coller dans une feuille de calcul Excel ou un autre fichier.</span><span class="sxs-lookup"><span data-stu-id="0065e-203">You can flatten the results, copy the data from the Results view, and paste it into an Excel worksheet or other file.</span></span>  
  
 <span data-ttu-id="0065e-204">Pour simplifier le processus d'enregistrement des résultats, le Concepteur d'exploration de données fournit également la possibilité d'enregistrer les données dans une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="0065e-204">To simplify the process of saving results, Data Mining Designer also provides the ability to save the data to a data source view.</span></span> <span data-ttu-id="0065e-205">La fonctionnalité d'enregistrement des résultats dans une vue de source de données est disponible uniquement dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0065e-205">The functionality for saving results to a data source view is available only in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="0065e-206">Les résultats peuvent être stockées uniquement dans un format à plat.</span><span class="sxs-lookup"><span data-stu-id="0065e-206">The results can only be stored in a flattened format.</span></span>  
  
#### <a name="to-flatten-the-results-in-the-results-pane"></a><span data-ttu-id="0065e-207">Pour aplatir les résultats dans le volet Résultats</span><span class="sxs-lookup"><span data-stu-id="0065e-207">To flatten the results in the Results pane</span></span>  
  
1.  <span data-ttu-id="0065e-208">Dans la Générateur de requêtes de prédiction, cliquez sur **basculer en mode création de requête**.</span><span class="sxs-lookup"><span data-stu-id="0065e-208">In the Prediction Query Builder, click **Switch to query design view**.</span></span>  
  
     <span data-ttu-id="0065e-209">La vue se modifie pour autoriser l'édition manuelle du texte de la requête DMX.</span><span class="sxs-lookup"><span data-stu-id="0065e-209">The view changes to allow manual editing of the DMX query text.</span></span>  
  
2.  <span data-ttu-id="0065e-210">Tapez le mot clé `FLATTENED` après le mot clé `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="0065e-210">Type the `FLATTENED` keyword after the `SELECT` keyword.</span></span> <span data-ttu-id="0065e-211">Le texte de la requête tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="0065e-211">The complete query text should be as follows:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    ```  
  
3.  <span data-ttu-id="0065e-212">Éventuellement, vous pouvez taper une clause pour restreindre les résultats, comme l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="0065e-212">Optionally, you can type a clause to restrict the results, such as the following example:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    WHERE [Forecasting].[Model Region] = 'M200 North America'   
    OR [Forecasting].[Model Region] = 'M200 Europe'  
  
    ```  
  
4.  <span data-ttu-id="0065e-213">Cliquez sur **basculer vers l’affichage des résultats de la requête**.</span><span class="sxs-lookup"><span data-stu-id="0065e-213">Click **Switch to query result view**.</span></span>  
  
#### <a name="to-export-prediction-query-results"></a><span data-ttu-id="0065e-214">Pour exporter des résultats d'une requête de prédiction</span><span class="sxs-lookup"><span data-stu-id="0065e-214">To export prediction query results</span></span>  
  
1.  <span data-ttu-id="0065e-215">Cliquez sur **enregistrer les résultats**de la requête.</span><span class="sxs-lookup"><span data-stu-id="0065e-215">Click **Save query results**.</span></span>  
  
2.  <span data-ttu-id="0065e-216">Dans la boîte de dialogue Enregistrer le résultat de la **requête d’exploration de données** , pour source de **données**, sélectionnez [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0065e-216">In the **Save Data Mining Query Result** dialog box, for **Data Source**, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="0065e-217">Vous pouvez également créer une source de données si vous souhaitez enregistrer les données dans une base de données relationnelles différente.</span><span class="sxs-lookup"><span data-stu-id="0065e-217">You can also create a data source if you want to save the data to a different relational database.</span></span>  
  
3.  <span data-ttu-id="0065e-218">Dans la colonne nom de la **table** , tapez un nouveau nom de table temporaire, tel que **tester les prédictions**.</span><span class="sxs-lookup"><span data-stu-id="0065e-218">In the **Table Name** column, type a new temporary table name, such as **Test Predictions**.</span></span>  
  
4.  <span data-ttu-id="0065e-219">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0065e-219">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0065e-220">Pour consulter la table que vous avez créée, créez une connexion au moteur de base de données de l'instance où vous avez enregistré les données, et créez une requête.</span><span class="sxs-lookup"><span data-stu-id="0065e-220">To view the table that you created, create a connection to the database engine of the instance where you saved the data, and create a query.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="0065e-221">Conclusion</span><span class="sxs-lookup"><span data-stu-id="0065e-221">Conclusion</span></span>  
 <span data-ttu-id="0065e-222">Vous avez appris à générer un modèle de série chronologique de base, interpréter les prédictions et créer des prédictions.</span><span class="sxs-lookup"><span data-stu-id="0065e-222">You have learned how to build a basic time series model, interpret the forecasts, and create predictions.</span></span>  
  
 <span data-ttu-id="0065e-223">Les tâches restantes dans ce didacticiel sont facultatives et décrivent les prédictions avancées de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="0065e-223">The remaining tasks in this tutorial are optional, and describe advanced time series predictions.</span></span> <span data-ttu-id="0065e-224">Si vous décidez de continuer, vous allez apprendre à ajouter de nouvelles données à votre modèle et à créer des prédictions sur la série étendue.</span><span class="sxs-lookup"><span data-stu-id="0065e-224">If you decide to go on, you will learn how to add new data to your model and create predictions on the extended series.</span></span> <span data-ttu-id="0065e-225">Vous apprendrez également comment effectuer la prédiction croisée en utilisant la tendance du modèle mais en remplaçant les données à une nouvelle série de données.</span><span class="sxs-lookup"><span data-stu-id="0065e-225">You will also learn how to perform cross-prediction, by using the trend in the model but replacing the data with a new series of data.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="0065e-226">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="0065e-226">Next Lesson</span></span>  
 [<span data-ttu-id="0065e-227">Prédictions de série chronologique avancées &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="0065e-227">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="0065e-228">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0065e-228">See Also</span></span>  
 [<span data-ttu-id="0065e-229">Time Series Model Query Examples</span><span class="sxs-lookup"><span data-stu-id="0065e-229">Time Series Model Query Examples</span></span>](../../2014/analysis-services/data-mining/time-series-model-query-examples.md)  
  
  
