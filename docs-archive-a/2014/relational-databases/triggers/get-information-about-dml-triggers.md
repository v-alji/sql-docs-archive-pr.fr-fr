---
title: Obtenir des informations sur les déclencheurs DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- viewing DML triggers
- DML triggers, metadata
- displaying DML triggers
- status information [SQL Server], triggers
- DML triggers, viewing
ms.assetid: 37574aac-181d-4aca-a2cc-8abff64237dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 2f65976d2f517137e23bd9e5e1c98cc76324bc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613884"
---
# <a name="get-information-about-dml-triggers"></a><span data-ttu-id="02987-102">Obtenir des informations sur les déclencheurs DML</span><span class="sxs-lookup"><span data-stu-id="02987-102">Get Information About DML Triggers</span></span>
  <span data-ttu-id="02987-103">Cette rubrique explique comment obtenir des informations sur les déclencheurs DML dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02987-103">This topic describes how to get information about DML triggers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="02987-104">Ces informations peuvent inclure les types de déclencheurs existant sur une table, ainsi que leur nom, leur propriétaire et la date de leur création ou modification.</span><span class="sxs-lookup"><span data-stu-id="02987-104">This information can include the types of triggers on a table, the name of a trigger, its owner and the date it was created or modified.</span></span> <span data-ttu-id="02987-105">Si le déclencheur n'a pas été chiffré lors de sa création, vous obtenez la définition du déclencheur.</span><span class="sxs-lookup"><span data-stu-id="02987-105">If the trigger was not encrypted when it was created, you obtain the definition of the trigger.</span></span> <span data-ttu-id="02987-106">Vous pouvez utiliser la définition pour vous aider à comprendre comment un déclencheur affecte la table sur laquelle il est défini.</span><span class="sxs-lookup"><span data-stu-id="02987-106">You can use the definition to help you understand how a trigger affects the table up on which it is defined.</span></span> <span data-ttu-id="02987-107">En outre, vous pouvez déterminer les objets qu'un déclencheur spécifique utilise.</span><span class="sxs-lookup"><span data-stu-id="02987-107">Also, you can find out the objects that a specific trigger uses.</span></span> <span data-ttu-id="02987-108">Avec ces informations, vous pouvez identifier les objets dont l'éventuelle suppression ou modification aurait une répercussion sur le déclencheur.</span><span class="sxs-lookup"><span data-stu-id="02987-108">With this information, you can identify the objects that affect the trigger if they are changed or deleted in the database.</span></span>  
  
 <span data-ttu-id="02987-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="02987-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="02987-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="02987-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="02987-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="02987-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="02987-112">**Pour obtenir des informations sur les déclencheurs DML, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="02987-112">**To get information about DML triggers, using:**</span></span>  
  
     [<span data-ttu-id="02987-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="02987-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="02987-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="02987-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="02987-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="02987-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="02987-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="02987-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="02987-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="02987-117">Permissions</span></span>  
 <span data-ttu-id="02987-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span><span class="sxs-lookup"><span data-stu-id="02987-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="02987-119">Pour plus d'informations, consultez [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="02987-119">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
 <span data-ttu-id="02987-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span><span class="sxs-lookup"><span data-stu-id="02987-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span></span>  
 <span data-ttu-id="02987-121">Nécessite l'appartenance au rôle **public** .</span><span class="sxs-lookup"><span data-stu-id="02987-121">Requires membership in the **public** role.</span></span> <span data-ttu-id="02987-122">La définition des objets utilisateur est visible par le propriétaire de l’objet ou les bénéficiaires de l’une des autorisations suivantes : ALTER, CONTROL, TAKE OWNERSHIP ou VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="02987-122">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="02987-123">Ces autorisations sont implicitement possédées par des membres des rôles de base de données fixes **db_owner**, **db_ddladmin**et **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="02987-123">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="02987-124">**sys.sql_expression_dependencies**</span><span class="sxs-lookup"><span data-stu-id="02987-124">**sys.sql_expression_dependencies**</span></span>  
 <span data-ttu-id="02987-125">Requiert l’autorisation VIEW DEFINITION sur la base de données et l’autorisation SELECT sur **sys.sql_expression_dependencies** pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="02987-125">Requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="02987-126">Par défaut, l’autorisation SELECT est accordée uniquement aux membres du rôle de base de données fixe **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="02987-126">By default, SELECT permission is granted only to members of the **db_owner** fixed database role.</span></span> <span data-ttu-id="02987-127">Lorsque les autorisations SELECT et VIEW DEFINITION sont accordées à un autre utilisateur, le bénéficiaire peut consulter toutes les dépendances dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="02987-127">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="02987-128">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="02987-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="02987-129">Pour voir la définition d'un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="02987-129">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="02987-130">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="02987-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="02987-131">Développez la base de données choisie, développez **Tables**, puis développez la table qui contient le déclencheur dont vous souhaitez consulter la définition.</span><span class="sxs-lookup"><span data-stu-id="02987-131">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger for which you want to view the definition.</span></span>  
  
3.  <span data-ttu-id="02987-132">Développez **Déclencheurs**, cliquez avec le bouton droit sur le déclencheur de votre choix, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="02987-132">Expand **Triggers**, right-click the trigger you want, and then click **Modify**.</span></span> <span data-ttu-id="02987-133">La définition du déclencheur DML s'affiche dans la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="02987-133">The definition of the DML trigger appears in the query window.</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="02987-134">Pour afficher les dépendances d'un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="02987-134">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="02987-135">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="02987-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="02987-136">Développez la base de données choisie, développez **Tables**, puis développez la table qui contient le déclencheur et ses dépendances que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="02987-136">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger and its dependencies that you want to view.</span></span>  
  
3.  <span data-ttu-id="02987-137">Développez **Déclencheurs**, cliquez avec le bouton droit sur le déclencheur de votre choix, puis cliquez sur **Afficher les dépendances**.</span><span class="sxs-lookup"><span data-stu-id="02987-137">Expand **Triggers**, right-click the trigger you want, and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="02987-138">Dans la fenêtre **Dépendances d’objets**, sélectionnez **Objets dépendants de \<DML trigger name>** pour afficher les objets qui dépendent du déclencheur DML.</span><span class="sxs-lookup"><span data-stu-id="02987-138">In the **Object Dependencies** window, to view the objects that depend on the DML trigger, select **Objects that depend on \<DML trigger name>**.</span></span> <span data-ttu-id="02987-139">Les objets apparaissent dans la zone **Dépendances** .</span><span class="sxs-lookup"><span data-stu-id="02987-139">The objects appear in the **Dependencies** area.</span></span>  
  
     <span data-ttu-id="02987-140">Pour afficher les objets dont dépend le déclencheur DML, sélectionnez **Objets dont dépend \<DML trigger name>** .</span><span class="sxs-lookup"><span data-stu-id="02987-140">To view the objects on which the DML depends, select **Objects on which \<DML trigger name> depends**.</span></span> <span data-ttu-id="02987-141">Les objets apparaissent dans la zone **Dépendances** .</span><span class="sxs-lookup"><span data-stu-id="02987-141">The objects appear in the **Dependencies** area.</span></span> <span data-ttu-id="02987-142">Développez chaque nœud pour voir tous les objets.</span><span class="sxs-lookup"><span data-stu-id="02987-142">Expand each node to see all the objects.</span></span>  
  
5.  <span data-ttu-id="02987-143">Pour obtenir des informations sur un objet qui apparaît dans la zone **Dépendances** , cliquez sur l'objet.</span><span class="sxs-lookup"><span data-stu-id="02987-143">To obtain information about an object that appears in the **Dependencies** area, click the object.</span></span> <span data-ttu-id="02987-144">Dans le champ **Objet sélectionné** , les informations sont fournies dans les zones **Nom**, **Type**et **Type de dépendance** .</span><span class="sxs-lookup"><span data-stu-id="02987-144">In the **Selected object** field, information is provided in the **Name**, **Type**, and **Dependency type** boxes.</span></span>  
  
6.  <span data-ttu-id="02987-145">Pour fermer la fenêtre **Dépendances d'objet** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="02987-145">To close the **Object Dependencies** window, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="02987-146">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="02987-146">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="02987-147">Pour voir la définition d'un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="02987-147">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="02987-148">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02987-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="02987-149">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="02987-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="02987-150">Copiez et collez l'un des exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="02987-150">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="02987-151">Chaque exemple montre comment afficher la définition du déclencheur `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="02987-151">Each example shows how you can view the definition of the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT definition   
FROM sys.sql_modules  
WHERE object_id = OBJECT_ID(N'Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECT_DEFINITION (OBJECT_ID(N'Person.iuPerson')) AS ObjectDefinition;   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
EXEC sp_helptext 'Person.iuPerson'  
GO  
  
```  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="02987-152">Pour afficher les dépendances d'un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="02987-152">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="02987-153">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02987-153">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="02987-154">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="02987-154">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="02987-155">Copiez et collez l'un des exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="02987-155">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="02987-156">Chaque exemple montre comment afficher les dépendances du déclencheur `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="02987-156">Each example shows how you can view the dependencies of `iuPerson` trigger.</span></span>  
  
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
WHERE referencing_id = OBJECT_ID(N'Person.iuPerson');   
GO  
  
```  
  
#### <a name="to-view-information-about-dml-triggers-in-the-database"></a><span data-ttu-id="02987-157">Pour afficher les informations sur les déclencheurs DML dans la base de données</span><span class="sxs-lookup"><span data-stu-id="02987-157">To view information about DML triggers in the database</span></span>  
  
1.  <span data-ttu-id="02987-158">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02987-158">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="02987-159">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="02987-159">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="02987-160">Copiez et collez l'un des exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="02987-160">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="02987-161">Chaque exemple montre comment afficher des informations sur les déclencheurs DML (`TR`) dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="02987-161">Each example shows how you can view information about DML triggers (`TR`) in the database.</span></span>  
  
```  
USE AdventureWorks2012;   
GO  
SELECT  name, parent_id, create_date, modify_date, is_instead_of_trigger  
FROM sys.triggers  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT  name, object_id, schema_id, parent_object_id, type_desc, create_date, modify_date, is_published  
FROM sys.objects  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECTPROPERTY(OBJECT_ID(N'Person.iuPerson'), 'ExecIsInsteadOfTrigger');   
GO  
  
```  
  
#### <a name="to-view-information-about-events-that-fire-a-dml-trigger"></a><span data-ttu-id="02987-162">Pour afficher les informations sur les événements qui activent un déclencheur DML</span><span class="sxs-lookup"><span data-stu-id="02987-162">To view information about events that fire a DML trigger</span></span>  
  
1.  <span data-ttu-id="02987-163">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02987-163">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="02987-164">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="02987-164">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="02987-165">Copiez et collez l'un des exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="02987-165">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="02987-166">Chaque exemple montre comment afficher les événements qui déclenchent le déclencheur `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="02987-166">Each example shows how you can view the events that fire the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT object_id, type, type_desc, is_trigger_event, event_group_type, event_group_type_desc   
FROM sys.events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO   
SELECT object_id, type,is_first, is_last  
FROM sys.trigger_events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="02987-167">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02987-167">See Also</span></span>  
 <span data-ttu-id="02987-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="02987-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="02987-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="02987-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="02987-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="02987-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="02987-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="02987-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="02987-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="02987-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="02987-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="02987-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="02987-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="02987-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="02987-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="02987-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="02987-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="02987-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="02987-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="02987-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="02987-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
  
