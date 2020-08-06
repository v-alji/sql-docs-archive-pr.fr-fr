---
title: Leçon 9. Restaurer une base de données à partir du stockage Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ebba12c7-3d13-4c9d-8540-ad410a08356d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5e7c2350bb2a9b1f8c31da8e094459b5bc8ccd90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614035"
---
# <a name="lesson-9-restore-a-database-from-azure-storage"></a><span data-ttu-id="565b8-103">Leçon 9.</span><span class="sxs-lookup"><span data-stu-id="565b8-103">Lesson 9.</span></span> <span data-ttu-id="565b8-104">Restaurer une base de données à partir du Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="565b8-104">Restore a database from Azure Storage</span></span>
  <span data-ttu-id="565b8-105">Dans cette leçon, vous allez apprendre à restaurer un fichier de sauvegarde de base de données à partir du stockage Azure dans une base de données, qui réside localement ou dans une machine virtuelle dans Azure.</span><span class="sxs-lookup"><span data-stu-id="565b8-105">In this lesson, you will learn how to restore a database backup file from Azure Storage to a database, which either resides on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="565b8-106">Pour suivre cette leçon, vous n'avez pas besoin de terminer les leçons 4, 5, 6, 7 et 8.</span><span class="sxs-lookup"><span data-stu-id="565b8-106">To follow this lesson, you do not need to complete Lesson 4, 5, 6, 7, and 8.</span></span>  
  
 <span data-ttu-id="565b8-107">Cette leçon suppose que vous avez déjà effectué les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="565b8-107">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="565b8-108">Vous avez créé une base de données sur l'ordinateur source.</span><span class="sxs-lookup"><span data-stu-id="565b8-108">You have created a database in the source machine.</span></span>  
  
-   <span data-ttu-id="565b8-109">Vous avez créé une sauvegarde de votre base de données (. bak) dans le stockage Azure à l’aide de la fonctionnalité [SQL Server sauvegarde et restauration avec le service de stockage d’objets BLOB Azure](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="565b8-109">You have created a backup of your database (.bak) in Azure Storage by using the [SQL Server Backup and Restore with Azure Blob Storage Service](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) feature.</span></span> <span data-ttu-id="565b8-110">Notez que vous devez créer d'autres informations d'identification SQL Server au cours de cette étape.</span><span class="sxs-lookup"><span data-stu-id="565b8-110">Note that you will need to create another SQL Server Credential in this step.</span></span> <span data-ttu-id="565b8-111">Ces informations d'identification utilisent des clés de compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="565b8-111">This credential uses storage account keys.</span></span>  
  
-   <span data-ttu-id="565b8-112">Vous avez un compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="565b8-112">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="565b8-113">Vous avez créé un conteneur sous votre compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="565b8-113">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="565b8-114">Vous avez créé une stratégie sur un conteneur avec des droits en lecture, écriture et création de liste.</span><span class="sxs-lookup"><span data-stu-id="565b8-114">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="565b8-115">Vous avez également généré une clé SAS.</span><span class="sxs-lookup"><span data-stu-id="565b8-115">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="565b8-116">Vous avez créé un SQL Server des informations d’identification sur votre ordinateur pour la fonctionnalité d’intégration du stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="565b8-116">You have created a SQL Server credential on your machine for Azure Storage Integration feature.</span></span> <span data-ttu-id="565b8-117">Notez que ces informations d'identification nécessitent une clé de signature d'accès partagé (SAS).</span><span class="sxs-lookup"><span data-stu-id="565b8-117">Note that this credential requires a Shared Access Signature (SAS) key.</span></span>  
  
 <span data-ttu-id="565b8-118">Pour restaurer une base de données à partir du stockage Azure, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="565b8-118">To restore a database from Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="565b8-119">Exécutez SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="565b8-119">Start SQL Server Management Studio.</span></span> <span data-ttu-id="565b8-120">Connectez-vous à l'instance par défaut.</span><span class="sxs-lookup"><span data-stu-id="565b8-120">Connect to the default instance.</span></span>  
  
2.  <span data-ttu-id="565b8-121">Cliquez sur **nouvelle requête** dans la barre d’outils standard.</span><span class="sxs-lookup"><span data-stu-id="565b8-121">Click **New Query** on the Standard Toolbar.</span></span>  
  
3.  <span data-ttu-id="565b8-122">Copiez et collez la totalité du script suivant dans la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="565b8-122">Copy and paste the following complete script to the query window.</span></span> <span data-ttu-id="565b8-123">Modifiez le script en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="565b8-123">Modify the script as needed.</span></span>  
  
     <span data-ttu-id="565b8-124">**Remarque :** Vous exécutez l' `RESTORE` instruction pour restaurer la sauvegarde de base de données (. bak) dans le stockage Azure vers une instance de base de données sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="565b8-124">**Note:** You run the `RESTORE` statement to restore the database backup (.bak) in Azure Storage to a database instance in another machine.</span></span>  
  
    ```sql  
  
    USE master   
    GO   
    -- Create a new database to be backed up.   
    CREATE DATABASE TestDbRestoreFrom;   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO   
    USE TestDbRestoreFrom;   
    GO   
    SELECT * from dbo.Table1;   
    GO   
    -- Create a credential to be used by SQL Server Backup and Restore with Azure -----Blob Storage Service.   
    USE master;   
    GO   
    CREATE CREDENTIAL BackupCredential    
    WITH IDENTITY= 'teststorageaccnt',   
    SECRET = 'BO1nH/lWRdnc8TGPlQIXmGLWVCoEa48suYSGiAlC73+S0TX5VXo5/LCm8qiyGCYafDg4ZsueDIV3GQ5RXHaRGw=='    
    GO   
    -- Display the newly created credential   
    SELECT * from sys.credentials   
    -- Create a backup in Azure Storage.   
    BACKUP DATABASE TestDBRestoreFrom    
    TO URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
          WITH CREDENTIAL = 'BackupCredential'    
         ,COMPRESSION   
         ,STATS = 5;   
    GO    
    -- Create a Shared Access Signature credential   
    CREATE CREDENTIAL [https://teststorageaccnt.blob.core.windows.net/testrestorefrom]   
    WITH IDENTITY='SHARED ACCESS SIGNATURE',   
    SECRET = 'sv=2012-02-12&sr=c&si=policy_resfrom&sig=EhVpzLUXjG4ThAMLmVhrnoiCt8IfmD3BsuYiMawGzxc%3D'   
    GO   
    USE master;   
    GO   
    RESTORE DATABASE TestDBRestoreFrom    
    FROM URL = 'https://teststorageaccnt.blob.core.windows.net/testrestorefrom/TestDBRestoreFrom.bak'    
    WITH    
    CREDENTIAL = 'BackupCredential',    
    REPLACE,   
    MOVE 'TestDBRestoreFrom' TO 'C:\Backup\TestDBRestoreFrom.mdf',     
    MOVE 'TestDBRestoreFrom_log' TO 'C:\Backup\TestDBRestoreFrom_log.ldf';   
    GO  
  
    ```  
  
 <span data-ttu-id="565b8-125">**Fin du didacticiel : SQL Server de fichiers de données dans le service de stockage Azure**</span><span class="sxs-lookup"><span data-stu-id="565b8-125">**End of Tutorial: SQL Server Data Files in Azure Storage service**</span></span>  
  
  
