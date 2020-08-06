---
title: Tâches de requête d’exploration de données et procédures | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], how-to topics
ms.assetid: 1bc2a775-6e62-4c66-a53c-201f2ea66295
author: minewiskan
ms.author: owend
ms.openlocfilehash: 454a3af33d0c18232bb36771235b328a17da6b86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614266"
---
# <a name="data-mining-query-tasks-and-how-tos"></a><span data-ttu-id="65892-102">Tâches de requête d’exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="65892-102">Data Mining Query Tasks and How-tos</span></span>
  <span data-ttu-id="65892-103">La capacité de créer des requêtes est essentielle si vous devez utiliser vos modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="65892-103">The ability to create queries is critical if you are to make use of your data mining models.</span></span> <span data-ttu-id="65892-104">Cette section fournit des liens vers des exemples de création de requêtes sur un modèle d’exploration de données à l’aide des outils fournis dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)][!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65892-104">This section provides links to examples of how to create queries against a data mining model by using the tools provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="65892-105">Pour plus d’informations sur ce qu’est une requête d’exploration de donnée, ou sur les différents types de requêtes que vous pouvez créer, consultez [Requêtes d’exploration de données](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="65892-105">If you need more information about what a data mining query is, or the different types of queries you can create, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
## <a name="creating-queries-with-prediction-query-builder"></a><span data-ttu-id="65892-106">Création de requêtes avec le Générateur de requêtes de prédiction</span><span class="sxs-lookup"><span data-stu-id="65892-106">Creating Queries with Prediction Query Builder</span></span>  
 <span data-ttu-id="65892-107">Le Générateur de requêtes de prédiction est fourni dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)][!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] comme un moyen de générer graphiquement des requêtes sur des modèles d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="65892-107">The Prediction Query Builder is provided in both [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] as a way of graphically building queries against data mining models.</span></span> <span data-ttu-id="65892-108">Les rubriques suivantes expliquent comment sélectionner un modèle, spécifier une source de données, personnaliser les prédictions et enregistrer la sortie.</span><span class="sxs-lookup"><span data-stu-id="65892-108">The following topics explain how you can select a model, specify a data source, customize the predictions, and save output.</span></span>  
  
-   [<span data-ttu-id="65892-109">Créer une requête de prédiction à l’aide du Générateur de requêtes de prédiction</span><span class="sxs-lookup"><span data-stu-id="65892-109">Create a Prediction Query Using the Prediction Query Builder</span></span>](create-a-prediction-query-using-the-prediction-query-builder.md)  
  
-   [<span data-ttu-id="65892-110">créer une requête singleton dans le Concepteur d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="65892-110">Create a Singleton Query in the Data Mining Designer</span></span>](create-a-singleton-query-in-the-data-mining-designer.md)  
  
-   [<span data-ttu-id="65892-111">Créer une requête de prédiction à l’aide du Générateur de requêtes de prédiction</span><span class="sxs-lookup"><span data-stu-id="65892-111">Create a Prediction Query Using the Prediction Query Builder</span></span>](create-a-prediction-query-using-the-prediction-query-builder.md)  
  
-   [<span data-ttu-id="65892-112">Afficher et enregistrer les résultats d'une requête de prédiction</span><span class="sxs-lookup"><span data-stu-id="65892-112">View and Save the Results of a Prediction Query</span></span>](view-and-save-the-results-of-a-prediction-query.md)  
  
-   [<span data-ttu-id="65892-113">Modifier manuellement une requête de prédiction</span><span class="sxs-lookup"><span data-stu-id="65892-113">Manually Edit a Prediction Query</span></span>](manually-edit-a-prediction-query.md)  
  
-   [<span data-ttu-id="65892-114">Appliquer des fonctions de prédiction à un modèle</span><span class="sxs-lookup"><span data-stu-id="65892-114">Apply Prediction Functions to a Model</span></span>](apply-prediction-functions-to-a-model.md)  
  
-   [<span data-ttu-id="65892-115">Choisir et mapper les données d'entrée pour une requête de prédiction</span><span class="sxs-lookup"><span data-stu-id="65892-115">Choose and Map Input Data for a Prediction Query</span></span>](choose-and-map-input-data-for-a-prediction-query.md)  
  
## <a name="using-other-data-mining-query-tools"></a><span data-ttu-id="65892-116">Utilisation d'autres outils de requête d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="65892-116">Using Other Data Mining Query Tools</span></span>  
 <span data-ttu-id="65892-117">En plus d’utiliser le Générateur de requêtes de prédiction, vous pouvez taper une requête directement dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] avec DMX ou XMLA.</span><span class="sxs-lookup"><span data-stu-id="65892-117">In addition to using the Prediction Query Builder, you can type a query directly into [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using DMX or by using XMLA.</span></span> <span data-ttu-id="65892-118">Vous pouvez également générer des requêtes de prédiction par programmation et les envoyer à un serveur [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65892-118">You can also build prediction queries programmatically and send them to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server.</span></span> <span data-ttu-id="65892-119">Les rubriques suivantes fournissent des informations sur la création et l'utilisation des requêtes de prédiction en dehors du générateur de requêtes de prédiction.</span><span class="sxs-lookup"><span data-stu-id="65892-119">The following topics provide more information about how to create and work with prediction queries outside of the Prediction Query Builder.</span></span>  
  
 [<span data-ttu-id="65892-120">Créer une requête singleton de prédiction à partir d'un modèle</span><span class="sxs-lookup"><span data-stu-id="65892-120">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
 <span data-ttu-id="65892-121">Décrit comment utiliser les outils fournis dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour créer et exécuter une requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="65892-121">Describes how to use the tools in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to build and run a prediction query.</span></span>  
  
 [<span data-ttu-id="65892-122">Créer une requête singleton de prédiction à partir d'un modèle</span><span class="sxs-lookup"><span data-stu-id="65892-122">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
 <span data-ttu-id="65892-123">Décrit comment utiliser les modèles fournis dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour ajouter des paramètres à une requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="65892-123">Describes how to use the templates that are provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to add parameters to a prediction query.</span></span>  
  
 [<span data-ttu-id="65892-124">Modifier la valeur du délai d'attente pour les requêtes d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="65892-124">Change the Time-out Value for Data Mining Queries</span></span>](change-the-time-out-value-for-data-mining-queries.md)  
 <span data-ttu-id="65892-125">Décrit comment définir des propriétés sur le serveur qui contrôlent le comportement lié aux requêtes d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="65892-125">Describes how to set properties on the server that control behavior related to data mining queries.</span></span>  
  
 [<span data-ttu-id="65892-126">Créer une requête de contenu sur un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="65892-126">Create a Content Query on a Mining Model</span></span>](create-a-content-query-on-a-mining-model.md)  
 <span data-ttu-id="65892-127">Décrit comment créer des requêtes qui retournent des informations détaillées stockées dans le modèle d'exploration de données à l'aide des ensembles de lignes de schéma d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="65892-127">Describes how to create queries that return detailed information that is stored in the mining model by using the data mining schema rowsets.</span></span>  
  
 [<span data-ttu-id="65892-128">Créer une requête d’exploration de données en utilisant XMLA</span><span class="sxs-lookup"><span data-stu-id="65892-128">Create a Data Mining Query by Using XMLA</span></span>](create-a-data-mining-query-by-using-xmla.md)  
 <span data-ttu-id="65892-129">Décrit comment créer une requête sur le contenu d'un modèle d'exploration de données en utilisant les modèles XMLA dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65892-129">Describes how to create a query against mining model content by using the XMLA templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65892-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65892-130">See Also</span></span>  
 <span data-ttu-id="65892-131">[Référence du langage des requêtes et expressions &#40;Analysis Services&#41;](https://msdn.microsoft.com/library/gg492188(SQL.130).aspx) </span><span class="sxs-lookup"><span data-stu-id="65892-131">[Query and Expression Language Reference &#40;Analysis Services&#41;](https://msdn.microsoft.com/library/gg492188(SQL.130).aspx) </span></span>  
 [<span data-ttu-id="65892-132">Procédures stockées d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="65892-132">Data Mining Stored Procedures &#40;Analysis Services - Data Mining&#41;</span></span>](/sql/analysis-services/data-mining/data-mining-stored-procedures-analysis-services-data-mining)  
  
  
