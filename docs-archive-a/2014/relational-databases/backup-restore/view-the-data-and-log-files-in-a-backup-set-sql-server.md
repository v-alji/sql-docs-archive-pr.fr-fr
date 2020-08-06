---
title: Afficher les fichiers de données et les fichiers journaux dans un jeu de sauvegarde (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], viewing backup sets
- viewing backup set information
- backup sets [SQL Server], viewing files in
- displaying backup set information
- transaction log backups [SQL Server], viewing backup sets
- backing up [SQL Server], viewing backup sets
ms.assetid: abb6420c-f809-426e-aeb4-d0a74989cf39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7dbcb14a658b49aba6f5f2ebe3425a2ab5759efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703008"
---
# <a name="view-the-data-and-log-files-in-a-backup-set-sql-server"></a><span data-ttu-id="dc752-102">Afficher les fichiers de données et les fichiers journaux dans un jeu de sauvegarde (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dc752-102">View the Data and Log Files in a Backup Set (SQL Server)</span></span>
  <span data-ttu-id="dc752-103">Cette rubrique explique comment afficher les fichiers de données et les fichiers journaux d'un jeu de sauvegarde dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc752-103">This topic describes how to view the data and log files in a backup set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="dc752-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="dc752-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dc752-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="dc752-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dc752-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dc752-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dc752-107">**Pour afficher les fichiers de données et les fichiers journaux dans un jeu de sauvegarde, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="dc752-107">**To view the data and log files in a backup set, using:**</span></span>  
  
     [<span data-ttu-id="dc752-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dc752-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dc752-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc752-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dc752-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="dc752-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dc752-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dc752-111">Security</span></span>  
 <span data-ttu-id="dc752-112">Pour plus d’informations sur la sécurité, consultez [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="dc752-112">For information about security, see [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dc752-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="dc752-113">Permissions</span></span>  
 <span data-ttu-id="dc752-114">Dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et les versions ultérieures, l'obtention d'informations relatives à un jeu de sauvegarde ou une unité de sauvegarde requiert l'autorisation CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="dc752-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="dc752-115">Pour plus d’informations, consultez [GRANT – octroi d’autorisations de base de données &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dc752-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dc752-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dc752-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="dc752-117">Pour afficher les données et les fichiers journaux dans un jeu de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="dc752-117">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="dc752-118">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="dc752-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="dc752-119">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="dc752-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="dc752-120">Cliquez avec le bouton droit de la souris sur la base de données, puis cliquez sur **Propriétés**pour ouvrir la boîte de dialogue **Propriétés de la base de données** .</span><span class="sxs-lookup"><span data-stu-id="dc752-120">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="dc752-121">Dans le volet **Sélectionnez une page** , cliquez sur **Fichiers**.</span><span class="sxs-lookup"><span data-stu-id="dc752-121">In the **Select a Page** pane, click **Files**.</span></span>  
  
5.  <span data-ttu-id="dc752-122">Dans la grille **Fichiers de la base de données** , recherchez la liste des fichiers de données et des fichiers journaux et leurs propriétés.</span><span class="sxs-lookup"><span data-stu-id="dc752-122">Look in the **Database files** grid for a list of the data and log files and their properties.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dc752-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dc752-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="dc752-124">Pour afficher les données et les fichiers journaux dans un jeu de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="dc752-124">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="dc752-125">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc752-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dc752-126">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="dc752-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dc752-127">Utilisez l'instruction [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="dc752-127">Use the [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) statement.</span></span> <span data-ttu-id="dc752-128">Cet exemple retourne des informations sur le deuxième jeu de sauvegarde (`FILE=2`) sur l'unité de sauvegarde `AdventureWorksBackups` .</span><span class="sxs-lookup"><span data-stu-id="dc752-128">This example returns information about the second backup set (`FILE=2`) on the `AdventureWorksBackups` backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE FILELISTONLY FROM AdventureWorksBackups   
   WITH FILE=2;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc752-129"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dc752-129">See Also</span></span>  
 <span data-ttu-id="dc752-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc752-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="dc752-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc752-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="dc752-132">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc752-132">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="dc752-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc752-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="dc752-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc752-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 [<span data-ttu-id="dc752-135">Unités de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dc752-135">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
