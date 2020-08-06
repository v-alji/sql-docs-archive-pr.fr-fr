---
title: Interroger les paramètres utilisés pour créer un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: ce7719e0-6127-4d9c-a753-0e0a3db065e1
author: minewiskan
ms.author: owend
ms.openlocfilehash: a3802a0d70579f613accbe6abd310da909751b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702159"
---
# <a name="query-the-parameters-used-to-create-a-mining-model"></a><span data-ttu-id="07ab1-102">Interroger les paramètres utilisés pour créer un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="07ab1-102">Query the Parameters Used to Create a Mining Model</span></span>
  <span data-ttu-id="07ab1-103">La composition d'un modèle d'exploration de données est affecté non seulement par les cas d'apprentissage, mais aussi par les paramètres définis lors de la création du modèle.</span><span class="sxs-lookup"><span data-stu-id="07ab1-103">The composition of a mining model is affected not only by the training cases, but by the parameters that were set when the model was created.</span></span> <span data-ttu-id="07ab1-104">Par conséquent, il peut s'avérer utile d'extraire les paramètres d'un modèle existant pour mieux comprendre le comportement du modèle.</span><span class="sxs-lookup"><span data-stu-id="07ab1-104">Therefore, you might find it useful to retrieve the parameter settings of an existing model to better understand the behavior of the model.</span></span> <span data-ttu-id="07ab1-105">La récupération des paramètres peut aussi servir à documenter une version particulière de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="07ab1-105">Retrieving parameters is also useful when documenting a particular version of that model.</span></span>  
  
 <span data-ttu-id="07ab1-106">Pour rechercher les paramètres qui ont été utilisés lors de la création du modèle, vous créez une requête sur l'un des ensembles de lignes de schéma de modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="07ab1-106">To find the parameters that were used when the model was created, you create a query against one of the mining model schema rowsets.</span></span> <span data-ttu-id="07ab1-107">Dans [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)], ces ensembles de lignes de schéma sont exposés sous la forme d’un ensemble de vues système que vous pouvez interroger facilement en utilisant la syntaxe Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="07ab1-107">In [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)], these schema rowsets are exposed as a set of system views that you can query easily by using Transact-SQL syntax.</span></span> <span data-ttu-id="07ab1-108">Cette procédure décrit comment créer une requête qui retourne les paramètres qui ont été utilisés pour créer le modèle d'exploration de données spécifié.</span><span class="sxs-lookup"><span data-stu-id="07ab1-108">This procedure describes how to create a query that returns the parameters that were used to create the specified mining model.</span></span>  
  
### <a name="to-open-a-query-window-for-a-schema-rowset-query"></a><span data-ttu-id="07ab1-109">Pour ouvrir une fenêtre Requête pour une requête d'ensemble de lignes de schéma</span><span class="sxs-lookup"><span data-stu-id="07ab1-109">To open a Query window for a schema rowset query</span></span>  
  
1.  <span data-ttu-id="07ab1-110">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez l'instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui contient le modèle à interroger.</span><span class="sxs-lookup"><span data-stu-id="07ab1-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the model you want to query.</span></span>  
  
2.  <span data-ttu-id="07ab1-111">Cliquez avec le bouton droit sur le nom de l’instance, sélectionnez **Nouvelle requête**, puis sélectionnez **DMX**.</span><span class="sxs-lookup"><span data-stu-id="07ab1-111">Right-click the instance name, select **New Query**, and then select **DMX**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="07ab1-112"> Vous pouvez également créer une requête sur un modèle d'exploration de données à l'aide du modèle **MDX** .</span><span class="sxs-lookup"><span data-stu-id="07ab1-112">You can also create a query against a data mining model by using the **MDX** template.</span></span>  
  
3.  <span data-ttu-id="07ab1-113">Si l'instance contient plusieurs bases de données, sélectionnez la base de données contenant le modèle à interroger dans la liste **Bases de données disponibles** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="07ab1-113">If the instance contains multiple databases, select the database that contains the model you want to query from the **Available Databases** list in the toolbar.</span></span>  
  
### <a name="to-return-model-parameters-for-an-existing-mining-model"></a><span data-ttu-id="07ab1-114">Pour retourner les paramètres de modèle pour un modèle d'exploration de données existant</span><span class="sxs-lookup"><span data-stu-id="07ab1-114">To return model parameters for an existing mining model</span></span>  
  
1.  <span data-ttu-id="07ab1-115">Dans le volet Requête DMX, tapez ou collez le texte suivant :</span><span class="sxs-lookup"><span data-stu-id="07ab1-115">In the DMX query pane, type or paste the following text:</span></span>  
  
    ```  
    SELECT MINING_PARAMETERS  
    FROM $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = ''  
    ```  
  
2.  <span data-ttu-id="07ab1-116">Dans l'Explorateur d'objets, sélectionnez le modèle d'exploration de données désiré, puis faites-le glisser dans le volet Requête DMX entre les guillemets simples.</span><span class="sxs-lookup"><span data-stu-id="07ab1-116">In Object Explorer, select the mining model you want, and then drag it into the DMX Query pane, between the single quotation marks.</span></span>  
  
3.  <span data-ttu-id="07ab1-117">Appuyez sur F5 ou cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="07ab1-117">Press F5, or click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07ab1-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="07ab1-118">Example</span></span>  
 <span data-ttu-id="07ab1-119">Le code suivant retourne la liste des paramètres utilisés pour créer le modèle d'exploration de données dans le [Didacticiel sur l'exploration de données de base](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="07ab1-119">The following code returns a list of the parameters that were used to create the mining model that you build in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="07ab1-120">Ces paramètres incluent les valeurs explicites des options par défaut utilisées par les services d'exploration de données disponibles à partir des fournisseurs sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="07ab1-120">These parameters include the explicit values for any defaults used by the mining services available from providers on the server.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
 <span data-ttu-id="07ab1-121">L'exemple de code retourne les paramètres suivants pour le modèle de clustering :</span><span class="sxs-lookup"><span data-stu-id="07ab1-121">The code example returns the following parameters for the clustering model:</span></span>  
  
 <span data-ttu-id="07ab1-122">Résultats de l'exemple :</span><span class="sxs-lookup"><span data-stu-id="07ab1-122">eExample Results:</span></span>  
  
 <span data-ttu-id="07ab1-123">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="07ab1-123">MINING_PARAMETERS</span></span>  
  
 <span data-ttu-id="07ab1-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span><span class="sxs-lookup"><span data-stu-id="07ab1-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ab1-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07ab1-125">See Also</span></span>  
 <span data-ttu-id="07ab1-126">[Tâches de requête d’exploration de données et procédures](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="07ab1-126">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="07ab1-127">Requêtes d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="07ab1-127">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
