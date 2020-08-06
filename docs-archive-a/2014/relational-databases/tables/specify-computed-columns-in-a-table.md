---
title: Spécifier les colonnes calculées dans une table | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, define
ms.assetid: 731a4576-09c1-47f0-a8f6-edd0b55679f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22e4df8d67b61e50383ffd8e33f982990ff3f2ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612710"
---
# <a name="specify-computed-columns-in-a-table"></a><span data-ttu-id="2a47a-102">Spécifier les colonnes calculées dans une table</span><span class="sxs-lookup"><span data-stu-id="2a47a-102">Specify Computed Columns in a Table</span></span>
  <span data-ttu-id="2a47a-103">Une colonne calculée est une colonne virtuelle qui n'est pas stockée physiquement dans la table, à moins que la colonne ne soit indiquée comme PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="2a47a-103">A computed column is a virtual column that is not physically stored in the table, unless the column is marked PERSISTED.</span></span> <span data-ttu-id="2a47a-104">Une expression de colonne calculée peut utiliser des données d'autres colonnes afin de calculer une valeur pour la colonne à laquelle elle appartient.</span><span class="sxs-lookup"><span data-stu-id="2a47a-104">A computed column expression can use data from other columns to calculate a value for the column to which it belongs.</span></span> <span data-ttu-id="2a47a-105">Vous pouvez spécifier une expression pour une colonne calculée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a47a-105">You can specify an expression for a computed column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2a47a-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2a47a-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2a47a-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2a47a-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2a47a-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2a47a-108">Limitations and Restrictions</span></span>](#Limitations)  
  
     [<span data-ttu-id="2a47a-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2a47a-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2a47a-110">**Pour spécifier une colonne calculée à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="2a47a-110">**To specify a computed column, using:**</span></span>  
  
     [<span data-ttu-id="2a47a-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a47a-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2a47a-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a47a-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2a47a-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2a47a-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="2a47a-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="2a47a-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2a47a-115">Une colonne calculée ne peut pas être utilisée en tant que définition de contrainte DEFAULT ou FOREIGN KEY ou avec une définition de contrainte NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="2a47a-115">A computed column cannot be used as a DEFAULT or FOREIGN KEY constraint definition or with a NOT NULL constraint definition.</span></span> <span data-ttu-id="2a47a-116">Toutefois, si sa valeur est définie par une expression déterministe et que le type de données du résultat est autorisé dans les colonnes d'index, elle peut être utilisée en tant que colonne clé dans un index ou composante d'une contrainte PRIMARY KEY ou UNIQUE quelconque.</span><span class="sxs-lookup"><span data-stu-id="2a47a-116">However, if the computed column value is defined by a deterministic expression and the data type of the result is allowed in index columns, a computed column can be used as a key column in an index or as part of any PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="2a47a-117">Par exemple, si la table possède les colonnes d'entiers a et b, la colonne calculée a + b peut être indexée, contrairement à la colonne calculée a + DATEPART(dd, GETDATE()) dont la valeur est susceptible d'évoluer au fil des appels.</span><span class="sxs-lookup"><span data-stu-id="2a47a-117">For example, if the table has integer columns a and b, the computed column a + b may be indexed, but computed column a + DATEPART(dd, GETDATE()) cannot be indexed, because the value might change in subsequent invocations.</span></span>  
  
-   <span data-ttu-id="2a47a-118">Une colonne calculée ne peut pas être la cible d'une instruction INSERT ou UPDATE.</span><span class="sxs-lookup"><span data-stu-id="2a47a-118">A computed column cannot be the target of an INSERT or UPDATE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2a47a-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2a47a-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2a47a-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2a47a-120">Permissions</span></span>  
 <span data-ttu-id="2a47a-121">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="2a47a-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2a47a-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2a47a-122">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-add-a-new-computed-column"></a><a name="NewColumn"></a> <span data-ttu-id="2a47a-123">Pour ajouter une nouvelle colonne calculée</span><span class="sxs-lookup"><span data-stu-id="2a47a-123">To add a new computed column</span></span>  
  
1.  <span data-ttu-id="2a47a-124">Dans l' **Explorateur d'objets**, développez la table à laquelle vous voulez ajouter une nouvelle colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="2a47a-124">In **Object Explorer**, expand the table for which you want to add the new computed column.</span></span> <span data-ttu-id="2a47a-125">Cliquez avec le bouton droit sur **Colonnes** et sélectionnez **Nouvelle colonne**.</span><span class="sxs-lookup"><span data-stu-id="2a47a-125">Right-click **Columns** and select **New Column**.</span></span>  
  
2.  <span data-ttu-id="2a47a-126">Entrez le nom de la colonne et acceptez le type de données par défaut (`nchar`(10)).</span><span class="sxs-lookup"><span data-stu-id="2a47a-126">Enter the column name and accept the default data type (`nchar`(10)).</span></span> <span data-ttu-id="2a47a-127">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] détermine le type de données de la colonne calculée en appliquant les règles de priorité des types de données aux expressions spécifiées dans la formule.</span><span class="sxs-lookup"><span data-stu-id="2a47a-127">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines the data type of the computed column by applying the rules of data type precedence to the expressions specified in the formula.</span></span> <span data-ttu-id="2a47a-128">Par exemple, si la formule fait référence à une colonne de type `money` et à une colonne de type `int`, la colonne calculée est de type `money` car ce type de données a la priorité la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="2a47a-128">For example, if the formula references a column of type `money` and a column of type `int`, the computed column will be of type `money` because that data type has the higher precedence.</span></span> <span data-ttu-id="2a47a-129">Pour plus d’informations, consultez [Priorités des types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2a47a-129">For more information, see [Data Type Precedence &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span></span>  
  
3.  <span data-ttu-id="2a47a-130">Dans l'onglet **Propriétés des colonnes** , développez la propriété **Spécification de la colonne calculée** .</span><span class="sxs-lookup"><span data-stu-id="2a47a-130">In the **Column Properties** tab, expand the **Computed Column Specification** property.</span></span>  
  
4.  <span data-ttu-id="2a47a-131">Dans la propriété enfant **(Formule)** , entrez l’expression pour cette colonne dans la cellule de grille située à droite.</span><span class="sxs-lookup"><span data-stu-id="2a47a-131">In the **(Formula)** child property, enter the expression for this column in the grid cell to the right.</span></span> <span data-ttu-id="2a47a-132">Par exemple, dans une colonne `SalesTotal` , la formule que vous écrivez peut être `SubTotal+TaxAmt+Freight`, qui ajoute la valeur dans ces colonnes pour chaque ligne de la table.</span><span class="sxs-lookup"><span data-stu-id="2a47a-132">For example, in a `SalesTotal` column, the formula you enter might be `SubTotal+TaxAmt+Freight`, which adds the value in these columns for each row in the table.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="2a47a-133">Lorsqu'une formule combine deux expressions de type de données différents, les règles de priorité des types de données spécifient que le type ayant une priorité plus faible est converti dans un type ayant une priorité plus élevée.</span><span class="sxs-lookup"><span data-stu-id="2a47a-133">When a formula combines two expressions of different data types, the rules for data type precedence specify that the data type with the lower precedence is converted to the data type with the higher precedence.</span></span> <span data-ttu-id="2a47a-134">Si la conversion n'est pas prise en charge en tant que conversion implicite, l'erreur «`Error validating the formula for column column_name.`» est retournée.</span><span class="sxs-lookup"><span data-stu-id="2a47a-134">If the conversion is not a supported implicit conversion, the error "`Error validating the formula for column column_name.`" is returned.</span></span> <span data-ttu-id="2a47a-135">Utilisez la fonction CAST ou CONVERT pour résoudre le conflit de type de données.</span><span class="sxs-lookup"><span data-stu-id="2a47a-135">Use the CAST or CONVERT function to resolve the data type conflict.</span></span> <span data-ttu-id="2a47a-136">Par exemple, si une colonne de type `nvarchar` est associée à une colonne de type `int`, le type entier doit être converti en `nvarchar` comme indiqué dans cette formule `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span><span class="sxs-lookup"><span data-stu-id="2a47a-136">For example, if a column of type `nvarchar` is combined with a column of type `int`, the integer type must be converted to `nvarchar` as shown in this formula `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span></span> <span data-ttu-id="2a47a-137">Pour plus d’informations, consultez [CAST et CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2a47a-137">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
5.  <span data-ttu-id="2a47a-138">Indiquez si les données doivent être enregistrées en choisissant **Oui** ou **Non** dans la liste déroulante de la propriété enfant **Is Persisted** .</span><span class="sxs-lookup"><span data-stu-id="2a47a-138">Indicate whether the data is persisted by choosing **Yes** or **No** from the drop-down for the **Is Persisted** child property.</span></span>  
  
6.  <span data-ttu-id="2a47a-139">Dans le menu **Fichier**, cliquez sur **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="2a47a-139">On the **File** menu, click **Save**_table name_.</span></span>  
  
#### <a name="to-add-a-computed-column-definition-to-an-existing-column"></a><span data-ttu-id="2a47a-140">Pour ajouter une définition de colonne calculée à une colonne existante</span><span class="sxs-lookup"><span data-stu-id="2a47a-140">To add a computed column definition to an existing column</span></span>  
  
1.  <span data-ttu-id="2a47a-141">Dans l’ **Explorateur d’objets**, cliquez avec le bouton droit sur la table contenant la colonne à modifier et développez **Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="2a47a-141">In **Object Explorer**, right-click the table with the column for which you want to change and expand the **Columns** folder.</span></span>  
  
2.  <span data-ttu-id="2a47a-142">Cliquez avec le bouton droit sur la colonne dans laquelle vous voulez spécifier une formule de colonne calculée et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2a47a-142">Right-click the column for which you want to specify a computed column formula and click **Delete**.</span></span> <span data-ttu-id="2a47a-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a47a-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="2a47a-144">Ajoutez une nouvelle colonne et spécifiez la formule de colonne calculée en suivant la procédure précédente pour ajouter une nouvelle colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="2a47a-144">Add a new column and specify the computed column formula by following the previous procedure to add a new computed column.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2a47a-145">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2a47a-145">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-computed-column-when-creating-a-table"></a><span data-ttu-id="2a47a-146">Pour ajouter une colonne calculée lors de la création d'une table</span><span class="sxs-lookup"><span data-stu-id="2a47a-146">To add a computed column when creating a table</span></span>  
  
1.  <span data-ttu-id="2a47a-147">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a47a-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2a47a-148">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2a47a-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2a47a-149">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2a47a-149">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="2a47a-150">L'exemple crée une table avec une colonne calculée qui multiplie la valeur de la colonne `QtyAvailable` par la valeur de la colonne `UnitPrice` .</span><span class="sxs-lookup"><span data-stu-id="2a47a-150">The example creates a table with a computed column that multiplies the value in the `QtyAvailable` column times the value in the `UnitPrice` column.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products   
    (  
        ProductID int IDENTITY (1,1) NOT NULL  
      , QtyAvailable smallint  
      , UnitPrice money  
      , InventoryValue AS QtyAvailable * UnitPrice  
    );  
  
    -- Insert values into the table.  
    INSERT INTO dbo.Products (QtyAvailable, UnitPrice)  
    VALUES (25, 2.00), (10, 1.5);  
  
    -- Display the rows in the table.  
    SELECT ProductID, QtyAvailable, UnitPrice, InventoryValue  
    FROM dbo.Products;  
  
    ```  
  
#### <a name="to-add-a-new-computed-column-to-an-existing-table"></a><span data-ttu-id="2a47a-151">Pour ajouter une nouvelle colonne calculée dans une table existante</span><span class="sxs-lookup"><span data-stu-id="2a47a-151">To add a new computed column to an existing table</span></span>  
  
1.  <span data-ttu-id="2a47a-152">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a47a-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2a47a-153">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2a47a-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2a47a-154">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2a47a-154">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="2a47a-155">L'exemple suivant ajoute une nouvelle colonne à la table créée dans l'exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="2a47a-155">The following example adds a new column to the table created in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.35);  
  
    ```  
  
#### <a name="to-change-an-existing-column-to-a-computed-column"></a><span data-ttu-id="2a47a-156">Pour modifier une colonne existante en une colonne calculée</span><span class="sxs-lookup"><span data-stu-id="2a47a-156">To change an existing column to a computed column</span></span>  
  
1.  <span data-ttu-id="2a47a-157">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a47a-157">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2a47a-158">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2a47a-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2a47a-159">Pour modifier une colonne existante en une colonne calculée vous devez supprimer et recréer la colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="2a47a-159">To change an existing column to a computed column you must drop and re-create the computed column.</span></span> <span data-ttu-id="2a47a-160">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2a47a-160">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="2a47a-161">L'exemple suivant modifie la colonne ajoutée dans l'exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="2a47a-161">The following example modifies the column added in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products DROP COLUMN RetailValue;  
    GO  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.5);  
  
    ```  
  
     <span data-ttu-id="2a47a-162">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2a47a-162">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
