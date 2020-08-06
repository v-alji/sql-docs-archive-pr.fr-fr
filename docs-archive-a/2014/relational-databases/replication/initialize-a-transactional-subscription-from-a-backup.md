---
title: Initialiser un abonnement transactionnel à partir d’une sauvegarde (programmation Transact-SQL de la réplication) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: d0637fc4-27cc-4046-98ea-dc86b7a3bd75
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1563d58f2d54f77680781e22a162112ade1658e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601328"
---
# <a name="initialize-a-transactional-subscription-from-a-backup-replication-transact-sql-programming"></a><span data-ttu-id="7f763-102">Initialiser un abonnement transactionnel à partir d'une sauvegarde (programmation Transact-SQL de la réplication)</span><span class="sxs-lookup"><span data-stu-id="7f763-102">Initialize a Transactional Subscription from a Backup (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="7f763-103">Bien qu'un abonnement à une publication transactionnelle soit en général initialisé à l'aide d'un instantané, il est possible d'initialiser un abonnement à partir d'une sauvegarde en utilisant les procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="7f763-103">Although a subscription to a transactional publication is typically initialized with a snapshot, a subscription can be initialized from a backup using replication stored procedures.</span></span> <span data-ttu-id="7f763-104">Pour plus d’informations, consultez [Initialiser un abonnement transactionnel sans instantané](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="7f763-104">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
### <a name="to-initialize-a-transactional-subscriber-from-a-backup"></a><span data-ttu-id="7f763-105">Pour initialiser un Abonné transactionnel à partir d'une sauvegarde</span><span class="sxs-lookup"><span data-stu-id="7f763-105">To initialize a transactional subscriber from a backup</span></span>  
  
1.  <span data-ttu-id="7f763-106">Pour une publication existante, vérifiez que la publication prend en charge la capacité d’initialiser à partir d’une sauvegarde en exécutant [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="7f763-106">For an existing publication, ensure that the publication supports the ability to initialize from backup by executing [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="7f763-107">Notez la valeur de **allow_initialize_from_backup** dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="7f763-107">Note the value of **allow_initialize_from_backup** in the result set.</span></span>  
  
    -   <span data-ttu-id="7f763-108">Si la valeur est **1**, la publication prend en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="7f763-108">If the value is **1**, the publication supports this functionality.</span></span>  
  
    -   <span data-ttu-id="7f763-109">Si la valeur est **0**, exécutez [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) au niveau du serveur de publication sur la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="7f763-109">If the value is **0**, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="7f763-110">Spécifiez une valeur de **allow_initialize_from_backup** pour \*\* \@ propriété\*\* et une valeur `true` pour \*\* \@ valeur\*\*.</span><span class="sxs-lookup"><span data-stu-id="7f763-110">Specify a value of **allow_initialize_from_backup** for **\@property** and a value of `true` for **\@value**.</span></span>  
  
2.  <span data-ttu-id="7f763-111">Pour une nouvelle publication, exécutez [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) au niveau du serveur de publication sur la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="7f763-111">For a new publication, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="7f763-112">Spécifiez une valeur `true` pour **allow_initialize_from_backup**.</span><span class="sxs-lookup"><span data-stu-id="7f763-112">Specify a value of `true` for **allow_initialize_from_backup**.</span></span> <span data-ttu-id="7f763-113">Pour plus d’informations, voir [Create a Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="7f763-113">For more information, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="7f763-114">Afin d'éviter les données d'abonnés manquantes, lorsque vous utilisez **sp_addpublication** avec `@allow_initialize_from_backup = N'true'`, utilisez toujours `@immediate_sync = N'true'`.</span><span class="sxs-lookup"><span data-stu-id="7f763-114">To avoid missing subscriber data, when using **sp_addpublication** with `@allow_initialize_from_backup = N'true'`, always use `@immediate_sync = N'true'`.</span></span>  
  
3.  <span data-ttu-id="7f763-115">Créez une sauvegarde de la base de données de publication à l’aide de l’instruction [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7f763-115">Create a backup of the publication database using the [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
4.  <span data-ttu-id="7f763-116">Restaurez la sauvegarde sur l’Abonné à l’aide de l’instruction [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7f763-116">Restore the backup on the Subscriber using the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement.</span></span>  
  
5.  <span data-ttu-id="7f763-117">Exécutez la procédure stockée [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) sur la base de données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="7f763-117">At the Publisher on the publication database, execute the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="7f763-118">Spécifiez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="7f763-118">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="7f763-119">\*\* \@ sync_type\*\* : valeur **Initialize with backup**.</span><span class="sxs-lookup"><span data-stu-id="7f763-119">**\@sync_type** - a value of **initialize with backup**.</span></span>  
  
    -   <span data-ttu-id="7f763-120">\*\* \@ BackupDeviceType\*\* : type d’unité de sauvegarde : **logique** (par défaut), **disque**ou **bande**.</span><span class="sxs-lookup"><span data-stu-id="7f763-120">**\@backupdevicetype** - the type of backup device: **logical** (default), **disk**, or **tape**.</span></span>  
  
    -   <span data-ttu-id="7f763-121">\*\* \@ backupdevicename\*\* : unité de sauvegarde logique ou physique à utiliser pour la restauration.</span><span class="sxs-lookup"><span data-stu-id="7f763-121">**\@backupdevicename** - the logical or physical backup device to use for the restore.</span></span>  
  
         <span data-ttu-id="7f763-122">Pour une unité logique, spécifiez le nom de l'unité de sauvegarde qui a été spécifié quand **sp_addumpdevice** a été utilisé pour créer l'unité.</span><span class="sxs-lookup"><span data-stu-id="7f763-122">For a logical device, specify the name of the backup device specified when **sp_addumpdevice** was used to create the device.</span></span>  
  
         <span data-ttu-id="7f763-123">Pour une unité physique, spécifiez un chemin d'accès complet et un nom de fichier, tels que `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` ou `TAPE = '\\.\TAPE0'`;</span><span class="sxs-lookup"><span data-stu-id="7f763-123">For a physical device, specify a complete path and file name, such as `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` or `TAPE = '\\.\TAPE0'`.</span></span>  
  
    -   <span data-ttu-id="7f763-124">Facultatif \*\* \@ mot de passe\*\* : mot de passe qui a été fourni lors de la création du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7f763-124">(Optional) **\@password** - a password that was provided when the backup set was created.</span></span>  
  
    -   <span data-ttu-id="7f763-125">Facultatif \*\* \@ MEDIAPASSWORD\*\* : mot de passe qui a été fourni lors de la mise en forme du support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="7f763-125">(Optional) **\@mediapassword** - a password that was provided when the media set was formatted.</span></span>  
  
    -   <span data-ttu-id="7f763-126">Facultatif \*\* \@ fileidhint –\*\* : identificateur du jeu de sauvegarde à restaurer.</span><span class="sxs-lookup"><span data-stu-id="7f763-126">(Optional) **\@fileidhint** - identifier for the backup set to be restored.</span></span> <span data-ttu-id="7f763-127">Par exemple, la valeur **1** indique le premier jeu de sauvegarde sur le support de sauvegarde et la valeur **2** le second jeu de sauvegarde ;</span><span class="sxs-lookup"><span data-stu-id="7f763-127">For example, specifying **1** indicates the first backup set on the backup medium and **2** indicates the second backup set.</span></span>  
  
    -   <span data-ttu-id="7f763-128">(Facultatif pour les périphériques à bandes) \*\* \@ décharger\*\* -spécifiez la valeur **1** (valeur par défaut) si la bande doit être déchargée du lecteur une fois la restauration terminée et **0** si elle ne doit pas être déchargée.</span><span class="sxs-lookup"><span data-stu-id="7f763-128">(Optional for tape devices) **\@unload** - specify a value of **1** (default) if the tape should be unloaded from the drive after the restore is complete and **0** if it should not be unloaded.</span></span>  
  
6.  <span data-ttu-id="7f763-129">(Facultatif) Pour un abonnement par extraction, exécutez [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) et [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) au niveau de l’abonné sur la base de données d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="7f763-129">(Optional) For a pull subscription, execute [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) and [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="7f763-130">Pour plus d’informations, consultez [Créer un abonnement par extraction de données (pull)](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="7f763-130">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
7.  <span data-ttu-id="7f763-131">(Facultatif) Démarrez l'Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="7f763-131">(Optional) Start the Distribution Agent.</span></span> <span data-ttu-id="7f763-132">Pour plus d'informations, consultez [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) ou [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="7f763-132">For more information, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) or [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f763-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f763-133">See Also</span></span>  
 <span data-ttu-id="7f763-134">[Copier des bases de données avec la sauvegarde et la restauration](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="7f763-134">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="7f763-135">Sauvegarder et restaurer des bases de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="7f763-135">Back Up and Restore of SQL Server Databases</span></span>](../backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
  
