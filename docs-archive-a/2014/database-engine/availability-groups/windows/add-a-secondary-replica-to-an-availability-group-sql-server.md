---
title: Ajouter un réplica secondaire à un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 6669dcce-85f9-495f-aadf-7f62cff4a9da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 498103a781641c72e166c6b11663f5248ae5ccfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601710"
---
# <a name="add-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="17c48-102">Ajouter un réplica secondaire à un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="17c48-102">Add a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="17c48-103">Cette rubrique explique comment ajouter un réplica secondaire à un groupe de disponibilité AlwaysOn existant à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17c48-103">This topic describes how to add a secondary replica to an existing AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="17c48-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="17c48-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="17c48-105">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="17c48-105">Prerequisites and Restrictions</span></span>](#PrerequisitesRestrictions)  
  
     [<span data-ttu-id="17c48-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="17c48-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="17c48-107">**Pour ajouter un réplica, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="17c48-107">**To add a replica, using:**</span></span>  
  
     [<span data-ttu-id="17c48-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17c48-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="17c48-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17c48-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="17c48-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="17c48-110">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="17c48-111">**Suivi :**  [Après avoir ajouté un réplica secondaire](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="17c48-111">**Follow Up:**  [After Adding a Secondary Replica](#FollowUp)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="17c48-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="17c48-112">Before You Begin</span></span>  
 <span data-ttu-id="17c48-113">Nous vous recommandons fortement de lire cette section avant d'essayer de créer votre premier groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="17c48-113">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
##  <a name="prerequisites-and-restrictions"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="17c48-114">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="17c48-114">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="17c48-115">Vous devez être connecté à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="17c48-115">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
 <span data-ttu-id="17c48-116">Pour plus d’informations, consultez [Conditions préalables requises, restrictions et recommandations pour les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="17c48-116">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="17c48-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="17c48-117">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="17c48-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="17c48-118">Permissions</span></span>  
 <span data-ttu-id="17c48-119">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="17c48-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="17c48-120">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17c48-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="17c48-121">**Pour ajouter un réplica**</span><span class="sxs-lookup"><span data-stu-id="17c48-121">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="17c48-122">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="17c48-122">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="17c48-123">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="17c48-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="17c48-124">Cliquez avec le bouton droit sur le groupe de disponibilité, puis sélectionnez l'une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="17c48-124">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="17c48-125">Sélectionnez la commande **Ajouter un réplica** pour lancer l'Assistant Ajouter un réplica au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="17c48-125">Select the **Add Replica** command to launch the Add Replica to Availability Group Wizard.</span></span> <span data-ttu-id="17c48-126">Pour plus d’informations, consultez [Utiliser l’Assistant Ajouter un réplica au groupe de disponibilité &#40;SQL Server Management Studio&#41;](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="17c48-126">For more information, see [Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md).</span></span>  
  
    -   <span data-ttu-id="17c48-127">Vous pouvez également sélectionner la commande **Propriétés** pour ouvrir la boîte de dialogue **Propriétés du groupe de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="17c48-127">Alternatively, select the **Properties** command to open the **Availability Group Properties** dialog box.</span></span> <span data-ttu-id="17c48-128">Les étapes permettant d'ajouter un réplica dans cette boîte de dialogue sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="17c48-128">The steps for adding a replica in this dialog box are as follows:</span></span>  
  
        1.  <span data-ttu-id="17c48-129">Dans le volet **Réplicas de disponibilité** de la boîte de dialogue, cliquez sur le bouton **Ajouter** .</span><span class="sxs-lookup"><span data-stu-id="17c48-129">In the **Availability Replicas** pane of the dialog box, click the **Add** button.</span></span> <span data-ttu-id="17c48-130">Cela permet de créer et de sélectionner une entrée de réplica dans laquelle le champ vide d'instance de serveur est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="17c48-130">This creates and selects a replica entry in which the blank Server Instance field is selected.</span></span>  
  
        2.  <span data-ttu-id="17c48-131">Entrez le nom d'une instance de serveur qui satisfait aux conditions préalables requises pour héberger un réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="17c48-131">Enter the name of a server instance that meets the prerequisites for hosting an availability replica.</span></span>  
  
         <span data-ttu-id="17c48-132">Pour ajouter des réplicas supplémentaires, répétez les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="17c48-132">To add an additional replicas, repeat the preceding steps.</span></span> <span data-ttu-id="17c48-133">Lorsque vous avez terminé de spécifier des réplicas, cliquez sur **OK** pour terminer l'opération.</span><span class="sxs-lookup"><span data-stu-id="17c48-133">When you are done specifying replicas, click **OK** to complete the operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="17c48-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17c48-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="17c48-135">**Pour ajouter un réplica**</span><span class="sxs-lookup"><span data-stu-id="17c48-135">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="17c48-136">Connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="17c48-136">Connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="17c48-137">Ajoutez le nouveau réplica secondaire au groupe de disponibilité en utilisant la clause ADD REPLICA ON de l'instruction ALTER AVAILABILITY GROUP.</span><span class="sxs-lookup"><span data-stu-id="17c48-137">Add the new secondary replica to the availability group by using the ADD REPLICA ON clause of the ALTER AVAILABILITY GROUP statement.</span></span> <span data-ttu-id="17c48-138">Les options ENDPOINT_URL, AVAILABILITY_MODE et FAILOVER_MODE sont requises dans une clause ADD REPLICA ON.</span><span class="sxs-lookup"><span data-stu-id="17c48-138">The ENDPOINT_URL, AVAILABILITY_MODE, and FAILOVER_MODE options are required in an ADD REPLICA ON clause.</span></span> <span data-ttu-id="17c48-139">Les autres options de réplica, BACKUP_PRIORITY, SECONDARY_ROLE, PRIMARY_ROLE et SESSION_TIMEOUT, sont facultatives.</span><span class="sxs-lookup"><span data-stu-id="17c48-139">The other replica options- BACKUP_PRIORITY, SECONDARY_ROLE, PRIMARY_ROLE, and SESSION_TIMEOUT-are optional.</span></span> <span data-ttu-id="17c48-140">Pour plus d’informations, consultez [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="17c48-140">For more information, see [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
     <span data-ttu-id="17c48-141">Par exemple, l'instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] suivante crée un réplica dans un groupe de disponibilité nommé `MyAG` sur l'instance de serveur par défaut hébergée par `COMPUTER04`, dont l'URL du point de terminaison est `TCP://COMPUTER04.Adventure-Works.com:5022'`.</span><span class="sxs-lookup"><span data-stu-id="17c48-141">For example, the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement creates a new replica to an availability group named `MyAG` on the default server instance hosted by `COMPUTER04`, whose endpoint URL is `TCP://COMPUTER04.Adventure-Works.com:5022'`.</span></span> <span data-ttu-id="17c48-142">Ce réplica prend en charge le basculement manuel et le mode de disponibilité avec validation synchrone.</span><span class="sxs-lookup"><span data-stu-id="17c48-142">This replica supports manual failover and asynchronous-commit availability mode.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG ADD REPLICA ON 'COMPUTER04'   
       WITH (  
             ENDPOINT_URL = 'TCP://COMPUTER04.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="17c48-143">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="17c48-143">Using PowerShell</span></span>  
 <span data-ttu-id="17c48-144">**Pour ajouter un réplica**</span><span class="sxs-lookup"><span data-stu-id="17c48-144">**To add a replica**</span></span>  
  
1.  <span data-ttu-id="17c48-145">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="17c48-145">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="17c48-146">Utilisez l’applet de commande **New-SqlAvailabilityReplica** .</span><span class="sxs-lookup"><span data-stu-id="17c48-146">Use the **New-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="17c48-147">Par exemple, la commande suivante ajoute un réplica de disponibilité à un groupe de disponibilité existant nommé `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="17c48-147">For example, the following command adds an availability replica to an existing availability group named `MyAg`.</span></span> <span data-ttu-id="17c48-148">Ce réplica prend en charge le basculement manuel et le mode de disponibilité avec validation synchrone.</span><span class="sxs-lookup"><span data-stu-id="17c48-148">This replica supports manual failover and asynchronous-commit availability mode.</span></span> <span data-ttu-id="17c48-149">Avec le rôle secondaire, ce réplica prendra en charge les connexions d'accès en lecture. Vous pourrez ainsi décharger le traitement en lecture sur ce réplica.</span><span class="sxs-lookup"><span data-stu-id="17c48-149">In the secondary role, this replica will support read access connections, allowing you to offload read-only processing to this replica.</span></span>  
  
    ```powershell
    $agPath = "SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
    $endpointURL = "TCP://PrimaryServerName.domain.com:5022"  
    $failoverMode = "Manual"  
    $availabilityMode = "AsynchronousCommit"  
    $secondaryReadMode = "AllowAllConnections"  
  
    New-SqlAvailabilityReplica -Name SecondaryServer\Instance `   
    -EndpointUrl $endpointURL `   
    -FailoverMode $failoverMode `   
    -AvailabilityMode $availabilityMode `   
    -ConnectionModeInSecondaryRole $secondaryReadMode `   
    -Path $agPath  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="17c48-150">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17c48-150">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="17c48-151">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="17c48-151">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="17c48-152">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="17c48-152">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="17c48-153">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="17c48-153">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-adding-a-secondary-replica"></a><a name="FollowUp"></a> <span data-ttu-id="17c48-154">Suivi : Après avoir ajouté un réplica secondaire</span><span class="sxs-lookup"><span data-stu-id="17c48-154">Follow Up: After Adding a Secondary Replica</span></span>  
 <span data-ttu-id="17c48-155">Pour ajouter un réplica pour un groupe de disponibilité existant, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="17c48-155">To add a replica for an existing availability group, you must perform the following steps:</span></span>  
  
1.  <span data-ttu-id="17c48-156">Connectez-vous à l'instance de serveur qui va héberger le nouveau réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="17c48-156">Connect to the server instance that is going to host the new secondary replica.</span></span>  
  
2.  <span data-ttu-id="17c48-157">Joignez le nouveau réplica secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="17c48-157">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="17c48-158">Pour plus d’informations, consultez [Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="17c48-158">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="17c48-159">Pour chaque base de données du groupe de disponibilité, créez une base de données secondaire sur l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="17c48-159">For each database in the availability group, create a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="17c48-160">Pour plus d’informations, consultez [Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="17c48-160">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="17c48-161">Joignez chacune des nouvelles bases de données secondaires au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="17c48-161">Join each of the new secondary databases to the availability group.</span></span> <span data-ttu-id="17c48-162">Pour plus d’informations, consultez [Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="17c48-162">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="17c48-163">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="17c48-163">Related Tasks</span></span>  
 <span data-ttu-id="17c48-164">**Pour gérer un réplica de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="17c48-164">**To manage an availability replica**</span></span>  
  
-   [<span data-ttu-id="17c48-165">Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="17c48-165">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="17c48-166">Supprimer un réplica secondaire d’un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="17c48-166">Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;</span></span>](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="17c48-167">Configurer l’accès en lecture seule sur un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="17c48-167">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="17c48-168">Modifier le mode de disponibilité d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="17c48-168">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="17c48-169">Modifier le mode de basculement d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="17c48-169">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="17c48-170">Modifier le délai d’expiration de session pour un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="17c48-170">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="17c48-171">Modifier le délai d’expiration de session pour un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="17c48-171">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="17c48-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17c48-172">See Also</span></span>  
 <span data-ttu-id="17c48-173">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17c48-173">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="17c48-174">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="17c48-174">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="17c48-175">[Création et configuration des groupes de disponibilité &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="17c48-175">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="17c48-176">[Utilisez le tableau de bord AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="17c48-176">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="17c48-177">Surveiller des groupes de disponibilité &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17c48-177">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
  
  
