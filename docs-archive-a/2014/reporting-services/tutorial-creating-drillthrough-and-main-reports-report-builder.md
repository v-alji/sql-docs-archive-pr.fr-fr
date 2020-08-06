---
title: 'Didacticiel : création d’un rapport principal et d’un rapport d’extraction (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7168c8d3-cef5-4c4a-a0bf-fff1ac5b8b71
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7d30b59a0c5523ed50df06f8587bbd701ae4c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706115"
---
# <a name="tutorial-creating-drillthrough-and-main-reports-report-builder"></a><span data-ttu-id="c4024-102">Didacticiel : création d'un rapport principal et d'un rapport d'extraction (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="c4024-102">Tutorial: Creating Drillthrough and Main Reports (Report Builder)</span></span>
  <span data-ttu-id="c4024-103">Ce didacticiel vous apprend comment créer deux types de rapports : un rapport d'extraction et un rapport principal.</span><span class="sxs-lookup"><span data-stu-id="c4024-103">This tutorial teaches you how to create two kinds of reports: a drillthrough report and a main report.</span></span> <span data-ttu-id="c4024-104">Les exemples de données de ventes utilisés dans ces rapports sont récupérés d'un cube Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c4024-104">The sample sales data used in these reports is retrieved from an Analysis Services cube.</span></span> <span data-ttu-id="c4024-105">L'illustration suivante montre les rapports que vous allez créer.</span><span class="sxs-lookup"><span data-stu-id="c4024-105">The following illustration shows the reports you will create.</span></span>  
  
 <span data-ttu-id="c4024-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span><span class="sxs-lookup"><span data-stu-id="c4024-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span></span>  
  
 <span data-ttu-id="c4024-107">L’illustration suivante montre comment la valeur de champ, Games and Toys, du rapport principal s’affiche dans le titre du rapport d’extraction.</span><span class="sxs-lookup"><span data-stu-id="c4024-107">The following illustration shows how the field value, Games and Toys, in the main report displays in the drillthrough report's title.</span></span> <span data-ttu-id="c4024-108">Les données de l'extraction se rapportent à la catégorie de produit Games and Toys.</span><span class="sxs-lookup"><span data-stu-id="c4024-108">The data in the drillthrough pertains to the Games and Toys product category.</span></span>  
  
 <span data-ttu-id="c4024-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span><span class="sxs-lookup"><span data-stu-id="c4024-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="c4024-110">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="c4024-110">What You Will Learn</span></span>  
 <span data-ttu-id="c4024-111">**Dans le rapport d'extraction, vous allez apprendre à :**</span><span class="sxs-lookup"><span data-stu-id="c4024-111">**In the drillthrough report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="c4024-112">Créer un rapport de matrice d'extraction et un dataset à partir de l'Assistant Tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="c4024-112">Create a Drillthrough Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#DMatrixAndDataset)  
  
    1.  [<span data-ttu-id="c4024-113">Spécifier une connexion de données</span><span class="sxs-lookup"><span data-stu-id="c4024-113">Specify a Data Connection</span></span>](#DConnection)  
  
    2.  [<span data-ttu-id="c4024-114">Créer une requête MDX</span><span class="sxs-lookup"><span data-stu-id="c4024-114">Create an MDX Query</span></span>](#DMDXQuery)  
  
    3.  [<span data-ttu-id="c4024-115">Organiser les données dans des groupes Style</span><span class="sxs-lookup"><span data-stu-id="c4024-115">Organize Data into Groups Style</span></span>](#DLayout)  
  
    4.  [<span data-ttu-id="c4024-116">Ajouter des sous-totaux et des totaux</span><span class="sxs-lookup"><span data-stu-id="c4024-116">Add Subtotals and Totals</span></span>](#DTotals)  
  
    5.  [<span data-ttu-id="c4024-117">Choisir un style</span><span class="sxs-lookup"><span data-stu-id="c4024-117">Choose a Style</span></span>](#DStyle)  
  
2.  [<span data-ttu-id="c4024-118">Mettre en forme les données en tant que devises</span><span class="sxs-lookup"><span data-stu-id="c4024-118">Format Data as Currency</span></span>](#DFormat)  
  
3.  [<span data-ttu-id="c4024-119">Ajouter des colonnes pour afficher les valeurs des ventes dans les graphiques sparkline</span><span class="sxs-lookup"><span data-stu-id="c4024-119">Add columns to Show Sales Values in Sparklines</span></span>](#DSparkline)  
  
4.  [<span data-ttu-id="c4024-120">Ajouter un titre de rapport avec le nom d'une catégorie de produit</span><span class="sxs-lookup"><span data-stu-id="c4024-120">Add Report Title with Product Category Name</span></span>](#DReportTitle)  
  
5.  [<span data-ttu-id="c4024-121">Mettre à jour des propriétés de paramètre</span><span class="sxs-lookup"><span data-stu-id="c4024-121">Update Parameter Properties</span></span>](#DParameter)  
  
6.  [<span data-ttu-id="c4024-122">Enregistrer le rapport dans une bibliothèque SharePoint</span><span class="sxs-lookup"><span data-stu-id="c4024-122">Save the Report to a SharePoint Library</span></span>](#DSave)  
  
 <span data-ttu-id="c4024-123">**Dans le rapport principal, vous allez apprendre à :**</span><span class="sxs-lookup"><span data-stu-id="c4024-123">**In the main report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="c4024-124">Créer le rapport de matrice principal et un dataset à partir de l'Assistant Tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="c4024-124">Create the Main Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#MMatrixAndDataset)  
  
    1.  [<span data-ttu-id="c4024-125">Spécifier une connexion de données</span><span class="sxs-lookup"><span data-stu-id="c4024-125">Specify a Data Connection</span></span>](#MConnection)  
  
    2.  [<span data-ttu-id="c4024-126">Créer une requête MDX</span><span class="sxs-lookup"><span data-stu-id="c4024-126">Create an MDX Query</span></span>](#MMDXQuery)  
  
    3.  [<span data-ttu-id="c4024-127">Organiser les données dans des groupes</span><span class="sxs-lookup"><span data-stu-id="c4024-127">Organize Data into Groups</span></span>](#MLayout)  
  
    4.  [<span data-ttu-id="c4024-128">Ajouter des sous-totaux et des totaux</span><span class="sxs-lookup"><span data-stu-id="c4024-128">Add Subtotals and Totals</span></span>](#MTotals)  
  
    5.  [<span data-ttu-id="c4024-129">Choisir un style</span><span class="sxs-lookup"><span data-stu-id="c4024-129">Choose a Style</span></span>](#MStyle)  
  
2.  [<span data-ttu-id="c4024-130">Supprimer la ligne de total général</span><span class="sxs-lookup"><span data-stu-id="c4024-130">Remove the Grand Total Row</span></span>](#MGrandTotal)  
  
3.  [<span data-ttu-id="c4024-131">Configurer une action de zone de texte pour l'extraction</span><span class="sxs-lookup"><span data-stu-id="c4024-131">Configure Text Box Action for Drillthrough</span></span>](#MDrillthrough)  
  
4.  [<span data-ttu-id="c4024-132">Remplacer des valeurs numériques par des indicateurs</span><span class="sxs-lookup"><span data-stu-id="c4024-132">Replace Numeric Values with Indicators</span></span>](#MIndicators)  
  
5.  [<span data-ttu-id="c4024-133">Mettre à jour des propriétés de paramètre</span><span class="sxs-lookup"><span data-stu-id="c4024-133">Update Parameter Properties</span></span>](#MParameter)  
  
6.  [<span data-ttu-id="c4024-134">Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="c4024-134">Add a Report Title</span></span>](#MTitle)  
  
7.  [<span data-ttu-id="c4024-135">Enregistrer le rapport dans une bibliothèque SharePoint</span><span class="sxs-lookup"><span data-stu-id="c4024-135">Save the Report to a SharePoint Library</span></span>](#MSave)  
  
8.  [<span data-ttu-id="c4024-136">Exécuter les rapports principal et d'extraction</span><span class="sxs-lookup"><span data-stu-id="c4024-136">Run the Main and Drillthrough Reports</span></span>](#MRunReports)  
  
 <span data-ttu-id="c4024-137">Durée estimée pour effectuer ce didacticiel : 30 minutes.</span><span class="sxs-lookup"><span data-stu-id="c4024-137">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4024-138">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c4024-138">Requirements</span></span>  
 <span data-ttu-id="c4024-139">Pour suivre ce didacticiel, vous avez besoin d'accéder au cube Contoso Sales.</span><span class="sxs-lookup"><span data-stu-id="c4024-139">This tutorial requires access to the Contoso Sales cube.</span></span> <span data-ttu-id="c4024-140">Cette condition s'applique à la fois aux rapports principal et d'extraction.</span><span class="sxs-lookup"><span data-stu-id="c4024-140">This requirement applies to both the drillthrough and the main reports.</span></span> <span data-ttu-id="c4024-141">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="c4024-141">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-drillthrough-report-from-the-table-or-matrix-wizard"></a><a name="DMatrixAndDataset"></a><span data-ttu-id="c4024-142">1. créer un rapport d’extraction à partir de l’Assistant tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="c4024-142">1. Create a Drillthrough Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="c4024-143">Dans la boîte de dialogue Prise en main , créez un rapport de matrice à l’aide de **l’Assistant Tableau ou matrice**.</span><span class="sxs-lookup"><span data-stu-id="c4024-143">From the Getting Started dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span> <span data-ttu-id="c4024-144">Deux modes sont disponibles dans l'assistant : création de rapport et création de dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="c4024-144">There are two modes available in the wizard: report design and shared dataset design.</span></span> <span data-ttu-id="c4024-145">Dans ce didacticiel, vous allez utiliser le mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-145">In this tutorial, you will use the report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="c4024-146">Pour créer un rapport</span><span class="sxs-lookup"><span data-stu-id="c4024-146">To create a new report</span></span>  
  
1.  <span data-ttu-id="c4024-147">Cliquez sur **Démarrer**, pointez sur **programmes**, sur [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Générateur de rapports**, puis cliquez sur **Générateur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="c4024-147">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="c4024-148">La boîte de dialogue **Mise en route** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="c4024-148">The **Getting Started** dialog box opens.</span></span> <span data-ttu-id="c4024-149">S’il n’apparaît pas, à partir du bouton **Générateur de rapports** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c4024-149">If it does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="c4024-150">Dans le volet gauche, assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c4024-150">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="c4024-151">Dans le volet droit, vérifiez que **Assistant Tableau ou matrice** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c4024-151">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="DConnection"></a><span data-ttu-id="c4024-152">1a.</span><span class="sxs-lookup"><span data-stu-id="c4024-152">1a.</span></span> <span data-ttu-id="c4024-153">Spécifier une connexion de données</span><span class="sxs-lookup"><span data-stu-id="c4024-153">Specify a Data Connection</span></span>  
 <span data-ttu-id="c4024-154">Une connexion de données contient les informations nécessaires pour se connecter à une source de données externe telle qu'un cube Analysis Services ou une base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c4024-154">A data connection contains the information necessary to connect to an external data source such as an Analysis Services cube or a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="c4024-155">Pour spécifier une connexion de données, vous pouvez utiliser une source de données partagée sur le serveur de rapports ou créer une source de données incorporée utilisée uniquement dans ce rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-155">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span> <span data-ttu-id="c4024-156">Dans ce didacticiel, vous allez utiliser une source de données incorporée.</span><span class="sxs-lookup"><span data-stu-id="c4024-156">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="c4024-157">Pour en savoir plus sur l’utilisation d’une source de données partagée, consultez [Autres manières d’obtenir une connexion de données &#40;Générateur de rapports&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c4024-157">To learn more about using a shared data source, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="c4024-158">Pour créer une source de données incorporée</span><span class="sxs-lookup"><span data-stu-id="c4024-158">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="c4024-159">Dans la page **Choisir un dataset** , sélectionnez **Créer un dataset**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c4024-159">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="c4024-160">La page **Choisir une connexion à une source de données** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="c4024-160">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="c4024-161">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c4024-161">Click **New**.</span></span> <span data-ttu-id="c4024-162">La boîte de dialogue **Propriétés de la source de données** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="c4024-162">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c4024-163">Dans **Nom**, tapez **Online and Reseller Sales Detail** comme nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="c4024-163">In **Name**, type **Online and Reseller Sales Detail** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="c4024-164">Dans **Sélectionner un type de connexion**, sélectionnez **Microsoft SQL Server Analysis Services**, puis cliquez sur **Générer**.</span><span class="sxs-lookup"><span data-stu-id="c4024-164">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="c4024-165">Dans **Source de données**, vérifiez que la source de données est **Microsoft SQL Server Analysis Services (AdomdClient)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-165">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="c4024-166">Dans **Nom du serveur**, tapez le nom d’un serveur où est installée une instance d’Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c4024-166">In **Server name**, type the name of a server where an instance of Analysis Services is installed.</span></span>  
  
7.  <span data-ttu-id="c4024-167">Dans **Sélectionner ou entrer un nom de base de données**, sélectionnez le cube Contoso.</span><span class="sxs-lookup"><span data-stu-id="c4024-167">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="c4024-168">Vérifiez que **Chaîne de connexion** présente la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="c4024-168">Verify that **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
     <span data-ttu-id="c4024-169">`<servername>` est le nom d'une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] où est installé Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c4024-169">The `<servername>` is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with Analysis Services installed.</span></span>  
  
10. <span data-ttu-id="c4024-170">Cliquez sur **Type d’informations d’identification**.</span><span class="sxs-lookup"><span data-stu-id="c4024-170">Click **Credentials type**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4024-171">Selon le mode de configuration des autorisations sur la source de données, vous devrez peut-être modifier les options d'authentification par défaut.</span><span class="sxs-lookup"><span data-stu-id="c4024-171">Depending on how permissions are configured on the data source, you might need to change the default authentication options.</span></span> <span data-ttu-id="c4024-172">Pour plus d’informations, consultez [Sécurité &#40;Générateur de rapports&#41;](report-builder/security-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c4024-172">For more information, see [Security &#40;Report Builder&#41;](report-builder/security-report-builder.md).</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="c4024-173">La page **Choisir une connexion à une source de données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c4024-173">The **Choose a connection to a data source** page appears.</span></span>  
  
12. <span data-ttu-id="c4024-174">Pour vous assurer que vous pouvez vous connecter à la source de données, cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="c4024-174">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="c4024-175">Le message la **connexion a été créée** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c4024-175">The message **Connection created successfully** appears.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="c4024-176">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c4024-176">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="DMDXQuery"></a><span data-ttu-id="c4024-177">ter.</span><span class="sxs-lookup"><span data-stu-id="c4024-177">1b.</span></span> <span data-ttu-id="c4024-178">Créer une requête MDX</span><span class="sxs-lookup"><span data-stu-id="c4024-178">Create an MDX Query</span></span>  
 <span data-ttu-id="c4024-179">Dans un rapport, vous pouvez utiliser un dataset partagé qui comprend une requête prédéfinie, ou vous pouvez créer un dataset incorporé utilisable uniquement dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-179">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="c4024-180">Dans ce didacticiel, vous allez créer un dataset incorporé.</span><span class="sxs-lookup"><span data-stu-id="c4024-180">In this tutorial, you will create an embedded dataset.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="c4024-181">Pour créer des filtres de requête</span><span class="sxs-lookup"><span data-stu-id="c4024-181">To create query filters</span></span>  
  
1.  <span data-ttu-id="c4024-182">Sur la page **créer une requête** , dans le volet métadonnées, cliquez sur le bouton **(...)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-182">On the **Design a query** page, in the Metadata pane, click the button **(...)**.</span></span>  
  
2.  <span data-ttu-id="c4024-183">Dans la boîte de dialogue **Sélection de cube** , cliquez sur Sales, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-183">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="c4024-184">Si vous ne souhaitez pas générer la requête MDX manuellement, cliquez sur l’icône ![Passer en mode Création](media/rsqdicon-designmode.gif "Passer en mode Création"), basculez le concepteur de requêtes en mode Requête, collez la requête MDX complète dans le concepteur de requêtes, puis passez à l’étape 6 de la section [Pour créer le jeu de données](#DSkip).</span><span class="sxs-lookup"><span data-stu-id="c4024-184">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 6 in [To create the dataset](#DSkip).</span></span>  
  
    ```  
    SELECT NON EMPTY { [Measures].[Sales Amount], [Measures].[Sales Return Amount] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS * [Product].[Product Subcategory Name].[Product Subcategory Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGS  
    ```  
  
3.  <span data-ttu-id="c4024-185">Dans le volet Groupe de mesures, développez Channel, puis faites glisser Channel Name vers la colonne **Hierarchy** dans le volet de filtre.</span><span class="sxs-lookup"><span data-stu-id="c4024-185">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="c4024-186">Le nom de la dimension, Channel, est ajouté automatiquement à la colonne **Dimension** .</span><span class="sxs-lookup"><span data-stu-id="c4024-186">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="c4024-187">Ne modifiez pas la colonne **Dimension** ou **Opérateur** .</span><span class="sxs-lookup"><span data-stu-id="c4024-187">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="c4024-188">Pour ouvrir la liste **Expression de filtre** , cliquez sur la flèche vers le bas dans la colonne **Expression de filtre** .</span><span class="sxs-lookup"><span data-stu-id="c4024-188">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="c4024-189">Dans la liste d’expression de filtre, développez **All Channel**, cliquez sur **Online**, sur **Reseller**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-189">In the filter expression list, expand **All Channel**, click **Online**, click **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c4024-190">La requête inclut maintenant un filtre ne comportant que les canaux suivants : Online (en ligne) et Reseller (revendeur).</span><span class="sxs-lookup"><span data-stu-id="c4024-190">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="c4024-191">Développez la dimension Sales Territory, puis faites glisser Sales Territory Group vers la colonne **Hierarchy** , sous **Channel Name**.</span><span class="sxs-lookup"><span data-stu-id="c4024-191">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column (below **Channel Name**).</span></span>  
  
7.  <span data-ttu-id="c4024-192">Ouvrez la liste **Expression de filtre** , développez **All Sales Territory**, cliquez sur **North America**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-192">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c4024-193">La requête comporte désormais un filtre permettant de n'inclure que les ventes réalisées en Amérique du Nord.</span><span class="sxs-lookup"><span data-stu-id="c4024-193">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="c4024-194">Dans le volet Groupe de mesures, développez Date, puis faites glisser Calendar Year vers la colonne **Hierarchy** dans le volet de filtre.</span><span class="sxs-lookup"><span data-stu-id="c4024-194">In the Measure Group pane, expand Date, and then drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="c4024-195">Le nom de la dimension, Date, est ajouté automatiquement à la colonne **Dimension** .</span><span class="sxs-lookup"><span data-stu-id="c4024-195">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="c4024-196">Ne modifiez pas la colonne **Dimension** ou **Opérateur** .</span><span class="sxs-lookup"><span data-stu-id="c4024-196">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="c4024-197">Pour ouvrir la liste **Expression de filtre** , cliquez sur la flèche vers le bas dans la colonne **Expression de filtre** .</span><span class="sxs-lookup"><span data-stu-id="c4024-197">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="c4024-198">Dans la liste Expression de filtre, développez **All Date**, cliquez sur **Year 2009**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-198">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c4024-199">La requête comporte maintenant un filtre permettant de n'inclure que l'année civile 2009.</span><span class="sxs-lookup"><span data-stu-id="c4024-199">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="c4024-200">Pour créer le paramètre</span><span class="sxs-lookup"><span data-stu-id="c4024-200">To create the parameter</span></span>  
  
1.  <span data-ttu-id="c4024-201">Développez la dimension Product, puis faites glisser le membre Product Category Name vers la colonne **Hierarchy** sous **Calendar Year**.</span><span class="sxs-lookup"><span data-stu-id="c4024-201">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Calendar Year**.</span></span>  
  
2.  <span data-ttu-id="c4024-202">Ouvrez la liste **Expression de filtre** , cliquez sur **All Products**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-202">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="c4024-203">Cliquez sur la case à cocher **Paramètre** .</span><span class="sxs-lookup"><span data-stu-id="c4024-203">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="c4024-204">La requête contient à présent le paramètre ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="c4024-204">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4024-205">Le paramètre contient les noms des catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="c4024-205">The parameter contains the names of product categories.</span></span> <span data-ttu-id="c4024-206">Lorsque vous cliquez sur le nom d'une catégorie de produit dans le rapport principal, celui-ci est passé au rapport d'extraction à l'aide de ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="c4024-206">When you click a product category name in the main report, its name is passed to the drillthrough report by using this parameter.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="DSkip"></a><span data-ttu-id="c4024-207">Pour créer le DataSet</span><span class="sxs-lookup"><span data-stu-id="c4024-207">To create the dataset</span></span>  
  
1.  <span data-ttu-id="c4024-208">À partir de la dimension Channel, faites glisser Channel Name vers le volet de données.</span><span class="sxs-lookup"><span data-stu-id="c4024-208">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="c4024-209">À partir de la dimension Product, faites glisser Product Category Name vers le volet de données, et placez-le à droite de Channel Name.</span><span class="sxs-lookup"><span data-stu-id="c4024-209">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="c4024-210">À partir de la dimension Product, faites glisser Product Subcategory Name vers le volet de données, puis placez-le à droite de Product Category Name.</span><span class="sxs-lookup"><span data-stu-id="c4024-210">From the Product dimension, drag Product Subcategory Name to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="c4024-211">Dans le volet Métadonnées, développez **Mesure**, puis Sales.</span><span class="sxs-lookup"><span data-stu-id="c4024-211">In the Metadata pane, expand **Measure**, and then expand Sales.</span></span>  
  
5.  <span data-ttu-id="c4024-212">Faites glisser la mesure Sales Amount vers le volet de données, puis placez-la à droite de Product Subcategory Name.</span><span class="sxs-lookup"><span data-stu-id="c4024-212">Drag the Sales Amount measure to the data pane, and then place it to the right of Product Subcategory Name.</span></span>  
  
6.  <span data-ttu-id="c4024-213">Dans la barre d’outils du concepteur de requêtes, cliquez sur **exécuter ( !)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-213">On the query designer toolbar, click **Run (!)**.</span></span>  
  
7.  <span data-ttu-id="c4024-214">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c4024-214">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="DLayout"></a><span data-ttu-id="c4024-215">1C.</span><span class="sxs-lookup"><span data-stu-id="c4024-215">1c.</span></span> <span data-ttu-id="c4024-216">Organiser les données dans des groupes</span><span class="sxs-lookup"><span data-stu-id="c4024-216">Organize Data into Groups</span></span>  
 <span data-ttu-id="c4024-217">Lorsque vous sélectionnez les champs dans lesquels regrouper les données, vous concevez une matrice dont les lignes et les colonnes affichent des données de détail et des données agrégées.</span><span class="sxs-lookup"><span data-stu-id="c4024-217">When you select the fields on which to group the data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="c4024-218">Pour organiser les données en groupes</span><span class="sxs-lookup"><span data-stu-id="c4024-218">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="c4024-219">Cliquez sur Conception pour basculer en mode **Conception**.</span><span class="sxs-lookup"><span data-stu-id="c4024-219">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c4024-220">Dans la page **Organiser les champs** , faites glisser Product_Subcategory_Name vers **Groupes de lignes**.</span><span class="sxs-lookup"><span data-stu-id="c4024-220">On the **Arrange fields** page, drag Product_Subcategory_Name to **Row groups**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4024-221">Les espaces dans les noms sont remplacés par des traits de soulignement (_).</span><span class="sxs-lookup"><span data-stu-id="c4024-221">The spaces in the names are replaced with underscores (_).</span></span> <span data-ttu-id="c4024-222">Par exemple, Product Category Name est remplacé par Product_Category_Name.</span><span class="sxs-lookup"><span data-stu-id="c4024-222">For example Product Category Name is Product_Category_Name.</span></span>  
  
3.  <span data-ttu-id="c4024-223">Faites glisser Channel_Name vers **Groupes de colonnes**.</span><span class="sxs-lookup"><span data-stu-id="c4024-223">Drag Channel_Name to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="c4024-224">Faites glisser Sales_Amount vers **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="c4024-224">Drag Sales_Amount to **Values**.</span></span>  
  
     <span data-ttu-id="c4024-225">Sales_Amount est agrégé automatiquement par la fonction Sum, l’agrégat par défaut des champs numériques.</span><span class="sxs-lookup"><span data-stu-id="c4024-225">Sales_Amount is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="c4024-226">La valeur est `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="c4024-226">The value is `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="c4024-227">Pour consulter les autres fonctions d'agrégation disponibles, ouvrez la liste déroulante (ne modifiez pas la fonction d'agrégation).</span><span class="sxs-lookup"><span data-stu-id="c4024-227">To view the other aggregate functions available, open the drop-down list (do not change the aggregate function).</span></span>  
  
5.  <span data-ttu-id="c4024-228">Faites glisser Sales_Return_Amount vers **Valeurs**et placez-le sous `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="c4024-228">Drag Sales_Return_Amount to **Values**, and then place it below `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="c4024-229">Les étapes 4 et 5 spécifient les données à afficher dans la matrice.</span><span class="sxs-lookup"><span data-stu-id="c4024-229">Steps 4 and 5 specify the data to display in the matrix.</span></span>  
  
6.  <span data-ttu-id="c4024-230">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c4024-230">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="DTotals"></a><span data-ttu-id="c4024-231">1D.</span><span class="sxs-lookup"><span data-stu-id="c4024-231">1d.</span></span> <span data-ttu-id="c4024-232">Ajouter des sous-totaux et des totaux</span><span class="sxs-lookup"><span data-stu-id="c4024-232">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="c4024-233">Après avoir créé des groupes, vous pouvez ajouter et mettre en forme les lignes dans lesquelles afficher les valeurs d'agrégat des champs.</span><span class="sxs-lookup"><span data-stu-id="c4024-233">After you create groups, you can add and format rows where the aggregate values for the fields will display.</span></span> <span data-ttu-id="c4024-234">Vous pouvez également afficher toutes les données ou laisser l'utilisateur développer/réduire les données regroupées de manière interactive.</span><span class="sxs-lookup"><span data-stu-id="c4024-234">You can also choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="c4024-235">Pour ajouter des sous-totaux et des totaux</span><span class="sxs-lookup"><span data-stu-id="c4024-235">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="c4024-236">Dans la page **Choisir la disposition** , sous **Options**, vérifiez que **Afficher les sous-totaux et les totaux généraux** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c4024-236">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="c4024-237">Le volet Aperçu de l'Assistant affiche une matrice avec quatre lignes.</span><span class="sxs-lookup"><span data-stu-id="c4024-237">The wizard Preview pane displays a matrix with four rows.</span></span>  
  
2.  <span data-ttu-id="c4024-238">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c4024-238">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="DStyle"></a><span data-ttu-id="c4024-239">1La.</span><span class="sxs-lookup"><span data-stu-id="c4024-239">1e.</span></span> <span data-ttu-id="c4024-240">Choisir un style</span><span class="sxs-lookup"><span data-stu-id="c4024-240">Choose a Style</span></span>  
 <span data-ttu-id="c4024-241">Un style spécifie un style de police, un jeu de couleurs et un style de bordure.</span><span class="sxs-lookup"><span data-stu-id="c4024-241">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="c4024-242">Pour spécifier un style</span><span class="sxs-lookup"><span data-stu-id="c4024-242">To specify a style</span></span>  
  
1.  <span data-ttu-id="c4024-243">Dans la page **choisir un style** , dans le volet styles, sélectionnez ardoise.</span><span class="sxs-lookup"><span data-stu-id="c4024-243">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="c4024-244">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="c4024-244">Click **Finish**.</span></span>  
  
     <span data-ttu-id="c4024-245">Le tableau est ajouté à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="c4024-245">The table is added to the design surface.</span></span>  
  
3.  <span data-ttu-id="c4024-246">Pour afficher un aperçu du rapport, cliquez sur **Exécuter (!)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-246">To preview the report, click **Run (!)**.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="DFormat"></a><span data-ttu-id="c4024-247">2. mettre en forme les données en tant que devise</span><span class="sxs-lookup"><span data-stu-id="c4024-247">2. Format Data as Currency</span></span>  
 <span data-ttu-id="c4024-248">Appliquez une mise en forme de devise aux champs de montant des ventes dans le rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="c4024-248">Apply currency formatting to the sales amount fields in the drillthrough report.</span></span>  
  
#### <a name="to-format-data-as-currency"></a><span data-ttu-id="c4024-249">Pour mettre en forme les données en tant que devise</span><span class="sxs-lookup"><span data-stu-id="c4024-249">To format data as currency</span></span>  
  
1.  <span data-ttu-id="c4024-250">Cliquez sur Conception pour basculer en mode **Conception**.</span><span class="sxs-lookup"><span data-stu-id="c4024-250">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c4024-251">Pour sélectionner et mettre en forme plusieurs cellules simultanément, appuyez sur la touche Ctrl et sélectionnez les cellules qui contiennent les données de ventes numériques.</span><span class="sxs-lookup"><span data-stu-id="c4024-251">To select and format multiple cells at one time, press the Ctrl key, and then select the cells that contain the numeric sales data.</span></span>  
  
3.  <span data-ttu-id="c4024-252">Sous l’onglet **Accueil** , dans le groupe **Nombre** , cliquez sur **Devise**.</span><span class="sxs-lookup"><span data-stu-id="c4024-252">On the **Home** tab, in the **Number** group, click **Currency**.</span></span>  
  
##  <a name="3-add-columns-to-show-sales-values-in-sparklines"></a><a name="DSparkline"></a><span data-ttu-id="c4024-253">3. ajouter des colonnes pour afficher les valeurs des ventes dans les graphiques sparkline</span><span class="sxs-lookup"><span data-stu-id="c4024-253">3. Add Columns to Show Sales Values in Sparklines</span></span>  
 <span data-ttu-id="c4024-254">Au lieu d'afficher les ventes et les retours de ventes sous forme de valeurs monétaires, le rapport affiche les valeurs dans un graphique sparkline.</span><span class="sxs-lookup"><span data-stu-id="c4024-254">Instead of showing sales and sales returns as currency values, the report shows the values in a sparkline.</span></span>  
  
#### <a name="to-add-sparklines-to-columns"></a><span data-ttu-id="c4024-255">Pour ajouter des graphiques sparkline à des colonnes</span><span class="sxs-lookup"><span data-stu-id="c4024-255">To add sparklines to columns</span></span>  
  
1.  <span data-ttu-id="c4024-256">Cliquez sur Conception pour basculer en mode **Conception**.</span><span class="sxs-lookup"><span data-stu-id="c4024-256">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c4024-257">Dans le groupe Total de la matrice, cliquez avec le bouton droit sur la colonne **Sales Amount** , sélectionnez **Insérer une colonne**, puis **À droite**.</span><span class="sxs-lookup"><span data-stu-id="c4024-257">In the Total group of the matrix, right-click the **Sales Amount** column, click **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="c4024-258">Une colonne vide est ajoutée à la droite de **Sales Amount**.</span><span class="sxs-lookup"><span data-stu-id="c4024-258">An empty column is added to the right of **Sales Amount**.</span></span>  
  
3.  <span data-ttu-id="c4024-259">Sur le ruban, cliquez sur **Rectangle**, puis cliquez sur la cellule vide à la droite de la cellule `[Sum(Sales_Amount)]` dans le groupe de lignes [Product_Subcategory].</span><span class="sxs-lookup"><span data-stu-id="c4024-259">On the ribbon, click **Rectangle**, and then click the empty cell to the right of the `[Sum(Sales_Amount)]` cell in the [Product_Subcategory] row group.</span></span>  
  
4.  <span data-ttu-id="c4024-260">Sur le ruban, cliquez sur l’icône **Graphique sparkline** , puis cliquez sur la cellule dans laquelle le rectangle a été ajouté.</span><span class="sxs-lookup"><span data-stu-id="c4024-260">On the ribbon, click the **Sparkline** icon, and then click the cell where the rectangle was added.</span></span>  
  
5.  <span data-ttu-id="c4024-261">Dans la boîte de dialogue **Sélectionner un type de graphique sparkline** , vérifiez que le type **Colonne** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c4024-261">In the **Select Sparkline Type** dialog box, verify that **Column** type is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="c4024-262">Cliquez avec le bouton droit sur le graphique sparkline.</span><span class="sxs-lookup"><span data-stu-id="c4024-262">Right-click the sparkline.</span></span>  
  
8.  <span data-ttu-id="c4024-263">Dans le volet Données du graphique, cliquez sur l’icône **Ajouter un champ** , puis sur Sales_Amount.</span><span class="sxs-lookup"><span data-stu-id="c4024-263">In the Chart Data pane, click the **Add field** icon, and then click Sales_Amount.</span></span>  
  
9. <span data-ttu-id="c4024-264">Cliquez avec le bouton droit sur la colonne `Sales_Return_Amount` , puis ajoutez une colonne à la droite de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="c4024-264">Right-click the `Sales_Return_Amount` column, and then add a column to the right of it.</span></span>  
  
10. <span data-ttu-id="c4024-265">Répétez les étapes 2 à 6.</span><span class="sxs-lookup"><span data-stu-id="c4024-265">Repeat steps 2 through 6.</span></span>  
  
11. <span data-ttu-id="c4024-266">Cliquez avec le bouton droit sur le graphique sparkline.</span><span class="sxs-lookup"><span data-stu-id="c4024-266">Right-click the sparkline.</span></span>  
  
12. <span data-ttu-id="c4024-267">Dans le volet Données du graphique, cliquez sur l’icône **Ajouter un champ** , puis sur Sales_Return_Amount.</span><span class="sxs-lookup"><span data-stu-id="c4024-267">In the Chart Data pane, click the **Add field** icon, and then click Sales_Return_Amount.</span></span>  
  
13. <span data-ttu-id="c4024-268">Pour afficher un aperçu du rapport, cliquez sur **Exécuter (!)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-268">To preview the report, click **Run**.</span></span>  
  
##  <a name="4-add-report-title-with-product-category-name"></a><a name="DReportTitle"></a><span data-ttu-id="c4024-269">4. Ajouter un titre de rapport avec le nom de catégorie de produit</span><span class="sxs-lookup"><span data-stu-id="c4024-269">4. Add Report Title with Product Category Name</span></span>  
 <span data-ttu-id="c4024-270">Un titre de rapport s'affiche dans la partie supérieure du rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-270">A report title appears at the top of the report.</span></span> <span data-ttu-id="c4024-271">Vous pouvez placer le titre du rapport dans un en-tête de rapport, ou si le rapport n'en utilise pas, dans une zone de texte située en haut du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-271">You can place the report title in a report header or, if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="c4024-272">Dans ce didacticiel, vous allez utiliser la zone de texte placée automatiquement en haut du corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-272">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="c4024-273">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="c4024-273">To add a report title</span></span>  
  
1.  <span data-ttu-id="c4024-274">Cliquez sur Conception pour basculer en mode **Conception**.</span><span class="sxs-lookup"><span data-stu-id="c4024-274">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c4024-275">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="c4024-275">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="c4024-276">Tapez **Sales and Returns for Category:**.</span><span class="sxs-lookup"><span data-stu-id="c4024-276">Type **Sales and Returns for Category:**.</span></span>  
  
4.  <span data-ttu-id="c4024-277">Cliquez avec le bouton droit, puis sélectionnez **Créer un espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="c4024-277">Right-click, and then click **Create Placeholder**.</span></span>  
  
5.  <span data-ttu-id="c4024-278">Cliquez sur le bouton **(fx)** à la droite de la liste **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="c4024-278">Click the **(fx)** button to the right of the **Value** list.</span></span>  
  
6.  <span data-ttu-id="c4024-279">Dans la boîte de dialogue **Expression** , dans le volet Catégorie, cliquez sur **Dataset**, puis dans la liste **Valeurs** , double-cliquez sur `First(Product_Category_Name)`.</span><span class="sxs-lookup"><span data-stu-id="c4024-279">In the **Expression** dialog box, in the Category pane, click **Dataset**, and then in the **Values** list double-click `First(Product_Category_Name)`.</span></span>  
  
     <span data-ttu-id="c4024-280">La zone **Expression** contient l’expression suivante :</span><span class="sxs-lookup"><span data-stu-id="c4024-280">The **Expression** box contains the following expression:</span></span>  
  
    ```  
    =First(Fields!Product_Category_Name.Value, "DataSet1")  
    ```  
  
7.  <span data-ttu-id="c4024-281">Pour afficher un aperçu du rapport, cliquez sur **Exécuter (!)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-281">To preview the report, click **Run**.</span></span>  
  
 <span data-ttu-id="c4024-282">Le titre du rapport inclut le nom de la première catégorie de produit.</span><span class="sxs-lookup"><span data-stu-id="c4024-282">The report title includes the name of the first product category.</span></span> <span data-ttu-id="c4024-283">Par la suite, après avoir exécuté ce rapport en tant que rapport d'extraction, le nom de la catégorie de produit changera de manière dynamique afin de refléter le nom de la catégorie de produit sur lequel l'utilisateur a cliqué dans le rapport principal.</span><span class="sxs-lookup"><span data-stu-id="c4024-283">Later, after you run this report as a drillthrough report, the product category name will dynamically change to reflect the name of the product category that was clicked in the main report.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="DParameter"></a><span data-ttu-id="c4024-284">5. mettre à jour les propriétés des paramètres</span><span class="sxs-lookup"><span data-stu-id="c4024-284">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="c4024-285">Par défaut, les paramètres sont visibles, ce qui n'est pas approprié pour ce rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-285">By default parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="c4024-286">Vous allez mettre à jour les propriétés de paramètre pour le rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="c4024-286">You will update the parameter properties for the drillthrough report.</span></span>  
  
#### <a name="to-hide-a-parameter"></a><span data-ttu-id="c4024-287">Pour masquer un paramètre</span><span class="sxs-lookup"><span data-stu-id="c4024-287">To hide a parameter</span></span>  
  
1.  <span data-ttu-id="c4024-288">Dans le volet des données de rapport, développez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="c4024-288">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="c4024-289">Cliquez avec le bouton droit sur \@ ProductProductCategoryName, puis cliquez sur **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="c4024-289">Right-click \@ProductProductCategoryName, and then click **Parameter Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4024-290">Le caractère \@ à côté du nom indique qu'il s'agit d'un paramètre.</span><span class="sxs-lookup"><span data-stu-id="c4024-290">The \@ character next to the name indicates that this is a parameter.</span></span>  
  
3.  <span data-ttu-id="c4024-291">Sous l’onglet **Général** , cliquez sur **Masqué**.</span><span class="sxs-lookup"><span data-stu-id="c4024-291">On the **General** tab, click **Hidden**.</span></span>  
  
4.  <span data-ttu-id="c4024-292">Dans la zone **Demander** , tapez **Product Category**.</span><span class="sxs-lookup"><span data-stu-id="c4024-292">In the **Prompt** box, type **Product Category**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4024-293">Comme le paramètre est masqué, cette invite n'est jamais utilisée.</span><span class="sxs-lookup"><span data-stu-id="c4024-293">Because the parameter is hidden, this prompt is never used.</span></span>  
  
5.  <span data-ttu-id="c4024-294">Cliquez éventuellement sur **Valeurs disponibles** et sur **Valeurs par défaut** , et passez en revue leurs options.</span><span class="sxs-lookup"><span data-stu-id="c4024-294">Optionally, click **Available Values** and **Default Values** and review their options.</span></span> <span data-ttu-id="c4024-295">Ne modifiez aucune des options de ces onglets.</span><span class="sxs-lookup"><span data-stu-id="c4024-295">Do not change any options on these tabs.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report-to-a-sharepoint-library"></a><a name="DSave"></a><span data-ttu-id="c4024-296">6. enregistrer le rapport dans une bibliothèque SharePoint</span><span class="sxs-lookup"><span data-stu-id="c4024-296">6. Save the Report to a SharePoint Library</span></span>  
 <span data-ttu-id="c4024-297">Vous pouvez enregistrer le rapport dans une bibliothèque SharePoint, sur un serveur de rapports ou sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c4024-297">You can save the report to a SharePoint library, report server, or your computer.</span></span> <span data-ttu-id="c4024-298">Si vous enregistrez le rapport sur votre ordinateur, plusieurs fonctionnalités de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] telles que les parties de rapports et les sous-rapports ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="c4024-298">If you save the report to your computer, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span> <span data-ttu-id="c4024-299">Dans ce didacticiel, vous allez enregistrer le rapport dans une bibliothèque SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c4024-299">In this tutorial, you will save the report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="c4024-300">Pour enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="c4024-300">To save the report</span></span>  
  
1.  <span data-ttu-id="c4024-301">À partir du bouton Générateur de rapports, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c4024-301">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="c4024-302">La boîte de dialogue **Enregistrer en tant que rapport** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c4024-302">The **Save As Report** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4024-303">Si vous réenregistrez un rapport, il est automatiquement stocké à son emplacement précédent.</span><span class="sxs-lookup"><span data-stu-id="c4024-303">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="c4024-304">Pour modifier l’emplacement, utilisez l’option **Enregistrer sous** .</span><span class="sxs-lookup"><span data-stu-id="c4024-304">To change the location, use the **Save As** option.</span></span>  
  
2.  <span data-ttu-id="c4024-305">Pour afficher une liste de serveurs de rapports et de sites SharePoint récemment utilisés, cliquez sur **Sites et serveurs récents**.</span><span class="sxs-lookup"><span data-stu-id="c4024-305">To show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="c4024-306">Sélectionnez ou tapez le nom du site SharePoint sur lequel vous êtes autorisé à enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="c4024-306">Select or type the name of the SharePoint site where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="c4024-307">L'URL de la bibliothèque SharePoint présente la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="c4024-307">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
4.  <span data-ttu-id="c4024-308">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c4024-308">Click **Save**.</span></span>  
  
     <span data-ttu-id="c4024-309">La liste**Sites et serveurs récents** répertorie les bibliothèques sur le site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c4024-309">**Recent Sites and Servers** lists the libraries on the SharePoint site.</span></span>  
  
5.  <span data-ttu-id="c4024-310">Accédez à la bibliothèque où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-310">Navigate to the library where you will save the report.</span></span>  
  
6.  <span data-ttu-id="c4024-311">Dans la zone **Nom** , remplacez le nom par défaut par **ResellerVSOnlineDrillthrough**.</span><span class="sxs-lookup"><span data-stu-id="c4024-311">In the **Name** box, replace the default name with **ResellerVSOnlineDrillthrough**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4024-312">Vous allez enregistrer le rapport principal au même emplacement.</span><span class="sxs-lookup"><span data-stu-id="c4024-312">You will save the main report to the same location.</span></span> <span data-ttu-id="c4024-313">Si vous souhaitez enregistrer les rapports principal et d’extraction dans des bibliothèques ou des sites différents, vous devez mettre à jour le chemin de l’action **Atteindre le rapport** dans le rapport principal.</span><span class="sxs-lookup"><span data-stu-id="c4024-313">If you want to save the main and drillthrough reports to different sites or libraries, you must update the path of the **Go to report** action in the main report.</span></span>  
  
7.  <span data-ttu-id="c4024-314">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c4024-314">Click **Save**.</span></span>  
  
##  <a name="1-create-a-new-report-from-the-table-or-matrix-wizard"></a><a name="MMatrixAndDataset"></a><span data-ttu-id="c4024-315">1. créer un rapport à partir de l’Assistant tableau ou matrice</span><span class="sxs-lookup"><span data-stu-id="c4024-315">1. Create a New Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="c4024-316">Dans la boîte de dialogue **Prise en main** , créez un rapport de matrice à l’aide de **l’Assistant Tableau ou matrice**.</span><span class="sxs-lookup"><span data-stu-id="c4024-316">From the **Getting Started** dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="c4024-317">Pour créer un rapport</span><span class="sxs-lookup"><span data-stu-id="c4024-317">To create a new report</span></span>  
  
1.  <span data-ttu-id="c4024-318">Cliquez sur **Démarrer**, pointez sur **programmes**, sur [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Générateur de rapports**, puis cliquez sur **Générateur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="c4024-318">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
2.  <span data-ttu-id="c4024-319">Dans la boîte de dialogue **Prise en main** , vérifiez que **Nouveau rapport** est sélectionné, puis cliquez sur **Assistant Tableau ou matrice**.</span><span class="sxs-lookup"><span data-stu-id="c4024-319">In the **Getting Started** dialog box, verify that **New Report** is selected, and then click **Table or Matrix Wizard**.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="MConnection"></a><span data-ttu-id="c4024-320">1a.</span><span class="sxs-lookup"><span data-stu-id="c4024-320">1a.</span></span> <span data-ttu-id="c4024-321">Spécifier une connexion de données</span><span class="sxs-lookup"><span data-stu-id="c4024-321">Specify a Data Connection</span></span>  
 <span data-ttu-id="c4024-322">Vous allez ajouter une source de données incorporée au rapport principal.</span><span class="sxs-lookup"><span data-stu-id="c4024-322">You will add an embedded data source to the main report.</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="c4024-323">Pour créer une source de données incorporée</span><span class="sxs-lookup"><span data-stu-id="c4024-323">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="c4024-324">Dans la page **Choisir un dataset** , sélectionnez **Créer un dataset**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c4024-324">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="c4024-325">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c4024-325">Click **New**.</span></span>  
  
3.  <span data-ttu-id="c4024-326">Dans la zone **Nom**, tapez **Online and Reseller Sales Main** comme nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="c4024-326">In **Name**, type **Online and Reseller Sales Main** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="c4024-327">Dans **Sélectionner un type de connexion**, sélectionnez **Microsoft SQL Server Analysis Services**, puis cliquez sur **Générer**.</span><span class="sxs-lookup"><span data-stu-id="c4024-327">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="c4024-328">Dans **Source de données**, vérifiez que la source de données est **Microsoft SQL Server Analysis Services (AdomdClient)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-328">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="c4024-329">Dans **nom du serveur**, tapez le nom d’un serveur sur lequel une instance de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] est installée.</span><span class="sxs-lookup"><span data-stu-id="c4024-329">In **Server name**, type the name of a server where an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is installed.</span></span>  
  
7.  <span data-ttu-id="c4024-330">Dans **Sélectionner ou entrer un nom de base de données**, sélectionnez le cube Contoso.</span><span class="sxs-lookup"><span data-stu-id="c4024-330">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="c4024-331">Vérifiez que **Chaîne de connexion** présente la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="c4024-331">Verify that the **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
10. <span data-ttu-id="c4024-332">Cliquez sur **Type d’informations d’identification**.</span><span class="sxs-lookup"><span data-stu-id="c4024-332">Click **Credentials type**.</span></span>  
  
     <span data-ttu-id="c4024-333">Selon le mode de configuration des autorisations sur la source de données, vous devrez peut-être modifier l'authentification par défaut.</span><span class="sxs-lookup"><span data-stu-id="c4024-333">Depending on how permissions are configured on the data source, you might need to change the default authentication.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="c4024-334">Pour vous assurer que vous pouvez vous connecter à la source de données, cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="c4024-334">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="c4024-335">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c4024-335">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="MMDXQuery"></a><span data-ttu-id="c4024-336">ter.</span><span class="sxs-lookup"><span data-stu-id="c4024-336">1b.</span></span> <span data-ttu-id="c4024-337">Créer une requête MDX</span><span class="sxs-lookup"><span data-stu-id="c4024-337">Create an MDX Query</span></span>  
 <span data-ttu-id="c4024-338">À présent, créez un dataset incorporé.</span><span class="sxs-lookup"><span data-stu-id="c4024-338">Next, create an embedded dataset.</span></span> <span data-ttu-id="c4024-339">Pour ce faire, vous allez utiliser le concepteur de requêtes afin de créer des filtres, des paramètres et des membres calculés, ainsi que le dataset lui-même.</span><span class="sxs-lookup"><span data-stu-id="c4024-339">To do so, you will use the query designer to create filters, parameters, and calculated members as well as the dataset itself.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="c4024-340">Pour créer des filtres de requête</span><span class="sxs-lookup"><span data-stu-id="c4024-340">To create query filters</span></span>  
  
1.  <span data-ttu-id="c4024-341">Sur la page **créer une requête** , dans le volet métadonnées, dans la section cube, cliquez sur le bouton de sélection **(...)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-341">On the **Design a query** page, in the Metadata pane, in the cube section, click the ellipsis **(...)**.</span></span>  
  
2.  <span data-ttu-id="c4024-342">Dans la boîte de dialogue **Sélection de cube** , cliquez sur Sales, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-342">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="c4024-343">Si vous ne souhaitez pas générer la requête MDX manuellement, cliquez sur l’icône ![Passer en mode Création](media/rsqdicon-designmode.gif "Passer en mode Création"), basculez le concepteur de requêtes en mode Requête, collez la requête MDX complète dans le concepteur de requêtes, puis passez à l’étape 5 de la section [Pour créer le jeu de données](#MSkip).</span><span class="sxs-lookup"><span data-stu-id="c4024-343">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 5 in [To create the dataset](#MSkip).</span></span>  
  
    ```  
    WITH MEMBER [Measures].[Net QTY] AS [Measures].[Sales Quantity] -[Measures].[Sales Return Quantity] MEMBER [Measures].[Net Sales] AS [Measures].[Sales Amount] - [Measures].[Sales Return Amount] SELECT NON EMPTY { [Measures].[Net QTY], [Measures].[Net Sales] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGSQuery text: Code.  
    ```  
  
3.  <span data-ttu-id="c4024-344">Dans le volet Groupe de mesures, développez Channel, puis faites glisser Channel Name vers la colonne **Hierarchy** dans le volet de filtre.</span><span class="sxs-lookup"><span data-stu-id="c4024-344">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="c4024-345">Le nom de la dimension, Channel, est ajouté automatiquement à la colonne **Dimension** .</span><span class="sxs-lookup"><span data-stu-id="c4024-345">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="c4024-346">Ne modifiez pas la colonne **Dimension** ou **Opérateur** .</span><span class="sxs-lookup"><span data-stu-id="c4024-346">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="c4024-347">Pour ouvrir la liste **Expression de filtre** , cliquez sur la flèche vers le bas dans la colonne **Expression de filtre** .</span><span class="sxs-lookup"><span data-stu-id="c4024-347">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="c4024-348">Dans la liste Expression de filtre, développez **All Channel**, cliquez sur **Online** et **Reseller**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-348">In the filter expression list, expand **All Channel**, click **Online** and **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c4024-349">La requête inclut maintenant un filtre ne comportant que les canaux suivants : Online (en ligne) et Reseller (revendeur).</span><span class="sxs-lookup"><span data-stu-id="c4024-349">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="c4024-350">Développez la dimension Sales secteur, puis faites glisser Sales secteur Group vers la colonne **Hierarchy** , sous **Channel Name**.</span><span class="sxs-lookup"><span data-stu-id="c4024-350">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column, below **Channel Name**.</span></span>  
  
7.  <span data-ttu-id="c4024-351">Ouvrez la liste **Expression de filtre** , développez **All Sales Territory**, cliquez sur **North America**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-351">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c4024-352">La requête comporte désormais un filtre permettant de n'inclure que les ventes réalisées en Amérique du Nord.</span><span class="sxs-lookup"><span data-stu-id="c4024-352">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="c4024-353">Dans le volet Groupe de mesures, développez Date, et faites glisser Calendar Year vers la colonne **Hierarchy** dans le volet de filtre.</span><span class="sxs-lookup"><span data-stu-id="c4024-353">In the Measure Group pane, expand Date, and drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="c4024-354">Le nom de la dimension, Date, est ajouté automatiquement à la colonne **Dimension** .</span><span class="sxs-lookup"><span data-stu-id="c4024-354">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="c4024-355">Ne modifiez pas la colonne **Dimension** ou **Opérateur** .</span><span class="sxs-lookup"><span data-stu-id="c4024-355">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="c4024-356">Pour ouvrir la liste **Expression de filtre** , cliquez sur la flèche vers le bas dans la colonne **Expression de filtre** .</span><span class="sxs-lookup"><span data-stu-id="c4024-356">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="c4024-357">Dans la liste Expression de filtre, développez **All Date**, cliquez sur **Year 2009**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-357">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c4024-358">La requête comporte maintenant un filtre permettant de n'inclure que l'année civile 2009.</span><span class="sxs-lookup"><span data-stu-id="c4024-358">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="c4024-359">Pour créer le paramètre</span><span class="sxs-lookup"><span data-stu-id="c4024-359">To create the parameter</span></span>  
  
1.  <span data-ttu-id="c4024-360">Développez la dimension Product, faites glisser le membre Product Category Name vers la colonne **Hierarchy** sous **Sales Territory Group**.</span><span class="sxs-lookup"><span data-stu-id="c4024-360">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Sales Territory Group**.</span></span>  
  
2.  <span data-ttu-id="c4024-361">Ouvrez la liste **Expression de filtre** , cliquez sur **All Products**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-361">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="c4024-362">Cliquez sur la case à cocher **Paramètre** .</span><span class="sxs-lookup"><span data-stu-id="c4024-362">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="c4024-363">La requête contient à présent le paramètre ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="c4024-363">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
#### <a name="to-create-calculated-members"></a><span data-ttu-id="c4024-364">Pour créer des membres calculés</span><span class="sxs-lookup"><span data-stu-id="c4024-364">To create calculated members</span></span>  
  
1.  <span data-ttu-id="c4024-365">Placez le curseur à l’intérieur du volet Membres calculés, cliquez avec le bouton droit, puis sélectionnez **Nouveau membre calculé**.</span><span class="sxs-lookup"><span data-stu-id="c4024-365">Place the cursor inside the Calculated Members pane, right-click, and then click **New Calculated Member**.</span></span>  
  
2.  <span data-ttu-id="c4024-366">Dans le volet métadonnées, développez **mesures** , puis Sales.</span><span class="sxs-lookup"><span data-stu-id="c4024-366">In the Metadata pane, expand **Measures** and then expand Sales.</span></span>  
  
3.  <span data-ttu-id="c4024-367">Faites glisser la mesure Sales Quantity vers la zone **Expression** , tapez le caractère de soustraction (-), puis faites glisser la mesure Sales Return Quantity vers la zone **Expression** ; placez-la après le caractère de soustraction.</span><span class="sxs-lookup"><span data-stu-id="c4024-367">Drag the Sales Quantity measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Quantity measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="c4024-368">Le code suivant montre l'expression :</span><span class="sxs-lookup"><span data-stu-id="c4024-368">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Quantity] - [Measures].[Sales Return Quantity]  
    ```  
  
4.  <span data-ttu-id="c4024-369">Dans la zone Nom, tapez **Net QTY**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-369">In the Name box, type **Net QTY**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c4024-370">Le volet Membres calculés contient le membre calculé **Net QTY** .</span><span class="sxs-lookup"><span data-stu-id="c4024-370">The Calculated Members pane lists the **Net QTY** calculated member.</span></span>  
  
5.  <span data-ttu-id="c4024-371">Cliquez avec le bouton droit sur **Membres calculés**, puis sélectionnez **Nouveau membre calculé**.</span><span class="sxs-lookup"><span data-stu-id="c4024-371">Right-click **Calculated Members**, and then click **New Calculated Member**.</span></span>  
  
6.  <span data-ttu-id="c4024-372">Dans le volet Métadonnées, développez **Mesures**, puis Sales.</span><span class="sxs-lookup"><span data-stu-id="c4024-372">In the Metadata pane, expand **Measures**, and then expand Sales.</span></span>  
  
7.  <span data-ttu-id="c4024-373">Faites glisser la mesure Sales Amount vers la zone **Expression** , tapez le caractère de soustraction (-), puis faites glisser la mesure Sales Return Amount vers la zone **Expression** ; placez-la après le caractère de soustraction.</span><span class="sxs-lookup"><span data-stu-id="c4024-373">Drag the Sales Amount measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Amount measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="c4024-374">Le code suivant montre l'expression :</span><span class="sxs-lookup"><span data-stu-id="c4024-374">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Amount] - [Measures].[Sales Return Amount]  
    ```  
  
8.  <span data-ttu-id="c4024-375">Dans la zone **Nom** , tapez  **Net Sales**, puis cliquez sur **OK**. Le volet Membres calculés contient le membre calculé **Net Sales** .</span><span class="sxs-lookup"><span data-stu-id="c4024-375">In the **Name** box, type  **Net Sales**, and then click **OK**.The Calculated Members pane lists the **Net Sales** calculated member.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="MSkip"></a><span data-ttu-id="c4024-376">Pour créer le DataSet</span><span class="sxs-lookup"><span data-stu-id="c4024-376">To create the dataset</span></span>  
  
1.  <span data-ttu-id="c4024-377">À partir de la dimension Channel, faites glisser Channel Name vers le volet de données.</span><span class="sxs-lookup"><span data-stu-id="c4024-377">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="c4024-378">À partir de la dimension Product, faites glisser Product Category Name vers le volet de données, et placez-le à droite de Channel Name.</span><span class="sxs-lookup"><span data-stu-id="c4024-378">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="c4024-379">À partir de **Membres calculés**, faites glisser `Net QTY` vers le volet de données, puis placez-le à droite de Product Category Name.</span><span class="sxs-lookup"><span data-stu-id="c4024-379">From **Calculated Members**, drag `Net QTY` to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="c4024-380">À partir de Membres calculés, faites glisser Net Sales vers le volet de données, puis placez-le à droite de `Net QTY`.</span><span class="sxs-lookup"><span data-stu-id="c4024-380">From Calculated Members, drag Net Sales to the data pane, and then place it to the right of `Net QTY`.</span></span>  
  
5.  <span data-ttu-id="c4024-381">Dans la barre d’outils du concepteur de requêtes, cliquez sur **exécuter ( !)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-381">On the query designer toolbar, click **Run (!)**.</span></span>  
  
     <span data-ttu-id="c4024-382">Passez en revue le jeu de résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="c4024-382">Review the query result set.</span></span>  
  
6.  <span data-ttu-id="c4024-383">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c4024-383">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="MLayout"></a><span data-ttu-id="c4024-384">1C.</span><span class="sxs-lookup"><span data-stu-id="c4024-384">1c.</span></span> <span data-ttu-id="c4024-385">Organiser les données dans des groupes</span><span class="sxs-lookup"><span data-stu-id="c4024-385">Organize Data into Groups</span></span>  
 <span data-ttu-id="c4024-386">Lorsque vous sélectionnez les champs dans lesquels regrouper des données, vous concevez une matrice dont les lignes et les colonnes affichent des données de détail et des données agrégées.</span><span class="sxs-lookup"><span data-stu-id="c4024-386">When you select the fields on which to group data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="c4024-387">Pour organiser les données en groupes</span><span class="sxs-lookup"><span data-stu-id="c4024-387">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="c4024-388">Dans la page **Organiser les champs** , faites glisser Product_Category_Name vers **Groupes de ligne**.</span><span class="sxs-lookup"><span data-stu-id="c4024-388">On the **Arrange fields** page, drag Product_Category_Name to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="c4024-389">Faites glisser Channel_Name vers **Groupes de colonnes**.</span><span class="sxs-lookup"><span data-stu-id="c4024-389">Drag Channel_Name to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="c4024-390">Faites glisser `Net_QTY` vers **Valeurs**.</span><span class="sxs-lookup"><span data-stu-id="c4024-390">Drag `Net_QTY` to **Values**.</span></span>  
  
     <span data-ttu-id="c4024-391">`Net_QTY` est agrégé automatiquement par la fonction Sum, l’agrégat par défaut des champs numériques.</span><span class="sxs-lookup"><span data-stu-id="c4024-391">`Net_QTY` is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="c4024-392">La valeur est `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="c4024-392">The value is `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="c4024-393">Pour consulter les autres fonctions d'agrégation disponibles, ouvrez la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="c4024-393">To view the other aggregate functions available, open the drop-down list.</span></span> <span data-ttu-id="c4024-394">Ne modifiez pas la fonction d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="c4024-394">Do not change the aggregate function.</span></span>  
  
4.  <span data-ttu-id="c4024-395">Faites glisser `Net_Sales_Return` vers **Valeurs** et placez-le sous `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="c4024-395">Drag `Net_Sales_Return` to **Values** and then place it below `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="c4024-396">Les étapes 3 et 4 spécifient les données à afficher dans la matrice.</span><span class="sxs-lookup"><span data-stu-id="c4024-396">Steps 3 and 4 specify the data to display in the matrix.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="MTotals"></a><span data-ttu-id="c4024-397">1D.</span><span class="sxs-lookup"><span data-stu-id="c4024-397">1d.</span></span> <span data-ttu-id="c4024-398">Ajouter des sous-totaux et des totaux</span><span class="sxs-lookup"><span data-stu-id="c4024-398">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="c4024-399">Vous pouvez afficher des sous-totaux et des totaux généraux dans les rapports.</span><span class="sxs-lookup"><span data-stu-id="c4024-399">You can show subtotals and grand totals in reports.</span></span> <span data-ttu-id="c4024-400">Les données dans le rapport principal s'affichent sous la forme d'un indicateur ; vous allez supprimer le total général après avoir exécuté l'assistant.</span><span class="sxs-lookup"><span data-stu-id="c4024-400">The data in the main report displays as an indicator; you will remove the grand total after you complete the wizard.</span></span>  
  
#### <a name="to-add-subtotals-and-grand-totals"></a><span data-ttu-id="c4024-401">Pour ajouter des sous-totaux et des totaux généraux</span><span class="sxs-lookup"><span data-stu-id="c4024-401">To add subtotals and grand totals</span></span>  
  
1.  <span data-ttu-id="c4024-402">Dans la page **Choisir la disposition** , sous **Options**, vérifiez que **Afficher les sous-totaux et les totaux généraux** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c4024-402">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="c4024-403">Le volet Aperçu de l'Assistant affiche une matrice avec quatre lignes.</span><span class="sxs-lookup"><span data-stu-id="c4024-403">The wizard Preview pane displays a matrix with four rows.</span></span>  <span data-ttu-id="c4024-404">Lorsque vous exécutez le rapport, chaque ligne s'affiche de la manière suivante : la première ligne correspond au groupe de colonnes, la seconde ligne aux titres de colonnes, la troisième ligne contient les données de catégories de produits (`[Sum(Net_ QTY)]` et `[Sum(Net_Sales)]`, tandis que la quatrième ligne indique les totaux.</span><span class="sxs-lookup"><span data-stu-id="c4024-404">When you run the report, each row will display in the following way: The first row is the column group, the second row contains the column headings, the third row contains the product category data (`[Sum(Net_ QTY)]` and `[Sum(Net_Sales)]`, and the fourth row contains the totals.</span></span>  
  
2.  <span data-ttu-id="c4024-405">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c4024-405">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="MStyle"></a><span data-ttu-id="c4024-406">1La.</span><span class="sxs-lookup"><span data-stu-id="c4024-406">1e.</span></span> <span data-ttu-id="c4024-407">Choisir un style</span><span class="sxs-lookup"><span data-stu-id="c4024-407">Choose a Style</span></span>  
 <span data-ttu-id="c4024-408">Appliquez le style Ardoise au rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-408">Apply the Slate style to the report.</span></span> <span data-ttu-id="c4024-409">Il s'agit du même style que celui utilisé par le rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="c4024-409">This is the same style that the drillthrough report uses.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="c4024-410">Pour spécifier un style</span><span class="sxs-lookup"><span data-stu-id="c4024-410">To specify a style</span></span>  
  
1.  <span data-ttu-id="c4024-411">Dans la page **choisir un style** , dans le volet styles, sélectionnez ardoise.</span><span class="sxs-lookup"><span data-stu-id="c4024-411">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="c4024-412">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="c4024-412">Click **Finish**.</span></span>  
  
3.  <span data-ttu-id="c4024-413">Pour afficher un aperçu du rapport, cliquez sur **Exécuter (!)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-413">To preview the report, click **Run**.</span></span>  
  
##  <a name="2-remove-the-grand-total-row"></a><a name="MGrandTotal"></a><span data-ttu-id="c4024-414">2. supprimer la ligne de total général</span><span class="sxs-lookup"><span data-stu-id="c4024-414">2. Remove the Grand Total Row</span></span>  
 <span data-ttu-id="c4024-415">Les valeurs de données sont affichées sous forme d'états d'indicateur, avec les totaux des groupes de colonnes.</span><span class="sxs-lookup"><span data-stu-id="c4024-415">The data values are shown as indictor states, including the column group totals.</span></span> <span data-ttu-id="c4024-416">Supprimez la ligne qui affiche le total général.</span><span class="sxs-lookup"><span data-stu-id="c4024-416">Remove the row that displays the grand total.</span></span>  
  
#### <a name="to-remove-the-grand-total-row"></a><span data-ttu-id="c4024-417">Pour supprimer la ligne de total général</span><span class="sxs-lookup"><span data-stu-id="c4024-417">To remove the grand total row</span></span>  
  
1.  <span data-ttu-id="c4024-418">Cliquez sur Conception pour basculer en mode **Conception**.</span><span class="sxs-lookup"><span data-stu-id="c4024-418">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c4024-419">Cliquez sur la ligne Total (la dernière ligne dans la matrice), cliquez avec le bouton droit, puis cliquez sur **Supprimer les lignes**.</span><span class="sxs-lookup"><span data-stu-id="c4024-419">Click the Total row (the last row in the matrix), right-click, and then click **Delete Rows**.</span></span>  
  
3.  <span data-ttu-id="c4024-420">Pour afficher un aperçu du rapport, cliquez sur **Exécuter (!)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-420">To preview the report, click **Run**.</span></span>  
  
##  <a name="3-configure-text-box-action-for-drillthrough"></a><a name="MDrillthrough"></a><span data-ttu-id="c4024-421">3. configurer l’action de zone de texte pour l’extraction</span><span class="sxs-lookup"><span data-stu-id="c4024-421">3. Configure Text Box Action for Drillthrough</span></span>  
 <span data-ttu-id="c4024-422">Pour activer l'extraction, spécifiez une action sur une zone de texte dans le rapport principal.</span><span class="sxs-lookup"><span data-stu-id="c4024-422">To enable the drillthrough, specify an action on a text box in the main report.</span></span>  
  
#### <a name="to-enable-an-action"></a><span data-ttu-id="c4024-423">Pour activer une action</span><span class="sxs-lookup"><span data-stu-id="c4024-423">To enable an action</span></span>  
  
1.  <span data-ttu-id="c4024-424">Cliquez sur Conception pour basculer en mode **Conception**.</span><span class="sxs-lookup"><span data-stu-id="c4024-424">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c4024-425">Cliquez avec le bouton droit dans la cellule qui contient Product_Category_Name, puis sélectionnez **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="c4024-425">Right-click the cell that contains Product_Category_Name, and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="c4024-426">Cliquez sur l'onglet **Action**.</span><span class="sxs-lookup"><span data-stu-id="c4024-426">Click the **Action** tab.</span></span>  
  
4.  <span data-ttu-id="c4024-427">Sélectionnez **atteindre le rapport.**</span><span class="sxs-lookup"><span data-stu-id="c4024-427">Select **Go to report.**</span></span>  
  
5.  <span data-ttu-id="c4024-428">Dans **Spécifier un rapport**, cliquez sur **Parcourir**, puis recherchez le rapport d’extraction nommé ResellerVSOnlineDrillthrough.</span><span class="sxs-lookup"><span data-stu-id="c4024-428">In **Specify a report**, click **Browse**, and then locate the drillthrough report named ResellerVSOnlineDrillthrough.</span></span>  
  
6.  <span data-ttu-id="c4024-429">Pour ajouter un paramètre pour exécuter le rapport d’extraction, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c4024-429">To add a parameter to run the drillthrough report, click **Add**.</span></span>  
  
7.  <span data-ttu-id="c4024-430">Dans la liste **Nom** , sélectionnez ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="c4024-430">In the **Name** list, select ProductProductCategoryName.</span></span>  
  
8.  <span data-ttu-id="c4024-431">Dans la zone **Valeur**, tapez `[Product_Category_Name.UniqueName]`.</span><span class="sxs-lookup"><span data-stu-id="c4024-431">In **Value**, type `[Product_Category_Name.UniqueName]`.</span></span>  
  
     <span data-ttu-id="c4024-432">Product_Category_Name est un champ du dataset.</span><span class="sxs-lookup"><span data-stu-id="c4024-432">Product_Category_Name is a field in the dataset.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c4024-433">Vous devez inclure la propriété `UniqueName` car l'action d'extraction requiert une valeur unique.</span><span class="sxs-lookup"><span data-stu-id="c4024-433">You must include the `UniqueName` property because the drillthrough action requires a unique value.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-format-the-drillthrough-field"></a><span data-ttu-id="c4024-434">Pour mettre en forme le champ d'extraction</span><span class="sxs-lookup"><span data-stu-id="c4024-434">To format the drillthrough field</span></span>  
  
1.  <span data-ttu-id="c4024-435">Cliquez avec le bouton droit dans la cellule qui contient `Product_Category_Name`, puis cliquez sur **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="c4024-435">Right-click the cell that contains the `Product_Category_Name`, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="c4024-436">Cliquez sur l'onglet **Police** .</span><span class="sxs-lookup"><span data-stu-id="c4024-436">Click the **Font** tab.</span></span>  
  
3.  <span data-ttu-id="c4024-437">Dans la liste **Effets** , sélectionnez **Souligné**.</span><span class="sxs-lookup"><span data-stu-id="c4024-437">In the **Effects** list, select **Underline**.</span></span>  
  
4.  <span data-ttu-id="c4024-438">Dans la liste **Couleur** , sélectionnez **Bleu**.</span><span class="sxs-lookup"><span data-stu-id="c4024-438">In the **Color** list, select **Blue**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c4024-439">Cliquez sur **Exécuter**pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-439">To preview your report, click **Run**.</span></span>  
  
 <span data-ttu-id="c4024-440">Les noms des catégories de produits présentent le format de lien courant (bleu et souligné).</span><span class="sxs-lookup"><span data-stu-id="c4024-440">The product category names are in the common link format (blue and underlined).</span></span>  
  
##  <a name="4-replace-numeric-values-with-indicators"></a><a name="MIndicators"></a><span data-ttu-id="c4024-441">4. remplacer des valeurs numériques par des indicateurs</span><span class="sxs-lookup"><span data-stu-id="c4024-441">4. Replace Numeric Values with Indicators</span></span>  
 <span data-ttu-id="c4024-442">Utilisez des indicateurs pour afficher l'état de quantités et de ventes pour les canaux en ligne et les revendeurs.</span><span class="sxs-lookup"><span data-stu-id="c4024-442">Use indicators to show the state of quantities and sales for Online and Reseller channels.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-qty-values"></a><span data-ttu-id="c4024-443">Pour ajouter un indicateur pour les valeurs de quantité nette</span><span class="sxs-lookup"><span data-stu-id="c4024-443">To add an indicator for Net QTY values</span></span>  
  
1.  <span data-ttu-id="c4024-444">Cliquez sur Conception pour basculer en mode **Conception**.</span><span class="sxs-lookup"><span data-stu-id="c4024-444">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c4024-445">Sur le ruban, cliquez sur l’icône **Rectangle** , puis cliquez dans la cellule `[Sum(Net QTY)]` dans le groupe de lignes `[Product_Category_Name]` dans le groupe de colonnes `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="c4024-445">On the ribbon, click the **Rectangle** icon, and then click in the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
3.  <span data-ttu-id="c4024-446">Sur le ruban, cliquez sur l’icône **Indicateur** , puis cliquez à l’intérieur du rectangle.</span><span class="sxs-lookup"><span data-stu-id="c4024-446">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span> <span data-ttu-id="c4024-447">La boîte de dialogue **Sélectionner un type d’indicateur** s’affiche ; l’indicateur **Directionnel** y est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c4024-447">The **Select Indicator Type** dialog box opens with the **Directional** indicator selected.</span></span>  
  
4.  <span data-ttu-id="c4024-448">Cliquez sur le type **3 Signes** , puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-448">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="c4024-449">Cliquez avec le bouton droit sur l’indicateur et, dans le volet Données de la jauge, cliquez sur la flèche vers le bas en regard de **(Non spécifié)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-449">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="c4024-450">Sélectionnez `Net_QTY`.</span><span class="sxs-lookup"><span data-stu-id="c4024-450">Select `Net_QTY`.</span></span>  
  
6.  <span data-ttu-id="c4024-451">Répétez les étapes 2 à 5 pour la cellule `[Sum(Net QTY)]` dans le groupe de lignes `[Product_Category_Name]` dans **Total**.</span><span class="sxs-lookup"><span data-stu-id="c4024-451">Repeat steps 2 through 5 for the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-sales-values"></a><span data-ttu-id="c4024-452">Pour ajouter un indicateur pour les valeurs de chiffre d'affaires net</span><span class="sxs-lookup"><span data-stu-id="c4024-452">To add an indicator for Net Sales values</span></span>  
  
1.  <span data-ttu-id="c4024-453">Sur le ruban, cliquez sur l’icône **Rectangle** , puis cliquez à l’intérieur de la cellule `[Sum(Net_Sales)]` dans le groupe de lignes `[Product_Category_Name]` dans le groupe de colonnes `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="c4024-453">On the ribbon, click the **Rectangle** icon, and then click inside the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
2.  <span data-ttu-id="c4024-454">Sur le ruban, cliquez sur l’icône **Indicateur** , puis cliquez à l’intérieur du rectangle.</span><span class="sxs-lookup"><span data-stu-id="c4024-454">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span>  
  
3.  <span data-ttu-id="c4024-455">Cliquez sur le type **3 Signes** , puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4024-455">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="c4024-456">Cliquez avec le bouton droit sur l’indicateur et, dans le volet Données de la jauge, cliquez sur la flèche vers le bas en regard de **(Non spécifié)**.</span><span class="sxs-lookup"><span data-stu-id="c4024-456">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="c4024-457">Sélectionnez `Net_Sales`.</span><span class="sxs-lookup"><span data-stu-id="c4024-457">Select `Net_Sales`.</span></span>  
  
5.  <span data-ttu-id="c4024-458">Répétez les étapes 1 à 4 pour la cellule `[Sum(Net_Sales)]` dans le groupe de lignes `[Product_Category_Name]` dans **Total**.</span><span class="sxs-lookup"><span data-stu-id="c4024-458">Repeat steps 1 through 4 for the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
6.  <span data-ttu-id="c4024-459">Cliquez sur **Exécuter**pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-459">To preview your report, click **Run**.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="MParameter"></a><span data-ttu-id="c4024-460">5. mettre à jour les propriétés des paramètres</span><span class="sxs-lookup"><span data-stu-id="c4024-460">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="c4024-461">Par défaut, les paramètres sont visibles, ce qui n'est pas approprié pour ce rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-461">By default, parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="c4024-462">Vous allez mettre à jour les propriétés de paramètre afin de rendre ce dernier interne au rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-462">You will update the parameter properties to make the parameter internal.</span></span>  
  
#### <a name="to-make-the-parameter-internal"></a><span data-ttu-id="c4024-463">Pour rendre le paramètre interne</span><span class="sxs-lookup"><span data-stu-id="c4024-463">To make the parameter internal</span></span>  
  
1.  <span data-ttu-id="c4024-464">Dans le volet des données de rapport, développez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="c4024-464">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="c4024-465">Cliquez avec le bouton droit sur `@ProductProductCategoryName,` , puis sélectionnez **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="c4024-465">Right-click `@ProductProductCategoryName,` and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="c4024-466">Sous l’onglet **Général** , cliquez sur **Interne**.</span><span class="sxs-lookup"><span data-stu-id="c4024-466">On the **General** tab, click **Internal**.</span></span>  
  
4.  <span data-ttu-id="c4024-467">Cliquez éventuellement sur les onglets **Valeurs disponibles** et **Valeurs par défaut** et passez en revue les options qu’ils contiennent.</span><span class="sxs-lookup"><span data-stu-id="c4024-467">Optionally, click the **Available Values** and **Default Values** tabs and review their options.</span></span> <span data-ttu-id="c4024-468">Ne modifiez aucune des options de ces onglets.</span><span class="sxs-lookup"><span data-stu-id="c4024-468">Do not change any options on these tabs.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-add-a-report-title"></a><a name="MTitle"></a><span data-ttu-id="c4024-469">6. Ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="c4024-469">6. Add a Report Title</span></span>  
 <span data-ttu-id="c4024-470">Ajoutez un titre au rapport principal.</span><span class="sxs-lookup"><span data-stu-id="c4024-470">Add a title to the main report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="c4024-471">Pour ajouter un titre de rapport</span><span class="sxs-lookup"><span data-stu-id="c4024-471">To add a report title</span></span>  
  
1.  <span data-ttu-id="c4024-472">Dans l'aire de conception, cliquez sur **Cliquez pour ajouter un titre**.</span><span class="sxs-lookup"><span data-stu-id="c4024-472">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="c4024-473">Tapez **2009 Product Category Sales: Online and Reseller Category:**.</span><span class="sxs-lookup"><span data-stu-id="c4024-473">Type **2009 Product Category Sales: Online and Reseller Category:**.</span></span>  
  
3.  <span data-ttu-id="c4024-474">Sélectionnez le texte que vous avez tapé.</span><span class="sxs-lookup"><span data-stu-id="c4024-474">Select the text you typed.</span></span>  
  
4.  <span data-ttu-id="c4024-475">Sous l’onglet **Accueil** du ruban, dans le groupe Police, sélectionnez la police **Times New Roman** , la taille **16pt** et les styles **Gras** et **Italique** .</span><span class="sxs-lookup"><span data-stu-id="c4024-475">On the **Home** tab of the ribbon, in the Font group, select the **Times New Roman** font, **16pt** size, and the **Bold** and **Italic** styles.</span></span>  
  
5.  <span data-ttu-id="c4024-476">Cliquez sur **Exécuter**pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-476">To preview your report, click **Run**.</span></span>  
  
##  <a name="7-save-the-main-report-to-a-sharepoint-library"></a><a name="MSave"></a><span data-ttu-id="c4024-477">7. enregistrer le rapport principal dans une bibliothèque SharePoint</span><span class="sxs-lookup"><span data-stu-id="c4024-477">7. Save the Main Report to a SharePoint Library</span></span>  
 <span data-ttu-id="c4024-478">Enregistrez le rapport principal dans une bibliothèque SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c4024-478">Save the main report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="c4024-479">Pour enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="c4024-479">To save the report</span></span>  
  
1.  <span data-ttu-id="c4024-480">Cliquez sur Conception pour basculer en mode **Conception**.</span><span class="sxs-lookup"><span data-stu-id="c4024-480">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="c4024-481">À partir du bouton Générateur de rapports, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c4024-481">From the Report Builder button, click **Save**.</span></span>  
  
3.  <span data-ttu-id="c4024-482">Cliquez éventuellement sur **Sites et serveurs récents**pour afficher une liste de serveurs de rapports et de sites SharePoint récemment utilisés.</span><span class="sxs-lookup"><span data-stu-id="c4024-482">Optionally, to show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
4.  <span data-ttu-id="c4024-483">Sélectionnez ou tapez le nom du site SharePoint sur lequel vous êtes autorisé à enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="c4024-483">Select or type the name of the SharePoint site where you have permission to save reports.</span></span> <span data-ttu-id="c4024-484">L'URL de la bibliothèque SharePoint présente la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="c4024-484">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
5.  <span data-ttu-id="c4024-485">Naviguez jusqu'à la bibliothèque où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="c4024-485">Navigate to the library where you want to save the report.</span></span>  
  
6.  <span data-ttu-id="c4024-486">Dans la zone **Nom**, remplacez le nom par défaut par **ResellerVSOnlineMain**.</span><span class="sxs-lookup"><span data-stu-id="c4024-486">In **Name**, replace the default name with **ResellerVSOnlineMain**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c4024-487">Enregistrez le rapport principal au même emplacement que celui où vous avez enregistré le rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="c4024-487">Save the main report to the same location where you saved the drillthrough report.</span></span> <span data-ttu-id="c4024-488">Pour enregistrer les rapports principal et d’extraction dans des bibliothèques ou des sites différents, confirmez que l’action **Atteindre le rapport** du rapport principal pointe vers l’emplacement correct du rapport d’extraction.</span><span class="sxs-lookup"><span data-stu-id="c4024-488">To save the main and drillthrough reports to different sites or libraries, confirm that the **Go to report** action in the main report, points to the correct location of the drillthrough report.</span></span>  
  
7.  <span data-ttu-id="c4024-489">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c4024-489">Click **Save**.</span></span>  
  
##  <a name="8-run-the-main-and-drillthrough-reports"></a><a name="MRunReports"></a><span data-ttu-id="c4024-490">8. exécuter les rapports principal et d’extraction</span><span class="sxs-lookup"><span data-stu-id="c4024-490">8. Run the Main and Drillthrough Reports</span></span>  
 <span data-ttu-id="c4024-491">Exécutez le rapport principal, puis cliquez sur des valeurs dans la colonne de catégorie de produit afin d'exécuter le rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="c4024-491">Run the main report, and then click values in the product category column to run the drillthrough report.</span></span>  
  
#### <a name="to-run-the-reports"></a><span data-ttu-id="c4024-492">Pour exécuter les rapports</span><span class="sxs-lookup"><span data-stu-id="c4024-492">To run the reports</span></span>  
  
1.  <span data-ttu-id="c4024-493">Ouvrez la bibliothèque SharePoint où sont enregistrés les rapports.</span><span class="sxs-lookup"><span data-stu-id="c4024-493">Open the SharePoint library where the reports are saved.</span></span>  
  
2.  <span data-ttu-id="c4024-494">Double-cliquez sur ResellerVSOnlineMain.</span><span class="sxs-lookup"><span data-stu-id="c4024-494">Double-click ResellerVSOnlineMain.</span></span>  
  
     <span data-ttu-id="c4024-495">Le rapport est exécuté et affiche les informations relatives aux ventes de catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="c4024-495">The report runs and displays product category sales information.</span></span>  
  
3.  <span data-ttu-id="c4024-496">Cliquez sur le lien **Games and Toys** dans la colonne qui contient les noms des catégories de produits.</span><span class="sxs-lookup"><span data-stu-id="c4024-496">Click the **Games and Toys** link in the column that contains product category names.</span></span>  
  
     <span data-ttu-id="c4024-497">Le rapport d'extraction est exécuté et affiche uniquement les valeurs pour la catégorie de produit Games and Toys.</span><span class="sxs-lookup"><span data-stu-id="c4024-497">The drillthrough report runs, displaying only the values for the Games and Toys product category.</span></span>  
  
4.  <span data-ttu-id="c4024-498">Pour revenir au rapport principal, cliquez sur le bouton Précédent dans Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c4024-498">To return to the main report, click the Internet Explorer back button.</span></span>  
  
5.  <span data-ttu-id="c4024-499">Explorez éventuellement les autres catégories de produits en cliquant sur leur nom.</span><span class="sxs-lookup"><span data-stu-id="c4024-499">Optionally, explore other product categories by clicking their names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4024-500">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4024-500">See Also</span></span>  
 [<span data-ttu-id="c4024-501">Didacticiels &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="c4024-501">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
