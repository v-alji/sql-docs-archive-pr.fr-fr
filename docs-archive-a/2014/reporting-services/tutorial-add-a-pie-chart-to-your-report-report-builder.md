---
title: 'Didacticiel : ajouter un graphique à secteurs à un rapport (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eaadf7bf-c312-428a-b214-0a1fbf959c3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 318370b185dcd75a8c3c54be49c47756bad5f3c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704783"
---
# <a name="tutorial-add-a-pie-chart-to-your-report-report-builder"></a><span data-ttu-id="797d1-102">Didacticiel : ajouter un graphique à secteurs à un rapport (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="797d1-102">Tutorial: Add a Pie Chart to Your Report (Report Builder)</span></span>
  <span data-ttu-id="797d1-103">Les graphiques à secteurs et les graphiques en anneau affichent des données sous la forme d'une proportion de la totalité.</span><span class="sxs-lookup"><span data-stu-id="797d1-103">Pie charts and doughnut charts display data as a proportion of the whole.</span></span> <span data-ttu-id="797d1-104">Les graphiques en secteurs sont utilisés le plus souvent pour faire des comparaisons entre des groupes.</span><span class="sxs-lookup"><span data-stu-id="797d1-104">Pie charts are most commonly used to make comparisons between groups.</span></span> <span data-ttu-id="797d1-105">Les graphique à secteurs et les graphiques en anneau, ainsi que les graphiques en pyramide et les graphiques en entonnoir, constituent un groupe de graphiques connus sous le nom de graphiques à base de formes.</span><span class="sxs-lookup"><span data-stu-id="797d1-105">Pie and doughnut charts, along with pyramid and funnel charts, constitute a group of charts known as shape charts.</span></span> <span data-ttu-id="797d1-106">Les graphiques à base de formes n'ont pas d'axe.</span><span class="sxs-lookup"><span data-stu-id="797d1-106">Shape charts have no axes.</span></span> <span data-ttu-id="797d1-107">Lorsqu'un champ numérique est placé sur un graphique à base de formes, le graphique calcule le pourcentage de chaque valeur par rapport au total.</span><span class="sxs-lookup"><span data-stu-id="797d1-107">When a numeric field is dropped on a shape chart, the chart calculates the percentage of each value to the total.</span></span>  
  
 <span data-ttu-id="797d1-108">Lorsqu'un graphique à secteurs comporte trop de points de données, vos étiquettes de points de données peuvent devenir illisibles.</span><span class="sxs-lookup"><span data-stu-id="797d1-108">If there are too many data points on a pie chart, your data point labels might be too crowded to read.</span></span> <span data-ttu-id="797d1-109">Dans ce cas, envisagez d’utiliser un graphique en courbes.</span><span class="sxs-lookup"><span data-stu-id="797d1-109">In that case, consider using a line chart.</span></span> <span data-ttu-id="797d1-110">Pensez à utiliser des graphiques à secteurs uniquement lorsque vos données ont été agrégées en quelques points de données.</span><span class="sxs-lookup"><span data-stu-id="797d1-110">Consider using pie charts only after you have aggregated your data into a few data points.</span></span>  
  
 <span data-ttu-id="797d1-111">L'illustration suivante montre le graphique à secteurs que vous allez créer.</span><span class="sxs-lookup"><span data-stu-id="797d1-111">The following illustration shows the pie chart you will create.</span></span>  
  
 <span data-ttu-id="797d1-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span><span class="sxs-lookup"><span data-stu-id="797d1-112">![rs_TutorialPieChartConcave](../../2014/tutorials/media/rs-tutorialpiechartconcave.gif "rs_TutorialPieChartConcave")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="797d1-113">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="797d1-113">What You Will Learn</span></span>  
 <span data-ttu-id="797d1-114">Dans ce didacticiel, vous apprendrez à :</span><span class="sxs-lookup"><span data-stu-id="797d1-114">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="797d1-115">Créer un graphique à secteurs à partir de l'Assistant Graphique</span><span class="sxs-lookup"><span data-stu-id="797d1-115">Create a Pie Chart from the Chart Wizard</span></span>](#Chart)  
  
2.  [<span data-ttu-id="797d1-116">Choisir le type de graphique</span><span class="sxs-lookup"><span data-stu-id="797d1-116">Choose the Chart Type</span></span>](#ChartType)  
  
3.  [<span data-ttu-id="797d1-117">Afficher des pourcentages dans chaque secteur</span><span class="sxs-lookup"><span data-stu-id="797d1-117">Display Percentages in Each Slice</span></span>](#Percentages)  
  
4.  [<span data-ttu-id="797d1-118">Combiner de petits secteurs en un secteur</span><span class="sxs-lookup"><span data-stu-id="797d1-118">Combine Small Slices into One Slice</span></span>](#CombineSlices)  
  
5.  [<span data-ttu-id="797d1-119">Personnaliser l'effet de dessin</span><span class="sxs-lookup"><span data-stu-id="797d1-119">Customize the Drawing Effect</span></span>](#DrawingEffect)  
  
6.  [<span data-ttu-id="797d1-120">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="797d1-120">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="797d1-121">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="797d1-121">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="797d1-122">Dans ce didacticiel, les étapes de l'Assistant sont consolidées en deux procédures.</span><span class="sxs-lookup"><span data-stu-id="797d1-122">In this tutorial, the steps for the wizard are consolidated into two procedures.</span></span> <span data-ttu-id="797d1-123">Pour obtenir des instructions pas à pas sur l’accès à un serveur de rapports, l’ajout d’une source de données et l’ajout d’un dataset, consultez le premier didacticiel de cette série : [Didacticiel : création d’un rapport de tableau de base &#40;Générateur de rapports&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="797d1-123">For step-by-step instructions about how to browse to a report server, add a data source, and add a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="797d1-124">Durée estimée pour effectuer le didacticiel : 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="797d1-124">Estimated time to complete this tutorial: 10 minutes</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="797d1-125">Spécifications</span><span class="sxs-lookup"><span data-stu-id="797d1-125">Requirements</span></span>  
 <span data-ttu-id="797d1-126">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="797d1-126">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-pie-chart-from-the-chart-wizard"></a><a name="Chart"></a><span data-ttu-id="797d1-127">1. créer un graphique à secteurs à partir de l’Assistant graphique</span><span class="sxs-lookup"><span data-stu-id="797d1-127">1. Create a Pie Chart from the Chart Wizard</span></span>  
 <span data-ttu-id="797d1-128">Dans la boîte de dialogue Mise en route, utilisez l'Assistant Graphique pour créer un dataset incorporé, choisissez une source de données partagée et créez un graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="797d1-128">From the Getting Started dialog box, use the Chart Wizard to create an embedded dataset, choose a shared data source, and create a pie chart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="797d1-129">Dans ce didacticiel, la requête contient les valeurs de données, afin qu'il ne soit pas nécessaire de disposer d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="797d1-129">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="797d1-130">Cela rend la requête assez longue.</span><span class="sxs-lookup"><span data-stu-id="797d1-130">This makes the query quite long.</span></span> <span data-ttu-id="797d1-131">Dans un environnement métier, une requête ne contient pas les données.</span><span class="sxs-lookup"><span data-stu-id="797d1-131">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="797d1-132">Ceci est nécessaire à des fins de formation uniquement.</span><span class="sxs-lookup"><span data-stu-id="797d1-132">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-chart-report"></a><span data-ttu-id="797d1-133">Pour créer un rapport de graphique</span><span class="sxs-lookup"><span data-stu-id="797d1-133">To create a new chart report</span></span>  
  
1.  <span data-ttu-id="797d1-134">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur **Générateur de rapports Microsoft SQL Server 2012**, puis cliquez sur **Générateur de rapports version**.</span><span class="sxs-lookup"><span data-stu-id="797d1-134">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="797d1-135">La boîte de dialogue Mise en route s'affiche.</span><span class="sxs-lookup"><span data-stu-id="797d1-135">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="797d1-136"> Si la boîte de dialogue Mise en route ne s'affiche pas, à partir du bouton Générateur de rapports, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="797d1-136">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="797d1-137">Dans le volet gauche, assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="797d1-137">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="797d1-138">Dans le volet droit, cliquez sur **Assistant Graphique**.</span><span class="sxs-lookup"><span data-stu-id="797d1-138">In the right pane, click **Chart Wizard**.</span></span>  
  
4.  <span data-ttu-id="797d1-139">Dans la page **choisir un DataSet** , cliquez sur **créer un DataSet**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="797d1-139">On the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="797d1-140">Dans la page **Choisir une connexion à une source de données** , sélectionnez une source de données existante ou naviguez jusqu’au serveur de rapports, sélectionnez une source de données, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="797d1-140">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="797d1-141">Vous devrez peut-être entrer un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="797d1-141">You may need to enter a user name and password.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="797d1-142">La source de données que vous choisissez n'a pas d'importance, tant que vous disposez des autorisations appropriées.</span><span class="sxs-lookup"><span data-stu-id="797d1-142">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="797d1-143">Vous n'allez pas récupérer de données à partir de la source de données.</span><span class="sxs-lookup"><span data-stu-id="797d1-143">You will not be getting data from the data source.</span></span> <span data-ttu-id="797d1-144">Pour plus d’informations, consultez [Autres manières d’obtenir une connexion de données &#40;Générateur de rapports&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="797d1-144">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
6.  <span data-ttu-id="797d1-145">Sur la page **créer une requête** , cliquez sur **modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="797d1-145">On the **Design a Query** page, click **Edit as Text**.</span></span>  
  
7.  <span data-ttu-id="797d1-146">Collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="797d1-146">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Advanced Digital Camera' AS Product, CAST(254995.21 AS money) AS Sales  
    UNION SELECT 'Slim Digital Camera' AS Product, CAST(164499.04 AS money) AS Sales  
    UNION SELECT 'SLR Digital Camera' AS Product, CAST(782176.79 AS money) AS Sales  
    UNION SELECT 'Lens Adapter' AS Product, CAST(36333.08 AS money) AS Sales  
    UNION SELECT 'Macro Zoom Lens' AS Product, CAST(40199.3 AS money) AS Sales  
    UNION SELECT 'USB Cable' AS Product, CAST(53245.5 AS money) AS Sales  
    UNION SELECT 'Independent Filmmaker Camcorder' AS Product, CAST(452288.0 AS money) AS Sales  
    UNION SELECT 'Full Frame Digital Camera' AS Product, CAST(247250.85 AS money) AS Sales  
    ```  
  
8.  <span data-ttu-id="797d1-147">(Facultatif) Cliquez sur le bouton Exécuter (**!**) pour voir les données sur lesquelles votre graphique sera basé.</span><span class="sxs-lookup"><span data-stu-id="797d1-147">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>  
  
9. <span data-ttu-id="797d1-148">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="797d1-148">Click **Next**.</span></span>  
  
##  <a name="2-choose-the-chart-type"></a><a name="ChartType"></a><span data-ttu-id="797d1-149">2. choisir le type de graphique</span><span class="sxs-lookup"><span data-stu-id="797d1-149">2. Choose the Chart Type</span></span>  
 <span data-ttu-id="797d1-150">Vous avez le choix entre plusieurs types de graphiques prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="797d1-150">You can choose from a variety of predefined chart types.</span></span>  
  
#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="797d1-151">Pour ajouter un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="797d1-151">To add a pie chart</span></span>  
  
1.  <span data-ttu-id="797d1-152">Dans la page **choisir un type de graphique** , cliquez sur **secteurs**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="797d1-152">On the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span> <span data-ttu-id="797d1-153">La page **Organiser les champs du graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="797d1-153">The **Arrange chart fields** page opens.</span></span>  
  
     <span data-ttu-id="797d1-154">Dans la page **Organiser les champs du graphique** , faites glisser le champ Product vers le volet **Catégories** .</span><span class="sxs-lookup"><span data-stu-id="797d1-154">On the **Arrange chart fields** page, drag the Product field to the **Categories** pane.</span></span> <span data-ttu-id="797d1-155">Les catégories définissent le nombre de secteurs du graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="797d1-155">Categories define the number of slices in the pie chart.</span></span> <span data-ttu-id="797d1-156">Dans cet exemple, il y a huit secteurs, un pour chaque produit.</span><span class="sxs-lookup"><span data-stu-id="797d1-156">In this example, there will be eight slices, one for each product.</span></span>  
  
2.  <span data-ttu-id="797d1-157">Faites glisser le champ Sales vers le volet **Valeurs** .</span><span class="sxs-lookup"><span data-stu-id="797d1-157">Drag the Sales field to the **Values** pane.</span></span> <span data-ttu-id="797d1-158">Le champ Sales représente le montant des ventes réalisées pour la sous-catégorie.</span><span class="sxs-lookup"><span data-stu-id="797d1-158">Sales represents the sales amount for the subcategory.</span></span> <span data-ttu-id="797d1-159">Le volet **Valeurs** affiche `[Sum(Sales)]` , car le graphique affiche l’agrégat pour chaque produit.</span><span class="sxs-lookup"><span data-stu-id="797d1-159">The **Values** pane displays `[Sum(Sales)]` because the chart displays the aggregate for each product.</span></span>  
  
3.  <span data-ttu-id="797d1-160">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="797d1-160">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="797d1-161">Dans la page **choisir un style** , dans le volet styles, sélectionnez un style.</span><span class="sxs-lookup"><span data-stu-id="797d1-161">On the **Choose a style** page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="797d1-162">Un style spécifie un style de police, un jeu de couleurs et un style de bordure.</span><span class="sxs-lookup"><span data-stu-id="797d1-162">A style specifies a font style, a set of colors, and a border style.</span></span> <span data-ttu-id="797d1-163">Lorsque vous sélectionnez un style, le volet Aperçu affiche un aperçu du graphique avec ce style.</span><span class="sxs-lookup"><span data-stu-id="797d1-163">When you select a style, the Preview pane displays a sample of the chart with that style.</span></span>  
  
5.  <span data-ttu-id="797d1-164">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="797d1-164">Click **Finish**.</span></span>  
  
     <span data-ttu-id="797d1-165">Le graphique est ajouté à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="797d1-165">The chart is added to the design surface.</span></span>  
  
6.  <span data-ttu-id="797d1-166">Cliquez sur le graphique pour afficher ses poignées.</span><span class="sxs-lookup"><span data-stu-id="797d1-166">Click the chart to display the chart handles.</span></span> <span data-ttu-id="797d1-167">Faites glisser l'angle inférieur droit du graphique pour augmenter sa taille.</span><span class="sxs-lookup"><span data-stu-id="797d1-167">Drag the bottom-right corner of the chart to increase the size of the chart.</span></span> <span data-ttu-id="797d1-168">Notez que la taille de l'aire de conception du rapport augmente pour s'adapter à la taille du graphique.</span><span class="sxs-lookup"><span data-stu-id="797d1-168">Note that the report design surface increases in size to accommodate the chart size.</span></span>  
  
7.  <span data-ttu-id="797d1-169">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-169">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="797d1-170">Le rapport affiche le graphique à secteurs avec huit secteurs, un pour chaque produit.</span><span class="sxs-lookup"><span data-stu-id="797d1-170">The report displays the pie chart with eight slices, one for each product.</span></span> <span data-ttu-id="797d1-171">La taille de chaque secteur représente les ventes de ce produit.</span><span class="sxs-lookup"><span data-stu-id="797d1-171">The size of each slice represents the sales for that product.</span></span> <span data-ttu-id="797d1-172">Trois des secteurs sont assez fins.</span><span class="sxs-lookup"><span data-stu-id="797d1-172">Three of the slices are quite thin.</span></span>  
  
##  <a name="3-display-percentages-in-each-slice"></a><a name="Percentages"></a><span data-ttu-id="797d1-173">3. afficher les pourcentages dans chaque secteur</span><span class="sxs-lookup"><span data-stu-id="797d1-173">3. Display Percentages in Each Slice</span></span>  
 <span data-ttu-id="797d1-174">Sur chaque secteur du graphique, vous pouvez afficher le pourcentage de ce secteur par rapport à l'ensemble.</span><span class="sxs-lookup"><span data-stu-id="797d1-174">On each slice of the pie, you can display a percentage for this slice compared to the whole pie.</span></span>  
  
#### <a name="to-display-percentages-in-each-slice-of-the-pie-chart"></a><span data-ttu-id="797d1-175">Pour afficher des pourcentages dans chaque secteur du graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="797d1-175">To display percentages in each slice of the pie chart</span></span>  
  
1.  <span data-ttu-id="797d1-176">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-176">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="797d1-177">Cliquez avec le bouton droit sur le graphique à secteurs, puis cliquez sur **Afficher les étiquettes de données**.</span><span class="sxs-lookup"><span data-stu-id="797d1-177">Right-click the pie chart and click **Show Data Labels**.</span></span> <span data-ttu-id="797d1-178">Les étiquettes de données s'affichent sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="797d1-178">The data labels appear on the chart.</span></span>  
  
3.  <span data-ttu-id="797d1-179">Cliquez avec le bouton droit sur une étiquette, puis cliquez sur Propriétés de l’étiquette de la **série**.</span><span class="sxs-lookup"><span data-stu-id="797d1-179">Right-click a label, and then click **Series Label Properties**.</span></span>  
  
4.  <span data-ttu-id="797d1-180">Dans données de l’étiquette, dans la zone de liste déroulante, sélectionnez **#PERCENT**.</span><span class="sxs-lookup"><span data-stu-id="797d1-180">In Label data, from the drop-down box, select **#PERCENT**.</span></span>  
  
     <span data-ttu-id="797d1-181">Pour afficher les valeurs sous forme de pourcentages, la propriété UseValueAsLabel doit avoir la valeur false.</span><span class="sxs-lookup"><span data-stu-id="797d1-181">To display values as percentages, the UseValueAsLabel property must be false.</span></span> <span data-ttu-id="797d1-182">Si vous êtes invité à définir cette valeur dans la boîte de dialogue **Confirmer l’action** , cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="797d1-182">If you are prompted to set this value in the **Confirm Action** dialog, click **Yes**.</span></span>  
  
5.  <span data-ttu-id="797d1-183">Facultatif Pour spécifier le nombre de décimales affichées sur l’étiquette, tapez `#PERCENT{Pn}` où *n* est le nombre de décimales à afficher.</span><span class="sxs-lookup"><span data-stu-id="797d1-183">(Optional) To specify how many decimal places the label shows, type `#PERCENT{Pn}` where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="797d1-184">Par exemple, pour ne pas afficher de décimales, tapez `#PERCENT{P0}` .</span><span class="sxs-lookup"><span data-stu-id="797d1-184">For example, to display no decimal places, type `#PERCENT{P0}`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="797d1-185">L’option**Format de nombre** de la boîte de dialogue **Propriétés de l’étiquette de la série** n’a aucun effet quand vous mettez en forme des pourcentages.</span><span class="sxs-lookup"><span data-stu-id="797d1-185">**Number Format** in the **Series Label Properties** dialog box has no effect when you format percentages.</span></span> <span data-ttu-id="797d1-186">Elle met uniquement en forme les étiquettes sous forme de pourcentages, mais ne calcule pas le pourcentage représenté par chaque secteur du graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="797d1-186">This formats the labels as percentages, but does not calculate the percentage of the pie that each slice represents.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="797d1-187">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-187">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="797d1-188">Le rapport affiche le pourcentage de chaque secteur par rapport à l'ensemble.</span><span class="sxs-lookup"><span data-stu-id="797d1-188">The report displays the percentage of the whole for each pie slice.</span></span>  
  
##  <a name="4-combine-small-slices-into-one-slice"></a><a name="CombineSlices"></a><span data-ttu-id="797d1-189">4. combiner les petits secteurs en un seul secteur</span><span class="sxs-lookup"><span data-stu-id="797d1-189">4. Combine Small Slices into One Slice</span></span>  
 <span data-ttu-id="797d1-190">Trois des secteurs du graphique à secteurs sont assez petits.</span><span class="sxs-lookup"><span data-stu-id="797d1-190">Three of the slices in the pie are quite small.</span></span> <span data-ttu-id="797d1-191">Vous pouvez combiner plusieurs petits secteurs en un secteur plus grand qui représente l'ensemble de ces secteurs.</span><span class="sxs-lookup"><span data-stu-id="797d1-191">You can combine multiple small slices into one larger slice that represents all of them.</span></span>  
  
#### <a name="to-combine-any-slices-on-the-pie-chart-smaller-than-5-percent-into-one-slice"></a><span data-ttu-id="797d1-192">Pour regrouper dans un même secteur les secteurs du graphique représentant moins de 5 pour cent</span><span class="sxs-lookup"><span data-stu-id="797d1-192">To combine any slices on the pie chart smaller than 5 percent into one slice</span></span>  
  
1.  <span data-ttu-id="797d1-193">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-193">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="797d1-194">Sous l’onglet **affichage** , dans le groupe **Afficher/masquer** , sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="797d1-194">On the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="797d1-195">Dans l'aire de conception, cliquez sur un secteur du graphique.</span><span class="sxs-lookup"><span data-stu-id="797d1-195">On the design surface, click on any slice of the pie chart.</span></span> <span data-ttu-id="797d1-196">Les propriétés de la série sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="797d1-196">The properties for the series are displayed in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="797d1-197">Dans la section **Général** , développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="797d1-197">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="797d1-198">Définissez la propriété **CollectedStyle** sur **SingleSlice**.</span><span class="sxs-lookup"><span data-stu-id="797d1-198">Set the **CollectedStyle** property to **SingleSlice**.</span></span>  
  
6.  <span data-ttu-id="797d1-199">Vérifiez que la propriété **CollectedThreshold** a la valeur 5.</span><span class="sxs-lookup"><span data-stu-id="797d1-199">Verify that the **CollectedThreshold** property is set to 5.</span></span>  
  
7.  <span data-ttu-id="797d1-200">Vérifiez que la propriété **CollectedThresholdUsePercent** a la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="797d1-200">Verify that the **CollectedThresholdUsePercent** property is set to **True**.</span></span>  
  
8.  <span data-ttu-id="797d1-201">Dans le ruban, sous l’onglet dossier de **démarrage** , cliquez sur **exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-201">On the Ribbon, on the **Home** tab, click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="797d1-202">Dans la légende, la catégorie « Autre » est désormais présente.</span><span class="sxs-lookup"><span data-stu-id="797d1-202">In the legend, the category "Other" now exists.</span></span> <span data-ttu-id="797d1-203">Le nouveau secteur regroupe tous les secteurs de moins de 5 % dans un seul secteur qui représente 6 % de l'ensemble.</span><span class="sxs-lookup"><span data-stu-id="797d1-203">The new pie slice combines all the slices that were under 5% into one slice that is 6% of the whole pie.</span></span>  
  
##  <a name="5-customize-the-drawing-effect"></a><a name="DrawingEffect"></a><span data-ttu-id="797d1-204">5. personnaliser l’effet de dessin</span><span class="sxs-lookup"><span data-stu-id="797d1-204">5. Customize the Drawing Effect</span></span>  
 <span data-ttu-id="797d1-205">Dans l'Assistant Graphique, le style par défaut d'un graphique à secteurs est Océan, qui représente un effet de dessin concave.</span><span class="sxs-lookup"><span data-stu-id="797d1-205">In the Chart Wizard, the default style for a pie chart is Ocean, which features a Concave drawing effect.</span></span> <span data-ttu-id="797d1-206">Vous pouvez le changer après avoir exécuté l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="797d1-206">You can change that after you run the wizard.</span></span>  
  
#### <a name="to-add-a-drawing-effect-to-the-pie-chart"></a><span data-ttu-id="797d1-207">Pour ajouter un effet de dessin au graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="797d1-207">To add a drawing effect to the pie chart</span></span>  
  
1.  <span data-ttu-id="797d1-208">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-208">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="797d1-209">Si le volet Propriétés n’est pas déjà ouvert, sous l’onglet **affichage** , sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="797d1-209">If the Properties pane is not already opened, on the **View** tab, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="797d1-210">Double-cliquez sur le graphique à secteurs lui-même.</span><span class="sxs-lookup"><span data-stu-id="797d1-210">Double-click the pie chart itself.</span></span> <span data-ttu-id="797d1-211">Les propriétés de série du graphique à secteurs sont affichées dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="797d1-211">The series properties for the pie chart are shown in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="797d1-212">Dans le volet Propriétés, développez le nœud **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="797d1-212">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
5.  <span data-ttu-id="797d1-213">Définissez **PieDrawingStyle** sur **SoftEdge**.</span><span class="sxs-lookup"><span data-stu-id="797d1-213">Set the **PieDrawingStyle** to **SoftEdge**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="797d1-214">Les effets de dessin et les effets en trois dimensions sont des options exclusives.</span><span class="sxs-lookup"><span data-stu-id="797d1-214">Drawing effects and three-dimensional effects are exclusive options.</span></span> <span data-ttu-id="797d1-215">Si un graphique a des effets en trois dimensions, **PieDrawingStyle** n’est pas disponible dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="797d1-215">If a chart has three-dimensional effects applied, **PieDrawingStyle** is not available on the Properties pane.</span></span>  
  
6.  <span data-ttu-id="797d1-216">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-216">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="797d1-217">L'illustration suivante montre le graphique à secteurs avec l'effet de contour adouci.</span><span class="sxs-lookup"><span data-stu-id="797d1-217">The following illustration shows the pie chart with the soft edge effect.</span></span>  
  
 <span data-ttu-id="797d1-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span><span class="sxs-lookup"><span data-stu-id="797d1-218">![rs_TutorialPieChartSoftEdge](../../2014/tutorials/media/rs-tutorialpiechartsoftedge.gif "rs_TutorialPieChartSoftEdge")</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="797d1-219">6. Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="797d1-219">6. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="797d1-220">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="797d1-220">To add a report title</span></span>  
  
1.  <span data-ttu-id="797d1-221">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="797d1-221">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="797d1-222">Tapez **Ventes d’appareils photo et de caméscopes**, appuyez sur Entrée, puis tapez **En pourcentage du total des ventes**, afin d’obtenir ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="797d1-222">Type **Camera and Camcorder Sales**, press ENTER, and then type **As a Percentage of Total Sales**, so it looks like this:</span></span>  
  
     <span data-ttu-id="797d1-223">**Ventes d’appareils photo et de caméscopes**</span><span class="sxs-lookup"><span data-stu-id="797d1-223">**Camera and Camcorder Sales**</span></span>  
  
     <span data-ttu-id="797d1-224">**En pourcentage du total des ventes**</span><span class="sxs-lookup"><span data-stu-id="797d1-224">**As a Percentage of Total Sales**</span></span>  
  
3.  <span data-ttu-id="797d1-225">Sélectionnez **ventes d’appareils photo et de caméscopes**, puis cliquez sur le bouton **gras** dans la section **police** de l’onglet dossier de **démarrage** du ruban.</span><span class="sxs-lookup"><span data-stu-id="797d1-225">Select **Camera and Camcorder Sales**, and click the **Bold** button from the **Font** section of the **Home** tab of the ribbon.</span></span>  
  
4.  <span data-ttu-id="797d1-226">Sélectionnez **en pourcentage du total des ventes**, puis dans la section **police** de l’onglet dossier de **départ** , définissez la taille de police sur **10**.</span><span class="sxs-lookup"><span data-stu-id="797d1-226">Select **As a Percentage of Total Sales**, and in the **Font** section on the **Home** tab, set the font size to **10**.</span></span>  
  
5.  <span data-ttu-id="797d1-227">(Facultatif) Vous devrez peut-être agrandir la zone de texte Titre pour contenir les deux lignes de texte.</span><span class="sxs-lookup"><span data-stu-id="797d1-227">(Optional) You may need to make the Title text box taller to accommodate the two lines of text.</span></span>  
  
     <span data-ttu-id="797d1-228">Ce titre s'affiche alors dans la partie supérieure du rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-228">This title will appear at the top of the report.</span></span> <span data-ttu-id="797d1-229">En l’absence d’en-tête de page défini, les éléments situés au-dessus du corps du rapport font office d’en-tête de rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-229">When there is no page header defined, items at the top of the report body are the equivalent of a report header.</span></span>  
  
6.  <span data-ttu-id="797d1-230">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-230">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="797d1-231">7. enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="797d1-231">7. Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="797d1-232">Pour enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="797d1-232">To save the report</span></span>  
  
1.  <span data-ttu-id="797d1-233">Basculez en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-233">Switch to report design view.</span></span>  
  
2.  <span data-ttu-id="797d1-234">À partir du bouton Générateur de rapports , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="797d1-234">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="797d1-235">Dans **Nom**, tapez **Graphique à secteurs des ventes**.</span><span class="sxs-lookup"><span data-stu-id="797d1-235">In **Name**, type **Sales Pie Chart**.</span></span>  
  
4.  <span data-ttu-id="797d1-236">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="797d1-236">Click **Save**.</span></span>  
  
 <span data-ttu-id="797d1-237">Votre rapport est enregistré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="797d1-237">Your report is saved on the report server.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="797d1-238">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="797d1-238">Next Steps</span></span>  
 <span data-ttu-id="797d1-239">Vous avez terminé le didacticiel d'ajout d'un graphique à secteurs à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="797d1-239">You have successfully completed the Adding a Pie Chart to Your Report tutorial.</span></span> <span data-ttu-id="797d1-240">Pour en savoir plus sur les graphiques, consultez [Graphiques &#40;Générateur de rapports et SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) et [Graphiques sparkline et barres de données &#40;Générateur de rapports et SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="797d1-240">To learn more about charts, see [Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) and [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="797d1-241">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="797d1-241">See Also</span></span>  
 <span data-ttu-id="797d1-242">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="797d1-242">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="797d1-243">Générateur de rapports dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="797d1-243">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
