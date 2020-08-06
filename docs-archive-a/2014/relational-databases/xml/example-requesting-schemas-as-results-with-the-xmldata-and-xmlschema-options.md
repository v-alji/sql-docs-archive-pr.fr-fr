---
title: 'Exemple : demande de schémas comme résultats à l’aide des options XMLDATA et XMLSCHEMA | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, requesting schema example
- RAW mode, with XMLDATA and XMLSCHEMA
ms.assetid: 3504ca38-be66-42b2-8dab-f499c9584840
author: rothja
ms.author: jroth
ms.openlocfilehash: af244e3436df4d8665079ce20fb749a44021fe04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707327"
---
# <a name="example-requesting-schemas-as-results-with-the-xmldata-and-xmlschema-options"></a><span data-ttu-id="0b2f6-102">Exemple : demande de schémas comme résultats à l'aide des options XMLDATA et XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="0b2f6-102">Example: Requesting Schemas as Results with the XMLDATA and XMLSCHEMA Options</span></span>
  <span data-ttu-id="0b2f6-103">La requête suivante retourne le schéma XML-DATA qui décrit la structure du document.</span><span class="sxs-lookup"><span data-stu-id="0b2f6-103">The following query returns the XML-DATA schema that describes the document structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b2f6-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="0b2f6-104">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, XMLDATA  
GO  
```  
  
 <span data-ttu-id="0b2f6-105">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="0b2f6-105">This is the result:</span></span>  
  
```  
<Schema name="Schema1" xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:datatypes">  
  <ElementType name="row" content="empty" model="closed">  
    <AttributeType name="ProductModelID" dt:type="i4" />  
    <AttributeType name="Name" dt:type="string" />  
    <attribute type="ProductModelID" />  
    <attribute type="Name" />  
  </ElementType>  
</Schema>  
<row xmlns="x-schema:#Schema1" ProductModelID="122" Name="All-Purpose Bike Stand" />  
<row xmlns="x-schema:#Schema1" ProductModelID="119" Name="Bike Wash" />  
```  
  
> [!NOTE]
>  <span data-ttu-id="0b2f6-106"><`Schema`> est déclaré en tant qu'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="0b2f6-106">The <`Schema`> is declared as a namespace.</span></span> <span data-ttu-id="0b2f6-107">Pour éviter les conflits d'espaces de noms lorsque plusieurs schémas XML-Data sont interrogés dans des requêtes FOR XML différentes, l'identificateur d'espace de noms, `Schema1` dans cet exemple, est modifié à chaque exécution de requête.</span><span class="sxs-lookup"><span data-stu-id="0b2f6-107">To avoid namespace collisions when multiple XML-Data schemas are requested in different FOR XML queries, the namespace identifier, `Schema1` in this example, changes with every query execution.</span></span> <span data-ttu-id="0b2f6-108">L’identificateur d’espace de noms est composé de **Schema_n_** où **_n_** est un entier.</span><span class="sxs-lookup"><span data-stu-id="0b2f6-108">The namespace identifier is made up of **Schema_n_** where **_n_** is an integer.</span></span>  
  
 <span data-ttu-id="0b2f6-109">En spécifiant l'option `XMLSCHEMA` , vous pouvez demander le schéma XSD pour le résultat.</span><span class="sxs-lookup"><span data-stu-id="0b2f6-109">By specifying the `XMLSCHEMA` option, you can request the XSD schema for the result.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, XMLSCHEMA  
GO  
```  
  
 <span data-ttu-id="0b2f6-110">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="0b2f6-110">This is the result:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="row">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="122" Name="All-Purpose Bike Stand" />  
<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="119" Name="Bike Wash" />  
  
```  
  
 <span data-ttu-id="0b2f6-111">Vous pouvez spécifier l'URI d'espace de noms cible comme argument facultatif de XMLSCHEMA dans FOR XML.</span><span class="sxs-lookup"><span data-stu-id="0b2f6-111">You can specify the target namespace URI as an optional argument to XMLSCHEMA in FOR XML.</span></span> <span data-ttu-id="0b2f6-112">Cela retourne l'espace de noms cible spécifié dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="0b2f6-112">This returns the specified target namespace in the schema.</span></span> <span data-ttu-id="0b2f6-113">Cet espace de noms cible reste le même chaque fois que vous exécutez la requête.</span><span class="sxs-lookup"><span data-stu-id="0b2f6-113">This target namespace remains the same every time you execute the query.</span></span> <span data-ttu-id="0b2f6-114">Par exemple, la version modifiée ci-dessous de la requête précédente inclut l'URI d'espace de noms, `'urn:example.com'`, comme argument.</span><span class="sxs-lookup"><span data-stu-id="0b2f6-114">For example, the following modified version of the previous query includes the namespace URI, `'urn:example.com'`, as an argument.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, XMLSCHEMA ('urn:example.com')  
GO  
```  
  
 <span data-ttu-id="0b2f6-115">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="0b2f6-115">This is the result:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:example.com" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="row">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<row xmlns="urn:example.com" ProductModelID="122" Name="All-Purpose Bike Stand" />  
<row xmlns="urn:example.com" ProductModelID="119" Name="Bike Wash" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b2f6-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b2f6-116">See Also</span></span>  
 [<span data-ttu-id="0b2f6-117">Utiliser le mode RAW avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="0b2f6-117">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
