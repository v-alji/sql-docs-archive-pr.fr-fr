---
title: Installer la version autonome de Générateur de rapports (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6b2291bb-1d20-4d08-81cb-a16dd8e01faf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ba8c132125f56ad833a71a1c82221e2bf28d13e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611585"
---
# <a name="install-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="efb6f-102">Installer la version autonome du Générateur de rapports (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="efb6f-102">Install the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="efb6f-103">Vous pouvez installer Générateur de rapports à partir du [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack dans le [Centre de téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=53613) ou à un emplacement tel que le dossier public dans lequel le ReportBuilder3_x86.msi, le Package Windows Installer pour générateur de rapports, a été téléchargé.</span><span class="sxs-lookup"><span data-stu-id="efb6f-103">You can install Report Builder from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] feature pack on the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613) or a location such as public folder to which the ReportBuilder3_x86.msi, the Windows Installer Package for Report Builder, has been downloaded.</span></span>  
  
 <span data-ttu-id="efb6f-104">Vous pouvez également effectuer une installation du Générateur de rapports à partir de la ligne de commande et spécifier des arguments afin de personnaliser l'installation.</span><span class="sxs-lookup"><span data-stu-id="efb6f-104">You can also perform a command line installation of Report Builder and provide arguments to customize the installation.</span></span> <span data-ttu-id="efb6f-105">Outre les paramètres MSI standard intrinsèques, vous pouvez utiliser les paramètres personnalisés fournis par le Générateur de rapports : RBINSTALLDIR et REPORTSERVERURL.</span><span class="sxs-lookup"><span data-stu-id="efb6f-105">In addition to the standard MSI intrinsic parameters, you can use the custom parameters that Report Builder provides: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="efb6f-106">RBINSTALLDIR spécifie le dossier d'installation racine pour le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="efb6f-106">RBINSTALLDIR specifies the root installation folder for Report Builder.</span></span> <span data-ttu-id="efb6f-107">REPORTSERVERURL spécifie le serveur de rapports par défaut utilisé par le Générateur de rapports pour enregistrer des rapports.</span><span class="sxs-lookup"><span data-stu-id="efb6f-107">REPORTSERVERURL specifies the default report server that Report Builder uses to save reports on the server.</span></span>  
  
 <span data-ttu-id="efb6f-108">Si vous souhaitez effectuer une installation totalement sans assistance, sans aucune interaction avec l’interface utilisateur, spécifiez l’option **/quiet** .</span><span class="sxs-lookup"><span data-stu-id="efb6f-108">If you want a completely silent installation, with no user interface interaction at all, specify the **/quiet** option.</span></span> <span data-ttu-id="efb6f-109">Par défaut, l'indicateur d'option quiet supprime les erreurs d'installation.</span><span class="sxs-lookup"><span data-stu-id="efb6f-109">By design, the quiet option flag suppresses installation errors.</span></span> <span data-ttu-id="efb6f-110">Il est par conséquent recommandé d’inclure l’option **/l** , qui spécifie l’enregistrement dans le journal, lorsque vous utilisez l’option quiet.</span><span class="sxs-lookup"><span data-stu-id="efb6f-110">It is therefore recommended that you include the **/l** option, which specifies logging, when you use the quiet option.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="efb6f-111">Les fonctionnalités de sécurité de Windows Vista et Windows 7 requièrent des autorisations élevées pour exécuter des opérations en ligne de commande ; par conséquent, vous êtes invité à confirmer que vous avez l'autorisation d'exécuter la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="efb6f-111">Windows Vista and Windows 7 security features require elevated permissions to run command line operations and will prompt for permission to run the command line.</span></span> <span data-ttu-id="efb6f-112">Il ne s'agit pas d'une installation sans assistance.</span><span class="sxs-lookup"><span data-stu-id="efb6f-112">The installation is not silent.</span></span> <span data-ttu-id="efb6f-113">Pour effectuer une installation sans assistance, vous devez exécuter la ligne de commande en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="efb6f-113">To make the installation silent, you need to run the command line as an administrator.</span></span>  
  
### <a name="to-install-report-builder-from-the-download-site"></a><span data-ttu-id="efb6f-114">Pour installer le Générateur de rapports à partir du site de téléchargement</span><span class="sxs-lookup"><span data-stu-id="efb6f-114">To install Report Builder from the download site</span></span>  
  
1.  <span data-ttu-id="efb6f-115">Accédez à [Microsoft SQL Server 2012 générateur de rapports](https://go.microsoft.com/fwlink/?LinkID=219138) et recherchez la section générateur de rapports de la page Web.</span><span class="sxs-lookup"><span data-stu-id="efb6f-115">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section of the Web page.</span></span>  
  
2.  <span data-ttu-id="efb6f-116">Cliquez sur **package x86**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-116">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="efb6f-117">Dans la boîte de dialogue **téléchargement de fichier** , cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-117">In the **File Download** dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="efb6f-118">Téléchargez uniquement les fichiers provenant de sources fiables.</span><span class="sxs-lookup"><span data-stu-id="efb6f-118">Download only files from trusted sources.</span></span>  
  
4.  <span data-ttu-id="efb6f-119">Dans la boîte de dialogue Internet Explorer, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-119">In the Internet Explorer dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="efb6f-120">Exécutez uniquement les fichiers provenant de sources fiables.</span><span class="sxs-lookup"><span data-stu-id="efb6f-120">Run only files from trusted sources.</span></span>  
  
5.  <span data-ttu-id="efb6f-121">L'Assistant Générateur de rapports Microsoft SQL Server démarre.</span><span class="sxs-lookup"><span data-stu-id="efb6f-121">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
6.  <span data-ttu-id="efb6f-122">Sur la page **Bienvenue dans l’Assistant Installation** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-122">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="efb6f-123">Sur la page **contrat de licence** , lisez le contrat, puis sélectionnez l’option **J’accepte les termes du contrat de licence** .</span><span class="sxs-lookup"><span data-stu-id="efb6f-123">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="efb6f-124">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-124">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="efb6f-125">Spécifiez votre nom et le nom de la société.</span><span class="sxs-lookup"><span data-stu-id="efb6f-125">Provide your personal name and company name.</span></span> <span data-ttu-id="efb6f-126">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="efb6f-127">Sur la page **sélection de composant** , cliquez éventuellement sur **Parcourir** ou coût du **disque**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-127">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="efb6f-128">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-128">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="efb6f-129">Cliquez sur **Parcourir** pour afficher l’emplacement par défaut de générateur de rapports et le mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="efb6f-129">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="efb6f-130">Le dossier d’installation par défaut de Générateur de rapports est \<drive> Program Files\Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="efb6f-130">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="efb6f-131">Cliquez sur **coût du disque** pour connaître la quantité d’espace disque consommée par générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="efb6f-131">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="efb6f-132">Si l'espace disque libre sur un volume n'est pas suffisant, le volume est mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="efb6f-132">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
10. <span data-ttu-id="efb6f-133">Dans la page **Serveur cible par défaut** , spécifiez éventuellement l'URL du serveur de rapports cible s'il est différent du serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="efb6f-133">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="efb6f-134">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-134">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="efb6f-135">Si vous prévoyez de travailler avec le Générateur de rapports lorsqu'il est connecté à un serveur de rapports, il est plus commode de spécifier l'URL du serveur à ce stade.</span><span class="sxs-lookup"><span data-stu-id="efb6f-135">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="efb6f-136">Toutefois, vous pouvez également effectuer cette opération à partir de la boîte de dialogue **options** lorsque vous travaillez dans générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="efb6f-136">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
11. <span data-ttu-id="efb6f-137">Cliquez sur **installer** pour terminer l’installation de générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="efb6f-137">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-a-share"></a><span data-ttu-id="efb6f-138">Pour installer le Générateur de rapports à partir d'un partage</span><span class="sxs-lookup"><span data-stu-id="efb6f-138">To install Report Builder from a share</span></span>  
  
1.  <span data-ttu-id="efb6f-139">Contactez votre administrateur afin de connaître l'emplacement du fichier ReportBuilder3_x86.msi que vous exécutez pour installer le Générateur de rapports sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="efb6f-139">Contact your administrator for the location of ReportBuilder3_x86.msi.msi that you run to install Report Builder on your local computer.</span></span>  
  
2.  <span data-ttu-id="efb6f-140">Recherchez le fichier ReportBuilder3_x86.msi, le package MSI Windows Installer pour le Générateur de rapports, puis cliquez dessus.</span><span class="sxs-lookup"><span data-stu-id="efb6f-140">Browse to locate the ReportBuilder3_x86.msi.msi, the Windows Installer Package (MSI) for Report Builder, and click it.</span></span>  
  
     <span data-ttu-id="efb6f-141">L'Assistant Générateur de rapports Microsoft SQL Server démarre.</span><span class="sxs-lookup"><span data-stu-id="efb6f-141">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
3.  <span data-ttu-id="efb6f-142">Sur la page **Bienvenue dans l’Assistant Installation** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-142">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="efb6f-143">Sur la page **contrat de licence** , lisez le contrat, puis sélectionnez l’option **J’accepte les termes du contrat de licence** .</span><span class="sxs-lookup"><span data-stu-id="efb6f-143">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="efb6f-144">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-144">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="efb6f-145">Spécifiez votre nom et le nom de la société.</span><span class="sxs-lookup"><span data-stu-id="efb6f-145">Provide your personal name and company name.</span></span> <span data-ttu-id="efb6f-146">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="efb6f-147">Sur la page **sélection de composant** , cliquez éventuellement sur **Parcourir** ou coût du **disque**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-147">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="efb6f-148">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-148">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="efb6f-149">Cliquez sur **Parcourir** pour afficher l’emplacement par défaut de générateur de rapports et le mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="efb6f-149">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="efb6f-150">Le dossier d’installation par défaut de Générateur de rapports est \<drive> Program Files\Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="efb6f-150">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="efb6f-151">Cliquez sur **coût du disque** pour connaître la quantité d’espace disque consommée par générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="efb6f-151">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="efb6f-152">Si l'espace disque libre sur un volume n'est pas suffisant, le volume est mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="efb6f-152">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
7.  <span data-ttu-id="efb6f-153">Dans la page **Serveur cible par défaut** , spécifiez éventuellement l'URL du serveur de rapports cible s'il est différent du serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="efb6f-153">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="efb6f-154">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-154">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="efb6f-155">Si vous prévoyez de travailler avec le Générateur de rapports lorsqu'il est connecté à un serveur de rapports, il est plus commode de spécifier l'URL du serveur à ce stade.</span><span class="sxs-lookup"><span data-stu-id="efb6f-155">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="efb6f-156">Toutefois, vous pouvez également effectuer cette opération à partir de la boîte de dialogue **options** lorsque vous travaillez dans générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="efb6f-156">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
8.  <span data-ttu-id="efb6f-157">Cliquez sur **installer** pour terminer l’installation de générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="efb6f-157">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-the-command-line"></a><span data-ttu-id="efb6f-158">Pour installer le Générateur de rapports à partir de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="efb6f-158">To install Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="efb6f-159">Accédez à [Microsoft SQL Server 2012 générateur de rapports](https://go.microsoft.com/fwlink/?LinkID=219138) et recherchez la section générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="efb6f-159">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section.</span></span>  
  
2.  <span data-ttu-id="efb6f-160">Cliquez sur **package x86**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-160">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="efb6f-161">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="efb6f-161">Click Save.</span></span>  
  
4.  <span data-ttu-id="efb6f-162">Si vous le souhaitez, accédez à l’emplacement où vous souhaitez enregistrer, vérifiez que l’option **Enregistrer sous** est **Windows Installer Package**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-162">Optionally, browse to the location to save to, verify the **Save as** option is **Windows Installer Package**, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="efb6f-163">Dans le menu **Démarrer** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="efb6f-163">On the **Start** menu, click **Run**.</span></span>  
  
6.  <span data-ttu-id="efb6f-164">Dans la zone de texte Ouvrir, tapez .`cmd.`</span><span class="sxs-lookup"><span data-stu-id="efb6f-164">In the Open text box, type `cmd.`</span></span>  
  
7.  <span data-ttu-id="efb6f-165">Dans la fenêtre d'invite de commandes, naviguez jusqu'au dossier où vous avez enregistré ReportBuilder3_x86.msi.</span><span class="sxs-lookup"><span data-stu-id="efb6f-165">In the Command Prompt window, navigate to the folder where you saved ReportBuilder3_x86.msi.</span></span>  
  
8.  <span data-ttu-id="efb6f-166">Tapez une commande au format suivant :</span><span class="sxs-lookup"><span data-stu-id="efb6f-166">Type a command with the following format:</span></span>  
  
     `msiexec/i ReportBuilder3_.msi /option [value] [/option [value]]`  
  
     <span data-ttu-id="efb6f-167">Les deux options spécifiques à l'installation du Générateur de rapports sont : RBINSTALLDIR et REPORTSERVERURL.</span><span class="sxs-lookup"><span data-stu-id="efb6f-167">The two options specific to installing Report Builder are: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="efb6f-168">Il n'est pas obligatoire d'inclure ces arguments dans la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="efb6f-168">It not required that you include these arguments in the command line.</span></span> <span data-ttu-id="efb6f-169">Voici la ligne de commande de base :</span><span class="sxs-lookup"><span data-stu-id="efb6f-169">The following is the baseline command:</span></span>  
  
     `msiexec /i ReportBuilder3_x86.msi /quiet`  
  
9. <span data-ttu-id="efb6f-170">Pour exécuter la commande, appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="efb6f-170">To run the command, press Enter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb6f-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="efb6f-171">See Also</span></span>  
 <span data-ttu-id="efb6f-172">[Installer, désinstaller et Générateur de rapports la prise en charge](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="efb6f-172">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="efb6f-173">Désinstallez la version autonome de Générateur de rapports &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="efb6f-173">Uninstall the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  
