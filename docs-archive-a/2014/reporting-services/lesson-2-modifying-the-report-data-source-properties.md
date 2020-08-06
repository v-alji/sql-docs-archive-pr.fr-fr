---
title: 'Leçon 2 : modification des propriétés d’une source de données de rapport | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c962b0ff-ce8a-4742-8262-dc730901afcf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05e56a58ce28ee1e1e450d3af012cbd1ffe668ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601975"
---
# <a name="lesson-2-modifying-the-report-data-source-properties"></a><span data-ttu-id="ecf04-102">Lesson 2: Modifying the Report Data Source Properties</span><span class="sxs-lookup"><span data-stu-id="ecf04-102">Lesson 2: Modifying the Report Data Source Properties</span></span>
  <span data-ttu-id="ecf04-103">Dans cette leçon, vous allez utiliser le Gestionnaire de rapports pour sélectionner un rapport qui sera remis à ses destinataires.</span><span class="sxs-lookup"><span data-stu-id="ecf04-103">In this lesson, you will use Report Manager to select a report that will be delivered to recipients.</span></span> <span data-ttu-id="ecf04-104">L’abonnement piloté par les données que vous allez définir distribue le rapport **Sales Order** créé dans le didacticiel [Créer un rapport de tableau de base &#40;Didacticiel SSRS&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ecf04-104">The data-driven subscription that you will define will distribute the **Sales Order** report created in the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span></span> <span data-ttu-id="ecf04-105">Au cours des étapes qui suivent, vous allez modifier les informations de connexion à la source de données utilisée par le rapport pour extraire les données.</span><span class="sxs-lookup"><span data-stu-id="ecf04-105">In the steps that follow, you will modify the data source connection information used by the report to get data.</span></span> <span data-ttu-id="ecf04-106">Seuls les rapports qui utilisent des **informations d’identification stockées** pour accéder à une source de données de rapport peuvent être distribués par le biais d’un abonnement piloté par les données.</span><span class="sxs-lookup"><span data-stu-id="ecf04-106">Only reports that use **stored credentials** to access a report data source can be distributed through a data-driven subscription.</span></span> <span data-ttu-id="ecf04-107">Les informations d'identification stockées sont nécessaires pour traiter les rapports de façon autonome.</span><span class="sxs-lookup"><span data-stu-id="ecf04-107">Stored credentials are necessary for unattended report processing.</span></span>

 <span data-ttu-id="ecf04-108">Vous allez également modifier le dataset et le rapport pour qu'ils utilisent un paramètre permettant de filtrer le rapport sur `[Order]` de sorte que l'abonnement puisse générer plusieurs instances différentes du rapport pour des commandes et des formats de rendu spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ecf04-108">You will also modify the dataset and report to use a parameter to filter the report on the `[Order]` so the subscription can output different instances of the report for specific orders and rendering formats.</span></span>

 <span data-ttu-id="ecf04-109">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="ecf04-109">**In this topic:**</span></span>

-   [<span data-ttu-id="ecf04-110">Pour modifier les propriétés d'une source de données</span><span class="sxs-lookup"><span data-stu-id="ecf04-110">To Modify the Data Source Properties</span></span>](#bkmk_modify_datasource)

-   [<span data-ttu-id="ecf04-111">Pour modifier AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="ecf04-111">To Modify the AdventureWorksDataset</span></span>](#bkmk_modify_dataset)

-   [<span data-ttu-id="ecf04-112">Pour ajouter un paramètre de rapport et republier le rapport</span><span class="sxs-lookup"><span data-stu-id="ecf04-112">To Add a Report Parameter and Republish the Report</span></span>](#bkmk_add_reportparameter)

-   [<span data-ttu-id="ecf04-113">Pour redéployer le rapport</span><span class="sxs-lookup"><span data-stu-id="ecf04-113">To Re-deploy the Report</span></span>](#bkmk_redeploy)

##  <a name="to-modify-the-data-source-properties"></a><a name="bkmk_modify_datasource"></a><span data-ttu-id="ecf04-114">Pour modifier les propriétés de la source de données</span><span class="sxs-lookup"><span data-stu-id="ecf04-114">To Modify the Data Source Properties</span></span>

1.  <span data-ttu-id="ecf04-115">Démarrez [Gestionnaire de rapports &#40;&#41;en mode natif SSRS](../../2014/reporting-services/report-manager-ssrs-native-mode.md) avec des privilèges d’administrateur. par exemple, cliquez avec le bouton droit sur l’icône d’Internet Explorer, puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>

2.  <span data-ttu-id="ecf04-116">Accédez au dossier contenant le rapport **Sales Orders** et, dans le menu contextuel du rapport, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-116">Browse to the folder containing the **Sales Orders** report and in the context menu of the report, click **Manage**.</span></span>

     <span data-ttu-id="ecf04-117">![Ouvrir le menu contextuel du rapport et sélectionnez gérer](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Ouvrir le menu contextuel du rapport et sélectionnez gérer")</span><span class="sxs-lookup"><span data-stu-id="ecf04-117">![Open the report context menu and select manage](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Open the report context menu and select manage")</span></span>

3.  <span data-ttu-id="ecf04-118">Cliquez sur l'onglet **Sources de données** .</span><span class="sxs-lookup"><span data-stu-id="ecf04-118">Click the **Data Sources** tab.</span></span>

4.  <span data-ttu-id="ecf04-119">Dans **Type de connexion**, sélectionnez **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-119">For **Connection Type**, select **Microsoft SQL Server**.</span></span>

5.  <span data-ttu-id="ecf04-120">La chaîne de connexion à la source de données personnalisée sera la chaîne suivante et l'on suppose que l'exemple de base de données se trouve sur un serveur de base de données local :</span><span class="sxs-lookup"><span data-stu-id="ecf04-120">The custom data source connection string will be the following and it assumes that the sample database is on a local database server:</span></span>

    ```
    Data source=localhost; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="ecf04-121">Cliquez sur **Informations d'identification stockées en sécurité dans le serveur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-121">Click **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="ecf04-122">Tapez votre nom d’utilisateur (utilisez le format *domaine\utilisateur*) et votre mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ecf04-122">Type your user name (use the format *domain\user*) and password.</span></span> <span data-ttu-id="ecf04-123">Si vous n'êtes pas autorisé à accéder à la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , spécifiez une connexion qui rendra cet accès possible.</span><span class="sxs-lookup"><span data-stu-id="ecf04-123">If you do not have permission to access the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database, specify a login that does.</span></span>

8.  <span data-ttu-id="ecf04-124">Cliquez sur **Utiliser comme informations d'identification Windows lors de la connexion à la source de données**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-124">Click **Use as windows credentials when connecting to the data source**, and then click **OK**.</span></span> <span data-ttu-id="ecf04-125">Si vous n'utilisez pas de compte de domaine (par exemple, si vous utilisez une connexion [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ), n'activez pas cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="ecf04-125">If you are not using a domain account (for example, if you are using a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login), do not click this checkbox.</span></span>

9. <span data-ttu-id="ecf04-126">Cliquez sur **Tester la connexion** pour vous assurer que vous pouvez vous connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="ecf04-126">Click **Test Connection** to verify you can connect to the data source.</span></span>

10. <span data-ttu-id="ecf04-127">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-127">Click **Apply**.</span></span>

11. <span data-ttu-id="ecf04-128">Affichez le rapport pour vérifier qu'il s'exécute avec les informations d'identification que vous avez spécifiées.</span><span class="sxs-lookup"><span data-stu-id="ecf04-128">View the report to verify that the report runs with the credentials you specified.</span></span> <span data-ttu-id="ecf04-129">Pour afficher le rapport, cliquez sur l’onglet **affichage** . Notez qu’une fois le rapport ouvert, vous devez sélectionner un nom d’employé, puis cliquer sur le bouton **afficher le rapport** pour afficher le rapport.</span><span class="sxs-lookup"><span data-stu-id="ecf04-129">To view the report, click the **View** tab. Note that once the report is open, you must select an Employee name and then click the **View Report** button to view the report.</span></span>

##  <a name="to-modify-the-adventureworksdataset"></a><a name="bkmk_modify_dataset"></a><span data-ttu-id="ecf04-130">Pour modifier le AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="ecf04-130">To Modify the AdventureWorksDataset</span></span>

1.  <span data-ttu-id="ecf04-131">Ouvrez le rapport Sales Orders dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecf04-131">Open the Sales Orders report in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span></span>

2.  <span data-ttu-id="ecf04-132">Cliquez avec le bouton droit sur le dataset `AdventureWorksDataset` et cliquez sur **Propriétés du dataset**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-132">Right-click the dataset `AdventureWorksDataset` and click **Dataset Properties**.</span></span>

3.  <span data-ttu-id="ecf04-133">Ajoutez l'instruction `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` avant l'instruction `Group By` .</span><span class="sxs-lookup"><span data-stu-id="ecf04-133">Add the statement `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` before the `Group By` statement.</span></span> <span data-ttu-id="ecf04-134">La syntaxe de requête complète est la suivante :</span><span class="sxs-lookup"><span data-stu-id="ecf04-134">The full query syntax is the following:</span></span>

    ```
    SELECT soh.OrderDate AS Date, soh.SalesOrderNumber AS [Order], pps.Name AS Subcat, pp.Name AS Product, SUM(sd.OrderQty) AS Qty, SUM(sd.LineTotal)  AS LineTotal
    FROM Sales.SalesPerson AS sp INNER JOIN
      Sales.SalesOrderHeader AS soh ON sp.BusinessEntityID = soh.SalesPersonID INNER JOIN
       Sales.SalesOrderDetail AS sd ON sd.SalesOrderID = soh.SalesOrderID INNER JOIN
       Production.Product AS pp ON sd.ProductID = pp.ProductID
    INNER JOIN
       Production.ProductSubcategory AS pps ON pp.ProductSubcategoryID = pps.ProductSubcategoryID 
    INNER JOIN
        Production.ProductCategory AS ppc ON ppc.ProductCategoryID = pps.ProductCategoryID

    WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)

    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name, soh.SalesPersonID
    HAVING (ppc.Name = 'Clothing')
    ```

4.  <span data-ttu-id="ecf04-135">Cliquez sur **OK**</span><span class="sxs-lookup"><span data-stu-id="ecf04-135">Click **OK**</span></span>

##  <a name="to-add-a-report-parameter-and-republish-the-report"></a><a name="bkmk_add_reportparameter"></a><span data-ttu-id="ecf04-136">Pour ajouter un paramètre de rapport et republier le rapport</span><span class="sxs-lookup"><span data-stu-id="ecf04-136">To Add a Report Parameter and Republish the Report</span></span>

1.  <span data-ttu-id="ecf04-137">Dans le volet des **données de rapport** , cliquez sur **Nouveau** , puis sur **Paramètre...**</span><span class="sxs-lookup"><span data-stu-id="ecf04-137">In the **Report Data** pane click **New** and then click **Parameter...**</span></span>

2.  <span data-ttu-id="ecf04-138">Dans **Nom**, tapez `OrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="ecf04-138">In **Name**, type `OrderNumber`.</span></span>

3.  <span data-ttu-id="ecf04-139">À l' **Invite**, tapez `OrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="ecf04-139">In **Prompt**, type `OrderNumber`.</span></span>

4.  <span data-ttu-id="ecf04-140">Sélectionnez **Autoriser une valeur vide ("")**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-140">Select **Allow blank value ("")**.</span></span>

5.  <span data-ttu-id="ecf04-141">Sélectionnez **Autoriser les valeurs de type Null**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-141">Select **Allow null value**.</span></span>

6.  <span data-ttu-id="ecf04-142">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-142">Click **OK**.</span></span> <span data-ttu-id="ecf04-143">Ce paramètre sera ajouté dans le volet des **données de rapport** et il ressemblera à l'image suivante :</span><span class="sxs-lookup"><span data-stu-id="ecf04-143">The parameter will be added to the **Report Data pane** and it will look like the following image:</span></span>

     <span data-ttu-id="ecf04-144">![Le nouveau paramètre est ajouté au volet des données de rapport](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "Le nouveau paramètre est ajouté au volet des données de rapport")</span><span class="sxs-lookup"><span data-stu-id="ecf04-144">![The new parameter is added to the Report Data pane](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "The new parameter is added to the Report Data pane")</span></span>

7.  <span data-ttu-id="ecf04-145">Cliquez sur l'onglet **Aperçu** pour exécuter le rapport. Notez la zone d'entrée du paramètre en haut du rapport.</span><span class="sxs-lookup"><span data-stu-id="ecf04-145">Click the **Preview** tab to run the report.Note the parameter input box at the top of the report.</span></span> <span data-ttu-id="ecf04-146">Vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="ecf04-146">You can either:</span></span>

    -   <span data-ttu-id="ecf04-147">Cliquez sur Afficher le rapport pour afficher le rapport dans son intégralité sans utiliser de paramètre.</span><span class="sxs-lookup"><span data-stu-id="ecf04-147">Click View Report to see the full report without using a parameter.</span></span>

    -   <span data-ttu-id="ecf04-148">Désélectionnez l'option Null et tapez un numéro de commande, so71949 par exemple, pour afficher uniquement cette commande dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="ecf04-148">Unselect the Null option and type an order number, for example so71949 to view only the one order in the report.</span></span>

         <span data-ttu-id="ecf04-149">![Visionneuse de rapports avec zone de paramètres visible](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Visionneuse de rapports avec zone de paramètres visible")</span><span class="sxs-lookup"><span data-stu-id="ecf04-149">![Report viewer with parameter area visible](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Report viewer with parameter area visible")</span></span>

8.  <span data-ttu-id="ecf04-150">Redéployez le rapport afin que la configuration de l'abonnement dans la leçon suivante puisse utiliser les modifications que vous avez apportées dans cette leçon.</span><span class="sxs-lookup"><span data-stu-id="ecf04-150">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="ecf04-151">Pour plus d’informations sur les propriétés de projet utilisées dans le didacticiel de table, consultez la section « pour publier le rapport sur le serveur de rapports (facultatif) » de la [leçon 6 : ajout d’un regroupement et de totaux &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ecf04-151">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

##  <a name="to-re-deploy-the-report"></a><a name="bkmk_redeploy"></a><span data-ttu-id="ecf04-152">Pour redéployer le rapport</span><span class="sxs-lookup"><span data-stu-id="ecf04-152">To Re-deploy the Report</span></span>

1.  <span data-ttu-id="ecf04-153">Redéployez le rapport afin que la configuration de l'abonnement dans la leçon suivante puisse utiliser les modifications que vous avez apportées dans cette leçon.</span><span class="sxs-lookup"><span data-stu-id="ecf04-153">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="ecf04-154">Pour plus d’informations sur les propriétés de projet utilisées dans le didacticiel de table, consultez la section « pour publier le rapport sur le serveur de rapports (facultatif) » de la [leçon 6 : ajout d’un regroupement et de totaux &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ecf04-154">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

2.  <span data-ttu-id="ecf04-155">Dans la barre d'outils, cliquez sur **Générer** , puis sur **Déployer le didacticiel**.</span><span class="sxs-lookup"><span data-stu-id="ecf04-155">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ecf04-156">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="ecf04-156">Next Steps</span></span>
 <span data-ttu-id="ecf04-157">Vous avez correctement configuré le rapport pour extraire les données au moyen des informations d'identification stockées.</span><span class="sxs-lookup"><span data-stu-id="ecf04-157">You successfully configured the report to get data using stored credentials.</span></span> <span data-ttu-id="ecf04-158">Vous allez ensuite spécifier l'abonnement en utilisant les pages d'abonnement piloté par les données du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="ecf04-158">Next, you specify the subscription using the Data-Driven Subscription pages in Report Manager.</span></span> <span data-ttu-id="ecf04-159">Consultez la [Leçon 3 : Définition d’un abonnement piloté par les données](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="ecf04-159">See [Lesson 3: Defining a Data-Driven Subscription](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ecf04-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ecf04-160">See Also</span></span>
 <span data-ttu-id="ecf04-161">[Gérer les sources de données de rapport](report-data/manage-report-data-sources.md) [Spécifiez les informations d’identification et de connexion pour les sources de données de rapport](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [créer un abonnement piloté par les données &#40;didacticiel SSRS&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [créer un rapport de tableau de base &#40;didacticiel SSRS&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="ecf04-161">[Manage Report Data Sources](report-data/manage-report-data-sources.md) [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span></span>


