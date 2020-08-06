---
title: Se connecter à n’importe quel SQL Server composant à partir de SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], SQL Server Management Studio
- saving connections
- components [SQL Server], connections
- SQL Server Management Studio [SQL Server], connections
ms.assetid: 5eeb41bd-b25b-4d3b-a005-a7d9e4b5978e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cd3e185ea6f289a2a6db46cdca2cb310fefbcf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702311"
---
# <a name="connect-to-any-sql-server-component-from-sql-server-management-studio"></a><span data-ttu-id="96c4d-102">Se connecter à n'importe quel composant de SQL Server à partir de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96c4d-102">Connect to Any SQL Server Component from SQL Server Management Studio</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="96c4d-103">fournit des fonctionnalités pour la gestion de tous les composants de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96c4d-103">provides functionality for managing every component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="96c4d-104">Utilisez [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] pour vous connecter à :</span><span class="sxs-lookup"><span data-stu-id="96c4d-104">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to connect to:</span></span>  
  
-   <span data-ttu-id="96c4d-105">Une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96c4d-105">An instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="96c4d-106">.</span><span class="sxs-lookup"><span data-stu-id="96c4d-106">.</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]<span data-ttu-id="96c4d-107">.</span><span class="sxs-lookup"><span data-stu-id="96c4d-107">.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="96c4d-108">.</span><span class="sxs-lookup"><span data-stu-id="96c4d-108">.</span></span>  
  
 <span data-ttu-id="96c4d-109">Bien que [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] vous permette d'utiliser des requêtes sans que vous deviez établir une connexion à une source de données, la plupart des autres tâches requièrent une connexion.</span><span class="sxs-lookup"><span data-stu-id="96c4d-109">Although [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] allows you to work with queries without first establishing a connection to a data source, most other tasks require a connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="96c4d-110">contient la boîte de dialogue **Se connecter au serveur** qui vous permet de configurer les propriétés de connexion aux composants [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96c4d-110">provides the **Connect to Server** dialog box to configure connection properties to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="96c4d-111">Quand [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] démarre, il ouvre la boîte de dialogue **Se connecter au serveur** et vous invite à vous connecter à un serveur.</span><span class="sxs-lookup"><span data-stu-id="96c4d-111">When [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] starts, it opens the **Connect to Server** dialog box and prompts you to connect to a server.</span></span> <span data-ttu-id="96c4d-112">Le **Se connecter au serveur** boîte de dialogue conserve les paramètres de connexion depuis leur dernière utilisation.</span><span class="sxs-lookup"><span data-stu-id="96c4d-112">The **Connect to Server** dialog box retains the connection settings from the last time it was used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96c4d-113">Cette fonctionnalité peut être désactivée pour qu'aucune connexion ne soit automatiquement établie.</span><span class="sxs-lookup"><span data-stu-id="96c4d-113">This feature can be turned off so no connection is automatically initiated.</span></span> <span data-ttu-id="96c4d-114">Pour plus d’informations, consultez [Options de démarrage du service moteur de base de données](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="96c4d-114">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
## <a name="saving-connections"></a><span data-ttu-id="96c4d-115">enregistrement des connexions</span><span class="sxs-lookup"><span data-stu-id="96c4d-115">Saving Connections</span></span>  
 <span data-ttu-id="96c4d-116">Vous pouvez enregistrer des connexions à des serveurs spécifiques dans les serveurs inscrits ou des connexions dans des projets à l'aide de l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="96c4d-116">You can save connections to specific servers in Registered Servers, or you can save connections in projects with Solution Explorer.</span></span>  
  
### <a name="saving-connections-in-registered-servers"></a><span data-ttu-id="96c4d-117">Enregistrement des connexions dans les serveurs inscrits</span><span class="sxs-lookup"><span data-stu-id="96c4d-117">Saving Connections in Registered Servers</span></span>  
 <span data-ttu-id="96c4d-118">Lorsque vous inscrivez un serveur, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] enregistre les informations de connexion dans les serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="96c4d-118">When you register a server, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] saves the connection information in Registered Servers.</span></span> <span data-ttu-id="96c4d-119">Pour vous connecter à un serveur inscrit, double-cliquez sur le nom du serveur dans les serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="96c4d-119">To connect to a registered server, double-click the server name in Registered Servers.</span></span> <span data-ttu-id="96c4d-120">L'Explorateur d'objets ouvre alors une connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="96c4d-120">Object Explorer then opens a connection to the server.</span></span>  
  
### <a name="saving-connections-in-solution-explorer"></a><span data-ttu-id="96c4d-121">Enregistrement des connexions dans l'Explorateur de solutions</span><span class="sxs-lookup"><span data-stu-id="96c4d-121">Saving Connections in Solution Explorer</span></span>  
 <span data-ttu-id="96c4d-122">L'Explorateur de solutions vous permet de stocker les requêtes, les scripts, les connexions et d'autres informations associées dans un projet.</span><span class="sxs-lookup"><span data-stu-id="96c4d-122">Solution Explorer allows you to store related queries, scripts, connections, and other associated information in a project.</span></span> <span data-ttu-id="96c4d-123">Chaque projet de script contient un nœud appelé **Connexions**où vous pouvez enregistrer une ou plusieurs connexions.</span><span class="sxs-lookup"><span data-stu-id="96c4d-123">Each script project contains a node called **Connections**, where you can save one or more connections.</span></span> <span data-ttu-id="96c4d-124">Pour ajouter une connexion, cliquez avec le bouton droit sur **Connexions**, puis cliquez sur **Nouvelle connexion**.</span><span class="sxs-lookup"><span data-stu-id="96c4d-124">To add a connection, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="96c4d-125">Pour accéder à une connexion enregistrée, développez **Connexions** et double-cliquez sur la connexion.</span><span class="sxs-lookup"><span data-stu-id="96c4d-125">To access a saved connection, expand **Connections** and double-click the connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="96c4d-126">ouvre une fenêtre de requête associée à cette connexion.</span><span class="sxs-lookup"><span data-stu-id="96c4d-126">opens a query window associated with that connection.</span></span> <span data-ttu-id="96c4d-127">Une fois enregistrés, les scripts conservent leur association à une connexion spécifique.</span><span class="sxs-lookup"><span data-stu-id="96c4d-127">When saved, scripts retain their association to a specific connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c4d-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96c4d-128">See Also</span></span>  
 <span data-ttu-id="96c4d-129">[Utiliser SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="96c4d-129">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="96c4d-130">l’Explorateur d’objets</span><span class="sxs-lookup"><span data-stu-id="96c4d-130">Object Explorer</span></span>](../object/object-explorer.md)  
  
  
