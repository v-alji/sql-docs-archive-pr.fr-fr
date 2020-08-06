---
title: Copier des colonnes d’une table vers une autre (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying columns
- columns [SQL Server], copying
ms.assetid: 5f5e70dc-69f9-44b8-bc48-b5d51ac20d77
author: stevestein
ms.author: sstein
ms.openlocfilehash: 37b98bf0910cbbb4c2a1d7fe01f11d52703ec88c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615100"
---
# <a name="copy-columns-from-one-table-to-another-database-engine"></a><span data-ttu-id="f6121-102">Copier des colonnes d'une table vers une autre (Moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="f6121-102">Copy Columns from One Table to Another (Database Engine)</span></span>
  <span data-ttu-id="f6121-103">Cette rubrique explique comment copier des colonnes d'une table vers une autre, en copiant uniquement la définition de la colonne ou la définition et les données dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6121-103">This topic describes how to copy columns from one table to another, copying either just the column definition, or the definition and data in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f6121-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f6121-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f6121-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f6121-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f6121-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f6121-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f6121-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f6121-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f6121-108">**Pour copier des colonnes à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="f6121-108">**To coy columns, using:**</span></span>  
  
     [<span data-ttu-id="f6121-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f6121-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f6121-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f6121-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f6121-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f6121-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f6121-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="f6121-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f6121-113">Lorsque vous copiez une colonne contenant un type de données alias d'une base de données dans l'autre, le type de données alias risque de ne pas être disponible dans la base de données cible.</span><span class="sxs-lookup"><span data-stu-id="f6121-113">When you copy a column that has an alias data type from one database to another, the alias data type may not be available in the destination database.</span></span> <span data-ttu-id="f6121-114">En pareil cas, la colonne se voit assigner le type de données de base le plus proche disponible dans cette base de données.</span><span class="sxs-lookup"><span data-stu-id="f6121-114">In such a case, the column will be assigned the nearest matching base data type available in that database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f6121-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f6121-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f6121-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f6121-116">Permissions</span></span>  
 <span data-ttu-id="f6121-117">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="f6121-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f6121-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f6121-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="f6121-119">Pour copier des définitions de colonne d'une table vers une autre</span><span class="sxs-lookup"><span data-stu-id="f6121-119">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="f6121-120">Ouvrez la table contenant les colonnes à copier et celle dans laquelle vous souhaitez les copier en cliquant avec le bouton droit sur les tables, puis cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="f6121-120">Open the table with columns you want to copy and the one you want to copy into by right-clicking the tables, and then clicking **Design**.</span></span>  
  
2.  <span data-ttu-id="f6121-121">Cliquez sur l'onglet de la table contenant les colonnes que vous souhaitez copier et sélectionnez ces colonnes.</span><span class="sxs-lookup"><span data-stu-id="f6121-121">Click the tab for the table with the columns you want to copy and select those columns.</span></span>  
  
3.  <span data-ttu-id="f6121-122">Dans le menu **Edition** , cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="f6121-122">From the **Edit** menu, click **Copy**.</span></span>  
  
4.  <span data-ttu-id="f6121-123">Cliquez sur l'onglet de la table dans laquelle vous souhaitez copier les colonnes.</span><span class="sxs-lookup"><span data-stu-id="f6121-123">Click the tab for the table into which you want to copy the columns.</span></span>  
  
5.  <span data-ttu-id="f6121-124">Sélectionnez la colonne qui doit suivre les colonnes insérées, puis cliquez sur **Coller** dans le menu **Edition**.</span><span class="sxs-lookup"><span data-stu-id="f6121-124">Select the column you want to follow the inserted columns and, from the **Edit** menu, click **Paste**.</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="f6121-125">Pour copier des données d'une table vers une autre</span><span class="sxs-lookup"><span data-stu-id="f6121-125">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="f6121-126">Conformez-vous aux instructions relatives à la copie des définitions de colonne ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="f6121-126">Follow the directions for copying column definitions above.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f6121-127">Avant de commencer à copier des données d'une table vers une autre, assurez-vous que les types de données contenus dans les colonnes de destination sont compatibles avec ceux des données des colonnes sources.</span><span class="sxs-lookup"><span data-stu-id="f6121-127">Before you begin to copy data from one table to another, make sure that the data types in the destination columns are compatible with the data types of the source columns</span></span>  
  
2.  <span data-ttu-id="f6121-128">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur le nœud **Vues** , puis cliquez sur **Nouvelle vue**.</span><span class="sxs-lookup"><span data-stu-id="f6121-128">In Object Explorer, right-click the **Views** node, and then click **New View**.</span></span>  
  
3.  <span data-ttu-id="f6121-129">Dans le menu **Concepteur de requêtes** , pointez sur **Modifier le type**, puis cliquez sur **Insérer les résultats**.</span><span class="sxs-lookup"><span data-stu-id="f6121-129">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
4.  <span data-ttu-id="f6121-130">Dans la boîte de dialogue **Choisir la table cible pour la requête Insérer les résultats** , sélectionnez la table dans laquelle vous souhaitez copier les données, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6121-130">In the **Choose Target Table for Insert Results** dialog box, select the table into which you want to copy the data, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f6121-131">Si vous copiez des lignes au sein d'une même table, vous pouvez ajouter la table source comme table de destination.</span><span class="sxs-lookup"><span data-stu-id="f6121-131">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f6121-132">Le**Concepteur de requêtes** ne peut pas déterminer à l'avance les tables et vues qu'il est possible de mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="f6121-132">**Query Designer** cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="f6121-133">Par conséquent, la liste des tables fournie dans la boîte de dialogue **Choisir la table cible pour la requête Insérer les résultats** affiche toutes les tables et vues disponibles dans la connexion de données sur laquelle porte la requête, même celles vers lesquelles il est impossible de copier des lignes.</span><span class="sxs-lookup"><span data-stu-id="f6121-133">Therefore, the list of tables in the **Choose Target Table for Insert Results** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
5.  <span data-ttu-id="f6121-134">Cliquez avec le bouton droit dans le corps du volet Schéma et, dans le menu contextuel, cliquez sur **Add Table to Diagram**.</span><span class="sxs-lookup"><span data-stu-id="f6121-134">Right-click in the body of the diagram pane and, from the shortcut menu, click **Add Table to Diagram**.</span></span>  
  
6.  <span data-ttu-id="f6121-135">Dans la boîte de dialogue **Ajouter une table** , sélectionnez chaque table de laquelle vous souhaitez copier des données, cliquez sur **Ajouter**, puis sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="f6121-135">In the **Add Table** dialog box, select each table from which you want to copy data, click **Add**, and then click **Close**.</span></span>  
  
     <span data-ttu-id="f6121-136">Les tables apparaissent dans le volet Schéma sous une forme abrégée.</span><span class="sxs-lookup"><span data-stu-id="f6121-136">The tables, in an abbreviated form, appear in the diagram pane.</span></span>  
  
7.  <span data-ttu-id="f6121-137">Dans les tables abrégées, activez les cases à cocher correspondant aux colonnes dont vous souhaitez copier des données.</span><span class="sxs-lookup"><span data-stu-id="f6121-137">In the abbreviated tables, check the boxes for any columns from which you want to copy data.</span></span>  
  
8.  <span data-ttu-id="f6121-138">Dans la colonne **Ajouter** du volet Critères, pour chaque colonne cible, choisissez une colonne dont vous souhaitez copier des données.</span><span class="sxs-lookup"><span data-stu-id="f6121-138">In the criteria pane, in the **Append** column, for each target column choose a column from which you want to copy data.</span></span>  
  
9. <span data-ttu-id="f6121-139">Spécifiez les lignes à copier en entrant des conditions de recherche dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="f6121-139">Specify the rows to copy by entering search conditions in the criteria pane.</span></span> <span data-ttu-id="f6121-140">Pour plus d’informations, consultez [Spécifier des conditions de recherche &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f6121-140">For details, see [Specify Search Conditions &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="f6121-141">Si vous ne spécifiez pas de condition de recherche, toutes les lignes de la table source seront copiées vers la table de destination.</span><span class="sxs-lookup"><span data-stu-id="f6121-141">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
10. <span data-ttu-id="f6121-142">Si vous souhaitez copier des informations de synthèse, spécifiez **des options Group by** .</span><span class="sxs-lookup"><span data-stu-id="f6121-142">If you want to copy summary information, specify **Group By** options.</span></span> <span data-ttu-id="f6121-143">Pour plus d’informations, consultez [Synthétiser ou regrouper des valeurs de toutes les lignes d’une table &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f6121-143">For details, see [Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span></span>  
  
11. <span data-ttu-id="f6121-144">Cliquez sur le bouton **Exécuter SQL** pour exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="f6121-144">Click the **Execute SQL button** to run the query.</span></span>  
  
     <span data-ttu-id="f6121-145">Lorsque vous exécutez une requête Insert Values, aucun résultat n'apparaît dans le [volet Résultats](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f6121-145">When you execute an insert results query, no results are reported in the [Results Pane](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="f6121-146">En fait, un message indiquant le nombre de lignes copiées s'affiche.</span><span class="sxs-lookup"><span data-stu-id="f6121-146">Instead, a message appears indicating how many rows were copied.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f6121-147">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f6121-147">Using Transact-SQL</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="f6121-148">Pour copier des définitions de colonne d'une table vers une autre</span><span class="sxs-lookup"><span data-stu-id="f6121-148">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="f6121-149">Vous ne pouvez pas copier des colonnes individuelles d'une table dans une autre table existante à l'aide d'instructions Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="f6121-149">You cannot copy individual columns from one table to another existing table by using Transact-SQL statements.</span></span> <span data-ttu-id="f6121-150">Toutefois, vous pouvez créer une table dans le groupe de fichiers par défaut et y insère les lignes résultant de la requête à l'aide de SELECT INTO.</span><span class="sxs-lookup"><span data-stu-id="f6121-150">However, you can create a new table in the default filegroup and inserts the resulting rows from the query into it by using SELECT INTO.</span></span> <span data-ttu-id="f6121-151">Pour plus d’informations, consultez [Clause INTO &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f6121-151">For more information, see [INTO Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="f6121-152">Pour copier des données d'une table vers une autre</span><span class="sxs-lookup"><span data-stu-id="f6121-152">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="f6121-153">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6121-153">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f6121-154">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f6121-154">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f6121-155">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f6121-155">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.EmployeeSales  
    ( BusinessEntityID   varchar(11) NOT NULL,  
      SalesYTD money NOT NULL  
    );  
    GO  
    INSERT INTO dbo.EmployeeSales  
        SELECT BusinessEntityID, SalesYTD   
        FROM Sales.SalesPerson;  
    GO  
    ```  
  
  
