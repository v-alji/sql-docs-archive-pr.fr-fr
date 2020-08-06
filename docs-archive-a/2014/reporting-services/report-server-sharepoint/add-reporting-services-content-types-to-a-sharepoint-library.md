---
title: Ajouter le composant WebPart Visionneuse de rapports à une page Web (Reporting Services en mode intégré SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SharePoint integration [Reporting Services], viewing reports
- Web Parts [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
ms.assetid: cac75345-2380-467d-a394-0a2140908a5a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d9b933fad8bc566b3cb0ef04303a85c5f034e620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704876"
---
# <a name="add-the-report-viewer-web-part-to-a-web-page-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="7bcd3-102">Ajouter le composant WebPart Visionneuse de rapports à une page Web (Reporting Services en mode intégré SharePoint)</span><span class="sxs-lookup"><span data-stu-id="7bcd3-102">Add the Report Viewer Web Part to a Web Page (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="7bcd3-103">Vous pouvez utiliser le composant WebPart Visionneuse de rapports pour afficher les rapports qui s'exécutent sur un serveur de rapports configuré en mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-103">You can use the Report Viewer Web Part to view reports that run on report server that is configured to run in SharePoint integrated mode.</span></span> <span data-ttu-id="7bcd3-104">Vous pouvez utiliser le composant WebPart pour afficher les fichiers de définition de rapport (.rdl) que vous avez créés dans le Générateur de rapports ou le Concepteur de rapports, et que vous avez téléchargés vers une bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-104">You can use the Web Part to display report definition (.rdl) files that you created in Report Builder or Report Designer and uploaded to a library.</span></span>  
  
 <span data-ttu-id="7bcd3-105">Vous pouvez ajouter le composant WebPart de visionneuse de rapports à une page Web si vous souhaitez incorporer un rapport dans cette page.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-105">You can add the Report Viewer Web Part to a Web page if you want to embed a report on that page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bcd3-106">Même si leurs noms sont identiques, le composant WebPart Visionneuse de rapports installé par le complément [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] est différent du composant WebPart Visionneuse de rapports inclus dans le fichier RSWebParts.cab.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-106">Although they have identical names, the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in is different from the Report Viewer Web Part that is included in the RSWebParts.cab file.</span></span> <span data-ttu-id="7bcd3-107">Les instructions de cette rubrique sont spécifiques au composant WebPart Visionneuse de rapports installé à l'aide du complément [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bcd3-107">The instructions in this topic are specifically for the Report Viewer Web Part that is installed through the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Add-in.</span></span>  
  
 <span data-ttu-id="7bcd3-108">Pour ajouter un composant WebPart à une page Web, vous devez disposer de l'autorisation Ajouter et personnaliser les pages au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-108">To add a Web Part to a Web page, you must have the Add and Customize Pages permission at the site level.</span></span> <span data-ttu-id="7bcd3-109">Si vous utilisez des paramètres de sécurité par défaut, cette autorisation est accordée aux membres du groupe **Propriétaires** qui ont le niveau d’autorisation Contrôle total.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-109">If you are using default security settings, this permission is granted to members of the **Owners** group who have the Full Control level of permission.</span></span>  
  
### <a name="to-embed-a-report-in-a-web-page"></a><span data-ttu-id="7bcd3-110">Pour incorporer un rapport dans une page Web</span><span class="sxs-lookup"><span data-stu-id="7bcd3-110">To embed a report in a Web page</span></span>  
  
1.  <span data-ttu-id="7bcd3-111">Ouvrez ou créez la page ou le tableau de bord de composant WebPart.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-111">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="7bcd3-112">Dans **Actions de site**, cliquez sur **Modifier la page**.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-112">On **Site Actions**, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="7bcd3-113">Cliquez sur **Ajouter un composant WebPart**.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-113">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="7bcd3-114">Dans la liste de catégories WebPart, sélectionnez la catégorie **Divers** , puis **Visionneuse de rapports SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-114">In the list of web part categories, select the **Miscellaneous** category, and then select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="7bcd3-115">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-115">Click **Add**.</span></span> <span data-ttu-id="7bcd3-116">Le composant WebPart est ajouté en haut de la zone.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-116">The Web Part is added at the top of the zone.</span></span> <span data-ttu-id="7bcd3-117">Vous pouvez le faire glisser vers un autre emplacement de la zone.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-117">You can drag it to a different location in the zone.</span></span>  
  
6.  <span data-ttu-id="7bcd3-118">Dans la visionneuse, cliquez sur **Cliquez ici pour ouvrir le volet d’outils**.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-118">Within the viewer, click **Click here to open the tool pane**.</span></span>  
  
7.  <span data-ttu-id="7bcd3-119">Sélectionnez un rapport dans une bibliothèque de la collection de sites actuelle en cliquant sur le bouton Parcourir (**...**).</span><span class="sxs-lookup"><span data-stu-id="7bcd3-119">Select a report from any library in the current site collection by clicking the browse (**...**) button.</span></span> <span data-ttu-id="7bcd3-120">Vous pouvez également taper l'URL du rapport.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-120">You can also type the report URL.</span></span> <span data-ttu-id="7bcd3-121">Pour déterminer l’URL d’un rapport, cliquez avec le bouton droit sur le rapport, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-121">To determine the URL for any report, right-click the report and select **Properties**.</span></span> <span data-ttu-id="7bcd3-122">Ne cliquez pas sur la flèche orientée vers le bas en regard du rapport ; l'URL du rapport n'est pas indiquée dans la page Afficher les propriétés de l'élément.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-122">Do not click the down arrow next to the report; the report URL is not indicated in the View Properties page of the item.</span></span> <span data-ttu-id="7bcd3-123">Si vous copiez et collez l’URL à partir de la boîte de dialogue **Propriétés** , remplacez l’encodage d’URL « %20 » par un espace (par exemple « Company%20Sales » doit s’écrire « Company Sales »).</span><span class="sxs-lookup"><span data-stu-id="7bcd3-123">If you copy and paste the URL from the **Properties** dialog box, replace the "%20" URL encoding with a space (for example, "Company%20Sales" should be "Company Sales").</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7bcd3-124">Chaque composant WebPart Visionneuse de rapports contient un seul rapport.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-124">Each Report Viewer Web Part contains a single report.</span></span> <span data-ttu-id="7bcd3-125">L'URL doit correspondre au chemin d'accès complet d'un rapport situé sur le site SharePoint actuel ou sur un site inclus dans la même batterie de serveurs ou application Web.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-125">The URL must be the fully qualified path to a report that is on the current SharePoint site, or on a site within the same Web application or farm.</span></span> <span data-ttu-id="7bcd3-126">L'URL doit correspondre à une bibliothèque de documents ou à un dossier situé dans une bibliothèque de documents contenant le rapport.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-126">The URL must resolve to a document library or to a folder within a document library that contains the report.</span></span> <span data-ttu-id="7bcd3-127">L'URL de rapport doit inclure l'extension de fichier .rdl.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-127">The report URL must include the .rdl file extension.</span></span> <span data-ttu-id="7bcd3-128">Si le rapport dépend d'un modèle ou de fichiers de source de données partagée, vous n'avez pas besoin de spécifier ces fichiers dans l'URL.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-128">If the report depends on a model or shared data source files, you do not need to specify those files in the URL.</span></span> <span data-ttu-id="7bcd3-129">Le rapport contient les références aux fichiers nécessaires.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-129">The report contains references to the files it needs.</span></span>  
  
8.  <span data-ttu-id="7bcd3-130">Tant que le volet d'outils est ouvert, vous pouvez définir certaines propriétés afin de modifier l'apparence et la mise en page par défaut.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-130">While the tool pane is open, you can set properties to modify the default appearance and layout.</span></span>  
  
9. <span data-ttu-id="7bcd3-131">Cliquez au bas du volet d’outils sur **Appliquer** , puis sur **OK** pour fermer le volet.</span><span class="sxs-lookup"><span data-stu-id="7bcd3-131">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bcd3-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7bcd3-132">See Also</span></span>  
 <span data-ttu-id="7bcd3-133">[Composant WebPart Visionneuse de rapports sur un site SharePoint](../report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="7bcd3-133">[Report Viewer Web Part on a SharePoint Site](../report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 <span data-ttu-id="7bcd3-134">[Personnaliser le composant WebPart Visionneuse de rapports](../customize-the-report-viewer-web-part.md) </span><span class="sxs-lookup"><span data-stu-id="7bcd3-134">[Customize the Report Viewer Web Part](../customize-the-report-viewer-web-part.md) </span></span>  
 <span data-ttu-id="7bcd3-135">[Octroi d’autorisations sur des éléments de serveur de rapports sur un site SharePoint](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="7bcd3-135">[Granting Permissions on Report Server Items on a SharePoint Site](../security/granting-permissions-on-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="7bcd3-136">Installer ou désinstaller le complément Reporting Services pour SharePoint &#40;SharePoint 2010 et SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="7bcd3-136">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](../install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
