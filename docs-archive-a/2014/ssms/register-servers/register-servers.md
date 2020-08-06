---
title: Inscrire des serveurs
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlserverregisteredserver.dhelp
helpviewer_keywords:
- connections [SQL Server], registered servers
- registering servers
- servers [SQL Server], registering
- server management [SQL Server], registering servers
- server registration [SQL Server]
ms.assetid: c2a2513e-fa09-419c-99e7-a12d57c5a0db
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f4b23ba127c6b000b0abbe832c4c072ada78c5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603762"
---
# <a name="register-servers"></a><span data-ttu-id="1077d-102">Inscrire des serveurs</span><span class="sxs-lookup"><span data-stu-id="1077d-102">Register Servers</span></span>
  <span data-ttu-id="1077d-103">L'inscription d'un serveur dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] vous permet de stocker les informations de connexion au serveur pour des connexions futures. Il existe trois façons d'inscrire un serveur dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1077d-103">Registering a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] allows you to store the server connection information for future connections.There are three ways to register a server in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="1077d-104">Les instances locales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont automatiquement inscrites lors du premier lancement de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] après son installation.</span><span class="sxs-lookup"><span data-stu-id="1077d-104">Local instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are automatically registered during the first launch of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] after its installation.</span></span>  
  
2.  <span data-ttu-id="1077d-105">Vous pouvez également initier le processus d'enregistrement automatique à n'importe quel moment, pour restaurer l'inscription des instances de serveur locales.</span><span class="sxs-lookup"><span data-stu-id="1077d-105">You can also initiate the automatic registration process at any time, to restore the registration of local server instances.</span></span>  
  
3.  <span data-ttu-id="1077d-106">Enfin, vous pouvez inscrire un serveur au moyen de l'outil Serveurs inscrits dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1077d-106">Lastly, you can register a server using the Registered Servers tool in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="benefits-of-registered-servers"></a><span data-ttu-id="1077d-107">Avantages des serveurs inscrits</span><span class="sxs-lookup"><span data-stu-id="1077d-107">Benefits of Registered Servers</span></span>  
 <span data-ttu-id="1077d-108">Grâce aux serveurs inscrits, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1077d-108">With Registered Servers you can:</span></span>  
  
-   <span data-ttu-id="1077d-109">inscrire les serveurs pour conserver les informations de connexion ;</span><span class="sxs-lookup"><span data-stu-id="1077d-109">Register servers to preserve the connection information.</span></span>  
  
-   <span data-ttu-id="1077d-110">déterminer si un serveur inscrit est en cours d'exécution ;</span><span class="sxs-lookup"><span data-stu-id="1077d-110">Determine if a registered server is running.</span></span>  
  
-   <span data-ttu-id="1077d-111">connecter facilement l'Explorateur d'objets et l'Éditeur de requête à un serveur inscrit ;</span><span class="sxs-lookup"><span data-stu-id="1077d-111">Easily connect Object Explorer and Query Editor to a registered server.</span></span>  
  
-   <span data-ttu-id="1077d-112">modifier ou supprimer les informations d'inscription d'un serveur inscrit ;</span><span class="sxs-lookup"><span data-stu-id="1077d-112">Edit or delete the registration information for a registered server.</span></span>  
  
-   <span data-ttu-id="1077d-113">créer des groupes de serveurs ;</span><span class="sxs-lookup"><span data-stu-id="1077d-113">Create groups of servers.</span></span>  
  
-   <span data-ttu-id="1077d-114">attribuer des noms conviviaux aux serveurs inscrits en fournissant une valeur dans la zone **Nom du serveur inscrit** (qui est différente de la liste **Nom du serveur** ) ;</span><span class="sxs-lookup"><span data-stu-id="1077d-114">Provide user-friendly names for registered servers by providing a value in the **Registered server name** box that is different from the **Server name** list.</span></span>  
  
-   <span data-ttu-id="1077d-115">fournir une description détaillée des serveurs inscrits ;</span><span class="sxs-lookup"><span data-stu-id="1077d-115">Provide detailed descriptions for registered servers.</span></span>  
  
-   <span data-ttu-id="1077d-116">fournir une description détaillée des groupes de serveurs inscrits ;</span><span class="sxs-lookup"><span data-stu-id="1077d-116">Provide detailed descriptions of registered server groups.</span></span>  
  
-   <span data-ttu-id="1077d-117">exporter des groupes de serveurs inscrits ;</span><span class="sxs-lookup"><span data-stu-id="1077d-117">Export registered server groups.</span></span>  
  
-   <span data-ttu-id="1077d-118">importer des groupes de serveurs inscrits ;</span><span class="sxs-lookup"><span data-stu-id="1077d-118">Import registered server groups.</span></span>  
  
-   <span data-ttu-id="1077d-119">consulter les fichiers journaux de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour les instances en ligne ou hors connexion de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1077d-119">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files for online or offline instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="1077d-120">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="1077d-120">Related Tasks</span></span>  
 <span data-ttu-id="1077d-121">Utilisez les rubriques suivantes pour commencer à utiliser les serveurs inscrits :</span><span class="sxs-lookup"><span data-stu-id="1077d-121">Use the following topics to get started with registered servers:</span></span>  
  
|<span data-ttu-id="1077d-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="1077d-122">**Description**</span></span>|<span data-ttu-id="1077d-123">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="1077d-123">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="1077d-124">Inscrire les instances de serveur locales</span><span class="sxs-lookup"><span data-stu-id="1077d-124">Register local server instances</span></span>|[<span data-ttu-id="1077d-125">Inscrire un serveur connecté &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-125">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](register-a-connected-server-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-126">Inscrire un serveur</span><span class="sxs-lookup"><span data-stu-id="1077d-126">Register a server</span></span>|[<span data-ttu-id="1077d-127">Créer un nouveau serveur inscrit &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-127">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-128">Afficher les serveurs inscrits</span><span class="sxs-lookup"><span data-stu-id="1077d-128">View registered servers</span></span>|[<span data-ttu-id="1077d-129">Afficher des serveurs inscrits dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1077d-129">View Registered Servers in SQL Server Management Studio</span></span>](view-registered-servers-in-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-130">Supprimer un serveur inscrit</span><span class="sxs-lookup"><span data-stu-id="1077d-130">Remove a registered server</span></span>|[<span data-ttu-id="1077d-131">Supprimer un serveur inscrit &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-131">Remove a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](remove-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-132">Modifier l'inscription d'un serveur</span><span class="sxs-lookup"><span data-stu-id="1077d-132">Change a server's registration</span></span>|[<span data-ttu-id="1077d-133">Modifier l’inscription d’un serveur &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-133">Change a Server's Registration &#40;SQL Server Management Studio&#41;</span></span>](change-a-server-s-registration-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-134">Se connecter à un serveur inscrit</span><span class="sxs-lookup"><span data-stu-id="1077d-134">Connect to a registered server</span></span>|[<span data-ttu-id="1077d-135">Se connecter à un serveur inscrit &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-135">Connect to a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](connect-to-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-136">Se déconnecter d'un serveur inscrit</span><span class="sxs-lookup"><span data-stu-id="1077d-136">Disconnect from a registered server</span></span>|[<span data-ttu-id="1077d-137">Se déconnecter d’un serveur inscrit &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-137">Disconnect from a Registered Server &#40;SQL Server Management Studio&#41;</span></span>](disconnect-from-a-registered-server-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-138">Déplacer un serveur ou un groupe de serveurs inscrit</span><span class="sxs-lookup"><span data-stu-id="1077d-138">Move a registered server or server group</span></span>|[<span data-ttu-id="1077d-139">Déplacer un serveur inscrit ou un groupe de serveurs inscrits &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-139">Move a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](move-a-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="1077d-140">Modifier le nom d'un serveur ou d'un groupe de serveurs inscrit</span><span class="sxs-lookup"><span data-stu-id="1077d-140">Change the name of a registered server or server group</span></span>|[<span data-ttu-id="1077d-141">Modifier le nom d’un serveur ou d’un groupe de serveurs inscrits &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-141">Change the Name of a Registered Server or Registered Server Group &#40;SQL Server Management Studio&#41;</span></span>](change-the-name-of-registered-server-or-registered-server-group.md)|  
|<span data-ttu-id="1077d-142">Créer ou modifier un groupe de serveurs</span><span class="sxs-lookup"><span data-stu-id="1077d-142">Create or edit a server group</span></span>|[<span data-ttu-id="1077d-143">Créer ou modifier un groupe de serveurs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-143">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-or-edit-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-144">Supprimer un groupe de serveurs</span><span class="sxs-lookup"><span data-stu-id="1077d-144">Remove a server group</span></span>|[<span data-ttu-id="1077d-145">Supprimer un groupe de serveurs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-145">Remove a Server Group &#40;SQL Server Management Studio&#41;</span></span>](remove-a-server-group-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-146">Exporter des informations de serveur inscrit</span><span class="sxs-lookup"><span data-stu-id="1077d-146">Export registered server information</span></span>|[<span data-ttu-id="1077d-147">Exporter les informations des serveurs inscrits &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-147">Export Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](export-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-148">Importer des informations de serveur inscrit</span><span class="sxs-lookup"><span data-stu-id="1077d-148">Import registered server information</span></span>|[<span data-ttu-id="1077d-149">Importer les informations des serveurs inscrits &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-149">Import Registered Server Information &#40;SQL Server Management Studio&#41;</span></span>](import-registered-server-information-sql-server-management-studio.md)|  
|<span data-ttu-id="1077d-150">Créer un serveur de gestion centralisée et un groupe de serveurs</span><span class="sxs-lookup"><span data-stu-id="1077d-150">Create a Central Management Server and Server Group</span></span>|[<span data-ttu-id="1077d-151">Créer un serveur d’administration centralisée et un groupe de serveurs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-151">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](create-a-central-management-server-and-server-group.md)|  
|<span data-ttu-id="1077d-152">Exécuter des instructions sur plusieurs serveurs simultanément</span><span class="sxs-lookup"><span data-stu-id="1077d-152">Execute statements against multiple servers simultaneously</span></span>|[<span data-ttu-id="1077d-153">Exécuter des instructions simultanément sur plusieurs serveurs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1077d-153">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](execute-statements-against-multiple-servers-simultaneously.md)|  
  
## <a name="see-also"></a><span data-ttu-id="1077d-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1077d-154">See Also</span></span>  
 [<span data-ttu-id="1077d-155">Serveurs distants</span><span class="sxs-lookup"><span data-stu-id="1077d-155">Remote Servers</span></span>](../../database-engine/configure-windows/remote-servers.md)  
  
  
