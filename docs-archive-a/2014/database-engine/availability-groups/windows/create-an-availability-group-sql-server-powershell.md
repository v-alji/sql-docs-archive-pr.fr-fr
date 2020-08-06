---
title: Créer un groupe de disponibilité (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: bc69a7df-20fa-41e1-9301-11317c5270d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3af9bf896b954e6849c0d491f9ed267655369ccb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710819"
---
# <a name="create-an-availability-group-sql-server-powershell"></a><span data-ttu-id="f0315-102">Créer un groupe de disponibilité (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f0315-102">Create an Availability Group (SQL Server PowerShell)</span></span>
  <span data-ttu-id="f0315-103">Cette rubrique explique comment utiliser des applets de commande PowerShell pour créer et configurer un groupe de disponibilité AlwaysOn à l'aide de PowerShell dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0315-103">This topic describes how to use PowerShell cmdlets to create and configure an AlwaysOn availability group by using PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="f0315-104">Un *groupe de disponibilité* définit un jeu de bases de données utilisateur qui basculent en tant qu'unité unique et un jeu de partenaires de basculement, appelés *réplicas de disponibilité*, qui prennent en charge le basculement.</span><span class="sxs-lookup"><span data-stu-id="f0315-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, which support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0315-105">Pour obtenir une présentation des groupes de disponibilité, consultez [Vue d’ensemble des groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0315-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="f0315-106">Comme alternative à l'utilisation des applets de commande PowerShell, vous pouvez utiliser l'Assistant Création d'un groupe de disponibilité ou [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0315-106">As an alternative to using PowerShell cmdlets, you can use the Create Availability Group wizard or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f0315-107">Pour plus d’informations, consultez [Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md) ou [Créer un groupe de disponibilité &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f0315-107">For more information, see [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md) or [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f0315-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f0315-108">Before You Begin</span></span>  
 <span data-ttu-id="f0315-109">Nous vous recommandons fortement de lire cette section avant d'essayer de créer votre premier groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0315-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a> <span data-ttu-id="f0315-110">Conditions préalables requises, restrictions et recommandations</span><span class="sxs-lookup"><span data-stu-id="f0315-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="f0315-111">Avant de créer un groupe de disponibilité, vérifiez que les instances hôtes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] résident chacune sur un nœud WSFC (Clustering de basculement Windows Server) différent au sein du même clustering de basculement WSFC.</span><span class="sxs-lookup"><span data-stu-id="f0315-111">Before creating an availability group, verify that the host instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] each resides on a different Windows Server Failover Clustering (WSFC) node of a single WSFC failover cluster.</span></span> <span data-ttu-id="f0315-112">En outre, vérifiez que vos instances de serveur respectent les autres conditions préalables applicables, que toutes les autres spécifications [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] sont respectées et que vous avez pris note des recommandations.</span><span class="sxs-lookup"><span data-stu-id="f0315-112">Also, verify that your server instances met the other server-instance prerequisites and that all of the other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] requirements are meet and that you are aware of the recommendations.</span></span> <span data-ttu-id="f0315-113">Pour plus d’informations, nous vous conseillons vivement de lire la rubrique [Conditions préalables requises, restrictions et recommandations pour les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="f0315-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f0315-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0315-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f0315-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f0315-115">Permissions</span></span>  
 <span data-ttu-id="f0315-116">Requiert l’appartenance au rôle serveur fixe **sysadmin** et l’autorisation de serveur CREATE AVAILABILITY GROUP, l’autorisation ALTER ANY AVAILABILITY GROUP ou l’autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="f0315-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-powershell-cmdlets"></a><a name="SummaryPSStatements"></a><span data-ttu-id="f0315-117">Résumé des tâches et applets de commande PowerShell correspondantes</span><span class="sxs-lookup"><span data-stu-id="f0315-117">Summary of Tasks and Corresponding PowerShell Cmdlets</span></span>  
 <span data-ttu-id="f0315-118">Le tableau suivant répertorie les tâches de base impliquées dans la configuration d'un groupe de disponibilité et indique celles qui sont prises en charge par les applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0315-118">The following table lists the basic tasks involved in configuring an availability group and indicates those that are supported by PowerShell cmdlets.</span></span> <span data-ttu-id="f0315-119">Les tâches [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] doivent être effectuées dans la séquence dans laquelle elles sont présentées dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="f0315-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="f0315-120">Tâche</span><span class="sxs-lookup"><span data-stu-id="f0315-120">Task</span></span>|<span data-ttu-id="f0315-121">Applets de commande PowerShell (le cas échéant) ou instruction Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0315-121">PowerShell Cmdlets (if Available) or Transact-SQL Statement</span></span>|<span data-ttu-id="f0315-122">Où effectuer la tâche**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="f0315-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|--------------------------------------------------------------------|-------------------------------------------|  
|<span data-ttu-id="f0315-123">Créer le point de terminaison de mise en miroir de bases de données (une fois par instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="f0315-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|`New-SqlHadrEndPoint`|<span data-ttu-id="f0315-124">Exécutez sur chaque instance de serveur dans laquelle le point de terminaison de mise en miroir de bases de données est manquant.</span><span class="sxs-lookup"><span data-stu-id="f0315-124">Execute on each server instance that lacks database mirroring endpoint.</span></span><br /><br /> <span data-ttu-id="f0315-125">Remarque : pour modifier un point de terminaison de mise en miroir de bases de données existant, utilisez `Set-SqlHadrEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="f0315-125">Note: To alter an existing database mirroring endpoint, use `Set-SqlHadrEndpoint`.</span></span>|  
|<span data-ttu-id="f0315-126">Créer un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="f0315-126">Create availability group</span></span>|<span data-ttu-id="f0315-127">En premier lieu, utilisez l'applet de commande `New-SqlAvailabilityReplica` avec le paramètre `-AsTemplate` pour créer un objet réplica de disponibilité en mémoire pour chacun des deux réplicas de disponibilité que vous envisagez d'inclure dans le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0315-127">First, use the `New-SqlAvailabilityReplica` cmdlet with the `-AsTemplate` parameter to create an in-memory availability-replica object for each of the two availability replicas that you plan to include in the availability group.</span></span><br /><br /> <span data-ttu-id="f0315-128">Puis, créez le groupe de disponibilité en utilisant l'applet de commande `New-SqlAvailabilityGroup` et en référençant vos objets réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0315-128">Then, create the availability group by using the `New-SqlAvailabilityGroup` cmdlet and referencing your availability-replica objects.</span></span>|<span data-ttu-id="f0315-129">Exécutez sur l'instance de serveur qui hébergera le réplica principal initial.</span><span class="sxs-lookup"><span data-stu-id="f0315-129">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="f0315-130">Joindre le réplica secondaire au groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="f0315-130">Join secondary replica to availability group</span></span>|`Join-SqlAvailabilityGroup`|<span data-ttu-id="f0315-131">Exécutez sur chaque instance de serveur qui héberge un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="f0315-131">Execute on each server instance that is hosts a secondary replica.</span></span>|  
|<span data-ttu-id="f0315-132">Préparer la base de données secondaire</span><span class="sxs-lookup"><span data-stu-id="f0315-132">Prepare the secondary database</span></span>|<span data-ttu-id="f0315-133">`Backup-SqlDatabase` et `Restore-SqlDatabase`</span><span class="sxs-lookup"><span data-stu-id="f0315-133">`Backup-SqlDatabase` and `Restore-SqlDatabase`</span></span>|<span data-ttu-id="f0315-134">Créez des sauvegardes sur l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f0315-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="f0315-135">Restaurez les sauvegardes sur chaque instance de serveur qui héberge un réplica secondaire, à l'aide du paramètre de restauration `NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="f0315-135">Restore backups on each server instance that hosts a secondary replica, using the `NoRecovery` restore parameter.</span></span> <span data-ttu-id="f0315-136">Si les chemins d'accès de fichier diffèrent entre les ordinateurs qui hébergent le réplica principal et le réplica secondaire cible, utilisez également le paramètre de restauration `RelocateFile`.</span><span class="sxs-lookup"><span data-stu-id="f0315-136">If the file paths differ between the computers that host the primary replica and the target secondary replica, also use the `RelocateFile` restore parameter.</span></span>|  
|<span data-ttu-id="f0315-137">Démarrer la synchronisation des données en joignant chaque base de données secondaire au groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="f0315-137">Start data synchronization by joining each secondary database to availability group</span></span>|`Add-SqlAvailabilityDatabase`|<span data-ttu-id="f0315-138">Exécutez sur chaque instance de serveur qui héberge un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="f0315-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="f0315-139">**<sup>\*</sup>** Pour effectuer une tâche donnée, remplacez le répertoire ( `cd` ) par l’instance ou les instances de serveur indiquées.</span><span class="sxs-lookup"><span data-stu-id="f0315-139">**<sup>\*</sup>**  To perform a given task, change directory (`cd`) to the indicated server instance or instances.</span></span>  
  
###  <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><a name="PsProviderLinks"></a><span data-ttu-id="f0315-140">Pour configurer et utiliser le fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0315-140">To Set Up and Use the SQL Server PowerShell Provider</span></span>  
  
-   [<span data-ttu-id="f0315-141">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0315-141">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="f0315-142">Obtenir de l'aide sur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0315-142">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="using-powershell-to-create-and-configure-an-availability-group"></a><a name="PowerShellProcedure"></a><span data-ttu-id="f0315-143">Utilisation de PowerShell pour créer et configurer un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="f0315-143">Using PowerShell to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0315-144">Pour afficher la syntaxe et un exemple d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement PowerShell [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0315-144">To view the syntax and an example of a given cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f0315-145">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f0315-145">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
1.  <span data-ttu-id="f0315-146">Accédez au répertoire (`cd`) de l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f0315-146">Change directory (`cd`) to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="f0315-147">Créez un objet réplica de disponibilité en mémoire pour le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="f0315-147">Create an in-memory availability-replica object for the primary replica.</span></span>  
  
3.  <span data-ttu-id="f0315-148">Créez un objet réplica de disponibilité en mémoire pour chacun des réplicas secondaires.</span><span class="sxs-lookup"><span data-stu-id="f0315-148">Create an in-memory availability-replica object for each of the secondary replicas.</span></span>  
  
4.  <span data-ttu-id="f0315-149">Créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0315-149">Create the availability group.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f0315-150">La longueur maximale d'un nom de groupe de disponibilité est de 128 caractères.</span><span class="sxs-lookup"><span data-stu-id="f0315-150">The maximum length for an availability group name is 128 characters.</span></span>  
  
5.  <span data-ttu-id="f0315-151">Joignez le nouveau réplica secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0315-151">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="f0315-152">Pour plus d’informations, consultez [Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0315-152">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
6.  <span data-ttu-id="f0315-153">Pour chaque base de données dans le groupe de disponibilité, créez une base de données secondaire en restaurant des sauvegardes récentes de la base de données primaire, à l'aide de RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="f0315-153">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span>  
  
7.  <span data-ttu-id="f0315-154">Joignez chaque nouvelle base de données secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0315-154">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="f0315-155">Pour plus d’informations, consultez [Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0315-155">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
8.  <span data-ttu-id="f0315-156">Éventuellement, utilisez la commande `dir` Windows pour vérifier le contenu du nouveau groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0315-156">Optionally, use the Windows `dir` command to verify the contents of the new availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0315-157">Si les comptes de service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] des instances serveur s'exécutent sous des comptes utilisateur de domaine différents, sur chaque instance serveur, créez une connexion pour l'autre instance serveur et accordez l'autorisation CONNECT sur le point de terminaison de mise en miroir de bases de données local.</span><span class="sxs-lookup"><span data-stu-id="f0315-157">If the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service accounts of the server instances run under different domain user accounts, on each server instance, create a login for the other server instance and grant this login CONNECT permission to the local database mirroring endpoint.</span></span>  
  
##  <a name="example-using-powershell-to-create-an-availability-group"></a><a name="ExampleConfigureGroup"></a><span data-ttu-id="f0315-158">Exemple : utilisation de PowerShell pour créer un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="f0315-158">Example: Using PowerShell to Create an Availability Group</span></span>  
 <span data-ttu-id="f0315-159">L'exemple PowerShell suivant crée et configure un groupe de disponibilité simple nommé `MyAG` avec deux réplicas de disponibilité et une base de données de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0315-159">The following PowerShell example creates and configures a simple availability group named `MyAG` with two availability replicas and one availability database.</span></span> <span data-ttu-id="f0315-160">L'exemple :</span><span class="sxs-lookup"><span data-stu-id="f0315-160">The example:</span></span>  
  
1.  <span data-ttu-id="f0315-161">Sauvegarde `MyDatabase` et son journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="f0315-161">Backs up `MyDatabase` and its transaction log.</span></span>  
  
2.  <span data-ttu-id="f0315-162">Restaure `MyDatabase` et son journal des transactions, à l'aide de l'option `-NoRecovery`.</span><span class="sxs-lookup"><span data-stu-id="f0315-162">Restores `MyDatabase` and its transaction log, using the `-NoRecovery` option.</span></span>  
  
3.  <span data-ttu-id="f0315-163">Crée une représentation en mémoire du réplica principal, qui sera hébergée par l'instance locale de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (nommée `PrimaryComputer\Instance`).</span><span class="sxs-lookup"><span data-stu-id="f0315-163">Creates an in-memory representation of the primary replica, which will be hosted by the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (named `PrimaryComputer\Instance`).</span></span>  
  
4.  <span data-ttu-id="f0315-164">Crée une représentation en mémoire du réplica secondaire, qui sera hébergée par une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (nommée `SecondaryComputer\Instance`).</span><span class="sxs-lookup"><span data-stu-id="f0315-164">Creates an in-memory representation of the secondary replica, which will be hosted by an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (named `SecondaryComputer\Instance`).</span></span>  
  
5.  <span data-ttu-id="f0315-165">Crée un groupe de disponibilité nommé `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="f0315-165">Creates an availability group named `MyAG`.</span></span>  
  
6.  <span data-ttu-id="f0315-166">Joint le réplica secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0315-166">Joins the secondary replica to the availability group.</span></span>  
  
7.  <span data-ttu-id="f0315-167">Joint la base de données secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="f0315-167">Joins the secondary database to the availability group.</span></span>  
  
```powershell
# Backup my database and its log on the primary  
Backup-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.bak" `  
    -ServerInstance "PrimaryComputer\Instance"  
  
Backup-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.log" `  
    -ServerInstance "PrimaryComputer\Instance" `  
    -BackupAction Log   
  
# Restore the database and log on the secondary (using NO RECOVERY)  
Restore-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.bak" `  
    -ServerInstance "SecondaryComputer\Instance" `  
    -NoRecovery  
  
Restore-SqlDatabase `  
    -Database "MyDatabase" `  
    -BackupFile "\\share\backups\MyDatabase.log" `  
    -ServerInstance "SecondaryComputer\Instance" `  
    -RestoreAction Log `  
    -NoRecovery  
  
# Create an in-memory representation of the primary replica.  
$primaryReplica = New-SqlAvailabilityReplica `  
    -Name "PrimaryComputer\Instance" `  
    -EndpointURL "TCP://PrimaryComputer.domain.com:5022" `  
    -AvailabilityMode "SynchronousCommit" `  
    -FailoverMode "Automatic" `  
    -Version 12 `  
    -AsTemplate  
  
# Create an in-memory representation of the secondary replica.  
$secondaryReplica = New-SqlAvailabilityReplica `  
    -Name "SecondaryComputer\Instance" `  
    -EndpointURL "TCP://SecondaryComputer.domain.com:5022" `  
    -AvailabilityMode "SynchronousCommit" `  
    -FailoverMode "Automatic" `  
    -Version 12 `  
    -AsTemplate  
  
# Create the availability group  
New-SqlAvailabilityGroup `  
    -Name "MyAG" `  
    -Path "SQLSERVER:\SQL\PrimaryComputer\Instance" `  
    -AvailabilityReplica @($primaryReplica,$secondaryReplica) `  
    -Database "MyDatabase"  
  
# Join the secondary replica to the availability group.  
Join-SqlAvailabilityGroup -Path "SQLSERVER:\SQL\SecondaryComputer\Instance" -Name "MyAG"  
  
# Join the secondary database to the availability group.  
Add-SqlAvailabilityDatabase -Path "SQLSERVER:\SQL\SecondaryComputer\Instance\AvailabilityGroups\MyAG" -Database "MyDatabase"  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="f0315-168">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="f0315-168">Related Tasks</span></span>  
 <span data-ttu-id="f0315-169">**Pour configurer une instance de serveur pour les groupes de disponibilité AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f0315-169">**To configure a server instance for AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="f0315-170">Activer et désactiver les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-170">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="f0315-171">Créer un point de terminaison de mise en miroir de bases de données pour groupes de disponibilité AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-171">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
 <span data-ttu-id="f0315-172">**Pour configurer les propriétés du groupe de disponibilité et du réplica**</span><span class="sxs-lookup"><span data-stu-id="f0315-172">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="f0315-173">Modifier le mode de disponibilité d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-173">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="f0315-174">Modifier le mode de basculement d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-174">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="f0315-175">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-175">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="f0315-176">Configurer la stratégie de basculement flexible pour contrôler les conditions du basculement automatique (groupes de disponibilité AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="f0315-176">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="f0315-177">Spécifier l’URL de point de terminaison lors de l’ajout ou lors de la modification d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-177">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="f0315-178">Configurer la sauvegarde sur des réplicas de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-178">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="f0315-179">Configurer l’accès en lecture seule sur un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-179">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="f0315-180">Configurer le routage en lecture seule pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-180">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f0315-181">Modifier le délai d’expiration de session pour un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-181">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="f0315-182">**Pour terminer la configuration du groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="f0315-182">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="f0315-183">Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-183">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f0315-184">Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-184">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f0315-185">Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-185">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="f0315-186">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-186">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="f0315-187">**Autres méthodes de création d'un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="f0315-187">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="f0315-188">Utiliser l’Assistant Groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-188">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f0315-189">Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-189">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f0315-190">Créer un groupe de disponibilité &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-190">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
 <span data-ttu-id="f0315-191">**Pour résoudre les problèmes de configuration des groupes de disponibilité AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f0315-191">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="f0315-192">Résoudre les problèmes de configuration de groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f0315-192">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="f0315-193">Résoudre les problèmes liés à l’échec d’une opération d’ajout de fichier &#40;groupes de disponibilité AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-193">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="f0315-194">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="f0315-194">Related Content</span></span>  
  
-   <span data-ttu-id="f0315-195">**Blogs :**</span><span class="sxs-lookup"><span data-stu-id="f0315-195">**Blogs:**</span></span>  
  
     [<span data-ttu-id="f0315-196">AlwaysON - HADRON Learning Series : Worker Pool Usage for HADRON Enabled Databases (en anglais)</span><span class="sxs-lookup"><span data-stu-id="f0315-196">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="f0315-197">Configuration d'AlwaysOn avec SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0315-197">Configuring AlwaysOn with SQL Server PowerShell</span></span>](https://blogs.msdn.com/b/sqlalwayson/archive/2012/02/03/configuring-alwayson-with-sql-server-powershell.aspx)  
  
     [<span data-ttu-id="f0315-198">Blogs de l'équipe de SQL Server AlwaysOn : Blog officiel de l'équipe de SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f0315-198">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="f0315-199">Blogs des ingénieurs du Service clientèle et du Support technique de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f0315-199">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="f0315-200">**Vidéos :**</span><span class="sxs-lookup"><span data-stu-id="f0315-200">**Videos:**</span></span>  
  
     [<span data-ttu-id="f0315-201">Microsoft SQL Server, nom de code « Denali », série AlwaysOn, Partie 1 : Présentation de la solution haute disponibilité de la prochaine génération</span><span class="sxs-lookup"><span data-stu-id="f0315-201">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="f0315-202">Microsoft SQL Server, nom de code « Denali », série AlwaysOn, Partie 2 : Génération d'une solution haute disponibilité critique à l'aide d'AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f0315-202">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="f0315-203">**Livres blancs :**</span><span class="sxs-lookup"><span data-stu-id="f0315-203">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="f0315-204">Guide de solutions Microsoft SQL Server AlwaysOn pour la haute disponibilité et la récupération d'urgence</span><span class="sxs-lookup"><span data-stu-id="f0315-204">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="f0315-205">Livres blancs de Microsoft pour SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="f0315-205">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="f0315-206">Livres blancs de l'équipe de consultants clients de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f0315-206">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="f0315-207">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0315-207">See Also</span></span>  
 [<span data-ttu-id="f0315-208">Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0315-208">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md)   
