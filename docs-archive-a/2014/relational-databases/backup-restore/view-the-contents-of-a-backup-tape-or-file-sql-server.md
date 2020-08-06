---
title: Afficher le contenu d’un fichier ou d’une bande de sauvegarde (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- displaying backup content
- viewing backup content
- tape backup devices, viewing contents
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
ms.assetid: cd6674a2-ca55-4b5a-a971-878ba001821e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 044519b64d41fbbdfc9302ce24369ab282727f67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703011"
---
# <a name="view-the-contents-of-a-backup-tape-or-file-sql-server"></a><span data-ttu-id="bde8e-102">Afficher le contenu d'un fichier ou d'une bande de sauvegarde (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bde8e-102">View the Contents of a Backup Tape or File (SQL Server)</span></span>
  <span data-ttu-id="bde8e-103">Cette rubrique explique comment afficher le contenu d'un fichier ou d'une bande de sauvegarde dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bde8e-103">This topic describes how to view the content of a backup tape or file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bde8e-104">La prise en charge des unités de sauvegarde sur bande sera supprimée dans une prochaine version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bde8e-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="bde8e-105">Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="bde8e-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="bde8e-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="bde8e-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bde8e-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="bde8e-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bde8e-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bde8e-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bde8e-109">**Pour afficher le contenu d'un fichier ou d'une bande de sauvegarde, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="bde8e-109">**To view the content of a backup tape or file, using:**</span></span>  
  
     [<span data-ttu-id="bde8e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bde8e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bde8e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bde8e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bde8e-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="bde8e-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bde8e-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bde8e-113">Security</span></span>  
 <span data-ttu-id="bde8e-114">Pour plus d’informations sur la sécurité, consultez [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bde8e-114">For information about security, see [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bde8e-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="bde8e-115">Permissions</span></span>  
 <span data-ttu-id="bde8e-116">Dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et les versions ultérieures, l'obtention d'informations relatives à un jeu de sauvegarde ou une unité de sauvegarde requiert l'autorisation CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="bde8e-116">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="bde8e-117">Pour plus d’informations, consultez [GRANT – octroi d’autorisations de base de données &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bde8e-117">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bde8e-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bde8e-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="bde8e-119">Pour afficher le contenu d'un fichier ou d'une bande de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="bde8e-119">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="bde8e-120">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="bde8e-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="bde8e-121">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="bde8e-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="bde8e-122">Cliquez avec le bouton droit sur la base de données à sauvegarder, pointez sur **Tâches**, puis cliquez sur **Sauvegarder**.</span><span class="sxs-lookup"><span data-stu-id="bde8e-122">Right-click the database you want to backup, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="bde8e-123">La boîte de dialogue **Sauvegarder la base de données** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bde8e-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="bde8e-124">Dans la section **Destination** de la page **Général** , cliquez sur **Disque** ou sur **Bande**.</span><span class="sxs-lookup"><span data-stu-id="bde8e-124">In the **Destination** section of the **General** page, click either **Disk** or **Tape**.</span></span> <span data-ttu-id="bde8e-125">Dans la zone de liste **Sauvegarde sur** , recherchez le fichier disque ou la bande souhaitée.</span><span class="sxs-lookup"><span data-stu-id="bde8e-125">In the **Back up to** list box, look for the disk file or tape you want.</span></span>  
  
     <span data-ttu-id="bde8e-126">Si le fichier disque ou la bande ne figure pas dans la zone de liste, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="bde8e-126">If the disk file or tape is not displayed in the list-box, click **Add**.</span></span> <span data-ttu-id="bde8e-127">Sélectionnez un nom de fichier ou un lecteur de bande.</span><span class="sxs-lookup"><span data-stu-id="bde8e-127">Select a file name or tape drive.</span></span> <span data-ttu-id="bde8e-128">Pour l’ajouter à la zone de liste **Sauvegarde sur** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bde8e-128">To add it to the **Back up to** list-box, click **OK**.</span></span>  
  
5.  <span data-ttu-id="bde8e-129">Dans la zone de liste **Sauvegarde sur** , sélectionnez le chemin d’accès au disque ou au lecteur de bande que vous souhaitez afficher et cliquez sur **Sommaire**.</span><span class="sxs-lookup"><span data-stu-id="bde8e-129">In the **Back up to** list-box, select the path of the disk or tape drive you want to view, and click **Contents**.</span></span> <span data-ttu-id="bde8e-130">La boîte de dialogue **Contenu de l'unité** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="bde8e-130">This opens the **Device Contents** dialog box.</span></span>  
  
6.  <span data-ttu-id="bde8e-131">Le volet droit affiche des informations relatives au support de sauvegarde et aux jeux de sauvegarde sur la bande ou le fichier sélectionné.</span><span class="sxs-lookup"><span data-stu-id="bde8e-131">The right-hand pane displays information about the media set and backup sets on the selected tape or file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bde8e-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bde8e-132">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="bde8e-133">Pour afficher le contenu d'un fichier ou d'une bande de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="bde8e-133">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="bde8e-134">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bde8e-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bde8e-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="bde8e-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bde8e-136">Utilisez l'instruction [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="bde8e-136">Use the [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) statement.</span></span> <span data-ttu-id="bde8e-137">Cet exemple retourne des informations de base sur le fichier nommé `AdventureWorks2012-FullBackup.bak`.</span><span class="sxs-lookup"><span data-stu-id="bde8e-137">This example returns information about the file named `AdventureWorks2012-FullBackup.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
RESTORE HEADERONLY   
FROM DISK = N'C:\AdventureWorks2012-FullBackup.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="bde8e-138"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bde8e-138">See Also</span></span>  
 <span data-ttu-id="bde8e-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bde8e-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="bde8e-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bde8e-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="bde8e-141">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bde8e-141">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="bde8e-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bde8e-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="bde8e-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bde8e-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="bde8e-144">[Unités de sauvegarde &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bde8e-144">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="bde8e-145">[Définir une unité de sauvegarde logique pour un fichier de disque &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bde8e-145">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="bde8e-146">Définir une unité de sauvegarde logique pour un lecteur de bande &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bde8e-146">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
