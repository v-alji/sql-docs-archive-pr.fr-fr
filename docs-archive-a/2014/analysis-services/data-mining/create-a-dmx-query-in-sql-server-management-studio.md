---
title: Créer une requête DMX dans SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- templates [Analysis Services], queries
- SQL Server Management Studio [Analysis Services], DMX queries
- predictions [Analysis Services], DMX prediction queries
- predictions [DMX]
- prediction queries [DMX]
- queries [DMX], prediction queries
- mining models [Analysis Services], DMX
ms.assetid: 568ce40a-1f53-47eb-8c79-14347cdfde83
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20fc7a618f4977058203d8f35d235b543609dd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611412"
---
# <a name="create-a-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="ff02a-102">Créer une requête DMX dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ff02a-102">Create a DMX Query in SQL Server Management Studio</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ff02a-103">fournit un ensemble de fonctionnalités pour vous aider à créer des requêtes de prédiction, des requêtes de contenu et des requêtes de définition des données sur des modèles et des structures d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="ff02a-103">provides a set of features to help you create prediction queries, content queries, and data definition queries against mining models and mining structures.</span></span>  
  
-   <span data-ttu-id="ff02a-104">Le générateur de requêtes de prédiction graphique est disponible dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] et [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]pour simplifier le processus d’écriture des requêtes de prédiction et de mappage de jeux de données à un modèle.</span><span class="sxs-lookup"><span data-stu-id="ff02a-104">The graphical Prediction Query Builder is available in both [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], to simplify the process of writing prediction queries and mapping data sets to a model.</span></span>  
  
-   <span data-ttu-id="ff02a-105">Les modèles de requête fournis dans l'Explorateur de modèles accélèrent la création de plusieurs types de requêtes DMX, notamment plusieurs types de requêtes de prédiction.</span><span class="sxs-lookup"><span data-stu-id="ff02a-105">The query templates provided in the Template Explorer jump-start the creation of many kinds of DMX queries, including many types of prediction queries.</span></span> <span data-ttu-id="ff02a-106">Des modèles sont fournis pour les requêtes de contenu, les requêtes utilisées dans des jeux de données imbriqués, les requêtes qui retournent des cas de structure d'exploration de données et même des requêtes de définition de données.</span><span class="sxs-lookup"><span data-stu-id="ff02a-106">Templates are provided for content queries, queries used nested data sets, queries that return cases from the mining structure, and even data definition queries.</span></span>  
  
-   <span data-ttu-id="ff02a-107">L'explorateur de métadonnées des volets de requête MDX et DMX fournit une liste des modèles et des structures disponibles que vous pouvez faire glisser et déplacer dans le générateur de requêtes, ainsi qu'une liste des fonctions DMX.</span><span class="sxs-lookup"><span data-stu-id="ff02a-107">The Metadata Explorer in the MDX and DMX query panes provides a list of available models and structures that you can drag and drop into the query builder, as well as a list of DMX functions.</span></span> <span data-ttu-id="ff02a-108">Cette fonctionnalité simplifie l'obtention des noms corrects d'objets, sans saisie.</span><span class="sxs-lookup"><span data-stu-id="ff02a-108">This feature makes it easy to get object names right, without typing.</span></span>  
  
 <span data-ttu-id="ff02a-109">Cette rubrique décrit la génération d'une requête DMX à l'aide de l'explorateur de métadonnées et de l'éditeur de requête DMX.</span><span class="sxs-lookup"><span data-stu-id="ff02a-109">This topic describes how to build a DMX query by using the Metadata Explorer and the DMX query editor.</span></span>  
  
##  <a name="dmx-query-templates"></a><a name="BKMK_Templates"></a> <span data-ttu-id="ff02a-110">Modèles de requête DMX</span><span class="sxs-lookup"><span data-stu-id="ff02a-110">DMX Query Templates</span></span>  
 <span data-ttu-id="ff02a-111">Des modèles permettant de créer des requêtes DMX de base sont disponibles dans l'Explorateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="ff02a-111">Templates for creating basic DMX queries are available in Template Explorer.</span></span> <span data-ttu-id="ff02a-112">Le dossier **DMX** contient des modèles d’exploration de données, divisés en catégories comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff02a-112">The **DMX** folder contains data mining templates, which are divided into these categories:</span></span>  
  
-   <span data-ttu-id="ff02a-113">**Contenu du modèle**</span><span class="sxs-lookup"><span data-stu-id="ff02a-113">**Model Content**</span></span>  
  
-   <span data-ttu-id="ff02a-114">**Gestion des modèles**</span><span class="sxs-lookup"><span data-stu-id="ff02a-114">**Model Management**</span></span>  
  
-   <span data-ttu-id="ff02a-115">**Requêtes de prédiction**</span><span class="sxs-lookup"><span data-stu-id="ff02a-115">**Prediction Queries**</span></span>  
  
-   <span data-ttu-id="ff02a-116">**Structure de contenu**</span><span class="sxs-lookup"><span data-stu-id="ff02a-116">**Structure Content**</span></span>  
  
 <span data-ttu-id="ff02a-117">Vous pouvez également créer des modèles personnalisés, pour les requêtes ou les commandes que vous exécutez fréquemment.</span><span class="sxs-lookup"><span data-stu-id="ff02a-117">You can also create custom templates, for queries or commands that you run frequently.</span></span>  
  
## <a name="xmla-query-templates"></a><span data-ttu-id="ff02a-118">Modèles de requête XMLA</span><span class="sxs-lookup"><span data-stu-id="ff02a-118">XMLA Query Templates</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="ff02a-119">fournit également des modèles pour les requêtes XMLA.</span><span class="sxs-lookup"><span data-stu-id="ff02a-119">also provides templates for XMLA queries.</span></span>  
  
 <span data-ttu-id="ff02a-120">Les types de requêtes se chevauchent selon qu'ils sont effectués à l'aide de XMLA ou DMX.</span><span class="sxs-lookup"><span data-stu-id="ff02a-120">There is some overlap between the types of queries that you can perform by using XMLA and DMX.</span></span> <span data-ttu-id="ff02a-121">Par exemple, vous pouvez créer des requêtes de contenu de modèle à l'aide de DMX ou des ensembles de lignes de schéma d'exploration de données, mais les ensembles de lignes de schéma contiennent parfois des informations qui ne sont pas exposés dans les requêtes de contenu DMX.</span><span class="sxs-lookup"><span data-stu-id="ff02a-121">For example, you can create some model content queries by using either DMX or the data mining schema rowsets, but the schema rowsets sometimes contain information that is not exposed in DMX content queries.</span></span>  
  
 <span data-ttu-id="ff02a-122">Il existe également des différences essentielles dans la façon dont les opérations sont gérées dans DMX et dans XMLA.</span><span class="sxs-lookup"><span data-stu-id="ff02a-122">There are also some key differences in the way that operations are handled in DMX and in XMLA.</span></span> <span data-ttu-id="ff02a-123">Par exemple, vous pouvez utiliser XMLA pour effectuer des opérations administratives telles que la sauvegarde d’une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] entière, mais si vous souhaitez sauvegarder un modèle d’exploration de données unique, DMX fournit une commande simple, [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx), mieux adaptée à cette fin.</span><span class="sxs-lookup"><span data-stu-id="ff02a-123">For example, you can use XMLA to perform administrative operations such as backup of an entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, but if you want to back up a single mining model, DMX provides a simple command, [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx), that is better suited to that purpose.</span></span>  
  
##  <a name="build-and-run-a-dmx-query"></a><a name="BKMK_Building_Queries"></a> <span data-ttu-id="ff02a-124">Générer et exécuter une requête DMX.</span><span class="sxs-lookup"><span data-stu-id="ff02a-124">Build and Run a DMX Query</span></span>  
  
#### <a name="open-a-new-dmx-query-window"></a><span data-ttu-id="ff02a-125">Ouvrir une fenêtre de nouvelle requête DMX.</span><span class="sxs-lookup"><span data-stu-id="ff02a-125">Open a new DMX Query window</span></span>  
  
1.  <span data-ttu-id="ff02a-126">Cliquez sur **Nouvelle requête** dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], puis sélectionnez **Nouvelle requête DMX Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="ff02a-126">Click **New Query** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then select **New Analysis Server DMX Query**.</span></span>  
  
2.  <span data-ttu-id="ff02a-127">Lorsque la boîte de dialogue **Se connecter au serveur** s’affiche, sélectionnez l’instance d’ [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui contient les modèles d’exploration de données que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="ff02a-127">When the **Connect to Server** dialog box appears, select the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining models you want to work with.</span></span>  
  
#### <a name="open-template-explorer"></a><span data-ttu-id="ff02a-128">Ouvrir l'Explorateur de modèles</span><span class="sxs-lookup"><span data-stu-id="ff02a-128">Open Template Explorer</span></span>  
  
1.  <span data-ttu-id="ff02a-129">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], dans le menu **Affichage** , sélectionnez **Explorateur de modèles**.</span><span class="sxs-lookup"><span data-stu-id="ff02a-129">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, select **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="ff02a-130">Cliquez sur **Serveur d’analyse** pour afficher une arborescence des modèles qui s’appliquent à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff02a-130">Click **Analysis Server** to see a tree view of the templates that apply to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
#### <a name="apply-a-template-to-build-a-query"></a><span data-ttu-id="ff02a-131">Appliquez un modèle pour générer une requête</span><span class="sxs-lookup"><span data-stu-id="ff02a-131">Apply a template to build a query</span></span>  
  
-   <span data-ttu-id="ff02a-132">Cliquez avec le bouton droit sur le type de requête approprié et sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="ff02a-132">Right-click the appropriate query type and select **Open**.</span></span>  
  
-   <span data-ttu-id="ff02a-133">Ou, faites glisser le modèle dans l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="ff02a-133">Or, drag the template into the query editor.</span></span>  
  
-   <span data-ttu-id="ff02a-134">Vous pouvez également remplir les paramètres de la requête à l’aide de l’option **Spécifier les valeurs pour les paramètres**du menu **Requête** .</span><span class="sxs-lookup"><span data-stu-id="ff02a-134">You can also fill in the parameters for the query by using the option, **Specify Values for Parameters**, from the **Query** menu.</span></span>  
  
 <span data-ttu-id="ff02a-135">Pour obtenir des exemples de création de types spécifiques de requêtes à partir de modèles, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff02a-135">For examples of how to create specific types of queries from templates, see the following topics:</span></span>  
  
 [<span data-ttu-id="ff02a-136">Créer une requête singleton de prédiction à partir d'un modèle</span><span class="sxs-lookup"><span data-stu-id="ff02a-136">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
  
 [<span data-ttu-id="ff02a-137">Créer une requête de contenu sur un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="ff02a-137">Create a Content Query on a Mining Model</span></span>](create-a-content-query-on-a-mining-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff02a-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff02a-138">See Also</span></span>  
 <span data-ttu-id="ff02a-139">[Interfaces de requête d’exploration de données](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ff02a-139">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="ff02a-140">Référence DMX &#40;Data Mining Extensions&#41;</span><span class="sxs-lookup"><span data-stu-id="ff02a-140">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
