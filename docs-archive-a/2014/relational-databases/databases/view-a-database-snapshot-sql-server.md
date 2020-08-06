---
title: Afficher un instantané de base de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], viewing
- displaying database snapshots
- viewing database snapshots
ms.assetid: 123f19b2-0850-4033-8507-59ebdfb368ee
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92c5c557656e87be562e9d5477f14f66b2c39e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708435"
---
# <a name="view-a-database-snapshot-sql-server"></a><span data-ttu-id="26c28-102">Afficher un instantané de base de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="26c28-102">View a Database Snapshot (SQL Server)</span></span>
  <span data-ttu-id="26c28-103">Cette rubrique explique comment afficher un instantané de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26c28-103">This topic explains how to view a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="26c28-104">Pour créer, restaurer ou supprimer un instantané de base de données, vous devez impérativement utiliser [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26c28-104">To create, revert to, or delete a database snapshot, you must use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="26c28-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="26c28-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="26c28-106">**Pour afficher un instantané de base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="26c28-106">**To view a database snapshot, using:**</span></span>  
  
     [<span data-ttu-id="26c28-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26c28-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="26c28-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26c28-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="26c28-109">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26c28-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="26c28-110">**Pour afficher un instantané de base de données**</span><span class="sxs-lookup"><span data-stu-id="26c28-110">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="26c28-111">Dans l'Explorateur d'objets, connectez-vous à l'instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="26c28-111">In Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="26c28-112">Développez **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="26c28-112">Expand **Databases.**</span></span>  
  
3.  <span data-ttu-id="26c28-113">Développez **Instantanés de base de données**et sélectionnez l’instantané que vous voulez afficher.</span><span class="sxs-lookup"><span data-stu-id="26c28-113">Expand **Database Snapshots**, and select the snapshot you want to view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="26c28-114">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26c28-114">Using Transact-SQL</span></span>  
 <span data-ttu-id="26c28-115">**Pour afficher un instantané de base de données**</span><span class="sxs-lookup"><span data-stu-id="26c28-115">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="26c28-116">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26c28-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="26c28-117">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="26c28-117">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="26c28-118">Pour répertorier les instantanés de base de données de l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], interrogez la colonne **source_database_id** de l’affichage catalogue [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) pour les valeurs non-NULL.</span><span class="sxs-lookup"><span data-stu-id="26c28-118">To list the database snapshots of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], query the **source_database_id** column of the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view for non-NULL values.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="26c28-119">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="26c28-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="26c28-120">Créer un instantané de base de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="26c28-120">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="26c28-121">Rétablir une base de données dans l’état d’un instantané de base de données</span><span class="sxs-lookup"><span data-stu-id="26c28-121">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="26c28-122">Supprimer un instantané de base de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="26c28-122">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="26c28-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26c28-123">See Also</span></span>  
 [<span data-ttu-id="26c28-124">Instantanés de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="26c28-124">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
