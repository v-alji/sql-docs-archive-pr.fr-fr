---
title: Renommer une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], renaming
- renaming stored procedures
ms.assetid: 5d2e4c68-7e0b-4405-8919-f5b203e46770
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02e1acb528a32ef242e160e0ce5dd0267237c876
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615108"
---
# <a name="rename-a-stored-procedure"></a><span data-ttu-id="d2939-102">Renommer une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="d2939-102">Rename a Stored Procedure</span></span>
  <span data-ttu-id="d2939-103">Cette rubrique explique comment renommer une procédure stockée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2939-103">This topic describes how to rename a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d2939-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d2939-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d2939-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d2939-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d2939-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d2939-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d2939-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d2939-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d2939-108">**Pour renommer une procédure stockée à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="d2939-108">**To rename a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="d2939-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d2939-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d2939-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d2939-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d2939-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d2939-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d2939-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d2939-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d2939-113">Les noms des procédures doivent respecter les conventions concernant les [identificateurs](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d2939-113">Procedure names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="d2939-114">Le fait de renommer une procédure stockée ne modifie pas le nom de l’objet correspondant dans la colonne de définition de l’affichage catalogue **sys.sql_modules** .</span><span class="sxs-lookup"><span data-stu-id="d2939-114">Renaming a stored procedure will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="d2939-115">Par conséquent, nous vous recommandons de ne pas renommer ce type d'objet.</span><span class="sxs-lookup"><span data-stu-id="d2939-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="d2939-116">À la place, supprimez, puis recréez la procédure stockée avec son nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="d2939-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="d2939-117">La modification du nom ou de la définition d'une procédure peut entraîner l'échec de ses objets dépendants si ceux-ci n'ont pas été mis à jour pour refléter les modifications apportées à la procédure.</span><span class="sxs-lookup"><span data-stu-id="d2939-117">Changing the name or definition of a procedure can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the procedure.</span></span> <span data-ttu-id="d2939-118">Pour plus d’informations, consultez [Afficher les dépendances d’une procédure stockée](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="d2939-118">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d2939-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d2939-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d2939-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d2939-120">Permissions</span></span>  
 <span data-ttu-id="d2939-121">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="d2939-121">CREATE PROCEDURE</span></span>  
 <span data-ttu-id="d2939-122">Nécessite l’autorisation CREATE PROCEDURE dans la base de données et l’autorisation ALTER sur le schéma dans lequel la procédure est créée, ou nécessite l’appartenance au rôle de base de données fixe **db_ddladmin**.</span><span class="sxs-lookup"><span data-stu-id="d2939-122">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created, or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
 <span data-ttu-id="d2939-123">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="d2939-123">ALTER PROCEDURE</span></span>  
 <span data-ttu-id="d2939-124">Requiert l’autorisation ALTER sur la procédure ou l’appartenance au rôle de base de données fixe **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="d2939-124">Requires ALTER permission on the procedure or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d2939-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d2939-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="d2939-126">Pour renommer une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="d2939-126">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="d2939-127">Dans l'Explorateur d'objets, connectez-vous à une instance de [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="d2939-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d2939-128">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure, puis développez **Programmabilité**.</span><span class="sxs-lookup"><span data-stu-id="d2939-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="d2939-129">[Déterminez les dépendances de la procédure stockée](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="d2939-129">[Determine the dependencies of the stored procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
4.  <span data-ttu-id="d2939-130">Développez **Procédures stockées**, cliquez avec le bouton droit sur la procédure à renommer, puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="d2939-130">Expand **Stored Procedures**, right-click the procedure to rename, and then click **Rename**.</span></span>  
  
5.  <span data-ttu-id="d2939-131">Modifiez le nom de la procédure.</span><span class="sxs-lookup"><span data-stu-id="d2939-131">Modify the procedure name.</span></span>  
  
6.  <span data-ttu-id="d2939-132">Modifiez le nom de la procédure référencé dans tous les objets ou scripts dépendants.</span><span class="sxs-lookup"><span data-stu-id="d2939-132">Modify the procedure name referenced in any dependent objects or scripts.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d2939-133">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d2939-133">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="d2939-134">Pour renommer une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="d2939-134">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="d2939-135">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2939-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d2939-136">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d2939-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d2939-137">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d2939-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d2939-138">Cet exemple montre comment renommer une procédure en la supprimant puis en la recréant avec un nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="d2939-138">This example shows how to rename a procedure by dropping the procedure and re-creating the procedure with a new name.</span></span> <span data-ttu-id="d2939-139">Le premier exemple crée la procédure stockée `'HumanResources.uspGetAllEmployeesTest`.</span><span class="sxs-lookup"><span data-stu-id="d2939-139">The first example creates the stored procedure `'HumanResources.uspGetAllEmployeesTest`.</span></span> <span data-ttu-id="d2939-140">Le deuxième exemple renomme la procédure stockée en `HumanResources.uspEveryEmployeeTest`.</span><span class="sxs-lookup"><span data-stu-id="d2939-140">The second example renames the stored procedure to `HumanResources.uspEveryEmployeeTest`.</span></span>  
  
```sql  
--Create the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspGetAllEmployeesTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
  
--Rename the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspEveryEmployeeTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2939-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d2939-141">See Also</span></span>  
 <span data-ttu-id="d2939-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2939-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span></span>  
 <span data-ttu-id="d2939-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2939-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="d2939-144">[Créer une procédure stockée](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d2939-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="d2939-145">[Modifier une procédure stockée](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d2939-145">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="d2939-146">[Supprimer une procédure stockée](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d2939-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="d2939-147">[Afficher la définition d'une procédure stockée](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="d2939-147">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="d2939-148">Afficher les dépendances d’une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="d2939-148">View the Dependencies of a Stored Procedure</span></span>](view-the-dependencies-of-a-stored-procedure.md)  
  
  
