---
title: Configurer la réplication pour les groupes de disponibilité AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 4e001426-5ae0-4876-85ef-088d6e3fb61c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 916458d2d6b8fbba81940257ee85ffe014d1f12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697191"
---
# <a name="configure-replication-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="43824-102">Configurer la réplication pour les groupes de disponibilité Always On (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="43824-102">Configure Replication for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="43824-103">La configuration de la réplication [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et des groupes de disponibilité AlwaysOn implique sept étapes.</span><span class="sxs-lookup"><span data-stu-id="43824-103">Configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replication and AlwaysOn availability groups involves seven steps.</span></span> <span data-ttu-id="43824-104">Chaque étape est décrite plus en détail dans les sections qui suivent.</span><span class="sxs-lookup"><span data-stu-id="43824-104">Each step is described in more detail in the following sections.</span></span>  

##  <a name="1-configure-the-database-publications-and-subscriptions"></a><a name="step1"></a> <span data-ttu-id="43824-105">1. Configurez les publications et les abonnements de la base de données.</span><span class="sxs-lookup"><span data-stu-id="43824-105">1. Configure the Database Publications and Subscriptions</span></span>  

### <a name="configure-the-distributor"></a><span data-ttu-id="43824-106">Configurer le serveur de distribution</span><span class="sxs-lookup"><span data-stu-id="43824-106">Configure the distributor</span></span>
  
 <span data-ttu-id="43824-107">Le serveur de distribution ne doit être un hôte pour aucun des réplicas actuels (ou visés) du groupe de disponibilité dont la base de données de publication est (ou devient) membre.</span><span class="sxs-lookup"><span data-stu-id="43824-107">The distributor should not be a host for any of the current (or intended) replicas of the availability group that the publishing database is (or will become) a member of.</span></span>  
  
1.  <span data-ttu-id="43824-108">Configurez la distribution sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="43824-108">Configure distribution at the distributor.</span></span> <span data-ttu-id="43824-109">Si des procédures stockées sont utilisées pour la configuration, exécutez `sp_adddistributor`.</span><span class="sxs-lookup"><span data-stu-id="43824-109">If stored procedures are being used for configuration, run `sp_adddistributor`.</span></span> <span data-ttu-id="43824-110">Utilisez le *@password* paramètre pour identifier le mot de passe qui sera utilisé lorsqu’un serveur de publication distant se connecte au serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="43824-110">Use the *@password* parameter to identify the password that will be used when a remote publisher connects to the distributor.</span></span> <span data-ttu-id="43824-111">Le mot de passe est également nécessaire sur chaque serveur de publication distant lorsque le serveur de distribution distant est configuré.</span><span class="sxs-lookup"><span data-stu-id="43824-111">The password will also be needed at each remote publisher when the remote distributor is set up.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = '**Strong password for distributor**';  
    ```  
  
2.  <span data-ttu-id="43824-112">Créez la base de données de distribution sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="43824-112">Create the distribution database at the distributor.</span></span> <span data-ttu-id="43824-113">Si des procédures stockées sont utilisées pour la configuration, exécutez `sp_adddistributiondb`.</span><span class="sxs-lookup"><span data-stu-id="43824-113">If stored procedures are being used for configuration, run `sp_adddistributiondb`.</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sys.sp_adddistributiondb  
        @database = 'distribution',  
        @security_mode = 1;  
    ```  
  
3.  <span data-ttu-id="43824-114">Configurez le serveur de publication distant.</span><span class="sxs-lookup"><span data-stu-id="43824-114">Configure the remote publisher.</span></span> <span data-ttu-id="43824-115">Si des procédures stockées sont utilisées pour configurer le serveur de distribution, exécutez `sp_adddistpublisher`.</span><span class="sxs-lookup"><span data-stu-id="43824-115">If stored procedures are being used to configure the distributor, run `sp_adddistpublisher`.</span></span> <span data-ttu-id="43824-116">Le *@security_mode* paramètre est utilisé pour déterminer comment la procédure stockée de validation du serveur de publication exécutée à partir des agents de réplication se connecte au réplica principal actuel.</span><span class="sxs-lookup"><span data-stu-id="43824-116">The *@security_mode* parameter is used to determine how the publisher validation stored procedure that is run from the replication agents, connects to the current primary.</span></span> <span data-ttu-id="43824-117">Si la valeur est 1, l'authentification Windows est utilisée pour la connexion au principal actuel.</span><span class="sxs-lookup"><span data-stu-id="43824-117">If set to 1 Windows authentication is used to connect to the current primary.</span></span> <span data-ttu-id="43824-118">Si la valeur est 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] l’authentification est utilisée avec les *@login* valeurs et spécifiées *@password* .</span><span class="sxs-lookup"><span data-stu-id="43824-118">If set to 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authentication is used with the specified *@login* and *@password* values.</span></span> <span data-ttu-id="43824-119">La connexion et le mot de passe spécifiés doivent être valides sur chaque réplica secondaire pour que la procédure stockée de validation se connecte avec succès à ce réplica.</span><span class="sxs-lookup"><span data-stu-id="43824-119">The login and password specified must be valid at each secondary replica for the validation stored procedure to successfully connect to that replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43824-120">Si des agents de réplication modifiés s'exécutent sur un ordinateur autre que le serveur de distribution, l'utilisation de l'authentification Windows pour la connexion au principal requiert la configuration de l'authentification Kerberos pour la communication entre les ordinateurs hôtes de réplica.</span><span class="sxs-lookup"><span data-stu-id="43824-120">If any modified replication agents run on a computer other than the distributor, use of Windows authentication for the connection to the primary will require Kerberos authentication to be configured for the communication between the replica host computers.</span></span> <span data-ttu-id="43824-121">L'utilisation d'une connexion [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour la connexion au principal actuel ne requiert pas l'authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="43824-121">Use of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login for the connection to the current primary will not require Kerberos authentication.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistpublisher  
        @publisher = 'AGPrimaryReplicaHost',  
        @distribution_db = 'distribution',  
        @working_directory = '\\MyReplShare\WorkingDir',  
        @login = 'MyPubLogin',  
        @password = '**Strong password for publisher**';  
    ```  
  
 <span data-ttu-id="43824-122">Pour plus d’informations, consultez [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="43824-122">For more information, see [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span></span>  
  
### <a name="configure-the-publisher-at-the-original-publisher"></a><span data-ttu-id="43824-123">Configurer le serveur de publication sur le serveur de publication d'origine</span><span class="sxs-lookup"><span data-stu-id="43824-123">Configure the publisher at the original publisher</span></span>
  
1.  <span data-ttu-id="43824-124">Configurez la distribution à distance.</span><span class="sxs-lookup"><span data-stu-id="43824-124">Configure remote distribution.</span></span> <span data-ttu-id="43824-125">Si des procédures stockées sont utilisées pour configurer le serveur de publication, exécutez `sp_adddistributor`.</span><span class="sxs-lookup"><span data-stu-id="43824-125">If stored procedures are being used to configure the publisher, run `sp_adddistributor`.</span></span> <span data-ttu-id="43824-126">Spécifiez la même valeur pour que *@password* celle utilisée lorsque `sp_adddistrbutor` a été exécuté sur le serveur de distribution pour configurer la distribution.</span><span class="sxs-lookup"><span data-stu-id="43824-126">Specify the same value for *@password* as that used when `sp_adddistrbutor` was run at the distributor to set up distribution.</span></span>  
  
    ```sql
    exec sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = 'MyDistPass'  
    ```  
  
2.  <span data-ttu-id="43824-127">Activez la base de données pour la réplication.</span><span class="sxs-lookup"><span data-stu-id="43824-127">Enable the database for replication.</span></span> <span data-ttu-id="43824-128">Si des procédures stockées sont utilisées pour configurer le serveur de publication, exécutez `sp_replicationdboption`.</span><span class="sxs-lookup"><span data-stu-id="43824-128">If stored procedures are being used to configure the publisher, run `sp_replicationdboption`.</span></span> <span data-ttu-id="43824-129">Si la réplication transactionnelle et la réplication de fusion doivent être configurées pour la base de données, chacune doit être activée.</span><span class="sxs-lookup"><span data-stu-id="43824-129">If both transactional and merge replication are to be configured for the database, each must be enabled.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'true';  
  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'merge publish',  
        @value = 'true';  
    ```  
  
3.  <span data-ttu-id="43824-130">Créez la publication, les articles et les abonnements de réplication.</span><span class="sxs-lookup"><span data-stu-id="43824-130">Create the replication publication, articles, and subscriptions.</span></span> <span data-ttu-id="43824-131">Pour plus d'informations sur la configuration de la réplication, consultez « Publication de données et d'objets de base de données ».</span><span class="sxs-lookup"><span data-stu-id="43824-131">For more information about how to configure replication, see Publishing Data and Database objects.</span></span>  
  
##  <a name="2-configure-the-alwayson-availability-group"></a><a name="step2"></a><span data-ttu-id="43824-132">2. configurer le groupe de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="43824-132">2. Configure the AlwaysOn Availability Group</span></span>  
 <span data-ttu-id="43824-133">Dans le principal visé, créez le groupe de disponibilité avec la base de données publiée (ou à publier) en tant que base de données membre.</span><span class="sxs-lookup"><span data-stu-id="43824-133">At the intended primary, create the availability group with the published (or to be published) database as a member database.</span></span> <span data-ttu-id="43824-134">Si vous utilisez l'Assistant Groupe de disponibilité, vous pouvez autoriser l'Assistant à synchroniser pour la première fois les bases de données de réplica secondaire ou vous pouvez effectuer l'initialisation manuellement à l'aide des fonctionnalités de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="43824-134">If using the Availability Group Wizard, you can either allow the wizard to initially synchronize the secondary replica databases or you can perform the initialization manually by using backup and restore.</span></span>  
  
 <span data-ttu-id="43824-135">Créez un écouteur DNS pour le groupe de disponibilité qui sera utilisé par les agents de réplication pour la connexion au principal actuel.</span><span class="sxs-lookup"><span data-stu-id="43824-135">Create a DNS listener for the availability group that will be used by the replication agents to connect to the current primary.</span></span> <span data-ttu-id="43824-136">Le nom de l'écouteur spécifié sera utilisé comme cible de redirection pour la paire « serveur de publication d'origine/base de données publiée ».</span><span class="sxs-lookup"><span data-stu-id="43824-136">The listener name that is specified will be used as the target of redirection for the original publisher/published database pair.</span></span> <span data-ttu-id="43824-137">Par exemple, si vous utilisez DDL pour configurer le groupe de disponibilité, l'exemple de code suivant peut être utilisé pour spécifier un écouteur d'un groupe de disponibilité nommé `MyAG` :</span><span class="sxs-lookup"><span data-stu-id="43824-137">For example, if you are using DDL to configure the availability group, the following code example can be used to specify an availability group listener for an existing availability group named `MyAG`:</span></span>  
  
```sql
ALTER AVAILABILITY GROUP 'MyAG'   
    ADD LISTENER 'MyAGListenerName' (WITH IP (('10.120.19.155', '255.255.254.0')));  
```  
  
 <span data-ttu-id="43824-138">Pour plus d’informations, consultez [Création et configuration des groupes de disponibilité &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="43824-138">For more information, see [Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span></span>  
  
##  <a name="3-insure-that-all-of-the-secondary-replica-hosts-are-configured-for-replication"></a><a name="step3"></a><span data-ttu-id="43824-139">3. Vérifiez que tous les hôtes de réplica secondaire sont configurés pour la réplication</span><span class="sxs-lookup"><span data-stu-id="43824-139">3. Insure that all of the Secondary Replica Hosts are Configured for Replication</span></span>  
 <span data-ttu-id="43824-140">Pour chaque hôte de réplica secondaire, vérifiez que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a été configuré pour prendre en charge la réplication.</span><span class="sxs-lookup"><span data-stu-id="43824-140">At each secondary replica host, verify that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been configured to support replication.</span></span> <span data-ttu-id="43824-141">La requête suivante peut être exécutée sur chaque hôte de réplica secondaire pour déterminer si la réplication est installée :</span><span class="sxs-lookup"><span data-stu-id="43824-141">The following query can be run at each secondary replica host to determine whether replication is installed:</span></span>  
  
```sql
USE master;  
GO  
DECLARE @installed int;  
EXEC @installed = sys.sp_MS_replication_installed;  
SELECT @installed;  
```  
  
 <span data-ttu-id="43824-142">Si *@installed* a la valeur 0, la réplication doit être ajoutée à l' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span><span class="sxs-lookup"><span data-stu-id="43824-142">If *@installed* is 0, replication must be added to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span>  
  
##  <a name="4-configure-the-secondary-replica-hosts-as-replication-publishers"></a><a name="step4"></a> <span data-ttu-id="43824-143">4. Configurer les hôtes de réplica secondaire comme des serveurs de publication de réplication</span><span class="sxs-lookup"><span data-stu-id="43824-143">4. Configure the Secondary Replica Hosts as Replication Publishers</span></span>  
 <span data-ttu-id="43824-144">Un réplica secondaire ne peut pas servir de serveur de publication ou de de republication de réplication, mais la réplication doit être configurée de sorte que le serveur secondaire puisse prendre la suite après un basculement.</span><span class="sxs-lookup"><span data-stu-id="43824-144">A secondary replica cannot act as a replication publisher or republisher but replication must be configured so that the secondary can take over after a failover.</span></span> <span data-ttu-id="43824-145">Sur le serveur de distribution, configurez la distribution pour chaque hôte de réplica secondaire.</span><span class="sxs-lookup"><span data-stu-id="43824-145">At the distributor, configure distribution for each secondary replica host.</span></span> <span data-ttu-id="43824-146">Indiquez la même base de données de distribution et le même répertoire de travail spécifiés lorsque le serveur de publication d'origine a été ajouté au serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="43824-146">Specify the same distribution database and working directory as was specified when the original publisher was added to the distributor.</span></span> <span data-ttu-id="43824-147">Si vous utilisez des procédures stockées pour configurer la distribution, utilisez `sp_adddistpublisher` pour associer les serveurs de publication distants au serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="43824-147">If you are using stored procedures to configure distribution, use `sp_adddistpublisher` to associate the remote publishers with the distributor.</span></span> <span data-ttu-id="43824-148">Si *@login* et *@password* ont été utilisés pour le serveur de publication d’origine, spécifiez les mêmes valeurs pour chaque lorsque vous ajoutez les hôtes de réplica secondaire comme serveurs de publication.</span><span class="sxs-lookup"><span data-stu-id="43824-148">If *@login* and *@password* were used for the original publisher, specify the same values for each when you add the secondary replica hosts as publishers.</span></span>  
  
```sql
EXEC sys.sp_adddistpublisher  
    @publisher = 'AGSecondaryReplicaHost',  
    @distribution_db = 'distribution',  
    @working_directory = '\\MyReplShare\WorkingDir',  
    @login = 'MyPubLogin',  
    @password = '**Strong password for publisher**';  
```  
  
 <span data-ttu-id="43824-149">Pour chaque hôte de réplica secondaire, configurez la distribution.</span><span class="sxs-lookup"><span data-stu-id="43824-149">At each secondary replica host, configure distribution.</span></span> <span data-ttu-id="43824-150">Identifiez le serveur de distribution du serveur de publication d'origine comme serveur de distribution distant.</span><span class="sxs-lookup"><span data-stu-id="43824-150">Identify the distributor of the original publisher as the remote distributor.</span></span> <span data-ttu-id="43824-151">Utilisez le même mot de passe utilisé lorsque `sp_adddistributor` a été exécuté initialement sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="43824-151">Use the same password as that used when `sp_adddistributor` was run originally at the distributor.</span></span> <span data-ttu-id="43824-152">Si des procédures stockées sont utilisées pour configurer la distribution, le *@password* paramètre de `sp_adddistributor` est utilisé pour spécifier le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="43824-152">If stored procedures are being used to configure distribution, the *@password* parameter of `sp_adddistributor` is used to specify the password.</span></span>  
  
```sql
EXEC sp_adddistributor   
    @distributor = 'MyDistributor',  
    @password = '**Strong password for distributor**';  
```  
  
 <span data-ttu-id="43824-153">Pour chaque hôte de réplica secondaire, assurez-vous que les abonnés de transmission de type push des publications dans la base de données apparaissent en tant que serveurs liés.</span><span class="sxs-lookup"><span data-stu-id="43824-153">At each secondary replica host, make sure that the push subscribers of the database publications appear as linked servers.</span></span> <span data-ttu-id="43824-154">Si des procédures stockées sont utilisées pour configurer les serveurs de publication distants, utilisez `sp_addlinkedserver` pour ajouter aux serveurs de publication les abonnés (si absents) en tant que serveurs liés.</span><span class="sxs-lookup"><span data-stu-id="43824-154">If stored procedures are being used to configure the remote publishers, use `sp_addlinkedserver` to add the subscribers (if not already present) as linked servers to the publishers.</span></span>  
  
```sql
EXEC sys.sp_addlinkedserver   
    @server = 'MySubscriber';  
```  
  
##  <a name="5-redirect-the-original-publisher-to-the-ag-listener-name"></a><a name="step5"></a> <span data-ttu-id="43824-155">5. Rediriger le serveur de publication d'origine sur le nom de l'écouteur du groupe de disponibilité (AG)</span><span class="sxs-lookup"><span data-stu-id="43824-155">5. Redirect the Original Publisher to the AG Listener Name</span></span>  
 <span data-ttu-id="43824-156">Sur le serveur de distribution, dans la base de données de distribution, exécutez la procédure stockée `sp_redirect_publisher` pour associer le serveur de publication d'origine et la base de données publiée au nom de l'écouteur du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="43824-156">At the distributor, in the distribution database, run the stored procedure `sp_redirect_publisher` to associate the original publisher and the published database with the availability group listener name of the availability group.</span></span>  
  
```sql
USE distribution;  
GO  
EXEC sys.sp_redirect_publisher   
@original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = 'MyAGListenerName';  
```  
  
##  <a name="6-run-the-replication-validation-stored-procedure-to-verify-the-configuration"></a><a name="step6"></a> <span data-ttu-id="43824-157">6. Exécuter la procédure stockée de validation de réplication pour vérifier la configuration</span><span class="sxs-lookup"><span data-stu-id="43824-157">6. Run the Replication Validation Stored Procedure to Verify the Configuration</span></span>  
 <span data-ttu-id="43824-158">Sur le serveur de distribution, dans la base de données de distribution, exécutez la procédure stockée `sp_validate_replica_hosts_as_publishers` pour vérifier que tous les hôtes de réplica sont désormais configurés pour servir de serveurs de publication dans la base de données publiée.</span><span class="sxs-lookup"><span data-stu-id="43824-158">At the distributor, in the distribution database, run the stored procedure `sp_validate_replica_hosts_as_publishers` to verify that all replica hosts are now configured to serve as publishers for the published database.</span></span>  
  
```sql
USE distribution;  
GO  
DECLARE @redirected_publisher sysname;  
EXEC sys.sp_validate_replica_hosts_as_publishers  
    @original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = @redirected_publisher output;  
```  
  
 <span data-ttu-id="43824-159">La procédure stockée `sp_validate_replica_hosts_as_publishers` doit être exécutée à partir d'une connexion disposant d'autorisations suffisantes sur chaque hôte de réplica de groupe de disponibilité pour demander les informations sur le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="43824-159">The stored procedure `sp_validate_replica_hosts_as_publishers` should be run from a login with sufficient authorization at each availability group replica host to query for information about the availability group.</span></span> <span data-ttu-id="43824-160">Contrairement à `sp_validate_redirected_publisher` , il utilise les informations d’identification de l’appelant et n’utilise pas la connexion conservée dans msdb. dbo. MSdistpublishers pour se connecter aux réplicas du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="43824-160">Unlike `sp_validate_redirected_publisher`, it uses the credentials of the caller and does not use the login retained in msdb.dbo.MSdistpublishers to connect to the availability group replicas.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43824-161">`sp_validate_replica_hosts_as_publishers` échoue avec l'erreur suivante lors de la validation des hôtes de réplica secondaire qui n'autorisent pas l'accès en lecture, ou requièrent la spécification de l'intention de lecture.</span><span class="sxs-lookup"><span data-stu-id="43824-161">`sp_validate_replica_hosts_as_publishers` will fail with the following error when validating secondary replica hosts that do not allow read access, or require read intent to be specified.</span></span>  
>   
>  <span data-ttu-id="43824-162">Msg 21899, Niveau 11, État 1, Procédure `sp_hadr_verify_subscribers_at_publisher`, Ligne 109</span><span class="sxs-lookup"><span data-stu-id="43824-162">Msg 21899, Level 11, State 1, Procedure `sp_hadr_verify_subscribers_at_publisher`, Line 109</span></span>  
>   
>  <span data-ttu-id="43824-163">La requête au serveur de publication redirigé 'MyReplicaHostName' pour déterminer s’il y a des entrées sysserver pour les abonnés du serveur de publication d’origine 'MyOriginalPublisher' a échoué avec l’erreur '976', message d’erreur 'Erreur 976, Niveau 14, État 1, Message : La base de données cible, 'MyPublishedDB', est membre d’un groupe de disponibilité et n’est actuellement pas accessible pour les requêtes.</span><span class="sxs-lookup"><span data-stu-id="43824-163">The query at the redirected publisher 'MyReplicaHostName' to determine whether there were sysserver entries for the subscribers of the original publisher 'MyOriginalPublisher' failed with error '976', error message 'Error 976, Level 14, State 1, Message: The target database, 'MyPublishedDB', is participating in an availability group and is currently not accessible for queries.</span></span> <span data-ttu-id="43824-164">Le déplacement des données est alors suspendu ou le réplica de disponibilité n'est pas activé pour l'accès en lecture.</span><span class="sxs-lookup"><span data-stu-id="43824-164">Either data movement is suspended or the availability replica is not enabled for read access.</span></span> <span data-ttu-id="43824-165">Pour autoriser l'accès en lecture seule à cette base de données et à d'autres dans le groupe de disponibilité, activez l'accès en lecture sur un ou plusieurs réplicas de disponibilité secondaires dans le groupe.</span><span class="sxs-lookup"><span data-stu-id="43824-165">To allow read-only access to this and other databases in the availability group, enable read access to one or more secondary availability replicas in the group.</span></span>  <span data-ttu-id="43824-166">Pour plus d'informations, consultez l'instruction `ALTER AVAILABILITY GROUP` dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43824-166">For more information, see the `ALTER AVAILABILITY GROUP` statement in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.'.</span></span>  
>   
>  <span data-ttu-id="43824-167">Une ou plusieurs erreurs de validation de serveur de publication ont été rencontrées pour l'hôte de réplica 'MyReplicaHostName'.</span><span class="sxs-lookup"><span data-stu-id="43824-167">One or more publisher validation errors were encountered for replica host 'MyReplicaHostName'.</span></span>  
  
 <span data-ttu-id="43824-168">Ce comportement est normal.</span><span class="sxs-lookup"><span data-stu-id="43824-168">This is expected behavior.</span></span> <span data-ttu-id="43824-169">Vous devez vérifier la présence des entrées de serveur d’abonné sur ces hôtes de réplica secondaire en interrogeant les entrées sysserver directement sur l’hôte.</span><span class="sxs-lookup"><span data-stu-id="43824-169">You must verify the presence of the subscriber server entries at these secondary replica hosts by querying for the sysserver entries directly at the host.</span></span>  
  
##  <a name="7-add-the-original-publisher-to-replication-monitor"></a><a name="step7"></a> <span data-ttu-id="43824-170">7. Ajouter un serveur de publication d'origine au moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="43824-170">7. Add the Original Publisher to Replication Monitor</span></span>  
 <span data-ttu-id="43824-171">Pour chaque réplica de groupe de disponibilité, ajoutez le serveur de publication d'origine au moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="43824-171">At each availability group replica, add the original publisher to Replication Monitor.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="43824-172">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="43824-172">Related Tasks</span></span>  
 <span data-ttu-id="43824-173">**Réplication**</span><span class="sxs-lookup"><span data-stu-id="43824-173">**Replication**</span></span>  
  
-   [<span data-ttu-id="43824-174">Maintenance d’une base de données de publication AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-174">Maintaining an AlwaysOn Publication Database &#40;SQL Server&#41;</span></span>](maintaining-an-always-on-publication-database-sql-server.md)  
  
-   [<span data-ttu-id="43824-175">Réplication, Change Tracking, capture de données modifiées et groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-175">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="43824-176">FAQ sur l’administration de la réplication</span><span class="sxs-lookup"><span data-stu-id="43824-176">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
 <span data-ttu-id="43824-177">**Pour créer et configurer un groupe de disponibilité**</span><span class="sxs-lookup"><span data-stu-id="43824-177">**To create and configure an availability group**</span></span>  
  
-   [<span data-ttu-id="43824-178">Utiliser l’Assistant Groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-178">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="43824-179">Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-179">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="43824-180">Créer un groupe de disponibilité &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-180">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="43824-181">Créer un groupe de disponibilité &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-181">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="43824-182">Spécifier l’URL de point de terminaison lors de l’ajout ou lors de la modification d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-182">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="43824-183">Créer un point de terminaison de mise en miroir de bases de données pour groupes de disponibilité AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-183">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="43824-184">Joindre un réplica secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-184">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="43824-185">Préparer manuellement une base de données secondaire pour un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-185">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="43824-186">Joindre une base de données secondaire à un groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-186">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="43824-187">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43824-187">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="43824-188">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43824-188">See Also</span></span>  
 <span data-ttu-id="43824-189">[Conditions préalables requises, restrictions et recommandations pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="43824-189">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="43824-190">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="43824-190">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="43824-191">[Groupes de disponibilité AlwaysOn : interopérabilité (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="43824-191">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="43824-192">Réplication SQL Server</span><span class="sxs-lookup"><span data-stu-id="43824-192">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
