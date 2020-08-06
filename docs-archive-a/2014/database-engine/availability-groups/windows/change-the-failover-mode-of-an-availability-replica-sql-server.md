---
title: Changer le mode de basculement d’un réplica de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover modes [SQL Server]
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], failover modes
- Availability Groups [SQL Server], configuring
ms.assetid: 619a826f-8e65-48eb-8c34-39497d238279
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d946440e2950192299c42652babb4082790dbd03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708679"
---
# <a name="change-the-failover-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="ca043-102">Modifier le mode de basculement d'un réplica de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ca043-102">Change the Failover Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="ca043-103">Cette rubrique explique comment modifier le mode de basculement d'un réplica de disponibilité dans un groupe de disponibilité AlwaysOn dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca043-103">This topic describes how to change the failover mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="ca043-104">Le mode de basculement est une propriété de réplica qui détermine le mode de basculement pour les réplicas qui s'exécutent en mode de disponibilité avec validation synchrone.</span><span class="sxs-lookup"><span data-stu-id="ca043-104">The failover mode is a replica property that determines the failover mode for replicas that run under synchronous-commit availability mode.</span></span> <span data-ttu-id="ca043-105">Pour plus d’informations, consultez [Basculement et modes de basculement &#40;groupes de disponibilité AlwaysOn&#41;](failover-and-failover-modes-always-on-availability-groups.md) et [Modes de disponibilité &#40;groupes de disponibilité AlwaysOn&#41;](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="ca043-105">For more information, see [Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) and [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ca043-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ca043-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="ca043-107">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="ca043-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="ca043-108">Cette tâche est prise en charge uniquement sur les réplicas principaux.</span><span class="sxs-lookup"><span data-stu-id="ca043-108">This task is supported only on primary replicas.</span></span> <span data-ttu-id="ca043-109">Vous devez être connecté à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ca043-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="ca043-110">Les instances de cluster de basculement (FCI) SQL Server ne prennent pas en charge le basculement automatique par les groupes de disponibilité. Par conséquent, tout réplica de disponibilité hébergé par une instance de cluster de basculement ne peut être configuré que pour un basculement manuel.</span><span class="sxs-lookup"><span data-stu-id="ca043-110">SQL Server Failover Cluster Instances (FCIs) do not support automatic failover by availability groups, so any availability replica that is hosted by an FCI can only be configured for manual failover.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ca043-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ca043-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ca043-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ca043-112">Permissions</span></span>  
 <span data-ttu-id="ca043-113">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ca043-113">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ca043-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ca043-114">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ca043-115">**Pour modifier le mode de basculement d'un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="ca043-115">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="ca043-116">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="ca043-116">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ca043-117">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="ca043-117">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="ca043-118">Cliquez sur le groupe de disponibilité dont vous souhaitez modifier le réplica.</span><span class="sxs-lookup"><span data-stu-id="ca043-118">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="ca043-119">Cliquez avec le bouton droit sur le réplica, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ca043-119">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="ca043-120">Dans la boîte de dialogue **Propriétés du réplica de disponibilité** , utilisez la liste déroulante **Mode de basculement** pour modifier le mode de basculement de ce réplica.</span><span class="sxs-lookup"><span data-stu-id="ca043-120">In the **Availability Replica Properties** dialog box, use the **Failover mode** drop list to change the failover mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ca043-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ca043-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="ca043-122">**Pour modifier le mode de basculement d'un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="ca043-122">**To change the failover mode of an availability replica**</span></span>  
  
1.  <span data-ttu-id="ca043-123">Connectez-vous à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ca043-123">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="ca043-124">Utilisez l'instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="ca043-124">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="ca043-125">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span><span class="sxs-lookup"><span data-stu-id="ca043-125">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="ca043-126">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="ca043-126">WITH ( {</span></span>  
  
     <span data-ttu-id="ca043-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="ca043-127">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="ca043-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="ca043-128">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="ca043-129">}  )</span><span class="sxs-lookup"><span data-stu-id="ca043-129">}  )</span></span>  
  
     <span data-ttu-id="ca043-130">where</span><span class="sxs-lookup"><span data-stu-id="ca043-130">where</span></span>  
  
    -   <span data-ttu-id="ca043-131">*nom_groupe* correspond au nom du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ca043-131">*group_name* is the name of the availability group.</span></span>  
  
    -   <span data-ttu-id="ca043-132">{ '*nom_système*[\\*nom_instance*]' | '*nom_réseau_FCI*[\\*nom_instance*]' }</span><span class="sxs-lookup"><span data-stu-id="ca043-132">{ '*system_name*[\\*instance_name*]' | '*FCI_network_name*[\\*instance_name*]' }</span></span>  
  
         <span data-ttu-id="ca043-133">Spécifie l'adresse de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge le réplica de disponibilité à modifier.</span><span class="sxs-lookup"><span data-stu-id="ca043-133">Specifies the address of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica to be altered.</span></span> <span data-ttu-id="ca043-134">Les composants de cette adresse sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ca043-134">The components of this address are as follows:</span></span>  
  
         <span data-ttu-id="ca043-135">*nom_système*</span><span class="sxs-lookup"><span data-stu-id="ca043-135">*system_name*</span></span>  
         <span data-ttu-id="ca043-136">Nom NetBIOS du système informatique sur lequel réside une instance de serveur autonome.</span><span class="sxs-lookup"><span data-stu-id="ca043-136">Is the NetBIOS name of the computer system on which a stand-alone server instance resides.</span></span>  
  
         <span data-ttu-id="ca043-137">*nom_réseau_FCI*</span><span class="sxs-lookup"><span data-stu-id="ca043-137">*FCI_network_name*</span></span>  
         <span data-ttu-id="ca043-138">Nom réseau utilisé pour accéder à un cluster de basculement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans lequel une instance de serveur cible est un serveur partenaire de basculement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (FCI).</span><span class="sxs-lookup"><span data-stu-id="ca043-138">Is the network name that is used to access a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster in which a target server instance is a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover partner (an FCI).</span></span>  
  
         <span data-ttu-id="ca043-139">*instance_name*</span><span class="sxs-lookup"><span data-stu-id="ca043-139">*instance_name*</span></span>  
         <span data-ttu-id="ca043-140">Nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge le réplica de disponibilité cible.</span><span class="sxs-lookup"><span data-stu-id="ca043-140">Is the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the target availability replica.</span></span> <span data-ttu-id="ca043-141">Pour une instance de serveur par défaut, *nom_instance* est facultatif.</span><span class="sxs-lookup"><span data-stu-id="ca043-141">For a default server instance, *instance_name* is optional.</span></span>  
  
     <span data-ttu-id="ca043-142">Pour plus d’informations sur ces paramètres, consultez [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ca043-142">For more information about these parameters, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="ca043-143">L’exemple suivant, entré sur le réplica principal du groupe de disponibilité *MyAG* , remplace le mode de basculement par le basculement automatique sur le réplica de disponibilité situé sur l’instance de serveur par défaut sur un ordinateur nommé *COMPUTER01*.</span><span class="sxs-lookup"><span data-stu-id="ca043-143">The following example, entered on the primary replica of the *MyAG* availability group, changes the failover mode to automatic failover on the availability replica that is located on the default server instance on a computer named *COMPUTER01*.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP MyAG MODIFY REPLICA ON 'COMPUTER01' WITH  
       (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="ca043-144">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca043-144">Using PowerShell</span></span>  

### <a name="to-change-the-failover-mode-of-an-availability-replica"></a><span data-ttu-id="ca043-145">Pour modifier le mode de basculement d'un réplica de disponibilité</span><span class="sxs-lookup"><span data-stu-id="ca043-145">To change the failover mode of an availability replica</span></span>
  
1.  <span data-ttu-id="ca043-146">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ca043-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="ca043-147">Utilisez l'applet de commande `Set-SqlAvailabilityReplica` avec le paramètre `FailoverMode`.</span><span class="sxs-lookup"><span data-stu-id="ca043-147">Use the `Set-SqlAvailabilityReplica` cmdlet with the `FailoverMode` parameter.</span></span> <span data-ttu-id="ca043-148">En définissant un réplica en mode de basculement automatique, vous devrez peut-être utiliser le paramètre `AvailabilityMode` pour modifier le réplica en mode de disponibilité avec validation synchrone.</span><span class="sxs-lookup"><span data-stu-id="ca043-148">When setting a replica to automatic failover, you might need to use the `AvailabilityMode` parameter to change the replica to synchronous-commit availability mode.</span></span>  
  
     <span data-ttu-id="ca043-149">Par exemple, la commande suivante modifie le réplica `MyReplica` dans le groupe de disponibilité `MyAg` afin qu'il utilise le mode de disponibilité avec validation synchrone et prenne en charge le basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="ca043-149">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\Replicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca043-150">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca043-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="ca043-151">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ca043-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="ca043-152">Pour configurer et utiliser le fournisseur de SQL Server PowerShell, consultez [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ca043-152">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ca043-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ca043-153">See Also</span></span>  
 [<span data-ttu-id="ca043-154">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca043-154">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
 <span data-ttu-id="ca043-155">[Modes de disponibilité &#40;groupes de disponibilité AlwaysOn&#41;](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="ca043-155">[Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="ca043-156">Basculement et modes de basculement &#40;groupes de disponibilité AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="ca043-156">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md) 
