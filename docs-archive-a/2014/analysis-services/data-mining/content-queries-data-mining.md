---
title: Requêtes de contenu (exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c4f4a5a8-a230-4222-bece-9d563501f65f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44b162c34f5f505462a713205d8434484473afa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614918"
---
# <a name="content-queries-data-mining"></a><span data-ttu-id="fa75d-102">Requêtes de contenu (Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="fa75d-102">Content Queries (Data Mining)</span></span>
  <span data-ttu-id="fa75d-103">Une requête de contenu est une façon d'extraire des informations sur les statistiques internes et la structure du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="fa75d-103">A content query is a way of extracting information about the internal statistics and structure of the mining model.</span></span> <span data-ttu-id="fa75d-104">Parfois, une requête de contenu peut fournir des détails qui ne sont pas aisément disponibles dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="fa75d-104">Sometimes a content query can provide details that are not readily available in the viewer.</span></span> <span data-ttu-id="fa75d-105">Vous pouvez également utiliser les résultats d'une requête de contenu pour extraire des informations par programme pour d'autres utilisations.</span><span class="sxs-lookup"><span data-stu-id="fa75d-105">You can also use the results of a content query to extract information programmatically for other uses.</span></span>  
  
 <span data-ttu-id="fa75d-106">Cette section fournit des informations générales sur les types d'informations que vous pouvez récupérer à l'aide d'une requête de contenu, ainsi que la syntaxe DMX générale pour les requêtes de contenu.</span><span class="sxs-lookup"><span data-stu-id="fa75d-106">This section provides general information about the types of information that you can retrieve by using a content query, and the general DMX syntax for content queries.</span></span>  
  
 [<span data-ttu-id="fa75d-107">Requêtes de contenu de base</span><span class="sxs-lookup"><span data-stu-id="fa75d-107">Basic Content Queries</span></span>](#bkmk_ContentQuery)  
  
-   [<span data-ttu-id="fa75d-108">Requêtes sur les données de structure et de cas</span><span class="sxs-lookup"><span data-stu-id="fa75d-108">Queries on Structure and Case Data</span></span>](#bkmk_Structure)  
  
-   [<span data-ttu-id="fa75d-109">Requêtes sur les schémas de modèle</span><span class="sxs-lookup"><span data-stu-id="fa75d-109">Queries on Model Patterns</span></span>](#bkmk_Patterns)  
  
 [<span data-ttu-id="fa75d-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="fa75d-110">Examples</span></span>](#bkmk_Examples)  
  
-   [<span data-ttu-id="fa75d-111">Requête de contenu sur un modèle d'association</span><span class="sxs-lookup"><span data-stu-id="fa75d-111">Content Query on an Association Model</span></span>](#bkmk_Assoc)  
  
-   [<span data-ttu-id="fa75d-112">Requête de contenu sur un modèle d'arbre de décision</span><span class="sxs-lookup"><span data-stu-id="fa75d-112">Content Query on a Decision Trees Model</span></span>](#bkmk_DecTree)  
  
 [<span data-ttu-id="fa75d-113">Utilisation des résultats de requête</span><span class="sxs-lookup"><span data-stu-id="fa75d-113">Working with the Query Results</span></span>](#bkmk_Results)  
  
##  <a name="basic-content-queries"></a><a name="bkmk_ContentQuery"></a><span data-ttu-id="fa75d-114">Requêtes de contenu de base</span><span class="sxs-lookup"><span data-stu-id="fa75d-114">Basic Content Queries</span></span>  
 <span data-ttu-id="fa75d-115">Vous pouvez créer des requêtes de contenu à l'aide du générateur de requêtes de prédiction, utiliser les modèles de requête de contenu DMX fournis dans SQL Server Management Studio ou écrire des requêtes directement dans DMX.</span><span class="sxs-lookup"><span data-stu-id="fa75d-115">You can create content queries by using the Prediction Query Builder, use the DMX content query templates that are provided in SQL Server Management Studio, or write queries directly in DMX.</span></span> <span data-ttu-id="fa75d-116">Contrairement aux requêtes de prédiction, vous n'avez pas besoin de joindre des données externes ; il est donc facile d'écrire des requêtes de contenu.</span><span class="sxs-lookup"><span data-stu-id="fa75d-116">Unlike prediction queries you do not need to join external data, so content queries are easy to write.</span></span>  
  
 <span data-ttu-id="fa75d-117">Cette section fournit une vue d'ensemble des types de requêtes de contenu que vous pouvez créer.</span><span class="sxs-lookup"><span data-stu-id="fa75d-117">This section provides an overview of the types of content queries you can create.</span></span>  
  
-   <span data-ttu-id="fa75d-118">Les requêtes sur la structure d'exploration de données ou les données de cas vous permettent d'afficher les données détaillées utilisées pour l'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="fa75d-118">Queries on the mining structure or case data let you view the detailed data that was used for training.</span></span>  
  
-   <span data-ttu-id="fa75d-119">Les requêtes sur le modèle peuvent retourner des schémas, des listes d'attributs, des formules, etc.</span><span class="sxs-lookup"><span data-stu-id="fa75d-119">Queries on the model can return patterns, lists of attributes, formulas, and so forth.</span></span>  
  
###  <a name="queries-on-structure-and-case-data"></a><a name="bkmk_Structure"></a> <span data-ttu-id="fa75d-120">Requêtes sur les données de cas et de structure</span><span class="sxs-lookup"><span data-stu-id="fa75d-120">Queries on Structure and Case Data</span></span>  
 <span data-ttu-id="fa75d-121">DMX prend en charge des requêtes sur les données mises en cache utilisées pour créer des structures et des modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="fa75d-121">DMX supports queries on the cached data that is used to build mining structures and models.</span></span> <span data-ttu-id="fa75d-122">Par défaut, ce cache est créé lorsque vous définissez la structure d'exploration de données et est rempli lorsque vous traitez la structure ou le modèle.</span><span class="sxs-lookup"><span data-stu-id="fa75d-122">By default, this cache is created when you define the mining structure, and is populated when you process the structure or model.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="fa75d-123">Ce cache ne peut pas être effacé ni supprimé si vous avez besoin de données distinctes dans les jeux d'apprentissage et de test.</span><span class="sxs-lookup"><span data-stu-id="fa75d-123">This cache cannot be cleared or deleted if you need to separate data into training and testing sets.</span></span> <span data-ttu-id="fa75d-124">Si le cache est supprimé, vous ne pouvez pas interroger les données de cas.</span><span class="sxs-lookup"><span data-stu-id="fa75d-124">If the cache is cleared, you cannot query the case data.</span></span>  
  
 <span data-ttu-id="fa75d-125">Les exemples suivants illustrent les schémas courants pour créer des requêtes sur les données de cas ou des requêtes sur les données de la structure d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="fa75d-125">The following examples show the common patterns for creating queries on the case data, or queries on the data in the mining structure:</span></span>  
  
 <span data-ttu-id="fa75d-126">**Obtenir toutes les cas d'un modèle**</span><span class="sxs-lookup"><span data-stu-id="fa75d-126">**Get all the cases for a model**</span></span>  
 `SELECT FROM <model>.CASES`  
  
 <span data-ttu-id="fa75d-127">Utilisez cette instruction pour récupérer les colonnes spécifiées des données de cas utilisées pour générer un modèle.</span><span class="sxs-lookup"><span data-stu-id="fa75d-127">Use this statement to retrieve specified columns from the case data used to build a model.</span></span> <span data-ttu-id="fa75d-128">Vous devez disposer d'autorisations d'extraction sur le modèle pour exécuter cette requête.</span><span class="sxs-lookup"><span data-stu-id="fa75d-128">You must have drillthrough permissions on the model to run this query.</span></span>  
  
 <span data-ttu-id="fa75d-129">**Afficher toutes les données incluses dans la structure**</span><span class="sxs-lookup"><span data-stu-id="fa75d-129">**View all the data that is included in the structure**</span></span>  
 `SELECT FROM <structure>.CASES`  
  
 <span data-ttu-id="fa75d-130">Utiliser cette instruction pour afficher toutes les données incluses dans la structure, y compris les colonnes qui ne sont pas incluses dans un modèle d'exploration de données particulier.</span><span class="sxs-lookup"><span data-stu-id="fa75d-130">Use this statement to view all the data that is included in the structure, including columns that are not included in a particular mining model.</span></span> <span data-ttu-id="fa75d-131">Vous devez disposer d'autorisations d'extraction sur le modèle, ainsi que sur la structure, afin de récupérer des données de la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="fa75d-131">You must have drillthrough permissions on the model, as well as on the structure, to retrieve data from the mining structure.</span></span>  
  
 <span data-ttu-id="fa75d-132">**Obtenir une plage de valeurs**</span><span class="sxs-lookup"><span data-stu-id="fa75d-132">**Get range of values**</span></span>  
 `SELECT DISTINCT RangeMin(<column>), RangeMax(<column>) FROM <model>`  
  
 <span data-ttu-id="fa75d-133">Utilisez cette instruction pour rechercher la valeur minimale, la valeur maximale et la moyenne d'une colonne continue, ou des compartiments d'une colonne discrétisée.</span><span class="sxs-lookup"><span data-stu-id="fa75d-133">Use this statement to find the minimum value, maximum value, and mean of a continuous column, or of the buckets of a DISCRETIZED column.</span></span>  
  
 <span data-ttu-id="fa75d-134">**Obtenir des valeurs distinctes**</span><span class="sxs-lookup"><span data-stu-id="fa75d-134">**Get distinct values**</span></span>  
 `SELECT DISTINCT <column>FROM <model>`  
  
 <span data-ttu-id="fa75d-135">Utilisez cette instruction pour récupérer toutes les valeurs d'une colonne DISCRÈTE.</span><span class="sxs-lookup"><span data-stu-id="fa75d-135">Use this statement to retrieve all the values of a DISCRETE column.</span></span>  <span data-ttu-id="fa75d-136">N'utilisez pas cette instruction pour les colonnes discrétisées ; utilisez à la place les fonctions `RangeMin` et `RangeMax`.</span><span class="sxs-lookup"><span data-stu-id="fa75d-136">Do not use this statement for DISCRETIZED columns; use the `RangeMin` and `RangeMax` functions instead.</span></span>  
  
 <span data-ttu-id="fa75d-137">**Rechercher les cas utilisés pour l'apprentissage d'un modèle ou d'une structure**</span><span class="sxs-lookup"><span data-stu-id="fa75d-137">**Find the cases that were used to train a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTrainingCase()`  
  
 <span data-ttu-id="fa75d-138">Utilisez cette instruction pour obtenir le jeu complet de données qui ont été utilisées dans l'apprentissage d'un modèle.</span><span class="sxs-lookup"><span data-stu-id="fa75d-138">Use this statement to get the complete set of data that was used in a training a model.</span></span>  
  
 <span data-ttu-id="fa75d-139">**Rechercher les cas utilisés pour tester un modèle ou une structure**</span><span class="sxs-lookup"><span data-stu-id="fa75d-139">**Find the cases that are used for testing a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTestingCase()`  
  
 <span data-ttu-id="fa75d-140">Utilisez cette instruction pour obtenir les données qui ont été mises de côté pour tester des modèles d'exploration de données associés à une structure spécifique.</span><span class="sxs-lookup"><span data-stu-id="fa75d-140">Use this statement to get the data that has been set aside for testing mining models related to a specific structure.</span></span>  
  
 <span data-ttu-id="fa75d-141">**Extraction d'un schéma de modèle spécifique vers des données de cas sous-jacentes**</span><span class="sxs-lookup"><span data-stu-id="fa75d-141">**Drillthrough from a specific model pattern to underlying case data**</span></span>  
 `SELECT FROM <model>.CASESWHERE IsTrainingCase() AND IsInNode(<node>)`  
  
 <span data-ttu-id="fa75d-142">Utilisez cette instruction pour récupérer des données de cas détaillées d'un modèle ayant fait l'objet d'un apprentissage.</span><span class="sxs-lookup"><span data-stu-id="fa75d-142">Use this statement to retrieve detailed case data from a trained model.</span></span> <span data-ttu-id="fa75d-143">Vous devez spécifier un nœud spécifique : par exemple, vous devez connaître l'ID de nœud du cluster, la branche spécifique de l'arbre de décision, etc. De plus, vous devez disposer d'autorisations d'extraction sur le modèle pour exécuter cette requête.</span><span class="sxs-lookup"><span data-stu-id="fa75d-143">You must specify a specific node: for example, you must know the node ID of the cluster, the specific branch of the decision tree, etc. Moreover, you must have drillthrough permissions on the model to run this query.</span></span>  
  
###  <a name="queries-on-model-patterns-statistics-and-attributes"></a><a name="bkmk_Patterns"></a><span data-ttu-id="fa75d-144">Requêtes sur les modèles de modèle, les statistiques et les attributs</span><span class="sxs-lookup"><span data-stu-id="fa75d-144">Queries on Model Patterns, Statistics, and Attributes</span></span>  
 <span data-ttu-id="fa75d-145">Le contenu d'un modèle d'exploration de données est utile à de nombreuses fins.</span><span class="sxs-lookup"><span data-stu-id="fa75d-145">The content of a data mining model is useful for many purposes.</span></span> <span data-ttu-id="fa75d-146">Avec une requête de contenu de modèle, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fa75d-146">With a model content query, you can:</span></span>  
  
-   <span data-ttu-id="fa75d-147">Extraire les formules ou les probabilités permettant d'effectuer vos propres calculs.</span><span class="sxs-lookup"><span data-stu-id="fa75d-147">Extract formulas or probabilities for making your own calculations.</span></span>  
  
-   <span data-ttu-id="fa75d-148">Pour un modèle d'association, récupérer les règles utilisées pour générer une prédiction.</span><span class="sxs-lookup"><span data-stu-id="fa75d-148">For an association model, retrieve the rules that are used to generate a prediction.</span></span>  
  
-   <span data-ttu-id="fa75d-149">Récupérer les descriptions de règles spécifiques afin que vous puissiez utiliser les règles dans une application personnalisée.</span><span class="sxs-lookup"><span data-stu-id="fa75d-149">Retrieve the descriptions of specific rules so that you can use the rules in a custom application.</span></span>  
  
-   <span data-ttu-id="fa75d-150">Afficher les moyennes mobiles détectées par un modèle de série chronologique.</span><span class="sxs-lookup"><span data-stu-id="fa75d-150">View the moving averages detected by a time series model.</span></span>  
  
-   <span data-ttu-id="fa75d-151">Obtenir la formule de régression pour plusieurs segments de la courbe de tendance.</span><span class="sxs-lookup"><span data-stu-id="fa75d-151">Obtain the regression formula for some segment of the trend line.</span></span>  
  
-   <span data-ttu-id="fa75d-152">Récupérer des informations utilisables sur les clients identifiés comme faisant partie d'un cluster spécifique.</span><span class="sxs-lookup"><span data-stu-id="fa75d-152">Retrieve actionable information about customers identified as being part of a specific cluster.</span></span>  
  
 <span data-ttu-id="fa75d-153">Les exemples suivants montrent certains schémas courants pour créer des requêtes sur le contenu du modèle :</span><span class="sxs-lookup"><span data-stu-id="fa75d-153">The following examples show some of the common patterns for creating queries on the model content:</span></span>  
  
 <span data-ttu-id="fa75d-154">**Obtenir des schémas du modèle**</span><span class="sxs-lookup"><span data-stu-id="fa75d-154">**Get patterns from the model**</span></span>  
 `SELECT FROM <model>.CONTENT`  
  
 <span data-ttu-id="fa75d-155">Utilisez cette instruction pour récupérer des informations détaillées sur les nœuds spécifiques dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="fa75d-155">Use this statement to retrieve detailed information about specific nodes in the model.</span></span> <span data-ttu-id="fa75d-156">Selon le type d'algorithme, le nœud peut contenir des règles et des formules, des statistiques de variance et de prise en charge, etc.</span><span class="sxs-lookup"><span data-stu-id="fa75d-156">Depending on the algorithm type, the node can contain rules and formulas, support and variance statistics, and so forth.</span></span>  
  
 <span data-ttu-id="fa75d-157">**Récupérer des attributs utilisés dans un modèle ayant fait l'objet d'un apprentissage**</span><span class="sxs-lookup"><span data-stu-id="fa75d-157">**Retrieve attributes used in a trained model**</span></span>  
 `CALL System.GetModelAttributes(<model>)`  
  
 <span data-ttu-id="fa75d-158">Utilisez cette procédure stockée pour récupérer la liste des attributs utilisés par un modèle.</span><span class="sxs-lookup"><span data-stu-id="fa75d-158">Use this stored procedure to retrieve the list of attributes that were used by a model.</span></span> <span data-ttu-id="fa75d-159">Ces informations sont utiles pour déterminer les attributs qui ont été éliminés en raison de la sélection des fonctionnalités, par exemple.</span><span class="sxs-lookup"><span data-stu-id="fa75d-159">This information is useful for determining attributes that were eliminated as a result of feature selection, for example.</span></span>  
  
 <span data-ttu-id="fa75d-160">**Récupérer le contenu stocké dans une dimension d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="fa75d-160">**Retrieve content stored in a data mining dimension**</span></span>  
 `SELECT FROM <model>.DIMENSIONCONTENT`  
  
 <span data-ttu-id="fa75d-161">Utilisez cette instruction pour récupérer les données d'une dimension d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="fa75d-161">Use this statement to retrieve the data from a data mining dimension.</span></span>  
  
 <span data-ttu-id="fa75d-162">Ce type de requête est principalement destiné à une utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="fa75d-162">This query type is principally for internal use.</span></span> <span data-ttu-id="fa75d-163">Toutefois, tous les algorithmes ne prennent pas en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="fa75d-163">However, not all algorithms support this functionality.</span></span> <span data-ttu-id="fa75d-164">La prise en charge est indiquée par un indicateur dans l'ensemble de lignes de schéma MINING_SERVICES.</span><span class="sxs-lookup"><span data-stu-id="fa75d-164">Support is indicated by a flag in the MINING_SERVICES schema rowset.</span></span>  
  
 <span data-ttu-id="fa75d-165">Si vous développez votre propre algorithme de plug-in, vous pouvez utiliser cette instruction pour vérifier le contenu de votre modèle pour le test.</span><span class="sxs-lookup"><span data-stu-id="fa75d-165">If you develop your own plug-in algorithm, you might use this statement to verify the content of your model for testing.</span></span>  
  
 <span data-ttu-id="fa75d-166">**Obtenir la représentation PMML d'un modèle**</span><span class="sxs-lookup"><span data-stu-id="fa75d-166">**Get the PMML representation of a model**</span></span>  
 `SELECT * FROM <model>.PMML`  
  
 <span data-ttu-id="fa75d-167">Obtient un document XML qui représente le modèle au format PMML.</span><span class="sxs-lookup"><span data-stu-id="fa75d-167">Gets an XML document that represents the model in PMML format.</span></span> <span data-ttu-id="fa75d-168">Tous les types de modèle ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="fa75d-168">Not all model types are supported.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_Examples"></a> <span data-ttu-id="fa75d-169">Exemples</span><span class="sxs-lookup"><span data-stu-id="fa75d-169">Examples</span></span>  
 <span data-ttu-id="fa75d-170">Bien que certains contenus de modèle soient standard dans les algorithmes, certaines parties du contenu varient considérablement, selon l'algorithme que vous avez utilisé pour générer le modèle.</span><span class="sxs-lookup"><span data-stu-id="fa75d-170">Although some model content is standard across algorithms, some parts of the content vary greatly depending on the algorithm that you used to build the model.</span></span> <span data-ttu-id="fa75d-171">Par conséquent, lorsque vous créez une requête de contenu, vous devez identifier les types d'informations qui sont les plus utiles dans votre modèle spécifique.</span><span class="sxs-lookup"><span data-stu-id="fa75d-171">Therefore, when you create a content query, you must understand what information in the model is most useful to your specific model.</span></span>  
  
 <span data-ttu-id="fa75d-172">Certains exemples sont fournis dans cette section pour montrer comment le choix de l'algorithme affecte le type d'informations stockées dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="fa75d-172">A few examples are provided in this section to illustrate how the choice of algorithm affects the kind of information that is stored in the model.</span></span> <span data-ttu-id="fa75d-173">Pour plus d’informations sur le contenu du modèle d’exploration de données et sur le contenu spécifique à chaque type de modèle, consultez [Contenu du modèle d’exploration de données &#40;Analysis Services – Exploration de données&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="fa75d-173">For more information about mining model content, and the content that is specific to each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
###  <a name="example-1-content-query-on-an-association-model"></a><a name="bkmk_Assoc"></a> <span data-ttu-id="fa75d-174">Exemple 1 : requête de contenu sur un modèle d'association</span><span class="sxs-lookup"><span data-stu-id="fa75d-174">Example 1: Content Query on an Association Model</span></span>  
 <span data-ttu-id="fa75d-175">L'instruction, `SELECT FROM <model>.CONTENT`, retourne différents types d'informations, selon le type de modèle que vous interrogez.</span><span class="sxs-lookup"><span data-stu-id="fa75d-175">The statement, `SELECT FROM <model>.CONTENT`, returns different kinds of information, depending on the type of model you are querying.</span></span> <span data-ttu-id="fa75d-176">Pour un modèle d'association, le *type de nœud*constitue une information clé.</span><span class="sxs-lookup"><span data-stu-id="fa75d-176">For an association model, a key piece of information is the *node type*.</span></span> <span data-ttu-id="fa75d-177">Les nœuds sont comme des conteneurs pour les informations dans le contenu du modèle.</span><span class="sxs-lookup"><span data-stu-id="fa75d-177">Nodes are like containers for information in the model content.</span></span> <span data-ttu-id="fa75d-178">Dans un modèle d'association, les nœuds qui représentent des règles ont une valeur NODE_TYPE de 8, tandis que les nœuds qui représentent des jeux d'éléments ont une valeur NODE_TYPE de 7.</span><span class="sxs-lookup"><span data-stu-id="fa75d-178">In an association model, nodes that represent rules have a NODE_TYPE value of 8, whereas nodes that represent itemsets have a NODE_TYPE value of 7.</span></span>  
  
 <span data-ttu-id="fa75d-179">Ainsi, la requête suivante retourne les 10 premiers jeux d’éléments, classés par prise en charge (classement par défaut).</span><span class="sxs-lookup"><span data-stu-id="fa75d-179">Thus, the following query returns the top 10 itemsets, ranked by support (the default ordering).</span></span>  
  
```  
SELECT TOP 10 NODE_DESCRIPTION, NODE_PROBABILITY, SUPPORT  
FROM <model>.CONTENT WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="fa75d-180">La requête suivante est générée sur la base de ces informations.</span><span class="sxs-lookup"><span data-stu-id="fa75d-180">The following query builds on this information.</span></span> <span data-ttu-id="fa75d-181">La requête retourne trois colonnes : l’ID du nœud, la règle complète et le produit sur le côté droit du jeu d’éléments, c’est-à-dire le produit qui est prédit pour être associé à d’autres produits dans le cadre d’un jeu d’éléments.</span><span class="sxs-lookup"><span data-stu-id="fa75d-181">The query returns three columns: the ID of the node, the complete rule, and the product on the right-hand side of the itemset-that is, the product that is predicted to be associated with some other products as part of an itemset.</span></span>  
  
```  
SELECT FLATTENED NODE_UNIQUE_NAME, NODE_DESCRIPTION,  
     (SELECT RIGHT(ATTRIBUTE_NAME, (LEN(ATTRIBUTE_NAME)-LEN('Association model name')))   
FROM NODE_DISTRIBUTION  
WHERE LEN(ATTRIBUTE_NAME)>2  
)   
AS RightSideProduct  
FROM [<Association model name>].CONTENT  
WHERE NODE_TYPE = 8   
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="fa75d-182">Le mot clé FLATTENED indique que l'ensemble de lignes imbriqué doit être converti en table aplatie.</span><span class="sxs-lookup"><span data-stu-id="fa75d-182">The FLATTENED keyword indicates that the nested rowset should be converted into a flattened table.</span></span> <span data-ttu-id="fa75d-183">L'attribut qui représente le produit dans la partie droite de la règle est contenu dans la table NODE_DISTRIBUTION ; par conséquent, nous récupérons uniquement la ligne qui contient un nom d'attribut en spécifiant que la longueur doit être supérieure à 2.</span><span class="sxs-lookup"><span data-stu-id="fa75d-183">The attribute that represents the product on the right-hand side of the rule is contained in the NODE_DISTRIBUTION table; therefore, we retrieve only the row that contains an attribute name, by adding a requirement that the length be greater than 2.</span></span>  
  
 <span data-ttu-id="fa75d-184">Une fonction de chaîne simple est utilisée pour supprimer le nom du modèle de la troisième colonne.</span><span class="sxs-lookup"><span data-stu-id="fa75d-184">A simple string function is used to remove the name of the model from the third column.</span></span> <span data-ttu-id="fa75d-185">(En général, le nom du modèle est préfixé avec les valeurs des colonnes imbriquées.)</span><span class="sxs-lookup"><span data-stu-id="fa75d-185">(Usually the model name is prefixed to the values of nested columns.)</span></span>  
  
 <span data-ttu-id="fa75d-186">La clause WHERE spécifie que la valeur de NODE_TYPE doit être 8 pour récupérer uniquement des règles.</span><span class="sxs-lookup"><span data-stu-id="fa75d-186">The WHERE clause specifies that the value of NODE_TYPE should be 8, to retrieve only rules.</span></span>  
  
 <span data-ttu-id="fa75d-187">Pour obtenir plus d’exemples, consultez [Exemples de requête de modèle d’association](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="fa75d-187">For more examples, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
###  <a name="example-2-content-query-on-a-decision-trees-model"></a><a name="bkmk_DecTree"></a> <span data-ttu-id="fa75d-188">Exemple 2 : requête de contenu sur un modèle d'arbre de décision</span><span class="sxs-lookup"><span data-stu-id="fa75d-188">Example 2: Content Query on a Decision Trees Model</span></span>  
 <span data-ttu-id="fa75d-189">Un modèle d'arbre de décision peut être utilisé pour la prédiction ainsi que pour la classification.</span><span class="sxs-lookup"><span data-stu-id="fa75d-189">A decision tree model can be used for prediction as well as for classification.</span></span>  <span data-ttu-id="fa75d-190">Dans cet exemple, on suppose que vous utilisez le modèle pour prédire un résultat, mais vous souhaitez également découvrir quels facteurs ou règles peuvent être utilisés pour classer les résultats.</span><span class="sxs-lookup"><span data-stu-id="fa75d-190">This example assumes that you are using the model to predict an outcome, but you also want to find out which factors or rules can be used to classify the outcome.</span></span>  
  
 <span data-ttu-id="fa75d-191">Dans un modèle d'arbre de décision, les nœuds sont utilisés pour représenter des arbres et des nœuds terminaux.</span><span class="sxs-lookup"><span data-stu-id="fa75d-191">In a decision tree model, nodes are used to represent both trees and leaf nodes.</span></span> <span data-ttu-id="fa75d-192">La légende de chaque nœud contient la description du chemin d'accès au résultat.</span><span class="sxs-lookup"><span data-stu-id="fa75d-192">The caption for each node contains the description of the path to the outcome.</span></span> <span data-ttu-id="fa75d-193">Par conséquent, pour tracer le chemin d'accès d'un résultat particulier, vous devez identifier le nœud qui le contient, et obtenir des détails relatifs à ce nœud.</span><span class="sxs-lookup"><span data-stu-id="fa75d-193">Therefore, to trace the path for any particular outcome, you need to identify the node that contains it, and get the details for that node.</span></span>  
  
 <span data-ttu-id="fa75d-194">Dans votre requête de prédiction, vous ajoutez la fonction de prédiction [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx), afin d’obtenir l’ID du nœud associé, comme le montre l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="fa75d-194">In your prediction query, you add the prediction function [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx), to get the ID of the related node, as shown in the following example:</span></span>  
  
```  
SELECT  Predict([Bike Buyer]), PredictNodeID([Bike Buyer])   
FROM [<decision tree model name>]  
PREDICTION JOIN   
<input rowset>   
```  
  
 <span data-ttu-id="fa75d-195">Une fois que vous avez l'ID du nœud qui contient le résultat, vous pouvez récupérer la règle ou le chemin d'accès qui explique la prédiction en créant une requête de contenu incluant NODE_CAPTION, comme suit :</span><span class="sxs-lookup"><span data-stu-id="fa75d-195">Once you have the ID of the node that contains the outcome, you can retrieve the rule or path that explains the prediction by creating a content query that includes the NODE_CAPTION, as follows:</span></span>  
  
```  
SELECT NODE_CAPTION  
FROM [<decision tree model name>]   
WHERE NODE_UNIQUE_NAME= '<node id>'  
```  
  
 <span data-ttu-id="fa75d-196">Pour obtenir plus d’exemples, consultez [Exemples de requêtes de modèle d’arbre de décision](decision-trees-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="fa75d-196">For more examples, see [Decision Trees Model Query Examples](decision-trees-model-query-examples.md).</span></span>  
  
##  <a name="working-with-the-query-results"></a><a name="bkmk_Results"></a><span data-ttu-id="fa75d-197">Utilisation des résultats de la requête</span><span class="sxs-lookup"><span data-stu-id="fa75d-197">Working with the Query Results</span></span>  
 <span data-ttu-id="fa75d-198">Comme le montrent les exemples, les requêtes de contenu retournent principalement des ensembles de lignes tabulaires, mais ils peuvent également inclure des informations des colonnes imbriquées.</span><span class="sxs-lookup"><span data-stu-id="fa75d-198">As the examples demonstrate, content queries mostly return tabular rowsets, but can also include information from nested columns.</span></span> <span data-ttu-id="fa75d-199">Vous pouvez aplatir l'ensemble de lignes retourné, mais cela peut rendre l'utilisation des résultats plus complexe.</span><span class="sxs-lookup"><span data-stu-id="fa75d-199">You can flatten the rowset that is returned, but this can make working with results more complex.</span></span> <span data-ttu-id="fa75d-200">Le contenu du nœud NODE_DISTRIBUTION en particulier est imbriqué, mais il contient des informations intéressantes sur le modèle.</span><span class="sxs-lookup"><span data-stu-id="fa75d-200">The content of the NODE_DISTRIBUTION node in particular is nested, but contains much interesting information about the model.</span></span>  
  
 <span data-ttu-id="fa75d-201">Pour plus d'informations sur l'utilisation des ensembles de lignes hiérarchiques, consultez la spécification OLEDB sur MSDN.</span><span class="sxs-lookup"><span data-stu-id="fa75d-201">For more information about how to work with hierarchical rowsets, see the OLEDB specification on MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa75d-202">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa75d-202">See Also</span></span>  
 <span data-ttu-id="fa75d-203">[Fonctionnement de l’instruction DMX Select](/sql/dmx/understanding-the-dmx-select-statement) </span><span class="sxs-lookup"><span data-stu-id="fa75d-203">[Understanding the DMX Select Statement](/sql/dmx/understanding-the-dmx-select-statement) </span></span>  
 [<span data-ttu-id="fa75d-204">Requêtes d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="fa75d-204">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
