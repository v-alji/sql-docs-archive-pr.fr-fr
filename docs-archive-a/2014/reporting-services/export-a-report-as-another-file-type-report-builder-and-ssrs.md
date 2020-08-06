---
title: Exporter un rapport dans un autre type de fichier (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b577568b-ecbd-44c3-be88-31dab6fc38a2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 240d3266b7b8c9a445658a9fd21fb9ea18a4c113
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695440"
---
# <a name="export-a-report-as-another-file-type-report-builder-and-ssrs"></a><span data-ttu-id="272e0-102">Exporter un rapport dans un autre type de fichier (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="272e0-102">Export a Report as Another File Type (Report Builder and SSRS)</span></span>
  <span data-ttu-id="272e0-103">Vous pouvez effectuer le rendu d'un rapport dans un autre format de fichier, tel que CSV, Image, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)]ou [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], en affichant un aperçu de votre rapport dans le Générateur de rapports ou le Concepteur de rapports, ou vous pouvez effectuer le rendu du rapport en visualisant le rapport sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="272e0-103">You can render a report to another file format, such as CSV, Image, PDF, [!INCLUDE[ofprword](../includes/ofprword-md.md)], or [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)], while previewing your report in Report Builder or Report Designer, or you can render the report while viewing the report on the report server.</span></span> <span data-ttu-id="272e0-104">Le rendu du rapport dans un format spécifique est utile lorsque vous souhaitez enregistrer immédiatement le rapport dans un autre type de fichier sans le publier sur le serveur de rapports ou lorsque vous souhaitez voir l'aspect de votre conception de rapport une fois remis aux lecteurs du rapport dans un format spécifique.</span><span class="sxs-lookup"><span data-stu-id="272e0-104">Rendering the report in a specific format in is helpful when you want to immediately save the report as another file type without publishing the report to the report server or when you want to see how your report design will appear when delivered to your report readers in a specific format.</span></span> <span data-ttu-id="272e0-105">Le rendu du rapport sur le serveur de rapports est utile lorsque vous définissez des abonnements ou remettez vos rapports via messagerie électronique, ou si vous souhaitez enregistrer un rapport qui est disponible sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="272e0-105">Rendering the report on the report server is useful when you set up subscriptions or deliver your reports via e-mail, or if you want to save a report that is available on the report server.</span></span> <span data-ttu-id="272e0-106">Pour plus d’informations, consultez [Abonnements et remise &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="272e0-106">For more information, see [Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../includes/ssrbrddup-md.md)]  
  
### <a name="to-export-a-report-as-another-file-type-in-report-builder"></a><span data-ttu-id="272e0-107">Pour exporter un rapport dans un autre type de fichier dans le Générateur de rapports</span><span class="sxs-lookup"><span data-stu-id="272e0-107">To export a report as another file type in Report Builder</span></span>  
  
1.  <span data-ttu-id="272e0-108">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="272e0-108">Preview the report.</span></span>  
  
2.  <span data-ttu-id="272e0-109">Dans le ruban, cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="272e0-109">On the ribbon, click **Export**.</span></span>  
  
3.  <span data-ttu-id="272e0-110">Sélectionnez le format que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="272e0-110">Select the format that you want to use.</span></span>  
  
     <span data-ttu-id="272e0-111">La boîte de dialogue **Enregistrer sous** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="272e0-111">The **Save As** dialog box opens.</span></span> <span data-ttu-id="272e0-112">Par défaut, le nom du fichier correspond à celui du rapport que vous avez exporté.</span><span class="sxs-lookup"><span data-stu-id="272e0-112">By default, the file name is that of the report that you exported.</span></span> <span data-ttu-id="272e0-113">Vous pouvez éventuellement modifier le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="272e0-113">Optionally, you can change the file name.</span></span>  
  
4.  <span data-ttu-id="272e0-114">Accédez à l'emplacement où vous avez enregistré le rapport exporté et ouvrez-le.</span><span class="sxs-lookup"><span data-stu-id="272e0-114">Navigate to the location where you saved the exported report and open it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="272e0-115">Si le programme ne peut pas ouvrir le rapport dans le format que vous avez choisi car aucun programme n'est associé à ce type de fichier, vous êtes invité à enregistrer le rapport exporté ou à rechercher un programme en ligne pour ouvrir le rapport.</span><span class="sxs-lookup"><span data-stu-id="272e0-115">If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-report-manager"></a><span data-ttu-id="272e0-116">Pour exporter un rapport dans un autre type de fichier dans le Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="272e0-116">To export a report as another file type in Report Manager</span></span>  
  
1.  <span data-ttu-id="272e0-117">À partir du Gestionnaire de rapports, affichez la page **Accueil** et naviguez jusqu'au rapport que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="272e0-117">From the Report Manager **Home** page, navigate to the report that you want to export.</span></span>  
  
2.  <span data-ttu-id="272e0-118">Cliquez sur le rapport.</span><span class="sxs-lookup"><span data-stu-id="272e0-118">Click the report.</span></span>  
  
     <span data-ttu-id="272e0-119">Le rapport est généré.</span><span class="sxs-lookup"><span data-stu-id="272e0-119">The report is generated.</span></span>  
  
3.  <span data-ttu-id="272e0-120">Dans la barre d'outils Visionneuse de rapports, cliquez sur la flèche déroulante **Sélectionner un format** .</span><span class="sxs-lookup"><span data-stu-id="272e0-120">On the Report Viewer toolbar, click the **Select a format** drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="272e0-121">Sélectionnez le format que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="272e0-121">Select the format that you want to use.</span></span>  
  
5.  <span data-ttu-id="272e0-122">Cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="272e0-122">Click **Export**.</span></span>  
  
     <span data-ttu-id="272e0-123">Un message s'affiche qui vous demande si vous souhaitez ouvrir ou enregistrer le fichier.</span><span class="sxs-lookup"><span data-stu-id="272e0-123">A message appears asking you if you want to open or save the file.</span></span>  
  
6.  <span data-ttu-id="272e0-124">Pour afficher le rapport dans le format d'exportation sélectionné, cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="272e0-124">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="272e0-125">\- ou -</span><span class="sxs-lookup"><span data-stu-id="272e0-125">\- or -</span></span>  
  
     <span data-ttu-id="272e0-126">Pour enregistrer immédiatement le rapport dans le format d'exportation sélectionné, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="272e0-126">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="272e0-127">À l'aide de l'application associée au format que vous avez choisi, le rapport est affiché ou enregistré.</span><span class="sxs-lookup"><span data-stu-id="272e0-127">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="272e0-128">Si vous cliquez sur **Enregistrer**, vous devrez indiquer un emplacement pour enregistrer votre rapport.</span><span class="sxs-lookup"><span data-stu-id="272e0-128">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="272e0-129">**Remarque** Si le programme ne peut pas ouvrir le rapport dans le format que vous avez choisi car vous ne disposez pas d'un programme associé à ce type de fichier, vous serez invité à enregistrer le rapport exporté ou à rechercher un programme en ligne pour ouvrir le rapport.</span><span class="sxs-lookup"><span data-stu-id="272e0-129">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
### <a name="to-export-a-report-as-another-file-type-in-a-sharepoint-library"></a><span data-ttu-id="272e0-130">Pour exporter un rapport dans un autre type de fichier dans une bibliothèque SharePoint</span><span class="sxs-lookup"><span data-stu-id="272e0-130">To export a report as another file type in a SharePoint library</span></span>  
  
1.  <span data-ttu-id="272e0-131">Affichez un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="272e0-131">Preview the report.</span></span>  
  
2.  <span data-ttu-id="272e0-132">Dans la barre d'outils, cliquez sur **Actions**, pointez sur **Exporter**, puis sélectionnez le format à utiliser.</span><span class="sxs-lookup"><span data-stu-id="272e0-132">On the toolbar, click **Actions**, point to **Export**, and then select the format that you want to use.</span></span>  
  
     <span data-ttu-id="272e0-133">La boîte de dialogue **Téléchargement de fichiers** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="272e0-133">The **File Download** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="272e0-134">Pour afficher le rapport dans le format d'exportation sélectionné, cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="272e0-134">To view the report in the selected export format, click **Open**.</span></span>  
  
     <span data-ttu-id="272e0-135">\- ou -</span><span class="sxs-lookup"><span data-stu-id="272e0-135">\- or -</span></span>  
  
     <span data-ttu-id="272e0-136">Pour enregistrer immédiatement le rapport dans le format d'exportation sélectionné, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="272e0-136">To immediately save the report in the selected export format, click **Save**.</span></span>  
  
     <span data-ttu-id="272e0-137">À l'aide de l'application associée au format que vous avez choisi, le rapport est affiché ou enregistré.</span><span class="sxs-lookup"><span data-stu-id="272e0-137">Using the application that is associated with the format that you chose, the report is either displayed or saved.</span></span> <span data-ttu-id="272e0-138">Si vous cliquez sur **Enregistrer**, vous devrez indiquer un emplacement pour enregistrer votre rapport.</span><span class="sxs-lookup"><span data-stu-id="272e0-138">If you click **Save**, you will be prompted for a location where you can save your report.</span></span>  
  
     <span data-ttu-id="272e0-139">Modifiez éventuellement le nom de fichier du rapport exporté.</span><span class="sxs-lookup"><span data-stu-id="272e0-139">Optionally, change the file name of the exported report.</span></span>  
  
     <span data-ttu-id="272e0-140">**Remarque** Si le programme ne peut pas ouvrir le rapport dans le format que vous avez choisi car vous ne disposez pas d'un programme associé à ce type de fichier, vous serez invité à enregistrer le rapport exporté ou à rechercher un programme en ligne pour ouvrir le rapport.</span><span class="sxs-lookup"><span data-stu-id="272e0-140">**Note** If the program cannot open the report in the format that you chose because you do not have a program associated with this file type, you will be prompted to save the exported report or to find a program online to open the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="272e0-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="272e0-141">See Also</span></span>  
 <span data-ttu-id="272e0-142">[Exportation de rapports &#40;Générateur de rapports et SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="272e0-142">[Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="272e0-143">[Pagination dans Reporting Services &#40;Générateur de rapports et SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="272e0-143">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="272e0-144">Fonctionnalités interactives des différentes extensions de rendu de rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="272e0-144">Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;</span></span>](report-builder/interactive-functionality-different-report-rendering-extensions.md)  
  
  
