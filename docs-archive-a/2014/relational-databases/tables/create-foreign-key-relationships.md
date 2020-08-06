---
title: Créer des relations de clé étrangère | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], creating
ms.assetid: 867a54b8-5be4-46e6-9702-49ae6dabf67c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ee0de3311eb6abffcdb71ab725d0650fe96b04c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615092"
---
# <a name="create-foreign-key-relationships"></a><span data-ttu-id="f1a9f-102">Créer des relations de clé étrangère</span><span class="sxs-lookup"><span data-stu-id="f1a9f-102">Create Foreign Key Relationships</span></span>
  <span data-ttu-id="f1a9f-103">Cette rubrique explique comment créer des relations de clé étrangère dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1a9f-103">This topic describes how to create foreign key relationships in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f1a9f-104">Vous créez une relation entre deux tables lorsque vous voulez associer des lignes d'une table à des lignes appartenant à une autre table.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-104">You create a relationship between two tables when you want to associate rows of one table with rows of another.</span></span>  
  
 <span data-ttu-id="f1a9f-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f1a9f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f1a9f-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f1a9f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f1a9f-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f1a9f-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f1a9f-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1a9f-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f1a9f-109">**Pour créer des relations de clé étrangère, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="f1a9f-109">**To Create Foreign Key Relationships by using:**</span></span>  
  
     [<span data-ttu-id="f1a9f-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1a9f-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f1a9f-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1a9f-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f1a9f-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f1a9f-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f1a9f-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f1a9f-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f1a9f-114">Une contrainte de clé étrangère ne doit pas forcément être liée seulement à une contrainte de clé primaire d'une autre table. Elle peut également être définie pour référencer les colonnes d'une contrainte UNIQUE d'une autre table.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-114">A foreign key constraint does not have to be linked only to a primary key constraint in another table; it can also be defined to reference the columns of a UNIQUE constraint in another table.</span></span>  
  
-   <span data-ttu-id="f1a9f-115">Lorsqu'une valeur différente de NULL est entrée dans la colonne d'une contrainte FOREIGN KEY, la valeur doit exister dans la colonne référencée. Dans le cas contraire, le système retourne un message d'erreur signalant une violation de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-115">When a value other than NULL is entered into the column of a FOREIGN KEY constraint, the value must exist in the referenced column; otherwise, a foreign key violation error message is returned.</span></span> <span data-ttu-id="f1a9f-116">Pour vous assurer que toutes les valeurs d'une contrainte de clé étrangère composite sont vérifiées, spécifiez NOT NULL pour toutes les colonnes participant à la contrainte.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-116">To make sure that all values of a composite foreign key constraint are verified, specify NOT NULL on all the participating columns.</span></span>  
  
-   <span data-ttu-id="f1a9f-117">Les contraintes FOREIGN KEY ne peuvent faire référence qu'à des tables au sein de la même base de données sur le même serveur.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-117">FOREIGN KEY constraints can reference only tables within the same database on the same server.</span></span> <span data-ttu-id="f1a9f-118">L'intégrité référentielle inter-base de données doit être implémentée via les déclencheurs.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-118">Cross-database referential integrity must be implemented through triggers.</span></span> <span data-ttu-id="f1a9f-119">Pour plus d’informations, consultez [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f1a9f-119">For more information, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
-   <span data-ttu-id="f1a9f-120">Les contraintes FOREIGN KEY peuvent faire référence à une autre colonne dans la même table.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-120">FOREIGN KEY constraints can reference another column in the same table.</span></span> <span data-ttu-id="f1a9f-121">On appelle habituellement ce mécanisme « auto-référence ».</span><span class="sxs-lookup"><span data-stu-id="f1a9f-121">This is referred to as a self-reference.</span></span>  
  
-   <span data-ttu-id="f1a9f-122">Une contrainte FOREIGN KEY spécifiée au niveau de la colonne ne peut lister qu'une colonne de référence.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-122">A FOREIGN KEY constraint specified at the column level can list only one reference column.</span></span> <span data-ttu-id="f1a9f-123">Cette colonne doit avoir le même type de données que la colonne pour laquelle la contrainte est définie.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-123">This column must have the same data type as the column on which the constraint is defined.</span></span>  
  
-   <span data-ttu-id="f1a9f-124">Une contrainte FOREIGN KEY spécifiée au niveau de la table doit avoir le même nombre de colonnes de référence que le nombre de colonnes de la liste des colonnes de la contrainte.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-124">A FOREIGN KEY constraint specified at the table level must have the same number of reference columns as the number of columns in the constraint column list.</span></span> <span data-ttu-id="f1a9f-125">Le type de données de chaque colonne de référence doit également être identique à la colonne de référence correspondante dans la liste des colonnes.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-125">The data type of each reference column must also be the same as the corresponding column in the column list.</span></span>  
  
-   <span data-ttu-id="f1a9f-126">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] n'a pas de limite prédéfinie du nombre de contraintes FOREIGN KEY qu'une table peut contenir et qui référencent d'autres tables ou du nombre de contraintes FOREIGN KEY possédées par d'autres tables qui font référence à une table spécifique.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-126">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not have a predefined limit on either the number of FOREIGN KEY constraints a table can contain that reference other tables, or the number of FOREIGN KEY constraints that are owned by other tables that reference a specific table.</span></span> <span data-ttu-id="f1a9f-127">Cependant, le nombre réel de contraintes FOREIGN KEY qui peuvent être utilisées est limité par la configuration matérielle et par la conception de la base de données et de l'application.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-127">Nevertheless, the actual number of FOREIGN KEY constraints that can be used is limited by the hardware configuration and by the design of the database and application.</span></span> <span data-ttu-id="f1a9f-128">Nous vous recommandons de ne pas insérer plus de 253 contraintes FOREIGN KEY dans une table et qu'une même table ne soit pas référencée par plus de 253 contraintes FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-128">We recommend that a table contain no more than 253 FOREIGN KEY constraints, and that it be referenced by no more than 253 FOREIGN KEY constraints.</span></span>  
  
-   <span data-ttu-id="f1a9f-129">Les contraintes FOREIGN KEY ne sont pas appliquées dans les tables temporaires.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-129">FOREIGN KEY constraints are not enforced on temporary tables.</span></span>  
  
-   <span data-ttu-id="f1a9f-130">Si une clé étrangère est définie sur une colonne avec le type de données CLR défini par l'utilisateur, l'implémentation du type doit prendre en charge le tri binaire.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-130">If a foreign key is defined on a CLR user-defined type column, the implementation of the type must support binary ordering.</span></span> <span data-ttu-id="f1a9f-131">Pour plus d’informations, consultez [Types CLR définis par l’utilisateur](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="f1a9f-131">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
-   <span data-ttu-id="f1a9f-132">Une colonne de type `varchar(max)` ne peut participer à une contrainte FOREIGN KEY que si la clé primaire qu'elle référence est également définie comme étant de type `varchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-132">A column of type `varchar(max)` can participate in a FOREIGN KEY constraint only if the primary key it references is also defined as type `varchar(max)`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f1a9f-133">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1a9f-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f1a9f-134">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f1a9f-134">Permissions</span></span>  
 <span data-ttu-id="f1a9f-135">La création d'une nouvelle table avec une clé étrangère nécessite une autorisation CREATE TABLE dans la base de données et une autorisation ALTER pour le schéma dans lequel la table a été créée.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-135">Creating a new table with a foreign key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="f1a9f-136">La création d'une clé étrangère dans une table existante nécessite l'autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-136">Creating a foreign key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f1a9f-137">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1a9f-137">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-foreign-key-relationship-in-table-designer"></a><span data-ttu-id="f1a9f-138">Pour créer une relation de clé étrangère dans le Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="f1a9f-138">To create a foreign key relationship in Table Designer</span></span>  
  
1.  <span data-ttu-id="f1a9f-139">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur la table qui se trouve du côté clé étrangère de la relation et cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-139">In Object Explorer, right-click the table that will be on the foreign-key side of the relationship and click **Design**.</span></span>  
  
     <span data-ttu-id="f1a9f-140">La table s'ouvre dans le **Concepteur de tables**.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-140">The table opens in **Table Designer**.</span></span>  
  
2.  <span data-ttu-id="f1a9f-141">Dans le menu **Concepteur de tables** , cliquez sur **Relations**.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-141">From the **Table Designer** menu, click **Relationships**.</span></span>  
  
3.  <span data-ttu-id="f1a9f-142">Dans la boîte de dialogue **Relations de clé étrangère** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-142">In the **Foreign-key Relationships** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="f1a9f-143">La relation s'affiche dans la liste **Relation sélectionné**e avec un nom fourni par le système au format FK_\<*tablename*>_\<*tablename*>, où  *est le nom de la table* de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-143">The relationship appears in the **Selected Relationship** list with a system-provided name in the format FK_\<*tablename*>_\<*tablename*>, where *tablename* is the name of the foreign key table.</span></span>  
  
4.  <span data-ttu-id="f1a9f-144">Cliquez sur la relation dans la liste **Relation sélectionnée** .</span><span class="sxs-lookup"><span data-stu-id="f1a9f-144">Click the relationship in the **Selected Relationship** list.</span></span>  
  
5.  <span data-ttu-id="f1a9f-145">Cliquez sur **Spécification de tables et colonnes** dans la grille affichée à droite et cliquez sur le bouton de sélection ( **...** ), à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-145">Click **Tables and Columns Specification** in the grid to the right and click the ellipses (**...**) to the right of the property.</span></span>  
  
6.  <span data-ttu-id="f1a9f-146">Dans la liste déroulante **Clé primaire** de la boîte de dialogue **Tables et colonnes** , choisissez la table qui sera du côté clé primaire de la relation.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-146">In the **Tables and Columns** dialog box, in the **Primary Key** drop-down list, choose the table that will be on the primary-key side of the relationship.</span></span>  
  
7.  <span data-ttu-id="f1a9f-147">Dans la grille située au-dessous, choisissez les colonnes qui participent à la clé primaire de la table.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-147">In the grid beneath, choose the columns contributing to the table's primary key.</span></span> <span data-ttu-id="f1a9f-148">Dans la cellule de la grille située à gauche de chaque colonne, choisissez la colonne clé étrangère correspondante dans la table de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-148">In the adjacent grid cell to the left of each column, choose the corresponding foreign-key column of the foreign-key table.</span></span>  
  
     <span data-ttu-id="f1a9f-149">Le**Concepteur de tables** propose un nom pour la relation.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-149">**Table Designer** suggests a name for the relationship.</span></span> <span data-ttu-id="f1a9f-150">Pour changer ce nom, modifiez le contenu de la zone de texte **Nom de la relation** .</span><span class="sxs-lookup"><span data-stu-id="f1a9f-150">To change this name, edit the contents of the **Relationship Name** text box.</span></span>  
  
8.  <span data-ttu-id="f1a9f-151">Choisissez **OK** pour créer la relation.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-151">Choose **OK** to create the relationship.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f1a9f-152">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1a9f-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-foreign-key-in-a-new-table"></a><span data-ttu-id="f1a9f-153">Pour créer une clé étrangère dans une nouvelle table</span><span class="sxs-lookup"><span data-stu-id="f1a9f-153">To create a foreign key in a new table</span></span>  
  
1.  <span data-ttu-id="f1a9f-154">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1a9f-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f1a9f-155">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f1a9f-156">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-156">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f1a9f-157">L'exemple crée une table et définit une contrainte de clé étrangère sur la colonne `TempID` qui fait référence à la colonne `SalesReasonID` dans la table `Sales.SalesReason` .</span><span class="sxs-lookup"><span data-stu-id="f1a9f-157">The example creates a table and defines a foreign key constraint on the column `TempID` that references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span> <span data-ttu-id="f1a9f-158">Les clauses ON DELETE CASCADE et ON UPDATE CASCADE sont utilisées pour garantir que les modifications apportées à la table `Sales.SalesReason` sont automatiquement propagées dans la table `Sales.TempSalesReason` .</span><span class="sxs-lookup"><span data-stu-id="f1a9f-158">The ON DELETE CASCADE and ON UPDATE CASCADE clauses are used to ensure that changes made to `Sales.SalesReason` table are automatically propagated to the `Sales.TempSalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Sales.TempSalesReason (TempID int NOT NULL, Name nvarchar(50),   
    CONSTRAINT PK_TempSales PRIMARY KEY NONCLUSTERED (TempID),   
    CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    );GO  
  
    ```  
  
#### <a name="to-create-a-foreign-key-in-an-existing-table"></a><span data-ttu-id="f1a9f-159">Pour créer une clé étrangère dans une table existante</span><span class="sxs-lookup"><span data-stu-id="f1a9f-159">To create a foreign key in an existing table</span></span>  
  
1.  <span data-ttu-id="f1a9f-160">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1a9f-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f1a9f-161">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f1a9f-162">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f1a9f-162">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f1a9f-163">L'exemple crée une clé étrangère sur la colonne `TempID` et référence la colonne `SalesReasonID` dans la table `Sales.SalesReason` .</span><span class="sxs-lookup"><span data-stu-id="f1a9f-163">The example creates a foreign key on the column `TempID` and references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Sales.TempSalesReason   
    ADD CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    ;  
    GO  
  
    ```  
  
     <span data-ttu-id="f1a9f-164">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) et [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f1a9f-164">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
  
