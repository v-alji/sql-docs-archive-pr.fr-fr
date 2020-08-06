---
title: Prise en charge d’OLTP en mémoire par Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b1cc7c30-1747-4c21-88ac-e95a5e58baac
author: rothja
ms.author: jroth
ms.openlocfilehash: bf3708a258e3bb97231e45b10bea2c59351a06a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708336"
---
# <a name="transact-sql-support-for-in-memory-oltp"></a><span data-ttu-id="92523-102">Prise en charge d'OLTP en mémoire par Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92523-102">Transact-SQL Support for In-Memory OLTP</span></span>
  <span data-ttu-id="92523-103">Vous pouvez accédez aux tables optimisées en mémoire à l'aide d'une requête Transact-SQL ou d'une instruction DML (SELECT, INSERT, UPDATE ou DELETE), d'une instruction ad hoc et d'un module SQL, par exemple des procédures stockées, des fonctions table, des fonctions scalaires, des déclencheurs et des vues.</span><span class="sxs-lookup"><span data-stu-id="92523-103">You can access memory-optimized tables using any Transact-SQL query or DML statement (SELECT, INSERT, UPDATE, or DELETE), ad hoc statement, and SQL module such as stored procedures, table-value functions, scalar functions, triggers, and views.</span></span> <span data-ttu-id="92523-104">Pour plus d’informations, consultez [accès aux tables optimisées en mémoire à l’aide de Transact-SQL interprété](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="92523-104">For more information see [Accessing Memory-Optimized Tables Using Interpreted Transact-SQL](accessing-memory-optimized-tables-using-interpreted-transact-sql.md).</span></span>  
  
 <span data-ttu-id="92523-105">Les procédures stockées qui font référence uniquement aux tables optimisées en mémoire peuvent être nativement compilées en code machine ce qui offre des gains de performances par rapport à des procédures stockées (disques) interprétées.</span><span class="sxs-lookup"><span data-stu-id="92523-105">Stored procedures that only reference memory-optimized tables can be natively compiled into machine code and typically provide significant performance gains over interpreted (disk-based) stored procedures.</span></span> <span data-ttu-id="92523-106">Pour bénéficier d'un accès optimisé aux tables optimisées en mémoire, utilisez des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="92523-106">For optimized access to memory-optimized tables use natively compiled stored procedures.</span></span> <span data-ttu-id="92523-107">Pour plus d’informations, consultez [Procédures stockées compilées en mode natif](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="92523-107">For more information, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="92523-108">Lors de la création et de la modification d'objets de base de données (instructions DDL), les instructions suivantes ont été modifiées :</span><span class="sxs-lookup"><span data-stu-id="92523-108">When creating and modifying database objects (DDL statements), the following statements have been modified:</span></span>  
  
-   <span data-ttu-id="92523-109">[Options de fichier et de groupe de fichiers ALTER database &#40;&#41;Transact-SQL](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (voir `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="92523-109">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="92523-110">[Créer une &#40;de base de données SQL Server&#41;Transact-SQL](/sql/t-sql/statements/create-database-sql-server-transact-sql) (voir `MEMORY_OPTIMIZED_DATA` )</span><span class="sxs-lookup"><span data-stu-id="92523-110">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) (see `MEMORY_OPTIMIZED_DATA`)</span></span>  
  
-   <span data-ttu-id="92523-111">[Créer une procédure &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-procedure-transact-sql) (voir `NATIVE_COMPILATION` , `SCHEMABINDING` , `EXECUTE AS` et `BEGIN ATOMIC` )</span><span class="sxs-lookup"><span data-stu-id="92523-111">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) (see `NATIVE_COMPILATION`, `SCHEMABINDING`, `EXECUTE AS`, and `BEGIN ATOMIC`)</span></span>  
  
-   <span data-ttu-id="92523-112">[Create table &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-table-transact-sql) (voir `MEMORY_OPTIMIZED` ,,, `DURABILITY` `BUCKET_COUNT` `INDEX` et `HASH` )</span><span class="sxs-lookup"><span data-stu-id="92523-112">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) (see `MEMORY_OPTIMIZED`, `DURABILITY`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="92523-113">[Créer un type &#40;&#41;Transact-SQL](/sql/t-sql/statements/create-type-transact-sql) (voir `MEMORY_OPTIMIZED` ,, `BUCKET_COUNT` `INDEX` et `HASH` )</span><span class="sxs-lookup"><span data-stu-id="92523-113">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) (see `MEMORY_OPTIMIZED`, `BUCKET_COUNT`, `INDEX`, and `HASH`)</span></span>  
  
-   <span data-ttu-id="92523-114">[Déclarer @local_variable &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (voir `NULL`  |  `NOT NULL` )</span><span class="sxs-lookup"><span data-stu-id="92523-114">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) (see `NULL` | `NOT NULL`)</span></span>  
  
 <span data-ttu-id="92523-115">Les tables optimisées en mémoire prennent en charge `PRIMARY KEY` et `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="92523-115">Memory-optimized tables support `PRIMARY KEY` and `NOT NULL` constraints.</span></span> <span data-ttu-id="92523-116">Pour plus d’informations sur l’implémentation de contraintes non prises en charge, consultez [migration de contraintes de vérification et de clé étrangère](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="92523-116">For information on implementing unsupported constraints, see [Migrating Check and Foreign Key Constraints](../../database-engine/migrating-check-and-foreign-key-constraints.md).</span></span>  
  
 <span data-ttu-id="92523-117">Pour plus d’informations sur les fonctionnalités non prises en charge, consultez [Les constructions Transact-SQL ne sont pas prises en charge par l’OLTP en mémoire](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="92523-117">For information on unsupported features, see [Transact-SQL Constructs Not Supported by In-Memory OLTP](transact-sql-constructs-not-supported-by-in-memory-oltp.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92523-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="92523-118">In This Section</span></span>  
  
-   [<span data-ttu-id="92523-119">Types de données pris en charge</span><span class="sxs-lookup"><span data-stu-id="92523-119">Supported Data Types</span></span>](supported-data-types-for-in-memory-oltp.md)  
  
-   [<span data-ttu-id="92523-120">Accès aux tables optimisées en mémoire à l’aide du Transact-SQL interprété</span><span class="sxs-lookup"><span data-stu-id="92523-120">Accessing Memory-Optimized Tables Using Interpreted Transact-SQL</span></span>](accessing-memory-optimized-tables-using-interpreted-transact-sql.md)  
  
-   [<span data-ttu-id="92523-121">Vues système, procédures stockées, DMV et types d’attente pour l’OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="92523-121">System Views, Stored Procedures, DMVs and Wait Types for In-Memory OLTP</span></span>](../../database-engine/system-views-stored-procedures-dmvs-and-wait-types-for-in-memory-oltp.md)  
  
## <a name="see-also"></a><span data-ttu-id="92523-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92523-122">See Also</span></span>  
 <span data-ttu-id="92523-123">[OLTP en mémoire &#40;optimisation en mémoire&#41;](in-memory-oltp-in-memory-optimization.md) </span><span class="sxs-lookup"><span data-stu-id="92523-123">[In-Memory OLTP &#40;In-Memory Optimization&#41;](in-memory-oltp-in-memory-optimization.md) </span></span>  
 <span data-ttu-id="92523-124">[Problèmes de migration pour les procédures stockées compilées en mode natif](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="92523-124">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 <span data-ttu-id="92523-125">[Fonctionnalités de SQL Server prises en charge](unsupported-sql-server-features-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="92523-125">[Supported SQL Server Features](unsupported-sql-server-features-for-in-memory-oltp.md) </span></span>  
 [<span data-ttu-id="92523-126">Procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="92523-126">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
