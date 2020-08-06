---
title: Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- inbound connections
- database mirroring [SQL Server], security
ms.assetid: 5d48bb98-61f0-4b99-8f1a-b53f831d63d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c05397dfbd1740293c4b154ace1ed5704cec11a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601665"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-inbound-connections-transact-sql"></a><span data-ttu-id="f73b6-102">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f73b6-102">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="f73b6-103">Cette rubrique décrit les étapes requises pour configurer les instances de serveur afin qu'elles utilisent les certificats pour authentifier les connexions entrantes dans le cadre de la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="f73b6-103">This topic describes the steps for configuring server instances to use certificates to authenticate inbound connections for database mirroring.</span></span> <span data-ttu-id="f73b6-104">Avant de définir des connexions entrantes, vous devez configurer les connexions sortantes sur chacune des instances du serveur.</span><span class="sxs-lookup"><span data-stu-id="f73b6-104">Before you can set up inbound connections, you must configure outbound connections on each server instance.</span></span> <span data-ttu-id="f73b6-105">Pour plus d’informations, consultez [Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="f73b6-105">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
 <span data-ttu-id="f73b6-106">La configuration des connexions entrantes se fait en quatre temps, à savoir :</span><span class="sxs-lookup"><span data-stu-id="f73b6-106">The process of configuring inbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="f73b6-107">Création d'une connexion pour l'autre système</span><span class="sxs-lookup"><span data-stu-id="f73b6-107">Create a login for other system.</span></span>  
  
2.  <span data-ttu-id="f73b6-108">Créez un utilisateur pour cette connexion.</span><span class="sxs-lookup"><span data-stu-id="f73b6-108">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="f73b6-109">Obtenez le certificat pour la mise en miroir du point de terminaison de l'autre instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="f73b6-109">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="f73b6-110">Associez le certificat à l'utilisateur créé à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="f73b6-110">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="f73b6-111">Accordez à ce point de terminaison de mise en miroir l'autorisation CONNECT sur la connexion.</span><span class="sxs-lookup"><span data-stu-id="f73b6-111">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="f73b6-112">S'il existe un témoin, vous devez également configurer les connexions entrantes pour celui-ci.</span><span class="sxs-lookup"><span data-stu-id="f73b6-112">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="f73b6-113">Cela exige la définition des noms de connexion, des utilisateurs et des certificats pour le témoin sur les deux partenaires, et inversement.</span><span class="sxs-lookup"><span data-stu-id="f73b6-113">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="f73b6-114">La procédure suivante décrit ces étapes en détail.</span><span class="sxs-lookup"><span data-stu-id="f73b6-114">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="f73b6-115">Pour chaque étape, la procédure fournit un exemple de configuration d'une instance du serveur sur un système nommé HOST_A.</span><span class="sxs-lookup"><span data-stu-id="f73b6-115">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="f73b6-116">La section Exemple qui l'accompagne explique les mêmes étapes pour une autre instance du serveur sur un système nommé HOST_B.</span><span class="sxs-lookup"><span data-stu-id="f73b6-116">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
### <a name="to-configure-server-instances-for-inbound-mirroring-connections-on-host_a"></a><span data-ttu-id="f73b6-117">Pour configurer les instances du serveur pour les connexions de mise en miroir entrantes (sur HOST_A)</span><span class="sxs-lookup"><span data-stu-id="f73b6-117">To configure server instances for inbound mirroring connections (on HOST_A)</span></span>  
  
1.  <span data-ttu-id="f73b6-118">Créez une connexion pour l'autre système.</span><span class="sxs-lookup"><span data-stu-id="f73b6-118">Create a login for the other system.</span></span>  
  
     <span data-ttu-id="f73b6-119">L’exemple suivant crée une connexion pour le système, HOST_B, dans la base de données **master** de l’instance du serveur sur HOST_A. Dans cet exemple, la connexion s’appelle `HOST_B_login`.</span><span class="sxs-lookup"><span data-stu-id="f73b6-119">The following example creates a login for the system, HOST_B, in the **master** database of the server instance on HOST_A; in this example, the login is named `HOST_B_login`.</span></span> <span data-ttu-id="f73b6-120">Remplacez le mot de passe donné en exemple par un mot de passe qui vous est propre.</span><span class="sxs-lookup"><span data-stu-id="f73b6-120">Substitute a password of your own for the sample password.</span></span>  
  
    ```sql  
    USE master;  
    CREATE LOGIN HOST_B_login   
       WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
     <span data-ttu-id="f73b6-121">Pour plus d’informations, consultez [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f73b6-121">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
     <span data-ttu-id="f73b6-122">Pour afficher les connexions existant pour cette instance du serveur, vous pouvez utiliser l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="f73b6-122">To view the logins on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.server_principals;  
    ```  
  
     <span data-ttu-id="f73b6-123">Pour plus d’informations, consultez [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f73b6-123">For more information, see [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span></span>  
  
2.  <span data-ttu-id="f73b6-124">Créez un utilisateur pour cette connexion.</span><span class="sxs-lookup"><span data-stu-id="f73b6-124">Create a user for that login.</span></span>  
  
     <span data-ttu-id="f73b6-125">L'exemple suivant crée un utilisateur, `HOST_B_user`, pour la connexion créée lors de l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="f73b6-125">The following example creates a user, `HOST_B_user`, for the login created in the preceding step.</span></span>  
  
    ```sql  
    USE master;  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
     <span data-ttu-id="f73b6-126">Pour plus d’informations, consultez [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f73b6-126">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
     <span data-ttu-id="f73b6-127">Pour afficher les utilisateurs existant pour cette instance du serveur, vous pouvez utiliser l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="f73b6-127">To view the users on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.sysusers;  
    ```  
  
     <span data-ttu-id="f73b6-128">Pour plus d’informations, consultez [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f73b6-128">For more information, see [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span></span>  
  
3.  <span data-ttu-id="f73b6-129">Obtenez le certificat pour la mise en miroir du point de terminaison de l'autre instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="f73b6-129">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
     <span data-ttu-id="f73b6-130">Si vous ne l'avez pas encore fait lors de la configuration des connexions sortantes, obtenez une copie du certificat pour le point de terminaison de mise en miroir de l'instance du serveur distant.</span><span class="sxs-lookup"><span data-stu-id="f73b6-130">If you have not already done so when configuring outbound connections, obtain a copy of the certificate for the mirroring endpoint of the remote server instance.</span></span> <span data-ttu-id="f73b6-131">Pour ce faire, sauvegardez le certificat sur cette instance de serveur comme décrit dans [Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="f73b6-131">To do this, back up the certificate on that server instance as described in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span> <span data-ttu-id="f73b6-132">Lors de la copie d'un certificat sur un autre système, utilisez une méthode de copie sécurisée.</span><span class="sxs-lookup"><span data-stu-id="f73b6-132">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="f73b6-133">Veillez particulièrement à sécuriser tous vos certificats.</span><span class="sxs-lookup"><span data-stu-id="f73b6-133">Be extremely careful to keep all of your certificates secure.</span></span>  
  
     <span data-ttu-id="f73b6-134">Pour plus d’informations, consultez [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f73b6-134">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
4.  <span data-ttu-id="f73b6-135">Associez le certificat à l'utilisateur créé à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="f73b6-135">Associate the certificate with the user created in step 2.</span></span>  
  
     <span data-ttu-id="f73b6-136">L'exemple suivant associe le certificat de HOST_B avec son utilisateur sur HOST_A.</span><span class="sxs-lookup"><span data-stu-id="f73b6-136">The following example, associates the certificate of HOST_B with its user on HOST_A.</span></span>  
  
    ```sql  
    USE master;  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
     <span data-ttu-id="f73b6-137">Pour plus d’informations, consultez [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f73b6-137">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="f73b6-138">Pour afficher les certificats existant pour cette instance du serveur, vous pouvez utiliser l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="f73b6-138">To view the certificates on this server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="f73b6-139">Pour plus d’informations, consultez [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f73b6-139">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
5.  <span data-ttu-id="f73b6-140">Accordez l'autorisation CONNECT à la connexion pour le point de terminaison de mise en miroir distant.</span><span class="sxs-lookup"><span data-stu-id="f73b6-140">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
     <span data-ttu-id="f73b6-141">Par exemple, pour accorder l’autorisation sur HOST_A à l’instance du serveur distant sur HOST_B afin qu’elle puisse se connecter à sa connexion locale, c’est-à-dire à `HOST_B_login`, utilisez les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="f73b6-141">For example, to grant permission on HOST_A to the remote server instance on HOST_B to connect to its local login-that is, to connect to `HOST_B_login`-use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```sql  
    USE master;  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
     <span data-ttu-id="f73b6-142">Pour plus d’informations, consultez [Autorisations de point de terminaison GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f73b6-142">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="f73b6-143">Cette dernière étape conclut la configuration de l'authentification par certificat de HOST_B lors de sa connexion à HOST_A.</span><span class="sxs-lookup"><span data-stu-id="f73b6-143">This completes setting up certificate authentication for HOST_B to log in to HOST_A.</span></span>  
  
 <span data-ttu-id="f73b6-144">Il vous faut maintenant procéder de même pour les communications entrantes pour HOST_A sur HOST_B</span><span class="sxs-lookup"><span data-stu-id="f73b6-144">You now need to perform the equivalent inbound steps for HOST_A on HOST_B.</span></span> <span data-ttu-id="f73b6-145">Ces étapes sont expliquées dans la partie consacrée aux connexions entrantes de l'exemple présenté dans la section Exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f73b6-145">These steps are illustrated in the inbound portion of the example in the Example section, below.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f73b6-146">Exemple</span><span class="sxs-lookup"><span data-stu-id="f73b6-146">Example</span></span>  
 <span data-ttu-id="f73b6-147">L'exemple suivant explique comment configurer HOST_B pour les connexions entrantes.</span><span class="sxs-lookup"><span data-stu-id="f73b6-147">The following example demonstrates configuring HOST_B for inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f73b6-148">Cet exemple utilise un fichier de certificat contenant le certificat HOST_A qui est créé par un extrait de code dans [Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="f73b6-148">This example uses a certificate file containing the HOST_A certificate that is created by a code snippet in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
```sql  
USE master;  
--On HOST_B, create a login for HOST_A.  
CREATE LOGIN HOST_A_login WITH PASSWORD = 'AStrongPassword!@#';  
GO  
--Create a user, HOST_A_user, for that login.  
CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
GO  
--Obtain HOST_A certificate. (See the note   
--   preceding this example.)  
--Asscociate this certificate with the user, HOST_A_user.  
CREATE CERTIFICATE HOST_A_cert  
   AUTHORIZATION HOST_A_user  
   FROM FILE = 'C:\HOST_A_cert.cer';  
GO  
--Grant CONNECT permission for the server instance on HOST_A.  
GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO HOST_A_login;  
GO  
```  
  
 <span data-ttu-id="f73b6-149">Si vous envisagez d'utiliser le mode haute sécurité avec basculement automatique, vous devez répéter les mêmes étapes pour configurer le témoin pour les connexions sortantes et entrantes.</span><span class="sxs-lookup"><span data-stu-id="f73b6-149">If you intend to run in high-safety mode with automatic failover, you must repeat the same set up steps to configure the witness for outbound and inbound connections.</span></span>  
  
 <span data-ttu-id="f73b6-150">Pour plus d’informations sur la création d’une base de données miroir, et obtenir un exemple Transact-SQL, consultez [Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f73b6-150">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="f73b6-151">Pour obtenir un exemple Transact-SQL d’établissement d’une session en mode hautes performances, consultez [Exemple : Configuration de la mise en miroir de bases de données à l’aide de certificats &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f73b6-151">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f73b6-152">Sécurité du .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f73b6-152">.NET Framework Security</span></span>  
 <span data-ttu-id="f73b6-153">Lors de la copie d'un certificat sur un autre système, utilisez une méthode de copie sécurisée.</span><span class="sxs-lookup"><span data-stu-id="f73b6-153">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="f73b6-154">Veillez particulièrement à sécuriser tous vos certificats.</span><span class="sxs-lookup"><span data-stu-id="f73b6-154">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f73b6-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f73b6-155">See Also</span></span>  
 <span data-ttu-id="f73b6-156">[Sécurité de transport pour la mise en miroir de bases de données et les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="f73b6-156">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="f73b6-157">[Autorisations GRANT sur point de terminaison &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f73b6-157">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 <span data-ttu-id="f73b6-158">[Configurer une base de données miroir chiffrée](set-up-an-encrypted-mirror-database.md) </span><span class="sxs-lookup"><span data-stu-id="f73b6-158">[Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md) </span></span>  
 <span data-ttu-id="f73b6-159">[Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f73b6-159">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 [<span data-ttu-id="f73b6-160">Résoudre des problèmes de configuration de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f73b6-160">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
