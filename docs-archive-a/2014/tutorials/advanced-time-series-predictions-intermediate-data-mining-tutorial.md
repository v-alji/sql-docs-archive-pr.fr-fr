---
title: Prédictions de séries chronologiques avancées (didacticiel sur l’exploration de données intermédiaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b614ebdb-07ca-44af-a0ff-893364bd4b71
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 70ebf856ba0782cbf44969aba30602818015582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704500"
---
# <a name="advanced-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="01430-102">Prédictions de série chronologique avancées (Didacticiel intermédiaire sur l'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="01430-102">Advanced Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="01430-103">Le modèle de prévision vous a appris que même si les ventes dans la plupart des régions suivent une tendance similaire, certaines régions et certains modèles, tels que le modèle M200 dans la région Pacific, présentent des tendances très différentes.</span><span class="sxs-lookup"><span data-stu-id="01430-103">You saw from exploring the forecasting model that although sales in most of the regions follow a similar pattern, some regions and some models, such as the M200 model in the Pacific region, exhibit very different trends.</span></span> <span data-ttu-id="01430-104">Ceci n'est pas une surprise puisque vous savez que les différences entre les régions sont courantes et sont causées par de nombreux facteurs, notamment les promotions marketing, la création de rapports inexacts ou des événements géopolitiques.</span><span class="sxs-lookup"><span data-stu-id="01430-104">This does not surprise you, as you know that differences among regions are common and can be caused by many factors, including marketing promotions, inaccurate reporting, or geopolitical events.</span></span>  
  
 <span data-ttu-id="01430-105">Toutefois, vos utilisateurs demandent un modèle qui peut être appliqué dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="01430-105">However, your users are asking for a model that can be applied worldwide.</span></span> <span data-ttu-id="01430-106">C'est pourquoi, dans le but de réduire la portée de facteurs individuels sur les projections, vous décidez de générer un modèle basé sur les mesures cumulées des ventes internationales.</span><span class="sxs-lookup"><span data-stu-id="01430-106">Therefore, to minimize the effect of individual factors on projections, you decide to build a model that is based on aggregated measures of worldwide sales.</span></span> <span data-ttu-id="01430-107">Vous pouvez alors utiliser ce modèle pour faire des prédictions pour chacune des régions.</span><span class="sxs-lookup"><span data-stu-id="01430-107">You can then use this model to make predictions for each individual region.</span></span>  
  
 <span data-ttu-id="01430-108">Dans cette tâche, vous allez générer toutes les sources de données dont vous avez besoin pour effectuer les tâches de prédiction avancées.</span><span class="sxs-lookup"><span data-stu-id="01430-108">In this task, you will build all the data sources that you need to perform the advanced prediction tasks.</span></span> <span data-ttu-id="01430-109">Vous allez créer deux vues de source de données à utiliser comme entrées à la requête de prédiction, et une vue de source de données à utiliser lors de la génération d'un nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="01430-109">You will create two data source views for use as inputs to the prediction query, and one data source view to use in building a new model.</span></span>  
  
 <span data-ttu-id="01430-110">**Étapes**</span><span class="sxs-lookup"><span data-stu-id="01430-110">**Steps**</span></span>  
  
1.  [<span data-ttu-id="01430-111">Préparez les données de ventes étendues (pour la prédiction)</span><span class="sxs-lookup"><span data-stu-id="01430-111">Prepare the extended sales data (for prediction)</span></span>](#bkmk_newExtendData)  
  
2.  [<span data-ttu-id="01430-112">Préparez les données cumulées (pour générer le modèle)</span><span class="sxs-lookup"><span data-stu-id="01430-112">Prepare the aggregated data (for building the model)</span></span>](#bkmk_newReplaceData)  
  
3.  [<span data-ttu-id="01430-113">Préparez les données de la série (pour la prédiction croisée)</span><span class="sxs-lookup"><span data-stu-id="01430-113">Prepare the series data (for cross-prediction)</span></span>](#bkmk_CrossData2)  
  
4.  [<span data-ttu-id="01430-114">Effectuez les prédictions à l'aide d'EXTEND</span><span class="sxs-lookup"><span data-stu-id="01430-114">Predict using EXTEND</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
5.  [<span data-ttu-id="01430-115">Créez le modèle de prédiction croisée</span><span class="sxs-lookup"><span data-stu-id="01430-115">Create the cross-prediction model</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
6.  [<span data-ttu-id="01430-116">Effectuez les prédictions à l'aide de REPLACE</span><span class="sxs-lookup"><span data-stu-id="01430-116">Predict using REPLACE</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
7.  [<span data-ttu-id="01430-117">Examinez les nouvelles prédictions</span><span class="sxs-lookup"><span data-stu-id="01430-117">Review the new predictions</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
##  <a name="creating-the-new-extended-sales-data"></a><a name="bkmk_newExtendData"></a><span data-ttu-id="01430-118">Création des nouvelles données de ventes étendues</span><span class="sxs-lookup"><span data-stu-id="01430-118">Creating the New Extended Sales Data</span></span>  
 <span data-ttu-id="01430-119">Pour mettre à jour vos données de ventes, vous devez obtenir les derniers chiffres de vente.</span><span class="sxs-lookup"><span data-stu-id="01430-119">To update your sales data, you will need to get the latest sales figures.</span></span> <span data-ttu-id="01430-120">Les données qui viennent d'arriver de la région Pacific sont d'un intérêt particulier car cette région a lancé une promotion commerciale régionale pour attirer l'attention sur les nouveaux magasins et pour attiser la conscience de leurs produits.</span><span class="sxs-lookup"><span data-stu-id="01430-120">Of particular interest are the data just in from the Pacific region, which launched a regional sales promotion to call attention to the new stores and raise awareness of their products.</span></span>  
  
 <span data-ttu-id="01430-121">Pour ce scénario, nous partons du principe que les données ont été importées à partir d’un classeur Excel qui contient seulement trois mois de nouvelles données pour deux régions.</span><span class="sxs-lookup"><span data-stu-id="01430-121">For this scenario, we'll assume that the data has been imported from an Excel workbook that contains just three months of new data for a couple of regions.</span></span> <span data-ttu-id="01430-122">Vous allez créer une table pour les données à l’aide d’un script Transact-SQL, puis définir une vue de source de données à utiliser pour la prédiction.</span><span class="sxs-lookup"><span data-stu-id="01430-122">You'll create a table for the data using a Transact-SQL script, and then define a data source view to use for prediction.</span></span>  
  
#### <a name="create-the-table-with-new-sales-data"></a><span data-ttu-id="01430-123">Créez la table avec les nouvelles données de ventes</span><span class="sxs-lookup"><span data-stu-id="01430-123">Create the table with new sales data</span></span>  
  
1.  <span data-ttu-id="01430-124">Dans une fenêtre de requête Transact-SQL, exécutez l'instruction suivante pour ajouter les données de ventes à la base de données AdventureWorksDW (ou une autre base de données).</span><span class="sxs-lookup"><span data-stu-id="01430-124">In a Transact-SQL query window, execute the following statement to add the sales data to the AdventureWorksDW database (or any other database).</span></span>  
  
    ```  
    USE [database name];  
    GO  
    IF OBJECT_ID ([dbo].[NewSalesData]) IS NOT NULL   
        DROP TABLE [dbo].[NewSalesData];  
    GO  
    CREATE TABLE [dbo].[NewSalesData]([Series] [nvarchar](255) NULL,  
    [NewDate] [datetime] NULL,  
    [NewQty] [float] NULL,  
    [NewAmount] [money] NULL) ON [PRIMARY]  
  
    GO  
    ```  
  
2.  <span data-ttu-id="01430-125">Insérez les nouvelles valeurs à l'aide du script suivant.</span><span class="sxs-lookup"><span data-stu-id="01430-125">Insert the new values using the following script.</span></span>  
  
    ```  
    INSERT INTO [NewSalesData]  
    (Series,NewDate,NewQty,NewAmount)  
    VALUES('T1000 Pacific', '7/25/08', 55, '$130,170.22'),  
    ('T1000 Pacific', '8/25/08', 50, '$114,435.36 '),  
    ('T1000 Pacific', '9/25/08', 50, '$117,296.24 '),  
    ('T1000 Europe', '7/25/08', 37, '$88,210.00 '),  
    ('T1000 Europe', '8/25/08', 41, '$97,746.00 '),  
    ('T1000 Europe', '9/25/08', 37, '$88,210.00 '),  
    ('T1000 North America', '7/25/08', 69, '$164,500.00 '),  
    ('T1000 North America', '8/25/08', 66, '$157,348.00 '),  
    ('T1000 North America', '9/25/08', 58, '$138,276.00 '),  
    ('M200 Pacific', '7/25/08', 65, '$149,824.35'),  
    ('M200 Pacific', '8/25/08', 54,  '$124,619.46'),  
    ('M200 Pacific', '9/25/08', 61, '$141,143.39'),  
    ('M200 Europe', '7/25/08', 75, '$173,026.00'),  
    ('M200 Europe', '8/25/08', 76, '$175,212.00'),  
    ('M200 Europe', '9/25/08', 84, '$193,731.00'),  
    ('M200 North America', '7/25/08', 94, '$216,916.00'),  
    ('M200 North America', '8/25/08', 94, '$216,891.00'),  
    ('M200 North America', '9/25/08', 91,'$209,943.00');  
    ```  
  
    > [!WARNING]  
    >  <span data-ttu-id="01430-126">Les guillemets sont utilisés avec les valeurs monétaires pour empêcher les problèmes liés au séparateur à virgule et au symbole monétaire.</span><span class="sxs-lookup"><span data-stu-id="01430-126">The quotation marks are used with the currency values to prevent problems with the comma separator and the currency symbol.</span></span> <span data-ttu-id="01430-127">Vous pouvez également transmettre les valeurs monétaires dans ce format : `130170.22`</span><span class="sxs-lookup"><span data-stu-id="01430-127">You could also pass in the currency values in this format: `130170.22`</span></span>  
    >   
    >  <span data-ttu-id="01430-128">Notez que les dates utilisées dans l'exemple de base de données ont changé pour cette version.</span><span class="sxs-lookup"><span data-stu-id="01430-128">Note that the dates used in the sample database have changed for this release.</span></span> <span data-ttu-id="01430-129">Si vous utilisez une version antérieure d'AdventureWorks, vous devrez peut-être ajuster les dates insérées en conséquence.</span><span class="sxs-lookup"><span data-stu-id="01430-129">If you are using an earlier edition of AdventureWorks, you might need to adjust the inserted dates accordingly.</span></span>  
  
###  <a name="create-a-data-source-view-using-the-new-sales-data"></a><a name="bkmk_newReplaceData"></a><span data-ttu-id="01430-130">Créer une vue de source de données à l’aide des nouvelles données de ventes</span><span class="sxs-lookup"><span data-stu-id="01430-130">Create a data source view using the new sales data</span></span>  
  
1.  <span data-ttu-id="01430-131">Dans l' **Explorateur de solutions**, cliquez avec le bouton droit sur **Vues des sources de données**, puis sélectionnez **Nouvelle vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="01430-131">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="01430-132">Dans l'Assistant Vue de source de données, faites les sélections suivantes :</span><span class="sxs-lookup"><span data-stu-id="01430-132">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="01430-133">**Source de données**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01430-133">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="01430-134">**Sélectionner des tables et des vues**: sélectionnez la table que vous venez de créer, NewSalesData.</span><span class="sxs-lookup"><span data-stu-id="01430-134">**Select Tables and Views**: Select the table that you just created, NewSalesData.</span></span>  
  
3.  <span data-ttu-id="01430-135">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="01430-135">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="01430-136">Dans l’aire de conception de la vue de source de données, cliquez avec le bouton droit sur NewSalesData, puis sélectionnez **Explorer les données** pour vérifier les données.</span><span class="sxs-lookup"><span data-stu-id="01430-136">In the Data Source View design surface, right-click NewSalesData, and then select **Explore Data** to verify the data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="01430-137">Vous allez utiliser ces données uniquement pour la prédiction, donc il n'est pas important que ces données soient incomplètes.</span><span class="sxs-lookup"><span data-stu-id="01430-137">You will use this data for prediction only, so it does not matter that the data is incomplete.</span></span>  
  
##  <a name="creating-the-data-for-the-cross-prediction-model"></a><a name="bkmk_CrossData2"></a><span data-ttu-id="01430-138">Création des données pour le modèle de prédiction croisée</span><span class="sxs-lookup"><span data-stu-id="01430-138">Creating the Data for the Cross-Prediction Model</span></span>  
 <span data-ttu-id="01430-139">Les données utilisées dans le modèle de prévision d'origine ont déjà été groupées, dans une certaine mesure, par la vue vTimeSeries qui a réduit plusieurs modèles de vélos en un plus petit nombre de catégories et fusionné les résultats de différents pays en régions.</span><span class="sxs-lookup"><span data-stu-id="01430-139">The data that was used in the original forecasting model was already grouped somewhat by the view vTimeSeries, which collapsed several bike models into a smaller number of categories, and merged results from individual countries into regions.</span></span> <span data-ttu-id="01430-140">Pour créer un modèle qui peut être utilisé pour les projections internationales, vous allez créer des agrégations simples supplémentaires directement dans le Concepteur de vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="01430-140">To create a model that can be used for world-wide projections, you will create some additional simple aggregations directly in the Data Source View Designer.</span></span> <span data-ttu-id="01430-141">La nouvelle vue de source de données ne contiendra qu'une somme et une moyenne des ventes de tous les produits pour toutes les régions.</span><span class="sxs-lookup"><span data-stu-id="01430-141">The new data source view will contain just a sum and an average of the sales of all products for all regions.</span></span>  
  
 <span data-ttu-id="01430-142">Après avoir créé la source de données utilisée pour le modèle, vous devez créer une nouvelle vue de source de données pour la prédiction.</span><span class="sxs-lookup"><span data-stu-id="01430-142">After you have created the data source used for the model, you must create a new data source view to use for prediction.</span></span> <span data-ttu-id="01430-143">Par exemple, si vous souhaitez prédire des ventes pour l'Europe à l'aide du nouveau modèle international, vous devez charger uniquement les données de la région Europe.</span><span class="sxs-lookup"><span data-stu-id="01430-143">For example, if you want to predict sales for Europe using the new worldwide model, you must feed in data for the Europe region only.</span></span> <span data-ttu-id="01430-144">Vous allez définir une nouvelle vue de source de données qui filtre les données d'origine et modifier la condition de filtre pour chaque ensemble de requêtes de prédiction.</span><span class="sxs-lookup"><span data-stu-id="01430-144">So you will set up a new data source view that filters the original data, and change the filter condition for each set of prediction queries.</span></span>  
  
#### <a name="to-create-the-model-data-using-a-custom-data-source-view"></a><span data-ttu-id="01430-145">Pour créer les données de modèle à l'aide d'une vue de source de données personnalisée</span><span class="sxs-lookup"><span data-stu-id="01430-145">To create the model data using a custom data source view</span></span>  
  
1.  <span data-ttu-id="01430-146">Dans l' **Explorateur de solutions**, cliquez avec le bouton droit sur **Vues des sources de données**, puis sélectionnez **Nouvelle vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="01430-146">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="01430-147">Dans la page d'accueil de l'Assistant, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="01430-147">On the welcome page of the wizard, click **Next**.</span></span>  
  
3.  <span data-ttu-id="01430-148">Dans la page **Sélectionner une source de données** , sélectionnez [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)], puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="01430-148">On the **Select Data Source** page, select [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="01430-149">Dans la page **Sélectionner des tables et des vues**, n’ajoutez pas de tables. cliquez simplement sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="01430-149">In the page, **Select Tables and Views**, do not add any tables-just click **Next**.</span></span>  
  
5.  <span data-ttu-id="01430-150">Dans la page **fin de l’Assistant**, tapez le nom `AllRegions` , puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="01430-150">On the page, **Completing the Wizard**, type the name `AllRegions`, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="01430-151">Ensuite, cliquez avec le bouton droit sur l'aire de conception Vue de source de données vierge, puis sélectionnez **Nouvelle requête nommée**.</span><span class="sxs-lookup"><span data-stu-id="01430-151">Next, right-click the blank data source view design surface, and then select **New Named Query**.</span></span>  
  
7.  <span data-ttu-id="01430-152">Dans la boîte de dialogue **créer une requête nommée** , pour **nom**, type `AllRegions` et pour **Description**, tapez **somme et moyenne des ventes pour tous les modèles et régions**.</span><span class="sxs-lookup"><span data-stu-id="01430-152">In the **Create Named Query** dialog box, for **Name**, type `AllRegions`, and for **Description**, type **Sum and average of sales for all models and regions**.</span></span>  
  
8.  <span data-ttu-id="01430-153">Dans le volet Texte SQL, tapez l'instruction suivante et cliquez sur OK :</span><span class="sxs-lookup"><span data-stu-id="01430-153">In the SQL text pane, type the following statement and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate,   
    SUM([Quantity]) as SumQty, AVG([Quantity]) as AvgQty,  
    SUM([Amount]) AS SumAmt, AVG([Amount]) AS AvgAmt,  
    'All Regions' as [Region]  
    FROM dbo.vTimeSeries   
    GROUP BY ReportingDate  
    ```  
  
9. <span data-ttu-id="01430-154">Cliquez avec le bouton droit sur la `AllRegions` table, puis sélectionnez **Explorer les données**.</span><span class="sxs-lookup"><span data-stu-id="01430-154">Right-click the `AllRegions` table, and then select **Explore Data**.</span></span>  
  
###  <a name="to-create-the-series-data-for-cross-prediction"></a><a name="bkmk_CrossData"></a><span data-ttu-id="01430-155">Pour créer les données de série pour la prédiction croisée</span><span class="sxs-lookup"><span data-stu-id="01430-155">To create the series data for cross-prediction</span></span>  
  
1.  <span data-ttu-id="01430-156">Dans l' **Explorateur de solutions**, cliquez avec le bouton droit sur **Vues des sources de données**, puis sélectionnez **Nouvelle vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="01430-156">In **Solution Explorer**, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="01430-157">Dans l'Assistant Vue de source de données, faites les sélections suivantes :</span><span class="sxs-lookup"><span data-stu-id="01430-157">In the Data Source View wizard, make the following selections:</span></span>  
  
     <span data-ttu-id="01430-158">**Source de données**:[!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01430-158">**Data Source**: [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]</span></span>  
  
     <span data-ttu-id="01430-159">**Sélectionner des tables et des vues**: ne sélectionnez pas de tables</span><span class="sxs-lookup"><span data-stu-id="01430-159">**Select Tables and Views**: Do not select any tables</span></span>  
  
     <span data-ttu-id="01430-160">**Nom** : `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="01430-160">**Name**: `T1000 Pacific Region`</span></span>  
  
3.  <span data-ttu-id="01430-161">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="01430-161">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="01430-162">Cliquez avec le bouton droit sur l'aire de conception vide pour **1000 Pacific Region.dsv**, puis sélectionnez **Nouvelle requête nommée**.</span><span class="sxs-lookup"><span data-stu-id="01430-162">Right-click the empty design surface for **T1000 Pacific Region.dsv**, and then select **New Named Query**.</span></span>  
  
     <span data-ttu-id="01430-163">La boîte de dialogue **Créer une requête nommée** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="01430-163">The **Create Named Query** dialog box appears.</span></span> <span data-ttu-id="01430-164">Retapez le nom, puis ajoutez la description suivante :</span><span class="sxs-lookup"><span data-stu-id="01430-164">Retype the name, and then add the following description:</span></span>  
  
     <span data-ttu-id="01430-165">**Nom** : `T1000 Pacific Region`</span><span class="sxs-lookup"><span data-stu-id="01430-165">**Name**: `T1000 Pacific Region`</span></span>  
  
     <span data-ttu-id="01430-166">**Description**: **Filtrer `vTimeSeries` par région et par modèle**</span><span class="sxs-lookup"><span data-stu-id="01430-166">**Description**: **Filter`vTimeSeries`by region and model**</span></span>  
  
5.  <span data-ttu-id="01430-167">Dans le volet Texte, tapez la requête suivante et cliquez sur OK :</span><span class="sxs-lookup"><span data-stu-id="01430-167">In the text pane, type the following query, and then click OK:</span></span>  
  
    ```  
    SELECT ReportingDate, ModelRegion, Quantity, Amount  
    FROM dbo.vTimeSeries  
    WHERE (ModelRegion = N'T1000 Pacific')  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="01430-168">Puisque vous devez créer des prédictions séparément pour chaque série, vous pouvez copier le texte de la requête et l'enregistrer dans un fichier texte afin de le réutiliser pour les autres séries de données.</span><span class="sxs-lookup"><span data-stu-id="01430-168">Since you will need to create predictions for each series separately, you might want to copy the query text and save it to a text file so that you can re-use it for the other data series.</span></span>  
  
6.  <span data-ttu-id="01430-169">Dans l’aire de conception de la vue de source de données, cliquez avec le bouton droit sur T1000 Pacific, puis sélectionnez **Explorer les données** pour vérifier que les données sont filtrées correctement.</span><span class="sxs-lookup"><span data-stu-id="01430-169">In the Data Source View design surface, right-click T1000 Pacific, and then select **Explore Data** to verify that the data is filtered correctly.</span></span>  
  
     <span data-ttu-id="01430-170">Vous utiliserez ces données comme entrée au modèle lors de la création des requêtes de prédiction croisée.</span><span class="sxs-lookup"><span data-stu-id="01430-170">You will use this data as the input to the model when creating cross-prediction queries.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="01430-171">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="01430-171">Next Task in Lesson</span></span>  
 [<span data-ttu-id="01430-172">Prédictions de série chronologique utilisant des données mises à jour &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="01430-172">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="01430-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01430-173">See Also</span></span>  
 <span data-ttu-id="01430-174">[Algorithme MTS (Microsoft Time Series)](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="01430-174">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 <span data-ttu-id="01430-175">[Référence technique de l’algorithme MTS (Microsoft Time Series)](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="01430-175">[Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="01430-176">Vues de sources de données dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="01430-176">Data Source Views in Multidimensional Models</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models)  
  
  
