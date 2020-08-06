---
title: Récupérer des données d’un modèle d’exploration de données (DMX) (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- retrieving report data
- datasets [Reporting Services], with DMX queries
- datasets [Reporting Services], Analysis Services
- queries [Reporting Services], data mining prediction
ms.assetid: d9cd3624-1594-4707-8887-55437dd7e07c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a59184524967a9bfe772e41890afc3b900cc9e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706252"
---
# <a name="retrieve-data-from-a-data-mining-model-dmx-ssrs"></a><span data-ttu-id="9a2c1-102">Récupérer des données d'un modèle d'exploration de données (DMX) (SSRS)</span><span class="sxs-lookup"><span data-stu-id="9a2c1-102">Retrieve Data from a Data Mining Model (DMX) (SSRS)</span></span>
  <span data-ttu-id="9a2c1-103">Pour utiliser les données d’un modèle d’exploration de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] dans votre rapport, vous devez définir une source de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ainsi qu’un ou plusieurs datasets de rapport.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-103">To use data from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data mining model in your report, you must define a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source and one or more report datasets.</span></span> <span data-ttu-id="9a2c1-104">Lorsque vous créez la définition de la source de données, vous devez spécifier une chaîne de connexion et des informations d'identification pour pouvoir accéder à la source de données à partir de l'ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-104">When you create the data source definition, you must specify a connection string and credentials so that you can access the data source from your client computer.</span></span>  
  
 <span data-ttu-id="9a2c1-105">Vous pouvez créer une définition de source de données incorporée à utiliser par un seul rapport ou une définition de source de données partagée utilisable par plusieurs rapports.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-105">You can create an embedded data source definition for use by a single report or a shared data source definition that can be used by multiple reports.</span></span> <span data-ttu-id="9a2c1-106">Les procédures de cette rubrique décrivent la création d'une source de données incorporée.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-106">The procedures in this topic describe how to create an embedded data source.</span></span> <span data-ttu-id="9a2c1-107">Pour plus d’informations sur les sources de données partagées, consultez [Connexions de données ou sources de données incorporées et partagées &#40;Générateur de rapports et SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) et [Créer, modifier, puis supprimer des sources de données partagées &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9a2c1-107">For more information about shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) and [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
 <span data-ttu-id="9a2c1-108">Après avoir créé une source de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], vous pouvez créer un ou plusieurs datasets.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-108">After you create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you can create one or more datasets.</span></span> <span data-ttu-id="9a2c1-109">Pour chaque dataset, vous utilisez un concepteur de requêtes de prédiction de l'exploration de données (DMX) pour créer une requête DMX qui spécifie la collection de champs.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-109">For each dataset, you use a Data Mining Prediction Expression (DMX) query designer to create a DMX query that specifies the field collection.</span></span> <span data-ttu-id="9a2c1-110">Pour plus d’informations, consultez [Interface utilisateur du Concepteur de requêtes DMX Analysis Services](analysis-services-dmx-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9a2c1-110">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span></span>  
  
 <span data-ttu-id="9a2c1-111">Le nom du dataset créé apparaît dans le volet des données de rapport sous la forme d'un nœud sous la source de données correspondante.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-111">After you create a dataset, the name of the dataset appears in the Report Data pane as a node under its data source.</span></span>  
  
 <span data-ttu-id="9a2c1-112">Après avoir publié votre rapport, vous pouvez devoir modifier les informations d'identification pour la source de données afin que les autorisations soient valides pour récupérer les données lorsque le rapport s'exécute sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-112">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
### <a name="to-create-an-embedded-microsoft-sql-server-analysis-services-data-source"></a><span data-ttu-id="9a2c1-113">Pour créer une source de données Microsoft SQL Server Analysis Services incorporée</span><span class="sxs-lookup"><span data-stu-id="9a2c1-113">To create an embedded Microsoft SQL Server Analysis Services data source</span></span>  
  
1.  <span data-ttu-id="9a2c1-114">Dans la barre d'outils du volet Données du rapport, cliquez sur **Nouveau**, puis sur **Source de données**.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-114">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="9a2c1-115">Dans la boîte de dialogue **Propriétés de la source de données** , tapez un nom dans la zone de texte **Nom** ou acceptez le nom par défaut.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-115">In the **Data Source Properties** dialog box, type a name in the **Name** text box, or accept the default name.</span></span>  
  
3.  <span data-ttu-id="9a2c1-116">Vérifiez que l’option **Connexion incorporée** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-116">Verify that **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="9a2c1-117">Dans la liste déroulante **Type** , sélectionnez **Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-117">From the **Type** drop-down list, select **Microsoft SQL Server Analysis Services**.</span></span>  
  
5.  <span data-ttu-id="9a2c1-118">Spécifiez une chaîne de connexion qui fonctionne avec votre source de données [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a2c1-118">Specify a connection string that works with your [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source.</span></span>  
  
     <span data-ttu-id="9a2c1-119">Contactez l'administrateur de votre base de données pour connaître les informations de connexion et d'identification à utiliser pour se connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-119">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="9a2c1-120">L’exemple de chaîne de connexion suivant spécifie l’exemple de base de données [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] sur le client local.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-120">The following connection string example specifies the sample [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] database on the local client.</span></span>  
  
    ```  
    Data Source=localhost;Initial Catalog=AdventureWorksDW2012  
    ```  
  
6.  <span data-ttu-id="9a2c1-121">Cliquez sur **Informations d'identification**.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-121">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="9a2c1-122">Définissez les informations d'identification à utiliser pour se connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-122">Set the credentials to use to connect to the data source.</span></span> <span data-ttu-id="9a2c1-123">Pour plus d’informations, consultez [Spécifier des informations d’identification et de connexion pour les sources de données de rapport](../../integration-services/connection-manager/data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="9a2c1-123">For more information, see [Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a2c1-124">Pour tester la connexion à la source de données, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-124">To test the data source connection, click **Edit**.</span></span> <span data-ttu-id="9a2c1-125">Dans la boîte de dialogue **Propriétés de connexion** , cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-125">In the **Connection Properties** dialog box, click **Test Connection**.</span></span> <span data-ttu-id="9a2c1-126">Si le test a réussi, le message « Le test de la connexion a réussi. » s’affiche.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-126">If the test is successful, you will see the information message "Test connection succeeded."</span></span> <span data-ttu-id="9a2c1-127">Si le test échoue, un message d'avertissement apparaît avec d'autres informations sur la cause de l'échec.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-127">If the test fails, you will see a warning message with more information about why the test was not successful.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="9a2c1-128">La source de données apparaît dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-128">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-a-dataset-for-a-microsoft-sql-server-analysis-services"></a><span data-ttu-id="9a2c1-129">Pour créer un dataset pour Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9a2c1-129">To create a dataset for a Microsoft SQL Server Analysis Services</span></span>  
  
1.  <span data-ttu-id="9a2c1-130">Dans le volet **Données du rapport** , cliquez avec le bouton droit sur le nom de la source de données qui se connecte à une source de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], puis cliquez sur **Ajouter un dataset**.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-130">In the **Report Data** pane, right-click the name of the data source that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="9a2c1-131">Dans la boîte de dialogue **Propriétés du dataset** , tapez un nom dans la zone de texte **Nom** .</span><span class="sxs-lookup"><span data-stu-id="9a2c1-131">In the **Dataset Properties** dialog box, type a name in the **Name** text box.</span></span>  
  
3.  <span data-ttu-id="9a2c1-132">Dans la zone **Source de données**, vérifiez que le nom est celui d’une source de données qui se connecte à une source de données [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a2c1-132">In the **Data source box**, verify that the name is the name of a data source that connects to an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source.</span></span>  
  
4.  <span data-ttu-id="9a2c1-133">Cliquez sur **Concepteur de requêtes** pour ouvrir le concepteur de requêtes graphique afin de créer une requête de manière interactive.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-133">Click **Query Designer** to open the graphical query designer to build a query interactively.</span></span> <span data-ttu-id="9a2c1-134">Si le concepteur de requêtes s’ouvre en mode MDX, cliquez sur **Type de commande DMX** (![Basculer vers la vue langage de requête DMX](../media/rsqdicon-commandtypedmx.gif "Basculer vers l'affichage de langage de requête DMX")) dans la barre d’outils pour basculer vers le concepteur de requêtes d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-134">If the query designer opens in MDX mode, click **Command Type DMX** (![Change to DMX query language view](../media/rsqdicon-commandtypedmx.gif "Change to DMX query language view")) on the toolbar to switch to the data mining query designer.</span></span> <span data-ttu-id="9a2c1-135">Pour plus d’informations, consultez [Interface utilisateur du Concepteur de requêtes DMX Analysis Services](analysis-services-dmx-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9a2c1-135">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span></span>  
  
     <span data-ttu-id="9a2c1-136">Vous pouvez également importer une requête DMX existante à partir d’un autre rapport. Pour ce faire, cliquez sur **Importer**, puis naviguez jusqu’au fichier .rdl contenant la requête DMX.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-136">Alternatively, to import an existing DMX query from another report, click **Import**, and then navigate to the .rdl file with the DMX query.</span></span> <span data-ttu-id="9a2c1-137">L'importation d'une requête à partir d'un fichier .dmx n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-137">Importing a query from an .dmx file is not supported.</span></span>  
  
5.  <span data-ttu-id="9a2c1-138">Après avoir créé et exécuté votre requête pour afficher des exemples de résultats, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-138">After you create and run your query to see sample results, click **OK**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="9a2c1-139">Le dataset et sa collection de champs s'affichent dans le volet des données de rapport sous le nœud de source de données.</span><span class="sxs-lookup"><span data-stu-id="9a2c1-139">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a2c1-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a2c1-140">See Also</span></span>  
 <span data-ttu-id="9a2c1-141">[Type de connexion Analysis Services pour DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9a2c1-141">[Analysis Services Connection Type for DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) </span></span>  
 <span data-ttu-id="9a2c1-142">[Connexions de données, sources de données et chaînes de connexion dans Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="9a2c1-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="9a2c1-143">[Collection de champs de dataset &#40;Générateur de rapports et SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9a2c1-143">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="9a2c1-144">Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9a2c1-144">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
