---
title: Définition et utilisation d’une action d’extraction | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 3765f865-2b93-44be-b290-28e3815d5ecb
author: minewiskan
ms.author: owend
ms.openlocfilehash: ea19a9721d87936bc88b5401c71ee550a47bc1ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698724"
---
# <a name="defining-and-using-a-drillthrough-action"></a><span data-ttu-id="1a326-102">Définition et utilisation d'une action d'extraction</span><span class="sxs-lookup"><span data-stu-id="1a326-102">Defining and Using a Drillthrough Action</span></span>
  <span data-ttu-id="1a326-103">Le dimensionnement des données de fait par une dimension de fait sans filtrage correct des données retournées par la requête peut ralentir les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="1a326-103">Dimensioning fact data by a fact dimension without correctly filtering the data that the query returns can cause slow query performance.</span></span> <span data-ttu-id="1a326-104">Pour éviter ceci, vous pouvez définir une action d'extraction qui restreint le nombre total de lignes retournées.</span><span class="sxs-lookup"><span data-stu-id="1a326-104">To avoid this, you can define a drillthrough action that restricts the total number of rows that are returned.</span></span> <span data-ttu-id="1a326-105">Cela améliorera considérablement les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="1a326-105">This will significantly improve query performance.</span></span>  
  
 <span data-ttu-id="1a326-106">Dans les tâches de cette rubrique, vous définissez une action d'extraction pour retourner des informations détaillées sur les commandes pour les ventes à des clients via Internet.</span><span class="sxs-lookup"><span data-stu-id="1a326-106">In the tasks in this topic, you define a drillthrough action to return order detail information for sales to customers over the Internet.</span></span>  
  
## <a name="defining-the-drillthrough-action-properties"></a><span data-ttu-id="1a326-107">Définition des propriétés d'une action d'extraction</span><span class="sxs-lookup"><span data-stu-id="1a326-107">Defining the Drillthrough Action Properties</span></span>  
  
1.  <span data-ttu-id="1a326-108">Ouvrez le Concepteur de cube pour le cube du didacticiel de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur l’onglet **Actions** .</span><span class="sxs-lookup"><span data-stu-id="1a326-108">In Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, click the **Actions** tab.</span></span>  
  
     <span data-ttu-id="1a326-109">L’onglet **Actions** comporte plusieurs volets.</span><span class="sxs-lookup"><span data-stu-id="1a326-109">The **Actions** tab includes several panes.</span></span> <span data-ttu-id="1a326-110">Sur le côté gauche de l’onglet se trouvent le volet **Organisateur d’action** et le volet **Outils de calcul** .</span><span class="sxs-lookup"><span data-stu-id="1a326-110">On the left side of the tab are the **Action Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="1a326-111">À droite de ces deux volets se trouve le volet de **visualisation** , qui contient les détails de l’action qui est sélectionnée dans le volet **Organisateur d’action** .</span><span class="sxs-lookup"><span data-stu-id="1a326-111">The pane to the right of these two panes is the **Display** pane, which contains the details of the action that is selected in the **Action Organizer** pane.</span></span>  
  
     <span data-ttu-id="1a326-112">L’image suivante montre l’onglet **Actions** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="1a326-112">The following image shows the **Actions** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="1a326-113">![Onglet Actions du Concepteur de cube](../../2014/tutorials/media/l8-action1.gif "Onglet Actions du Concepteur de cube")</span><span class="sxs-lookup"><span data-stu-id="1a326-113">![Actions tab of Cube Designer](../../2014/tutorials/media/l8-action1.gif "Actions tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="1a326-114">Dans la barre d’outils de l’onglet **Actions** , cliquez sur le bouton **Nouvelle action d’extraction** .</span><span class="sxs-lookup"><span data-stu-id="1a326-114">On the toolbar of the **Actions** tab, click the **New Drillthrough Action** button.</span></span>  
  
     <span data-ttu-id="1a326-115">Un modèle d'action vide apparaît dans le volet de visualisation.</span><span class="sxs-lookup"><span data-stu-id="1a326-115">A blank action template appears in the display pane.</span></span>  
  
     <span data-ttu-id="1a326-116">![Modèle d'action vide dans le volet d'informations](../../2014/tutorials/media/l8-action2.gif "Modèle d'action vide dans le volet d'informations")</span><span class="sxs-lookup"><span data-stu-id="1a326-116">![Blank Action template in the display pane](../../2014/tutorials/media/l8-action2.gif "Blank Action template in the display pane")</span></span>  
  
3.  <span data-ttu-id="1a326-117">Dans la zone **nom** , remplacez le nom de cette action par `Internet Sales Details Drillthrough Action` .</span><span class="sxs-lookup"><span data-stu-id="1a326-117">In the **Name** box, change the name of this action to `Internet Sales Details Drillthrough Action`.</span></span>  
  
4.  <span data-ttu-id="1a326-118">Dans la liste **Membres de groupe de mesures** , sélectionnez **Internet Sales**.</span><span class="sxs-lookup"><span data-stu-id="1a326-118">In the **Measure group members** list, select **Internet Sales**.</span></span>  
  
5.  <span data-ttu-id="1a326-119">Dans la zone **Colonnes d’extraction** , sélectionnez **Internet Sales Order Details** dans la liste **Dimensions** .</span><span class="sxs-lookup"><span data-stu-id="1a326-119">In the **Drillthrough Columns** box, select **Internet Sales Order Details** in the **Dimensions** list.</span></span>  
  
6.  <span data-ttu-id="1a326-120">Dans la liste **Colonnes de retour** , cochez les cases **Item Description** et **Order Number** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a326-120">In the **Return Columns** list, select the **Item Description** and the **Order Number** check boxes, and then click **OK**.</span></span> <span data-ttu-id="1a326-121">L'image suivante montre le modèle d'action tel qu'il doit se présenter à ce stade de la procédure.</span><span class="sxs-lookup"><span data-stu-id="1a326-121">The following image shows the Action template as it should appear at this point in this procedure.</span></span>  
  
     <span data-ttu-id="1a326-122">![Zone Colonnes d'extraction](../../2014/tutorials/media/l8-action3.gif "Zone Colonnes d'extraction")</span><span class="sxs-lookup"><span data-stu-id="1a326-122">![Drillthrough Columns box](../../2014/tutorials/media/l8-action3.gif "Drillthrough Columns box")</span></span>  
  
7.  <span data-ttu-id="1a326-123">Développez la zone **Propriétés supplémentaires** , comme le montre l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="1a326-123">Expand the **Additional Properties** box, as shown in the following image.</span></span>  
  
     <span data-ttu-id="1a326-124">![Zone Propriétés supplémentaires](../../2014/tutorials/media/l8-action4.gif "Zone Propriétés supplémentaires")</span><span class="sxs-lookup"><span data-stu-id="1a326-124">![Additional Properties box](../../2014/tutorials/media/l8-action4.gif "Additional Properties box")</span></span>  
  
8.  <span data-ttu-id="1a326-125">Dans la zone **nombre maximal de lignes** , tapez `10` .</span><span class="sxs-lookup"><span data-stu-id="1a326-125">In the **Maximum Rows** box, type `10`.</span></span>  
  
9. <span data-ttu-id="1a326-126">Dans la zone **légende** , tapez `Drillthrough to Order Details...` .</span><span class="sxs-lookup"><span data-stu-id="1a326-126">In the **Caption** box, type `Drillthrough to Order Details...`.</span></span>  
  
     <span data-ttu-id="1a326-127">Ces paramètres limitent le nombre de lignes retournées et spécifient la légende qui apparaît dans le menu de l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="1a326-127">These settings limit the number of rows returned and specify the caption that appears in the client application menu.</span></span> <span data-ttu-id="1a326-128">L’image suivante montre ces paramètres dans la zone **Propriétés supplémentaires** .</span><span class="sxs-lookup"><span data-stu-id="1a326-128">The following image shows these settings in the **AdditionalProperties** box.</span></span>  
  
     <span data-ttu-id="1a326-129">![Zone Propriétés supplémentaires](../../2014/tutorials/media/l8-action5.gif "Zone Propriétés supplémentaires")</span><span class="sxs-lookup"><span data-stu-id="1a326-129">![Additional Properties box](../../2014/tutorials/media/l8-action5.gif "Additional Properties box")</span></span>  
  
## <a name="using-the-drillthrough-action"></a><span data-ttu-id="1a326-130">Utilisation de l'action d'extraction</span><span class="sxs-lookup"><span data-stu-id="1a326-130">Using the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="1a326-131">Dans le menu **Générer** , cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="1a326-131">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="1a326-132">Une fois le déploiement terminé, cliquez sur l’onglet **Navigateur** dans le Concepteur de cube pour le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur **Reconnexion** .</span><span class="sxs-lookup"><span data-stu-id="1a326-132">When deployment has successfully completed, click the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="1a326-133">Démarrez Excel.</span><span class="sxs-lookup"><span data-stu-id="1a326-133">Start Excel.</span></span>  
  
4.  <span data-ttu-id="1a326-134">Ajoutez la mesure **Internet Sales-Sales Amount** à la zone Valeurs.</span><span class="sxs-lookup"><span data-stu-id="1a326-134">Add the **Internet Sales-Sales Amount** measure to the Values area.</span></span>  
  
5.  <span data-ttu-id="1a326-135">Ajoutez la hiérarchie définie par l’utilisateur **Customer Geography** à partir du dossier **Location** de la dimension **Customer** à la zone **Filtre de rapport** .</span><span class="sxs-lookup"><span data-stu-id="1a326-135">Add the **Customer Geography** user-defined hierarchy from the **Location** folder in the **Customer** dimension to the **Report Filter** area.</span></span>  
  
6.  <span data-ttu-id="1a326-136">Dans le tableau croisé dynamique, dans **Customer Geography**, ajoutez un filtre qui sélectionne un seul client.</span><span class="sxs-lookup"><span data-stu-id="1a326-136">On the PivotTable, in **Customer Geography**, add a filter that selects a single customer.</span></span> <span data-ttu-id="1a326-137">Développez successivement **All Customers**, **Australia**, **Queensland**, **Brisbane**et **4000**, cochez la case **Adam Powell**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a326-137">Expand **All Customers**, expand **Australia**, expand **Queensland**, expand **Brisbane**, expand **4000**, select the check box for **Adam Powell**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="1a326-138">Les ventes totales de produits par [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] à Adam Powell sont affichées dans la zone de données.</span><span class="sxs-lookup"><span data-stu-id="1a326-138">The total sales of products by [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] to Adam Powell are displayed in the data area.</span></span>  
  
7.  <span data-ttu-id="1a326-139">Cliquez avec le bouton droit sur le montant des ventes, pointez sur **Actions supplémentaires**, puis cliquez sur **Drillthrough to Order Details**.</span><span class="sxs-lookup"><span data-stu-id="1a326-139">Right-click on the sales amount, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="1a326-140">Les détails des commandes qui ont été expédiées à Adam Powell sont affichés dans la **Visionneuse des données d’exemple**, comme le montre l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="1a326-140">The details of the orders that were shipped to Adam Powell are displayed in the **Data Sample Viewer**, as shown in the following image.</span></span> <span data-ttu-id="1a326-141">Cependant, certains détails supplémentaires pourraient être utiles, par exemple la date de la commande, la date de livraison prévue et la date d'expédition.</span><span class="sxs-lookup"><span data-stu-id="1a326-141">However, some additional details would also be useful, such as the order date, due date, and ship date.</span></span> <span data-ttu-id="1a326-142">Dans la procédure suivante, vous allez ajouter ces détails supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="1a326-142">In the next procedure, you will add these additional details.</span></span>  
  
     <span data-ttu-id="1a326-143">![Commandes expédiées à Adam Powell](../../2014/tutorials/media/l8-action6.gif "Commandes expédiées à Adam Powell")</span><span class="sxs-lookup"><span data-stu-id="1a326-143">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action6.gif "Orders shipped to Adam Powell")</span></span>  
  
8.  <span data-ttu-id="1a326-144">Fermez Excel.</span><span class="sxs-lookup"><span data-stu-id="1a326-144">Close Excel/</span></span>  
  
## <a name="modifying-the-drillthrough-action"></a><span data-ttu-id="1a326-145">Modification de l'action d'extraction</span><span class="sxs-lookup"><span data-stu-id="1a326-145">Modifying the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="1a326-146">Ouvrez le Concepteur de dimensions pour la dimension **Internet Sales Order Details** .</span><span class="sxs-lookup"><span data-stu-id="1a326-146">Open Dimension Designer for the **Internet Sales Order Details** dimension.</span></span>  
  
     <span data-ttu-id="1a326-147">Observez que trois attributs seulement ont été définis pour cette dimension.</span><span class="sxs-lookup"><span data-stu-id="1a326-147">Notice that only three attributes have been defined for this dimension.</span></span>  
  
2.  <span data-ttu-id="1a326-148">Dans le volet **Vue de source de données** , cliquez avec le bouton droit dans une zone ouverte, puis cliquez sur **Afficher toutes les tables**.</span><span class="sxs-lookup"><span data-stu-id="1a326-148">In the **Data Source View** pane, right-click an open area, and then click **Show All Tables**.</span></span>  
  
3.  <span data-ttu-id="1a326-149">Dans le menu **Format** , pointez sur **Disposition automatique** , puis cliquez sur **Diagramme**.</span><span class="sxs-lookup"><span data-stu-id="1a326-149">On the **Format** menu, point to **Autolayout** and then click **Diagram**.</span></span>  
  
4.  <span data-ttu-id="1a326-150">Localisez la table **InternetSales (dbo.FactInternetSales)** en cliquant avec le bouton droit dans une zone ouverte du volet **Vue de source de données** .</span><span class="sxs-lookup"><span data-stu-id="1a326-150">Locate the **InternetSales (dbo.FactInternetSales)** table by right-clicking in an open area of the **Data Source View** pane.</span></span> <span data-ttu-id="1a326-151">Puis, cliquez sur **Rechercher une table** , cliquez sur **InternetSales** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a326-151">Then click **Find Table,** click **InternetSales,** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="1a326-152">Créez les nouveaux attributs basés sur les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1a326-152">Create new attributes based on the following columns:</span></span>  
  
    -   <span data-ttu-id="1a326-153">OrderDateKey</span><span class="sxs-lookup"><span data-stu-id="1a326-153">OrderDateKey</span></span>  
  
    -   <span data-ttu-id="1a326-154">DueDateKey</span><span class="sxs-lookup"><span data-stu-id="1a326-154">DueDateKey</span></span>  
  
    -   <span data-ttu-id="1a326-155">ShipDateKey</span><span class="sxs-lookup"><span data-stu-id="1a326-155">ShipDateKey</span></span>  
  
6.  <span data-ttu-id="1a326-156">Affectez à la propriété **nom** de l’attribut **Order Date Key** la valeur `Order Date` , cliquez sur le bouton Parcourir pour la propriété **colonne de nom** , et dans la boîte de dialogue **colonne de nom** , sélectionnez **Date** comme table source et sélectionnez SimpleDate comme colonne source.</span><span class="sxs-lookup"><span data-stu-id="1a326-156">Change the **Name** property for the **Order Date Key** attribute to `Order Date` Then, click the browse button for the **Name Column** property, and in the **Name Column** dialog box, select **Date** as the source table and select SimpleDate as the source column.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="1a326-157">Modifiez la propriété de **nom** de l’attribut de **clé de date d’échéance** sur, puis `Due Date` , en utilisant la même méthode que l’attribut **Order Date Key** , remplacez la valeur de la propriété **Name Column** de cet attribut par **date. SimpleDate (WCHAR)**.</span><span class="sxs-lookup"><span data-stu-id="1a326-157">Change the **Name** property for the **Due Date Key** attribute to `Due Date`, and then, by using the same method as the **Order Date Key** attribute, change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
8.  <span data-ttu-id="1a326-158">Remplacez la propriété **Name** de l’attribut **Ship Date Key** par `Ship Date` , puis remplacez la propriété **Name Column** de cet attribut par **date. SimpleDate (WCHAR)**.</span><span class="sxs-lookup"><span data-stu-id="1a326-158">Change the **Name** property for the **Ship Date Key** attribute to `Ship Date`, and then change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
9. <span data-ttu-id="1a326-159">Sélectionnez l’onglet **Actions** du Concepteur de cube pour le cube du didacticiel de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a326-159">Switch to the **Actions** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
10. <span data-ttu-id="1a326-160">Dans la zone **Colonnes d’extraction** , cochez les cases pour ajouter les colonnes suivantes à la liste **Colonnes de retour** , puis cliquez sur **OK**:</span><span class="sxs-lookup"><span data-stu-id="1a326-160">In the **Drillthrough Columns** box, select the check boxes to add the following columns to the **Return Columns** list, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="1a326-161">Order Date</span><span class="sxs-lookup"><span data-stu-id="1a326-161">Order Date</span></span>  
  
    -   <span data-ttu-id="1a326-162">Due Date</span><span class="sxs-lookup"><span data-stu-id="1a326-162">Due Date</span></span>  
  
    -   <span data-ttu-id="1a326-163">Ship Date</span><span class="sxs-lookup"><span data-stu-id="1a326-163">Ship Date</span></span>  
  
     <span data-ttu-id="1a326-164">L'image suivante montre ces colonnes sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1a326-164">The following image shows these columns selected.</span></span>  
  
     <span data-ttu-id="1a326-165">![Zone Colonnes d'extraction](../../2014/tutorials/media/l8-action7.gif "Zone Colonnes d'extraction")</span><span class="sxs-lookup"><span data-stu-id="1a326-165">![Drillthrough Columns box](../../2014/tutorials/media/l8-action7.gif "Drillthrough Columns box")</span></span>  
  
## <a name="reviewing-the-modified-drillthrough-action"></a><span data-ttu-id="1a326-166">Vérification de l'action d'extraction modifiée</span><span class="sxs-lookup"><span data-stu-id="1a326-166">Reviewing the Modified Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="1a326-167">Dans le menu **Générer** , cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="1a326-167">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="1a326-168">Une fois le déploiement terminé, cliquez sur l’onglet **Navigateur** dans le Concepteur de cube pour le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur **Reconnexion** .</span><span class="sxs-lookup"><span data-stu-id="1a326-168">When deployment has successfully completed, switch to the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="1a326-169">Démarrez Excel.</span><span class="sxs-lookup"><span data-stu-id="1a326-169">Start Excel.</span></span>  
  
4.  <span data-ttu-id="1a326-170">Recréez le tableau croisé dynamique à l’aide de **Internet Sales-Sales Amount** dans la zone Valeurs et **Customer Geography** dans le Filtre de rapport.</span><span class="sxs-lookup"><span data-stu-id="1a326-170">Recreate the PivotTable using **Internet Sales-Sales Amount** in the Values area and **Customer Geography** in the Report Filter.</span></span>  
  
     <span data-ttu-id="1a326-171">Ajoutez un filtre qui sélectionne **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**et **Adam Powell**.</span><span class="sxs-lookup"><span data-stu-id="1a326-171">Add a filter that selects from **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**, **Adam Powell**.</span></span>  
  
5.  <span data-ttu-id="1a326-172">Cliquez sur la cellule de données **Internet Sales-Sales Amount** , pointez sur **Actions supplémentaires**, puis cliquez **Drillthrough to Order Details**.</span><span class="sxs-lookup"><span data-stu-id="1a326-172">Click the **Internet Sales-Sales Amount** data cell, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="1a326-173">Les détails des commandes expédiées à Adam Powell sont affichés dans la feuille de calcul temporaire.</span><span class="sxs-lookup"><span data-stu-id="1a326-173">The details of these orders shipped to Adam Powell are displayed in a temporary worksheet.</span></span> <span data-ttu-id="1a326-174">Cela inclut une description de l'article, le numéro de commande, la date de commande, la date d'échéance et la date de livraison, comme illustré dans l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="1a326-174">This includes item description, order number, order date, due date, and ship date information, as shown in the following image.</span></span>  
  
     <span data-ttu-id="1a326-175">![Commandes expédiées à Adam Powell](../../2014/tutorials/media/l8-action8.gif "Commandes expédiées à Adam Powell")</span><span class="sxs-lookup"><span data-stu-id="1a326-175">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action8.gif "Orders shipped to Adam Powell")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="1a326-176">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="1a326-176">Next Lesson</span></span>  
 [<span data-ttu-id="1a326-177">Leçon 9 : Définition de perspectives et de traductions</span><span class="sxs-lookup"><span data-stu-id="1a326-177">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="1a326-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a326-178">See Also</span></span>  
 <span data-ttu-id="1a326-179">[Actions &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="1a326-179">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="1a326-180">[Actions dans les modèles multidimensionnels](multidimensional-models/actions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="1a326-180">[Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="1a326-181">[Relations de dimension](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="1a326-181">[Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 <span data-ttu-id="1a326-182">[Définition d’une relation de faits](lesson-5-2-defining-a-fact-relationship.md) </span><span class="sxs-lookup"><span data-stu-id="1a326-182">[Defining a Fact Relationship](lesson-5-2-defining-a-fact-relationship.md) </span></span>  
 [<span data-ttu-id="1a326-183">Définir une relation de fait et des propriétés de relation de fait</span><span class="sxs-lookup"><span data-stu-id="1a326-183">Define a Fact Relationship and Fact Relationship Properties</span></span>](multidimensional-models/define-a-fact-relationship-and-fact-relationship-properties.md)  
  
  
