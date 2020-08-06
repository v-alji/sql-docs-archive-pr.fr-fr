---
title: Imprimer un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b96936c9-c387-41a9-8c19-6eb325769ffd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe029019cdf9739153256db399cfa1426d3ba632
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603280"
---
# <a name="print-a-report-report-builder-and-ssrs"></a><span data-ttu-id="c5b3a-102">Imprimer un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="c5b3a-102">Print a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c5b3a-103">Après avoir enregistré un rapport sur un serveur de rapports, vous pouvez l'afficher et l'imprimer à partir d'un navigateur, du Gestionnaire de rapports ou de toute application permettant d'afficher un rapport exporté.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-103">After you save a report to a report server, you can view and print the report from a browser, Report Manager, or any application that you use to view an exported report.</span></span> <span data-ttu-id="c5b3a-104">Avant d'enregistrer un rapport, vous pouvez l'imprimer après avoir affiché son aperçu.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-104">Before saving a report, you can print it when you preview it.</span></span>  
  
 <span data-ttu-id="c5b3a-105">Lorsque vous imprimez un rapport, vous pouvez spécifier le format du papier à utiliser.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-105">When you print a report, you can specify the size of the paper to use.</span></span> <span data-ttu-id="c5b3a-106">Le format du papier détermine le nombre de pages dans un rapport et les données de rapport qui remplissent chaque page.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-106">The size of the paper determines the number of pages in a report and which report data fits on each page.</span></span> <span data-ttu-id="c5b3a-107">Le format de papier affecte uniquement les rapports rendus avec des convertisseurs de saut de page manuel : PDF, Image et Impression.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-107">Paper size affects only reports that are rendered with hard page-break renders: PDF, Image, and Print.</span></span> <span data-ttu-id="c5b3a-108">La définition du format de papier n'a aucun effet sur d'autres convertisseurs.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-108">Setting the paper size has no effect on other renderers.</span></span> <span data-ttu-id="c5b3a-109">Pour plus d’informations, consultez [Comportements de rendu &#40;Générateur de rapports et SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c5b3a-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="c5b3a-110">Dans la barre d'outils de la visionneuse de rapports dans le Gestionnaire de rapports ou en mode Aperçu dans le Générateur de rapports, vous pouvez exporter un rapport vers un convertisseur de saut de page manuel ou cliquer sur le bouton Imprimer pour imprimer une copie du rapport.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-110">From the report viewer toolbar in Report Manager or in preview in Report Builder, you can export a report to a hard page-break renderer or click the Print button to print a copy of the report.</span></span> <span data-ttu-id="c5b3a-111">Vous pouvez devoir définir le format de papier ou d'autres propriétés de mise en page.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-111">You might need to set the paper size or other page setup properties.</span></span> <span data-ttu-id="c5b3a-112">Utilisez la boîte de dialogue **Propriétés du rapport** pour modifier les propriétés de mise en page, y compris le format de papier.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-112">Use the **Report Properties** dialog box to change page setup properties, including paper size.</span></span>  
  
 <span data-ttu-id="c5b3a-113">Vous pouvez spécifier les marges de page pour l'impression à deux emplacements : en mode Création et en mode Exécution.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-113">You can specify print page margins in two different locations: in design mode and in run mode.</span></span>  
  
-   <span data-ttu-id="c5b3a-114">**Mode Création.**</span><span class="sxs-lookup"><span data-stu-id="c5b3a-114">**Design mode.**</span></span> <span data-ttu-id="c5b3a-115">Lorsque vous définissez des marges de page en mode Création, ces paramètres sont enregistrés dans la définition de rapport lorsque vous enregistrez le rapport.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-115">When you set page margins in design mode, these settings are saved in the report definition when you save the report.</span></span>  
  
-   <span data-ttu-id="c5b3a-116">**Mode d’exécution.**</span><span class="sxs-lookup"><span data-stu-id="c5b3a-116">**Run mode.**</span></span> <span data-ttu-id="c5b3a-117">Lorsque vous définissez des marges de page en mode Exécution, ces informations ne sont pas enregistrées dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-117">When you set page margins in run mode, this information is not saved in the report definition.</span></span> <span data-ttu-id="c5b3a-118">La prochaine fois que vous imprimerez le rapport, vous obtiendrez les paramètres de la définition du rapport à moins que vous n'indiquiez de nouveau vos marges pour l'impression.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-118">The next time you print the report, you will get the settings from the report definition, unless you indicate your print margins again.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5b3a-119">Les marges pour l'impression ne sont pas affichées en mode Création et Exécution.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-119">Print margins are not displayed in design or run modes.</span></span> <span data-ttu-id="c5b3a-120">Il n'y a aucune relation entre l'aire de conception et la zone d'impression de votre rapport.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-120">There is no relationship between the design surface area and the print area of your report.</span></span> <span data-ttu-id="c5b3a-121">Pour afficher les marges pour l’impression, en mode Exécution, cliquez sur Page sous l’onglet **Exécuter** dans le ruban.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-121">To see print margins, in run mode, click Print Layout on the **Run** tab on the Ribbon.</span></span>  
  
 <span data-ttu-id="c5b3a-122">Pour plus d’informations sur la pagination des rapports, consultez [Pagination dans Reporting Services &#40;Générateur de rapports et SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c5b3a-122">For more information about report paging, see [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-print-a-report-in-report-builder"></a><span data-ttu-id="c5b3a-123">Pour imprimer un rapport dans le Générateur de rapports</span><span class="sxs-lookup"><span data-stu-id="c5b3a-123">To print a report in Report Builder</span></span>  
  
1.  <span data-ttu-id="c5b3a-124">Ouvrez un rapport.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-124">Open a report.</span></span>  
  
2.  <span data-ttu-id="c5b3a-125">Dans l’onglet dossier de démarrage, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-125">On the Home tab, click **Run**.</span></span>  
  
3.  <span data-ttu-id="c5b3a-126">(Facultatif) Cliquez sur **Page** pour visualiser l’apparence du rapport imprimé.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-126">(optional) Click **Print Layout** to see how the report will look when it is printed.</span></span>  
  
4.  <span data-ttu-id="c5b3a-127">(Facultatif) Cliquez sur **Mise en page** pour définir le papier, l’orientation et les marges.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-127">(optional) Click **Page Setup** to set paper, orientation, and margins.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5b3a-128">Les valeurs par défaut proviennent des propriétés du rapport, qui sont définies en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-128">The default values for these come from the report properties, which are set in Design view.</span></span> <span data-ttu-id="c5b3a-129">Les valeurs que vous définissez dans cette boîte de dialogue **Mise en page** s’appliquent uniquement à la session active.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-129">The values you set here in the **Page Setup** dialog box are for this session only.</span></span> <span data-ttu-id="c5b3a-130">Si vous fermez puis rouvrez le rapport, il présentera à nouveau les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-130">When you close this report and reopen it, it will have the default values again.</span></span>  
  
5.  <span data-ttu-id="c5b3a-131">Cliquez sur **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-131">Click **Print**.</span></span>  
  
6.  <span data-ttu-id="c5b3a-132">Dans la boîte de dialogue **Imprimer** , sélectionnez une imprimante et spécifiez d’autres options d’impression.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-132">In the **Print** dialog box, select a printer and specify other printing options.</span></span>  
  
### <a name="to-print-a-report-from-a-web-browser-application"></a><span data-ttu-id="c5b3a-133">Pour imprimer un rapport à partir d'un navigateur Web</span><span class="sxs-lookup"><span data-stu-id="c5b3a-133">To print a report from a Web browser application</span></span>  
  
1.  <span data-ttu-id="c5b3a-134">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c5b3a-134">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="c5b3a-135">Dans le Gestionnaire de rapports, parcourez l'arborescence jusqu'au rapport à imprimer.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-135">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="c5b3a-136">Ouvrez le rapport.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-136">Open the report.</span></span>  
  
3.  <span data-ttu-id="c5b3a-137">Dans la barre d’outils, en haut du rapport, cliquez sur **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-137">On the toolbar at the top of the report, click **Print**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5b3a-138">Lorsque vous imprimez un rapport HTML pour la première fois, le serveur de rapports vous invite à installer un contrôle ActiveX d'impression.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-138">The first time you print an HTML report, the report server prompts you to install an ActiveX control used for printing.</span></span> <span data-ttu-id="c5b3a-139">Vous devez installer et configurer ce contrôle pour pouvoir imprimer.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-139">You must install and configure the control to print.</span></span>  
  
4.  <span data-ttu-id="c5b3a-140">Dans la boîte de dialogue **Imprimer** , sélectionnez une imprimante, puis cliquez sur **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-140">In the **Print** dialog box, select a printer, and then click **Prin**t.</span></span>  
  
### <a name="to-print-a-report-from-other-applications"></a><span data-ttu-id="c5b3a-141">Pour imprimer un rapport à partir d'autres applications</span><span class="sxs-lookup"><span data-stu-id="c5b3a-141">To print a report from other applications</span></span>  
  
1.  <span data-ttu-id="c5b3a-142">Dans le Gestionnaire de rapports, parcourez l'arborescence jusqu'au rapport à imprimer.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-142">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="c5b3a-143">Ouvrez le rapport.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-143">Open the report.</span></span>  
  
2.  <span data-ttu-id="c5b3a-144">Dans la barre d’outils en haut du rapport, sélectionnez un format de rendu, puis cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-144">On the toolbar at the top of the report, select a rendering format, and then click **Export**.</span></span> <span data-ttu-id="c5b3a-145">Le rapport s'ouvre dans une application visionneuse correspondant au format de rendu.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-145">The report opens in a viewer application that corresponds to the rendering format.</span></span>  
  
     <span data-ttu-id="c5b3a-146">De fait, si vous sélectionnez le format PDF, le rapport s'ouvre dans Adobe Acrobat Reader.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-146">For example, if you select PDF, the report opens in Adobe Acrobat Reader.</span></span>  
  
3.  <span data-ttu-id="c5b3a-147">Dans le menu **Fichier** de ce programme, cliquez sur **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-147">On the **File** menu in that program, click **Print**.</span></span>  
  
### <a name="to-change-paper-size"></a><span data-ttu-id="c5b3a-148">Pour modifier le format de papier</span><span class="sxs-lookup"><span data-stu-id="c5b3a-148">To change paper size</span></span>  
  
1.  <span data-ttu-id="c5b3a-149">Cliquez avec le bouton droit à l’extérieur du corps du rapport, puis cliquez sur **Propriétés du rapport**.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-149">Right-click outside of the report body and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="c5b3a-150">Dans **Mise en page**, sélectionnez une valeur dans la liste **Format de papier** .</span><span class="sxs-lookup"><span data-stu-id="c5b3a-150">In **Page Setup**, select a value from the **Paper Size** list.</span></span> <span data-ttu-id="c5b3a-151">Chaque option remplit les propriétés **Largeur** et **Hauteur** .</span><span class="sxs-lookup"><span data-stu-id="c5b3a-151">Each option populates the **Width** and **Height** properties.</span></span> <span data-ttu-id="c5b3a-152">Vous pouvez également spécifier un format personnalisé en tapant des valeurs numériques dans les zones **Largeur** et **Hauteur** .</span><span class="sxs-lookup"><span data-stu-id="c5b3a-152">You can also specify a custom size by typing numeric values in the **Width** and **Height** boxes.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5b3a-153">Les valeurs qui définissent la taille sont assorties d'une unité par défaut qui est basée sur les paramètres régionaux de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-153">Size values have a default unit based on the user's locale settings.</span></span> <span data-ttu-id="c5b3a-154">Pour choisir une unité différente, tapez un indicateur d'unité physique comme cm, mm, pt ou pc après la valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="c5b3a-154">To designate a different unit, type a physical unit designator such as cm, mm, pt, or pc after the numeric value.</span></span>  
  
### <a name="to-set-page-margins-in-design-mode"></a><span data-ttu-id="c5b3a-155">Pour définir des marges de page en mode Création</span><span class="sxs-lookup"><span data-stu-id="c5b3a-155">To set page margins in design mode</span></span>  
  
-   <span data-ttu-id="c5b3a-156">Cliquez avec le bouton droit sur la zone bleue autour de l’aire de conception, cliquez sur **Propriétés du rapport**, puis cliquez sur la page **Mise en page** .</span><span class="sxs-lookup"><span data-stu-id="c5b3a-156">Right-click the blue area around the design surface, click **Report Properties**, and then click the **Page Setup** page.</span></span>  
  
### <a name="to-set-page-margins-in-run-mode"></a><span data-ttu-id="c5b3a-157">Pour définir des marges de page en mode Exécution</span><span class="sxs-lookup"><span data-stu-id="c5b3a-157">To set page margins in run mode</span></span>  
  
-   <span data-ttu-id="c5b3a-158">Cliquez sur **Mise en page** sous l’onglet **Exécuter** .</span><span class="sxs-lookup"><span data-stu-id="c5b3a-158">Click **Page Setup** on the **Run** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b3a-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c5b3a-159">See Also</span></span>  
 <span data-ttu-id="c5b3a-160">[Imprimer des rapports &#40;Générateur de rapports et SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c5b3a-160">[Print Reports &#40;Report Builder and SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c5b3a-161">[Exportation de rapports &#40;Générateur de rapports et SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c5b3a-161">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c5b3a-162">[Boîte de dialogue Propriétés du rapport, Mise en page &#40;Générateur de rapports&#41;](../report-properties-dialog-box-page-setup-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c5b3a-162">[Report Properties Dialog Box, Page Setup &#40;Report Builder&#41;](../report-properties-dialog-box-page-setup-report-builder.md) </span></span>  
 [<span data-ttu-id="c5b3a-163">Mode Conception de rapport &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="c5b3a-163">Report Design View &#40;Report Builder&#41;</span></span>](report-design-view-report-builder.md)  
  
  
