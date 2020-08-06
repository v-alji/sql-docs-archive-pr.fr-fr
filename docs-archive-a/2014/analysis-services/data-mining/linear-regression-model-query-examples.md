---
title: Exemples de requêtes de modèle de régression linéaire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- linear regression algorithms [Analysis Services]
- linear regression [Analysis Services]
- content queries [DMX]
ms.assetid: fd3cf312-57a1-44b6-b772-fce6fc1c26d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 02d4b7309d7b5ea3d6295089f0fb2e778b1c9b4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614263"
---
# <a name="linear-regression-model-query-examples"></a><span data-ttu-id="535b0-102">Exemples de requête de modèle de régression linéaire</span><span class="sxs-lookup"><span data-stu-id="535b0-102">Linear Regression Model Query Examples</span></span>
  <span data-ttu-id="535b0-103">Lorsque vous créez une requête sur un modèle d'exploration de données, vous pouvez créer une requête de contenu, qui fournit des détails sur les modèles (ou séquences) découverts au cours de l'analyse, ou créer une requête de prédiction, qui utilise les séquences du modèle pour effectuer des prédictions pour les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="535b0-103">When you create a query against a data mining model, you can create a content query, which provides details about the patterns discovered in analysis, or you can create a prediction query, which uses the patterns in the model to make predictions for new data.</span></span> <span data-ttu-id="535b0-104">Par exemple, une requête de contenu peut fournir des détails supplémentaires sur la formule de régression, tandis qu'une requête de prédiction peut vous indiquer si un nouveau point de données est adapté au modèle.</span><span class="sxs-lookup"><span data-stu-id="535b0-104">For example, a content query might provide additional details about the regression formula, while a prediction query might tell you if a new data point fits the model.</span></span> <span data-ttu-id="535b0-105">Vous pouvez également extraire les métadonnées relatives au modèle en utilisant une requête.</span><span class="sxs-lookup"><span data-stu-id="535b0-105">You can also retrieve metadata about the model by using a query.</span></span>  
  
 <span data-ttu-id="535b0-106">Cette section explique comment créer ces requêtes pour les modèles basés sur l'algorithme MLR (Microsoft Linear Regression).</span><span class="sxs-lookup"><span data-stu-id="535b0-106">This section explains how to create queries for models that are based on the Microsoft Linear Regression algorithm.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="535b0-107">La régression linéaire étant basée sur un cas spécial de l'algorithme MDT (Microsoft Decision Trees), les similarités sont nombreuses, et certains modèles d'arbre de décision qui utilisent des attributs prédictibles continus peuvent contenir des formules de régression.</span><span class="sxs-lookup"><span data-stu-id="535b0-107">Because linear regression is based on a special case of the Microsoft Decision Trees algorithm, there are many similarities, and some decision tree models that use continuous predictable attributes can contain regression formulas.</span></span> <span data-ttu-id="535b0-108">Pour plus d’informations, consultez [Références techniques relatives à l’algorithme MDT (Microsoft Decision Trees)](microsoft-decision-trees-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="535b0-108">For more information, see [Microsoft Decision Trees Algorithm Technical Reference](microsoft-decision-trees-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="535b0-109">**Requêtes de contenu**</span><span class="sxs-lookup"><span data-stu-id="535b0-109">**Content queries**</span></span>  
  
 [<span data-ttu-id="535b0-110">Utilisation de l'ensemble de lignes de schéma d'exploration de données pour déterminer les paramètres utilisés pour un modèle</span><span class="sxs-lookup"><span data-stu-id="535b0-110">Using the Data Mining Schema Rowset to determine parameters used for a model</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="535b0-111">Utilisation de DMX pour retourner la formule de régression du modèle</span><span class="sxs-lookup"><span data-stu-id="535b0-111">Using DMX to return the regression formula for the model</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="535b0-112">Retour uniquement du coefficient du modèle</span><span class="sxs-lookup"><span data-stu-id="535b0-112">Returning only the coefficient for the model</span></span>](#bkmk_Query3)  
  
 <span data-ttu-id="535b0-113">**Requêtes de prédiction**</span><span class="sxs-lookup"><span data-stu-id="535b0-113">**Prediction queries**</span></span>  
  
 [<span data-ttu-id="535b0-114">Prédiction du revenu à l'aide d'une requête singleton</span><span class="sxs-lookup"><span data-stu-id="535b0-114">Predicting income using a singleton query</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="535b0-115">Utilisation des fonctions de prédiction avec un modèle de régression</span><span class="sxs-lookup"><span data-stu-id="535b0-115">Using prediction functions with a regression model</span></span>](#bkmk_Query5)  
  
##  <a name="finding-information-about-the-linear-regression-model"></a><a name="bkmk_top"></a> <span data-ttu-id="535b0-116">Recherche d'informations sur le modèle de régression linéaire</span><span class="sxs-lookup"><span data-stu-id="535b0-116">Finding Information about the Linear Regression Model</span></span>  
 <span data-ttu-id="535b0-117">La structure d'un modèle de régression linéaire est extrêmement simple : le modèle d'exploration de données représente les données sous la forme d'un nœud unique qui définit la formule de régression.</span><span class="sxs-lookup"><span data-stu-id="535b0-117">The structure of a linear regression model is extremely simple: the mining model represents the data as a single node, which defines the regression formula.</span></span> <span data-ttu-id="535b0-118">Pour plus d’informations, consultez [Contenu du modèle d’exploration de données pour les modèles de régression logistique &#40;Analysis Services – Exploration de données&#41;](mining-model-content-for-logistic-regression-models.md).</span><span class="sxs-lookup"><span data-stu-id="535b0-118">For more information, see [Mining Model Content for Logistic Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-logistic-regression-models.md).</span></span>  
  
 [<span data-ttu-id="535b0-119">Retour au début</span><span class="sxs-lookup"><span data-stu-id="535b0-119">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-1-using-the-data-mining-schema-rowset-to-determine-parameters-used-for-a-model"></a><a name="bkmk_Query1"></a> <span data-ttu-id="535b0-120">Exemple de requête 1 : utilisation de l'ensemble de lignes de schéma d'exploration de données pour déterminer les paramètres utilisés pour un modèle</span><span class="sxs-lookup"><span data-stu-id="535b0-120">Sample Query 1: Using the Data Mining Schema Rowset to Determine Parameters Used for a Model</span></span>  
 <span data-ttu-id="535b0-121">En interrogeant l'ensemble de lignes de schéma d'exploration de données, vous pouvez obtenir les métadonnées relatives au modèle.</span><span class="sxs-lookup"><span data-stu-id="535b0-121">By querying the data mining schema rowset, you can find metadata about the model.</span></span> <span data-ttu-id="535b0-122">Celles-ci peuvent inclure la date de création du modèle, celle de son dernier traitement, le nom de la structure d'exploration de données sur laquelle le modèle est basé, ainsi que le nom de la colonne désignée comme attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="535b0-122">This might include when the model was created, when the model was last processed, the name of the mining structure that the model is based on, and the name of the column designated as the predictable attribute.</span></span> <span data-ttu-id="535b0-123">Vous pouvez également retourner les paramètres qui ont été utilisés lorsque le modèle a été créé pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="535b0-123">You can also return the parameters that were used when the model was first created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM_PredictIncome'  
```  
  
 <span data-ttu-id="535b0-124">Exemples de résultats :</span><span class="sxs-lookup"><span data-stu-id="535b0-124">Sample results:</span></span>  
  
|<span data-ttu-id="535b0-125">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="535b0-125">MINING_PARAMETERS</span></span>|  
|------------------------|  
|<span data-ttu-id="535b0-126">COMPLEXITY_PENALTY=0.9,</span><span class="sxs-lookup"><span data-stu-id="535b0-126">COMPLEXITY_PENALTY=0.9,</span></span><br /><br /> <span data-ttu-id="535b0-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="535b0-127">MAXIMUM_INPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="535b0-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span><span class="sxs-lookup"><span data-stu-id="535b0-128">MAXIMUM_OUTPUT_ATTRIBUTES=255,</span></span><br /><br /> <span data-ttu-id="535b0-129">MINIMUM_SUPPORT=10,</span><span class="sxs-lookup"><span data-stu-id="535b0-129">MINIMUM_SUPPORT=10,</span></span><br /><br /> <span data-ttu-id="535b0-130">SCORE_METHOD=4,</span><span class="sxs-lookup"><span data-stu-id="535b0-130">SCORE_METHOD=4,</span></span><br /><br /> <span data-ttu-id="535b0-131">SPLIT_METHOD=3,</span><span class="sxs-lookup"><span data-stu-id="535b0-131">SPLIT_METHOD=3,</span></span><br /><br /> <span data-ttu-id="535b0-132">FORCE_REGRESSOR=</span><span class="sxs-lookup"><span data-stu-id="535b0-132">FORCE_REGRESSOR=</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="535b0-133">Le paramètre`FORCE_REGRESSOR =` indique que la valeur actuelle du paramètre FORCE_REGRESSOR est Null.</span><span class="sxs-lookup"><span data-stu-id="535b0-133">The parameter setting, "`FORCE_REGRESSOR =` ", indicates that the current value for the FORCE_REGRESSOR parameter is null.</span></span>  
  
 [<span data-ttu-id="535b0-134">Retour au début</span><span class="sxs-lookup"><span data-stu-id="535b0-134">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-2-retrieving-the-regression-formula-for-the-model"></a><a name="bkmk_Query2"></a> <span data-ttu-id="535b0-135">Exemple de requête 2 : récupération de la formule de régression du modèle</span><span class="sxs-lookup"><span data-stu-id="535b0-135">Sample Query 2: Retrieving the Regression Formula for the Model</span></span>  
 <span data-ttu-id="535b0-136">La requête suivante retourne le contenu du modèle d'exploration de données pour un modèle de régression linéaire qui a été construit en utilisant la même source de données de publipostage ciblé que celle utilisée dans le [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="535b0-136">The following query returns the mining model content for a linear regression model that was built by using the same Targeted Mailing data source that was used in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="535b0-137">Ce modèle prédit le revenu des clients en fonction de leur âge.</span><span class="sxs-lookup"><span data-stu-id="535b0-137">This model predicts customer income based on age.</span></span>  
  
 <span data-ttu-id="535b0-138">La requête retourne le contenu du nœud qui contient la formule de régression.</span><span class="sxs-lookup"><span data-stu-id="535b0-138">The query returns the contents of the node that contains the regression formula.</span></span> <span data-ttu-id="535b0-139">Chaque variable et chaque coefficient est stocké dans une ligne distincte de la table imbriquée NODE_DISTRIBUTION.</span><span class="sxs-lookup"><span data-stu-id="535b0-139">Each variable and coefficient is stored in a separate row of the nested NODE_DISTRIBUTION table.</span></span> <span data-ttu-id="535b0-140">Pour consulter la formule de régression complète, dans la [Visionneuse d’arborescences Microsoft](browse-a-model-using-the-microsoft-tree-viewer.md), cliquez sur le nœud **(Tout)** , puis ouvrez **Légende d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="535b0-140">If you want to view the complete regression formula, use the [Microsoft Tree Viewer](browse-a-model-using-the-microsoft-tree-viewer.md), click the **(All)** node, and open the **Mining Legend**.</span></span>  
  
```  
SELECT FLATTENED NODE_DISTRIBUTION as t  
FROM LR_PredictIncome.CONTENT  
```  
  
> [!NOTE]  
>  <span data-ttu-id="535b0-141">Si vous faites référence à des colonnes individuelles de la table imbriquée en utilisant une requête comme `SELECT <column name> from NODE_DISTRIBUTION`, certaines colonnes, comme **SUPPORT** ou **PROBABILITY**, doivent être placées entre crochets afin de les distinguer des mots clés réservés qui portent le même nom.</span><span class="sxs-lookup"><span data-stu-id="535b0-141">If you reference individual columns of the nested table by using a query such as `SELECT <column name> from NODE_DISTRIBUTION`, some columns, such as **SUPPORT** or **PROBABILITY**, must be enclosed in brackets to distinguish them from reserved keywords of the same name.</span></span>  
  
 <span data-ttu-id="535b0-142">Résultats attendus :</span><span class="sxs-lookup"><span data-stu-id="535b0-142">Expected results:</span></span>  
  
|<span data-ttu-id="535b0-143">T.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="535b0-143">t.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="535b0-144">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="535b0-144">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="535b0-145">t.SUPPORT</span><span class="sxs-lookup"><span data-stu-id="535b0-145">t.SUPPORT</span></span>|<span data-ttu-id="535b0-146">t.PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="535b0-146">t.PROBABILITY</span></span>|<span data-ttu-id="535b0-147">t.VARIANCE</span><span class="sxs-lookup"><span data-stu-id="535b0-147">t.VARIANCE</span></span>|<span data-ttu-id="535b0-148">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="535b0-148">t.VALUETYPE</span></span>|  
|-----------------------|------------------------|---------------|-------------------|----------------|-----------------|  
|<span data-ttu-id="535b0-149">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="535b0-149">Yearly Income</span></span>|<span data-ttu-id="535b0-150">Manquant</span><span class="sxs-lookup"><span data-stu-id="535b0-150">Missing</span></span>|<span data-ttu-id="535b0-151">0</span><span class="sxs-lookup"><span data-stu-id="535b0-151">0</span></span>|<span data-ttu-id="535b0-152">0.000457142857142857</span><span class="sxs-lookup"><span data-stu-id="535b0-152">0.000457142857142857</span></span>|<span data-ttu-id="535b0-153">0</span><span class="sxs-lookup"><span data-stu-id="535b0-153">0</span></span>|<span data-ttu-id="535b0-154">1</span><span class="sxs-lookup"><span data-stu-id="535b0-154">1</span></span>|  
|<span data-ttu-id="535b0-155">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="535b0-155">Yearly Income</span></span>|<span data-ttu-id="535b0-156">57220.8876687257</span><span class="sxs-lookup"><span data-stu-id="535b0-156">57220.8876687257</span></span>|<span data-ttu-id="535b0-157">17484</span><span class="sxs-lookup"><span data-stu-id="535b0-157">17484</span></span>|<span data-ttu-id="535b0-158">0.999542857142857</span><span class="sxs-lookup"><span data-stu-id="535b0-158">0.999542857142857</span></span>|<span data-ttu-id="535b0-159">1041275619.52776</span><span class="sxs-lookup"><span data-stu-id="535b0-159">1041275619.52776</span></span>|<span data-ttu-id="535b0-160">3</span><span class="sxs-lookup"><span data-stu-id="535b0-160">3</span></span>|  
|<span data-ttu-id="535b0-161">Age</span><span class="sxs-lookup"><span data-stu-id="535b0-161">Age</span></span>|<span data-ttu-id="535b0-162">471.687717702463</span><span class="sxs-lookup"><span data-stu-id="535b0-162">471.687717702463</span></span>|<span data-ttu-id="535b0-163">0</span><span class="sxs-lookup"><span data-stu-id="535b0-163">0</span></span>|<span data-ttu-id="535b0-164">0</span><span class="sxs-lookup"><span data-stu-id="535b0-164">0</span></span>|<span data-ttu-id="535b0-165">126.969442359327</span><span class="sxs-lookup"><span data-stu-id="535b0-165">126.969442359327</span></span>|<span data-ttu-id="535b0-166">7</span><span class="sxs-lookup"><span data-stu-id="535b0-166">7</span></span>|  
|<span data-ttu-id="535b0-167">Age</span><span class="sxs-lookup"><span data-stu-id="535b0-167">Age</span></span>|<span data-ttu-id="535b0-168">234.680904692439</span><span class="sxs-lookup"><span data-stu-id="535b0-168">234.680904692439</span></span>|<span data-ttu-id="535b0-169">0</span><span class="sxs-lookup"><span data-stu-id="535b0-169">0</span></span>|<span data-ttu-id="535b0-170">0</span><span class="sxs-lookup"><span data-stu-id="535b0-170">0</span></span>|<span data-ttu-id="535b0-171">0</span><span class="sxs-lookup"><span data-stu-id="535b0-171">0</span></span>|<span data-ttu-id="535b0-172">8</span><span class="sxs-lookup"><span data-stu-id="535b0-172">8</span></span>|  
|<span data-ttu-id="535b0-173">Age</span><span class="sxs-lookup"><span data-stu-id="535b0-173">Age</span></span>|<span data-ttu-id="535b0-174">45.4269617936399</span><span class="sxs-lookup"><span data-stu-id="535b0-174">45.4269617936399</span></span>|<span data-ttu-id="535b0-175">0</span><span class="sxs-lookup"><span data-stu-id="535b0-175">0</span></span>|<span data-ttu-id="535b0-176">0</span><span class="sxs-lookup"><span data-stu-id="535b0-176">0</span></span>|<span data-ttu-id="535b0-177">126.969442359327</span><span class="sxs-lookup"><span data-stu-id="535b0-177">126.969442359327</span></span>|<span data-ttu-id="535b0-178">9</span><span class="sxs-lookup"><span data-stu-id="535b0-178">9</span></span>|  
||<span data-ttu-id="535b0-179">35793.5477381267</span><span class="sxs-lookup"><span data-stu-id="535b0-179">35793.5477381267</span></span>|<span data-ttu-id="535b0-180">0</span><span class="sxs-lookup"><span data-stu-id="535b0-180">0</span></span>|<span data-ttu-id="535b0-181">0</span><span class="sxs-lookup"><span data-stu-id="535b0-181">0</span></span>|<span data-ttu-id="535b0-182">1012968919.28372</span><span class="sxs-lookup"><span data-stu-id="535b0-182">1012968919.28372</span></span>|<span data-ttu-id="535b0-183">11</span><span class="sxs-lookup"><span data-stu-id="535b0-183">11</span></span>|  
  
 <span data-ttu-id="535b0-184">En comparaison, dans **Légende d’exploration de données**, la formule de régression apparaît comme suit :</span><span class="sxs-lookup"><span data-stu-id="535b0-184">In comparison, in the **Mining Legend**, the regression formula appears as follows:</span></span>  
  
 <span data-ttu-id="535b0-185">Yearly Income = 57,220.919 + 471.688 \* (Age - 45.427)</span><span class="sxs-lookup"><span data-stu-id="535b0-185">Yearly Income = 57,220.919 + 471.688 \* (Age - 45.427)</span></span>  
  
 <span data-ttu-id="535b0-186">Vous pouvez constater que dans **Légende d’exploration de données**, certains nombres sont arrondis ; toutefois, la table NODE_DISTRIBUTION et **Légende d’exploration de données** contiennent essentiellement les mêmes valeurs.</span><span class="sxs-lookup"><span data-stu-id="535b0-186">You can see that in the **Mining Legend**, some numbers are rounded; however, the NODE_DISTRIBUTION table and the **Mining Legend** essentially contain the same values.</span></span>  
  
 <span data-ttu-id="535b0-187">Les valeurs indiquées dans la colonne VALUETYPE précisent le type des informations contenues dans chaque ligne, ce qui est utile si vous traitez les résultats par programme.</span><span class="sxs-lookup"><span data-stu-id="535b0-187">The values in the VALUETYPE column tell you what kind of information is contained in each row, which is useful if you are processing the results programmatically.</span></span> <span data-ttu-id="535b0-188">Le tableau suivant affiche les types de valeur qui sont générés pour une formule de régression linéaire.</span><span class="sxs-lookup"><span data-stu-id="535b0-188">The following table shows the value types that are output for a linear regression formula.</span></span>  
  
|<span data-ttu-id="535b0-189">VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="535b0-189">VALUETYPE</span></span>|  
|---------------|  
|<span data-ttu-id="535b0-190">1 (Manquante)</span><span class="sxs-lookup"><span data-stu-id="535b0-190">1 (Missing)</span></span>|  
|<span data-ttu-id="535b0-191">3 (Continue)</span><span class="sxs-lookup"><span data-stu-id="535b0-191">3 (Continuous)</span></span>|  
|<span data-ttu-id="535b0-192">7 (Coefficient)</span><span class="sxs-lookup"><span data-stu-id="535b0-192">7 (Coefficient)</span></span>|  
|<span data-ttu-id="535b0-193">8 (Gain du score)</span><span class="sxs-lookup"><span data-stu-id="535b0-193">8 (Score Gain)</span></span>|  
|<span data-ttu-id="535b0-194">9 (Statistiques)</span><span class="sxs-lookup"><span data-stu-id="535b0-194">9 (Statistics)</span></span>|  
|<span data-ttu-id="535b0-195">7 (Coefficient)</span><span class="sxs-lookup"><span data-stu-id="535b0-195">7 (Coefficient)</span></span>|  
|<span data-ttu-id="535b0-196">8 (Gain du score)</span><span class="sxs-lookup"><span data-stu-id="535b0-196">8 (Score Gain)</span></span>|  
|<span data-ttu-id="535b0-197">9 (Statistiques)</span><span class="sxs-lookup"><span data-stu-id="535b0-197">9 (Statistics)</span></span>|  
|<span data-ttu-id="535b0-198">11 (Ordonnée à l'origine)</span><span class="sxs-lookup"><span data-stu-id="535b0-198">11 (Intercept)</span></span>|  
  
 <span data-ttu-id="535b0-199">Pour plus d’informations sur la signification de chaque type de valeur pour les modèles de régression, consultez [Contenu du modèle d’exploration de données pour les modèles de régression linéaire &#40;Analysis Services – Exploration de données&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="535b0-199">For more information about the meaning of each value type for regression models, see [Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="535b0-200">Retour au début</span><span class="sxs-lookup"><span data-stu-id="535b0-200">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-3-returning-only-the-coefficient-for-the-model"></a><a name="bkmk_Query3"></a> <span data-ttu-id="535b0-201">Exemple de requête 3 : retour uniquement du coefficient du modèle</span><span class="sxs-lookup"><span data-stu-id="535b0-201">Sample Query 3: Returning Only the Coefficient for the Model</span></span>  
 <span data-ttu-id="535b0-202">En utilisant l'énumération VALUETYPE, vous pouvez retourner uniquement le coefficient de l'équation de régression, tel qu'indiqué dans la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="535b0-202">By using the VALUETYPE enumeration, you can return only the coefficient for the regression equation, as shown in the following query:</span></span>  
  
```  
SELECT FLATTENED MODEL_NAME,  
    (SELECT ATTRIBUTE_VALUE, VALUETYPE  
     FROM NODE_DISTRIBUTION  
     WHERE VALUETYPE = 11)   
AS t  
FROM LR_PredictIncome.CONTENT  
```  
  
 <span data-ttu-id="535b0-203">Cette requête retourne deux lignes : une provenant du contenu du modèle d'exploration de données et celle provenant de la table imbriquée qui contient le coefficient.</span><span class="sxs-lookup"><span data-stu-id="535b0-203">This query returns two rows, one from the mining model content, and the row from the nested table that contains the coefficient.</span></span> <span data-ttu-id="535b0-204">La colonne ATTRIBUTE_NAME n'est pas incluse ici parce qu'elle est toujours vide pour le coefficient.</span><span class="sxs-lookup"><span data-stu-id="535b0-204">The ATTRIBUTE_NAME column is not included here because it is always blank for the coefficient.</span></span>  
  
|<span data-ttu-id="535b0-205">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="535b0-205">MODEL_NAME</span></span>|<span data-ttu-id="535b0-206">t.ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="535b0-206">t.ATTRIBUTE_VALUE</span></span>|<span data-ttu-id="535b0-207">t.VALUETYPE</span><span class="sxs-lookup"><span data-stu-id="535b0-207">t.VALUETYPE</span></span>|  
|-----------------|------------------------|-----------------|  
|<span data-ttu-id="535b0-208">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="535b0-208">LR_PredictIncome</span></span>|||  
|<span data-ttu-id="535b0-209">LR_PredictIncome</span><span class="sxs-lookup"><span data-stu-id="535b0-209">LR_PredictIncome</span></span>|<span data-ttu-id="535b0-210">35793.5477381267</span><span class="sxs-lookup"><span data-stu-id="535b0-210">35793.5477381267</span></span>|<span data-ttu-id="535b0-211">11</span><span class="sxs-lookup"><span data-stu-id="535b0-211">11</span></span>|  
  
 [<span data-ttu-id="535b0-212">Retour au début</span><span class="sxs-lookup"><span data-stu-id="535b0-212">Return to Top</span></span>](#bkmk_top)  
  
## <a name="making-predictions-from-a-linear-regression-model"></a><span data-ttu-id="535b0-213">Élaborer des prédictions à partir d'un modèle de régression linéaire</span><span class="sxs-lookup"><span data-stu-id="535b0-213">Making Predictions from a Linear Regression Model</span></span>  
 <span data-ttu-id="535b0-214">Vous pouvez créer des requêtes de prédiction sur des modèles de régression linéaire en utilisant l'onglet Prévision de modèle d'exploration de données du Concepteur d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="535b0-214">You can build prediction queries on linear regression models by using the Mining Model Prediction tab in Data Mining Designer.</span></span> <span data-ttu-id="535b0-215">Le générateur de requêtes de prédiction est disponible à la fois dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] et [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="535b0-215">The prediction query builder is available in both [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="535b0-216">Vous pouvez également créer des requêtes sur les modèles de régression en utilisant les compléments d’exploration de données pour Excel [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou les compléments d’exploration de données pour Excel [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="535b0-216">You can also create queries on regression models by using the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Data Mining Add-ins for Excel or the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] Data Mining Add-ins for Excel.</span></span> <span data-ttu-id="535b0-217">Même si les compléments d'exploration de données pour Excel ne créent pas de modèles de régression, vous pouvez parcourir et interroger un modèle d'exploration de données stocké sur une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="535b0-217">Even though the Data Mining Add-ins for Excel do not create regression models, you can browse and query any mining model that is stored on an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="535b0-218">Retour au début</span><span class="sxs-lookup"><span data-stu-id="535b0-218">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-4-predicting-income-using-a-singleton-query"></a><a name="bkmk_Query4"></a> <span data-ttu-id="535b0-219">Exemple de requête 4 : prédiction du revenu à l'aide d'une requête singleton</span><span class="sxs-lookup"><span data-stu-id="535b0-219">Sample Query 4: Predicting Income using a Singleton Query</span></span>  
 <span data-ttu-id="535b0-220">La méthode la plus facile pour créer une requête singleton sur un modèle de régression consiste à utiliser la boîte de dialogue **Entrée de requête singleton** .</span><span class="sxs-lookup"><span data-stu-id="535b0-220">The easiest way to create a single query on a regression model is by using the **Singleton Query Input** dialog box.</span></span> <span data-ttu-id="535b0-221">Par exemple, vous pouvez créer la requête DMX suivante en sélectionnant le modèle de régression approprié, en sélectionnant **requête singleton**, puis `20` en tapant comme valeur pour **Age**.</span><span class="sxs-lookup"><span data-stu-id="535b0-221">For example, you can build the following DMX query by selecting the appropriate regression model, choosing **Singleton Query**, and then typing `20` as the value for **Age**.</span></span>  
  
```  
SELECT [LR_PredictIncome].[Yearly Income]  
From   [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="535b0-222">Exemples de résultats :</span><span class="sxs-lookup"><span data-stu-id="535b0-222">Sample results:</span></span>  
  
|<span data-ttu-id="535b0-223">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="535b0-223">Yearly Income</span></span>|  
|-------------------|  
|<span data-ttu-id="535b0-224">45227.302092176</span><span class="sxs-lookup"><span data-stu-id="535b0-224">45227.302092176</span></span>|  
  
 [<span data-ttu-id="535b0-225">Retour au début</span><span class="sxs-lookup"><span data-stu-id="535b0-225">Return to Top</span></span>](#bkmk_top)  
  
###  <a name="sample-query-5-using-prediction-functions-with-a-regression-model"></a><a name="bkmk_Query5"></a> <span data-ttu-id="535b0-226">Exemple de requête 5 : utilisation des fonctions de prédiction avec un modèle de régression</span><span class="sxs-lookup"><span data-stu-id="535b0-226">Sample Query 5: Using Prediction Functions with a Regression Model</span></span>  
 <span data-ttu-id="535b0-227">Vous pouvez utiliser de nombreuses fonctions de prédiction standard avec les modèles de régression linéaire.</span><span class="sxs-lookup"><span data-stu-id="535b0-227">You can use many of the standard prediction functions with linear regression models.</span></span> <span data-ttu-id="535b0-228">L'exemple suivant montre comment ajouter des statistiques descriptives aux résultats de requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="535b0-228">The following example illustrates how to add some descriptive statistics to the prediction query results.</span></span> <span data-ttu-id="535b0-229">D'après ces résultats, vous pouvez constater que l'écart de la moyenne est très important pour ce modèle.</span><span class="sxs-lookup"><span data-stu-id="535b0-229">From these results, you can see that there is considerable deviation from the mean for this model.</span></span>  
  
```  
SELECT  
  ([LR_PredictIncome].[Yearly Income]) as [PredIncome],  
  (PredictStdev([LR_PredictIncome].[Yearly Income])) as [StDev1]  
From  
  [LR_PredictIncome]  
NATURAL PREDICTION JOIN  
(SELECT 20 AS [Age]) AS t  
```  
  
 <span data-ttu-id="535b0-230">Exemples de résultats :</span><span class="sxs-lookup"><span data-stu-id="535b0-230">Sample results:</span></span>  
  
|<span data-ttu-id="535b0-231">Yearly Income</span><span class="sxs-lookup"><span data-stu-id="535b0-231">Yearly Income</span></span>|<span data-ttu-id="535b0-232">StDev1</span><span class="sxs-lookup"><span data-stu-id="535b0-232">StDev1</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="535b0-233">45227.302092176</span><span class="sxs-lookup"><span data-stu-id="535b0-233">45227.302092176</span></span>|<span data-ttu-id="535b0-234">31827.1726561396</span><span class="sxs-lookup"><span data-stu-id="535b0-234">31827.1726561396</span></span>|  
  
 [<span data-ttu-id="535b0-235">Retour au début</span><span class="sxs-lookup"><span data-stu-id="535b0-235">Return to Top</span></span>](#bkmk_top)  
  
## <a name="list-of-prediction-functions"></a><span data-ttu-id="535b0-236">Liste des fonctions de prédiction</span><span class="sxs-lookup"><span data-stu-id="535b0-236">List of Prediction Functions</span></span>  
 <span data-ttu-id="535b0-237">Tous les algorithmes [!INCLUDE[msCoName](../../includes/msconame-md.md)] prennent en charge un ensemble commun de fonctions.</span><span class="sxs-lookup"><span data-stu-id="535b0-237">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="535b0-238">Toutefois, l'algorithme MLR ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression) prend en charge les fonctions supplémentaires répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="535b0-238">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Linear Regression algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="535b0-239">Fonction de prédiction</span><span class="sxs-lookup"><span data-stu-id="535b0-239">Prediction Function</span></span>|<span data-ttu-id="535b0-240">Usage</span><span class="sxs-lookup"><span data-stu-id="535b0-240">Usage</span></span>|  
|[<span data-ttu-id="535b0-241">IsDescendant &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="535b0-241">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="535b0-242">Détermine si un nœud est un enfant d'un autre nœud dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="535b0-242">Determines whether one node is a child of another node in the model.</span></span>|  
|[<span data-ttu-id="535b0-243">IsInNode &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="535b0-243">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="535b0-244">Indique si le nœud spécifié contient le cas courant.</span><span class="sxs-lookup"><span data-stu-id="535b0-244">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="535b0-245">PredictHistogram &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="535b0-245">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="535b0-246">Retourne une valeur ou un ensemble de valeurs prédites pour une colonne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="535b0-246">Returns a predicted value, or set of values, for a specified column.</span></span>|  
|[<span data-ttu-id="535b0-247">PredictNodeId &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="535b0-247">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="535b0-248">Retourne Node_ID pour chaque cas.</span><span class="sxs-lookup"><span data-stu-id="535b0-248">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="535b0-249">PredictStdev &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="535b0-249">PredictStdev &#40;DMX&#41;</span></span>](/sql/dmx/predictstdev-dmx)|<span data-ttu-id="535b0-250">Retourne l'écart-type pour la valeur prédite.</span><span class="sxs-lookup"><span data-stu-id="535b0-250">Returns standard deviation for the predicted value.</span></span>|  
|[<span data-ttu-id="535b0-251">PredictSupport &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="535b0-251">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="535b0-252">Retourne la valeur de support pour un état spécifié.</span><span class="sxs-lookup"><span data-stu-id="535b0-252">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="535b0-253">PredictVariance &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="535b0-253">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="535b0-254">Retourne la variance d'une colonne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="535b0-254">Returns the variance of a specified column.</span></span>|  
  
 <span data-ttu-id="535b0-255">Pour obtenir la liste des fonctions qui sont communes à tous les algorithmes [!INCLUDE[msCoName](../../includes/msconame-md.md)], consultez [Algorithmes d’exploration de données &#40;Analysis Services – Exploration de données&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="535b0-255">For a list of the functions that are common to all [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span> <span data-ttu-id="535b0-256">Pour plus d’informations sur l’utilisation de ces fonctions, consultez [Fonctions DMX &#40;Data Mining Extensions&#41;](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="535b0-256">For more information about how to use these functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="535b0-257">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="535b0-257">See Also</span></span>  
 <span data-ttu-id="535b0-258">[Algorithme de régression linéaire Microsoft](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="535b0-258">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="535b0-259">[Requêtes d’exploration de données](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="535b0-259">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="535b0-260">[Référence technique de l’algorithme de régression linéaire Microsoft](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="535b0-260">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="535b0-261">Contenu du modèle d’exploration de données pour les modèles de régression linéaire &#40;Analysis Services – Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="535b0-261">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
