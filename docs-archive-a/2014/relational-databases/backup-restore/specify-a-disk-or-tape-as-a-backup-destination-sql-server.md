---
title: Spécifier un disque ou une bande comme destination de sauvegarde (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
- backups [SQL Server], creating
- tape backup devices, backing up
ms.assetid: e391f452-ed8c-4b40-b846-ac3881271b94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a0f8ec5d9741e42f3b7d8eda8ebdba23622982d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699786"
---
# <a name="specify-a-disk-or-tape-as-a-backup-destination-sql-server"></a><span data-ttu-id="d97ee-102">Spécifier un disque ou une bande comme destination de sauvegarde (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d97ee-102">Specify a Disk or Tape As a Backup Destination (SQL Server)</span></span>
  <span data-ttu-id="d97ee-103">Cette rubrique explique comment spécifier un disque ou une bande comme destination de sauvegarde dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d97ee-103">This topic describes how to specify a disk or tape as a backup destination in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d97ee-104">La prise en charge des unités de sauvegarde sur bande sera supprimée dans une prochaine version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d97ee-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="d97ee-105">Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="d97ee-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="d97ee-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d97ee-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d97ee-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d97ee-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d97ee-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d97ee-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d97ee-109">**Pour spécifier un disque ou une bande comme destination de sauvegarde, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="d97ee-109">**To specify a disk or tape as a backup destination, using:**</span></span>  
  
     [<span data-ttu-id="d97ee-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d97ee-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d97ee-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d97ee-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d97ee-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d97ee-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d97ee-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d97ee-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d97ee-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d97ee-114">Permissions</span></span>  
 <span data-ttu-id="d97ee-115">Les autorisations BACKUP DATABASE et BACKUP LOG reviennent par défaut aux membres du rôle serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="d97ee-115">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="d97ee-116">Des problèmes de propriété et d'autorisations sur le fichier physique de l'unité de sauvegarde sont susceptibles de perturber une opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d97ee-116">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d97ee-117">doit être en mesure de lire et d'écrire sur l'unité ; le compte sous lequel le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute doit avoir des autorisations d'écriture.</span><span class="sxs-lookup"><span data-stu-id="d97ee-117">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="d97ee-118">Toutefois, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), qui ajoute une entrée pour une unité de sauvegarde dans les tables système, ne vérifie pas les autorisations d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="d97ee-118">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="d97ee-119">De tels problèmes pour le fichier physique de l'unité de sauvegarde peuvent n'apparaître que lorsque la ressource physique est sollicitée au moment de la sauvegarde ou de la restauration.</span><span class="sxs-lookup"><span data-stu-id="d97ee-119">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d97ee-120">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d97ee-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="d97ee-121">Pour spécifier un disque ou une bande comme destination de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="d97ee-121">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="d97ee-122">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="d97ee-122">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="d97ee-123">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="d97ee-123">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="d97ee-124">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**.</span><span class="sxs-lookup"><span data-stu-id="d97ee-124">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="d97ee-125">La boîte de dialogue **Sauvegarder la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="d97ee-125">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="d97ee-126">Dans la section **Destination** de la page **Général** , cliquez sur **Disque** ou sur **Bande**.</span><span class="sxs-lookup"><span data-stu-id="d97ee-126">In the **Destination** section of the **General** page, click **Disk** or **Tape**.</span></span> <span data-ttu-id="d97ee-127">Pour sélectionner les chemins d'accès à 64 lecteurs de bande ou de disque au maximum contenant un seul support de sauvegarde, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d97ee-127">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span>  
  
     <span data-ttu-id="d97ee-128">Pour supprimer une destination de sauvegarde, sélectionnez-la, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="d97ee-128">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="d97ee-129">Pour afficher le contenu d'une destination de sauvegarde, sélectionnez-la, puis cliquez sur **Sommaire**.</span><span class="sxs-lookup"><span data-stu-id="d97ee-129">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d97ee-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d97ee-130">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="d97ee-131">Pour spécifier un disque ou une bande comme destination de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="d97ee-131">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="d97ee-132">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d97ee-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d97ee-133">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d97ee-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d97ee-134">Dans l'instruction [BACKUP](/sql/t-sql/statements/backup-transact-sql) , spécifiez le fichier ou l'unité et son nom physique.</span><span class="sxs-lookup"><span data-stu-id="d97ee-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the file or device and its physical name.</span></span> <span data-ttu-id="d97ee-135">Cet exemple sauvegarde la base de données `AdventureWorks2012` dans le fichier disque `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span><span class="sxs-lookup"><span data-stu-id="d97ee-135">This example backs up the `AdventureWorks2012` database to the disk file `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d97ee-136"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d97ee-136">See Also</span></span>  
 <span data-ttu-id="d97ee-137">[Sauvegarder un journal des transactions &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d97ee-137">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="d97ee-138">[Sauvegarder des fichiers et des groupes de fichiers &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d97ee-138">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="d97ee-139">[Définir une unité de sauvegarde logique pour un fichier de disque &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d97ee-139">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 <span data-ttu-id="d97ee-140">[Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d97ee-140">[Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="d97ee-141">Définir une unité de sauvegarde logique pour un lecteur de bande &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d97ee-141">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
