---
title: Afficher les dépendances d’une table | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table dependencies [SQL Server]
- dependencies [SQL Server], tables
- displaying dependences
- viewing dependencies
ms.assetid: c4351ef5-e7d0-46e7-8367-88695e9974f8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f54b913124cdaa8a7dfeebac01ba070cc37d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615078"
---
# <a name="view-the-dependencies-of-a-table"></a><span data-ttu-id="bb464-102">Afficher les dépendances d'une table</span><span class="sxs-lookup"><span data-stu-id="bb464-102">View the Dependencies of a Table</span></span>
  <span data-ttu-id="bb464-103">Vous pouvez afficher les dépendances d’une table dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb464-103">You can view a table's dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="bb464-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="bb464-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bb464-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="bb464-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bb464-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bb464-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bb464-107">**Pour afficher les dépendances d’une table à l’aide de :**</span><span class="sxs-lookup"><span data-stu-id="bb464-107">**To view a table's dependencies, using:**</span></span>  
  
     [<span data-ttu-id="bb464-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb464-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bb464-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bb464-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bb464-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="bb464-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bb464-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bb464-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bb464-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="bb464-112">Permissions</span></span>  
 <span data-ttu-id="bb464-113">Requiert l'autorisation VIEW DEFINITION sur la base de données et l'autorisation SELECT sur sys.sql_expression_dependencies pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="bb464-113">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="bb464-114">Par défaut, l'autorisation SELECT est accordée uniquement aux membres du rôle de base de données fixe db_owner.</span><span class="sxs-lookup"><span data-stu-id="bb464-114">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="bb464-115">Lorsque les autorisations SELECT et VIEW DEFINITION sont accordées à un autre utilisateur, le bénéficiaire peut consulter toutes les dépendances dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="bb464-115">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bb464-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb464-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-table"></a><span data-ttu-id="bb464-117">Pour afficher les dépendances d'une table</span><span class="sxs-lookup"><span data-stu-id="bb464-117">To view the dependencies of a table</span></span>  
  
1.  <span data-ttu-id="bb464-118">Dans l' **Explorateur d'objets**, développez **Bases de données**, développez une base de données, puis **Tables**.</span><span class="sxs-lookup"><span data-stu-id="bb464-118">In **Object Explorer**, expand **Databases**, expand a database, and then expand **Tables**.</span></span>  
  
2.  <span data-ttu-id="bb464-119">Cliquez avec le bouton droit sur une table, puis cliquez sur **Afficher les dépendances**.</span><span class="sxs-lookup"><span data-stu-id="bb464-119">Right-click a table, and then click **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="bb464-120">Dans la boîte de dialogue **Dépendances d’objets** _\<object name>_ , sélectionnez soit **Objets dépendant de** _\<object name>_ , soit **Objets dont dépend** _\<object name>_ .</span><span class="sxs-lookup"><span data-stu-id="bb464-120">In the **Object Dependencies**_\<object name>_ dialog box, select either **Objects that depend on** _\<object name>_, or **Objects on which**_\<object name>_**depends**.</span></span>  
  
4.  <span data-ttu-id="bb464-121">Sélectionnez un objet dans la grille **Dépendances** .</span><span class="sxs-lookup"><span data-stu-id="bb464-121">Select an object in the **Dependencies** grid.</span></span> <span data-ttu-id="bb464-122">Le type de l’objet (par exemple « déclencheur » ou « procédure stockée ») apparaît dans la zone **Type** .</span><span class="sxs-lookup"><span data-stu-id="bb464-122">The type of object (such as "Trigger" or "Stored Procedure"), appears in the **Type** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bb464-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bb464-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-objects-that-depend-on-a-table"></a><span data-ttu-id="bb464-124">Pour afficher les objets qui dépendent d'une table</span><span class="sxs-lookup"><span data-stu-id="bb464-124">To view the objects that depend on a table</span></span>  
  
1.  <span data-ttu-id="bb464-125">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb464-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bb464-126">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="bb464-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bb464-127">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="bb464-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');   
    GO  
  
    ```  
  
#### <a name="to-view-the-objects-on-which-a-table-depends"></a><span data-ttu-id="bb464-128">Pour afficher les objets dont dépend une table</span><span class="sxs-lookup"><span data-stu-id="bb464-128">To view the objects on which a table depends</span></span>  
  
1.  <span data-ttu-id="bb464-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb464-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bb464-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="bb464-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bb464-131">L'exemple suivant retourne les objets qui dépendent de la table `Production.Product`.</span><span class="sxs-lookup"><span data-stu-id="bb464-131">The following example returns the objects that depend on the table `Production.Product`.</span></span> <span data-ttu-id="bb464-132">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="bb464-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referenced_id = OBJECT_ID(N'Production.Product');   
    GO  
  
    ```  
  
 <span data-ttu-id="bb464-133">Pour plus d’informations, consultez [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="bb464-133">For additional information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)</span></span>  
  
  
