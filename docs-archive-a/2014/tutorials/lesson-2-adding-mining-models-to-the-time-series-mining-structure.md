---
title: 'Leçon 2 : ajout de modèles d’exploration de données à la structure d’exploration de données de série chronologique | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75c2a74b-21ce-44fb-a26b-68be4c685c12
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ae0bb91fafb53c0c077a4e0d82558b550d0e6070
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600426"
---
# <a name="lesson-2-adding-mining-models-to-the-time-series-mining-structure"></a><span data-ttu-id="9f145-102">Leçon 2 : Ajout de modèles d’exploration de données à la structure d’exploration de données de série chronologique</span><span class="sxs-lookup"><span data-stu-id="9f145-102">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>
  <span data-ttu-id="9f145-103">Dans cette leçon, vous allez ajouter un nouveau modèle d’exploration de données à la structure d’exploration de données que vous venez de créer dans la [leçon 1 : création d’un modèle](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md)d’exploration de données de série chronologique et d’une structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="9f145-103">In this lesson, you will add a new mining model to the mining structure that you just created in [Lesson 1: Creating a Time Series Mining Model and Mining Structure](../../2014/tutorials/lesson-1-creating-a-time-series-mining-model-and-mining-structure.md).</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="9f145-104">Instruction ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="9f145-104">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="9f145-105">Afin d’ajouter un nouveau modèle d’exploration de données à une structure d’exploration de données existante, vous utilisez l’instruction [ALTER Mining structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="9f145-105">In order to add a new mining model to an existing mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="9f145-106">Le code de l’instruction peut être divisé en plusieurs parties :</span><span class="sxs-lookup"><span data-stu-id="9f145-106">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="9f145-107">Identification de la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="9f145-107">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="9f145-108">Attribution d'un nom au modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="9f145-108">Naming the mining model</span></span>  
  
-   <span data-ttu-id="9f145-109">Définition de la colonne clé</span><span class="sxs-lookup"><span data-stu-id="9f145-109">Defining the key column</span></span>  
  
-   <span data-ttu-id="9f145-110">Définition des colonnes prédictibles</span><span class="sxs-lookup"><span data-stu-id="9f145-110">Defining the predictable columns</span></span>  
  
-   <span data-ttu-id="9f145-111">Spécification des modifications d'algorithme et de paramètre</span><span class="sxs-lookup"><span data-stu-id="9f145-111">Specifying the algorithm and any parameter changes</span></span>  
  
 <span data-ttu-id="9f145-112">L'exemple générique suivant utilise l'instruction ALTER MINING STRUCTURE :</span><span class="sxs-lookup"><span data-stu-id="9f145-112">The following is a generic example of the ALTER MINING STRUCTURE statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
   ([<key columns>],  
    <mining model columns>  
   )  
USING <algorithm name>([<algorithm parameters>])  
[WITH DRILLTHROUGH]  
```  
  
 <span data-ttu-id="9f145-113">La première ligne du code identifie la structure d'exploration de données existante à laquelle les modèles d'exploration de données seront ajoutés :</span><span class="sxs-lookup"><span data-stu-id="9f145-113">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="9f145-114">La ligne suivante du code désigne le modèle d'exploration de données qui sera ajouté à la structure d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="9f145-114">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="9f145-115">Pour plus d’informations sur l’attribution d’un nom à un objet dans DMX, consultez [identificateurs &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="9f145-115">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="9f145-116">Les lignes suivantes du code définissent les colonnes de la structure d'exploration de données employées dans le modèle d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="9f145-116">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key columns>],  
<mining model columns>  
```  
  
 <span data-ttu-id="9f145-117">Vous pouvez uniquement utiliser les colonnes déjà existantes dans la structure d'exploration de données ; de même, la première colonne de la liste doit correspondre à la colonne clé issue de la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="9f145-117">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="9f145-118">Les lignes suivantes du code définissent l'algorithme d'exploration de données qui génère le modèle d'exploration de données et les paramètres d'algorithme que vous pouvez définir sur l'algorithme, puis indiquent si vous pouvez effectuer une extraction du modèle d'exploration de données vers des données détaillées de la vue dans les cas d'apprentissage :</span><span class="sxs-lookup"><span data-stu-id="9f145-118">The next lines of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm, and specify whether you can drill down from the mining model into view detailed data in the training cases:</span></span>  
  
```  
USING <algorithm name>([<algorithm parameters>])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="9f145-119">Pour plus d’informations sur les paramètres d’algorithme que vous pouvez ajuster, consultez informations techniques de référence sur l' [algorithme MTS (Microsoft Time Series](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)).</span><span class="sxs-lookup"><span data-stu-id="9f145-119">For more information about the algorithm parameters that you can adjust, see [Microsoft Time Series Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="9f145-120">Vous pouvez spécifier l'utilisation d'une colonne du modèle d'exploration de données à des fins de prédiction en utilisant la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="9f145-120">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="9f145-121">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="9f145-121">Lesson Tasks</span></span>  
 <span data-ttu-id="9f145-122">Dans cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="9f145-122">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="9f145-123">ajouter un nouveau modèle d'exploration de données de série chronologique à la structure ;</span><span class="sxs-lookup"><span data-stu-id="9f145-123">Add a new time series mining model to the structure.</span></span>  
  
-   <span data-ttu-id="9f145-124">modifier les paramètres d'algorithme pour utiliser une autre méthode d'analyse et de prédiction.</span><span class="sxs-lookup"><span data-stu-id="9f145-124">Change the algorithm parameters to use a different method of analysis and prediction</span></span>  
  
## <a name="adding-an-arima-time-series-model-to-the-structure"></a><span data-ttu-id="9f145-125">Ajout d'un modèle de série chronologique ARIMA à la structure</span><span class="sxs-lookup"><span data-stu-id="9f145-125">Adding an ARIMA Time Series Model to the Structure</span></span>  
 <span data-ttu-id="9f145-126">La première étape consiste à ajouter un nouveau modèle d'exploration de données de prévision à la structure existante.</span><span class="sxs-lookup"><span data-stu-id="9f145-126">The first step is to add a new forecasting mining model to the existing structure.</span></span> <span data-ttu-id="9f145-127">Par défaut, l'algorithme MTS ([!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series) crée des modèles d'exploration de données de série chronologique en utilisant deux algorithmes, ARIMA et ARTXP, puis en fusionnant les résultats.</span><span class="sxs-lookup"><span data-stu-id="9f145-127">By default, the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm creates time series mining models by using two algorithms, ARIMA and ARTXP, and blending the results.</span></span> <span data-ttu-id="9f145-128">Toutefois, vous pouvez spécifier un seul algorithme à utiliser ou spécifier la fusion exacte des algorithmes.</span><span class="sxs-lookup"><span data-stu-id="9f145-128">However, you can specify a single algorithm to use, or you can specify the exact blend of algorithms.</span></span> <span data-ttu-id="9f145-129">Au cours de cette étape, vous allez ajouter un nouveau modèle qui utilise uniquement l'algorithme ARIMA.</span><span class="sxs-lookup"><span data-stu-id="9f145-129">In this step, you will add a new model that uses only the ARIMA algorithm.</span></span> <span data-ttu-id="9f145-130">Cet algorithme est optimisé pour les prédictions à long terme.</span><span class="sxs-lookup"><span data-stu-id="9f145-130">This algorithm is optimized for long-term prediction.</span></span>  
  
#### <a name="to-add-an-arima-time-series-mining-model"></a><span data-ttu-id="9f145-131">Pour ajouter un modèle d'exploration de données de série chronologique ARIMA</span><span class="sxs-lookup"><span data-stu-id="9f145-131">To add an ARIMA time series mining model</span></span>  
  
1.  <span data-ttu-id="9f145-132">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX** pour ouvrir l’éditeur de requête et une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="9f145-132">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="9f145-133">Copiez l'exemple générique de l'instruction ALTER MINING STRUCTURE dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="9f145-133">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="9f145-134">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="9f145-134">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="9f145-135">par :</span><span class="sxs-lookup"><span data-stu-id="9f145-135">with:</span></span>  
  
    ```  
    [Forecasting_MIXED_Structure]  
    ```  
  
4.  <span data-ttu-id="9f145-136">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="9f145-136">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="9f145-137">par :</span><span class="sxs-lookup"><span data-stu-id="9f145-137">with:</span></span>  
  
    ```  
    Forecasting_ARIMA  
    ```  
  
5.  <span data-ttu-id="9f145-138">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="9f145-138">Replace the following:</span></span>  
  
    ```  
    <key columns>,  
    ```  
  
     <span data-ttu-id="9f145-139">par :</span><span class="sxs-lookup"><span data-stu-id="9f145-139">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]  
    ```  
  
     <span data-ttu-id="9f145-140">Notez que vous n'avez pas besoin de répéter les informations relatives au type de date ou de contenu que vous avez fournies dans l'instruction CREATE MINING MODEL, parce que ces informations sont déjà stockées dans la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="9f145-140">Note that you do not need to repeat any of the date type or content type information that you provided in the CREATE MINING MODEL statement, because this information is already stored in the mining structure.</span></span>  
  
6.  <span data-ttu-id="9f145-141">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="9f145-141">Replace the following:</span></span>  
  
    ```  
    <mining model columns>  
    ```  
  
     <span data-ttu-id="9f145-142">par :</span><span class="sxs-lookup"><span data-stu-id="9f145-142">with:</span></span>  
  
    ```  
    ([Quantity] PREDICT,  
    [Amount] PREDICT  
    )  
    ```  
  
7.  <span data-ttu-id="9f145-143">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="9f145-143">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([<algorithm parameters>])   
    [WITH DRILLTHROUGH]  
    ```  
  
     <span data-ttu-id="9f145-144">par :</span><span class="sxs-lookup"><span data-stu-id="9f145-144">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="9f145-145">L'instruction obtenue doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="9f145-145">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARIMA]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARIMA')  
    WITH DRILLTHROUGH  
    ```  
  
8.  <span data-ttu-id="9f145-146">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="9f145-146">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
9. <span data-ttu-id="9f145-147">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Forecasting_ARIMA.dmx` .</span><span class="sxs-lookup"><span data-stu-id="9f145-147">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARIMA.dmx`.</span></span>  
  
10. <span data-ttu-id="9f145-148">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="9f145-148">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-artxp-time-series-model-to-the-structure"></a><span data-ttu-id="9f145-149">Ajout d'un modèle de série chronologique ARTXP à la structure</span><span class="sxs-lookup"><span data-stu-id="9f145-149">Adding an ARTXP Time Series Model to the Structure</span></span>  
 <span data-ttu-id="9f145-150">L'algorithme ARTXP était l'algorithme de série chronologique par défaut dans SQL Server 2005 et il est optimisé pour des prédictions à court terme.</span><span class="sxs-lookup"><span data-stu-id="9f145-150">The ARTXP algorithm was the default time series algorithm in SQL Server 2005 and is optimized for short-term prediction.</span></span> <span data-ttu-id="9f145-151">Pour comparer des prédictions à l'aide des trois algorithmes de série chronologique, vous allez ajouter un autre modèle basé sur l'algorithme ARTXP.</span><span class="sxs-lookup"><span data-stu-id="9f145-151">To compare predictions by using all three time series algorithms, you will add one more model that is based on the ARTXP algorithm.</span></span>  
  
#### <a name="to-add-an-artxp-time-series-mining-model"></a><span data-ttu-id="9f145-152">Pour ajouter un modèle d'exploration de données de série chronologique ARTXP</span><span class="sxs-lookup"><span data-stu-id="9f145-152">To add an ARTXP time series mining model</span></span>  
  
1.  <span data-ttu-id="9f145-153">Copiez le code suivant dans une fenêtre de requête vide.</span><span class="sxs-lookup"><span data-stu-id="9f145-153">Copy the following code into a blank query window.</span></span>  
  
     <span data-ttu-id="9f145-154">Notez que vous n'avez pas besoin d'apporter de modifications  l'exception du nom du nouveau modèle d'exploration de données et de la valeur du paramètre FORECAST_METHOD.</span><span class="sxs-lookup"><span data-stu-id="9f145-154">Note that you do not need to change anything except the name of the new mining model, and the value of the FORECAST_METHOD parameter.</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Forecasting_MIXED_Structure]  
    ADD MINING MODEL [Forecasting_ARTXP]  
       (  
       ([ReportingDate],  
        [ModelRegion],  
        ([Quantity] PREDICT,  
        [Amount] PREDICT  
       )   
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = .08, FORECAST_METHOD = 'ARTXP')  
    WITH DRILLTHROUGH  
    ```  
  
2.  <span data-ttu-id="9f145-155">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="9f145-155">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
3.  <span data-ttu-id="9f145-156">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Forecasting_ARTXP.dmx` .</span><span class="sxs-lookup"><span data-stu-id="9f145-156">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_ARTXP.dmx`.</span></span>  
  
4.  <span data-ttu-id="9f145-157">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="9f145-157">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="9f145-158">Dans la leçon suivante, vous allez traiter tous les modèles et la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="9f145-158">In the next lesson, you will process all of the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="9f145-159">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="9f145-159">Next Lesson</span></span>  
 [<span data-ttu-id="9f145-160">Leçon 3 : Traitement de la structure et des modèles de série chronologique</span><span class="sxs-lookup"><span data-stu-id="9f145-160">Lesson 3: Processing the Time Series Structure and Models</span></span>](../../2014/tutorials/lesson-3-processing-the-time-series-structure-and-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="9f145-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f145-161">See Also</span></span>  
 <span data-ttu-id="9f145-162">[Algorithme MTS (Microsoft Time Series)](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="9f145-162">[Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md) </span></span>  
 [<span data-ttu-id="9f145-163">Informations techniques de référence sur l’algorithme MTS (Microsoft Time Series)</span><span class="sxs-lookup"><span data-stu-id="9f145-163">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
