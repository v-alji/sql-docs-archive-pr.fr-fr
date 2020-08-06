---
title: Créer un rapport en escalier (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5933c4f0-c713-4ecb-b521-ff46c9c63fff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d845993ac1462cef2d39638101e5c7b9fc314b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603872"
---
# <a name="create-a-stepped-report-report-builder-and-ssrs"></a><span data-ttu-id="89eb7-102">Créer un rapport en escalier (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="89eb7-102">Create a Stepped Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="89eb7-103">Un rapport par palier affiche des lignes de détails ou des groupes enfants mis en retrait sous un groupe parent dans la même colonne, comme le montre l'exemple ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="89eb7-103">A stepped report shows detail rows or child groups indented under a parent group in the same column, as shown in the example below:</span></span>  
  
 <span data-ttu-id="89eb7-104">![Rapport par palier rendu](../media/steppedreportrendered.gif "Rapport par palier rendu")</span><span class="sxs-lookup"><span data-stu-id="89eb7-104">![Rendered stepped report](../media/steppedreportrendered.gif "Rendered stepped report")</span></span>  
  
 <span data-ttu-id="89eb7-105">Les rapports traditionnels sous forme de table placent le groupe parent dans une colonne adjacente dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="89eb7-105">Traditional table reports place the parent group in an adjacent column on the report.</span></span> <span data-ttu-id="89eb7-106">La nouvelle région de données de tableau matriciel vous permet d’ajouter un groupe et des lignes de détails ou des groupes enfants à la même colonne.</span><span class="sxs-lookup"><span data-stu-id="89eb7-106">The new tablix data region enables you to add a group and detail rows or child groups to the same column.</span></span> <span data-ttu-id="89eb7-107">Pour différencier les lignes de groupe des lignes de détails ou de groupes enfants, vous pouvez appliquer une mise en forme telle qu'une couleur de police ou vous pouvez mettre en retrait les lignes de détails.</span><span class="sxs-lookup"><span data-stu-id="89eb7-107">To differentiate the group rows from the detail or child group rows, you can apply formatting such as font color, or you can indent the detail rows.</span></span>  
  
 <span data-ttu-id="89eb7-108">Les procédures de cette rubrique vous expliquent comment créer manuellement un rapport en escalier, mais vous pouvez également utiliser l'Assistant Nouveau tableau ou nouvelle matrice.</span><span class="sxs-lookup"><span data-stu-id="89eb7-108">The procedures in this topic show you how to manually create a stepped report, but you can also use the New Table and Matrix Wizard.</span></span> <span data-ttu-id="89eb7-109">Il fournit la mise en page pour les rapports en escalier, ce qui en facilite la création.</span><span class="sxs-lookup"><span data-stu-id="89eb7-109">It provides the layout for stepped reports, making it easy to create them.</span></span> <span data-ttu-id="89eb7-110">Après avoir exécuté l'Assistant, vous pouvez améliorer le rapport.</span><span class="sxs-lookup"><span data-stu-id="89eb7-110">After you complete the wizard, you can further enhance the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89eb7-111">L'Assistant est disponible uniquement dans le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="89eb7-111">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-stepped-report"></a><span data-ttu-id="89eb7-112">Pour créer un rapport en escalier</span><span class="sxs-lookup"><span data-stu-id="89eb7-112">To create a stepped report</span></span>  
  
1.  <span data-ttu-id="89eb7-113">Créez un rapport de table.</span><span class="sxs-lookup"><span data-stu-id="89eb7-113">Create a table report.</span></span> <span data-ttu-id="89eb7-114">Par exemple, insérez une région de données de tableau matriciel et ajoutez des champs à la ligne de données.</span><span class="sxs-lookup"><span data-stu-id="89eb7-114">For example, insert a tablix data region and add fields to the Data row.</span></span>  
  
2.  <span data-ttu-id="89eb7-115">Ajoutez un groupe parent à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="89eb7-115">Add a parent group to your report.</span></span>  
  
    1.  <span data-ttu-id="89eb7-116">Cliquez n'importe où dans la table pour la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="89eb7-116">Click anywhere in the table to select it.</span></span> <span data-ttu-id="89eb7-117">Le volet de regroupement affiche le groupe de détails dans le volet Groupes de lignes.</span><span class="sxs-lookup"><span data-stu-id="89eb7-117">The Grouping pane displays the Details group in the Row Groups pane.</span></span>  
  
    2.  <span data-ttu-id="89eb7-118">Dans le volet de regroupement, cliquez avec le bouton droit sur le groupe de détails, pointez sur **Ajouter un groupe**, puis cliquez sur **Groupe parent**.</span><span class="sxs-lookup"><span data-stu-id="89eb7-118">In the Grouping Pane, right-click the Details Group, point to **Add Group**, and then click **Parent Group**.</span></span>  
  
    3.  <span data-ttu-id="89eb7-119">Dans la boîte de dialogue **Groupe de tableau matriciel** , indiquez un nom pour le groupe et tapez ou sélectionnez une expression de groupe dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="89eb7-119">In the **Tablix Group** dialog box, provide a name for the group and type or select a group expression from the drop-down list.</span></span> <span data-ttu-id="89eb7-120">La liste déroulante affiche les expressions de champ simples qui sont disponibles dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="89eb7-120">The drop-down list displays the simple field expressions that are available in the Report Data pane.</span></span> <span data-ttu-id="89eb7-121">Par exemple, [PostalCode] est une expression de champ simple pour le champ PostalCode d'un dataset.</span><span class="sxs-lookup"><span data-stu-id="89eb7-121">For example, [PostalCode] is a simple field expression for the PostalCode field in a dataset.</span></span>  
  
    4.  <span data-ttu-id="89eb7-122">Sélectionnez **Ajouter l’en-tête du groupe**.</span><span class="sxs-lookup"><span data-stu-id="89eb7-122">Select **Add group header**.</span></span> <span data-ttu-id="89eb7-123">Cette option ajoute une ligne statique au-dessus du groupe pour l'étiquette et les totaux du groupe.</span><span class="sxs-lookup"><span data-stu-id="89eb7-123">This option adds a static row above the group for the group label and group totals.</span></span> <span data-ttu-id="89eb7-124">De la même manière, vous pouvez sélectionner **Ajouter le pied de page du groupe** pour ajouter une ligne statique au-dessous du groupe.</span><span class="sxs-lookup"><span data-stu-id="89eb7-124">Likewise, you can select **Add group footer** to add a static row below the group.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="89eb7-125">Vous disposez maintenant d'un rapport tabulaire de base.</span><span class="sxs-lookup"><span data-stu-id="89eb7-125">You now have a basic tabular report.</span></span> <span data-ttu-id="89eb7-126">Lorsqu'il est rendu, une colonne s'affiche avec la valeur d'instance de groupe, et une ou plusieurs colonnes avec les données de détail groupées.</span><span class="sxs-lookup"><span data-stu-id="89eb7-126">When it is rendered, you see one column with the group instance value, and one or more columns with grouped detail data.</span></span> <span data-ttu-id="89eb7-127">L'illustration suivante montre l'apparence de la région de données sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="89eb7-127">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="89eb7-128">![Région de données de table avec groupe](../media/tabledataregionwithgroup.gif "Région de données de table avec groupe")</span><span class="sxs-lookup"><span data-stu-id="89eb7-128">![Table data region with group](../media/tabledataregionwithgroup.gif "Table data region with group")</span></span>  
  
     <span data-ttu-id="89eb7-129">L'illustration suivante montre l'apparence de la région de données rendue lorsque vous affichez le rapport.</span><span class="sxs-lookup"><span data-stu-id="89eb7-129">The following figure shows how the rendered data region might look when you view the report.</span></span>  
  
     <span data-ttu-id="89eb7-130">![Rapport groupé rendu](../media/tablereportrendered.gif "Rapport groupé rendu")</span><span class="sxs-lookup"><span data-stu-id="89eb7-130">![Rendered grouped report](../media/tablereportrendered.gif "Rendered grouped report")</span></span>  
  
3.  <span data-ttu-id="89eb7-131">Pour un rapport par palier, vous n'avez pas besoin de la première colonne qui affiche l'instance de groupe.</span><span class="sxs-lookup"><span data-stu-id="89eb7-131">For a stepped report, you do not need the first column that shows the group instance.</span></span> <span data-ttu-id="89eb7-132">À la place, copiez la valeur de la cellule d'en-tête de groupe, supprimez la colonne de groupe et collez la valeur dans la première zone de texte de la ligne d'en-tête de groupe.</span><span class="sxs-lookup"><span data-stu-id="89eb7-132">Instead, copy the value in the group header cell, delete the group column, and paste in the first text box in the group header row.</span></span> <span data-ttu-id="89eb7-133">Pour supprimer la colonne de groupe, cliquez avec le bouton droit sur la colonne de groupe ou sur la cellule, puis cliquez sur **Supprimer les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="89eb7-133">To remove the group column, right-click the group column or cell, and click **Delete Columns**.</span></span> <span data-ttu-id="89eb7-134">L'illustration suivante montre l'apparence de la région de données sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="89eb7-134">The following figure shows what the data region might look like on the design surface.</span></span>  
  
     <span data-ttu-id="89eb7-135">![Région de données avec ligne d'en-tête de groupe](../media/tabledataregiongroupheader.gif "Région de données avec ligne d'en-tête de groupe")</span><span class="sxs-lookup"><span data-stu-id="89eb7-135">![Data region with group header row](../media/tabledataregiongroupheader.gif "Data region with group header row")</span></span>  
  
4.  <span data-ttu-id="89eb7-136">Pour mettre en retrait les lignes de détails sous la ligne d'en-tête de groupe dans la même colonne, modifiez la marge intérieure de la cellule de données de détail.</span><span class="sxs-lookup"><span data-stu-id="89eb7-136">To indent the detail rows under the group header row in the same column, change the padding of the detail data cell.</span></span>  
  
    1.  <span data-ttu-id="89eb7-137">Sélectionnez la cellule avec le champ de détail que vous souhaitez mettre en retrait.</span><span class="sxs-lookup"><span data-stu-id="89eb7-137">Select the cell with the detail field that you want to indent.</span></span> <span data-ttu-id="89eb7-138">Les propriétés de la zone de texte de cette cellule s'affichent dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="89eb7-138">The text box properties for that cell appear in the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="89eb7-139">Dans le volet Propriétés, sous **Alignement**, développez les propriétés pour **Marge intérieure**.</span><span class="sxs-lookup"><span data-stu-id="89eb7-139">In the Properties pane, under **Alignment**, expand the properties for **Padding**.</span></span>  
  
    3.  <span data-ttu-id="89eb7-140">Pour **gauche**, tapez une nouvelle valeur de marge intérieure, telle que `.5in` .</span><span class="sxs-lookup"><span data-stu-id="89eb7-140">For **Left**, type a new padding value, such as `.5in`.</span></span> <span data-ttu-id="89eb7-141">La marge intérieure met en retrait le texte de la cellule selon la valeur que vous avez spécifiée.</span><span class="sxs-lookup"><span data-stu-id="89eb7-141">Padding indents the text in the cell by the value you specify.</span></span> <span data-ttu-id="89eb7-142">La valeur par défaut de la marge intérieure est égale à 2 points.</span><span class="sxs-lookup"><span data-stu-id="89eb7-142">The default padding is 2 points.</span></span> <span data-ttu-id="89eb7-143">Les valeurs valides pour les propriétés Padding sont zéro ou une valeur positive, suivis d'un indicateur de taille.</span><span class="sxs-lookup"><span data-stu-id="89eb7-143">Valid values for the Padding properties are zero or a positive number, followed by a size designator.</span></span>  
  
         <span data-ttu-id="89eb7-144">Les indicateurs de taille sont :</span><span class="sxs-lookup"><span data-stu-id="89eb7-144">Size designators are:</span></span>  
  
        |||  
        |-|-|  
        |`in`|<span data-ttu-id="89eb7-145">Pouces (1 pouce = 2,54 centimètres)</span><span class="sxs-lookup"><span data-stu-id="89eb7-145">Inches (1 inch = 2.54 centimeters)</span></span>|  
        |`cm`|<span data-ttu-id="89eb7-146">Centimètres</span><span class="sxs-lookup"><span data-stu-id="89eb7-146">Centimeters</span></span>|  
        |`mm`|<span data-ttu-id="89eb7-147">Millimètres</span><span class="sxs-lookup"><span data-stu-id="89eb7-147">Millimeters</span></span>|  
        |`pt`|<span data-ttu-id="89eb7-148">Points (1 point = 1/72 pouce)</span><span class="sxs-lookup"><span data-stu-id="89eb7-148">Points (1 point = 1/72 inch)</span></span>|  
        |`pc`|<span data-ttu-id="89eb7-149">Picas (1 pica = 12 points)</span><span class="sxs-lookup"><span data-stu-id="89eb7-149">Picas (1 pica = 12 points)</span></span>|  
  
     <span data-ttu-id="89eb7-150">Votre région de données doit ressembler à l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="89eb7-150">Your data region will look similar to the following example.</span></span>  
  
     <span data-ttu-id="89eb7-151">![Région de données pour un rapport par palier](../media/steppedreportdataregion.gif "Région de données pour un rapport par palier")</span><span class="sxs-lookup"><span data-stu-id="89eb7-151">![Data region for stepped report](../media/steppedreportdataregion.gif "Data region for stepped report")</span></span>  
  
     <span data-ttu-id="89eb7-152">**Région de données pour une mise en page de rapport en escalier**</span><span class="sxs-lookup"><span data-stu-id="89eb7-152">**Data Region for Stepped Report Layout**</span></span>  
  
     <span data-ttu-id="89eb7-153">Sous l’onglet **Accueil** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="89eb7-153">On the **Home** tab Click **Run**.</span></span> <span data-ttu-id="89eb7-154">Le rapport affiche le groupe avec des niveaux en retrait pour les valeurs des groupes enfants.</span><span class="sxs-lookup"><span data-stu-id="89eb7-154">The report displays the group with indented levels for the child group values.</span></span>  
  
### <a name="to-create-a-stepped-report-with-multiple-groups"></a><span data-ttu-id="89eb7-155">Pour créer un rapport par palier avec plusieurs groupes</span><span class="sxs-lookup"><span data-stu-id="89eb7-155">To create a stepped report with multiple groups</span></span>  
  
1.  <span data-ttu-id="89eb7-156">Créez un rapport selon les indications de la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="89eb7-156">Create a report as described in the previous procedure.</span></span>  
  
2.  <span data-ttu-id="89eb7-157">Ajoutez des groupes supplémentaires à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="89eb7-157">Add additional groups to your report.</span></span>  
  
    1.  <span data-ttu-id="89eb7-158">Dans le volet Groupes de lignes, cliquez avec le bouton droit sur le groupe, cliquez sur **Ajouter un groupe**, puis choisissez le type du groupe à ajouter.</span><span class="sxs-lookup"><span data-stu-id="89eb7-158">In the Row Groups pane, right-click the group, click **Add Group**, and then choose the type of group you want to add.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="89eb7-159">Il existe plusieurs façons d'ajouter des groupes à une région de données.</span><span class="sxs-lookup"><span data-stu-id="89eb7-159">There are several ways to add groups to a data region.</span></span> <span data-ttu-id="89eb7-160">Pour plus d’informations, consultez [Ajouter ou supprimer un groupe dans une région de données &#40;générateur de rapports et des&#41;SSRS ](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="89eb7-160">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
    2.  <span data-ttu-id="89eb7-161">Dans la boîte de dialogue **Groupe de tableaux matriciels** , tapez un nom.</span><span class="sxs-lookup"><span data-stu-id="89eb7-161">In the **Tablix Group** dialog box, type a name.</span></span>  
  
    3.  <span data-ttu-id="89eb7-162">Dans **Expression Groupe**, tapez une expression ou sélectionnez le champ de dataset sur lequel effectuer le regroupement.</span><span class="sxs-lookup"><span data-stu-id="89eb7-162">In **Group expression**, type an expression or select a dataset field to group on.</span></span> <span data-ttu-id="89eb7-163">Pour créer une expression, cliquez sur le bouton d’expression (**fx**) pour ouvrir la boîte de dialogue **Expression** .</span><span class="sxs-lookup"><span data-stu-id="89eb7-163">To create an expression, click the expression (**fx**) button to open the **Expression** dialog box.</span></span>  
  
    4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
3.  <span data-ttu-id="89eb7-164">Modifiez la marge intérieure de la cellule qui affiche les données du groupe.</span><span class="sxs-lookup"><span data-stu-id="89eb7-164">Change the padding for the cell that displays the group data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89eb7-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89eb7-165">See Also</span></span>  
 <span data-ttu-id="89eb7-166">[En-têtes et pieds de page &#40;Générateur de rapports et SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="89eb7-166">[Page Headers and Footers &#40;Report Builder and SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="89eb7-167">[Mise en forme des éléments de rapport &#40;Générateur de rapports et SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="89eb7-167">[Formatting Report Items &#40;Report Builder and SSRS&#41;](formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="89eb7-168">[Région de données de tableau matriciel &#40;Générateur de rapports et SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="89eb7-168">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="89eb7-169">[Tables &#40;Générateur de rapports et SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="89eb7-169">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="89eb7-170">[Matrices &#40;Générateur de rapports et SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="89eb7-170">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="89eb7-171">[Répertorie &#40;Générateur de rapports et SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="89eb7-171">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="89eb7-172">Tables, matrices et listes &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="89eb7-172">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
