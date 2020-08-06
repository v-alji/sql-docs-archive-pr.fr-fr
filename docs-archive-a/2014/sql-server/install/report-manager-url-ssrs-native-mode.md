---
title: URL de Gestionnaire de rapports (SSRS en mode natif) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.rsconfigtool.reportmanagervirtualdirectory.f1
ms.assetid: 45768952-23a6-45a5-b541-e7bf192b4a78
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ec43c91bb2d24bb96cc6541d93311ce6dd234ed4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611513"
---
# <a name="report-manager-url-ssrs-native-mode"></a><span data-ttu-id="59bde-102">URL du gestionnaire de rapports (SSRS en mode natif)</span><span class="sxs-lookup"><span data-stu-id="59bde-102">Report Manager URL (SSRS Native Mode)</span></span>
  <span data-ttu-id="59bde-103">Utilisez la page URL du Gestionnaire de rapports pour configurer ou modifier l'URL permettant d'accéder au Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="59bde-103">Use the Report Manager URL page to configure or modify the URL used to access Report Manager.</span></span> <span data-ttu-id="59bde-104">Par défaut, l'URL du Gestionnaire de rapports hérite du préfixe, de l'adresse IP et du port de l'URL du service Web Report Server URL.</span><span class="sxs-lookup"><span data-stu-id="59bde-104">By default, the Report Manager URL inherits the prefix, IP address, and port of the Report Server Web service URL.</span></span> <span data-ttu-id="59bde-105">La raison en est que le Gestionnaire de rapports fournit l'accès frontal au service Web qui s'exécute au sein du même service Report Server.</span><span class="sxs-lookup"><span data-stu-id="59bde-105">This is because Report Manager provides front-end access to the Web service that runs within the same Report Server service.</span></span> <span data-ttu-id="59bde-106">Si vous isolez les applications de service et utilisez le Gestionnaire de rapports pour accéder à un service Web Report Server sur un autre ordinateur, vous devez modifier le fichier RSReportServer.config pour pointer le Gestionnaire de rapports sur une instance différente.</span><span class="sxs-lookup"><span data-stu-id="59bde-106">If you are isolating the service applications and using Report Manager to access a Report Server Web service on a different computer, you must edit RSReportServer.config file to point Report Manager to a different instance.</span></span> <span data-ttu-id="59bde-107">Pour plus d’informations sur la configuration d’une connexion Gestionnaire de rapports à un serveur de rapports distant, consultez [Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="59bde-107">For more information about configuring a Report Manager connection to a remote report server, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
 [!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="59bde-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode natif.</span><span class="sxs-lookup"><span data-stu-id="59bde-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
 <span data-ttu-id="59bde-109">Si vous êtes en train de configurer le serveur de rapports pour qu'il s'exécute en mode intégré SharePoint, ne créez pas l'URL du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="59bde-109">If you are configuring the report server to run in SharePoint integrated mode, do not create a Report Manager URL.</span></span> <span data-ttu-id="59bde-110">Le Gestionnaire de rapports n'est pas pris en charge sur un serveur de rapports exécuté en mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="59bde-110">Report Manager is not supported on a report server that runs in SharePoint integrated mode.</span></span> <span data-ttu-id="59bde-111">Si une URL existe déjà pour le Gestionnaire de rapports, elle devient indisponible après que vous avez configuré le serveur de rapports pour qu'il s'exécute en mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="59bde-111">If a URL already exists for Report Manager, it will become unavailable after you configure the report server to run in SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="59bde-112">Pour ouvrir cette page, démarrez le Gestionnaire de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et cliquez sur **URL du Gestionnaire de rapports** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="59bde-112">To open this page, start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager and click **Report Manager URL** in the navigation pane.</span></span> <span data-ttu-id="59bde-113">Pour plus d’informations sur le démarrage du Configuration Manager, consultez [Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="59bde-113">For more information about how to start the Configuration Manager, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59bde-114">Si le Gestionnaire de rapports n'est pas activé, vous ne pouvez pas définir d'options sur cette page.</span><span class="sxs-lookup"><span data-stu-id="59bde-114">If Report Manager is not enabled, you cannot set options on this page.</span></span> <span data-ttu-id="59bde-115">Pour plus d’informations sur l’activation de la Gestionnaire de rapports, consultez [Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="59bde-115">For more information about enabling Report Manager, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="59bde-116">Options</span><span class="sxs-lookup"><span data-stu-id="59bde-116">Options</span></span>  
 <span data-ttu-id="59bde-117">**Répertoire virtuel**</span><span class="sxs-lookup"><span data-stu-id="59bde-117">**Virtual Directory**</span></span>  
 <span data-ttu-id="59bde-118">Spécifie le nom de répertoire virtuel pour le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="59bde-118">Specifies the virtual directory name for Report Manager.</span></span> <span data-ttu-id="59bde-119">Vous ne pouvez avoir qu'un seul nom de répertoire virtuel pour chaque instance du Gestionnaire de rapports sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="59bde-119">You can only have one virtual directory name for each Report Manager instance on the same computer.</span></span>  
  
 <span data-ttu-id="59bde-120">**URLs**</span><span class="sxs-lookup"><span data-stu-id="59bde-120">**URLs**</span></span>  
 <span data-ttu-id="59bde-121">Affiche l'URL définie pour l'instance en cours du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="59bde-121">Displays the URL defined for the current Report Manager instance.</span></span>  
  
 <span data-ttu-id="59bde-122">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="59bde-122">**Advanced**</span></span>  
 <span data-ttu-id="59bde-123">Ajoutez une URL supplémentaire pour l'instance en cours du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="59bde-123">Add an additional URL for the current Report Manager instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59bde-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="59bde-124">See Also</span></span>  
 <span data-ttu-id="59bde-125">[Configurer une URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="59bde-125">[Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="59bde-126">[URL dans les fichiers de configuration &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="59bde-126">[URLs in Configuration Files  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="59bde-127">Configurer des URL de serveurs de rapports &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="59bde-127">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
  
  
