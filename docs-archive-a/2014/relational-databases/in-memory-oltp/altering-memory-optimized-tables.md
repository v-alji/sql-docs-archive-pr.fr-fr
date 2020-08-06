---
title: Modification des tables à mémoire optimisée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 690b70b7-5be1-4014-af97-54e531997839
author: rothja
ms.author: jroth
ms.openlocfilehash: 4eedc6fdb45efc6c87765cd2208ead90c1887c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613461"
---
# <a name="altering-memory-optimized-tables"></a><span data-ttu-id="add40-102">Modification des tables à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="add40-102">Altering Memory-Optimized Tables</span></span>
  <span data-ttu-id="add40-103">L'exécution d'opérations ALTER sur les tables mémoire optimisées n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="add40-103">Performing ALTER operations on memory-optimized tables is not supported.</span></span> <span data-ttu-id="add40-104">Cela comprend les opérations telles que la modification du nombre de compartiments, l'ajout ou la suppression d'un index et l'ajout ou la suppression d'une colonne.</span><span class="sxs-lookup"><span data-stu-id="add40-104">This includes such operations as changing the bucket_count, adding or removing an index, and adding or removing a column.</span></span> <span data-ttu-id="add40-105">Cette rubrique fournit des instructions pour mettre à jour des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="add40-105">This topic provides guidelines on how to update memory-optimized tables.</span></span>  
  
## <a name="updating-the-definition-of-a-memory-optimized-table"></a><span data-ttu-id="add40-106">Mise à jour de la définition d'une table mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="add40-106">Updating the Definition of a Memory-Optimized Table</span></span>  
 <span data-ttu-id="add40-107">Pour mettre à jour la définition d'une table mémoire optimisée, vous devez créer une nouvelle table avec la définition de la table mise à jour, copiez les données dans la nouvelle table et commencer à utiliser la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="add40-107">Updating the definition of a memory-optimized table requires you to create a new table with the updated table definition, copy the data to the new table, and start using the new table.</span></span> <span data-ttu-id="add40-108">Sauf si la table est en lecture seule, vous devez arrêter la charge de travail sur la table, afin de garantir qu'aucune modification n'est apportée à la table pendant la copie des données.</span><span class="sxs-lookup"><span data-stu-id="add40-108">Unless the table is read-only, this requires stopping the workload on the table, to ensure no changes are made to the table while the data copy is performed.</span></span>  
  
 <span data-ttu-id="add40-109">La procédure suivante présente les étapes nécessaires pour mettre à jour une table.</span><span class="sxs-lookup"><span data-stu-id="add40-109">The following procedure outlines the steps required to update a table.</span></span> <span data-ttu-id="add40-110">Dans cet exemple, la mise à jour ajoute un index.</span><span class="sxs-lookup"><span data-stu-id="add40-110">In this example, the update adds an index.</span></span> <span data-ttu-id="add40-111">Cette procédure conserve le nom de la table et nécessite deux opérations de copie de données : une dans une table temporaire et une dans la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="add40-111">This procedure preserves the name of the table and requires two data copy operations: once to a temporary table, and once to the new table.</span></span> <span data-ttu-id="add40-112">La modification du nombre de compartiments (bucket_count) d'un index ou l'ajout ou la suppression d'une colonne s'effectuent de la même façon.</span><span class="sxs-lookup"><span data-stu-id="add40-112">Changing the bucket_count of an index or adding or removing a column is performed the same way.</span></span>  
  
1.  <span data-ttu-id="add40-113">Arrêtez la charge de travail sur la table.</span><span class="sxs-lookup"><span data-stu-id="add40-113">Stop the workload on the table.</span></span>  
  
2.  <span data-ttu-id="add40-114">Générez un script pour la table et ajoutez le nouvel index au script.</span><span class="sxs-lookup"><span data-stu-id="add40-114">Generate script for the table and add the new index to the script.</span></span>  
  
3.  <span data-ttu-id="add40-115">Générez un script pour les objets liés au schéma (principalement des procédures stockées compilées en mode natif) référençant la table T et leurs autorisations.</span><span class="sxs-lookup"><span data-stu-id="add40-115">Generate script for the schema-bound objects (mainly natively compiled stored procedures) referencing T and their permissions.</span></span>  
  
     <span data-ttu-id="add40-116">Vous trouverez les objets liés au schéma référençant la table à l'aide de la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="add40-116">The schema-bound objects referencing the table can be found using the following query:</span></span>  
  
    ```sql  
    declare @t nvarchar(255) = N'<table name>'  
  
    select r.referencing_schema_name, r.referencing_entity_name  
    from sys.dm_sql_referencing_entities (@t, 'OBJECT') as r join sys.sql_modules m on r.referencing_id=m.object_id  
    where r.is_caller_dependent = 0 and m.is_schema_bound=1;  
    ```  
  
     <span data-ttu-id="add40-117">Les autorisations d'une procédure stockée peuvent faire l'objet d'un script à l'aide du code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant :</span><span class="sxs-lookup"><span data-stu-id="add40-117">The permissions of a stored procedure can be scripted using the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
    ```sql  
    declare @sp nvarchar(255) = N'<procedure name>'  
    declare @permissions nvarchar(max) = N''  
  
    select @permissions += dp.state_desc + N' ' + dp.permission_name + N' ON ' +   
       quotename(schema_name(o.schema_id)) + N'.' + quotename(o.name) + N' TO ' +  
       quotename(u.name) + N'; ' + char(13)  
    from sys.database_permissions as dp  
  
    join sys.database_principals as u  
       on u.principal_id = dp.grantee_principal_id  
  
    join sys.objects as o  
       on o.object_id = dp.major_id  
    where dp.class = 1 /* object */  
       and dp.minor_id = 0 and o.object_id=object_id(@sp);  
  
    select @permissions  
    ```  
  
4.  <span data-ttu-id="add40-118">Créez une copie de la table et copiez les données de la table d'origine dans la copie de la table.</span><span class="sxs-lookup"><span data-stu-id="add40-118">Create a copy of the table and copy the data from the original table to the copy of the table.</span></span> <span data-ttu-id="add40-119">La copie peut être créée à l’aide du [!INCLUDE[tsql](../../includes/tsql-md.md)] <sup>1</sup>suivant.</span><span class="sxs-lookup"><span data-stu-id="add40-119">The copy can be created using the following [!INCLUDE[tsql](../../includes/tsql-md.md)]<sup>1</sup>.</span></span>  
  
    ```sql  
    select * into dbo.T_copy from dbo.T  
    ```  
  
     <span data-ttu-id="add40-120">Si la mémoire disponible est suffisante, `T_copy` peut être une table optimisée en mémoire, ce qui accélère la copie des données.<sup> 2</sup></span><span class="sxs-lookup"><span data-stu-id="add40-120">If there is enough available memory, `T_copy` could be a memory-optimized table, which makes the data copy faster.<sup>2</sup></span></span>  
  
5.  <span data-ttu-id="add40-121">Supprimez les objets liés au schéma référençant la table d'origine.</span><span class="sxs-lookup"><span data-stu-id="add40-121">Drop the schema-bound objects referencing the original table.</span></span>  
  
6.  <span data-ttu-id="add40-122">Supprimez la table d'origine.</span><span class="sxs-lookup"><span data-stu-id="add40-122">Drop the original table.</span></span>  
  
7.  <span data-ttu-id="add40-123">Créez la nouvelle table (`T`) avec le script qui contient le nouvel index.</span><span class="sxs-lookup"><span data-stu-id="add40-123">Create the new table (`T`) with the script containing the new index.</span></span>  
  
8.  <span data-ttu-id="add40-124">Copiez les données de `T_copy` dans `T`.</span><span class="sxs-lookup"><span data-stu-id="add40-124">Copy the data from `T_copy` to `T`.</span></span>  
  
9. <span data-ttu-id="add40-125">Recréez les objets de référencement liés au schéma et appliquez les autorisations.</span><span class="sxs-lookup"><span data-stu-id="add40-125">Recreate the referencing schema-bound objects and apply the permissions.</span></span>  
  
10. <span data-ttu-id="add40-126">Démarrez la charge de travail sur `T`.</span><span class="sxs-lookup"><span data-stu-id="add40-126">Start the workload on `T`.</span></span>  
  
 <span data-ttu-id="add40-127"><sup>1</sup> Notez que `T_copy` est conservé sur le disque dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="add40-127"><sup>1</sup> Note that `T_copy` is persisted to disk in this example.</span></span> <span data-ttu-id="add40-128">Si une sauvegarde de `T` est disponible, `T_copy` peut être une table temporaire ou non durable.</span><span class="sxs-lookup"><span data-stu-id="add40-128">If a backup of `T` is available, `T_copy` could be a temporary or a non-durable table.</span></span>  
  
 <span data-ttu-id="add40-129"><sup>2</sup> il doit y avoir suffisamment de mémoire pour `T_copy` .</span><span class="sxs-lookup"><span data-stu-id="add40-129"><sup>2</sup> There must be enough memory for `T_copy`.</span></span> <span data-ttu-id="add40-130">La mémoire n'est pas libérée immédiatement lors de l'exécution de `DROP TABLE`.</span><span class="sxs-lookup"><span data-stu-id="add40-130">Memory is not freed immediately on `DROP TABLE`.</span></span> <span data-ttu-id="add40-131">Si la table `T_copy` est mémoire optimisée, la mémoire disponible doit être suffisante pour deux copies supplémentaires de la table `T`.</span><span class="sxs-lookup"><span data-stu-id="add40-131">If `T_copy` is memory optimized, there needs to be enough memory for two additional copies of `T`.</span></span> <span data-ttu-id="add40-132">Si la table `T_copy` est sur disque, la mémoire disponible doit être suffisante pour une copie supplémentaire de la table `T`, car le garbage collector doit rattraper son retard après suppression de l'ancienne version de `T`.</span><span class="sxs-lookup"><span data-stu-id="add40-132">If `T_copy` is a disk-based table, there only needs to be enough memory for one additional copy of `T`, due to the garbage collector needing to catch up after dropping the old version of `T`.</span></span>  
  
## <a name="changing-schema-powershell"></a><span data-ttu-id="add40-133">Modification du schéma (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="add40-133">Changing Schema (PowerShell)</span></span>  
 <span data-ttu-id="add40-134">Les scripts PowerShell suivants préparent et génèrent les modifications de schéma en créant un script des autorisations de table et associées.</span><span class="sxs-lookup"><span data-stu-id="add40-134">The following PowerShell scripts prepare and generate for schema changes by scripting the table and associated permissions.</span></span>  
  
```powershell
prepare_schema_change.ps1 <serverName> <databaseName> <schemaName> <tableName>
```
  
 <span data-ttu-id="add40-135">Ce script accepte comme argument une table et génère le script de l'objet et de ses autorisations et des objets de référencement liés au schéma et leurs autorisations dans le dossier actif.</span><span class="sxs-lookup"><span data-stu-id="add40-135">This script takes as arguments a table, and scripts the object and its permissions and referencing schema-bound objects and their permissions in the current folder.</span></span> <span data-ttu-id="add40-136">Au total, sept scripts sont générés pour la mise à jour du schéma de la table d'entrée.</span><span class="sxs-lookup"><span data-stu-id="add40-136">A total of 7 scripts are generated for updating the schema of the input table:</span></span>  
  
-   <span data-ttu-id="add40-137">Copiez les données dans une table temporaire (un segment mémoire).</span><span class="sxs-lookup"><span data-stu-id="add40-137">Copy data to a temporary table (a heap).</span></span>  
  
-   <span data-ttu-id="add40-138">Supprimez les objets liés au schéma référençant la table.</span><span class="sxs-lookup"><span data-stu-id="add40-138">Drop schema-bound objects referencing the table.</span></span>  
  
-   <span data-ttu-id="add40-139">Déposer la table.</span><span class="sxs-lookup"><span data-stu-id="add40-139">Drop the table.</span></span>  
  
-   <span data-ttu-id="add40-140">Recréez la table avec le nouveau schéma et réappliquez les autorisations.</span><span class="sxs-lookup"><span data-stu-id="add40-140">Recreate the table with the new schema and reapply permissions.</span></span>  
  
-   <span data-ttu-id="add40-141">Copiez les données de la table temporaire dans la table recréée.</span><span class="sxs-lookup"><span data-stu-id="add40-141">Copy data from the temporary table to the recreated table.</span></span>  
  
-   <span data-ttu-id="add40-142">Recréez les objets liés au schéma référençant la table et leurs autorisations.</span><span class="sxs-lookup"><span data-stu-id="add40-142">Recreate schema-bound objects referencing the table and their permissions.</span></span>  
  
-   <span data-ttu-id="add40-143">Supprimez la table temporaire.</span><span class="sxs-lookup"><span data-stu-id="add40-143">Drop the temporary table.</span></span>  
  
 <span data-ttu-id="add40-144">Le script de l'étape 4 doit être mis à jour afin de refléter les modifications de schéma souhaitées.</span><span class="sxs-lookup"><span data-stu-id="add40-144">The script for step 4 should be updated to reflect the desired schema changes.</span></span> <span data-ttu-id="add40-145">Si des modifications sont apportées aux colonnes de la table, les scripts pour les étapes 5 (copier les données de la table temporaire) et 6 (recréer des procédures stockées) doivent être mis à jour si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="add40-145">If there are any changes in the columns of the table, the scripts for steps 5 (copy data from temporary table) and 6 (recreate stored procedures) should be updated as necessary.</span></span>  
  
```powershell
# Prepare for schema changes by scripting out the table, as well as associated permissions
# Usage: prepare_schema_change.ps1 server_name db_name schema_name table_name  
# stop execution once an error occurs  
$ErrorActionPreference="Stop"  
  
if($args.Count -le 3)  
{  
   throw "Usage prepare_schema_change.ps1 server_name db_name schema_name table_name"  
}  
  
$servername = $args[0]  
$database = $args[1]  
$schema = $args[2]  
$object = $args[3]  
  
$object_heap = "$object$(Get-Random)"  
  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.SMO") | Out-Null  
  
$server =  New-Object ("Microsoft.SqlServer.Management.SMO.Server") ($servername)  
$scripter = New-Object ("Microsoft.SqlServer.Management.SMO.Scripter") ($server)  
  
## initialize table variable  
$tableUrn = $server.Databases[$database].Tables[$object, $schema]  
if($tableUrn.Count -eq 0)  
{  
   throw "Table or database not found"  
}  
  
## initialize scripting object  
$scriptingOptions = New-Object ("Microsoft.SqlServer.Management.SMO.ScriptingOptions")
$scriptingOptions.Permissions = $True  
$scriptingOptions.ScriptDrops = $True  
  
$scripter.Options = $scriptingOptions;  
  
Write-Host "(1) Scripting SELECT INTO $object_heap for table [$object] to 1_copy_to_heap_for_$schema`_$object.sql"  
Echo "SELECT * INTO $schema.$object_heap FROM $schema.$object WITH (SNAPSHOT)" | Out-File "1_copy_to_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(2) Scripting DROP for procs schema-bound to [$object] 2_drop_procs_$schema`_$object.sql"  
## query referencing schema-bound objects  
$dt = $server.Databases[$database].ExecuteWithResults("select r.referencing_schema_name, r.referencing_entity_name  
from sys.dm_sql_referencing_entities ('$schema.$object', 'OBJECT') as r join sys.sql_modules m on r.referencing_id=m.object_id  
where r.is_caller_dependent = 0 and m.is_schema_bound=1;")  
  
## initialize out file  
Echo "" | Out-File "2_drop_procs_$schema`_$object.sql"  
## loop through schema-bound objects  
ForEach ($t In $dt.Tables)  
{    
   ForEach ($r In $t.Rows)  
   {    
      ## script object   
      $so =  $server.Databases[$database].StoredProcedures[$r[1], $r[0]]  
      $scripter.Script($so) | Out-File -Append "2_drop_procs_$schema`_$object.sql"  
   }  
}  
Write-Host "--done--"  
Write-Host ""  
Write-Host "(3) Scripting DROP table for [$object] to 3_drop_table_$schema`_$object.sql"
$scripter.Script($tableUrn) | Out-File "3_drop_table_$schema`_$object.sql";
Write-Host "--done--"  
Write-Host ""  
  
## now script creates  
$scriptingOptions.ScriptDrops = $False  
  
Write-Host "(4) Scripting CREATE table and permissions for [$object] to !please_edit_4_create_table_$schema`_$object.sql"  
Write-Host "***** rename this script to 4_create_table.sql after completing the updates to the schema"
$scripter.Script($tableUrn) | Out-File "!please_edit_4_create_table_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(5) Scripting INSERT INTO table from heap and UPDATE STATISTICS for [$object] to 5_copy_from_heap_$schema`_$object.sql"  
Write-Host "[update this script if columns are added to or removed from the table]"  
Echo "INSERT INTO [$schema].[$object] SELECT * FROM [$schema].[$object_heap]; UPDATE STATISTICS [$schema].[$object] WITH FULLSCAN, NORECOMPUTE" | Out-File "5_copy_from_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(6) Scripting CREATE PROC and permissions for procedures schema-bound to [$object] to 6_create_procs_$schema`_$object.sql"  
Write-Host "[update the procedure definitions if columns are renamed or removed]"  
## initialize out file  
Echo "" | Out-File "6_create_procs_$schema`_$object.sql"  
## loop through schema-bound objects  
ForEach ($t In $dt.Tables)  
{    
   ForEach ($r In $t.Rows)  
   {    
      ## script the schema-bound object  
      $so =  $server.Databases[$database].StoredProcedures[$r[1], $r[0]]  
      ForEach($s In $scripter.Script($so))  
        {  
            Echo $s | Out-File -Append "6_create_procs_$schema`_$object.sql"  
            Echo "GO" | Out-File -Append "6_create_procs_$schema`_$object.sql"  
        }  
   }  
}  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(7) Scripting DROP $object_heap to 7_drop_heap_$schema`_$object.sql"  
Echo "DROP TABLE $schema.$object_heap" | Out-File "7_drop_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
```  
  
 <span data-ttu-id="add40-146">Le script PowerShell suivant exécute les modifications de schéma qui ont fait l'objet d'un script dans l'exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="add40-146">The following PowerShell script executes the schema changes that were scripted in the previous sample.</span></span> <span data-ttu-id="add40-147">Ce script accepte comme argument une table et exécute les scripts de modification de schéma qui ont été générés pour cette table et les procédures stockées associées.</span><span class="sxs-lookup"><span data-stu-id="add40-147">This script takes as argument a table, and executes the schema change scripts that were generated for that table and the associated stored procedures.</span></span>  
  
 <span data-ttu-id="add40-148">Utilisation : execute_schema_change.ps1 *SERVER_NAME \* \* db_name `schema_name` table_name*</span><span class="sxs-lookup"><span data-stu-id="add40-148">Usage: execute_schema_change.ps1 *server_name\*\*db_name`schema_name`table_name*</span></span>  
  
```powershell
# stop execution once an error occurs  
$ErrorActionPreference="Stop"  
  
if($args.Count -le 3)  
{  
   throw "Usage execute_schema_change.ps1 server_name db_name schema_name table_name"  
}  
  
$servername = $args[0]  
$database = $args[1]  
$schema = $args[2]  
$object = $args[3]  
  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.SMO") | Out-Null  
  
$server =  New-Object ("Microsoft.SqlServer.Management.SMO.Server") ($servername)  
$database = $server.Databases[$database]  
$table = $database.Tables[$object, $schema]  
if($table.Count -eq 0)  
{  
   throw "Table or database not found"  
}  
  
$1 = Get-Item "1_copy_to_heap_$schema`_$object.sql"  
$2 = Get-Item "2_drop_procs_$schema`_$object.sql"  
$3 = Get-Item "3_drop_table_$schema`_$object.sql"  
$4 = Get-Item "4_create_table_$schema`_$object.sql"  
$5 = Get-Item "5_copy_from_heap_$schema`_$object.sql"  
$6 = Get-Item "6_create_procs_$schema`_$object.sql"  
$7 = Get-Item "7_drop_heap_$schema`_$object.sql"  
  
Write-Host "(1) Running SELECT INTO heap for table [$object] from 1_copy_to_heap_for_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $1.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(2) Running DROP for procs schema-bound from [$object] 2_drop_procs_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $2.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(3) Running DROP table for [$object] to 4_drop_table_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $3.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(4) Running CREATE table and permissions for [$object] from 4_create_table_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $4.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(5) Running INSERT INTO table from heap for [$object] and UPDATE STATISTICS from 5_copy_from_heap_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $5.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(6) Running CREATE PROC and permissions for procedures schema-bound to [$object] from 6_create_procs_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $6.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(7) Running DROP heap from 7_drop_heap_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $7.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
```  
  
## <a name="see-also"></a><span data-ttu-id="add40-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="add40-149">See Also</span></span>  
 [<span data-ttu-id="add40-150">Tables à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="add40-150">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
