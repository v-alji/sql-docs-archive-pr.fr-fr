---
title: Ajouter des espaces de noms aux requêtes avec WITH XMLNAMESPACES | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENTS XSINIL directive
- adding namespaces
- XSINIL directive
- default namespaces
- queries [XML in SQL Server], WITH XMLNAMESPACES clause
- predefined namespaces [XML in SQL Server]
- FOR XML clause, WITH XMLNAMESPACES clause
- namespaces [XML in SQL Server]
- xml data type [SQL Server], WITH XMLNAMESPACES clause
- WITH XMLNAMESPACES clause
ms.assetid: 2189cb5e-4460-46c5-a254-20c833ebbfec
author: rothja
ms.author: jroth
ms.openlocfilehash: ed5d719a845996215fffc18af64401779f848cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600699"
---
# <a name="add-namespaces-to-queries-with-with-xmlnamespaces"></a><span data-ttu-id="269d3-102">Ajouter des espaces de noms aux requêtes avec WITH XMLNAMESPACES</span><span class="sxs-lookup"><span data-stu-id="269d3-102">Add Namespaces to Queries with WITH XMLNAMESPACES</span></span>
  <span data-ttu-id="269d3-103">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) fournit une prise en charge des URI d’espace de noms de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="269d3-103">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) provides namespace URI support in the following way:</span></span>  
  
-   <span data-ttu-id="269d3-104">Il rend le préfixe de l’espace de noms associé au mappage d’URI disponible lors de la [Construction de données XML à l’aide de requêtes FOR XML](for-xml-sql-server.md) .</span><span class="sxs-lookup"><span data-stu-id="269d3-104">It makes the namespace prefix to URI mapping available when [Constructing XML Using FOR XML](for-xml-sql-server.md) queries.</span></span>  
  
-   <span data-ttu-id="269d3-105">Il met l’espace de noms associé au mappage d’URI à la disposition du contexte d’espace de noms statique des [méthodes de type de données xml](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="269d3-105">It makes the namespace to URI mapping available to the static namespace context of the [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span>  
  
## <a name="using-with-xmlnamespaces-in-the-for-xml-queries"></a><span data-ttu-id="269d3-106">Utilisation de WITH XMLNAMESPACES dans les requêtes FOR XML</span><span class="sxs-lookup"><span data-stu-id="269d3-106">Using WITH XMLNAMESPACES in the FOR XML Queries</span></span>  
 <span data-ttu-id="269d3-107">WITH XMLNAMESPACES vous permet d'inclure des espaces de noms XML dans des requêtes FOR XML.</span><span class="sxs-lookup"><span data-stu-id="269d3-107">WITH XMLNAMESPACES lets you include XML namespaces in FOR XML queries.</span></span> <span data-ttu-id="269d3-108">Examinons, par exemple, la requête FOR XML suivante :</span><span class="sxs-lookup"><span data-stu-id="269d3-108">For example, consider the following FOR XML query:</span></span>  
  
```  
SELECT ProductID, Name, Color  
FROM   Production.Product  
WHERE  ProductID=316 or ProductID=317  
FOR XML RAW  
```  
  
 <span data-ttu-id="269d3-109">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="269d3-109">This is the result:</span></span>  
  
```  
<row ProductID="316" Name="Blade" />  
<row ProductID="317" Name="LL Crankarm" Color="Black" />  
  
```  
  
 <span data-ttu-id="269d3-110">Pour ajouter des espaces de noms aux données XML générées par la requête FOR XML, commencez par spécifier le préfixe d'espace de noms associé aux mappages d'URI à l'aide de la clause WITH NAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="269d3-110">To add namespaces to the XML constructed by the FOR XML query, first specify the namespace prefix to URI mappings by using the WITH NAMESPACES clause.</span></span> <span data-ttu-id="269d3-111">Ensuite, utilisez les préfixes d'espace de noms pour spécifier les noms dans la requête, comme illustré dans la requête modifiée ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="269d3-111">Then, use the namespace prefixes in specifying the names in the query as shown in the following modified query.</span></span> <span data-ttu-id="269d3-112">Notez que la clause WITH XMLNAMESPACES spécifie le préfixe d'espace de noms (`ns1`) au mappage d'URI (`uri`).</span><span class="sxs-lookup"><span data-stu-id="269d3-112">Note that the WITH XMLNAMESPACES clause specifies the namespace prefix (`ns1`) to URI (`uri`) mapping.</span></span> <span data-ttu-id="269d3-113">Le préfixe `ns1` est alors utilisé pour spécifier les noms d'élément et d'attribut que doit générer la requête FOR XML.</span><span class="sxs-lookup"><span data-stu-id="269d3-113">The `ns1` prefix is then used in specifying the element and attribute names to be constructed by the FOR XML query.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Prod'), ELEMENTS  
  
```  
  
 <span data-ttu-id="269d3-114">Le résultat XML inclut les préfixes d'espace de noms :</span><span class="sxs-lookup"><span data-stu-id="269d3-114">The XML result includes the namespace prefixes:</span></span>  
  
```  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
</ns1:Prod>  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>317</ns1:ProductID>  
  <ns1:Name>LL Crankarm</ns1:Name>  
  <ns1:Color>Black</ns1:Color>  
</ns1:Prod>  
  
```  
  
 <span data-ttu-id="269d3-115">Ce qui suit s'applique à la clause WITH XMLNAMESPACES :</span><span class="sxs-lookup"><span data-stu-id="269d3-115">The following applies to the WITH XMLNAMESPACES clause:</span></span>  
  
-   <span data-ttu-id="269d3-116">Cela est pris en charge uniquement sur les modes RAW, AUTO et PATH des requêtes FOR XML.</span><span class="sxs-lookup"><span data-stu-id="269d3-116">It is supported only on the RAW, AUTO, and PATH modes of the FOR XML queries.</span></span> <span data-ttu-id="269d3-117">Le mode EXPLICIT n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="269d3-117">The EXPLICIT mode is not supported.</span></span>  
  
-   <span data-ttu-id="269d3-118">Il affecte uniquement les préfixes d’espace de noms des requêtes FOR XML et les méthodes de type de données **xml** , mais pas l’analyseur XML.</span><span class="sxs-lookup"><span data-stu-id="269d3-118">It only affects the namespace prefixes of FOR XML queries and the **xml** data type methods, but not the XML parser.</span></span> <span data-ttu-id="269d3-119">Par exemple, la requête ci-dessous retourne une erreur, car le document XML ne possède pas de déclaration d'espace de noms pour le préfixe myNS.</span><span class="sxs-lookup"><span data-stu-id="269d3-119">For example, the following query returns an error, because the XML document has no namespace declaration for the myNS prefix.</span></span>  
  
-   <span data-ttu-id="269d3-120">Les directives FOR XML, XMLSCHEMA et XMLDATA ne peuvent pas être utilisées lorsqu'une clause WITH XMLNAMESPACES est utilisée.</span><span class="sxs-lookup"><span data-stu-id="269d3-120">The FOR XML directives, XMLSCHEMA and XMLDATA cannot be used when a WITH XMLNAMESPACES clause is being used.</span></span>  
  
    ```  
    CREATE TABLE T (x xml)  
    go  
    WITH XMLNAMESPACES ('http://abc' as myNS )  
    INSERT INTO T VALUES('<myNS:root/>')  
    ```  
  
## <a name="using-the-xsinil-directive"></a><span data-ttu-id="269d3-121">Utilisation de la directive XSINIL</span><span class="sxs-lookup"><span data-stu-id="269d3-121">Using the XSINIL Directive</span></span>  
 <span data-ttu-id="269d3-122">Vous ne pouvez pas définir le préfixe xsi dans la clause WITH XMLNAMESPACES si vous utilisez la directive ELEMENTS XSINIL.</span><span class="sxs-lookup"><span data-stu-id="269d3-122">You cannot define the xsi prefix in the WITH XMLNAMESPACES clause if you are using the ELEMENTS XSINIL directive.</span></span> <span data-ttu-id="269d3-123">À la place, il est ajouté automatiquement lorsque vous utilisez ELEMENTS XSINIL.</span><span class="sxs-lookup"><span data-stu-id="269d3-123">Instead, it is added automatically when you use ELEMENTS XSINIL.</span></span> <span data-ttu-id="269d3-124">La requête ci-dessous utilise ELEMENTS XSINIL qui génère des données XML centrées sur les éléments, dans lesquelles les valeurs Null sont mappées sur les éléments dont l’attribut **xsi:nil** a la valeur True.</span><span class="sxs-lookup"><span data-stu-id="269d3-124">The following query uses ELEMENTS XSINIL that generates element-centric XML where null values are mapped to elements that have the **xsi:nil** attribute set to True.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316   
FOR XML RAW, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="269d3-125">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="269d3-125">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
  <ns1:Color xsi:nil="true" />  
</row>  
```  
  
## <a name="specifying-default-namespaces"></a><span data-ttu-id="269d3-126">Spécification d'espaces de noms par défaut</span><span class="sxs-lookup"><span data-stu-id="269d3-126">Specifying Default Namespaces</span></span>  
 <span data-ttu-id="269d3-127">Au lieu de déclarer un préfixe d'espace de noms, vous pouvez déclarer un espace de noms par défaut en utilisant un mot clé DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="269d3-127">Instead of declaring a namespace prefix, you can declare a default namespace by using a DEFAULT keyword.</span></span> <span data-ttu-id="269d3-128">Dans la requête FOR XML, il liera l'espace de noms par défaut aux nœuds XML dans les données XML résultantes.</span><span class="sxs-lookup"><span data-stu-id="269d3-128">In the FOR XML query, it will bind the default namespace to XML nodes in the resulting XML.</span></span> <span data-ttu-id="269d3-129">Dans l'exemple ci-dessous, WITH XMLNAMESPACES définit deux préfixes d'espaces de noms qui sont définis ensemble à l'aide d'un espace de noms par défaut.</span><span class="sxs-lookup"><span data-stu-id="269d3-129">In the following example, the WITH XMLNAMESPACES defines two namespace prefixes that are defined together with a default namespace.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,   
                    'uri2' as ns2,  
                    DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product   
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Product'), ROOT('ns2:root'), ELEMENTS  
```  
  
 <span data-ttu-id="269d3-130">La requête FOR XML génère des données XML centrées sur les éléments.</span><span class="sxs-lookup"><span data-stu-id="269d3-130">The FOR XML query generates element-centric XML.</span></span> <span data-ttu-id="269d3-131">Notez que la requête utilise les deux préfixes d'espaces de noms dans l'affectation de noms aux nœuds.</span><span class="sxs-lookup"><span data-stu-id="269d3-131">Note that the query uses both the namespace prefixes in naming nodes.</span></span> <span data-ttu-id="269d3-132">Dans la clause SELECT, ProductID, Name et Color ne spécifient pas de nom avec un préfixe quelconque.</span><span class="sxs-lookup"><span data-stu-id="269d3-132">In the SELECT clause, the ProductID, Name, and Color do not specify a name with any prefix.</span></span> <span data-ttu-id="269d3-133">Par conséquent, les éléments correspondants dans les données XML résultantes appartiennent à l'espace de noms par défaut.</span><span class="sxs-lookup"><span data-stu-id="269d3-133">Therefore, the corresponding elements in the resulting XML belong to the default namespace.</span></span>  
  
```  
<ns2:root xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">  
  <ns1:Product>  
    <ProductID>316</ProductID>  
    <Name>Blade</Name>  
  </ns1:Product>  
  <ns1:Product>  
    <ProductID>317</ProductID>  
    <Name>LL Crankarm</Name>  
    <Color>Black</Color>  
  </ns1:Product>  
</ns2:root>  
```  
  
 <span data-ttu-id="269d3-134">La requête ci-dessous est similaire à la précédente, mais le mode FOR XML AUTO est spécifié.</span><span class="sxs-lookup"><span data-stu-id="269d3-134">The following query is similar to the previous one, except that the FOR XML AUTO mode is specified.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,  'uri2' as ns2,DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product as "ns1:Product"  
WHERE ProductID=316 or ProductID=317  
FOR XML AUTO, ROOT('ns2:root'), ELEMENTS  
```  
  
## <a name="using-predefined-namespaces"></a><span data-ttu-id="269d3-135">Utilisation d'espaces de noms prédéfinis</span><span class="sxs-lookup"><span data-stu-id="269d3-135">Using Predefined Namespaces</span></span>  
 <span data-ttu-id="269d3-136">Lorsque vous utilisez des espaces de noms prédéfinis, à l'exception des espaces de noms xml et xsi lorsque ELEMENTS XSINIL est utilisé, vous devez spécifier explicitement la liaison avec les espaces de noms à l'aide de WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="269d3-136">When you use predefined namespaces, except the xml namespace and the xsi namespace when ELEMENTS XSINIL is used, you must explicitly specify the namespace binding by using WITH XMLNAMESPACES.</span></span> <span data-ttu-id="269d3-137">La requête ci-dessous définit explicitement le préfixe d'espace de noms associé à la liaison d'URI pour l'espace de noms prédéfini (`urn:schemas-microsoft-com:xml-sql`).</span><span class="sxs-lookup"><span data-stu-id="269d3-137">The following query explicitly defines the namespace prefix to URI binding for the predefined namespace (`urn:schemas-microsoft-com:xml-sql`).</span></span>  
  
```  
WITH XMLNAMESPACES ('urn:schemas-microsoft-com:xml-sql' as sql)  
SELECT 'SELECT * FROM Customers FOR XML AUTO, ROOT("a")' AS "sql:query"  
FOR XML PATH('sql:root')  
```  
  
 <span data-ttu-id="269d3-138">Voici l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="269d3-138">This is the result.</span></span> <span data-ttu-id="269d3-139">Les utilisateurs SQLXML sont familiarisés avec ce modèle XML.</span><span class="sxs-lookup"><span data-stu-id="269d3-139">SQLXML users are familiar with this XML template.</span></span> <span data-ttu-id="269d3-140">Pour plus d’informations, consultez [Concepts de la programmation SQLXML 4.0](../sqlxml/sqlxml-4-0-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="269d3-140">For more information, see [SQLXML 4.0 Programming Concepts](../sqlxml/sqlxml-4-0-programming-concepts.md).</span></span>  
  
```  
<sql:root xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>SELECT * FROM Customers FOR XML AUTO, ROOT("a")</sql:query>  
</sql:root>  
```  
  
 <span data-ttu-id="269d3-141">Seul le préfixe d'espace de noms xml peut être utilisé sans qu'il soit défini explicitement dans WITH XMLNAMESPACES, comme l'illustre la requête en mode PATH ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="269d3-141">Only the xml namespace prefix can be used without explicitly defining it in WITH XMLNAMESPACES, as shown in the following PATH mode query.</span></span> <span data-ttu-id="269d3-142">En outre, si le préfixe est déclaré, il doit être lié à l’espace de noms http://www.w3.org/XML/1998/namespace.</span><span class="sxs-lookup"><span data-stu-id="269d3-142">Also, if the prefix is declared, it has to be bound to the namespace http://www.w3.org/XML/1998/namespace.</span></span> <span data-ttu-id="269d3-143">Les noms spécifiés dans la clause SELECT font référence au préfixe d'espace de noms xml qui n'est pas défini explicitement à l'aide de WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="269d3-143">The names specified in the SELECT clause refer to the xml namespace prefix that is not explicitly defined by using WITH XMLNAMESPACES.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
go  
```  
  
 <span data-ttu-id="269d3-144">Les attributs @xml:lang utilisent l’espace de noms xml prédéfini.</span><span class="sxs-lookup"><span data-stu-id="269d3-144">The @xml:lang attributes use the predefined xml namespace.</span></span> <span data-ttu-id="269d3-145">Comme XML version 1.0 ne requiert pas la déclaration explicite de la liaison d'espace de noms xml, le résultat n'inclut pas de déclaration explicite de la liaison d'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="269d3-145">Because XML version 1.0 does not require the explicit declaration of the xml namespace binding, the result will not include an explicit declaration of the namespace binding.</span></span>  
  
 <span data-ttu-id="269d3-146">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="269d3-146">This is the result:</span></span>  
  
```  
<Translation>  
  <English xml:lang="en">food</English>  
  <German xml:lang="ger">Essen</German>  
</Translation>  
```  
  
## <a name="using-with-xmlnamespaces-with-the-xml-data-type-methods"></a><span data-ttu-id="269d3-147">Utilisation de WITH XMLNAMESPACES avec les méthodes de type de données xml</span><span class="sxs-lookup"><span data-stu-id="269d3-147">Using WITH XMLNAMESPACES with the xml Data Type Methods</span></span>  
 <span data-ttu-id="269d3-148">Les [méthodes de type de données xml](/sql/t-sql/xml/xml-data-type-methods) spécifiées dans une requête SELECT, ou dans UPDATE quand il s’agit de la méthode **modify()** , doivent toutes répéter la déclaration d’espace de noms dans leur prologue.</span><span class="sxs-lookup"><span data-stu-id="269d3-148">The [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) specified in a SELECT query, or in UPDATE when it is the **modify()** method, all have to repeat the namespace declaration in their prolog.</span></span> <span data-ttu-id="269d3-149">Ceci peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="269d3-149">This can be time-consuming.</span></span> <span data-ttu-id="269d3-150">Par exemple, la requête ci-dessous récupère les identificateurs des modèles de produits dont les descriptions de catalogue incluent une spécification.</span><span class="sxs-lookup"><span data-stu-id="269d3-150">For example, the following query retrieves product model IDs whose catalog descriptions do include specification.</span></span> <span data-ttu-id="269d3-151">À savoir que l'élément <`Specifications`> existe.</span><span class="sxs-lookup"><span data-stu-id="269d3-151">That is, the <`Specifications`> element exists.</span></span>  
  
```  
SELECT ProductModelID, CatalogDescription.query('  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
    declare namespace  pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
```  
  
 <span data-ttu-id="269d3-152">Dans la requête précédente, les deux méthodes **query()** et **exist()** déclarent le même espace de noms dans leur prologue.</span><span class="sxs-lookup"><span data-stu-id="269d3-152">In the previous query, both the **query()** and **exist()** methods declare the same namespace in their prolog.</span></span> <span data-ttu-id="269d3-153">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="269d3-153">For example:</span></span>  
  
```  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
```  
  
 <span data-ttu-id="269d3-154">Une autre méthode consiste à déclarer WITH XMLNAMESPACES au préalable et à utiliser les préfixes d'espace de noms dans la requête.</span><span class="sxs-lookup"><span data-stu-id="269d3-154">Alternatively, you can declare WITH XMLNAMESPACES first and use the namespace prefixes in the query.</span></span> <span data-ttu-id="269d3-155">Dans ce cas, il n’est pas nécessaire que les méthodes **query()** et **exist()** incluent les déclarations d’espace de noms dans leurs prologues.</span><span class="sxs-lookup"><span data-stu-id="269d3-155">In this case, the **query()** and **exist()** methods  do not have to include namespace declarations in their prolog.</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' as pd)  
SELECT ProductModelID, CatalogDescription.query('  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
Go  
```  
  
 <span data-ttu-id="269d3-156">Notez qu'une déclaration explicite dans le prologue XQuery remplace le préfixe d'espace de noms et l'espace de noms d'élément par défaut qui sont définis dans la clause WITH.</span><span class="sxs-lookup"><span data-stu-id="269d3-156">Note that an explicit declaration in the XQuery prolog overrides the namespace prefix and the default element namespace that are defined in the WITH clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269d3-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="269d3-157">See Also</span></span>  
 <span data-ttu-id="269d3-158">[méthodes de type de données xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="269d3-158">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="269d3-159">[Références relatives au langage Xquery &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span><span class="sxs-lookup"><span data-stu-id="269d3-159">[XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span></span>  
 <span data-ttu-id="269d3-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span><span class="sxs-lookup"><span data-stu-id="269d3-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span></span>  
 [<span data-ttu-id="269d3-161">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="269d3-161">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
