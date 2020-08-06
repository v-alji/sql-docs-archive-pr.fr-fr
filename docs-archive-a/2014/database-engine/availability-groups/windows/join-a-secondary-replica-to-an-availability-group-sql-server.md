---
title: Joindre un réplica secondaire à un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joinreplica.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
ms.assetid: e5bd2489-097a-490e-8ea1-34fe48378ad1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c38c2d59a46b15fc9a1dca77ae6a67e8e59e1b80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604717"
---
# <a name="join-a-secondary-replica-to-an-availability-group-sql-server"></a><span data-ttu-id="a29c9-102">Joindre un réplica secondaire à un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a29c9-102">Join a Secondary Replica to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="a29c9-103">Cette rubrique explique comment joindre un réplica secondaire à un groupe de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)], ou de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a29c9-103">This topic describes how to join a secondary replica to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a29c9-104">Une fois qu'un réplica secondaire a été ajouté à un groupe de disponibilité AlwaysOn, le réplica secondaire doit être joint au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a29c9-104">After a secondary replica is added to an AlwaysOn availability group, the secondary replica must be joined to the availability group.</span></span> <span data-ttu-id="a29c9-105">L'opération de jointure du réplica doit être effectuée sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="a29c9-105">The join-replica operation must be performed on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting the secondary replica.</span></span>  
  
-   <span data-ttu-id="a29c9-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="a29c9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a29c9-107">Composants requis</span><span class="sxs-lookup"><span data-stu-id="a29c9-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="a29c9-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a29c9-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a29c9-109">**Pour préparer une base de données secondaire, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="a29c9-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="a29c9-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a29c9-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a29c9-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a29c9-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="a29c9-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a29c9-112">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="a29c9-113">**Suivi :** [configurer des bases de données secondaires](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a29c9-113">**Follow Up:** [Configure Secondary Databases](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a29c9-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a29c9-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a29c9-115">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="a29c9-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="a29c9-116">Le réplica principal du groupe de disponibilité doit être actuellement en ligne.</span><span class="sxs-lookup"><span data-stu-id="a29c9-116">The primary replica of the availability group must currently be online.</span></span>  
  
-   <span data-ttu-id="a29c9-117">Vous devez être connecté à l'instance de serveur qui héberge un réplica secondaire qui n'a pas encore été joint au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a29c9-117">You must be connected to the server instance that hosts a secondary replica that has not yet have been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="a29c9-118">L'instance de serveur local doit être en mesure de se connecter au point de terminaison de mise en miroir de bases de données de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="a29c9-118">The local server instance must be able to connect to the database mirroring endpoint of the server instance that is hosting the primary replica.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a29c9-119">Si aucune condition préalable n'est satisfaite, l'opération de jointure échoue.</span><span class="sxs-lookup"><span data-stu-id="a29c9-119">If any prerequisite is not met, the join operation fails.</span></span> <span data-ttu-id="a29c9-120">Après l'échec d'une tentative de jointure, vous devrez peut-être vous connecter à l'instance de serveur qui héberge le réplica principal afin de supprimer et de rajouter le réplica secondaire avant de pouvoir le joindre au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a29c9-120">After a failed join attempt, you might need to connect to the server instance that hosts the primary replica to remove and re-add the secondary replica before you can join it to the availability group.</span></span> <span data-ttu-id="a29c9-121">Pour plus d’informations, consultez [Supprimer un réplica secondaire d’un groupe de disponibilité &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) et [Ajouter un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a29c9-121">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md) and [Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a29c9-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a29c9-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a29c9-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a29c9-123">Permissions</span></span>  
 <span data-ttu-id="a29c9-124">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="a29c9-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a29c9-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a29c9-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a29c9-126">**Pour joindre un réplica de disponibilité à un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="a29c9-126">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="a29c9-127">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica secondaire, puis cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="a29c9-127">In Object Explorer, connect to the server instance that hosts the secondary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="a29c9-128">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="a29c9-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="a29c9-129">Sélectionnez le groupe de disponibilité du réplica secondaire auquel vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="a29c9-129">Select the availability group of the secondary replica to which you are connected.</span></span>  
  
4.  <span data-ttu-id="a29c9-130">Cliquez avec le bouton droit sur le réplica secondaire et cliquez sur **Joindre au groupe de disponibilité**.</span><span class="sxs-lookup"><span data-stu-id="a29c9-130">Right-click the secondary replica, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="a29c9-131">Cette opération ouvre la boîte de dialogue **Joindre le réplica au groupe de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="a29c9-131">This opens the **Join Replica to Availability Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="a29c9-132">Pour joindre le réplica secondaire au groupe de disponibilité, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a29c9-132">To join the secondary replica to the availability group, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a29c9-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a29c9-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="a29c9-134">**Pour joindre un réplica de disponibilité à un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="a29c9-134">**To join an availability replica to an availability group**</span></span>  
  
1.  <span data-ttu-id="a29c9-135">Connectez-vous à l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="a29c9-135">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="a29c9-136">Utilisez l'instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="a29c9-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="a29c9-137">ALTER AVAILABILITY GROUP *nom_groupe* JOIN</span><span class="sxs-lookup"><span data-stu-id="a29c9-137">ALTER AVAILABILITY GROUP *group_name* JOIN</span></span>  
  
     <span data-ttu-id="a29c9-138">où *nom_groupe* correspond au nom du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a29c9-138">where *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="a29c9-139">L'exemple suivant joint le réplica secondaire au groupe de disponibilité `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="a29c9-139">The following example, joins the secondary replica to the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="a29c9-140">Pour consulter cette instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] utilisée en contexte, consultez [Créer un groupe de disponibilité &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a29c9-140">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="a29c9-141">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a29c9-141">Using PowerShell</span></span>  
 <span data-ttu-id="a29c9-142">**Pour joindre un réplica de disponibilité à un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="a29c9-142">**To join an availability replica to an availability group**</span></span>  
  
 <span data-ttu-id="a29c9-143">Dans le fournisseur PowerShell [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="a29c9-143">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="a29c9-144">Remplacez le répertoire (`cd`) par l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="a29c9-144">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="a29c9-145">Joignez le réplica secondaire au groupe de disponibilité en exécutant l’applet de commande **Join-SqlAvailabilityGroup** avec le nom du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a29c9-145">Join the secondary replica to the availability group by executing the **Join-SqlAvailabilityGroup** cmdlet with the name of the availability group.</span></span>  
  
     <span data-ttu-id="a29c9-146">Par exemple, la commande suivante joint un réplica secondaire hébergé par l'instance de serveur situé dans le chemin d'accès spécifié au groupe de disponibilité nommé `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="a29c9-146">For example, the following command joins a secondary replica hosted by the server instance located at the specified path to the availability group named `MyAg`.</span></span>  <span data-ttu-id="a29c9-147">Cette instance de serveur doit héberger un réplica secondaire dans ce groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a29c9-147">This server instance must host a secondary replica in this availability group.</span></span>  
  
    ```powershell
    Join-SqlAvailabilityGroup -Path SQLSERVER:\SQL\SecondaryServer\InstanceName -Name 'MyAg'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="a29c9-148">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a29c9-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="a29c9-149">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a29c9-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="a29c9-150">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a29c9-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="a29c9-151">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="a29c9-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-configure-secondary-databases"></a><a name="FollowUp"></a><span data-ttu-id="a29c9-152">Suivi : configurer des bases de données secondaires</span><span class="sxs-lookup"><span data-stu-id="a29c9-152">Follow Up: Configure Secondary Databases</span></span>  
 <span data-ttu-id="a29c9-153">Pour chaque base de données dans le groupe de disponibilité, vous avez besoin d'une base de données secondaire sur l'instance de serveur qui héberge le réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="a29c9-153">For every database in the availability group, you need a secondary database on the server instance that is hosting the secondary replica.</span></span> <span data-ttu-id="a29c9-154">Vous pouvez configurer des bases de données secondaires avant ou après avoir joint un réplica secondaire à un groupe de disponibilité, comme suit :</span><span class="sxs-lookup"><span data-stu-id="a29c9-154">You can configure secondary databases either before or after you join a secondary replica to an availability group, as follows:</span></span>  
  
1.  <span data-ttu-id="a29c9-155">Restaurez une base de données récente et les sauvegardes de fichier journal de chaque base de données primaire sur l'instance de serveur qui héberge le réplica secondaire, à l'aide de RESTORE WITH NORECOVERY pour chaque opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="a29c9-155">Restore recent database and log backups of each primary database onto the server instance that hosts the secondary replica, using RESTORE WITH NORECOVERY for every restore operation.</span></span> <span data-ttu-id="a29c9-156">Pour plus d’informations, consultez [Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a29c9-156">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="a29c9-157">Joignez chaque base de données secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="a29c9-157">Join each secondary database to the availability group.</span></span> <span data-ttu-id="a29c9-158">Pour plus d’informations, consultez [Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a29c9-158">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a29c9-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a29c9-159">See Also</span></span>  
 <span data-ttu-id="a29c9-160">[Création et configuration des groupes de disponibilité &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a29c9-160">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="a29c9-161">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a29c9-161">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="a29c9-162">Résoudre les problèmes de configuration de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;supprimé</span><span class="sxs-lookup"><span data-stu-id="a29c9-162">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
