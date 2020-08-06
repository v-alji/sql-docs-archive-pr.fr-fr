---
title: Exemples de requêtes de modèle d’association | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- rules [Data Mining]
- association rules
- content queries [DMX]
ms.assetid: 68b39f5c-c439-44ac-8046-6f2d36649059
author: minewiskan
ms.author: owend
ms.openlocfilehash: a19eb2302639c7f13d48a8778969bbeca4fee18d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613703"
---
# <a name="association-model-query-examples"></a><span data-ttu-id="98fb5-102">Exemples de requêtes de modèle d'association</span><span class="sxs-lookup"><span data-stu-id="98fb5-102">Association Model Query Examples</span></span>
  <span data-ttu-id="98fb5-103">Lorsque vous créez une requête sur un modèle d'exploration de données, vous pouvez soit créer une requête de contenu qui fournit des détails sur les règles et les jeux d'éléments découverts au cours de l'analyse, soit créer une requête de prédiction qui utilise les associations découvertes dans les données pour faire des prédictions.</span><span class="sxs-lookup"><span data-stu-id="98fb5-103">When you create a query against a data mining model, you can create either a content query, which provides details about the rules and itemsets discovered during analysis, or you can create a prediction query, which uses the associations discovered in the data to make predictions.</span></span> <span data-ttu-id="98fb5-104">En général, pour un modèle d'association, les prédictions sont basées sur des règles et peuvent être utilisées pour faire des recommandations, tandis que les interrogations sur du contenu explorent la relation entre les jeux d'éléments.</span><span class="sxs-lookup"><span data-stu-id="98fb5-104">For an association model, predictions typically are based on rules, and can be used to make recommendations, whereas queries on content typically explore the relationship among itemsets.</span></span> <span data-ttu-id="98fb5-105">Vous pouvez aussi récupérer des métadonnées sur le modèle.</span><span class="sxs-lookup"><span data-stu-id="98fb5-105">You can also retrieve metadata about the model.</span></span>  
  
 <span data-ttu-id="98fb5-106">Cette section explique comment créer ces types de requêtes pour les modèles basés sur l’algorithme MAR ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules).</span><span class="sxs-lookup"><span data-stu-id="98fb5-106">This section explains how to create these kinds of queries for models that are based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span>  
  
 <span data-ttu-id="98fb5-107">**Requêtes de contenu**</span><span class="sxs-lookup"><span data-stu-id="98fb5-107">**Content Queries**</span></span>  
  
 [<span data-ttu-id="98fb5-108">Obtention de données de métadonnées de modèle avec DMX</span><span class="sxs-lookup"><span data-stu-id="98fb5-108">Getting model metadata data by using DMX</span></span>](#bkmk_Query1)  
  
 [<span data-ttu-id="98fb5-109">Obtention de métadonnées de l'ensemble de lignes de schéma</span><span class="sxs-lookup"><span data-stu-id="98fb5-109">Getting metadata from the schema rowset</span></span>](#bkmk_Query2)  
  
 [<span data-ttu-id="98fb5-110">Récupération des paramètres d'origine pour le modèle</span><span class="sxs-lookup"><span data-stu-id="98fb5-110">Retrieving the original parameters for the model</span></span>](#bkmk_Query3)  
  
 [<span data-ttu-id="98fb5-111">Récupération d'une liste de jeux d'éléments et produits</span><span class="sxs-lookup"><span data-stu-id="98fb5-111">Retrieving a list of itemsets and products</span></span>](#bkmk_Query4)  
  
 [<span data-ttu-id="98fb5-112">Retour de 10 principaux jeux d'éléments</span><span class="sxs-lookup"><span data-stu-id="98fb5-112">Returning the top 10 itemsets</span></span>](#bkmk_Query5)  
  
 <span data-ttu-id="98fb5-113">**Requêtes de prédiction**</span><span class="sxs-lookup"><span data-stu-id="98fb5-113">**Prediction Queries**</span></span>  
  
 [<span data-ttu-id="98fb5-114">Prédire des éléments associés</span><span class="sxs-lookup"><span data-stu-id="98fb5-114">Predicting associated items</span></span>](#bkmk_Query6)  
  
 [<span data-ttu-id="98fb5-115">Identification de la confiance pour les jeux d'éléments connexes</span><span class="sxs-lookup"><span data-stu-id="98fb5-115">Determining confidence for related itemsets</span></span>](#bkmk_Query7)  
  
##  <a name="finding-information-about-the-model"></a><a name="bkmk_top2"></a> <span data-ttu-id="98fb5-116">Recherche d'informations sur le modèle</span><span class="sxs-lookup"><span data-stu-id="98fb5-116">Finding Information about the Model</span></span>  
 <span data-ttu-id="98fb5-117">Tous les modèles d'exploration de données exposent le contenu appris par l'algorithme en fonction d'un schéma standardisé, appelé l'ensemble de lignes de schéma du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="98fb5-117">All mining models expose the content learned by the algorithm according to a standardized schema, which is named the mining model schema rowset.</span></span> <span data-ttu-id="98fb5-118">Vous pouvez créer des requêtes sur l'ensemble de lignes de schéma du modèle d'exploration de données en utilisant des instructions DMX (Data Mining Extensions) ou des procédures stockées [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="98fb5-118">You can create queries against the mining model schema rowset either by using Data Mining Extensions (DMX) statements, or by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="98fb5-119">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], vous pouvez également interroger directement les ensemble de lignes de schéma en tant que tables système en utilisant une syntaxe de type SQL.</span><span class="sxs-lookup"><span data-stu-id="98fb5-119">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can also query the schema rowsets directly as system tables, by using a SQL-like syntax.</span></span>  
  
###  <a name="sample-query-1-getting-model-metadata-by-using-dmx"></a><a name="bkmk_Query1"></a> <span data-ttu-id="98fb5-120">Exemple de requête 1 : obtention des métadonnées du modèle à l'aide de DMX</span><span class="sxs-lookup"><span data-stu-id="98fb5-120">Sample Query 1: Getting Model Metadata by Using DMX</span></span>  
 <span data-ttu-id="98fb5-121">La requête suivante retourne les métadonnées de base sur le modèle d'association, `Association`, telles que le nom du modèle, la base de données où le modèle est stocké et le nombre de nœuds enfants dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="98fb5-121">The following query returns basic metadata about the association model, `Association`, such as the name of the model, the database where the model is stored, and the number of child nodes in the model.</span></span> <span data-ttu-id="98fb5-122">Cette requête utilise une requête de contenu DMX pour récupérer les métadonnées du nœud parent du modèle:</span><span class="sxs-lookup"><span data-stu-id="98fb5-122">This query uses a DMX content query to retrieve the metadata from the parent node of the model:</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, NODE_CAPTION,   
NODE_SUPPORT, [CHILDREN_CARDINALITY], NODE_DESCRIPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="98fb5-123">Vous devez mettre le nom de la colonne, CHILDREN_CARDINALITY, entre parenthèses pour le distinguer du mot clé réservé MDX du même nom.</span><span class="sxs-lookup"><span data-stu-id="98fb5-123">You must enclose the name of the column, CHILDREN_CARDINALITY, in brackets to distinguish it from the MDX reserved keyword of the same name.</span></span>  
  
 <span data-ttu-id="98fb5-124">Résultats de l'exemple :</span><span class="sxs-lookup"><span data-stu-id="98fb5-124">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98fb5-125">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="98fb5-125">MODEL_CATALOG</span></span>|<span data-ttu-id="98fb5-126">Association Test</span><span class="sxs-lookup"><span data-stu-id="98fb5-126">Association Test</span></span>|  
|<span data-ttu-id="98fb5-127">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="98fb5-127">MODEL_NAME</span></span>|<span data-ttu-id="98fb5-128">Association</span><span class="sxs-lookup"><span data-stu-id="98fb5-128">Association</span></span>|  
|<span data-ttu-id="98fb5-129">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="98fb5-129">NODE_CAPTION</span></span>|<span data-ttu-id="98fb5-130">Association Rules Model</span><span class="sxs-lookup"><span data-stu-id="98fb5-130">Association Rules Model</span></span>|  
|<span data-ttu-id="98fb5-131">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="98fb5-131">NODE_SUPPORT</span></span>|<span data-ttu-id="98fb5-132">14879</span><span class="sxs-lookup"><span data-stu-id="98fb5-132">14879</span></span>|  
|<span data-ttu-id="98fb5-133">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="98fb5-133">CHILDREN_CARDINALITY</span></span>|<span data-ttu-id="98fb5-134">942</span><span class="sxs-lookup"><span data-stu-id="98fb5-134">942</span></span>|  
|<span data-ttu-id="98fb5-135">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="98fb5-135">NODE_DESCRIPTION</span></span>|<span data-ttu-id="98fb5-136">Association Rules Model; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span><span class="sxs-lookup"><span data-stu-id="98fb5-136">Association Rules Model; ITEMSET_COUNT=679; RULE_COUNT=263; MIN_SUPPORT=14; MAX_SUPPORT=4334; MIN_ITEMSET_SIZE=0; MAX_ITEMSET_SIZE=3; MIN_PROBABILITY=0.400390625; MAX_PROBABILITY=1; MIN_LIFT=0.14309369632511; MAX_LIFT=1.95758227647523</span></span>|  
  
 <span data-ttu-id="98fb5-137">Pour connaître la signification de ces colonnes dans un modèle d’association, consultez [Contenu du modèle d’exploration de données pour les modèles d’association &#40;Analysis Services - Exploration de données&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="98fb5-137">For a definition of what these columns mean in an association model, see [Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;](mining-model-content-for-association-models-analysis-services-data-mining.md).</span></span>  
  
 [<span data-ttu-id="98fb5-138">Retour au début</span><span class="sxs-lookup"><span data-stu-id="98fb5-138">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-2-getting-additional-metadata-from-the-schema-rowset"></a><a name="bkmk_Query2"></a> <span data-ttu-id="98fb5-139">Exemple de requête 2 : obtention de métadonnées supplémentaires à partir de l'ensemble de lignes de schéma</span><span class="sxs-lookup"><span data-stu-id="98fb5-139">Sample Query 2: Getting Additional Metadata from the Schema Rowset</span></span>  
 <span data-ttu-id="98fb5-140">En interrogeant l'ensemble de lignes de schéma d'exploration de données, vous pouvez obtenir les mêmes informations que celles retournées par une requête de contenu DMX.</span><span class="sxs-lookup"><span data-stu-id="98fb5-140">By querying the data mining schema rowset, you can find the same information that is returned in a DMX content query.</span></span> <span data-ttu-id="98fb5-141">Toutefois, l'ensemble de lignes de schéma fournit quelques colonnes supplémentaires, telles que la date à laquelle le modèle a été traité pour la dernière fois, la structure d'exploration de données et le nom de la colonne utilisée comme attribut prévisible.</span><span class="sxs-lookup"><span data-stu-id="98fb5-141">However, the schema rowset provides some additional columns, such as the date the model was last processed, the mining structure, and the name of the column used as the predictable attribute.</span></span>  
  
```  
SELECT MODEL_CATALOG, MODEL_NAME, SERVICE_NAME, PREDICTION_ENTITY,   
MINING_STRUCTURE, LAST_PROCESSED  
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="98fb5-142">Résultats de l'exemple :</span><span class="sxs-lookup"><span data-stu-id="98fb5-142">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98fb5-143">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="98fb5-143">MODEL_CATALOG</span></span>|<span data-ttu-id="98fb5-144">Adventure Works DW Multidimensional 2012</span><span class="sxs-lookup"><span data-stu-id="98fb5-144">Adventure Works DW Multidimensional 2012</span></span>|  
|<span data-ttu-id="98fb5-145">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="98fb5-145">MODEL_NAME</span></span>|<span data-ttu-id="98fb5-146">Association</span><span class="sxs-lookup"><span data-stu-id="98fb5-146">Association</span></span>|  
|<span data-ttu-id="98fb5-147">SERVICE_NAME</span><span class="sxs-lookup"><span data-stu-id="98fb5-147">SERVICE_NAME</span></span>|<span data-ttu-id="98fb5-148">Association Rules Model</span><span class="sxs-lookup"><span data-stu-id="98fb5-148">Association Rules Model</span></span>|  
|<span data-ttu-id="98fb5-149">PREDICTION_ENTITY</span><span class="sxs-lookup"><span data-stu-id="98fb5-149">PREDICTION_ENTITY</span></span>|<span data-ttu-id="98fb5-150">v Assoc Seq Line Items</span><span class="sxs-lookup"><span data-stu-id="98fb5-150">v Assoc Seq Line Items</span></span>|  
|<span data-ttu-id="98fb5-151">MINING_STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="98fb5-151">MINING_STRUCTURE</span></span>|<span data-ttu-id="98fb5-152">Association</span><span class="sxs-lookup"><span data-stu-id="98fb5-152">Association</span></span>|  
|<span data-ttu-id="98fb5-153">LAST_PROCESSED</span><span class="sxs-lookup"><span data-stu-id="98fb5-153">LAST_PROCESSED</span></span>|<span data-ttu-id="98fb5-154">9/29/2007 10:21:24 PM</span><span class="sxs-lookup"><span data-stu-id="98fb5-154">9/29/2007 10:21:24 PM</span></span>|  
  
 [<span data-ttu-id="98fb5-155">Retour au début</span><span class="sxs-lookup"><span data-stu-id="98fb5-155">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-3-retrieving-original-parameters-for-model"></a><a name="bkmk_Query3"></a> <span data-ttu-id="98fb5-156">Exemple de requête 3 : récupération des paramètres d'origine pour le modèle</span><span class="sxs-lookup"><span data-stu-id="98fb5-156">Sample Query 3: Retrieving Original Parameters for Model</span></span>  
 <span data-ttu-id="98fb5-157">La requête suivante retourne une colonne unique qui contient des détails sur la configuration des paramètres utilisée au moment de la création du modèle.</span><span class="sxs-lookup"><span data-stu-id="98fb5-157">The following query returns a single column that contains details about the parameter settings that were used when the model was created.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
from $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'Association'  
```  
  
 <span data-ttu-id="98fb5-158">Résultats de l'exemple :</span><span class="sxs-lookup"><span data-stu-id="98fb5-158">Example results:</span></span>  
  
 <span data-ttu-id="98fb5-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span><span class="sxs-lookup"><span data-stu-id="98fb5-159">MAXIMUM_ITEMSET_COUNT=200000,MAXIMUM_ITEMSET_SIZE=3,MAXIMUM_SUPPORT=1,MINIMUM_SUPPORT=9.40923449156529E-04,MINIMUM_IMPORTANCE=-999999999,MINIMUM_ITEMSET_SIZE=0,MINIMUM_PROBABILITY=0.4</span></span>  
  
 [<span data-ttu-id="98fb5-160">Retour au début</span><span class="sxs-lookup"><span data-stu-id="98fb5-160">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="finding-information-about-rules-and-itemsets"></a><span data-ttu-id="98fb5-161">Recherche d'informations sur les règles et les jeux d'éléments</span><span class="sxs-lookup"><span data-stu-id="98fb5-161">Finding Information about Rules and Itemsets</span></span>  
 <span data-ttu-id="98fb5-162">En général, un modèle d'association sert à deux choses : découvrir des informations sur les jeux d'éléments fréquents et récupérer des détails sur des règles et des jeux d'éléments particuliers.</span><span class="sxs-lookup"><span data-stu-id="98fb5-162">There are two common uses of an association model: to discover information about frequent itemsets, and to extract details about particular rules and itemsets.</span></span> <span data-ttu-id="98fb5-163">Par exemple, vous souhaitez peut-être récupérer une liste des règles dont le score indique qu'elles sont particulièrement intéressantes ou créer une liste des jeux d'éléments les plus courants.</span><span class="sxs-lookup"><span data-stu-id="98fb5-163">For example, you might want to extract a list of rules that were scored as being especially interesting, or create a list of the most common itemsets.</span></span> <span data-ttu-id="98fb5-164">Vous récupérez de telles informations en utilisant une requête de contenu DMX.</span><span class="sxs-lookup"><span data-stu-id="98fb5-164">You retrieve such information by using a DMX content query.</span></span> <span data-ttu-id="98fb5-165">Vous pouvez aussi parcourir ces informations à l’aide de la **visionneuse d’associations Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="98fb5-165">You can also browse this information by using the **Microsoft Association Viewer**.</span></span>  
  
###  <a name="sample-query-4-retrieving-list-of-itemsets-and-products"></a><a name="bkmk_Query4"></a> <span data-ttu-id="98fb5-166">Exemple de requête 4 : récupération d'une liste de jeux d'éléments et de produits</span><span class="sxs-lookup"><span data-stu-id="98fb5-166">Sample Query 4: Retrieving List of Itemsets and Products</span></span>  
 <span data-ttu-id="98fb5-167">La requête suivante récupère tous les jeux d'éléments, ainsi qu'une table imbriquée qui répertorie les produits inclus dans chaque jeu d'éléments.</span><span class="sxs-lookup"><span data-stu-id="98fb5-167">The following query retrieves all of the itemsets, together with a nested table that lists the products included in each itemset.</span></span> <span data-ttu-id="98fb5-168">La colonne NODE_NAME contient l'ID unique du jeu d'éléments dans le modèle, tandis que la colonne NODE_CAPTION fournit une description textuelle des éléments.</span><span class="sxs-lookup"><span data-stu-id="98fb5-168">The NODE_NAME column contains the unique ID of the itemset within the model, whereas the NODE_CAPTION provides a text description of the items.</span></span> <span data-ttu-id="98fb5-169">Dans cet exemple, la table imbriquée est aplatie, de telle sorte qu'un jeu d'éléments contenant deux produits génère deux lignes dans les résultats.</span><span class="sxs-lookup"><span data-stu-id="98fb5-169">In this example, the nested table is flattened, so that an itemset that contains two products generates two rows in the results.</span></span> <span data-ttu-id="98fb5-170">Vous pouvez omettre le mot clé FLATTENED si votre client prend en charge des données hiérarchiques.</span><span class="sxs-lookup"><span data-stu-id="98fb5-170">You can omit the FLATTENED keyword if your client supports hierarchical data.</span></span>  
  
```  
SELECT FLATTENED NODE_NAME, NODE_CAPTION,  
NODE_PROBABILITY, NODE_SUPPORT,  
(SELECT ATTRIBUTE_NAME FROM NODE_DISTRIBUTION) as PurchasedProducts  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="98fb5-171">Résultats de l'exemple :</span><span class="sxs-lookup"><span data-stu-id="98fb5-171">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98fb5-172">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="98fb5-172">NODE_NAME</span></span>|<span data-ttu-id="98fb5-173">37</span><span class="sxs-lookup"><span data-stu-id="98fb5-173">37</span></span>|  
|<span data-ttu-id="98fb5-174">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="98fb5-174">NODE_CAPTION</span></span>|<span data-ttu-id="98fb5-175">Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="98fb5-175">Sport-100 = Existing</span></span>|  
|<span data-ttu-id="98fb5-176">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="98fb5-176">NODE_PROBABILITY</span></span>|<span data-ttu-id="98fb5-177">0.291283016331743</span><span class="sxs-lookup"><span data-stu-id="98fb5-177">0.291283016331743</span></span>|  
|<span data-ttu-id="98fb5-178">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="98fb5-178">NODE_SUPPORT</span></span>|<span data-ttu-id="98fb5-179">4334</span><span class="sxs-lookup"><span data-stu-id="98fb5-179">4334</span></span>|  
|<span data-ttu-id="98fb5-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="98fb5-180">PURCHASEDPRODUCTS.ATTRIBUTE_NAME</span></span>|<span data-ttu-id="98fb5-181">v Assoc Seq Line Items(Sport-100)</span><span class="sxs-lookup"><span data-stu-id="98fb5-181">v Assoc Seq Line Items(Sport-100)</span></span>|  
  
 [<span data-ttu-id="98fb5-182">Retour au début</span><span class="sxs-lookup"><span data-stu-id="98fb5-182">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-5-returning-top-10-itemsets"></a><a name="bkmk_Query5"></a> <span data-ttu-id="98fb5-183">Exemple de requête 5 : retour des 10 premiers jeux d'éléments</span><span class="sxs-lookup"><span data-stu-id="98fb5-183">Sample Query 5: Returning Top 10 Itemsets</span></span>  
 <span data-ttu-id="98fb5-184">Cet exemple montre comment utiliser une partie des fonctions de regroupement et de classement fournies par défaut par DMX.</span><span class="sxs-lookup"><span data-stu-id="98fb5-184">This example demonstrates how to use some of the grouping and ordering functions that DMX provides by default.</span></span> <span data-ttu-id="98fb5-185">La requête retourne les 10 premiers jeux d'éléments issus du classement selon la prise en charge pour chaque nœud.</span><span class="sxs-lookup"><span data-stu-id="98fb5-185">The query returns the top 10 itemsets when ordered by the support for each node.</span></span> <span data-ttu-id="98fb5-186">Notez que vous n'avez pas besoin de regrouper les résultats explicitement comme vous le feriez dans Transact-SQL ; toutefois, vous pouvez utiliser une seule fonction d'agrégation dans chaque requête.</span><span class="sxs-lookup"><span data-stu-id="98fb5-186">Note that you do not need to explicitly group the results, as you would in Transact-SQL; however, you can use only one aggregate function in each query.</span></span>  
  
```  
SELECT TOP 10 (NODE_SUPPORT),NODE_NAME, NODE_CAPTION  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="98fb5-187">Résultats de l'exemple :</span><span class="sxs-lookup"><span data-stu-id="98fb5-187">Example results:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98fb5-188">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="98fb5-188">NODE_SUPPORT</span></span>|<span data-ttu-id="98fb5-189">4334</span><span class="sxs-lookup"><span data-stu-id="98fb5-189">4334</span></span>|  
|<span data-ttu-id="98fb5-190">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="98fb5-190">NODE_NAME</span></span>|<span data-ttu-id="98fb5-191">37</span><span class="sxs-lookup"><span data-stu-id="98fb5-191">37</span></span>|  
|<span data-ttu-id="98fb5-192">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="98fb5-192">NODE_CAPTION</span></span>|<span data-ttu-id="98fb5-193">Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="98fb5-193">Sport-100 = Existing</span></span>|  
  
 [<span data-ttu-id="98fb5-194">Retour au début</span><span class="sxs-lookup"><span data-stu-id="98fb5-194">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="making-predictions-using-the-model"></a><span data-ttu-id="98fb5-195">Exécution de prédictions à l'aide du modèle</span><span class="sxs-lookup"><span data-stu-id="98fb5-195">Making Predictions using the Model</span></span>  
 <span data-ttu-id="98fb5-196">Un modèle de règles d'association est souvent utilisé pour générer recommandations qui sont basées sur les corrélations découvertes dans les jeux d'éléments.</span><span class="sxs-lookup"><span data-stu-id="98fb5-196">An association rules model is often used to generate recommendations, which are based on correlations discovered in the itemsets.</span></span> <span data-ttu-id="98fb5-197">Par conséquent, lorsque vous créez une requête de prédiction basée sur un modèle de règles d'association, vous utilisez en général les règles dans le modèle pour faire des estimations basées sur les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="98fb5-197">Therefore, when you create a prediction query based on an association rules model, you are typically using the rules in the model to make guesses based on new data.</span></span>  <span data-ttu-id="98fb5-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) est la fonction qui retourne des recommandations et possède plusieurs arguments que vous pouvez utiliser pour personnaliser les résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="98fb5-198">[PredictAssociation &#40;DMX&#41;](/sql/dmx/predictassociation-dmx) is the function that returns recommendations, and has several arguments that you can use to customize the query results.</span></span>  
  
 <span data-ttu-id="98fb5-199">Les requêtes sur un modèle d'association peuvent aussi être utiles pour retourner par exemple la confiance pour des règles et des jeux d'éléments afin de comparer l'efficacité de différentes stratégies de ventes croisées.</span><span class="sxs-lookup"><span data-stu-id="98fb5-199">Another example of where queries on an association model might be useful is to return the confidence for various rules and itemsets so that you can compare the effectiveness of different cross-sell strategies.</span></span> <span data-ttu-id="98fb5-200">Les exemples suivants illustrent comment créer de telles requêtes.</span><span class="sxs-lookup"><span data-stu-id="98fb5-200">The following examples illustrate how to create such queries.</span></span>  
  
###  <a name="sample-query-6-predicting-associated-items"></a><a name="bkmk_Query6"></a> <span data-ttu-id="98fb5-201">Exemple de requête 6 : prédiction d'éléments associés</span><span class="sxs-lookup"><span data-stu-id="98fb5-201">Sample Query 6: Predicting Associated Items</span></span>  
 <span data-ttu-id="98fb5-202">Cet exemple utilise le modèle d’association créé dans le [Didacticiel sur l’exploration de données intermédiaire &#40;Analysis Services - Exploration de données&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="98fb5-202">This example uses the Association model created in the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="98fb5-203">Il montre comment créer une requête de prédiction qui indique les produits à recommander à un client ayant acheté un produit particulier.</span><span class="sxs-lookup"><span data-stu-id="98fb5-203">It demonstrates how to create a prediction query that tells you what products to recommend to a customer who has purchased a particular product.</span></span> <span data-ttu-id="98fb5-204">Ce type de requête, dans lequel vous fournissez des valeurs au modèle dans une instruction `SELECT...UNION`, est appelé « requête singleton ».</span><span class="sxs-lookup"><span data-stu-id="98fb5-204">This type of query, where you provide values to the model in a `SELECT...UNION` statement, is called a singleton query.</span></span> <span data-ttu-id="98fb5-205">La colonne du modèle prévisible qui correspond aux nouvelles valeurs étant une table imbriquée, vous devez utiliser une clause `SELECT` pour mapper la nouvelle valeur à la colonne de table imbriquée, `[Model]`, et une autre clause `SELECT` pour mapper la colonne de table imbriquée à la colonne de niveau de cas, `[v Assoc Seq Line Items]`.</span><span class="sxs-lookup"><span data-stu-id="98fb5-205">Because the predictable model column that corresponds to the new values is a nested table, you must use one `SELECT` clause to map the new value to the nested table column, `[Model]`, and another `SELECT` clause to map the nested table column to the case-level column, `[v Assoc Seq Line Items]`.</span></span> <span data-ttu-id="98fb5-206">L'ajout du mot clé INCLUDE-STATISTICS à la requête vous permet de voir la probabilité et la prise en charge pour les recommandations.</span><span class="sxs-lookup"><span data-stu-id="98fb5-206">Adding the keyword INCLUDE-STATISTICS to the query lets you see the probability and support for the recommendations.</span></span>  
  
```  
SELECT PredictAssociation([Association].[vAssocSeqLineItems],INCLUDE_STATISTICS, 3)  
FROM [Association]  
NATURAL PREDICTION JOIN   
(SELECT  
(SELECT 'Classic Vest' as [Model])  
AS [v Assoc Seq Line Items])  
AS t  
```  
  
 <span data-ttu-id="98fb5-207">Résultats de l'exemple :</span><span class="sxs-lookup"><span data-stu-id="98fb5-207">Example results:</span></span>  
  
|<span data-ttu-id="98fb5-208">Modèle</span><span class="sxs-lookup"><span data-stu-id="98fb5-208">Model</span></span>|<span data-ttu-id="98fb5-209">$SUPPORT</span><span class="sxs-lookup"><span data-stu-id="98fb5-209">$SUPPORT</span></span>|<span data-ttu-id="98fb5-210">$PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="98fb5-210">$PROBABILITY</span></span>|<span data-ttu-id="98fb5-211">$ADJUSTEDPROBABILITY</span><span class="sxs-lookup"><span data-stu-id="98fb5-211">$ADJUSTEDPROBABILITY</span></span>|  
|-----------|--------------|------------------|--------------------------|  
|<span data-ttu-id="98fb5-212">Sport-100</span><span class="sxs-lookup"><span data-stu-id="98fb5-212">Sport-100</span></span>|<span data-ttu-id="98fb5-213">4334</span><span class="sxs-lookup"><span data-stu-id="98fb5-213">4334</span></span>|<span data-ttu-id="98fb5-214">0.291283</span><span class="sxs-lookup"><span data-stu-id="98fb5-214">0.291283</span></span>|<span data-ttu-id="98fb5-215">0.252696</span><span class="sxs-lookup"><span data-stu-id="98fb5-215">0.252696</span></span>|  
|<span data-ttu-id="98fb5-216">Water Bottle</span><span class="sxs-lookup"><span data-stu-id="98fb5-216">Water Bottle</span></span>|<span data-ttu-id="98fb5-217">2866</span><span class="sxs-lookup"><span data-stu-id="98fb5-217">2866</span></span>|<span data-ttu-id="98fb5-218">0.19262</span><span class="sxs-lookup"><span data-stu-id="98fb5-218">0.19262</span></span>|<span data-ttu-id="98fb5-219">0.175205</span><span class="sxs-lookup"><span data-stu-id="98fb5-219">0.175205</span></span>|  
|<span data-ttu-id="98fb5-220">Patch kit</span><span class="sxs-lookup"><span data-stu-id="98fb5-220">Patch kit</span></span>|<span data-ttu-id="98fb5-221">2113</span><span class="sxs-lookup"><span data-stu-id="98fb5-221">2113</span></span>|<span data-ttu-id="98fb5-222">0.142012</span><span class="sxs-lookup"><span data-stu-id="98fb5-222">0.142012</span></span>|<span data-ttu-id="98fb5-223">0.132389</span><span class="sxs-lookup"><span data-stu-id="98fb5-223">0.132389</span></span>|  
  
 [<span data-ttu-id="98fb5-224">Retour au début</span><span class="sxs-lookup"><span data-stu-id="98fb5-224">Return to Top</span></span>](#bkmk_top2)  
  
###  <a name="sample-query-7-determining-confidence-for-related-itemsets"></a><a name="bkmk_Query7"></a> <span data-ttu-id="98fb5-225">Exemple de requête 7 : identification de la confiance pour les jeux d'éléments connexes</span><span class="sxs-lookup"><span data-stu-id="98fb5-225">Sample Query 7: Determining Confidence for Related Itemsets</span></span>  
 <span data-ttu-id="98fb5-226">Si les règles sont utiles pour générer des recommandations, les jeux d'éléments sont plus intéressants pour effectuer une analyse plus poussée des séquences dans le jeu de données.</span><span class="sxs-lookup"><span data-stu-id="98fb5-226">Whereas rules are useful for generating recommendations, itemsets are more interesting for deeper analysis of the patterns in the data set.</span></span> <span data-ttu-id="98fb5-227">Par exemple, si vous n'êtes pas satisfait de la recommandation retournée par la requête de l'exemple précédent, vous pouvez examiner d'autres jeux d'éléments qui contiennent le produit A pour savoir avec plus de certitude si le produit A est un accessoire que les gens ont tendance à acheter avec tous les types de produits ou si le produit A est en forte corrélation avec les achats de produits particuliers.</span><span class="sxs-lookup"><span data-stu-id="98fb5-227">For example, if you were not satisfied with the recommendation that are returned by the previous sample query, you could examine other itemsets that contain Product A, to can get a better idea of whether Product A is an accessory that people tend to buy with all kinds of products, or whether A is strongly correlated with purchases of particular products.</span></span> <span data-ttu-id="98fb5-228">Le moyen le plus simple d'explorer ces relations consiste à filtrer les jeux d'éléments dans la Visionneuse d'associations [!INCLUDE[msCoName](../../includes/msconame-md.md)] ; toutefois, vous pouvez récupérer les mêmes informations avec une requête.</span><span class="sxs-lookup"><span data-stu-id="98fb5-228">The easiest way to explore these relationships is by filtering the itemsets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Viewer; however, you can retrieve the same information with a query.</span></span>  
  
 <span data-ttu-id="98fb5-229">L'exemple de requête suivant retourne tous les jeux d'éléments qui incluent l'élément Water Bottle, y compris l'élément unique Water Bottle.</span><span class="sxs-lookup"><span data-stu-id="98fb5-229">The following sample query returns all itemsets that include the Water Bottle item, including the single item Water bottle.</span></span>  
  
```  
SELECT TOP 100 FROM   
(  
SELECT FLATTENED NODE_CAPTION, NODE_SUPPORT,   
(SELECT ATTRIBUTE_NAME from NODE_DISTRIBUTION  
WHERE ATTRIBUTE_NAME = 'v Assoc Seq Line Items(Water Bottle)') as D  
FROM Association.CONTENT  
WHERE NODE_TYPE = 7  
) AS Items  
WHERE [D.ATTRIBUTE_NAME] <> NULL  
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="98fb5-230">Résultats de l'exemple :</span><span class="sxs-lookup"><span data-stu-id="98fb5-230">Example results:</span></span>  
  
|<span data-ttu-id="98fb5-231">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="98fb5-231">NODE_CAPTION</span></span>|<span data-ttu-id="98fb5-232">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="98fb5-232">NODE_SUPPORT</span></span>|<span data-ttu-id="98fb5-233">D.ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="98fb5-233">D.ATTRIBUTE_NAME</span></span>|  
|-------------------|-------------------|-----------------------|  
|<span data-ttu-id="98fb5-234">Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="98fb5-234">Water Bottle = Existing</span></span>|<span data-ttu-id="98fb5-235">2866</span><span class="sxs-lookup"><span data-stu-id="98fb5-235">2866</span></span>|<span data-ttu-id="98fb5-236">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="98fb5-236">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="98fb5-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="98fb5-237">Mountain Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="98fb5-238">1136</span><span class="sxs-lookup"><span data-stu-id="98fb5-238">1136</span></span>|<span data-ttu-id="98fb5-239">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="98fb5-239">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="98fb5-240">Road Bottle Cage = Existing, Water Bottle = Existing</span><span class="sxs-lookup"><span data-stu-id="98fb5-240">Road Bottle Cage = Existing, Water Bottle = Existing</span></span>|<span data-ttu-id="98fb5-241">1068</span><span class="sxs-lookup"><span data-stu-id="98fb5-241">1068</span></span>|<span data-ttu-id="98fb5-242">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="98fb5-242">v Assoc Seq Line Items(Water Bottle)</span></span>|  
|<span data-ttu-id="98fb5-243">Water Bottle = Existing, Sport-100 = Existing</span><span class="sxs-lookup"><span data-stu-id="98fb5-243">Water Bottle = Existing, Sport-100 = Existing</span></span>|<span data-ttu-id="98fb5-244">734</span><span class="sxs-lookup"><span data-stu-id="98fb5-244">734</span></span>|<span data-ttu-id="98fb5-245">v Assoc Seq Line Items(Water Bottle)</span><span class="sxs-lookup"><span data-stu-id="98fb5-245">v Assoc Seq Line Items(Water Bottle)</span></span>|  
  
 <span data-ttu-id="98fb5-246">Cette requête retourne les deux lignes de la table imbriquée qui correspondent aux critères, et toutes les lignes de l’extérieur ou de la table de cas.</span><span class="sxs-lookup"><span data-stu-id="98fb5-246">This query returns both the rows from the nested table that match the criteria, and all the rows from the outside or case table.</span></span> <span data-ttu-id="98fb5-247">Par conséquent, vous devez ajouter une condition qui élimine les lignes de table de cas dont le nom d'attribut cible a la valeur Null.</span><span class="sxs-lookup"><span data-stu-id="98fb5-247">Therefore, you must add a condition that eliminates the case table rows that have a null value for the target attribute name.</span></span>  
  
 [<span data-ttu-id="98fb5-248">Retour au début</span><span class="sxs-lookup"><span data-stu-id="98fb5-248">Return to Top</span></span>](#bkmk_top2)  
  
## <a name="function-list"></a><span data-ttu-id="98fb5-249">Liste de fonctions</span><span class="sxs-lookup"><span data-stu-id="98fb5-249">Function List</span></span>  
 <span data-ttu-id="98fb5-250">Tous les algorithmes [!INCLUDE[msCoName](../../includes/msconame-md.md)] prennent en charge un ensemble commun de fonctions.</span><span class="sxs-lookup"><span data-stu-id="98fb5-250">All [!INCLUDE[msCoName](../../includes/msconame-md.md)] algorithms support a common set of functions.</span></span> <span data-ttu-id="98fb5-251">Toutefois, l'algorithme [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association prend en charge les fonctions supplémentaires répertoriées dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="98fb5-251">However, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association algorithm supports the additional functions listed in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98fb5-252">Fonction de prédiction</span><span class="sxs-lookup"><span data-stu-id="98fb5-252">Prediction Function</span></span>|<span data-ttu-id="98fb5-253">Usage</span><span class="sxs-lookup"><span data-stu-id="98fb5-253">Usage</span></span>|  
|[<span data-ttu-id="98fb5-254">IsDescendant &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="98fb5-254">IsDescendant &#40;DMX&#41;</span></span>](/sql/dmx/isdescendant-dmx)|<span data-ttu-id="98fb5-255">Détermine si un nœud est un enfant d'un autre nœud dans le graphique de réseau neuronal.</span><span class="sxs-lookup"><span data-stu-id="98fb5-255">Determines whether one node is a child of another node in the neural network graph.</span></span>|  
|[<span data-ttu-id="98fb5-256">IsInNode &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="98fb5-256">IsInNode &#40;DMX&#41;</span></span>](/sql/dmx/isinnode-dmx)|<span data-ttu-id="98fb5-257">Indique si le nœud spécifié contient le cas courant.</span><span class="sxs-lookup"><span data-stu-id="98fb5-257">Indicates whether the specified node contains the current case.</span></span>|  
|[<span data-ttu-id="98fb5-258">PredictAdjustedProbability &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="98fb5-258">PredictAdjustedProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictadjustedprobability-dmx)|<span data-ttu-id="98fb5-259">Retourne la probabilité pondérée.</span><span class="sxs-lookup"><span data-stu-id="98fb5-259">Returns the weighted probability.</span></span>|  
|[<span data-ttu-id="98fb5-260">PredictAssociation &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="98fb5-260">PredictAssociation &#40;DMX&#41;</span></span>](/sql/dmx/predictassociation-dmx)|<span data-ttu-id="98fb5-261">Prédit l'appartenance à un dataset associatif.</span><span class="sxs-lookup"><span data-stu-id="98fb5-261">Predicts membership in an associative dataset.</span></span>|  
|[<span data-ttu-id="98fb5-262">PredictHistogram &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="98fb5-262">PredictHistogram &#40;DMX&#41;</span></span>](/sql/dmx/predicthistogram-dmx)|<span data-ttu-id="98fb5-263">Retourne une table des valeurs associées à la valeur prédite actuelle.</span><span class="sxs-lookup"><span data-stu-id="98fb5-263">Returns a table of values related to the current predicted value.</span></span>|  
|[<span data-ttu-id="98fb5-264">PredictNodeId &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="98fb5-264">PredictNodeId &#40;DMX&#41;</span></span>](/sql/dmx/predictnodeid-dmx)|<span data-ttu-id="98fb5-265">Retourne Node_ID pour chaque cas.</span><span class="sxs-lookup"><span data-stu-id="98fb5-265">Returns the Node_ID for each case.</span></span>|  
|[<span data-ttu-id="98fb5-266">PredictProbability &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="98fb5-266">PredictProbability &#40;DMX&#41;</span></span>](/sql/dmx/predictprobability-dmx)|<span data-ttu-id="98fb5-267">Retourne la probabilité pour la valeur prédite.</span><span class="sxs-lookup"><span data-stu-id="98fb5-267">Returns probability for the predicted value.</span></span>|  
|[<span data-ttu-id="98fb5-268">PredictSupport &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="98fb5-268">PredictSupport &#40;DMX&#41;</span></span>](/sql/dmx/predictsupport-dmx)|<span data-ttu-id="98fb5-269">Retourne la valeur de support pour un état spécifié.</span><span class="sxs-lookup"><span data-stu-id="98fb5-269">Returns the support value for a specified state.</span></span>|  
|[<span data-ttu-id="98fb5-270">PredictVariance &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="98fb5-270">PredictVariance &#40;DMX&#41;</span></span>](/sql/dmx/predictvariance-dmx)|<span data-ttu-id="98fb5-271">Retourne la variance de la valeur prédite.</span><span class="sxs-lookup"><span data-stu-id="98fb5-271">Returns variance for the predicted value.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98fb5-272">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98fb5-272">See Also</span></span>  
 <span data-ttu-id="98fb5-273">[Algorithme d’association Microsoft](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="98fb5-273">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 <span data-ttu-id="98fb5-274">[Référence technique de l’algorithme Microsoft Association](microsoft-association-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="98fb5-274">[Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="98fb5-275">Contenu du modèle d’exploration de données pour les modèles d’association &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="98fb5-275">Mining Model Content for Association Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-association-models-analysis-services-data-mining.md)  
  
  
