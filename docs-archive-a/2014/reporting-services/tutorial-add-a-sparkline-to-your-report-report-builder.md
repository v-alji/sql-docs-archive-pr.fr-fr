---
title: 'Didacticiel : ajouter un graphique sparkline à un rapport (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 18c90a36-48bf-4805-a960-2d1e8f00c2dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb1bf83810b6c743b977e399864ce2edd514f572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704779"
---
# <a name="tutorial-add-a-sparkline-to-your-report-report-builder"></a><span data-ttu-id="ce02f-102">Didacticiel : ajouter un graphique sparkline à un rapport (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="ce02f-102">Tutorial: Add a Sparkline to Your Report (Report Builder)</span></span>
  <span data-ttu-id="ce02f-103">Dans ce didacticiel, vous allez créer un rapport de tableau de base reposant sur les exemples de données de vente, puis ajouter un graphique sparkline à une cellule du tableau.</span><span class="sxs-lookup"><span data-stu-id="ce02f-103">In this tutorial, you create a basic table report based on sample sales data, and then add a sparkline chart to a cell in the table.</span></span>  
  
 <span data-ttu-id="ce02f-104">Une version améliorée du rapport créé dans ce didacticiel est disponible sous forme d'exemple de rapport Générateur de rapports de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce02f-104">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="ce02f-105">Pour plus d’informations sur le téléchargement de cet exemple de rapport et d’autres, consultez [Générateur de rapports exemples de rapports](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="ce02f-105">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span> <span data-ttu-id="ce02f-106">L'illustration suivante montre l'exemple de rapport similaire à celui que vous allez créer.</span><span class="sxs-lookup"><span data-stu-id="ce02f-106">The following illustration shows the sample report similar to the one that you will create.</span></span>  
  
 <span data-ttu-id="ce02f-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span><span class="sxs-lookup"><span data-stu-id="ce02f-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span></span>  
  
 <span data-ttu-id="ce02f-108">La vidéo [Comment : créer un graphique sparkline dans une table (générateur de rapports vidéo)](https://technet.microsoft.com/bi/ff871942.aspx) illustre la création d’un rapport similaire avec des graphiques sparkline.</span><span class="sxs-lookup"><span data-stu-id="ce02f-108">The video [How to: Create a Sparkline in a Table (Report Builder Video)](https://technet.microsoft.com/bi/ff871942.aspx) illustrates how to create a similar report with sparklines.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="ce02f-109">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="ce02f-109">What You Will Learn</span></span>  
 <span data-ttu-id="ce02f-110">Dans ce didacticiel, vous apprendrez à effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce02f-110">In this tutorial, you will learn how to do the following:</span></span>  
  
 1. [<span data-ttu-id="ce02f-111">Créer un rapport avec un tableau</span><span class="sxs-lookup"><span data-stu-id="ce02f-111">Create a Report with a Table</span></span>](#CreateTable)  
  
 2. [<span data-ttu-id="ce02f-112">Créer une requête dans l'Assistant Tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="ce02f-112">Create a Query in the Table or Matrix Wizard</span></span>](#Query)  
  
 3. [<span data-ttu-id="ce02f-113">Ajouter un graphique sparkline au tableau</span><span class="sxs-lookup"><span data-stu-id="ce02f-113">Add a Sparkline to the Table</span></span>](#Sparkline)  
  
 4. [<span data-ttu-id="ce02f-114">Aligner les graphiques sparkline verticalement et horizontalement</span><span class="sxs-lookup"><span data-stu-id="ce02f-114">Align the Sparklines Vertically and Horizontally</span></span>](#AlignSparklines)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="ce02f-115">Autres étapes facultatives</span><span class="sxs-lookup"><span data-stu-id="ce02f-115">Other Optional Steps</span></span>  
 5. [<span data-ttu-id="ce02f-116">Mettre en forme les données en tant que devises</span><span class="sxs-lookup"><span data-stu-id="ce02f-116">Format Data as Currency</span></span>](#FormatCurrency)  
  
 6. [<span data-ttu-id="ce02f-117">Mettre en forme les données en tant que dates</span><span class="sxs-lookup"><span data-stu-id="ce02f-117">Format Data as Dates</span></span>](#FormatDates)  
  
 7. [<span data-ttu-id="ce02f-118">Modifier la largeur des colonnes</span><span class="sxs-lookup"><span data-stu-id="ce02f-118">Change Column Widths</span></span>](#Width)  
  
 8. [<span data-ttu-id="ce02f-119">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="ce02f-119">Add a Report Title</span></span>](#Title)  
  
 9. [<span data-ttu-id="ce02f-120">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="ce02f-120">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="ce02f-121">Durée estimée pour effectuer ce didacticiel : 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="ce02f-121">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce02f-122">Spécifications</span><span class="sxs-lookup"><span data-stu-id="ce02f-122">Requirements</span></span>  
 <span data-ttu-id="ce02f-123">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="ce02f-123">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-report-with-a-table"></a><a name="CreateTable"></a><span data-ttu-id="ce02f-124">1. créer un rapport avec une table</span><span class="sxs-lookup"><span data-stu-id="ce02f-124">1. Create a Report with a Table</span></span>  
  
#### <a name="to-create-a-report"></a><span data-ttu-id="ce02f-125">Pour créer un rapport</span><span class="sxs-lookup"><span data-stu-id="ce02f-125">To create a report</span></span>  
  
1.  <span data-ttu-id="ce02f-126">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur **Générateur de rapports Microsoft SQL Server 2012**, puis cliquez sur **Générateur de rapports version**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-126">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="ce02f-127">La boîte de dialogue **Mise en route** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="ce02f-127">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce02f-128">Si la boîte de dialogue **prise en main** n’apparaît pas, à partir du bouton **Générateur de rapports** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-128">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="ce02f-129">Dans le volet gauche, assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ce02f-129">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="ce02f-130">Dans le volet droit, cliquez sur **Assistant Tableau ou matrice**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-130">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="ce02f-131">Dans la page **Choisir un dataset** , sélectionnez **Créer un dataset**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-131">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="ce02f-132">La page **Choisir une connexion à une source de données** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="ce02f-132">The **Choose a connection to a data source** page opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce02f-133">Ce didacticiel n'a pas besoin de données spécifiques. Il a juste besoin d'une connexion à une base de données [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce02f-133">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="ce02f-134">Si une connexion est répertoriée sous **Connexions à la source de données**, vous pouvez la sélectionner et passer à l’étape 10.</span><span class="sxs-lookup"><span data-stu-id="ce02f-134">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to step 10.</span></span> <span data-ttu-id="ce02f-135">Pour plus d’informations, consultez [Autres manières d’obtenir une connexion de données &#40;Générateur de rapports&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="ce02f-135">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  <span data-ttu-id="ce02f-136">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-136">Click **New**.</span></span> <span data-ttu-id="ce02f-137">La boîte de dialogue **Propriétés de la source de données** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="ce02f-137">The **Data Source Properties** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="ce02f-138">Dans **Nom**, tapez **Ventes de produits**comme nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="ce02f-138">In **Name**, type **Product Sales**, a name for the data source.</span></span>  
  
7.  <span data-ttu-id="ce02f-139">Dans **Sélectionner un type de connexion**, assurez-vous que **Microsoft SQL Server** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ce02f-139">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
8.  <span data-ttu-id="ce02f-140">Dans **Chaîne de connexion**, tapez le texte suivant :</span><span class="sxs-lookup"><span data-stu-id="ce02f-140">In **Connection string**, type the following text:</span></span>  
  
     <span data-ttu-id="ce02f-141">**Source de données =\<servername>**</span><span class="sxs-lookup"><span data-stu-id="ce02f-141">**Data Source=\<servername>**</span></span>  
  
     <span data-ttu-id="ce02f-142">L’expression \<servername>, par exemple Rapport001, spécifie un ordinateur sur lequel une instance du moteur de base de données SQL Server est installée.</span><span class="sxs-lookup"><span data-stu-id="ce02f-142">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="ce02f-143">Dans la mesure où les données du rapport ne sont pas extraites d'une base de données SQL Server, vous n'avez pas besoin d'inclure le nom d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="ce02f-143">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="ce02f-144">La base de données par défaut sur le serveur spécifié est utilisée pour analyser la requête.</span><span class="sxs-lookup"><span data-stu-id="ce02f-144">The default database on the specified server is used to parse the query.</span></span>  
  
9. <span data-ttu-id="ce02f-145">Cliquez sur **Informations d'identification**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-145">Click **Credentials**.</span></span> <span data-ttu-id="ce02f-146">Entrez les informations d'identification nécessaires pour accéder à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="ce02f-146">Enter the credentials that you need to access the external data source.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="ce02f-147">Vous revenez à la page **Choisir une connexion à une source de données** .</span><span class="sxs-lookup"><span data-stu-id="ce02f-147">You are back on the **Choose a connection to a data source** page.</span></span>  
  
11. <span data-ttu-id="ce02f-148">Pour vous assurer que vous pouvez vous connecter à la source de données, cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-148">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="ce02f-149">Le message « La connexion a été correctement créée » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="ce02f-149">The message "Connection created successfully" appears.</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="ce02f-150">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-150">Click **Next**.</span></span>  
  
##  <a name="2-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="ce02f-151">2. créer une requête dans l’Assistant Tableau</span><span class="sxs-lookup"><span data-stu-id="ce02f-151">2. Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="ce02f-152">Dans un rapport, vous pouvez utiliser un dataset partagé qui comprend une requête prédéfinie, ou vous pouvez créer un dataset incorporé utilisable uniquement dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-152">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="ce02f-153">Dans ce didacticiel, vous allez créer un dataset incorporé.</span><span class="sxs-lookup"><span data-stu-id="ce02f-153">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce02f-154">Dans ce didacticiel, la requête contient les valeurs de données, afin qu'il ne soit pas nécessaire de disposer d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="ce02f-154">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="ce02f-155">Cela rend la requête assez longue.</span><span class="sxs-lookup"><span data-stu-id="ce02f-155">This makes the query quite long.</span></span> <span data-ttu-id="ce02f-156">Dans un environnement métier, une requête ne contient pas les données.</span><span class="sxs-lookup"><span data-stu-id="ce02f-156">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="ce02f-157">Ceci est nécessaire à des fins de formation uniquement.</span><span class="sxs-lookup"><span data-stu-id="ce02f-157">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="ce02f-158">Pour créer une requête</span><span class="sxs-lookup"><span data-stu-id="ce02f-158">To create a query</span></span>  
  
1.  <span data-ttu-id="ce02f-159">Dans la page **Créer une requête** , le concepteur de requêtes relationnelles est ouvert.</span><span class="sxs-lookup"><span data-stu-id="ce02f-159">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="ce02f-160">Pour ce didacticiel, vous utiliserez le Concepteur de requêtes textuel.</span><span class="sxs-lookup"><span data-stu-id="ce02f-160">For this tutorial, you will use the text-based query designer.</span></span>  
  
2.  <span data-ttu-id="ce02f-161">Cliquez sur **modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-161">Click **Edit As Text**.</span></span> <span data-ttu-id="ce02f-162">Le Concepteur de requêtes textuel affiche un volet de requête et un volet de résultats.</span><span class="sxs-lookup"><span data-stu-id="ce02f-162">The text-based query designer displays a query pane and a results pane.</span></span>  
  
3.  <span data-ttu-id="ce02f-163">Collez la requête [!INCLUDE[tsql](../includes/tsql-md.md)] ci-après dans la zone **Requête** .</span><span class="sxs-lookup"><span data-stu-id="ce02f-163">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Budget Movie-Maker' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Slim Digital' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,'Accessories' as Subcategory,    
       'Budget Movie-Maker' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2010-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Carrying Case' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
4.  <span data-ttu-id="ce02f-164">Dans la barre d’outils du Concepteur de requêtes, cliquez sur Exécuter (**!**).</span><span class="sxs-lookup"><span data-stu-id="ce02f-164">On the query designer toolbar, click Run  (**!**).</span></span>  
  
     <span data-ttu-id="ce02f-165">La requête s’exécute et affiche le jeu de résultats pour les champs **SalesDate**, **Subcategory**, **Product**, **Sales**et **Quantity**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-165">The query runs and displays the result set for the fields **SalesDate**, **Subcategory**, **Product**, **Sales**, and **Quantity**.</span></span>  
  
5.  <span data-ttu-id="ce02f-166">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-166">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="ce02f-167">Dans la page **Organiser les champs** , faites glisser **Sales** vers **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-167">On the **Arrange fields** page, drag **Sales** to **Values**.</span></span>  
  
     <span data-ttu-id="ce02f-168">**Sales** est agrégé par la fonction Sum.</span><span class="sxs-lookup"><span data-stu-id="ce02f-168">**Sales** is aggregated by the Sum function.</span></span> <span data-ttu-id="ce02f-169">La valeur est [Sum(Sales)].</span><span class="sxs-lookup"><span data-stu-id="ce02f-169">The value is [Sum(Sales)].</span></span>  
  
7.  <span data-ttu-id="ce02f-170">Faites glisser **Product** vers **Groupes de lignes**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-170">Drag **Product** to **Row groups**.</span></span>  
  
8.  <span data-ttu-id="ce02f-171">Faites glisser **SalesDate** vers **Groupes de colonnes**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-171">Drag **SalesDate** to **Column groups**.</span></span>  
  
9. <span data-ttu-id="ce02f-172">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-172">Click **Next**.</span></span>  
  
10. <span data-ttu-id="ce02f-173">Dans la page **Choisir la disposition** , sous **Options**, vérifiez que **Afficher les sous-totaux et les totaux généraux** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ce02f-173">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="ce02f-174">Le volet Aperçu de l'Assistant affiche un tableau avec trois lignes.</span><span class="sxs-lookup"><span data-stu-id="ce02f-174">The wizard Preview pane displays a table with three rows.</span></span> <span data-ttu-id="ce02f-175">Lorsque vous exécutez le rapport, chaque ligne est affichée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="ce02f-175">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="ce02f-176">La première ligne apparaît une fois pour le tableau afin d'afficher les en-têtes de colonnes.</span><span class="sxs-lookup"><span data-stu-id="ce02f-176">The first row will appear once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="ce02f-177">La deuxième ligne est répétée une fois pour chaque produit et affiche le nom du produit, le total par jour et le total de ligne.</span><span class="sxs-lookup"><span data-stu-id="ce02f-177">The second row will repeat once for each product and display the product name, total per day, and line total.</span></span>  
  
    3.  <span data-ttu-id="ce02f-178">La troisième ligne apparaît une fois pour le tableau afin d'afficher les totaux généraux.</span><span class="sxs-lookup"><span data-stu-id="ce02f-178">The third row will appear once for the table to display the grand totals.</span></span>  
  
11. <span data-ttu-id="ce02f-179">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-179">Click **Next**.</span></span>  
  
12. <span data-ttu-id="ce02f-180">Dans la page **Choisir un style** , dans le volet **Styles** , sélectionnez **Ardoise**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-180">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>  
  
     <span data-ttu-id="ce02f-181">Le volet Aperçu affiche un aperçu du tableau avec ce style.</span><span class="sxs-lookup"><span data-stu-id="ce02f-181">The Preview pane displays a sample of the table with that style.</span></span>  
  
13. <span data-ttu-id="ce02f-182">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-182">Click **Finish**.</span></span>  
  
14. <span data-ttu-id="ce02f-183">Le tableau est ajouté à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="ce02f-183">The table is added to the design surface.</span></span> <span data-ttu-id="ce02f-184">Il comporte trois colonnes et trois lignes.</span><span class="sxs-lookup"><span data-stu-id="ce02f-184">The table has three columns and three rows.</span></span>  
  
     <span data-ttu-id="ce02f-185">Recherchez le volet de regroupement.</span><span class="sxs-lookup"><span data-stu-id="ce02f-185">Look in the Grouping pane.</span></span> <span data-ttu-id="ce02f-186">S’il n’est pas visible, dans le menu **Affichage** , cliquez sur **Regroupement**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-186">If you can't see the Grouping pane, on the **View** menu, click **Grouping**.</span></span> <span data-ttu-id="ce02f-187">Le volet Groupes de lignes affiche un groupe de lignes : **Product**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-187">The Row Groups pane shows one row group: **Product**.</span></span> <span data-ttu-id="ce02f-188">Le volet Groupes de colonnes affiche un groupe de colonnes : **SalesDate**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-188">The Column Groups pane shows one column group: **SalesDate**.</span></span> <span data-ttu-id="ce02f-189">Les données de détail sont toutes les données récupérées par la requête de dataset.</span><span class="sxs-lookup"><span data-stu-id="ce02f-189">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
15. <span data-ttu-id="ce02f-190">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-190">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-add-a-sparkline"></a><a name="Sparkline"></a><span data-ttu-id="ce02f-191">3. Ajouter un graphique sparkline</span><span class="sxs-lookup"><span data-stu-id="ce02f-191">3. Add a Sparkline</span></span>  
  
#### <a name="to-add-a-sparkline-chart-to-a-table"></a><span data-ttu-id="ce02f-192">Pour ajouter un graphique sparkline à un tableau</span><span class="sxs-lookup"><span data-stu-id="ce02f-192">To add a sparkline chart to a table</span></span>  
  
1.  <span data-ttu-id="ce02f-193">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="ce02f-193">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="ce02f-194">Sélectionnez la colonne Total de votre tableau.</span><span class="sxs-lookup"><span data-stu-id="ce02f-194">Select the Total column in your table.</span></span>  
  
3.  <span data-ttu-id="ce02f-195">Cliquez avec le bouton droit, pointez sur **Insérer une colonne**, puis cliquez sur **Gauche**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-195">Right-click, point to **Insert Column**, and then click **Left**.</span></span>  
  
4.  <span data-ttu-id="ce02f-196">Dans la nouvelle colonne, cliquez avec le bouton droit sur la ligne [Product], pointez sur l’onglet **Insérer** un ruban, puis cliquez sur **graphique sparkline**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-196">In the new column, right-click in the [Product] row, point to the **Insert** ribbon tab, and then click **Sparkline**.</span></span>  
  
5.  <span data-ttu-id="ce02f-197">Assurez-vous que le premier graphique sparkline de la ligne **colonne** est sélectionné, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-197">Make sure the first sparkline in the **Column** row is selected and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="ce02f-198">Cliquez sur le graphique sparkline pour afficher le volet Données du graphique.</span><span class="sxs-lookup"><span data-stu-id="ce02f-198">Click the sparkline to show the Chart Data pane.</span></span>  
  
7.  <span data-ttu-id="ce02f-199">Cliquez sur le signe plus (+) dans la zone valeurs, puis cliquez sur **Sales**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-199">Click the plus (+) sign in the Values box, and then click **Sales**.</span></span>  
  
     <span data-ttu-id="ce02f-200">Les valeurs du champ **Sales** sont maintenant les valeurs du graphique sparkline.</span><span class="sxs-lookup"><span data-stu-id="ce02f-200">The values in the **Sales** field are now the values for the sparkline.</span></span>  
  
8.  <span data-ttu-id="ce02f-201">Cliquez sur le signe plus (+) dans la zone groupes de catégories, puis cliquez sur **DateVente**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-201">Click the plus (+) sign in the Category Groups box, and then click **SalesDate**.</span></span>  
  
9. <span data-ttu-id="ce02f-202">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-202">Click **Run** to preview your report.</span></span>  
  
     <span data-ttu-id="ce02f-203">Notez que des graphiques sparkline sont présents dans chaque ligne du tableau, mais qu'ils ne sont pas corrects.</span><span class="sxs-lookup"><span data-stu-id="ce02f-203">Note that there are sparkline charts in each row of the table, but they're not correct.</span></span> <span data-ttu-id="ce02f-204">Les barres des graphiques ne sont pas alignées les unes par rapport aux autres.</span><span class="sxs-lookup"><span data-stu-id="ce02f-204">The bars in the charts don't line up with each other.</span></span> <span data-ttu-id="ce02f-205">Il n'y a que quatre barres dans la seconde ligne de données, ce qui fait qu'elles sont plus larges que les barres de la première ligne, qui en a six.</span><span class="sxs-lookup"><span data-stu-id="ce02f-205">There are only four bars in the second row of data, so the bars are wider than the bars in the first row, which has six.</span></span> <span data-ttu-id="ce02f-206">Vous ne pouvez pas comparer les valeurs de chaque produit par jour.</span><span class="sxs-lookup"><span data-stu-id="ce02f-206">You can't compare values for each product per day.</span></span> <span data-ttu-id="ce02f-207">Elles doivent être alignées les unes par rapport aux autres.</span><span class="sxs-lookup"><span data-stu-id="ce02f-207">They need to line up with each other.</span></span>  
  
     <span data-ttu-id="ce02f-208">Notez également que pour chaque ligne, la barre la plus grande correspond à la hauteur de la ligne.</span><span class="sxs-lookup"><span data-stu-id="ce02f-208">Also note that for each row, the tallest bar for that row is the height of the row.</span></span> <span data-ttu-id="ce02f-209">Cela est également trompeur, car les valeurs les plus élevées pour chaque ligne ne sont pas égales : la plus grande valeur pour le fabricant de films de budget est $10 400, mais la plus grande valeur pour Compact Digital est $26 576-plus de deux fois plus grand.</span><span class="sxs-lookup"><span data-stu-id="ce02f-209">This is misleading, too, because the largest values for each row are not equal: the largest value for Budget Movie-Maker is $10,400, but the largest value for Slim Digital is $26,576-more than twice as large.</span></span> <span data-ttu-id="ce02f-210">Or les barres les plus grandes pour ces deux lignes ont pratiquement la même hauteur.</span><span class="sxs-lookup"><span data-stu-id="ce02f-210">And yet the largest bars in those two rows are about the same height.</span></span> <span data-ttu-id="ce02f-211">Il faut donc également les mettre à la même échelle que les autres graphiques sparkline.</span><span class="sxs-lookup"><span data-stu-id="ce02f-211">That also needs to be made to scale with the other sparklines.</span></span>  
  
     <span data-ttu-id="ce02f-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span><span class="sxs-lookup"><span data-stu-id="ce02f-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span></span>  
  
##  <a name="4-align-the-sparklines-vertically-and-horizontally"></a><a name="AlignSparklines"></a><span data-ttu-id="ce02f-213">4. Aligner les graphiques sparkline verticalement et horizontalement</span><span class="sxs-lookup"><span data-stu-id="ce02f-213">4. Align the Sparklines Vertically and Horizontally</span></span>  
 <span data-ttu-id="ce02f-214">Les graphiques sparkline sont difficiles à lire lorsqu’ils n’utilisent pas tous les mêmes mesures.</span><span class="sxs-lookup"><span data-stu-id="ce02f-214">The sparklines are hard to read when they don't all use the same measurements.</span></span> <span data-ttu-id="ce02f-215">Les axes horizontal et vertical doivent chacun correspondre au reste.</span><span class="sxs-lookup"><span data-stu-id="ce02f-215">Both the horizontal and vertical axes for each need to match the rest.</span></span>  
  
#### <a name="to-set-alignment-for-the-sparklines-in-the-table"></a><span data-ttu-id="ce02f-216">Pour définir l'alignement des graphiques sparkline dans le tableau</span><span class="sxs-lookup"><span data-stu-id="ce02f-216">To set alignment for the sparklines in the table</span></span>  
  
1.  <span data-ttu-id="ce02f-217">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="ce02f-217">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="ce02f-218">Cliquez avec le bouton droit sur le graphique sparkline, puis cliquez sur **Propriétés de l’axe vertical**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-218">Right-click the sparkline and click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="ce02f-219">Cochez la case **Aligner les axes dans** .</span><span class="sxs-lookup"><span data-stu-id="ce02f-219">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="ce02f-220">Tablix1 est affiché dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ce02f-220">Tablix1 is showing in the list.</span></span> <span data-ttu-id="ce02f-221">Il s'agit de la seule option.</span><span class="sxs-lookup"><span data-stu-id="ce02f-221">That is the only option.</span></span> <span data-ttu-id="ce02f-222">Elle permet de définir la hauteur des barres de chaque graphique sparkline par rapport aux autres.</span><span class="sxs-lookup"><span data-stu-id="ce02f-222">This sets the height of the bars in each sparkline relative to the others.</span></span>  
  
4.  <span data-ttu-id="ce02f-223">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-223">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="ce02f-224">Cliquez avec le bouton droit sur le graphique sparkline, puis cliquez sur **Propriétés de l’axe horizontal**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-224">Right-click the sparkline and click **Horizontal Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="ce02f-225">Cochez la case **Aligner les axes dans** .</span><span class="sxs-lookup"><span data-stu-id="ce02f-225">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="ce02f-226">Tablix1 est affiché dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ce02f-226">Tablix1 is showing in the list.</span></span> <span data-ttu-id="ce02f-227">Il s'agit de la seule option.</span><span class="sxs-lookup"><span data-stu-id="ce02f-227">That is the only option.</span></span> <span data-ttu-id="ce02f-228">Elle permet de définir la largeur des barres de chaque graphique sparkline par rapport aux autres.</span><span class="sxs-lookup"><span data-stu-id="ce02f-228">This sets the width of the bars in each sparkline relative to the others.</span></span> <span data-ttu-id="ce02f-229">Si certains graphiques sparkline possèdent moins de barres que d'autres, ils présenteront alors des espaces vides pour les données manquantes.</span><span class="sxs-lookup"><span data-stu-id="ce02f-229">If some sparklines have fewer bars than others, then those sparklines will have blank spaces for the missing data.</span></span>  
  
7.  <span data-ttu-id="ce02f-230">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-230">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="ce02f-231">Cliquez sur **Exécuter** pour afficher un nouvel aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-231">Click **Run** to preview your report again.</span></span>  
  
 <span data-ttu-id="ce02f-232">Notez que toutes les barres sont maintenant alignées sur les barres des autres lignes.</span><span class="sxs-lookup"><span data-stu-id="ce02f-232">Note that all the bars are now aligned with the bars in the other rows.</span></span>  
  
##  <a name="5-optional-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="ce02f-233">5. (facultatif) mettre en forme les données en tant que devise</span><span class="sxs-lookup"><span data-stu-id="ce02f-233">5. (Optional) Format Data as Currency</span></span>  
 <span data-ttu-id="ce02f-234">Par défaut, les données de synthèse du champ **Sales** affichent un nombre général.</span><span class="sxs-lookup"><span data-stu-id="ce02f-234">By default, the summary data for the **Sales** field displays a general number.</span></span> <span data-ttu-id="ce02f-235">Appliquez une mise en forme pour afficher ce nombre dans un format monétaire.</span><span class="sxs-lookup"><span data-stu-id="ce02f-235">Format it to display the number as currency.</span></span> <span data-ttu-id="ce02f-236">Activez/désactivez **Styles des espaces réservés** pour afficher les zones de texte mises en forme et le texte de l’espace réservé en tant qu’exemples de valeurs.</span><span class="sxs-lookup"><span data-stu-id="ce02f-236">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="ce02f-237">Pour mettre en forme un champ monétaire</span><span class="sxs-lookup"><span data-stu-id="ce02f-237">To format a currency field</span></span>  
  
1.  <span data-ttu-id="ce02f-238">Cliquez sur **Conception** pour basculer en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="ce02f-238">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="ce02f-239">Cliquez sur la cellule de la deuxième ligne (sous la ligne des en-têtes de colonne) dans la colonne **DateVente** , puis faites glisser pour sélectionner toutes les cellules qui contiennent `[Sum(Sales)]` .</span><span class="sxs-lookup"><span data-stu-id="ce02f-239">Click the cell in the second row (under the column headings row) in the **SalesDate** column and drag to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="ce02f-240">Sous l’onglet **Accueil** , dans le groupe **Nombre** , cliquez sur le bouton **Devise** .</span><span class="sxs-lookup"><span data-stu-id="ce02f-240">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="ce02f-241">Les cellules changent pour afficher le format de devise.</span><span class="sxs-lookup"><span data-stu-id="ce02f-241">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="ce02f-242">Si votre paramètre régional est Anglais (États-Unis), le texte d’exemple par défaut est [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="ce02f-242">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="ce02f-243">Si vous ne voyez pas d’exemple de valeur monétaire, cliquez sur **styles des espaces réservés** dans le groupe **nombres** , puis cliquez sur **exemples de valeurs**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-243">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="ce02f-244">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-244">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="ce02f-245">Les valeurs de synthèse des **ventes** sont affichées sous forme de devise.</span><span class="sxs-lookup"><span data-stu-id="ce02f-245">The summary values for **Sales** display as currency.</span></span>  
  
##  <a name="6-optional-format-data-as-dates"></a><a name="FormatDates"></a><span data-ttu-id="ce02f-246">6. (facultatif) mettre en forme les données en tant que dates</span><span class="sxs-lookup"><span data-stu-id="ce02f-246">6. (Optional) Format Data as Dates</span></span>  
 <span data-ttu-id="ce02f-247">Par défaut, le champ **DateVente** affiche à la fois les informations de date et d’heure.</span><span class="sxs-lookup"><span data-stu-id="ce02f-247">By default, the **SalesDate** field displays both date and time information.</span></span> <span data-ttu-id="ce02f-248">Vous pouvez le mettre en forme de sorte qu'il n'affiche que la date.</span><span class="sxs-lookup"><span data-stu-id="ce02f-248">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="ce02f-249">Pour appliquer à un champ de date le format par défaut</span><span class="sxs-lookup"><span data-stu-id="ce02f-249">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="ce02f-250">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="ce02f-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="ce02f-251">Cliquez sur la cellule qui contient `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="ce02f-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="ce02f-252">Dans le ruban, sous l’onglet dossier de **démarrage** , dans le groupe **nombre** , dans la liste déroulante, sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-252">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="ce02f-253">La cellule affiche l’exemple de date **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-253">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="ce02f-254">Si vous ne voyez pas s’afficher d’exemple de date, cliquez sur **Styles des espaces réservés** dans le groupe **Nombres** , puis cliquez sur **Valeurs d’aperçu**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-254">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="ce02f-255">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-255">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="ce02f-256">Les valeurs **DateVente** sont affichées dans le format de date par défaut.</span><span class="sxs-lookup"><span data-stu-id="ce02f-256">The **SalesDate** values display in the default date format.</span></span>  
  
##  <a name="7-optional-change-column-widths"></a><a name="Width"></a><span data-ttu-id="ce02f-257">7. (facultatif) modifier la largeur des colonnes</span><span class="sxs-lookup"><span data-stu-id="ce02f-257">7. (Optional) Change Column Widths</span></span>  
 <span data-ttu-id="ce02f-258">Par défaut, chaque cellule d'un tableau contient une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="ce02f-258">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="ce02f-259">Une zone de texte s'étend verticalement pour accueillir le texte lors du rendu de la page.</span><span class="sxs-lookup"><span data-stu-id="ce02f-259">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="ce02f-260">Dans le rapport rendu, chaque ligne s'étend en fonction de la hauteur de la plus grande zone de texte rendue dans la ligne.</span><span class="sxs-lookup"><span data-stu-id="ce02f-260">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="ce02f-261">La hauteur de la ligne dans l'aire de conception n'a aucun impact sur la hauteur de la ligne dans le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="ce02f-261">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="ce02f-262">Pour réduire l'espace vertical occupé par chaque ligne, augmentez la largeur de colonne afin d'accueillir le contenu attendu des zones de texte dans la colonne sur une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="ce02f-262">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-columns"></a><span data-ttu-id="ce02f-263">Pour modifier la largeur des colonnes</span><span class="sxs-lookup"><span data-stu-id="ce02f-263">To change the width of columns</span></span>  
  
1.  <span data-ttu-id="ce02f-264">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="ce02f-264">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="ce02f-265">Cliquez sur la table pour que les poignées de ligne et de colonne apparaissent au-dessus et à côté de la table.</span><span class="sxs-lookup"><span data-stu-id="ce02f-265">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="ce02f-266">Les barres grises le long du haut et du côté de la table sont les poignées de colonne et de ligne.</span><span class="sxs-lookup"><span data-stu-id="ce02f-266">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="ce02f-267">Placez le curseur entre les séparateurs de colonne pour qu'il se transforme en flèche à deux pointes.</span><span class="sxs-lookup"><span data-stu-id="ce02f-267">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="ce02f-268">Faites glisser les colonnes pour les redimensionner.</span><span class="sxs-lookup"><span data-stu-id="ce02f-268">Drag the columns to the size you want.</span></span> <span data-ttu-id="ce02f-269">Par exemple, développez la colonne **produit** afin que le nom du produit s’affiche sur une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="ce02f-269">For example, expand the column for **Product** so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="ce02f-270">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-270">Click **Run** to preview your report.</span></span>  
  
##  <a name="8-optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="ce02f-271">8. (facultatif) ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="ce02f-271">8. (Optional) Add a Report Title</span></span>  
 <span data-ttu-id="ce02f-272">Un titre de rapport s'affiche dans la partie supérieure du rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-272">A report title appears at the top of the report.</span></span> <span data-ttu-id="ce02f-273">Vous pouvez placer le titre du rapport dans un en-tête de rapport, ou si le rapport n'en utilise pas, dans une zone de texte située en haut du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-273">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="ce02f-274">Dans ce didacticiel, vous allez utiliser la zone de texte placée automatiquement en haut du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-274">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="ce02f-275">Vous pouvez améliorer le texte en appliquant différents types de styles de police, de tailles et de couleurs à des expressions et des caractères spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ce02f-275">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="ce02f-276">Pour plus d’informations, consultez [Mettre en forme du texte dans une zone de texte &#40;Générateur de rapports et SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ce02f-276">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="ce02f-277">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="ce02f-277">To add a report title</span></span>  
  
1.  <span data-ttu-id="ce02f-278">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-278">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="ce02f-279">Tapez **Product Sales**, puis cliquez à l’extérieur de la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="ce02f-279">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="ce02f-280">Cliquez avec le bouton droit sur la zone de texte qui contient **Product Sales** , puis cliquez sur **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-280">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="ce02f-281">Dans la boîte de dialogue **Propriétés de la zone de texte** , cliquez sur **Police**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-281">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="ce02f-282">Dans la liste **Taille** , sélectionnez **18pt**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-282">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="ce02f-283">Dans la liste **couleur** , sélectionnez **marron**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-283">In the **Color** list, select **Maroon**.</span></span>  
  
7.  <span data-ttu-id="ce02f-284">Sélectionnez **Gras**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-284">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="ce02f-285">9. enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="ce02f-285">9. Save the Report</span></span>  
 <span data-ttu-id="ce02f-286">Enregistrez le rapport sur un serveur de rapports ou sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ce02f-286">Save the report to a report server or your computer.</span></span> <span data-ttu-id="ce02f-287">Si vous n'enregistrez pas le rapport sur le serveur de rapports, plusieurs fonctionnalités de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] telles que les parties de rapports et les sous-rapports ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="ce02f-287">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="ce02f-288">Pour enregistrer le rapport sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="ce02f-288">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="ce02f-289">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-289">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="ce02f-290">Cliquez sur **Sites et serveurs récents**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-290">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="ce02f-291">Sélectionnez ou tapez le nom du serveur de rapports sur lequel vous êtes autorisé à enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="ce02f-291">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="ce02f-292">Le message « Connexion au serveur de rapports » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="ce02f-292">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="ce02f-293">Une fois la connexion établie, le contenu du dossier de rapports spécifié par l'administrateur du serveur de rapports s'affiche comme emplacement par défaut des rapports.</span><span class="sxs-lookup"><span data-stu-id="ce02f-293">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="ce02f-294">Dans **Nom**, remplacez le nom par défaut par **Ventes de produits**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-294">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="ce02f-295">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-295">Click **Save**.</span></span>  
  
 <span data-ttu-id="ce02f-296">Le rapport est enregistré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ce02f-296">The report is saved to the report server.</span></span> <span data-ttu-id="ce02f-297">Le nom du serveur de rapports auquel vous êtes connecté est indiqué dans la barre d'état située au bas de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="ce02f-297">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="ce02f-298">Pour enregistrer le rapport sur votre ordinateur</span><span class="sxs-lookup"><span data-stu-id="ce02f-298">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="ce02f-299">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-299">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="ce02f-300">Cliquez sur **Bureau**, **Mes documents**ou **Poste de travail**, puis naviguez jusqu’au dossier où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="ce02f-300">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="ce02f-301">Dans **Nom**, remplacez le nom par défaut par **Ventes de produits**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-301">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="ce02f-302">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ce02f-302">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ce02f-303">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="ce02f-303">Next Steps</span></span>  
 <span data-ttu-id="ce02f-304">Ainsi s'achève le didacticiel de création d'un rapport de tableau avec des graphiques sparkline.</span><span class="sxs-lookup"><span data-stu-id="ce02f-304">This concludes the tutorial for creating a table report with sparkline charts.</span></span> <span data-ttu-id="ce02f-305">Pour plus d’informations sur ces graphiques sparkline, consultez [Graphiques sparkline et barres de données &#40;Générateur de rapports et SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ce02f-305">For more information about sparklines, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce02f-306">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce02f-306">See Also</span></span>  
 <span data-ttu-id="ce02f-307">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="ce02f-307">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="ce02f-308">Générateur de rapports dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ce02f-308">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
