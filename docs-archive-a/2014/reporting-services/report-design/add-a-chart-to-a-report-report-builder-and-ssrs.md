---
title: Ajouter un graphique à un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6b595dc-f775-4a53-8554-74a0bf9335ec
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 789dd6cce10b0425833ea63f2f7941ea75970a25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600554"
---
# <a name="add-a-chart-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="dd738-102">Ajouter un graphique à un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="dd738-102">Add a Chart to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dd738-103">Lorsque vous souhaitez résumer des données sous un format visuel, utilisez une région de données de graphique.</span><span class="sxs-lookup"><span data-stu-id="dd738-103">When you want to summarize data in a visual format, use a Chart data region.</span></span> <span data-ttu-id="dd738-104">Il est important de choisir un type de graphique approprié au type des données que vous présentez.</span><span class="sxs-lookup"><span data-stu-id="dd738-104">It is important to choose an appropriate chart type for the type of data that you are presenting.</span></span> <span data-ttu-id="dd738-105">Cela affecte l'interprétation des données lorsqu'elles sont transformées en graphique.</span><span class="sxs-lookup"><span data-stu-id="dd738-105">This affects how well the data can be interpreted when put in chart form.</span></span> <span data-ttu-id="dd738-106">Pour plus d’informations, consultez [Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd738-106">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="dd738-107">Le moyen le plus simple d'ajouter une région de données graphique à votre rapport consiste à exécuter l'Assistant Nouveau graphique.</span><span class="sxs-lookup"><span data-stu-id="dd738-107">The simplest way to add a Chart data region to your report is to run the New Chart Wizard.</span></span> <span data-ttu-id="dd738-108">Cet Assistant propose des histogrammes, des graphiques à barres, des graphiques en courbes, des graphiques à secteurs et des graphiques en aires.</span><span class="sxs-lookup"><span data-stu-id="dd738-108">The wizard offers column, line, pie, bar, and area charts.</span></span> <span data-ttu-id="dd738-109">Pour ces types de graphiques et d'autres, vous pouvez également ajouter un graphique manuellement.</span><span class="sxs-lookup"><span data-stu-id="dd738-109">For these and other chart types, you can also add a chart manually.</span></span>  
  
 <span data-ttu-id="dd738-110">Après avoir ajouté une région de données graphique à l’aire de conception, vous pouvez faire glisser des champs de dataset du rapport pour les données numériques et non numériques vers le volet Données du graphique du graphique.</span><span class="sxs-lookup"><span data-stu-id="dd738-110">After you add a Chart data region to the design surface, you can drag report dataset fields for numeric and non-numeric data to the Chart Data pane of the chart.</span></span> <span data-ttu-id="dd738-111">Cliquez sur le graphique pour afficher le volet Données du graphique avec ses trois zones : Groupes de séries, Groupes de catégories et Valeurs.</span><span class="sxs-lookup"><span data-stu-id="dd738-111">Click the chart to display the Chart Data pane with its three areas: Series Groups, Category Groups, and Values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-chart-to-a-report-by-using-the-chart-wizard"></a><span data-ttu-id="dd738-112">Pour ajouter un graphique à un rapport à l'aide de l'Assistant Graphique</span><span class="sxs-lookup"><span data-stu-id="dd738-112">To add a chart to a report by using the Chart Wizard</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="dd738-113">L'Assistant Graphique est disponible uniquement dans le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="dd738-113">The Chart Wizard is only available in Report Builder.</span></span>  
  
     <span data-ttu-id="dd738-114">Sous l’onglet **Insérer** , cliquez sur **Graphique**, puis sur **Assistant Graphique**.</span><span class="sxs-lookup"><span data-stu-id="dd738-114">On the **Insert** tab, click **Chart**, and then click **Chart Wizard**.</span></span>  
  
2.  <span data-ttu-id="dd738-115">Suivez les étapes de l’Assistant **Nouveau graphique** .</span><span class="sxs-lookup"><span data-stu-id="dd738-115">Follow the steps in the **New** Chart wizard.</span></span>  
  
3.  <span data-ttu-id="dd738-116">Sous l’onglet **Accueil** , cliquez sur **Exécuter** pour visualiser le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="dd738-116">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="dd738-117">Sous l’onglet **Exécuter** , cliquez sur **Conception** pour continuer à utiliser le rapport.</span><span class="sxs-lookup"><span data-stu-id="dd738-117">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-chart-to-a-report"></a><span data-ttu-id="dd738-118">Pour ajouter un graphique à un rapport</span><span class="sxs-lookup"><span data-stu-id="dd738-118">To add a chart to a report</span></span>  
  
1.  <span data-ttu-id="dd738-119">Créez un rapport et définissez un dataset.</span><span class="sxs-lookup"><span data-stu-id="dd738-119">Create a report and define a dataset.</span></span> <span data-ttu-id="dd738-120">Pour plus d’informations, consultez [Ajouter des données à un rapport &#40;générateur de rapports et SSRS&#41;](../report-data/report-datasets-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd738-120">For more information, see [Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="dd738-121">Sous l’onglet **Insérer** , cliquez sur **Graphique**, puis sur **Insérer un graphique**.</span><span class="sxs-lookup"><span data-stu-id="dd738-121">On the **Insert** tab, click **Chart**, and then click **Insert Chart**.</span></span>  
  
3.  <span data-ttu-id="dd738-122">Cliquez sur l'aire de conception à l'endroit où doit venir se positionner le coin supérieur gauche du graphique, puis faites glisser la souris jusqu'à l'endroit où doit venir se positionner son coin inférieur droit.</span><span class="sxs-lookup"><span data-stu-id="dd738-122">Click on the design surface where you want the upper-left corner of the chart, and then drag to where you want the lower-right corner of the chart.</span></span>  
  
     <span data-ttu-id="dd738-123">La boîte de dialogue **Sélectionner un type de graphique** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="dd738-123">The **Select Chart Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="dd738-124">Sélectionnez le type de graphique que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="dd738-124">Select the type of chart you want to add.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="dd738-125">Cliquez sur le graphique pour afficher le volet **Données du graphique** .</span><span class="sxs-lookup"><span data-stu-id="dd738-125">Click the chart to display the **Chart Data** pane.</span></span>  
  
6.  <span data-ttu-id="dd738-126">Ajoutez un ou plusieurs champs à la zone **Valeurs** .</span><span class="sxs-lookup"><span data-stu-id="dd738-126">Add one or more fields to the **Values** area.</span></span> <span data-ttu-id="dd738-127">Ces informations seront tracées sur l'axe des ordonnées.</span><span class="sxs-lookup"><span data-stu-id="dd738-127">This information will be plotted on the value axis.</span></span>  
  
7.  <span data-ttu-id="dd738-128">Ajoutez un champ de regroupement à la zone **Groupes d’abscisses** .</span><span class="sxs-lookup"><span data-stu-id="dd738-128">Add a grouping field to the **Category Groups** area.</span></span> <span data-ttu-id="dd738-129">Quand vous ajoutez ce champ à la zone **Groupes d’abscisses** , un champ de regroupement est automatiquement créé.</span><span class="sxs-lookup"><span data-stu-id="dd738-129">When you add this field to the **Category Groups** area, a grouping field is automatically created for you.</span></span> <span data-ttu-id="dd738-130">Chaque groupe représente un point de données dans votre série.</span><span class="sxs-lookup"><span data-stu-id="dd738-130">Each group represents a data point in your series.</span></span>  
  
8.  <span data-ttu-id="dd738-131">Pour résumer les données par catégorie, cliquez avec le bouton droit sur le champ de données et cliquez sur **Propriétés de la série**.</span><span class="sxs-lookup"><span data-stu-id="dd738-131">To summarize the data by category, right-click the data field and click **Series Properties**.</span></span> <span data-ttu-id="dd738-132">Dans la zone **Catégorie** , sélectionnez le champ de catégorie dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="dd738-132">In the **Category** box, select the category field from the drop-down list.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="dd738-133">Sous l’onglet **Accueil** , cliquez sur **Exécuter** pour visualiser le rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="dd738-133">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
10. <span data-ttu-id="dd738-134">Sous l’onglet **Exécuter** , cliquez sur **Conception** pour continuer à utiliser le rapport.</span><span class="sxs-lookup"><span data-stu-id="dd738-134">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
 <span data-ttu-id="dd738-135">Sur les graphiques avec des axes, tels que les graphiques à barres et histogrammes, il est possible que l'axe des abscisses n'affiche pas toutes les étiquettes de catégorie.</span><span class="sxs-lookup"><span data-stu-id="dd738-135">On charts with axes, such as bar and column charts, the category axis may not display all the category labels.</span></span> <span data-ttu-id="dd738-136">Pour plus d’informations sur la façon de modifier les étiquettes d’axe, consultez [Spécifier un intervalle d’axe &#40;Générateur de rapports et SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd738-136">For more information about how to change the axis labels, see [Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd738-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd738-137">See Also</span></span>  
 <span data-ttu-id="dd738-138">[Graphiques &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd738-138">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd738-139">[Types de graphiques &#40;Générateur de rapports et SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd738-139">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd738-140">[Points de données vides et Null dans les graphiques &#40;Générateur de rapports et SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dd738-140">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dd738-141">[Didacticiel : ajout d’un graphique à barres à un rapport (Générateur de rapports)](https://go.microsoft.com/fwlink/?LinkId=198052) </span><span class="sxs-lookup"><span data-stu-id="dd738-141">[Tutorial: Adding a Bar Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198052) </span></span>  
 <span data-ttu-id="dd738-142">[Didacticiel : ajout d’un graphique à barres à un rapport (Concepteur de rapports)](https://go.microsoft.com/fwlink/?LinkId=198042) </span><span class="sxs-lookup"><span data-stu-id="dd738-142">[Tutorial: Adding a Bar Chart to a Report (Report Designer)](https://go.microsoft.com/fwlink/?LinkId=198042) </span></span>  
 <span data-ttu-id="dd738-143">[Didacticiel : ajout d’un graphique à secteurs à un rapport (Générateur de rapports)](https://go.microsoft.com/fwlink/?LinkId=198051) </span><span class="sxs-lookup"><span data-stu-id="dd738-143">[Tutorial: Adding a Pie Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198051) </span></span>  
 [<span data-ttu-id="dd738-144">Didacticiel : ajout d’un graphique à secteurs à un rapport (Concepteur de rapports)</span><span class="sxs-lookup"><span data-stu-id="dd738-144">Tutorial: Adding a Pie Chart to a Report (Report Designer)</span></span>](https://go.microsoft.com/fwlink/?LinkId=198041)  
  
  
