---
title: Afficher la définition d’une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], viewing
- definition of stored procedure
- viewing stored procedures
- displaying stored procedures
ms.assetid: 93318587-a0c5-4788-946f-3b5dc8372ea9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4da455d38f984b08ee1f396f26cd4cc85411be92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605328"
---
# <a name="view-the-definition-of-a-stored-procedure"></a><span data-ttu-id="89a6b-102">Afficher la définition d'une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="89a6b-102">View the Definition of a Stored Procedure</span></span>
    
##  <a name="you-can-view-the-definition-of-a-stored-procedure-in-ssmanstudiofull-using-object-explorer-menu-options-or-in-the-query-editor-using-tsql-this-topic-describes-how-to-view-the-definition-of-procedure-in-object-explorer-and-by-using-a-system-stored-procedure-system-function-and-object-catalog-view-in-the-query-editor"></a><a name="Top"></a><span data-ttu-id="89a6b-103">Vous pouvez afficher la définition d’une procédure stockée dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] à l’aide des options du menu de l’Explorateur d’objets ou dans l’éditeur de requête à l’aide de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="89a6b-103">You can view the definition of a stored procedure in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or in the Query Editor using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="89a6b-104">Cette rubrique décrit comment afficher la définition de la procédure dans l'Explorateur d'objets et en utilisant une procédure stockée système, une fonction système et un affichage catalogue d'objets dans l'éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="89a6b-104">This topic describes how to view the definition of procedure in Object Explorer and by using a system stored procedure, system function, and object catalog view in the Query Editor.</span></span>  
  
-   <span data-ttu-id="89a6b-105">**Avant de commencer :**  [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="89a6b-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="89a6b-106">**Pour afficher la définition d'une procédure, à l'aide de :**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="89a6b-106">**To view the definition of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="89a6b-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="89a6b-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="89a6b-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="89a6b-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="89a6b-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="89a6b-109">Permissions</span></span>  
 <span data-ttu-id="89a6b-110">Procédure stockée système : `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="89a6b-110">System Stored Procedure: `sp_helptext`</span></span>  
 <span data-ttu-id="89a6b-111">Nécessite l'appartenance au rôle **public** .</span><span class="sxs-lookup"><span data-stu-id="89a6b-111">Requires membership in the **public** role.</span></span> <span data-ttu-id="89a6b-112">Les définitions de l'objet système sont visibles publiquement.</span><span class="sxs-lookup"><span data-stu-id="89a6b-112">System object definitions are publicly visible.</span></span> <span data-ttu-id="89a6b-113">La définition des objets utilisateur est visible par le propriétaire de l’objet ou les bénéficiaires de l’une des autorisations suivantes : ALTER, CONTROL, TAKE OWNERSHIP ou VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="89a6b-113">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span>  
  
 <span data-ttu-id="89a6b-114">Fonction système : `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="89a6b-114">System Function: `OBJECT_DEFINITION`</span></span>  
 <span data-ttu-id="89a6b-115">Les définitions de l'objet système sont visibles publiquement.</span><span class="sxs-lookup"><span data-stu-id="89a6b-115">System object definitions are publicly visible.</span></span> <span data-ttu-id="89a6b-116">La définition des objets utilisateur est visible par le propriétaire de l’objet ou les bénéficiaires de l’une des autorisations suivantes : ALTER, CONTROL, TAKE OWNERSHIP ou VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="89a6b-116">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="89a6b-117">Ces autorisations sont implicitement possédées par des membres des rôles de base de données fixes **db_owner**, **db_ddladmin**et **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="89a6b-117">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="89a6b-118">Affichage catalogue d'objets : `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="89a6b-118">Object Catalog View: `sys.sql_modules`</span></span>  
 <span data-ttu-id="89a6b-119">La visibilité des métadonnées dans les affichages catalogue est limitée aux éléments sécurisables qu'un utilisateur détient ou pour lesquels des autorisations lui ont été accordées.</span><span class="sxs-lookup"><span data-stu-id="89a6b-119">The visibility of the metadata in catalog views is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="89a6b-120">Pour plus d'informations, consultez [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="89a6b-120">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="how-to-view-the-definition-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="89a6b-121">Comment afficher la définition d'une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="89a6b-121">How to View the Definition of a Stored Procedure</span></span>  
 <span data-ttu-id="89a6b-122">Vous pouvez utiliser l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="89a6b-122">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="89a6b-123">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="89a6b-123">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="89a6b-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="89a6b-124">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="89a6b-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="89a6b-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="89a6b-126">**Pour afficher la définition d'une procédure dans l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="89a6b-126">**To view the definition a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="89a6b-127">Dans l'Explorateur d'objets, connectez-vous à une instance de [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="89a6b-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="89a6b-128">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure, puis développez **Programmabilité**.</span><span class="sxs-lookup"><span data-stu-id="89a6b-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="89a6b-129">Développez **Procédures stockées**, cliquez avec le bouton de droite sur la procédure, puis cliquez sur **Script de procédure stockée en tant que**, puis cliquez sur l'une des options suivantes : **Créer dans**, **Modifier dans** ou **Déposer et créer dans**.</span><span class="sxs-lookup"><span data-stu-id="89a6b-129">Expand **Stored Procedures**, right-click the procedure and then click **Script Stored Procedure as**, and then click one of the following: **Create To**, **Alter To**, or **Drop and Create To**.</span></span>  
  
4.  <span data-ttu-id="89a6b-130">Sélectionnez **Nouvelle fenêtre d’éditeur de requête**.</span><span class="sxs-lookup"><span data-stu-id="89a6b-130">Select **New Query Editor Window**.</span></span> <span data-ttu-id="89a6b-131">Cette action affiche la définition de la procédure.</span><span class="sxs-lookup"><span data-stu-id="89a6b-131">This will display the procedure definition.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="89a6b-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="89a6b-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="89a6b-133">**Pour afficher la définition d'une procédure dans l'éditeur de requête**</span><span class="sxs-lookup"><span data-stu-id="89a6b-133">**To view the definition of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="89a6b-134">Procédure stockée système : `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="89a6b-134">System Stored Procedure: `sp_helptext`</span></span>  
 1.  <span data-ttu-id="89a6b-135">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89a6b-135">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="89a6b-136">Dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="89a6b-136">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="89a6b-137">Dans la fenêtre de requête, entrez l'instruction suivante qui utilise la procédure stockée système `sp_helptext`.</span><span class="sxs-lookup"><span data-stu-id="89a6b-137">In the query window, enter the following statement that uses the `sp_helptext` system stored procedure.</span></span> <span data-ttu-id="89a6b-138">Modifiez le nom de la base de données et celui de la procédure stockée pour faire référence à la base de données et à la procédure stockée de votre choix.</span><span class="sxs-lookup"><span data-stu-id="89a6b-138">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_helptext N'AdventureWorks2012.dbo.uspLogError';  
    ```  
  
 <span data-ttu-id="89a6b-139">Fonction système : `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="89a6b-139">System Function: `OBJECT_DEFINITION`</span></span>  
 1.  <span data-ttu-id="89a6b-140">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89a6b-140">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="89a6b-141">Dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="89a6b-141">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="89a6b-142">Dans la fenêtre de requête, entrez les instructions suivantes qui utilisent la fonction système `OBJECT_DEFINITION`.</span><span class="sxs-lookup"><span data-stu-id="89a6b-142">In the query window, enter the following statements that use the `OBJECT_DEFINITION` system function.</span></span> <span data-ttu-id="89a6b-143">Modifiez le nom de la base de données et celui de la procédure stockée pour faire référence à la base de données et à la procédure stockée de votre choix.</span><span class="sxs-lookup"><span data-stu-id="89a6b-143">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
 <span data-ttu-id="89a6b-144">Affichage catalogue d'objets : `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="89a6b-144">Object Catalog View: `sys.sql_modules`</span></span>  
 1.  <span data-ttu-id="89a6b-145">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89a6b-145">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="89a6b-146">Dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="89a6b-146">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="89a6b-147">Dans la fenêtre de requête, entrez les instructions suivantes qui utilisent l'affichage catalogue `sys.sql_modules`.</span><span class="sxs-lookup"><span data-stu-id="89a6b-147">In the query window, enter the following statements that use the `sys.sql_modules` catalog view.</span></span> <span data-ttu-id="89a6b-148">Modifiez le nom de la base de données et celui de la procédure stockée pour faire référence à la base de données et à la procédure stockée de votre choix.</span><span class="sxs-lookup"><span data-stu-id="89a6b-148">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition  
    FROM sys.sql_modules  
    WHERE object_id = (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="89a6b-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89a6b-149">See Also</span></span>  
 <span data-ttu-id="89a6b-150">[Créer une procédure stockée](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="89a6b-150">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="89a6b-151">[Modifier une procédure stockée](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="89a6b-151">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="89a6b-152">[Supprimer une procédure stockée](delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="89a6b-152">[Delete a Stored Procedure](delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="89a6b-153">[Renommer une procédure stockée](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="89a6b-153">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="89a6b-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="89a6b-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span></span>  
 <span data-ttu-id="89a6b-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="89a6b-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="89a6b-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="89a6b-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span></span>  
 [<span data-ttu-id="89a6b-157">OBJECT_ID &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="89a6b-157">OBJECT_ID &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-id-transact-sql)  
  
  
