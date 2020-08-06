---
title: Insérer ou supprimer une indicateur (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a8b1aac1-53ef-47a4-afc0-8fa866c6c480
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 186ed4f5b6cf7cb239dc7c33a11089c11bccae14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703875"
---
# <a name="add-or-delete-an-indicator-report-builder-and-ssrs"></a><span data-ttu-id="edc17-102">Ajouter ou supprimer un indicateur (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="edc17-102">Add or Delete an Indicator (Report Builder and SSRS)</span></span>
  <span data-ttu-id="edc17-103">Les indicateurs sont des jauges minimales qui communiquent en un coup d'œil l'état d'une valeur de donnée unique.</span><span class="sxs-lookup"><span data-stu-id="edc17-103">Indicators are minimal gauges that convey the state of a single data value at a glance.</span></span> <span data-ttu-id="edc17-104">Pour plus d’informations les concernant, consultez [Indicateurs &#40;Générateur de rapports et SSRS&#41;](indicators-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="edc17-104">For more information about them, see [Indicators &#40;Report Builder and SSRS&#41;](indicators-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="edc17-105">Les indicateurs sont généralement placés dans des cellules d'une table ou d'une matrice, mais vous pouvez également les utiliser seuls, côte à côte avec des jauges ou incorporés dans des jauges.</span><span class="sxs-lookup"><span data-stu-id="edc17-105">Indicators are commonly placed in cells in a table or matrix, but you can also use indicators by themselves, side-by-side with gauges, or embedded in gauges.</span></span>  
  
 <span data-ttu-id="edc17-106">Lorsque vous ajoutez un indicateur pour la première fois, il est configuré par défaut pour utiliser des pourcentages comme unités de mesure.</span><span class="sxs-lookup"><span data-stu-id="edc17-106">When you first add an indicator, it is by default configured to use percentages as measurement units.</span></span> <span data-ttu-id="edc17-107">Les plages de pourcentage sont réparties uniformément entre les membres du jeu d'indicateurs, et l'étendue de valeurs indiquée par l'indicateur correspond au parent de l'indicateur tel qu'une table ou une matrice.</span><span class="sxs-lookup"><span data-stu-id="edc17-107">The percentage ranges are evenly distributed across members of the indicator set, and the scope of values shown by the indicator is the parent of the indicator such as a table or matrix.</span></span>  
  
 <span data-ttu-id="edc17-108">Vous pouvez mettre à jour les valeurs et les états d'indicateurs.</span><span class="sxs-lookup"><span data-stu-id="edc17-108">You can update the values and states of indicators.</span></span> <span data-ttu-id="edc17-109">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="edc17-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="edc17-110">Modifier les icônes d’indicateur et jeux d’indicateurs &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="edc17-110">Change Indicator Icons and Indicator Sets &#40;Report Builder and SSRS&#41;</span></span>](change-indicator-icons-and-indicator-sets-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="edc17-111">Définir et configurer des unités de mesure &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="edc17-111">Set and Configure Measurement Units &#40;Report Builder and SSRS&#41;</span></span>](set-and-configure-measurement-units-report-builder-and-ssrs.md)  
  
-   [<span data-ttu-id="edc17-112">Définir l’étendue de synchronisation &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="edc17-112">Set Synchronization Scope &#40;Report Builder and SSRS&#41;</span></span>](set-synchronization-scope-report-builder-and-ssrs.md)  
  
 <span data-ttu-id="edc17-113">Étant donné qu’un indicateur est positionné à l’intérieur du panneau de jauge, vous devez sélectionner l’indicateur au lieu du panneau quand vous souhaitez configurer l’indicateur à l’aide de la boîte de dialogue **Propriétés des indicateurs** ou du volet **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="edc17-113">Because an indicator is positioned inside the gauge panel, you need to select the indicator instead of the panel when you want to configure the indicator by using the **Indicators Properties** dialog box or the **Properties** pane.</span></span> <span data-ttu-id="edc17-114">L'image suivante illustre un indicateur sélectionné dans son panneau de jauge.</span><span class="sxs-lookup"><span data-stu-id="edc17-114">The following picture shows a selected indicator in its gauge panel.</span></span>  
  
 <span data-ttu-id="edc17-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span><span class="sxs-lookup"><span data-stu-id="edc17-115">![rs_GaugePanelWithIndicator](../media/rs-gaugepanelwithindicator.gif "rs_GaugePanelWithIndicator")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="edc17-116">Selon la largeur de colonne et la longueur des valeurs de données, le texte des cellules de table ou de matrice peut être renvoyé à la ligne automatiquement et s'afficher sur plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="edc17-116">Depending on column width and the length of data values, the text in table or matrix cells might wrap and display text on multiple lines.</span></span> <span data-ttu-id="edc17-117">Lorsque cela se produit, l'icône d'indicateur peut s'étirer et changer de forme.</span><span class="sxs-lookup"><span data-stu-id="edc17-117">When this occurs, the indicator icon might be stretched and change shape.</span></span> <span data-ttu-id="edc17-118">Cela peut rendre l'icône d'indicateur moins lisible.</span><span class="sxs-lookup"><span data-stu-id="edc17-118">This can make the indicator icon less readable.</span></span> <span data-ttu-id="edc17-119">Placez l'indicateur à l'intérieur d'un rectangle pour vous assurer que l'icône n'est pas étirée.</span><span class="sxs-lookup"><span data-stu-id="edc17-119">Place the indicator inside a rectangle to ensure that the icon is never stretched.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="edc17-120">Pour ajouter un indicateur à une table ou une matrice</span><span class="sxs-lookup"><span data-stu-id="edc17-120">To add an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="edc17-121">Ouvrez un rapport existant ou créez un rapport qui contient une table et une matrice avec les données que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="edc17-121">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="edc17-122">Pour plus d’informations, consultez [Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) ou [Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="edc17-122">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="edc17-123">Insérez une colonne dans votre table ou matrice.</span><span class="sxs-lookup"><span data-stu-id="edc17-123">Insert a column in your table or matrix.</span></span> <span data-ttu-id="edc17-124">Pour plus d’informations, consultez [Insérer ou supprimer une colonne &#40;Générateur de rapports et SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="edc17-124">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="edc17-125">Le cas échéant, sous l’onglet **Insérer** , cliquez sur **Rectangle**, puis sur une cellule dans la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="edc17-125">Optionally, on the **Insert** tab, click **Rectangle**, and then click a cell in the new column.</span></span>  
  
4.  <span data-ttu-id="edc17-126">Sous l’onglet **Insérer** , cliquez sur **Indicateur**, puis sur une cellule dans la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="edc17-126">On the **Insert** tab, click **Indicator**, and then click a cell in the new column.</span></span>  
  
     <span data-ttu-id="edc17-127">Si vous avez ajouté un rectangle à une cellule, cliquez sur cette cellule.</span><span class="sxs-lookup"><span data-stu-id="edc17-127">If you added a rectangle to a cell, click that cell.</span></span>  
  
5.  <span data-ttu-id="edc17-128">Dans la boîte de dialogue **Sélectionner le style d’indicateur** , dans le volet gauche, cliquez sur le type d’indicateur de votre choix, puis sur le jeu d’indicateurs.</span><span class="sxs-lookup"><span data-stu-id="edc17-128">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
6.  <span data-ttu-id="edc17-129">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="edc17-129">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="edc17-130">Cliquez sur l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="edc17-130">Click the indicator.</span></span> <span data-ttu-id="edc17-131">Le volet **Données de la jauge** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="edc17-131">The **Gauge Data** pane opens.</span></span>  
  
8.  <span data-ttu-id="edc17-132">Dans la zone **Valeurs** , dans la liste déroulante **(Non spécifié)** , cliquez sur le champ dont vous souhaitez afficher les valeurs sous la forme d’un indicateur.</span><span class="sxs-lookup"><span data-stu-id="edc17-132">In the **Values** area, in the **(Unspecified)** drop-down list, click the field whose values you want to display as an indicator.</span></span>  
  
     <span data-ttu-id="edc17-133">L'indicateur est configuré pour utiliser des valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="edc17-133">The indicator is configured to use default values.</span></span> <span data-ttu-id="edc17-134">Par défaut, les indicateurs sont configurés pour utiliser des pourcentages comme unités de mesure et les plages de pourcentage sont réparties uniformément entre les membres de l'indicateur et la valeur que l'indicateur indique utilise l'étendue du groupe le plus proche.</span><span class="sxs-lookup"><span data-stu-id="edc17-134">By default, indicators are configured use percentages as measurement units and the percentage ranges are evenly distributed across the members of the indicator and the value that the indicator conveys uses the scope of the nearest group.</span></span>  
  
### <a name="to-delete-an-indicator-to-a-table-or-matrix"></a><span data-ttu-id="edc17-135">Pour supprimer un indicateur dans une table ou une matrice</span><span class="sxs-lookup"><span data-stu-id="edc17-135">To delete an indicator to a table or matrix</span></span>  
  
1.  <span data-ttu-id="edc17-136">Cliquez avec le bouton droit sur l’indicateur à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="edc17-136">Right-click the indicator to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="edc17-137">Un indicateur peut être positionné à l'intérieur d'un panneau de jauge qui contient d'autres indicateurs ou jauges.</span><span class="sxs-lookup"><span data-stu-id="edc17-137">An indicator might be positioned inside a gauge panel that contains other indicators or gauges.</span></span> <span data-ttu-id="edc17-138">Si les panneaux de jauge contiennent plusieurs éléments, veillez à cliquer sur l'indicateur pour le supprimer, et non sur le panneau de jauge.</span><span class="sxs-lookup"><span data-stu-id="edc17-138">If the gauge panels contain multiple items, be sure to click the indicator to delete it, not the gauge panel.</span></span> <span data-ttu-id="edc17-139">Si vous cliquez sur le panneau de jauge et le supprimez, le panneau de jauge et tous les éléments qu'il contient sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="edc17-139">If you click and then delete the gauge panel, the gauge panels and all the items in it are deleted.</span></span>  
  
2.  <span data-ttu-id="edc17-140">Cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="edc17-140">Click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edc17-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="edc17-141">See Also</span></span>  
 [<span data-ttu-id="edc17-142">Indicateurs &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="edc17-142">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
