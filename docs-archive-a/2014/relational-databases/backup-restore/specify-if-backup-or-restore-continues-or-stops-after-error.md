---
title: Spécifier si une opération de sauvegarde ou de restauration continue ou s’arrête après la survenue d’une erreur (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], backups
- backing up databases [SQL Server], errors
- backups [SQL Server], errors
- database backups [SQL Server], errors
ms.assetid: 042be17a-b9b0-4629-b6bb-b87a8bc6c316
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 87cccec6f7eea18f2750d3b0be81b577b0eb170a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613474"
---
# <a name="specify-whether-a-backup-or-restore-operation-continues-or-stops-after-encountering-an-error-sql-server"></a><span data-ttu-id="dba28-102">Spécifier si une opération de sauvegarde ou de restauration continue ou s'arrête après la survenue d'une erreur (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dba28-102">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error (SQL Server)</span></span>
  <span data-ttu-id="dba28-103">Cette rubrique indique comment spécifier si une opération de sauvegarde ou de restauration continue ou s'arrête après la survenue d'une erreur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dba28-103">This topic describes how to specify whether a backup or restore operation continues or stops after encountering an error in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="dba28-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="dba28-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dba28-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="dba28-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dba28-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dba28-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dba28-107">**Pour spécifier si une opération de sauvegarde ou de restauration continue après la survenue d'une erreur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="dba28-107">**To specify whether a backup or restore operation continues after encountering an error, using:**</span></span>  
  
     [<span data-ttu-id="dba28-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dba28-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dba28-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dba28-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dba28-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="dba28-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dba28-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dba28-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dba28-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="dba28-112">Permissions</span></span>  
 <span data-ttu-id="dba28-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="dba28-113">BACKUP</span></span>  
 <span data-ttu-id="dba28-114">Les autorisations BACKUP DATABASE et BACKUP LOG reviennent par défaut aux membres du rôle serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="dba28-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="dba28-115">Des problèmes de propriété et d'autorisations sur le fichier physique de l'unité de sauvegarde sont susceptibles de perturber une opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dba28-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dba28-116">doit être en mesure de lire et d'écrire sur l'unité ; le compte sous lequel le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute doit avoir des autorisations d'écriture.</span><span class="sxs-lookup"><span data-stu-id="dba28-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="dba28-117">Toutefois, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), qui ajoute une entrée pour une unité de sauvegarde dans les tables système, ne vérifie pas les autorisations d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="dba28-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="dba28-118">De tels problèmes pour le fichier physique de l'unité de sauvegarde peuvent n'apparaître que lorsque la ressource physique est sollicitée au moment de la sauvegarde ou de la restauration.</span><span class="sxs-lookup"><span data-stu-id="dba28-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="dba28-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="dba28-119">RESTORE</span></span>  
 <span data-ttu-id="dba28-120">Si la base de données restaurée n'existe pas, l'utilisateur doit posséder les autorisations CREATE DATABASE afin de pouvoir exécuter RESTORE.</span><span class="sxs-lookup"><span data-stu-id="dba28-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="dba28-121">Si la base de données existe, les autorisations RESTORE reviennent par défaut aux membres des rôles serveur fixe **sysadmin** et **dbcreator** et au propriétaire (**dbo**) de la base de données (pour l’option FROM DATABASE_SNAPSHOT, la base de données existe toujours).</span><span class="sxs-lookup"><span data-stu-id="dba28-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="dba28-122">Les autorisations RESTORE sont attribuées aux rôles dont les informations d'appartenance sont toujours immédiatement accessibles à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="dba28-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="dba28-123">Étant donné que l’appartenance au rôle de base de données fixe ne peut être contrôlée que quand la base de données est accessible et non endommagée, ce qui n’est pas toujours le cas lorsque RESTORE est exécuté, les membres du rôle de base de données fixe **db_owner** ne détiennent pas d’autorisations RESTORE.</span><span class="sxs-lookup"><span data-stu-id="dba28-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dba28-124">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dba28-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-whether-backup-continues-or-stops-after-an-error-is-encountered"></a><span data-ttu-id="dba28-125">Pour spécifier si la sauvegarde continue ou s'arrête après la survenue d'une erreur</span><span class="sxs-lookup"><span data-stu-id="dba28-125">To specify whether backup continues or stops after an error is encountered</span></span>  
  
1.  <span data-ttu-id="dba28-126">Suivez les étapes pour [créer une sauvegarde de base de données](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dba28-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="dba28-127">Sur la page **Options** , dans la section **Fiabilité** , cliquez sur **Effectuer une somme de contrôle avant d'écrire sur le support** et sur **Continuer lors d'erreurs**.</span><span class="sxs-lookup"><span data-stu-id="dba28-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media** and **Continue on error**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dba28-128">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dba28-128">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-whether-a-backup-operation-continues-or-stops-after-encountering-an-error"></a><span data-ttu-id="dba28-129">Pour spécifier si une opération de sauvegarde continue ou s'arrête après la survenue d'une erreur</span><span class="sxs-lookup"><span data-stu-id="dba28-129">To specify whether a backup operation continues or stops after encountering an error</span></span>  
  
1.  <span data-ttu-id="dba28-130">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dba28-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dba28-131">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="dba28-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dba28-132">Dans l’instruction [BACKUP](/sql/t-sql/statements/backup-transact-sql) , spécifiez l’option CONTINUE_AFTER ERROR pour continuer ou l’option STOP_ON_ERROR pour arrêter.</span><span class="sxs-lookup"><span data-stu-id="dba28-132">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the CONTINUE_AFTER ERROR option to continue or the STOP_ON_ERROR option to stop.</span></span> <span data-ttu-id="dba28-133">Le comportement par défaut consiste à arrêter l'opération après la survenue d'une erreur.</span><span class="sxs-lookup"><span data-stu-id="dba28-133">The default behavior is to stop after encountering an error.</span></span> <span data-ttu-id="dba28-134">Cet exemple indique à l'opération de sauvegarde de continuer en dépit d'une erreur.</span><span class="sxs-lookup"><span data-stu-id="dba28-134">This example instructs the backup operation to continue despite encountering an error.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM, CONTINUE_AFTER_ERROR;  
GO  
```  
  
#### <a name="to-specify-whether-a-restore-operation-continues-or-stops-after-encountering-an-error"></a><span data-ttu-id="dba28-135">Pour spécifier si l'opération de restauration continue ou s'arrête après la survenue d'une erreur</span><span class="sxs-lookup"><span data-stu-id="dba28-135">To specify whether a restore operation continues or stops after encountering an error</span></span>  
  
1.  <span data-ttu-id="dba28-136">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dba28-136">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dba28-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="dba28-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dba28-138">Dans l’instruction [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , spécifiez l’option CONTINUE_AFTER ERROR pour continuer ou l’option STOP_ON_ERROR pour arrêter.</span><span class="sxs-lookup"><span data-stu-id="dba28-138">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the CONTINUE_AFTER ERROR option to continue or the STOP_ON_ERROR option to stop.</span></span> <span data-ttu-id="dba28-139">Le comportement par défaut consiste à arrêter l'opération après la survenue d'une erreur.</span><span class="sxs-lookup"><span data-stu-id="dba28-139">The default behavior is to stop after encountering an error.</span></span> <span data-ttu-id="dba28-140">Cet exemple indique à l'opération de restauration de continuer en dépit d'une erreur.</span><span class="sxs-lookup"><span data-stu-id="dba28-140">This example instructs the restore operation to continue despite encountering an error.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'   
   WITH CHECKSUM, CONTINUE_AFTER_ERROR;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="dba28-141"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dba28-141">See Also</span></span>  
 <span data-ttu-id="dba28-142">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dba28-142">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="dba28-143">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dba28-143">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="dba28-144">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dba28-144">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="dba28-145">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dba28-145">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="dba28-146">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dba28-146">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="dba28-147">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dba28-147">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="dba28-148">[Arguments RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dba28-148">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="dba28-149">[Erreurs de support possibles pendant les opérations de sauvegarde et de restauration &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dba28-149">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="dba28-150">Activer ou désactiver des sommes de contrôle de sauvegarde au cours d’opérations de sauvegarde ou de restauration &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dba28-150">Enable or Disable Backup Checksums During Backup or Restore &#40;SQL Server&#41;</span></span>](enable-or-disable-backup-checksums-during-backup-or-restore-sql-server.md)  
  
  
