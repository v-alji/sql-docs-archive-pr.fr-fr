---
title: Supprimer une unité de sauvegarde (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], deleting devices
- backup devices [SQL Server], deleting
- deleting backup devices
- removing backup devices
- backing up databases [SQL Server], backup devices
ms.assetid: 7be62480-ed6a-4262-a071-1feba73b1c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8734e587a8ecde315fb17120511455a59e38901
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604587"
---
# <a name="delete-a-backup-device-sql-server"></a><span data-ttu-id="17421-102">Supprimer une unité de sauvegarde (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="17421-102">Delete a Backup Device (SQL Server)</span></span>
  <span data-ttu-id="17421-103">Cette rubrique explique comment supprimer une unité de sauvegarde dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17421-103">This topic describes how to delete a backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="17421-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="17421-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="17421-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="17421-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="17421-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="17421-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="17421-107">**Pour supprimer une unité de sauvegarde, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="17421-107">**To delete a backup device, using:**</span></span>  
  
     [<span data-ttu-id="17421-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17421-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="17421-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17421-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="17421-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="17421-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="17421-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="17421-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="17421-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="17421-112">Permissions</span></span>  
 <span data-ttu-id="17421-113">Nécessite l'appartenance au rôle serveur fixe **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="17421-113">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="17421-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17421-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="17421-115">Pour supprimer une unité de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="17421-115">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="17421-116">Après vous être connecté à l'instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], dans l'Explorateur d'objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="17421-116">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="17421-117">Développez **Objets serveur**, puis **Unités de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="17421-117">Expand **Server Objects**, and then expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="17421-118">Cliquez avec le bouton droit sur l’unité de votre choix, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="17421-118">Right-click the device you want, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="17421-119">Dans la boîte de dialogue **Supprimer un objet** , vérifiez que le nom d'unité correct apparaît dans la colonne **Nom de l'objet** .</span><span class="sxs-lookup"><span data-stu-id="17421-119">In the **Delete Object** dialog box, verify that the correct device name appears in the **Object Name** column.</span></span>  
  
5.  <span data-ttu-id="17421-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17421-120">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="17421-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17421-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="17421-122">Pour supprimer une unité de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="17421-122">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="17421-123">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17421-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="17421-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="17421-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="17421-125">Copiez et collez l'exemple suivant dans la requête.</span><span class="sxs-lookup"><span data-stu-id="17421-125">Copy and paste the following example into the query.</span></span> <span data-ttu-id="17421-126">Cet exemple montre comment utiliser [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) pour supprimer une unité de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="17421-126">This example shows how to use [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) to delete a backup device.</span></span> <span data-ttu-id="17421-127">Exécutez le premier exemple afin de créer l’unité de sauvegarde `mybackupdisk` et le nom physique `c:\backup\backup1.bak`.</span><span class="sxs-lookup"><span data-stu-id="17421-127">Execute the first example to create the `mybackupdisk` backup device and the physical name `c:\backup\backup1.bak`.</span></span> <span data-ttu-id="17421-128">Exécutez `sp_dropdevice` pour supprimer l'unité de sauvegarde `mybackupdisk`.</span><span class="sxs-lookup"><span data-stu-id="17421-128">Execute `sp_dropdevice` to delete the `mybackupdisk` backup device.</span></span> <span data-ttu-id="17421-129">Le paramètre `delfile` supprime le nom physique.</span><span class="sxs-lookup"><span data-stu-id="17421-129">The `delfile` parameter deletes the physical name.</span></span>  
  
```sql  
--Define a backup device and physical name.   
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mybackupdisk', 'c:\backup\backup1.bak' ;  
GO  
--Delete the backup device and the physical name.  
USE AdventureWorks2012 ;  
GO  
EXEC sp_dropdevice ' mybackupdisk ', 'delfile' ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="17421-130"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17421-130">See Also</span></span>  
 <span data-ttu-id="17421-131">[Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="17421-131">[View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span></span>  
 <span data-ttu-id="17421-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17421-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="17421-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17421-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="17421-134">[Unités de sauvegarde &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="17421-134">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="17421-135">sp_addumpdevice &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17421-135">sp_addumpdevice &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)  
  
  
