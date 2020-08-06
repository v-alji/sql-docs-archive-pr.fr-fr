---
title: Configurer et administrer un serveur de rapports (SSRS en mode natif) | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, components
- deploying [Reporting Services], component options
- report servers [Reporting Services], component options
- configuration options [Reporting Services]
- administering Reporting Services
- components [Reporting Services], configuring
- configuring servers [Reporting Services]
ms.assetid: cfec012b-56f1-4346-9814-247acf22351c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5164fd2f9170cb092a45394f64f06d7622253f2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611552"
---
# <a name="configure-and-administer-a-report-server-ssrs-native-mode"></a><span data-ttu-id="ee92f-102">Configurer et administrer un serveur de rapports (SSRS en mode natif)</span><span class="sxs-lookup"><span data-stu-id="ee92f-102">Configure and Administer a Report Server (SSRS Native Mode)</span></span>
  <span data-ttu-id="ee92f-103">Cette rubrique récapitule les approches que vous pouvez utiliser pour configurer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee92f-103">This topic summarizes the approaches that you can use to configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="ee92f-104">Elle inclut également une liste de rubriques qui expliquent comment configurer des composants, des fonctions ou des fonctionnalités de serveur spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ee92f-104">It also includes a list of topics that explain how to configure specific components, features, or server capabilities.</span></span> <span data-ttu-id="ee92f-105">Pour configurer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="ee92f-105">To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can:</span></span>  
  
-   <span data-ttu-id="ee92f-106">utiliser le Gestionnaire de configuration de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ee92f-106">Use the Reporting Services Configuration Manager.</span></span> <span data-ttu-id="ee92f-107">Un grand nombre de rubriques de cette section contiennent des informations décrivant comment configurer des fonctions spécifiques par le biais de cet outil ;</span><span class="sxs-lookup"><span data-stu-id="ee92f-107">Many of the topics in this section contain information about how to configure specific features through this tool.</span></span>  
  
-   <span data-ttu-id="ee92f-108">utiliser [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] pour personnaliser les propriétés du serveur, activer Mes rapports, d’activer les journaux des traces et définir des valeurs par défaut à l’échelle du site.</span><span class="sxs-lookup"><span data-stu-id="ee92f-108">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to customize server properties, enable My Reports, enable trace logs, and set site-wide defaults.</span></span> <span data-ttu-id="ee92f-109">Pour plus d’informations sur les paramètres de site, consultez [Serveur de rapports Reporting Services &#40;mode natif&#41;](reporting-services-report-server-native-mode.md) pour Management Studio.</span><span class="sxs-lookup"><span data-stu-id="ee92f-109">For more information about site settings, see [Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) for Management Studio.</span></span> <span data-ttu-id="ee92f-110">Notez que vous pouvez créer et exécuter un script qui définit des propriétés de serveur par programmation.</span><span class="sxs-lookup"><span data-stu-id="ee92f-110">Note that you can create and run script that sets server properties programmatically.</span></span> <span data-ttu-id="ee92f-111">Pour plus d’informations, consultez [Écrire des scripts pour les tâches d’administration et de déploiement](../tools/script-deployment-and-administrative-tasks.md) et [Propriétés système de Report Server](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ee92f-111">For more information, see [Script Deployment and Administrative Tasks](../tools/script-deployment-and-administrative-tasks.md) and [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span></span>  
  
-   <span data-ttu-id="ee92f-112">utiliser le Gestionnaire de rapports pour accorder des autorisations d'accès au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ee92f-112">Use Report Manager to grant permissions to access the report server.</span></span> <span data-ttu-id="ee92f-113">Les autorisations sont fournies via des attributions de rôles que vous définissez pour chaque compte d'utilisateur ou de groupe.</span><span class="sxs-lookup"><span data-stu-id="ee92f-113">Permissions are conveyed through role assignments that you define for each user or group account.</span></span> <span data-ttu-id="ee92f-114">Pour plus d’informations, consultez [Rôles et autorisations &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ee92f-114">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="ee92f-115">modifier éventuellement les fichiers de configuration afin de changer les paramètres d'application.</span><span class="sxs-lookup"><span data-stu-id="ee92f-115">Optionally, modify configuration files to change application settings.</span></span> <span data-ttu-id="ee92f-116">Pour plus d’informations sur chaque fichier ainsi que des instructions pour les modifier, consultez [Reporting Services Configuration Files](reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="ee92f-116">For more information about each file and guidelines for modifying them, see [Reporting Services Configuration Files](reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee92f-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ee92f-117">In This Section</span></span>  
 [<span data-ttu-id="ee92f-118">Configurer des URL de serveurs de rapports &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee92f-118">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
 <span data-ttu-id="ee92f-119">Décrit comment définir les URL d'accès au serveur de rapports et au Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="ee92f-119">Describes how to define the URLs used to access the report server and Report Manager.</span></span>  
  
 [<span data-ttu-id="ee92f-120">Configurer le compte de service Report Server &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee92f-120">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="ee92f-121">Fournit des recommandations et des procédures pour la modification du compte de service et du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ee92f-121">Provides recommendations and steps on how to modify service account and password.</span></span>  
  
 [<span data-ttu-id="ee92f-122">Créer une base de données du serveur de rapports &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee92f-122">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
 <span data-ttu-id="ee92f-123">Décrit le mode de création d'une base de données du serveur de rapports, tel qu'il est exigé pour le stockage des objets et des métadonnées de serveur.</span><span class="sxs-lookup"><span data-stu-id="ee92f-123">Describes how to create a report server database, required for storing server metadata and objects.</span></span>  
  
 [<span data-ttu-id="ee92f-124">Configurer une connexion à la base de données du serveur de rapports &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee92f-124">Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md)  
 <span data-ttu-id="ee92f-125">Décrit le mode de modification de la chaîne de connexion utilisée par le serveur de rapports pour se connecter à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ee92f-125">Describes how to modify the connection string used by the report server to connect to the report server database.</span></span>  
  
 [<span data-ttu-id="ee92f-126">Configurer un serveur de rapports pour la remise par messagerie &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="ee92f-126">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="ee92f-127">Décrit comment configurer un serveur de rapports pour la prise en charge de la distribution des rapports par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="ee92f-127">Describes how to configure a report server to support e-mail report distribution.</span></span>  
  
 [<span data-ttu-id="ee92f-128">Configurer le compte d’exécution sans assistance &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ee92f-128">Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="ee92f-129">Décrit comment configurer un compte d'utilisateur de manière à traiter les rapports en mode sans assistance.</span><span class="sxs-lookup"><span data-stu-id="ee92f-129">Describes how to configure a user account to process reports in unattended mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee92f-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee92f-130">See Also</span></span>  
 <span data-ttu-id="ee92f-131">[Configurer l’accès Générateur de rapports](configure-report-builder-access.md) </span><span class="sxs-lookup"><span data-stu-id="ee92f-131">[Configure Report Builder Access](configure-report-builder-access.md) </span></span>  
 <span data-ttu-id="ee92f-132">[Fichiers de configuration de Reporting Services](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="ee92f-132">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="ee92f-133">[Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="ee92f-133">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="ee92f-134">[Sécurité et protection Reporting Services](../security/reporting-services-security-and-protection.md) </span><span class="sxs-lookup"><span data-stu-id="ee92f-134">[Reporting Services Security and Protection](../security/reporting-services-security-and-protection.md) </span></span>  
 [<span data-ttu-id="ee92f-135">Serveur de rapports Reporting Services &#40;mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="ee92f-135">Reporting Services Report Server &#40;Native Mode&#41;</span></span>](reporting-services-report-server-native-mode.md)  
  
  
