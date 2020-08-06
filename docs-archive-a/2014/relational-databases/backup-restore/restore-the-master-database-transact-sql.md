---
title: Restaurer la base de données MASTER (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- master database [SQL Server], restoring
ms.assetid: c83d802c-e84e-4458-b3ca-173d9ba32f73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c9cb078b7af60fc5e060bcb144fc9cbaee8ecf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612411"
---
# <a name="restore-the-master-database-transact-sql"></a><span data-ttu-id="b005b-102">Restaurer la base de données MASTER (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b005b-102">Restore the master Database (Transact-SQL)</span></span>
  <span data-ttu-id="b005b-103">Cette rubrique explique comment restaurer la base de données **master** à partir d'une sauvegarde complète d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="b005b-103">This topic explains how to restore the **master** database from a full database backup.</span></span>  
  
### <a name="to-restore-the-master-database"></a><span data-ttu-id="b005b-104">Pour restaurer la base de données master</span><span class="sxs-lookup"><span data-stu-id="b005b-104">To restore the master database</span></span>  
  
1.  <span data-ttu-id="b005b-105">Démarrez l'instance de serveur en mode mono-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b005b-105">Start the server instance in single-user mode.</span></span>  
  
     <span data-ttu-id="b005b-106">Pour savoir comment spécifier le paramètre de démarrage mono-utilisateur ( **-m**), consultez [Configurer les options de démarrage du serveur &#40;Gestionnaire de configuration SQL Server&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="b005b-106">For information about how to specify the single-user startup parameter (**-m**), see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
2.  <span data-ttu-id="b005b-107">Pour restaurer une sauvegarde complète de la base de données **master**, utilisez l’instruction [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] suivante :</span><span class="sxs-lookup"><span data-stu-id="b005b-107">To restore a full database backup of **master**, use the following [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="b005b-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span><span class="sxs-lookup"><span data-stu-id="b005b-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span></span>  
  
     <span data-ttu-id="b005b-109">L'option REPLACE indique à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de restaurer la base de données spécifiée même lorsqu'il existe déjà une base de données du même nom.</span><span class="sxs-lookup"><span data-stu-id="b005b-109">The REPLACE option instructs [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to restore the specified database even when a database of the same name already exists.</span></span> <span data-ttu-id="b005b-110">Le cas échéant, la base de données existante est supprimée.</span><span class="sxs-lookup"><span data-stu-id="b005b-110">The existing database, if any, is deleted.</span></span> <span data-ttu-id="b005b-111">En mode mono-utilisateur, nous vous recommandons d’entrer l’instruction RESTORE DATABASE dans l’ [utilitaire sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b005b-111">In single-user mode, we recommend that you enter the RESTORE DATABASE statement in the [sqlcmd utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="b005b-112">Pour plus d’informations, consultez [Utiliser l’utilitaire sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b005b-112">For more information, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b005b-113">Une fois la base de données **MASTER** restaurée, l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] s’arrête et met fin au processus **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="b005b-113">After **master** is restored, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] shuts down and terminates the **sqlcmd** process.</span></span> <span data-ttu-id="b005b-114">Avant de redémarrer l'instance du serveur, supprimez le paramètre de démarrage en mode mono-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b005b-114">Before you restart the server instance, remove the single-user startup parameter.</span></span> <span data-ttu-id="b005b-115">Pour plus d’informations, consultez [Configurer les options de démarrage du serveur &#40;Gestionnaire de configuration SQL Server&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="b005b-115">For more information, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
3.  <span data-ttu-id="b005b-116">Redémarrez l'instance du serveur et poursuivez les autres étapes de récupération telles que la restauration d'autres bases de données, l'attachement de bases de données et la correction des incompatibilités au niveau utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b005b-116">Restart the server instance and continue other recovery steps such as restoring other databases, attaching databases, and correcting user mismatches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b005b-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="b005b-117">Example</span></span>  
 <span data-ttu-id="b005b-118">Dans l'exemple suivant, la base de données `master` est restaurée sur l'instance du serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="b005b-118">The following example restores the `master` database on the default server instance.</span></span> <span data-ttu-id="b005b-119">L'exemple suppose que l'instance du serveur s'exécute déjà en mode mono-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b005b-119">The example assumes that the server instance is already running in single-user mode.</span></span> <span data-ttu-id="b005b-120">L’exemple démarre `sqlcmd` et exécute une instruction `RESTORE DATABASE` qui restaure une sauvegarde complète de la base de données de `master` à partir d’une unité de disque : `Z:\SQLServerBackups\master.bak`.</span><span class="sxs-lookup"><span data-stu-id="b005b-120">The example starts `sqlcmd` and executes a `RESTORE DATABASE` statement that restores a full database backup of `master` from a disk device: `Z:\SQLServerBackups\master.bak`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b005b-121">Pour une instance nommée, la commande **sqlcmd** doit spécifier l'option **-S** _\<ComputerName>_ \\ *\<InstanceName>* .</span><span class="sxs-lookup"><span data-stu-id="b005b-121">For a named instance, the **sqlcmd** command must specify the **-S**_\<ComputerName>_\\*\<InstanceName>* option.</span></span>  
  
```  
  
      C:\> sqlcmd  
1> RESTORE DATABASE master FROM DISK = 'Z:\SQLServerBackups\master.bak' WITH REPLACE;  
2> GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b005b-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b005b-122">See Also</span></span>  
 <span data-ttu-id="b005b-123">[Restaurations complètes de bases de données &#40;mode de récupération simple&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="b005b-123">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="b005b-124">[Restaurations complètes de bases de données &#40;mode de récupération complète&#41;](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="b005b-124">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="b005b-125">[Dépanner des utilisateurs orphelins &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b005b-125">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 <span data-ttu-id="b005b-126">[Attacher et détacher une base de données &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b005b-126">[Database Detach and Attach &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="b005b-127">[Reconstruire des bases de données système](../databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="b005b-127">[Rebuild System Databases](../databases/system-databases.md) </span></span>  
 <span data-ttu-id="b005b-128">[Options de démarrage du service moteur de base de données](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span><span class="sxs-lookup"><span data-stu-id="b005b-128">[Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span></span>  
 <span data-ttu-id="b005b-129">[Gestionnaire de configuration SQL Server](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b005b-129">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="b005b-130">[Sauvegarder et restaurer des bases de données système &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b005b-130">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="b005b-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b005b-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="b005b-132">Démarrer SQL Server en mode mono-utilisateur</span><span class="sxs-lookup"><span data-stu-id="b005b-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
