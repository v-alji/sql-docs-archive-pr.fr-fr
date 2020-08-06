---
title: Afficher les dépendances d’une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], dependencies
- displaying stored procedure dependencies
- viewing stored procedure dependencies
ms.assetid: 6ae0a369-1bc7-4ae4-be89-2b483697cd1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 790684035d2db3b697fb8b718c96182eda8f1186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615103"
---
# <a name="view-the-dependencies-of-a-stored-procedure"></a><span data-ttu-id="6dc16-102">Afficher les dépendances d'une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="6dc16-102">View the Dependencies of a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-view-stored-procedure-dependencies-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="6dc16-103">Cette rubrique explique comment consulter les dépendances des procédures stockées dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dc16-103">This topic describes how to view stored procedure dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="6dc16-104">**Avant de commencer :**  [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="6dc16-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="6dc16-105">**Pour afficher les dépendances d’une procédure avec :**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="6dc16-105">**To view the dependencies of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6dc16-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="6dc16-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6dc16-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6dc16-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6dc16-108">Autorisations</span><span class="sxs-lookup"><span data-stu-id="6dc16-108">Permissions</span></span>  
 <span data-ttu-id="6dc16-109">Fonction système : `sys.dm_sql_referencing_entities`</span><span class="sxs-lookup"><span data-stu-id="6dc16-109">System Function: `sys.dm_sql_referencing_entities`</span></span>  
 <span data-ttu-id="6dc16-110">Requiert l'autorisation CONTROL sur l'entité référencée et l'autorisation SELECT sur sys.dm_sql_referencing_entities.</span><span class="sxs-lookup"><span data-stu-id="6dc16-110">Requires CONTROL permission on the referenced entity and SELECT permission on sys.dm_sql_referencing_entities.</span></span> <span data-ttu-id="6dc16-111">Lorsque l'entité référencée est une fonction de partition, l'autorisation CONTROL sur la base de données est requise.</span><span class="sxs-lookup"><span data-stu-id="6dc16-111">When the referenced entity is a partition function, CONTROL permission on the database is required.</span></span> <span data-ttu-id="6dc16-112">Par défaut, l'autorisation SELECT est accordée à public.</span><span class="sxs-lookup"><span data-stu-id="6dc16-112">By default, SELECT permission is granted to public.</span></span>  
  
 <span data-ttu-id="6dc16-113">Fonction système : `sys.dm_sql_referenced_entities`</span><span class="sxs-lookup"><span data-stu-id="6dc16-113">System Function: `sys.dm_sql_referenced_entities`</span></span>  
 <span data-ttu-id="6dc16-114">Requiert l'autorisation SELECT sur sys.dm_sql_referenced_entities et l'autorisation VIEW DEFINITION sur l'entité de référence.</span><span class="sxs-lookup"><span data-stu-id="6dc16-114">Requires SELECT permission on sys.dm_sql_referenced_entities and VIEW DEFINITION permission on the referencing entity.</span></span> <span data-ttu-id="6dc16-115">Par défaut, l'autorisation SELECT est accordée à public.</span><span class="sxs-lookup"><span data-stu-id="6dc16-115">By default, SELECT permission is granted to public.</span></span> <span data-ttu-id="6dc16-116">Requiert l'autorisation VIEW DEFINITION sur la base de données ou l'autorisation ALTER DATABASE DDL TRIGGER sur la base de données lorsque l'entité de référence est un déclencheur DDL au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="6dc16-116">Requires VIEW DEFINITION permission on the database or ALTER DATABASE DDL TRIGGER permission on the database when the referencing entity is a database-level DDL trigger.</span></span> <span data-ttu-id="6dc16-117">Requiert l'autorisation VIEW ANY DEFINITION sur le serveur lorsque l'entité de référence est un déclencheur DDL au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="6dc16-117">Requires VIEW ANY DEFINITION permission on the server when the referencing entity is a server-level DDL trigger.</span></span>  
  
 <span data-ttu-id="6dc16-118">Affichage catalogue d'objets : `sys.sql_expression_dependencies`</span><span class="sxs-lookup"><span data-stu-id="6dc16-118">Object Catalog View: `sys.sql_expression_dependencies`</span></span>  
 <span data-ttu-id="6dc16-119">Requiert l'autorisation VIEW DEFINITION sur la base de données et l'autorisation SELECT sur sys.sql_expression_dependencies pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="6dc16-119">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="6dc16-120">Par défaut, l'autorisation SELECT est accordée uniquement aux membres du rôle de base de données fixe db_owner.</span><span class="sxs-lookup"><span data-stu-id="6dc16-120">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="6dc16-121">Lorsque les autorisations SELECT et VIEW DEFINITION sont accordées à un autre utilisateur, le bénéficiaire peut consulter toutes les dépendances dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="6dc16-121">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="how-to-view-the-dependencies-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="6dc16-122">Pour afficher les dépendances d'une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="6dc16-122">How to View the Dependencies of a Stored Procedure</span></span>  
 <span data-ttu-id="6dc16-123">Vous pouvez utiliser l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6dc16-123">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="6dc16-124">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6dc16-124">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="6dc16-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6dc16-125">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6dc16-126">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6dc16-126">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6dc16-127">**Pour afficher les dépendances d'une procédure dans l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="6dc16-127">**To view the dependencies of a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="6dc16-128">Dans l'Explorateur d'objets, connectez-vous à une instance de [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="6dc16-128">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6dc16-129">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure, puis développez **Programmabilité**.</span><span class="sxs-lookup"><span data-stu-id="6dc16-129">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="6dc16-130">Développez **Procédures stockées**, cliquez avec le bouton droit sur la procédure, puis cliquez sur **Afficher les dépendances**.</span><span class="sxs-lookup"><span data-stu-id="6dc16-130">Expand **Stored Procedures**, right-click the procedure and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="6dc16-131">Examinez la liste des objets qui dépendent de la procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-131">View the list of objects that depend on the procedure.</span></span>  
  
5.  <span data-ttu-id="6dc16-132">Examinez la liste des objets dont dépend la procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-132">View the list of objects on which the procedure depends.</span></span>  
  
6.  <span data-ttu-id="6dc16-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6dc16-133">Click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6dc16-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6dc16-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="6dc16-135">**Pour afficher les dépendances d'une procédure dans l'Éditeur de requête**</span><span class="sxs-lookup"><span data-stu-id="6dc16-135">**To view the dependencies of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="6dc16-136">Fonction système : `sys.dm_sql_referencing_entities`</span><span class="sxs-lookup"><span data-stu-id="6dc16-136">System Function: `sys.dm_sql_referencing_entities`</span></span>  
 <span data-ttu-id="6dc16-137">Cette fonction est utilisée pour afficher les objets qui dépendent d'une procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-137">This function is used to display the objects that depend on a procedure.</span></span>  
  
1.  <span data-ttu-id="6dc16-138">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="6dc16-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6dc16-139">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-139">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="6dc16-140">Dans le menu **Fichier** , cliquez sur **Nouvelle requête** .</span><span class="sxs-lookup"><span data-stu-id="6dc16-140">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="6dc16-141">Copiez et collez les exemples suivants dans l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="6dc16-141">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="6dc16-142">Le premier exemple crée la procédure `uspVendorAllInfo` qui retourne le nom de tous les fournisseurs dans la base de données [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , les produits qu'ils vendent, leurs conditions de crédit et leur disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6dc16-142">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="6dc16-143">Une fois la procédure créée, le deuxième exemple utilise la fonction sys.dm_sql_referencing_entities pour afficher les objets qui dépendent de la procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-143">After the procedure is created, the second example uses the sys.dm_sql_referencing_entities function to display the objects that depend on the procedure.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referencing_schema_name, referencing_entity_name, referencing_id, referencing_class_desc, is_caller_dependent  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');   
    GO  
  
    ```  
  
 <span data-ttu-id="6dc16-144">Fonction système : `sys.dm_sql_referenced_entities`</span><span class="sxs-lookup"><span data-stu-id="6dc16-144">System Function: `sys.dm_sql_referenced_entities`</span></span>  
 <span data-ttu-id="6dc16-145">Cette fonction est utilisée pour afficher les objets dont la procédure dépend.</span><span class="sxs-lookup"><span data-stu-id="6dc16-145">This function is used to display the objects a procedure depends on.</span></span>  
  
1.  <span data-ttu-id="6dc16-146">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="6dc16-146">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6dc16-147">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-147">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="6dc16-148">Dans le menu **Fichier** , cliquez sur **Nouvelle requête** .</span><span class="sxs-lookup"><span data-stu-id="6dc16-148">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="6dc16-149">Copiez et collez les exemples suivants dans l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="6dc16-149">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="6dc16-150">Le premier exemple crée la procédure `uspVendorAllInfo` qui retourne le nom de tous les fournisseurs dans la base de données [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , les produits qu'ils vendent, leurs conditions de crédit et leur disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6dc16-150">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="6dc16-151">Une fois la procédure créée, le deuxième exemple utilise la fonction sys.dm_sql_referenced_entities pour afficher les objets dont dépend la procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-151">After the procedure is created, the second example uses the sys.dm_sql_referenced_entities function to display the objects that the procedure depends on.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referenced_schema_name, referenced_entity_name,  
    referenced_minor_name,referenced_minor_id, referenced_class_desc,  
    is_caller_dependent, is_ambiguous  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');  
    GO  
    ```  
  
 <span data-ttu-id="6dc16-152">Affichage catalogue d'objets : `sys.sql_expression_dependencies`</span><span class="sxs-lookup"><span data-stu-id="6dc16-152">Object Catalog View: `sys.sql_expression_dependencies`</span></span>  
 <span data-ttu-id="6dc16-153">Cette vue peut être utilisée pour afficher des objets dont une procédure dépend ou qui dépendent d'une procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-153">This view can be used to display objects that a procedure depends on or that depend on a procedure.</span></span>  
  
 <span data-ttu-id="6dc16-154">Affichage des objets qui dépendent d'une procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-154">Displaying the objects that depend on a procedure.</span></span>  
 1.  <span data-ttu-id="6dc16-155">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="6dc16-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6dc16-156">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-156">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="6dc16-157">Dans le menu **Fichier** , cliquez sur **Nouvelle requête** .</span><span class="sxs-lookup"><span data-stu-id="6dc16-157">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="6dc16-158">Copiez et collez les exemples suivants dans l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="6dc16-158">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="6dc16-159">Le premier exemple crée la procédure `uspVendorAllInfo` qui retourne le nom de tous les fournisseurs dans la base de données [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , les produits qu'ils vendent, leurs conditions de crédit et leur disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6dc16-159">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="6dc16-160">Une fois la procédure créée, le deuxième exemple utilise la fonction sys.sql_expression_dependencies pour afficher les objets qui dépendent de la procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-160">After the procedure is created, the second example uses the sys.sql_expression_dependencies view to display the objects that depend on the procedure.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_SCHEMA_NAME ( referencing_id ) AS referencing_schema_name,  
        OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referenced_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
 <span data-ttu-id="6dc16-161">Affichage des objets dont une procédure dépend.</span><span class="sxs-lookup"><span data-stu-id="6dc16-161">Displaying the objects a procedure depends on.</span></span>  
 1.  <span data-ttu-id="6dc16-162">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="6dc16-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6dc16-163">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-163">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="6dc16-164">Dans le menu **Fichier** , cliquez sur **Nouvelle requête** .</span><span class="sxs-lookup"><span data-stu-id="6dc16-164">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="6dc16-165">Copiez et collez les exemples suivants dans l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="6dc16-165">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="6dc16-166">Le premier exemple crée la procédure `uspVendorAllInfo` qui retourne le nom de tous les fournisseurs dans la base de données [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , les produits qu'ils vendent, leurs conditions de crédit et leur disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6dc16-166">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="6dc16-167">Une fois la procédure créée, le deuxième exemple utilise la fonction sys.sql_expression_dependencies pour afficher les objets dont dépend la procédure.</span><span class="sxs-lookup"><span data-stu-id="6dc16-167">After the procedure is created, the second example uses the sys.sql_expression_dependencies view to display the objects the procedure depends on.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referencing_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6dc16-168">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6dc16-168">See Also</span></span>  
 <span data-ttu-id="6dc16-169">[Renommer une procédure stockée](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6dc16-169">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="6dc16-170">[sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6dc16-170">[sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql) </span></span>  
 <span data-ttu-id="6dc16-171">[sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6dc16-171">[sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql) </span></span>  
 [<span data-ttu-id="6dc16-172">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6dc16-172">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
  
