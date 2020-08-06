---
title: Afficher des informations de classement | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], view
ms.assetid: 1338b4ea-7142-44bc-a3b9-44e54431405f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 995e559cfd7ca871f5abd90751f2f79167bdf76f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614644"
---
# <a name="view-collation-information"></a><span data-ttu-id="7dc50-102">Afficher des informations de classement</span><span class="sxs-lookup"><span data-stu-id="7dc50-102">View Collation Information</span></span>
    
##  <a name="you-can-view-the-collation-of-a-server-database-or-column-in-ssmanstudiofull-using-object-explorer-menu-options-or-by-using-tsql"></a><a name="Top"></a> <span data-ttu-id="7dc50-103">Vous pouvez afficher le classement d'un serveur, d'une base de données ou d'une colonne dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] à l'aide des options de menu de l'Explorateur d'objets ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dc50-103">You can view the collation of a server, database, or column in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
##  <a name="how-to-view-a-collation-setting"></a><a name="Procedures"></a> <span data-ttu-id="7dc50-104">Comment afficher un paramètre de classement</span><span class="sxs-lookup"><span data-stu-id="7dc50-104">How to View a Collation Setting</span></span>  
 <span data-ttu-id="7dc50-105">Vous pouvez utiliser l'un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7dc50-105">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="7dc50-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7dc50-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="7dc50-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7dc50-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7dc50-108">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7dc50-108">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7dc50-109">**Pour afficher un paramètre de classement pour un serveur (instance de SQL Server) dans l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="7dc50-109">**To view a collation setting for a server (instance of SQL Server) in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="7dc50-110">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dc50-110">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7dc50-111">Cliquez avec le bouton droit sur l’instance et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7dc50-111">Right-click the instance and select **Properties**.</span></span>  
  
 <span data-ttu-id="7dc50-112">**Pour afficher un paramètre de classement pour une base de données dans l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="7dc50-112">**To view a collation setting for a database in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="7dc50-113">Dans l'Explorateur d'objets, connectez-vous à une instance de [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="7dc50-113">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7dc50-114">Développez **Bases de données**, cliquez avec le bouton droit sur la base de données et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7dc50-114">Expand **Databases**, right-click the database and select **Properties**.</span></span>  
  
 <span data-ttu-id="7dc50-115">**Pour afficher un paramètre de classement pour une colonne dans l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="7dc50-115">**To view a collation setting for a column in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="7dc50-116">Dans l'Explorateur d'objets, connectez-vous à une instance de [!INCLUDE[ssDE](../../includes/ssde-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="7dc50-116">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="7dc50-117">Développez **Bases de données**, la base de données, puis **Tables**.</span><span class="sxs-lookup"><span data-stu-id="7dc50-117">Expand **Databases**, expand the database and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="7dc50-118">Développez la table contenant la colonne, puis développez **Colonnes**.</span><span class="sxs-lookup"><span data-stu-id="7dc50-118">Expand the table that contains the column and then expand **Columns**.</span></span>  
  
4.  <span data-ttu-id="7dc50-119">Cliquez avec le bouton droit sur la colonne et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7dc50-119">Right-click the column and select **Properties**.</span></span> <span data-ttu-id="7dc50-120">Si la propriété de classement est vide, la colonne n'est pas un type de données character.</span><span class="sxs-lookup"><span data-stu-id="7dc50-120">If the collation property is empty, the column is not a character data type.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7dc50-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7dc50-121">Using Transact-SQL</span></span>  
 <span data-ttu-id="7dc50-122">**Pour afficher le paramètre de classement d'un serveur**</span><span class="sxs-lookup"><span data-stu-id="7dc50-122">**To view the collation setting of a server**</span></span>  
  
1.  <span data-ttu-id="7dc50-123">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et, dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7dc50-123">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7dc50-124">Dans la fenêtre de requête, entrez l'instruction suivante qui utilise la fonction système SERVERPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="7dc50-124">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, SERVERPROPERTY('collation'));  
    ```  
  
3.  <span data-ttu-id="7dc50-125">Vous pouvez également utiliser la procédure stockée système sp_helpsort.</span><span class="sxs-lookup"><span data-stu-id="7dc50-125">Alternatively, you can use the sp_helpsort system stored procedure.</span></span>  
  
    ```  
    EXECUTE sp_helpsort;  
    ```  
  
 <span data-ttu-id="7dc50-126">**Pour afficher tous les classements pris en charge par [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="7dc50-126">**To view all collations supported by [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**</span></span>  
  
1.  <span data-ttu-id="7dc50-127">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et, dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7dc50-127">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7dc50-128">Dans la fenêtre de requête, entrez l'instruction suivante qui utilise la fonction système SERVERPROPERTY.</span><span class="sxs-lookup"><span data-stu-id="7dc50-128">In the query window, enter the following statement that uses the SERVERPROPERTY system function.</span></span>  
  
    ```  
    SELECT name, description FROM sys.fn_helpcollations();  
    ```  
  
 <span data-ttu-id="7dc50-129">**Pour afficher le paramètre de classement d'une base de données**</span><span class="sxs-lookup"><span data-stu-id="7dc50-129">**To view the collation setting of a database**</span></span>  
  
1.  <span data-ttu-id="7dc50-130">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et, dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7dc50-130">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7dc50-131">Dans la fenêtre de requête, entrez l'instruction suivante qui utilise l'affichage catalogue système sys.databases.</span><span class="sxs-lookup"><span data-stu-id="7dc50-131">In the query window, enter the following statement that uses the sys.databases system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.databases;  
    ```  
  
3.  <span data-ttu-id="7dc50-132">Vous pouvez également utiliser la fonction système DATABASEPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="7dc50-132">Alternatively, you can use the DATABASEPROPERTYEX system function.</span></span>  
  
    ```  
    SELECT CONVERT (varchar, DATABASEPROPERTYEX('database_name','collation'));  
    ```  
  
 <span data-ttu-id="7dc50-133">**Pour afficher le paramètre de classement d'une colonne**</span><span class="sxs-lookup"><span data-stu-id="7dc50-133">**To view the collation setting of a column**</span></span>  
  
1.  <span data-ttu-id="7dc50-134">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] et, dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7dc50-134">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and on the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="7dc50-135">Dans la fenêtre de requête, entrez l'instruction suivante qui utilise l'affichage catalogue système sys.columns.</span><span class="sxs-lookup"><span data-stu-id="7dc50-135">In the query window, enter the following statement that uses the sys.columns system catalog view.</span></span>  
  
    ```  
    SELECT name, collation_name FROM sys.columns WHERE name = N'<insert character data type column name>';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7dc50-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7dc50-136">See Also</span></span>  
 <span data-ttu-id="7dc50-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7dc50-137">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="7dc50-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7dc50-138">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="7dc50-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7dc50-139">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="7dc50-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7dc50-140">[sys.columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) </span></span>  
 <span data-ttu-id="7dc50-141">[Priorité de classement &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7dc50-141">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 [<span data-ttu-id="7dc50-142">sp_helpsort &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7dc50-142">sp_helpsort &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-helpsort-transact-sql)  
  
  
