---
title: Exécuter une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.executeprocedure.f1
- sql12.swb.executeprocedure.general.f1
helpviewer_keywords:
- stored procedures [SQL Server], parameters
- extended stored procedures [SQL Server], executing
- system stored procedures [SQL Server], executing
- stored procedures [SQL Server], executing
- user-defined stored procedures [SQL Server]
ms.assetid: a0b1337d-2059-4872-8c62-3f967d8b170f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c679ba7af3ac9f60d312b33c0346e50687387476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613355"
---
# <a name="execute-a-stored-procedure"></a><span data-ttu-id="618fa-102">Exécuter une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="618fa-102">Execute a Stored Procedure</span></span>
  <span data-ttu-id="618fa-103">Cette rubrique explique comment exécuter une procédure stockée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="618fa-103">This topic describes how to execute a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="618fa-104">Il existe deux façons différentes d'exécuter une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="618fa-104">There are two different ways to execute a stored procedure.</span></span> <span data-ttu-id="618fa-105">La première approche, et aussi la plus courante, est qu'une application ou un utilisateur appelle la procédure.</span><span class="sxs-lookup"><span data-stu-id="618fa-105">The first and most common approach is for an application or user to call the procedure.</span></span> <span data-ttu-id="618fa-106">La deuxième méthode consiste à définir la procédure pour qu'elle s'exécute automatiquement lorsqu'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] démarre.</span><span class="sxs-lookup"><span data-stu-id="618fa-106">The second approach is to set the procedure to run automatically when an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="618fa-107">Lorsqu'une procédure est appelée par une application ou un utilisateur, le mot clé [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE ou EXEC est explicitement établi dans l'appel.</span><span class="sxs-lookup"><span data-stu-id="618fa-107">When a procedure is called by an application or user, the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE or EXEC keyword is explicitly stated in the call.</span></span> <span data-ttu-id="618fa-108">Sinon, la procédure peut être appelée et exécutée sans le mot clé si elle est la première instruction dans le traitement [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="618fa-108">Alternatively, the procedure can be called and executed without the keyword if the procedure is the first statement in the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch.</span></span>  
  
 <span data-ttu-id="618fa-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="618fa-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="618fa-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="618fa-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="618fa-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="618fa-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="618fa-112">Recommandations</span><span class="sxs-lookup"><span data-stu-id="618fa-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="618fa-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="618fa-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="618fa-114">**Pour exécuter une procédure stockée à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="618fa-114">**To execute a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="618fa-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="618fa-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="618fa-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="618fa-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="618fa-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="618fa-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="618fa-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="618fa-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="618fa-119">Le classement de la base de données d'appel est utilisé pour mettre en correspondance les noms des procédures système.</span><span class="sxs-lookup"><span data-stu-id="618fa-119">The calling database collation is used when matching system procedure names.</span></span> <span data-ttu-id="618fa-120">Par conséquent, utilisez systématiquement la casse exacte des noms des procédures système dans vos appels de procédure.</span><span class="sxs-lookup"><span data-stu-id="618fa-120">Therefore, always use the exact case of system procedure names in procedure calls.</span></span> <span data-ttu-id="618fa-121">Par exemple, le code suivant ne fonctionnera pas s'il est exécuté dans le contexte d'une base de données dotée d'un classement qui respecte la casse :</span><span class="sxs-lookup"><span data-stu-id="618fa-121">For example, this code will fail if it is executed in the context of a database that has a case-sensitive collation:</span></span>  
  
    ```sql  
    EXEC SP_heLP; -- Will fail to resolve because SP_heLP does not equal sp_help  
    ```  
  
     <span data-ttu-id="618fa-122">Pour afficher les noms exacts des procédures système, interrogez les affichages catalogue [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) et [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="618fa-122">To display the exact system procedure names, query the [sys.system_objects](/sql/relational-databases/system-catalog-views/sys-system-objects-transact-sql) and [sys.system_parameters](/sql/relational-databases/system-catalog-views/sys-system-parameters-transact-sql) catalog views.</span></span>  
  
-   <span data-ttu-id="618fa-123">Si une procédure définie par l'utilisateur a le même nom qu'une procédure système, elle peut ne jamais s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="618fa-123">If a user-defined procedure has the same name as a system procedure, the user-defined procedure might not ever execute.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="618fa-124">Recommandations</span><span class="sxs-lookup"><span data-stu-id="618fa-124">Recommendations</span></span>  
  
-   <span data-ttu-id="618fa-125">Exécution de procédures stockées système</span><span class="sxs-lookup"><span data-stu-id="618fa-125">Executing System Stored Procedures</span></span>  
  
     <span data-ttu-id="618fa-126">Les procédures système commencent par le préfixe **sp_** .</span><span class="sxs-lookup"><span data-stu-id="618fa-126">System procedures begin with the prefix **sp_**.</span></span> <span data-ttu-id="618fa-127">Étant donné qu'elles figurent logiquement dans toutes les bases de données d'utilisateur et les bases de données définies par le système, elles peuvent être exécutés à partir de n'importe quelle base de données sans devoir qualifier entièrement le nom de la procédure.</span><span class="sxs-lookup"><span data-stu-id="618fa-127">Because they logically appear in all user- and system- defined databases, they can be executed from any database without having to fully quality the procedure name.</span></span> <span data-ttu-id="618fa-128">Cependant, nous vous conseillons de qualifier tous les noms de procédures système à l’aide du nom de schéma **sys** pour éviter les conflits de nom.</span><span class="sxs-lookup"><span data-stu-id="618fa-128">However, we recommend schema-qualifying all system procedure names with the **sys** schema name to prevent name conflicts.</span></span> <span data-ttu-id="618fa-129">L'exemple suivant illustre la méthode recommandée pour l'appel d'une procédure système.</span><span class="sxs-lookup"><span data-stu-id="618fa-129">The following example demonstrates the recommended method of calling a system procedure.</span></span>  
  
    ```sql  
    EXEC sys.sp_who;  
    ```  
  
-   <span data-ttu-id="618fa-130">Exécution de procédures stockées définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="618fa-130">Executing User-defined Stored Procedures</span></span>  
  
     <span data-ttu-id="618fa-131">En exécutant une procédure définie par l'utilisateur, il est recommandé de qualifier le nom de la procédure avec le nom du schéma.</span><span class="sxs-lookup"><span data-stu-id="618fa-131">When executing a user-defined procedure, we recommend qualifying the procedure name with the schema name.</span></span> <span data-ttu-id="618fa-132">Cette pratique améliore légèrement les performances car le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] n'a pas à rechercher dans plusieurs schémas.</span><span class="sxs-lookup"><span data-stu-id="618fa-132">This practice gives a small performance boost because the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] does not have to search multiple schemas.</span></span> <span data-ttu-id="618fa-133">Elle évite également d'exécuter la procédure incorrecte si une base de données a des procédures de même nom dans plusieurs schémas.</span><span class="sxs-lookup"><span data-stu-id="618fa-133">It also prevents executing the wrong procedure if a database has procedures with the same name in multiple schemas.</span></span>  
  
     <span data-ttu-id="618fa-134">L'exemple suivant illustre la méthode recommandée pour l'exécution d'une procédure définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="618fa-134">The following example demonstrates the recommended method to execute a user-defined procedure.</span></span> <span data-ttu-id="618fa-135">Notez que la procédure accepte un paramètre d'entrée.</span><span class="sxs-lookup"><span data-stu-id="618fa-135">Notice that the procedure accepts one input parameter.</span></span> <span data-ttu-id="618fa-136">Pour plus d’informations sur la spécification des paramètres d’entrée et de sortie, consultez [Spécifier les paramètres](specify-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="618fa-136">For information about specifying input and output parameters, see [Specify Parameters](specify-parameters.md).</span></span>  
  
    ```sql  
    USE AdventureWorks2012;  
    GO  
    EXEC dbo.uspGetEmployeeManagers @BusinessEntityID = 50;  
    ```  
  
     <span data-ttu-id="618fa-137">-Ou-</span><span class="sxs-lookup"><span data-stu-id="618fa-137">-Or-</span></span>  
  
    ```sql  
    EXEC AdventureWorks2012.dbo.uspGetEmployeeManagers 50;  
    GO  
    ```  
  
     <span data-ttu-id="618fa-138">Si une procédure non qualifiée définie par l'utilisateur est spécifiée, le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] la recherche dans l'ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="618fa-138">If a nonqualified user-defined procedure is specified, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] searches for the procedure in the following order:</span></span>  
  
    1.  <span data-ttu-id="618fa-139">Schéma **sys** de la base de données active.</span><span class="sxs-lookup"><span data-stu-id="618fa-139">The **sys** schema of the current database.</span></span>  
  
    2.  <span data-ttu-id="618fa-140">Schéma par défaut de l'appelant s'il est exécuté dans un traitement ou en SQL dynamique,</span><span class="sxs-lookup"><span data-stu-id="618fa-140">The caller's default schema if it is executed in a batch or in dynamic SQL.</span></span> <span data-ttu-id="618fa-141">ou bien, si le nom non qualifié de la procédure apparaît dans le corps d'une autre définition de procédure, le schéma contenant cette autre procédure est recherché par la suite.</span><span class="sxs-lookup"><span data-stu-id="618fa-141">Or, if the nonqualified procedure name appears inside the body of another procedure definition, the schema that contains this other procedure is searched next.</span></span>  
  
    3.  <span data-ttu-id="618fa-142">Schéma **dbo** dans la base de données active.</span><span class="sxs-lookup"><span data-stu-id="618fa-142">The **dbo** schema in the current database.</span></span>  
  
-   <span data-ttu-id="618fa-143">Exécution automatique des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="618fa-143">Executing Stored Procedures Automatically</span></span>  
  
     <span data-ttu-id="618fa-144">Les procédures marquées pour l'exécution automatique sont exécutées à chaque fois que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] démarre et que la base de données **master** est récupérée pendant le processus de démarrage.</span><span class="sxs-lookup"><span data-stu-id="618fa-144">Procedures marked for automatic execution are executed every time [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] starts and the **master** database is recovered during that startup process.</span></span> <span data-ttu-id="618fa-145">Configurer des procédures pour qu'elles s'exécutent automatiquement peut être utile pour effectuer des opérations de maintenance de base de données ou pour exécuter les procédures en continu en tant que processus d'arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="618fa-145">Setting up procedures to execute automatically can be useful for performing database maintenance operations or for having procedures run continuously as background processes.</span></span> <span data-ttu-id="618fa-146">Cette solution revêt également de l'importance dans le cas de procédures exécutant des tâches système ou de maintenance dans **tempdb**, par exemple la création d'une table temporaire globale.</span><span class="sxs-lookup"><span data-stu-id="618fa-146">Another use for automatic execution is to have the procedure perform system or maintenance tasks in **tempdb**, such as creating a global temporary table.</span></span> <span data-ttu-id="618fa-147">De cette façon, la table temporaire existe toujours après que **tempdb** est recréée durant le démarrage de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="618fa-147">This makes sure that such a temporary table will always exist when **tempdb** is re-created during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
     <span data-ttu-id="618fa-148">Une procédure exécutée automatiquement opère avec les mêmes droits que les membres du rôle de serveur **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="618fa-148">A procedure that is automatically executed operates with the same permissions as members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="618fa-149">Les messages d'erreur produits par une procédure sont enregistrés dans le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="618fa-149">Any error messages generated by the procedure are written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
     <span data-ttu-id="618fa-150">Le nombre de procédures au démarrage est illimité, mais gardez à l'esprit que chacune utilise un thread de travail lors de son exécution.</span><span class="sxs-lookup"><span data-stu-id="618fa-150">There is no limit to the number of startup procedures you can have, but be aware that each consumes one worker thread while executing.</span></span> <span data-ttu-id="618fa-151">Si vous devez exécuter plusieurs procédures au démarrage mais si vous ne devez pas les exécuter de manière parallèle, utilisez comme procédure de démarrage une des procédures qui appellera les autres.</span><span class="sxs-lookup"><span data-stu-id="618fa-151">If you must execute multiple procedures at startup but do not need to execute them in parallel, make one procedure the startup procedure and have that procedure call the other procedures.</span></span> <span data-ttu-id="618fa-152">Cette démarche permet de n'utiliser qu'un seul thread de travail.</span><span class="sxs-lookup"><span data-stu-id="618fa-152">This uses only one worker thread.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="618fa-153">Une procédure en exécution automatique ne retourne pas de jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="618fa-153">Do not return any result sets from a procedure that is executed automatically.</span></span> <span data-ttu-id="618fa-154">En effet, la procédure est exécutée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et non par une application ou un utilisateur et il n'y a pas d'emplacement où envoyer le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="618fa-154">Because the procedure is being executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instead of an application or user, there is nowhere for the result sets to go.</span></span>  
  
-   <span data-ttu-id="618fa-155">Définition, désactivation et contrôle de l'exécution automatique</span><span class="sxs-lookup"><span data-stu-id="618fa-155">Setting, Clearing, and Controlling Automatic Execution</span></span>  
  
     <span data-ttu-id="618fa-156">Seul l’administrateur système (**sa**) peut marquer une procédure de sorte qu’elle s’exécute automatiquement.</span><span class="sxs-lookup"><span data-stu-id="618fa-156">Only the system administrator (**sa**) can mark a procedure to execute automatically.</span></span> <span data-ttu-id="618fa-157">En outre, la procédure doit se trouver dans la base de données **master** , être la propriété de **sa**et ne pas posséder de paramètres d'entrée ou de sortie.</span><span class="sxs-lookup"><span data-stu-id="618fa-157">In addition, the procedure must be in the **master** database, owned by **sa**, and cannot have input or output parameters.</span></span>  
  
     <span data-ttu-id="618fa-158">Utilisez [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) pour :</span><span class="sxs-lookup"><span data-stu-id="618fa-158">Use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to:</span></span>  
  
    1.  <span data-ttu-id="618fa-159">désigner une procédure existante comme procédure de démarrage ;</span><span class="sxs-lookup"><span data-stu-id="618fa-159">Designate an existing procedure as a startup procedure.</span></span>  
  
    2.  <span data-ttu-id="618fa-160">supprimer l'exécution automatique d'une procédure au démarrage de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="618fa-160">Stop a procedure from executing at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="618fa-161">Sécurité</span><span class="sxs-lookup"><span data-stu-id="618fa-161">Security</span></span>  
 <span data-ttu-id="618fa-162">Pour plus d’informations, consultez [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) et [Clause EXECUTE AS &#40;Transact-SQL& #41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="618fa-162">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql) and [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="618fa-163">Autorisations</span><span class="sxs-lookup"><span data-stu-id="618fa-163">Permissions</span></span>  
 <span data-ttu-id="618fa-164">Pour plus d’informations, consultez la section « Autorisations » dans [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="618fa-164">For more information, see the "Permissions" section in [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="618fa-165">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="618fa-165">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="618fa-166">Pour exécuter une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="618fa-166">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="618fa-167">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], développez cette instance, puis développez **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="618fa-167">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="618fa-168">Développez la base de données que vous souhaitez, développez **Programmabilité**, puis développez **Procédures stockées**.</span><span class="sxs-lookup"><span data-stu-id="618fa-168">Expand the database that you want, expand **Programmability**, and then expand **Stored Procedures**.</span></span>  
  
3.  <span data-ttu-id="618fa-169">Cliquez avec le bouton droit sur la procédure stockée définie par l’utilisateur à executer, puis cliquez sur **Exécuter la procédure stockée**.</span><span class="sxs-lookup"><span data-stu-id="618fa-169">Right-click the user-defined stored procedure that you want and click **Execute Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="618fa-170">Dans la boîte de dialogue **Exécuter la procédure** , entrez une valeur pour chaque paramètre et indiquez si le paramètre doit passer une valeur Null.</span><span class="sxs-lookup"><span data-stu-id="618fa-170">In the **Execute Procedure** dialog box, specify a value for each parameter and whether it should pass a null value.</span></span>  
  
     <span data-ttu-id="618fa-171">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="618fa-171">**Parameter**</span></span>  
     <span data-ttu-id="618fa-172">Indique le nom du paramètre.</span><span class="sxs-lookup"><span data-stu-id="618fa-172">Indicates the name of the parameter.</span></span>  
  
     <span data-ttu-id="618fa-173">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="618fa-173">**Data Type**</span></span>  
     <span data-ttu-id="618fa-174">Indique le type de données du paramètre.</span><span class="sxs-lookup"><span data-stu-id="618fa-174">Indicates the data type of the parameter.</span></span>  
  
     <span data-ttu-id="618fa-175">**Paramètre de sortie**</span><span class="sxs-lookup"><span data-stu-id="618fa-175">**Output Parameter**</span></span>  
     <span data-ttu-id="618fa-176">Indique si le paramètre est un paramètre de sortie.</span><span class="sxs-lookup"><span data-stu-id="618fa-176">Indicates if this is an output parameter.</span></span>  
  
     <span data-ttu-id="618fa-177">**Passer les valeurs de type NULL**</span><span class="sxs-lookup"><span data-stu-id="618fa-177">**Pass Null Value**</span></span>  
     <span data-ttu-id="618fa-178">Permet le passage d'une valeur NULL en tant que valeur du paramètre.</span><span class="sxs-lookup"><span data-stu-id="618fa-178">Pass a NULL as the value of the parameter.</span></span>  
  
     <span data-ttu-id="618fa-179">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="618fa-179">**Value**</span></span>  
     <span data-ttu-id="618fa-180">Tapez la valeur du paramètre lors de l'appel de la procédure.</span><span class="sxs-lookup"><span data-stu-id="618fa-180">Type the value for the parameter when calling the procedure.</span></span>  
  
5.  <span data-ttu-id="618fa-181">Pour exécuter la procédure stockée, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="618fa-181">To execute the stored procedure, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="618fa-182">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="618fa-182">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-stored-procedure"></a><span data-ttu-id="618fa-183">Pour exécuter une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="618fa-183">To execute a stored procedure</span></span>  
  
1.  <span data-ttu-id="618fa-184">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="618fa-184">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="618fa-185">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="618fa-185">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="618fa-186">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="618fa-186">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="618fa-187">Cet exemple montre comment exécuter une procédure stockée qui attend un seul paramètre.</span><span class="sxs-lookup"><span data-stu-id="618fa-187">This example shows how to execute a stored procedure that expects one parameter.</span></span> <span data-ttu-id="618fa-188">L'exemple exécute la procédure stockée `uspGetEmployeeManagers` avec la valeur  `6` spécifiée pour le paramètre `@EmployeeID` .</span><span class="sxs-lookup"><span data-stu-id="618fa-188">The example executes the `uspGetEmployeeManagers` stored procedure with the value  `6` specified as the `@EmployeeID` parameter.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC dbo.uspGetEmployeeManagers 6;  
GO  
```  
  
#### <a name="to-set-or-clear-a-procedure-for-executing-automatically"></a><span data-ttu-id="618fa-189">Pour valider ou désactiver l'exécution automatique d'une procédure</span><span class="sxs-lookup"><span data-stu-id="618fa-189">To set or clear a procedure for executing automatically</span></span>  
  
1.  <span data-ttu-id="618fa-190">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="618fa-190">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="618fa-191">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="618fa-191">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="618fa-192">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="618fa-192">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="618fa-193">Cet exemple montre comment utiliser [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) pour définir l’exécution automatique d’une procédure.</span><span class="sxs-lookup"><span data-stu-id="618fa-193">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to set a procedure for automatic execution.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionName = ] 'startup'   
    , @OptionValue = 'on';  
```  
  
#### <a name="to-stop-a-procedure-from-executing-automatically"></a><span data-ttu-id="618fa-194">Pour arrêter l'exécution automatique d'une procédure</span><span class="sxs-lookup"><span data-stu-id="618fa-194">To stop a procedure from executing automatically</span></span>  
  
1.  <span data-ttu-id="618fa-195">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="618fa-195">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="618fa-196">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="618fa-196">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="618fa-197">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="618fa-197">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="618fa-198">Cet exemple montre comment utiliser [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) pour arrêter l’exécution automatique d’une procédure.</span><span class="sxs-lookup"><span data-stu-id="618fa-198">This example shows how to use [sp_procoption](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql) to stop a procedure from executing automatically.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_procoption @ProcName = '<procedure name>'   
    , @OptionValue = 'off';  
```  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="618fa-199">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="618fa-199">Example (Transact-SQL)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="618fa-200">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="618fa-200">See Also</span></span>  
 <span data-ttu-id="618fa-201">[Spécifier les paramètres](specify-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="618fa-201">[Specify Parameters](specify-parameters.md) </span></span>  
 <span data-ttu-id="618fa-202">[Configurer l'option de configuration du serveur scan for startup procs](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="618fa-202">[Configure the scan for startup procs Server Configuration Option](../../database-engine/configure-windows/configure-the-scan-for-startup-procs-server-configuration-option.md) </span></span>  
 <span data-ttu-id="618fa-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="618fa-203">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="618fa-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="618fa-204">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="618fa-205">Procédures stockées &#40;moteur de base de données &#41;</span><span class="sxs-lookup"><span data-stu-id="618fa-205">Stored Procedures &#40;Database Engine&#41;</span></span>](stored-procedures-database-engine.md)  
  
  
