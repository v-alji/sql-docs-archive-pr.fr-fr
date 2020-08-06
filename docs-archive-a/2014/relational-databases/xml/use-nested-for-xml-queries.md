---
title: Utiliser des requêtes FOR XML imbriquées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, nested FOR XML queries
- queries [XML in SQL Server], nested FOR XML
- nested FOR XML queries
ms.assetid: 7604161a-a958-446d-b102-7dee432979d0
author: rothja
ms.author: jroth
ms.openlocfilehash: 60c4198697f8d19c9b2e5bc1b415e0787861d40a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706280"
---
# <a name="use-nested-for-xml-queries"></a><span data-ttu-id="8e532-102">Utiliser des requêtes FOR XML imbriquées</span><span class="sxs-lookup"><span data-stu-id="8e532-102">Use Nested FOR XML Queries</span></span>
  <span data-ttu-id="8e532-103">Le `xml` type de données et la [directive type dans les requêtes for XML](type-directive-in-for-xml-queries.md) permettent au XML retourné par les requêtes for XML d’être traité sur le serveur et sur le client.</span><span class="sxs-lookup"><span data-stu-id="8e532-103">The `xml` data type and the [TYPE directive in FOR XML queries](type-directive-in-for-xml-queries.md) enable the XML returned by the FOR XML queries to be processed on the server as well as on the client.</span></span>  
  
## <a name="processing-with-xml-type-variables"></a><span data-ttu-id="8e532-104">Traitement avec des variables de type xml</span><span class="sxs-lookup"><span data-stu-id="8e532-104">Processing with xml Type Variables</span></span>  
 <span data-ttu-id="8e532-105">Vous pouvez affecter le résultat de la requête FOR XML à une variable de type `xml` ou bien utiliser XQuery pour interroger le résultat et affecter celui-ci à une variable de type `xml` en vue d'un traitement supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="8e532-105">You can assign the FOR XML query result to an `xml` type variable, or use XQuery to query the result, and assign that result to an `xml` type variable for more processing.</span></span>  
  
```  
DECLARE @x xml  
SET @x=(SELECT ProductModelID, Name  
        FROM Production.ProductModel  
        WHERE ProductModelID=122 or ProductModelID=119  
        FOR XML RAW, TYPE)  
SELECT @x  
-- Result  
--<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
--<row ProductModelID="119" Name="Bike Wash" />  
```  
  
 <span data-ttu-id="8e532-106">Vous pouvez poursuivre le traitement du document XML renvoyé dans la variable `@x` à l'aide de l'une des méthodes de type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="8e532-106">You can additionally process the XML returned in the variable, `@x`, by using one of the `xml` data type methods.</span></span> <span data-ttu-id="8e532-107">Par exemple, vous pouvez extraire la valeur de l’attribut `ProductModelID` à l’aide de la [méthode value()](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="8e532-107">For example, you can retrieve the `ProductModelID` attribute value by using the [value() method](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
DECLARE @i int;  
SET @i = (SELECT @x.value('/row[1]/@ProductModelID[1]', 'int'));  
SELECT @i;  
```  
  
 <span data-ttu-id="8e532-108">Dans l'exemple suivant, le résultat de la requête `FOR XML` renvoyé est de type `xml` car la directive `TYPE` est spécifiée dans la clause `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="8e532-108">In the following example, the `FOR XML` query result is returned as an `xml` type, because the `TYPE` directive is specified in the `FOR XML` clause.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=119 or ProductModelID=122  
FOR XML RAW, TYPE,ROOT('myRoot');  
  
```  
  
 <span data-ttu-id="8e532-109">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="8e532-109">This is the result:</span></span>  
  
```  
<myRoot>  
  <row ProductModelID="122" Name="All-Purpose Bike Stand" />  
  <row ProductModelID="119" Name="Bike Wash" />  
</myRoot>  
```  
  
 <span data-ttu-id="8e532-110">Étant donné que le résultat est de type `xml`, vous pouvez spécifier l'une des méthodes de type de données `xml` directement par rapport à ce document XML, comme le montre la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="8e532-110">Because the result is of `xml` type, you can specify one of the `xml` data type methods directly against this XML, as shown in the following query.</span></span> <span data-ttu-id="8e532-111">Dans la requête, la [méthode query() (type de données xml)](/sql/t-sql/xml/query-method-xml-data-type) est utilisée pour extraire le premier élément enfant <`row`> de l’élément <`myRoot`>.</span><span class="sxs-lookup"><span data-stu-id="8e532-111">In the query, the [query() method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) is used to retrieve the first <`row`> element child of the <`myRoot`> element.</span></span>  
  
```  
SELECT  (SELECT ProductModelID, Name  
         FROM Production.ProductModel  
         WHERE ProductModelID=119 or ProductModelID=122  
         FOR XML RAW, TYPE,ROOT('myRoot')).query('/myRoot[1]/row[1]');  
  
```  
  
 <span data-ttu-id="8e532-112">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="8e532-112">This is the result:</span></span>  
  
```  
<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
```  
  
## <a name="returning-inner-for-xml-query-results-to-outer-queries-as-xml-type-instances"></a><span data-ttu-id="8e532-113">Renvoi de résultats de requêtes FOR XML internes à des requêtes externes en tant qu'instances de type xml</span><span class="sxs-lookup"><span data-stu-id="8e532-113">Returning Inner FOR XML Query Results to Outer Queries as xml Type Instances</span></span>  
 <span data-ttu-id="8e532-114">Vous pouvez écrire des requêtes `FOR XML` imbriquées où le résultat de la requête interne est retourné en tant que type `xml` à la requête externe.</span><span class="sxs-lookup"><span data-stu-id="8e532-114">You can write nested `FOR XML` queries where the result of the inner query is returned as an `xml` type to the outer query.</span></span> <span data-ttu-id="8e532-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8e532-115">For example:</span></span>  
  
```  
SELECT Col1,   
       Col2,   
       ( SELECT Col3, Col4   
        FROM  T2  
        WHERE T2.Col = T1.Col  
        ...  
        FOR XML AUTO, TYPE )  
FROM T1  
WHERE ...  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="8e532-116">Notez les points suivants dans la requête précédente :</span><span class="sxs-lookup"><span data-stu-id="8e532-116">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="8e532-117">Le XML généré par la requête `FOR XML` interne est ajouté au XML généré par la requête `FOR XML`externe.</span><span class="sxs-lookup"><span data-stu-id="8e532-117">The XML generated by the inner `FOR XML` query is added to the XML generated by the outer `FOR XML`.</span></span>  
  
-   <span data-ttu-id="8e532-118">La requête interne spécifie la directive `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="8e532-118">The inner query specifies the `TYPE` directive.</span></span> <span data-ttu-id="8e532-119">Par conséquent, les données XML retournées par la requête interne sont du type `xml`.</span><span class="sxs-lookup"><span data-stu-id="8e532-119">Therefore, the XML data returned by the inner query is of `xml` type.</span></span> <span data-ttu-id="8e532-120">Si la directive TYPE n'est pas spécifiée, le résultat de la requête `FOR XML` interne est retourné en tant que `nvarchar(max)` et les données XML sont converties en entités.</span><span class="sxs-lookup"><span data-stu-id="8e532-120">If the TYPE directive is not specified, the result of the inner `FOR XML` query is returned as `nvarchar(max)` and the XML data is entitized.</span></span>  
  
## <a name="controlling-the-shape-of-resulting-xml-data"></a><span data-ttu-id="8e532-121">Contrôle de la forme des données XML résultantes</span><span class="sxs-lookup"><span data-stu-id="8e532-121">Controlling the Shape of Resulting XML Data</span></span>  
 <span data-ttu-id="8e532-122">Les requêtes FOR XML imbriquées vous permettent de mieux contrôler la forme des données XML résultantes.</span><span class="sxs-lookup"><span data-stu-id="8e532-122">Nested FOR XML queries give you more control in defining the shape of the resulting XML data.</span></span> <span data-ttu-id="8e532-123">Vous pouvez utiliser des requêtes FOR XML imbriquées pour construire des données XML centrées partiellement sur l'attribut et partiellement sur l'élément.</span><span class="sxs-lookup"><span data-stu-id="8e532-123">You can use nested FOR XML queries to construct XML that is partly attribute-centric and partly element-centric.</span></span>  
  
 <span data-ttu-id="8e532-124">Pour plus d’informations sur la spécification de données XML centrées sur l’attribut et sur l’élément avec des requêtes FOR XML imbriquées, consultez [Comparaison de la requête FOR XML et de la requête FOR XML imbriquée](../xml/for-xml-query-compared-to-nested-for-xml-query.md) et [Façonner des données XML avec des requêtes FOR XML imbriquées](../xml/shape-xml-with-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="8e532-124">For more information about specifying both attribute-centric and element-centric XML with nested FOR XML queries, see [FOR XML Query Compared to Nested FOR XML Query](../xml/for-xml-query-compared-to-nested-for-xml-query.md) and [Shape XML with Nested FOR XML Queries](../xml/shape-xml-with-nested-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="8e532-125">Vous pouvez générer des hiérarchies XML qui incluent des frères en spécifiant des requêtes FOR XML en mode AUTO imbriquées.</span><span class="sxs-lookup"><span data-stu-id="8e532-125">You can generate XML hierarchies that include siblings by specifying nested AUTO mode FOR XML queries.</span></span> <span data-ttu-id="8e532-126">Pour plus d’informations, consultez [Générer des frères à l’aide d’une requête imbriquée en mode AUTO](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span><span class="sxs-lookup"><span data-stu-id="8e532-126">For more information, see [Generate Siblings with a Nested AUTO Mode Query](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span></span>  
  
 <span data-ttu-id="8e532-127">Quel que soit le mode utilisé, les requêtes FOR XML imbriquées procurent davantage de contrôle dans la description de la forme des données XML résultantes.</span><span class="sxs-lookup"><span data-stu-id="8e532-127">Regardless of which mode you use, nested FOR XML queries provide more control in describing the shape of the resulting XML.</span></span> <span data-ttu-id="8e532-128">Elles peuvent être utilisées à la place des requêtes en mode EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="8e532-128">They can be used in the place of EXPLICIT mode queries.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8e532-129">Exemples</span><span class="sxs-lookup"><span data-stu-id="8e532-129">Examples</span></span>  
 <span data-ttu-id="8e532-130">Les rubriques suivantes fournissent des exemples de requêtes FOR XML imbriquées.</span><span class="sxs-lookup"><span data-stu-id="8e532-130">The following topics provide examples of nested FOR XML queries.</span></span>  
  
 [<span data-ttu-id="8e532-131">Comparaison de la requête FOR XML et de la requête FOR XML imbriquée</span><span class="sxs-lookup"><span data-stu-id="8e532-131">FOR XML Query Compared to Nested FOR XML Query</span></span>](../xml/for-xml-query-compared-to-nested-for-xml-query.md)  
 <span data-ttu-id="8e532-132">Compare une requête FOR XML d'un seul niveau à une requête FOR XML imbriquée.</span><span class="sxs-lookup"><span data-stu-id="8e532-132">Compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="8e532-133">Cet exemple inclut une démonstration de la manière de spécifier à la fois des données XML centrées sur l'attribut et centrées sur l'élément comme résultat de requête.</span><span class="sxs-lookup"><span data-stu-id="8e532-133">This example includes a demonstration of how to specify both attribute-centric and element-centric XML as the result of the query.</span></span>  
  
 [<span data-ttu-id="8e532-134">Générer des frères à l’aide d’une requête imbriquée en mode AUTO</span><span class="sxs-lookup"><span data-stu-id="8e532-134">Generate Siblings with a Nested AUTO Mode Query</span></span>](../xml/generate-siblings-with-a-nested-auto-mode-query.md)  
 <span data-ttu-id="8e532-135">Montre comment générer des frères à l'aide d'une requête imbriquée en mode AUTO</span><span class="sxs-lookup"><span data-stu-id="8e532-135">Shows how to generate siblings by using a nested AUTO mode query</span></span>  
  
 [<span data-ttu-id="8e532-136">Utiliser des requêtes FOR XML imbriquées dans ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8e532-136">Use Nested FOR XML Queries in ASP.NET</span></span>](use-nested-for-xml-queries-in-asp-net.md)  
 <span data-ttu-id="8e532-137">Montre comment une application ASPX peut utiliser FOR XML pour retourner des données XML à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e532-137">Demonstrates how an ASPX application can use FOR XML to return XML from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="8e532-138">Façonner des données XML avec des requêtes FOR XML imbriquées</span><span class="sxs-lookup"><span data-stu-id="8e532-138">Shape XML with Nested FOR XML Queries</span></span>](../xml/shape-xml-with-nested-for-xml-queries.md)  
 <span data-ttu-id="8e532-139">Montre comment utiliser des requêtes FOR XML imbriquées pour contrôler la structure d'un document XML créé par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e532-139">Shows how to use nested FOR XML queries to control the structure of an XML document created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
