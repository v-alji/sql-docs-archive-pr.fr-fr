---
title: Configurer des protocoles clients | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default protocols
- network protocols [SQL Server], client configuration
- TCP/IP [SQL Server], client protocols
- disabling client protocols
- ordering protocols [SQL Server]
- protocols [SQL Server], order for client computers
- configure client protocols
- client protocols [SQL Server]
- protocols [SQL Server], client configuration
ms.assetid: 3dfa2702-ba65-43b4-a777-6727846e133a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2eb223815c3e3af50813e02d3ded60573c327155
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614850"
---
# <a name="configure-client-protocols"></a><span data-ttu-id="7112b-102">configurer des protocoles clients</span><span class="sxs-lookup"><span data-stu-id="7112b-102">Configure Client Protocols</span></span>
  <span data-ttu-id="7112b-103">Cette rubrique décrit comment configurer les protocoles clients utilisés par les applications clientes dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7112b-103">This topic describes how to configure client protocols used by client applications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="7112b-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prend en charge la communication cliente par le biais du protocole réseau TCP/IP et du protocole des canaux nommés.</span><span class="sxs-lookup"><span data-stu-id="7112b-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports client communication with the TCP/IP network protocol and the named pipes protocol.</span></span> <span data-ttu-id="7112b-105">Le protocole de mémoire partagée est également disponible si le client se connecte à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7112b-105">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="7112b-106">Il existe trois méthodes courantes de sélection du protocole.</span><span class="sxs-lookup"><span data-stu-id="7112b-106">There are three common methods of selecting the protocol.</span></span>  
  
-   <span data-ttu-id="7112b-107">Configurer toutes les applications clientes de manière à ce qu'elles utilisent le même protocole réseau, en définissant l'ordre des protocoles dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7112b-107">Configure all client applications to use the same network protocol by setting the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
-   <span data-ttu-id="7112b-108">Configurer une application cliente spécifique de manière à ce qu'elle utilise un protocole réseau particulier, en créant un alias.</span><span class="sxs-lookup"><span data-stu-id="7112b-108">Configure a single client application to use a different network protocol by creating an alias.</span></span> <span data-ttu-id="7112b-109">Pour plus d’informations, consultez [Créer ou supprimer un alias de serveur devant être utilisé par un client &#40;Gestionnaire de configuration SQL Server&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="7112b-109">For more information, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="7112b-110">Certaines applications clientes, telles que sqlcmd.exe, peuvent spécifier le protocole dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="7112b-110">Some client applications, such as sqlcmd.exe, can specify the protocol as part of the connection string.</span></span> <span data-ttu-id="7112b-111">Pour plus d’informations, consultez [Se connecter au moteur de base de données avec sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="7112b-111">For more information, see [Connect to the Database Engine With sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7112b-112">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="7112b-112">Using SQL Server Configuration Manager</span></span>  
  
###  <a name="to-enable-or-disable-a-client-protocol"></a><a name="EnableDisable"></a> <span data-ttu-id="7112b-113">Pour activer ou désactiver un protocole client</span><span class="sxs-lookup"><span data-stu-id="7112b-113">To enable or disable a client protocol</span></span>  
  
1.  <span data-ttu-id="7112b-114">Dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], développez **Configuration de SQL Server Native Client**, cliquez avec le bouton droit sur **Protocoles clients**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7112b-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7112b-115">Dans la zone **Protocoles désactivés**, cliquez sur un protocole, puis sélectionnez **Activer** pour l’activer.</span><span class="sxs-lookup"><span data-stu-id="7112b-115">Click a protocol in the **Disabled Protocols** box, and then click **Enable**, to enable a protocol.</span></span>  
  
3.  <span data-ttu-id="7112b-116">Dans la zone **Protocoles activés**, cliquez sur un protocole, puis sélectionnez **Désactiver** pour le désactiver.</span><span class="sxs-lookup"><span data-stu-id="7112b-116">Click a protocol in the **Enabled Protocols** box, and then click **Disable**, to disable a protocol.</span></span>  
  
###  <a name="to-change-the-default-protocol-or-the-protocol-order-for-client-computers"></a><a name="ChangeDefault"></a> <span data-ttu-id="7112b-117">Pour modifier le protocole par défaut ou l’ordre des protocoles pour les ordinateurs clients</span><span class="sxs-lookup"><span data-stu-id="7112b-117">To change the default protocol or the protocol order for client computers</span></span>  
  
1.  <span data-ttu-id="7112b-118">Dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], développez **Configuration de SQL Server Native Client**, cliquez avec le bouton droit sur **Protocoles clients**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7112b-118">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7112b-119">Dans la zone **Protocoles activés**, cliquez sur **Monter** ou sur **Descendre** pour modifier l’ordre dans lequel les protocoles sont essayés lors d’une tentative de connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7112b-119">In the **Enabled Protocols** box, click **Move Up** or **Move Down**, to change the order in which protocols are tried, when attempting to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7112b-120">Le protocole figurant en première position dans la zone **Protocoles activés** est le protocole par défaut.</span><span class="sxs-lookup"><span data-stu-id="7112b-120">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="7112b-121">Le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crée des entrées de Registre pour les configurations d'alias de serveur et la bibliothèque réseau cliente par défaut.</span><span class="sxs-lookup"><span data-stu-id="7112b-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager creates registry entries for the server alias configurations and default client network library.</span></span> <span data-ttu-id="7112b-122">Toutefois, l'application n'installe pas les bibliothèques réseau clientes, ni les protocoles réseau [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7112b-122">However, the application does not install either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries or the network protocols.</span></span> <span data-ttu-id="7112b-123">Les bibliothèques réseau clientes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont installées au cours de l’installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les protocoles réseau sont installés lors de l’installation de Microsoft Windows (ou via **Réseaux** dans le **Panneau de configuration**).</span><span class="sxs-lookup"><span data-stu-id="7112b-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries are installed during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup; the network protocols are installed as part of Microsoft Windows Setup (or through **Networks** in **Control Panel**).</span></span> <span data-ttu-id="7112b-124">Un protocole réseau spécifique peut ne pas être disponible lors de l’installation de Windows.</span><span class="sxs-lookup"><span data-stu-id="7112b-124">A particular network protocol may not be available as part of Windows Setup.</span></span> <span data-ttu-id="7112b-125">Pour plus d'informations concernant l’installation de ces protocoles réseau, consultez la documentation de l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="7112b-125">For more information about installing these network protocols, see the vendor documentation.</span></span>  
  
###  <a name="to-configure-a-client-to-use-tcpip"></a><a name="Configure"></a> <span data-ttu-id="7112b-126">Pour configurer un client pour l’utilisation de TCP/IP</span><span class="sxs-lookup"><span data-stu-id="7112b-126">To configure a client to use TCP/IP</span></span>  
  
1.  <span data-ttu-id="7112b-127">Dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], développez **Configuration de SQL Server Native Client**, cliquez avec le bouton droit sur **Protocoles clients**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7112b-127">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7112b-128">Dans la zone **Protocoles activés**, cliquez sur la flèche vers le haut ou vers le bas pour modifier l’ordre dans lequel les protocoles sont essayés lors d’une tentative de connexion à SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7112b-128">In the **Enabled Protocols** box, click the up and down arrows to change the order in which protocols are tried, when attempting to connect to SQL Server.</span></span> <span data-ttu-id="7112b-129">Le protocole figurant en première position dans la zone **Protocoles activés** est le protocole par défaut.</span><span class="sxs-lookup"><span data-stu-id="7112b-129">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
 <span data-ttu-id="7112b-130">Vous pouvez activer le protocole de mémoire partagée séparément en cochant la case **Activer le protocole de mémoire partagée**.</span><span class="sxs-lookup"><span data-stu-id="7112b-130">The shared memory protocol is enabled separately by checking the **Enabled Shared Memory Protocol** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7112b-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7112b-131">See Also</span></span>  
 [<span data-ttu-id="7112b-132">Configurer l’option de configuration du serveur remote login timeout</span><span class="sxs-lookup"><span data-stu-id="7112b-132">Configure the remote login timeout Server Configuration Option</span></span>](configure-the-remote-login-timeout-server-configuration-option.md)  
  
  
