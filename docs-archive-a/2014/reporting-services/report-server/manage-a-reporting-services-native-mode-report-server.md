---
title: Gérer un serveur de rapports Reporting Services (SSRS) en mode natif | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- configuration options [Reporting Services]
- report servers [Reporting Services], configuring
ms.assetid: 6ca03a09-d6a8-4c93-ba12-1c99dcbfb618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d44a9329074a20c04f878c055674ea563b297f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611532"
---
# <a name="manage-a-reporting-services-native-mode-report-server"></a><span data-ttu-id="2cdd3-102">Gérer un serveur de rapports Reporting Services (SSRS) en mode natif</span><span class="sxs-lookup"><span data-stu-id="2cdd3-102">Manage a Reporting Services Native Mode Report Server</span></span>
  <span data-ttu-id="2cdd3-103">Cette section contient des procédures qui indiquent comment configurer une instance de serveur de rapports en mode natif à l'aide du Gestionnaire de configuration de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-103">This section contains procedures for configuring a native mode report server instance using the Reporting Services Configuration Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cdd3-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2cdd3-104">In This Section</span></span>  
 <span data-ttu-id="2cdd3-105">Les rubriques de cette section sont organisées en catégories afin que vous puissiez rechercher plus aisément les instructions que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-105">The topics in this section are organized into categories so that you can more easily find the instructions you want.</span></span> <span data-ttu-id="2cdd3-106">La première section contient les rubriques pour les tâches de configuration de base pour un serveur de rapports en mode natif.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-106">The first section contains topics for basic configuration tasks for a native mode report server.</span></span> <span data-ttu-id="2cdd3-107">La deuxième section contient les rubriques de configuration avancées.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-107">The second section contains advanced configuration topics.</span></span> <span data-ttu-id="2cdd3-108">La troisième section contient les rubriques pour configurer un serveur de rapports afin qu'il s'exécute en mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-108">The third section contains topics for configuring a report server to run in SharePoint integrated mode.</span></span>  
  
### <a name="basic-configuration"></a><span data-ttu-id="2cdd3-109">Configuration de base</span><span class="sxs-lookup"><span data-stu-id="2cdd3-109">Basic Configuration</span></span>  
 [<span data-ttu-id="2cdd3-110">Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="2cdd3-110">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
 <span data-ttu-id="2cdd3-111">Indique la procédure à suivre pour démarrer l'outil de configuration de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-111">Provides steps for starting the Reporting Services Configuration tool.</span></span>  
  
 [<span data-ttu-id="2cdd3-112">Configurer un compte de service &#40;Gestionnaire de configuration de SSR&#41;</span><span class="sxs-lookup"><span data-stu-id="2cdd3-112">Configure a Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="2cdd3-113">Explique comment spécifier des informations de compte et de mot de passe pour le service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-113">Explains how to specify account and password information for the Report Server service.</span></span>  
  
 [<span data-ttu-id="2cdd3-114">Inscrire un nom de principal du service &#40;SPN&#41; pour un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="2cdd3-114">Register a Service Principal Name &#40;SPN&#41; for a Report Server</span></span>](register-a-service-principal-name-spn-for-a-report-server.md)  
 <span data-ttu-id="2cdd3-115">Explique comment enregistrer manuellement un SPN pour un serveur de rapports qui s'exécute sous un compte d'utilisateur de domaine sur un réseau qui utilise l'authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-115">Explains how to manually register an SPN for a report server that runs under a domain user account on a network that uses Kerberos authentication.</span></span>  
  
 [<span data-ttu-id="2cdd3-116">Configurer une URL &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2cdd3-116">Configure a URL  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-url-ssrs-configuration-manager.md)  
 <span data-ttu-id="2cdd3-117">Explique comment établir une ou plusieurs URL utilisées pour accéder au service Web Report Server et au Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-117">Explains how to establish one or more URLs used to access the Report Server Web service and Report Manager.</span></span>  
  
 [<span data-ttu-id="2cdd3-118">Créer une base de données du serveur de rapports en mode natif &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2cdd3-118">Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)  
 <span data-ttu-id="2cdd3-119">Indique la procédure à suivre pour créer une base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-119">Provides steps for creating a report server database.</span></span> <span data-ttu-id="2cdd3-120">Cette étape est nécessaire pour déployer une installation de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-120">This step is required for deploying a Reporting Services installation.</span></span>  
  
### <a name="advanced-or-optional-configuration"></a><span data-ttu-id="2cdd3-121">Configuration avancée ou facultative</span><span class="sxs-lookup"><span data-stu-id="2cdd3-121">Advanced or Optional Configuration</span></span>  
 [<span data-ttu-id="2cdd3-122">Configurer un déploiement par montée en puissance parallèle de serveurs de rapports en mode natif &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2cdd3-122">Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md)  
 <span data-ttu-id="2cdd3-123">Indique la procédure à suivre pour configurer plusieurs serveurs de rapports afin qu'ils partagent une base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-123">Provides steps for configuring multiple report servers to share a report server database.</span></span>  
  
 [<span data-ttu-id="2cdd3-124">Configurer un serveur de rapports pour la remise par messagerie &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="2cdd3-124">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="2cdd3-125">Fournit des instructions de configuration d'un serveur de rapports pour la distribution par messagerie.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-125">Provides steps for configuring a report server for e-mail distribution.</span></span>  
  
 [<span data-ttu-id="2cdd3-126">Configurer un pare-feu pour accéder au serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="2cdd3-126">Configure a Firewall for Report Server Access</span></span>](configure-a-firewall-for-report-server-access.md)  
 <span data-ttu-id="2cdd3-127">Explique comment ouvrir les ports utilisés pour les demandes entrantes et les réponses sortantes d'un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-127">Explains how to open ports used for inbound requests and outbound responses from a report server.</span></span>  
  
 [<span data-ttu-id="2cdd3-128">Configurer un serveur de rapports en mode natif pour l’administration locale &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2cdd3-128">Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;</span></span>](configure-a-native-mode-report-server-for-local-administration-ssrs.md)  
 <span data-ttu-id="2cdd3-129">Décrit les étapes supplémentaires requises pour se connecter au Gestionnaire de rapports ou à un serveur de rapports en utilisant http://localhost.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-129">Describes additional steps required to connect to Report Manager or a report server using http://localhost.</span></span>  
  
 [<span data-ttu-id="2cdd3-130">Configurer un serveur de rapports pour l'administration à distance</span><span class="sxs-lookup"><span data-stu-id="2cdd3-130">Configure a Report Server for Remote Administration</span></span>](configure-a-report-server-for-remote-administration.md)  
 <span data-ttu-id="2cdd3-131">Explique comment configurer une instance de serveur de rapports distante afin que vous puissiez vous y connecter et le configurer à partir d'un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-131">Explains how to configure a remote report server instance so that you can connect to and configure it from a different computer.</span></span>  
  
 [<span data-ttu-id="2cdd3-132">Activer ou désactiver les fonctionnalités Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2cdd3-132">Turn Reporting Services Features On or Off</span></span>](turn-reporting-services-features-on-or-off.md)  
 <span data-ttu-id="2cdd3-133">Explique comment supprimer les fonctionnalités inutilisées dans une installation Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-133">Explains how to remove unused features in a Reporting Services installation.</span></span>  
  
 [<span data-ttu-id="2cdd3-134">Activer les erreurs distantes &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2cdd3-134">Enable Remote Errors &#40;Reporting Services&#41;</span></span>](enable-remote-errors-reporting-services.md)  
 <span data-ttu-id="2cdd3-135">Explique comment définir des propriétés de serveur sur un serveur de rapports de façon à retourner des informations supplémentaires concernant les conditions d'erreur qui se produisent sur des serveurs distants.</span><span class="sxs-lookup"><span data-stu-id="2cdd3-135">Explains how to set server properties on a report server to return additional information about error conditions that occur on remote servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cdd3-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2cdd3-136">See Also</span></span>  
 <span data-ttu-id="2cdd3-137">[Configurer et administrer un serveur de rapports &#40;SSRS en mode natif&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="2cdd3-137">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="2cdd3-138">Configuration et administration d’un serveur de rapports &#40;mode SharePoint de Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2cdd3-138">Configuration and Administration of a Report Server &#40;Reporting Services SharePoint Mode&#41;</span></span>](../configure-administer-report-server-reporting-services-sharepoint-mode.md)  
  
  
