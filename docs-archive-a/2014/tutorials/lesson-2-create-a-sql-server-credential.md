---
title: 'Leçon 2 : créer des informations d’identification de SQL Server | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 64f8805c-1ddc-4c96-a47c-22917d12e1ab
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e8b13c8d4d9e5937064cef5503ec64bfd6e4a2d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710064"
---
# <a name="lesson-2-create-a-sql-server-credential"></a><span data-ttu-id="f327d-102">Leçon 2 : Créer des informations d'identification SQL Server</span><span class="sxs-lookup"><span data-stu-id="f327d-102">Lesson 2: Create a SQL Server Credential</span></span>
  <span data-ttu-id="f327d-103">**Informations d’identification :** Les informations d'identification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sont des objets utilisés pour stocker les informations d'authentification requises pour la connexion à une ressource en dehors de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f327d-103">**Credential:** A [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="f327d-104">Ici, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] les processus de sauvegarde et de restauration utilisent les informations d’identification pour s’authentifier auprès du service de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="f327d-104">Here, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="f327d-105">Les informations d'identification contiennent le nom du compte de stockage et ses valeurs de **clé d'accès** .</span><span class="sxs-lookup"><span data-stu-id="f327d-105">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="f327d-106">Une fois les informations d'identification créées, vous devez les spécifier dans l'option WITH CREDENTIAL lorsque vous publiez des instructions BACKUP/RESTORE.</span><span class="sxs-lookup"><span data-stu-id="f327d-106">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="f327d-107">Pour plus d'informations sur l'affichage, la copie ou la régénération des **access keys**de compte de stockage, consultez [Afficher, copier et régénérer les clés d'accès d'un compte de stockage Windows Azure](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="f327d-107">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="f327d-108">Pour obtenir des informations générales sur les informations d’identification, consultez [informations d’identification](../relational-databases/security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="f327d-108">For general information about credentials, see [Credentials](../relational-databases/security/authentication-access/credentials-database-engine.md).</span></span>  
  
 <span data-ttu-id="f327d-109">Pour plus d’informations sur d’autres exemples d’utilisation des informations d’identification, consultez [créer un Proxy SQL Server Agent](../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="f327d-109">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f327d-110">La configuration requise pour la création d’une SQL Server informations d’identification décrites ci-dessous est spécifique aux processus de sauvegarde SQL Server ([SQL Server sauvegarde vers une URL](../relational-databases/backup-restore/sql-server-backup-to-url.md)et [SQL Server la sauvegarde managée dans Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span><span class="sxs-lookup"><span data-stu-id="f327d-110">The requirements for creating a SQL Server credential described below are specific to SQL Server backup processes ([SQL Server Backup to URL](../relational-databases/backup-restore/sql-server-backup-to-url.md), and [SQL Server Managed  Backup to Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span></span> <span data-ttu-id="f327d-111">SQL Server, lorsqu'il accède au stockage Azure pour écrire ou lire des sauvegardes, utilise le nom du compte de stockage et les informations de clé d'accès.</span><span class="sxs-lookup"><span data-stu-id="f327d-111">SQL Server, when accessing Azure storage to write or read backups uses the storage account name and access key information.</span></span>  <span data-ttu-id="f327d-112">Pour plus d'informations sur la création d'informations d'identification pour le stockage des fichiers de base de données dans le stockage Azure, consultez [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)</span><span class="sxs-lookup"><span data-stu-id="f327d-112">For more information on creating credentials for storing database files in Azure storage, see [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)</span></span>  
  
## <a name="create-a-sql-server-credential"></a><span data-ttu-id="f327d-113">Créer des informations d'identification SQL Server</span><span class="sxs-lookup"><span data-stu-id="f327d-113">Create a SQL Server Credential</span></span>  
 <span data-ttu-id="f327d-114">Pour créer des informations d'identification SQL Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f327d-114">To create a SQL Server Credential, use the following steps:</span></span>  
  
1.  <span data-ttu-id="f327d-115">Connectez-vous à SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="f327d-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="f327d-116">Dans l'Explorateur d'objets, connectez-vous à l'instance du moteur de base de données sur lequel la base de données AdventureWorks2012 est installée, ou utilisez la base de données que vous envisagez d'utiliser pour ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="f327d-116">In Object Explorer, connect to the instance of Database Engine that has AdventureWorks2012 database installed, or use your own database you plan to use for this tutorial.</span></span>  
  
3.  <span data-ttu-id="f327d-117">Dans la barre d'outils **standard** , cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f327d-117">On the **Standard** tool bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="f327d-118">Copiez et collez l'exemple suivant dans la fenêtre de requête et modifiez-le si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f327d-118">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account (See Lesson 1)   
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account (See Lesson 1)  
  
    ```  
  
     <span data-ttu-id="f327d-119">![mappage de la compte de stockage à l'information d'identification](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "mappage de la compte de stockage à l'information d'identification")</span><span class="sxs-lookup"><span data-stu-id="f327d-119">![mapping storage account to sql credentials](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
5.  <span data-ttu-id="f327d-120">Vérifiez l’instruction T-SQL et cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f327d-120">Verify the T-SQL statement and click **Execute**.</span></span>  
  
 <span data-ttu-id="f327d-121">Pour plus d’informations sur le service de stockage d’objets BLOB Azure pour les concepts et la configuration requise pour la sauvegarde, consultez [SQL Server la sauvegarde et la restauration avec le service de stockage d’objets BLOB Azure](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="f327d-121">For more information about the Azure Blob storage service for backup concepts and requirements, see [SQL Server Backup and Restore with Azure Blob Storage Service](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="f327d-122">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="f327d-122">Next Lesson</span></span>  
 <span data-ttu-id="f327d-123">[Leçon 3 : écrire une sauvegarde de base de données complète dans le service de stockage d’objets BLOB Azure](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="f327d-123">[Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span></span>  
  
  
