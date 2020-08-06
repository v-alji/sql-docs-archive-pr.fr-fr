---
title: Créer une carte de documents (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c200a97b-67f2-499f-8374-3ed1ebe3f33c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a9dad0f8e6ee1d9b9ada44fda0eec5908f27cfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603890"
---
# <a name="create-a-document-map-report-builder-and-ssrs"></a><span data-ttu-id="ec309-102">Créer un explorateur de documents (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="ec309-102">Create a Document Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ec309-103">Un explorateur de documents fournit un ensemble de liens de navigation permettant d'accéder aux éléments de rapport dans un rapport rendu.</span><span class="sxs-lookup"><span data-stu-id="ec309-103">A document map provides a set of navigational links to report items in a rendered report.</span></span> <span data-ttu-id="ec309-104">Lorsque vous visualisez un rapport qui comprend un explorateur de document, un volet latéral distinct apparaît en regard du rapport.</span><span class="sxs-lookup"><span data-stu-id="ec309-104">When you view a report that includes a document map, a separate side pane appears next to the report.</span></span> <span data-ttu-id="ec309-105">L'utilisateur peut cliquer sur les liens de l'explorateur de documents pour accéder à la page du rapport qui affiche l'élément en question.</span><span class="sxs-lookup"><span data-stu-id="ec309-105">A user can click links in the document map to jump to the report page that displays that item.</span></span> <span data-ttu-id="ec309-106">Les sections et les groupes du rapport sont organisés en une hiérarchie de liens.</span><span class="sxs-lookup"><span data-stu-id="ec309-106">Report sections and groups are arranged in a hierarchy of links.</span></span> <span data-ttu-id="ec309-107">Lorsque vous cliquez sur un de ses éléments, le rapport est actualisé de façon à afficher la zone du rapport correspondant à l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ec309-107">Clicking items in the document map refreshes the report and displays the area of the report that corresponds to the item in the document map.</span></span>  
  
 <span data-ttu-id="ec309-108">Pour ajouter des liens à l'explorateur de documents, vous affectez à la propriété `DocumentMapLabel` de l'élément de rapport du texte que vous créez ou une expression dont le résultat est le texte que vous souhaitez afficher dans l'explorateur de documents.</span><span class="sxs-lookup"><span data-stu-id="ec309-108">To add links to the document map, you set the `DocumentMapLabel` property of the report item to text that you create or to an expression that evaluates to the text that you want display in the document map.</span></span> <span data-ttu-id="ec309-109">Vous pouvez également ajouter à l'explorateur de documents des valeurs uniques pour un groupe de tables ou de matrices.</span><span class="sxs-lookup"><span data-stu-id="ec309-109">You can also add the unique values for a table or matrix group to the document map.</span></span> <span data-ttu-id="ec309-110">Par exemple, pour un groupe se basant sur la couleur, chaque couleur unique est un lien vers la page du rapport qui affiche l'instance de groupe correspondant à cette couleur.</span><span class="sxs-lookup"><span data-stu-id="ec309-110">For example, for a group based on color, each unique color is a link to the report page that displays the group instance for that color.</span></span>  
  
 <span data-ttu-id="ec309-111">Vous pouvez également créer une URL d’accès à un rapport qui remplace l’affichage de l’explorateur de documents, ce qui permet d’exécuter le rapport sans afficher l’explorateur de documents, puis cliquer sur le bouton **Afficher / masquer l’explorateur de documents** dans la barre d’outils de la visionneuse de rapports pour activer/désactiver l’affichage.</span><span class="sxs-lookup"><span data-stu-id="ec309-111">You can also create a URL to a report that overrides the display of the document map, so that you can run the report without displaying the document map, and then click the **Show/Hide Document Map** button on the report viewer toolbar to toggle the display.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="document-maps-and-rendering-extensions"></a><a name="DocMapRenderExtensions"></a> <span data-ttu-id="ec309-112">Explorateurs de document et extensions de rendu</span><span class="sxs-lookup"><span data-stu-id="ec309-112">Document Maps and Rendering Extensions</span></span>  
 <span data-ttu-id="ec309-113">L’explorateur de document est destiné à être utilisé dans l’extension de rendu HTML, par exemple dans l’Aperçu ou la Visionneuse de rapports.</span><span class="sxs-lookup"><span data-stu-id="ec309-113">The document map is intended for use in the HTML rendering extension-for example, in Preview and the Report Viewer.</span></span> <span data-ttu-id="ec309-114">Les autres extensions de rendu articulent un explorateur de document différemment :</span><span class="sxs-lookup"><span data-stu-id="ec309-114">Other rendering extensions have different ways of articulating a document map:</span></span>  
  
-   <span data-ttu-id="ec309-115">L'extension PDF restitue un plan de document sous la forme du volet Signets.</span><span class="sxs-lookup"><span data-stu-id="ec309-115">PDF renders a document map as the Bookmarks pane.</span></span>  
  
-   <span data-ttu-id="ec309-116">L'extension Excel restitue un explorateur de document sous la forme d'une feuille de calcul nommée qui comprend une hiérarchie de liens.</span><span class="sxs-lookup"><span data-stu-id="ec309-116">Excel renders a document map as a named worksheet that includes a hierarchy of links.</span></span> <span data-ttu-id="ec309-117">Les sections du rapport sont restituées dans des feuilles de calcul distinctes incluses avec l'explorateur de document dans le même classeur.</span><span class="sxs-lookup"><span data-stu-id="ec309-117">Report sections are rendered in separate worksheets that are included with the document map in the same workbook.</span></span>  
  
-   <span data-ttu-id="ec309-118">Dans Word, la table des matières est un explorateur de documents.</span><span class="sxs-lookup"><span data-stu-id="ec309-118">Word includes a document map as the table of contents.</span></span>  
  
-   <span data-ttu-id="ec309-119">Les extensions Atom, TIFF, XML et CSV ignorent les explorateurs de documents.</span><span class="sxs-lookup"><span data-stu-id="ec309-119">Atom, TIFF, XML, and CSV ignore document maps.</span></span>  
  
 <span data-ttu-id="ec309-120">Pour plus d’informations, consultez [Fonctionnalité interactive des différentes extensions de rendu de rapport &#40;Générateur de rapports et SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="ec309-120">For more information, see [Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span></span>  
  
##  <a name="AddRptItemToMap"></a>   
#### <a name="to-add-a-report-item-to-a-document-map"></a><span data-ttu-id="ec309-121">Pour ajouter un élément de rapport à un explorateur de documents</span><span class="sxs-lookup"><span data-stu-id="ec309-121">To add a report item to a document map</span></span>  
  
1.  <span data-ttu-id="ec309-122">En mode Conception, sélectionnez l'élément de rapport (par exemple une table, une matrice ou une jauge) que vous souhaitez ajouter à l'explorateur de documents.</span><span class="sxs-lookup"><span data-stu-id="ec309-122">In Design view, select the report item such as a table, matrix, or gauge that you want to add to the document map.</span></span> <span data-ttu-id="ec309-123">Les propriétés de l'élément de rapport s'affichent dans le volet Propriétés.</span><span class="sxs-lookup"><span data-stu-id="ec309-123">The report item properties appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ec309-124">Pour sélectionner une région de données de tableau matriciel, cliquez dans n'importe quelle cellule pour afficher les handles de ligne et de colonne, puis cliquez sur le handle d'angle.</span><span class="sxs-lookup"><span data-stu-id="ec309-124">To select a tablix data region, click in any cell to display the row and column handles, and then click the corner handle.</span></span>  
  
2.  <span data-ttu-id="ec309-125">Dans le volet Propriétés, tapez le texte que vous souhaitez voir apparaître dans l’Explorateur de documents dans la `DocumentMapLabel` propriété, ou entrez une expression qui prend la valeur d’une étiquette.</span><span class="sxs-lookup"><span data-stu-id="ec309-125">In the Properties pane, type the text that you want to appear in the document map in the `DocumentMapLabel` property, or enter an expression that evaluates to a label.</span></span> <span data-ttu-id="ec309-126">Par exemple, tapez **Graphique sur les ventes**.</span><span class="sxs-lookup"><span data-stu-id="ec309-126">For example, type **Sales Chart**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ec309-127">Si le volet Propriétés n’est pas visible, sous l’onglet **Affichage** , dans le groupe **Afficher/Masquer** , sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ec309-127">If you do not see the Properties pane, on the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="ec309-128">Répétez les étapes 1 et 2 pour chaque élément de rapport devant apparaître dans l'explorateur de documents.</span><span class="sxs-lookup"><span data-stu-id="ec309-128">Repeat steps 1 and 2 for every report item that you want to appear in the document map.</span></span>  
  
4.  <span data-ttu-id="ec309-129">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ec309-129">Click **Run**.</span></span> <span data-ttu-id="ec309-130">Le rapport est exécuté et l'explorateur de documents affiche les étiquettes que vous avez créées.</span><span class="sxs-lookup"><span data-stu-id="ec309-130">The report runs and the document map displays the labels you created.</span></span> <span data-ttu-id="ec309-131">Cliquez sur un lien quelconque pour accéder à la page du rapport contenant l'élément en question.</span><span class="sxs-lookup"><span data-stu-id="ec309-131">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="AddUniqueValuesToMap"></a>   
#### <a name="to-add-unique-group-values-to-a-document-map"></a><span data-ttu-id="ec309-132">Pour ajouter des valeurs de groupe uniques à un explorateur de documents</span><span class="sxs-lookup"><span data-stu-id="ec309-132">To add unique group values to a document map</span></span>  
  
1.  <span data-ttu-id="ec309-133">En mode Conception, sélectionnez la table, la matrice ou la liste qui contient le groupe que vous souhaitez afficher dans l'explorateur de documents.</span><span class="sxs-lookup"><span data-stu-id="ec309-133">In Design view, select the table, matrix, or list that contains the group that you want to display in the document map.</span></span> <span data-ttu-id="ec309-134">Le volet Regroupement affiche les groupes de lignes et de colonnes.</span><span class="sxs-lookup"><span data-stu-id="ec309-134">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="ec309-135">Dans le volet Groupes de lignes, cliquez avec le bouton droit sur le groupe, puis cliquez sur **Modifier le groupe**.</span><span class="sxs-lookup"><span data-stu-id="ec309-135">In the Row Groups pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="ec309-136">La page **Général** de la boîte de dialogue **Propriétés du groupe de tableaux matriciels** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="ec309-136">The **General** page of the **Tablix Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="ec309-137">Cliquez sur **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="ec309-137">Click **Advanced**.</span></span>  
  
4.  <span data-ttu-id="ec309-138">Dans la zone de liste **Explorateur de documents** , tapez ou sélectionnez une expression qui correspond à l'expression de groupe.</span><span class="sxs-lookup"><span data-stu-id="ec309-138">In the **Document map** list box, type or select an expression that matches the group expression.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="ec309-139">Répétez les étapes 1 à 4 pour chaque groupe devant apparaître dans l'explorateur de documents.</span><span class="sxs-lookup"><span data-stu-id="ec309-139">Repeat steps 1-4 for every group that you want to appear in the document map.</span></span>  
  
7.  <span data-ttu-id="ec309-140">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ec309-140">Click **Run**.</span></span> <span data-ttu-id="ec309-141">Le rapport est exécuté et l'explorateur de documents affiche les valeurs de groupe.</span><span class="sxs-lookup"><span data-stu-id="ec309-141">The report runs and the document map displays the group values.</span></span> <span data-ttu-id="ec309-142">Cliquez sur un lien quelconque pour accéder à la page du rapport contenant l'élément en question.</span><span class="sxs-lookup"><span data-stu-id="ec309-142">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="HideMapWhenViewRpt"></a>   
#### <a name="to-hide-the-document-map-when-you-view-a-report"></a><span data-ttu-id="ec309-143">Pour masquer l'explorateur de documents lors de l'affichage d'un rapport</span><span class="sxs-lookup"><span data-stu-id="ec309-143">To hide the document map when you view a report</span></span>  
  
1.  <span data-ttu-id="ec309-144">Dans le Gestionnaire de rapports, accédez au rapport contenant l'explorateur de documents.</span><span class="sxs-lookup"><span data-stu-id="ec309-144">In Report Manager, browse to the report that has the document map.</span></span>  
  
     <span data-ttu-id="ec309-145">Par exemple, pour les exemples de rapport [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] , l'URL suivante spécifie le rapport nommé Product Catalog.</span><span class="sxs-lookup"><span data-stu-id="ec309-145">For example, for the [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] sample reports, the following URL specifies the report named Product Catalog.</span></span>  
  
    ```  
    http://localhost/Reports/Pages/Report.aspx?ItemPath=%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    ```  
  
2.  <span data-ttu-id="ec309-146">Copiez le chemin d'accès du rapport sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ec309-146">Copy the report path on the server.</span></span> <span data-ttu-id="ec309-147">Dans l'exemple, le chemin d'accès du rapport est `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span><span class="sxs-lookup"><span data-stu-id="ec309-147">In the example, the report path is `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span></span>  
  
3.  <span data-ttu-id="ec309-148">Créez une nouvelle URL composée des trois éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ec309-148">Create a new URL with the following three components:</span></span>  
  
    -   <span data-ttu-id="ec309-149">Visionneuse de rapports sur le serveur de rapports : `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span><span class="sxs-lookup"><span data-stu-id="ec309-149">The report viewer on the report server: `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span></span>  
  
    -   <span data-ttu-id="ec309-150">Nom du rapport copié à l'étape 1, par exemple : `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span><span class="sxs-lookup"><span data-stu-id="ec309-150">The name of the report you copied in step 1, for example: `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span></span>  
  
    -   <span data-ttu-id="ec309-151">Paramètres d'informations du périphérique qui spécifient le masquage de l'explorateur de documents : `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span><span class="sxs-lookup"><span data-stu-id="ec309-151">The device information parameters that specify hiding the document map: `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span></span>  
  
     <span data-ttu-id="ec309-152">L'URL ci-dessous est composée de ces trois éléments, ajoutés dans l'ordre dans lequel ils sont mentionnés.</span><span class="sxs-lookup"><span data-stu-id="ec309-152">The following URL consists of these three components appended in the order they are listed.</span></span>  
  
    ```  
    http://localhost/ReportServer/Pages/ReportViewer.aspx?  
    %2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    &rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False  
    ```  
  
     <span data-ttu-id="ec309-153">Pour utiliser cette URL, copiez-la et supprimez tous les sauts de ligne.</span><span class="sxs-lookup"><span data-stu-id="ec309-153">To use this URL, copy it and remove all line breaks.</span></span>  
  
4.  <span data-ttu-id="ec309-154">Collez l'URL dans le Gestionnaire de rapports et appuyez sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="ec309-154">Paste the URL in Report Manager, and then press ENTER.</span></span> <span data-ttu-id="ec309-155">Le rapport est exécuté et l'explorateur de documents est masqué.</span><span class="sxs-lookup"><span data-stu-id="ec309-155">The report runs, and the document map is hidden.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec309-156">Pour plus d’informations sur le téléchargement des exemples de rapports, consultez [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Générateur de rapports et concepteur de rapports exemples de rapports](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="ec309-156">For more information about downloading sample reports, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
>   
>  <span data-ttu-id="ec309-157">Pour plus d'informations, consultez « Accès URL » dans la [documentation de Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ec309-157">For more information, see "URL Access" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="ec309-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ec309-158">See Also</span></span>  
 [<span data-ttu-id="ec309-159">Recherche et affichage de rapports dans le Gestionnaire de rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ec309-159">Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md)  
  
  
