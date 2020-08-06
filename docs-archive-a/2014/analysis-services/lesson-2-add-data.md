---
title: 'Leçon 2 : ajouter des données | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 13c3a8cc-b1db-4aba-ad9b-038b7971be8d
author: minewiskan
ms.author: owend
ms.openlocfilehash: c844ea6558949407ca9b8206601ff7fe802ec399
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603114"
---
# <a name="lesson-2-add-data"></a><span data-ttu-id="0470e-102">Leçon 2 : Ajouter des données</span><span class="sxs-lookup"><span data-stu-id="0470e-102">Lesson 2: Add Data</span></span>
  <span data-ttu-id="0470e-103">Dans cette leçon, vous allez utiliser l'Assistant Importation de table dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] pour vous connecter à la base de données SQL AdventureWorksDW, sélectionner des données, afficher un aperçu et filtrer les données, puis les importer dans votre espace de travail de modèle.</span><span class="sxs-lookup"><span data-stu-id="0470e-103">In this lesson, you will use the Table Import Wizard in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] to connect to the AdventureWorksDW SQL database, select data, preview, and filter the data, and then import the data into your model workspace.</span></span>  
  
 <span data-ttu-id="0470e-104">À l'aide de l'Assistant Importation de Table, vous pouvez importer des données provenant de diverses sources relationnelles : Access, SQL, Oracle, Sybase, Informix, DB2, Teradata et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="0470e-104">By using the Table Import Wizard, you can import data from a variety of relational sources: Access, SQL, Oracle, Sybase, Informix, DB2, Teradata, and more.</span></span> <span data-ttu-id="0470e-105">Les étapes d'importation de données à partir des différentes sources relationnelles sont très semblables à celles qui suivent.</span><span class="sxs-lookup"><span data-stu-id="0470e-105">The steps for importing data from each of these relational sources are very similar to what is described below.</span></span> <span data-ttu-id="0470e-106">En outre, les données peuvent être sélectionnées à l'aide d'une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="0470e-106">Additionally, data can be selected using a stored procedure.</span></span>  
  
 <span data-ttu-id="0470e-107">Pour en savoir plus sur l’importation de données et les différents types de sources de données que vous pouvez importer, consultez [Sources de données &#40;SSAS Tabulaire&#41;](data-sources-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="0470e-107">To learn more about importing data and the different types of data sources you can import from, see [Data Sources &#40;SSAS Tabular&#41;](data-sources-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="0470e-108">Durée estimée pour suivre cette leçon : **20 minutes**</span><span class="sxs-lookup"><span data-stu-id="0470e-108">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0470e-109">Prérequis</span><span class="sxs-lookup"><span data-stu-id="0470e-109">Prerequisites</span></span>  
 <span data-ttu-id="0470e-110">Cette rubrique fait partie d’un didacticiel de modélisation tabulaire, qui doit être suivi dans l’ordre prévu.</span><span class="sxs-lookup"><span data-stu-id="0470e-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="0470e-111">Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la leçon précédente : [leçon 1 : créer un projet de modèle tabulaire](lesson-1-create-a-new-tabular-model-project.md).</span><span class="sxs-lookup"><span data-stu-id="0470e-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 1: Create a New Tabular Model Project](lesson-1-create-a-new-tabular-model-project.md).</span></span>  
  
## <a name="create-a-connection"></a><span data-ttu-id="0470e-112">Créer une connexion</span><span class="sxs-lookup"><span data-stu-id="0470e-112">Create a Connection</span></span>  
  
#### <a name="to-create-a-connection-to-a-the-adventureworksdw2012-database"></a><span data-ttu-id="0470e-113">Pour créer une connexion à la base de données AdventureWorksDW2012</span><span class="sxs-lookup"><span data-stu-id="0470e-113">To create a connection to a the AdventureWorksDW2012 database</span></span>  
  
1.  <span data-ttu-id="0470e-114">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , puis sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="0470e-114">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
     <span data-ttu-id="0470e-115">Cela lance l'Assistant Importation de table qui vous guide à travers les étapes de configuration d'une connexion à une source de données.</span><span class="sxs-lookup"><span data-stu-id="0470e-115">This launches the Table Import Wizard which guides you through setting up a connection to a data source.</span></span> <span data-ttu-id="0470e-116">Si l'option **Importer à partir de la source de données** est grisée, double-cliquez sur **Model.bim** dans l' **Explorateur de solutions** pour ouvrir le modèle dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="0470e-116">If **Import from Data Source** is greyed out, double click **Model.bim** in **Solution Explorer** to open the model in the designer.</span></span>  
  
2.  <span data-ttu-id="0470e-117">Dans l' **Assistant Importation de table**, sous **Bases de données relationnelles**, cliquez sur **Microsoft SQL Server**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0470e-117">In the **Table Import Wizard**, under **Relational Databases**, click **Microsoft SQL Server**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="0470e-118">Dans la page **se connecter à une base de données Microsoft SQL Server** , dans **nom convivial**de la connexion, tapez `Adventure Works DB from SQL` .</span><span class="sxs-lookup"><span data-stu-id="0470e-118">In the **Connect to a Microsoft SQL Server Database** page, in **Friendly Connection Name**, type `Adventure Works DB from SQL`.</span></span>  
  
4.  <span data-ttu-id="0470e-119">Dans la zone **Nom du serveur**, tapez ou sélectionnez le nom du serveur sur lequel vous avez installé la base de données AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="0470e-119">In **Server name**, type the name of the server you installed the AdventureWorksDW database.</span></span>  
  
5.  <span data-ttu-id="0470e-120">Dans le champ **Nom de la base de données** , cliquez sur la flèche orientée vers le bas et sélectionnez **AdventureWorksDW**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0470e-120">In the **Database name** field, click the down arrow and select **AdventureWorksDW**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="0470e-121">Dans la page **Informations d'emprunt d'identité** , vous devez spécifier les informations d'identification qu'Analysis Services utilisera pour se connecter à la source de données lors de l'importation et du traitement des données.</span><span class="sxs-lookup"><span data-stu-id="0470e-121">In the **Impersonation Information** page, you need to specify the credentials Analysis Services will use to connect to the data source when importing and processing data.</span></span> <span data-ttu-id="0470e-122">Vérifiez que l'option **Nom d'utilisateur et mot de passe Windows spécifiques** est sélectionnée, puis, dans **Nom d'utilisateur** et **Mot de passe**, entrez vos informations d'identification de connexion Windows, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0470e-122">Verify **Specific Windows user name and password** is selected, and then in **User Name** and **Password**, enter your Windows logon credentials, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0470e-123">L'utilisation d'un compte d'utilisateur et d'un mot de passe Windows est la méthode la plus sûre pour se connecter à une source de données.</span><span class="sxs-lookup"><span data-stu-id="0470e-123">Using a Windows user account and password provides the most secure method of connecting to a data source.</span></span> <span data-ttu-id="0470e-124">Pour plus d’informations, consultez [Emprunt d’identité &#40;SSAS Tabulaire&#41;](tabular-models/impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="0470e-124">For more information, see [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span></span>  
  
7.  <span data-ttu-id="0470e-125">Dans la page **Choisir comment importer les données** , vérifiez que l'option **Sélectionner les données à importer dans une liste de tables et de vues** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0470e-125">In the **Choose How to Import the Data** page, verify **Select from a list of tables and views to choose the data to import** is selected.</span></span> <span data-ttu-id="0470e-126">Vous souhaitez choisir dans une liste de tables et de vues et vous devez donc cliquer sur **Suivant** pour afficher la liste de toutes les tables sources dans la base de données source.</span><span class="sxs-lookup"><span data-stu-id="0470e-126">You want to select from a list of tables and views, so click **Next** to display a list of all the source tables in the source database.</span></span>  
  
8.  <span data-ttu-id="0470e-127">Dans la page **Sélectionner des Tables et des vues** , activez la case à cocher pour les tables suivantes : **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**et **FactInternetSales**.</span><span class="sxs-lookup"><span data-stu-id="0470e-127">In the **Select Tables and Views** page, select the check box for the following tables: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**, and **FactInternetSales**.</span></span>  
  
9. <span data-ttu-id="0470e-128">Nous souhaitons donner aux tables du modèle des noms plus facilement compréhensibles.</span><span class="sxs-lookup"><span data-stu-id="0470e-128">We want to give the tables in the model more easily understood names.</span></span> <span data-ttu-id="0470e-129">Cliquez sur la cellule dans la colonne **Nom convivial** pour **DimCustomer**.</span><span class="sxs-lookup"><span data-stu-id="0470e-129">Click on the cell in the **Friendly Name** column for **DimCustomer**.</span></span> <span data-ttu-id="0470e-130">Renommez la table en supprimant « Dim » de DimCustomer.</span><span class="sxs-lookup"><span data-stu-id="0470e-130">Rename the table by removing "Dim" from DimCustomer.</span></span>  
  
10. <span data-ttu-id="0470e-131">Renommez les autres tables :</span><span class="sxs-lookup"><span data-stu-id="0470e-131">Rename the other tables:</span></span>  
  
    |<span data-ttu-id="0470e-132">Nom de la source</span><span class="sxs-lookup"><span data-stu-id="0470e-132">Source name</span></span>|<span data-ttu-id="0470e-133">Nom convivial</span><span class="sxs-lookup"><span data-stu-id="0470e-133">Friendly Name</span></span>|  
    |-----------------|-------------------|  
    |<span data-ttu-id="0470e-134">DimDate</span><span class="sxs-lookup"><span data-stu-id="0470e-134">DimDate</span></span>|<span data-ttu-id="0470e-135">Date</span><span class="sxs-lookup"><span data-stu-id="0470e-135">Date</span></span>|  
    |<span data-ttu-id="0470e-136">DimGeography</span><span class="sxs-lookup"><span data-stu-id="0470e-136">DimGeography</span></span>|<span data-ttu-id="0470e-137">Geography</span><span class="sxs-lookup"><span data-stu-id="0470e-137">Geography</span></span>|  
    |<span data-ttu-id="0470e-138">DimProduct</span><span class="sxs-lookup"><span data-stu-id="0470e-138">DimProduct</span></span>|<span data-ttu-id="0470e-139">Produit</span><span class="sxs-lookup"><span data-stu-id="0470e-139">Product</span></span>|  
    |<span data-ttu-id="0470e-140">DimProductCategory</span><span class="sxs-lookup"><span data-stu-id="0470e-140">DimProductCategory</span></span>|<span data-ttu-id="0470e-141">Catégorie de produit</span><span class="sxs-lookup"><span data-stu-id="0470e-141">Product Category</span></span>|  
    |<span data-ttu-id="0470e-142">DimProductSubcategory</span><span class="sxs-lookup"><span data-stu-id="0470e-142">DimProductSubcategory</span></span>|<span data-ttu-id="0470e-143">Product Subcategory</span><span class="sxs-lookup"><span data-stu-id="0470e-143">Product Subcategory</span></span>|  
    |<span data-ttu-id="0470e-144">FactInternetSales</span><span class="sxs-lookup"><span data-stu-id="0470e-144">FactInternetSales</span></span>|<span data-ttu-id="0470e-145">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="0470e-145">Internet Sales</span></span>|  
  
     <span data-ttu-id="0470e-146">**NE CLIQUEZ PAS** sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="0470e-146">**DO NOT** click **Finish**.</span></span>  
  
 <span data-ttu-id="0470e-147">Maintenant que vous êtes connecté à la base de données, que vous avez sélectionné les tables à importer et que vous leur avez attribué un nom convivial, passez directement à la section suivante intitulée [Filtrer les données de table avant l'importation](#FilterData).</span><span class="sxs-lookup"><span data-stu-id="0470e-147">Now that you have connected to the database, selected the tables to import, and given the tables friendly names, go to the next section, [Filter the Table Data prior to Importing](#FilterData).</span></span>  
  
##  <a name="filter-the-table-data"></a><a name="FilterData"></a><span data-ttu-id="0470e-148">Filtrer les données de la table</span><span class="sxs-lookup"><span data-stu-id="0470e-148">Filter the Table Data</span></span>  
 <span data-ttu-id="0470e-149">La table DimCustomer que vous importez de la base de données contient un sous-ensemble des données de la base de données d'origine SQL Server Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="0470e-149">The DimCustomer table that you are importing from the database contains a subset of the data from the original SQL Server Adventure Works database.</span></span> <span data-ttu-id="0470e-150">Vous allez filtrer les colonnes de la table DimCustomer qui ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="0470e-150">You will filter out some of the columns from the DimCustomer table that aren't necessary.</span></span> <span data-ttu-id="0470e-151">Lorsque cela est possible, filtrez les données qui ne seront pas utilisées afin d'économiser l'espace en mémoire utilisé par le modèle.</span><span class="sxs-lookup"><span data-stu-id="0470e-151">When possible, you will want to filter out data that will not be used in order to save in-memory space used by the model.</span></span>  
  
#### <a name="to-filter-the-table-data-prior-to-importing"></a><span data-ttu-id="0470e-152">Pour filtrer les données de table avant l'importation</span><span class="sxs-lookup"><span data-stu-id="0470e-152">To filter the table data prior to importing</span></span>  
  
1.  <span data-ttu-id="0470e-153">Sélectionnez la ligne correspondant à la table **Customer**, puis cliquez sur **Afficher un aperçu et filtrer**.</span><span class="sxs-lookup"><span data-stu-id="0470e-153">Select the row for the **Customer** table, and then click **Preview & Filter**.</span></span> <span data-ttu-id="0470e-154">La fenêtre **Aperçu de la table sélectionnée** s'affiche en présentant toutes les colonnes de la table source DimCustomer.</span><span class="sxs-lookup"><span data-stu-id="0470e-154">The **Preview Selected Table** window opens with all the columns in the DimCustomer source table displayed.</span></span>  
  
2.  <span data-ttu-id="0470e-155">Désactivez la case à cocher en haut des colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0470e-155">Clear the checkbox at the top of the following columns:</span></span>  
  
    |<span data-ttu-id="0470e-156">Customer</span><span class="sxs-lookup"><span data-stu-id="0470e-156">Customer</span></span>|  
    |--------------|  
    |<span data-ttu-id="0470e-157">**SpanishEducation**</span><span class="sxs-lookup"><span data-stu-id="0470e-157">**SpanishEducation**</span></span>|  
    |<span data-ttu-id="0470e-158">**FrenchEducation**</span><span class="sxs-lookup"><span data-stu-id="0470e-158">**FrenchEducation**</span></span>|  
    |<span data-ttu-id="0470e-159">**SpanishOccupation**</span><span class="sxs-lookup"><span data-stu-id="0470e-159">**SpanishOccupation**</span></span>|  
    |<span data-ttu-id="0470e-160">**FrenchOccupation**</span><span class="sxs-lookup"><span data-stu-id="0470e-160">**FrenchOccupation**</span></span>|  
  
     <span data-ttu-id="0470e-161">Étant donné que les valeurs de ces colonnes ne sont pas appropriées à l'analyse des ventes sur Internet, il est inutile de les importer.</span><span class="sxs-lookup"><span data-stu-id="0470e-161">Since the values for these columns are not relevant to Internet sales analysis, there is no need to import these columns.</span></span> <span data-ttu-id="0470e-162">Éliminer les colonnes inutiles réduira la taille de votre modèle.</span><span class="sxs-lookup"><span data-stu-id="0470e-162">Eliminating unnecessary columns will make your model smaller.</span></span>  
  
3.  <span data-ttu-id="0470e-163">Vérifiez que toutes les autres colonnes sont cochées, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0470e-163">Verify that all other columns are checked, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0470e-164">Notez que les mots **filtres appliqués** s’affichent maintenant dans la colonne **Détails du filtre** de la ligne **client** . Si vous cliquez sur ce lien, vous verrez une description textuelle des filtres que vous venez d’appliquer.</span><span class="sxs-lookup"><span data-stu-id="0470e-164">Notice the words **Applied filters** are now displayed in the **Filter Details** column in the **Customer** row; if you click on that link you'll see a text description of the filters you just applied.</span></span>  
  
4.  <span data-ttu-id="0470e-165">Filtrez les autres tables en désactivant les cases à cocher des colonnes suivantes dans chaque table :</span><span class="sxs-lookup"><span data-stu-id="0470e-165">Filter the remaining tables by clearing the checkboxes for the following columns in each table:</span></span>  
  
    |<span data-ttu-id="0470e-166">Date</span><span class="sxs-lookup"><span data-stu-id="0470e-166">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="0470e-167">**DateKey**</span><span class="sxs-lookup"><span data-stu-id="0470e-167">**DateKey**</span></span>|  
    |<span data-ttu-id="0470e-168">**SpanishDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="0470e-168">**SpanishDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="0470e-169">**FrenchDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="0470e-169">**FrenchDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="0470e-170">**SpanishMonthName**</span><span class="sxs-lookup"><span data-stu-id="0470e-170">**SpanishMonthName**</span></span>|  
    |<span data-ttu-id="0470e-171">**FrenchMonthName**</span><span class="sxs-lookup"><span data-stu-id="0470e-171">**FrenchMonthName**</span></span>|  
  
    |<span data-ttu-id="0470e-172">Geography</span><span class="sxs-lookup"><span data-stu-id="0470e-172">Geography</span></span>|  
    |---------------|  
    |<span data-ttu-id="0470e-173">**SpanishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="0470e-173">**SpanishCountryRegionName**</span></span>|  
    |<span data-ttu-id="0470e-174">**FrenchCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="0470e-174">**FrenchCountryRegionName**</span></span>|  
    |<span data-ttu-id="0470e-175">**IpAddressLocator**</span><span class="sxs-lookup"><span data-stu-id="0470e-175">**IpAddressLocator**</span></span>|  
  
    |<span data-ttu-id="0470e-176">Produit</span><span class="sxs-lookup"><span data-stu-id="0470e-176">Product</span></span>|  
    |-------------|  
    |<span data-ttu-id="0470e-177">**SpanishProductName**</span><span class="sxs-lookup"><span data-stu-id="0470e-177">**SpanishProductName**</span></span>|  
    |<span data-ttu-id="0470e-178">**FrenchProductName**</span><span class="sxs-lookup"><span data-stu-id="0470e-178">**FrenchProductName**</span></span>|  
    |<span data-ttu-id="0470e-179">**FrenchDescription**</span><span class="sxs-lookup"><span data-stu-id="0470e-179">**FrenchDescription**</span></span>|  
    |<span data-ttu-id="0470e-180">**ChineseDescription**</span><span class="sxs-lookup"><span data-stu-id="0470e-180">**ChineseDescription**</span></span>|  
    |<span data-ttu-id="0470e-181">**ArabicDescription**</span><span class="sxs-lookup"><span data-stu-id="0470e-181">**ArabicDescription**</span></span>|  
    |<span data-ttu-id="0470e-182">**HebrewDescription**</span><span class="sxs-lookup"><span data-stu-id="0470e-182">**HebrewDescription**</span></span>|  
    |<span data-ttu-id="0470e-183">**ThaiDescription**</span><span class="sxs-lookup"><span data-stu-id="0470e-183">**ThaiDescription**</span></span>|  
    |<span data-ttu-id="0470e-184">**GermanDescription**</span><span class="sxs-lookup"><span data-stu-id="0470e-184">**GermanDescription**</span></span>|  
    |<span data-ttu-id="0470e-185">**JapaneseDescription**</span><span class="sxs-lookup"><span data-stu-id="0470e-185">**JapaneseDescription**</span></span>|  
    |<span data-ttu-id="0470e-186">**TurkishDescription**</span><span class="sxs-lookup"><span data-stu-id="0470e-186">**TurkishDescription**</span></span>|  
  
    |<span data-ttu-id="0470e-187">Catégorie de produit</span><span class="sxs-lookup"><span data-stu-id="0470e-187">Product Category</span></span>|  
    |----------------------|  
    |<span data-ttu-id="0470e-188">**SpanishProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="0470e-188">**SpanishProductCategoryName**</span></span>|  
    |<span data-ttu-id="0470e-189">**FrenchProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="0470e-189">**FrenchProductCategoryName**</span></span>|  
  
    |<span data-ttu-id="0470e-190">Product Subcategory</span><span class="sxs-lookup"><span data-stu-id="0470e-190">Product Subcategory</span></span>|  
    |-------------------------|  
    |<span data-ttu-id="0470e-191">**SpanishProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="0470e-191">**SpanishProductSubcategoryName**</span></span>|  
    |<span data-ttu-id="0470e-192">**FrenchProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="0470e-192">**FrenchProductSubcategoryName**</span></span>|  
  
    |<span data-ttu-id="0470e-193">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="0470e-193">Internet Sales</span></span>|  
    |--------------------|  
    |<span data-ttu-id="0470e-194">**OrderDateKey**</span><span class="sxs-lookup"><span data-stu-id="0470e-194">**OrderDateKey**</span></span>|  
    |<span data-ttu-id="0470e-195">**DueDateKey**</span><span class="sxs-lookup"><span data-stu-id="0470e-195">**DueDateKey**</span></span>|  
    |<span data-ttu-id="0470e-196">**ShipDateKey**</span><span class="sxs-lookup"><span data-stu-id="0470e-196">**ShipDateKey**</span></span>|  
  
 <span data-ttu-id="0470e-197">Maintenant que vous avez prévisualisé et filtré les données inutiles, vous pouvez importer les données.</span><span class="sxs-lookup"><span data-stu-id="0470e-197">Now that you have previewed and filtered out unnecessary data, you can import the data.</span></span> <span data-ttu-id="0470e-198">Allez à la section suivante **Importer les tables et les données de colonne sélectionnées**.</span><span class="sxs-lookup"><span data-stu-id="0470e-198">Go to the next section **Import the Selected Tables and Column Data**.</span></span>  
  
##  <a name="import-the-selected-tables-and-column-data"></a><a name="Import"></a><span data-ttu-id="0470e-199">Importer les tables et les données de colonne sélectionnées</span><span class="sxs-lookup"><span data-stu-id="0470e-199">Import the Selected Tables and Column Data</span></span>  
 <span data-ttu-id="0470e-200">Vous pouvez maintenant importer les données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="0470e-200">You can now import the selected data.</span></span> <span data-ttu-id="0470e-201">L'Assistant importe les données de la table avec toutes les relations entre les tables.</span><span class="sxs-lookup"><span data-stu-id="0470e-201">The wizard imports the table data along with any relationships between tables.</span></span> <span data-ttu-id="0470e-202">De nouvelles tables et colonnes sont créées dans le modèle en utilisant les noms conviviaux spécifiés, et les données filtrées ne seront pas importées.</span><span class="sxs-lookup"><span data-stu-id="0470e-202">New tables and columns are created in the model using the friendly names you specified, and data that you filtered out will not be imported.</span></span>  
  
#### <a name="to-import-the-selected-tables-and-column-data"></a><span data-ttu-id="0470e-203">Pour importer les tables et les données de colonne sélectionnées</span><span class="sxs-lookup"><span data-stu-id="0470e-203">To import the selected tables and column data</span></span>  
  
1.  <span data-ttu-id="0470e-204">Passez en revue vos sélections.</span><span class="sxs-lookup"><span data-stu-id="0470e-204">Review your selections.</span></span> <span data-ttu-id="0470e-205">Si tout semble OK, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="0470e-205">If everything looks OK, click **Finish**.</span></span>  
  
     <span data-ttu-id="0470e-206">Pendant l'importation des données, l'Assistant affiche le nombre de lignes qui ont été extraites.</span><span class="sxs-lookup"><span data-stu-id="0470e-206">While importing the data, the wizard displays how many rows have been fetched.</span></span> <span data-ttu-id="0470e-207">Lorsque toutes les données ont été importées, un message de réussite s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0470e-207">When all the data has been imported, a message indicating success is displayed.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="0470e-208"> Pour afficher les relations qui ont été créées automatiquement entre les tables importées, sur la ligne **Préparation des données** , cliquez sur **Détails**.</span><span class="sxs-lookup"><span data-stu-id="0470e-208">To see the relationships that were automatically created between the imported tables, on the **Data preparation** row, click **Details**.</span></span>  
  
2.  <span data-ttu-id="0470e-209">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="0470e-209">Click **Close**.</span></span>  
  
     <span data-ttu-id="0470e-210">L'Assistant se ferme et le concepteur de modèles est visible.</span><span class="sxs-lookup"><span data-stu-id="0470e-210">The wizard closes and the model designer is visible.</span></span> <span data-ttu-id="0470e-211">Chaque table a été ajoutée en tant que nouvel onglet du concepteur de modèles.</span><span class="sxs-lookup"><span data-stu-id="0470e-211">Each table has been added as a new tab in the model designer.</span></span>  
  
## <a name="save-the-model-project"></a><span data-ttu-id="0470e-212">Enregistrer le projet de modèle</span><span class="sxs-lookup"><span data-stu-id="0470e-212">Save the Model Project</span></span>  
 <span data-ttu-id="0470e-213">Il est important de sauvegarder fréquemment votre projet de modèle.</span><span class="sxs-lookup"><span data-stu-id="0470e-213">It is important to frequently save your model project.</span></span>  
  
#### <a name="to-save-the-model-project"></a><span data-ttu-id="0470e-214">Pour enregistrer votre projet de modèle</span><span class="sxs-lookup"><span data-stu-id="0470e-214">To save the model project</span></span>  
  
-   <span data-ttu-id="0470e-215">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur le menu **Fichier** , puis cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="0470e-215">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **File** menu, and then click **Save All**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="0470e-216">étape suivante</span><span class="sxs-lookup"><span data-stu-id="0470e-216">Next Step</span></span>  
 <span data-ttu-id="0470e-217">Pour poursuivre l’étude de ce didacticiel, passez à la [Leçon 3 : Renommer des colonnes](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="0470e-217">To continue this tutorial, go to the next lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
  
