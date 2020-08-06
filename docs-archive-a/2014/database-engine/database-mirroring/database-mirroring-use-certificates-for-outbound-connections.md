---
title: Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- outbound connections [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 464c9096-10d6-4c5e-8bb1-19acba27ad9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f380f268f8d0f8d033db9c28f83d066d3f134571
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601664"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-outbound-connections-transact-sql"></a><span data-ttu-id="6b051-102">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6b051-102">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="6b051-103">Cette rubrique explique comment configurer les instances de serveur de sorte qu'elles utilisent des certificats pour authentifier les connexions sortantes de la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="6b051-103">This topic describes the steps for configuring server instances to use certificates to authenticate outbound connections for database mirroring.</span></span> <span data-ttu-id="6b051-104">La configuration des connexions sortantes doit être effectuée avant celle des connexions entrantes.</span><span class="sxs-lookup"><span data-stu-id="6b051-104">Outbound connection configuration must be done before you can set up inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b051-105">Toutes les connexions de mise en miroir situées sur une instance du serveur utilisent un point de terminaison de mise en miroir de bases de données unique, et vous devez spécifier la méthode d'authentification de l'instance du serveur au moment de la création de ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="6b051-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span>  
  
 <span data-ttu-id="6b051-106">Le processus de configuration des connexions sortantes comprend les étapes générales suivantes :</span><span class="sxs-lookup"><span data-stu-id="6b051-106">The process of configuring outbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="6b051-107">Dans la base de données **MASTER** , créez une clé principale de base de données.</span><span class="sxs-lookup"><span data-stu-id="6b051-107">In the **master** database, create a database Master Key.</span></span>  
  
2.  <span data-ttu-id="6b051-108">Dans la base de données **master** , créez un certificat chiffré sur l’instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="6b051-108">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="6b051-109">Créez un point de terminaison pour l'instance du serveur à l'aide de son certificat.</span><span class="sxs-lookup"><span data-stu-id="6b051-109">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="6b051-110">Sauvegardez le certificat dans un fichier et copiez-le par sécurité sur un ou plusieurs autres systèmes.</span><span class="sxs-lookup"><span data-stu-id="6b051-110">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="6b051-111">Vous devez exécuter cette procédure pour chaque partenaire et pour le témoin éventuel.</span><span class="sxs-lookup"><span data-stu-id="6b051-111">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="6b051-112">La procédure suivante décrit ces étapes en détail.</span><span class="sxs-lookup"><span data-stu-id="6b051-112">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="6b051-113">Pour chaque étape, la procédure fournit un exemple de configuration d'une instance du serveur sur un système nommé HOST_A.</span><span class="sxs-lookup"><span data-stu-id="6b051-113">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="6b051-114">La section Exemple qui l'accompagne explique les mêmes étapes pour une autre instance du serveur sur un système nommé HOST_B.</span><span class="sxs-lookup"><span data-stu-id="6b051-114">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="6b051-115">Procédure</span><span class="sxs-lookup"><span data-stu-id="6b051-115">Procedure</span></span>  
  
#### <a name="to-configure-server-instances-for-outbound-mirroring-connections-on-host_a"></a><span data-ttu-id="6b051-116">Pour configurer les instances du serveur pour les connexions de mise en miroir sortantes (sur HOST_A)</span><span class="sxs-lookup"><span data-stu-id="6b051-116">To configure server instances for outbound mirroring connections (On HOST_A)</span></span>  
  
1.  <span data-ttu-id="6b051-117">Dans la base de données **MASTER** , créez la clé principale de base de données, s’il n’en existe aucune.</span><span class="sxs-lookup"><span data-stu-id="6b051-117">On the **master** database, create the database Master Key, if none exists.</span></span> <span data-ttu-id="6b051-118">Pour afficher les clés existantes d’une base de données, utilisez l’affichage catalogue [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="6b051-118">To view the existing keys for a database, use the [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) catalog view.</span></span>  
  
     <span data-ttu-id="6b051-119">Pour créer la clé principale de base de données, utilisez la commande [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="6b051-119">To create the database Master Key, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command:</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
     <span data-ttu-id="6b051-120">Utilisez un mot de passe fort et unique, puis enregistrez-le dans un lieu sûr.</span><span class="sxs-lookup"><span data-stu-id="6b051-120">Use a unique, strong password, and record it in a safe place.</span></span>  
  
     <span data-ttu-id="6b051-121">Pour plus d’informations, consultez [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) et [Créer une clé principale de base de données](../../relational-databases/security/encryption/create-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="6b051-121">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) and [Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md).</span></span>  
  
2.  <span data-ttu-id="6b051-122">Dans la base de données **MASTER**, créez un certificat chiffré sur l’instance de serveur à utiliser pour ses connexions sortantes de la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="6b051-122">In the **master** database, create an encrypted certificate on the server instance to use for its outbound connections for database mirroring.</span></span>  
  
     <span data-ttu-id="6b051-123">Par exemple, pour créer un certificat pour le système HOST_A :</span><span class="sxs-lookup"><span data-stu-id="6b051-123">For example, to create a certificate for the HOST_A system.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="6b051-124">Si vous envisagez d'utiliser le certificat pendant plusieurs années, spécifiez la date d'expiration en heure UTC à l'aide de l'option EXPIRY_DATE dans votre instruction CREATE CERTIFICATE.</span><span class="sxs-lookup"><span data-stu-id="6b051-124">If you intend to use the certificate for more than one year, specify the expiry date in UTC time by using the EXPIRY_DATE option in your CREATE CERTIFICATE statement.</span></span> <span data-ttu-id="6b051-125">Nous vous recommandons également d'utiliser SQL Server Management Studio pour créer une règle de gestion basée sur des stratégies pour vous alerter lorsque vos certificats expirent.</span><span class="sxs-lookup"><span data-stu-id="6b051-125">Also, we recommend that you use SQL Server Management Studio to create a Policy-Based Management rule to alert you when your certificates are expiring.</span></span> <span data-ttu-id="6b051-126">À l’aide de la boîte de dialogue de gestion de la stratégie **Créer une nouvelle condition** , créez cette règle sur le champ **@ExpirationDate** de la facette **Certificat** .</span><span class="sxs-lookup"><span data-stu-id="6b051-126">Using the Policy Management **Create New Condition** dialog box, create this rule on the **@ExpirationDate** field of the **Certificate** facet.</span></span> <span data-ttu-id="6b051-127">Pour plus d’informations, consultez [Administrer des serveurs à l’aide de la gestion basée sur des stratégies](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) et [Sécurisation de SQL Server](../../relational-databases/security/securing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6b051-127">For more information, see [Administer Servers by Using Policy-Based Management](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) and [Securing SQL Server](../../relational-databases/security/securing-sql-server.md).</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate for database mirroring',   
       EXPIRY_DATE = '11/30/2013';  
    GO  
    ```  
  
     <span data-ttu-id="6b051-128">Pour plus d’informations, consultez [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6b051-128">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="6b051-129">Pour afficher les certificats stockés dans la base de données **MASTER**, vous pouvez utiliser les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="6b051-129">To view the certificates in the **master** database, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="6b051-130">Pour plus d’informations, consultez [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6b051-130">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
3.  <span data-ttu-id="6b051-131">Vérifiez que le point de terminaison de mise en miroir de bases de données existe sur chacune des instances de serveur.</span><span class="sxs-lookup"><span data-stu-id="6b051-131">Ensure that the database mirroring endpoint exist on each of the server instances.</span></span>  
  
     <span data-ttu-id="6b051-132">Si un point de terminaison de mise en miroir de bases de données existe déjà pour l'instance de serveur, vous devez le réutiliser pour toutes les autres sessions que vous établissez sur cette instance.</span><span class="sxs-lookup"><span data-stu-id="6b051-132">If a database mirroring endpoint already exists for the server instance, you should reuse that endpoint for any other sessions you establish on the server instance.</span></span> <span data-ttu-id="6b051-133">Pour déterminer si un point de terminaison de mise en miroir de bases de données existe sur une instance de serveur et pour afficher sa configuration, utilisez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="6b051-133">To determine whether a database mirroring endpoint exists on a server instance and to view its configuration, use the following statement:</span></span>  
  
    ```  
    SELECT name, role_desc, state_desc, connection_auth_desc, encryption_algorithm_desc   
       FROM sys.database_mirroring_endpoints;  
    ```  
  
     <span data-ttu-id="6b051-134">Si aucun point de terminaison n'existe, créez un point de terminaison qui utilise ce certificat pour les connexions sortantes et qui a recours à ses informations d'identification à des fins de vérification sur l'autre système.</span><span class="sxs-lookup"><span data-stu-id="6b051-134">If no endpoint exists, create an endpoint that uses this certificate for outbound connections and that uses the certificate's credentials for verification on the other system.</span></span> <span data-ttu-id="6b051-135">Il s'agit d'un point de terminaison de niveau serveur utilisé par toutes les sessions de mise en miroir auxquelles participe l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="6b051-135">This is a server-wide endpoint that is used by all mirroring sessions in which the server instance participates.</span></span>  
  
     <span data-ttu-id="6b051-136">L'instruction suivante permet de créer un point de terminaison de mise en miroir pour l'exemple d'instance de serveur de HOST_A :</span><span class="sxs-lookup"><span data-stu-id="6b051-136">For example, to create a mirroring endpoint for the example server instance on HOST_A.</span></span>  
  
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
  
     <span data-ttu-id="6b051-137">Pour plus d’informations, consultez [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6b051-137">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
4.  <span data-ttu-id="6b051-138">Sauvegardez le certificat et copiez-le sur le ou les autres systèmes.</span><span class="sxs-lookup"><span data-stu-id="6b051-138">Back up the certificate and copy it to the other system or systems.</span></span> <span data-ttu-id="6b051-139">Cette opération est nécessaire pour configurer les connexions entrantes sur l'autre système.</span><span class="sxs-lookup"><span data-stu-id="6b051-139">This is necessary in order to configure inbound connections on the other system.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
     <span data-ttu-id="6b051-140">Pour plus d’informations, consultez [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6b051-140">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="6b051-141">Copiez ce certificat en utilisant la méthode sécurisée de votre choix.</span><span class="sxs-lookup"><span data-stu-id="6b051-141">Copy this certificate using any secure method you choose.</span></span> <span data-ttu-id="6b051-142">Veillez particulièrement à sécuriser tous vos certificats.</span><span class="sxs-lookup"><span data-stu-id="6b051-142">Be extremely careful to keep all of your certificates secure.</span></span>  
  
 <span data-ttu-id="6b051-143">L'exemple de code des étapes précédentes configure des connexions sortantes sur HOST_A.</span><span class="sxs-lookup"><span data-stu-id="6b051-143">The example code in the preceding steps configure outbound connections on HOST_A.</span></span>  
  
 <span data-ttu-id="6b051-144">Vous devez maintenant effectuer les étapes équivalentes pour configurer des connexions sortantes sur HOST_B.</span><span class="sxs-lookup"><span data-stu-id="6b051-144">You now need to perform the equivalent outbound steps for HOST_B.</span></span> <span data-ttu-id="6b051-145">Ces étapes sont illustrées dans la section « Exemple » ci-après.</span><span class="sxs-lookup"><span data-stu-id="6b051-145">These steps are illustrated in the following Example section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b051-146">Exemple</span><span class="sxs-lookup"><span data-stu-id="6b051-146">Example</span></span>  
 <span data-ttu-id="6b051-147">L'exemple ci-dessous illustre la configuration de HOST_B pour la prise en charge des connexions sortantes.</span><span class="sxs-lookup"><span data-stu-id="6b051-147">The following example demonstrates configuring HOST_B for outbound connections.</span></span>  
  
```  
USE master;  
--Create the database Master Key, if needed.  
CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
GO  
-- Make a certifcate on HOST_B server instance.  
CREATE CERTIFICATE HOST_B_cert   
   WITH SUBJECT = 'HOST_B certificate for database mirroring',   
   EXPIRY_DATE = '11/30/2013';  
GO  
--Create a mirroring endpoint for the server instance on HOST_B.  
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
--Backup HOST_B certificate.  
BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
GO   
--Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.  
```  
  
 <span data-ttu-id="6b051-148">Copiez le certificat sur l'autre système en utilisant la méthode sécurisée de votre choix.</span><span class="sxs-lookup"><span data-stu-id="6b051-148">Copy the certificate to the other system using any secure method you choose.</span></span> <span data-ttu-id="6b051-149">Veillez particulièrement à sécuriser tous vos certificats.</span><span class="sxs-lookup"><span data-stu-id="6b051-149">Be extremely careful to keep all of your certificates secure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6b051-150">Une fois que vous avez défini les connexions sortantes, vous devez configurer les connexions entrantes sur chacune des instances du serveur pour l'instance ou les instances de l'autre serveur.</span><span class="sxs-lookup"><span data-stu-id="6b051-150">After you set up outbound connections, you must configure inbound connections on each server instance for the other server instance or instances.</span></span> <span data-ttu-id="6b051-151">Pour plus d’informations, consultez [Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="6b051-151">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
 <span data-ttu-id="6b051-152">Pour plus d’informations sur la création d’une base de données miroir, et obtenir un exemple Transact-SQL, consultez [Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6b051-152">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="6b051-153">Pour obtenir un exemple Transact-SQL d’établissement d’une session en mode hautes performances, consultez [Exemple : Configuration de la mise en miroir de bases de données à l’aide de certificats &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="6b051-153">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6b051-154">Sécurité du .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6b051-154">.NET Framework Security</span></span>  
 <span data-ttu-id="6b051-155">À moins que vous ne puissiez garantir la sécurité de votre réseau, il est recommandé d'utiliser le chiffrement pour les connexions de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="6b051-155">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="6b051-156">Lors de la copie d'un certificat sur un autre système, utilisez une méthode de copie sécurisée.</span><span class="sxs-lookup"><span data-stu-id="6b051-156">When copying a certificate to another system, use a secure copy method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b051-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b051-157">See Also</span></span>  
 <span data-ttu-id="6b051-158">[Choisir un algorithme de chiffrement](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="6b051-158">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="6b051-159">[Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6b051-159">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="6b051-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6b051-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="6b051-161">[Exemple : Configuration de la mise en miroir de bases de données à l’aide de certificats &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="6b051-161">[Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span></span>  
 <span data-ttu-id="6b051-162">[Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6b051-162">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="6b051-163">[Résolution des problèmes de configuration de mise en miroir de bases de données &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6b051-163">[Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md) </span></span>  
 [<span data-ttu-id="6b051-164">Configurer une base de données miroir chiffrée</span><span class="sxs-lookup"><span data-stu-id="6b051-164">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
