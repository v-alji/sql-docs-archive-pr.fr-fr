---
title: Filtres de jointure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server replication], join
- publications [SQL Server replication], join filters
- merge replication join filters [SQL Server replication]
- join filters
ms.assetid: dd78fd8f-56e3-4582-9abd-6bc25c91e075
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b97e7d7b53e6a3fdb242d1272e013bbd45f0ed17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599940"
---
# <a name="join-filters"></a><span data-ttu-id="a33c5-102">filtres de jointure</span><span class="sxs-lookup"><span data-stu-id="a33c5-102">Join Filters</span></span>
  <span data-ttu-id="a33c5-103">Un filtre de jointure permet de filtrer une table en fonction du filtrage d'une table associée dans la publication.</span><span class="sxs-lookup"><span data-stu-id="a33c5-103">A join filter allows a table to be filtered based on how a related table in the publication is filtered.</span></span> <span data-ttu-id="a33c5-104">En général, une table parente est filtrée à l'aide d'un filtre paramétré ; un ou plusieurs filtres de jointure sont ensuite définis à peu près de la même façon que vous définissez une jointure entre des tables.</span><span class="sxs-lookup"><span data-stu-id="a33c5-104">Typically a parent table is filtered using a parameterized filter; then one or more join filters are defined in much the same way that you define a join between tables.</span></span> <span data-ttu-id="a33c5-105">Les filtres de jointure étendent le filtre paramétré de telle façon que les données des tables liées soient répliquées seulement si elles correspondent à la clause du filtre de jointure.</span><span class="sxs-lookup"><span data-stu-id="a33c5-105">The join filters extend the parameterized filter so that the data in the related tables is only replicated if it matches the join filter clause.</span></span>  
  
 <span data-ttu-id="a33c5-106">En règle générale, les filtres de jointure suivent les relations clé primaire/clé étrangère définies pour les tables auxquelles ils sont appliqués, mais ils ne sont pas strictement limités à ces relations.</span><span class="sxs-lookup"><span data-stu-id="a33c5-106">Join filters typically follow the primary key/foreign key relationships defined for the tables to which they are applied, but they are not limited strictly to primary key/foreign key relationships.</span></span> <span data-ttu-id="a33c5-107">Le filtre de jointure peut être basé sur toute logique comparant des données associées dans deux tables.</span><span class="sxs-lookup"><span data-stu-id="a33c5-107">The join filter can be based on any logic that compares related data in two tables.</span></span>  
  
 <span data-ttu-id="a33c5-108">Supposons les tables suivantes dans la base de données exemple [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] , qui sont associées via des relations de clé primaire à clé étrangère :</span><span class="sxs-lookup"><span data-stu-id="a33c5-108">Consider the following tables in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database, which are related through primary key to foreign key relationships:</span></span>  
  
-   <span data-ttu-id="a33c5-109">**HumanResources.Employee**</span><span class="sxs-lookup"><span data-stu-id="a33c5-109">**HumanResources.Employee**</span></span>  
  
-   <span data-ttu-id="a33c5-110">**Sales.SalesOrderHeader**</span><span class="sxs-lookup"><span data-stu-id="a33c5-110">**Sales.SalesOrderHeader**</span></span>  
  
-   <span data-ttu-id="a33c5-111">**Sales.SalesOrderDetail**</span><span class="sxs-lookup"><span data-stu-id="a33c5-111">**Sales.SalesOrderDetail**</span></span>  
  
 <span data-ttu-id="a33c5-112">Ces tables peuvent être utilisées dans une application d'aide aux forces de ventes mobiles, mais elles doivent être filtrées de façon à ce que chaque commercial de la table **HumanResources.Employee** reçoive seulement les données se rapportant aux commandes de ses clients.</span><span class="sxs-lookup"><span data-stu-id="a33c5-112">These tables could be used in an application to support a mobile sales force, but they must be filtered so that each sales person in the **HumanResources.Employee** table receives only the data relevant to their customers' orders.</span></span>  
  
 <span data-ttu-id="a33c5-113">La première étape consiste à définir un filtre paramétré sur la table parente, qui est dans cet exemple la table **HumanResources.Employee** .</span><span class="sxs-lookup"><span data-stu-id="a33c5-113">The first step is to define a parameterized filter on the parent table, which in this example is the **HumanResources.Employee** table.</span></span> <span data-ttu-id="a33c5-114">Cette table comprend la colonne **LoginID**, qui contient le nom de connexion de chaque employé sous la forme *domain\login*.</span><span class="sxs-lookup"><span data-stu-id="a33c5-114">This table includes the column **LoginID**, which contains the login for each employee in the form *domain\login*.</span></span> <span data-ttu-id="a33c5-115">Pour filtrer cette table de façon à ce que chaque employé reçoive seulement les données qui le concernent, spécifiez la clause de filtre paramétré suivante :</span><span class="sxs-lookup"><span data-stu-id="a33c5-115">To filter this table so that each employee receives only the data related to them, specify a parameterized filter clause of:</span></span>  
  
```  
LoginID = SUSER_SNAME()  
```  
  
 <span data-ttu-id="a33c5-116">Ce filtre garantit que l'abonnement de chaque employé contient seulement les données de la table **HumanResources.Employee** qui se rapportent à cet employé (une seule ligne dans le cas présent).</span><span class="sxs-lookup"><span data-stu-id="a33c5-116">This filter ensures that each employee's subscription only contains data from the **HumanResources.Employee** table that is relevant to that employee (which in this case is a single row).</span></span> <span data-ttu-id="a33c5-117">Pour plus d'informations, voir [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="a33c5-117">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 <span data-ttu-id="a33c5-118">L'étape suivante consiste à étendre ce filtre à chacune des tables associées, à l'aide d'une syntaxe similaire à celle qui est utilisée pour spécifier une jointure entre deux tables.</span><span class="sxs-lookup"><span data-stu-id="a33c5-118">The next step is to extend this filter to each of the related tables, using syntax similar to that used to specify a join between two tables.</span></span> <span data-ttu-id="a33c5-119">La première clause du filtre de jointure est :</span><span class="sxs-lookup"><span data-stu-id="a33c5-119">The first join filter clause is:</span></span>  
  
```  
Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
```  
  
 <span data-ttu-id="a33c5-120">Ceci fait que l'abonnement contient seulement les données des commandes concernant chacun des commerciaux.</span><span class="sxs-lookup"><span data-stu-id="a33c5-120">This ensures the subscription contains only the order data relevant to each sales person.</span></span> <span data-ttu-id="a33c5-121">La seconde clause du filtre de jointure est :</span><span class="sxs-lookup"><span data-stu-id="a33c5-121">The second join filter clause is:</span></span>  
  
```  
SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
```  
  
 <span data-ttu-id="a33c5-122">Ceci fait que l'abonnement contient seulement les données détaillées associées aux données des commandes pour chacun des commerciaux.</span><span class="sxs-lookup"><span data-stu-id="a33c5-122">This ensures the subscription contains only the detail data related to the order data for each sales person.</span></span> <span data-ttu-id="a33c5-123">Cet exemple montre une table jointe à chaque point ; il est également possible de joindre plusieurs tables à chaque point.</span><span class="sxs-lookup"><span data-stu-id="a33c5-123">This example shows a single table being joined at each point; it is also possible to join more than one table at each point.</span></span>  
  
 <span data-ttu-id="a33c5-124">Les filtres de jointure peuvent être ajoutés un par un via l'Assistant Nouvelle publication et la boîte de dialogue **Propriétés de la publication** , ou bien ils peuvent être ajoutés par programmation.</span><span class="sxs-lookup"><span data-stu-id="a33c5-124">Join filters can be added one at a time through the New Publication Wizard and the **Publication Properties** dialog box, or they can be added programmatically.</span></span> <span data-ttu-id="a33c5-125">Ils peuvent aussi être générés automatiquement via l'Assistant Nouvelle publication : vous spécifiez un filtre de lignes pour une table et des filtres de jointure sont appliqués à toutes les tables associées.</span><span class="sxs-lookup"><span data-stu-id="a33c5-125">They can also be generated automatically through the New Publication Wizard: you specify a row filter for a table and join filters are applied to all related tables.</span></span> <span data-ttu-id="a33c5-126">Pour plus d’informations, consultez [Définir et modifier un filtre de jointure entre des articles de fusion](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Générer automatiquement un ensemble de filtres de jointure entre des articles de fusion &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md), et [Définir un article](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="a33c5-126">For more information, see [Define and Modify a Join Filter Between Merge Articles](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Automatically Generate a Set of Join Filters Between Merge Articles &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md), and [Define an Article](../publish/define-an-article.md).</span></span>  
  
## <a name="optimizing-join-filter-performance"></a><span data-ttu-id="a33c5-127">Optimisation des performances des filtres de jointure</span><span class="sxs-lookup"><span data-stu-id="a33c5-127">Optimizing Join Filter Performance</span></span>  
 <span data-ttu-id="a33c5-128">Les performances des filtres de jointure peuvent être optimisées en suivant ces conseils :</span><span class="sxs-lookup"><span data-stu-id="a33c5-128">Join filter performance can be optimized by following these guidelines:</span></span>  
  
-   <span data-ttu-id="a33c5-129">Limitez le nombre de tables dans la hiérarchie du filtre de jointure.</span><span class="sxs-lookup"><span data-stu-id="a33c5-129">Limit the number of tables in the join filter hierarchy.</span></span>  
  
     <span data-ttu-id="a33c5-130">Les filtres de jointure peuvent impliquer un nombre illimité de tables, mais des filtres avec un grand nombre de tables peuvent avoir un impact significatif sur les performances lors du traitement de la fusion.</span><span class="sxs-lookup"><span data-stu-id="a33c5-130">Join Filters can involve an unlimited number of tables, but filters with a large number of tables can significantly impact performance during merge processing.</span></span> <span data-ttu-id="a33c5-131">Si vous générez des filtres de jointure pour au moins cinq tables, envisagez d'autres solutions : ne filtrez pas les petites tables, les tables qui ne changent pas ou les tables de recherche principales.</span><span class="sxs-lookup"><span data-stu-id="a33c5-131">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="a33c5-132">Utilisez des filtres de jointure seulement entre des tables qui doivent être partitionnées entre des abonnements.</span><span class="sxs-lookup"><span data-stu-id="a33c5-132">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="a33c5-133">Définissez l'option **join unique key** à **True** là où c'est approprié.</span><span class="sxs-lookup"><span data-stu-id="a33c5-133">Set the **join unique key** option to **True** where appropriate.</span></span>  
  
     <span data-ttu-id="a33c5-134">Le traitement de fusion a des possibilités d'optimisation des performances spéciales si la colonne jointe dans le parent est unique.</span><span class="sxs-lookup"><span data-stu-id="a33c5-134">The merge process has special performance optimizations available if the joined column in the parent is unique.</span></span> <span data-ttu-id="a33c5-135">Si la condition de jointure est basée sur une colonne unique, définissez l'option **join unique key** pour le filtre de jointure.</span><span class="sxs-lookup"><span data-stu-id="a33c5-135">If the join condition is based on a unique column, set the **join unique key** option for the join filter.</span></span> <span data-ttu-id="a33c5-136">Pour des informations sur la définition de cette option, consultez les rubriques Procédure dont la liste figure dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="a33c5-136">For information about setting this option, see the how-to topics listed in the previous section.</span></span>  
  
-   <span data-ttu-id="a33c5-137">Vérifiez que les colonnes référencées dans les filtres de jointure sont indexées.</span><span class="sxs-lookup"><span data-stu-id="a33c5-137">Ensure that the columns referenced in join filters are indexed.</span></span>  
  
     <span data-ttu-id="a33c5-138">Si les colonnes référencées dans le filtre sont indexées, la réplication peut traiter les filtres plus efficacement.</span><span class="sxs-lookup"><span data-stu-id="a33c5-138">If the columns referenced in the filter are indexed, replication can process the filters more efficiently.</span></span>  
  
-   <span data-ttu-id="a33c5-139">Ne créez pas de filtres de lignes équivalents aux filtres de jointure.</span><span class="sxs-lookup"><span data-stu-id="a33c5-139">Do not create row filters that mimic join filters.</span></span>  
  
     <span data-ttu-id="a33c5-140">Il est possible de créer des filtres de lignes qui sont équivalents à des filtres de jointure en utilisant une sous-requête dans une clause WHERE, comme ceci :</span><span class="sxs-lookup"><span data-stu-id="a33c5-140">It is possible to create row filters that mimic join filters by using a subquery in a WHERE clause, such as:</span></span>  
  
    ```  
    WHERE Customer.SalesPersonID IN (SELECT EmployeeID FROM Employee WHERE LoginID = SUSER_SNAME())   
    ```  
  
     <span data-ttu-id="a33c5-141">Il est fortement recommandé que toutes les logiques de ce type soient exprimées dans un filtre de jointure plutôt que dans une sous-requête.</span><span class="sxs-lookup"><span data-stu-id="a33c5-141">It is strongly recommended that all such logic be expressed in a join filter rather than a subquery.</span></span> <span data-ttu-id="a33c5-142">Si votre application requiert qu'un filtre de lignes utilise une sous-requête, vérifiez que la sous-requête référence seulement des données de consultation qui ne font pas l'objet de modifications.</span><span class="sxs-lookup"><span data-stu-id="a33c5-142">If your application requires a row filter to use a subsquery, ensure that the subquery only references lookup data that does not change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33c5-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a33c5-143">See Also</span></span>  
 <span data-ttu-id="a33c5-144">[Filtrer des données publiées en vue de la réplication de fusion](filter-published-data-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="a33c5-144">[Filter Published Data for Merge Replication](filter-published-data-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="a33c5-145">Filtres de lignes paramétrés</span><span class="sxs-lookup"><span data-stu-id="a33c5-145">Parameterized Row Filters</span></span>](parameterized-filters-parameterized-row-filters.md)  
  
  
