---
title: Bonnes pratiques en matière de sauvegarde SQL Server vers une URL et résolution des problèmes associés | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: de676bea-cec7-479d-891a-39ac8b85664f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06127b5e4b422750554c30fae23b6190107cb643
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611127"
---
# <a name="sql-server-backup-to-url-best-practices-and-troubleshooting"></a><span data-ttu-id="2ae7b-102">Meilleures pratiques et dépannage de sauvegarde SQL Server vers une URL</span><span class="sxs-lookup"><span data-stu-id="2ae7b-102">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>
  <span data-ttu-id="2ae7b-103">Cette rubrique présente des bonnes pratiques et des conseils de dépannage pour la sauvegarde et la restauration SQL Server dans le service Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-103">This topic includes best practices and troubleshooting tips for SQL Server backup and restores to the Azure Blob service.</span></span>  
  
 <span data-ttu-id="2ae7b-104">Pour plus d’informations sur l’utilisation du service de stockage Blob Azure pour les opérations de sauvegarde et de restauration SQL Server, consultez :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-104">For more information about using Azure Blob storage service for SQL Server backup or restore operations, see:</span></span>  
  
-   [<span data-ttu-id="2ae7b-105">Sauvegarde et restauration SQL Server avec le service Stockage Blob Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="2ae7b-105">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
-   [<span data-ttu-id="2ae7b-106">Tutoriel : Sauvegarde et restauration SQL Server avec le service Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="2ae7b-106">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="managing-backups"></a><span data-ttu-id="2ae7b-107">Gestion des sauvegardes</span><span class="sxs-lookup"><span data-stu-id="2ae7b-107">Managing Backups</span></span>  
 <span data-ttu-id="2ae7b-108">La liste suivante comprend des recommandations générales sur la gestion des sauvegardes :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-108">The following list includes general recommendations to manage backups:</span></span>  
  
-   <span data-ttu-id="2ae7b-109">Nous vous recommandons d'utiliser un nom de fichier unique pour chaque sauvegarde afin d'éviter tout remplacement accidentel des objets blob.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-109">Unique file name for every backup is recommended to prevent accidentally overwriting the blobs.</span></span>  
  
-   <span data-ttu-id="2ae7b-110">Lors de la création d'un conteneur, nous vous recommandons de configurer le niveau d'accès sur **Privé**, afin que seuls les utilisateurs ou comptes qui peuvent fournir les informations d'identification requises puissent lire ou écrire les objets blob dans le conteneur.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-110">When creating a container, it is recommended that you set the access level to **private**, so only users or accounts that can provide the required authentication information can read or write the blobs in the container.</span></span>  
  
-   <span data-ttu-id="2ae7b-111">Pour SQL Server bases de données sur une instance de SQL Server s’exécutant sur une machine virtuelle Azure, utilisez un compte de stockage dans la même région que la machine virtuelle afin d’éviter les coûts de transfert de données entre les régions.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-111">For SQL Server databases on an instance of SQL Server running in an Azure Virtual Machine, use a storage account in the same region as the virtual machine to avoid data transfer costs between regions.</span></span> <span data-ttu-id="2ae7b-112">L'utilisation de la même région garantit également des performances optimales pour les opérations de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-112">Using the same region also ensures optimal performance for backup and restore operations.</span></span>  
  
-   <span data-ttu-id="2ae7b-113">L'échec d'une activité de sauvegarde peut générer un fichier de sauvegarde non valide.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-113">Failed backup activity can result in an invalid backup file.</span></span> <span data-ttu-id="2ae7b-114">Nous vous recommandons d'identifier périodiquement les sauvegardes en échec et de supprimer les fichiers d'objets blob.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-114">We recommend periodic identification of failed backups and deleting the blob files.</span></span> <span data-ttu-id="2ae7b-115">Pour plus d'informations, consultez [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span><span class="sxs-lookup"><span data-stu-id="2ae7b-115">For more information, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
-   <span data-ttu-id="2ae7b-116">L'utilisation de `WITH COMPRESSION` pendant la sauvegarde peut réduire les coûts du stockage et des transactions de stockage.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-116">Using the `WITH COMPRESSION` option during backup can minimize your storage costs and storage transaction costs.</span></span> <span data-ttu-id="2ae7b-117">Elle peut également réduire le temps nécessaire pour terminer le processus de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-117">It can also decrease the time taken to complete the backup process.</span></span>  
  
## <a name="handling-large-files"></a><span data-ttu-id="2ae7b-118">Gestion des fichiers volumineux</span><span class="sxs-lookup"><span data-stu-id="2ae7b-118">Handling Large Files</span></span>  
  
-   <span data-ttu-id="2ae7b-119">L’opération de sauvegarde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise plusieurs threads pour optimiser le transfert de données vers les services de stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup operation uses multiple threads to optimize data transfer to Azure Blob storage services.</span></span>  <span data-ttu-id="2ae7b-120">Toutefois, les performances dépendent de divers facteurs, tels que la bande passante de l'éditeur de logiciels et la taille de la base de données.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-120">However the performance depends on various factors, such as ISV bandwidth and size of the database.</span></span> <span data-ttu-id="2ae7b-121">Si vous envisagez de sauvegarder des bases de données ou groupes de fichiers volumineux à partir d'une base de données SQL Server locale, nous vous recommandons de commencer par tester le débit.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-121">If you plan to back up large databases or filegroups from an on-premise SQL Server database, it is recommended that you do some throughput testing first.</span></span> <span data-ttu-id="2ae7b-122">Les [contrats SLA de stockage Azure](https://go.microsoft.com/fwlink/?LinkId=271619) ont des durées de traitement maximales pour les objets BLOB que vous pouvez prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-122">[Azure storage SLA's](https://go.microsoft.com/fwlink/?LinkId=271619) have maximum processing times for blobs that you can take into consideration.</span></span>  
  
-   <span data-ttu-id="2ae7b-123">L'utilisation de l'option `WITH COMPRESSION`, comme recommandé dans la section **Gestion de la sauvegarde**, est très importante lors de la sauvegarde de fichiers volumineux.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-123">Using the `WITH COMPRESSION` option as recommended in the **Managing Backup** section, it is very important when backing up large files.</span></span>  
  
## <a name="troubleshooting-backup-to-or-restore-from-url"></a><span data-ttu-id="2ae7b-124">Dépannage des problèmes de sauvegarde vers une URL ou de restauration depuis une URL</span><span class="sxs-lookup"><span data-stu-id="2ae7b-124">Troubleshooting Backup To or Restore from URL</span></span>  
 <span data-ttu-id="2ae7b-125">Voici quelques méthodes rapides qui vous aideront à résoudre les erreurs survenant lors de la sauvegarde ou de la restauration vers/depuis le service de stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-125">Following are some quick ways to troubleshoot errors when backing up to or restoring from the Azure Blob storage service.</span></span>  
  
 <span data-ttu-id="2ae7b-126">Pour éviter les erreurs dues à des options ou des limitations non prises en charge, consultez la liste des limitations et la prise en charge des commandes BACKUP et Restore dans l’article [SQL Server la sauvegarde et la restauration avec le service de stockage d’objets BLOB Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) .</span><span class="sxs-lookup"><span data-stu-id="2ae7b-126">To avoid errors due to unsupported options or limitations, review the list of limitations, and support for BACKUP and RESTORE commands information in the [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md) article.</span></span>  
  
 <span data-ttu-id="2ae7b-127">**Erreurs d'authentification :**</span><span class="sxs-lookup"><span data-stu-id="2ae7b-127">**Authentication Errors:**</span></span>  
  
-   <span data-ttu-id="2ae7b-128">WITH CREDENTIAL est une nouvelle option requise pour la sauvegarde ou la restauration à partir du service de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-128">WITH CREDENTIAL is a new option and required to back up to or restore from the Azure Blob storage service.</span></span> <span data-ttu-id="2ae7b-129">Les défaillances liées aux informations d'identification peuvent être les suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-129">Failures related to credential could be the following:</span></span>  
  
     <span data-ttu-id="2ae7b-130">Les informations d'identification spécifiées dans la commande `BACKUP` ou `RESTORE` n'existent pas.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-130">The credential specified in the `BACKUP` or `RESTORE` command does not exist.</span></span> <span data-ttu-id="2ae7b-131">Pour éviter ce problème, vous pouvez inclure des instructions T-SQL afin de créer les informations d'identification si elles n'existent pas dans l'instruction de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-131">To avoid this issue, you can include T-SQL statements to create the credential if one does not exist in the backup statement.</span></span> <span data-ttu-id="2ae7b-132">Voici un exemple que vous pouvez utiliser :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-132">The following is an example you can use:</span></span>  
  
    ```  
    IF NOT EXISTS  
    (SELECT * FROM sys.credentials   
    WHERE credential_identity = 'mycredential')  
    CREATE CREDENTIAL <credential name> WITH IDENTITY = 'mystorageaccount'  
    ,SECRET = '<storage access key> ;  
  
    ```  
  
-   <span data-ttu-id="2ae7b-133">Les informations d'identification existent, mais le compte de connexion utilisé pour exécuter la commande de sauvegarde ne dispose pas des autorisations appropriées pour accéder aux informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-133">The credential exists but the login account that is used to run the backup command does not have permissions to access the credentials.</span></span> <span data-ttu-id="2ae7b-134">Utilisez un compte de connexion dans le rôle **db_backupoperator** avec des autorisations **Modifier des informations d’identification** .</span><span class="sxs-lookup"><span data-stu-id="2ae7b-134">Use a login account in the **db_backupoperator** role with **Alter any credential** permissions.</span></span>  
  
-   <span data-ttu-id="2ae7b-135">Vérifiez le nom du compte de stockage et la valeur des clés.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-135">Verify the storage account name and key values.</span></span> <span data-ttu-id="2ae7b-136">Les informations stockées dans les informations d’identification doivent correspondre aux valeurs de propriétés du compte de stockage Azure utilisé lors des opérations de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-136">The information stored in the credential must match the property values of the Azure storage account you are using in the backup and restore operations.</span></span>  
  
 <span data-ttu-id="2ae7b-137">**Erreurs/Échecs de sauvegarde :**</span><span class="sxs-lookup"><span data-stu-id="2ae7b-137">**Backup Errors/Failures:**</span></span>  
  
-   <span data-ttu-id="2ae7b-138">Les sauvegardes parallèles dans un même objet blob provoquent l'échec d'une des sauvegardes avec l'erreur **Échec de l’initialisation** .</span><span class="sxs-lookup"><span data-stu-id="2ae7b-138">Parallel backups to the same blob cause one of the backups to fail with an **Initialization failed** error.</span></span>  
  
-   <span data-ttu-id="2ae7b-139">Utilisez les journaux d'erreurs suivants pour vous aider à résoudre les erreurs de sauvegarde :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-139">Use the following error logs to help with troubleshooting backup errors:</span></span>  
  
    -   <span data-ttu-id="2ae7b-140">Définissez l'indicateur de trace 3051 pour activer la journalisation dans un journal des erreurs spécifique au format suivant :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-140">Set trace flag 3051 to turn on logging to a specific error log with the following format in:</span></span>  
  
         <span data-ttu-id="2ae7b-141">BackupToUrl- \<instname> - \<dbname> -action- \<PID> . log où \<action> est l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-141">BackupToUrl-\<instname>-\<dbname>-action-\<PID>.log Where \<action> is one of:</span></span>  
  
        -   `DB`  
  
        -   `FILELISTONLY`  
  
        -   `LABELONLY`  
  
        -   `HEADERONLY`  
  
        -   `VERIFYONLY`  
  
    -   <span data-ttu-id="2ae7b-142">Vous pouvez également trouver des informations en examinant le journal des événements Windows, sous les journaux des applications portant le nom « SQLBackupToUrl ».</span><span class="sxs-lookup"><span data-stu-id="2ae7b-142">You can also find information by reviewing the Windows Event Log - Under Application logs with the name 'SQLBackupToUrl'.</span></span>  
  
-   <span data-ttu-id="2ae7b-143">En cas de restauration d'une sauvegarde compressée, vous pouvez rencontrer l'erreur suivante :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-143">When restoring from a compressed backup, you might see the following error:</span></span>  
  
    -   <span data-ttu-id="2ae7b-144">**SqlException 3284 s’est produit. Gravité : 16 État : 5**</span><span class="sxs-lookup"><span data-stu-id="2ae7b-144">**SqlException 3284 occurred. Severity: 16 State: 5**</span></span>  
        <span data-ttu-id="2ae7b-145">**La marque de message sur l’appareil' https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak 'n’est pas alignée. Réexécutez l’instruction RESTORE avec la même taille de bloc que celle utilisée pour créer le jeu de sauvegarde : ' 65536 'ressemble à une valeur possible.**</span><span class="sxs-lookup"><span data-stu-id="2ae7b-145">**Message Filemark on device 'https://mystorage.blob.core.windows.net/mycontainer/TestDbBackupSetNumber2_0.bak' is not aligned. Reissue the Restore statement with the same block size used to create the backupset: '65536' looks like a possible value.**</span></span>  
  
         <span data-ttu-id="2ae7b-146">Pour résoudre cette erreur, réexécutez l'instruction `BACKUP` en spécifiant `BLOCKSIZE = 65536`.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-146">To solve this error, reissue the `BACKUP` statement with `BLOCKSIZE = 65536` specified.</span></span>  
  
-   <span data-ttu-id="2ae7b-147">Erreur lors de la sauvegarde en raison d’objets blob pour lesquels un bail est actif : L’échec d’une activité de sauvegarde peut aboutir à des objets blob avec des bails actifs.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-147">Error during backup due to blobs that have active lease on them: Failed backup activity can result in blobs with active leases.</span></span>  
  
     <span data-ttu-id="2ae7b-148">Si une instruction de sauvegarde est retentée, l'opération de sauvegarde échoue avec une erreur semblable à celle qui suit :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-148">If a backup statement is reattempted, backup operation might fail with an error similar to the following:</span></span>  
  
     <span data-ttu-id="2ae7b-149">**La sauvegarde vers l'URL a reçu une exception du point de terminaison distant. Message d’exception : Le serveur distant a retourné une erreur : (412) Il y a actuellement un bail sur l’objet blob et aucun ID de bail n’a été spécifié dans la requête**.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-149">**Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (412) There is currently a lease on the blob and no lease ID was specified in the request**.</span></span>  
  
     <span data-ttu-id="2ae7b-150">Si une instruction de restauration est tentée sur un fichier de sauvegarde d'objet blob dont le bail est actif, l'opération de restauration échoue avec une erreur semblable à celle qui suit :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-150">If a restore statement is attempted on a backup blob file that has an active lease, the restore operation fails with an error similar to the following:</span></span>  
  
     <span data-ttu-id="2ae7b-151">**Message d'exception : Le serveur distant a retourné une erreur : (409) Conflit.**</span><span class="sxs-lookup"><span data-stu-id="2ae7b-151">**Exception Message: The remote server returned an error: (409) Conflict..**</span></span>  
  
     <span data-ttu-id="2ae7b-152">Lorsqu'une telle erreur se produit, les fichiers d'objets blob doivent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-152">When such error occurs, the blob files need to be deleted.</span></span> <span data-ttu-id="2ae7b-153">Pour plus d'informations sur ce scénario et la résolution du problème, consultez [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span><span class="sxs-lookup"><span data-stu-id="2ae7b-153">For more information on this scenario and how to correct this problem, see [Deleting Backup Blob Files with Active Leases](deleting-backup-blob-files-with-active-leases.md)</span></span>  
  
## <a name="proxy-errors"></a><span data-ttu-id="2ae7b-154">Erreurs de proxy</span><span class="sxs-lookup"><span data-stu-id="2ae7b-154">Proxy Errors</span></span>  
 <span data-ttu-id="2ae7b-155">Si vous utilisez des serveurs proxy pour l'accès à Internet, les erreurs suivantes peuvent survenir :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-155">If you are using Proxy Servers to access the internet, you may see the following issues:</span></span>  
  
 <span data-ttu-id="2ae7b-156">**Limitation de la connexion par les serveurs proxy :**</span><span class="sxs-lookup"><span data-stu-id="2ae7b-156">**Connection throttling by Proxy Servers:**</span></span>  
  
 <span data-ttu-id="2ae7b-157">Les serveurs proxy peuvent avoir des paramètres qui limitent le nombre de connexions par minute.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-157">Proxy Servers can have settings that limit the number of connections per minute.</span></span> <span data-ttu-id="2ae7b-158">Le processus de sauvegarde vers l'URL est un processus multithread et, par conséquent, il peut dépasser cette limite.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-158">The Backup to URL process is a multi-threaded process and hence can go over this limit.</span></span> <span data-ttu-id="2ae7b-159">Si cela se produit, le serveur proxy supprime la connexion.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-159">If this happens, the proxy server kills the connection.</span></span> <span data-ttu-id="2ae7b-160">Pour résoudre ce problème, modifiez les paramètres du proxy afin que SQL Server n'utilise pas le proxy.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-160">To resolve this issue, change the proxy settings so SQL Server is not using the proxy.</span></span>   <span data-ttu-id="2ae7b-161">Voici quelques exemples des types d'erreur ou des messages qui peuvent s'afficher dans le journal des erreurs :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-161">Following are some examples of the types or error messages you may see in the error log:</span></span>  
  
-   <span data-ttu-id="2ae7b-162">Échec de l’écriture sur « http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak » : la sauvegarde vers l’URL a reçu une exception du point de terminaison distant.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-162">Write on "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak" failed: Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="2ae7b-163">Message d'exception : impossible de lire les données de la connexion de transport : la connexion a été fermée.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-163">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
-   <span data-ttu-id="2ae7b-164">Une erreur d’E/S non récupérable s’est produite sur le fichier « http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak: ». L’erreur n’a pas pu être collectée à partir du point de terminaison distant.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-164">A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Error could not be gathered from Remote Endpoint.</span></span>  
  
     <span data-ttu-id="2ae7b-165">Msg 3013, Niveau 16, État 1, Ligne 2</span><span class="sxs-lookup"><span data-stu-id="2ae7b-165">Msg 3013, Level 16, State 1, Line 2</span></span>  
  
     <span data-ttu-id="2ae7b-166">La sauvegarde de base de données s'est terminée anormalement.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-166">BACKUP DATABASE is terminating abnormally.</span></span>  
  
-   <span data-ttu-id="2ae7b-167">BackupIoRequest :: ReportIoError : échec d’écriture sur l’unité de sauvegarde' http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak '.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-167">BackupIoRequest::ReportIoError: write failure on backup device 'http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak'.</span></span> <span data-ttu-id="2ae7b-168">Erreur de système d'exploitation. La sauvegarde vers l'URL a reçu une exception du point de terminaison distant.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-168">Operating system error Backup to URL received an exception from the remote endpoint.</span></span> <span data-ttu-id="2ae7b-169">Message d'exception : impossible de lire les données de la connexion de transport : la connexion a été fermée.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-169">Exception Message: Unable to read data from the transport connection: The connection was closed.</span></span>  
  
 <span data-ttu-id="2ae7b-170">Si vous activez la journalisation détaillée à l'aide de l'indicateur de trace 3051, vous pouvez également voir le message suivant dans les journaux :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-170">If you turn on the verbose logging using the trace flag 3051 you may also see the following message in the logs:</span></span>  
  
 <span data-ttu-id="2ae7b-171">Code d'état HTTP 502, message d'état HTTP, erreur de proxy (le nombre de requêtes HTTP par minute a dépassé la limite configurée.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-171">HTTP status code 502, HTTP Status Message Proxy Error ( The number of HTTP requests per minute exceeded the configured limit.</span></span> <span data-ttu-id="2ae7b-172">Contactez votre administrateur ISA Server.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-172">Contact your ISA Server administrator.</span></span>  <span data-ttu-id="2ae7b-173">)</span><span class="sxs-lookup"><span data-stu-id="2ae7b-173">)</span></span>  
  
 <span data-ttu-id="2ae7b-174">**Les paramètres du proxy par défaut ne sont pas sélectionnés :**</span><span class="sxs-lookup"><span data-stu-id="2ae7b-174">**Default Proxy Settings not picked up:**</span></span>  
  
 <span data-ttu-id="2ae7b-175">Parfois, les paramètres par défaut ne sont pas sélectionnés et provoquent des erreurs d’authentification du proxy telles que celle illustrée ci-dessous :*une erreur d’e/s non récupérable s’est produite dans le fichier « http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak: ». la sauvegarde vers l’URL a reçu une exception du point de terminaison distant. Message d’exception : le serveur distant a retourné une erreur : (407)* **authentification proxy requise**.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-175">Sometimes the default settings are not picked up causing proxy authentication errors such as the one shown below:*A nonrecoverable I/O error occurred on file "http://storageaccount.blob.core.windows.net/container/BackupAzurefile.bak:" Backup to URL received an exception from the remote endpoint. Exception Message: The remote server returned an error: (407)* **Proxy Authentication Required**.</span></span>  
  
 <span data-ttu-id="2ae7b-176">Pour résoudre ce problème, créez un fichier de configuration qui permet au processus de sauvegarde vers l'URL d'utiliser les paramètres du proxy par défaut à l'aide des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-176">To resolve this issue, create a configuration file that allows the Backup to URL process to use the default proxy settings using the following steps:</span></span>  
  
1.  <span data-ttu-id="2ae7b-177">Créez un fichier de configuration nommé BackuptoURL.exe.config avec le code xml suivant :</span><span class="sxs-lookup"><span data-stu-id="2ae7b-177">Create a configuration file named BackuptoURL.exe.config  with the following xml:</span></span>  
  
    ```  
    <?xml version ="1.0"?>  
    <configuration>   
                    <system.net>   
                                    <defaultProxy enabled="true" useDefaultCredentials="true">   
                                                    <proxy usesystemdefault="true" />   
                                    </defaultProxy>   
                    </system.net>  
    </configuration>  
  
    ```  
  
2.  <span data-ttu-id="2ae7b-178">Placez le fichier de configuration dans le dossier Binn de l'instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-178">Place the configuration file in the Binn folder of the SQL Server Instance.</span></span> <span data-ttu-id="2ae7b-179">Par exemple, si mon SQL Server est installé sur le lecteur C de l’ordinateur, placez le fichier de configuration ici : *C:\Program Files\Microsoft SQL Server\MSSQL12. \<InstanceName> \MSSQL\Binn*.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-179">For example, if my SQL Server is installed on the C drive of the machine, place the configuration file here: *C:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Binn*.</span></span>  
  
## <a name="troubleshooting-sql-server-managed-backup-to-azure"></a><span data-ttu-id="2ae7b-180">Dépannage de la sauvegarde managée de SQL Server sur Azure</span><span class="sxs-lookup"><span data-stu-id="2ae7b-180">Troubleshooting SQL Server Managed Backup to Azure</span></span>  
 <span data-ttu-id="2ae7b-181">Étant donné que la sauvegarde managée de SQL Server est générée par dessus la sauvegarde vers l'URL, les conseils de dépannage décrits dans les premières sections s'appliquent aux bases de données ou aux instances qui utilisent la sauvegarde managée de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2ae7b-181">Since SQL Server Managed Backup is built on top of Backup to URL, the troubleshooting tips described in the earlier sections apply to databases or instances using SQL Server Managed Backup.</span></span>  <span data-ttu-id="2ae7b-182">Pour plus d’informations sur la résolution des problèmes SQL Server la gestion de la sauvegarde sur Azure, voir [troubleshooting SQL Server Managed Backup to Azure](sql-server-managed-backup-to-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="2ae7b-182">Information about troubleshooting SQL Server Managed Backup to Azure is described in detail in [Troubleshooting SQL Server Managed  Backup to Azure](sql-server-managed-backup-to-microsoft-azure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae7b-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ae7b-183">See Also</span></span>  
 [<span data-ttu-id="2ae7b-184">Restauration à partir des sauvegardes stockées dans Azure</span><span class="sxs-lookup"><span data-stu-id="2ae7b-184">Restoring From Backups Stored in Azure</span></span>](restoring-from-backups-stored-in-microsoft-azure.md)  
  
  
