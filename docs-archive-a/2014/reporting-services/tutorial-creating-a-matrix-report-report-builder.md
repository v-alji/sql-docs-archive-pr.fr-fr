---
title: 'Didacticiel : création d’un rapport de matrice (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9ee19c2e-2a8c-4bb0-9274-04a5812c2e96
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3df32098d9e6400931ba2a88b2ffd22d6e015a62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706123"
---
# <a name="tutorial-creating-a-matrix-report-report-builder"></a><span data-ttu-id="16983-102">Didacticiel : création d'un rapport de matrice (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="16983-102">Tutorial: Creating a Matrix Report (Report Builder)</span></span>
  <span data-ttu-id="16983-103">Ce didacticiel vous apprend comment créer un rapport de matrice de base reposant sur des exemples de données de vente.</span><span class="sxs-lookup"><span data-stu-id="16983-103">This tutorial teaches you how to create a basic matrix report based on sample sales data.</span></span> <span data-ttu-id="16983-104">La matrice comporte des groupes de lignes et de colonnes imbriqués, ainsi qu'un groupe de colonnes adjacent.</span><span class="sxs-lookup"><span data-stu-id="16983-104">The matrix has nested row and column groups and an adjacent column group.</span></span> <span data-ttu-id="16983-105">Vous apprendrez également comment mettre en forme les colonnes et faire pivoter le texte.</span><span class="sxs-lookup"><span data-stu-id="16983-105">You will also learn how to format columns and rotate text.</span></span> <span data-ttu-id="16983-106">L'illustration suivante montre un rapport similaire à celui que vous allez créer.</span><span class="sxs-lookup"><span data-stu-id="16983-106">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="16983-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="16983-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span></span>  
  
 <span data-ttu-id="16983-108">Une version améliorée du rapport créé dans ce didacticiel est disponible sous forme d'exemple de rapport du Générateur de rapports de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16983-108">An enhanced version of the report you will create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="16983-109">Pour plus d’informations sur le téléchargement de cet exemple de rapport et d’autres, consultez [Générateur de rapports exemples de rapports](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="16983-109">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="16983-110">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="16983-110">What You Will Learn</span></span>  
 <span data-ttu-id="16983-111">Dans ce didacticiel, vous apprendrez à :</span><span class="sxs-lookup"><span data-stu-id="16983-111">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="16983-112">Créer un rapport de matrice et un dataset à partir de l'Assistant Nouveau tableau ou nouvelle matrice</span><span class="sxs-lookup"><span data-stu-id="16983-112">Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>](#CreateMatrix)  
  
2.  [<span data-ttu-id="16983-113">Organiser les données et choisir la mise en page et le style à partir de l'Assistant Nouveau tableau ou nouvelle matrice</span><span class="sxs-lookup"><span data-stu-id="16983-113">Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>](#Groups)  
  
3.  [<span data-ttu-id="16983-114">Mettre en forme les données</span><span class="sxs-lookup"><span data-stu-id="16983-114">Format Data</span></span>](#FormatData)  
  
4.  [<span data-ttu-id="16983-115">Ajouter un groupe de colonnes adjacent</span><span class="sxs-lookup"><span data-stu-id="16983-115">Add Adjacent Column Group</span></span>](#AdjacentGroup)  
  
5.  [<span data-ttu-id="16983-116">Modifier la largeur des colonnes</span><span class="sxs-lookup"><span data-stu-id="16983-116">Change Column Widths</span></span>](#Width)  
  
6.  [<span data-ttu-id="16983-117">Fusionner des cellules de matrice</span><span class="sxs-lookup"><span data-stu-id="16983-117">Merge Matrix Cells</span></span>](#MergeCells)  
  
7.  [<span data-ttu-id="16983-118">Ajouter un en-tête de rapport et un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="16983-118">Add a Report Header and Report Title</span></span>](#HeaderTitle)  
  
8.  [<span data-ttu-id="16983-119">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="16983-119">Save the Report</span></span>](#Save)  
  
### <a name="other-optional-step"></a><span data-ttu-id="16983-120">Autre étape facultative</span><span class="sxs-lookup"><span data-stu-id="16983-120">Other Optional Step</span></span>  
  
1.  [<span data-ttu-id="16983-121">Faire pivoter la zone de texte de 270 degrés</span><span class="sxs-lookup"><span data-stu-id="16983-121">Rotate Text Box 270 Degrees</span></span>](#RotateTextBox)  
  
 <span data-ttu-id="16983-122">Durée estimée pour effectuer le didacticiel : 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="16983-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16983-123">Spécifications</span><span class="sxs-lookup"><span data-stu-id="16983-123">Requirements</span></span>  
 <span data-ttu-id="16983-124">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="16983-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-new-table-or-matrix-wizard"></a><a name="CreateMatrix"></a><span data-ttu-id="16983-125">1. créer un rapport de matrice et un DataSet à partir de l’Assistant Nouveau tableau ou nouvelle matrice</span><span class="sxs-lookup"><span data-stu-id="16983-125">1. Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="16983-126">À partir de la boîte de dialogue **prise en main** dans générateur de rapports, choisissez une source de données partagée, créez un dataset incorporé, puis affichez les données dans une matrice.</span><span class="sxs-lookup"><span data-stu-id="16983-126">From the **Getting Started** dialog box in Report Builder, choose a shared data source, create an embedded dataset, and then display the data in a matrix.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16983-127">Dans ce didacticiel, la requête contient déjà les valeurs de données, afin qu'il ne soit pas nécessaire de disposer d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="16983-127">In this tutorial, the query already contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="16983-128">Cela rend la requête assez longue.</span><span class="sxs-lookup"><span data-stu-id="16983-128">This makes the query quite long.</span></span> <span data-ttu-id="16983-129">Dans un environnement métier, une requête ne contient pas les données.</span><span class="sxs-lookup"><span data-stu-id="16983-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="16983-130">Ceci est nécessaire à des fins de formation uniquement.</span><span class="sxs-lookup"><span data-stu-id="16983-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix"></a><span data-ttu-id="16983-131">Pour créer une nouvelle matrice</span><span class="sxs-lookup"><span data-stu-id="16983-131">To create a new matrix</span></span>  
  
1.  <span data-ttu-id="16983-132">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur **Générateur de rapports Microsoft SQL Server 2012**, puis cliquez sur **Générateur de rapports version**.</span><span class="sxs-lookup"><span data-stu-id="16983-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16983-133">La boîte de dialogue **Mise en route** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="16983-133">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="16983-134">Si ce n’est pas le cas, à partir du bouton Générateur de rapports, cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="16983-134">If it doesn't, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="16983-135">Dans le volet gauche, assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="16983-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="16983-136">Dans le volet droit, cliquez sur **Assistant Tableau ou matrice**.</span><span class="sxs-lookup"><span data-stu-id="16983-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="16983-137">Dans la page **Choisir un dataset** , cliquez sur **Créer un dataset**.</span><span class="sxs-lookup"><span data-stu-id="16983-137">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="16983-138">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="16983-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="16983-139">Dans la page **choisir une connexion à une source de données** , sélectionnez une source de données existante ou accédez au serveur de rapports, puis sélectionnez une source de données.</span><span class="sxs-lookup"><span data-stu-id="16983-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server, and then select a data source.</span></span> <span data-ttu-id="16983-140">Si aucune source de données n'est disponible ou si vous n'avez pas accès à un serveur de rapports, vous pouvez utiliser une source de données incorporée à la place.</span><span class="sxs-lookup"><span data-stu-id="16983-140">If no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="16983-141">Pour plus d’informations sur la création d’une source de données incorporée, consultez [Didacticiel : création d’un rapport de tableau de base &#40;Générateur de rapports&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="16983-141">For more information about creating an embedded data source, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="16983-142">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="16983-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="16983-143">Dans la page **Créer une requête** , cliquez sur **Modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="16983-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="16983-144">Copiez et collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="16983-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity  
    ```  
  
10. <span data-ttu-id="16983-145">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="16983-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-and-choose-layout-and-style-from-the-new-table-or-matrix-wizard"></a><a name="Groups"></a><span data-ttu-id="16983-146">2. organiser les données et choisir la mise en page et le style à partir de l’Assistant Nouveau tableau ou nouvelle matrice</span><span class="sxs-lookup"><span data-stu-id="16983-146">2. Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="16983-147">Utilisez l'Assistant pour obtenir une conception initiale dans laquelle afficher les données.</span><span class="sxs-lookup"><span data-stu-id="16983-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="16983-148">Le volet de visualisation de l'Assistant vous aide à visualiser le résultat du regroupement des données avant de terminer la conception de la matrice.</span><span class="sxs-lookup"><span data-stu-id="16983-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-and-choose-a-layout-and-style"></a><span data-ttu-id="16983-149">Pour organiser les données en groupes et choisir une mise en page et un style</span><span class="sxs-lookup"><span data-stu-id="16983-149">To organize data into groups and choose a layout and style</span></span>  
  
1.  <span data-ttu-id="16983-150">Dans la page **Organiser les champs** , faites glisser Territory de **Champs disponibles** vers **Groupes de lignes**.</span><span class="sxs-lookup"><span data-stu-id="16983-150">On the **Arrange fields** page, drag Territory from **Available fields** to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="16983-151">Faites glisser SalesDate vers **Groupes de lignes** et placez-le sous Territory.</span><span class="sxs-lookup"><span data-stu-id="16983-151">Drag SalesDate to **Row groups** and place it below Territory.</span></span>  
  
     <span data-ttu-id="16983-152">L’ordre dans lequel les champs sont répertoriés dans **Groupes de lignes** définit la hiérarchie des groupes.</span><span class="sxs-lookup"><span data-stu-id="16983-152">The order in which fields are listed in **Row groups** defines the group hierarchy.</span></span> <span data-ttu-id="16983-153">Les étapes 1 et 2 organisent les valeurs des champs par secteur de vente (Territory), puis par date de vente (SalesDate).</span><span class="sxs-lookup"><span data-stu-id="16983-153">Steps 1 and 2 organize the values of the fields first by territory, and then by sales date.</span></span>  
  
3.  <span data-ttu-id="16983-154">Faites glisser Subcategory vers **Groupes de colonnes**.</span><span class="sxs-lookup"><span data-stu-id="16983-154">Drag Subcategory to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="16983-155">Faites glisser Product vers **groupes de colonnes,** puis placez sous sous-catégorie.</span><span class="sxs-lookup"><span data-stu-id="16983-155">Drag Product to **Column groups,** and then place below Subcategory.</span></span>  
  
     <span data-ttu-id="16983-156">L’ordre dans lequel les champs sont répertoriés dans **groupes de colonnes** définit la hiérarchie des groupes.</span><span class="sxs-lookup"><span data-stu-id="16983-156">The order in which fields are listed in **Column groups** defines the group hierarchy.</span></span>  
  
     <span data-ttu-id="16983-157">Les étapes 3 et 4 organisent les valeurs des champs par sous-catégorie (SubCategory), puis par produit (Product).</span><span class="sxs-lookup"><span data-stu-id="16983-157">Steps 3 and 4 organize the values for the fields first by subcategory, and then by product.</span></span>  
  
5.  <span data-ttu-id="16983-158">Faites glisser Sales vers **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="16983-158">Drag Sales to **Values**.</span></span>  
  
     <span data-ttu-id="16983-159">Sales est synthétisé à l'aide de la fonction Sum, la fonction de synthèse par défaut des champs numériques.</span><span class="sxs-lookup"><span data-stu-id="16983-159">Sales is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
6.  <span data-ttu-id="16983-160">Faites glisser Quantity vers **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="16983-160">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="16983-161">Quantity est synthétisé à l'aide de la fonction Sum.</span><span class="sxs-lookup"><span data-stu-id="16983-161">Quantity is summarized with the Sum function.</span></span>  
  
     <span data-ttu-id="16983-162">Les étapes 5 et 6 spécifient les données à afficher dans les cellules de données de la matrice.</span><span class="sxs-lookup"><span data-stu-id="16983-162">Steps 5 and 6 specify the data to display in the matrix data cells.</span></span>  
  
7.  <span data-ttu-id="16983-163">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="16983-163">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="16983-164">Dans la page choisir la disposition, sous **options**, vérifiez que **afficher les sous-totaux et les totaux généraux** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="16983-164">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
9. <span data-ttu-id="16983-165">Vérifiez que **Bloqué, sous-total ci-dessous** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="16983-165">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
10. <span data-ttu-id="16983-166">Vérifiez que l’option **Développer/Réduire les groupes** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="16983-166">Verify the option **Expand/collapse groups** is selected.</span></span>  
  
11. <span data-ttu-id="16983-167">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="16983-167">Click **Next**.</span></span>  
  
12. <span data-ttu-id="16983-168">Dans la page Choisir un style , dans le volet Styles , sélectionnez **Ardoise**.</span><span class="sxs-lookup"><span data-stu-id="16983-168">On the Choose a Style page, in the Styles pane, select **Slate**.</span></span>  
  
13. <span data-ttu-id="16983-169">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="16983-169">Click **Finish**.</span></span>  
  
     <span data-ttu-id="16983-170">La matrice est ajoutée à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="16983-170">The matrix is added to the design surface.</span></span> <span data-ttu-id="16983-171">Le volet Groupes de lignes affiche deux groupes de lignes : Territory et SalesDate.</span><span class="sxs-lookup"><span data-stu-id="16983-171">The Row Groups pane shows two row groups: Territory and SalesDate.</span></span> <span data-ttu-id="16983-172">Le volet Groupes de colonnes affiche deux groupes de colonnes : Subcategory et Product.</span><span class="sxs-lookup"><span data-stu-id="16983-172">The Column Groups pane shows two column groups: Subcategory and Product.</span></span> <span data-ttu-id="16983-173">Les données de détail sont toutes les données récupérées par la requête de dataset.</span><span class="sxs-lookup"><span data-stu-id="16983-173">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
14. <span data-ttu-id="16983-174">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-174">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="16983-175">Pour chaque produit vendu à une date spécifique, la matrice affiche la sous-catégorie à laquelle le produit appartient et le secteur des ventes.</span><span class="sxs-lookup"><span data-stu-id="16983-175">For each product that is sold on a specific date, the matrix shows the subcategory to which the product belongs and the territory of the sales.</span></span>  
  
##  <a name="3-format-data"></a><a name="FormatData"></a><span data-ttu-id="16983-176">3. mettre en forme les données</span><span class="sxs-lookup"><span data-stu-id="16983-176">3. Format Data</span></span>  
 <span data-ttu-id="16983-177">Par défaut, les données de synthèse du champ Sales affichent un nombre général et le champ SalesDate affiche des informations de date et d'heure.</span><span class="sxs-lookup"><span data-stu-id="16983-177">By default, the summary data for the Sales field displays a general number and the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="16983-178">Mettez en forme le champ Sales de manière à afficher le nombre sous forme de devise et le champ SalesDate afin qu'il n'affiche que la date.</span><span class="sxs-lookup"><span data-stu-id="16983-178">Format the Sales field to display the number as currency and the SalesDate field to display only the date.</span></span> <span data-ttu-id="16983-179">Activez/désactivez **Styles des espaces réservés** pour afficher les zones de texte mises en forme et le texte de l’espace réservé en tant qu’exemples de valeurs.</span><span class="sxs-lookup"><span data-stu-id="16983-179">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-fields"></a><span data-ttu-id="16983-180">Pour mettre en forme les champs</span><span class="sxs-lookup"><span data-stu-id="16983-180">To format fields</span></span>  
  
1.  <span data-ttu-id="16983-181">Cliquez sur **Conception** pour basculer en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="16983-181">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="16983-182">Appuyez sur la touche Ctrl, puis sélectionnez les neuf cellules contenant `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="16983-182">Press the Ctrl key, and then select the nine cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="16983-183">Sous l’onglet **Accueil** , dans le groupe **Nombre** , cliquez sur **Devise**.</span><span class="sxs-lookup"><span data-stu-id="16983-183">On the **Home** tab, in the **Number** group, click **Currency**.</span></span> <span data-ttu-id="16983-184">Le contenu des cellules est maintenant au format de devise.</span><span class="sxs-lookup"><span data-stu-id="16983-184">The cells changeto show the formatted currency.</span></span>  
  
     <span data-ttu-id="16983-185">Si votre paramètre régional est Anglais (États-Unis), le texte d’exemple par défaut est [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="16983-185">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="16983-186">Si vous ne voyez pas d’exemple de valeur monétaire, cliquez sur **styles des espaces réservés** dans le groupe **nombres** , puis cliquez sur **exemples de valeurs**.</span><span class="sxs-lookup"><span data-stu-id="16983-186">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="16983-187">Cliquez sur la cellule qui contient `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="16983-187">Click the cell that contains `[SalesDate]`.</span></span>  
  
5.  <span data-ttu-id="16983-188">Dans le groupe **nombre** , dans la liste déroulante, sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="16983-188">In the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="16983-189">La cellule affiche l’exemple de date **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="16983-189">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="16983-190">Si vous ne voyez pas s’afficher d’exemple de date, cliquez sur **Styles des espaces réservés** dans le groupe **Nombres** , puis cliquez sur **Valeurs d’aperçu**.</span><span class="sxs-lookup"><span data-stu-id="16983-190">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
6.  <span data-ttu-id="16983-191">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-191">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="16983-192">Les valeurs de date affichent uniquement les dates et les valeurs de ventes sont affichées sous forme de valeurs monétaires.</span><span class="sxs-lookup"><span data-stu-id="16983-192">The date values display only dates and the sales values display as currency.</span></span>  
  
##  <a name="4-add-adjacent-column-group"></a><a name="AdjacentGroup"></a><span data-ttu-id="16983-193">4. Ajouter un groupe de colonnes adjacent</span><span class="sxs-lookup"><span data-stu-id="16983-193">4. Add Adjacent Column Group</span></span>  
 <span data-ttu-id="16983-194">Vous pouvez imbriquer des groupes de lignes et de colonnes dans des relations parent-enfant ou définir des groupes adjacents dans des relations de frère.</span><span class="sxs-lookup"><span data-stu-id="16983-194">You can nest row and column groups in parent child relationships or adjacent in sibling relationships.</span></span>  
  
 <span data-ttu-id="16983-195">Ajoutez un groupe de colonnes adjacent au groupe de colonnes Subcategory, copiez les cellules pour remplir le nouveau groupe de colonnes, puis utilisez une expression pour créer la valeur de l'en-tête de groupe de colonnes.</span><span class="sxs-lookup"><span data-stu-id="16983-195">Add a column group that is adjacent to the Subcategory column group, copy cells to populate the new column group, and then use an expression to create the value of the column group header.</span></span>  
  
#### <a name="to-add-an-adjacent-column-group"></a><span data-ttu-id="16983-196">Pour ajouter un groupe de colonnes adjacent</span><span class="sxs-lookup"><span data-stu-id="16983-196">To add an adjacent column group</span></span>  
  
1.  <span data-ttu-id="16983-197">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="16983-197">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="16983-198">Cliquez avec le bouton droit sur la cellule qui contient `[Subcategory]`, pointez sur **Ajouter un groupe**, puis cliquez sur **Adjacent à droite**.</span><span class="sxs-lookup"><span data-stu-id="16983-198">Right-click the cell that contains `[Subcategory]`, point to **Add Group**, and then click **Adjacent Right**.</span></span>  
  
     <span data-ttu-id="16983-199">La boîte de dialogue **Groupe de tableaux matriciels** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="16983-199">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="16983-200">Dans la liste **Regrouper par** , sélectionnez SalesDate, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="16983-200">In the **Group By** list, select SalesDate, and then click **OK**.</span></span>  
  
     <span data-ttu-id="16983-201">Un nouveau groupe de colonnes est ajouté à gauche du groupe de colonnes Subcategory.</span><span class="sxs-lookup"><span data-stu-id="16983-201">A new column group is added to the left of the Subcategory column group.</span></span>  
  
4.  <span data-ttu-id="16983-202">Cliquez avec le bouton droit sur la cellule du nouveau groupe de colonnes qui contient `[SalesDate],` , puis cliquez sur **Expression**.</span><span class="sxs-lookup"><span data-stu-id="16983-202">Right-click the cell in the new column group that contains `[SalesDate],` and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="16983-203">Copiez l'expression suivante dans la zone d'expression.</span><span class="sxs-lookup"><span data-stu-id="16983-203">Copy the following expression to expression box.</span></span>  
  
    ```  
    =WeekdayName(DatePart("w",Fields!SalesDate.Value))  
    ```  
  
     <span data-ttu-id="16983-204">Cette expression extrait le nom de jour de la semaine de la date de vente.</span><span class="sxs-lookup"><span data-stu-id="16983-204">This expression extracts the weekday name from the sales date.</span></span> <span data-ttu-id="16983-205">Pour plus d’informations, consultez [Expressions &#40;Générateur de rapports et SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="16983-205">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="16983-206">Cliquez avec le bouton droit sur la cellule du groupe de colonnes Subcategory qui contient Total, puis cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="16983-206">Right-click the cell in the Subcategory column group that contains Total, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="16983-207">Cliquez avec le bouton droit immédiatement en-dessous de la cellule qui contient l’expression créée à l’étape 5, puis cliquez sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="16983-207">Right-click the cell immediately below the cell that contains the expression you created in step 5 and click **Paste**.</span></span>  
  
8.  <span data-ttu-id="16983-208">Appuyez sur la touche Ctrl.</span><span class="sxs-lookup"><span data-stu-id="16983-208">Press the Ctrl key.</span></span>  
  
9. <span data-ttu-id="16983-209">Dans le groupe Subcategory, cliquez avec le bouton droit sur l’en-tête de colonne Sales et sur les trois cellules en dessous, puis cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="16983-209">In the Subcategory group, click the Sales column header and the three cells below it, right-click, and then click **Copy**.</span></span>  
  
10. <span data-ttu-id="16983-210">Collez les quatre cellules dans les quatre cellules vides du nouveau groupe de colonnes.</span><span class="sxs-lookup"><span data-stu-id="16983-210">Paste the four cells into the four empty cells in the new column group.</span></span>  
  
11. <span data-ttu-id="16983-211">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-211">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="16983-212">Le rapport inclut des colonnes nommées Monday et Tuesday.</span><span class="sxs-lookup"><span data-stu-id="16983-212">The report includes columns named Monday and Tuesday.</span></span> <span data-ttu-id="16983-213">Le dataset contient uniquement des données pour ces deux jours.</span><span class="sxs-lookup"><span data-stu-id="16983-213">The dataset contains only data for these two days.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16983-214">Si les données avaient inclus d'autres jours, le rapport aurait également inclus des colonnes pour ces jours.</span><span class="sxs-lookup"><span data-stu-id="16983-214">If the data included other days, the report would include columns for them as well.</span></span> <span data-ttu-id="16983-215">Chaque colonne a l’en-tête de colonne, `Sales` et les totaux des ventes par secteur.</span><span class="sxs-lookup"><span data-stu-id="16983-215">Each column has the column header, `Sales`, and sales totals by territory.</span></span>  
  
##  <a name="5-change-column-widths"></a><a name="Width"></a><span data-ttu-id="16983-216">5. modifier la largeur des colonnes</span><span class="sxs-lookup"><span data-stu-id="16983-216">5. Change Column Widths</span></span>  
 <span data-ttu-id="16983-217">Un rapport qui inclut une matrice s'étend généralement horizontalement et verticalement lorsqu'il s'exécute.</span><span class="sxs-lookup"><span data-stu-id="16983-217">A report that includes a matrix typically expands horizontally as well as vertically when it runs.</span></span> <span data-ttu-id="16983-218">Le contrôle de l'expansion horizontale est particulièrement important si vous projetez d'exporter le rapport vers des formats tels que Microsoft Word ou Adobe PDF qui sont utilisés pour imprimer les rapports.</span><span class="sxs-lookup"><span data-stu-id="16983-218">Controlling horizontal expansion is particularly important if you plan to export the report to formats such as Microsoft Word or Adobe PDF that are used for printed reports.</span></span> <span data-ttu-id="16983-219">Si le rapport s'étend horizontalement sur plusieurs pages, le rapport imprimé est difficile à comprendre.</span><span class="sxs-lookup"><span data-stu-id="16983-219">If the report expands horizontally across multiple pages, the printed report is difficult to understand.</span></span> <span data-ttu-id="16983-220">Pour réduire l'expansion horizontale, vous pouvez redimensionner les colonnes afin qu'elles ne soient pas plus larges que nécessaire pour afficher les données sans renvoi à la ligne.</span><span class="sxs-lookup"><span data-stu-id="16983-220">To minimize horizontal expansion, you can resize columns to be only the width necessary to display the data without wrapping.</span></span> <span data-ttu-id="16983-221">Vous pouvez également renommer les colonnes afin que leur titre soit ajusté à la largeur nécessaire pour afficher les données.</span><span class="sxs-lookup"><span data-stu-id="16983-221">You can also rename columns so that their titles fit the width needed to display the data.</span></span>  
  
#### <a name="to-rename-and-resize-the-columns"></a><span data-ttu-id="16983-222">Pour renommer et redimensionner les colonnes</span><span class="sxs-lookup"><span data-stu-id="16983-222">To rename and resize the columns</span></span>  
  
1.  <span data-ttu-id="16983-223">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="16983-223">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="16983-224">Sélectionnez le texte dans la colonne Quantity la plus à gauche, puis tapez **QTY**.</span><span class="sxs-lookup"><span data-stu-id="16983-224">Select the text in the furthest Quantity column to the left, and then type **QTY**.</span></span>  
  
     <span data-ttu-id="16983-225">Le titre de la colonne est maintenant QTY.</span><span class="sxs-lookup"><span data-stu-id="16983-225">The column title is now QTY.</span></span>  
  
3.  <span data-ttu-id="16983-226">Répétez l'étape 2 pour les autres colonnes nommées Quantity.</span><span class="sxs-lookup"><span data-stu-id="16983-226">Repeat step 2 for the other columns named Quantity.</span></span> <span data-ttu-id="16983-227">Il y en a deux.</span><span class="sxs-lookup"><span data-stu-id="16983-227">There are two of them.</span></span>  
  
4.  <span data-ttu-id="16983-228">Cliquez sur la matrice pour que les poignées de ligne et de colonne apparaissent au-dessus et à côté de la matrice.</span><span class="sxs-lookup"><span data-stu-id="16983-228">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
     <span data-ttu-id="16983-229">Les barres grises le long du haut et du côté de la table sont les poignées de colonne et de ligne.</span><span class="sxs-lookup"><span data-stu-id="16983-229">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
5.  <span data-ttu-id="16983-230">Pour redimensionner la colonne QTY la plus à gauche, pointez sur la ligne entre les poignées de colonne afin que le curseur se transforme en flèche à deux pointes.</span><span class="sxs-lookup"><span data-stu-id="16983-230">To resize the furthest QTY column to the left, point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="16983-231">Faites glisser la colonne vers la gauche jusqu'à ce qu'elle fasse 0,5 pouce de large.</span><span class="sxs-lookup"><span data-stu-id="16983-231">Drag the column towards the left until it is 1/2 inch wide.</span></span>  
  
     <span data-ttu-id="16983-232">Une largeur de colonne de 0,5 pouce est parfaite pour afficher la quantité.</span><span class="sxs-lookup"><span data-stu-id="16983-232">A column width of 1/2 inch is adequate to display the quantity.</span></span>  
  
6.  <span data-ttu-id="16983-233">Répétez l'étape 5 pour les autres colonnes nommées QTY.</span><span class="sxs-lookup"><span data-stu-id="16983-233">Repeat step 5 for the other columns named QTY.</span></span>  
  
7.  <span data-ttu-id="16983-234">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-234">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="16983-235">Les colonnes du rapport qui contiennent des quantités sont désormais nommées QTY et sont plus étroites.</span><span class="sxs-lookup"><span data-stu-id="16983-235">The columns in the report that contains quantities are now named QTY and the columns are narrower.</span></span>  
  
##  <a name="6-merge-matrix-cells"></a><a name="MergeCells"></a><span data-ttu-id="16983-236">6. fusionner des cellules de matrice</span><span class="sxs-lookup"><span data-stu-id="16983-236">6. Merge Matrix Cells</span></span>  
 <span data-ttu-id="16983-237">La zone d'angle se trouve dans le coin supérieur gauche de la matrice.</span><span class="sxs-lookup"><span data-stu-id="16983-237">The corner area is in the upper left corner of the matrix.</span></span> <span data-ttu-id="16983-238">Selon le nombre de groupes de lignes et de colonnes dans la matrice, le nombre de cellules de la zone d'angle varie.</span><span class="sxs-lookup"><span data-stu-id="16983-238">Depending on the number of row and column groups in the matrix, the number of cells in the corner area varies.</span></span> <span data-ttu-id="16983-239">La matrice générée dans ce didacticiel comporte quatre cellules dans sa zone d'angle.</span><span class="sxs-lookup"><span data-stu-id="16983-239">The matrix, built in this tutorial, has four cells in its corner area.</span></span> <span data-ttu-id="16983-240">Les cellules sont disposées en deux lignes et deux colonnes, ce qui reflète la profondeur des hiérarchies de groupes de lignes et de colonnes.</span><span class="sxs-lookup"><span data-stu-id="16983-240">The cells are arranged in two rows and two columns, reflecting the depth of row and column group hierarchies.</span></span> <span data-ttu-id="16983-241">Les quatre cellules ne sont pas utilisées dans ce rapport et vous allez les fusionner en une seule.</span><span class="sxs-lookup"><span data-stu-id="16983-241">The four cells are not used in this report and you will merge them into one.</span></span>  
  
#### <a name="to-merge-matrix-cells"></a><span data-ttu-id="16983-242">Pour fusionner des cellules de matrice</span><span class="sxs-lookup"><span data-stu-id="16983-242">To merge matrix cells</span></span>  
  
1.  <span data-ttu-id="16983-243">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="16983-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="16983-244">Cliquez sur la matrice pour que les poignées de ligne et de colonne apparaissent au-dessus et à côté de la matrice.</span><span class="sxs-lookup"><span data-stu-id="16983-244">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
3.  <span data-ttu-id="16983-245">Appuyez sur la touche Ctrl, puis sélectionnez les quatre cellules d'angle.</span><span class="sxs-lookup"><span data-stu-id="16983-245">Press the Ctrl key, and then select the four corner cells.</span></span>  
  
4.  <span data-ttu-id="16983-246">Cliquez avec le bouton droit sur les cellules, puis cliquez sur **fusionner les cellules**.</span><span class="sxs-lookup"><span data-stu-id="16983-246">Right-click the cells and then click **Merge Cells**.</span></span>  
  
5.  <span data-ttu-id="16983-247">Cliquez avec le bouton droit sur la cellule d’angle, puis cliquez sur **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="16983-247">Right-click the corner cell, and then click **Text Box Properties**.</span></span>  
  
6.  <span data-ttu-id="16983-248">Cliquez sur l'onglet **Remplissage** .</span><span class="sxs-lookup"><span data-stu-id="16983-248">Click the **Fill** tab.</span></span>  
  
7.  <span data-ttu-id="16983-249">Cliquez sur le bouton (***FX***) pour **couleur de remplissage**.</span><span class="sxs-lookup"><span data-stu-id="16983-249">Click the (***fx***) button for **Fill color**.</span></span>  
  
8.  <span data-ttu-id="16983-250">Copiez et collez l'expression suivante dans la zone d'expression.</span><span class="sxs-lookup"><span data-stu-id="16983-250">Copy and paste the following expression in the expression box.</span></span>  
  
    ```  
    #96a4b2  
    ```  
  
     <span data-ttu-id="16983-251">Il s'agit de la valeur RVB pour une couleur bleu gris utilisée dans le style Ardoise.</span><span class="sxs-lookup"><span data-stu-id="16983-251">This is the RGB hex value for a gray blue color used in the Slate style.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="16983-252">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-252">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="16983-253">La matrice de l'angle supérieur est une cellule unique de la même couleur que les cellules des groupes de colonnes et des groupes de lignes.</span><span class="sxs-lookup"><span data-stu-id="16983-253">The upper corner matrix is a single cell and has the same color as the row group and column group cells.</span></span>  
  
##  <a name="7-add-a-report-header-and-report-title"></a><a name="HeaderTitle"></a><span data-ttu-id="16983-254">7. Ajouter un en-tête de rapport et un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="16983-254">7. Add a Report Header and Report Title</span></span>  
 <span data-ttu-id="16983-255">Un titre de rapport s'affiche dans la partie supérieure du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-255">A report title appears at the top of the report.</span></span> <span data-ttu-id="16983-256">Vous pouvez placer le titre du rapport dans un en-tête de rapport, ou si le rapport n'en utilise pas, dans une zone de texte située en haut du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-256">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="16983-257">Dans ce didacticiel, vous allez supprimer la zone de texte au haut du rapport et ajouter un titre à l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="16983-257">In this tutorial, you will remove the text box at the top of the report and add a title to the header.</span></span>  
  
#### <a name="to-add-a-report-header-and-report-title"></a><span data-ttu-id="16983-258">Pour ajouter un en-tête de rapport et un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="16983-258">To add a report header and report title</span></span>  
  
1.  <span data-ttu-id="16983-259">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="16983-259">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="16983-260">Cliquez sur la zone de texte en haut du corps du rapport qui contient **cliquez pour ajouter un titre**, puis appuyez sur la touche Suppr.</span><span class="sxs-lookup"><span data-stu-id="16983-260">Click the text box at the top of the report body that contains **Click to add title**, and then press the Delete key.</span></span>  
  
3.  <span data-ttu-id="16983-261">Sous l’onglet **Insérer** du ruban, cliquez sur **en-tête** , puis sur **Ajouter un en-tête**.</span><span class="sxs-lookup"><span data-stu-id="16983-261">On the **Insert** tab of the ribbon, click **Header** and then click **Add Header**.</span></span>  
  
     <span data-ttu-id="16983-262">Un en-tête est ajouté en haut du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-262">A header is added to the top of the report body.</span></span>  
  
4.  <span data-ttu-id="16983-263">Sous l’onglet **Insérer** , cliquez sur **Zone de texte**, puis faites glisser une zone de texte à l’intérieur de l’en-tête du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-263">On the **Insert** tab, click **Text Box**, and then drag a text box inside the report header.</span></span> <span data-ttu-id="16983-264">Définissez sa taille sur environ 6 pouces de long et 0,75 pouce de haut et placez-la sur le côté gauche de l'en-tête de rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-264">Make the text box about 6 inches long and 3/4 inch tall and place it on the left side of the report header.</span></span>  
  
5.  <span data-ttu-id="16983-265">Dans la zone de texte, tapez **Sales by Territory, Subcategory, and Day**.</span><span class="sxs-lookup"><span data-stu-id="16983-265">In the text box, type **Sales by Territory, Subcategory, and Day**.</span></span>  
  
6.  <span data-ttu-id="16983-266">Sélectionnez le texte que vous avez tapé, cliquez dessus avec le bouton droit, puis cliquez sur **Propriétés du texte**.</span><span class="sxs-lookup"><span data-stu-id="16983-266">Select the text you typed, right-click, and then click **Text Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16983-267">Pour mettre en forme les caractères en même temps, ils doivent être contigus.</span><span class="sxs-lookup"><span data-stu-id="16983-267">To format characters at the same time, they must be contiguous.</span></span>  
  
7.  <span data-ttu-id="16983-268">Dans la boîte de dialogue **Propriétés du texte** , cliquez sur **police**.</span><span class="sxs-lookup"><span data-stu-id="16983-268">In the **Text Properties** dialog box, click **Font**.</span></span>  
  
8.  <span data-ttu-id="16983-269">Dans la liste **police** , sélectionnez **Times New Roman**; dans **taille** , sélectionnez **24 PT**, **dans couleur** , sélectionnez **marron**, puis dans **style** , sélectionnez **italique**.</span><span class="sxs-lookup"><span data-stu-id="16983-269">In the **Font** list, select **Times New Roman**; in **Size** select **24 pt**, in **Color** select **Maroon**, and in **Style** select **Italic**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="16983-270">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-270">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="16983-271">Le rapport inclut un titre de rapport dans l'en-tête de rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-271">The report includes a report title in the report header.</span></span>  
  
##  <a name="8-save-the-report"></a><a name="Save"></a><span data-ttu-id="16983-272">8. enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="16983-272">8. Save the Report</span></span>  
 <span data-ttu-id="16983-273">Vous pouvez enregistrer les rapports sur un serveur de rapports, dans une bibliothèque SharePoint ou sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="16983-273">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="16983-274">Dans ce didacticiel, enregistrez le rapport sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="16983-274">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="16983-275">Si vous n'avez pas accès à un serveur de rapports, enregistrez le rapport sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="16983-275">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="16983-276">Pour enregistrer le rapport sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="16983-276">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="16983-277">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="16983-277">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="16983-278">Cliquez sur **Sites et serveurs récents**.</span><span class="sxs-lookup"><span data-stu-id="16983-278">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="16983-279">Sélectionnez ou tapez le nom du serveur de rapports sur lequel vous êtes autorisé à enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="16983-279">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="16983-280">Le message « Connexion au serveur de rapports » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="16983-280">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="16983-281">Une fois la connexion établie, le contenu du dossier de rapports spécifié par l’administrateur du serveur de rapports s’affiche comme emplacement par défaut des rapports.</span><span class="sxs-lookup"><span data-stu-id="16983-281">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="16983-282">Dans **Nom**, remplacez le nom par défaut par **SalesByTerritorySubcategory**.</span><span class="sxs-lookup"><span data-stu-id="16983-282">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
5.  <span data-ttu-id="16983-283">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="16983-283">Click **Save**.</span></span>  
  
 <span data-ttu-id="16983-284">Le rapport est enregistré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="16983-284">The report is saved to the report server.</span></span> <span data-ttu-id="16983-285">Le nom du serveur de rapports auquel vous êtes connecté est indiqué dans la barre d'état située au bas de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="16983-285">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="16983-286">Pour enregistrer le rapport sur votre ordinateur</span><span class="sxs-lookup"><span data-stu-id="16983-286">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="16983-287">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="16983-287">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="16983-288">Cliquez sur **Bureau**, **Mes documents**ou **Poste de travail**, puis naviguez jusqu'au dossier où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-288">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="16983-289">Dans **Nom**, remplacez le nom par défaut par **SalesByTerritorySubcategory**.</span><span class="sxs-lookup"><span data-stu-id="16983-289">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
4.  <span data-ttu-id="16983-290">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="16983-290">Click **Save**.</span></span>  
  
##  <a name="9-optional-rotate-text-box-270-degrees"></a><a name="RotateTextBox"></a><span data-ttu-id="16983-291">9. (facultatif) faire pivoter la zone de texte de 270 degrés</span><span class="sxs-lookup"><span data-stu-id="16983-291">9. (Optional) Rotate Text Box 270 Degrees</span></span>  
 <span data-ttu-id="16983-292">Un rapport avec des matrices peut s'étendre horizontalement et verticalement lorsqu'il s'exécute.</span><span class="sxs-lookup"><span data-stu-id="16983-292">A report with matrices can expand horizontally and vertically when it runs.</span></span> <span data-ttu-id="16983-293">En faisant pivoter les zones de texte verticalement, ou de 270 degrés, vous pouvez gagner de l'espace horizontal.</span><span class="sxs-lookup"><span data-stu-id="16983-293">By rotating text boxes vertically, or 270 degrees, you can save horizontal space.</span></span> <span data-ttu-id="16983-294">Le rapport rendu sera alors plus étroit, et s'il est exporté dans un format tel que Microsoft Word, il rentrera plus facilement sur une page imprimée.</span><span class="sxs-lookup"><span data-stu-id="16983-294">The rendered report is then narrower and if exported to a format such as Microsoft Word, will be more likely to fit on a printed page.</span></span>  
  
 <span data-ttu-id="16983-295">Une zone de texte peut également afficher du texte horizontal dans le sens vertical (de haut en bas).</span><span class="sxs-lookup"><span data-stu-id="16983-295">A text box can also display text as horizontal, vertical (top to bottom).</span></span> <span data-ttu-id="16983-296">Pour plus d’informations, consultez [Zones de texte &#40;Générateur de rapports et SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="16983-296">For more information, see [Text Boxes &#40;Report Builder and SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-rotate-text-box-270-degrees"></a><span data-ttu-id="16983-297">Pour faire pivoter la zone de texte de 270 degrés</span><span class="sxs-lookup"><span data-stu-id="16983-297">To rotate text box 270 degrees</span></span>  
  
1.  <span data-ttu-id="16983-298">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="16983-298">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="16983-299">Cliquez sur la cellule qui contient `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="16983-299">Click the cell that contains `[Territory].`</span></span>  
  
3.  <span data-ttu-id="16983-300">Dans le volet Propriétés, recherchez la propriété WritingMode et, dans sa liste déroulante, sélectionnez **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="16983-300">In the Properties pane, locate the WritingMode property and in its drop-down list, select **Rotate270**.</span></span>  
  
     <span data-ttu-id="16983-301">Si le volet Propriétés n’est pas ouvert, cliquez sur l’onglet **Affichage** du ruban et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="16983-301">If the Properties pane is not open, click the **View** tab of the ribbon, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="16983-302">Vérifiez que la propriété CanGrow a la valeur `True` .</span><span class="sxs-lookup"><span data-stu-id="16983-302">Verify that the CanGrow property is set to `True`.</span></span>  
  
5.  <span data-ttu-id="16983-303">Redimensionnez la colonne Territory afin qu'elle fasse à 0,5 pouce de large et supprimez le titre de la colonne.</span><span class="sxs-lookup"><span data-stu-id="16983-303">Resize the Territory column to be 1/2 inch wide and delete the column title.</span></span>  
  
6.  <span data-ttu-id="16983-304">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="16983-304">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="16983-305">Le nom du secteur est écrit verticalement, de bas en haut.</span><span class="sxs-lookup"><span data-stu-id="16983-305">The territory name is written vertically, bottom to top.</span></span> <span data-ttu-id="16983-306">La hauteur du groupe de lignes Territory varie en fonction de la longueur du nom du secteur.</span><span class="sxs-lookup"><span data-stu-id="16983-306">The height of the Territory row group varies by the length of the territory name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="16983-307">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="16983-307">Next Steps</span></span>  
 <span data-ttu-id="16983-308">Ainsi s'achève le didacticiel de création d'un rapport de matrice.</span><span class="sxs-lookup"><span data-stu-id="16983-308">This concludes the tutorial for how to create a matrix report.</span></span> <span data-ttu-id="16983-309">Pour plus d’informations sur les matrices, consultez [tables, matrices et listes &#40;générateur de rapports et ssrs&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [matrices &#40;Générateur de rapports et SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), zones de région de données de tableau [matriciel &#40;générateur de rapports et SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)et [cellules, lignes et colonnes de région de données de tableau matriciel &#40;générateur de rapports&#41; et SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="16983-309">For more information about matrices, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Matrices &#40;Report Builder and SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16983-310">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16983-310">See Also</span></span>  
 <span data-ttu-id="16983-311">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="16983-311">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="16983-312">Générateur de rapports dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="16983-312">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
