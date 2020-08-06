---
title: Configuration de la surface d’exposition | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- reducing attackable surface area
- upgrading SQL Server, security
- surface area configuration [SQL Server]
- surface area configuration [SQL Server], about surface area configuration
- attackable surface area [SQL Server]
- installing SQL Server, security
ms.assetid: f741169c-1453-4ad2-830b-bf2be27d712f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ef64fbbeb2b8953ff3816db63572b499d42f012e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697660"
---
# <a name="surface-area-configuration"></a><span data-ttu-id="871c6-102">Configuration de la surface d'exposition</span><span class="sxs-lookup"><span data-stu-id="871c6-102">Surface Area Configuration</span></span>
  <span data-ttu-id="871c6-103">Dans la configuration par défaut des nouvelles installations de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], de nombreuses fonctionnalités ne sont pas activées.</span><span class="sxs-lookup"><span data-stu-id="871c6-103">In the default configuration of new installations of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], many features are not enabled.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="871c6-104">installe et démarre de manière sélective uniquement les principaux services et fonctionnalités, de manière à réduire le nombre de fonctionnalités qui peuvent être soumises à une attaque d'un utilisateur malveillant.</span><span class="sxs-lookup"><span data-stu-id="871c6-104">selectively installs and starts only key services and features, to minimize the number of features that can be attacked by a malicious user.</span></span> <span data-ttu-id="871c6-105">Un administrateur système peut modifier ces valeurs par défaut au moment de l'installation, et également activer ou désactiver sélectivement les fonctionnalités d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="871c6-105">A system administrator can change these defaults at installation time and also selectively enable or disable features of a running instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="871c6-106">En outre, certains composants peuvent ne pas être disponibles lors de la connexion à partir d'autres ordinateurs jusqu'à ce que les protocoles soient configurés.</span><span class="sxs-lookup"><span data-stu-id="871c6-106">Additionally, some components may not be available when connecting from other computers until protocols are configured.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="871c6-107">Contrairement aux nouvelles installations, aucun service ou fonctionnalité existant n'est désactivé durant une mise à niveau, mais des options de configuration de la surface d'exposition supplémentaires peuvent être appliquées une fois la mise à niveau terminée.</span><span class="sxs-lookup"><span data-stu-id="871c6-107">Unlike new installations, no existing services or features are turned off during an upgrade, but additional surface area configuration options can be applied after the upgrade is completed.</span></span>  
  
## <a name="protocols-connection-and-startup-options"></a><span data-ttu-id="871c6-108">Protocoles, connexion et options de démarrage</span><span class="sxs-lookup"><span data-stu-id="871c6-108">Protocols, Connection, and Startup Options</span></span>  
 <span data-ttu-id="871c6-109">Utilisez le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour démarrer et arrêter des services, configurer les options de démarrage et activer des protocoles et autres options de connexion.</span><span class="sxs-lookup"><span data-stu-id="871c6-109">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to start and stop services, configure the startup options, and enable protocols and other connection options.</span></span>  
  
#### <a name="to-start-sql-server-configuration-manager"></a><span data-ttu-id="871c6-110">Pour démarrer le Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="871c6-110">To start SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="871c6-111">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="871c6-111">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    -   <span data-ttu-id="871c6-112">Utilisez la zone **Services SQL Server** pour démarrer des composants et configurer les options de démarrage automatique.</span><span class="sxs-lookup"><span data-stu-id="871c6-112">Use the **SQL Server Services** area to start components and configure the automatic starting options.</span></span>  
  
    -   <span data-ttu-id="871c6-113">Utilisez la zone **Configuration du réseau SQL Server** pour activer des protocoles de connexion et des options de connexion telles que les ports TCP/IP fixes ou le forçage du chiffrement.</span><span class="sxs-lookup"><span data-stu-id="871c6-113">Use the **SQL Server Network Configuration** area to enable connection protocols, and connection options such as fixed TCP/IP ports, or forcing encryption.</span></span>  
  
 <span data-ttu-id="871c6-114">Pour plus d'informations, consultez [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="871c6-114">For more information, see [SQL Server Configuration Manager](../sql-server-configuration-manager.md).</span></span> <span data-ttu-id="871c6-115">La connectivité distante peut également dépendre de la configuration correcte d'un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="871c6-115">Remote connectivity can also depend upon the correct configuration of a firewall.</span></span> <span data-ttu-id="871c6-116">Pour plus d’informations, consultez [Configurer le Pare-feu Windows pour autoriser l’accès à SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="871c6-116">For more information, see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
## <a name="enabling-and-disabling-features"></a><span data-ttu-id="871c6-117">Activation et désactivation de fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="871c6-117">Enabling and Disabling Features</span></span>  
 <span data-ttu-id="871c6-118">L'activation et la désactivation de fonctionnalités [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut être configurée à l'aide de facettes dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="871c6-118">Enabling and disabling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features can be configured using facets in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-configure-surface-area-using-facets"></a><span data-ttu-id="871c6-119">Pour configurer la surface d'exposition à l'aide de facettes</span><span class="sxs-lookup"><span data-stu-id="871c6-119">To configure surface area using facets</span></span>  
  
1.  <span data-ttu-id="871c6-120">Dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , connectez-vous à un composant de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="871c6-120">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] connect to a component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="871c6-121">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le serveur, puis cliquez sur **Facettes**.</span><span class="sxs-lookup"><span data-stu-id="871c6-121">In Object Explorer, right-click the server, and then click **Facets**.</span></span>  
  
3.  <span data-ttu-id="871c6-122">Dans la boîte de dialogue **Afficher les facettes** , développez la liste **Facette** et sélectionnez la facette **Configuration de la surface d’exposition** appropriée (**Configuration de la surface d’exposition**, **Configuration de la surface d’exposition pour Analysis Services**ou **Configuration de la surface d’exposition pour Reporting Services**).</span><span class="sxs-lookup"><span data-stu-id="871c6-122">In the **View Facets** dialog box, expand the **Facet** list, and select the appropriate **Surface Area Configuration** facet (**Surface Area Configuration**, **Surface Area Configuration for Analysis Services**, or **Surface Area Configuration for Reporting Services**).</span></span>  
  
4.  <span data-ttu-id="871c6-123">Dans la zone **Propriétés de la facette** , sélectionnez les valeurs souhaitées pour chaque propriété.</span><span class="sxs-lookup"><span data-stu-id="871c6-123">In the **Facet properties** area, select the values that you want for each property.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="871c6-124">Pour vérifier périodiquement la configuration d'une facette, utilisez la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="871c6-124">To periodically check the configuration of a facet, use Policy-Based Management.</span></span> <span data-ttu-id="871c6-125">Pour plus d’informations sur la gestion basée sur des stratégies, consultez [Administrer des serveurs à l’aide de la gestion basée sur des stratégies](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="871c6-125">For more information about Policy-Based Management, see [Administer Servers by Using Policy-Based Management](../policy-based-management/administer-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="871c6-126">Vous pouvez également définir des options du [!INCLUDE[ssDE](../../includes/ssde-md.md)] à l'aide de la procédure stockée `sp_configure`.</span><span class="sxs-lookup"><span data-stu-id="871c6-126">You can also set [!INCLUDE[ssDE](../../includes/ssde-md.md)] options using the `sp_configure` stored procedure.</span></span> <span data-ttu-id="871c6-127">Pour plus d’informations, consultez [Options de configuration de serveur &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="871c6-127">For more information, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
 <span data-ttu-id="871c6-128">Pour modifier la propriété **EnableIntegrated Security** de [!INCLUDE[ssRS](../../includes/ssrs.md)], utilisez les paramètres de propriété dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="871c6-128">To change the **EnableIntegrated Security** property of [!INCLUDE[ssRS](../../includes/ssrs.md)], use the property settings in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="871c6-129">Pour modifier les propriétés **Événements programmés et remise du rapport activés** et **Service Web et accès HTTP activés** , modifiez le fichier de configuration **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="871c6-129">To change the **Schedule events and report delivery** property and the **Web service and HTTP access** property, edit the **RSReportServer.config** configuration file.</span></span>  
  
## <a name="command-prompt-options"></a><span data-ttu-id="871c6-130">Options d'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="871c6-130">Command-prompt Options</span></span>  
 <span data-ttu-id="871c6-131">Utilisez l’applet de commande **Invoke-PolicyEvaluation**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell pour appeler des stratégies de configuration de la surface d’exposition.</span><span class="sxs-lookup"><span data-stu-id="871c6-131">Use the **Invoke-PolicyEvaluation**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell cmdlet to invoke Surface Area Configuration Policies.</span></span> <span data-ttu-id="871c6-132">Pour plus d’informations, consultez [Utiliser les applets de commande du Moteur de base de données](../../database-engine/use-the-database-engine-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="871c6-132">For more information, see [Use the Database Engine cmdlets](../../database-engine/use-the-database-engine-cmdlets.md).</span></span>  
  
## <a name="soap-and-service-broker-endpoints"></a><span data-ttu-id="871c6-133">Points de terminaison SOAP et Service Broker</span><span class="sxs-lookup"><span data-stu-id="871c6-133">SOAP and Service Broker Endpoints</span></span>  
 <span data-ttu-id="871c6-134">Pour désactiver des points de terminaison, utilisez la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="871c6-134">To turn endpoints off, use Policy-Based Management.</span></span> <span data-ttu-id="871c6-135">Pour créer et modifier les propriétés de points de terminaison, utilisez [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) et [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="871c6-135">To create and alter the properties of endpoints, use [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) and [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="871c6-136">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="871c6-136">Related Content</span></span>  
 [<span data-ttu-id="871c6-137">Centre de sécurité pour le moteur de base de données SQL Server et Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="871c6-137">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="871c6-138">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="871c6-138">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
