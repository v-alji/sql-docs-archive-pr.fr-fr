---
title: Configurer un pare-feu pour accéder au serveur de rapports | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- firewall systems [Reporting Services]
- configuring servers [Reporting Services]
ms.assetid: 04dae07a-a3a4-424c-9bcb-a8000e20dc93
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b578c980522d24f5a24a73fdfd080ec425335aac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611562"
---
# <a name="configure-a-firewall-for-report-server-access"></a><span data-ttu-id="45aca-102">Configurer un pare-feu pour accéder au serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="45aca-102">Configure a Firewall for Report Server Access</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="45aca-103">et les rapports publiés sont accessibles via les URL qui spécifient une adresse IP, un port et un répertoire virtuel.</span><span class="sxs-lookup"><span data-stu-id="45aca-103">Report server applications and published reports are accessed through URLs that specify an IP address, port, and virtual directory.</span></span> <span data-ttu-id="45aca-104">Si le Pare-feu Windows est activé, le port que le serveur de rapports est configuré pour utiliser est très probablement fermé.</span><span class="sxs-lookup"><span data-stu-id="45aca-104">If Windows Firewall is turned on, the port that the report server is configured to use is most likely closed.</span></span> <span data-ttu-id="45aca-105">La présence d'une page Web vierge après la demande d'un rapport ou l'affichage d'une page vierge lorsque vous tentez d'ouvrir le Gestionnaire de rapports à partir d'un ordinateur client distant constituent une indication qu'un port peut être fermé.</span><span class="sxs-lookup"><span data-stu-id="45aca-105">Indications that a port might be closed are the appearance of a blank Web page after requesting a report, or a blank page when you attempt to open Report Manager from a remote client computer.</span></span>  
  
 <span data-ttu-id="45aca-106">Pour ouvrir un port, vous devez utiliser le Pare-feu Windows sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="45aca-106">To open a port, you must use the Windows Firewall utility on the report server computer.</span></span> <span data-ttu-id="45aca-107">Reporting Services n'ouvrent pas de ports automatiquement ; vous devez effectuer cette étape manuellement.</span><span class="sxs-lookup"><span data-stu-id="45aca-107">Reporting Services will not open ports for you; you must perform this step manually.</span></span>  
  
 <span data-ttu-id="45aca-108">Par défaut, le serveur de rapports écoute les requêtes HTTP sur le port 80.</span><span class="sxs-lookup"><span data-stu-id="45aca-108">By default, the report server listens for HTTP requests on port 80.</span></span> <span data-ttu-id="45aca-109">De ce fait, les instructions suivantes incluent les étapes qui spécifient ce port.</span><span class="sxs-lookup"><span data-stu-id="45aca-109">As such, the following instructions include steps that specify that port.</span></span> <span data-ttu-id="45aca-110">Si vous avez configuré les URL du serveur de rapports pour utiliser un autre port, vous devez spécifier ce numéro de port lors des instructions ci-après.</span><span class="sxs-lookup"><span data-stu-id="45aca-110">If you configured the report server URLs to use a different port, you must specify that port number when following the instructions below.</span></span>  
  
 <span data-ttu-id="45aca-111">Si vous accédez à des bases de données relationnelles [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur des ordinateurs externes, ou si la base de données du serveur de rapports se trouve sur une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] externe, vous devez ouvrir les ports 1433 et 1434 sur l'ordinateur externe.</span><span class="sxs-lookup"><span data-stu-id="45aca-111">If you are accessing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relational databases on external computers, or if the report server database is on an external [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, you must open port 1433 and 1434 on the external computer.</span></span> <span data-ttu-id="45aca-112">Pour plus d’informations, consultez [Configurer un pare-feu Windows pour accéder au moteur de base de données](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45aca-112">For more information, see [Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="45aca-113">Pour plus d’informations sur les paramètres par défaut du Pare-feu Windows et pour obtenir une description des ports TCP qui affectent le [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]et [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], consultez [Configurer le Pare-feu Windows pour autoriser l’accès à SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45aca-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="45aca-114">Conditions préalables requises</span><span class="sxs-lookup"><span data-stu-id="45aca-114">Prerequisites</span></span>  
 <span data-ttu-id="45aca-115">Ces instructions supposent que vous avez déjà configuré le compte de service, créé la base de données du serveur de rapports et configuré les URLS du service Web Report Server et du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="45aca-115">These instructions assume that you already configured the service account, created the report server database, and configured URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="45aca-116">Pour plus d’informations, consultez [Gérer un serveur de rapports Reporting Services (SSRS) en mode natif](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="45aca-116">For more information, see [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
 <span data-ttu-id="45aca-117">Vous devez aussi avoir vérifié que le serveur de rapports est accessible via une connexion locale du navigateur Web à l'instance locale du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="45aca-117">You should also have verified that the report server is accessible over a local Web browser connection to the local report server instance.</span></span> <span data-ttu-id="45aca-118">Cette étape établit que votre installation est en état de marche.</span><span class="sxs-lookup"><span data-stu-id="45aca-118">This step establishes that you have a working installation.</span></span> <span data-ttu-id="45aca-119">Vous devez vérifier que l'installation est configurée correctement avant de commencer à ouvrir les ports.</span><span class="sxs-lookup"><span data-stu-id="45aca-119">You should verify that the installation is configured correctly before you begin opening ports.</span></span> <span data-ttu-id="45aca-120">Pour compléter cette étape sur Windows Server, vous devez également avoir ajouté le site du serveur de rapports aux Sites de confiance.</span><span class="sxs-lookup"><span data-stu-id="45aca-120">To complete this step on  Windows Server, you must have also added the report server site to Trusted Sites.</span></span> <span data-ttu-id="45aca-121">Pour plus d’informations, consultez [Configurer un serveur de rapports en mode natif pour l’administration locale &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="45aca-121">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="opening-ports-in-windows-firewall"></a><span data-ttu-id="45aca-122">Ouverture des ports dans le Pare-feu Windows</span><span class="sxs-lookup"><span data-stu-id="45aca-122">Opening Ports in Windows Firewall</span></span>  
 <span data-ttu-id="45aca-123">Il existe des instructions distinctes selon les différentes versions du Pare-feu Windows.</span><span class="sxs-lookup"><span data-stu-id="45aca-123">There are separate instructions for different versions of Windows Firewall.</span></span>  
  
#### <a name="to-open-port-80-on-windows-7-windows-server-2008-r2-windows-server-2012-and-2012-r2"></a><span data-ttu-id="45aca-124">Pour ouvrir le port 80 sur Windows 7, Windows Server 2008 R2, Windows Server 2012 et Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="45aca-124">To open port 80 on Windows 7, Windows Server 2008 R2, Windows Server 2012 and 2012 R2</span></span>  
  
1.  <span data-ttu-id="45aca-125">Dans le menu **Démarrer** , cliquez sur **Panneau de configuration**, cliquez sur **Système et sécurité**, puis sur **Pare-feu Windows**.</span><span class="sxs-lookup"><span data-stu-id="45aca-125">From the **Start** menu, click **Control Panel**, click **System and Security**, and then click **Windows Firewall**.</span></span> <span data-ttu-id="45aca-126">Le Panneau de configuration n'est pas configuré pour l'affichage de « Catégorie », vous devez seulement sélectionner le **Pare-feu Windows**.</span><span class="sxs-lookup"><span data-stu-id="45aca-126">Control Panel is not configured for 'Category' view, you only need to select **Windows Firewall.**</span></span>  
  
2.  <span data-ttu-id="45aca-127">Cliquez sur **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="45aca-127">Click **Advanced Settings**.</span></span>  
  
3.  <span data-ttu-id="45aca-128">Cliquez sur **Règles de trafic entrant**.</span><span class="sxs-lookup"><span data-stu-id="45aca-128">Click **Inbound Rules.**</span></span>  
  
4.  <span data-ttu-id="45aca-129">Cliquez sur **Nouvelle règle** dans la fenêtre **Actions\*\*\*\*.**</span><span class="sxs-lookup"><span data-stu-id="45aca-129">Click **New Rule** in the **Actions** window **.**</span></span>  
  
5.  <span data-ttu-id="45aca-130">Cliquez sur **Type de règle** de **Port**.</span><span class="sxs-lookup"><span data-stu-id="45aca-130">Click **Rule Type** of **Port.**</span></span>  
  
6.  <span data-ttu-id="45aca-131">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="45aca-131">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="45aca-132">Dans la page **Protocole et ports** , cliquez sur **TCP**.</span><span class="sxs-lookup"><span data-stu-id="45aca-132">On the **Protocol and Ports** page click **TCP**.</span></span>  
  
8.  <span data-ttu-id="45aca-133">Sélectionnez **Ports locaux spécifiques** et tapez la valeur **80**.</span><span class="sxs-lookup"><span data-stu-id="45aca-133">Select **Specific Local Ports** and type a value of **80**.</span></span>  
  
9. <span data-ttu-id="45aca-134">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="45aca-134">Click **Next**.</span></span>  
  
10. <span data-ttu-id="45aca-135">Dans la page **Action** , cliquez sur **Autoriser la connexion**.</span><span class="sxs-lookup"><span data-stu-id="45aca-135">On the **Action** page click **Allow the connection**.</span></span>  
  
11. <span data-ttu-id="45aca-136">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="45aca-136">Click **Next**.</span></span>  
  
12. <span data-ttu-id="45aca-137">Dans la page **Profil** , cliquez sur les options appropriées pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="45aca-137">On the **Profile** page click the appropriate options for your environment.</span></span>  
  
13. <span data-ttu-id="45aca-138">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="45aca-138">Click **Next**.</span></span>  
  
14. <span data-ttu-id="45aca-139">Dans la page **Nom** , entrez un nom de**ReportServer (TCP sur le port 80)**.</span><span class="sxs-lookup"><span data-stu-id="45aca-139">On the **Name** page enter a name of**ReportServer (TCP on port 80)**</span></span>  
  
15. <span data-ttu-id="45aca-140">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="45aca-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="45aca-141">Redémarrez l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="45aca-141">Restart the computer.</span></span>  
  
#### <a name="to-open-port-80-on-windows-vista-or-windows-server-2008"></a><span data-ttu-id="45aca-142">Pour ouvrir le port 80 sur Windows Vista ou Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="45aca-142">To open port 80 on Windows Vista or Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="45aca-143">Dans le menu **Démarrer** , cliquez sur **panneau de configuration**, sur **sécurité**, puis sur **pare-feu Windows**.</span><span class="sxs-lookup"><span data-stu-id="45aca-143">From the **Start** menu, click **Control Panel**, click **Security**, and then click **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="45aca-144">Cliquez sur **Autoriser un programme via le Pare-feu Windows**.</span><span class="sxs-lookup"><span data-stu-id="45aca-144">Click **Allow a program through Windows Firewall**.</span></span>  
  
3.  <span data-ttu-id="45aca-145">Cliquez sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="45aca-145">Click **Continue**.</span></span>  
  
4.  <span data-ttu-id="45aca-146">Sous l’onglet exceptions, cliquez sur **Ajouter un port**.</span><span class="sxs-lookup"><span data-stu-id="45aca-146">On the Exceptions tab, click **Add Port**.</span></span>  
  
5.  <span data-ttu-id="45aca-147">Dans nom, tapez **reportserver (TCP sur le port 80)**.</span><span class="sxs-lookup"><span data-stu-id="45aca-147">In Name, type **ReportServer (TCP on port 80)**.</span></span>  
  
6.  <span data-ttu-id="45aca-148">Dans numéro de port, tapez **80**.</span><span class="sxs-lookup"><span data-stu-id="45aca-148">In Port number, type **80**.</span></span>  
  
7.  <span data-ttu-id="45aca-149">Vérifiez que **TCP** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="45aca-149">Verify that **TCP** is selected.</span></span>  
  
8.  <span data-ttu-id="45aca-150">Cliquez sur **Modifier l'étendue**.</span><span class="sxs-lookup"><span data-stu-id="45aca-150">Click **Change Scope**.</span></span>  
  
9. <span data-ttu-id="45aca-151">Cliquez sur **mon réseau (sous-réseau) uniquement**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="45aca-151">Click **My network (subnet) only**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="45aca-152">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="45aca-152">Click **OK** to close the dialog box.</span></span>  
  
11. <span data-ttu-id="45aca-153">Redémarrez l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="45aca-153">Restart the computer.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="45aca-154">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="45aca-154">Next Steps</span></span>  
 <span data-ttu-id="45aca-155">Après avoir ouvert le port et avant de confirmer si les utilisateurs distants peuvent accéder au serveur de rapports sur le port que vous ouvrez, vous devez accorder l'accès utilisateur au serveur de rapports à travers les attributions de rôle sur la page d'Accueil et au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="45aca-155">After you open the port and before you confirm whether remote users can access the report server on the port that you open, you must grant user access to the report server through role assignments on Home and at the site level.</span></span> <span data-ttu-id="45aca-156">Vous pouvez ouvrir un port correctement et que les connexions du serveur de rapports échouent si les utilisateurs n'ont pas les autorisations suffisantes.</span><span class="sxs-lookup"><span data-stu-id="45aca-156">You can open a port correctly and still have report server connections fail if users do not have sufficient permissions.</span></span> <span data-ttu-id="45aca-157">Pour plus d’informations, consultez [Accorder à un utilisateur l’accès à un serveur de rapports &#40;Gestionnaire de rapports&#41;](../security/grant-user-access-to-a-report-server.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45aca-157">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](../security/grant-user-access-to-a-report-server.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="45aca-158">Vous pouvez également vérifier que le port est ouvert correctement en démarrant le Gestionnaire de rapports sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="45aca-158">You can also verify that the port is opened correctly by starting Report Manager on a different computer.</span></span> <span data-ttu-id="45aca-159">Pour plus d’informations, consultez [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45aca-159">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45aca-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45aca-160">See Also</span></span>  
 <span data-ttu-id="45aca-161">[Configurer le compte de service Report Server &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="45aca-161">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="45aca-162">[Configurer des URL de serveurs de rapports &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="45aca-162">[Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="45aca-163">[Créer une base de données du serveur de rapports &#40;SSRS Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="45aca-163">[Create a Report Server Database  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="45aca-164">[Configurer le compte de service Report Server &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="45aca-164">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="45aca-165">Gérer un serveur de rapports Reporting Services en mode natif</span><span class="sxs-lookup"><span data-stu-id="45aca-165">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
