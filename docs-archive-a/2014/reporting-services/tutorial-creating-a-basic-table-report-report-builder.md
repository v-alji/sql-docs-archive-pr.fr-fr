---
title: 'Tutoriel : Création d’un rapport de tableau de base (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d9e30521-f8ae-4c45-89c3-d40727f622f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3587e2a53e2b09dd347a2733875eafd708b8a05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602706"
---
# <a name="tutorial-creating-a-basic-table-report-report-builder"></a><span data-ttu-id="f5cf0-102">Tutoriel : Création d'un rapport de tableau de base (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="f5cf0-102">Tutorial: Creating a Basic Table Report (Report Builder)</span></span>
  <span data-ttu-id="f5cf0-103">Ce didacticiel vous apprend à créer un rapport de tableau de base à partir des exemples de données de ventes.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-103">This tutorial teaches you to create a basic table report based on sample sales data.</span></span> <span data-ttu-id="f5cf0-104">L’illustration suivante montre le rapport que vous allez créer.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-104">The following illustration shows the report you will create.</span></span>  
  
 <span data-ttu-id="f5cf0-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="f5cf0-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="f5cf0-106">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="f5cf0-106">What You Will Learn</span></span>  
 <span data-ttu-id="f5cf0-107">Dans ce didacticiel, vous apprendrez à effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="f5cf0-107">In this tutorial, you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="f5cf0-108">Créer un rapport à partir de la mise en route</span><span class="sxs-lookup"><span data-stu-id="f5cf0-108">Create a New Report from Getting Started</span></span>](#CreateTable)  
  
    1.  [<span data-ttu-id="f5cf0-109">Spécifier une connexion de données dans l'Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-109">Specify a Data Connection in the Table Wizard</span></span>](#DataConnection)  
  
    2.  [<span data-ttu-id="f5cf0-110">Créer une requête dans l'Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-110">Create a Query in the Table Wizard</span></span>](#Query)  
  
    3.  [<span data-ttu-id="f5cf0-111">Organiser les données en groupes dans l'Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-111">Organize Data into Groups in the Table Wizard</span></span>](#Groups)  
  
    4.  [<span data-ttu-id="f5cf0-112">Ajouter des lignes de sous-total et de total dans l'Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-112">Add Subtotal and Total Rows in the Table Wizard</span></span>](#Subtotals)  
  
    5.  [<span data-ttu-id="f5cf0-113">Choisir un style dans l'Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-113">Choose a Style in the Table Wizard</span></span>](#Style)  
  
2.  [<span data-ttu-id="f5cf0-114">Mettre en forme les données en tant que devises</span><span class="sxs-lookup"><span data-stu-id="f5cf0-114">Format Data as Currency</span></span>](#FormatCurrency)  
  
3.  [<span data-ttu-id="f5cf0-115">Mettre en forme les données de date</span><span class="sxs-lookup"><span data-stu-id="f5cf0-115">Format Data as Date</span></span>](#FormatDate)  
  
4.  [<span data-ttu-id="f5cf0-116">Modifier la largeur des colonnes</span><span class="sxs-lookup"><span data-stu-id="f5cf0-116">Change Column Widths</span></span>](#Width)  
  
5.  [<span data-ttu-id="f5cf0-117">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="f5cf0-117">Add a Report Title</span></span>](#Title)  
  
6.  [<span data-ttu-id="f5cf0-118">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="f5cf0-118">Save the Report</span></span>](#Save)  
  
7.  [<span data-ttu-id="f5cf0-119">Exporter le rapport</span><span class="sxs-lookup"><span data-stu-id="f5cf0-119">Export the Report</span></span>](#Export)  
  
 <span data-ttu-id="f5cf0-120">Durée estimée pour effectuer le didacticiel : 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-120">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5cf0-121">Spécifications</span><span class="sxs-lookup"><span data-stu-id="f5cf0-121">Requirements</span></span>  
 <span data-ttu-id="f5cf0-122">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="f5cf0-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-new-report-from-getting-started"></a><a name="CreateTable"></a><span data-ttu-id="f5cf0-123">1. créer un rapport à partir de Prise en main</span><span class="sxs-lookup"><span data-stu-id="f5cf0-123">1. Create a New Report from Getting Started</span></span>  
 <span data-ttu-id="f5cf0-124">Créez un rapport de tableau à partir de la boîte de dialogue **prise en main** .</span><span class="sxs-lookup"><span data-stu-id="f5cf0-124">Create a table report from the **Getting Started** dialog box.</span></span> <span data-ttu-id="f5cf0-125">Il existe deux modes : création de rapport et création de dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-125">There are two modes: report design and shared dataset design.</span></span> <span data-ttu-id="f5cf0-126">En mode création de rapport, vous pouvez spécifier les données dans le volet des données de rapport et la disposition du rapport dans l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-126">In report design mode, you specify data in the Report Data pane and the report layout on the design surface.</span></span> <span data-ttu-id="f5cf0-127">En mode création de dataset partagé, vous créez des requêtes de dataset à partager avec d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-127">In shared dataset design mode, you create dataset queries to share with others.</span></span> <span data-ttu-id="f5cf0-128">Dans ce didacticiel, vous allez utiliser le mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-128">In this tutorial, you will be using report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="f5cf0-129">Pour créer un rapport</span><span class="sxs-lookup"><span data-stu-id="f5cf0-129">To create a new report</span></span>  
  
1.  <span data-ttu-id="f5cf0-130">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur **Générateur de rapports Microsoft SQL Server 2012**, puis cliquez sur **Générateur de rapports version**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-130">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="f5cf0-131">La boîte de dialogue **Mise en route** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-131">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f5cf0-132">Si la boîte de dialogue **prise en main** n’apparaît pas, à partir du bouton **Générateur de rapports** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-132">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="f5cf0-133">Dans le volet gauche, assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-133">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="f5cf0-134">Dans le volet droit, vérifiez que **Assistant Tableau ou matrice** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-134">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection-in-the-table-wizard"></a><a name="DataConnection"></a><span data-ttu-id="f5cf0-135">1a.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-135">1a.</span></span> <span data-ttu-id="f5cf0-136">Spécifier une connexion de données dans l'Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-136">Specify a Data Connection in the Table Wizard</span></span>  
 <span data-ttu-id="f5cf0-137">Une connexion de données contient les informations nécessaires pour se connecter à une source de données externe telle qu'une base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5cf0-137">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="f5cf0-138">En règle générale, vous obtenez les informations de connexion et le type d'informations d'identification à utiliser auprès du propriétaire de la source de données.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-138">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span> <span data-ttu-id="f5cf0-139">Pour spécifier une connexion de données, vous pouvez utiliser une source de données partagée sur le serveur de rapports ou créer une source de données incorporée utilisée uniquement dans ce rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-139">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span>  
  
 <span data-ttu-id="f5cf0-140">Dans ce didacticiel, vous allez utiliser une source de données incorporée.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-140">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="f5cf0-141">Pour en savoir plus sur l’utilisation des sources de données partagées, consultez [Autres procédures pour l’obtention d’une connexion de données &#40;Générateur de rapports&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f5cf0-141">To learn more about using a shared data sources, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="f5cf0-142">Pour créer une source de données incorporée</span><span class="sxs-lookup"><span data-stu-id="f5cf0-142">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="f5cf0-143">Dans la page **Choisir un dataset** , sélectionnez **Créer un dataset**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-143">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="f5cf0-144">La page **Choisir une connexion à une source de données** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-144">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="f5cf0-145">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-145">Click **New**.</span></span> <span data-ttu-id="f5cf0-146">La boîte de dialogue **Propriétés de la source de données** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-146">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="f5cf0-147">Dans **nom**, tapez **ventes de produits** comme nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-147">In **Name**, type **Product Sales** a name for the data source.</span></span>  
  
4.  <span data-ttu-id="f5cf0-148">Dans **Sélectionner un type de connexion**, assurez-vous que **Microsoft SQL Server** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-148">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
5.  <span data-ttu-id="f5cf0-149">Dans **chaîne de connexion**, tapez le texte suivant, où *\<servername>* est le nom d’une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="f5cf0-149">In **Connection string**, type the following text, where *\<servername>* is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
    ```  
    Data Source=<servername>  
    ```  
  
     <span data-ttu-id="f5cf0-150">Dans la mesure où vous utilisez une requête qui contient les données au lieu de récupérer ces dernières à partir d'une base de données, la chaîne de connexion n'inclut pas le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-150">Because you will use a query that contains the data instead of retrieving the data from a database, the connection string does not include the database name.</span></span> <span data-ttu-id="f5cf0-151">Pour plus d’informations, voir [Éléments requis pour les didacticiels (Générateur de rapports)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="f5cf0-151">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
6.  <span data-ttu-id="f5cf0-152">Cliquez sur **Informations d'identification**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-152">Click **Credentials**.</span></span> <span data-ttu-id="f5cf0-153">Entrez les informations d'identification nécessaires pour accéder à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-153">Enter the credentials that you need to access the external data source.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="f5cf0-154">Vous revenez à la page **Choisir une connexion à une source de données** .</span><span class="sxs-lookup"><span data-stu-id="f5cf0-154">You are back on the **Choose a connection to a data source** page.</span></span>  
  
8.  <span data-ttu-id="f5cf0-155">Pour vous assurer que vous pouvez vous connecter à la source de données, cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-155">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="f5cf0-156">Le message « La connexion a été correctement créée » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-156">The message "Connection created successfully" appears.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="f5cf0-157">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-157">Click **Next**.</span></span>  
  
##  <a name="1b-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="f5cf0-158">ter.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-158">1b.</span></span> <span data-ttu-id="f5cf0-159">Créer une requête dans l'Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-159">Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="f5cf0-160">Dans un rapport, vous pouvez utiliser un dataset partagé qui comprend une requête prédéfinie, ou vous pouvez créer un dataset incorporé utilisable uniquement dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-160">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="f5cf0-161">Dans ce didacticiel, vous allez créer un dataset incorporé.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-161">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f5cf0-162">Dans ce didacticiel, la requête contient les valeurs de données, afin qu'il ne soit pas nécessaire de disposer d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-162">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="f5cf0-163">Cela rend la requête assez longue.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-163">This makes the query quite long.</span></span> <span data-ttu-id="f5cf0-164">Dans un environnement métier, une requête ne contient pas les données.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-164">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="f5cf0-165">Ceci est nécessaire à des fins de formation uniquement.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-165">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="f5cf0-166">Pour créer une requête</span><span class="sxs-lookup"><span data-stu-id="f5cf0-166">To create a query</span></span>  
  
1.  <span data-ttu-id="f5cf0-167">Dans la page **Créer une requête** , le concepteur de requêtes relationnelles est ouvert.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-167">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="f5cf0-168">Pour ce didacticiel, vous utiliserez le Concepteur de requêtes textuel.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-168">For this tutorial, you will use the text-based query designer.</span></span>  
  
     <span data-ttu-id="f5cf0-169">Cliquez sur **modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-169">Click **Edit As Text**.</span></span> <span data-ttu-id="f5cf0-170">Le Concepteur de requêtes textuel affiche un volet de requête et un volet de résultats.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-170">The text-based query designer displays a query pane and a results pane.</span></span>  
  
2.  <span data-ttu-id="f5cf0-171">Collez la requête [!INCLUDE[tsql](../includes/tsql-md.md)] ci-après dans la zone **Requête** .</span><span class="sxs-lookup"><span data-stu-id="f5cf0-171">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(9924.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Mini Battery Charger' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Telephoto Conversion Lens' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,'Accessories' as Subcategory,    
       'USB Cable' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Business Videographer' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-10' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Social Videographer' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Advanced Digital' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Compact Digital' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Consumer Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera 35mm' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
  
    ```  
  
3.  <span data-ttu-id="f5cf0-172">Dans la barre d’outils du concepteur de requêtes, cliquez sur **exécuter** (**!**).</span><span class="sxs-lookup"><span data-stu-id="f5cf0-172">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="f5cf0-173">La requête s'exécute et affiche le jeu de résultats pour les champs SalesDate, Subcategory, Product, Sales et Quantity.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-173">The query runs and displays the result set for the fields SalesDate, Subcategory, Product, Sales, and Quantity.</span></span>  
  
     <span data-ttu-id="f5cf0-174">Dans le jeu de résultats, les en-têtes de colonnes sont basés sur les noms présents dans la requête.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-174">In the result set, the column headings are based on the names in the query.</span></span> <span data-ttu-id="f5cf0-175">Dans le dataset, les en-têtes de colonnes deviennent les noms de champs et sont enregistrés dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-175">In the dataset, the column headings become the field names, and are saved in the report.</span></span> <span data-ttu-id="f5cf0-176">Après avoir terminé l'Assistant, vous pouvez utiliser le volet des données de rapport pour afficher la collection de champs de dataset.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-176">After you complete the wizard, you can use the Report Data pane to view the collection of dataset fields.</span></span>  
  
4.  <span data-ttu-id="f5cf0-177">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-177">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups-in-the-table-wizard"></a><a name="Groups"></a><span data-ttu-id="f5cf0-178">1C.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-178">1c.</span></span> <span data-ttu-id="f5cf0-179">Organiser les données en groupes dans l'Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-179">Organize Data into Groups in the Table Wizard</span></span>  
 <span data-ttu-id="f5cf0-180">Lorsque vous sélectionnez des champs à regrouper, vous concevez un tableau dont les lignes et les colonnes affichent des données de détail et des données agrégées.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-180">When you select fields to group on, you design a table that has rows and columns that display detail data and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="f5cf0-181">Pour organiser les données en groupes</span><span class="sxs-lookup"><span data-stu-id="f5cf0-181">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="f5cf0-182">Dans la page **Organiser les champs** , faites glisser Product vers **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-182">On the **Arrange fields** page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="f5cf0-183">Faites glisser Quantity vers **Valeurs** et placez-le sous Product.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-183">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="f5cf0-184">Quantity est automatiquement agrégé par la fonction Sum, l'agrégat par défaut des champs numériques.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-184">Quantity is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="f5cf0-185">La valeur est [Sum(Quantity)].</span><span class="sxs-lookup"><span data-stu-id="f5cf0-185">The value is [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="f5cf0-186">Vous pouvez ouvrir la liste déroulante pour consulter les autres fonctions d'agrégation disponibles.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-186">You can open the drop-down list to view the other aggregate functions available.</span></span> <span data-ttu-id="f5cf0-187">Ne modifiez pas la fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-187">Do not change the aggregate function.</span></span>  
  
3.  <span data-ttu-id="f5cf0-188">Faites glisser Sales vers **Valeurs** et placez-le sous [Sum(Quantity)].</span><span class="sxs-lookup"><span data-stu-id="f5cf0-188">Drag Sales to **Values** and place below [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="f5cf0-189">Sales est agrégé par la fonction Sum.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-189">Sales is aggregated by the Sum function.</span></span> <span data-ttu-id="f5cf0-190">La valeur est [Sum(Sales)].</span><span class="sxs-lookup"><span data-stu-id="f5cf0-190">The value is [Sum(Sales)].</span></span>  
  
     <span data-ttu-id="f5cf0-191">Les étapes 1, 2 et 3 spécifient les données à afficher dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-191">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="f5cf0-192">Faites glisser SalesDate vers **Groupes de lignes**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-192">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="f5cf0-193">Faites glisser Subcategory vers **Groupes de lignes** et placez-le sous SalesDate.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-193">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="f5cf0-194">Les étapes 4 et 5 organisent les valeurs des champs par date, puis par sous-catégorie de produits pour chaque date.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-194">Steps 4 and 5 organize the values for the fields first by date, and then by product subcategory for that date.</span></span>  
  
6.  <span data-ttu-id="f5cf0-195">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-195">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotal-and-total-rows-in-the-table-wizard"></a><a name="Subtotals"></a><span data-ttu-id="f5cf0-196">1D.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-196">1d.</span></span> <span data-ttu-id="f5cf0-197">Ajouter des lignes de sous-total et de total dans l'Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-197">Add Subtotal and Total Rows in the Table Wizard</span></span>  
 <span data-ttu-id="f5cf0-198">Après avoir créé des groupes, vous pouvez ajouter et mettre en forme les lignes dans lesquelles afficher les valeurs agrégées des champs.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-198">After you create groups, you can add and format rows on which to display aggregate values for the fields.</span></span> <span data-ttu-id="f5cf0-199">Vous pouvez afficher toutes les données ou laisser l'utilisateur développer/réduire les données regroupées de manière interactive.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-199">You can choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="f5cf0-200">Pour ajouter des sous-totaux et des totaux</span><span class="sxs-lookup"><span data-stu-id="f5cf0-200">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="f5cf0-201">Dans la page **Choisir la disposition** , sous **Options**, vérifiez que **Afficher les sous-totaux et les totaux généraux** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-201">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
2.  <span data-ttu-id="f5cf0-202">Vérifiez que **Bloqué, sous-total ci-dessous** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-202">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
     <span data-ttu-id="f5cf0-203">Le volet Aperçu de l'Assistant affiche un tableau avec cinq lignes.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-203">The wizard Preview pane displays a table with five rows.</span></span> <span data-ttu-id="f5cf0-204">Lorsque vous exécutez le rapport, chaque ligne est affichée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="f5cf0-204">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="f5cf0-205">La première ligne est répétée une fois pour le tableau afin d'afficher les en-têtes de colonnes.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-205">The first row will repeat once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="f5cf0-206">La deuxième ligne est répétée une fois pour chaque élément de ligne dans la commande client et affiche le nom du produit, la quantité commandée et le total de ligne.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-206">The second row will repeat once for each line item in the sales order and display the product name, order quantity, and line total.</span></span>  
  
    3.  <span data-ttu-id="f5cf0-207">La troisième ligne est répétée une fois pour chaque commande client afin d'afficher les sous-totaux par commande.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-207">The third row will repeat once for each sales order to display subtotals per order.</span></span>  
  
    4.  <span data-ttu-id="f5cf0-208">La quatrième ligne est répétée une fois pour chaque date de commande afin d'afficher les sous-totaux par jour.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-208">The fourth row will repeat once for each order date to display the subtotals per day.</span></span>  
  
    5.  <span data-ttu-id="f5cf0-209">La cinquième ligne est répétée une fois pour le tableau afin d'afficher les totaux généraux.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-209">The fifth row will repeat once for the table to display the grand totals.</span></span>  
  
3.  <span data-ttu-id="f5cf0-210">Décochez l’option **Développer/Réduire les groupes**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-210">Clear the option **Expand/collapse groups**.</span></span> <span data-ttu-id="f5cf0-211">Dans ce didacticiel, le rapport que vous créez n'utilise pas la fonctionnalité d'exploration vers le bas qui permet à un utilisateur de développer une hiérarchie de groupe parente afin d'afficher les lignes de groupes enfants et les lignes de détails.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-211">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
4.  <span data-ttu-id="f5cf0-212">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-212">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style-in-the-table-wizard"></a><a name="Style"></a><span data-ttu-id="f5cf0-213">1La.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-213">1e.</span></span> <span data-ttu-id="f5cf0-214">Choisir un style dans l'Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-214">Choose a Style in the Table Wizard</span></span>  
 <span data-ttu-id="f5cf0-215">Un style spécifie un style de police, un jeu de couleurs et un style de bordure.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-215">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-table-style"></a><span data-ttu-id="f5cf0-216">Pour spécifier un style de tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-216">To specify a table style</span></span>  
  
1.  <span data-ttu-id="f5cf0-217">Dans la page **choisir un style** , dans le volet styles, sélectionnez océan.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-217">On the **Choose a Style** page, in the Styles pane, select Ocean.</span></span>  
  
     <span data-ttu-id="f5cf0-218">Le volet Aperçu affiche un aperçu du tableau avec ce style.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-218">The Preview pane displays a sample of the table with that style.</span></span>  
  
2.  <span data-ttu-id="f5cf0-219">Éventuellement, cliquez sur les autres styles pour voir l'aperçu correspondant.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-219">Optionally, click the other styles to see the sample with them applied.</span></span>  
  
3.  <span data-ttu-id="f5cf0-220">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-220">Click **Finish**.</span></span>  
  
 <span data-ttu-id="f5cf0-221">Le tableau est ajouté à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-221">The table is added to the design surface.</span></span> <span data-ttu-id="f5cf0-222">Le tableau possède 5 colonnes et 5 lignes.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-222">The table has 5 columns and 5 rows.</span></span> <span data-ttu-id="f5cf0-223">Le volet Groupes de lignes affiche trois lignes : SalesDate, Subcategory et Details.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-223">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="f5cf0-224">Les données de détail sont toutes les données récupérées par la requête de dataset.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-224">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="f5cf0-225">2. mettre en forme les données en tant que devise</span><span class="sxs-lookup"><span data-stu-id="f5cf0-225">2. Format Data as Currency</span></span>  
 <span data-ttu-id="f5cf0-226">Par défaut, les données de synthèse du champ Sales affichent un nombre général.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-226">By default, the summary data for the Sales field displays a general number.</span></span> <span data-ttu-id="f5cf0-227">Appliquez une mise en forme pour afficher ce nombre dans un format monétaire.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-227">Format it to display the number as currency.</span></span> <span data-ttu-id="f5cf0-228">Activez/désactivez **Styles des espaces réservés** pour afficher les zones de texte mises en forme et le texte de l’espace réservé en tant qu’exemples de valeurs.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-228">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="f5cf0-229">Pour mettre en forme un champ monétaire</span><span class="sxs-lookup"><span data-stu-id="f5cf0-229">To format a currency field</span></span>  
  
1.  <span data-ttu-id="f5cf0-230">Cliquez sur **Conception** pour basculer en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-230">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="f5cf0-231">Cliquez sur la cellule de la deuxième ligne (sous la ligne des en-têtes de colonnes) de la colonne Sales et faites glisser la souris vers le bas de façon à sélectionner toutes les cellules qui contiennent `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-231">Click the cell in the second row (under the column headings row) in the Sales column and drag down to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="f5cf0-232">Sous l’onglet **Accueil** , dans le groupe **Nombre** , cliquez sur le bouton **Devise** .</span><span class="sxs-lookup"><span data-stu-id="f5cf0-232">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="f5cf0-233">Les cellules changent pour afficher le format de devise.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-233">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="f5cf0-234">Si votre paramètre régional est Anglais (États-Unis), le texte d’exemple par défaut est [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="f5cf0-234">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="f5cf0-235">Si vous ne voyez pas d’exemple de valeur monétaire, cliquez sur **styles des espaces réservés** dans le groupe **nombres** , puis cliquez sur **exemples de valeurs**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-235">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="f5cf0-236">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-236">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="f5cf0-237">Les valeurs de synthèse de Sales s'affichent sous forme de devises.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-237">The summary values for Sales display as currency.</span></span>  
  
##  <a name="3-format-data-as-date"></a><a name="FormatDate"></a><span data-ttu-id="f5cf0-238">3. mettre en forme les données en tant que date</span><span class="sxs-lookup"><span data-stu-id="f5cf0-238">3. Format Data as Date</span></span>  
 <span data-ttu-id="f5cf0-239">Par défaut, le champ SalesDate affiche les informations de date et d'heure.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-239">By default, the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="f5cf0-240">Vous pouvez le mettre en forme de sorte qu'il n'affiche que la date.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-240">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="f5cf0-241">Pour appliquer à un champ de date le format par défaut</span><span class="sxs-lookup"><span data-stu-id="f5cf0-241">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="f5cf0-242">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-242">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="f5cf0-243">Cliquez sur la cellule qui contient `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-243">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="f5cf0-244">Dans le ruban, sous l’onglet dossier de **démarrage** , dans le groupe **nombre** , dans la liste déroulante, sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-244">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="f5cf0-245">La cellule affiche l’exemple de date **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-245">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="f5cf0-246">Si vous ne voyez pas s’afficher d’exemple de date, cliquez sur **Styles des espaces réservés** dans le groupe **Nombres** , puis cliquez sur **Valeurs d’aperçu**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-246">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="f5cf0-247">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-247">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="f5cf0-248">Les valeurs de SalesDate s'affichent dans le format de date par défaut.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-248">The SalesDate values display in the default date format.</span></span>  
  
#### <a name="to-change-the-date-format-to-a-custom-format"></a><span data-ttu-id="f5cf0-249">Pour appliquer à une date un format personnalisé</span><span class="sxs-lookup"><span data-stu-id="f5cf0-249">To change the date format to a custom format</span></span>  
  
1.  <span data-ttu-id="f5cf0-250">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="f5cf0-251">Cliquez sur la cellule qui contient `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="f5cf0-252">Dans l’onglet dossier de **démarrage** , dans le groupe **nombre** , cliquez sur le lanceur de boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-252">On the **Home** tab, in the **Number** group, click the dialog box launcher.</span></span>  
  
     <span data-ttu-id="f5cf0-253">Il s'agit de la petite flèche située à l'angle droit du groupe.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-253">The launcher is the small arrow in the right-hand corner of the group.</span></span> <span data-ttu-id="f5cf0-254">La boîte de dialogue **Propriétés de la zone de texte** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-254">The **Text Box Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="f5cf0-255">Dans le volet Catégorie, vérifiez que **Date** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-255">In the Category pane, verify that **Date** is selected.</span></span>  
  
5.  <span data-ttu-id="f5cf0-256">Dans le volet **Type** , sélectionnez **January 31, 2000**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-256">In the **Type** pane, select **January 31, 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="f5cf0-257">La cellule affiche l’exemple de date **[January 31, 2000]**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-257">The cell displays the example date **[January 31, 2000]**.</span></span>  
  
7.  <span data-ttu-id="f5cf0-258">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-258">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="f5cf0-259">La valeur affichée du champ SalesDate correspond au mois dans sa forme textuelle et non numérique.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-259">The SalesDate value displays with the name of the month instead of the number for the month.</span></span>  
  
##  <a name="4-change-column-widths"></a><a name="Width"></a><span data-ttu-id="f5cf0-260">4. modifier la largeur des colonnes</span><span class="sxs-lookup"><span data-stu-id="f5cf0-260">4. Change Column Widths</span></span>  
 <span data-ttu-id="f5cf0-261">Par défaut, chaque cellule d'un tableau contient une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-261">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="f5cf0-262">Une zone de texte s'étend verticalement pour accueillir le texte lors du rendu de la page.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-262">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="f5cf0-263">Dans le rapport rendu, chaque ligne s'étend en fonction de la hauteur de la plus grande zone de texte rendue dans la ligne.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-263">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="f5cf0-264">La hauteur de la ligne dans l'aire de conception n'a aucun impact sur la hauteur de la ligne dans le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-264">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="f5cf0-265">Pour réduire l'espace vertical occupé par chaque ligne, augmentez la largeur de colonne afin d'accueillir le contenu attendu des zones de texte dans la colonne sur une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-265">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-table-columns"></a><span data-ttu-id="f5cf0-266">Pour modifier la largeur des colonnes d'un tableau</span><span class="sxs-lookup"><span data-stu-id="f5cf0-266">To change the width of table columns</span></span>  
  
1.  <span data-ttu-id="f5cf0-267">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-267">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="f5cf0-268">Cliquez sur la table pour que les poignées de ligne et de colonne apparaissent au-dessus et à côté de la table.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-268">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="f5cf0-269">Les barres grises le long du haut et du côté de la table sont les poignées de colonne et de ligne.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-269">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="f5cf0-270">Placez le curseur entre les séparateurs de colonne pour qu'il se transforme en flèche à deux pointes.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-270">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="f5cf0-271">Faites glisser les colonnes pour les redimensionner.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-271">Drag the columns to the size you want.</span></span> <span data-ttu-id="f5cf0-272">Par exemple, agrandissez la colonne Product de sorte que le nom des produits tienne sur une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-272">For example, expand the column for Product so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="f5cf0-273">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-273">Click **Run** to preview your report.</span></span>  
  
##  <a name="5-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="f5cf0-274">5. Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="f5cf0-274">5. Add a Report Title</span></span>  
 <span data-ttu-id="f5cf0-275">Un titre de rapport s'affiche dans la partie supérieure du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-275">A report title appears at the top of the report.</span></span> <span data-ttu-id="f5cf0-276">Vous pouvez placer le titre du rapport dans un en-tête de rapport, ou si le rapport n'en utilise pas, dans une zone de texte située en haut du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-276">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="f5cf0-277">Dans ce didacticiel, vous allez utiliser la zone de texte placée automatiquement en haut du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-277">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="f5cf0-278">Vous pouvez améliorer le texte en appliquant différents types de styles de police, de tailles et de couleurs à des expressions et des caractères spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-278">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="f5cf0-279">Pour plus d’informations, consultez [Mettre en forme du texte dans une zone de texte &#40;Générateur de rapports et SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f5cf0-279">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="f5cf0-280">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="f5cf0-280">To add a report title</span></span>  
  
1.  <span data-ttu-id="f5cf0-281">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-281">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="f5cf0-282">Tapez **Product Sales**, puis cliquez à l’extérieur de la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-282">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="f5cf0-283">Cliquez avec le bouton droit sur la zone de texte qui contient **Product Sales** , puis cliquez sur **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-283">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="f5cf0-284">Dans la boîte de dialogue **Propriétés de la zone de texte** , cliquez sur **Police**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-284">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="f5cf0-285">Dans la liste **Taille** , sélectionnez **18pt**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-285">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="f5cf0-286">Dans la liste **Couleur** , sélectionnez **Bleuet**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-286">In the **Color** list, select **Cornflower Blue**.</span></span>  
  
7.  <span data-ttu-id="f5cf0-287">Sélectionnez **Gras**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-287">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report"></a><a name="Save"></a><span data-ttu-id="f5cf0-288">6. enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="f5cf0-288">6. Save the Report</span></span>  
 <span data-ttu-id="f5cf0-289">Enregistrez le rapport sur un serveur de rapports ou sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-289">Save the report to a report server or your computer.</span></span> <span data-ttu-id="f5cf0-290">Si vous n'enregistrez pas le rapport sur le serveur de rapports, plusieurs fonctionnalités de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] telles que les parties de rapports et les sous-rapports ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-290">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="f5cf0-291">Pour enregistrer le rapport sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="f5cf0-291">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="f5cf0-292">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-292">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="f5cf0-293">Cliquez sur **Sites et serveurs récents**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-293">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="f5cf0-294">Sélectionnez ou tapez le nom du serveur de rapports sur lequel vous êtes autorisé à enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-294">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="f5cf0-295">Le message « Connexion au serveur de rapports » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-295">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="f5cf0-296">Une fois la connexion établie, le contenu du dossier de rapports spécifié par l'administrateur du serveur de rapports s'affiche comme emplacement par défaut des rapports.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-296">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="f5cf0-297">Dans **Nom**, remplacez le nom par défaut par **Ventes de produits**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-297">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="f5cf0-298">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-298">Click **Save**.</span></span>  
  
 <span data-ttu-id="f5cf0-299">Le rapport est enregistré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-299">The report is saved to the report server.</span></span> <span data-ttu-id="f5cf0-300">Le nom du serveur de rapports auquel vous êtes connecté est indiqué dans la barre d'état située au bas de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-300">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="f5cf0-301">Pour enregistrer le rapport sur votre ordinateur</span><span class="sxs-lookup"><span data-stu-id="f5cf0-301">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="f5cf0-302">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-302">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="f5cf0-303">Cliquez sur **Bureau**, **Mes documents**ou **Poste de travail**, puis naviguez jusqu’au dossier où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-303">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="f5cf0-304">Dans **Nom**, remplacez le nom par défaut par **Ventes de produits**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-304">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="f5cf0-305">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-305">Click **Save**.</span></span>  
  
##  <a name="7-export-the-report"></a><a name="Export"></a><span data-ttu-id="f5cf0-306">7. exporter le rapport</span><span class="sxs-lookup"><span data-stu-id="f5cf0-306">7. Export the Report</span></span>  
 <span data-ttu-id="f5cf0-307">Les rapports peuvent être exportés vers différents formats, par exemple Microsoft Excel et les fichiers de valeurs séparées par des virgules (CSV).</span><span class="sxs-lookup"><span data-stu-id="f5cf0-307">Reports can be exported to different formats such Microsoft Excel and comma separated value (CSV).</span></span> <span data-ttu-id="f5cf0-308">Pour plus d’informations, consultez [exportation de rapports &#40;générateur de rapports et&#41;SSRS ](report-builder/export-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f5cf0-308">For more information, see [Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="f5cf0-309">Dans ce didacticiel, vous allez exporter le rapport vers Excel et définir une propriété du rapport afin de fournir un nom personnalisé pour l'onglet de classeur.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-309">In this tutorial, you will export the report to Excel and set a property on the report to provide a custom name for the workbook tab.</span></span>  
  
#### <a name="to-specify-the-workbook-tab-name"></a><span data-ttu-id="f5cf0-310">Pour spécifier le nom de l'onglet de classeur</span><span class="sxs-lookup"><span data-stu-id="f5cf0-310">To specify the workbook tab name</span></span>  
  
1.  <span data-ttu-id="f5cf0-311">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-311">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="f5cf0-312">Cliquez n'importe où en dehors du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-312">Click anywhere outside the report.</span></span>  
  
3.  <span data-ttu-id="f5cf0-313">. Dans le volet Propriétés, recherchez la propriété InitialPageName et tapez **ventes de produits Excel**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-313">.In the Properties pane, locate the InitialPageName property and type **Product Sales Excel**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f5cf0-314">Si le volet Propriétés n’est pas visible, cliquez sur l’onglet Affichage sur le ruban, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-314">If the Properties pane is not visible, click the View tab on the ribbon, and then click **Properties**.</span></span>  
  
#### <a name="to-export-a-report-to-excel"></a><span data-ttu-id="f5cf0-315">Pour exporter un rapport vers Excel</span><span class="sxs-lookup"><span data-stu-id="f5cf0-315">To export a report to Excel</span></span>  
  
1.  <span data-ttu-id="f5cf0-316">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-316">Click **Run** to preview the report.</span></span>  
  
2.  <span data-ttu-id="f5cf0-317">. Sur le ruban, cliquez sur **Exporter**, puis sur **Excel**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-317">.On the ribbon, click **Export**, and then click **Excel**.</span></span>  
  
     <span data-ttu-id="f5cf0-318">La boîte de dialogue **Enregistrer sous** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-318">The **Save As** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="f5cf0-319">Accédez au dossier **documents** .</span><span class="sxs-lookup"><span data-stu-id="f5cf0-319">Browse to the **Documents** folder.</span></span>  
  
4.  <span data-ttu-id="f5cf0-320">Dans la zone de texte **nom de fichier** , tapez **ventes de produits Excel**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-320">In the **File name** text box, type **Product Sales Excel**.</span></span>  
  
5.  <span data-ttu-id="f5cf0-321">Vérifiez que le type de fichier est **classeur Excel**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-321">Verify that the file type is **Excel Workbook**.</span></span>  
  
6.  <span data-ttu-id="f5cf0-322">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-322">Click **Save**.</span></span>  
  
#### <a name="to-view-the-report-in-excel"></a><span data-ttu-id="f5cf0-323">Pour afficher le rapport dans Excel</span><span class="sxs-lookup"><span data-stu-id="f5cf0-323">To view the report in Excel</span></span>  
  
1.  <span data-ttu-id="f5cf0-324">Ouvrez le dossier **documents** et double-cliquez sur **ventes de produits Excel.xlsx**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-324">Open the **Documents** folder and double click **Product Sales Excel.xlsx**.</span></span>  
  
2.  <span data-ttu-id="f5cf0-325">Vérifiez que le nom de l’onglet de classeur est **Product Sales Excel**.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-325">Verify that the name of the workbook tab is **Product Sales Excel**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f5cf0-326">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="f5cf0-326">Next Steps</span></span>  
 <span data-ttu-id="f5cf0-327">Ceci conclut la procédure pas à pas décrivant comment créer un rapport de tableau de base.</span><span class="sxs-lookup"><span data-stu-id="f5cf0-327">This concludes the walkthrough for how to create a basic table report.</span></span> <span data-ttu-id="f5cf0-328">Pour plus d’informations sur les tables, consultez [Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f5cf0-328">For more information about tables, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5cf0-329">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5cf0-329">See Also</span></span>  
 <span data-ttu-id="f5cf0-330">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="f5cf0-330">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="f5cf0-331">Générateur de rapports dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="f5cf0-331">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
