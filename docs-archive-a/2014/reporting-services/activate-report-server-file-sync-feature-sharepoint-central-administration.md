---
title: Activer la fonctionnalité de File Sync du serveur de rapports dans l’administration centrale de SharePoint | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/06/2017
ms.openlocfilehash: 55feac69da85c7287ea56f4b8245350dd7e69565
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611619"
---
# <a name="activate-the-report-server-file-sync-feature-in-sharepoint-central-administration"></a><span data-ttu-id="3e78c-102">Activer la fonctionnalité Synchronisation de fichiers de serveur de rapports dans l'Administration centrale de SharePoint</span><span class="sxs-lookup"><span data-stu-id="3e78c-102">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>

<span data-ttu-id="3e78c-103">La fonctionnalité Synchronisation de fichiers de serveur de rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] utilise des gestionnaires d'événements SharePoint pour synchroniser le catalogue du serveur de rapports avec les éléments des bibliothèques de documents.</span><span class="sxs-lookup"><span data-stu-id="3e78c-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Server File Sync feature utilizes SharePoint event handlers to synchronize the report server catalog with items in document libraries.</span></span> <span data-ttu-id="3e78c-104">Cette fonctionnalité est particulièrement intéressante lorsque des utilisateurs téléchargent fréquemment des éléments de rapport publiés directement dans des bibliothèques de documents SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3e78c-104">This feature is beneficial when users frequently upload published report items directly to SharePoint document libraries.</span></span> <span data-ttu-id="3e78c-105">Si la fonctionnalité de synchronisation de fichiers n’est pas activée, le contenu est toujours synchronisé mais pas aussi fréquemment.</span><span class="sxs-lookup"><span data-stu-id="3e78c-105">If the file Sync feature isn't activated, content will still be synchronized but not as frequently.</span></span>  
  
<span data-ttu-id="3e78c-106">La fonctionnalité Synchronisation de fichiers peut être activée dans l’administration des sites SharePoint après installation du complément [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] pour les produits SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3e78c-106">The File Sync feature can be activated in SharePoint Site Administration after you install the [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span>  
  
<span data-ttu-id="3e78c-107">Cette fonctionnalité peut être activée et désactivée manuellement site par site, mais pas au niveau de la collection de sites.</span><span class="sxs-lookup"><span data-stu-id="3e78c-107">This feature can be manually activated and deactivated per site but not at the site collection level.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e78c-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="3e78c-108">Prerequisites</span></span>  
 <span data-ttu-id="3e78c-109">Le complément [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pour SharePoint doit être installé.</span><span class="sxs-lookup"><span data-stu-id="3e78c-109">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in for SharePoint must be installed.</span></span> <span data-ttu-id="3e78c-110">Si le complément n’est pas installé, la fonctionnalité de synchronisation de fichiers ne sera pas visible dans la liste des fonctionnalités du site.</span><span class="sxs-lookup"><span data-stu-id="3e78c-110">If the add-in isn't installed, the file sync feature won't be visible in the site feature list.</span></span>  
  
 <span data-ttu-id="3e78c-111">Pour vérifier l'installation, consultez la liste des applications installées dans le [!INCLUDE[msCoName](../includes/msconame-md.md)]\*\*Panneau de configuration \*\*Windows.</span><span class="sxs-lookup"><span data-stu-id="3e78c-111">To verify installation, view the list of installed applications in [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows **Control Panel**.</span></span> <span data-ttu-id="3e78c-112">Si le complément [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] est installé, suivez les instructions fournies dans cette rubrique pour activer la fonctionnalité de synchronisation de fichiers.</span><span class="sxs-lookup"><span data-stu-id="3e78c-112">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in is installed, follow the instructions in this topic to activate the report server file sync feature.</span></span>  
  
### <a name="to-activate-or-deactivate-the-reporting-services-file-sync-feature-on-a-site"></a><span data-ttu-id="3e78c-113">Pour activer ou désactiver la fonctionnalité Synchronisation de fichiers de serveur de rapports sur un site</span><span class="sxs-lookup"><span data-stu-id="3e78c-113">To activate or deactivate the Reporting Services File Sync feature on a Site</span></span>  
  
1.  <span data-ttu-id="3e78c-114">Dans la page principale de votre site, cliquez sur le menu **actions du site** , puis sur **paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="3e78c-114">From the main page of your site, click the **Site Actions** menu and click **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="3e78c-115">Dans **actions du site**, cliquez sur gérer les **fonctionnalités du site**.</span><span class="sxs-lookup"><span data-stu-id="3e78c-115">In the **Site Actions**, click **Manage Site Features**.</span></span>  
  
3.  <span data-ttu-id="3e78c-116">Recherchez **Synchronisation de fichiers de serveur de rapports** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3e78c-116">Find **Report Server File Sync** in the list.</span></span>  
  
4.  <span data-ttu-id="3e78c-117">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="3e78c-117">Click **Activate**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e78c-118">Pour désactiver la fonctionnalité Synchronisation de fichiers de serveur de rapports, appliquez la même procédure, mais cliquez sur **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="3e78c-118">To deactivate the Report Server file sync feature, you can use the same procedure but click **Deactivate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e78c-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e78c-119">See Also</span></span>  
 <span data-ttu-id="3e78c-120">[Résoudre les problèmes liés aux parties de rapports &#40;Générateur de rapports et SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3e78c-120">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="3e78c-121">[Activer le serveur de rapports et les fonctionnalités d’intégration de Power View dans SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="3e78c-121">[Activate the Report Server and Power View Integration Features in SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span></span>  
 <span data-ttu-id="3e78c-122">[Installer ou désinstaller le complément Reporting Services pour SharePoint &#40;SharePoint 2010 et SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="3e78c-122">[Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="3e78c-123">Installer ou désinstaller le complément Reporting Services pour SharePoint &#40;SharePoint 2010 et SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="3e78c-123">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
