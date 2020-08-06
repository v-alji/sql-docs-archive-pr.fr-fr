---
title: Créer une requête d’exploration de données à l’aide de XMLA | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: 8f6b6008-006c-4792-9bd1-64c30dc3fd41
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0e85b17db0781671fab0874706f12fdac95b30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613704"
---
# <a name="create-a-data-mining-query-by-using-xmla"></a><span data-ttu-id="6456c-102">Créer une requête d’exploration de données en utilisant XMLA</span><span class="sxs-lookup"><span data-stu-id="6456c-102">Create a Data Mining Query by Using XMLA</span></span>
  <span data-ttu-id="6456c-103">Vous pouvez créer diverses requêtes sur les objets d'exploration de données en utilisant AMO, DMX ou XML/A.</span><span class="sxs-lookup"><span data-stu-id="6456c-103">You can create a variety of queries against data mining objects by using AMO, DMX, or XML/A.</span></span>  
  
 <span data-ttu-id="6456c-104">XML est utilisé pour les communications entre le serveur Analysis Services et tous les clients.</span><span class="sxs-lookup"><span data-stu-id="6456c-104">XML is used for communication between the Analysis Services server and all clients.</span></span> <span data-ttu-id="6456c-105">Par conséquent, bien qu'il soit en général beaucoup plus facile de créer des requêtes de contenu à l'aide de DMX, vous pouvez écrire des requêtes à l'aide des instructions DISCOVER et COMMAND en XML/A, en utilisant un client qui prend en charge le protocole SOAP ou en créant une requête XML/A dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6456c-105">Therefore, although it is generally much easier to create content queries by using DMX, you can write queries by using the DISCOVER and COMMAND statements in XML/A, either by using a client that supports the SOAP protocol, or by creating an XML/A query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6456c-106">Cette rubrique explique comment utiliser les modèles XML/A qui sont disponibles dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour créer une requête de contenu du modèle sur un modèle d’exploration de données stocké sur le serveur actuel.</span><span class="sxs-lookup"><span data-stu-id="6456c-106">This topic explains how to use the XML/A templates that are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a model content query against a mining model stored on the current server.</span></span>  
  
## <a name="querying-data-mining-schema-rowsets-by-using-xmla"></a><span data-ttu-id="6456c-107">Interrogation des ensembles de lignes de schéma d'exploration de données à l'aide de XML/A</span><span class="sxs-lookup"><span data-stu-id="6456c-107">Querying Data Mining Schema Rowsets by Using XML/A</span></span>  
  
#### <a name="to-open-an-xmla-template"></a><span data-ttu-id="6456c-108">Pour ouvrir un modèle XML/A</span><span class="sxs-lookup"><span data-stu-id="6456c-108">To open an XML/A template</span></span>  
  
1.  <span data-ttu-id="6456c-109">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], dans le menu **Affichage** , cliquez sur **Explorateur de modèles**.</span><span class="sxs-lookup"><span data-stu-id="6456c-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="6456c-110">Cliquez sur l'icône du cube pour ouvrir la liste des modèles d'Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="6456c-110">Click the cube icon to open the list of Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="6456c-111">Dans la liste des catégories de modèles, développez **XMLA**, développez **Ensembles de lignes de schéma**, puis double-cliquez sur **Découvrir les ensembles de lignes du schéma** pour ouvrir le modèle dans l’éditeur de code approprié.</span><span class="sxs-lookup"><span data-stu-id="6456c-111">In the list of template categories, expand **XMLA**, expand **Schema Rowsets**, and double-click **Discover Schema Rowsets** to open the template in the appropriate code editor.</span></span>  
  
4.  <span data-ttu-id="6456c-112">Dans la boîte de dialogue **Se connecter à Analysis Services** , fournissez les informations de connexion, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="6456c-112">In the **Connect to Analysis Services** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="6456c-113">Une nouvelle fenêtre de l'éditeur de requête s'affiche avec le modèle **Découvrir les ensembles de lignes du schéma** .</span><span class="sxs-lookup"><span data-stu-id="6456c-113">A new query editor window opens, populated with the **Discover Schema Rowsets** template.</span></span>  
  
#### <a name="to-discover-column-names-from-the-mining-model-content-schema-rowset"></a><span data-ttu-id="6456c-114">Pour découvrir les noms des colonnes à partir de l'ensemble de lignes de schéma MINING MODEL CONTENT</span><span class="sxs-lookup"><span data-stu-id="6456c-114">To discover column names from the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="6456c-115">Avec le modèle **Découvrir les ensembles de lignes du schéma** ouvert, cliquez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6456c-115">With the **Discover Schema Rowsets** template open, click **Execute**.</span></span>  
  
     <span data-ttu-id="6456c-116">Une liste d'ensembles de lignes de schéma est retournée dans le volet **Résultats** qui contient les noms et les colonnes des ensembles de lignes disponibles sur l'instance actuelle.</span><span class="sxs-lookup"><span data-stu-id="6456c-116">A list of schema rowsets is returned in the **Results** pane that contains the rowset names and rowset columns for all rowsets available on the current instance.</span></span>  
  
2.  <span data-ttu-id="6456c-117">Dans le volet **requête** , placez le curseur après **\<Restriction List>** et appuyez sur entrée pour ajouter une nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="6456c-117">In the **Query** pane, place the cursor after **\<Restriction List>** and press ENTER to add a new line.</span></span>  
  
3.  <span data-ttu-id="6456c-118">Placez le curseur sur la ligne vide et tapez \*\* \<SchemaName> DMSCHEMA_MINING_MODEL_CONTENT \</SchemaName> \*\*</span><span class="sxs-lookup"><span data-stu-id="6456c-118">Place the cursor on the blank line and type **\<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT\</SchemaName>**</span></span>  
  
     <span data-ttu-id="6456c-119">La section complète relative aux restrictions doit s'afficher comme suit :</span><span class="sxs-lookup"><span data-stu-id="6456c-119">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT</SchemaName>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
4.  <span data-ttu-id="6456c-120">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6456c-120">Click **Execute**.</span></span>  
  
     <span data-ttu-id="6456c-121">Le volet **Résultats** affiche une liste de noms de colonnes pour l'ensemble de lignes de schéma spécifié.</span><span class="sxs-lookup"><span data-stu-id="6456c-121">The **Results** pane shows a list of column names for the specified schema rowset.</span></span>  
  
#### <a name="to-create-a-content-query-using-the-mining-model-content-schema-rowset"></a><span data-ttu-id="6456c-122">Pour créer une requête de contenu à partir de l'ensemble de lignes de schéma MINING MODEL CONTENT</span><span class="sxs-lookup"><span data-stu-id="6456c-122">To create a content query using the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="6456c-123">Dans le modèle **Découvrir les ensembles de lignes du schéma** , modifiez le type de requête en remplaçant le texte à l'intérieur des balises de type de requête.</span><span class="sxs-lookup"><span data-stu-id="6456c-123">In the **Discover Schema Rowsets** template, change the request type by replacing the text inside the request type tags.</span></span>  
  
     <span data-ttu-id="6456c-124">Remplacez cette ligne :</span><span class="sxs-lookup"><span data-stu-id="6456c-124">Replace this line:</span></span>  
  
     `<RequestType>DISCOVER_SCHEMA_ROWSETS</RequestType>`  
  
     <span data-ttu-id="6456c-125">par la ligne suivante :</span><span class="sxs-lookup"><span data-stu-id="6456c-125">with the following line:</span></span>  
  
     <span data-ttu-id="6456c-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span><span class="sxs-lookup"><span data-stu-id="6456c-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span></span>  
  
2.  <span data-ttu-id="6456c-127">Modifiez la liste de restriction pour spécifier un modèle d'exploration de données par nom, en ajoutant une nouvelle condition aux listes de restriction.</span><span class="sxs-lookup"><span data-stu-id="6456c-127">Change the restriction list to specify a mining model by name, by adding a new condition to the restriction lists.</span></span>  
  
3.  <span data-ttu-id="6456c-128">Dans le modèle, placez le curseur après `<Restriction List>` et appuyez sur Entrée pour ajouter une nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="6456c-128">In the template, place the cursor after `<Restriction List>` and press ENTER to add a new line.</span></span>  
  
4.  <span data-ttu-id="6456c-129">Placez le curseur sur la ligne vide et tapez **<MODEL_NAME>Mon nom de modèle</MODEL_NAME>**</span><span class="sxs-lookup"><span data-stu-id="6456c-129">Place the cursor on the blank line and type **<MODEL_NAME>My model name</MODEL_NAME>**</span></span>  
  
     <span data-ttu-id="6456c-130">La section complète relative aux restrictions doit s'afficher comme suit :</span><span class="sxs-lookup"><span data-stu-id="6456c-130">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<MODEL_NAME>My model name</MODEL_NAME>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
5.  <span data-ttu-id="6456c-131">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6456c-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="6456c-132">Le volet Résultats affiche la définition de schéma ainsi que les valeurs du modèle spécifié.</span><span class="sxs-lookup"><span data-stu-id="6456c-132">The Results pane displays the schema definition, together with the values for the specified model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6456c-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6456c-133">See Also</span></span>  
 <span data-ttu-id="6456c-134">[Contenu du modèle d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6456c-134">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="6456c-135">Data Mining Schema Rowsets</span><span class="sxs-lookup"><span data-stu-id="6456c-135">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
