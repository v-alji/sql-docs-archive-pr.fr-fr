---
title: 'Didacticiel : ajouter un graphique à barres à un rapport (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6956ebd6-0217-4087-a4fa-5cc1c3804691
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01708ca548c40118daa03fac34d8a323d628b012
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603811"
---
# <a name="tutorial-add-a-bar-chart-to-your-report-report-builder"></a><span data-ttu-id="1785e-102">Didacticiel : ajouter un graphique à barres à un rapport (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="1785e-102">Tutorial: Add a Bar Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="1785e-103">Un graphique à barres représente les données de catégorie horizontalement.</span><span class="sxs-lookup"><span data-stu-id="1785e-103">A bar chart displays category data horizontally.</span></span> <span data-ttu-id="1785e-104">Cela peut aider à :</span><span class="sxs-lookup"><span data-stu-id="1785e-104">This can help to:</span></span>  
  
-   <span data-ttu-id="1785e-105">améliorer la lisibilité des noms de catégorie longs ;</span><span class="sxs-lookup"><span data-stu-id="1785e-105">Improve readability of long category names.</span></span>  
  
-   <span data-ttu-id="1785e-106">améliorer la compréhension des heures représentées sous forme de valeurs ;</span><span class="sxs-lookup"><span data-stu-id="1785e-106">Improve understandability of times plotted as values.</span></span>  
  
-   <span data-ttu-id="1785e-107">comparer la valeur relative de plusieurs séries.</span><span class="sxs-lookup"><span data-stu-id="1785e-107">Compare the relative value of multiple series.</span></span>  
  
 <span data-ttu-id="1785e-108">L'illustration suivante montre le graphique à barres que vous allez créer, avec les ventes de 2008 et 2009 pour les cinq meilleurs commerciaux, par ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="1785e-108">The following illustration shows the bar chart that you will create, with sales for 2008 and 2009 for the top five salespeople, in alphabetical order.</span></span>  
  
 <span data-ttu-id="1785e-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span><span class="sxs-lookup"><span data-stu-id="1785e-109">![rs_BarChartTutorial](../../2014/tutorials/media/rs-barcharttutorial.gif "rs_BarChartTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="1785e-110">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="1785e-110">What You Will Learn</span></span>  
 <span data-ttu-id="1785e-111">Dans ce didacticiel, vous apprendrez à effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1785e-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="1785e-112">Créer un graphique à partir de l'Assistant Graphique</span><span class="sxs-lookup"><span data-stu-id="1785e-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="1785e-113">Choisir le type de graphique</span><span class="sxs-lookup"><span data-stu-id="1785e-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="1785e-114">Afficher toutes les valeurs des catégories sur l'axe vertical</span><span class="sxs-lookup"><span data-stu-id="1785e-114">Display all Category Values on the Vertical Axis</span></span>](#AllValues)  
  
4.  [<span data-ttu-id="1785e-115">Modifier l'affichage des noms sur l'axe vertical</span><span class="sxs-lookup"><span data-stu-id="1785e-115">Modify the Display of Names on the Vertical Axis</span></span>](#Sort)  
  
5.  [<span data-ttu-id="1785e-116">Déplacer la légende</span><span class="sxs-lookup"><span data-stu-id="1785e-116">Move the Legend</span></span>](#Legend)  
  
6.  [<span data-ttu-id="1785e-117">Déplacer le titre du graphique</span><span class="sxs-lookup"><span data-stu-id="1785e-117">Move the Chart Title</span></span>](#ChartTitle)  
  
7.  [<span data-ttu-id="1785e-118">Mettre en forme et étiqueter l'axe horizontal</span><span class="sxs-lookup"><span data-stu-id="1785e-118">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
8.  [<span data-ttu-id="1785e-119">Ajouter un filtre pour afficher les cinq valeurs supérieures</span><span class="sxs-lookup"><span data-stu-id="1785e-119">Add a Filter to Display the Top Five Values</span></span>](#Filter)  
  
9. [<span data-ttu-id="1785e-120">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="1785e-120">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="1785e-121">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="1785e-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="1785e-122">Dans ce didacticiel, les étapes de l'Assistant sont consolidées en une seule procédure.</span><span class="sxs-lookup"><span data-stu-id="1785e-122">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="1785e-123">Pour obtenir des instructions pas à pas sur l’accès à un serveur de rapports, la création d’un dataset et le choix d’une source de données, consultez le premier didacticiel de cette série : [Didacticiel : création d’un rapport de tableau de base &#40;Générateur de rapports&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="1785e-123">For step-by-step instructions about how to browse to a report server, create a dataset, and choose a data source, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="1785e-124">Durée estimée pour effectuer ce didacticiel : 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="1785e-124">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1785e-125">Spécifications</span><span class="sxs-lookup"><span data-stu-id="1785e-125">Requirements</span></span>  
 <span data-ttu-id="1785e-126">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="1785e-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="1785e-127">1. créer un rapport de graphique à partir de l’Assistant graphique</span><span class="sxs-lookup"><span data-stu-id="1785e-127">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="1785e-128">Dans la boîte de dialogue **prise en main** , créez un dataset incorporé, choisissez une source de données partagée et créez un graphique à barres à l’aide de l’Assistant graphique.</span><span class="sxs-lookup"><span data-stu-id="1785e-128">From the **Getting Started** dialog box, create an embedded dataset, choose a shared data source, and create a bar chart by using the Chart Wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1785e-129">Dans ce didacticiel, la requête contient les valeurs des données : elle n’a donc pas besoin d’une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="1785e-129">In this tutorial, the query contains the data values so that it does not need an external data source.</span></span> <span data-ttu-id="1785e-130">Cela rend la requête assez longue.</span><span class="sxs-lookup"><span data-stu-id="1785e-130">This makes the query quite long.</span></span> <span data-ttu-id="1785e-131">Dans un environnement métier, une requête ne contient pas les données.</span><span class="sxs-lookup"><span data-stu-id="1785e-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="1785e-132">Ceci est nécessaire à des fins de formation uniquement.</span><span class="sxs-lookup"><span data-stu-id="1785e-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="1785e-133">Pour créer un rapport de graphique</span><span class="sxs-lookup"><span data-stu-id="1785e-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="1785e-134">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur **Générateur de rapports Microsoft SQL Server 2012**, puis cliquez sur **Générateur de rapports version**.</span><span class="sxs-lookup"><span data-stu-id="1785e-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="1785e-135">La boîte de dialogue **prise en main** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1785e-135">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1785e-136">Si la boîte de dialogue **prise en main** ne s’affiche pas, cliquez sur le bouton Générateur de rapports, puis cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1785e-136">If the **Getting Started** dialog box does not appear, click the Report Builder button, and then click **New**.</span></span>  
  
2.  <span data-ttu-id="1785e-137">Dans le volet gauche, assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1785e-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="1785e-138">Dans le volet droit, cliquez sur **Assistant Graphique**.</span><span class="sxs-lookup"><span data-stu-id="1785e-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="1785e-139">Dans la page **choisir un DataSet** , cliquez sur **créer un DataSet**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="1785e-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="1785e-140">Dans la page **Choisir une connexion à une source de données** , sélectionnez une source de données existante ou naviguez jusqu’au serveur de rapports, sélectionnez une source de données, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1785e-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="1785e-141">Vous devrez peut-être entrer un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="1785e-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1785e-142">La source de données que vous choisissez n'a pas d'importance, tant que vous disposez des autorisations appropriées.</span><span class="sxs-lookup"><span data-stu-id="1785e-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="1785e-143">Vous n'allez pas récupérer de données à partir de la source de données.</span><span class="sxs-lookup"><span data-stu-id="1785e-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="1785e-144">Pour plus d’informations, consultez [Autres manières d’obtenir une connexion de données &#40;Générateur de rapports&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="1785e-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="1785e-145">Dans la page **Créer une requête** , cliquez sur **Modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="1785e-145">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="1785e-146">Collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="1785e-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Luis' as FirstName, 'Alverca' as LastName, CAST(170000.00 AS money) AS SalesYear2009, CAST(150000. AS money) AS SalesYear2008  
    UNION SELECT 'Jeffrey' as FirstName, 'Zeng' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(190000. AS money) AS SalesYear2008  
    UNION SELECT 'Houman' as FirstName, 'Pournasseh' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Robin' as FirstName, 'Wood' as LastName, CAST(75000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'Daniela' as FirstName, 'Guaita' as LastName,  CAST(170000. AS money) AS SalesYear2009, CAST(175000. AS money) AS SalesYear2008  
    UNION SELECT 'John' as FirstName, 'Yokim' as LastName, CAST(160000. AS money) AS SalesYear2009, CAST(195000. AS money) AS SalesYear2008  
    UNION SELECT 'Delphine' as FirstName, 'Ribaute' as LastName, CAST(180000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Robert' as FirstName, 'Hernady' as LastName, CAST(140000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Tanja' as FirstName, 'Plate' as LastName, CAST(150000. AS money) AS SalesYear2009, CAST(160000. AS money) AS SalesYear2008  
    UNION SELECT 'David' as FirstName, 'Bradley' as LastName, CAST(210000. AS money) AS SalesYear2009, CAST(180000. AS money) AS SalesYear2008  
    UNION SELECT 'Michal' as FirstName, 'Jaworski' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(220000. AS money) AS SalesYear2008  
    UNION SELECT 'Chris' as FirstName, 'Ashton' as LastName, CAST(195000. AS money) AS SalesYear2009, CAST(205000. AS money) AS SalesYear2008  
    UNION SELECT 'Pongsiri' as FirstName, 'Hirunyanitiwatna' as LastName, CAST(175000. AS money) AS SalesYear2009, CAST(215000. AS money) AS SalesYear2008  
    UNION SELECT 'Brian' as FirstName, 'Burke' as LastName, CAST(187000. AS money) AS SalesYear2009, CAST(207000. AS money) AS SalesYear2008  
    ```  
  
8.  <span data-ttu-id="1785e-147">(Facultatif) Cliquez sur le bouton Exécuter (**!**) pour voir les données sur lesquelles votre graphique sera basé.</span><span class="sxs-lookup"><span data-stu-id="1785e-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="1785e-148">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1785e-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="1785e-149">2. choisir le type de graphique</span><span class="sxs-lookup"><span data-stu-id="1785e-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="1785e-150">Vous avez le choix entre plusieurs types de graphiques prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="1785e-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="1785e-151">Pour ajouter un histogramme</span><span class="sxs-lookup"><span data-stu-id="1785e-151">To add a column chart</span></span>  
  
1.  <span data-ttu-id="1785e-152">Dans la page **Choisir un type de graphique** , l’histogramme est le type de graphique par défaut.</span><span class="sxs-lookup"><span data-stu-id="1785e-152">On the **Choose a chart type** page, the column chart is the default chart type.</span></span>  
  
2.  <span data-ttu-id="1785e-153">Cliquez sur **Barre**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1785e-153">Click **Bar**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="1785e-154">Dans la page **organiser les champs du graphique** , il y a quatre champs dans le volet **champs disponibles** : FirstName, LastName, SalesYear2009 et SalesYear2008.</span><span class="sxs-lookup"><span data-stu-id="1785e-154">On the **Arrange chart fields** page, there are four fields in the **Available fields** pane: FirstName, LastName, SalesYear2009, and SalesYear2008.</span></span>  
  
3.  <span data-ttu-id="1785e-155">Faites glisser LastName vers le volet Catégories.</span><span class="sxs-lookup"><span data-stu-id="1785e-155">Drag LastName to the Categories pane.</span></span>  
  
4.  <span data-ttu-id="1785e-156">Faites glisser SalesYear2009 vers le volet valeurs.</span><span class="sxs-lookup"><span data-stu-id="1785e-156">Drag SalesYear2009 to the Values pane.</span></span> <span data-ttu-id="1785e-157">SalesYear2009 représente le montant des ventes de chaque commercial pour l'année 2009.</span><span class="sxs-lookup"><span data-stu-id="1785e-157">SalesYear2009 represents the sales amount for each salesperson for the year 2009.</span></span> <span data-ttu-id="1785e-158">Le volet Valeurs affiche `[Sum(SalesYear2009)]` , car le graphique affiche l'agrégat pour chaque produit.</span><span class="sxs-lookup"><span data-stu-id="1785e-158">The Values pane displays `[Sum(SalesYear2009)]` because the chart displays the aggregate for each product.</span></span>  
  
5.  <span data-ttu-id="1785e-159">Faites glisser SalesYear2008 vers le volet valeurs sous SalesYear2009.</span><span class="sxs-lookup"><span data-stu-id="1785e-159">Drag SalesYear2008 to the Values pane under SalesYear2009.</span></span> <span data-ttu-id="1785e-160">SalesYear2008 représente le montant des ventes de chaque commercial pour l'année 2008.</span><span class="sxs-lookup"><span data-stu-id="1785e-160">SalesYear2008 represents the sales amount for each salesperson for the year 2008.</span></span>  
  
6.  <span data-ttu-id="1785e-161">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1785e-161">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="1785e-162">Dans la page **choisir un style** , dans le volet styles, sélectionnez un style.</span><span class="sxs-lookup"><span data-stu-id="1785e-162">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="1785e-163">Un style spécifie un style de police, un jeu de couleurs et un style de bordure.</span><span class="sxs-lookup"><span data-stu-id="1785e-163">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="1785e-164">Lorsque vous sélectionnez un style, le volet Aperçu affiche un aperçu du graphique avec ce style.</span><span class="sxs-lookup"><span data-stu-id="1785e-164">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
8.  <span data-ttu-id="1785e-165">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="1785e-165">Click **Finish**.</span></span>  
  
     <span data-ttu-id="1785e-166">Le graphique est ajouté à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="1785e-166">The chart is added to the design surface.</span></span>  
  
9. <span data-ttu-id="1785e-167">Cliquez sur le graphique pour afficher ses poignées.</span><span class="sxs-lookup"><span data-stu-id="1785e-167">Click the chart to display the chart handles.</span></span> <span data-ttu-id="1785e-168">Faites glisser l'angle inférieur droit du graphique pour augmenter sa taille.</span><span class="sxs-lookup"><span data-stu-id="1785e-168">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span>  
  
10. <span data-ttu-id="1785e-169">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1785e-170">Le rapport affiche le graphique à barres des ventes de chaque commercial pour les années 2008 et 2009.</span><span class="sxs-lookup"><span data-stu-id="1785e-170">The report displays the bar chart for sales for each sales person for the years 2008 and 2009.</span></span> <span data-ttu-id="1785e-171">La longueur de la barre correspond au total des ventes.</span><span class="sxs-lookup"><span data-stu-id="1785e-171">The length of the bar corresponds to the sales total.</span></span>  
  
##  <a name="3-modify-the-display-of-names-on-the-vertical-axis"></a><a name="AllValues"></a><span data-ttu-id="1785e-172">3. modifier l’affichage des noms sur l’axe vertical</span><span class="sxs-lookup"><span data-stu-id="1785e-172">3. Modify the Display of Names on the Vertical Axis</span></span>  
 <span data-ttu-id="1785e-173">Par défaut, seules quelques-unes des valeurs de l'axe vertical s'affichent.</span><span class="sxs-lookup"><span data-stu-id="1785e-173">By default, only some of the values on the vertical axis appear.</span></span> <span data-ttu-id="1785e-174">Vous pouvez modifier le graphique pour afficher toutes les catégories.</span><span class="sxs-lookup"><span data-stu-id="1785e-174">You can change the chart to display all categories.</span></span>  
  
#### <a name="to-display-all-sales-persons-along-the-category-axis-of-a-bar-chart"></a><span data-ttu-id="1785e-175">Pour afficher tous les commerciaux le long de l'axe des abscisses d'un graphique à barres</span><span class="sxs-lookup"><span data-stu-id="1785e-175">To display all sales persons along the category axis of a bar chart</span></span>  
  
1.  <span data-ttu-id="1785e-176">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1785e-177">Cliquez avec le bouton droit sur l’axe vertical, puis cliquez sur Propriétés de l' **axe vertical**.</span><span class="sxs-lookup"><span data-stu-id="1785e-177">Right-click the vertical axis, and then click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="1785e-178">Sous **Plage et intervalle de l’axe**, dans la zone **Intervalle** , tapez **1**.</span><span class="sxs-lookup"><span data-stu-id="1785e-178">Under **Axis range and interval**, in the **Interval** box, type **1**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="1785e-179">Cliquez avec le bouton droit sur le titre de l' **axe** vertical et désactivez la case à cocher **afficher le titre** de l’axe.</span><span class="sxs-lookup"><span data-stu-id="1785e-179">Right-click the vertical **Axis Title** and clear the **Show Axis Title** check box.</span></span>  
  
6.  <span data-ttu-id="1785e-180">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-180">Click **Run** to preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1785e-181">Si vous ne parvenez pas à lire les noms des commerciaux sur l'axe vertical, vous pouvez augmenter la taille de votre graphique ou modifier les options de mise en forme des étiquettes d'axe.</span><span class="sxs-lookup"><span data-stu-id="1785e-181">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
###  <a name="display-last-name-and-first-name-on-vertical-axis"></a><a name="CategoryExpression"></a><span data-ttu-id="1785e-182">Afficher le nom et le prénom sur l’axe vertical</span><span class="sxs-lookup"><span data-stu-id="1785e-182">Display Last Name and First Name on Vertical Axis</span></span>  
 <span data-ttu-id="1785e-183">Vous pouvez modifier l'expression de catégorie pour inclure le nom suivi du prénom de chaque commercial.</span><span class="sxs-lookup"><span data-stu-id="1785e-183">You can change the category expression to include last name followed by first name of each sales person.</span></span>  
  
##### <a name="to-change-the-category-expression"></a><span data-ttu-id="1785e-184">Pour modifier l'expression de catégorie</span><span class="sxs-lookup"><span data-stu-id="1785e-184">To change the category expression</span></span>  
  
1.  <span data-ttu-id="1785e-185">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-185">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1785e-186">Double-cliquez sur le graphique pour afficher le volet **Données du graphique** .</span><span class="sxs-lookup"><span data-stu-id="1785e-186">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="1785e-187">Dans la zone **Groupes de catégories** , cliquez avec le bouton droit sur le champ [LastName], puis cliquez sur **Propriétés du groupe de catégories**.</span><span class="sxs-lookup"><span data-stu-id="1785e-187">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="1785e-188">Dans Étiquette, cliquez sur le bouton Expression (Fx).</span><span class="sxs-lookup"><span data-stu-id="1785e-188">In Label, click the expression (Fx) button.</span></span>  
  
5.  <span data-ttu-id="1785e-189">Tapez l’expression suivante : `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="1785e-189">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
     <span data-ttu-id="1785e-190">Cette expression concatène le nom, une virgule et le prénom.</span><span class="sxs-lookup"><span data-stu-id="1785e-190">This expression concatenates the last name, a comma, and the first name.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="1785e-191">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-191">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1785e-192">Si les prénoms n'apparaissent pas lorsque vous exécutez le rapport, vous pouvez actualiser les données manuellement.</span><span class="sxs-lookup"><span data-stu-id="1785e-192">If the first names do not appear when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="1785e-193">Toujours en mode Aperçu, sous l’onglet **Exécuter** du groupe **Navigation** , cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="1785e-193">While still in preview mode, on the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1785e-194">Si vous ne parvenez pas à lire les noms des commerciaux sur l'axe vertical, vous pouvez augmenter la taille de votre graphique ou modifier les options de mise en forme des étiquettes d'axe.</span><span class="sxs-lookup"><span data-stu-id="1785e-194">If you cannot read the salesperson names on the vertical axis, you can make your chart taller or change the formatting options for the axis labels.</span></span>  
  
##  <a name="4-change-the-sort-order-for-names-on-the-vertical-axis"></a><a name="Sort"></a><span data-ttu-id="1785e-195">4. modifier l’ordre de tri pour les noms sur l’axe vertical</span><span class="sxs-lookup"><span data-stu-id="1785e-195">4. Change the Sort Order for Names on the Vertical Axis</span></span>  
 <span data-ttu-id="1785e-196">Lorsque vous triez les données d'un graphique, vous modifiez l'ordre des valeurs sur l'axe des abscisses.</span><span class="sxs-lookup"><span data-stu-id="1785e-196">When you sort the data on a chart, you are changing the order of values on the category axis.</span></span>  
  
#### <a name="to-sort-the-names-in-alphabetical-order-on-the-bar-chart"></a><span data-ttu-id="1785e-197">Pour trier les noms dans l'ordre alphabétique sur le graphique à barres</span><span class="sxs-lookup"><span data-stu-id="1785e-197">To sort the names in alphabetical order on the bar chart</span></span>  
  
1.  <span data-ttu-id="1785e-198">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-198">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1785e-199">Double-cliquez sur le graphique pour afficher le volet **Données du graphique** .</span><span class="sxs-lookup"><span data-stu-id="1785e-199">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="1785e-200">Dans la zone **Groupes de catégories** , cliquez avec le bouton droit sur le champ [LastName], puis cliquez sur **Propriétés du groupe de catégories**.</span><span class="sxs-lookup"><span data-stu-id="1785e-200">In the **Category Groups** area, right-click [LastName], and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="1785e-201">Cliquez sur **Tri**.</span><span class="sxs-lookup"><span data-stu-id="1785e-201">Click **Sorting**.</span></span> <span data-ttu-id="1785e-202">La page **Modifiez les options de tri** affiche une liste d’expressions de tri.</span><span class="sxs-lookup"><span data-stu-id="1785e-202">The **Change sorting options** page displays a list of sort expressions.</span></span> <span data-ttu-id="1785e-203">Par défaut, cette liste a une expression de tri identique à l'expression de groupe de la catégorie d'origine.</span><span class="sxs-lookup"><span data-stu-id="1785e-203">By default, this list has one sort expression that is the same as the original category group expression.</span></span>  
  
5.  <span data-ttu-id="1785e-204">Dans Trier par, cliquez sur le bouton Expression (**FX**).</span><span class="sxs-lookup"><span data-stu-id="1785e-204">In Sort by, click the expression (**Fx**) button.</span></span>  
  
6.  <span data-ttu-id="1785e-205">Tapez l’expression suivante : `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span><span class="sxs-lookup"><span data-stu-id="1785e-205">Type the following expression: `=Fields!LastName.Value & ", " & Fields!FirstName.Value`</span></span>  
  
7.  <span data-ttu-id="1785e-206">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1785e-206">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="1785e-207">De retour sur la page **Propriétés du groupe de catégories** , dans la liste déroulante **ordre** , sélectionnez **Z à A**. Cela sélectionne l’ordre alphabétique inversé afin que les noms s’affichent dans l’ordre de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="1785e-207">Back on the **Category Group Properties** page, in the **Order** drop-down list, select **Z to A**. This selects reverse alphabetical order so that the names appear in order from top to bottom.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="1785e-208">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-208">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1785e-209">Les noms sur l’axe horizontal sont triés dans l’ordre inverse, avec **Alerca** en haut et **Zeng** en bas.</span><span class="sxs-lookup"><span data-stu-id="1785e-209">The names on the horizontal axis are sorted in reverse order, with **Alerca** at the top and **Zeng** at the bottom.</span></span>  
  
##  <a name="5-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="1785e-210">5. déplacer la légende</span><span class="sxs-lookup"><span data-stu-id="1785e-210">5. Move the Legend</span></span>  
 <span data-ttu-id="1785e-211">Pour améliorer la lisibilité des valeurs du graphique, vous pouvez déplacer la légende du graphique.</span><span class="sxs-lookup"><span data-stu-id="1785e-211">To improve the readability of the chart values, you might want to move the chart legend.</span></span> <span data-ttu-id="1785e-212">Par exemple, dans un graphique à barres horizontales, vous pouvez modifier la position de la légende de manière à l'afficher au-dessus ou en dessous de la zone de graphique.</span><span class="sxs-lookup"><span data-stu-id="1785e-212">For example, in a bar chart where bars are shown horizontally, you can change the position of the legend so that it is above or below the chart area.</span></span> <span data-ttu-id="1785e-213">Cela permet d'augmenter l'espace horizontal entre les barres.</span><span class="sxs-lookup"><span data-stu-id="1785e-213">This gives more horizontal space to the bars.</span></span>  
  
#### <a name="to-display-the-legend-below-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="1785e-214">Pour afficher la légende sous la zone de graphique d'un graphique à barres</span><span class="sxs-lookup"><span data-stu-id="1785e-214">To display the legend below the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="1785e-215">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-215">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1785e-216">Cliquez avec le bouton droit sur la légende du graphique.</span><span class="sxs-lookup"><span data-stu-id="1785e-216">Right-click the legend on the chart.</span></span>  
  
3.  <span data-ttu-id="1785e-217">Sélectionnez **Propriétés de la légende**.</span><span class="sxs-lookup"><span data-stu-id="1785e-217">Select **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="1785e-218">Pour **Position de la légende**, sélectionnez une position différente.</span><span class="sxs-lookup"><span data-stu-id="1785e-218">For **Legend position**, select a different position.</span></span> <span data-ttu-id="1785e-219">Par exemple, choisissez de positionner le graphique en bas au centre.</span><span class="sxs-lookup"><span data-stu-id="1785e-219">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="1785e-220">Lorsque la légende est placée en haut ou en bas d'un graphique, la disposition de la légende change de vertical à horizontal.</span><span class="sxs-lookup"><span data-stu-id="1785e-220">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="1785e-221">Vous pouvez sélectionner une autre disposition dans la liste déroulante **Disposition** .</span><span class="sxs-lookup"><span data-stu-id="1785e-221">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="1785e-222">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-222">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="1785e-223">6. titre du graphique</span><span class="sxs-lookup"><span data-stu-id="1785e-223">6. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area-of-a-bar-chart"></a><span data-ttu-id="1785e-224">Pour modifier le titre d'un graphique à barres au-dessus de la zone de graphique</span><span class="sxs-lookup"><span data-stu-id="1785e-224">To change the chart title above the chart area of a bar chart</span></span>  
  
1.  <span data-ttu-id="1785e-225">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-225">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1785e-226">Sélectionnez les mots **titre du graphique** en haut du graphique, puis tapez le texte suivant : **ventes pour 2008 et 2009**.</span><span class="sxs-lookup"><span data-stu-id="1785e-226">Select the words **Chart Title** at the top of the chart, and then type the following text: **Sales for 2008 and 2009**.</span></span>  
  
3.  <span data-ttu-id="1785e-227">Cliquez n'importe où en dehors du texte.</span><span class="sxs-lookup"><span data-stu-id="1785e-227">Click anywhere outside the text.</span></span>  
  
4.  <span data-ttu-id="1785e-228">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-228">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="1785e-229">7. mettre en forme et étiqueter l’axe horizontal</span><span class="sxs-lookup"><span data-stu-id="1785e-229">7. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="1785e-230">Par défaut, l'axe horizontal affiche les valeurs dans un format général qui est mis à l'échelle automatiquement pour s'ajuster à la taille du graphique.</span><span class="sxs-lookup"><span data-stu-id="1785e-230">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-the-numbers-on-the-horizontal-axis"></a><span data-ttu-id="1785e-231">Pour mettre en forme les nombres sur l'axe horizontal</span><span class="sxs-lookup"><span data-stu-id="1785e-231">To format the numbers on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="1785e-232">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-232">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1785e-233">Cliquez sur l'axe horizontal en bas du graphique pour le sélectionner.</span><span class="sxs-lookup"><span data-stu-id="1785e-233">Click the horizontal axis along the bottom of the chart to select it.</span></span>  
  
     <span data-ttu-id="1785e-234">Dans le ruban, sous l’onglet dossier de **démarrage** , dans le groupe **nombre** , cliquez sur le bouton **devise** .</span><span class="sxs-lookup"><span data-stu-id="1785e-234">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="1785e-235">Les étiquettes de l'axe horizontal changent et utilisent une devise.</span><span class="sxs-lookup"><span data-stu-id="1785e-235">The horizontal axis labels change to currency.</span></span>  
  
3.  <span data-ttu-id="1785e-236">(Facultatif) Supprimez les chiffres décimaux.</span><span class="sxs-lookup"><span data-stu-id="1785e-236">(Optional) Remove the decimal digits.</span></span> <span data-ttu-id="1785e-237">Près du bouton **Devise** , cliquez deux fois sur le bouton **Réduire les décimales** .</span><span class="sxs-lookup"><span data-stu-id="1785e-237">Near the **Currency** button, click the **Decrease Decimal** button twice.</span></span>  
  
4.  <span data-ttu-id="1785e-238">Cliquez avec le bouton droit sur l’axe horizontal, puis cliquez sur **Propriétés de l’axe horizontal**.</span><span class="sxs-lookup"><span data-stu-id="1785e-238">Right-click the horizontal axis, and click **Horizontal Axis Properties**.</span></span>  
  
5.  <span data-ttu-id="1785e-239">Sous l’onglet **nombre** , sélectionnez **afficher les valeurs en milliers.**</span><span class="sxs-lookup"><span data-stu-id="1785e-239">On the **Number** tab, select **Show values in Thousands.**</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="1785e-240">Cliquez avec le bouton droit sur le titre de l' **axe** , puis cliquez sur **Propriétés du titre**de l’axe.</span><span class="sxs-lookup"><span data-stu-id="1785e-240">Right-click **Axis Title** and click **Axis Title Properties**.</span></span>  
  
8.  <span data-ttu-id="1785e-241">Dans la zone de **texte titre** , tapez **ventes en milliers** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1785e-241">In the **Title text** box, type **Sales in thousands** and click **OK**.</span></span>  
  
9. <span data-ttu-id="1785e-242">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-242">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1785e-243">Le rapport affiche les montants des ventes sur l'axe horizontal sous forme de devises en milliers, sans chiffres décimaux.</span><span class="sxs-lookup"><span data-stu-id="1785e-243">The report displays the sales amount on the horizontal axis as currency in thousands, and has no decimal digits.</span></span>  
  
##  <a name="8-add-a-filter-to-display-the-top-five-values"></a><a name="Filter"></a><span data-ttu-id="1785e-244">8. Ajouter un filtre pour afficher les cinq premières valeurs</span><span class="sxs-lookup"><span data-stu-id="1785e-244">8. Add a Filter to Display the Top Five Values</span></span>  
 <span data-ttu-id="1785e-245">Vous pouvez ajouter un filtre au graphique pour spécifier les données du dataset à inclure ou exclure dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="1785e-245">You can add a filter to the chart to specify which data from the dataset to include or exclude in the chart.</span></span>  
  
#### <a name="to-add-a-filter-and-display-the-top-five-values"></a><span data-ttu-id="1785e-246">Pour ajouter un filtre et afficher les cinq valeurs supérieures</span><span class="sxs-lookup"><span data-stu-id="1785e-246">To add a filter and display the top five values</span></span>  
  
1.  <span data-ttu-id="1785e-247">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-247">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1785e-248">Double-cliquez sur le graphique pour afficher le volet **Données du graphique** .</span><span class="sxs-lookup"><span data-stu-id="1785e-248">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="1785e-249">Dans la zone **Groupes de catégories** , cliquez avec le bouton droit sur le champ [LastName], puis cliquez sur **Propriétés du groupe de catégories**.</span><span class="sxs-lookup"><span data-stu-id="1785e-249">In the **Category Groups** area, right-click the [LastName] field, and then click **Category Group Properties**.</span></span>  
  
4.  <span data-ttu-id="1785e-250">Cliquez sur **Filtres**.</span><span class="sxs-lookup"><span data-stu-id="1785e-250">Click **Filters**.</span></span> <span data-ttu-id="1785e-251">La page **Modifiez les filtres** peut afficher une liste d’expressions de filtre.</span><span class="sxs-lookup"><span data-stu-id="1785e-251">The **Change filters** page can display a list of filter expressions.</span></span> <span data-ttu-id="1785e-252">Par défaut, cette liste est vide.</span><span class="sxs-lookup"><span data-stu-id="1785e-252">By default, this list is empty.</span></span>  
  
5.  <span data-ttu-id="1785e-253">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="1785e-253">Click **Add**.</span></span> <span data-ttu-id="1785e-254">Un nouveau filtre vide apparaît.</span><span class="sxs-lookup"><span data-stu-id="1785e-254">A new blank filter appears.</span></span>  
  
6.  <span data-ttu-id="1785e-255">Dans **expression**, tapez **[Sum (SalesYear2009)]**.</span><span class="sxs-lookup"><span data-stu-id="1785e-255">In **Expression**, type **[Sum(SalesYear2009)]**.</span></span> <span data-ttu-id="1785e-256">Cela crée l’expression sous-jacente `=Sum(Fields!SalesYear2009.Value)`, que vous pouvez afficher en cliquant sur le bouton **fx** .</span><span class="sxs-lookup"><span data-stu-id="1785e-256">This creates the underlying expression `=Sum(Fields!SalesYear2009.Value)`, which you can see if you click the **fx** button.</span></span>  
  
7.  <span data-ttu-id="1785e-257">Vérifiez que le type de données est **Text**.</span><span class="sxs-lookup"><span data-stu-id="1785e-257">Verify that the data type is **Text**.</span></span>  
  
8.  <span data-ttu-id="1785e-258">Dans **Opérateur**, sélectionnez **N supérieurs** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="1785e-258">In **Operator**, select **Top N** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="1785e-259">Dans **Valeur**, tapez l’expression suivante : **=5**</span><span class="sxs-lookup"><span data-stu-id="1785e-259">In **Value**, type the following expression: **=5**</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="1785e-260">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-260">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="1785e-261">Si les résultats ne sont pas filtrés lorsque vous exécutez le rapport, vous pouvez actualiser les données manuellement.</span><span class="sxs-lookup"><span data-stu-id="1785e-261">If the results are not filtered when you run the report, you can refresh the data manually.</span></span> <span data-ttu-id="1785e-262">Sous l’onglet **Exécuter** , dans le groupe **Navigation** , cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="1785e-262">On the **Run** tab in the **Navigation** group, click **Refresh**.</span></span>  
  
 <span data-ttu-id="1785e-263">Le graphique affiche les noms des cinq meilleurs commerciaux issus des données de ventes 2009.</span><span class="sxs-lookup"><span data-stu-id="1785e-263">The chart shows the top five salesperson names from the 2009 sales data.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="1785e-264">9. Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="1785e-264">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="1785e-265">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="1785e-265">To add a report title</span></span>  
  
1.  <span data-ttu-id="1785e-266">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="1785e-266">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="1785e-267">Tapez **graphique à barres des ventes**, appuyez sur entrée, puis tapez **cinq meilleurs vendeurs pour 2009**. il ressemble à ceci :</span><span class="sxs-lookup"><span data-stu-id="1785e-267">Type **Sales Bar Chart**, press ENTER, and then type **Top Five Sellers for 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="1785e-268">**Graphique à barres des ventes**</span><span class="sxs-lookup"><span data-stu-id="1785e-268">**Sales Bar Chart**</span></span>  
  
     <span data-ttu-id="1785e-269">**Cinq meilleurs vendeurs pour 2009**</span><span class="sxs-lookup"><span data-stu-id="1785e-269">**Top Five Sellers for 2009**</span></span>  
  
3.  <span data-ttu-id="1785e-270">Sélectionnez **Graphique à barres des ventes**, puis cliquez sur le bouton **Gras** .</span><span class="sxs-lookup"><span data-stu-id="1785e-270">Select **Sales Bar Chart**, and click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="1785e-271">Sélectionnez les **cinq meilleurs vendeurs pour 2009**, puis dans la section **police** de l’onglet dossier de **départ** , définissez la taille de police sur **10**.</span><span class="sxs-lookup"><span data-stu-id="1785e-271">Select **Top Five Sellers for 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="1785e-272">(Facultatif) Vous devrez peut-être agrandir la zone de texte Titre pour contenir les deux lignes de texte.</span><span class="sxs-lookup"><span data-stu-id="1785e-272">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="1785e-273">Ce titre s'affiche alors dans la partie supérieure du rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-273">This title will appear at the top of the report.</span></span> <span data-ttu-id="1785e-274">En l’absence d’en-tête de page défini, les éléments situés au-dessus du corps du rapport font office d’en-tête de rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-274">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="1785e-275">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-275">Click **Run** to preview the report.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="1785e-276">10. enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="1785e-276">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="1785e-277">Pour enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="1785e-277">To save the report</span></span>  
  
1.  <span data-ttu-id="1785e-278">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-278">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="1785e-279">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="1785e-279">From the **Report Builder** button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="1785e-280">Dans **Nom**, tapez **Graphique à barres des ventes**.</span><span class="sxs-lookup"><span data-stu-id="1785e-280">In **Name**, type **Sales Bar Chart**.</span></span>  
  
4.  <span data-ttu-id="1785e-281">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1785e-281">Click **Save**.</span></span>  
  
 <span data-ttu-id="1785e-282">Votre rapport est enregistré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1785e-282">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1785e-283">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="1785e-283">Next Steps</span></span>  
 <span data-ttu-id="1785e-284">Vous avez réalisé le didacticiel d'ajout d'un graphique à barres à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="1785e-284">You have successfully completed the Adding a Bar Chart to Your Report tutorial.</span></span> <span data-ttu-id="1785e-285">Pour en savoir plus sur les graphiques, consultez [Graphiques &#40;Générateur de rapports et SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) et [Graphiques sparkline et barres de données &#40;Générateur de rapports et SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1785e-285">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1785e-286">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1785e-286">See Also</span></span>  
 <span data-ttu-id="1785e-287">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="1785e-287">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="1785e-288">Générateur de rapports dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="1785e-288">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
