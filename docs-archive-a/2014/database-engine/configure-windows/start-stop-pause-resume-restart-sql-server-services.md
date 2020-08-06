---
title: Démarrer, arrêter, suspendre, reprendre, redémarrer le service Moteur de base de données, SQL Server Agent ou SQL Server Browser | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, start and stop services
- stopping SQL Server Agent
- parameters [SQL Server], startup options
- SQL Server, startup options
- Database Engine [SQL Server], starting and stopping services
- pausing SQL Server
- PowerShell [SQL Server], starting and stopping services
- single-user mode [SQL Server], starting in
- SQL Server Management Studio [SQL Server], starting or stopping services
- stopping SQL Server Browser service
- starting SQL Server Agent
- default instances [SQL Server], starting and stopping
- SQL Server Agent, starting and stopping
- command prompt [SQL Server], starting and stopping SQL Server services
- continuing SQL Server
- starting SQL Server Database Engine
- net stop commands [SQL Server]
- command prompt [SQL Server], SQL Browser service
- Configuration Manager, start and stop services
- resuming SQL Server
- startup options [SQL Server]
- named instances [SQL Server], starting and stopping
- net start commands [SQL Server]
- SQL Server, starting and stopping
- stopping SQL Server
- starting SQL Server Browser service
- SQL Server Database Engine setting startup options
- administering SQL Server, starting and stopping services
- Management Studio [SQL Server], starting or stopping services
ms.assetid: 32660a02-e5a1-411a-9e57-7066ca459df6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f4b102c8fd81923d7386c8e556896e715311a07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706707"
---
# <a name="start-stop-pause-resume-restart-the-database-engine-sql-server-agent-or-sql-server-browser-service"></a><span data-ttu-id="b9966-102">Démarrer, arrêter, suspendre, reprendre, redémarrer le moteur de base de données, SQL Server Agent ou le service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="b9966-102">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>
  <span data-ttu-id="b9966-103">Cette rubrique explique comment démarrer, des commandes arrêter, des commandes interrompre, des commandes reprendre, des commandes ou redémarrer le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], des commandes l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , des commandes de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], des commandes **net** à partir d'une invite de commandes, de des commandes [!INCLUDE[tsql](../../includes/tsql-md.md)], des commandes or PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9966-103">This topic describes how to start, stop, pause, resume, or restart the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], **net** commands from a command prompt, [!INCLUDE[tsql](../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
-   <span data-ttu-id="b9966-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b9966-104">**Before you begin:**</span></span>  
  
    -   [<span data-ttu-id="b9966-105">Quels sont ces services ?</span><span class="sxs-lookup"><span data-stu-id="b9966-105">What are these services?</span></span>](#Services)  
  
    -   [<span data-ttu-id="b9966-106">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b9966-106">Additional Information</span></span>](#MoreInformation)  
  
    -   [<span data-ttu-id="b9966-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b9966-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b9966-108">**Instructions pour utiliser :**</span><span class="sxs-lookup"><span data-stu-id="b9966-108">**Instructions using:**</span></span>  
  
    -   [<span data-ttu-id="b9966-109">Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9966-109">SQL Server Configuration Manager</span></span>](#SSCMProcedure)  
  
    -   [<span data-ttu-id="b9966-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b9966-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   [<span data-ttu-id="b9966-111">commandes net à partir d'une fenêtre d'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="b9966-111">net Commands from a Command Prompt window</span></span>](#CommandPrompt)  
  
    -   [<span data-ttu-id="b9966-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9966-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   [<span data-ttu-id="b9966-113">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9966-113">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b9966-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b9966-114">Before You Begin</span></span>  
  
###  <a name="what-is-the-ssdenoversion-service-the-ssnoversion-agent-service-and-the-ssnoversion-browser-service"></a><a name="Services"></a> <span data-ttu-id="b9966-115">Qu'est-ce que le service [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent et le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser ?</span><span class="sxs-lookup"><span data-stu-id="b9966-115">What is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service?</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b9966-116">sont des programmes exécutables qui s'exécutent en tant que service Windows.</span><span class="sxs-lookup"><span data-stu-id="b9966-116">components are executable programs that run as a Windows service.</span></span> <span data-ttu-id="b9966-117">Les programmes qui s'exécutent en tant que service Windows peuvent continuer à fonctionner sans afficher d'activité sur l'écran de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b9966-117">Programs that run as a Windows service can continue to operate without displaying any activity on the computer screen.</span></span>  
  
 <span data-ttu-id="b9966-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)]services**</span><span class="sxs-lookup"><span data-stu-id="b9966-118">**[!INCLUDE[ssDE](../../includes/ssde-md.md)] service**</span></span>  
 <span data-ttu-id="b9966-119">Processus exécutable qui est le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9966-119">The executable process that is the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="b9966-120">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] peut être l'instance par défaut (avec une limite d'une par ordinateur), ou peut être l'une des nombreuses instances nommées du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9966-120">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be the default instance (limit one per computer), or can be one of many named instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="b9966-121">Utilisez le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour déterminer quelles instances du [!INCLUDE[ssDE](../../includes/ssde-md.md)] sont installées sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b9966-121">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to determine which instances of [!INCLUDE[ssDE](../../includes/ssde-md.md)] are installed on the computer.</span></span> <span data-ttu-id="b9966-122">L’instance par défaut (si vous l’installez) est indiquée sous la forme \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)\*\*.</span><span class="sxs-lookup"><span data-stu-id="b9966-122">The default instance (if you install it) is listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)**.</span></span> <span data-ttu-id="b9966-123">Les instances nommées (si vous les installez) sont répertoriées sous la forme \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)\*\*.</span><span class="sxs-lookup"><span data-stu-id="b9966-123">Named instances (if you install them) are listed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (<instance_name>)**.</span></span> <span data-ttu-id="b9966-124">Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express est installé en tant que \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLExpress)\*\*.</span><span class="sxs-lookup"><span data-stu-id="b9966-124">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express is installed as **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SQLEXPRESS)**.</span></span>  
  
 <span data-ttu-id="b9966-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Service agent**</span><span class="sxs-lookup"><span data-stu-id="b9966-125">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service**</span></span>  
 <span data-ttu-id="b9966-126">Service Windows qui exécute des tâches administratives planifiées, appelées travaux et alertes.</span><span class="sxs-lookup"><span data-stu-id="b9966-126">A Windows service that executes scheduled administrative tasks, which are called jobs and alerts.</span></span> <span data-ttu-id="b9966-127">Pour plus d’informations, consultez [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="b9966-127">For more information, see [SQL Server Agent](../../ssms/agent/sql-server-agent.md).</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b9966-128">Agent n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9966-128">Agent is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b9966-129">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="b9966-129">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="b9966-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Service Browser**</span><span class="sxs-lookup"><span data-stu-id="b9966-130">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service**</span></span>  
 <span data-ttu-id="b9966-131">Service Windows qui écoute les demandes entrantes des ressources [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et fournit aux clients des informations sur les instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installées sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b9966-131">A Windows service that listens for incoming requests for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides clients information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span> <span data-ttu-id="b9966-132">Une seule instance du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser est utilisée pour toutes les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installées sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b9966-132">A single instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is used for all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer.</span></span>  
  
###  <a name="additional-information"></a><a name="MoreInformation"></a><span data-ttu-id="b9966-133">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b9966-133">Additional Information</span></span>  
  
-   <span data-ttu-id="b9966-134">La suspension du service [!INCLUDE[ssDE](../../includes/ssde-md.md)] empêche les nouveaux utilisateurs de se connecter au [!INCLUDE[ssDE](../../includes/ssde-md.md)], mais les utilisateurs qui sont déjà connectés peuvent continuer à travailler jusqu'à ce que leurs connexions soient interrompues.</span><span class="sxs-lookup"><span data-stu-id="b9966-134">Pausing the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service prevents new users from connecting to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but users who are already connected can continue to work until their connections are broken.</span></span> <span data-ttu-id="b9966-135">Utilisez suspendre lorsque vous souhaitez attendre que les utilisateurs aient terminé leur travail avant d'arrêter le service.</span><span class="sxs-lookup"><span data-stu-id="b9966-135">Use pause when you want to wait for users to complete work before you stop the service.</span></span> <span data-ttu-id="b9966-136">Cela leur permet d'effectuer les transactions en cours.</span><span class="sxs-lookup"><span data-stu-id="b9966-136">This enables them to complete transactions that are in progress.</span></span> <span data-ttu-id="b9966-137">Reprendre permet au [!INCLUDE[ssDE](../../includes/ssde-md.md)] d'accepter à nouveau de nouvelles connexions.</span><span class="sxs-lookup"><span data-stu-id="b9966-137">Resume allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to accept new connections again.</span></span> <span data-ttu-id="b9966-138">Le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent ne peut pas être suspendu ou repris.</span><span class="sxs-lookup"><span data-stu-id="b9966-138">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service cannot be paused or resumed.</span></span>  
  
-   <span data-ttu-id="b9966-139">Le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] indiquent l'état actuel des services à l'aide des icônes suivantes.</span><span class="sxs-lookup"><span data-stu-id="b9966-139">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] display the current status of services by using the following icons.</span></span>  
  
     <span data-ttu-id="b9966-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="b9966-140">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager**</span></span>  
  
    -   <span data-ttu-id="b9966-141">Une flèche verte sur l'icône située à côté du nom du service indique que le service a démarré.</span><span class="sxs-lookup"><span data-stu-id="b9966-141">A green arrow on the icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="b9966-142">Un carré rouge sur l'icône située à côté du nom du service indique que le service s'est arrêté.</span><span class="sxs-lookup"><span data-stu-id="b9966-142">A red square on the icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="b9966-143">Deux lignes bleues verticales sur l'icône située à côté du nom du service indique que le service est suspendu.</span><span class="sxs-lookup"><span data-stu-id="b9966-143">Two vertical blue lines on the icon next to the service name indicates that the service is paused.</span></span>  
  
    -   <span data-ttu-id="b9966-144">Lors du redémarrage du [!INCLUDE[ssDE](../../includes/ssde-md.md)], un carré rouge indique que le service s'est arrêté, puis une flèche verte indique que le service a démarré.</span><span class="sxs-lookup"><span data-stu-id="b9966-144">When restarting the [!INCLUDE[ssDE](../../includes/ssde-md.md)], a red square will indicate that the service stopped, and then a green arrow will indicate that he service started successfully.</span></span>  
  
     **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
    -   <span data-ttu-id="b9966-145">Une flèche blanche sur l'icône de cercle vert située à côté du nom du service indique que le service a démarré.</span><span class="sxs-lookup"><span data-stu-id="b9966-145">A white arrow on a green circle icon next to the service name indicates that the service is started.</span></span>  
  
    -   <span data-ttu-id="b9966-146">Un carré blanc sur l'icône de cercle rouge située à côté du nom du service indique que le service s'est arrêté.</span><span class="sxs-lookup"><span data-stu-id="b9966-146">A white square on a red circle icon next to the service name indicates that the service is stopped.</span></span>  
  
    -   <span data-ttu-id="b9966-147">Deux lignes blanches verticales sur une icône de cercle bleue située à côté du nom du service indiquent que le service est suspendu.</span><span class="sxs-lookup"><span data-stu-id="b9966-147">Two vertical white lines on a blue circle icon next to the service name indicates that the service is paused.</span></span>  
  
-   <span data-ttu-id="b9966-148">Lorsque vous utilisez le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], seules les options possibles sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="b9966-148">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], only options that are possible will be available.</span></span> <span data-ttu-id="b9966-149">Par exemple, si le service a déjà démarré, **Démarrer** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="b9966-149">For example, if the service is already started, **Start** will be unavailable.</span></span>  
  
-   <span data-ttu-id="b9966-150">Lors de l'exécution sur un cluster, le service [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] est mieux géré à l'aide de l'Administrateur de cluster.</span><span class="sxs-lookup"><span data-stu-id="b9966-150">When running on a cluster, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] service is best managed by using Cluster Administrator.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b9966-151">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b9966-151">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b9966-152">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b9966-152">Permissions</span></span>  
 <span data-ttu-id="b9966-153">Par défaut, seuls les membres du groupe des administrateurs locaux peuvent démarrer, arrêter, interrompre, reprendre ou redémarrer un service.</span><span class="sxs-lookup"><span data-stu-id="b9966-153">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="b9966-154">Pour accorder aux non-administrateurs la capacité de gérer des services, consultez [Comment accorder aux utilisateurs des droits de gestion des services dans Windows Server 2003](https://support.microsoft.com/kb/325349).</span><span class="sxs-lookup"><span data-stu-id="b9966-154">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="b9966-155">(le processus est semblable sur d'autres versions de Windows).</span><span class="sxs-lookup"><span data-stu-id="b9966-155">(The process is similar on other versions of Windows.)</span></span>  
  
 <span data-ttu-id="b9966-156">L’arrêt du [!INCLUDE[ssDE](../../includes/ssde-md.md)] à l’aide de la [!INCLUDE[tsql](../../includes/tsql-md.md)] `SHUTDOWN` commande requiert l’appartenance aux rôles serveur fixes **sysadmin** ou **ServerAdmin** , et n’est pas transférable.</span><span class="sxs-lookup"><span data-stu-id="b9966-156">Stopping the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using the [!INCLUDE[tsql](../../includes/tsql-md.md)]`SHUTDOWN` command requires membership in the **sysadmin** or **serveradmin** fixed server roles, and is not transferable.</span></span>  
  
##  <a name="using-ssnoversion-configuration-manager"></a><a name="SSCMProcedure"></a><span data-ttu-id="b9966-157">Utilisation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b9966-157">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="b9966-158">Pour démarrer, arrêter, interrompre, reprendre, ou redémarrer une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9966-158">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="b9966-159">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b9966-159">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="b9966-160">Si la boîte de dialogue **Contrôle de compte d'utilisateur** s'affiche, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b9966-160">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="b9966-161">Dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , dans le volet gauche, cliquez sur **Services SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b9966-161">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="b9966-162">Dans le volet de résultats, cliquez avec le bouton droit sur **SQL Server (MSSQLServer)** ou sur une instance nommée, puis cliquez sur **Démarrer**, **Arrêter**, **Suspendre**, **Reprendre**ou **Redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="b9966-162">In the results pane, right-click **SQL Server (MSSQLServer)** or a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="b9966-163">Cliquez sur **OK** pour fermer le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9966-163">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9966-164">Pour démarrer une instance de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] avec les options de démarrage, consultez [Configurer les options de démarrage du serveur &#40;Gestionnaire de configuration SQL Server&#41;](scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="b9966-164">To start an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with startup options, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](scm-services-configure-server-startup-options.md).</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-ssnoversion-browser-or-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="b9966-165">Pour démarrer, arrêter, interrompre, reprendre, ou redémarrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser ou une instance de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9966-165">To start, stop, pause, resume, or restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser or an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="b9966-166">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b9966-166">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="b9966-167">Si la boîte de dialogue **Contrôle de compte d'utilisateur** s'affiche, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b9966-167">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="b9966-168">Dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , dans le volet gauche, cliquez sur **Services SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b9966-168">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, click **SQL Server Services**.</span></span>  
  
4.  <span data-ttu-id="b9966-169">Dans le volet des résultats, cliquez avec le bouton droit sur \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] navigateur**ou \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent (MSSQLSERVER)** ou sur \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent (<instance_name>)\*\* pour une instance nommée, puis cliquez sur **Démarrer**, **arrêter**, **suspendre**, **reprendre**ou **redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="b9966-169">In the results pane, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser**, or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (MSSQLServer)** or **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent (<instance_name>)** for a named instance, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
5.  <span data-ttu-id="b9966-170">Cliquez sur **OK** pour fermer le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9966-170">Click **OK** to close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9966-171">L’agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas être suspendu.</span><span class="sxs-lookup"><span data-stu-id="b9966-171">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent cannot be paused.</span></span>  
  
##  <a name="using-ssnoversion-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b9966-172">Utilisation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span><span class="sxs-lookup"><span data-stu-id="b9966-172">Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Studio</span></span>  
  
#### <a name="to-start-stop-pause-resume-or-restart-the-an-instance-of-the-ssdenoversion"></a><span data-ttu-id="b9966-173">Pour démarrer, arrêter, interrompre, reprendre, ou redémarrer une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9966-173">To start, stop, pause, resume, or restart the an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="b9966-174">Dans l’Explorateur d’objets, connectez-vous à l’instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)], cliquez avec le bouton droit sur l’instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] à démarrer, puis cliquez **Démarrer**, **Arrêter**, **Suspendre**, **Reprendre**ou **Redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="b9966-174">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
     <span data-ttu-id="b9966-175">Ou, dans Serveurs inscrits, cliquez avec le bouton droit sur l’instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] à démarrer, pointez sur **Contrôle du service**, puis cliquez sur **Démarrer**, **Arrêter**, **Suspendre**, **Reprendre**ou **Redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="b9966-175">Or, in Registered Servers, right-click the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] you want to start, point to **Service Control**, and then click **Start**, **Stop**, **Pause**, **Resume**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="b9966-176">Si la boîte de dialogue **Contrôle de compte d'utilisateur** s'affiche, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b9966-176">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="b9966-177">Lorsque vous y êtes invité, et si vous souhaitez exécuter l'action, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b9966-177">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
#### <a name="to-start-stop-or-restart-the-an-instance-of-the-ssnoversion-agent"></a><span data-ttu-id="b9966-178">Pour démarrer, arrêter ou redémarrer une instance de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9966-178">To start, stop, or restart the an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
1.  <span data-ttu-id="b9966-179">Dans l’Explorateur d’objets, connectez-vous à l’instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] , cliquez avec le bouton droit sur \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent\*\*, puis cliquez sur **Démarrer**, **arrêter**ou **redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="b9966-179">In Object Explorer, connect to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent**, and then click **Start**, **Stop**, or **Restart**.</span></span>  
  
2.  <span data-ttu-id="b9966-180">Si la boîte de dialogue **Contrôle de compte d'utilisateur** s'affiche, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b9966-180">If the **User Account Control** dialog box appears, click **Yes**.</span></span>  
  
3.  <span data-ttu-id="b9966-181">Lorsque vous y êtes invité, et si vous souhaitez exécuter l'action, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b9966-181">When prompted if you want to perform the action, click **Yes**.</span></span>  
  
##  <a name="from-the-command-prompt-window-using-net-commands"></a><a name="CommandPrompt"></a> <span data-ttu-id="b9966-182">À partir de la fenêtre d'invite de commandes en utilisant les commandes net</span><span class="sxs-lookup"><span data-stu-id="b9966-182">From the Command Prompt Window using net Commands</span></span>  
 <span data-ttu-id="b9966-183">Les services [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent être démarrés, arrêtés ou suspendus à l’aide des commandes [!INCLUDE[msCoName](../../includes/msconame-md.md)]**net** Windows.</span><span class="sxs-lookup"><span data-stu-id="b9966-183">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services can be started, stopped, or paused by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows **net** commands.</span></span>  
  
###  <a name="to-start-the-default-instance-of-the-ssde"></a><a name="dbDefault"></a> <span data-ttu-id="b9966-184">Pour démarrer l'instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9966-184">To start the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="b9966-185">À partir d'une invite de commandes, entrez l'une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9966-185">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="b9966-186">**net start "SQL Server (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="b9966-186">**net start "SQL Server (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="b9966-187">-ou-</span><span class="sxs-lookup"><span data-stu-id="b9966-187">-or-</span></span>  
  
     <span data-ttu-id="b9966-188">**net start MSSQLSERVER**</span><span class="sxs-lookup"><span data-stu-id="b9966-188">**net start MSSQLSERVER**</span></span>  
  
###  <a name="to-start-a-named-instance-of-the-ssde"></a><a name="dbNamed"></a> <span data-ttu-id="b9966-189">Pour démarrer une instance nommée du [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9966-189">To start a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
-   <span data-ttu-id="b9966-190">À partir d'une invite de commandes, entrez l'une des commandes suivantes.</span><span class="sxs-lookup"><span data-stu-id="b9966-190">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="b9966-191">Remplacez le *\<instancename>* par le nom de l'instance à gérer.</span><span class="sxs-lookup"><span data-stu-id="b9966-191">Replace *\<instancename>* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="b9966-192">**net start "SQL Server (** *nom_instance* **)"**</span><span class="sxs-lookup"><span data-stu-id="b9966-192">**net start "SQL Server (** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="b9966-193">-ou-</span><span class="sxs-lookup"><span data-stu-id="b9966-193">-or-</span></span>  
  
     <span data-ttu-id="b9966-194">**net start MSSQL$** *nom_instance*</span><span class="sxs-lookup"><span data-stu-id="b9966-194">**net start MSSQL$** *instancename*</span></span>  
  
###  <a name="to-start-the-ssde-with-startup-options"></a><a name="dbStartup"></a> <span data-ttu-id="b9966-195">Pour démarrer le [!INCLUDE[ssDE](../../includes/ssde-md.md)] avec des options de démarrage</span><span class="sxs-lookup"><span data-stu-id="b9966-195">To start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] with startup options</span></span>  
  
-   <span data-ttu-id="b9966-196">Ajoutez les options de démarrage à la fin de l’instruction **"SQL Server (MSSQLSERVER)"** , en les séparant par un espace.</span><span class="sxs-lookup"><span data-stu-id="b9966-196">Add startup options to the end of the **net start "SQL Server (MSSQLSERVER)"** statement, separated by a space.</span></span> <span data-ttu-id="b9966-197">Lors d’un démarrage avec l’instruction **net start**, les options de démarrage utilisent une barre oblique (/) au lieu d’un tiret (-).</span><span class="sxs-lookup"><span data-stu-id="b9966-197">When started using **net start**, startup options use a slash (/) instead of a hyphen (-).</span></span>  
  
     <span data-ttu-id="b9966-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span><span class="sxs-lookup"><span data-stu-id="b9966-198">**net start "SQL Server (MSSQLSERVER)" /f /m**</span></span>  
  
     <span data-ttu-id="b9966-199">-ou-</span><span class="sxs-lookup"><span data-stu-id="b9966-199">-or-</span></span>  
  
     <span data-ttu-id="b9966-200">**net start MSSQLSERVER /f /m**</span><span class="sxs-lookup"><span data-stu-id="b9966-200">**net start MSSQLSERVER /f /m**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b9966-201">Pour plus d’informations sur les options de démarrage, consultez [Options de démarrage du service moteur de base de données](database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="b9966-201">For more information about startup options, see [Database Engine Service Startup Options](database-engine-service-startup-options.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-the-default-instance-of-ssnoversion"></a><a name="agDefault"></a> <span data-ttu-id="b9966-202">Pour démarrer l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur l'instance par défaut de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9966-202">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="b9966-203">À partir d'une invite de commandes, entrez l'une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9966-203">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="b9966-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span><span class="sxs-lookup"><span data-stu-id="b9966-204">**net start "SQL Server Agent (MSSQLSERVER)"**</span></span>  
  
     <span data-ttu-id="b9966-205">-ou-</span><span class="sxs-lookup"><span data-stu-id="b9966-205">-or-</span></span>  
  
     <span data-ttu-id="b9966-206">**net start SQLSERVERAGENT**</span><span class="sxs-lookup"><span data-stu-id="b9966-206">**net start SQLSERVERAGENT**</span></span>  
  
###  <a name="to-start-the-ssnoversion-agent-on-a-named-instance-of-ssnoversion"></a><a name="agNamed"></a><span data-ttu-id="b9966-207">Pour démarrer l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent sur une instance nommée de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9966-207">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent on a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="b9966-208">À partir d'une invite de commandes, entrez l'une des commandes suivantes.</span><span class="sxs-lookup"><span data-stu-id="b9966-208">From a command prompt, enter one of the following commands.</span></span> <span data-ttu-id="b9966-209">Remplacez *nom_instance* par le nom de l’instance à gérer.</span><span class="sxs-lookup"><span data-stu-id="b9966-209">Replace *instancename* with the name of the instance you want to manage.</span></span>  
  
     <span data-ttu-id="b9966-210">**net start "SQL Server Agent (** *nom_instance* **)"**</span><span class="sxs-lookup"><span data-stu-id="b9966-210">**net start "SQL Server Agent(** *instancename* **)"**</span></span>  
  
     <span data-ttu-id="b9966-211">-ou-</span><span class="sxs-lookup"><span data-stu-id="b9966-211">-or-</span></span>  
  
     <span data-ttu-id="b9966-212">**net start SQLAgent$** *nom_instance*</span><span class="sxs-lookup"><span data-stu-id="b9966-212">**net start SQLAgent$** *instancename*</span></span>  
  
 <span data-ttu-id="b9966-213">Pour obtenir des informations sur la façon d’exécuter l’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en mode détaillé à des fins de résolution des problèmes, consultez [Application sqlagent90](../../tools/sqlagent90-application.md).</span><span class="sxs-lookup"><span data-stu-id="b9966-213">For information about how to run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in verbose mode for troubleshooting, see [sqlagent90 Application](../../tools/sqlagent90-application.md).</span></span>  
  
###  <a name="to-start-the-ssnoversion-browser"></a><a name="Browser"></a> <span data-ttu-id="b9966-214">Pour démarrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span><span class="sxs-lookup"><span data-stu-id="b9966-214">To start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span></span>  
  
-   <span data-ttu-id="b9966-215">À partir d'une invite de commandes, entrez l'une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b9966-215">From a command prompt, enter one of the following commands:</span></span>  
  
     <span data-ttu-id="b9966-216">**net start "SQL Server Browser"**</span><span class="sxs-lookup"><span data-stu-id="b9966-216">**net start "SQL Server Browser"**</span></span>  
  
     <span data-ttu-id="b9966-217">-ou-</span><span class="sxs-lookup"><span data-stu-id="b9966-217">-or-</span></span>  
  
     <span data-ttu-id="b9966-218">**net start SQLBrowser**</span><span class="sxs-lookup"><span data-stu-id="b9966-218">**net start SQLBrowser**</span></span>  
  
###  <a name="to-pause-or-stop-services-from-the-command-prompt-window"></a><a name="pauseStop"></a> <span data-ttu-id="b9966-219">Pour suspendre ou arrêter des services à partir de la fenêtre d'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="b9966-219">To pause or stop services from the Command Prompt window</span></span>  
  
-   <span data-ttu-id="b9966-220">Pour suspendre ou arrêter des services, modifiez les commandes des façons suivantes.</span><span class="sxs-lookup"><span data-stu-id="b9966-220">To pause or stop services modify the commands in the following ways.</span></span>  
  
    -   <span data-ttu-id="b9966-221">Pour suspendre un service, remplacez **net start** par **net pause**.</span><span class="sxs-lookup"><span data-stu-id="b9966-221">To pause a service, replace **net start** with **net pause**.</span></span>  
  
    -   <span data-ttu-id="b9966-222">Pour arrêter un service, remplacez **net start** par **net stop**.</span><span class="sxs-lookup"><span data-stu-id="b9966-222">To stop a service, replace **net start** with use **net stop**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b9966-223">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9966-223">Using Transact-SQL</span></span>  
 <span data-ttu-id="b9966-224">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] peut être arrêté à l'aide de l'instruction `SHUTDOWN`.</span><span class="sxs-lookup"><span data-stu-id="b9966-224">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can be stopped by using the `SHUTDOWN` statement.</span></span>  
  
#### <a name="to-stop-the-ssde-using-tsql"></a><span data-ttu-id="b9966-225">Pour arrêter le [!INCLUDE[ssDE](../../includes/ssde-md.md)] à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9966-225">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
-   <span data-ttu-id="b9966-226">Pour attendre la fin des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] et des procédures stockées en cours d'exécution, puis arrêter le [!INCLUDE[ssDE](../../includes/ssde-md.md)], exécutez l'instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="b9966-226">To wait for currently running [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and stored procedures to finish, and then stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)], execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN;   
    ```  
  
-   <span data-ttu-id="b9966-227">Pour arrêter le [!INCLUDE[ssDE](../../includes/ssde-md.md)] immédiatement, exécutez l'instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="b9966-227">To stop the [!INCLUDE[ssDE](../../includes/ssde-md.md)] immediately, execute the following statement.</span></span>  
  
    ```sql  
    SHUTDOWN WITH NOWAIT;   
    ```  
  
 <span data-ttu-id="b9966-228">Pour plus d’informations sur l' `SHUTDOWN` instruction, consultez [Shutdown &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b9966-228">For more information about the `SHUTDOWN` statement, see [SHUTDOWN &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/shutdown-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="b9966-229">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9966-229">Using PowerShell</span></span>  
  
#### <a name="to-start-and-stop-ssde-services"></a><span data-ttu-id="b9966-230">Pour démarrer et arrêter des services du [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9966-230">To start and stop [!INCLUDE[ssDE](../../includes/ssde-md.md)] services</span></span>  
  
1.  <span data-ttu-id="b9966-231">Dans une fenêtre d'invite de commandes, démarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell en exécutant la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="b9966-231">In a Command Prompt window, start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell by executing the following command.</span></span>  
  
    ```ms-dos  
    sqlps  
    ```  
  
2.  <span data-ttu-id="b9966-232">À l'invite de commandes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell, exécutez la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="b9966-232">At a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell command prompt, by executing the following command.</span></span> <span data-ttu-id="b9966-233">Remplacez `computername` par le nom de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b9966-233">Replace `computername` with the name of your computer.</span></span>  
  
    ```powershell  
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\computername  
    $Wmi = (Get-Item .).ManagedComputer
    ```  
  
3.  <span data-ttu-id="b9966-234">Identifiez le service que vous souhaitez arrêter ou démarrer.</span><span class="sxs-lookup"><span data-stu-id="b9966-234">Identify the service that you want to stop or start.</span></span> <span data-ttu-id="b9966-235">Choisissez l'une des lignes suivantes.</span><span class="sxs-lookup"><span data-stu-id="b9966-235">Pick one of the following lines.</span></span> <span data-ttu-id="b9966-236">Remplacez `instancename` par le nom de l'instance nommée.</span><span class="sxs-lookup"><span data-stu-id="b9966-236">Replace `instancename` with the name of the named instance.</span></span>  
  
    -   <span data-ttu-id="b9966-237">Pour obtenir une référence à l'instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9966-237">To get a reference to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQLSERVER']  
        ```  
  
    -   <span data-ttu-id="b9966-238">Pour obtenir une référence à une instance nommée du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9966-238">To get a reference to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['MSSQL$instancename']  
        ```  
  
    -   <span data-ttu-id="b9966-239">Pour obtenir une référence au service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sur l'instance par défaut du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9966-239">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLSERVERAGENT']  
        ```  
  
    -   <span data-ttu-id="b9966-240">Pour obtenir une référence au service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sur une instance nommée du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9966-240">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service on a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLAGENT$instancename']  
        ```  
  
    -   <span data-ttu-id="b9966-241">Pour obtenir une référence au service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="b9966-241">To get a reference to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
        ```powershell  
        $DfltInstance = $Wmi.Services['SQLBROWSER']  
        ```  
  
4.  <span data-ttu-id="b9966-242">Terminez l'exemple pour démarrer, puis arrêter le service sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b9966-242">Complete the example to start and then stop the selected service.</span></span>  
  
    ```powershell  
    # Display the state of the service.  
    $DfltInstance  
    # Start the service.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b9966-243">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9966-243">See Also</span></span>  
 <span data-ttu-id="b9966-244">[Démarrer SQL Server avec une configuration minimale](start-sql-server-with-minimal-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b9966-244">[Start SQL Server with Minimal Configuration](start-sql-server-with-minimal-configuration.md) </span></span>  
 [<span data-ttu-id="b9966-245">Fonctionnalités prises en charge par les éditions de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b9966-245">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
