---
title: Contenu du modèle d’exploration de données pour les modèles de clustering (Analysis Services-exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- nearest neighbor [Data Mining]
- clustering [Data Mining]
- mining model content, clustering models
- clustering algorithms [Analysis Services]
ms.assetid: aed1b7d3-8f20-4eeb-b156-0229f942cefd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 400575d5c6ce8094b67500d15a86137302282fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604286"
---
# <a name="mining-model-content-for-clustering-models-analysis-services---data-mining"></a><span data-ttu-id="4a69b-102">Contenu du modèle d'exploration de données pour les modèles de clustering (Analysis Services - Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="4a69b-102">Mining Model Content for Clustering Models (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="4a69b-103">Cette rubrique décrit le contenu du modèle d'exploration de données qui est spécifique aux modèles qui utilisent l'algorithme de gestion de clusters Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4a69b-103">This topic describes mining model content that is specific to models that use the Microsoft Clustering algorithm.</span></span> <span data-ttu-id="4a69b-104">Pour obtenir une explication générale du contenu du modèle d’exploration de données pour tous les types de modèles, consultez [Contenu du modèle d’exploration &#40;Analysis Services – Exploration de données&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4a69b-104">For a general explanation of mining model content for all model types, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="understanding-the-structure-of-a-clustering-model"></a><span data-ttu-id="4a69b-105">Présentation de la structure d'un modèle de clustering</span><span class="sxs-lookup"><span data-stu-id="4a69b-105">Understanding the Structure of a Clustering Model</span></span>  
 <span data-ttu-id="4a69b-106">Un modèle de clustering a une structure simple.</span><span class="sxs-lookup"><span data-stu-id="4a69b-106">A clustering model has a simple structure.</span></span> <span data-ttu-id="4a69b-107">Chaque modèle a un nœud parent unique qui représente le modèle et ses métadonnées, et chaque nœud parent possède une liste plate de clusters (NODE_TYPE = 5).</span><span class="sxs-lookup"><span data-stu-id="4a69b-107">Each model has a single parent node that represents the model and its metadata, and each parent node has a flat list of clusters (NODE_TYPE = 5).</span></span> <span data-ttu-id="4a69b-108">Cette organisation est illustrée dans l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="4a69b-108">This organization is shown in the following image.</span></span>  
  
 <span data-ttu-id="4a69b-109">![structure de contenu de modèle pour le clustering](../media/modelcontentstructure-clust.gif "structure de contenu de modèle pour le clustering")</span><span class="sxs-lookup"><span data-stu-id="4a69b-109">![structure of model content for clustering](../media/modelcontentstructure-clust.gif "structure of model content for clustering")</span></span>  
  
 <span data-ttu-id="4a69b-110">Chaque nœud enfant représente un cluster unique et contient des statistiques détaillées sur les attributs des cas dans ce cluster,</span><span class="sxs-lookup"><span data-stu-id="4a69b-110">Each child node represents a single cluster and contains detailed statistics about the attributes of the cases in that cluster.</span></span> <span data-ttu-id="4a69b-111">notamment le nombre de cas dans le cluster et la distribution des valeurs qui distinguent le cluster d'autres clusters.</span><span class="sxs-lookup"><span data-stu-id="4a69b-111">This includes a count of the number of cases in the cluster, and the distribution of values that distinguish the cluster from other clusters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a69b-112">Il est inutile de parcourir les nœuds pour obtenir le nombre ou une description des clusters ; le nœud parent du modèle compte et répertorie aussi les clusters.</span><span class="sxs-lookup"><span data-stu-id="4a69b-112">You do not need to iterate through the nodes to get a count or description of the clusters; the model parent node also counts and lists the clusters.</span></span>  
  
 <span data-ttu-id="4a69b-113">Le nœud parent contient des statistiques utiles qui décrivent la distribution réelle de tous les cas d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="4a69b-113">The parent node contains useful statistics that describe the actual distribution of all the training cases.</span></span> <span data-ttu-id="4a69b-114">Ces statistiques se trouvent dans la colonne de table imbriquée NODE_DISTRIBUTION.</span><span class="sxs-lookup"><span data-stu-id="4a69b-114">These statistics are found in the nested table column, NODE_DISTRIBUTION.</span></span> <span data-ttu-id="4a69b-115">Par exemple, la table suivante contient plusieurs lignes de la table NODE_DISTRIBUTION qui décrivent la distribution des données démographiques pour le modèle de clustering, `TM_Clustering`, que vous créez dans le [Didacticiel sur l’exploration de données de base](../../tutorials/basic-data-mining-tutorial.md):</span><span class="sxs-lookup"><span data-stu-id="4a69b-115">For example, the following table shows several rows from the NODE_DISTRIBUTION table that describe the distribution of customer demographics for the clustering model, `TM_Clustering`, that you create in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md):</span></span>  
  
|<span data-ttu-id="4a69b-116">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a69b-116">ATTRIBUTE_NAME</span></span>|<span data-ttu-id="4a69b-117">ATTRIBUTE_VALUE</span><span class="sxs-lookup"><span data-stu-id="4a69b-117">ATRIBUTE_VALUE</span></span>|<span data-ttu-id="4a69b-118">SUPPORT</span><span class="sxs-lookup"><span data-stu-id="4a69b-118">SUPPORT</span></span>|<span data-ttu-id="4a69b-119">PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="4a69b-119">PROBABILITY</span></span>|<span data-ttu-id="4a69b-120">variance</span><span class="sxs-lookup"><span data-stu-id="4a69b-120">VARIANCE</span></span>|<span data-ttu-id="4a69b-121">VALUE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a69b-121">VALUE_TYPE</span></span>|  
|---------------------|---------------------|-------------|-----------------|--------------|-----------------|  
|<span data-ttu-id="4a69b-122">Age</span><span class="sxs-lookup"><span data-stu-id="4a69b-122">Age</span></span>|<span data-ttu-id="4a69b-123">Manquant</span><span class="sxs-lookup"><span data-stu-id="4a69b-123">Missing</span></span>|<span data-ttu-id="4a69b-124">0</span><span class="sxs-lookup"><span data-stu-id="4a69b-124">0</span></span>|<span data-ttu-id="4a69b-125">0</span><span class="sxs-lookup"><span data-stu-id="4a69b-125">0</span></span>|<span data-ttu-id="4a69b-126">0</span><span class="sxs-lookup"><span data-stu-id="4a69b-126">0</span></span>|<span data-ttu-id="4a69b-127">1 (Manquante)</span><span class="sxs-lookup"><span data-stu-id="4a69b-127">1 (Missing)</span></span>|  
|<span data-ttu-id="4a69b-128">Age</span><span class="sxs-lookup"><span data-stu-id="4a69b-128">Age</span></span>|<span data-ttu-id="4a69b-129">44.9016152716593</span><span class="sxs-lookup"><span data-stu-id="4a69b-129">44.9016152716593</span></span>|<span data-ttu-id="4a69b-130">12939</span><span class="sxs-lookup"><span data-stu-id="4a69b-130">12939</span></span>|<span data-ttu-id="4a69b-131">1</span><span class="sxs-lookup"><span data-stu-id="4a69b-131">1</span></span>|<span data-ttu-id="4a69b-132">125.663453102554</span><span class="sxs-lookup"><span data-stu-id="4a69b-132">125.663453102554</span></span>|<span data-ttu-id="4a69b-133">3 (Continue)</span><span class="sxs-lookup"><span data-stu-id="4a69b-133">3 (Continuous)</span></span>|  
|<span data-ttu-id="4a69b-134">Sexe</span><span class="sxs-lookup"><span data-stu-id="4a69b-134">Gender</span></span>|<span data-ttu-id="4a69b-135">Manquant</span><span class="sxs-lookup"><span data-stu-id="4a69b-135">Missing</span></span>|<span data-ttu-id="4a69b-136">0</span><span class="sxs-lookup"><span data-stu-id="4a69b-136">0</span></span>|<span data-ttu-id="4a69b-137">0</span><span class="sxs-lookup"><span data-stu-id="4a69b-137">0</span></span>|<span data-ttu-id="4a69b-138">0</span><span class="sxs-lookup"><span data-stu-id="4a69b-138">0</span></span>|<span data-ttu-id="4a69b-139">1 (Manquante)</span><span class="sxs-lookup"><span data-stu-id="4a69b-139">1 (Missing)</span></span>|  
|<span data-ttu-id="4a69b-140">Sexe</span><span class="sxs-lookup"><span data-stu-id="4a69b-140">Gender</span></span>|<span data-ttu-id="4a69b-141">F</span><span class="sxs-lookup"><span data-stu-id="4a69b-141">F</span></span>|<span data-ttu-id="4a69b-142">6350</span><span class="sxs-lookup"><span data-stu-id="4a69b-142">6350</span></span>|<span data-ttu-id="4a69b-143">0.490764355823479</span><span class="sxs-lookup"><span data-stu-id="4a69b-143">0.490764355823479</span></span>|<span data-ttu-id="4a69b-144">0</span><span class="sxs-lookup"><span data-stu-id="4a69b-144">0</span></span>|<span data-ttu-id="4a69b-145">4 (Discrète)</span><span class="sxs-lookup"><span data-stu-id="4a69b-145">4 (Discrete)</span></span>|  
|<span data-ttu-id="4a69b-146">Sexe</span><span class="sxs-lookup"><span data-stu-id="4a69b-146">Gender</span></span>|<span data-ttu-id="4a69b-147">M</span><span class="sxs-lookup"><span data-stu-id="4a69b-147">M</span></span>|<span data-ttu-id="4a69b-148">6589</span><span class="sxs-lookup"><span data-stu-id="4a69b-148">6589</span></span>|<span data-ttu-id="4a69b-149">0.509235644176521</span><span class="sxs-lookup"><span data-stu-id="4a69b-149">0.509235644176521</span></span>|<span data-ttu-id="4a69b-150">0</span><span class="sxs-lookup"><span data-stu-id="4a69b-150">0</span></span>|<span data-ttu-id="4a69b-151">4 (Discrète)</span><span class="sxs-lookup"><span data-stu-id="4a69b-151">4 (Discrete)</span></span>|  
  
 <span data-ttu-id="4a69b-152">D'après ces résultats, vous pouvez voir que 12939 cas ont été utilisés pour générer le modèle, que le rapport entre les hommes et les femmes est d'environ 50/50 et que l'âge moyen est 44 ans.</span><span class="sxs-lookup"><span data-stu-id="4a69b-152">From these results, you can see that there were 12939 cases used to build the model, that the ratio of males to females was about 50-50, and that the mean age was 44.</span></span> <span data-ttu-id="4a69b-153">Les statistiques descriptives varient selon que le type de l'attribut signalé est un type de données numériques continues, tel que l'âge, ou un type de valeur discrète, tel que le sexe.</span><span class="sxs-lookup"><span data-stu-id="4a69b-153">The descriptive statistics vary depending on whether the attribute being reported is a continuous numeric data type, such as age, or a discrete value type, such as gender.</span></span> <span data-ttu-id="4a69b-154">Les mesures statistiques *moyenne* et *variance* sont calculées pour les types de données continues, tandis que *probabilité* et *prise en charge* sont calculées pour les types de données discrètes.</span><span class="sxs-lookup"><span data-stu-id="4a69b-154">The statistical measures *mean* and *variance* are computed for continuous data types, whereas *probability* and *support* are computed for discrete data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a69b-155">La variance représente la variance totale pour le cluster.</span><span class="sxs-lookup"><span data-stu-id="4a69b-155">The variance represents the total variance for the cluster.</span></span> <span data-ttu-id="4a69b-156">Lorsque la valeur de la variance est faible, cela signifie que la plupart des valeurs dans la colonne sont assez proches de la moyenne.</span><span class="sxs-lookup"><span data-stu-id="4a69b-156">When the value for variance is small, it indicates that most values in the column were fairly close to the mean.</span></span> <span data-ttu-id="4a69b-157">Pour obtenir l'écart type, calculez la racine carrée de la variance.</span><span class="sxs-lookup"><span data-stu-id="4a69b-157">To obtain the standard deviation, calculate the square root of the variance.</span></span>  
  
 <span data-ttu-id="4a69b-158">Notez qu'il existe, pour chacun des attributs, un type de valeur `Missing` qui vous indique combien de cas ne possèdent pas de données pour cet attribut.</span><span class="sxs-lookup"><span data-stu-id="4a69b-158">Note that for each of the attributes there is a `Missing` value type that tells you how many cases had no data for that attribute.</span></span> <span data-ttu-id="4a69b-159">Les données manquantes peuvent être importantes et affecter les calculs de différentes manières en fonction du type de données.</span><span class="sxs-lookup"><span data-stu-id="4a69b-159">Missing data can be significant and affects calculations in different ways, depending on the data type.</span></span> <span data-ttu-id="4a69b-160">Pour plus d’informations, consultez [Valeurs manquantes &#40;Analysis Services - Exploration de données&#41;](missing-values-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4a69b-160">For more information, see [Missing Values &#40;Analysis Services - Data Mining&#41;](missing-values-analysis-services-data-mining.md).</span></span>  
  
## <a name="model-content-for-a-clustering-model"></a><span data-ttu-id="4a69b-161">Contenu du modèle pour un modèle de clustering</span><span class="sxs-lookup"><span data-stu-id="4a69b-161">Model Content for a Clustering Model</span></span>  
 <span data-ttu-id="4a69b-162">Cette section fournit des informations et des exemples pour les colonnes du contenu du modèle d'exploration de données qui s'appliquent aux modèles de clustering.</span><span class="sxs-lookup"><span data-stu-id="4a69b-162">This section provides detail and examples only for those columns in the mining model content that are relevant for clustering models.</span></span>  
  
 <span data-ttu-id="4a69b-163">Pour plus d’informations sur les colonnes à caractère général dans l’ensemble de lignes du schéma, comme MODEL_CATALOG et MODEL_NAME, consultez [Contenu du modèle d’exploration &#40;Analysis Services – Exploration de données&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4a69b-163">For information about the general-purpose columns in the schema rowset, such as MODEL_CATALOG and MODEL_NAME, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="4a69b-164">MODEL_CATALOG</span><span class="sxs-lookup"><span data-stu-id="4a69b-164">MODEL_CATALOG</span></span>  
 <span data-ttu-id="4a69b-165">Nom de la base de données où le modèle est stocké.</span><span class="sxs-lookup"><span data-stu-id="4a69b-165">Name of the database where the model is stored.</span></span>  
  
 <span data-ttu-id="4a69b-166">MODEL_NAME</span><span class="sxs-lookup"><span data-stu-id="4a69b-166">MODEL_NAME</span></span>  
 <span data-ttu-id="4a69b-167">Nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="4a69b-167">Name of the model.</span></span>  
  
 <span data-ttu-id="4a69b-168">ATTRIBUTE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a69b-168">ATTRIBUTE_NAME</span></span>  
 <span data-ttu-id="4a69b-169">Toujours vide dans les modèles de clustering car il n’existe aucun attribut prédictible dans le mode.</span><span class="sxs-lookup"><span data-stu-id="4a69b-169">Always blank in clustering models because there is no predictable attribute in the mode.</span></span>  
  
 <span data-ttu-id="4a69b-170">NODE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a69b-170">NODE_NAME</span></span>  
 <span data-ttu-id="4a69b-171">Toujours identique à NODE_UNIQUE_NAME.</span><span class="sxs-lookup"><span data-stu-id="4a69b-171">Always same as NODE_UNIQUE_NAME.</span></span>  
  
 <span data-ttu-id="4a69b-172">NODE_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a69b-172">NODE_UNIQUE_NAME</span></span>  
 <span data-ttu-id="4a69b-173">Identificateur unique pour le nœud dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="4a69b-173">A unique identifier for the node within the model.</span></span> <span data-ttu-id="4a69b-174">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="4a69b-174">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="4a69b-175">NODE_TYPE</span><span class="sxs-lookup"><span data-stu-id="4a69b-175">NODE_TYPE</span></span>  
 <span data-ttu-id="4a69b-176">Un modèle de clustering génère en sortie les types de nœuds suivants :</span><span class="sxs-lookup"><span data-stu-id="4a69b-176">A clustering model outputs the following node types:</span></span>  
  
|<span data-ttu-id="4a69b-177">ID et nom du nœud</span><span class="sxs-lookup"><span data-stu-id="4a69b-177">Node ID and Name</span></span>|<span data-ttu-id="4a69b-178">Description</span><span class="sxs-lookup"><span data-stu-id="4a69b-178">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="4a69b-179">1 (Modèle)</span><span class="sxs-lookup"><span data-stu-id="4a69b-179">1 (Model)</span></span>|<span data-ttu-id="4a69b-180">Nœud racine pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="4a69b-180">Root node for model.</span></span>|  
|<span data-ttu-id="4a69b-181">5 (cluster)</span><span class="sxs-lookup"><span data-stu-id="4a69b-181">5 (Cluster)</span></span>|<span data-ttu-id="4a69b-182">Contient le nombre de cas dans le cluster, les caractéristiques des cas dans le cluster et des statistiques qui décrivent les valeurs dans le cluster.</span><span class="sxs-lookup"><span data-stu-id="4a69b-182">Contains a count of cases in the cluster, the characteristics of cases in the cluster, and statistics that describe the values in the cluster.</span></span>|  
  
 <span data-ttu-id="4a69b-183">NODE_CAPTION</span><span class="sxs-lookup"><span data-stu-id="4a69b-183">NODE_CAPTION</span></span>  
 <span data-ttu-id="4a69b-184">Nom convivial utilisé à des fins d'affichage.</span><span class="sxs-lookup"><span data-stu-id="4a69b-184">A friendly name for display purposes.</span></span> <span data-ttu-id="4a69b-185">Lorsque vous créez un modèle, la valeur de NODE_UNIQUE_NAME est utilisée automatiquement comme légende.</span><span class="sxs-lookup"><span data-stu-id="4a69b-185">When you create a model, the value of NODE_UNIQUE_NAME is automatically used as the caption.</span></span> <span data-ttu-id="4a69b-186">Toutefois, vous pouvez modifier la valeur de NODE_CAPTION pour mettre à jour le nom d'affichage du cluster, par programmation ou à l'aide la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="4a69b-186">However, you can change the value for NODE_CAPTION to update the display name for the cluster, either programmatically or by using the viewer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a69b-187">Lorsque vous retraitez le modèle, toutes les modifications de nom sont remplacées par les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="4a69b-187">When you reprocess the model, all name changes will be overwritten by the new values.</span></span> <span data-ttu-id="4a69b-188">Vous ne pouvez pas rendre des noms persistants dans le modèle, ni faire le suivi des modifications dans l'appartenance au cluster entre différentes versions d'un modèle.</span><span class="sxs-lookup"><span data-stu-id="4a69b-188">You cannot persist names in the model, or track changes in cluster membership between different versions of a model.</span></span>  
  
 <span data-ttu-id="4a69b-189">CHILDREN_CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="4a69b-189">CHILDREN_CARDINALITY</span></span>  
 <span data-ttu-id="4a69b-190">Estimation du nombre d'enfants du nœud.</span><span class="sxs-lookup"><span data-stu-id="4a69b-190">An estimate of the number of children that the node has.</span></span>  
  
 <span data-ttu-id="4a69b-191">**Nœud parent** : indique le nombre de clusters dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="4a69b-191">**Parent node** Indicates the number of clusters in the model.</span></span>  
  
 <span data-ttu-id="4a69b-192">**Nœuds terminaux** : toujours 0.</span><span class="sxs-lookup"><span data-stu-id="4a69b-192">**Cluster nodes** Always 0.</span></span>  
  
 <span data-ttu-id="4a69b-193">PARENT_UNIQUE_NAME</span><span class="sxs-lookup"><span data-stu-id="4a69b-193">PARENT_UNIQUE_NAME</span></span>  
 <span data-ttu-id="4a69b-194">Nom unique du parent du nœud.</span><span class="sxs-lookup"><span data-stu-id="4a69b-194">The unique name of the node's parent.</span></span>  
  
 <span data-ttu-id="4a69b-195">**Nœud parent** : toujours NULL.</span><span class="sxs-lookup"><span data-stu-id="4a69b-195">**Parent node** Always NULL</span></span>  
  
 <span data-ttu-id="4a69b-196">**Nœuds du cluster** : généralement 000.</span><span class="sxs-lookup"><span data-stu-id="4a69b-196">**Cluster nodes** Usually 000.</span></span>  
  
 <span data-ttu-id="4a69b-197">NODE_DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4a69b-197">NODE_DESCRIPTION</span></span>  
 <span data-ttu-id="4a69b-198">Description du nœud.</span><span class="sxs-lookup"><span data-stu-id="4a69b-198">A description of the node.</span></span>  
  
 <span data-ttu-id="4a69b-199">**Nœud parent** : toujours **Tout**.</span><span class="sxs-lookup"><span data-stu-id="4a69b-199">**Parent node** Always **(All)**.</span></span>  
  
 <span data-ttu-id="4a69b-200">**Nœuds du cluster** : liste séparée par des virgules des attributs principaux qui distinguent le cluster des autres clusters.</span><span class="sxs-lookup"><span data-stu-id="4a69b-200">**Cluster nodes** A comma-separated list of the primary attributes that distinguish the cluster from other clusters.</span></span>  
  
 <span data-ttu-id="4a69b-201">NODE_RULE</span><span class="sxs-lookup"><span data-stu-id="4a69b-201">NODE_RULE</span></span>  
 <span data-ttu-id="4a69b-202">Non utilisé pour les modèles de clustering.</span><span class="sxs-lookup"><span data-stu-id="4a69b-202">Not used for clustering models.</span></span>  
  
 <span data-ttu-id="4a69b-203">MARGINAL_RULE</span><span class="sxs-lookup"><span data-stu-id="4a69b-203">MARGINAL_RULE</span></span>  
 <span data-ttu-id="4a69b-204">Non utilisé pour les modèles de clustering.</span><span class="sxs-lookup"><span data-stu-id="4a69b-204">Not used for clustering models.</span></span>  
  
 <span data-ttu-id="4a69b-205">NODE_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="4a69b-205">NODE_PROBABILITY</span></span>  
 <span data-ttu-id="4a69b-206">Probabilité associée à ce nœud.</span><span class="sxs-lookup"><span data-stu-id="4a69b-206">The probability associated with this node.</span></span> <span data-ttu-id="4a69b-207">**Nœud parent** : toujours 1.</span><span class="sxs-lookup"><span data-stu-id="4a69b-207">**Parent node** Always 1.</span></span>  
  
 <span data-ttu-id="4a69b-208">**Nœuds du cluster** : la probabilité représente la probabilité composée des attributs, avec certains ajustements selon l’algorithme utilisé pour créer le modèle de clustering.</span><span class="sxs-lookup"><span data-stu-id="4a69b-208">**Cluster nodes** The probability represents the compound probability of the attributes, with some adjustments depending on the algorithm used to create the clustering model.</span></span>  
  
 <span data-ttu-id="4a69b-209">MARGINAL_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="4a69b-209">MARGINAL_PROBABILITY</span></span>  
 <span data-ttu-id="4a69b-210">Probabilité d'accès au nœud à partir du nœud parent.</span><span class="sxs-lookup"><span data-stu-id="4a69b-210">The probability of reaching the node from the parent node.</span></span> <span data-ttu-id="4a69b-211">Dans un modèle de clustering, la probabilité marginale est toujours la même que la probabilité du nœud.</span><span class="sxs-lookup"><span data-stu-id="4a69b-211">In a clustering model, the marginal probability is always the same as the node probability.</span></span>  
  
 <span data-ttu-id="4a69b-212">NODE_DISTRIBUTION</span><span class="sxs-lookup"><span data-stu-id="4a69b-212">NODE_DISTRIBUTION</span></span>  
 <span data-ttu-id="4a69b-213">Table qui contient l'histogramme de probabilité du nœud.</span><span class="sxs-lookup"><span data-stu-id="4a69b-213">A table that contains the probability histogram of the node.</span></span>  
  
 <span data-ttu-id="4a69b-214">**Nœud parent** : consultez l’introduction de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4a69b-214">**Parent node** See the Introduction to this topic.</span></span>  
  
 <span data-ttu-id="4a69b-215">**Nœuds du cluster** : représente la distribution des attributs et des valeurs pour les cas inclus dans ce cluster.</span><span class="sxs-lookup"><span data-stu-id="4a69b-215">**Cluster nodes** Represents the distribution of attributes and values for cases that are included in this cluster.</span></span>  
  
 <span data-ttu-id="4a69b-216">NODE_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="4a69b-216">NODE_SUPPORT</span></span>  
 <span data-ttu-id="4a69b-217">Nombre de cas qui prennent en charge ce nœud.</span><span class="sxs-lookup"><span data-stu-id="4a69b-217">The number of cases that support this node.</span></span> <span data-ttu-id="4a69b-218">**Nœud parent** : indique le nombre de cas d’apprentissage pour tout le modèle.</span><span class="sxs-lookup"><span data-stu-id="4a69b-218">**Parent node** Indicates the number of training cases for the entire model.</span></span>  
  
 <span data-ttu-id="4a69b-219">**Nœuds du cluster** : indique la taille du cluster sous la forme d’un nombre de cas.</span><span class="sxs-lookup"><span data-stu-id="4a69b-219">**Cluster nodes** Indicates the size of the cluster as a number of cases.</span></span>  
  
 <span data-ttu-id="4a69b-220">**Remarque** : Si le modèle utilise le clustering K-Means, chaque cas ne peut appartenir qu’à un seul cluster.</span><span class="sxs-lookup"><span data-stu-id="4a69b-220">**Note** If the model uses K-Means clustering, each case can belong to only one cluster.</span></span> <span data-ttu-id="4a69b-221">Toutefois, si le modèle utilise le clustering EM, chaque cas peut appartenir à un cluster différent, et une distance pondérée est attribuée au cas pour chaque cluster auquel il appartient.</span><span class="sxs-lookup"><span data-stu-id="4a69b-221">However, if the model uses EM clustering, each case can belong to different cluster, and the case is assigned a weighted distance for each cluster to which it belongs.</span></span> <span data-ttu-id="4a69b-222">Par conséquent, pour les modèles EM, la somme de la prise en charge pour un cluster individuel est supérieure à la prise en charge pour le modèle global.</span><span class="sxs-lookup"><span data-stu-id="4a69b-222">Therefore, for EM models the sum of support for an individual cluster is greater than support for the overall model.</span></span>  
  
 <span data-ttu-id="4a69b-223">MSOLAP_MODEL_COLUMN</span><span class="sxs-lookup"><span data-stu-id="4a69b-223">MSOLAP_MODEL_COLUMN</span></span>  
 <span data-ttu-id="4a69b-224">Non utilisé pour les modèles de clustering.</span><span class="sxs-lookup"><span data-stu-id="4a69b-224">Not used for clustering models.</span></span>  
  
 <span data-ttu-id="4a69b-225">MSOLAP_NODE_SCORE</span><span class="sxs-lookup"><span data-stu-id="4a69b-225">MSOLAP_NODE_SCORE</span></span>  
 <span data-ttu-id="4a69b-226">Affiche un score associé au nœud.</span><span class="sxs-lookup"><span data-stu-id="4a69b-226">Displays a score associated with the node.</span></span>  
  
 <span data-ttu-id="4a69b-227">**Nœud parent** : score BIC (Bayesian Information Criterion) du modèle de clustering.</span><span class="sxs-lookup"><span data-stu-id="4a69b-227">**Parent node** The Bayesian Information Criterion (BIC) score for the clustering model.</span></span>  
  
 <span data-ttu-id="4a69b-228">**Nœuds terminaux** : toujours 0.</span><span class="sxs-lookup"><span data-stu-id="4a69b-228">**Cluster nodes** Always 0.</span></span>  
  
 <span data-ttu-id="4a69b-229">MSOLAP_NODE_SHORT_CAPTION</span><span class="sxs-lookup"><span data-stu-id="4a69b-229">MSOLAP_NODE_SHORT_CAPTION</span></span>  
 <span data-ttu-id="4a69b-230">Étiquette utilisée à des fins d'affichage.</span><span class="sxs-lookup"><span data-stu-id="4a69b-230">A label used for display purposes.</span></span> <span data-ttu-id="4a69b-231">Vous ne pouvez pas modifier cette légende.</span><span class="sxs-lookup"><span data-stu-id="4a69b-231">You cannot change this caption.</span></span>  
  
 <span data-ttu-id="4a69b-232">**Nœud parent** : type de modèle : modèle de cluster.</span><span class="sxs-lookup"><span data-stu-id="4a69b-232">**Parent node** The type of model: Cluster model</span></span>  
  
 <span data-ttu-id="4a69b-233">**Nœuds du cluster** : nom du cluster.</span><span class="sxs-lookup"><span data-stu-id="4a69b-233">**Cluster nodes** The name of the cluster.</span></span> <span data-ttu-id="4a69b-234">Par exemple : Cluster 1.</span><span class="sxs-lookup"><span data-stu-id="4a69b-234">Example: Cluster 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a69b-235">Notes</span><span class="sxs-lookup"><span data-stu-id="4a69b-235">Remarks</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="4a69b-236">fournit plusieurs méthodes pour créer un modèle de clustering.</span><span class="sxs-lookup"><span data-stu-id="4a69b-236">provides multiple methods for creating a clustering model.</span></span> <span data-ttu-id="4a69b-237">Si vous ne savez pas quelle méthode a été utilisée pour créer le modèle avec lequel vous travaillez, vous pouvez récupérer les métadonnées du modèle par programmation en utilisant un client ADOMD ou un objet AMO, ou encore en interrogeant l'ensemble de lignes de schéma d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="4a69b-237">If you do not know which method was used to create the model that you are working with, you can retrieve the model metadata programmatically, by using an ADOMD client or AMO, or by querying the data mining schema rowset.</span></span> <span data-ttu-id="4a69b-238">Pour plus d’informations, consultez [Interroger les paramètres utilisés pour créer un modèle d’exploration de données](query-the-parameters-used-to-create-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="4a69b-238">For more information, see [Query the Parameters Used to Create a Mining Model](query-the-parameters-used-to-create-a-mining-model.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a69b-239">La structure et le contenu du modèle restent les même, indépendamment de la méthode de clustering ou des paramètres que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="4a69b-239">The structure and content of the model stay the same, regardless of which clustering method or parameters you use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a69b-240">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a69b-240">See Also</span></span>  
 <span data-ttu-id="4a69b-241">[Contenu du modèle d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4a69b-241">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="4a69b-242">[Visionneuses de modèles d’exploration de données](data-mining-model-viewers.md) </span><span class="sxs-lookup"><span data-stu-id="4a69b-242">[Data Mining Model Viewers](data-mining-model-viewers.md) </span></span>  
 <span data-ttu-id="4a69b-243">[Algorithme de clustering Microsoft](microsoft-clustering-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="4a69b-243">[Microsoft Clustering Algorithm](microsoft-clustering-algorithm.md) </span></span>  
 [<span data-ttu-id="4a69b-244">Requêtes d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="4a69b-244">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
