---
title: 'Didacticiel : introduction aux expressions | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d05ef4c-5f91-48b2-8795-f0a201a0b3cc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62a815800dba0730052eb812124d4561d031d0e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706107"
---
# <a name="tutorial-introducing-expressions"></a><span data-ttu-id="7a1c7-102">Didacticiel : introduction aux expressions</span><span class="sxs-lookup"><span data-stu-id="7a1c7-102">Tutorial: Introducing Expressions</span></span>
  <span data-ttu-id="7a1c7-103">Les expressions vous permettent de créer des rapports puissants et flexibles.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-103">Expressions help you create powerful and flexible reports.</span></span> <span data-ttu-id="7a1c7-104">Ce didacticiel vous apprend à créer et implémenter des expressions qui utilisent des fonctions et des opérateurs communs.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-104">This tutorial teaches you to create and implement expressions that use common functions and operators.</span></span> <span data-ttu-id="7a1c7-105">Vous allez utiliser la boîte de dialogue **expression** pour écrire des expressions qui concatènent des valeurs de nom, Rechercher des valeurs dans un DataSet distinct, afficher différentes images en fonction des valeurs de champ, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-105">You will use the **Expression** dialog box to write expressions that concatenate name values, look up values in a separate dataset, display different pictures based on field values, and so on.</span></span>  
  
 <span data-ttu-id="7a1c7-106">Le rapport est un rapport en barres avec des lignes en couleur alternées de lignes blanches.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-106">The report is a barred report with alternating row colors in white and a color.</span></span> <span data-ttu-id="7a1c7-107">Le rapport inclut un paramètre de sélection de couleur pour les lignes non blanches.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-107">The report includes a parameter for selecting the color of the non-white rows.</span></span>  
  
 <span data-ttu-id="7a1c7-108">L'illustration suivante montre un rapport similaire à celui que vous allez créer.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-108">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="7a1c7-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span><span class="sxs-lookup"><span data-stu-id="7a1c7-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="7a1c7-110">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="7a1c7-110">What You Will Learn</span></span>  
 <span data-ttu-id="7a1c7-111">Dans ce didacticiel, vous apprendrez à effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="7a1c7-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="7a1c7-112">Créer un rapport de tableau et un dataset à partir de l'Assistant Tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="7a1c7-112">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="7a1c7-113">Mettre à jour les noms par défaut de la source de données et du dataset</span><span class="sxs-lookup"><span data-stu-id="7a1c7-113">Update Default Names of the Data Source and Dataset</span></span>](#UpdateNames)  
  
3.  [<span data-ttu-id="7a1c7-114">Afficher le prénom, les initiales et le nom</span><span class="sxs-lookup"><span data-stu-id="7a1c7-114">Display First Name, Initial, and Last Name</span></span>](#Concatenate)  
  
4.  [<span data-ttu-id="7a1c7-115">Utiliser des images pour afficher le sexe</span><span class="sxs-lookup"><span data-stu-id="7a1c7-115">Use Images to Display Gender</span></span>](#Gender)  
  
5.  [<span data-ttu-id="7a1c7-116">Rechercher un nom de CountryRegion</span><span class="sxs-lookup"><span data-stu-id="7a1c7-116">Look Up CountryRegion Name</span></span>](#Lookup)  
  
6.  [<span data-ttu-id="7a1c7-117">Compter les jours depuis le dernier achat</span><span class="sxs-lookup"><span data-stu-id="7a1c7-117">Count Days Since Last Purchase</span></span>](#Count)  
  
7.  [<span data-ttu-id="7a1c7-118">Utiliser un indicateur pour afficher la comparaison des ventes</span><span class="sxs-lookup"><span data-stu-id="7a1c7-118">Use an Indicator to Show Sales Comparison</span></span>](#Indicator)  
  
8.  [<span data-ttu-id="7a1c7-119">Transformer le rapport en rapport « barre verte »</span><span class="sxs-lookup"><span data-stu-id="7a1c7-119">Make the Report a "Green Bar" Report</span></span>](#GreenBar)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="7a1c7-120">Autres étapes facultatives</span><span class="sxs-lookup"><span data-stu-id="7a1c7-120">Other Optional Steps</span></span>  
  
-   [<span data-ttu-id="7a1c7-121">Formater la colonne de date</span><span class="sxs-lookup"><span data-stu-id="7a1c7-121">Format Date Column</span></span>](#DateFormat)  
  
-   [<span data-ttu-id="7a1c7-122">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="7a1c7-122">Add a Report Title</span></span>](#Title)  
  
-   [<span data-ttu-id="7a1c7-123">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="7a1c7-123">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="7a1c7-124">Durée estimée pour effectuer ce didacticiel : 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-124">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a1c7-125">Spécifications</span><span class="sxs-lookup"><span data-stu-id="7a1c7-125">Requirements</span></span>  
 <span data-ttu-id="7a1c7-126">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="7a1c7-126">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="7a1c7-127">1. créer un rapport de tableau et un DataSet à partir de l’Assistant tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="7a1c7-127">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="7a1c7-128">Créez un rapport de tableau, une source de données et un dataset.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-128">Create a table report, a data source, and a dataset.</span></span> <span data-ttu-id="7a1c7-129">Lorsque vous créez le tableau, n'incluez que quelques champs.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-129">When you lay out the table, you will include only a few fields.</span></span> <span data-ttu-id="7a1c7-130">Après avoir terminé l'Assistant, vous ajouterez manuellement des colonnes.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-130">After you complete the wizard you will manually add columns.</span></span> <span data-ttu-id="7a1c7-131">L'Assistant vous permet de disposer facilement un tableau et d'appliquer un style.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-131">The wizard makes it easy for you to lay out the table and apply a style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a1c7-132">Dans ce didacticiel, la requête contient les valeurs de données, afin qu'il ne soit pas nécessaire de disposer d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-132">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="7a1c7-133">Cela rend la requête assez longue.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-133">This makes the query quite long.</span></span> <span data-ttu-id="7a1c7-134">Dans un environnement métier, une requête ne contient pas les données.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-134">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="7a1c7-135">Ceci est nécessaire à des fins de formation uniquement.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-135">This is for learning purposes only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a1c7-136">Dans ce didacticiel, les étapes de l'Assistant sont consolidées en une seule procédure.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-136">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="7a1c7-137">Pour obtenir des instructions pas à pas sur l’accès à un serveur de rapports, le choix d’une source de données et la création d’un dataset, consultez le premier didacticiel de cette série : [Didacticiel : création d’un rapport de tableau de base &#40;Générateur de rapports&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7a1c7-137">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
#### <a name="to-create-a-new-table-report"></a><span data-ttu-id="7a1c7-138">Pour créer un nouveau rapport de tableau</span><span class="sxs-lookup"><span data-stu-id="7a1c7-138">To create a new table report</span></span>  
  
1.  <span data-ttu-id="7a1c7-139">Cliquez sur **Démarrer**, pointez sur **programmes**, cliquez sur [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Générateur de rapports**, puis sur **Générateur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-139">Click **Start**, point to **Programs**, click [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="7a1c7-140">La boîte de dialogue **prise en main** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-140">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a1c7-141">Si la boîte de dialogue **prise en main** n’apparaît pas, à partir du bouton **Générateur de rapports** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-141">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a1c7-142">Si vous préférez utiliser la version ClickOnce de Générateur de rapports, ouvrez Gestionnaire de rapports et cliquez sur **Générateur de rapports**, ou accédez à un site SharePoint sur lequel Reporting Services types de contenu tels que les rapports sont activés, puis cliquez sur **Générateur de rapports rapport** dans le menu **nouveau document** sous l’onglet **documents** d’une bibliothèque de documents partagés.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-142">If you prefer using the ClickOnce version of Report Builder, open Report Manager and click **Report Builder**, or go to a SharePoint site on which Reporting Services content types such as reports are enabled and click **Report Builder Report** on the **New Document** menu on the **Documents** tab of a shared documents library.</span></span>  
  
2.  <span data-ttu-id="7a1c7-143">Dans le volet gauche, assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-143">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="7a1c7-144">Dans le volet droit, cliquez sur **Assistant Tableau ou matrice**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-144">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="7a1c7-145">Dans la page **Choisir un dataset** , cliquez sur **Créer un dataset**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-145">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="7a1c7-146">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="7a1c7-147">Dans la page **Choisir une connexion à une source de données** , sélectionnez une source de données de type **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-147">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="7a1c7-148">Sélectionnez une source de données dans la liste ou naviguez jusqu'au serveur de rapports pour en sélectionner une.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-148">Select a data source from the list or browse to the report server to select one.</span></span>  
  
7.  <span data-ttu-id="7a1c7-149">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-149">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="7a1c7-150">Dans la page **Créer une requête** , cliquez sur **Modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-150">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="7a1c7-151">Collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="7a1c7-151">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Lauren' AS FirstName,'Johnson' AS LastName, 'American Samoa' AS StateProvince, 1 AS CountryRegionID,'Unknown' AS Gender, CAST(9996.60 AS money) AS YTDPurchase, CAST('2010-6-10' AS date) AS LastPurchase  
    UNION SELECT'Warren' AS FirstName, 'Pal' AS LastName, 'New South Wales' AS StateProvince, 2 AS CountryRegionID, 'Male' AS Gender, CAST(5747.25 AS money) AS YTDPurchase, CAST('2010-7-3' AS date) AS LastPurchase  
    UNION SELECT 'Fernando' AS FirstName, 'Ross' AS LastName, 'Alberta' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(9248.15 AS money) AS YTDPurchase, CAST('2010-10-17' AS date) AS LastPurchase  
    UNION SELECT 'Rob' AS FirstName, 'Caron' AS LastName, 'Northwest Territories' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(742.50 AS money) AS YTDPurchase, CAST('2010-4-29' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Bailey' AS LastName, 'British Columbia' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(1147.50 AS money) AS YTDPurchase, CAST('2010-6-15' AS date) AS LastPurchase  
    UNION SELECT  'Bridget' AS FirstName, 'She' AS LastName, 'Hamburg' AS StateProvince, 4 AS CountryRegionID, 'Female' AS Gender, CAST(7497.30 AS money) AS YTDPurchase, CAST('2010-5-10' AS date) AS LastPurchase  
    UNION SELECT 'Alexander' AS FirstName, 'Martin' AS LastName, 'Saxony' AS StateProvince, 4 AS CountryRegionID, 'Male' AS Gender, CAST(2997.60 AS money) AS YTDPurchase, CAST('2010-11-19' AS date) AS LastPurchase  
    UNION SELECT 'Yolanda' AS FirstName, 'Sharma' AS LastName ,'Micronesia' AS StateProvince, 5 AS CountryRegionID, 'Female' AS Gender, CAST(3247.95 AS money) AS YTDPurchase, CAST('2010-8-23' AS date) AS LastPurchase  
    UNION SELECT 'Marc' AS FirstName, 'Zimmerman' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1200.00 AS money) AS YTDPurchase, CAST('2010-11-16' AS date) AS LastPurchase  
    UNION SELECT 'Katherine' AS FirstName, 'Abel' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Female' AS Gender, CAST(2025.00 AS money) AS YTDPurchase, CAST('2010-12-1' AS date) AS LastPurchase  
    UNION SELECT 'Nicolas' as FirstName, 'Anand' AS LastName, 'Seine (Paris)' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1425.00 AS money) AS YTDPurchase, CAST('2010-12-11' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Peters' AS LastName, 'England' AS StateProvince, 12 AS CountryRegionID, 'Male' AS Gender, CAST(887.50 AS money) AS YTDPurchase, CAST('2010-8-15' AS date) AS LastPurchase  
    UNION SELECT 'Alison' AS FirstName, 'Nath' AS LastName, 'Alaska' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(607.50 AS money) AS YTDPurchase, CAST('2010-10-13' AS date) AS LastPurchase  
    UNION SELECT 'Grace' AS FirstName, 'Patterson' AS LastName, 'Kansas' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(1215.00 AS money) AS YTDPurchase, CAST('2010-10-18' AS date) AS LastPurchase  
    UNION SELECT 'Bobby' AS FirstName, 'Sanchez' AS LastName, 'North Dakota' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(6191.00 AS money) AS YTDPurchase, CAST('2010-9-17' AS date) AS LastPurchase  
    UNION SELECT 'Charles' AS FirstName, 'Reed' AS LastName, 'Nebraska' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8772.00 AS money) AS YTDPurchase, CAST('2010-8-27' AS date) AS LastPurchase  
    UNION SELECT 'Orlando' AS FirstName, 'Romeo' AS LastName, 'Texas' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8578.00 AS money) AS YTDPurchase, CAST('2010-7-29' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    ```  
  
     <span data-ttu-id="7a1c7-152">La requête spécifie les noms de colonne, notamment la date de naissance, le prénom, le nom, l'État ou la province, l'identifiant de pays/région, le sexe et les achats de l'année en cours jusqu'à ce jour.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-152">The query specifies column names that include a birth date, first name, last name, state or province, country/region identifier, gender, and year-to-date purchases.</span></span>  
  
10. <span data-ttu-id="7a1c7-153">Dans la barre d’outils du concepteur de requêtes, cliquez sur **exécuter** (**!**).</span><span class="sxs-lookup"><span data-stu-id="7a1c7-153">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="7a1c7-154">Le jeu de résultats affiche 20 lignes de données et comprend les colonnes suivantes : FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurcharse et LastPurchase.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-154">The result set displays 20 rows of data and includes the following columns: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase, and LastPurchase.</span></span>  
  
11. <span data-ttu-id="7a1c7-155">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-155">Click **Next**.</span></span>  
  
12. <span data-ttu-id="7a1c7-156">Dans la page **Organiser les champs** , faites glisser les champs suivants, dans l’ordre spécifié, de la liste **Champs disponibles** vers la liste **Valeurs** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-156">On the **Arrange fields** page, drag the following fields, in the specified order, from the **Available Fields** list to the **Values** list.</span></span>  
  
    -   <span data-ttu-id="7a1c7-157">StateProvince</span><span class="sxs-lookup"><span data-stu-id="7a1c7-157">StateProvince</span></span>  
  
    -   <span data-ttu-id="7a1c7-158">CountryRegionID</span><span class="sxs-lookup"><span data-stu-id="7a1c7-158">CountryRegionID</span></span>  
  
    -   <span data-ttu-id="7a1c7-159">LastPurchase</span><span class="sxs-lookup"><span data-stu-id="7a1c7-159">LastPurchase</span></span>  
  
    -   <span data-ttu-id="7a1c7-160">YTDPurchase</span><span class="sxs-lookup"><span data-stu-id="7a1c7-160">YTDPurchase</span></span>  
  
     <span data-ttu-id="7a1c7-161">Les champs CountryRegionID et YTDPurchase contenant des données numériques, l'agrégat SUM est appliqué par défaut.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-161">Because the CountryRegionID and YTDPurchase contain numeric data, the SUM aggregate is applied to them by default.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a1c7-162">Les champs FirstName et LastName ne sont pas inclus.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-162">The FirstName and LastName fields are not included.</span></span> <span data-ttu-id="7a1c7-163">Vous les ajouterez dans une prochaine étape.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-163">You will add them in a later step.</span></span>  
  
13. <span data-ttu-id="7a1c7-164">Dans la liste **valeurs** , cliquez avec le bouton droit `CountryRegionID` et cliquez sur l’option **Sum** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-164">In the **Values** list, right-click `CountryRegionID` and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="7a1c7-165">L'agrégat Sum n'est plus appliqué à CountryRegionID.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-165">Sum is no longer applied to CountryRegionID.</span></span>  
  
14. <span data-ttu-id="7a1c7-166">Dans la liste **Valeurs** , cliquez avec le bouton droit sur **YTDPurchase** et cliquez sur l’option **Sum** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-166">In the **Values** list, right-click **YTDPurchase** and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="7a1c7-167">L'agrégat Sum n'est plus appliqué à YTDPurchase.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-167">Sum is no longer applied to YTDPurchase.</span></span>  
  
15. <span data-ttu-id="7a1c7-168">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-168">Click **Next**.</span></span>  
  
16. <span data-ttu-id="7a1c7-169">Dans la page **Choisir la disposition**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-169">On the **Choose the layout** page, click **Next**.</span></span>  
  
17. <span data-ttu-id="7a1c7-170">Dans la page **choisir un style** , cliquez sur **ardoise**, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-170">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
##  <a name="2-update-default-names-of-the-data-source-and-dataset"></a><a name="UpdateNames"></a><span data-ttu-id="7a1c7-171">2. mettre à jour les noms par défaut de la source de données et du DataSet</span><span class="sxs-lookup"><span data-stu-id="7a1c7-171">2. Update Default Names of the Data Source and Dataset</span></span>  
  
#### <a name="to-update-the-default-name-of-the-data-source"></a><span data-ttu-id="7a1c7-172">Pour mettre à jour le nom par défaut de la source de données</span><span class="sxs-lookup"><span data-stu-id="7a1c7-172">To update the default name of the data source</span></span>  
  
1.  <span data-ttu-id="7a1c7-173">Dans le volet Données du rapport, développez **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-173">In the Report Data pane, expand **Data Sources**.</span></span>  
  
2.  <span data-ttu-id="7a1c7-174">Cliquez avec le bouton droit sur **DataSource1** et cliquez sur **Propriétés de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-174">Right-click **DataSource1** and click **Data Source Properties.**</span></span>  
  
3.  <span data-ttu-id="7a1c7-175">Dans la zone **Nom** , tapez **ExpressionsDataSource**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-175">In the **Name** box, type **ExpressionsDataSource**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-update-the-default-name-of-the-dataset"></a><span data-ttu-id="7a1c7-176">Pour mettre à jour le nom par défaut du dataset</span><span class="sxs-lookup"><span data-stu-id="7a1c7-176">To update the default name of the dataset</span></span>  
  
1.  <span data-ttu-id="7a1c7-177">Dans le volet Données du rapport, développez **Datasets**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-177">In the Report Data pane, expand **Datasets**.</span></span>  
  
2.  <span data-ttu-id="7a1c7-178">Cliquez avec le bouton droit sur le **Dataset1** et cliquez sur **Propriétés du dataset**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-178">Right-click **DataSet1** and click **Dataset Properties.**</span></span>  
  
3.  <span data-ttu-id="7a1c7-179">Dans la zone **Nom** , tapez **Expressions**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-179">In the **Name** box, type **Expressions**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="3-display-first-name-initial-and-last-name"></a><a name="Concatenate"></a><span data-ttu-id="7a1c7-180">3. afficher le prénom, le nom et le prénom</span><span class="sxs-lookup"><span data-stu-id="7a1c7-180">3. Display First Name, Initial, and Last Name</span></span>  
 <span data-ttu-id="7a1c7-181">Utilisez la fonction **Left** et l’opérateur **Concaténer** (**&**) dans une expression dont la valeur est un nom qui comprend une initiale et un nom.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-181">Use the **Left** function and the **Concatenate** (**&**) operator in an expression that evaluates to a name that includes an initial and a last name.</span></span> <span data-ttu-id="7a1c7-182">Vous pouvez générer l’expression pas à pas ou avancer dans la procédure et copier/coller l’expression à partir du didacticiel dans la boîte de dialogue **Expression** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-182">You can build the expression step by step or skip ahead in the procedure and copy/paste the expression from the tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the-name-column"></a><span data-ttu-id="7a1c7-183">Pour ajouter la colonne Name</span><span class="sxs-lookup"><span data-stu-id="7a1c7-183">To add the Name column</span></span>  
  
1.  <span data-ttu-id="7a1c7-184">Cliquez avec le bouton droit sur la colonne **StateProvince** , pointez sur **Insérer une colonne**et cliquez sur **Gauche**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-184">Right-click the **StateProvince** column, point to **Insert Column**, and then click **Left**.</span></span>  
  
     <span data-ttu-id="7a1c7-185">Une nouvelle colonne est ajoutée à gauche de la colonne **StateProvince** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-185">A new column is added to the left of the **StateProvince** column.</span></span>  
  
2.  <span data-ttu-id="7a1c7-186">Cliquez sur le titre de la nouvelle colonne et tapez **Name**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-186">Click the title of the new column and type **Name**</span></span>  
  
3.  <span data-ttu-id="7a1c7-187">Cliquez avec le bouton droit sur la cellule de données pour la colonne **Name** et cliquez sur **Expression**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-187">Right-click the data cell for the **Name** column and click **Expression**.</span></span>  
  
4.  <span data-ttu-id="7a1c7-188">Dans la boîte de dialogue **Expression** , développez **Fonctions communes**, puis cliquez sur **Texte**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-188">In the **Expression** dialog box, expand **Common Functions**, and then click **Text**.</span></span>  
  
5.  <span data-ttu-id="7a1c7-189">Dans la liste **Élément** , double-cliquez sur **Left**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-189">In the **Item** list, double-click **Left**.</span></span>  
  
     <span data-ttu-id="7a1c7-190">La fonction **Left** est ajoutée à l’expression.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-190">The **Left** function is added to the expression.</span></span>  
  
6.  <span data-ttu-id="7a1c7-191">Dans la liste **Catégorie** , cliquez sur **Champs (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-191">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="7a1c7-192">Dans la liste **Valeurs** , double-cliquez sur **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-192">In the **Values** list, double-click **FirstName**.</span></span>  
  
8.  <span data-ttu-id="7a1c7-193">Tapez **, 1)**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-193">Type **, 1)**</span></span>  
  
     <span data-ttu-id="7a1c7-194">Cette expression extrait un caractère de la valeur **FirstName** , en partant de la gauche.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-194">This expression extracts one character from the **FirstName** value, counting from the left.</span></span>  
  
9. <span data-ttu-id="7a1c7-195">Tapez **&" "&**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-195">Type **&" "&**</span></span>  
  
10. <span data-ttu-id="7a1c7-196">Dans la liste **Valeurs** , double-cliquez sur **LastName**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-196">In the **Values** list, double-click **LastName**.</span></span>  
  
     <span data-ttu-id="7a1c7-197">Expression complétée : `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span><span class="sxs-lookup"><span data-stu-id="7a1c7-197">The completed expression: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="7a1c7-198">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-198">Click **Run** to preview the report.</span></span>  
  
##  <a name="4-use-images-to-display-gender"></a><a name="Gender"></a><span data-ttu-id="7a1c7-199">4. utiliser des images pour afficher le sexe</span><span class="sxs-lookup"><span data-stu-id="7a1c7-199">4. Use Images to Display Gender</span></span>  
 <span data-ttu-id="7a1c7-200">Utilisez des images pour afficher le sexe d'une personne et identifiez les valeurs de sexe inconnues à l'aide d'une troisième image.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-200">Use images to show the gender of a person, and identify unknown gender values by using a third image.</span></span> <span data-ttu-id="7a1c7-201">Ajoutez trois images cachées au rapport et une nouvelle colonne pour afficher les images, puis déterminez l'image qui apparaît dans la colonne en fonction de la valeur du champ Sexe.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-201">You will add to the report three hidden images and a new column to display the images, and then determine the image that appears in the column based on the value of the Gender field.</span></span>  
  
 <span data-ttu-id="7a1c7-202">Pour appliquer une couleur à la cellule du tableau qui contient l'image lors de la conversion du rapport en rapport en barres, ajoutez un rectangle puis ajoutez l'image au rectangle.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-202">To apply a color to the table cell that contains the image when you make the report a barred report, you will add a rectangle and then add the image to the rectangle.</span></span> <span data-ttu-id="7a1c7-203">Vous devez utiliser un rectangle car vous pouvez appliquez une couleur d'arrière-plan à un rectangle et non à une image.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-203">You need to use a rectangle because you can apply a background color to a rectangle, but not to an image.</span></span>  
  
 <span data-ttu-id="7a1c7-204">Le didacticiel utilise des images installées avec Windows, mais vous pouvez utiliser l'image que vous voulez.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-204">The tutorial uses images that are installed with Windows, but you can use any images available to you.</span></span> <span data-ttu-id="7a1c7-205">Utilisez des images incorporées, il n'est pas nécessaire de les installer sur votre ordinateur local ou sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-205">You will use embedded images, and they do not need to be installed on your local computer or the report server.</span></span>  
  
#### <a name="to-add-images-to-the-report-body"></a><span data-ttu-id="7a1c7-206">Pour ajouter des images au corps du rapport</span><span class="sxs-lookup"><span data-stu-id="7a1c7-206">To add images to the report body</span></span>  
  
1.  <span data-ttu-id="7a1c7-207">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-207">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="7a1c7-208">Sous l’onglet **Insérer** du ruban, cliquez sur **Image** et cliquez dans le corps du rapport, en dessous du tableau.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-208">On the **Insert** tab of the ribbon, click **Image** and then click in the report body, below the table.</span></span>  
  
     <span data-ttu-id="7a1c7-209">La boîte de dialogue **Propriétés de l’image** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-209">The **Image Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="7a1c7-210">Cliquez sur **Importer** et naviguez vers C:\Users\Public\Public Pictures\Sample Pictures.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-210">Click **Import** and navigate to C:\Users\Public\Public Pictures\Sample Pictures.</span></span>  
  
4.  <span data-ttu-id="7a1c7-211">Cliquez sur Penguins.JPG et cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-211">Click Penguins.JPG and click **Open**.</span></span>  
  
     <span data-ttu-id="7a1c7-212">Dans la boîte de dialogue **Propriétés de l’image**, cliquez sur **Visibilité**, puis sur l’option **Masquer**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-212">In the **Image Properties** dialog box, click **Visibility** and then click the **Hide** option.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="7a1c7-213">Répétez les étapes 2 à 5, mais choisissez Koala.JPG.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-213">Repeat steps 2 through 5, but choose Koala.JPG.</span></span>  
  
7.  <span data-ttu-id="7a1c7-214">Répétez les étapes 2 à 5, mais choisissez Tulips.JPG.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-214">Repeat steps 2 through 5, but choose Tulips.JPG.</span></span>  
  
#### <a name="to-add-the-gender-column"></a><span data-ttu-id="7a1c7-215">Pour ajouter la colonne Gender</span><span class="sxs-lookup"><span data-stu-id="7a1c7-215">To add the Gender column</span></span>  
  
1.  <span data-ttu-id="7a1c7-216">Cliquez avec le bouton droit sur la colonne **Name**, pointez sur **Insérer une colonne** et cliquez sur **Droite**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-216">Right-click the **Name** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="7a1c7-217">Une nouvelle colonne est ajoutée à droite de la colonne **Name**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-217">A new column is added to the right of the **Name** column.</span></span>  
  
2.  <span data-ttu-id="7a1c7-218">Cliquez sur le titre de la nouvelle colonne et tapez **Gender**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-218">Click the title of the new column and type **Gender**</span></span>  
  
#### <a name="to-add-a-rectangle"></a><span data-ttu-id="7a1c7-219">Pour ajouter un rectangle</span><span class="sxs-lookup"><span data-stu-id="7a1c7-219">To add a rectangle</span></span>  
  
-   <span data-ttu-id="7a1c7-220">Sous l’onglet **Insérer** du ruban, cliquez sur **Rectangle** et cliquez sur la cellule de données de la colonne **Gender**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-220">On the **Insert** tab of the ribbon, click **Rectangle** and then click in the data cell of the **Gender** column.</span></span>  
  
     <span data-ttu-id="7a1c7-221">Un rectangle est ajouté à la cellule.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-221">A rectangle is added to the cell.</span></span>  
  
#### <a name="to-add-an-image-to-the-rectangle"></a><span data-ttu-id="7a1c7-222">Pour ajouter une image au rectangle.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-222">To add an image to the rectangle</span></span>  
  
1.  <span data-ttu-id="7a1c7-223">Cliquez avec le bouton droit dans le rectangle, pointez sur **Insérer** puis cliquez sur **Image**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-223">Right-click in the rectangle, point to **Insert**, and then click **Image**.</span></span>  
  
2.  <span data-ttu-id="7a1c7-224">Dans la boîte de dialogue **Propriétés de l’image**, cliquez sur la flèche pointant vers le bas située à côté de **Utiliser cette image** et sélectionnez une des images ajoutées, par exemple Penguins.JPG.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-224">In the **Image Properties** dialog box, click the down arrow beside **Use this image**, and select one of the images you added, for example, Penguins.JPG.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-use-images-to-show-gender"></a><span data-ttu-id="7a1c7-225">Pour utiliser des images pour afficher le sexe</span><span class="sxs-lookup"><span data-stu-id="7a1c7-225">To use images to show gender</span></span>  
  
1.  <span data-ttu-id="7a1c7-226">Cliquez avec le bouton droit sur l’image dans la cellule de données de la colonne **Gender** et cliquez sur **Propriétés de l’image**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-226">Right-click the image in the data cell in the **Gender** column and click **Image Properties**.</span></span>  
  
2.  <span data-ttu-id="7a1c7-227">Dans la boîte de dialogue **Propriétés de l’image**, cliquez sur le bouton d’expression **fx** situé à côté de la zone de texte **Utiliser cette image**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-227">In the **Image Properties** dialog box, click the expression **fx** button next to the **Use this image** text box.</span></span>  
  
3.  <span data-ttu-id="7a1c7-228">Dans la boîte de dialogue **Expression** , développez **Fonctions communes** et cliquez sur **Flux de programme**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-228">In the **Expression** dialog box, expand **Common Functions** and click **Program Flow**.</span></span>  
  
4.  <span data-ttu-id="7a1c7-229">Dans la liste **Élément** , double-cliquez sur **Switch**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-229">In the **Item** list, double-click **Switch**.</span></span>  
  
5.  <span data-ttu-id="7a1c7-230">Dans la liste **Catégorie** , cliquez sur **Champs (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-230">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="7a1c7-231">Dans la liste **Valeurs** , double-cliquez sur **Gender**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-231">In the **Values** list, double-click **Gender**.</span></span>  
  
7.  <span data-ttu-id="7a1c7-232">Tapez **="Male", "Koala",**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-232">Type **="Male", "Koala",**</span></span>  
  
8.  <span data-ttu-id="7a1c7-233">Dans la liste **Valeurs** , double-cliquez sur **Gender**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-233">In the **Values** list, double-click **Gender**.</span></span>  
  
9. <span data-ttu-id="7a1c7-234">Tapez **="Female", "Penguins",**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-234">Type **="Female", "Penguins",**</span></span>  
  
10. <span data-ttu-id="7a1c7-235">Dans la liste **Valeurs** , double-cliquez sur **Gender**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-235">In the **Values** list, double-click **Gender**.</span></span>  
  
11. <span data-ttu-id="7a1c7-236">Tapez **="Unknown", "Tulips")**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-236">Type **="Unknown", "Tulips")**</span></span>  
  
     <span data-ttu-id="7a1c7-237">Expression complétée : `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span><span class="sxs-lookup"><span data-stu-id="7a1c7-237">The completed expression: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="7a1c7-238">Recliquez sur **OK** pour fermer la boîte de dialogue **Propriétés de l’image**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-238">Click **OK** again to close the **Image Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="7a1c7-239">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-239">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-look-up-countryregion-name"></a><a name="Lookup"></a><span data-ttu-id="7a1c7-240">5. Rechercher le nom PaysRégion</span><span class="sxs-lookup"><span data-stu-id="7a1c7-240">5. Look Up CountryRegion Name</span></span>  
 <span data-ttu-id="7a1c7-241">Créez le dataset CountryRegion et utilisez la fonction **Lookup** pour afficher le nom d’un pays/région au lieu de l’identifiant de pays/région.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-241">Create the CountryRegion dataset and use the **Lookup** function to display the name of a country/region instead of the identifier of the country/region.</span></span>  
  
#### <a name="to-create-the-countryregion-dataset"></a><span data-ttu-id="7a1c7-242">Pour créer le dataset CountryRegion</span><span class="sxs-lookup"><span data-stu-id="7a1c7-242">To create the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="7a1c7-243">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="7a1c7-244">Dans le volet données du rapport, cliquez sur **nouveau** , puis sur **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-244">In the Report Data pane, click **New** and then click **Dataset**.</span></span>  
  
3.  <span data-ttu-id="7a1c7-245">Cliquez sur **Utiliser un dataset incorporé dans mon rapport**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-245">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="7a1c7-246">Dans la liste **Source de données** , sélectionnez ExpressionsDataSource.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-246">In the **Data source** list, select ExpressionsDataSource.</span></span>  
  
5.  <span data-ttu-id="7a1c7-247">Dans la zone **Nom** , tapez **CountryRegion**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-247">In the **Name** box, type **CountryRegion**</span></span>  
  
6.  <span data-ttu-id="7a1c7-248">Vérifiez que le type de requête **Texte** est sélectionné et cliquez sur **Concepteur de requêtes**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-248">Verify that the **Text** query type is selected and click **Query Designer**.</span></span>  
  
7.  <span data-ttu-id="7a1c7-249">Cliquez sur **Modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-249">Click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="7a1c7-250">Copiez et collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="7a1c7-250">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 1 AS ID, 'American Samoa' AS CountryRegion  
    UNION SELECT 2 AS CountryRegionID, 'Australia' AS CountryRegion  
    UNION SELECT 3 AS ID, 'Canada' AS CountryRegion  
    UNION SELECT 4 AS ID, 'Germany' AS CountryRegion  
    UNION SELECT 5 AS ID, 'Micronesia' AS CountryRegion  
    UNION SELECT 6 AS ID, 'France' AS CountryRegion  
    UNION SELECT 7 AS ID, 'United States' AS CountryRegion  
    UNION SELECT 8 AS ID, 'Brazil' AS CountryRegion  
    UNION SELECT 9 AS ID, 'Mexico' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Japan' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Australia' AS CountryRegion  
    UNION SELECT 12 AS ID, 'United Kingdom' AS CountryRegion  
    ```  
  
9. <span data-ttu-id="7a1c7-251">Cliquez sur **exécuter** (**!**) pour exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-251">Click **Run** (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="7a1c7-252">Les résultats de la requête sont les identifiants et les noms des pays/régions.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-252">The query results are the country/region identifiers and names.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="7a1c7-253">Recliquez sur **OK** pour fermer la boîte de dialogue **Propriétés du dataset** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-253">Click **OK** again to close the **Dataset Properties** dialog box.</span></span>  
  
#### <a name="to-look-up-values-in-the-countryregion-dataset"></a><span data-ttu-id="7a1c7-254">Pour rechercher des valeurs dans le dataset CountryRegion</span><span class="sxs-lookup"><span data-stu-id="7a1c7-254">To look up values in the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="7a1c7-255">Cliquez sur le titre de la colonne **Country Region ID** et supprimez le texte : ID.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-255">Click the **Country Region ID** column title and delete the text: ID.</span></span>  
  
2.  <span data-ttu-id="7a1c7-256">Cliquez avec le bouton droit sur la cellule de données pour la colonne **Country Region** et cliquez sur **Expression**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-256">Right-click the data cell for the **Country Region** column and click **Expression**.</span></span>  
  
3.  <span data-ttu-id="7a1c7-257">Supprimez l'expression sauf le signe (=) de début.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-257">Delete the expression except the initial equal (=) sign.</span></span>  
  
     <span data-ttu-id="7a1c7-258">L’expression restante est : `=`</span><span class="sxs-lookup"><span data-stu-id="7a1c7-258">The remaining expression is: `=`</span></span>  
  
4.  <span data-ttu-id="7a1c7-259">Dans la boîte de dialogue **Expression**, développez **Fonctions communes** et cliquez sur **Divers**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-259">In the **Expression** dialog box, expand **Common Functions** and click **Miscellaneous**.</span></span>  
  
5.  <span data-ttu-id="7a1c7-260">Dans la liste **Élément**, double-cliquez sur **Lookup**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-260">In the **Item** list, double-click **Lookup**.</span></span>  
  
6.  <span data-ttu-id="7a1c7-261">Dans la liste **Catégorie** , cliquez sur **Champs (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-261">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="7a1c7-262">Dans la liste **valeurs** , double-cliquez sur `CountryRegionID` .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-262">In the **Values** list, double-click `CountryRegionID`.</span></span>  
  
8.  <span data-ttu-id="7a1c7-263">Si le curseur ne se trouve pas déjà immédiatement après `CountryRegionID.Value`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-263">If the cursor is not already immediately after `CountryRegionID.Value`, place it there.</span></span>  
  
9. <span data-ttu-id="7a1c7-264">Supprimez la parenthèse de droite puis tapez **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-264">Delete the right parenthesis and then type **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span></span>  
  
     <span data-ttu-id="7a1c7-265">Expression complétée : `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span><span class="sxs-lookup"><span data-stu-id="7a1c7-265">The completed expression: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span></span>  
  
     <span data-ttu-id="7a1c7-266">La syntaxe de la fonction **Lookup** spécifie une recherche entre CountryRegionID et ID dans le dataset CountryRegion qui retourne la valeur CountryRegion, également dans le dataset CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-266">The syntax of the **Lookup** function specifies a lookup between CountryRegionID and ID in the CountryRegion dataset that returns the CountryRegion value, which is also in the CountryRegion dataset.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="7a1c7-267">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-267">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-count-days-since-last-purchase"></a><a name="Count"></a><span data-ttu-id="7a1c7-268">6. compter les jours depuis le dernier achat</span><span class="sxs-lookup"><span data-stu-id="7a1c7-268">6. Count Days Since Last Purchase</span></span>  
 <span data-ttu-id="7a1c7-269">Ajoutez une colonne, puis utilisez la fonction **Now** ou la `ExecutionTime` variable globale intégrée pour calculer le nombre de jours à partir d’aujourd’hui depuis les derniers achats d’une personne.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-269">Add a column and then use the **Now** function or the `ExecutionTime` built-in global variable to calculate the number of days from today since a person's last purchases.</span></span>  
  
#### <a name="to-add-the-days-ago-column"></a><span data-ttu-id="7a1c7-270">Pour ajouter la colonne Days Ago</span><span class="sxs-lookup"><span data-stu-id="7a1c7-270">To add the Days Ago column</span></span>  
  
1.  <span data-ttu-id="7a1c7-271">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-271">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="7a1c7-272">Cliquez avec le bouton droit sur la colonne **Last Purchase** , pointez sur **Insérer une colonne**et cliquez sur **Droite**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-272">Right-click the **Last Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="7a1c7-273">Une nouvelle colonne est ajoutée à droite de la colonne **Last Purchase** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-273">A new column is added to the right of the **Last Purchase** column.</span></span>  
  
3.  <span data-ttu-id="7a1c7-274">Dans l’en-tête de colonne, tapez **Days Ago**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-274">In the column header, type **Days Ago**</span></span>  
  
4.  <span data-ttu-id="7a1c7-275">Cliquez avec le bouton droit sur la cellule de données pour la colonne **Days Ago** et cliquez sur **Expression**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-275">Right-click the data cell for the **Days Ago** column and click **Expression**.</span></span>  
  
5.  <span data-ttu-id="7a1c7-276">Dans la boîte de dialogue **Expression**, développez **Fonctions communes**, puis cliquez sur **Date & heure**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-276">In the **Expression** dialog box, expand **Common Functions**, and then click **Date & Time**.</span></span>  
  
6.  <span data-ttu-id="7a1c7-277">Dans la liste **Élément** , double-cliquez sur **DateDiff**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-277">In the **Item** list, double-click **DateDiff**.</span></span>  
  
7.  <span data-ttu-id="7a1c7-278">Si le curseur ne se trouve pas déjà immédiatement après `DateDiff(`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-278">If the cursor is not already immediately after `DateDiff(`, place it there.</span></span>  
  
8.  <span data-ttu-id="7a1c7-279">Tapez **"d",**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-279">Type **"d",**</span></span>  
  
9. <span data-ttu-id="7a1c7-280">Dans la liste **Catégorie** , cliquez sur **Champs (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-280">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
10. <span data-ttu-id="7a1c7-281">Dans la liste **Valeurs**, double-cliquez sur **LastPurchase**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-281">In the **Values** list, double-click **LastPurchase**.</span></span>  
  
11. <span data-ttu-id="7a1c7-282">Si le curseur ne se trouve pas déjà immédiatement après `Fields!LastPurchase.Value`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-282">If the cursor is not already immediately after `Fields!LastPurchase.Value`, place it there.</span></span>  
  
12. <span data-ttu-id="7a1c7-283">Tapez **,**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-283">Type **,**</span></span>  
  
13. <span data-ttu-id="7a1c7-284">Dans la liste **Catégorie**, recliquez sur **Date & heure**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-284">In the **Category** list, click **Date & Time** again.</span></span>  
  
14. <span data-ttu-id="7a1c7-285">Dans la liste **Élément**, double-cliquez sur **Now**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-285">In the **Item** list, double-click **Now**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="7a1c7-286">Dans les rapports de production, vous ne devez pas utiliser la fonction **Now** dans les expressions évaluées plusieurs fois pendant la génération du rapport (par exemple, dans les lignes de détails d’un rapport).</span><span class="sxs-lookup"><span data-stu-id="7a1c7-286">In production reports you should not use the **Now** function in expressions that are evaluated multiple times as the report renders (for example, in the detail rows of a report).</span></span> <span data-ttu-id="7a1c7-287">La valeur de **Now** change de ligne en ligne et les différentes valeurs affectent les résultats de l’évaluation des expressions, ce qui entraîne des résultats légèrement incohérents.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-287">The value of **Now** changes from row to row and the different values affect the evaluation results of expressions, which leads to results that are subtly inconsistent.</span></span> <span data-ttu-id="7a1c7-288">Vous devez utiliser à la place la variable globale `ExecutionTime` fournie par [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a1c7-288">Instead, you should use the `ExecutionTime` global variable that [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides.</span></span>  
  
15. <span data-ttu-id="7a1c7-289">Si le curseur ne se trouve pas déjà immédiatement après `Now(`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-289">If the cursor is not already immediately after `Now(`, place it there.</span></span>  
  
16. <span data-ttu-id="7a1c7-290">Supprimez la parenthèse de gauche puis tapez **)**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-290">Delete the left parenthesis and then type **)**</span></span>  
  
     <span data-ttu-id="7a1c7-291">Expression complétée : `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span><span class="sxs-lookup"><span data-stu-id="7a1c7-291">The completed expression: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span></span>  
  
17. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="7-use-an-indicator-to-show-sales-comparison"></a><a name="Indicator"></a><span data-ttu-id="7a1c7-292">7. utiliser un indicateur pour afficher la comparaison des ventes</span><span class="sxs-lookup"><span data-stu-id="7a1c7-292">7. Use an Indicator to Show Sales Comparison</span></span>  
 <span data-ttu-id="7a1c7-293">Ajoutez une nouvelle colonne et utilisez un indicateur pour indiquer si les achats de l’année en cours (CÀJ) d’une personne sont au-dessus ou en dessous de la moyenne des achats AAJ.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-293">Add a new column and use an indicator to show whether a person's year-to-date (YTD) purchases are above or below the average YTD purchases.</span></span> <span data-ttu-id="7a1c7-294">La fonction **Round** supprime les décimales des valeurs.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-294">The **Round** function removes decimals from values.</span></span>  
  
 <span data-ttu-id="7a1c7-295">La configuration de l'indicateur et de ses états nécessite plusieurs étapes.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-295">The configuration of the indicator and its states requires many steps.</span></span> <span data-ttu-id="7a1c7-296">Si vous le souhaitez, dans la procédure « pour configurer l’indicateur », vous pouvez ignorer et copier/coller les expressions terminées à partir de ce didacticiel dans la boîte de dialogue **expression** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-296">If you want to, in the "To configure the indicator" procedure, you can skip ahead and copy/paste the completed expressions from this tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the--or---avg-sales-column"></a><span data-ttu-id="7a1c7-297">Pour ajouter la colonne + or - AVG Sales</span><span class="sxs-lookup"><span data-stu-id="7a1c7-297">To add the + or - AVG Sales column</span></span>  
  
1.  <span data-ttu-id="7a1c7-298">Cliquez avec le bouton droit sur la colonne **YTD Purchase** , pointez sur **Insérer une colonne**et cliquez sur **Droite**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-298">Right-click the **YTD Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="7a1c7-299">Une nouvelle colonne est ajoutée à droite de la colonne **YTD Purchase** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-299">A new column is added to the right of the **YTD Purchase** column.</span></span>  
  
2.  <span data-ttu-id="7a1c7-300">Cliquez sur le titre de la nouvelle colonne et tapez **+ or - AVG Sales**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-300">Click the title of the column and type **+ or - AVG Sales**</span></span>  
  
#### <a name="to-add-an-indicator"></a><span data-ttu-id="7a1c7-301">Pour ajouter un indicateur</span><span class="sxs-lookup"><span data-stu-id="7a1c7-301">To add an indicator</span></span>  
  
1.  <span data-ttu-id="7a1c7-302">Sous l’onglet **Insérer** du ruban, cliquez sur **Indicateur** et cliquez sur la cellule de données de la colonne **+ or - AVG Sales**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-302">On the **Insert** tab of the ribbon, click **Indicator**, and then click the data cell for the **+ or - AVG Sales** column.</span></span>  
  
     <span data-ttu-id="7a1c7-303">La boîte de dialogue **Sélectionner un type d’indicateur** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-303">The **Select Indicator Type** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="7a1c7-304">Dans le groupe **Directionnel** des jeux d’icônes, cliquez sur le jeu des trois flèches grises.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-304">In the **Directional** group of icon sets, click the set of three gray arrows.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-configure-the-indicator"></a><span data-ttu-id="7a1c7-305">Pour configurer l'indicateur</span><span class="sxs-lookup"><span data-stu-id="7a1c7-305">To configure the indicator</span></span>  
  
1.  <span data-ttu-id="7a1c7-306">Cliquez avec le bouton droit sur l’indicateur, cliquez sur **Propriétés de l’indicateur**, puis sur **Valeur et états**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-306">Right-click the indicator, click **Indicator Properties**, and then click **Value and States**.</span></span>  
  
2.  <span data-ttu-id="7a1c7-307">Cliquez sur le bouton d’expression **fx** situé à côté de la zone de texte **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-307">Click the expression **fx** button next to the **Value** text box.</span></span>  
  
3.  <span data-ttu-id="7a1c7-308">Dans la boîte de dialogue **Expression** , développez **Fonctions communes**, puis cliquez sur **Math**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-308">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
4.  <span data-ttu-id="7a1c7-309">Dans la liste **Élément** , double-cliquez sur **Round**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-309">In the **Item** list, double-click **Round**.</span></span>  
  
5.  <span data-ttu-id="7a1c7-310">Dans la liste **Catégorie** , cliquez sur **Champs (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-310">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="7a1c7-311">Dans la liste **Valeurs**, double-cliquez sur **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-311">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
7.  <span data-ttu-id="7a1c7-312">Si le curseur ne se trouve pas déjà immédiatement après `Fields!YTDPurchase.Value`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-312">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
8.  <span data-ttu-id="7a1c7-313">Entrer**-**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-313">Type  **-**</span></span>  
  
9. <span data-ttu-id="7a1c7-314">Redéveloppez **Fonctions communes** et cliquez sur **Agrégation**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-314">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
10. <span data-ttu-id="7a1c7-315">Dans la liste **Élément**, double-cliquez sur **Avg**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-315">In the **Item** list, double-click **Avg**.</span></span>  
  
11. <span data-ttu-id="7a1c7-316">Dans la liste **Catégorie** , cliquez sur **Champs (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-316">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
12. <span data-ttu-id="7a1c7-317">Dans la liste **Valeurs**, double-cliquez sur **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-317">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
13. <span data-ttu-id="7a1c7-318">Si le curseur ne se trouve pas déjà immédiatement après `Fields!YTDPurchase.Value`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-318">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
14. <span data-ttu-id="7a1c7-319">Tapez **, "Expressions"))**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-319">Type **, "Expressions"))**</span></span>  
  
     <span data-ttu-id="7a1c7-320">Expression complétée : `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span><span class="sxs-lookup"><span data-stu-id="7a1c7-320">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span></span>  
  
15. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
16. <span data-ttu-id="7a1c7-321">Dans la zone **Unité de mesure des états** , sélectionnez **Numérique**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-321">In the **States Measurement Unit** box, select **Numeric**.</span></span>  
  
17. <span data-ttu-id="7a1c7-322">Dans la ligne contenant la flèche pointant vers le bas, cliquez sur le bouton **fx** situé à droite de la zone de texte pour la valeur **Démarrer** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-322">In the row with the down-pointing arrow, click the **fx** button to the right of the text box for the **Start** value.</span></span>  
  
18. <span data-ttu-id="7a1c7-323">Dans la boîte de dialogue **Expression** , développez **Fonctions communes**, puis cliquez sur **Math**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-323">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
19. <span data-ttu-id="7a1c7-324">Dans la liste **Élément** , double-cliquez sur **Round**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-324">In the **Item** list, double-click **Round**.</span></span>  
  
20. <span data-ttu-id="7a1c7-325">Dans la liste **Catégorie** , cliquez sur **Champs (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-325">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
21. <span data-ttu-id="7a1c7-326">Dans la liste **Valeurs**, double-cliquez sur **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-326">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
22. <span data-ttu-id="7a1c7-327">Si le curseur ne se trouve pas déjà immédiatement après `Fields!YTDPurchase.Value`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-327">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="7a1c7-328">Entrer**-**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-328">Type  **-**</span></span>  
  
24. <span data-ttu-id="7a1c7-329">Redéveloppez **Fonctions communes** et cliquez sur **Agrégation**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-329">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
25. <span data-ttu-id="7a1c7-330">Dans la liste **Élément**, double-cliquez sur **Avg**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-330">In the **Item** list, double-click **Avg**.</span></span>  
  
26. <span data-ttu-id="7a1c7-331">Dans la liste **Catégorie** , cliquez sur **Champs (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-331">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
27. <span data-ttu-id="7a1c7-332">Dans la liste **Valeurs**, double-cliquez sur **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-332">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
28. <span data-ttu-id="7a1c7-333">Si le curseur ne se trouve pas déjà immédiatement après `Fields!YTDPurchase.Value`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-333">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
29. <span data-ttu-id="7a1c7-334">Tapez **, "Expressions")) < 0**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-334">Type **, "Expressions")) < 0**</span></span>  
  
     <span data-ttu-id="7a1c7-335">Expression complétée : `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span><span class="sxs-lookup"><span data-stu-id="7a1c7-335">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span></span>  
  
30. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
31. <span data-ttu-id="7a1c7-336">Dans la zone de texte de la valeur **Fin** , tapez **0**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-336">In the text box for the **End** value, type **0**</span></span>  
  
32. <span data-ttu-id="7a1c7-337">Cliquez sur la ligne contenant la flèche pointant à l’horizontale et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-337">Click the row with the horizontal-pointing arrow and click **Delete**.</span></span>  
  
33. <span data-ttu-id="7a1c7-338">Dans la ligne contenant la flèche pointant vers le haut, dans la zone **Démarrer** , tapez **0**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-338">In the row with the up-pointing arrow, in the **Start** box, type **0**</span></span>  
  
34. <span data-ttu-id="7a1c7-339">Cliquez sur le bouton **fx** situé à droite de la zone de texte pour la valeur **Fin** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-339">Click the **fx** button to the right of the text box for the **End** value.</span></span>  
  
35. <span data-ttu-id="7a1c7-340">Dans la boîte de dialogue **expression** , créez l’expression :`=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span><span class="sxs-lookup"><span data-stu-id="7a1c7-340">In the **Expression** dialog box, create the expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span></span>  
  
36. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
37. <span data-ttu-id="7a1c7-341">Cliquez sur **OK** à nouveau pour fermer la boîte de dialogue **Propriétés de l’indicateur** .</span><span class="sxs-lookup"><span data-stu-id="7a1c7-341">Click **OK** again to close the **Indicator properties** dialog box.</span></span>  
  
38. <span data-ttu-id="7a1c7-342">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-342">Click **Run** to preview the report.</span></span>  
  
##  <a name="8-make-the-report-a-green-bar-report"></a><a name="GreenBar"></a><span data-ttu-id="7a1c7-343">8. transformer le rapport en rapport « barre verte »</span><span class="sxs-lookup"><span data-stu-id="7a1c7-343">8. Make the Report a "Green Bar" Report</span></span>  
 <span data-ttu-id="7a1c7-344">Utilisez un paramètre pour spécifier la couleur à appliquer aux lignes alternées dans le rapport, pour en faire un rapport en barres.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-344">Use a parameter to specify the color to apply to alternating rows in the report, making it a barred report.</span></span>  
  
#### <a name="to-add-a-parameter"></a><span data-ttu-id="7a1c7-345">Pour ajouter un paramètre</span><span class="sxs-lookup"><span data-stu-id="7a1c7-345">To add a parameter</span></span>  
  
1.  <span data-ttu-id="7a1c7-346">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-346">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="7a1c7-347">Dans le volet **Données du rapport** , cliquez avec le bouton droit sur **Paramètres** et cliquez sur **Ajouter un paramètre**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-347">In the **Report Data** pane, right-click **Parameters** and click **Add Parameter**.</span></span>  
  
     <span data-ttu-id="7a1c7-348">La boîte de dialogue **Propriétés du paramètre de rapport** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-348">The **Report Parameter Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="7a1c7-349">Dans **Invite**, tapez **Choisir une couleur**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-349">In **Prompt**, type **Choose color**</span></span>  
  
4.  <span data-ttu-id="7a1c7-350">Dans la zone **Nom**, tapez **RowColor**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-350">In **Name**, type **RowColor**</span></span>  
  
5.  <span data-ttu-id="7a1c7-351">Dans le volet gauche, cliquez sur **Valeurs disponibles**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-351">In the left pane, click **Available Values**.</span></span>  
  
6.  <span data-ttu-id="7a1c7-352">Cliquez sur **Spécifier les valeurs**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-352">Click **Specify values**.</span></span>  
  
7.  <span data-ttu-id="7a1c7-353">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-353">Click **Add**.</span></span>  
  
8.  <span data-ttu-id="7a1c7-354">Dans la zone **étiquette** , tapez : **jaune**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-354">In the **Label** box, type: **Yellow**</span></span>  
  
9. <span data-ttu-id="7a1c7-355">Dans la zone **Valeur** , tapez **Yellow**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-355">In the **Value** box, type **Yellow**</span></span>  
  
10. <span data-ttu-id="7a1c7-356">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-356">Click **Add**.</span></span>  
  
11. <span data-ttu-id="7a1c7-357">Dans la zone **Étiquette** , tapez **Green**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-357">In the **Label** box, type **Green**</span></span>  
  
12. <span data-ttu-id="7a1c7-358">Dans la zone **Valeur** , tapez **PaleGreen**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-358">In the **Value** box, type **PaleGreen**</span></span>  
  
13. <span data-ttu-id="7a1c7-359">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-359">Click **Add**.</span></span>  
  
14. <span data-ttu-id="7a1c7-360">Dans la zone **Étiquette** , tapez **Blue**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-360">In the **Label** box, type **Blue**</span></span>  
  
15. <span data-ttu-id="7a1c7-361">Dans la zone **Valeur** , tapez **LightBlue**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-361">In the **Value** box, type **LightBlue**</span></span>  
  
16. <span data-ttu-id="7a1c7-362">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-362">Click **Add**.</span></span>  
  
17. <span data-ttu-id="7a1c7-363">Dans la zone **Étiquette** , tapez **Pink**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-363">In the **Label** box, type **Pink**</span></span>  
  
18. <span data-ttu-id="7a1c7-364">Dans la zone **Valeur** , tapez **Pink**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-364">In the **Value** box, type **Pink**</span></span>  
  
19. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-apply-alternating-colors-to-detail-rows"></a><span data-ttu-id="7a1c7-365">Pour appliquer des couleurs alternées aux lignes de détails</span><span class="sxs-lookup"><span data-stu-id="7a1c7-365">To apply alternating colors to detail rows</span></span>  
  
1.  <span data-ttu-id="7a1c7-366">Cliquez sur l’onglet **Affichage** du ruban et vérifiez que **Propriétés** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-366">Click the **View** tab on the ribbon and verify that **Properties** is selected.</span></span>  
  
2.  <span data-ttu-id="7a1c7-367">Cliquez sur la cellule de données pour la colonne **Name** et enfoncez la touche Maj.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-367">Click the data cell for the **Name** column and press the Shift key.</span></span>  
  
3.  <span data-ttu-id="7a1c7-368">Une par une, cliquez sur les autres cellules de la ligne.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-368">One by one, click the other cells in the row.</span></span>  
  
4.  <span data-ttu-id="7a1c7-369">Dans le volet Propriétés, cliquez sur **BackgroundColor**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-369">In the Properties pane, click **BackgroundColor**.</span></span>  
  
     <span data-ttu-id="7a1c7-370">Si votre volet de propriétés répertorie les propriétés par catégorie, vous trouverez **BackgroundColor** sous la catégorie **Remplir**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-370">If your Properties pane lists properties by category, you will find the **BackgroundColor** under the **Fill** category.</span></span>  
  
5.  <span data-ttu-id="7a1c7-371">Cliquez sur la flèche pointant vers le bas, puis sur **Expression**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-371">Click the down arrow and then click **Expression**.</span></span>  
  
6.  <span data-ttu-id="7a1c7-372">Dans la boîte de dialogue **Expression** , développez **Fonctions communes**puis cliquez sur **Flux de programme**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-372">In the **Expression** dialog box, expand **Common Functions**, and then click **Program Flow**.</span></span>  
  
7.  <span data-ttu-id="7a1c7-373">Dans la liste **Élément** , double-cliquez sur **IIf**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-373">In the **Item** list, double-click **IIf**.</span></span>  
  
8.  <span data-ttu-id="7a1c7-374">Développez **Fonctions communes** et cliquez sur **Agrégation**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-374">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
9. <span data-ttu-id="7a1c7-375">Dans la liste **Élément**, double-cliquez sur **RunningValue**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-375">In the **Item** list, double-click **RunningValue**.</span></span>  
  
10. <span data-ttu-id="7a1c7-376">Dans la liste **Catégorie** , cliquez sur **Champs (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-376">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
11. <span data-ttu-id="7a1c7-377">Dans la liste **Valeurs** , double-cliquez sur **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-377">In the **Values** list, double-click **FirstName**.</span></span>  
  
12. <span data-ttu-id="7a1c7-378">Si le curseur ne se trouve pas déjà immédiatement après `Fields!FirstName.Value`, placez-le à cet endroit et tapez **,**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-378">If the cursor is not already immediately after `Fields!FirstName.Value`, place it there and type **,**</span></span>  
  
13. <span data-ttu-id="7a1c7-379">Développez **Fonctions communes** et cliquez sur **Agrégation**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-379">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
14. <span data-ttu-id="7a1c7-380">Dans la liste **Élément**, double-cliquez sur **Count**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-380">In the **Item** list, double-click **Count**.</span></span>  
  
15. <span data-ttu-id="7a1c7-381">Si le curseur ne se trouve pas déjà immédiatement après `Count(`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-381">If the cursor is not already immediately after `Count(`, place it there.</span></span>  
  
16. <span data-ttu-id="7a1c7-382">Supprimez la parenthèse de gauche, puis tapez **, "expressions")**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-382">Delete the left parenthesis and then type **,"Expressions")**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7a1c7-383">Expressions est le nom du dataset dans lequel sont comptées les lignes de données.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-383">Expressions is the name of the dataset in which to count data rows.</span></span>  
  
17. <span data-ttu-id="7a1c7-384">Développez **Opérateurs** et cliquez sur **Arithmétique**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-384">Expand **Operators** and click **Arithmetic**.</span></span>  
  
18. <span data-ttu-id="7a1c7-385">Dans la liste **Élément**, double-cliquez sur **Mod**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-385">In the **Item** list, double-click **Mod**.</span></span>  
  
19. <span data-ttu-id="7a1c7-386">Si le curseur ne se trouve pas déjà immédiatement après `Mod`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-386">If the cursor is not already immediately after `Mod`, place it there.</span></span>  
  
20. <span data-ttu-id="7a1c7-387">Tapez **2 =0,**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-387">Type  **2 =0,**</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="7a1c7-388">Veillez à inclure un espace avant de taper le chiffre 2.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-388">Be sure you include a space before you type the number 2.</span></span>  
  
21. <span data-ttu-id="7a1c7-389">Cliquez sur **Paramètres** et dans la liste **Valeurs** , double-cliquez sur **RowColor**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-389">Click **Parameters** and in the **Values** list, double-click **RowColor**.</span></span>  
  
22. <span data-ttu-id="7a1c7-390">Si le curseur ne se trouve pas déjà immédiatement après `Parameters!RowColor.Value`, placez-le à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-390">If the cursor is not already immediately after `Parameters!RowColor.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="7a1c7-391">Type **, "White")**</span><span class="sxs-lookup"><span data-stu-id="7a1c7-391">Type **, "White")**</span></span>  
  
     <span data-ttu-id="7a1c7-392">Expression complétée : `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span><span class="sxs-lookup"><span data-stu-id="7a1c7-392">The completed expression: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span></span>  
  
24. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="run-the-report"></a><span data-ttu-id="7a1c7-393">Exécuter le rapport</span><span class="sxs-lookup"><span data-stu-id="7a1c7-393">Run the Report</span></span>  
  
1.  <span data-ttu-id="7a1c7-394">Si vous ne vous trouvez pas sous l’onglet **Accueil**, cliquez sur **Accueil** pour retourner au mode Conception.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-394">If not on the **Home** tab, click **Home** to return to design view.</span></span>  
  
2.  <span data-ttu-id="7a1c7-395">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-395">Click **Run**.</span></span>  
  
3.  <span data-ttu-id="7a1c7-396">Dans la liste déroulante **Choisir une couleur**, sélectionnez la couleur des barres non blanches du rapport.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-396">In the **Choose color** drop-down list, select the color of the non-white bars on the report.</span></span>  
  
4.  <span data-ttu-id="7a1c7-397">Cliquez sur **Afficher le rapport**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-397">Click **View Report**.</span></span>  
  
     <span data-ttu-id="7a1c7-398">Le rapport est généré et les lignes alternées sont de la couleur d'arrière-plan que vous avez choisie.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-398">The report renders and alternating rows have the background that you chose.</span></span>  
  
##  <a name="optional-format-date-column"></a><a name="DateFormat"></a><span data-ttu-id="7a1c7-399">facultatif Formater la colonne de date</span><span class="sxs-lookup"><span data-stu-id="7a1c7-399">(optional) Format Date Column</span></span>  
 <span data-ttu-id="7a1c7-400">Formatez la colonne **Last Purchase** qui contient des dates.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-400">Format the **Last Purchase** column, which contains dates.</span></span>  
  
#### <a name="to-format-date-column"></a><span data-ttu-id="7a1c7-401">Pour formater la colonne de dates</span><span class="sxs-lookup"><span data-stu-id="7a1c7-401">To format date column</span></span>  
  
1.  <span data-ttu-id="7a1c7-402">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-402">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="7a1c7-403">Cliquez avec le bouton droit sur la cellule de données pour la colonne **Last Purchase** et cliquez sur **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-403">Right-click the data cell for the **Last Purchase** column and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="7a1c7-404">Dans la boîte de dialogue **Propriétés de la zone de texte**, cliquez sur **Nombre**, cliquez sur **Date**, puis sur le type **\*1/31/2000**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-404">In the **Text Box Properties** dialog box, click **Number**, click **Date**, and then click the type **\*1/31/2000**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="7a1c7-405">facultatif Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="7a1c7-405">(optional) Add a Report Title</span></span>  
 <span data-ttu-id="7a1c7-406">Ajoutez un titre au rapport.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-406">Add a title to the report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="7a1c7-407">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="7a1c7-407">To add a report title</span></span>  
  
1.  <span data-ttu-id="7a1c7-408">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-408">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="7a1c7-409">Tapez **Synthèse de la comparaison des ventes**, puis cliquez à l’extérieur de la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-409">Type **Sales Comparison Summary**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="7a1c7-410">Cliquez avec le bouton droit sur la zone de texte qui contient **Synthèse de la comparaison des ventes**, puis cliquez sur **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-410">Right-click the text box that contains **Sales Comparison Summary** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="7a1c7-411">Dans la boîte de dialogue **Propriétés de la zone de texte** , cliquez sur **Police**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-411">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="7a1c7-412">Dans la liste **Taille** , sélectionnez **18pt**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-412">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="7a1c7-413">Dans la liste **Couleur**, sélectionnez **Gris**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-413">In the **Color** list, select **Gray**.</span></span>  
  
7.  <span data-ttu-id="7a1c7-414">Sélectionnez **Gras** et **Italique**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-414">Select  **Bold** and  **Italic**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-save-the-report"></a><a name="Save"></a><span data-ttu-id="7a1c7-415">facultatif Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="7a1c7-415">(optional) Save the Report</span></span>  
 <span data-ttu-id="7a1c7-416">Vous pouvez enregistrer les rapports sur un serveur de rapports, dans une bibliothèque SharePoint ou sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-416">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="7a1c7-417">Pour plus d’informations, consultez [Enregistrement des rapports &#40;Générateur de rapports&#41;](report-builder/saving-reports-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7a1c7-417">For more information, see [Saving Reports &#40;Report Builder&#41;](report-builder/saving-reports-report-builder.md).</span></span>  
  
 <span data-ttu-id="7a1c7-418">Dans ce didacticiel, enregistrez le rapport sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-418">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="7a1c7-419">Si vous n'avez pas accès à un serveur de rapports, enregistrez le rapport sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-419">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-to-a-report-server"></a><span data-ttu-id="7a1c7-420">Pour enregistrer le rapport sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="7a1c7-420">To save the report to a report server</span></span>  
  
1.  <span data-ttu-id="7a1c7-421">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-421">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="7a1c7-422">Cliquez sur **Sites et serveurs récents**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-422">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="7a1c7-423">Sélectionnez ou tapez le nom du serveur de rapports sur lequel vous êtes autorisé à enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-423">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="7a1c7-424">Le message « Connexion au serveur de rapports » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-424">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="7a1c7-425">Une fois la connexion établie, le contenu du dossier de rapports spécifié par l’administrateur du serveur de rapports s’affiche comme emplacement par défaut des rapports.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-425">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="7a1c7-426">Dans **Nom**, remplacez le nom par défaut par **Synthèse de la comparaison des ventes**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-426">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
5.  <span data-ttu-id="7a1c7-427">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-427">Click **Save**.</span></span>  
  
 <span data-ttu-id="7a1c7-428">Le rapport est enregistré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-428">The report is saved to the report server.</span></span> <span data-ttu-id="7a1c7-429">Le nom du serveur de rapports auquel vous êtes connecté est indiqué dans la barre d'état située au bas de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-429">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-to-your-computer"></a><span data-ttu-id="7a1c7-430">Pour enregistrer le rapport sur votre ordinateur</span><span class="sxs-lookup"><span data-stu-id="7a1c7-430">To save the report to your computer</span></span>  
  
1.  <span data-ttu-id="7a1c7-431">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-431">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="7a1c7-432">Cliquez sur **Bureau**, **Mes documents**ou **Poste de travail**, puis naviguez jusqu'au dossier où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-432">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="7a1c7-433">Dans **Nom**, remplacez le nom par défaut par **Synthèse de la comparaison des ventes**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-433">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
4.  <span data-ttu-id="7a1c7-434">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7a1c7-434">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a1c7-435">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a1c7-435">See Also</span></span>  
 <span data-ttu-id="7a1c7-436">[Expressions &#40;Générateur de rapports et SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7a1c7-436">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7a1c7-437">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7a1c7-437">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7a1c7-438">[Indicateurs &#40;Générateur de rapports et SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7a1c7-438">[Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7a1c7-439">[Images, zones de texte, rectangles et lignes &#40;Générateur de rapports et SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7a1c7-439">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7a1c7-440">[Tables &#40;Générateur de rapports et SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7a1c7-440">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7a1c7-441">Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7a1c7-441">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
