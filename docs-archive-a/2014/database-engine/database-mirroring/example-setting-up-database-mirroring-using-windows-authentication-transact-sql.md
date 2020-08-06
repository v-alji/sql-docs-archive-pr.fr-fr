---
title: 'Exemple : configuration de la mise en miroir de bases de données à l’aide de l’authentification Windows (Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- Windows authentication [SQL Server]
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: 35800769-aede-4aac-b077-0e0e487e302f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95df855e8e41c5937aae02884c71792537eb2bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601647"
---
# <a name="example-setting-up-database-mirroring-using-windows-authentication-transact-sql"></a><span data-ttu-id="4cec6-102">Exemple : configurer la mise en miroir de bases de données à l'aide de l'authentification Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4cec6-102">Example: Setting Up Database Mirroring Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="4cec6-103">Cet exemple illustre toutes les étapes nécessaires à la création d'une session de mise en miroir de base de données avec un serveur témoin à l'aide de l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="4cec6-103">This example shows all the stages required to create a database mirroring session with a witness using Windows Authentication.</span></span> <span data-ttu-id="4cec6-104">Les exemples de cette rubrique utilisent [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cec6-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4cec6-105">Notez qu'au lieu d'utiliser les étapes [!INCLUDE[tsql](../../includes/tsql-md.md)], vous pouvez utiliser l'Assistant Sécurité de mise en miroir de bases de données pour configurer la mise en miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="4cec6-105">Note that as an alternative to using [!INCLUDE[tsql](../../includes/tsql-md.md)] steps, you can use the Configure Database Mirroring Security Wizard for database mirroring setup.</span></span> <span data-ttu-id="4cec6-106">Pour plus d’informations, consultez [Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="4cec6-106">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="4cec6-107">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="4cec6-107">Prerequisite</span></span>  
 <span data-ttu-id="4cec6-108">L'exemple utilise la base de données d'exemple **AdventureWorks** , qui emploie par défaut le mode de récupération simple.</span><span class="sxs-lookup"><span data-stu-id="4cec6-108">The example uses the **AdventureWorks** sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="4cec6-109">Pour utiliser la mise en miroir avec cette base de données, vous devez la modifier pour qu'elle utilise le mode de restauration complète.</span><span class="sxs-lookup"><span data-stu-id="4cec6-109">To use database mirroring with this database, you must alter it to use the full recovery model.</span></span> <span data-ttu-id="4cec6-110">Pour obtenir ce résultat dans [!INCLUDE[tsql](../../includes/tsql-md.md)], utilisez l'instruction ALTER DATABASE comme suit :</span><span class="sxs-lookup"><span data-stu-id="4cec6-110">To do this in [!INCLUDE[tsql](../../includes/tsql-md.md)], use the ALTER DATABASE statement, as follows:</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE AdventureWorks   
SET RECOVERY FULL;  
GO  
```  
  
 <span data-ttu-id="4cec6-111">Pour plus d’informations sur la modification du modèle de récupération dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], consultez [Afficher ou modifier le mode de récupération d’une base de données &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4cec6-111">For information on changing the recovery model in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="4cec6-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4cec6-112">Permissions</span></span>  
 <span data-ttu-id="4cec6-113">Nécessite l'autorisation ALTER sur la base de données et l'autorisation CREATE ENDPOINT, ou l'appartenance au rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4cec6-113">Requires ALTER permission on the database and CREATE ENDPOINT permission, or membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cec6-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="4cec6-114">Example</span></span>  
 <span data-ttu-id="4cec6-115">Dans cet exemple, les deux partenaires et le témoin sont les instances de serveur par défaut réparties sur trois systèmes informatiques.</span><span class="sxs-lookup"><span data-stu-id="4cec6-115">In this example, the two partners and the witness are the default server instances on three computer systems.</span></span> <span data-ttu-id="4cec6-116">Les trois instances de serveur utilisent le même domaine Windows, mais le compte d'utilisateur (utilisé comme compte de service au démarrage) est différent pour l'instance du témoin de l'exemple.</span><span class="sxs-lookup"><span data-stu-id="4cec6-116">The three server instances run the same Windows domain, but the user account (used as the startup service account) is different for the example's witness server instance.</span></span>  
  
 <span data-ttu-id="4cec6-117">Le tableau ci-dessous récapitule les valeurs utilisées dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="4cec6-117">The following table summarizes the values used in this example.</span></span>  
  
|<span data-ttu-id="4cec6-118">Rôle initial de la mise en miroir</span><span class="sxs-lookup"><span data-stu-id="4cec6-118">Initial mirroring role</span></span>|<span data-ttu-id="4cec6-119">Système hôte</span><span class="sxs-lookup"><span data-stu-id="4cec6-119">Host system</span></span>|<span data-ttu-id="4cec6-120">Compte d’utilisateur de domaine</span><span class="sxs-lookup"><span data-stu-id="4cec6-120">Domain user account</span></span>|  
|----------------------------|-----------------|-------------------------|  
|<span data-ttu-id="4cec6-121">Principal</span><span class="sxs-lookup"><span data-stu-id="4cec6-121">Principal</span></span>|<span data-ttu-id="4cec6-122">PARTNERHOST1</span><span class="sxs-lookup"><span data-stu-id="4cec6-122">PARTNERHOST1</span></span>|<span data-ttu-id="4cec6-123">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="4cec6-123">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="4cec6-124">Miroir</span><span class="sxs-lookup"><span data-stu-id="4cec6-124">Mirror</span></span>|<span data-ttu-id="4cec6-125">PARTNERHOST5</span><span class="sxs-lookup"><span data-stu-id="4cec6-125">PARTNERHOST5</span></span>|<span data-ttu-id="4cec6-126">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="4cec6-126">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="4cec6-127">Témoin</span><span class="sxs-lookup"><span data-stu-id="4cec6-127">Witness</span></span>|<span data-ttu-id="4cec6-128">WITNESSHOST4</span><span class="sxs-lookup"><span data-stu-id="4cec6-128">WITNESSHOST4</span></span>|<span data-ttu-id="4cec6-129">*\<Somedomain>\\<witnessuser\>*</span><span class="sxs-lookup"><span data-stu-id="4cec6-129">*\<Somedomain>\\<witnessuser\>*</span></span>|  
  
1.  <span data-ttu-id="4cec6-130">Créez un point de terminaison dans l'instance du serveur principal (instance par défaut sur PARTNERHOST1).</span><span class="sxs-lookup"><span data-stu-id="4cec6-130">Create an endpoint on the principal server instance (default instance on PARTNERHOST1).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=PARTNER)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    -- Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
2.  <span data-ttu-id="4cec6-131">Créez un point de terminaison dans l'instance du serveur miroir (instance par défaut sur PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="4cec6-131">Create an endpoint on the mirror server instance (default instance on PARTNERHOST5).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="4cec6-132">Créez un point de terminaison dans l'instance du serveur témoin (instance par défaut sur WITNESSHOST4).</span><span class="sxs-lookup"><span data-stu-id="4cec6-132">Create an endpoint on the witness server instance (default instance on WITNESSHOST4).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    --Create a login for the partner server instances,  
    --which are both running as Mydomain\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [Mydomain\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
4.  <span data-ttu-id="4cec6-133">Création de la base de données miroir</span><span class="sxs-lookup"><span data-stu-id="4cec6-133">Create the mirror database.</span></span> <span data-ttu-id="4cec6-134">Pour plus d’informations, consultez [Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4cec6-134">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="4cec6-135">Dans l'instance du serveur miroir sur PARTNERHOST5, définissez l'instance de serveur sur PARTNERHOST1 comme partenaire (ce qui en fait l'instance initiale du serveur principal).</span><span class="sxs-lookup"><span data-stu-id="4cec6-135">On the mirror server instance on PARTNERHOST5, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1.COM:7022'  
    GO  
    ```  
  
6.  <span data-ttu-id="4cec6-136">Dans l'instance du serveur principal sur PARTNERHOST1, définissez l'instance de serveur sur PARTNERHOST5 comme partenaire (ce qui en fait l'instance initiale du serveur miroir).</span><span class="sxs-lookup"><span data-stu-id="4cec6-136">On the principal server instance on PARTNERHOST1, set the server instance on PARTNERHOST5 as the partner (making it the initial mirror server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5.COM:7022'  
    GO  
    ```  
  
7.  <span data-ttu-id="4cec6-137">Sur le serveur principal, définissez le témoin (qui se trouve sur WITNESSHOST4).</span><span class="sxs-lookup"><span data-stu-id="4cec6-137">On the principal server, set the witness (which is on WITNESSHOST4).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4.COM:7022'  
    GO  
    ```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4cec6-138">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="4cec6-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4cec6-139">Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4cec6-139">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="4cec6-140">Démarrer l’Assistant Configuration de la sécurité de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4cec6-140">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
-   [<span data-ttu-id="4cec6-141">Configurer une base de données miroir pour utiliser la propriété Trustworthy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4cec6-141">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
-   [<span data-ttu-id="4cec6-142">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4cec6-142">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="4cec6-143">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4cec6-143">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="4cec6-144">Exemple : Configuration de la mise en miroir de bases de données à l’aide de certificats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4cec6-144">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="4cec6-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4cec6-145">See Also</span></span>  
 <span data-ttu-id="4cec6-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cec6-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="4cec6-147">[Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4cec6-147">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="4cec6-148">[Sécurité de transport pour la mise en miroir de bases de données et les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="4cec6-148">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="4cec6-149">[Gérer les métadonnées durant la mise à disposition d’une base de données sur une autre instance de serveur &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span><span class="sxs-lookup"><span data-stu-id="4cec6-149">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span></span>  
 [<span data-ttu-id="4cec6-150">Centre de sécurité pour le moteur de base de données SQL Server et Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="4cec6-150">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
