---
title: Solutions d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
- data mining [Analysis Services], development
ms.assetid: 84f6548d-ebb0-4e10-9b29-66253fa0a04a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0ab4b5ddcc9958fa36d6c8ecae0e7fd79585b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604293"
---
# <a name="data-mining-solutions"></a><span data-ttu-id="571cf-102">Solutions d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="571cf-102">Data Mining Solutions</span></span>
  <span data-ttu-id="571cf-103">Une solution d'exploration de données est une solution [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui contient un ou plusieurs projets d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="571cf-103">A data mining solution is an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] solution that contains one or more data mining projects.</span></span>  
  
 <span data-ttu-id="571cf-104">Les rubriques de cette section fournissent des informations sur la conception et l’implémentation d’une solution d’exploration de données intégrée à l’aide de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="571cf-104">The topics in this section provide information about how to design and implement an integrated data mining solution by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="571cf-105">Pour une présentation du processus de conception d’exploration de données et des outils connexes, consultez [Concepts d’exploration de données](data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="571cf-105">For an overview of the data mining design process and related tools, see [Data Mining Concepts](data-mining-concepts.md).</span></span>  
  
 <span data-ttu-id="571cf-106">Pour plus d’informations sur d’autres types de projets qui sont utiles pour l’exploration de données, consultez [Projets connexes pour des solutions d’exploration de données](data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="571cf-106">For more information about additional projects types that are useful for data mining, see [Related Projects for Data Mining Solutions](data-mining-solutions.md).</span></span>  
  
 [<span data-ttu-id="571cf-107">Modèles d'exploration de données relationnels et solutions multidimensionnelles</span><span class="sxs-lookup"><span data-stu-id="571cf-107">Relational vs. Multidimensional Solutions</span></span>](#bkmk_RelMD)  
  
 [<span data-ttu-id="571cf-108">Déploiement de solutions d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="571cf-108">Deploying Data Mining Solutions</span></span>](#bkmk_Deploy)  
  
 [<span data-ttu-id="571cf-109">Procédures pas à pas liées à la solution</span><span class="sxs-lookup"><span data-stu-id="571cf-109">Solution Walkthroughs</span></span>](#bkmk_Walkthru)  
  
##  <a name="relational-vs-multidimensional-solutions"></a><a name="bkmk_RelMD"></a><span data-ttu-id="571cf-110">Solutions relationnelles et solutions multidimensionnelles</span><span class="sxs-lookup"><span data-stu-id="571cf-110">Relational vs. Multidimensional Solutions</span></span>  
 <span data-ttu-id="571cf-111">Une solution d’exploration de données peut être basée sur des données multidimensionnelles (c’est-à-dire un cube existant) ou sur des données purement relationnelles, telles que les tables et les vues d’un entrepôt de données, ou sur des fichiers texte, des classeurs Excel ou d’autres sources de données externes.</span><span class="sxs-lookup"><span data-stu-id="571cf-111">A data mining solution can be based either on multidimensional data-that is, an existing cube-or on purely relational data, such as the tables and views in a data warehouse, or on text files, Excel workbooks, or other external data sources.</span></span>  
  
-   <span data-ttu-id="571cf-112">Vous pouvez créer des objets d'exploration de données dans une solution de base de données multidimensionnelle existante.</span><span class="sxs-lookup"><span data-stu-id="571cf-112">You can create data mining objects within an existing multidimensional database solution.</span></span>  
  
     <span data-ttu-id="571cf-113">Vous créez généralement une solution de ce genre si vous avez déjà créé un cube et que vous voulez effectuer une exploration de données en utilisant ce cube comme source de données.</span><span class="sxs-lookup"><span data-stu-id="571cf-113">Typically you would create a solution like this if you have already created a cube and want to perform data mining by using the cube as a data source.</span></span> <span data-ttu-id="571cf-114">Lorsque vous déplacez et sauvegardez des modèles basés sur un cube, le cube doit également être déplacé ou copié.</span><span class="sxs-lookup"><span data-stu-id="571cf-114">When you move and backup models based on a cube, the cube must also be moved or copied.</span></span>  
  
-   <span data-ttu-id="571cf-115">Vous pouvez créer une solution d'exploration de données qui contient uniquement des objets d'exploration de données, y compris les sources de données et vues de sources de données de prise en charge, et qui utilise uniquement la source de données relationnelle.</span><span class="sxs-lookup"><span data-stu-id="571cf-115">You can create a data mining solution that contains only data mining objects, including the supporting data sources and data source views, and that uses relational data source only.</span></span>  
  
     <span data-ttu-id="571cf-116">Cette méthode est recommandée pour créer des modèles d'exploration de données, car la rapidité du traitement et de l'interrogation est généralement optimale sur les sources de données relationnelles.</span><span class="sxs-lookup"><span data-stu-id="571cf-116">This is the preferred method for creating data mining models, as processing and querying is generally fastest against relational data sources.</span></span> <span data-ttu-id="571cf-117">Vous pouvez également déplacer et sauvegarder facilement des modèles entre des serveurs à l'aide des commandes EXPORT et IMPORT.</span><span class="sxs-lookup"><span data-stu-id="571cf-117">You can also easily move and backup models between servers by using the EXPORT and IMPORT commands.</span></span>  
  
##  <a name="deploying-data-mining-solutions"></a><a name="bkmk_Deploy"></a><span data-ttu-id="571cf-118">Déploiement de solutions d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="571cf-118">Deploying Data Mining Solutions</span></span>  
 <span data-ttu-id="571cf-119">L'instance d'[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dans laquelle vous déployez la solution doit être en cours d'exécution dans un mode qui prend en charge les objets multidimensionnels et les objets d'exploration de données ; autrement dit, vous ne pouvez pas déployer des objets d'exploration de données dans une instance qui héberge des modèles tabulaires ou des données PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="571cf-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="571cf-120">Par conséquent, lorsque vous créez une solution d'exploration de données dans Visual Studio, veillez à utiliser le modèle **Projet multidimensionnel et d'exploration de données Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="571cf-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="571cf-121">Lorsque vous déployez la solution, les objets utilisés pour l'exploration de données sont créés dans l'instance d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] spécifiée, dans une base de données portant le même nom que le fichier solution.</span><span class="sxs-lookup"><span data-stu-id="571cf-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
 <span data-ttu-id="571cf-122">Pour plus d’informations sur la façon de déployer des solutions relationnelles et des solutions multidimensionnelles, consultez [Déploiement de solutions d’exploration de données](deployment-of-data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="571cf-122">For more information about how to deploy both relational and multidimensional solutions, see [Deployment of Data Mining Solutions](deployment-of-data-mining-solutions.md).</span></span>  
  
##  <a name="solution-walkthrough"></a><a name="bkmk_Walkthru"></a> <span data-ttu-id="571cf-123">Procédure pas à pas liées à la solution</span><span class="sxs-lookup"><span data-stu-id="571cf-123">Solution Walkthrough</span></span>  
 <span data-ttu-id="571cf-124">Fournit une vue d'ensemble de la création de solutions d'exploration de données à l'aide de l'Assistant Exploration de données.</span><span class="sxs-lookup"><span data-stu-id="571cf-124">Provides an overview of how to create data mining solutions by using the Data Mining Wizard.</span></span>  
  
 [<span data-ttu-id="571cf-125">Créer une structure d’exploration de données relationnelle</span><span class="sxs-lookup"><span data-stu-id="571cf-125">Create a Relational Mining Structure</span></span>](create-a-relational-mining-structure.md)  
 <span data-ttu-id="571cf-126">Créez une structure d'exploration de données à partir de données relationnelles, de fichiers texte et d'autres sources qui peuvent être combinées dans une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="571cf-126">Create a mining structure from relational data, text files, and other sources that can be combined in a data source view.</span></span>  
  
 [<span data-ttu-id="571cf-127">Create an OLAP Mining Structure</span><span class="sxs-lookup"><span data-stu-id="571cf-127">Create an OLAP Mining Structure</span></span>](create-an-olap-mining-structure.md)  
 <span data-ttu-id="571cf-128">Créez une structure d'exploration de données basée sur des données dans un cube OLAP.</span><span class="sxs-lookup"><span data-stu-id="571cf-128">Create a mining structure based on data in an OLAP cube.</span></span> <span data-ttu-id="571cf-129">Les modèles que vous créez à partir de données OLAP peuvent être enregistrés en tant que dimension d'exploration de données, ou vous pouvez enregistrer l'ensemble de données et vos modèles en tant que nouveau cube.</span><span class="sxs-lookup"><span data-stu-id="571cf-129">Models that you create from OLAP data can be saved as a data mining dimension, or you can save the set of data and your models as a new cube.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="571cf-130">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="571cf-130">In This Section</span></span>  
 [<span data-ttu-id="571cf-131">Projets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="571cf-131">Data Mining Projects</span></span>](data-mining-projects.md)  
  
 [<span data-ttu-id="571cf-132">Traitement des objets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="571cf-132">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)  
  
 [<span data-ttu-id="571cf-133">Projets connexes pour des solutions d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="571cf-133">Related Projects for Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
 [<span data-ttu-id="571cf-134">Déploiement de solutions d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="571cf-134">Deployment of Data Mining Solutions</span></span>](deployment-of-data-mining-solutions.md)  
  
## <a name="related-tasks-and-topics"></a><span data-ttu-id="571cf-135">Tâches et rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="571cf-135">Related Tasks and Topics</span></span>  
 <span data-ttu-id="571cf-136">Après avoir créé une solution d'exploration de données de base, notamment des sources de données et une structure d'exploration de données, vous pouvez générer la solution en ajoutant de nouveaux modèles, en testant et en comparant des modèles, en créant des prédictions et effectuant des essais avec des sous-ensembles de données.</span><span class="sxs-lookup"><span data-stu-id="571cf-136">After you have created a basic data mining solution, including data sources and a mining structure, you can build on the solution by adding new models, testing and comparing models, creating predictions, and experimenting with subsets of data.</span></span>  
  
 <span data-ttu-id="571cf-137">Pour plus d'informations, consultez les liens suivants :</span><span class="sxs-lookup"><span data-stu-id="571cf-137">For more information, see the following links:</span></span>  
  
|<span data-ttu-id="571cf-138">Tâches</span><span class="sxs-lookup"><span data-stu-id="571cf-138">Tasks</span></span>|<span data-ttu-id="571cf-139">Rubriques</span><span class="sxs-lookup"><span data-stu-id="571cf-139">Topics</span></span>|  
|-----------|------------|  
|<span data-ttu-id="571cf-140">Testez les modèles que vous créez, validez la qualité de vos données d'apprentissage et créez des graphiques qui représentent la précision des modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="571cf-140">Test the models you create, validate the quality of your training data, and create charts that represent the accuracy of data mining models.</span></span>|[<span data-ttu-id="571cf-141">Test et validation &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="571cf-141">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)|  
|<span data-ttu-id="571cf-142">Effectuez l'apprentissage du modèle en remplissant la structure et les modèles associés avec des données.</span><span class="sxs-lookup"><span data-stu-id="571cf-142">Train the model by populating the structure and related models with data.</span></span> <span data-ttu-id="571cf-143">Mettez à jour et étendez des modèles avec de nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="571cf-143">Update and extend models with new data.</span></span>|[<span data-ttu-id="571cf-144">Traitement des objets d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="571cf-144">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)|  
|<span data-ttu-id="571cf-145">Personnalisez un modèle d'exploration de données en appliquant des filtres aux données d'apprentissage, en choisissant un algorithme différent ou en définissant des paramètres d'algorithme avancés.</span><span class="sxs-lookup"><span data-stu-id="571cf-145">Customize a mining model by applying filters to the training data, choosing a different algorithm, or setting advanced algorithm parameters.</span></span>|[<span data-ttu-id="571cf-146">Personnaliser les modèles et les structures d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="571cf-146">Customize Mining Models and Structure</span></span>](customize-mining-models-and-structure.md)|  
|<span data-ttu-id="571cf-147">Personnalisez un modèle d'exploration de données en appliquant des filtres aux données utilisées dans l'apprentissage du modèle.</span><span class="sxs-lookup"><span data-stu-id="571cf-147">Customize a mining model by applying filters to the data used in training the mode.</span></span>|[<span data-ttu-id="571cf-148">Ajouter des modèles d’exploration de données à une structure &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="571cf-148">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](add-mining-models-to-a-structure-analysis-services-data-mining.md)|  
|<span data-ttu-id="571cf-149">Mettez à jour et gérer des solutions d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="571cf-149">Update and manage data mining solutions.</span></span>|<span data-ttu-id="571cf-150">Lien à déterminer</span><span class="sxs-lookup"><span data-stu-id="571cf-150">Link TBD</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="571cf-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="571cf-151">See Also</span></span>  
 [<span data-ttu-id="571cf-152">Didacticiels sur l’exploration de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="571cf-152">Data Mining Tutorials &#40;Analysis Services&#41;</span></span>](../data-mining-tutorials-analysis-services.md)  
  
  
