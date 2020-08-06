---
title: Ajouter une base de données à un groupe de disponibilité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server], in availability group
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: 2a54eef8-9e8e-4e04-909c-6970112d55cc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0907cf711cac65ad77a8948841d92705fdc1eac9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601129"
---
# <a name="add-a-database-to-an-availability-group-sql-server"></a><span data-ttu-id="e2bab-102">Ajouter une base de données à un groupe de disponibilité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e2bab-102">Add a Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="e2bab-103">Cette rubrique explique comment ajouter une base de données à un groupe de disponibilité AlwaysOn à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2bab-103">This topic describes how to add a database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="e2bab-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="e2bab-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e2bab-105">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="e2bab-105">Prerequisites and Restrictions</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="e2bab-106">autorisations</span><span class="sxs-lookup"><span data-stu-id="e2bab-106">Permissions</span></span>](#Permissions)  
  
-   <span data-ttu-id="e2bab-107">**Pour ajouter une base de données à un groupe de disponibilité, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="e2bab-107">**To add a database to an availability group, using:**</span></span>  
  
     [<span data-ttu-id="e2bab-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e2bab-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e2bab-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2bab-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="e2bab-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2bab-110">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e2bab-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e2bab-111">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="e2bab-112">Conditions préalables requises et restrictions</span><span class="sxs-lookup"><span data-stu-id="e2bab-112">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="e2bab-113">Vous devez être connecté à l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="e2bab-113">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="e2bab-114">La base de données doit résider sur l'instance de serveur qui héberge le réplica principal et se conformer aux conditions préalables requises et aux restrictions applicables aux bases de données de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="e2bab-114">The database must reside on the server instance that hosts the primary replica and comply with the prerequisites and restrictions for availability databases.</span></span> <span data-ttu-id="e2bab-115">Pour plus d’informations, consultez [Conditions préalables requises, restrictions et recommandations pour les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="e2bab-115">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e2bab-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e2bab-116">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e2bab-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="e2bab-117">Permissions</span></span>  
 <span data-ttu-id="e2bab-118">Requiert l'autorisation ALTER AVAILABILITY GROUP sur le groupe de disponibilité, l'autorisation CONTROL AVAILABILITY GROUP, l'autorisation ALTER ANY AVAILABILITY GROUP ou l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="e2bab-118">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e2bab-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e2bab-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="e2bab-120">**Pour ajouter une base de données à un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="e2bab-120">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="e2bab-121">Dans l'Explorateur d'objets, connectez-vous à l'instance de serveur qui héberge le réplica principal et développez l'arborescence du serveur.</span><span class="sxs-lookup"><span data-stu-id="e2bab-121">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="e2bab-122">Développez le nœud **Haute disponibilité AlwaysOn** et le nœud **Groupes de disponibilité** .</span><span class="sxs-lookup"><span data-stu-id="e2bab-122">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="e2bab-123">Cliquez avec le bouton droit sur le groupe de disponibilité, puis sélectionnez l'une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2bab-123">Right-click the availability group, and select one of the following commands:</span></span>  
  
    -   <span data-ttu-id="e2bab-124">Pour lancer l'Assistant Ajouter une base de données au groupe de disponibilité, sélectionnez la commande **Ajouter une base de données** .</span><span class="sxs-lookup"><span data-stu-id="e2bab-124">To launch the Add Database to Availability Group Wizard, select the **Add Database** command.</span></span> <span data-ttu-id="e2bab-125">Pour plus d’informations, consultez [Utiliser l’Assistant Ajouter une base de données au groupe de disponibilité &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="e2bab-125">For more information, see [Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md).</span></span>  
  
    -   <span data-ttu-id="e2bab-126">Pour ajouter une ou plusieurs bases de données en les spécifiant dans la boîte de dialogue **Propriétés du groupe de disponibilité** , sélectionnez la commande **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="e2bab-126">To add one or more databases by specifying them in the **Availability Group Properties** dialog box, select the **Properties** command.</span></span> <span data-ttu-id="e2bab-127">Les étapes d'ajout d'une base de données sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2bab-127">The steps for adding a database are as follows:</span></span>  
  
        1.  <span data-ttu-id="e2bab-128">Dans le volet **Bases de données de disponibilité** , cliquez sur le bouton **Ajouter** .</span><span class="sxs-lookup"><span data-stu-id="e2bab-128">In the **Availability Databases** pane, click the **Add** button.</span></span> <span data-ttu-id="e2bab-129">Cela permet de créer et de sélectionner un champ de base de données vide.</span><span class="sxs-lookup"><span data-stu-id="e2bab-129">This creates and selects a blank database field.</span></span>  
  
        2.  <span data-ttu-id="e2bab-130">Entrez le nom d'une base de données répondant aux exigences requises applicables aux bases de données de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="e2bab-130">Enter the name of a database that meets the availability-databases prerequisites.</span></span>  
  
         <span data-ttu-id="e2bab-131">Pour ajouter une autre base de données, répétez les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="e2bab-131">To add another database, repeat the preceding steps.</span></span> <span data-ttu-id="e2bab-132">Lorsque vous avez terminé la spécification des bases de données, cliquez sur **OK** pour terminer l'opération.</span><span class="sxs-lookup"><span data-stu-id="e2bab-132">When you are done specifying databases, click **OK** to complete the operation.</span></span>  
  
         <span data-ttu-id="e2bab-133">Après avoir utilisé la boîte de dialogue **Propriétés du groupe de disponibilité** pour ajouter une base de données à un groupe de disponibilité, vous devez configurer la base de données secondaire correspondante sur chaque instance de serveur qui héberge un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="e2bab-133">After you use the **Availability Group Properties** dialog box to add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="e2bab-134">Pour plus d’informations, consultez [Démarrer un mouvement de données sur une base de données secondaire AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e2bab-134">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e2bab-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2bab-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="e2bab-136">**Pour ajouter une base de données à un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="e2bab-136">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="e2bab-137">Connectez-vous à l'instance de serveur qui héberge l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="e2bab-137">Connect to the server instance that hosts the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="e2bab-138">Utilisez l'instruction [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="e2bab-138">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="e2bab-139">ALTER AVAILABILITY GROUP *nom_groupe* ADD DATABASE *nom_base_de_données* [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="e2bab-139">ALTER AVAILABILITY GROUP *group_name* ADD DATABASE *database_name* [,...*n*]</span></span>  
  
     <span data-ttu-id="e2bab-140">où *nom_groupe* est le nom du groupe de disponibilité et *nom_base_de_données* est le nom d’une base de données à ajouter au groupe.</span><span class="sxs-lookup"><span data-stu-id="e2bab-140">where *group_name* is the name of the availability group and *database_name* is the name of a database to be added to the group.</span></span>  
  
     <span data-ttu-id="e2bab-141">L’exemple suivant ajoute la base de données *MyDb3* au groupe de disponibilité *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="e2bab-141">The following example adds the *MyDb3* database to the *MyAG* availability group.</span></span>  
  
    ```  
    -- Connect to the server instance that hosts the primary replica.  
    -- Add an existing database to the availability group.  
    ALTER AVAILABILITY GROUP MyAG ADD DATABASE MyDb3;  
    GO  
    ```  
  
3.  <span data-ttu-id="e2bab-142">Après avoir ajouté une base de données à un groupe de disponibilité, vous devez configurer la base de données secondaire correspondante sur chaque instance de serveur qui héberge un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="e2bab-142">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="e2bab-143">Pour plus d’informations, consultez [Démarrer un mouvement de données sur une base de données secondaire AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e2bab-143">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="e2bab-144">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2bab-144">Using PowerShell</span></span>  
 <span data-ttu-id="e2bab-145">**Pour ajouter une base de données à un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="e2bab-145">**To add a database to an availability group**</span></span>  
  
1.  <span data-ttu-id="e2bab-146">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="e2bab-146">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="e2bab-147">Utilisez l'applet de commande `Add-SqlAvailabilityDatabase`.</span><span class="sxs-lookup"><span data-stu-id="e2bab-147">Use the `Add-SqlAvailabilityDatabase` cmdlet.</span></span>  
  
     <span data-ttu-id="e2bab-148">Par exemple, la commande suivante ajoute la base de données secondaire `MyDd` au groupe de disponibilité `MyAG` , dont le réplica principal est hébergé par `PrimaryServer\InstanceName`.</span><span class="sxs-lookup"><span data-stu-id="e2bab-148">For example, the following command adds the secondary database `MyDd` to the `MyAG` availability group, whose primary replica is hosted by `PrimaryServer\InstanceName`.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase `   
     -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAG `   
     -Database "MyDb"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="e2bab-149">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2bab-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="e2bab-150">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e2bab-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
3.  <span data-ttu-id="e2bab-151">Après avoir ajouté une base de données à un groupe de disponibilité, vous devez configurer la base de données secondaire correspondante sur chaque instance de serveur qui héberge un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="e2bab-151">After you add a database to an availability group, you need to configure the corresponding secondary database on each server instance that hosts a secondary replica.</span></span> <span data-ttu-id="e2bab-152">Pour plus d’informations, consultez [Démarrer un mouvement de données sur une base de données secondaire AlwaysOn &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e2bab-152">For more information, see [Start Data Movement on an AlwaysOn Secondary Database &#40;SQL Server&#41;](start-data-movement-on-an-always-on-secondary-database-sql-server.md).</span></span>  
  
 <span data-ttu-id="e2bab-153">Pour configurer et utiliser le fournisseur de SQL Server PowerShell, consultez [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="e2bab-153">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>

 <span data-ttu-id="e2bab-154">L'exemple suivant illustre le processus complet de préparation d'une base de données secondaire à partir d'une base de données présente sur l'instance de serveur qui héberge le réplica principal d'un groupe de disponibilité, qui consiste à ajouter la base de données à un groupe de disponibilité (en tant que base de données primaire) puis à joindre la base de données secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="e2bab-154">The following example shows the full process for preparing a secondary database from a database on the server instance that hosts the primary replica of an availability group, adding the database to an availability group (as a primary database), and then joining the secondary database to the availability group.</span></span> <span data-ttu-id="e2bab-155">Dans cet exemple, la base de données et son journal de transactions sont d'abord sauvegardés.</span><span class="sxs-lookup"><span data-stu-id="e2bab-155">First, the example backs up the database and its transaction log.</span></span> <span data-ttu-id="e2bab-156">Les sauvegardes de la base de données et du journal sont ensuite restaurées sur les instances de serveur qui hébergent un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="e2bab-156">Then the example restores the database and log backups to the server instances that host a secondary replica.</span></span>  
  
 <span data-ttu-id="e2bab-157">Dans cet exemple, l'applet de commande `Add-SqlAvailabilityDatabase` est appelée deux fois : d'abord sur le réplica principal pour ajouter la base de données au groupe de disponibilité, puis sur le réplica secondaire pour joindre la base de données secondaire présente sur ce réplica au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="e2bab-157">The example calls `Add-SqlAvailabilityDatabase` twice: first on the primary replica to add the database to the availability group, and then on the secondary replica to join the secondary database on that replica to the availability group.</span></span> <span data-ttu-id="e2bab-158">Si vous avez plusieurs réplicas secondaires, restaurez et joignez la base de données secondaire sur chacun d'eux.</span><span class="sxs-lookup"><span data-stu-id="e2bab-158">If you have more than one secondary replica, restore and join the secondary database on each of them.</span></span>  
  
```powershell
$DatabaseBackupFile = "\\share\backups\MyDatabase.bak"  
$LogBackupFile = "\\share\backups\MyDatabase.trn"  
$MyAgPrimaryPath = "SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg"  
$MyAgSecondaryPath = "SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAg"  
  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "PrimaryServer\InstanceName"  
Backup-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "PrimaryServer\InstanceName" -BackupAction 'Log'  
  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $DatabaseBackupFile -ServerInstance "SecondaryServer\InstanceName" -NoRecovery  
Restore-SqlDatabase -Database "MyDatabase" -BackupFile $LogBackupFile -ServerInstance "SecondaryServer\InstanceName" -RestoreAction 'Log' -NoRecovery  
  
Add-SqlAvailabilityDatabase -Path $MyAgPrimaryPath -Database "MyDatabase"  
Add-SqlAvailabilityDatabase -Path $MyAgSecondaryPath -Database "MyDatabase"
```  
  
## <a name="see-also"></a><span data-ttu-id="e2bab-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2bab-159">See Also</span></span>  
 <span data-ttu-id="e2bab-160">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e2bab-160">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="e2bab-161">[Création et configuration des groupes de disponibilité &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e2bab-161">[Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="e2bab-162">[Utilisez le tableau de bord AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="e2bab-162">[Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="e2bab-163">Surveiller des groupes de disponibilité &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e2bab-163">Monitor Availability Groups &#40;Transact-SQL&#41;</span></span>](monitor-availability-groups-transact-sql.md)  
