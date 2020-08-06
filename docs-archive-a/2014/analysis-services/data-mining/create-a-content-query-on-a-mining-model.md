---
title: Créer une requête de contenu sur un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: a0ce837a-89ed-46cf-9ce1-801ccb75fa04
author: minewiskan
ms.author: owend
ms.openlocfilehash: 26af1100d6ba80185c1cc4de18548df0e387824c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694840"
---
# <a name="create-a-content-query-on-a-mining-model"></a><span data-ttu-id="6fbcc-102">Créer une requête de contenu sur un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="6fbcc-102">Create a Content Query on a Mining Model</span></span>
  <span data-ttu-id="6fbcc-103">Vous pouvez interroger par programme le contenu du modèle d'exploration de données en utilisant AMO ou XML/A, mais il est plus facile de créer des requêtes à l'aide de DMX.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-103">You can query the mining model content programmatically by using AMO or XML/A, but it is easier to create queries by using DMX.</span></span> <span data-ttu-id="6fbcc-104">Vous pouvez créer des requêtes sur les ensembles de lignes de schéma d'exploration de données en établissant une connexion à l'instance d' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et en créant une requête utilisant les vues DMV fournies par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fbcc-104">You can also create queries against the data mining schema rowsets by establishing a connection to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and creating a query using the DMVs provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6fbcc-105">Les procédures suivantes montrent comment créer des requêtes sur un modèle d'exploration de données en utilisant DMX, et comment interroger les ensembles de lignes de schéma d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-105">The following procedures demonstrate how to create queries against a mining model by using DMX, and how to query the data mining schema rowsets.</span></span>  
  
 <span data-ttu-id="6fbcc-106">Pour obtenir un exemple illustrant la façon de créer une requête similaire en utilisant XML/A, consultez [Créer une requête d’exploration de données en utilisant XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="6fbcc-106">For an example of how to create a similar query by using XML/A, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="querying-data-mining-model-content-by-using-dmx"></a><span data-ttu-id="6fbcc-107">Interrogation du contenu de modèle d'exploration de données en utilisant DMX</span><span class="sxs-lookup"><span data-stu-id="6fbcc-107">Querying Data Mining Model Content by Using DMX</span></span>  
  
#### <a name="to-create-a-dmx-model-content-query"></a><span data-ttu-id="6fbcc-108">Pour créer une requête de contenu de modèle DMX</span><span class="sxs-lookup"><span data-stu-id="6fbcc-108">To create a DMX model content query</span></span>  
  
1.  <span data-ttu-id="6fbcc-109">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], dans le menu **Affichage** , cliquez sur **Explorateur de modèles**.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="6fbcc-110">Dans le volet **Explorateur de modèles** , cliquez sur l'icône de cube pour modifier la liste et afficher les modèles Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-110">In the **Template Explorer** pane, click the cube icon to change the list and display Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="6fbcc-111">Dans la liste des catégories de modèles, développez **DMX**, développez **Contenu des modèles**et double-cliquez sur **Requête de contenu**.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-111">In the list of template categories, expand **DMX**, expand **Model Content**, and double-click **Content Query**.</span></span>  
  
4.  <span data-ttu-id="6fbcc-112">Dans la boîte de dialogue **Se connecter à Analysis Services** , sélectionnez l'instance qui contient le modèle d'exploration de données que vous voulez interroger et cliquez sur **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-112">In the **Connect to Analysis Services** dialog box, select the instance that contains the mining model you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="6fbcc-113">Le modèle **Requête de contenu** s'ouvre dans l'éditeur de code approprié.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-113">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="6fbcc-114">Le volet de métadonnées répertorie les modèles qui sont disponibles dans la base de données active.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-114">The metadata pane lists the models that are available in the current database.</span></span> <span data-ttu-id="6fbcc-115">Pour changer la base de données, sélectionnez une autre base de données dans la liste **Bases de données disponibles** .</span><span class="sxs-lookup"><span data-stu-id="6fbcc-115">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
5.  <span data-ttu-id="6fbcc-116">Entrez le nom d’un modèle d’exploration de données sur la ligne, `FROM` [ *\<mining model, name, MyModel>* ] `.CONTENT` .</span><span class="sxs-lookup"><span data-stu-id="6fbcc-116">Enter the name of a mining model in the line, `FROM` [*\<mining model, name, MyModel>*]`.CONTENT`.</span></span> <span data-ttu-id="6fbcc-117">Si le nom du modèle d'exploration de données contient des espaces, vous devez le mettre entre crochets.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-117">If the mining model name contains spaces, you must enclose the name in brackets.</span></span>  
  
     <span data-ttu-id="6fbcc-118">Si vous ne voulez pas taper le nom, vous pouvez sélectionner un modèle d'exploration de données dans l' **Explorateur d'objets** et le faire glisser dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-118">If you don't want to type the name, you can select a mining model in **Object Explorer** and drag it into the template.</span></span>  
  
6.  <span data-ttu-id="6fbcc-119">Dans la ligne, `SELECT` *\<select list, expr list, \*>* tapez les noms des colonnes dans l’ensemble de lignes de schéma du contenu du modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-119">In the line, `SELECT`*\<select list, expr list, \*>*, type the names of columns in the mining model content schema rowset.</span></span>  
  
     <span data-ttu-id="6fbcc-120">Pour afficher une liste des colonnes que vous pouvez retourner dans les requêtes de contenu de modèle d’exploration de données, consultez [Contenu du modèle d’exploration &#40;Analysis Services - Exploration de données&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="6fbcc-120">To view a list of columns that you can return in mining model content queries, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
7.  <span data-ttu-id="6fbcc-121">En option, tapez une condition dans la clause WHERE du modèle pour restreindre les lignes retournées à des nœuds ou des valeurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-121">Optionally, type a condition in the WHERE clause of the template to restrict the rows returned to specific nodes or values.</span></span>  
  
8.  <span data-ttu-id="6fbcc-122">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-122">Click **Execute**.</span></span>  
  
## <a name="querying-the-data-mining-schema-rowsets"></a><span data-ttu-id="6fbcc-123">Interrogation des ensembles de lignes de schéma d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="6fbcc-123">Querying the Data Mining Schema Rowsets</span></span>  
  
#### <a name="to-create-a-query-against-the-data-mining-schema-rowset"></a><span data-ttu-id="6fbcc-124">Pour créer une requête sur l'ensemble de lignes de schéma d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="6fbcc-124">To create a query against the data mining schema rowset</span></span>  
  
1.  <span data-ttu-id="6fbcc-125">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], dans la barre d'outils **Nouvelle requête** , cliquez sur **Requête DMX Analysis Services**ou sur **Requête MDX Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **New Query** toolbar, click **Analysis Services DMX Query**, or **Analysis Services MDX query**.</span></span>  
  
2.  <span data-ttu-id="6fbcc-126">Dans la boîte de dialogue **Se connecter à Analysis Services** , sélectionnez l'instance qui contient les objets que vous voulez interroger et cliquez sur **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-126">In the **Connect to Analysis Services** dialog box, select the instance that contains the objects you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="6fbcc-127">Le modèle **Requête de contenu** s'ouvre dans l'éditeur de code approprié.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-127">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="6fbcc-128">Le volet de métadonnées répertorie les objets qui sont disponibles dans la base de données active.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-128">The metadata pane lists the objects that are available in the current database.</span></span> <span data-ttu-id="6fbcc-129">Pour changer la base de données, sélectionnez une autre base de données dans la liste **Bases de données disponibles** .</span><span class="sxs-lookup"><span data-stu-id="6fbcc-129">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
3.  <span data-ttu-id="6fbcc-130">Dans l'éditeur de requête, tapez :</span><span class="sxs-lookup"><span data-stu-id="6fbcc-130">In the query editor, type the following:</span></span>  
  
     `SELECT *`  
  
     `FROM $system.DMSCHEMA_MINING_MODEL_CONTENT`  
  
     `WHERE MODEL_NAME = '<model name>'`  
  
4.  <span data-ttu-id="6fbcc-131">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="6fbcc-132">Le volet Résultats affiche le contenu du modèle.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-132">The Results pane displays the contents of the model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6fbcc-133">Pour afficher la liste de tous les ensembles de lignes de schéma que vous pouvez interroger sur l'instance active, utilisez cette requête : `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span><span class="sxs-lookup"><span data-stu-id="6fbcc-133">To view a list of all the schema rowsets that you can query on the current instance, use this query: `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span></span> <span data-ttu-id="6fbcc-134">Ou, pour obtenir la liste des ensembles de lignes de schéma spécifiques à l'exploration de données, consultez [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="6fbcc-134">Or, for a list of schema rowsets specific to data mining, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fbcc-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6fbcc-135">See Also</span></span>  
 <span data-ttu-id="6fbcc-136">[Contenu du modèle d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6fbcc-136">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="6fbcc-137">Data Mining Schema Rowsets</span><span class="sxs-lookup"><span data-stu-id="6fbcc-137">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
