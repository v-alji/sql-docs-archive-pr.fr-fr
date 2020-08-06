---
title: 'Leçon 4 : ajout d’une table au rapport (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ddf2914-bcdd-427d-8cba-0ccb8342f819
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52694168bd60b8e3807db6204f33a89815573093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601967"
---
# <a name="lesson-4-adding-a-table-to-the-report-reporting-services"></a><span data-ttu-id="bc7f6-102">Leçon 4 : Ajout d'une table au rapport (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="bc7f6-102">Lesson 4: Adding a Table to the Report (Reporting Services)</span></span>
  <span data-ttu-id="bc7f6-103">Une fois le dataset défini, vous pouvez commencer à concevoir le rapport.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-103">After the dataset is defined, you can start designing the report.</span></span> <span data-ttu-id="bc7f6-104">Pour créer une mise en page de rapport, faites glisser les régions de données, les zones de texte, les images et autres éléments que vous souhaitez inclure dans un rapport vers l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-104">You create a report layout by dragging and dropping data regions, text boxes, images, and other items that you want to include in your report to the design surface.</span></span>  
  
 <span data-ttu-id="bc7f6-105">Les éléments qui contiennent des lignes de données répétées de datasets sous-jacents sont appelés *régions de données*.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-105">Items that contain repeated rows of data from underlying datasets are called *data regions*.</span></span> <span data-ttu-id="bc7f6-106">Un rapport de base possède une seule région de données, mais vous pouvez en ajouter davantage (pour ajouter un graphique à un rapport tabulaire, par exemple).</span><span class="sxs-lookup"><span data-stu-id="bc7f6-106">A basic report will have only one data region, but you can add more, for example, if you want to add a chart to your tabular report.</span></span> <span data-ttu-id="bc7f6-107">Une fois que vous avez ajouté une région de données, vous pouvez y ajouter des champs.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-107">After you add a data region, you can add fields to the data region.</span></span>  
  
### <a name="to-add-a-table-data-region-and-fields-to-a-report-layout"></a><span data-ttu-id="bc7f6-108">Pour ajouter une région de données de table et des champs à une mise en page de rapport</span><span class="sxs-lookup"><span data-stu-id="bc7f6-108">To add a Table data region and fields to a report layout</span></span>  
  
1.  <span data-ttu-id="bc7f6-109">Dans la **Boîte à outils**, cliquez sur **Table**, puis sur l’aire de conception et faites glisser la souris.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-109">In the **Toolbox**, click **Table**, and then click on the design surface and drag the mouse.</span></span> <span data-ttu-id="bc7f6-110">Le Concepteur de rapports trace une région de donnée de table composée de trois colonnes au centre de l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-110">Report Designer draws a table data region with three columns in the center of the design surface.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc7f6-111">La **Boîte à outils** peut s’afficher sous la forme d’un onglet situé à gauche du volet **Données du rapport** .</span><span class="sxs-lookup"><span data-stu-id="bc7f6-111">The **Toolbox** may appear as a tab on the left side of the **Report Data** pane.</span></span> <span data-ttu-id="bc7f6-112">Pour ouvrir la **boîte à outils**, déplacez le pointeur sur l’onglet **boîte à outils** . Si la **boîte à outils** n’est pas visible, dans le menu **affichage** , cliquez sur **boîte à outils**.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-112">To open the **Toolbox**, move the pointer over the **Toolbox** tab. If the **Toolbox** is not visible, from the **View** menu, click **Toolbox**.</span></span>  
  
2.  <span data-ttu-id="bc7f6-113">Dans le volet **données du rapport** , développez le jeu de données **AdventureWorksDataSet** pour afficher les champs.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-113">In the **Report Data** pane, expand the **AdventureWorksDataset** dataset to display the fields.</span></span>  
  
3.  <span data-ttu-id="bc7f6-114">Faites glisser le champ Date du volet **Données du rapport** vers la première colonne de la table.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-114">Drag the Date field from the **Report Data** pane to the first column in the table.</span></span>  
  
     <span data-ttu-id="bc7f6-115">Lorsque vous déposez ce champ dans la première colonne, deux événements se produisent.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-115">When you drop the field into the first column, two things happen.</span></span> <span data-ttu-id="bc7f6-116">En premier lieu, la cellule de données affiche le nom du champ, appelé *expression de champ*, entre crochets : `[Date]`.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-116">First, the data cell will display the field name, known as the *field expression*, in brackets: `[Date]`.</span></span> <span data-ttu-id="bc7f6-117">En second lieu, une valeur d'en-tête de colonne est automatiquement ajoutée à la ligne d'en-tête, immédiatement au-dessus de l'expression de champ.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-117">Second, a column header value is automatically added to Header row, just above the field expression.</span></span> <span data-ttu-id="bc7f6-118">Par défaut, la colonne porte le nom du champ.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-118">By default, the column is the name of the field.</span></span> <span data-ttu-id="bc7f6-119">Vous pouvez sélectionner le texte de la ligne d'en-tête et taper un nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-119">You can select the Header row text and type a new name.</span></span>  
  
4.  <span data-ttu-id="bc7f6-120">Faites glisser le champ Order du volet **Données du rapport** vers la deuxième colonne de la table.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-120">Drag the Order field from the **Report Data** pane to the second column in the table.</span></span>  
  
5.  <span data-ttu-id="bc7f6-121">Faites glisser le champ Product du volet **Données du rapport** vers la troisième colonne de la table.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-121">Drag the Product field from the **Report Data** pane to the third column in the table.</span></span>  
  
6.  <span data-ttu-id="bc7f6-122">Faites glisser le champ Qty vers le bord droit de la troisième colonne jusqu'à ce que vous obteniez un curseur vertical et que le pointeur de la souris prennent la forme d'un signe plus [+].</span><span class="sxs-lookup"><span data-stu-id="bc7f6-122">Drag the Qty field to the right edge of the third column until you get a vertical cursor and the mouse pointer has a plus sign [+].</span></span> <span data-ttu-id="bc7f6-123">Lorsque vous relâchez le bouton de la souris, une quatrième colonne est créée pour `[Qty]`.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-123">When you release the mouse button, a fourth column is created for `[Qty]`.</span></span>  
  
7.  <span data-ttu-id="bc7f6-124">Ajoutez le champ LineTotal de la même façon, en créant une cinquième colonne.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-124">Add the LineTotal field in the same way, creating a fifth column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bc7f6-125">L'en-tête de colonne est Line Total.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-125">The column header is Line Total.</span></span> <span data-ttu-id="bc7f6-126">Le Concepteur de rapports crée automatiquement un nom convivial pour la colonne en fractionnant LineTotal en deux mots.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-126">Report Designer automatically creates a friendly name for the column by splitting LineTotal into two words.</span></span>  
  
     <span data-ttu-id="bc7f6-127">Le diagramme suivant représente une région de données de table qui a été remplie avec les champs suivants : Date, Order, Product, Qty et Line Total.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-127">The following diagram shows a table data region that has been populated with these fields: Date, Order, Product, Qty, and Line Total.</span></span>  
  
     <span data-ttu-id="bc7f6-128">![Conception, table avec ligne d'en-tête et ligne de détails](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Conception, table avec ligne d'en-tête et ligne de détails")</span><span class="sxs-lookup"><span data-stu-id="bc7f6-128">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
## <a name="preview-your-report"></a><span data-ttu-id="bc7f6-129">Affichage d'un aperçu d'un rapport</span><span class="sxs-lookup"><span data-stu-id="bc7f6-129">Preview Your Report</span></span>  
 <span data-ttu-id="bc7f6-130">L'affichage d'un aperçu d'un rapport vous permet de visualiser le rapport rendu sans avoir à le publier au préalable sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-130">Previewing a report enables you to view the rendered report without having to first publish it to a report server.</span></span> <span data-ttu-id="bc7f6-131">Vous souhaiterez probablement afficher fréquemment des aperçus du rapport pendant sa conception.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-131">You will probably want to preview your report frequently during design time.</span></span> <span data-ttu-id="bc7f6-132">Afficher un aperçu du rapport entraîne également l'exécution de la validation au niveau de la conception et des connexions de données pour vous permettre de corriger les erreurs et les problèmes avant la publication sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-132">Previewing the report will also run validation on the design and data connections so you can correct errors and issues before publishing the report to a report server.</span></span>  
  
#### <a name="to-preview-a-report"></a><span data-ttu-id="bc7f6-133">Pour afficher l'aperçu d'un rapport</span><span class="sxs-lookup"><span data-stu-id="bc7f6-133">To preview a report</span></span>  
  
-   <span data-ttu-id="bc7f6-134">Cliquez sur l’onglet **Aperçu** . concepteur de rapports exécute le rapport et l’affiche en mode aperçu.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-134">Click the **Preview** tab. Report Designer runs the report and displays it in Preview view.</span></span>  
  
     <span data-ttu-id="bc7f6-135">Le diagramme suivant représente une partie du rapport en mode Aperçu.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-135">The following diagram shows part of the report in Preview view.</span></span>  
  
     <span data-ttu-id="bc7f6-136">![Aperçu, lignes de détails de table avec 5 colonnes](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Aperçu, lignes de détails de table avec 5 colonnes")</span><span class="sxs-lookup"><span data-stu-id="bc7f6-136">![Preview, Detail rows of table with 5 columns](../../2014/tutorials/media/rs-basictabledetailspreview.gif "Preview, Detail rows of table with 5 columns")</span></span>  
  
     <span data-ttu-id="bc7f6-137">Remarquez que la devise (dans la colonne Line Total) possède six décimales après la virgule et que la date comporte un horodatage.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-137">Notice that the currency (in the Line Total column) has six places after the decimal, and the date has includes a time stamp.</span></span> <span data-ttu-id="bc7f6-138">Vous allez reprendre cette mise en forme dans la leçon suivante.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-138">You're going to fix that formatting in the next lesson.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc7f6-139">Dans le menu **Fichier** , cliquez sur **Enregistrer tout** pour enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-139">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bc7f6-140">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="bc7f6-140">Next Steps</span></span>  
 <span data-ttu-id="bc7f6-141">Vous avez ajouté avec succès une région de données de table à votre rapport, ajouté des champs à la région de données et affiché un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-141">You have successfully added a Table data region to your report, added fields to the data region, and previewed your report.</span></span> <span data-ttu-id="bc7f6-142">Vous allez ensuite mettre en forme des en-têtes de colonnes et des valeurs de devise et de date.</span><span class="sxs-lookup"><span data-stu-id="bc7f6-142">Next, you will format column headers and date and currency values.</span></span> <span data-ttu-id="bc7f6-143">Consultez [Leçon 5 : mise en forme d’un rapport &#40;Reporting Services&#41;](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="bc7f6-143">See [Lesson 5: Formatting a Report &#40;Reporting Services&#41;](../reporting-services/lesson-5-formatting-a-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc7f6-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc7f6-144">See Also</span></span>  
 <span data-ttu-id="bc7f6-145">[Tables &#40;Générateur de rapports et SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bc7f6-145">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bc7f6-146">Collection de champs de dataset &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bc7f6-146">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](report-data/dataset-fields-collection-report-builder-and-ssrs.md)  
  
  
