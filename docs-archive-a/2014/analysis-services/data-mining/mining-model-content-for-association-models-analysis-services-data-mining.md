---
title: Contenu du modèle d’exploration de données pour les modèles d’Association (Analysis Services-exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- itemsets [Analysis Services]
- association algorithms [Analysis Services]
- mining model content, association models
- rules [Data Mining]
- associations [Analysis Services]
ms.assetid: d5849bcb-4b8f-4f71-9761-7dc5bb465224
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8904ce155526aee595db19094fd2bad48770e83e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604284"
---
# <a name="mining-model-content-for-association-models-analysis-services---data-mining"></a><span data-ttu-id="2bef4-102">Contenu du modèle d'exploration de données pour les modèles d'association (Analysis Services - Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="2bef4-102">Mining Model Content for Association Models (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="2bef4-103">Cette rubrique décrit le contenu du modèle d’exploration qui est spécifique aux modèles utilisant l’algorithme MAR ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules).</span><span class="sxs-lookup"><span data-stu-id="2bef4-103">This topic describes mining model content that is specific to models that use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules algorithm.</span></span> <span data-ttu-id="2bef4-104">Pour une explication de la terminologie générale et statistique en rapport avec le contenu du modèle d’exploration de données pour tous les types de modèles, consultez [Contenu du modèle d’exploration &#40;Analysis Services – Exploration de données&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2bef4-104">For an explanation of general and statistical terminology related to mining model content that applies to all model types, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="understanding-the-structure-of-an-association-model"></a><span data-ttu-id="2bef4-105">Fonctionnement de la structure d'un modèle d'association</span><span class="sxs-lookup"><span data-stu-id="2bef4-105">Understanding the Structure of an Association Model</span></span>  
 <span data-ttu-id="2bef4-106">La structure d'un modèle d'association est simple.</span><span class="sxs-lookup"><span data-stu-id="2bef4-106">An association model has a simple structure.</span></span> <span data-ttu-id="2bef4-107">Chaque modèle possède un nœud parent unique qui représente le modèle et ses métadonnées, et chaque nœud parent possède une liste plate de jeux d'éléments et de règles.</span><span class="sxs-lookup"><span data-stu-id="2bef4-107">Each model has a single parent node that represents the model and its metadata, and each parent node has a flat list of itemsets and rules.</span></span> <span data-ttu-id="2bef4-108">Les jeux d'éléments et les règles ne sont pas organisés dans des arbres. Comme le montre le diagramme suivant, les jeux d'éléments précèdent les règles.</span><span class="sxs-lookup"><span data-stu-id="2bef4-108">The itemsets and rules are not organized in trees, they are ordered with itemsets first and rules next as shown in the following diagram.</span></span>  
  
 <span data-ttu-id="2bef4-109">![structure de contenu de modèle pour des modèles d'association](../media/modelcontentstructure-assoc.gif "structure de contenu de modèle pour des modèles d'association")</span><span class="sxs-lookup"><span data-stu-id="2bef4-109">![structure of model content for association models](../media/modelcontentstructure-assoc.gif "structure of model content for association models")</span></span>  
  
 <span data-ttu-id="2bef4-110">Chaque jeu d'éléments est contenu dans son propre nœud (NODE_TYPE = 7).</span><span class="sxs-lookup"><span data-stu-id="2bef4-110">Each itemset is contained in its own node (NODE_TYPE = 7).</span></span> <span data-ttu-id="2bef4-111">Le *nœud* : inclut la définition du jeu d’éléments, le nombre de cas contenant ce jeu d’éléments, ainsi que d’autres informations.</span><span class="sxs-lookup"><span data-stu-id="2bef4-111">The *node* includes the definition of the itemset, the number of cases that contain this itemset, and other information.</span></span>  
  
 <span data-ttu-id="2bef4-112">Chaque règle est également contenue dans son propre nœud (NODE_TYPE = 8).</span><span class="sxs-lookup"><span data-stu-id="2bef4-112">Each rule is also contained in its own node (NODE_TYPE = 8).</span></span> <span data-ttu-id="2bef4-113">Une *règle* : décrit une séquence générale indiquant comment les éléments sont associés.</span><span class="sxs-lookup"><span data-stu-id="2bef4-113">A *rule* describes a general pattern for how items are associated.</span></span> <span data-ttu-id="2bef4-114">Une règle s'apparente à une instruction IF-THEN.</span><span class="sxs-lookup"><span data-stu-id="2bef4-114">A rule is like an IF-THEN statement.</span></span> <span data-ttu-id="2bef4-115">La partie gauche de la règle indique une condition existante ou un jeu de conditions.</span><span class="sxs-lookup"><span data-stu-id="2bef4-115">The left-hand side of the rule shows an existing condition or set of conditions.</span></span> <span data-ttu-id="2bef4-116">Quant à la partie droite de la règle, elle indique l'élément de votre jeu de données qui est généralement associé aux conditions de la partie gauche.</span><span class="sxs-lookup"><span data-stu-id="2bef4-116">The right-hand side of the rule shows the item in your data set that is usually associated with the conditions on the left side.</span></span>  
  
 <span data-ttu-id="2bef4-117">**Remarque :** Si vous voulez extraire les règles ou les jeux d’éléments, vous pouvez utiliser une requête pour retourner uniquement les types de nœuds souhaités.</span><span class="sxs-lookup"><span data-stu-id="2bef4-117">**Note** If you want to extract either the rules or the itemsets, you can use a query to return only the node types that you want.</span></span> <span data-ttu-id="2bef4-118">Pour plus d’informations, consultez [Exemples de requête de modèle d’association](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="2bef4-118">For more information, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
## <a name="model-content-for-an-association-model"></a><span data-ttu-id="2bef4-119">Contenu du modèle pour un modèle d'association</span><span class="sxs-lookup"><span data-stu-id="2bef4-119">Model Content for an Association Model</span></span>  
 <span data-ttu-id="2bef4-120">Cette section fournit des informations et des exemples pour les colonnes du contenu du modèle d'exploration de données qui s'appliquent aux modèles d'association.</span><span class="sxs-lookup"><span data-stu-id="2bef4-120">This section provides detail and examples only for those columns in the mining model content that are relevant for association models.</span></span>  
  
 <span data-ttu-id="2bef4-121">Pour plus d’informations sur les colonnes à caractère général dans l’ensemble de lignes du schéma, comme MODEL_CATALOG et MODEL_NAME, consultez [Contenu du modèle d’exploration &#40;Analysis Services – Exploration de données&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2bef4-121">For information about the general-purpose columns in the schema rowset, such as MODEL_CATALOG and MODEL_NAME, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="2bef4-122">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2bef4-122">MODEL_CATALOG</span></span>  
 <span data-ttu-id="2bef4-123">Nom de la base de données où le modèle est stocké.</span><span class="sxs-lookup"><span data-stu-id="2bef4-123">Name of the database where the model is stored.</span></span>  
  
 <span data-ttu-id="2bef4-124">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="2bef4-124">MODEL_NAME</span></span>  
 <span data-ttu-id="2bef4-125">Nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-125">Name of the model.</span></span>  
  
 <span data-ttu-id="2bef4-126">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="2bef4-126">ATTRIBUTE_NAME</span></span>  
 <span data-ttu-id="2bef4-127">Noms des attributs qui correspondent à ce nœud.</span><span class="sxs-lookup"><span data-stu-id="2bef4-127">The names of the attributes that correspond to this node.</span></span>  
  
 <span data-ttu-id="2bef4-128">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="2bef4-128">NODE_NAME</span></span>  
 <span data-ttu-id="2bef4-129">Nom du nœud.</span><span class="sxs-lookup"><span data-stu-id="2bef4-129">The name of the node.</span></span> <span data-ttu-id="2bef4-130">Pour un modèle d'association, cette colonne contient la même valeur que NODE_UNIQUE_NAME.</span><span class="sxs-lookup"><span data-stu-id="2bef4-130">For an association model, this column contains the same value as NODE_UNIQUE_NAME.</span></span>  
  
 <span data-ttu-id="2bef4-131">NODE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="2bef4-131">NODE_UNIQUE_NAME</span></span>  
 <span data-ttu-id="2bef4-132">Nom unique du nœud.</span><span class="sxs-lookup"><span data-stu-id="2bef4-132">The unique name of the node.</span></span>  
  
 <span data-ttu-id="2bef4-133">NODE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2bef4-133">NODE_TYPE</span></span>  
 <span data-ttu-id="2bef4-134">Un modèle d'association génère uniquement en sortie les types de nœuds suivants :</span><span class="sxs-lookup"><span data-stu-id="2bef4-134">A association model outputs only the following node types:</span></span>  
  
|<span data-ttu-id="2bef4-135">ID du type de nœud</span><span class="sxs-lookup"><span data-stu-id="2bef4-135">Node Type ID</span></span>|<span data-ttu-id="2bef4-136">Type</span><span class="sxs-lookup"><span data-stu-id="2bef4-136">Type</span></span>|  
|------------------|----------|  
|<span data-ttu-id="2bef4-137">1 (Modèle)</span><span class="sxs-lookup"><span data-stu-id="2bef4-137">1 (Model)</span></span>|<span data-ttu-id="2bef4-138">Nœud racine ou parent.</span><span class="sxs-lookup"><span data-stu-id="2bef4-138">Root or parent node.</span></span>|  
|<span data-ttu-id="2bef4-139">7 (Jeu d'éléments)</span><span class="sxs-lookup"><span data-stu-id="2bef4-139">7 (Itemset)</span></span>|<span data-ttu-id="2bef4-140">Jeu d'éléments ou collection de paires attribut/valeur.</span><span class="sxs-lookup"><span data-stu-id="2bef4-140">An itemset, or collection of attribute-value pairs.</span></span> <span data-ttu-id="2bef4-141">Exemples :</span><span class="sxs-lookup"><span data-stu-id="2bef4-141">Examples:</span></span><br /><br /> `Product 1 = Existing, Product 2 = Existing`<br /><br /> <span data-ttu-id="2bef4-142">or</span><span class="sxs-lookup"><span data-stu-id="2bef4-142">or</span></span><br /><br /> <span data-ttu-id="2bef4-143">`Gender = Male`.</span><span class="sxs-lookup"><span data-stu-id="2bef4-143">`Gender = Male`.</span></span>|  
|<span data-ttu-id="2bef4-144">8 (Règle)</span><span class="sxs-lookup"><span data-stu-id="2bef4-144">8 (Rule)</span></span>|<span data-ttu-id="2bef4-145">Règle définissant la façon dont les éléments sont liés les uns aux autres.</span><span class="sxs-lookup"><span data-stu-id="2bef4-145">A rule defining how items relate to each other.</span></span><br /><br /> <span data-ttu-id="2bef4-146">Exemple :</span><span class="sxs-lookup"><span data-stu-id="2bef4-146">Example:</span></span><br /><br /> <span data-ttu-id="2bef4-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span><span class="sxs-lookup"><span data-stu-id="2bef4-147">`Product 1 = Existing, Product 2 = Existing -> Product 3 = Existing`.</span></span>|  
  
 <span data-ttu-id="2bef4-148">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="2bef4-148">NODE_CAPTION</span></span>  
 <span data-ttu-id="2bef4-149">Étiquette ou légende associée au nœud.</span><span class="sxs-lookup"><span data-stu-id="2bef4-149">A label or a caption associated with the node.</span></span>  
  
 <span data-ttu-id="2bef4-150">**Nœud de jeu d’éléments** : liste d’éléments séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="2bef4-150">**Itemset node** A comma-separated list of items.</span></span>  
  
 <span data-ttu-id="2bef4-151">**Nœud de règle** : contient les parties gauche et droite de la règle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-151">**Rule node** Contains the left and right-hand sides of the rule.</span></span>  
  
 <span data-ttu-id="2bef4-152">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2bef4-152">CHILDREN_CARDINALITY</span></span>  
 <span data-ttu-id="2bef4-153">Indique le nombre d'enfants du nœud actuel.</span><span class="sxs-lookup"><span data-stu-id="2bef4-153">Indicates the number of children of the current node.</span></span>  
  
 <span data-ttu-id="2bef4-154">**Nœud parent** : indique le nombre total de jeux d’éléments et de règles.</span><span class="sxs-lookup"><span data-stu-id="2bef4-154">**Parent node** Indicates the total number of itemsets plus rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bef4-155">Pour obtenir la répartition du nombre de jeux d'éléments et de règles, consultez NODE_DESCRIPTION pour le nœud racine du modèle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-155">To get a breakdown of the count for itemsets and rules, see the NODE_DESCRIPTION for the root node of the model.</span></span>  
  
 <span data-ttu-id="2bef4-156">**Nœud de jeu d’éléments ou de règle** : toujours 0.</span><span class="sxs-lookup"><span data-stu-id="2bef4-156">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="2bef4-157">PARENT_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="2bef4-157">PARENT_UNIQUE_NAME</span></span>  
 <span data-ttu-id="2bef4-158">Nom unique du parent du nœud.</span><span class="sxs-lookup"><span data-stu-id="2bef4-158">The unique name of the node's parent.</span></span>  
  
 <span data-ttu-id="2bef4-159">**Nœud parent** Toujours NULL.</span><span class="sxs-lookup"><span data-stu-id="2bef4-159">**Parent node** Always NULL.</span></span>  
  
 <span data-ttu-id="2bef4-160">**Nœud de jeu d’éléments ou de règle** : toujours 0.</span><span class="sxs-lookup"><span data-stu-id="2bef4-160">**Itemset or rule node** Always 0.</span></span>  
  
 <span data-ttu-id="2bef4-161">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2bef4-161">NODE_DESCRIPTION</span></span>  
 <span data-ttu-id="2bef4-162">Description conviviale du contenu du nœud.</span><span class="sxs-lookup"><span data-stu-id="2bef4-162">A user-friendly description of the contents of the node.</span></span>  
  
 <span data-ttu-id="2bef4-163">**Nœud parent** : inclut une liste des informations suivantes à propos du modèle, séparées par des virgules :</span><span class="sxs-lookup"><span data-stu-id="2bef4-163">**Parent node** Includes a comma-separated list of the following information about the model:</span></span>  
  
|<span data-ttu-id="2bef4-164">Élément</span><span class="sxs-lookup"><span data-stu-id="2bef4-164">Item</span></span>|<span data-ttu-id="2bef4-165">Description</span><span class="sxs-lookup"><span data-stu-id="2bef4-165">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2bef4-166">ITEMSET_COUNT</span><span class="sxs-lookup"><span data-stu-id="2bef4-166">ITEMSET_COUNT</span></span>|<span data-ttu-id="2bef4-167">Nombre de jeux d'éléments dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-167">Count of all itemsets in model.</span></span>|  
|<span data-ttu-id="2bef4-168">RULE_COUNT</span><span class="sxs-lookup"><span data-stu-id="2bef4-168">RULE_COUNT</span></span>|<span data-ttu-id="2bef4-169">Nombre de règles dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-169">Count of all rules in model.</span></span>|  
|<span data-ttu-id="2bef4-170">MIN_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2bef4-170">MIN_SUPPORT</span></span>|<span data-ttu-id="2bef4-171">Prise en charge minimale trouvée pour un jeu d'éléments unique.</span><span class="sxs-lookup"><span data-stu-id="2bef4-171">The minimum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="2bef4-172">**Remarque** : Cette valeur peut différer de celle à laquelle vous avez défini le paramètre *MINIMUM _SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="2bef4-172">**Note** This value might differ from the value that you set for the *MINIMUM _SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="2bef4-173">MAX_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2bef4-173">MAX_SUPPORT</span></span>|<span data-ttu-id="2bef4-174">Prise en charge maximale trouvée pour un jeu d'éléments unique.</span><span class="sxs-lookup"><span data-stu-id="2bef4-174">The maximum support found for any single itemset.</span></span><br /><br /> <span data-ttu-id="2bef4-175">**Remarque** : Cette valeur peut différer de celle à laquelle vous avez défini le paramètre *MAXIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="2bef4-175">**Note** This value might differ from the value that you set for the *MAXIMUM_SUPPORT* parameter.</span></span>|  
|<span data-ttu-id="2bef4-176">MIN_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="2bef4-176">MIN_ITEMSET_SIZE</span></span>|<span data-ttu-id="2bef4-177">Taille du plus petit jeu d'éléments, représentée par un nombre d'éléments.</span><span class="sxs-lookup"><span data-stu-id="2bef4-177">The size of the smallest itemset, represented as a count of items.</span></span><br /><br /> <span data-ttu-id="2bef4-178">La valeur 0 indique que l'état `Missing` a été traité en tant qu'élément indépendant.</span><span class="sxs-lookup"><span data-stu-id="2bef4-178">A value of 0 indicates that the `Missing` state was treated as an independent item.</span></span><br /><br /> <span data-ttu-id="2bef4-179">**Remarque** : La valeur par défaut du paramètre *MINIMUM_ITEMSET_SIZE* est 1.</span><span class="sxs-lookup"><span data-stu-id="2bef4-179">**Note** The default value of the *MINIMUM_ITEMSET_SIZE* parameter is 1.</span></span>|  
|<span data-ttu-id="2bef4-180">MAX_ITEMSET_SIZE</span><span class="sxs-lookup"><span data-stu-id="2bef4-180">MAX_ITEMSET_SIZE</span></span>|<span data-ttu-id="2bef4-181">Indique la taille du plus grand jeu d'éléments trouvé.</span><span class="sxs-lookup"><span data-stu-id="2bef4-181">Indicates the size of the largest itemset that was found.</span></span><br /><br /> <span data-ttu-id="2bef4-182">**Remarque** : Cette valeur est conditionnée par la valeur que vous avez attribuée au paramètre *MAX_ITEMSET_SIZE* quand vous avez créé le modèle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-182">**Note** This value is constrained by the value that you set for the *MAX_ITEMSET_SIZE* parameter when you created the model.</span></span> <span data-ttu-id="2bef4-183">Cette valeur ne peut jamais dépasser cette valeur ; toutefois, elle peut être inférieure à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="2bef4-183">This value can never exceed that value; however, it can be less.</span></span> <span data-ttu-id="2bef4-184">La valeur par défaut est 3.</span><span class="sxs-lookup"><span data-stu-id="2bef4-184">The default value is 3.</span></span>|  
|<span data-ttu-id="2bef4-185">MIN_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="2bef4-185">MIN_PROBABILITY</span></span>|<span data-ttu-id="2bef4-186">Probabilité minimale détectée pour un jeu d'éléments ou une règle unique dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-186">The minimum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="2bef4-187">Exemple : 0.400390625</span><span class="sxs-lookup"><span data-stu-id="2bef4-187">Example: 0.400390625</span></span><br /><br /> <span data-ttu-id="2bef4-188">**Remarque** : Pour les jeux d’éléments, cette valeur est toujours supérieure à celle que vous avez attribuée au paramètre *MINIMUM_PROBABILITY* lors de la création du modèle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-188">**Note** For itemsets, this value is always greater than the value that you set for the *MINIMUM_PROBABILITY* parameter when you created the model.</span></span>|  
|<span data-ttu-id="2bef4-189">MAX_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="2bef4-189">MAX_PROBABILITY</span></span>|<span data-ttu-id="2bef4-190">Probabilité maximale détectée pour un jeu d'éléments ou une règle unique dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-190">The maximum probability detected for any single itemset or rule in the model.</span></span><br /><br /> <span data-ttu-id="2bef4-191">Exemple : 1</span><span class="sxs-lookup"><span data-stu-id="2bef4-191">Example: 1</span></span><br /><br /> <span data-ttu-id="2bef4-192">**Remarque** : Il n’existe pas de paramètre pour conditionner la probabilité maximale des jeux d’éléments.</span><span class="sxs-lookup"><span data-stu-id="2bef4-192">**Note** There is no parameter to constrain maximum probability of itemsets.</span></span> <span data-ttu-id="2bef4-193">Si vous voulez éliminer des éléments qui sont trop fréquents, utilisez à la place le paramètre *MAXIMUM_SUPPORT* .</span><span class="sxs-lookup"><span data-stu-id="2bef4-193">If you want to eliminate items that are too frequent, use the *MAXIMUM_SUPPORT* parameter instead.</span></span>|  
|<span data-ttu-id="2bef4-194">MIN_LIFT</span><span class="sxs-lookup"><span data-stu-id="2bef4-194">MIN_LIFT</span></span>|<span data-ttu-id="2bef4-195">Quantité minimale de finesse fournie par le modèle pour un jeu d'éléments.</span><span class="sxs-lookup"><span data-stu-id="2bef4-195">The minimum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="2bef4-196">Exemple : 0,14309369632511</span><span class="sxs-lookup"><span data-stu-id="2bef4-196">Example: 0.14309369632511</span></span><br /><br /> <span data-ttu-id="2bef4-197">Remarque : le fait de connaître la finesse minimale peut vous aider à déterminer si la finesse est significative pour un jeu d’éléments.</span><span class="sxs-lookup"><span data-stu-id="2bef4-197">Note: Knowing the minimum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
|<span data-ttu-id="2bef4-198">MAX_LIFT</span><span class="sxs-lookup"><span data-stu-id="2bef4-198">MAX_LIFT</span></span>|<span data-ttu-id="2bef4-199">Quantité maximale de finesse fournie par le modèle pour un jeu d'éléments.</span><span class="sxs-lookup"><span data-stu-id="2bef4-199">The maximum amount of lift that is provided by the model for any itemset.</span></span><br /><br /> <span data-ttu-id="2bef4-200">Exemple: 1,95758227647523 **Remarque** : Le fait de connaître la finesse maximale peut vous aider à déterminer si la finesse est significative pour un jeu d’éléments.</span><span class="sxs-lookup"><span data-stu-id="2bef4-200">Example: 1.95758227647523 **Note** Knowing the maximum lift can help you determine whether the lift for any one itemset is significant.</span></span>|  
  
 <span data-ttu-id="2bef4-201">**Nœud de jeu d’éléments** : les nœuds de jeu d’éléments contiennent une liste des éléments qui est affichée sous forme d’une chaîne de texte avec une virgule comme séparateur.</span><span class="sxs-lookup"><span data-stu-id="2bef4-201">**Itemset node** Itemset nodes contain a list of the items, displayed as a comma-separated text string.</span></span>  
  
 <span data-ttu-id="2bef4-202">Exemple :</span><span class="sxs-lookup"><span data-stu-id="2bef4-202">Example:</span></span>  
  
 `Touring Tire = Existing, Water Bottle = Existing`  
  
 <span data-ttu-id="2bef4-203">Cela signifie que les pneus pour vélo de tourisme et les bidons d'eau ont été achetés ensemble.</span><span class="sxs-lookup"><span data-stu-id="2bef4-203">This means touring tires and water bottles were purchased together.</span></span>  
  
 <span data-ttu-id="2bef4-204">**Nœud de règle** : les nœuds de règle contiennent une partie gauche et une partie droite de la règle, séparées par une flèche.</span><span class="sxs-lookup"><span data-stu-id="2bef4-204">**Rule node** Rule nodes contains a left-hand and right-hand side of the rule, separated by an arrow.</span></span>  
  
 <span data-ttu-id="2bef4-205">Exemple : `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span><span class="sxs-lookup"><span data-stu-id="2bef4-205">Example: `Touring Tire = Existing, Water Bottle = Existing -> Cycling cap = Existing`</span></span>  
  
 <span data-ttu-id="2bef4-206">Cela signifie que si quelqu'un a acheté un pneu pour vélo de tourisme et un bidon d'eau, il était aussi susceptible d'acheter une casquette de cyclisme.</span><span class="sxs-lookup"><span data-stu-id="2bef4-206">This means that if someone bought a touring tire and a water bottle, they were also likely to buy a cycling cap.</span></span>  
  
 <span data-ttu-id="2bef4-207">NODE_RULE</span><span class="sxs-lookup"><span data-stu-id="2bef4-207">NODE_RULE</span></span>  
 <span data-ttu-id="2bef4-208">Fragment XML qui décrit la règle ou le jeu d'éléments incorporé dans le nœud.</span><span class="sxs-lookup"><span data-stu-id="2bef4-208">An XML fragment that describes the rule or itemset that is embedded in the node.</span></span>  
  
 <span data-ttu-id="2bef4-209">**Nœud parent** : vide.</span><span class="sxs-lookup"><span data-stu-id="2bef4-209">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="2bef4-210">**Nœud de jeu d’éléments** : vide.</span><span class="sxs-lookup"><span data-stu-id="2bef4-210">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="2bef4-211">**Nœud de règle** : le fragment XML inclut d’autres informations utiles sur la règle, comme la prise en charge, la confiance et le nombre d’éléments, ainsi que l’ID du nœud qui représente la partie gauche de la règle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-211">**Rule node** The XML fragment includes additional useful information about the rule, such as support, confidence, and the number of items, and the ID of the node that represents the left-hand side of the rule.</span></span>  
  
 <span data-ttu-id="2bef4-212">MARGINAL_RULE</span><span class="sxs-lookup"><span data-stu-id="2bef4-212">MARGINAL_RULE</span></span>  
 <span data-ttu-id="2bef4-213">: vide.</span><span class="sxs-lookup"><span data-stu-id="2bef4-213">Blank.</span></span>  
  
 <span data-ttu-id="2bef4-214">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="2bef4-214">NODE_PROBABILITY</span></span>  
 <span data-ttu-id="2bef4-215">Une probabilité ou un score de confiance associé au jeu d'éléments ou à la règle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-215">A probability or confidence score associated with the itemset or rule.</span></span>  
  
 <span data-ttu-id="2bef4-216">**Nœud parent** : toujours 0.</span><span class="sxs-lookup"><span data-stu-id="2bef4-216">**Parent node** Always 0.</span></span>  
  
 <span data-ttu-id="2bef4-217">**Nœud de jeu d’éléments** : probabilité du jeu d’éléments.</span><span class="sxs-lookup"><span data-stu-id="2bef4-217">**Itemset node** Probability of the itemset.</span></span>  
  
 <span data-ttu-id="2bef4-218">**Nœud de règle** : valeur de la confiance pour la règle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-218">**Rule node** Confidence value for the rule.</span></span>  
  
 <span data-ttu-id="2bef4-219">MARGINAL_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="2bef4-219">MARGINAL_PROBABILITY</span></span>  
 <span data-ttu-id="2bef4-220">Identique à NODE_PROBABILITY.</span><span class="sxs-lookup"><span data-stu-id="2bef4-220">Same as NODE_PROBABILITY.</span></span>  
  
 <span data-ttu-id="2bef4-221">NODE_DISTRIBUTION</span><span class="sxs-lookup"><span data-stu-id="2bef4-221">NODE_DISTRIBUTION</span></span>  
 <span data-ttu-id="2bef4-222">La table contient des informations très différentes, selon que le nœud est un jeu d'éléments ou une règle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-222">The table contains very different information, depending on whether the node is an itemset or a rule.</span></span>  
  
 <span data-ttu-id="2bef4-223">**Nœud parent** : vide.</span><span class="sxs-lookup"><span data-stu-id="2bef4-223">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="2bef4-224">**Nœud de jeu d’éléments** : répertorie chaque élément dans le jeu d’éléments avec une probabilité et une valeur de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="2bef4-224">**Itemset node** Lists each item in the itemset together with a probability and support value.</span></span> <span data-ttu-id="2bef4-225">Par exemple, si le jeu d'éléments contient deux produits, le nom de chaque produit est répertorié avec le nombre des cas qui incluent chaque produit.</span><span class="sxs-lookup"><span data-stu-id="2bef4-225">For example, if the itemset contains two products, the name of each product is listed, together with the count of cases that include each product.</span></span>  
  
 <span data-ttu-id="2bef4-226">**Nœud de règle** : contient deux lignes.</span><span class="sxs-lookup"><span data-stu-id="2bef4-226">**Rule node** Contains two rows.</span></span> <span data-ttu-id="2bef4-227">La première ligne montre l'attribut de la partie droite de la règle, c'est-à-dire l'élément prédit, avec un score de confiance.</span><span class="sxs-lookup"><span data-stu-id="2bef4-227">The first row shows the attribute from the right-hand side of the rule, which is the predicted item, together with a confidence score.</span></span>  
  
 <span data-ttu-id="2bef4-228">La deuxième ligne est unique aux modèles d'association ; elle contient un pointeur vers le jeu d'éléments dans la partie droite de la règle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-228">The second row is unique to association models; it contains a pointer to the itemset on the right-hand side of the rule.</span></span> <span data-ttu-id="2bef4-229">Le pointeur est représenté dans la colonne ATTRIBUTE_VALUE comme l'ID du jeu d'éléments qui contient uniquement l'élément de la partie droite.</span><span class="sxs-lookup"><span data-stu-id="2bef4-229">The pointer is represented in the ATTRIBUTE_VALUE column as the ID of the itemset that contains only the right-hand item.</span></span>  
  
 <span data-ttu-id="2bef4-230">Par exemple, si la règle est `If {A,B} Then {C}`, la table contient le nom de l'élément `{C}`et l'ID du nœud qui contient le jeu d'éléments pour l'élément C.</span><span class="sxs-lookup"><span data-stu-id="2bef4-230">For example, if the rule is `If {A,B} Then {C}`, the table contains the name of the item `{C}`, and the ID of the node that contains the itemset for item C.</span></span>  
  
 <span data-ttu-id="2bef4-231">Ce pointeur est utile car vous pouvez déterminer à partir du nœud de jeu d'éléments combien de cas en tout incluent le produit de la partie droite.</span><span class="sxs-lookup"><span data-stu-id="2bef4-231">This pointer is useful because you can determine from the itemset node how many cases in all include the right-hand side product.</span></span> <span data-ttu-id="2bef4-232">Les cas soumis à la règle `If {A,B} Then {C}` sont un sous-ensemble des cas répertoriés dans le jeu d'éléments de `{C}`.</span><span class="sxs-lookup"><span data-stu-id="2bef4-232">The cases that are subject to the rule `If {A,B} Then {C}` are a subset of the cases listed in the itemset for `{C}`.</span></span>  
  
 <span data-ttu-id="2bef4-233">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2bef4-233">NODE_SUPPORT</span></span>  
 <span data-ttu-id="2bef4-234">Nombre de cas qui prennent en charge ce nœud.</span><span class="sxs-lookup"><span data-stu-id="2bef4-234">The number of cases that support this node.</span></span>  
  
 <span data-ttu-id="2bef4-235">**Nœud parent** : nombre de cas dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-235">**Parent node** Number of cases in the model.</span></span>  
  
 <span data-ttu-id="2bef4-236">**Nœud de jeu d’éléments** : nombre de cas contenant tous les éléments dans le jeu d’éléments.</span><span class="sxs-lookup"><span data-stu-id="2bef4-236">**Itemset node** Number of cases that contains all items in the itemset.</span></span>  
  
 <span data-ttu-id="2bef4-237">**Nœud de règle** : nombre de cas contenant tous les éléments inclus dans la règle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-237">**Rule node** The number of cases that contain all items included in the rule.</span></span>  
  
 <span data-ttu-id="2bef4-238">MSOLAP_MODEL_COLUMN</span><span class="sxs-lookup"><span data-stu-id="2bef4-238">MSOLAP_MODEL_COLUMN</span></span>  
 <span data-ttu-id="2bef4-239">Contient des informations différentes selon que le nœud est un jeu d'éléments ou une règle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-239">Contains different information depending on whether the node is an itemset or rule.</span></span>  
  
 <span data-ttu-id="2bef4-240">**Nœud parent** : vide.</span><span class="sxs-lookup"><span data-stu-id="2bef4-240">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="2bef4-241">**Nœud de jeu d’éléments** : vide.</span><span class="sxs-lookup"><span data-stu-id="2bef4-241">**Itemset node** Blank.</span></span>  
  
 <span data-ttu-id="2bef4-242">**Nœud de règle** : ID du jeu d’éléments contenant les éléments dans la partie gauche de la règle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-242">**Rule node** The ID of the itemset that contains the items in the left-hand side of the rule.</span></span> <span data-ttu-id="2bef4-243">Par exemple, si la règle est `If {A,B} Then {C}`, cette colonne contient l’ID du jeu d’éléments contenant seulement `{A,B}`.</span><span class="sxs-lookup"><span data-stu-id="2bef4-243">For example, if the rule is `If {A,B} Then {C}`, this column contains the ID of the itemset that contains only `{A,B}`.</span></span>  
  
 <span data-ttu-id="2bef4-244">MSOLAP_NODE_SCORE</span><span class="sxs-lookup"><span data-stu-id="2bef4-244">MSOLAP_NODE_SCORE</span></span>  
 <span data-ttu-id="2bef4-245">**Nœud parent** : vide.</span><span class="sxs-lookup"><span data-stu-id="2bef4-245">**Parent node** Blank.</span></span>  
  
 <span data-ttu-id="2bef4-246">**Nœud de jeu d’éléments** : score d’importance pour le jeu d’éléments.</span><span class="sxs-lookup"><span data-stu-id="2bef4-246">**Itemset node** Importance score for the itemset.</span></span>  
  
 <span data-ttu-id="2bef4-247">**Nœud de règle** : score d’importance pour la règle.</span><span class="sxs-lookup"><span data-stu-id="2bef4-247">**Rule node** Importance score for the rule.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bef4-248">L'importance est calculée différemment pour les jeux d'éléments et les règles.</span><span class="sxs-lookup"><span data-stu-id="2bef4-248">Importance is calculated differently for itemsets and rules.</span></span> <span data-ttu-id="2bef4-249">Pour plus d’informations, consultez [Références techniques relatives à l’algorithme Microsoft Association](microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="2bef4-249">For more information, see [Microsoft Association Algorithm Technical Reference](microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="2bef4-250">MSOLAP_NODE_SHORT_CAPTION</span><span class="sxs-lookup"><span data-stu-id="2bef4-250">MSOLAP_NODE_SHORT_CAPTION</span></span>  
 <span data-ttu-id="2bef4-251">: vide.</span><span class="sxs-lookup"><span data-stu-id="2bef4-251">Blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bef4-252">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2bef4-252">See Also</span></span>  
 <span data-ttu-id="2bef4-253">[Contenu du modèle d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="2bef4-253">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="2bef4-254">[Algorithme d’association Microsoft](microsoft-association-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="2bef4-254">[Microsoft Association Algorithm](microsoft-association-algorithm.md) </span></span>  
 [<span data-ttu-id="2bef4-255">Exemples de requêtes de modèle d'association</span><span class="sxs-lookup"><span data-stu-id="2bef4-255">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
  
