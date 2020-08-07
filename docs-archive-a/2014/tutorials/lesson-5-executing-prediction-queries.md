---
title: 'Leçon 5 : exécution des requêtes de prédiction | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0037bd2f-aa2d-464b-bf86-b0210f0438b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a5f4d6dd79f62541e207df688349f694680e2421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703524"
---
# <a name="lesson-5-executing-prediction-queries"></a><span data-ttu-id="24c84-102">Leçon 5 : Exécution des requêtes de prédiction</span><span class="sxs-lookup"><span data-stu-id="24c84-102">Lesson 5: Executing Prediction Queries</span></span>
  <span data-ttu-id="24c84-103">Dans cette leçon, vous allez utiliser la forme [Select from \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) de l’instruction SELECT pour créer deux types différents de prédictions en fonction du modèle d’arbre de décision que vous avez créé au cours de la [leçon 2 : ajout de modèles d’exploration de données à la structure d’exploration de données d’association](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="24c84-103">In this lesson, you will use the [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement to create two different types of predictions based on the decision tree model you created in [Lesson 2: Adding Mining Models to the Association Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="24c84-104">Ces types de prédiction sont définis ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="24c84-104">These prediction types are defined below.</span></span>  
  
 <span data-ttu-id="24c84-105">Requête singleton</span><span class="sxs-lookup"><span data-stu-id="24c84-105">Singleton Query</span></span>  
 <span data-ttu-id="24c84-106">Utilisez une requête singleton pour fournir les valeurs appropriées lors des prédictions.</span><span class="sxs-lookup"><span data-stu-id="24c84-106">Use a singleton query to provide ad hoc values when making predictions.</span></span> <span data-ttu-id="24c84-107">Par exemple, vous pouvez déterminer si un client est susceptible d'acheter un vélo, en intégrant dans la requête des entrées telles que la distance domicile-travail, le code postal ou le nombre d'enfants du client.</span><span class="sxs-lookup"><span data-stu-id="24c84-107">For example, you can determine whether a single customer is likely to be a bike buyer, by passing inputs to the query such as the commute distance, the area code, or the number of children of the customer.</span></span> <span data-ttu-id="24c84-108">La requête singleton renvoie une valeur qui indique la probabilité que la personne achète un vélo en fonction de ces entrées.</span><span class="sxs-lookup"><span data-stu-id="24c84-108">The singleton query returns a value that indicates how likely the person is to purchase a bicycle based on those inputs.</span></span>  
  
 <span data-ttu-id="24c84-109">Requête par lot</span><span class="sxs-lookup"><span data-stu-id="24c84-109">Batch Query</span></span>  
 <span data-ttu-id="24c84-110">Optez pour une requête par lot si vous souhaitez déterminer qui, dans une liste de clients potentiels, est susceptible d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="24c84-110">Use a batch query to determine who in a table of potential customers is likely to purchase a bicycle.</span></span> <span data-ttu-id="24c84-111">Par exemple, si votre service marketing vous communique une liste de clients et d'attributs de clients, vous pouvez alors procéder à une prédiction par lot pour évaluer qui dans la liste des clients est un acheteur de vélo potentiel.</span><span class="sxs-lookup"><span data-stu-id="24c84-111">For example, if your marketing department provides you with a list of customers and customer attributes, then you can use a batch prediction to determine who from the table is likely to purchase a bicycle.</span></span>  
  
 <span data-ttu-id="24c84-112">La forme [Select from \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) de l’instruction SELECT contient trois parties :</span><span class="sxs-lookup"><span data-stu-id="24c84-112">The [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement contains three parts:</span></span>  
  
-   <span data-ttu-id="24c84-113">Liste des colonnes du modèle d'exploration de données et des fonctions de prédiction retournées dans les résultats.</span><span class="sxs-lookup"><span data-stu-id="24c84-113">A list of the mining model columns and prediction functions that are returned in the results.</span></span> <span data-ttu-id="24c84-114">Ces résultats peuvent également contenir les colonnes d'entrée issues des données sources.</span><span class="sxs-lookup"><span data-stu-id="24c84-114">The results can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="24c84-115">Requête source définissant les données utilisées pour créer une prédiction.</span><span class="sxs-lookup"><span data-stu-id="24c84-115">The source query defining the data that is being used to create a prediction.</span></span> <span data-ttu-id="24c84-116">Par exemple, dans le cadre d'une requête par lot, il peut s'agir d'une liste de clients.</span><span class="sxs-lookup"><span data-stu-id="24c84-116">For example, in a batch query this could be a list of customers.</span></span>  
  
-   <span data-ttu-id="24c84-117">Mappage entre les colonnes du modèle d'exploration de données et les données source.</span><span class="sxs-lookup"><span data-stu-id="24c84-117">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="24c84-118">Si les noms correspondent, vous pouvez alors adopter la syntaxe NATURAL et ignorer les mappages de colonnes.</span><span class="sxs-lookup"><span data-stu-id="24c84-118">If these names match, then you can use NATURAL syntax and leave out the column mappings.</span></span>  
  
 <span data-ttu-id="24c84-119">Vous pouvez davantage affiner la requête à l'aide de fonctions de prédiction.</span><span class="sxs-lookup"><span data-stu-id="24c84-119">You can further enhance the query by using prediction functions.</span></span> <span data-ttu-id="24c84-120">Les fonctions de prédiction fournissent des informations supplémentaires, notamment la probabilité d'une prédiction, et offrent une prise en charge de la prédiction dans le dataset d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="24c84-120">Prediction functions provide additional information, such as the probability of a prediction occurring, and provide support for the prediction in the training dataset.</span></span> <span data-ttu-id="24c84-121">Pour plus d’informations sur les fonctions de prédiction, consultez [fonctions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="24c84-121">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="24c84-122">Les prédictions de ce didacticiel sont fondées sur la table ProspectiveBuyer de l'exemple de base de données [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24c84-122">The predictions in this tutorial are based on the ProspectiveBuyer table in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database.</span></span> <span data-ttu-id="24c84-123">La table ProspectiveBuyer renferme une liste de clients potentiels et de leurs caractéristiques associées.</span><span class="sxs-lookup"><span data-stu-id="24c84-123">The ProspectiveBuyer table contains a list of potential customers and their associated characteristics.</span></span> <span data-ttu-id="24c84-124">Les clients de cette table sont indépendants des clients avec lesquels le modèle d'exploration de données d'arbre de décision a été créé.</span><span class="sxs-lookup"><span data-stu-id="24c84-124">The customers in this table are independent of the customers that were used to create the decision tree mining model.</span></span>  
  
 <span data-ttu-id="24c84-125">Vous pouvez également créer des prédictions à l'aide du générateur de requêtes de prédiction disponible dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24c84-125">You can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="24c84-126">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="24c84-126">Lesson Tasks</span></span>  
 <span data-ttu-id="24c84-127">Dans cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="24c84-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="24c84-128">Créez une requête singleton pour déterminer si un client donné est susceptible d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="24c84-128">Create a singleton query to determine whether a specific customer is likely to purchase a bicycle.</span></span>  
  
-   <span data-ttu-id="24c84-129">Créez une requête par lot pour déterminer qui, dans une liste de clients potentiels, est susceptible d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="24c84-129">Create a batch query to determine which customers, listed in a table of customers, are likely to purchase a bicycle.</span></span>  
  
## <a name="singleton-query"></a><span data-ttu-id="24c84-130">Requête singleton</span><span class="sxs-lookup"><span data-stu-id="24c84-130">Singleton Query</span></span>  
 <span data-ttu-id="24c84-131">La première étape consiste à utiliser le [modèle SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) dans une requête de prédiction Singleton.</span><span class="sxs-lookup"><span data-stu-id="24c84-131">The first step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a singleton prediction query.</span></span> <span data-ttu-id="24c84-132">L'exemple générique suivant utilise l'instruction singleton :</span><span class="sxs-lookup"><span data-stu-id="24c84-132">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
```  
  
 <span data-ttu-id="24c84-133">La première ligne du code définit les colonnes du modèle d'exploration de données que doit retourner la requête et spécifie le nom du modèle d'exploration de données utilisé pour générer la prédiction :</span><span class="sxs-lookup"><span data-stu-id="24c84-133">The first line of the code defines the columns from the mining model that the query should return, and specifies the mining model that is used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
```  
  
 <span data-ttu-id="24c84-134">Les lignes suivantes du code définissent les caractéristiques du client avec lequel vous avez généré une prédiction :</span><span class="sxs-lookup"><span data-stu-id="24c84-134">The next lines of the code define the characteristics of the customer that you use to create a prediction:</span></span>  
  
```  
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="24c84-135">Si vous spécifiez NATURAL PREDICTION JOIN, le serveur fait correspondre chaque colonne du modèle avec une colonne d'entrée en se basant sur les noms des colonnes.</span><span class="sxs-lookup"><span data-stu-id="24c84-135">If you specify NATURAL PREDICTION JOIN, the server matches each column from the model to a column from the input, based on column names.</span></span> <span data-ttu-id="24c84-136">Si les noms des colonnes ne correspondent pas, les colonnes sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="24c84-136">If column names do not match, the columns are ignored.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query"></a><span data-ttu-id="24c84-137">Pour créer une requête de prédiction singleton</span><span class="sxs-lookup"><span data-stu-id="24c84-137">To create a singleton prediction query</span></span>  
  
1.  <span data-ttu-id="24c84-138">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="24c84-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="24c84-139">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="24c84-139">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="24c84-140">Copiez l'exemple générique de l'instruction singleton dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="24c84-140">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="24c84-141">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="24c84-141">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="24c84-142">par :</span><span class="sxs-lookup"><span data-stu-id="24c84-142">with:</span></span>  
  
    ```  
    [Bike Buyer] AS Buyer, PredictHistogram([Bike Buyer]) AS Statistics  
    ```  
  
     <span data-ttu-id="24c84-143">L'instruction AS est employée pour créer des alias pour les colonnes retournées par la requête.</span><span class="sxs-lookup"><span data-stu-id="24c84-143">The AS statement is used to alias columns returned by the query.</span></span> <span data-ttu-id="24c84-144">La fonction [PredictHistogram](/sql/dmx/predicthistogram-dmx) retourne des statistiques sur la prédiction, notamment la probabilité et la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="24c84-144">The [PredictHistogram](/sql/dmx/predicthistogram-dmx) function returns statistics about the prediction, including the probability and the support.</span></span> <span data-ttu-id="24c84-145">Pour plus d’informations sur les fonctions qui peuvent être utilisées dans une instruction de prédiction, consultez [fonctions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="24c84-145">For more information about the functions that can be used in a prediction statement, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
4.  <span data-ttu-id="24c84-146">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="24c84-146">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="24c84-147">par :</span><span class="sxs-lookup"><span data-stu-id="24c84-147">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="24c84-148">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="24c84-148">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column name>], ...)  AS t  
    ```  
  
     <span data-ttu-id="24c84-149">par :</span><span class="sxs-lookup"><span data-stu-id="24c84-149">with:</span></span>  
  
    ```  
    (SELECT 35 AS [Age],  
      '5-10 Miles' AS [Commute Distance],  
      '1' AS [House Owner Flag],  
      2 AS [Number Cars Owned],  
      2 AS [Total Children]) AS t  
    ```  
  
     <span data-ttu-id="24c84-150">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="24c84-150">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
       [Bike Buyer] AS Buyer,  
       PredictHistogram([Bike Buyer]) AS Statistics  
    FROM  
       [Decision Tree]  
    NATURAL PREDICTION JOIN  
    (SELECT 35 AS [Age],  
       '5-10 Miles' AS [Commute Distance],  
       '1' AS [House Owner Flag],  
       2 AS [Number Cars Owned],  
       2 AS [Total Children]) AS t  
    ```  
  
6.  <span data-ttu-id="24c84-151">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="24c84-151">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="24c84-152">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Singleton_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="24c84-152">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_Query.dmx`.</span></span>  
  
8.  <span data-ttu-id="24c84-153">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="24c84-153">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="24c84-154">La requête retourne une prédiction indiquant dans quelle mesure un client avec les caractéristiques précisées est susceptible d'acheter un vélo, ainsi que des statistiques sur cette prédiction.</span><span class="sxs-lookup"><span data-stu-id="24c84-154">The query returns a prediction about whether a customer with the specified characteristics will purchase a bicycle, as well as statistics about that prediction.</span></span>  
  
## <a name="batch-query"></a><span data-ttu-id="24c84-155">Requête par lot</span><span class="sxs-lookup"><span data-stu-id="24c84-155">Batch Query</span></span>  
 <span data-ttu-id="24c84-156">L’étape suivante consiste à utiliser le [modèle SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) dans une requête de prédiction par lot.</span><span class="sxs-lookup"><span data-stu-id="24c84-156">The next step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a batch prediction query.</span></span> <span data-ttu-id="24c84-157">L'exemple générique suivant utilise une instruction par lot :</span><span class="sxs-lookup"><span data-stu-id="24c84-157">The following is a generic example of a batch statement:</span></span>  
  
```  
SELECT TOP <number> <select list>   
FROM [<mining model name>]  
PREDICTION JOIN  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
ON <on clause, mapping,>  
WHERE <where clause, boolean expression,>  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="24c84-158">Tout comme dans la requête singleton, les deux premières lignes du code définissent les colonnes du modèle d'exploration de données que retourne la requête, ainsi que le nom du modèle d'exploration utilisé pour générer la prédiction.</span><span class="sxs-lookup"><span data-stu-id="24c84-158">As in the singleton query, the first two lines of the code define the columns from mining model that the query returns, as well as the name of the mining model that is used to generate the prediction.</span></span> <span data-ttu-id="24c84-159">L' \<number> instruction Top spécifie que la requête retourne uniquement le nombre ou les résultats spécifiés par \<number> .</span><span class="sxs-lookup"><span data-stu-id="24c84-159">The TOP \<number> statement specifies that the query will only return the number or the results specified by \<number>.</span></span>  
  
 <span data-ttu-id="24c84-160">Les lignes suivantes du code définissent les données source sur lesquelles les prédictions sont fondées :</span><span class="sxs-lookup"><span data-stu-id="24c84-160">The next lines of the code define the source data that the predictions are based on:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
```  
  
 <span data-ttu-id="24c84-161">Vous disposez de plusieurs options pour la méthode d'extraction des données source mais, dans ce didacticiel, vous utiliserez OPENQUERY.</span><span class="sxs-lookup"><span data-stu-id="24c84-161">You have several options for the method of retrieving the source data, but in this tutorial, you will use OPENQUERY.</span></span> <span data-ttu-id="24c84-162">Pour plus d’informations sur les options disponibles, consultez [&#60;&#62;de requête de données source ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="24c84-162">For more information about the options available, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
 <span data-ttu-id="24c84-163">La ligne suivante définit le mappage entre les colonnes source du modèle d'exploration et les colonnes des données source :</span><span class="sxs-lookup"><span data-stu-id="24c84-163">The next line defines the mapping between the source columns in the mining model and the columns in the source data:</span></span>  
  
```  
ON <column mappings>  
```  
  
 <span data-ttu-id="24c84-164">La clause WHERE filtre les résultats retournés par la requête de prédiction :</span><span class="sxs-lookup"><span data-stu-id="24c84-164">The WHERE clause filters the results returned by the prediction query:</span></span>  
  
```  
WHERE <where clause, boolean expression,>  
```  
  
 <span data-ttu-id="24c84-165">La dernière ligne du code, qui est facultative, précise la colonne selon laquelle les résultats seront triés :</span><span class="sxs-lookup"><span data-stu-id="24c84-165">The last and optional line of the code specifies the column that the results will be ordered by:</span></span>  
  
```  
ORDER BY <expression> [DESC|ASC]  
```  
  
 <span data-ttu-id="24c84-166">Utilisez ORDER BY conjointement avec l’instruction TOP \<number> pour filtrer les résultats retournés.</span><span class="sxs-lookup"><span data-stu-id="24c84-166">Use ORDER BY in combination with the TOP \<number> statement, to filter the results that are returned.</span></span> <span data-ttu-id="24c84-167">Par exemple, dans cette prédiction, vous allez retourner les dix meilleurs acheteurs de vélos triés selon la probabilité d'exactitude de la prédiction.</span><span class="sxs-lookup"><span data-stu-id="24c84-167">For example, in this prediction you will return the top ten bike buyers, ordered by the probability of the prediction being correct.</span></span> <span data-ttu-id="24c84-168">Vous pouvez recourir à la syntaxe [DESC|ASC] pour contrôler l'ordre d'affichage des résultats.</span><span class="sxs-lookup"><span data-stu-id="24c84-168">You can use [DESC|ASC] syntax to control the order in which the results are displayed.</span></span>  
  
#### <a name="to-create-a-batch-prediction-query"></a><span data-ttu-id="24c84-169">Pour créer une requête de prédiction par lot</span><span class="sxs-lookup"><span data-stu-id="24c84-169">To create a batch prediction query</span></span>  
  
1.  <span data-ttu-id="24c84-170">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="24c84-170">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="24c84-171">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="24c84-171">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="24c84-172">Copiez l'exemple générique de l'instruction par lot dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="24c84-172">Copy the generic example of the batch statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="24c84-173">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="24c84-173">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="24c84-174">par :</span><span class="sxs-lookup"><span data-stu-id="24c84-174">with:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    ```  
  
     <span data-ttu-id="24c84-175">La clause TOP 10 indique que la requête retourne uniquement les dix meilleurs résultats.</span><span class="sxs-lookup"><span data-stu-id="24c84-175">The TOP 10 clause specifies that only the top ten results will be returned by the query.</span></span> <span data-ttu-id="24c84-176">L'instruction ORDER BY de cette requête trie les résultats selon la probabilité d'exactitude de la prédiction. Ainsi, seuls les dix meilleurs résultats possibles sont retournés.</span><span class="sxs-lookup"><span data-stu-id="24c84-176">The ORDER BY statement in this query orders the results by the probability of the prediction being correct, so only the ten most likely results will be returned.</span></span>  
  
4.  <span data-ttu-id="24c84-177">Remplacez l'espace réservé suivant :</span><span class="sxs-lookup"><span data-stu-id="24c84-177">Replace the following placeholder:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="24c84-178">Par le nom du modèle de données :</span><span class="sxs-lookup"><span data-stu-id="24c84-178">With the name of the model:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="24c84-179">Remplacez l'instruction générique OPENQUERY suivante :</span><span class="sxs-lookup"><span data-stu-id="24c84-179">Replace the following generic OPENQUERY statement:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="24c84-180">Par une instruction qui fait référence à l'entrepôt de données Adventureworks, notamment :</span><span class="sxs-lookup"><span data-stu-id="24c84-180">With a statement that references the current Adventureworks data warehouse, such as:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2014],  
      'SELECT  
        [LastName],  
        [FirstName],  
        [MaritalStatus],  
        [Gender],  
        [YearlyIncome],  
        [TotalChildren],  
        [NumberChildrenAtHome],  
        [Education],  
        [Occupation],  
        [HouseOwnerFlag],  
        [NumberCarsOwned]  
      FROM  
        [dbo].[ProspectiveBuyer]  
      ') AS t  
    ```  
  
6.  <span data-ttu-id="24c84-181">Remplacez la syntaxe générique suivante :</span><span class="sxs-lookup"><span data-stu-id="24c84-181">Replace the following generic syntax:</span></span>  
  
    ```  
    <ON clause, mapping,>   
    WHERE <where clause, boolean expression,>  
    ORDER BY <expression>  
    ```  
  
     <span data-ttu-id="24c84-182">Par les mappages de colonnes nécessaire pour ce modèle et un jeu de données d'entrée :</span><span class="sxs-lookup"><span data-stu-id="24c84-182">With the column mappings needed for this model and input data set:</span></span>  
  
    ```  
    [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
     <span data-ttu-id="24c84-183">Spécifiez `DESC` pour afficher en premier les résultats à plus forte probabilité.</span><span class="sxs-lookup"><span data-stu-id="24c84-183">Specify `DESC` in order to list the results with the highest probability first.</span></span>  
  
     <span data-ttu-id="24c84-184">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="24c84-184">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    FROM  
      [Decision Tree]  
    PREDICTION JOIN  
      OPENQUERY([Adventure Works DW 2014],  
        'SELECT  
          [LastName],  
          [FirstName],  
          [MaritalStatus],  
          [Gender],  
          [YearlyIncome],  
          [TotalChildren],  
          [NumberChildrenAtHome],  
          [Education],  
          [Occupation],  
          [HouseOwnerFlag],  
          [NumberCarsOwned]  
        FROM  
          [dbo].[ProspectiveBuyer]  
        ') AS t  
    ON  
      [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
7.  <span data-ttu-id="24c84-185">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="24c84-185">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="24c84-186">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Batch_Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="24c84-186">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Batch_Prediction.dmx`.</span></span>  
  
9. <span data-ttu-id="24c84-187">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="24c84-187">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="24c84-188">La requête retourne une table répertoriant les noms des clients, une prédiction indiquant si chaque client est un acheteur de vélo potentiel et la probabilité de cette prédiction.</span><span class="sxs-lookup"><span data-stu-id="24c84-188">The query returns a table containing customer names, a prediction of whether each customer will purchase a bicycle, and the probability of the prediction.</span></span>  
  
 <span data-ttu-id="24c84-189">C'est la dernière étape du didacticiel Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="24c84-189">This is the last step in the Bike Buyer tutorial.</span></span> <span data-ttu-id="24c84-190">Vous disposez désormais d'un ensemble de modèles d'exploration de données à l'aide desquels vous pouvez examiner des similitudes entre vos clients et prévoir qui parmi eux sont des acheteurs potentiels de vélos.</span><span class="sxs-lookup"><span data-stu-id="24c84-190">You now have a set of mining models that you can use to explore similarities between you customers and predict whether potential customers will purchase a bicycle.</span></span>  
  
 <span data-ttu-id="24c84-191">Pour savoir comment utiliser DMX dans un scénario de panier d’évolution, consultez le didacticiel sur le panier d’un [marché DMX](../../2014/tutorials/market-basket-dmx-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="24c84-191">To learn how to use DMX in a Market Basket scenario, see [Market Basket DMX Tutorial](../../2014/tutorials/market-basket-dmx-tutorial.md).</span></span>  
  
  
