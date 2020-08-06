---
title: 'Didacticiel : mettre en forme du texte (Générateur de rapports) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 67d8513e-8a70-464b-b87f-e91d010cfd82
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c96b500f8aa30b77c78f75ccd1342398fd44eb2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706112"
---
# <a name="tutorial-format-text-report-builder"></a><span data-ttu-id="f5d95-102">Didacticiel : mettre en forme du texte (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="f5d95-102">Tutorial: Format Text (Report Builder)</span></span>
  <span data-ttu-id="f5d95-103">Dans ce didacticiel, vous pouvez vous entraîner à mettre en forme le texte de plusieurs façons.</span><span class="sxs-lookup"><span data-stu-id="f5d95-103">In this tutorial, you can practice formatting text in various ways.</span></span> <span data-ttu-id="f5d95-104">Après avoir configuré le rapport vierge avec la source de données et le dataset, vous pourrez choisir les étapes que vous souhaitez explorer.</span><span class="sxs-lookup"><span data-stu-id="f5d95-104">After you set up the blank report with the data source and dataset, you can pick and choose the steps that you want to explore.</span></span>  
  
 <span data-ttu-id="f5d95-105">L'illustration suivante montre un rapport similaire à celui que vous allez créer.</span><span class="sxs-lookup"><span data-stu-id="f5d95-105">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="f5d95-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span><span class="sxs-lookup"><span data-stu-id="f5d95-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span></span>  
  
 <span data-ttu-id="f5d95-107">Dans une étape, vous allez sciemment générer une erreur afin de voir pourquoi il s'agit d'une erreur.</span><span class="sxs-lookup"><span data-stu-id="f5d95-107">In one step, you make a mistake on purpose so you can see why it is a mistake.</span></span> <span data-ttu-id="f5d95-108">Vous corrigerez ensuite l'erreur pour obtenir l'effet souhaité.</span><span class="sxs-lookup"><span data-stu-id="f5d95-108">Then you correct the mistake to achieve the desired effect.</span></span>  
  
 <span data-ttu-id="f5d95-109">Une version améliorée du rapport créé dans ce didacticiel est disponible sous forme d'exemple de rapport Générateur de rapports de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5d95-109">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="f5d95-110">Pour plus d’informations sur le téléchargement de cet exemple de rapport et d’autres, consultez [Générateur de rapports exemples de rapports](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="f5d95-110">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="f5d95-111">Ce que vous allez apprendre</span><span class="sxs-lookup"><span data-stu-id="f5d95-111">What You Will Learn</span></span>  
  
### <a name="set-up-the-report"></a><span data-ttu-id="f5d95-112">Configurer le rapport</span><span class="sxs-lookup"><span data-stu-id="f5d95-112">Set Up the Report</span></span>  
 1. [<span data-ttu-id="f5d95-113">Créer un rapport vierge avec une source de données et un DataSet</span><span class="sxs-lookup"><span data-stu-id="f5d95-113">Create a Blank Report with a Data Source and Dataset</span></span>](#CreateReport)  
  
 2. [<span data-ttu-id="f5d95-114">Ajouter un champ à l'aire de conception du rapport (de façon incorrecte, puis correcte)</span><span class="sxs-lookup"><span data-stu-id="f5d95-114">Add a Field to the Report Design Surface (Incorrectly, then Correctly)</span></span>](#AddField)  
  
 3. [<span data-ttu-id="f5d95-115">Ajoutez une table au rapport Aire de conception</span><span class="sxs-lookup"><span data-stu-id="f5d95-115">Add a Table to the Report Design Surface</span></span>](#AddTable)  
  
### <a name="pick-and-choose"></a><span data-ttu-id="f5d95-116">Choisir</span><span class="sxs-lookup"><span data-stu-id="f5d95-116">Pick and Choose</span></span>  
 [<span data-ttu-id="f5d95-117">Ajouter un lien hypertexte au rapport</span><span class="sxs-lookup"><span data-stu-id="f5d95-117">Add a Hyperlink to the Report</span></span>](#AddHyperlink)  
  
 [<span data-ttu-id="f5d95-118">Faire pivoter le texte dans le rapport</span><span class="sxs-lookup"><span data-stu-id="f5d95-118">Rotate Text in the Report</span></span>](#RotateText)  
  
 [<span data-ttu-id="f5d95-119">Affichage de texte avec une mise en forme HTML</span><span class="sxs-lookup"><span data-stu-id="f5d95-119">Displaying Text with HTML Formatting</span></span>](#FormatHTML)  
  
 [<span data-ttu-id="f5d95-120">Mettre en forme la devise</span><span class="sxs-lookup"><span data-stu-id="f5d95-120">Format Currency</span></span>](#FormatCurrency)  
  
 [<span data-ttu-id="f5d95-121">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="f5d95-121">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="f5d95-122">Durée estimée pour effectuer le didacticiel : 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="f5d95-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5d95-123">Spécifications</span><span class="sxs-lookup"><span data-stu-id="f5d95-123">Requirements</span></span>  
 <span data-ttu-id="f5d95-124">Pour plus d’informations sur les spécifications, consultez [Éléments requis pour les didacticiels &#40;Générateur de rapports&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="f5d95-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="create-a-blank-report-with-a-data-source-and-dataset"></a><a name="CreateReport"></a><span data-ttu-id="f5d95-125">Créer un rapport vierge avec une source de données et un DataSet</span><span class="sxs-lookup"><span data-stu-id="f5d95-125">Create a Blank Report with a Data Source and Dataset</span></span>  
  
#### <a name="to-create-a-blank-report"></a><span data-ttu-id="f5d95-126">Pour créer un rapport vierge</span><span class="sxs-lookup"><span data-stu-id="f5d95-126">To create a blank report</span></span>  
  
1.  <span data-ttu-id="f5d95-127">Cliquez sur **Démarrer**, pointez sur **programmes**, sur [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Générateur de rapports**, puis cliquez sur **Générateur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-127">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f5d95-128">La boîte de dialogue **Mise en route** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f5d95-128">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="f5d95-129">Si elle ne s'affiche pas, à partir du bouton Générateur de rapports, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-129">If it does not, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="f5d95-130">Dans le volet gauche de la boîte de dialogue **Mise en route** , assurez-vous que **Nouveau rapport** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f5d95-130">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="f5d95-131">Dans le volet droit, cliquez sur **Rapport vierge**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-131">In the right pane, click **Blank Report**.</span></span>  
  
#### <a name="to-create-a-data-source"></a><span data-ttu-id="f5d95-132">Pour créer une source de données</span><span class="sxs-lookup"><span data-stu-id="f5d95-132">To create a data source</span></span>  
  
1.  <span data-ttu-id="f5d95-133">Dans le volet données du rapport, cliquez sur **nouveau**, puis sur **source de données**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-133">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="f5d95-134">Dans la zone **Nom** , tapez **TextDataSource**</span><span class="sxs-lookup"><span data-stu-id="f5d95-134">In the **Name** box, type: **TextDataSource**</span></span>  
  
3.  <span data-ttu-id="f5d95-135">Cliquez sur **Utiliser une connexion incorporée dans mon rapport**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-135">Click **Use a connection embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="f5d95-136">Vérifiez que le type de connexion est Microsoft SQL Server, puis dans la zone **chaîne de connexion** , tapez : source de \*\*données = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="f5d95-136">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f5d95-137">L’expression \<servername>, par exemple Rapport001, spécifie un ordinateur sur lequel une instance du moteur de base de données SQL Server est installée.</span><span class="sxs-lookup"><span data-stu-id="f5d95-137">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="f5d95-138">Ce didacticiel n'a pas besoin de données spécifiques. Il a juste besoin d'une connexion à une base de données [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f5d95-138">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="f5d95-139">Si une connexion à une source de données est déjà répertoriée sous **Connexions à la source de données**, vous pouvez la sélectionner et passer à la procédure suivante, « Pour créer un dataset ».</span><span class="sxs-lookup"><span data-stu-id="f5d95-139">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to the next procedure, "To create a dataset."</span></span> <span data-ttu-id="f5d95-140">Pour plus d’informations, consultez [Autres manières d’obtenir une connexion de données &#40;Générateur de rapports&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="f5d95-140">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-create-a-dataset"></a><span data-ttu-id="f5d95-141">Pour créer un dataset</span><span class="sxs-lookup"><span data-stu-id="f5d95-141">To create a dataset</span></span>  
  
1.  <span data-ttu-id="f5d95-142">Dans le volet des données de rapport, cliquez sur **Nouveau**, puis sur **Dataset**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-142">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>  
  
2.  <span data-ttu-id="f5d95-143">Vérifiez que la source de données est **TextDataSource**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-143">Verify that the data source is **TextDataSource**.</span></span>  
  
3.  <span data-ttu-id="f5d95-144">Dans la zone **Nom** , tapez **TextDataset**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-144">In the **Name** box, type: **TextDataset.**</span></span>  
  
4.  <span data-ttu-id="f5d95-145">Vérifiez que le type de requête **Texte** est sélectionné, puis cliquez sur **Concepteur de requêtes**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-145">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>  
  
5.  <span data-ttu-id="f5d95-146">Cliquez sur **Modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-146">Click **Edit as Text**.</span></span>  
  
6.  <span data-ttu-id="f5d95-147">Collez la requête suivante dans le volet de requête :</span><span class="sxs-lookup"><span data-stu-id="f5d95-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    ```  
  
7.  <span data-ttu-id="f5d95-148">Cliquez sur Exécuter (**!**) pour exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="f5d95-148">Click Run (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="f5d95-149">Les résultats de la requête sont les données qui peuvent être affichées dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="f5d95-149">The query results are the data available to display in your report.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="add-a-field-to-the-report-design-surface"></a><a name="AddField"></a><span data-ttu-id="f5d95-150">Ajoutez un champ au rapport Aire de conception</span><span class="sxs-lookup"><span data-stu-id="f5d95-150">Add a Field to the Report Design Surface</span></span>  
 <span data-ttu-id="f5d95-151">Si vous souhaitez qu'un champ de votre dataset apparaisse dans un rapport, votre premier réflexe peut être de le faire glisser directement sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="f5d95-151">If you want a field from your dataset to appear in a report, your first impulse may be to drag it directly to the design surface.</span></span> <span data-ttu-id="f5d95-152">Cet exercice montre pourquoi cela ne fonctionne pas et ce que vous devez faire à la place.</span><span class="sxs-lookup"><span data-stu-id="f5d95-152">This exercise points out why that doesn't work and what to do instead.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-wrong-result"></a><span data-ttu-id="f5d95-153">Pour ajouter un champ au rapport (et obtenir le résultat incorrect)</span><span class="sxs-lookup"><span data-stu-id="f5d95-153">To add a field to the report (and get the wrong result)</span></span>  
  
1.  <span data-ttu-id="f5d95-154">Faites glisser le champ **FullName** du volet Données du rapport vers l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="f5d95-154">Drag the **FullName** field from the Report Data pane to the design surface.</span></span>  
  
     <span data-ttu-id="f5d95-155">Le Générateur de rapports crée une zone de texte contenant une expression, représentée sous la forme \<Expr>.</span><span class="sxs-lookup"><span data-stu-id="f5d95-155">Report Builder creates a text box with an expression in it, represented as \<Expr>.</span></span>  
  
2.  <span data-ttu-id="f5d95-156">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-156">Click **Run**.</span></span>  
  
     <span data-ttu-id="f5d95-157">Notez qu’il n’existe qu’un seul enregistrement, **Fernando Ross**, qui est le premier enregistrement dans la requête par ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="f5d95-157">Note that there is just one record, **Fernando Ross**, which is alphabetically the first record in the query.</span></span> <span data-ttu-id="f5d95-158">Le champ ne se répète pas pour afficher les autres enregistrements.</span><span class="sxs-lookup"><span data-stu-id="f5d95-158">The field does not repeat to show the other records in that field.</span></span>  
  
3.  <span data-ttu-id="f5d95-159">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5d95-159">Click **Design** to return to design view.</span></span>  
  
4.  <span data-ttu-id="f5d95-160">Sélectionnez l’expression \<Expr> dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="f5d95-160">Select the expression \<Expr> in the text box.</span></span>  
  
5.  <span data-ttu-id="f5d95-161">Dans le volet Propriétés, les éléments suivants sont affichés pour la propriété **Valeur** (si le volet Propriétés n’est pas affiché, sous l’onglet **Affichage** , cochez **Propriétés**) :</span><span class="sxs-lookup"><span data-stu-id="f5d95-161">In the Properties pane, for the **Value** property, you see the following (if you don't see the Properties pane, on the **View** tab, check **Properties**):</span></span>  
  
    ```  
    =First(Fields!FullName.Value, "TextDataSet")  
    ```  
  
     <span data-ttu-id="f5d95-162">La fonction `First` permet de récupérer uniquement la première valeur d'un champ, et c'est ce qu'elle a fait.</span><span class="sxs-lookup"><span data-stu-id="f5d95-162">The `First` function is designed to retrieve only the first value in a field, and that is what it has done.</span></span>  
  
     <span data-ttu-id="f5d95-163">Le fait de faire glisser le champ directement sur l'aire de conception a créé une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="f5d95-163">Dragging the field directly to the design surface created a text box.</span></span> <span data-ttu-id="f5d95-164">Les zones de texte par elles-mêmes ne sont pas des régions de données et n'affichent donc pas les données d'un dataset de rapport.</span><span class="sxs-lookup"><span data-stu-id="f5d95-164">Text boxes by themselves are not data regions, so they do not display data from a report dataset.</span></span> <span data-ttu-id="f5d95-165">Les zones de texte dans les régions de données, comme les tableaux, les matrices et les listes, affichent des données.</span><span class="sxs-lookup"><span data-stu-id="f5d95-165">Text boxes in data regions, such as tables, matrices, and lists, do display data.</span></span>  
  
6.  <span data-ttu-id="f5d95-166">Sélectionnez la zone de texte (si l'expression est sélectionnée, appuyez sur Échap pour sélectionner la zone de texte) et appuyez sur la touche Suppr.</span><span class="sxs-lookup"><span data-stu-id="f5d95-166">Select the text box (if you have the expression selected, press ESC to select the text box), and press the DELETE key.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-right-result"></a><span data-ttu-id="f5d95-167">Pour ajouter un champ au rapport (et obtenir le résultat correct)</span><span class="sxs-lookup"><span data-stu-id="f5d95-167">To add a field to the report (and get the right result)</span></span>  
  
1.  <span data-ttu-id="f5d95-168">Sous l’onglet **Insertion** du Ruban, dans la zone **Régions de données** , cliquez sur **Liste**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-168">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List**.</span></span> <span data-ttu-id="f5d95-169">Cliquez sur l'aire de conception, puis faites glisser la souris pour créer une zone d'environ 5 cm de large sur 2,5 cm de haut.</span><span class="sxs-lookup"><span data-stu-id="f5d95-169">Click the design surface, and then drag to create a box that about two inches wide and one inch tall.</span></span>  
  
2.  <span data-ttu-id="f5d95-170">Faites glisser le champ **FullName** du volet Données du rapport vers la zone de liste.</span><span class="sxs-lookup"><span data-stu-id="f5d95-170">Drag the **FullName** field from the Report Data pane to the list box.</span></span>  
  
     <span data-ttu-id="f5d95-171">Cette fois, le Générateur de rapports crée une zone de texte contenant l’expression `[FullName]` .</span><span class="sxs-lookup"><span data-stu-id="f5d95-171">This time Report Builder creates a text box with the expression `[FullName]` in it.</span></span>  
  
3.  <span data-ttu-id="f5d95-172">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-172">Click **Run**.</span></span>  
  
     <span data-ttu-id="f5d95-173">Notez que cette fois, la zone se répète de manière à afficher tous les enregistrements de la requête.</span><span class="sxs-lookup"><span data-stu-id="f5d95-173">Note that this time the box repeats to show all the records in the query.</span></span>  
  
4.  <span data-ttu-id="f5d95-174">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5d95-174">Click **Design** to return to design view.</span></span>  
  
5.  <span data-ttu-id="f5d95-175">Sélectionnez l'expression dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="f5d95-175">Select the expression in the text box.</span></span>  
  
6.  <span data-ttu-id="f5d95-176">Dans le volet Propriétés, les éléments suivants sont affichés pour la propriété **Valeur** :</span><span class="sxs-lookup"><span data-stu-id="f5d95-176">In the Properties pane, for the **Value** property, you see the following:</span></span>  
  
    ```  
    =Fields!FullName.Value  
    ```  
  
     <span data-ttu-id="f5d95-177">En faisant glisser la zone de texte vers la région de données de liste, vous affichez les données du dataset.</span><span class="sxs-lookup"><span data-stu-id="f5d95-177">By dragging the text box to the list data region, you display the data that is in the dataset.</span></span>  
  
7.  <span data-ttu-id="f5d95-178">Sélectionnez la zone de liste et appuyez sur la touche Suppr.</span><span class="sxs-lookup"><span data-stu-id="f5d95-178">Select the list box and press the DELETE key.</span></span>  
  
##  <a name="add-a-table-to-the-report-design-surface"></a><a name="AddTable"></a><span data-ttu-id="f5d95-179">Ajoutez une table au rapport Aire de conception</span><span class="sxs-lookup"><span data-stu-id="f5d95-179">Add a Table to the Report Design Surface</span></span>  
 <span data-ttu-id="f5d95-180">Créez cette table pour avoir un emplacement où placer les liens hypertexte et le texte pivoté.</span><span class="sxs-lookup"><span data-stu-id="f5d95-180">Create this table so that you'll have a place to put hyperlinks and rotated text.</span></span>  
  
#### <a name="to-add-a-table-to-the-report"></a><span data-ttu-id="f5d95-181">Pour ajouter un tableau au rapport</span><span class="sxs-lookup"><span data-stu-id="f5d95-181">To add a table to the report</span></span>  
  
1.  <span data-ttu-id="f5d95-182">Dans le menu **Insérer** , cliquez sur **tableau**, puis sur **Assistant Tableau**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-182">On the **Insert** menu, click **Table**, and then click **Table Wizard**.</span></span>  
  
2.  <span data-ttu-id="f5d95-183">Dans la page **choisir un DataSet** de l’Assistant Nouveau tableau ou nouvelle matrice, cliquez sur **choisir un DataSet existant dans ce rapport ou un dataset partagé**, puis cliquez sur **TextDataset (dans ce rapport)**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-183">On the **Choose a dataset** page of the New Table or Matrix wizard, click **Choose an existing dataset in this report or a shared dataset**, and click **TextDataset (in this Report)**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="f5d95-184">Dans la **page organiser les champs** , faites glisser les champs **secteur**, **linktext**et **produit** vers **groupes de lignes**, faites glisser le champ **Sales** vers **valeurs**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-184">On the **Arrange fields** page, drag the **Territory**, **LinkText**, and **Product** fields to **Row groups**, drag the **Sales** field to **Values**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f5d95-185">Dans la page **choisir la disposition** , désactivez la case à cocher **développer/réduire les groupes** afin de pouvoir voir le tableau entier, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-185">On the **Choose the layout** page, clear the **Expand/collapse groups** check box so you can see the whole table, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="f5d95-186">Dans la page **choisir un style** , cliquez sur **ardoise**, puis sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-186">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="f5d95-187">Faites glisser le tableau sous le bloc de titre.</span><span class="sxs-lookup"><span data-stu-id="f5d95-187">Drag the table so it is below the title block.</span></span>  
  
7.  <span data-ttu-id="f5d95-188">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-188">Click **Run**.</span></span>  
  
     <span data-ttu-id="f5d95-189">Le tableau semble parfait, mais il contient deux lignes de total.</span><span class="sxs-lookup"><span data-stu-id="f5d95-189">The table looks OK, but it has two Total rows.</span></span> <span data-ttu-id="f5d95-190">Le champ **linktext** n’a pas besoin d’une ligne de total.</span><span class="sxs-lookup"><span data-stu-id="f5d95-190">The **LinkText** field doesn't need a Total row.</span></span>  
  
8.  <span data-ttu-id="f5d95-191">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5d95-191">Click **Design** to return to design view.</span></span>  
  
9. <span data-ttu-id="f5d95-192">Cliquez avec le bouton droit sur la zone de texte qui contient `[LinkText]` , puis cliquez sur **fractionner les cellules**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-192">Right-click the text box that contains `[LinkText]`, and click **Split Cells**.</span></span>  
  
10. <span data-ttu-id="f5d95-193">Sélectionnez la cellule vide sous la `[LinkText]` cellule, maintenez la touche Maj enfoncée et sélectionnez les deux cellules à droite : la cellule **total** dans la colonne **Product** et la `[Sum(Sales)]` cellule dans la colonne **Sales** .</span><span class="sxs-lookup"><span data-stu-id="f5d95-193">Select the empty cell below the `[LinkText]` cell, and then hold down the SHIFT key and select the two cells to its right: the **Total** cell in the **Product** column and the `[Sum(Sales)]` cell in the **Sales** column.</span></span>  
  
11. <span data-ttu-id="f5d95-194">Après avoir sélectionné ces trois cellules, cliquez avec le bouton droit sur l’une de ces cellules, puis cliquez sur **Supprimer la ligne**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-194">With those three cells selected, right-click one of those cells and click **Delete Row**.</span></span>  
  
12. <span data-ttu-id="f5d95-195">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-195">Click **Run**.</span></span>  
  
##  <a name="add-a-hyperlink-to-the-report"></a><a name="AddHyperlink"></a><span data-ttu-id="f5d95-196">Ajouter un lien hypertexte au rapport</span><span class="sxs-lookup"><span data-stu-id="f5d95-196">Add a Hyperlink to the Report</span></span>  
 <span data-ttu-id="f5d95-197">Dans cette section, vous allez ajouter un lien hypertexte au texte du tableau de la section précédente.</span><span class="sxs-lookup"><span data-stu-id="f5d95-197">In this section, you add a hyperlink to text in the table from the previous section.</span></span>  
  
#### <a name="to-add-a-hyperlink-to-the-report"></a><span data-ttu-id="f5d95-198">Pour ajouter un lien hypertexte au rapport</span><span class="sxs-lookup"><span data-stu-id="f5d95-198">To add a hyperlink to the report</span></span>  
  
1.  <span data-ttu-id="f5d95-199">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5d95-199">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="f5d95-200">Cliquez avec le bouton droit dans la cellule qui contient `[LinkText]`, puis cliquez sur **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-200">Right-click in the cell containing `[LinkText]`, and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="f5d95-201">Dans la zone Propriétés de la **zone de texte** , cliquez sur **action**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-201">In the **Text Box Properties** box, click **Action**.</span></span>  
  
4.  <span data-ttu-id="f5d95-202">Cliquez sur **accéder à l’URL**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-202">Click **Go to URL**.</span></span>  
  
5.  <span data-ttu-id="f5d95-203">Dans la zone **Sélectionner une URL** , cliquez sur **[URL]**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-203">In the **Select URL** box, click **[URL]**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="f5d95-204">Notez que le texte n'est en aucune manière différent.</span><span class="sxs-lookup"><span data-stu-id="f5d95-204">Note that the text does not look any different.</span></span> <span data-ttu-id="f5d95-205">Vous devez lui donner l'apparence de texte de lien.</span><span class="sxs-lookup"><span data-stu-id="f5d95-205">You need to make it look like link text.</span></span>  
  
7.  <span data-ttu-id="f5d95-206">Sélectionnez `[LinkText]`.</span><span class="sxs-lookup"><span data-stu-id="f5d95-206">Select `[LinkText]`.</span></span>  
  
8.  <span data-ttu-id="f5d95-207">Dans la section **police** de l’onglet dossier de **démarrage** , cliquez sur le bouton **souligné** , puis cliquez sur la flèche déroulante en regard du bouton **couleur** , puis cliquez sur **bleu**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-207">In the **Font** section of the **Home** tab, click the **Underline** button, and then click the drop-down arrow next to the **Color** button, and click **Blue**.</span></span>  
  
9. <span data-ttu-id="f5d95-208">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-208">Click **Run**.</span></span>  
  
     <span data-ttu-id="f5d95-209">Le texte a maintenant l'apparence d'un lien.</span><span class="sxs-lookup"><span data-stu-id="f5d95-209">The text now looks like a link.</span></span>  
  
10. <span data-ttu-id="f5d95-210">Cliquez sur un lien.</span><span class="sxs-lookup"><span data-stu-id="f5d95-210">Click a link.</span></span> <span data-ttu-id="f5d95-211">Si l'ordinateur est connecté à Internet, un navigateur s'ouvre sur une rubrique d'aide du Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="f5d95-211">If the computer is connected to the Internet, a browser will open to a Report Builder Help topic.</span></span>  
  
##  <a name="rotate-text-in-the-report"></a><a name="RotateText"></a><span data-ttu-id="f5d95-212">Faire pivoter le texte dans le rapport</span><span class="sxs-lookup"><span data-stu-id="f5d95-212">Rotate Text in the Report</span></span>  
 <span data-ttu-id="f5d95-213">Dans cette section, vous allez faire pivoter une partie du texte du tableau des sections précédentes.</span><span class="sxs-lookup"><span data-stu-id="f5d95-213">In this section, you rotate some of the text in the table from the previous sections.</span></span>  
  
#### <a name="to-rotate-text"></a><span data-ttu-id="f5d95-214">Pour faire pivoter le texte</span><span class="sxs-lookup"><span data-stu-id="f5d95-214">To rotate text</span></span>  
  
1.  <span data-ttu-id="f5d95-215">Cliquez sur **Conception** pour repasser en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5d95-215">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="f5d95-216">Cliquez dans la cellule qui contient `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="f5d95-216">Click in the cell containing `[Territory].`</span></span>  
  
3.  <span data-ttu-id="f5d95-217">Sous l’onglet **Accueil** , dans la section **Police** , cliquez sur le bouton **Gras** .</span><span class="sxs-lookup"><span data-stu-id="f5d95-217">On the **Home** tab in the **Font** section, click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="f5d95-218">Si le volet Propriétés n’est pas ouvert, sous l’onglet **Affichage** , cochez la case **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="f5d95-218">If the Properties pane is not open, on the **View** tab, select the **Properties** check box.</span></span>  
  
5.  <span data-ttu-id="f5d95-219">Recherchez la propriété WritingMode dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="f5d95-219">Locate the WritingMode property in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f5d95-220">Quand les propriétés du volet Propriétés sont organisées en catégories, WritingMode figure dans la catégorie **Localisation** .</span><span class="sxs-lookup"><span data-stu-id="f5d95-220">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span> <span data-ttu-id="f5d95-221">Assurez-vous que vous avez sélectionné la cellule et non le texte.</span><span class="sxs-lookup"><span data-stu-id="f5d95-221">Be sure you have selected the cell and not the text.</span></span> <span data-ttu-id="f5d95-222">WritingMode est une propriété de la zone de texte, pas du texte.</span><span class="sxs-lookup"><span data-stu-id="f5d95-222">WritingMode is a property of the text box, not of the text.</span></span>  
  
6.  <span data-ttu-id="f5d95-223">Dans la zone de liste, cliquez sur **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-223">In the list box, click **Rotate270**.</span></span>  
  
7.  <span data-ttu-id="f5d95-224">Dans l’onglet dossier de **démarrage** de la section **paragraphe** , cliquez sur les boutons **centraux** et **centraux** pour localiser le texte au centre de la cellule à la fois verticalement et horizontalement.</span><span class="sxs-lookup"><span data-stu-id="f5d95-224">On the **Home** tab in the **Paragraph** section, click the **Middle** and **Center** buttons to locate the text in the center of the cell both vertically and horizontally.</span></span>  
  
8.  <span data-ttu-id="f5d95-225">Cliquez sur Exécuter (**!**).</span><span class="sxs-lookup"><span data-stu-id="f5d95-225">Click Run (**!**).</span></span>  
  
 <span data-ttu-id="f5d95-226">Le texte de la cellule `[Territory]` s'exécute maintenant verticalement de bas en haut des cellules.</span><span class="sxs-lookup"><span data-stu-id="f5d95-226">Now the text in the `[Territory]` cell runs vertically from the bottom to the top of the cells.</span></span>  
  
##  <a name="displaying-text-with-html-formatting"></a><a name="FormatHTML"></a><span data-ttu-id="f5d95-227">Affichage de texte avec une mise en forme HTML</span><span class="sxs-lookup"><span data-stu-id="f5d95-227">Displaying Text with HTML Formatting</span></span>  
  
#### <a name="to-display-text-formatted-as-html"></a><span data-ttu-id="f5d95-228">Pour afficher le texte mis en forme en HTML</span><span class="sxs-lookup"><span data-stu-id="f5d95-228">To display text formatted as HTML</span></span>  
  
1.  <span data-ttu-id="f5d95-229">Cliquez sur **Conception** pour basculer en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5d95-229">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="f5d95-230">Sous l’onglet **Insertion** , cliquez sur **Zone de texte**, puis sur l’aire de conception, cliquez et faites glisser la souris pour créer une zone de texte sous le tableau d’environ 10 cm de large sur 8 cm de haut.</span><span class="sxs-lookup"><span data-stu-id="f5d95-230">On the **Insert** tab, click **Text Box**, and then on the design surface, click and drag to create a text box under the table, about four inches wide and three inches tall.</span></span>  
  
3.  <span data-ttu-id="f5d95-231">Copiez le texte suivant et collez-le dans la zone de texte :</span><span class="sxs-lookup"><span data-stu-id="f5d95-231">Copy this text and paste it into the text box:</span></span>  
  
    ```  
    <h4>Limitations of cascading style sheet attributes</h4>  
          <p>Only a basic set of <b>cascading style sheet (CSS)</b> attributes are defined:</p>  
          <ul><li>  
              text-align, text-indent  
            </li><li>  
              font-family, font-size  
            </li><li>  
              color  
            </li><li>  
              padding, padding-bottom, padding-top, padding-right, padding-left  
            </li><li>  
              font-weight  
            </li></ul>  
    ```  
  
4.  <span data-ttu-id="f5d95-232">Sélectionnez tout le texte de la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="f5d95-232">Select all of the text in the text box.</span></span>  
  
     <span data-ttu-id="f5d95-233">Il s'agit d'une propriété du texte, pas de la zone de texte. Ainsi, une zone de texte peut contenir à la fois du texte brut et du texte qui utilise des balises HTML comme styles.</span><span class="sxs-lookup"><span data-stu-id="f5d95-233">This is a property of the text, not the text box, so in one text box you could have a mixture of plain text and text that uses HTML tags as styles.</span></span>  
  
5.  <span data-ttu-id="f5d95-234">Cliquez avec le bouton droit sur l’ensemble du texte sélectionné, puis cliquez sur **Propriétés du texte**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-234">Right-click all of the selected text and click **Text Properties**.</span></span>  
  
6.  <span data-ttu-id="f5d95-235">Sur la page **général** , sous **type de balise**, cliquez sur **HTML-interpréter les balises html comme des styles**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-235">On the **General** page, under **Markup type**, click **HTML - Interpret HTML tags as styles**.</span></span>  
  
7.  <span data-ttu-id="f5d95-236">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-236">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="f5d95-237">Cliquez sur Exécuter (**!**) pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5d95-237">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="f5d95-238">Le texte de la zone de texte est affiché sous forme de titre, paragraphe et liste à puce.</span><span class="sxs-lookup"><span data-stu-id="f5d95-238">The text in the text box is displayed as a heading, paragraph, and bulleted list.</span></span>  
  
##  <a name="format-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="f5d95-239">Mettre en forme la devise</span><span class="sxs-lookup"><span data-stu-id="f5d95-239">Format Currency</span></span>  
  
#### <a name="to-format-numbers-as-currency"></a><span data-ttu-id="f5d95-240">Pour mettre en forme des nombres en devise</span><span class="sxs-lookup"><span data-stu-id="f5d95-240">To format numbers as currency</span></span>  
  
1.  <span data-ttu-id="f5d95-241">Cliquez sur **Conception** pour basculer en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="f5d95-241">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="f5d95-242">Cliquez sur la cellule supérieure du tableau contenant `[Sum(Sales)]`, maintenez la touche Maj enfoncée et cliquez sur la cellule inférieure du tableau contenant `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="f5d95-242">Click the top table cell that contains `[Sum(Sales)]`, hold down the SHIFT key, and click the bottom table cell that contains `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="f5d95-243">Sous l’onglet **Accueil** , dans le groupe **Nombre** , cliquez sur le bouton **Devise** .</span><span class="sxs-lookup"><span data-stu-id="f5d95-243">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>  
  
4.  <span data-ttu-id="f5d95-244">Facultatif Dans l’onglet dossier de **démarrage** , dans le groupe **nombre** , cliquez sur le bouton **styles des espaces réservés** et cliquez sur **exemples de valeurs** pour voir comment les nombres sont mis en forme.</span><span class="sxs-lookup"><span data-stu-id="f5d95-244">(Optional) On the **Home** tab, in the **Number** group, click the **Placeholder Styles** button and click **Sample Values** to see how the numbers will be formatted.</span></span>  
  
5.  <span data-ttu-id="f5d95-245">(Facultatif) Sous l’onglet **Accueil** , dans le groupe **Nombre** , cliquez sur le bouton **Réduire les décimales** à deux reprises, pour afficher les valeurs en dollars sans indication de centimes.</span><span class="sxs-lookup"><span data-stu-id="f5d95-245">(Optional) On the **Home** tab, in the **Number** group, click the **Decrease Decimals** button twice to display dollar figures with no cents.</span></span>  
  
6.  <span data-ttu-id="f5d95-246">Cliquez sur Exécuter (**!**) pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="f5d95-246">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="f5d95-247">Le rapport affiche maintenant les données mises en forme et est plus facile à lire.</span><span class="sxs-lookup"><span data-stu-id="f5d95-247">The report now displays formatted data and is easier to read.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="f5d95-248">Enregistrer le rapport</span><span class="sxs-lookup"><span data-stu-id="f5d95-248">Save the Report</span></span>  
 <span data-ttu-id="f5d95-249">Vous pouvez enregistrer les rapports sur un serveur de rapports, dans une bibliothèque SharePoint ou sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f5d95-249">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="f5d95-250">Dans ce didacticiel, enregistrez le rapport sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="f5d95-250">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="f5d95-251">Si vous n'avez pas accès à un serveur de rapports, enregistrez le rapport sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f5d95-251">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="f5d95-252">Pour enregistrer le rapport sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="f5d95-252">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="f5d95-253">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-253">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="f5d95-254">Cliquez sur **Sites et serveurs récents**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-254">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="f5d95-255">Sélectionnez ou tapez le nom du serveur de rapports sur lequel vous êtes autorisé à enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="f5d95-255">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="f5d95-256">Le message « Connexion au serveur de rapports » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f5d95-256">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="f5d95-257">Une fois la connexion établie, le contenu du dossier de rapports spécifié par l'administrateur du serveur de rapports s'affiche comme emplacement par défaut des rapports.</span><span class="sxs-lookup"><span data-stu-id="f5d95-257">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="f5d95-258">Dans **Nom**, remplacez le nom par défaut par un nom de votre choix.</span><span class="sxs-lookup"><span data-stu-id="f5d95-258">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
5.  <span data-ttu-id="f5d95-259">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-259">Click **Save**.</span></span>  
  
 <span data-ttu-id="f5d95-260">Le rapport est enregistré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="f5d95-260">The report is saved to the report server.</span></span> <span data-ttu-id="f5d95-261">Le nom du serveur de rapports auquel vous êtes connecté est indiqué dans la barre d'état située au bas de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="f5d95-261">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="f5d95-262">Pour enregistrer le rapport sur votre ordinateur</span><span class="sxs-lookup"><span data-stu-id="f5d95-262">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="f5d95-263">À partir du bouton **Générateur de rapports** , cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-263">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="f5d95-264">Cliquez sur **Bureau**, **Mes documents**ou **Poste de travail**, puis naviguez jusqu'au dossier où vous souhaitez enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="f5d95-264">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="f5d95-265">Dans **Nom**, remplacez le nom par défaut par un nom de votre choix.</span><span class="sxs-lookup"><span data-stu-id="f5d95-265">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
4.  <span data-ttu-id="f5d95-266">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f5d95-266">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f5d95-267">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="f5d95-267">Next Steps</span></span>  
 <span data-ttu-id="f5d95-268">Il existe de nombreuses façons de mettre en forme du texte dans Générateur de rapports [Didacticiel : la création d’un rapport de forme libre &#40;Générateur de rapports&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) contient plus d’exemples.</span><span class="sxs-lookup"><span data-stu-id="f5d95-268">There are many ways to format text in Report Builder [Tutorial: Creating a Free Form Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) contains more examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5d95-269">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5d95-269">See Also</span></span>  
 <span data-ttu-id="f5d95-270">[Didacticiels &#40;Générateur de rapports&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="f5d95-270">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="f5d95-271">[Mise en forme des éléments de rapport &#40;Générateur de rapports et SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f5d95-271">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f5d95-272">Générateur de rapports dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="f5d95-272">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
