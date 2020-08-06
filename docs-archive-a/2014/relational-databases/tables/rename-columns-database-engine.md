---
title: Renommer des colonnes (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], names
- renaming columns
- column names [SQL Server]
ms.assetid: 7c71ec9f-0180-4398-b32a-4bfb7592e75d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6871ab82eaa17aa5e392e6b2bb3f5c60058f9af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612715"
---
# <a name="rename-columns-database-engine"></a><span data-ttu-id="ab700-102">Renommer des colonnes (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="ab700-102">Rename Columns (Database Engine)</span></span>
  <span data-ttu-id="ab700-103">Vous pouvez renommer une colonne de table dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab700-103">You can rename a table column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ab700-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ab700-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ab700-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ab700-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ab700-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ab700-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ab700-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ab700-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ab700-108">**Pour renommer des colonnes, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="ab700-108">**To rename columns, using:**</span></span>  
  
     [<span data-ttu-id="ab700-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab700-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ab700-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab700-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ab700-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ab700-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ab700-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ab700-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ab700-113">Si vous renommez une colonne, les références à cette colonne ne sont pas automatiquement renommées.</span><span class="sxs-lookup"><span data-stu-id="ab700-113">Renaming a column will not automatically rename references to that column.</span></span> <span data-ttu-id="ab700-114">Vous devez modifier manuellement tout objet qui référence la colonne renommée.</span><span class="sxs-lookup"><span data-stu-id="ab700-114">You must modify any objects that reference the renamed column manually.</span></span> <span data-ttu-id="ab700-115">Par exemple, si vous renommez une colonne de table et si cette colonne est référencée dans un déclencheur, vous devez modifier le déclencheur pour refléter le nouveau nom de colonne.</span><span class="sxs-lookup"><span data-stu-id="ab700-115">For example, if you rename a table column and that column is referenced in a trigger, you must modify the trigger to reflect the new column name.</span></span> <span data-ttu-id="ab700-116">Utilisez [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) pour obtenir la liste des dépendances de l’objet avant de le renommer.</span><span class="sxs-lookup"><span data-stu-id="ab700-116">Use [sys.sql_expression_dependencies](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) to list dependencies on the object before renaming it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ab700-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ab700-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ab700-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ab700-118">Permissions</span></span>  
 <span data-ttu-id="ab700-119">Requiert une autorisation ALTER sur l'objet.</span><span class="sxs-lookup"><span data-stu-id="ab700-119">Requires ALTER permission on the object.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ab700-120">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab700-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-column-using-object-explorer"></a><span data-ttu-id="ab700-121">Pour renommer une colonne à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="ab700-121">To rename a column using Object Explorer</span></span>  
  
1.  <span data-ttu-id="ab700-122">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab700-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ab700-123">Dans **l’Explorateur d’objets**, cliquez avec le bouton droit sur la table dans laquelle vous souhaitez renommer des colonnes et choisissez **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="ab700-123">In **Object Explorer**, right-click the table in which you want to rename columns and choose **Rename**.</span></span>  
  
3.  <span data-ttu-id="ab700-124">Tapez une nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="ab700-124">Type a new column name.</span></span>  
  
#### <a name="to-rename-a-column-using-table-designer"></a><span data-ttu-id="ab700-125">Pour renommer une colonne à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="ab700-125">To rename a column using Table Designer</span></span>  
  
1.  <span data-ttu-id="ab700-126">Dans **l’Explorateur d’objets**, cliquez avec le bouton droit sur la table dans laquelle vous souhaitez renommer des colonnes et choisissez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="ab700-126">In **Object Explorer**, right-click the table to which you want to rename columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="ab700-127">Sous **Nom de la colonne**, sélectionnez le nom que vous souhaitez modifier et tapez-en un nouveau.</span><span class="sxs-lookup"><span data-stu-id="ab700-127">Under **Column Name**, select the name you want to change and type a new one.</span></span>  
  
3.  <span data-ttu-id="ab700-128">Dans le menu **Fichier**, cliquez sur **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="ab700-128">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab700-129">Vous pouvez également modifier le nom d'une colonne sous l'onglet **Propriétés des colonnes** . Sélectionnez la colonne dont vous souhaitez modifier le nom et tapez une nouvelle valeur pour **Nom**.</span><span class="sxs-lookup"><span data-stu-id="ab700-129">You can also change the name of a column in the **Column Properties** tab. Select the column whose name you want to change and type a new value for **Name**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ab700-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab700-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="ab700-131">**Pour renommer une colonne**</span><span class="sxs-lookup"><span data-stu-id="ab700-131">**To rename a column**</span></span>  
  
#### <a name="to-rename-a-column"></a><span data-ttu-id="ab700-132">Pour renommer une colonne</span><span class="sxs-lookup"><span data-stu-id="ab700-132">To rename a column</span></span>  
  
1.  <span data-ttu-id="ab700-133">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab700-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ab700-134">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="ab700-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ab700-135">L'exemple suivant renomme la colonne `TerritoryID` dans la table `Sales.SalesTerritory` en `TerrID`.</span><span class="sxs-lookup"><span data-stu-id="ab700-135">The following example renames the column `TerritoryID` in the table `Sales.SalesTerritory` to `TerrID`.</span></span> <span data-ttu-id="ab700-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="ab700-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename 'Sales.SalesTerritory.TerritoryID', 'TerrID', 'COLUMN';  
    GO  
    ```  
  
 <span data-ttu-id="ab700-137">Pour plus d’informations, consultez [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ab700-137">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
