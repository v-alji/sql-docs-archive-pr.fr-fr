---
title: Définir une unité de sauvegarde logique pour un lecteur de bande (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- tape backup devices, creating
ms.assetid: 66f36e1d-0287-4fac-8a51-71f9f0d7ad5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8728df2cc0b5907e51da84ed9e77d897a1718d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709695"
---
# <a name="define-a-logical-backup-device-for-a-tape-drive-sql-server"></a><span data-ttu-id="bdfa6-102">Définir une unité de sauvegarde logique pour un lecteur de bande (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bdfa6-102">Define a Logical Backup Device for a Tape Drive (SQL Server)</span></span>
  <span data-ttu-id="bdfa6-103">Cette rubrique explique comment définir une unité de sauvegarde logique pour un lecteur de bande dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdfa6-103">This topic describes how to define a logical backup device for a tape drive in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bdfa6-104">Une unité logique est un nom défini par l'utilisateur qui désigne une unité de sauvegarde physique spécifique (un fichier de disque ou un lecteur de bande).</span><span class="sxs-lookup"><span data-stu-id="bdfa6-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="bdfa6-105">L'initialisation de l'unité physique se produit ultérieurement, lorsqu'une sauvegarde est écrite sur l'unité de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bdfa6-106">La prise en charge des unités de sauvegarde sur bande sera supprimée dans une prochaine version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdfa6-106">Support for tape backup devices will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bdfa6-107">Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-107">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="bdfa6-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="bdfa6-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bdfa6-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="bdfa6-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bdfa6-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="bdfa6-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bdfa6-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bdfa6-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bdfa6-112">**Pour définir une unité de sauvegarde logique pour un lecteur de bande, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="bdfa6-112">**To define a logical backup device for a tape drive, using:**</span></span>  
  
     [<span data-ttu-id="bdfa6-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bdfa6-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bdfa6-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bdfa6-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bdfa6-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="bdfa6-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bdfa6-116">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="bdfa6-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="bdfa6-117">Le ou les lecteurs de bande doivent être pris en charge par le système d'exploitation Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-117">The tape drive or drives must be supported by the Microsoft Windows operating system.</span></span>  
  
-   <span data-ttu-id="bdfa6-118">Le périphérique à bandes doit être connecté physiquement à l'ordinateur qui exécute une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdfa6-118">The tape device must be connected physically to the computer that is running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bdfa6-119">La sauvegarde sur des bandes à distance n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-119">Backing up to remote tape devices is not supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bdfa6-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bdfa6-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bdfa6-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="bdfa6-121">Permissions</span></span>  
 <span data-ttu-id="bdfa6-122">Nécessite l'appartenance au rôle serveur fixe **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="bdfa6-122">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="bdfa6-123">Requiert l'autorisation d'écrire sur le disque.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-123">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bdfa6-124">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bdfa6-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="bdfa6-125">Pour définir une unité de sauvegarde logique pour un lecteur de bande</span><span class="sxs-lookup"><span data-stu-id="bdfa6-125">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="bdfa6-126">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-126">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="bdfa6-127">Développez **Objets serveur**, puis cliquez avec le bouton droit sur **Unités de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-127">Expand **Server Objects**, and then right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="bdfa6-128">Cliquez sur **Nouvelle unité de sauvegarde**, pour ouvrir la boîte de dialogue **Unité de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="bdfa6-128">Click **New Backup Device**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="bdfa6-129">Entrez un nom d'unité.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-129">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="bdfa6-130">Pour la destination, cliquez sur **Bande** puis sélectionnez un lecteur de bande qui n'est pas déjà associé à une autre unité de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-130">For the destination, click **Tape** and select a tape drive that is not already associated with another backup device.</span></span> <span data-ttu-id="bdfa6-131">Si aucun lecteur de bande de ce type n'est disponible, l'option **Bande** est inactive.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-131">If no such tape drives are available, the **Tape** option is inactive.</span></span>  
  
6.  <span data-ttu-id="bdfa6-132">Pour définir la nouvelle unité, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-132">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="bdfa6-133">Pour procéder à une sauvegarde sur cette nouvelle unité, ajoutez-la au champ **Sauvegarde sur** dans la boîte de dialogue **Sauvegarder la base de données** (**Général**).</span><span class="sxs-lookup"><span data-stu-id="bdfa6-133">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="bdfa6-134">Pour plus d’informations, consultez [Créer une sauvegarde complète de base de données &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bdfa6-134">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bdfa6-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bdfa6-135">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="bdfa6-136">Pour définir une unité de sauvegarde logique pour un lecteur de bande</span><span class="sxs-lookup"><span data-stu-id="bdfa6-136">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="bdfa6-137">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdfa6-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bdfa6-138">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bdfa6-139">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="bdfa6-140">Cet exemple montre comment utiliser [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) pour définir une unité de sauvegarde logique pour une bande.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-140">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a tape.</span></span> <span data-ttu-id="bdfa6-141">Cet exemple ajoute l'unité de sauvegarde sur bande appelée `tapedump1`, dont le nom physique est `\\.\tape0`.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-141">The example adds the tape backup device named `tapedump1`, with the physical name `\\.\tape0`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'tape', 'tapedump1', '\\.\tape0' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdfa6-142"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bdfa6-142">See Also</span></span>  
 <span data-ttu-id="bdfa6-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bdfa6-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="bdfa6-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bdfa6-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="bdfa6-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bdfa6-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="bdfa6-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bdfa6-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="bdfa6-147">[Unités de sauvegarde &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bdfa6-147">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="bdfa6-148">[Définir une unité de sauvegarde logique pour un fichier de disque &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bdfa6-148">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="bdfa6-149">Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bdfa6-149">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
