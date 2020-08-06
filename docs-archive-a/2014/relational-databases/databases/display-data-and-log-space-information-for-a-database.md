---
title: Afficher les informations sur l’espace occupé par les données et par le journal d’une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], space
- status information [SQL Server], space
- displaying space information
- disk space [SQL Server], displaying
- databases [SQL Server], space used
- viewing space information
- space allocation [SQL Server], displaying
- data space [SQL Server]
ms.assetid: c7b99463-4bab-4e9b-9217-fcb0898dc757
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1beb8cdedbc2b72eadeeb350ee1c3b6d16218205
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709555"
---
# <a name="display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="b4daa-102">Afficher les informations sur l'espace occupé par les données et par le journal d'une base de données</span><span class="sxs-lookup"><span data-stu-id="b4daa-102">Display Data and Log Space Information for a Database</span></span>
  <span data-ttu-id="b4daa-103">Cette rubrique explique comment afficher des informations sur l'espace occupé par les données et par le journal d'une base de données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4daa-103">This topic describes how to display the data and log space information for a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b4daa-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b4daa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b4daa-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b4daa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b4daa-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b4daa-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b4daa-107">**Pour afficher les informations sur l'espace occupé par les données et par le journal d'une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b4daa-107">**To display data and log space information for a database, using:**</span></span>  
  
     [<span data-ttu-id="b4daa-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b4daa-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b4daa-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4daa-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b4daa-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b4daa-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b4daa-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b4daa-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b4daa-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b4daa-112">Permissions</span></span>  
 <span data-ttu-id="b4daa-113">L’autorisation d’exécuter **sp_spaceused** est accordée au rôle **public** .</span><span class="sxs-lookup"><span data-stu-id="b4daa-113">Permission to execute **sp_spaceused** is granted to the **public** role.</span></span> <span data-ttu-id="b4daa-114">Seuls les membres du rôle de base de données fixe **db_owner** peuvent spécifier le paramètre **@updateusage** .</span><span class="sxs-lookup"><span data-stu-id="b4daa-114">Only members of the **db_owner** fixed database role can specify the **@updateusage** parameter.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b4daa-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b4daa-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="b4daa-116">Pour afficher les informations sur l'espace occupé par les données et par le journal d'une base de données</span><span class="sxs-lookup"><span data-stu-id="b4daa-116">To display data and log space information for a database</span></span>  
  
1.  <span data-ttu-id="b4daa-117">Dans l'Explorateur d'objets, connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="b4daa-117">In Object Explorer, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="b4daa-118">Développez **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="b4daa-118">Expand **Databases**.</span></span>  
  
3.  <span data-ttu-id="b4daa-119">Cliquez avec le bouton droit sur une base de données, pointez sur **Rapports**, sur **Rapports standard**, puis cliquez sur **Utilisation du disque**.</span><span class="sxs-lookup"><span data-stu-id="b4daa-119">Right-click a database, point to **Reports**, point to **Standard Reports,**, and then click **Disk Usage**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b4daa-120">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4daa-120">Using Transact-SQL</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-using-sp_spaceused"></a><span data-ttu-id="b4daa-121">Pour afficher les informations sur l'espace occupé par les données et par le journal d'une base de données à l'aide de sp_spaceused</span><span class="sxs-lookup"><span data-stu-id="b4daa-121">To display data and log space information for a database by using sp_spaceused</span></span>  
  
1.  <span data-ttu-id="b4daa-122">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4daa-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b4daa-123">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b4daa-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b4daa-124">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b4daa-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b4daa-125">Cet exemple utilise la procédure stockée système [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) pour communiquer des informations sur l’espace disque pour la table `Vendor` et ses index.</span><span class="sxs-lookup"><span data-stu-id="b4daa-125">This example uses the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure to report disk space information for the `Vendor` table and its indexes.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_spaceused N'Purchasing.Vendor';  
GO  
```  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-querying-sysdatabase_files"></a><span data-ttu-id="b4daa-126">Pour afficher les informations sur l'espace occupé par les données et par le journal d'une base de données en interrogeant sys.database_files</span><span class="sxs-lookup"><span data-stu-id="b4daa-126">To display data and log space information for a database by querying sys.database_files</span></span>  
  
1.  <span data-ttu-id="b4daa-127">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4daa-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b4daa-128">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b4daa-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b4daa-129">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b4daa-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b4daa-130">L’exemple suivant interroge l’affichage catalogue [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) pour retourner des informations spécifiques sur les fichiers de données et les fichiers journaux de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4daa-130">This example queries the [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) catalog view to return specific information about the data and log files in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT file_id, name, type_desc, physical_name, size, max_size  
FROM sys.database_files ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4daa-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4daa-131">See Also</span></span>  
 <span data-ttu-id="b4daa-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b4daa-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="b4daa-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b4daa-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="b4daa-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b4daa-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span></span>  
 <span data-ttu-id="b4daa-135">[Ajouter des fichiers de données ou journaux à une base de données](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="b4daa-135">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="b4daa-136">Supprimer des fichiers de données ou des fichiers journaux d’une base de données</span><span class="sxs-lookup"><span data-stu-id="b4daa-136">Delete Data or Log Files from a Database</span></span>](delete-data-or-log-files-from-a-database.md)  
  
  
