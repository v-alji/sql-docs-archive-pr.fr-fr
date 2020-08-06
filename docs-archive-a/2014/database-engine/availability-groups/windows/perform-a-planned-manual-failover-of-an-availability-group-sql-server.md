---
title: Effectuer un basculement manuel planifié d'un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.manualfailover.f1
helpviewer_keywords:
- Availability Groups [SQL Server], failover
- failover [SQL Server], AlwaysOn Availability Groups
ms.assetid: 419f655d-3f9a-4e7d-90b9-f0bab47b3178
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c62942eaa8f4ab4472bca5c7123e5999eb069216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703304"
---
# <a name="perform-a-planned-manual-failover-of-an-availability-group-sql-server"></a><span data-ttu-id="a813c-102">Effectuer un basculement manuel planifié d'un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a813c-102">Perform a Planned Manual Failover of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="a813c-103">Cette rubrique explique comment effectuer un basculement manuel sans perte de données ( *basculement manuel planifié*) sur un groupe de disponibilité AlwaysOn à l’aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , de [!INCLUDE[tsql](../../../includes/tsql-md.md)] ou de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a813c-103">This topic describes how to perform a manual failover without data loss (a *planned manual failover*) on an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a813c-104">Un groupe de disponibilité bascule au niveau d'un réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a813c-104">An availability group fails over at the level of an availability replica.</span></span> <span data-ttu-id="a813c-105">Un basculement manuel planifié, à l'instar de tout basculement [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , entraîne la transition d'un réplica secondaire vers le rôle principal et, simultanément, celle de l'ancien réplica principal vers le rôle secondaire.</span><span class="sxs-lookup"><span data-stu-id="a813c-105">A planned manual failover, like any [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] failover, transitions a secondary replica to primary role and, concurrently, transitions the former primary replica to the secondary role.</span></span>  
  
 <span data-ttu-id="a813c-106">Un basculement manuel planifié, pris en charge uniquement lorsque le réplica principal et le réplica secondaire cible s'exécutent en mode de validation synchrone et sont actuellement synchronisés, conserve toutes les données dans les bases de données secondaires jointes au groupe de disponibilité sur le réplica secondaire cible.</span><span class="sxs-lookup"><span data-stu-id="a813c-106">A planned manual failover, which is supported only when the primary replica and the target secondary replica are running in synchronous-commit mode and are currently synchronized, preserves all the data in the secondary databases that are joined to the availability group on the target secondary replica.</span></span> <span data-ttu-id="a813c-107">Une fois la transition du réplica principal précédent vers le rôle secondaire terminé, ses bases de données deviennent les bases de données secondaires et démarrent la synchronisation avec les nouvelles bases de données primaires.</span><span class="sxs-lookup"><span data-stu-id="a813c-107">Once the former primary replica transitions to the secondary role, its databases become secondary databases and begin synchronizing with the new primary databases.</span></span> <span data-ttu-id="a813c-108">Une fois que toutes ont passé à l'état SYNCHRONIZED, le nouveau réplica secondaire devient éligible pour servir de cible d'un futur basculement manuel planifié.</span><span class="sxs-lookup"><span data-stu-id="a813c-108">After they all transition into the SYNCHRONIZED state, the new secondary replica becomes eligible to serve as the target of a future planned manual failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a813c-109">Si les réplicas principal et secondaire sont tous les deux configurés pour le mode de basculement automatique, une fois que le réplica secondaire est synchronisé, il peut également servir de cible à un basculement automatique.</span><span class="sxs-lookup"><span data-stu-id="a813c-109">If the secondary and primary replicas are both configured for automatic failover mode, once the secondary replica is synchronized, it can also serve as the target for an automatic failover.</span></span> <span data-ttu-id="a813c-110">Pour plus d’informations, consultez [Modes de disponibilité &#40;groupes de disponibilité AlwaysOn&#41;](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="a813c-110">For more information, see [Availability Modes &#40;AlwaysOn Availability Groups&#41;](availability-modes-always-on-availability-groups.md).</span></span>  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a813c-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a813c-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a813c-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="a813c-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a813c-113">Une commande de basculement retourne dès que le réplica secondaire cible a accepté la commande.</span><span class="sxs-lookup"><span data-stu-id="a813c-113">A failover command returns as soon as the target secondary replica has accepted the command.</span></span> <span data-ttu-id="a813c-114">Toutefois, la récupération de la base de données est asynchrone après que le basculement du groupe de disponibilité est terminé.</span><span class="sxs-lookup"><span data-stu-id="a813c-114">However, database recovery occurs asynchronously after the availability group has finished failing over.</span></span>  
  
-   <span data-ttu-id="a813c-115">La cohérence entre bases de données sur plusieurs bases de données dans le groupe de disponibilité n'est pas conservée lors d'un basculement.</span><span class="sxs-lookup"><span data-stu-id="a813c-115">Cross-database consistency across databases within the availability group is not maintained on failover.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a813c-116">Les transactions entre bases de données et les transactions distribuées ne sont pas prises en charge par [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a813c-116">Cross-database transactions and distributed transactions are not supported by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="a813c-117">Pour plus d’informations, consultez [Transactions entre bases de données non prises en charge pour la mise en miroir de bases de données ou les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="a813c-117">For more information, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="a813c-118">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="a813c-118">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="a813c-119">Le réplica secondaire cible et le réplica principal doivent tous les deux s'exécuter en mode de disponibilité avec validation synchrone.</span><span class="sxs-lookup"><span data-stu-id="a813c-119">The target secondary replica and the primary replica must both be running in synchronous-commit availability mode.</span></span>  
  
-   <span data-ttu-id="a813c-120">Le réplica secondaire cible doit être actuellement synchronisé avec le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="a813c-120">The target secondary replica must currently be synchronized with the primary replica.</span></span> <span data-ttu-id="a813c-121">Pour cela, il faut que toutes les bases de données secondaires sur ce réplica secondaire aient été jointes au groupe de disponibilité et soient synchronisées avec leurs bases de données primaires correspondantes (autrement dit, les bases de données secondaires locales doivent avoir l'état SYNCHRONIZED).</span><span class="sxs-lookup"><span data-stu-id="a813c-121">This requires that all the secondary databases on this secondary replica must have been joined to the availability group and be synchronized with their corresponding primary databases (that is, the local secondary databases must be SYNCHRONIZED).</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="a813c-122">Pour déterminer la disponibilité de basculement d'un réplica secondaire, interrogez la colonne **is_failover_ready** dans la vue de gestion dynamique [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) , ou regardez dans la colonne **Disponibilité de basculement** du [tableau de bord du groupe AlwaysOn](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="a813c-122">To determine the failover readiness of an secondary replica, query the **is_failover_ready** column in the [sys.dm_hadr_database_cluster_states](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-cluster-states-transact-sql) dynamic management view, or look at the **Failover Readiness** column of the [AlwaysOn Group Dashboard](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
-   <span data-ttu-id="a813c-123">Cette tâche est prise en charge uniquement sur le réplica secondaire cible.</span><span class="sxs-lookup"><span data-stu-id="a813c-123">This task is supported only on the target secondary replica.</span></span> <span data-ttu-id="a813c-124">Vous devez être connecté à l'instance de serveur qui héberge le réplica secondaire cible.</span><span class="sxs-lookup"><span data-stu-id="a813c-124">You must be connected to the server instance that hosts the target secondary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a813c-125">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a813c-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a813c-126">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a813c-126">Permissions</span></span>  
 <span data-ttu-id="a813c-127">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="a813c-127">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a813c-128">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a813c-128">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a813c-129">**Pour basculer manuellement un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="a813c-129">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="a813c-130">Dans l'Explorateur d'objets, connectez-vous à une instance de serveur qui héberge un réplica secondaire du groupe de disponibilité qui doit être basculé, et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="a813c-130">In Object Explorer, connect to a server instance that hosts a secondary replica of the availability group that needs to be failed over, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="a813c-131">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="a813c-131">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="a813c-132">Cliquez avec le bouton droit sur le groupe de disponibilité à basculer et sélectionnez la commande **Basculement** .</span><span class="sxs-lookup"><span data-stu-id="a813c-132">Right-click the availability group to be failed over, and select the **Failover** command.</span></span>  
  
4.  <span data-ttu-id="a813c-133">Cette commande lance l'Assistant Basculer le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a813c-133">This launches the Failover Availability Group Wizard.</span></span> <span data-ttu-id="a813c-134">Pour plus d’informations, consultez [Utiliser l’Assistant Basculer le groupe de disponibilité &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="a813c-134">For more information, see [Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a813c-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a813c-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="a813c-136">**Pour basculer manuellement un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="a813c-136">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="a813c-137">Connectez-vous à l'instance de serveur qui héberge le réplica secondaire cible.</span><span class="sxs-lookup"><span data-stu-id="a813c-137">Connect to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="a813c-138">Utilisez l'instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="a813c-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="a813c-139">ALTER AVAILABILITY GROUP *nom_groupe* FAILOVER</span><span class="sxs-lookup"><span data-stu-id="a813c-139">ALTER AVAILABILITY GROUP *group_name* FAILOVER</span></span>  
  
     <span data-ttu-id="a813c-140">où *nom_groupe* correspond au nom du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a813c-140">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="a813c-141">L’exemple suivant bascule manuellement le groupe de disponibilité *MyAg* vers le réplica secondaire connecté.</span><span class="sxs-lookup"><span data-stu-id="a813c-141">The following example manually fails over the *MyAg* availability group to the connected secondary replica.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAg FAILOVER;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a813c-142">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a813c-142">Using PowerShell</span></span>  
 <span data-ttu-id="a813c-143">**Pour basculer manuellement un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="a813c-143">**To manually fail over an availability group**</span></span>  
  
1.  <span data-ttu-id="a813c-144">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica secondaire cible.</span><span class="sxs-lookup"><span data-stu-id="a813c-144">Change directory (`cd`) to the server instance that hosts the target secondary replica.</span></span>  
  
2.  <span data-ttu-id="a813c-145">Utilisez l'applet de commande `Switch-SqlAvailabilityGroup`.</span><span class="sxs-lookup"><span data-stu-id="a813c-145">Use the `Switch-SqlAvailabilityGroup` cmdlet.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a813c-146">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a813c-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="a813c-147">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a813c-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
     <span data-ttu-id="a813c-148">L’exemple suivant effectue un basculement manuel du groupe de disponibilité *MyAg* vers le réplica secondaire dont le chemin est spécifié.</span><span class="sxs-lookup"><span data-stu-id="a813c-148">The following example manually fails over the *MyAg* availability group to the secondary replica with the specified path.</span></span>  
  
    ```powershell
    Switch-SqlAvailabilityGroup -Path SQLSERVER:\Sql\SecondaryServer\InstanceName\AvailabilityGroups\MyAg  
    ```  
  
 <span data-ttu-id="a813c-149">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a813c-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="a813c-150">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a813c-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="a813c-151">Obtenir de l'aide sur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a813c-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="follow-up-after-manually-failing-over-an-availability-group"></a><a name="FollowUp"></a> <span data-ttu-id="a813c-152">Suivi : Après avoir basculé manuellement un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="a813c-152">Follow Up: After Manually Failing Over an Availability Group</span></span>  
 <span data-ttu-id="a813c-153">Si vous avez effectué le basculement en dehors de [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] du groupe de disponibilité, ajustez les votes de quorum des nœuds WSFC afin de refléter la nouvelle configuration du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a813c-153">If you failed over outside of the [!INCLUDE[ssFosAuto](../../../includes/ssfosauto-md.md)] of the availability group, adjust the quorum votes of the WSFC nodes to reflect your new availability group configuration.</span></span> <span data-ttu-id="a813c-154">Pour plus d’informations, consultez [Clustering de basculement Windows Server &#40;WSFC&#41; avec SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a813c-154">For more information, see [Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server](../../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a813c-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a813c-155">See Also</span></span>  
 <span data-ttu-id="a813c-156">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a813c-156">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="a813c-157">[Basculement et modes de basculement &#40;groupes de disponibilité AlwaysOn&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="a813c-157">[Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;](failover-and-failover-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="a813c-158">Effectuer un basculement manuel forcé d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a813c-158">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
