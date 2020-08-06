---
title: Afficher des rapports d’Reporting Services sur des appareils Microsoft surface et Apple iOS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- iPad
- Safari
- SSRS
- Report Viewer [Reporting Services]
- iOS
ms.assetid: 2124bcf5-d60a-475f-a4ae-de6df44d2860
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db52ed500559969ae52eb9477caa6b410889c1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612159"
---
# <a name="view-reporting-services-reports-on-microsoft-surface-devices-and--apple-ios-devices"></a><span data-ttu-id="3694a-102">Afficher des rapports Reporting Services sur des appareils Microsoft Surface et Apple iOS</span><span class="sxs-lookup"><span data-stu-id="3694a-102">View Reporting Services Reports on Microsoft Surface Devices and  Apple iOS Devices</span></span>
  <span data-ttu-id="3694a-103">Cet article décrit les fonctionnalités et les flux de travail de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pris en charge pour les appareils Microsoft Surface ainsi que les appareils utilisant Apple iOS 6 et Apple Safari, tels que les iPad.</span><span class="sxs-lookup"><span data-stu-id="3694a-103">This article describes the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features and workflows supported for Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari such as the iPad.</span></span>

## <a name="view-and-interact-with-reports"></a><span data-ttu-id="3694a-104">Afficher et interagir avec les rapports</span><span class="sxs-lookup"><span data-stu-id="3694a-104">View and Interact With Reports</span></span>
 <span data-ttu-id="3694a-105">À compter de [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] prend en charge l'affichage et l'interactivité de base sur les appareils Microsoft Surface et les appareils utilisant Apple iOS et le navigateur Apple Safari, tels que les iPad.</span><span class="sxs-lookup"><span data-stu-id="3694a-105">Starting with [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] supports viewing and basic interactivity with reports on Microsoft Surface devices, and devices with Apple iOS 6 and Apple Safari browser such as the iPad.</span></span> <span data-ttu-id="3694a-106">Vous pouvez également publier des rapports à l'aide d'appareils Microsoft Surface.</span><span class="sxs-lookup"><span data-stu-id="3694a-106">You can also publish reports using Microsoft Surface devices.</span></span>

 <span data-ttu-id="3694a-107">![Bureau](media/videothumbnail.jpg "Bureau IPad") de l’iPad Regardez une démonstration de l’affichage des rapports sur un iPad.</span><span class="sxs-lookup"><span data-stu-id="3694a-107">![IPad Desktop](media/videothumbnail.jpg "IPad Desktop") Watch a demonstration of viewing reports on an iPad.</span></span>

 <span data-ttu-id="3694a-108">Vous pouvez également afficher des rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] sur un appareil Windows Phone 8.</span><span class="sxs-lookup"><span data-stu-id="3694a-108">You can also view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports on a Windows Phone 8 device.</span></span>

 <span data-ttu-id="3694a-109">Pour utiliser les fonctionnalités décrites dans cette rubrique, installez l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3694a-109">To utilize the features described in this topic, install one of the following:</span></span>

-   <span data-ttu-id="3694a-110">Pour un serveur de rapports en mode natif, installez [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="3694a-110">For a native mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later.</span></span>

     [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)]<span data-ttu-id="3694a-111">peut être téléchargé à partir du [Centre de téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=35575).</span><span class="sxs-lookup"><span data-stu-id="3694a-111">is available for download from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=35575).</span></span>

-   <span data-ttu-id="3694a-112">Pour un serveur de rapports en mode SharePoint, installez [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] ou version ultérieure du complément de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pour les produits SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3694a-112">For a SharePoint mode report server, install [!INCLUDE[ssSQL11SP1long](../includes/sssql11sp1long-md.md)] or later of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span>

 <span data-ttu-id="3694a-113">**Pour afficher un rapport et interagir avec sur votre iPad ou votre appareil Microsoft Surface**</span><span class="sxs-lookup"><span data-stu-id="3694a-113">**To view and interact with a report on an iPad device or Microsoft Surface device**</span></span>

1.  <span data-ttu-id="3694a-114">Vérifiez que vous pouvez vous connecter au serveur de rapports ou au site SharePoint où réside le rapport.</span><span class="sxs-lookup"><span data-stu-id="3694a-114">Make sure that you can connect to the report server or SharePoint site where the report resides.</span></span>

2.  <span data-ttu-id="3694a-115">Ouvrez le rapport en effectuant une des actions suivantes.</span><span class="sxs-lookup"><span data-stu-id="3694a-115">Open the report by doing one of the following.</span></span>

    -   <span data-ttu-id="3694a-116">**Démarrer à partir d’un message électronique :** dans un message électronique qui est créé par un abonnement [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , appuyez sur l’URL du rapport.</span><span class="sxs-lookup"><span data-stu-id="3694a-116">**Start from e-mail:** From an e-mail that is created by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] subscription, tap the URL of the report.</span></span> <span data-ttu-id="3694a-117">Le rapport s'ouvre dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="3694a-117">The report will open in the browser.</span></span>

    -   <span data-ttu-id="3694a-118">**Lancement à partir du serveur de rapports :** Parcourez le répertoire sur le serveur de rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , puis touchez le nom du rapport pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="3694a-118">**Start from Report Server:** Browse the directory on the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server, and then tap the report name to open the report.</span></span>

    -   <span data-ttu-id="3694a-119">**Démarrer à partir d'une bibliothèque de documents SharePoint :** accédez à une bibliothèque de documents SharePoint qui contient les rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , puis touchez le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="3694a-119">**Start from a SharePoint document library:** Browse to a SharePoint document library that contains [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports, and then tap the report name.</span></span> <span data-ttu-id="3694a-120">Vous pouvez afficher et interagir avec le rapport.</span><span class="sxs-lookup"><span data-stu-id="3694a-120">You can view and interact with the report.</span></span>

        > [!IMPORTANT]
        >  <span data-ttu-id="3694a-121"> Pour un iPad, assurez-vous que la propriété **Private Browsing** de Safari est désactivée.</span><span class="sxs-lookup"><span data-stu-id="3694a-121">For the iPad, ensure that the **Private Browsing** property for Safari is turned off.</span></span>

    -   <span data-ttu-id="3694a-122">**Composant WebPart SharePoint :** si le composant WebPart a été ajouté à une page SharePoint, vous pouvez afficher des rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3694a-122">**SharePoint web part:** If the web part has been added to a SharePoint page, you can view [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] reports.</span></span>

3.  <span data-ttu-id="3694a-123">Sur votre appareil Microsoft Surface, vous pouvez également ouvrir le rapport grâce au Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="3694a-123">On your Microsoft Surface device, you can also open the report by using Report Manager.</span></span> <span data-ttu-id="3694a-124">Parcourez le répertoire du Gestionnaire de rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , puis touchez le nom du rapport pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="3694a-124">Browse the directory in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager, and then tap the report name to open the report.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="3694a-125">L'affichage des rapports dans le Gestionnaire de rapports n'est pas pris en charge sur un iPad.</span><span class="sxs-lookup"><span data-stu-id="3694a-125">Viewing reports in Report Manager is not supported on an iPad.</span></span>

4.  <span data-ttu-id="3694a-126">Faites défiler le rapport et zoomez en procédant comme suit.</span><span class="sxs-lookup"><span data-stu-id="3694a-126">Scroll and zoom by doing the following.</span></span>

    -   <span data-ttu-id="3694a-127">Pour faire défiler le rapport, faites glisser votre doigt sur l'écran (vers le haut, vers le bas, à gauche ou à droite).</span><span class="sxs-lookup"><span data-stu-id="3694a-127">To scroll the report, drag your finger across the screen (up, down, left or right).</span></span> <span data-ttu-id="3694a-128">Il s'agit du mouvement de balayage.</span><span class="sxs-lookup"><span data-stu-id="3694a-128">This is the swipe gesture.</span></span>

    -   <span data-ttu-id="3694a-129">Pour effectuer un zoom avant, placez deux doigts sur l'écran et séparez-les.</span><span class="sxs-lookup"><span data-stu-id="3694a-129">To zoom in, place two fingers on the screen and separate the fingers.</span></span> <span data-ttu-id="3694a-130">Pour effectuer un zoom arrière, placez deux doigts sur l'écran et rapprochez-les.</span><span class="sxs-lookup"><span data-stu-id="3694a-130">To zoom out, place two fingers on the screen and move the fingers together.</span></span> <span data-ttu-id="3694a-131">Il s'agit du mouvement de pincement.</span><span class="sxs-lookup"><span data-stu-id="3694a-131">This is the pinch gesture.</span></span>

5.  <span data-ttu-id="3694a-132">Parcourez le rapport et interagissez avec lui en procédant comme suit.</span><span class="sxs-lookup"><span data-stu-id="3694a-132">Navigate and interact with the report by doing the following.</span></span>

    -   <span data-ttu-id="3694a-133">Réduisez et développez les éléments du rapport, les lignes et les colonnes associées à des groupes, en touchant le signe plus (+) pour réduire et le signe moins (-) pour développer.</span><span class="sxs-lookup"><span data-stu-id="3694a-133">Collapse and expand report items, and rows and columns that are associated with groups, by taping the plus (+) sign to collapse and the minus (-) sign to expand.</span></span>

    -   <span data-ttu-id="3694a-134">Inversez l'ordre croissant et décroissant des lignes dans une table ou des lignes et des colonnes dans une matrice, en touchant le bouton de tri.</span><span class="sxs-lookup"><span data-stu-id="3694a-134">Toggle between ascending and descending order for rows in a table or for rows and columns in a matrix, by tapping the sort button.</span></span> <span data-ttu-id="3694a-135">Le bouton de tri est généralement situé dans l'en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="3694a-135">The sort button is usually located in the column header.</span></span>

    -   <span data-ttu-id="3694a-136">Développez et réduisez le volet des paramètres, en touchant le bouton fléché en haut du rapport.</span><span class="sxs-lookup"><span data-stu-id="3694a-136">Expand and collapse the parameter pane, by tapping the arrow button near the top of the report.</span></span>

    -   <span data-ttu-id="3694a-137">Sélectionnez une valeur de paramètre en touchant la zone ou le contrôle en regard du paramètre.</span><span class="sxs-lookup"><span data-stu-id="3694a-137">Select a parameter value by tapping the box or control next to the parameter.</span></span> <span data-ttu-id="3694a-138">Touchez **Afficher le rapport** pour appliquer la valeur de paramètre au rapport.</span><span class="sxs-lookup"><span data-stu-id="3694a-138">Tap **View Report** to apply the parameter value to the report.</span></span>

    -   <span data-ttu-id="3694a-139">Recherchez le contenu du rapport en touchant la case à cocher située en regard de **Rechercher**, entrez un terme de recherche, puis touchez **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="3694a-139">Search the report content by taping the box next to **Find**, typing a search term, and then taping **Find**.</span></span>

    -   <span data-ttu-id="3694a-140">Parcourez les pages du rapport en touchant les boutons de navigation, ou en touchant la zone de texte en regard des boutons et en tapant le numéro de page.</span><span class="sxs-lookup"><span data-stu-id="3694a-140">Navigate the report pages by tapping the navigation buttons, or tapping the text box next to the buttons and typing the page number.</span></span>

    -   <span data-ttu-id="3694a-141">Accédez aux URL en touchant les liens hypertexte qui ont été ajoutés aux éléments du rapport, tels que les zones de texte, les images, les graphiques, les jauges.</span><span class="sxs-lookup"><span data-stu-id="3694a-141">Navigate to URLs by taping hyperlinks that have been added to report items such as text boxes, images, charts, and gauges.</span></span>

    -   <span data-ttu-id="3694a-142">Exportez le rapport en touchant l'icône du **menu déroulant Exporter** , puis en touchant un format de fichier.</span><span class="sxs-lookup"><span data-stu-id="3694a-142">Export the report by tapping the icon for the **Export drop down menu** and then tapping a file format.</span></span>

        -   <span data-ttu-id="3694a-143">Si vous affichez le rapport sur un appareil Microsoft surface, vous pouvez exporter le rapport dans l’un des formats suivants.</span><span class="sxs-lookup"><span data-stu-id="3694a-143">If you're viewing the report on a Microsoft Surface device, you can export the report to one of the following formats.</span></span>

            -   <span data-ttu-id="3694a-144">Fichier XML avec données de rapport</span><span class="sxs-lookup"><span data-stu-id="3694a-144">XML file with report data</span></span>

            -   <span data-ttu-id="3694a-145">CSV (délimité par des virgules)</span><span class="sxs-lookup"><span data-stu-id="3694a-145">CSV (comma delimited)</span></span>

            -   <span data-ttu-id="3694a-146">PDF</span><span class="sxs-lookup"><span data-stu-id="3694a-146">PDF</span></span>

            -   <span data-ttu-id="3694a-147">MHTML (archive Web)</span><span class="sxs-lookup"><span data-stu-id="3694a-147">MHTML (web archive)</span></span>

            -   <span data-ttu-id="3694a-148">Excel</span><span class="sxs-lookup"><span data-stu-id="3694a-148">Excel</span></span>

            -   <span data-ttu-id="3694a-149">TIFF</span><span class="sxs-lookup"><span data-stu-id="3694a-149">TIFF</span></span>

            -   <span data-ttu-id="3694a-150">Word</span><span class="sxs-lookup"><span data-stu-id="3694a-150">Word</span></span>

        -   <span data-ttu-id="3694a-151">Si vous affichez le rapport sur un iPad, vous pouvez exporter le rapport en tant que fichier TIFF ou PDF.</span><span class="sxs-lookup"><span data-stu-id="3694a-151">If you're viewing the report on an iPad, you can export the report as a TIFF or PDF file.</span></span>

## <a name="authentication"></a><span data-ttu-id="3694a-152">Authentification</span><span class="sxs-lookup"><span data-stu-id="3694a-152">Authentication</span></span>
 <span data-ttu-id="3694a-153">L'authentification RSWindowsNTLM et l'authentification RSWindowsBasic fonctionnent avec [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] en mode natif et avec l'iPad.</span><span class="sxs-lookup"><span data-stu-id="3694a-153">RSWindowsNTLM authentication and RSWindowsBasic authentication work with [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode and the iPad.</span></span>

 <span data-ttu-id="3694a-154">En général, il est recommandé de ne pas utiliser RSWindowsBasic dans un environnement autre que https car ce type d'authentification ne garantit pas la confidentialité des informations de connexion transmises.</span><span class="sxs-lookup"><span data-stu-id="3694a-154">In general, it is recommended that RSWindowsBasic is not used in non-https environments because this type of authentication provides no confidentiality for the transmitted credentials.</span></span>

 <span data-ttu-id="3694a-155">Pour plus d'informations sur l'authentification RSWindowsNTLM et RSWindowsBasic, consultez [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="3694a-155">For more information about RSWindowsNTLM and RSWindowsBasic authentication, see [Authentication with the Report Server](security/authentication-with-the-report-server.md).</span></span>

## <a name="uploading-reports"></a><span data-ttu-id="3694a-156">Téléchargement de rapports</span><span class="sxs-lookup"><span data-stu-id="3694a-156">Uploading Reports</span></span>
 <span data-ttu-id="3694a-157">Publiez des rapports à partir d'un appareil Microsoft Surface à l'aide des méthodes suivantes, si vous disposez des autorisations appropriées.</span><span class="sxs-lookup"><span data-stu-id="3694a-157">You can publish reports from a Microsoft Surface device using one of the following methods, if you have the appropriate permissions.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="3694a-158">Ces méthodes ne sont pas prises en charge sur un iPad.</span><span class="sxs-lookup"><span data-stu-id="3694a-158">These methods are not supported on the iPad.</span></span>

-   <span data-ttu-id="3694a-159">Téléchargez un fichier de définition de rapport (.rdl) dans une bibliothèque de documents SharePoint en ouvrant la bibliothèque et en touchant **Télécharger un document**.</span><span class="sxs-lookup"><span data-stu-id="3694a-159">Upload a report definition file (.rdl) to a SharePoint document library by opening the library and tapping **Upload Document**.</span></span>

-   <span data-ttu-id="3694a-160">Téléchargez un fichier de définition de rapport dans la base de données du serveur de rapports en ouvrant le Gestionnaire de rapports et en touchant **Télécharger un fichier**.</span><span class="sxs-lookup"><span data-stu-id="3694a-160">Upload a report definition file to the report server database by opening Report Manager and tapping **Upload File**.</span></span>

## <a name="additional-information"></a><span data-ttu-id="3694a-161">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3694a-161">Additional Information</span></span>
 <span data-ttu-id="3694a-162">Pour plus d'informations sur [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] et les navigateurs pris en charge, consultez :</span><span class="sxs-lookup"><span data-stu-id="3694a-162">For more information on [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and supported browsers, see:</span></span>

-   [<span data-ttu-id="3694a-163">Planification de la prise en charge des navigateurs Reporting Services et Power View &#40;Reporting Services 2014&#41;</span><span class="sxs-lookup"><span data-stu-id="3694a-163">Planning for Reporting Services and Power View Browser Support &#40;Reporting Services 2014&#41;</span></span>](../../2014/reporting-services/browser-support-for-reporting-services-and-power-view.md)

 <span data-ttu-id="3694a-164">Pour plus d'informations sur Microsoft Business Intelligence et les appareils mobiles, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3694a-164">For more information on Microsoft Business Intelligence and Mobile devices, see the following:</span></span>

-   <span data-ttu-id="3694a-165">[Vue d’ensemble des appareils mobiles et SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161351(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="3694a-165">[Overview of mobile devices and SharePoint 2013](https://technet.microsoft.com/library/fp161351\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161351(v=office.15).aspx).</span></span>

-   <span data-ttu-id="3694a-166">[Navigateurs d’appareils mobiles pris en charge dans SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) ( https://technet.microsoft.com/library/fp161353(v=office.15).aspx) .</span><span class="sxs-lookup"><span data-stu-id="3694a-166">[Supported mobile device browsers in SharePoint 2013](https://technet.microsoft.com/library/fp161353\(v=office.15\).aspx) (https://technet.microsoft.com/library/fp161353(v=office.15).aspx).</span></span>

-   <span data-ttu-id="3694a-167">[Affichage des rapports et des tableaux de bord sur les appareils Apple iPad (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) ( https://technet.microsoft.com/library/hh697482.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3694a-167">[Viewing reports and scorecards on Apple iPad devices (SharePoint Server 2010)](https://technet.microsoft.com/library/hh697482.aspx) (https://technet.microsoft.com/library/hh697482.aspx).</span></span>

-   <span data-ttu-id="3694a-168">[Affichage des rapports de Reporting Services sur un iPad (vidéo)](https://technet.microsoft.com/sqlserver/jj873792.aspx) ( https://technet.microsoft.com/sqlserver/jj873792.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3694a-168">[Viewing Reporting Services Reports on an iPad (video)](https://technet.microsoft.com/sqlserver/jj873792.aspx) (https://technet.microsoft.com/sqlserver/jj873792.aspx).</span></span>

-   [<span data-ttu-id="3694a-169">Affichage de rapports Reporting Services sur un appareil Microsoft Surface RT (vidéo)</span><span class="sxs-lookup"><span data-stu-id="3694a-169">Viewing Reporting Services Reports on a Microsoft Surface RT Device (video)</span></span>](https://technet.microsoft.com/sqlserver/dn146017)


