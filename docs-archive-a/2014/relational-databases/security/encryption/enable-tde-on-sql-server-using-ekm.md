---
title: Activer TDE à l’aide de EKM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], TDE using an EKM
- TDE, EKM how to
- EKM, TDE how to
- Transparent Data Encryption, using EKM
ms.assetid: b892e7a7-95bd-4903-bf54-55ce08e225af
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: e659c5ff0245fdb17192b845eafc60badf5e295e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709071"
---
# <a name="enable-tde-using-ekm"></a><span data-ttu-id="850a1-102">Activer le chiffrement transparent des données à l'aide de la gestion de clés extensible (EKM)</span><span class="sxs-lookup"><span data-stu-id="850a1-102">Enable TDE Using EKM</span></span>
  <span data-ttu-id="850a1-103">Cette rubrique explique comment activer le chiffrement transparent des données (TDE) dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] afin de protéger une clé de chiffrement de base de données à l'aide d'une clé asymétrique stockée dans un module de gestion de clés extensible (EKM) avec [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="850a1-103">This topic describes how to enable transparent data encryption (TDE) in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to protect a database encryption key by using an asymmetric key stored in an extensible key management (EKM) module with [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="850a1-104">TDE chiffre le stockage de l’ensemble de la base de données avec une clé symétrique, appelée « clé de chiffrement de base de données ».</span><span class="sxs-lookup"><span data-stu-id="850a1-104">TDE encrypts the storage of an entire database by using a symmetric key called the database encryption key.</span></span> <span data-ttu-id="850a1-105">La clé de chiffrement de base de données peut également être protégée à l'aide d'un certificat qui est lui-même protégé par la clé principale de base de données de la base de données MASTER</span><span class="sxs-lookup"><span data-stu-id="850a1-105">The database encryption key can also be protected using a certificate which is protected by the database master key of the master database.</span></span> <span data-ttu-id="850a1-106">Pour plus d’informations sur la protection de la clé de chiffrement de base de données à l’aide de la clé principale de base de données, consultez [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="850a1-106">For more information about protecting the database encryption key by using the database master key, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span> <span data-ttu-id="850a1-107">Pour plus d’informations sur la configuration de TDE lorsque [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est exécuté sur une machine virtuelle Azure, consultez [Gestion de clés extensible à l’aide d’Azure Key Vault &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="850a1-107">For information about configuring TDE when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running on an Azure VM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
 <span data-ttu-id="850a1-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="850a1-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="850a1-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="850a1-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="850a1-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="850a1-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="850a1-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="850a1-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="850a1-112">Pour activer le chiffrement TDE à l'aide de la gestion de clés extensible, avec Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="850a1-112">To enable TDE using EKM, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="850a1-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="850a1-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="850a1-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="850a1-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="850a1-115">Vous devez être un utilisateur doté de privilèges élevés (comme un administrateur système) pour créer une clé de chiffrement de base de données et chiffrer une base de données.</span><span class="sxs-lookup"><span data-stu-id="850a1-115">You must be a high privileged user (such as a system administrator) to create a database encryption key and encrypt a database.</span></span> <span data-ttu-id="850a1-116">Cet utilisateur doit pouvoir être authentifié par le module EKM.</span><span class="sxs-lookup"><span data-stu-id="850a1-116">That user must be able to be authenticated by the EKM module.</span></span>  
  
-   <span data-ttu-id="850a1-117">Au démarrage, le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] doit ouvrir la base de données.</span><span class="sxs-lookup"><span data-stu-id="850a1-117">Upon start up the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must open the database.</span></span> <span data-ttu-id="850a1-118">Pour ce faire, vous devez créer des informations d'identification qui seront authentifiées par la gestion de clés extensible et les ajouter à un nom de connexion reposant sur une clé asymétrique.</span><span class="sxs-lookup"><span data-stu-id="850a1-118">To do this, you should create a credential that will be authenticated by the EKM, and add it to a login that is based on an asymmetric key.</span></span> <span data-ttu-id="850a1-119">Les utilisateurs ne peuvent pas se connecter à l'aide de ce nom de connexion, mais le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] sera en mesure de s'authentifier auprès du périphérique EKM.</span><span class="sxs-lookup"><span data-stu-id="850a1-119">Users cannot login using that login, but the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] will be able to authenticate itself with the EKM device.</span></span>  
  
-   <span data-ttu-id="850a1-120">En cas de perte de la clé asymétrique stockée dans le module EKM, la base de données ne peut pas être ouverte par [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="850a1-120">If the asymmetric key stored in the EKM module is lost, the database will not be able to be opened by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="850a1-121">Si le fournisseur EKM vous permet de sauvegarder la clé asymétrique, vous devez créer une sauvegarde et la stocker dans un endroit sûr.</span><span class="sxs-lookup"><span data-stu-id="850a1-121">If the EKM provider lets you back up the asymmetric key, you should create a back up and store it in a secure location.</span></span>  
  
-   <span data-ttu-id="850a1-122">Les options et les paramètres requis par votre fournisseur EKM peuvent différer de ce qui est indiqué dans l'exemple de code ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="850a1-122">The options and parameters required by your EKM provider can differ from what is provided in the code example below.</span></span> <span data-ttu-id="850a1-123">Pour plus d'informations, consultez votre fournisseur EKM.</span><span class="sxs-lookup"><span data-stu-id="850a1-123">For more information, see your EKM provider.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="850a1-124">Sécurité</span><span class="sxs-lookup"><span data-stu-id="850a1-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="850a1-125">Autorisations</span><span class="sxs-lookup"><span data-stu-id="850a1-125">Permissions</span></span>  
 <span data-ttu-id="850a1-126">Cette rubrique utilise les autorisations suivantes :</span><span class="sxs-lookup"><span data-stu-id="850a1-126">This topic uses the following permissions:</span></span>  
  
-   <span data-ttu-id="850a1-127">Pour modifier une option de configuration et exécuter l'instruction RECONFIGURE, vous devez disposer de l'autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="850a1-127">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="850a1-128">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="850a1-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
-   <span data-ttu-id="850a1-129">Requiert l'autorisation ALTER ANY CREDENTIAL.</span><span class="sxs-lookup"><span data-stu-id="850a1-129">Requires ALTER ANY CREDENTIAL permission.</span></span>  
  
-   <span data-ttu-id="850a1-130">Nécessite l'autorisation ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="850a1-130">Requires ALTER ANY LOGIN permission.</span></span>  
  
-   <span data-ttu-id="850a1-131">Requiert l'autorisation CREATE ASYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="850a1-131">Requires CREATE ASYMMETRIC KEY permission.</span></span>  
  
-   <span data-ttu-id="850a1-132">Requiert l'autorisation CONTROL sur la base de données pour chiffrer la base de données.</span><span class="sxs-lookup"><span data-stu-id="850a1-132">Requires CONTROL permission on the database to encrypt the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="850a1-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="850a1-133">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-tde-using-ekm"></a><span data-ttu-id="850a1-134">Pour activer le chiffrement transparent des données (TDE) à l'aide de la gestion de clés extensible (EKM)</span><span class="sxs-lookup"><span data-stu-id="850a1-134">To enable TDE using EKM</span></span>  
  
1.  <span data-ttu-id="850a1-135">Copiez les fichiers fournis par le fournisseur EKM à un emplacement approprié sur l'ordinateur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="850a1-135">Copy the files supplied by the EKM provider to an appropriate location on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="850a1-136">Dans cet exemple, le dossier **C:\EKM** est utilisé.</span><span class="sxs-lookup"><span data-stu-id="850a1-136">In this example, we use the **C:\EKM** folder.</span></span>  
  
2.  <span data-ttu-id="850a1-137">Installez les certificats requis par votre fournisseur EKM sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="850a1-137">Install certificates to the computer as required by your EKM provider.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="850a1-138">ne propose pas de fournisseur EKM.</span><span class="sxs-lookup"><span data-stu-id="850a1-138">does not supply an EKM provider.</span></span> <span data-ttu-id="850a1-139">Chaque fournisseur EKM peut utiliser des procédures différentes pour l'installation, la configuration et l'autorisation des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="850a1-139">Each EKM provider can have different procedures for installing, configuring and authorizing users.</span></span>  <span data-ttu-id="850a1-140">Consultez la documentation de votre fournisseur EKM pour effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="850a1-140">Consult your EKM provider documentation to complete this step.</span></span>  
  
3.  <span data-ttu-id="850a1-141">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="850a1-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
4.  <span data-ttu-id="850a1-142">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="850a1-142">On the Standard bar, click **New Query**.</span></span>  
  
5.  <span data-ttu-id="850a1-143">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="850a1-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Enable advanced options.  
    sp_configure 'show advanced options', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Enable EKM provider  
    sp_configure 'EKM provider enabled', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Create a cryptographic provider, which we have chosen to call "EKM_Prov," based on an EKM provider  
  
    CREATE CRYPTOGRAPHIC PROVIDER EKM_Prov   
    FROM FILE = 'C:\EKM_Files\KeyProvFile.dll' ;  
    GO  
  
    -- Create a credential that will be used by system administrators.  
    CREATE CREDENTIAL sa_ekm_tde_cred   
    WITH IDENTITY = 'Identity1',   
    SECRET = 'q*gtev$0u#D1v'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
    GO  
  
    -- Add the credential to a high privileged user such as your   
    -- own domain login in the format [DOMAIN\login].  
    ALTER LOGIN Contoso\Mary  
    ADD CREDENTIAL sa_ekm_tde_cred ;  
    GO  
    -- create an asymmetric key stored inside the EKM provider  
    USE master ;  
    GO  
    CREATE ASYMMETRIC KEY ekm_login_key   
    FROM PROVIDER [EKM_Prov]  
    WITH ALGORITHM = RSA_512,  
    PROVIDER_KEY_NAME = 'SQL_Server_Key' ;  
    GO  
  
    -- Create a credential that will be used by the Database Engine.  
    CREATE CREDENTIAL ekm_tde_cred   
    WITH IDENTITY = 'Identity2'   
    , SECRET = 'jeksi84&sLksi01@s'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
  
    -- Add a login used by TDE, and add the new credential to the login.  
    CREATE LOGIN EKM_Login   
    FROM ASYMMETRIC KEY ekm_login_key ;  
    GO  
    ALTER LOGIN EKM_Login   
    ADD CREDENTIAL ekm_tde_cred ;  
    GO  
  
    -- Create the database encryption key that will be used for TDE.  
    USE AdventureWorks2012 ;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM  = AES_128  
    ENCRYPTION BY SERVER ASYMMETRIC KEY ekm_login_key ;  
    GO  
  
    -- Alter the database to enable transparent data encryption.  
    ALTER DATABASE AdventureWorks2012   
    SET ENCRYPTION ON ;  
    GO  
    ```  
  
 <span data-ttu-id="850a1-144">Pour plus d’informations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="850a1-144">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="850a1-145">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="850a1-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
-   [<span data-ttu-id="850a1-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="850a1-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)  
  
-   [<span data-ttu-id="850a1-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="850a1-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="850a1-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="850a1-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)  
  
-   [<span data-ttu-id="850a1-149">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="850a1-149">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
-   [<span data-ttu-id="850a1-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="850a1-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="850a1-151">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="850a1-151">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
-   [<span data-ttu-id="850a1-152">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="850a1-152">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
-   [<span data-ttu-id="850a1-153">Gestion de clés extensible à l’aide d’Azure Key Vault &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="850a1-153">Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;</span></span>](extensible-key-management-using-azure-key-vault-sql-server.md)  
  
-   [<span data-ttu-id="850a1-154">Transparent Data Encryption avec Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="850a1-154">Transparent Data Encryption with Azure SQL Database</span></span>](../../../database-engine/transparent-data-encryption-with-azure-sql-database.md)  
  
  
