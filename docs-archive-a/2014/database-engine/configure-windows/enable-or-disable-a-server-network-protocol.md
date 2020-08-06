---
title: Activer ou désactiver un protocole réseau de serveur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], disabling
- remote connections [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], disabling using Configuration Manager
- disabling network protocols, Configuration Manager
- network protocols [SQL Server], enabling
- enabling network protocols, Configuration Manager
- surface area configuration [SQL Server], connection protocols
- connections [SQL Server], enabling remote using Configuration Manager
ms.assetid: ec5ccb69-61c9-4576-8843-014b976fd46e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 737edae84ff284ed726ade69cb48e574b830611e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700212"
---
# <a name="enable-or-disable-a-server-network-protocol"></a><span data-ttu-id="c6633-102">Activer ou désactiver un protocole réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="c6633-102">Enable or Disable a Server Network Protocol</span></span>
  <span data-ttu-id="c6633-103">Tous les protocoles réseau sont installés par le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mais ils peuvent être activés ou non.</span><span class="sxs-lookup"><span data-stu-id="c6633-103">All network protocols are installed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, but may or may not be enabled.</span></span> <span data-ttu-id="c6633-104">Cette rubrique décrit comment activer ou désactiver un protocole réseau de serveur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide du gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6633-104">This topic describes how to enable or disable a server network protocol in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or PowerShell.</span></span> <span data-ttu-id="c6633-105">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] doit être arrêté et redémarré pour que la modification soit prise en compte.</span><span class="sxs-lookup"><span data-stu-id="c6633-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] must be stopped and restarted for the change to take effect.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c6633-106">Lors de l'installation de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] une connexion est ajoutée pour le groupe BUILTIN\Users.</span><span class="sxs-lookup"><span data-stu-id="c6633-106">During setup of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] a login is added for the BUILTIN\Users group.</span></span> <span data-ttu-id="c6633-107">Cela permet à tous les utilisateurs authentifiés sur l'ordinateur d'accéder à l'instance de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] en tant que membres du rôle public.</span><span class="sxs-lookup"><span data-stu-id="c6633-107">This allows all authenticated users of the computer to access the instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] as a member of the public role.</span></span> <span data-ttu-id="c6633-108">La connexion BUILTIN\Users peut être supprimée sans risque pour restreindre l'accès au [!INCLUDE[ssDE](../../includes/ssde-md.md)] aux utilisateurs de l'ordinateur qui disposent de connexions ou qui sont membres d'autres groupes Windows avec des connexions.</span><span class="sxs-lookup"><span data-stu-id="c6633-108">The BUILTIN\Users login can be safely removed to restrict [!INCLUDE[ssDE](../../includes/ssde-md.md)] access to computer users who have individual logins or are members of other Windows groups with logins.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="c6633-109">Les fournisseurs de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et [!INCLUDE[msCoName](../../includes/msconame-md.md)] pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prennent en charge TLS 1.0 et SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="c6633-109">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[msCoName](../../includes/msconame-md.md)] data providers for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support TLS 1.0 and SSL 3.0.</span></span> <span data-ttu-id="c6633-110">Si vous appliquez un autre protocole (comme TLS 1.1 ou TLS 1.2) en apportant des modifications dans la couche SChannel du système d’exploitation, vos connexions à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] risquent d’échouer.</span><span class="sxs-lookup"><span data-stu-id="c6633-110">If you enforce a different protocol (such as TLS 1.1 or TLS 1.2) by making changes in the operating system SChannel layer, your connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might fail.</span></span>  
  
 <span data-ttu-id="c6633-111">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c6633-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c6633-112">**Pour activer ou désactiver un protocole réseau de serveur à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="c6633-112">**To enable or disable a server network protocol using:**</span></span>  
  
     [<span data-ttu-id="c6633-113">Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6633-113">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c6633-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6633-114">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c6633-115">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6633-115">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-a-server-network-protocol"></a><span data-ttu-id="c6633-116">Pour activer un protocole réseau de serveur</span><span class="sxs-lookup"><span data-stu-id="c6633-116">To enable a server network protocol</span></span>  
  
1.  <span data-ttu-id="c6633-117">Dans le Gestionnaire de configuration du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , développez **Configuration du réseau SQL Server**dans le volet de la console.</span><span class="sxs-lookup"><span data-stu-id="c6633-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, expand **SQL Server  Network Configuration**.</span></span>  
  
2.  <span data-ttu-id="c6633-118">Dans le volet de console, cliquez sur **Protocoles pour** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="c6633-118">In the console pane, click **Protocols for** *\<instance name>*.</span></span>  
  
3.  <span data-ttu-id="c6633-119">Dans le volet d’informations, cliquez avec le bouton droit sur le protocole à modifier, puis cliquez sur **Activer** ou **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="c6633-119">In the details pane, right-click the protocol you want to change, and then click **Enable** or **Disable**.</span></span>  
  
4.  <span data-ttu-id="c6633-120">Dans le volet de la console, cliquez sur **Services SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c6633-120">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="c6633-121">Dans le volet d’informations, cliquez avec le bouton droit sur **SQL Server ( ***\<instance name>*** )**, puis cliquez sur **redémarrer**pour arrêter et redémarrer le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span><span class="sxs-lookup"><span data-stu-id="c6633-121">In the details pane, right-click **SQL Server (***\<instance name>***)**, and then click **Restart**, to stop and restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
##  <a name="using-sql-server-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="c6633-122">Utilisation de PowerShell SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6633-122">Using SQL Server PowerShell</span></span>  
  
#### <a name="to-enable-a-server-network-protocol-using-powershell"></a><span data-ttu-id="c6633-123">Pour activer un protocole réseau de serveur à l'aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6633-123">To Enable a Server Network Protocol Using PowerShell</span></span>  
  
1.  <span data-ttu-id="c6633-124">En utilisant des autorisations d'administrateur, ouvrez une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="c6633-124">Using administrator permissions open a command prompt.</span></span>  
  
2.  <span data-ttu-id="c6633-125">Démarrez Windows PowerShell 2.0 à partir de la barre des tâches, ou cliquez successivement sur Démarrer, Tous les Programmes, Accessoires, Windows PowerShell, puis Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6633-125">Start Windows PowerShell 2.0 from the taskbar, or click Start, then All Programs, then Accessories, then Windows PowerShell, then Windows PowerShell.</span></span>  
  
3.  <span data-ttu-id="c6633-126">Importez le module **sqlps** en entrant`Import-Module "sqlps"`</span><span class="sxs-lookup"><span data-stu-id="c6633-126">Import the **sqlps** module by entering `Import-Module "sqlps"`</span></span>  
  
4.  <span data-ttu-id="c6633-127">Exécutez les instructions suivantes pour activer les protocoles TCP et de canaux nommés.</span><span class="sxs-lookup"><span data-stu-id="c6633-127">Execute the following statements to enable both the TCP and named pipes protocols.</span></span> <span data-ttu-id="c6633-128">Remplacez `<computer_name>` par le nom de l'ordinateur qui exécute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6633-128">Replace `<computer_name>` with the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c6633-129">Si vous configurez une instance nommée, remplacez `MSSQLSERVER` par le nom de cette instance.</span><span class="sxs-lookup"><span data-stu-id="c6633-129">If you are configuring a named instance, replace `MSSQLSERVER` with the instance name.</span></span>  
  
     <span data-ttu-id="c6633-130">Pour désactiver des protocoles, affectez aux propriétés `IsEnabled` la valeur `$false`.</span><span class="sxs-lookup"><span data-stu-id="c6633-130">To disable protocols, set the `IsEnabled` properties to `$false`.</span></span>  
  
    ```powershell
    $smo = 'Microsoft.SqlServer.Management.Smo.'  
    $wmi = new-object ($smo + 'Wmi.ManagedComputer').  
  
    # List the object properties, including the instance names.  
    $Wmi  
  
    # Enable the TCP protocol on the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    $Tcp = $wmi.GetSmoObject($uri)  
    $Tcp.IsEnabled = $true  
    $Tcp.Alter()  
    $Tcp  
  
    # Enable the named pipes protocol for the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Np']"  
    $Np = $wmi.GetSmoObject($uri)  
    $Np.IsEnabled = $true  
    $Np.Alter()  
    $Np  
    ```  
  
#### <a name="to-configure-the-protocols-for-the-local-computer"></a><span data-ttu-id="c6633-131">Pour configurer les protocoles pour l'ordinateur local</span><span class="sxs-lookup"><span data-stu-id="c6633-131">To configure the protocols for the local computer</span></span>  
  
-   <span data-ttu-id="c6633-132">Lorsque le script est exécuté localement et configure l'ordinateur local, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell peut rendre le script plus souple en déterminant de façon dynamique le nom de l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="c6633-132">When the script is run locally and configures the local computer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell can make the script more flexible by dynamically determining the local computer name.</span></span> <span data-ttu-id="c6633-133">Pour récupérer le nom de l'ordinateur local, remplacez la ligne qui définit la variable `$uri` par la ligne suivante.</span><span class="sxs-lookup"><span data-stu-id="c6633-133">To retrieve the local computer name, replace the line setting the `$uri` variable with the following line.</span></span>  
  
    ```powershell
    $uri = "ManagedComputer[@Name='" + (Get-Item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    ```  
  
#### <a name="to-restart-the-database-engine-by-using-sql-server-powershell"></a><span data-ttu-id="c6633-134">Pour redémarrer le Moteur de base de données à l'aide de SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6633-134">To restart the Database Engine by using SQL Server PowerShell</span></span>  
  
-   <span data-ttu-id="c6633-135">Après avoir activé ou désactivé des protocoles, vous devez arrêter et redémarrer le [!INCLUDE[ssDE](../../includes/ssde-md.md)] pour que la modification entre en vigueur.</span><span class="sxs-lookup"><span data-stu-id="c6633-135">After you enable or disable protocols, you must stop and restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for the change to take effect.</span></span> <span data-ttu-id="c6633-136">Exécutez les instructions suivantes pour arrêter et démarrer l'instance par défaut à l'aide de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6633-136">Execute the following statements to stop and start the default instance by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span></span> <span data-ttu-id="c6633-137">Pour arrêter et démarrer une instance nommée, remplacez `'MSSQLSERVER'` par `'MSSQL$<instance_name>'`.</span><span class="sxs-lookup"><span data-stu-id="c6633-137">To stop and start a named instance replace `'MSSQLSERVER'` with `'MSSQL$<instance_name>'`.</span></span>  
  
    ```powershell
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\<computer_name>  
    $Wmi = (Get-Item .).ManagedComputer  
    # Get a reference to the default instance of the Database Engine.  
    $DfltInstance = $Wmi.Services['MSSQLSERVER']  
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Start the service again.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache and display the state of the service.  
    $DfltInstance.Refresh(); $DfltInstance  
    ```  
