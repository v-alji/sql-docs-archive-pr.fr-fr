---
title: Créer une spécification de l’audit du serveur et de la base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlaudit.dbaudit.general.f1
helpviewer_keywords:
- audits [SQL Server], creating database specification
- database audit [SQL Server]
ms.assetid: 26ee85de-6e97-4318-b526-900924d96e62
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0cad01eae45d534f0f74911ce8f57827858cc920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700967"
---
# <a name="create-a-server-audit-and-database-audit-specification"></a><span data-ttu-id="7f3ae-102">Créer une spécification de l'audit du serveur et de la base de données</span><span class="sxs-lookup"><span data-stu-id="7f3ae-102">Create a Server Audit and Database Audit Specification</span></span>
  <span data-ttu-id="7f3ae-103">Cette rubrique explique comment créer un audit de serveur et une spécification d'audit de base de données dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3ae-103">This topic describes how to create a server audit and database audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7f3ae-104">L'*audit* d'une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou d'une base de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implique le suivi et l'enregistrement des événements qui se produisent sur le système.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="7f3ae-105">L’objet *Audit SQL Server* recueille une seule instance des actions et des groupes d’actions au niveau du serveur ou de la base de données à surveiller.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="7f3ae-106">L'audit s'effectue au niveau de l'instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f3ae-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="7f3ae-107">Vous pouvez exécuter plusieurs audits par instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f3ae-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="7f3ae-108">L’objet *Spécification d’audit de niveau base de données* appartient à un audit.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-108">The *Database-Level Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="7f3ae-109">Vous pouvez créer une spécification d'audit de base de données par base de données SQL Server et par audit.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-109">You can create one database audit specification per SQL Server database per audit.</span></span> <span data-ttu-id="7f3ae-110">Pour plus d’informations, consultez [SQL Server Audit &#40;moteur de base de données&#41;](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="7f3ae-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="7f3ae-111">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7f3ae-112">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7f3ae-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="7f3ae-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7f3ae-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7f3ae-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7f3ae-115">**Pour créer un audit de serveur et une spécification d'audit de base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-115">**To create a server audit and database audit specification, using:**</span></span>  
  
     [<span data-ttu-id="7f3ae-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7f3ae-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7f3ae-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7f3ae-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7f3ae-118">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7f3ae-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7f3ae-119">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="7f3ae-119">Limitations and Restrictions</span></span>  
 <span data-ttu-id="7f3ae-120">Les spécifications d'audit de base de données sont des objets non sécurisables qui résident dans une base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-120">Database audit specifications are non-securable objects that reside in a given database.</span></span> <span data-ttu-id="7f3ae-121">Lorsqu'une spécification d'audit de base de données est créée, elle se trouve dans un état désactivé.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-121">When a database audit specification is created, it is in a disabled state.</span></span>  
  
 <span data-ttu-id="7f3ae-122">Lorsque vous créez ou modifiez une spécification de l'audit de la base de données dans une base de données utilisateur, n'incluez pas d'actions d'audit sur des objets dans l'étendue du serveur, tels que les vues système.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-122">When you are creating or modifying a database audit specification in a user database, do not include audit actions on server-scope objects, such as the system views.</span></span> <span data-ttu-id="7f3ae-123">Sinon, l'audit est créé.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-123">If server-scoped objects are included, the audit will be created.</span></span> <span data-ttu-id="7f3ae-124">Toutefois, les objets dans l'étendue du serveur ne sont pas inclus, et aucune erreur n'est retournée.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-124">However, the server-scoped objects will not be included, and no error will be returned.</span></span> <span data-ttu-id="7f3ae-125">Pour auditer des objets dans l'étendue du serveur, utilisez une spécification de l'audit de la base de données dans la base de données MASTER.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-125">To audit server-scope objects, use a database audit specification in the master database.</span></span>  
  
 <span data-ttu-id="7f3ae-126">Les spécifications d'audit de base de données résident dans la base de données où elles sont créées, à l'exception de la base de données système `tempdb`.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-126">Database audit specifications reside in the database where they are created, with the exception of the `tempdb` system database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7f3ae-127">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7f3ae-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7f3ae-128">Autorisations</span><span class="sxs-lookup"><span data-stu-id="7f3ae-128">Permissions</span></span>  
  
-   <span data-ttu-id="7f3ae-129">Les utilisateurs disposant de l'autorisation ALTER ANY DATABASE AUDIT peuvent créer des spécifications d'audit de base de données et les lier à un audit quelconque.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-129">Users with the ALTER ANY DATABASE AUDIT permission can create database audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="7f3ae-130">Une fois qu’une spécification d’audit de la base de données est créée, elle peut être affichée par des principaux disposant des autorisations CONTROL SERVER, ALTER ANY DATABASE AUDIT ou du compte sysadmin.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-130">After a database audit specification is created, it can be viewed by principals with the CONTROL SERVER,  ALTER ANY DATABASE AUDIT permissions, or the sysadmin account.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7f3ae-131">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7f3ae-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="7f3ae-132">Pour créer un audit de serveur</span><span class="sxs-lookup"><span data-stu-id="7f3ae-132">To create a server audit</span></span>  
  
1.  <span data-ttu-id="7f3ae-133">Dans l'Explorateur d'objets, développez le dossier **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="7f3ae-133">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="7f3ae-134">Cliquez avec le bouton droit sur le dossier **audits** et sélectionnez **nouvel audit...**. Pour plus d’informations, consultez [créer un audit de serveur et une spécification d’audit de serveur](create-a-server-audit-and-server-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="7f3ae-134">Right-click the **Audits** folder and select **New Audit...**. For more information, see [Create a Server Audit and Server Audit Specification](create-a-server-audit-and-server-audit-specification.md).</span></span>  
  
3.  <span data-ttu-id="7f3ae-135">Lorsque vous avez fini de sélectionner les options, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-135">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="7f3ae-136">Pour créer une spécification d'audit de niveau base de données</span><span class="sxs-lookup"><span data-stu-id="7f3ae-136">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="7f3ae-137">Dans l'Explorateur d'objets, développez la base de données dans laquelle vous souhaitez créer une spécification d'audit.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-137">In Object Explorer, expand the database where you want to create an audit specification.</span></span>  
  
2.  <span data-ttu-id="7f3ae-138">Développez le dossier **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="7f3ae-138">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="7f3ae-139">Cliquez avec le bouton droit sur le dossier **spécifications de l’audit de la base de données** et sélectionnez **nouvelle spécification de l’audit de la base de données.**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-139">Right-click the **Database Audit Specifications** folder and select **New Database Audit Specification...**.</span></span>  
  
     <span data-ttu-id="7f3ae-140">Les options suivantes sont disponibles dans la boîte de dialogue **Créer la spécification de l'audit de la base de données** .</span><span class="sxs-lookup"><span data-stu-id="7f3ae-140">The following options are available on the **Create Database Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="7f3ae-141">**Nom**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-141">**Name**</span></span>  
     <span data-ttu-id="7f3ae-142">Nom de la spécification de l'audit de la base de données.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-142">The name of the database audit specification.</span></span> <span data-ttu-id="7f3ae-143">Le nom est généré automatiquement lorsque vous créez une spécification d'audit du serveur, mais vous pouvez le modifier.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-143">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="7f3ae-144">**Audit**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-144">**Audit**</span></span>  
     <span data-ttu-id="7f3ae-145">Nom d'un audit de base de données existant.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-145">The name of an existing database audit.</span></span> <span data-ttu-id="7f3ae-146">Tapez le nom de l'audit ou sélectionnez-le dans la liste.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-146">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="7f3ae-147">**Type d'action de l'audit**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-147">**Audit Action Type**</span></span>  
     <span data-ttu-id="7f3ae-148">Spécifie les groupes d'actions d'audit de niveau base de données et les actions d'audit à capturer.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-148">Specifies the database-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="7f3ae-149">Pour obtenir la liste d’actions d’audit et de groupes d’actions d’audit de niveau base de données, ainsi qu’une description des événements qu’ils contiennent, consultez [Actions et groupes d’actions SQL Server Audit](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="7f3ae-149">For the list of database-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="7f3ae-150">**Schéma d'objet**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-150">**Object Schema**</span></span>  
     <span data-ttu-id="7f3ae-151">Affiche le schéma du **Nom de l’objet**spécifié.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-151">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="7f3ae-152">**Nom de l’objet**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-152">**Object Name**</span></span>  
     <span data-ttu-id="7f3ae-153">Nom de l'objet à auditer.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-153">The name of the object to audit.</span></span> <span data-ttu-id="7f3ae-154">Disponible uniquement pour les actions d'audit ; ne s'applique pas aux groupes d'audit.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-154">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="7f3ae-155">**Points de suspension (...)**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-155">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="7f3ae-156">Ouvre la boîte de dialogue **Sélectionner des objets** permettant de rechercher et sélectionner un objet disponible, en fonction du **Type d'action de l'audit**spécifié.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-156">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="7f3ae-157">**Nom principal**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-157">**Principal Name**</span></span>  
     <span data-ttu-id="7f3ae-158">Compte par lequel filtrer l'audit pour l'objet audité.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-158">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="7f3ae-159">**Points de suspension (...)**</span><span class="sxs-lookup"><span data-stu-id="7f3ae-159">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="7f3ae-160">Ouvre la boîte de dialogue **Sélectionner des objets** permettant de rechercher et sélectionner un objet disponible, en fonction du **Nom de l'objet**spécifié.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-160">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
4.  <span data-ttu-id="7f3ae-161">Lorsque vous avez fini de sélectionner l'option, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-161">When you are finished selecting option, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7f3ae-162">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7f3ae-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="7f3ae-163">Pour créer un audit de serveur</span><span class="sxs-lookup"><span data-stu-id="7f3ae-163">To create a server audit</span></span>  
  
1.  <span data-ttu-id="7f3ae-164">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3ae-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7f3ae-165">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7f3ae-166">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE master ;  
    GO  
    -- Create the server audit.   
    CREATE SERVER AUDIT Payrole_Security_Audit  
        TO FILE ( FILEPATH =   
    'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA' ) ;   
    GO  
    -- Enable the server audit.   
    ALTER SERVER AUDIT Payrole_Security_Audit   
    WITH (STATE = ON) ;  
    ```  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="7f3ae-167">Pour créer une spécification d'audit de niveau base de données</span><span class="sxs-lookup"><span data-stu-id="7f3ae-167">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="7f3ae-168">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f3ae-168">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7f3ae-169">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-169">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7f3ae-170">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-170">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7f3ae-171">L'exemple crée une spécification d'audit de base de données appelée `Audit_Pay_Tables` qui audite les instructions SELECT et INSERT par l'utilisateur `dbo` , pour la table `HumanResources.EmployeePayHistory` en fonction de l'audit de serveur défini précédemment.</span><span class="sxs-lookup"><span data-stu-id="7f3ae-171">The example creates a database audit specification called `Audit_Pay_Tables` that audits SELECT and INSERT statements by the `dbo` user, for the `HumanResources.EmployeePayHistory` table based on the server audit defined above.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    -- Create the database audit specification.   
    CREATE DATABASE AUDIT SPECIFICATION Audit_Pay_Tables  
    FOR SERVER AUDIT Payrole_Security_Audit  
    ADD (SELECT , INSERT  
         ON HumanResources.EmployeePayHistory BY dbo )   
    WITH (STATE = ON) ;   
    GO  
  
    ```  
  
 <span data-ttu-id="7f3ae-172">Pour plus d’informations, consultez [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) et [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7f3ae-172">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span></span>  
  
  
