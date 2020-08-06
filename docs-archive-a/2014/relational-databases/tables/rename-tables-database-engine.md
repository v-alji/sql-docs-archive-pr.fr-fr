---
title: Renommer des tables (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table renaming [SQL Server]
- table names [SQL Server]
- tables [SQL Server], Visual Database Tools
- renaming tables
ms.assetid: 2f5c922d-4d71-4694-9fca-28dd99375799
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e73bbb92d8fd3fdcaa7756ce1dcb74d8cd598b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612712"
---
# <a name="rename-tables-database-engine"></a><span data-ttu-id="2bd2a-102">Renommer des tables (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="2bd2a-102">Rename Tables (Database Engine)</span></span>
  <span data-ttu-id="2bd2a-103">Vous pouvez renommer une table dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bd2a-103">You can rename a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="2bd2a-104">Ne renommez une table qu'après mûre réflexion.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-104">Think carefully before you rename a table.</span></span> <span data-ttu-id="2bd2a-105">En effet, s'il existe des requêtes, des vues, des fonctions définies par l'utilisateur, des procédures stockées ou des programmes qui font référence à cette table, le changement de nom rend tous ces objets non valides.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="2bd2a-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2bd2a-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2bd2a-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2bd2a-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2bd2a-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2bd2a-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2bd2a-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2bd2a-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2bd2a-110">**Pour renommer une table à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="2bd2a-110">**To rename a table, using:**</span></span>  
  
     [<span data-ttu-id="2bd2a-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2bd2a-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2bd2a-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2bd2a-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2bd2a-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2bd2a-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2bd2a-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2bd2a-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2bd2a-115">Le fait de renommer une table ne renomme pas automatiquement les références à cette table.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-115">Renaming a table will not automatically rename references to that table.</span></span> <span data-ttu-id="2bd2a-116">Vous devez modifier manuellement tout objet qui référence la table renommée.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-116">You must manually modify any objects that reference the renamed table.</span></span> <span data-ttu-id="2bd2a-117">Par exemple, si vous renommez une table et si cette table est référencée dans un déclencheur, vous devez modifier le déclencheur pour refléter le nouveau nom de table.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-117">For example, if you rename a table and that table is referenced in a trigger, you must modify the trigger to reflect the new table name.</span></span> <span data-ttu-id="2bd2a-118">Utilisez [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) pour obtenir la liste des dépendances de la table avant de la renommer.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-118">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the table before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2bd2a-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2bd2a-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2bd2a-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2bd2a-120">Permissions</span></span>  
 <span data-ttu-id="2bd2a-121">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2bd2a-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2bd2a-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="2bd2a-123">Pour renommer une table</span><span class="sxs-lookup"><span data-stu-id="2bd2a-123">To rename a table</span></span>  
  
1.  <span data-ttu-id="2bd2a-124">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur la table que vous souhaitez renommer et choisissez **Conception** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-124">In Object Explorer, right-click the table you want to rename and choose **Design** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="2bd2a-125">Dans le menu **Affichage** , choisissez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-125">From the **View** menu, choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="2bd2a-126">Dans le champ de la valeur **Nom** de la fenêtre **Propriétés** , tapez un nouveau nom pour la table.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-126">In the field for the **Name** value in the **Properties** window, type a new name for the table.</span></span>  
  
4.  <span data-ttu-id="2bd2a-127">Pour annuler cette action, appuyez sur la touche Échap avant de quitter ce champ.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-127">To cancel this action, press the ESC key before leaving this field.</span></span>  
  
5.  <span data-ttu-id="2bd2a-128">Dans le menu **fichier** , choisissez **Enregistrer**_nom_de la table.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-128">From the **File** menu choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2bd2a-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2bd2a-129">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-table"></a><span data-ttu-id="2bd2a-130">Pour renommer une table</span><span class="sxs-lookup"><span data-stu-id="2bd2a-130">To rename a table</span></span>  
  
1.  <span data-ttu-id="2bd2a-131">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bd2a-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2bd2a-132">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2bd2a-133">L'exemple suivant renomme la table `SalesTerritory` en `SalesTerr` dans le schéma `Sales` .</span><span class="sxs-lookup"><span data-stu-id="2bd2a-133">The following example renames the `SalesTerritory` table to `SalesTerr` in the `Sales` schema.</span></span> <span data-ttu-id="2bd2a-134">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2bd2a-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    EXEC sp_rename 'Sales.SalesTerritory', 'SalesTerr';  
    ```  
  
 <span data-ttu-id="2bd2a-135">Pour obtenir des exemples supplémentaires, consultez [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2bd2a-135">For additional examples, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
