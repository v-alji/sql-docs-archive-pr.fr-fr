---
title: Sauvegardes de type copie seule (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- copy-only backups [SQL Server]
- COPY_ONLY option [BACKUP statement]
- backups [SQL Server], copy-only backups
ms.assetid: f82d6918-a5a7-4af8-868e-4247f5b00c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc74d7b1bba2a0163ac9edefb5d465c54ef6296c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614666"
---
# <a name="copy-only-backups-sql-server"></a><span data-ttu-id="112bf-102">Sauvegardes de type copie seule (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="112bf-102">Copy-Only Backups (SQL Server)</span></span>
  <span data-ttu-id="112bf-103">Une *sauvegarde de copie uniquement* est une sauvegarde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] indépendante du mécanisme des sauvegardes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conventionnelles.</span><span class="sxs-lookup"><span data-stu-id="112bf-103">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="112bf-104">Normalement, une sauvegarde modifie la base de données et affecte la restauration des sauvegardes ultérieures.</span><span class="sxs-lookup"><span data-stu-id="112bf-104">Usually, taking a backup changes the database and affects how later backups are restored.</span></span> <span data-ttu-id="112bf-105">Parfois, cependant, il est utile d'effectuer une sauvegarde à une fin précise sans affecter les procédures globales de sauvegarde et de restauration de la base de données.</span><span class="sxs-lookup"><span data-stu-id="112bf-105">However, occasionally, it is useful to take a backup for a special purpose without affecting the overall backup and restore procedures for the database.</span></span> <span data-ttu-id="112bf-106">Pour cela, on peut recourir à une sauvegarde de copie uniquement.</span><span class="sxs-lookup"><span data-stu-id="112bf-106">Copy-only backups serve this purpose.</span></span>  
  
 <span data-ttu-id="112bf-107">Les types de sauvegarde de copie uniquement sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="112bf-107">The types of copy-only backups are as follows:</span></span>  
  
-   <span data-ttu-id="112bf-108">Sauvegardes complètes de copie uniquement (tous modes de récupération)</span><span class="sxs-lookup"><span data-stu-id="112bf-108">Copy-only full backups (all recovery models)</span></span>  
  
     <span data-ttu-id="112bf-109">Une sauvegarde de copie uniquement ne peut pas servir de base différentielle ni de sauvegarde différentielle et n'a aucune incidence sur la base différentielle.</span><span class="sxs-lookup"><span data-stu-id="112bf-109">A copy-only backup cannot serve as a differential base or differential backup and does not affect the differential base.</span></span>  
  
     <span data-ttu-id="112bf-110">La restauration d'une sauvegarde complète de copie uniquement est identique à la restauration de toute autre sauvegarde complète.</span><span class="sxs-lookup"><span data-stu-id="112bf-110">Restoring a copy-only full backup is the same as restoring any other full backup.</span></span>  
  
-   <span data-ttu-id="112bf-111">Sauvegardes de fichier journal de copie uniquement (en mode de récupération complète et en mode de récupération utilisant les journaux de transactions uniquement)</span><span class="sxs-lookup"><span data-stu-id="112bf-111">Copy-only log backups (full recovery model and bulk-logged recovery model only)</span></span>  
  
     <span data-ttu-id="112bf-112">Une sauvegarde du journal de type copie seule préserve le point d'archive du journal existant et, donc, n'a pas d'incidence sur l'ordre des sauvegardes régulières des journaux.</span><span class="sxs-lookup"><span data-stu-id="112bf-112">A copy-only log backup preserves the existing log archive point and, therefore, does not affect the sequencing of regular log backups.</span></span> <span data-ttu-id="112bf-113">Les sauvegardes de journaux de type copie seule sont généralement superflues.</span><span class="sxs-lookup"><span data-stu-id="112bf-113">Copy-only log backups are typically unnecessary.</span></span> <span data-ttu-id="112bf-114">En revanche, vous pouvez créer une nouvelle sauvegarde de routine des journaux (à l'aide de WITH NORECOVERY) et utiliser cette sauvegarde conjointement avec toute sauvegarde des journaux précédente nécessaire à la séquence de restauration.</span><span class="sxs-lookup"><span data-stu-id="112bf-114">Instead, you can create a new routine log backup (using WITH NORECOVERY) and use that backup together with any previous log backups that are required for the restore sequence.</span></span> <span data-ttu-id="112bf-115">Toutefois, une sauvegarde de fichier journal de copie uniquement peut parfois être utile pour effectuer une restauration en ligne.</span><span class="sxs-lookup"><span data-stu-id="112bf-115">However, a copy-only log backup can sometimes be useful for performing an online restore.</span></span> <span data-ttu-id="112bf-116">Pour obtenir un exemple, consultez [Exemple : Restauration en ligne d’un fichier en lecture/écriture &#40;mode de récupération complète&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="112bf-116">For an example of this, see [Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span></span>  
  
     <span data-ttu-id="112bf-117">Le journal des transactions n'est jamais tronqué après une sauvegarde de type copie seule.</span><span class="sxs-lookup"><span data-stu-id="112bf-117">The transaction log is never truncated after a copy-only backup.</span></span>  
  
 <span data-ttu-id="112bf-118">Les sauvegardes de copie uniquement sont enregistrées dans la colonne **is_copy_only** de la table [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="112bf-118">Copy-only backups are recorded in the **is_copy_only** column of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) table.</span></span>  
  
## <a name="to-create-a-copy-only-backup"></a><span data-ttu-id="112bf-119">Pour créer une sauvegarde de type copie uniquement</span><span class="sxs-lookup"><span data-stu-id="112bf-119">To Create a Copy-Only Backup</span></span>  
 <span data-ttu-id="112bf-120">Vous pouvez créer une sauvegarde de copie uniquement à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="112bf-120">You can create a copy-only backup by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="112bf-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="112bf-121">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="112bf-122">Sur la page **Général** de la boîte de dialogue **Sauvegarder la base de données**, sélectionnez l’option **Sauvegarde de copie uniquement**.</span><span class="sxs-lookup"><span data-stu-id="112bf-122">On the **General** page of the **Back Up Database** dialog box, select the **Copy Only Backup** option.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="112bf-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="112bf-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="112bf-124">La syntaxe [!INCLUDE[tsql](../../../includes/tsql-md.md)] essentielle est la suivante :</span><span class="sxs-lookup"><span data-stu-id="112bf-124">The essential [!INCLUDE[tsql](../../../includes/tsql-md.md)] syntax is as follows:</span></span>  
  
-   <span data-ttu-id="112bf-125">Pour une sauvegarde complète de type copie uniquement :</span><span class="sxs-lookup"><span data-stu-id="112bf-125">For a copy-only full backup:</span></span>  
  
     <span data-ttu-id="112bf-126">SAUVEGARDER la base de données *database_name* sur \<backup_device*> \*... AVEC COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="112bf-126">BACKUP DATABASE *database_name* TO \<backup_device*>\* ... WITH COPY_ONLY ...</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="112bf-127">COPY_ONLY n'a aucun effet lorsqu'il est spécifié avec l'option DIFFERENTIAL.</span><span class="sxs-lookup"><span data-stu-id="112bf-127">COPY_ONLY has no effect when specified with the DIFFERENTIAL option.</span></span>  
  
-   <span data-ttu-id="112bf-128">Pour une sauvegarde de fichier journal de type copie uniquement</span><span class="sxs-lookup"><span data-stu-id="112bf-128">For a copy-only log backup:</span></span>  
  
     <span data-ttu-id="112bf-129">SAUVEGARDER les *database_name* du journal sur *\<*backup_device*>* ... AVEC COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="112bf-129">BACKUP LOG *database_name* TO *\<*backup_device*>* ... WITH COPY_ONLY ...</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="112bf-130">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="112bf-130">Using PowerShell</span></span>  
  
<span data-ttu-id="112bf-131">Utilisez l'applet de commande `Backup-SqlDatabase` avec le paramètre `-CopyOnly`.</span><span class="sxs-lookup"><span data-stu-id="112bf-131">Use the `Backup-SqlDatabase` cmdlet with the `-CopyOnly` parameter.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="112bf-132">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="112bf-132">Related Tasks</span></span>  

### <a name="to-create-a-full-or-log-backup"></a><span data-ttu-id="112bf-133">Pour créer une sauvegarde complète ou de fichier journal</span><span class="sxs-lookup"><span data-stu-id="112bf-133">To create a full or log backup</span></span>
  
-   [<span data-ttu-id="112bf-134">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="112bf-134">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="112bf-135">Sauvegarder un journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="112bf-135">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
### <a name="to-view-copy-only-backups"></a><span data-ttu-id="112bf-136">Pour afficher des sauvegardes de copie uniquement</span><span class="sxs-lookup"><span data-stu-id="112bf-136">To view copy-only backups</span></span>
  
-   [<span data-ttu-id="112bf-137">backupset &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="112bf-137">backupset &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
### <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><span data-ttu-id="112bf-138">Pour configurer et utiliser le fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="112bf-138">To set up and use the SQL Server PowerShell provider</span></span>
  
-   [<span data-ttu-id="112bf-139">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="112bf-139">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  

## <a name="see-also"></a><span data-ttu-id="112bf-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="112bf-140">See Also</span></span>  
 <span data-ttu-id="112bf-141">[Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="112bf-141">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="112bf-142">[Modes de récupération &#40;SQL Server&#41;](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="112bf-142">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="112bf-143">[Copier des bases de données avec la sauvegarde et la restauration](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="112bf-143">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="112bf-144">Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="112bf-144">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
