---
title: Générer un schéma XSD en ligne | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- XMLSCHEMA option
- schemas [SQL Server], XML
- XDR schemas
- FOR XML clause, inline XSD schema generation
- inline XSD schema generation [SQL Server]
- XMLDATA option
ms.assetid: 04b35145-1cca-45f4-9eb7-990abf2e647d
author: rothja
ms.author: jroth
ms.openlocfilehash: 2af748d4fc6ae67f57568be58ec7f59876098f52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710432"
---
# <a name="generate-an-inline-xsd-schema"></a><span data-ttu-id="b496e-102">Générer un schéma XSD en ligne</span><span class="sxs-lookup"><span data-stu-id="b496e-102">Generate an Inline XSD Schema</span></span>
  <span data-ttu-id="b496e-103">Dans une clause FOR XML, vous pouvez demander que votre requête retourne un schéma en ligne avec les résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="b496e-103">In a FOR XML clause, you can request that your query return an inline schema together with the query results.</span></span> <span data-ttu-id="b496e-104">Pour obtenir un schéma XDR, utilisez le mot clé XMLDATA dans la clause FOR XML.</span><span class="sxs-lookup"><span data-stu-id="b496e-104">If you want an XDR schema, you use the XMLDATA keyword in the FOR XML clause.</span></span> <span data-ttu-id="b496e-105">Pour obtenir un schéma XSD, utilisez le mot clé XMLSCHEMA.</span><span class="sxs-lookup"><span data-stu-id="b496e-105">If you want an XSD schema, you use the XMLSCHEMA keyword.</span></span>  
  
 <span data-ttu-id="b496e-106">Cette rubrique décrit le mot clé XMLSCHEMA et explique la structure du schéma XSD en ligne résultant.</span><span class="sxs-lookup"><span data-stu-id="b496e-106">This topic describes the XMLSCHEMA keyword and explains the structure of the resulting inline XSD schema.</span></span> <span data-ttu-id="b496e-107">Les limites suivantes sont à respecter lorsque vous demandez des schémas en ligne :</span><span class="sxs-lookup"><span data-stu-id="b496e-107">Following are the limitations when you are requesting inline schemas:</span></span>  
  
-   <span data-ttu-id="b496e-108">Vous pouvez spécifier XMLSCHEMA seulement en mode RAW et AUTO, pas en mode EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="b496e-108">You can specify XMLSCHEMA only in RAW and AUTO mode, not in EXPLICIT mode.</span></span>  
  
-   <span data-ttu-id="b496e-109">Si une requête FOR XML imbriquée spécifie la directive TYPE, le résultat de la requête est de type `xml` et ce résultat est traité comme une instance de données XML non typées.</span><span class="sxs-lookup"><span data-stu-id="b496e-109">If a nested FOR XML query specifies the TYPE directive, the query result is of `xml` type, and this result is treated as an instance of untyped XML data.</span></span> <span data-ttu-id="b496e-110">Pour plus d’informations, consultez [Données XML &#40;SQL Server&#41;](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b496e-110">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="b496e-111">Lorsque vous spécifiez XMLSCHEMA dans une requête FOR XML, vous recevez à la fois un schéma et des données XML, le résultat de la requête.</span><span class="sxs-lookup"><span data-stu-id="b496e-111">When you specify XMLSCHEMA in a FOR XML query, you receive both a schema and XML data, the query result.</span></span> <span data-ttu-id="b496e-112">Chaque élément de niveau supérieur des données fait référence au schéma précédent en utilisant une déclaration d'espace de noms qui, à son tour, fait référence à l'espace de noms cible du schéma en ligne.</span><span class="sxs-lookup"><span data-stu-id="b496e-112">Each top-level element of the data refers to the previous schema by using a default namespace declaration that, in turn, refers to the target namespace of the inline schema.</span></span>  
  
 <span data-ttu-id="b496e-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b496e-113">For example:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks2012].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<Production.ProductModel xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="1" Name="Classic Vest" />  
```  
  
 <span data-ttu-id="b496e-114">Le résultat inclut un schéma XML et le résultat XML.</span><span class="sxs-lookup"><span data-stu-id="b496e-114">The result includes XML schema and the XML result.</span></span> <span data-ttu-id="b496e-115">L'élément de niveau supérieur <`ProductModel`> dans le résultat fait référence au schéma en utilisant la déclaration d'espace de noms par défaut, xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" .</span><span class="sxs-lookup"><span data-stu-id="b496e-115">The <`ProductModel`> top-level element in the result refers to the schema by using the default namespace declaration, xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" .</span></span>  
  
 <span data-ttu-id="b496e-116">La partie schéma du résultat peut contenir plusieurs documents de schéma qui décrivent plusieurs espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="b496e-116">The schema part of the result may contain multiple schema documents that describe multiple namespaces.</span></span> <span data-ttu-id="b496e-117">Au minimum, le deux documents de schéma ci-dessous sont retournés :</span><span class="sxs-lookup"><span data-stu-id="b496e-117">At a minimum, the following two schema documents are returned:</span></span>  
  
-   <span data-ttu-id="b496e-118">Un document de schéma pour l’espace de noms **Sqltypes** et pour lequel les types SQL de base sont retournés.</span><span class="sxs-lookup"><span data-stu-id="b496e-118">One schema document for the **Sqltypes** namespace, and for which the base SQL types are being returned.</span></span>  
  
-   <span data-ttu-id="b496e-119">Un autre document de schéma qui décrit la forme du résultat de la requête FOR XML.</span><span class="sxs-lookup"><span data-stu-id="b496e-119">Another schema document that describes the shape of the FOR XML query result.</span></span>  
  
 <span data-ttu-id="b496e-120">En outre, si des types de données `xml` typées sont inclus dans le résultat de la requête, les schémas associés avec ces types de données `xml` typés sont inclus.</span><span class="sxs-lookup"><span data-stu-id="b496e-120">Also, if any typed `xml` data types are included in the query result, the schemas associated with those typed `xml` data types are included.</span></span>  
  
 <span data-ttu-id="b496e-121">L'espace de noms cible du document de schéma qui décrit la forme du résultat FOR XML contient une partie fixe et une partie numérique incrémentée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b496e-121">The target namespace of the schema document that describes the shape of the FOR XML result contains a fixed portion and a numeric portion that increments automatically.</span></span> <span data-ttu-id="b496e-122">Le format de cet espace de noms est illustré dans ce qui suit, où *n* est un entier positif.</span><span class="sxs-lookup"><span data-stu-id="b496e-122">The format of this namespace is shown in the following where *n* is a positive integer.</span></span> <span data-ttu-id="b496e-123">Par exemple, dans la requête précédente, urn:schemas-microsoft-com:sql:SqlRowSet1 est l'espace de noms cible.</span><span class="sxs-lookup"><span data-stu-id="b496e-123">For example, in the previous query, urn:schemas-microsoft-com:sql:SqlRowSet1 is the target namespace.</span></span>  
  
```  
urn:schemas-microsoft-com:sql:SqlRowSetn  
```  
  
 <span data-ttu-id="b496e-124">La modification dans les espaces de noms cibles du résultat qui s'est produite d'une exécution à l'autre peut ne pas être souhaitée.</span><span class="sxs-lookup"><span data-stu-id="b496e-124">The change in the target namespaces in the result that occurred from one execution to another may not be desirable.</span></span> <span data-ttu-id="b496e-125">Par exemple, si vous interrogez les données XML résultantes, la modification dans l'espace de noms cible requiert que vous mettiez à jour votre requête.</span><span class="sxs-lookup"><span data-stu-id="b496e-125">For example, if you query the resulting XML, the change in target namespace will require that you update your query.</span></span> <span data-ttu-id="b496e-126">Vous pouvez éventuellement spécifier un espace de noms cible lorsque l'option XMLSCHEMA est ajoutée dans la clause FOR XML.</span><span class="sxs-lookup"><span data-stu-id="b496e-126">You can optionally specify a target namespace when the XMLSCHEMA option is added in the FOR XML clause.</span></span> <span data-ttu-id="b496e-127">Les données XML résultantes incluront l'espace de noms spécifié et resteront les mêmes, quel que soit le nombre de fois que vous exécutez la requête.</span><span class="sxs-lookup"><span data-stu-id="b496e-127">The resulting XML will include the namespace you provided and will remain the same, regardless of how many times you run the query.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM   Production.ProductModel  
WHERE ProductModelID=1  
FOR XML AUTO, XMLSCHEMA ('MyURI')  
```  
  
## <a name="entity-elements"></a><span data-ttu-id="b496e-128">Éléments d'entité</span><span class="sxs-lookup"><span data-stu-id="b496e-128">Entity Elements</span></span>  
 <span data-ttu-id="b496e-129">Pour pouvoir analyser les détails de la structure de schéma XSD générée pour le résultat de la requête, l'élément d'entité doit être décrit au préalable</span><span class="sxs-lookup"><span data-stu-id="b496e-129">In order to discuss the details of the XSD schema structure generated for the query result, the entity element has to first be described</span></span>  
  
 <span data-ttu-id="b496e-130">Un élément d'entité dans les données XML retournées par une requête FOR XML est un élément généré à partir d'une table et non pas à partir d'une colonne.</span><span class="sxs-lookup"><span data-stu-id="b496e-130">An entity element in the XML data returned by FOR XML query is an element that is generated from a table and not from a column.</span></span> <span data-ttu-id="b496e-131">Par exemple, la requête FOR XML ci-dessous retourne des informations de contact à partir de la table `Person` dans la base de données `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="b496e-131">For example, the following FOR XML query returns contact information from the `Person` table in the `AdventureWorks2012` database.</span></span>  
  
```  
SELECT BusinessEntityID, FirstName  
FROM Person.Person  
WHERE BusinessEntityID = 1  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="b496e-132">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="b496e-132">This is the result:</span></span>  
  
 `<Person>`  
  
 `<BusinessEntityID>1</BusinessEntityID>`  
  
 `<FirstName>Ken</FirstName>`  
  
 `</Person>`  
  
 <span data-ttu-id="b496e-133">Dans ce résultat, <`Person`> est l'élément d'entité.</span><span class="sxs-lookup"><span data-stu-id="b496e-133">In this result, <`Person`> is the entity element.</span></span> <span data-ttu-id="b496e-134">Plusieurs éléments d'entité peuvent exister dans le résultat XML et chacun de ces éléments possède une déclaration globale dans le schéma XSD en ligne.</span><span class="sxs-lookup"><span data-stu-id="b496e-134">There can be multiple entity elements in the XML result and each of these has a global declaration in the inline XSD schema.</span></span> <span data-ttu-id="b496e-135">Par exemple, la requête ci-dessous récupère l'en-tête de commande et les informations détaillées d'une commande spécifique.</span><span class="sxs-lookup"><span data-stu-id="b496e-135">For example, the following query retrieves sales order header and detail information for a specific order.</span></span>  
  
```  
SELECT  SalesOrderHeader.SalesOrderID, ProductID, OrderQty  
FROM    Sales.SalesOrderHeader, Sales.SalesOrderDetail  
WHERE   SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
AND     SalesOrderHeader.SalesOrderID=5001  
FOR XML AUTO, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="b496e-136">Comme la requête spécifie la directive ELEMENTS, les données XML résultantes sont centrées sur les éléments.</span><span class="sxs-lookup"><span data-stu-id="b496e-136">Because the query specifies the ELEMENTS directive, the resulting XML is element-centric.</span></span> <span data-ttu-id="b496e-137">La requête spécifie également la directive XMLSCHEMA.</span><span class="sxs-lookup"><span data-stu-id="b496e-137">The query also specifies the XMLSCHEMA directive.</span></span> <span data-ttu-id="b496e-138">Par conséquent, un schéma XSD en ligne est retourné.</span><span class="sxs-lookup"><span data-stu-id="b496e-138">Therefore, an inline XSD schema is returned.</span></span> <span data-ttu-id="b496e-139">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="b496e-139">This is the result:</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="Sales.SalesOrderHeader">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="SalesOrderID" type="sqltypes:int" />`  
  
 `<xsd:element ref="schema:Sales.SalesOrderDetail" minOccurs="0" maxOccurs="unbounded" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `<xsd:element name="Sales.SalesOrderDetail">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="OrderQty" type="sqltypes:smallint" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 <span data-ttu-id="b496e-140">Notez les points suivants dans la requête précédente :</span><span class="sxs-lookup"><span data-stu-id="b496e-140">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="b496e-141">Dans le résultat, <`SalesOrderHeader`> et <`SalesOrderDetail`> sont des éléments d'entité.</span><span class="sxs-lookup"><span data-stu-id="b496e-141">In the result, <`SalesOrderHeader`> and <`SalesOrderDetail`> are entity elements.</span></span> <span data-ttu-id="b496e-142">Pour cette raison, ils sont déclarés globalement dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="b496e-142">Because of this, they are globally declared in the schema.</span></span> <span data-ttu-id="b496e-143">Ainsi, la déclaration apparaît au plus haut niveau au sein de l'élément <`Schema`>.</span><span class="sxs-lookup"><span data-stu-id="b496e-143">That is, the declaration appears at the top level inside the <`Schema`> element.</span></span>  
  
-   <span data-ttu-id="b496e-144"><`SalesOrderID`>, <`ProductID`> et <`OrderQty`> ne sont pas des éléments d'entité, car ils sont mappés avec des colonnes.</span><span class="sxs-lookup"><span data-stu-id="b496e-144">The <`SalesOrderID`>, <`ProductID`>, and <`OrderQty`> are not entity elements, because they map to columns.</span></span> <span data-ttu-id="b496e-145">Les données de colonne sont retournées en tant qu'éléments dans les données XML, en raison de la directive ELEMENTS.</span><span class="sxs-lookup"><span data-stu-id="b496e-145">The column data is returned as elements in the XML, because of the ELEMENTS directive.</span></span> <span data-ttu-id="b496e-146">Elles sont mappées avec les éléments locaux du type complexe de l'élément d'entité.</span><span class="sxs-lookup"><span data-stu-id="b496e-146">These are mapped to local elements of the entity element's complex type.</span></span> <span data-ttu-id="b496e-147">Notez que si la directive ELEMENTS n'est pas spécifiée, les valeurs `SalesOrderID`, `ProductID` et `OrderQty` sont mappées avec les attributs locaux du type complexe de l'élément d'entité correspondant.</span><span class="sxs-lookup"><span data-stu-id="b496e-147">Note that if the ELEMENTS directive is not specified, the `SalesOrderID`, `ProductID` and `OrderQty` values are mapped to local attributes of the corresponding entity element's complex type.</span></span>  
  
## <a name="attribute-name-clashes"></a><span data-ttu-id="b496e-148">Conflits de noms d'attributs</span><span class="sxs-lookup"><span data-stu-id="b496e-148">Attribute Name Clashes</span></span>  
 <span data-ttu-id="b496e-149">La discussion suivante est basée sur les tables `CustOrder` et `CustOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="b496e-149">The following discussion is based on the `CustOrder` and `CustOrderDetail` tables.</span></span> <span data-ttu-id="b496e-150">Pour tester les exemples suivants, créez ces tables et ajoutez vos propres données d'exemple :</span><span class="sxs-lookup"><span data-stu-id="b496e-150">To test the following samples, create these tables and add your own sample data:</span></span>  
  
```  
CREATE TABLE CustOrder (OrderID int primary key, CustomerID int)  
GO  
CREATE TABLE CustOrderDetail (OrderID int, ProductID int, Qty int)  
GO  
```  
  
 <span data-ttu-id="b496e-151">Dans FOR XML, le même nom est parfois utilisé pour indiquer des propriétés ou des attributs différents.</span><span class="sxs-lookup"><span data-stu-id="b496e-151">In FOR XML, the same name is sometimes used to indicate different properties, attributes.</span></span> <span data-ttu-id="b496e-152">Par exemple, la requête ci-dessous en mode RAW centré sur les attributs génère deux attributs du même nom, OrderID.</span><span class="sxs-lookup"><span data-stu-id="b496e-152">For example, the following attribute-centric RAW mode query generates two attributes that have the same name, OrderID.</span></span> <span data-ttu-id="b496e-153">Cela génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="b496e-153">This generates an error.</span></span>  
  
```  
SELECT CustOrder.OrderID,   
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
FROM   dbo.CustOrder, dbo.CustOrderDetail  
WHERE  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA  
```  
  
 <span data-ttu-id="b496e-154">Toutefois, comme il est possible de disposer de deux éléments du même nom, vous pouvez éliminer le problème en ajoutant la directive ELEMENTS :</span><span class="sxs-lookup"><span data-stu-id="b496e-154">However, because it is acceptable to have two elements that have the same name, you can eliminate the problem by adding the ELEMENTS directive:</span></span>  
  
```  
SELECT CustOrder.OrderID,  
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
from   dbo.CustOrder, dbo.CustOrderDetail  
where  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA, ELEMENTS  
```  
  
 <span data-ttu-id="b496e-155">Voici l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="b496e-155">This is the result.</span></span> <span data-ttu-id="b496e-156">Notez dans le schéma XSD en ligne que l'élément OrderID est défini deux fois.</span><span class="sxs-lookup"><span data-stu-id="b496e-156">Note in the inline XSD schema, the OrderID element is defined two times.</span></span> <span data-ttu-id="b496e-157">Dans une des déclarations, minOccurs a la valeur 0, ce qui correspond à l'OrderID de la table CustOrderDetail, et l'autre déclaration est mappée avec la colonne clé primaire OrderID de la table `CustOrder` où minOccurs a la valeur 1 par défaut.</span><span class="sxs-lookup"><span data-stu-id="b496e-157">One of the declarations has minOccurs set to 0, corresponding to the OrderID from the CustOrderDetail table, and the second one maps to the OrderID primary key column of the `CustOrder` table where minOccurs is 1 by default.</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" />`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" minOccurs="0" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
## <a name="element-name-clashes"></a><span data-ttu-id="b496e-158">Conflits de noms d'éléments</span><span class="sxs-lookup"><span data-stu-id="b496e-158">Element Name Clashes</span></span>  
 <span data-ttu-id="b496e-159">Dans FOR XML, le même nom peut être utilisé pour indiquer deux sous-éléments.</span><span class="sxs-lookup"><span data-stu-id="b496e-159">In FOR XML, the same name can be used to indicate two subelements.</span></span> <span data-ttu-id="b496e-160">Par exemple, la requête ci-dessous récupère les valeurs ListPrice et DealerPrice des produits, mais la requête spécifie le même alias, Price, pour ces deux colonnes.</span><span class="sxs-lookup"><span data-stu-id="b496e-160">For example, the following query retrieves ListPrice and DealerPrice values of products, but the query specifies the same alias, Price, for these two columns.</span></span> <span data-ttu-id="b496e-161">Par conséquent, l'ensemble de lignes résultant possèdera deux colonnes du même nom.</span><span class="sxs-lookup"><span data-stu-id="b496e-161">Therefore, the resulting rowset will have two columns with same name.</span></span>  
  
### <a name="case-1-both-subelements-are-nonkey-columns-of-the-same-type-and-can-be-null"></a><span data-ttu-id="b496e-162">Cas n° 1 : les deux sous-éléments sont des colonnes non-clés du même type et acceptent la valeur NULL</span><span class="sxs-lookup"><span data-stu-id="b496e-162">Case 1: Both subelements are nonkey columns of the same type and can be NULL</span></span>  
 <span data-ttu-id="b496e-163">Dans la requête ci-dessous, les deux sous-éléments sont des colonnes non-clés du même type et ils acceptent la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="b496e-163">In the following query, both subelements are nonkey columns of the same type and can be NULL.</span></span>  
  
```  
DROP TABLE T  
go  
CREATE TABLE T (ProductID int primary key, ListPrice money, DealerPrice money)  
go  
INSERT INTO T values (1, 1.25, null)  
go  
  
SELECT ProductID, ListPrice Price, DealerPrice Price  
FROM   T  
for    XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="b496e-164">Ceci représente le schéma XML correspondant généré.</span><span class="sxs-lookup"><span data-stu-id="b496e-164">This is the corresponding XML generated.</span></span> <span data-ttu-id="b496e-165">Seule une fraction du schéma XSD en ligne est indiquée :</span><span class="sxs-lookup"><span data-stu-id="b496e-165">Only a fraction of the inline XSD is shown:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" minOccurs="0" maxOccurs="2" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `</row>`  
  
 <span data-ttu-id="b496e-166">Notez les éléments suivants dans le schéma XSD en ligne :</span><span class="sxs-lookup"><span data-stu-id="b496e-166">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="b496e-167">ListPrice et DealerPrice sont du même type, `money`, et les deux acceptent la valeur NULL dans la table.</span><span class="sxs-lookup"><span data-stu-id="b496e-167">Both the ListPrice and DealerPrice are of the same type, `money`, and both can be NULL in the table.</span></span> <span data-ttu-id="b496e-168">Par conséquent, comme ils peuvent ne pas être retournés dans les données XML résultantes, il existe un seul élément enfant <`Price`> dans la déclaration de type complexe de l'élément <`row`> pour lequel minOccurs=0 et maxOccurs=2.</span><span class="sxs-lookup"><span data-stu-id="b496e-168">Therefore, because they may not be returned in the resulting XML, there is only one <`Price`> child element in the complex type declaration of the <`row`> element that has minOccurs=0 and maxOccurs=2.</span></span>  
  
-   <span data-ttu-id="b496e-169">Dans le résultat, comme `DealerPrice` a une valeur NULL dans la table, seul `ListPrice` est retourné comme élément <`Price`>.</span><span class="sxs-lookup"><span data-stu-id="b496e-169">In the result, because the `DealerPrice` value is NULL in the table, only `ListPrice` is returned as a <`Price`> element.</span></span> <span data-ttu-id="b496e-170">Si vous ajoutez le paramètre `XSINIL` à la directive ELEMENTS, vous recevrez les deux éléments pour lesquels `xsi:nil` a pour valeur TRUE pour l’élément <`Price`> qui correspond à DealerPrice.</span><span class="sxs-lookup"><span data-stu-id="b496e-170">If you add the `XSINIL` parameter to the ELEMENTS directive, you will receive both of the elements that have the `xsi:nil` value set to TRUE for the<`Price`> element that corresponds to DealerPrice.</span></span> <span data-ttu-id="b496e-171">Vous recevrez aussi deux éléments enfants <`Price`> dans la définition de type complexe <`row`> dans le schéma XSD en ligne avec l'attribut `nillable` ayant la valeur TRUE pour les deux.</span><span class="sxs-lookup"><span data-stu-id="b496e-171">You will also receive two <`Price`> child elements in the <`row`> complex type definition in the inline XSD schema with the `nillable` attribute set to TRUE for both.</span></span> <span data-ttu-id="b496e-172">Ce fragment est un résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="b496e-172">This fragment is a partial result:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `<Price xsi:nil="true" />`  
  
 `</row>`  
  
### <a name="case-2-one-key-and-one-nonkey-column-of-the-same-type"></a><span data-ttu-id="b496e-173">Cas n° 2 : une colonne clé et une colonne non-clé du même type</span><span class="sxs-lookup"><span data-stu-id="b496e-173">Case 2: One key and one nonkey column of the same type</span></span>  
 <span data-ttu-id="b496e-174">La requête ci-dessous illustre une colonne clé et une colonne non-clé du même type.</span><span class="sxs-lookup"><span data-stu-id="b496e-174">The following query illustrates one key and one nonkey column of the same type.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 int, Col3 nvarchar(20))  
go  
INSERT INTO T VALUES (1, 1, 'test')  
go   
```  
  
 <span data-ttu-id="b496e-175">La requête ci-dessous exécutée sur la table **T** spécifie le même alias pour Col1 et Col2, où Col1 est une clé primaire et ne peut pas avoir la valeur NULL, alors que Col2 accepte la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="b496e-175">The following query against table **T** specifies the same alias for Col1 and Col2, where Col1 is a primary key and cannot be null, and Col2 can be null.</span></span> <span data-ttu-id="b496e-176">Cela génère deux éléments frères qui sont des enfants de l'élément <`row`>.</span><span class="sxs-lookup"><span data-stu-id="b496e-176">This generates two sibling elements that are children of the <`row`> element.</span></span>  
  
```  
SELECT Col1 as Col, Col2 as Col, Col3  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="b496e-177">Voici l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="b496e-177">This is the result.</span></span> <span data-ttu-id="b496e-178">Seul un fragment du schéma XSD en ligne est indiqué :</span><span class="sxs-lookup"><span data-stu-id="b496e-178">Only a fragment of the inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="Col3" minOccurs="0">`  
  
 `<xsd:simpleType>`  
  
 `<xsd:restriction base="sqltypes:nvarchar"`  
  
 `sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth"`  
  
 `sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `</xsd:element>`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col>1</Col>`  
  
 `<Col>1</Col>`  
  
 `<Col3>test</Col3>`  
  
 `</row>`  
  
 <span data-ttu-id="b496e-179">Notez dans le schéma XSD en ligne que l'élément <`Col`> correspondant à Col2 a une valeur minOccurs égale à 0.</span><span class="sxs-lookup"><span data-stu-id="b496e-179">Note in the inline XSD schema that the <`Col`> element corresponding to the Col2 has minOccurs set to 0.</span></span>  
  
### <a name="case-3-both-elements-of-different-types-and-corresponding-columns-can-be-null"></a><span data-ttu-id="b496e-180">Cas n° 3 : les deux éléments sont de types différents et les colonnes correspondantes acceptent la valeur NULL</span><span class="sxs-lookup"><span data-stu-id="b496e-180">Case 3: Both elements of different types and corresponding columns can be NULL</span></span>  
 <span data-ttu-id="b496e-181">La requête ci-dessous est spécifiée sur l'exemple de table défini dans le cas 2 :</span><span class="sxs-lookup"><span data-stu-id="b496e-181">The following query is specified against the sample table shown in case 2:</span></span>  
  
```  
SELECT Col1, Col2 as Col, Col3 as Col  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="b496e-182">Dans la requête ci-dessous, Col2 et Col3 obtiennent les mêmes alias.</span><span class="sxs-lookup"><span data-stu-id="b496e-182">In the following query, Col2 and Col3 are given the same aliases.</span></span> <span data-ttu-id="b496e-183">Cela génère deux éléments frères du même nom, qui sont tous les deux des enfants de l'élément <`raw`> dans le résultat.</span><span class="sxs-lookup"><span data-stu-id="b496e-183">This generates two sibling elements that have the same name and that are both children of the <`raw`> element in the result.</span></span> <span data-ttu-id="b496e-184">Ces deux colonnes sont de types différents et acceptent la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="b496e-184">Both of these columns are of different types and both can be NULL.</span></span> <span data-ttu-id="b496e-185">Voici l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="b496e-185">This is the result.</span></span> <span data-ttu-id="b496e-186">Seul le schéma XSD en ligne partielle est indiqué.</span><span class="sxs-lookup"><span data-stu-id="b496e-186">Only partial inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:simpleType name="Col1">`  
  
 `<xsd:restriction base="sqltypes:int" />`  
  
 `</xsd:simpleType>`  
  
 `<xsd:simpleType name="Col2">`  
  
 `<xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col1" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" minOccurs="0" maxOccurs="2" type="xsd:anySimpleType" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col1>1</Col1>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col1">1</Col>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col2">test</Col>`  
  
 `</row>`  
  
 <span data-ttu-id="b496e-187">Notez les éléments suivants dans le schéma XSD en ligne :</span><span class="sxs-lookup"><span data-stu-id="b496e-187">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="b496e-188">Comme Col2 et Col3 acceptent la valeur NULL, la déclaration d'élément <`Col`> spécifie une valeur minOccurs égale à 0 et une valeur maxOccurs égale à 2.</span><span class="sxs-lookup"><span data-stu-id="b496e-188">Because both Col2 and Col3 can be NULL, the <`Col`> element declaration specifies the minOccurs as 0 and maxOccurs as 2.</span></span>  
  
-   <span data-ttu-id="b496e-189">Comme les deux éléments <`Col`> sont frères, le schéma contient une seule déclaration d'élément.</span><span class="sxs-lookup"><span data-stu-id="b496e-189">Because both the <`Col`> elements are siblings, there is one element declaration in the schema.</span></span> <span data-ttu-id="b496e-190">En outre, comme les deux éléments sont également de types différents, bien qu'ils soient tous les deux d'un type simple, le type de l'élément dans le schéma est `xsd:anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="b496e-190">Also, because both of the elements are also of different types, though both are simple types, the type of the element in the schema is `xsd:anySimpleType`.</span></span> <span data-ttu-id="b496e-191">Dans le résultat, chaque type d'instance est identifié par l'attribut `xsi:type` .</span><span class="sxs-lookup"><span data-stu-id="b496e-191">In the result, each instance type is identified by the `xsi:type` attribute.</span></span>  
  
-   <span data-ttu-id="b496e-192">Dans le résultat, chaque instance de l'élément <`Col`> fait référence à son type d'instance en utilisant l'attribut `xsi:type`.</span><span class="sxs-lookup"><span data-stu-id="b496e-192">In the result, every instance of the <`Col`> element refers to its instance type by using the `xsi:type` attribute.</span></span>  
  
  
