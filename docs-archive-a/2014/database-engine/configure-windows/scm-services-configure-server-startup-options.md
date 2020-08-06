---
title: Configurer les options de démarrage du serveur (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/07/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- parameters [SQL Server], startup options
- SQL Server, startup options
- single-user mode [SQL Server], starting in
- startup options [SQL Server]
- SQL Server services, setting startup options
ms.assetid: 7a94643c-6460-4baf-bb31-0cb99eaf970d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 405a96208c774a6326a69cf9826a14ca3552eae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697156"
---
# <a name="configure-server-startup-options-sql-server-configuration-manager"></a><span data-ttu-id="4fea9-102">Configurer les options de démarrage du serveur (Gestionnaire de configuration SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4fea9-102">Configure Server Startup Options (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="4fea9-103">Cette rubrique explique comment configurer les options de démarrage à utiliser à chaque démarrage du [!INCLUDE[ssDE](../../includes/ssde-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de Configuration Manager [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fea9-103">This topic describes how to configure startup options that will be used every time the [!INCLUDE[ssDE](../../includes/ssde-md.md)] starts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="4fea9-104">Pour obtenir la liste des options de démarrage, consultez [Options de démarrage du service moteur de base de données](database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="4fea9-104">For a list of startup options, see [Database Engine Service Startup Options](database-engine-service-startup-options.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4fea9-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4fea9-105">Before You Begin</span></span>  
  
### <a name="limitations-and-restrictions"></a><span data-ttu-id="4fea9-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4fea9-106">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4fea9-107">écrit les paramètres de démarrage dans le Registre.</span><span class="sxs-lookup"><span data-stu-id="4fea9-107">Configuration Manager writes startup parameters to the registry.</span></span> <span data-ttu-id="4fea9-108">Ils prennent effet lors du redémarrage suivant du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fea9-108">They take effect upon the next startup of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="4fea9-109">Dans un cluster, les modifications doivent être effectuées sur le serveur actif lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est en ligne, et elles s'appliqueront lorsque le [!INCLUDE[ssDE](../../includes/ssde-md.md)] redémarrera.</span><span class="sxs-lookup"><span data-stu-id="4fea9-109">On a cluster, changes must be made on the active server when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is online, and will take effect when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is restarted.</span></span> <span data-ttu-id="4fea9-110">La mise à jour dans le Registre des options de démarrage sur l'autre nœud interviendra lors du basculement suivant.</span><span class="sxs-lookup"><span data-stu-id="4fea9-110">The registry update of the startup options on the other node will occur upon the next failover.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4fea9-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4fea9-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4fea9-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4fea9-112">Permissions</span></span>  
 <span data-ttu-id="4fea9-113">La configuration des options de démarrage du serveur est limitée aux utilisateurs qui peuvent modifier les entrées associées dans le Registre.</span><span class="sxs-lookup"><span data-stu-id="4fea9-113">Configuring server startup options is restricted to users who can change the related entries in the registry.</span></span> <span data-ttu-id="4fea9-114">Notamment :</span><span class="sxs-lookup"><span data-stu-id="4fea9-114">This includes the following users.</span></span>  
  
-   <span data-ttu-id="4fea9-115">les membres du groupe Administrateurs local ;</span><span class="sxs-lookup"><span data-stu-id="4fea9-115">Members of the local administrators group.</span></span>  
  
-   <span data-ttu-id="4fea9-116">Le compte de domaine utilisé par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], si le [!INCLUDE[ssDE](../../includes/ssde-md.md)] est configuré pour l'exécution sous un compte de domaine.</span><span class="sxs-lookup"><span data-stu-id="4fea9-116">The domain account that is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is configured to run under a domain account.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4fea9-117">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="4fea9-117">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-configure-startup-options"></a><span data-ttu-id="4fea9-118">Pour configurer les options de démarrage</span><span class="sxs-lookup"><span data-stu-id="4fea9-118">To configure startup options</span></span>  
  
1.  <span data-ttu-id="4fea9-119">Dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , cliquez sur **Services SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4fea9-119">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, click **SQL Server Services**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4fea9-120">Étant donné que le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est un composant logiciel enfichable pour le programme [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console et non pas un programme autonome, le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n’apparaît pas en tant qu’application dans les versions plus récentes de Windows.</span><span class="sxs-lookup"><span data-stu-id="4fea9-120">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager does not appear as an application in newer versions of Windows.</span></span>  
    >   
    >  -   <span data-ttu-id="4fea9-121">**Windows 10**:</span><span class="sxs-lookup"><span data-stu-id="4fea9-121">**Windows 10**:</span></span>  
    >          <span data-ttu-id="4fea9-122">Pour ouvrir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, dans la **page de démarrage**, tapez SQLServerManager12. msc (pour [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="4fea9-122">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, on the **Start Page**, type SQLServerManager12.msc (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="4fea9-123">Pour les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , remplacez 12 par un nombre plus petit.</span><span class="sxs-lookup"><span data-stu-id="4fea9-123">For previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replace 12 with a smaller number.</span></span> <span data-ttu-id="4fea9-124">Le fait de cliquer sur SQLServerManager12.msc ouvre le Gestionnaire de Configuration.</span><span class="sxs-lookup"><span data-stu-id="4fea9-124">Clicking SQLServerManager12.msc opens the Configuration Manager.</span></span> <span data-ttu-id="4fea9-125">Pour épingler le Configuration Manager à la page de démarrage ou à la barre des tâches, cliquez avec le bouton droit sur SQLServerManager12. msc, puis cliquez sur **ouvrir l’emplacement du fichier**.</span><span class="sxs-lookup"><span data-stu-id="4fea9-125">To pin the Configuration Manager to the Start Page or Task Bar, right-click SQLServerManager12.msc, and then click **Open file location**.</span></span> <span data-ttu-id="4fea9-126">Dans l’Explorateur de fichiers Windows, cliquez avec le bouton droit sur SQLServerManager12. msc, puis cliquez sur **épingler pour démarrer** ou **Épingler à la barre des tâches**.</span><span class="sxs-lookup"><span data-stu-id="4fea9-126">In the Windows File Explorer, right-click SQLServerManager12.msc, and then click **Pin to Start** or **Pin to taskbar**.</span></span>  
    > -   <span data-ttu-id="4fea9-127">**Windows 8**:</span><span class="sxs-lookup"><span data-stu-id="4fea9-127">**Windows 8**:</span></span>  
    >          <span data-ttu-id="4fea9-128">Pour ouvrir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, dans l’icône **Rechercher** , sous **applications**, tapez **SQLServerManager \<version> . msc** , par exemple `SQLServerManager12.msc` , puis appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="4fea9-128">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager\<version>.msc** such as `SQLServerManager12.msc`, and then press **Enter**.</span></span>  
  
2.  <span data-ttu-id="4fea9-129">Dans le volet droit, cliquez avec le bouton droit sur **SQL Server (***<instance_name>***)**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4fea9-129">In the right pane, right-click **SQL Server (***<instance_name>***)**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="4fea9-130">Sous l'onglet **Paramètres de démarrage** , dans la zone **Spécifiez un paramètre de démarrage** , tapez le paramètre, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4fea9-130">On the **Startup Parameters** tab, in the **Specify a startup parameter** box, type the parameter, and then click **Add**.</span></span>  
  
     <span data-ttu-id="4fea9-131">Par exemple, pour démarrer en mode mono-utilisateur, tapez `-m` dans la zone **Spécifiez un paramètre de démarrage** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4fea9-131">For example, to start in single-user mode, type `-m` in the **Specify a startup parameter** box and then click **Add**.</span></span> <span data-ttu-id="4fea9-132">(Lorsque vous redémarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en mode mono-utilisateur, arrêtez l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fea9-132">(When you restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in single-user mode, stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="4fea9-133">Sinon, l’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut se connecter en premier et vous empêcher de vous connecter en tant que second utilisateur.)</span><span class="sxs-lookup"><span data-stu-id="4fea9-133">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent might connect first and prevent you from connecting as a second user.)</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="4fea9-134">Redémarrez le [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fea9-134">Restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="4fea9-135">Une fois que vous avez terminé d’utiliser le mode mono-utilisateur, dans la zone paramètres de démarrage, sélectionnez le `-m` paramètre dans la zone **paramètres existants** , puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="4fea9-135">After you are finished using single-user mode, in the Startup Parameters box, select the `-m` parameter in the **Existing Parameters** box, and then click **Remove**.</span></span> <span data-ttu-id="4fea9-136">Redémarrez le [!INCLUDE[ssDE](../../includes/ssde-md.md)] pour rétablir [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en mode multi-utilisateur habituel.</span><span class="sxs-lookup"><span data-stu-id="4fea9-136">Restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to restore [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to the typical multi-user mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fea9-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4fea9-137">See Also</span></span>  
 <span data-ttu-id="4fea9-138">[Démarrer SQL Server en mode mono-utilisateur](start-sql-server-in-single-user-mode.md) </span><span class="sxs-lookup"><span data-stu-id="4fea9-138">[Start SQL Server in Single-User Mode](start-sql-server-in-single-user-mode.md) </span></span>  
 <span data-ttu-id="4fea9-139">[Se connecter à SQL Server quand les administrateurs système n’y ont plus accès](connect-to-sql-server-when-system-administrators-are-locked-out.md) </span><span class="sxs-lookup"><span data-stu-id="4fea9-139">[Connect to SQL Server When System Administrators Are Locked Out](connect-to-sql-server-when-system-administrators-are-locked-out.md) </span></span>  
 [<span data-ttu-id="4fea9-140">Démarrer, arrêter ou suspendre le service SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="4fea9-140">Start, Stop, or Pause the SQL Server Agent Service</span></span>](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
