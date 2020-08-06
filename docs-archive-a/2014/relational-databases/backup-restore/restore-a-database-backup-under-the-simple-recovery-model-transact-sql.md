---
title: Restaurer une sauvegarde de base de données en mode de récupération simple (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- database restores [SQL Server], full backups
- backing up databases [SQL Server], full backups
- database backups [SQL Server], full backups
- restoring databases [SQL Server], full backups
ms.assetid: a928fa36-e285-476f-9a7b-6840a8bb7283
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e264dd380c3dff40dacc4eb576d34af5195dec01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698328"
---
# <a name="restore-a-database-backup-under-the-simple-recovery-model-transact-sql"></a><span data-ttu-id="a279f-102">Restaurer une sauvegarde de base de données en mode de récupération simple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a279f-102">Restore a Database Backup Under the Simple Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="a279f-103">Cette rubrique explique comment restaurer une sauvegarde complète de base de données.</span><span class="sxs-lookup"><span data-stu-id="a279f-103">This topic explains how to restore a full database backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a279f-104">L'administrateur système qui restaure la sauvegarde complète de base de données doit être la seule personne à utiliser la base de données à restaurer.</span><span class="sxs-lookup"><span data-stu-id="a279f-104">The system administrator restoring the full database backup must be the only person currently using the database to be restored.</span></span>  
  
## <a name="prerequisites-and-recommendations"></a><span data-ttu-id="a279f-105">Prérequis et recommandations</span><span class="sxs-lookup"><span data-stu-id="a279f-105">Prerequisites and Recommendations</span></span>  
  
-   <span data-ttu-id="a279f-106">Pour restaurer une base de données chiffrée, vous devez avoir accès au certificat ou à la clé asymétrique qui a servi à chiffrer la base de données.</span><span class="sxs-lookup"><span data-stu-id="a279f-106">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="a279f-107">Sans le certificat et la clé asymétrique, la base de données ne peut pas être restaurée.</span><span class="sxs-lookup"><span data-stu-id="a279f-107">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="a279f-108">En conséquence, le certificat utilisé pour chiffrer la clé de chiffrement de base de données doit être conservé tant que la sauvegarde est utile.</span><span class="sxs-lookup"><span data-stu-id="a279f-108">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="a279f-109">Pour plus d'informations, consultez [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="a279f-109">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
-   <span data-ttu-id="a279f-110">Pour des raisons de sécurité, nous vous recommandons de ne pas attacher ni restaurer des bases de données provenant de sources inconnues ou non approuvées.</span><span class="sxs-lookup"><span data-stu-id="a279f-110">For security purposes, we recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="a279f-111">Ces bases de données peuvent contenir du code malveillant susceptible d'exécuter du code [!INCLUDE[tsql](../../includes/tsql-md.md)] indésirable ou de provoquer des erreurs en modifiant le schéma ou la structure physique des bases de données.</span><span class="sxs-lookup"><span data-stu-id="a279f-111">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="a279f-112">Avant d’utiliser une base de données issue d’une source inconnue ou non approuvée, exécutez [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sur la base de données sur un serveur autre qu’un serveur de production et examinez également le code, notamment les procédures stockées ou le code défini par l’utilisateur, de la base de données.</span><span class="sxs-lookup"><span data-stu-id="a279f-112">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="database-compatibility-level-after-upgrade"></a><span data-ttu-id="a279f-113">Niveau de compatibilité des bases de données après une mise à niveau</span><span class="sxs-lookup"><span data-stu-id="a279f-113">Database Compatibility Level After Upgrade</span></span>  
 <span data-ttu-id="a279f-114">Les niveaux de compatibilité des bases de données **tempdb**, **model**, **msdb** et **Resource** sont définis sur le niveau de compatibilité [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="a279f-114">The compatibility levels of the **tempdb**, **model**, **msdb** and **Resource** databases are set to the compatibility level of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after upgrade.</span></span> <span data-ttu-id="a279f-115">La base de données système **master** conserve le niveau de compatibilité qu’elle avait avant la mise à niveau, sauf si ce niveau était inférieur à 100.</span><span class="sxs-lookup"><span data-stu-id="a279f-115">The **master** system database retains the compatibility level it had before upgrade, unless that level was less than 100.</span></span> <span data-ttu-id="a279f-116">Si le niveau de compatibilité de la base de données **master** était inférieur à 100 avant la mise à niveau, il est défini sur 100 une fois celle-ci effectuée.</span><span class="sxs-lookup"><span data-stu-id="a279f-116">If the compatibility level of **master** was less than 100 before upgrade, it is set to 100 after upgrade.</span></span>  
  
 <span data-ttu-id="a279f-117">Si le niveau de compatibilité d'une base de données utilisateur est à 100 ou supérieur avant la mise à niveau, il reste le même après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="a279f-117">If the compatibility level of a user database was 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="a279f-118">Si le niveau de compatibilité était à 90 avant la mise à niveau, dans la base de données mise à niveau, le niveau de compatibilité est défini à 100, ce qui correspond au niveau de compatibilité le plus bas pris en charge dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a279f-118">If the compatibility level was 90 before upgrade, in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a279f-119">Les nouvelles bases de données utilisateur héritent du niveau de compatibilité de la base de données **model** .</span><span class="sxs-lookup"><span data-stu-id="a279f-119">New user databases will inherit the compatibility level of the **model** database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="a279f-120">Procédures</span><span class="sxs-lookup"><span data-stu-id="a279f-120">Procedures</span></span>  
  
#### <a name="to-restore-a-full-database-backup"></a><span data-ttu-id="a279f-121">Pour restaurer une sauvegarde complète de base de données</span><span class="sxs-lookup"><span data-stu-id="a279f-121">To restore a full database backup</span></span>  
  
1.  <span data-ttu-id="a279f-122">Exécutez l'instruction RESTORE DATABASE pour restaurer la sauvegarde complète de la base de données, en spécifiant :</span><span class="sxs-lookup"><span data-stu-id="a279f-122">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="a279f-123">le nom de la base de données à restaurer ;</span><span class="sxs-lookup"><span data-stu-id="a279f-123">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="a279f-124">l'unité de sauvegarde à partir de laquelle sera restaurée la sauvegarde complète de la base de données ;</span><span class="sxs-lookup"><span data-stu-id="a279f-124">The backup device from where the full database backup is restored.</span></span>  
  
    -   <span data-ttu-id="a279f-125">la clause NORECOVERY si vous devez appliquer la sauvegarde différentielle de base de données ou du journal des transactions après avoir restauré la sauvegarde complète de base de données.</span><span class="sxs-lookup"><span data-stu-id="a279f-125">The NORECOVERY clause if you have a transaction log or differential database backup to apply after restoring the full database backup.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a279f-126">Pour restaurer une base de données chiffrée, vous devez avoir accès au certificat ou à la clé asymétrique qui a servi à chiffrer la base de données.</span><span class="sxs-lookup"><span data-stu-id="a279f-126">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="a279f-127">Sans le certificat et la clé asymétrique, la base de données ne peut pas être restaurée.</span><span class="sxs-lookup"><span data-stu-id="a279f-127">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="a279f-128">En conséquence, le certificat utilisé pour chiffrer la clé de chiffrement de base de données doit être conservé tant que la sauvegarde est utile.</span><span class="sxs-lookup"><span data-stu-id="a279f-128">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="a279f-129">Pour plus d'informations, consultez [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="a279f-129">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
2.  <span data-ttu-id="a279f-130">Spécifiez éventuellement :</span><span class="sxs-lookup"><span data-stu-id="a279f-130">Optionally, specify:</span></span>  
  
    -   <span data-ttu-id="a279f-131">la clause FILE pour identifier le jeu de sauvegarde sur l'unité de sauvegarde à restaurer.</span><span class="sxs-lookup"><span data-stu-id="a279f-131">The FILE clause to identify the backup set on the backup device to restore.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a279f-132">Si vous restaurez une base de données de version antérieure à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], la base de données est automatiquement mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="a279f-132">If you restore an earlier version database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the database is automatically upgraded.</span></span> <span data-ttu-id="a279f-133">En général, la base de données est immédiatement disponible.</span><span class="sxs-lookup"><span data-stu-id="a279f-133">Typically, the database becomes available immediately.</span></span> <span data-ttu-id="a279f-134">Toutefois, si une base de données [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] comprend des index de recherche en texte intégral, le processus de mise à niveau les importe, les réinitialise ou les reconstruit, selon la valeur de la propriété de serveur  **upgrade_option** .</span><span class="sxs-lookup"><span data-stu-id="a279f-134">However, if a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the  **upgrade_option** server property.</span></span> <span data-ttu-id="a279f-135">Si l’option de mise à niveau a la valeur Importer (**upgrade_option** = 2) ou Reconstruire (**upgrade_option** = 0), les index de recherche en texte intégral ne seront pas disponibles pendant la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="a279f-135">If the upgrade option is set to import (**upgrade_option** = 2) or rebuild (**upgrade_option** = 0), the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="a279f-136">Selon le volume de données indexé, l'importation peut prendre plusieurs heures et la reconstruction jusqu'à dix fois plus longtemps.</span><span class="sxs-lookup"><span data-stu-id="a279f-136">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="a279f-137">Notez également que lorsque l'option de mise à niveau est Importer, les index de recherche en texte intégral associés sont reconstruits si aucun catalogue de texte intégral n'est disponible.</span><span class="sxs-lookup"><span data-stu-id="a279f-137">Note also that when the upgrade option is set to import, the associated full-text indexes are rebuilt if a full-text catalog is not available.</span></span> <span data-ttu-id="a279f-138">Pour modifier le paramètre de la propriété de serveur **upgrade_option** , utilisez [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a279f-138">To change the setting of the **upgrade_option** server property, use [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a279f-139"> Exemple</span><span class="sxs-lookup"><span data-stu-id="a279f-139">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a279f-140">Description</span><span class="sxs-lookup"><span data-stu-id="a279f-140">Description</span></span>  
 <span data-ttu-id="a279f-141">Cet exemple restaure la sauvegarde complète de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] à partir d'une bande.</span><span class="sxs-lookup"><span data-stu-id="a279f-141">This example restores the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] full database backup from tape.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a279f-142"> Exemple</span><span class="sxs-lookup"><span data-stu-id="a279f-142">Example</span></span>  
  
```  
USE master;  
GO  
RESTORE DATABASE AdventureWorks2012  
   FROM TAPE = '\\.\Tape0';  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="a279f-143"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a279f-143">See Also</span></span>  
 <span data-ttu-id="a279f-144">[Restaurations complètes de bases de données &#40;mode de récupération complète&#41;](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="a279f-144">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="a279f-145">[Restaurations complètes de bases de données &#40;mode de récupération simple&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="a279f-145">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="a279f-146">[Sauvegardes complètes de bases de données &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a279f-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="a279f-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a279f-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="a279f-148">[Historique de sauvegarde et informations d’en-tête &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a279f-148">[Backup History and Header Information &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span></span>  
 [<span data-ttu-id="a279f-149">Reconstruire des bases de données système</span><span class="sxs-lookup"><span data-stu-id="a279f-149">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  
