---
title: Activer le serveur de rapports et les fonctionnalités d’intégration de Power View dans SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7f64a54-c555-4d31-bf99-3abe57dc8626
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af5f544e959c039b0bdb85d63d0b94917254d78a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613338"
---
# <a name="activate-the-report-server-and-power-view-integration-features-in-sharepoint"></a><span data-ttu-id="d5ffb-102">Activer les fonctionnalités d'intégration Report Server et Power View dans SharePoint</span><span class="sxs-lookup"><span data-stu-id="d5ffb-102">Activate the Report Server and Power View Integration Features in SharePoint</span></span>
  <span data-ttu-id="d5ffb-103">Les [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] fonctionnalités de la collection de sites sont généralement activées par défaut après l’installation du [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] complément pour les produits SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features are usually activated by default after you install the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span> <span data-ttu-id="d5ffb-104">Dans certaines circonstances, vous devrez activer les fonctionnalités manuellement.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-104">In some situations you will need to manually activate the features.</span></span>  
  
 <span data-ttu-id="d5ffb-105">Si vous installez le complément [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] pour les produits SharePoint 2010 après l'installation du produit SharePoint, la fonctionnalité d'intégration du serveur de rapports et la fonctionnalité d'intégration de vue de remplissage sont uniquement activées pour les collections de sites racine.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-105">If you install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint 2010 Products after the installation of the SharePoint product, then the Report Server integration feature and the Power View integration feature will only be activated for root site collections.</span></span> <span data-ttu-id="d5ffb-106">Pour les autres collections de sites, vous devez activer manuellement les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-106">For other site collections, you will need to manually activate the features.</span></span> <span data-ttu-id="d5ffb-107">Par exemple, si vous avez une collection de sites **http://[nom de mon serveur]/sites/[nom de collection de sites]** vous devez activer manuellement les fonctionnalités de collection de sites [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5ffb-107">For example if you have a site collection of **http://[my server name]/sites/[site collection name]** you will need to manually activate the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features.</span></span>  
  
 <span data-ttu-id="d5ffb-108">S’il n’y a pas de collection de sites racine, le complément [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] enregistre un message semblable au suivant.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-108">When there is no root site collection, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in will log a message similar to the following.</span></span>  
  
 <span data-ttu-id="d5ffb-109">« L'application Web SharePoint 80 n'a pas de collection de sites racine »</span><span class="sxs-lookup"><span data-stu-id="d5ffb-109">"SharePoint web app 80 does not have root site collection"</span></span>  
  
 <span data-ttu-id="d5ffb-110">Le message se trouve dans le journal d’installation du complément, nommé « RS_SP_ #. log », où # est un nombre incrémenté.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-110">The message will be found in the add-in installation log, named "RS_SP_#.log" where # is an incrementing number.</span></span> <span data-ttu-id="d5ffb-111">Le fichier journal se trouve dans le dossier Temp de l’utilisateur actuel, par exemple C:\Users \\ [nom d’utilisateur] \AppData\Local\Temp. Pour plus d’informations sur les options de journalisation avec le complément, consultez [installer ou désinstaller le complément Reporting Services pour sharepoint &#40;sharepoint 2010 et sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="d5ffb-111">The log file will be found in the current users Temp folder, for example C:\Users\\[user name]\AppData\Local\Temp. For more information on logging options with the add-in, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span>  
  
 <span data-ttu-id="d5ffb-112">Dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="d5ffb-112">In this topic:</span></span>  
  
-   [<span data-ttu-id="d5ffb-113">Pour activer les fonctionnalités d'intégration de collections de sites Report Server et Power View :</span><span class="sxs-lookup"><span data-stu-id="d5ffb-113">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>](#bkmk_features)  
  
-   [<span data-ttu-id="d5ffb-114">Pour activer ou désactiver la fonctionnalité de collection de sites dans l'Administration centrale de Reporting Services :</span><span class="sxs-lookup"><span data-stu-id="d5ffb-114">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>](#bkmk_centraladmin)  
  
##  <a name="to-activate-the-report-server-and-power-view-integration-site-collection-features"></a><a name="bkmk_features"></a><span data-ttu-id="d5ffb-115">Pour activer les fonctionnalités du serveur de rapports et de la collection de sites d’intégration Power View :</span><span class="sxs-lookup"><span data-stu-id="d5ffb-115">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>  
  
1.  <span data-ttu-id="d5ffb-116">Ouvrez votre navigateur sur le site où vous souhaitez activer les fonctionnalités de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5ffb-116">Open your browser to the site where you want the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features active.</span></span>  
  
2.  <span data-ttu-id="d5ffb-117">Cliquez sur **Actions du site**.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-117">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="d5ffb-118">Cliquez sur **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-118">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="d5ffb-119">Cliquez sur **Fonctionnalités de la collection de sites** dans le groupe Administration de la collection de sites.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-119">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="d5ffb-120">Recherchez **Fonctionnalité d'intégration Report Server** ou **Fonctionnalité d'intégration de Power View** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-120">Find **Report Server Integration Feature** or **Power View Integration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="d5ffb-121">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-121">Click **Activate**.</span></span>  
  
 <span data-ttu-id="d5ffb-122">Pour désactiver les fonctionnalités, vous pouvez utiliser la même procédure en cliquant sur **Désactiver** au lieu d' **Activer**.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-122">To deactivate the features, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
##  <a name="to-activate-or-deactivate-reporting-services-central-administration-site-collection-feature"></a><a name="bkmk_centraladmin"></a><span data-ttu-id="d5ffb-123">Pour activer ou désactiver Reporting Services fonctionnalité de collection de sites d’administration centrale :</span><span class="sxs-lookup"><span data-stu-id="d5ffb-123">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>  
  
1.  <span data-ttu-id="d5ffb-124">Ouvrez votre navigateur dans l'Administration centrale de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-124">Open your browser to SharePoint Central Administration.</span></span>  
  
2.  <span data-ttu-id="d5ffb-125">Cliquez sur **Actions du site**.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-125">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="d5ffb-126">Cliquez sur **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-126">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="d5ffb-127">Cliquez sur **Fonctionnalités de la collection de sites** dans le groupe Administration de la collection de sites.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-127">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="d5ffb-128">Recherchez **Fonctionnalité d'administration centrale du serveur de rapports** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-128">Find **Report Server Central Administration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="d5ffb-129">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-129">Click **Activate**.</span></span>  
  
 <span data-ttu-id="d5ffb-130">Pour désactiver la fonctionnalité, vous pouvez utiliser la même procédure en cliquant sur **Désactiver** au lieu d' **Activer**.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-130">To deactivate the feature, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d5ffb-131">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="d5ffb-131">Next Steps</span></span>  
 <span data-ttu-id="d5ffb-132">Une fois la fonctionnalité activée, vous pouvez continuer l'intégration de serveur.</span><span class="sxs-lookup"><span data-stu-id="d5ffb-132">After the feature is activated, you can continue with server integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ffb-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5ffb-133">See Also</span></span>  
 [<span data-ttu-id="d5ffb-134">Installer ou désinstaller le complément Reporting Services pour SharePoint &#40;SharePoint 2010 et SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="d5ffb-134">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
