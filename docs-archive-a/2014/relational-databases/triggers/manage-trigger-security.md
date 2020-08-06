---
title: Gérer la sécurité des déclencheurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], security
ms.assetid: e94720a8-a3a2-4364-b0a3-bbe86e3ce4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: fdc176dcad50c3bf28f058c3724a01267975bfc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613872"
---
# <a name="manage-trigger-security"></a><span data-ttu-id="3e6d5-102">Gérer la sécurité des déclencheurs</span><span class="sxs-lookup"><span data-stu-id="3e6d5-102">Manage Trigger Security</span></span>
  <span data-ttu-id="3e6d5-103">Par défaut, les déclencheurs DML et DDL s'exécutent dans le contexte de l'utilisateur ayant appelé le déclencheur.</span><span class="sxs-lookup"><span data-stu-id="3e6d5-103">By default, both DML and DDL triggers execute under the context of the user that calls the trigger.</span></span> <span data-ttu-id="3e6d5-104">L'appelant d'un déclencheur correspond à l'utilisateur exécutant l'instruction qui provoque l'activation du déclencheur.</span><span class="sxs-lookup"><span data-stu-id="3e6d5-104">The caller of a trigger is the user that executes the statement that causes the trigger to run.</span></span> <span data-ttu-id="3e6d5-105">Par exemple, si l’utilisatrice **Mary** exécute une instruction DELETE provoquant l’activation d’un déclencheur DML intitulé **DML_trigMary** , le code inclus dans **DML_trigMary** s’exécute dans le contexte des autorisations utilisateur associées à **Mary**.</span><span class="sxs-lookup"><span data-stu-id="3e6d5-105">For example, if user **Mary** executes a DELETE statement that causes DML trigger **DML_trigMary** to run, the code inside **DML_trigMary** executes in the context of the user privileges for **Mary**.</span></span> <span data-ttu-id="3e6d5-106">Ce comportement par défaut peut malheureusement être exploité par des utilisateurs mal intentionnés voulant introduire du code dangereux dans une base de données ou une instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="3e6d5-106">This default behavior can be exploited by users who want to introduce malicious code in the database or server instance.</span></span> <span data-ttu-id="3e6d5-107">Prenons pour exemple le déclencheur DDL suivant créé par l'utilisateur `JohnDoe`:</span><span class="sxs-lookup"><span data-stu-id="3e6d5-107">For example, the following DDL trigger is created by user `JohnDoe`:</span></span>  
  
 `CREATE TRIGGER DDL_trigJohnDoe`  
  
 `ON DATABASE`  
  
 `FOR ALTER_TABLE`  
  
 `AS`  
  
 `GRANT CONTROL SERVER TO JohnDoe ;`  
  
 `GO`  
  
 <span data-ttu-id="3e6d5-108">Ce que ce déclencheur provoque est l’attribution de l’autorisation `GRANT CONTROL SERVER` à **dès qu’un utilisateur autorisé à exécuter une instruction** , tel qu’un membre du rôle serveur fixe `ALTER TABLE` sysadmin `JohnDoe` , exécute une instruction `CONTROL SERVER` .</span><span class="sxs-lookup"><span data-stu-id="3e6d5-108">What this trigger means is that as soon as a user that has permission to execute a `GRANT CONTROL SERVER` statement, such as a member of the **sysadmin** fixed server role, executes an `ALTER TABLE` statement, `JohnDoe` is granted `CONTROL SERVER` permission.</span></span> <span data-ttu-id="3e6d5-109">En d'autres termes, même si `JohnDoe` ne peut pas s'accorder lui-même l'autorisation `CONTROL SERVER` , il a activé le code du déclencheur qui lui accorde cette autorisation pour qu'il s'exécute sous des privilèges promus.</span><span class="sxs-lookup"><span data-stu-id="3e6d5-109">In other words, although `JohnDoe` cannot grant `CONTROL SERVER` permission to himself, he enabled the trigger code that grants him this permission to execute under escalated privileges.</span></span> <span data-ttu-id="3e6d5-110">Aussi bien les déclencheurs DML que les déclencheurs DDL permettent ce type de menace de sécurité.</span><span class="sxs-lookup"><span data-stu-id="3e6d5-110">Both DML and DDL triggers are open to this kind of security threat.</span></span>  
  
## <a name="trigger-security-best-practices"></a><span data-ttu-id="3e6d5-111">Méthodes conseillées pour la sécurité liée aux déclencheurs</span><span class="sxs-lookup"><span data-stu-id="3e6d5-111">Trigger Security Best Practices</span></span>  
 <span data-ttu-id="3e6d5-112">Nous vous proposons les mesures suivantes pour éviter que du code de déclencheur s'exécute sous des privilèges promus :</span><span class="sxs-lookup"><span data-stu-id="3e6d5-112">You can take the following measures to prevent trigger code from executing under escalated privileges:</span></span>  
  
-   <span data-ttu-id="3e6d5-113">Prenez connaissance des déclencheurs DML et DDL existant dans la base de données et sur l’instance du serveur en interrogeant les vues de catalogue [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) et [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3e6d5-113">Be aware of the DML and DDL triggers that exist in the database and on the server instance by querying the [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) and [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) catalog views.</span></span> <span data-ttu-id="3e6d5-114">La requête suivante renvoie tous les déclencheurs DML de la base de données actuelle, tous les déclencheurs DDL au niveau de la base de données actuelle et tous les déclencheurs DDL de niveau serveur inclus dans l'instance du serveur :</span><span class="sxs-lookup"><span data-stu-id="3e6d5-114">The following query returns all DML and database-level DDL triggers in the current database, and all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    SELECT type, name, parent_class_desc FROM sys.triggers  
    UNION  
    SELECT type, name, parent_class_desc FROM sys.server_triggers ;  
    ```  
  
-   <span data-ttu-id="3e6d5-115">Utilisez [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) afin de désactiver les déclencheurs pouvant mettre en péril l’intégrité de la base de données ou du serveur si les déclencheurs s’exécutent sous des privilèges promus.</span><span class="sxs-lookup"><span data-stu-id="3e6d5-115">Use [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) to disable triggers that can harm the integrity of the database or server if the triggers execute under escalated privileges.</span></span> <span data-ttu-id="3e6d5-116">L'instruction suivante désactive tous les déclencheurs DDL de niveau base de données dans la base de données actuelle :</span><span class="sxs-lookup"><span data-stu-id="3e6d5-116">The following statement disables all database-level DDL triggers in the current database:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON DATABASE  
    ```  
  
     <span data-ttu-id="3e6d5-117">L'instruction suivante désactive tous les déclencheurs DDL de niveau serveur sur l'instance du serveur :</span><span class="sxs-lookup"><span data-stu-id="3e6d5-117">This statement disables all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON ALL SERVER  
    ```  
  
     <span data-ttu-id="3e6d5-118">Enfin, cette instruction désactive tous les déclencheurs DML de la base de données actuelle :</span><span class="sxs-lookup"><span data-stu-id="3e6d5-118">This statement disables all DML triggers in the current database:</span></span>  
  
    ```  
    DECLARE @schema_name sysname, @trigger_name sysname, @object_name sysname ;  
    DECLARE @sql nvarchar(max) ;  
    DECLARE trig_cur CURSOR FORWARD_ONLY READ_ONLY FOR  
        SELECT SCHEMA_NAME(schema_id) AS schema_name,  
            name AS trigger_name,  
            OBJECT_NAME(parent_object_id) as object_name  
        FROM sys.objects WHERE type in ('TR', 'TA') ;  
  
    OPEN trig_cur ;  
    FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        SELECT @sql = 'DISABLE TRIGGER ' + QUOTENAME(@schema_name) + '.'  
            + QUOTENAME(@trigger_name) +  
            ' ON ' + QUOTENAME(@schema_name) + '.'   
            + QUOTENAME(@object_name) + ' ; ' ;  
        EXEC (@sql) ;  
        FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
    END  
    GO  
  
    -- Verify triggers are disabled. Should return an empty result set.  
    SELECT * FROM sys.triggers WHERE is_disabled = 0 ;  
    GO  
  
    CLOSE trig_cur ;  
    DEALLOCATE trig_cur;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3e6d5-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e6d5-119">See Also</span></span>  
 <span data-ttu-id="3e6d5-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3e6d5-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="3e6d5-121">[Déclencheurs DML](../triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="3e6d5-121">[DML Triggers](../triggers/dml-triggers.md) </span></span>  
 [<span data-ttu-id="3e6d5-122">Déclencheurs DDL</span><span class="sxs-lookup"><span data-stu-id="3e6d5-122">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
