---
title: Créer une sauvegarde chiffrée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: e29061d3-c2ab-4d98-b9be-8e90a11d17fe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d46cc686684d87fe393a5db7cfe01194ae917836
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707635"
---
# <a name="create-an-encrypted-backup"></a><span data-ttu-id="3eb40-102">Créer une sauvegarde chiffrée</span><span class="sxs-lookup"><span data-stu-id="3eb40-102">Create an Encrypted Backup</span></span>
  <span data-ttu-id="3eb40-103">Cette rubrique décrit les étapes nécessaires pour créer une sauvegarde chiffrée à l'aide de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="3eb40-103">This topic describes the steps necessary to create an encrypted backup using Transact-SQL.</span></span>  
  
## <a name="backup-to-disk-with-encryption"></a><span data-ttu-id="3eb40-104">Sauvegarde sur disque avec chiffrement</span><span class="sxs-lookup"><span data-stu-id="3eb40-104">Backup to Disk with Encryption</span></span>  
 <span data-ttu-id="3eb40-105">**Configuration requise :**</span><span class="sxs-lookup"><span data-stu-id="3eb40-105">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="3eb40-106">Accès à un disque local ou à un stockage disposant de l'espace approprié pour créer une sauvegarde de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3eb40-106">Access to a local disk or to storage with adequate space to create a backup of the database.</span></span>  
  
-   <span data-ttu-id="3eb40-107">Une clé principale de base de données pour la base de données master, et un certificat ou une clé asymétrique disponible sur l'instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3eb40-107">A Database Master Key for the master database, and a certificate or asymmetric key available on the instance of SQL Server.</span></span> <span data-ttu-id="3eb40-108">Pour les conditions et les autorisations de chiffrement, consultez [Backup Encryption](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="3eb40-108">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
 <span data-ttu-id="3eb40-109">Utilisez la procédure suivante pour créer une sauvegarde chiffrée d'une base de données sur un disque local.</span><span class="sxs-lookup"><span data-stu-id="3eb40-109">Use the following steps to create an encrypted backup of a database to a local disk.</span></span> <span data-ttu-id="3eb40-110">Cet exemple utilise une base de données utilisateur appelée MyTestDB.</span><span class="sxs-lookup"><span data-stu-id="3eb40-110">This example uses a user database called MyTestDB.</span></span>  
  
1.  <span data-ttu-id="3eb40-111">**Créer une clé principale de base de données de la base de données MASTER :** Choisissez un mot de passe pour chiffrer la copie de la clé principale qui sera stockée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3eb40-111">**Create a Database Master Key of the master database:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="3eb40-112">Connectez-vous au moteur de base de données, ouvrez une nouvelle fenêtre de requête, copiez et collez l'exemple, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3eb40-112">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.   
    -- The key is encrypted using the password "<master key password>"  
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
2.  <span data-ttu-id="3eb40-113">**Créer un certificat de sauvegarde :** Créez un certificat de sauvegarde dans la base de données MASTER.</span><span class="sxs-lookup"><span data-stu-id="3eb40-113">**Create a Backup Certificate:** Create a backup certificate in the master database.</span></span> <span data-ttu-id="3eb40-114">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3eb40-114">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
    ```  
    Use Master  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDB Backup Encryption Certificate';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="3eb40-115">**Sauvegarder la base de données :** Spécifiez l'algorithme de chiffrement et le certificat à utiliser.</span><span class="sxs-lookup"><span data-stu-id="3eb40-115">**Backup the database:** Specify the encryption algorithm and certificate to use.</span></span> <span data-ttu-id="3eb40-116">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3eb40-116">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO DISK = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      COMPRESSION,  
      ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
 <span data-ttu-id="3eb40-117">Pour obtenir un exemple de chiffrement d’une sauvegarde protégée par une gestion de clés extensible, consultez [Gestion de clés extensible à l’aide d’Azure Key Vault &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3eb40-117">For an example of encrypting a backup protected by an EKM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](../security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
### <a name="backup-to-azure-storage-with-encryption"></a><span data-ttu-id="3eb40-118">Sauvegarder dans le Stockage Azure avec chiffrement</span><span class="sxs-lookup"><span data-stu-id="3eb40-118">Backup to Azure Storage with Encryption</span></span>  
 <span data-ttu-id="3eb40-119">Si vous créez une sauvegarde dans le stockage Azure à l’aide de l’option **Sauvegarde SQL Server vers une URL**, les étapes de chiffrement sont identiques, mais vous devez utiliser l’URL de destination et les informations d’identification SQL pour l’authentification dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="3eb40-119">If you are creating a backup to Azure storage using the **SQL Server Backup to URL** option, the encryption steps are the same, but you must use URL as the destination and a SQL Credential to authenticate to the Azure storage.</span></span> <span data-ttu-id="3eb40-120">Si vous souhaitez configurer à l' [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] aide des options de chiffrement, consultez Configuration de la [SQL Server gestion de la sauvegarde sur Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) et [configuration d’SQL Server sauvegarde managée sur Azure pour les groupes de disponibilité](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="3eb40-120">If you want to configure [!INCLUDE[ss_smartbackup](../../includes/ss-smartbackup-md.md)] with encryption options, see [Setting up SQL Server Managed Backup to Azure](enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 <span data-ttu-id="3eb40-121">**Configuration requise :**</span><span class="sxs-lookup"><span data-stu-id="3eb40-121">**Prerequisites:**</span></span>  
  
-   <span data-ttu-id="3eb40-122">Un compte de stockage Windows et un conteneur.</span><span class="sxs-lookup"><span data-stu-id="3eb40-122">A windows storage account and a container.</span></span> <span data-ttu-id="3eb40-123">Pour plus d'informations, consultez</span><span class="sxs-lookup"><span data-stu-id="3eb40-123">For more information, see.</span></span> <span data-ttu-id="3eb40-124">[Leçon 1 : Créer des objets de stockage Azure](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span><span class="sxs-lookup"><span data-stu-id="3eb40-124">[Lesson 1: Create Azure Storage Objects](../../tutorials/lesson-1-create-windows-azure-storage-objects.md).</span></span>  
  
-   <span data-ttu-id="3eb40-125">Une clé principale de base de données pour la base de données master, et un certificat ou une clé asymétrique sur l'instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3eb40-125">A Database Master Key for the master database, and a certificate or asymmetric key  on the instance of SQL Server.</span></span> <span data-ttu-id="3eb40-126">Pour les conditions et les autorisations de chiffrement, consultez [Backup Encryption](backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="3eb40-126">For encryption requirements and permissions, see [Backup Encryption](backup-encryption.md).</span></span>  
  
1.  <span data-ttu-id="3eb40-127">**Créer des informations d’identification SQL Server :** Pour créer des informations d'identification SQL Server, connectez-vous au moteur de base de données, ouvrez une nouvelle fenêtre de requête, copiez et collez l'exemple suivant, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3eb40-127">**Create SQL Server Credential:** To create a SQL Server credential, connect to the Database Engine, open a new query window, and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account    
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account  
    ```  
  
2.  <span data-ttu-id="3eb40-128">**Créer une clé principale de base de données :** Choisissez un mot de passe pour chiffrer la copie de la clé principale qui sera stockée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3eb40-128">**Create a Database Master Key:** Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span> <span data-ttu-id="3eb40-129">Connectez-vous au moteur de base de données, ouvrez une nouvelle fenêtre de requête, copiez et collez l'exemple, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3eb40-129">Connect to the database engine, start a new query windows and copy and paste the following example and click **Execute**.</span></span>  
  
    ```  
    -- Creates a database master key.  
    -- The key is encrypted using the password "<master key password>"  
    USE Master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<master key password>';  
    GO  
  
    ```  
  
3.  <span data-ttu-id="3eb40-130">**Créer un certificat de sauvegarde :** Créez un certificat de sauvegarde dans la base de données MASTER.</span><span class="sxs-lookup"><span data-stu-id="3eb40-130">**Create a Backup Certificate:** Create a Backup Certificate in the master database.</span></span> <span data-ttu-id="3eb40-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3eb40-131">Copy and paste the following example in the query window and click **Execute**</span></span>  
  
    ```  
    USE Master;  
    GO  
    CREATE CERTIFICATE MyTestDBBackupEncryptCert  
       WITH SUBJECT = 'MyTestDBBackupEncryptCert ';  
    GO  
  
    ```  
  
4.  <span data-ttu-id="3eb40-132">**Sauvegarder la base de données :** Spécifiez l'algorithme de chiffrement et le certificat à utiliser.</span><span class="sxs-lookup"><span data-stu-id="3eb40-132">**Backup the database:** Specify the encryption algorithm and the certificate to use.</span></span> <span data-ttu-id="3eb40-133">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3eb40-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE [MyTestDB]  
    TO URL = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Backup\MyTestDB.bak'  
    WITH  
      CREDENTIAL 'mycredential' - this is the name of the credential created in the first step.  
      ,COMPRESSION  
      ,ENCRYPTION   
       (  
       ALGORITHM = AES_256,  
       SERVER CERTIFICATE = MyTestDBBackupEncryptCert  
       ),  
      STATS = 10  
    GO  
  
    ```  
  
  
