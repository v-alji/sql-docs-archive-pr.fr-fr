---
title: Déploiement de solutions d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], deploying
- deploying [Analysis Services], production environments
- deploying [Analysis Services - data mining]
- solutions [Analysis Services], deploying
- models [Analysis Services], data mining
ms.assetid: d83effc7-437d-42e9-8ac3-b65f79e27043
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5764be2f7530add2fa4cb028b288be69598bb95c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613219"
---
# <a name="deployment-of-data-mining-solutions"></a><span data-ttu-id="ecea7-102">Déploiement de solutions d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="ecea7-102">Deployment of Data Mining Solutions</span></span>
  <span data-ttu-id="ecea7-103">La dernière étape du processus d'exploration de données consiste à déployer les modèles dans un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="ecea7-103">The last step in the data mining process is to deploy the models to a production environment.</span></span> <span data-ttu-id="ecea7-104">Le déploiement est important car il met les modèles à la disposition des utilisateurs afin de vous permettre d'effectuer n'importe laquelle des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ecea7-104">Deployment is important because it makes the models available to users so that you can perform any of the following tasks:</span></span>  
  
-   <span data-ttu-id="ecea7-105">Utiliser les modèles pour créer des prédictions et prendre des décisions d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="ecea7-105">Use the models to create predictions and make business decisions.</span></span> <span data-ttu-id="ecea7-106">Pour plus d’informations sur les outils que vous pouvez utiliser pour créer des requêtes, consultez [interfaces de requête d’exploration de données](data-mining-query-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ecea7-106">For information about the tools you can use to create queries, see [Data Mining Query Interfaces](data-mining-query-tools.md).</span></span>  
  
-   <span data-ttu-id="ecea7-107">Incorporer la fonctionnalité d'exploration de données directement dans une application.</span><span class="sxs-lookup"><span data-stu-id="ecea7-107">Embed data mining functionality directly into an application.</span></span> <span data-ttu-id="ecea7-108">Vous pouvez inclure des objets AMO (Analysis Management Objects) ou un assembly contenant un ensemble d'objets qui peuvent être utilisés par votre application pour créer, modifier, traiter et supprimer des structures d'exploration de données et des modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="ecea7-108">You can include Analysis Management Objects (AMO) or an assembly that contains a set of objects that your application can use to create, alter, process, and delete mining structures and mining models.</span></span>  
  
-   <span data-ttu-id="ecea7-109">Créer des rapports qui permettent aux utilisateurs de demander des prédictions, d'afficher des tendances ou de comparer des modèles.</span><span class="sxs-lookup"><span data-stu-id="ecea7-109">Create reports that let users request predictions, view trends, or compare models.</span></span>  
  
 <span data-ttu-id="ecea7-110">Cette section fournit des informations détaillées sur les options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ecea7-110">This section provides detailed information about deployment options.</span></span>  
  
 [<span data-ttu-id="ecea7-111">Conditions requises pour le déploiement de solutions d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="ecea7-111">Requirements for Deployment of Data Mining Solutions</span></span>](#bkmk_Reqs)  
  
 [<span data-ttu-id="ecea7-112">Déploiement d'une solution relationnelle</span><span class="sxs-lookup"><span data-stu-id="ecea7-112">Deploying a Relational Solution</span></span>](#bkmk_RelationalSltn)  
  
 [<span data-ttu-id="ecea7-113">Déploiement d'une solution multidimensionnelle</span><span class="sxs-lookup"><span data-stu-id="ecea7-113">Deploying a Multidimensional Solution</span></span>](#bkmk_MDSltn)  
  
 [<span data-ttu-id="ecea7-114">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="ecea7-114">Related Resources</span></span>](#bkmk_Resources)  
  
## <a name="in-this-section"></a><span data-ttu-id="ecea7-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ecea7-115">In This Section</span></span>  
 [<span data-ttu-id="ecea7-116">Déployer une solution d'exploration de données sur des versions antérieures de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ecea7-116">Deploy a Data Mining Solution to Previous Versions of SQL Server</span></span>](deploy-a-data-mining-solution-to-previous-versions-of-sql-server.md)  
  
 [<span data-ttu-id="ecea7-117">Exporter et importer des objets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="ecea7-117">Export and Import Data Mining Objects</span></span>](export-and-import-data-mining-objects.md)  
  
##  <a name="requirements-for-deployment-of-data-mining-solutions"></a><a name="bkmk_Reqs"></a><span data-ttu-id="ecea7-118">Conditions requises pour le déploiement de solutions d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="ecea7-118">Requirements for Deployment of Data Mining Solutions</span></span>  
 <span data-ttu-id="ecea7-119">L'instance d'[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dans laquelle vous déployez la solution doit être en cours d'exécution dans un mode qui prend en charge les objets multidimensionnels et les objets d'exploration de données ; autrement dit, vous ne pouvez pas déployer des objets d'exploration de données dans une instance qui héberge des modèles tabulaires ou des données PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="ecea7-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="ecea7-120">Par conséquent, lorsque vous créez une solution d'exploration de données dans Visual Studio, veillez à utiliser le modèle **Projet multidimensionnel et d'exploration de données Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="ecea7-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="ecea7-121">Lorsque vous déployez la solution, les objets utilisés pour l'exploration de données sont créés dans l'instance d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] spécifiée, dans une base de données portant le même nom que le fichier solution.</span><span class="sxs-lookup"><span data-stu-id="ecea7-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
###  <a name="deploying-a-relational-solution"></a><a name="bkmk_RelationalSltn"></a><span data-ttu-id="ecea7-122">Déploiement d’une solution relationnelle</span><span class="sxs-lookup"><span data-stu-id="ecea7-122">Deploying a Relational Solution</span></span>  
 <span data-ttu-id="ecea7-123">Lorsque vous déployez une solution d'exploration de données relationnelle, les objets d'exploration de données requis sont créés dans une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , et les objets sont traités par défaut.</span><span class="sxs-lookup"><span data-stu-id="ecea7-123">When you deploy a relational data mining solution, the required data mining objects are created within a new [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, and the objects are processed by default.</span></span> <span data-ttu-id="ecea7-124">Vous pouvez modifier les options de traitement à l'aide de la propriété de configuration **Option de traitement**.</span><span class="sxs-lookup"><span data-stu-id="ecea7-124">You can change processing options by using the configuration property, **Processing Option**.</span></span> <span data-ttu-id="ecea7-125">Pour plus d’informations, consultez [Configurer les propriétés d’un projet Analysis Services &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="ecea7-125">For more information, see [Configure Analysis Services Project Properties &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md).</span></span>  
  
 <span data-ttu-id="ecea7-126">Par défaut, seules les modifications incrémentielles sont déployées à chaque fois.</span><span class="sxs-lookup"><span data-stu-id="ecea7-126">By default, only incremental changes are deployed each time.</span></span> <span data-ttu-id="ecea7-127">En d'autres termes, vous pouvez modifier un modèle d'exploration de données, et lorsque vous redéployez le projet, seul ce modèle d'exploration de données est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="ecea7-127">In other words, you can modify a mining model, and when you re-deploy the project, only that mining model would be updated.</span></span> <span data-ttu-id="ecea7-128">Toutefois, si vous avez plusieurs clients qui modifient la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , cela peut générer des erreurs.</span><span class="sxs-lookup"><span data-stu-id="ecea7-128">However, if you have multiple clients editing the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, this can lead to errors.</span></span> <span data-ttu-id="ecea7-129">Pour modifier le mode de déploiement par défaut afin que la totalité de la base de données soit actualisée lorsque vous déployez la solution, modifiez la propriété **Mode de déploiement** .</span><span class="sxs-lookup"><span data-stu-id="ecea7-129">To change the default deployment mode so that the entire database is refreshed when you deploy the solution, change the **Deployment Mode** property</span></span>  
  
 <span data-ttu-id="ecea7-130">Dans une solution d'exploration de données relationnelles, les seuls objets qui doivent être déployés sont la définition des sources de données, toute vue de sources de données, les structures d'exploration de données et tous les modèles d'exploration de données dépendants.</span><span class="sxs-lookup"><span data-stu-id="ecea7-130">In a relational data mining solution, the only objects that must be deployed are the data source definition, any data source views that were used, the mining structures, and all dependent mining models.</span></span>  
  
###  <a name="deploying-a-multidimensional-solution"></a><a name="bkmk_MDSltn"></a><span data-ttu-id="ecea7-131">Déploiement d’une solution multidimensionnelle</span><span class="sxs-lookup"><span data-stu-id="ecea7-131">Deploying a Multidimensional Solution</span></span>  
 <span data-ttu-id="ecea7-132">Lorsque vous déployez une solution d'exploration de données multidimensionnelle, cette solution crée vos objets d'exploration de données dans la même base de données que le cube source.</span><span class="sxs-lookup"><span data-stu-id="ecea7-132">When you deploy a multidimensional data mining solution, this solution creates your data mining objects within the same database as the source cube.</span></span>  
  
 <span data-ttu-id="ecea7-133">Lorsque vous traitez la structure d'exploration de données ou le modèle d'exploration de données, vous devez également traiter le cube source.</span><span class="sxs-lookup"><span data-stu-id="ecea7-133">When you process the mining structure or mining model, you must process the source cube as well.</span></span> <span data-ttu-id="ecea7-134">Par conséquent, le déploiement d'une solution qui utilise des modèles d'exploration de données OLAP peut prendre plus de temps que les solutions d'exploration de données relationnelles.</span><span class="sxs-lookup"><span data-stu-id="ecea7-134">For this reason, deploying a solution that uses OLAP mining models can take longer than relational data mining solutions.</span></span>  
  
 <span data-ttu-id="ecea7-135">En général, les objets d'exploration de données utilisent également les mêmes sources de données et vues de sources de données que celles utilisées pour le cube.</span><span class="sxs-lookup"><span data-stu-id="ecea7-135">Typically data mining objects also use the same data sources and data source views that are used for the cube.</span></span> <span data-ttu-id="ecea7-136">Toutefois, vous pouvez ajouter des sources de données et des vues de sources de données qui sont spécifiquement destinées à l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="ecea7-136">However, you can add data sources and data source views that are targeted specifically to data mining.</span></span> <span data-ttu-id="ecea7-137">Par exemple, un cube ne contient généralement pas de données sur les clients potentiels, ou sur les données externes non utilisées dans les objets multidimensionnels.</span><span class="sxs-lookup"><span data-stu-id="ecea7-137">For example, typically a cube would not contain data about prospective clients, or external data not used in the multidimensional objects.</span></span>  
  
##  <a name="related-resources"></a><a name="bkmk_Resources"></a><span data-ttu-id="ecea7-138">Ressources associées</span><span class="sxs-lookup"><span data-stu-id="ecea7-138">Related Resources</span></span>  
 [<span data-ttu-id="ecea7-139">Déplacement d'objets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="ecea7-139">Moving Data Mining Objects</span></span>](moving-data-mining-objects.md)  
  
 <span data-ttu-id="ecea7-140">Si votre modèle est basé uniquement sur des données relationnelles, l'exportation et l'importation d'objets à l'aide de DMX est la façon la plus simple de déplacer des modèles.</span><span class="sxs-lookup"><span data-stu-id="ecea7-140">If your model is based on relational data only, exporting and importing objects using DMX is the easiest way to move models.</span></span>  
  
 [<span data-ttu-id="ecea7-141">Déplacer une base de données Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ecea7-141">Move an Analysis Services Database</span></span>](../multidimensional-models/move-an-analysis-services-database.md)  
  
 <span data-ttu-id="ecea7-142">Lorsque des modèles utilisent un cube comme source de données, reportez-vous à cette rubrique pour plus d'informations sur le déplacement de modèles et de leurs données de cube de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="ecea7-142">When models use a cube as a data source, refer to this topic for more information about how to move models and their supporting cube data.</span></span>  
  
 [<span data-ttu-id="ecea7-143">Déployer des projets Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="ecea7-143">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](../multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
 <span data-ttu-id="ecea7-144">Fournit des informations générales sur le déploiement de projets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , et décrit les propriétés que vous pouvez définir dans le cadre de la configuration du projet.</span><span class="sxs-lookup"><span data-stu-id="ecea7-144">Provides general information about deployment of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects, and describes the properties that you can set as part of the project configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecea7-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ecea7-145">See Also</span></span>  
 <span data-ttu-id="ecea7-146">[Traitement d’objets de modèle multidimensionnel](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="ecea7-146">[Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span></span>  
 <span data-ttu-id="ecea7-147">[Interfaces de requête d’exploration de données](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ecea7-147">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="ecea7-148">Exigences et considérations concernant le traitement &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="ecea7-148">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](processing-requirements-and-considerations-data-mining.md)  
  
  
