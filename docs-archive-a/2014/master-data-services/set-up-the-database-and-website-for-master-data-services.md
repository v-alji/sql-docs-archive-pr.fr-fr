---
title: Configurer la base de données et le site Web pour Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
f1_keywords:
- sql12.mds.configmanager.general.f1
ms.assetid: d50863e7-50d9-4ab8-aabb-fd68e2d132a1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da797bc6f9838a2baab6cc440cc7d778a7a6e186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614704"
---
# <a name="set-up-the-database-and-website-for-master-data-services"></a><span data-ttu-id="32c1b-102">Configurer la base de données et le site web de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="32c1b-102">Set up the Database and Website for Master Data Services</span></span>
  <span data-ttu-id="32c1b-103">Utilisez le [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] pour configurer la base de données et le site web pour [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span><span class="sxs-lookup"><span data-stu-id="32c1b-103">Use the [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to set up the database and website for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (MDS)</span></span>  
  
 <span data-ttu-id="32c1b-104">Pour configurer la base de données et le site web, effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="32c1b-104">To set up the database and website, complete the following tasks.</span></span>  
  
1.  <span data-ttu-id="32c1b-105">Créez une base de données à l’aide de la page **configuration de la base de données** dans [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32c1b-105">Create a database using the **Database Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="32c1b-106">Pour plus d’informations, consultez [page Configuration de la base de données &#40;Gestionnaire de configuration Master Data Services&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) et [Assistant Création de base de données &#40;gestionnaire de configuration Master Data Services&#41;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="32c1b-106">For information, see [Database Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/database-configuration-page-master-data-services-configuration-manager.md) and [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
2.  <span data-ttu-id="32c1b-107">Créez un site Web, sélectionnez le site Web par défaut ou sélectionnez un autre site Web existant, à l’aide de la page **configuration Web** dans [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32c1b-107">Create a new website, select the default website, or select another existing website, using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="32c1b-108">Associez ensuite la base de données MDS à l'application web sélectionnée ou créée.</span><span class="sxs-lookup"><span data-stu-id="32c1b-108">Then associate the MDS database with the web application you select or create.</span></span>  
  
     <span data-ttu-id="32c1b-109">Pour plus d’informations, consultez [page Configuration Web &#40;Gestionnaire de configuration Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) et [boîte de dialogue créer un site web &#40;gestionnaire de configuration Master Data Services&#41;](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="32c1b-109">For information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
3.  <span data-ttu-id="32c1b-110">Facultatif Activez l’intégration avec Data Quality Services à l’aide de la page de **configuration Web** dans [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32c1b-110">(Optional) Enable integration with Data Quality Services using the **Web Configuration** page in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span>  
  
     <span data-ttu-id="32c1b-111">Pour plus d’informations, consultez [page de configuration Web &#40;Gestionnaire de configuration Master Data Services&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) et [activer l’intégration de Data Quality Services avec Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="32c1b-111">For more information, see [Web Configuration Page &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/web-configuration-page-master-data-services-configuration-manager.md) and [Enable Data Quality Services Integration with Master Data Services](install-windows/enable-data-quality-services-integration-with-master-data-services.md).</span></span>  
  
 <span data-ttu-id="32c1b-112">Vous pouvez utiliser [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] pour spécifier des paramètres pour les applications et services web associés à la base de données MDS.</span><span class="sxs-lookup"><span data-stu-id="32c1b-112">You can also use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to specify settings for the web applications and services associated with the MDS database.</span></span> <span data-ttu-id="32c1b-113">Par exemple, vous pouvez spécifier la fréquence à laquelle les données sont chargées ou des e-mails de validation envoyés.</span><span class="sxs-lookup"><span data-stu-id="32c1b-113">For example, you can specify how frequently data is loaded or how often validation emails are sent.</span></span> <span data-ttu-id="32c1b-114">Pour plus d’informations, consultez [Paramètres système &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="32c1b-114">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c1b-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32c1b-115">See Also</span></span>  
 <span data-ttu-id="32c1b-116">[Base de données Master Data Services](../../2014/master-data-services/master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="32c1b-116">[Master Data Services Database](../../2014/master-data-services/master-data-services-database.md) </span></span>  
 [<span data-ttu-id="32c1b-117">Application Web Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="32c1b-117">Master Data Manager Web Application</span></span>](../../2014/master-data-services/master-data-manager-web-application.md)  
  
  
