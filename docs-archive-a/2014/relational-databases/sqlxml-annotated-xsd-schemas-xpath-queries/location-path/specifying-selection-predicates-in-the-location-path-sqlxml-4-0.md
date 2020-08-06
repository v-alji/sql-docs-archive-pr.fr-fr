---
title: Spécification de prédicats de sélection dans le chemin d’accès d’emplacement (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- predicates [SQLXML]
- position-based filtering [SQLXML]
- XPath queries [SQLXML], location paths
- filtering [SQLXML]
- location path for XPath query
ms.assetid: dbef4cf4-a89b-4d7e-b72b-4062f7b29a80
author: rothja
ms.author: jroth
ms.openlocfilehash: d323558556fb05d350e48ea9218a8e9b8dc9b5c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610536"
---
# <a name="specifying-selection-predicates-in-the-location-path-sqlxml-40"></a><span data-ttu-id="7a106-102">Spécification de prédicats de sélection dans le chemin d'accès d'emplacement (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7a106-102">Specifying Selection Predicates in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="7a106-103">Un prédicat filtre un élément node-set par rapport à un axe (semblable à une clause WHERE dans une instruction SELECT).</span><span class="sxs-lookup"><span data-stu-id="7a106-103">A predicate filters a node-set with respect to an axis (similar to a WHERE clause in a SELECT statement).</span></span> <span data-ttu-id="7a106-104">Le prédicat est spécifié entre crochets.</span><span class="sxs-lookup"><span data-stu-id="7a106-104">The predicate is specified between brackets.</span></span> <span data-ttu-id="7a106-105">Pour chaque nœud de l'élément node-set à filtrer, l'expression de prédicat est évaluée avec ce nœud en tant que nœud de contexte et avec le nombre de nœuds de l'élément node-set en tant que taille de contexte.</span><span class="sxs-lookup"><span data-stu-id="7a106-105">For each node in the node-set to be filtered, the predicate expression is evaluated with that node as the context node, with the number of nodes in the node-set as context size.</span></span> <span data-ttu-id="7a106-106">Si l'expression de prédicat prend la valeur TRUE pour ce nœud, ce dernier est inclus dans l'élément node-set obtenu.</span><span class="sxs-lookup"><span data-stu-id="7a106-106">If the predicate expression evaluates to TRUE for that node, the node is included in the resulting node-set.</span></span>  
  
 <span data-ttu-id="7a106-107">XPath autorise également un filtrage basé sur les positions.</span><span class="sxs-lookup"><span data-stu-id="7a106-107">XPath also allows position-based filtering.</span></span> <span data-ttu-id="7a106-108">Une expression de prédicat qui correspond à un nombre sélectionne ce nœud ordinal.</span><span class="sxs-lookup"><span data-stu-id="7a106-108">A predicate expression evaluating to a number selects that ordinal node.</span></span> <span data-ttu-id="7a106-109">Par exemple, le chemin d'accès d'emplacement `Customer[3]` retourne le troisième client.</span><span class="sxs-lookup"><span data-stu-id="7a106-109">For example, the location path `Customer[3]` returns the third customer.</span></span> <span data-ttu-id="7a106-110">De tels prédicats numériques ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="7a106-110">Such numeric predicates are not supported.</span></span> <span data-ttu-id="7a106-111">Seules les expressions de prédicat qui retournent un résultat booléen sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="7a106-111">Only predicate expressions that return a Boolean result are supported.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a106-112">Pour plus d’informations sur les limitations de cette implémentation XPath de XPath et sur les différences entre elle et la spécification W3C, consultez [Introduction à l’utilisation de requêtes xpath &#40;SQLXML 4,0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="7a106-112">For information about the limitations of this XPath implementation of XPath and the differences between it and the W3C specification, see [Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span></span>  
  
## <a name="selection-predicate-example-1"></a><span data-ttu-id="7a106-113">Prédicat de sélection : exemple 1</span><span class="sxs-lookup"><span data-stu-id="7a106-113">Selection Predicate: Example 1</span></span>  
 <span data-ttu-id="7a106-114">L’expression XPath suivante (chemin d’accès d’emplacement) sélectionne à partir du nœud de contexte actuel tous les **\<Customer>** éléments enfants dont l’attribut **CustomerID** a la valeur ALFKI :</span><span class="sxs-lookup"><span data-stu-id="7a106-114">The following XPath expression (location path) selects from the current context node all the **\<Customer>** element children that have the **CustomerID** attribute with value of ALFKI:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="ALFKI"]  
```  
  
 <span data-ttu-id="7a106-115">Dans cette requête XPath, `child` et `attribute` sont les noms d'axes.</span><span class="sxs-lookup"><span data-stu-id="7a106-115">In this XPath query, `child` and `attribute` are axis names.</span></span> <span data-ttu-id="7a106-116">`Customer`est le test de nœud (TRUE si `Customer` est un **\<element node>** , car **\<element>** est le type de nœud principal de l' `child` axe).</span><span class="sxs-lookup"><span data-stu-id="7a106-116">`Customer` is the node test (TRUE if `Customer` is an **\<element node>**, because **\<element>** is the principal node type for the `child` axis).</span></span> <span data-ttu-id="7a106-117">`attribute::CustomerID="ALFKI"` est le prédicat.</span><span class="sxs-lookup"><span data-stu-id="7a106-117">`attribute::CustomerID="ALFKI"` is the predicate.</span></span> <span data-ttu-id="7a106-118">Dans le prédicat, `attribute` est l’axe et `CustomerID` est le test de nœud (true si **CustomerID** est un attribut du nœud de contexte, car **\<attribute>** est le type de nœud principal de `attribute` Axis).</span><span class="sxs-lookup"><span data-stu-id="7a106-118">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an attribute of the context node, because **\<attribute>** is the principal node type of `attribute` axis).</span></span>  
  
 <span data-ttu-id="7a106-119">À l'aide de la syntaxe abrégée, la requête XPath peut également être spécifiée de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="7a106-119">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer[@CustomerID="ALFKI"]  
```  
  
## <a name="selection-predicate-example-2"></a><span data-ttu-id="7a106-120">Prédicat de sélection : exemple 2</span><span class="sxs-lookup"><span data-stu-id="7a106-120">Selection Predicate: Example 2</span></span>  
 <span data-ttu-id="7a106-121">L’expression XPath suivante (chemin d’accès d’emplacement) sélectionne à partir du nœud de contexte actuel tous les petits-enfants ayant l' **\<Order>** attribut **SalesOrderID** avec la valeur 1 :</span><span class="sxs-lookup"><span data-stu-id="7a106-121">The following XPath expression (location path) selects from the current context node all the **\<Order>** grandchildren that have the **SalesOrderID** attribute with the value 1:</span></span>  
  
```  
/child::Customer/child::Order[attribute::SalesOrderID="1"]  
```  
  
 <span data-ttu-id="7a106-122">Dans cette expression XPath, `child` et `attribute` sont les noms des axes.</span><span class="sxs-lookup"><span data-stu-id="7a106-122">In this XPath expression, `child` and `attribute` are the axis names.</span></span> <span data-ttu-id="7a106-123">`Customer`, `Order` et `SalesOrderID` sont les tests de nœud.</span><span class="sxs-lookup"><span data-stu-id="7a106-123">`Customer`, `Order`, and `SalesOrderID` are the node tests.</span></span> <span data-ttu-id="7a106-124">`attribute::OrderID="1"` est le prédicat.</span><span class="sxs-lookup"><span data-stu-id="7a106-124">`attribute::OrderID="1"` is the predicate.</span></span>  
  
 <span data-ttu-id="7a106-125">À l'aide de la syntaxe abrégée, la requête XPath peut également être spécifiée de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="7a106-125">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer/Order[@SalesOrderID="1"]  
```  
  
## <a name="selection-predicate-example-3"></a><span data-ttu-id="7a106-126">Prédicat de sélection : exemple 3</span><span class="sxs-lookup"><span data-stu-id="7a106-126">Selection Predicate: Example 3</span></span>  
 <span data-ttu-id="7a106-127">L’expression XPath suivante (chemin d’accès d’emplacement) sélectionne à partir du nœud de contexte actuel tous les **\<Customer>** enfants qui ont un ou plusieurs **\<ContactName>** enfants :</span><span class="sxs-lookup"><span data-stu-id="7a106-127">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children that have one or more **\<ContactName>** children:</span></span>  
  
```  
child::Customer[child::ContactName]  
```  
  
 <span data-ttu-id="7a106-128">Cet exemple suppose que **\<ContactName>** est un élément enfant de l' **\<Customer>** élément dans le document XML, appelé *mappage centré* sur l’élément dans un schéma XSD annoté.</span><span class="sxs-lookup"><span data-stu-id="7a106-128">This example assumes that the **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, which is referred to as *element-centric mapping* in an annotated XSD schema.</span></span>  
  
 <span data-ttu-id="7a106-129">Dans cette expression XPath, `child` est le nom de l'axe.</span><span class="sxs-lookup"><span data-stu-id="7a106-129">In this XPath expression, `child` is the axis name.</span></span> <span data-ttu-id="7a106-130">`Customer`est le test de nœud (TRUE si `Customer` est un **\<element>** nœud, car **\<element>** est le type de nœud principal pour `child` Axis).</span><span class="sxs-lookup"><span data-stu-id="7a106-130">`Customer` is the node test (TRUE if `Customer` is an **\<element>** node, because **\<element>** is the principal node type for `child` axis).</span></span> <span data-ttu-id="7a106-131">`child::ContactName` est le prédicat.</span><span class="sxs-lookup"><span data-stu-id="7a106-131">`child::ContactName` is the predicate.</span></span> <span data-ttu-id="7a106-132">Dans le prédicat, `child` est l’axe et `ContactName` est le test de nœud (true si `ContactName` est un **\<element>** nœud).</span><span class="sxs-lookup"><span data-stu-id="7a106-132">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an **\<element>** node).</span></span>  
  
 <span data-ttu-id="7a106-133">Cette expression retourne uniquement les **\<Customer>** éléments enfants du nœud de contexte qui ont des **\<ContactName>** éléments enfants.</span><span class="sxs-lookup"><span data-stu-id="7a106-133">This expression returns only the **\<Customer>** element children of the context node that have **\<ContactName>** element children.</span></span>  
  
 <span data-ttu-id="7a106-134">À l'aide de la syntaxe abrégée, la requête XPath peut également être spécifiée de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="7a106-134">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[ContactName]  
```  
  
## <a name="selection-predicate-example-4"></a><span data-ttu-id="7a106-135">Prédicat de sélection : exemple 4</span><span class="sxs-lookup"><span data-stu-id="7a106-135">Selection Predicate: Example 4</span></span>  
 <span data-ttu-id="7a106-136">L’expression XPath suivante sélectionne les **\<Customer>** éléments enfants du nœud de contexte qui n’ont pas d' **\<ContactName>** éléments enfants :</span><span class="sxs-lookup"><span data-stu-id="7a106-136">The following XPath expression selects **\<Customer>** element children of the context node that do not have **\<ContactName>** element children:</span></span>  
  
```  
child::Customer[not(child::ContactName)]  
```  
  
 <span data-ttu-id="7a106-137">Cet exemple suppose que **\<ContactName>** est un élément enfant de l' **\<Customer>** élément dans le document XML et que le champ ContactName n’est pas requis dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="7a106-137">This example assumes that **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, and the ContactName field is not required in the database.</span></span>  
  
 <span data-ttu-id="7a106-138">Dans cet exemple, `child` est l'axe.</span><span class="sxs-lookup"><span data-stu-id="7a106-138">In this example, `child` is the axis.</span></span> <span data-ttu-id="7a106-139">`Customer`est le test de nœud (TRUE si `Customer` est un \<element> nœud).</span><span class="sxs-lookup"><span data-stu-id="7a106-139">`Customer` is the node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="7a106-140">`not(child::ContactName)` est le prédicat.</span><span class="sxs-lookup"><span data-stu-id="7a106-140">`not(child::ContactName)` is the predicate.</span></span> <span data-ttu-id="7a106-141">Dans le prédicat, `child` est l’axe et `ContactName` est le test de nœud (true si `ContactName` est un \<element> nœud).</span><span class="sxs-lookup"><span data-stu-id="7a106-141">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an \<element> node).</span></span>  
  
 <span data-ttu-id="7a106-142">À l'aide de la syntaxe abrégée, la requête XPath peut également être spécifiée de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="7a106-142">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[not(ContactName)]  
```  
  
## <a name="selection-predicate-example-5"></a><span data-ttu-id="7a106-143">Prédicat de sélection : exemple 5</span><span class="sxs-lookup"><span data-stu-id="7a106-143">Selection Predicate: Example 5</span></span>  
 <span data-ttu-id="7a106-144">L’expression XPath suivante sélectionne à partir du nœud de contexte actuel tous les **\<Customer>** enfants qui ont l’attribut **CustomerID** :</span><span class="sxs-lookup"><span data-stu-id="7a106-144">The following XPath expression selects from the current context node all the **\<Customer>** children that have the **CustomerID** attribute:</span></span>  
  
```  
child::Customer[attribute::CustomerID]  
```  
  
 <span data-ttu-id="7a106-145">Dans cet exemple, `child` est l’axe et `Customer` est le test de nœud (true si `Customer` est un \<element> nœud).</span><span class="sxs-lookup"><span data-stu-id="7a106-145">In this example, `child` is the axis and `Customer` is node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="7a106-146">`attribute::CustomerID` est le prédicat.</span><span class="sxs-lookup"><span data-stu-id="7a106-146">`attribute::CustomerID` is the predicate.</span></span> <span data-ttu-id="7a106-147">Dans le prédicat, `attribute` est l’axe et `CustomerID` est le PRÉDICAT (true si `CustomerID` est un **\<attribute>** nœud).</span><span class="sxs-lookup"><span data-stu-id="7a106-147">In the predicate, `attribute` is the axis and `CustomerID` is the predicate (TRUE if `CustomerID` is an **\<attribute>** node).</span></span>  
  
 <span data-ttu-id="7a106-148">À l'aide de la syntaxe abrégée, la requête XPath peut également être spécifiée de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="7a106-148">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[@CustomerID]  
```  
  
## <a name="selection-predicate-example-6"></a><span data-ttu-id="7a106-149">Prédicat de sélection : exemple 6</span><span class="sxs-lookup"><span data-stu-id="7a106-149">Selection Predicate: Example 6</span></span>  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="7a106-150">SQLXML 4.0 inclut la prise en charge des requêtes XPath qui contiennent un produit croisé dans le prédicat, comme l'illustre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="7a106-150">SQLXML 4.0 includes support for XPath queries that contain a cross-product in the predicate, as shown in the following example:</span></span>  
  
```  
Customer[Order/@OrderDate=Order/@ShipDate]  
```  
  
 <span data-ttu-id="7a106-151">Cette requête sélectionne tous les clients avec un `Order` quelconque pour lequel `OrderDate` est égal au `ShipDate` de tout `Order`.</span><span class="sxs-lookup"><span data-stu-id="7a106-151">This query selects all customers with any `Order` for which the `OrderDate` equals the `ShipDate` of any `Order`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a106-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a106-152">See Also</span></span>  
 <span data-ttu-id="7a106-153">[Présentation des schémas XSD annotés &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="7a106-153">[Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="7a106-154">Mise en forme XML côté client &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7a106-154">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
