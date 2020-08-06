---
title: Requête (SQL Server les compléments d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- queries [data mining]
- Data Mining Query Advanced Editor
- query builder [data mining]
- DMX
ms.assetid: 16af4a6f-18d4-496a-a304-7a13aa32ee76
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90794aae8a3d664d47ab251ffdd954f22d48f992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706856"
---
# <a name="query-sql-server-data-mining-add-ins"></a><span data-ttu-id="e815d-102">Requête (Compléments d'exploration de données SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e815d-102">Query (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="e815d-103">![Bouton Modèle de requête, ruban Exploration de données](media/dmc-query.gif "Bouton Modèle de requête, ruban Exploration de données")</span><span class="sxs-lookup"><span data-stu-id="e815d-103">![Query Model button, Data Mining ribbon](media/dmc-query.gif "Query Model button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="e815d-104">L'Assistant **Requête** vous permet d'interagir avec les modèles d'exploration de données existants pour établir des prédictions en fonction des données d'un tableau Excel, d'une plage Excel ou d'une autre source de données.</span><span class="sxs-lookup"><span data-stu-id="e815d-104">The **Query** wizard helps you interact with existing mining models to make predictions based on data in an Excel table, an Excel range, or another data source.</span></span> <span data-ttu-id="e815d-105">Le processus consistant à appliquer de nouvelles données à un modèle existant pour prévoir des tendances est appelé *requête de prédiction*.</span><span class="sxs-lookup"><span data-stu-id="e815d-105">The process of applying new data to an existing model to predict trends is called a *prediction query*.</span></span>  
  
 <span data-ttu-id="e815d-106">L'Assistant **Requête** propose également un éditeur avancé pour créer ou modifier des modèles d'exploration de données, pour générer des requêtes personnalisées ou pour utiliser des structures qui ne sont pas prises en charge dans les autres outils, tels que des datasets imbriqués.</span><span class="sxs-lookup"><span data-stu-id="e815d-106">The **Query** wizard also provides an advanced editor for creating or modifying data mining models, for generating custom queries, or for working with structures not supported in the other tools, such as nested datasets.</span></span>  
  
-   <span data-ttu-id="e815d-107">Utilisez l’éditeur de texte pour taper ou coller des instructions DMX (Data Mining Extensions) que vous avez créées ailleurs.</span><span class="sxs-lookup"><span data-stu-id="e815d-107">Use the text editor to type or paste in the Data Mining Extensions (DMX) statements you've created elsewhere.</span></span>  
  
-   <span data-ttu-id="e815d-108">Utilisez le générateur de requêtes interactif pour composer une instruction DMX personnalisée à l'aide de modèles et de boîtes de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e815d-108">Use the interactive Query Builder to compose a custom DMX statement with the help of templates and dialog boxes.</span></span>  
  
-   <span data-ttu-id="e815d-109">Créez des instructions DMX pour gérer ou sauvegarder des structures et des modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="e815d-109">Create DMX statements to manage or back up mining models and structures.</span></span>  
  
## <a name="using-the-query-wizard"></a><span data-ttu-id="e815d-110">Utilisation de l'Assistant Requête</span><span class="sxs-lookup"><span data-stu-id="e815d-110">Using the Query Wizard</span></span>  
  
1.  <span data-ttu-id="e815d-111">Tout d'abord, vous devez spécifier une source pour les données à utiliser comme entrée.</span><span class="sxs-lookup"><span data-stu-id="e815d-111">First, you must specify a source for the data to use as input.</span></span> <span data-ttu-id="e815d-112">Vous pouvez utiliser les données d'une plage ou d'un tableau Excel existant, ou vous pouvez spécifier une instruction SQL pour extraire les données.</span><span class="sxs-lookup"><span data-stu-id="e815d-112">You can use data in an existing Excel table or range, or you can specify a SQL statement to retrieve the data.</span></span>  
  
2.  <span data-ttu-id="e815d-113">Ensuite, l'Assistant présente la liste des modèles d'exploration de données disponibles sur le serveur auquel vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="e815d-113">Next, the wizard presents a list of data mining models on the server to which you are connected.</span></span> <span data-ttu-id="e815d-114">Si vous savez quel modèle utiliser et que vous maîtrisez l'exploration de données, vous pouvez également cliquer sur **Avancé** pour ouvrir l' **Éditeur de requêtes avancé d'exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="e815d-114">If you know the model you want and are familiar with data mining, you can also click **Advanced** to open the **Data Mining Advanced Query Editor**.</span></span>  
  
3.  <span data-ttu-id="e815d-115">En fonction du type de modèle que vous choisissez, vous devez spécifier la colonne qui contient les données à évaluer et définir des mappages entre les colonnes des données d'entrée et les colonnes du modèle.</span><span class="sxs-lookup"><span data-stu-id="e815d-115">Depending on the type of model that you choose, you must specify the column that contains the data to be evaluated, and define mappings between the input data columns and the model columns.</span></span> <span data-ttu-id="e815d-116">En fonction de l'algorithme choisi, vous pouvez définir d'autres propriétés du modèle.</span><span class="sxs-lookup"><span data-stu-id="e815d-116">Depending on the algorithm you choose, you can set other properties on the model.</span></span>  
  
4.  <span data-ttu-id="e815d-117">En dernier lieu, l'Assistant vous permet également de choisir une ou plusieurs prédictions et de spécifier une destination afin d'y stocker les résultats.</span><span class="sxs-lookup"><span data-stu-id="e815d-117">Finally, the wizard also gives you the ability to choose one or more predictions, and specify a destination in which to store the results.</span></span>  
  
 <span data-ttu-id="e815d-118">Vous pouvez à tout moment cliquer sur **Avancé** pour basculer vers l' **Éditeur de requêtes avancé d'exploration de données**qui vous permet de contrôler davantage chaque partie de l'instruction DMX.</span><span class="sxs-lookup"><span data-stu-id="e815d-118">At any time, you can click **Advanced** to switch to the **Data Mining Advanced Query Editor**, which gives you more control over each part of the DMX statement.</span></span> <span data-ttu-id="e815d-119">Pour plus d’informations sur l’utilisation des outils avancés de modification de requêtes, consultez [éditeur de requêtes d’exploration de données avancé](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="e815d-119">For more information about how to use the advanced query editing tools, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="e815d-120">Spécifications</span><span class="sxs-lookup"><span data-stu-id="e815d-120">Requirements</span></span>  
 <span data-ttu-id="e815d-121">Pour utiliser l'Assistant **Requête** , vous devez être connecté à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e815d-121">To use the **Query** wizard, you must be connected to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e815d-122">Qui plus est, le serveur doit contenir au moins un modèle d'exploration de données d'un type approprié.</span><span class="sxs-lookup"><span data-stu-id="e815d-122">Moreover, the server must contain at least one data mining model of an appropriate type.</span></span> <span data-ttu-id="e815d-123">Si aucun modèle d'exploration de données n'est disponible, vous pouvez en créer un à l'aide des Assistants fournis dans le Client d'exploration de données pour Excel.</span><span class="sxs-lookup"><span data-stu-id="e815d-123">If no mining models are available, you can create one by using the wizards provided in the Data Mining Client for Excel.</span></span> <span data-ttu-id="e815d-124">Pour plus d’informations sur la création d’un nouveau mode d’exploration de données à l’aide d’un Assistant, consultez [création d’un modèle d’exploration de données](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="e815d-124">For information about how to create a new mining mode by using a wizard, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e815d-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e815d-125">See Also</span></span>  
 <span data-ttu-id="e815d-126">[Déploiement et mise à l’échelle des modèles d’exploration de données &#40;les compléments d’exploration de données pour Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="e815d-126">[Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="e815d-127">Client d’exploration de données pour Excel &#40;SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="e815d-127">Data Mining Client for Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](data-mining-client-for-excel-sql-server-data-mining-add-ins.md)  
  
  
