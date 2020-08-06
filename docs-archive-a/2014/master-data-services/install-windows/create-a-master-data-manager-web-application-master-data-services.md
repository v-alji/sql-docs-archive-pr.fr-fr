---
title: Créer une application web Master Data Manager (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 241d46d7-8008-47f6-bebd-0dfff1cc856a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fd81188b499850397aa8ffd2e40cfcb91c648288
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602169"
---
# <a name="create-a-master-data-manager-web-application-master-data-services"></a><span data-ttu-id="002cf-102">Créer une application Web Master Data Manager (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="002cf-102">Create a Master Data Manager Web Application (Master Data Services)</span></span>
  <span data-ttu-id="002cf-103">L’application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] offre une interface permettant aux utilisateurs de travailler avec des données de référence et aux administrateurs de configurer et de gérer MDS.</span><span class="sxs-lookup"><span data-stu-id="002cf-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application provides an interface for users to work with master data and for administrators to configure and administer MDS.</span></span>  
  
 <span data-ttu-id="002cf-104">Une application Web doit toujours être contenue par un site Web.</span><span class="sxs-lookup"><span data-stu-id="002cf-104">A web application must always be contained by a website.</span></span> <span data-ttu-id="002cf-105">Pour créer une application Web, vous devez au choix :</span><span class="sxs-lookup"><span data-stu-id="002cf-105">To create a web application, you must either:</span></span>  
  
-   <span data-ttu-id="002cf-106">Utiliser le site Web par défaut puis créer l'application Web,</span><span class="sxs-lookup"><span data-stu-id="002cf-106">Use the Default website and then create the web application,</span></span>  
  
-   <span data-ttu-id="002cf-107">Utiliser un site Web existant puis créer l'application Web, ou</span><span class="sxs-lookup"><span data-stu-id="002cf-107">Use an existing website and then create the web application, or</span></span>  
  
-   <span data-ttu-id="002cf-108">Créer un site web, qui crée automatiquement une application Web.</span><span class="sxs-lookup"><span data-stu-id="002cf-108">Create a new website, which automatically creates a web application.</span></span>  
  
 <span data-ttu-id="002cf-109">Après avoir créé l'application Web, vous l'associez à la base de données [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="002cf-109">After you create the web application, you associate it with the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="002cf-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="002cf-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="002cf-111">Pour plus d’informations sur la configuration requise pour l’ordinateur qui héberge l’application web, consultez [Configuration requise pour l’application Web &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="002cf-111">For information about the requirements for the computer that hosts the web application, see [Web Application Requirements &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="002cf-112">Pour créer une application Web Master Data Manager dans un nouveau site Web</span><span class="sxs-lookup"><span data-stu-id="002cf-112">To create a Master Data Manager web application in a new website</span></span>  
 <span data-ttu-id="002cf-113">Quand vous créez un site web, l’application web racine est l’application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="002cf-113">When you create a new website, the root web application is the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="002cf-114">L'application Web est également ajoutée à un nouveau pool d'applications.</span><span class="sxs-lookup"><span data-stu-id="002cf-114">The web application is also added to a new application pool.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="002cf-115">Si vous appliquez cette procédure, vous ne pouvez pas spécifier de chemin virtuel ni d’alias de l’application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="002cf-115">If you follow this procedure, you cannot specify a virtual path and alias of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="002cf-116">Si vous souhaitez spécifier un chemin virtuel et un alias pour [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], vous devez créer une application web dans un site web existant qui n’est pas encore configuré comme application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="002cf-116">If you want to specify a virtual path and alias for [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must create a web application in an existing website that is not already configured as a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="002cf-117">En outre, [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] prend uniquement en charge la création de sites avec des liaisons HTTP.</span><span class="sxs-lookup"><span data-stu-id="002cf-117">Additionally, [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] supports creating sites with HTTP bindings only.</span></span> <span data-ttu-id="002cf-118">Pour ajouter une liaison HTTPS, créez un site et une application dans [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] , puis consultez [Sécuriser une application Web Master Data Manager](secure-a-master-data-manager-web-application.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="002cf-118">To add an HTTPS binding, create a new site and application in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] and then see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md) for more information.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="002cf-119">Pour créer une application Web Master Data Manager dans un nouveau site Web</span><span class="sxs-lookup"><span data-stu-id="002cf-119">To create a Master Data Manager web application in a new website</span></span>  
  
1.  <span data-ttu-id="002cf-120">Ouvrez [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="002cf-120">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="002cf-121">Dans le volet gauche, cliquez sur **Configuration Web**.</span><span class="sxs-lookup"><span data-stu-id="002cf-121">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="002cf-122">Dans la page **Configuration Web** , dans la liste des site web, sélectionnez **Créer un site Web**.</span><span class="sxs-lookup"><span data-stu-id="002cf-122">On the **Web Configuration** page, in the Website list, select **Create new website**.</span></span>  
  
4.  <span data-ttu-id="002cf-123">Dans la boîte de dialogue **Créer un site Web** , spécifiez les informations pour un nouveau site web.</span><span class="sxs-lookup"><span data-stu-id="002cf-123">On the **Create Website** dialog box, specify information for a new website.</span></span> <span data-ttu-id="002cf-124">Pour plus d’informations sur les options d’interface utilisateur dans la boîte de dialogue, consultez [Boîte de dialogue Créer un site Web &#40;Gestionnaire de configuration Master Data Services&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="002cf-124">For more information about the user interface (UI) options in the dialog box, see [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="002cf-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="002cf-125">Click **OK**.</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="002cf-126">Pour créer une application Web Master Data Manager dans un site Web existant</span><span class="sxs-lookup"><span data-stu-id="002cf-126">To create a Master Data Manager web application in an existing website</span></span>  
 <span data-ttu-id="002cf-127">Lorsque vous créez une application Web dans un site Web existant, vous pouvez choisir son chemin d'accès virtuel et son alias.</span><span class="sxs-lookup"><span data-stu-id="002cf-127">When you create a web application in an existing website, you can choose the virtual path and alias of the web application.</span></span> <span data-ttu-id="002cf-128">L'application Web est ajoutée à un nouveau pool d'applications.</span><span class="sxs-lookup"><span data-stu-id="002cf-128">The web application is added to a new application pool.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="002cf-129">Pour créer une application Web Master Data Manager dans un site Web existant</span><span class="sxs-lookup"><span data-stu-id="002cf-129">To create a Master Data Manager web application in an existing website</span></span>  
  
1.  <span data-ttu-id="002cf-130">Ouvrez [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="002cf-130">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="002cf-131">Dans le volet gauche, cliquez sur **Configuration Web**.</span><span class="sxs-lookup"><span data-stu-id="002cf-131">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="002cf-132">Dans la page **Configuration Web** , dans la liste **Site Web** , sélectionnez le site web dans lequel vous souhaitez créer l’application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="002cf-132">On the **Web Configuration** page, from the **Website** list, select the website in which you want to create the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="002cf-133">Cliquez sur **Créer une application**.</span><span class="sxs-lookup"><span data-stu-id="002cf-133">Click **Create Application**.</span></span>  
  
5.  <span data-ttu-id="002cf-134">Dans la boîte de dialogue **Créer une application Web** , spécifiez les informations pour une nouvelle application web.</span><span class="sxs-lookup"><span data-stu-id="002cf-134">On the **Create Web Application** dialog box, specify information for a new web application.</span></span> <span data-ttu-id="002cf-135">Pour plus d’informations sur les options d’interface utilisateur dans la boîte de dialogue, consultez [Boîte de dialogue Créer une application Web &#40;Gestionnaire de configuration Master Data Services&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="002cf-135">For more information about the user interface (UI) options in the dialog box, see [Create Web Application Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
6.  <span data-ttu-id="002cf-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="002cf-136">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="002cf-137">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="002cf-137">Next Steps</span></span>  
  
-   <span data-ttu-id="002cf-138">Associez l'application Web à une base de données [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="002cf-138">Associate the web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="002cf-139">Pour plus d’informations, consultez [Associer une base de données Master Data Services et une application Web](associate-a-master-data-services-database-and-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="002cf-139">For more information, see [Associate a Master Data Services Database and Web Application](associate-a-master-data-services-database-and-web-application.md).</span></span>  
  
-   <span data-ttu-id="002cf-140">Éventuellement, configurez le site web qui héberge l’application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] pour qu’il utilise une liaison HTTPS si vous souhaitez chiffrer le contenu à l’aide du protocole SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="002cf-140">Optionally, configure the website that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to use an HTTPS binding if you want to encrypt content by using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="002cf-141">Vous devez utiliser un outil IIS, tel que IIS Manager, pour configurer le certificat du serveur Web et configurer une liaison HTTPS et les paramètres SSL pour le site.</span><span class="sxs-lookup"><span data-stu-id="002cf-141">You must use an Internet Information Services (IIS) tool, such as IIS Manager, to configure the server certificate for the web server, and to configure an HTTPS binding and the SSL settings for the site.</span></span> <span data-ttu-id="002cf-142">Pour plus d’informations, consultez [Sécuriser une application Web Master Data Manager](secure-a-master-data-manager-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="002cf-142">For more information, see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002cf-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="002cf-143">See Also</span></span>  
 [<span data-ttu-id="002cf-144">Installer Master Data Services</span><span class="sxs-lookup"><span data-stu-id="002cf-144">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
