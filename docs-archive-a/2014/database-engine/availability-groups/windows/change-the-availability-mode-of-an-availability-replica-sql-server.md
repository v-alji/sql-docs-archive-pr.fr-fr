---
title: Changer le mode de disponibilité d’un réplica de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], availability modes
ms.assetid: c4da8f25-fb1b-45a4-8bf2-195df6df634c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1636f3ea86e083e47276423b120dbc8d3744d387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708688"
---
# <a name="change-the-availability-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="93426-102">Modifier le mode de disponibilité d'un réplica de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="93426-102">Change the Availability Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="93426-103">Cette rubrique explique comment modifier le mode de disponibilité d'un réplica de disponibilité dans un groupe de disponibilité AlwaysOn dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93426-103">This topic describes how to change the availability mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="93426-104">Le mode de disponibilité est une propriété de réplica qui contrôle si le réplica effectue la validation de façon synchrone ou asynchrone.</span><span class="sxs-lookup"><span data-stu-id="93426-104">The availability mode is a replica property that controls the whether the replica commits asynchronously or synchronously.</span></span> <span data-ttu-id="93426-105">Le*mode de validation asynchrone* optimise les performances au détriment d’une haute disponibilité et prend en charge uniquement le basculement forcé manuel (avec une possible perte de données), qu’on appelle généralement *basculement forcé*.</span><span class="sxs-lookup"><span data-stu-id="93426-105">*Asynchronous-commit mode* maximizes performance at the expense of high availability and supports only forced manual failover (with possible data loss), typically called *forced failover*.</span></span> <span data-ttu-id="93426-106">Le*mode de validation synchrone* privilégie la haute disponibilité plutôt que les performances et, une fois que le réplica secondaire est synchronisé, prend en charge le basculement manuel et, éventuellement, le basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="93426-106">*Synchronous-commit mode* emphasizes high availability over performance and, once the secondary replica is synchronized, supports manual failover and, optionally, automatic failover.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="93426-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="93426-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="93426-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="93426-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="93426-109">Vous devez être connecté à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="93426-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="93426-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="93426-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="93426-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="93426-111">Permissions</span></span>  
 <span data-ttu-id="93426-112">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="93426-112">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="93426-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93426-113">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="93426-114">**Pour modifier le mode de disponibilité d'un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="93426-114">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="93426-115">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="93426-115">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="93426-116">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="93426-116">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="93426-117">Cliquez sur le groupe de disponibilité dont vous souhaitez modifier le réplica.</span><span class="sxs-lookup"><span data-stu-id="93426-117">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="93426-118">Cliquez avec le bouton droit sur le réplica, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="93426-118">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="93426-119">Dans la boîte de dialogue **Propriétés du réplica de disponibilité** , utilisez la liste déroulante **Mode de disponibilité** pour modifier le mode de disponibilité de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="93426-119">In the **Availability Replica Properties** dialog box, use the **Availability mode** drop list to change the availability mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="93426-120">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93426-120">Using Transact-SQL</span></span>  
 <span data-ttu-id="93426-121">**Pour modifier le mode de disponibilité d'un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="93426-121">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="93426-122">Connectez-vous à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="93426-122">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="93426-123">Utilisez l'instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="93426-123">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="93426-124">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span><span class="sxs-lookup"><span data-stu-id="93426-124">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="93426-125">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="93426-125">WITH ( {</span></span>  
  
     <span data-ttu-id="93426-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="93426-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="93426-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="93426-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="93426-128">} )</span><span class="sxs-lookup"><span data-stu-id="93426-128">} )</span></span>  
  
     <span data-ttu-id="93426-129">où *group_name* est le nom du groupe de disponibilité et *SERVER_NAME* est le nom de l’instance de serveur qui héberge le réplica à modifier.</span><span class="sxs-lookup"><span data-stu-id="93426-129">where *group_name* is the name of the availability group and *server_name* is the name of the server instance that hosts the replica to be modified.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93426-130">FAILOVER_MODE = AUTOMATIC n’est pris en charge que si vous spécifiez aussi AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span><span class="sxs-lookup"><span data-stu-id="93426-130">FAILOVER_MODE = AUTOMATIC is supported only if you also specify AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span></span>  
  
     <span data-ttu-id="93426-131">L'exemple suivant, écrit sur le réplica principal du groupe de disponibilité `AccountsAG` , modifie les modes de disponibilité et de basculement par une validation synchrone et un basculement automatique, pour le réplica hébergé par l'instance de serveur `INSTANCE09` .</span><span class="sxs-lookup"><span data-stu-id="93426-131">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the availability and failover modes to synchronous commit and automatic failover, respectively, for the replica hosted by the `INSTANCE09` server instance.</span></span>  
  
    ```  
  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (AVAILABILITY_MODE = SYNCHRONOUS_COMMIT);  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="93426-132">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="93426-132">Using PowerShell</span></span>

### <a name="to-change-the-availability-mode-of-an-availability-group"></a><span data-ttu-id="93426-133">Pour modifier le mode de disponibilité d'un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="93426-133">To change the availability mode of an availability group</span></span>
  
1.  <span data-ttu-id="93426-134">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="93426-134">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="93426-135">Utilisez l'applet de commande `Set-SqlAvailabilityReplica` avec le paramètre `AvailabilityMode` et, éventuellement, le paramètre `FailoverMode`.</span><span class="sxs-lookup"><span data-stu-id="93426-135">Use the `Set-SqlAvailabilityReplica` cmdlet with the `AvailabilityMode` parameter and, optionally, the `FailoverMode` parameter.</span></span>  
  
     <span data-ttu-id="93426-136">Par exemple, la commande suivante modifie le réplica `MyReplica` dans le groupe de disponibilité `MyAg` afin qu'il utilise le mode de disponibilité avec validation synchrone et prenne en charge le basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="93426-136">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `   
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="93426-137">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93426-137">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="93426-138">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="93426-138">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="93426-139">Pour configurer et utiliser le fournisseur de SQL Server PowerShell, consultez [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="93426-139">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="93426-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93426-140">See Also</span></span>  
 <span data-ttu-id="93426-141">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="93426-141">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="93426-142">[Modes de disponibilité (groupes de disponibilité AlwaysOn)](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="93426-142">[Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="93426-143">Basculement et modes de basculement &#40;groupes de disponibilité AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="93426-143">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md)  
