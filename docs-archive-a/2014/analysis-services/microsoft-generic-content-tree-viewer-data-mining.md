---
title: Visionneuse de l’arborescence de contenu générique Microsoft (exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.contentviewer.f1
ms.assetid: 751b4393-f6fd-48c1-bcef-bdca589ce34c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0dab06d6af8f2c5af029d9ce831f518faa4067e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707956"
---
# <a name="microsoft-generic-content-tree-viewer-data-mining"></a><span data-ttu-id="4c26e-102">Visionneuse de l'arborescence de contenu générique Microsoft (exploration de données)</span><span class="sxs-lookup"><span data-stu-id="4c26e-102">Microsoft Generic Content Tree Viewer (Data Mining)</span></span>
  <span data-ttu-id="4c26e-103">La **Visionneuse de l'arborescence de contenu générique Microsoft** affiche des informations détaillées sur le contenu d'un modèle d'exploration de données dans un format de table HTML standardisé.</span><span class="sxs-lookup"><span data-stu-id="4c26e-103">The **Microsoft Generic Content Tree Viewer** displays detailed information about the contents of a data mining mode in a standardized HTML table format.</span></span> <span data-ttu-id="4c26e-104">Cette vue est utile car elle présente la structure sous-jacente du modèle, ainsi que des détails sur les coefficients, la distribution des valeurs, et beaucoup plus encore.</span><span class="sxs-lookup"><span data-stu-id="4c26e-104">This view is useful because it exposes the underlying structure of the model, as well details about coefficients, the distribution of values, and much more.</span></span>  
  
 <span data-ttu-id="4c26e-105">Le contenu réel affiché dans la table varie selon l'algorithme utilisé et peut inclure des colonnes, des règles, des propriétés, des attributs, des nœuds et des formules.</span><span class="sxs-lookup"><span data-stu-id="4c26e-105">The actual content displayed in the table varies depending on the algorithm that was used and might include columns, rules, properties, attributes, nodes, and formulas.</span></span> <span data-ttu-id="4c26e-106">Pour plus d’informations sur le contenu du modèle et sur l’interprétation des informations relatives à chaque type de modèle, consultez [Contenu du modèle d’exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4c26e-106">For more information about model content, and how to interpret the information for each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="4c26e-107">Les informations affichées dans la visionneuse utilisent une structure commune basée sur l'ensemble de lignes de schéma du contenu des modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="4c26e-107">The information that is displayed in the viewer uses a common structure that is based on the content schema rowset for mining models.</span></span> <span data-ttu-id="4c26e-108">L'ensemble de lignes de schéma de contenu est une infrastructure générique pour le stockage des modèles, des statistiques et d'autres contenus d'un modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="4c26e-108">The content schema rowset is a generic framework for storing patterns, statistics, and other contents of a data mining model.</span></span> <span data-ttu-id="4c26e-109">Pour obtenir la liste des colonnes contenues dans l’ensemble de lignes de schéma pour les modèles d’exploration de données, consultez [Ensemble de lignes DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="4c26e-109">For a list of the columns in the data mining schema rowset for mining models, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4c26e-110">Options</span><span class="sxs-lookup"><span data-stu-id="4c26e-110">Options</span></span>  
 <span data-ttu-id="4c26e-111">**Légende de nœud (identificateur unique)**</span><span class="sxs-lookup"><span data-stu-id="4c26e-111">**Node caption (Unique ID)**</span></span>  
 <span data-ttu-id="4c26e-112">Ce volet affiche la liste de tous les nœuds dans le modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4c26e-112">This pane displays a list of all the nodes in the selected mining model.</span></span> <span data-ttu-id="4c26e-113">La façon dont les nœuds sont réorganisés dans l'arborescence est différente selon le type de modèle que vous affichez.</span><span class="sxs-lookup"><span data-stu-id="4c26e-113">The way the nodes are arranged in the tree is different depending on the type of model you are viewing.</span></span>  
  
 <span data-ttu-id="4c26e-114">Vous pouvez cliquer sur chaque nœud pour afficher des détails le concernant dans le volet **Détails du nœud** .</span><span class="sxs-lookup"><span data-stu-id="4c26e-114">You can click each node to display details about the node in the **Node details** pane.</span></span>  
  
 <span data-ttu-id="4c26e-115">**Détails du nœud**</span><span class="sxs-lookup"><span data-stu-id="4c26e-115">**Node details**</span></span>  
 <span data-ttu-id="4c26e-116">Affiche des informations détaillées à propos du contenu du nœud sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4c26e-116">Displays detailed information about the content of the selected node.</span></span> <span data-ttu-id="4c26e-117">Chaque nœud stocke les informations le concernant dans un format standardisé, mais le contenu et la précision de chaque ligne de la table dépendent du type de modèle ou du type de nœud que vous affichez.</span><span class="sxs-lookup"><span data-stu-id="4c26e-117">Each node stores its information in a standardized format, but the contents and significance of each line of the table depends on the type of model or type of node that you are viewing.</span></span> <span data-ttu-id="4c26e-118">Par exemple, les informations stockées pour un nœud qui représente une règle dans un modèle d'association contiennent des informations différentes d'un nœud qui représente une arborescence dans un modèle d'arbre de décision.</span><span class="sxs-lookup"><span data-stu-id="4c26e-118">For example, the information stored for a node that represents a rule in an association model contains different information than a node that represents a tree in a decision trees model.</span></span>  
  
 <span data-ttu-id="4c26e-119">Pour en savoir plus sur l’interprétation des informations de nœud d’un type de modèle spécifique, consultez [Contenu du modèle d’exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4c26e-119">For information about how to interpret the node information for a specific model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c26e-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c26e-120">See Also</span></span>  
 <span data-ttu-id="4c26e-121">[Algorithmes d’exploration de données &#40;Analysis Services d’exploration de données&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4c26e-121">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="4c26e-122">[Visionneuses de modèles d’exploration de données &#40;le concepteur de modèle d’exploration de données&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="4c26e-122">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="4c26e-123">Requêtes d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="4c26e-123">Data Mining Queries</span></span>](data-mining/data-mining-queries.md)  
  
  
