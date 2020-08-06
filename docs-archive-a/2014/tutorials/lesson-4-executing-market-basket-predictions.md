---
title: 'Leçon 4 : exécution des prédictions du panier de marché | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b3238f1b-ea04-4253-ade2-838a806b62fe
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 3b49fc242eb8b2242269c5af33cc094937bbe0de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604324"
---
# <a name="lesson-4-executing-market-basket-predictions"></a><span data-ttu-id="ee900-102">Leçon 4 : Exécution de prédictions Market Basket</span><span class="sxs-lookup"><span data-stu-id="ee900-102">Lesson 4: Executing Market Basket Predictions</span></span>
  <span data-ttu-id="ee900-103">Dans cette leçon, vous allez utiliser l' `SELECT` instruction DMX pour créer des prédictions basées sur les modèles d’association que vous avez créés au cours de la [leçon 2 : ajout de modèles d’exploration de données à la structure d’exploration de données Market panier](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="ee900-103">In this lesson, you will use the DMX `SELECT` statement to create predictions based on the association models you created in [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="ee900-104">Une requête de prédiction est créée en utilisant l'instruction DMX `SELECT` et en ajoutant une clause `PREDICTION JOIN`</span><span class="sxs-lookup"><span data-stu-id="ee900-104">A prediction query is created by using the DMX `SELECT` statement and adding a `PREDICTION JOIN` clause.</span></span> <span data-ttu-id="ee900-105">Pour plus d’informations sur la syntaxe d’une jointure de prédiction, consultez [SELECT FROM &#60;model&#62; Prediction join &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span><span class="sxs-lookup"><span data-stu-id="ee900-105">For more information about the syntax of a prediction join, see [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span></span>  
  
 <span data-ttu-id="ee900-106">Le formulaire **Sélectionner à partir d’une \<model> jointure de prédiction** de l' `SELECT` instruction contient trois parties :</span><span class="sxs-lookup"><span data-stu-id="ee900-106">The **SELECT FROM \<model> PREDICTION JOIN** form of the `SELECT` statement contains three parts:</span></span>  
  
-   <span data-ttu-id="ee900-107">Liste des colonnes du modèle d'exploration de données et des fonctions de prédiction renvoyées dans l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="ee900-107">A list of the mining model columns and prediction functions that are returned in the result set.</span></span> <span data-ttu-id="ee900-108">Cette liste peut également contenir les colonnes d'entrée issues des données source.</span><span class="sxs-lookup"><span data-stu-id="ee900-108">This list can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="ee900-109">Requête source qui définit les données utilisées pour créer une prédiction.</span><span class="sxs-lookup"><span data-stu-id="ee900-109">A source query that defines the data that is being used to create a prediction.</span></span> <span data-ttu-id="ee900-110">Par exemple, si vous créez de nombreuses prédictions dans un lot, la requête source pourrait extraire une liste de clients.</span><span class="sxs-lookup"><span data-stu-id="ee900-110">For example, if you are creating many predictions in a batch, the source query could retrieve a list of customers.</span></span>  
  
-   <span data-ttu-id="ee900-111">Mappage entre les colonnes du modèle d'exploration de données et les données source.</span><span class="sxs-lookup"><span data-stu-id="ee900-111">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="ee900-112">Si les noms des colonnes correspondent, vous pouvez utiliser la syntaxe `NATURAL PREDICTION JOIN` et omettre les mappages de colonnes.</span><span class="sxs-lookup"><span data-stu-id="ee900-112">If the columns names match, you can use the `NATURAL PREDICTION JOIN` syntax and omit the column mappings.</span></span>  
  
 <span data-ttu-id="ee900-113">Vous pouvez affiner la requête à l'aide de fonctions de prédiction.</span><span class="sxs-lookup"><span data-stu-id="ee900-113">You can enhance the query by using prediction functions.</span></span> <span data-ttu-id="ee900-114">Les fonctions de prédiction fournissent des informations supplémentaires, notamment la probabilité d'une prédiction, ou offrent la prise en charge d'une prédiction dans le dataset d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="ee900-114">Prediction functions provide additional information, such as the probability of a prediction occurring, or the support for a prediction in the training dataset.</span></span> <span data-ttu-id="ee900-115">Pour plus d’informations sur les fonctions de prédiction, consultez [fonctions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="ee900-115">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="ee900-116">Vous pouvez également faire appel au générateur de requêtes de prédiction disponible dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour créer des requêtes de prédiction.</span><span class="sxs-lookup"><span data-stu-id="ee900-116">You can also use the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create prediction queries.</span></span>  
  
## <a name="singleton-prediction-join-statement"></a><span data-ttu-id="ee900-117">Instruction singleton PREDICTION JOIN</span><span class="sxs-lookup"><span data-stu-id="ee900-117">Singleton PREDICTION JOIN Statement</span></span>  
 <span data-ttu-id="ee900-118">La première étape consiste à créer une requête singleton à l’aide de la syntaxe **Select from \<model> PREDICTION JOIN** et en fournissant un ensemble unique de valeurs comme entrée.</span><span class="sxs-lookup"><span data-stu-id="ee900-118">The first step is to create a singleton query, by using the **SELECT FROM \<model> PREDICTION JOIN** syntax and supplying a single set of values as input.</span></span> <span data-ttu-id="ee900-119">L'exemple générique suivant utilise l'instruction singleton :</span><span class="sxs-lookup"><span data-stu-id="ee900-119">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list>  
    FROM [<mining model>]   
[NATURAL] PREDICTION JOIN  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
AS [<input alias>]  
```  
  
 <span data-ttu-id="ee900-120">La première ligne du code définit les colonnes du modèle d'exploration de données que retourne la requête et spécifie le nom du modèle d'exploration utilisé pour générer la prédiction :</span><span class="sxs-lookup"><span data-stu-id="ee900-120">The first line of the code defines the columns from the mining model that the query returns, and specifies the name of the mining model used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>]   
```  
  
 <span data-ttu-id="ee900-121">La ligne suivante du code indique l'opération à effectuer.</span><span class="sxs-lookup"><span data-stu-id="ee900-121">The next line of the code indicates the operation to perform.</span></span> <span data-ttu-id="ee900-122">Étant donné que vous spécifierez des valeurs pour chacune des colonnes et que vous taperez les noms de colonnes exactement pour qu'ils correspondent au modèle, vous pouvez utiliser la syntaxe `NATURAL PREDICTION JOIN`.</span><span class="sxs-lookup"><span data-stu-id="ee900-122">Because you will specify values for each of the columns and type the column names exactly so as to match the model, you can use the `NATURAL PREDICTION JOIN` syntax.</span></span> <span data-ttu-id="ee900-123">Toutefois, si les noms de colonne étaient différents, il vous faudra spécifier des mappages entre les colonnes dans le modèle et les colonnes dans les nouvelles données en ajoutant une clause `ON`.</span><span class="sxs-lookup"><span data-stu-id="ee900-123">However, if the column names were different, you would have to specify mappings between the columns in the model and the columns in the new data by adding an `ON` clause.</span></span>  
  
```  
[NATURAL] PREDICTION JOIN  
```  
  
 <span data-ttu-id="ee900-124">Les lignes suivantes du code définissent les produits du panier d'achat à utiliser pour prédire d'autres produits ajoutés par un client :</span><span class="sxs-lookup"><span data-stu-id="ee900-124">The next lines of the code define the products in the shopping cart that will be used to predict additional products that a customer will add:</span></span>  
  
```  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="ee900-125">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="ee900-125">Lesson Tasks</span></span>  
 <span data-ttu-id="ee900-126">Dans cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ee900-126">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="ee900-127">Créez une requête qui prédit les autres éléments qu’un client est susceptible d’acheter, en fonction des éléments déjà présents dans le panier.</span><span class="sxs-lookup"><span data-stu-id="ee900-127">Create a query that predicts what other items a customer will likely purchase, based on items already existing in their shopping cart.</span></span> <span data-ttu-id="ee900-128">Vous allez créer cette requête à l’aide du modèle d’exploration de données avec le *MINIMUM_PROBABILITY*par défaut.</span><span class="sxs-lookup"><span data-stu-id="ee900-128">You will create this query by using the mining model with the default *MINIMUM_PROBABILITY*.</span></span>  
  
-   <span data-ttu-id="ee900-129">créer une requête pour prédire quels autres articles un client est susceptible d'acheter, en vous basant sur des articles déjà présents dans son panier d'achat.</span><span class="sxs-lookup"><span data-stu-id="ee900-129">Create a query that predicts what other items a customer will likely purchase based on items already existing in their shopping cart.</span></span> <span data-ttu-id="ee900-130">Cette requête est basée sur un modèle différent, dans lequel *MINIMUM_PROBABILITY* a été défini sur 0,01.</span><span class="sxs-lookup"><span data-stu-id="ee900-130">This query is based on a different model, in which *MINIMUM_PROBABILITY* has been set to 0.01.</span></span> <span data-ttu-id="ee900-131">Étant donné que la valeur par défaut pour *MINIMUM_PROBABILITY* dans les modèles d’association est 0,3, la requête sur ce modèle doit retourner plus d’éléments possibles que la requête sur le modèle par défaut.</span><span class="sxs-lookup"><span data-stu-id="ee900-131">Because the default value for *MINIMUM_PROBABILITY* in association models is 0.3, the query on this model should return more possible items than the query on the default model.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-the-default-minimum_probability"></a><span data-ttu-id="ee900-132">Création d'une prédiction à l'aide d'un modèle avec le paramètre MINIMUM_PROBABILITY par défaut</span><span class="sxs-lookup"><span data-stu-id="ee900-132">Create a Prediction by Using a Model with the Default MINIMUM_PROBABILITY</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="ee900-133">Pour créer une requête Association</span><span class="sxs-lookup"><span data-stu-id="ee900-133">To create an association query</span></span>  
  
1.  <span data-ttu-id="ee900-134">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX** pour ouvrir l’éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="ee900-134">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="ee900-135">Copiez l'exemple générique de l'instruction `PREDICTION JOIN` dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="ee900-135">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="ee900-136">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="ee900-136">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="ee900-137">par :</span><span class="sxs-lookup"><span data-stu-id="ee900-137">with:</span></span>  
  
    ```  
    PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
     <span data-ttu-id="ee900-138">Vous pouvez simplement inclure le nom de colonne [Products], mais à l’aide de la fonction [Predict &#40;DMX&#41;](/sql/dmx/predict-dmx) , vous pouvez limiter le nombre de produits retournés par l’algorithme à trois.</span><span class="sxs-lookup"><span data-stu-id="ee900-138">You could just include the column name [Products], but by using the [Predict &#40;DMX&#41;](/sql/dmx/predict-dmx) function, you can limit the number of products that are returned by the algorithm to three.</span></span> <span data-ttu-id="ee900-139">Vous pouvez également utiliser l'instruction `INCLUDE_STATISTICS` pour vous procurer des informations supplémentaires sur chaque produit, notamment sur la prise en charge, la probabilité et la probabilité ajustée.</span><span class="sxs-lookup"><span data-stu-id="ee900-139">You can also use `INCLUDE_STATISTICS`, which returns the support, probability, and adjusted probability for each product.</span></span> <span data-ttu-id="ee900-140">Ces statistiques vous aident à évaluer la précision de la prédiction.</span><span class="sxs-lookup"><span data-stu-id="ee900-140">These statistics help you rate the accuracy of the prediction.</span></span>  
  
4.  <span data-ttu-id="ee900-141">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="ee900-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="ee900-142">par :</span><span class="sxs-lookup"><span data-stu-id="ee900-142">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="ee900-143">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="ee900-143">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="ee900-144">par :</span><span class="sxs-lookup"><span data-stu-id="ee900-144">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="ee900-145">Cette instruction utilise l'instruction `UNION` pour spécifier trois produits à inclure dans le panier d'achat avec les produits prédits.</span><span class="sxs-lookup"><span data-stu-id="ee900-145">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="ee900-146">La colonne Model dans l'instruction `SELECT` correspond à la colonne de modèle figurant dans la table imbriquée des produits.</span><span class="sxs-lookup"><span data-stu-id="ee900-146">The Model column in the `SELECT` statement corresponds to the model column that is contained in the nested products table.</span></span>  
  
     <span data-ttu-id="ee900-147">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="ee900-147">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Default Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="ee900-148">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="ee900-148">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="ee900-149">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="ee900-149">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="ee900-150">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="ee900-150">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="ee900-151">La requête retourne une table qui contient trois produits : HL Mountain Tire, Fender Set – Mountain et ML Mountain Tire.</span><span class="sxs-lookup"><span data-stu-id="ee900-151">The query returns a table that contains three products: HL Mountain Tire, Fender Set - Mountain, and ML Mountain Tire.</span></span> <span data-ttu-id="ee900-152">La table répertorie ces produits retournés par ordre de probabilité.</span><span class="sxs-lookup"><span data-stu-id="ee900-152">The table lists these returned products in order of probability.</span></span> <span data-ttu-id="ee900-153">Le produit retourné le plus susceptible d'être inclus dans le même panier d'achat que les trois produits spécifiés dans la requête apparaît en haut de la table.</span><span class="sxs-lookup"><span data-stu-id="ee900-153">The returned product that is most likely to be included in the same shopping cart as the three products specified in the query appears at the top of the table.</span></span> <span data-ttu-id="ee900-154">Les deux produits qui suivent sont les produits suivants les plus susceptibles d'être inclus dans le panier d'achat.</span><span class="sxs-lookup"><span data-stu-id="ee900-154">The two products that follow are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="ee900-155">La table renferme également des statistiques indiquant la précision de la prédiction.</span><span class="sxs-lookup"><span data-stu-id="ee900-155">The table also contains statistics describing the accuracy of the prediction.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-a-minimum_probability-of-001"></a><span data-ttu-id="ee900-156">Création d'une prédiction à l'aide d'un modèle avec un paramètre MINIMUM_PROBABILITY de 0.01</span><span class="sxs-lookup"><span data-stu-id="ee900-156">Create a Prediction by Using a Model with a MINIMUM_PROBABILITY of 0.01</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="ee900-157">Pour créer une requête Association</span><span class="sxs-lookup"><span data-stu-id="ee900-157">To create an association query</span></span>  
  
1.  <span data-ttu-id="ee900-158">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX** pour ouvrir l’éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="ee900-158">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="ee900-159">Copiez l'exemple générique de l'instruction `PREDICTION JOIN` dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="ee900-159">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="ee900-160">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="ee900-160">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="ee900-161">par :</span><span class="sxs-lookup"><span data-stu-id="ee900-161">with:</span></span>  
  
    ```  
    PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
4.  <span data-ttu-id="ee900-162">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="ee900-162">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="ee900-163">par :</span><span class="sxs-lookup"><span data-stu-id="ee900-163">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="ee900-164">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="ee900-164">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="ee900-165">par :</span><span class="sxs-lookup"><span data-stu-id="ee900-165">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="ee900-166">Cette instruction utilise l'instruction `UNION` pour spécifier trois produits à inclure dans le panier d'achat avec les produits prédits.</span><span class="sxs-lookup"><span data-stu-id="ee900-166">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="ee900-167">La colonne `[Model]` dans l'instruction `SELECT` correspond à la colonne figurant dans la table imbriquée des produits.</span><span class="sxs-lookup"><span data-stu-id="ee900-167">The `[Model]` column in the `SELECT` statement corresponds to the column in the nested products table.</span></span>  
  
     <span data-ttu-id="ee900-168">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="ee900-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Modified Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="ee900-169">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="ee900-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="ee900-170">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Modified Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="ee900-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="ee900-171">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="ee900-171">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="ee900-172">La requête retourne une table qui contient trois produits : HL Mountain Tire, Water Bottle et Fender Set – Mountain.</span><span class="sxs-lookup"><span data-stu-id="ee900-172">The query returns a table that contains three products: HL Mountain Tire, Water Bottle, and Fender Set - Mountain.</span></span> <span data-ttu-id="ee900-173">La table répertorie ces produits par ordre de probabilité.</span><span class="sxs-lookup"><span data-stu-id="ee900-173">The table lists these products in order of probability.</span></span> <span data-ttu-id="ee900-174">Le produit affiché en haut de la table est le produit le plus susceptible d'être inclus dans le même panier d'achat que les trois produits spécifiés dans la requête.</span><span class="sxs-lookup"><span data-stu-id="ee900-174">The product that appears at the top of the table is the product that is most likely to be included in the same shopping cart as the three products specified in the query.</span></span> <span data-ttu-id="ee900-175">Les produits restants sont les produits suivants les plus susceptibles d'être inclus dans le panier d'achat.</span><span class="sxs-lookup"><span data-stu-id="ee900-175">The remaining products are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="ee900-176">La table renferme également des statistiques qui indiquent la précision de la prédiction.</span><span class="sxs-lookup"><span data-stu-id="ee900-176">The table also contains statistics that describe the accuracy of the prediction.</span></span>  
  
     <span data-ttu-id="ee900-177">Vous pouvez voir à partir des résultats de cette requête que la valeur du paramètre *MINIMUM_PROBABILITY* affecte les résultats retournés par la requête.</span><span class="sxs-lookup"><span data-stu-id="ee900-177">You can see from the results of this query that the value of the *MINIMUM_PROBABILITY* parameter affects the results returned by the query.</span></span>  
  
 <span data-ttu-id="ee900-178">C'est la dernière étape du didacticiel Market Basket.</span><span class="sxs-lookup"><span data-stu-id="ee900-178">This is the last step in the Market Basket tutorial.</span></span> <span data-ttu-id="ee900-179">Vous disposez à présent d'un ensemble de modèles à l'aide desquels il vous est possible de prévoir les produits que les clients sont susceptibles d'acheter en même temps.</span><span class="sxs-lookup"><span data-stu-id="ee900-179">You now have a set of models that you can use to predict the products that customers might purchase at the same time.</span></span>  
  
 <span data-ttu-id="ee900-180">Pour en savoir plus sur l’utilisation de DMX dans un autre scénario prédictif, consultez le [didacticiel DMX Buyer](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ee900-180">To learn how to use DMX in another predictive scenario, see [Bike Buyer DMX Tutorial](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee900-181">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee900-181">See Also</span></span>  
 <span data-ttu-id="ee900-182">[Exemples de requêtes de modèle d’association](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="ee900-182">[Association Model Query Examples](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span></span>  
 [<span data-ttu-id="ee900-183">Interface de requête d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="ee900-183">Data Mining Query Interfaces</span></span>](../../2014/analysis-services/data-mining/data-mining-query-tools.md)  
  
  
