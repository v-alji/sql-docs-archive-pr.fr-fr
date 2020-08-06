---
title: Ajouter un signet à un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f130562e-5673-40e3-8e01-de7227a21d41
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fae543dd1b071ff38853637a3da57ffd2410c3a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707160"
---
# <a name="add-a-bookmark-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="ef2da-102">Ajouter un signet à un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ef2da-102">Add a Bookmark to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ef2da-103">Ajoutez des signets et des liens de signet à un rapport lorsque vous souhaitez fournir une table des matières personnalisée ou des liens de navigation interne personnalisés dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="ef2da-103">Add bookmarks and bookmark links to a report when you want to provide a customized table of contents or to provide customized internal navigation links in the report.</span></span> <span data-ttu-id="ef2da-104">En général, vous ajoutez des signets aux emplacements du rapport où vous souhaitez amener les utilisateurs, comme les tables ou graphiques, ou les valeurs de groupe uniques qui figurent dans une table ou une matrice.</span><span class="sxs-lookup"><span data-stu-id="ef2da-104">Typically, you add bookmarks to locations in the report to which you want to direct users, such as to each table or chart or to the unique group values displayed in a table or matrix.</span></span> <span data-ttu-id="ef2da-105">Vous pouvez créer vos propres chaînes à utiliser en tant que signets, ou, pour les groupes, vous pouvez définir le signet sur l'expression de groupe.</span><span class="sxs-lookup"><span data-stu-id="ef2da-105">You can create your own strings to use as bookmarks, or, for groups, you can set the bookmark to the group expression.</span></span>  
  
 <span data-ttu-id="ef2da-106">Une fois que vous avez créé des signets, vous pouvez ajouter des éléments de rapport sur lesquels l'utilisateur peut cliquer pour atteindre chaque signet.</span><span class="sxs-lookup"><span data-stu-id="ef2da-106">After you create bookmarks, you can add report items that the user can click to go to each bookmark.</span></span> <span data-ttu-id="ef2da-107">Ces éléments sont souvent des zones de texte ou des images.</span><span class="sxs-lookup"><span data-stu-id="ef2da-107">These items are typically text boxes or images.</span></span>  
  
 <span data-ttu-id="ef2da-108">Par exemple, si votre rapport affiche une table dans laquelle un regroupement par couleur a été effectué, vous pouvez ajouter à l'en-tête de groupe un signet basé sur l'expression de groupe.</span><span class="sxs-lookup"><span data-stu-id="ef2da-108">For example, if your report displays a table grouped by color, you would add a bookmark based on the group expression to the group header.</span></span> <span data-ttu-id="ef2da-109">Vous pouvez ensuite ajouter au début du rapport une table avec une seule zone de texte qui affiche les couleurs et définir le lien de signet vers cette zone de texte.</span><span class="sxs-lookup"><span data-stu-id="ef2da-109">Then you would add a table with a single text box at the beginning of the report that displayed the color values, and set the bookmark link on that text box.</span></span> <span data-ttu-id="ef2da-110">Lorsque vous cliquez sur la couleur, le rapport accède à la page qui affiche la ligne d'en-tête de groupe correspondant à cette couleur.</span><span class="sxs-lookup"><span data-stu-id="ef2da-110">When you click the color, the report jumps to the page that displays the group header row for that color.</span></span>  
  
 <span data-ttu-id="ef2da-111">Vous pouvez ajouter un signet à tout élément de rapport et ajouter un lien de signet à tout élément assorti d'une propriété **Action** , par exemple, une zone de texte, une image ou une série calculée dans un graphique.</span><span class="sxs-lookup"><span data-stu-id="ef2da-111">You can add a bookmark to any report item and add a bookmark link to any item that has an **Action** property, for example, a text box, an image, or a calculated series in a chart.</span></span> <span data-ttu-id="ef2da-112">Pour plus d’informations, consultez [Boîte de dialogue Propriétés relatives aux actions &#40;Générateur de rapports et SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ef2da-112">For more information, see the [Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-bookmark"></a><span data-ttu-id="ef2da-113">Pour ajouter un signet</span><span class="sxs-lookup"><span data-stu-id="ef2da-113">To add a bookmark</span></span>  
  
1.  <span data-ttu-id="ef2da-114">En mode création de rapport, sélectionnez la zone de texte, l'image, le graphique ou un autre élément de rapport auquel ajouter un signet.</span><span class="sxs-lookup"><span data-stu-id="ef2da-114">In report design view, select the text box, image, chart, or other report item to which you want to add a bookmark.</span></span> <span data-ttu-id="ef2da-115">Les propriétés de l'élément sélectionné s'affichent dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="ef2da-115">The properties for the selected item appear in the Properties pane.</span></span>  
  
2.  <span data-ttu-id="ef2da-116">Dans la zone de texte située en regard de **Signet**, tapez une chaîne qui constituera l'étiquette de ce signet.</span><span class="sxs-lookup"><span data-stu-id="ef2da-116">In the text box next to **Bookmark**, type a string that is the label for this bookmark.</span></span> <span data-ttu-id="ef2da-117">Par exemple, vous pouvez taper **PhotoVélo** comme signet pour une image de votre rapport.</span><span class="sxs-lookup"><span data-stu-id="ef2da-117">For example, you could type **BikePhoto** as the bookmark for an image in your report.</span></span> <span data-ttu-id="ef2da-118">Vous pouvez aussi cliquer sur le bouton Expression (**fx**) pour ouvrir la boîte de dialogue **Expression** et spécifier une expression qui donne une étiquette.</span><span class="sxs-lookup"><span data-stu-id="ef2da-118">Alternatively, click the Expression (**fx**) button to open the **Expression** dialog box to specify an expression that evaluates to a label.</span></span> <span data-ttu-id="ef2da-119">Pour un groupe, l'expression que vous tapez doit être l'expression de groupe.</span><span class="sxs-lookup"><span data-stu-id="ef2da-119">For a group, the expression you type should be the group expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ef2da-120">Le signet peut être une chaîne quelconque, mais il doit être unique dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="ef2da-120">The bookmark can be any string, but it must be unique in the report.</span></span> <span data-ttu-id="ef2da-121">S'il n'est pas unique, un lien vers celui-ci utilisera le premier signet correspondant.</span><span class="sxs-lookup"><span data-stu-id="ef2da-121">If the bookmark is not unique, a link to the bookmark finds the first matching bookmark.</span></span>  
  
### <a name="to-add-a-bookmark-link"></a><span data-ttu-id="ef2da-122">Pour ajouter un lien de signet</span><span class="sxs-lookup"><span data-stu-id="ef2da-122">To add a bookmark link</span></span>  
  
1.  <span data-ttu-id="ef2da-123">En mode Conception, cliquez avec le bouton droit sur la zone de texte, l’image ou le graphique auquel vous voulez ajouter un lien, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ef2da-123">In Design view, right-click the text box, image, chart, to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ef2da-124">Dans la boîte de dialogue **Propriétés** de cet élément de rapport, cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="ef2da-124">In The **Properties** dialog box for that report item, click **Action**.</span></span>  
  
3.  <span data-ttu-id="ef2da-125">Sélectionnez **Atteindre le signet**.</span><span class="sxs-lookup"><span data-stu-id="ef2da-125">Select **Go to bookmark**.</span></span> <span data-ttu-id="ef2da-126">Une section supplémentaire apparaît dans la boîte de dialogue pour cette option.</span><span class="sxs-lookup"><span data-stu-id="ef2da-126">An additional section appears in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="ef2da-127">Dans la zone **Sélectionnez un signet** , tapez ou sélectionnez un signet ou une expression qui est évaluée en signet.</span><span class="sxs-lookup"><span data-stu-id="ef2da-127">In the **Select bookmark** box, type or select a bookmark or an expression that evaluates to a bookmark.</span></span> <span data-ttu-id="ef2da-128">À l'aide de l'exemple précédent, tapez **PhotoVélo** pour créer un lien vers l'image dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="ef2da-128">Using the previous example, type **BikePhoto** to create a link to the image in your report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="ef2da-129">(Facultatif) Le texte n'est pas mis en forme automatiquement comme un lien.</span><span class="sxs-lookup"><span data-stu-id="ef2da-129">(Optional) The text is not automatically formatted like a link.</span></span> <span data-ttu-id="ef2da-130">Pour le texte, il est utile de modifier la couleur et l'effet du texte pour indiquer qu'il s'agit d'un lien.</span><span class="sxs-lookup"><span data-stu-id="ef2da-130">For text, it is helpful to change the color and effect of the text to indicate that the text is a link.</span></span> <span data-ttu-id="ef2da-131">Par exemple, changez la couleur en bleu et l'effet en soulignement dans la section **Police** sous l'onglet Accueil du ruban.</span><span class="sxs-lookup"><span data-stu-id="ef2da-131">For example, change the color to blue and the effect to underline in the **Font** section in the Home tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="ef2da-132">Pour tester le lien, cliquez sur **Exécuter** afin d'afficher l'aperçu du rapport, puis cliquez sur l'élément de rapport sur lequel vous avez défini ce lien.</span><span class="sxs-lookup"><span data-stu-id="ef2da-132">To test the link, click **Run** to preview the report, and then click the report item that you set this link on..</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2da-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef2da-133">See Also</span></span>  
 <span data-ttu-id="ef2da-134">[Tri interactif, Explorateurs de documents et liens &#40;Générateur de rapports et SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ef2da-134">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ef2da-135">[Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ef2da-135">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ef2da-136">Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ef2da-136">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
