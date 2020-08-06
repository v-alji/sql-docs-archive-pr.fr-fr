---
title: Configurer un serveur de rapports en mode natif pour l’administration locale (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- UAC
- installing Reporting Services
- Windows Vista
- Localhost
- windows server 2008
- Vista
ms.assetid: 312c6bb8-b3f7-4142-a55f-c69ee15bbf52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ad53f293ef825a382d9e39b58527a36ef291687a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611561"
---
# <a name="configure-a-native-mode-report-server-for-local-administration-ssrs"></a><span data-ttu-id="c65f8-102">Configurer un serveur de rapports en mode natif pour l'administration locale (SSRS)</span><span class="sxs-lookup"><span data-stu-id="c65f8-102">Configure a Native Mode Report Server for Local Administration (SSRS)</span></span>
  <span data-ttu-id="c65f8-103">Le déploiement d'un serveur de rapports [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sur l'un des systèmes d'exploitation suivants requiert davantage d'étapes de configuration si vous souhaitez administrer l'instance du serveur de rapports localement.</span><span class="sxs-lookup"><span data-stu-id="c65f8-103">Deploying a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server on one of the following operating systems requires more configuration steps if you want to administer the report server instance locally.</span></span> <span data-ttu-id="c65f8-104">Cette rubrique explique comment configurer le serveur de rapports pour l'administration locale.</span><span class="sxs-lookup"><span data-stu-id="c65f8-104">This topic explains how to configure the report server for local administration.</span></span> <span data-ttu-id="c65f8-105">Si vous n’avez pas encore installé ou configuré le serveur de rapports, consultez [installer SQL Server 2014 à partir de l’Assistant installation &#40;&#41;d'](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) installation et [gérer un serveur de rapports Reporting Services en mode natif](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="c65f8-105">If you have not yet installed or configured the report server, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) and [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
||  
|-|  
|<span data-ttu-id="c65f8-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en mode natif</span><span class="sxs-lookup"><span data-stu-id="c65f8-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
-   [!INCLUDE[winblue_server_2](../../includes/winblue-server-2-md.md)]  
  
-   [!INCLUDE[winblue_client_2](../../includes/winblue-client-2-md.md)]  
  
-   [!INCLUDE[win8](../../includes/win8-md.md)]  
  
-   [!INCLUDE[win8srv](../../includes/win8srv-md.md)]  
  
-   [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)]  
  
-   [!INCLUDE[win7](../../includes/win7-md.md)]  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)]  
  
 <span data-ttu-id="c65f8-107">Étant donné que les systèmes d'exploitation indiqués limitent les autorisations, les membres du groupe Administrateurs local exécutent la plupart des applications comme s'ils utilisaient le compte Utilisateur standard.</span><span class="sxs-lookup"><span data-stu-id="c65f8-107">Because the noted operating systems limit permissions, members of the local Administrators group run most applications as if they are using the Standard User account.</span></span>  
  
 <span data-ttu-id="c65f8-108">Même si cette solution améliore la sécurité globale de votre système, elle vous empêche d'utiliser les attributions de rôle prédéfinies et intégrées que Reporting Services crée pour les administrateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="c65f8-108">While this practice improves the overall security of your system, it prevents you from using the predefined, built-in role assignments that Reporting Services creates for local administrators.</span></span>  
  
-   [<span data-ttu-id="c65f8-109">Présentation des modifications de configuration</span><span class="sxs-lookup"><span data-stu-id="c65f8-109">Overview of Configuration Changes</span></span>](#bkmk_configuraiton_overview)  
  
-   [<span data-ttu-id="c65f8-110">Pour configurer un serveur de rapports local et l'administration du gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="c65f8-110">To Configure Local Report Server and Report Manager Administration</span></span>](#bkmk_configure_local_server)  
  
-   [<span data-ttu-id="c65f8-111">Pour configurer SQL Server Management Studio (SSMS) pour l'administration du serveur de rapports local</span><span class="sxs-lookup"><span data-stu-id="c65f8-111">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>](#bkmk_configure_ssms)  
  
-   [<span data-ttu-id="c65f8-112">Pour configurer SQL Server Data Tools BI (SSDT) pour la publication sur un serveur de rapports local</span><span class="sxs-lookup"><span data-stu-id="c65f8-112">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>](#bkmk_configure_ssdt)  
  
-   [<span data-ttu-id="c65f8-113">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c65f8-113">Additional Information</span></span>](#bkmk_addiitonal_informaiton)  
  
##  <a name="overview-of-configuration-changes"></a><a name="bkmk_configuraiton_overview"></a><span data-ttu-id="c65f8-114">Vue d’ensemble des modifications de configuration</span><span class="sxs-lookup"><span data-stu-id="c65f8-114">Overview of Configuration Changes</span></span>  
 <span data-ttu-id="c65f8-115">Les modifications de configuration suivantes configurent le serveur afin d'utiliser des autorisations standard pour gérer le contenu et les opérations du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="c65f8-115">The following configuration changes configure the server so that you can use standard user permissions to manage report server content and operations:</span></span>  
  
-   <span data-ttu-id="c65f8-116">Ajoutez les URL [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] aux sites approuvés.</span><span class="sxs-lookup"><span data-stu-id="c65f8-116">Add [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs to trusted sites.</span></span> <span data-ttu-id="c65f8-117">Par défaut, Internet Explorer est exécuté en **Mode protégé**sur les systèmes d’exploitation répertoriés, une fonctionnalité qui empêche les demandes du navigateur d’atteindre les processus globaux qui s’exécutent sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c65f8-117">By default, Internet Explorer running on the listed operating systems runs in **Protected Mode**, a feature that blocks browser requests from reaching high-level processes that run on the same computer.</span></span> <span data-ttu-id="c65f8-118">Vous pouvez désactiver le mode protégé pour les applications du serveur de rapports en les ajoutant comme Sites de confiance.</span><span class="sxs-lookup"><span data-stu-id="c65f8-118">You can disable protected mode for the report server applications by adding them as Trusted Sites.</span></span>  
  
-   <span data-ttu-id="c65f8-119">Créez les attributions de rôle qui vous accordent en tant qu'administrateur du serveur de rapports l'autorisation de gérer le contenu et les opérations sans devoir utiliser la fonctionnalité **Exécuter en tant qu'administrateur** sur Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c65f8-119">Create role assignments that grant you, the report server administrator, permission to manage content and operations without having to use the **Run as administrator** feature on Internet Explorer.</span></span> <span data-ttu-id="c65f8-120">En créant des attributions de rôle pour votre compte d'utilisateur Windows, vous accédez à un serveur de rapports avec les autorisations Gestionnaire de contenu et Administrateur système via des attributions de rôle explicites qui remplacent les attributions de rôle prédéfinies et intégrées créées par Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c65f8-120">By creating role assignments for your Windows user account, you gain access to a report server with Content Manager and System Administrator permissions through explicit role assignments that replace the predefined, built-in role assignments that Reporting Services creates.</span></span>  
  
##  <a name="to-configure-local-report-server-and-report-manager-administration"></a><a name="bkmk_configure_local_server"></a><span data-ttu-id="c65f8-121">Pour configurer le serveur de rapports local et l’administration de Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="c65f8-121">To Configure Local Report Server and Report Manager Administration</span></span>  
 <span data-ttu-id="c65f8-122">Complétez les étapes de configuration de cette section si vous souhaitez accéder à un serveur de rapports local et vous voyez des erreurs semblables à la suivante :</span><span class="sxs-lookup"><span data-stu-id="c65f8-122">Complete the configuration steps in this section if you are browsing to a local report server and you see errors similar to the following:</span></span>  
  
-   <span data-ttu-id="c65f8-123">L'utilisateur `'Domain\[user name]`» ne dispose pas des autorisations requises.</span><span class="sxs-lookup"><span data-stu-id="c65f8-123">User `'Domain\[user name]`' does not have required permissions.</span></span> <span data-ttu-id="c65f8-124">Vérifiez que les autorisations suffisantes ont été accordées et qu'aucune restriction liée au contrôle de compte d'utilisateur (UAC) Windows ne pose problème.</span><span class="sxs-lookup"><span data-stu-id="c65f8-124">Verify that sufficient permissions have been granted and Windows User Account Control (UAC) restrictions have been addressed.</span></span>  
  
###  <a name="trusted-site-settings-in-the-browser"></a><a name="bkmk_site_settings"></a><span data-ttu-id="c65f8-125">Paramètres du site de confiance dans le navigateur</span><span class="sxs-lookup"><span data-stu-id="c65f8-125">Trusted Site Settings in the Browser</span></span>  
  
1.  <span data-ttu-id="c65f8-126">Ouvrez une fenêtre du navigateur avec les autorisations Exécuter en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="c65f8-126">Open a browser window with Run as administrator permissions.</span></span> <span data-ttu-id="c65f8-127">Dans le menu **Démarrer** , cliquez sur **Tous les programmes**, cliquez avec le bouton droit sur **Internet Explorer**et sélectionnez **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-127">From the **Start** menu, click **All Programs**, right-click **Internet Explorer**, and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c65f8-128">Cliquez sur **Autoriser** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="c65f8-128">Click **Allow** to continue.</span></span>  
  
3.  <span data-ttu-id="c65f8-129">Dans l'adresse URL, entrez l'URL du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="c65f8-129">In the URL address, enter the Report Manager URL.</span></span> <span data-ttu-id="c65f8-130">Pour obtenir des instructions, consultez [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c65f8-130">For instructions, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="c65f8-131">Cliquez sur **Outils**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-131">Click **Tools**.</span></span>  
  
5.  <span data-ttu-id="c65f8-132">Cliquez sur **Options Internet**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-132">Click **Internet Options**.</span></span>  
  
6.  <span data-ttu-id="c65f8-133">Cliquez sur **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-133">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="c65f8-134">Cliquez sur **Sites de confiance**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-134">Click **Trusted Sites**.</span></span>  
  
8.  <span data-ttu-id="c65f8-135">Cliquez sur **Sites**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-135">Click **Sites**.</span></span>  
  
9. <span data-ttu-id="c65f8-136">Ajoutez `http://<your-server-name>`.</span><span class="sxs-lookup"><span data-stu-id="c65f8-136">Add `http://<your-server-name>`.</span></span>  
  
10. <span data-ttu-id="c65f8-137">Décochez la case **Nécessite la certification du serveur (https:) pour tous les sites dans cette zone** si vous n’utilisez pas HTTPS pour le site par défaut.</span><span class="sxs-lookup"><span data-stu-id="c65f8-137">Clear the check box **Require server certification (https:) for all sites in this zone** if you are not using HTTPS for the default site.</span></span>  
  
11. <span data-ttu-id="c65f8-138">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-138">Click **Add**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-folder-settings"></a><a name="bkmk_configure_folder_settings"></a> <span data-ttu-id="c65f8-139">Paramètres du dossier du gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="c65f8-139">Report Manager Folder Settings</span></span>  
  
1.  <span data-ttu-id="c65f8-140">Dans le Gestionnaire de rapports, sur la page d'accueil, cliquez sur **Paramètres du dossier**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-140">In Report Manager, on the Home page, click **Folder Settings**.</span></span>  
  
2.  <span data-ttu-id="c65f8-141">Dans la page Paramètres du dossier, cliquez sur **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-141">In the Folder Settings page, click **Security**.</span></span>  
  
3.  <span data-ttu-id="c65f8-142">Cliquez sur **Nouvelle attribution de rôle**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-142">Click **New Role Assignment**.</span></span>  
  
4.  <span data-ttu-id="c65f8-143">Dans le champ **Nom d'utilisateur ou de groupe** entrez votre compte d'utilisateur Windows au format : `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="c65f8-143">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
5.  <span data-ttu-id="c65f8-144">Sélectionnez **Gestionnaire de contenu**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-144">Select **Content Manager**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
###  <a name="report-manager-site-settings"></a><a name="bkmk_configure_site_settings"></a> <span data-ttu-id="c65f8-145">Paramètres du site du gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="c65f8-145">Report Manager Site Settings</span></span>  
  
1.  <span data-ttu-id="c65f8-146">Ouvrez votre navigateur avec des privilèges d'administrateur et accédez au gestionnaire de rapports, `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="c65f8-146">Open your browser with administrative privileges and browse to report manager, `http://<server name>/reports`.</span></span>  
  
2.  <span data-ttu-id="c65f8-147">Cliquez sur **Paramètres du site** dans l'angle supérieur de la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="c65f8-147">Click **Site Settings** in the upper corner of the Home page.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="c65f8-148">**Remarque :** si vous ne voyez pas l'option **Paramètre du site** , fermez et rouvrez votre navigateur et accédez au gestionnaire de rapports avec des privilèges d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="c65f8-148">**Note:** If you do not see the **Site Settings** option, close and reopen your browser and browse to report manager with administrative privileges.</span></span>  
  
3.  <span data-ttu-id="c65f8-149">Cliquez sur **sécurité**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-149">Click **security**.</span></span>  
  
4.  <span data-ttu-id="c65f8-150">Cliquez sur **Nouvelle attribution de rôle**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-150">Click **New Role Assignment**.</span></span>  
  
5.  <span data-ttu-id="c65f8-151">Dans le champ **Nom d'utilisateur ou de groupe** entrez votre compte d'utilisateur Windows au format : `<domain>\<user>`.</span><span class="sxs-lookup"><span data-stu-id="c65f8-151">In the **Group or user name** field, type your Windows user account in this format: `<domain>\<user>`.</span></span>  
  
6.  <span data-ttu-id="c65f8-152">Sélectionnez **Administrateur système**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-152">Select **System Administrator**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="c65f8-153">Fermez le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="c65f8-153">Close Report Manager.</span></span>  
  
9. <span data-ttu-id="c65f8-154">Rouvrez le Gestionnaire de rapports dans Internet Explorer, sans utiliser **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-154">Re-open Report Manager in Internet Explorer, without using **Run as administrator**.</span></span>  
  
##  <a name="to-configure-sql-server-management-studio-ssms-for-local-report-server-administration"></a><a name="bkmk_configure_ssms"></a><span data-ttu-id="c65f8-155">Pour configurer SQL Server Management Studio (SSMS) pour l’administration du serveur de rapports local</span><span class="sxs-lookup"><span data-stu-id="c65f8-155">To Configure SQL Server Management Studio (SSMS) for local report server administration</span></span>  
 <span data-ttu-id="c65f8-156">Par défaut, vous ne pouvez accéder à toutes les propriétés du serveur de rapports disponibles dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] à moins de démarrer [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] avec des privilèges d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="c65f8-156">By default, you cannot access all of the report server properties available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] unless you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
 <span data-ttu-id="c65f8-157">**Pour configurer les propriétés et attributions de rôles [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** , vous n'avez donc pas besoin de démarrer [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] avec des autorisations élevées chaque fois :</span><span class="sxs-lookup"><span data-stu-id="c65f8-157">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]** role properties and role assignments so you do not need to start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with elevated permissions each time:</span></span>  
  
-   <span data-ttu-id="c65f8-158">Dans le menu **Démarrer** , cliquez sur **Tous les programmes**, sur **SQL Server 2014**, cliquez avec le bouton droit sur **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-158">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]**, and then click **Run as administrator**.</span></span>  
  
-   <span data-ttu-id="c65f8-159">Connectez-vous à votre serveur local [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c65f8-159">Connect to your local [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server.</span></span>  
  
-   <span data-ttu-id="c65f8-160">Dans le nœud **Sécurité** , cliquez sur **Rôles système**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-160">In the **Security** node, click **System Roles**.</span></span>  
  
-   <span data-ttu-id="c65f8-161">Cliquez avec le bouton droit sur **Administrateur système** , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-161">Right-click **System Administrator** and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="c65f8-162">Dans la page **Propriétés de rôle système** , sélectionnez **Afficher les propriétés du serveur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-162">In the **System Role Properties** page, select **View report server properties**.</span></span> <span data-ttu-id="c65f8-163">Sélectionnez toute autre propriété que vous souhaitez associer aux membres du rôle d'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="c65f8-163">Select any other properties you want associated with members of the system administrators role.</span></span>  
  
-   <span data-ttu-id="c65f8-164">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-164">Click **OK**.</span></span>  
  
-   <span data-ttu-id="c65f8-165">Fermez [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c65f8-165">Close [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]</span></span>  
  
-   <span data-ttu-id="c65f8-166">Pour ajouter un utilisateur au rôle système « administrateur système », consultez la section [Paramètres du site du gestionnaire de rapports](#bkmk_configure_site_settings) plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c65f8-166">To add a user to the system role "system administrator", see the [Report Manager Site Settings](#bkmk_configure_site_settings) section earlier in this topic.</span></span>  
  
 <span data-ttu-id="c65f8-167">Maintenant, lorsque vous ouvrez [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et vous ne sélectionnez pas explicitement **Exécuter en tant qu'administrateur** , vous avez accès aux propriétés du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="c65f8-167">Now when you open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and do not explicitly select **Run as administrator** you have access to the report server properties.</span></span>  
  
##  <a name="to-configure-sql-server-data-tools-bi-ssdt-to-publish-to-a-local-report-server"></a><a name="bkmk_configure_ssdt"></a><span data-ttu-id="c65f8-168">Pour configurer SQL Server Data Tools BI (SSDT) pour la publication sur un serveur de rapports local</span><span class="sxs-lookup"><span data-stu-id="c65f8-168">To Configure SQL Server Data Tools BI (SSDT) to Publish to a Local Report Server</span></span>  
 <span data-ttu-id="c65f8-169">Si vous avez installé [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] sur l’un des systèmes d’exploitation répertoriés dans la première section de cette rubrique et que vous souhaitez que SSDT interagisse avec un serveur de rapports local en mode natif, vous rencontrerez des erreurs d’autorisation sauf si vous ouvrez [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] avec des autorisations élevées ou si vous configurez des rôles Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c65f8-169">If you installed [!INCLUDE[SSDTDev11](../../includes/ssdtdev11-md.md)] on one of the operating systems listed in the first section of this topic, and you want SSDT to interact with a local Native mode report server, you will experiences permission errors unless you open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] with elevated permissions or configure reporting services roles.</span></span> <span data-ttu-id="c65f8-170">Par exemple, si vous n'avez pas les autorisations suffisantes, vous rencontrerez des avertissements semblables au suivant :</span><span class="sxs-lookup"><span data-stu-id="c65f8-170">For example, if you do not have sufficient permissions, you experience issues similar to the following:</span></span>  
  
-   <span data-ttu-id="c65f8-171">Lorsque vous tentez de déployer des éléments de rapport sur le serveur de rapports local, vous voyez un message d'erreur similaire au suivant dans la fenêtre **Liste d'erreurs** :</span><span class="sxs-lookup"><span data-stu-id="c65f8-171">When you attempt to deploy report items to the local report server, you see an error message similar to the following in the **Error List** window:</span></span>  
  
    -   <span data-ttu-id="c65f8-172">Les autorisations accordées à l’utilisateur « Domaine\\<nom utilisateur\> » sont insuffisantes pour effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="c65f8-172">The permissions granted to user 'Domain\\<user name\>' are insufficient for performing this operation.</span></span>  
  
 <span data-ttu-id="c65f8-173">**Pour exécuter avec des autorisations élevées chaque fois que vous ouvrez SSDT :**</span><span class="sxs-lookup"><span data-stu-id="c65f8-173">**To run with elevated permissions each time you open SSDT:**</span></span>  
  
1.  <span data-ttu-id="c65f8-174">Dans l’écran d’accueil, tapez, `sql server` puis cliquez avec le bouton droit sur **SQL Server Data Tools pour Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-174">From the start screen, type `sql server` and then right-click **SQL Server Data Tools for Visual Studio**.</span></span> <span data-ttu-id="c65f8-175">Cliquez sur **Exécuter en tant qu’administrateur**</span><span class="sxs-lookup"><span data-stu-id="c65f8-175">Click **Run as administrator**</span></span>  
  
     <span data-ttu-id="c65f8-176">**Ou**, sur les systèmes d'exploitation plus anciens :</span><span class="sxs-lookup"><span data-stu-id="c65f8-176">**Or**, on older operating systems:</span></span>  
  
     <span data-ttu-id="c65f8-177">Dans le menu **Démarrer** , cliquez sur **Tous les programmes**, sur **SQL Server 2014**, cliquez avec le bouton droit sur **Outils de données SQL Server**, puis cliquez sur **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-177">From the **Start** menu, click **All Programs**, click **SQL Server 2014**, right-click **SQL Server Data Tools**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c65f8-178">Cliquez sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-178">Click **Continue**.</span></span>  
  
3.  <span data-ttu-id="c65f8-179">Cliquez sur **Exécuter le programme**.</span><span class="sxs-lookup"><span data-stu-id="c65f8-179">Click **Run Program**.</span></span>  
  
 <span data-ttu-id="c65f8-180">Vous devez maintenant être en mesure de déployer les rapports et autres éléments sur un serveur de rapports local.</span><span class="sxs-lookup"><span data-stu-id="c65f8-180">You should now be able to deploy reports and other items to a local report server.</span></span>  
  
 <span data-ttu-id="c65f8-181">**Pour configurer les propriétés et attributions de rôles [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , vous n'avez donc pas besoin de démarrer SSDT avec des autorisations élevées chaque fois :**</span><span class="sxs-lookup"><span data-stu-id="c65f8-181">**To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] role assignments so you do not need to start SSDT with elevated permissions each time:**</span></span>  
  
-   <span data-ttu-id="c65f8-182">Consultez les sections [Paramètres du dossier du gestionnaire de rapports](#bkmk_configure_folder_settings) et [Paramètres du site du gestionnaire de rapports](#bkmk_configure_site_settings) plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c65f8-182">See the [Report Manager Folder Settings](#bkmk_configure_folder_settings) and [Report Manager Site Settings](#bkmk_configure_site_settings) sections earlier in this topic.</span></span>  
  
##  <a name="additional-information"></a><a name="bkmk_addiitonal_informaiton"></a><span data-ttu-id="c65f8-183">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c65f8-183">Additional Information</span></span>  
 <span data-ttu-id="c65f8-184">Une étape de configuration supplémentaire et courante pour l'administration [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] consiste à ouvrir le port 80 dans le Pare-feu Windows pour autoriser l'accès à l'ordinateur du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="c65f8-184">An additional and common configuration step related to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] administration is to open port 80 in Windows Firewall to allow access to the report server computer.</span></span> <span data-ttu-id="c65f8-185">Pour obtenir des instructions, consultez [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="c65f8-185">For instructions, see [Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65f8-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c65f8-186">See Also</span></span>  
 [<span data-ttu-id="c65f8-187">Gérer un serveur de rapports Reporting Services en mode natif</span><span class="sxs-lookup"><span data-stu-id="c65f8-187">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
