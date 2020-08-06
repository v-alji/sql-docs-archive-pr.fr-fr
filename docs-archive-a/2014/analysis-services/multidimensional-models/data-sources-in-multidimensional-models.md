---
title: Sources de données dans les modèles multidimensionnels | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- metadata [Analysis Services]
- Analysis Services objects, data sources
- storing data [Analysis Services], data sources
- data sources [Analysis Services], about data sources
- security [Analysis Services], data sources
- data sources [Analysis Services]
- storage [Analysis Services], data sources
ms.assetid: a16469d9-9d53-4e35-9982-fc06327a9d33
author: minewiskan
ms.author: owend
ms.openlocfilehash: 41386c1c7abb0324aa17df24b3c427ca8cbb5615
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613182"
---
# <a name="data-sources-in-multidimensional-models"></a><span data-ttu-id="d66e8-102">Sources de données dans des modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="d66e8-102">Data Sources in Multidimensional Models</span></span>
  <span data-ttu-id="d66e8-103">Toutes les données que vous importez ou chargez dans un modèle multidimensionnel proviennent d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d66e8-103">All data that you import or load into a multidimensional model originates from an external data source.</span></span> <span data-ttu-id="d66e8-104">En général, les données source proviennent d’un entrepôt de données conçu pour générer des rapports, mais elles peuvent provenir de n’importe quelle base de données relationnelle, accessible directement ou indirectement via un intermédiaire, tel qu’un package [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d66e8-104">Typically, source data is from a data warehouse designed for reporting purposes, but it could come from any relational database that is accessed directly or indirectly through an intermediary, such as an [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span>  
  
 <span data-ttu-id="d66e8-105">Un objet **source de données** dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] spécifie une connexion directe à une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d66e8-105">A **data source** object in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] specifies a direct connection to an external data source.</span></span> <span data-ttu-id="d66e8-106">En plus de l'emplacement physique, un objet de source de données spécifie la chaîne de connexion, le fournisseur de données, les informations d'identification et d'autres propriétés qui contrôlent le comportement de connexion.</span><span class="sxs-lookup"><span data-stu-id="d66e8-106">In addition to physical location, a data source object specifies the connection string, data provider, credentials, and other properties that control connection behavior.</span></span>  
  
 <span data-ttu-id="d66e8-107">Les informations fournies par l'objet source de données sont utilisées pour les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d66e8-107">Information provided by the data source object is used during the following operations:</span></span>  
  
-   <span data-ttu-id="d66e8-108">Obtenir des informations sur le schéma et d'autres métadonnées utilisées pour générer des vues de sources de données dans un modèle.</span><span class="sxs-lookup"><span data-stu-id="d66e8-108">Get schema information and other metadata used to generate data source views into a model.</span></span>  
  
-   <span data-ttu-id="d66e8-109">Interroger ou charger des données dans un modèle lors du traitement.</span><span class="sxs-lookup"><span data-stu-id="d66e8-109">Query or load data into a model during processing.</span></span>  
  
-   <span data-ttu-id="d66e8-110">Exécuter des requêtes dans des modèles multidimensionnels ou d'exploration de données qui utilisent le mode de stockage ROLAP.</span><span class="sxs-lookup"><span data-stu-id="d66e8-110">Run queries against multidimensional or data mining models that use ROLAP storage mode.</span></span>  
  
-   <span data-ttu-id="d66e8-111">Écrire ou lire des partitions distantes.</span><span class="sxs-lookup"><span data-stu-id="d66e8-111">Read or write to remote partitions.</span></span>  
  
-   <span data-ttu-id="d66e8-112">Établir une connexion à des objets liés et effectuer une synchronisation de la cible vers la source.</span><span class="sxs-lookup"><span data-stu-id="d66e8-112">Connect to linked objects, as well as synchronize from target to source.</span></span>  
  
-   <span data-ttu-id="d66e8-113">Effectuer des opérations de réécriture qui mettent à jour les données de la table de faits stockées dans une base de données relationnelle.</span><span class="sxs-lookup"><span data-stu-id="d66e8-113">Perform write back operations that update fact table data stored in a relational database.</span></span>  
  
 <span data-ttu-id="d66e8-114">Au moment de la création d’un modèle multidimensionnel, vous commencez par créer l’objet source de données, puis vous l’utilisez pour générer l’objet suivant, une **vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="d66e8-114">When building a multidimensional model from the bottom up, you start by creating the data source object, and then use it to generate the next object, a **data source view**.</span></span> <span data-ttu-id="d66e8-115">Une vue de source de données est la couche d'abstraction de données dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="d66e8-115">A data source view is the data abstraction layer in the model.</span></span> <span data-ttu-id="d66e8-116">Il est généralement créée après l'objet source de données, à l'aide du schéma de la base de données source comme base.</span><span class="sxs-lookup"><span data-stu-id="d66e8-116">It is typically created after the data source object, using the schema of the source database as the basis.</span></span> <span data-ttu-id="d66e8-117">Toutefois, vous pouvez choisir d'autres méthodes pour générer un modèle, y compris commencer par les cubes et les dimensions et générer le schéma qui prend le mieux en charge votre conception.</span><span class="sxs-lookup"><span data-stu-id="d66e8-117">However, you can choose other ways to build a model, including starting with cubes and dimensions, and generating the schema that best supports your design.</span></span>  
  
 <span data-ttu-id="d66e8-118">Quelle que soit la méthode de création choisie, chaque modèle requiert au moins un objet source de données qui spécifie une connexion aux données source.</span><span class="sxs-lookup"><span data-stu-id="d66e8-118">Regardless of how you build it, each model requires at least one data source object that specifies a connection to source data.</span></span> <span data-ttu-id="d66e8-119">Vous pouvez créer plusieurs objets sources de données dans un modèle unique pour utiliser des données provenant de différentes sources ou modifier les propriétés de connexion d'objets spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d66e8-119">You can create multiple data source objects in a single model to use data from different sources or vary connection properties for specific objects.</span></span>  
  
 <span data-ttu-id="d66e8-120">Les objets sources de données peuvent être gérés indépendamment des autres objets dans votre modèle.</span><span class="sxs-lookup"><span data-stu-id="d66e8-120">Data source objects can be managed independently of other objects in your model.</span></span> <span data-ttu-id="d66e8-121">Après avoir créé une source de données, vous pouvez modifier ses propriétés ultérieurement, puis prétraiter le modèle pour vous assurer que les données sont récupérées correctement.</span><span class="sxs-lookup"><span data-stu-id="d66e8-121">After you create a data source, you can change its properties later, and then preprocess the model to ensure the data is retrieved correctly.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="d66e8-122">Tâches et rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="d66e8-122">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="d66e8-123">Rubrique</span><span class="sxs-lookup"><span data-stu-id="d66e8-123">Topic</span></span>|<span data-ttu-id="d66e8-124">Description</span><span class="sxs-lookup"><span data-stu-id="d66e8-124">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d66e8-125">Sources de données prises en charge &#40;SSAS multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="d66e8-125">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)|<span data-ttu-id="d66e8-126">Décrit les types de sources de données qui peuvent être utilisés dans un modèle multidimensionnel.</span><span class="sxs-lookup"><span data-stu-id="d66e8-126">Describes the types of data sources that can be used in a multidimensional model.</span></span>|  
|[<span data-ttu-id="d66e8-127">Créer une source de données &#40;SSAS Multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="d66e8-127">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](create-a-data-source-ssas-multidimensional.md)|<span data-ttu-id="d66e8-128">Explique comment ajouter un objet de source de données à un modèle multidimensionnel.</span><span class="sxs-lookup"><span data-stu-id="d66e8-128">Explains how to add a data source object to a multidimensional model.</span></span>|  
|[<span data-ttu-id="d66e8-129">Supprimer une source de données dans l’Explorateur de solutions &#40;SSAS Multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="d66e8-129">Delete a Data Source in Solution Explorer &#40;SSAS Multidimensional&#41;</span></span>](delete-a-data-source-in-solution-explorer-ssas-multidimensional.md)|<span data-ttu-id="d66e8-130">Utilisez cette procédure pour supprimer un objet de source de données d'un modèle multidimensionnel.</span><span class="sxs-lookup"><span data-stu-id="d66e8-130">Use this procedure to delete a data source object from a multidimensional model.</span></span>|  
|[<span data-ttu-id="d66e8-131">Définir les propriétés de la source de données &#40;SSAS Multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="d66e8-131">Set Data Source Properties &#40;SSAS Multidimensional&#41;</span></span>](set-data-source-properties-ssas-multidimensional.md)|<span data-ttu-id="d66e8-132">Décrit chaque propriété et explique comment la définir.</span><span class="sxs-lookup"><span data-stu-id="d66e8-132">Describes each property and explains how to set each one.</span></span>|  
|[<span data-ttu-id="d66e8-133">Définir les options d’emprunt d’identité &#40;SSAS - Multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="d66e8-133">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](set-impersonation-options-ssas-multidimensional.md)|<span data-ttu-id="d66e8-134">Explique comment configurer les options dans la boîte de dialogue Informations d'emprunt d'identité.</span><span class="sxs-lookup"><span data-stu-id="d66e8-134">Explains how to configure options in the Impersonation Information dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d66e8-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d66e8-135">See Also</span></span>  
 <span data-ttu-id="d66e8-136">[Objets de base de données &#40;Analysis Services-données multidimensionnelles&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d66e8-136">[Database Objects &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="d66e8-137">[Architecture logique &#40;Analysis Services-données multidimensionnelles&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d66e8-137">[Logical Architecture &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span></span>  
 <span data-ttu-id="d66e8-138">[Vues de sources de données dans les modèles multidimensionnels](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="d66e8-138">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="d66e8-139">Sources de données et liaisons &#40;SSAS Multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="d66e8-139">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](data-sources-and-bindings-ssas-multidimensional.md)  
  
  
