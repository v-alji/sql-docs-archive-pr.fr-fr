---
title: Protocoles réseau et bibliothèques réseau | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- protocols [SQL Server]
- configuration options [SQL Server], protocols
- network libraries [SQL Server]
- protocols [SQL Server], about network protocols
- pipes [SQL Server]
- network protocols [SQL Server]
- default SQL Server configurations
- library [SQL Server]
- network protocols [SQL Server], about network protocols
- configuration options [SQL Server], libraries
ms.assetid: 8cd437f6-9af1-44ce-9cb0-4d10c83da9ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be012ea2bc9499a99ca7763446c6f26cf219a18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613779"
---
# <a name="network-protocols-and-network-libraries"></a><span data-ttu-id="e34d0-102">Protocoles réseau et bibliothèques réseau</span><span class="sxs-lookup"><span data-stu-id="e34d0-102">Network Protocols and Network Libraries</span></span>
  <span data-ttu-id="e34d0-103">Un serveur peut être à l'écoute ou contrôler plusieurs protocoles réseau simultanément.</span><span class="sxs-lookup"><span data-stu-id="e34d0-103">A server can listen on, or monitor, multiple network protocols at one time.</span></span> <span data-ttu-id="e34d0-104">Cependant, chaque protocole doit être configuré.</span><span class="sxs-lookup"><span data-stu-id="e34d0-104">However, each protocol must be configured.</span></span> <span data-ttu-id="e34d0-105">Lorsqu'un protocole spécifique n'est pas configuré, le serveur ne peut pas se placer à l'écoute de ce protocole.</span><span class="sxs-lookup"><span data-stu-id="e34d0-105">If a particular protocol is not configured, the server cannot listen on that protocol.</span></span> <span data-ttu-id="e34d0-106">Après l'installation, vous pouvez modifier ces configurations de protocole avec le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e34d0-106">After installation, you can change the protocol configurations using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="default-sql-server-network-configuration"></a><span data-ttu-id="e34d0-107">Configuration réseau par défaut de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e34d0-107">Default SQL Server Network Configuration</span></span>  
 <span data-ttu-id="e34d0-108">Une instance par défaut de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configurée pour le port TCP/IP 1433 et le canal nommé \\\\.\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="e34d0-108">A default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for TCP/IP port 1433, and named pipe \\\\.\pipe\sql\query.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e34d0-109">sont configurées pour des ports dynamiques TCP, avec un numéro de port attribué par le système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="e34d0-109">named instances are configured for TCP dynamic ports, with a port number assigned by the operating system.</span></span>  
  
 <span data-ttu-id="e34d0-110">Si vous ne pouvez pas utiliser les adresses de port dynamiques (par exemple, lorsque des connexions d' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doivent traverser un serveur pare-feu configuré pour passer des adresses de port spécifiques),</span><span class="sxs-lookup"><span data-stu-id="e34d0-110">If you cannot use dynamic port addresses (for example, when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections must pass through a firewall server configured to pass through specific port addresses).</span></span> <span data-ttu-id="e34d0-111">sélectionnez un numéro de port non assigné.</span><span class="sxs-lookup"><span data-stu-id="e34d0-111">Select an unassigned port number.</span></span> <span data-ttu-id="e34d0-112">Les affectations de numéro de port sont gérées par l’IANA (Internet Assigned Numbers Authority) et sont listées dans [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span><span class="sxs-lookup"><span data-stu-id="e34d0-112">Port number assignments are managed by the Internet Assigned Numbers Authority and are listed at [http://www.iana.org](https://go.microsoft.com/fwlink/?LinkId=48844).</span></span>  
  
 <span data-ttu-id="e34d0-113">Pour renforcer la sécurité, la connectivité réseau n'est pas entièrement activée lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="e34d0-113">To enhance security, network connectivity is not fully enabled when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span> <span data-ttu-id="e34d0-114">Pour activer, désactiver et configurer les protocoles réseau une fois l'installation terminée, utilisez la zone Configuration du réseau [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e34d0-114">To enable, disable, and configure network protocols after Setup is complete, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Configuration area of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="server-message-block-protocol"></a><span data-ttu-id="e34d0-115">Protocole SMB</span><span class="sxs-lookup"><span data-stu-id="e34d0-115">Server Message Block Protocol</span></span>  
 <span data-ttu-id="e34d0-116">Les serveurs déployés dans le réseau de périmètre doivent avoir tous les protocoles inutilisés désactivés, y compris le protocole SMB (Server Message Block).</span><span class="sxs-lookup"><span data-stu-id="e34d0-116">Servers in the perimeter network should have all unnecessary protocols disabled, including server message block (SMB).</span></span> <span data-ttu-id="e34d0-117">Les serveurs Web et les serveurs DNS (Domain Name System) ne nécessitent pas SMB.</span><span class="sxs-lookup"><span data-stu-id="e34d0-117">Web servers and Domain Name System (DNS) servers do not require SMB.</span></span> <span data-ttu-id="e34d0-118">Ce protocole doit être désactivé pour limiter le risque lié à l'énumération des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e34d0-118">This protocol should be disabled to counter the threat of user enumeration.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e34d0-119">La désactivation du protocole SMB empêchera au service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou Windows Cluster d'accéder au partage de fichiers distant.</span><span class="sxs-lookup"><span data-stu-id="e34d0-119">Disabling Server Message Block will block the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Windows Cluster service from accessing the remote file share.</span></span> <span data-ttu-id="e34d0-120">Ne désactivez pas SMB si vous effectuez l'une des opérations suivantes ou si vous planifiez de le faire :</span><span class="sxs-lookup"><span data-stu-id="e34d0-120">Do not disable SMB if you do or plan to do one of the following:</span></span>  
> 
>  -   <span data-ttu-id="e34d0-121">Utiliser le nœud de cluster Windows et le mode de quorum majoritaire du partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e34d0-121">Use Windows Cluster Node and File Share Majority Quorum mode</span></span>  
> -   <span data-ttu-id="e34d0-122">Spécifier un partage de fichiers SMB comme répertoire de données pendant l'installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e34d0-122">Specify an SMB file share as the data directory during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation</span></span>  
> -   <span data-ttu-id="e34d0-123">Créer un fichier de base de données sur un partage de fichiers SMB.</span><span class="sxs-lookup"><span data-stu-id="e34d0-123">Create a database file on an SMB file share</span></span>  
  
#### <a name="to-disable-smb"></a><span data-ttu-id="e34d0-124">Pour désactiver le protocole SMB</span><span class="sxs-lookup"><span data-stu-id="e34d0-124">To disable SMB</span></span>  
  
1.  <span data-ttu-id="e34d0-125">Dans le menu **Démarrer** , pointez sur **Paramètres**, puis cliquez sur **Connexions réseau et accès à distance**.</span><span class="sxs-lookup"><span data-stu-id="e34d0-125">On the **Start** menu, point to **Settings**, and then click **Network and Dial-up Connections**.</span></span>  
  
     <span data-ttu-id="e34d0-126">Cliquez avec le bouton droit sur la connexion Internet, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e34d0-126">Right-click the Internet-facing connection, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e34d0-127">Activez la case à cocher **Client pour les réseaux Microsoft** , puis cliquez sur **Désinstaller**.</span><span class="sxs-lookup"><span data-stu-id="e34d0-127">Select the **Client for Microsoft Networks** check box, and then click **Uninstall**.</span></span>  
  
3.  <span data-ttu-id="e34d0-128">Suivez les étapes de désinstallation.</span><span class="sxs-lookup"><span data-stu-id="e34d0-128">Follow the uninstall steps.</span></span>  
  
4.  <span data-ttu-id="e34d0-129">Sélectionnez **Partage de fichiers et d'imprimantes pour les réseaux Microsoft**, puis cliquez sur **Désinstaller**.</span><span class="sxs-lookup"><span data-stu-id="e34d0-129">Select **File and Printer Sharing for Microsoft Networks**, and then click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="e34d0-130">Suivez les étapes de désinstallation.</span><span class="sxs-lookup"><span data-stu-id="e34d0-130">Follow the uninstall steps.</span></span>  
  
#### <a name="to-disable-smb-on-servers-accessible-from-the-internet"></a><span data-ttu-id="e34d0-131">Pour désactiver SMB sur les serveurs accessibles à partir d'Internet</span><span class="sxs-lookup"><span data-stu-id="e34d0-131">To disable SMB on servers accessible from the Internet</span></span>  
  
-   <span data-ttu-id="e34d0-132">Dans les propriétés de Connexion au réseau local, utilisez la boîte de dialogue **Propriétés de Protocole Internet TCP/IP** pour supprimer **Partage de fichiers et d’imprimantes pour les réseaux Microsoft** et **Client pour les réseaux Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="e34d0-132">In the Local Area Connection properties, use the **Transmission Control Protocol/Internet Protocol (TCP/IP) properties** dialog box to remove **File and Printer Sharing for Microsoft Networks** and **Client for Microsoft Networks**.</span></span>  
  
## <a name="endpoints"></a><span data-ttu-id="e34d0-133">Points de terminaison</span><span class="sxs-lookup"><span data-stu-id="e34d0-133">Endpoints</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e34d0-134">introduit un nouveau concept pour les connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; la connexion est représentée à l’extrémité du serveur sous la forme d’un [!INCLUDE[tsql](../../includes/tsql-md.md)]*point de terminaison*.</span><span class="sxs-lookup"><span data-stu-id="e34d0-134">introduces a new concept for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections; the connection is represented on the server end by a [!INCLUDE[tsql](../../includes/tsql-md.md)]*endpoint*.</span></span> <span data-ttu-id="e34d0-135">Des autorisations peuvent être accordées, retirées et refusées pour les points de terminaison [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e34d0-135">Permissions can be granted, revoked, and denied for [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints.</span></span> <span data-ttu-id="e34d0-136">Par défaut, tous les utilisateurs ont l'autorisation d'accéder à un point de terminaison sauf si cette autorisation est refusée ou retirée par un membre du groupe sysadmin ou par le propriétaire du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e34d0-136">By default, all users have permissions to access an endpoint unless the permissions are denied or revoked by a member of the sysadmin group or by the endpoint owner.</span></span> <span data-ttu-id="e34d0-137">La syntaxe GRANT, REVOKE et DENY ENDPOINT utilise un ID de point de terminaison que l'administrateur doit prendre dans l'affichage catalogue du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e34d0-137">The GRANT, REVOKE, and DENY ENDPOINT syntax uses an endpoint ID that the administrator must get from the endpoint's catalog view.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e34d0-138">crée des points de terminaison [!INCLUDE[tsql](../../includes/tsql-md.md)] pour tous les protocoles réseau pris en charge, ainsi que pour la connexion administrateur dédiée.</span><span class="sxs-lookup"><span data-stu-id="e34d0-138">Setup creates [!INCLUDE[tsql](../../includes/tsql-md.md)] endpoints for all supported network protocols, as well as for the dedicated administrator connection.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="e34d0-139">créés par le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se présentent comme suit :</span><span class="sxs-lookup"><span data-stu-id="e34d0-139">endpoints created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup are as follows:</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="e34d0-140">ordinateur local</span><span class="sxs-lookup"><span data-stu-id="e34d0-140">local machine</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="e34d0-141">canaux nommés</span><span class="sxs-lookup"><span data-stu-id="e34d0-141">named pipes</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="e34d0-142">par défaut</span><span class="sxs-lookup"><span data-stu-id="e34d0-142">default TCP</span></span>  
  
 <span data-ttu-id="e34d0-143">Pour plus d’informations sur les points de terminaison, consultez [Configurer le moteur de base de données de manière à écouter sur plusieurs ports TCP](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) et [Affichages catalogue de points de terminaison &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e34d0-143">For more information about endpoints, see [Configure the Database Engine to Listen on Multiple TCP Ports](../../database-engine/configure-windows/configure-the-database-engine-to-listen-on-multiple-tcp-ports.md) and [Endpoints Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql).</span></span>  
  
 <span data-ttu-id="e34d0-144">Pour plus d’informations sur les configurations réseau [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consultez la rubrique suivante dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="e34d0-144">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network configurations, see the following topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="e34d0-145">Configuration réseau du serveur</span><span class="sxs-lookup"><span data-stu-id="e34d0-145">Server Network Configuration</span></span>](../../database-engine/configure-windows/server-network-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="e34d0-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e34d0-146">See Also</span></span>  
 <span data-ttu-id="e34d0-147">[Configuration de la surface d'exposition](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="e34d0-147">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 <span data-ttu-id="e34d0-148">[Considérations sur la sécurité pour une installation SQL Server](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="e34d0-148">[Security Considerations for a SQL Server Installation](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="e34d0-149">Planification d'une installation SQL Server</span><span class="sxs-lookup"><span data-stu-id="e34d0-149">Planning a SQL Server Installation</span></span>](../../../2014/sql-server/install/planning-a-sql-server-installation.md)  
  
  
