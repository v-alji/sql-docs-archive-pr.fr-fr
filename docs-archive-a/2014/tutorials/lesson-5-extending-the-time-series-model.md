---
title: 'Leçon 5 : extension du modèle de série chronologique | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7aad4946-c903-4e25-88b9-b087c20cb67d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2716e985897f8115d189d9410b7cdb13fb1af291
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603168"
---
# <a name="lesson-5-extending-the-time-series-model"></a><span data-ttu-id="4e5e8-102">Leçon 5 : Extension du modèle de série chronologique</span><span class="sxs-lookup"><span data-stu-id="4e5e8-102">Lesson 5: Extending the Time Series Model</span></span>
  <span data-ttu-id="4e5e8-103">Dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise, vous pouvez ajouter de nouvelles données à un modèle de série chronologique et les incorporer automatiquement au modèle.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-103">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Enterprise, you can add new data to a time series model and automatically incorporate the new data into the model.</span></span> <span data-ttu-id="4e5e8-104">Vous ajoutez de nouvelles données à un modèle d'exploration de données de série chronologique de l'une des deux manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-104">You add new data to a time series mining model in one of two ways:</span></span>  
  
-   <span data-ttu-id="4e5e8-105">Utilisez une instruction PREDICTION JOIN pour joindre des données d'une source externe aux données d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-105">Use a PREDICTION JOIN to join data in an external source to the training data.</span></span>  
  
-   <span data-ttu-id="4e5e8-106">Utilisez une requête singleton de prédiction pour fournir les données un secteur à la fois.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-106">Use a singleton prediction query to provide data one slice at a time.</span></span>  
  
 <span data-ttu-id="4e5e8-107">Par exemple, supposons que vous avez effectué l'apprentissage du modèle d'exploration de données sur les données de ventes existantes il y a quelques mois.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-107">For example, assume that you trained the mining model on existing sales data some months ago.</span></span> <span data-ttu-id="4e5e8-108">Lorsque vous effectuez de nouvelles ventes, vous pouvez avoir envie de mettre à jour les prédictions de ventes afin d'incorporer ces nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-108">When you get new sales, you might want to update the sales predictions to incorporate the new data.</span></span> <span data-ttu-id="4e5e8-109">Pour cela, il vous suffit de fournir les nouveaux chiffres de ventes en tant que données d'entrée et de générer de nouvelles prédictions basées sur le jeu de données composite.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-109">You can do this in one step, by supplying the new sales figures as input data and generating new predictions based on the composite data set.</span></span>  
  
## <a name="making-predictions-with-extend_model_cases"></a><span data-ttu-id="4e5e8-110">Exécution de prédictions avec EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="4e5e8-110">Making Predictions with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="4e5e8-111">Les exemples génériques suivants de prédiction de série chronologique utilisent EXTEND_MODEL_CASES.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-111">The following are generic examples of a time series prediction using EXTEND_MODEL_CASES.</span></span> <span data-ttu-id="4e5e8-112">Le premier exemple vous permet de spécifier le nombre de prédictions commençant à partir de la dernière étape du modèle d'origine :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-112">The first example enables you to specify the number of predictions starting from the last time step of the original model:</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>]  
```  
  
 <span data-ttu-id="4e5e8-113">Le deuxième exemple vous permet de spécifier l'étape à laquelle les prédictions doivent démarrer et celle à laquelle elles doivent se terminer.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-113">The second example enables you to specify the time step where predictions should start, and where they should end.</span></span> <span data-ttu-id="4e5e8-114">Cette option est importante lorsque vous étendez les cas de modèles parce que, par défaut, les étapes utilisées pour les requêtes de prédiction démarrent toujours à la fin de la série d'origine.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-114">This option is important when you extend the model cases because, by default, the time steps used for prediction queries always start at the end of the original series.</span></span>  
  
```  
SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n-start, n-end, EXTEND_MODEL_CASES)   
FROM <mining model>  
PREDICTION JOIN <source query>  
[WHERE <criteria>}  
```  
  
 <span data-ttu-id="4e5e8-115">Dans ce didacticiel, vous allez créer deux types de requêtes.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-115">In this tutorial, you will create both kinds of queries.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query-on-a-time-series-model"></a><span data-ttu-id="4e5e8-116">Pour créer une requête singleton de prédiction sur un modèle de série chronologique</span><span class="sxs-lookup"><span data-stu-id="4e5e8-116">To create a singleton prediction query on a time series model</span></span>  
  
1.  <span data-ttu-id="4e5e8-117">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-117">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="4e5e8-118">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-118">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="4e5e8-119">Copiez l'exemple générique de l'instruction singleton dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-119">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="4e5e8-120">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-120">Replace the following:</span></span>  
  
    ```  
    SELECT [<model columns>,] PredictTimeSeries(<table column reference>, n, EXTEND_MODEL_CASES)   
    ```  
  
     <span data-ttu-id="4e5e8-121">par :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-121">with:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    ```  
  
     <span data-ttu-id="4e5e8-122">La première ligne extrait une valeur du modèle qui identifie la série.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-122">The first line retrieves a value from the model that identifies the series.</span></span>  
  
     <span data-ttu-id="4e5e8-123">La deuxième ligne contient la fonction de prédiction, qui reçoit 6 prédictions pour Quantity.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-123">The second line contains the prediction function, which gets 6 predictions for Quantity.</span></span> <span data-ttu-id="4e5e8-124">Un alias, `PredictQty`, est affecté à la colonne des résultats de prédiction pour simplifier la compréhension des résultats.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-124">An alias, `PredictQty`, is assigned to the prediction result column to make it easier to understand the results.</span></span>  
  
4.  <span data-ttu-id="4e5e8-125">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-125">Replace the following:</span></span>  
  
    ```  
    FROM <mining model>  
    ```  
  
     <span data-ttu-id="4e5e8-126">par :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-126">with:</span></span>  
  
    ```  
    FROM [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="4e5e8-127">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-127">Replace the following:</span></span>  
  
    ```  
    PREDICTION JOIN <source query>  
    ```  
  
     <span data-ttu-id="4e5e8-128">par :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-128">with:</span></span>  
  
    ```  
    NATURAL PREDICTION JOIN   
    (  
       SELECT 1 AS [Reporting Date],  
       '10' AS [Quantity],  
       'M200 Europe' AS [Model Region]  
       UNION SELECT  
       2 AS [Reporting Date],  
       15 AS [Quantity]),  
       'M200 Europe' AS [Model Region]  
    ) AS t  
    ```  
  
6.  <span data-ttu-id="4e5e8-129">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-129">Replace the following:</span></span>  
  
    ```  
    [WHERE <criteria>]  
    ```  
  
     <span data-ttu-id="4e5e8-130">par :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-130">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="4e5e8-131">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-131">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT [Model Region],  
    PredictTimeSeries([Quantity],6, EXTEND_MODEL_CASES) AS PredictQty  
    FROM  
       [Forecasting_MIXED]  
    NATURAL PREDICTION JOIN   
       SELECT 1 AS [ReportingDate],  
      '10' AS [Quantity],  
      'M200 Europe' AS [ModelRegion]  
    UNION SELECT  
      2 AS [ReportingDate],  
      15 AS [Quantity]),  
      'M200 Europe' AS [ModelRegion]  
    ) AS t  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
7.  <span data-ttu-id="4e5e8-132">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-132">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="4e5e8-133">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Singleton_TimeSeries_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="4e5e8-133">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_TimeSeries_Query.dmx`.</span></span>  
  
9. <span data-ttu-id="4e5e8-134">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="4e5e8-134">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="4e5e8-135">La requête renvoie des prédictions de quantité de ventes pour le vélo M200 dans les régions Europe et Pacific.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-135">The query returns predictions of sales quantity for the M200 bicycle in the Europe and Pacific regions.</span></span>  
  
## <a name="understanding-prediction-start-with-extend_model_cases"></a><span data-ttu-id="4e5e8-136">Démarrage de prédiction avec EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="4e5e8-136">Understanding Prediction Start with EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="4e5e8-137">Maintenant que vous avez créé des prédictions basées sur le modèle d'origine, et avec de nouvelles données, vous pouvez comparer les résultats pour observer comment la mise à jour des données de ventes affecte les prédictions.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-137">Now that you have created predictions based on the original model, and with new data, you can compare the results to see how updating the sales data affects the predictions.</span></span> <span data-ttu-id="4e5e8-138">Avant cela, examinez le code que vous venez de créer et remarquez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-138">Before you do so, review the code that you just created, and notice the following:</span></span>  
  
-   <span data-ttu-id="4e5e8-139">Vous avez fourni de nouvelles données uniquement pour la région Europe.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-139">You supplied new data for only the Europe region.</span></span>  
  
-   <span data-ttu-id="4e5e8-140">Vous avez fourni des nouvelles données uniquement pour deux mois.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-140">You supplied only two months' worth of new data.</span></span>  
  
 <span data-ttu-id="4e5e8-141">Le tableau suivant montre comment les nouvelles valeurs fournies pour M200 Europe affectent les prédictions.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-141">The following table shows how the new values supplied for M200 Europe affect predictions.</span></span> <span data-ttu-id="4e5e8-142">Vous n'avez pas fourni de nouvelles données pour le produit M200 dans la région Pacific, mais cette série est présentée à titre de comparaison :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-142">You did not provide any new data for the M200 product in the Pacific region, but this series is presented for comparison:</span></span>  
  
 <span data-ttu-id="4e5e8-143">**Produit et région : M200 Europe**</span><span class="sxs-lookup"><span data-stu-id="4e5e8-143">**Product and Region: M200 Europe**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="4e5e8-144">Modèle existant (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="4e5e8-144">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="4e5e8-145">Modèle avec les données de ventes (`PredictTimeSeries` mises à jour avec `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="4e5e8-145">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="4e5e8-146">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="4e5e8-146">M200 Europe</span></span>|<span data-ttu-id="4e5e8-147">7/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-147">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-148">77</span><span class="sxs-lookup"><span data-stu-id="4e5e8-148">77</span></span>|<span data-ttu-id="4e5e8-149">10</span><span class="sxs-lookup"><span data-stu-id="4e5e8-149">10</span></span>|  
|<span data-ttu-id="4e5e8-150">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="4e5e8-150">M200 Europe</span></span>|<span data-ttu-id="4e5e8-151">8/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-151">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-152">64</span><span class="sxs-lookup"><span data-stu-id="4e5e8-152">64</span></span>|<span data-ttu-id="4e5e8-153">15</span><span class="sxs-lookup"><span data-stu-id="4e5e8-153">15</span></span>|  
|<span data-ttu-id="4e5e8-154">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="4e5e8-154">M200 Europe</span></span>|<span data-ttu-id="4e5e8-155">9/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-155">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-156">59</span><span class="sxs-lookup"><span data-stu-id="4e5e8-156">59</span></span>|<span data-ttu-id="4e5e8-157">72</span><span class="sxs-lookup"><span data-stu-id="4e5e8-157">72</span></span>|  
|<span data-ttu-id="4e5e8-158">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="4e5e8-158">M200 Europe</span></span>|<span data-ttu-id="4e5e8-159">10/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-159">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-160">56</span><span class="sxs-lookup"><span data-stu-id="4e5e8-160">56</span></span>|<span data-ttu-id="4e5e8-161">69</span><span class="sxs-lookup"><span data-stu-id="4e5e8-161">69</span></span>|  
|<span data-ttu-id="4e5e8-162">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="4e5e8-162">M200 Europe</span></span>|<span data-ttu-id="4e5e8-163">11/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-163">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-164">56</span><span class="sxs-lookup"><span data-stu-id="4e5e8-164">56</span></span>|<span data-ttu-id="4e5e8-165">68</span><span class="sxs-lookup"><span data-stu-id="4e5e8-165">68</span></span>|  
|<span data-ttu-id="4e5e8-166">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="4e5e8-166">M200 Europe</span></span>|<span data-ttu-id="4e5e8-167">25/12/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-167">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-168">74</span><span class="sxs-lookup"><span data-stu-id="4e5e8-168">74</span></span>|<span data-ttu-id="4e5e8-169">89</span><span class="sxs-lookup"><span data-stu-id="4e5e8-169">89</span></span>|  
  
 <span data-ttu-id="4e5e8-170">**Produit et région : M200 Pacific**</span><span class="sxs-lookup"><span data-stu-id="4e5e8-170">**Product and Region: M200 Pacific**</span></span>  
  
|||||  
|-|-|-|-|  
|||<span data-ttu-id="4e5e8-171">Modèle existant (`PredictTimeSeries`)</span><span class="sxs-lookup"><span data-stu-id="4e5e8-171">Existing model (`PredictTimeSeries`)</span></span>|<span data-ttu-id="4e5e8-172">Modèle avec les données de ventes (`PredictTimeSeries` mises à jour avec `EXTEND_MODEL_CASES`)</span><span class="sxs-lookup"><span data-stu-id="4e5e8-172">Model with updated sales data (`PredictTimeSeries` with `EXTEND_MODEL_CASES`)</span></span>|  
|<span data-ttu-id="4e5e8-173">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="4e5e8-173">M200 Pacific</span></span>|<span data-ttu-id="4e5e8-174">7/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-174">7/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-175">41</span><span class="sxs-lookup"><span data-stu-id="4e5e8-175">41</span></span>|<span data-ttu-id="4e5e8-176">41</span><span class="sxs-lookup"><span data-stu-id="4e5e8-176">41</span></span>|  
|<span data-ttu-id="4e5e8-177">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="4e5e8-177">M200 Pacific</span></span>|<span data-ttu-id="4e5e8-178">8/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-178">8/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-179">44</span><span class="sxs-lookup"><span data-stu-id="4e5e8-179">44</span></span>|<span data-ttu-id="4e5e8-180">44</span><span class="sxs-lookup"><span data-stu-id="4e5e8-180">44</span></span>|  
|<span data-ttu-id="4e5e8-181">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="4e5e8-181">M200 Pacific</span></span>|<span data-ttu-id="4e5e8-182">9/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-182">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-183">38</span><span class="sxs-lookup"><span data-stu-id="4e5e8-183">38</span></span>|<span data-ttu-id="4e5e8-184">38</span><span class="sxs-lookup"><span data-stu-id="4e5e8-184">38</span></span>|  
|<span data-ttu-id="4e5e8-185">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="4e5e8-185">M200 Pacific</span></span>|<span data-ttu-id="4e5e8-186">10/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-186">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-187">41</span><span class="sxs-lookup"><span data-stu-id="4e5e8-187">41</span></span>|<span data-ttu-id="4e5e8-188">41</span><span class="sxs-lookup"><span data-stu-id="4e5e8-188">41</span></span>|  
|<span data-ttu-id="4e5e8-189">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="4e5e8-189">M200 Pacific</span></span>|<span data-ttu-id="4e5e8-190">11/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-190">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-191">36</span><span class="sxs-lookup"><span data-stu-id="4e5e8-191">36</span></span>|<span data-ttu-id="4e5e8-192">36</span><span class="sxs-lookup"><span data-stu-id="4e5e8-192">36</span></span>|  
|<span data-ttu-id="4e5e8-193">M200 Pacific</span><span class="sxs-lookup"><span data-stu-id="4e5e8-193">M200 Pacific</span></span>|<span data-ttu-id="4e5e8-194">25/12/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-194">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-195">39</span><span class="sxs-lookup"><span data-stu-id="4e5e8-195">39</span></span>|<span data-ttu-id="4e5e8-196">39</span><span class="sxs-lookup"><span data-stu-id="4e5e8-196">39</span></span>|  
  
 <span data-ttu-id="4e5e8-197">D'après ces résultats, vous pouvez conclure deux choses :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-197">From these results, you can see two things:</span></span>  
  
-   <span data-ttu-id="4e5e8-198">Les deux premières prédictions pour la série M200 Europe sont exactement les mêmes que les nouvelles données que vous avez fournies.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-198">The first two predictions for the M200 Europe series are exactly the same as the new data you supplied.</span></span> <span data-ttu-id="4e5e8-199">Par sa conception, Analysis Services renvoie les nouveaux points de données réels au lieu d'élaborer une prédiction.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-199">By design, Analysis Services returns the actual new data points instead of making a prediction.</span></span> <span data-ttu-id="4e5e8-200">Ceci est dû au fait que lorsque vous étendez les cas de modèles, les étapes utilisées pour les requêtes de prédiction démarrent toujours à la fin de la série d'origine.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-200">That is because when you extend the model cases, the time steps used for prediction queries always start at the end of the original series.</span></span> <span data-ttu-id="4e5e8-201">Par conséquent, si vous ajoutez deux nouveaux points de données, les deux premières prédictions renvoyées et les nouvelles données se chevauchent.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-201">Therefore, if you add two new data points, the first two predictions returned overlap with the new data.</span></span>  
  
-   <span data-ttu-id="4e5e8-202">Après avoir utilisé tous les nouveaux points de données, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] élabore des prédictions selon le modèle mis à jour.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-202">After all the new data points are used up, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] makes predictions based on the updated model.</span></span> <span data-ttu-id="4e5e8-203">Par conséquent, à compter de septembre 2005, vous pouvez observer la différence entre les prédictions pour M200 Europe depuis le modèle d'origine, dans la colonne gauche, et le modèle qui utilise EXTEND_MODEL_CASES, dans la colonne droite.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-203">Therefore, starting in September 2005, you can see the difference between predictions for M200 Europe from the original model, in the left-hand column, and the model that uses EXTEND_MODEL_CASES, in the right-hand column.</span></span> <span data-ttu-id="4e5e8-204">Les prédictions sont différentes parce que le modèle a été mis à jour avec les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-204">The predictions are different because the model has been updated with the new data.</span></span>  
  
## <a name="using-start-and-end-time-steps-to-control-predictions"></a><span data-ttu-id="4e5e8-205">Utilisation d'étapes de début et de fin pour contrôler des prédictions</span><span class="sxs-lookup"><span data-stu-id="4e5e8-205">Using Start and End Time Steps to Control Predictions</span></span>  
 <span data-ttu-id="4e5e8-206">Lorsque vous étendez un modèle, les nouvelles données sont toujours jointes à la fin de la série.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-206">When you extend a model, the new data is always attached to the end of the series.</span></span> <span data-ttu-id="4e5e8-207">Toutefois, à des fins de prédiction, les tranches de temps utilisées pour les requêtes de prédiction commencent toujours à la fin de la série d'origine.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-207">However, for the purpose of prediction, the time slices used for prediction queries start at the end of the original series.</span></span> <span data-ttu-id="4e5e8-208">Si vous souhaitez obtenir uniquement les nouvelles prédictions lorsque vous ajoutez les nouvelles données, vous devez spécifier le point de départ sous la forme d'un nombre de tranches de temps.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-208">If you want to obtain only the new predictions when you add the new data, you must specify the starting point as a number of time slices.</span></span> <span data-ttu-id="4e5e8-209">Par exemple, si vous ajoutez deux nouveaux points de données et souhaitez élaborer quatre nouvelles prédictions, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="4e5e8-209">For example, if you are adding two new data points and want to make four new predictions, you would do the following:</span></span>  
  
-   <span data-ttu-id="4e5e8-210">Créez une jointure PREDICTION JOIN sur un modèle de série chronologique et spécifiez deux mois de nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-210">Create a PREDICTION JOIN on a time series model, and specify two months of new data.</span></span>  
  
-   <span data-ttu-id="4e5e8-211">Demandez des prédictions pour quatre tranches de temps, dont le point de départ est la tranche de temps 3 et le point de terminaison la tranche de temps 6.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-211">Request predictions for four time slices, where the starting point is 3, and the ending point is time slice 6.</span></span>  
  
 <span data-ttu-id="4e5e8-212">En d’autres termes, si vos nouvelles données contiennent n tranches de temps et que vous demandez des prédictions pour les étapes 1 à n, les prédictions coïncideront avec la même période que les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-212">In other words, if your new data contains n time slices, and you request predictions for time steps 1 through n, the predictions will coincide with the same period as the new data.</span></span> <span data-ttu-id="4e5e8-213">Pour obtenir de nouvelles prédictions pour des périodes non couvertes par vos données, vous devez commencer les prédictions à la tranche de temps n+1 après la nouvelle série de données ou vous assurer de demander des tranches de temps supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-213">To get new predictions for a time periods not covered by your data, you must either start predictions at the time slice n+1 after the new data series, or make sure that you request additional time slices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e5e8-214">Vous ne pouvez pas effectuer de prédictions historiques lorsque vous ajoutez de nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-214">You cannot make historical predictions when you add new data.</span></span>  
  
 <span data-ttu-id="4e5e8-215">L'exemple suivant présente l'instruction DMX qui vous permet d'obtenir uniquement les nouvelles prédictions pour les deux séries mentionnées dans l'exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-215">The following example shows the DMX statement that lets you get only the new predictions for the two series in the previous example.</span></span>  
  
```  
SELECT [Model Region],  
PredictTimeSeries([Quantity],3,6, EXTEND_MODEL_CASES) AS PredictQty  
FROM  
   [Forecasting_MIXED]  
NATURAL PREDICTION JOIN   
   SELECT 1 AS [ReportingDate],  
  '10' AS [Quantity],  
  'M200 Europe' AS [ModelRegion]  
UNION SELECT  
  2 AS [ReportingDate],  
  15 AS [Quantity]),  
  'M200 Europe' AS [ModelRegion]  
) AS t  
WHERE [ModelRegion] = 'M200 Europe'  
```  
  
 <span data-ttu-id="4e5e8-216">Les résultats de prédiction démarrent à la tranche de temps 3, qui se situe après les 2 mois de nouvelles données que vous avez fournis.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-216">The prediction results start at time slice 3, which is after the 2 months of new data that you supplied.</span></span>  
  
 <span data-ttu-id="4e5e8-217">**Produit et région : M200 Europe**</span><span class="sxs-lookup"><span data-stu-id="4e5e8-217">**Product and Region: M200 Europe**</span></span>  
  
 <span data-ttu-id="4e5e8-218">Modèle avec les données mises à jour (PredictTimeSeries avec EXTEND_MODEL_CASES)</span><span class="sxs-lookup"><span data-stu-id="4e5e8-218">Model with updated data (PredictTimeSeries with EXTEND_MODEL_CASES)</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="4e5e8-219">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="4e5e8-219">M200 Europe</span></span>|<span data-ttu-id="4e5e8-220">9/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-220">9/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-221">72</span><span class="sxs-lookup"><span data-stu-id="4e5e8-221">72</span></span>|  
|<span data-ttu-id="4e5e8-222">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="4e5e8-222">M200 Europe</span></span>|<span data-ttu-id="4e5e8-223">10/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-223">10/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-224">69</span><span class="sxs-lookup"><span data-stu-id="4e5e8-224">69</span></span>|  
|<span data-ttu-id="4e5e8-225">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="4e5e8-225">M200 Europe</span></span>|<span data-ttu-id="4e5e8-226">11/25/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-226">11/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-227">68</span><span class="sxs-lookup"><span data-stu-id="4e5e8-227">68</span></span>|  
|<span data-ttu-id="4e5e8-228">M200 Europe</span><span class="sxs-lookup"><span data-stu-id="4e5e8-228">M200 Europe</span></span>|<span data-ttu-id="4e5e8-229">25/12/2008 12:00:00</span><span class="sxs-lookup"><span data-stu-id="4e5e8-229">12/25/2008 12:00:00 AM</span></span>|<span data-ttu-id="4e5e8-230">89</span><span class="sxs-lookup"><span data-stu-id="4e5e8-230">89</span></span>|  
  
## <a name="making-predictions-with-replace_model_cases"></a><span data-ttu-id="4e5e8-231">Exécution de prédictions avec REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="4e5e8-231">Making Predictions with REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="4e5e8-232">Le remplacement des cas de modèles s'avère utile lorsque vous souhaitez effectuer l'apprentissage d'un modèle sur un ensemble de cas, puis appliquer ce modèle à une série de données différente.</span><span class="sxs-lookup"><span data-stu-id="4e5e8-232">Replacing the model cases is useful when you want to train a model on one set of cases and then apply that model to a different data series.</span></span> <span data-ttu-id="4e5e8-233">Une procédure pas à pas détaillée de ce scénario est présentée dans la [leçon 2 : génération d’un scénario de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="4e5e8-233">A detailed walkthrough of this scenario is presented in [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e5e8-234">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e5e8-234">See Also</span></span>  
 <span data-ttu-id="4e5e8-235">[Exemples de requêtes de modèle de série chronologique](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="4e5e8-235">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="4e5e8-236">PredictTimeSeries &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="4e5e8-236">PredictTimeSeries &#40;DMX&#41;</span></span>](/sql/dmx/predicttimeseries-dmx)  
  
  
