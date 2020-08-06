---
title: Gérer la table suspect_pages (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
- restoring pages [SQL Server]
- pages [SQL Server], suspect
- pages [SQL Server], restoring
- suspect_pages system table
- suspect pages [SQL Server]
- restoring [SQL Server], pages
ms.assetid: f394d4bc-1518-4e61-97fc-bf184d972e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dd7aea63ae85a16e23ff532c7e18ace3c376a707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614664"
---
# <a name="manage-the-suspect_pages-table-sql-server"></a><span data-ttu-id="713f7-102">Gérer la table suspect_pages (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="713f7-102">Manage the suspect_pages Table (SQL Server)</span></span>
  <span data-ttu-id="713f7-103">Cette rubrique explique comment gérer la table **suspect_pages** dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="713f7-103">This topic describes how to manage the **suspect_pages** table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="713f7-104">La table **suspect_pages** est conçue pour gérer les informations sur les pages suspectes et aide à déterminer si une restauration est nécessaire ou non.</span><span class="sxs-lookup"><span data-stu-id="713f7-104">The **suspect_pages** table is used for maintaining information about suspect pages, and is relevant in helping to decide whether a restore is necessary.</span></span> <span data-ttu-id="713f7-105">La table [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) réside dans la [base de données msdb](../databases/msdb-database.md).</span><span class="sxs-lookup"><span data-stu-id="713f7-105">The [suspect_pages](/sql/relational-databases/system-tables/suspect-pages-transact-sql) table resides in the [msdb database](../databases/msdb-database.md).</span></span>  
  
 <span data-ttu-id="713f7-106">Une page est considérée « suspecte » quand le [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] rencontre l'une des erreurs suivantes alors qu'il essaie de lire une page de données :</span><span class="sxs-lookup"><span data-stu-id="713f7-106">A page is considered "suspect" when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] encounters one of the following errors when it tries to read a data page:</span></span>  
  
-   <span data-ttu-id="713f7-107">Une [erreur 823](../errors-events/mssqlserver-823-database-engine-error.md) provoquée par un contrôle de redondance cyclique (CRC) émis par le système d’exploitation, telle qu’une erreur disque (certaines erreurs matérielles)</span><span class="sxs-lookup"><span data-stu-id="713f7-107">An [823 error](../errors-events/mssqlserver-823-database-engine-error.md) that was caused by a cyclic redundancy check (CRC) issued by the operating system, such as a disk error (certain hardware errors)</span></span>  
  
-   <span data-ttu-id="713f7-108">Une [erreur 824](../errors-events/mssqlserver-824-database-engine-error.md), telle qu’une page endommagée (toute erreur logique)</span><span class="sxs-lookup"><span data-stu-id="713f7-108">An [824 error](../errors-events/mssqlserver-824-database-engine-error.md), such as a torn page (any logical error)</span></span>  
  
 <span data-ttu-id="713f7-109">L’ID de page de chaque page suspecte est enregistré dans la table **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="713f7-109">The page ID of every suspect page is recorded in the **suspect_pages** table.</span></span> <span data-ttu-id="713f7-110">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] enregistre toutes les pages suspectes détectées lors du traitement standard, notamment dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="713f7-110">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] records any suspect pages encountered during regular processing, such as the following:</span></span>  
  
-   <span data-ttu-id="713f7-111">une requête doit lire une page ;</span><span class="sxs-lookup"><span data-stu-id="713f7-111">A query has to read a page.</span></span>  
  
-   <span data-ttu-id="713f7-112">au cours d'une opération DBCC CHECKDB ;</span><span class="sxs-lookup"><span data-stu-id="713f7-112">During a DBCC CHECKDB operation.</span></span>  
  
-   <span data-ttu-id="713f7-113">au cours d'une opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="713f7-113">During a backup operation.</span></span>  
  
 <span data-ttu-id="713f7-114">La table **suspect_pages** est aussi mise à jour selon les besoins au cours d’une opération de restauration, une opération de réparation DBCC ou une opération de suppression de base de données.</span><span class="sxs-lookup"><span data-stu-id="713f7-114">The **suspect_pages** table is also updated as necessary during a restore operation, a DBCC repair operation, or a drop database operation.</span></span>  
  
 <span data-ttu-id="713f7-115">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="713f7-115">**In This Topic**</span></span>  
  
-   <span data-ttu-id="713f7-116">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="713f7-116">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="713f7-117">Recommandations</span><span class="sxs-lookup"><span data-stu-id="713f7-117">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="713f7-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="713f7-118">Security</span></span>](#Security)  
  
-   <span data-ttu-id="713f7-119">**Pour gérer la table suspect_pages, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="713f7-119">**To manage the suspect_pages table, using:**</span></span>  
  
     [<span data-ttu-id="713f7-120">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="713f7-120">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="713f7-121">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="713f7-121">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="713f7-122">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="713f7-122">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="713f7-123">Recommandations</span><span class="sxs-lookup"><span data-stu-id="713f7-123">Recommendations</span></span>  
  
-   <span data-ttu-id="713f7-124">**Erreurs enregistrées dans la table suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="713f7-124">**Errors Recorded in suspect_pages Table**</span></span>  
  
     <span data-ttu-id="713f7-125">La table **suspect_pages** contient une ligne pour chaque page dans laquelle une erreur 824 (avec une limite de 1 000 lignes) s’est produite.</span><span class="sxs-lookup"><span data-stu-id="713f7-125">The **suspect_pages** table contains one row per page that failed with an 824 error, up to a limit of 1,000 rows.</span></span> <span data-ttu-id="713f7-126">Le tableau suivant présente les erreurs consignées dans la colonne **event_type** de la table **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="713f7-126">The following table shows errors logged in the **event_type** column of the **suspect_pages** table.</span></span>  
  
    |<span data-ttu-id="713f7-127">Description de l'erreur</span><span class="sxs-lookup"><span data-stu-id="713f7-127">Error description</span></span>|<span data-ttu-id="713f7-128">Valeur**event_type**</span><span class="sxs-lookup"><span data-stu-id="713f7-128">**event_type** value</span></span>|  
    |-----------------------|---------------------------|  
    |<span data-ttu-id="713f7-129">Erreur 823 provoquée par une erreur CRC du système d'exploitation ou erreur 824 autre qu'une somme de contrôle incorrecte ou une page endommagée (par exemple, ID de page incorrect)</span><span class="sxs-lookup"><span data-stu-id="713f7-129">823 error caused by an operating system CRC error  or 824 error other than a bad checksum or a torn page (for example, a bad page ID)</span></span>|<span data-ttu-id="713f7-130">1</span><span class="sxs-lookup"><span data-stu-id="713f7-130">1</span></span>|  
    |<span data-ttu-id="713f7-131">Somme de contrôle incorrecte</span><span class="sxs-lookup"><span data-stu-id="713f7-131">Bad checksum</span></span>|<span data-ttu-id="713f7-132">2</span><span class="sxs-lookup"><span data-stu-id="713f7-132">2</span></span>|  
    |<span data-ttu-id="713f7-133">Page endommagée</span><span class="sxs-lookup"><span data-stu-id="713f7-133">Torn page</span></span>|<span data-ttu-id="713f7-134">3</span><span class="sxs-lookup"><span data-stu-id="713f7-134">3</span></span>|  
    |<span data-ttu-id="713f7-135">Page restaurée (la page a été restaurée après avoir été marquée comme incorrecte)</span><span class="sxs-lookup"><span data-stu-id="713f7-135">Restored (The page was restored after it was marked bad)</span></span>|<span data-ttu-id="713f7-136">4</span><span class="sxs-lookup"><span data-stu-id="713f7-136">4</span></span>|  
    |<span data-ttu-id="713f7-137">Réparée (DBCC, AlwaysOn ou la mise en miroir a réparé la page)</span><span class="sxs-lookup"><span data-stu-id="713f7-137">Repaired (DBCC, AlwaysOn, or mirroring repaired the page)</span></span>|<span data-ttu-id="713f7-138">5</span><span class="sxs-lookup"><span data-stu-id="713f7-138">5</span></span>|  
    |<span data-ttu-id="713f7-139">Page désallouée par DBCC</span><span class="sxs-lookup"><span data-stu-id="713f7-139">Deallocated by DBCC</span></span>|<span data-ttu-id="713f7-140">7</span><span class="sxs-lookup"><span data-stu-id="713f7-140">7</span></span>|  
  
     <span data-ttu-id="713f7-141">La table **suspect_pages** enregistre aussi les erreurs temporaires.</span><span class="sxs-lookup"><span data-stu-id="713f7-141">The **suspect_pages** table also records transient errors.</span></span> <span data-ttu-id="713f7-142">Elles peuvent être le résultat notamment d'une erreur d'E/S (un câble déconnecté, par exemple) ou de l'échec temporaire d'un test de somme de contrôle répété sur une page.</span><span class="sxs-lookup"><span data-stu-id="713f7-142">Sources of transient errors include an I/O error (for example, a cable was disconnected) or a page that temporarily fails a repeated checksum test.</span></span>  
  
-   <span data-ttu-id="713f7-143">**Mise à jour de la table suspect_pages à l'aide du moteur de base de données**</span><span class="sxs-lookup"><span data-stu-id="713f7-143">**How the Database Engine Updates the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="713f7-144">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] entreprend les actions suivantes dans la table **suspect_pages** :</span><span class="sxs-lookup"><span data-stu-id="713f7-144">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] takes the following actions on the **suspect_pages** table:</span></span>  
  
    -   <span data-ttu-id="713f7-145">Si la table n'est pas remplie, elle est mise à jour à chaque erreur 824 afin de signaler qu'une erreur s'est produite, et le compteur d'erreurs est incrémenté.</span><span class="sxs-lookup"><span data-stu-id="713f7-145">If the table is not full, it is updated for every 824 error, to indicate that an error has occurred, and the error counter is incremented.</span></span> <span data-ttu-id="713f7-146">Si une page comporte une erreur après qu’elle a été corrigée par réparation, restauration ou désallocation, son nombre **number_of_errors** est incrémenté et sa colonne **last_update** est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="713f7-146">If a page has an error after it is fixed by being repaired, restored, or deallocated, its **number_of_errors** count is incremented and its **last_update** column is updated</span></span>  
  
    -   <span data-ttu-id="713f7-147">Après la correction d’une page répertoriée par une opération de restauration ou de réparation, cette opération met à jour la ligne **suspect_pages** pour indiquer que la page est réparée (**event_type** = 5) ou restaurée (**event_type** = 4).</span><span class="sxs-lookup"><span data-stu-id="713f7-147">After a listed page is fixed by a restore or a repair operation, the operation updates the **suspect_pages** row to indicate that the page is repaired (**event_type** = 5) or restored (**event_type** = 4).</span></span>  
  
    -   <span data-ttu-id="713f7-148">Si vous procédez à une vérification DBCC, toutes les pages exemptes d’erreurs sont marquées comme étant réparées (**event_type** = 5) ou désallouées (**event_type** = 7).</span><span class="sxs-lookup"><span data-stu-id="713f7-148">If a DBCC check is run, the check marks any error-free pages as repaired (**event_type** = 5) or deallocated (**event_type** = 7).</span></span>  
  
-   <span data-ttu-id="713f7-149">**Mises à jour automatiques dans la table suspect_pages**</span><span class="sxs-lookup"><span data-stu-id="713f7-149">**Automatic Updates to the suspect_pages Table**</span></span>  
  
     <span data-ttu-id="713f7-150">Un serveur partenaire de mise en miroir de bases de données ou un réplica de disponibilité AlwaysOn met à jour la table **suspect_pages** après l'échec d'une tentative de lecture d'une page d'un fichier de données pour l'une des raisons suivantes.</span><span class="sxs-lookup"><span data-stu-id="713f7-150">A database mirroring partner or AlwaysOn availability replica updates the **suspect_pages** table after an attempt to read a page from a data file fails for one of the following reasons.</span></span>  
  
    -   <span data-ttu-id="713f7-151">Une erreur 823 provoquée par une erreur CRC du système d'exploitation</span><span class="sxs-lookup"><span data-stu-id="713f7-151">An 823 error that is caused by an operating system CRC error.</span></span>  
  
    -   <span data-ttu-id="713f7-152">Une erreur 824 (altération logique telle qu'une page endommagée)</span><span class="sxs-lookup"><span data-stu-id="713f7-152">An 824 error (logical corruption such as a torn page).</span></span>  
  
     <span data-ttu-id="713f7-153">Les actions suivantes mettent également à jour automatiquement des lignes de la table **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="713f7-153">The following actions also automatically update rows in the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="713f7-154">DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS met à jour la table **suspect_pages** pour indiquer chaque page qu’il a désallouée ou réparée.</span><span class="sxs-lookup"><span data-stu-id="713f7-154">DBCC CHECKDB REPAIR_ALLOW_DATA_LOSS updates the **suspect_pages** table to indicate each page that it has deallocated or repaired.</span></span>  
  
    -   <span data-ttu-id="713f7-155">Une restauration (RESTORE) complète de fichier ou de page marque les entrées de pages comme restaurées.</span><span class="sxs-lookup"><span data-stu-id="713f7-155">A full, file, or page RESTORE marks the page entries as restored.</span></span>  
  
     <span data-ttu-id="713f7-156">Les actions suivantes suppriment automatiquement des lignes de la table **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="713f7-156">The following actions automatically delete rows from the **suspect_pages** table.</span></span>  
  
    -   <span data-ttu-id="713f7-157">ALTER DATABASE REMOVE FILE</span><span class="sxs-lookup"><span data-stu-id="713f7-157">ALTER DATABASE REMOVE FILE</span></span>  
  
    -   <span data-ttu-id="713f7-158">DROP DATABASE</span><span class="sxs-lookup"><span data-stu-id="713f7-158">DROP DATABASE</span></span>  
  
-   <span data-ttu-id="713f7-159">**Rôle de maintenance de l'administrateur de base de données**</span><span class="sxs-lookup"><span data-stu-id="713f7-159">**Maintenance Role of the Database Administrator**</span></span>  
  
     <span data-ttu-id="713f7-160">Les administrateurs de base de données sont responsables de la gestion de la table ; leur rôle consiste principalement à supprimer les lignes anciennes.</span><span class="sxs-lookup"><span data-stu-id="713f7-160">Database administrators are responsible for managing the table, primarily by deleting old rows.</span></span> <span data-ttu-id="713f7-161">La table **suspect_pages** est limitée en taille ; une fois la table remplie, les nouvelles erreurs ne sont plus consignées.</span><span class="sxs-lookup"><span data-stu-id="713f7-161">The **suspect_pages** table is limited in size, and if it fills, new errors are not logged.</span></span> <span data-ttu-id="713f7-162">Pour empêcher la saturation de la table, l'administrateur de la base de données ou l'administrateur système doit manuellement y effacer les anciennes entrées en supprimant les lignes.</span><span class="sxs-lookup"><span data-stu-id="713f7-162">To prevent this table from filling up, the database administrator or system administrator must manually clear out old entries from this table by deleting rows.</span></span> <span data-ttu-id="713f7-163">Ainsi, nous vous recommandons de supprimer ou d’archiver régulièrement les lignes comportant un **event_type** restauré ou réparé, ou les lignes comportant une valeur ancienne pour **last_update** .</span><span class="sxs-lookup"><span data-stu-id="713f7-163">Therefore, we recommend that you periodically delete or archive rows that have an **event_type** of restored or repaired, or rows that have an old **last_update** value.</span></span>  
  
     <span data-ttu-id="713f7-164">Pour surveiller l’activité sur la table suspect_pages, vous pouvez utiliser la [classe d’événements Database Suspect Data Page](../event-classes/database-suspect-data-page-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="713f7-164">To monitor the activity on the suspect_pages table, you can use the [Database Suspect Data Page Event Class](../event-classes/database-suspect-data-page-event-class.md).</span></span> <span data-ttu-id="713f7-165">Des lignes sont parfois ajoutées à la table **suspect_pages** à cause d’erreurs temporaires.</span><span class="sxs-lookup"><span data-stu-id="713f7-165">Rows are sometimes added to the **suspect_pages** table because of transient errors.</span></span> <span data-ttu-id="713f7-166">Cependant, si de nombreuses lignes sont ajoutées à la table, le sous-système d'E/S est probablement défectueux.</span><span class="sxs-lookup"><span data-stu-id="713f7-166">If many rows are being added to the table, however, a problem probably exists with the I/O subsystem.</span></span> <span data-ttu-id="713f7-167">Si vous remarquez une augmentation soudaine du nombre de lignes ajoutées à la table, nous vous recommandons de rechercher la source des problèmes éventuels dans le sous-système d'E/S.</span><span class="sxs-lookup"><span data-stu-id="713f7-167">If you notice a sudden increase in the number of rows being added to the table, we recommend that you investigate possible problems in your I/O subsystem.</span></span>  
  
     <span data-ttu-id="713f7-168">Un administrateur de base de données peut également insérer ou mettre à jour des enregistrements.</span><span class="sxs-lookup"><span data-stu-id="713f7-168">A database administrator can also insert or update records.</span></span> <span data-ttu-id="713f7-169">Par exemple, la mise à jour d'une ligne peut être utile si un administrateur de base de données sait qu'une page suspecte particulière est intacte en réalité, mais souhaite malgré tout conserver l'enregistrement correspondant pendant un certain temps.</span><span class="sxs-lookup"><span data-stu-id="713f7-169">For example, updating a row might useful when the database administrator knows that a particular suspect page is actually intact, but wants to preserve the record for a while.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="713f7-170">Sécurité</span><span class="sxs-lookup"><span data-stu-id="713f7-170">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="713f7-171">Autorisations</span><span class="sxs-lookup"><span data-stu-id="713f7-171">Permissions</span></span>  
 <span data-ttu-id="713f7-172">Toute personne ayant accès à **msdb** peut lire les données de la table **suspect_pages** .</span><span class="sxs-lookup"><span data-stu-id="713f7-172">Anyone with access to **msdb** can read the data in the **suspect_pages** table.</span></span> <span data-ttu-id="713f7-173">Toute personne ayant l'autorisation UPDATE sur la table suspect_pages peut mettre à jour ses enregistrements.</span><span class="sxs-lookup"><span data-stu-id="713f7-173">Anyone with UPDATE permission on the suspect_pages table can update its records.</span></span> <span data-ttu-id="713f7-174">Les membres du rôle de base de données fixe **db_owner** sur **msdb** ou du rôle serveur fixe **sysadmin** peuvent insérer, mettre à jour et supprimer des enregistrements.</span><span class="sxs-lookup"><span data-stu-id="713f7-174">Members the **db_owner** fixed database role on **msdb** or the **sysadmin** fixed server role can insert, update, and delete records.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="713f7-175">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="713f7-175">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="713f7-176">Pour gérer la table suspect_pages</span><span class="sxs-lookup"><span data-stu-id="713f7-176">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="713f7-177">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], développez cette instance, puis développez **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="713f7-177">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="713f7-178">Développez **Bases de données système**, puis **msdb**, **Tables**et **Tables système**.</span><span class="sxs-lookup"><span data-stu-id="713f7-178">Expand **System Databases**, expand **msdb**, expand **Tables**, and then expand **System Tables**.</span></span>  
  
3.  <span data-ttu-id="713f7-179">Développez **dbo.suspect_pages** et cliquez avec le bouton droit sur **Modifier les 200 lignes du haut**.</span><span class="sxs-lookup"><span data-stu-id="713f7-179">Expand **dbo.suspect_pages** and right-click **Edit Top 200 Rows**.</span></span>  
  
4.  <span data-ttu-id="713f7-180">Dans la fenêtre de requête, modifiez, mettez à jour ou supprimez les lignes de votre choix.</span><span class="sxs-lookup"><span data-stu-id="713f7-180">In the query window, edit, update, or delete the rows that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="713f7-181">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="713f7-181">Using Transact-SQL</span></span>  
  
#### <a name="to-manage-the-suspect_pages-table"></a><span data-ttu-id="713f7-182">Pour gérer la table suspect_pages</span><span class="sxs-lookup"><span data-stu-id="713f7-182">To manage the suspect_pages table</span></span>  
  
1.  <span data-ttu-id="713f7-183">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="713f7-183">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="713f7-184">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="713f7-184">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="713f7-185">Copiez et collez les exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="713f7-185">Copy and paste the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="713f7-186">Cet exemple supprime certaines des lignes de la table `suspect_pages` .</span><span class="sxs-lookup"><span data-stu-id="713f7-186">This example deletes some of the rows from the `suspect_pages` table.</span></span>  
  
```  
-- Delete restored, repaired, or deallocated pages.  
DELETE FROM msdb..suspect_pages  
   WHERE (event_type = 4 OR event_type = 5 OR event_type = 7);  
GO  
  
```  
  
 <span data-ttu-id="713f7-187">Cet exemple retourne les pages incorrectes dans la table `suspect_pages` .</span><span class="sxs-lookup"><span data-stu-id="713f7-187">This example returns the bad pages in the `suspect_pages` table.</span></span>  
  
```  
-- Select nonspecific 824, bad checksum, and torn page errors.  
SELECT * FROM msdb..suspect_pages  
   WHERE (event_type = 1 OR event_type = 2 OR event_type = 3);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="713f7-188"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="713f7-188">See Also</span></span>  
 <span data-ttu-id="713f7-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="713f7-189">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 <span data-ttu-id="713f7-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="713f7-190">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="713f7-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="713f7-191">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="713f7-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="713f7-192">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="713f7-193">[Restaurer des pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="713f7-193">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 <span data-ttu-id="713f7-194">[suspect_pages &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="713f7-194">[suspect_pages &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/suspect-pages-transact-sql) </span></span>  
 <span data-ttu-id="713f7-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="713f7-195">[MSSQLSERVER_823](../errors-events/mssqlserver-823-database-engine-error.md) </span></span>  
 [<span data-ttu-id="713f7-196">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="713f7-196">MSSQLSERVER_824</span></span>](../errors-events/mssqlserver-824-database-engine-error.md)  
  
  
