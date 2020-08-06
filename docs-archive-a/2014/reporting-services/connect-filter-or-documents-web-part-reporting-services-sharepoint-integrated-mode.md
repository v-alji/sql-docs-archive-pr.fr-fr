---
title: Connecter un composant WebPart de filtre ou de documents (Reporting Services en mode intégré SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Filter Web Part [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
- Documents Web Part [Reporting Services]
ms.assetid: 6a303135-c0ef-44cd-a423-1cea8df3dcf3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5ea7b9f9aba128052ae6ac7f05ef40517eb50e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602785"
---
# <a name="connect-filter-or-documents-web-part-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="9abd7-102">Connecter un composant WebPart de filtre ou de documents (Reporting Services en mode intégré SharePoint)</span><span class="sxs-lookup"><span data-stu-id="9abd7-102">Connect Filter or Documents Web Part (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="9abd7-103">Si vous utilisez un produit SharePoint, vous pouvez créer un tableau de bord ou une page WebPart qui inclut un composant WebPart de filtre ou un composant WebPart de documents et un composant WebPart Visionneuse de rapports.</span><span class="sxs-lookup"><span data-stu-id="9abd7-103">If you are using a SharePoint product, you can create a dashboard or Web Part Page that includes a Filter Web Part or Documents Web part and a Report Viewer Web Part.</span></span> <span data-ttu-id="9abd7-104">Les versions prises en charge sont [!INCLUDE[SPF2010](../includes/spf2010-md.md)] et [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9abd7-104">Supported versions are [!INCLUDE[SPF2010](../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span></span> <span data-ttu-id="9abd7-105">[!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] et [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 sont également pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9abd7-105">Also supported are [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] or [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span></span> <span data-ttu-id="9abd7-106">En connectant un composant WebPart de filtre, les utilisateurs qui sélectionnent des valeurs de filtre dans un composant WebPart de filtre peuvent envoyer la valeur à un rapport paramétrable sur la même page.</span><span class="sxs-lookup"><span data-stu-id="9abd7-106">By connecting a Filter Web Part, users who select filter values in a Filter Web Part can send the value to a parameterized report on the same page.</span></span> <span data-ttu-id="9abd7-107">En connectant un composant WebPart de documents, les utilisateurs qui cliquent sur des rapports dans la bibliothèque de documents peuvent afficher les rapports dans un composant WebPart de visionneuse de rapports adjacent.</span><span class="sxs-lookup"><span data-stu-id="9abd7-107">By connecting a Documents Web Part, users who click on reports in the Documents library can view the report in an adjacent Report Viewer Web Part.</span></span>  
  
 <span data-ttu-id="9abd7-108">Le composant WebPart de filtre sert à envoyer des valeurs à un ou plusieurs paramètres d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="9abd7-108">The Filter Web Part is used to send values to one or more parameters on a report.</span></span> <span data-ttu-id="9abd7-109">Pour utiliser un composant WebPart de filtre, le rapport doit disposer de paramètres concernant ce composant qui sont compatibles avec les valeurs, le type de données et le format envoyés par le composant WebPart.</span><span class="sxs-lookup"><span data-stu-id="9abd7-109">To use a Filter Web Part, the report must have parameters defined for it that are compatible with the values, data type, and format sent by the Web Part.</span></span>  
  
 <span data-ttu-id="9abd7-110">Le composant WebPart de documents est associé à la bibliothèque de documents du site d'accueil.</span><span class="sxs-lookup"><span data-stu-id="9abd7-110">The Documents Web Part is associated with the Documents library of the Home site.</span></span> <span data-ttu-id="9abd7-111">Pour afficher, ajouter ou supprimer des éléments de la bibliothèque de documents, cliquez sur **Afficher tout le contenu du site**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-111">To view, add, or remove items from the Documents library, click **View All Site Content**.</span></span> <span data-ttu-id="9abd7-112">Dans Bibliothèques, cliquez sur **Documents**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-112">In Libraries, click **Documents**.</span></span> <span data-ttu-id="9abd7-113">Vous pouvez utiliser les menus **Nouveau**, **Télécharger**et **Actions** pour gérer les éléments de la bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="9abd7-113">You can use the **New**, **Upload**, and **Actions** menu to manage the items in the Documents library.</span></span>  
  
### <a name="to-connect-a-filter-web-part"></a><span data-ttu-id="9abd7-114">Pour connecter un composant WebPart de filtre</span><span class="sxs-lookup"><span data-stu-id="9abd7-114">To connect a Filter Web Part</span></span>  
  
1.  <span data-ttu-id="9abd7-115">Ouvrez ou créez la page ou le tableau de bord de composant WebPart.</span><span class="sxs-lookup"><span data-stu-id="9abd7-115">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="9abd7-116">Dans le menu **Actions de site** , cliquez sur **Modifier la page**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-116">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="9abd7-117">Cliquez sur **Ajouter un composant WebPart**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-117">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="9abd7-118">Dans **tous les composants WebPart**, dans la catégorie **divers** , sélectionnez **SQL Server Reporting Services visionneuse de rapports**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-118">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="9abd7-119">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-119">Click **Add**.</span></span> <span data-ttu-id="9abd7-120">Le composant WebPart est ajouté en haut de la zone.</span><span class="sxs-lookup"><span data-stu-id="9abd7-120">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="9abd7-121">Dans une autre zone de la même page ou du même tableau de bord de composant WebPart, cliquez sur **Ajouter un composant WebPart**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-121">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
7.  <span data-ttu-id="9abd7-122">Dans **tous les composants WebPart**, dans la section **filtres** , sélectionnez un composant WebPart.</span><span class="sxs-lookup"><span data-stu-id="9abd7-122">In **All Web Parts**, in the **Filters** section, select a Web Part.</span></span>  
  
8.  <span data-ttu-id="9abd7-123">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-123">Click **Add**.</span></span> <span data-ttu-id="9abd7-124">Le composant WebPart est ajouté en haut de la zone.</span><span class="sxs-lookup"><span data-stu-id="9abd7-124">The Web Part is added at the top of the zone.</span></span>  
  
9. <span data-ttu-id="9abd7-125">Dans la zone qui contient le composant WebPart, cliquez sur le menu **modifier** du composant WebPart, pointez sur **Connexions**, sur **Envoyer les valeurs de filtre à**, puis sélectionnez **Visionneuse de rapports** - *nom de rapport*.</span><span class="sxs-lookup"><span data-stu-id="9abd7-125">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Send Filter Values To**, and then select **Report Viewer** - *report name*.</span></span>  
  
10. <span data-ttu-id="9abd7-126">Vérifiez vos modifications et enregistrez la page.</span><span class="sxs-lookup"><span data-stu-id="9abd7-126">Check in your changes and save the page.</span></span>  
  
### <a name="to-connect-a-documents-web-part"></a><span data-ttu-id="9abd7-127">Pour connecter un composant WebPart de documents</span><span class="sxs-lookup"><span data-stu-id="9abd7-127">To connect a Documents Web Part</span></span>  
  
1.  <span data-ttu-id="9abd7-128">Ouvrez ou créez la page ou le tableau de bord de composant WebPart.</span><span class="sxs-lookup"><span data-stu-id="9abd7-128">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="9abd7-129">Dans le menu **Actions de site** , cliquez sur **Modifier la page**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-129">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="9abd7-130">Cliquez sur **Ajouter un composant WebPart**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-130">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="9abd7-131">Dans **Tous les composants WebPart**, dans la section **Listes et bibliothèque** , sélectionnez **Documents**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-131">In **All Web Parts**, in the **Lists and Library** section, select **Documents.**</span></span>  
  
5.  <span data-ttu-id="9abd7-132">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-132">Click **Add**.</span></span> <span data-ttu-id="9abd7-133">Le composant WebPart est ajouté en haut de la zone.</span><span class="sxs-lookup"><span data-stu-id="9abd7-133">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="9abd7-134">Cliquez au bas du volet d’outils sur **Appliquer** , puis sur **OK** pour fermer le volet.</span><span class="sxs-lookup"><span data-stu-id="9abd7-134">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
7.  <span data-ttu-id="9abd7-135">Dans une autre zone de la même page ou du même tableau de bord de composant WebPart, cliquez sur **Ajouter un composant WebPart**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-135">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
8.  <span data-ttu-id="9abd7-136">Dans **Tous les composants WebPart**, dans la catégorie **Divers** , sélectionnez **Visionneuse de rapports SQL Server Reporting Services.**</span><span class="sxs-lookup"><span data-stu-id="9abd7-136">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer.**</span></span>  
  
9. <span data-ttu-id="9abd7-137">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-137">Click **Add**.</span></span> <span data-ttu-id="9abd7-138">Le composant WebPart est ajouté en haut de la zone.</span><span class="sxs-lookup"><span data-stu-id="9abd7-138">The Web Part is added at the top of the zone.</span></span>  
  
10. <span data-ttu-id="9abd7-139">Dans la zone qui contient le composant WebPart, cliquez sur le menu **modifier** du composant WebPart, pointez sur **Connexions**, sur **Source des définitions de rapport**, puis sélectionnez **Documents**.</span><span class="sxs-lookup"><span data-stu-id="9abd7-139">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Get report definitions from**, and then select **Documents**.</span></span>  
  
11. <span data-ttu-id="9abd7-140">Vérifiez vos modifications et enregistrez la page.</span><span class="sxs-lookup"><span data-stu-id="9abd7-140">Check in your changes and save the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9abd7-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9abd7-141">See Also</span></span>  
 <span data-ttu-id="9abd7-142">[Ajoutez le composant WebPart Visionneuse de rapports à une page Web &#40;Reporting Services en mode intégré SharePoint&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="9abd7-142">[Add the Report Viewer Web Part to a Web Page &#40;Reporting Services in SharePoint Integrated Mode&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="9abd7-143">[Composant WebPart Visionneuse de rapports sur un site SharePoint](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="9abd7-143">[Report Viewer Web Part on a SharePoint Site](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="9abd7-144">Personnaliser le composant WebPart Visionneuse de rapports</span><span class="sxs-lookup"><span data-stu-id="9abd7-144">Customize the Report Viewer Web Part</span></span>](../../2014/reporting-services/customize-the-report-viewer-web-part.md)  
  
  
