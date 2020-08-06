---
title: Ajouter une action Développer ou Réduire à un élément (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 49f07ad6-242b-4861-8fc1-91ca78c36d6c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 331c6a14a4a898ffcdf86f274c00e7ad3c801ec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696423"
---
# <a name="add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs"></a><span data-ttu-id="ca3bb-102">Ajouter une action Développer ou Réduire à un élément (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ca3bb-102">Add an Expand or Collapse Action to an Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ca3bb-103">Vous pouvez permettre à un utilisateur de développer ou de réduire interactivement des éléments de rapport, ou dans une table ou une matrice, de développer ou de réduire des lignes et des colonnes associées à un groupe.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-103">You can enable a user to interactively expand or collapse report items, or expand or collapse rows and columns associated with a group for a table or matrix.</span></span> <span data-ttu-id="ca3bb-104">Pour autoriser les utilisateurs à développer ou réduire un élément, définissez les propriétés de visibilité de cet élément.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-104">To allow users to expand or collapse an item, you set the visibility properties for that item.</span></span> <span data-ttu-id="ca3bb-105">La définition de la visibilité s'effectue dans une Visionneuse de rapports HTML et porte parfois le nom d'action d' *exploration* .</span><span class="sxs-lookup"><span data-stu-id="ca3bb-105">Setting visibility works in an HTML report viewer, and is sometimes called a *drilldown* action.</span></span>  
  
 <span data-ttu-id="ca3bb-106">En mode création de rapport, vous spécifiez le nom de la zone de texte où vous souhaitez afficher les icônes de développement et de réduction.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-106">In report design view, you specify the name of the text box where you want to display the expand and collapse toggle icons.</span></span> <span data-ttu-id="ca3bb-107">Dans le rapport rendu, la zone de texte affiche un signe plus (+) ou un signe moins (-) en plus de son contenu.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-107">In the rendered report, the text box displays a plus (+) or minus (-) sign in addition to its contents.</span></span> <span data-ttu-id="ca3bb-108">Lorsque l'utilisateur clique sur la bascule, l'affichage de rapport est actualisé de manière à montrer ou masquer l'élément de rapport, en fonction des paramètres de visibilité actuels des éléments du rapport.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-108">When the user clicks the toggle, the report display is refreshed to show or hide the report item, based on the current visibility settings for items in the report.</span></span>  
  
 <span data-ttu-id="ca3bb-109">En règle générale, l'action de développement et réduction permet d'afficher uniquement les données de synthèse et fournit à l'utilisateur la possibilité de cliquer sur le signe plus afin d'afficher les données de détail.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-109">Typically, the expand and collapse action is used to initially display only summary data and to enable the user to click the plus sign to show detail data.</span></span> <span data-ttu-id="ca3bb-110">Par exemple, vous pouvez à la base masquer une table qui indique les valeurs d'un graphique ou masquer les groupes enfants d'une table avec des groupes de lignes et de colonnes imbriqués, comme dans un rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-110">For example, you can initially hide a table that displays values for a chart, or hide child groups for a table with nested row or column groups, as in a drilldown report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-expand-and-collapse-action-to-a-group"></a><span data-ttu-id="ca3bb-111">Pour ajouter une action Développer/Réduire à un groupe</span><span class="sxs-lookup"><span data-stu-id="ca3bb-111">To add expand and collapse action to a group</span></span>  
  
1.  <span data-ttu-id="ca3bb-112">En mode création de rapport, cliquez sur le tableau ou la matrice pour les sélectionner.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-112">In report design view, click the table or matrix to select it.</span></span> <span data-ttu-id="ca3bb-113">Le volet Regroupement affiche les groupes de lignes et de colonnes.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-113">The Grouping pane displays the row and column groups.</span></span>  
  
     <span data-ttu-id="ca3bb-114">![Volet de regroupement](../media/groupingpane.png "Volet de regroupement")</span><span class="sxs-lookup"><span data-stu-id="ca3bb-114">![Grouping Pane](../media/groupingpane.png "Grouping Pane")</span></span>  
  
     <span data-ttu-id="ca3bb-115">Si le volet de regroupement ne s'affiche pas, cliquez sur le menu **Affichage** , puis cliquez sur **Regroupement**.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-115">If the Grouping pane does not appear, click the **View** menu and then click **Grouping**.</span></span>  
  
2.  <span data-ttu-id="ca3bb-116">Cliquez avec le bouton droit n’importe où dans la barre de titre du volet de regroupement, puis cliquez sur **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-116">Right-click anywhere in the title bar of the Grouping pane, and then click **Advanced**.</span></span> <span data-ttu-id="ca3bb-117">Le volet Regroupement bascule dans un autre mode pour afficher la structure d'affichage sous-jacente des lignes et des colonnes sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-117">The Grouping pane mode toggles to show the underlying display structure for rows and columns on the design surface.</span></span>  
  
     <span data-ttu-id="ca3bb-118">![Volet de regroupement avec menu Mode avancé](../media/groupingpane-advancedmode.png "Volet de regroupement avec menu Mode avancé")</span><span class="sxs-lookup"><span data-stu-id="ca3bb-118">![Grouping Pane with Advanced Mode menu](../media/groupingpane-advancedmode.png "Grouping Pane with Advanced Mode menu")</span></span>  
  
3.  <span data-ttu-id="ca3bb-119">Dans le volet Groupe approprié, cliquez sur le nom du groupe de lignes ou du groupe de colonnes dont vous souhaitez masquer les lignes ou les colonnes qui y sont associées.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-119">In the appropriate group pane, click the name of the row group or column group for which you want to hide the associated rows or columns.</span></span> <span data-ttu-id="ca3bb-120">Le groupe est sélectionné et le volet Propriétés affiche les propriétés **Membre du tableau matriciel** .</span><span class="sxs-lookup"><span data-stu-id="ca3bb-120">The group is selected and the Properties pane shows the **Tablix Member** properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca3bb-121"> Si vous ne voyez pas le volet Propriétés, cliquez sur **Affichage** sur le ruban, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-121">If you do not see the Properties pane, click **View** on the Ribbon and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="ca3bb-122">Dans `Hidden` , choisissez l’une des options suivantes pour définir la visibilité de cet élément de rapport la première fois que vous exécutez un rapport :</span><span class="sxs-lookup"><span data-stu-id="ca3bb-122">In `Hidden`, choose one of the following options to set the visibility of this report item the first time you run a report:</span></span>  
  
    -   <span data-ttu-id="ca3bb-123">Sélectionnez `False` cette option pour afficher l’élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-123">Select `False` to display the report item.</span></span>  
  
    -   <span data-ttu-id="ca3bb-124">Sélectionnez `True` cette option pour masquer l’élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-124">Select `True` to hide the report item.</span></span>  
  
    -   <span data-ttu-id="ca3bb-125">Sélectionnez cette option **\<Expression>** pour ouvrir la boîte de dialogue **expression** et créer une expression qui est évaluée au moment de l’exécution pour déterminer la visibilité.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-125">Select **\<Expression>** to open the **Expression** dialog box to create an expression that is evaluated at run time to determine the visibility.</span></span>  
  
5.  <span data-ttu-id="ca3bb-126">Dans **ToggleItem**, sélectionnez dans la liste déroulante le nom d’une zone de texte à laquelle ajouter l’image bascule.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-126">In **ToggleItem**, from the drop-down box, select the name of a text box to which to add the toggle image.</span></span>  
  
     <span data-ttu-id="ca3bb-127">Dans l'image suivante, le groupe de lignes Couleur est configuré de façon à permettre aux utilisateurs de développer et de réduire les lignes associées.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-127">In the following image, the Color row group is configured enable users to expand and collapse associated rows.</span></span>  
  
     <span data-ttu-id="ca3bb-128">![Configuration du développement d'un groupe de lignes](../media/expandcollapse-confighiddentoggleitemwithnumbers.png "Configuration du développement d'un groupe de lignes")</span><span class="sxs-lookup"><span data-stu-id="ca3bb-128">![Configuring a row group to be expanded](../media/expandcollapse-confighiddentoggleitemwithnumbers.png "Configuring a row group to be expanded")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca3bb-129">La zone de texte avec l'image bascule ne peut pas être le groupe de lignes ou de colonnes dont vous souhaitez masquer les lignes ou les colonnes qui y sont associées.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-129">The text box with the toggle image cannot be the row or column group for which you want to hide the associated rows or columns.</span></span> <span data-ttu-id="ca3bb-130">Elle doit figurer dans le même groupe que l'élément qui est en train d'être masqué ou dans un groupe ancêtre.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-130">It must either be in the same group as the item that is being hidden or in an ancestor group.</span></span> <span data-ttu-id="ca3bb-131">Par exemple, pour afficher ou masquer les lignes associées à un groupe enfant, sélectionnez une zone de texte dans une ligne associée au groupe parent.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-131">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span>  
  
6.  <span data-ttu-id="ca3bb-132">Pour tester la bascule, exécutez le rapport et cliquez sur la zone de texte comportant l'image bascule.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-132">To test the toggle, run the report and click the text box with the toggle image.</span></span> <span data-ttu-id="ca3bb-133">L'affichage du rapport est actualisé de manière à afficher des groupes de lignes et des groupes de colonnes avec leur visibilité basculée.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-133">The report display refreshes to show row groups and column groups with their toggled visibility.</span></span>  
  
     <span data-ttu-id="ca3bb-134">![Exécution du rapport avec un groupe de lignes à développer](../media/expandcollapse-runreport-rowgroup.png "Exécution du rapport avec un groupe de lignes à développer")</span><span class="sxs-lookup"><span data-stu-id="ca3bb-134">![Running report with expandable row group](../media/expandcollapse-runreport-rowgroup.png "Running report with expandable row group")</span></span>  
  
### <a name="to-add-expand-and-collapse-action-to-a-report-item"></a><span data-ttu-id="ca3bb-135">Pour ajouter une action Développer/Réduire à un élément de rapport</span><span class="sxs-lookup"><span data-stu-id="ca3bb-135">To add expand and collapse action to a report item</span></span>  
  
1.  <span data-ttu-id="ca3bb-136">En mode création de rapport, cliquez avec le bouton droit sur l’élément de rapport à afficher ou à masquer, puis cliquez sur *\<report item>* **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-136">In report design view, right-click the report item to show or hide, and then click *\<report item>* **Properties**.</span></span> <span data-ttu-id="ca3bb-137">La *\<report item>* boîte de dialogue **Propriétés** de l’élément de rapport s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-137">The *\<report item>* **Properties** dialog box for the report item opens.</span></span>  
  
2.  <span data-ttu-id="ca3bb-138">Cliquez sur **Visibilité**.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-138">Click **Visibility**.</span></span>  
  
3.  <span data-ttu-id="ca3bb-139">Dans **Lors de la première exécution du rapport**, choisissez l'une des options suivantes pour définir la visibilité de cet élément de rapport la première fois vous exécutez un rapport :</span><span class="sxs-lookup"><span data-stu-id="ca3bb-139">In **When the report is initially run**, choose one of the following options to set the visibility of this report item the first time you run a report:</span></span>  
  
    -   <span data-ttu-id="ca3bb-140">Sélectionnez **Afficher** pour afficher l'élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-140">Select **Show** to display the report item.</span></span>  
  
    -   <span data-ttu-id="ca3bb-141">Sélectionnez **Masquer** pour masquer l'élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-141">Select **Hide** to hide the report item.</span></span>  
  
    -   <span data-ttu-id="ca3bb-142">Sélectionnez **Afficher ou masquer en fonction d'une expression** pour utiliser une expression évaluée au moment de l'exécution pour déterminer la visibilité.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-142">Select **Show or hide based on an expression** to use an expression evaluated at run time to determine the visibility.</span></span> <span data-ttu-id="ca3bb-143">Cliquez sur (**FX**) pour ouvrir la boîte de dialogue **expression** et créer une expression.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-143">Click (**fx**) to open the **Expression** dialog box to create an expression.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="ca3bb-144">Quand vous spécifiez une expression de visibilité, vous définissez la propriété Hidden de l’élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-144">When you specify an expression for visibility, you are setting the Hidden property of the report item.</span></span> <span data-ttu-id="ca3bb-145">L'expression prend la valeur `Boolean``True` pour masquer l'élément, et la valeur `False` pour l'afficher.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-145">The expression evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span>  
  
4.  <span data-ttu-id="ca3bb-146">Dans **L’affichage peut être activé ou désactivé par cet élément de rapport**, tapez ou sélectionnez dans la liste déroulante le nom d’une zone de texte du rapport où afficher une image bascule, par exemple Textbox1.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-146">In **Display can be toggled by this report item**, from the drop-down box, type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span>  
  
     <span data-ttu-id="ca3bb-147">Dans l'image suivante, la table est configurée de manière à permettre aux utilisateurs de la développer et de la réduire.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-147">In the following image, the table is configured to enable users to expand and collapse it.</span></span> <span data-ttu-id="ca3bb-148">L'affichage de la table peut être activé et désactivé depuis la zone de texte Table de Produits.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-148">The display of the table is toggled by the Products Table text box.</span></span>  
  
     <span data-ttu-id="ca3bb-149">![Configurer le développement d'une table rapport](../media/expandcollapse-reporttable.png "Configurer le développement d'une table rapport")</span><span class="sxs-lookup"><span data-stu-id="ca3bb-149">![Configure a report table to be expanded](../media/expandcollapse-reporttable.png "Configure a report table to be expanded")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca3bb-150">La zone de texte que vous choisissez doit figurer dans l'étendue actuelle ou contenante de cet élément de rapport (jusqu'au corps du rapport inclus).</span><span class="sxs-lookup"><span data-stu-id="ca3bb-150">The text box that you choose must be in the current or containing scope for this report item (up to and including the report body).</span></span> <span data-ttu-id="ca3bb-151">Par exemple, pour afficher ou masquer un graphique, sélectionnez une zone de texte qui est dans la même étendue contenante que le graphique, par exemple le corps du rapport ou un rectangle.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-151">For example, to toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span> <span data-ttu-id="ca3bb-152">La zone de texte doit figurer dans la même hiérarchie de conteneurs ou à un niveau plus élevé.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-152">The text box must be in the same container hierarchy or higher.</span></span>  
  
5.  <span data-ttu-id="ca3bb-153">Pour tester la bascule, exécutez le rapport et cliquez sur la zone de texte comportant l'image bascule.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-153">To test the toggle, run the report and click the text box with the toggle image.</span></span> <span data-ttu-id="ca3bb-154">L'affichage du rapport est actualisé de manière à afficher les éléments du rapport avec leur visibilité basculée.</span><span class="sxs-lookup"><span data-stu-id="ca3bb-154">The report display refreshes to show report items with their toggled visibility.</span></span>  
  
     <span data-ttu-id="ca3bb-155">![Exécution du rapport avec une table en cours de développement](../media/expandcollapse-runreport-reporttable.png "Exécution du rapport avec une table en cours de développement")</span><span class="sxs-lookup"><span data-stu-id="ca3bb-155">![Running report with an expanding table](../media/expandcollapse-runreport-reporttable.png "Running report with an expanding table")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca3bb-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ca3bb-156">See Also</span></span>  
 <span data-ttu-id="ca3bb-157">[Action d’exploration &#40;Générateur de rapports et SSRS&#41;](drilldown-action-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ca3bb-157">[Drilldown Action &#40;Report Builder and SSRS&#41;](drilldown-action-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ca3bb-158">Masquer un élément &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ca3bb-158">Hide an Item &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/hide-an-item-report-builder-and-ssrs.md)  
  
  
