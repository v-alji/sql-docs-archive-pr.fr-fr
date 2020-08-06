---
title: Parcourir un modèle à l’aide de la visionneuse de l’arborescence de contenu générique Microsoft | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining model content, viewing
ms.assetid: 4a5f7c51-c704-4214-b05d-21cf735e6d96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90d47262a09060a11020e50b3724753799d2d188
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614279"
---
# <a name="browse-a-model-using-the-microsoft-generic-content-tree-viewer"></a><span data-ttu-id="e48d7-102">Explorer un modèle à l'aide de la visionneuse de l'arborescence de contenu générique Microsoft</span><span class="sxs-lookup"><span data-stu-id="e48d7-102">Browse a Model Using the Microsoft Generic Content Tree Viewer</span></span>
  <span data-ttu-id="e48d7-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Mining Model Content Viewer fournit des informations détaillées sur les séquences identifiées par l’algorithme d’exploration de données et donne aussi accès aux différentes statistiques générées pendant le processus d’analyse.</span><span class="sxs-lookup"><span data-stu-id="e48d7-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Mining Model Content Viewer provides detailed information about the patterns found by the mining algorithm, and also provides access to various statistics generated during the analysis process.</span></span> <span data-ttu-id="e48d7-104">Les informations varient en quantité et en type selon l'algorithme utilisé, mais elles peuvent inclure les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="e48d7-104">The amount and type of information depends on the algorithm that was used, but can include the following categories:</span></span>  
  
-   <span data-ttu-id="e48d7-105">Des segments de données et leurs caractéristiques.</span><span class="sxs-lookup"><span data-stu-id="e48d7-105">Segments of data, and their characteristics.</span></span>  
  
-   <span data-ttu-id="e48d7-106">Des statistiques descriptives sur chaque de groupe ou sur le jeu entier de données.</span><span class="sxs-lookup"><span data-stu-id="e48d7-106">Descriptive statistics about each group or about the whole set of data.</span></span>  
  
-   <span data-ttu-id="e48d7-107">Le nombre de branches ou de nœuds enfants dans une arborescence.</span><span class="sxs-lookup"><span data-stu-id="e48d7-107">The number of branches or child nodes in a tree.</span></span>  
  
-   <span data-ttu-id="e48d7-108">Des calculs, tels que la variance et la moyenne, pour un cluster ou un jeu entier de données.</span><span class="sxs-lookup"><span data-stu-id="e48d7-108">Calculations, such as variance and mean, for a cluster or a whole set of data.</span></span>  
  
 <span data-ttu-id="e48d7-109">Ces informations peuvent vous aider à mieux comprendre les résultats de votre analyse.</span><span class="sxs-lookup"><span data-stu-id="e48d7-109">Viewing this information can help you better understand the results of your analysis.</span></span> <span data-ttu-id="e48d7-110">Vous pouvez aussi identifier comment ajuster votre modèle puis effectuer un nouvel apprentissage,</span><span class="sxs-lookup"><span data-stu-id="e48d7-110">You can also identify ways to fine-tune, and then retrain, your model.</span></span> <span data-ttu-id="e48d7-111">ou bien décider d'effectuer un nouvel apprentissage en utilisant un algorithme différent.</span><span class="sxs-lookup"><span data-stu-id="e48d7-111">Or, you might decide to retrain by using a different algorithm.</span></span>  
  
## <a name="viewing-mining-model-content"></a><span data-ttu-id="e48d7-112">Affichage du contenu d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="e48d7-112">Viewing Mining Model Content</span></span>  
 <span data-ttu-id="e48d7-113">[!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Viewer affiche les colonnes, les règles, les propriétés, les attributs, les nœuds et tout autre contenu de *l’ensemble de lignes du schéma de contenu* du modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e48d7-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Viewer displays the columns, rules, properties, attributes, nodes, and other content from the *content schema rowset* of the mining model.</span></span> <span data-ttu-id="e48d7-114">L'ensemble de lignes de schéma du contenu est une infrastructure générique permettant de présenter des informations détaillées sur le contenu d'un modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e48d7-114">The content schema rowset is a generic framework for presenting detailed information about the content of a data mining model.</span></span>  
  
 <span data-ttu-id="e48d7-115">Ces informations détaillées sont contenues dans une table HTML qui représente les modèles, les clusters ou les arborescences du modèle en tant que nœuds.</span><span class="sxs-lookup"><span data-stu-id="e48d7-115">This detailed information is contained in an HTML table that represents the patterns, clusters, or trees in the model as nodes.</span></span> <span data-ttu-id="e48d7-116">Vous pouvez cliquer sur chaque nœud et le développer pour obtenir plus de détails, tels que les formules ou le nombre de valeurs distinctes pour un attribut numérique.</span><span class="sxs-lookup"><span data-stu-id="e48d7-116">You can click on each node and expand it to see more detail, such as the formulas or the count of distinct values for a numeric attribute.</span></span> <span data-ttu-id="e48d7-117">Vous pouvez également explorer les relations parent/enfant entre les nœuds.</span><span class="sxs-lookup"><span data-stu-id="e48d7-117">You can also explore the child-parent relationships among the nodes.</span></span>  
  
 <span data-ttu-id="e48d7-118">Pour plus d’informations sur la signification générale des termes utilisés dans le contenu du modèle d’exploration de données, consultez [Contenu du modèle d’exploration &#40;Analysis Services - Exploration de données&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="e48d7-118">For more information about the general meaning of the terms used in the mining model content, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span> <span data-ttu-id="e48d7-119">Cette rubrique contient également des liens vers des informations relatives au contenu des modèles d'exploration de données pour des types de modèles spécifiques.</span><span class="sxs-lookup"><span data-stu-id="e48d7-119">The topic also contains links to information about mining model content for specific types of models.</span></span> <span data-ttu-id="e48d7-120">Étant donné que chaque type de modèle d'exploration de données contient des informations qui sont très spécifiques à l'algorithme et aux modèles se trouvant dans les données, nous vous recommandons de consulter la rubrique de références techniques pour chaque type de modèle afin de comprendre parfaitement les détails de chaque type de modèle.</span><span class="sxs-lookup"><span data-stu-id="e48d7-120">Each type of mining model contains information that is highly specific to the algorithm and the patterns found in the data, so we recommend that you consult the technical reference topic for each model type in order to fully understand each model type.</span></span>  
  
## <a name="querying-mining-model-content"></a><span data-ttu-id="e48d7-121">Interrogation du contenu d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="e48d7-121">Querying Mining Model Content</span></span>  
 <span data-ttu-id="e48d7-122">Vous pouvez également accéder aux informations fournies par la visionneuse de l’arborescence de contenu générique [!INCLUDE[msCoName](../../includes/msconame-md.md)] en interrogeant le modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e48d7-122">The same information that is provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer is also available by querying the mining model.</span></span> <span data-ttu-id="e48d7-123">Vous pouvez créer des requêtes sur le contenu du modèle d'exploration de données en utilisant des instructions DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="e48d7-123">You can create queries against mining model content by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="e48d7-124">Par exemple, dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vous pouvez exécuter une requête de contenu en utilisant l’instruction DMX suivante :</span><span class="sxs-lookup"><span data-stu-id="e48d7-124">For example, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can run a content query by executing the following DMX statement:</span></span>  
  
```  
SELECT * FROM [<mining model name>].CONTENT  
```  
  
 <span data-ttu-id="e48d7-125">Pour plus d’informations, consultez [Requêtes d’exploration de données](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e48d7-125">For more information, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e48d7-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e48d7-126">See Also</span></span>  
 <span data-ttu-id="e48d7-127">[Visionneuse de l’arborescence de contenu générique Microsoft &#40;l’exploration de données&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="e48d7-127">[Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md) </span></span>  
 [<span data-ttu-id="e48d7-128">Algorithmes d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="e48d7-128">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
  
