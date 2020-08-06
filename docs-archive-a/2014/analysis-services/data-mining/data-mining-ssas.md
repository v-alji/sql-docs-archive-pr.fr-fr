---
title: Exploration de données (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
ms.assetid: b1c912da-72f6-4d96-89c8-55a2c4f19e88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7044ee397d457f7924d0db99dbec6659f969f104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612629"
---
# <a name="data-mining-ssas"></a><span data-ttu-id="5e540-102">Data Mining (SSAS)</span><span class="sxs-lookup"><span data-stu-id="5e540-102">Data Mining (SSAS)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="5e540-103">fournit une plateforme intégrée pour les solutions qui intègrent l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="5e540-103">provides an integrated platform for solutions that incorporate data mining.</span></span> <span data-ttu-id="5e540-104">Vous pouvez utiliser des données de cube ou relationnelles pour créer des solutions décisionnelles avec des analyses prévisionnelles.</span><span class="sxs-lookup"><span data-stu-id="5e540-104">You can use either relational or cube data to create business intelligence solutions with predictive analytics.</span></span>  
  
## <a name="benefits-of-data-mining"></a><span data-ttu-id="5e540-105">Avantages de l’exploration de données</span><span class="sxs-lookup"><span data-stu-id="5e540-105">Benefits of Data Mining</span></span>  
 <span data-ttu-id="5e540-106">L'exploration de données utilise les principes statistiques bien connus pour découvrir des modèles dans vos données, afin de prendre des décisions réfléchies concernant des problèmes complexes.</span><span class="sxs-lookup"><span data-stu-id="5e540-106">Data mining uses well-researched statistical principles to discover patterns in your data, helping you make intelligent decisions about complex problems.</span></span> <span data-ttu-id="5e540-107">En appliquant les algorithmes d'exploration de données dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à vos données, vous pouvez prévoir des tendances, identifier des modèles, créer des règles et des recommandations, analyser la séquence d'événements dans des jeux de données complexes et bénéficier de nouvelles analyses.</span><span class="sxs-lookup"><span data-stu-id="5e540-107">By applying the data mining algorithms in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to your data, you can forecast trends, identify patterns, create rules and recommendations, analyze the sequence of events in complex data sets, and gain new insights.</span></span>  
  
 <span data-ttu-id="5e540-108">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], l’exploration des données est une fonctionnalité puissante et accessible, qui est intégrée aux principaux outils utilisés pour effectuer des analyses et créer des rapports.</span><span class="sxs-lookup"><span data-stu-id="5e540-108">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], data mining is powerful, accessible, and integrated with the tools that many people prefer to use for analysis and reporting.</span></span> <span data-ttu-id="5e540-109">Consultez les liens de cette section pour connaître la structure générale de l'exploration de données dont vous avez besoin pour commencer.</span><span class="sxs-lookup"><span data-stu-id="5e540-109">See the links in this section to get the broad background about data mining that you need to get started.</span></span>  
  
## <a name="key-data-mining-features"></a><span data-ttu-id="5e540-110">Fonctionnalités d'exploration de données clés</span><span class="sxs-lookup"><span data-stu-id="5e540-110">Key Data Mining Features</span></span>  
 <span data-ttu-id="5e540-111">SQL Server fournit les fonctionnalités suivantes pour la prise en charge des solutions d'exploration de données intégrées :</span><span class="sxs-lookup"><span data-stu-id="5e540-111">SQL Server provides the following features in support of integrated data mining solutions:</span></span>  
  
-   <span data-ttu-id="5e540-112">Plusieurs sources de données : vous n'avez pas à créer d'entrepôt de données ni de cube OLAP pour effectuer l'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="5e540-112">Multiple data sources: You do not have to create a data warehouse or an OLAP cube to do data mining.</span></span> <span data-ttu-id="5e540-113">Vous pouvez utiliser des données tabulaires, des feuilles de calcul et même des fichiers texte provenant de fournisseurs externes.</span><span class="sxs-lookup"><span data-stu-id="5e540-113">You can use tabular data from external providers, spreadsheets, and even text files.</span></span> <span data-ttu-id="5e540-114">Vous pouvez aussi facilement exploiter les cubes OLAP créés dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e540-114">You can also easily mine OLAP cubes created in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="5e540-115">Toutefois, vous ne pouvez pas utiliser les données d'une base de données en mémoire.</span><span class="sxs-lookup"><span data-stu-id="5e540-115">However, you cannot use data from an in-memory database.</span></span>  
  
-   <span data-ttu-id="5e540-116">Nettoyage de données intégré, gestion des données et ETL (extraction, transformation et chargement) : Data Quality Services fournit des outils avancés pour le profilage et le nettoyage des données.</span><span class="sxs-lookup"><span data-stu-id="5e540-116">Integrated data cleansing, data management, and ETL: Data Quality Services provides advanced tools for profiling and cleansing data.</span></span> <span data-ttu-id="5e540-117">Integration Services peut être utilisé pour générer des processus ETL pour nettoyer les données, ainsi que pour créer, traiter, effectuer l'apprentissage et mettre à jour des modèles.</span><span class="sxs-lookup"><span data-stu-id="5e540-117">Integration Services can be used to build ETL processes for cleaning data, and also for building, processing, training, and updating models.</span></span>  
  
-   <span data-ttu-id="5e540-118">Plusieurs algorithmes personnalisables : outre la mise à disposition d'algorithmes comme le clustering, les réseaux neuronaux et les arbres de décision, la plateforme prend en charge le développement de vos propres algorithmes de plug-in personnalisés.</span><span class="sxs-lookup"><span data-stu-id="5e540-118">Multiple customizable algorithms: In addition to providing algorithms such as clustering, neural networks, and decisions trees, the platform supports development of your own custom plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="5e540-119">Infrastructure de test de modèle : testez vos modèles et jeux de données à l'aide d'outils statistiques importants comme la validation croisée, les matrices de classification, les graphiques de courbes d'élévation et les nuages de points.</span><span class="sxs-lookup"><span data-stu-id="5e540-119">Model testing infrastructure: Test your models and data sets using important statistical tools as cross-validation, classification matrices, lift charts, and scatter plots.</span></span> <span data-ttu-id="5e540-120">Créez et gérez facilement des jeux d'apprentissage et de test.</span><span class="sxs-lookup"><span data-stu-id="5e540-120">Easily create and manage testing and training sets.</span></span>  
  
-   <span data-ttu-id="5e540-121">Interrogation et extraction : créez des requêtes de prédiction, récupérer les schémas et statistiques de modèles et explorez des données de cas.</span><span class="sxs-lookup"><span data-stu-id="5e540-121">Querying and drillthrough: Create prediction queries, retrieve model patterns and statistics, and drill through to case data.</span></span>  
  
-   <span data-ttu-id="5e540-122">Outils clients : outre les studios de développement et de conception fournis par SQL Server, vous pouvez utiliser les compléments d'exploration de données pour Excel afin de créer, interroger et parcourir des modèles.</span><span class="sxs-lookup"><span data-stu-id="5e540-122">Client tools: In addition to the development and design studios provided by SQL Server, you can use the Data Mining Add-ins for Excel to create, query, and browse models.</span></span> <span data-ttu-id="5e540-123">Vous pouvez également créer des clients personnalisés, notamment des services Web.</span><span class="sxs-lookup"><span data-stu-id="5e540-123">Or, create custom clients, including Web services.</span></span>  
  
-   <span data-ttu-id="5e540-124">Prise en charge du langage de script et des API managées : tous les objets d'exploration de données sont entièrement programmables.</span><span class="sxs-lookup"><span data-stu-id="5e540-124">Scripting language support and managed API: All data mining objects are fully programmable.</span></span> <span data-ttu-id="5e540-125">La création de scripts est possible grâce à MDX, XMLA ou aux extensions PowerShell pour [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e540-125">Scripting is possible through MDX, XMLA, or the PowerShell extensions for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="5e540-126">Utilisez le langage DMX (Data Mining Extensions) pour la création rapide de requêtes et de scripts.</span><span class="sxs-lookup"><span data-stu-id="5e540-126">Use the Data Mining Extensions (DMX) language for fast querying and scripting.</span></span>  
  
-   <span data-ttu-id="5e540-127">Sécurité et déploiement : fournit la sécurité basée sur les rôles via [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], notamment les autorisations distinctes pour l’extraction des données de structure et de modèle.</span><span class="sxs-lookup"><span data-stu-id="5e540-127">Security and deployment: Provides role-based security through [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], including separate permissions for drillthrough to model and structure data.</span></span> <span data-ttu-id="5e540-128">Déploiement simple des modèles vers d'autres serveurs, afin que les utilisateurs puissent accéder aux modèles ou effectuer des prédictions</span><span class="sxs-lookup"><span data-stu-id="5e540-128">Easy deployment of models to other servers, so that users can access the patterns or perform predictions</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e540-129">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5e540-129">In This Section</span></span>  
 <span data-ttu-id="5e540-130">Les rubriques de cette section présentent les principales fonctionnalités de l'exploration de données et des tâches associées de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5e540-130">The topics in this section introduce the principal features of SQL Server Data Mining and related tasks.</span></span>  
  
-   [<span data-ttu-id="5e540-131">Concepts d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="5e540-131">Data Mining Concepts</span></span>](data-mining-concepts.md)  
  
-   [<span data-ttu-id="5e540-132">Algorithmes d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="5e540-132">Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining-algorithms-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="5e540-133">Structures d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="5e540-133">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](mining-structures-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="5e540-134">Modèles d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="5e540-134">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-models-analysis-services-data-mining.md)  
  
-   [<span data-ttu-id="5e540-135">Test et validation &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="5e540-135">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)  
  
-   [<span data-ttu-id="5e540-136">Requêtes d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="5e540-136">Data Mining Queries</span></span>](data-mining-queries.md)  
  
-   [<span data-ttu-id="5e540-137">Solutions d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="5e540-137">Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
-   [<span data-ttu-id="5e540-138">Outils d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="5e540-138">Data Mining Tools</span></span>](data-mining-tools.md)  
  
-   [<span data-ttu-id="5e540-139">Architecture d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="5e540-139">Data Mining Architecture</span></span>](data-mining-architecture.md)  
  
-   [<span data-ttu-id="5e540-140">Vue d’ensemble de la sécurité &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="5e540-140">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
  
