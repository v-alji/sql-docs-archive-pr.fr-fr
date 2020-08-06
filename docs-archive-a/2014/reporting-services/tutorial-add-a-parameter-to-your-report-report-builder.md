---
title: 'Didacticiel : ajouter un paramètre à votre rapport (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eab34ec4-b3ad-4a76-95cc-07b2f75ee6d7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dff41066a2d505ab53b17a10fb3da9b6cb17130f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704784"
---
# <a name="tutorial-add-a-parameter-to-your-report-report-builder"></a><span data-ttu-id="d58b0-102">Didacticiel : ajouter un paramètre à un rapport (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="d58b0-102">Tutorial: Add a Parameter to Your Report (Report Builder)</span></span>
  <span data-ttu-id="d58b0-103">Ajoutez un paramètre à votre rapport pour permettre aux utilisateurs de filtrer les données de rapport à partir de la source de données ou dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-103">Add a parameter to your report to let users filter report data from the data source or in the report.</span></span> <span data-ttu-id="d58b0-104">Les paramètres de rapport sont créés automatiquement pour chaque paramètre de requête que vous incluez dans une requête de dataset.</span><span class="sxs-lookup"><span data-stu-id="d58b0-104">Report parameters are created automatically for each query parameter that you include in a dataset query.</span></span> <span data-ttu-id="d58b0-105">Le type de données du paramètre détermine son apparence dans la barre d'outils de l'affichage du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-105">The parameter data type determines how it appears on the report view toolbar.</span></span>  
  
 <span data-ttu-id="d58b0-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span><span class="sxs-lookup"><span data-stu-id="d58b0-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="d58b0-107">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="d58b0-107">What You Will Learn</span></span>  
 <span data-ttu-id="d58b0-108">Dans ce didacticiel, vous apprendrez à effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="d58b0-108">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="d58b0-109">Créer un rapport de matrice et un dataset à partir de l'Assistant Tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="d58b0-109">Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="d58b0-110">Organiser les données, choisir la mise en page et le style à partir de l'Assistant Tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="d58b0-110">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="d58b0-111">Ajouter un paramètre de requête pour créer un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-111">Add a Query Parameter to Create a Report Parameter</span></span>](#Query)  
  
4.  [<span data-ttu-id="d58b0-112">Modifier le type de données par défaut et d'autres propriétés pour un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-112">Change Default Data Type and Other Properties for a Report Parameter</span></span>](#ChangeDefaultProperties)  
  
    1.  [<span data-ttu-id="d58b0-113">Ajouter un dataset pour fournir des valeurs disponibles et des noms d'affichage</span><span class="sxs-lookup"><span data-stu-id="d58b0-113">Add a Dataset to Provide Available Values and Display Names</span></span>](#AddDataset)  
  
    2.  [<span data-ttu-id="d58b0-114">Spécifier les valeurs disponibles pour la création d'une liste déroulante de valeurs</span><span class="sxs-lookup"><span data-stu-id="d58b0-114">Specify Available Values to Create a Drop-List of Values</span></span>](#AvailableValues)  
  
    3.  [<span data-ttu-id="d58b0-115">Spécifier des valeurs par défaut de sorte que le rapport s'exécute automatiquement</span><span class="sxs-lookup"><span data-stu-id="d58b0-115">Specify Default Values so the Report Runs Automatically</span></span>](#DefaultValues)  
  
    4.  [<span data-ttu-id="d58b0-116">Rechercher une valeur à partir d'un dataset qui contient des paires nom/valeur</span><span class="sxs-lookup"><span data-stu-id="d58b0-116">Look up a Value from a Dataset that has Name/Value Pairs</span></span>](#NameValue)  
  
5.  [<span data-ttu-id="d58b0-117">Afficher la valeur de paramètre sélectionnée dans le rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-117">Display the Selected Parameter Value in the Report</span></span>](#Expression)  
  
6.  [<span data-ttu-id="d58b0-118">Utiliser le paramètre de rapport dans un filtre</span><span class="sxs-lookup"><span data-stu-id="d58b0-118">Use the Report Parameter in a Filter</span></span>](#Filter)  
  
7.  [<span data-ttu-id="d58b0-119">Modifier le paramètre de rapport pour accepter plusieurs valeurs</span><span class="sxs-lookup"><span data-stu-id="d58b0-119">Change the Report Parameter to Accept Multiple Values</span></span>](#Multivalued)  
  
8.  [<span data-ttu-id="d58b0-120">Ajouter un paramètre booléen pour la visibilité conditionnelle</span><span class="sxs-lookup"><span data-stu-id="d58b0-120">Add a Boolean Parameter for Conditional Visibility</span></span>](#Boolean)  
  
9. [<span data-ttu-id="d58b0-121">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-121">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="d58b0-122">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-122">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="d58b0-123">Dans ce didacticiel, les étapes de l'Assistant sont consolidées en une seule procédure.</span><span class="sxs-lookup"><span data-stu-id="d58b0-123">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="d58b0-124">Pour obtenir des instructions pas à pas sur l’accès à un serveur de rapports, le choix d’une source de données et la création d’un dataset, consultez le premier didacticiel de cette série : [Didacticiel : création d’un rapport de tableau de base &#40;Générateur de rapports&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="d58b0-124">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="d58b0-125">Durée estimée pour effectuer le didacticiel : 25 minutes.</span><span class="sxs-lookup"><span data-stu-id="d58b0-125">Estimated time to complete this tutorial: 25 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d58b0-126">Spécifications</span><span class="sxs-lookup"><span data-stu-id="d58b0-126">Requirements</span></span>  
 <span data-ttu-id="d58b0-127">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="d58b0-127">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="d58b0-128">1. créer un rapport de matrice et un DataSet à partir de l’Assistant tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="d58b0-128">1. Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="d58b0-129">Créez un rapport de matrice, une source de données et un dataset.</span><span class="sxs-lookup"><span data-stu-id="d58b0-129">Create a matrix report, a data source, and a dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d58b0-130">Dans ce didacticiel, la requête contient les valeurs de données, afin qu'il ne soit pas nécessaire de disposer d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d58b0-130">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="d58b0-131">Cela rend la requête assez longue.</span><span class="sxs-lookup"><span data-stu-id="d58b0-131">This makes the query quite long.</span></span> <span data-ttu-id="d58b0-132">Dans un environnement métier, une requête ne contient pas les données.</span><span class="sxs-lookup"><span data-stu-id="d58b0-132">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="d58b0-133">Ceci est nécessaire à des fins de formation uniquement.</span><span class="sxs-lookup"><span data-stu-id="d58b0-133">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix-report"></a><span data-ttu-id="d58b0-134">Pour créer un rapport de matrice</span><span class="sxs-lookup"><span data-stu-id="d58b0-134">To create a new matrix report</span></span>  
  
1.  <span data-ttu-id="d58b0-135">Cliquez sur **Démarrer**, pointez sur **programmes**, sur [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Générateur de rapports**, puis cliquez sur **Générateur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-135">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="d58b0-136">La boîte de dialogue **prise en main** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="d58b0-136">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d58b0-137">Si la boîte de dialogue **prise en main** n’apparaît pas, à partir du bouton **Générateur de rapports** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-137">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="d58b0-138">Dans le volet gauche, assurez-vous que **Rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d58b0-138">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="d58b0-139">Dans le volet droit, cliquez sur **Assistant Tableau ou matrice**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-139">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="d58b0-140">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-140">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="d58b0-141">Dans la page **Choisir un dataset** , cliquez sur **Créer un dataset**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-141">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
6.  <span data-ttu-id="d58b0-142">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-142">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="d58b0-143">Dans la page **Choisir une connexion à une source de données** , sélectionnez une source de données de type **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-143">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="d58b0-144">Sélectionnez une source de données dans la liste ou naviguez jusqu'au serveur de rapports pour en sélectionner une.</span><span class="sxs-lookup"><span data-stu-id="d58b0-144">Select a data source from the list or browse to the report server to select one.</span></span>  
  
8.  <span data-ttu-id="d58b0-145">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-145">Click **Next**.</span></span>  
  
9. <span data-ttu-id="d58b0-146">Dans la page **Créer une requête** , cliquez sur **Modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-146">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
10. <span data-ttu-id="d58b0-147">Collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="d58b0-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    ;WITH CTE (StoreID, Subcategory, Quantity)   
    AS (  
    SELECT 200 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 2002 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Camcorders' AS Subcategory, 1954 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Accessories' AS Subcategory, 1895 AS Quantity  
    UNION SELECT  199 AS StoreID, 'Digital Cameras' AS Subcategory, 1849 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1579 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Camcorders' AS Subcategory, 1561 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital Cameras' AS Subcategory, 1553 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Accessories' AS Subcategory, 1534 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Accessories' AS Subcategory, 1755 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Camcorders' AS Subcategory, 1631 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1772 AS Quantity)  
    SELECT StoreID, Subcategory, Quantity  
    FROM CTE  
    ```  
  
     <span data-ttu-id="d58b0-148">Cette requête combine les résultats de plusieurs instructions SELECT [!INCLUDE[tsql](../includes/tsql-md.md)] dans une expression de table commune pour spécifier des valeurs basées sur des données simplifiées de l'exemple de base de données Contoso.</span><span class="sxs-lookup"><span data-stu-id="d58b0-148">This query combines the results of several [!INCLUDE[tsql](../includes/tsql-md.md)] SELECT statements inside a common table expression to specify values that are based on simplified data from the Contoso sample database.</span></span> <span data-ttu-id="d58b0-149">Les données de ventes de Contoso représentent les données de ventes internationales relatives aux biens de consommation.</span><span class="sxs-lookup"><span data-stu-id="d58b0-149">The Contoso sales data represents international sales data for consumer goods.</span></span> <span data-ttu-id="d58b0-150">Ce didacticiel utilise les données de ventes spécifiques aux appareils photo.</span><span class="sxs-lookup"><span data-stu-id="d58b0-150">This tutorial uses sales data for cameras.</span></span> <span data-ttu-id="d58b0-151">Les sous-catégories représentent les appareils photo numériques, les appareils photo numériques reflex à lentille unique (SLR), les caméscopes et les accessoires.</span><span class="sxs-lookup"><span data-stu-id="d58b0-151">The subcategories represent digital cameras, digital single lens reflex (SLR) cameras, camcorders, and accessories.</span></span>  
  
     <span data-ttu-id="d58b0-152">La requête spécifie des noms de colonnes comprenant un identificateur de magasin, une sous-catégorie d'éléments de ventes et le volume commandé pour les commandes client de trois magasins.</span><span class="sxs-lookup"><span data-stu-id="d58b0-152">The query specifies column names that include a store identifier, a sales item subcategory, and the quantity ordered for sales orders from three stores.</span></span> <span data-ttu-id="d58b0-153">Dans cette requête, le nom du magasin ne fait pas partie du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="d58b0-153">In this query, the store name is not part of the result set.</span></span> <span data-ttu-id="d58b0-154">Ultérieurement, dans ce didacticiel, vous rechercherez le nom du magasin qui correspond à l'identificateur de magasin d'un dataset distinct.</span><span class="sxs-lookup"><span data-stu-id="d58b0-154">Later in this tutorial, you will look up the name of the store that corresponds to the store identifier from a separate dataset.</span></span>  
  
     <span data-ttu-id="d58b0-155">Cette requête ne contient pas de paramètres de requête.</span><span class="sxs-lookup"><span data-stu-id="d58b0-155">This query does not contain query parameters.</span></span> <span data-ttu-id="d58b0-156">Vous ajouterez ultérieurement des paramètres de requête dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="d58b0-156">You will add query parameters later in this tutorial.</span></span>  
  
11. <span data-ttu-id="d58b0-157">Dans la barre d’outils du concepteur de requêtes, cliquez sur **exécuter** (**!**).</span><span class="sxs-lookup"><span data-stu-id="d58b0-157">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="d58b0-158">Le jeu de résultats affiche 11 lignes de données qui montrent le volume d'articles vendus pour chaque sous-catégorie dans quatre magasins et inclut les colonnes suivantes : StoreID, Subcategory, Quantity.</span><span class="sxs-lookup"><span data-stu-id="d58b0-158">The result set displays 11 rows of data that show the quantity of items sold for each subcategory for four stores, and includes the following columns: StoreID, Subcategory, Quantity.</span></span>  
  
12. <span data-ttu-id="d58b0-159">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-159">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="d58b0-160">2. organiser les données, choisir la disposition et le style à partir de l’Assistant tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="d58b0-160">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="d58b0-161">Utilisez l'Assistant pour obtenir une conception initiale dans laquelle afficher les données.</span><span class="sxs-lookup"><span data-stu-id="d58b0-161">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="d58b0-162">Le volet de visualisation de l'Assistant vous aide à visualiser le résultat du regroupement des données avant de terminer la conception de la table ou de la matrice.</span><span class="sxs-lookup"><span data-stu-id="d58b0-162">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="d58b0-163">Pour organiser les données en groupes</span><span class="sxs-lookup"><span data-stu-id="d58b0-163">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="d58b0-164">Dans la page **Organiser les champs** , faites glisser Subcategory vers **Groupes de lignes**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-164">On the **Arrange fields** page, drag Subcategory to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="d58b0-165">Faites glisser StoreID vers **Groupes de colonnes**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-165">Drag StoreID to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="d58b0-166">Faites glisser Quantity vers **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-166">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="d58b0-167">Vous avez organisé les valeurs des quantités vendues dans des lignes regroupées par sous-catégorie.</span><span class="sxs-lookup"><span data-stu-id="d58b0-167">You have organized the quantity sold values in rows grouped by subcategory.</span></span> <span data-ttu-id="d58b0-168">Il y a une colonne pour chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="d58b0-168">There will be one column for each store.</span></span>  
  
4.  <span data-ttu-id="d58b0-169">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-169">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="d58b0-170">Dans la page **choisir une disposition** , sous **options**, vérifiez que **afficher les sous-totaux et les totaux généraux** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d58b0-170">On the **Choose a Layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="d58b0-171">Lorsque vous exécuterez le rapport, la dernière colonne affichera la quantité totale de chaque sous-catégorie pour tous les magasins, et la dernière ligne affichera la quantité totale pour toutes les sous-catégories pour chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="d58b0-171">When you run the report, the last column will show the total quantity of each subcategory for all stores, and the last row will show the total quantity for all subcategories for each store.</span></span>  
  
6.  <span data-ttu-id="d58b0-172">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-172">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="d58b0-173">Dans la page **choisir un style** , dans le volet styles, sélectionnez un style.</span><span class="sxs-lookup"><span data-stu-id="d58b0-173">On the **Choose a Style** page, in the Styles pane, select a style.</span></span>  
  
8.  <span data-ttu-id="d58b0-174">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-174">Click **Finish**.</span></span>  
  
     <span data-ttu-id="d58b0-175">La matrice est ajoutée à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="d58b0-175">The matrix is added to the design surface.</span></span> <span data-ttu-id="d58b0-176">La matrice affiche trois colonnes et trois lignes.</span><span class="sxs-lookup"><span data-stu-id="d58b0-176">The matrix displays three columns and three rows.</span></span> <span data-ttu-id="d58b0-177">Les cellules de la première ligne contiennent Subcategory, [StoreID] et Total.</span><span class="sxs-lookup"><span data-stu-id="d58b0-177">The contents of the cells in the first row are Subcategory, [StoreID], and Total.</span></span> <span data-ttu-id="d58b0-178">Les cellules de la deuxième ligne contiennent des expressions qui représentent la sous-catégorie, la quantité d'articles vendus pour chaque magasin, ainsi que la quantité totale de chaque sous-catégorie pour tous les magasins.</span><span class="sxs-lookup"><span data-stu-id="d58b0-178">The contents of the cells in the second row contain expressions that represent the subcategory, the quantity of items sold for each store, and the total quantity for each subcategory for all stores.</span></span> <span data-ttu-id="d58b0-179">Les cellules de la dernière ligne affichent le total global pour chaque magasin.</span><span class="sxs-lookup"><span data-stu-id="d58b0-179">The cells in the final row display the grand total for each store.</span></span>  
  
9. <span data-ttu-id="d58b0-180">Cliquez dans la matrice, pointez sur le bord de la première colonne, saisissez la poignée, puis augmentez la largeur de la colonne.</span><span class="sxs-lookup"><span data-stu-id="d58b0-180">Click in the matrix, hover over the edge of the first column, grab the handle, and expand the column width.</span></span>  
  
10. <span data-ttu-id="d58b0-181">Cliquez sur **Exécuter** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-181">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="d58b0-182">Le rapport s'exécute sur le serveur de rapports en présentant son titre et l'heure à laquelle il a été traité.</span><span class="sxs-lookup"><span data-stu-id="d58b0-182">The report runs on the report server and displays the title and the time the report processing occurred.</span></span>  
  
 <span data-ttu-id="d58b0-183">Dans ce scénario, les en-têtes de colonnes affichent l'identificateur du magasin mais pas le nom du magasin.</span><span class="sxs-lookup"><span data-stu-id="d58b0-183">In this scenario, the column headings display the store identifier but not the store name.</span></span> <span data-ttu-id="d58b0-184">Ultérieurement, vous ajouterez une expression pour rechercher le nom de magasin dans un dataset qui contient des paires nom d'identificateur/nom de magasin.</span><span class="sxs-lookup"><span data-stu-id="d58b0-184">Later, you will add an expression to look up the store name in a dataset that contains store identifier/store name pairs.</span></span>  
  
##  <a name="3-add-a-query-parameter-to-create-a-report-parameter"></a><a name="Query"></a><span data-ttu-id="d58b0-185">3. Ajouter un paramètre de requête pour créer un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-185">3. Add a Query Parameter to Create a Report Parameter</span></span>  
 <span data-ttu-id="d58b0-186">Lorsque vous ajoutez un paramètre de requête à une requête, le Générateur de rapports crée automatiquement un paramètre de rapport à valeur unique avec des propriétés par défaut pour le nom, le texte affiché à l'invite et le type de données.</span><span class="sxs-lookup"><span data-stu-id="d58b0-186">When you add a query parameter to a query, Report Builder automatically creates a single-valued report parameter with default properties for name, prompt, and data type.</span></span>  
  
#### <a name="to-add-a-query-parameter"></a><span data-ttu-id="d58b0-187">Pour ajouter un paramètre de requête</span><span class="sxs-lookup"><span data-stu-id="d58b0-187">To add a query parameter</span></span>  
  
1.  <span data-ttu-id="d58b0-188">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="d58b0-188">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="d58b0-189">Dans le volet des données de rapport, développez le dossier **Datasets** , cliquez avec le bouton droit sur **DataSet1**, puis cliquez sur **Requête**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-189">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
3.  <span data-ttu-id="d58b0-190">Ajoutez la [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause suivante comme dernière ligne de la requête :</span><span class="sxs-lookup"><span data-stu-id="d58b0-190">Add the following [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause as the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID = (@StoreID)  
    ```  
  
     <span data-ttu-id="d58b0-191">La `WHERE` clause limite les données récupérées à l’identificateur de magasin spécifié par le paramètre de requête *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="d58b0-191">The `WHERE` clause limits the retrieved data to the store identifier that is specified by the query parameter *@StoreID*.</span></span>  
  
4.  <span data-ttu-id="d58b0-192">Dans la barre d’outils du concepteur de requêtes, cliquez sur **exécuter** (**!**).</span><span class="sxs-lookup"><span data-stu-id="d58b0-192">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="d58b0-193">La boîte de dialogue **Définir les paramètres de la requête** s’ouvre et vous êtes invité à définir une valeur pour le paramètre de requête *@StoreID*.</span><span class="sxs-lookup"><span data-stu-id="d58b0-193">The **Define Query Parameters** dialog box opens and prompts for a value for the query parameter *@StoreID*.</span></span>  
  
5.  <span data-ttu-id="d58b0-194">Dans **Valeur du paramètre**, tapez **200**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-194">In **Parameter Value**, type **200**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="d58b0-195">Le jeu de résultats affiche les quantités vendues des articles « Accessories », « Camcorders » et « Digital SLR Cameras » pour l’identificateur de magasin **200**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-195">The result set displays the quantities sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="d58b0-196">Dans le volet des données de rapport, développez le dossier **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="d58b0-196">In the Report Data pane, expand the **Parameters** folder.</span></span>  
  
 <span data-ttu-id="d58b0-197">Notez qu’il existe désormais un paramètre de rapport nommé *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="d58b0-197">Notice that there is now a report parameter named *@StoreID*.</span></span> <span data-ttu-id="d58b0-198">Par défaut, le type de données du paramètre est **texte**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-198">By default, the parameter has data type **Text**.</span></span> <span data-ttu-id="d58b0-199">Dans la mesure où l'identificateur de magasin est un entier, vous devez remplacer le type de données par le type Entier dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="d58b0-199">Because the store identifier is an integer, you will change the data type to Integer in the next procedure.</span></span>  
  
##  <a name="4-change-default-data-type-and-other-properties-for-a-report-parameter"></a><a name="ChangeDefaultProperties"></a><span data-ttu-id="d58b0-200">4. modifier le type de données par défaut et d’autres propriétés pour un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-200">4. Change Default Data Type and Other Properties for a Report Parameter</span></span>  
 <span data-ttu-id="d58b0-201">Après avoir créé un paramètre de rapport, vous pouvez ajuster les valeurs par défaut des propriétés.</span><span class="sxs-lookup"><span data-stu-id="d58b0-201">After a report parameter is created, you can adjust the default values for properties.</span></span>  
  
#### <a name="to-change-the-default-data-type-for-a-report-parameter"></a><span data-ttu-id="d58b0-202">Pour modifier le type de données par défaut d'un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-202">To change the default data type for a report parameter</span></span>  
  
1.  <span data-ttu-id="d58b0-203">Dans le volet des données de rapport, sous le nœud **paramètres** , cliquez avec le bouton droit sur *@StoreID* , puis cliquez sur **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-203">In the Report Data pane under the **Parameters** node, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="d58b0-204">Dans invite, tapez **identificateur du magasin ?**</span><span class="sxs-lookup"><span data-stu-id="d58b0-204">In Prompt, type **Store identifier?**</span></span> <span data-ttu-id="d58b0-205">Ce texte s'affiche sur la barre d'outils de la visionneuse de rapports lorsque vous exécutez le rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-205">This text appears on the report viewer toolbar when you run the report.</span></span>  
  
3.  <span data-ttu-id="d58b0-206">Dans **Type de données**, dans la liste déroulante, sélectionnez **Entier**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-206">In **Data type**, from the drop-down list, select **Integer**.</span></span>  
  
4.  <span data-ttu-id="d58b0-207">Acceptez les valeurs par défaut restantes dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d58b0-207">Accept the remaining default values in the dialog box.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="d58b0-208">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-208">Preview the report.</span></span> <span data-ttu-id="d58b0-209">La visionneuse de rapports affiche l’invite pour *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="d58b0-209">The report viewer displays the prompt for *@StoreID*.</span></span>  
  
7.  <span data-ttu-id="d58b0-210">Dans la barre d’outils de la visionneuse de rapports, en regard de StoreID, tapez **200**, puis cliquez sur **Afficher le rapport**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-210">On the report viewer toolbar, next to Store ID, type **200**, and then click **View Report**.</span></span>  
  
##  <a name="4a-add-a-dataset-to-provide-available-values-and-display-names"></a><a name="AddDataset"></a><span data-ttu-id="d58b0-211">4a.</span><span class="sxs-lookup"><span data-stu-id="d58b0-211">4a.</span></span> <span data-ttu-id="d58b0-212">Ajouter un dataset pour fournir des valeurs disponibles et des noms d'affichage</span><span class="sxs-lookup"><span data-stu-id="d58b0-212">Add a Dataset to Provide Available Values and Display Names</span></span>  
 <span data-ttu-id="d58b0-213">Pour vous assurer qu'un utilisateur ne peut taper que des valeurs valides pour un paramètre, vous pouvez créer une liste déroulante de valeurs à choisir.</span><span class="sxs-lookup"><span data-stu-id="d58b0-213">To ensure a user can type only valid values for a parameter, you can create a drop-down list of values to choose from.</span></span> <span data-ttu-id="d58b0-214">Les valeurs peuvent provenir d'un dataset ou d'une liste que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="d58b0-214">The values can come from a dataset or from a list that you specify.</span></span> <span data-ttu-id="d58b0-215">Les valeurs disponibles doivent être fournies à partir d'un dataset comportant une requête qui ne contient pas de référence au paramètre.</span><span class="sxs-lookup"><span data-stu-id="d58b0-215">Available values must be supplied from a dataset that has a query that does not contain a reference to the parameter.</span></span>  
  
#### <a name="to-create-a-dataset-for-valid-values-for-a-parameter"></a><span data-ttu-id="d58b0-216">Pour créer un dataset de valeurs valides pour un paramètre</span><span class="sxs-lookup"><span data-stu-id="d58b0-216">To create a dataset for valid values for a parameter</span></span>  
  
1.  <span data-ttu-id="d58b0-217">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="d58b0-217">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="d58b0-218">Dans le volet des données de rapport, cliquez avec le bouton droit sur le dossier **Datasets** , puis cliquez sur **Ajouter un dataset**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-218">In the Report Data pane, right-click the **Datasets** folder, and then click **Add Dataset**.</span></span>  
  
3.  <span data-ttu-id="d58b0-219">Dans **Nom**, tapez **Stores**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-219">In **Name**, type **Stores**.</span></span>  
  
4.  <span data-ttu-id="d58b0-220">Sélectionnez l’option **utiliser un dataset incorporé dans mon rapport** .</span><span class="sxs-lookup"><span data-stu-id="d58b0-220">Select the **Use a dataset embedded in my report** option.</span></span>  
  
5.  <span data-ttu-id="d58b0-221">Dans **source de données**, dans la liste déroulante, choisissez la source de données que vous avez créée dans la première procédure.</span><span class="sxs-lookup"><span data-stu-id="d58b0-221">In **Data source**, from the drop-down list, choose the data source you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="d58b0-222">Dans **Type de requête**, assurez-vous que **Texte** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d58b0-222">In **Query type**, verify that **Text** is selected.</span></span>  
  
7.  <span data-ttu-id="d58b0-223">Dans **Requête**, collez le texte suivant :</span><span class="sxs-lookup"><span data-stu-id="d58b0-223">In **Query**, paste the following text:</span></span>  
  
    ```  
    SELECT 200 AS StoreID, 'Contoso Catalog Store' as StoreName  
    UNION SELECT 199 AS StoreID, 'Contoso North America Online Store' as StoreName  
    UNION SELECT 307 AS StoreID, 'Contoso Asia Online Store' as StoreName  
    UNION SELECT 306 AS StoreID, 'Contoso Europe Online Store' as StoreName  
    ```  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="d58b0-224">Le volet des données de rapport affiche les champs StoreID et StoreName sous le nœud du dataset **Stores** .</span><span class="sxs-lookup"><span data-stu-id="d58b0-224">The Report Data pane displays the fields StoreID and StoreName under the **Stores** dataset node.</span></span>  
  
##  <a name="4b-specify-available-values-to-create-a-drop-down-list-of-values"></a><a name="AvailableValues"></a><span data-ttu-id="d58b0-225">4b.</span><span class="sxs-lookup"><span data-stu-id="d58b0-225">4b.</span></span> <span data-ttu-id="d58b0-226">Spécifier les valeurs disponibles pour la création d'une liste déroulante de valeurs</span><span class="sxs-lookup"><span data-stu-id="d58b0-226">Specify Available Values to Create a Drop-down List of Values</span></span>  
 <span data-ttu-id="d58b0-227">Après avoir créé un dataset pour fournir des valeurs disponibles, vous devez modifier les propriétés de rapport pour spécifier quel dataset et quel champ utiliser pour remplir la liste déroulante à l'aide de valeurs valides dans la barre d'outils de la visionneuse de rapports.</span><span class="sxs-lookup"><span data-stu-id="d58b0-227">After you create a dataset to provide available values, you must change the report properties to specify which dataset and which field to use to populate the drop-down list of valid values on the reportviewer toolbar.</span></span>  
  
#### <a name="to-provide-available-values-for-a-parameter-from-a-dataset"></a><span data-ttu-id="d58b0-228">Pour fournir des valeurs disponibles pour un paramètre à partir d'un dataset</span><span class="sxs-lookup"><span data-stu-id="d58b0-228">To provide available values for a parameter from a dataset</span></span>  
  
1.  <span data-ttu-id="d58b0-229">Dans le volet données du rapport, cliquez avec le bouton droit sur le paramètre *@StoreID* , puis cliquez sur **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-229">In the Report Data pane, right-click the parameter *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="d58b0-230">Cliquez sur **Valeurs disponibles**, puis sur **Obtenir les valeurs à partir d’une requête**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-230">Click **Available Values**, and then click **Get values from a query**.</span></span>  
  
3.  <span data-ttu-id="d58b0-231">Dans la liste déroulante **Dataset**, cliquez sur **Stores**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-231">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
4.  <span data-ttu-id="d58b0-232">Dans la liste déroulante **Champ de valeur**, cliquez sur StoreID.</span><span class="sxs-lookup"><span data-stu-id="d58b0-232">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
5.  <span data-ttu-id="d58b0-233">Dans la liste déroulante **Champ d’étiquette**, cliquez sur StoreName.</span><span class="sxs-lookup"><span data-stu-id="d58b0-233">In **Label field**, from the drop-down list, click StoreName.</span></span> <span data-ttu-id="d58b0-234">Le champ d'étiquette spécifie le nom d'affichage de la valeur.</span><span class="sxs-lookup"><span data-stu-id="d58b0-234">The label field specifies the display name for the value.</span></span>  
  
6.  <span data-ttu-id="d58b0-235">Cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-235">Click **General**.</span></span>  
  
7.  <span data-ttu-id="d58b0-236">Dans invite, tapez **nom du magasin ?**</span><span class="sxs-lookup"><span data-stu-id="d58b0-236">In Prompt, type **Store name?**</span></span>  
  
     <span data-ttu-id="d58b0-237">L'utilisateur sélectionnera désormais un nom dans une liste de noms de magasins au lieu d'identificateurs de magasin.</span><span class="sxs-lookup"><span data-stu-id="d58b0-237">The user will now select from a list of store names instead of store identifiers.</span></span> <span data-ttu-id="d58b0-238">Notez que le type de données du paramètre reste **Entier** , car le paramètre est basé sur l’identificateur de magasin au lieu du nom de magasin.</span><span class="sxs-lookup"><span data-stu-id="d58b0-238">Note that the parameter data type remains **Integer** because the parameter is based on the store identifier, not the store name.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="d58b0-239">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-239">Preview the report.</span></span>  
  
     <span data-ttu-id="d58b0-240">Dans la barre d’outils de la visionneuse de rapports, la zone de texte du paramètre est maintenant une liste déroulante qui s’affiche **\<Select a Value>** .</span><span class="sxs-lookup"><span data-stu-id="d58b0-240">In the report viewer toolbar, the parameter text box is now a drop-down list that displays **\<Select a Value>**.</span></span>  
  
10. <span data-ttu-id="d58b0-241">Dans la liste déroulante, sélectionnez magasin du catalogue contoso, puis cliquez sur **afficher le rapport**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-241">From the drop-down list, select Contoso Catalog Store, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="d58b0-242">Le rapport affiche les quantités vendues des articles « Accessories », « Camcorders » et « Digital SLR Cameras » pour l’identificateur de magasin **200**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-242">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4c-specify-default-values-so-the-report-runs-automatically"></a><a name="DefaultValues"></a><span data-ttu-id="d58b0-243">Quat.</span><span class="sxs-lookup"><span data-stu-id="d58b0-243">4c.</span></span> <span data-ttu-id="d58b0-244">Spécifier des valeurs par défaut de sorte que le rapport s'exécute automatiquement</span><span class="sxs-lookup"><span data-stu-id="d58b0-244">Specify Default Values so the Report Runs Automatically</span></span>  
 <span data-ttu-id="d58b0-245">Vous pouvez spécifier une valeur par défaut pour chaque paramètre afin que le rapport s'exécute automatiquement.</span><span class="sxs-lookup"><span data-stu-id="d58b0-245">You can specify a default value for each parameter so the report runs automatically.</span></span>  
  
#### <a name="to-specify-a-default-value-from-a-dataset"></a><span data-ttu-id="d58b0-246">Pour spécifier une valeur par défaut à partir d'un dataset</span><span class="sxs-lookup"><span data-stu-id="d58b0-246">To specify a default value from a dataset</span></span>  
  
1.  <span data-ttu-id="d58b0-247">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="d58b0-247">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="d58b0-248">Dans le volet des données de rapport, cliquez avec le bouton droit sur *@StoreID* , puis cliquez sur **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-248">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="d58b0-249">Cliquez sur **valeurs par défaut**, puis sur **obtenir les valeurs à partir d’une requête**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-249">Click **Default Values**, and then click **Get values from a query**.</span></span>  
  
4.  <span data-ttu-id="d58b0-250">Dans la liste déroulante **Dataset**, cliquez sur **Stores**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-250">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
5.  <span data-ttu-id="d58b0-251">Dans la liste déroulante **Champ de valeur**, cliquez sur StoreID.</span><span class="sxs-lookup"><span data-stu-id="d58b0-251">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="d58b0-252">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-252">Preview the report.</span></span>  
  
 <span data-ttu-id="d58b0-253">Pour *@StoreID* , la visionneuse de rapports affiche la valeur « Contoso Amérique du Nord Online Store ».</span><span class="sxs-lookup"><span data-stu-id="d58b0-253">For *@StoreID*, the report viewer displays the value "Contoso North America Online Store".</span></span> <span data-ttu-id="d58b0-254">Il s’agit de la première valeur du jeu de résultats pour les **magasins**de jeux de données.</span><span class="sxs-lookup"><span data-stu-id="d58b0-254">This is the first value from the result set for the dataset **Stores**.</span></span> <span data-ttu-id="d58b0-255">Le rapport affiche la quantité vendue des articles « Digital Cameras » pour l’identificateur de magasin **199**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-255">The report displays the quantity sold for Digital Cameras for store identifier **199**.</span></span>  
  
#### <a name="to-specify-a-custom-default-value"></a><span data-ttu-id="d58b0-256">Pour spécifier une valeur par défaut personnalisée</span><span class="sxs-lookup"><span data-stu-id="d58b0-256">To specify a custom default value</span></span>  
  
1.  <span data-ttu-id="d58b0-257">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="d58b0-257">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="d58b0-258">Dans le volet des données de rapport, cliquez avec le bouton droit sur *@StoreID* , puis cliquez sur **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-258">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="d58b0-259">Cliquez sur **valeurs par défaut**, cliquez sur **spécifier les valeurs**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-259">Click **Default Values**, and click **Specify values**, and then click **Add**.</span></span> <span data-ttu-id="d58b0-260">Une nouvelle ligne de valeurs est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="d58b0-260">A new value row is added.</span></span>  
  
4.  <span data-ttu-id="d58b0-261">Dans **Valeur**, tapez **200**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-261">In **Value**, type **200**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="d58b0-262">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-262">Preview the report.</span></span>  
  
 <span data-ttu-id="d58b0-263">Pour *@StoreID* , la visionneuse de rapports affiche la valeur « Contoso Catalog Store ».</span><span class="sxs-lookup"><span data-stu-id="d58b0-263">For *@StoreID*, the report viewer displays the value "Contoso Catalog Store".</span></span> <span data-ttu-id="d58b0-264">Il s’agit du nom d’affichage de l’identificateur de magasin **200**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-264">This is the display name for store identifier **200**.</span></span> <span data-ttu-id="d58b0-265">Le rapport affiche les quantités vendues des articles « Accessories », « Camcorders » et « Digital SLR Cameras » pour l’identificateur de magasin **200**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-265">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4d-look-up-a-value-from-a-dataset-that-has-namevalue-pairs"></a><a name="NameValue"></a><span data-ttu-id="d58b0-266">4D.</span><span class="sxs-lookup"><span data-stu-id="d58b0-266">4d.</span></span> <span data-ttu-id="d58b0-267">Rechercher une valeur à partir d'un dataset qui contient des paires nom/valeur</span><span class="sxs-lookup"><span data-stu-id="d58b0-267">Look up a Value from a Dataset that has Name/Value Pairs</span></span>  
 <span data-ttu-id="d58b0-268">Un dataset peut contenir à la fois l'identificateur et le champ Nom correspondant.</span><span class="sxs-lookup"><span data-stu-id="d58b0-268">A dataset might contain both the identifier and the corresponding name field.</span></span> <span data-ttu-id="d58b0-269">Lorsque vous avez seulement un identificateur, vous pouvez rechercher le nom correspondant dans un dataset que vous avez créé et qui inclut des paires nom/valeur.</span><span class="sxs-lookup"><span data-stu-id="d58b0-269">When you only have an identifier, you can look up the corresponding name in a dataset that you created that includes name/value pairs.</span></span>  
  
#### <a name="to-look-up-a-value-from-a-dataset"></a><span data-ttu-id="d58b0-270">Pour rechercher une valeur dans un dataset</span><span class="sxs-lookup"><span data-stu-id="d58b0-270">To look up a value from a dataset</span></span>  
  
1.  <span data-ttu-id="d58b0-271">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="d58b0-271">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="d58b0-272">Dans l’aire de conception, dans la matrice, dans le premier en-tête de ligne ou de colonne, cliquez avec le bouton droit sur `[StoreID]` , puis cliquez sur **Expression**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-272">On the design surface, in the matrix, in the first row column header, right-click `[StoreID]` and then click **Expression**.</span></span>  
  
3.  <span data-ttu-id="d58b0-273">Dans le volet Expression, supprimez tout le texte sauf le signe `equals` (=) de début.</span><span class="sxs-lookup"><span data-stu-id="d58b0-273">In the expression pane, delete all text except the beginning `equals` (=).</span></span>  
  
4.  <span data-ttu-id="d58b0-274">Dans **Catégorie**, développez **Fonctions communes**, puis cliquez sur **Divers**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-274">In **Category**, expand **Common Functions**, and click **Miscellaneous**.</span></span> <span data-ttu-id="d58b0-275">Le volet Élément affiche un ensemble de fonctions.</span><span class="sxs-lookup"><span data-stu-id="d58b0-275">The Item pane displays a set of functions.</span></span>  
  
5.  <span data-ttu-id="d58b0-276">Dans Élément, double-cliquez sur **Recherche**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-276">In Item, double-click **Lookup**.</span></span> <span data-ttu-id="d58b0-277">Le volet Expression affiche `=Lookup(`.</span><span class="sxs-lookup"><span data-stu-id="d58b0-277">The expression pane displays `=Lookup(`.</span></span> <span data-ttu-id="d58b0-278">Le volet d'exemple affiche un exemple de syntaxe de recherche.</span><span class="sxs-lookup"><span data-stu-id="d58b0-278">The Example pane displays an example of Lookup syntax.</span></span>  
  
6.  <span data-ttu-id="d58b0-279">Tapez l’expression suivante : `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span><span class="sxs-lookup"><span data-stu-id="d58b0-279">Type the following expression: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span></span>  
  
     <span data-ttu-id="d58b0-280">La fonction de recherche prend la valeur de StoreID, la recherche dans le dataset « Stores », puis retourne la valeur StoreName.</span><span class="sxs-lookup"><span data-stu-id="d58b0-280">The Lookup function takes the value for StoreID, looks it up in the "Stores" dataset, and returns the StoreName value.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="d58b0-281">L’en-tête de colonne de magasin contient le texte affiché pour une expression complexe : **<\<Expr>>** .</span><span class="sxs-lookup"><span data-stu-id="d58b0-281">The store column header contains the display text for a complex expression: **<\<Expr>>**.</span></span>  
  
8.  <span data-ttu-id="d58b0-282">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-282">Preview the report.</span></span>  
  
 <span data-ttu-id="d58b0-283">La zone de texte en haut de chaque page affiche le nom de magasin au lieu de l'identificateur de magasin.</span><span class="sxs-lookup"><span data-stu-id="d58b0-283">The text box at the top of each page displays the store name instead of the store identifier.</span></span>  
  
##  <a name="5-display-the-selected-parameter-value-in-the-report"></a><a name="Expression"></a><span data-ttu-id="d58b0-284">5. afficher la valeur de paramètre sélectionnée dans le rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-284">5. Display the Selected Parameter Value in the Report</span></span>  
 <span data-ttu-id="d58b0-285">Lorsqu'un utilisateur a des questions sur un rapport, il est utile de connaître les valeurs de paramètres qu'il a choisies.</span><span class="sxs-lookup"><span data-stu-id="d58b0-285">When a user has questions about a report, it helps to know which parameter values they chose.</span></span> <span data-ttu-id="d58b0-286">Vous pouvez conserver les valeurs sélectionnées par l'utilisateur pour chaque paramètre du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-286">You can preserve user-selected values for each parameter in the report.</span></span> <span data-ttu-id="d58b0-287">L'une des solutions possibles consiste à afficher les paramètres dans une zone de texte au sein du pied de page.</span><span class="sxs-lookup"><span data-stu-id="d58b0-287">One way is to display the parameters in a text box in the page footer.</span></span>  
  
#### <a name="to-display-the-selected-parameter-value-and-label-on-a-page-footer"></a><span data-ttu-id="d58b0-288">Pour afficher la valeur du paramètre sélectionné et son étiquette dans un pied de page</span><span class="sxs-lookup"><span data-stu-id="d58b0-288">To display the selected parameter value and label on a page footer</span></span>  
  
1.  <span data-ttu-id="d58b0-289">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="d58b0-289">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="d58b0-290">Cliquez avec le bouton droit sur le pied de page, pointez sur **Insérer**, puis cliquez sur **zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-290">Right-click the page footer, point to **Insert**, and then click **Text Box**.</span></span> <span data-ttu-id="d58b0-291">Faites glisser la zone de texte en regard de la zone de texte comportant l'horodatage.</span><span class="sxs-lookup"><span data-stu-id="d58b0-291">Drag the text box next to the text box with the time stamp.</span></span> <span data-ttu-id="d58b0-292">Saisissez la poignée latérale de la zone de texte et augmentez la largeur de cette dernière.</span><span class="sxs-lookup"><span data-stu-id="d58b0-292">Grab the side handle of the text box and expand the width.</span></span>  
  
3.  <span data-ttu-id="d58b0-293">À partir du volet données du rapport, faites glisser le paramètre *@StoreID* vers la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="d58b0-293">From the Report Data pane, drag the parameter *@StoreID* to the text box.</span></span> <span data-ttu-id="d58b0-294">La zone de texte affiche `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="d58b0-294">The text box displays `[@StoreID]`.</span></span>  
  
4.  <span data-ttu-id="d58b0-295">Pour afficher l'étiquette de paramètre, cliquez dans la zone de texte jusqu'à ce que le curseur d'insertion s'affiche après l'expression existante, tapez un espace, puis faites glisser une autre copie du paramètre du volet des données de rapport vers la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="d58b0-295">To display the parameter label, click in the text box until the insert cursor appears after the existing expression, type a space, and then drag another copy of the parameter from the Report Data pane to the text box.</span></span> <span data-ttu-id="d58b0-296">La zone de texte affiche `[@StoreID] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="d58b0-296">The text box displays `[@StoreID] [@StoreID]`.</span></span>  
  
5.  <span data-ttu-id="d58b0-297">Cliquez avec le bouton droit sur la première expression, puis cliquez sur **expression**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-297">Right-click the first expression and click **Expression**.</span></span> <span data-ttu-id="d58b0-298">La boîte de dialogue **Expression** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="d58b0-298">The **Expression** dialog box opens.</span></span> <span data-ttu-id="d58b0-299">Remplacez le texte `Value` par `Label`.</span><span class="sxs-lookup"><span data-stu-id="d58b0-299">Replace the text `Value` by `Label`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="d58b0-300">Le texte affiche : `[@StoreID.Label] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="d58b0-300">The text displays: `[@StoreID.Label] [@StoreID]`.</span></span>  
  
7.  <span data-ttu-id="d58b0-301">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-301">Preview the report.</span></span>  
  
##  <a name="6-use-the-report-parameter-in-a-filter"></a><a name="Filter"></a><span data-ttu-id="d58b0-302">6. utiliser le paramètre de rapport dans un filtre</span><span class="sxs-lookup"><span data-stu-id="d58b0-302">6. Use the Report Parameter in a Filter</span></span>  
 <span data-ttu-id="d58b0-303">Les filtres permettent de contrôler les données à utiliser dans un rapport une fois qu'il a été récupéré à partir d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d58b0-303">Filters help control which data to use in a report after it is retrieved from an external data source.</span></span> <span data-ttu-id="d58b0-304">Pour fournir à un utilisateur la possibilité de contrôler les données qu'il souhaite afficher, vous pouvez inclure le paramètre de rapport dans un filtre pour la matrice.</span><span class="sxs-lookup"><span data-stu-id="d58b0-304">To let a user help control the data they want to see, you can include the report parameter in a filter for the matrix.</span></span>  
  
#### <a name="to-specify-a-parameter-in-a-matrix-filter"></a><span data-ttu-id="d58b0-305">Pour spécifier un paramètre dans un filtre de matrice</span><span class="sxs-lookup"><span data-stu-id="d58b0-305">To specify a parameter in a matrix filter</span></span>  
  
1.  <span data-ttu-id="d58b0-306">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="d58b0-306">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="d58b0-307">Cliquez avec le bouton droit sur une ligne ou un descripteur d’en-tête de colonne dans la matrice, puis cliquez sur **Propriétés du tableau matriciel**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-307">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="d58b0-308">Cliquez sur **Filtres**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-308">Click **Filters**, and then click **Add**.</span></span> <span data-ttu-id="d58b0-309">Une nouvelle ligne de filtres apparaît.</span><span class="sxs-lookup"><span data-stu-id="d58b0-309">A new filter row appears.</span></span>  
  
4.  <span data-ttu-id="d58b0-310">Dans la liste déroulante **Expression**,, sélectionnez le champ de dataset StoreID.</span><span class="sxs-lookup"><span data-stu-id="d58b0-310">In **Expression**, from the drop-down list, select the dataset field StoreID.</span></span> <span data-ttu-id="d58b0-311">Le type de données affiche **Entier**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-311">The data type displays **Integer**.</span></span> <span data-ttu-id="d58b0-312">Lorsque la valeur d'expression est un champ de dataset, le type de données est défini automatiquement.</span><span class="sxs-lookup"><span data-stu-id="d58b0-312">When the expression value is a dataset field, the data type is set automatically.</span></span>  
  
5.  <span data-ttu-id="d58b0-313">Dans **opérateur**, vérifiez que `equals` (=) est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d58b0-313">In **Operator**, verify that `equals` (=) is selected.</span></span>  
  
6.  <span data-ttu-id="d58b0-314">Dans la zone **Valeur**, tapez `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="d58b0-314">In **Value**, type `[@StoreID]`.</span></span> <span data-ttu-id="d58b0-315">`[@StoreID]` est la syntaxe d’expression simple qui représente `=Parameters!StoreID.Value`.</span><span class="sxs-lookup"><span data-stu-id="d58b0-315">`[@StoreID]` is the simple expression syntax that represents `=Parameters!StoreID.Value`.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="d58b0-316">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-316">Preview the report.</span></span>  
  
     <span data-ttu-id="d58b0-317">La matrice affiche des données uniquement pour « Contoso Catalog Store ».</span><span class="sxs-lookup"><span data-stu-id="d58b0-317">The matrix displays data only for "Contoso Catalog Store".</span></span>  
  
9. <span data-ttu-id="d58b0-318">Dans la barre d’outils de la visionneuse de rapports, pour **Nom du magasin ?**, sélectionnez **Contoso Asia Online Store**, puis cliquez sur **Afficher le rapport**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-318">On the report viewer toolbar, for **Store name?**, select **Contoso Asia Online Store**, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="d58b0-319">La matrice affiche les données qui correspondent au magasin que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d58b0-319">The matrix displays data that corresponds to the store that you selected.</span></span>  
  
##  <a name="7-change-the-report-parameter-to-accept-multiple-values"></a><a name="Multivalued"></a><span data-ttu-id="d58b0-320">7. modifier le paramètre de rapport pour accepter plusieurs valeurs</span><span class="sxs-lookup"><span data-stu-id="d58b0-320">7. Change the Report Parameter to Accept Multiple Values</span></span>  
 <span data-ttu-id="d58b0-321">Pour changer un paramètre à valeur unique en paramètre à valeurs multiples, vous devez modifier la requête, ainsi que toutes les expressions qui contiennent une référence au paramètre, notamment les filtres.</span><span class="sxs-lookup"><span data-stu-id="d58b0-321">To change a parameter from single to multivalued, you must change the query, and all expressions that contain a reference to the parameter, including filters.</span></span> <span data-ttu-id="d58b0-322">Un paramètre à valeurs multiples est un tableau de valeurs.</span><span class="sxs-lookup"><span data-stu-id="d58b0-322">A multivalued parameter is an array of values.</span></span> <span data-ttu-id="d58b0-323">Dans une requête de dataset, la syntaxe de requête doit tester l'inclusion d'une valeur dans un ensemble de valeurs.</span><span class="sxs-lookup"><span data-stu-id="d58b0-323">In a dataset query, query syntax must test for inclusion of one value in a set of values.</span></span> <span data-ttu-id="d58b0-324">Dans une expression de rapport, la syntaxe d'expression doit accéder à un tableau de valeurs au lieu d'une valeur individuelle.</span><span class="sxs-lookup"><span data-stu-id="d58b0-324">In a report expression, expression syntax must access an array of values instead of an individual value.</span></span>  
  
#### <a name="to-change-a-parameter-from-single-to-multivalued"></a><span data-ttu-id="d58b0-325">Pour changer un paramètre à valeur unique en paramètre à valeurs multiples</span><span class="sxs-lookup"><span data-stu-id="d58b0-325">To change a parameter from single to multivalued</span></span>  
  
1.  <span data-ttu-id="d58b0-326">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="d58b0-326">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="d58b0-327">Dans le volet des données de rapport, cliquez avec le bouton droit sur *@StoreID* , puis cliquez sur **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-327">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="d58b0-328">Sélectionnez **Autoriser les valeurs multiples**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-328">Select **Allow multiple values**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="d58b0-329">Dans le volet des données de rapport, développez le dossier **Datasets** , cliquez avec le bouton droit sur **DataSet1**, puis cliquez sur **Requête**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-329">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
6.  <span data-ttu-id="d58b0-330">Remplacez `equals` (=) par `IN` dans la [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause de la dernière ligne de la requête :</span><span class="sxs-lookup"><span data-stu-id="d58b0-330">Change `equals` (=) to `IN` in the [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause in the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID IN (@StoreID)  
    ```  
  
     <span data-ttu-id="d58b0-331">L'opérateur `IN` teste l'inclusion d'une valeur dans un ensemble de valeurs.</span><span class="sxs-lookup"><span data-stu-id="d58b0-331">The `IN` operator tests a value for inclusion in a set of values.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="d58b0-332">Cliquez avec le bouton droit sur une ligne ou un descripteur d’en-tête de colonne dans la matrice, puis cliquez sur **Propriétés du tableau matriciel**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-332">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
9. <span data-ttu-id="d58b0-333">Cliquez sur **Filtres**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-333">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="d58b0-334">Dans **Opérateur**, sélectionnez **In**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-334">In **Operator**, select **In**.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="d58b0-335">Dans la zone de texte qui affiche le paramètre au sein du pied de page, supprimez l'ensemble du texte.</span><span class="sxs-lookup"><span data-stu-id="d58b0-335">In the text box that displays the parameter in the page footer, delete all text.</span></span>  
  
13. <span data-ttu-id="d58b0-336">Cliquez avec le bouton droit sur la zone de texte, puis cliquez sur **Expression**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-336">Right-click the text box, and then click **Expression**.</span></span> <span data-ttu-id="d58b0-337">Tapez l’expression suivante : `=Join(Parameters!StoreID.Label, ", ")`</span><span class="sxs-lookup"><span data-stu-id="d58b0-337">Type the following expression: `=Join(Parameters!StoreID.Label, ", ")`</span></span>  
  
     <span data-ttu-id="d58b0-338">Cette expression concatène tous les noms de magasins que l'utilisateur a sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="d58b0-338">This expression concatenates all store names that the user selected.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
15. <span data-ttu-id="d58b0-339">Cliquez dans la zone de texte devant l'expression que vous venez de créer, puis tapez ce qui suit : Valeurs de paramètres sélectionnées :.</span><span class="sxs-lookup"><span data-stu-id="d58b0-339">Click in the text box in front of the expression that you just created, and then type the following: Parameter Values Selected:.</span></span>  
  
16. <span data-ttu-id="d58b0-340">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-340">Preview the report.</span></span>  
  
17. <span data-ttu-id="d58b0-341">Cliquez sur la liste déroulante en regard de Nom du magasin ?</span><span class="sxs-lookup"><span data-stu-id="d58b0-341">Click the drop-down list next to Store Name?</span></span>  
  
     <span data-ttu-id="d58b0-342">Chaque valeur valide s'affiche en regard d'une case à cocher.</span><span class="sxs-lookup"><span data-stu-id="d58b0-342">Each valid value appears next to a check box.</span></span>  
  
18. <span data-ttu-id="d58b0-343">Cliquez sur **Sélectionner tout**, puis sur **Afficher le rapport**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-343">Click **Select All**, and then click **View Report**.</span></span>  
  
     <span data-ttu-id="d58b0-344">Le rapport affiche les quantités vendues pour toutes les sous-catégories de tous les magasins.</span><span class="sxs-lookup"><span data-stu-id="d58b0-344">The report displays the quantity sold for all subcategories for all stores.</span></span>  
  
19. <span data-ttu-id="d58b0-345">Dans la liste déroulante, cliquez sur **Sélectionner tout** afin d’effacer la liste, cliquez sur « Contoso Catalog Store » et sur « Contoso Asia Online Store », puis cliquez sur **Afficher le rapport**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-345">From the drop-down list, click **Select All** to clear the list, click "Contoso Catalog Store" and "Contoso Asia Online Store", and then click **View Report**.</span></span>  
  
##  <a name="8-add-a-boolean-parameter-for-conditional-visibility"></a><a name="Boolean"></a><span data-ttu-id="d58b0-346">8. Ajouter un paramètre booléen pour la visibilité conditionnelle</span><span class="sxs-lookup"><span data-stu-id="d58b0-346">8. Add a Boolean Parameter for Conditional Visibility</span></span>  
  
#### <a name="to-add-a-boolean-parameter"></a><span data-ttu-id="d58b0-347">Pour ajouter un paramètre booléen</span><span class="sxs-lookup"><span data-stu-id="d58b0-347">To add a boolean parameter</span></span>  
  
1.  <span data-ttu-id="d58b0-348">Dans l’aire de conception, dans le volet des données de rapport, cliquez avec le bouton droit sur **Paramètres**, puis cliquez sur **Add Ajouter un paramètre**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-348">On the design surface, in the Report Data pane, right-click **Parameters**, and click **Add Parameter**.</span></span>  
  
2.  <span data-ttu-id="d58b0-349">Dans la zone **Nom**, tapez ShowSelections.</span><span class="sxs-lookup"><span data-stu-id="d58b0-349">In **Name**, type ShowSelections.</span></span>  
  
3.  <span data-ttu-id="d58b0-350">Dans **Invite**, tapez Afficher les sélections ?</span><span class="sxs-lookup"><span data-stu-id="d58b0-350">In **Prompt**, type Show selections?</span></span>  
  
4.  <span data-ttu-id="d58b0-351">Dans **type de données**, dans la liste déroulante, cliquez sur **booléen**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-351">In **Data type**, from the drop-down list, click **Boolean**.</span></span>  
  
5.  <span data-ttu-id="d58b0-352">Cliquez sur **Valeurs par défaut**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-352">Click **Default Values**.</span></span>  
  
6.  <span data-ttu-id="d58b0-353">Cliquez sur **Spécifier les valeurs**, puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-353">Click **Specify value**, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="d58b0-354">Dans la zone **Valeur**, tapez **False**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-354">In **Value**, type **False**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-set-visibility-based-on-a-boolean-parameter"></a><span data-ttu-id="d58b0-355">Pour définir la visibilité en fonction d'un paramètre booléen</span><span class="sxs-lookup"><span data-stu-id="d58b0-355">To set visibility based on a boolean parameter</span></span>  
  
1.  <span data-ttu-id="d58b0-356">Dans l’aire de conception, cliquez avec le bouton droit sur la zone de texte du pied de page qui affiche les valeurs de paramètres, puis cliquez sur **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-356">On the design surface, right-click the text box in the page footer that displays the parameter values, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="d58b0-357">Cliquez sur **Visibilité**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-357">Click **Visibility**.</span></span>  
  
3.  <span data-ttu-id="d58b0-358">Sélectionnez l’option **Afficher ou masquer en fonction d’une expression**, puis cliquez sur le bouton Expression **Fx**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-358">Select the option **Show or hide based on an expression**, and then click the expression button **Fx**.</span></span>  
  
4.  <span data-ttu-id="d58b0-359">Tapez l’expression suivante : `=Not Parameters!ShowSelections.Value`</span><span class="sxs-lookup"><span data-stu-id="d58b0-359">Type the following expression: `=Not Parameters!ShowSelections.Value`</span></span>  
  
     <span data-ttu-id="d58b0-360">L'option de visibilité de la zone de texte est contrôlée par la propriété Hidden.</span><span class="sxs-lookup"><span data-stu-id="d58b0-360">The text box Visibility option is controlled by the property Hidden.</span></span> <span data-ttu-id="d58b0-361">Appliquez l'opérateur `Not` afin que lorsque le paramètre est sélectionné, la valeur False soit affectée à la propriété Hidden et que la zone de texte soit affichée.</span><span class="sxs-lookup"><span data-stu-id="d58b0-361">Apply the `Not` operator so that when the parameter is selected, the Hidden property is false, and the text box will be displayed.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="d58b0-362">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-362">Preview the report.</span></span>  
  
     <span data-ttu-id="d58b0-363">La zone de texte qui affiche les choix de paramètre ne s'affiche pas.</span><span class="sxs-lookup"><span data-stu-id="d58b0-363">The text box that displays the parameter choices does not appear.</span></span>  
  
8.  <span data-ttu-id="d58b0-364">Dans la barre d’outils de la visionneuse de rapports, en regard de **afficher les sélections**, cliquez sur `True` .</span><span class="sxs-lookup"><span data-stu-id="d58b0-364">In the report viewer toolbar, next to **Show selections**, click `True`.</span></span>  
  
9. <span data-ttu-id="d58b0-365">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-365">Preview the report.</span></span>  
  
 <span data-ttu-id="d58b0-366">La zone de texte située dans le pied de page affiche tous les noms de magasins que vous avez sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="d58b0-366">The text box in the page footer displays all the store names that you selected.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="d58b0-367">9. Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-367">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="d58b0-368">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-368">To add a report title</span></span>  
  
1.  <span data-ttu-id="d58b0-369">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-369">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="d58b0-370">Tapez Ventes de produits paramétrables, puis cliquez en dehors de la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="d58b0-370">Type Parameterized Product Sales, and then click outside the text box.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="d58b0-371">10. enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="d58b0-371">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="d58b0-372">Pour enregistrer le rapport sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="d58b0-372">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="d58b0-373">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-373">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="d58b0-374">Cliquez sur **Sites et serveurs récents**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-374">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="d58b0-375">Sélectionnez ou tapez le nom du serveur de rapports sur lequel vous êtes autorisé à enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="d58b0-375">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="d58b0-376">Le message **Connexion au serveur de rapports**s’affiche.</span><span class="sxs-lookup"><span data-stu-id="d58b0-376">The message **Connecting to report server appears**.</span></span> <span data-ttu-id="d58b0-377">Une fois la connexion établie, le contenu du dossier de rapports spécifié par l'administrateur du serveur de rapports s'affiche comme emplacement par défaut des rapports.</span><span class="sxs-lookup"><span data-stu-id="d58b0-377">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="d58b0-378">Dans la zone **Nom**, remplacez le nom par défaut par État des ventes paramétrable.</span><span class="sxs-lookup"><span data-stu-id="d58b0-378">In **Name**, replace the default name with Parameterized Sales Report.</span></span>  
  
5.  <span data-ttu-id="d58b0-379">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d58b0-379">Click **Save**.</span></span>  
  
 <span data-ttu-id="d58b0-380">Le rapport est enregistré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d58b0-380">The report is saved to the report server.</span></span> <span data-ttu-id="d58b0-381">Le serveur de rapports auquel vous êtes connecté est indiqué dans la barre d'état située au bas de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="d58b0-381">The report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d58b0-382">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="d58b0-382">Next Steps</span></span>  
 <span data-ttu-id="d58b0-383">Ceci conclut la procédure pas à pas décrivant comment ajouter un paramètre à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="d58b0-383">This concludes the walkthrough for how to add a parameter to your report.</span></span> <span data-ttu-id="d58b0-384">Pour en savoir plus sur les paramètres, consultez [Paramètres de rapport &#40;Générateur de rapports et Concepteur de rapports&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="d58b0-384">To learn more about parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d58b0-385">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d58b0-385">See Also</span></span>  
 <span data-ttu-id="d58b0-386">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="d58b0-386">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="d58b0-387">Générateur de rapports dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="d58b0-387">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
