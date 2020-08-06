---
title: 'Leçon 1 : création d’un modèle et d’une structure d’exploration de données de série chronologique | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b201f2b8-9ab5-425b-9ff3-fe321a60a7b7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2513bc3837dd224f6561eb0015ced538ea3add8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601845"
---
# <a name="lesson-1-creating-a-time-series-mining-model-and-mining-structure"></a><span data-ttu-id="c7f1f-102">Leçon 1 : Création d’une structure d’exploration de données et de modèle d’exploration de données de série chronologique</span><span class="sxs-lookup"><span data-stu-id="c7f1f-102">Lesson 1: Creating a Time Series Mining Model and Mining Structure</span></span>
  <span data-ttu-id="c7f1f-103">Dans cette leçon, vous allez créer un modèle d'exploration de données qui vous permet de prédire des valeurs dans le temps à partir de données historiques.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-103">In this lesson, you will create a mining model that allows you to predict values over time, based on historical data.</span></span> <span data-ttu-id="c7f1f-104">Lorsque vous créez le modèle, la structure sous-jacente est générée automatiquement et peut servir de base pour les modèles d'exploration de données supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-104">When you create the model, the underlying structure will be generated automatically and can be used as the basis for additional mining models.</span></span>  
  
 <span data-ttu-id="c7f1f-105">Cette leçon suppose que vous connaissez les modèles de prévision et les spécifications de l'algorithme MTS (Microsoft Time Series).</span><span class="sxs-lookup"><span data-stu-id="c7f1f-105">This lesson assumes that you are familiar with forecasting models and with the requirements of the Microsoft Time Series algorithm.</span></span> <span data-ttu-id="c7f1f-106">Pour plus d’informations, consultez [Algorithme MTS (Microsoft Time Series)](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="c7f1f-106">For more information, see [Microsoft Time Series Algorithm](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md).</span></span>  
  
## <a name="create-mining-model-statement"></a><span data-ttu-id="c7f1f-107">Instruction CREATE MINING MODEL</span><span class="sxs-lookup"><span data-stu-id="c7f1f-107">CREATE MINING MODEL Statement</span></span>  
 <span data-ttu-id="c7f1f-108">Pour créer un modèle d’exploration de données directement et générer automatiquement la structure d’exploration de données sous-jacente, vous utilisez l’instruction [Create Mining model &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) .</span><span class="sxs-lookup"><span data-stu-id="c7f1f-108">In order to create a mining model directly and automatically generate the underlying mining structure, you use the [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx) statement.</span></span> <span data-ttu-id="c7f1f-109">Le code de l’instruction peut être divisé en plusieurs parties :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="c7f1f-110">Attribution d'un nom au modèle</span><span class="sxs-lookup"><span data-stu-id="c7f1f-110">Naming the model</span></span>  
  
-   <span data-ttu-id="c7f1f-111">Définition de l'horodatage</span><span class="sxs-lookup"><span data-stu-id="c7f1f-111">Defining the time stamp</span></span>  
  
-   <span data-ttu-id="c7f1f-112">Définition de la colonne clé de série facultative</span><span class="sxs-lookup"><span data-stu-id="c7f1f-112">Defining the optional series key column</span></span>  
  
-   <span data-ttu-id="c7f1f-113">Définition des attributs ou de l'attribut prédictible</span><span class="sxs-lookup"><span data-stu-id="c7f1f-113">Defining the predictable attribute or attributes</span></span>  
  
 <span data-ttu-id="c7f1f-114">L'exemple générique suivant utilise l'instruction CREATE MINING MODEL :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-114">The following is a generic example of the CREATE MINING MODEL statement:</span></span>  
  
```  
CREATE MINING MODEL [<Mining Structure Name>]  
(  
   <key columns>,  
   <predictable attribute columns>  
)  
USING <algorithm name>([parameter list])  
WITH DRILLTHROUGH  
```  
  
 <span data-ttu-id="c7f1f-115">La première ligne du code définit le nom du modèle d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-115">The first line of the code defines the name of the mining model:</span></span>  
  
```  
CREATE MINING MODEL [Mining Model Name]  
```  
  
 <span data-ttu-id="c7f1f-116">Le service Analysis Services génère un nom pour la structure sous-jacente en annexant "_structure" au nom du modèle, ce qui garantit l'unicité du nom de la structure dans le nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-116">Analysis Services automatically generates a name for the underlying structure, by appending "_structure" to the model name, which ensures that the structure name is unique from the model name.</span></span> <span data-ttu-id="c7f1f-117">Pour plus d’informations sur l’attribution d’un nom à un objet dans DMX, consultez [identificateurs &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="c7f1f-117">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="c7f1f-118">La ligne suivante du code définit la colonne clé pour le modèle d'exploration de données qui dans le cas d'un modèle de série chronologique identifie de manière unique une étape dans les données sources.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-118">The next line of the code defines the key column for the mining model, which in the case of a time series model uniquely identifies a time step in the source data.</span></span> <span data-ttu-id="c7f1f-119">L’étape de temps est identifiée par les `KEY TIME` Mots clés après le nom de colonne et les types de données.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-119">The time step is identified with the `KEY TIME` keywords after the column name and data types.</span></span> <span data-ttu-id="c7f1f-120">Si le modèle de série chronologique a une clé de série séparée, il est identifié à l'aide du mot clé `KEY`.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-120">If the time series model has a separate series key, it is identified by using the `KEY` keyword.</span></span>  
  
```  
<key columns>  
```  
  
 <span data-ttu-id="c7f1f-121">La ligne suivante du code est utilisée pour définir les colonnes du modèle qui sera prédit.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-121">The next line of the code is used to define the columns in the model that will be predicted.</span></span> <span data-ttu-id="c7f1f-122">Vous pouvez avoir plusieurs attributs prédictibles dans un modèle d'exploration de données unique.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-122">You can have multiple predictable attributes in a single mining model.</span></span> <span data-ttu-id="c7f1f-123">Lorsqu'il y a plusieurs attributs prédictibles, l'algorithme MTS (Microsoft Time Series) génère une analyse séparée pour chaque série :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-123">When there are multiple predictable attributes, the Microsoft Time Series algorithm generates a separate analysis for each series:</span></span>  
  
```  
<predictable attribute columns>  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="c7f1f-124">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="c7f1f-124">Lesson Tasks</span></span>  
 <span data-ttu-id="c7f1f-125">Dans cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-125">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="c7f1f-126">créer une requête vide ;</span><span class="sxs-lookup"><span data-stu-id="c7f1f-126">Create a new blank query</span></span>  
  
-   <span data-ttu-id="c7f1f-127">modifier la requête pour créer le modèle d'exploration de données ;</span><span class="sxs-lookup"><span data-stu-id="c7f1f-127">Alter the query to create the mining model</span></span>  
  
-   <span data-ttu-id="c7f1f-128">Exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="c7f1f-128">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="c7f1f-129">Création de la requête</span><span class="sxs-lookup"><span data-stu-id="c7f1f-129">Creating the Query</span></span>  
 <span data-ttu-id="c7f1f-130">La première étape consiste à se connecter à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et à créer une nouvelle requête DMX dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7f1f-130">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="c7f1f-131">Pour créer une requête DMX dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7f1f-131">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="c7f1f-132">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7f1f-132">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="c7f1f-133">Dans la boîte de dialogue **se connecter au serveur** , pour **type de serveur**, sélectionnez **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-133">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="c7f1f-134">Dans **nom du serveur**, tapez `LocalHost` ou le nom de l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à laquelle vous souhaitez vous connecter pour cette leçon.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-134">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="c7f1f-135">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-135">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="c7f1f-136">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-136">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="c7f1f-137">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-137">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="c7f1f-138">Modification de la requête</span><span class="sxs-lookup"><span data-stu-id="c7f1f-138">Altering the Query</span></span>  
 <span data-ttu-id="c7f1f-139">L'étape suivante consiste à modifier l'instruction CREATE MINING MODEL pour créer le modèle d'exploration de données utilisé pour la prévision ainsi que sa structure d'exploration de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-139">The next step is to modify the CREATE MINING MODEL statement to create the mining model used for forecasting, together with its underlying mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-model-statement"></a><span data-ttu-id="c7f1f-140">Pour personnaliser l'instruction CREATE MINING MODEL</span><span class="sxs-lookup"><span data-stu-id="c7f1f-140">To customize the CREATE MINING MODEL statement</span></span>  
  
1.  <span data-ttu-id="c7f1f-141">Dans l'Éditeur de requête, copiez l'exemple générique de l'instruction CREATE MINING MODEL dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-141">In Query Editor, copy the generic example of the CREATE MINING MODEL statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="c7f1f-142">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-142">Replace the following:</span></span>  
  
    ```  
    [mining model name]   
    ```  
  
     <span data-ttu-id="c7f1f-143">par :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-143">with:</span></span>  
  
    ```  
    [Forecasting_MIXED]  
    ```  
  
3.  <span data-ttu-id="c7f1f-144">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-144">Replace the following:</span></span>  
  
    ```  
    <key columns>  
    ```  
  
     <span data-ttu-id="c7f1f-145">par :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-145">with:</span></span>  
  
    ```  
    [Reporting Date] DATE KEY TIME,  
    [Model Region] TEXT KEY  
    ```  
  
     <span data-ttu-id="c7f1f-146">Le mot clé `TIME KEY` indique que la colonne ReportingDate contient les valeurs de l'étape utilisées pour classer les valeurs.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-146">The `TIME KEY` keyword indicates that the ReportingDate column contains the time step values used to order the values.</span></span> <span data-ttu-id="c7f1f-147">Les étapes peuvent être des dates et des heures, des entiers ou tout type de données classées, à condition que les valeurs soient uniques et les données triées.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-147">Time steps can be dates and times, integers, or any ordered data type, so long as the values are unique and the data is sorted.</span></span>  
  
     <span data-ttu-id="c7f1f-148">Les mots clés `TEXT` et `KEY` indiquent que la colonne ModelRegion contient une clé de série supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-148">The `TEXT` and `KEY` keywords indicate that the ModelRegion column contains an additional series key.</span></span> <span data-ttu-id="c7f1f-149">Vous ne pouvez avoir qu'une seule clé de série, et les valeurs dans la colonne doivent être distinctes.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-149">You can have only one series key, and the values in the column must be distinct.</span></span>  
  
4.  <span data-ttu-id="c7f1f-150">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-150">Replace the following:</span></span>  
  
    ```  
    < predictable attribute columns> )  
    ```  
  
     <span data-ttu-id="c7f1f-151">par :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-151">with:</span></span>  
  
    ```  
    [Quantity] LONG CONTINUOUS PREDICT,  
    [Amount] DOUBLE CONTINUOUS PREDICT  
    )  
    ```  
  
5.  <span data-ttu-id="c7f1f-152">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-152">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>([parameter list])  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="c7f1f-153">par :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-153">with:</span></span>  
  
    ```  
    USING Microsoft_Time_Series(AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="c7f1f-154">Le paramètre d'algorithme, `AUTO_DETECT_PERIODICITY` = 0.8, indique que vous souhaitez que l'algorithme détecte des cycles dans les données.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-154">The algorithm parameter, `AUTO_DETECT_PERIODICITY` = 0.8, indicates that you want the algorithm to detect cycles in the data.</span></span> <span data-ttu-id="c7f1f-155">Définir cette valeur proche de 1 privilégie la découverte de nombreux modèles mais peut ralentir le traitement.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-155">Setting this value closer to 1 favors the discovery of many patterns but can slow processing.</span></span>  
  
     <span data-ttu-id="c7f1f-156">Le paramètre d'algorithme, `FORECAST_METHOD`, indique si vous souhaitez que les données soient analysées à l'aide de ARTXP, ARIMA, ou un mélange des deux.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-156">The algorithm parameter, `FORECAST_METHOD`, indicates whether you want the data to be analyzed using ARTXP, ARIMA, or a mixture of both.</span></span>  
  
     <span data-ttu-id="c7f1f-157">Le mot clé, `WITH DRILLTHROUGH`, spécifie que vous souhaitez consulter des statistiques détaillées dans les données sources une fois le modèle terminé.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-157">The keyword, `WITH DRILLTHROUGH`, specify that you want to be able to view detailed statistics in the source data after the model is complete.</span></span> <span data-ttu-id="c7f1f-158">Vous devez ajouter cette clause pour parcourir le modèle à l'aide de la Visionneuse de l'algorithme MTS (Microsoft Time Series).</span><span class="sxs-lookup"><span data-stu-id="c7f1f-158">You must add this clause if you want to browse the model by using the Microsoft Time Series Viewer.</span></span> <span data-ttu-id="c7f1f-159">Elle n'est pas obligatoire pour la prédiction.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-159">It is not required for prediction.</span></span>  
  
     <span data-ttu-id="c7f1f-160">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING MODEL [Forecasting_MIXED]  
         (  
        [Reporting Date] DATE KEY TIME,  
        [Model Region] TEXT KEY,  
        [Quantity] LONG CONTINUOUS PREDICT,  
        [Amount] DOUBLE CONTINUOUS PREDICT  
        )  
    USING Microsoft_Time_Series (AUTO_DETECT_PERIODICITY = 0.8, FORECAST_METHOD = 'MIXED')  
    WITH DRILLTHROUGH  
  
    ```  
  
6.  <span data-ttu-id="c7f1f-161">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="c7f1f-162">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Forecasting_MIXED.dmx` .</span><span class="sxs-lookup"><span data-stu-id="c7f1f-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Forecasting_MIXED.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="c7f1f-163">Exécution de la requête</span><span class="sxs-lookup"><span data-stu-id="c7f1f-163">Executing the Query</span></span>  
 <span data-ttu-id="c7f1f-164">La dernière étape concerne l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-164">The final step is to execute the query.</span></span> <span data-ttu-id="c7f1f-165">Après sa création et son enregistrement, la requête doit être exécutée pour permettre la création sur le serveur de sa structure d'exploration de données et du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-165">After a query is created and saved, it needs to be executed to create the mining model and its mining structure on the server.</span></span> <span data-ttu-id="c7f1f-166">Pour plus d’informations sur l’exécution de requêtes dans l’éditeur de requête, consultez [moteur de base de données l’éditeur de requête &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="c7f1f-166">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="c7f1f-167">Pour exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="c7f1f-167">To execute the query</span></span>  
  
-   <span data-ttu-id="c7f1f-168">Dans l’éditeur de requête, dans la barre d’outils, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-168">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="c7f1f-169">L’état de la requête s’affiche dans l’onglet **messages** en bas de l’éditeur de requête à la fin de l’exécution de l’instruction.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-169">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="c7f1f-170">Les messages doivent révéler le texte suivant :</span><span class="sxs-lookup"><span data-stu-id="c7f1f-170">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="c7f1f-171">Une nouvelle structure nommée **Forecasting_MIXED_Structure** existe désormais sur le serveur, ainsi que le modèle d’exploration de données associé **Forecasting_MIXED**.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-171">A new structure named **Forecasting_MIXED_Structure** now exists on the server, together with the related mining model **Forecasting_MIXED**.</span></span>  
  
 <span data-ttu-id="c7f1f-172">Dans la leçon suivante, vous allez ajouter un modèle d’exploration de données à la structure d’exploration de données **Forecasting_MIXED** que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="c7f1f-172">In the next lesson, you will add a mining model to the **Forecasting_MIXED** mining structure that you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="c7f1f-173">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="c7f1f-173">Next Lesson</span></span>  
 [<span data-ttu-id="c7f1f-174">Leçon 2 : Ajout de modèles d’exploration de données à la structure d’exploration de données de série chronologique</span><span class="sxs-lookup"><span data-stu-id="c7f1f-174">Lesson 2: Adding Mining Models to the Time Series Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-time-series-mining-structure.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7f1f-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7f1f-175">See Also</span></span>  
 <span data-ttu-id="c7f1f-176">[Contenu du modèle d’exploration de données pour les modèles de série chronologique &#40;Analysis Services d’exploration de données&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c7f1f-176">[Mining Model Content for Time Series Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="c7f1f-177">Informations techniques de référence sur l’algorithme MTS (Microsoft Time Series)</span><span class="sxs-lookup"><span data-stu-id="c7f1f-177">Microsoft Time Series Algorithm Technical Reference</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm-technical-reference.md)  
  
  
