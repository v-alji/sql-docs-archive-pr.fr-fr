---
title: Données hiérarchiques (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [SQL Server], tables to support
- hierarchyid [Database Engine], concepts
- hierarchical tables [Database Engine]
- SqlHierarchyId
- hierarchyid [Database Engine]
- hierarchical queries [SQL Server], using hierarchyid data type
ms.assetid: 19aefa9a-fbc2-4b22-92cf-67b8bb01671c
author: rothja
ms.author: jroth
ms.openlocfilehash: 351a5a4aa6bc1655b8da5fced3e51385dd498bdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604449"
---
# <a name="hierarchical-data-sql-server"></a><span data-ttu-id="a4f18-102">Données hiérarchiques (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4f18-102">Hierarchical Data (SQL Server)</span></span>
  <span data-ttu-id="a4f18-103">Le `hierarchyid` type de données intégré facilite le stockage et l’interrogation des données hiérarchiques.</span><span class="sxs-lookup"><span data-stu-id="a4f18-103">The built-in `hierarchyid` data type makes it easier to store and query hierarchical data.</span></span> <span data-ttu-id="a4f18-104">`hierarchyid`est optimisé pour représenter les arborescences, qui sont le type le plus courant de données hiérarchiques.</span><span class="sxs-lookup"><span data-stu-id="a4f18-104">`hierarchyid` is optimized for representing trees, which are the most common type of hierarchical data.</span></span>  
  
 <span data-ttu-id="a4f18-105">Les données hiérarchiques sont définies comme un jeu d'éléments de données liés entre eux par des relations hiérarchiques.</span><span class="sxs-lookup"><span data-stu-id="a4f18-105">Hierarchical data is defined as a set of data items that are related to each other by hierarchical relationships.</span></span> <span data-ttu-id="a4f18-106">Des relations hiérarchiques existent dans lesquelles un élément de données est le parent d'un autre élément.</span><span class="sxs-lookup"><span data-stu-id="a4f18-106">Hierarchical relationships exist where one item of data is the parent of another item.</span></span> <span data-ttu-id="a4f18-107">Voici quelques exemples de données hiérarchiques communément stockées dans les bases de données :</span><span class="sxs-lookup"><span data-stu-id="a4f18-107">Examples of the hierarchical data that is commonly stored in databases include the following:</span></span>  
  
-   <span data-ttu-id="a4f18-108">Structure d'organisation</span><span class="sxs-lookup"><span data-stu-id="a4f18-108">An organizational structure</span></span>  
  
-   <span data-ttu-id="a4f18-109">Système de fichiers</span><span class="sxs-lookup"><span data-stu-id="a4f18-109">A file system</span></span>  
  
-   <span data-ttu-id="a4f18-110">Ensemble de tâches dans un projet</span><span class="sxs-lookup"><span data-stu-id="a4f18-110">A set of tasks in a project</span></span>  
  
-   <span data-ttu-id="a4f18-111">Taxonomie de termes langagiers</span><span class="sxs-lookup"><span data-stu-id="a4f18-111">A taxonomy of language terms</span></span>  
  
-   <span data-ttu-id="a4f18-112">Graphique de liens entre pages Web</span><span class="sxs-lookup"><span data-stu-id="a4f18-112">A graph of links between Web pages</span></span>  
  
 <span data-ttu-id="a4f18-113">Le type de données [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) permet de créer des tables avec une structure hiérarchique ou de décrire la structure hiérarchique de données stockées à un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="a4f18-113">Use [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) as a data type to create tables with a hierarchical structure, or to describe the hierarchical structure of data that is stored in another location.</span></span> <span data-ttu-id="a4f18-114">Utilisez les [fonctions hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) de [!INCLUDE[tsql](../includes/tsql-md.md)] pour interroger et gérer les données hiérarchiques.</span><span class="sxs-lookup"><span data-stu-id="a4f18-114">Use the [hierarchyid functions](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) in [!INCLUDE[tsql](../includes/tsql-md.md)] to query and manage hierarchical data.</span></span>  
  
##  <a name="key-properties-of-hierarchyid"></a><a name="keyprops"></a> <span data-ttu-id="a4f18-115">Propriétés principales de hierarchyid</span><span class="sxs-lookup"><span data-stu-id="a4f18-115">Key Properties of hierarchyid</span></span>  
 <span data-ttu-id="a4f18-116">Une valeur du type de données `hierarchyid` représente une position dans une hiérarchie d'arborescence.</span><span class="sxs-lookup"><span data-stu-id="a4f18-116">A value of the `hierarchyid` data type represents a position in a tree hierarchy.</span></span> <span data-ttu-id="a4f18-117">Les valeurs de `hierarchyid` ont les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4f18-117">Values for `hierarchyid` have the following properties:</span></span>  
  
-   <span data-ttu-id="a4f18-118">Extrêmement compact</span><span class="sxs-lookup"><span data-stu-id="a4f18-118">Extremely compact</span></span>  
  
     <span data-ttu-id="a4f18-119">Le nombre moyen de bits nécessaires pour représenter un nœud dans une arborescence avec *n* nœuds dépend de la sortance moyenne (nombre moyen d’enfants d’un nœud).</span><span class="sxs-lookup"><span data-stu-id="a4f18-119">The average number of bits that are required to represent a node in a tree with *n* nodes depends on the average fanout (the average number of children of a node).</span></span> <span data-ttu-id="a4f18-120">Pour les petites sortances (de 0 à 7), la taille est d’environ 6\*logA*n* bits, où A est la sortance moyenne.</span><span class="sxs-lookup"><span data-stu-id="a4f18-120">For small fanouts, (0-7) the size is about 6\*logA*n* bits, where A is the average fanout.</span></span> <span data-ttu-id="a4f18-121">Un nœud dans une hiérarchie d'organisation de 100 000 personnes avec une sortance moyenne de 6 niveaux prend approximativement 38 bits.</span><span class="sxs-lookup"><span data-stu-id="a4f18-121">A node in an organizational hierarchy of 100,000 people with an average fanout of 6 levels takes about 38 bits.</span></span> <span data-ttu-id="a4f18-122">Ce chiffre est arrondi à 40 bits, ou 5 octets, pour le stockage.</span><span class="sxs-lookup"><span data-stu-id="a4f18-122">This is rounded up to 40 bits, or 5 bytes, for storage.</span></span>  
  
-   <span data-ttu-id="a4f18-123">La comparaison est effectuée dans l'ordre à profondeur prioritaire</span><span class="sxs-lookup"><span data-stu-id="a4f18-123">Comparison is in depth-first order</span></span>  
  
     <span data-ttu-id="a4f18-124">Avec deux `hierarchyid` valeurs **a** et **b**, **un<b** signifie que a est avant b dans un parcours à profondeur prioritaire de l’arborescence.</span><span class="sxs-lookup"><span data-stu-id="a4f18-124">Given two `hierarchyid` values **a** and **b**, **a<b** means a comes before b in a depth-first traversal of the tree.</span></span> <span data-ttu-id="a4f18-125">Les index sur les types de données `hierarchyid` sont dans l'ordre à profondeur prioritaire, et les nœuds proches les uns des autres dans un parcours à profondeur prioritaire sont stockés les uns à côté des autres.</span><span class="sxs-lookup"><span data-stu-id="a4f18-125">Indexes on `hierarchyid` data types are in depth-first order, and nodes close to each other in a depth-first traversal are stored near each other.</span></span> <span data-ttu-id="a4f18-126">Par exemple, les enfants d'un enregistrement sont stockés à côté de cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="a4f18-126">For example, the children of a record are stored adjacent to that record.</span></span>  
  
-   <span data-ttu-id="a4f18-127">Prise en charge des insertions et suppressions arbitraires</span><span class="sxs-lookup"><span data-stu-id="a4f18-127">Support for arbitrary insertions and deletions</span></span>  
  
     <span data-ttu-id="a4f18-128">En utilisant la méthode [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) , il est toujours possible de générer un frère à droite d'un nœud donné, à gauche d'un nœud donné, ou entre les deux frères.</span><span class="sxs-lookup"><span data-stu-id="a4f18-128">By using the [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) method, it is always possible to generate a sibling to the right of any given node, to the left of any given node, or between any two siblings.</span></span> <span data-ttu-id="a4f18-129">La propriété de comparaison est maintenue lorsqu'un nombre arbitraire de nœuds est inséré ou supprimé dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="a4f18-129">The comparison property is maintained when an arbitrary number of nodes is inserted or deleted from the hierarchy.</span></span> <span data-ttu-id="a4f18-130">La plupart des insertions et suppressions préservent la propriété de compacité.</span><span class="sxs-lookup"><span data-stu-id="a4f18-130">Most insertions and deletions preserve the compactness property.</span></span> <span data-ttu-id="a4f18-131">Toutefois, les insertions entre deux nœuds produiront des valeurs hierarchyid avec une représentation légèrement moins compacte.</span><span class="sxs-lookup"><span data-stu-id="a4f18-131">However, insertions between two nodes will produce hierarchyid values with a slightly less compact representation.</span></span>  
  
  
##  <a name="limitations-of-hierarchyid"></a><a name="limits"></a> <span data-ttu-id="a4f18-132">Limites de hierarchyid</span><span class="sxs-lookup"><span data-stu-id="a4f18-132">Limitations of hierarchyid</span></span>  
 <span data-ttu-id="a4f18-133">Le `hierarchyid` type de données présente les limitations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4f18-133">The `hierarchyid` data type has the following limitations:</span></span>  
  
-   <span data-ttu-id="a4f18-134">Une colonne de type `hierarchyid` ne représente pas automatiquement une arborescence.</span><span class="sxs-lookup"><span data-stu-id="a4f18-134">A column of type `hierarchyid` does not automatically represent a tree.</span></span> <span data-ttu-id="a4f18-135">Il appartient à l'application de générer et d'assigner des valeurs `hierarchyid` de telle façon que la relation voulue entre les lignes soit reflétée dans les valeurs.</span><span class="sxs-lookup"><span data-stu-id="a4f18-135">It is up to the application to generate and assign `hierarchyid` values in such a way that the desired relationship between rows is reflected in the values.</span></span> <span data-ttu-id="a4f18-136">Certaines applications peuvent avoir une colonne de type `hierarchyid` qui indique l'emplacement dans une hiérarchie définie dans une autre table.</span><span class="sxs-lookup"><span data-stu-id="a4f18-136">Some applications might have a column of type `hierarchyid` that indicates the location in a hierarchy defined in another table.</span></span>  
  
-   <span data-ttu-id="a4f18-137">Il appartient à l'application de gérer la concurrence en générant et en affectant des valeurs `hierarchyid`</span><span class="sxs-lookup"><span data-stu-id="a4f18-137">It is up to the application to manage concurrency in generating and assigning `hierarchyid` values.</span></span> <span data-ttu-id="a4f18-138">Rien ne garantit que les valeurs `hierarchyid` d'une colonne sont uniques, à moins que l'application utilise une contrainte de clé unique ou applique elle-même l'unicité selon sa propre logique.</span><span class="sxs-lookup"><span data-stu-id="a4f18-138">There is no guarantee that `hierarchyid` values in a column are unique unless the application uses a unique key constraint or enforces uniqueness itself through its own logic.</span></span>  
  
-   <span data-ttu-id="a4f18-139">Les relations hiérarchiques représentées par les valeurs `hierarchyid` ne sont pas appliquées de la même manière qu'une relation de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="a4f18-139">Hierarchical relationships represented by `hierarchyid` values are not enforced like a foreign key relationship.</span></span> <span data-ttu-id="a4f18-140">Dans une relation hiérarchique, il est possible et parfois nécessaire que A ait un enfant B, puis que A soit supprimé, laissant B avec une relation à un enregistrement inexistant.</span><span class="sxs-lookup"><span data-stu-id="a4f18-140">It is possible and sometimes appropriate to have a hierarchical relationship where A has a child B, and then A is deleted leaving B with a relationship to a nonexistent record.</span></span> <span data-ttu-id="a4f18-141">Si ce comportement n'est pas acceptable, l'application doit rechercher des descendants avant de supprimer des parents.</span><span class="sxs-lookup"><span data-stu-id="a4f18-141">If this behavior is unacceptable, the application must query for descendants before deleting parents.</span></span>  
  
  
##  <a name="when-to-use-alternatives-to-hierarchyid"></a><a name="alternatives"></a> <span data-ttu-id="a4f18-142">Quand utiliser des alternatives à hierarchyid</span><span class="sxs-lookup"><span data-stu-id="a4f18-142">When to Use Alternatives to hierarchyid</span></span>  
 <span data-ttu-id="a4f18-143">Les deux alternatives à `hierarchyid` pour représenter des données hiérarchiques sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4f18-143">Two alternatives to `hierarchyid` for representing hierarchical data are:</span></span>  
  
-   <span data-ttu-id="a4f18-144">Parent/enfant</span><span class="sxs-lookup"><span data-stu-id="a4f18-144">Parent/Child</span></span>  
  
-   <span data-ttu-id="a4f18-145">XML</span><span class="sxs-lookup"><span data-stu-id="a4f18-145">XML</span></span>  
  
 <span data-ttu-id="a4f18-146">`hierarchyid` est généralement supérieur à ces alternatives.</span><span class="sxs-lookup"><span data-stu-id="a4f18-146">`hierarchyid` is generally superior to these alternatives.</span></span> <span data-ttu-id="a4f18-147">Toutefois, il existe certaines situations spécifiques, détaillées ci-dessous, pour lesquelles ces alternatives peuvent s'avérer supérieures.</span><span class="sxs-lookup"><span data-stu-id="a4f18-147">However, there are specific situations detailed below where the alternatives are likely superior.</span></span>  
  
### <a name="parentchild"></a><span data-ttu-id="a4f18-148">Parent/enfant</span><span class="sxs-lookup"><span data-stu-id="a4f18-148">Parent/Child</span></span>  
 <span data-ttu-id="a4f18-149">Lors de l'utilisation de l'approche de parent/enfant, chaque ligne contient une référence au parent.</span><span class="sxs-lookup"><span data-stu-id="a4f18-149">When using the Parent/Child approach, each row contains a reference to the parent.</span></span> <span data-ttu-id="a4f18-150">La table suivante définit une table classique qui est utilisée pour contenir les lignes parent et enfant dans une relation parent/enfant :</span><span class="sxs-lookup"><span data-stu-id="a4f18-150">The following table defines a typical table used to contain the parent and the child rows in a Parent/Child relationship:</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE TABLE ParentChildOrg  
   (  
    BusinessEntityID int PRIMARY KEY,  
    ManagerId int REFERENCES ParentChildOrg(BusinessEntityID),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
```  
  
 <span data-ttu-id="a4f18-151">Comparaison de parent/enfant et `hierarchyid` pour les opérations courantes</span><span class="sxs-lookup"><span data-stu-id="a4f18-151">Comparing Parent/Child and `hierarchyid` for Common Operations</span></span>  
  
-   <span data-ttu-id="a4f18-152">Les requêtes de sous-arborescence sont beaucoup plus rapides avec `hierarchyid`</span><span class="sxs-lookup"><span data-stu-id="a4f18-152">Subtree queries are significantly faster with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="a4f18-153">Les requêtes de descendants directs sont légèrement plus lentes avec `hierarchyid`</span><span class="sxs-lookup"><span data-stu-id="a4f18-153">Direct descendant queries are slightly slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="a4f18-154">Le déplacement de nœuds non terminaux est beaucoup plus lent avec `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="a4f18-154">Moving non-leaf nodes is slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="a4f18-155">L'insertion de nœuds non terminaux et l'insertion ou le déplacement de nœuds terminaux présentent la même complexité avec `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="a4f18-155">Inserting non-leaf nodes and inserting or moving leaf nodes has the same complexity with `hierarchyid`.</span></span>  
  
 <span data-ttu-id="a4f18-156">Il se peut que la relation parent/enfant soit supérieure si les conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="a4f18-156">Parent/Child might be superior when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="a4f18-157">La taille de la clé est essentielle.</span><span class="sxs-lookup"><span data-stu-id="a4f18-157">The size of the key is critical.</span></span> <span data-ttu-id="a4f18-158">Pour le même nombre de nœuds, une valeur `hierarchyid` est égale ou supérieure à une valeur de famille d'entiers (`smallint`, `int`, `bigint`).</span><span class="sxs-lookup"><span data-stu-id="a4f18-158">For the same number of nodes, a `hierarchyid` value is equal to or larger than an integer-family (`smallint`, `int`, `bigint`) value.</span></span> <span data-ttu-id="a4f18-159">Cela ne constitue une raison d'utiliser la relation parent/enfant que dans de rares cas, car la localité d'E/S et la complexité de l'UC de `hierarchyid` sont meilleures que celles des expressions de table communes requises lorsque vous utilisez une structure parent/enfant.</span><span class="sxs-lookup"><span data-stu-id="a4f18-159">This is only a reason to use Parent/Child in rare cases, because `hierarchyid` has significantly better locality of I/O and CPU complexity than the common table expressions required when you are using a Parent/Child structure.</span></span>  
  
-   <span data-ttu-id="a4f18-160">Les requêtes portent rarement sur plusieurs sections de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="a4f18-160">Queries rarely query across sections of the hierarchy.</span></span> <span data-ttu-id="a4f18-161">En d'autres termes, les requêtes portent habituellement sur un seul point de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="a4f18-161">In other words, queries usually address only a single point in the hierarchy.</span></span> <span data-ttu-id="a4f18-162">Dans ces cas, la co-location n'est pas importante.</span><span class="sxs-lookup"><span data-stu-id="a4f18-162">In these cases co-location is not important.</span></span> <span data-ttu-id="a4f18-163">Par exemple, parent/enfant est supérieur lorsque la table d'organisation est utilisée uniquement pour le traitement des salaires d'employés individuels.</span><span class="sxs-lookup"><span data-stu-id="a4f18-163">For example, Parent/Child is superior when the organization table is only used to process payroll for individual employees.</span></span>  
  
-   <span data-ttu-id="a4f18-164">Les sous-arborescences qui ne sont pas au niveau du nœud terminal sont fréquemment déplacées et les performances sont importantes.</span><span class="sxs-lookup"><span data-stu-id="a4f18-164">Non-leaf subtrees move frequently and performance is very important.</span></span> <span data-ttu-id="a4f18-165">Dans une représentation parent/enfant, la modification de l'emplacement d'une ligne dans une hiérarchie affecte une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="a4f18-165">In a parent/child representation changing the location of a row in a hierarchy affects a single row.</span></span> <span data-ttu-id="a4f18-166">La modification de l’emplacement d’une ligne dans une `hierarchyid` utilisation affecte *n* lignes, où *n* est le nombre de nœuds dans la sous-arborescence qui est déplacée.</span><span class="sxs-lookup"><span data-stu-id="a4f18-166">Changing the location of a row in a `hierarchyid` usage affects *n* rows, where *n* is number of nodes in the sub-tree being moved.</span></span>  
  
     <span data-ttu-id="a4f18-167">Si les sous-arborescences qui ne sont pas au niveau du nœud terminal sont fréquemment déplacées et que les performances sont importantes, mais que la plupart des déplacements se font à un niveau bien défini de la hiérarchie, envisagez le fractionnement des niveaux supérieurs et inférieurs en deux hiérarchies.</span><span class="sxs-lookup"><span data-stu-id="a4f18-167">If the non-leaf subtrees move frequently and performance is important, but most of the moves are at a well-defined level of the hierarchy, consider splitting the higher and lower levels into two hierarchies.</span></span> <span data-ttu-id="a4f18-168">Tous les déplacements se font ainsi dans les niveaux du nœud terminal de la hiérarchie supérieure.</span><span class="sxs-lookup"><span data-stu-id="a4f18-168">This makes all moves into leaf-levels of the higher hierarchy.</span></span> <span data-ttu-id="a4f18-169">Prenons par exemple une hiérarchie de sites Web hébergés par un service.</span><span class="sxs-lookup"><span data-stu-id="a4f18-169">For instance, consider a hierarchy of Web sites hosted by a service.</span></span> <span data-ttu-id="a4f18-170">Les sites contiennent de nombreuses pages organisées de façon hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="a4f18-170">Sites contain many pages arranged in a hierarchical manner.</span></span> <span data-ttu-id="a4f18-171">Les sites hébergés peuvent être déplacés vers d'autres emplacements dans la hiérarchie de site, mais les pages subordonnées sont rarement réorganisées.</span><span class="sxs-lookup"><span data-stu-id="a4f18-171">Hosted sites might be moved to other locations in the site hierarchy, but the subordinate pages are rarely re-arranged.</span></span> <span data-ttu-id="a4f18-172">Cela peut être représenté de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="a4f18-172">This could be represented via:</span></span>  
  
    ```  
    CREATE TABLE HostedSites   
       (  
        SiteId hierarchyid, PageId hierarchyid  
       ) ;  
    GO  
    ```  
  
  
### <a name="xml"></a><span data-ttu-id="a4f18-173">XML</span><span class="sxs-lookup"><span data-stu-id="a4f18-173">XML</span></span>  
 <span data-ttu-id="a4f18-174">Un document XML est une arborescence. Par conséquent, une instance de type de données XML unique peut représenter la totalité d'une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="a4f18-174">An XML document is a tree, and therefore a single XML data type instance can represent a complete hierarchy.</span></span> <span data-ttu-id="a4f18-175">Dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , lorsqu’un index XML est créé, les `hierarchyid` valeurs sont utilisées en interne pour représenter la position dans la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="a4f18-175">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when an XML index is created, `hierarchyid` values are used internally to represent the position in the hierarchy.</span></span>  
  
 <span data-ttu-id="a4f18-176">Il peut être préférable d'utiliser le type de données XML lorsque les conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="a4f18-176">Using XML data type can be superior when all the following are true:</span></span>  
  
-   <span data-ttu-id="a4f18-177">La hiérarchie est toujours stockée et extraite dans sa totalité.</span><span class="sxs-lookup"><span data-stu-id="a4f18-177">The complete hierarchy is always stored and retrieved.</span></span>  
  
-   <span data-ttu-id="a4f18-178">Les données sont consommées au format XML par l'application.</span><span class="sxs-lookup"><span data-stu-id="a4f18-178">The data is consumed in XML format by the application.</span></span>  
  
-   <span data-ttu-id="a4f18-179">Les recherches de prédicat sont extrêmement limitées et non critiques pour les performances.</span><span class="sxs-lookup"><span data-stu-id="a4f18-179">Predicate searches are extremely limited and not performance critical.</span></span>  
  
 <span data-ttu-id="a4f18-180">Par exemple, si une application effectue le suivi de plusieurs organisations, stocke et extrait toujours la totalité de la hiérarchie d'organisation et que ses requêtes ne portent pas sur une organisation unique, une table se présentant au format suivant peut être appropriée :</span><span class="sxs-lookup"><span data-stu-id="a4f18-180">For example, if an application tracks multiple organizations, always stores and retrieves the complete organizational hierarchy, and does not query into a single organization, a table of the following form might make sense:</span></span>  
  
```  
CREATE TABLE XMLOrg   
    (  
    Orgid int,  
    Orgdata xml  
    ) ;  
GO  
```  
  
  
##  <a name="indexing-strategies-for-hierarchical-data"></a><a name="indexing"></a> <span data-ttu-id="a4f18-181">Stratégies d'indexation des données hiérarchiques</span><span class="sxs-lookup"><span data-stu-id="a4f18-181">Indexing Strategies for Hierarchical Data</span></span>  
 <span data-ttu-id="a4f18-182">Il existe deux stratégies d'indexation des données hiérarchiques :</span><span class="sxs-lookup"><span data-stu-id="a4f18-182">There are two strategies for indexing hierarchical data:</span></span>  
  
-   <span data-ttu-id="a4f18-183">**À profondeur prioritaire**</span><span class="sxs-lookup"><span data-stu-id="a4f18-183">**Depth-first**</span></span>  
  
     <span data-ttu-id="a4f18-184">Un index à profondeur prioritaire stocke les lignes dans une sous-arborescence à proximité les unes des autres.</span><span class="sxs-lookup"><span data-stu-id="a4f18-184">A depth-first index stores the rows in a subtree near each other.</span></span> <span data-ttu-id="a4f18-185">Par exemple, tous les employés ayant un supérieur sont stockés à proximité de l'enregistrement de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="a4f18-185">For example, all employees that report through a manager are stored near their managers' record.</span></span>  
  
     <span data-ttu-id="a4f18-186">Dans un index à profondeur prioritaire, tous les nœuds dans la sous-arborescence d'un nœud sont colocalisés.</span><span class="sxs-lookup"><span data-stu-id="a4f18-186">In a depth-first index, all nodes in the subtree of a node are co-located.</span></span> <span data-ttu-id="a4f18-187">Les index à profondeur prioritaire sont par conséquent efficaces pour répondre aux requêtes sur les sous-arborescences, comme « Rechercher tous les fichiers dans ce dossier et ses sous-dossiers ».</span><span class="sxs-lookup"><span data-stu-id="a4f18-187">Depth-first indexes are therefore efficient for answering queries about subtrees, such as "Find all files in this folder and its subfolders".</span></span>  
  
-   <span data-ttu-id="a4f18-188">**À largeur prioritaire**</span><span class="sxs-lookup"><span data-stu-id="a4f18-188">**Breadth-first**</span></span>  
  
     <span data-ttu-id="a4f18-189">Un index à largeur prioritaire stocke les lignes en regroupant les niveaux de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="a4f18-189">A breadth-first stores the rows each level of the hierarchy together.</span></span> <span data-ttu-id="a4f18-190">Par exemple, les enregistrements des employés ayant le même supérieur direct sont stockés à proximité les uns des autres.</span><span class="sxs-lookup"><span data-stu-id="a4f18-190">For example, the records of employees who directly report to the same manager are stored near each other.</span></span>  
  
     <span data-ttu-id="a4f18-191">Dans un index à largeur prioritaire, tous les enfants directs d'un nœud sont colocalisés.</span><span class="sxs-lookup"><span data-stu-id="a4f18-191">In a breadth-first index all direct children of a node are co-located.</span></span> <span data-ttu-id="a4f18-192">Les index à largeur prioritaire sont par conséquent efficaces pour répondre aux requêtes sur les enfants immédiats, telle que « Rechercher tous les employés dont ce responsable est le supérieur direct ».</span><span class="sxs-lookup"><span data-stu-id="a4f18-192">Breadth-first indexes are therefore efficient for answering queries about immediate children, such as "Find all employees who report directly to this manager".</span></span>  
  
 <span data-ttu-id="a4f18-193">Le choix entre profondeur prioritaire, largeur prioritaire ou les deux, et la sélection de l'un d'eux comme clé de clustering (si nécessaire) dépend de l'importance relative des types de requêtes ci-dessus et de l'importance relative de SELECT par rapport aux opérations DML.</span><span class="sxs-lookup"><span data-stu-id="a4f18-193">Whether to have depth-first, breadth-first, or both, and which to make the clustering key (if any), depends on the relative importance of the above types of queries, and the relative importance of SELECT vs. DML operations.</span></span> <span data-ttu-id="a4f18-194">Pour un exemple détaillé de stratégies d'indexation, consultez [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="a4f18-194">For a detailed example of indexing strategies, see [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
### <a name="creating-indexes"></a><span data-ttu-id="a4f18-195">Création des index</span><span class="sxs-lookup"><span data-stu-id="a4f18-195">Creating Indexes</span></span>  
 <span data-ttu-id="a4f18-196">Vous pouvez utiliser la méthode GetLevel() pour créer un classement à largeur prioritaire.</span><span class="sxs-lookup"><span data-stu-id="a4f18-196">The GetLevel() method can be used to create a breadth first ordering.</span></span> <span data-ttu-id="a4f18-197">Dans l'exemple suivant, des index à largeur prioritaire et des index à profondeur prioritaire sont créés :</span><span class="sxs-lookup"><span data-stu-id="a4f18-197">In the following example, both breadth-first and depth-first indexes are created:</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;   
GO  
  
CREATE TABLE Organization  
   (  
    BusinessEntityID hierarchyid,  
    OrgLevel as BusinessEntityID.GetLevel(),   
    EmployeeName nvarchar(50) NOT NULL  
   ) ;  
GO  
  
CREATE CLUSTERED INDEX Org_Breadth_First   
ON Organization(OrgLevel,BusinessEntityID) ;  
GO  
  
CREATE UNIQUE INDEX Org_Depth_First   
ON Organization(BusinessEntityID) ;  
GO  
```  
  
  
## <a name="examples"></a><span data-ttu-id="a4f18-198">Exemples</span><span class="sxs-lookup"><span data-stu-id="a4f18-198">Examples</span></span>  
  
### <a name="simple-example"></a><span data-ttu-id="a4f18-199">Exemple simple</span><span class="sxs-lookup"><span data-stu-id="a4f18-199">Simple Example</span></span>  
 <span data-ttu-id="a4f18-200">L'exemple suivant est intentionnellement très simplifié pour vous aider à démarrer.</span><span class="sxs-lookup"><span data-stu-id="a4f18-200">The following example is intentionally simplistic to help you get started.</span></span> <span data-ttu-id="a4f18-201">Créez une table pour contenir des données de type geography.</span><span class="sxs-lookup"><span data-stu-id="a4f18-201">First create a table to hold some geography data.</span></span>  
  
```  
CREATE TABLE SimpleDemo  
(Level hierarchyid NOT NULL,  
Location nvarchar(30) NOT NULL,  
LocationType nvarchar(9) NULL);  
```  
  
 <span data-ttu-id="a4f18-202">Insérez maintenant les données de certains continents, pays, états et villes.</span><span class="sxs-lookup"><span data-stu-id="a4f18-202">Now insert data for some continents, countries, states, and cities.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES   
('/1/', 'Europe', 'Continent'),  
('/2/', 'South America', 'Continent'),  
('/1/1/', 'France', 'Country'),  
('/1/1/1/', 'Paris', 'City'),  
('/1/2/1/', 'Madrid', 'City'),  
('/1/2/', 'Spain', 'Country'),  
('/3/', 'Antarctica', 'Continent'),  
('/2/1/', 'Brazil', 'Country'),  
('/2/1/1/', 'Brasilia', 'City'),  
('/2/1/2/', 'Bahia', 'State'),  
('/2/1/2/1/', 'Salvador', 'City'),  
('/3/1/', 'McMurdo Station', 'City');  
```  
  
 <span data-ttu-id="a4f18-203">Sélectionnez les données, en ajoutant une colonne qui convertit les données de niveau en une valeur texte facile à comprendre.</span><span class="sxs-lookup"><span data-stu-id="a4f18-203">Select the data, adding a column that converts the Level data into a text value that is easy to understand.</span></span> <span data-ttu-id="a4f18-204">Cette requête trie également les résultats par le type de données `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="a4f18-204">This query also orders the result by the `hierarchyid` data type.</span></span>  
  
```  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], *   
FROM SimpleDemo ORDER BY Level;  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
Converted Level  Level     Location         LocationType  
/1/              0x58      Europe           Continent  
/1/1/            0x5AC0    France           Country  
/1/1/1/          0x5AD6    Paris            City  
/1/2/            0x5B40    Spain            Country  
/1/2/1/          0x5B56    Madrid           City  
/2/              0x68      South America    Continent  
/2/1/            0x6AC0    Brazil           Country  
/2/1/1/          0x6AD6    Brasilia         City  
/2/1/2/          0x6ADA    Bahia            State  
/2/1/2/1/        0x6ADAB0  Salvador         City  
/3/              0x78      Antarctica       Continent  
/3/1/            0x7AC0    McMurdo Station  City  
```  
  
 <span data-ttu-id="a4f18-205">Notez que la hiérarchie a une structure valide, même si elle n'est pas cohérente en interne.</span><span class="sxs-lookup"><span data-stu-id="a4f18-205">Notice that the hierarchy is has a valid structure, even though it is not internally consistent.</span></span> <span data-ttu-id="a4f18-206">Bahia est le seul État.</span><span class="sxs-lookup"><span data-stu-id="a4f18-206">Bahia is the only state.</span></span> <span data-ttu-id="a4f18-207">Il s'affiche dans la hiérarchie en tant qu'homologue de la ville Brasilia.</span><span class="sxs-lookup"><span data-stu-id="a4f18-207">It appears in the hierarchy as a peer of the city Brasilia.</span></span> <span data-ttu-id="a4f18-208">De même, McMurdo Station n'a pas de pays parent.</span><span class="sxs-lookup"><span data-stu-id="a4f18-208">Similarly, McMurdo Station does not have a parent country.</span></span> <span data-ttu-id="a4f18-209">Les utilisateurs doivent décider si ce type de hiérarchie convient à leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="a4f18-209">Users must decide if this type of hierarchy is appropriate for their use.</span></span>  
  
 <span data-ttu-id="a4f18-210">Ajoutez une autre ligne et sélectionnez les résultats.</span><span class="sxs-lookup"><span data-stu-id="a4f18-210">Add another row and select the results.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/1/3/1/', 'Kyoto', 'City'), ('/1/3/1/', 'London', 'City');  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], * FROM SimpleDemo ORDER BY Level;  
```  
  
 <span data-ttu-id="a4f18-211">Cela indique d'autres problèmes possibles.</span><span class="sxs-lookup"><span data-stu-id="a4f18-211">This demonstrates more possible problems.</span></span> <span data-ttu-id="a4f18-212">Kyoto peut être inséré en tant que niveau `/1/3/1/` bien qu'il n'existe pas de niveau parent `/1/3/`.</span><span class="sxs-lookup"><span data-stu-id="a4f18-212">Kyoto can be inserted as level `/1/3/1/` even though there is no parent level `/1/3/`.</span></span> <span data-ttu-id="a4f18-213">Et Londres et Kyoto ont la même valeur de `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="a4f18-213">And both London and Kyoto have the same value for the `hierarchyid`.</span></span> <span data-ttu-id="a4f18-214">Là encore, les utilisateurs doivent décider si ce type de hiérarchie convient à leur utilisation, et bloquer les valeurs qui ne sont pas valides pour leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="a4f18-214">Again, users must decide if this type of hierarchy is appropriate for their use, and block values that are invalid for their usage.</span></span>  
  
 <span data-ttu-id="a4f18-215">En outre, la table n'utilise pas le haut de la hiérarchie `'/'`.</span><span class="sxs-lookup"><span data-stu-id="a4f18-215">Also, this table did not use the top of the hierarchy `'/'`.</span></span> <span data-ttu-id="a4f18-216">Il a été omis, car il n'y a aucun parent commun à tous les continents.</span><span class="sxs-lookup"><span data-stu-id="a4f18-216">It was omitted because there is no common parent of all the continents.</span></span> <span data-ttu-id="a4f18-217">Pour en ajouter un, ajoutez la planète entière.</span><span class="sxs-lookup"><span data-stu-id="a4f18-217">You can add one by adding the whole planet.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/', 'Earth', 'Planet');  
```  
  
##  <a name="related-tasks"></a><a name="tasks"></a> <span data-ttu-id="a4f18-218">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a4f18-218">Related Tasks</span></span>  
  
###  <a name="migrating-from-parentchild-to-hierarchyid"></a><a name="migrating"></a> <span data-ttu-id="a4f18-219">Migration de parent/enfant vers hierarchyid</span><span class="sxs-lookup"><span data-stu-id="a4f18-219">Migrating from Parent/Child to hierarchyid</span></span>  
 <span data-ttu-id="a4f18-220">La plupart des arborescences sont représentées à l'aide de parent/enfant.</span><span class="sxs-lookup"><span data-stu-id="a4f18-220">Most trees are represented using Parent/Child.</span></span> <span data-ttu-id="a4f18-221">La méthode la plus simple pour effectuer une migration d'une structure parent/enfant vers une table à l'aide de `hierarchyid` consiste à utiliser une colonne ou une table temporaire pour conserver une trace du nombre de nœuds à chaque niveau de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="a4f18-221">The easiest way to migrate from a Parent/Child structure to a table using `hierarchyid` is to use a temporary column or a temporary table to keep track of the number of nodes at each level of the hierarchy.</span></span> <span data-ttu-id="a4f18-222">Pour voir un exemple de migration de table parent/enfant, consultez la leçon 1 de [Didacticiel : utilisation du type de données hierarchyid](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="a4f18-222">For an example of migrating a Parent/Child table, see lesson 1 of [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
###  <a name="managing-a-tree-using-hierarchyid"></a><a name="BKMK_ManagingTrees"></a> <span data-ttu-id="a4f18-223">Gestion d'une arborescence à l'aide de hierarchyid</span><span class="sxs-lookup"><span data-stu-id="a4f18-223">Managing a Tree Using hierarchyid</span></span>  
 <span data-ttu-id="a4f18-224">Bien qu'une colonne `hierarchyid` ne représente pas nécessairement une arborescence, une application peut facilement faire en sorte que ce soit le cas.</span><span class="sxs-lookup"><span data-stu-id="a4f18-224">Although a `hierarchyid` column does not necessarily represent a tree, an application can easily ensure that it does.</span></span>  
  
-   <span data-ttu-id="a4f18-225">Lorsque vous générez de nouvelles valeurs, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4f18-225">When generating new values, do one of the following:</span></span>  
  
    -   <span data-ttu-id="a4f18-226">Effectuez le suivi du dernier numéro enfant dans la ligne parent.</span><span class="sxs-lookup"><span data-stu-id="a4f18-226">Keep track of the last child number in the parent row.</span></span>  
  
    -   <span data-ttu-id="a4f18-227">Calculez le dernier enfant.</span><span class="sxs-lookup"><span data-stu-id="a4f18-227">Compute the last child.</span></span> <span data-ttu-id="a4f18-228">Cette opération nécessite un index à largeur prioritaire pour être efficace.</span><span class="sxs-lookup"><span data-stu-id="a4f18-228">Doing this efficiently requires a breadth-first index.</span></span>  
  
-   <span data-ttu-id="a4f18-229">Appliquez l'unicité en créant un index unique sur la colonne, éventuellement en tant que partie d'une clé de clustering.</span><span class="sxs-lookup"><span data-stu-id="a4f18-229">Enforce uniqueness by creating a unique index on the column, perhaps as part of a clustering key.</span></span> <span data-ttu-id="a4f18-230">Pour vous assurer que des valeurs uniques sont insérées, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4f18-230">To ensure that unique values are inserted, do one of the following:</span></span>  
  
    -   <span data-ttu-id="a4f18-231">détection des échecs de violation de clés uniques et nouvelle tentative.</span><span class="sxs-lookup"><span data-stu-id="a4f18-231">Detect unique key violation failures and retry.</span></span>  
  
    -   <span data-ttu-id="a4f18-232">Détermination de l'unicité de chaque nouveau nœud enfant et insertion dans une transaction sérialisable.</span><span class="sxs-lookup"><span data-stu-id="a4f18-232">Determine the uniqueness of each new child node, and insert it as part of a serializable transaction.</span></span>  
  
  
#### <a name="example-using-error-detection"></a><span data-ttu-id="a4f18-233">Exemple utilisant la détection d'erreurs</span><span class="sxs-lookup"><span data-stu-id="a4f18-233">Example Using Error Detection</span></span>  
 <span data-ttu-id="a4f18-234">Dans l’exemple suivant, le code calcule la nouvelle valeur enfant **EmployeeId** , puis détecte toute violation de clé et retourne au marqueur **INS_EMP** pour recalculer la valeur **EmployeeId** de la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="a4f18-234">In the following example, the sample code computes the new child **EmployeeId** value, and then detects any key violation and returns to **INS_EMP** marker to recompute the **EmployeeId** value for the new row:</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
CREATE TABLE Org_T1  
   (  
    EmployeeId hierarchyid PRIMARY KEY,  
    OrgLevel AS EmployeeId.GetLevel(),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
  
CREATE INDEX Org_BreadthFirst ON Org_T1(OrgLevel, EmployeeId)  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50) )   
AS  
BEGIN  
    DECLARE @last_child hierarchyid  
INS_EMP:   
    SELECT @last_child = MAX(EmployeeId) FROM Org_T1   
    WHERE EmployeeId.GetAncestor(1) = @mgrid  
INSERT Org_T1 (EmployeeId, EmployeeName)  
SELECT @mgrid.GetDescendant(@last_child, NULL), @EmpName   
-- On error, return to INS_EMP to recompute @last_child  
IF @@error <> 0 GOTO INS_EMP   
END ;  
GO  
```  
  
  
#### <a name="example-using-a-serializable-transaction"></a><span data-ttu-id="a4f18-235">Exemple utilisant une transaction sérialisable</span><span class="sxs-lookup"><span data-stu-id="a4f18-235">Example Using a Serializable Transaction</span></span>  
 <span data-ttu-id="a4f18-236">Les limites du type de données **Org_BreadthFirst** garantit que la détermination de **@last_child** utilise une recherche de plage.</span><span class="sxs-lookup"><span data-stu-id="a4f18-236">The **Org_BreadthFirst** index ensures that determining **@last_child** uses a range seek.</span></span> <span data-ttu-id="a4f18-237">En plus des autres cas d’erreur qu’une application peut souhaiter vérifier, une violation de clé dupliquée après l’insertion indique une tentative d’ajout de plusieurs employés ayant le même ID et **@last_child** doit donc être recalculée.</span><span class="sxs-lookup"><span data-stu-id="a4f18-237">In addition to other error cases an application might want to check, a duplicate key violation after the insert indicates an attempt to add multiple employees with the same id, and therefore **@last_child** must be recomputed.</span></span> <span data-ttu-id="a4f18-238">Le code suivant utilise une transaction sérialisable et un index à largeur prioritaire pour calculer la nouvelle valeur de nœud :</span><span class="sxs-lookup"><span data-stu-id="a4f18-238">The following code uses a serializable transaction and a breadth-first index to compute the new node value:</span></span>  
  
```  
CREATE TABLE Org_T2  
    (  
    EmployeeId hierarchyid PRIMARY KEY,  
    LastChild hierarchyid,   
    EmployeeName nvarchar(50)   
    ) ;  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50))   
AS  
BEGIN  
DECLARE @last_child hierarchyid  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION   
  
UPDATE Org_T2   
SET @last_child = LastChild = EmployeeId.GetDescendant(LastChild,NULL)  
WHERE EmployeeId = @mgrid  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(@last_child, @EmpName)  
COMMIT  
END ;  
```  
  
 <span data-ttu-id="a4f18-239">Le code suivant remplit la table avec trois lignes et retourne les résultats :</span><span class="sxs-lookup"><span data-stu-id="a4f18-239">The following code populates the table with three rows and returns the results:</span></span>  
  
```  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(hierarchyid::GetRoot(), 'David') ;  
GO  
AddEmp 0x , 'Sariya'  
GO  
AddEmp 0x58 , 'Mary'  
GO  
SELECT * FROM Org_T2  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
EmployeeId LastChild EmployeeName  
---------- --------- ------------  
0x        0x58       David  
0x58      0x5AC0     Sariya  
0x5AC0    NULL       Mary  
```  
  
  
###  <a name="enforcing-a-tree"></a><a name="BKMK_EnforcingTrees"></a> <span data-ttu-id="a4f18-240">Application d'une arborescence</span><span class="sxs-lookup"><span data-stu-id="a4f18-240">Enforcing a tree</span></span>  
 <span data-ttu-id="a4f18-241">Les exemples ci-dessus illustrent la manière dont une application peut garantir la conservation d'une arborescence.</span><span class="sxs-lookup"><span data-stu-id="a4f18-241">The above examples illustrate how an application can ensure that a tree is maintained.</span></span> <span data-ttu-id="a4f18-242">Pour appliquer une arborescence à l'aide de contraintes, une colonne calculée qui définit le parent de chaque nœud peut être créée avec une contrainte de clé étrangère vers l'ID de clé primaire.</span><span class="sxs-lookup"><span data-stu-id="a4f18-242">To enforce a tree by using constraints, a computed column that defines the parent of each node can be created with a foreign key constraint back to the primary key id.</span></span>  
  
```  
CREATE TABLE Org_T3  
(  
   EmployeeId hierarchyid PRIMARY KEY,  
   ParentId AS EmployeeId.GetAncestor(1) PERSISTED    
      REFERENCES Org_T3(EmployeeId),  
   LastChild hierarchyid,   
   EmployeeName nvarchar(50)  
)  
GO  
```  
  
 <span data-ttu-id="a4f18-243">Cette méthode d'application d'une relation est préférable lorsqu'un code non fiable pour maintenir l'arborescence hiérarchique dispose d'un accès DML direct à la table.</span><span class="sxs-lookup"><span data-stu-id="a4f18-243">This method of enforcing a relationship is preferred when code that is not trusted to maintain the hierarchical tree has direct DML access to the table.</span></span> <span data-ttu-id="a4f18-244">Toutefois, cette méthode est susceptible de réduire les performances car la contrainte doit être vérifiée à chaque opération DML.</span><span class="sxs-lookup"><span data-stu-id="a4f18-244">However this method might reduce performance because the constraint must be checked on every DML operation.</span></span>  
  
  
###  <a name="finding-ancestors-by-using-the-clr"></a><a name="findclr"></a> <span data-ttu-id="a4f18-245">Recherche d'ancêtres à l'aide du CLR</span><span class="sxs-lookup"><span data-stu-id="a4f18-245">Finding Ancestors by Using the CLR</span></span>  
 <span data-ttu-id="a4f18-246">La recherche de l'ancêtre commun le plus bas est une opération courante impliquant deux nœuds dans une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="a4f18-246">A common operation involving two nodes in a hierarchy is to find the lowest common ancestor.</span></span> <span data-ttu-id="a4f18-247">Cela peut être écrit dans [!INCLUDE[tsql](../includes/tsql-md.md)] ou CLR, car le `hierarchyid` type est disponible dans les deux.</span><span class="sxs-lookup"><span data-stu-id="a4f18-247">This can be written in either [!INCLUDE[tsql](../includes/tsql-md.md)] or CLR, because the `hierarchyid` type is available in both.</span></span> <span data-ttu-id="a4f18-248">L'utilisation de CLR est recommandée car les performances seront plus rapides.</span><span class="sxs-lookup"><span data-stu-id="a4f18-248">CLR is recommended because performance will be faster.</span></span>  
  
 <span data-ttu-id="a4f18-249">Utilisez le code CLR suivant pour répertorier les ancêtres et trouver l'ancêtre commun le plus bas :</span><span class="sxs-lookup"><span data-stu-id="a4f18-249">Use the following CLR code to list ancestors and to find the lowest common ancestor:</span></span>  
  
```  
using System;  
using System.Collections;  
using System.Text;  
using Microsoft.SqlServer.Server;  
using Microsoft.SqlServer.Types;  
  
public partial class HierarchyId_Operations  
{  
    [SqlFunction(FillRowMethodName = "FillRow_ListAncestors")]  
    public static IEnumerable ListAncestors(SqlHierarchyId h)  
    {  
        while (!h.IsNull)  
        {  
            yield return (h);  
            h = h.GetAncestor(1);  
        }  
    }  
    public static void FillRow_ListAncestors(Object obj, out SqlHierarchyId ancestor)  
    {  
        ancestor = (SqlHierarchyId)obj;  
    }  
  
    public static HierarchyId CommonAncestor(SqlHierarchyId h1, HierarchyId h2)  
    {  
        while (!h1.IsDescendant(h2))  
            h1 = h1.GetAncestor(1);  
  
        return h1;  
    }  
}  
```  
  
 <span data-ttu-id="a4f18-250">Pour utiliser les méthodes **ListAncestor** et **CommonAncestor** dans les exemples [!INCLUDE[tsql](../includes/tsql-md.md)] suivants, générez la DLL et créez l’assembly **HierarchyId_Operations** dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en exécutant du code semblable à celui-ci :</span><span class="sxs-lookup"><span data-stu-id="a4f18-250">To use the **ListAncestor** and **CommonAncestor** methods in the following [!INCLUDE[tsql](../includes/tsql-md.md)] examples, build the DLL and create the **HierarchyId_Operations** assembly in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by executing code similar to the following:</span></span>  
  
```  
CREATE ASSEMBLY HierarchyId_Operations   
FROM '<path to DLL>\ListAncestors.dll'  
GO  
```  
  
  
###  <a name="listing-ancestors"></a><a name="ancestors"></a> <span data-ttu-id="a4f18-251">Répertorier les ancêtres</span><span class="sxs-lookup"><span data-stu-id="a4f18-251">Listing Ancestors</span></span>  
 <span data-ttu-id="a4f18-252">La création d'une liste d'ancêtres d'un nœud est une opération courante, par exemple pour afficher la position au sein d'une organisation.</span><span class="sxs-lookup"><span data-stu-id="a4f18-252">Creating a list of ancestors of a node is a common operation, for instance to show position in an organization.</span></span> <span data-ttu-id="a4f18-253">Pour cela, vous pouvez par exemple utiliser une fonction table à l’aide de la classe **HierarchyId_Operations** définie ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="a4f18-253">One way of doing this is by using a table-valued-function using the **HierarchyId_Operations** class defined above:</span></span>  
  
 <span data-ttu-id="a4f18-254">Utilisation de [!INCLUDE[tsql](../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a4f18-254">Using [!INCLUDE[tsql](../includes/tsql-md.md)]:</span></span>  
  
```  
CREATE FUNCTION ListAncestors (@node hierarchyid)  
RETURNS TABLE (node hierarchyid)  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.ListAncestors  
GO  
```  
  
 <span data-ttu-id="a4f18-255">Exemple d'utilisation :</span><span class="sxs-lookup"><span data-stu-id="a4f18-255">Example of usage:</span></span>  
  
```  
DECLARE @h hierarchyid  
SELECT @h = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- /1/1/5/2/  
  
SELECT LoginID, OrgNode.ToString() AS LogicalNode  
FROM HumanResources.EmployeeDemo AS ED  
JOIN ListAncestors(@h) AS A   
   ON ED.OrgNode = A.Node  
GO  
```  
  
  
###  <a name="finding-the-lowest-common-ancestor"></a><a name="lowestcommon"></a> <span data-ttu-id="a4f18-256">Recherche de l'ancêtre commun le plus bas</span><span class="sxs-lookup"><span data-stu-id="a4f18-256">Finding the Lowest Common Ancestor</span></span>  
 <span data-ttu-id="a4f18-257">À l’aide de la classe **HierarchyId_Operations** définie ci-dessus, créez la fonction [!INCLUDE[tsql](../includes/tsql-md.md)] suivante pour rechercher l’ancêtre commun le plus bas impliquant deux nœuds dans une hiérarchie :</span><span class="sxs-lookup"><span data-stu-id="a4f18-257">Using the **HierarchyId_Operations** class defined above, create the following [!INCLUDE[tsql](../includes/tsql-md.md)] function to find the lowest common ancestor involving two nodes in a hierarchy:</span></span>  
  
```  
CREATE FUNCTION CommonAncestor (@node1 hierarchyid, @node2 hierarchyid)  
RETURNS hierarchyid  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.CommonAncestor  
GO  
```  
  
 <span data-ttu-id="a4f18-258">Exemple d'utilisation :</span><span class="sxs-lookup"><span data-stu-id="a4f18-258">Example of usage:</span></span>  
  
```  
DECLARE @h1 hierarchyid, @h2 hierarchyid  
  
SELECT @h1 = OrgNode   
FROM  HumanResources.EmployeeDemo   
WHERE LoginID = 'adventure-works\jossef0' -- Node is /1/1/3/  
  
SELECT @h2 = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- Node is /1/1/5/2/  
  
SELECT OrgNode.ToString() AS LogicalNode, LoginID   
FROM HumanResources.EmployeeDemo    
WHERE OrgNode = dbo.CommonAncestor(@h1, @h2) ;  
```  
  
 <span data-ttu-id="a4f18-259">Le nœud résultant est /1/1/</span><span class="sxs-lookup"><span data-stu-id="a4f18-259">The resultant node is /1/1/</span></span>  
  
  
###  <a name="moving-subtrees"></a><a name="BKMK_MovingSubtrees"></a> <span data-ttu-id="a4f18-260">Déplacement de sous-arborescences</span><span class="sxs-lookup"><span data-stu-id="a4f18-260">Moving Subtrees</span></span>  
 <span data-ttu-id="a4f18-261">Une autre opération courante concerne le déplacement de sous-arborescences.</span><span class="sxs-lookup"><span data-stu-id="a4f18-261">Another common operation is moving subtrees.</span></span> <span data-ttu-id="a4f18-262">La procédure ci-dessous prend la sous-arborescence de **@oldMgr** et la fait (y compris **@oldMgr** ) une sous-arborescence de **@newMgr** .</span><span class="sxs-lookup"><span data-stu-id="a4f18-262">The procedure below takes the subtree of **@oldMgr** and makes it (including **@oldMgr**) a subtree of **@newMgr**.</span></span>  
  
```  
CREATE PROCEDURE MoveOrg(@oldMgr nvarchar(256), @newMgr nvarchar(256) )  
AS  
BEGIN  
DECLARE @nold hierarchyid, @nnew hierarchyid  
SELECT @nold = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @oldMgr ;  
  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION  
SELECT @nnew = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @newMgr ;  
  
SELECT @nnew = @nnew.GetDescendant(max(OrgNode), NULL)   
FROM HumanResources.EmployeeDemo WHERE OrgNode.GetAncestor(1)=@nnew ;  
  
UPDATE HumanResources.EmployeeDemo    
SET OrgNode = OrgNode.GetReparentedValue(@nold, @nnew)  
WHERE OrgNode.IsDescendantOf(@nold) = 1 ;  
  
COMMIT TRANSACTION  
END ;  
GO  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="a4f18-263">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4f18-263">See Also</span></span>  
 <span data-ttu-id="a4f18-264">[Référence de méthodes de type de données hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="a4f18-264">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="a4f18-265">[Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="a4f18-265">[Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span></span>  
 [<span data-ttu-id="a4f18-266">hierarchyid &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a4f18-266">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
