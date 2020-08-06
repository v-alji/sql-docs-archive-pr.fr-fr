---
title: Configurer un serveur pour l’écoute sur un autre canal (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Named Pipes [SQL Server], configuring
- listening [SQL Server], pipes
- pipes [SQL Server], alternate
- alternate pipes [SQL Server]
ms.assetid: 914f7491-e2be-4b0d-b3aa-fe5409cdbafa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 57d70cf4cd1d7474b895aeb8cb144c885e8a0f99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601096"
---
# <a name="configure-a-server-to-listen-on-an-alternate-pipe-sql-server-configuration-manager"></a><span data-ttu-id="390b5-102">Configurer un serveur pour l'écoute d'un canal de remplacement (Gestionnaire de configuration SQL Server)</span><span class="sxs-lookup"><span data-stu-id="390b5-102">Configure a Server to Listen on an Alternate Pipe (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="390b5-103">Cette rubrique décrit comment configurer un serveur pour l'écoute sur un autre canal dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide du Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="390b5-103">This topic describes how to configure a server to listen on an alternate pipe in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="390b5-104">Par défaut, l’instance par défaut du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] écoute le canal nommé \\\\.\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="390b5-104">By default, the default instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on named pipe \\\\.\pipe\sql\query.</span></span> <span data-ttu-id="390b5-105">Les instances nommées de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et de [!INCLUDE[ssEW](../../includes/ssew-md.md)] écoutent d'autres canaux.</span><span class="sxs-lookup"><span data-stu-id="390b5-105">Named instances of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] listen on other pipes.</span></span>  
  
 <span data-ttu-id="390b5-106">Il y a trois manières de se connecter à un canal nommé spécifique avec une application cliente :</span><span class="sxs-lookup"><span data-stu-id="390b5-106">There are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="390b5-107">Exécution du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="390b5-107">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="390b5-108">Création d'un alias sur le client, spécification du canal nommé.</span><span class="sxs-lookup"><span data-stu-id="390b5-108">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="390b5-109">Programmer le client pour une connexion à l'aide d'une chaîne de connexion personnalisée.</span><span class="sxs-lookup"><span data-stu-id="390b5-109">Program the client to connect using a custom connection string.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="390b5-110">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="390b5-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-configure-the-named-pipe-used-by-the-sql-server-database-engine"></a><span data-ttu-id="390b5-111">Pour configurer le canal nommé utilisé par le moteur de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="390b5-111">To configure the named pipe used by the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="390b5-112">Dans le Gestionnaire de configuration SQL Server, dans le volet de la console, développez **Configuration du réseau SQL Server**, puis cliquez pour développer **Protocoles pour** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="390b5-112">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, and then click expand **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="390b5-113">Dans le volet d’informations, cliquez avec le bouton droit sur **Canaux nommés**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="390b5-113">In the details pane, right-click **Named Pipes**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="390b5-114">Sous l'onglet **Protocole** , dans la zone **Nom du canal** , tapez le canal que le [!INCLUDE[ssDE](../../includes/ssde-md.md)] doit écouter, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="390b5-114">On the **Protocol** tab, in the **Pipe Name** box, type the pipe you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="390b5-115">Dans le volet de la console, cliquez sur **Services SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="390b5-115">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="390b5-116">Dans le volet d’informations, cliquez avec le bouton droit sur **SQL Server (** \<instance name> **)** , puis cliquez sur **Redémarrer** pour arrêter et redémarrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="390b5-116">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="390b5-117">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] écoute un autre canal, il y a trois manières de se connecter à un canal nommé spécifique avec une application cliente :</span><span class="sxs-lookup"><span data-stu-id="390b5-117">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening on an alternate pipe, there are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="390b5-118">Exécution du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="390b5-118">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="390b5-119">Création d'un alias sur le client, spécification du canal nommé.</span><span class="sxs-lookup"><span data-stu-id="390b5-119">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="390b5-120">Programmer le client pour une connexion à l'aide d'une chaîne de connexion personnalisée.</span><span class="sxs-lookup"><span data-stu-id="390b5-120">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="390b5-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="390b5-121">See Also</span></span>  
 <span data-ttu-id="390b5-122">[Créer ou modifier un alias de serveur devant être utilisé par un client &#40;Gestionnaire de configuration SQL Server&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span><span class="sxs-lookup"><span data-stu-id="390b5-122">[Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span></span>  
 [<span data-ttu-id="390b5-123">Configuration réseau du serveur</span><span class="sxs-lookup"><span data-stu-id="390b5-123">Server Network Configuration</span></span>](server-network-configuration.md)  
  
  
