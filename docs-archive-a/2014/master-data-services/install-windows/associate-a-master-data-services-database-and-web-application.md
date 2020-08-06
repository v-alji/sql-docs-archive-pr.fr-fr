---
title: Associer une base de données Master Data Services et une application web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ccb25672-f71d-4135-b548-f50eb45d8fa5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 01afde6aea5065a51cb9e7ae5dc4151e9f1e9fc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696911"
---
# <a name="associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="fe34c-102">Associer une base de données Master Data Services et une application Web</span><span class="sxs-lookup"><span data-stu-id="fe34c-102">Associate a Master Data Services Database and Web Application</span></span>
  <span data-ttu-id="fe34c-103">Associez votre application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] à une base de données [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] pour spécifier la base de données à utiliser pour les opérations web.</span><span class="sxs-lookup"><span data-stu-id="fe34c-103">Associate your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database to specify the database to use for web operations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fe34c-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="fe34c-104">Prerequisites</span></span>  
  
-   [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] <span data-ttu-id="fe34c-105">doit être installé sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="fe34c-105">must be installed on the local computer.</span></span> <span data-ttu-id="fe34c-106">Pour plus d’informations, consultez [Installer Master Data Services](install-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fe34c-106">For more information, see [Install Master Data Services](install-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="fe34c-107">Une application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] locale doit exister.</span><span class="sxs-lookup"><span data-stu-id="fe34c-107">A local [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application must exist.</span></span> <span data-ttu-id="fe34c-108">Pour plus d’informations, consultez [Créer une application web Master Data Manager &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fe34c-108">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="fe34c-109">Une base de données [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] locale ou distante doit exister.</span><span class="sxs-lookup"><span data-stu-id="fe34c-109">Either a local or remote [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database must exist.</span></span> <span data-ttu-id="fe34c-110">Pour plus d’informations, consultez [Créer une base de données Master Data Services](create-a-master-data-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="fe34c-110">For more information, see [Create a Master Data Services Database](create-a-master-data-services-database.md).</span></span>  
  
### <a name="to-associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="fe34c-111">Pour associer une base de données Master Data Services et une application Web</span><span class="sxs-lookup"><span data-stu-id="fe34c-111">To associate a Master Data Services database and web application</span></span>  
  
1.  <span data-ttu-id="fe34c-112">Ouvrez [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe34c-112">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="fe34c-113">Dans le volet gauche, cliquez sur **Configuration Web**.</span><span class="sxs-lookup"><span data-stu-id="fe34c-113">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="fe34c-114">Dans la page **Configuration Web** , sous **Application Web**, dans la liste **Site Web** , sélectionnez le site web qui contient votre application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe34c-114">On the **Web Configuration** page, under **Web application**, from the **Website** list, select the website that contains your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="fe34c-115">Dans la zone **Application web** , sélectionnez l’application web qui héberge [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe34c-115">In the **Web application** box, select the web application that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
5.  <span data-ttu-id="fe34c-116">Sous **Associer l’application à une base de données**, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="fe34c-116">Under **Associate Application with Database**, click **Select**.</span></span> <span data-ttu-id="fe34c-117">La boîte de dialogue **Connexion à une base de données** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="fe34c-117">The **Connect to Database** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="fe34c-118">Spécifiez les informations de connexion pour l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui héberge la base de données [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] et cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="fe34c-118">Specify connection information for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database, and click **Connect**.</span></span>  
  
7.  <span data-ttu-id="fe34c-119">Dans la liste **Base de données Master Data Services** , sélectionnez la base de données que vous souhaitez associer à l’application web et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe34c-119">From the **Master Data Services database** list, select the database you want to associate the web application with and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="fe34c-120">Sous **Associer l’application à une base de données**, vérifiez que l’instance et les informations de la base de données sont correctes, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="fe34c-120">Under **Associate Application with Database**, verify that the instance and database information are correct, and then click **Apply**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fe34c-121">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="fe34c-121">Next Steps</span></span>  
  
-   <span data-ttu-id="fe34c-122">Lorsque l'application Web est créée, l'accès par programme au service Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] est automatiquement activé.</span><span class="sxs-lookup"><span data-stu-id="fe34c-122">Programmatic access to [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web services is automatically enabled when the web application is created.</span></span> <span data-ttu-id="fe34c-123">Pour permettre aux développeurs d'accéder aux métadonnées de service afin de créer facilement des classes proxy pour l'accès par programme, activez la publication de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="fe34c-123">To let developers access the service metadata to easily generate proxy classes for programmatic access, enable metadata publishing.</span></span> <span data-ttu-id="fe34c-124">Pour plus d’informations, consultez [Créer des classes proxy de service Web Master Data Manager](../develop/create-master-data-manager-web-service-proxy-classes.md).</span><span class="sxs-lookup"><span data-stu-id="fe34c-124">For more information, see [Create Master Data Manager Web Service Proxy Classes](../develop/create-master-data-manager-web-service-proxy-classes.md).</span></span>  
  
-   <span data-ttu-id="fe34c-125">Ajoutez des utilisateurs et des groupes à [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fe34c-125">Add users and groups to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="fe34c-126">Si aucun utilisateur ou groupe n’a accès à [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], vous devez ouvrir [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] à l’aide des informations d’identification de l’administrateur système [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fe34c-126">If no users or groups have been granted access to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must open [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] using the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] system administrator credentials.</span></span> <span data-ttu-id="fe34c-127">Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../administrators-master-data-services.md) et [Utilisateurs et groupes &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fe34c-127">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md) and [Users and Groups &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe34c-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe34c-128">See Also</span></span>  
 <span data-ttu-id="fe34c-129">[Installer Master Data Services](install-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fe34c-129">[Install Master Data Services](install-master-data-services.md) </span></span>  
 [<span data-ttu-id="fe34c-130">Page Configuration web &#40;Gestionnaire de configuration de Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fe34c-130">Web Configuration Page &#40;Master Data Services Configuration Manager&#41;</span></span>](../web-configuration-page-master-data-services-configuration-manager.md)  
  
  
