---
title: MSSQLSERVER_605 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 605 (Database Engine error)
ms.assetid: d8d3a22e-1ff8-48a4-891f-4c8619437e24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e196fba84af492b25e798629d3e808b1bf22857e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612837"
---
# <a name="mssqlserver_605"></a><span data-ttu-id="dbf06-102">MSSQLSERVER_605</span><span class="sxs-lookup"><span data-stu-id="dbf06-102">MSSQLSERVER_605</span></span>
    
## <a name="details"></a><span data-ttu-id="dbf06-103">Détails</span><span class="sxs-lookup"><span data-stu-id="dbf06-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dbf06-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="dbf06-104">Product Name</span></span>|<span data-ttu-id="dbf06-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dbf06-105">SQL Server</span></span>|  
|<span data-ttu-id="dbf06-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="dbf06-106">Event ID</span></span>|<span data-ttu-id="dbf06-107">605</span><span class="sxs-lookup"><span data-stu-id="dbf06-107">605</span></span>|  
|<span data-ttu-id="dbf06-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="dbf06-108">Event Source</span></span>|<span data-ttu-id="dbf06-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dbf06-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dbf06-110">Composant</span><span class="sxs-lookup"><span data-stu-id="dbf06-110">Component</span></span>|<span data-ttu-id="dbf06-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dbf06-111">SQLEngine</span></span>|  
|<span data-ttu-id="dbf06-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="dbf06-112">Symbolic Name</span></span>|<span data-ttu-id="dbf06-113">WRONGPAGE</span><span class="sxs-lookup"><span data-stu-id="dbf06-113">WRONGPAGE</span></span>|  
|<span data-ttu-id="dbf06-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="dbf06-114">Message Text</span></span>|<span data-ttu-id="dbf06-115">La tentative d'extraction de la page logique %S_PGID dans la base de données %d a échoué.</span><span class="sxs-lookup"><span data-stu-id="dbf06-115">Attempt to fetch logical page %S_PGID in database %d failed.</span></span> <span data-ttu-id="dbf06-116">Elle appartient à l'unité d'allocation %I64d et non à %I64d.</span><span class="sxs-lookup"><span data-stu-id="dbf06-116">It belongs to allocation unit %I64d not to %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dbf06-117">Explication</span><span class="sxs-lookup"><span data-stu-id="dbf06-117">Explanation</span></span>  
 <span data-ttu-id="dbf06-118">Cette erreur est généralement synonyme d'altération de page ou d'allocation dans la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="dbf06-118">This error generally signifies page or allocation corruption in the specified database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dbf06-119">détecte l’altération en suivant les liens des pages ou en utilisant la page IAM (Index Allocation Map) au cours de la lecture de pages appartenant à une table.</span><span class="sxs-lookup"><span data-stu-id="dbf06-119">detects corruption when reading pages belonging to a table either by following the page linkages or by using the Index Allocation Map (IAM).</span></span> <span data-ttu-id="dbf06-120">Toutes les pages allouées à une table doivent appartenir à l'une des unités d'allocations associées à la table.</span><span class="sxs-lookup"><span data-stu-id="dbf06-120">All pages allocated to a table must belong to one of the allocation units associated with the table.</span></span> <span data-ttu-id="dbf06-121">Si l'ID d'unité d'allocation contenu dans l'en-tête de page ne correspond pas à un ID d'unité d'allocation associé à la table, cette exception est générée.</span><span class="sxs-lookup"><span data-stu-id="dbf06-121">If the allocation unit ID contained in the page header does not match an allocation unit ID associated with the table, this exception is raised.</span></span> <span data-ttu-id="dbf06-122">Le premier ID d'unité d'allocation listé dans le message d'erreur est l'ID présent dans l'en-tête de page et le second est l'ID associé à la table.</span><span class="sxs-lookup"><span data-stu-id="dbf06-122">The first allocation unit ID listed in the error message is the ID present in the page header, and the second allocation unit value is the ID associated with the table.</span></span>  
  
 <span data-ttu-id="dbf06-123">**Erreurs d’altération des données**</span><span class="sxs-lookup"><span data-stu-id="dbf06-123">**Data Corruption Errors**</span></span>  
  
 <span data-ttu-id="dbf06-124">Un niveau de gravité de 21 indique une potentielle altération des données.</span><span class="sxs-lookup"><span data-stu-id="dbf06-124">A severity level of 21 indicates potential data corruption.</span></span> <span data-ttu-id="dbf06-125">Les causes possibles sont les suivantes : chaîne de page endommagée, page IAM altérée ou entrée non valide dans la vue de catalogue [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) pour l’objet concerné.</span><span class="sxs-lookup"><span data-stu-id="dbf06-125">Possible causes are a damaged page chain, a corrupt IAM, or an invalid entry in the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view for that object.</span></span> <span data-ttu-id="dbf06-126">Ces erreurs sont souvent causées par une défaillance du matériel ou du pilote de disque.</span><span class="sxs-lookup"><span data-stu-id="dbf06-126">These errors are often caused by hardware or disk device driver failure.</span></span>  
  
 <span data-ttu-id="dbf06-127">**Erreurs temporaires**</span><span class="sxs-lookup"><span data-stu-id="dbf06-127">**Transient Errors**</span></span>  
  
 <span data-ttu-id="dbf06-128">Un niveau de gravité de 12 indique une potentielle erreur temporaire, c'est-à-dire qu'elle se produit dans le cache mais n'indique aucune altération des données sur le disque.</span><span class="sxs-lookup"><span data-stu-id="dbf06-128">A severity level of 12 indicates a potential transient error; that is, it occurs in the cache and does not indicate damage to data on disk.</span></span> <span data-ttu-id="dbf06-129">Les erreurs 605 temporaires peuvent être causées par les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="dbf06-129">Transient 605 errors can be caused by the following conditions:</span></span>  
  
-   <span data-ttu-id="dbf06-130">Le système d'exploitation informe prématurément [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qu'une opération d'E/S vient de se terminer. Le message d'erreur est affiché même si aucune altération des données n'a lieu.</span><span class="sxs-lookup"><span data-stu-id="dbf06-130">The operating system prematurely notifies [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that an I/O operation has completed; the error message is displayed even though no actual data corruption exists.</span></span>  
  
 <span data-ttu-id="dbf06-131">Une requête est exécutée avec l'indicateur d'optimiseur NOLOCK ou le niveau d'isolement des transactions est défini avec la valeur READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="dbf06-131">Running a query with the Optimizer hint NOLOCK or setting the transaction isolation level to READ UNCOMMITTED.</span></span> <span data-ttu-id="dbf06-132">Lorsqu'une requête utilisant NOLOCK ou READ UNCOMMITTED tente de lire des données qui ont été déplacées ou modifiées par un autre utilisateur, une erreur 605 se produit.</span><span class="sxs-lookup"><span data-stu-id="dbf06-132">When a query that is using NOLOCK or READ UNCOMMITTED tries to read data that is being moved or changed by another user, a 605 error occurs.</span></span> <span data-ttu-id="dbf06-133">Pour vérifier qu'il s'agit bien d'une erreur 605 temporaire, réexécutez la requête ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="dbf06-133">To verify that it is a transient 605 error, rerun the query later.</span></span> <span data-ttu-id="dbf06-134">Pour plus d’informations, consultez l’article [235880](https://support.microsoft.com/kb/235880/en-us) de la Base de connaissances : « Vous recevez un message d’erreur « Erreur 605 » lorsque vous exécutez une requête avec l’indicateur d’optimiseur NOLOCK ou vous le niveau d’isolement de transaction définissez à READ UNCOMMITTED dans SQL Server ».</span><span class="sxs-lookup"><span data-stu-id="dbf06-134">For more information, see this KB article [235880](https://support.microsoft.com/kb/235880/en-us): "You receive an "Error 605" error message when you run a query with the optimizer hint NOLOCK or you set the transaction isolation level to READ UNCOMMITTED in SQL Server."</span></span>  
  
 <span data-ttu-id="dbf06-135">Généralement, si l'erreur se produit lors de l'accès aux données, mais que les opérations DBCC CHECKDB qui suivent s'exécutent sans erreur, l'erreur 605 était probablement temporaire.</span><span class="sxs-lookup"><span data-stu-id="dbf06-135">In general, if the error occurs during data access but subsequent DBCC CHECKDB operations complete without error, the 605 error was probably transient.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dbf06-136">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="dbf06-136">User Action</span></span>  
 <span data-ttu-id="dbf06-137">Si l'erreur 605 n'est pas temporaire, le problème est grave et doit être résolu en effectuant les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dbf06-137">If the 605 error is not transient, the problem is severe and must be corrected by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="dbf06-138">Identifiez les tables associées aux unités d'allocation spécifiées dans le message en exécutant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="dbf06-138">Identify the tables associated with the allocation units specified in the message by running the following query.</span></span> <span data-ttu-id="dbf06-139">Remplacez `allocation_unit_id` par les unités d'allocation spécifiées dans le message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="dbf06-139">Replace `allocation_unit_id` with the allocation units specified in the error message.</span></span>  
  
     <span data-ttu-id="dbf06-140">USE`database_name`;</span><span class="sxs-lookup"><span data-stu-id="dbf06-140">USE`database_name`;</span></span>  
  
     <span data-ttu-id="dbf06-141">GO</span><span class="sxs-lookup"><span data-stu-id="dbf06-141">GO</span></span>  
  
     <span data-ttu-id="dbf06-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span><span class="sxs-lookup"><span data-stu-id="dbf06-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span></span>  
  
     <span data-ttu-id="dbf06-143">au.type_desc allocation_type AS, au.data_pages, partition_number</span><span class="sxs-lookup"><span data-stu-id="dbf06-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span></span>  
  
     <span data-ttu-id="dbf06-144">FROM sys.allocation_units AS au</span><span class="sxs-lookup"><span data-stu-id="dbf06-144">FROM sys.allocation_units AS au</span></span>  
  
     <span data-ttu-id="dbf06-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span><span class="sxs-lookup"><span data-stu-id="dbf06-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span></span>  
  
     <span data-ttu-id="dbf06-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span><span class="sxs-lookup"><span data-stu-id="dbf06-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span></span>  
  
     <span data-ttu-id="dbf06-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span><span class="sxs-lookup"><span data-stu-id="dbf06-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span></span>  
  
     <span data-ttu-id="dbf06-148">ORDER BY au.allocation_unit_id;</span><span class="sxs-lookup"><span data-stu-id="dbf06-148">ORDER BY au.allocation_unit_id;</span></span>  
  
     <span data-ttu-id="dbf06-149">GO</span><span class="sxs-lookup"><span data-stu-id="dbf06-149">GO</span></span>  
  
2.  <span data-ttu-id="dbf06-150">Exécutez DBCC CHECKTABLE sans clause REPAIR sur la table associée au deuxième ID d'unité d'allocation spécifié dans le message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="dbf06-150">Execute DBCC CHECKTABLE without a REPAIR clause on the table associated with the second allocation unit ID specified in the error message.</span></span>  
  
3.  <span data-ttu-id="dbf06-151">Exécutez DBCC CHECKDB sans clause REPAIR dès que possible pour déterminer le niveau d'altération des données dans l'ensemble de la base de données.</span><span class="sxs-lookup"><span data-stu-id="dbf06-151">Execute DBCC CHECKDB without a REPAIR clause as soon as possible to determine the full extent of the corruption in the entire database.</span></span>  
  
4.  <span data-ttu-id="dbf06-152">Dans le journal des erreurs, recherchez d'autres erreurs qui accompagnent souvent une erreur 605 et examinez le journal des événements Windows pour détecter d'éventuels problèmes système ou matériels associés.</span><span class="sxs-lookup"><span data-stu-id="dbf06-152">Check the error log for other errors that often accompany a 605 error and examine the Windows Event Log for any system or hardware related issues.</span></span> <span data-ttu-id="dbf06-153">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="dbf06-153">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="dbf06-154">Si le problème n'est pas matériel, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="dbf06-154">If the problem is not hardware related, perform one of the following tasks:</span></span>  
  
1.  <span data-ttu-id="dbf06-155">Restaurez la base de données à partir d'une sauvegarde saine.</span><span class="sxs-lookup"><span data-stu-id="dbf06-155">Restore the database from a known clean backup.</span></span> <span data-ttu-id="dbf06-156">Vous pouvez optimiser la fonctionnalité de sauvegarde de la restauration de pages pour restaurer uniquement les pages endommagées.</span><span class="sxs-lookup"><span data-stu-id="dbf06-156">You can leverage the page restore backup feature to restore just the damaged pages.</span></span>  
  
2.  <span data-ttu-id="dbf06-157">Exécutez DBCC CHECKDB avec la clause REPAIR recommandée par l'opération DBCC CHECKDB effectuée à l'étape 3 pour réparer l'endommagement.</span><span class="sxs-lookup"><span data-stu-id="dbf06-157">Run DBCC CHECKDB with the REPAIR clause recommended by the DBCC CHECKDB operation performed in step 3 to repair the corruption.</span></span> <span data-ttu-id="dbf06-158">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="dbf06-158">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span> <span data-ttu-id="dbf06-159">Gardez le résultat de DBCC CHECKDB à disposition pour consultation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="dbf06-159">Have the output from DBCC CHECKDB available for review.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="dbf06-160">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="dbf06-160">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf06-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbf06-161">See Also</span></span>  
 [<span data-ttu-id="dbf06-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dbf06-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql)  
  
  
