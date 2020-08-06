---
title: 'Didacticiel : ajouter un histogramme à un rapport (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 63480059-b7b9-44b5-9d7f-91780db708b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ef3b3f2872c2f8181296bb05337ca18975ac2f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706151"
---
# <a name="tutorial-add-a-column-chart-to-your-report-report-builder"></a><span data-ttu-id="767e4-102">Didacticiel : ajouter un histogramme à un rapport (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="767e4-102">Tutorial: Add a Column Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="767e4-103">Un histogramme affiche une série sous la forme d'un ensemble de barres verticales regroupées par catégorie.</span><span class="sxs-lookup"><span data-stu-id="767e4-103">A column chart displays a series as a set of vertical bars that are grouped by category.</span></span> <span data-ttu-id="767e4-104">Un histogramme s'avère utile pour :</span><span class="sxs-lookup"><span data-stu-id="767e4-104">A column chart can be useful to:</span></span>  
  
-   <span data-ttu-id="767e4-105">montrer l'évolution des données sur une période ;</span><span class="sxs-lookup"><span data-stu-id="767e4-105">Show data changes over a period of time.</span></span>  
  
-   <span data-ttu-id="767e4-106">comparer la valeur relative de plusieurs séries.</span><span class="sxs-lookup"><span data-stu-id="767e4-106">Compare the relative value of multiple series.</span></span>  
  
-   <span data-ttu-id="767e4-107">afficher une moyenne mobile pour montrer les tendances.</span><span class="sxs-lookup"><span data-stu-id="767e4-107">Display a moving average to show trends.</span></span>  
  
 <span data-ttu-id="767e4-108">L'illustration suivante montre l'histogramme que vous allez créer, avec une moyenne mobile.</span><span class="sxs-lookup"><span data-stu-id="767e4-108">The following illustration shows the column chart you will create, with a moving average.</span></span>  
  
 <span data-ttu-id="767e4-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span><span class="sxs-lookup"><span data-stu-id="767e4-109">![rs_TutorialColChartFinished](../../2014/tutorials/media/rs-tutorialcolchartfinished.gif "rs_TutorialColChartFinished")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="767e4-110">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="767e4-110">What You Will Learn</span></span>  
 <span data-ttu-id="767e4-111">Dans ce didacticiel, vous apprendrez à effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="767e4-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="767e4-112">Créer un graphique à partir de l'Assistant Graphique</span><span class="sxs-lookup"><span data-stu-id="767e4-112">Create a Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="767e4-113">Choisir le type de graphique</span><span class="sxs-lookup"><span data-stu-id="767e4-113">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="767e4-114">Mettre en forme et étiqueter l'axe horizontal</span><span class="sxs-lookup"><span data-stu-id="767e4-114">Format and Label the Horizontal Axis</span></span>](#Horizontal)  
  
4.  [<span data-ttu-id="767e4-115">Déplacer la légende</span><span class="sxs-lookup"><span data-stu-id="767e4-115">Move the Legend</span></span>](#Legend)  
  
5.  [<span data-ttu-id="767e4-116">Intituler le graphique</span><span class="sxs-lookup"><span data-stu-id="767e4-116">Title the Chart</span></span>](#ChartTitle)  
  
6.  [<span data-ttu-id="767e4-117">Mettre en forme et étiqueter l'axe vertical</span><span class="sxs-lookup"><span data-stu-id="767e4-117">Format and Label the Vertical Axis</span></span>](#Vertical)  
  
7.  [<span data-ttu-id="767e4-118">Ajouter une moyenne mobile</span><span class="sxs-lookup"><span data-stu-id="767e4-118">Add a Moving Average</span></span>](#Average)  
  
8.  [<span data-ttu-id="767e4-119">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="767e4-119">Add a Report Title</span></span>](#Title)  
  
9. [<span data-ttu-id="767e4-120">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="767e4-120">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="767e4-121">Dans ce didacticiel, les étapes de l'Assistant sont consolidées en une seule procédure.</span><span class="sxs-lookup"><span data-stu-id="767e4-121">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="767e4-122">Pour obtenir des instructions pas à pas sur l’accès à un serveur de rapports, le choix d’une source de données et la création d’un dataset, consultez le premier didacticiel de cette série : [Didacticiel : création d’un rapport de tableau de base &#40;Générateur de rapports&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="767e4-122">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="767e4-123">Durée estimée pour effectuer ce didacticiel : 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="767e4-123">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="767e4-124">Spécifications</span><span class="sxs-lookup"><span data-stu-id="767e4-124">Requirements</span></span>  
 <span data-ttu-id="767e4-125">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="767e4-125">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-chart-report-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="767e4-126">1. créer un rapport de graphique à partir de l’Assistant graphique</span><span class="sxs-lookup"><span data-stu-id="767e4-126">1. Create a Chart Report from the Chart Wizard</span></span>  
 <span data-ttu-id="767e4-127">À partir de la boîte de dialogue **prise en main** , utilisez l’Assistant graphique pour créer un dataset incorporé, choisir une source de données partagée et créer un histogramme.</span><span class="sxs-lookup"><span data-stu-id="767e4-127">From the **Getting Started** dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a column chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="767e4-128">Dans ce didacticiel, la requête contient les valeurs de données, afin qu'il ne soit pas nécessaire de disposer d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="767e4-128">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="767e4-129">Cela rend la requête assez longue.</span><span class="sxs-lookup"><span data-stu-id="767e4-129">This makes the query quite long.</span></span> <span data-ttu-id="767e4-130">Dans un environnement métier, une requête ne contient pas les données.</span><span class="sxs-lookup"><span data-stu-id="767e4-130">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="767e4-131">Ceci est nécessaire à des fins de formation uniquement.</span><span class="sxs-lookup"><span data-stu-id="767e4-131">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="767e4-132">Pour créer un rapport de graphique</span><span class="sxs-lookup"><span data-stu-id="767e4-132">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="767e4-133">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur **Générateur de rapports Microsoft SQL Server 2012**, puis cliquez sur **Générateur de rapports version**.</span><span class="sxs-lookup"><span data-stu-id="767e4-133">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="767e4-134">La boîte de dialogue **prise en main** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="767e4-134">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="767e4-135">Si la boîte de dialogue **prise en main** n’apparaît pas, à partir du bouton **Générateur de rapports** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="767e4-135">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="767e4-136">Dans le volet gauche, assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="767e4-136">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="767e4-137">Dans le volet droit, cliquez sur **Assistant Graphique**.</span><span class="sxs-lookup"><span data-stu-id="767e4-137">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="767e4-138">Dans la page **Choisir un dataset**, cliquez sur **Créer un dataset**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="767e4-138">On the **Choose a dataset page**, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="767e4-139">Dans la page **Choisir une connexion à une source de données** , sélectionnez une source de données existante ou naviguez jusqu’au serveur de rapports, sélectionnez une source de données, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="767e4-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="767e4-140">Vous devrez peut-être entrer un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="767e4-140">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="767e4-141">La source de données que vous choisissez n'a pas d'importance, tant que vous disposez des autorisations appropriées.</span><span class="sxs-lookup"><span data-stu-id="767e4-141">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="767e4-142">Vous n'allez pas récupérer de données à partir de la source de données.</span><span class="sxs-lookup"><span data-stu-id="767e4-142">You will not be getting data from the data source.</span></span> <span data-ttu-id="767e4-143">Pour plus d’informations, consultez [Autres manières d’obtenir une connexion de données &#40;Générateur de rapports&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="767e4-143">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="767e4-144">Dans la page **Créer une requête** , cliquez sur **Modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="767e4-144">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="767e4-145">Collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="767e4-145">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-01' AS date) AS SalesDate, CAST(54995.21 AS money) AS Sales  
    UNION SELECT CAST('2009-01-05' AS date) AS SalesDate, CAST(64499.04 AS money) AS Sales  
    UNION SELECT CAST('2009-02-11' AS date) AS SalesDate, CAST(37821.79 AS money) AS Sales  
    UNION SELECT CAST('2009-03-18' AS date) AS SalesDate, CAST(53633.08 AS money) AS Sales  
    UNION SELECT CAST('2009-04-23' AS date) AS SalesDate, CAST(24019.3 AS money) AS Sales  
    UNION SELECT CAST('2009-05-01' AS date) AS SalesDate, CAST(93245.5 AS money) AS Sales  
    UNION SELECT CAST('2009-06-06' AS date) AS SalesDate, CAST(55288.0 AS money) AS Sales  
    UNION SELECT CAST('2009-06-16' AS date) AS SalesDate, CAST(68733.5 AS money) AS Sales  
    UNION SELECT CAST('2009-07-16' AS date) AS SalesDate, CAST(24750.85 AS money) AS Sales  
    UNION SELECT CAST('2009-08-23' AS date) AS SalesDate, CAST(43452.3 AS money) AS Sales  
    UNION SELECT CAST('2009-09-24' AS date) AS SalesDate, CAST(58656. AS money) AS Sales  
    UNION SELECT CAST('2009-10-15' AS date) AS SalesDate, CAST(44583. AS money) AS Sales  
    UNION SELECT CAST('2009-11-21' AS date) AS SalesDate, CAST(81568. AS money) AS Sales  
    UNION SELECT CAST('2009-12-15' AS date) AS SalesDate, CAST(45973. AS money) AS Sales  
    UNION SELECT CAST('2009-12-26' AS date) AS SalesDate, CAST(96357. AS money) AS Sales  
    UNION SELECT CAST('2009-12-31' AS date) AS SalesDate, CAST(81946. AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="767e4-146">(Facultatif) Cliquez sur le bouton Exécuter (**!**) pour voir les données sur lesquelles votre graphique sera basé.</span><span class="sxs-lookup"><span data-stu-id="767e4-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="767e4-147">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="767e4-147">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="767e4-148">2. choisir le type de graphique</span><span class="sxs-lookup"><span data-stu-id="767e4-148">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="767e4-149">Vous avez le choix entre plusieurs types de graphiques prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="767e4-149">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-column-chart"></a><span data-ttu-id="767e4-150">Pour ajouter un histogramme</span><span class="sxs-lookup"><span data-stu-id="767e4-150">To add a column chart</span></span>  
  
1.  <span data-ttu-id="767e4-151">Dans la page **Choisir un type de graphique** , l’histogramme est le type de graphique par défaut.</span><span class="sxs-lookup"><span data-stu-id="767e4-151">On the **Choose a chart type** page, the column chart is the default chart type.</span></span> <span data-ttu-id="767e4-152">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="767e4-152">Click **Next**.</span></span>  
  
2.  <span data-ttu-id="767e4-153">Dans la page **Organiser les champs du graphique** , faites glisser le champ SalesDate vers **Catégories**.</span><span class="sxs-lookup"><span data-stu-id="767e4-153">On the **Arrange chart fields** page, drag the SalesDate field to **Categories**.</span></span> <span data-ttu-id="767e4-154">Les catégories s'affichent sur l'axe horizontal.</span><span class="sxs-lookup"><span data-stu-id="767e4-154">Categories display on the horizontal axis.</span></span>  
  
3.  <span data-ttu-id="767e4-155">Faites glisser le champ Sales vers **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="767e4-155">Drag the Sales field to **Values**.</span></span> <span data-ttu-id="767e4-156">La zone **Valeurs** affiche Sum(Sales), car la somme de la valeur totale des ventes est agrégée pour chaque date.</span><span class="sxs-lookup"><span data-stu-id="767e4-156">The **Values** box displays Sum(Sales) because the sum of the sales total value is aggregated for each date.</span></span> <span data-ttu-id="767e4-157">Les valeurs s'affichent sur l'axe vertical.</span><span class="sxs-lookup"><span data-stu-id="767e4-157">Values display on the vertical axis.</span></span>  
  
4.  <span data-ttu-id="767e4-158">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="767e4-158">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="767e4-159">Dans la page **choisir un style** , dans la zone styles, sélectionnez un style.</span><span class="sxs-lookup"><span data-stu-id="767e4-159">On the **Choose a Style** page, in the Styles box, select a style.</span></span>  
  
     <span data-ttu-id="767e4-160">Un style spécifie un style de police, un jeu de couleurs et un style de bordure.</span><span class="sxs-lookup"><span data-stu-id="767e4-160">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="767e4-161">Lorsque vous sélectionnez un style, le volet Aperçu affiche un aperçu du graphique avec ce style.</span><span class="sxs-lookup"><span data-stu-id="767e4-161">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
6.  <span data-ttu-id="767e4-162">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="767e4-162">Click **Finish**.</span></span>  
  
     <span data-ttu-id="767e4-163">Le graphique est ajouté à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="767e4-163">The chart is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="767e4-164">Cliquez sur le graphique pour afficher ses poignées.</span><span class="sxs-lookup"><span data-stu-id="767e4-164">Click the chart to display the chart handles.</span></span> <span data-ttu-id="767e4-165">Faites glisser l'angle inférieur droit du graphique pour augmenter sa taille.</span><span class="sxs-lookup"><span data-stu-id="767e4-165">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="767e4-166">Notez que la taille de l'aire de conception du rapport augmente pour s'adapter à la taille du graphique.</span><span class="sxs-lookup"><span data-stu-id="767e4-166">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
8.  <span data-ttu-id="767e4-167">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-167">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-format-and-label-the-horizontal-axis"></a><a name="Horizontal"></a><span data-ttu-id="767e4-168">3. mettre en forme et étiqueter l’axe horizontal</span><span class="sxs-lookup"><span data-stu-id="767e4-168">3. Format and Label the Horizontal Axis</span></span>  
 <span data-ttu-id="767e4-169">Par défaut, l'axe horizontal affiche les valeurs dans un format général qui est mis à l'échelle automatiquement pour s'ajuster à la taille du graphique.</span><span class="sxs-lookup"><span data-stu-id="767e4-169">By default, the horizontal axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-a-date-on-the-horizontal-axis"></a><span data-ttu-id="767e4-170">Pour mettre en forme une date sur l'axe horizontal</span><span class="sxs-lookup"><span data-stu-id="767e4-170">To format a date on the horizontal axis</span></span>  
  
1.  <span data-ttu-id="767e4-171">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-171">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="767e4-172">Cliquez avec le bouton droit sur l’axe horizontal, puis cliquez sur Propriétés de l' **axe horizontal**.</span><span class="sxs-lookup"><span data-stu-id="767e4-172">Right-click the horizontal axis, and then click **Horizontal Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="767e4-173">Cliquez sur **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="767e4-173">Click **Number**.</span></span>  
  
4.  <span data-ttu-id="767e4-174">Dans **catégorie**, sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="767e4-174">In **Category**, select **Date**.</span></span>  
  
5.  <span data-ttu-id="767e4-175">Dans la zone **Type** , sélectionnez **31 Jan 2000**.</span><span class="sxs-lookup"><span data-stu-id="767e4-175">In the **Type** box, select **31 Jan 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="767e4-176">Sous l’onglet Accueil, cliquez sur **Exécuter** pour afficher l’aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-176">On the Home tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="767e4-177">La date s'affiche dans le format de date que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="767e4-177">The date displays in the date format that you selected.</span></span> <span data-ttu-id="767e4-178">Notez que le graphique ne répertorie pas chaque catégorie sur l'axe horizontal.</span><span class="sxs-lookup"><span data-stu-id="767e4-178">Notice that the chart does not label every category on the horizontal axis.</span></span> <span data-ttu-id="767e4-179">Par défaut, seules sont incluses les étiquettes qui n'empiètent pas sur l'axe.</span><span class="sxs-lookup"><span data-stu-id="767e4-179">By default, only labels that fit next to the axis are included.</span></span>  
  
 <span data-ttu-id="767e4-180">Vous pouvez personnaliser l'affichage des étiquettes en les faisant pivoter et en spécifiant l'intervalle.</span><span class="sxs-lookup"><span data-stu-id="767e4-180">You can customize the label display by rotating the labels and specifying the interval.</span></span>  
  
#### <a name="to-rotate-the-axis-labels-and-change-the-display-interval-along-the-horizontal-axis"></a><span data-ttu-id="767e4-181">Pour faire pivoter les étiquettes sur l'axe horizontal et modifier l'intervalle qui les sépare</span><span class="sxs-lookup"><span data-stu-id="767e4-181">To rotate the axis labels and change the display interval along the horizontal axis</span></span>  
  
1.  <span data-ttu-id="767e4-182">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-182">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="767e4-183">Cliquez avec le bouton droit sur le titre de l’axe horizontal, puis cliquez sur **afficher le titre** de l’axe pour supprimer le titre.</span><span class="sxs-lookup"><span data-stu-id="767e4-183">Right-click the horizontal axis title, and then click **Show Axis Title** to remove the title.</span></span> <span data-ttu-id="767e4-184">Étant donné que l'axe horizontal indique les dates, le titre n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="767e4-184">Because the horizontal axis displays dates, the title is not needed.</span></span>  
  
3.  <span data-ttu-id="767e4-185">Cliquez avec le bouton droit sur l’axe horizontal, puis cliquez sur Propriétés de l' **axe horizontal**.</span><span class="sxs-lookup"><span data-stu-id="767e4-185">Right-click the horizontal axis and then click **Horizontal Axis Properties**.</span></span>  
  
4.  <span data-ttu-id="767e4-186">Dans la page **options** de l’axe sous **plage et intervalle**de l’axe, tapez **3** pour **intervalle**.</span><span class="sxs-lookup"><span data-stu-id="767e4-186">In the **Axis Options** page under **Axis range and interval**, type **3** for **Interval**.</span></span> <span data-ttu-id="767e4-187">Le graphique affiche les dates selon un intervalle de trois.</span><span class="sxs-lookup"><span data-stu-id="767e4-187">The chart will display every third date.</span></span>  
  
5.  <span data-ttu-id="767e4-188">Cliquez sur **Étiquettes**.</span><span class="sxs-lookup"><span data-stu-id="767e4-188">Click **Labels**.</span></span>  
  
6.  <span data-ttu-id="767e4-189">Dans **modifier les options d’ajustement automatique des étiquettes d’axe**, sélectionnez **désactiver l’ajustement automatique**.</span><span class="sxs-lookup"><span data-stu-id="767e4-189">In **Change axis label auto-fit options**, select **Disable auto-fit**.</span></span>  
  
7.  <span data-ttu-id="767e4-190">Dans **Angle de rotation des étiquettes**, sélectionnez **-90**.</span><span class="sxs-lookup"><span data-stu-id="767e4-190">In **Label rotation angle**, select **-90**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="767e4-191">L'exemple de texte de l'axe horizontal pivote de 90 degrés.</span><span class="sxs-lookup"><span data-stu-id="767e4-191">The sample text for the horizontal axis rotates by 90 degrees.</span></span>  
  
9. <span data-ttu-id="767e4-192">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-192">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="767e4-193">Sur le graphique, les étiquettes pivotent et sont affichées à raison d'une date sur trois.</span><span class="sxs-lookup"><span data-stu-id="767e4-193">On the chart, the labels are rotated and the label for every third date is shown.</span></span>  
  
##  <a name="4-move-the-legend"></a><a name="Legend"></a><span data-ttu-id="767e4-194">4. déplacer la légende</span><span class="sxs-lookup"><span data-stu-id="767e4-194">4. Move the Legend</span></span>  
 <span data-ttu-id="767e4-195">La légende est créée automatiquement à partir des données de catégories et de séries.</span><span class="sxs-lookup"><span data-stu-id="767e4-195">The legend is automatically created from category and series data.</span></span>  
  
#### <a name="to-move-the-legend-below-the-chart-area-of-a-column-chart"></a><span data-ttu-id="767e4-196">Pour déplacer la légende sous la zone de graphique d'un histogramme</span><span class="sxs-lookup"><span data-stu-id="767e4-196">To move the legend below the chart area of a column chart</span></span>  
  
1.  <span data-ttu-id="767e4-197">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-197">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="767e4-198">Cliquez avec le bouton droit sur la légende du graphique, puis cliquez sur Propriétés de la **légende**.</span><span class="sxs-lookup"><span data-stu-id="767e4-198">Right-click the legend on the chart, and then click **Legend Properties**.</span></span>  
  
3.  <span data-ttu-id="767e4-199">Pour **disposition et position**, sélectionnez une autre position.</span><span class="sxs-lookup"><span data-stu-id="767e4-199">For **Layout and Position**, select a different position.</span></span> <span data-ttu-id="767e4-200">Par exemple, choisissez de positionner le graphique en bas au centre.</span><span class="sxs-lookup"><span data-stu-id="767e4-200">For example, set the position to the middle bottom option.</span></span>  
  
     <span data-ttu-id="767e4-201">Lorsque la légende est placée en haut ou en bas d'un graphique, la disposition de la légende change de vertical à horizontal.</span><span class="sxs-lookup"><span data-stu-id="767e4-201">When the legend is placed at the top or bottom of a chart, the layout of the legend changes from vertical to horizontal.</span></span> <span data-ttu-id="767e4-202">Vous pouvez sélectionner une autre disposition dans la liste déroulante **Disposition** .</span><span class="sxs-lookup"><span data-stu-id="767e4-202">You can select a different layout from the **Layout** drop-down list.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="767e4-203">(Facultatif) Étant donné que ce didacticiel ne comprend qu'une seule catégorie, la légende n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="767e4-203">(Optional) Because there is only one category in this tutorial, the legend is not needed.</span></span> <span data-ttu-id="767e4-204">Pour supprimer la légende, cliquez avec le bouton droit sur la légende, puis cliquez sur **Supprimer la légende**.</span><span class="sxs-lookup"><span data-stu-id="767e4-204">To remove the legend, right-click the legend and then click **Delete Legend**.</span></span>  
  
6.  <span data-ttu-id="767e4-205">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-205">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-title-the-chart"></a><a name="ChartTitle"></a><span data-ttu-id="767e4-206">5. titre du graphique</span><span class="sxs-lookup"><span data-stu-id="767e4-206">5. Title the Chart</span></span>  
  
#### <a name="to-change-the-chart-title-above-the-chart-area"></a><span data-ttu-id="767e4-207">Pour modifier le titre d'un graphique au-dessus de la zone de graphique</span><span class="sxs-lookup"><span data-stu-id="767e4-207">To change the chart title above the chart area</span></span>  
  
1.  <span data-ttu-id="767e4-208">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="767e4-209">Sélectionnez les mots **titre du graphique** en haut du graphique, puis tapez le texte suivant : total des **commandes client de magasin**.</span><span class="sxs-lookup"><span data-stu-id="767e4-209">Select the words **Chart Title** at the top of the chart, and then type the following text: **Store Sales Order Totals**.</span></span>  
  
3.  <span data-ttu-id="767e4-210">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-210">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-format-and-label-the-vertical-axis"></a><a name="Vertical"></a><span data-ttu-id="767e4-211">6. mettre en forme et étiqueter l’axe vertical</span><span class="sxs-lookup"><span data-stu-id="767e4-211">6. Format and Label the Vertical Axis</span></span>  
 <span data-ttu-id="767e4-212">Par défaut, l'axe vertical affiche les valeurs dans un format général qui est mis à l'échelle automatiquement pour s'ajuster à la taille du graphique.</span><span class="sxs-lookup"><span data-stu-id="767e4-212">By default, the vertical axis displays values in a general format that is automatically scaled to fit the size of the chart.</span></span>  
  
#### <a name="to-format-as-currency-the-numbers-on-the-vertical-axis"></a><span data-ttu-id="767e4-213">Pour appliquer le format monétaire aux chiffres figurant sur l'axe vertical</span><span class="sxs-lookup"><span data-stu-id="767e4-213">To format as currency the numbers on the vertical axis</span></span>  
  
1.  <span data-ttu-id="767e4-214">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-214">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="767e4-215">Double-cliquez sur les étiquettes de l’axe vertical sur le côté du graphique pour les sélectionner.</span><span class="sxs-lookup"><span data-stu-id="767e4-215">Double-click the labels on the vertical axis along the side of the chart to select them.</span></span>  
  
3.  <span data-ttu-id="767e4-216">Dans le ruban, sous l’onglet dossier de **démarrage** , dans le groupe **nombre** , cliquez sur le bouton **devise** .</span><span class="sxs-lookup"><span data-stu-id="767e4-216">On the ribbon, on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="767e4-217">Les étiquettes de l'axe changent pour afficher le format monétaire.</span><span class="sxs-lookup"><span data-stu-id="767e4-217">The axis labels change to show the currency format.</span></span>  
  
4.  <span data-ttu-id="767e4-218">Dans le ruban, sous l’onglet dossier de **démarrage** , dans le groupe **nombre** , cliquez sur le bouton **réduire la décimale** deux fois pour afficher le nombre arrondi au dollar le plus proche.</span><span class="sxs-lookup"><span data-stu-id="767e4-218">On the ribbon, on the **Home** tab, in the **Number** group, click the **Decrease Decimal** button two times, to show the number rounded to the nearest dollar.</span></span>  
  
5.  <span data-ttu-id="767e4-219">Cliquez avec le bouton droit sur l’axe vertical, puis cliquez sur Propriétés de l' **axe vertical**.</span><span class="sxs-lookup"><span data-stu-id="767e4-219">Right-click the vertical axis and click **Vertical Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="767e4-220">Cliquez sur **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="767e4-220">Click **Number**.</span></span> <span data-ttu-id="767e4-221">Notez que **devise** est déjà sélectionné dans la zone **catégorie** et que la valeur **décimale** est déjà **0** (zéro).</span><span class="sxs-lookup"><span data-stu-id="767e4-221">Note that **Currency** is already selected in the **Category** box, and **Decimal places** is already **0** (zero).</span></span>  
  
7.  <span data-ttu-id="767e4-222">Dans la zone **afficher les valeurs dans** , cliquez sur **milliers**.</span><span class="sxs-lookup"><span data-stu-id="767e4-222">In the **Show Values in** box, click **Thousands**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="767e4-223">Cliquez avec le bouton droit sur le titre de l’axe vertical sur le côté du graphique, puis cliquez sur **Propriétés du titre**de l’axe.</span><span class="sxs-lookup"><span data-stu-id="767e4-223">Right-click the vertical axis title along the side of the chart and click **Axis Title Properties**.</span></span>  
  
10. <span data-ttu-id="767e4-224">Remplacez le texte du champ **texte du titre** par le texte suivant : **total des ventes (en milliers)**.</span><span class="sxs-lookup"><span data-stu-id="767e4-224">Replace the text in the **Title text** field with the following text: **Sales Total (in Thousands)**.</span></span> <span data-ttu-id="767e4-225">Vous pouvez également spécifier diverses options de mise en forme du titre.</span><span class="sxs-lookup"><span data-stu-id="767e4-225">You can also specify a variety of options related to how the title is formatted.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="767e4-226">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-add-a-moving-average"></a><a name="Average"></a><span data-ttu-id="767e4-227">7. Ajouter une moyenne mobile</span><span class="sxs-lookup"><span data-stu-id="767e4-227">7. Add a Moving Average</span></span>  
  
#### <a name="to-add-a-moving-average"></a><span data-ttu-id="767e4-228">Pour ajouter une moyenne mobile</span><span class="sxs-lookup"><span data-stu-id="767e4-228">To add a moving average</span></span>  
  
1.  <span data-ttu-id="767e4-229">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-229">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="767e4-230">Double-cliquez sur le graphique pour afficher le volet **Données du graphique** .</span><span class="sxs-lookup"><span data-stu-id="767e4-230">Double-click the chart to display the **Chart Data** pane.</span></span>  
  
3.  <span data-ttu-id="767e4-231">Cliquez avec le bouton droit sur le champ **[Sum (Sales)]** dans la zone **valeurs** , puis cliquez sur **Ajouter une série calculée**.</span><span class="sxs-lookup"><span data-stu-id="767e4-231">Right-click the **[Sum(Sales)]** field that is in the **Values** area, and then click **Add Calculated Series**.</span></span>  
  
4.  <span data-ttu-id="767e4-232">Dans **Formule**, vérifiez que **Moyenne mobile** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="767e4-232">In **Formula**, verify that **Moving average** is selected.</span></span>  
  
5.  <span data-ttu-id="767e4-233">Dans **Définir les paramètres de la formule**, pour **Période**, sélectionnez **4**.</span><span class="sxs-lookup"><span data-stu-id="767e4-233">In **Set Formula Parameters**, for **Period**, select **4**.</span></span>  
  
6.  <span data-ttu-id="767e4-234">Cliquez sur **bordure**.</span><span class="sxs-lookup"><span data-stu-id="767e4-234">Click **Border**.</span></span>  
  
7.  <span data-ttu-id="767e4-235">Dans **largeur de ligne**, sélectionnez **3 points**.</span><span class="sxs-lookup"><span data-stu-id="767e4-235">In **Line width**, select **3pt**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="767e4-236">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-236">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="767e4-237">Le graphique présente une ligne qui indique la moyenne mobile pour le total des ventes par date. La moyenne est ici calculée toutes les quatre dates.</span><span class="sxs-lookup"><span data-stu-id="767e4-237">The chart displays a line that shows the moving average for total sales by date, averaged over every four dates.</span></span>  
  
##  <a name="8-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="767e4-238">8. Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="767e4-238">8. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="767e4-239">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="767e4-239">To add a report title</span></span>  
  
1.  <span data-ttu-id="767e4-240">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-240">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="767e4-241">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="767e4-241">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="767e4-242">Tapez **graphique des ventes**, appuyez sur entrée, puis tapez **janvier à décembre 2009**pour obtenir l’aspect suivant :</span><span class="sxs-lookup"><span data-stu-id="767e4-242">Type **Sales Chart**, press ENTER, and then type **January to December 2009**, so it looks like this:</span></span>  
  
     <span data-ttu-id="767e4-243">**Graphique sur les ventes**</span><span class="sxs-lookup"><span data-stu-id="767e4-243">**Sales Chart**</span></span>  
  
     <span data-ttu-id="767e4-244">**Janvier à décembre 2009**</span><span class="sxs-lookup"><span data-stu-id="767e4-244">**January to December 2009**</span></span>  
  
4.  <span data-ttu-id="767e4-245">Sélectionnez **graphique des ventes**, puis cliquez sur le bouton **gras** dans la section **police** de l’onglet dossier de **démarrage** du ruban.</span><span class="sxs-lookup"><span data-stu-id="767e4-245">Select **Sales Chart**, and click the **Bold** button in the **Font** section on the **Home** tab of the ribbon.</span></span>  
  
5.  <span data-ttu-id="767e4-246">Sélectionnez **janvier jusqu’au 2009 décembre**, puis dans la section **police** de l’onglet dossier de **départ** , définissez la taille de police sur **10**.</span><span class="sxs-lookup"><span data-stu-id="767e4-246">Select **January to December 2009**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
6.  <span data-ttu-id="767e4-247">Facultatif Vous devrez peut-être agrandir la zone de texte du **titre** pour accueillir les deux lignes de texte en tirant sur les flèches à deux pointes lorsque vous cliquez au milieu du bord inférieur.</span><span class="sxs-lookup"><span data-stu-id="767e4-247">(Optional) You may need to make the **Title** text box taller to accommodate the two lines of text by pulling down on the double-headed arrows when you click in the middle of the bottom edge.</span></span>  
  
     <span data-ttu-id="767e4-248">Ce titre s'affiche alors dans la partie supérieure du rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-248">This title will appear at the top of the report.</span></span> <span data-ttu-id="767e4-249">En l’absence d’en-tête de page défini, les éléments situés au-dessus du corps du rapport font office d’en-tête de rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-249">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
7.  <span data-ttu-id="767e4-250">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-250">Click **Run** to preview the report.</span></span>  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="767e4-251">9. enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="767e4-251">9. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="767e4-252">Pour enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="767e4-252">To save the report</span></span>  
  
1.  <span data-ttu-id="767e4-253">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-253">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="767e4-254">À partir du bouton Générateur de rapports , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="767e4-254">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="767e4-255">Dans **Nom**, tapez **Histogramme des commandes client**.</span><span class="sxs-lookup"><span data-stu-id="767e4-255">In **Name**, type **Sales Order Column Chart**.</span></span>  
  
4.  <span data-ttu-id="767e4-256">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="767e4-256">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="767e4-257">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="767e4-257">Next Steps</span></span>  
 <span data-ttu-id="767e4-258">Vous avez terminé le didacticiel Ajout d'un histogramme à un rapport.</span><span class="sxs-lookup"><span data-stu-id="767e4-258">You have successfully completed the Adding a Column Chart to Your Report tutorial.</span></span> <span data-ttu-id="767e4-259">Pour en savoir plus sur les graphiques, consultez [Graphiques &#40;Générateur de rapports et SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) et [Graphiques sparkline et barres de données &#40;Générateur de rapports et SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="767e4-259">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="767e4-260">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="767e4-260">See Also</span></span>  
 <span data-ttu-id="767e4-261">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="767e4-261">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="767e4-262">Générateur de rapports dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="767e4-262">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
