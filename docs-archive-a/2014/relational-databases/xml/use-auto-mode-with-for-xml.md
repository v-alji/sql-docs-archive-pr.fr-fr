---
title: Utiliser le mode AUTO avec FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, AUTO mode
- ELEMENTS option
- FOR XML AUTO mode
- AUTO FOR XML mode
ms.assetid: 7140d656-1d42-4f01-a533-5251429f4450
author: rothja
ms.author: jroth
ms.openlocfilehash: 232cc046667c6d31cb9657a7abdc862204507d23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610518"
---
# <a name="use-auto-mode-with-for-xml"></a><span data-ttu-id="d8910-102">Utiliser le mode AUTO avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="d8910-102">Use AUTO Mode with FOR XML</span></span>
  <span data-ttu-id="d8910-103">Comme décrit dans [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md), le mode AUTO retourne des résultats de requête en tant qu’éléments XML imbriqués.</span><span class="sxs-lookup"><span data-stu-id="d8910-103">As described in [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md), AUTO mode returns query results as nested XML elements.</span></span> <span data-ttu-id="d8910-104">Cela ne permet pas de contrôler de façon précise la forme du document XML généré à partir du résultat d'une requête.</span><span class="sxs-lookup"><span data-stu-id="d8910-104">This does not provide much control over the shape of the XML generated from a query result.</span></span> <span data-ttu-id="d8910-105">Les requêtes au mode AUTO sont utiles pour générer des hiérarchies simples.</span><span class="sxs-lookup"><span data-stu-id="d8910-105">The AUTO mode queries are useful if you want to generate simple hierarchies.</span></span> <span data-ttu-id="d8910-106">Toutefois, [Utiliser le mode EXPLICIT avec FOR XML](use-explicit-mode-with-for-xml.md) et [Utiliser le mode PATH avec FOR XML](use-path-mode-with-for-xml.md) fournissent davantage de contrôle et de souplesse pour déterminer la forme du XML à partir d’un résultat de requête.</span><span class="sxs-lookup"><span data-stu-id="d8910-106">However, [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) and [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) provide more control and flexibility in deciding the shape of the XML from a query result.</span></span>  
  
 <span data-ttu-id="d8910-107">Chaque table de la clause FROM, dont au moins une colonne est répertoriée dans la clause SELECT, est représentée sous la forme d'un élément XML.</span><span class="sxs-lookup"><span data-stu-id="d8910-107">Each table in the FROM clause, from which at least one column is listed in the SELECT clause, is represented as an XML element.</span></span> <span data-ttu-id="d8910-108">Les colonnes répertoriées dans la clause SELECT sont mappées avec des attributs ou des sous-éléments si l'option ELEMENTS facultative est spécifiée dans la clause FOR XML.</span><span class="sxs-lookup"><span data-stu-id="d8910-108">The columns listed in the SELECT clause are mapped to attributes or subelements, if the optional ELEMENTS option is specified in the FOR XML clause.</span></span>  
  
 <span data-ttu-id="d8910-109">La hiérarchie XML, imbrication des éléments, obtenue dans les données XML dépend de l'ordre des tables définies par les colonnes indiquées dans la clause SELECT.</span><span class="sxs-lookup"><span data-stu-id="d8910-109">The XML hierarchy, nesting of the elements, in the resulting XML is based on the order of tables identified by the columns specified in the SELECT clause.</span></span> <span data-ttu-id="d8910-110">Par conséquent, l'ordre dans lequel les noms de colonnes sont spécifiés dans la clause SELECT est significatif.</span><span class="sxs-lookup"><span data-stu-id="d8910-110">Therefore, the order in which column names are specified in the SELECT clause is significant.</span></span> <span data-ttu-id="d8910-111">La première table identifiée, celle qui se trouve le plus à gauche, constitue l'élément du plus haut niveau dans le document XML résultant.</span><span class="sxs-lookup"><span data-stu-id="d8910-111">The first, leftmost table that is identified forms the top element in the resulting XML document.</span></span> <span data-ttu-id="d8910-112">La deuxième table la plus à gauche, identifiée par des colonnes dans l'instruction SELECT, constitue un sous-élément de l'élément de plus haut niveau et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="d8910-112">The second leftmost table, identified by columns in the SELECT statement, forms a subelement within the top element, and so on.</span></span>  
  
 <span data-ttu-id="d8910-113">Si un nom de colonne répertorié dans la clause SELECT provient d'une table déjà identifiée par une colonne précédemment spécifiée dans cette clause, la colonne est ajoutée en tant qu'attribut de l'élément déjà créé et aucun nouveau niveau de hiérarchie n'est ouvert.</span><span class="sxs-lookup"><span data-stu-id="d8910-113">If a column name listed in the SELECT clause is from a table that is already identified by a previously specified column in the SELECT clause, the column is added as an attribute of the element already created, instead of opening a new level of hierarchy.</span></span> <span data-ttu-id="d8910-114">Si l'option ELEMENTS est spécifiée, la colonne est ajoutée en tant qu'attribut.</span><span class="sxs-lookup"><span data-stu-id="d8910-114">If the ELEMENTS option is specified, the column is added as an attribute.</span></span>  
  
 <span data-ttu-id="d8910-115">Exécutez par exemple cette requête :</span><span class="sxs-lookup"><span data-stu-id="d8910-115">For example, execute this query:</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO  
```  
  
 <span data-ttu-id="d8910-116">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="d8910-116">This is the partial result:</span></span>  
  
```  
<Cust CustomerID="1" CustomerType="S">  
  <OrderHeader CustomerID="1" SalesOrderID="43860" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="44501" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="45283" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="46042" Status="5" />  
</Cust>  
...  
```  
  
 <span data-ttu-id="d8910-117">Notez les points suivants relatifs à la clause SELECT :</span><span class="sxs-lookup"><span data-stu-id="d8910-117">Note the following in the SELECT clause:</span></span>  
  
-   <span data-ttu-id="d8910-118">L'identificateur CustomerID référence la table Cust.</span><span class="sxs-lookup"><span data-stu-id="d8910-118">The CustomerID references the Cust table.</span></span> <span data-ttu-id="d8910-119">Par conséquent, un élément <`Cust`> est créé et un attribut CustomerID y est ajouté.</span><span class="sxs-lookup"><span data-stu-id="d8910-119">Therefore, a <`Cust`> element is created and CustomerID is added as its attribute.</span></span>  
  
-   <span data-ttu-id="d8910-120">Ensuite, trois colonnes, OrderHeader.CustomerID, OrderHeader.SaleOrderID et OrderHeader.Status, référencent la table OrderHeader.</span><span class="sxs-lookup"><span data-stu-id="d8910-120">Next, three columns, OrderHeader.CustomerID, OrderHeader.SaleOrderID, and OrderHeader.Status, reference the OrderHeader table.</span></span> <span data-ttu-id="d8910-121">Par conséquent, un élément <`OrderHeader`> est ajouté en tant que sous-élément de l'élément <`Cust`> et les trois colonnes sont ajoutées en tant qu'attributs de <`OrderHeader`>.</span><span class="sxs-lookup"><span data-stu-id="d8910-121">Therefore, an <`OrderHeader`> element is added as a subelement of the <`Cust`> element and the three columns are added as attributes of <`OrderHeader`>.</span></span>  
  
-   <span data-ttu-id="d8910-122">Ensuite, la colonne Cust.CustomerType référence de nouveau la table Cust déjà identifiée par la colonne Cust.CustomerID.</span><span class="sxs-lookup"><span data-stu-id="d8910-122">Next, the Cust.CustomerType column again references the Cust table that was already identified by the Cust.CustomerID column.</span></span> <span data-ttu-id="d8910-123">Aucun nouvel élément n'est donc créé.</span><span class="sxs-lookup"><span data-stu-id="d8910-123">Therefore, no new element is created.</span></span> <span data-ttu-id="d8910-124">À la place, l'attribut CustomerType est ajouté à l'élément <`Cust`> précédemment créé.</span><span class="sxs-lookup"><span data-stu-id="d8910-124">Instead, the CustomerType attribute is added to the <`Cust`> element that was previously created.</span></span>  
  
-   <span data-ttu-id="d8910-125">La requête spécifie des alias pour les noms de tables.</span><span class="sxs-lookup"><span data-stu-id="d8910-125">The query specifies aliases for the table names.</span></span> <span data-ttu-id="d8910-126">Ces alias apparaissent sous la forme de noms d'éléments correspondants.</span><span class="sxs-lookup"><span data-stu-id="d8910-126">These aliases appear as corresponding element names.</span></span>  
  
-   <span data-ttu-id="d8910-127">La clause ORDER BY est requise pour regrouper tous les enfants situés sous un même parent.</span><span class="sxs-lookup"><span data-stu-id="d8910-127">ORDER BY is required to group all children under one parent.</span></span>  
  
 <span data-ttu-id="d8910-128">La requête suivante est similaire à la précédente, sauf que la clause SELECT spécifie des colonnes de la table OrderHeader avant les colonnes de la table Cust.</span><span class="sxs-lookup"><span data-stu-id="d8910-128">This query is similar to the previous one, except the SELECT clause specifies columns in the OrderHeader table before the columns in the Cust table.</span></span> <span data-ttu-id="d8910-129">Par conséquent, un premier élément <`OrderHeader`> est créé, auquel est ensuite ajouté l'élément enfant <`Cust`>.</span><span class="sxs-lookup"><span data-stu-id="d8910-129">Therefore, first <`OrderHeader`> element is created and then the <`Cust`> child element is added to it.</span></span>  
  
```  
select OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerID,   
       Cust.CustomerType  
from Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
where Cust.CustomerID = OrderHeader.CustomerID  
for xml auto  
```  
  
 <span data-ttu-id="d8910-130">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="d8910-130">This is the partial result:</span></span>  
  
```  
<OrderHeader CustomerID="1" SalesOrderID="43860" Status="5">  
  <Cust CustomerID="1" CustomerType="S" />  
</OrderHeader>  
...  
```  
  
 <span data-ttu-id="d8910-131">Si l'option ELEMENTS est ajoutée à la clause FOR XML, des données XML centrées sur l'élément sont renvoyées.</span><span class="sxs-lookup"><span data-stu-id="d8910-131">If the ELEMENTS option is added in the FOR XML clause, element-centric XML is returned.</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="d8910-132">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="d8910-132">This is the partial result:</span></span>  
  
```  
<Cust>  
  <CustomerID>1</CustomerID>  
  <CustomerType>S</CustomerType>  
  <OrderHeader>  
    <CustomerID>1</CustomerID>  
    <SalesOrderID>43860</SalesOrderID>  
    <Status>5</Status>  
  </OrderHeader>  
   ...  
</Cust>  
...  
```  
  
 <span data-ttu-id="d8910-133">Dans cette requête, les valeurs CustomerID sont comparées d’une ligne à l’autre lors de la création des éléments \<Cust>, car CustomerID est la clé primaire de la table.</span><span class="sxs-lookup"><span data-stu-id="d8910-133">In this query, the CustomerID values are compared from one row to the next in creating the \<Cust> elements, because CustomerID is the primary key of the table.</span></span> <span data-ttu-id="d8910-134">Si CustomerID n'est pas identifié en tant que clé primaire de la table, toutes les valeurs de colonnes (CustomerID et CustomerType dans cette requête) sont comparées d'une ligne à l'autre.</span><span class="sxs-lookup"><span data-stu-id="d8910-134">If CustomerID is not identified as the primary key for the table, all the column values (CustomerID, CustomerType in this query) are compared from one row to the next.</span></span> <span data-ttu-id="d8910-135">Si les valeurs diffèrent, un nouvel élément \<Cust> est ajouté au document XML.</span><span class="sxs-lookup"><span data-stu-id="d8910-135">If the values differ, a new \<Cust> element is added to the XML.</span></span>  
  
 <span data-ttu-id="d8910-136">Lors de la comparaison de ces valeurs de colonnes, si l’une des colonnes à comparer est de type **text**, **ntext**, **image**ou **xml**, la clause FOR XML considère que les valeurs sont différentes et non comparées, même si elles peuvent être identiques.</span><span class="sxs-lookup"><span data-stu-id="d8910-136">When comparing these column values, if any of the columns to be compared are of type **text**, **ntext**, **image**, or **xml**, FOR XML assumes that the values are different and not compared, even though they may be the same.</span></span> <span data-ttu-id="d8910-137">Cela est dû au fait que la comparaison des objets volumineux n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d8910-137">This is because comparing large objects is not supported.</span></span> <span data-ttu-id="d8910-138">Des éléments sont ajoutés au résultat pour chaque ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d8910-138">Elements are added to the result for each row selected.</span></span> <span data-ttu-id="d8910-139">Les colonnes de type **(n)varchar(max)** et **varbinary(max)** sont comparées.</span><span class="sxs-lookup"><span data-stu-id="d8910-139">Note that columns of **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="d8910-140">À l'image d'une colonne d'agrégation ou calculée, lorsqu'une colonne figurant dans la clause SELECT ne peut être associée à aucune des tables identifiées dans la clause FROM, elle est ajoutée au document XML dans le niveau d'imbrication le plus profond dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d8910-140">When a column in the SELECT clause cannot be associated with any of the tables identified in the FROM clause, as in the case of an aggregate column or computed column, the column is added in the XML document in the deepest nesting level in place when it is encountered in the list.</span></span> <span data-ttu-id="d8910-141">Si une telle colonne apparaît comme première colonne dans la clause SELECT, elle est ajoutée à l'élément supérieur.</span><span class="sxs-lookup"><span data-stu-id="d8910-141">If such a column appears as the first column in the SELECT clause, the column is added to the top element.</span></span>  
  
 <span data-ttu-id="d8910-142">Si le caractère générique astérisque « \* » est spécifié dans la clause SELECT, l'imbrication est déterminée de la même façon que celle précédemment décrite, en fonction de l'ordre dans lequel les lignes sont renvoyées par le moteur de requête.</span><span class="sxs-lookup"><span data-stu-id="d8910-142">If the asterisk (\*) wildcard character is specified in the SELECT clause, the nesting is determined in the same way as previously described, based on the order that the rows are returned by the query engine.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8910-143">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d8910-143">In This Section</span></span>  
 <span data-ttu-id="d8910-144">Les rubriques suivantes fournissent des informations supplémentaires sur le mode AUTO :</span><span class="sxs-lookup"><span data-stu-id="d8910-144">The following topics provide more information about AUTO mode:</span></span>  
  
-   [<span data-ttu-id="d8910-145">Utiliser l’option BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="d8910-145">Use the BINARY BASE64 Option</span></span>](use-the-binary-base64-option.md)  
  
-   [<span data-ttu-id="d8910-146">Heuristique du mode AUTO permettant de définir la forme des données XML renvoyées</span><span class="sxs-lookup"><span data-stu-id="d8910-146">AUTO Mode Heuristics in Shaping Returned XML</span></span>](auto-mode-heuristics-in-shaping-returned-xml.md)  
  
-   [<span data-ttu-id="d8910-147">Exemples : Utilisation du mode AUTO</span><span class="sxs-lookup"><span data-stu-id="d8910-147">Examples: Using AUTO Mode</span></span>](examples-using-auto-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8910-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8910-148">See Also</span></span>  
 <span data-ttu-id="d8910-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d8910-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="d8910-150">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d8910-150">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
