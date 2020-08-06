---
title: Types de données pris en charge | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a7380ef0-c9d7-49e4-b6de-fad34752b9f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a7dda500486c39a66f871d5934f957028fc51e9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708344"
---
# <a name="supported-data-types"></a><span data-ttu-id="04ccf-102">Types de données pris en charge</span><span class="sxs-lookup"><span data-stu-id="04ccf-102">Supported Data Types</span></span>
  <span data-ttu-id="04ccf-103">Les types de données suivants sont **pris en charge** dans les tables optimisées en mémoire et les procédures stockées compilées en mode natif :</span><span class="sxs-lookup"><span data-stu-id="04ccf-103">The following data types are **supported** in memory-optimized tables and natively compiled stored procedures:</span></span>  
  
 <span data-ttu-id="04ccf-104">**Types de données numériques**</span><span class="sxs-lookup"><span data-stu-id="04ccf-104">**Numeric Data Types**</span></span>  
  
|<span data-ttu-id="04ccf-105">Type de données</span><span class="sxs-lookup"><span data-stu-id="04ccf-105">Data type</span></span>|<span data-ttu-id="04ccf-106">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="04ccf-106">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="04ccf-107">int</span><span class="sxs-lookup"><span data-stu-id="04ccf-107">int</span></span>|[<span data-ttu-id="04ccf-108">int, bigint, smallint et tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-108">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="04ccf-109">bigint</span><span class="sxs-lookup"><span data-stu-id="04ccf-109">bigint</span></span>|[<span data-ttu-id="04ccf-110">int, bigint, smallint et tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-110">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="04ccf-111">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="04ccf-111">smallint</span></span>|[<span data-ttu-id="04ccf-112">int, bigint, smallint et tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-112">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="04ccf-113">TINYINT</span><span class="sxs-lookup"><span data-stu-id="04ccf-113">tinyint</span></span>|[<span data-ttu-id="04ccf-114">int, bigint, smallint et tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-114">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="04ccf-115">Décimal</span><span class="sxs-lookup"><span data-stu-id="04ccf-115">decimal</span></span>|[<span data-ttu-id="04ccf-116">decimal et numeric &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-116">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="04ccf-117">numeric</span><span class="sxs-lookup"><span data-stu-id="04ccf-117">numeric</span></span>|[<span data-ttu-id="04ccf-118">decimal et numeric &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-118">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="04ccf-119">float</span><span class="sxs-lookup"><span data-stu-id="04ccf-119">float</span></span>|[<span data-ttu-id="04ccf-120">float et real &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-120">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="04ccf-121">real</span><span class="sxs-lookup"><span data-stu-id="04ccf-121">real</span></span>|[<span data-ttu-id="04ccf-122">float et real &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-122">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="04ccf-123">money</span><span class="sxs-lookup"><span data-stu-id="04ccf-123">money</span></span>|[<span data-ttu-id="04ccf-124">money et smallmoney &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-124">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
|<span data-ttu-id="04ccf-125">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="04ccf-125">smallmoney</span></span>|[<span data-ttu-id="04ccf-126">money et smallmoney &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-126">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
  
 <span data-ttu-id="04ccf-127">**Types de données de chaîne**</span><span class="sxs-lookup"><span data-stu-id="04ccf-127">**String Data Types**</span></span>  
  
|<span data-ttu-id="04ccf-128">Type de données</span><span class="sxs-lookup"><span data-stu-id="04ccf-128">Data type</span></span>|<span data-ttu-id="04ccf-129">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="04ccf-129">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="04ccf-130">char(n)</span><span class="sxs-lookup"><span data-stu-id="04ccf-130">char(n)</span></span>|[<span data-ttu-id="04ccf-131">char et varchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-131">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="04ccf-132">varchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="04ccf-132">varchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="04ccf-133">char et varchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-133">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="04ccf-134">nchar(n)</span><span class="sxs-lookup"><span data-stu-id="04ccf-134">nchar(n)</span></span>|[<span data-ttu-id="04ccf-135">nchar et nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-135">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="04ccf-136">nvarchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="04ccf-136">nvarchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="04ccf-137">nchar et nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-137">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="04ccf-138">sysname</span><span class="sxs-lookup"><span data-stu-id="04ccf-138">sysname</span></span>|[<span data-ttu-id="04ccf-139">nchar et nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-139">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
  
 <span data-ttu-id="04ccf-140"><sup>1</sup> la limite est de 8060 octets par ligne au total, en comptant (n) dans les types de longueur variable.</span><span class="sxs-lookup"><span data-stu-id="04ccf-140"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="04ccf-141">Pour plus d'informations sur les classements pris en charge, voir [Collations and Code Pages](../../database-engine/collations-and-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="04ccf-141">For information about supported collations, see [Collations and Code Pages](../../database-engine/collations-and-code-pages.md).</span></span>  
  
 <span data-ttu-id="04ccf-142">**Types de données de date et d’heure**</span><span class="sxs-lookup"><span data-stu-id="04ccf-142">**Date and Time Data Types**</span></span>  
  
|<span data-ttu-id="04ccf-143">Type de données</span><span class="sxs-lookup"><span data-stu-id="04ccf-143">Data type</span></span>|<span data-ttu-id="04ccf-144">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="04ccf-144">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="04ccf-145">Date</span><span class="sxs-lookup"><span data-stu-id="04ccf-145">date</span></span>|[<span data-ttu-id="04ccf-146">date &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-146">date &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/date-transact-sql)|  
|<span data-ttu-id="04ccf-147">time</span><span class="sxs-lookup"><span data-stu-id="04ccf-147">time</span></span>|[<span data-ttu-id="04ccf-148">time &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-148">time &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/time-transact-sql)|  
|<span data-ttu-id="04ccf-149">DATETIME</span><span class="sxs-lookup"><span data-stu-id="04ccf-149">datetime</span></span>|[<span data-ttu-id="04ccf-150">datetime &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-150">datetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime-transact-sql)|  
|<span data-ttu-id="04ccf-151">datetime2</span><span class="sxs-lookup"><span data-stu-id="04ccf-151">datetime2</span></span>|[<span data-ttu-id="04ccf-152">datetime2 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-152">datetime2 &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime2-transact-sql)|  
|<span data-ttu-id="04ccf-153">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="04ccf-153">smalldatetime</span></span>|[<span data-ttu-id="04ccf-154">smalldatetime &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-154">smalldatetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/smalldatetime-transact-sql)|  
  
 <span data-ttu-id="04ccf-155">**Types de données binaires**</span><span class="sxs-lookup"><span data-stu-id="04ccf-155">**Binary Data Types**</span></span>  
  
|<span data-ttu-id="04ccf-156">Type de données</span><span class="sxs-lookup"><span data-stu-id="04ccf-156">Data type</span></span>|<span data-ttu-id="04ccf-157">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="04ccf-157">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="04ccf-158">bit</span><span class="sxs-lookup"><span data-stu-id="04ccf-158">bit</span></span>|[<span data-ttu-id="04ccf-159">bit &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-159">bit &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/bit-transact-sql)|  
|<span data-ttu-id="04ccf-160">binary(n)</span><span class="sxs-lookup"><span data-stu-id="04ccf-160">binary(n)</span></span>|[<span data-ttu-id="04ccf-161">binary et varbinary &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-161">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
|<span data-ttu-id="04ccf-162">varbinary (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="04ccf-162">varbinary(n) <sup>1</sup></span></span>|[<span data-ttu-id="04ccf-163">binary et varbinary &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-163">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
  
 <span data-ttu-id="04ccf-164"><sup>1</sup> la limite est de 8060 octets par ligne au total, en comptant (n) dans les types de longueur variable.</span><span class="sxs-lookup"><span data-stu-id="04ccf-164"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="04ccf-165">**Autres types de données**</span><span class="sxs-lookup"><span data-stu-id="04ccf-165">**Other data types**</span></span>  
  
|<span data-ttu-id="04ccf-166">Type de données</span><span class="sxs-lookup"><span data-stu-id="04ccf-166">Data type</span></span>|<span data-ttu-id="04ccf-167">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="04ccf-167">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="04ccf-168">UNIQUEIDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="04ccf-168">uniqueidentifier</span></span>|[<span data-ttu-id="04ccf-169">uniqueidentifier &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="04ccf-169">uniqueidentifier &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/uniqueidentifier-transact-sql)|  
  
 <span data-ttu-id="04ccf-170">**Types de données non pris en charge**</span><span class="sxs-lookup"><span data-stu-id="04ccf-170">**Unsupported Data Types**</span></span>  
  
 <span data-ttu-id="04ccf-171">Les types de données suivants ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="04ccf-171">The following data types are not supported:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="04ccf-172">DATETIMEOFFSET</span><span class="sxs-lookup"><span data-stu-id="04ccf-172">DATETIMEOFFSET</span></span>|<span data-ttu-id="04ccf-173">GEOGRAPHY</span><span class="sxs-lookup"><span data-stu-id="04ccf-173">GEOGRAPHY</span></span>|<span data-ttu-id="04ccf-174">GEOMETRY</span><span class="sxs-lookup"><span data-stu-id="04ccf-174">GEOMETRY</span></span>|  
|<span data-ttu-id="04ccf-175">HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="04ccf-175">HIERARCHYID</span></span>|<span data-ttu-id="04ccf-176">Objets de grande taille (LOB).</span><span class="sxs-lookup"><span data-stu-id="04ccf-176">Large Objects (LOBs).</span></span> <span data-ttu-id="04ccf-177">Par exemple, varchar(max), nvarchar(max), varbinary(max), image, xml, text et ntext.</span><span class="sxs-lookup"><span data-stu-id="04ccf-177">For example, varchar(max), nvarchar(max), varbinary(max), image, xml, text, and ntext.</span></span>|<span data-ttu-id="04ccf-178">ROWVERSION</span><span class="sxs-lookup"><span data-stu-id="04ccf-178">ROWVERSION</span></span>|  
|<span data-ttu-id="04ccf-179">sql_variant</span><span class="sxs-lookup"><span data-stu-id="04ccf-179">sql_variant</span></span>|<span data-ttu-id="04ccf-180">Fonctions CLR</span><span class="sxs-lookup"><span data-stu-id="04ccf-180">CLR functions</span></span>|<span data-ttu-id="04ccf-181">Types définis par l'utilisateur (UDT)</span><span class="sxs-lookup"><span data-stu-id="04ccf-181">User-defined types (UDTs)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04ccf-182">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="04ccf-182">See Also</span></span>  
 <span data-ttu-id="04ccf-183">[Prise en charge d'OLTP en mémoire par Transact-SQL](transact-sql-support-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="04ccf-183">[Transact-SQL Support for In-Memory OLTP](transact-sql-support-for-in-memory-oltp.md) </span></span>  
 <span data-ttu-id="04ccf-184">[Implémentation de colonnes LOB dans une table optimisée en mémoire](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span><span class="sxs-lookup"><span data-stu-id="04ccf-184">[Implementing LOB Columns in a Memory-Optimized Table](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span></span>  
 [<span data-ttu-id="04ccf-185">Implémentation de SQL_VARIANT dans un tableau mémoire optimisé</span><span class="sxs-lookup"><span data-stu-id="04ccf-185">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
  
