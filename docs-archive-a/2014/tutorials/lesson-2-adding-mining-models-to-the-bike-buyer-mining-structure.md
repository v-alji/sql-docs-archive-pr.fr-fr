---
title: 'Leçon 2 : ajout de modèles d’exploration de données à la structure d’exploration de données vélo Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 03fe44c5-6452-4ed0-95f6-9682670c0f52
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: de65fb7a85154f607cd8f266faec4621cdc41476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702212"
---
# <a name="lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure"></a><span data-ttu-id="83bd4-102">Leçon 2 : Ajout de modèles d’exploration de données à la structure d’exploration de données Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="83bd4-102">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="83bd4-103">Dans cette leçon, vous allez ajouter deux modèles d’exploration de données à la structure d’exploration de données Bike Buyer que vous avez créée [leçon 1 : création de la structure d’exploration de données Bike Buyer](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="83bd4-103">In this lesson, you will add two mining models to the Bike Buyer mining structure that you created [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span></span> <span data-ttu-id="83bd4-104">Vous pourrez utiliser ces modèles pour explorer des données avec l'un et créer des tâches de prédiction avec l'autre.</span><span class="sxs-lookup"><span data-stu-id="83bd4-104">These mining models will allow you to explore the data using one model, and to create predictions using another.</span></span>  
  
 <span data-ttu-id="83bd4-105">Pour découvrir comment les clients potentiels peuvent être catégorisés par leurs caractéristiques, vous allez créer un modèle d’exploration de données basé sur l' [algorithme de clustering Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="83bd4-105">To explore how potential customers can be categorized by their characteristics, you will create a mining model based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span> <span data-ttu-id="83bd4-106">Au cours d'une autre leçon, vous découvrirez comment cet algorithme recherche des clusters de clients partageant les mêmes caractéristiques.</span><span class="sxs-lookup"><span data-stu-id="83bd4-106">In a later lesson, you will explore how this algorithm finds clusters of customers who share similar characteristics.</span></span> <span data-ttu-id="83bd4-107">Par exemple, vous découvrirez peut-être que certains clients vivent proches les uns des autres, se déplacent à vélo et présentent le même parcours éducatif.</span><span class="sxs-lookup"><span data-stu-id="83bd4-107">For example, you might find that certain customers tend to live close to each other, commute by bicycle, and have similar education backgrounds.</span></span> <span data-ttu-id="83bd4-108">Vous pouvez recourir à ces clusters pour mieux comprendre les relations entre différents clients et exploiter les informations recueillies pour mettre sur pied une stratégie marketing ciblant des clients spécifiques.</span><span class="sxs-lookup"><span data-stu-id="83bd4-108">You can use these clusters to better understand how different customers are related, and to use the information to create a marketing strategy that targets specific customers.</span></span>  
  
 <span data-ttu-id="83bd4-109">Pour prédire si un client potentiel est susceptible d’acheter un vélo, vous allez créer un modèle d’exploration de données basé sur l' [algorithme MDT (Microsoft Decision Trees](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)).</span><span class="sxs-lookup"><span data-stu-id="83bd4-109">To predict whether a potential customer is likely to buy a bicycle, you will create a mining model based on the [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="83bd4-110">Cet algorithme examine les informations relatives à chaque client potentiel et recherche des caractéristiques à même de l'aider à prévoir et identifier d'éventuels acheteurs de vélos.</span><span class="sxs-lookup"><span data-stu-id="83bd4-110">This algorithm looks through the information that is associated with each potential customer, and finds characteristics that are useful in predicting if they will buy a bicycle.</span></span> <span data-ttu-id="83bd4-111">Il compare alors les valeurs des caractéristiques de précédents acheteurs avec celles de potentiels nouveaux clients pour déterminer si ces derniers sont susceptibles d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="83bd4-111">It then compares the values of the characteristics of previous bike buyers against new potential customers to determine whether the new potential customers are likely to buy a bicycle.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="83bd4-112">Instruction ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="83bd4-112">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="83bd4-113">Pour ajouter un modèle d’exploration de données à la structure d’exploration de données, vous utilisez l’instruction [ALTER Mining structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="83bd4-113">In order to add a mining model to the mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="83bd4-114">Le code de l’instruction peut être divisé en plusieurs parties :</span><span class="sxs-lookup"><span data-stu-id="83bd4-114">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="83bd4-115">Identification de la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="83bd4-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="83bd4-116">Attribution d'un nom au modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="83bd4-116">Naming the mining model</span></span>  
  
-   <span data-ttu-id="83bd4-117">Définition de la colonne clé</span><span class="sxs-lookup"><span data-stu-id="83bd4-117">Defining the key column</span></span>  
  
-   <span data-ttu-id="83bd4-118">Définition des colonnes d'entrée et des colonnes prédictibles</span><span class="sxs-lookup"><span data-stu-id="83bd4-118">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="83bd4-119">Identification des modifications d'algorithme et de paramètre</span><span class="sxs-lookup"><span data-stu-id="83bd4-119">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="83bd4-120">L'exemple générique suivant utilise l'instruction ALTER MINING MODEL :</span><span class="sxs-lookup"><span data-stu-id="83bd4-120">The following is a generic example of the ALTER MINING MODEL statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
(  
    [<key column>],  
    <mining model columns>,  
) USING <algorithm name>( <algorithm parameters> )  
WITH FILTER (<expression>)  
```  
  
 <span data-ttu-id="83bd4-121">La première ligne du code identifie la structure d'exploration de données existante à laquelle les modèles d'exploration de données seront ajoutés :</span><span class="sxs-lookup"><span data-stu-id="83bd4-121">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="83bd4-122">La ligne suivante du code désigne le modèle d'exploration de données qui sera ajouté à la structure d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="83bd4-122">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="83bd4-123">Pour plus d’informations sur l’attribution d’un nom à un objet dans DMX, consultez [identificateurs &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="83bd4-123">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="83bd4-124">Les lignes suivantes du code définissent les colonnes de la structure d'exploration de données employées dans le modèle d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="83bd4-124">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns>  
```  
  
 <span data-ttu-id="83bd4-125">Vous pouvez uniquement utiliser les colonnes déjà existantes dans la structure d'exploration de données ; de même, la première colonne de la liste doit correspondre à la colonne clé issue de la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="83bd4-125">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="83bd4-126">La ligne suivante du code définit l'algorithme d'exploration de données chargé de générer le modèle d'exploration de données ainsi que les paramètres d'algorithme que vous pouvez définir dans l'algorithme :</span><span class="sxs-lookup"><span data-stu-id="83bd4-126">The next line of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm:</span></span>  
  
```  
) USING <algorithm name>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="83bd4-127">Pour plus d’informations sur les paramètres d’algorithme que vous pouvez ajuster, consultez [algorithme MDT (Microsoft Decision Trees](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) ) et [algorithme de clustering Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="83bd4-127">For more information about the algorithm parameters that you can adjust, see [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) and [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span>  
  
 <span data-ttu-id="83bd4-128">Vous pouvez spécifier l'utilisation d'une colonne du modèle d'exploration de données à des fins de prédiction en utilisant la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="83bd4-128">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
 <span data-ttu-id="83bd4-129">La dernière ligne du code, qui est facultative, définit un filtre appliqué lors de l'apprentissage du modèle et de son test.</span><span class="sxs-lookup"><span data-stu-id="83bd4-129">The final line of the code, which is optional, defines a filter that is applied when training and testing the model.</span></span> <span data-ttu-id="83bd4-130">Pour plus d’informations sur la façon d’appliquer des filtres à des modèles d’exploration de données, consultez [filtres pour les modèles d’exploration de données &#40;Analysis Services&#41;d’exploration de données ](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="83bd4-130">For more information about how to apply filters to mining models, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="83bd4-131">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="83bd4-131">Lesson Tasks</span></span>  
 <span data-ttu-id="83bd4-132">Dans cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="83bd4-132">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="83bd4-133">ajouter un modèle d'exploration de données d'arbre de décision à la structure Bike Buyer à l'aide de l'algorithme [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees (MDT) ;</span><span class="sxs-lookup"><span data-stu-id="83bd4-133">Add a decision tree mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm</span></span>  
  
-   <span data-ttu-id="83bd4-134">ajouter un modèle d'exploration de données clustering à la structure Bike Buyer à l'aide de l'algorithme [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering.</span><span class="sxs-lookup"><span data-stu-id="83bd4-134">Add a clustering mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm</span></span>  
  
-   <span data-ttu-id="83bd4-135">Puisque vous souhaitez consulter des résultats pour tous les cas, n'ajoutez pas encore de filtre aux modèles.</span><span class="sxs-lookup"><span data-stu-id="83bd4-135">Because you want to see results for all cases, you will not yet add a filter to either model.</span></span>  
  
## <a name="adding-a-decision-tree-mining-model-to-the-structure"></a><span data-ttu-id="83bd4-136">Ajout d’un modèle d’exploration de données d’arbre de décision à la structure</span><span class="sxs-lookup"><span data-stu-id="83bd4-136">Adding a Decision Tree Mining Model to the Structure</span></span>  
 <span data-ttu-id="83bd4-137">La première étape consiste à ajouter un modèle d'exploration de données à l'aide de l'algorithme [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees (MDT)</span><span class="sxs-lookup"><span data-stu-id="83bd4-137">The first step is to add a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
#### <a name="to-add-a-decision-tree-mining-model"></a><span data-ttu-id="83bd4-138">Pour ajouter un modèle d'exploration de données d'arbre de décision</span><span class="sxs-lookup"><span data-stu-id="83bd4-138">To add a decision tree mining model</span></span>  
  
1.  <span data-ttu-id="83bd4-139">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX** pour ouvrir l’éditeur de requête et une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="83bd4-139">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="83bd4-140">Copiez l'exemple générique de l'instruction ALTER MINING STRUCTURE dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="83bd4-140">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="83bd4-141">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="83bd4-141">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="83bd4-142">par :</span><span class="sxs-lookup"><span data-stu-id="83bd4-142">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="83bd4-143">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="83bd4-143">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="83bd4-144">par :</span><span class="sxs-lookup"><span data-stu-id="83bd4-144">with:</span></span>  
  
    ```  
    Decision Tree  
    ```  
  
5.  <span data-ttu-id="83bd4-145">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="83bd4-145">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    ```  
  
     <span data-ttu-id="83bd4-146">par :</span><span class="sxs-lookup"><span data-stu-id="83bd4-146">with:</span></span>  
  
    ```  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ```  
  
     <span data-ttu-id="83bd4-147">Dans ce cas, la colonne `[Bike Buyer]` est désignée en tant que colonne PREDICT.</span><span class="sxs-lookup"><span data-stu-id="83bd4-147">In this case, the `[Bike Buyer]` column has been designated as the PREDICT column.</span></span>  
  
6.  <span data-ttu-id="83bd4-148">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="83bd4-148">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )   
    ```  
  
     <span data-ttu-id="83bd4-149">par :</span><span class="sxs-lookup"><span data-stu-id="83bd4-149">with:</span></span>  
  
    ```  
    Using Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="83bd4-150">L'instruction WITH DRILLTHROUGH vous permet d'explorer les cas utilisés pour la création du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="83bd4-150">The WITH DRILLTHROUGH statement allows you to explore the cases that were used to build the mining model.</span></span>  
  
     <span data-ttu-id="83bd4-151">L'instruction obtenue doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="83bd4-151">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Decision Tree]  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ) USING Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
7.  <span data-ttu-id="83bd4-152">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="83bd4-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="83bd4-153">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `DT_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="83bd4-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `DT_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="83bd4-154">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="83bd4-154">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-a-clustering-mining-model-to-the-structure"></a><span data-ttu-id="83bd4-155">Ajout d'un modèle d'exploration de données clustering à une structure</span><span class="sxs-lookup"><span data-stu-id="83bd4-155">Adding a Clustering Mining Model to the Structure</span></span>  
 <span data-ttu-id="83bd4-156">Vous pouvez maintenant ajouter un modèle d'exploration de données à la structure d'exploration de données Bike Buyer fondé sur l'algorithme [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering.</span><span class="sxs-lookup"><span data-stu-id="83bd4-156">You can now add a mining model to the Bike Buyer mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span> <span data-ttu-id="83bd4-157">Du fait que le modèle d'exploration de données clustering exploite l'ensemble des colonnes définies dans la structure d'exploration de données, vous pouvez utiliser un raccourci pour ajouter le modèle à la structure en omettant la définition des colonnes d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="83bd4-157">Because the clustering mining model will use all the columns defined in the mining structure, you can use a shortcut to add the model to the structure by omitting the definition of the mining columns.</span></span>  
  
#### <a name="to-add-a-clustering-mining-model"></a><span data-ttu-id="83bd4-158">Pour ajouter un modèle d'exploration de données clustering</span><span class="sxs-lookup"><span data-stu-id="83bd4-158">To add a Clustering mining model</span></span>  
  
1.  <span data-ttu-id="83bd4-159">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX** pour ouvrir l’éditeur de requête et une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="83bd4-159">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor opens and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="83bd4-160">Copiez l'exemple générique de l'instruction ALTER MINING STRUCTURE dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="83bd4-160">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="83bd4-161">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="83bd4-161">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="83bd4-162">par :</span><span class="sxs-lookup"><span data-stu-id="83bd4-162">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="83bd4-163">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="83bd4-163">Replace the following:</span></span>  
  
    ```  
    <mining model>   
    ```  
  
     <span data-ttu-id="83bd4-164">par :</span><span class="sxs-lookup"><span data-stu-id="83bd4-164">with:</span></span>  
  
    ```  
    Clustering Model  
    ```  
  
5.  <span data-ttu-id="83bd4-165">Supprimez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="83bd4-165">Delete the following:</span></span>  
  
    ```  
    (  
        [<key column>],  
        <mining model columns>,  
    )  
    ```  
  
6.  <span data-ttu-id="83bd4-166">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="83bd4-166">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="83bd4-167">par :</span><span class="sxs-lookup"><span data-stu-id="83bd4-167">with:</span></span>  
  
    ```  
    USING Microsoft_Clustering  
    ```  
  
     <span data-ttu-id="83bd4-168">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="83bd4-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Clustering]  
    USING Microsoft_Clustering   
    ```  
  
7.  <span data-ttu-id="83bd4-169">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="83bd4-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="83bd4-170">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Clustering_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="83bd4-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Clustering_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="83bd4-171">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="83bd4-171">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="83bd4-172">Dans la leçon suivante, vous allez traiter les modèles et la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="83bd4-172">In the next lesson, you will process the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="83bd4-173">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="83bd4-173">Next Lesson</span></span>  
 [<span data-ttu-id="83bd4-174">Leçon 3 : Traitement de la structure d’exploration de données Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="83bd4-174">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-bike-buyer-mining-structure.md)  
  
  
