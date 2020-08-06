---
title: Restaurer une sauvegarde à partir d’une unité (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring databases [SQL Server], device restores
- backup devices [SQL Server], restoring from
- database restores [SQL Server], device restores
- devices [SQL Server]
ms.assetid: 6e139de7-7de2-4d18-9df0-beac31ba7ff1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50d7f7b8e255aea470a1065df669c0cc3169a8dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698327"
---
# <a name="restore-a-backup-from-a-device-sql-server"></a><span data-ttu-id="28784-102">Restaurer une sauvegarde à partir d'une unité (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="28784-102">Restore a Backup from a Device (SQL Server)</span></span>
  <span data-ttu-id="28784-103">Cette rubrique explique comment restaurer une sauvegarde à partir d'une unité dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28784-103">This topic describes how to restore a backup from a device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28784-104">Pour plus d’informations sur la sauvegarde de SQL Server dans le service de stockage d’objets BLOB Azure, consultez, [SQL Server sauvegarde et restauration avec le service de stockage d’objets BLOB Azure](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="28784-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="28784-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="28784-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="28784-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="28784-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="28784-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="28784-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="28784-108">**Pour restaurer une sauvegarde à partir d'une unité, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="28784-108">**To restore a backup from a device, using:**</span></span>  
  
     [<span data-ttu-id="28784-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28784-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="28784-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28784-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="28784-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="28784-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="28784-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="28784-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="28784-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="28784-113">Permissions</span></span>  
 <span data-ttu-id="28784-114">Si la base de données restaurée n'existe pas, l'utilisateur doit posséder les autorisations CREATE DATABASE afin de pouvoir exécuter RESTORE.</span><span class="sxs-lookup"><span data-stu-id="28784-114">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="28784-115">Si la base de données existe, les autorisations RESTORE reviennent par défaut aux membres des rôles serveur fixe **sysadmin** et **dbcreator** et au propriétaire (**dbo**) de la base de données (pour l’option FROM DATABASE_SNAPSHOT, la base de données existe toujours).</span><span class="sxs-lookup"><span data-stu-id="28784-115">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="28784-116">Les autorisations RESTORE sont attribuées aux rôles dont les informations d'appartenance sont toujours immédiatement accessibles à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="28784-116">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="28784-117">Étant donné que l’appartenance au rôle de base de données fixe ne peut être contrôlée que quand la base de données est accessible et non endommagée, ce qui n’est pas toujours le cas lorsque RESTORE est exécuté, les membres du rôle de base de données fixe **db_owner** ne détiennent pas d’autorisations RESTORE.</span><span class="sxs-lookup"><span data-stu-id="28784-117">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="28784-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="28784-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="28784-119">Pour restaurer une sauvegarde à partir d'une unité</span><span class="sxs-lookup"><span data-stu-id="28784-119">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="28784-120">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="28784-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="28784-121">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="28784-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="28784-122">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, puis cliquez sur **Restaurer**.</span><span class="sxs-lookup"><span data-stu-id="28784-122">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="28784-123">Cliquez sur le type de restauration de votre choix (**Base de données**, **Fichiers et groupes de fichiers**ou **Journal des transactions**).</span><span class="sxs-lookup"><span data-stu-id="28784-123">Click the type of restore operation you want (**Database**, **Files and Filegroups**, or **Transaction Log**).</span></span> <span data-ttu-id="28784-124">Cette opération permet d'ouvrir la boîte de dialogue de restauration correspondante.</span><span class="sxs-lookup"><span data-stu-id="28784-124">This opens the corresponding restore dialog box.</span></span>  
  
5.  <span data-ttu-id="28784-125">Dans la page **Général** , dans la section **Source de restauration** , cliquez sur **À partir de l'unité**.</span><span class="sxs-lookup"><span data-stu-id="28784-125">On the **General** page, in the **Restore source** section, click **From device**.</span></span>  
  
6.  <span data-ttu-id="28784-126">Cliquez sur le bouton d'exploration de la zone de texte **À partir de l'unité** afin d'ouvrir la boîte de dialogue **Spécifier la sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="28784-126">Click the browse button for the **From device** text box, which opens the **Specify Backup** dialog box.</span></span>  
  
7.  <span data-ttu-id="28784-127">Dans la zone de texte **Support de sauvegarde** , sélectionnez **Unité de sauvegarde**, puis cliquez sur le bouton **Ajouter** pour ouvrir la boîte de dialogue **Sélectionner l'unité de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="28784-127">In the **Backup media** text box, select **Backup Device**, and click the **Add** button to open the **Select Backup Device** dialog box.</span></span>  
  
8.  <span data-ttu-id="28784-128">Dans la zone de texte **Unité de sauvegarde** , sélectionnez l'unité à utiliser pour la restauration.</span><span class="sxs-lookup"><span data-stu-id="28784-128">In the **Backup device** text box, select the device you want to use for the restore operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="28784-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="28784-129">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="28784-130">Pour restaurer une sauvegarde à partir d'une unité</span><span class="sxs-lookup"><span data-stu-id="28784-130">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="28784-131">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28784-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="28784-132">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="28784-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="28784-133">Dans l'instruction [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , spécifiez une unité de sauvegarde logique ou physique à utiliser pour l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="28784-133">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify a logical or physical backup device to use for the backup operation.</span></span> <span data-ttu-id="28784-134">Cet exemple effectue une restauration à partir d’un fichier disque qui a le nom physique `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span><span class="sxs-lookup"><span data-stu-id="28784-134">This example restores from a disk file that has the physical name `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak' ;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="28784-135"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28784-135">See Also</span></span>  
 <span data-ttu-id="28784-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28784-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="28784-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28784-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="28784-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28784-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="28784-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28784-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="28784-140">[Restaurer une sauvegarde de base de données en mode de récupération simple &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="28784-140">[Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span></span>  
 <span data-ttu-id="28784-141">[Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="28784-141">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="28784-142">[Restaurer une sauvegarde différentielle de base de données &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="28784-142">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="28784-143">[Restaurer une base de données à un nouvel emplacement &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="28784-143">[Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="28784-144">[Sauvegarder des fichiers et des groupes de fichiers &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="28784-144">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="28784-145">[Sauvegarder un journal des transactions &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="28784-145">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="28784-146">Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28784-146">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
