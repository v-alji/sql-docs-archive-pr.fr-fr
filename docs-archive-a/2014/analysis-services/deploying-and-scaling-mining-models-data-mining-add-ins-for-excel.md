---
title: Déploiement et mise à l’échelle des modèles d’exploration de données (compléments d’exploration de données pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- manage
ms.assetid: 4c617375-6b01-4a71-9680-de0cbf2cff05
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd2839144d4d1667da09830aaabd1ec3f17a9c21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612004"
---
# <a name="deploying-and-scaling-mining-models-data-mining-add-ins-for-excel"></a><span data-ttu-id="2605c-102">Déploiement et mise à l'échelle des modèles d'exploration de données (Compléments d'exploration de données pour Excel)</span><span class="sxs-lookup"><span data-stu-id="2605c-102">Deploying and Scaling Mining Models (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="2605c-103">Les outils du groupe **utilisation du modèle** et **gestion** sont fournis pour vous aider à gérer et à parcourir les modèles d’exploration de données existants.</span><span class="sxs-lookup"><span data-stu-id="2605c-103">The tools in the **Model Usage** and **Management** group are provided to help you manage and browse existing mining models.</span></span> <span data-ttu-id="2605c-104">Utilisez ces outils pour afficher tous les modèles stockés sur une instance d'[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], et non pas uniquement ceux créés avec les compléments.</span><span class="sxs-lookup"><span data-stu-id="2605c-104">You can use these tools to view any models that are stored on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], not just those created using the add-ins.</span></span>  
  
 <span data-ttu-id="2605c-105">Si vous disposez des autorisations nécessaires, vous pouvez supprimer, modifier, renommer ou traiter des modèles et des structures d'exploration de données existants sans quitter Excel.</span><span class="sxs-lookup"><span data-stu-id="2605c-105">If you have the necessary permissions, you can delete, modify, rename, or process existing mining models and structures without leaving Excel.</span></span>  
  
## <a name="model-usage-toolbar"></a><span data-ttu-id="2605c-106">Barre d'outils Utilisation du modèle</span><span class="sxs-lookup"><span data-stu-id="2605c-106">Model Usage Toolbar</span></span>  
  
### <a name="browse"></a><span data-ttu-id="2605c-107">Parcourir</span><span class="sxs-lookup"><span data-stu-id="2605c-107">Browse</span></span>  
 <span data-ttu-id="2605c-108">Utilisez l’Assistant **Parcourir** pour sélectionner un modèle d’exploration de données existant, puis affichez et explorez le modèle dans une visionneuse qui contient plusieurs graphiques et outils.</span><span class="sxs-lookup"><span data-stu-id="2605c-108">Use the **Browse** wizard to select an existing data mining model, and then view and explore the model in a viewer that contains multiple graphs and tools.</span></span>  
  
 <span data-ttu-id="2605c-109">Pour plus d’informations, consultez [navigation dans les modèles dans Excel &#40;SQL Server les compléments d’exploration de données&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="2605c-109">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="document-model"></a><span data-ttu-id="2605c-110">Modèle de document</span><span class="sxs-lookup"><span data-stu-id="2605c-110">Document Model</span></span>  
 <span data-ttu-id="2605c-111">Cliquez sur **modèle de document** pour démarrer un assistant qui crée un rapport des structures d’exploration de données et des modèles d’exploration de données que vous avez créés.</span><span class="sxs-lookup"><span data-stu-id="2605c-111">Click **Document Model** to start a wizard that creates a report of the mining structures and mining models that you have created.</span></span> <span data-ttu-id="2605c-112">Créez des rapports de base ou avancés.</span><span class="sxs-lookup"><span data-stu-id="2605c-112">You can create basic or advanced reports.</span></span> <span data-ttu-id="2605c-113">Les rapports contiennent des métadonnées de colonne et de modèle, et sont utiles pour documenter votre travail et le suivi des modifications dans les modèles.</span><span class="sxs-lookup"><span data-stu-id="2605c-113">The reports include column and model metadata, so are useful for documenting your work and tracking changes in models.</span></span>  
  
 <span data-ttu-id="2605c-114">Pour plus d’informations, consultez [documentation des modèles d’exploration de données &#40;compléments d’exploration de données pour Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="2605c-114">For more information, see [Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span></span>  
  
### <a name="query"></a><span data-ttu-id="2605c-115">Query</span><span class="sxs-lookup"><span data-stu-id="2605c-115">Query</span></span>  
 <span data-ttu-id="2605c-116">Cliquez sur **requête** pour démarrer l’Assistant **requête** .</span><span class="sxs-lookup"><span data-stu-id="2605c-116">Click **Query** to start the **Query** wizard.</span></span> <span data-ttu-id="2605c-117">Cet Assistant vous guide de manière interactive au cours de la création d'une requête de prédiction relative au modèle d'exploration de données existant.</span><span class="sxs-lookup"><span data-stu-id="2605c-117">The wizard interactively walks you through the process of creating a prediction query against an existing data mining model.</span></span>  
  
 <span data-ttu-id="2605c-118">Pour personnaliser davantage la requête ou créer des requêtes qui ne sont pas incluses dans l’Assistant, cliquez simplement sur le bouton **avancé** pour démarrer la **requête d’exploration de données éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="2605c-118">To further customize the query, or build queries not included in the wizard, just click the **Advanced** button to start the **Data Mining Query Advanced Editor**.</span></span>  
  
 <span data-ttu-id="2605c-119">Pour plus d’informations, consultez [&#40;des compléments d’exploration de données SQL Server&#41;](query-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="2605c-119">For more information, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="data-mining-advanced-query-editor"></a><span data-ttu-id="2605c-120">Éditeur de requêtes avancé d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="2605c-120">Data Mining Advanced Query Editor</span></span>  
 <span data-ttu-id="2605c-121">Cet éditeur vous permet d'utiliser des modèles DMX (Data Mining Extensions) pour accélérer une requête, puis de modifier les entrées, les sorties, les algorithmes et les paramètres pour créer un modèle d'exploration de données, une structure d'exploration de données ou une requête de prédiction personnalisés.</span><span class="sxs-lookup"><span data-stu-id="2605c-121">In this editor, you can use Data Mining Extensions (DMX) templates to jumpstart a query, and then modify the inputs, outputs, algorithms, and parameters to create a custom mining model, mining structure, or prediction query.</span></span>  
  
 <span data-ttu-id="2605c-122">Pour plus d’informations, consultez [éditeur de requêtes d’exploration de données avancé](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="2605c-122">For more information, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="management"></a><span data-ttu-id="2605c-123">Gestion</span><span class="sxs-lookup"><span data-stu-id="2605c-123">Management</span></span>  
 <span data-ttu-id="2605c-124">Utilisez l’Assistant **gérer les modèles** pour afficher les modèles existants sur la connexion actuelle.</span><span class="sxs-lookup"><span data-stu-id="2605c-124">Use the **Manage Models** wizard to view existing models on the current connection.</span></span> <span data-ttu-id="2605c-125">Vous pouvez également supprimer, renommer, traiter ou importer et exporter des structures et des modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="2605c-125">You can also delete, rename, process, or import and export mining models and structures.</span></span>  
  
 <span data-ttu-id="2605c-126">Pour plus d’informations, consultez [gérer les modèles &#40;SQL Server des compléments d’exploration de données&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="2605c-126">For more information, see [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2605c-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2605c-127">See Also</span></span>  
 <span data-ttu-id="2605c-128">[Création d’un modèle d’exploration de données](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="2605c-128">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="2605c-129">Validation des modèles et utilisation de modèles pour la prédiction &#40;compléments d’exploration de données pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="2605c-129">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
