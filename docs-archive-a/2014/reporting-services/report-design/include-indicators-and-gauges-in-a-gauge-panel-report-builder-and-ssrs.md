---
title: Inclure des indicateurs et des jauges dans un panneau de jauge (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4dff9b67-b483-4c51-a822-6dbe706a6840
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b1107745f54cd94abd7507a3e9b5a706ca5402de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707155"
---
# <a name="include-indicators-and-gauges-in-a-gauge-panel-report-builder-and-ssrs"></a><span data-ttu-id="c1a5d-102">Inclure des indicateurs et des jauges dans un panneau de jauge (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="c1a5d-102">Include Indicators and Gauges in a Gauge Panel (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c1a5d-103">Le panneau de jauge est le conteneur de niveau supérieur qui contient un ou plusieurs jauges et indicateurs.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-103">The gauge panel is the top-level container that holds one or more gauges and indicators.</span></span> <span data-ttu-id="c1a5d-104">Les indicateurs peuvent être incorporés dans les jauges ou placés en regard de celles-ci dans le panneau de jauge.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-104">Indicators can be embedded in gauges or placed next to them in the gauge panel.</span></span>  
  
 <span data-ttu-id="c1a5d-105">Si l'indicateur et la jauge sont adjacents dans le panneau de jauge et affichent des données de champs différents, vous pouvez ajouter des étiquettes pour clarifier les données transmises par la jauge et l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-105">If the indicator and gauge are adjacent in the gauge panel and show data from different fields, you might want to add labels to make it clear what data the gauge and indicator convey.</span></span>  
  
 <span data-ttu-id="c1a5d-106">Les options de jauge et d'indicateur peuvent être définies à l'aide d'expressions.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-106">Gauge and indicator options can be set by using expressions.</span></span> <span data-ttu-id="c1a5d-107">Pour plus d’informations, consultez [Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c1a5d-107">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-embed-an-indicator-in-a-gauge"></a><span data-ttu-id="c1a5d-108">Pour incorporer un indicateur dans une jauge</span><span class="sxs-lookup"><span data-stu-id="c1a5d-108">To embed an indicator in a gauge</span></span>  
  
1.  <span data-ttu-id="c1a5d-109">Ouvrez un rapport existant ou créez un rapport qui contient une table et une matrice avec les données que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-109">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="c1a5d-110">Pour plus d’informations, consultez [Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) ou [Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c1a5d-110">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="c1a5d-111">Insérez une colonne dans votre table ou matrice.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-111">Insert a column in your table or matrix.</span></span> <span data-ttu-id="c1a5d-112">Pour plus d’informations, consultez [Insérer ou supprimer une colonne &#40;Générateur de rapports et SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c1a5d-112">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="c1a5d-113">Sous l’onglet **Insérer** , dans le groupe **Régions de données** , cliquez sur **Jauge**, puis sur une cellule dans la nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-113">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then, and then click a cell in the new column.</span></span> <span data-ttu-id="c1a5d-114">La boîte de dialogue **Sélectionner le type de jauge** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-114">The **Select Gauge Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="c1a5d-115">Cliquez sur **Radial**.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-115">Click **Radial**.</span></span> <span data-ttu-id="c1a5d-116">La première jauge radiale est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-116">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c1a5d-117">Cliquez sur la jauge.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-117">Click the gauge.</span></span> <span data-ttu-id="c1a5d-118">Le volet **Données de la jauge** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-118">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="c1a5d-119">Dans la zone **Valeurs** , dans la zone de liste **(Non spécifié)** , cliquez sur le champ dont vous souhaitez afficher les valeurs dans la jauge.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-119">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="c1a5d-120">Vous pouvez également faire glisser le champ à utiliser à partir du dataset du rapport.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-120">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="c1a5d-121">Cliquez avec le bouton droit sur la jauge, cliquez sur **Ajouter un indicateur**, puis sur **Enfant**.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-121">Right-click the gauge, click **Add Indicator**, and then click **Child**.</span></span> <span data-ttu-id="c1a5d-122">La boîte de dialogue **Sélectionner un style d’indicateur** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-122">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="c1a5d-123">Dans la boîte de dialogue **Sélectionner le style d’indicateur** , dans le volet gauche, cliquez sur le type d’indicateur de votre choix, puis sur le jeu d’indicateurs.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-123">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="c1a5d-124">Cliquez sur l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-124">Click the indicator.</span></span> <span data-ttu-id="c1a5d-125">Le volet **Données de la jauge** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-125">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="c1a5d-126">Dans la zone **Valeurs** , dans la zone de liste **(Non spécifié)** , cliquez sur le champ dont vous souhaitez afficher les valeurs sous la forme d’un indicateur.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-126">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="c1a5d-127">Vous pouvez également faire glisser le champ à utiliser à partir du dataset du rapport.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-127">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="c1a5d-128">Il peut s'agir du même champ que celui que vous utilisez dans la jauge ou d'un champ différent.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-128">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-show-an-indicator-and-gauge-side-by-side"></a><span data-ttu-id="c1a5d-129">Pour afficher côte à côte un indicateur et une jauge</span><span class="sxs-lookup"><span data-stu-id="c1a5d-129">To show an indicator and gauge side by side</span></span>  
  
1.  <span data-ttu-id="c1a5d-130">Ouvrez un rapport existant ou créez un rapport qui contient une table et une matrice avec les données que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-130">Open an existing report or create a new report that contains a table and matrix with the data you want to display.</span></span> <span data-ttu-id="c1a5d-131">Pour plus d’informations, consultez [Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) ou [Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c1a5d-131">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) or [Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="c1a5d-132">Insérez une colonne dans votre table ou matrice.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-132">Insert a column in your table or matrix.</span></span> <span data-ttu-id="c1a5d-133">Pour plus d’informations, consultez [Insérer ou supprimer une colonne &#40;Générateur de rapports et SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c1a5d-133">For more information, see [Insert or Delete a Column &#40;Report Builder and SSRS&#41;](insert-or-delete-a-column-report-builder-and-ssrs.md).</span></span>  
  
3.  <span data-ttu-id="c1a5d-134">Sous l’onglet **Insérer** , dans le groupe **Régions de données** , cliquez sur **Jauge**, puis sur une cellule dans la colonne que vous avez insérée.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-134">On the **Insert** tab, in the **Data Regions** group, click **Gauge**, and then click a cell in the column you inserted.</span></span> <span data-ttu-id="c1a5d-135">La boîte de dialogue **Sélectionner le type de jauge** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-135">The **Select Gauge Type** dialog appears.</span></span>  
  
4.  <span data-ttu-id="c1a5d-136">Cliquez sur **Radial**.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-136">Click **Radial**.</span></span> <span data-ttu-id="c1a5d-137">La première jauge radiale est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-137">The first radial gauge is selected.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c1a5d-138">Cliquez sur la jauge.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-138">Click the gauge.</span></span> <span data-ttu-id="c1a5d-139">Le volet **Données de la jauge** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-139">The **Gauge Data** pane opens.</span></span>  
  
7.  <span data-ttu-id="c1a5d-140">Dans la zone **Valeurs** , dans la zone de liste **(Non spécifié)** , cliquez sur le champ dont vous souhaitez afficher les valeurs dans la jauge.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-140">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display in the gauge.</span></span> <span data-ttu-id="c1a5d-141">Vous pouvez également faire glisser le champ à utiliser à partir du dataset du rapport.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-141">Alternatively, drag the field to use from the report dataset.</span></span>  
  
8.  <span data-ttu-id="c1a5d-142">Cliquez avec le bouton droit sur la jauge, cliquez sur **Ajouter un indicateur**, puis sur **Adjacent**.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-142">Right-click the gauge, click **Add Indicator**, and then click **Adjacent**.</span></span> <span data-ttu-id="c1a5d-143">La boîte de dialogue **Sélectionner un style d’indicateur** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-143">The **Select Indicator Style** dialog box opens.</span></span>  
  
9. <span data-ttu-id="c1a5d-144">Dans la boîte de dialogue **Sélectionner le style d’indicateur** , dans le volet gauche, cliquez sur le type d’indicateur de votre choix, puis sur le jeu d’indicateurs.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-144">In the **Select Indicator Style** dialog box, in the left pane, click the indicator type you want, and then click the indicator set.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
11. <span data-ttu-id="c1a5d-145">Cliquez sur l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-145">Click the indicator.</span></span> <span data-ttu-id="c1a5d-146">Le volet **Données de la jauge** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-146">The **Gauge Data** pane opens.</span></span>  
  
12. <span data-ttu-id="c1a5d-147">Dans la zone **Valeurs** , dans la zone de liste **(Non spécifié)** , cliquez sur le champ dont vous souhaitez afficher les valeurs sous la forme d’un indicateur.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-147">In the **Values** area, in the **(Unspecified)** list box, click the field whose values you want to display as an indicator.</span></span> <span data-ttu-id="c1a5d-148">Vous pouvez également faire glisser le champ à utiliser à partir du dataset du rapport.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-148">Alternatively, drag the field to use from the report dataset.</span></span>  
  
     <span data-ttu-id="c1a5d-149">Il peut s'agir du même champ que celui que vous utilisez dans la jauge ou d'un champ différent.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-149">The field can be the same or a different field from the one you use in the gauge.</span></span>  
  
13. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
14. <span data-ttu-id="c1a5d-150">Cliquez avec le bouton droit sur le panneau de jauge, puis cliquez sur **Ajouter une étiquette**.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-150">Right-click the gauge panel and click **Add Label**.</span></span> <span data-ttu-id="c1a5d-151">Une étiquette est ajoutée au panneau de jauge.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-151">A label is added to the gauge panel.</span></span> <span data-ttu-id="c1a5d-152">Répétez l'opération une fois de plus.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-152">Repeat one more time.</span></span>  
  
     <span data-ttu-id="c1a5d-153">Le panneau de jauge a deux étiquettes.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-153">The gauge panel has two labels.</span></span>  
  
15. <span data-ttu-id="c1a5d-154">Faites glisser chaque étiquette vers un emplacement près de la jauge ou de l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="c1a5d-154">Drag each label to a location near the gauge or indicator.</span></span>  
  
16. <span data-ttu-id="c1a5d-155">Cliquez avec le bouton droit sur l’étiquette près de la jauge, cliquez sur **Propriétés de l’étiquette**, puis tapez le texte que vous souhaitez dans la zone **Texte** .</span><span class="sxs-lookup"><span data-stu-id="c1a5d-155">Right-click the label near the gauge, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
17. <span data-ttu-id="c1a5d-156">Cliquez avec le bouton droit sur l’étiquette près de l’indicateur, cliquez sur **Propriétés de l’étiquette**, puis tapez le texte que vous souhaitez dans la zone **Texte** .</span><span class="sxs-lookup"><span data-stu-id="c1a5d-156">Right-click the label near the indicator, click **Label Properties**,and type the text you want in the **Text** box.</span></span>  
  
18. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1a5d-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1a5d-157">See Also</span></span>  
 [<span data-ttu-id="c1a5d-158">Indicateurs &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c1a5d-158">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
