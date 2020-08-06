---
title: Boîte de dialogue Propriétés de l’action (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.action.f1
- "10413"
- "10504"
- sql12.rtp.rptdesigner.calculatedseriesproperties.action.f1
- sql12.rtp.rptdesigner.pictureproperties.action.f1
- sql12.rtp.rptdesigner.actionproperties.f1
- sql12.rtp.rptdesigner.charttitleproperties.action.f1
- "10133"
- "10052"
- "10147"
- sql12.rtp.rptdesigner.chartproperties.action.f1
- "10122"
- sql12.rtp.rptdesigner.serieslabelproperties.action.f1
- sql12.rtp.rptdesigner.textboxproperties.action.f1
- "10162"
- "10168"
- sql12.rtp.rptdesigner.textproperties.action.f1
- sql12.rtp.rptdesigner.placeholderproperties.action.f1
- "10250"
- "10129"
- "10244"
- sql12.rtp.rptdesigner.seriesproperties.action.f1
ms.assetid: 2c5d915b-4f97-42cf-b8f1-49ca3ff3d0f9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77b51af0763010676b95fcedb433ab963fc7fcdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611616"
---
# <a name="action-properties-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="15f16-102">Boîte de dialogue Propriétés relatives aux actions (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="15f16-102">Action Properties Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="15f16-103">Vous pouvez utiliser la boîte de dialogue **Action** pour activer les options de lien hypertexte pour un graphique, une jauge ou des éléments cartographiques prenant les liens en charge.</span><span class="sxs-lookup"><span data-stu-id="15f16-103">The **Action** dialog box can be used to enable hyperlink options for a chart, gauge, and map elements that support links.</span></span> <span data-ttu-id="15f16-104">Définissez une action afin qu'un utilisateur puisse cliquer sur le rapport et aller à une URL, à un rapport différent sur le même serveur de rapports ou sur un site SharePoint intégré à un serveur de rapports, ou encore à un emplacement différent dans le même rapport.</span><span class="sxs-lookup"><span data-stu-id="15f16-104">Define an action so that a user can click on the report and link to a URL, to a different report on the same report server or on a SharePoint site that is integrated with a report server, or to a different location in the same report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="15f16-105">Options</span><span class="sxs-lookup"><span data-stu-id="15f16-105">Options</span></span>  
 <span data-ttu-id="15f16-106">**Activer en tant qu'action**</span><span class="sxs-lookup"><span data-stu-id="15f16-106">**Enable as an action**</span></span>  
 <span data-ttu-id="15f16-107">Sélectionnez une option pour indiquer l'action à effectuer lorsque l'utilisateur clique sur l'élément.</span><span class="sxs-lookup"><span data-stu-id="15f16-107">Select an option to indicate the action to perform when the user clicks the item.</span></span>  
  
 <span data-ttu-id="15f16-108">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="15f16-108">**None**</span></span>  
 <span data-ttu-id="15f16-109">Choisissez cette option pour indiquer qu'aucune action n'est associée à l'élément.</span><span class="sxs-lookup"><span data-stu-id="15f16-109">Choose this option to indicate that the item has no action.</span></span>  
  
 <span data-ttu-id="15f16-110">**Atteindre le rapport**</span><span class="sxs-lookup"><span data-stu-id="15f16-110">**Go to report**</span></span>  
 <span data-ttu-id="15f16-111">Choisissez cette option pour créer un lien vers un rapport d'extraction situé sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="15f16-111">Choose this option to create a link to a drillthrough report that is located on a report server.</span></span> <span data-ttu-id="15f16-112">Les options supplémentaires suivantes s’affichent quand vous sélectionnez **Atteindre le rapport**.</span><span class="sxs-lookup"><span data-stu-id="15f16-112">The following additional options appear when you select **Go to report**.</span></span>  
  
 <span data-ttu-id="15f16-113">**Spécifier un rapport**</span><span class="sxs-lookup"><span data-stu-id="15f16-113">**Specify a report**</span></span>  
 <span data-ttu-id="15f16-114">Tapez ou sélectionnez le nom du rapport à utiliser en tant que rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="15f16-114">Type or select the name of the report that you want to use as a drillthrough report.</span></span> <span data-ttu-id="15f16-115">Les rapports d'extraction doivent se trouver sur le même serveur de rapports que ce rapport.</span><span class="sxs-lookup"><span data-stu-id="15f16-115">Drillthrough reports must be on the same report server as this report.</span></span>  
  
 <span data-ttu-id="15f16-116">Pour un rapport publié sur un serveur de rapports configuré pour le mode natif, utilisez un chemin d'accès complet ou relatif sans l'extension de nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="15f16-116">For a report published to a report server configured for native mode, use a full or relative path without the file name extension.</span></span> <span data-ttu-id="15f16-117">Si le rapport se trouve dans le même dossier que le rapport actuel, utilisez uniquement le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="15f16-117">If the report is in the same folder as the current report, use the name of the report only.</span></span> <span data-ttu-id="15f16-118">Si le rapport se trouve dans un dossier différent sur le même serveur de rapports, utilisez un chemin d'accès relatif ou un chemin d'accès complet.</span><span class="sxs-lookup"><span data-stu-id="15f16-118">If the report is in a different folder on the same report server, use a relative path or a full path.</span></span> <span data-ttu-id="15f16-119">Un chemin d'accès relatif commence à partir du dossier actif et remonte dans l'arborescence des dossiers, par exemple ../Dossier2/Rapport1.</span><span class="sxs-lookup"><span data-stu-id="15f16-119">A relative path starts from the current folder and moves up the folder hierarchy, for example, ../Folder2/Report1.</span></span> <span data-ttu-id="15f16-120">Un chemin d'accès complet démarre à partir de /, le dossier de base.</span><span class="sxs-lookup"><span data-stu-id="15f16-120">A full path starts from /, the Home folder.</span></span> <span data-ttu-id="15f16-121">Par exemple, /Rapports/Rapport1.</span><span class="sxs-lookup"><span data-stu-id="15f16-121">For example, /Reports/Report1.</span></span>  
  
 <span data-ttu-id="15f16-122">Pour un rapport publié sur un serveur de rapports configuré en mode intégré SharePoint, utilisez une URL complète incluant l'extension de nom de fichier (.rdl).</span><span class="sxs-lookup"><span data-stu-id="15f16-122">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL including the file name extension (.rdl).</span></span> <span data-ttu-id="15f16-123">Par exemple, http:// *\<SharePointservername>/\<site>* /documents/rapport1.rdl.</span><span class="sxs-lookup"><span data-stu-id="15f16-123">For example, http://*\<SharePointservername>/\<site>*/Documents/Report1.rdl.</span></span> <span data-ttu-id="15f16-124">Les chemins d'accès relatifs ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="15f16-124">Relative paths are not supported.</span></span>  
  
 <span data-ttu-id="15f16-125">Pour plus d’informations, consultez [Spécification de chemins d’accès à des éléments externes &#40;Générateur de rapports et SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) dans la [documentation du Générateur de rapports](https://go.microsoft.com/fwlink/?LinkId=154494) sur msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="15f16-125">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) in the [Report Builder documentation](https://go.microsoft.com/fwlink/?LinkId=154494) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="15f16-126">**Utilisez ces paramètres pour exécuter le rapport**</span><span class="sxs-lookup"><span data-stu-id="15f16-126">**Use these parameters to run the report**</span></span>  
 <span data-ttu-id="15f16-127">Ajoutez une liste de paramètres à transmettre au rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="15f16-127">Add a list of parameters to pass to the drillthrough report.</span></span> <span data-ttu-id="15f16-128">Les noms des paramètres doivent correspondre aux paramètres définis pour le rapport cible.</span><span class="sxs-lookup"><span data-stu-id="15f16-128">The parameter names must match the parameters defined for the target report.</span></span> <span data-ttu-id="15f16-129">Utilisez les boutons **Ajouter** et **Supprimer** pour ajouter et supprimer des paramètres. Utilisez les flèches de direction pour ordonner la liste de paramètres.</span><span class="sxs-lookup"><span data-stu-id="15f16-129">Use the **Add** and **Delete** buttons to add and remove parameters and use the up and down arrows to order the list of parameters.</span></span>  
  
 <span data-ttu-id="15f16-130">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="15f16-130">**Add**</span></span>  
 <span data-ttu-id="15f16-131">Ajoutez un nouveau paramètre à transmettre au rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="15f16-131">Add a new parameter to pass to the drillthrough report.</span></span>  
  
 <span data-ttu-id="15f16-132">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="15f16-132">**Delete**</span></span>  
 <span data-ttu-id="15f16-133">Supprimez un paramètre pour le rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="15f16-133">Delete a parameter for the drillthrough report.</span></span>  
  
 <span data-ttu-id="15f16-134">**Flèche haut**</span><span class="sxs-lookup"><span data-stu-id="15f16-134">**Up arrow**</span></span>  
 <span data-ttu-id="15f16-135">Déplacez le paramètre vers le haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="15f16-135">Move the parameter up in the list.</span></span>  
  
 <span data-ttu-id="15f16-136">**Flèche bas**</span><span class="sxs-lookup"><span data-stu-id="15f16-136">**Down arrow**</span></span>  
 <span data-ttu-id="15f16-137">Déplacez le paramètre vers le bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="15f16-137">Move the parameter down in the list.</span></span>  
  
 <span data-ttu-id="15f16-138">**Nom**</span><span class="sxs-lookup"><span data-stu-id="15f16-138">**Name**</span></span>  
 <span data-ttu-id="15f16-139">Tapez le texte qui correspond au nom d'un paramètre défini dans le rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="15f16-139">Type text that is the name of a parameter defined in the drillthrough report.</span></span>  
  
 <span data-ttu-id="15f16-140">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="15f16-140">**Value**</span></span>  
 <span data-ttu-id="15f16-141">Tapez ou sélectionnez une valeur à transmettre pour le paramètre nommé dans le rapport d'extraction.</span><span class="sxs-lookup"><span data-stu-id="15f16-141">Type or select a value to pass for the named parameter in the drillthrough report.</span></span> <span data-ttu-id="15f16-142">Cliquez sur le bouton **Expression** (*fx*) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="15f16-142">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="15f16-143">**Omettre**</span><span class="sxs-lookup"><span data-stu-id="15f16-143">**Omit**</span></span>  
 <span data-ttu-id="15f16-144">Sélectionnez pour empêcher le paramètre de s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="15f16-144">Select to prevent the parameter from running.</span></span> <span data-ttu-id="15f16-145">Par défaut, cette case à cocher est désactivée et n'est pas active.</span><span class="sxs-lookup"><span data-stu-id="15f16-145">By default, this check box is cleared and not active.</span></span> <span data-ttu-id="15f16-146">Pour cocher la case, cliquez sur le bouton **Expression** (*fx*) et tapez **True** ou créez une expression.</span><span class="sxs-lookup"><span data-stu-id="15f16-146">To select the check box, click the **Expression** (*fx*) button and either type **True** or create an expression.</span></span> <span data-ttu-id="15f16-147">La case à cocher est activée lorsque vous cliquez sur **OK** dans la boîte de dialogue **expression** .</span><span class="sxs-lookup"><span data-stu-id="15f16-147">The check box is selected when you click **OK** in the **Expression** dialog box.</span></span>  
  
 <span data-ttu-id="15f16-148">**Atteindre le signet**</span><span class="sxs-lookup"><span data-stu-id="15f16-148">**Go to bookmark**</span></span>  
 <span data-ttu-id="15f16-149">Choisissez cette option pour définir un lien vers un signet dans le rapport actuel.</span><span class="sxs-lookup"><span data-stu-id="15f16-149">Choose this option to define a link to a bookmark in the current report.</span></span> <span data-ttu-id="15f16-150">L’option supplémentaire suivante s’affiche quand vous sélectionnez **Atteindre le signet**.</span><span class="sxs-lookup"><span data-stu-id="15f16-150">The following additional option appears when you select **Go to bookmark**.</span></span>  
  
 <span data-ttu-id="15f16-151">**Sélectionner un signet**</span><span class="sxs-lookup"><span data-stu-id="15f16-151">**Select bookmark**</span></span>  
 <span data-ttu-id="15f16-152">Tapez ou sélectionnez l'identificateur de signet du rapport à atteindre lorsque l'utilisateur clique sur le lien.</span><span class="sxs-lookup"><span data-stu-id="15f16-152">Type or select the bookmark ID for the report to jump to when the user clicks the link.</span></span> <span data-ttu-id="15f16-153">Cliquez sur le bouton Expression (**fx**) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="15f16-153">Click the Expression (**fx**) button to change the expression.</span></span> <span data-ttu-id="15f16-154">L'identificateur du signet peut correspondre à un ID statique ou une expression ayant pour résultat un identificateur du signet.</span><span class="sxs-lookup"><span data-stu-id="15f16-154">The bookmark ID can be either a static ID or an expression that evaluates to a bookmark ID.</span></span> <span data-ttu-id="15f16-155">L'expression peut inclure un champ qui contient un identificateur de signet.</span><span class="sxs-lookup"><span data-stu-id="15f16-155">The expression can include a field that contains a bookmark ID.</span></span>  
  
 <span data-ttu-id="15f16-156">Pour définir un lien vers un signet, vous devez d'abord définir la propriété de signet d'un élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="15f16-156">To link to a bookmark, you must first set the Bookmark property of a report item.</span></span> <span data-ttu-id="15f16-157">Pour définir la propriété de signet, sélectionnez un élément de rapport et, dans le volet Propriétés, tapez une valeur ou expression pour l'identificateur du signet, par exemple, SalesChart ou 5TopSales.</span><span class="sxs-lookup"><span data-stu-id="15f16-157">To set the Bookmark property, select a report item, and in the Properties pane, type a value or expression for the bookmark ID; for example, SalesChart or 5TopSales.</span></span>  
  
 <span data-ttu-id="15f16-158">**Atteindre l'URL**</span><span class="sxs-lookup"><span data-stu-id="15f16-158">**Go to URL**</span></span>  
 <span data-ttu-id="15f16-159">Choisissez cette option pour définir un lien vers une page Web.</span><span class="sxs-lookup"><span data-stu-id="15f16-159">Choose this option to define a link to a Web page.</span></span> <span data-ttu-id="15f16-160">Tapez ou sélectionnez l'URL d'une page Web, ou une expression qui prend la valeur de l'URL d'une page Web.</span><span class="sxs-lookup"><span data-stu-id="15f16-160">Type or select the URL of a Web page or an expression that evaluates to the URL of a Web page.</span></span> <span data-ttu-id="15f16-161">Cliquez sur le bouton **Expression** (*fx*) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="15f16-161">Click the **Expression** (*fx*) button to change the expression.</span></span> <span data-ttu-id="15f16-162">Cette expression peut inclure un champ qui contient une URL.</span><span class="sxs-lookup"><span data-stu-id="15f16-162">This expression can include a field that contains a URL.</span></span> <span data-ttu-id="15f16-163">L’option supplémentaire suivante s’affiche quand vous sélectionnez **Atteindre l’URL**.</span><span class="sxs-lookup"><span data-stu-id="15f16-163">The following additional option appears when you select **Go to URL**.</span></span>  
  
 <span data-ttu-id="15f16-164">**Sélectionner une URL**</span><span class="sxs-lookup"><span data-stu-id="15f16-164">**Select URL**</span></span>  
 <span data-ttu-id="15f16-165">Tapez ou entrez l'URL de l'élément.</span><span class="sxs-lookup"><span data-stu-id="15f16-165">Type or enter the URL of the item.</span></span> <span data-ttu-id="15f16-166">Pour un élément publié sur un serveur de rapports configuré pour le mode natif, utilisez un chemin d'accès complet ou relatif.</span><span class="sxs-lookup"><span data-stu-id="15f16-166">For an item published to a report server configured for native mode, use a full or relative path.</span></span> <span data-ttu-id="15f16-167">Par exemple, http:// *\<servername>* /images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="15f16-167">For example, http://*\<servername>*/images/image1.jpg.</span></span> <span data-ttu-id="15f16-168">Pour un élément publié sur un serveur de rapports configuré en mode intégré SharePoint, utilisez une URL complète (par exemple, http:// *\<SharePointservername>/\<site>* /Documents/images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="15f16-168">For an item published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f16-169">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="15f16-169">See Also</span></span>  
 <span data-ttu-id="15f16-170">[Graphiques &#40;Générateur de rapports et SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="15f16-170">[Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="15f16-171">[Aide Générateur de rapports pour les boîtes de dialogue, les volets et les assistants](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="15f16-171">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="15f16-172">[Paramètres de rapport &#40;Générateur de rapports et de Concepteur de rapports&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="15f16-172">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="15f16-173">[Ajoutez un sous-rapport et des paramètres &#40;Générateur de rapports et SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="15f16-173">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="15f16-174">Tri interactif, Explorateurs de documents et liens &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="15f16-174">Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;</span></span>](report-design/interactive-sort-document-maps-and-links-report-builder-and-ssrs.md)  
  
  
