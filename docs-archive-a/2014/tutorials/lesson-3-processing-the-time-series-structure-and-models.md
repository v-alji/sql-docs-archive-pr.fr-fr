---
title: 'Leçon 3 : traitement de la structure et des modèles de série chronologique | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 16e27b57-eae1-47a7-a02c-47b6ed487d87
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 493d27c9836eb765c655eba5bbb004e4d48cde40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702200"
---
# <a name="lesson-3-processing-the-time-series-structure-and-models"></a><span data-ttu-id="67f3b-102">Leçon 3 : Traitement de la structure et des modèles de série chronologique</span><span class="sxs-lookup"><span data-stu-id="67f3b-102">Lesson 3: Processing the Time Series Structure and Models</span></span>
  <span data-ttu-id="67f3b-103">Dans cette leçon, vous allez utiliser l’instruction [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) pour traiter les structures d’exploration de données de série chronologique et les modèles d’exploration de données que vous avez créés.</span><span class="sxs-lookup"><span data-stu-id="67f3b-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement to process the time series mining structures and mining models that you created.</span></span>  
  
 <span data-ttu-id="67f3b-104">Lorsque vous traitez une structure d'exploration de données, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] lit les données sources et génère les structures qui soutiennent les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="67f3b-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="67f3b-105">Vous devez toujours traiter un modèle et une structure d'exploration de données au moment où vous les créez.</span><span class="sxs-lookup"><span data-stu-id="67f3b-105">You always have to process a mining model and structure when you first create it.</span></span> <span data-ttu-id="67f3b-106">Si vous spécifiez la structure d'exploration de données lors de l'utilisation de l'instruction INSERT INTO, l'instruction traite la structure et tous ses modèles d'exploration de données associés.</span><span class="sxs-lookup"><span data-stu-id="67f3b-106">If you specify the mining structure when using INSERT INTO, the statement processes the mining structure and all its associated mining models.</span></span>  
  
 <span data-ttu-id="67f3b-107">Lorsque vous ajoutez un modèle d'exploration de données à une structure d'exploration de données déjà traitée, vous pouvez utiliser l'instruction `INSERT INTO MINING MODEL` pour traiter uniquement le nouveau modèle d'exploration de données à l'aide des données existantes.</span><span class="sxs-lookup"><span data-stu-id="67f3b-107">When you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to process just the new mining model by using the existing data.</span></span>  
  
 <span data-ttu-id="67f3b-108">Pour plus d’informations sur le traitement des modèles d’exploration de données, consultez [exigences et considérations relatives au traitement &#40;&#41;d’exploration de données ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="67f3b-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="67f3b-109">Instruction INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="67f3b-109">INSERT INTO Statement</span></span>  
 <span data-ttu-id="67f3b-110">Pour effectuer l’apprentissage de la structure d’exploration de données de série chronologique et de tous ses modèles d’exploration de données associés, utilisez l’instruction [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="67f3b-110">In order to train the time series mining structure and all its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="67f3b-111">Le code de cette instruction peut être divisé selon les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="67f3b-111">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="67f3b-112">Identification de la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="67f3b-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="67f3b-113">Liste des colonnes de la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="67f3b-113">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="67f3b-114">Définition des données d'apprentissage</span><span class="sxs-lookup"><span data-stu-id="67f3b-114">Defining the training data</span></span>  
  
 <span data-ttu-id="67f3b-115">L'exemple générique suivant utilise l'instruction `INSERT INTO` :</span><span class="sxs-lookup"><span data-stu-id="67f3b-115">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="67f3b-116">La première ligne du code identifie la structure d'exploration de données à apprendre :</span><span class="sxs-lookup"><span data-stu-id="67f3b-116">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="67f3b-117">Les lignes suivantes du code précisent les colonnes définies par la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="67f3b-117">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="67f3b-118">Vous devez répertorier chaque colonne dans la structure d'exploration de données et chaque colonne doit mapper une colonne figurant dans les données de la requête source.</span><span class="sxs-lookup"><span data-stu-id="67f3b-118">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="67f3b-119">Les dernières lignes du code précisent les données à utiliser pour l'apprentissage de la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="67f3b-119">The final lines of the code define the data that will be used to train the mining structure.</span></span>  
  
```  
OPENQUERY (<source data definition>)  
```  
  
 <span data-ttu-id="67f3b-120">Dans cette leçon, vous allez utiliser l'instruction `OPENQUERY` pour définir les données sources.</span><span class="sxs-lookup"><span data-stu-id="67f3b-120">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="67f3b-121">Pour plus d’informations sur les autres méthodes de définition d’une requête sur les données sources, consultez [&#60;&#62;de requête de données source ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="67f3b-121">For more information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="67f3b-122">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="67f3b-122">Lesson Tasks</span></span>  
 <span data-ttu-id="67f3b-123">Au cours de cette leçon, vous allez effectuer la tâche suivante :</span><span class="sxs-lookup"><span data-stu-id="67f3b-123">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="67f3b-124">traiter la structure d'exploration de données Forecasting_MIXED_Structure ;</span><span class="sxs-lookup"><span data-stu-id="67f3b-124">Process the mining structure Forecasting_MIXED_Structure</span></span>  
  
-   <span data-ttu-id="67f3b-125">traiter les modèles d'exploration de données associés Forecasting_MIXED, Forecasting_ARIMA et Forecasting_ARTXP.</span><span class="sxs-lookup"><span data-stu-id="67f3b-125">Process the related mining models Forecasting_MIXED, Forecasting_ARIMA, and Forecasting_ARTXP</span></span>  
  
## <a name="processing-the-time-series-mining-structure"></a><span data-ttu-id="67f3b-126">Traitement de la structure d'exploration de données de série chronologique</span><span class="sxs-lookup"><span data-stu-id="67f3b-126">Processing the Time Series Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-and-related-mining-models-by-using-insert-into"></a><span data-ttu-id="67f3b-127">Pour traiter la structure d'exploration de données et les modèles associés à l'aide d'une instruction INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="67f3b-127">To process the mining structure and related mining models by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="67f3b-128">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="67f3b-128">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="67f3b-129">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="67f3b-129">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="67f3b-130">Copiez l'exemple générique de l'instruction INSERT INTO dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="67f3b-130">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="67f3b-131">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="67f3b-131">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="67f3b-132">par :</span><span class="sxs-lookup"><span data-stu-id="67f3b-132">with:</span></span>  
  
    ```  
    Forecasting_MIXED_Structure  
    ```  
  
4.  <span data-ttu-id="67f3b-133">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="67f3b-133">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="67f3b-134">par :</span><span class="sxs-lookup"><span data-stu-id="67f3b-134">with:</span></span>  
  
    ```  
    [ReportingDate],  
    [ModelRegion]   
    ```  
  
5.  <span data-ttu-id="67f3b-135">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="67f3b-135">Replace the following:</span></span>  
  
    ```  
    OPENQUERY(<source data definition>)  
    ```  
  
     <span data-ttu-id="67f3b-136">par :</span><span class="sxs-lookup"><span data-stu-id="67f3b-136">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2008R2],'SELECT [ReportingDate], [ModelRegion], [Quantity], [Amount]  
    FROM vTimeSeries ORDER BY [ReportingDate]')  
    ```  
  
     <span data-ttu-id="67f3b-137">La requête source fait référence [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] à la source de données définie dans l’exemple de projet IntermediateTutorial.</span><span class="sxs-lookup"><span data-stu-id="67f3b-137">The source query references the  [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the IntermediateTutorial sample project.</span></span> <span data-ttu-id="67f3b-138">Elle utilise cette source de données pour accéder à la vue vTimeSeries.</span><span class="sxs-lookup"><span data-stu-id="67f3b-138">It uses this data source to access the view vTimeSeries.</span></span> <span data-ttu-id="67f3b-139">Cette vue renferme les données sources à utiliser pour l'apprentissage du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="67f3b-139">This view contains the source data that will be used to train the mining model.</span></span> <span data-ttu-id="67f3b-140">Si vous n’êtes pas familiarisé avec ce projet ou ces vues, consultez[leçon 2 : génération d’un scénario de prévision &#40;didacticiel sur l’exploration de données intermédiaire&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="67f3b-140">If you are not familiar with this project or this views, see[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="67f3b-141">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="67f3b-141">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Forecasting_MIXED_Structure]  
    (  
       [ReportingDate],[ModelRegion],[Quantity],[Amount])  
    )  
    OPENQUERY(  
    [Adventure Works DW 2008R2],  
    'SELECT [ReportingDate],[ModelRegion],[Quantity],[Amount] FROM vTimeSeries ORDER BY [ReportingDate]'  
    )   
    ```  
  
6.  <span data-ttu-id="67f3b-142">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="67f3b-142">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="67f3b-143">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `ProcessForecastingAll.dmx` .</span><span class="sxs-lookup"><span data-stu-id="67f3b-143">In the **Save As** dialog box, browse to the appropriate folder, and name the file `ProcessForecastingAll.dmx`.</span></span>  
  
8.  <span data-ttu-id="67f3b-144">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="67f3b-144">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="67f3b-145">Une fois que l'exécution de la requête est terminée, vous pouvez créer des prédictions en utilisant les modèles d'exploration de données traités.</span><span class="sxs-lookup"><span data-stu-id="67f3b-145">After the query has finished running, you can create predictions by using the processed mining models.</span></span> <span data-ttu-id="67f3b-146">Dans la leçon suivante, vous allez créer plusieurs prédictions basées sur les modèles d'exploration de données que vous avez créés.</span><span class="sxs-lookup"><span data-stu-id="67f3b-146">In the next lesson, you will create several predictions based on the mining models that you created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="67f3b-147">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="67f3b-147">Next Lesson</span></span>  
 [<span data-ttu-id="67f3b-148">Leçon 4 : Création de prédictions de série chronologique à l’aide d’extensions DMX</span><span class="sxs-lookup"><span data-stu-id="67f3b-148">Lesson 4: Creating Time Series Predictions Using DMX</span></span>](../../2014/tutorials/lesson-4-creating-time-series-predictions-using-dmx.md)  
  
## <a name="see-also"></a><span data-ttu-id="67f3b-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67f3b-149">See Also</span></span>  
 <span data-ttu-id="67f3b-150">[Exigences et considérations relatives au traitement &#40;l’exploration de données&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="67f3b-150">[Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md) </span></span>  
 <span data-ttu-id="67f3b-151">[&#60;&#62;de requête de données source](/sql/dmx/source-data-query) </span><span class="sxs-lookup"><span data-stu-id="67f3b-151">[&#60;source data query&#62;](/sql/dmx/source-data-query) </span></span>  
 [<span data-ttu-id="67f3b-152">&#41;&#40;DMX OPENQUERY</span><span class="sxs-lookup"><span data-stu-id="67f3b-152">OPENQUERY &#40;DMX&#41;</span></span>](/sql/dmx/source-data-query-openquery)  
  
  
