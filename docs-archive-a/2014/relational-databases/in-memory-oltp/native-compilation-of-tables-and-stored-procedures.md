---
title: Compilation en mode natif de tables et de procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5880fbd9-a23e-464a-8b44-09750eeb2dad
author: rothja
ms.author: jroth
ms.openlocfilehash: 32c5b04610d894e06278fbeecdaf3bbebe850d60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611074"
---
# <a name="native-compilation-of-tables-and-stored-procedures"></a><span data-ttu-id="dfc7f-102">Compilation en mode natif de tables et de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="dfc7f-102">Native Compilation of Tables and Stored Procedures</span></span>
  <span data-ttu-id="dfc7f-103">L'OLTP en mémoire introduit le concept de compilation native.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-103">In-Memory OLTP introduces the concept of native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dfc7f-104">peut compiler en mode natif des procédures stockées qui accèdent aux tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-104">can natively compile stored procedures that access memory-optimized tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dfc7f-105">peut également compiler en mode natif des tables optimisées en mémoire.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-105">is also able to natively compile memory-optimized tables.</span></span> <span data-ttu-id="dfc7f-106">La compilation native permet un accès aux données plus rapide et une exécution des requêtes plus efficace que le [!INCLUDE[tsql](../../includes/tsql-md.md)](traditionnel) interprété.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-106">Native compilation allows faster data access and more efficient query execution than interpreted (traditional) [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="dfc7f-107">La compilation en mode natif de tables et de procédures stockées produit des DLL.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-107">Native compilation of tables and stored procedures produce DLLs.</span></span>  
  
 <span data-ttu-id="dfc7f-108">La compilation en mode natif des types de table optimisée en mémoire est également prise en charge.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-108">Native compilation of memory optimized table types is also supported.</span></span> <span data-ttu-id="dfc7f-109">Pour plus d'informations, consultez [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span><span class="sxs-lookup"><span data-stu-id="dfc7f-109">For more information, see [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span></span>  
  
 <span data-ttu-id="dfc7f-110">La compilation native fait référence au processus de conversion des constructions de programmation en code natif, constitué d'instructions de processeur, sans recourir à une compilation ou une interprétation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-110">Native compilation refers to the process of converting programming constructs to native code, consisting of processor instructions without the need for further compilation or interpretation.</span></span>  
  
 <span data-ttu-id="dfc7f-111">L'OLTP en mémoire compile les tables optimisées en mémoire quand elles sont créées, ainsi que les procédures stockées compilées en mode natif au moment de leur chargement dans des DLL natives.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-111">In-Memory OLTP compiles memory-optimized tables when they are created, and natively compiled stored procedures when they are loaded to native DLLs.</span></span> <span data-ttu-id="dfc7f-112">En outre, les DLL sont recompilées au redémarrage de la base de données ou du serveur.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-112">In addition, the DLLs are recompiled after a database or server restart.</span></span> <span data-ttu-id="dfc7f-113">Les informations nécessaires pour recréer les DLL sont stockées dans les métadonnées de la base de données.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-113">The information necessary to recreate the DLLs is stored in the database metadata.</span></span> <span data-ttu-id="dfc7f-114">Les DLL ne font pas partie de la base de données, bien qu'elles lui soient associées.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-114">The DLLs are not part of the database, though they are associated with the database.</span></span> <span data-ttu-id="dfc7f-115">Par exemple, les DLL ne sont pas incluses dans les sauvegardes de base de données.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-115">For example, the DLLs are not included in database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfc7f-116">Les tables optimisées en mémoire sont recompilées lors d'un redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-116">Memory-optimized tables are recompiled during a server restart.</span></span> <span data-ttu-id="dfc7f-117">Pour accélérer la récupération de la base de données, les procédures stockées compilées en mode natif ne sont pas recompilées lors d'un redémarrage du serveur. Elles sont compilées au moment de la première exécution.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-117">To speed up database recovery, natively compiled stored procedures are not recompiled during a server restart, they are compiled at the time of first execution.</span></span> <span data-ttu-id="dfc7f-118">En conséquence de cette compilation différée, les procédures stockées compilées en mode natif n’apparaissent que lors de l’appel de [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) après la première exécution.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-118">As a result of this deferred compilation, natively compiled stored procedures only appear when calling [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) after first execution.</span></span>  
  
## <a name="maintenance-of-in-memory-oltp-dlls"></a><span data-ttu-id="dfc7f-119">Maintenance des DLL de l'OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="dfc7f-119">Maintenance of In-Memory OLTP DLLs</span></span>  
 <span data-ttu-id="dfc7f-120">La requête suivante affiche toutes les DLL de tables et de procédures stockées ayant été chargées en mémoire sur le serveur :</span><span class="sxs-lookup"><span data-stu-id="dfc7f-120">The following query shows all table and stored procedure DLLs currently loaded in memory on the server:</span></span>  
  
```sql  
SELECT name, description FROM sys.dm_os_loaded_modules  
where description = 'XTP Native DLL'  
```  
  
 <span data-ttu-id="dfc7f-121">Les administrateurs de base de données n'ont pas besoin de conserver les fichiers générés par la compilation native.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-121">Database administrators do not need to maintain files that are generated by a native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dfc7f-122">supprime automatiquement les fichiers générés qui ne sont plus nécessaires.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-122">automatically removes generated files that are no longer needed.</span></span> <span data-ttu-id="dfc7f-123">Par exemple, les fichiers générés sont supprimés lorsque vous supprimez une table et une procédure stockée, ou si vous supprimez une base de données.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-123">For example, generated files will be deleted when a table and stored procedure is deleted, or if a database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfc7f-124">Si la compilation échoue ou est interrompue, certains fichiers générés ne sont pas supprimés.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-124">If compilation fails or is interrupted, some generated files are not removed.</span></span> <span data-ttu-id="dfc7f-125">Ces fichiers sont intentionnellement conservés pour la prise en charge et sont supprimés lorsque la base de données est supprimée.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-125">These files are intentionally left behind for supportability and are removed when the database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dfc7f-126">Lors du démarrage de la base de données, SQL Server compile les DLL de toutes les tables nécessaires à la récupération de la base de données.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-126">During database startup, SQL Server compiles DLLs for all tables needed for database recovery.</span></span> <span data-ttu-id="dfc7f-127">Si une table a été supprimée juste avant un redémarrage de la base de données, il peut y avoir des restes de la table dans les fichiers de point de contrôle ou dans le journal des transactions : la DLL de la table doit alors être recompilée lors du démarrage de la base de données.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-127">If a table was dropped just prior to a database restart there can still be remnants of the table in the checkpoint files or the transaction log so the DLL for the table might be recompiled during database startup.</span></span> <span data-ttu-id="dfc7f-128">Après le redémarrage, la DLL est déchargée et les fichiers supprimés par le processus de nettoyage normal.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-128">After restart the DLL will be unloaded and the files will be removed by the normal cleanup process.</span></span>  
  
## <a name="native-compilation-of-tables"></a><span data-ttu-id="dfc7f-129">Compilation native des tables</span><span class="sxs-lookup"><span data-stu-id="dfc7f-129">Native Compilation of Tables</span></span>  
 <span data-ttu-id="dfc7f-130">La création d'une table optimisée en mémoire à l'aide de l'instruction `CREATE TABLE` entraîne l'écriture des informations de la table dans les métadonnées de la base de données et la création des structures de table et d'index en mémoire.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-130">Creating a memory-optimized table using the `CREATE TABLE` statement results in the table information being written to the database metadata and the table and index structures created in memory.</span></span> <span data-ttu-id="dfc7f-131">La table sera également compilée dans une DLL.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-131">The table will also be compiled to a DLL.</span></span>  
  
 <span data-ttu-id="dfc7f-132">Consultez l'exemple de script suivant, qui crée une base de données et une table optimisée en mémoire :</span><span class="sxs-lookup"><span data-stu-id="dfc7f-132">Consider the following sample script, which creates a database and a memory-optimized table:</span></span>  
  
```sql  
use master  
go  
create database db1  
go  
alter database db1 add filegroup db1_mod contains memory_optimized_data  
go  
-- adapt filename as needed  
alter database db1 add file (name='db1_mod', filename='c:\data\db1_mod') to filegroup db1_mod  
go  
use db1  
go  
create table dbo.t1  
   (c1 int not null primary key nonclustered,  
    c2 INT)  
with (memory_optimized=on)  
go  
-- retrieve the path of the DLL for table t1  
select name, description FROM sys.dm_os_loaded_modules  
where name like '%xtp_t_' + cast(db_id() as varchar(10)) + '_' + cast(object_id('dbo.t1') as varchar(10)) + '.dll'  
go  
```  
  
 <span data-ttu-id="dfc7f-133">La création de la table crée également la DLL de table et charge la DLL dans la mémoire.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-133">Creating the table also creates the table DLL and loads the DLL in memory.</span></span> <span data-ttu-id="dfc7f-134">Une requête DMV exécutée immédiatement après l'instruction CREATE TABLE récupère le chemin d'accès de la DLL de table.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-134">The DMV query immediately after the CREATE TABLE statement retrieves the path of the table DLL.</span></span>  
  
 <span data-ttu-id="dfc7f-135">La DLL de table comprend les structures d'index et le format de ligne de la table.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-135">The table DLL understands the index structures and row format of the table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dfc7f-136">utilise la DLL pour parcourir les index, extraire des lignes et enregistrer le contenu des lignes.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-136">uses the DLL for traversing indexes, retrieving rows, as well as storing the contents of the rows.</span></span>  
  
## <a name="native-compilation-of-stored-procedures"></a><span data-ttu-id="dfc7f-137">Procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="dfc7f-137">Native Compilation of Stored Procedures</span></span>  
 <span data-ttu-id="dfc7f-138">Les procédures stockées qui sont identifiées par NATIVE_COMPILATION sont compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-138">Stored procedures that are marked with NATIVE_COMPILATION are natively compiled.</span></span> <span data-ttu-id="dfc7f-139">Cela signifie que toutes les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] de la procédure sont compilées en code natif en vue d'accélérer l'exécution de la logique métier critique pour les performances.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-139">This means the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure are all compiled to native code for efficient execution of performance-critical business logic.</span></span>  
  
 <span data-ttu-id="dfc7f-140">Pour plus d'informations sur les procédures stockées compilées en mode natif, consultez [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="dfc7f-140">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="dfc7f-141">Prenons l'exemple de procédure stockée suivant, qui insère des lignes dans la table t1 de l'exemple précédent :</span><span class="sxs-lookup"><span data-stu-id="dfc7f-141">Consider the following sample stored procedure, which inserts rows in the table t1 from the previous example:</span></span>  
  
```sql  
create procedure dbo.native_sp  
with native_compilation, schemabinding, execute as owner  
as  
begin atomic  
with (transaction isolation level=snapshot, language=N'us_english')  
  
  declare @i int = 1000000  
  while @i > 0  
  begin  
    insert dbo.t1 values (@i, @i+1)  
    set @i -= 1  
  end  
  
end  
go  
exec dbo.native_sp  
go  
-- reset  
delete from dbo.t1  
go  
```  
  
 <span data-ttu-id="dfc7f-142">La DLL de native_sp peut interagir directement avec la DLL de t1, ainsi que le moteur de stockage de l'OLTP en mémoire, pour insérer les lignes le plus rapidement possible.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-142">The DLL for native_sp can interact directly with the DLL for t1, as well as the In-Memory OLTP storage engine, to insert the rows as fast as possible.</span></span>  
  
 <span data-ttu-id="dfc7f-143">Le compilateur de l'OLTP en mémoire tire parti de l'optimiseur de requête pour créer un plan d'exécution efficace pour chacune des requêtes dans la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-143">The In-Memory OLTP compiler leverages the query optimizer to create an efficient execution plan for each of the queries in the stored procedure.</span></span> <span data-ttu-id="dfc7f-144">Notez que les procédures stockées compilées en mode natif ne sont pas automatiquement recompilées si les données de la table sont modifiées.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-144">Note that natively compiled stored procedures are not automatically recompiled if the data in the table changes.</span></span> <span data-ttu-id="dfc7f-145">Pour plus d’informations sur la gestion des statistiques et des procédures stockées avec l’OLTP en mémoire, consultez [Statistiques pour les tables mémoire optimisées](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="dfc7f-145">For more information on maintaining statistics and stored procedures with In-Memory OLTP see [Statistics for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="security-considerations-for-native-compilation"></a><span data-ttu-id="dfc7f-146">Considérations sur la sécurité à prendre en compte pour une compilation native</span><span class="sxs-lookup"><span data-stu-id="dfc7f-146">Security Considerations for Native Compilation</span></span>  
 <span data-ttu-id="dfc7f-147">La compilation native des tables et des procédures stockées utilise le compilateur de l'OLTP en mémoire.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-147">Native compilation of tables and stored procedures uses the In-Memory OLTP compiler.</span></span> <span data-ttu-id="dfc7f-148">Ce compilateur génère des fichiers qui sont écrits sur le disque et chargés en mémoire.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-148">This compiler produces files that are written to disk and loaded into memory.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dfc7f-149">utilise les mécanismes suivants pour restreindre l'accès à ces fichiers.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-149">uses the following mechanisms to limit access to these files.</span></span>  
  
### <a name="native-compiler"></a><span data-ttu-id="dfc7f-150">Compilateur natif</span><span class="sxs-lookup"><span data-stu-id="dfc7f-150">Native Compiler</span></span>  
 <span data-ttu-id="dfc7f-151">Le fichier exécutable du compilateur, ainsi que les fichiers binaires et les fichiers d'en-tête nécessaires pour la compilation native, sont installés dans le cadre de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans le dossier MSSQL\Binn\Xtp.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-151">The compiler executable, as well as binaries and header files required for native compilation are installed as part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance under the folder MSSQL\Binn\Xtp.</span></span> <span data-ttu-id="dfc7f-152">Par conséquent, si l’instance par défaut est installée sous c:\Program Files, les fichiers du compilateur sont installés dans c:\Program Files \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \MSSQL12. MSSQLSERVER\MSSQL\Binn\Xtp.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-152">So, if the default instance is installed under C:\Program Files, the compiler files are installed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\Binn\Xtp.</span></span>  
  
 <span data-ttu-id="dfc7f-153">Pour limiter l'accès au compilateur, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise des listes de contrôle d'accès (ACL) qui permettent de restreindre l'accès aux fichiers binaires.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-153">To limit access to the compiler, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses access control lists (ACLs) to restrict access to binary files.</span></span> <span data-ttu-id="dfc7f-154">Tous les fichiers binaires [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont protégés contre la modification ou la falsification via des listes de contrôle d'accès.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-154">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries are protected against modification or tampering through ACLs.</span></span> <span data-ttu-id="dfc7f-155">Les listes de contrôle d'accès du compilateur natif limitent également l'utilisation du compilateur ; seuls le compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les administrateurs système disposent des autorisations de lecture et d'exécution des fichiers du compilateur natif.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-155">The native compiler's ACLs also limit use of the compiler; only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators have read and execute permissions for native compiler files.</span></span>  
  
### <a name="files-generated-by-a-native-compilation"></a><span data-ttu-id="dfc7f-156">Fichiers générés par une compilation native</span><span class="sxs-lookup"><span data-stu-id="dfc7f-156">Files Generated by a Native Compilation</span></span>  
 <span data-ttu-id="dfc7f-157">Les fichiers créés lorsqu'une table ou une procédure stockée est compilée sont les fichiers DLL et les fichiers intermédiaires, notamment les fichiers portant les extensions suivantes : .c, .obj, .xml et .pdb.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-157">The files produced when a table or stored procedure is compiled include the DLL and intermediate files including files with the following extensions: .c, .obj, .xml, and .pdb.</span></span> <span data-ttu-id="dfc7f-158">Les fichiers générés sont enregistrés dans un sous-dossier du dossier de données par défaut.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-158">The generated files are saved in a subfolder of the default data folder.</span></span> <span data-ttu-id="dfc7f-159">Le sous-dossier est appelé Xtp.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-159">The subfolder is called Xtp.</span></span> <span data-ttu-id="dfc7f-160">Lors de l’installation de l’instance par défaut avec le dossier de données par défaut, les fichiers générés sont placés dans C:\Program Files \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \MSSQL12. MSSQLSERVER\MSSQL\DATA\Xtp.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-160">When installing the default instance with the default data folder, the generated files are placed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\DATA\Xtp.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dfc7f-161">empêche la falsification avec les DLL générées de trois manières :</span><span class="sxs-lookup"><span data-stu-id="dfc7f-161">prevents tampering with the generated DLLs in three ways:</span></span>  
  
-   <span data-ttu-id="dfc7f-162">Lorsqu'une table ou une procédure stockée est compilée dans une DLL, cette DLL est immédiatement chargée en mémoire et liée au processus sqlserver.exe.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-162">When a table or stored procedure is compiled to a DLL, this DLL is immediately loaded into memory and linked to the sqlserver.exe process.</span></span> <span data-ttu-id="dfc7f-163">Un fichier DLL ne peut pas être modifié lorsqu'il est lié à un processus.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-163">A DLL cannot be modified while it is linked to a process.</span></span>  
  
-   <span data-ttu-id="dfc7f-164">Lorsqu'une base de données redémarre, toutes les tables et les procédures stockées sont recompilées (supprimées et recréés) en fonction des métadonnées de la base de données.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-164">When a database is restarted, all tables and stored procedures are recompiled (removed and recreated) based on the database metadata.</span></span> <span data-ttu-id="dfc7f-165">Ceci entraîne la suppression des éventuelles modifications apportées à un fichier généré par un agent malveillant.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-165">This will remove any changes made to a generated file by a malicious agent.</span></span>  
  
-   <span data-ttu-id="dfc7f-166">Les fichiers générés sont considérés comme faisant partie des données utilisateur, et ont les mêmes restrictions de sécurité, via les listes de contrôle d'accès, que les fichiers de base de données : seuls le compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les administrateurs système ont accès à ces fichiers.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-166">The generated files are considered part of user data, and have the same security restrictions, via ACLs, as database files: only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators can access these files.</span></span>  
  
 <span data-ttu-id="dfc7f-167">Aucune intervention de l'utilisateur n'est nécessaire pour gérer ces fichiers.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-167">No user interaction is needed to manage these files.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dfc7f-168">crée et supprime les fichiers, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="dfc7f-168">will create and remove the files as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc7f-169">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dfc7f-169">See Also</span></span>  
 <span data-ttu-id="dfc7f-170">[Tables optimisées en mémoire](memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="dfc7f-170">[Memory-Optimized Tables](memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="dfc7f-171">Procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="dfc7f-171">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
