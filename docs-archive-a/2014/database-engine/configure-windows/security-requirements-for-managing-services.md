---
title: Spécifications de sécurité pour la gestion des services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent service, security
- services [SQL Server], security
- SQL Server services, security
- WMI Providers [SQL Server]
- server configuration [SQL Server]
- security [SQL Server], services
- services [SQL Server], WMI
ms.assetid: 1874a317-ddb2-425d-98d9-b53e1be6fc6a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 46a777858c01bf3057093d34b29b9a2093668e97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706743"
---
# <a name="security-requirements-for-managing-services"></a><span data-ttu-id="21141-102">Spécifications de sécurité pour la gestion des services</span><span class="sxs-lookup"><span data-stu-id="21141-102">Security Requirements for Managing Services</span></span>
  <span data-ttu-id="21141-103">Pour gérer les services [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, utilisez le Gestionnaire de configuration SQL Server ou [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21141-103">To manage the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Services, use either SQL Server Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="21141-104">Pour gérer les services sur des serveurs clusters, utilisez l'Administrateur de cluster.</span><span class="sxs-lookup"><span data-stu-id="21141-104">Manage the services on clustered servers with the Cluster Administrator.</span></span>  
  
 <span data-ttu-id="21141-105">Pour gérer le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et définir les options de configuration du serveur, vous devez être membre du rôle serveur fixe **serveradmin** ou **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="21141-105">To manage the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service and set the server configuration options, you must be a member of the **serveradmin** fixed server role or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="21141-106">Les membres du groupe **Administrateurs** Windows peuvent démarrer et arrêter des services et configurer les options serveur fournies par Windows.</span><span class="sxs-lookup"><span data-stu-id="21141-106">Members of the Windows **Administrators** group can start and stop services and configure the server options that Windows provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21141-107">Pour bien fonctionner, les comptes utilisés pour les services doivent être configurés correctement au niveau du domaine, du système de fichiers et des autorisations de Registre.</span><span class="sxs-lookup"><span data-stu-id="21141-107">To operate properly, the accounts used for the services must be configured with the correct domain, file system, and registry permissions.</span></span> <span data-ttu-id="21141-108">Pour plus d’informations sur les autorisations requises, consultez [Configurer les comptes de service Windows et les autorisations](configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="21141-108">For information about the required permissions, see [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md).</span></span>  
  
## <a name="windows-management-instrumentation"></a><span data-ttu-id="21141-109">Windows Management Instrumentation</span><span class="sxs-lookup"><span data-stu-id="21141-109">Windows Management Instrumentation</span></span>  
 <span data-ttu-id="21141-110">Le Gestionnaire de configuration SQL Server et [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] utilisent Windows Management Instrumentation pour afficher et modifier une partie des propriétés de serveur.</span><span class="sxs-lookup"><span data-stu-id="21141-110">SQL Server Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] use Windows Management Instrumentation (WMI) to display and modify some of the server properties.</span></span> <span data-ttu-id="21141-111">Pour gérer les services et obtenir l'état des services, l'utilisateur doit posséder les droits nécessaires pour accéder à l'objet WMI.</span><span class="sxs-lookup"><span data-stu-id="21141-111">To manage services and obtain the status of the services, the user must have rights to access the WMI object.</span></span> <span data-ttu-id="21141-112">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], voici les pages de propriétés de serveur qui utilisent WMI :</span><span class="sxs-lookup"><span data-stu-id="21141-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the following server property pages use WMI:</span></span>  
  
-   <span data-ttu-id="21141-113">Démarrage automatique des services</span><span class="sxs-lookup"><span data-stu-id="21141-113">Autostart Services</span></span>  
  
-   <span data-ttu-id="21141-114">Paramètres de démarrage</span><span class="sxs-lookup"><span data-stu-id="21141-114">Startup Parameters</span></span>  
  
-   <span data-ttu-id="21141-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="21141-115">Security</span></span>  
  
-   <span data-ttu-id="21141-116">Paramètres divers du serveur</span><span class="sxs-lookup"><span data-stu-id="21141-116">Misc Server Settings</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="21141-117">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="21141-117">Related Tasks</span></span>  
 [<span data-ttu-id="21141-118">Configurer WMI pour afficher l'état du serveur dans les outils SQL Server</span><span class="sxs-lookup"><span data-stu-id="21141-118">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
## <a name="related-content"></a><span data-ttu-id="21141-119">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="21141-119">Related Content</span></span>  
 [<span data-ttu-id="21141-120">Fournisseur WMI pour les concepts de gestion de configuration</span><span class="sxs-lookup"><span data-stu-id="21141-120">WMI Provider for Configuration Management Concepts</span></span>](../../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
