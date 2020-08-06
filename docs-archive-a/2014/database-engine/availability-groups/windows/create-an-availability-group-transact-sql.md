---
title: Créer un groupe de disponibilité (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: 8b0a6301-8b79-4415-b608-b40876f30066
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57a494af168a8f5572bafe93f8fb47b22a954a19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710812"
---
# <a name="create-an-availability-group-transact-sql"></a><span data-ttu-id="bad3a-102">Créer un groupe de disponibilité (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bad3a-102">Create an Availability Group (Transact-SQL)</span></span>
  <span data-ttu-id="bad3a-103">Cette rubrique explique comment utiliser [!INCLUDE[tsql](../../../includes/tsql-md.md)] pour créer et configurer un groupe de disponibilité sur des instances de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] sur lesquelles la fonctionnalité [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] est activée.</span><span class="sxs-lookup"><span data-stu-id="bad3a-103">This topic describes how to use [!INCLUDE[tsql](../../../includes/tsql-md.md)] to create and configure an availability group on instances of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] on which the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature is enabled.</span></span> <span data-ttu-id="bad3a-104">Un *groupe de disponibilité* définit un jeu de bases de données utilisateur qui basculent en tant qu'unité unique et un jeu de partenaires de basculement, appelés *réplicas de disponibilité*, qui prennent en charge le basculement.</span><span class="sxs-lookup"><span data-stu-id="bad3a-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, that support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bad3a-105">Pour obtenir une présentation des groupes de disponibilité, consultez [Vue d’ensemble des groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bad3a-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="bad3a-106">En guise d'alternative à [!INCLUDE[tsql](../../../includes/tsql-md.md)], vous pouvez utiliser l'Assistant Création d'un groupe de disponibilité ou les applets de commande PowerShell [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bad3a-106">As an alternative to using [!INCLUDE[tsql](../../../includes/tsql-md.md)], you can use the Create Availability Group wizard or [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell cmdlets.</span></span> <span data-ttu-id="bad3a-107">Pour plus d’informations, consultez [Utiliser l’Assistant Groupe de disponibilité &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md), [Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)ou [Créer un groupe de disponibilité &#40;SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="bad3a-107">For more information, see [Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md), [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md), or [Create an Availability Group &#40;SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bad3a-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="bad3a-108">Before You Begin</span></span>  
 <span data-ttu-id="bad3a-109">Nous vous recommandons fortement de lire cette section avant d'essayer de créer votre premier groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bad3a-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a><span data-ttu-id="bad3a-110">Conditions préalables requises, restrictions et recommandations</span><span class="sxs-lookup"><span data-stu-id="bad3a-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="bad3a-111">Avant de créer un groupe de disponibilité, vérifiez que les instances de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui hébergent les réplicas de disponibilité résident sur des nœuds WSFC (Windows Server Failover Clustering) différents au sein du même clustering de basculement WSFC.</span><span class="sxs-lookup"><span data-stu-id="bad3a-111">Before creating an availability group, verify that the instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that host availability replicas reside on different Windows Server Failover Clustering (WSFC) node within the same WSFC failover cluster.</span></span> <span data-ttu-id="bad3a-112">Vérifiez également que chaque instance du serveur répond à toutes les autres conditions requises relatives à [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bad3a-112">Also, verify that each of the server instance meets all other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites.</span></span> <span data-ttu-id="bad3a-113">Pour plus d’informations, nous vous conseillons vivement de lire la rubrique [Conditions préalables requises, restrictions et recommandations pour les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="bad3a-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bad3a-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bad3a-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bad3a-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="bad3a-115">Permissions</span></span>  
 <span data-ttu-id="bad3a-116">Requiert l’appartenance au rôle serveur fixe **sysadmin** et l’autorisation de serveur CREATE AVAILABILITY GROUP, l’autorisation ALTER ANY AVAILABILITY GROUP ou l’autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="bad3a-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-transact-sql-statements"></a><a name="SummaryTsqlStatements"></a> <span data-ttu-id="bad3a-117">Résumé des tâches et instructions Transact-SQL correspondantes</span><span class="sxs-lookup"><span data-stu-id="bad3a-117">Summary of Tasks and Corresponding Transact-SQL Statements</span></span>  
 <span data-ttu-id="bad3a-118">Le tableau suivant répertorie les tâches de base impliquées dans la création et la configuration d'un groupe de disponibilité et indique les instructions [!INCLUDE[tsql](../../../includes/tsql-md.md)] à utiliser pour ces tâches.</span><span class="sxs-lookup"><span data-stu-id="bad3a-118">The following table lists the basic tasks involved in creating and configuring an availability group and indicates which [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements to use for these tasks.</span></span> <span data-ttu-id="bad3a-119">Les tâches [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] doivent être effectuées dans la séquence dans laquelle elles sont présentées dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="bad3a-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="bad3a-120">Tâche</span><span class="sxs-lookup"><span data-stu-id="bad3a-120">Task</span></span>|<span data-ttu-id="bad3a-121">Instruction(s) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bad3a-121">Transact-SQL Statement(s)</span></span>|<span data-ttu-id="bad3a-122">Où effectuer la tâche**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="bad3a-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|----------------------------------|-------------------------------------------|  
|<span data-ttu-id="bad3a-123">Créer le point de terminaison de mise en miroir de bases de données (une fois par instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="bad3a-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|<span data-ttu-id="bad3a-124">[Créer un point de terminaison](/sql/t-sql/statements/create-endpoint-transact-sql) *EndpointName* ... POUR DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="bad3a-124">[CREATE ENDPOINT](/sql/t-sql/statements/create-endpoint-transact-sql) *endpointName* ... FOR DATABASE_MIRRORING</span></span>|<span data-ttu-id="bad3a-125">Exécutez sur chaque instance de serveur dans laquelle le point de terminaison de mise en miroir de bases de données est manquant.</span><span class="sxs-lookup"><span data-stu-id="bad3a-125">Execute on each server instance that lacks database mirroring endpoint.</span></span>|  
|<span data-ttu-id="bad3a-126">Créer un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="bad3a-126">Create availability group</span></span>|[<span data-ttu-id="bad3a-127">CREATE AVAILABILITY GROUP</span><span class="sxs-lookup"><span data-stu-id="bad3a-127">CREATE AVAILABILITY GROUP</span></span>](/sql/t-sql/statements/create-availability-group-transact-sql)|<span data-ttu-id="bad3a-128">Exécutez sur l'instance de serveur qui hébergera le réplica principal initial.</span><span class="sxs-lookup"><span data-stu-id="bad3a-128">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="bad3a-129">Joindre le réplica secondaire au groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="bad3a-129">Join secondary replica to availability group</span></span>|<span data-ttu-id="bad3a-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *nom_groupe* JOIN</span><span class="sxs-lookup"><span data-stu-id="bad3a-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *group_name* JOIN</span></span>|<span data-ttu-id="bad3a-131">Exécutez sur chaque instance de serveur qui héberge un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="bad3a-131">Execute on each server instance that hosts a secondary replica.</span></span>|  
|<span data-ttu-id="bad3a-132">Préparer la base de données secondaire</span><span class="sxs-lookup"><span data-stu-id="bad3a-132">Prepare the secondary database</span></span>|<span data-ttu-id="bad3a-133">[Sauvegarde](/sql/t-sql/statements/backup-transact-sql) et [restauration](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bad3a-133">[BACKUP](/sql/t-sql/statements/backup-transact-sql) and [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>|<span data-ttu-id="bad3a-134">Créez des sauvegardes sur l'instance de serveur qui héberge le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="bad3a-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="bad3a-135">Restaurez les sauvegardes sur chaque instance de serveur qui héberge un réplica secondaire, à l'aide de RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="bad3a-135">Restore backups on each server instance that hosts a secondary replica, using RESTORE WITH NORECOVERY.</span></span>|  
|<span data-ttu-id="bad3a-136">Démarrer la synchronisation des données en joignant chaque base de données secondaire au groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="bad3a-136">Start data synchronization by joining each secondary database to availability group</span></span>|<span data-ttu-id="bad3a-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *nom_base_de_données* SET HADR AVAILABILITY GROUP = *nom_groupe*</span><span class="sxs-lookup"><span data-stu-id="bad3a-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>|<span data-ttu-id="bad3a-138">Exécutez sur chaque instance de serveur qui héberge un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="bad3a-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="bad3a-139">**<sup>\*</sup>** Pour effectuer une tâche donnée, connectez-vous à l’instance ou aux instances de serveur indiquées.</span><span class="sxs-lookup"><span data-stu-id="bad3a-139">**<sup>\*</sup>**  To perform a given task, connect to the indicated server instance or instances.</span></span>  
  
##  <a name="using-transact-sql-to-create-and-configure-an-availability-group"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bad3a-140">Utilisation de Transact-SQL pour créer et configurer un groupe de disponibilité</span><span class="sxs-lookup"><span data-stu-id="bad3a-140">Using Transact-SQL to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bad3a-141">Pour obtenir un exemple de procédure de configuration qui contient des exemples de code de chacune de ces instructions [!INCLUDE[tsql](../../../includes/tsql-md.md)] , consultez [Exemple : configuration d’un groupe de disponibilité qui utilise l’authentification Windows](#ExampleConfigAGWinAuth).</span><span class="sxs-lookup"><span data-stu-id="bad3a-141">For a sample configuration procedure containing code examples of each these [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements, see [Example: Configuring an Availability Group that Uses Windows Authentication](#ExampleConfigAGWinAuth).</span></span>  
  
1.  <span data-ttu-id="bad3a-142">Connectez-vous à l'instance de serveur qui hébergera le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="bad3a-142">Connect to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="bad3a-143">Créez le groupe de disponibilité à l’aide de l’instruction [Create Availability Group](/sql/t-sql/statements/create-availability-group-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bad3a-143">Create the availability group by using the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
3.  <span data-ttu-id="bad3a-144">Joignez le nouveau réplica secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bad3a-144">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="bad3a-145">Pour plus d’informations, consultez [Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bad3a-145">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="bad3a-146">Pour chaque base de données dans le groupe de disponibilité, créez une base de données secondaire en restaurant des sauvegardes récentes de la base de données primaire, à l'aide de RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="bad3a-146">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="bad3a-147">Pour plus d’informations, consultez [Exemple : configuration d’un groupe de disponibilité à l’aide de l’authentification Windows (Transact-SQL)](create-an-availability-group-transact-sql.md), en commençant par l’étape de restauration de la sauvegarde de base de données.</span><span class="sxs-lookup"><span data-stu-id="bad3a-147">For more information, see [Example: Setting Up an Availability Group Using Windows Authentication (Transact-SQL)](create-an-availability-group-transact-sql.md), starting with the step that restores the database backup.</span></span>  
  
5.  <span data-ttu-id="bad3a-148">Joignez chaque nouvelle base de données secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bad3a-148">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="bad3a-149">Pour plus d’informations, consultez [Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bad3a-149">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="example-configuring-an-availability-group-that-uses-windows-authentication"></a><a name="ExampleConfigAGWinAuth"></a> <span data-ttu-id="bad3a-150">Exemple : configuration d’un groupe de disponibilité qui utilise l’authentification Windows</span><span class="sxs-lookup"><span data-stu-id="bad3a-150">Example: Configuring an Availability Group that Uses Windows Authentication</span></span>  
 <span data-ttu-id="bad3a-151">Cet exemple crée un exemple de procédure de configuration [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] qui utilise [!INCLUDE[tsql](../../../includes/tsql-md.md)] pour installer des points de terminaison de mise en miroir de bases de données qui utilisent l'authentification Windows, et créer et configurer un groupe de disponibilité et ses bases de données secondaires.</span><span class="sxs-lookup"><span data-stu-id="bad3a-151">This example creates a sample [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration procedure that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to set up database mirroring endpoints that use Windows Authentication and to create and configure an availability group and its secondary databases.</span></span>  
  
 <span data-ttu-id="bad3a-152">Cet exemple contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="bad3a-152">This example contains the following sections:</span></span>  
  
-   [<span data-ttu-id="bad3a-153">Conditions préalables à l’utilisation de l’exemple de procédure de configuration</span><span class="sxs-lookup"><span data-stu-id="bad3a-153">Prerequisites for Using the Sample Configuration Procedure</span></span>](#PrerequisitesForExample)  
  
-   [<span data-ttu-id="bad3a-154">Exemple de procédure de configuration</span><span class="sxs-lookup"><span data-stu-id="bad3a-154">Sample Configuration Procedure</span></span>](#SampleProcedure)  
  
-   [<span data-ttu-id="bad3a-155">Exemple de code complet pour l'exemple de procédure de configuration</span><span class="sxs-lookup"><span data-stu-id="bad3a-155">Complete Code Example for Sample Configuration Procedure</span></span>](#CompleteCodeExample)  
  
###  <a name="prerequisites-for-using-the-sample-configuration-procedure"></a><a name="PrerequisitesForExample"></a> <span data-ttu-id="bad3a-156">Conditions préalables requises pour l'utilisation de l'exemple de procédure de configuration</span><span class="sxs-lookup"><span data-stu-id="bad3a-156">Prerequisites for Using the Sample Configuration Procedure</span></span>  
 <span data-ttu-id="bad3a-157">Cet exemple de procédure présente les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="bad3a-157">This sample procedure has the following requirements:</span></span>  
  
-   <span data-ttu-id="bad3a-158">Les instances de serveur doivent prendre en charge [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bad3a-158">The server instances must support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="bad3a-159">Pour plus d’informations, consultez [Conditions préalables requises, restrictions et recommandations pour les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="bad3a-159">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
-   <span data-ttu-id="bad3a-160">Deux exemples de bases de données, *MyDb1* et *MyDb2*, doivent exister sur l'instance de serveur qui hébergera le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="bad3a-160">Two sample databases, *MyDb1* and *MyDb2*, must exist on the server instance that will host the primary replica.</span></span> <span data-ttu-id="bad3a-161">Les exemples de code suivants créent et configurent ces deux bases de données et créent une sauvegarde complète de chacune d'elles.</span><span class="sxs-lookup"><span data-stu-id="bad3a-161">The following code examples create and configure these two databases and create a full backup of each.</span></span> <span data-ttu-id="bad3a-162">Exécutez ces exemples de code sur l'instance de serveur sur laquelle vous envisagez de créer l'exemple de groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bad3a-162">Execute these code examples on the server instance on which you intend to create the sample availability group.</span></span> <span data-ttu-id="bad3a-163">Cette instance de serveur hébergera le réplica principal initial de l'exemple de groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bad3a-163">This server instance will host the initial primary replica of the sample availability group.</span></span>  
  
    1.  <span data-ttu-id="bad3a-164">L'exemple [!INCLUDE[tsql](../../../includes/tsql-md.md)] suivant crée ces bases de données et les modifie pour utiliser le mode de récupération complète :</span><span class="sxs-lookup"><span data-stu-id="bad3a-164">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] example creates these databases and alters them to use the full recovery model:</span></span>  
  
        ```sql
        -- Create sample databases:  
        CREATE DATABASE MyDb1;  
        GO  
        ALTER DATABASE MyDb1 SET RECOVERY FULL;  
        GO  
  
        CREATE DATABASE MyDb2;  
        GO  
        ALTER DATABASE MyDb2 SET RECOVERY FULL;  
        GO  
        ```  
  
    2.  <span data-ttu-id="bad3a-165">L'exemple de code suivant crée une sauvegarde complète des bases de données *MyDb1* et *MyDb2*.</span><span class="sxs-lookup"><span data-stu-id="bad3a-165">The following code example creates a full database backup of *MyDb1* and *MyDb2*.</span></span> <span data-ttu-id="bad3a-166">Cet exemple de code utilise un partage de sauvegarde fictif, \\ \\ *FileServer* \\ *SQLbackups*.</span><span class="sxs-lookup"><span data-stu-id="bad3a-166">This code example uses a fictional backup share, \\\\*FILESERVER*\\*SQLbackups*.</span></span>  
  
        ```sql
        -- Backup sample databases:  
        BACKUP DATABASE MyDb1   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
            WITH FORMAT  
        GO  
  
        BACKUP DATABASE MyDb2   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
            WITH FORMAT  
        GO
        ```  
  
###  <a name="sample-configuration-procedure"></a><a name="SampleProcedure"></a> <span data-ttu-id="bad3a-167">Exemple de procédure de configuration</span><span class="sxs-lookup"><span data-stu-id="bad3a-167">Sample Configuration Procedure</span></span>  
 <span data-ttu-id="bad3a-168">Dans cet exemple de configuration, le réplica de disponibilité sera créé sur deux instances de serveur autonomes dont les comptes de service s'exécutent sous des domaines différents, mais approuvés (`DOMAIN1` et `DOMAIN2`).</span><span class="sxs-lookup"><span data-stu-id="bad3a-168">In this sample configuration, the availability replica will be created on two stand-alone server instances whose service accounts run under different, but trusted, domains (`DOMAIN1` and `DOMAIN2`).</span></span>  
  
 <span data-ttu-id="bad3a-169">Le tableau ci-dessous récapitule les valeurs utilisées dans cet exemple de configuration.</span><span class="sxs-lookup"><span data-stu-id="bad3a-169">The following table summarizes the values used in this sample configuration.</span></span>  
  
|<span data-ttu-id="bad3a-170">Rôle initial</span><span class="sxs-lookup"><span data-stu-id="bad3a-170">Initial role</span></span>|<span data-ttu-id="bad3a-171">Système</span><span class="sxs-lookup"><span data-stu-id="bad3a-171">System</span></span>|<span data-ttu-id="bad3a-172">Instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hôte</span><span class="sxs-lookup"><span data-stu-id="bad3a-172">Host [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Instance</span></span>|  
|------------------|------------|---------------------------------------------|  
|<span data-ttu-id="bad3a-173">Principal</span><span class="sxs-lookup"><span data-stu-id="bad3a-173">Primary</span></span>|`COMPUTER01`|`AgHostInstance`|  
|<span data-ttu-id="bad3a-174">Secondary</span><span class="sxs-lookup"><span data-stu-id="bad3a-174">Secondary</span></span>|`COMPUTER02`|<span data-ttu-id="bad3a-175">Instance par défaut.</span><span class="sxs-lookup"><span data-stu-id="bad3a-175">Default instance.</span></span>|  
  
1.  <span data-ttu-id="bad3a-176">Créez un point de terminaison de mise en miroir de bases de données nommé *dbm_endpoint* sur l’instance de serveur sur laquelle vous envisagez de créer le groupe de disponibilité (il s’agit d’une instance nommée `AgHostInstance` sur `COMPUTER01`).</span><span class="sxs-lookup"><span data-stu-id="bad3a-176">Create a database mirroring endpoint named *dbm_endpoint* on the server instance on which you plan to create the availability group (this is an instance named `AgHostInstance` on `COMPUTER01`).</span></span> <span data-ttu-id="bad3a-177">Ce point de terminaison utilise le port 7022.</span><span class="sxs-lookup"><span data-stu-id="bad3a-177">This endpoint uses port 7022.</span></span> <span data-ttu-id="bad3a-178">Notez que l'instance de serveur sur laquelle vous créez le groupe de disponibilité hébergera le réplica principal.</span><span class="sxs-lookup"><span data-stu-id="bad3a-178">Note that the server instance on which you create the availability group will host the primary replica.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the primary replica:  
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
2.  <span data-ttu-id="bad3a-179">Créez un point de terminaison *dbm_endpoint* sur l’instance de serveur qui hébergera le réplica secondaire (il s’agit de l’instance de serveur par défaut sur `COMPUTER02`).</span><span class="sxs-lookup"><span data-stu-id="bad3a-179">Create an endpoint *dbm_endpoint* on the server instance that will host the secondary replica (this is the default server instance on `COMPUTER02`).</span></span> <span data-ttu-id="bad3a-180">Ce point de terminaison utilise le port 5022.</span><span class="sxs-lookup"><span data-stu-id="bad3a-180">This endpoint uses port 5022.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the secondary replica:   
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=5022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
3.  > [!NOTE]  
    >  <span data-ttu-id="bad3a-181">Si les comptes de service des instances de serveur qui hébergeront vos réplicas de disponibilité s'exécutent sous le même compte de domaine, cette étape est inutile.</span><span class="sxs-lookup"><span data-stu-id="bad3a-181">If the service accounts of the server instances that are to host your availability replicas run under the same domain account this step is unnecessary.</span></span> <span data-ttu-id="bad3a-182">Ignorez-la et passez directement à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="bad3a-182">Skip it and go directly to the next step.</span></span>  
  
     <span data-ttu-id="bad3a-183">Si les comptes de service des instances de serveur s'exécutent sous des comptes utilisateur de domaine différents, sur chaque instance de serveur, créez une connexion pour l'autre instance de serveur et accordez cette autorisation de connexion pour accéder au point de terminaison de mise en miroir de bases de données local.</span><span class="sxs-lookup"><span data-stu-id="bad3a-183">If the service accounts of the server instances run under different domain users, on each server instance, create a login for the other server instance and grant this login permission to access the local database mirroring endpoint.</span></span>  
  
     <span data-ttu-id="bad3a-184">L'exemple de code suivant affiche les instructions [!INCLUDE[tsql](../../../includes/tsql-md.md)] pour créer une connexion et lui accorder l'autorisation sur un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="bad3a-184">The following code example shows the [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements for creating a login and granting it permission on an endpoint.</span></span> <span data-ttu-id="bad3a-185">Le compte de domaine de l’instance de serveur distant est représenté ici en tant que *nom_domaine*\\*nom_utilisateur*.</span><span class="sxs-lookup"><span data-stu-id="bad3a-185">The domain account of the remote server instance is represented here as *domain_name*\\*user_name*.</span></span>  
  
    ```sql
    -- If necessary, create a login for the service account, domain_name\user_name  
    -- of the server instance that will host the other replica:  
    USE master;  
    GO  
    CREATE LOGIN [domain_name\user_name] FROM WINDOWS;  
    GO  
    -- And Grant this login connect permissions on the endpoint:  
    GRANT CONNECT ON ENDPOINT::dbm_endpoint   
       TO [domain_name\user_name];  
    GO  
    ```  
  
4.  <span data-ttu-id="bad3a-186">Sur l'instance de serveur où résident les bases de données utilisateur, créez le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bad3a-186">On the server instance where the user databases reside, create the availability group.</span></span>  
  
     <span data-ttu-id="bad3a-187">L'exemple de code suivant crée un groupe de disponibilité nommé *MyAG* sur l'instance de serveur sur laquelle les exemples de bases de données, *MyDb1* et *MyDb2*, ont été créés.</span><span class="sxs-lookup"><span data-stu-id="bad3a-187">The following code example creates an availability group named *MyAG* on the server instance on which the sample databases, *MyDb1* and *MyDb2*, were created.</span></span> <span data-ttu-id="bad3a-188">L'instance de serveur local, `AgHostInstance`, sur *COMPUTER01* est spécifiée en premier.</span><span class="sxs-lookup"><span data-stu-id="bad3a-188">The local server instance, `AgHostInstance`, on *COMPUTER01* is specified first.</span></span> <span data-ttu-id="bad3a-189">Cette instance hébergera le réplica principal initial.</span><span class="sxs-lookup"><span data-stu-id="bad3a-189">This instance will host the initial primary replica.</span></span> <span data-ttu-id="bad3a-190">Une instance de serveur distant, l'instance de serveur par défaut sur *COMPUTER02*, est spécifiée pour héberger un réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="bad3a-190">A remote server instance, the default server instance on *COMPUTER02*, is specified to host a secondary replica.</span></span> <span data-ttu-id="bad3a-191">Les deux réplicas de disponibilité sont configurés de manière à utiliser le mode de validation asynchrone avec basculement manuel (pour les réplicas à validation asynchrone, le basculement manuel correspond à un basculement forcé entraînant une éventuelle perte de données).</span><span class="sxs-lookup"><span data-stu-id="bad3a-191">Both availability replica are configured to use asynchronous-commit mode with manual failover (for asynchronous-commit replicas manual failover means  forced failover with possible data loss).</span></span>  
  
    ```sql
    -- Create the availability group, MyAG:   
    CREATE AVAILABILITY GROUP MyAG   
       FOR   
          DATABASE MyDB1, MyDB2   
       REPLICA ON   
          'COMPUTER01\AgHostInstance' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',   
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             ),  
          'COMPUTER02' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );   
    GO  
    ```  
  
     <span data-ttu-id="bad3a-192">Pour obtenir d’autres exemples de code [!INCLUDE[tsql](../../../includes/tsql-md.md)] permettant de créer un groupe de disponibilité, consultez [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bad3a-192">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
5.  <span data-ttu-id="bad3a-193">Sur l'instance de serveur qui héberge le réplica secondaire, joignez le réplica secondaire au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bad3a-193">On the server instance that hosts the secondary replica, join the secondary replica to the availability group.</span></span>  
  
     <span data-ttu-id="bad3a-194">L'exemple de code suivant joint le réplica secondaire sur `COMPUTER02` au groupe de disponibilité `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="bad3a-194">The following code example joins the secondary replica on `COMPUTER02` to the `MyAG` availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join the secondary replica to the availability group:  
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    GO  
    ```  
  
6.  <span data-ttu-id="bad3a-195">Sur l'instance de serveur qui héberge le réplica secondaire, créez les bases de données secondaires.</span><span class="sxs-lookup"><span data-stu-id="bad3a-195">On the server instance that hosts the secondary replica, create the secondary databases.</span></span>  
  
     <span data-ttu-id="bad3a-196">L'exemple de code suivant crée les bases de données secondaires *MyDb1* et *MyDb2* en restaurant des sauvegardes de base de données à l'aide de l'option RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="bad3a-196">The following code example creates the *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- Restore database backups using the WITH NORECOVERY option:  
    RESTORE DATABASE MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NORECOVERY  
    GO  
  
    RESTORE DATABASE MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH NORECOVERY  
    GO
    ```  
  
7.  <span data-ttu-id="bad3a-197">Sur l'instance de serveur qui héberge le réplica principal, sauvegardez le journal des transactions sur chacune des bases de données primaires.</span><span class="sxs-lookup"><span data-stu-id="bad3a-197">On the server instance that hosts the primary replica, back up the transaction log on each of the primary databases.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="bad3a-198">Lorsque vous configurez un vrai groupe de disponibilité, nous vous recommandons, avant d'effectuer cette sauvegarde de fichier journal, d'interrompre les tâches de sauvegarde de fichier journal pour vos bases de données primaires jusqu'à ce que vous ayez joint les bases de données secondaires correspondantes au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bad3a-198">When you are configuring a real availability group, we recommend that, before taking this log backup, you suspend log backup tasks for your primary databases until you have joined the corresponding secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="bad3a-199">L'exemple de code suivant crée une sauvegarde du journal des transactions sur MyDb1 et MyDb2.</span><span class="sxs-lookup"><span data-stu-id="bad3a-199">The following code example creates a transaction log backup on MyDb1 and on MyDb2.</span></span>  
  
    ```sql
    -- On the server instance that hosts the primary replica,   
    -- Backup the transaction log on each primary database:  
    BACKUP LOG MyDb1   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NOFORMAT  
    GO  
  
    BACKUP LOG MyDb2   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITHNOFORMAT  
    GO
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="bad3a-200">En général, une sauvegarde de fichier journal doit être effectuée sur chaque base de données primaire, puis doit être restaurée sur la base de données secondaire correspondante (en utilisant l'option WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="bad3a-200">Typically, a log backup must be taken on each primary database and then restored on the corresponding secondary database (using WITH NORECOVERY).</span></span> <span data-ttu-id="bad3a-201">Toutefois, cette sauvegarde du fichier journal peut s'avérer superflue, si la base de données vient d'être créée et qu'aucune sauvegarde du fichier journal n'a été encore réalisée ou si le mode de récupération vient d'être modifié de SIMPLE à FULL.</span><span class="sxs-lookup"><span data-stu-id="bad3a-201">However, this log backup might be unnecessary if the database has just been created and no log backup has been taken yet or the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
8.  <span data-ttu-id="bad3a-202">Sur l'instance de serveur qui héberge le réplica secondaire, appliquez des sauvegardes de fichier journal aux bases de données secondaires.</span><span class="sxs-lookup"><span data-stu-id="bad3a-202">On the server instance that hosts the secondary replica, apply log backups to the secondary databases.</span></span>  
  
     <span data-ttu-id="bad3a-203">L'exemple de code suivant applique les sauvegardes aux bases de données secondaires *MyDb1* et *MyDb2* en restaurant des sauvegardes de base de données à l'aide de l'option RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="bad3a-203">The following code example applies backups to *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="bad3a-204">Lorsque vous préparez une base de données secondaire réelle, vous devez appliquer chaque sauvegarde de fichier journal effectuée depuis la sauvegarde de la base de données à partir de laquelle vous avez créé la base de données secondaire, en démarrant avec la plus ancienne et en utilisant toujours l'option RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="bad3a-204">When you are preparing a real secondary database, you need to apply every log backup taken since the database backup from which you created the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="bad3a-205">Bien sûr, si vous restaurez à la fois des sauvegardes de bases de données complètes et différentielles, vous devez uniquement appliquer les sauvegardes de fichier journal effectuées après la sauvegarde différentielle.</span><span class="sxs-lookup"><span data-stu-id="bad3a-205">Of course, if you restore both full and differential database backups, you would only need to apply the log backups taken after the differential backup.</span></span>  
  
    ```sql
    -- Restore the transaction log on each secondary database,  
    -- using the WITH NORECOVERY option:  
    RESTORE LOG MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    RESTORE LOG MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
9. <span data-ttu-id="bad3a-206">Sur l'instance de serveur qui héberge le réplica secondaire, joignez les nouvelles bases de données secondaires au groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bad3a-206">On the server instance that hosts the secondary replica, join the new secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="bad3a-207">L'exemple de code suivant, joint la base de données secondaire *MyDb1* , puis les bases de données secondaires *MyDb2* au groupe de disponibilité *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="bad3a-207">The following code example, joins the *MyDb1* secondary database and then the *MyDb2* secondary databases to the *MyAG* availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join each secondary database to the availability group:  
    ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
    GO  
  
    ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
    GO
    ```  
  
###  <a name="complete-code-example-for-sample-configuration-procedure"></a><a name="CompleteCodeExample"></a> <span data-ttu-id="bad3a-208">Exemple de code complet pour l'exemple de procédure de configuration</span><span class="sxs-lookup"><span data-stu-id="bad3a-208">Complete Code Example for Sample Configuration Procedure</span></span>  
 <span data-ttu-id="bad3a-209">L'exemple suivant fusionne les exemples de code de toutes les étapes de l'exemple de procédure configuration.</span><span class="sxs-lookup"><span data-stu-id="bad3a-209">The following example merges the code examples from all the steps of the sample configuration procedure.</span></span> <span data-ttu-id="bad3a-210">Le tableau suivant répertorie les valeurs d'espace réservé utilisées dans cet exemple de code.</span><span class="sxs-lookup"><span data-stu-id="bad3a-210">The following table summarized the placeholder values used in this code example.</span></span> <span data-ttu-id="bad3a-211">Pour plus d'informations sur les étapes de cet exemple de code, consultez [Conditions préalables requises pour l'utilisation de l'exemple de procédure de configuration](#PrerequisitesForExample) et [Exemple de procédure de configuration](#SampleProcedure), plus avant dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="bad3a-211">For more information about the steps in this code example, see [Prerequisites for Using the Sample Configuration Procedure](#PrerequisitesForExample) and [Sample Configuration Procedure](#SampleProcedure), earlier in this topic.</span></span>  
  
|<span data-ttu-id="bad3a-212">Espace réservé</span><span class="sxs-lookup"><span data-stu-id="bad3a-212">Placeholder</span></span>|<span data-ttu-id="bad3a-213">Description</span><span class="sxs-lookup"><span data-stu-id="bad3a-213">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="bad3a-214">\\\\*FILESERVER*\\*SQLbackups*</span><span class="sxs-lookup"><span data-stu-id="bad3a-214">\\\\*FILESERVER*\\*SQLbackups*</span></span>|<span data-ttu-id="bad3a-215">Partage de sauvegarde fictif.</span><span class="sxs-lookup"><span data-stu-id="bad3a-215">Fictional backup share.</span></span>|  
|<span data-ttu-id="bad3a-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span><span class="sxs-lookup"><span data-stu-id="bad3a-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span></span>|<span data-ttu-id="bad3a-217">Fichier de sauvegarde pour MyDb1.</span><span class="sxs-lookup"><span data-stu-id="bad3a-217">Backup file for MyDb1.</span></span>|  
|<span data-ttu-id="bad3a-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span><span class="sxs-lookup"><span data-stu-id="bad3a-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span></span>|<span data-ttu-id="bad3a-219">Fichier de sauvegarde pour MyDb2.</span><span class="sxs-lookup"><span data-stu-id="bad3a-219">Backup file for MyDb2.</span></span>|  
|<span data-ttu-id="bad3a-220">*7022*</span><span class="sxs-lookup"><span data-stu-id="bad3a-220">*7022*</span></span>|<span data-ttu-id="bad3a-221">Numéro de port affecté à chaque point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="bad3a-221">Port number assigned to each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="bad3a-222">*COMPUTER01\AgHostInstance*</span><span class="sxs-lookup"><span data-stu-id="bad3a-222">*COMPUTER01\AgHostInstance*</span></span>|<span data-ttu-id="bad3a-223">Instance de serveur qui héberge le réplica principal initial.</span><span class="sxs-lookup"><span data-stu-id="bad3a-223">Server instance that hosts the initial primary replica.</span></span>|  
|<span data-ttu-id="bad3a-224">*COMPUTER02*</span><span class="sxs-lookup"><span data-stu-id="bad3a-224">*COMPUTER02*</span></span>|<span data-ttu-id="bad3a-225">Instance de serveur qui héberge le réplica secondaire initial.</span><span class="sxs-lookup"><span data-stu-id="bad3a-225">Server instance that hosts the initial secondary replica.</span></span> <span data-ttu-id="bad3a-226">Il s'agit de l'instance de serveur par défaut sur `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="bad3a-226">This is the default server instance on `COMPUTER02`.</span></span>|  
|<span data-ttu-id="bad3a-227">*dbm_endpoint*</span><span class="sxs-lookup"><span data-stu-id="bad3a-227">*dbm_endpoint*</span></span>|<span data-ttu-id="bad3a-228">Nom spécifié pour chaque point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="bad3a-228">Name specified for each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="bad3a-229">*MyAG*</span><span class="sxs-lookup"><span data-stu-id="bad3a-229">*MyAG*</span></span>|<span data-ttu-id="bad3a-230">Nom de l'exemple de groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="bad3a-230">Name of sample availability group.</span></span>|  
|<span data-ttu-id="bad3a-231">*MyDb1*</span><span class="sxs-lookup"><span data-stu-id="bad3a-231">*MyDb1*</span></span>|<span data-ttu-id="bad3a-232">Nom du premier exemple de base de données.</span><span class="sxs-lookup"><span data-stu-id="bad3a-232">Name of first sample database.</span></span>|  
|<span data-ttu-id="bad3a-233">*MyDb2*</span><span class="sxs-lookup"><span data-stu-id="bad3a-233">*MyDb2*</span></span>|<span data-ttu-id="bad3a-234">Nom du deuxième exemple de base de données.</span><span class="sxs-lookup"><span data-stu-id="bad3a-234">Name of second sample database.</span></span>|  
|<span data-ttu-id="bad3a-235">*DOMAINE1\utilisateur1*</span><span class="sxs-lookup"><span data-stu-id="bad3a-235">*DOMAIN1\user1*</span></span>|<span data-ttu-id="bad3a-236">Compte de service de l'instance de serveur qui hébergera le réplica principal initial.</span><span class="sxs-lookup"><span data-stu-id="bad3a-236">Service account of the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="bad3a-237">*DOMAINE2\utilisateur2*</span><span class="sxs-lookup"><span data-stu-id="bad3a-237">*DOMAIN2\user2*</span></span>|<span data-ttu-id="bad3a-238">Compte de service de l'instance de serveur qui hébergera le réplica secondaire initial.</span><span class="sxs-lookup"><span data-stu-id="bad3a-238">Service account of the server instance that is to host the initial secondary replica.</span></span>|  
|<span data-ttu-id="bad3a-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span><span class="sxs-lookup"><span data-stu-id="bad3a-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span></span>|<span data-ttu-id="bad3a-240">URL du point de terminaison de l'instance AgHostInstance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur COMPUTER01.</span><span class="sxs-lookup"><span data-stu-id="bad3a-240">Endpoint URL of the AgHostInstance instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER01.</span></span>|  
|<span data-ttu-id="bad3a-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span><span class="sxs-lookup"><span data-stu-id="bad3a-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span></span>|<span data-ttu-id="bad3a-242">URL de point de terminaison de l'instance par défaut de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur COMPUTER02.</span><span class="sxs-lookup"><span data-stu-id="bad3a-242">Endpoint URL of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER02.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="bad3a-243">Pour obtenir d’autres exemples de code [!INCLUDE[tsql](../../../includes/tsql-md.md)] permettant de créer un groupe de disponibilité, consultez [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bad3a-243">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
```sql
-- on the server instance that will host the primary replica,   
-- create sample databases:  
CREATE DATABASE MyDb1;  
GO  
ALTER DATABASE MyDb1 SET RECOVERY FULL;  
GO  
  
CREATE DATABASE MyDb2;  
GO  
ALTER DATABASE MyDb2 SET RECOVERY FULL;  
GO  
  
-- Backup sample databases:  
BACKUP DATABASE MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FORMAT  
GO  
  
BACKUP DATABASE MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FORMAT  
GO  
  
-- Create the endpoint on the server instance that will host the primary replica:  
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- Create the endpoint on the server instance that will host the secondary replica:   
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the primary replica,   
-- create a login for the service account   
-- of the server instance that will host the secondary replica, DOMAIN2\user2,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
CREATE LOGIN [DOMAIN2\user2] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN2\user2];  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the secondary replica,  
-- create a login for the service account   
-- of the server instance that will host the primary replica, DOMAIN1\user1,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
  
CREATE LOGIN [DOMAIN1\user1] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN1\user1];  
GO  
  
-- On the server instance that will host the primary replica,   
-- create the availability group, MyAG:  
CREATE AVAILABILITY GROUP MyAG   
   FOR   
      DATABASE MyDB1, MyDB2   
   REPLICA ON   
      'COMPUTER01\AgHostInstance' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         ),  
      'COMPUTER02' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         );   
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join the secondary replica to the availability group:  
ALTER AVAILABILITY GROUP MyAG JOIN;  
GO  
  
-- Restore database backups onto this server instance, using RESTORE WITH NORECOVERY:  
RESTORE DATABASE MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NORECOVERY  
GO  
  
RESTORE DATABASE MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH NORECOVERY  
GO  
  
-- Back up the transaction log on each primary database:  
BACKUP LOG MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NOFORMAT  
GO  
  
BACKUP LOG MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITHNOFORMAT  
GO  
  
-- Restore the transaction log on each secondary database,  
-- using the WITH NORECOVERY option:  
RESTORE LOG MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FILE=1, NORECOVERY  
GO  
RESTORE LOG MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FILE=1, NORECOVERY  
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join each secondary database to the availability group:  
ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
GO  
  
ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
GO
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="bad3a-244">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="bad3a-244">Related Tasks</span></span>  
 <span data-ttu-id="bad3a-245">**Pour configurer les propriétés du groupe de disponibilité et du réplica**</span><span class="sxs-lookup"><span data-stu-id="bad3a-245">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="bad3a-246">Modifier le mode de disponibilité d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-246">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="bad3a-247">Modifier le mode de basculement d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-247">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="bad3a-248">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-248">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="bad3a-249">Configurer la stratégie de basculement flexible pour contrôler les conditions du basculement automatique (groupes de disponibilité AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="bad3a-249">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="bad3a-250">Spécifier l’URL de point de terminaison lors de l’ajout ou lors de la modification d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-250">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="bad3a-251">Configurer la sauvegarde sur des réplicas de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-251">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="bad3a-252">Configurer l’accès en lecture seule sur un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-252">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="bad3a-253">Configurer le routage en lecture seule pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-253">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="bad3a-254">Modifier le délai d’expiration de session pour un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-254">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="bad3a-255">**Pour terminer la configuration du groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="bad3a-255">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="bad3a-256">Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-256">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="bad3a-257">Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-257">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="bad3a-258">Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-258">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="bad3a-259">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-259">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="bad3a-260">**Autres méthodes de création d'un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="bad3a-260">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="bad3a-261">Utiliser l’Assistant Groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-261">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="bad3a-262">Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-262">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="bad3a-263">Créer un groupe de disponibilité &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-263">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
 <span data-ttu-id="bad3a-264">**Pour activer les groupes de disponibilité AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="bad3a-264">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="bad3a-265">Activer et désactiver les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-265">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="bad3a-266">**Pour configurer un point de terminaison pour la mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="bad3a-266">**To configure a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="bad3a-267">Créer un point de terminaison de mise en miroir de bases de données pour groupes de disponibilité AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-267">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="bad3a-268">Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-268">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="bad3a-269">Utiliser des certificats pour un point de terminaison de mise en miroir de bases de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-269">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
-   [<span data-ttu-id="bad3a-270">Spécifier l’URL de point de terminaison lors de l’ajout ou lors de la modification d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-270">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="bad3a-271">**Pour résoudre les problèmes de configuration des groupes de disponibilité AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="bad3a-271">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="bad3a-272">Résoudre les problèmes de configuration de groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bad3a-272">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="bad3a-273">Résoudre les problèmes liés à l’échec d’une opération d’ajout de fichier &#40;groupes de disponibilité AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-273">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="bad3a-274">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="bad3a-274">Related Content</span></span>  
  
-   <span data-ttu-id="bad3a-275">**Blogs :**</span><span class="sxs-lookup"><span data-stu-id="bad3a-275">**Blogs:**</span></span>  
  
     [<span data-ttu-id="bad3a-276">AlwaysON - HADRON Learning Series : Worker Pool Usage for HADRON Enabled Databases (en anglais)</span><span class="sxs-lookup"><span data-stu-id="bad3a-276">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="bad3a-277">Blogs de l'équipe de SQL Server AlwaysOn : Blog officiel de l'équipe de SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="bad3a-277">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="bad3a-278">Blogs des ingénieurs du Service clientèle et du Support technique de SQL Server</span><span class="sxs-lookup"><span data-stu-id="bad3a-278">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="bad3a-279">**Vidéos :**</span><span class="sxs-lookup"><span data-stu-id="bad3a-279">**Videos:**</span></span>  
  
     [<span data-ttu-id="bad3a-280">Microsoft SQL Server, nom de code « Denali », série AlwaysOn, Partie 1 : Présentation de la solution haute disponibilité de la prochaine génération</span><span class="sxs-lookup"><span data-stu-id="bad3a-280">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="bad3a-281">Microsoft SQL Server, nom de code « Denali », série AlwaysOn, Partie 2 : Génération d'une solution haute disponibilité critique à l'aide d'AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="bad3a-281">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="bad3a-282">**Livres blancs :**</span><span class="sxs-lookup"><span data-stu-id="bad3a-282">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="bad3a-283">Guide de solutions Microsoft SQL Server AlwaysOn pour la haute disponibilité et la récupération d'urgence</span><span class="sxs-lookup"><span data-stu-id="bad3a-283">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="bad3a-284">Livres blancs de Microsoft pour SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="bad3a-284">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="bad3a-285">Livres blancs de l'équipe de consultants clients de SQL Server</span><span class="sxs-lookup"><span data-stu-id="bad3a-285">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="bad3a-286">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bad3a-286">See Also</span></span>  
 <span data-ttu-id="bad3a-287">[Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bad3a-287">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="bad3a-288">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bad3a-288">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="bad3a-289">Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bad3a-289">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)   
