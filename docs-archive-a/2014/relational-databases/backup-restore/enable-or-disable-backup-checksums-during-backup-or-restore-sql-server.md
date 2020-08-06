---
title: Activer ou désactiver des sommes de contrôle de sauvegarde au cours d’opérations de sauvegarde ou de restauration (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup checksums [SQL Server]
- disabling checksums
- checksums [SQL Server]
ms.assetid: 6786bd1e-ad97-430a-8dfb-d4ba952d6c4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a239dcdfca689be8555117104264d66a2ac037f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709692"
---
# <a name="enable-or-disable-backup-checksums-during-backup-or-restore-sql-server"></a><span data-ttu-id="4c5d7-102">Activer ou désactiver des sommes de contrôle de sauvegarde au cours d'opérations de sauvegarde ou de restauration (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4c5d7-102">Enable or Disable Backup Checksums During Backup or Restore (SQL Server)</span></span>
  <span data-ttu-id="4c5d7-103">Cette rubrique décrit comment activer ou désactiver les sommes de contrôle de sauvegarde lorsque vous sauvegardez ou restaurez une base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c5d7-103">This topic describes how to enable or disable backup checksums when you are backing up or restoring a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4c5d7-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="4c5d7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4c5d7-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="4c5d7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4c5d7-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4c5d7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4c5d7-107">**Pour activer ou désactiver les sommes de contrôle de sauvegarde, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="4c5d7-107">**To enable or disable backup checksums, using:**</span></span>  
  
     [<span data-ttu-id="4c5d7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c5d7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4c5d7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c5d7-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4c5d7-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4c5d7-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4c5d7-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4c5d7-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4c5d7-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4c5d7-112">Permissions</span></span>  
 <span data-ttu-id="4c5d7-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="4c5d7-113">BACKUP</span></span>  
 <span data-ttu-id="4c5d7-114">Les autorisations BACKUP DATABASE et BACKUP LOG reviennent par défaut aux membres du rôle serveur fixe **sysadmin** et des rôles de base de données fixes **db_owner** et **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="4c5d7-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="4c5d7-115">Des problèmes de propriété et d'autorisations sur le fichier physique de l'unité de sauvegarde sont susceptibles de perturber une opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4c5d7-116">doit être en mesure de lire et d'écrire sur l'unité ; le compte sous lequel le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute doit avoir des autorisations d'écriture.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="4c5d7-117">Toutefois, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), qui ajoute une entrée pour une unité de sauvegarde dans les tables système, ne vérifie pas les autorisations d’accès au fichier.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="4c5d7-118">De tels problèmes pour le fichier physique de l'unité de sauvegarde peuvent n'apparaître que lorsque la ressource physique est sollicitée au moment de la sauvegarde ou de la restauration.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="4c5d7-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="4c5d7-119">RESTORE</span></span>  
 <span data-ttu-id="4c5d7-120">Si la base de données restaurée n'existe pas, l'utilisateur doit posséder les autorisations CREATE DATABASE afin de pouvoir exécuter RESTORE.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="4c5d7-121">Si la base de données existe, les autorisations RESTORE reviennent par défaut aux membres des rôles serveur fixe **sysadmin** et **dbcreator** et au propriétaire (**dbo**) de la base de données (pour l’option FROM DATABASE_SNAPSHOT, la base de données existe toujours).</span><span class="sxs-lookup"><span data-stu-id="4c5d7-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="4c5d7-122">Les autorisations RESTORE sont attribuées aux rôles dont les informations d'appartenance sont toujours immédiatement accessibles à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="4c5d7-123">Étant donné que l’appartenance au rôle de base de données fixe ne peut être contrôlée que quand la base de données est accessible et non endommagée, ce qui n’est pas toujours le cas lorsque RESTORE est exécuté, les membres du rôle de base de données fixe **db_owner** ne détiennent pas d’autorisations RESTORE.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4c5d7-124">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c5d7-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-or-disable-checksums-during-a-backup-operation"></a><span data-ttu-id="4c5d7-125">Pour activer ou désactiver les sommes de contrôle pendant une opération de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="4c5d7-125">To enable or disable checksums during a backup operation</span></span>  
  
1.  <span data-ttu-id="4c5d7-126">Suivez les étapes pour [créer une sauvegarde de base de données](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c5d7-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="4c5d7-127">Sur la page **Options** , dans la section **Fiabilité** , cliquez sur **Effectuer une somme de contrôle avant d'écrire sur le support**.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4c5d7-128">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c5d7-128">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-backup-operation"></a><span data-ttu-id="4c5d7-129">Pour activer ou désactiver la somme de contrôle de sauvegarde pour une opération de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="4c5d7-129">To enable or disable backup checksum for a backup operation</span></span>  
  
1.  <span data-ttu-id="4c5d7-130">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c5d7-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c5d7-131">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4c5d7-132">Pour activer les sommes de contrôle de sauvegarde dans une instruction [BACKUP](/sql/t-sql/statements/backup-transact-sql) , spécifiez l'option WITH CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-132">To enable backup checksums in a [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="4c5d7-133">Pour désactiver les sommes de contrôle de sauvegarde, spécifiez l'option WITH NO_CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-133">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="4c5d7-134">Ceci est le comportement par défaut, sauf pour une sauvegarde compressée.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-134">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="4c5d7-135">L'exemple suivant spécifie que les sommes de contrôle doivent être effectuées.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-135">The following example specifies that checksums be performed.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-restore-operation"></a><span data-ttu-id="4c5d7-136">Pour activer ou désactiver la somme de contrôle de sauvegarde pour une opération de restauration</span><span class="sxs-lookup"><span data-stu-id="4c5d7-136">To enable or disable backup checksum for a restore operation</span></span>  
  
1.  <span data-ttu-id="4c5d7-137">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c5d7-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4c5d7-138">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4c5d7-139">Pour activer les sommes de contrôle de sauvegarde dans une instruction [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , spécifiez l'option WITH CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-139">To enable backup checksums in a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="4c5d7-140">Ceci est le comportement par défaut pour une sauvegarde compressée.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-140">This is the default behavior for a compressed backup.</span></span> <span data-ttu-id="4c5d7-141">Pour désactiver les sommes de contrôle de sauvegarde, spécifiez l'option WITH NO_CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-141">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="4c5d7-142">Ceci est le comportement par défaut, sauf pour une sauvegarde compressée.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-142">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="4c5d7-143">L'exemple suivant spécifie que les sommes de contrôle de sauvegarde doivent être effectuées.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-143">The following example specifies that backup checksums be performed.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
> [!WARNING]  
>  <span data-ttu-id="4c5d7-144">Si vous spécifiez explicitement CHECKSUM pour une opération de restauration et que la sauvegarde contient des sommes de contrôle de sauvegarde, ces sommes de contrôle de sauvegarde ainsi que les sommes de contrôle de page sont vérifiées, comme dans le cas par défaut.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-144">If you explicitly request CHECKSUM for a restore operation and if the backup contains backup checksums, backup checksums and page checksums are both verified, as in the default case.</span></span> <span data-ttu-id="4c5d7-145">Toutefois, si le jeu de sauvegarde manque de sommes de contrôle de sauvegarde, l'opération de restauration se solde par un échec et l'affichage d'un message indiquant l'absence des sommes de contrôle.</span><span class="sxs-lookup"><span data-stu-id="4c5d7-145">However, if the backup set lacks backup checksums, the restore operation fails with a message indicating that checksums are not present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c5d7-146"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c5d7-146">See Also</span></span>  
 <span data-ttu-id="4c5d7-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c5d7-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="4c5d7-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c5d7-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="4c5d7-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c5d7-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="4c5d7-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c5d7-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="4c5d7-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c5d7-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="4c5d7-152">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c5d7-152">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="4c5d7-153">[Arguments RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c5d7-153">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="4c5d7-154">[Erreurs de support possibles pendant les opérations de sauvegarde et de restauration &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4c5d7-154">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="4c5d7-155">Spécifier si une opération de sauvegarde ou de restauration continue ou s’arrête après la survenue d’une erreur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c5d7-155">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
  
