---
title: Créer des tables (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table creation [SQL Server], Visual Database Tools
ms.assetid: 6f7c6ac5-e6d3-4dca-831e-b28442ba535b
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8d84a4da6a10fbcbae311fe1bf738c03b85a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615085"
---
# <a name="create-tables-database-engine"></a><span data-ttu-id="500b3-102">Créer des tables (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="500b3-102">Create Tables (Database Engine)</span></span>
  <span data-ttu-id="500b3-103">Vous pouvez créer une table, la nommer et l'ajouter à une base de données existante dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="500b3-103">You can create a new table, name it, and add it to an existing database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>

> [!NOTE]
>  <span data-ttu-id="500b3-104">Si vous êtes connecté à une base de données SQL Azure, la nouvelle option de table lance un script de création de modèle de table.</span><span class="sxs-lookup"><span data-stu-id="500b3-104">If you are connected to a SQL Azure database, the new table option launches a create table template script.</span></span> <span data-ttu-id="500b3-105">Modifiez les paramètres, puis exécutez le script pour créer une table.</span><span class="sxs-lookup"><span data-stu-id="500b3-105">Edit the parameters, then run the script to create a new table.</span></span> <span data-ttu-id="500b3-106">Pour plus d'informations, consultez [SQL Azure Overview (en anglais)](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx).</span><span class="sxs-lookup"><span data-stu-id="500b3-106">For more information, see [SQL Azure Overview](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx).</span></span>

 <span data-ttu-id="500b3-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="500b3-107">**In This Topic**</span></span>

-   <span data-ttu-id="500b3-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="500b3-108">**Before you begin:**</span></span>

     [<span data-ttu-id="500b3-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="500b3-109">Security</span></span>](#Security)

-   <span data-ttu-id="500b3-110">**Pour créer une table à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="500b3-110">**To create a table, using:**</span></span>

     [<span data-ttu-id="500b3-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="500b3-111">SQL Server Management Studio</span></span>](#SSMSProcedure)

     [<span data-ttu-id="500b3-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="500b3-112">Transact-SQL</span></span>](#TsqlProcedure)

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="500b3-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="500b3-113">Before You Begin</span></span>

###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="500b3-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="500b3-114">Security</span></span>

####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="500b3-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="500b3-115">Permissions</span></span>
 <span data-ttu-id="500b3-116">Nécessite une autorisation CREATE TABLE dans la base de données et une autorisation ALTER pour le schéma dans lequel la table a été créée.</span><span class="sxs-lookup"><span data-stu-id="500b3-116">Requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>

 <span data-ttu-id="500b3-117">Si des colonnes dans l'instruction CREATE TABLE sont définies comme un type de données CLR défini par l'utilisateur, la propriété du type ou une autorisation REFERENCES est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="500b3-117">If any columns in the CREATE TABLE statement are defined as a CLR user-defined type, either ownership of the type or REFERENCES permission on it is required.</span></span>

 <span data-ttu-id="500b3-118">Si des colonnes dans l'instruction CREATE TABLE sont associées à une collection de schémas XML, la propriété de la collection de schémas XML ou une autorisation REFERENCES pour le type est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="500b3-118">If any columns in the CREATE TABLE statement have an XML schema collection associated with them, either ownership of the XML schema collection or REFERENCES permission on it is required.</span></span>

##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="500b3-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="500b3-119">Using SQL Server Management Studio</span></span>

#### <a name="to-create-a-table-with-table-designer"></a><span data-ttu-id="500b3-120">Pour créer une table avec le Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="500b3-120">To create a table with Table Designer</span></span>

1.  <span data-ttu-id="500b3-121">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] qui contient la base de données à modifier.</span><span class="sxs-lookup"><span data-stu-id="500b3-121">In **Object Explorer**, connect to the instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] that contains the database to be modified.</span></span>

2.  <span data-ttu-id="500b3-122">Dans l' **Explorateur d'objets**, développez le nœud **Bases de données** , puis la base de données qui va contenir la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="500b3-122">In **Object Explorer**, expand the **Databases** node and then expand the database that will contain the new table.</span></span>

3.  <span data-ttu-id="500b3-123">Cliquez avec le bouton droit sur le nœud **Tables** de votre base de données dans l’Explorateur d’objets, puis cliquez sur **Nouvelle table**.</span><span class="sxs-lookup"><span data-stu-id="500b3-123">In Object Explorer, right-click the **Tables** node of your database and then click **New Table**.</span></span>

4.  <span data-ttu-id="500b3-124">Tapez les noms des colonnes, choisissez des types de données et spécifiez si les valeurs null sont autorisées pour chaque colonne, comme indiqué dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="500b3-124">Type column names, choose data types, and choose whether to allow nulls for each column as shown in the following illustration.</span></span>

     <span data-ttu-id="500b3-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span><span class="sxs-lookup"><span data-stu-id="500b3-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span></span>

5.  <span data-ttu-id="500b3-126">Pour spécifier davantage de propriétés pour une colonne, par exemple des valeurs d'identité ou de colonne calculée, cliquez sur la colonne et choisissez les propriétés appropriées dans l'onglet des propriétés de la colonne.</span><span class="sxs-lookup"><span data-stu-id="500b3-126">To specify more properties for a column, such as identity or computed column values, click the column and in the column properties tab, choose the appropriate properties.</span></span> <span data-ttu-id="500b3-127">Pour plus d’informations sur les propriétés des colonnes, consultez [Propriétés des colonnes de table &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="500b3-127">For more information about column properties, see [Table Column Properties &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span></span>

6.  <span data-ttu-id="500b3-128">Pour spécifier une colonne comme clé primaire, cliquez avec le bouton droit sur la colonne et sélectionnez **Définir la clé primaire**.</span><span class="sxs-lookup"><span data-stu-id="500b3-128">To specify a column as a primary key, right-click the column and select **Set Primary Key**.</span></span> <span data-ttu-id="500b3-129">Pour plus d’informations, consultez [Create Primary Keys](../tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="500b3-129">For more information, see [Create Primary Keys](../tables/create-primary-keys.md).</span></span>

7.  <span data-ttu-id="500b3-130">Pour créer des relations de clé étrangère, des contraintes de validation ou des index, cliquez avec le bouton droit dans le volet Concepteur de tables et sélectionnez un objet dans la liste, comme indiqué dans l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="500b3-130">To create foreign key relationships, check constraints, or indexes, right-click in the Table Designer pane and select an object from the list as shown in the following illustration.</span></span>

     <span data-ttu-id="500b3-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span><span class="sxs-lookup"><span data-stu-id="500b3-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span></span>

     <span data-ttu-id="500b3-132">Pour plus d'informations sur ces objets, consultez [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) et [Indexes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="500b3-132">For more information about these objects, see [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) and [Indexes](../indexes/indexes.md).</span></span>

8.  <span data-ttu-id="500b3-133">Par défaut, la table est contenue dans le schéma **dbo** .</span><span class="sxs-lookup"><span data-stu-id="500b3-133">By default, the table is contained in the **dbo** schema.</span></span> <span data-ttu-id="500b3-134">Pour spécifier un schéma différent pour la table, cliquez avec le bouton droit dans le volet Concepteur de tables et sélectionnez **Propriétés** , comme indiqué dans l’illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="500b3-134">To specify a different schema for the table, right-click in the Table Designer pane and select **Properties** as shown in the following illustration.</span></span> <span data-ttu-id="500b3-135">Dans la liste déroulante **Schémas** , sélectionnez le schéma approprié.</span><span class="sxs-lookup"><span data-stu-id="500b3-135">From the **Schema** drop-down list, select the appropriate schema.</span></span>

     <span data-ttu-id="500b3-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span><span class="sxs-lookup"><span data-stu-id="500b3-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span></span>

     <span data-ttu-id="500b3-137">Pour plus d'informations sur les schémas, consultez [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span><span class="sxs-lookup"><span data-stu-id="500b3-137">For more information about schemas, see [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span></span>

9. <span data-ttu-id="500b3-138">Dans le menu **Fichier**, choisissez **Enregistrer** *nom de la table*.</span><span class="sxs-lookup"><span data-stu-id="500b3-138">From the **File** menu, choose **Save** *table name*.</span></span>

10. <span data-ttu-id="500b3-139">Dans la boîte de dialogue **Choisir un nom** , tapez un nom pour la table et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="500b3-139">In the **Choose Name** dialog box, type a name for the table and click **OK**.</span></span>

11. <span data-ttu-id="500b3-140">Pour afficher la nouvelle table, dans l' **Explorateur d'objets**, développez le nœud **Tables** et appuyez sur la touche **F5** pour actualiser la liste d'objets.</span><span class="sxs-lookup"><span data-stu-id="500b3-140">To view the new table, in **Object Explorer**, expand the **Tables** node and press **F5** to refresh the list of objects.</span></span> <span data-ttu-id="500b3-141">La nouvelle table s'affiche dans la liste des tables.</span><span class="sxs-lookup"><span data-stu-id="500b3-141">The new table is displayed in the list of tables.</span></span>

##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="500b3-142">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="500b3-142">Using Transact-SQL</span></span>

#### <a name="to-create-a-table-in-the-query-editor"></a><span data-ttu-id="500b3-143">Pour créer une table dans l'éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="500b3-143">To create a table in the Query Editor</span></span>

1.  <span data-ttu-id="500b3-144">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="500b3-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>

2.  <span data-ttu-id="500b3-145">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="500b3-145">On the Standard bar, click **New Query**.</span></span>

3.  <span data-ttu-id="500b3-146">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="500b3-146">Copy and paste the following example into the query window and click **Execute**.</span></span>

    ```
    CREATE TABLE dbo.PurchaseOrderDetail
    (
        PurchaseOrderID int NOT NULL
        ,LineNumber smallint NOT NULL
        ,ProductID int NULL
        ,UnitPrice money NULL
        ,OrderQty smallint NULL
        ,ReceivedQty float NULL
        ,RejectedQty float NULL
        ,DueDate datetime NULL
    );
    ```

 <span data-ttu-id="500b3-147">Pour obtenir d’autres exemples, consultez [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="500b3-147">For more examples, see [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span>


