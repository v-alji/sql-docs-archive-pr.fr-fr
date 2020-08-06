---
title: Afficher une liste des bases de données sur une instance de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- current databases
- databases currently on server [SQL Server]
- database list [SQL Server]
- viewing database list
- displaying database list
- databases [SQL Server], viewing
- servers [SQL Server], databases listed on
- listing databases
ms.assetid: 7ee7a789-db36-4be9-8a0e-0362a1e152dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 47283fa9065a0b9d6238dab804094d9a65d17897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708432"
---
# <a name="view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="795ef-102">Afficher une liste des bases de données sur une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="795ef-102">View a List of Databases on an Instance of SQL Server</span></span>
  <span data-ttu-id="795ef-103">Cette rubrique explique comment afficher une liste des bases de données sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="795ef-103">This topic describes how to view a list of databases on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="795ef-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="795ef-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="795ef-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="795ef-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="795ef-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="795ef-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="795ef-107">**Pour afficher une liste des bases de données sur une instance de SQL Server, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="795ef-107">**To view a list of databases on an instance of SQL Server, using:**</span></span>  
  
     [<span data-ttu-id="795ef-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="795ef-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="795ef-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="795ef-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="795ef-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="795ef-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="795ef-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="795ef-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="795ef-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="795ef-112">Permissions</span></span>  
 <span data-ttu-id="795ef-113">Si l’appelant de **sys.databases** n’est pas le propriétaire de la base de données et si celle-ci n’est pas de type **master** ou **tempdb**, les autorisations minimales requises pour consulter la ligne correspondante sont les autorisations ALTER ANY DATABASE ou VIEW ANY DATABASE au niveau du serveur, ou encore l’autorisation CREATE DATABASE dans la base de données **master** .</span><span class="sxs-lookup"><span data-stu-id="795ef-113">If the caller of **sys.databases** is not the owner of the database and the database is not **master** or **tempdb**, the minimum permissions required to see the corresponding row are ALTER ANY DATABASE or VIEW ANY DATABASE server-level permission, or CREATE DATABASE permission in the **master** database.</span></span> <span data-ttu-id="795ef-114">La base de données à laquelle l'appelant est connecté peut toujours être vue dans **sys.databases**.</span><span class="sxs-lookup"><span data-stu-id="795ef-114">The database to which the caller is connected can always be viewed in **sys.databases**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="795ef-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="795ef-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="795ef-116">Pour afficher une liste des bases de données sur une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="795ef-116">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="795ef-117">Dans **l’Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], puis développez-la.</span><span class="sxs-lookup"><span data-stu-id="795ef-117">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="795ef-118">Pour afficher une liste de toutes les bases de données de l'instance, développez **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="795ef-118">To see a list of all databases on the instance, expand **Databases**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="795ef-119">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="795ef-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-list-of-databases-on-an-instance-of-sql-server"></a><span data-ttu-id="795ef-120">Pour afficher une liste des bases de données sur une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="795ef-120">To view a list of databases on an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="795ef-121">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="795ef-121">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="795ef-122">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="795ef-122">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="795ef-123">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="795ef-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="795ef-124">Cet exemple retourne une liste des bases de données de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="795ef-124">This example returns a list of databases on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="795ef-125">La liste inclut les noms des bases de données, leurs ID de base de données, et les dates auxquelles les bases de données ont été créées.</span><span class="sxs-lookup"><span data-stu-id="795ef-125">The list includes the names of the databases, their database IDs, and the dates when the databases were created.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT name, database_id, create_date  
FROM sys.databases ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="795ef-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="795ef-126">See Also</span></span>  
 <span data-ttu-id="795ef-127">[Affichages catalogue de bases de données et de fichiers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="795ef-127">[Databases and Files Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/databases-and-files-catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="795ef-128">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="795ef-128">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
