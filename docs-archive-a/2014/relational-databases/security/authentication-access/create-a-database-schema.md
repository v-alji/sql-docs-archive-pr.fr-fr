---
title: Créer un schéma de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.schemas.general.f1
helpviewer_keywords:
- creating schemas with Management Studio
- CREATE SCHEMA [Management Studio]
- database schemas
- schemas [SQL Server], creating
ms.assetid: ed2a5522-f4d2-4111-95a4-d3e1e5081739
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 3ac0c00768db6501c7d786c35758c1a9d75a5a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697770"
---
# <a name="create-a-database-schema"></a><span data-ttu-id="12e54-102">Créer un schéma de base de données</span><span class="sxs-lookup"><span data-stu-id="12e54-102">Create a Database Schema</span></span>
  <span data-ttu-id="12e54-103">Cette rubrique explique comment créer un schéma dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12e54-103">This topic describes how to create a schema in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="12e54-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="12e54-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="12e54-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="12e54-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="12e54-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="12e54-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="12e54-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="12e54-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="12e54-108">**Pour créer un schéma, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="12e54-108">**To create a schema, using:**</span></span>  
  
     [<span data-ttu-id="12e54-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="12e54-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="12e54-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="12e54-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="12e54-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="12e54-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="12e54-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="12e54-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="12e54-113">Le nouveau schéma appartient à l'un des principaux de base de données suivants : utilisateur de base de données, rôle de base de données ou rôle d'application.</span><span class="sxs-lookup"><span data-stu-id="12e54-113">The new schema is owned by one of the following database-level principals: database user, database role, or application role.</span></span> <span data-ttu-id="12e54-114">Les objets créés dans un schéma appartiennent au propriétaire du schéma. La valeur **principal_id** de ces objets est NULL dans **sys.objects**.</span><span class="sxs-lookup"><span data-stu-id="12e54-114">Objects created within a schema are owned by the owner of the schema, and have a NULL **principal_id** in **sys.objects**.</span></span> <span data-ttu-id="12e54-115">Il est possible de transférer la propriété des objets contenus dans le schéma à n'importe quel principal de base de données, mais le propriétaire du schéma conserve toujours l'autorisation CONTROL sur les objets dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="12e54-115">Ownership of schema-contained objects can be transferred to any database-level principal, but the schema owner always retains CONTROL permission on objects within the schema.</span></span>  
  
-   <span data-ttu-id="12e54-116">Lors de la création d'un objet de base de données, si vous spécifiez un principal de domaine valide (utilisateur ou groupe) comme propriétaire de l'objet, le principal du domaine est ajouté à la base de données en tant que schéma.</span><span class="sxs-lookup"><span data-stu-id="12e54-116">When creating a database object, if you specify a valid domain principal (user or group) as the object owner, the domain principal will be added to the database as a schema.</span></span> <span data-ttu-id="12e54-117">Le nouveau schéma appartiendra à ce principal de domaine.</span><span class="sxs-lookup"><span data-stu-id="12e54-117">The new schema will be owned by that domain principal.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="12e54-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="12e54-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="12e54-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="12e54-119">Permissions</span></span>  
  
-   <span data-ttu-id="12e54-120">Nécessite l'autorisation CREATE SCHEMA sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="12e54-120">Requires CREATE SCHEMA permission on the database.</span></span>  
  
-   <span data-ttu-id="12e54-121">Pour spécifier un autre utilisateur comme propriétaire du schéma à créer, l'appelant doit avoir l'autorisation IMPERSONATE sur cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="12e54-121">To specify another user as the owner of the schema being created, the caller must have IMPERSONATE permission on that user.</span></span> <span data-ttu-id="12e54-122">Si un rôle de base de données est spécifié en tant que propriétaire, l'appelant doit disposer de l'un des éléments suivants : appartenance au rôle ou autorisation ALTER pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="12e54-122">If a database role is specified as the owner, the caller must have one of the following: membership in the role or ALTER permission on the role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="12e54-123">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="12e54-123">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-schema"></a><span data-ttu-id="12e54-124">Pour créer un schéma</span><span class="sxs-lookup"><span data-stu-id="12e54-124">To create a schema</span></span>  
  
1.  <span data-ttu-id="12e54-125">Dans l'Explorateur d'objets, développez le dossier **Bases de données** .</span><span class="sxs-lookup"><span data-stu-id="12e54-125">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="12e54-126">Développez la base de données où créer le schéma de la base de données.</span><span class="sxs-lookup"><span data-stu-id="12e54-126">Expand the database in which to create the new database schema.</span></span>  
  
3.  <span data-ttu-id="12e54-127">Cliquez avec le bouton droit sur le dossier **Sécurité** , pointez sur **Nouveau**, puis sélectionnez **Schéma**.</span><span class="sxs-lookup"><span data-stu-id="12e54-127">Right-click the **Security** folder, point to **New**, and select **Schema**.</span></span>  
  
4.  <span data-ttu-id="12e54-128">Dans la boîte de dialogue **Schéma - Nouveau** , sur la page **Général** , entrez un nom pour le nouveau schéma dans la zone **Nom du schéma** .</span><span class="sxs-lookup"><span data-stu-id="12e54-128">In the **Schema - New** dialog box, on the **General** page, enter a name for the new schema in the **Schema name** box.</span></span>  
  
5.  <span data-ttu-id="12e54-129">Dans la zone **Propriétaire du schéma** , entrez le nom d'un utilisateur de base de données ou d'un rôle propriétaire du schéma.</span><span class="sxs-lookup"><span data-stu-id="12e54-129">In the **Schema owner** box, enter the name of a database user or role to own the schema.</span></span> <span data-ttu-id="12e54-130">Vous pouvez également cliquer sur **Rechercher** pour ouvrir la boîte de dialogue **Rechercher les rôles et les utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="12e54-130">Alternately, click **Search** to open the **Search Roles and Users** dialog box.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="12e54-131">Options supplémentaires</span><span class="sxs-lookup"><span data-stu-id="12e54-131">Additional Options</span></span>  
 <span data-ttu-id="12e54-132">La boîte de dialogue **Schéma- Nouveau** offre également des options sur deux pages supplémentaires : **Autorisations** et **Propriétés étendues**.</span><span class="sxs-lookup"><span data-stu-id="12e54-132">The **Schema- New** dialog box also offers options on two additional pages: **Permissions** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="12e54-133">La page **Autorisations** répertorie tous les éléments sécurisables possibles et les autorisations sur les éléments sécurisables qui peuvent être accordées à la connexion.</span><span class="sxs-lookup"><span data-stu-id="12e54-133">The **Permissions** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="12e54-134">La page **Propriétés étendues** vous permet d'ajouter des propriétés personnalisées aux utilisateurs de base de données.</span><span class="sxs-lookup"><span data-stu-id="12e54-134">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="12e54-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="12e54-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schema"></a><span data-ttu-id="12e54-136">Pour créer un schéma</span><span class="sxs-lookup"><span data-stu-id="12e54-136">To create a schema</span></span>  
  
1.  <span data-ttu-id="12e54-137">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12e54-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="12e54-138">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="12e54-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="12e54-139">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="12e54-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the schema Sprockets owned by Annik that contains table NineProngs.   
    -- The statement grants SELECT to Mandar and denies SELECT to Prasanna.  
  
    CREATE SCHEMA Sprockets AUTHORIZATION Annik  
        CREATE TABLE NineProngs (source int, cost int, partnumber int)  
        GRANT SELECT ON SCHEMA::Sprockets TO Mandar  
        DENY SELECT ON SCHEMA::Sprockets TO Prasanna;  
    GO  
    ```  
  
 <span data-ttu-id="12e54-140">Pour plus d’informations, consultez [CREATE SCHEMA &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="12e54-140">For more information, see [CREATE SCHEMA &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span></span>  
  
  
