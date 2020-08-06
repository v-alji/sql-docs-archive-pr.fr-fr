---
title: Accorder des autorisations sur une procédure stockée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], permissions
ms.assetid: a7d15816-a788-4099-ad91-dc4b26618299
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23ea130b9d2033128adc99413c053d66936e3ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610523"
---
# <a name="grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="5ec62-102">Accorder des autorisations sur une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="5ec62-102">Grant Permissions on a Stored Procedure</span></span>
  <span data-ttu-id="5ec62-103">Cette rubrique explique comment accorder des autorisations sur une procédure stockée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en utilisant [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ec62-103">This topic describes how to grant permissions on a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5ec62-104">Les autorisations peuvent être accordées à un utilisateur existant, à un rôle de base de données ou à un rôle d'application dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5ec62-104">Permissions can be granted to an existing user, database role, or application role in the database.</span></span>  
  
 <span data-ttu-id="5ec62-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5ec62-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5ec62-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5ec62-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5ec62-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5ec62-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5ec62-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5ec62-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5ec62-109">**Pour accorder des autorisations sur une procédure stockée à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="5ec62-109">**To grant permissions on a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="5ec62-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5ec62-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5ec62-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5ec62-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5ec62-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5ec62-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5ec62-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5ec62-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5ec62-114">Vous ne pouvez pas utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour accorder des autorisations sur des procédures ou des fonctions système.</span><span class="sxs-lookup"><span data-stu-id="5ec62-114">You cannot use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to grant permissions on system procedures or system functions.</span></span> <span data-ttu-id="5ec62-115">Utilisez les [Accords d'autorisations sur objet](/sql/t-sql/statements/grant-object-permissions-transact-sql) à la place.</span><span class="sxs-lookup"><span data-stu-id="5ec62-115">Use [GRANT Object Permissions](/sql/t-sql/statements/grant-object-permissions-transact-sql) instead.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5ec62-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5ec62-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5ec62-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5ec62-117">Permissions</span></span>  
 <span data-ttu-id="5ec62-118">Le fournisseur d'autorisations (ou le principal spécifié avec l'option AS) doit posséder l'autorisation elle-même avec l'option GRANT OPTION ou une autorisation plus élevée qui implique l'autorisation accordée.</span><span class="sxs-lookup"><span data-stu-id="5ec62-118">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION, or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="5ec62-119">Exige l'autorisation ALTER sur le schéma auquel appartient la procédure ou l'autorisation CONTROL sur la procédure.</span><span class="sxs-lookup"><span data-stu-id="5ec62-119">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span> <span data-ttu-id="5ec62-120">Pour plus d’informations, consultez [Octroi d’autorisations d’objet &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5ec62-120">For more information, see [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5ec62-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5ec62-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="5ec62-122">Pour accorder des autorisations sur une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="5ec62-122">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="5ec62-123">Dans l'Explorateur d'objets, connectez-vous à une instance de [!INCLUDE[ssDE](../../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="5ec62-123">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5ec62-124">Développez **Bases de données**, développez la base de données à laquelle appartient la procédure, puis développez **Programmabilité**.</span><span class="sxs-lookup"><span data-stu-id="5ec62-124">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="5ec62-125">Développez **Procédures stockées**, cliquez avec le bouton droit sur la procédure sur laquelle vous voulez accorder des autorisations, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5ec62-125">Expand **Stored Procedures**, right-click the procedure to grant permissions on, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="5ec62-126">Dans **Propriétés de la procédure stockée**, sélectionnez la page **Autorisations** .</span><span class="sxs-lookup"><span data-stu-id="5ec62-126">From **Stored Procedure Properties**, select the **Permissions** page.</span></span>  
  
5.  <span data-ttu-id="5ec62-127">Pour accorder des autorisations à un utilisateur, à un rôle de base de données ou à un rôle d'application, cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="5ec62-127">To grant permissions to a user, database role, or application role, click **Search**.</span></span>  
  
6.  <span data-ttu-id="5ec62-128">Dans **Sélectionner des utilisateurs ou des rôles**, cliquez sur **Types d'objets** pour ajouter ou désactiver les utilisateurs et les rôles de votre choix.</span><span class="sxs-lookup"><span data-stu-id="5ec62-128">In **Select Users or Roles**, click **Object Types** to add or clear the users and roles you want.</span></span>  
  
7.  <span data-ttu-id="5ec62-129">Cliquez sur **Parcourir** pour afficher la liste des utilisateurs ou des rôles.</span><span class="sxs-lookup"><span data-stu-id="5ec62-129">Click **Browse** to display the list of users or roles.</span></span> <span data-ttu-id="5ec62-130">Sélectionnez les utilisateurs ou les rôles auxquels les autorisations doivent être accordées.</span><span class="sxs-lookup"><span data-stu-id="5ec62-130">Select the users or roles to whom permissions should be granted.</span></span>  
  
8.  <span data-ttu-id="5ec62-131">Dans la grille **Autorisations explicites** , sélectionnez les autorisations à accorder à l'utilisateur ou au rôle spécifiés.</span><span class="sxs-lookup"><span data-stu-id="5ec62-131">In the **Explicit Permissions** grid, select the permissions to grant to the specified user or role.</span></span> <span data-ttu-id="5ec62-132">Pour obtenir une description des autorisations, consultez [Autorisations &#40;moteur de base de données&#41;](../security/permissions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="5ec62-132">For a description of the permissions, see [Permissions &#40;Database Engine&#41;](../security/permissions-database-engine.md).</span></span>  
  
 <span data-ttu-id="5ec62-133">Sélectionner **Accorder** indique que le bénéficiaire recevra l'autorisation spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5ec62-133">Selecting **Grant** indicates the grantee will be given the specified permission.</span></span> <span data-ttu-id="5ec62-134">Sélectionner **Accorder avec** indique que le bénéficiaire de l'autorisation a également la possibilité d'accorder l'autorisation spécifiée à d'autres principaux.</span><span class="sxs-lookup"><span data-stu-id="5ec62-134">Selecting **Grant With** indicates that the grantee will also be able to grant the specified permission to other principals.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5ec62-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5ec62-135">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="5ec62-136">Pour accorder des autorisations sur une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="5ec62-136">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="5ec62-137">Connectez-vous au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ec62-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5ec62-138">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5ec62-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5ec62-139">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5ec62-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5ec62-140">Dans cet exemple, l'autorisation `EXECUTE` sur la procédure stockée `HumanResources.uspUpdateEmployeeHireInfo` est accordée à un rôle d'application nommé `Recruiting11`.</span><span class="sxs-lookup"><span data-stu-id="5ec62-140">This example grants `EXECUTE` permission on the stored procedure `HumanResources.uspUpdateEmployeeHireInfo` to an application role named `Recruiting11`.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
    TO Recruiting11;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ec62-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ec62-141">See Also</span></span>  
 <span data-ttu-id="5ec62-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5ec62-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span></span>  
 <span data-ttu-id="5ec62-143">[GRANT – octroi d’autorisations d’objet &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5ec62-143">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="5ec62-144">[Créer une procédure stockée](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5ec62-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="5ec62-145">[Modifier une procédure stockée](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5ec62-145">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="5ec62-146">[Supprimer une procédure stockée](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="5ec62-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="5ec62-147">Renommer une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="5ec62-147">Rename a Stored Procedure</span></span>](rename-a-stored-procedure.md)  
  
  
