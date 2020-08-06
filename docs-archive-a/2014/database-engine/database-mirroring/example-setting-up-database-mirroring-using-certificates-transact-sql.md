---
title: 'Exemple : configuration de la mise en miroir de bases de données à l’aide de certificats (Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: df489ecd-deee-465c-a26a-6d1bef6d7b66
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea87e2de984107c5a0fda6eb2629ee5cfd197841
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709931"
---
# <a name="example-setting-up-database-mirroring-using-certificates-transact-sql"></a><span data-ttu-id="3eee8-102">Exemple : Configuration de la mise en miroir de bases de données à l’aide de certificats (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3eee8-102">Example: Setting Up Database Mirroring Using Certificates (Transact-SQL)</span></span>
  <span data-ttu-id="3eee8-103">Cet exemple décrit toutes les étapes de création d'une session de mise en miroir de bases de données à l'aide de l'authentification basée sur les certificats.</span><span class="sxs-lookup"><span data-stu-id="3eee8-103">This example shows all the stages required to create a database mirroring session using certificate-based authentication.</span></span> <span data-ttu-id="3eee8-104">Les exemples de cette rubrique utilisent [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3eee8-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3eee8-105">À moins que vous ne puissiez garantir la sécurité de votre réseau, il est recommandé d'utiliser le chiffrement pour les connexions de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="3eee8-105">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="3eee8-106">Lors de la copie d'un certificat sur un autre système, utilisez une méthode de copie sécurisée.</span><span class="sxs-lookup"><span data-stu-id="3eee8-106">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="3eee8-107">Veillez particulièrement à sécuriser tous vos certificats.</span><span class="sxs-lookup"><span data-stu-id="3eee8-107">Be extremely careful to keep all of your certificates secure.</span></span>  
  
##  <a name="example"></a><a name="ExampleH2"></a> <span data-ttu-id="3eee8-108">Exemple</span><span class="sxs-lookup"><span data-stu-id="3eee8-108">Example</span></span>  
 <span data-ttu-id="3eee8-109">L'exemple suivant illustre ce qui doit être fait sur un serveur partenaire qui réside sur HOST_A.</span><span class="sxs-lookup"><span data-stu-id="3eee8-109">The following example demonstrates what must be done on one partner that resides on HOST_A.</span></span> <span data-ttu-id="3eee8-110">Dans cet exemple, les deux serveurs partenaires sont les instances de serveur par défaut réparties sur trois systèmes informatiques.</span><span class="sxs-lookup"><span data-stu-id="3eee8-110">In this example, the two partners are the default server instances on three computer systems.</span></span> <span data-ttu-id="3eee8-111">Les deux instances de serveur sont exécutées dans des domaines Windows non approuvés, par conséquent l'authentification basée sur les certificats est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3eee8-111">The two server instances run in nontrusted Windows domains, so certificate-based authentication is required.</span></span>  
  
 <span data-ttu-id="3eee8-112">Le rôle principal initial est occupé par HOST_A, et le rôle miroir par HOST_B.</span><span class="sxs-lookup"><span data-stu-id="3eee8-112">The initial principal role is taken by HOST_A, and the mirror role is taken by HOST_B.</span></span>  
  
 <span data-ttu-id="3eee8-113">La configuration de la mise en miroir de bases de données à l’aide de certificats implique quatre étapes générales, dont les première, deuxième et quatrième sont illustrées par cet exemple.</span><span class="sxs-lookup"><span data-stu-id="3eee8-113">Setting up database mirroring using certificates involves four general stages, of which three stages-1, 2, and 4-are demonstrated by this example.</span></span> <span data-ttu-id="3eee8-114">Ces étapes sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3eee8-114">These stages are as follows:</span></span>  
  
1.  [<span data-ttu-id="3eee8-115">Configuration des connexions sortantes</span><span class="sxs-lookup"><span data-stu-id="3eee8-115">Configuring Outbound Connections</span></span>](#ConfiguringOutboundConnections)  
  
     <span data-ttu-id="3eee8-116">Cet exemple montre les étapes nécessaires à la :</span><span class="sxs-lookup"><span data-stu-id="3eee8-116">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="3eee8-117">configuration d'Host_A pour les connexions sortantes ;</span><span class="sxs-lookup"><span data-stu-id="3eee8-117">Configuring Host_A for outbound connections.</span></span>  
  
    2.  <span data-ttu-id="3eee8-118">configuration d'Host_B pour les connexions sortantes.</span><span class="sxs-lookup"><span data-stu-id="3eee8-118">Configuring Host_B for outbound connections.</span></span>  
  
     <span data-ttu-id="3eee8-119">Pour plus d’informations sur cette étape de la configuration de la mise en miroir de bases de données, consultez [Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="3eee8-119">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
2.  [<span data-ttu-id="3eee8-120">Configuration des connexions entrantes</span><span class="sxs-lookup"><span data-stu-id="3eee8-120">Configuring Inbound Connections</span></span>](#ConfigureInboundConnections)  
  
     <span data-ttu-id="3eee8-121">Cet exemple montre les étapes nécessaires à la :</span><span class="sxs-lookup"><span data-stu-id="3eee8-121">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="3eee8-122">configuration d'Host_A pour les connexions entrantes ;</span><span class="sxs-lookup"><span data-stu-id="3eee8-122">Configuring Host_A for inbound connections.</span></span>  
  
    2.  <span data-ttu-id="3eee8-123">configuration d'Host_B pour les connexions entrantes.</span><span class="sxs-lookup"><span data-stu-id="3eee8-123">Configuring Host_B for inbound connections.</span></span>  
  
     <span data-ttu-id="3eee8-124">Pour plus d’informations sur cette étape de la configuration de la mise en miroir de bases de données, consultez [Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="3eee8-124">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
3.  <span data-ttu-id="3eee8-125">Création de la base de données miroir</span><span class="sxs-lookup"><span data-stu-id="3eee8-125">Creating the Mirror Database</span></span>  
  
     <span data-ttu-id="3eee8-126">Pour plus d’informations sur la création d’une base de données miroir, consultez [Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3eee8-126">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
4.  [<span data-ttu-id="3eee8-127">Configuration des serveurs partenaires de mise en miroir</span><span class="sxs-lookup"><span data-stu-id="3eee8-127">Configuring the Mirroring Partners</span></span>](#ConfigureMirroringPartners)  
  
###  <a name="configuring-outbound-connections"></a><a name="ConfiguringOutboundConnections"></a> <span data-ttu-id="3eee8-128">Configuration des connexions sortantes</span><span class="sxs-lookup"><span data-stu-id="3eee8-128">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="3eee8-129">**Pour configurer Host_A pour les connexions sortantes**</span><span class="sxs-lookup"><span data-stu-id="3eee8-129">**To configure Host_A for outbound connections**</span></span>  
  
1.  <span data-ttu-id="3eee8-130">Dans la base de données master, créez la clé principale de base de données, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3eee8-130">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
2.  <span data-ttu-id="3eee8-131">Activez un certificat pour cette instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="3eee8-131">Make a certificate for this server instance.</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate';  
    GO  
    ```  
  
3.  <span data-ttu-id="3eee8-132">Créez un point de terminaison de mise en miroir pour l'instance de serveur à l'aide du certificat.</span><span class="sxs-lookup"><span data-stu-id="3eee8-132">Create a mirroring endpoint for server instance using the certificate.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_A_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
4.  <span data-ttu-id="3eee8-133">Sauvegardez le certificat HOST_A, et copiez-le sur l'autre système, HOST_B.</span><span class="sxs-lookup"><span data-stu-id="3eee8-133">Back up the HOST_A certificate, and copy it to other system, HOST_B.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
5.  <span data-ttu-id="3eee8-134">Au moyen d'une méthode sécurisée de copie quelconque, copiez C:\HOST_A_cert.cer sur HOST_B.</span><span class="sxs-lookup"><span data-stu-id="3eee8-134">Using any secure copy method, copy C:\HOST_A_cert.cer to HOST_B.</span></span>  
  
 <span data-ttu-id="3eee8-135">**Pour configurer Host_B pour les connexions sortantes**</span><span class="sxs-lookup"><span data-stu-id="3eee8-135">**To configure Host_B for outbound connections**</span></span>  
  
1.  <span data-ttu-id="3eee8-136">Dans la base de données master, créez la clé principale de base de données, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3eee8-136">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
    GO  
    ```  
  
2.  <span data-ttu-id="3eee8-137">Activez un certificat sur l'instance de serveur HOST_B.</span><span class="sxs-lookup"><span data-stu-id="3eee8-137">Make a certificate on the HOST_B server instance.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert   
       WITH SUBJECT = 'HOST_B certificate for database mirroring';  
    GO  
    ```  
  
3.  <span data-ttu-id="3eee8-138">Créez un point de terminaison de mise en miroir pour l'instance de serveur sur HOST_B.</span><span class="sxs-lookup"><span data-stu-id="3eee8-138">Create a mirroring endpoint for the server instance on HOST_B.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_B_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
4.  <span data-ttu-id="3eee8-139">Sauvegardez le certificat HOST_B.</span><span class="sxs-lookup"><span data-stu-id="3eee8-139">Back up HOST_B certificate.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
    GO   
    ```  
  
5.  <span data-ttu-id="3eee8-140">Au moyen d'une méthode sécurisée de copie quelconque, copiez C:\HOST_B_cert.cer sur HOST_A.</span><span class="sxs-lookup"><span data-stu-id="3eee8-140">Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.</span></span>  
  
 <span data-ttu-id="3eee8-141">Pour plus d’informations, consultez [Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="3eee8-141">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
###  <a name="configuring-inbound-connections"></a><a name="ConfigureInboundConnections"></a> <span data-ttu-id="3eee8-142">Configuration des connexions entrantes</span><span class="sxs-lookup"><span data-stu-id="3eee8-142">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="3eee8-143">**Pour configurer Host_A pour les connexions entrantes**</span><span class="sxs-lookup"><span data-stu-id="3eee8-143">**To configure Host_A for inbound connections**</span></span>  
  
1.  <span data-ttu-id="3eee8-144">Créez une connexion sur HOST_A pour HOST_B.</span><span class="sxs-lookup"><span data-stu-id="3eee8-144">Create a login on HOST_A for HOST_B.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_B_login WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
2.  <span data-ttu-id="3eee8-145">--Créez un utilisateur pour cette connexion.</span><span class="sxs-lookup"><span data-stu-id="3eee8-145">--Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="3eee8-146">--Associez le certificat à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3eee8-146">--Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="3eee8-147">Accordez l'autorisation CONNECT à la connexion pour le point de terminaison de mise en miroir distant.</span><span class="sxs-lookup"><span data-stu-id="3eee8-147">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
 <span data-ttu-id="3eee8-148">**Pour configurer Host_B pour les connexions entrantes**</span><span class="sxs-lookup"><span data-stu-id="3eee8-148">**To configure Host_B for inbound connections**</span></span>  
  
1.  <span data-ttu-id="3eee8-149">Créez une connexion sur HOST_B pour HOST_A.</span><span class="sxs-lookup"><span data-stu-id="3eee8-149">Create a login on HOST_B for HOST_A.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_A_login WITH PASSWORD = '=Sample#2_Strong_Password2';  
    GO  
    ```  
  
2.  <span data-ttu-id="3eee8-150">Créez un utilisateur pour cette connexion.</span><span class="sxs-lookup"><span data-stu-id="3eee8-150">Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="3eee8-151">Associez le certificat à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3eee8-151">Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_A_cert  
       AUTHORIZATION HOST_A_user  
       FROM FILE = 'C:\HOST_A_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="3eee8-152">Accordez l'autorisation CONNECT à la connexion pour le point de terminaison de mise en miroir distant.</span><span class="sxs-lookup"><span data-stu-id="3eee8-152">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_A_login];  
    GO  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3eee8-153">Si vous envisagez d'utiliser le mode haute sécurité avec basculement automatique, vous devez répéter les mêmes étapes pour configurer le témoin pour les connexions sortantes et entrantes.</span><span class="sxs-lookup"><span data-stu-id="3eee8-153">If you intend to run in high-safety mode with automatic failover, you must repeat the same setup steps to configure the witness for outbound and inbound connections.</span></span> <span data-ttu-id="3eee8-154">La configuration des connexions entrantes lorsqu'un serveur témoin est impliqué suppose de configurer les connexions et les utilisateurs du serveur témoin sur les deux serveurs partenaires, ainsi que les connexions et les utilisateurs des deux serveurs partenaires sur le serveur témoin.</span><span class="sxs-lookup"><span data-stu-id="3eee8-154">Setting up the inbound connections when a witness is involved requires that you set up logins and users for the witness on both of the partners and for both partners on the witness.</span></span>  
  
 <span data-ttu-id="3eee8-155">Pour plus d’informations, consultez [Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="3eee8-155">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
### <a name="creating-the-mirror-database"></a><span data-ttu-id="3eee8-156">Création de la base de données miroir</span><span class="sxs-lookup"><span data-stu-id="3eee8-156">Creating the Mirror Database</span></span>  
 <span data-ttu-id="3eee8-157">Pour plus d’informations sur la création d’une base de données miroir, consultez [Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3eee8-157">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
###  <a name="configuring-the-mirroring-partners"></a><a name="ConfigureMirroringPartners"></a> <span data-ttu-id="3eee8-158">Configuration des serveurs partenaires de mise en miroir</span><span class="sxs-lookup"><span data-stu-id="3eee8-158">Configuring the Mirroring Partners</span></span>  
  
1.  <span data-ttu-id="3eee8-159">Sur l'instance de serveur miroir de HOST_B, définissez l'instance de serveur de HOST_A en tant que serveur partenaire (en faisant d'elle l'instance initiale de serveur principal).</span><span class="sxs-lookup"><span data-stu-id="3eee8-159">On the mirror server instance on HOST_B, set the server instance on HOST_A as the partner (making it the initial principal server instance).</span></span> <span data-ttu-id="3eee8-160">Remplacez une adresse réseau valide par `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span><span class="sxs-lookup"><span data-stu-id="3eee8-160">Substitute a valid network address for `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span></span> <span data-ttu-id="3eee8-161">Pour plus d’informations, consultez [Spécifier une adresse réseau de serveur &#40;mise en miroir de bases de données&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="3eee8-161">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
    ```  
    --At HOST_B, set server instance on HOST_A as partner (principal server):  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_A.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
2.  <span data-ttu-id="3eee8-162">Sur l'instance de serveur principal de HOST_A, définissez l'instance de serveur de HOST_B en tant que serveur partenaire (en faisant d'elle l'instance initiale de serveur miroir).</span><span class="sxs-lookup"><span data-stu-id="3eee8-162">On the principal server instance on HOST_A, set the server instance on HOST_B as the partner (making it the initial mirror server instance).</span></span> <span data-ttu-id="3eee8-163">Remplacez une adresse réseau valide par `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span><span class="sxs-lookup"><span data-stu-id="3eee8-163">Substitute a valid network address for `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span></span>  
  
    ```  
    --At HOST_A, set server instance on HOST_B as partner (mirror server).  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
3.  <span data-ttu-id="3eee8-164">Cet exemple suppose que la session est exécutée en mode hautes performances.</span><span class="sxs-lookup"><span data-stu-id="3eee8-164">This example assumes that the session will be running in high-performance mode.</span></span> <span data-ttu-id="3eee8-165">Pour configurer cette session au mode hautes performances, sur l'instance de serveur principal (sur HOST_A), désactivez la sécurité des transactions.</span><span class="sxs-lookup"><span data-stu-id="3eee8-165">To configure this session for high-performance mode, on the principal server instance (on HOST_A), set transaction safety to OFF.</span></span>  
  
    ```  
    --Change to high-performance mode by turning off transacton safety.  
    ALTER DATABASE AdventureWorks   
        SET PARTNER SAFETY OFF  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="3eee8-166">Si vous envisagez de l’exécuter en mode haute sécurité avec basculement automatique, laissez la sécurité des transactions définie sur Full (paramètre par défaut) et ajoutez le témoin dès que possible après l’exécution de la deuxième instruction SET PARTNER **' *`partner_server`* '** .</span><span class="sxs-lookup"><span data-stu-id="3eee8-166">If you intend to run in high-safety mode with automatic failover, leave transaction safety set to FULL (the default setting) and add the witness as soon as possible after executing the second SET PARTNER **'*`partner_server`*'** statement.</span></span> <span data-ttu-id="3eee8-167">Notez que le serveur témoin doit d'abord être configuré pour les connexions sortantes et entrantes.</span><span class="sxs-lookup"><span data-stu-id="3eee8-167">Note that the witness must first be configured for outbound and inbound connections.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3eee8-168">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="3eee8-168">Related Tasks</span></span>  
  
-   [<span data-ttu-id="3eee8-169">Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3eee8-169">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="3eee8-170">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3eee8-170">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="3eee8-171">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3eee8-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="3eee8-172">Gestion des connexions et des travaux après un basculement de rôle &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3eee8-172">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
-   <span data-ttu-id="3eee8-173">[Gérer les métadonnées durant la mise à disposition d’une base de données sur une autre instance de serveur &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3eee8-173">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span></span>  
  
-   [<span data-ttu-id="3eee8-174">Résoudre des problèmes de configuration de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3eee8-174">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="3eee8-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3eee8-175">See Also</span></span>  
 <span data-ttu-id="3eee8-176">[Sécurité de transport pour la mise en miroir de bases de données et les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="3eee8-176">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="3eee8-177">[Spécifier une adresse réseau de serveur &#40;mise en miroir de bases de données&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="3eee8-177">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="3eee8-178">[Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3eee8-178">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="3eee8-179">[Utiliser des certificats pour un point de terminaison de mise en miroir de bases de données &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="3eee8-179">[Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span></span>  
 <span data-ttu-id="3eee8-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3eee8-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="3eee8-181">Centre de sécurité pour le moteur de base de données SQL Server et Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="3eee8-181">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
