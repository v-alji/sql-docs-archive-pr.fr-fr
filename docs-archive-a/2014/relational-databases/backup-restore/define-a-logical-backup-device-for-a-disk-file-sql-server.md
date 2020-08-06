---
title: Définir une unité de sauvegarde logique pour un lecteur de disque (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
ms.assetid: 86331d43-c738-4523-ae3d-7d6700348ed1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8aa92296da81f984f260deace887c15f13443b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709700"
---
# <a name="define-a-logical-backup-device-for-a-disk-file-sql-server"></a><span data-ttu-id="e2314-102">Définir une unité de sauvegarde logique pour un fichier de disque (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e2314-102">Define a Logical Backup Device for a Disk File (SQL Server)</span></span>
  <span data-ttu-id="e2314-103">Cette rubrique explique comment définir une unité de sauvegarde logique pour un fichier de disque dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2314-103">This topic describes how to define a logical backup device for a disk file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e2314-104">Une unité logique est un nom défini par l'utilisateur qui désigne une unité de sauvegarde physique spécifique (un fichier de disque ou un lecteur de bande).</span><span class="sxs-lookup"><span data-stu-id="e2314-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="e2314-105">L'initialisation de l'unité physique se produit ultérieurement, lorsqu'une sauvegarde est écrite sur l'unité de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="e2314-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
 <span data-ttu-id="e2314-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="e2314-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e2314-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="e2314-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e2314-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="e2314-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e2314-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="e2314-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="e2314-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e2314-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e2314-111">**Pour définir une unité de sauvegarde logique pour un fichier de disque, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="e2314-111">**To define a logical backup device for a disk file, using:**</span></span>  
  
     [<span data-ttu-id="e2314-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e2314-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e2314-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2314-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e2314-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e2314-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e2314-115">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="e2314-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e2314-116">Le nom d'unité logique doit être unique parmi toutes les unités de sauvegarde logiques résidant sur l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="e2314-116">The logical device name must be unique among all the logical backup devices on the server instance.</span></span> <span data-ttu-id="e2314-117">Pour afficher les noms d’unités logiques existantes, interrogez l’affichage catalogue [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e2314-117">To view the existing logical device names, query the [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) catalog view.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="e2314-118">Recommandations</span><span class="sxs-lookup"><span data-stu-id="e2314-118">Recommendations</span></span>  
  
-   <span data-ttu-id="e2314-119">À titre de recommandation, il est préférable que le disque de sauvegarde ne soit pas le même que les disques de données ou de journal de la base de données.</span><span class="sxs-lookup"><span data-stu-id="e2314-119">We recommend that a backup disk be a different disk than the database data and log disks.</span></span> <span data-ttu-id="e2314-120">Ce paramètre est primordial pour garantir l'accès aux sauvegardes en cas d'échec du disque de données ou de journal.</span><span class="sxs-lookup"><span data-stu-id="e2314-120">This is necessary to make sure that you can access the backups if the data or log disk fails.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e2314-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e2314-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e2314-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="e2314-122">Permissions</span></span>  
 <span data-ttu-id="e2314-123">Nécessite l'appartenance au rôle serveur fixe **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="e2314-123">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="e2314-124">Requiert l'autorisation d'écrire sur le disque.</span><span class="sxs-lookup"><span data-stu-id="e2314-124">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e2314-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e2314-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-disk-file"></a><span data-ttu-id="e2314-126">Pour définir une unité de sauvegarde logique pour un fichier de disque</span><span class="sxs-lookup"><span data-stu-id="e2314-126">To define a logical backup device for a disk file</span></span>  
  
1.  <span data-ttu-id="e2314-127">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="e2314-127">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="e2314-128">Développez **Objets serveur**, puis cliquez avec le bouton droit sur **Unités de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="e2314-128">Expand **Server Objects**, and right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="e2314-129">Cliquez sur **Nouvelle unité de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="e2314-129">Click **New Backup Device**.</span></span> <span data-ttu-id="e2314-130">La boîte de dialogue **Unité de sauvegarde** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="e2314-130">The **Backup Device** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="e2314-131">Entrez un nom d'unité.</span><span class="sxs-lookup"><span data-stu-id="e2314-131">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="e2314-132">Pour la destination, cliquez sur **Fichier** et spécifiez le chemin d'accès complet du fichier.</span><span class="sxs-lookup"><span data-stu-id="e2314-132">For the destination, click **File** and specify the full path of the file.</span></span>  
  
6.  <span data-ttu-id="e2314-133">Pour définir la nouvelle unité, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2314-133">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="e2314-134">Pour procéder à une sauvegarde sur cette nouvelle unité, ajoutez-la au champ **Sauvegarde sur** dans la boîte de dialogue **Sauvegarder la base de données** (**Général**).</span><span class="sxs-lookup"><span data-stu-id="e2314-134">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="e2314-135">Pour plus d’informations, consultez [Créer une sauvegarde complète de base de données &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e2314-135">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e2314-136">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e2314-136">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-for-a-disk-file"></a><span data-ttu-id="e2314-137">Pour définir une unité logique pour un fichier de disque</span><span class="sxs-lookup"><span data-stu-id="e2314-137">To define a logical backup for a disk file</span></span>  
  
1.  <span data-ttu-id="e2314-138">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2314-138">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e2314-139">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e2314-139">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e2314-140">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e2314-140">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e2314-141">Cet exemple montre comment utiliser [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) pour définir une unité de sauvegarde logique pour un fichier de disque.</span><span class="sxs-lookup"><span data-stu-id="e2314-141">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a disk file.</span></span> <span data-ttu-id="e2314-142">Cet exemple ajoute l'unité de sauvegarde sur disque appelée `mydiskdump`, dont le nom physique est `c:\dump\dump1.bak`.</span><span class="sxs-lookup"><span data-stu-id="e2314-142">The example adds the disk backup device named `mydiskdump`, with the physical name `c:\dump\dump1.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mydiskdump', 'c:\dump\dump1.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2314-143"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2314-143">See Also</span></span>  
 <span data-ttu-id="e2314-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e2314-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="e2314-145">[Unités de sauvegarde &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e2314-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="e2314-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e2314-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="e2314-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e2314-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="e2314-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e2314-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="e2314-149">[Définir une unité de sauvegarde logique pour un lecteur de bande &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e2314-149">[Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span></span>  
 [<span data-ttu-id="e2314-150">Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e2314-150">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
