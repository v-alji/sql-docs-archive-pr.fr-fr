---
title: Façonner des données XML avec des requêtes FOR XML imbriquées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], nested FOR XML
- XML [SQL Server], FOR XML queries
ms.assetid: 8dc42c05-16e8-4b7b-a5d3-550b55acae26
author: rothja
ms.author: jroth
ms.openlocfilehash: 738b5b3ec67dada90c851d284ccc8b3009a51aa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611631"
---
# <a name="shape-xml-with-nested-for-xml-queries"></a><span data-ttu-id="b7c26-102">Façonner des données XML avec des requêtes FOR XML imbriquées</span><span class="sxs-lookup"><span data-stu-id="b7c26-102">Shape XML with Nested FOR XML Queries</span></span>
  <span data-ttu-id="b7c26-103">L'exemple suivant interroge la table `Production.Product` pour extraire les valeurs `ListPrice` et `StandardCost` d'un produit spécifique.</span><span class="sxs-lookup"><span data-stu-id="b7c26-103">The following example queries the `Production.Product` table to retrieve the `ListPrice` and `StandardCost` values of a specific product.</span></span> <span data-ttu-id="b7c26-104">Pour rendre la requête intéressante, les deux prix sont renvoyés dans un élément <`Price`> et chaque élément <`Price`> possède un attribut `PriceType`.</span><span class="sxs-lookup"><span data-stu-id="b7c26-104">To make the query interesting, both prices are returned in a <`Price`> element, and each <`Price`> element has a `PriceType` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7c26-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="b7c26-105">Example</span></span>  
 <span data-ttu-id="b7c26-106">Voici la forme attendue du document XML :</span><span class="sxs-lookup"><span data-stu-id="b7c26-106">This is the expected shape of the XML:</span></span>  
  
```  
<xsd:schema xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet2" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet2" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.Product" type="xsd:anyType" />  
</xsd:schema>  
<Production.Product xmlns="urn:schemas-microsoft-com:sql:SqlRowSet2" ProductID="520">  
  <Price xmlns="" PriceType="ListPrice">133.34</Price>  
  <Price xmlns="" PriceType="StandardCost">98.77</Price>  
</Production.Product>  
```  
  
 <span data-ttu-id="b7c26-107">Voici la requête FOR XML imbriquée :</span><span class="sxs-lookup"><span data-stu-id="b7c26-107">This is the nested FOR XML query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Product.ProductID,   
          (SELECT 'ListPrice' as PriceType,   
                   CAST(CAST(ListPrice as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE),  
          (SELECT  'StandardCost' as PriceType,   
                   CAST(CAST(StandardCost as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE)  
FROM Production.Product  
WHERE ProductID=520  
for XML AUTO, TYPE, XMLSCHEMA  
```  
  
 <span data-ttu-id="b7c26-108">Notez les points suivants dans la requête précédente :</span><span class="sxs-lookup"><span data-stu-id="b7c26-108">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="b7c26-109">L’instruction SELECT externe construit l’élément <`Product`> qui possède un attribut **ProductID** et deux éléments enfants <`Price`>.</span><span class="sxs-lookup"><span data-stu-id="b7c26-109">The outer SELECT statement constructs the <`Product`> element that has a **ProductID** attribute and two <`Price`> child elements.</span></span>  
  
-   <span data-ttu-id="b7c26-110">Les deux instructions SELECT internes construisent deux éléments <`Price`>, possédant chacun un attribut **PriceType** et des données XML qui renvoient le prix du produit.</span><span class="sxs-lookup"><span data-stu-id="b7c26-110">The two inner SELECT statements construct two <`Price`> elements, each with a **PriceType** attribute and XML that returns the product price.</span></span>  
  
-   <span data-ttu-id="b7c26-111">La directive XMLSCHEMA figurant dans l'instruction SELECT externe génère le schéma XSD en ligne qui décrit la forme du document XML obtenu.</span><span class="sxs-lookup"><span data-stu-id="b7c26-111">The XMLSCHEMA directive in the outer SELECT statement generates the inline XSD schema that describes the shape of the resulting XML.</span></span>  
  
 <span data-ttu-id="b7c26-112">Pour rendre la requête intéressante, vous pouvez écrire la requête FOR XML puis écrire une requête XQuery par rapport au résultat afin de redéfinir la forme du document XML, comme le montre la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="b7c26-112">To make the query interesting, you can write the FOR XML query and then write an XQuery against the result to reshape the XML, as shown in the following query:</span></span>  
  
```  
SELECT ProductID,   
 ( SELECT p2.ListPrice, p2.StandardCost  
   FROM Production.Product p2   
   WHERE Product.ProductID = p2.ProductID  
   FOR XML AUTO, ELEMENTS XSINIL, type ).query('  
                                   for $p in /p2/*  
                                   return   
                                    <Price PriceType = "{local-name($p)}">  
                                     { data($p) }  
                                    </Price>  
                                  ')  
FROM Production.Product  
WHERE ProductID = 520  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="b7c26-113">L'exemple précédent utilise la méthode `query()` du type de données `xml` pour interroger le document XML renvoyé par la requête FOR XML interne et construire le résultat attendu.</span><span class="sxs-lookup"><span data-stu-id="b7c26-113">The previous example uses the `query()` method of the `xml` data type to query the XML returned by the inner FOR XML query and construct the expected result.</span></span>  
  
 <span data-ttu-id="b7c26-114">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="b7c26-114">This is the result:</span></span>  
  
```  
<Production.Product ProductID="520">  
  <Price PriceType="ListPrice">133.3400</Price>  
  <Price PriceType="StandardCost">98.7700</Price>  
</Production.Product>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7c26-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7c26-115">See Also</span></span>  
 [<span data-ttu-id="b7c26-116">Utiliser des requêtes FOR XML imbriquées</span><span class="sxs-lookup"><span data-stu-id="b7c26-116">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
