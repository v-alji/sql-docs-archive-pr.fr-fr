---
title: 'Leçon 3 : définition d’un dataset destiné à un rapport de table (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ee93dfcb-8f52-4d63-b4f6-0d38e00fd350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 33fe48a60db2e7d15d205a4bff6205347f95c61c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603306"
---
# <a name="lesson-3-defining-a-dataset-for-the-table-report-reporting-services"></a><span data-ttu-id="54db6-102">Leçon 3 : définition d'un dataset destiné à un rapport de table (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="54db6-102">Lesson 3: Defining a Dataset for the Table Report (Reporting Services)</span></span>
  <span data-ttu-id="54db6-103">Après avoir défini une source de données, vous devez spécifier un dataset.</span><span class="sxs-lookup"><span data-stu-id="54db6-103">After you define the data source, you need to define a dataset.</span></span> <span data-ttu-id="54db6-104">Dans [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], les données utilisées par les rapports sont contenues dans des *datasets*.</span><span class="sxs-lookup"><span data-stu-id="54db6-104">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], data that you use in reports is contained in a *dataset*.</span></span> <span data-ttu-id="54db6-105">Les datasets contiennent un pointeur qui renvoient à la source des données, la requête que doit utiliser le rapport ainsi que des champs et variables calculées.</span><span class="sxs-lookup"><span data-stu-id="54db6-105">A dataset includes a pointer to a data source and a query to be used by the report, as well as calculated fields and variables.</span></span>  
  
 <span data-ttu-id="54db6-106">Le Concepteur de requêtes du Concepteur de rapports permet de définir des requêtes.</span><span class="sxs-lookup"><span data-stu-id="54db6-106">You can use the query designer in Report Designer to design the query.</span></span> <span data-ttu-id="54db6-107">Pour ce didacticiel, vous allez créer une requête qui extrait les informations sur les commandes à partir de la [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] base de données **2008** .</span><span class="sxs-lookup"><span data-stu-id="54db6-107">For this tutorial, you will create a query that retrieves sales order information from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]**2008** database.</span></span>  
  
### <a name="to-define-a-transact-sql-query-for-report-data"></a><span data-ttu-id="54db6-108">Pour définir une requête Transact-SQL pour les données du rapport</span><span class="sxs-lookup"><span data-stu-id="54db6-108">To define a Transact-SQL query for report data</span></span>  
  
1.  <span data-ttu-id="54db6-109">Dans le volet **données du rapport** , cliquez sur **nouveau**, puis sur **DataSet...**. La boîte de dialogue **Propriétés du DataSet** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="54db6-109">In the **Report Data** pane, click **New**, and then click **Dataset...**. The **Dataset Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="54db6-110">Dans la zone **Nom** , tapez **AdventureWorksDataset**.</span><span class="sxs-lookup"><span data-stu-id="54db6-110">In the **Name** box, type **AdventureWorksDataset**.</span></span>  
  
3.  <span data-ttu-id="54db6-111">Cliquez sur **Utiliser un dataset incorporé dans mon rapport**.</span><span class="sxs-lookup"><span data-stu-id="54db6-111">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="54db6-112">Assurez-vous que le nom de votre source de données, AdventureWorks2012, se trouve dans la zone de texte **source de données** , et que le **type de requête** est **texte**.</span><span class="sxs-lookup"><span data-stu-id="54db6-112">Make sure the name of your data source, AdventureWorks2012, is in the **Data source** text box, and that the **Query type** is **Text**.</span></span>  
  
5.  <span data-ttu-id="54db6-113">Tapez ou copiez et collez la requête Transact-SQL ci-après dans la zone **Requête** .</span><span class="sxs-lookup"><span data-stu-id="54db6-113">Type, or copy and paste, the following Transact-SQL query into the **Query** box.</span></span>  
  
    ```  
    SELECT   
       soh.OrderDate AS [Date],   
       soh.SalesOrderNumber AS [Order],   
       pps.Name AS Subcat, pp.Name as Product,    
       SUM(sd.OrderQty) AS Qty,  
       SUM(sd.LineTotal) AS LineTotal  
    FROM Sales.SalesPerson sp   
       INNER JOIN Sales.SalesOrderHeader AS soh   
          ON sp.BusinessEntityID = soh.SalesPersonID  
       INNER JOIN Sales.SalesOrderDetail AS sd   
          ON sd.SalesOrderID = soh.SalesOrderID  
       INNER JOIN Production.Product AS pp   
          ON sd.ProductID = pp.ProductID  
       INNER JOIN Production.ProductSubcategory AS pps   
          ON pp.ProductSubcategoryID = pps.ProductSubcategoryID  
       INNER JOIN Production.ProductCategory AS ppc   
          ON ppc.ProductCategoryID = pps.ProductCategoryID  
    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name,   
       soh.SalesPersonID  
    HAVING ppc.Name = 'Clothing'  
    ```  
  
6.  <span data-ttu-id="54db6-114">(Facultatif) Cliquez sur le bouton **Concepteur de requêtes** .</span><span class="sxs-lookup"><span data-stu-id="54db6-114">(Optional) Click the **Query Designer** button.</span></span> <span data-ttu-id="54db6-115">La requête est affichée dans le Concepteur de requêtes textuel.</span><span class="sxs-lookup"><span data-stu-id="54db6-115">The query is displayed in the text-based query designer.</span></span> <span data-ttu-id="54db6-116">Vous pouvez utiliser le concepteur de requêtes graphique en cliquant sur l’option **Modifier en tant que texte**.</span><span class="sxs-lookup"><span data-stu-id="54db6-116">You can toggle to the graphical query designer by clicking **Edit As Text**.</span></span> <span data-ttu-id="54db6-117">Affichez les résultats de la requête en cliquant sur le bouton exécuter **( !)** dans la barre d’outils du concepteur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="54db6-117">View the results of the query by clicking the run **(!)** button on the query designer toolbar.</span></span>  
  
     <span data-ttu-id="54db6-118">Vous pouvez consulter les données contenues dans six champs à partir de quatre tables différentes de la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54db6-118">You see the data from six fields from four different tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="54db6-119">La requête utilise des fonctionnalités Transact-SQL telles que des alias.</span><span class="sxs-lookup"><span data-stu-id="54db6-119">The query makes use of Transact-SQL functionality such as aliases.</span></span> <span data-ttu-id="54db6-120">Par exemple, la table SalesOrderHeader est intitulée soh.</span><span class="sxs-lookup"><span data-stu-id="54db6-120">For example, the SalesOrderHeader table is called soh.</span></span>  
  
     <span data-ttu-id="54db6-121">Cliquez sur **OK** pour quitter le Concepteur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="54db6-121">Click **OK** to exit the query designer.</span></span>  
  
7.  <span data-ttu-id="54db6-122">Cliquez sur **OK** pour quitter la boîte de dialogue **Propriétés du dataset** .</span><span class="sxs-lookup"><span data-stu-id="54db6-122">Click **OK** to exit the **Dataset Properties** dialog box.</span></span>  
  
     <span data-ttu-id="54db6-123">Les champs et votre dataset **AdventureWorksDataset** s’affichent dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="54db6-123">Your **AdventureWorksDataset** dataset and fields appear in the Report Data pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="54db6-124">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="54db6-124">Next Task</span></span>  
 <span data-ttu-id="54db6-125">Vous venez de spécifier une requête qui permet d'extraire les données pour votre rapport.</span><span class="sxs-lookup"><span data-stu-id="54db6-125">You have successfully specified a query that retrieves data for your report.</span></span> <span data-ttu-id="54db6-126">Vous allez ensuite créer la disposition du rapport.</span><span class="sxs-lookup"><span data-stu-id="54db6-126">Next, you will create the report layout.</span></span> <span data-ttu-id="54db6-127">Consultez [Leçon 4 : ajout d’une table au rapport &#40;Reporting Services&#41;](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="54db6-127">See [Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;](lesson-4-adding-a-table-to-the-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54db6-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54db6-128">See Also</span></span>  
 <span data-ttu-id="54db6-129">[Outils de conception de requête dans Concepteur de rapports SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="54db6-129">[Query Design Tools in Report Designer SQL Server Data Tools &#40;SSRS&#41;](report-data/query-design-tools-ssrs.md) </span></span>  
 <span data-ttu-id="54db6-130">[Type de connexion SQL Server &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="54db6-130">[SQL Server Connection Type &#40;SSRS&#41;](report-data/sql-server-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="54db6-131">Tutoriel : Écriture d’instructions Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54db6-131">Tutorial: Writing Transact-SQL Statements</span></span>](../t-sql/tutorial-writing-transact-sql-statements.md)  
  
  
