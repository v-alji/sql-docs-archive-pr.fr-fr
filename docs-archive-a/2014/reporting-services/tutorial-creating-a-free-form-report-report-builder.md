---
title: 'Didacticiel : création d’un rapport au format libre (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 87288b59-faf2-4b1d-a8e4-a7582baedf2f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 515b0d2566efa4e11216a28648338c7ec43f3950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706135"
---
# <a name="tutorial-creating-a-free-form-report-report-builder"></a><span data-ttu-id="f6742-102">Didacticiel : création d'un rapport au format libre (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="f6742-102">Tutorial: Creating a Free Form Report (Report Builder)</span></span>
  <span data-ttu-id="f6742-103">Ce didacticiel vous apprend à créer un rapport de forme libre SSRS qui ressemble à une lettre type.</span><span class="sxs-lookup"><span data-stu-id="f6742-103">This tutorial teaches you how to create an SSRS free form report that resembles a forms letter.</span></span> <span data-ttu-id="f6742-104">Vous pouvez organiser les éléments du rapport pour créer un formulaire avec des zones de texte, des images et autres régions de données.</span><span class="sxs-lookup"><span data-stu-id="f6742-104">You can arrange report items to create a form with text boxes, images and other data regions.</span></span>

 <span data-ttu-id="f6742-105">Le rapport que vous créez dans ce didacticiel est basé sur des exemples de données de vente incluses dans le didacticiel.</span><span class="sxs-lookup"><span data-stu-id="f6742-105">The report you create in this tutorial is based on sample sales data that is included in the tutorial.</span></span> <span data-ttu-id="f6742-106">Le rapport regroupe les informations par secteur de vente et affiche le nom du directeur des ventes pour le secteur, ainsi que des informations détaillées et de synthèse sur les ventes.</span><span class="sxs-lookup"><span data-stu-id="f6742-106">The report groups information by territory and displays the name of the sales manager for the territory as well as detailed and summary sales information.</span></span> <span data-ttu-id="f6742-107">Vous allez utiliser la région de données de liste comme base du rapport de forme libre, puis ajouterez un panneau décoratif avec une image, du texte statique avec des données insérées, un tableau pour afficher les informations détaillées, et éventuellement, un graphique à secteurs et un histogramme pour afficher les informations de synthèse.</span><span class="sxs-lookup"><span data-stu-id="f6742-107">You will use the list data region as the foundation for the free form report, and then add a decorative panel with an image, static text with data inserted, a table to show detailed information, and optionally, pie and column charts to display summary information.</span></span>

##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="f6742-108">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="f6742-108">What You Will Learn</span></span>
 <span data-ttu-id="f6742-109">Dans ce didacticiel, vous apprendrez à effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6742-109">In this tutorial, you will learn how to do the following:</span></span>

-   [<span data-ttu-id="f6742-110">Créer un rapport, une source de données et un dataset vides</span><span class="sxs-lookup"><span data-stu-id="f6742-110">Create a Blank Report, Data Source, and Dataset</span></span>](#BlankReport)

-   [<span data-ttu-id="f6742-111">Ajouter et configurer une liste</span><span class="sxs-lookup"><span data-stu-id="f6742-111">Add and Configure a List</span></span>](#List)

-   [<span data-ttu-id="f6742-112">Ajouter des graphiques</span><span class="sxs-lookup"><span data-stu-id="f6742-112">Add Graphics</span></span>](#Graphics)

-   [<span data-ttu-id="f6742-113">Ajouter du texte de forme libre</span><span class="sxs-lookup"><span data-stu-id="f6742-113">Add Free Form Text</span></span>](#Text)

-   [<span data-ttu-id="f6742-114">Ajouter un tableau pour afficher les détails</span><span class="sxs-lookup"><span data-stu-id="f6742-114">Add a Table to Show Details</span></span>](#Table)

-   [<span data-ttu-id="f6742-115">Mettre en forme les données</span><span class="sxs-lookup"><span data-stu-id="f6742-115">Format Data</span></span>](#Format)

-   [<span data-ttu-id="f6742-116">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="f6742-116">Save the Report</span></span>](#Save)

### <a name="other-optional-steps"></a><span data-ttu-id="f6742-117">Autres étapes facultatives</span><span class="sxs-lookup"><span data-stu-id="f6742-117">Other Optional Steps</span></span>

-   [<span data-ttu-id="f6742-118">Ajouter une ligne pour séparer les zones du rapport</span><span class="sxs-lookup"><span data-stu-id="f6742-118">Add a Line to Separate Areas of Report</span></span>](#Line)

-   [<span data-ttu-id="f6742-119">Ajouter la visualisation des données de synthèse</span><span class="sxs-lookup"><span data-stu-id="f6742-119">Add Summary Data Visualization</span></span>](#Visualization)

 <span data-ttu-id="f6742-120">Durée estimée pour effectuer le didacticiel : 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="f6742-120">Estimated time to complete this tutorial: 20 minutes.</span></span>

## <a name="requirements"></a><span data-ttu-id="f6742-121">Spécifications</span><span class="sxs-lookup"><span data-stu-id="f6742-121">Requirements</span></span>
 <span data-ttu-id="f6742-122">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="f6742-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>

##  <a name="1-create-a-blank-report-data-source-and-dataset"></a><a name="BlankReport"></a><span data-ttu-id="f6742-123">1. créer un rapport vide, une source de données et un jeu de données</span><span class="sxs-lookup"><span data-stu-id="f6742-123">1. Create a Blank Report, Data Source, and Dataset</span></span>

> [!NOTE]
>  <span data-ttu-id="f6742-124">Dans ce didacticiel, la requête contient les valeurs de données, afin que le rapport n'ait pas besoin d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="f6742-124">In this tutorial, the query contains the data values so that the report does not need an external data source.</span></span> <span data-ttu-id="f6742-125">L'utilisation de ce type de données internes est très utile à des fins pédagogiques, mais l'approche rend la requête longue.</span><span class="sxs-lookup"><span data-stu-id="f6742-125">The use of this type of internal data is great for learning purposes, but the approach makes the query long.</span></span> <span data-ttu-id="f6742-126">.</span><span class="sxs-lookup"><span data-stu-id="f6742-126">.</span></span>

#### <a name="to-create-a-blank-report"></a><span data-ttu-id="f6742-127">Pour créer un rapport vierge</span><span class="sxs-lookup"><span data-stu-id="f6742-127">To create a blank report</span></span>

1.  <span data-ttu-id="f6742-128">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur **Générateur de rapports Microsoft SQL Server 2012**, puis cliquez sur **Générateur de rapports version**.</span><span class="sxs-lookup"><span data-stu-id="f6742-128">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f6742-129">La boîte de dialogue **Mise en route** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f6742-129">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="f6742-130">Si elle ne s'affiche pas, à partir du bouton Générateur de rapports, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f6742-130">If it does not, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="f6742-131">Dans le volet gauche de la boîte de dialogue **Mise en route** , assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f6742-131">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>

3.  <span data-ttu-id="f6742-132">Dans le volet droit, cliquez sur **Rapport vierge**.</span><span class="sxs-lookup"><span data-stu-id="f6742-132">In the right pane, click **Blank Report**.</span></span>

#### <a name="to-create-a-new-data-source"></a><span data-ttu-id="f6742-133">Pour créer une source de données</span><span class="sxs-lookup"><span data-stu-id="f6742-133">To create a new data source</span></span>

1.  <span data-ttu-id="f6742-134">Dans le volet données du rapport, cliquez sur **nouveau**, puis sur **source de données**.</span><span class="sxs-lookup"><span data-stu-id="f6742-134">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>

2.  <span data-ttu-id="f6742-135">Dans la `Name` zone, tapez : **ListDataSource**</span><span class="sxs-lookup"><span data-stu-id="f6742-135">In the `Name` box, type: **ListDataSource**</span></span>

3.  <span data-ttu-id="f6742-136">Cliquez sur **Utiliser une connexion incorporée dans mon rapport**.</span><span class="sxs-lookup"><span data-stu-id="f6742-136">Click **Use a connection embedded in my report**.</span></span>

4.  <span data-ttu-id="f6742-137">Vérifiez que le type de connexion est Microsoft SQL Server, puis dans la zone **chaîne de connexion** , tapez : source de \*\*données = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="f6742-137">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>

     <span data-ttu-id="f6742-138">\<servername>, par exemple Rapport001, spécifie un ordinateur sur lequel une instance du SQL Server Moteur de base de données est installée.</span><span class="sxs-lookup"><span data-stu-id="f6742-138">\<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="f6742-139">Dans la mesure où les données du rapport ne sont pas extraites d'une base de données SQL Server, vous n'avez pas besoin d'inclure le nom d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="f6742-139">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="f6742-140">La base de données par défaut sur le serveur spécifié est utilisée pour analyser la requête.</span><span class="sxs-lookup"><span data-stu-id="f6742-140">The default database on the specified server is used to parse the query.</span></span>

5.  <span data-ttu-id="f6742-141">Cliquez sur **Informations d'identification**, puis entrez les informations d'identification requises pour se connecter à l'instance du moteur de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f6742-141">Click **Credentials**, and enter the credentials needed to connect to the instance of the SQL Server Database Engine.</span></span>

6.  <span data-ttu-id="f6742-142">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6742-142">Click **OK**.</span></span>

#### <a name="to-create-a-new-dataset"></a><span data-ttu-id="f6742-143">Pour créer un dataset</span><span class="sxs-lookup"><span data-stu-id="f6742-143">To create a new dataset</span></span>

1.  <span data-ttu-id="f6742-144">Dans le volet des données de rapport, cliquez sur **Nouveau**, puis sur **Dataset**.</span><span class="sxs-lookup"><span data-stu-id="f6742-144">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>

2.  <span data-ttu-id="f6742-145">Dans la `Name` zone, tapez : **ListDataset.**</span><span class="sxs-lookup"><span data-stu-id="f6742-145">In the `Name` box, type: **ListDataset.**</span></span>

3.  <span data-ttu-id="f6742-146">Cliquez sur **Utiliser un dataset incorporé dans mon rapport**, puis vérifiez que la source de données est **ListDataSource**.</span><span class="sxs-lookup"><span data-stu-id="f6742-146">Click **Use a dataset embedded in my report**, and verify that the data source is **ListDataSource**.</span></span>

4.  <span data-ttu-id="f6742-147">Vérifiez que le type de requête **Texte** est sélectionné, puis cliquez sur **Concepteur de requêtes**.</span><span class="sxs-lookup"><span data-stu-id="f6742-147">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>

5.  <span data-ttu-id="f6742-148">Cliquez sur **Modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="f6742-148">Click **Edit as Text**.</span></span>

6.  <span data-ttu-id="f6742-149">Copiez et collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="f6742-149">Copy and paste the following query into the query pane:</span></span>

    ```
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity
    ```

7.  <span data-ttu-id="f6742-150">Cliquez sur l'icône Exécuter pour exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="f6742-150">Click Run icon to run the query.</span></span>

     <span data-ttu-id="f6742-151">Les résultats de la requête sont les données qui peuvent être affichées dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-151">The query results are the data available to display in your report.</span></span>

     <span data-ttu-id="f6742-152">![Concepteur de requêtes](../../2014/tutorials/media/tutorial-querydesigner.png "Concepteur de requêtes")</span><span class="sxs-lookup"><span data-stu-id="f6742-152">![Query Designer](../../2014/tutorials/media/tutorial-querydesigner.png "Query Designer")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="2-add-and-configure-a-list"></a><a name="List"></a><span data-ttu-id="f6742-153">2. Ajouter et configurer une liste</span><span class="sxs-lookup"><span data-stu-id="f6742-153">2. Add and Configure a List</span></span>
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="f6742-154">fournit trois modèles de région de données : tableau, matrice et liste.</span><span class="sxs-lookup"><span data-stu-id="f6742-154">provides three data region templates: table, matrix, and list.</span></span> <span data-ttu-id="f6742-155">Ces modèles sont tous basés sur une région de données de tableau matriciel.</span><span class="sxs-lookup"><span data-stu-id="f6742-155">These templates are all based on a tablix data region.</span></span>

 <span data-ttu-id="f6742-156">Dans ce didacticiel, vous allez utiliser une liste pour afficher les informations de ventes pour les secteurs de vente dans un rapport ayant l'apparence d'un bulletin d'informations.</span><span class="sxs-lookup"><span data-stu-id="f6742-156">In this tutorial, you will use a list to display the sales information for sales territories in a report that resembles a newsletter.</span></span> <span data-ttu-id="f6742-157">Les informations sont regroupées par secteur.</span><span class="sxs-lookup"><span data-stu-id="f6742-157">The information is grouped by territory.</span></span> <span data-ttu-id="f6742-158">Vous allez ajouter un nouveau groupe de lignes qui regroupe les données par secteur, puis vous supprimerez le groupe de lignes Détails intégré.</span><span class="sxs-lookup"><span data-stu-id="f6742-158">You will add a new row group that groups data by territory, and then delete the built-in Details row group.</span></span> <span data-ttu-id="f6742-159">Le modèle de liste est idéal pour la création de rapports de forme libre.</span><span class="sxs-lookup"><span data-stu-id="f6742-159">The list template is ideal for creating free form reports.</span></span> <span data-ttu-id="f6742-160">Pour plus d’informations, consultez la page [répertorie &#40;générateur de rapports et les&#41;SSRS ](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f6742-160">For more information, see [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="f6742-161">Ce rapport utilise le format de papier Letter (8,5 X 11) et des marges de 1 pouce.</span><span class="sxs-lookup"><span data-stu-id="f6742-161">This report uses the paper size Letter (8.5 X11) and 1 inch margins.</span></span> <span data-ttu-id="f6742-162">Une page de rapport de plus de 9 pouces de haut ou de plus de 6,5 pouces de large peut générer des pages vierges.</span><span class="sxs-lookup"><span data-stu-id="f6742-162">A report page taller than 9 inches or wider than 6 1/2 inches might generate blank pages.</span></span>

#### <a name="to-add-a-list"></a><span data-ttu-id="f6742-163">Pour ajouter une liste</span><span class="sxs-lookup"><span data-stu-id="f6742-163">To add a list</span></span>

1.  <span data-ttu-id="f6742-164">Sous l'onglet **Insertion** du ruban, dans la zone **Régions de données** , cliquez sur **Liste** , puis faites glisser la liste dans le corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-164">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List** and then drag the list inside the report body.</span></span> <span data-ttu-id="f6742-165">Définissez la taille de la liste sur 7 pouces de haut et 6,25 pouces de large.</span><span class="sxs-lookup"><span data-stu-id="f6742-165">Make the list 7 inches tall and 6.25 inches wide.</span></span>

2.  <span data-ttu-id="f6742-166">Cliquez dans la liste, cliquez avec le bouton droit en haut de la liste, puis cliquez sur **Propriétés du tableau matriciel**.</span><span class="sxs-lookup"><span data-stu-id="f6742-166">Click inside the list, right-click the top of the list, and then click **Tablix Properties**.</span></span>

     <span data-ttu-id="f6742-167">![Ajout de liste](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Ajout de liste")</span><span class="sxs-lookup"><span data-stu-id="f6742-167">![Adding list](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Adding list")</span></span>

3.  <span data-ttu-id="f6742-168">Dans la liste déroulante **Nom du dataset** , sélectionnez **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="f6742-168">In the **Dataset name** drop-down list, select **ListDataset**.</span></span>

4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

5.  <span data-ttu-id="f6742-169">Cliquez avec le bouton droit dans la liste, puis cliquez sur **Propriétés du rectangle**.</span><span class="sxs-lookup"><span data-stu-id="f6742-169">Right-click inside the list, and then click **Rectangle Properties**.</span></span>

     <span data-ttu-id="f6742-170">![Commande des propriétés de rectangle](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Commande des propriétés de rectangle")</span><span class="sxs-lookup"><span data-stu-id="f6742-170">![Rectangle Properties command](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Rectangle Properties command")</span></span>

6.  <span data-ttu-id="f6742-171">Sous l'onglet **Général** , activez la case à cocher **Insérer un saut de page après** .</span><span class="sxs-lookup"><span data-stu-id="f6742-171">On the **General** tab, select the **Add a page break after** checkbox.</span></span>

7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-new-row-group-and-to-delete-the-details-group"></a><span data-ttu-id="f6742-172">Pour ajouter un nouveau groupe de lignes et supprimer le groupe Détails</span><span class="sxs-lookup"><span data-stu-id="f6742-172">To add a new row group and to delete the Details group</span></span>

1.  <span data-ttu-id="f6742-173">Dans le volet Groupes de lignes, cliquez avec le bouton droit sur le groupe Détails, pointez sur **Ajouter un groupe**, puis cliquez sur **Groupe parent**.</span><span class="sxs-lookup"><span data-stu-id="f6742-173">In the Row Groups pane, right-click the Details group, point to **Add Group**, and then click **Parent Group**.</span></span>

     <span data-ttu-id="f6742-174">![Commande du groupe parent](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Commande du groupe parent")</span><span class="sxs-lookup"><span data-stu-id="f6742-174">![Parent Group command](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Parent Group command")</span></span>

2.  <span data-ttu-id="f6742-175">Dans la liste déroulante, sélectionnez `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="f6742-175">In the drop-down list, select `[Territory].`</span></span>

3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="f6742-176">Une colonne est ajoutée à la liste.</span><span class="sxs-lookup"><span data-stu-id="f6742-176">A column is added to the list.</span></span> <span data-ttu-id="f6742-177">La colonne contient la cellule `[Territory].`.</span><span class="sxs-lookup"><span data-stu-id="f6742-177">The column contains the cell `[Territory].`</span></span>

4.  <span data-ttu-id="f6742-178">Cliquez avec le bouton droit sur la colonne Territory dans la liste, puis cliquez sur **Supprimer les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="f6742-178">Right-click the Territory column in the list, and then click **Delete Columns**.</span></span>

     <span data-ttu-id="f6742-179">![Supprimer les colonnes](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Supprimer les colonnes")</span><span class="sxs-lookup"><span data-stu-id="f6742-179">![Delete columns](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Delete columns")</span></span>

5.  <span data-ttu-id="f6742-180">Sélectionnez **Supprimer les colonnes uniquement**.</span><span class="sxs-lookup"><span data-stu-id="f6742-180">Click **Delete Columns only**.</span></span>

     <span data-ttu-id="f6742-181">![Boîte de dialogue Supprimer les colonnes](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "boîte de dialogue Supprimer les colonnes")</span><span class="sxs-lookup"><span data-stu-id="f6742-181">![Delete Columns dialog box](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "Delete Columns dialog box")</span></span>

6.  <span data-ttu-id="f6742-182">Dans le volet Groupes de lignes, cliquez avec le bouton droit sur le groupe **Détails** , puis cliquez sur **Supprimer le groupe**.</span><span class="sxs-lookup"><span data-stu-id="f6742-182">In the Row Groups pane, right-click the **Details** group, and then click **Delete Group**.</span></span>

     <span data-ttu-id="f6742-183">![Supprimer le groupe des détails](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Supprimer le groupe des détails")</span><span class="sxs-lookup"><span data-stu-id="f6742-183">![Delete Details Group](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Delete Details Group")</span></span>

7.  <span data-ttu-id="f6742-184">Cliquez sur **Supprimer le groupe uniquement**.</span><span class="sxs-lookup"><span data-stu-id="f6742-184">Click **Delete Group only**.</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="3-add-graphics"></a><a name="Graphics"></a><span data-ttu-id="f6742-185">3. ajouter des graphiques</span><span class="sxs-lookup"><span data-stu-id="f6742-185">3. Add Graphics</span></span>
 <span data-ttu-id="f6742-186">L'un des avantages de l'utilisation d'une région de données de liste est que vous pouvez ajouter des éléments de rapport comme des rectangles et des zones de texte n'importe où, sans être limité par une disposition tabulaire.</span><span class="sxs-lookup"><span data-stu-id="f6742-186">One of the advantages of using a list data region is that you can add report items such as rectangles and text boxes anywhere, instead of being limited to a tabular layout.</span></span> <span data-ttu-id="f6742-187">Vous allez améliorer l'apparence du rapport en ajoutant un graphique (un rectangle rempli avec une couleur).</span><span class="sxs-lookup"><span data-stu-id="f6742-187">You will enhance the appearance of the report by adding a graphic (a rectangle filled with a color).</span></span>

#### <a name="to-add-graphic-elements-to-the-report"></a><span data-ttu-id="f6742-188">Pour ajouter des éléments graphiques au rapport</span><span class="sxs-lookup"><span data-stu-id="f6742-188">To add graphic elements to the report</span></span>

1.  <span data-ttu-id="f6742-189">Sous l’onglet **Insérer** du ruban, cliquez sur **rectangle**, puis faites glisser un rectangle dans l’angle supérieur gauche de la liste.</span><span class="sxs-lookup"><span data-stu-id="f6742-189">On the **Insert** tab of the ribbon, click **Rectangle**,and then drag a rectangle to the upper left corner of the list.</span></span> <span data-ttu-id="f6742-190">Définissez la taille du rectangle sur 7 pouces de haut et 1 pouce de large.</span><span class="sxs-lookup"><span data-stu-id="f6742-190">Make the rectangle 7 inches tall and 1 inch wide.</span></span>

2.  <span data-ttu-id="f6742-191">Cliquez avec le bouton droit sur le rectangle, puis cliquez sur **Propriétés du rectangle**.</span><span class="sxs-lookup"><span data-stu-id="f6742-191">Right-click the rectangle, and then click **Rectangle Properties**.</span></span>

3.  <span data-ttu-id="f6742-192">Cliquez sur l'onglet **Remplissage** .</span><span class="sxs-lookup"><span data-stu-id="f6742-192">Click the **Fill** tab.</span></span>

4.  <span data-ttu-id="f6742-193">Dans la liste déroulante **Couleur de remplissage** , cliquez sur **Couleurs supplémentaires**, puis sélectionnez la couleur **Gris foncé** .</span><span class="sxs-lookup"><span data-stu-id="f6742-193">In the **Fill color** drop-down list, click **More Colors**, and then select the **DarkGray** color.</span></span>

     <span data-ttu-id="f6742-194">![Sélectionner la couleur de remplissage](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Sélectionner la couleur de remplissage")</span><span class="sxs-lookup"><span data-stu-id="f6742-194">![Select fill color](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Select fill color")</span></span>

5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

6.  <span data-ttu-id="f6742-195">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-195">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="f6742-196">Le côté gauche du rapport a maintenant un graphique vertical formé d'un rectangle gris foncé.</span><span class="sxs-lookup"><span data-stu-id="f6742-196">The left side of the report now has vertical graphic that consists of a dark gray rectangle.</span></span>

##  <a name="4-add-free-form-text"></a><a name="Text"></a><span data-ttu-id="f6742-197">4. Ajouter un texte de forme libre</span><span class="sxs-lookup"><span data-stu-id="f6742-197">4. Add Free Form Text</span></span>
 <span data-ttu-id="f6742-198">Une zone de texte contient du texte statique qui est répété sur chaque page de rapport, ainsi que des champs de données.</span><span class="sxs-lookup"><span data-stu-id="f6742-198">A text box contains static text that is repeated on each report page as well as data fields.</span></span>

#### <a name="to-add-text-to-the-report"></a><span data-ttu-id="f6742-199">Pour ajouter du texte au rapport</span><span class="sxs-lookup"><span data-stu-id="f6742-199">To add text to the report</span></span>

1.  <span data-ttu-id="f6742-200">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f6742-200">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="f6742-201">Sous l'onglet **Insertion** du ruban, cliquez sur **Zone de texte**, puis faites glisser une zone de texte en haut à gauche de la liste, à l'intérieur du rectangle que vous avez ajouté précédemment.</span><span class="sxs-lookup"><span data-stu-id="f6742-201">On the **Insert** tab of the ribbon, click **Text Box**, and then drag a text box to the upper left corner of the list, but inside of the rectangle you added previously.</span></span> <span data-ttu-id="f6742-202">Définissez la taille de la zone de texte sur environ 3 pouces de haut et 5 pouces de large.</span><span class="sxs-lookup"><span data-stu-id="f6742-202">Make the text box about 3 inches tall and 5 inches wide.</span></span>

3.  <span data-ttu-id="f6742-203">Placez le curseur dans la partie supérieure de la zone de texte, puis tapez **Bulletin d'informations pour** .</span><span class="sxs-lookup"><span data-stu-id="f6742-203">Place the cursor in the upper part of the text box, and then type: **Newsletter for** .</span></span>

     <span data-ttu-id="f6742-204">![Ajouter un texte de titre au bulletin d’informations](../../2014/tutorials/media/tutorial-newsletterfor.png "Ajouter un texte de titre au bulletin d’informations")</span><span class="sxs-lookup"><span data-stu-id="f6742-204">![Add newsletter heading text](../../2014/tutorials/media/tutorial-newsletterfor.png "Add newsletter heading text")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f6742-205">Veillez à inclure l'espace supplémentaire après « pour ».</span><span class="sxs-lookup"><span data-stu-id="f6742-205">Be sure to include the extra space after the word "for".</span></span> <span data-ttu-id="f6742-206">Cet espace sépare le texte du champ que vous allez ajouter à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="f6742-206">The space separates the text and the field that you will add in the next step.</span></span>

4.  <span data-ttu-id="f6742-207">Faites glisser le champ Territory vers la zone de texte et placez-le après le texte que vous avez tapé à l'étape 3.</span><span class="sxs-lookup"><span data-stu-id="f6742-207">Drag the Territory field to the text box and place it after the text you typed in step 3.</span></span>

     <span data-ttu-id="f6742-208">![Ajouter le champ du secteur de vente](../../2014/tutorials/media/tutorial-addterritorialfield.png "Ajouter le champ du secteur de vente")</span><span class="sxs-lookup"><span data-stu-id="f6742-208">![Add Territorial field](../../2014/tutorials/media/tutorial-addterritorialfield.png "Add Territorial field")</span></span>

5.  <span data-ttu-id="f6742-209">Sélectionnez tout le texte, cliquez avec le bouton droit, puis cliquez sur **Propriétés du texte**.</span><span class="sxs-lookup"><span data-stu-id="f6742-209">Select all text, right-click, and then click **Text Properties**.</span></span>

6.  <span data-ttu-id="f6742-210">Cliquez sur l'onglet **Police** .</span><span class="sxs-lookup"><span data-stu-id="f6742-210">Click the **Font** tab.</span></span>

7.  <span data-ttu-id="f6742-211">Dans la liste **Police** , sélectionnez **Times New Roman**; dans **Taille** , sélectionnez **20 pt**; dans **Couleur** , sélectionnez **Rouge**.</span><span class="sxs-lookup"><span data-stu-id="f6742-211">In the **Font** list, select **Times New Roman**; in **Size** select **20 pt**, in **Color** select **Red**.</span></span>

     <span data-ttu-id="f6742-212">![Propriétés du texte](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Propriétés du texte")</span><span class="sxs-lookup"><span data-stu-id="f6742-212">![Text Properties](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Text Properties")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

9. <span data-ttu-id="f6742-213">Placez le curseur sous le texte que vous avez tapé à l'étape 3 et tapez **Bonjour** .</span><span class="sxs-lookup"><span data-stu-id="f6742-213">Place the cursor below the text you typed in step 3 and type: **Hello** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f6742-214">Veillez à inclure l'espace supplémentaire après « Bonjour ».</span><span class="sxs-lookup"><span data-stu-id="f6742-214">Be sure to include the extra space after the word "Hello".</span></span> <span data-ttu-id="f6742-215">Cet espace sépare le texte du champ que vous allez ajouter à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="f6742-215">The space separates the text and the field that you will add in the next step.</span></span>

10. <span data-ttu-id="f6742-216">Faites glisser le champ FullName vers la zone de texte et placez-le après le texte que vous avez tapé à l'étape 9, puis tape une virgule (,).</span><span class="sxs-lookup"><span data-stu-id="f6742-216">Drag the FullName field to the text box and place it after the text you typed in step 9, and then type a comma (,).</span></span>

     <span data-ttu-id="f6742-217">![Ajouter le champ du nom complet](../../2014/tutorials/media/tutorial-addfullnamefield.png "Ajouter le champ du nom complet")</span><span class="sxs-lookup"><span data-stu-id="f6742-217">![Add Full Name field](../../2014/tutorials/media/tutorial-addfullnamefield.png "Add Full Name field")</span></span>

11. <span data-ttu-id="f6742-218">Sélectionnez le texte que vous avez ajouté aux étapes 9 et 10, cliquez avec le bouton droit, puis cliquez sur **Propriétés du texte**.</span><span class="sxs-lookup"><span data-stu-id="f6742-218">Select the text you added in steps 9 and 10, right-click, and then click **Text Properties**.</span></span>

12. <span data-ttu-id="f6742-219">Cliquez sur l'onglet **Police** .</span><span class="sxs-lookup"><span data-stu-id="f6742-219">Click the **Font** tab.</span></span>

13. <span data-ttu-id="f6742-220">Dans la liste **Police** , sélectionnez **Times New Roman**; dans **Taille** , sélectionnez **16 pt**; dans **Couleur** , sélectionnez **Noir** .</span><span class="sxs-lookup"><span data-stu-id="f6742-220">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Black** color.</span></span>

14. [!INCLUDE[clickOK](../includes/clickok-md.md)]

15. <span data-ttu-id="f6742-221">Placez le curseur sous le texte que vous avez ajouté aux étapes 9 à 13, puis copiez et collez le texte grec suivant :</span><span class="sxs-lookup"><span data-stu-id="f6742-221">Place the cursor below the text you added in steps 9 through 13, and then copy and paste the following "greeked" text:</span></span>

    ```
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin sed dolor in ipsum pulvinar egestas. Sed sed lacus at leo ornare ultricies. Vivamus velit risus, euismod nec sodales gravida, gravida in dui. Etiam ullamcorper elit vitae justo fermentum ut ullamcorper augue sodales. Ut placerat, nisl quis feugiat adipiscing, nibh est aliquet est, mollis faucibus mauris lectus quis arcu. In mollis tincidunt lacinia. In vitae erat ut lorem tincidunt luctus. Curabitur et magna nunc, sit amet adipiscing nisi. Nulla rhoncus elementum orci nec tincidunt. Aliquam imperdiet cursus erat vel tincidunt. Donec et neque ac urna rutrum sodales. In id purus et nisl dignissim dapibus. Sed rhoncus metus at felis feugiat eu tempor dolor vehicula. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam faucibus consectetur diam eu pellentesque. 
    Nulla facilisi. Proin ligula enim, porta ut tincidunt id, adipiscing sit amet eros. Ut purus sem, bibendum et vulputate sit amet, facilisis eget magna. Sed aliquam erat non erat eleifend hendrerit. Ut a ligula est, sit amet eleifend enim. Ut et nisl enim, sit amet adipiscing augue. Vivamus eu arcu ac libero posuere elementum. Integer condimentum bibendum venenatis. Integer odio tellus, feugiat in pellentesque semper, interdum nec sem. Sed cursus euismod sem, ut elementum sapien placerat vel. 
    ```

16. <span data-ttu-id="f6742-222">Sélectionnez le texte que vous avez ajouté à l'étape 15, cliquez avec le bouton droit, puis cliquez sur **Propriétés du texte**.</span><span class="sxs-lookup"><span data-stu-id="f6742-222">Select the text you added in steps 15, right-click, and then click **Text Properties**.</span></span>

17. <span data-ttu-id="f6742-223">Cliquez sur l'onglet **Police** .</span><span class="sxs-lookup"><span data-stu-id="f6742-223">Click the **Font** tab.</span></span>

18. <span data-ttu-id="f6742-224">Dans la liste **Police** , sélectionnez **Arial**; dans **Taille** , sélectionnez **10 pt**; dans **Couleur** , sélectionnez **Noir**.</span><span class="sxs-lookup"><span data-stu-id="f6742-224">In the **Font** list, select **Arial**; in **Size** select **10 pt**, in **Color** select **Black**.</span></span>

19. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="f6742-225">![Ajouter le texte du bulletin d'informations](../../2014/tutorials/media/tutorial-newslettertext.png "Ajouter le texte du bulletin d'informations")</span><span class="sxs-lookup"><span data-stu-id="f6742-225">![Add newsletter text](../../2014/tutorials/media/tutorial-newslettertext.png "Add newsletter text")</span></span>

20. <span data-ttu-id="f6742-226">Placez le curseur sous le texte que vous avez collé à étape 15, puis tapez **Félicitations pour le total de vos ventes,** .</span><span class="sxs-lookup"><span data-stu-id="f6742-226">Place the cursor below the text you pasted in step 15, and then type: **Congratulations on your total sales of** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f6742-227">Veillez à inclure l'espace supplémentaire après la virgule.</span><span class="sxs-lookup"><span data-stu-id="f6742-227">Be sure to include the extra space after the word "of".</span></span> <span data-ttu-id="f6742-228">Cet espace sépare le texte du champ que vous allez ajouter à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="f6742-228">The space separates the text and the field that you will add in the next step.</span></span>

21. <span data-ttu-id="f6742-229">Faites glisser le champ Ventes vers la zone de texte, placez-le après le texte que vous avez tapé à l'étape 20, puis tapez un point d'exclamation (!).</span><span class="sxs-lookup"><span data-stu-id="f6742-229">Drag the Sales field to the text box, place it after the text you typed in step 20, and then type an exclamation mark (!).</span></span>

22. <span data-ttu-id="f6742-230">Mettez en surbrillance le champ Sales, cliquez avec le bouton droit sur le champ, puis cliquez sur **expression**.</span><span class="sxs-lookup"><span data-stu-id="f6742-230">Highlight the Sales field, right-click the field, and then click **Expression**.</span></span>

23. <span data-ttu-id="f6742-231">Dans la zone d'expression, modifiez l'expression pour inclure la fonction Sum comme suit :</span><span class="sxs-lookup"><span data-stu-id="f6742-231">In the expression box, change the expression to include the Sum function as follows:</span></span>

    ```
    =Sum(Fields!Sales.value)
    ```

24. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="f6742-232">![Ajouter une expression au champ des ventes](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Ajouter une expression au champ des ventes")</span><span class="sxs-lookup"><span data-stu-id="f6742-232">![Add an expression to sales field](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Add an expression to sales field")</span></span>

25. <span data-ttu-id="f6742-233">Sélectionnez le texte que vous avez ajouté aux étapes 20 à 23, cliquez avec le bouton droit, puis cliquez sur **Propriétés du texte**.</span><span class="sxs-lookup"><span data-stu-id="f6742-233">Select the text you added in steps 20 through 23, right-click, and then click **Text Properties**.</span></span>

26. <span data-ttu-id="f6742-234">Cliquez sur l'onglet **Police** .</span><span class="sxs-lookup"><span data-stu-id="f6742-234">Click the **Font** tab.</span></span>

27. <span data-ttu-id="f6742-235">Dans la liste **Police** , sélectionnez **Times New Roman**; dans **Taille** , sélectionnez **16 pt**; dans **Couleur** , sélectionnez **Rouge**.</span><span class="sxs-lookup"><span data-stu-id="f6742-235">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Red**.</span></span>

28. [!INCLUDE[clickOK](../includes/clickok-md.md)]

29. <span data-ttu-id="f6742-236">Sélectionnez `[Sum(Sales)]` , puis sous l'onglet **Accueil** , dans le groupe **Nombre** , cliquez sur le bouton **Devise** .</span><span class="sxs-lookup"><span data-stu-id="f6742-236">Select `[Sum(Sales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="f6742-237">![Ajouter un symbole monétaire](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Ajouter un symbole monétaire")</span><span class="sxs-lookup"><span data-stu-id="f6742-237">![Add currency symbol](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Add currency symbol")</span></span>

30. <span data-ttu-id="f6742-238">Cliquez avec le bouton droit sur la zone de texte contenant le texte « Cliquez pour ajouter un titre », puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="f6742-238">Right-click the text box with the "Click to add title" text, and then click **Delete**.</span></span>

31. <span data-ttu-id="f6742-239">Sélectionnez la zone de liste et à l'aide des touches de direction, déplacez-la vers le haut de la page.</span><span class="sxs-lookup"><span data-stu-id="f6742-239">Select the list box and using the arrow keys, move it to the top of the page.</span></span>

32. <span data-ttu-id="f6742-240">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-240">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="f6742-241">Le rapport affiche le texte statique et chaque page du rapport inclut des données relatives à un secteur de vente.</span><span class="sxs-lookup"><span data-stu-id="f6742-241">The report displays static text and each report page includes data that pertains to a territory.</span></span> <span data-ttu-id="f6742-242">Les ventes sont mises en forme en tant que valeurs monétaires.</span><span class="sxs-lookup"><span data-stu-id="f6742-242">Sales are formatted as currency.</span></span>

 <span data-ttu-id="f6742-243">![Aperçu du bulletin d'informations](../../2014/tutorials/media/tutorial-newsletters.png "Aperçu du bulletin d'informations")</span><span class="sxs-lookup"><span data-stu-id="f6742-243">![Preview of Newsletter](../../2014/tutorials/media/tutorial-newsletters.png "Preview of Newsletter")</span></span>

##  <a name="5-add-a-table-to-show-sales-details"></a><a name="Table"></a><span data-ttu-id="f6742-244">5. Ajouter une table pour afficher les détails des ventes</span><span class="sxs-lookup"><span data-stu-id="f6742-244">5. Add a Table to Show Sales Details</span></span>
 <span data-ttu-id="f6742-245">Utilisez l'Assistant Nouveau tableau ou nouvelle matrice pour ajouter un tableau au rapport de forme libre.</span><span class="sxs-lookup"><span data-stu-id="f6742-245">Use the New Table and Matrix Wizard to add a table to the free form report.</span></span> <span data-ttu-id="f6742-246">Après avoir terminé l'Assistant, vous ajouterez manuellement une ligne pour les totaux.</span><span class="sxs-lookup"><span data-stu-id="f6742-246">After you complete the wizard, you will manually add a row for totals.</span></span>

#### <a name="to-add-a-table"></a><span data-ttu-id="f6742-247">Pour ajouter un tableau</span><span class="sxs-lookup"><span data-stu-id="f6742-247">To add a table</span></span>

1.  <span data-ttu-id="f6742-248">Sous l'onglet **Insertion** du ruban, dans la zone **Régions de données** , cliquez sur **Tableau**, puis sur **Assistant Tableau**.</span><span class="sxs-lookup"><span data-stu-id="f6742-248">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **Table**, and then click **Table Wizard**.</span></span>

2.  <span data-ttu-id="f6742-249">Dans la page Choisir un dataset, cliquez sur **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="f6742-249">On the Choose a dataset page, click **ListDataset**.</span></span>

3.  <span data-ttu-id="f6742-250">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f6742-250">Click **Next**.</span></span>

4.  <span data-ttu-id="f6742-251">Dans la page **Organiser les champs** , faites glisser le champ Product de **Champs disponibles** vers **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="f6742-251">On the **Arrange fields** page, drag the Product field from **Available fields** to **Values.**</span></span>

5.  <span data-ttu-id="f6742-252">Répétez l'étape 4 pour SalesDate, Quantity et Sales.</span><span class="sxs-lookup"><span data-stu-id="f6742-252">Repeat step 4, for SalesDate, Quantity, and Sales.</span></span> <span data-ttu-id="f6742-253">Placez SalesDate sous Product, Quantity sous SalesDate et Sales sous SalesDate.</span><span class="sxs-lookup"><span data-stu-id="f6742-253">Place SalesDate below Product, Quantity below SalesDate, and Sales below SalesDate.</span></span>

6.  <span data-ttu-id="f6742-254">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f6742-254">Click **Next**.</span></span>

7.  <span data-ttu-id="f6742-255">Dans la page **Choisir la disposition** , observez la mise en page de la table.</span><span class="sxs-lookup"><span data-stu-id="f6742-255">On the **Choose the layout** page, view the layout of the table.</span></span>

     <span data-ttu-id="f6742-256">Le tableau est très simple.</span><span class="sxs-lookup"><span data-stu-id="f6742-256">The table is very simple.</span></span> <span data-ttu-id="f6742-257">Il comporte cinq colonnes et aucun groupe de lignes ni de colonnes.</span><span class="sxs-lookup"><span data-stu-id="f6742-257">It consists of five columns and has no row or column groups.</span></span> <span data-ttu-id="f6742-258">Dans la mesure où il ne comporte aucun groupe, les options de mise en page relatives aux groupes ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="f6742-258">Because it has no groups, the layout options related to groups, are not available.</span></span> <span data-ttu-id="f6742-259">Vous mettrez manuellement à jour le tableau ultérieurement de manière à inclure un total.</span><span class="sxs-lookup"><span data-stu-id="f6742-259">You will manually update the table to include a total later in the tutorial.</span></span>

8.  <span data-ttu-id="f6742-260">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f6742-260">Click **Next**.</span></span>

9. <span data-ttu-id="f6742-261">Dans la page **Choisir un style** , dans le volet **Styles** , sélectionnez **Ardoise**.</span><span class="sxs-lookup"><span data-stu-id="f6742-261">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

10. <span data-ttu-id="f6742-262">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f6742-262">Click **Finish**.</span></span>

11. <span data-ttu-id="f6742-263">Faites glisser le tableau sous la zone de texte que vous avez ajoutée dans la leçon 4.</span><span class="sxs-lookup"><span data-stu-id="f6742-263">Drag the table to below the text box that you added in lesson 4.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f6742-264">Assurez-vous que le tableau est à l'intérieur de la liste.</span><span class="sxs-lookup"><span data-stu-id="f6742-264">Make sure the table is inside the list.</span></span>

12. <span data-ttu-id="f6742-265">Vérifiez que la table est sélectionnée, puis, dans le volet Groupe de lignes, cliquez avec le bouton droit sur Détails, pointez sur **Ajouter un total**, puis cliquez sur **Après**.</span><span class="sxs-lookup"><span data-stu-id="f6742-265">Confirmed that the table is selected, then in the Row Group pane right-click Details, point to **Add Total**, and then click **After**.</span></span>

     <span data-ttu-id="f6742-266">![Ajouter le total du rapport](../../2014/tutorials/media/tutorial-addtotal.png "Ajouter le total du rapport")</span><span class="sxs-lookup"><span data-stu-id="f6742-266">![Add report total](../../2014/tutorials/media/tutorial-addtotal.png "Add report total")</span></span>

13. <span data-ttu-id="f6742-267">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-267">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="f6742-268">Le rapport affiche un tableau avec les détails des ventes et les totaux.</span><span class="sxs-lookup"><span data-stu-id="f6742-268">The report displays a table with sales details and totals.</span></span>

 <span data-ttu-id="f6742-269">![Total des ventes dans le rapport](../../2014/tutorials/media/tutorial-reportsalestotals.png "Total des ventes dans le rapport")</span><span class="sxs-lookup"><span data-stu-id="f6742-269">![Sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals.png "Sales totals in report")</span></span>

##  <a name="6-format-data"></a><a name="Format"></a><span data-ttu-id="f6742-270">6. mettre en forme les données</span><span class="sxs-lookup"><span data-stu-id="f6742-270">6. Format Data</span></span>
 <span data-ttu-id="f6742-271">Mettez en forme les données numériques sous forme de valeurs monétaires et les dates sous forme de jour et heure.</span><span class="sxs-lookup"><span data-stu-id="f6742-271">Format numeric data as currency and dates as day and time only.</span></span>

#### <a name="to-format-fields-table"></a><span data-ttu-id="f6742-272">Pour mettre en forme les champs du tableau</span><span class="sxs-lookup"><span data-stu-id="f6742-272">To format fields table</span></span>

1.  <span data-ttu-id="f6742-273">Cliquez sur **Conception** pour basculer en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f6742-273">Click **Design** to switch to design view.</span></span>

2.  <span data-ttu-id="f6742-274">Cliquez sur les cellules du tableau qui contiennent `[Sum(SalesSales)]` et sous l'onglet **Accueil** , dans le groupe **Nombre** , cliquez sur le bouton **Devise** .</span><span class="sxs-lookup"><span data-stu-id="f6742-274">Click the table cells that contain `[Sum(SalesSales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="f6742-275">![Ajouter un symbole monétaire à la somme des ventes](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Ajouter un symbole monétaire à la somme des ventes")</span><span class="sxs-lookup"><span data-stu-id="f6742-275">![Add currency symbol to sum sales](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Add currency symbol to sum sales")</span></span>

3.  <span data-ttu-id="f6742-276">Cliquez sur la cellule qui contient `[SalesDate]` et dans le groupe **Nombre** , dans la liste déroulante, sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="f6742-276">Click the cell that contains `[SalesDate]` and in the **Number** group, from the drop-down list, select **Date**.</span></span>

4.  <span data-ttu-id="f6742-277">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-277">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="f6742-278">Le rapport affiche maintenant les données mises en forme et est plus facile à lire.</span><span class="sxs-lookup"><span data-stu-id="f6742-278">The report now displays formatted data and is easier to read.</span></span>

 <span data-ttu-id="f6742-279">![Mettre en forme le total des ventes dans le rapport](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Mettre en forme le total des ventes dans le rapport")</span><span class="sxs-lookup"><span data-stu-id="f6742-279">![Format sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Format sales totals in report")</span></span>

##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="f6742-280">7. enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="f6742-280">7. Save the Report</span></span>
 <span data-ttu-id="f6742-281">Vous pouvez enregistrer les rapports sur un serveur de rapports, dans une bibliothèque SharePoint ou sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f6742-281">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="f6742-282">Vous pouvez également exporter le rapport dans de nombreux formats tels que Word et PDF ; pour ce faire, exécutez le rapport, puis sélectionnez le format dans le menu **Exporter** .</span><span class="sxs-lookup"><span data-stu-id="f6742-282">You can also export the report to a variety of formats such as Word and PDF, by running the report and selecting the format from the **Export** menu.</span></span>

 <span data-ttu-id="f6742-283">Dans ce didacticiel, enregistrez le rapport sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="f6742-283">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="f6742-284">Si vous n'avez pas accès à un serveur de rapports, enregistrez le rapport sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f6742-284">If you do not have access to a report server, save the report to your computer.</span></span>

#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="f6742-285">Pour enregistrer le rapport sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="f6742-285">To save the report on a report server</span></span>

1.  <span data-ttu-id="f6742-286">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="f6742-286">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="f6742-287">Cliquez sur **Sites et serveurs récents**.</span><span class="sxs-lookup"><span data-stu-id="f6742-287">Click **Recent Sites and Servers**.</span></span>

3.  <span data-ttu-id="f6742-288">Sélectionnez ou tapez le nom du serveur de rapports sur lequel vous êtes autorisé à enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="f6742-288">Select or type the name of the report server where you have permission to save reports.</span></span>

     <span data-ttu-id="f6742-289">Le message « Connexion au serveur de rapports » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f6742-289">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="f6742-290">Une fois la connexion établie, le contenu du dossier de rapports spécifié par l'administrateur du serveur de rapports s'affiche comme emplacement par défaut des rapports.</span><span class="sxs-lookup"><span data-stu-id="f6742-290">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>

4.  <span data-ttu-id="f6742-291">Dans `Name` , remplacez le nom par défaut par **SalesInformationByTerritory**.</span><span class="sxs-lookup"><span data-stu-id="f6742-291">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

5.  <span data-ttu-id="f6742-292">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f6742-292">Click **Save**.</span></span>

 <span data-ttu-id="f6742-293">Le rapport est enregistré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="f6742-293">The report is saved to the report server.</span></span> <span data-ttu-id="f6742-294">Le nom du serveur de rapports auquel vous êtes connecté est indiqué dans la barre d'état située au bas de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="f6742-294">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>

#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="f6742-295">Pour enregistrer le rapport sur votre ordinateur</span><span class="sxs-lookup"><span data-stu-id="f6742-295">To save the report on your computer</span></span>

1.  <span data-ttu-id="f6742-296">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="f6742-296">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="f6742-297">Cliquez sur **Bureau**, **Mes documents**ou **Poste de travail**, puis naviguez jusqu'au dossier où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-297">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>

3.  <span data-ttu-id="f6742-298">Dans `Name` , remplacez le nom par défaut par **SalesInformationByTerritory**.</span><span class="sxs-lookup"><span data-stu-id="f6742-298">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

4.  <span data-ttu-id="f6742-299">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f6742-299">Click **Save**.</span></span>

##  <a name="8-optional-add-a-line-to-separate-areas-of-the-report"></a><a name="Line"></a><span data-ttu-id="f6742-300">8. (facultatif) ajouter une ligne pour séparer les zones du rapport</span><span class="sxs-lookup"><span data-stu-id="f6742-300">8. (Optional) Add a Line to Separate Areas of the Report</span></span>
 <span data-ttu-id="f6742-301">Ajoutez une ligne pour séparer la zone éditoriale de la zone de détails dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-301">Add a line to separate the editorial and details areas of the report.</span></span>

#### <a name="to-add-a-line"></a><span data-ttu-id="f6742-302">Pour ajouter une ligne</span><span class="sxs-lookup"><span data-stu-id="f6742-302">To add a line</span></span>

1.  <span data-ttu-id="f6742-303">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f6742-303">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="f6742-304">Sous l'onglet **Insertion** du ruban, dans la zone **Éléments de rapport** , cliquez sur **Ligne**.</span><span class="sxs-lookup"><span data-stu-id="f6742-304">On the **Insert** tab of the ribbon, in the **Report Items** area, click **Line.**</span></span>

3.  <span data-ttu-id="f6742-305">Dessinez une ligne sous la zone de texte de forme libre que vous avez ajoutée dans la leçon 4.</span><span class="sxs-lookup"><span data-stu-id="f6742-305">Draw a line below the free form text box you added in lesson 4.</span></span>

4.  <span data-ttu-id="f6742-306">Cliquez sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="f6742-306">Click the line.</span></span>

5.  <span data-ttu-id="f6742-307">Cliquez sur l'onglet **Accueil** .</span><span class="sxs-lookup"><span data-stu-id="f6742-307">Click the **Home** tab.</span></span>

6.  <span data-ttu-id="f6742-308">Dans la zone **Bordure** , sélectionnez une largeur de **4 1/2** points et la couleur **Rouge**.</span><span class="sxs-lookup"><span data-stu-id="f6742-308">In the **Border** area, for width select **4 1/2** pt and for color, for color select **Red**.</span></span>

     <span data-ttu-id="f6742-309">![Ajouter une ligne au rapport](../../2014/tutorials/media/tutorial-reportwithline.png "Ajouter une ligne au rapport")</span><span class="sxs-lookup"><span data-stu-id="f6742-309">![Add line to report](../../2014/tutorials/media/tutorial-reportwithline.png "Add line to report")</span></span>

##  <a name="9-optional-add-summary-data-visualization"></a><a name="Visualization"></a><span data-ttu-id="f6742-310">9. (facultatif) ajouter la visualisation des données de synthèse</span><span class="sxs-lookup"><span data-stu-id="f6742-310">9. (Optional) Add Summary Data Visualization</span></span>
 <span data-ttu-id="f6742-311">Les rectangles vous aident à contrôler le rendu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-311">Rectangles help you control how the report renders.</span></span> <span data-ttu-id="f6742-312">Placez un graphique à secteurs et un histogramme à l'intérieur d'un rectangle pour vérifier que le rendu du rapport est conforme à vos attentes</span><span class="sxs-lookup"><span data-stu-id="f6742-312">Place a pie and column chart inside a rectangle to ensure that the report renders the way you want.</span></span>

#### <a name="to-add-a-rectangle"></a><span data-ttu-id="f6742-313">Pour ajouter un rectangle</span><span class="sxs-lookup"><span data-stu-id="f6742-313">To add a rectangle</span></span>

1.  <span data-ttu-id="f6742-314">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f6742-314">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="f6742-315">Sous l'onglet **Insertion** du ruban, dans la zone **Éléments de rapport** , cliquez sur **Rectangle**, puis fait glisser le rectangle à l'intérieur de la liste, à droite du tableau.</span><span class="sxs-lookup"><span data-stu-id="f6742-315">On the **Insert** tab of the ribbon, in the **Report Items** area click **Rectangle**, and then drag the rectangle inside the list, to the right of the table.</span></span> <span data-ttu-id="f6742-316">Définissez la taille du rectangle sur 2 pouces de large et 4 pouces de haut.</span><span class="sxs-lookup"><span data-stu-id="f6742-316">Make the rectangle 2 inches wide and 4 inches tall.</span></span>

3.  <span data-ttu-id="f6742-317">Alignez le haut du rectangle et le haut du tableau.</span><span class="sxs-lookup"><span data-stu-id="f6742-317">Align the tops of the rectangle and the table.</span></span>

#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="f6742-318">Pour ajouter un graphique à secteurs</span><span class="sxs-lookup"><span data-stu-id="f6742-318">To add a pie chart</span></span>

1.  <span data-ttu-id="f6742-319">Sous l'onglet **Insertion** du ruban, dans la zone **Visualisations des données** , cliquez sur **Graphique** , puis sur **Assistant Graphique**.</span><span class="sxs-lookup"><span data-stu-id="f6742-319">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="f6742-320">Dans la page Choisir un dataset , cliquez sur **ListDataset**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f6742-320">On the Choose a dataset page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="f6742-321">Cliquez sur **Secteurs**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f6742-321">Click **Pie**, and then click **Next**.</span></span>

4.  <span data-ttu-id="f6742-322">Sur la page Organiser les champs du graphique, faites glisser Product vers **Catégories**.</span><span class="sxs-lookup"><span data-stu-id="f6742-322">On the arrange chart fields page, drag Product to **Categories**.</span></span>

5.  <span data-ttu-id="f6742-323">Faites glisser Quantity vers **valeurs**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f6742-323">Drag Quantity to **Values**, and then click **Next**.</span></span>

6.  <span data-ttu-id="f6742-324">Dans la page **Choisir un style** , dans le volet **Styles** , sélectionnez **Ardoise**.</span><span class="sxs-lookup"><span data-stu-id="f6742-324">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="f6742-325">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f6742-325">Click **Finish**.</span></span>

8.  <span data-ttu-id="f6742-326">Redimensionnez le graphique qui s'affiche dans le coin supérieur gauche du rapport afin qu'il fasse 1,5 pouce de haut et 2 pouces de large.</span><span class="sxs-lookup"><span data-stu-id="f6742-326">Resize the chart that appears in the upper left corner of the report, to be 1 1/2 inches tall and 2 inches wide.</span></span>

9. <span data-ttu-id="f6742-327">Faites glisser le graphique à l'intérieur du rectangle.</span><span class="sxs-lookup"><span data-stu-id="f6742-327">Drag the chart inside the rectangle.</span></span>

     <span data-ttu-id="f6742-328">![Ajouter un graphique en secteurs](../../2014/tutorials/media/tutorial-addpiechart.png "Ajouter un graphique en secteurs")</span><span class="sxs-lookup"><span data-stu-id="f6742-328">![Add pie chart](../../2014/tutorials/media/tutorial-addpiechart.png "Add pie chart")</span></span>

10. <span data-ttu-id="f6742-329">Cliquez avec le bouton droit sur le titre du graphique, puis cliquez sur **Propriétés du titre**.</span><span class="sxs-lookup"><span data-stu-id="f6742-329">Right-click the chart title, and then click **Title Properties**.</span></span>

11. <span data-ttu-id="f6742-330">Dans la boîte de dialogue **Propriétés du titre du graphique** , dans le texte du titre, tapez **Quantités de produits vendues**.</span><span class="sxs-lookup"><span data-stu-id="f6742-330">In the **Chart Title Properties** dialog box, in Title text, type: **Product Quantities Sold**.</span></span>

12. <span data-ttu-id="f6742-331">Cliquez sur l'onglet **Police** , puis dans la liste **Taille** , cliquez sur **10pt**.</span><span class="sxs-lookup"><span data-stu-id="f6742-331">Click the **Font** tab, and in the **Size** list, click **10pt**.</span></span>

13. [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-column-chart"></a><span data-ttu-id="f6742-332">Pour ajouter un histogramme</span><span class="sxs-lookup"><span data-stu-id="f6742-332">To add a column chart</span></span>

1.  <span data-ttu-id="f6742-333">Sous l'onglet **Insertion** du ruban, dans la zone **Visualisations des données** , cliquez sur **Graphique** , puis sur **Assistant Graphique**.</span><span class="sxs-lookup"><span data-stu-id="f6742-333">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="f6742-334">Dans la page **Choisir un dataset** , cliquez sur **ListDataset**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f6742-334">On the **Choose a dataset** page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="f6742-335">Cliquez sur **Colonne**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f6742-335">Click **Column**, and then click **Next**.</span></span>

4.  <span data-ttu-id="f6742-336">Dans la page organiser les champs du graphique, faites glisser le champ produit vers **catégories**.</span><span class="sxs-lookup"><span data-stu-id="f6742-336">On the arrange chart fields page, drag the Product field to **Categories**.</span></span>

5.  <span data-ttu-id="f6742-337">Faites glisser Sales vers **Valeurs** , puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f6742-337">Drag Sales to **Values,** and then click **Next**.</span></span>

     <span data-ttu-id="f6742-338">Les valeurs s'affichent sur l'axe vertical.</span><span class="sxs-lookup"><span data-stu-id="f6742-338">Values display on the vertical axis.</span></span>

6.  <span data-ttu-id="f6742-339">Dans la page **Choisir un style** , dans le volet **Styles** , sélectionnez **Ardoise**.</span><span class="sxs-lookup"><span data-stu-id="f6742-339">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="f6742-340">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f6742-340">Click **Finish**.</span></span>

     <span data-ttu-id="f6742-341">Un histogramme est ajouté dans le coin supérieur gauche du rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-341">A column chart is added to the upper left corner of the report.</span></span>

8.  <span data-ttu-id="f6742-342">Redimensionnez le graphique de sorte qu'il fasse 2 pouces de large sur 2 pouces de haut.</span><span class="sxs-lookup"><span data-stu-id="f6742-342">Resize the chart to be 2 inches wide and 2 inches tall.</span></span>

9. <span data-ttu-id="f6742-343">Faites glisser le graphique à l'intérieur du rectangle, sous le graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="f6742-343">Drag the chart inside the rectangle, below the pie chart.</span></span>

     <span data-ttu-id="f6742-344">![Ajouter un histogramme](../../2014/tutorials/media/tutorial-addcolumnchart.png "Ajouter un histogramme")</span><span class="sxs-lookup"><span data-stu-id="f6742-344">![Add column chart](../../2014/tutorials/media/tutorial-addcolumnchart.png "Add column chart")</span></span>

10. <span data-ttu-id="f6742-345">Cliquez avec le bouton droit sur le titre du graphique, puis cliquez sur **Propriétés du titre**.</span><span class="sxs-lookup"><span data-stu-id="f6742-345">Right-click the chart title and then click **Title Properties**.</span></span>

11. <span data-ttu-id="f6742-346">Dans la boîte de dialogue **Propriétés du titre du graphique** , dans le texte du titre, tapez **Ventes de produits**.</span><span class="sxs-lookup"><span data-stu-id="f6742-346">In the **Chart Title Properties** dialog box, in Title text, type: **Product Sales**.</span></span>

12. <span data-ttu-id="f6742-347">Cliquez sur l'onglet **Police** , puis dans la liste **Taille** , cliquez sur **10pt**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6742-347">Click the **Font** tab, and in the **Size** list click **10pt**, and then click **OK**.</span></span>

13. <span data-ttu-id="f6742-348">Dans l'histogramme, cliquez avec le bouton droit sur l'axe vertical, puis désélectionnez **Afficher le titre de l'axe**.</span><span class="sxs-lookup"><span data-stu-id="f6742-348">In the column chart, right click the vertical axis, and then deselect **Show Axis Title**.</span></span>

14. <span data-ttu-id="f6742-349">Répétez l'étape 13 pour l'axe horizontal.</span><span class="sxs-lookup"><span data-stu-id="f6742-349">Repeat step 13 for the horizontal axis.</span></span>

15. <span data-ttu-id="f6742-350">Cliquez avec le bouton droit sur la légende, puis cliquez sur **Supprimer la légende**.</span><span class="sxs-lookup"><span data-stu-id="f6742-350">Right click the legend, and then click **Delete Legend**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f6742-351">Le fait de supprimer le titre des axes et la légende rend un petit graphique plus lisible.</span><span class="sxs-lookup"><span data-stu-id="f6742-351">Removing axis titles and the legend makes the chart more readable when it is a small size.</span></span>

 <span data-ttu-id="f6742-352">![Changer les titres des graphiques et supprimer le titre de l'axe](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Changer les titres des graphiques et supprimer le titre de l'axe")</span><span class="sxs-lookup"><span data-stu-id="f6742-352">![Change chart titles and remove axis title](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Change chart titles and remove axis title")</span></span>

#### <a name="to-verify-the-charts-are-inside-the-rectangle"></a><span data-ttu-id="f6742-353">Pour vérifier que les graphiques sont à l'intérieur du rectangle</span><span class="sxs-lookup"><span data-stu-id="f6742-353">To verify the charts are inside the rectangle</span></span>

1.  <span data-ttu-id="f6742-354">Cliquez sur le rectangle que vous avez ajouté précédemment dans cette leçon.</span><span class="sxs-lookup"><span data-stu-id="f6742-354">Click the rectangle you added earlier in this lesson.</span></span>

     <span data-ttu-id="f6742-355">Dans le volet Propriétés, la propriété `Name` affiche le nom du rectangle.</span><span class="sxs-lookup"><span data-stu-id="f6742-355">In the Properties pane, the `Name` property displays the name of the rectangle.</span></span>

     <span data-ttu-id="f6742-356">![Nom du rectangle](../../2014/tutorials/media/tutorial-rectanglename.png "Nom du rectangle")</span><span class="sxs-lookup"><span data-stu-id="f6742-356">![Name of rectangle](../../2014/tutorials/media/tutorial-rectanglename.png "Name of rectangle")</span></span>

2.  <span data-ttu-id="f6742-357">Cliquez sur le graphique à secteurs.</span><span class="sxs-lookup"><span data-stu-id="f6742-357">Click the pie chart.</span></span>

3.  <span data-ttu-id="f6742-358">Dans le volet **Propriétés** , vérifiez que la `Parent` propriété contient le nom du rectangle.</span><span class="sxs-lookup"><span data-stu-id="f6742-358">In the **Properties** pane, verify that the `Parent` property contains the name of the rectangle.</span></span>

     <span data-ttu-id="f6742-359">![Propriété parente du graphique en secteurs](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Propriété parente du graphique en secteurs")</span><span class="sxs-lookup"><span data-stu-id="f6742-359">![Parent property for pie chart](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Parent property for pie chart")</span></span>

4.  <span data-ttu-id="f6742-360">Cliquez sur l'histogramme et répétez les étapes 2 et 3.</span><span class="sxs-lookup"><span data-stu-id="f6742-360">Click the column chart and repeat steps 2 and 3.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f6742-361">Si les graphiques ne sont pas à l'intérieur du rectangle, le rapport rendu n'affiche pas les graphiques ensemble.</span><span class="sxs-lookup"><span data-stu-id="f6742-361">If the charts are not inside the rectangle, the rendered report does not display the charts together.</span></span>

#### <a name="to-make-the-charts-the-same-size"></a><span data-ttu-id="f6742-362">Pour donner la même taille aux graphiques</span><span class="sxs-lookup"><span data-stu-id="f6742-362">To make the charts the same size</span></span>

1.  <span data-ttu-id="f6742-363">Cliquez sur le graphique à secteurs, appuyez sur la touche Ctrl, puis cliquez sur l'histogramme.</span><span class="sxs-lookup"><span data-stu-id="f6742-363">Click the pie chart, press the Ctrl key, and then click the column chart.</span></span>

2.  <span data-ttu-id="f6742-364">Les deux graphiques étant sélectionnés, cliquez avec le bouton droit, pointez sur **Disposition**, puis cliquez sur **Uniformiser la largeur**.</span><span class="sxs-lookup"><span data-stu-id="f6742-364">With both charts selected, right-click, point to **Layout**, and then click **Make Same Width**.</span></span>

     <span data-ttu-id="f6742-365">![Uniformiser les largeurs des graphiques](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Uniformiser les largeurs des graphiques")</span><span class="sxs-lookup"><span data-stu-id="f6742-365">![Make chart widths the same](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Make chart widths the same")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f6742-366">L'élément sur lequel vous cliquez en premier détermine la largeur de tous les éléments sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="f6742-366">The item you click first determines the width of all the selected items.</span></span>

3.  <span data-ttu-id="f6742-367">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f6742-367">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="f6742-368">Le rapport affiche maintenant les données de synthèse des ventes dans un graphique à secteurs et un histogramme.</span><span class="sxs-lookup"><span data-stu-id="f6742-368">The report now displays summary sales data in pie and column charts.</span></span>

 <span data-ttu-id="f6742-369">![Didacticiel SSRS, rapport au format libre](../../2014/tutorials/media/tutorial-reportfinal.png "Didacticiel SSRS, rapport au format libre")</span><span class="sxs-lookup"><span data-stu-id="f6742-369">![SSRS tutorial, free form report](../../2014/tutorials/media/tutorial-reportfinal.png "SSRS tutorial, free form report")</span></span>

## <a name="more-information"></a><span data-ttu-id="f6742-370">Informations complémentaires</span><span class="sxs-lookup"><span data-stu-id="f6742-370">More Information</span></span>
 <span data-ttu-id="f6742-371">Pour plus d’informations sur les listes, consultez [tables, matrices et listes &#40;générateur de rapports et ssrs&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [répertorie les &#40;Générateur de rapports et SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), les zones de région de données de tableau [matriciel &#40;générateur de rapports et SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), ainsi que les [cellules, lignes et colonnes de région de données de tableau matriciel &#40;générateur de rapports&#41; et SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f6742-371">For more information about lists, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="f6742-372">Pour plus d’informations sur les concepteurs de requêtes, consultez [Concepteurs de requêtes &#40;Générateur de rapports&#41;](../../2014/reporting-services/query-designers-report-builder.md) et [Interface utilisateur du concepteur de requêtes textuel &#40;Générateur de rapports&#41;](report-data/text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f6742-372">For more information about query designers, see [Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) and [Text-based Query Designer User Interface &#40;Report Builder&#41;](report-data/text-based-query-designer-user-interface-report-builder.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6742-373">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6742-373">See Also</span></span>
 <span data-ttu-id="f6742-374">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) [Générateur de rapports dans SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="f6742-374">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span></span>


