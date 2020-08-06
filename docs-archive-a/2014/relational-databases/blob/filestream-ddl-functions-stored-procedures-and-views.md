---
title: DDL, fonctions, procédures stockées et vues FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
ms.assetid: 9ecb49ee-f64e-4d30-a803-e4064a21950a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dffcc454d21a0a8dea0e98c4db2c19a4af29e948
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600084"
---
# <a name="filestream-ddl-functions-stored-procedures-and-views"></a><span data-ttu-id="d2954-102">DDL, fonctions, procédures stockées et vues FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="d2954-102">FILESTREAM DDL, Functions, Stored Procedures, and Views</span></span>
  <span data-ttu-id="d2954-103">Répertorie les instructions Transact-SQL et les objets de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui prennent en charge FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d2954-103">Lists the Transact-SQL statements and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects that support FILESTREAM.</span></span>  
  
 <span data-ttu-id="d2954-104">Pour obtenir la liste des objets de base de données qui prennent en charge la fonctionnalité FileTable, consultez [FileTable DDL, Functions, Stored Procedures, and Views](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="d2954-104">For the list of database objects that support the FileTable feature, see [FileTable DDL, Functions, Stored Procedures, and Views](../views/views.md).</span></span>  
  
##  <a name="transact-sql-data-definition-language-ddl-statements"></a><a name="ddl"></a> <span data-ttu-id="d2954-105">Instructions DDL (Data Definition Language, langage de définition de données) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d2954-105">Transact-SQL Data Definition Language (DDL) Statements</span></span>  
  
-   [<span data-ttu-id="d2954-106">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-106">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
-   [<span data-ttu-id="d2954-107">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-107">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
-   [<span data-ttu-id="d2954-108">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-108">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
-   [<span data-ttu-id="d2954-109">ALTER TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-109">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
-   [<span data-ttu-id="d2954-110">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-110">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
-   <span data-ttu-id="d2954-111">[DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="d2954-111">[DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)DROP INDEX</span></span>  
  
##  <a name="system-functions"></a><a name="func"></a> <span data-ttu-id="d2954-112">Fonctions système</span><span class="sxs-lookup"><span data-stu-id="d2954-112">System Functions</span></span>  
  
-   [<span data-ttu-id="d2954-113">GET_FILESTREAM_TRANSACTION_CONTEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-113">GET_FILESTREAM_TRANSACTION_CONTEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/get-filestream-transaction-context-transact-sql)  
  
-   [<span data-ttu-id="d2954-114">PathName &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-114">PathName &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/pathname-transact-sql)  
  
##  <a name="system-stored-procedures"></a><a name="proc"></a> <span data-ttu-id="d2954-115">Procédures stockées système</span><span class="sxs-lookup"><span data-stu-id="d2954-115">System Stored Procedures</span></span>  
  
-   [<span data-ttu-id="d2954-116">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-116">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
-   [<span data-ttu-id="d2954-117">sp_filestream_force_garbage_collection &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-117">sp_filestream_force_garbage_collection &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-filestream-force-garbage-collection)  
  
##  <a name="system-views---catalog-views"></a><a name="cat"></a> <span data-ttu-id="d2954-118">Vues système - Affichages catalogue</span><span class="sxs-lookup"><span data-stu-id="d2954-118">System Views - Catalog Views</span></span>  
  
-   [<span data-ttu-id="d2954-119">sys.database_filestream_options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-119">sys.database_filestream_options &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-filestream-options-transact-sql)  
  
##  <a name="system-views---dynamic-management-views"></a><a name="dmv"></a> <span data-ttu-id="d2954-120">Vues système – Vues de gestion dynamique</span><span class="sxs-lookup"><span data-stu-id="d2954-120">System Views - Dynamic Management Views</span></span>  
  
-   [<span data-ttu-id="d2954-121">sys.dm_filestream_file_io_handles &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-121">sys.dm_filestream_file_io_handles &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-handles-transact-sql)  
  
-   [<span data-ttu-id="d2954-122">sys.dm_filestream_file_io_requests &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2954-122">sys.dm_filestream_file_io_requests &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-file-io-requests-transact-sql)  
  
##  <a name="programming-apis"></a><a name="api"></a> <span data-ttu-id="d2954-123">API de programmation</span><span class="sxs-lookup"><span data-stu-id="d2954-123">Programming APIs</span></span>  
  
-   [<span data-ttu-id="d2954-124">Accéder à des données FILESTREAM avec OpenSqlFilestream</span><span class="sxs-lookup"><span data-stu-id="d2954-124">Access FILESTREAM Data with OpenSqlFilestream</span></span>](access-filestream-data-with-opensqlfilestream.md)  
  
-   [<span data-ttu-id="d2954-125">API managée - classe SqlFileStream</span><span class="sxs-lookup"><span data-stu-id="d2954-125">Managed API - SqlFileStream Class</span></span>](https://go.microsoft.com/fwlink/?LinkId=220875)  
  
  
