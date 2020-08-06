---
title: Applets de commande PowerShell pour Reporting Services mode SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7835bc97-2827-4215-b0dd-52f692ce5e02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b20ad870fd8a9cd7f220eebb2b954d7a88a10c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710256"
---
# <a name="powershell-cmdlets-for-reporting-services-sharepoint-mode"></a><span data-ttu-id="07b4a-102">Applets de commande PowerShell pour le mode SharePoint de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="07b4a-102">PowerShell cmdlets for Reporting Services SharePoint Mode</span></span>
  <span data-ttu-id="07b4a-103">Lorsque vous installez le [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] mode SharePoint, les applets de commande PowerShell sont installées pour prendre en charge les serveurs de rapports en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07b4a-103">When you install [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint mode, PowerShell cmdlets are installed to support report Servers in SharePoint mode.</span></span> <span data-ttu-id="07b4a-104">Les applets de commande couvrent trois catégories de fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="07b4a-104">The cmdlets cover three categories of functionality.</span></span>  
  
-   <span data-ttu-id="07b4a-105">Installation du service partagé et du proxy SharePoint de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-105">Installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service and proxy.</span></span>  
  
-   <span data-ttu-id="07b4a-106">Configuration et gestion des applications de service et des proxys associés d' [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-106">Provisioning and management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and associated proxies.</span></span>  
  
-   <span data-ttu-id="07b4a-107">Gestion des fonctionnalités d' [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , par exemple extensions et clés de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="07b4a-107">Management of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features, for example extensions and encryption keys.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../includes/applies-md.md)]<span data-ttu-id="07b4a-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]Mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="07b4a-108">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint Mode</span></span>|  
  
 <span data-ttu-id="07b4a-109">**Cette rubrique contient les sections suivantes :**</span><span class="sxs-lookup"><span data-stu-id="07b4a-109">**This topic contains the following:**</span></span>  
  
-   [<span data-ttu-id="07b4a-110">Résumé des applets de commande</span><span class="sxs-lookup"><span data-stu-id="07b4a-110">Cmdlet Summary</span></span>](#bkmk_cmdlet_sum)  
  
-   [<span data-ttu-id="07b4a-111">Applets de commande de service partagé et de proxy</span><span class="sxs-lookup"><span data-stu-id="07b4a-111">Shared Service and Proxy Cmdlets</span></span>](#bkmk_sharedservice_cmdlets)  
  
-   [<span data-ttu-id="07b4a-112">Applets de commande d’application de service et de proxy</span><span class="sxs-lookup"><span data-stu-id="07b4a-112">Service Application and Proxy Cmdlets</span></span>](#bkmk_serviceapp_cmdlets)  
  
-   [<span data-ttu-id="07b4a-113">Reporting Services des applets de commande de fonctionnalités personnalisées</span><span class="sxs-lookup"><span data-stu-id="07b4a-113">Reporting Services Custom Functionality Cmdlets</span></span>](#bkmk_ssrsfeatures_cmdlets)  
  
-   [<span data-ttu-id="07b4a-114">Exemples de base</span><span class="sxs-lookup"><span data-stu-id="07b4a-114">Basic Samples</span></span>](#bkmk_basic_samples)  
  
-   [<span data-ttu-id="07b4a-115">Exemples détaillés</span><span class="sxs-lookup"><span data-stu-id="07b4a-115">Detailed Samples</span></span>](#bkmk_detailedsamples)  
  
    -   [<span data-ttu-id="07b4a-116">Créer une application de service Reporting Services et un proxy</span><span class="sxs-lookup"><span data-stu-id="07b4a-116">Create a Reporting Services service application and proxy</span></span>](#bkmk_example_create_service_application)  
  
    -   [<span data-ttu-id="07b4a-117">Analyse et mise à jour d'une extension de remise Reporting Services</span><span class="sxs-lookup"><span data-stu-id="07b4a-117">Review and update a Reporting Services delivery extension</span></span>](#bkmk_example_delivery_extension)  
  
    -   [<span data-ttu-id="07b4a-118">Obtenir et définir les propriétés de la base de données d'application Reporting Services, par exemple le délai d'expiration de la base de données</span><span class="sxs-lookup"><span data-stu-id="07b4a-118">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>](#bkmk_example_db_properties)  
  
    -   [<span data-ttu-id="07b4a-119">Répertorier les extensions de données Reporting Services-mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="07b4a-119">List reporting services data extensions - SharePoint mode</span></span>](#bkmk_example_list_data_extensions)  
  
    -   [<span data-ttu-id="07b4a-120">Modifier et répertorier les propriétaires d'abonnement</span><span class="sxs-lookup"><span data-stu-id="07b4a-120">Change and list subscription owners</span></span>](#bkmk_change_subscription_owner)  
  
##  <a name="cmdlet-summary"></a><a name="bkmk_cmdlet_sum"></a><span data-ttu-id="07b4a-121">Résumé de l’applet de commande</span><span class="sxs-lookup"><span data-stu-id="07b4a-121">Cmdlet Summary</span></span>  

 <span data-ttu-id="07b4a-122">Pour exécuter les applets de commande, vous devez ouvrir SharePoint Management Shell.</span><span class="sxs-lookup"><span data-stu-id="07b4a-122">To run the cmdlets you need to open the SharePoint Management Shell.</span></span> <span data-ttu-id="07b4a-123">Vous pouvez aussi utiliser l’éditeur d’interface utilisateur graphique fourni avec Microsoft Windows : **l’Environnement d’écriture de scripts intégré de Windows PowerShell (ISE)**.</span><span class="sxs-lookup"><span data-stu-id="07b4a-123">You can also use the graphical user interface editor that is included with Microsoft Windows, **Windows PowerShell Integrated Scripting Environment (ISE)**.</span></span> <span data-ttu-id="07b4a-124">Pour plus d’informations, consultez [Démarrage de Windows PowerShell sur Windows Server](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="07b4a-124">For more information, see [Starting Windows PowerShell on Windows Server](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell).</span></span> <span data-ttu-id="07b4a-125">Dans les résumés d’applets de commande suivants, les références aux bases de données de l’application de service font référence à toutes les bases de données créées et utilisées par une [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] application de service.</span><span class="sxs-lookup"><span data-stu-id="07b4a-125">In the following cmdlet summaries, the references to service application 'databases', refer to all of the databases created and used by a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="07b4a-126">Cela inclut la configuration, la définition d'alertes et les bases de données temp.</span><span class="sxs-lookup"><span data-stu-id="07b4a-126">This includes the configuration, alerting, and temp databases.</span></span>  

  
 <span data-ttu-id="07b4a-127">Si vous voyez un message d'erreur semblable au suivant lorsque vous tapez les exemples PowerShell :</span><span class="sxs-lookup"><span data-stu-id="07b4a-127">If you see an error message similar to the following when you type the PowerShell examples:</span></span>  
  
-   <span data-ttu-id="07b4a-128">Install-SPRSService : Le terme 'Install-SPRSService' n'est pas reconnu comme</span><span class="sxs-lookup"><span data-stu-id="07b4a-128">Install-SPRSService : The term 'Install-SPRSService' is not recognized as the</span></span>  
    <span data-ttu-id="07b4a-129">nom d'applet de commande, fonction, fichier de script ou programme exécutable.</span><span class="sxs-lookup"><span data-stu-id="07b4a-129">name of a cmdlet, function, script file, or operable program.</span></span> <span data-ttu-id="07b4a-130">Vérifiez l’orthographe du nom ou, si un chemin d’accès a été inclus, vérifiez que le chemin d’accès est correct et réessayez.</span><span class="sxs-lookup"><span data-stu-id="07b4a-130">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>  
  
 <span data-ttu-id="07b4a-131">Un des problèmes suivants se produit :</span><span class="sxs-lookup"><span data-stu-id="07b4a-131">One of the following issues is occurring:</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="07b4a-132">n'est pas installé et par conséquent, les applets de commande [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ne sont pas installées.</span><span class="sxs-lookup"><span data-stu-id="07b4a-132">SharePoint mode is not installed and therefore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets are not installed.</span></span>  
  
-   <span data-ttu-id="07b4a-133">Vous avez exécuté la commande PowerShell dans Windows PowerShell ou Windows PowerShell ISE au lieu de SharePoint Management Shell.</span><span class="sxs-lookup"><span data-stu-id="07b4a-133">You ran the PowerShell command in Windows PowerShell or Windows PowerShell ISE instead of the SharePoint Management Shell.</span></span> <span data-ttu-id="07b4a-134">Utilisez SharePoint Management Shell ou ajoutez le composant logiciel enfichable SharePoint à la fenêtre Windows PowerShell à l'aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="07b4a-134">Use the SharePoint Management shell or add the SharePoint Snap-in to the Windows PowerShell window with the following command:</span></span>  
  
    ```powershell
    Add-PSSnapin Microsoft.SharePoint.PowerShell  
    ```  
  
 <span data-ttu-id="07b4a-135">Pour plus d’informations, consultez [utiliser Windows PowerShell pour administrer SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) ( https://technet.microsoft.com/library/ee806878.aspx) .</span><span class="sxs-lookup"><span data-stu-id="07b4a-135">For more information see [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878.aspx) (https://technet.microsoft.com/library/ee806878.aspx).</span></span>  
  
#### <a name="to-open-the-sharepoint-management-shell-and-run-cmdlets"></a><span data-ttu-id="07b4a-136">Pour ouvrir SharePoint Management Shell et exécuter les applets de commande</span><span class="sxs-lookup"><span data-stu-id="07b4a-136">To Open the SharePoint Management Shell and run cmdlets</span></span>  
  
1.  <span data-ttu-id="07b4a-137">Cliquez sur le bouton **Démarrer**</span><span class="sxs-lookup"><span data-stu-id="07b4a-137">Click the **Start** button</span></span>  
  
2.  <span data-ttu-id="07b4a-138">Cliquez sur le groupe **Produits Microsoft SharePoint** .</span><span class="sxs-lookup"><span data-stu-id="07b4a-138">Click the **Microsoft SharePoint Products** group.</span></span>  
  
3.  <span data-ttu-id="07b4a-139">Cliquez sur **SharePoint Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="07b4a-139">Click the **SharePoint Management Shell**.</span></span>  
  
 <span data-ttu-id="07b4a-140">Pour consulter l’aide sur la ligne de commande pour une applet de commande, utilisez la commande « Get-Help » de PowerShell à l’invite de commandes PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07b4a-140">To view command line help for a cmdlet use the PowerShell 'Get-Help' command at the PowerShell command prompt.</span></span> <span data-ttu-id="07b4a-141">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="07b4a-141">For example:</span></span>  
  
 `Get-Help Get-SPRSServiceApplicationServers`  
  
###  <a name="shared-service-and-proxy-cmdlets"></a><a name="bkmk_sharedservice_cmdlets"></a><span data-ttu-id="07b4a-142">Applets de commande de service partagé et de proxy</span><span class="sxs-lookup"><span data-stu-id="07b4a-142">Shared Service and Proxy Cmdlets</span></span>  
 <span data-ttu-id="07b4a-143">Le tableau suivant contient les applets de commande PowerShell pour le service partagé [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07b4a-143">The following table contains the PowerShell cmdlets for the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint shared service.</span></span>  
  
|<span data-ttu-id="07b4a-144">Applet de commande</span><span class="sxs-lookup"><span data-stu-id="07b4a-144">Cmdlet</span></span>|<span data-ttu-id="07b4a-145">Description</span><span class="sxs-lookup"><span data-stu-id="07b4a-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="07b4a-146">Install-SPRSService</span><span class="sxs-lookup"><span data-stu-id="07b4a-146">Install-SPRSService</span></span>|<span data-ttu-id="07b4a-147">Installe et enregistre, ou désinstalle, le service partagé [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-147">Installs and registers, or uninstalls, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="07b4a-148">Cette opération peut être effectuée uniquement sur l'ordinateur qui dispose d'une installation de SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07b4a-148">This can be done only on the machine that has an installation of SQL Server [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="07b4a-149">Pour l'installation, deux opérations ont lieu :</span><span class="sxs-lookup"><span data-stu-id="07b4a-149">For installation, two operations occur:</span></span><br /><br /> <span data-ttu-id="07b4a-150">1) le [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service est installé dans la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="07b4a-150">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is installed in the farm.</span></span><br /><br /> <span data-ttu-id="07b4a-151">2) l' [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] instance de service est installée sur l’ordinateur actuel.</span><span class="sxs-lookup"><span data-stu-id="07b4a-151">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service instance is installed to the current machine.</span></span><br /><br /> <span data-ttu-id="07b4a-152">Pour la désinstallation, deux opérations ont lieu :</span><span class="sxs-lookup"><span data-stu-id="07b4a-152">For Uninstallation, two operations occur:</span></span><br /><span data-ttu-id="07b4a-153">1) le [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service est désinstallé de l’ordinateur actuel.</span><span class="sxs-lookup"><span data-stu-id="07b4a-153">1) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the current machine.</span></span><br /><span data-ttu-id="07b4a-154">2) le [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service est désinstallé de la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="07b4a-154">2) The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service is uninstalled from the farm.</span></span><br /><br /> <br /><br /> <span data-ttu-id="07b4a-155">Remarque : si d'autres ordinateurs dans la batterie de serveurs ont le service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] installée ou, si des applications de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] s'exécutent toujours dans la batterie de serveurs, un avertissement s'affiche.</span><span class="sxs-lookup"><span data-stu-id="07b4a-155">NOTE: If there are any other machines in the farm that have the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service installed, or if there are still [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications running in the farm, a warning message is displayed.</span></span>|  
|<span data-ttu-id="07b4a-156">Install-SPRSServiceProxy</span><span class="sxs-lookup"><span data-stu-id="07b4a-156">Install-SPRSServiceProxy</span></span>|<span data-ttu-id="07b4a-157">Installe et enregistre, ou désinstalle, le proxy du service Reporting Services dans la batterie de serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07b4a-157">Installs and registers, or uninstalls, the Reporting Services service proxy in the SharePoint farm.</span></span>|  
|<span data-ttu-id="07b4a-158">Get-SPRSProxyUrl</span><span class="sxs-lookup"><span data-stu-id="07b4a-158">Get-SPRSProxyUrl</span></span>|<span data-ttu-id="07b4a-159">Obtient les URL pour accéder au service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-159">Gets the URL(s) for accessing the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="07b4a-160">Get-SPRSServiceApplicationServers</span><span class="sxs-lookup"><span data-stu-id="07b4a-160">Get-SPRSServiceApplicationServers</span></span>|<span data-ttu-id="07b4a-161">Obtient tous les serveurs dans la batterie SharePoint locale qui contiennent une installation du service partagé [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-161">Gets all servers in the local SharePoint farm that contain an installation of the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] shared service.</span></span> <span data-ttu-id="07b4a-162">Cette applet de commande est utile pour les mises à niveau de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , car elle permet de déterminer quels serveurs exécutent le service partagé et doivent, par conséquent, être mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="07b4a-162">This cmdlet is useful for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] upgrades, to determine which servers run the shared service and therefore need to be upgraded.</span></span>|  
  
###  <a name="service-application-and-proxy-cmdlets"></a><a name="bkmk_serviceapp_cmdlets"></a> <span data-ttu-id="07b4a-163">Applets de commande d'application de service et de proxy</span><span class="sxs-lookup"><span data-stu-id="07b4a-163">Service Application and Proxy Cmdlets</span></span>  
 <span data-ttu-id="07b4a-164">Le tableau suivant contient les applets de commande PowerShell pour les applications de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] et leurs proxys associés.</span><span class="sxs-lookup"><span data-stu-id="07b4a-164">The following table contains the PowerShell cmdlets for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications and their associated proxies.</span></span>  
  
|<span data-ttu-id="07b4a-165">Applet de commande</span><span class="sxs-lookup"><span data-stu-id="07b4a-165">cmdlet</span></span>|<span data-ttu-id="07b4a-166">Description</span><span class="sxs-lookup"><span data-stu-id="07b4a-166">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="07b4a-167">Get-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="07b4a-167">Get-SPRSServiceApplication</span></span>|<span data-ttu-id="07b4a-168">Obtient un ou plusieurs objets d'application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-168">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application objects.</span></span>|  
|<span data-ttu-id="07b4a-169">New-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="07b4a-169">New-SPRSServiceApplication</span></span>|<span data-ttu-id="07b4a-170">Crée une application de service Reporting Services et des bases de données associées.</span><span class="sxs-lookup"><span data-stu-id="07b4a-170">Create a new Reporting Services service application and associated databases.</span></span><br /><br /> <span data-ttu-id="07b4a-171">Paramètre LogonType : spécifie si le serveur de rapports utilise le compte de pool d'applications SSRS ou un compte de connexion SQL Server pour accéder à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="07b4a-171">LogonType Parameter: Specifies if the report server uses the SSRS Application Pool account or a SQL Server login to access the report server database.</span></span> <span data-ttu-id="07b4a-172">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="07b4a-172">It can be one of the following:</span></span><br /><br /> <span data-ttu-id="07b4a-173">0 Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="07b4a-173">0 Windows Authentication</span></span><br /><br /> <span data-ttu-id="07b4a-174">1 SQL Server</span><span class="sxs-lookup"><span data-stu-id="07b4a-174">1 SQL Server</span></span><br /><br /> <span data-ttu-id="07b4a-175">2. Compte du pool d'applications (valeur par défaut)</span><span class="sxs-lookup"><span data-stu-id="07b4a-175">2 Application Pool Account (default)</span></span>|  
|<span data-ttu-id="07b4a-176">Remove-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="07b4a-176">Remove-SPRSServiceApplication</span></span>|<span data-ttu-id="07b4a-177">Supprime l'application de service Reporting Services spécifiée.</span><span class="sxs-lookup"><span data-stu-id="07b4a-177">Removes the specified Reporting Services service application.</span></span> <span data-ttu-id="07b4a-178">Cela supprimera également les bases de données associées.</span><span class="sxs-lookup"><span data-stu-id="07b4a-178">This will also remove the associated databases.</span></span>|  
|<span data-ttu-id="07b4a-179">Set-SPRSServiceApplication</span><span class="sxs-lookup"><span data-stu-id="07b4a-179">Set-SPRSServiceApplication</span></span>|<span data-ttu-id="07b4a-180">Modifie les propriétés d'une base de données d'application de service Reporting Services existante.</span><span class="sxs-lookup"><span data-stu-id="07b4a-180">Edits the properties of an existing Reporting Services service application.</span></span>|  
|<span data-ttu-id="07b4a-181">New-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="07b4a-181">New-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="07b4a-182">Crée un nouveau proxy d'application de service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="07b4a-182">Creates a new Reporting Services service application proxy.</span></span>|  
|<span data-ttu-id="07b4a-183">Get-SPRSServiceApplicationProxy</span><span class="sxs-lookup"><span data-stu-id="07b4a-183">Get-SPRSServiceApplicationProxy</span></span>|<span data-ttu-id="07b4a-184">Obtient un ou plusieurs proxys d'application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-184">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application proxies.</span></span>|  
|<span data-ttu-id="07b4a-185">Dismount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="07b4a-185">Dismount-SPRSDatabase</span></span>|<span data-ttu-id="07b4a-186">Démonte les bases de données d'application de service pour une application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-186">Dismounts the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="07b4a-187">Remove-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="07b4a-187">Remove-SPRSDatabase</span></span>|<span data-ttu-id="07b4a-188">Supprime les bases de données d'application de service pour une application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-188">Remove the service application databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="07b4a-189">Set-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="07b4a-189">Set-SPRSDatabase</span></span>|<span data-ttu-id="07b4a-190">Définit les propriétés des bases de données associées à une application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-190">Sets the properties of the databases associated to a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="07b4a-191">Mount-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="07b4a-191">Mount-SPRSDatabase</span></span>|<span data-ttu-id="07b4a-192">Monte les bases de données pour une application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-192">Mounts databases for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="07b4a-193">New-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="07b4a-193">New-SPRSDatabase</span></span>|<span data-ttu-id="07b4a-194">Crée les nouvelles bases de données d'application de service pour l'application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] spécifiée.</span><span class="sxs-lookup"><span data-stu-id="07b4a-194">Create new service application databases for the specified [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>|  
|<span data-ttu-id="07b4a-195">Get-SPRSDatabaseCreationScript</span><span class="sxs-lookup"><span data-stu-id="07b4a-195">Get-SPRSDatabaseCreationScript</span></span>|<span data-ttu-id="07b4a-196">Génère le script de création de base de données à l'écran pour une application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-196">Outputs the database creation script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="07b4a-197">Vous pouvez ensuite exécuter le script dans SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="07b4a-197">You can then run the script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="07b4a-198">Get-SPRSDatabase</span><span class="sxs-lookup"><span data-stu-id="07b4a-198">Get-SPRSDatabase</span></span>|<span data-ttu-id="07b4a-199">Obtient une ou plusieurs bases de données d'application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-199">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases.</span></span> <span data-ttu-id="07b4a-200">Utilisez la commande pour obtenir l'ID de la base de données d'application de service afin d'utiliser l'applet de commande Set-SPRSDatabase pour modifier les propriétés, par exemple `querytimeout`.</span><span class="sxs-lookup"><span data-stu-id="07b4a-200">Use the command to get the ID of service application database so you can use the Set-SPRSDatabase comdlet to modify properties, for example the `querytimeout`.</span></span> <span data-ttu-id="07b4a-201">Consultez l'exemple de la rubrique, [Obtenir et définir les propriétés de la base de données d'application Reporting Services, par exemple le délai d'expiration de la base de données](#bkmk_example_db_properties).</span><span class="sxs-lookup"><span data-stu-id="07b4a-201">See the example in this topic, [Get and set properties of the Reporting Servicea application database, for example database timeout](#bkmk_example_db_properties).</span></span>|  
|<span data-ttu-id="07b4a-202">Get-SPRSDatabaseRightsScript</span><span class="sxs-lookup"><span data-stu-id="07b4a-202">Get-SPRSDatabaseRightsScript</span></span>|<span data-ttu-id="07b4a-203">Génère le script des droits de la base de données à l'écran pour une application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-203">Outputs the database rights script to the screen for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="07b4a-204">Invite à entrer l'utilisateur et la base de données souhaités, puis retourne un script Transact-SQL que vous pouvez exécuter pour modifier des autorisations.</span><span class="sxs-lookup"><span data-stu-id="07b4a-204">It will prompt for desired user and database then returns transact SQL you can run to modify permissions.</span></span> <span data-ttu-id="07b4a-205">Vous pouvez ensuite exécuter ce script dans SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="07b4a-205">You can then run this script in SQL Server Management Studio.</span></span>|  
|<span data-ttu-id="07b4a-206">Get-SPRSDatabaseUpgradeScript</span><span class="sxs-lookup"><span data-stu-id="07b4a-206">Get-SPRSDatabaseUpgradeScript</span></span>|<span data-ttu-id="07b4a-207">Génère un script de mise à niveau de base de données à l'écran.</span><span class="sxs-lookup"><span data-stu-id="07b4a-207">Outputs a database upgrade script to the screen.</span></span> <span data-ttu-id="07b4a-208">Le script met à niveau les bases de données d'application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] vers la version de la base de données de l'installation actuelle de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-208">The script will upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application databases to the database version of the current [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] installation.</span></span>|  
  
###  <a name="reporting-services-custom-functionality-cmdlets"></a><a name="bkmk_ssrsfeatures_cmdlets"></a><span data-ttu-id="07b4a-209">Reporting Services des applets de commande de fonctionnalités personnalisées</span><span class="sxs-lookup"><span data-stu-id="07b4a-209">Reporting Services Custom Functionality Cmdlets</span></span>  
  
|<span data-ttu-id="07b4a-210">Applet de commande</span><span class="sxs-lookup"><span data-stu-id="07b4a-210">Cmdlet</span></span>|<span data-ttu-id="07b4a-211">Description</span><span class="sxs-lookup"><span data-stu-id="07b4a-211">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="07b4a-212">Update-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="07b4a-212">Update-SPRSEncryptionKey</span></span>|<span data-ttu-id="07b4a-213">Met à jour la clé de chiffrement de l'application de service Reporting Services spécifiée et re-chiffre ses données.</span><span class="sxs-lookup"><span data-stu-id="07b4a-213">Updates the encryption key for the specified Reporting Services service application and re-encrypts its data.</span></span>|  
|<span data-ttu-id="07b4a-214">Restore-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="07b4a-214">Restore-SPRSEncryptionKey</span></span>|<span data-ttu-id="07b4a-215">Restaure une clé de chiffrement précédemment sauvegardée pour une application de service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="07b4a-215">Restores a previously backed up encryption key for a Reporting Services service application.</span></span>|  
|<span data-ttu-id="07b4a-216">Remove-SPRSEncryptedData</span><span class="sxs-lookup"><span data-stu-id="07b4a-216">Remove-SPRSEncryptedData</span></span>|<span data-ttu-id="07b4a-217">Supprime les données chiffrées de l'application de service Reporting Services spécifiée.</span><span class="sxs-lookup"><span data-stu-id="07b4a-217">Delete the encrypted data for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="07b4a-218">Backup-SPRSEncryptionKey</span><span class="sxs-lookup"><span data-stu-id="07b4a-218">Backup-SPRSEncryptionKey</span></span>|<span data-ttu-id="07b4a-219">Sauvegarde la clé de chiffrement de l'application de service Reporting Services spécifiée.</span><span class="sxs-lookup"><span data-stu-id="07b4a-219">Backs up the encryption key for the specified Reporting Services service application.</span></span>|  
|<span data-ttu-id="07b4a-220">New-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="07b4a-220">New-SPRSExtension</span></span>|<span data-ttu-id="07b4a-221">Enregistre une nouvelle extension avec une application de service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="07b4a-221">Registers a new extension with a Reporting Services service application.</span></span>|  
|<span data-ttu-id="07b4a-222">Set-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="07b4a-222">Set-SPRSExtension</span></span>|<span data-ttu-id="07b4a-223">Définit les propriétés d'une extension Reporting Services existante.</span><span class="sxs-lookup"><span data-stu-id="07b4a-223">Sets the properties of an existing Reporting Services extension.</span></span>|  
|<span data-ttu-id="07b4a-224">Remove-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="07b4a-224">Remove-SPRSExtension</span></span>|<span data-ttu-id="07b4a-225">Supprime une extension d'une application de service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="07b4a-225">Removes an extension from a Reporting Services service application.</span></span>|  
|<span data-ttu-id="07b4a-226">Get-SPRSExtension</span><span class="sxs-lookup"><span data-stu-id="07b4a-226">Get-SPRSExtension</span></span>|<span data-ttu-id="07b4a-227">Obtient une ou plusieurs extensions d' [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pour une application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-227">Gets one or more [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] extensions for a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span><br /><br /> <span data-ttu-id="07b4a-228">Les valeurs autorisées sont :</span><span class="sxs-lookup"><span data-stu-id="07b4a-228">Valid values are:</span></span><br /><br /> <span data-ttu-id="07b4a-229">**Distribution**</span><span class="sxs-lookup"><span data-stu-id="07b4a-229">**Delivery**</span></span><br /><br /> <span data-ttu-id="07b4a-230">**DeliveryUI**</span><span class="sxs-lookup"><span data-stu-id="07b4a-230">**DeliveryUI**</span></span><br /><br /> <span data-ttu-id="07b4a-231">**Render**</span><span class="sxs-lookup"><span data-stu-id="07b4a-231">**Render**</span></span><br /><br /> <span data-ttu-id="07b4a-232">**Données**</span><span class="sxs-lookup"><span data-stu-id="07b4a-232">**Data**</span></span><br /><br /> <span data-ttu-id="07b4a-233">**Sécurité**</span><span class="sxs-lookup"><span data-stu-id="07b4a-233">**Security**</span></span><br /><br /> <span data-ttu-id="07b4a-234">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="07b4a-234">**Authentication**</span></span><br /><br /> <span data-ttu-id="07b4a-235">**EventProcessing**</span><span class="sxs-lookup"><span data-stu-id="07b4a-235">**EventProcessing**</span></span><br /><br /> <span data-ttu-id="07b4a-236">**ReportItems**</span><span class="sxs-lookup"><span data-stu-id="07b4a-236">**ReportItems**</span></span><br /><br /> <span data-ttu-id="07b4a-237">**Designer**</span><span class="sxs-lookup"><span data-stu-id="07b4a-237">**Designer**</span></span><br /><br /> <span data-ttu-id="07b4a-238">**ReportItemDesigner**</span><span class="sxs-lookup"><span data-stu-id="07b4a-238">**ReportItemDesigner**</span></span><br /><br /> <span data-ttu-id="07b4a-239">**ReportItemConverter**</span><span class="sxs-lookup"><span data-stu-id="07b4a-239">**ReportItemConverter**</span></span><br /><br /> <span data-ttu-id="07b4a-240">**ReportDefinitionCustomization**</span><span class="sxs-lookup"><span data-stu-id="07b4a-240">**ReportDefinitionCustomization**</span></span>|  
|<span data-ttu-id="07b4a-241">Get-SPRSSite</span><span class="sxs-lookup"><span data-stu-id="07b4a-241">Get-SPRSSite</span></span>|<span data-ttu-id="07b4a-242">Obtient les sites SharePoint en fonction de l'activation de la fonction « ReportingService ».</span><span class="sxs-lookup"><span data-stu-id="07b4a-242">Gets the SharePoint sites based on whether the "ReportingService" feature is enabled.</span></span> <span data-ttu-id="07b4a-243">Par défaut, les sites qui activent la fonction « ReportingService » sont retournés.</span><span class="sxs-lookup"><span data-stu-id="07b4a-243">By default, sites that enable the "ReportingService" feature are returned.</span></span>|  
  
##  <a name="basic-samples"></a><a name="bkmk_basic_samples"></a><span data-ttu-id="07b4a-244">Exemples de base</span><span class="sxs-lookup"><span data-stu-id="07b4a-244">Basic Samples</span></span>  
 <span data-ttu-id="07b4a-245">Retournez la liste des applets de commande qui contiennent « SPRS » dans le nom.</span><span class="sxs-lookup"><span data-stu-id="07b4a-245">Return a list of cmdlets that contain 'SPRS' in the name.</span></span> <span data-ttu-id="07b4a-246">Ce sera la liste complète des applets de commande de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07b4a-246">This will be the full list of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] cmdlets.</span></span>  
  
```powershell
Get-command -noun *SPRS*  
```  
  
 <span data-ttu-id="07b4a-247">Ou bien, vous serez redirigés vers un fichier texte nommé commandlist.txt contenant plus de détails.</span><span class="sxs-lookup"><span data-stu-id="07b4a-247">Or with a little more detail, piped to a text file named commandlist.txt</span></span>  
  
```powershell
Get-Command -Noun *SPRS* | Select name, definition | Format-List | Out-File c:\commandlist.txt  
```  
  
 <span data-ttu-id="07b4a-248">Installez le service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint et le proxy de service.</span><span class="sxs-lookup"><span data-stu-id="07b4a-248">Install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] SharePoint service and service proxy.</span></span>  
  
```powershell
Install-SPRSService  
```  
  
```powershell
Install-SPRSServiceProxy  
```  
  
 <span data-ttu-id="07b4a-249">Démarrer le service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07b4a-249">Start the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service</span></span>  
  
```powershell
Get-SPServiceInstance -all | where {$_.TypeName -like "SQL Server Reporting*"} | Start-SPServiceInstance  
```  
  
 <span data-ttu-id="07b4a-250">Tapez la commande suivante à partir de SharePoint Management Shell pour retourner une liste filtrée des lignes du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="07b4a-250">Type the following command from the SharePoint Management Shell to return a filtered list of rows from the a log file.</span></span> <span data-ttu-id="07b4a-251">La commande filtre les lignes qui contiennent « ssrscustomactionerror ».</span><span class="sxs-lookup"><span data-stu-id="07b4a-251">The command will filter for lines that contain "ssrscustomactionerror".</span></span> <span data-ttu-id="07b4a-252">Cet exemple consulte le fichier journal créé lorsque le fichier rssharepoint.msi a été installé.</span><span class="sxs-lookup"><span data-stu-id="07b4a-252">This example is looking at the log file created when the rssharepoint.msi was installed.</span></span>  
  
```powershell
Get-Content -Path C:\Users\testuser\AppData\Local\Temp\rs_sp_0.log | Select-String "ssrscustomactionerror"  
```  
  
##  <a name="detailed-samples"></a><a name="bkmk_detailedsamples"></a><span data-ttu-id="07b4a-253">Exemples détaillés</span><span class="sxs-lookup"><span data-stu-id="07b4a-253">Detailed Samples</span></span>  
 <span data-ttu-id="07b4a-254">En plus des exemples suivants, consultez la section « script Windows PowerShell » dans la rubrique [script Windows PowerShell pour les étapes 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span><span class="sxs-lookup"><span data-stu-id="07b4a-254">In addition to the following samples, see the section "Windows PowerShell Script" in the topic [Windows PowerShell script for Steps 1-4](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2013.md#bkmk_full_script).</span></span>  
  
###  <a name="create-a-reporting-services-service-application-and-proxy"></a><a name="bkmk_example_create_service_application"></a><span data-ttu-id="07b4a-255">Créer une application de service Reporting Services et un proxy</span><span class="sxs-lookup"><span data-stu-id="07b4a-255">Create a Reporting Services service application and proxy</span></span>  
 <span data-ttu-id="07b4a-256">Cet exemple de script effectue les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="07b4a-256">This sample script completes the following tasks:</span></span>  
  
1.  <span data-ttu-id="07b4a-257">Création d'une application de service Reporting Services et d'un proxy.</span><span class="sxs-lookup"><span data-stu-id="07b4a-257">Create a Reporting Services service application and proxy.</span></span> <span data-ttu-id="07b4a-258">Le script suppose que le pool d’applications « My App Pool » existe déjà.</span><span class="sxs-lookup"><span data-stu-id="07b4a-258">The script assumes the application pool "My App Pool" already exists.</span></span>  
  
2.  <span data-ttu-id="07b4a-259">Ajout du proxy au groupe de proxy par défaut</span><span class="sxs-lookup"><span data-stu-id="07b4a-259">Add the proxy to the default proxy group</span></span>  
  
3.  <span data-ttu-id="07b4a-260">Octroi de l’accès à l’application de service à la base de données de contenu de l’application web sur le port 80.</span><span class="sxs-lookup"><span data-stu-id="07b4a-260">Grant the service app access to the port 80 web app's content database.</span></span> <span data-ttu-id="07b4a-261">Le script suppose que le site « http://sitename » existe déjà.</span><span class="sxs-lookup"><span data-stu-id="07b4a-261">The script assumes site "http://sitename" already exists.</span></span>  
  
```powershell
# Create service application and service application proxy  
$appPool = Get-SPServiceApplicationPool "My App Pool"  
$serviceApp = New-SPRSServiceApplication "My RS Service App" -ApplicationPool $appPool  
$serviceAppProxy = New-SPRSServiceApplicationProxy -Name "My RS Service App Proxy" -ServiceApplication $serviceApp  
  
# Add service application proxy to default proxy group.  Any web application that uses the default proxy group will now be able to use this service application.  
Get-SPServiceApplicationProxyGroup -default | Add-SPServiceApplicationProxyGroupMember -Member $serviceAppProxy  
  
# Grant application pool account access to the port 80 web application's content database.  
$webApp = Get-SPWebApplication "http://sitename"  
$appPoolAccountName = $appPool.ProcessAccount.LookupName()  
$webApp.GrantAccessToProcessIdentity($appPoolAccountName)
```  
  
###  <a name="review-and-update-a-reporting-services-delivery-extension"></a><a name="bkmk_example_delivery_extension"></a><span data-ttu-id="07b4a-262">Examiner et mettre à jour une extension de remise Reporting Services</span><span class="sxs-lookup"><span data-stu-id="07b4a-262">Review and update a Reporting Services delivery extension</span></span>  
 <span data-ttu-id="07b4a-263">L’exemple de script PowerShell suivant met à jour la configuration de l’extension de remise du courrier électronique par le serveur de rapports pour l’application de service nommée `My RS Service App`.</span><span class="sxs-lookup"><span data-stu-id="07b4a-263">The following PowerShell script example, updates the configuration for the report server e-mail delivery extension for the service application named `My RS Service App`.</span></span> <span data-ttu-id="07b4a-264">Mettez à jour les valeurs du serveur SMTP (`<email server name>`) et de l’alias de messagerie électronique FROM (`<your FROM email address>`).</span><span class="sxs-lookup"><span data-stu-id="07b4a-264">Update the values for the SMTP server (`<email server name>`) and the FROM email alias (`<your FROM email address>`).</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication -Name "My RS Service App"  
$emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
$emailXml = [xml]$emailCfg
$emailXml.SelectSingleNode("//SMTPServer").InnerText = "<email server name>"  
$emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
$emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
$emailXml.SelectSingleNode("//From").InnerText = '<your FROM email address>'  
Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
```  
  
 <span data-ttu-id="07b4a-265">Dans l'exemple ci-dessus, si vous ne connaissiez pas le nom exact de l'application de service, vous pouvez réécrire la première instruction pour obtenir l'application de service en fonction d'une recherche portant sur son nom partiel.</span><span class="sxs-lookup"><span data-stu-id="07b4a-265">In the above example if you did not know the exact name of the service application, you could rewrite the first statement to get the service application based on a search of the partial name.</span></span> <span data-ttu-id="07b4a-266">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="07b4a-266">For example:</span></span>  
  
```powershell
$app = Get-SPRSServiceApplication | Where {$_.name -like " ssrs_testapp *"}  
```  
  
 <span data-ttu-id="07b4a-267">Le script suivant retourne les valeurs de configuration actuelles pour l’extension de remise de courrier électronique du serveur de rapports pour l’application de service nommée « Application Reporting Services ».</span><span class="sxs-lookup"><span data-stu-id="07b4a-267">The following script will return the current configuration values for the report server e-mail delivery extension for the service application named "Reporting Services Application".</span></span> <span data-ttu-id="07b4a-268">La première étape définit la valeur de la variable $app pour l'objet de l'application de service dont le nom est « My RS Service App ».</span><span class="sxs-lookup"><span data-stu-id="07b4a-268">The first step sets the value of the variable $app to the object of the service application that has a name of " My RS Service App "</span></span>  
  
 <span data-ttu-id="07b4a-269">La deuxième instruction obtiendra l’extension de remise « Report Server Email » pour l’objet d’application de service dans la variable $app, puis sélectionne le configuration XML.</span><span class="sxs-lookup"><span data-stu-id="07b4a-269">The second statement will Get the 'Report Server Email' delivery extension for the service application object in variable $app, and select the configurationXML</span></span>  
  
```powershell
$app = Get-SPRSServiceapplication -Name "Reporting Services Application"  
Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
 <span data-ttu-id="07b4a-270">Vous pouvez réécrire les deux instructions ci-dessus dans une seule :</span><span class="sxs-lookup"><span data-stu-id="07b4a-270">You can also rewrite the above two statements as one:</span></span>  
  
```powershell
Get-SPRSServiceApplication -Name "Reporting Services Application" | Get-SPRSExtension -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
```  
  
###  <a name="get-and-set-properties-of-the-reporting-servicea-application-database-for-example-database-timeout"></a><a name="bkmk_example_db_properties"></a><span data-ttu-id="07b4a-271">Obtenir et définir les propriétés de la base de données d’application Reporting Services, par exemple le délai d’expiration de la base de données</span><span class="sxs-lookup"><span data-stu-id="07b4a-271">Get and set properties of the Reporting Servicea application database, for example database timeout</span></span>  
 <span data-ttu-id="07b4a-272">L'exemple suivant renvoie d'abord une liste des bases de données et propriétés afin de déterminer le guid (ID) de base de données que vous fournissez à la commande.</span><span class="sxs-lookup"><span data-stu-id="07b4a-272">The following example first returns a list of the databases and properties so you can determine the database guid (ID) that you then supply to the set command.</span></span> <span data-ttu-id="07b4a-273">Pour obtenir une liste complète des propriétés, utilisez `Get-SPRSDatabase | format-list`.</span><span class="sxs-lookup"><span data-stu-id="07b4a-273">For a full list of the properties, use `Get-SPRSDatabase | format-list`.</span></span>  
  
```powershell
Get-SPRSDatabase | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance
```  
  
 <span data-ttu-id="07b4a-274">Voici un exemple de sortie.</span><span class="sxs-lookup"><span data-stu-id="07b4a-274">The following is an example of the output.</span></span> <span data-ttu-id="07b4a-275">Déterminez l'ID de la base de données que vous voulez modifier et utilisez l'ID de l'applet de commande SET.</span><span class="sxs-lookup"><span data-stu-id="07b4a-275">Determine the ID for the database you want to modify and use the ID in the SET cmdlet.</span></span>  
  
-   `Id                : 56f8d1bc-cb04-44cf-bd41-a873643c5a14`  
  
     `QueryTimeout      : 120`  
  
     `ConnectionTimeout : 15`  
  
     `Status            : Online`  
  
     `Server            : SPServer Name=uetestb01`  
  
     `ServiceInstance   : SPDatabaseServiceInstance`  
  
```powershell
Set-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 -QueryTimeout 300  
```  
  
 <span data-ttu-id="07b4a-276">Pour vérifier que la valeur est définie, réexécutez l'applet de commande GET.</span><span class="sxs-lookup"><span data-stu-id="07b4a-276">To verify the value is set, run the GET cmdlet again.</span></span>  
  
```powershell
Get-SPRSDatabase -Identity 56f8d1bc-cb04-44cf-bd41-a873643c5a14 | Select id, querytimeout,connectiontimeout, status, server, ServiceInstance  
```  
  
###  <a name="list-reporting-services-data-extensions---sharepoint-mode"></a><a name="bkmk_example_list_data_extensions"></a><span data-ttu-id="07b4a-277">Répertorier les extensions de données Reporting Services-mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="07b4a-277">List reporting services data extensions - SharePoint mode</span></span>  
 <span data-ttu-id="07b4a-278">L'exemple suivant effectue une itération sur chaque application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] et répertorie les extensions de données actuelles.</span><span class="sxs-lookup"><span data-stu-id="07b4a-278">The following example loops through each [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application and lists the current data extensions for each.</span></span>  
  
```powershell
$apps = Get-SPRSServiceApplication  
foreach ($app in $apps)
{  
Write-host -ForegroundColor "yellow" Service App Name $app.Name  
Get-SPRSExtension -identity $app -ExtensionType "Data" | select name, extensiontype | Format-Table -AutoSize  
}  
```  
  
 <span data-ttu-id="07b4a-279">**Exemple de sortie :**</span><span class="sxs-lookup"><span data-stu-id="07b4a-279">**Example output:**</span></span>  
  
-   `Name           ExtensionType`  
  
     `----           -------------`  
  
     `SQL                     Data`  
  
     `SQLAZURE                Data`  
  
     `SQLPDW                  Data`  
  
     `OLEDB                   Data`  
  
     `OLEDB-MD                Data`  
  
     `ORACLE                  Data`  
  
     `ODBC                    Data`  
  
     `XML                     Data`  
  
     `SHAREPOINTLIST          Data`  
  
###  <a name="change-and-list-subscription-owners"></a><a name="bkmk_change_subscription_owner"></a><span data-ttu-id="07b4a-280">Modifier et répertorier les propriétaires d’abonnements</span><span class="sxs-lookup"><span data-stu-id="07b4a-280">Change and list subscription owners</span></span>  
 <span data-ttu-id="07b4a-281">Consultez [Utiliser PowerShell pour modifier et répertorier Reporting Services propriétaires d’abonnement et exécuter un abonnement](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="07b4a-281">See [Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07b4a-282">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07b4a-282">See Also</span></span>  
 <span data-ttu-id="07b4a-283">[Utiliser PowerShell pour modifier et répertorier Reporting Services propriétaires d’abonnement et exécuter un abonnement](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="07b4a-283">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](subscriptions/manage-subscription-owners-and-run-subscription-powershell.md) </span></span>  
 <span data-ttu-id="07b4a-284">[Liste de vérification : utiliser PowerShell pour vérifier PowerPivot pour SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span><span class="sxs-lookup"><span data-stu-id="07b4a-284">[CheckList: Use PowerShell to Verify PowerPivot for SharePoint](https://docs.microsoft.com/analysis-services/instances/install-windows/checklist-use-powershell-to-verify-power-pivot-for-sharepoint) </span></span>  
 [<span data-ttu-id="07b4a-285">Scripts PowerShell de gestion CodePlex SharePoint</span><span class="sxs-lookup"><span data-stu-id="07b4a-285">CodePlex SharePoint Management PowerShell scripts</span></span>](https://sharepointpsscripts.codeplex.com/)   
