---
title: Définition et exploration des indicateurs de performance clés | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 648b9a02-1278-4f11-b940-6f0de6a4042d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44febe6c6c5d432f0cdee43e8eaaa3401c54a2c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698748"
---
# <a name="defining-and-browsing-kpis"></a><span data-ttu-id="816b6-102">Définition et exploration d'indicateurs de performance clés</span><span class="sxs-lookup"><span data-stu-id="816b6-102">Defining and Browsing KPIs</span></span>
  <span data-ttu-id="816b6-103">Pour définir un indicateur de performance clé (PKI, Key Performance Indicator), vous définissez d'abord son nom et le groupe de mesures auquel il est associé.</span><span class="sxs-lookup"><span data-stu-id="816b6-103">To define key performance indicators (KPIs), you first define a KPI name and the measure group to which the KPI is associated.</span></span> <span data-ttu-id="816b6-104">Un indicateur de performance clé peut être associé à tous les groupes de mesures ou à un seul groupe de mesures.</span><span class="sxs-lookup"><span data-stu-id="816b6-104">A KPI can be associated with all measure groups or with a single measure group.</span></span> <span data-ttu-id="816b6-105">Vous définissez ensuite les éléments suivants de l'indicateur de performance clé :</span><span class="sxs-lookup"><span data-stu-id="816b6-105">You then define the following elements of the KPI:</span></span>

-   <span data-ttu-id="816b6-106">L'expression de valeur</span><span class="sxs-lookup"><span data-stu-id="816b6-106">The value expression</span></span>

     <span data-ttu-id="816b6-107">Une expression de valeur est une mesure physique, par exemple Sales, une mesure calculée, par exemple Profit, ou un calcul qui est défini dans l'indicateur de performance clé à l'aide d'une expression MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="816b6-107">A value expression is a physical measure such as Sales, a calculated measure such as Profit, or a calculation that is defined within the KPI by using a Multidimensional Expressions (MDX) expression.</span></span>

-   <span data-ttu-id="816b6-108">L'expression d'objectif</span><span class="sxs-lookup"><span data-stu-id="816b6-108">The goal expression</span></span>

     <span data-ttu-id="816b6-109">Une expression d'objectif est soit une valeur, soit une expression MDX dont la résolution fournit une valeur, qui fixe la cible de la mesure que définit l'expression de valeur.</span><span class="sxs-lookup"><span data-stu-id="816b6-109">A goal expression is a value, or an MDX expression that resolves to a value, that defines the target for the measure that the value expression defines.</span></span> <span data-ttu-id="816b6-110">Par exemple, une expression d'objectif peut être le montant par lequel les directeurs d'une société veulent augmenter les ventes ou le bénéfice.</span><span class="sxs-lookup"><span data-stu-id="816b6-110">For example, a goal expression could be the amount by which the business managers of a company want to increase sales or profit.</span></span>

-   <span data-ttu-id="816b6-111">L'expression d'état</span><span class="sxs-lookup"><span data-stu-id="816b6-111">The status expression</span></span>

     <span data-ttu-id="816b6-112">Une expression d'état est une expression MDX que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilise pour évaluer l'état actuel de l'évolution de l'expression de valeur par rapport à l'expression d'objectif.</span><span class="sxs-lookup"><span data-stu-id="816b6-112">A status expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current status of the value expression compared to the goal expression.</span></span> <span data-ttu-id="816b6-113">Une expression de but est une valeur normalisée appartenant à la plage de -1 à +1, où -1 est synonyme de très mauvais et +1 de très bon.</span><span class="sxs-lookup"><span data-stu-id="816b6-113">A goal expression is a normalized value in the range of -1 to +1, where -1 is very bad, and +1 is very good.</span></span> <span data-ttu-id="816b6-114">L'expression d'état s'affiche avec une image pour vous aider à déterminer facilement l'état de l'expression de valeur comparée à l'expression d'objectif.</span><span class="sxs-lookup"><span data-stu-id="816b6-114">The status expression displays a graphic to help you easily determine the status of the value expression compared to the goal expression.</span></span>

-   <span data-ttu-id="816b6-115">L'expression de tendance</span><span class="sxs-lookup"><span data-stu-id="816b6-115">The trend expression</span></span>

     <span data-ttu-id="816b6-116">Une expression de tendance est une expression MDX que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilise pour évaluer la tendance actuelle de l'évolution de l'expression de valeur par rapport à l'expression d'objectif.</span><span class="sxs-lookup"><span data-stu-id="816b6-116">A trend expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current trend of the value expression compared to the goal expression.</span></span> <span data-ttu-id="816b6-117">L'expression de tendance aide l'utilisateur à déterminer rapidement si l'expression de valeur s'améliore ou se dégrade par rapport à l'expression d'objectif.</span><span class="sxs-lookup"><span data-stu-id="816b6-117">The trend expression helps the business user to quickly determine whether the value expression is becoming better or worse relative to the goal expression.</span></span> <span data-ttu-id="816b6-118">Vous pouvez associer différentes images à l'expression de tendance pour permettre aux utilisateurs dans une entreprise de comprendre la tendance d'un coup d'œil.</span><span class="sxs-lookup"><span data-stu-id="816b6-118">You can associate one of several graphics with the trend expression to help business users be able to quickly understand the trend.</span></span>

 <span data-ttu-id="816b6-119">En plus de ces éléments, vous définissez plusieurs propriétés d'un indicateur de performance clé.</span><span class="sxs-lookup"><span data-stu-id="816b6-119">In addition to these elements that you define for a KPI, you also define several properties of a KPI.</span></span> <span data-ttu-id="816b6-120">Ces propriétés incluent un dossier d'affichage, un indicateur parent si l'indicateur est calculé à partir d'autres indicateurs de performance clés, le membre de temps actif (s'il y en a un), le poids de l'indicateur de performance clé (s'il en a un) et une description.</span><span class="sxs-lookup"><span data-stu-id="816b6-120">These properties include a display folder, a parent KPI if the KPI is computed from other KPIs, the current time member if there is one, the weight of the KPI if it has one, and a description of the KPI.</span></span>

> [!NOTE]
>  <span data-ttu-id="816b6-121">Pour obtenir plus d’exemples d’indicateurs de performance clés (KPI), consultez les exemples de KPI sous l’onglet Modèles du volet Outils de calcul ou dans les exemples de l’entrepôt de données **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="816b6-121">For more examples of KPIs, see the KPI examples on the Templates tab in the Calculation Tools pane or in the examples in the **Adventure Works DW 2012** sample data warehouse.</span></span> <span data-ttu-id="816b6-122">Pour plus d’informations sur la façon d’installer cette base de données, consultez [Installer les exemples de données et de projets pour le didacticiel sur la modélisation multidimensionnelle Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="816b6-122">For more information about how to install this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

 <span data-ttu-id="816b6-123">Dans la tâche de cette leçon, vous définissez les indicateurs de performance clés dans le projet du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis vous parcourez le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en utilisant ces indicateurs de performance clés.</span><span class="sxs-lookup"><span data-stu-id="816b6-123">In the task in this lesson, you define  KPIs in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, and you then browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube by using these KPIs.</span></span> <span data-ttu-id="816b6-124">Vous allez définir les indicateurs de performance clés suivants :</span><span class="sxs-lookup"><span data-stu-id="816b6-124">You will define the following KPIs:</span></span>

-   <span data-ttu-id="816b6-125">Reseller Revenue</span><span class="sxs-lookup"><span data-stu-id="816b6-125">Reseller Revenue</span></span>

     <span data-ttu-id="816b6-126">Cet indicateur de performance clé permet de comparer les ventes de revendeurs réelles aux quotas pour les ventes de revendeurs, de mesurer leur éloignement de l'objectif et d'identifier la tendance dans la réalisation de l'objectif.</span><span class="sxs-lookup"><span data-stu-id="816b6-126">This KPI is used to measure how actual reseller sales compare to sales quotas for reseller sales, how close the sales are to the goal, and what the trend is toward reaching the goal.</span></span>

-   <span data-ttu-id="816b6-127">Product Gross Profit Margin</span><span class="sxs-lookup"><span data-stu-id="816b6-127">Product Gross Profit Margin</span></span>

     <span data-ttu-id="816b6-128">Cet indicateur de performance clé sert d'une part à déterminer l'éloignement de la marge brute totale pour chaque catégorie de produit par rapport à l'objectif de chaque catégorie de produit, et d'autre part, à identifier la tendance dans la réalisation de cet objectif.</span><span class="sxs-lookup"><span data-stu-id="816b6-128">This KPI is used to determine how close the gross profit margin is for each product category to a specified goal for each product category, and also to determine the trend toward reaching this goal.</span></span>

## <a name="defining-the-reseller-revenue-kpi"></a><span data-ttu-id="816b6-129">Définition de l'indicateur de performance clé Reseller Revenue</span><span class="sxs-lookup"><span data-stu-id="816b6-129">Defining the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="816b6-130">Ouvrez le Concepteur de cube pour le cube du didacticiel de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , puis cliquez sur l’onglet **Indicateurs de performance clés** .</span><span class="sxs-lookup"><span data-stu-id="816b6-130">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **KPIs** tab.</span></span>

     <span data-ttu-id="816b6-131">L’onglet **Indicateurs de performance clés** comporte plusieurs volets.</span><span class="sxs-lookup"><span data-stu-id="816b6-131">The **KPIs** tab includes several panes.</span></span> <span data-ttu-id="816b6-132">Sur le côté gauche de l’onglet se trouvent le volet **Organisateur d’indicateur de performance clé (KPI)** et le volet **Outils de calcul** .</span><span class="sxs-lookup"><span data-stu-id="816b6-132">On the left side of the tab are the **KPI Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="816b6-133">Le volet d’informations au milieu de l’onglet contient les détails de l’indicateur de performance clé qui est sélectionné dans le volet **Organisateur d’indicateur de performance clé (KPI)** .</span><span class="sxs-lookup"><span data-stu-id="816b6-133">The display pane in the middle of the tab contains the details of the KPI that is selected in the **KPI Organizer** pane.</span></span>

     <span data-ttu-id="816b6-134">L’image suivante montre l’onglet **Indicateurs de performance clés** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="816b6-134">The following image shows the **KPIs** tab of Cube Designer.</span></span>

     <span data-ttu-id="816b6-135">![Onglet Indicateurs de performance clés du Concepteur de cube](../../2014/tutorials/media/l7-kpi-1.gif "Onglet Indicateurs de performance clés du Concepteur de cube")</span><span class="sxs-lookup"><span data-stu-id="816b6-135">![KPIs tab of Cube Designer](../../2014/tutorials/media/l7-kpi-1.gif "KPIs tab of Cube Designer")</span></span>

2.  <span data-ttu-id="816b6-136">Dans la barre d’outils de l’onglet **Indicateurs de performance clés** , cliquez sur le bouton **Nouvel indicateur de performance clé (KPI)** .</span><span class="sxs-lookup"><span data-stu-id="816b6-136">On the toolbar of the **KPIs** tab, click the **New KPI** button.</span></span>

     <span data-ttu-id="816b6-137">Un modèle d'indicateur de performance clé vide apparaît dans le volet d'informations, comme le montre l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="816b6-137">A blank KPI template appears in the display pane, as shown in the following image.</span></span>

     <span data-ttu-id="816b6-138">![Modèle d'indicateur de performance clé vide dans le volet d'informations](../../2014/tutorials/media/l7-kpi-2.gif "Modèle d'indicateur de performance clé vide dans le volet d'informations")</span><span class="sxs-lookup"><span data-stu-id="816b6-138">![Blank KPI template in display pane](../../2014/tutorials/media/l7-kpi-2.gif "Blank KPI template in display pane")</span></span>

3.  <span data-ttu-id="816b6-139">Dans la zone **nom** , tapez `Reseller Revenue` , puis sélectionnez **Reseller Sales** dans la liste groupe de **mesures associé** .</span><span class="sxs-lookup"><span data-stu-id="816b6-139">In the **Name** box, type `Reseller Revenue`, and then select **Reseller Sales** in the **Associated measure group** list.</span></span>

4.  <span data-ttu-id="816b6-140">Sous l’onglet **Métadonnées** du volet **Outils de calcul** , développez **Mesures**, **Reseller Sales**, puis faites glisser la mesure **Reseller Sales-Sales Amount** jusqu’à la zone **Expression de valeur** .</span><span class="sxs-lookup"><span data-stu-id="816b6-140">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Reseller Sales**, and then drag the **Reseller Sales-Sales Amount** measure to the **Value Expression** box.</span></span>

5.  <span data-ttu-id="816b6-141">Sous l’onglet **Métadonnées** du volet **Outils de calcul** , développez **Mesures**, **Sales Quotas**, puis faites glisser la mesure **Sales Amount Quota** jusqu’à la zone **Expression d’objectif** .</span><span class="sxs-lookup"><span data-stu-id="816b6-141">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Sales Quotas**, and then drag the **Sales Amount Quota** measure to the **Goal Expression** box.</span></span>

6.  <span data-ttu-id="816b6-142">Vérifiez que l’indicateur **Jauge** est sélectionné dans la liste **Indicateur d’état** , puis tapez l’expression MDX suivante dans la zone **Expression d’état** :</span><span class="sxs-lookup"><span data-stu-id="816b6-142">Verify that **Gauge** is selected in the **Status indicator** list, and then type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
     When 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.95
       Then 1
     When
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")<.95
       And 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.85
       Then 0
      Else-1
    End
    ```

     <span data-ttu-id="816b6-143">Cette expression MDX fournit la base d'évaluation des progrès réalisés en direction de l'objectif.</span><span class="sxs-lookup"><span data-stu-id="816b6-143">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span> <span data-ttu-id="816b6-144">Dans cette expression MDX, si les ventes de revendeurs réelles s'élèvent à plus de 85 pour cent de l'objectif, une valeur de 0 est utilisée pour remplir l'image choisie.</span><span class="sxs-lookup"><span data-stu-id="816b6-144">In this MDX expression, if actual reseller sales are more than 85 percent of the goal, a value of 0 is used to populate the chosen graphic.</span></span> <span data-ttu-id="816b6-145">Comme la jauge est l'image choisie, le pointeur de la jauge sera à mi-chemin entre vide et plein.</span><span class="sxs-lookup"><span data-stu-id="816b6-145">Because a gauge is the chosen graphic, the pointer in the gauge will be half-way between empty and full.</span></span> <span data-ttu-id="816b6-146">Si les ventes de revendeurs réelles dépassent 90 pour cent de l'objectif, le pointeur de la jauge sera aux trois-quarts du chemin entre vide et plein.</span><span class="sxs-lookup"><span data-stu-id="816b6-146">If actual reseller sales are more the 90 percent, the pointer on the gauge will be three-fourths of the way between empty and full.</span></span>

7.  <span data-ttu-id="816b6-147">Vérifiez que l’indicateur **Flèche standard** est sélectionné dans la liste **Indicateur de tendance** , puis tapez l’expression suivante dans la zone **Expression de tendance** :</span><span class="sxs-lookup"><span data-stu-id="816b6-147">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following expression in the **Trend expression** box:</span></span>

    ```
    Case
     When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
     When  (
      KpiValue("Reseller Revenue") - 
       (KpiValue("Reseller Revenue"), 
        ParallelPeriod
         ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
          /
          (KpiValue ("Reseller Revenue"),
           ParallelPeriod
            ([Date].[Calendar Date].[Calendar Year],1,
             [Date].[Calendar Date].CurrentMember)))
           >=.02
      Then 1
       When(
        KpiValue("Reseller Revenue") - 
         (KpiValue ( "Reseller Revenue" ),
          ParallelPeriod
           ([Date].[Calendar Date].[Calendar Year],1,
            [Date].[Calendar Date].CurrentMember))
           /
            (KpiValue("Reseller Revenue"),
             ParallelPeriod
              ([Date].[Calendar Date].[Calendar Year],1,
                [Date].[Calendar Date].CurrentMember)))
            <=.02
      Then -1
       Else 0
    End
    ```

     <span data-ttu-id="816b6-148">Cette expression MDX fournit la base d'évaluation de la tendance dans la réalisation de l'objectif défini.</span><span class="sxs-lookup"><span data-stu-id="816b6-148">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-reseller-revenue-kpi"></a><span data-ttu-id="816b6-149">Exploration du cube en utilisant l'indicateur de performance clé Reseller Revenue</span><span class="sxs-lookup"><span data-stu-id="816b6-149">Browsing the Cube by Using the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="816b6-150">Dans le menu **Générer** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="816b6-150">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="816b6-151">Après avoir déployé le didacticiel, cliquez sur le bouton **Mode Navigateur** dans la barre d’outils de l’onglet **Indicateurs de performance clés** , puis cliquez sur **Reconnexion**.</span><span class="sxs-lookup"><span data-stu-id="816b6-151">When deployment has successfully completed, on the toolbar of the **KPIs** tab, click the **Browser View** button, and then click **Reconnect**.</span></span>

     <span data-ttu-id="816b6-152">Les jauges d’état et de tendance sont affichées dans le volet **Navigateur d’indicateur de performance clé (KPI)** pour les ventes de revendeurs en fonction des valeurs du membre par défaut de chaque dimension, avec la valeur de l’expression de valeur et de l’expression d’objectif.</span><span class="sxs-lookup"><span data-stu-id="816b6-152">The status and trend gauges are displayed in the **KPI Browser** pane for reseller sales based on the values for the default member of each dimension, together with the value for the value and the goal.</span></span> <span data-ttu-id="816b6-153">Le membre par défaut de chaque dimension est le membre Tous du niveau Tous parce que vous n'avez pas défini d'autre membre de dimension que le membre par défaut.</span><span class="sxs-lookup"><span data-stu-id="816b6-153">The default member of each dimension is the All member of the All level, because you have not defined any other member of any dimension as the default member.</span></span>

3.  <span data-ttu-id="816b6-154">Dans le volet de filtre, sélectionnez **Sales Territory** dans la liste **Dimension** , sélectionnez **Sales Territories** dans la liste **Hiérarchie** , sélectionnez **Equal** dans la liste **Opérateur** , puis cochez la case **North America** dans la liste **Expression de filtre** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="816b6-154">In the filter pane, select **Sales Territory** in the **Dimension** list, select **Sales Territories** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **North America** check box in the **Filter Expression** list, and then click **OK**.</span></span>

4.  <span data-ttu-id="816b6-155">Dans la ligne suivante du volet **Filtre** , sélectionnez **Date** dans la liste **Dimension** , sélectionnez **Calendar Date** dans la liste **Hiérarchie** , sélectionnez **Equal** dans la liste **Opérateur** , puis cochez la case **Q3 CY 2007** dans la liste **Expression de filtre** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="816b6-155">In the next row in the **Filter** pane, select **Date** in the **Dimension** list, select **Calendar Date** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **Q3 CY 2007** check box in the **Filter Expression** list, and then click **OK**.</span></span>

5.  <span data-ttu-id="816b6-156">Cliquez n’importe où dans le volet **Navigateur d’indicateur de performance clé (KPI)** pour actualiser les valeurs de **l’indicateur de performance clé Reseller Revenue**.</span><span class="sxs-lookup"><span data-stu-id="816b6-156">Click anywhere in the **KPI Browser** pane to update the values for the **Reseller Revenue KPI**.</span></span>

     <span data-ttu-id="816b6-157">Notez que les sections **Valeur**, **Objectif**et **État** de l’indicateur de performance clé reflètent les valeurs pour la nouvelle période de temps.</span><span class="sxs-lookup"><span data-stu-id="816b6-157">Notice that the **Value**, **Goal**, and **Status** sections of the KPI reflect the values for the new time period</span></span>

## <a name="defining-the-product-gross-profit-margin-kpi"></a><span data-ttu-id="816b6-158">Définition de l'indicateur de performance clé Product Gross Profit Margin</span><span class="sxs-lookup"><span data-stu-id="816b6-158">Defining the Product Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="816b6-159">Cliquez sur le bouton **Mode Formulaire** dans la barre d’outils de l’onglet **Indicateurs de performance clés** , puis cliquez sur le bouton **Nouvel indicateur de performance clé (KPI)** .</span><span class="sxs-lookup"><span data-stu-id="816b6-159">Click the **Form View** button on the toolbar of the **KPIs** tab, and then click the **New KPI** button.</span></span>

2.  <span data-ttu-id="816b6-160">Dans la zone **nom** , tapez `Product Gross Profit Margin` , puis vérifiez que **\<All>** apparaît dans la liste **groupe de mesures associé** .</span><span class="sxs-lookup"><span data-stu-id="816b6-160">In the **Name** box, type `Product Gross Profit Margin`, and then verify that **\<All>** appears in the **Associated measure group** list.</span></span>

3.  <span data-ttu-id="816b6-161">Sous l’onglet **Métadonnées** du volet **Outils de calcul** , faites glisser la mesure **Total GPM** jusqu’à la zone **Expression de valeur** .</span><span class="sxs-lookup"><span data-stu-id="816b6-161">In the **Metadata** tab in the **Calculation Tools** pane, drag the **Total GPM** measure to the **Value Expression** box.</span></span>

4.  <span data-ttu-id="816b6-162">Dans la zone **Expression d’objectif** , tapez l’expression suivante :</span><span class="sxs-lookup"><span data-stu-id="816b6-162">In the **Goal Expression** box, type the following expression:</span></span>

    ```
    Case
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Accessories]
        Then .40                 
        When [Product].[Category].CurrentMember 
          Is [Product].[Category].[Bikes]
        Then .12                
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Clothing]
        Then .20
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Components]
        Then .10
        Else .12            
    End
    ```

5.  <span data-ttu-id="816b6-163">Dans la liste **Indicateur d’état** , sélectionnez **Cylindre**.</span><span class="sxs-lookup"><span data-stu-id="816b6-163">In the **Status indicator** list, select **Cylinder**.</span></span>

6.  <span data-ttu-id="816b6-164">Tapez l’expression MDX suivante dans la zone **Expression d’état** :</span><span class="sxs-lookup"><span data-stu-id="816b6-164">Type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .90
        Then 1
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) <  .90
             And 
             KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .80
        Then 0
        Else -1
    End
    ```

     <span data-ttu-id="816b6-165">Cette expression MDX fournit la base d'évaluation des progrès réalisés en direction de l'objectif.</span><span class="sxs-lookup"><span data-stu-id="816b6-165">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span>

7.  <span data-ttu-id="816b6-166">Vérifiez que l’indicateur **Flèche standard** est sélectionné dans la liste **Indicateur de tendance** , puis tapez l’expression MDX suivante dans la zone **Expression de tendance** :</span><span class="sxs-lookup"><span data-stu-id="816b6-166">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following MDX expression in the **Trend expression** box:</span></span>

    ```
    Case
    When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
       When VBA!Abs
        (
          KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            ) /
            (
              KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            )  
          ) <=.02
      Then 0
      When KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[ Calendar Date].[ Calendar Year],
               1,
               [Date].[ Calendar Date].CurrentMember
             )
           ) /
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[Calendar Date].[Calendar Year],
               1,
               [Date].[Calendar Date].CurrentMember
             )
           )  >.02
      Then 1
      Else -1
    End
    ```

     <span data-ttu-id="816b6-167">Cette expression MDX fournit la base d'évaluation de la tendance dans la réalisation de l'objectif défini.</span><span class="sxs-lookup"><span data-stu-id="816b6-167">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-total-gross-profit-margin-kpi"></a><span data-ttu-id="816b6-168">Exploration du cube en utilisant l'indicateur de performance clé Total Gross Profit Margin</span><span class="sxs-lookup"><span data-stu-id="816b6-168">Browsing the Cube by Using the Total Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="816b6-169">Dans le menu **Générer** , cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="816b6-169">On the **Build** menu, click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="816b6-170">Après avoir déployé le didacticiel, cliquez sur **Reconnexion** dans la barre d’outils de l’onglet **Indicateurs de performance clés** , puis cliquez sur **Mode Navigateur**.</span><span class="sxs-lookup"><span data-stu-id="816b6-170">When deployment has successfully completed, click **Reconnect** on the toolbar of the **KPIs** tab, and then click **Browser View**.</span></span>

     <span data-ttu-id="816b6-171">L' `Product Gross Profit Margin` indicateur de performance clé apparaît et affiche la valeur KPI pour **Q3 CY 2007** et le secteur de vente **Amérique du Nord** .</span><span class="sxs-lookup"><span data-stu-id="816b6-171">The `Product Gross Profit Margin` KPI appears and displays the KPI value for **Q3 CY 2007** and the **North America** sales territory.</span></span>

3.  <span data-ttu-id="816b6-172">Dans le volet **Filtre** , sélectionnez **Product** dans la liste **Dimension** , sélectionnez **Category** dans la liste **Hiérarchie** , sélectionnez **Equal** dans la liste **Opérateur** , sélectionnez **Bikes** dans la liste **Expression de filtre** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="816b6-172">In the **Filter** pane, select **Product** in the **Dimension** list, select **Category** in the **Hierarchy** list, select **Equal** in the **Operator** list, and then select **Bikes** in the **Filter Expression** list, and then click **OK**.</span></span>

     <span data-ttu-id="816b6-173">La marge brute de la vente de vélos par les revendeurs en Amérique du Nord pour le troisième trimestre de l'année fiscale 2007 s'affiche.</span><span class="sxs-lookup"><span data-stu-id="816b6-173">The gross profit margin for the sale of Bikes by resellers in North America in Q3 CY 2007 appears.</span></span>

## <a name="next-lesson"></a><span data-ttu-id="816b6-174">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="816b6-174">Next Lesson</span></span>
 [<span data-ttu-id="816b6-175">Leçon 8 : Définition des actions</span><span class="sxs-lookup"><span data-stu-id="816b6-175">Lesson 8: Defining Actions</span></span>](lesson-8-defining-actions.md)


