---
title: Ajouter des types de contenu de serveur de rapports à une bibliothèque (Reporting Services en mode intégré SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ac9136c8-9ef4-484c-8e9d-05008a186db5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9e0ee56c235a54920fba5389a61f300eeaa65329
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707312"
---
# <a name="add-report-server-content-types-to-a-library-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="d93cd-102">Ajouter des types de contenu de serveur de rapports à une bibliothèque (Reporting Services en mode intégré SharePoint)</span><span class="sxs-lookup"><span data-stu-id="d93cd-102">Add Report Server Content Types to a Library (Reporting Services in SharePoint Integrated Mode)</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="d93cd-103">fournit des types de contenu prédéfinis SharePoint qui sont utilisés pour gérer les fichiers de sources de données partagées (.rsds), les modèles de rapports (.smdl) et les fichiers de définitions de rapports (.rdl) du Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d93cd-103">provides predefined SharePoint content types that are used to manage shared data source (.rsds) files, report models (.smdl), and Report Builder report definition (.rdl) files.</span></span> <span data-ttu-id="d93cd-104">L'ajout à une bibliothèque des types de contenu **Rapport du Générateur de rapports**, **Modèle de rapport**et **Source de données du rapport** active la commande **Nouveau** , qui permet de créer de nouveaux documents de ce type.</span><span class="sxs-lookup"><span data-stu-id="d93cd-104">Adding a **Report Builder Report**, **Report Model**, and **Report Data Source** content type to a library enables the **New** command so that you can create new documents of that type.</span></span>  
  
 <span data-ttu-id="d93cd-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="d93cd-105">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>  
  
 <span data-ttu-id="d93cd-106">Pour ajouter des types de contenu à une bibliothèque, vous devez être administrateur de site ou bénéficier du niveau d'autorisation Contrôle total.</span><span class="sxs-lookup"><span data-stu-id="d93cd-106">To add content types to a library, you must be a site administrator or have Full Control level of permission.</span></span>  
  
 <span data-ttu-id="d93cd-107">Les types de contenu et la gestion des types de contenu [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] seront automatiquement activés dans toutes les bibliothèques de documents pour les collections de sites existantes créées à partir du modèle de site **Business Intelligence Center** suivant :</span><span class="sxs-lookup"><span data-stu-id="d93cd-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types and content type management will automatically be enabled in all document libraries for existing site collections created from the following **Business Intelligence Center** site template.</span></span>  
  
 <span data-ttu-id="d93cd-108">Les sites créés après l'intégration de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] n'auront pas les types de contenu [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] activés.</span><span class="sxs-lookup"><span data-stu-id="d93cd-108">Sites created after the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration will not have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types enabled.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="d93cd-109">Si vous **n'avez pas** configuré au préalable les types de contenus d'une bibliothèque, commencez par activer la gestion des types de contenu, puis activez les types de contenu [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d93cd-109">If you have **not** previously configured content types for a library, first enable management of content types, then enable the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types.</span></span> <span data-ttu-id="d93cd-110">Reportez-vous aux procédures d'activation de la gestion de type de contenu dans une seule bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="d93cd-110">See the procedures on enabling content type management in a single document library.</span></span>  
  
 <span data-ttu-id="d93cd-111">**Courte vidéo :** [(SSRS) Enabling Content Types in SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w).</span><span class="sxs-lookup"><span data-stu-id="d93cd-111">**Short video:** [(SSRS) Enabling Content Types in SharePoint2010.wmv](http://www.youtube.com/watch?v=yqhm3DrtT1w) (http://www.youtube.com/watch?v=yqhm3DrtT1w).</span></span>  
  
 <span data-ttu-id="d93cd-112">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="d93cd-112">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="d93cd-113">Activer les types de contenu dans toutes les bibliothèques de documents dans un BI Center existant</span><span class="sxs-lookup"><span data-stu-id="d93cd-113">Enable content types in all document libraries in an existing BI center</span></span>](#bkmk_enable_all)  
  
-   [<span data-ttu-id="d93cd-114">Pour activer la gestion des types de contenu pour une bibliothèque de documents (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="d93cd-114">To enable content type management for a single document library (SharePoint 2013)</span></span>](#bkmk_enable_content_management)  
  
-   [<span data-ttu-id="d93cd-115">Pour ajouter des types de contenu Reporting Services (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="d93cd-115">To add Reporting Services content types (SharePoint 2013)</span></span>](#bkmk_add_single)  
  
-   [<span data-ttu-id="d93cd-116">Pour activer la gestion des types de contenu pour une bibliothèque de documents (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="d93cd-116">To enable content type management for a single document library (SharePoint 2010)</span></span>](#bkmk_enable_content_management_2010)  
  
-   [<span data-ttu-id="d93cd-117">Pour ajouter des types de contenu de serveur de rapports (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="d93cd-117">To add report server content types (SharePoint 2010)</span></span>](#bkmk_add_single_2010)  
  
-   [<span data-ttu-id="d93cd-118">Pour activer les types de contenu et la gestion du contenu pour plusieurs sites BI</span><span class="sxs-lookup"><span data-stu-id="d93cd-118">To enable Content types and content management for multiple BI sites</span></span>](#bkmk_enable_multiple_sites)  
  
##  <a name="enable-content-types-in-all-document-libraries-in-an-existing-bi-center"></a><a name="bkmk_enable_all"></a> <span data-ttu-id="d93cd-119">Activer les types de contenu dans toutes les bibliothèques de documents dans un BI center existant</span><span class="sxs-lookup"><span data-stu-id="d93cd-119">Enable content types in all document libraries in an existing BI center</span></span>  
  
1.  <span data-ttu-id="d93cd-120">Pour activer les types de contenu et la gestion du contenu dans toutes les bibliothèques de documents dans un site **Business Intelligence Center** existant, utilisez la fonction d'intégration [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d93cd-120">To enable the content types and content management in all document libraries in an existing **Business Intelligence Center** site, you can toggle the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] integration feature.</span></span>  
  
2.  <span data-ttu-id="d93cd-121">Allez à **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-121">Go to **Site settings**.</span></span>  
  
    -   <span data-ttu-id="d93cd-122">Dans SharePoint 2013, cliquez sur l'icône **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="d93cd-122">In SharePoint 2013, click the **Settings** icon.</span></span> <span data-ttu-id="d93cd-123">![Paramètres SharePoint](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "Paramètres SharePoint")</span><span class="sxs-lookup"><span data-stu-id="d93cd-123">![SharePoint Settings](https://docs.microsoft.com/analysis-services/analysis-services/media/as-sharepoint2013-settings-gear.gif "SharePoint Settings")</span></span>  
  
    -   <span data-ttu-id="d93cd-124">Dans SharePoint 2010, cliquez sur **Actions du site**, puis sur **Paramètre du site**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-124">In SharePoint 2010, click **Site Actions**, then click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="d93cd-125">Cliquez sur fonctionnalités de la **collection de sites**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-125">Click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="d93cd-126">Recherchez **Fonctionnalité d'intégration Report Server** dans la liste et cliquez sur **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-126">Find the **Report Server Integration Feature** and click **Deactivate**.</span></span>  
  
     <span data-ttu-id="d93cd-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span><span class="sxs-lookup"><span data-stu-id="d93cd-127">![rs_reportserver_integration_active](media/rs-reportserver-integration-active.gif "rs_reportserver_integration_active")</span></span>  
  
5.  <span data-ttu-id="d93cd-128">Actualisez le navigateur, puis cliquez sur **Activer** pour la **Fonctionnalité d'intégration Report Server**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-128">Refresh the browser then click **Activate** for the **Report Server Integration Feature**.</span></span>  
  
    <span data-ttu-id="d93cd-129">![Désactivation](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span><span class="sxs-lookup"><span data-stu-id="d93cd-129">![Deactivate](media/rs-reportserver-integration-deactivate.gif "rs_reportserver_integration_deactive")</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2013"></a><a name="bkmk_enable_content_management"></a><span data-ttu-id="d93cd-130">Pour activer la gestion des types de contenu pour une seule bibliothèque de documents (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="d93cd-130">To enable content type management for a single document library (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="d93cd-131">Ouvrez la bibliothèque pour laquelle activer plusieurs types de contenu.</span><span class="sxs-lookup"><span data-stu-id="d93cd-131">Open the library for which you want to enable multiple content types.</span></span>  
  
2.  <span data-ttu-id="d93cd-132">Dans le ruban, cliquez sur **Bibliothèque** .</span><span class="sxs-lookup"><span data-stu-id="d93cd-132">Click **Library** in the ribbon.</span></span>  
  
     <span data-ttu-id="d93cd-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span><span class="sxs-lookup"><span data-stu-id="d93cd-133">![rs_SharePoint2013_LibraryRibbon](media/rs-sharepoint2013-libraryribbon.gif "rs_SharePoint2013_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="d93cd-134">Dans le ruban **Bibliothèque** , cliquez sur **Paramètres de la bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-134">On the **Library** ribbon, click **Library Settings**.</span></span> <span data-ttu-id="d93cd-135">Si **Paramètres de la bibliothèque** n'est pas visible, ou si le bouton est désactivé, vous n'êtes pas autorisé à configurer les paramètres de la bibliothèque, ni les types de contenu.</span><span class="sxs-lookup"><span data-stu-id="d93cd-135">If you do not see **Library Settings** or the button is disabled, you do not have permission to configure library settings, including content types.</span></span>  
  
     <span data-ttu-id="d93cd-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span><span class="sxs-lookup"><span data-stu-id="d93cd-136">![rs_SharePoint2013_LibrarySettings](media/rs-sharepoint2013-librarysettings.gif "rs_SharePoint2013_LibrarySettings")</span></span>  
  
4.  <span data-ttu-id="d93cd-137">Dans la section **Paramètres généraux** , cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-137">In the **General Settings** section, click **Advanced settings**.</span></span>  
  
     <span data-ttu-id="d93cd-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span><span class="sxs-lookup"><span data-stu-id="d93cd-138">![rs_SharePoint2013_LibrarySettings_AdvancedSettings](media/rs-sharepoint2013-librarysettings-advancedsettings.gif "rs_SharePoint2013_LibrarySettings_AdvancedSettings")</span></span>  
  
5.  <span data-ttu-id="d93cd-139">Dans la section **Types de contenu** , sélectionnez **Oui** pour autoriser la gestion des types de contenu.</span><span class="sxs-lookup"><span data-stu-id="d93cd-139">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="d93cd-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-140">Click **OK**.</span></span>  
  
##  <a name="to-add-reporting-services-content-types-sharepoint-2013"></a><a name="bkmk_add_single"></a> <span data-ttu-id="d93cd-141">Pour ajouter des types de contenu Reporting Services (SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="d93cd-141">To add Reporting Services content types (SharePoint 2013)</span></span>  
  
1.  <span data-ttu-id="d93cd-142">Ouvrez la bibliothèque pour laquelle vous voulez ajouter des types de contenu Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d93cd-142">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="d93cd-143">Dans le ruban, cliquez sur **Bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-143">On the ribbon, click **Library**.</span></span>  
  
3.  <span data-ttu-id="d93cd-144">Cliquez sur **Paramètres de la bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-144">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="d93cd-145">Sous **Types de contenu**, cliquez sur **Ajouter à partir de types de contenu de site existants**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-145">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="d93cd-146">Dans **Sélectionner des types de contenu dans**, sélectionnez **Types de contenu SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-146">In **Select site content types from**, select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="d93cd-147">Dans la liste **Types de contenu de site disponibles** , cliquez sur **Générateur de rapports**, puis sur **Ajouter** pour déplacer le type de contenu sélectionné dans la liste **Type de contenu à ajouter** .</span><span class="sxs-lookup"><span data-stu-id="d93cd-147">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="d93cd-148">Pour ajouter les types de contenu **Modèle de rapport** et **Source de données du rapport** , répétez l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="d93cd-148">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="d93cd-149">Lorsque vous avez terminé d'ajouter les types de contenu, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-149">When you finish adding content types, click **OK**.</span></span>  
  
9. > [!NOTE]  
    >  <span data-ttu-id="d93cd-150"> Si le groupe de types de contenu [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]**Types de contenu SQL Server Reporting Services** n'est pas visible dans la page **Ajouter des types de contenu** , l'une des conditions suivantes est remplie :</span><span class="sxs-lookup"><span data-stu-id="d93cd-150">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content type group **SQL Server Reporting Services Content Types** is not visible on the **Add Content Types** page, one of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="d93cd-151">Le complément [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pour les produits SharePoint n'est pas installé.</span><span class="sxs-lookup"><span data-stu-id="d93cd-151">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint products has not been installed.</span></span> <span data-ttu-id="d93cd-152">Pour plus d’informations, consultez [installer ou désinstaller le complément Reporting Services pour sharepoint &#40;sharepoint 2010 et sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="d93cd-152">For more information, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span> <span data-ttu-id="d93cd-153">Cette rubrique contient des informations sur l'installation du complément et les étapes de l'installation uniquement des fichiers du complément afin de contourner les problèmes.</span><span class="sxs-lookup"><span data-stu-id="d93cd-153">The topic includes information on installing the add-in and stepping through a files only installation of the add-in to work around issues.</span></span>  
  
    -   <span data-ttu-id="d93cd-154">Le complément est installé, mais la fonctionnalité de collection de sites **Fonctionnalité d’intégration du serveur de rapports** n’est pas active.</span><span class="sxs-lookup"><span data-stu-id="d93cd-154">The add-in is installed but the site collection feature **Report Server Integration Feature** is not active.</span></span> <span data-ttu-id="d93cd-155">Vérifiez la fonctionnalité de collection de sites dans **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-155">Verify the site collection feature in **Site Settings**.</span></span>  
  
    -   <span data-ttu-id="d93cd-156">Tous les types de contenu [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ont déjà été ajoutés à la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="d93cd-156">All of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types have already been added to the library.</span></span> <span data-ttu-id="d93cd-157">Si tous les types de contenu font partie de la bibliothèque, alors le groupe est supprimé de la page **Ajouter des types de contenu** .</span><span class="sxs-lookup"><span data-stu-id="d93cd-157">If all the content types are part of a library, then the group is removed from the **Add Content Types** page.</span></span> <span data-ttu-id="d93cd-158">Si vous supprimez un ou plusieurs types de contenu [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , alors le groupe **Types de contenu SQL Server Reporting Services** est visible sur la page **Ajouter des types de contenu** .</span><span class="sxs-lookup"><span data-stu-id="d93cd-158">If you delete one or more of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] content types, then the group **SQL Server Reporting Services Content Types** will be visible on the **Add Content Types** page.</span></span>  
  
##  <a name="to-enable-content-type-management-for-a-single-document-library-sharepoint-2010"></a><a name="bkmk_enable_content_management_2010"></a><span data-ttu-id="d93cd-159">Pour activer la gestion des types de contenu pour une seule bibliothèque de documents (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="d93cd-159">To enable content type management for a single document library (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="d93cd-160">Ouvrez la bibliothèque pour laquelle activer plusieurs types de contenu.</span><span class="sxs-lookup"><span data-stu-id="d93cd-160">Open the library for which you want to enable multiple content types.</span></span> <span data-ttu-id="d93cd-161">Dans la barre de menus de la bibliothèque, vous devez voir les menus suivants : **Nouveau**, **Télécharger**, **Actions**et **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-161">On the library menu bar, you should see the following menus: **New**, **Upload**, **Actions**, and **Settings**.</span></span> <span data-ttu-id="d93cd-162">Si le menu **Paramètres**n'est pas visible, vous n'êtes pas autorisé à ajouter un type de contenu.</span><span class="sxs-lookup"><span data-stu-id="d93cd-162">If you do not see **Settings**, you do not have permission to add a content type.</span></span>  
  
2.  <span data-ttu-id="d93cd-163">Dans le ruban **Outils de bibliothèque** , cliquez sur **Bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-163">On the **Library Tools** ribbon, click **Library**.</span></span>  
  
     <span data-ttu-id="d93cd-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span><span class="sxs-lookup"><span data-stu-id="d93cd-164">![rs_SharePoint2010_LibraryRibbon](media/rs-sharepoint2010-libraryribbon.gif "rs_SharePoint2010_LibraryRibbon")</span></span>  
  
3.  <span data-ttu-id="d93cd-165">Dans le groupe du ruban **Paramètres** , cliquez sur **Paramètres de la bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-165">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="d93cd-166">Sous **Paramètres généraux**, cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-166">Under **General Settings**, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="d93cd-167">Dans la section **Types de contenu** , sélectionnez **Oui** pour autoriser la gestion des types de contenu.</span><span class="sxs-lookup"><span data-stu-id="d93cd-167">In the **Content Types** section, select **Yes** to allow management of content types.</span></span>  
  
6.  <span data-ttu-id="d93cd-168">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-168">Click **OK**.</span></span>  
  
##  <a name="to-add-report-server-content-types-sharepoint-2010"></a><a name="bkmk_add_single_2010"></a><span data-ttu-id="d93cd-169">Pour ajouter des types de contenu de serveur de rapports (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="d93cd-169">To add report server content types (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="d93cd-170">Ouvrez la bibliothèque pour laquelle vous voulez ajouter des types de contenu Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d93cd-170">Open the library for which you want to add Reporting Services content types.</span></span>  
  
2.  <span data-ttu-id="d93cd-171">Sous les onglets du ruban **Outils de bibliothèque** , cliquez sur l'onglet **Bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-171">On the **Library Tools** ribbon tabs, click the **Library tab**.</span></span>  
  
3.  <span data-ttu-id="d93cd-172">Dans le groupe du ruban **Paramètres** , cliquez sur **Paramètres de la bibliothèque**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-172">On the **Settings** ribbon group, click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="d93cd-173">Sous **Types de contenu**, cliquez sur **Ajouter à partir de types de contenu de site existants**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-173">Under **Content Types**, click **Add from existing site content types**.</span></span>  
  
5.  <span data-ttu-id="d93cd-174">Dans la section **Sélectionner des types de contenu** , dans **Sélectionner des types de contenu dans**, cliquez sur la flèche pour sélectionner **Types de contenu SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-174">In the **Select Content Types** section, in **Select site content types from**, click the arrow to select **SQL Server Reporting Services Content Types**.</span></span>  
  
6.  <span data-ttu-id="d93cd-175">Dans la liste **Types de contenu de site disponibles** , cliquez sur **Générateur de rapports**, puis sur **Ajouter** pour déplacer le type de contenu sélectionné dans la liste **Type de contenu à ajouter** .</span><span class="sxs-lookup"><span data-stu-id="d93cd-175">In the **Available Site Content Types** list, click **Report Builder**, and then click **Add** to move the selected content type to the **Content types to add** list.</span></span>  
  
7.  <span data-ttu-id="d93cd-176">Pour ajouter les types de contenu **Modèle de rapport** et **Source de données du rapport** , répétez l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="d93cd-176">To add **Report Model** and **Report Data Source** content types, repeat the previous step.</span></span>  
  
8.  <span data-ttu-id="d93cd-177">Lorsque vous avez terminé d'ajouter les types de contenu, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-177">When you finish adding content types, click **OK**.</span></span>  
  
##  <a name="to-enable-content-types-and-content-management-for-multiple-bi-sites"></a><a name="bkmk_enable_multiple_sites"></a><span data-ttu-id="d93cd-178">Pour activer les types de contenu et la gestion du contenu pour plusieurs sites BI</span><span class="sxs-lookup"><span data-stu-id="d93cd-178">To enable Content types and content management for multiple BI sites</span></span>  
  
1.  <span data-ttu-id="d93cd-179">Pour les serveurs de rapports SQL Server Reporting Services 2008 et 2008 R2, vous pouvez activer les types de contenu et la gestion du contenu pour plusieurs sites Business Intelligence Center :</span><span class="sxs-lookup"><span data-stu-id="d93cd-179">For SQL Server Reporting Services 2008 and 2008 R2 report servers, you can enable content types and content management for multiple Business Intelligence Center sites:</span></span>  
  
2.  <span data-ttu-id="d93cd-180">Dans Administration centrale de SharePoint, cliquez sur **Paramètres généraux de l'application**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-180">In SharePoint Central Administration, click **General Applications settings**.</span></span> <span data-ttu-id="d93cd-181">Dans la section **SQL Server Reporting Services (2008 et 2008 R2)** , cliquez sur **Intégration de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-181">In the **SQL Server Reporting Services (2008 and 2008 R2)** section, click **Reporting Services Integration**.</span></span>  
  
     <span data-ttu-id="d93cd-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span><span class="sxs-lookup"><span data-stu-id="d93cd-182">![rs_general_app_settings](media/rs-general-app-settings.gif "rs_general_app_settings")</span></span>  
  
3.  <span data-ttu-id="d93cd-183">Cliquez sur **Activer la fonctionnalité dans toutes les collections de sites existantes**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-183">Click **Activate feature in all exciting site collections**.</span></span>  
  
     <span data-ttu-id="d93cd-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span><span class="sxs-lookup"><span data-stu-id="d93cd-184">![rs_general_app_settings_old_integrations](media/rs-general-app-settings-old-integrations.gif "rs_general_app_settings_old_integrations")</span></span>  
  
4.  <span data-ttu-id="d93cd-185">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d93cd-185">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d93cd-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d93cd-186">See Also</span></span>  
 <span data-ttu-id="d93cd-187">[Informations de référence sur les autorisations de liste et de site SharePoint pour les éléments de serveur de rapports](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="d93cd-187">[SharePoint Site and List Permission Reference for Report Server Items](security/sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="d93cd-188">Démarrer Générateur de rapports &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="d93cd-188">Start Report Builder &#40;Report Builder&#41;</span></span>](report-builder/start-report-builder.md)  
  
  
