---
title: Leçon 5. Facultatif Chiffrer votre base de données à l’aide de TDE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ba793c8f-665a-4c46-b68d-f558a37906b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 613b66c04a69364f3c9be1059f95021dd3eff595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611071"
---
# <a name="lesson-5-optional-encrypt-your-database-using-tde"></a><span data-ttu-id="2641f-103">Leçon 5.</span><span class="sxs-lookup"><span data-stu-id="2641f-103">Lesson 5.</span></span> <span data-ttu-id="2641f-104">(Facultatif) Chiffrer votre base de données avec TDE</span><span class="sxs-lookup"><span data-stu-id="2641f-104">(Optional) Encrypt your database using TDE</span></span>
  <span data-ttu-id="2641f-105">En tant qu'étape facultative, chiffrez la base de données créée.</span><span class="sxs-lookup"><span data-stu-id="2641f-105">As an optional step, you can encrypt the newly created database.</span></span> <span data-ttu-id="2641f-106">Le chiffrement transparent des données (TDE, Transparent Data Encryption) effectue le chiffrement et le déchiffrement des E/S en temps réel des fichiers de données et des fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="2641f-106">Transparent data encryption (TDE) performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="2641f-107">Le type de chiffrement utilise une clé de chiffrement de base de données (DEK), stockée dans l'enregistrement de démarrage de base de données pour être disponible pendant la récupération.</span><span class="sxs-lookup"><span data-stu-id="2641f-107">This kind of encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="2641f-108">Pour plus d’informations, consultez [Transparent Data Encryption &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) et [déplacer une base de données protégée TDE vers une autre SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2641f-108">For more information, see [Transparent Data Encryption &#40;TDE&#41;](security/encryption/transparent-data-encryption.md) and [Move a TDE Protected Database to Another SQL Server](security/encryption/move-a-tde-protected-database-to-another-sql-server.md).</span></span>  
  
 <span data-ttu-id="2641f-109">Cette leçon suppose que vous avez déjà effectué les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="2641f-109">This lesson assumes you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="2641f-110">Vous avez un compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="2641f-110">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="2641f-111">Vous avez créé un conteneur sous votre compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="2641f-111">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="2641f-112">Vous avez créé une stratégie sur un conteneur avec des droits en lecture, écriture et création de liste.</span><span class="sxs-lookup"><span data-stu-id="2641f-112">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="2641f-113">Vous avez également généré une clé SAS.</span><span class="sxs-lookup"><span data-stu-id="2641f-113">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="2641f-114">Vous avez créé des informations d'identification SQL Server sur l'ordinateur source.</span><span class="sxs-lookup"><span data-stu-id="2641f-114">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="2641f-115">Vous avez créé une base de données en suivant la procédure décrite dans la leçon 4.</span><span class="sxs-lookup"><span data-stu-id="2641f-115">You have created a database by following the steps that are described in Lesson 4.</span></span>  
  
 <span data-ttu-id="2641f-116">Si vous souhaitez chiffrer une base de données, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2641f-116">If you want to encrypt a database, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2641f-117">Sur l'ordinateur source, modifiez et exécutez les instructions suivantes dans une fenêtre de requête :</span><span class="sxs-lookup"><span data-stu-id="2641f-117">In the source machine, modify and run the following statements in a query window:</span></span>  
  
    ```  
  
    -- Create a master key and a server certificate   
    USE master   
    GO   
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01';   
    GO   
    CREATE CERTIFICATE MySQLCert WITH SUBJECT = 'SQL - Azure Storage Certification'   
    GO   
    -- Create a backup of the server certificate in the master database.   
    -- Store TDS certificates in the source machine locally.   
    BACKUP CERTIFICATE MySQLCert   
    TO FILE = 'C:\certs\MySQLCert.CER'   
    WITH PRIVATE KEY   
    (   
    FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
    ENCRYPTION BY PASSWORD = 'MySQLKey01'   
    );  
  
    ```  
  
2.  <span data-ttu-id="2641f-118">Ensuite, chiffrez votre nouvelle base de données dans l'ordinateur source en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="2641f-118">Then, encrypt your new database in the source machine by following these steps:</span></span>  
  
    ```  
  
    -- Switch to the new database.   
    -- Create a database encryption key, that is protected by the server certificate in the master database.    
    -- Alter the new database to encrypt the database using TDE.   
    USE TestDB1;   
    GO   
    -- Encrypt your database   
    CREATE DATABASE ENCRYPTION KEY   
    WITH ALGORITHM = AES_256   
    ENCRYPTION BY SERVER CERTIFICATE MySQLCert   
    GO   
  
    ALTER DATABASE TestDB1   
    SET ENCRYPTION ON   
    GO  
  
    ```  
  
 <span data-ttu-id="2641f-119">Si vous voulez connaître l'état de chiffrement d'une base de données et ses clés de chiffrement associées, exécutez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="2641f-119">If you want to learn the encryption state of a database and its associated database encryption keys, run the following statement:</span></span>  
  
```  
  
SELECT * FROM sys.dm_database_encryption_keys;   
GO  
  
```  
  
 <span data-ttu-id="2641f-120">Pour obtenir des informations détaillées sur les instructions Transact-SQL utilisées dans cette leçon, consultez [CREATE DATABASE &#40;SQL Server Transact-sql&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [Create Certificate &#40;transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql)et [sys. dm_database_encryption_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2641f-120">For detailed information the Transact-SQL statements that have been used in this lesson, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql), [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql), [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql), [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql), and [sys.dm_database_encryption_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span></span>  
  
 <span data-ttu-id="2641f-121">**Leçon suivante :**</span><span class="sxs-lookup"><span data-stu-id="2641f-121">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="2641f-122">Leçon 6 : Migrer une base de données d’une machine source locale vers une machine de destination dans Azure</span><span class="sxs-lookup"><span data-stu-id="2641f-122">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>](lesson-5-backup-database-using-file-snapshot-backup.md)  
  
  
