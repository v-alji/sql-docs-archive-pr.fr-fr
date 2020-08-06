---
title: Activer et désactiver la capture de données modifiées (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change data capture [SQL Server], enabling tables
- change data capture [SQL Server], enabling databases
- change data capture [SQL Server], disabling databases
- change data capture [SQL Server], disabling tables
ms.assetid: b741894f-d267-4b10-adfe-cbc14aa6caeb
author: rothja
ms.author: jroth
ms.openlocfilehash: df0a2fd4a2c6ffb2de58d6b52360d1730d0fa7df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605312"
---
# <a name="enable-and-disable-change-data-capture-sql-server"></a><span data-ttu-id="21418-102">Activer et désactiver la capture de données modifiées (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="21418-102">Enable and Disable Change Data Capture (SQL Server)</span></span>
  <span data-ttu-id="21418-103">Cette rubrique décrit l'activation et la désactivation de la capture de données modifiées pour une base de données et une table.</span><span class="sxs-lookup"><span data-stu-id="21418-103">This topic describes how to enable and disable change data capture for a database and a table.</span></span>  
  
## <a name="enable-change-data-capture-for-a-database"></a><span data-ttu-id="21418-104">Activer la capture des données modifiées pour une base de données</span><span class="sxs-lookup"><span data-stu-id="21418-104">Enable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="21418-105">Avant qu'une instance de capture puisse être créée pour des tables individuelles, un membre du rôle serveur fixe `sysadmin` doit d'abord activer la base de données pour la capture des données modifiées.</span><span class="sxs-lookup"><span data-stu-id="21418-105">Before a capture instance can be created for individual tables, a member of the `sysadmin` fixed server role must first enable the database for change data capture.</span></span> <span data-ttu-id="21418-106">Cela se fait en exécutant la procédure stockée [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) dans le contexte de la base de données.</span><span class="sxs-lookup"><span data-stu-id="21418-106">This is done by running the stored procedure [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) in the database context.</span></span> <span data-ttu-id="21418-107">Pour déterminer si une base de données est déjà activée, interrogez la colonne `is_cdc_enabled` dans l'affichage catalogue `sys.databases`.</span><span class="sxs-lookup"><span data-stu-id="21418-107">To determine if a database is already enabled, query the `is_cdc_enabled` column in the `sys.databases` catalog view.</span></span>  
  
 <span data-ttu-id="21418-108">Lorsqu'une base de données est activée pour la capture des données modifiées, le schéma `cdc`, l'utilisateur `cdc`, les tables de métadonnées, ainsi que d'autres objets systèmes sont créés pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="21418-108">When a database is enabled for change data capture, the `cdc` schema, `cdc` user, metadata tables, and other system objects are created for the database.</span></span> <span data-ttu-id="21418-109">Le schéma `cdc` contient les tables de métadonnées de capture des données modifiées et, une fois que les tables sources sont activées pour la capture des données modifiées, les tables de modifications individuelles servent de base de données de référentiel pour les données modifiées.</span><span class="sxs-lookup"><span data-stu-id="21418-109">The `cdc` schema contains the change data capture metadata tables and, after source tables are enabled for change data capture, the individual change tables serve as a repository for change data.</span></span> <span data-ttu-id="21418-110">Le schéma `cdc` contient également les fonctions système associées utilisées pour rechercher les données modifiées.</span><span class="sxs-lookup"><span data-stu-id="21418-110">The `cdc` schema also contains associated system functions used to query for change data.</span></span>  
  
 <span data-ttu-id="21418-111">La capture des données modifiées requiert une utilisation exclusive du schéma `cdc` et de l'utilisateur `cdc`.</span><span class="sxs-lookup"><span data-stu-id="21418-111">Change data capture requires exclusive use of the `cdc` schema and `cdc` user.</span></span> <span data-ttu-id="21418-112">Si un schéma ou un utilisateur de base de données nommé *cdc* existe actuellement dans une base de données, celle-ci ne peut pas être activée pour la capture des données modifiées tant que le schéma et/ou l'utilisateur n'a pas été supprimé ou renommé.</span><span class="sxs-lookup"><span data-stu-id="21418-112">If either a schema or a database user named *cdc* currently exists in a database, the database cannot be enabled for change data capture until the schema and or user are dropped or renamed.</span></span>  
  
 <span data-ttu-id="21418-113">Pour un exemple d'activation de base de données, consultez le modèle Activer la base de données pour la capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="21418-113">See the Enable Database for Change Data Capture template for an example of enabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="21418-114">Pour repérer les modèles dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], allez dans **Afficher**, cliquez sur **Explorateur de modèles**, puis sélectionnez **Modèles SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="21418-114">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then select **SQL Server Templates**.</span></span> <span data-ttu-id="21418-115">**Capture de données modifiées** est un sous-dossier.</span><span class="sxs-lookup"><span data-stu-id="21418-115">**Change Data Capture** is a sub-folder.</span></span> <span data-ttu-id="21418-116">Sous ce dossier, vous trouverez tous les modèles auxquels il est fait référence dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="21418-116">Under this folder, you will find all the templates referenced in this topic.</span></span> <span data-ttu-id="21418-117">On trouve également une icône **Explorateur de modèles** dans la barre d'outils [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21418-117">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- ====  
-- Enable Database for CDC template   
-- ====  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_db  
GO  
```  
  
## <a name="disable-change-data-capture-for-a-database"></a><span data-ttu-id="21418-118">Désactiver la capture des données modifiées pour une base de données</span><span class="sxs-lookup"><span data-stu-id="21418-118">Disable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="21418-119">Un membre du `sysadmin` rôle serveur fixe peut exécuter la procédure stockée [sys. Sp_cdc_disable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) dans le contexte de la base de données pour désactiver la capture de données modifiées pour une base de données.</span><span class="sxs-lookup"><span data-stu-id="21418-119">A member of the `sysadmin` fixed server role can run the stored procedure [sys.sp_cdc_disable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) in the database context to disable change data capture for a database.</span></span> <span data-ttu-id="21418-120">Il n'est pas nécessaire de désactiver individuellement les tables avant de désactiver la base de données.</span><span class="sxs-lookup"><span data-stu-id="21418-120">It is not necessary to disable individual tables before you disable the database.</span></span> <span data-ttu-id="21418-121">La désactivation de la base de données supprime toutes les métadonnées de capture de données modifiées associées, y compris l'utilisateur et le schéma `cdc`, ainsi que les travaux de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="21418-121">Disabling the database removes all associated change data capture metadata, including the `cdc` user and schema and the change data capture jobs.</span></span> <span data-ttu-id="21418-122">Toutefois, tous les rôles de régulation créés par capture de données modifiées ne seront pas supprimés automatiquement et doivent être supprimés explicitement.</span><span class="sxs-lookup"><span data-stu-id="21418-122">However, any gating roles created by change data capture will not be removed automatically and must be explicitly deleted.</span></span> <span data-ttu-id="21418-123">Pour déterminer si une base de données est activée, interrogez la colonne `is_cdc_enabled` dans l'affichage catalogue sys.databases.</span><span class="sxs-lookup"><span data-stu-id="21418-123">To determine if a database is enabled, query the `is_cdc_enabled` column in the sys.databases catalog view.</span></span>  
  
 <span data-ttu-id="21418-124">Si une base de données sur laquelle la capture de données modifiées est activée est supprimée, les travaux de capture de données modifiées sont également et automatiquement supprimés.</span><span class="sxs-lookup"><span data-stu-id="21418-124">If a change data capture enabled database is dropped, change data capture jobs are automatically removed.</span></span>  
  
 <span data-ttu-id="21418-125">Pour un exemple de désactivation d'une base de données, consultez le modèle Désactiver la base de données pour la capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="21418-125">See the Disable Database for Change Data Capture template for an example of disabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="21418-126">Pour repérer les modèles dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], allez dans **Afficher**, cliquez sur **Explorateur de modèles**, puis sur **Modèles SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="21418-126">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then click **SQL Server Templates**.</span></span> <span data-ttu-id="21418-127">**Capture de données modifiées** est un sous-dossier où vous trouverez tous les modèles qui sont référencés dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="21418-127">**Change Data Capture** is a sub-folder where you will find all the templates that are referenced in this topic.</span></span> <span data-ttu-id="21418-128">On trouve également une icône **Explorateur de modèles** dans la barre d'outils [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21418-128">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- =======  
-- Disable Database for Change Data Capture template   
-- =======  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_db  
GO  
```  
  
## <a name="enable-change-data-capture-for-a-table"></a><span data-ttu-id="21418-129">Activer la capture des données modifiées pour une table</span><span class="sxs-lookup"><span data-stu-id="21418-129">Enable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="21418-130">Une fois qu'une base de données a été activée pour la capture des données modifiées, les membres du rôle de base de données fixe `db_owner` peuvent créer une instance de capture pour les tables sources individuelles à l'aide de la procédure stockée `sys.sp_cdc_enable_table`.</span><span class="sxs-lookup"><span data-stu-id="21418-130">After a database has been enabled for change data capture, members of the `db_owner` fixed database role can create a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_enable_table`.</span></span> <span data-ttu-id="21418-131">Pour déterminer si une table source a été déjà activée pour la capture des données modifiées, examinez la colonne is_tracked_by_cdc dans l'affichage catalogue `sys.tables`.</span><span class="sxs-lookup"><span data-stu-id="21418-131">To determine whether a source table has already been enabled for change data capture, examine the is_tracked_by_cdc column in the `sys.tables` catalog view.</span></span>  
  
 <span data-ttu-id="21418-132">Les options suivantes peuvent être spécifiées lorsque vous créez une instance de capture :</span><span class="sxs-lookup"><span data-stu-id="21418-132">The following options can be specified when creating a capture instance:</span></span>  
  
 <span data-ttu-id="21418-133">`Columns in the source table to be captured`.</span><span class="sxs-lookup"><span data-stu-id="21418-133">`Columns in the source table to be captured`.</span></span>  
  
 <span data-ttu-id="21418-134">Par défaut, toutes les colonnes de la table source sont identifiées comme colonnes capturées.</span><span class="sxs-lookup"><span data-stu-id="21418-134">By default, all of the columns in the source table are identified as captured columns.</span></span> <span data-ttu-id="21418-135">Si seul un sous-ensemble de colonnes doit être suivi, par exemple pour des raisons de confidentialité ou de performance, utilisez le *@captured_column_list* paramètre pour spécifier le sous-ensemble de colonnes.</span><span class="sxs-lookup"><span data-stu-id="21418-135">If only a subset of columns need to be tracked, such as for privacy or performance reasons, use the *@captured_column_list* parameter to specify the subset of columns.</span></span>  
  
 `A filegroup to contain the change table.`  
  
 <span data-ttu-id="21418-136">Par défaut, la table de modifications se situe dans le groupe de fichiers par défaut de la base de données.</span><span class="sxs-lookup"><span data-stu-id="21418-136">By default, the change table is located in the default filegroup of the database.</span></span> <span data-ttu-id="21418-137">Les propriétaires de bases de données qui souhaitent contrôler le placement des tables de modifications individuelles peuvent utiliser le *@filegroup_name* paramètre pour spécifier un groupe de fichiers particulier pour la table de modifications associée à l’instance de capture.</span><span class="sxs-lookup"><span data-stu-id="21418-137">Database owners who want to control the placement of individual change tables can use the *@filegroup_name* parameter to specify a particular filegroup for the change table associated with the capture instance.</span></span> <span data-ttu-id="21418-138">Le groupe de fichiers nommé doit déjà exister.</span><span class="sxs-lookup"><span data-stu-id="21418-138">The named filegroup must already exist.</span></span> <span data-ttu-id="21418-139">En règle générale, il est recommandé de placer des tables de modifications dans un groupe de fichiers séparé des tables sources.</span><span class="sxs-lookup"><span data-stu-id="21418-139">Generally, it is recommended that change tables be placed in a filegroup separate from source tables.</span></span> <span data-ttu-id="21418-140">Consultez le `Enable a Table Specifying Filegroup Option` modèle pour obtenir un exemple qui illustre l’utilisation du *@filegroup_name* paramètre.</span><span class="sxs-lookup"><span data-stu-id="21418-140">See the `Enable a Table Specifying Filegroup Option` template for an example showing use of the *@filegroup_name* parameter.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Specifying Filegroup Option Template  
-- =========  
USE MyDB  
GO  
  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@filegroup_name = N'MyDB_CT',  
@supports_net_changes = 1  
GO  
```  
  
 `A role for controlling access to a change table.`  
  
 <span data-ttu-id="21418-141">L'objectif du rôle nommé consiste à contrôler l'accès aux données modifiées.</span><span class="sxs-lookup"><span data-stu-id="21418-141">The purpose of the named role is to control access to the change data.</span></span> <span data-ttu-id="21418-142">Le rôle spécifié peut être un rôle serveur fixe existant ou un rôle de base de données.</span><span class="sxs-lookup"><span data-stu-id="21418-142">The specified role can be an existing fixed server role or a database role.</span></span> <span data-ttu-id="21418-143">Si le rôle spécifié n'existe pas déjà, un rôle de base de données portant ce nom est automatiquement créé.</span><span class="sxs-lookup"><span data-stu-id="21418-143">If the specified role does not already exist, a database role of that name is created automatically.</span></span> <span data-ttu-id="21418-144">Les membres du rôle `sysadmin` ou `db_owner` disposent d'un accès complet aux données des tables de modification.</span><span class="sxs-lookup"><span data-stu-id="21418-144">Members of either the `sysadmin` or `db_owner` role have full access to the data in the change tables.</span></span> <span data-ttu-id="21418-145">Tous les autres utilisateurs doivent disposer de l'autorisation SELECT pour toutes les colonnes capturées de la table source.</span><span class="sxs-lookup"><span data-stu-id="21418-145">All other users must have SELECT permission on all the captured columns of the source table.</span></span> <span data-ttu-id="21418-146">De plus, lorsqu'un rôle est spécifié, les utilisateurs qui ne sont pas membres du rôle `sysadmin` or `db_owner` doivent également être membres du rôle spécifié.</span><span class="sxs-lookup"><span data-stu-id="21418-146">In addition, when a role is specified, users who are not members of either the `sysadmin` or `db_owner` role must also be members of the specified role.</span></span>  
  
 <span data-ttu-id="21418-147">Si vous ne souhaitez pas utiliser un rôle de régulation, affectez explicitement la valeur *@role_name* null au paramètre.</span><span class="sxs-lookup"><span data-stu-id="21418-147">If you do not want to use a gating role, explicitly set the *@role_name* parameter to NULL.</span></span> <span data-ttu-id="21418-148">Consultez le modèle `Enable a Table Without Using a Gating Role` pour obtenir un exemple de l'activation d'une table sans un rôle de régulation.</span><span class="sxs-lookup"><span data-stu-id="21418-148">See the `Enable a Table Without Using a Gating Role` template for an example of enabling a table without a gating role.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Without Using a Gating Role template   
-- =========  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = NULL,  
@supports_net_changes = 1  
GO  
  
```  
  
 `A function to query for net changes.`  
  
 <span data-ttu-id="21418-149">Une instance de capture inclura toujours une fonction table pour retourner toutes les entrées de table de modifications qui ont eu lieu au cours d'un intervalle défini.</span><span class="sxs-lookup"><span data-stu-id="21418-149">A capture instance will always include a table valued function for returning all change table entries that occurred within a defined interval.</span></span> <span data-ttu-id="21418-150">On nomme cette fonction en ajoutant le nom de l'instance de capture à "cdc.fn_cdc_get_all_changes_".</span><span class="sxs-lookup"><span data-stu-id="21418-150">This function is named by appending the capture instance name to "cdc.fn_cdc_get_all_changes_".</span></span> <span data-ttu-id="21418-151">Pour plus d’informations, consultez [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="21418-151">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="21418-152">Si le paramètre *@supports_net_changes* a la valeur 1, une fonction de modifications nettes est également générée pour l’instance de capture.</span><span class="sxs-lookup"><span data-stu-id="21418-152">If the parameter *@supports_net_changes* is set to 1, a net changes function is also generated for the capture instance.</span></span> <span data-ttu-id="21418-153">Cette fonction retourne une seule modification pour chaque ligne distincte modifiée dans l'intervalle spécifié dans l'appel.</span><span class="sxs-lookup"><span data-stu-id="21418-153">This function returns only one change for each distinct row changed in the interval specified in the call.</span></span> <span data-ttu-id="21418-154">Pour plus d’informations, consultez [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="21418-154">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="21418-155">Pour prendre en charge les requêtes de modifications nettes, la table source doit disposer d'une clé primaire ou d'un index unique permettant d'identifier sans ambiguïté les lignes.</span><span class="sxs-lookup"><span data-stu-id="21418-155">To support net changes queries, the source table must have a primary key or unique index to uniquely identify rows.</span></span> <span data-ttu-id="21418-156">Si un index unique est utilisé, le nom de l’index doit être spécifié à l’aide du *@index_name* paramètre.</span><span class="sxs-lookup"><span data-stu-id="21418-156">If a unique index is used, the name of the index must be specified using the *@index_name* parameter.</span></span> <span data-ttu-id="21418-157">Les colonnes définies dans la clé primaire ou l'index unique doivent être incluses dans la liste des colonnes sources à capturer.</span><span class="sxs-lookup"><span data-stu-id="21418-157">The columns defined in the primary key or unique index must be included in the list of source columns to be captured.</span></span>  
  
 <span data-ttu-id="21418-158">Consultez le modèle `Enable a Table for All and Net Changes Queries` pour obtenir un exemple démontrant la création d'une instance de capture avec les deux fonctions de requête.</span><span class="sxs-lookup"><span data-stu-id="21418-158">See the `Enable a Table for All and Net Changes Queries` template for an example demonstrating the creation of a capture instance with both query functions.</span></span>  
  
```sql  
-- =============  
-- Enable a Table for All and Net Changes Queries template   
-- =============  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@supports_net_changes = 1  
GO  
```  
  
> [!NOTE]
>  <span data-ttu-id="21418-159">Si la capture de données modifiées est activée sur une table avec une clé primaire existante et que le *@index_name* paramètre n’est pas utilisé pour identifier un autre index unique, la fonctionnalité de capture de données modifiées utilisera la clé primaire.</span><span class="sxs-lookup"><span data-stu-id="21418-159">If change data capture is enabled on a table with an existing primary key, and the *@index_name* parameter is not used to identify an alternative unique index, the change data capture feature will use the primary key.</span></span> <span data-ttu-id="21418-160">Les modifications ultérieures à la clé primaire ne seront pas autorisées sans désactivation préalable de la capture de données modifiées pour la table.</span><span class="sxs-lookup"><span data-stu-id="21418-160">Subsequent changes to the primary key will not be allowed without first disabling change data capture for the table.</span></span> <span data-ttu-id="21418-161">Cela est vrai, que la prise en charge des requêtes de modifications nettes ait été demandée ou non lors de la configuration de la capture de données.</span><span class="sxs-lookup"><span data-stu-id="21418-161">This is true regardless of whether support for net changes queries was requested when change data capture was configured.</span></span> <span data-ttu-id="21418-162">Si une table ne contient pas de clé primaire au moment de son activation pour la capture de données modifiées, tout ajout ultérieur de clé primaire sera ignoré par la capture des données modifiées.</span><span class="sxs-lookup"><span data-stu-id="21418-162">If there is no primary key on a table at the time it is enabled for change data capture, the subsequent addition of a primary key is ignored by change data capture.</span></span> <span data-ttu-id="21418-163">Étant donné que la capture de données modifiées n'utilisera pas de clé primaire créée une fois la table activée, la clé et les colonnes clés peuvent être supprimées sans restrictions.</span><span class="sxs-lookup"><span data-stu-id="21418-163">Because change data capture will not use a primary key that is created after the table was enabled, the key and key columns can be removed without restrictions.</span></span>  
  
## <a name="disable-change-data-capture-for-a-table"></a><span data-ttu-id="21418-164">Désactiver la capture des données modifiées pour une table</span><span class="sxs-lookup"><span data-stu-id="21418-164">Disable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="21418-165">Les membres du rôle de base de données fixe `db_owner` peuvent supprimer une instance de capture pour les tables sources individuelles à l'aide de la procédure stockée `sys.sp_cdc_disable_table`.</span><span class="sxs-lookup"><span data-stu-id="21418-165">Members of the `db_owner` fixed database role can remove a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_disable_table`.</span></span> <span data-ttu-id="21418-166">Pour déterminer si une table source est actuellement activée pour la capture des données modifiées, examinez la colonne `is_tracked_by_cdc` dans l'affichage catalogue `sys.tables`.</span><span class="sxs-lookup"><span data-stu-id="21418-166">To determine whether a source table is currently enabled for change data capture, examine the `is_tracked_by_cdc` column in the `sys.tables` catalog view.</span></span> <span data-ttu-id="21418-167">S'il n'y a pas de tables activées pour la base de données après la désactivation, les travaux de capture de données modifiées sont également supprimés.</span><span class="sxs-lookup"><span data-stu-id="21418-167">If there are no tables enabled for the database after the disabling takes place, the change data capture jobs are also removed.</span></span>  
  
 <span data-ttu-id="21418-168">Si une table pour laquelle la capture de données modifiées est activée est supprimée, les métadonnées de capture de données modifiées associées à la table sont automatiquement supprimées.</span><span class="sxs-lookup"><span data-stu-id="21418-168">If a change data capture-enabled table is dropped, change data capture metadata that is associated with the table is automatically removed.</span></span>  
  
 <span data-ttu-id="21418-169">Pour un exemple de désactivation de table, consultez le modèle Désactiver une instance de capture pour une table.</span><span class="sxs-lookup"><span data-stu-id="21418-169">See the Disable a Capture Instance for a Table template for an example of disabling a table.</span></span>  
  
```sql  
-- =====  
-- Disable a Capture Instance for a Table template   
-- =====  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@capture_instance = N'dbo_MyTable'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="21418-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21418-170">See Also</span></span>  
 <span data-ttu-id="21418-171">[Suivi des modifications de données &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="21418-171">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="21418-172">[À propos de la capture de données modifiées &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="21418-172">[About Change Data Capture &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span></span>  
 <span data-ttu-id="21418-173">[Utiliser les données modifiées &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="21418-173">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="21418-174">Administrer et surveiller la capture de données modifiées &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="21418-174">Administer and Monitor Change Data Capture &#40;SQL Server&#41;</span></span>](../track-changes/administer-and-monitor-change-data-capture-sql-server.md)  
  
  
