---
title: 'Didacticiel : ajout d’un indicateur de performance clé à un rapport (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1bf77859-0b33-4f40-abaf-ebeeb6ebb1f8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 405978721068583597adf5c4257978a222121078
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704768"
---
# <a name="tutorial-adding-a-kpi-to-your-report-report-builder"></a><span data-ttu-id="2a9ef-102">Didacticiel : ajout d'un indicateur de performance clé à un rapport (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="2a9ef-102">Tutorial: Adding a KPI to Your Report (Report Builder)</span></span>
  <span data-ttu-id="2a9ef-103">Un indicateur de performance clé (KPI) est une valeur mesurable qui revêt une importance significative sur le plan opérationnel.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-103">A key performance indicator (KPI) is a measurable value that has business significance.</span></span> <span data-ttu-id="2a9ef-104">Ce didacticiel vous apprend comment inclure un indicateur de performance clé dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-104">This tutorial teaches you how to include a (KPI) in a report.</span></span> <span data-ttu-id="2a9ef-105">Dans ce scénario, le récapitulatif des ventes par sous-catégories de produits est l'indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-105">In this scenario, the sales summary by product subcategories is the KPI.</span></span> <span data-ttu-id="2a9ef-106">L'état actuel de l'indicateur de performance clé est indiqué à l'aide de couleurs, de jauges et d'indicateurs.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-106">The current state of the KPI is shown by using colors, gauges, and indicators.</span></span>  
  
 <span data-ttu-id="2a9ef-107">L'illustration suivante montre le rapport que vous allez créer.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-107">The following illustration shows the report that you will create.</span></span>  
  
 <span data-ttu-id="2a9ef-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span><span class="sxs-lookup"><span data-stu-id="2a9ef-108">![rs_AddKPITutorial](../../2014/tutorials/media/rs-addkpitutorial.gif "rs_AddKPITutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="2a9ef-109">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="2a9ef-109">What You Will Learn</span></span>  
 <span data-ttu-id="2a9ef-110">Dans ce didacticiel, vous allez apprendre à ajouter un indicateur de performance clé en définissant la couleur d'arrière-plan des cellules de tableau selon la valeur de la cellule. Vous apprendrez à ajouter et configurer une jauge et un indicateur.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-110">In this tutorial, you will learn to add a KPI by setting the background color of table cells based on cell value and add and configure a gauge and an indicator.</span></span> <span data-ttu-id="2a9ef-111">Vous apprendrez également à écrire l'expression qui définit la couleur d'arrière-plan des cellules de tableau.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-111">You also learn to write the expression that sets the background color of the table cells.</span></span>  
  
 <span data-ttu-id="2a9ef-112">Ce didacticiel contient les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="2a9ef-112">This tutorial contains the following procedures:</span></span>  
  
1.  [<span data-ttu-id="2a9ef-113">Créer un rapport de tableau et un dataset à partir de l'Assistant Tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="2a9ef-113">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Table)  
  
2.  [<span data-ttu-id="2a9ef-114">Organiser les données, choisir la mise en page et le style à partir de l'Assistant Tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="2a9ef-114">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="2a9ef-115">Utiliser les couleurs d'arrière-plan pour afficher un indicateur de performance clé</span><span class="sxs-lookup"><span data-stu-id="2a9ef-115">Use Background Colors to Display a KPI</span></span>](#BackgroundColors)  
  
4.  [<span data-ttu-id="2a9ef-116">Afficher un indicateur de performance clé à l'aide d'une jauge</span><span class="sxs-lookup"><span data-stu-id="2a9ef-116">Display a KPI by Using a Gauge</span></span>](#Gauge)  
  
5.  [<span data-ttu-id="2a9ef-117">Afficher un indicateur de performance clé à l'aide d'un indicateur</span><span class="sxs-lookup"><span data-stu-id="2a9ef-117">Display a KPI by Using an Indicator</span></span>](#Indicator)  
  
6.  [<span data-ttu-id="2a9ef-118">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="2a9ef-118">Add a Report Title</span></span>](#Title)  
  
7.  [<span data-ttu-id="2a9ef-119">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="2a9ef-119">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="2a9ef-120">Dans ce didacticiel, les étapes de l'Assistant sont consolidées sous forme de deux procédures : l'une pour créer le dataset, et l'autre pour créer une table.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-120">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="2a9ef-121">Pour obtenir des instructions pas à pas sur l’accès à un serveur de rapports, le choix d’une source de données, la création d’un dataset et l’exécution de l’Assistant, consultez le premier didacticiel de cette série : [Didacticiel : création d’un rapport de tableau de base &#40;Générateur de rapports&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="2a9ef-121">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="2a9ef-122">Durée estimée pour effectuer ce didacticiel : 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-122">Estimated time to complete this tutorial: 15 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a9ef-123">Spécifications</span><span class="sxs-lookup"><span data-stu-id="2a9ef-123">Requirements</span></span>  
 <span data-ttu-id="2a9ef-124">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="2a9ef-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Table"></a><span data-ttu-id="2a9ef-125">1. créer un rapport de tableau et un DataSet à partir de l’Assistant tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="2a9ef-125">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="2a9ef-126">Dans la boîte de dialogue **prise en main** , choisissez une source de données partagée, créez un dataset incorporé et affichez les données dans une table.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-126">From the **Getting Started** dialog box, choose a shared data source, create an embedded dataset, and display the data in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a9ef-127">Dans ce didacticiel, la requête contient les valeurs de données, afin qu'il ne soit pas nécessaire de disposer d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-127">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="2a9ef-128">Cela rend la requête assez longue.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-128">This makes the query quite long.</span></span> <span data-ttu-id="2a9ef-129">Dans un environnement métier, une requête ne contient pas les données.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="2a9ef-130">Ceci est nécessaire à des fins de formation uniquement.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-table"></a><span data-ttu-id="2a9ef-131">Pour créer une table</span><span class="sxs-lookup"><span data-stu-id="2a9ef-131">To create a new table</span></span>  
  
1.  <span data-ttu-id="2a9ef-132">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur **Générateur de rapports Microsoft SQL Server 2012**, puis cliquez sur **Générateur de rapports version**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="2a9ef-133">La boîte de dialogue **prise en main** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-133">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a9ef-134">Si la boîte de dialogue **prise en main** n’apparaît pas, à partir du bouton Générateur de rapports, cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-134">If the **Getting Started** dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="2a9ef-135">Dans le volet gauche, assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="2a9ef-136">Dans le volet droit, cliquez sur **Assistant Tableau ou matrice**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="2a9ef-137">Dans la page Choisir un dataset , cliquez sur **Créer un dataset**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-137">On the Choose a dataset page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="2a9ef-138">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="2a9ef-139">Dans la page **choisir une connexion à une source de données** , sélectionnez une source de données existante ou accédez au serveur de rapports et sélectionnez une source de données.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source.</span></span> <span data-ttu-id="2a9ef-140">Si aucune source de données n’est disponible ou que vous n’avez pas accès à un serveur de rapports, vous pouvez utiliser une source de données incorporée à la place.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-140">If there no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="2a9ef-141">Pour plus d’informations, consultez [Didacticiel : création d’un rapport de tableau de base &#40;Générateur de rapports&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="2a9ef-141">For more information, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="2a9ef-142">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="2a9ef-143">Dans la page **Créer une requête** , cliquez sur **Modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="2a9ef-144">Copiez et collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="2a9ef-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
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
  
10. <span data-ttu-id="2a9ef-145">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="2a9ef-146">2. organiser les données, choisir la disposition et le style à partir de l’Assistant tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="2a9ef-146">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="2a9ef-147">Utilisez l'Assistant pour obtenir une conception initiale dans laquelle afficher les données.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="2a9ef-148">Le volet de visualisation de l'Assistant vous aide à visualiser le résultat du regroupement des données avant de terminer la conception de la table ou de la matrice.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-choose-a-layout-and-a-style"></a><span data-ttu-id="2a9ef-149">Pour organiser les données en groupes, choisir une mise en page et un style</span><span class="sxs-lookup"><span data-stu-id="2a9ef-149">To organize data into groups, choose a layout and a style</span></span>  
  
1.  <span data-ttu-id="2a9ef-150">Dans la page Organiser les champs , faites glisser Product vers **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-150">On the Arrange fields page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="2a9ef-151">Faites glisser Quantity vers **Valeurs** et placez-le sous Product.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-151">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="2a9ef-152">Quantity est synthétisé à l'aide de la fonction Sum, la fonction de synthèse par défaut des champs numériques.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-152">Quantity is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
3.  <span data-ttu-id="2a9ef-153">Faites glisser Sales vers **Valeurs** et placez-le sous Quantity.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-153">Drag Sales to **Values** and place below Quantity.</span></span>  
  
     <span data-ttu-id="2a9ef-154">Les étapes 1, 2 et 3 spécifient les données à afficher dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-154">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="2a9ef-155">Faites glisser SalesDate vers **Groupes de lignes**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-155">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="2a9ef-156">Faites glisser Subcategory vers **Groupes de lignes** et placez-le sous SalesDate.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-156">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="2a9ef-157">Les étapes 4 et 5 organisent les valeurs des champs par date, puis par l'ensemble des ventes pour chaque date.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-157">Steps 4 and 5 organize the values for the fields first by date, and then by all sales for that date.</span></span>  
  
6.  <span data-ttu-id="2a9ef-158">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-158">Click **Next**.</span></span>  
  
     <span data-ttu-id="2a9ef-159">Lorsque vous exécutez le rapport, le tableau affiche chaque date, toutes les commandes pour chaque date et tous les produits, quantités et totaux de ventes pour chaque commande.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-159">When you run the report, the table displays each date, all orders for each date, and all products, quantities, and sales totals for each order.</span></span>  
  
7.  <span data-ttu-id="2a9ef-160">Dans la page choisir la disposition, sous **options**, vérifiez que **afficher les sous-totaux et les totaux généraux** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-160">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
8.  <span data-ttu-id="2a9ef-161">Vérifiez que **Bloqué, sous-total ci-dessous** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-161">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
9. <span data-ttu-id="2a9ef-162">Décochez l’option **Développer/Réduire les groupes**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-162">Clear the option **Expand/collapse groups**.</span></span>  
  
     <span data-ttu-id="2a9ef-163">Dans ce didacticiel, le rapport que vous créez n'utilise pas la fonctionnalité d'exploration vers le bas qui permet à un utilisateur de développer une hiérarchie de groupe parente afin d'afficher les lignes de groupes enfants et les lignes de détails.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-163">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
10. <span data-ttu-id="2a9ef-164">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-164">Click **Next**.</span></span>  
  
11. <span data-ttu-id="2a9ef-165">Dans la page Choisir un style, dans le volet Styles, sélectionnez un style.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-165">On the Choose a Style page, in the Styles pane, select a style.</span></span>  
  
     <span data-ttu-id="2a9ef-166">L'illustration du rapport finalisé montre le rapport dans le style Océan.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-166">The illustration of the completed report shows the report using the Ocean style.</span></span>  
  
12. <span data-ttu-id="2a9ef-167">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-167">Click **Finish**.</span></span>  
  
     <span data-ttu-id="2a9ef-168">Le tableau est ajouté à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-168">The table is added to the design surface.</span></span> <span data-ttu-id="2a9ef-169">Le tableau possède cinq colonnes et cinq lignes.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-169">The table has five columns and five rows.</span></span> <span data-ttu-id="2a9ef-170">Le volet Groupes de lignes affiche trois lignes : SalesDate, Subcategory et Details.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-170">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="2a9ef-171">Les données de détail sont toutes les données récupérées par la requête de dataset.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-171">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
13. <span data-ttu-id="2a9ef-172">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-172">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="2a9ef-173">Pour chaque produit vendu à une date spécifique, le tableau affiche le nom du produit, la quantité vendue et le total des ventes.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-173">For each product that is sold on a specific date, the table displays the product name, the quantity sold, and the sales total.</span></span> <span data-ttu-id="2a9ef-174">Les données sont organisées par date de vente, puis par sous-catégorie.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-174">The data is organized first by sales date and then by subcategory.</span></span>  
  
##  <a name="3-use-background-colors-to-display-a-kpi"></a><a name="BackgroundColors"></a><span data-ttu-id="2a9ef-175">3. utiliser les couleurs d’arrière-plan pour afficher un indicateur de performance clé</span><span class="sxs-lookup"><span data-stu-id="2a9ef-175">3. Use Background Colors to Display a KPI</span></span>  
 <span data-ttu-id="2a9ef-176">Les couleurs d'arrière-plan peuvent avoir la valeur d'une expression qui est évaluée lorsque vous exécutez le rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-176">Background colors can be set to an expression that is evaluated when you run the report.</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-by-using-background-colors"></a><span data-ttu-id="2a9ef-177">Pour afficher l'état actuel d'un KPI en utilisant des couleurs d'arrière-plan</span><span class="sxs-lookup"><span data-stu-id="2a9ef-177">To display the present state of a KPI by using background colors</span></span>  
  
1.  <span data-ttu-id="2a9ef-178">Dans le tableau, cliquez avec le bouton droit sur deux cellules en dessous de la `[Sum(Sales)]` cellule (la ligne de sous-total qui affiche les ventes d’une sous-catégorie), puis cliquez sur Propriétés de la **zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-178">In the table, right-click two cells down from the `[Sum(Sales)]` cell (the subtotal row that displays the sales for a subcategory), and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="2a9ef-179">Dans **remplissage**, cliquez sur le bouton **FX** en regard de l’option **couleur de remplissage** , puis entrez l’expression suivante dans le champ **définir l’expression pour : BackgroundColor** :</span><span class="sxs-lookup"><span data-stu-id="2a9ef-179">In **Fill**, click the **fx** button next to the **Fill color** option and enter the following expression in the **Set expression for: BackgroundColor** field:</span></span>  
  
 `=IIF(Sum(Fields!Sales.Value) >= 5000 ,"Lime", IIF(Sum(Fields!Sales.Value) < 2500, "Red","Yellow"))`  
  
 <span data-ttu-id="2a9ef-180">La couleur d'arrière-plan passe au vert, à l'aide de la nuance de vert nommée « Citron vert », pour chaque cellule qui contient une somme agrégée pour `[Sum(Sales)]` supérieure ou égale à 5000.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-180">This changes the background color to green, using the shade of green named "Lime", for each cell that contains an aggregated sum for `[Sum(Sales)]` that is greater than or equal to 5000.</span></span> <span data-ttu-id="2a9ef-181">Les valeurs de `[Sum(Sales)]` entre 2500 et 5000 sont colorées en jaune.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-181">Values of `[Sum(Sales)]` between 2500 and 5000 are colored yellow.</span></span> <span data-ttu-id="2a9ef-182">Les valeurs inférieures à 2500 sont colorées en rouge.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-182">Values less than 2500 are colored red.</span></span>  
  
1.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="2a9ef-183">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-183">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="2a9ef-184">Dans la ligne de sous-total qui affiche les ventes d'une sous-catégorie, la couleur d'arrière-plan de la cellule est le rouge, le jaune ou le vert, selon la valeur de la somme des ventes.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-184">In the subtotal row that displays the sales for a subcategory, the background color of the cell is red, yellow, or green depending on value of the sales sum.</span></span>  
  
##  <a name="4-display-a-kpi-by-using-a-gauge"></a><a name="Gauge"></a><span data-ttu-id="2a9ef-185">4. afficher un indicateur de performance clé à l’aide d’une jauge</span><span class="sxs-lookup"><span data-stu-id="2a9ef-185">4. Display a KPI by Using a Gauge</span></span>  
 <span data-ttu-id="2a9ef-186">Une jauge représente une valeur unique dans un dataset.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-186">A gauge depicts a single value in a dataset.</span></span> <span data-ttu-id="2a9ef-187">Ce didacticiel utilise une jauge linéaire horizontale, car sa forme et sa simplicité la rendent facile à lire, même lorsqu'elle est de petite taille et qu'elle est utilisée dans une cellule de tableau.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-187">This tutorial uses a horizontal linear gauge because its shape and simplicity makes it easy to read, even in when it is a small size and used within a table cell.</span></span> <span data-ttu-id="2a9ef-188">Pour plus d’informations, consultez [Jauges &#40;Générateur de rapports et SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2a9ef-188">For more information, see [Gauges &#40;Report Builder and SSRS&#41;](report-design/gauges-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-a-gauge"></a><span data-ttu-id="2a9ef-189">Pour afficher l'état présent d'un KPI à l'aide d'une jauge</span><span class="sxs-lookup"><span data-stu-id="2a9ef-189">To display the present state of a KPI using a gauge</span></span>  
  
1.  <span data-ttu-id="2a9ef-190">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-190">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="2a9ef-191">Dans le tableau, cliquez avec le bouton droit sur le gestionnaire de colonnes de la cellule que vous avez modifiée dans la procédure précédente, pointez sur **Insérer une colonne**, puis cliquez sur **droite**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-191">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="2a9ef-192">Une nouvelle colonne est ajoutée au tableau.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-192">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="2a9ef-193">Tapez **KPI** dans l’en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-193">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="2a9ef-194">Sous l’onglet **Insérer** , dans le groupe **régions de données** , cliquez sur **jauge**, puis cliquez sur l’aire de conception en dehors de la table.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-194">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click the design surface outside the table.</span></span> <span data-ttu-id="2a9ef-195">La boîte de dialogue **Sélectionner le type de jauge** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-195">The **Select Gauge Type** dialog box appears.</span></span>  
  
5.  <span data-ttu-id="2a9ef-196">Cliquez sur **linéaire**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-196">Click **Linear**.</span></span> <span data-ttu-id="2a9ef-197">Le premier type de jauge linéaire, **horizontal**, est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-197">The first linear gauge type, **Horizontal**, is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="2a9ef-198">Une jauge est ajoutée à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-198">A gauge is added to the design surface.</span></span>  
  
7.  <span data-ttu-id="2a9ef-199">À partir du volet des données de rapport, faites glisser Sales vers la jauge.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-199">From the Report Data pane, drag Sales to the gauge.</span></span> <span data-ttu-id="2a9ef-200">Lorsque vous faites glisser Sales sur la jauge, le volet Données de jauge s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-200">When you drag Sales across the gauge, the Gauge Data pane opens.</span></span>  
  
8.  <span data-ttu-id="2a9ef-201">Supprimez Sales dans la liste **valeurs** .</span><span class="sxs-lookup"><span data-stu-id="2a9ef-201">Drop Sales in the **Values** list.</span></span>  
  
     <span data-ttu-id="2a9ef-202">Une fois le champ déposé sur la jauge, les valeurs qu'il contient sont agrégées à l'aide de la fonction intégrée Sum.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-202">When you drop the field onto the gauge, the field is aggregated by using the built-in Sum function.</span></span>  
  
9. <span data-ttu-id="2a9ef-203">Cliquez avec le bouton droit sur le pointeur dans la jauge et cliquez sur **Propriétés du pointeur**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-203">Right-click the pointer in the gauge and click **Pointer Properties**.</span></span>  
  
10. <span data-ttu-id="2a9ef-204">Dans **type de pointeur**, sélectionnez **barre**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-204">In **Pointer Type**, select **Bar**.</span></span> <span data-ttu-id="2a9ef-205">Le pointeur abandonne sa forme de marqueur pour prendre celle d'une barre qui sera plus visible une fois que la jauge aura été ajoutée au tableau.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-205">This changes the pointer from a marker to a bar that will be more visible when the gauge is added to the table.</span></span>  
  
11. <span data-ttu-id="2a9ef-206">Cliquez sur **remplissage du pointeur**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-206">Click **Pointer Fill**.</span></span> <span data-ttu-id="2a9ef-207">Dans **couleur secondaire,** choisissez **jaune**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-207">In **Secondary Color,** pick **Yellow**.</span></span> <span data-ttu-id="2a9ef-208">Le motif de remplissage dégradé passe du blanc au jaune.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-208">The gradient fill pattern will change from white to yellow.</span></span>  
  
12. <span data-ttu-id="2a9ef-209">Cliquez avec le bouton droit sur l’échelle de la jauge, puis cliquez sur **Propriétés de l’échelle**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-209">Right-click the scale in the gauge and click **Scale Properties**.</span></span>  
  
13. <span data-ttu-id="2a9ef-210">Définissez l’option **maximum** sur 25000.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-210">Set the **Maximum** option to 25000.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a9ef-211">Au lieu d’une constante comme 25000, vous pouvez utiliser une expression pour calculer dynamiquement la valeur de l’option **Maximum** .</span><span class="sxs-lookup"><span data-stu-id="2a9ef-211">Instead of a constant such as 25000, you can use an expression to dynamically calculate the value of the **Maximum** option.</span></span> <span data-ttu-id="2a9ef-212">L'expression utilise alors la fonctionnalité d'agrégation et est semblable à l'expression `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-212">The expression would use the aggregate of aggregate feature and look similar to the expression `=Max(Sum(Fields!Sales.value), "Tablix1")`.</span></span>  
  
14. <span data-ttu-id="2a9ef-213">Faites glisser la jauge dans le tableau jusqu'à la troisième cellule de la ligne de sous-total qui affiche les ventes d'une sous-catégorie de la colonne que vous avez insérée.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-213">Drag the gauge inside the table into the third cell in the subtotal row that displays the sales for a subcategory of the column that you inserted.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a9ef-214">Vous devrez peut-être redimensionner la colonne afin que la jauge linéaire horizontale s'ajuste à la taille des cellules.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-214">You might have to resize the column so that the horizontal linear gauge fits into the cell.</span></span> <span data-ttu-id="2a9ef-215">Pour redimensionner la colonne, cliquez sur un en-tête de colonne, puis utilisez les poignées pour redimensionner les cellules horizontalement et verticalement.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-215">To resize the column, click a column header and use the handles to resize the cells horizontally and vertically.</span></span>  
  
15. <span data-ttu-id="2a9ef-216">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-216">Click **Run** to preview the report.</span></span>  
  
     <span data-ttu-id="2a9ef-217">La longueur horizontale de la barre de la jauge varie en fonction de la valeur du KPI.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-217">The horizontal length of the bar in the gauge changes depending on the value of the KPI.</span></span>  
  
16. <span data-ttu-id="2a9ef-218">(Facultatif) Ajoutez une aiguille maximale pour gérer le dépassement de capacité afin que toute valeur apparaissant dans la plage maximale de l'échelle renvoie constamment à cette aiguille :</span><span class="sxs-lookup"><span data-stu-id="2a9ef-218">(Optional) Add a maximum pin to handle overflow so that any value over the scale maximum always points to the maximum pin:</span></span>  
  
    1.  <span data-ttu-id="2a9ef-219">Ouvrez le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-219">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="2a9ef-220">Cliquez sur l’échelle.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-220">Click the scale.</span></span> <span data-ttu-id="2a9ef-221">Les propriétés de l'échelle linéaire s'affichent alors dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-221">The properties for the linear scale are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="2a9ef-222">Dans la catégorie **échelles** , développez le nœud **MaximumPin** .</span><span class="sxs-lookup"><span data-stu-id="2a9ef-222">In the **Scale Pins** category, expand the **MaximumPin** node.</span></span>  
  
    4.  <span data-ttu-id="2a9ef-223">Affectez à la propriété **activer** la valeur `True` .</span><span class="sxs-lookup"><span data-stu-id="2a9ef-223">Set the **Enable** property to `True`.</span></span> <span data-ttu-id="2a9ef-224">Une aiguille s'affiche alors derrière la valeur maximale de l'échelle.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-224">A pin appears after the maximum value on the scale.</span></span>  
  
    5.  <span data-ttu-id="2a9ef-225">Affectez à **BorderColor** la valeur `Lime` .</span><span class="sxs-lookup"><span data-stu-id="2a9ef-225">Set **BorderColor** to `Lime`.</span></span>  
  
17. <span data-ttu-id="2a9ef-226">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-226">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-display-a-kpi-by-using-an-indicator"></a><a name="Indicator"></a><span data-ttu-id="2a9ef-227">5. afficher un indicateur de performance clé à l’aide d’un indicateur</span><span class="sxs-lookup"><span data-stu-id="2a9ef-227">5. Display a KPI by Using an Indicator</span></span>  
 <span data-ttu-id="2a9ef-228">Les indicateurs sont de petites jauges simples qui permettent d'obtenir en un coup d'œil des valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-228">Indicators are small simple gauges that communicate data values at a glance.</span></span> <span data-ttu-id="2a9ef-229">En raison de leur taille et de leur simplicité, les indicateurs sont souvent utilisés dans les tableaux et les matrices.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-229">Because of their size and simplicity, indicators are often used in tables and matrices.</span></span> <span data-ttu-id="2a9ef-230">Pour plus d’informations, consultez [Indicateurs &#40;Générateur de rapports et SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2a9ef-230">For more information, see [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-display-the-present-state-of-a-kpi-using-an-indicator"></a><span data-ttu-id="2a9ef-231">Pour afficher l'état présent d'un KPI à l'aide d'un indicateur</span><span class="sxs-lookup"><span data-stu-id="2a9ef-231">To display the present state of a KPI using an indicator</span></span>  
  
1.  <span data-ttu-id="2a9ef-232">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-232">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="2a9ef-233">Dans le tableau, cliquez avec le bouton droit sur le gestionnaire de colonnes de la cellule que vous avez modifiée dans la procédure précédente, pointez sur **Insérer une colonne**, puis cliquez sur **droite**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-233">In the table, right-click the column handler for the cell that you changed in the previous procedure, point to **Insert Column**, and then click **Right**.</span></span> <span data-ttu-id="2a9ef-234">Une nouvelle colonne est ajoutée au tableau.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-234">A new column is added to the table.</span></span>  
  
3.  <span data-ttu-id="2a9ef-235">Tapez **KPI** dans l’en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-235">Type **KPI** in the column heading.</span></span>  
  
4.  <span data-ttu-id="2a9ef-236">Cliquez sur la cellule correspondant au sous-total de la sous-catégorie.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-236">Click the cell for the subcategory subtotal.</span></span>  
  
5.  <span data-ttu-id="2a9ef-237">Sous l’onglet **Insérer** , dans le groupe **régions de données** , double-cliquez sur **indicateur.**</span><span class="sxs-lookup"><span data-stu-id="2a9ef-237">On the **Insert** tab, in the **Data Regions** group, double-click **Indicator.**</span></span>  
  
     <span data-ttu-id="2a9ef-238">La boîte de dialogue **Sélectionner un type d’indicateur** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-238">The **Select Indicator Type** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="2a9ef-239">Cliquez sur **formes**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-239">Click **Shapes**.</span></span> <span data-ttu-id="2a9ef-240">Le premier type de forme, **3 indicateurs de trafic (sans bordure),** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-240">The first shape type, **3 Traffic Lights (Unrimmed),** is selected.</span></span>  
  
     <span data-ttu-id="2a9ef-241">Vous allez utiliser cet indicateur dans le didacticiel.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-241">You will use this indicator in the tutorial.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="2a9ef-242">L'indicateur est ajouté à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-242">The indicator is added to the design surface.</span></span>  
  
8.  <span data-ttu-id="2a9ef-243">Cliquez avec le bouton droit sur l’indicateur, puis cliquez sur **Propriétés de l’indicateur**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-243">Right-click the indicator and click **Indicator Properties**.</span></span>  
  
9. <span data-ttu-id="2a9ef-244">Cliquez sur **valeurs et États**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-244">Click **Values and States**.</span></span>  
  
10. <span data-ttu-id="2a9ef-245">Dans la liste déroulante valeur, sélectionnez **[Sum (Sales)]**, mais ne modifiez pas les autres options.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-245">In the Value drop-down list, select **[Sum(Sales)]**, but do not change any other options.</span></span>  
  
     <span data-ttu-id="2a9ef-246">Par défaut, la synchronisation des données se produit au niveau de la région de données et vous voyez s’afficher la valeur **Tablix1**, le nom de la région de données de table dans le rapport, dans la zone **Étendue de synchronisation** .</span><span class="sxs-lookup"><span data-stu-id="2a9ef-246">By default, data synchronization occurs across the data region and you see the value **Tablix1**, the name of the table data region in the report, in the **Synchronization scope** box.</span></span>  
  
     <span data-ttu-id="2a9ef-247">Dans ce rapport, vous pouvez également modifier l'étendue d'un indicateur placé dans la cellule du sous-total de la sous-catégorie pour synchroniser le champ SalesDate.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-247">In this report, you can also change the scope of an indicator placed in the cell of the subcategory subtotal to synchronize across the SalesDate field.</span></span>  
  
11. <span data-ttu-id="2a9ef-248">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-248">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="2a9ef-249">6. Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="2a9ef-249">6. Add a Report Title</span></span>  
 <span data-ttu-id="2a9ef-250">Un titre de rapport s'affiche dans la partie supérieure du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-250">A report title appears at the top of the report.</span></span> <span data-ttu-id="2a9ef-251">Vous pouvez placer le titre du rapport dans un en-tête de rapport, ou si le rapport n'en utilise pas, dans une zone de texte située en haut du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-251">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="2a9ef-252">Vous allez utiliser la zone de texte placée automatiquement en haut du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-252">You will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="2a9ef-253">Vous pouvez améliorer le texte en appliquant différents types de styles de police, de tailles et de couleurs à des expressions et des caractères spécifiques.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-253">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="2a9ef-254">Pour plus d’informations, consultez [Mettre en forme du texte dans une zone de texte &#40;Générateur de rapports et SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2a9ef-254">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="2a9ef-255">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="2a9ef-255">To add a report title</span></span>  
  
1.  <span data-ttu-id="2a9ef-256">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-256">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="2a9ef-257">Tapez **Product Sales KPI**, puis cliquez à l’extérieur de la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-257">Type **Product Sales KPI**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="2a9ef-258">Si vous le souhaitez, cliquez avec le bouton droit sur la zone de texte qui contient **Product Sales KPI**, cliquez sur Propriétés de la **zone de texte**, puis sous l’onglet police, sélectionnez les différents styles de police, tailles et couleurs.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-258">Optionally, right-click the text box that contains **Product Sales KPI**, click **Text Box Properties**, and then on the Font tab select the different font styles, sizes and colors.</span></span>  
  
4.  <span data-ttu-id="2a9ef-259">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-259">Click **Run** to preview the report.</span></span>  
  
##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="2a9ef-260">7. enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="2a9ef-260">7. Save the Report</span></span>  
 <span data-ttu-id="2a9ef-261">Enregistrez le rapport sur un serveur de rapports ou sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-261">Save the report to a report server or your computer.</span></span> <span data-ttu-id="2a9ef-262">Si vous n'enregistrez pas le rapport sur le serveur de rapports, plusieurs fonctionnalités de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] telles que les parties de rapports et les sous-rapports ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-262">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="2a9ef-263">Pour enregistrer le rapport sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="2a9ef-263">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="2a9ef-264">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-264">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="2a9ef-265">Cliquez sur **Sites et serveurs récents**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-265">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="2a9ef-266">Sélectionnez ou tapez le nom du serveur de rapports sur lequel vous êtes autorisé à enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-266">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="2a9ef-267">Le message « Connexion au serveur de rapports » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-267">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="2a9ef-268">Une fois la connexion établie, le contenu du dossier de rapports spécifié par l'administrateur du serveur de rapports s'affiche comme emplacement par défaut des rapports.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-268">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="2a9ef-269">Dans **Nom**, remplacez le nom par défaut par **Product Sales KPI**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-269">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
5.  <span data-ttu-id="2a9ef-270">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-270">Click **Save**.</span></span>  
  
 <span data-ttu-id="2a9ef-271">Le rapport est enregistré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-271">The report is saved to the report server.</span></span> <span data-ttu-id="2a9ef-272">Le nom du serveur de rapports auquel vous êtes connecté est indiqué dans la barre d'état située au bas de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-272">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="2a9ef-273">Pour enregistrer le rapport sur votre ordinateur</span><span class="sxs-lookup"><span data-stu-id="2a9ef-273">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="2a9ef-274">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-274">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="2a9ef-275">Cliquez sur **Bureau**, **Mes documents**ou **Poste de travail**, puis naviguez jusqu’au dossier où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-275">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a9ef-276">Si vous n’avez pas accès à un serveur de rapports, cliquez sur **Bureau**, **Mes documents**ou **Poste de travail** et enregistrez le rapport sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-276">If you do not have access to a report server, click **Desktop**, **My Documents**, or **My computer** and save the report to your computer.</span></span>  
  
1.  <span data-ttu-id="2a9ef-277">Dans **Nom**, remplacez le nom par défaut par **Product Sales KPI**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-277">In **Name**, replace the default name with **Product Sales KPI**.</span></span>  
  
2.  <span data-ttu-id="2a9ef-278">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-278">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2a9ef-279">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="2a9ef-279">Next Steps</span></span>  
 <span data-ttu-id="2a9ef-280">Vous avez terminé le didacticiel d'ajout d'un indicateur de performance clé à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="2a9ef-280">You have successfully completed the Adding a KPI to Your Report tutorial.</span></span> <span data-ttu-id="2a9ef-281">Pour plus d’informations, consultez indicateurs de jauges (Générateur de rapports) [&#40;générateur de rapports et&#41;SSRS ](report-design/indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2a9ef-281">For more information, see Gauges (Report Builder) [Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9ef-282">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a9ef-282">See Also</span></span>  
 <span data-ttu-id="2a9ef-283">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="2a9ef-283">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="2a9ef-284">Générateur de rapports dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="2a9ef-284">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
