---
title: Créer une base de données Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 8373bb35-f0f9-4c3c-a53c-dfaa2ce567ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ee90ac5d02489da3b411b12389e949ff3136287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602168"
---
# <a name="create-a-master-data-services-database"></a><span data-ttu-id="f54e4-102">Créer une base de données Master Data Services</span><span class="sxs-lookup"><span data-stu-id="f54e4-102">Create a Master Data Services Database</span></span>
  <span data-ttu-id="f54e4-103">Créez une base de données [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] lorsque vous avez besoin d’une nouvelle base de données pour prendre en charge l’application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] et le service web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f54e4-103">Create a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database when you need a new database to support the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application and [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f54e4-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="f54e4-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="f54e4-105">Pour plus d’informations sur la configuration requise pour l’ordinateur qui héberge la base de données, consultez [Configuration requise pour la base de données &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f54e4-105">For information about the requirements for the computer that hosts the database, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
### <a name="to-create-a-master-data-services-database"></a><span data-ttu-id="f54e4-106">Pour créer une base de données Master Data Services</span><span class="sxs-lookup"><span data-stu-id="f54e4-106">To create a Master Data Services database</span></span>  
  
1.  <span data-ttu-id="f54e4-107">Ouvrez [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f54e4-107">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="f54e4-108">Dans le volet gauche, cliquez sur **Configuration de la base de données**.</span><span class="sxs-lookup"><span data-stu-id="f54e4-108">In the left pane, click **Database Configuration**.</span></span>  
  
3.  <span data-ttu-id="f54e4-109">Dans la page **Configuration de la base de données** , cliquez sur **Créer une base de données**.</span><span class="sxs-lookup"><span data-stu-id="f54e4-109">On the **Database Configuration** page, click **Create Database**.</span></span>  
  
4.  <span data-ttu-id="f54e4-110">Exécutez l’Assistant **Création d’une base de données** pour créer et configurer la base de données.</span><span class="sxs-lookup"><span data-stu-id="f54e4-110">Complete the **Create Database** wizard to create and configure the database.</span></span> <span data-ttu-id="f54e4-111">Pour plus d’informations sur les options d’interface utilisateur de l’Assistant, consultez [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../create-database-wizard-master-data-services-configuration-manager.md) (Assistant Création d’une base de données (Gestionnaire de configuration de Master Data Services)).</span><span class="sxs-lookup"><span data-stu-id="f54e4-111">For information about the user interface (UI) options in the wizard, see [Create Database Wizard &#40;Master Data Services Configuration Manager&#41;](../create-database-wizard-master-data-services-configuration-manager.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f54e4-112">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="f54e4-112">Next Steps</span></span>  
  
-   <span data-ttu-id="f54e4-113">Configurez les paramètres système pour la base de données et l'application Web.</span><span class="sxs-lookup"><span data-stu-id="f54e4-113">Configure system settings for the database and web application.</span></span> <span data-ttu-id="f54e4-114">Pour plus d’informations, consultez [Paramètres système &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f54e4-114">For more information, see [System Settings &#40;Master Data Services&#41;](../system-settings-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f54e4-115">Créez une application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] à associer à cette base de données.</span><span class="sxs-lookup"><span data-stu-id="f54e4-115">Create a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to associate with this database.</span></span> <span data-ttu-id="f54e4-116">Pour plus d’informations, consultez [Créer une application web Master Data Manager &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f54e4-116">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="f54e4-117">Configurez un plan de maintenance pour sauvegarder la base de données et les journaux des transactions.</span><span class="sxs-lookup"><span data-stu-id="f54e4-117">Configure a maintenance plan to back up the database and transaction logs.</span></span> <span data-ttu-id="f54e4-118">Pour plus d’informations, consultez [Configuration requise pour la base de données &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f54e4-118">For more information, see [Database Requirements &#40;Master Data Services&#41;](database-requirements-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f54e4-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f54e4-119">See Also</span></span>  
 [<span data-ttu-id="f54e4-120">Installer Master Data Services</span><span class="sxs-lookup"><span data-stu-id="f54e4-120">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
