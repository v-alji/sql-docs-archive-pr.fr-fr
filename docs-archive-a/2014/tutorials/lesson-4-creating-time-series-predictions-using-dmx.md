---
title: 'Leçon 4 : création de prédictions de série chronologique à l’aide de DMX | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6b883e43-209d-489a-8dc3-9349f88acae8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 772e5f5f71ca82dd18fec48730522c80e907414f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694856"
---
# <a name="lesson-4-creating-time-series-predictions-using-dmx"></a><span data-ttu-id="261aa-102">Leçon 4 : Création de prédictions de série chronologique à l’aide d’extensions DMX</span><span class="sxs-lookup"><span data-stu-id="261aa-102">Lesson 4: Creating Time Series Predictions Using DMX</span></span>
  <span data-ttu-id="261aa-103">Dans cette leçon et dans la leçon suivante, vous allez utiliser les extensions DMX (Data Mining Extensions) pour créer différents types de prédictions en fonction des modèles de série chronologique que vous avez créés au cours de la [leçon 1 : création d’un modèle](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) d’exploration de données de série chronologique et d’une structure d’exploration de données, ainsi que [leçon 2 : ajout de modèles d’exploration de](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md)données</span><span class="sxs-lookup"><span data-stu-id="261aa-103">In this lesson and the following lesson, you will use Data Mining Extensions (DMX) to create different types of predictions based on the time series models that you created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md) and [Lesson 2: Adding Mining Models to the Time Series Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md).</span></span>  
  
 <span data-ttu-id="261aa-104">Avec un modèle de série chronologique, de nombreuses options sont à votre disposition pour élaborer des prédictions :</span><span class="sxs-lookup"><span data-stu-id="261aa-104">With a time series model, you have many options for making predictions:</span></span>  
  
-   <span data-ttu-id="261aa-105">Utilisation des modèles et données existants dans le modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="261aa-105">Use the existing patterns and data in the mining model</span></span>  
  
-   <span data-ttu-id="261aa-106">Utilisation des modèles existants dans le modèle d'exploration de données mais fourniture de nouvelles données</span><span class="sxs-lookup"><span data-stu-id="261aa-106">Use the existing patterns in the mining model but supply new data</span></span>  
  
-   <span data-ttu-id="261aa-107">Ajout de nouvelles données au modèle ou mise à jour du modèle</span><span class="sxs-lookup"><span data-stu-id="261aa-107">Add new data to the model or update the model.</span></span>  
  
 <span data-ttu-id="261aa-108">La syntaxe permettant d'effectuer ces types de prédictions est résumée ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="261aa-108">The syntax for making these prediction types is summarized below:</span></span>  
  
 <span data-ttu-id="261aa-109">Prédiction de série chronologique par défaut</span><span class="sxs-lookup"><span data-stu-id="261aa-109">Default time series prediction</span></span>  
 <span data-ttu-id="261aa-110">Utilisez [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) pour retourner le nombre spécifié de prédictions à partir du modèle d’exploration de données formé.</span><span class="sxs-lookup"><span data-stu-id="261aa-110">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) to return the specified number of predictions from the trained mining model.</span></span>  
  
 <span data-ttu-id="261aa-111">Par exemple, consultez [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) ou [exemples de requêtes de modèle de série chronologique](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="261aa-111">For example, see [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) or [Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md).</span></span>  
  
 <span data-ttu-id="261aa-112">EXTEND_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="261aa-112">EXTEND_MODEL_CASES</span></span>  
 <span data-ttu-id="261aa-113">Utilisez [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) avec l’argument EXTEND_MODEL_CASES pour ajouter de nouvelles données, étendre la série et créer des prédictions basées sur le modèle d’exploration de données mis à jour.</span><span class="sxs-lookup"><span data-stu-id="261aa-113">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the EXTEND_MODEL_CASES argument to add new data, extend the series, and create predictions based on the updated mining model.</span></span>  
  
 <span data-ttu-id="261aa-114">Ce didacticiel contient un exemple de la manière d'utiliser EXTEND_MODEL_CASES.</span><span class="sxs-lookup"><span data-stu-id="261aa-114">This tutorial contains an example of how to use EXTEND_MODEL_CASES.</span></span>  
  
 <span data-ttu-id="261aa-115">REPLACE_MODEL_CASES</span><span class="sxs-lookup"><span data-stu-id="261aa-115">REPLACE_MODEL_CASES</span></span>  
 <span data-ttu-id="261aa-116">Utilisez [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) avec l’argument REPLACE_MODEL_CASES pour remplacer les données d’origine par une nouvelle série de données, puis créez des prédictions en fonction de l’application des modèles dans le modèle d’exploration de données à la nouvelle série de données.</span><span class="sxs-lookup"><span data-stu-id="261aa-116">Use [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) with the REPLACE_MODEL_CASES argument to replace the original data with a new data series, and then create predictions based on applying the patterns in the mining model to the new data series.</span></span>  
  
 <span data-ttu-id="261aa-117">Pour obtenir un exemple d’utilisation de REPLACE_MODEL_CASES, consultez [leçon 2 : génération d’un scénario de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="261aa-117">For an example of how to use REPLACE_MODEL_CASES, see [Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="261aa-118">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="261aa-118">Lesson Tasks</span></span>  
 <span data-ttu-id="261aa-119">Dans cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="261aa-119">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="261aa-120">créer une requête pour obtenir les prédictions par défaut basées sur des données existantes.</span><span class="sxs-lookup"><span data-stu-id="261aa-120">Create a query to get the default predictions based on existing data.</span></span>  
  
 <span data-ttu-id="261aa-121">Au cours de la leçon suivante, vous allez effectuer les tâches connexes suivantes :</span><span class="sxs-lookup"><span data-stu-id="261aa-121">In the following lesson you will perform the following related tasks:</span></span>  
  
-   <span data-ttu-id="261aa-122">créer une requête pour fournir de nouvelles données et obtenir des prédictions mises à jour.</span><span class="sxs-lookup"><span data-stu-id="261aa-122">Create a query to supply new data and get updated predictions.</span></span>  
  
 <span data-ttu-id="261aa-123">En plus de pouvoir créer manuellement des requêtes en utilisant des extensions DMX, vous pouvez également créer des prédictions à l'aide du Générateur de requêtes de prédiction dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="261aa-123">In addition to creating queries manually by using DMX, you can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="simple-time-series-prediction-query"></a><span data-ttu-id="261aa-124">Requête de prédiction de série chronologique simple</span><span class="sxs-lookup"><span data-stu-id="261aa-124">Simple Time Series Prediction Query</span></span>  
 <span data-ttu-id="261aa-125">La première étape consiste à utiliser l'instruction `SELECT FROM` avec la fonction `PredictTimeSeries` pour créer des prédictions de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="261aa-125">The first step is to use the `SELECT FROM` statement together with the `PredictTimeSeries` function to create time series predictions.</span></span> <span data-ttu-id="261aa-126">Les modèles de série chronologique prennent en charge une syntaxe simplifiée pour créer des prédictions : vous n'avez pas besoin de fournir d'entrées, mais vous devez uniquement spécifier le nombre de prédictions à créer.</span><span class="sxs-lookup"><span data-stu-id="261aa-126">Time series models support a simplified syntax for creating predictions: you do not need to supply any inputs, but only have to specify the number of predictions to create.</span></span> <span data-ttu-id="261aa-127">L'exemple générique suivant présente l'instruction que vous utiliserez :</span><span class="sxs-lookup"><span data-stu-id="261aa-127">The following is a generic example of the statement you will use:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model name>]   
WHERE [<criteria>]  
```  
  
 <span data-ttu-id="261aa-128">La liste de sélection peut contenir des colonnes du modèle, telles que le nom de la gamme de produits pour laquelle vous créez les prédictions ou des fonctions de prédiction, telles que le [décalage &#40;dmx&#41;](/sql/dmx/lag-dmx) ou [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), qui sont spécifiquement pour les modèles d’exploration de données de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="261aa-128">The select list can contain columns from the model, such as the name of the product line that you are creating the predictions for, or prediction functions, such as [Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) or [PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx), which are specifically for time series mining models.</span></span>  
  
#### <a name="to-create-a-simple-time-series-prediction-query"></a><span data-ttu-id="261aa-129">Pour créer une requête de prédiction de série chronologique simple</span><span class="sxs-lookup"><span data-stu-id="261aa-129">To create a simple time series prediction query</span></span>  
  
1.  <span data-ttu-id="261aa-130">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="261aa-130">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="261aa-131">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="261aa-131">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="261aa-132">Copiez l'exemple générique de l'instruction dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="261aa-132">Copy the generic example of the statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="261aa-133">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="261aa-133">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="261aa-134">par :</span><span class="sxs-lookup"><span data-stu-id="261aa-134">with:</span></span>  
  
    ```  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    ```  
  
     <span data-ttu-id="261aa-135">La première ligne extrait une valeur du modèle d'exploration de données qui identifie la série.</span><span class="sxs-lookup"><span data-stu-id="261aa-135">The first line retrieves a value from the mining model that identifies the series.</span></span>  
  
     <span data-ttu-id="261aa-136">Les deuxième et troisième lignes utilisent la fonction `PredictTimeSeries`.</span><span class="sxs-lookup"><span data-stu-id="261aa-136">The second and third lines use the `PredictTimeSeries` function.</span></span> <span data-ttu-id="261aa-137">Chaque ligne prédit un attribut différent, `[Quantity]` ou `[Amount]`.</span><span class="sxs-lookup"><span data-stu-id="261aa-137">Each line predicts a different attribute, `[Quantity]` or `[Amount]`.</span></span> <span data-ttu-id="261aa-138">Les nombres indiqués après les noms des attributs prédictibles précisent le nombre d'étapes à prédire.</span><span class="sxs-lookup"><span data-stu-id="261aa-138">The numbers after the names of the predictable attributes specify the number of time steps to predict.</span></span>  
  
     <span data-ttu-id="261aa-139">La clause `AS` est utilisée pour fournir un nom à la colonne renvoyée par chaque fonction de prédiction.</span><span class="sxs-lookup"><span data-stu-id="261aa-139">The `AS` clause is used to provide a name for the column that is returned by each prediction function.</span></span> <span data-ttu-id="261aa-140">Si vous ne fournissez pas d'alias, les deux colonnes sont renvoyées avec l'étiquette `Expression` par défaut.</span><span class="sxs-lookup"><span data-stu-id="261aa-140">If you do not supply an alias, by default both columns are returned with the label, `Expression`.</span></span>  
  
4.  <span data-ttu-id="261aa-141">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="261aa-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="261aa-142">par :</span><span class="sxs-lookup"><span data-stu-id="261aa-142">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
5.  <span data-ttu-id="261aa-143">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="261aa-143">Replace the following:</span></span>  
  
    ```  
    WHERE [criteria>]   
    ```  
  
     <span data-ttu-id="261aa-144">par :</span><span class="sxs-lookup"><span data-stu-id="261aa-144">with:</span></span>  
  
    ```  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
     <span data-ttu-id="261aa-145">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="261aa-145">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
    [Forecasting_MIXED].[ModelRegion],  
    PredictTimeSeries([Forecasting_MIXED].[Quantity],6) AS PredictQty,  
    PredictTimeSeries ([Forecasting_MIXED].[Amount],6) AS PredictAmt  
    FROM   
    [Forecasting_MIXED]  
    WHERE [ModelRegion] = 'M200 Europe' OR  
    [ModelRegion] = 'M200 Pacific'  
    ```  
  
6.  <span data-ttu-id="261aa-146">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="261aa-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="261aa-147">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `SimpleTimeSeriesPrediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="261aa-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SimpleTimeSeriesPrediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="261aa-148">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="261aa-148">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="261aa-149">La requête renvoie 6 prédictions pour chacune des deux combinaisons de produit et région spécifiées dans la clause `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="261aa-149">The query returns 6 predictions for each of the two combinations of product and region that are specified in the `WHERE` clause.</span></span>  
  
 <span data-ttu-id="261aa-150">Dans la leçon suivante, vous allez créer une requête qui fournit de nouvelles données au modèle, puis comparer les résultats de cette prédiction avec celle que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="261aa-150">In the next lesson, you will create a query that supplies new data to the model, and compare the results of that prediction with the one you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="261aa-151">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="261aa-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="261aa-152">Leçon 5 : Extension du modèle de série chronologique</span><span class="sxs-lookup"><span data-stu-id="261aa-152">Lesson 5: Extending the Time Series Model</span></span>](../../2014/tutorials/lesson-5-extending-the-time-series-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="261aa-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="261aa-153">See Also</span></span>  
 <span data-ttu-id="261aa-154">[PredictTimeSeries&#41;DMX &#40;](/sql/dmx/predicttimeseries-dmx) </span><span class="sxs-lookup"><span data-stu-id="261aa-154">[PredictTimeSeries &#40;DMX&#41;](/sql/dmx/predicttimeseries-dmx) </span></span>  
 <span data-ttu-id="261aa-155">[Retard &#40;&#41;DMX](/sql/dmx/lag-dmx) </span><span class="sxs-lookup"><span data-stu-id="261aa-155">[Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) </span></span>  
 <span data-ttu-id="261aa-156">[Exemples de requêtes de modèle de série chronologique](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="261aa-156">[Time Series Model Query Examples](../../2014/analysis-services/data-mining/time-series-model-query-examples.md) </span></span>  
 [<span data-ttu-id="261aa-157">Leçon 2 : génération d’un scénario de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="261aa-157">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
  
