---
title: Supprimer des groupes de fichiers obsolètes (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], defunct filegroups
- defunct filegroups
- restoring filegroups [SQL Server]
- deferred transactions
- filegroups [SQL Server], defunct
- unrestored filegroups
ms.assetid: 055f9c6a-5c18-4942-98e7-ec918f0ff975
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2bcba095d668c5c1ab317269a18af4dc996f63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705196"
---
# <a name="remove-defunct-filegroups-sql-server"></a><span data-ttu-id="5d175-102">Supprimer des groupes de fichiers obsolètes (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5d175-102">Remove Defunct Filegroups (SQL Server)</span></span>
  <span data-ttu-id="5d175-103">Cette rubrique explique comment supprimer des groupes de fichiers obsolètes dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d175-103">This topic describes how to remove defunct filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5d175-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5d175-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5d175-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5d175-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5d175-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5d175-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="5d175-107">Recommandations</span><span class="sxs-lookup"><span data-stu-id="5d175-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5d175-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5d175-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5d175-109">**Pour supprimer des groupes de fichiers obsolètes, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5d175-109">**To remove defunct filegroups, using:**</span></span>  
  
     [<span data-ttu-id="5d175-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d175-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5d175-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d175-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5d175-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5d175-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5d175-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5d175-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5d175-114">Cette rubrique concerne les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui contiennent plusieurs fichiers ou groupes de fichiers et, dans le mode simple, seulement les groupes de fichiers en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5d175-114">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that contain multiple files or filegroups; and, under the simple model, only for read-only filegroups.</span></span>  
  
-   <span data-ttu-id="5d175-115">Tous les fichiers d'un groupe de fichiers prennent l'état « ancien » quand un groupe de fichiers hors connexion est supprimé.</span><span class="sxs-lookup"><span data-stu-id="5d175-115">All files in a filegroup become defunct when an offline filegroup is removed.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5d175-116">Recommandations</span><span class="sxs-lookup"><span data-stu-id="5d175-116">Recommendations</span></span>  
  
-   <span data-ttu-id="5d175-117">Si un groupe de fichiers non restauré ne doit jamais faire l'objet d'une restauration, vous pouvez rendre le groupe de fichiers *obsolète* en le supprimant de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5d175-117">If an unrestored filegroup will never have to be restored, you can make the filegroup *defunct* by removing it from the database.</span></span> <span data-ttu-id="5d175-118">Le groupe de fichiers obsolète ne peut jamais être restauré dans cette base de données, mais ses métadonnées restent.</span><span class="sxs-lookup"><span data-stu-id="5d175-118">The defunct filegroup can never be restored to this database, but its metadata remains.</span></span> <span data-ttu-id="5d175-119">Une fois le groupe de fichiers obsolète, la base de données peut être redémarrée et la récupération assurera la cohérence de la base de données au sein des groupes de fichiers restaurés.</span><span class="sxs-lookup"><span data-stu-id="5d175-119">After the filegroup is defunct, the database can be restarted, and recovery will make the database consistent across the restored filegroups.</span></span>  
  
     <span data-ttu-id="5d175-120">Ainsi, rendre obsolète un groupe de fichiers permet de résoudre les transactions différées causées par un groupe de fichiers hors connexion qui n'a plus sa place dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5d175-120">For example, making a filegroup defunct is an option for resolving deferred transactions that were caused by an offline filegroup that you no longer want in the database.</span></span> <span data-ttu-id="5d175-121">Les transactions qui étaient différées en raison du groupe de fichiers hors connexion quittent l'état différé une fois que le groupe de fichiers est obsolète.</span><span class="sxs-lookup"><span data-stu-id="5d175-121">Transactions that were deferred because the filegroup was offline are moved out of the deferred state after the filegroup becomes defunct.</span></span> <span data-ttu-id="5d175-122">Pour plus d’informations, consultez [Transactions différées &#40;SQL Server&#41;](deferred-transactions-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5d175-122">For more information, see [Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5d175-123">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5d175-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5d175-124">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5d175-124">Permissions</span></span>  
 <span data-ttu-id="5d175-125">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="5d175-125">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5d175-126">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d175-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="5d175-127">Pour supprimer des groupes de fichiers obsolètes</span><span class="sxs-lookup"><span data-stu-id="5d175-127">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="5d175-128">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="5d175-128">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5d175-129">Développez le dossier **Bases de données**, cliquez avec le bouton droit sur la base de données de laquelle vous souhaitez supprimer le fichier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5d175-129">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5d175-130">Sélectionnez la page **Fichiers** .</span><span class="sxs-lookup"><span data-stu-id="5d175-130">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="5d175-131">Dans la grille **Fichiers de la base de données** , sélectionnez les fichiers à supprimer, cliquez sur **Supprimer**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d175-131">In the **Database files** grid, select the files to delete, click **Remove**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="5d175-132">Sélectionnez la page **Groupes de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="5d175-132">Select the **Filegroups** page.</span></span>  
  
6.  <span data-ttu-id="5d175-133">Dans la grille **Lignes** , sélectionnez le groupe de fichiers à supprimer, cliquez sur **Supprimer**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d175-133">In the **Rows** grid, select the filegroup to delete, click **Remove**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5d175-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d175-134">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="5d175-135">Pour supprimer des groupes de fichiers obsolètes</span><span class="sxs-lookup"><span data-stu-id="5d175-135">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="5d175-136">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d175-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5d175-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5d175-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5d175-138">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5d175-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5d175-139">(**Remarque :** Cet exemple part du principe que les fichiers et le groupe de fichiers existent déjà.</span><span class="sxs-lookup"><span data-stu-id="5d175-139">(**Note:** This example assumes that the files and filegroup already exist.</span></span> <span data-ttu-id="5d175-140">Pour créer ces objets, consultez l’exemple B dans la rubrique [Options de fichiers et de groupes de fichiers ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).) Le premier exemple supprime les fichiers `test1dat3` et `test1dat4` du groupe de fichiers obsolète à l'aide de l'instruction `ALTER DATABASE` avec la clause `REMOVE FILE`.</span><span class="sxs-lookup"><span data-stu-id="5d175-140">To create these objects, see example B in the [ALTER DATABASE File and Filegroup Options](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) topic.) The first example removes the `test1dat3` and `test1dat4` files from the defunct filegroup by using the `ALTER DATABASE` statement with the `REMOVE FILE` clause.</span></span> <span data-ttu-id="5d175-141">Le deuxième exemple supprime le groupe de fichiers obsolète `Test1FG1`à l'aide de la clause `REMOVE FILEGROUP` .</span><span class="sxs-lookup"><span data-stu-id="5d175-141">The second example removes the defunct filegroup `Test1FG1`by using the `REMOVE FILEGROUP` clause.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat3 ;  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat4 ;  
GO  
  
```  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILEGROUP Test1FG1 ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d175-142"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d175-142">See Also</span></span>  
 <span data-ttu-id="5d175-143">[Options de fichiers et de groupes de fichiers ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span><span class="sxs-lookup"><span data-stu-id="5d175-143">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span></span>  
 <span data-ttu-id="5d175-144">[Transactions différées &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5d175-144">[Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span></span>  
 <span data-ttu-id="5d175-145">[Restaurations de fichiers &#40;mode de récupération complète&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="5d175-145">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="5d175-146">[Restaurations de fichiers &#40;mode de récupération simple&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="5d175-146">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="5d175-147">[Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5d175-147">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="5d175-148">[Restaurer des pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5d175-148">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 [<span data-ttu-id="5d175-149">Restaurations fragmentaires &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5d175-149">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
